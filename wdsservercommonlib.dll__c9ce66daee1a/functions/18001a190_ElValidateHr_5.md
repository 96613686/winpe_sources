# ElValidateHr_5

- ea: `0x18001a190`
- end: `0x18001a283`
- name: `ElValidateHr_5`
- size: `243`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800189d0`
- `0x180019a40`
- `0x180019cd0`
- `0x18001ac00`
- `0x18001c550`
- `0x18001c5e0`

## callees

- `0x1800063c4`
- `0x18001a190`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001a23a`
- `KERNEL32!SetLastError` at `0x18001a264`
- `KERNEL32!SetLastError` at `0x18001a23a`
- `KERNEL32!SetLastError` at `0x18001a264`
- `KERNEL32!GetLastError` at `0x18001a1b6`
- `KERNEL32!GetLastError` at `0x18001a202`
- `KERNEL32!GetLastError` at `0x18001a246`
- `KERNEL32!GetLastError` at `0x18001a1b6`
- `KERNEL32!GetLastError` at `0x18001a202`
- `KERNEL32!GetLastError` at `0x18001a246`

## string_xrefs

- `0x18001a1d2`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`
- `0x18001a21b`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_5(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
0x18001a190  mov     [rsp+arg_0], rbx
0x18001a195  mov     [rsp+arg_8], rsi
0x18001a19a  push    rdi
0x18001a19b  sub     rsp, 40h
0x18001a19f  mov     esi, r9d
0x18001a1a2  mov     edi, ecx
0x18001a1a4  test    ecx, ecx
0x18001a1a6  jns     loc_18001A270
0x18001a1ac  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001a1b4  jz      short loc_18001A1F8
0x18001a1b6  call    cs:__imp_GetLastError
0x18001a1bd  nop     dword ptr [rax+rax+00h]
0x18001a1c2  lea     r9, dword_1800331C4
0x18001a1c9  mov     [rsp+48h+var_20], edi
0x18001a1cd  mov     [rsp+48h+var_28], r9
0x18001a1d2  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001a1d9  mov     ebx, eax
0x18001a1db  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001a1e2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001a1e9  mov     r9d, esi
0x18001a1ec  mov     ecx, 80000h
0x18001a1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1f6  jmp     short loc_18001A238
0x18001a1f8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a200  jz      short loc_18001A246
0x18001a202  call    cs:__imp_GetLastError
0x18001a209  nop     dword ptr [rax+rax+00h]
0x18001a20e  lea     r9, dword_1800331C4
0x18001a215  mov     dword ptr [rsp+48h+var_28], edi
0x18001a219  mov     ebx, eax
0x18001a21b  lea     rdx, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001a222  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001a229  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001a230  mov     r8d, esi
0x18001a233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a238  mov     ecx, ebx; dwErrCode
0x18001a23a  call    cs:__imp_SetLastError
0x18001a241  nop     dword ptr [rax+rax+00h]
0x18001a246  call    cs:__imp_GetLastError
0x18001a24d  nop     dword ptr [rax+rax+00h]
0x18001a252  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001a259  mov     ebx, eax
0x18001a25b  jz      short loc_18001A262
0x18001a25d  call    ElTraceErrorInfo
0x18001a262  mov     ecx, ebx; dwErrCode
0x18001a264  call    cs:__imp_SetLastError
0x18001a26b  nop     dword ptr [rax+rax+00h]
0x18001a270  mov     rbx, [rsp+48h+arg_0]
0x18001a275  mov     eax, edi
0x18001a277  mov     rsi, [rsp+48h+arg_8]
0x18001a27c  add     rsp, 40h
0x18001a280  pop     rdi
0x18001a281  retn
```
