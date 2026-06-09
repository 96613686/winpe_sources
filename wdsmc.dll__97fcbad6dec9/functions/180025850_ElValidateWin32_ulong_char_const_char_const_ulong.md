# ElValidateWin32(ulong,char const *,char const *,ulong)

- ea: `0x180025850`
- end: `0x18002590d`
- name: `?ElValidateWin32@@YAKKPEBD0K@Z`
- size: `189`
- prototype: `unsigned int __fastcall(unsigned int, const char *, const char *, unsigned int)`
- caller_count: `182`
- callee_count: `2`
- tags: ``

## callers

- `0x180001110`
- `0x180002368`
- `0x1800026b8`
- `0x1800029f4`
- `0x180002ba4`
- `0x180002c70`
- `0x1800031e4`
- `0x180003314`
- `0x180003590`
- `0x180003f10`
- `0x180004184`
- `0x180004530`
- `0x18000463c`
- `0x18000480c`
- `0x180004c60`
- `0x1800053a0`
- `0x180005a4c`
- `0x180005e28`
- `0x180005f18`
- `0x180006488`
- `0x1800067f0`
- `0x180006bc4`
- `0x180006e48`
- `0x180006f84`
- `0x1800070ac`
- `0x1800071a0`
- `0x180007278`
- `0x180007358`
- `0x1800074bc`
- `0x180007668`
- `0x1800077b0`
- `0x1800078a8`
- `0x180007a24`
- `0x180007e64`
- `0x180008040`
- `0x1800082d0`
- `0x180008b58`
- `0x180008c50`
- `0x180008ff0`
- `0x180009130`
- `0x180009400`
- `0x18000967c`
- `0x180009ab8`
- `0x180009cec`
- `0x180009dc8`
- `0x180009e84`
- `0x18000a018`
- `0x18000a0a4`
- `0x18000a160`
- `0x18000a210`

## callees

- `0x180025850`
- `0x180026d70`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800258f0`
- `KERNEL32!SetLastError` at `0x1800258f0`
- `KERNEL32!GetLastError` at `0x18002587e`
- `KERNEL32!GetLastError` at `0x1800258c1`
- `KERNEL32!GetLastError` at `0x18002587e`
- `KERNEL32!GetLastError` at `0x1800258c1`

## pseudocode

```c
__int64 __fastcall ElValidateWin32(unsigned int a1, const char *a2, const char *a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, word_180029FDA, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, word_180029FDA, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180025850  mov     [rsp+arg_0], rbx
0x180025855  mov     [rsp+arg_8], rbp
0x18002585a  mov     [rsp+arg_10], rsi
0x18002585f  push    rdi
0x180025860  sub     rsp, 40h
0x180025864  mov     esi, r9d
0x180025867  mov     rbp, r8
0x18002586a  mov     edi, ecx
0x18002586c  test    ecx, ecx
0x18002586e  jz      loc_1800258F6
0x180025874  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002587c  jz      short loc_1800258B7
0x18002587e  call    cs:__imp_GetLastError
0x180025884  lea     r9, word_180029FDA
0x18002588b  mov     [rsp+48h+var_20], edi
0x18002588f  mov     [rsp+48h+var_28], r9
0x180025894  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18002589b  mov     ebx, eax
0x18002589d  mov     r9d, esi
0x1800258a0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800258a7  mov     r8, rbp
0x1800258aa  mov     ecx, 80000h
0x1800258af  call    cs:__guard_dispatch_icall_fptr
0x1800258b5  jmp     short loc_1800258EE
0x1800258b7  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800258bf  jz      short loc_1800258F6
0x1800258c1  call    cs:__imp_GetLastError
0x1800258c7  lea     r9, word_180029FDA
0x1800258ce  mov     dword ptr [rsp+48h+var_28], edi
0x1800258d2  mov     ebx, eax
0x1800258d4  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800258db  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800258e2  mov     r8d, esi
0x1800258e5  mov     rdx, rbp
0x1800258e8  call    cs:__guard_dispatch_icall_fptr
0x1800258ee  mov     ecx, ebx; dwErrCode
0x1800258f0  call    cs:__imp_SetLastError
0x1800258f6  mov     rbx, [rsp+48h+arg_0]
0x1800258fb  mov     eax, edi
0x1800258fd  mov     rbp, [rsp+48h+arg_8]
0x180025902  mov     rsi, [rsp+48h+arg_10]
0x180025907  add     rsp, 40h
0x18002590b  pop     rdi
0x18002590c  retn
```
