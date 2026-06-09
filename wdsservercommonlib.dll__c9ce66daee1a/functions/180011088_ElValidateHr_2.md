# ElValidateHr_2

- ea: `0x180011088`
- end: `0x18001117b`
- name: `ElValidateHr_2`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010300`
- `0x180010620`

## callees

- `0x1800063c4`
- `0x180011088`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180011132`
- `KERNEL32!SetLastError` at `0x18001115c`
- `KERNEL32!SetLastError` at `0x180011132`
- `KERNEL32!SetLastError` at `0x18001115c`
- `KERNEL32!GetLastError` at `0x1800110ae`
- `KERNEL32!GetLastError` at `0x1800110fa`
- `KERNEL32!GetLastError` at `0x18001113e`
- `KERNEL32!GetLastError` at `0x1800110ae`
- `KERNEL32!GetLastError` at `0x1800110fa`
- `KERNEL32!GetLastError` at `0x18001113e`

## string_xrefs

- `0x1800110ca`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`
- `0x180011113`: `onecore\base\eco\wds\wdslib\common\src\trace.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_2(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
      a4,
      &dword_1800331C4,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\trace.cpp",
      a4,
      &dword_1800331C4,
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
0x180011088  mov     [rsp+arg_0], rbx
0x18001108d  mov     [rsp+arg_8], rsi
0x180011092  push    rdi
0x180011093  sub     rsp, 40h
0x180011097  mov     esi, r9d
0x18001109a  mov     edi, ecx
0x18001109c  test    ecx, ecx
0x18001109e  jns     loc_180011168
0x1800110a4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800110ac  jz      short loc_1800110F0
0x1800110ae  call    cs:__imp_GetLastError
0x1800110b5  nop     dword ptr [rax+rax+00h]
0x1800110ba  lea     r9, dword_1800331C4
0x1800110c1  mov     [rsp+48h+var_20], edi
0x1800110c5  mov     [rsp+48h+var_28], r9
0x1800110ca  lea     r8, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800110d1  mov     ebx, eax
0x1800110d3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800110da  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800110e1  mov     r9d, esi
0x1800110e4  mov     ecx, 80000h
0x1800110e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ee  jmp     short loc_180011130
0x1800110f0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800110f8  jz      short loc_18001113E
0x1800110fa  call    cs:__imp_GetLastError
0x180011101  nop     dword ptr [rax+rax+00h]
0x180011106  lea     r9, dword_1800331C4
0x18001110d  mov     dword ptr [rsp+48h+var_28], edi
0x180011111  mov     ebx, eax
0x180011113  lea     rdx, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001111a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180011121  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180011128  mov     r8d, esi
0x18001112b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011130  mov     ecx, ebx; dwErrCode
0x180011132  call    cs:__imp_SetLastError
0x180011139  nop     dword ptr [rax+rax+00h]
0x18001113e  call    cs:__imp_GetLastError
0x180011145  nop     dword ptr [rax+rax+00h]
0x18001114a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180011151  mov     ebx, eax
0x180011153  jz      short loc_18001115A
0x180011155  call    ElTraceErrorInfo
0x18001115a  mov     ecx, ebx; dwErrCode
0x18001115c  call    cs:__imp_SetLastError
0x180011163  nop     dword ptr [rax+rax+00h]
0x180011168  mov     rbx, [rsp+48h+arg_0]
0x18001116d  mov     eax, edi
0x18001116f  mov     rsi, [rsp+48h+arg_8]
0x180011174  add     rsp, 40h
0x180011178  pop     rdi
0x180011179  retn
```
