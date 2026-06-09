# DeleteFileEx2

- ea: `0x18003d5cc`
- end: `0x18003dbc4`
- name: `DeleteFileEx2`
- size: `1528`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18003dbcc`
- `0x18003e7c0`
- `0x18003eae0`
- `0x18003eba8`

## callees

- `0x18000fd58`
- `0x18003d150`
- `0x18003d5cc`
- `0x18003f704`
- `0x180040a18`
- `0x1800607b0`
- `0x180060ce2`
- `0x180060e5a`
- `0x180060e70`
- `0x180061a10`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003d7a1`
- `KERNEL32!GetProcAddress` at `0x18003d7be`
- `KERNEL32!GetProcAddress` at `0x18003d7a1`
- `KERNEL32!GetProcAddress` at `0x18003d7be`
- `KERNEL32!SetFileAttributesW` at `0x18003d649`
- `KERNEL32!SetFileAttributesW` at `0x18003dae3`
- `KERNEL32!SetFileAttributesW` at `0x18003d649`
- `KERNEL32!SetFileAttributesW` at `0x18003dae3`
- `KERNEL32!GetFullPathNameW` at `0x18003d81d`
- `KERNEL32!GetFullPathNameW` at `0x18003d81d`
- `KERNEL32!FindClose` at `0x18003d982`
- `KERNEL32!FindClose` at `0x18003d982`
- `KERNEL32!HeapFree` at `0x18003d729`
- `KERNEL32!HeapFree` at `0x18003d9a2`
- `KERNEL32!HeapFree` at `0x18003db08`
- `KERNEL32!HeapFree` at `0x18003db7c`
- `KERNEL32!HeapFree` at `0x18003d729`
- `KERNEL32!HeapFree` at `0x18003d9a2`
- `KERNEL32!HeapFree` at `0x18003db08`
- `KERNEL32!HeapFree` at `0x18003db7c`
- `KERNEL32!GetLastError` at `0x18003d9b0`
- `KERNEL32!GetLastError` at `0x18003d9d5`
- `KERNEL32!GetLastError` at `0x18003db25`
- `KERNEL32!GetLastError` at `0x18003db3a`
- `KERNEL32!GetLastError` at `0x18003d9b0`
- `KERNEL32!GetLastError` at `0x18003d9d5`
- `KERNEL32!GetLastError` at `0x18003db25`
- `KERNEL32!GetLastError` at `0x18003db3a`
- `KERNEL32!GetFileAttributesW` at `0x18003d631`
- `KERNEL32!GetFileAttributesW` at `0x18003d631`
- `KERNEL32!GetFileInformationByHandle` at `0x18003d747`
- `KERNEL32!GetFileInformationByHandle` at `0x18003d747`
- `KERNEL32!GetModuleHandleW` at `0x18003d783`
- `KERNEL32!GetModuleHandleW` at `0x18003d783`
- `KERNEL32!CloseHandle` at `0x18003db17`
- `KERNEL32!CloseHandle` at `0x18003db17`
- `KERNEL32!CreateFileW` at `0x18003d68d`
- `KERNEL32!CreateFileW` at `0x18003d68d`
- `KERNEL32!SetLastError` at `0x18003db8b`
- `KERNEL32!SetLastError` at `0x18003db8b`
- `KERNEL32!GetProcessHeap` at `0x18003d715`
- `KERNEL32!GetProcessHeap` at `0x18003d98e`
- `KERNEL32!GetProcessHeap` at `0x18003daf4`
- `KERNEL32!GetProcessHeap` at `0x18003db68`
- `KERNEL32!GetProcessHeap` at `0x18003d715`
- `KERNEL32!GetProcessHeap` at `0x18003d98e`
- `KERNEL32!GetProcessHeap` at `0x18003daf4`
- `KERNEL32!GetProcessHeap` at `0x18003db68`
- `ntdll!NtSetInformationFile` at `0x18003da14`
- `ntdll!NtSetInformationFile` at `0x18003da49`
- `ntdll!NtSetInformationFile` at `0x18003da14`
- `ntdll!NtSetInformationFile` at `0x18003da49`
- `ntdll!RtlFreeHeap` at `0x18003d8eb`
- `ntdll!RtlFreeHeap` at `0x18003d8eb`
- `ntdll!RtlAllocateHeap` at `0x18003d8ab`
- `ntdll!RtlAllocateHeap` at `0x18003d8ab`
- `ntdll!RtlNtStatusToDosError` at `0x18003da63`
- `ntdll!RtlNtStatusToDosError` at `0x18003da63`

## string_xrefs

- `0x18003d77c`: `kernel32.dll`
- `0x18003d6ff`: `DeleteFileEx: Spoofing detected deleting [%s] -> [%s]`
- `0x18003d9bc`: `DeleteFileEx: Unable to allocate memory for the full path name; GLE = 0x%x`
- `0x18003d9e4`: `DeleteFileEx: Unable to get full path name on [%s]; GLE = 0x%x`
- `0x18003da72`: `DeleteFileEx: Unable to remove [%s]; GLE = 0x%x`
- `0x18003dab9`: `DeleteFileEx: hardlink given to us is: %s`
- `0x18003dacb`: `DeleteFileEx: Trying to set back attributes on: %s`
- `0x18003db31`: `DeleteFileEx: Unable to delete [%s]; GLE = 0x%x`
- `0x18003db46`: `DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall DeleteFileEx2(unsigned __int16 *a1, int a2)
{
  char v2; // di
  unsigned int v3; // r12d
  DWORD v4; // r15d
  const WCHAR *v6; // rax
  WCHAR *v7; // r14
  HANDLE FileW; // rax
  void *v9; // r13
  LPVOID v10; // rbx
  bool v11; // sf
  int v12; // eax
  HMODULE ModuleHandleW; // rax
  HMODULE v14; // rbx
  int v15; // ebx
  NTSTATUS v16; // eax
  WCHAR *v17; // rbx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  const wchar_t *v20; // r8
  HANDLE v21; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  char v24[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  int v28; // [rsp+58h] [rbp-A8h]
  DWORD dwFileAttributes; // [rsp+5Ch] [rbp-A4h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer; // [rsp+C0h] [rbp-40h] BYREF

  v28 = a2;
  v2 = a2;
  v31 = 0;
  v3 = 0;
  v4 = 0;
  v6 = (const WCHAR *)PrepareUnicodePath(a1);
  v7 = (WCHAR *)v6;
  if ( v6 )
  {
    dwFileAttributes = GetFileAttributesW(v6);
    if ( SetFileAttributesW(v7, 0x2000u) )
    {
      FileW = CreateFileW(v7, 0x10000u, (v2 & 1) == 0 ? 7 : 0, 0, 3u, 0x2200000u, 0);
      v9 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v26 = 0;
        v10 = 0;
        lpMem = 0;
        v24[0] = 1;
        v25 = 0;
        if ( (v2 & 0x20) == 0 || (v10 = lpMem, v11 = (int)ValidateRedirectedHandle(FileW, v7) < 0, v12 = v25, v11) )
          v12 = 1;
        if ( v12 )
        {
          if ( GetFileInformationByHandle(v9, &FileInformation)
            && FileInformation.nNumberOfLinks > 1
            && (!g_FindFirstFileName || !g_FindNextFileName) )
          {
            ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
            v14 = ModuleHandleW;
            if ( ModuleHandleW )
            {
              g_FindFirstFileName = (__int64)GetProcAddress(ModuleHandleW, "FindFirstFileNameW");
              g_FindNextFileName = (__int64)GetProcAddress(v14, "FindNextFileNameW");
            }
          }
        }
        else
        {
          LibLog(&g_WdsLibLog, 50331648, L"DeleteFileEx: Spoofing detected deleting [%s] -> [%s]", v7, v10);
          v4 = 681;
        }
        v15 = NtSetInformationFile(v9, &IoStatusBlock, v24, 1u, FileDispositionInformation);
        if ( v15 >= 0
          || (v27 = 1, v16 = NtSetInformationFile(v9, &IoStatusBlock, &v27, 4u, (FILE_INFORMATION_CLASS)64), v16 >= 0) )
        {
          v3 = 1;
        }
        else
        {
          if ( v16 != -1073741821 )
            v15 = v16;
          dwCreationDisposition[0] = RtlNtStatusToDosError(v15);
          v4 = dwCreationDisposition[0];
          LibLog(
            &g_WdsLibLog,
            50331648,
            L"DeleteFileEx: Unable to remove [%s]; GLE = 0x%x",
            v7,
            *(_QWORD *)dwCreationDisposition);
        }
        if ( v26 )
        {
          v17 = (WCHAR *)PrepareUnicodePath(&Buffer);
          if ( (v28 & 4) == 0 )
          {
            LibLog(&g_WdsLibLog, 0x4000000, L"DeleteFileEx: hardlink given to us is: %s", &Buffer);
            LibLog(&g_WdsLibLog, 0x4000000, L"DeleteFileEx: Trying to set back attributes on: %s", v17);
          }
          SetFileAttributesW(v17, dwFileAttributes);
          if ( v17 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v17);
          }
        }
        CloseHandle(v9);
        goto LABEL_30;
      }
      LastError = GetLastError();
      v20 = L"DeleteFileEx: Unable to delete [%s]; GLE = 0x%x";
    }
    else
    {
      LastError = GetLastError();
      v20 = L"DeleteFileEx: Unable to clear out attributes on [%s]; GLE = 0x%x";
    }
    v4 = LastError;
    LibLog(&g_WdsLibLog, 50331648, v20, a1, LastError);
LABEL_30:
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v7);
  }
  SetLastError(v4);
  return v3;
}

```

## disassembly

```asm
0x18003d5cc  mov     [rsp-8+arg_10], rbx
0x18003d5d1  push    rbp
0x18003d5d2  push    rsi
0x18003d5d3  push    rdi
0x18003d5d4  push    r12
0x18003d5d6  push    r13
0x18003d5d8  push    r14
0x18003d5da  push    r15
0x18003d5dc  lea     rbp, [rsp-0FFD0h]
0x18003d5e4  mov     eax, 100D0h
0x18003d5e9  call    _alloca_probe
0x18003d5ee  sub     rsp, rax
0x18003d5f1  mov     rax, cs:__security_cookie
0x18003d5f8  xor     rax, rsp
0x18003d5fb  mov     [rbp+10000h+var_40], rax
0x18003d602  xor     esi, esi
0x18003d604  mov     [rsp+10100h+var_100A8], edx
0x18003d608  mov     edi, edx
0x18003d60a  mov     [rsp+10100h+var_10098], rsi
0x18003d60f  lea     rdx, [rsp+10100h+var_10098]
0x18003d614  mov     r12d, esi
0x18003d617  mov     r15d, esi
0x18003d61a  mov     rbx, rcx
0x18003d61d  call    PrepareUnicodePath
0x18003d622  mov     r14, rax
0x18003d625  test    rax, rax
0x18003d628  jz      loc_18003DB88
0x18003d62e  mov     rcx, rax; lpFileName
0x18003d631  call    cs:__imp_GetFileAttributesW
0x18003d638  nop     dword ptr [rax+rax+00h]
0x18003d63d  mov     edx, 2000h; dwFileAttributes
0x18003d642  mov     rcx, r14; lpFileName
0x18003d645  mov     [rsp+10100h+dwFileAttributes], eax
0x18003d649  call    cs:__imp_SetFileAttributesW
0x18003d650  nop     dword ptr [rax+rax+00h]
0x18003d655  test    eax, eax
0x18003d657  jz      loc_18003DB3A
0x18003d65d  mov     eax, edi
0x18003d65f  mov     [rsp+10100h+hTemplateFile], rsi; hTemplateFile
0x18003d664  and     al, 1
0x18003d666  mov     [rsp+10100h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003d66e  neg     al
0x18003d670  mov     [rsp+10100h+dwCreationDisposition], 3; dwCreationDisposition
0x18003d678  mov     edx, 10000h; dwDesiredAccess
0x18003d67d  mov     rcx, r14; lpFileName
0x18003d680  sbb     r8d, r8d
0x18003d683  xor     r9d, r9d; lpSecurityAttributes
0x18003d686  not     r8d
0x18003d689  and     r8d, 7; dwShareMode
0x18003d68d  call    cs:__imp_CreateFileW
0x18003d694  nop     dword ptr [rax+rax+00h]
0x18003d699  mov     r13, rax
0x18003d69c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d6a0  jz      loc_18003DB25
0x18003d6a6  mov     [rsp+10100h+var_100B0], esi
0x18003d6aa  mov     ebx, esi
0x18003d6ac  mov     [rsp+10100h+lpMem], rbx
0x18003d6b1  mov     [rsp+10100h+var_100C0], 1
0x18003d6b6  mov     [rsp+10100h+var_100B8], esi
0x18003d6ba  test    dil, 20h
0x18003d6be  jz      short loc_18003D6E2
0x18003d6c0  lea     r9, [rsp+10100h+lpMem]
0x18003d6c5  mov     rdx, r14; String2
0x18003d6c8  lea     r8, [rsp+10100h+var_100B8]
0x18003d6cd  mov     rcx, rax; hFile
0x18003d6d0  call    ValidateRedirectedHandle
0x18003d6d5  mov     rbx, [rsp+10100h+lpMem]
0x18003d6da  test    eax, eax
0x18003d6dc  mov     eax, [rsp+10100h+var_100B8]
0x18003d6e0  jns     short loc_18003D6E7
0x18003d6e2  mov     eax, 1
0x18003d6e7  lea     rdi, g_WdsLibLog
0x18003d6ee  mov     esi, 3000000h
0x18003d6f3  test    eax, eax
0x18003d6f5  jnz     short loc_18003D740
0x18003d6f7  mov     r9, r14
0x18003d6fa  mov     qword ptr [rsp+10100h+dwCreationDisposition], rbx
0x18003d6ff  lea     r8, aDeletefileexSp; "DeleteFileEx: Spoofing detected deletin"...
0x18003d706  mov     edx, esi
0x18003d708  mov     rcx, rdi
0x18003d70b  call    LibLog
0x18003d710  test    rbx, rbx
0x18003d713  jz      short loc_18003D735
0x18003d715  call    cs:__imp_GetProcessHeap
0x18003d71c  nop     dword ptr [rax+rax+00h]
0x18003d721  mov     r8, rbx; lpMem
0x18003d724  xor     edx, edx; dwFlags
0x18003d726  mov     rcx, rax; hHeap
0x18003d729  call    cs:__imp_HeapFree
0x18003d730  nop     dword ptr [rax+rax+00h]
0x18003d735  mov     r15d, 2A9h
0x18003d73b  jmp     loc_18003D9F9
0x18003d740  lea     rdx, [rbp+10000h+FileInformation]; lpFileInformation
0x18003d744  mov     rcx, r13; hFile
0x18003d747  call    cs:__imp_GetFileInformationByHandle
0x18003d74e  nop     dword ptr [rax+rax+00h]
0x18003d753  xor     ebx, ebx
0x18003d755  test    eax, eax
0x18003d757  jz      loc_18003D9F9
0x18003d75d  cmp     [rbp+10000h+FileInformation.nNumberOfLinks], 1
0x18003d761  jbe     loc_18003D9F9
0x18003d767  cmp     cs:g_FindFirstFileName, rbx
0x18003d76e  jz      short loc_18003D77C
0x18003d770  mov     rax, cs:g_FindNextFileName
0x18003d777  test    rax, rax
0x18003d77a  jnz     short loc_18003D7DC
0x18003d77c  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18003d783  call    cs:__imp_GetModuleHandleW
0x18003d78a  nop     dword ptr [rax+rax+00h]
0x18003d78f  mov     rbx, rax
0x18003d792  test    rax, rax
0x18003d795  jz      short loc_18003D7D3
0x18003d797  lea     rdx, ProcName; "FindFirstFileNameW"
0x18003d79e  mov     rcx, rax; hModule
0x18003d7a1  call    cs:__imp_GetProcAddress
0x18003d7a8  nop     dword ptr [rax+rax+00h]
0x18003d7ad  lea     rdx, aFindnextfilena; "FindNextFileNameW"
0x18003d7b4  mov     rcx, rbx; hModule
0x18003d7b7  mov     cs:g_FindFirstFileName, rax
0x18003d7be  call    cs:__imp_GetProcAddress
0x18003d7c5  nop     dword ptr [rax+rax+00h]
0x18003d7ca  mov     cs:g_FindNextFileName, rax
0x18003d7d1  jmp     short loc_18003D7DA
0x18003d7d3  mov     rax, cs:g_FindNextFileName
0x18003d7da  xor     ebx, ebx
0x18003d7dc  cmp     cs:g_FindFirstFileName, rbx
0x18003d7e3  jz      loc_18003D9F9
0x18003d7e9  test    rax, rax
0x18003d7ec  jz      loc_18003D9F9
0x18003d7f2  cmp     [rsp+10100h+var_10098], rbx
0x18003d7f7  jz      loc_18003D9F9
0x18003d7fd  xor     edx, edx; Val
0x18003d7ff  lea     rcx, [rbp+10000h+Buffer]; void *
0x18003d803  mov     r8d, 10000h; Size
0x18003d809  call    memset_0
0x18003d80e  xor     r9d, r9d; lpFilePart
0x18003d811  lea     r8, [rbp+10000h+Buffer]; lpBuffer
0x18003d815  mov     edx, 8000h; nBufferLength
0x18003d81a  mov     rcx, r14; lpFileName
0x18003d81d  call    cs:__imp_GetFullPathNameW
0x18003d824  nop     dword ptr [rax+rax+00h]
0x18003d829  mov     [rsp+10100h+var_100BC], eax
0x18003d82d  test    eax, eax
0x18003d82f  jz      loc_18003D9D5
0x18003d835  movzx   eax, [rbp+10000h+Buffer]
0x18003d839  cmp     ax, 5Ch ; '\'
0x18003d83d  jnz     short loc_18003D86B
0x18003d83f  cmp     [rbp+10000h+var_1003E], ax
0x18003d843  jnz     short loc_18003D874
0x18003d845  cmp     [rbp+10000h+var_1003C], 3Fh ; '?'
0x18003d84a  jnz     loc_18003D9D5
0x18003d850  cmp     [rbp+10000h+var_1003A], ax
0x18003d854  jnz     loc_18003D9D5
0x18003d85a  cmp     [rbp+10000h+var_10038], bx
0x18003d85e  jz      loc_18003D9D5
0x18003d864  cmp     [rbp+10000h+var_10036], 3Ah ; ':'
0x18003d869  jmp     short loc_18003D879
0x18003d86b  test    ax, ax
0x18003d86e  jz      loc_18003D9D5
0x18003d874  cmp     [rbp+10000h+var_1003E], 3Ah ; ':'
0x18003d879  jnz     loc_18003D9D5
0x18003d87f  lea     rcx, [rbp+10000h+Buffer]
0x18003d883  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d887  inc     rax
0x18003d88a  cmp     [rcx+rax*2], bx
0x18003d88e  jnz     short loc_18003D887
0x18003d890  mov     rcx, gs:60h
0x18003d899  inc     eax
0x18003d89b  mov     edx, 8; Flags
0x18003d8a0  mov     r12d, eax
0x18003d8a3  mov     rcx, [rcx+30h]; HeapHandle
0x18003d8a7  lea     r8, [rax+rax]; Size
0x18003d8ab  call    cs:__imp_RtlAllocateHeap
0x18003d8b2  nop     dword ptr [rax+rax+00h]
0x18003d8b7  mov     rbx, rax
0x18003d8ba  test    rax, rax
0x18003d8bd  jz      loc_18003D9B0
0x18003d8c3  lea     r8, [rbp+10000h+Buffer]; unsigned __int16 *
0x18003d8c7  mov     edx, r12d; unsigned __int64
0x18003d8ca  mov     rcx, rax; unsigned __int16 *
0x18003d8cd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d8d2  mov     r12d, eax
0x18003d8d5  test    eax, eax
0x18003d8d7  jns     short loc_18003D90B
0x18003d8d9  mov     rcx, gs:60h
0x18003d8e2  mov     r8, rbx; P
0x18003d8e5  xor     edx, edx; Flags
0x18003d8e7  mov     rcx, [rcx+30h]; HeapHandle
0x18003d8eb  call    cs:__imp_RtlFreeHeap
0x18003d8f2  nop     dword ptr [rax+rax+00h]
0x18003d8f7  xor     eax, eax
0x18003d8f9  movzx   ecx, r12w
0x18003d8fd  mov     ebx, eax
0x18003d8ff  mov     rax, gs:30h
0x18003d908  mov     [rax+68h], ecx
0x18003d90b  test    rbx, rbx
0x18003d90e  jz      loc_18003D9B0
0x18003d914  mov     rax, cs:g_FindFirstFileName
0x18003d91b  lea     r9, [rbp+10000h+var_1003C]
0x18003d91f  lea     r8, [rsp+10100h+var_100BC]
0x18003d924  mov     [rsp+10100h+var_100BC], 7FFCh
0x18003d92c  xor     edx, edx
0x18003d92e  mov     rcx, r14
0x18003d931  call    cs:__guard_dispatch_icall_fptr
0x18003d937  mov     r12, rax
0x18003d93a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d93e  jz      short loc_18003D98E
0x18003d940  mov     rdx, rbx; String2
0x18003d943  lea     rcx, [rbp+10000h+Buffer]; String1
0x18003d947  call    _wcsicmp_0
0x18003d94c  test    eax, eax
0x18003d94e  jnz     short loc_18003D977
0x18003d950  mov     rax, cs:g_FindNextFileName
0x18003d957  lea     r8, [rbp+10000h+var_1003C]
0x18003d95b  lea     rdx, [rsp+10100h+var_100BC]
0x18003d960  mov     [rsp+10100h+var_100BC], 7FFCh
0x18003d968  mov     rcx, r12
0x18003d96b  call    cs:__guard_dispatch_icall_fptr
0x18003d971  test    eax, eax
0x18003d973  jz      short loc_18003D97F
0x18003d975  jmp     short loc_18003D940
0x18003d977  mov     [rsp+10100h+var_100B0], 1
0x18003d97f  mov     rcx, r12; hFindFile
0x18003d982  call    cs:__imp_FindClose
0x18003d989  nop     dword ptr [rax+rax+00h]
0x18003d98e  call    cs:__imp_GetProcessHeap
0x18003d995  nop     dword ptr [rax+rax+00h]
0x18003d99a  mov     r8, rbx; lpMem
0x18003d99d  xor     edx, edx; dwFlags
0x18003d99f  mov     rcx, rax; hHeap
0x18003d9a2  call    cs:__imp_HeapFree
0x18003d9a9  nop     dword ptr [rax+rax+00h]
0x18003d9ae  jmp     short loc_18003D9D0
0x18003d9b0  call    cs:__imp_GetLastError
0x18003d9b7  nop     dword ptr [rax+rax+00h]
0x18003d9bc  lea     r8, aDeletefileexUn_0; "DeleteFileEx: Unable to allocate memory"...
0x18003d9c3  mov     edx, esi
0x18003d9c5  mov     r9d, eax
0x18003d9c8  mov     rcx, rdi
0x18003d9cb  call    LibLog
0x18003d9d0  mov     r12d, r15d
0x18003d9d3  jmp     short loc_18003D9F9
0x18003d9d5  call    cs:__imp_GetLastError
0x18003d9dc  nop     dword ptr [rax+rax+00h]
0x18003d9e1  mov     r9, r14
0x18003d9e4  lea     r8, aDeletefileexUn_2; "DeleteFileEx: Unable to get full path n"...
0x18003d9eb  mov     edx, esi
0x18003d9ed  mov     [rsp+10100h+dwCreationDisposition], eax
0x18003d9f1  mov     rcx, rdi
0x18003d9f4  call    LibLog
0x18003d9f9  mov     r9d, 1; Length
0x18003d9ff  mov     [rsp+10100h+dwCreationDisposition], 0Dh; FileInformationClass
0x18003da07  lea     r8, [rsp+10100h+var_100C0]; FileInformation
0x18003da0c  mov     rcx, r13; FileHandle
0x18003da0f  lea     rdx, [rsp+10100h+IoStatusBlock]; IoStatusBlock
0x18003da14  call    cs:__imp_NtSetInformationFile
0x18003da1b  nop     dword ptr [rax+rax+00h]
0x18003da20  mov     ebx, eax
0x18003da22  test    eax, eax
0x18003da24  jns     short loc_18003DA8C
0x18003da26  mov     r9d, 4; Length
0x18003da2c  mov     [rsp+10100h+var_100AC], 1
0x18003da34  lea     r8, [rsp+10100h+var_100AC]; FileInformation
0x18003da39  mov     [rsp+10100h+dwCreationDisposition], 40h ; '@'; FileInformationClass
0x18003da41  lea     rdx, [rsp+10100h+IoStatusBlock]; IoStatusBlock
0x18003da46  mov     rcx, r13; FileHandle
0x18003da49  call    cs:__imp_NtSetInformationFile
0x18003da50  nop     dword ptr [rax+rax+00h]
0x18003da55  test    eax, eax
0x18003da57  jns     short loc_18003DA8C
0x18003da59  cmp     eax, 0C0000003h
0x18003da5e  cmovnz  ebx, eax
0x18003da61  mov     ecx, ebx; Status
0x18003da63  call    cs:__imp_RtlNtStatusToDosError
0x18003da6a  nop     dword ptr [rax+rax+00h]
0x18003da6f  mov     r9, r14
0x18003da72  lea     r8, aDeletefileexUn_1; "DeleteFileEx: Unable to remove [%s]; GL"...
0x18003da79  mov     edx, esi
0x18003da7b  mov     [rsp+10100h+dwCreationDisposition], eax
0x18003da7f  mov     rcx, rdi
0x18003da82  mov     r15d, eax
0x18003da85  call    LibLog
0x18003da8a  jmp     short loc_18003DA92
0x18003da8c  mov     r12d, 1
0x18003da92  cmp     [rsp+10100h+var_100B0], 0
0x18003da97  jz      short loc_18003DB14
0x18003da99  xor     edx, edx
0x18003da9b  lea     rcx, [rbp+10000h+Buffer]; unsigned __int16 *
0x18003da9f  call    PrepareUnicodePath
0x18003daa4  test    byte ptr [rsp+10100h+var_100A8], 4
0x18003daa9  mov     rbx, rax
0x18003daac  jnz     short loc_18003DADC
0x18003daae  mov     esi, 4000000h
0x18003dab3  lea     r9, [rbp+10000h+Buffer]
0x18003dab7  mov     edx, esi
0x18003dab9  lea     r8, aDeletefileexHa; "DeleteFileEx: hardlink given to us is: "...
0x18003dac0  mov     rcx, rdi
0x18003dac3  call    LibLog
0x18003dac8  mov     r9, rbx
0x18003dacb  lea     r8, aDeletefileexTr; "DeleteFileEx: Trying to set back attrib"...
  ... truncated ...
```
