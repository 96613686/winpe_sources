# ElValidateHr_5

- ea: `0x18001afd0`
- end: `0x18001b0c3`
- name: `ElValidateHr_5`
- size: `243`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800197b0`
- `0x18001a880`
- `0x18001ab10`
- `0x18001ba90`
- `0x18001d450`
- `0x18001d4e0`

## callees

- `0x180006ea4`
- `0x18001afd0`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001b07a`
- `KERNEL32!SetLastError` at `0x18001b0a4`
- `KERNEL32!SetLastError` at `0x18001b07a`
- `KERNEL32!SetLastError` at `0x18001b0a4`
- `KERNEL32!GetLastError` at `0x18001aff6`
- `KERNEL32!GetLastError` at `0x18001b042`
- `KERNEL32!GetLastError` at `0x18001b086`
- `KERNEL32!GetLastError` at `0x18001aff6`
- `KERNEL32!GetLastError` at `0x18001b042`
- `KERNEL32!GetLastError` at `0x18001b086`

## string_xrefs

- `0x18001b012`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`
- `0x18001b05b`: `onecore\base\eco\wds\wdslib\common\src\fileutil.cpp`

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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\fileutil.cpp",
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
0x18001afd0  mov     [rsp+arg_0], rbx
0x18001afd5  mov     [rsp+arg_8], rsi
0x18001afda  push    rdi
0x18001afdb  sub     rsp, 40h
0x18001afdf  mov     esi, r9d
0x18001afe2  mov     edi, ecx
0x18001afe4  test    ecx, ecx
0x18001afe6  jns     loc_18001B0B0
0x18001afec  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001aff4  jz      short loc_18001B038
0x18001aff6  call    cs:__imp_GetLastError
0x18001affd  nop     dword ptr [rax+rax+00h]
0x18001b002  lea     r9, dword_18003572C
0x18001b009  mov     [rsp+48h+var_20], edi
0x18001b00d  mov     [rsp+48h+var_28], r9
0x18001b012  lea     r8, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001b019  mov     ebx, eax
0x18001b01b  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001b022  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001b029  mov     r9d, esi
0x18001b02c  mov     ecx, 80000h
0x18001b031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b036  jmp     short loc_18001B078
0x18001b038  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001b040  jz      short loc_18001B086
0x18001b042  call    cs:__imp_GetLastError
0x18001b049  nop     dword ptr [rax+rax+00h]
0x18001b04e  lea     r9, dword_18003572C
0x18001b055  mov     dword ptr [rsp+48h+var_28], edi
0x18001b059  mov     ebx, eax
0x18001b05b  lea     rdx, aOnecoreBaseEco_1; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001b062  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001b069  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18001b070  mov     r8d, esi
0x18001b073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b078  mov     ecx, ebx; dwErrCode
0x18001b07a  call    cs:__imp_SetLastError
0x18001b081  nop     dword ptr [rax+rax+00h]
0x18001b086  call    cs:__imp_GetLastError
0x18001b08d  nop     dword ptr [rax+rax+00h]
0x18001b092  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18001b099  mov     ebx, eax
0x18001b09b  jz      short loc_18001B0A2
0x18001b09d  call    ElTraceErrorInfo
0x18001b0a2  mov     ecx, ebx; dwErrCode
0x18001b0a4  call    cs:__imp_SetLastError
0x18001b0ab  nop     dword ptr [rax+rax+00h]
0x18001b0b0  mov     rbx, [rsp+48h+arg_0]
0x18001b0b5  mov     eax, edi
0x18001b0b7  mov     rsi, [rsp+48h+arg_8]
0x18001b0bc  add     rsp, 40h
0x18001b0c0  pop     rdi
0x18001b0c1  retn
```
