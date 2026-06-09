# ScExtSendServiceShutdownMessage

- ea: `0x14002e550`
- end: `0x14002e6a2`
- name: `ScExtSendServiceShutdownMessage`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x140004c58`
- `0x14002e550`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002e602`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002e602`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002e594`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002e594`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002e662`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002e662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e5d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002e63a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e5a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e61b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e673`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e5a9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e61b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14002e673`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14002e574`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14002e574`

## string_xrefs

- `0x14002e58b`: `WMsgApi.dll`

## pseudocode

```c
__int64 __fastcall ScExtSendServiceShutdownMessage(__int64 a1)
{
  __int64 (__fastcall *v1)(_QWORD, __int64, __int64, __int64); // rax
  HMODULE Library; // rax
  HMODULE v4; // rbx
  DWORD LastError; // eax
  DWORD v6; // eax

  v1 = (__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))qword_1400BCA70;
  if ( qword_1400BCA70 )
    goto LABEL_13;
  RtlAcquireSRWLockExclusive(&g_Lock);
  if ( qword_1400BCA70 )
    goto LABEL_12;
  Library = LoadLibraryExW(L"WMsgApi.dll", 0, 0);
  v4 = Library;
  if ( !Library )
  {
    RtlReleaseSRWLockExclusive(&g_Lock);
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 46, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, LastError);
    }
    return (unsigned int)v4;
  }
  qword_1400BCA70 = (__int64)GetProcAddress(Library, "WmsgPostNotifyMessage");
  if ( qword_1400BCA70 )
  {
LABEL_12:
    RtlReleaseSRWLockExclusive(&g_Lock);
    v1 = (__int64 (__fastcall *)(_QWORD, __int64, __int64, __int64))qword_1400BCA70;
LABEL_13:
    LODWORD(v4) = v1(0, 768, 48, a1);
    return (unsigned int)v4;
  }
  RtlReleaseSRWLockExclusive(&g_Lock);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    v6 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 47, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, v6);
  }
  FreeLibrary(v4);
  LODWORD(v4) = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002e550  mov     [rsp+arg_0], rbx
0x14002e555  push    rdi
0x14002e556  sub     rsp, 30h
0x14002e55a  mov     rax, cs:qword_1400BCA70
0x14002e561  mov     rdi, rcx
0x14002e564  test    rax, rax
0x14002e567  jnz     loc_14002E680
0x14002e56d  lea     rcx, ?g_Lock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_Lock
0x14002e574  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14002e57a  cmp     cs:qword_1400BCA70, 0
0x14002e582  jnz     loc_14002E66C
0x14002e588  xor     r8d, r8d; dwFlags
0x14002e58b  lea     rcx, aWmsgapiDll; "WMsgApi.dll"
0x14002e592  xor     edx, edx; hFile
0x14002e594  call    cs:__imp_LoadLibraryExW
0x14002e59a  mov     rbx, rax
0x14002e59d  test    rax, rax
0x14002e5a0  jnz     short loc_14002E5F8
0x14002e5a2  lea     rcx, ?g_Lock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_Lock
0x14002e5a9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14002e5af  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5b6  lea     rax, WPP_GLOBAL_Control
0x14002e5bd  cmp     rcx, rax
0x14002e5c0  jz      loc_14002E695
0x14002e5c6  test    byte ptr [rcx+1Ch], 1
0x14002e5ca  jz      loc_14002E695
0x14002e5d0  call    cs:__imp_GetLastError
0x14002e5d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e5dd  lea     edx, [rbx+2Eh]
0x14002e5e0  mov     r9d, eax
0x14002e5e3  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14002e5ea  mov     rcx, [rcx+10h]
0x14002e5ee  call    WPP_SF_d
0x14002e5f3  jmp     loc_14002E695
0x14002e5f8  lea     rdx, aWmsgpostnotify; "WmsgPostNotifyMessage"
0x14002e5ff  mov     rcx, rbx; hModule
0x14002e602  call    cs:__imp_GetProcAddress
0x14002e608  mov     cs:qword_1400BCA70, rax
0x14002e60f  test    rax, rax
0x14002e612  jnz     short loc_14002E66C
0x14002e614  lea     rcx, ?g_Lock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_Lock
0x14002e61b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14002e621  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e628  lea     rax, WPP_GLOBAL_Control
0x14002e62f  cmp     rcx, rax
0x14002e632  jz      short loc_14002E65F
0x14002e634  test    byte ptr [rcx+1Ch], 1
0x14002e638  jz      short loc_14002E65F
0x14002e63a  call    cs:__imp_GetLastError
0x14002e640  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e647  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14002e64e  mov     edx, 2Fh ; '/'
0x14002e653  mov     r9d, eax
0x14002e656  mov     rcx, [rcx+10h]
0x14002e65a  call    WPP_SF_d
0x14002e65f  mov     rcx, rbx; hLibModule
0x14002e662  call    cs:__imp_FreeLibrary
0x14002e668  xor     ebx, ebx
0x14002e66a  jmp     short loc_14002E695
0x14002e66c  lea     rcx, ?g_Lock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_Lock
0x14002e673  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14002e679  mov     rax, cs:qword_1400BCA70
0x14002e680  xor     ecx, ecx
0x14002e682  mov     r9, rdi
0x14002e685  mov     edx, 300h
0x14002e68a  lea     r8d, [rcx+30h]
0x14002e68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e693  mov     ebx, eax
0x14002e695  mov     eax, ebx
0x14002e697  mov     rbx, [rsp+38h+arg_0]
0x14002e69c  add     rsp, 30h
0x14002e6a0  pop     rdi
0x14002e6a1  retn
```
