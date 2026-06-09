# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000c740`
- end: `0x18000c79d`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001670`
- `0x180007f30`
- `0x180008098`
- `0x18000cd44`

## callees

- `0x18000c740`
- `0x18000c7fc`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v3; // edx
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
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c740  mov     [rsp+arg_10], r8
0x18000c745  mov     qword ptr [rsp+arg_18], r9
0x18000c74a  sub     rsp, 48h
0x18000c74e  mov     rax, rdx
0x18000c751  test    rdx, rdx
0x18000c754  jz      short loc_18000C787
0x18000c756  cmp     rax, 7FFFFFFFh
0x18000c75c  jbe     short loc_18000C765
0x18000c75e  mov     edx, 80070057h
0x18000c763  jmp     short loc_18000C791
0x18000c765  lea     rdx, [rsp+48h+arg_18]
0x18000c76a  mov     [rsp+48h+var_18], 0
0x18000c773  mov     [rsp+48h+argList], rdx; argList
0x18000c778  mov     r9, r8; pszFormat
0x18000c77b  mov     rdx, rax; cchDest
0x18000c77e  call    StringVPrintfWorkerW
0x18000c783  mov     edx, eax
0x18000c785  jmp     short loc_18000C796
0x18000c787  mov     edx, 80070057h
0x18000c78c  test    rax, rax
0x18000c78f  jz      short loc_18000C796
0x18000c791  xor     eax, eax
0x18000c793  mov     [rcx], ax
0x18000c796  mov     eax, edx
0x18000c798  add     rsp, 48h
0x18000c79c  retn
```
