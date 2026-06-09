# IO::Path::FromKnownFolder(_GUID const &)

- ea: `0x140081d38`
- end: `0x140081ec8`
- name: `?FromKnownFolder@Path@IO@@SA?AV12@AEBU_GUID@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400195a8`
- `0x140088c2c`
- `0x14009a234`

## callees

- `0x140005530`
- `0x140006338`
- `0x14000b814`
- `0x140060498`
- `0x140060f58`
- `0x140061570`
- `0x140081c64`
- `0x140081d38`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x140081d6b`
- `KERNEL32!GetCurrentProcess` at `0x140081d6b`
- `KERNEL32!IsWow64Process` at `0x140081d78`
- `KERNEL32!IsWow64Process` at `0x140081d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140081e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140081e5b`
- `SHELL32!SHGetKnownFolderPath` at `0x140081df8`
- `SHELL32!SHGetKnownFolderPath` at `0x140081df8`

## string_xrefs

- `0x140081dcf`: `%CommonProgramW6432%`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IO::Path::FromKnownFolder(__int64 a1, const KNOWNFOLDERID *a2)
{
  HANDLE CurrentProcess; // rax
  const wchar_t *v5; // rdx
  PWSTR *v6; // rax
  __int64 v7; // rdx
  HRESULT v8; // esi
  __int64 v9; // r8
  _BYTE *v10; // rdx
  WINBOOL Wow64Process; // [rsp+30h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-61h] BYREF
  __int64 v14; // [rsp+40h] [rbp-59h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v16; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v17[56]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE *v18; // [rsp+C0h] [rbp+27h]

  v14 = a1;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  IsWow64Process(CurrentProcess, &Wow64Process);
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&FOLDERID_ProgramFilesX64.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)FOLDERID_ProgramFilesX64.Data4
    && Wow64Process )
  {
    v5 = L"%ProgramW6432%";
LABEL_5:
    IO::Path::Expand(a1, v5);
    return a1;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&FOLDERID_ProgramFilesCommonX64.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)FOLDERID_ProgramFilesCommonX64.Data4
    && Wow64Process )
  {
    v5 = L"%CommonProgramW6432%";
    goto LABEL_5;
  }
  pv = 0;
  v6 = (PWSTR *)stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v16, (__int64)&pv);
  v8 = SHGetKnownFolderPath(a2, 0, 0, v6);
  if ( v18 )
  {
    v14 = v16;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v18 + 16LL))(v18, &v14);
    if ( v18 )
    {
      v10 = v17;
      LOBYTE(v10) = v18 != v17;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v18 + 32LL))(v18, v10);
    }
  }
  if ( v8 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF__guid_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v7, v9, a2, v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  std::wstring::wstring(a1, pv);
  if ( pv )
    CoTaskMemFree(pv);
  return a1;
}

```

## disassembly

```asm
0x140081d38  mov     [rsp-8+arg_10], rbx
0x140081d3d  push    rbp
0x140081d3e  push    rsi
0x140081d3f  push    rdi
0x140081d40  lea     rbp, [rsp-47h]
0x140081d45  sub     rsp, 0E0h
0x140081d4c  mov     rax, cs:__security_cookie
0x140081d53  xor     rax, rsp
0x140081d56  mov     [rbp+57h+var_20], rax
0x140081d5a  mov     rdi, rdx
0x140081d5d  mov     rbx, rcx
0x140081d60  mov     [rbp+57h+var_B0], rcx
0x140081d64  mov     [rbp+57h+Wow64Process], 0
0x140081d6b  call    cs:__imp_GetCurrentProcess
0x140081d71  mov     rcx, rax; hProcess
0x140081d74  lea     rdx, [rbp+57h+Wow64Process]; Wow64Process
0x140081d78  call    cs:__imp_IsWow64Process
0x140081d7e  mov     rcx, [rdi]
0x140081d81  mov     edx, [rbp+57h+Wow64Process]
0x140081d84  cmp     rcx, qword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x140081d8b  jnz     short loc_140081DB2
0x140081d8d  mov     rcx, [rdi+8]
0x140081d91  cmp     rcx, qword ptr cs:FOLDERID_ProgramFilesX64.Data4
0x140081d98  jnz     short loc_140081DB2
0x140081d9a  test    edx, edx
0x140081d9c  jz      short loc_140081DB2
0x140081d9e  lea     rdx, aProgramw6432; "%ProgramW6432%"
0x140081da5  mov     rcx, rbx
0x140081da8  call    ?Expand@Path@IO@@SA?AV12@PEBG@Z; IO::Path::Expand(ushort const *)
0x140081dad  jmp     loc_140081E61
0x140081db2  mov     rax, [rdi]
0x140081db5  cmp     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data1
0x140081dbc  jnz     short loc_140081DD8
0x140081dbe  mov     rax, [rdi+8]
0x140081dc2  cmp     rax, qword ptr cs:FOLDERID_ProgramFilesCommonX64.Data4
0x140081dc9  jnz     short loc_140081DD8
0x140081dcb  test    edx, edx
0x140081dcd  jz      short loc_140081DD8
0x140081dcf  lea     rdx, aCommonprogramw; "%CommonProgramW6432%"
0x140081dd6  jmp     short loc_140081DA5
0x140081dd8  mov     [rbp+57h+pv], 0
0x140081de0  lea     rdx, [rbp+57h+pv]
0x140081de4  lea     rcx, [rbp+57h+var_70]
0x140081de8  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x140081ded  mov     r9, rax; ppszPath
0x140081df0  xor     r8d, r8d; hToken
0x140081df3  xor     edx, edx; dwFlags
0x140081df5  mov     rcx, rdi; rfid
0x140081df8  call    cs:__imp_SHGetKnownFolderPath
0x140081dfe  mov     esi, eax
0x140081e00  mov     rcx, [rbp+57h+var_30]
0x140081e04  test    rcx, rcx
0x140081e07  jz      short loc_140081E41
0x140081e09  mov     rdx, [rbp+57h+var_70]
0x140081e0d  mov     [rbp+57h+var_B0], rdx
0x140081e11  mov     rdx, [rcx]
0x140081e14  mov     rax, [rdx+10h]
0x140081e18  lea     rdx, [rbp+57h+var_B0]
0x140081e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081e21  mov     rcx, [rbp+57h+var_30]
0x140081e25  test    rcx, rcx
0x140081e28  jz      short loc_140081E41
0x140081e2a  mov     rax, [rcx]
0x140081e2d  lea     rdx, [rbp+57h+var_68]
0x140081e31  cmp     rcx, rdx
0x140081e34  setnz   dl
0x140081e37  mov     rax, [rax+20h]
0x140081e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081e40  nop
0x140081e41  test    esi, esi
0x140081e43  js      short loc_140081E83
0x140081e45  mov     rdx, [rbp+57h+pv]
0x140081e49  mov     rcx, rbx
0x140081e4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140081e51  nop
0x140081e52  mov     rcx, [rbp+57h+pv]; pv
0x140081e56  test    rcx, rcx
0x140081e59  jz      short loc_140081E61
0x140081e5b  call    cs:__imp_CoTaskMemFree
0x140081e61  mov     rax, rbx
0x140081e64  mov     rcx, [rbp+57h+var_20]
0x140081e68  xor     rcx, rsp; StackCookie
0x140081e6b  call    __security_check_cookie
0x140081e70  mov     rbx, [rsp+0F0h+arg_10]
0x140081e78  add     rsp, 0E0h
0x140081e7f  pop     rdi
0x140081e80  pop     rsi
0x140081e81  pop     rbp
0x140081e82  retn
0x140081e83  lea     rax, WPP_GLOBAL_Control
0x140081e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140081e91  cmp     rcx, rax
0x140081e94  jz      short loc_140081EAC
0x140081e96  test    byte ptr [rcx+1Ch], 1
0x140081e9a  jz      short loc_140081EAC
0x140081e9c  mov     [rsp+0F0h+var_D0], esi
0x140081ea0  mov     r9, rdi
0x140081ea3  mov     rcx, [rcx+10h]
0x140081ea7  call    WPP_SF__guid_d
0x140081eac  mov     edx, esi; int
0x140081eae  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140081eb2  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140081eb7  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140081ebe  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140081ec2  call    _CxxThrowException_0
```
