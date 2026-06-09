# ElValidateWin32_4

- ea: `0x180013afc`
- end: `0x180013bc5`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013a10`

## callees

- `0x180013afc`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013ba6`
- `KERNEL32!SetLastError` at `0x180013ba6`
- `KERNEL32!GetLastError` at `0x180013b22`
- `KERNEL32!GetLastError` at `0x180013b6e`
- `KERNEL32!GetLastError` at `0x180013b22`
- `KERNEL32!GetLastError` at `0x180013b6e`

## string_xrefs

- `0x180013b3e`: `onecore\base\eco\wds\wdslib\common\src\domaininfo.cpp`
- `0x180013b87`: `onecore\base\eco\wds\wdslib\common\src\domaininfo.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\domaininfo.cpp",
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
0x180013afc  mov     [rsp+arg_0], rbx
0x180013b01  mov     [rsp+arg_8], rsi
0x180013b06  push    rdi
0x180013b07  sub     rsp, 40h
0x180013b0b  mov     esi, r9d
0x180013b0e  mov     edi, ecx
0x180013b10  test    ecx, ecx
0x180013b12  jz      loc_180013BB2
0x180013b18  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013b20  jz      short loc_180013B64
0x180013b22  call    cs:__imp_GetLastError
0x180013b29  nop     dword ptr [rax+rax+00h]
0x180013b2e  lea     r9, dword_18003572C
0x180013b35  mov     [rsp+48h+var_20], edi
0x180013b39  mov     [rsp+48h+var_28], r9
0x180013b3e  lea     r8, aOnecoreBaseEco_24; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013b45  mov     ebx, eax
0x180013b47  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013b4e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013b55  mov     r9d, esi
0x180013b58  mov     ecx, 80000h
0x180013b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b62  jmp     short loc_180013BA4
0x180013b64  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013b6c  jz      short loc_180013BB2
0x180013b6e  call    cs:__imp_GetLastError
0x180013b75  nop     dword ptr [rax+rax+00h]
0x180013b7a  lea     r9, dword_18003572C
0x180013b81  mov     dword ptr [rsp+48h+var_28], edi
0x180013b85  mov     ebx, eax
0x180013b87  lea     rdx, aOnecoreBaseEco_24; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180013b8e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180013b95  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180013b9c  mov     r8d, esi
0x180013b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ba4  mov     ecx, ebx; dwErrCode
0x180013ba6  call    cs:__imp_SetLastError
0x180013bad  nop     dword ptr [rax+rax+00h]
0x180013bb2  mov     rbx, [rsp+48h+arg_0]
0x180013bb7  mov     eax, edi
0x180013bb9  mov     rsi, [rsp+48h+arg_8]
0x180013bbe  add     rsp, 40h
0x180013bc2  pop     rdi
0x180013bc3  retn
```
