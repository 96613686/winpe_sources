# DLConvertSidToStringSidW(void *,ushort * *)

- ea: `0x180044070`
- end: `0x1800440e5`
- name: `?DLConvertSidToStringSidW@@YAHPEAXPEAPEAG@Z`
- size: `117`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003e520`
- `0x18003e5a0`

## callees

- `0x180044070`
- `0x180044168`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004409e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004409e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800440b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800440b4`

## string_xrefs

- `0x1800440ad`: `ConvertSidToStringSidW`

## pseudocode

```c
__int64 __fastcall DLConvertSidToStringSidW(void *a1, unsigned __int16 **a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  DWORD SddlDll; // eax

  ProcAddress = (FARPROC)qword_1800703F8;
  if ( qword_1800703F8 )
    return ((unsigned int (__fastcall *)(void *, unsigned __int16 **))ProcAddress)(a1, a2);
  v5 = 0;
  SddlDll = DLpLoadSddlDll();
  if ( !SddlDll )
  {
    ProcAddress = GetProcAddress(g_hInstSddlDLL, "ConvertSidToStringSidW");
    qword_1800703F8 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v5;
    return ((unsigned int (__fastcall *)(void *, unsigned __int16 **))ProcAddress)(a1, a2);
  }
  SetLastError(SddlDll);
  return v5;
}

```

## disassembly

```asm
0x180044070  mov     [rsp+arg_0], rbx
0x180044075  mov     [rsp+arg_8], rsi
0x18004407a  push    rdi
0x18004407b  sub     rsp, 20h
0x18004407f  mov     rax, cs:qword_1800703F8
0x180044086  mov     rdi, rdx
0x180044089  mov     rsi, rcx
0x18004408c  test    rax, rax
0x18004408f  jnz     short loc_1800440C6
0x180044091  xor     ebx, ebx
0x180044093  call    ?DLpLoadSddlDll@@YAKXZ; DLpLoadSddlDll(void)
0x180044098  test    eax, eax
0x18004409a  jz      short loc_1800440A6
0x18004409c  mov     ecx, eax; dwErrCode
0x18004409e  call    cs:__imp_SetLastError
0x1800440a4  jmp     short loc_1800440D3
0x1800440a6  mov     rcx, cs:?g_hInstSddlDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800440ad  lea     rdx, aConvertsidtost; "ConvertSidToStringSidW"
0x1800440b4  call    cs:__imp_GetProcAddress
0x1800440ba  mov     cs:qword_1800703F8, rax
0x1800440c1  test    rax, rax
0x1800440c4  jz      short loc_1800440D3
0x1800440c6  mov     rdx, rdi
0x1800440c9  mov     rcx, rsi
0x1800440cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440d1  mov     ebx, eax
0x1800440d3  mov     rsi, [rsp+28h+arg_8]
0x1800440d8  mov     eax, ebx
0x1800440da  mov     rbx, [rsp+28h+arg_0]
0x1800440df  add     rsp, 20h
0x1800440e3  pop     rdi
0x1800440e4  retn
```
