# TestQueryData

- ea: `0x180003ae0`
- end: `0x180003b7c`
- name: `TestQueryData`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005848`
- `0x180005d48`
- `0x18000ddc4`

## callees

- `0x180003ae0`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003b1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003b1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003b35`

## string_xrefs

- `0x180003b17`: `kernelbase.dll`

## pseudocode

```c
FARPROC __fastcall TestQueryData(__int64 a1, unsigned int a2, unsigned int a3, _OWORD *a4)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    return (FARPROC)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _OWORD *))result)(a1, a2, a3, a4);
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _OWORD *))result)(a1, a2, a3, a4);
  *a4 = 0;
  a4[1] = 0;
  a4[2] = 0;
  return result;
}

```

## disassembly

```asm
0x180003ae0  mov     [rsp+arg_0], rbx
0x180003ae5  mov     [rsp+arg_8], rbp
0x180003aea  mov     [rsp+arg_10], rsi
0x180003aef  push    rdi
0x180003af0  sub     rsp, 30h
0x180003af4  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180003afb  mov     rbx, r9
0x180003afe  mov     edi, r8d
0x180003b01  mov     esi, edx
0x180003b03  mov     rbp, rcx
0x180003b06  test    rax, rax
0x180003b09  jnz     short loc_180003B57
0x180003b0b  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180003b12  test    rax, rax
0x180003b15  jnz     short loc_180003B2B
0x180003b17  lea     rcx, ModuleName; "kernelbase.dll"
0x180003b1e  call    cs:__imp_GetModuleHandleW
0x180003b24  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180003b2b  lea     rdx, ProcName; "TestQueryData"
0x180003b32  mov     rcx, rax; hModule
0x180003b35  call    cs:__imp_GetProcAddress
0x180003b3b  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180003b42  test    rax, rax
0x180003b45  jnz     short loc_180003B57
0x180003b47  xorps   xmm0, xmm0
0x180003b4a  movups  xmmword ptr [rbx], xmm0
0x180003b4d  movups  xmmword ptr [rbx+10h], xmm0
0x180003b51  movups  xmmword ptr [rbx+20h], xmm0
0x180003b55  jmp     short loc_180003B67
0x180003b57  mov     r9, rbx
0x180003b5a  mov     r8d, edi
0x180003b5d  mov     edx, esi
0x180003b5f  mov     rcx, rbp
0x180003b62  call    _guard_dispatch_icall
0x180003b67  mov     rbx, [rsp+38h+arg_0]
0x180003b6c  mov     rbp, [rsp+38h+arg_8]
0x180003b71  mov     rsi, [rsp+38h+arg_10]
0x180003b76  add     rsp, 30h
0x180003b7a  pop     rdi
0x180003b7b  retn
```
