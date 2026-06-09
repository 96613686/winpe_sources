# ElValidateWin32_5

- ea: `0x180014800`
- end: `0x1800148c9`
- name: `ElValidateWin32_5`
- size: `201`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012f40`
- `0x180012fe0`
- `0x180013080`
- `0x1800131c0`
- `0x180013400`
- `0x180013670`
- `0x180013840`
- `0x1800139d0`
- `0x180013bb0`
- `0x180013c60`
- `0x180013cf0`
- `0x180013d60`
- `0x180013ef0`
- `0x180013f70`
- `0x180014080`
- `0x180014170`
- `0x1800142f0`
- `0x1800145c0`

## callees

- `0x180014800`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800148aa`
- `KERNEL32!SetLastError` at `0x1800148aa`
- `KERNEL32!GetLastError` at `0x180014826`
- `KERNEL32!GetLastError` at `0x180014872`
- `KERNEL32!GetLastError` at `0x180014826`
- `KERNEL32!GetLastError` at `0x180014872`

## string_xrefs

- `0x180014842`: `onecore\base\eco\wds\wdslib\common\src\ldap.cpp`
- `0x18001488b`: `onecore\base\eco\wds\wdslib\common\src\ldap.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_5(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldap.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldap.cpp",
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
0x180014800  mov     [rsp+arg_0], rbx
0x180014805  mov     [rsp+arg_8], rsi
0x18001480a  push    rdi
0x18001480b  sub     rsp, 40h
0x18001480f  mov     esi, r9d
0x180014812  mov     edi, ecx
0x180014814  test    ecx, ecx
0x180014816  jz      loc_1800148B6
0x18001481c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014824  jz      short loc_180014868
0x180014826  call    cs:__imp_GetLastError
0x18001482d  nop     dword ptr [rax+rax+00h]
0x180014832  lea     r9, dword_1800331C4
0x180014839  mov     [rsp+48h+var_20], edi
0x18001483d  mov     [rsp+48h+var_28], r9
0x180014842  lea     r8, aOnecoreBaseEco_15; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180014849  mov     ebx, eax
0x18001484b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180014852  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014859  mov     r9d, esi
0x18001485c  mov     ecx, 80000h
0x180014861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014866  jmp     short loc_1800148A8
0x180014868  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014870  jz      short loc_1800148B6
0x180014872  call    cs:__imp_GetLastError
0x180014879  nop     dword ptr [rax+rax+00h]
0x18001487e  lea     r9, dword_1800331C4
0x180014885  mov     dword ptr [rsp+48h+var_28], edi
0x180014889  mov     ebx, eax
0x18001488b  lea     rdx, aOnecoreBaseEco_15; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180014892  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014899  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800148a0  mov     r8d, esi
0x1800148a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148a8  mov     ecx, ebx; dwErrCode
0x1800148aa  call    cs:__imp_SetLastError
0x1800148b1  nop     dword ptr [rax+rax+00h]
0x1800148b6  mov     rbx, [rsp+48h+arg_0]
0x1800148bb  mov     eax, edi
0x1800148bd  mov     rsi, [rsp+48h+arg_8]
0x1800148c2  add     rsp, 40h
0x1800148c6  pop     rdi
0x1800148c7  retn
```
