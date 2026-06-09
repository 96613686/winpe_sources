# ElValidateWin32_4

- ea: `0x18000ca48`
- end: `0x18000cb11`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c7f8`

## callees

- `0x18000ca48`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ca6e`
- `KERNEL32!GetLastError` at `0x18000caba`
- `KERNEL32!GetLastError` at `0x18000ca6e`
- `KERNEL32!GetLastError` at `0x18000caba`
- `KERNEL32!SetLastError` at `0x18000caf2`
- `KERNEL32!SetLastError` at `0x18000caf2`

## string_xrefs

- `0x18000ca8a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000cad3`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_4(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
        a4,
        qword_18000F3C0,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp",
        a4,
        qword_18000F3C0,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000ca48  mov     [rsp+arg_0], rbx
0x18000ca4d  mov     [rsp+arg_8], rsi
0x18000ca52  push    rdi
0x18000ca53  sub     rsp, 40h
0x18000ca57  mov     esi, r9d
0x18000ca5a  mov     edi, ecx
0x18000ca5c  test    ecx, ecx
0x18000ca5e  jz      loc_18000CAFE
0x18000ca64  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ca6c  jz      short loc_18000CAB0
0x18000ca6e  call    cs:__imp_GetLastError
0x18000ca75  nop     dword ptr [rax+rax+00h]
0x18000ca7a  lea     r9, qword_18000F3C0
0x18000ca81  mov     [rsp+48h+var_20], edi
0x18000ca85  mov     [rsp+48h+var_28], r9
0x18000ca8a  lea     r8, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ca91  mov     ebx, eax
0x18000ca93  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000ca9a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000caa1  mov     r9d, esi
0x18000caa4  mov     ecx, 80000h
0x18000caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caae  jmp     short loc_18000CAF0
0x18000cab0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000cab8  jz      short loc_18000CAFE
0x18000caba  call    cs:__imp_GetLastError
0x18000cac1  nop     dword ptr [rax+rax+00h]
0x18000cac6  lea     r9, qword_18000F3C0
0x18000cacd  mov     dword ptr [rsp+48h+var_28], edi
0x18000cad1  mov     ebx, eax
0x18000cad3  lea     rdx, aBaseEcoWdsLibM_1; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000cada  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000cae1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000cae8  mov     r8d, esi
0x18000caeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caf0  mov     ecx, ebx; dwErrCode
0x18000caf2  call    cs:__imp_SetLastError
0x18000caf9  nop     dword ptr [rax+rax+00h]
0x18000cafe  mov     rbx, [rsp+48h+arg_0]
0x18000cb03  mov     eax, edi
0x18000cb05  mov     rsi, [rsp+48h+arg_8]
0x18000cb0a  add     rsp, 40h
0x18000cb0e  pop     rdi
0x18000cb0f  retn
```
