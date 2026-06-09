# CMmcssTask::LoadRuntime(void)

- ea: `0x1801dfc10`
- end: `0x1801dfd7c`
- name: `?LoadRuntime@CMmcssTask@@AEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(CMmcssTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18000a810`

## callees

- `0x180042de0`
- `0x1801dfc10`
- `0x180231c34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcf2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801dfcf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfc9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfcbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfce1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfc26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfc9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfcbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dfce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dfd53`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801dfc33`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801dfc33`

## string_xrefs

- `0x1801dfc2c`: `avrt.dll`
- `0x1801dfca7`: `AvRevertMmThreadCharacteristics`
- `0x1801dfceb`: `AvSetMmThreadPriority`
- `0x1801dfcc9`: `AvSetMmThreadCharacteristicsW`

## pseudocode

```c
__int64 __fastcall CMmcssTask::LoadRuntime(CMmcssTask *this)
{
  HMODULE LibraryW; // rax
  signed int v3; // eax
  signed int v4; // ebx
  unsigned int v5; // eax
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  signed int v10; // eax
  signed int LastError; // eax
  signed int v12; // eax

  if ( *((_QWORD *)this + 6) )
    return 0;
  SetLastError(0);
  LibraryW = LoadLibraryW(L"avrt.dll");
  *((_QWORD *)this + 6) = LibraryW;
  if ( LibraryW )
  {
    SetLastError(0);
    ProcAddress = GetProcAddress(*((HMODULE *)this + 6), "AvRevertMmThreadCharacteristics");
    *((_QWORD *)this + 8) = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 333;
      goto LABEL_8;
    }
    SetLastError(0);
    v8 = GetProcAddress(*((HMODULE *)this + 6), "AvSetMmThreadCharacteristicsW");
    *((_QWORD *)this + 7) = v8;
    if ( !v8 )
    {
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 335;
      goto LABEL_8;
    }
    SetLastError(0);
    v9 = GetProcAddress(*((HMODULE *)this + 6), "AvSetMmThreadPriority");
    *((_QWORD *)this + 9) = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 337;
      goto LABEL_8;
    }
    return 0;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
    v4 = -2003304445;
  v5 = 330;
LABEL_8:
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v4, v5, 0);
  CMmcssTask::UnloadRuntime(this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801dfc10  mov     [rsp+arg_0], rbx
0x1801dfc15  push    rdi
0x1801dfc16  sub     rsp, 30h
0x1801dfc1a  cmp     qword ptr [rcx+30h], 0
0x1801dfc1f  mov     rdi, rcx
0x1801dfc22  jnz     short loc_1801DFC8C
0x1801dfc24  xor     ecx, ecx; dwErrCode
0x1801dfc26  call    cs:__imp_SetLastError
0x1801dfc2c  lea     rcx, aAvrtDll; "avrt.dll"
0x1801dfc33  call    cs:__imp_LoadLibraryW
0x1801dfc39  mov     [rdi+30h], rax
0x1801dfc3d  test    rax, rax
0x1801dfc40  jnz     short loc_1801DFC9B
0x1801dfc42  call    cs:__imp_GetLastError
0x1801dfc48  mov     ebx, eax
0x1801dfc4a  test    eax, eax
0x1801dfc4c  jle     short loc_1801DFC57
0x1801dfc4e  movzx   ebx, ax
0x1801dfc51  or      ebx, 80070000h
0x1801dfc57  mov     eax, 88980003h
0x1801dfc5c  test    ebx, ebx
0x1801dfc5e  cmovns  ebx, eax
0x1801dfc61  mov     eax, 14Ah
0x1801dfc66  xor     edx, edx; int *
0x1801dfc68  xor     r10d, r10d
0x1801dfc6b  mov     [rsp+38h+var_10], r10; void *
0x1801dfc70  xor     r8d, r8d; unsigned int
0x1801dfc73  mov     r9d, ebx; int
0x1801dfc76  mov     [rsp+38h+var_18], eax; unsigned int
0x1801dfc7a  lea     ecx, [rdx+14h]; unsigned int
0x1801dfc7d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801dfc82  mov     rcx, rdi; this
0x1801dfc85  call    ?UnloadRuntime@CMmcssTask@@AEAAXXZ; CMmcssTask::UnloadRuntime(void)
0x1801dfc8a  jmp     short loc_1801DFC8E
0x1801dfc8c  xor     ebx, ebx
0x1801dfc8e  mov     eax, ebx
0x1801dfc90  mov     rbx, [rsp+38h+arg_0]
0x1801dfc95  add     rsp, 30h
0x1801dfc99  pop     rdi
0x1801dfc9a  retn
0x1801dfc9b  xor     ecx, ecx; dwErrCode
0x1801dfc9d  call    cs:__imp_SetLastError
0x1801dfca3  mov     rcx, [rdi+30h]; hModule
0x1801dfca7  lea     rdx, aAvrevertmmthre; "AvRevertMmThreadCharacteristics"
0x1801dfcae  call    cs:__imp_GetProcAddress
0x1801dfcb4  mov     [rdi+40h], rax
0x1801dfcb8  test    rax, rax
0x1801dfcbb  jz      short loc_1801DFD2A
0x1801dfcbd  xor     ecx, ecx; dwErrCode
0x1801dfcbf  call    cs:__imp_SetLastError
0x1801dfcc5  mov     rcx, [rdi+30h]; hModule
0x1801dfcc9  lea     rdx, aAvsetmmthreadc; "AvSetMmThreadCharacteristicsW"
0x1801dfcd0  call    cs:__imp_GetProcAddress
0x1801dfcd6  mov     [rdi+38h], rax
0x1801dfcda  test    rax, rax
0x1801dfcdd  jz      short loc_1801DFD53
0x1801dfcdf  xor     ecx, ecx; dwErrCode
0x1801dfce1  call    cs:__imp_SetLastError
0x1801dfce7  mov     rcx, [rdi+30h]; hModule
0x1801dfceb  lea     rdx, aAvsetmmthreadp; "AvSetMmThreadPriority"
0x1801dfcf2  call    cs:__imp_GetProcAddress
0x1801dfcf8  mov     [rdi+48h], rax
0x1801dfcfc  test    rax, rax
0x1801dfcff  jnz     short loc_1801DFC8C
0x1801dfd01  call    cs:__imp_GetLastError
0x1801dfd07  mov     ebx, eax
0x1801dfd09  test    eax, eax
0x1801dfd0b  jle     short loc_1801DFD16
0x1801dfd0d  movzx   ebx, ax
0x1801dfd10  or      ebx, 80070000h
0x1801dfd16  mov     eax, 88980003h
0x1801dfd1b  test    ebx, ebx
0x1801dfd1d  cmovns  ebx, eax
0x1801dfd20  mov     eax, 151h
0x1801dfd25  jmp     loc_1801DFC66
0x1801dfd2a  call    cs:__imp_GetLastError
0x1801dfd30  mov     ebx, eax
0x1801dfd32  test    eax, eax
0x1801dfd34  jle     short loc_1801DFD3F
0x1801dfd36  movzx   ebx, ax
0x1801dfd39  or      ebx, 80070000h
0x1801dfd3f  mov     eax, 88980003h
0x1801dfd44  test    ebx, ebx
0x1801dfd46  cmovns  ebx, eax
0x1801dfd49  mov     eax, 14Dh
0x1801dfd4e  jmp     loc_1801DFC66
0x1801dfd53  call    cs:__imp_GetLastError
0x1801dfd59  mov     ebx, eax
0x1801dfd5b  test    eax, eax
0x1801dfd5d  jle     short loc_1801DFD68
0x1801dfd5f  movzx   ebx, ax
0x1801dfd62  or      ebx, 80070000h
0x1801dfd68  mov     eax, 88980003h
0x1801dfd6d  test    ebx, ebx
0x1801dfd6f  cmovns  ebx, eax
0x1801dfd72  mov     eax, 14Fh
0x1801dfd77  jmp     loc_1801DFC66
```
