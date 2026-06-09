# ElValidateWin32_8

- ea: `0x18001b0cc`
- end: `0x18001b195`
- name: `ElValidateWin32_8`
- size: `201`
- prototype: ``
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800197b0`
- `0x180019aec`
- `0x180019f54`
- `0x18001a1c8`
- `0x18001a5dc`
- `0x18001acf0`
- `0x18001aee0`
- `0x18001b220`
- `0x18001b280`
- `0x18001b610`
- `0x18001b780`
- `0x18001b890`
- `0x18001ba90`
- `0x18001bbc0`
- `0x18001bef0`
- `0x18001c240`
- `0x18001c370`
- `0x18001c780`
- `0x18001c930`
- `0x18001ca60`
- `0x18001cb00`
- `0x18001cca0`
- `0x18001cda0`
- `0x18001d180`
- `0x18001d2b0`
- `0x18001d510`
- `0x18001d640`
- `0x18001d730`
- `0x18001dc80`

## callees

- `0x18001b0cc`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001b176`
- `KERNEL32!SetLastError` at `0x18001b176`
- `KERNEL32!GetLastError` at `0x18001b0f2`
- `KERNEL32!GetLastError` at `0x18001b13e`
- `KERNEL32!GetLastError` at `0x18001b0f2`
- `KERNEL32!GetLastError` at `0x18001b13e`

## string_xrefs

- `0x18001b10e`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`
- `0x18001b157`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
0x18001b0cc  mov     [rsp+arg_0], rbx
0x18001b0d1  mov     [rsp+arg_8], rsi
0x18001b0d6  push    rdi
0x18001b0d7  sub     rsp, 40h
0x18001b0db  mov     esi, r9d
0x18001b0de  mov     edi, ecx
0x18001b0e0  test    ecx, ecx
0x18001b0e2  jz      loc_18001B182
0x18001b0e8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001b0f0  jz      short loc_18001B134
0x18001b0f2  call    cs:__imp_GetLastError
0x18001b0f9  nop     dword ptr [rax+rax+00h]
0x18001b0fe  lea     r9, dword_18003572C
0x18001b105  mov     [rsp+48h+var_20], edi
0x18001b109  mov     [rsp+48h+var_28], r9
0x18001b10e  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001b115  mov     ebx, eax
0x18001b117  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001b11e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001b125  mov     r9d, esi
0x18001b128  mov     ecx, 80000h
0x18001b12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b132  jmp     short loc_18001B174
0x18001b134  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001b13c  jz      short loc_18001B182
0x18001b13e  call    cs:__imp_GetLastError
0x18001b145  nop     dword ptr [rax+rax+00h]
0x18001b14a  lea     r9, dword_18003572C
0x18001b151  mov     dword ptr [rsp+48h+var_28], edi
0x18001b155  mov     ebx, eax
0x18001b157  lea     rdx, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001b15e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001b165  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001b16c  mov     r8d, esi
0x18001b16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b174  mov     ecx, ebx; dwErrCode
0x18001b176  call    cs:__imp_SetLastError
0x18001b17d  nop     dword ptr [rax+rax+00h]
0x18001b182  mov     rbx, [rsp+48h+arg_0]
0x18001b187  mov     eax, edi
0x18001b189  mov     rsi, [rsp+48h+arg_8]
0x18001b18e  add     rsp, 40h
0x18001b192  pop     rdi
0x18001b193  retn
```
