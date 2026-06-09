# ElValidateWin32_7

- ea: `0x180018444`
- end: `0x18001850d`
- name: `ElValidateWin32_7`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017540`
- `0x180017720`
- `0x180017aa0`
- `0x180017c10`
- `0x180017df0`
- `0x180017eb0`
- `0x180018260`

## callees

- `0x180018444`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800184ee`
- `KERNEL32!SetLastError` at `0x1800184ee`
- `KERNEL32!GetLastError` at `0x18001846a`
- `KERNEL32!GetLastError` at `0x1800184b6`
- `KERNEL32!GetLastError` at `0x18001846a`
- `KERNEL32!GetLastError` at `0x1800184b6`

## string_xrefs

- `0x180018486`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`
- `0x1800184cf`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_7(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
        a4,
        &dword_18003572C,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp",
        a4,
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180018444  mov     [rsp+arg_0], rbx
0x180018449  mov     [rsp+arg_8], rsi
0x18001844e  push    rdi
0x18001844f  sub     rsp, 40h
0x180018453  mov     esi, r9d
0x180018456  mov     edi, ecx
0x180018458  test    ecx, ecx
0x18001845a  jz      loc_1800184FA
0x180018460  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180018468  jz      short loc_1800184AC
0x18001846a  call    cs:__imp_GetLastError
0x180018471  nop     dword ptr [rax+rax+00h]
0x180018476  lea     r9, dword_18003572C
0x18001847d  mov     [rsp+48h+var_20], edi
0x180018481  mov     [rsp+48h+var_28], r9
0x180018486  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001848d  mov     ebx, eax
0x18001848f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180018496  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001849d  mov     r9d, esi
0x1800184a0  mov     ecx, 80000h
0x1800184a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184aa  jmp     short loc_1800184EC
0x1800184ac  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800184b4  jz      short loc_1800184FA
0x1800184b6  call    cs:__imp_GetLastError
0x1800184bd  nop     dword ptr [rax+rax+00h]
0x1800184c2  lea     r9, dword_18003572C
0x1800184c9  mov     dword ptr [rsp+48h+var_28], edi
0x1800184cd  mov     ebx, eax
0x1800184cf  lea     rdx, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800184d6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800184dd  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800184e4  mov     r8d, esi
0x1800184e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ec  mov     ecx, ebx; dwErrCode
0x1800184ee  call    cs:__imp_SetLastError
0x1800184f5  nop     dword ptr [rax+rax+00h]
0x1800184fa  mov     rbx, [rsp+48h+arg_0]
0x1800184ff  mov     eax, edi
0x180018501  mov     rsi, [rsp+48h+arg_8]
0x180018506  add     rsp, 40h
0x18001850a  pop     rdi
0x18001850b  retn
```
