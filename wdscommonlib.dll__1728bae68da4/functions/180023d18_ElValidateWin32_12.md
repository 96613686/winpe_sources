# ElValidateWin32_12

- ea: `0x180023d18`
- end: `0x180023de1`
- name: `ElValidateWin32_12`
- size: `201`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021680`
- `0x180021980`
- `0x180021ce0`
- `0x180021fd0`
- `0x180022060`
- `0x180022258`
- `0x180022408`
- `0x180022610`
- `0x180022680`
- `0x1800227b0`
- `0x180022f90`
- `0x180023220`
- `0x180023ab0`

## callees

- `0x180023d18`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180023dc2`
- `KERNEL32!SetLastError` at `0x180023dc2`
- `KERNEL32!GetLastError` at `0x180023d3e`
- `KERNEL32!GetLastError` at `0x180023d8a`
- `KERNEL32!GetLastError` at `0x180023d3e`
- `KERNEL32!GetLastError` at `0x180023d8a`

## string_xrefs

- `0x180023d5a`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023da3`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_12(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp",
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
0x180023d18  mov     [rsp+arg_0], rbx
0x180023d1d  mov     [rsp+arg_8], rsi
0x180023d22  push    rdi
0x180023d23  sub     rsp, 40h
0x180023d27  mov     esi, r9d
0x180023d2a  mov     edi, ecx
0x180023d2c  test    ecx, ecx
0x180023d2e  jz      loc_180023DCE
0x180023d34  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180023d3c  jz      short loc_180023D80
0x180023d3e  call    cs:__imp_GetLastError
0x180023d45  nop     dword ptr [rax+rax+00h]
0x180023d4a  lea     r9, dword_18003572C
0x180023d51  mov     [rsp+48h+var_20], edi
0x180023d55  mov     [rsp+48h+var_28], r9
0x180023d5a  lea     r8, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023d61  mov     ebx, eax
0x180023d63  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180023d6a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180023d71  mov     r9d, esi
0x180023d74  mov     ecx, 80000h
0x180023d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d7e  jmp     short loc_180023DC0
0x180023d80  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180023d88  jz      short loc_180023DCE
0x180023d8a  call    cs:__imp_GetLastError
0x180023d91  nop     dword ptr [rax+rax+00h]
0x180023d96  lea     r9, dword_18003572C
0x180023d9d  mov     dword ptr [rsp+48h+var_28], edi
0x180023da1  mov     ebx, eax
0x180023da3  lea     rdx, aOnecoreBaseEco_9; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023daa  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180023db1  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180023db8  mov     r8d, esi
0x180023dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dc0  mov     ecx, ebx; dwErrCode
0x180023dc2  call    cs:__imp_SetLastError
0x180023dc9  nop     dword ptr [rax+rax+00h]
0x180023dce  mov     rbx, [rsp+48h+arg_0]
0x180023dd3  mov     eax, edi
0x180023dd5  mov     rsi, [rsp+48h+arg_8]
0x180023dda  add     rsp, 40h
0x180023dde  pop     rdi
0x180023ddf  retn
```
