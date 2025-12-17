# Bank


  if (!rek || !nominal) {
    alert("Lengkapi data transfer");
    return;
  }

  if (nominal > saldo) {
    alert("Saldo tidak cukup");
    return;
  }

  saldo -= nominal;
  riwayat.unshift(`Transfer Rp ${nominal.toLocaleString("id-ID")} ke ${rek}`);
  localStorage.setItem("riwayat", JSON.stringify(riwayat));

  updateSaldo();
  alert("Transfer berhasil");
  showScreen("home");
}

function loadRiwayat() {
  const list = document.getElementById("riwayatList");
  list.innerHTML = "";
  riwayat.forEach(item => {
    const li = document.createElement("li");
    li.innerText = item;
    list.appendChild(li);
  });
}

document.addEventListener("click", () => {
  if (document.getElementById("riwayat").classList.contains("active")) {
    loadRiwayat();
  }
});

{
  "name": "MyBank Mobile",
  "short_name": "MyBank",
  "start_url": "index.html",
  "display": "standalone",
  "background_color": "#0d47a1",
  "theme_color": "#0d47a1"
}
