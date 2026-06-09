# CSBEFilePropertyStore::GetValueForMap_(PKEY_TO_FSDK_MAP const *,tagPROPVARIANT *)

- ea: `0x18002b794`
- end: `0x18002b966`
- name: `?GetValueForMap_@CSBEFilePropertyStore@@AEAAJPEBUPKEY_TO_FSDK_MAP@@PEAUtagPROPVARIANT@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(CSBEFilePropertyStore *__hidden this, const struct PKEY_TO_FSDK_MAP *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002b720`

## callees

- `0x180001c00`
- `0x18000624c`
- `0x18002ae94`
- `0x18002b45c`
- `0x18002b794`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b7e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b8be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b934`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b7e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b8be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002b934`
- `ole32!CoTaskMemAlloc` at `0x18002b826`
- `ole32!CoTaskMemAlloc` at `0x18002b826`
- `ole32!PropVariantClear` at `0x18002b862`
- `ole32!PropVariantClear` at `0x18002b8ad`
- `ole32!PropVariantClear` at `0x18002b8da`
- `ole32!PropVariantClear` at `0x18002b955`
- `ole32!PropVariantClear` at `0x18002b862`
- `ole32!PropVariantClear` at `0x18002b8ad`
- `ole32!PropVariantClear` at `0x18002b8da`
- `ole32!PropVariantClear` at `0x18002b955`

## pseudocode

```c
__int64 __fastcall CSBEFilePropertyStore::GetValueForMap_(
        CSBEFilePropertyStore *this,
        const struct PKEY_TO_FSDK_MAP *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v5; // rcx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rax
  unsigned __int16 *v9; // rax
  int SBEProperty; // ebx
  CSbePropertyGet *v11; // rsi
  __int128 v12; // xmm0
  BYTE *pData; // xmm1_8
  __int128 v15; // [rsp+20h] [rbp-40h] BYREF
  BYTE *v16; // [rsp+30h] [rbp-30h]
  PROPVARIANT pvar; // [rsp+38h] [rbp-28h] BYREF

  v16 = 0;
  v5 = *((_QWORD *)a2 + 3);
  v15 = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( !(unsigned int)_o__wcsicmp(v5, L"Is_Protected") )
  {
    v7 = L"WM/WMRVContentProtected";
    goto LABEL_13;
  }
  if ( *((_DWORD *)a2 + 4) != PKEY_MIMEType.pid )
    goto LABEL_12;
  v8 = *(_QWORD *)a2 - *(_QWORD *)&PKEY_MIMEType.fmtid.Data1;
  if ( *(_QWORD *)a2 == *(_QWORD *)&PKEY_MIMEType.fmtid.Data1 )
    v8 = *((_QWORD *)a2 + 1) - *(_QWORD *)PKEY_MIMEType.fmtid.Data4;
  if ( v8 )
  {
LABEL_12:
    v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
LABEL_13:
    v11 = (CSBEFilePropertyStore *)((char *)this + 576);
    SBEProperty = CSbePropertyGet::GetSBEProperty(v11, v7, &pvar);
    if ( SBEProperty < 0 )
      return (unsigned int)SBEProperty;
    goto LABEL_14;
  }
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x14u);
  pvar.hVal.QuadPart = (LONGLONG)v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  pvar.vt = 31;
  SBEProperty = StringCchCopyW(v9, 0xAu, L"video/wtv");
  if ( SBEProperty < 0 )
  {
    PropVariantClear(&pvar);
    return (unsigned int)SBEProperty;
  }
  v11 = (CSBEFilePropertyStore *)((char *)this + 576);
LABEL_14:
  if ( pvar.vt == 31 && (!pvar.hVal.QuadPart || !*pvar.bstrVal) )
    PropVariantClear(&pvar);
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3), L"Is_Protected") || pvar.vt == 11 && pvar.iVal )
  {
    if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 3), L"WM/Picture") )
    {
      SBEProperty = GetBitmapStreamFromSBEProperty((__int64)&pvar, (__int64)&v15);
      if ( SBEProperty < 0 )
        return (unsigned int)SBEProperty;
      PropVariantClear(&pvar);
      v12 = v15;
      pData = v16;
      goto LABEL_23;
    }
LABEL_22:
    v12 = *(_OWORD *)&pvar.vt;
    pData = pvar.bstrblobVal.pData;
LABEL_23:
    *(_OWORD *)&a3->vt = v12;
    a3->bstrblobVal.pData = pData;
    return (unsigned int)SBEProperty;
  }
  PropVariantClear(&pvar);
  SBEProperty = CSbePropertyGet::GetSBEProperty(v11, L"WM/WMRVContentProtected", &pvar);
  if ( SBEProperty >= 0 )
    goto LABEL_22;
  return (unsigned int)SBEProperty;
}

```

## disassembly

```asm
0x18002b794  push    rbp
0x18002b796  push    rbx
0x18002b797  push    rsi
0x18002b798  push    rdi
0x18002b799  push    r12
0x18002b79b  push    r14
0x18002b79d  push    r15
0x18002b79f  mov     rbp, rsp
0x18002b7a2  sub     rsp, 60h
0x18002b7a6  mov     rax, cs:__security_cookie
0x18002b7ad  xor     rax, rsp
0x18002b7b0  mov     [rbp+var_10], rax
0x18002b7b4  mov     rdi, rdx
0x18002b7b7  xor     eax, eax
0x18002b7b9  mov     rsi, rcx
0x18002b7bc  mov     [rbp+var_30], rax
0x18002b7c0  xorps   xmm0, xmm0
0x18002b7c3  mov     qword ptr [rbp+pvar+10h], rax
0x18002b7c7  xorps   xmm1, xmm1
0x18002b7ca  lea     rdx, aIsProtected; "Is_Protected"
0x18002b7d1  mov     rcx, [rdi+18h]
0x18002b7d5  mov     r14, r8
0x18002b7d8  movups  [rbp+var_40], xmm0
0x18002b7dc  movups  xmmword ptr [rbp+pvar], xmm1
0x18002b7e0  call    cs:__imp__o__wcsicmp
0x18002b7e6  xor     r15d, r15d
0x18002b7e9  mov     r12d, 1Fh
0x18002b7ef  test    eax, eax
0x18002b7f1  jnz     short loc_18002B7FC
0x18002b7f3  lea     rdx, aWmWmrvcontentp; "WM/WMRVContentProtected"
0x18002b7fa  jmp     short loc_18002B87A
0x18002b7fc  mov     eax, cs:PKEY_MIMEType.pid
0x18002b802  cmp     [rdi+10h], eax
0x18002b805  jnz     short loc_18002B876
0x18002b807  mov     rax, [rdi]
0x18002b80a  sub     rax, qword ptr cs:PKEY_MIMEType.fmtid.Data1
0x18002b811  jnz     short loc_18002B81E
0x18002b813  mov     rax, [rdi+8]
0x18002b817  sub     rax, qword ptr cs:PKEY_MIMEType.fmtid.Data4
0x18002b81e  test    rax, rax
0x18002b821  jnz     short loc_18002B876
0x18002b823  lea     ecx, [rax+14h]; cb
0x18002b826  call    cs:__imp_CoTaskMemAlloc
0x18002b82c  mov     qword ptr [rbp+pvar+8], rax
0x18002b830  test    rax, rax
0x18002b833  jnz     short loc_18002B83F
0x18002b835  mov     ebx, 8007000Eh
0x18002b83a  jmp     loc_18002B90C
0x18002b83f  lea     r8, aVideoWtv; "video/wtv"
0x18002b846  mov     word ptr [rbp+pvar], r12w
0x18002b84b  mov     edx, 0Ah; unsigned __int64
0x18002b850  mov     rcx, rax; unsigned __int16 *
0x18002b853  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b858  mov     ebx, eax
0x18002b85a  test    eax, eax
0x18002b85c  jns     short loc_18002B86D
0x18002b85e  lea     rcx, [rbp+pvar]; pvar
0x18002b862  call    cs:__imp_PropVariantClear
0x18002b868  jmp     loc_18002B90C
0x18002b86d  add     rsi, 240h
0x18002b874  jmp     short loc_18002B893
0x18002b876  mov     rdx, [rdi+18h]; unsigned __int16 *
0x18002b87a  add     rsi, 240h
0x18002b881  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18002b885  mov     rcx, rsi; this
0x18002b888  call    ?GetSBEProperty@CSbePropertyGet@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z; CSbePropertyGet::GetSBEProperty(ushort const *,tagPROPVARIANT *)
0x18002b88d  mov     ebx, eax
0x18002b88f  test    eax, eax
0x18002b891  js      short loc_18002B90C
0x18002b893  cmp     word ptr [rbp+pvar], r12w
0x18002b898  jnz     short loc_18002B8B3
0x18002b89a  mov     rax, qword ptr [rbp+pvar+8]
0x18002b89e  test    rax, rax
0x18002b8a1  jz      short loc_18002B8A9
0x18002b8a3  cmp     [rax], r15w
0x18002b8a7  jnz     short loc_18002B8B3
0x18002b8a9  lea     rcx, [rbp+pvar]; pvar
0x18002b8ad  call    cs:__imp_PropVariantClear
0x18002b8b3  mov     rcx, [rdi+18h]
0x18002b8b7  lea     rdx, aIsProtected; "Is_Protected"
0x18002b8be  call    cs:__imp__o__wcsicmp
0x18002b8c4  test    eax, eax
0x18002b8c6  jnz     short loc_18002B929
0x18002b8c8  cmp     word ptr [rbp+pvar], 0Bh
0x18002b8cd  jnz     short loc_18002B8D6
0x18002b8cf  cmp     word ptr [rbp+pvar+8], r15w
0x18002b8d4  jnz     short loc_18002B929
0x18002b8d6  lea     rcx, [rbp+pvar]; pvar
0x18002b8da  call    cs:__imp_PropVariantClear
0x18002b8e0  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18002b8e4  mov     rcx, rsi; this
0x18002b8e7  lea     rdx, aWmWmrvcontentp; "WM/WMRVContentProtected"
0x18002b8ee  call    ?GetSBEProperty@CSbePropertyGet@@QEAAJPEBGPEAUtagPROPVARIANT@@@Z; CSbePropertyGet::GetSBEProperty(ushort const *,tagPROPVARIANT *)
0x18002b8f3  mov     ebx, eax
0x18002b8f5  test    eax, eax
0x18002b8f7  js      short loc_18002B90C
0x18002b8f9  movups  xmm0, xmmword ptr [rbp+pvar]
0x18002b8fd  movsd   xmm1, qword ptr [rbp+pvar+10h]
0x18002b902  movups  xmmword ptr [r14], xmm0
0x18002b906  movsd   qword ptr [r14+10h], xmm1
0x18002b90c  mov     eax, ebx
0x18002b90e  mov     rcx, [rbp+var_10]
0x18002b912  xor     rcx, rsp; StackCookie
0x18002b915  call    __security_check_cookie
0x18002b91a  add     rsp, 60h
0x18002b91e  pop     r15
0x18002b920  pop     r14
0x18002b922  pop     r12
0x18002b924  pop     rdi
0x18002b925  pop     rsi
0x18002b926  pop     rbx
0x18002b927  pop     rbp
0x18002b928  retn
0x18002b929  mov     rcx, [rdi+18h]
0x18002b92d  lea     rdx, aWmPicture_0; "WM/Picture"
0x18002b934  call    cs:__imp__o__wcsicmp
0x18002b93a  test    eax, eax
0x18002b93c  jnz     short loc_18002B8F9
0x18002b93e  lea     rdx, [rbp+var_40]
0x18002b942  lea     rcx, [rbp+pvar]
0x18002b946  call    GetBitmapStreamFromSBEProperty
0x18002b94b  mov     ebx, eax
0x18002b94d  test    eax, eax
0x18002b94f  js      short loc_18002B90C
0x18002b951  lea     rcx, [rbp+pvar]; pvar
0x18002b955  call    cs:__imp_PropVariantClear
0x18002b95b  movups  xmm0, [rbp+var_40]
0x18002b95f  movsd   xmm1, [rbp+var_30]
0x18002b964  jmp     short loc_18002B902
```
