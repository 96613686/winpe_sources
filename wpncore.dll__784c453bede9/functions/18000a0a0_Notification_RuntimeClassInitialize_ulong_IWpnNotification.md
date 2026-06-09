# Notification::RuntimeClassInitialize(ulong,IWpnNotification *)

- ea: `0x18000a0a0`
- end: `0x18000a77e`
- name: `?RuntimeClassInitialize@Notification@@QEAAJKPEAUIWpnNotification@@@Z`
- size: `1758`
- prototype: `__int64 __fastcall(Notification *__hidden this, unsigned int, struct IWpnNotification *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ff0`

## callees

- `0x180004e38`
- `0x180009ed0`
- `0x18000a0a0`
- `0x18000c280`
- `0x18000e5f4`
- `0x18006e5ac`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Notification::RuntimeClassInitialize(Notification *this, int a2, struct IWpnNotification *a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  __int64 (__fastcall *v9)(struct IWpnNotification *, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall *v16)(struct IWpnNotification *, __int64 *); // rbx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rbx
  char *DeepCopyStream; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  unsigned int v25; // edi
  const char *v26; // r9
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 result; // rax
  int v31; // eax
  int v32; // [rsp+20h] [rbp-198h] BYREF
  int v33; // [rsp+24h] [rbp-194h] BYREF
  _QWORD *v34; // [rsp+28h] [rbp-190h] BYREF
  __int64 v35; // [rsp+30h] [rbp-188h] BYREF
  __int64 v36; // [rsp+38h] [rbp-180h] BYREF
  __int64 v37; // [rsp+40h] [rbp-178h] BYREF
  __int64 v38; // [rsp+48h] [rbp-170h] BYREF
  __int64 v39; // [rsp+50h] [rbp-168h] BYREF
  __int64 v40; // [rsp+58h] [rbp-160h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-158h] BYREF
  __int64 v42; // [rsp+68h] [rbp-150h]
  __int64 v43; // [rsp+70h] [rbp-148h]
  LPVOID v44; // [rsp+78h] [rbp-140h] BYREF
  __int64 v45; // [rsp+80h] [rbp-138h]
  __int64 v46; // [rsp+88h] [rbp-130h]
  LPVOID v47; // [rsp+90h] [rbp-128h] BYREF
  __int64 v48; // [rsp+98h] [rbp-120h]
  __int64 v49; // [rsp+A0h] [rbp-118h]
  LPVOID v50; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-108h]
  __int64 v52; // [rsp+B8h] [rbp-100h]
  __int64 v53; // [rsp+C0h] [rbp-F8h]
  LPVOID v54; // [rsp+C8h] [rbp-F0h]
  __int64 v55; // [rsp+D0h] [rbp-E8h]
  __int64 v56; // [rsp+D8h] [rbp-E0h]
  _DWORD v57[2]; // [rsp+E0h] [rbp-D8h] BYREF
  LPVOID v58; // [rsp+E8h] [rbp-D0h]
  LPVOID v59; // [rsp+F0h] [rbp-C8h]
  LPVOID v60; // [rsp+F8h] [rbp-C0h]
  __int64 v61; // [rsp+100h] [rbp-B8h]
  LPVOID v62; // [rsp+108h] [rbp-B0h]
  LPVOID v63; // [rsp+110h] [rbp-A8h]
  __int64 v64; // [rsp+118h] [rbp-A0h]
  __int64 v65; // [rsp+120h] [rbp-98h]
  int v66; // [rsp+128h] [rbp-90h]
  int v67; // [rsp+12Ch] [rbp-8Ch]
  __int64 v68; // [rsp+130h] [rbp-88h]
  bool v69; // [rsp+138h] [rbp-80h]
  int v70; // [rsp+139h] [rbp-7Fh]
  __int16 v71; // [rsp+13Dh] [rbp-7Bh]
  char v72; // [rsp+13Fh] [rbp-79h]
  _QWORD *v73; // [rsp+140h] [rbp-78h]
  GUID v74; // [rsp+148h] [rbp-70h]
  __int64 v75; // [rsp+158h] [rbp-60h]
  __int64 v76; // [rsp+160h] [rbp-58h]
  char v77; // [rsp+170h] [rbp-48h] BYREF
  GUID v78; // [rsp+178h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v54 = 0;
  v55 = -1;
  v56 = -1;
  try
  {
    v6 = (*(__int64 (**)(void))(*(_QWORD *)a3 + 32LL))();
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v6,
        v32);
    v50 = 0;
    v51 = -1;
    v52 = -1;
    v7 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a3 + 40LL))(a3, &v50);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v7,
        v32);
    v47 = 0;
    v48 = -1;
    v49 = -1;
    v8 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a3 + 120LL))(a3, &v47);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v8,
        v32);
    v36 = 0;
    v9 = *(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a3 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v10 = v9(a3, &v36);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v10,
        v32);
    v44 = 0;
    v45 = -1;
    v46 = -1;
    v11 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a3 + 56LL))(a3, &v44);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v11,
        v32);
    pv = 0;
    v42 = -1;
    v43 = -1;
    v12 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPVOID *))(*(_QWORD *)a3 + 64LL))(a3, &pv);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v12,
        v32);
    v38 = 0;
    v13 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a3 + 72LL))(a3, &v38);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v13,
        v32);
    v39 = 0;
    v14 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a3 + 88LL))(a3, &v39);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v14,
        v32);
    v33 = 0;
    v15 = (*(__int64 (__fastcall **)(struct IWpnNotification *, int *))(*(_QWORD *)a3 + 104LL))(a3, &v33);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v15,
        v32);
    v35 = 0;
    v16 = *(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a3 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v17 = v16(a3, &v35);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v17,
        v32);
    v78 = GUID_NULL;
    v18 = (*(__int64 (__fastcall **)(struct IWpnNotification *, GUID *))(*(_QWORD *)a3 + 112LL))(a3, &v78);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v18,
        v32);
    v32 = 0;
    v19 = (*(__int64 (__fastcall **)(struct IWpnNotification *, int *))(*(_QWORD *)a3 + 128LL))(a3, &v32);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v19,
        v32);
    v40 = 0;
    v20 = (*(__int64 (__fastcall **)(struct IWpnNotification *, __int64 *))(*(_QWORD *)a3 + 136LL))(a3, &v40);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
        (const char *)(unsigned int)v20,
        v32);
    v21 = 0;
    v53 = 0;
    if ( v36 )
    {
      DeepCopyStream = (char *)GetDeepCopyStream(&v37);
      if ( &v77 != DeepCopyStream )
      {
        v21 = *(_QWORD *)DeepCopyStream;
        *(_QWORD *)DeepCopyStream = 0;
      }
      v53 = v21;
      v23 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    v24 = 0;
    v34 = 0;
    if ( v35 )
    {
      v37 = v35;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      v31 = Microsoft::WRL::Details::MakeAndInitialize<WpnNotificationData,WpnNotificationData,IWpnNotificationData *>(
              &v34,
              &v37);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
          (const char *)(unsigned int)v31,
          v32);
      v24 = v34;
    }
    v57[0] = a2;
    v57[1] = 0;
    v58 = v54;
    v59 = v50;
    v60 = v47;
    v61 = v21;
    v62 = v44;
    v63 = pv;
    v64 = v38;
    v65 = v39;
    v66 = v33;
    v67 = 0;
    v68 = v40;
    v69 = v32 != 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = v24;
    v74 = v78;
    v75 = 1;
    v76 = 0;
    v25 = Notification::RuntimeClassInitialize(this, (const struct Notification::Initializer *)v57);
    v27 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v27 + 16LL))(v27, *v27);
    }
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v28 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v42 = 0;
    v43 = 0;
    if ( v44 )
    {
      CoTaskMemFree(v44);
      v44 = 0;
    }
    v45 = 0;
    v46 = 0;
    v29 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v47 )
    {
      CoTaskMemFree(v47);
      v47 = 0;
    }
    v48 = 0;
    v49 = 0;
    if ( v50 )
    {
      CoTaskMemFree(v50);
      v50 = 0;
    }
    v51 = 0;
    v52 = 0;
    if ( v54 )
      CoTaskMemFree(v54);
    result = v25;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x75,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notification.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x18000a0a0  mov     r11, rsp
0x18000a0a3  mov     [r11+20h], rbx
0x18000a0a7  push    rsi
0x18000a0a8  push    rdi
0x18000a0a9  push    r12
0x18000a0ab  push    r14
0x18000a0ad  push    r15
0x18000a0af  sub     rsp, 190h
0x18000a0b6  mov     rax, cs:__security_cookie
0x18000a0bd  xor     rax, rsp
0x18000a0c0  mov     [rsp+1B8h+var_30], rax
0x18000a0c8  mov     rdi, r8
0x18000a0cb  mov     r14d, edx
0x18000a0ce  mov     rsi, rcx
0x18000a0d1  xor     r15d, r15d
0x18000a0d4  mov     [r11-0F0h], r15
0x18000a0db  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000a0df  mov     [r11-0E8h], r12
0x18000a0e6  mov     [r11-0E0h], r12
0x18000a0ed  mov     rax, [r8]
0x18000a0f0  lea     rdx, [r11-0F0h]
0x18000a0f7  mov     rcx, r8
0x18000a0fa  mov     rax, [rax+20h]
0x18000a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a103  mov     rcx, [rsp+1B8h]; this
0x18000a10b  test    eax, eax
0x18000a10d  js      loc_18000A621
0x18000a113  mov     [rsp+1B8h+var_110], r15
0x18000a11b  mov     [rsp+1B8h+var_108], r12
0x18000a123  mov     [rsp+1B8h+var_100], r12
0x18000a12b  mov     rax, [rdi]
0x18000a12e  lea     rdx, [rsp+1B8h+var_110]
0x18000a136  mov     rcx, rdi
0x18000a139  mov     rax, [rax+28h]
0x18000a13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a142  mov     rcx, [rsp+1B8h]; this
0x18000a14a  test    eax, eax
0x18000a14c  js      loc_18000A636
0x18000a152  mov     [rsp+1B8h+var_128], r15
0x18000a15a  mov     [rsp+1B8h+var_120], r12
0x18000a162  mov     [rsp+1B8h+var_118], r12
0x18000a16a  mov     rax, [rdi]
0x18000a16d  lea     rdx, [rsp+1B8h+var_128]
0x18000a175  mov     rcx, rdi
0x18000a178  mov     rax, [rax+78h]
0x18000a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a181  mov     rcx, [rsp+1B8h]; this
0x18000a189  test    eax, eax
0x18000a18b  js      loc_18000A64B
0x18000a191  mov     [rsp+1B8h+var_180], r15
0x18000a196  mov     rax, [rdi]
0x18000a199  mov     rbx, [rax+30h]
0x18000a19d  lea     rcx, [rsp+1B8h+var_180]
0x18000a1a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a1a7  lea     rdx, [rsp+1B8h+var_180]
0x18000a1ac  mov     rcx, rdi
0x18000a1af  mov     rax, rbx
0x18000a1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b7  mov     rcx, [rsp+1B8h]; this
0x18000a1bf  test    eax, eax
0x18000a1c1  js      loc_18000A660
0x18000a1c7  mov     [rsp+1B8h+var_140], r15
0x18000a1cc  mov     [rsp+1B8h+var_138], r12
0x18000a1d4  mov     [rsp+1B8h+var_130], r12
0x18000a1dc  mov     rax, [rdi]
0x18000a1df  lea     rdx, [rsp+1B8h+var_140]
0x18000a1e4  mov     rcx, rdi
0x18000a1e7  mov     rax, [rax+38h]
0x18000a1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f0  mov     rcx, [rsp+1B8h]; this
0x18000a1f8  test    eax, eax
0x18000a1fa  js      loc_18000A675
0x18000a200  mov     [rsp+1B8h+pv], r15
0x18000a205  mov     [rsp+1B8h+var_150], r12
0x18000a20a  mov     [rsp+1B8h+var_148], r12
0x18000a20f  mov     rax, [rdi]
0x18000a212  lea     rdx, [rsp+1B8h+pv]
0x18000a217  mov     rcx, rdi
0x18000a21a  mov     rax, [rax+40h]
0x18000a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a223  mov     rcx, [rsp+1B8h]; this
0x18000a22b  test    eax, eax
0x18000a22d  js      loc_18000A68A
0x18000a233  mov     [rsp+1B8h+var_170], r15
0x18000a238  mov     rax, [rdi]
0x18000a23b  lea     rdx, [rsp+1B8h+var_170]
0x18000a240  mov     rcx, rdi
0x18000a243  mov     rax, [rax+48h]
0x18000a247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24c  mov     rcx, [rsp+1B8h]; this
0x18000a254  test    eax, eax
0x18000a256  js      loc_18000A69E
0x18000a25c  mov     [rsp+1B8h+var_168], r15
0x18000a261  mov     rax, [rdi]
0x18000a264  lea     rdx, [rsp+1B8h+var_168]
0x18000a269  mov     rcx, rdi
0x18000a26c  mov     rax, [rax+58h]
0x18000a270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a275  mov     rcx, [rsp+1B8h]; this
0x18000a27d  test    eax, eax
0x18000a27f  js      loc_18000A6B2
0x18000a285  mov     [rsp+1B8h+var_194], r15d
0x18000a28a  mov     rax, [rdi]
0x18000a28d  lea     rdx, [rsp+1B8h+var_194]
0x18000a292  mov     rcx, rdi
0x18000a295  mov     rax, [rax+68h]
0x18000a299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29e  mov     rcx, [rsp+1B8h]; this
0x18000a2a6  test    eax, eax
0x18000a2a8  js      loc_18000A6C6
0x18000a2ae  mov     [rsp+1B8h+var_188], r15
0x18000a2b3  mov     rax, [rdi]
0x18000a2b6  mov     rbx, [rax+60h]
0x18000a2ba  lea     rcx, [rsp+1B8h+var_188]
0x18000a2bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a2c4  lea     rdx, [rsp+1B8h+var_188]
0x18000a2c9  mov     rcx, rdi
0x18000a2cc  mov     rax, rbx
0x18000a2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d4  mov     rcx, [rsp+1B8h]; this
0x18000a2dc  test    eax, eax
0x18000a2de  js      loc_18000A6DB
0x18000a2e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000a2eb  movdqu  [rsp+1B8h+var_40], xmm0
0x18000a2f4  mov     rax, [rdi]
0x18000a2f7  lea     rdx, [rsp+1B8h+var_40]
0x18000a2ff  mov     rcx, rdi
0x18000a302  mov     rax, [rax+70h]
0x18000a306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a30b  mov     rcx, [rsp+1B8h]; this
0x18000a313  test    eax, eax
0x18000a315  js      loc_18000A6EF
0x18000a31b  mov     [rsp+1B8h+var_198], r15d; int
0x18000a320  mov     rax, [rdi]
0x18000a323  lea     rdx, [rsp+1B8h+var_198]
0x18000a328  mov     rcx, rdi
0x18000a32b  mov     rax, [rax+80h]
0x18000a332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a337  mov     rcx, [rsp+1B8h]; this
0x18000a33f  test    eax, eax
0x18000a341  js      loc_18000A703
0x18000a347  mov     [rsp+1B8h+var_160], r15
0x18000a34c  mov     rax, [rdi]
0x18000a34f  lea     rdx, [rsp+1B8h+var_160]
0x18000a354  mov     rcx, rdi
0x18000a357  mov     rax, [rax+88h]
0x18000a35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a363  mov     rcx, [rsp+1B8h]; this
0x18000a36b  test    eax, eax
0x18000a36d  js      loc_18000A717
0x18000a373  mov     ebx, r15d
0x18000a376  mov     [rsp+1B8h+var_F8], rbx
0x18000a37e  mov     rdx, [rsp+1B8h+var_180]
0x18000a383  test    rdx, rdx
0x18000a386  jz      short loc_18000A3C9
0x18000a388  lea     rcx, [rsp+1B8h+var_178]
0x18000a38d  call    ?GetDeepCopyStream@@YA?AV?$ComPtr@UIStream@@@WRL@Microsoft@@PEAUIStream@@@Z; GetDeepCopyStream(IStream *)
0x18000a392  lea     rcx, [rsp+1B8h+var_48]
0x18000a39a  cmp     rcx, rax
0x18000a39d  jz      short loc_18000A3A5
0x18000a39f  mov     rbx, [rax]
0x18000a3a2  mov     [rax], r15
0x18000a3a5  mov     [rsp+1B8h+var_F8], rbx
0x18000a3ad  mov     rcx, [rsp+1B8h+var_178]
0x18000a3b2  test    rcx, rcx
0x18000a3b5  jz      short loc_18000A3C9
0x18000a3b7  mov     [rsp+1B8h+var_178], r15
0x18000a3bc  mov     rax, [rcx]
0x18000a3bf  mov     rax, [rax+10h]
0x18000a3c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3c8  nop
0x18000a3c9  mov     rax, r15
0x18000a3cc  mov     [rsp+1B8h+var_190], rax
0x18000a3d1  mov     rcx, [rsp+1B8h+var_188]
0x18000a3d6  test    rcx, rcx
0x18000a3d9  jnz     loc_18000A72C
0x18000a3df  mov     [rsp+1B8h+var_D8], r14d
0x18000a3e7  xor     ecx, ecx
0x18000a3e9  mov     [rsp+1B8h+var_D4], ecx
0x18000a3f0  mov     rcx, [rsp+1B8h+var_F0]
0x18000a3f8  mov     [rsp+1B8h+var_D0], rcx
0x18000a400  mov     rcx, [rsp+1B8h+var_110]
0x18000a408  mov     [rsp+1B8h+var_C8], rcx
0x18000a410  mov     rcx, [rsp+1B8h+var_128]
0x18000a418  mov     [rsp+1B8h+var_C0], rcx
0x18000a420  mov     [rsp+1B8h+var_B8], rbx
0x18000a428  mov     rcx, [rsp+1B8h+var_140]
0x18000a42d  mov     [rsp+1B8h+var_B0], rcx
0x18000a435  mov     rcx, [rsp+1B8h+pv]
0x18000a43a  mov     [rsp+1B8h+var_A8], rcx
0x18000a442  mov     rcx, [rsp+1B8h+var_170]
0x18000a447  mov     [rsp+1B8h+var_A0], rcx
0x18000a44f  mov     rcx, [rsp+1B8h+var_168]
0x18000a454  mov     [rsp+1B8h+var_98], rcx
0x18000a45c  mov     ecx, [rsp+1B8h+var_194]
0x18000a460  mov     [rsp+1B8h+var_90], ecx
0x18000a467  xor     ecx, ecx
0x18000a469  mov     [rsp+1B8h+var_8C], ecx
0x18000a470  mov     rcx, [rsp+1B8h+var_160]
0x18000a475  mov     [rsp+1B8h+var_88], rcx
0x18000a47d  cmp     [rsp+1B8h+var_198], r15d
0x18000a482  setnz   [rsp+1B8h+var_80]
0x18000a48a  xor     ecx, ecx
0x18000a48c  mov     [rsp+1B8h+var_7F], ecx
0x18000a493  mov     [rsp+1B8h+var_7B], cx
0x18000a49b  mov     [rsp+1B8h+var_79], cl
0x18000a4a2  mov     [rsp+1B8h+var_78], rax
0x18000a4aa  movups  xmm0, [rsp+1B8h+var_40]
0x18000a4b2  movdqu  [rsp+1B8h+var_70], xmm0
0x18000a4bb  mov     [rsp+1B8h+var_60], 1
0x18000a4c7  mov     [rsp+1B8h+var_58], r15
0x18000a4cf  lea     rdx, [rsp+1B8h+var_D8]; struct Notification::Initializer *
0x18000a4d7  mov     rcx, rsi; this
0x18000a4da  call    ?RuntimeClassInitialize@Notification@@QEAAJAEBUInitializer@1@@Z; Notification::RuntimeClassInitialize(Notification::Initializer const &)
0x18000a4df  mov     edi, eax
0x18000a4e1  mov     rcx, [rsp+1B8h+var_190]
0x18000a4e6  test    rcx, rcx
0x18000a4e9  jz      short loc_18000A4FD
0x18000a4eb  mov     [rsp+1B8h+var_190], r15
0x18000a4f0  mov     rdx, [rcx]
0x18000a4f3  mov     rax, [rdx+10h]
0x18000a4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4fc  nop
0x18000a4fd  test    rbx, rbx
0x18000a500  jz      short loc_18000A512
0x18000a502  mov     rax, [rbx]
0x18000a505  mov     rcx, rbx
0x18000a508  mov     rax, [rax+10h]
0x18000a50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a511  nop
0x18000a512  mov     rcx, [rsp+1B8h+var_188]
0x18000a517  test    rcx, rcx
0x18000a51a  jz      short loc_18000A52E
0x18000a51c  mov     [rsp+1B8h+var_188], r15
0x18000a521  mov     rax, [rcx]
0x18000a524  mov     rax, [rax+10h]
0x18000a528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a52d  nop
0x18000a52e  mov     rcx, [rsp+1B8h+pv]; pv
0x18000a533  test    rcx, rcx
0x18000a536  jz      short loc_18000A543
0x18000a538  call    cs:__imp_CoTaskMemFree
0x18000a53e  mov     [rsp+1B8h+pv], r15
0x18000a543  mov     [rsp+1B8h+var_150], r15
0x18000a548  mov     [rsp+1B8h+var_148], r15
0x18000a54d  mov     rcx, [rsp+1B8h+var_140]; pv
0x18000a552  test    rcx, rcx
0x18000a555  jz      short loc_18000A562
0x18000a557  call    cs:__imp_CoTaskMemFree
0x18000a55d  mov     [rsp+1B8h+var_140], r15
0x18000a562  mov     [rsp+1B8h+var_138], r15
0x18000a56a  mov     [rsp+1B8h+var_130], r15
0x18000a572  mov     rcx, [rsp+1B8h+var_180]
0x18000a577  test    rcx, rcx
0x18000a57a  jz      short loc_18000A58E
0x18000a57c  mov     [rsp+1B8h+var_180], r15
0x18000a581  mov     rax, [rcx]
0x18000a584  mov     rax, [rax+10h]
0x18000a588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58d  nop
0x18000a58e  mov     rcx, [rsp+1B8h+var_128]; pv
0x18000a596  test    rcx, rcx
0x18000a599  jz      short loc_18000A5A9
0x18000a59b  call    cs:__imp_CoTaskMemFree
0x18000a5a1  mov     [rsp+1B8h+var_128], r15
0x18000a5a9  mov     [rsp+1B8h+var_120], r15
0x18000a5b1  mov     [rsp+1B8h+var_118], r15
0x18000a5b9  mov     rcx, [rsp+1B8h+var_110]; pv
0x18000a5c1  test    rcx, rcx
0x18000a5c4  jz      short loc_18000A5D4
0x18000a5c6  call    cs:__imp_CoTaskMemFree
0x18000a5cc  mov     [rsp+1B8h+var_110], r15
0x18000a5d4  mov     [rsp+1B8h+var_108], r15
0x18000a5dc  mov     [rsp+1B8h+var_100], r15
0x18000a5e4  mov     rcx, [rsp+1B8h+var_F0]; pv
0x18000a5ec  test    rcx, rcx
0x18000a5ef  jz      short loc_18000A5F7
0x18000a5f1  call    cs:__imp_CoTaskMemFree
0x18000a5f7  mov     eax, edi
0x18000a5f9  mov     rcx, [rsp+1B8h+var_30]
0x18000a601  xor     rcx, rsp; StackCookie
0x18000a604  call    __security_check_cookie
0x18000a609  mov     rbx, [rsp+1B8h+arg_18]
0x18000a611  add     rsp, 190h
0x18000a618  pop     r15
0x18000a61a  pop     r14
0x18000a61c  pop     r12
0x18000a61e  pop     rdi
0x18000a61f  pop     rsi
0x18000a620  retn
0x18000a621  mov     r9d, eax; char *
0x18000a624  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a62b  mov     edx, 4Eh ; 'N'; void *
0x18000a630  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a636  mov     r9d, eax; char *
0x18000a639  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a640  mov     edx, 50h ; 'P'; void *
0x18000a645  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a64b  mov     r9d, eax; char *
0x18000a64e  lea     r8, aOnecoreuapBase_87; "onecoreuap\\base\\diagnosis\\platform\\"...
  ... truncated ...
```
