# ElValidateWin32

- ea: `0x18000bd5c`
- end: `0x18000be2a`
- name: `ElValidateWin32`
- size: `206`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180004340`
- `0x180004460`
- `0x18000474c`
- `0x1800049e0`
- `0x180004d4c`
- `0x180005064`
- `0x180005558`
- `0x1800059f8`
- `0x180006dac`
- `0x180006f80`
- `0x18000726c`
- `0x1800077f4`
- `0x180007e80`
- `0x180008110`
- `0x180008174`
- `0x180008404`
- `0x180009b30`
- `0x180009d78`
- `0x180009fc8`
- `0x18000a5b8`
- `0x18000a610`
- `0x18000ceb0`
- `0x18000cfd0`

## callees

- `0x18000bd5c`
- `0x18000e010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000be06`
- `KERNEL32!SetLastError` at `0x18000be06`
- `KERNEL32!GetLastError` at `0x18000bd8a`
- `KERNEL32!GetLastError` at `0x18000bdd2`
- `KERNEL32!GetLastError` at `0x18000bd8a`
- `KERNEL32!GetLastError` at `0x18000bdd2`

## pseudocode

```c
__int64 __fastcall ElValidateWin32(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_180011084, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &dword_180011084, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000bd5c  mov     [rsp+arg_0], rbx
0x18000bd61  mov     [rsp+arg_8], rbp
0x18000bd66  mov     [rsp+arg_10], rsi
0x18000bd6b  push    rdi
0x18000bd6c  sub     rsp, 40h
0x18000bd70  mov     esi, r9d
0x18000bd73  mov     rbp, r8
0x18000bd76  mov     edi, ecx
0x18000bd78  test    ecx, ecx
0x18000bd7a  jz      loc_18000BE12
0x18000bd80  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000bd88  jz      short loc_18000BDC8
0x18000bd8a  call    cs:__imp_GetLastError
0x18000bd91  nop     dword ptr [rax+rax+00h]
0x18000bd96  lea     r9, dword_180011084
0x18000bd9d  mov     [rsp+48h+var_20], edi
0x18000bda1  mov     [rsp+48h+var_28], r9
0x18000bda6  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000bdad  mov     ebx, eax
0x18000bdaf  mov     r9d, esi
0x18000bdb2  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000bdb9  mov     r8, rbp
0x18000bdbc  mov     ecx, 80000h
0x18000bdc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdc6  jmp     short loc_18000BE04
0x18000bdc8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000bdd0  jz      short loc_18000BE12
0x18000bdd2  call    cs:__imp_GetLastError
0x18000bdd9  nop     dword ptr [rax+rax+00h]
0x18000bdde  lea     r9, dword_180011084
0x18000bde5  mov     dword ptr [rsp+48h+var_28], edi
0x18000bde9  mov     ebx, eax
0x18000bdeb  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000bdf2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000bdf9  mov     r8d, esi
0x18000bdfc  mov     rdx, rbp
0x18000bdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be04  mov     ecx, ebx; dwErrCode
0x18000be06  call    cs:__imp_SetLastError
0x18000be0d  nop     dword ptr [rax+rax+00h]
0x18000be12  mov     rbx, [rsp+48h+arg_0]
0x18000be17  mov     eax, edi
0x18000be19  mov     rbp, [rsp+48h+arg_8]
0x18000be1e  mov     rsi, [rsp+48h+arg_10]
0x18000be23  add     rsp, 40h
0x18000be27  pop     rdi
0x18000be28  retn
```
