# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x1800013e8`
- end: `0x18000145b`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `115`
- prototype: `__int64(char *Buffer, __int64, const char *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001338`

## callees

- `0x1800013e8`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180001425`
- `msvcrt!_vsnprintf` at `0x180001425`

## pseudocode

```c
__int64 StringCchPrintfA(char *Buffer, __int64 a2, const char *a3, ...)
{
  int v3; // edi
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list ArgList; // [rsp+58h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  v3 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    v3 = -2147024809;
  if ( v3 < 0 )
  {
    if ( a2 )
      *Buffer = 0;
  }
  else
  {
    v5 = a2 - 1;
    v3 = 0;
    v6 = _vsnprintf(Buffer, a2 - 1, a3, ArgList);
    if ( v6 < 0 || v6 > v5 )
    {
      Buffer[v5] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v6 == v5 )
    {
      Buffer[v5] = 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800013e8  mov     [rsp+arg_10], r8
0x1800013ed  mov     qword ptr [rsp+ArgList], r9
0x1800013f2  push    rbx
0x1800013f3  push    rsi
0x1800013f4  push    rdi
0x1800013f5  sub     rsp, 20h
0x1800013f9  xor     edi, edi
0x1800013fb  lea     rax, [rdx-1]
0x1800013ff  cmp     rax, 7FFFFFFEh
0x180001405  mov     rsi, rcx
0x180001408  mov     ecx, 80070057h
0x18000140d  cmova   edi, ecx
0x180001410  test    edi, edi
0x180001412  js      short loc_180001449
0x180001414  lea     rbx, [rdx-1]
0x180001418  mov     rcx, rsi; Buffer
0x18000141b  mov     rdx, rbx; BufferCount
0x18000141e  lea     r9, [rsp+38h+ArgList]; ArgList
0x180001423  xor     edi, edi
0x180001425  call    cs:__imp__vsnprintf
0x18000142b  test    eax, eax
0x18000142d  js      short loc_18000143E
0x18000142f  cdqe
0x180001431  cmp     rax, rbx
0x180001434  ja      short loc_18000143E
0x180001436  jnz     short loc_180001451
0x180001438  mov     [rbx+rsi], dil
0x18000143c  jmp     short loc_180001451
0x18000143e  mov     [rbx+rsi], dil
0x180001442  mov     edi, 8007007Ah
0x180001447  jmp     short loc_180001451
0x180001449  test    rdx, rdx
0x18000144c  jz      short loc_180001451
0x18000144e  mov     byte ptr [rsi], 0
0x180001451  mov     eax, edi
0x180001453  add     rsp, 20h
0x180001457  pop     rdi
0x180001458  pop     rsi
0x180001459  pop     rbx
0x18000145a  retn
```
