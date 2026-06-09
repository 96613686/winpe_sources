# WiaTrcLib::InitTraceFile(void)

- ea: `0x180075b04`
- end: `0x180075de1`
- name: `?InitTraceFile@WiaTrcLib@@YAJXZ`
- size: `733`
- prototype: `__int64 __fastcall(WiaTrcLib *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800767cc`

## callees

- `0x180033cc0`
- `0x180034658`
- `0x180075b04`
- `0x180075f3c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180075da5`
- `KERNEL32!LocalFree` at `0x180075db5`
- `KERNEL32!LocalFree` at `0x180075da5`
- `KERNEL32!LocalFree` at `0x180075db5`
- `KERNEL32!ReleaseMutex` at `0x180075d95`
- `KERNEL32!ReleaseMutex` at `0x180075d95`
- `KERNEL32!GetLastError` at `0x180075b8e`
- `KERNEL32!GetLastError` at `0x180075bc6`
- `KERNEL32!GetLastError` at `0x180075c4a`
- `KERNEL32!GetLastError` at `0x180075ca9`
- `KERNEL32!GetLastError` at `0x180075b8e`
- `KERNEL32!GetLastError` at `0x180075bc6`
- `KERNEL32!GetLastError` at `0x180075c4a`
- `KERNEL32!GetLastError` at `0x180075ca9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180075c5e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180075c7b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180075c5e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180075c7b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075c0b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075ce4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075c0b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180075ce4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075d33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075d6c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075d33`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075d6c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180075c40`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180075c40`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180075c2a`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180075c2a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180075cff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180075cff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180075b84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180075bbc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180075b84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180075bbc`

## pseudocode

```c
__int64 __fastcall WiaTrcLib::InitTraceFile(WiaTrcLib *this)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  signed int v4; // eax
  int v5; // r8d
  DWORD dwCreationDisposition; // edi
  int v7; // r8d
  HANDLE FileW; // rax
  int v9; // ecx
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_ATTRIBUTES hMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp+180h] BYREF

  if ( g_WiaTrace_bSuppressProcessOutput )
    return 0;
  v2 = 0;
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(&hMem, 0, sizeof(hMem));
  SecurityDescriptor.nLength = 24;
  hMem.nLength = 24;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GRGWGXDTSDCCLC;;;LS)(A;OICI;GRGWGXDTSDCCLC;;;AU)",
         1u,
         &SecurityDescriptor.lpSecurityDescriptor,
         0) )
  {
    goto LABEL_10;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( !v2 )
  {
LABEL_10:
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GA;;;LS)(A;OICI;GA;;;AU)",
           1u,
           &hMem.lpSecurityDescriptor,
           0) )
    {
      goto LABEL_11;
    }
    v4 = GetLastError();
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    if ( !v2 )
    {
LABEL_11:
      memset_0(Dst, 0, 0x20Au);
      ExpandEnvironmentStringsW(L"%systemroot%\\Debug\\WIA", Dst, 0x105u);
      if ( (unsigned int)WiaTrcLib::IsPathALink((WiaTrcLib *)Dst, (const unsigned __int16 *)1, v5)
        && !RemoveDirectoryW(Dst) )
      {
        goto LABEL_17;
      }
      if ( !CreateDirectoryW(Dst, &SecurityDescriptor) )
        GetLastError();
      if ( ((WiaTrcLib::g_WiaTrc_hFileMutex = CreateMutexW(&hMem, 1, L"Global\\WIATRACE_MUTEX")) != 0
         || (WiaTrcLib::g_WiaTrc_hFileMutex = CreateMutexW(0, 1, L"Global\\WIATRACE_MUTEX")) != 0)
        && ((memset_0(FileName, 0, 0x20Au), GetLastError() != 183)
          ? (dwCreationDisposition = (*(_WORD *)&g_WiaTrace_ulFlags & 0x400) != 0 ? 4 : 2)
          : (dwCreationDisposition = 4),
            (ExpandEnvironmentStringsW(L"%systemroot%\\Debug\\WIA\\wiatrace.log", FileName, 0x105u),
             !(unsigned int)WiaTrcLib::IsPathALink((WiaTrcLib *)FileName, 0, v7))
         || DeleteFileW(FileName)) )
      {
        WiaTrcLib::g_WiaTrc_hFile = CreateFileW(
                                      FileName,
                                      0x40000000u,
                                      3u,
                                      &SecurityDescriptor,
                                      dwCreationDisposition,
                                      0x80u,
                                      0);
        if ( WiaTrcLib::g_WiaTrc_hFile == (HANDLE)-1LL )
        {
          FileW = CreateFileW(FileName, 0x40000000u, 3u, 0, dwCreationDisposition, 0x80u, 0);
          v9 = v2;
          WiaTrcLib::g_WiaTrc_hFile = FileW;
          if ( FileW == (HANDLE)-1LL )
            v9 = -2147467259;
          v2 = v9;
        }
      }
      else
      {
LABEL_17:
        v2 = -2147467259;
      }
    }
  }
  if ( WiaTrcLib::g_WiaTrc_hFileMutex )
    ReleaseMutex(WiaTrcLib::g_WiaTrc_hFileMutex);
  if ( SecurityDescriptor.lpSecurityDescriptor )
    LocalFree(SecurityDescriptor.lpSecurityDescriptor);
  if ( hMem.lpSecurityDescriptor )
    LocalFree(hMem.lpSecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x180075b04  mov     [rsp-8+arg_0], rbx
0x180075b09  mov     [rsp-8+arg_8], rdi
0x180075b0e  push    rbp
0x180075b0f  lea     rbp, [rsp-3A0h]
0x180075b17  sub     rsp, 4A0h
0x180075b1e  mov     rax, cs:__security_cookie
0x180075b25  xor     rax, rsp
0x180075b28  mov     [rbp+3A0h+var_10], rax
0x180075b2f  cmp     cs:g_WiaTrace_bSuppressProcessOutput, 0
0x180075b36  jz      short loc_180075B3F
0x180075b38  xor     eax, eax
0x180075b3a  jmp     loc_180075DBD
0x180075b3f  xor     ebx, ebx
0x180075b41  lea     r8, [rsp+4A0h+SecurityDescriptor+8]; SecurityDescriptor
0x180075b46  xor     eax, eax
0x180075b48  lea     rcx, aDAOiciGaSyAOic_0; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OI"...
0x180075b4f  mov     [rsp+4A0h+var_450], rax
0x180075b54  xorps   xmm0, xmm0
0x180075b57  mov     [rsp+4A0h+var_438], rax
0x180075b5c  xorps   xmm1, xmm1
0x180075b5f  lea     eax, [rbx+18h]
0x180075b62  mov     dword ptr [rsp+4A0h+var_450], ebx
0x180075b66  movups  xmmword ptr [rsp+4A0h+SecurityDescriptor], xmm0
0x180075b6b  lea     edi, [rbx+1]
0x180075b6e  xor     r9d, r9d; SecurityDescriptorSize
0x180075b71  movups  xmmword ptr [rsp+4A0h+hMem], xmm1
0x180075b76  mov     edx, edi; StringSDRevision
0x180075b78  mov     dword ptr [rsp+4A0h+SecurityDescriptor], eax
0x180075b7c  mov     dword ptr [rsp+4A0h+hMem], eax
0x180075b80  mov     dword ptr [rsp+4A0h+var_438], ebx
0x180075b84  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180075b8a  test    eax, eax
0x180075b8c  jnz     short loc_180075BAB
0x180075b8e  call    cs:__imp_GetLastError
0x180075b94  mov     ebx, eax
0x180075b96  test    eax, eax
0x180075b98  jle     short loc_180075BA3
0x180075b9a  movzx   ebx, ax
0x180075b9d  or      ebx, 80070000h
0x180075ba3  test    ebx, ebx
0x180075ba5  jnz     loc_180075D89
0x180075bab  xor     r9d, r9d; SecurityDescriptorSize
0x180075bae  lea     r8, [rsp+4A0h+hMem+8]; SecurityDescriptor
0x180075bb3  mov     edx, edi; StringSDRevision
0x180075bb5  lea     rcx, aDAOiciGaSyAOic; "D:(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OI"...
0x180075bbc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180075bc2  test    eax, eax
0x180075bc4  jnz     short loc_180075BE3
0x180075bc6  call    cs:__imp_GetLastError
0x180075bcc  mov     ebx, eax
0x180075bce  test    eax, eax
0x180075bd0  jle     short loc_180075BDB
0x180075bd2  movzx   ebx, ax
0x180075bd5  or      ebx, 80070000h
0x180075bdb  test    ebx, ebx
0x180075bdd  jnz     loc_180075D89
0x180075be3  xor     edx, edx; Val
0x180075be5  lea     rcx, [rbp+3A0h+Dst]; void *
0x180075bec  mov     r8d, 20Ah; Size
0x180075bf2  call    memset_0
0x180075bf7  mov     r8d, 105h; nSize
0x180075bfd  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x180075c04  lea     rcx, aSystemrootDebu; "%systemroot%\\Debug\\WIA"
0x180075c0b  call    cs:__imp_ExpandEnvironmentStringsW
0x180075c11  mov     edx, edi; unsigned __int16 *
0x180075c13  lea     rcx, [rbp+3A0h+Dst]; this
0x180075c1a  call    ?IsPathALink@WiaTrcLib@@YAHPEBGH@Z; WiaTrcLib::IsPathALink(ushort const *,int)
0x180075c1f  test    eax, eax
0x180075c21  jz      short loc_180075C34
0x180075c23  lea     rcx, [rbp+3A0h+Dst]; lpPathName
0x180075c2a  call    cs:__imp_RemoveDirectoryW
0x180075c30  test    eax, eax
0x180075c32  jz      short loc_180075C8D
0x180075c34  lea     rdx, [rsp+4A0h+SecurityDescriptor]; lpSecurityAttributes
0x180075c39  lea     rcx, [rbp+3A0h+Dst]; lpPathName
0x180075c40  call    cs:__imp_CreateDirectoryW
0x180075c46  test    eax, eax
0x180075c48  jnz     short loc_180075C50
0x180075c4a  call    cs:__imp_GetLastError
0x180075c50  lea     r8, aGlobalWiatrace; "Global\\WIATRACE_MUTEX"
0x180075c57  mov     edx, edi; bInitialOwner
0x180075c59  lea     rcx, [rsp+4A0h+hMem]; lpMutexAttributes
0x180075c5e  call    cs:__imp_CreateMutexW
0x180075c64  mov     cs:?g_WiaTrc_hFileMutex@WiaTrcLib@@3PEAXEA, rax; void * WiaTrcLib::g_WiaTrc_hFileMutex
0x180075c6b  test    rax, rax
0x180075c6e  jnz     short loc_180075C97
0x180075c70  lea     r8, aGlobalWiatrace; "Global\\WIATRACE_MUTEX"
0x180075c77  mov     edx, edi; bInitialOwner
0x180075c79  xor     ecx, ecx; lpMutexAttributes
0x180075c7b  call    cs:__imp_CreateMutexW
0x180075c81  mov     cs:?g_WiaTrc_hFileMutex@WiaTrcLib@@3PEAXEA, rax; void * WiaTrcLib::g_WiaTrc_hFileMutex
0x180075c88  test    rax, rax
0x180075c8b  jnz     short loc_180075C97
0x180075c8d  mov     ebx, 80004005h
0x180075c92  jmp     loc_180075D89
0x180075c97  xor     edx, edx; Val
0x180075c99  lea     rcx, [rsp+4A0h+FileName]; void *
0x180075c9e  mov     r8d, 20Ah; Size
0x180075ca4  call    memset_0
0x180075ca9  call    cs:__imp_GetLastError
0x180075caf  cmp     eax, 0B7h
0x180075cb4  jnz     short loc_180075CBD
0x180075cb6  mov     edi, 4
0x180075cbb  jmp     short loc_180075CD2
0x180075cbd  mov     eax, cs:g_WiaTrace_ulFlags
0x180075cc3  and     eax, 400h
0x180075cc8  neg     eax
0x180075cca  sbb     edi, edi
0x180075ccc  and     edi, 2
0x180075ccf  add     edi, 2
0x180075cd2  mov     r8d, 105h; nSize
0x180075cd8  lea     rdx, [rsp+4A0h+FileName]; lpDst
0x180075cdd  lea     rcx, aSystemrootDebu_0; "%systemroot%\\Debug\\WIA\\wiatrace.log"
0x180075ce4  call    cs:__imp_ExpandEnvironmentStringsW
0x180075cea  xor     edx, edx; unsigned __int16 *
0x180075cec  lea     rcx, [rsp+4A0h+FileName]; this
0x180075cf1  call    ?IsPathALink@WiaTrcLib@@YAHPEBGH@Z; WiaTrcLib::IsPathALink(ushort const *,int)
0x180075cf6  test    eax, eax
0x180075cf8  jz      short loc_180075D09
0x180075cfa  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180075cff  call    cs:__imp_DeleteFileW
0x180075d05  test    eax, eax
0x180075d07  jz      short loc_180075C8D
0x180075d09  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180075d12  lea     r9, [rsp+4A0h+SecurityDescriptor]; lpSecurityAttributes
0x180075d17  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180075d1f  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180075d24  mov     edx, 40000000h; dwDesiredAccess
0x180075d29  mov     [rsp+4A0h+dwCreationDisposition], edi; dwCreationDisposition
0x180075d2d  mov     r8d, 3; dwShareMode
0x180075d33  call    cs:__imp_CreateFileW
0x180075d39  mov     cs:?g_WiaTrc_hFile@WiaTrcLib@@3PEAXEA, rax; void * WiaTrcLib::g_WiaTrc_hFile
0x180075d40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075d44  jnz     short loc_180075D89
0x180075d46  mov     [rsp+4A0h+hTemplateFile], 0; hTemplateFile
0x180075d4f  lea     r8d, [rax+4]; dwShareMode
0x180075d53  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180075d5b  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x180075d60  xor     r9d, r9d; lpSecurityAttributes
0x180075d63  mov     [rsp+4A0h+dwCreationDisposition], edi; dwCreationDisposition
0x180075d67  mov     edx, 40000000h; dwDesiredAccess
0x180075d6c  call    cs:__imp_CreateFileW
0x180075d72  mov     ecx, ebx
0x180075d74  mov     ebx, 80004005h
0x180075d79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075d7d  mov     cs:?g_WiaTrc_hFile@WiaTrcLib@@3PEAXEA, rax; void * WiaTrcLib::g_WiaTrc_hFile
0x180075d84  cmovz   ecx, ebx
0x180075d87  mov     ebx, ecx
0x180075d89  mov     rcx, cs:?g_WiaTrc_hFileMutex@WiaTrcLib@@3PEAXEA; hMutex
0x180075d90  test    rcx, rcx
0x180075d93  jz      short loc_180075D9B
0x180075d95  call    cs:__imp_ReleaseMutex
0x180075d9b  mov     rcx, [rsp+4A0h+SecurityDescriptor+8]; hMem
0x180075da0  test    rcx, rcx
0x180075da3  jz      short loc_180075DAB
0x180075da5  call    cs:__imp_LocalFree
0x180075dab  mov     rcx, [rsp+4A0h+hMem+8]; hMem
0x180075db0  test    rcx, rcx
0x180075db3  jz      short loc_180075DBB
0x180075db5  call    cs:__imp_LocalFree
0x180075dbb  mov     eax, ebx
0x180075dbd  mov     rcx, [rbp+3A0h+var_10]
0x180075dc4  xor     rcx, rsp; StackCookie
0x180075dc7  call    __security_check_cookie
0x180075dcc  lea     r11, [rsp+4A0h+var_s0]
0x180075dd4  mov     rbx, [r11+10h]
0x180075dd8  mov     rdi, [r11+18h]
0x180075ddc  mov     rsp, r11
0x180075ddf  pop     rbp
0x180075de0  retn
```
