# GetIndexedDBFilePath(ulong,bool,ushort * *,ushort * *)

- ea: `0x180009b00`
- end: `0x180009f5b`
- name: `?GetIndexedDBFilePath@@YAJK_NPEAPEAG1@Z`
- size: `1115`
- prototype: `__int64 __fastcall(unsigned int, bool, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x1800081b4`
- `0x1800086cc`
- `0x180009390`
- `0x1800a7180`

## callees

- `0x1800086ac`
- `0x180009b00`
- `0x180009f64`
- `0x18000a094`
- `0x180027550`
- `0x18004448c`
- `0x180073dc4`
- `0x180080f94`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009b8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009bab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009bab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e33`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180009eed`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180009eed`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180009ed5`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180009ed5`
- `RPCRT4!RpcRevertToSelf` at `0x180009bc1`
- `RPCRT4!RpcRevertToSelf` at `0x180009bc1`
- `RPCRT4!RpcImpersonateClient` at `0x180009b7b`
- `RPCRT4!RpcImpersonateClient` at `0x180009b7b`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180009bda`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180009bda`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180009c7a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180009c7a`
- `api-ms-win-appmodel-state-l1-2-0!GetAppDataFolder` at `0x180009c00`
- `api-ms-win-appmodel-state-l1-2-0!GetAppDataFolder` at `0x180009c4a`
- `api-ms-win-appmodel-state-l1-2-0!GetAppDataFolder` at `0x180009c00`
- `api-ms-win-appmodel-state-l1-2-0!GetAppDataFolder` at `0x180009c4a`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180009ea8`
- `iertutil!__imp_GetBrowserProfileDataFilePath` at `0x180009ea8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetIndexedDBFilePath(unsigned int a1, bool a2, unsigned __int16 **a3, unsigned __int16 **a4)
{
  void *v4; // rdi
  unsigned __int16 **v6; // r15
  unsigned __int16 *v9; // r12
  unsigned __int16 *v10; // rsi
  signed int PackageFamilyNameForPackage; // ebx
  RPC_STATUS v12; // eax
  HANDLE CurrentThread; // rax
  void *v14; // r14
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int16 *v17; // r15
  signed int v18; // eax
  const wchar_t *v19; // rdi
  __int64 v20; // rax
  __int64 v22; // rcx
  unsigned int v23; // r14d
  unsigned __int16 *v24; // rdi
  HRESULT BrowserProfileDataFilePath; // ebx
  unsigned __int16 *v26; // rcx
  signed int v28; // eax
  signed int LastError; // eax
  signed int v30; // eax
  __int64 v31; // rdx
  __int64 (**v32)[2]; // rax
  __int64 *v33; // rbx
  const unsigned __int16 *v34; // rsi
  unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // rdx
  void *Block; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 *v38; // [rsp+38h] [rbp-50h]
  unsigned int v39; // [rsp+90h] [rbp+8h] BYREF
  bool v40; // [rsp+98h] [rbp+10h]
  unsigned __int16 **v41; // [rsp+A0h] [rbp+18h]
  void *TokenHandle; // [rsp+A8h] [rbp+20h] BYREF

  v41 = a3;
  v40 = a2;
  v4 = 0;
  *a3 = 0;
  v6 = a3;
  *a4 = 0;
  if ( (a1 & 0x40) == 0 )
  {
    if ( (a1 & 0x10) == 0 )
    {
      v31 = 2LL * GetIndexFromContextFlags(a1);
      v32 = &off_180111D00;
      if ( (a1 & 8) == 0 )
        v32 = &off_180111C80;
      v33 = (__int64 *)v32[v31];
      v34 = (const unsigned __int16 *)operator new(0x208u);
      *v34 = 0;
      v35 = (unsigned __int16 *)operator new(0x208u);
      *v35 = 0;
      BrowserProfileDataFilePath = GetBrowserProfileDataFilePath(v33, 16, v34, 260);
      if ( BrowserProfileDataFilePath >= 0 )
      {
        BrowserProfileDataFilePath = StringCchCopyW(v35, v36, v34);
        if ( BrowserProfileDataFilePath >= 0 )
        {
          BrowserProfileDataFilePath = PathCchRemoveFileSpec(v35, 0x104u);
          if ( BrowserProfileDataFilePath >= 0 )
          {
            BrowserProfileDataFilePath = PathCchAddBackslash(v35, 0x104u);
            if ( BrowserProfileDataFilePath >= 0 )
            {
              if ( !a2
                || !*v35
                || (BrowserProfileDataFilePath = CreateAndEncryptDirectoryAsNeeded(v35, a1),
                    BrowserProfileDataFilePath >= 0) )
              {
                *a4 = (unsigned __int16 *)v34;
                *v6 = v35;
              }
            }
          }
        }
      }
      return (unsigned int)BrowserProfileDataFilePath;
    }
    v9 = 0;
    v38 = 0;
    v10 = 0;
    Block = 0;
    PackageFamilyNameForPackage = GetPackageFamilyNameForPackage((unsigned __int16 **)&Block);
    if ( PackageFamilyNameForPackage >= 0 )
    {
      TokenHandle = (void *)-1LL;
      v12 = RpcImpersonateClient(0);
      PackageFamilyNameForPackage = v12;
      if ( v12 > 0 )
        PackageFamilyNameForPackage = (unsigned __int16)v12 | 0x80070000;
      if ( PackageFamilyNameForPackage >= 0 )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
        {
          v4 = TokenHandle;
        }
        else
        {
          LastError = GetLastError();
          PackageFamilyNameForPackage = LastError;
          if ( LastError > 0 )
            PackageFamilyNameForPackage = (unsigned __int16)LastError | 0x80070000;
        }
        RpcRevertToSelf();
      }
      v14 = Block;
      if ( PackageFamilyNameForPackage >= 0 )
      {
        v15 = OpenStateExplicit(v4, Block);
        v16 = v15;
        if ( v15 )
        {
          v39 = 0;
          GetAppDataFolder(v15, 0, &v39);
          if ( GetLastError() == 122 )
          {
            v17 = (unsigned __int16 *)operator new(saturated_mul(v39, 2u));
            PackageFamilyNameForPackage = 0;
            if ( (unsigned int)GetAppDataFolder(v16, v17, &v39) )
              goto LABEL_17;
            v18 = GetLastError();
            PackageFamilyNameForPackage = v18;
            if ( v18 > 0 )
              PackageFamilyNameForPackage = (unsigned __int16)v18 | 0x80070000;
            if ( PackageFamilyNameForPackage >= 0 )
            {
LABEL_17:
              v10 = v17;
              v6 = v41;
            }
            else
            {
              operator delete(v17);
              v6 = v41;
            }
          }
          else
          {
            v28 = GetLastError();
            PackageFamilyNameForPackage = v28;
            if ( v28 > 0 )
              PackageFamilyNameForPackage = (unsigned __int16)v28 | 0x80070000;
          }
          CloseState(v16);
        }
        else
        {
          v30 = GetLastError();
          PackageFamilyNameForPackage = v30;
          if ( v30 > 0 )
            PackageFamilyNameForPackage = (unsigned __int16)v30 | 0x80070000;
        }
      }
      operator delete(v14);
    }
    if ( PackageFamilyNameForPackage < 0 )
    {
      v24 = 0;
    }
    else
    {
      v19 = L"Indexed DB\\EDP\\";
      if ( (a1 & 2) == 0 )
        v19 = L"Indexed DB\\";
      v20 = -1;
      while ( v10[++v20] != 0 )
        ;
      v22 = -1;
      do
        ++v22;
      while ( v19[v22] );
      v23 = v22 + v20 + 2;
      v9 = (unsigned __int16 *)operator new(saturated_mul(v23, 2u));
      if ( (int)StringCchPrintfW(v9, v23, L"%s\\%s", v10, v19) < 0 )
      {
        v24 = v38;
      }
      else
      {
        v24 = (unsigned __int16 *)operator new(saturated_mul(v23 + 14, 2u));
        BrowserProfileDataFilePath = StringCchPrintfW(v24, v23 + 14, L"%s%s", v9, L"IndexedDB.edb");
        if ( BrowserProfileDataFilePath >= 0 )
        {
          if ( !v40
            || (BrowserProfileDataFilePath = CreateAndEncryptDirectoryAsNeeded(v9, a1), BrowserProfileDataFilePath >= 0) )
          {
            *a4 = v24;
            v26 = v10;
            *v6 = v9;
            goto LABEL_31;
          }
        }
      }
      operator delete(v10);
    }
    BrowserProfileDataFilePath = -2147024891;
    if ( v9 )
      operator delete(v9);
    if ( !v24 )
      return (unsigned int)BrowserProfileDataFilePath;
    v26 = v24;
LABEL_31:
    operator delete(v26);
    return (unsigned int)BrowserProfileDataFilePath;
  }
  return GetSpartanIndexedDBFilePath(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_10], r8
0x180009b05  mov     [rsp+arg_8], dl
0x180009b09  push    rbx
0x180009b0a  push    rbp
0x180009b0b  push    rdi
0x180009b0c  push    r13
0x180009b0e  push    r14
0x180009b10  push    r15
0x180009b12  sub     rsp, 58h
0x180009b16  xor     edi, edi
0x180009b18  mov     r13, r9
0x180009b1b  mov     [r8], rdi
0x180009b1e  mov     r15, r8
0x180009b21  mov     [r9], rdi
0x180009b24  movzx   r14d, dl
0x180009b28  mov     ebp, ecx
0x180009b2a  test    cl, 40h
0x180009b2d  jnz     loc_180009E08
0x180009b33  mov     [rsp+88h+var_38], rsi
0x180009b38  test    bpl, 10h
0x180009b3c  jz      loc_180009E51
0x180009b42  mov     [rsp+88h+var_40], r12
0x180009b47  lea     rcx, [rsp+88h+Block]; unsigned __int16 **
0x180009b4c  mov     r12d, edi
0x180009b4f  mov     [rsp+88h+var_50], rdi
0x180009b54  mov     esi, edi
0x180009b56  mov     [rsp+88h+Block], rdi
0x180009b5b  call    ?GetPackageFamilyNameForPackage@@YAJPEAPEAG@Z; GetPackageFamilyNameForPackage(ushort * *)
0x180009b60  mov     ebx, eax
0x180009b62  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009b69  test    eax, eax
0x180009b6b  js      loc_180009C8F
0x180009b71  xor     ecx, ecx; BindingHandle
0x180009b73  mov     [rsp+88h+TokenHandle], r8
0x180009b7b  call    cs:__imp_RpcImpersonateClient
0x180009b81  mov     ebx, eax
0x180009b83  test    eax, eax
0x180009b85  jg      loc_180009F28
0x180009b8b  test    ebx, ebx
0x180009b8d  js      short loc_180009BC7
0x180009b8f  call    cs:__imp_GetCurrentThread
0x180009b95  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180009b9d  mov     edx, 0Eh; DesiredAccess
0x180009ba2  mov     rcx, rax; ThreadHandle
0x180009ba5  mov     r8d, 1; OpenAsSelf
0x180009bab  call    cs:__imp_OpenThreadToken
0x180009bb1  test    eax, eax
0x180009bb3  jz      loc_180009DEA
0x180009bb9  mov     rdi, [rsp+88h+TokenHandle]
0x180009bc1  call    cs:__imp_RpcRevertToSelf
0x180009bc7  mov     r14, [rsp+88h+Block]
0x180009bcc  test    ebx, ebx
0x180009bce  js      loc_180009C80
0x180009bd4  mov     rdx, r14
0x180009bd7  mov     rcx, rdi
0x180009bda  call    cs:__imp_OpenStateExplicit
0x180009be0  mov     rdi, rax
0x180009be3  test    rax, rax
0x180009be6  jz      loc_180009E33
0x180009bec  lea     r8, [rsp+88h+arg_0]
0x180009bf4  mov     [rsp+88h+arg_0], esi
0x180009bfb  xor     edx, edx
0x180009bfd  mov     rcx, rax
0x180009c00  call    cs:__imp_GetAppDataFolder
0x180009c06  call    cs:__imp_GetLastError
0x180009c0c  cmp     eax, 7Ah ; 'z'
0x180009c0f  jnz     loc_180009D9C
0x180009c15  mov     ecx, [rsp+88h+arg_0]
0x180009c1c  mov     eax, 2
0x180009c21  mul     rcx
0x180009c24  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009c2b  cmovb   rax, rcx
0x180009c2f  mov     rcx, rax; Size
0x180009c32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c37  lea     r8, [rsp+88h+arg_0]
0x180009c3f  mov     rdx, rax
0x180009c42  mov     rcx, rdi
0x180009c45  mov     r15, rax
0x180009c48  xor     ebx, ebx
0x180009c4a  call    cs:__imp_GetAppDataFolder
0x180009c50  test    eax, eax
0x180009c52  jnz     short loc_180009C6C
0x180009c54  call    cs:__imp_GetLastError
0x180009c5a  mov     ebx, eax
0x180009c5c  test    eax, eax
0x180009c5e  jg      loc_180009F36
0x180009c64  test    ebx, ebx
0x180009c66  js      loc_180009DBA
0x180009c6c  mov     rsi, r15
0x180009c6f  mov     r15, [rsp+88h+arg_10]
0x180009c77  mov     rcx, rdi
0x180009c7a  call    cs:__imp_CloseState
0x180009c80  mov     rcx, r14; Block
0x180009c83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009c88  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180009c8f  test    ebx, ebx
0x180009c91  js      loc_180009DCF
0x180009c97  lea     rax, aIndexedDb; "Indexed DB\\"
0x180009c9e  test    bpl, 2
0x180009ca2  lea     rdi, aIndexedDbEdp; "Indexed DB\\EDP\\"
0x180009ca9  cmovz   rdi, rax
0x180009cad  mov     rax, r8
0x180009cb0  cmp     [rsi+rax*2+2], r12w
0x180009cb6  lea     rax, [rax+1]
0x180009cba  jnz     short loc_180009CB0
0x180009cbc  mov     rcx, r8
0x180009cbf  nop
0x180009cc0  inc     rcx
0x180009cc3  cmp     [rdi+rcx*2], r12w
0x180009cc8  jnz     short loc_180009CC0
0x180009cca  lea     r14d, [rax+2]
0x180009cce  mov     eax, 2
0x180009cd3  add     r14d, ecx
0x180009cd6  mov     ebx, r14d
0x180009cd9  mul     rbx
0x180009cdc  cmovb   rax, r8
0x180009ce0  mov     rcx, rax; Size
0x180009ce3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ce8  mov     r9, rsi
0x180009ceb  mov     edx, r14d; unsigned __int64
0x180009cee  lea     r8, aSS; "%s\\%s"
0x180009cf5  mov     [rsp+88h+var_68], rdi
0x180009cfa  mov     rcx, rax; unsigned __int16 *
0x180009cfd  mov     r12, rax
0x180009d00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d05  mov     ebx, eax
0x180009d07  test    eax, eax
0x180009d09  js      loc_180009F44
0x180009d0f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009d16  lea     ebx, [r14+0Eh]
0x180009d1a  mov     eax, 2
0x180009d1f  mul     rbx
0x180009d22  cmovb   rax, rcx
0x180009d26  mov     rcx, rax; Size
0x180009d29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d2e  mov     rdi, rax
0x180009d31  lea     r8, aSS_0; "%s%s"
0x180009d38  lea     rax, aIndexeddbEdb; "IndexedDB.edb"
0x180009d3f  mov     rcx, rdi; unsigned __int16 *
0x180009d42  mov     r9, r12
0x180009d45  mov     [rsp+88h+var_68], rax
0x180009d4a  mov     edx, ebx; unsigned __int64
0x180009d4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d51  mov     ebx, eax
0x180009d53  test    eax, eax
0x180009d55  js      short loc_180009D76
0x180009d57  cmp     [rsp+88h+arg_8], 0
0x180009d5f  jnz     loc_180009E1A
0x180009d65  mov     [r13+0], rdi
0x180009d69  mov     rcx, rsi; Block
0x180009d6c  mov     [r15], r12
0x180009d6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d74  jmp     short loc_180009D82
0x180009d76  mov     rcx, rsi; Block
0x180009d79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d7e  test    ebx, ebx
0x180009d80  js      short loc_180009DD2
0x180009d82  mov     r12, [rsp+88h+var_40]
0x180009d87  mov     rsi, [rsp+88h+var_38]
0x180009d8c  mov     eax, ebx
0x180009d8e  add     rsp, 58h
0x180009d92  pop     r15
0x180009d94  pop     r14
0x180009d96  pop     r13
0x180009d98  pop     rdi
0x180009d99  pop     rbp
0x180009d9a  pop     rbx
0x180009d9b  retn
0x180009d9c  call    cs:__imp_GetLastError
0x180009da2  mov     ebx, eax
0x180009da4  test    eax, eax
0x180009da6  jle     loc_180009C77
0x180009dac  movzx   ebx, ax
0x180009daf  or      ebx, 80070000h
0x180009db5  jmp     loc_180009C77
0x180009dba  mov     rcx, r15; Block
0x180009dbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009dc2  mov     r15, [rsp+88h+arg_10]
0x180009dca  jmp     loc_180009C77
0x180009dcf  mov     rdi, r12
0x180009dd2  mov     ebx, 80070005h
0x180009dd7  test    r12, r12
0x180009dda  jnz     loc_180009F4E
0x180009de0  test    rdi, rdi
0x180009de3  jz      short loc_180009D82
0x180009de5  mov     rcx, rdi
0x180009de8  jmp     short loc_180009D6F
0x180009dea  call    cs:__imp_GetLastError
0x180009df0  mov     ebx, eax
0x180009df2  test    eax, eax
0x180009df4  jle     loc_180009BC1
0x180009dfa  movzx   ebx, ax
0x180009dfd  or      ebx, 80070000h
0x180009e03  jmp     loc_180009BC1
0x180009e08  add     rsp, 58h
0x180009e0c  pop     r15
0x180009e0e  pop     r14
0x180009e10  pop     r13
0x180009e12  pop     rdi
0x180009e13  pop     rbp
0x180009e14  pop     rbx
0x180009e15  jmp     ?GetSpartanIndexedDBFilePath@@YAJK_NPEAPEAG1@Z; GetSpartanIndexedDBFilePath(ulong,bool,ushort * *,ushort * *)
0x180009e1a  mov     edx, ebp; unsigned int
0x180009e1c  mov     rcx, r12; unsigned __int16 *
0x180009e1f  call    ?CreateAndEncryptDirectoryAsNeeded@@YAJPEBGK@Z; CreateAndEncryptDirectoryAsNeeded(ushort const *,ulong)
0x180009e24  mov     ebx, eax
0x180009e26  test    eax, eax
0x180009e28  jns     loc_180009D65
0x180009e2e  jmp     loc_180009D76
0x180009e33  call    cs:__imp_GetLastError
0x180009e39  mov     ebx, eax
0x180009e3b  test    eax, eax
0x180009e3d  jle     loc_180009C80
0x180009e43  movzx   ebx, ax
0x180009e46  or      ebx, 80070000h
0x180009e4c  jmp     loc_180009C80
0x180009e51  call    ?GetIndexFromContextFlags@@YAKK@Z; GetIndexFromContextFlags(ulong)
0x180009e56  mov     edx, eax
0x180009e58  lea     rcx, off_180111C80
0x180009e5f  add     rdx, rdx
0x180009e62  lea     rax, off_180111D00
0x180009e69  test    bpl, 8
0x180009e6d  cmovz   rax, rcx
0x180009e71  mov     ecx, 208h; Size
0x180009e76  mov     rbx, [rax+rdx*8]
0x180009e7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e7f  mov     ecx, 208h; Size
0x180009e84  mov     rsi, rax
0x180009e87  mov     [rax], di
0x180009e8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e8f  xor     edx, edx
0x180009e91  mov     r9d, 104h
0x180009e97  mov     r8, rsi
0x180009e9a  mov     rcx, rbx
0x180009e9d  mov     rdi, rax
0x180009ea0  mov     [rax], dx
0x180009ea3  mov     edx, 10h
0x180009ea8  call    cs:__imp_GetBrowserProfileDataFilePath
0x180009eae  mov     ebx, eax
0x180009eb0  test    eax, eax
0x180009eb2  js      loc_180009D87
0x180009eb8  mov     r8, rsi; unsigned __int16 *
0x180009ebb  mov     rcx, rdi; unsigned __int16 *
0x180009ebe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009ec3  mov     ebx, eax
0x180009ec5  test    eax, eax
0x180009ec7  js      loc_180009D87
0x180009ecd  mov     edx, 104h; cchPath
0x180009ed2  mov     rcx, rdi; pszPath
0x180009ed5  call    cs:__imp_PathCchRemoveFileSpec
0x180009edb  mov     ebx, eax
0x180009edd  test    eax, eax
0x180009edf  js      loc_180009D87
0x180009ee5  mov     edx, 104h; cchPath
0x180009eea  mov     rcx, rdi; pszPath
0x180009eed  call    cs:__imp_PathCchAddBackslash
0x180009ef3  mov     ebx, eax
0x180009ef5  test    eax, eax
0x180009ef7  js      loc_180009D87
0x180009efd  test    r14b, r14b
0x180009f00  jz      short loc_180009F1C
0x180009f02  cmp     word ptr [rdi], 0
0x180009f06  jz      short loc_180009F1C
0x180009f08  mov     edx, ebp; unsigned int
0x180009f0a  mov     rcx, rdi; unsigned __int16 *
0x180009f0d  call    ?CreateAndEncryptDirectoryAsNeeded@@YAJPEBGK@Z; CreateAndEncryptDirectoryAsNeeded(ushort const *,ulong)
0x180009f12  mov     ebx, eax
0x180009f14  test    eax, eax
0x180009f16  js      loc_180009D87
0x180009f1c  mov     [r13+0], rsi
0x180009f20  mov     [r15], rdi
0x180009f23  jmp     loc_180009D87
0x180009f28  movzx   ebx, ax
0x180009f2b  or      ebx, 80070000h
0x180009f31  jmp     loc_180009B8B
0x180009f36  movzx   ebx, ax
0x180009f39  or      ebx, 80070000h
0x180009f3f  jmp     loc_180009C64
0x180009f44  mov     rdi, [rsp+88h+var_50]
0x180009f49  jmp     loc_180009D76
0x180009f4e  mov     rcx, r12; Block
0x180009f51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f56  jmp     loc_180009DE0
```
