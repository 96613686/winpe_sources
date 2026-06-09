# CUwfManagement::GetProtectedVolumeAvailableSpace(ulong *)

- ea: `0x180015e74`
- end: `0x1800162cd`
- name: `?GetProtectedVolumeAvailableSpace@CUwfManagement@@AEAAJPEAK@Z`
- size: `1113`
- prototype: `__int64 __fastcall(CUwfManagement *this, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800163b0`

## callees

- `0x180001384`
- `0x1800054d0`
- `0x18000d5f0`
- `0x18000de30`
- `0x18000de90`
- `0x180015d70`
- `0x180015e74`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001616e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001622b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001627a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001616e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001622b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001627a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015fca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016056`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016108`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015f34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015fca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016056`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016108`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800161ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016210`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800161ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016210`

## string_xrefs

- `0x180015e9e`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static`
- `0x180015f74`: `Copy0`
- `0x180015f6d`: `Copy1`

## pseudocode

```c
__int64 __fastcall CUwfManagement::GetProtectedVolumeAvailableSpace(CUwfManagement *this, unsigned int *a2)
{
  int v3; // r15d
  LSTATUS Value; // eax
  bool v5; // sf
  const unsigned __int16 *v6; // rdx
  LSTATUS v7; // eax
  bool v8; // sf
  LSTATUS v9; // eax
  bool v10; // sf
  void *v11; // rdi
  unsigned int v12; // r14d
  HKEY v13; // rbx
  LSTATUS v14; // eax
  bool v15; // sf
  LSTATUS ValueW; // eax
  CUwfManagement *v17; // rcx
  bool v18; // sf
  bool v19; // cc
  void *v20; // rsi
  LSTATUS v21; // eax
  __int64 Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  BYTE lpData[4]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v28[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY v29; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v30; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v32; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v33[192]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v34[8]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v35; // [rsp+150h] [rbp+50h]

  *a2 = 0;
  hKey = 0;
  v30 = 0;
  v29 = 0;
  *(_DWORD *)lpData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v25 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  v3 = 0;
  *(_DWORD *)v28 = 0;
  if ( (int)CUwfRegKey::Open(
              &hKey,
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static",
              0x20019u) < 0 )
    goto LABEL_52;
  Type = 0x400000000LL;
  Value = RegQueryValueExW(hKey, L"CurrentSettings", 0, (LPDWORD)&Type, Data, (LPDWORD)&Type + 1);
  v5 = Value < 0;
  if ( Value )
  {
    if ( Value > 0 )
      v5 = 1;
    if ( v5 )
      goto LABEL_52;
  }
  else if ( Type != 0x400000004LL )
  {
    goto LABEL_52;
  }
  v6 = L"Copy0";
  if ( *(_DWORD *)Data )
    v6 = L"Copy1";
  if ( CUwfRegKey::OpenSubKey((CUwfRegKey *)&hKey, v6, 0x20019u, (struct CUwfRegKey *)&v30) < 0 )
    goto LABEL_52;
  Type = 4;
  v7 = RegQueryValueExW(v30, L"UWFEnabled", 0, (LPDWORD)&Type + 1, lpData, (LPDWORD)&Type);
  v8 = v7 < 0;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = 1;
    if ( v8 )
      goto LABEL_52;
  }
  else if ( Type != 0x400000004LL )
  {
    goto LABEL_52;
  }
  if ( !*(_DWORD *)lpData
    || CUwfRegKey::OpenSubKey((CUwfRegKey *)&v30, L"Volumes", 0x20019u, (struct CUwfRegKey *)&v29) < 0 )
  {
    goto LABEL_52;
  }
  Type = 4;
  v9 = RegQueryValueExW(v29, L"NumVolumes", 0, (LPDWORD)&Type + 1, v25, (LPDWORD)&Type);
  v10 = v9 < 0;
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = 1;
    if ( v10 )
      goto LABEL_52;
  }
  else if ( Type != 0x400000004LL )
  {
    goto LABEL_52;
  }
  v11 = 0;
  v12 = 0;
  if ( !*(_DWORD *)v25 )
    goto LABEL_52;
  while ( 1 )
  {
    hkey = 0;
    if ( (int)StringCchPrintfW(v34, 0xCu, L"%i", v12) < 0
      || CUwfRegKey::OpenSubKey((CUwfRegKey *)&v29, v34, 0x20019u, (struct CUwfRegKey *)&hkey) < 0 )
    {
      goto LABEL_32;
    }
    v13 = hkey;
    Type = 4;
    v14 = RegQueryValueExW(hkey, L"VolumeEnabled", 0, (LPDWORD)&Type + 1, v28, (LPDWORD)&Type);
    v15 = v14 < 0;
    if ( v14 )
      break;
    if ( Type == 0x400000004LL )
      goto LABEL_35;
LABEL_32:
    CUwfRegKey::Close(&hkey);
    if ( ++v12 >= *(_DWORD *)v25 )
      goto LABEL_50;
  }
  if ( v14 > 0 )
    v15 = 1;
  if ( v15 )
    goto LABEL_32;
LABEL_35:
  if ( *(_DWORD *)v28 != 1 )
    goto LABEL_32;
  memset_0(v33, 0, sizeof(v33));
  v32 = 0;
  if ( v11 )
  {
    operator delete[](v11);
    v11 = 0;
  }
  Type = 0;
  ValueW = RegGetValueW(v13, 0, L"VolumeName", 2u, (LPDWORD)&Type + 1, 0, (LPDWORD)&Type);
  v18 = ValueW < 0;
  v19 = ValueW <= 0;
  if ( ValueW )
  {
    v20 = 0;
LABEL_42:
    if ( !v19 )
      v18 = 1;
    if ( !v18 )
      goto LABEL_48;
LABEL_45:
    operator delete[](v20);
    goto LABEL_32;
  }
  v20 = operator new[](saturated_mul((unsigned __int64)(unsigned int)Type >> 1, 2u));
  if ( !v20 )
    goto LABEL_45;
  v21 = RegGetValueW(v13, 0, L"VolumeName", 2u, (LPDWORD)&Type + 1, v20, (LPDWORD)&Type);
  v18 = v21 < 0;
  v19 = v21 <= 0;
  if ( v21 )
    goto LABEL_42;
  v11 = v20;
LABEL_48:
  if ( CUwfManagement::GetOverlayInformation(
         v17,
         (const unsigned __int16 *)v11,
         (struct _UWFVOL_OVERLAY_DATA_OUTPUT *)v33,
         &v32,
         a2) < 0 )
    goto LABEL_32;
  v3 = 1;
  CUwfRegKey::Close(&hkey);
LABEL_50:
  if ( v11 )
    operator delete[](v11);
LABEL_52:
  CUwfRegKey::Close(&v29);
  CUwfRegKey::Close(&v30);
  CUwfRegKey::Close(&hKey);
  return v3 == 0 ? 0x80070002 : 0;
}

```

## disassembly

```asm
0x180015e74  push    rbp
0x180015e76  push    rbx
0x180015e77  push    rsi
0x180015e78  push    rdi
0x180015e79  push    r12
0x180015e7b  push    r13
0x180015e7d  push    r14
0x180015e7f  push    r15
0x180015e81  lea     rbp, [rsp-68h]
0x180015e86  sub     rsp, 168h
0x180015e8d  mov     rax, cs:__security_cookie
0x180015e94  xor     rax, rsp
0x180015e97  mov     [rbp+0A0h+var_48], rax
0x180015e9b  xor     r13d, r13d
0x180015e9e  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180015ea5  mov     [rdx], r13d
0x180015ea8  lea     rcx, [rsp+1A0h+hKey]; phkResult
0x180015ead  mov     r12, rdx
0x180015eb0  mov     [rsp+1A0h+hKey], r13
0x180015eb5  xorps   xmm0, xmm0
0x180015eb8  mov     [rsp+1A0h+var_138], r13
0x180015ebd  xor     eax, eax
0x180015ebf  mov     [rsp+1A0h+var_140], r13
0x180015ec4  mov     edi, 20019h
0x180015ec9  mov     dword ptr [rsp+1A0h+var_148], r13d
0x180015ece  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180015ed5  mov     dword ptr [rsp+1A0h+Data], r13d
0x180015eda  mov     r9d, edi; samDesired
0x180015edd  mov     dword ptr [rsp+1A0h+var_150], r13d
0x180015ee2  movups  xmmword ptr [rbp+0A0h+var_60], xmm0
0x180015ee6  mov     [rbp+0A0h+var_50], rax
0x180015eea  mov     r15d, r13d
0x180015eed  mov     dword ptr [rsp+1A0h+var_144], r13d
0x180015ef2  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015ef7  test    eax, eax
0x180015ef9  js      loc_180016280
0x180015eff  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180015f04  lea     rax, [rsp+1A0h+Type+4]
0x180015f09  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180015f0e  lea     esi, [r13+4]
0x180015f12  lea     rax, [rsp+1A0h+Data]
0x180015f17  mov     dword ptr [rsp+1A0h+Type], r13d
0x180015f1c  lea     r9, [rsp+1A0h+Type]; lpType
0x180015f21  mov     [rsp+1A0h+lpData], rax; lpData
0x180015f26  xor     r8d, r8d; lpReserved
0x180015f29  mov     dword ptr [rsp+1A0h+Type+4], esi
0x180015f2d  lea     rdx, aCurrentsetting; "CurrentSettings"
0x180015f34  call    cs:__imp_RegQueryValueExW
0x180015f3a  mov     ebx, 80070000h
0x180015f3f  test    eax, eax
0x180015f41  jz      short loc_180015F54
0x180015f43  jle     short loc_180015F4C
0x180015f45  movzx   eax, ax
0x180015f48  or      eax, ebx
0x180015f4a  test    eax, eax
0x180015f4c  js      loc_180016280
0x180015f52  jmp     short loc_180015F68
0x180015f54  cmp     dword ptr [rsp+1A0h+Type], esi
0x180015f58  jnz     loc_180016280
0x180015f5e  cmp     dword ptr [rsp+1A0h+Type+4], esi
0x180015f62  jnz     loc_180016280
0x180015f68  cmp     dword ptr [rsp+1A0h+Data], r13d
0x180015f6d  lea     rax, aCopy1; "Copy1"
0x180015f74  lea     rdx, aCopy0; "Copy0"
0x180015f7b  mov     r8d, edi; unsigned int
0x180015f7e  cmovnz  rdx, rax; unsigned __int16 *
0x180015f82  lea     r9, [rsp+1A0h+var_138]; struct CUwfRegKey *
0x180015f87  lea     rcx, [rsp+1A0h+hKey]; this
0x180015f8c  call    ?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z; CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)
0x180015f91  test    eax, eax
0x180015f93  js      loc_180016280
0x180015f99  mov     rcx, [rsp+1A0h+var_138]; hKey
0x180015f9e  lea     rax, [rsp+1A0h+Type]
0x180015fa3  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180015fa8  lea     r9, [rsp+1A0h+Type+4]; lpType
0x180015fad  lea     rax, [rsp+1A0h+var_148]
0x180015fb2  mov     dword ptr [rsp+1A0h+Type+4], r13d
0x180015fb7  xor     r8d, r8d; lpReserved
0x180015fba  mov     [rsp+1A0h+lpData], rax; lpData
0x180015fbf  lea     rdx, aUwfenabled; "UWFEnabled"
0x180015fc6  mov     dword ptr [rsp+1A0h+Type], esi
0x180015fca  call    cs:__imp_RegQueryValueExW
0x180015fd0  test    eax, eax
0x180015fd2  jz      short loc_180015FE5
0x180015fd4  jle     short loc_180015FDD
0x180015fd6  movzx   eax, ax
0x180015fd9  or      eax, ebx
0x180015fdb  test    eax, eax
0x180015fdd  js      loc_180016280
0x180015fe3  jmp     short loc_180015FF9
0x180015fe5  cmp     dword ptr [rsp+1A0h+Type+4], esi
0x180015fe9  jnz     loc_180016280
0x180015fef  cmp     dword ptr [rsp+1A0h+Type], esi
0x180015ff3  jnz     loc_180016280
0x180015ff9  cmp     dword ptr [rsp+1A0h+var_148], r13d
0x180015ffe  jz      loc_180016280
0x180016004  lea     r9, [rsp+1A0h+var_140]; struct CUwfRegKey *
0x180016009  mov     r8d, edi; unsigned int
0x18001600c  lea     rdx, aVolumes; "Volumes"
0x180016013  lea     rcx, [rsp+1A0h+var_138]; this
0x180016018  call    ?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z; CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)
0x18001601d  test    eax, eax
0x18001601f  js      loc_180016280
0x180016025  mov     rcx, [rsp+1A0h+var_140]; hKey
0x18001602a  lea     rax, [rsp+1A0h+Type]
0x18001602f  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180016034  lea     r9, [rsp+1A0h+Type+4]; lpType
0x180016039  lea     rax, [rsp+1A0h+var_150]
0x18001603e  mov     dword ptr [rsp+1A0h+Type+4], r13d
0x180016043  xor     r8d, r8d; lpReserved
0x180016046  mov     [rsp+1A0h+lpData], rax; lpData
0x18001604b  lea     rdx, aNumvolumes; "NumVolumes"
0x180016052  mov     dword ptr [rsp+1A0h+Type], esi
0x180016056  call    cs:__imp_RegQueryValueExW
0x18001605c  test    eax, eax
0x18001605e  jz      short loc_180016071
0x180016060  jle     short loc_180016069
0x180016062  movzx   eax, ax
0x180016065  or      eax, ebx
0x180016067  test    eax, eax
0x180016069  js      loc_180016280
0x18001606f  jmp     short loc_180016085
0x180016071  cmp     dword ptr [rsp+1A0h+Type+4], esi
0x180016075  jnz     loc_180016280
0x18001607b  cmp     dword ptr [rsp+1A0h+Type], esi
0x18001607f  jnz     loc_180016280
0x180016085  mov     rdi, r13
0x180016088  mov     r14d, r13d
0x18001608b  cmp     dword ptr [rsp+1A0h+var_150], r13d
0x180016090  jbe     loc_180016280
0x180016096  mov     r9d, r14d
0x180016099  mov     [rsp+1A0h+hkey], r13
0x18001609e  lea     r8, aI; "%i"
0x1800160a5  mov     edx, 0Ch; unsigned __int64
0x1800160aa  lea     rcx, [rbp+0A0h+var_60]; unsigned __int16 *
0x1800160ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800160b3  test    eax, eax
0x1800160b5  js      short loc_180016120
0x1800160b7  lea     r9, [rsp+1A0h+hkey]; struct CUwfRegKey *
0x1800160bc  mov     r8d, 20019h; unsigned int
0x1800160c2  lea     rdx, [rbp+0A0h+var_60]; unsigned __int16 *
0x1800160c6  lea     rcx, [rsp+1A0h+var_140]; this
0x1800160cb  call    ?OpenSubKey@CUwfRegKey@@QEAAJPEBGKAEAV1@@Z; CUwfRegKey::OpenSubKey(ushort const *,ulong,CUwfRegKey &)
0x1800160d0  test    eax, eax
0x1800160d2  js      short loc_180016120
0x1800160d4  mov     rbx, [rsp+1A0h+hkey]
0x1800160d9  lea     rax, [rsp+1A0h+Type]
0x1800160de  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800160e3  lea     r9, [rsp+1A0h+Type+4]; lpType
0x1800160e8  lea     rax, [rsp+1A0h+var_144]
0x1800160ed  mov     dword ptr [rsp+1A0h+Type+4], r13d
0x1800160f2  xor     r8d, r8d; lpReserved
0x1800160f5  mov     [rsp+1A0h+lpData], rax; lpData
0x1800160fa  lea     rdx, ValueName; "VolumeEnabled"
0x180016101  mov     dword ptr [rsp+1A0h+Type], esi
0x180016105  mov     rcx, rbx; hKey
0x180016108  call    cs:__imp_RegQueryValueExW
0x18001610e  test    eax, eax
0x180016110  jz      short loc_18001613D
0x180016112  jle     short loc_18001611E
0x180016114  movzx   eax, ax
0x180016117  or      eax, 80070000h
0x18001611c  test    eax, eax
0x18001611e  jns     short loc_180016149
0x180016120  lea     rcx, [rsp+1A0h+hkey]; this
0x180016125  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18001612a  inc     r14d
0x18001612d  cmp     r14d, dword ptr [rsp+1A0h+var_150]
0x180016132  jb      loc_180016096
0x180016138  jmp     loc_180016272
0x18001613d  cmp     dword ptr [rsp+1A0h+Type+4], esi
0x180016141  jnz     short loc_180016120
0x180016143  cmp     dword ptr [rsp+1A0h+Type], esi
0x180016147  jnz     short loc_180016120
0x180016149  cmp     dword ptr [rsp+1A0h+var_144], 1
0x18001614e  jnz     short loc_180016120
0x180016150  xor     edx, edx; Val
0x180016152  lea     rcx, [rbp+0A0h+var_120]; void *
0x180016156  mov     r8d, 0C0h; Size
0x18001615c  call    memset_0
0x180016161  mov     [rsp+1A0h+var_128], r13d
0x180016166  test    rdi, rdi
0x180016169  jz      short loc_180016177
0x18001616b  mov     rcx, rdi
0x18001616e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016174  mov     rdi, r13
0x180016177  lea     rax, [rsp+1A0h+Type]
0x18001617c  mov     dword ptr [rsp+1A0h+Type+4], r13d
0x180016181  mov     [rsp+1A0h+pcbData], rax; pcbData
0x180016186  lea     r8, aVolumename; "VolumeName"
0x18001618d  lea     rax, [rsp+1A0h+Type+4]
0x180016192  mov     [rsp+1A0h+lpcbData], r13; pvData
0x180016197  mov     esi, 2
0x18001619c  mov     [rsp+1A0h+lpData], rax; pdwType
0x1800161a1  mov     r9d, esi; dwFlags
0x1800161a4  mov     dword ptr [rsp+1A0h+Type], r13d
0x1800161a9  xor     edx, edx; lpSubKey
0x1800161ab  mov     rcx, rbx; hkey
0x1800161ae  call    cs:__imp_RegGetValueW
0x1800161b4  test    eax, eax
0x1800161b6  jz      short loc_1800161BD
0x1800161b8  mov     rsi, r13
0x1800161bb  jmp     short loc_18001621A
0x1800161bd  mov     ecx, dword ptr [rsp+1A0h+Type]
0x1800161c1  mov     rax, rsi
0x1800161c4  shr     rcx, 1
0x1800161c7  mul     rcx
0x1800161ca  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800161d1  cmovb   rax, rcx
0x1800161d5  mov     rcx, rax; unsigned __int64
0x1800161d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800161dd  mov     rsi, rax
0x1800161e0  test    rax, rax
0x1800161e3  jz      short loc_180016228
0x1800161e5  lea     rax, [rsp+1A0h+Type]
0x1800161ea  mov     r9d, 2; dwFlags
0x1800161f0  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800161f5  lea     r8, aVolumename; "VolumeName"
0x1800161fc  lea     rax, [rsp+1A0h+Type+4]
0x180016201  mov     [rsp+1A0h+lpcbData], rsi; pvData
0x180016206  xor     edx, edx; lpSubKey
0x180016208  mov     [rsp+1A0h+lpData], rax; pdwType
0x18001620d  mov     rcx, rbx; hkey
0x180016210  call    cs:__imp_RegGetValueW
0x180016216  test    eax, eax
0x180016218  jz      short loc_180016245
0x18001621a  jle     short loc_180016226
0x18001621c  movzx   eax, ax
0x18001621f  or      eax, 80070000h
0x180016224  test    eax, eax
0x180016226  jns     short loc_180016248
0x180016228  mov     rcx, rsi
0x18001622b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016231  lea     rcx, [rsp+1A0h+hkey]; this
0x180016236  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18001623b  mov     esi, 4
0x180016240  jmp     loc_18001612A
0x180016245  mov     rdi, rsi
0x180016248  lea     r9, [rsp+1A0h+var_128]; unsigned int *
0x18001624d  mov     [rsp+1A0h+lpData], r12; unsigned int *
0x180016252  lea     r8, [rbp+0A0h+var_120]; struct _UWFVOL_OVERLAY_DATA_OUTPUT *
0x180016256  mov     rdx, rdi; unsigned __int16 *
0x180016259  call    ?GetOverlayInformation@CUwfManagement@@AEAAJPEBGPEAU_UWFVOL_OVERLAY_DATA_OUTPUT@@PEAK2@Z; CUwfManagement::GetOverlayInformation(ushort const *,_UWFVOL_OVERLAY_DATA_OUTPUT *,ulong *,ulong *)
0x18001625e  lea     rcx, [rsp+1A0h+hkey]; this
0x180016263  test    eax, eax
0x180016265  js      short loc_180016236
0x180016267  mov     r15d, 1
0x18001626d  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180016272  test    rdi, rdi
0x180016275  jz      short loc_180016280
0x180016277  mov     rcx, rdi
0x18001627a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180016280  neg     r15d
0x180016283  lea     rcx, [rsp+1A0h+var_140]; this
0x180016288  sbb     ebx, ebx
0x18001628a  not     ebx
0x18001628c  and     ebx, 80070002h
0x180016292  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180016297  lea     rcx, [rsp+1A0h+var_138]; this
0x18001629c  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x1800162a1  lea     rcx, [rsp+1A0h+hKey]; this
0x1800162a6  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x1800162ab  mov     eax, ebx
0x1800162ad  mov     rcx, [rbp+0A0h+var_48]
0x1800162b1  xor     rcx, rsp; StackCookie
0x1800162b4  call    __security_check_cookie
0x1800162b9  add     rsp, 168h
0x1800162c0  pop     r15
0x1800162c2  pop     r14
0x1800162c4  pop     r13
0x1800162c6  pop     r12
0x1800162c8  pop     rdi
0x1800162c9  pop     rsi
0x1800162ca  pop     rbx
0x1800162cb  pop     rbp
0x1800162cc  retn
```
