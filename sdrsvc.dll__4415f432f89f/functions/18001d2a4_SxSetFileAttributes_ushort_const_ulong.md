# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x18001d2a4`
- end: `0x18001d4d3`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18001cecc`
- `0x18001d154`
- `0x18001dd98`

## callees

- `0x18000ea0c`
- `0x1800150f4`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001c61c`
- `0x18001d2a4`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d49f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d49f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d387`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d387`
- `ntdll!NtSetInformationFile` at `0x18001d477`
- `ntdll!NtSetInformationFile` at `0x18001d477`
- `ntdll!NtQueryInformationFile` at `0x18001d43d`
- `ntdll!NtQueryInformationFile` at `0x18001d43d`

## string_xrefs

- `0x18001d307`: `SxSetFileAttributes`

## pseudocode

```c
__int64 __fastcall SxSetFileAttributes(LPCWSTR lpFileName, int a2)
{
  int LastFailureAsHRESULT; // ebx
  __int64 v5; // rcx
  HANDLE FileW; // rdi
  unsigned int v7; // eax
  __int16 v8; // ax
  unsigned int v9; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-61h]
  int v12; // [rsp+40h] [rbp-49h] BYREF
  __int16 v13; // [rsp+44h] [rbp-45h]
  __int16 v14; // [rsp+46h] [rbp-43h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-11h] BYREF
  _BYTE FileInformation[40]; // [rsp+88h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxSetFileAttributes", 2380, 1);
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = -2147024809;
    v14 = 2386;
    goto LABEL_18;
  }
  v12 = 0;
  v13 = 2386;
  FileW = CreateFileW(lpFileName, 0x180u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v12 = 0;
    v13 = 2395;
    memset(FileInformation, 0, sizeof(FileInformation));
    v7 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    LastFailureAsHRESULT = HRESULTFromNTSTATUS(v7);
    v12 = LastFailureAsHRESULT;
    v8 = 2399;
    if ( LastFailureAsHRESULT >= 0
      && (v13 = 2399,
          *(_DWORD *)&FileInformation[32] = a2 | 0x80,
          v9 = NtSetInformationFile(FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation),
          LastFailureAsHRESULT = HRESULTFromNTSTATUS(v9),
          v12 = LastFailureAsHRESULT,
          v8 = 2405,
          LastFailureAsHRESULT >= 0) )
    {
      v13 = 2405;
    }
    else
    {
      v14 = v8;
    }
LABEL_17:
    CloseHandle(FileW);
    goto LABEL_18;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
  v12 = LastFailureAsHRESULT;
  v14 = 2395;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    LODWORD(dwFlagsAndAttributes) = LastFailureAsHRESULT;
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids,
      (unsigned int)"sh.IsValid()",
      (__int64)lpFileName,
      dwFlagsAndAttributes);
    LastFailureAsHRESULT = v12;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_17;
LABEL_18:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001d2a4  mov     [rsp-8+arg_10], rbx
0x18001d2a9  push    rbp
0x18001d2aa  push    rsi
0x18001d2ab  push    rdi
0x18001d2ac  push    r12
0x18001d2ae  push    r14
0x18001d2b0  lea     rbp, [rsp-37h]
0x18001d2b5  sub     rsp, 0C0h
0x18001d2bc  mov     rax, cs:__security_cookie
0x18001d2c3  xor     rax, rsp
0x18001d2c6  mov     [rbp+57h+var_30], rax
0x18001d2ca  mov     r14d, edx
0x18001d2cd  mov     rsi, rcx
0x18001d2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2d7  lea     r12, WPP_GLOBAL_Control
0x18001d2de  cmp     rcx, r12
0x18001d2e1  jz      short loc_18001D301
0x18001d2e3  test    dword ptr [rcx+1Ch], 20000000h
0x18001d2ea  jz      short loc_18001D301
0x18001d2ec  mov     rcx, [rcx+10h]
0x18001d2f0  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d2f7  mov     edx, 43h ; 'C'
0x18001d2fc  call    WPP_SF_
0x18001d301  mov     r9d, 1; unsigned __int16
0x18001d307  lea     rdx, aSxsetfileattri; "SxSetFileAttributes"
0x18001d30e  mov     r8d, 94Ch; unsigned __int16
0x18001d314  lea     rcx, [rbp+57h+var_A0]; this
0x18001d318  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d31d  xorps   xmm0, xmm0
0x18001d320  mov     dword ptr [rbp+57h+FileInformation], 0
0x18001d327  xor     eax, eax
0x18001d329  mov     [rbp+57h+var_34], eax
0x18001d32c  movups  [rbp+57h+FileInformation+4], xmm0
0x18001d330  movups  [rbp+57h+var_44], xmm0
0x18001d334  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001d338  test    rsi, rsi
0x18001d33b  jnz     short loc_18001D353
0x18001d33d  mov     ebx, 80070057h
0x18001d342  mov     eax, 952h
0x18001d347  mov     [rbp+57h+var_A0], ebx
0x18001d34a  mov     [rbp+57h+var_9A], ax
0x18001d34e  jmp     loc_18001D4A5
0x18001d353  xor     r9d, r9d; lpSecurityAttributes
0x18001d356  mov     [rbp+57h+var_A0], eax
0x18001d359  mov     eax, 952h
0x18001d35e  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x18001d367  mov     dword ptr [rsp+0E0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001d36f  mov     edx, 180h; dwDesiredAccess
0x18001d374  mov     rcx, rsi; lpFileName
0x18001d377  mov     [rbp+57h+var_9C], ax
0x18001d37b  lea     r8d, [r9+7]; dwShareMode
0x18001d37f  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001d387  call    cs:__imp_CreateFileW
0x18001d38d  mov     rdi, rax
0x18001d390  inc     rax
0x18001d393  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001d399  jnz     short loc_18001D403
0x18001d39b  call    GetLastFailureAsHRESULT
0x18001d3a0  mov     ebx, eax
0x18001d3a2  mov     [rbp+57h+var_A0], eax
0x18001d3a5  mov     eax, 95Bh
0x18001d3aa  mov     [rbp+57h+var_9A], ax
0x18001d3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3b5  cmp     rcx, r12
0x18001d3b8  jz      short loc_18001D3EB
0x18001d3ba  test    dword ptr [rcx+1Ch], 2000000h
0x18001d3c1  jz      short loc_18001D3EB
0x18001d3c3  mov     rcx, [rcx+10h]
0x18001d3c7  lea     r9, aShIsvalid; "sh.IsValid()"
0x18001d3ce  mov     edx, 44h ; 'D'
0x18001d3d3  mov     dword ptr [rsp+0E0h+dwFlagsAndAttributes], ebx
0x18001d3d7  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001d3de  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rsi
0x18001d3e3  call    WPP_SF_sSd
0x18001d3e8  mov     ebx, [rbp+57h+var_A0]
0x18001d3eb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001d3ef  jz      loc_18001D4A5
0x18001d3f5  test    rdi, rdi
0x18001d3f8  jz      loc_18001D4A5
0x18001d3fe  jmp     loc_18001D49C
0x18001d403  xorps   xmm0, xmm0
0x18001d406  mov     [rbp+57h+var_A0], 0
0x18001d40d  mov     eax, 95Bh
0x18001d412  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18001d416  mov     [rbp+57h+var_9C], ax
0x18001d41a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001d41e  xor     eax, eax
0x18001d420  mov     rcx, rdi; FileHandle
0x18001d423  movups  [rbp+57h+FileInformation], xmm0
0x18001d427  mov     qword ptr [rbp+57h+var_44+0Ch], rax
0x18001d42b  movups  xmmword ptr [rbp+0Fh], xmm0
0x18001d42f  lea     r12d, [rax+28h]
0x18001d433  lea     esi, [rax+4]
0x18001d436  mov     r9d, r12d; Length
0x18001d439  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18001d43d  call    cs:__imp_NtQueryInformationFile
0x18001d443  mov     ecx, eax
0x18001d445  call    HRESULTFromNTSTATUS
0x18001d44a  mov     ebx, eax
0x18001d44c  mov     [rbp+57h+var_A0], eax
0x18001d44f  test    eax, eax
0x18001d451  mov     eax, 95Fh
0x18001d456  js      short loc_18001D492
0x18001d458  bts     r14d, 7
0x18001d45d  mov     [rbp+57h+var_9C], ax
0x18001d461  mov     r9d, r12d; Length
0x18001d464  mov     dword ptr [rbp+57h+var_44+0Ch], r14d
0x18001d468  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18001d46c  mov     [rsp+0E0h+dwCreationDisposition], esi; FileInformationClass
0x18001d470  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001d474  mov     rcx, rdi; FileHandle
0x18001d477  call    cs:__imp_NtSetInformationFile
0x18001d47d  mov     ecx, eax
0x18001d47f  call    HRESULTFromNTSTATUS
0x18001d484  mov     ebx, eax
0x18001d486  mov     [rbp+57h+var_A0], eax
0x18001d489  test    eax, eax
0x18001d48b  mov     eax, 965h
0x18001d490  jns     short loc_18001D498
0x18001d492  mov     [rbp+57h+var_9A], ax
0x18001d496  jmp     short loc_18001D49C
0x18001d498  mov     [rbp+57h+var_9C], ax
0x18001d49c  mov     rcx, rdi; hObject
0x18001d49f  call    cs:__imp_CloseHandle
0x18001d4a5  lea     rcx, [rbp+57h+var_A0]; this
0x18001d4a9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d4ae  mov     eax, ebx
0x18001d4b0  mov     rcx, [rbp+57h+var_30]
0x18001d4b4  xor     rcx, rsp; StackCookie
0x18001d4b7  call    __security_check_cookie
0x18001d4bc  mov     rbx, [rsp+0E0h+arg_10]
0x18001d4c4  add     rsp, 0C0h
0x18001d4cb  pop     r14
0x18001d4cd  pop     r12
0x18001d4cf  pop     rdi
0x18001d4d0  pop     rsi
0x18001d4d1  pop     rbp
0x18001d4d2  retn
```
