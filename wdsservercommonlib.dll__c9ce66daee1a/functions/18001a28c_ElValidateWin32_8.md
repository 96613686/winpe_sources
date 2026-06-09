# ElValidateWin32_8

- ea: `0x18001a28c`
- end: `0x18001a355`
- name: `ElValidateWin32_8`
- size: `201`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800189d0`
- `0x180018d00`
- `0x180019154`
- `0x1800193b8`
- `0x1800197a8`
- `0x180019eb0`
- `0x18001a0a0`
- `0x18001a3e0`
- `0x18001a440`
- `0x18001a7b0`
- `0x18001a900`
- `0x18001aa00`
- `0x18001ac00`
- `0x18001ad30`
- `0x18001b050`
- `0x18001b3a0`
- `0x18001b4c0`
- `0x18001b8c0`
- `0x18001ba60`
- `0x18001bb90`
- `0x18001bc30`
- `0x18001bdc0`
- `0x18001bec0`
- `0x18001c280`
- `0x18001c3b0`
- `0x18001c610`
- `0x18001c730`
- `0x18001c810`
- `0x18001cd20`

## callees

- `0x18001a28c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001a336`
- `KERNEL32!SetLastError` at `0x18001a336`
- `KERNEL32!GetLastError` at `0x18001a2b2`
- `KERNEL32!GetLastError` at `0x18001a2fe`
- `KERNEL32!GetLastError` at `0x18001a2b2`
- `KERNEL32!GetLastError` at `0x18001a2fe`

## string_xrefs

- `0x18001a2ce`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`
- `0x18001a317`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_8(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
0x18001a28c  mov     [rsp+arg_0], rbx
0x18001a291  mov     [rsp+arg_8], rsi
0x18001a296  push    rdi
0x18001a297  sub     rsp, 40h
0x18001a29b  mov     esi, r9d
0x18001a29e  mov     edi, ecx
0x18001a2a0  test    ecx, ecx
0x18001a2a2  jz      loc_18001A342
0x18001a2a8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001a2b0  jz      short loc_18001A2F4
0x18001a2b2  call    cs:__imp_GetLastError
0x18001a2b9  nop     dword ptr [rax+rax+00h]
0x18001a2be  lea     r9, dword_1800331C4
0x18001a2c5  mov     [rsp+48h+var_20], edi
0x18001a2c9  mov     [rsp+48h+var_28], r9
0x18001a2ce  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001a2d5  mov     ebx, eax
0x18001a2d7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001a2de  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001a2e5  mov     r9d, esi
0x18001a2e8  mov     ecx, 80000h
0x18001a2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2f2  jmp     short loc_18001A334
0x18001a2f4  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a2fc  jz      short loc_18001A342
0x18001a2fe  call    cs:__imp_GetLastError
0x18001a305  nop     dword ptr [rax+rax+00h]
0x18001a30a  lea     r9, dword_1800331C4
0x18001a311  mov     dword ptr [rsp+48h+var_28], edi
0x18001a315  mov     ebx, eax
0x18001a317  lea     rdx, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001a31e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a325  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001a32c  mov     r8d, esi
0x18001a32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a334  mov     ecx, ebx; dwErrCode
0x18001a336  call    cs:__imp_SetLastError
0x18001a33d  nop     dword ptr [rax+rax+00h]
0x18001a342  mov     rbx, [rsp+48h+arg_0]
0x18001a347  mov     eax, edi
0x18001a349  mov     rsi, [rsp+48h+arg_8]
0x18001a34e  add     rsp, 40h
0x18001a352  pop     rdi
0x18001a353  retn
```
