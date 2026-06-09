# CStorageFolder::_GetObjectIDFromDisplayName(ushort *,ushort *,uint)

- ea: `0x180017834`
- end: `0x180017c82`
- name: `?_GetObjectIDFromDisplayName@CStorageFolder@@AEAAJPEAG0I@Z`
- size: `1102`
- prototype: `int(CStorageFolder *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800660d0`

## callees

- `0x180004110`
- `0x180016260`
- `0x180017834`
- `0x18002ff5c`
- `0x180039d74`
- `0x180039e80`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x180017ad0`
- `SHLWAPI!StrCmpIW` at `0x180017ad0`
- `ole32!CoTaskMemFree` at `0x180017b21`
- `ole32!CoTaskMemFree` at `0x180017b21`
- `ole32!PropVariantClear` at `0x180017b33`
- `ole32!PropVariantClear` at `0x180017bab`
- `ole32!PropVariantClear` at `0x180017b33`
- `ole32!PropVariantClear` at `0x180017bab`
- `ole32!CoCreateInstance` at `0x180017993`
- `ole32!CoCreateInstance` at `0x180017993`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CStorageFolder::_GetObjectIDFromDisplayName(
        CStorageFolder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  HRESULT PortableDeviceProperties; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // esi
  unsigned int i; // r14d
  PCWSTR psz2; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-48h] BYREF
  struct IPortableDevice *v15; // [rsp+40h] [rbp-40h] BYREF
  __int64 v16; // [rsp+48h] [rbp-38h] BYREF
  struct IPortableDeviceProperties *v17; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+58h] [rbp-28h] BYREF
  PROPVARIANT pvar; // [rsp+60h] [rbp-20h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+30h] BYREF

  psz2 = 0;
  v15 = 0;
  v18 = 0;
  v17 = 0;
  ppv = 0;
  v20 = 0;
  v16 = 0;
  memset(&pvar, 0, sizeof(pvar));
  PortableDeviceProperties = (*(__int64 (__fastcall **)(CStorageFolder *, _QWORD, struct IPortableDevice **))(*(_QWORD *)this + 136LL))(
                               this,
                               *((_QWORD *)this + 8),
                               &v15);
  v6 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v8 = 117;
LABEL_5:
    v9 = (unsigned int)PortableDeviceProperties;
LABEL_6:
    WPP_SF_d(v7[2], v8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v9);
    goto LABEL_47;
  }
  PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v15->lpVtbl->Capabilities)(
                               v15,
                               &v18);
  v6 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v8 = 118;
    goto LABEL_5;
  }
  PortableDeviceProperties = GetPortableDeviceProperties(v15, &v17);
  v6 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v8 = 119;
    goto LABEL_5;
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDeviceKeyCollection,
                               0,
                               1u,
                               &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                               &ppv);
  v6 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v8 = 120;
    goto LABEL_5;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
  PortableDeviceProperties = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64 *))(*(_QWORD *)v18 + 48LL))(
                               v18,
                               &WPD_FUNCTIONAL_CATEGORY_STORAGE,
                               &v16);
  v6 = PortableDeviceProperties;
  if ( PortableDeviceProperties < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v8 = 121;
    goto LABEL_5;
  }
  v10 = 0;
  for ( i = 0; !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v16 + 32LL))(v16, i, &pvar); ++i )
  {
    if ( pvar.vt != 31 )
    {
      v6 = -2147418113;
      goto LABEL_47;
    }
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v17->lpVtbl->GetValues)(
           v17,
           (LARGE_INTEGER)pvar.hVal.QuadPart,
           ppv,
           &v20);
    if ( v6 < 0 )
      goto LABEL_40;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PCWSTR *))(*(_QWORD *)v20 + 64LL))(
           v20,
           &WPD_OBJECT_NAME,
           &psz2) >= 0 )
    {
      if ( !StrCmpIW(a2, psz2) )
      {
        v10 = 1;
        v6 = 0;
        StringCchCopyW(a3, 0x104u, pvar.bstrVal);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, a2);
      }
      if ( psz2 )
      {
        CoTaskMemFree((LPVOID)psz2);
        psz2 = 0;
      }
    }
    PropVariantClear(&pvar);
    if ( v10 )
      goto LABEL_47;
  }
  if ( v6 >= 0 )
  {
    v6 = -2147024894;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
        (_DWORD)a2,
        2);
    goto LABEL_47;
  }
LABEL_40:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = 123;
    v9 = (unsigned int)v6;
    goto LABEL_6;
  }
LABEL_47:
  PropVariantClear(&pvar);
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
      (unsigned int)v6);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v17 )
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v17->lpVtbl->Release)(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v15 )
    ((void (__fastcall *)(struct IPortableDevice *))v15->lpVtbl->Release)(v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017834  mov     [rsp-28h+arg_8], rbx
0x180017839  mov     [rsp-28h+arg_10], rsi
0x18001783e  push    rbp
0x18001783f  push    rdi
0x180017840  push    r12
0x180017842  push    r14
0x180017844  push    r15
0x180017846  mov     rbp, rsp
0x180017849  sub     rsp, 80h
0x180017850  mov     r12, r8
0x180017853  mov     r15, rdx
0x180017856  mov     [rbp+psz2], 0
0x18001785e  mov     [rbp+var_40], 0
0x180017866  mov     [rbp+var_28], 0
0x18001786e  mov     [rbp+var_30], 0
0x180017876  mov     [rbp+var_48], 0
0x18001787e  mov     [rbp+arg_0], 0
0x180017886  mov     [rbp+var_38], 0
0x18001788e  xorps   xmm0, xmm0
0x180017891  xor     eax, eax
0x180017893  movups  xmmword ptr [rbp+pvar], xmm0
0x180017897  mov     qword ptr [rbp+pvar+10h], rax
0x18001789b  mov     rax, [rcx]
0x18001789e  lea     r8, [rbp+var_40]
0x1800178a2  mov     rdx, [rcx+40h]
0x1800178a6  mov     rax, [rax+88h]
0x1800178ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178b2  mov     ebx, eax
0x1800178b4  test    eax, eax
0x1800178b6  jns     short loc_1800178F6
0x1800178b8  lea     rdi, WPP_GLOBAL_Control
0x1800178bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c6  cmp     rcx, rdi
0x1800178c9  jz      loc_180017BA7
0x1800178cf  test    byte ptr [rcx+1Ch], 2
0x1800178d3  jz      loc_180017BA7
0x1800178d9  mov     edx, 75h ; 'u'
0x1800178de  mov     r9d, eax
0x1800178e1  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x1800178e8  mov     rcx, [rcx+10h]
0x1800178ec  call    WPP_SF_d
0x1800178f1  jmp     loc_180017BA7
0x1800178f6  mov     rcx, [rbp+var_40]
0x1800178fa  mov     rax, [rcx]
0x1800178fd  lea     rdx, [rbp+var_28]
0x180017901  mov     rax, [rax+30h]
0x180017905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001790a  mov     ebx, eax
0x18001790c  test    eax, eax
0x18001790e  jns     short loc_180017938
0x180017910  lea     rdi, WPP_GLOBAL_Control
0x180017917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001791e  cmp     rcx, rdi
0x180017921  jz      loc_180017BA7
0x180017927  test    byte ptr [rcx+1Ch], 2
0x18001792b  jz      loc_180017BA7
0x180017931  mov     edx, 76h ; 'v'
0x180017936  jmp     short loc_1800178DE
0x180017938  lea     rdx, [rbp+var_30]; struct IPortableDeviceProperties **
0x18001793c  mov     rcx, [rbp+var_40]; struct IPortableDevice *
0x180017940  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180017945  mov     ebx, eax
0x180017947  test    eax, eax
0x180017949  jns     short loc_180017976
0x18001794b  lea     rdi, WPP_GLOBAL_Control
0x180017952  mov     rcx, cs:WPP_GLOBAL_Control
0x180017959  cmp     rcx, rdi
0x18001795c  jz      loc_180017BA7
0x180017962  test    byte ptr [rcx+1Ch], 2
0x180017966  jz      loc_180017BA7
0x18001796c  mov     edx, 77h ; 'w'
0x180017971  jmp     loc_1800178DE
0x180017976  lea     rax, [rbp+var_48]
0x18001797a  mov     [rsp+80h+ppv], rax; ppv
0x18001797f  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180017986  xor     edx, edx; pUnkOuter
0x180017988  lea     r8d, [rdx+1]; dwClsContext
0x18001798c  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180017993  call    cs:__imp_CoCreateInstance
0x180017999  mov     ebx, eax
0x18001799b  test    eax, eax
0x18001799d  jns     short loc_1800179CA
0x18001799f  lea     rdi, WPP_GLOBAL_Control
0x1800179a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179ad  cmp     rcx, rdi
0x1800179b0  jz      loc_180017BA7
0x1800179b6  test    byte ptr [rcx+1Ch], 2
0x1800179ba  jz      loc_180017BA7
0x1800179c0  mov     edx, 78h ; 'x'
0x1800179c5  jmp     loc_1800178DE
0x1800179ca  mov     rcx, [rbp+var_48]
0x1800179ce  mov     rax, [rcx]
0x1800179d1  lea     rdx, WPD_OBJECT_NAME
0x1800179d8  mov     rax, [rax+28h]
0x1800179dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179e1  mov     rcx, [rbp+var_28]
0x1800179e5  mov     rax, [rcx]
0x1800179e8  lea     r8, [rbp+var_38]
0x1800179ec  lea     rdx, WPD_FUNCTIONAL_CATEGORY_STORAGE
0x1800179f3  mov     rax, [rax+30h]
0x1800179f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179fc  mov     ebx, eax
0x1800179fe  test    eax, eax
0x180017a00  jns     short loc_180017A2D
0x180017a02  lea     rdi, WPP_GLOBAL_Control
0x180017a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a10  cmp     rcx, rdi
0x180017a13  jz      loc_180017BA7
0x180017a19  test    byte ptr [rcx+1Ch], 2
0x180017a1d  jz      loc_180017BA7
0x180017a23  mov     edx, 79h ; 'y'
0x180017a28  jmp     loc_1800178DE
0x180017a2d  xor     esi, esi
0x180017a2f  xor     r14d, r14d
0x180017a32  lea     rdi, WPP_GLOBAL_Control
0x180017a39  mov     rcx, [rbp+var_38]
0x180017a3d  mov     rax, [rcx]
0x180017a40  lea     r8, [rbp+pvar]
0x180017a44  mov     edx, r14d
0x180017a47  mov     rax, [rax+20h]
0x180017a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a50  test    eax, eax
0x180017a52  jnz     loc_180017B4A
0x180017a58  mov     eax, 1Fh
0x180017a5d  cmp     ax, word ptr [rbp+pvar]
0x180017a61  jnz     loc_180017B6D
0x180017a67  mov     rcx, [rbp+arg_0]
0x180017a6b  test    rcx, rcx
0x180017a6e  jz      short loc_180017A84
0x180017a70  mov     rax, [rcx]
0x180017a73  mov     rax, [rax+10h]
0x180017a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a7c  mov     [rbp+arg_0], 0
0x180017a84  mov     rcx, [rbp+var_30]
0x180017a88  mov     rax, [rcx]
0x180017a8b  lea     r9, [rbp+arg_0]
0x180017a8f  mov     r8, [rbp+var_48]
0x180017a93  mov     rdx, qword ptr [rbp+pvar+8]
0x180017a97  mov     rax, [rax+28h]
0x180017a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aa0  mov     ebx, eax
0x180017aa2  test    eax, eax
0x180017aa4  js      loc_180017B4E
0x180017aaa  mov     rcx, [rbp+arg_0]
0x180017aae  mov     rax, [rcx]
0x180017ab1  lea     r8, [rbp+psz2]
0x180017ab5  lea     rdx, WPD_OBJECT_NAME
0x180017abc  mov     rax, [rax+40h]
0x180017ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ac5  test    eax, eax
0x180017ac7  js      short loc_180017B2F
0x180017ac9  mov     rdx, [rbp+psz2]; psz2
0x180017acd  mov     rcx, r15; psz1
0x180017ad0  call    cs:__imp_StrCmpIW
0x180017ad6  test    eax, eax
0x180017ad8  jnz     short loc_180017B18
0x180017ada  lea     esi, [rax+1]
0x180017add  xor     ebx, ebx
0x180017adf  mov     r8, qword ptr [rbp+pvar+8]; unsigned __int16 *
0x180017ae3  mov     edx, 104h; unsigned __int64
0x180017ae8  mov     rcx, r12; unsigned __int16 *
0x180017aeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017af7  cmp     rcx, rdi
0x180017afa  jz      short loc_180017B18
0x180017afc  test    byte ptr [rcx+1Ch], 40h
0x180017b00  jz      short loc_180017B18
0x180017b02  lea     edx, [rsi+79h]
0x180017b05  mov     r9, r15
0x180017b08  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180017b0f  mov     rcx, [rcx+10h]
0x180017b13  call    WPP_SF_S
0x180017b18  mov     rcx, [rbp+psz2]; pv
0x180017b1c  test    rcx, rcx
0x180017b1f  jz      short loc_180017B2F
0x180017b21  call    cs:__imp_CoTaskMemFree
0x180017b27  mov     [rbp+psz2], 0
0x180017b2f  lea     rcx, [rbp+pvar]; pvar
0x180017b33  call    cs:__imp_PropVariantClear
0x180017b39  test    esi, esi
0x180017b3b  jnz     short loc_180017B45
0x180017b3d  inc     r14d
0x180017b40  jmp     loc_180017A39
0x180017b45  cmp     esi, 1
0x180017b48  jz      short loc_180017BA7
0x180017b4a  test    ebx, ebx
0x180017b4c  jns     short loc_180017B74
0x180017b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b55  cmp     rcx, rdi
0x180017b58  jz      short loc_180017BA7
0x180017b5a  test    byte ptr [rcx+1Ch], 2
0x180017b5e  jz      short loc_180017BA7
0x180017b60  mov     edx, 7Bh ; '{'
0x180017b65  mov     r9d, ebx
0x180017b68  jmp     loc_1800178E1
0x180017b6d  mov     ebx, 8000FFFFh
0x180017b72  jmp     short loc_180017BA7
0x180017b74  mov     ebx, 80070002h
0x180017b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b80  cmp     rcx, rdi
0x180017b83  jz      short loc_180017BA7
0x180017b85  test    byte ptr [rcx+1Ch], 2
0x180017b89  jz      short loc_180017BA7
0x180017b8b  mov     edx, 7Ch ; '|'
0x180017b90  mov     dword ptr [rsp+80h+ppv], ebx
0x180017b94  mov     r9, r15
0x180017b97  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180017b9e  mov     rcx, [rcx+10h]
0x180017ba2  call    WPP_SF_Sd
0x180017ba7  lea     rcx, [rbp+pvar]; pvar
0x180017bab  call    cs:__imp_PropVariantClear
0x180017bb1  test    ebx, ebx
0x180017bb3  jns     short loc_180017BE0
0x180017bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bbc  cmp     rcx, rdi
0x180017bbf  jz      short loc_180017BE0
0x180017bc1  test    byte ptr [rcx+1Ch], 2
0x180017bc5  jz      short loc_180017BE0
0x180017bc7  mov     edx, 7Dh ; '}'
0x180017bcc  mov     r9d, ebx
0x180017bcf  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180017bd6  mov     rcx, [rcx+10h]
0x180017bda  call    WPP_SF_d
0x180017bdf  nop
0x180017be0  mov     rcx, [rbp+var_38]
0x180017be4  test    rcx, rcx
0x180017be7  jz      short loc_180017BF6
0x180017be9  mov     rax, [rcx]
0x180017bec  mov     rax, [rax+10h]
0x180017bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bf5  nop
0x180017bf6  mov     rcx, [rbp+arg_0]
0x180017bfa  test    rcx, rcx
0x180017bfd  jz      short loc_180017C0C
0x180017bff  mov     rax, [rcx]
0x180017c02  mov     rax, [rax+10h]
0x180017c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c0b  nop
0x180017c0c  mov     rcx, [rbp+var_48]
0x180017c10  test    rcx, rcx
0x180017c13  jz      short loc_180017C22
0x180017c15  mov     rax, [rcx]
0x180017c18  mov     rax, [rax+10h]
0x180017c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c21  nop
0x180017c22  mov     rcx, [rbp+var_30]
0x180017c26  test    rcx, rcx
0x180017c29  jz      short loc_180017C38
0x180017c2b  mov     rax, [rcx]
0x180017c2e  mov     rax, [rax+10h]
0x180017c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c37  nop
0x180017c38  mov     rcx, [rbp+var_28]
0x180017c3c  test    rcx, rcx
0x180017c3f  jz      short loc_180017C4E
0x180017c41  mov     rax, [rcx]
0x180017c44  mov     rax, [rax+10h]
0x180017c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c4d  nop
0x180017c4e  mov     rcx, [rbp+var_40]
0x180017c52  test    rcx, rcx
0x180017c55  jz      short loc_180017C64
0x180017c57  mov     rax, [rcx]
0x180017c5a  mov     rax, [rax+10h]
0x180017c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c63  nop
0x180017c64  mov     eax, ebx
0x180017c66  lea     r11, [rsp+80h+var_s0]
0x180017c6e  mov     rbx, [r11+38h]
0x180017c72  mov     rsi, [r11+40h]
0x180017c76  mov     rsp, r11
0x180017c79  pop     r15
0x180017c7b  pop     r14
0x180017c7d  pop     r12
0x180017c7f  pop     rdi
0x180017c80  pop     rbp
0x180017c81  retn
```
