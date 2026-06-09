# ElValidateWin32_4

- ea: `0x18000d6b0`
- end: `0x18000d779`
- name: `ElValidateWin32_4`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180004320`
- `0x180005920`
- `0x180008e70`
- `0x1800094b8`
- `0x1800096c0`
- `0x180009cb4`
- `0x18000a13c`
- `0x18000a948`
- `0x18000abe0`
- `0x18000ae64`
- `0x18000b17c`
- `0x18000bc58`
- `0x18000be68`
- `0x18000bfcc`
- `0x18000c148`
- `0x18000c46c`
- `0x18000c9f0`
- `0x18000d300`

## callees

- `0x18000d6b0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d6d6`
- `KERNEL32!GetLastError` at `0x18000d722`
- `KERNEL32!GetLastError` at `0x18000d6d6`
- `KERNEL32!GetLastError` at `0x18000d722`
- `KERNEL32!SetLastError` at `0x18000d75a`
- `KERNEL32!SetLastError` at `0x18000d75a`

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
        "base\\eco\\wds\\wdsimage\\src\\image.cpp",
        a4,
        &word_180013F66,
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
        "base\\eco\\wds\\wdsimage\\src\\image.cpp",
        a4,
        &word_180013F66,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000d6b0  mov     [rsp+arg_0], rbx
0x18000d6b5  mov     [rsp+arg_8], rsi
0x18000d6ba  push    rdi
0x18000d6bb  sub     rsp, 40h
0x18000d6bf  mov     esi, r9d
0x18000d6c2  mov     edi, ecx
0x18000d6c4  test    ecx, ecx
0x18000d6c6  jz      loc_18000D766
0x18000d6cc  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d6d4  jz      short loc_18000D718
0x18000d6d6  call    cs:__imp_GetLastError
0x18000d6dd  nop     dword ptr [rax+rax+00h]
0x18000d6e2  lea     r9, word_180013F66
0x18000d6e9  mov     [rsp+48h+var_20], edi
0x18000d6ed  mov     [rsp+48h+var_28], r9
0x18000d6f2  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d6f9  mov     ebx, eax
0x18000d6fb  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000d702  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000d709  mov     r9d, esi
0x18000d70c  mov     ecx, 80000h
0x18000d711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d716  jmp     short loc_18000D758
0x18000d718  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d720  jz      short loc_18000D766
0x18000d722  call    cs:__imp_GetLastError
0x18000d729  nop     dword ptr [rax+rax+00h]
0x18000d72e  lea     r9, word_180013F66
0x18000d735  mov     dword ptr [rsp+48h+var_28], edi
0x18000d739  mov     ebx, eax
0x18000d73b  lea     rdx, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d742  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000d749  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000d750  mov     r8d, esi
0x18000d753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d758  mov     ecx, ebx; dwErrCode
0x18000d75a  call    cs:__imp_SetLastError
0x18000d761  nop     dword ptr [rax+rax+00h]
0x18000d766  mov     rbx, [rsp+48h+arg_0]
0x18000d76b  mov     eax, edi
0x18000d76d  mov     rsi, [rsp+48h+arg_8]
0x18000d772  add     rsp, 40h
0x18000d776  pop     rdi
0x18000d777  retn
```
