# _pSpUtilsQueryUnbiasedInterruptTime

- ea: `0x18001802c`
- end: `0x1800180a8`
- name: `_pSpUtilsQueryUnbiasedInterruptTime`
- size: `124`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018248`

## callees

- `0x18001802c`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001804e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001804e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018063`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018063`

## string_xrefs

- `0x180018047`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall pSpUtilsQueryUnbiasedInterruptTime(__int64 a1)
{
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v2 = 1;
  if ( dword_1800238D0 )
  {
    ProcAddress = (FARPROC)qword_1800238C8;
  }
  else
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryUnbiasedInterruptTime");
      qword_1800238C8 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_1800238C8;
    }
    dword_1800238D0 = 1;
  }
  if ( !ProcAddress || !((unsigned int (__fastcall *)(__int64))ProcAddress)(a1) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18001802c  mov     [rsp+arg_0], rbx
0x180018031  push    rdi
0x180018032  sub     rsp, 20h
0x180018036  cmp     cs:dword_1800238D0, 0
0x18001803d  mov     rdi, rcx
0x180018040  mov     ebx, 1
0x180018045  jnz     short loc_180018081
0x180018047  lea     rcx, ModuleName; "ntdll.dll"
0x18001804e  call    cs:__imp_GetModuleHandleW
0x180018054  test    rax, rax
0x180018057  jz      short loc_180018072
0x180018059  lea     rdx, aRtlqueryunbias; "RtlQueryUnbiasedInterruptTime"
0x180018060  mov     rcx, rax; hModule
0x180018063  call    cs:__imp_GetProcAddress
0x180018069  mov     cs:qword_1800238C8, rax
0x180018070  jmp     short loc_180018079
0x180018072  mov     rax, cs:qword_1800238C8
0x180018079  mov     cs:dword_1800238D0, ebx
0x18001807f  jmp     short loc_180018088
0x180018081  mov     rax, cs:qword_1800238C8
0x180018088  test    rax, rax
0x18001808b  jz      short loc_180018099
0x18001808d  mov     rcx, rdi
0x180018090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018095  test    eax, eax
0x180018097  jnz     short loc_18001809B
0x180018099  xor     ebx, ebx
0x18001809b  mov     eax, ebx
0x18001809d  mov     rbx, [rsp+28h+arg_0]
0x1800180a2  add     rsp, 20h
0x1800180a6  pop     rdi
0x1800180a7  retn
```
