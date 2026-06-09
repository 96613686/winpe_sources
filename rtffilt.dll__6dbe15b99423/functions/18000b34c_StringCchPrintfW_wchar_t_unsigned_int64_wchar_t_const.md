# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x18000b34c`
- end: `0x18000b3cf`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b78`
- `0x180004f48`
- `0x180019a2b`
- `0x180019b59`
- `0x180019c8d`
- `0x180019cf8`
- `0x180019de0`
- `0x18001a063`
- `0x18001a0c2`
- `0x18001a121`
- `0x18001a226`
- `0x18001a4a9`
- `0x18001a508`
- `0x18001a567`
- `0x18001a5c6`

## callees

- `0x18000292c`
- `0x18000b34c`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
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
0x18000b34c  mov     [rsp+arg_10], r8
0x18000b351  mov     qword ptr [rsp+Args], r9
0x18000b356  push    rbx
0x18000b357  push    rdi
0x18000b358  sub     rsp, 38h
0x18000b35c  mov     rax, rdx
0x18000b35f  mov     rdi, rcx
0x18000b362  test    rdx, rdx
0x18000b365  jz      short loc_18000B3B7
0x18000b367  cmp     rax, 7FFFFFFFh
0x18000b36d  jbe     short loc_18000B376
0x18000b36f  mov     edx, 80070057h
0x18000b374  jmp     short loc_18000B3C1
0x18000b376  lea     rbx, [rdx-1]
0x18000b37a  mov     [rsp+48h+var_28], 0
0x18000b383  mov     rdx, rbx; BufferCount
0x18000b386  lea     r9, [rsp+48h+Args]; Args
0x18000b38b  call    _vsnwprintf
0x18000b390  test    eax, eax
0x18000b392  js      short loc_18000B3AA
0x18000b394  cdqe
0x18000b396  cmp     rax, rbx
0x18000b399  ja      short loc_18000B3AA
0x18000b39b  xor     edx, edx
0x18000b39d  cmp     rax, rbx
0x18000b3a0  jnz     short loc_18000B3C6
0x18000b3a2  xor     eax, eax
0x18000b3a4  mov     [rdi+rbx*2], ax
0x18000b3a8  jmp     short loc_18000B3C6
0x18000b3aa  xor     eax, eax
0x18000b3ac  mov     edx, 8007007Ah
0x18000b3b1  mov     [rdi+rbx*2], ax
0x18000b3b5  jmp     short loc_18000B3C6
0x18000b3b7  mov     edx, 80070057h
0x18000b3bc  test    rax, rax
0x18000b3bf  jz      short loc_18000B3C6
0x18000b3c1  xor     ecx, ecx
0x18000b3c3  mov     [rdi], cx
0x18000b3c6  mov     eax, edx
0x18000b3c8  add     rsp, 38h
0x18000b3cc  pop     rdi
0x18000b3cd  pop     rbx
0x18000b3ce  retn
```
