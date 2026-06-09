# ElValidateWin32(ulong,char const *,char const *,ulong)

- ea: `0x180014d58`
- end: `0x180014e15`
- name: `?ElValidateWin32@@YAKKPEBD0K@Z`
- size: `189`
- prototype: `unsigned int __fastcall(unsigned int, const char *, const char *, unsigned int)`
- caller_count: `141`
- callee_count: `2`
- tags: ``

## callers

- `0x1800013d0`
- `0x180001660`
- `0x1800016f0`
- `0x180001790`
- `0x180001870`
- `0x180001900`
- `0x1800019d0`
- `0x180001e14`
- `0x180002268`
- `0x1800026ac`
- `0x18000294c`
- `0x180002bd8`
- `0x180003398`
- `0x180003508`
- `0x1800036dc`
- `0x180003acc`
- `0x1800040ac`
- `0x1800042f4`
- `0x180004dbc`
- `0x180004f98`
- `0x1800051e8`
- `0x180005430`
- `0x18000563c`
- `0x180005818`
- `0x18000600c`
- `0x1800062f0`
- `0x1800063b4`
- `0x1800068b8`
- `0x1800069dc`
- `0x180006d2c`
- `0x180006dfc`
- `0x180007570`
- `0x180007f90`
- `0x180008aa0`
- `0x180008b68`
- `0x180008db4`
- `0x180009074`
- `0x180009164`
- `0x1800092a8`
- `0x180009680`
- `0x180009894`
- `0x180009b3c`
- `0x180009c30`
- `0x180009c94`
- `0x18000a15c`
- `0x18000a644`
- `0x18000a970`
- `0x18000aaac`
- `0x18000ab70`
- `0x18000ac50`

## callees

- `0x180014d58`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014d86`
- `KERNEL32!GetLastError` at `0x180014dc9`
- `KERNEL32!GetLastError` at `0x180014d86`
- `KERNEL32!GetLastError` at `0x180014dc9`
- `KERNEL32!SetLastError` at `0x180014df8`
- `KERNEL32!SetLastError` at `0x180014df8`

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
      g_ErrLibTraceFunctionEx(0x80000u, L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, qword_180018290, a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(L"[%S:%u] Expression: %S, Win32 Error=0x%x", a3, a4, qword_180018290, a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180014d58  mov     [rsp+arg_0], rbx
0x180014d5d  mov     [rsp+arg_8], rbp
0x180014d62  mov     [rsp+arg_10], rsi
0x180014d67  push    rdi
0x180014d68  sub     rsp, 40h
0x180014d6c  mov     esi, r9d
0x180014d6f  mov     rbp, r8
0x180014d72  mov     edi, ecx
0x180014d74  test    ecx, ecx
0x180014d76  jz      loc_180014DFE
0x180014d7c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014d84  jz      short loc_180014DBF
0x180014d86  call    cs:__imp_GetLastError
0x180014d8c  lea     r9, qword_180018290
0x180014d93  mov     [rsp+48h+var_20], edi
0x180014d97  mov     [rsp+48h+var_28], r9
0x180014d9c  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180014da3  mov     ebx, eax
0x180014da5  mov     r9d, esi
0x180014da8  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180014daf  mov     r8, rbp
0x180014db2  mov     ecx, 80000h
0x180014db7  call    cs:__guard_dispatch_icall_fptr
0x180014dbd  jmp     short loc_180014DF6
0x180014dbf  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014dc7  jz      short loc_180014DFE
0x180014dc9  call    cs:__imp_GetLastError
0x180014dcf  lea     r9, qword_180018290
0x180014dd6  mov     dword ptr [rsp+48h+var_28], edi
0x180014dda  mov     ebx, eax
0x180014ddc  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180014de3  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180014dea  mov     r8d, esi
0x180014ded  mov     rdx, rbp
0x180014df0  call    cs:__guard_dispatch_icall_fptr
0x180014df6  mov     ecx, ebx; dwErrCode
0x180014df8  call    cs:__imp_SetLastError
0x180014dfe  mov     rbx, [rsp+48h+arg_0]
0x180014e03  mov     eax, edi
0x180014e05  mov     rbp, [rsp+48h+arg_8]
0x180014e0a  mov     rsi, [rsp+48h+arg_10]
0x180014e0f  add     rsp, 40h
0x180014e13  pop     rdi
0x180014e14  retn
```
