# ElValidateHr_1

- ea: `0x18000ff48`
- end: `0x18001003b`
- name: `ElValidateHr_1`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f2f0`
- `0x18000fd00`

## callees

- `0x180006ea4`
- `0x18000ff48`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000fff2`
- `KERNEL32!SetLastError` at `0x18001001c`
- `KERNEL32!SetLastError` at `0x18000fff2`
- `KERNEL32!SetLastError` at `0x18001001c`
- `KERNEL32!GetLastError` at `0x18000ff6e`
- `KERNEL32!GetLastError` at `0x18000ffba`
- `KERNEL32!GetLastError` at `0x18000fffe`
- `KERNEL32!GetLastError` at `0x18000ff6e`
- `KERNEL32!GetLastError` at `0x18000ffba`
- `KERNEL32!GetLastError` at `0x18000fffe`

## string_xrefs

- `0x18000ff8a`: `onecore\base\eco\wds\wdslib\common\src\regkey.cpp`
- `0x18000ffd3`: `onecore\base\eco\wds\wdslib\common\src\regkey.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_1(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\regkey.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\regkey.cpp",
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
0x18000ff48  mov     [rsp+arg_0], rbx
0x18000ff4d  mov     [rsp+arg_8], rsi
0x18000ff52  push    rdi
0x18000ff53  sub     rsp, 40h
0x18000ff57  mov     esi, r9d
0x18000ff5a  mov     edi, ecx
0x18000ff5c  test    ecx, ecx
0x18000ff5e  jns     loc_180010028
0x18000ff64  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ff6c  jz      short loc_18000FFB0
0x18000ff6e  call    cs:__imp_GetLastError
0x18000ff75  nop     dword ptr [rax+rax+00h]
0x18000ff7a  lea     r9, dword_18003572C
0x18000ff81  mov     [rsp+48h+var_20], edi
0x18000ff85  mov     [rsp+48h+var_28], r9
0x18000ff8a  lea     r8, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000ff91  mov     ebx, eax
0x18000ff93  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ff9a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ffa1  mov     r9d, esi
0x18000ffa4  mov     ecx, 80000h
0x18000ffa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffae  jmp     short loc_18000FFF0
0x18000ffb0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ffb8  jz      short loc_18000FFFE
0x18000ffba  call    cs:__imp_GetLastError
0x18000ffc1  nop     dword ptr [rax+rax+00h]
0x18000ffc6  lea     r9, dword_18003572C
0x18000ffcd  mov     dword ptr [rsp+48h+var_28], edi
0x18000ffd1  mov     ebx, eax
0x18000ffd3  lea     rdx, aOnecoreBaseEco_31; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000ffda  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ffe1  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ffe8  mov     r8d, esi
0x18000ffeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff0  mov     ecx, ebx; dwErrCode
0x18000fff2  call    cs:__imp_SetLastError
0x18000fff9  nop     dword ptr [rax+rax+00h]
0x18000fffe  call    cs:__imp_GetLastError
0x180010005  nop     dword ptr [rax+rax+00h]
0x18001000a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180010011  mov     ebx, eax
0x180010013  jz      short loc_18001001A
0x180010015  call    ElTraceErrorInfo
0x18001001a  mov     ecx, ebx; dwErrCode
0x18001001c  call    cs:__imp_SetLastError
0x180010023  nop     dword ptr [rax+rax+00h]
0x180010028  mov     rbx, [rsp+48h+arg_0]
0x18001002d  mov     eax, edi
0x18001002f  mov     rsi, [rsp+48h+arg_8]
0x180010034  add     rsp, 40h
0x180010038  pop     rdi
0x180010039  retn
```
