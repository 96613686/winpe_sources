# ElValidateHrWithExceptions

- ea: `0x180007934`
- end: `0x1800079bf`
- name: `ElValidateHrWithExceptions`
- size: `139`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b90`
- `0x180007d60`
- `0x180007ec8`
- `0x180007fd4`
- `0x180008b50`

## callees

- `0x18000785c`
- `0x180007934`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000795b`
- `KERNEL32!GetLastError` at `0x18000795b`
- `KERNEL32!SetLastError` at `0x1800079a3`
- `KERNEL32!SetLastError` at `0x1800079a3`

## pseudocode

```c
__int64 ElValidateHrWithExceptions(int a1, __int64 a2, __int64 a3, _DWORD a4, unsigned int a5, ...)
{
  int v5; // ebx
  DWORD LastError; // esi
  unsigned int *v10; // rcx

  v5 = 0;
  if ( a1 < 0 && g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    if ( a5 )
    {
      v10 = &a5;
      while ( 1 )
      {
        v10 += 2;
        if ( a1 == *v10 )
          break;
        if ( ++v5 >= a5 )
          goto LABEL_7;
      }
    }
    else
    {
LABEL_7:
      ElValidateHrLite((unsigned int)a1, a2, a3);
    }
    SetLastError(LastError);
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180007934  push    rbx
0x180007936  push    rbp
0x180007937  push    rsi
0x180007938  push    rdi
0x180007939  push    r14
0x18000793b  push    r15
0x18000793d  sub     rsp, 38h
0x180007941  xor     ebx, ebx
0x180007943  mov     ebp, r9d
0x180007946  mov     r14, r8
0x180007949  mov     r15, rdx
0x18000794c  mov     edi, ecx
0x18000794e  test    ecx, ecx
0x180007950  jns     short loc_1800079AF
0x180007952  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, rbx; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180007959  jz      short loc_1800079AF
0x18000795b  call    cs:__imp_GetLastError
0x180007962  nop     dword ptr [rax+rax+00h]
0x180007967  lea     rcx, [rsp+68h+arg_28]
0x18000796f  mov     esi, eax
0x180007971  cmp     [rsp+68h+arg_20], ebx
0x180007978  jbe     short loc_180007991
0x18000797a  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000797e  lea     rcx, [rcx+8]
0x180007982  cmp     edi, [rcx]
0x180007984  jz      short loc_1800079A1
0x180007986  inc     ebx
0x180007988  cmp     ebx, [rsp+68h+arg_20]
0x18000798f  jb      short loc_18000797E
0x180007991  mov     r9d, ebp
0x180007994  mov     r8, r14
0x180007997  mov     rdx, r15
0x18000799a  mov     ecx, edi
0x18000799c  call    ElValidateHrLite
0x1800079a1  mov     ecx, esi; dwErrCode
0x1800079a3  call    cs:__imp_SetLastError
0x1800079aa  nop     dword ptr [rax+rax+00h]
0x1800079af  mov     eax, edi
0x1800079b1  add     rsp, 38h
0x1800079b5  pop     r15
0x1800079b7  pop     r14
0x1800079b9  pop     rdi
0x1800079ba  pop     rsi
0x1800079bb  pop     rbp
0x1800079bc  pop     rbx
0x1800079bd  retn
```
