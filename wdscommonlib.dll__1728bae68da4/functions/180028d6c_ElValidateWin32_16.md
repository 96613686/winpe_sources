# ElValidateWin32_16

- ea: `0x180028d6c`
- end: `0x180028e35`
- name: `ElValidateWin32_16`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028c80`

## callees

- `0x180028d6c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180028e16`
- `KERNEL32!SetLastError` at `0x180028e16`
- `KERNEL32!GetLastError` at `0x180028d92`
- `KERNEL32!GetLastError` at `0x180028dde`
- `KERNEL32!GetLastError` at `0x180028d92`
- `KERNEL32!GetLastError` at `0x180028dde`

## string_xrefs

- `0x180028dae`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`
- `0x180028df7`: `onecore\base\eco\wds\wdslib\common\src\winsockinitializer.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_16(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\winsockinitializer.cpp",
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
0x180028d6c  mov     [rsp+arg_0], rbx
0x180028d71  mov     [rsp+arg_8], rsi
0x180028d76  push    rdi
0x180028d77  sub     rsp, 40h
0x180028d7b  mov     esi, r9d
0x180028d7e  mov     edi, ecx
0x180028d80  test    ecx, ecx
0x180028d82  jz      loc_180028E22
0x180028d88  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028d90  jz      short loc_180028DD4
0x180028d92  call    cs:__imp_GetLastError
0x180028d99  nop     dword ptr [rax+rax+00h]
0x180028d9e  lea     r9, dword_18003572C
0x180028da5  mov     [rsp+48h+var_20], edi
0x180028da9  mov     [rsp+48h+var_28], r9
0x180028dae  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028db5  mov     ebx, eax
0x180028db7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180028dbe  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180028dc5  mov     r9d, esi
0x180028dc8  mov     ecx, 80000h
0x180028dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dd2  jmp     short loc_180028E14
0x180028dd4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028ddc  jz      short loc_180028E22
0x180028dde  call    cs:__imp_GetLastError
0x180028de5  nop     dword ptr [rax+rax+00h]
0x180028dea  lea     r9, dword_18003572C
0x180028df1  mov     dword ptr [rsp+48h+var_28], edi
0x180028df5  mov     ebx, eax
0x180028df7  lea     rdx, aOnecoreBaseEco_27; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028dfe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028e05  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180028e0c  mov     r8d, esi
0x180028e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e14  mov     ecx, ebx; dwErrCode
0x180028e16  call    cs:__imp_SetLastError
0x180028e1d  nop     dword ptr [rax+rax+00h]
0x180028e22  mov     rbx, [rsp+48h+arg_0]
0x180028e27  mov     eax, edi
0x180028e29  mov     rsi, [rsp+48h+arg_8]
0x180028e2e  add     rsp, 40h
0x180028e32  pop     rdi
0x180028e33  retn
```
