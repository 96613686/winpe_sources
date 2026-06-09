# ElValidateWin32_20

- ea: `0x18002a080`
- end: `0x18002a149`
- name: `ElValidateWin32_20`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029b00`

## callees

- `0x18002a080`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002a12a`
- `KERNEL32!SetLastError` at `0x18002a12a`
- `KERNEL32!GetLastError` at `0x18002a0a6`
- `KERNEL32!GetLastError` at `0x18002a0f2`
- `KERNEL32!GetLastError` at `0x18002a0a6`
- `KERNEL32!GetLastError` at `0x18002a0f2`

## string_xrefs

- `0x18002a0c2`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`
- `0x18002a10b`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_20(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
0x18002a080  mov     [rsp+arg_0], rbx
0x18002a085  mov     [rsp+arg_8], rsi
0x18002a08a  push    rdi
0x18002a08b  sub     rsp, 40h
0x18002a08f  mov     esi, r9d
0x18002a092  mov     edi, ecx
0x18002a094  test    ecx, ecx
0x18002a096  jz      loc_18002A136
0x18002a09c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002a0a4  jz      short loc_18002A0E8
0x18002a0a6  call    cs:__imp_GetLastError
0x18002a0ad  nop     dword ptr [rax+rax+00h]
0x18002a0b2  lea     r9, dword_18003572C
0x18002a0b9  mov     [rsp+48h+var_20], edi
0x18002a0bd  mov     [rsp+48h+var_28], r9
0x18002a0c2  lea     r8, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a0c9  mov     ebx, eax
0x18002a0cb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002a0d2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002a0d9  mov     r9d, esi
0x18002a0dc  mov     ecx, 80000h
0x18002a0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0e6  jmp     short loc_18002A128
0x18002a0e8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002a0f0  jz      short loc_18002A136
0x18002a0f2  call    cs:__imp_GetLastError
0x18002a0f9  nop     dword ptr [rax+rax+00h]
0x18002a0fe  lea     r9, dword_18003572C
0x18002a105  mov     dword ptr [rsp+48h+var_28], edi
0x18002a109  mov     ebx, eax
0x18002a10b  lea     rdx, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a112  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002a119  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002a120  mov     r8d, esi
0x18002a123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a128  mov     ecx, ebx; dwErrCode
0x18002a12a  call    cs:__imp_SetLastError
0x18002a131  nop     dword ptr [rax+rax+00h]
0x18002a136  mov     rbx, [rsp+48h+arg_0]
0x18002a13b  mov     eax, edi
0x18002a13d  mov     rsi, [rsp+48h+arg_8]
0x18002a142  add     rsp, 40h
0x18002a146  pop     rdi
0x18002a147  retn
```
