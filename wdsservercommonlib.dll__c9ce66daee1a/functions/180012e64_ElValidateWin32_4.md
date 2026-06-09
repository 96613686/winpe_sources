# ElValidateWin32_4

- ea: `0x180012e64`
- end: `0x180012f2d`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012d80`

## callees

- `0x180012e64`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012f0e`
- `KERNEL32!SetLastError` at `0x180012f0e`
- `KERNEL32!GetLastError` at `0x180012e8a`
- `KERNEL32!GetLastError` at `0x180012ed6`
- `KERNEL32!GetLastError` at `0x180012e8a`
- `KERNEL32!GetLastError` at `0x180012ed6`

## string_xrefs

- `0x180012ea6`: `onecore\base\eco\wds\wdslib\common\src\domaininfo.cpp`
- `0x180012eef`: `onecore\base\eco\wds\wdslib\common\src\domaininfo.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_4(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\domaininfo.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\domaininfo.cpp",
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
0x180012e64  mov     [rsp+arg_0], rbx
0x180012e69  mov     [rsp+arg_8], rsi
0x180012e6e  push    rdi
0x180012e6f  sub     rsp, 40h
0x180012e73  mov     esi, r9d
0x180012e76  mov     edi, ecx
0x180012e78  test    ecx, ecx
0x180012e7a  jz      loc_180012F1A
0x180012e80  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180012e88  jz      short loc_180012ECC
0x180012e8a  call    cs:__imp_GetLastError
0x180012e91  nop     dword ptr [rax+rax+00h]
0x180012e96  lea     r9, dword_1800331C4
0x180012e9d  mov     [rsp+48h+var_20], edi
0x180012ea1  mov     [rsp+48h+var_28], r9
0x180012ea6  lea     r8, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012ead  mov     ebx, eax
0x180012eaf  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180012eb6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180012ebd  mov     r9d, esi
0x180012ec0  mov     ecx, 80000h
0x180012ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eca  jmp     short loc_180012F0C
0x180012ecc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180012ed4  jz      short loc_180012F1A
0x180012ed6  call    cs:__imp_GetLastError
0x180012edd  nop     dword ptr [rax+rax+00h]
0x180012ee2  lea     r9, dword_1800331C4
0x180012ee9  mov     dword ptr [rsp+48h+var_28], edi
0x180012eed  mov     ebx, eax
0x180012eef  lea     rdx, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012ef6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180012efd  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180012f04  mov     r8d, esi
0x180012f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0c  mov     ecx, ebx; dwErrCode
0x180012f0e  call    cs:__imp_SetLastError
0x180012f15  nop     dword ptr [rax+rax+00h]
0x180012f1a  mov     rbx, [rsp+48h+arg_0]
0x180012f1f  mov     eax, edi
0x180012f21  mov     rsi, [rsp+48h+arg_8]
0x180012f26  add     rsp, 40h
0x180012f2a  pop     rdi
0x180012f2b  retn
```
