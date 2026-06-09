# ElValidateHr_6

- ea: `0x18001f080`
- end: `0x18001f173`
- name: `ElValidateHr_6`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e9f0`
- `0x18001ebe0`

## callees

- `0x180006ea4`
- `0x18001f080`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001f12a`
- `KERNEL32!SetLastError` at `0x18001f154`
- `KERNEL32!SetLastError` at `0x18001f12a`
- `KERNEL32!SetLastError` at `0x18001f154`
- `KERNEL32!GetLastError` at `0x18001f0a6`
- `KERNEL32!GetLastError` at `0x18001f0f2`
- `KERNEL32!GetLastError` at `0x18001f136`
- `KERNEL32!GetLastError` at `0x18001f0a6`
- `KERNEL32!GetLastError` at `0x18001f0f2`
- `KERNEL32!GetLastError` at `0x18001f136`

## string_xrefs

- `0x18001f0c2`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`
- `0x18001f10b`: `onecore\base\eco\wds\wdslib\common\src\keystring.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_6(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_18003572C,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\keystring.cpp",
      a4,
      &dword_18003572C,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18001f080  mov     [rsp+arg_0], rbx
0x18001f085  mov     [rsp+arg_8], rsi
0x18001f08a  push    rdi
0x18001f08b  sub     rsp, 40h
0x18001f08f  mov     esi, r9d
0x18001f092  mov     edi, ecx
0x18001f094  test    ecx, ecx
0x18001f096  jns     loc_18001F160
0x18001f09c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f0a4  jz      short loc_18001F0E8
0x18001f0a6  call    cs:__imp_GetLastError
0x18001f0ad  nop     dword ptr [rax+rax+00h]
0x18001f0b2  lea     r9, dword_18003572C
0x18001f0b9  mov     [rsp+48h+var_20], edi
0x18001f0bd  mov     [rsp+48h+var_28], r9
0x18001f0c2  lea     r8, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f0c9  mov     ebx, eax
0x18001f0cb  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001f0d2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f0d9  mov     r9d, esi
0x18001f0dc  mov     ecx, 80000h
0x18001f0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0e6  jmp     short loc_18001F128
0x18001f0e8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f0f0  jz      short loc_18001F136
0x18001f0f2  call    cs:__imp_GetLastError
0x18001f0f9  nop     dword ptr [rax+rax+00h]
0x18001f0fe  lea     r9, dword_18003572C
0x18001f105  mov     dword ptr [rsp+48h+var_28], edi
0x18001f109  mov     ebx, eax
0x18001f10b  lea     rdx, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f112  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f119  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001f120  mov     r8d, esi
0x18001f123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f128  mov     ecx, ebx; dwErrCode
0x18001f12a  call    cs:__imp_SetLastError
0x18001f131  nop     dword ptr [rax+rax+00h]
0x18001f136  call    cs:__imp_GetLastError
0x18001f13d  nop     dword ptr [rax+rax+00h]
0x18001f142  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001f149  mov     ebx, eax
0x18001f14b  jz      short loc_18001F152
0x18001f14d  call    ElTraceErrorInfo
0x18001f152  mov     ecx, ebx; dwErrCode
0x18001f154  call    cs:__imp_SetLastError
0x18001f15b  nop     dword ptr [rax+rax+00h]
0x18001f160  mov     rbx, [rsp+48h+arg_0]
0x18001f165  mov     eax, edi
0x18001f167  mov     rsi, [rsp+48h+arg_8]
0x18001f16c  add     rsp, 40h
0x18001f170  pop     rdi
0x18001f171  retn
```
