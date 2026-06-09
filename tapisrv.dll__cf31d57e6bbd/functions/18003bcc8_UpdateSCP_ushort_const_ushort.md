# UpdateSCP(ushort const *,ushort *)

- ea: `0x18003bcc8`
- end: `0x18003c026`
- name: `?UpdateSCP@@YAJPEBGPEAG@Z`
- size: `862`
- prototype: `__int64 __fastcall(LPCWSTR lpszPathName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18003d4ec`

## callees

- `0x180001600`
- `0x180039080`
- `0x1800390e4`
- `0x18003ad1c`
- `0x18003bcc8`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bea9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bec5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bef5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bf10`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bea9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bec5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bef5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003bf10`
- `KERNEL32!GetComputerNameExW` at `0x18003bdcc`
- `KERNEL32!GetComputerNameExW` at `0x18003bdcc`
- `KERNEL32!GetLastError` at `0x18003bdd6`
- `KERNEL32!GetLastError` at `0x18003bdd6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003bff4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003bff4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003bd8a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003bd8a`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18003bdf6`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18003bdf6`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18003bfc9`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18003bfc9`

## string_xrefs

- `0x18003bd2c`: `serviceDNSName`
- `0x18003be97`: `serviceDNSName`
- `0x18003bd0e`: `serviceBindingInformation`
- `0x18003beea`: `serviceBindingInformation`
- `0x18003bf1a`: `serviceBindingInformation being updated`
- `0x18003bf30`: `serviceBindingInformation okay`
- `0x18003bed4`: `serviceDNSName being updated`
- `0x18003becd`: `serviceDNSName okay`
- `0x18003bf94`: `ScpUpdate: Failed to set SCP values. 0x%x`

## pseudocode

```c
__int64 __fastcall UpdateSCP(LPCWSTR lpszPathName, unsigned __int16 *a2)
{
  int v4; // r12d
  int v5; // r15d
  int v6; // ebx
  int v7; // edx
  __int64 v8; // rcx
  HRESULT Object; // eax
  int v10; // eax
  int v11; // r8d
  int v12; // r14d
  int v13; // esi
  __int64 v14; // rdi
  int v15; // eax
  const char *v16; // rdx
  int v17; // eax
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pMem; // [rsp+38h] [rbp-C8h] BYREF
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  void *ppObject; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int128 v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  _QWORD v27[3]; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v28; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+A8h] [rbp-58h]
  int v30; // [rsp+ACh] [rbp-54h]
  __int128 *v31; // [rsp+B0h] [rbp-50h]
  int v32; // [rsp+B8h] [rbp-48h]
  const wchar_t *v33; // [rsp+C0h] [rbp-40h]
  int v34; // [rsp+C8h] [rbp-38h]
  int v35; // [rsp+CCh] [rbp-34h]
  __int128 *v36; // [rsp+D0h] [rbp-30h]
  int v37; // [rsp+D8h] [rbp-28h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  v19 = 0;
  v24 = 0;
  v26 = 0;
  nSize = 0;
  ppObject = 0;
  v4 = 0;
  pMem = 0;
  v27[1] = L"serviceBindingInformation";
  v27[0] = L"serviceDNSName";
  v28 = L"serviceDNSName";
  v29 = 2;
  v33 = L"serviceBindingInformation";
  v31 = &v23;
  v34 = 2;
  v36 = &v25;
  v30 = 3;
  v23 = 0;
  v5 = 0;
  v32 = 1;
  v25 = 0;
  v35 = 3;
  v37 = 1;
  v6 = CoInitializeEx(0, 0);
  if ( v6 < 0 )
    goto LABEL_29;
  v4 = 1;
  if ( (unsigned int)IsCurrentLocalSystem() )
  {
    v6 = ImpersonateLocalSystem(v8, v7);
    if ( v6 )
      goto LABEL_29;
    v5 = 1;
  }
  nSize = 260;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) )
  {
    v6 = GetLastError() | 0x10000000;
    goto LABEL_29;
  }
  Object = ADsGetObject(lpszPathName, &IID_IDirectoryObject, &ppObject);
  v6 = Object;
  if ( Object < 0 )
  {
    TRACELogPrint(65538, "ADsGetObject failed to bind to GUID (bind string: %S): hr=%x", lpszPathName, Object);
    goto LABEL_29;
  }
  v10 = (*(__int64 (__fastcall **)(void *, _QWORD *, __int64, LPVOID *, int *))(*(_QWORD *)ppObject + 32LL))(
          ppObject,
          v27,
          2,
          &pMem,
          &v19);
  v6 = v10;
  if ( v10 < 0 )
  {
    TRACELogPrint(65538, "GetObjectAttributes failed, hr=%x", (unsigned int)v10);
    goto LABEL_29;
  }
  v11 = *((_DWORD *)pMem + 3);
  if ( v11 != 3 || *((_DWORD *)pMem + 11) != 3 )
  {
    TRACELogPrint(
      65538,
      "GetObjectAttributes returned dwADsType (%d,%d) instead of CASE_IGNORE_STRING",
      v11,
      *((_DWORD *)pMem + 11));
    v6 = -2147467259;
    goto LABEL_29;
  }
  v12 = 0;
  v13 = 0;
  if ( v19 <= 0 )
    goto LABEL_29;
  do
  {
    v14 = 32LL * v13;
    if ( (unsigned int)_o__wcsicmp(L"serviceDNSName", *(_QWORD *)((char *)pMem + v14)) )
    {
      if ( (unsigned int)_o__wcsicmp(L"serviceBindingInformation", *(_QWORD *)((char *)pMem + v14)) )
        goto LABEL_24;
      if ( (unsigned int)_o__wcsicmp(a2, *(_QWORD *)(*(_QWORD *)((char *)pMem + v14 + 16) + 8LL)) )
      {
        TRACELogPrint(524290, "serviceBindingInformation being updated");
        v12 = 1;
        goto LABEL_24;
      }
      v16 = "serviceBindingInformation okay";
    }
    else
    {
      v15 = _o__wcsicmp(Buffer, *(_QWORD *)(*(_QWORD *)((char *)pMem + v14 + 16) + 8LL));
      v16 = "serviceDNSName being updated";
      if ( !v15 )
      {
        TRACELogPrint(524290, "serviceDNSName okay");
        goto LABEL_24;
      }
      v12 = 1;
    }
    TRACELogPrint(524290, v16);
LABEL_24:
    ++v13;
  }
  while ( v13 < v19 );
  if ( v12 )
  {
    *((_QWORD *)&v25 + 1) = a2;
    LODWORD(v23) = 3;
    LODWORD(v25) = 3;
    *((_QWORD *)&v23 + 1) = Buffer;
    v17 = (*(__int64 (__fastcall **)(void *, const wchar_t **, __int64, int *))(*(_QWORD *)ppObject + 40LL))(
            ppObject,
            &v28,
            2,
            &v19);
    v6 = v17;
    if ( v17 < 0 )
      TRACELogPrint(65538, "ScpUpdate: Failed to set SCP values. 0x%x", (unsigned int)v17);
  }
LABEL_29:
  if ( pMem )
    FreeADsMem(pMem);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( v5 )
    RevertLocalSystemImp();
  if ( v4 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003bcc8  mov     [rsp-8+arg_10], rbx
0x18003bccd  push    rbp
0x18003bcce  push    rsi
0x18003bccf  push    rdi
0x18003bcd0  push    r12
0x18003bcd2  push    r13
0x18003bcd4  push    r14
0x18003bcd6  push    r15
0x18003bcd8  lea     rbp, [rsp-200h]
0x18003bce0  sub     rsp, 300h
0x18003bce7  mov     rax, cs:__security_cookie
0x18003bcee  xor     rax, rsp
0x18003bcf1  mov     [rbp+230h+var_40], rax
0x18003bcf8  xor     eax, eax
0x18003bcfa  mov     [rsp+330h+var_300], 0
0x18003bd02  mov     [rsp+330h+var_2C8], rax
0x18003bd07  mov     r13, rdx
0x18003bd0a  mov     [rbp+230h+var_2B0], rax
0x18003bd0e  lea     rdx, aServicebinding_0; "serviceBindingInformation"
0x18003bd15  mov     [rsp+330h+nSize], eax
0x18003bd19  mov     rdi, rcx
0x18003bd1c  mov     [rsp+330h+ppObject], rax
0x18003bd21  xor     r12d, r12d
0x18003bd24  mov     [rsp+330h+pMem], rax
0x18003bd29  xorps   xmm0, xmm0
0x18003bd2c  lea     rax, aServicednsname_2; "serviceDNSName"
0x18003bd33  mov     [rbp+230h+var_2A0], rdx
0x18003bd37  mov     [rbp+230h+var_2A8], rax
0x18003bd3b  xorps   xmm1, xmm1
0x18003bd3e  lea     ecx, [r12+2]
0x18003bd43  mov     [rbp+230h+var_290], rax
0x18003bd47  lea     esi, [rcx-1]
0x18003bd4a  mov     [rbp+230h+var_288], ecx
0x18003bd4d  lea     rax, [rsp+330h+var_2D8]
0x18003bd52  mov     [rbp+230h+var_270], rdx
0x18003bd56  mov     [rbp+230h+var_280], rax
0x18003bd5a  lea     r14d, [r12+3]
0x18003bd5f  lea     rax, [rsp+330h+var_2C0]
0x18003bd64  mov     [rbp+230h+var_268], ecx
0x18003bd67  xor     edx, edx; dwCoInit
0x18003bd69  mov     [rbp+230h+var_260], rax
0x18003bd6d  xor     ecx, ecx; pvReserved
0x18003bd6f  mov     [rbp+230h+var_284], r14d
0x18003bd73  movups  [rsp+330h+var_2D8], xmm0
0x18003bd78  xor     r15d, r15d
0x18003bd7b  mov     [rbp+230h+var_278], esi
0x18003bd7e  movups  [rsp+330h+var_2C0], xmm1
0x18003bd83  mov     [rbp+230h+var_264], r14d
0x18003bd87  mov     [rbp+230h+var_258], esi
0x18003bd8a  call    cs:__imp_CoInitializeEx
0x18003bd90  mov     ebx, eax
0x18003bd92  test    eax, eax
0x18003bd94  js      loc_18003BFBF
0x18003bd9a  mov     r12d, esi
0x18003bd9d  call    ?IsCurrentLocalSystem@@YAJXZ; IsCurrentLocalSystem(void)
0x18003bda2  test    eax, eax
0x18003bda4  jz      short loc_18003BDB8
0x18003bda6  call    ?ImpersonateLocalSystem@@YAJXZ; ImpersonateLocalSystem(void)
0x18003bdab  mov     ebx, eax
0x18003bdad  test    eax, eax
0x18003bdaf  jnz     loc_18003BFBF
0x18003bdb5  mov     r15d, esi
0x18003bdb8  lea     r8, [rsp+330h+nSize]; nSize
0x18003bdbd  mov     [rsp+330h+nSize], 104h
0x18003bdc5  lea     rdx, [rbp+230h+Buffer]; lpBuffer
0x18003bdc9  mov     ecx, r14d; NameType
0x18003bdcc  call    cs:__imp_GetComputerNameExW
0x18003bdd2  test    eax, eax
0x18003bdd4  jnz     short loc_18003BDE7
0x18003bdd6  call    cs:__imp_GetLastError
0x18003bddc  mov     ebx, eax
0x18003bdde  bts     ebx, 1Ch
0x18003bde2  jmp     loc_18003BFBF
0x18003bde7  lea     r8, [rsp+330h+ppObject]; ppObject
0x18003bdec  mov     rcx, rdi; lpszPathName
0x18003bdef  lea     rdx, IID_IDirectoryObject; riid
0x18003bdf6  call    cs:__imp_ADsGetObject
0x18003bdfc  mov     ebx, eax
0x18003bdfe  test    eax, eax
0x18003be00  jns     short loc_18003BE1E
0x18003be02  mov     r9d, eax
0x18003be05  lea     rdx, aAdsgetobjectFa; "ADsGetObject failed to bind to GUID (bi"...
0x18003be0c  mov     r8, rdi
0x18003be0f  mov     ecx, 10002h
0x18003be14  call    TRACELogPrint
0x18003be19  jmp     loc_18003BFBF
0x18003be1e  mov     rcx, [rsp+330h+ppObject]
0x18003be23  lea     rdx, [rsp+330h+var_300]
0x18003be28  mov     [rsp+330h+var_310], rdx
0x18003be2d  lea     r9, [rsp+330h+pMem]
0x18003be32  mov     r8d, 2
0x18003be38  lea     rdx, [rbp+230h+var_2A8]
0x18003be3c  mov     rax, [rcx]
0x18003be3f  mov     rax, [rax+20h]
0x18003be43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be48  mov     ebx, eax
0x18003be4a  test    eax, eax
0x18003be4c  jns     short loc_18003BE67
0x18003be4e  lea     rdx, aGetobjectattri; "GetObjectAttributes failed, hr=%x"
0x18003be55  mov     r8d, eax
0x18003be58  mov     ecx, 10002h
0x18003be5d  call    TRACELogPrint
0x18003be62  jmp     loc_18003BFBF
0x18003be67  mov     rcx, [rsp+330h+pMem]
0x18003be6c  mov     r8d, [rcx+0Ch]
0x18003be70  cmp     r8d, r14d
0x18003be73  jnz     loc_18003BFA0
0x18003be79  cmp     [rcx+2Ch], r14d
0x18003be7d  jnz     loc_18003BFA0
0x18003be83  xor     r14d, r14d
0x18003be86  xor     esi, esi
0x18003be88  cmp     [rsp+330h+var_300], esi
0x18003be8c  jle     loc_18003BFBF
0x18003be92  mov     rdx, [rsp+330h+pMem]
0x18003be97  lea     rcx, aServicednsname_2; "serviceDNSName"
0x18003be9e  movsxd  rdi, esi
0x18003bea1  shl     rdi, 5
0x18003bea5  mov     rdx, [rdi+rdx]
0x18003bea9  call    cs:__imp__o__wcsicmp
0x18003beaf  test    eax, eax
0x18003beb1  jnz     short loc_18003BEE5
0x18003beb3  mov     rax, [rsp+330h+pMem]
0x18003beb8  lea     rcx, [rbp+230h+Buffer]
0x18003bebc  mov     rdx, [rdi+rax+10h]
0x18003bec1  mov     rdx, [rdx+8]
0x18003bec5  call    cs:__imp__o__wcsicmp
0x18003becb  test    eax, eax
0x18003becd  lea     rcx, aServicednsname; "serviceDNSName okay"
0x18003bed4  lea     rdx, aServicednsname_1; "serviceDNSName being updated"
0x18003bedb  cmovnz  r14d, r12d
0x18003bedf  cmovz   rdx, rcx
0x18003bee3  jmp     short loc_18003BF37
0x18003bee5  mov     rdx, [rsp+330h+pMem]
0x18003beea  lea     rcx, aServicebinding_0; "serviceBindingInformation"
0x18003bef1  mov     rdx, [rdi+rdx]
0x18003bef5  call    cs:__imp__o__wcsicmp
0x18003befb  test    eax, eax
0x18003befd  jnz     short loc_18003BF41
0x18003beff  mov     rax, [rsp+330h+pMem]
0x18003bf04  mov     rcx, r13
0x18003bf07  mov     rdx, [rdi+rax+10h]
0x18003bf0c  mov     rdx, [rdx+8]
0x18003bf10  call    cs:__imp__o__wcsicmp
0x18003bf16  test    eax, eax
0x18003bf18  jz      short loc_18003BF30
0x18003bf1a  lea     rdx, aServicebinding; "serviceBindingInformation being updated"
0x18003bf21  mov     ecx, 80002h
0x18003bf26  call    TRACELogPrint
0x18003bf2b  mov     r14d, r12d
0x18003bf2e  jmp     short loc_18003BF41
0x18003bf30  lea     rdx, aServicebinding_1; "serviceBindingInformation okay"
0x18003bf37  mov     ecx, 80002h
0x18003bf3c  call    TRACELogPrint
0x18003bf41  add     esi, r12d
0x18003bf44  cmp     esi, [rsp+330h+var_300]
0x18003bf48  jl      loc_18003BE92
0x18003bf4e  test    r14d, r14d
0x18003bf51  jz      short loc_18003BFBF
0x18003bf53  mov     ecx, 3
0x18003bf58  mov     qword ptr [rsp+330h+var_2C0+8], r13
0x18003bf5d  mov     dword ptr [rsp+330h+var_2D8], ecx
0x18003bf61  lea     rax, [rbp+230h+Buffer]
0x18003bf65  mov     dword ptr [rsp+330h+var_2C0], ecx
0x18003bf69  lea     r9, [rsp+330h+var_300]
0x18003bf6e  mov     rcx, [rsp+330h+ppObject]
0x18003bf73  lea     rdx, [rbp+230h+var_290]
0x18003bf77  mov     qword ptr [rsp+330h+var_2D8+8], rax
0x18003bf7c  mov     r8d, 2
0x18003bf82  mov     rax, [rcx]
0x18003bf85  mov     rax, [rax+28h]
0x18003bf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf8e  mov     ebx, eax
0x18003bf90  test    eax, eax
0x18003bf92  jns     short loc_18003BFBF
0x18003bf94  lea     rdx, aScpupdateFaile; "ScpUpdate: Failed to set SCP values. 0x"...
0x18003bf9b  jmp     loc_18003BE55
0x18003bfa0  mov     r9, [rsp+330h+pMem]
0x18003bfa5  lea     rdx, aGetobjectattri_0; "GetObjectAttributes returned dwADsType "...
0x18003bfac  mov     ecx, 10002h
0x18003bfb1  mov     r9d, [r9+2Ch]
0x18003bfb5  call    TRACELogPrint
0x18003bfba  mov     ebx, 80004005h
0x18003bfbf  mov     rcx, [rsp+330h+pMem]; pMem
0x18003bfc4  test    rcx, rcx
0x18003bfc7  jz      short loc_18003BFCF
0x18003bfc9  call    cs:__imp_FreeADsMem
0x18003bfcf  mov     rcx, [rsp+330h+ppObject]
0x18003bfd4  test    rcx, rcx
0x18003bfd7  jz      short loc_18003BFE5
0x18003bfd9  mov     rax, [rcx]
0x18003bfdc  mov     rax, [rax+10h]
0x18003bfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfe5  test    r15d, r15d
0x18003bfe8  jz      short loc_18003BFEF
0x18003bfea  call    ?RevertLocalSystemImp@@YAJXZ; RevertLocalSystemImp(void)
0x18003bfef  test    r12d, r12d
0x18003bff2  jz      short loc_18003BFFA
0x18003bff4  call    cs:__imp_CoUninitialize
0x18003bffa  mov     eax, ebx
0x18003bffc  mov     rcx, [rbp+230h+var_40]
0x18003c003  xor     rcx, rsp; StackCookie
0x18003c006  call    __security_check_cookie
0x18003c00b  mov     rbx, [rsp+330h+arg_10]
0x18003c013  add     rsp, 300h
0x18003c01a  pop     r15
0x18003c01c  pop     r14
0x18003c01e  pop     r13
0x18003c020  pop     r12
0x18003c022  pop     rdi
0x18003c023  pop     rsi
0x18003c024  pop     rbp
0x18003c025  retn
```
