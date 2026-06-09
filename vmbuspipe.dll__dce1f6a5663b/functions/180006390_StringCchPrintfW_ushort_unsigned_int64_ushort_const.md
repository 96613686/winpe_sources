# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006390`
- end: `0x1800063ff`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `111`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001980`
- `0x180001b84`
- `0x180005b68`

## callees

- `0x1800024e0`
- `0x180006390`
- `0x1800064a8`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v4; // ecx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringVPrintfWorkerW(a1, a2, a3, (STRSAFE_LPCWSTR)a3, va);
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180006390  mov     [rsp+arg_10], r8
0x180006395  mov     qword ptr [rsp+arg_18], r9
0x18000639a  sub     rsp, 48h
0x18000639e  mov     rax, cs:__security_cookie
0x1800063a5  xor     rax, rsp
0x1800063a8  mov     [rsp+48h+var_10], rax
0x1800063ad  xor     eax, eax
0x1800063af  mov     r10, rcx
0x1800063b2  test    rdx, rdx
0x1800063b5  jz      short loc_1800063DD
0x1800063b7  cmp     rdx, 7FFFFFFFh
0x1800063be  jbe     short loc_1800063C7
0x1800063c0  mov     ecx, 80070057h; pszDest
0x1800063c5  jmp     short loc_1800063E7
0x1800063c7  lea     rax, [rsp+48h+arg_18]
0x1800063cc  mov     r9, r8; pszFormat
0x1800063cf  mov     [rsp+48h+argList], rax; argList
0x1800063d4  call    StringVPrintfWorkerW
0x1800063d9  mov     ecx, eax
0x1800063db  jmp     short loc_1800063EB
0x1800063dd  mov     ecx, 80070057h
0x1800063e2  test    rdx, rdx
0x1800063e5  jz      short loc_1800063EB
0x1800063e7  mov     [r10], ax
0x1800063eb  mov     eax, ecx
0x1800063ed  mov     rcx, [rsp+48h+var_10]
0x1800063f2  xor     rcx, rsp; StackCookie
0x1800063f5  call    __security_check_cookie
0x1800063fa  add     rsp, 48h
0x1800063fe  retn
```
