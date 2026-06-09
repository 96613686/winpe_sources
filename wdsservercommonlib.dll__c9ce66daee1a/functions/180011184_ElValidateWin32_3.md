# ElValidateWin32_3

- ea: `0x180011184`
- end: `0x18001124d`
- name: `ElValidateWin32_3`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010300`
- `0x180010620`
- `0x1800109f0`

## callees

- `0x180011184`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001122e`
- `KERNEL32!SetLastError` at `0x18001122e`
- `KERNEL32!GetLastError` at `0x1800111aa`
- `KERNEL32!GetLastError` at `0x1800111f6`
- `KERNEL32!GetLastError` at `0x1800111aa`
- `KERNEL32!GetLastError` at `0x1800111f6`

## string_xrefs

- `0x1800111c6`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`
- `0x18001120f`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_3(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
        a4,
        &dword_1800331C4,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
        a4,
        &dword_1800331C4,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011184  mov     [rsp+arg_0], rbx
0x180011189  mov     [rsp+arg_8], rsi
0x18001118e  push    rdi
0x18001118f  sub     rsp, 40h
0x180011193  mov     esi, r9d
0x180011196  mov     edi, ecx
0x180011198  test    ecx, ecx
0x18001119a  jz      loc_18001123A
0x1800111a0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800111a8  jz      short loc_1800111EC
0x1800111aa  call    cs:__imp_GetLastError
0x1800111b1  nop     dword ptr [rax+rax+00h]
0x1800111b6  lea     r9, dword_1800331C4
0x1800111bd  mov     [rsp+48h+var_20], edi
0x1800111c1  mov     [rsp+48h+var_28], r9
0x1800111c6  lea     r8, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800111cd  mov     ebx, eax
0x1800111cf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800111d6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800111dd  mov     r9d, esi
0x1800111e0  mov     ecx, 80000h
0x1800111e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ea  jmp     short loc_18001122C
0x1800111ec  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800111f4  jz      short loc_18001123A
0x1800111f6  call    cs:__imp_GetLastError
0x1800111fd  nop     dword ptr [rax+rax+00h]
0x180011202  lea     r9, dword_1800331C4
0x180011209  mov     dword ptr [rsp+48h+var_28], edi
0x18001120d  mov     ebx, eax
0x18001120f  lea     rdx, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180011216  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001121d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180011224  mov     r8d, esi
0x180011227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001122c  mov     ecx, ebx; dwErrCode
0x18001122e  call    cs:__imp_SetLastError
0x180011235  nop     dword ptr [rax+rax+00h]
0x18001123a  mov     rbx, [rsp+48h+arg_0]
0x18001123f  mov     eax, edi
0x180011241  mov     rsi, [rsp+48h+arg_8]
0x180011246  add     rsp, 40h
0x18001124a  pop     rdi
0x18001124b  retn
```
