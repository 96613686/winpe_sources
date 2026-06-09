# RunDLL_InitActCtx(ushort const *,unsigned __int64 *,int)

- ea: `0x140007b40`
- end: `0x140007d9f`
- name: `?RunDLL_InitActCtx@@YAPEAXPEBGPEA_KH@Z`
- size: `607`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, ULONG_PTR *lpCookie)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x140007798`

## callees

- `0x1400015a0`
- `0x140001b90`
- `0x140006204`
- `0x140007b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007d5e`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140007bb7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x140007bb7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140007c20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140007c20`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140007d8b`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x140007d8b`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c30`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c71`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c91`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007cb1`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007d75`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c30`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c71`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007c91`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007cb1`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x140007d75`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x140007b78`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x140007b78`
- `ntdll!RtlSetSearchPathMode` at `0x140007b8b`
- `ntdll!RtlSetSearchPathMode` at `0x140007b8b`

## string_xrefs

- `0x140007c08`: `.manifest`

## pseudocode

```c
__int64 __fastcall RunDLL_InitActCtx(LPCWSTR lpFileName, ULONG_PTR *lpCookie)
{
  const WCHAR *v3; // rbx
  unsigned __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // rdi
  HANDLE v7; // rax
  void *v8; // rcx
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  HMODULE ModuleHandleW; // rax
  ACTCTXW pActCtx; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR FilePart; // [rsp+68h] [rbp-98h] BYREF
  ACTCTXW v16; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  *lpCookie = 0;
  v3 = lpFileName;
  if ( PathIsRelativeW(lpFileName) )
  {
    RtlSetSearchPathMode(32769);
    FilePart = 0;
    if ( SearchPathW(0, v3, 0, 0x104u, Buffer, &FilePart) )
      goto LABEL_3;
    return 0;
  }
  v9 = 2147483646;
  v10 = Buffer;
  v4 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*v3 )
      break;
    *v10++ = *v3++;
    --v9;
    --v4;
  }
  while ( v4 );
  v11 = v10 - 1;
  if ( v4 )
    v11 = v10;
  *v11 = 0;
  if ( !v4 )
    return 0;
LABEL_3:
  v5 = -1;
  v6 = -1;
  pActCtx.lpSource = Buffer;
  memset(&pActCtx.wProcessorArchitecture, 0, 40);
  *(_QWORD *)&pActCtx.cbSize = 56;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( (int)StringCchCatW(Buffer, v4, L".manifest") >= 0 && GetFileAttributesW(Buffer) != -1 )
    v5 = (__int64)CreateActCtxW(&pActCtx);
  if ( (unsigned __int64)(2LL * (int)v6) >= 0x208 )
    _report_rangecheckfailure();
  Buffer[(int)v6] = 0;
  if ( v5 == -1
    && (pActCtx.dwFlags = 8, pActCtx.lpResourceName = (LPCWSTR)123, v5 = (__int64)CreateActCtxW(&pActCtx), v5 == -1) )
  {
    pActCtx.lpResourceName = (LPCWSTR)124;
    v5 = (__int64)CreateActCtxW(&pActCtx);
    if ( v5 != -1 )
      return v5;
    pActCtx.lpResourceName = (LPCWSTR)2;
    v7 = CreateActCtxW(&pActCtx);
    v5 = (__int64)v7;
    if ( v7 == (HANDLE)-1LL )
    {
      memset(&v16, 0, 32);
      v16.dwFlags = 136;
      v16.lpApplicationName = 0;
      v16.lpResourceName = (LPCWSTR)7;
      v16.hModule = 0;
      ModuleHandleW = GetModuleHandleW(0);
      v16.cbSize = 56;
      v16.hModule = ModuleHandleW;
      v7 = CreateActCtxW(&v16);
      if ( v7 == (HANDLE)-1LL )
        return v5;
    }
    v8 = v7;
  }
  else
  {
    v8 = (void *)v5;
  }
  ActivateActCtx(v8, lpCookie);
  return v5;
}

```

## disassembly

```asm
0x140007b40  mov     [rsp-8+arg_10], rbx
0x140007b45  push    rbp
0x140007b46  push    rsi
0x140007b47  push    rdi
0x140007b48  push    r14
0x140007b4a  push    r15
0x140007b4c  lea     rbp, [rsp-1D0h]
0x140007b54  sub     rsp, 2D0h
0x140007b5b  mov     rax, cs:__security_cookie
0x140007b62  xor     rax, rsp
0x140007b65  mov     [rbp+1F0h+var_30], rax
0x140007b6c  xor     r14d, r14d
0x140007b6f  mov     rsi, rdx
0x140007b72  mov     [rdx], r14
0x140007b75  mov     rbx, rcx
0x140007b78  call    cs:__imp_PathIsRelativeW
0x140007b7e  test    eax, eax
0x140007b80  jz      loc_140007CC7
0x140007b86  mov     ecx, 8001h
0x140007b8b  call    cs:__imp_RtlSetSearchPathMode
0x140007b91  lea     rax, [rsp+2F0h+FilePart]
0x140007b96  mov     [rsp+2F0h+FilePart], r14
0x140007b9b  mov     [rsp+2F0h+lpFilePart], rax; lpFilePart
0x140007ba0  mov     r9d, 104h; nBufferLength
0x140007ba6  lea     rax, [rbp+1F0h+Buffer]
0x140007baa  xor     r8d, r8d; lpExtension
0x140007bad  mov     rdx, rbx; lpFileName
0x140007bb0  mov     [rsp+2F0h+lpBuffer], rax; lpBuffer
0x140007bb5  xor     ecx, ecx; lpPath
0x140007bb7  call    cs:__imp_SearchPathW
0x140007bbd  test    eax, eax
0x140007bbf  jz      loc_140007D0E
0x140007bc5  or      r15, 0FFFFFFFFFFFFFFFFh
0x140007bc9  xorps   xmm0, xmm0
0x140007bcc  xor     eax, eax
0x140007bce  mov     rbx, r15
0x140007bd1  mov     [rsp+2F0h+pActCtx.hModule], rax
0x140007bd6  mov     rdi, r15
0x140007bd9  lea     rax, [rbp+1F0h+Buffer]
0x140007bdd  movups  xmmword ptr [rsp+2F0h+pActCtx.cbSize], xmm0
0x140007be2  mov     [rsp+2F0h+pActCtx.lpSource], rax
0x140007be7  lea     rax, [rbp+1F0h+Buffer]
0x140007beb  movups  xmmword ptr [rsp+2F0h+pActCtx.wProcessorArchitecture], xmm0
0x140007bf0  mov     qword ptr [rsp+2F0h+pActCtx.cbSize], 38h ; '8'
0x140007bf9  movups  xmmword ptr [rsp+2F0h+pActCtx.lpResourceName], xmm0
0x140007bfe  inc     rdi
0x140007c01  cmp     [rax+rdi*2], r14w
0x140007c06  jnz     short loc_140007BFE
0x140007c08  lea     r8, aManifest; ".manifest"
0x140007c0f  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x140007c13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007c18  test    eax, eax
0x140007c1a  js      short loc_140007C39
0x140007c1c  lea     rcx, [rbp+1F0h+Buffer]; lpFileName
0x140007c20  call    cs:__imp_GetFileAttributesW
0x140007c26  cmp     eax, 0FFFFFFFFh
0x140007c29  jz      short loc_140007C39
0x140007c2b  lea     rcx, [rsp+2F0h+pActCtx]; pActCtx
0x140007c30  call    cs:__imp_CreateActCtxW
0x140007c36  mov     rbx, rax
0x140007c39  movsxd  rcx, edi
0x140007c3c  lea     rax, [rcx+rcx]
0x140007c40  cmp     rax, 208h
0x140007c46  jnb     loc_140007D99
0x140007c4c  mov     [rbp+rax+1F0h+Buffer], r14w
0x140007c52  cmp     rbx, r15
0x140007c55  jnz     loc_140007D85
0x140007c5b  lea     rcx, [rsp+2F0h+pActCtx]; pActCtx
0x140007c60  mov     [rsp+2F0h+pActCtx.dwFlags], 8
0x140007c68  mov     [rsp+2F0h+pActCtx.lpResourceName], 7Bh ; '{'
0x140007c71  call    cs:__imp_CreateActCtxW
0x140007c77  mov     rbx, rax
0x140007c7a  cmp     rax, r15
0x140007c7d  jnz     loc_140007D85
0x140007c83  lea     rcx, [rsp+2F0h+pActCtx]; pActCtx
0x140007c88  mov     [rsp+2F0h+pActCtx.lpResourceName], 7Ch ; '|'
0x140007c91  call    cs:__imp_CreateActCtxW
0x140007c97  mov     rbx, rax
0x140007c9a  cmp     rax, r15
0x140007c9d  jnz     loc_140007D91
0x140007ca3  lea     rcx, [rsp+2F0h+pActCtx]; pActCtx
0x140007ca8  mov     [rsp+2F0h+pActCtx.lpResourceName], 2
0x140007cb1  call    cs:__imp_CreateActCtxW
0x140007cb7  mov     rbx, rax
0x140007cba  cmp     rax, r15
0x140007cbd  jz      short loc_140007D36
0x140007cbf  mov     rcx, rax
0x140007cc2  jmp     loc_140007D88
0x140007cc7  mov     ecx, 7FFFFFFEh
0x140007ccc  lea     rax, [rbp+1F0h+Buffer]
0x140007cd0  mov     edx, 104h
0x140007cd5  test    rcx, rcx
0x140007cd8  jz      short loc_140007CF9
0x140007cda  movzx   r8d, word ptr [rbx]
0x140007cde  test    r8w, r8w
0x140007ce2  jz      short loc_140007CF9
0x140007ce4  mov     [rax], r8w
0x140007ce8  add     rbx, 2
0x140007cec  add     rax, 2
0x140007cf0  dec     rcx
0x140007cf3  sub     rdx, 1
0x140007cf7  jnz     short loc_140007CD5
0x140007cf9  test    rdx, rdx
0x140007cfc  lea     rcx, [rax-2]
0x140007d00  cmovnz  rcx, rax
0x140007d04  mov     [rcx], r14w
0x140007d08  jnz     loc_140007BC5
0x140007d0e  xor     eax, eax
0x140007d10  mov     rcx, [rbp+1F0h+var_30]
0x140007d17  xor     rcx, rsp; StackCookie
0x140007d1a  call    __security_check_cookie
0x140007d1f  mov     rbx, [rsp+2F0h+arg_10]
0x140007d27  add     rsp, 2D0h
0x140007d2e  pop     r15
0x140007d30  pop     r14
0x140007d32  pop     rdi
0x140007d33  pop     rsi
0x140007d34  pop     rbp
0x140007d35  retn
0x140007d36  xorps   xmm0, xmm0
0x140007d39  xor     eax, eax
0x140007d3b  movups  xmmword ptr [rsp+2F0h+var_280.cbSize], xmm0
0x140007d40  xor     ecx, ecx; lpModuleName
0x140007d42  mov     [rsp+2F0h+var_280.dwFlags], 88h
0x140007d4a  movups  xmmword ptr [rbp+1F0h+var_280.lpResourceName], xmm0
0x140007d4e  mov     [rbp+1F0h+var_280.lpResourceName], 7
0x140007d56  movups  xmmword ptr [rbp+1F0h+var_280.wProcessorArchitecture], xmm0
0x140007d5a  mov     [rbp+1F0h+var_280.hModule], rax
0x140007d5e  call    cs:__imp_GetModuleHandleW
0x140007d64  lea     rcx, [rsp+2F0h+var_280]; pActCtx
0x140007d69  mov     [rsp+2F0h+var_280.cbSize], 38h ; '8'
0x140007d71  mov     [rbp+1F0h+var_280.hModule], rax
0x140007d75  call    cs:__imp_CreateActCtxW
0x140007d7b  cmp     rax, r15
0x140007d7e  jz      short loc_140007D91
0x140007d80  jmp     loc_140007CBF
0x140007d85  mov     rcx, rbx; hActCtx
0x140007d88  mov     rdx, rsi; lpCookie
0x140007d8b  call    cs:__imp_ActivateActCtx
0x140007d91  mov     rax, rbx
0x140007d94  jmp     loc_140007D10
0x140007d99  call    __report_rangecheckfailure
```
