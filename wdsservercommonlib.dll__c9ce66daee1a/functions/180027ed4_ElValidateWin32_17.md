# ElValidateWin32_17

- ea: `0x180027ed4`
- end: `0x180027f96`
- name: `ElValidateWin32_17`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027cf0`

## callees

- `0x180027ed4`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180027f7c`
- `KERNEL32!SetLastError` at `0x180027f7c`
- `KERNEL32!GetLastError` at `0x180027ef2`
- `KERNEL32!GetLastError` at `0x180027f41`
- `KERNEL32!GetLastError` at `0x180027ef2`
- `KERNEL32!GetLastError` at `0x180027f41`

## string_xrefs

- `0x180027f0e`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`
- `0x180027f5a`: `onecore\base\eco\wds\wdslib\common\src\wdscred.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_17(unsigned int a1)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscred.cpp",
        84,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscred.cpp",
        84,
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
0x180027ed4  mov     [rsp+arg_0], rbx
0x180027ed9  push    rdi
0x180027eda  sub     rsp, 40h
0x180027ede  mov     edi, ecx
0x180027ee0  test    ecx, ecx
0x180027ee2  jz      loc_180027F88
0x180027ee8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027ef0  jz      short loc_180027F37
0x180027ef2  call    cs:__imp_GetLastError
0x180027ef9  nop     dword ptr [rax+rax+00h]
0x180027efe  lea     r9, dword_1800331C4
0x180027f05  mov     [rsp+48h+var_20], edi
0x180027f09  mov     [rsp+48h+var_28], r9
0x180027f0e  lea     r8, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027f15  mov     ebx, eax
0x180027f17  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180027f1e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180027f25  mov     r9d, 54h ; 'T'
0x180027f2b  mov     ecx, 80000h
0x180027f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f35  jmp     short loc_180027F7A
0x180027f37  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027f3f  jz      short loc_180027F88
0x180027f41  call    cs:__imp_GetLastError
0x180027f48  nop     dword ptr [rax+rax+00h]
0x180027f4d  lea     r9, dword_1800331C4
0x180027f54  mov     dword ptr [rsp+48h+var_28], edi
0x180027f58  mov     ebx, eax
0x180027f5a  lea     rdx, aOnecoreBaseEco_4; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180027f61  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180027f68  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180027f6f  mov     r8d, 54h ; 'T'
0x180027f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f7a  mov     ecx, ebx; dwErrCode
0x180027f7c  call    cs:__imp_SetLastError
0x180027f83  nop     dword ptr [rax+rax+00h]
0x180027f88  mov     rbx, [rsp+48h+arg_0]
0x180027f8d  mov     eax, edi
0x180027f8f  add     rsp, 40h
0x180027f93  pop     rdi
0x180027f94  retn
```
