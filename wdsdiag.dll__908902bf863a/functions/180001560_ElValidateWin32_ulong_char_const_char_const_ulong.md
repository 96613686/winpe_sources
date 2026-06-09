# ElValidateWin32(ulong,char const *,char const *,ulong)

- ea: `0x180001560`
- end: `0x18000161d`
- name: `?ElValidateWin32@@YAKKPEBD0K@Z`
- size: `189`
- prototype: `unsigned int __fastcall(unsigned int, const char *, const char *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001050`
- `0x1800012f0`
- `0x18000145c`

## callees

- `0x180001560`
- `0x180002220`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001600`
- `KERNEL32!SetLastError` at `0x180001600`
- `KERNEL32!GetLastError` at `0x18000158e`
- `KERNEL32!GetLastError` at `0x1800015d1`
- `KERNEL32!GetLastError` at `0x18000158e`
- `KERNEL32!GetLastError` at `0x1800015d1`

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
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &qword_1800034A8, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, &qword_1800034A8, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180001560  mov     [rsp+arg_0], rbx
0x180001565  mov     [rsp+arg_8], rbp
0x18000156a  mov     [rsp+arg_10], rsi
0x18000156f  push    rdi
0x180001570  sub     rsp, 40h
0x180001574  mov     esi, r9d
0x180001577  mov     rbp, r8
0x18000157a  mov     edi, ecx
0x18000157c  test    ecx, ecx
0x18000157e  jz      loc_180001606
0x180001584  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000158c  jz      short loc_1800015C7
0x18000158e  call    cs:__imp_GetLastError
0x180001594  lea     r9, qword_1800034A8
0x18000159b  mov     [rsp+48h+var_20], edi
0x18000159f  mov     [rsp+48h+var_28], r9
0x1800015a4  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800015ab  mov     ebx, eax
0x1800015ad  mov     r9d, esi
0x1800015b0  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800015b7  mov     r8, rbp
0x1800015ba  mov     ecx, 80000h
0x1800015bf  call    cs:__guard_dispatch_icall_fptr
0x1800015c5  jmp     short loc_1800015FE
0x1800015c7  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800015cf  jz      short loc_180001606
0x1800015d1  call    cs:__imp_GetLastError
0x1800015d7  lea     r9, qword_1800034A8
0x1800015de  mov     dword ptr [rsp+48h+var_28], edi
0x1800015e2  mov     ebx, eax
0x1800015e4  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800015eb  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800015f2  mov     r8d, esi
0x1800015f5  mov     rdx, rbp
0x1800015f8  call    cs:__guard_dispatch_icall_fptr
0x1800015fe  mov     ecx, ebx; dwErrCode
0x180001600  call    cs:__imp_SetLastError
0x180001606  mov     rbx, [rsp+48h+arg_0]
0x18000160b  mov     eax, edi
0x18000160d  mov     rbp, [rsp+48h+arg_8]
0x180001612  mov     rsi, [rsp+48h+arg_10]
0x180001617  add     rsp, 40h
0x18000161b  pop     rdi
0x18000161c  retn
```
