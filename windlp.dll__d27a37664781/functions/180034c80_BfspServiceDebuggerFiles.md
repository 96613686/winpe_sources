# BfspServiceDebuggerFiles

- ea: `0x180034c80`
- end: `0x180034fc1`
- name: `BfspServiceDebuggerFiles`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180032518`

## callees

- `0x180031598`
- `0x1800323e0`
- `0x18003379c`
- `0x180034c80`
- `0x1800366b8`
- `0x180037220`
- `0x180037440`
- `0x18007ecb2`
- `0x18007ed40`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180034e74`
- `msvcrt!wcsrchr` at `0x180034e74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034d93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034d93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034f84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034da7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034da7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034f92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ee9`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180034dda`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileSectionW` at `0x180034dda`

## string_xrefs

- `0x180034d6b`: `ServiceDebuggerFiles: %ws does not exist`
- `0x180034db7`: `ServiceDebuggerFiles: Failed to allocate config buffer`
- `0x180034dfa`: `ServiceDebuggerFiles: ConfigBuffer is too small`
- `0x180034eb4`: `Copying boot debugging files from %ws to %ws (%ws)`
- `0x180034f00`: `Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspServiceDebuggerFiles(__int64 a1)
{
  void *v2; // r13
  WCHAR *v3; // rbp
  wchar_t *v4; // rbx
  WCHAR *v5; // r15
  const wchar_t *Value; // rax
  int v7; // esi
  const WCHAR *v8; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  DWORD PrivateProfileSectionW; // eax
  DWORD v12; // r14d
  const wchar_t *v13; // rdi
  __int64 v14; // r12
  __int64 v15; // rcx
  wchar_t *v16; // rax
  wchar_t *v17; // r8
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  wchar_t *v20; // rax
  const wchar_t *v21; // rsi
  __int64 v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  __int64 v28; // [rsp+28h] [rbp-290h]
  BOOL v29; // [rsp+40h] [rbp-278h]
  WCHAR *v30; // [rsp+48h] [rbp-270h]
  wchar_t pszDest[264]; // [rsp+50h] [rbp-268h] BYREF

  BfspLogMessage(2, L"Servicing debugger files");
  v2 = (void *)BfspEnvExpandString(a1, L"|SYSPART|\\|DEST|");
  if ( v2 )
  {
    v3 = 0;
    v4 = 0;
    v30 = (WCHAR *)BfspEnvExpandString(a1, L"|SOURCE|\\BootDebuggerFiles.ini");
    v5 = v30;
    if ( v30 )
    {
      v4 = (wchar_t *)BfspEnvExpandString(a1, L"|SYSROOT|");
      if ( v4 )
      {
        Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
        v7 = wcsncmp_0(Value, L"EFI", 4u);
        v29 = BfspEnvGetValue(a1, L"ACLS") != 0;
        if ( (unsigned int)BfspFileExists(v30) )
        {
          v8 = L"BootDebuggerFiles.UEFI";
          if ( v7 )
            v8 = L"BootDebuggerFiles.PCAT";
          ProcessHeap = GetProcessHeap();
          v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x4000u);
          v3 = v10;
          if ( v10 )
          {
            PrivateProfileSectionW = GetPrivateProfileSectionW(v8, v10, 0x2000u, v30);
            v12 = PrivateProfileSectionW;
            if ( PrivateProfileSectionW )
            {
              if ( PrivateProfileSectionW >= 0x1FFE )
                BfspLogMessage(4, L"ServiceDebuggerFiles: ConfigBuffer is too small");
              v13 = v3;
              do
              {
                if ( !*v13 )
                  break;
                v14 = -1;
                do
                  ++v14;
                while ( v13[v14] );
                v15 = 2147483646;
                v16 = pszDest;
                v17 = v4;
                v18 = 260;
                do
                {
                  if ( !v15 )
                    break;
                  if ( !*v17 )
                    break;
                  *v16++ = *v17++;
                  --v15;
                  --v18;
                }
                while ( v18 );
                v19 = v16 - 1;
                if ( v18 )
                  v19 = v16;
                *v19 = 0;
                v20 = wcsrchr(v13, 0x5Cu);
                if ( v20 )
                {
                  v21 = v20 + 1;
                  *v20 = 0;
                  StringCchCatW(pszDest, 0x104u, v13);
                }
                else
                {
                  v21 = v13;
                }
                BfspLogMessage(2, L"Copying boot debugging files from %ws to %ws (%ws)", pszDest, v2, v21);
                if ( !(unsigned int)BfspCopyBootFileDirectory(
                                      (unsigned int)pszDest,
                                      0,
                                      (_DWORD)v2,
                                      (_DWORD)v21,
                                      0,
                                      v29,
                                      0,
                                      0) )
                {
                  LODWORD(v28) = GetLastError();
                  BfspLogMessage(
                    4,
                    L"Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x",
                    pszDest,
                    v2,
                    v21,
                    v28);
                }
                v22 = (unsigned int)(v14 + 1);
                v13 += v22;
                v12 -= v22;
              }
              while ( v12 );
              BfspLogMessage(2, L"Done servicing debugger files.");
              v5 = v30;
            }
            else
            {
              BfspLogMessage(2, L"List of debugger files is empty");
            }
          }
          else
          {
            BfspLogMessage(4, L"ServiceDebuggerFiles: Failed to allocate config buffer");
          }
        }
        else
        {
          BfspLogMessage(3, L"ServiceDebuggerFiles: %ws does not exist", v30);
        }
      }
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v5);
    }
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v2);
    if ( v3 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v3);
    }
    if ( v4 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180034c80  push    rbx
0x180034c82  push    rbp
0x180034c83  push    rsi
0x180034c84  push    rdi
0x180034c85  push    r12
0x180034c87  push    r13
0x180034c89  push    r14
0x180034c8b  push    r15
0x180034c8d  sub     rsp, 278h
0x180034c94  mov     rax, cs:__security_cookie
0x180034c9b  xor     rax, rsp
0x180034c9e  mov     [rsp+2B8h+var_58], rax
0x180034ca6  mov     rdi, rcx
0x180034ca9  lea     rdx, aServicingDebug; "Servicing debugger files"
0x180034cb0  mov     ecx, 2
0x180034cb5  call    BfspLogMessage
0x180034cba  lea     rdx, aSyspartDest; "|SYSPART|\\|DEST|"
0x180034cc1  mov     rcx, rdi
0x180034cc4  call    BfspEnvExpandString
0x180034cc9  xor     esi, esi
0x180034ccb  mov     r13, rax
0x180034cce  test    rax, rax
0x180034cd1  jz      loc_180034F98
0x180034cd7  lea     rdx, aSourceBootdebu; "|SOURCE|\\BootDebuggerFiles.ini"
0x180034cde  mov     rcx, rdi
0x180034ce1  mov     ebp, esi
0x180034ce3  mov     ebx, esi
0x180034ce5  call    BfspEnvExpandString
0x180034cea  mov     [rsp+2B8h+var_270], rax
0x180034cef  mov     r15, rax
0x180034cf2  test    rax, rax
0x180034cf5  jz      loc_180034F52
0x180034cfb  lea     rdx, aSysroot; "|SYSROOT|"
0x180034d02  mov     rcx, rdi
0x180034d05  call    BfspEnvExpandString
0x180034d0a  mov     rbx, rax
0x180034d0d  test    rax, rax
0x180034d10  jz      loc_180034F3E
0x180034d16  lea     rdx, aFwtype; "FWTYPE"
0x180034d1d  mov     rcx, rdi
0x180034d20  call    BfspEnvGetValue
0x180034d25  lea     r12d, [rsi+4]
0x180034d29  mov     rcx, rax; String1
0x180034d2c  mov     r8d, r12d; MaxCount
0x180034d2f  lea     rdx, aEfi; "EFI"
0x180034d36  call    wcsncmp_0
0x180034d3b  lea     rdx, aAcls; "ACLS"
0x180034d42  mov     rcx, rdi
0x180034d45  mov     esi, eax
0x180034d47  call    BfspEnvGetValue
0x180034d4c  xor     r14d, r14d
0x180034d4f  mov     ecx, r14d
0x180034d52  test    rax, rax
0x180034d55  setnz   cl
0x180034d58  mov     [rsp+2B8h+var_278], ecx
0x180034d5c  mov     rcx, r15
0x180034d5f  call    BfspFileExists
0x180034d64  test    eax, eax
0x180034d66  jnz     short loc_180034D7F
0x180034d68  mov     r8, r15
0x180034d6b  lea     rdx, aServicedebugge_0; "ServiceDebuggerFiles: %ws does not exis"...
0x180034d72  lea     ecx, [rbp+3]
0x180034d75  call    BfspLogMessage
0x180034d7a  jmp     loc_180034F3E
0x180034d7f  lea     rax, AppName; "BootDebuggerFiles.PCAT"
0x180034d86  test    esi, esi
0x180034d88  lea     rdi, aBootdebuggerfi_0; "BootDebuggerFiles.UEFI"
0x180034d8f  cmovnz  rdi, rax
0x180034d93  call    cs:__imp_GetProcessHeap
0x180034d99  mov     edx, 8; dwFlags
0x180034d9e  mov     r8d, 4000h; dwBytes
0x180034da4  mov     rcx, rax; hHeap
0x180034da7  call    cs:__imp_HeapAlloc
0x180034dad  xor     esi, esi
0x180034daf  mov     rbp, rax
0x180034db2  test    rax, rax
0x180034db5  jnz     short loc_180034DCB
0x180034db7  lea     rdx, aServicedebugge; "ServiceDebuggerFiles: Failed to allocat"...
0x180034dbe  mov     ecx, r12d
0x180034dc1  call    BfspLogMessage
0x180034dc6  jmp     loc_180034F3E
0x180034dcb  mov     r9, r15; lpFileName
0x180034dce  mov     r8d, 2000h; nSize
0x180034dd4  mov     rdx, rbp; lpReturnedString
0x180034dd7  mov     rcx, rdi; lpAppName
0x180034dda  call    cs:__imp_GetPrivateProfileSectionW
0x180034de0  mov     r14d, eax
0x180034de3  test    eax, eax
0x180034de5  jnz     short loc_180034DF3
0x180034de7  lea     rdx, aListOfDebugger; "List of debugger files is empty"
0x180034dee  lea     ecx, [rax+2]
0x180034df1  jmp     short loc_180034DC1
0x180034df3  cmp     eax, 1FFEh
0x180034df8  jb      short loc_180034E09
0x180034dfa  lea     rdx, aServicedebugge_1; "ServiceDebuggerFiles: ConfigBuffer is t"...
0x180034e01  mov     ecx, r12d
0x180034e04  call    BfspLogMessage
0x180034e09  mov     r15d, [rsp+2B8h+var_278]
0x180034e0e  mov     rdi, rbp
0x180034e11  cmp     [rdi], si
0x180034e14  jz      loc_180034F28
0x180034e1a  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034e1e  inc     r12
0x180034e21  cmp     [rdi+r12*2], si
0x180034e26  jnz     short loc_180034E1E
0x180034e28  mov     ecx, 7FFFFFFEh
0x180034e2d  lea     rax, [rsp+2B8h+pszDest]
0x180034e32  mov     r8, rbx
0x180034e35  mov     edx, 104h
0x180034e3a  test    rcx, rcx
0x180034e3d  jz      short loc_180034E5E
0x180034e3f  movzx   r9d, word ptr [r8]
0x180034e43  test    r9w, r9w
0x180034e47  jz      short loc_180034E5E
0x180034e49  mov     [rax], r9w
0x180034e4d  add     r8, 2
0x180034e51  add     rax, 2
0x180034e55  dec     rcx
0x180034e58  sub     rdx, 1
0x180034e5c  jnz     short loc_180034E3A
0x180034e5e  test    rdx, rdx
0x180034e61  lea     rcx, [rax-2]
0x180034e65  mov     edx, 5Ch ; '\'; Ch
0x180034e6a  cmovnz  rcx, rax
0x180034e6e  mov     [rcx], si
0x180034e71  mov     rcx, rdi; Str
0x180034e74  call    cs:__imp_wcsrchr
0x180034e7a  mov     rsi, rax
0x180034e7d  test    rax, rax
0x180034e80  jz      short loc_180034E9F
0x180034e82  xor     ecx, ecx
0x180034e84  add     rsi, 2
0x180034e88  mov     [rax], cx
0x180034e8b  mov     r8, rdi; pszSrc
0x180034e8e  lea     rcx, [rsp+2B8h+pszDest]; pszDest
0x180034e93  mov     edx, 104h; cchDest
0x180034e98  call    StringCchCatW
0x180034e9d  jmp     short loc_180034EA2
0x180034e9f  mov     rsi, rdi
0x180034ea2  mov     r9, r13
0x180034ea5  mov     [rsp+2B8h+var_298], rsi
0x180034eaa  lea     r8, [rsp+2B8h+pszDest]
0x180034eaf  mov     ecx, 2
0x180034eb4  lea     rdx, aCopyingBootDeb; "Copying boot debugging files from %ws t"...
0x180034ebb  call    BfspLogMessage
0x180034ec0  xor     eax, eax
0x180034ec2  lea     rcx, [rsp+2B8h+pszDest]
0x180034ec7  mov     [rsp+2B8h+var_280], eax
0x180034ecb  mov     r9, rsi
0x180034ece  mov     [rsp+2B8h+var_288], eax
0x180034ed2  mov     r8, r13
0x180034ed5  mov     dword ptr [rsp+2B8h+var_290], r15d
0x180034eda  xor     edx, edx
0x180034edc  mov     dword ptr [rsp+2B8h+var_298], eax
0x180034ee0  call    BfspCopyBootFileDirectory
0x180034ee5  test    eax, eax
0x180034ee7  jnz     short loc_180034F11
0x180034ee9  call    cs:__imp_GetLastError
0x180034eef  mov     dword ptr [rsp+2B8h+var_290], eax
0x180034ef3  mov     r9, r13
0x180034ef6  lea     r8, [rsp+2B8h+pszDest]
0x180034efb  mov     [rsp+2B8h+var_298], rsi
0x180034f00  lea     rdx, aErrorCopyingBo; "Error copying boot debugging files from"...
0x180034f07  mov     ecx, 4
0x180034f0c  call    BfspLogMessage
0x180034f11  lea     eax, [r12+1]
0x180034f16  mov     esi, 0
0x180034f1b  lea     rdi, [rdi+rax*2]
0x180034f1f  sub     r14d, eax
0x180034f22  jnz     loc_180034E11
0x180034f28  lea     rdx, aDoneServicingD; "Done servicing debugger files."
0x180034f2f  mov     ecx, 2
0x180034f34  call    BfspLogMessage
0x180034f39  mov     r15, [rsp+2B8h+var_270]
0x180034f3e  call    cs:__imp_GetProcessHeap
0x180034f44  mov     r8, r15; lpMem
0x180034f47  xor     edx, edx; dwFlags
0x180034f49  mov     rcx, rax; hHeap
0x180034f4c  call    cs:__imp_HeapFree
0x180034f52  call    cs:__imp_GetProcessHeap
0x180034f58  mov     r8, r13; lpMem
0x180034f5b  xor     edx, edx; dwFlags
0x180034f5d  mov     rcx, rax; hHeap
0x180034f60  call    cs:__imp_HeapFree
0x180034f66  test    rbp, rbp
0x180034f69  jz      short loc_180034F7F
0x180034f6b  call    cs:__imp_GetProcessHeap
0x180034f71  mov     r8, rbp; lpMem
0x180034f74  xor     edx, edx; dwFlags
0x180034f76  mov     rcx, rax; hHeap
0x180034f79  call    cs:__imp_HeapFree
0x180034f7f  test    rbx, rbx
0x180034f82  jz      short loc_180034F98
0x180034f84  call    cs:__imp_GetProcessHeap
0x180034f8a  mov     r8, rbx; lpMem
0x180034f8d  xor     edx, edx; dwFlags
0x180034f8f  mov     rcx, rax; hHeap
0x180034f92  call    cs:__imp_HeapFree
0x180034f98  mov     eax, 1
0x180034f9d  mov     rcx, [rsp+2B8h+var_58]
0x180034fa5  xor     rcx, rsp; StackCookie
0x180034fa8  call    __security_check_cookie
0x180034fad  add     rsp, 278h
0x180034fb4  pop     r15
0x180034fb6  pop     r14
0x180034fb8  pop     r13
0x180034fba  pop     r12
0x180034fbc  pop     rdi
0x180034fbd  pop     rsi
0x180034fbe  pop     rbp
0x180034fbf  pop     rbx
0x180034fc0  retn
```
