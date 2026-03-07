import React, { useState, useMemo } from 'react';
import { 
  Users, 
  LayoutDashboard, 
  Wallet, 
  Settings, 
  Search, 
  Filter, 
  ChevronRight, 
  UserCircle,
  FileText,
  MapPin,
  GraduationCap,
  CreditCard,
  X,
  CheckCircle2,
  Clock,
  FileCheck,
  FileX,
  BookOpen,
  Award,
  School,
  Briefcase,
  Loader2
} from 'lucide-react';

// --- MOCK DATA BERDASARKAN STRUKTUR 3 TABEL (NORMALISASI) ---
const mockSantri = [
  {
    // Tabel 1: Database Utama
    id: "SD-20250002",
    namaLengkap: "Ameera ayatul yamania",
    nipd: "-",
    nisn: "-",
    status: "Aktif",
    jenjang: "SD",
    halaqoh: "-",
    dapodik: "Belum Terdaftar",
    musyrif: "-",
    tahunMasuk: "2025",
    registrasi: "Belum Selesai",
    kelas: "I - A",
    keterangan: "Aktif",
    sppBulanan: "-",
    jenisKelamin: "PUTRI",
    ttl: "- / -",
    nik: "-",
    agama: "Islam",
    kontak: {
      wa: "-",
      email: "-",
      alamat: "-",
      desa: "-",
      kecamatan: "-",
      kabupaten: "-"
    },
    asalSekolah: {
      nama: "-",
      npsn: "-",
      alamat: "-",
      kecamatan: "-",
      kabupaten: "-",
      provinsi: "-"
    },
    fisik: { bb: "-", tb: "-", baju: "-", celana: "-", topi: "-" },
    
    // Tabel 2: Informasi_Wali
    keluarga: {
      anakKe: "-",
      jumlahSaudara: "-",
      tinggalBersama: "-",
      ayah: { nama: "-", ttl: "-", nik: "-", pekerjaan: "-", pendidikan: "-", hp: "-", penghasilan: "-" },
      ibu: { nama: "-", ttl: "-", nik: "-", pekerjaan: "-", pendidikan: "-", hp: "-", penghasilan: "-" },
      wali: { nama: "-", ttl: "-", nik: "-", pekerjaan: "-", pendidikan: "-", hp: "-", penghasilan: "-" }
    },
    berkas: {
      ijazah: false,
      foto: false,
      akte: false,
      kk: false,
      sertifikat: false,
      sktm: false
    },
    tahfizh: {
      juz: "Juz 30 & 29",
      suratTerakhir: "Al-Mulk",
      kualitas: "Jayyid Jiddan",
      prestasi: "Juara Harapan 1 MHQ Tingkat Yayasan"
    },

    // Tabel 3: Pembayaran_SPP
    pembayaran: [
      // Format: { bulanKe: 1, tanggal: "8/8/2025", nominal: "Rp1.250.000", status: "Lunas" }
    ]
  }
];

// --- MOCK DATA KELAS & HALAQOH ---
const mockKelas = [
  { id: "KL-01", nama: "I - A", jenjang: "SD", waliKelas: "Ustadzah Fatimah", jumlahSantri: 28 },
  { id: "KL-02", nama: "I - B", jenjang: "SD", waliKelas: "Ustadzah Aisyah", jumlahSantri: 26 },
  { id: "KL-03", nama: "VII - PUTRA", jenjang: "SMP", waliKelas: "Ustadz Ali", jumlahSantri: 32 },
];

const mockHalaqoh = [
  { id: "HL-01", nama: "Halaqoh Utsman", jenjang: "SD", musyrif: "Abdillah A Samsudin", jumlahSantri: 10 },
  { id: "HL-02", nama: "Halaqoh Ali", jenjang: "SD", musyrif: "Ustadz Umar", jumlahSantri: 12 },
  { id: "HL-03", nama: "Halaqoh Abu Bakar", jenjang: "SMP", musyrif: "Ustadz Hamzah", jumlahSantri: 15 },
];

const mockPengajar = [
  {
    id: "PPTQH0001",
    nuptk: "-",
    namaLengkap: "Abdillah A Samsudin",
    jenisKelamin: "Laki-Laki",
    nik: "-",
    umur: "-",
    ttl: "- / -",
    kontak: {
      wa: "082248471007",
      email: "abdillahsamsudin6@gmail.com",
      alamat: "-",
      desa: "-",
      kelurahan: "-",
      kecamatan: "-",
      kota: "-"
    },
    kepegawaian: {
      jabatan: "Guru / Musyrif",
      sk: "-",
      guruMapel: "-",
      musyrifKamar: "-",
      musyrifHalaqoh: "Halaqoh Utsman"
    },
    profil: { hobi: "-", keahlian: "-" },
    pendidikan: { sd: "-", smp: "-", sma: "-", s1: "-", s2: "-", s3: "-" }
  }
];

// Masukkan URL Web App Google Apps Script Anda ke sini setelah di-deploy
const GOOGLE_SCRIPT_URL = "URL_WEB_APP_ANDA_DISINI";

export default function App() {
  const [activeMenu, setActiveMenu] = useState('data-santri');
  const [selectedSantri, setSelectedSantri] = useState(null);
  const [selectedPengajar, setSelectedPengajar] = useState(null);
  const [searchQuery, setSearchQuery] = useState('');

  // --- STATE UNTUK DATA NYATA (DARI SPREADSHEET) ---
  const [dataSantri, setDataSantri] = useState(mockSantri); // Default ke mock untuk preview
  const [dataKelas, setDataKelas] = useState(mockKelas);
  const [dataHalaqoh, setDataHalaqoh] = useState(mockHalaqoh);
  const [dataPengajar, setDataPengajar] = useState(mockPengajar);
  const [isLoading, setIsLoading] = useState(false);

  // --- FUNGSI MENGAMBIL DATA (READ) ---
  const fetchData = async () => {
    setIsLoading(true);
    try {
      if (GOOGLE_SCRIPT_URL === "https://script.google.com/macros/s/AKfycbwMay5nhbwMpe8tLYJNi8p3vytyxYb50cO37rGm1Fqmyz7Um8vMbvwltP05xNdJrGla2w/exec") {
        // Jika belum ada URL, gunakan simulasi loading 1 detik lalu pakai mock data
        setTimeout(() => setIsLoading(false), 1000);
        return;
      }
      
      const response = await fetch(`${GOOGLE_SCRIPT_URL}?sheet=Database Utama`);
      const result = await response.json();
      
      if (result.status === 'success') {
        // Disini kita bisa memformat data JSON datar dari spreadsheet 
        // menjadi objek bersarang (nested) seperti format mockSantri.
        console.log("Data berhasil ditarik:", result.data);
        // setDataSantri(formatDataSpreadsheetKeReact(result.data));
      }
    } catch (error) {
      console.error("Gagal mengambil data dari Spreadsheet:", error);
    } finally {
      setIsLoading(false);
    }
  };

  // Muat data saat aplikasi pertama kali dijalankan
  React.useEffect(() => {
    fetchData();
  }, []);

  // --- FUNGSI TAMBAH DATA (CREATE) ---
  const handleAddData = async (sheetName, newData) => {
    setIsLoading(true);
    try {
      await fetch(GOOGLE_SCRIPT_URL, {
        method: "POST",
        body: JSON.stringify({ action: "add", sheet: sheetName, data: newData })
      });
      alert("Data berhasil ditambahkan!");
      fetchData(); // Refresh tabel
    } catch (error) {
      console.error("Gagal menambah data:", error);
    }
    setIsLoading(false);
  };

  // --- FUNGSI EDIT DATA (UPDATE) ---
  const handleUpdateData = async (sheetName, id, updatedData) => {
    setIsLoading(true);
    try {
      await fetch(GOOGLE_SCRIPT_URL, {
        method: "POST",
        body: JSON.stringify({ action: "update", sheet: sheetName, id: id, data: updatedData })
      });
      alert("Data berhasil diperbarui!");
      fetchData();
    } catch (error) {
      console.error("Gagal mengupdate data:", error);
    }
    setIsLoading(false);
  };

  // --- FUNGSI HAPUS DATA (DELETE) ---
  const handleDeleteData = async (sheetName, id) => {
    if(!window.confirm("Yakin ingin menghapus data ini?")) return;
    
    setIsLoading(true);
    try {
      await fetch(GOOGLE_SCRIPT_URL, {
        method: "POST",
        body: JSON.stringify({ action: "delete", sheet: sheetName, id: id })
      });
      alert("Data berhasil dihapus!");
      fetchData();
    } catch (error) {
      console.error("Gagal menghapus data:", error);
    }
    setIsLoading(false);
  };

  const menuTitles = {
    'data-santri': 'Data Santri',
    'akademik': 'Akademik',
    'ortu': 'Informasi Orang Tua',
    'tahfizh': 'Tahfizh & Prestasi',
    'keuangan': 'Keuangan',
    'kelas-halaqoh': 'Manajemen Kelas & Halaqoh',
    'pengajar': 'Manajemen Pengajar'
  };

  // Filter santri
  const filteredSantri = useMemo(() => {
    return dataSantri.filter(s => 
      s.namaLengkap.toLowerCase().includes(searchQuery.toLowerCase()) ||
      s.id.includes(searchQuery)
    );
  }, [searchQuery, dataSantri]);

  const filteredPengajar = useMemo(() => {
    return dataPengajar.filter(p => 
      p.namaLengkap.toLowerCase().includes(searchQuery.toLowerCase()) ||
      p.id.includes(searchQuery)
    );
  }, [searchQuery, dataPengajar]);

  const SidebarItem = ({ icon: Icon, label, id }) => (
    <button 
      onClick={() => { setActiveMenu(id); setSelectedSantri(null); setSelectedPengajar(null); }}
      className={`w-full flex items-center space-x-3 px-4 py-3 rounded-xl transition-all ${
        activeMenu === id 
          ? 'bg-blue-600 text-white shadow-md' 
          : 'text-slate-400 hover:bg-slate-800 hover:text-white'
      }`}
    >
      <Icon size={20} />
      <span className="font-medium">{label}</span>
    </button>
  );

  return (
    <div className="flex h-screen bg-slate-50 font-sans text-slate-800">
      {/* SIDEBAR */}
      <aside className="w-64 bg-slate-900 text-white p-6 flex flex-col shadow-xl z-10">
        <div className="flex items-center space-x-3 mb-10">
          <div className="w-10 h-10 bg-emerald-600 rounded-lg flex items-center justify-center font-bold text-xl shadow-lg shadow-emerald-600/30">
            YH
          </div>
          <div>
            <h1 className="font-bold text-sm tracking-wide">Yayasan Hidayatullah</h1>
            <p className="text-xs text-slate-400">Ternate</p>
          </div>
        </div>

        <nav className="space-y-2 flex-1">
          <SidebarItem icon={Users} label="Data Santri" id="data-santri" />
          <SidebarItem icon={GraduationCap} label="Akademik" id="akademik" />
          <SidebarItem icon={UserCircle} label="Informasi Orang Tua" id="ortu" />
          <SidebarItem icon={Award} label="Tahfizh & Prestasi" id="tahfizh" />
          <SidebarItem icon={School} label="Kelas & Halaqoh" id="kelas-halaqoh" />
          <SidebarItem icon={Briefcase} label="Manajemen Pengajar" id="pengajar" />
          <SidebarItem icon={Wallet} label="Keuangan" id="keuangan" />
        </nav>

        <div className="mt-auto pt-6 border-t border-slate-800">
          <div className="flex items-center space-x-3">
            <div className="w-10 h-10 bg-slate-700 rounded-full flex items-center justify-center">
              <UserCircle size={24} className="text-slate-300" />
            </div>
            <div>
              <p className="text-sm font-medium">Admin Pusat</p>
              <p className="text-xs text-slate-400">admin@pesantren.id</p>
            </div>
          </div>
        </div>
      </aside>

      {/* MAIN CONTENT */}
      <main className="flex-1 overflow-hidden flex flex-col">
        {/* HEADER */}
        <header className="bg-white border-b border-slate-200 h-20 flex items-center justify-between px-8 shadow-sm">
          <h2 className="text-2xl font-bold text-slate-800 capitalize">
            {menuTitles[activeMenu]}
          </h2>
          <div className="flex items-center space-x-4">
            {/* Indikator Loading */}
            {isLoading && (
              <div className="flex items-center text-blue-600 mr-2">
                <Loader2 className="animate-spin mr-2" size={20} />
                <span className="text-sm font-medium">Sinkronisasi...</span>
              </div>
            )}
            
            <div className="relative">
              <Search className="absolute left-3 top-1/2 -translate-y-1/2 text-slate-400" size={18} />
              <input 
                type="text" 
                placeholder="Cari Nama / ID Santri..." 
                value={searchQuery}
                onChange={(e) => setSearchQuery(e.target.value)}
                className="pl-10 pr-4 py-2 border border-slate-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500 w-64 text-sm transition-all"
              />
            </div>
            <button className="p-2 border border-slate-300 rounded-lg hover:bg-slate-50 text-slate-600 transition-colors">
              <Filter size={18} />
            </button>
            <button className="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg text-sm font-medium transition-colors shadow-sm shadow-blue-600/20">
              + Tambah Santri
            </button>
          </div>
        </header>

        {/* CONTENT AREA */}
        <div className="flex-1 overflow-auto p-8 relative">
          
          {/* VIEW: MANAJEMEN KELAS & HALAQOH */}
          {activeMenu === 'kelas-halaqoh' && !selectedSantri && (
            <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
              {/* Box Daftar Kelas */}
              <div className="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden flex flex-col h-[calc(100vh-180px)]">
                <div className="p-6 border-b border-slate-200 flex justify-between items-center bg-slate-50">
                  <h3 className="text-lg font-bold text-slate-800 flex items-center">
                    <School size={20} className="mr-2 text-blue-600"/> Daftar Kelas
                  </h3>
                  <button onClick={() => handleAddData("Kelas", { "ID": "KL-NEW", "Nama Kelas": "Kelas Baru" })} className="bg-blue-600 hover:bg-blue-700 text-white px-3 py-1.5 rounded-lg text-sm font-medium transition-colors shadow-sm">
                    + Tambah Kelas
                  </button>
                </div>
                <div className="overflow-auto flex-1">
                  <table className="w-full text-left border-collapse">
                    <thead>
                      <tr className="bg-white border-b border-slate-200 text-slate-600 text-sm">
                        <th className="p-4 font-semibold sticky top-0 bg-white">Nama Kelas</th>
                        <th className="p-4 font-semibold sticky top-0 bg-white">Jenjang</th>
                        <th className="p-4 font-semibold sticky top-0 bg-white">Wali Kelas</th>
                        <th className="p-4 font-semibold text-center sticky top-0 bg-white">Santri</th>
                      </tr>
                    </thead>
                    <tbody>
                      {dataKelas.map((kelas) => (
                        <tr key={kelas.id} className="border-b border-slate-100 hover:bg-slate-50 transition-colors">
                          <td className="p-4 text-sm font-bold text-slate-800">{kelas.nama}</td>
                          <td className="p-4 text-sm text-slate-600">{kelas.jenjang}</td>
                          <td className="p-4 text-sm text-slate-600">{kelas.waliKelas}</td>
                          <td className="p-4 text-sm font-medium text-center">
                            <span className="bg-blue-100 text-blue-700 px-2 py-1 rounded-full text-xs">{kelas.jumlahSantri}</span>
                          </td>
                        </tr>
                      ))}
                    </tbody>
                  </table>
                </div>
              </div>

              {/* Box Daftar Halaqoh */}
              <div className="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden flex flex-col h-[calc(100vh-180px)]">
                <div className="p-6 border-b border-slate-200 flex justify-between items-center bg-slate-50">
                  <h3 className="text-lg font-bold text-slate-800 flex items-center">
                    <Users size={20} className="mr-2 text-emerald-600"/> Daftar Halaqoh
                  </h3>
                  <button onClick={() => handleAddData("Halaqoh", { "ID": "HL-NEW", "Nama Halaqoh": "Halaqoh Baru" })} className="bg-emerald-600 hover:bg-emerald-700 text-white px-3 py-1.5 rounded-lg text-sm font-medium transition-colors shadow-sm">
                    + Tambah Halaqoh
                  </button>
                </div>
                <div className="overflow-auto flex-1">
                  <table className="w-full text-left border-collapse">
                    <thead>
                      <tr className="bg-white border-b border-slate-200 text-slate-600 text-sm">
                        <th className="p-4 font-semibold sticky top-0 bg-white">Nama Halaqoh</th>
                        <th className="p-4 font-semibold sticky top-0 bg-white">Jenjang</th>
                        <th className="p-4 font-semibold sticky top-0 bg-white">Musyrif</th>
                        <th className="p-4 font-semibold text-center sticky top-0 bg-white">Santri</th>
                      </tr>
                    </thead>
                    <tbody>
                      {dataHalaqoh.map((hlq) => (
                        <tr key={hlq.id} className="border-b border-slate-100 hover:bg-slate-50 transition-colors">
                          <td className="p-4 text-sm font-bold text-slate-800">{hlq.nama}</td>
                          <td className="p-4 text-sm text-slate-600">{hlq.jenjang}</td>
                          <td className="p-4 text-sm text-slate-600">{hlq.musyrif}</td>
                          <td className="p-4 text-sm font-medium text-center">
                            <span className="bg-emerald-100 text-emerald-700 px-2 py-1 rounded-full text-xs">{hlq.jumlahSantri}</span>
                          </td>
                        </tr>
                      ))}
                    </tbody>
                  </table>
                </div>
              </div>
            </div>
          )}

          {/* VIEW: TABEL UTAMA DINAMIS */}
          {activeMenu !== 'kelas-halaqoh' && activeMenu !== 'pengajar' && !selectedSantri && (
            <div className="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
              <table className="w-full text-left border-collapse">
                <thead>
                  <tr className="bg-slate-50 border-b border-slate-200 text-slate-600 text-sm">
                    {activeMenu === 'data-santri' && (
                      <>
                        <th className="p-4 font-semibold">ID / NIPD</th>
                        <th className="p-4 font-semibold">Nama Lengkap</th>
                        <th className="p-4 font-semibold">Kelas & Halaqoh</th>
                        <th className="p-4 font-semibold">Status</th>
                      </>
                    )}
                    {activeMenu === 'akademik' && (
                      <>
                        <th className="p-4 font-semibold">Nama Lengkap</th>
                        <th className="p-4 font-semibold">NISN / Dapodik</th>
                        <th className="p-4 font-semibold">Kelas & Halaqoh</th>
                        <th className="p-4 font-semibold">Asal Sekolah</th>
                      </>
                    )}
                    {activeMenu === 'ortu' && (
                      <>
                        <th className="p-4 font-semibold">Nama Santri</th>
                        <th className="p-4 font-semibold">Data Ayah (WA)</th>
                        <th className="p-4 font-semibold">Data Ibu (WA)</th>
                        <th className="p-4 font-semibold">Wali</th>
                      </>
                    )}
                    {activeMenu === 'tahfizh' && (
                      <>
                        <th className="p-4 font-semibold">Nama Lengkap</th>
                        <th className="p-4 font-semibold">Kelas / Halaqoh</th>
                        <th className="p-4 font-semibold">Capaian Hafalan</th>
                        <th className="p-4 font-semibold">Prestasi Terakhir</th>
                      </>
                    )}
                    {activeMenu === 'keuangan' && (
                      <>
                        <th className="p-4 font-semibold">ID / NIPD</th>
                        <th className="p-4 font-semibold">Nama Lengkap</th>
                        <th className="p-4 font-semibold">SPP Bulanan</th>
                        <th className="p-4 font-semibold">Status Pembayaran</th>
                      </>
                    )}
                    <th className="p-4 font-semibold text-center">Aksi</th>
                  </tr>
                </thead>
                <tbody>
                  {filteredSantri.map((santri, idx) => (
                    <tr key={santri.id} className="border-b border-slate-100 hover:bg-slate-50 transition-colors group">
                      {activeMenu === 'data-santri' && (
                        <>
                          <td className="p-4 text-sm font-medium text-slate-600">{santri.id}</td>
                          <td className="p-4 text-sm">
                            <p className="font-semibold text-slate-800">{santri.namaLengkap}</p>
                            <p className="text-xs text-slate-500 mt-0.5">{santri.jenjang} • {santri.jenisKelamin}</p>
                          </td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block">{santri.kelas}</span>
                            <span className="text-xs text-slate-500">{santri.halaqoh}</span>
                          </td>
                          <td className="p-4 text-sm">
                            <span className={`px-2.5 py-1 rounded-full text-xs font-medium ${
                              santri.status === 'Aktif' ? 'bg-emerald-100 text-emerald-700' : 'bg-red-100 text-red-700'
                            }`}>
                              {santri.status}
                            </span>
                          </td>
                        </>
                      )}
                      {activeMenu === 'akademik' && (
                        <>
                          <td className="p-4 text-sm font-semibold text-slate-800">{santri.namaLengkap}</td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block font-medium">NISN: {santri.nisn}</span>
                            <span className="text-xs text-slate-500">{santri.dapodik}</span>
                          </td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block">{santri.kelas}</span>
                            <span className="text-xs text-slate-500">{santri.halaqoh}</span>
                          </td>
                          <td className="p-4 text-sm text-slate-600">{santri.asalSekolah?.nama || '-'}</td>
                        </>
                      )}
                      {activeMenu === 'ortu' && (
                        <>
                          <td className="p-4 text-sm font-semibold text-slate-800">{santri.namaLengkap}</td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block font-medium">{santri.keluarga?.ayah?.nama || '-'}</span>
                            <span className="text-xs text-slate-500">{santri.keluarga?.ayah?.hp || '-'}</span>
                          </td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block font-medium">{santri.keluarga?.ibu?.nama || '-'}</span>
                            <span className="text-xs text-slate-500">{santri.keluarga?.ibu?.hp || '-'}</span>
                          </td>
                          <td className="p-4 text-sm text-slate-600">{santri.keluarga?.wali?.nama || '-'}</td>
                        </>
                      )}
                      {activeMenu === 'tahfizh' && (
                        <>
                          <td className="p-4 text-sm font-semibold text-slate-800">{santri.namaLengkap}</td>
                          <td className="p-4 text-sm text-slate-600">
                            <span className="block">{santri.kelas}</span>
                            <span className="text-xs text-slate-500">{santri.halaqoh}</span>
                          </td>
                          <td className="p-4 text-sm font-medium text-emerald-600">{santri.tahfizh?.juz || '-'}</td>
                          <td className="p-4 text-sm text-slate-600">{santri.tahfizh?.prestasi || '-'}</td>
                        </>
                      )}
                      {activeMenu === 'keuangan' && (
                        <>
                          <td className="p-4 text-sm font-medium text-slate-600">{santri.id}</td>
                          <td className="p-4 text-sm font-semibold text-slate-800">{santri.namaLengkap}</td>
                          <td className="p-4 text-sm font-medium text-slate-600">{santri.sppBulanan}</td>
                          <td className="p-4 text-sm">
                            {santri.pembayaran && santri.pembayaran.length > 0 ? (
                              <span className="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-medium bg-emerald-100 text-emerald-700">
                                <CheckCircle2 size={14} className="mr-1" /> {santri.pembayaran[0].status}
                              </span>
                            ) : (
                              <span className="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-medium bg-amber-100 text-amber-700">
                                <Clock size={14} className="mr-1" /> Belum
                              </span>
                            )}
                          </td>
                        </>
                      )}
                      <td className="p-4 text-center">
                        <button 
                          onClick={() => setSelectedSantri(santri)}
                          className="p-1.5 text-blue-600 hover:bg-blue-50 rounded-lg transition-colors inline-flex opacity-0 group-hover:opacity-100"
                        >
                          <ChevronRight size={20} />
                        </button>
                      </td>
                    </tr>
                  ))}
                  {filteredSantri.length === 0 && (
                    <tr>
                      <td colSpan="6" className="p-8 text-center text-slate-500">
                        Data santri tidak ditemukan.
                      </td>
                    </tr>
                  )}
                </tbody>
              </table>
            </div>
          )}

          {/* VIEW: TABEL PENGAJAR */}
          {activeMenu === 'pengajar' && !selectedPengajar && (
            <div className="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
              <table className="w-full text-left border-collapse">
                <thead>
                  <tr className="bg-slate-50 border-b border-slate-200 text-slate-600 text-sm">
                    <th className="p-4 font-semibold">ID / NUPTK</th>
                    <th className="p-4 font-semibold">Nama Lengkap</th>
                    <th className="p-4 font-semibold">Jabatan & Tugas</th>
                    <th className="p-4 font-semibold">Kontak</th>
                    <th className="p-4 font-semibold text-center">Aksi</th>
                  </tr>
                </thead>
                <tbody>
                  {filteredPengajar.map((pengajar) => (
                    <tr key={pengajar.id} className="border-b border-slate-100 hover:bg-slate-50 transition-colors group">
                      <td className="p-4 text-sm font-medium text-slate-600">
                        <span className="block">{pengajar.id}</span>
                        <span className="text-xs text-slate-500">NUPTK: {pengajar.nuptk}</span>
                      </td>
                      <td className="p-4 text-sm font-semibold text-slate-800">{pengajar.namaLengkap}</td>
                      <td className="p-4 text-sm text-slate-600">
                        <span className="block font-medium">{pengajar.kepegawaian.jabatan}</span>
                        <span className="text-xs text-emerald-600 font-medium">{pengajar.kepegawaian.musyrifHalaqoh}</span>
                      </td>
                      <td className="p-4 text-sm text-slate-600">
                        <span className="block">{pengajar.kontak.wa}</span>
                        <span className="text-xs text-slate-500">{pengajar.kontak.email}</span>
                      </td>
                      <td className="p-4 text-center">
                        <button 
                          onClick={() => setSelectedPengajar(pengajar)}
                          className="p-1.5 text-blue-600 hover:bg-blue-50 rounded-lg transition-colors inline-flex opacity-0 group-hover:opacity-100"
                        >
                          <ChevronRight size={20} />
                        </button>
                      </td>
                    </tr>
                  ))}
                  {filteredPengajar.length === 0 && (
                    <tr>
                      <td colSpan="5" className="p-8 text-center text-slate-500">
                        Data pengajar tidak ditemukan.
                      </td>
                    </tr>
                  )}
                </tbody>
              </table>
            </div>
          )}

          {/* VIEW: DETAIL SANTRI (SLIDE IN OVERLAY) */}
          {selectedSantri && (
            <div className="absolute inset-0 bg-white z-20 flex flex-col animate-in slide-in-from-right-8 duration-300">
              {/* Detail Header */}
              <div className="p-6 border-b border-slate-200 flex items-start justify-between bg-slate-50">
                <div className="flex items-center space-x-6">
                  <div className="w-24 h-24 bg-slate-200 rounded-xl shadow-sm flex items-center justify-center overflow-hidden border border-slate-300">
                    <UserCircle size={64} className="text-slate-400" />
                  </div>
                  <div>
                    <div className="flex items-center space-x-3 mb-1">
                      <h2 className="text-3xl font-bold text-slate-800">{selectedSantri.namaLengkap}</h2>
                      <span className="px-2.5 py-1 rounded-full text-xs font-bold bg-emerald-100 text-emerald-700 uppercase tracking-wider">
                        {selectedSantri.status}
                      </span>
                    </div>
                    <div className="flex space-x-4 text-sm text-slate-600 mt-2">
                      <span className="flex items-center"><MapPin size={16} className="mr-1.5 text-slate-400"/> ID: {selectedSantri.id}</span>
                      <span className="flex items-center"><GraduationCap size={16} className="mr-1.5 text-slate-400"/> {selectedSantri.kelas}</span>
                      <span className="flex items-center"><Users size={16} className="mr-1.5 text-slate-400"/> {selectedSantri.halaqoh} (Musyrif: {selectedSantri.musyrif})</span>
                    </div>
                  </div>
                </div>
                <button 
                  onClick={() => setSelectedSantri(null)}
                  className="p-2 text-slate-400 hover:text-red-500 hover:bg-red-50 rounded-lg transition-colors"
                >
                  <X size={24} />
                </button>
              </div>

              {/* Detail Tabs Component */}
              <DetailTabs santri={selectedSantri} />
            </div>
          )}

          {/* VIEW: DETAIL PENGAJAR (SLIDE IN OVERLAY) */}
          {selectedPengajar && (
            <div className="absolute inset-0 bg-white z-20 flex flex-col animate-in slide-in-from-right-8 duration-300">
              {/* Detail Header */}
              <div className="p-6 border-b border-slate-200 flex items-start justify-between bg-slate-50">
                <div className="flex items-center space-x-6">
                  <div className="w-24 h-24 bg-slate-200 rounded-xl shadow-sm flex items-center justify-center overflow-hidden border border-slate-300">
                    <Briefcase size={64} className="text-slate-400" />
                  </div>
                  <div>
                    <div className="flex items-center space-x-3 mb-1">
                      <h2 className="text-3xl font-bold text-slate-800">{selectedPengajar.namaLengkap}</h2>
                      <span className="px-2.5 py-1 rounded-full text-xs font-bold bg-blue-100 text-blue-700 uppercase tracking-wider">
                        {selectedPengajar.kepegawaian.jabatan || 'Pengajar'}
                      </span>
                    </div>
                    <div className="flex space-x-4 text-sm text-slate-600 mt-2">
                      <span className="flex items-center"><MapPin size={16} className="mr-1.5 text-slate-400"/> ID: {selectedPengajar.id}</span>
                      <span className="flex items-center"><UserCircle size={16} className="mr-1.5 text-slate-400"/> L/P: {selectedPengajar.jenisKelamin}</span>
                    </div>
                  </div>
                </div>
                <button 
                  onClick={() => setSelectedPengajar(null)}
                  className="p-2 text-slate-400 hover:text-red-500 hover:bg-red-50 rounded-lg transition-colors"
                >
                  <X size={24} />
                </button>
              </div>

              {/* Detail Tabs Pengajar Component */}
              <DetailPengajarTabs pengajar={selectedPengajar} />
            </div>
          )}

          {/* VIEW: DASHBOARD (Simple Mock) */}
          {activeMenu === 'dashboard' && (
            <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
              {[
                { label: "Total Santri Aktif", value: "342", color: "blue" },
                { label: "Pembayaran Lunas Bulan Ini", value: "285", color: "emerald" },
                { label: "Belum Daftar Ulang", value: "12", color: "amber" }
              ].map((stat, i) => (
                <div key={i} className="bg-white p-6 rounded-xl shadow-sm border border-slate-200">
                  <p className="text-slate-500 text-sm font-medium">{stat.label}</p>
                  <p className={`text-4xl font-bold mt-2 text-${stat.color}-600`}>{stat.value}</p>
                </div>
              ))}
            </div>
          )}
        </div>
      </main>
    </div>
  );
}

// Komponen Sub-Tabs untuk Detail Santri
function DetailTabs({ santri }) {
  const [activeTab, setActiveTab] = useState('data-santri');

  const tabs = [
    { id: 'data-santri', label: 'Data Santri', icon: FileText },
    { id: 'akademik', label: 'Akademik', icon: GraduationCap },
    { id: 'ortu', label: 'Informasi Orang Tua', icon: Users },
    { id: 'tahfizh', label: 'Tahfizh & Prestasi', icon: Award },
    { id: 'keuangan', label: 'Keuangan', icon: CreditCard },
  ];

  return (
    <div className="flex-1 flex flex-col bg-white overflow-hidden">
      {/* Tab Nav */}
      <div className="flex px-8 border-b border-slate-200 space-x-8 bg-white pt-4">
        {tabs.map(tab => (
          <button
            key={tab.id}
            onClick={() => setActiveTab(tab.id)}
            className={`flex items-center space-x-2 pb-4 border-b-2 transition-colors ${
              activeTab === tab.id 
                ? 'border-blue-600 text-blue-600 font-semibold' 
                : 'border-transparent text-slate-500 hover:text-slate-700 hover:border-slate-300'
            }`}
          >
            <tab.icon size={18} />
            <span>{tab.label}</span>
          </button>
        ))}
      </div>

      {/* Tab Content Area */}
      <div className="flex-1 overflow-auto p-8 bg-slate-50/50">
        
        {/* TAB 1: PROFIL */}
        {activeTab === 'data-santri' && (
          <div className="max-w-5xl space-y-8">
             <div>
              <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">
                 Identitas Utama
              </h3>
              <div className="grid grid-cols-3 gap-x-8 gap-y-4 bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                <InfoItem label="NIPD" value={santri.nipd} />
                <InfoItem label="NISN" value={santri.nisn} />
                <InfoItem label="Nama Lengkap" value={santri.namaLengkap} />
                <InfoItem label="Jenis Kelamin" value={santri.jenisKelamin} />
                <InfoItem label="Tempat, Tgl Lahir" value={santri.ttl} />
                <InfoItem label="NIK" value={santri.nik} />
                <InfoItem label="Agama" value={santri.agama} />
                <InfoItem label="Tahun Masuk" value={santri.tahunMasuk} />
                <InfoItem label="Status Dapodik" value={santri.dapodik} />
              </div>
            </div>

            <div className="grid grid-cols-2 gap-8">
              <div>
                <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">Data Fisik & Seragam</h3>
                <div className="grid grid-cols-2 gap-4 bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                  <InfoItem label="Berat Badan" value={`${santri.fisik?.bb || '-'} Kg`} />
                  <InfoItem label="Tinggi Badan" value={`${santri.fisik?.tb || '-'} cm`} />
                  <div className="col-span-2 grid grid-cols-3 gap-4 mt-2 pt-4 border-t border-slate-100">
                    <InfoItem label="Baju" value={santri.fisik?.baju} />
                    <InfoItem label="Celana" value={santri.fisik?.celana} />
                    <InfoItem label="Topi" value={santri.fisik?.topi} />
                  </div>
                </div>
              </div>
              <div>
                <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">Status Domisili Anak</h3>
                <div className="grid grid-cols-2 gap-4 bg-white p-6 rounded-xl border border-slate-200 shadow-sm h-[172px]">
                  <InfoItem label="Anak Ke" value={santri.keluarga?.anakKe} />
                  <InfoItem label="Jumlah Saudara" value={santri.keluarga?.jumlahSaudara} />
                  <div className="col-span-2">
                    <InfoItem label="Tinggal Bersama" value={santri.keluarga?.tinggalBersama} />
                  </div>
                </div>
              </div>
            </div>
          </div>
        )}

        {/* TAB 2: KELUARGA */}
        {activeTab === 'ortu' && (
          <div className="max-w-5xl space-y-6">
            <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
              <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Alamat & Kontak Santri</h3>
              <div className="grid grid-cols-3 gap-4">
                <div className="col-span-3"><InfoItem label="Alamat Lengkap" value={santri.kontak?.alamat} /></div>
                <InfoItem label="Desa" value={santri.kontak?.desa} />
                <InfoItem label="Kecamatan" value={santri.kontak?.kecamatan} />
                <InfoItem label="Kabupaten/Kota" value={santri.kontak?.kabupaten} />
                <InfoItem label="Nomor WA Santri" value={santri.kontak?.wa} />
                <InfoItem label="Email" value={santri.kontak?.email} />
              </div>
            </div>

            <div className="grid grid-cols-2 gap-6">
              <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Data Ayah</h3>
                <div className="grid grid-cols-2 gap-4">
                  <div className="col-span-2"><InfoItem label="Nama Lengkap" value={santri.keluarga?.ayah?.nama} /></div>
                  <div className="col-span-2"><InfoItem label="Tempat, Tgl Lahir" value={santri.keluarga?.ayah?.ttl} /></div>
                  <InfoItem label="NIK" value={santri.keluarga?.ayah?.nik} />
                  <InfoItem label="Nomor WA" value={santri.keluarga?.ayah?.hp} />
                  <InfoItem label="Pendidikan" value={santri.keluarga?.ayah?.pendidikan} />
                  <InfoItem label="Pekerjaan" value={santri.keluarga?.ayah?.pekerjaan} />
                  <div className="col-span-2"><InfoItem label="Penghasilan" value={santri.keluarga?.ayah?.penghasilan} /></div>
                </div>
              </div>
              
              <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Data Ibu</h3>
                <div className="grid grid-cols-2 gap-4">
                  <div className="col-span-2"><InfoItem label="Nama Lengkap" value={santri.keluarga?.ibu?.nama} /></div>
                  <div className="col-span-2"><InfoItem label="Tempat, Tgl Lahir" value={santri.keluarga?.ibu?.ttl} /></div>
                  <InfoItem label="NIK" value={santri.keluarga?.ibu?.nik} />
                  <InfoItem label="Nomor WA" value={santri.keluarga?.ibu?.hp} />
                  <InfoItem label="Pendidikan" value={santri.keluarga?.ibu?.pendidikan} />
                  <InfoItem label="Pekerjaan" value={santri.keluarga?.ibu?.pekerjaan} />
                  <div className="col-span-2"><InfoItem label="Penghasilan" value={santri.keluarga?.ibu?.penghasilan} /></div>
                </div>
              </div>

              <div className="col-span-2 bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Data Wali (Jika Ada)</h3>
                <div className="grid grid-cols-4 gap-4">
                  <InfoItem label="Nama Lengkap" value={santri.keluarga?.wali?.nama} />
                  <InfoItem label="Pekerjaan" value={santri.keluarga?.wali?.pekerjaan} />
                  <InfoItem label="Nomor WA" value={santri.keluarga?.wali?.hp} />
                  <InfoItem label="Penghasilan" value={santri.keluarga?.wali?.penghasilan} />
                </div>
              </div>
            </div>
          </div>
        )}

        {/* TAB 4: TAHFIZH & PRESTASI */}
        {activeTab === 'tahfizh' && (
          <div className="max-w-5xl space-y-8">
             <div>
              <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">
                 Capaian Hafalan (Tahfizh)
              </h3>
              <div className="grid grid-cols-3 gap-x-8 gap-y-4 bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                <InfoItem label="Total Juz" value={santri.tahfizh?.juz} />
                <InfoItem label="Surat Terakhir" value={santri.tahfizh?.suratTerakhir} />
                <InfoItem label="Kualitas Bacaan" value={santri.tahfizh?.kualitas} />
              </div>
            </div>

            <div>
              <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">
                 Riwayat Prestasi
              </h3>
              <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
                 <p className="text-sm font-semibold text-slate-800 flex items-center">
                    <Award size={18} className="text-emerald-600 mr-2" />
                    {santri.tahfizh?.prestasi || 'Belum ada data prestasi tercatat.'}
                 </p>
              </div>
            </div>
          </div>
        )}

        {/* TAB 5: KEUANGAN SPP */}
        {activeTab === 'keuangan' && (
          <div className="max-w-5xl">
            <div className="flex justify-between items-center mb-6">
              <div>
                <h3 className="text-xl font-bold text-slate-800">Riwayat Pembayaran SPP (36 Bulan)</h3>
                <p className="text-slate-500 text-sm">Biaya Bulanan: <span className="font-bold text-slate-700">{santri.sppBulanan || '-'}</span></p>
              </div>
              <button className="bg-emerald-600 hover:bg-emerald-700 text-white px-4 py-2 rounded-lg text-sm font-medium transition-colors shadow-sm">
                + Input Pembayaran
              </button>
            </div>

            <div className="bg-white rounded-xl shadow-sm border border-slate-200 overflow-hidden">
              <table className="w-full text-left border-collapse">
                <thead>
                  <tr className="bg-slate-50 border-b border-slate-200 text-slate-600 text-sm">
                    <th className="p-4 font-semibold w-24">Bulan Ke</th>
                    <th className="p-4 font-semibold">Tanggal Bayar</th>
                    <th className="p-4 font-semibold">Nominal</th>
                    <th className="p-4 font-semibold">Status</th>
                    <th className="p-4 font-semibold text-right">Aksi</th>
                  </tr>
                </thead>
                <tbody>
                  {santri.pembayaran?.map((pemb, idx) => (
                    <tr key={idx} className="border-b border-slate-100 hover:bg-slate-50 transition-colors">
                      <td className="p-4 text-sm font-bold text-slate-500 text-center">{pemb.bulanKe}</td>
                      <td className="p-4 text-sm font-medium text-slate-700">{pemb.tanggal}</td>
                      <td className="p-4 text-sm font-medium text-slate-700">{pemb.nominal}</td>
                      <td className="p-4 text-sm">
                        {pemb.status === 'Lunas' ? (
                          <span className="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-medium bg-emerald-100 text-emerald-700">
                            <CheckCircle2 size={14} className="mr-1" /> Lunas
                          </span>
                        ) : (
                          <span className="inline-flex items-center px-2.5 py-1 rounded-full text-xs font-medium bg-amber-100 text-amber-700">
                            <Clock size={14} className="mr-1" /> Belum
                          </span>
                        )}
                      </td>
                      <td className="p-4 text-right">
                        <button className="text-blue-600 hover:text-blue-800 text-sm font-medium">Edit</button>
                      </td>
                    </tr>
                  ))}
                  {/* Generate sisa bulan kosong sampai 36 bulan */}
                  {Array.from({ length: 36 - (santri.pembayaran?.length || 0) }).map((_, idx) => (
                     <tr key={`empty-${idx}`} className="border-b border-slate-50 bg-slate-50/50">
                      <td className="p-4 text-sm font-bold text-slate-400 text-center">{(santri.pembayaran?.length || 0) + idx + 1}</td>
                      <td className="p-4 text-sm text-slate-400">-</td>
                      <td className="p-4 text-sm text-slate-400">-</td>
                      <td className="p-4 text-sm text-slate-400">-</td>
                      <td className="p-4 text-right">
                        <button className="text-slate-400 hover:text-blue-600 text-sm font-medium transition-colors">Isi</button>
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}

// Komponen tambahan untuk Berkas
function BerkasItem({ label, status }) {
  return (
    <div className="flex items-center justify-between bg-slate-50 border border-slate-200 p-4 rounded-lg">
      <span className="text-sm font-medium text-slate-700">{label}</span>
      {status ? (
        <span className="flex items-center text-xs font-bold text-emerald-600 bg-emerald-100 px-2 py-1 rounded">
          <FileCheck size={14} className="mr-1" /> Ada
        </span>
      ) : (
        <span className="flex items-center text-xs font-bold text-slate-400 bg-slate-200 px-2 py-1 rounded">
          <FileX size={14} className="mr-1" /> Kosong
        </span>
      )}
    </div>
  );
}

// Komponen Utility untuk label data
function InfoItem({ label, value }) {
  return (
    <div className="flex flex-col">
      <span className="text-xs text-slate-400 font-medium uppercase tracking-wider mb-1">{label}</span>
      <span className="text-sm font-semibold text-slate-800">{value || '-'}</span>
    </div>
  );
}

// Komponen Sub-Tabs untuk Detail Pengajar
function DetailPengajarTabs({ pengajar }) {
  const [activeTab, setActiveTab] = useState('profil');

  const tabs = [
    { id: 'profil', label: 'Profil & Kontak', icon: UserCircle },
    { id: 'tugas', label: 'Penugasan & Halaqoh', icon: Briefcase },
    { id: 'pendidikan', label: 'Riwayat Pendidikan', icon: GraduationCap },
  ];

  // Menghubungkan pengajar dengan halaqoh yang dia pegang
  const halaqohTerkait = mockHalaqoh.filter(h => h.musyrif === pengajar.namaLengkap);

  return (
    <div className="flex-1 flex flex-col bg-white overflow-hidden">
      <div className="flex px-8 border-b border-slate-200 space-x-8 bg-white pt-4">
        {tabs.map(tab => (
          <button
            key={tab.id}
            onClick={() => setActiveTab(tab.id)}
            className={`flex items-center space-x-2 pb-4 border-b-2 transition-colors ${
              activeTab === tab.id 
                ? 'border-blue-600 text-blue-600 font-semibold' 
                : 'border-transparent text-slate-500 hover:text-slate-700 hover:border-slate-300'
            }`}
          >
            <tab.icon size={18} />
            <span>{tab.label}</span>
          </button>
        ))}
      </div>

      <div className="flex-1 overflow-auto p-8 bg-slate-50/50">
        {activeTab === 'profil' && (
          <div className="max-w-5xl space-y-6">
            <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
              <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Identitas Personal</h3>
              <div className="grid grid-cols-3 gap-4">
                <InfoItem label="ID Kepegawaian" value={pengajar.id} />
                <InfoItem label="NUPTK" value={pengajar.nuptk} />
                <InfoItem label="Nama Lengkap" value={pengajar.namaLengkap} />
                <InfoItem label="Jenis Kelamin" value={pengajar.jenisKelamin} />
                <InfoItem label="NIK" value={pengajar.nik} />
                <InfoItem label="Umur" value={pengajar.umur} />
                <InfoItem label="Tempat, Tgl Lahir" value={pengajar.ttl} />
                <InfoItem label="Keahlian" value={pengajar.profil.keahlian} />
                <InfoItem label="Hobi" value={pengajar.profil.hobi} />
              </div>
            </div>
            
            <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
              <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Data Kontak</h3>
              <div className="grid grid-cols-3 gap-4">
                <InfoItem label="WhatsApp" value={pengajar.kontak.wa} />
                <InfoItem label="Email" value={pengajar.kontak.email} />
                <InfoItem label="Desa" value={pengajar.kontak.desa} />
                <InfoItem label="Kelurahan" value={pengajar.kontak.kelurahan} />
                <InfoItem label="Kecamatan" value={pengajar.kontak.kecamatan} />
                <InfoItem label="Kota" value={pengajar.kontak.kota} />
                <div className="col-span-3">
                  <InfoItem label="Alamat Lengkap" value={pengajar.kontak.alamat} />
                </div>
              </div>
            </div>
          </div>
        )}

        {activeTab === 'tugas' && (
          <div className="max-w-5xl space-y-6">
            <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
              <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Status & Jabatan</h3>
              <div className="grid grid-cols-3 gap-4">
                <InfoItem label="Jabatan Utama" value={pengajar.kepegawaian.jabatan} />
                <InfoItem label="SK Pengangkatan" value={pengajar.kepegawaian.sk} />
                <InfoItem label="Guru Mapel" value={pengajar.kepegawaian.guruMapel} />
                <InfoItem label="Musyrif Kamar" value={pengajar.kepegawaian.musyrifKamar} />
                <InfoItem label="Musyrif Halaqoh" value={pengajar.kepegawaian.musyrifHalaqoh} />
              </div>
            </div>

            <div>
              <h3 className="text-lg font-bold text-slate-800 mb-4 flex items-center">
                <Users size={20} className="mr-2 text-emerald-600"/> Terhubung ke Halaqoh
              </h3>
              {halaqohTerkait.length > 0 ? (
                <div className="grid grid-cols-2 gap-4">
                  {halaqohTerkait.map(hlq => (
                    <div key={hlq.id} className="bg-emerald-50 border border-emerald-200 p-4 rounded-xl flex justify-between items-center">
                      <div>
                        <h4 className="font-bold text-emerald-800">{hlq.nama}</h4>
                        <p className="text-sm text-emerald-600">Jenjang: {hlq.jenjang}</p>
                      </div>
                      <span className="bg-emerald-200 text-emerald-800 px-3 py-1 rounded-full text-xs font-bold">
                        {hlq.jumlahSantri} Santri
                      </span>
                    </div>
                  ))}
                </div>
              ) : (
                <div className="bg-white p-6 rounded-xl border border-slate-200 text-center text-slate-500">
                  Pengajar ini belum ditugaskan sebagai Musyrif di halaqoh manapun.
                </div>
              )}
            </div>
          </div>
        )}

        {activeTab === 'pendidikan' && (
          <div className="max-w-5xl space-y-6">
            <div className="bg-white p-6 rounded-xl border border-slate-200 shadow-sm">
              <h3 className="text-md font-bold text-slate-800 mb-4 border-b border-slate-100 pb-2">Riwayat Pendidikan</h3>
              <div className="grid grid-cols-2 gap-6">
                <InfoItem label="S3 (Doktoral)" value={pengajar.pendidikan.s3} />
                <InfoItem label="S2 (Magister)" value={pengajar.pendidikan.s2} />
                <InfoItem label="S1 (Sarjana)" value={pengajar.pendidikan.s1} />
                <InfoItem label="SMA / Sederajat" value={pengajar.pendidikan.sma} />
                <InfoItem label="SMP / Sederajat" value={pengajar.pendidikan.smp} />
                <InfoItem label="SD / Sederajat" value={pengajar.pendidikan.sd} />
              </div>
            </div>
          </div>
        )}
      </div>
    </div>
  );
}
