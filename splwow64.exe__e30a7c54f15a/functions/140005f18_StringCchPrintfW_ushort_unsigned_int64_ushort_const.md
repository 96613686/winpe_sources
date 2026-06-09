# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005f18`
- end: `0x140005f9b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400036fc`
- `0x14000719c`
- `0x1400073ac`
- `0x14000805c`
- `0x140009214`
- `0x14000f9cc`
- `0x14000fae0`

## callees

- `0x1400028c4`
- `0x140005f18`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
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
0x140005f18  mov     [rsp+arg_10], r8
0x140005f1d  mov     qword ptr [rsp+Args], r9
0x140005f22  push    rbx
0x140005f23  push    rdi
0x140005f24  sub     rsp, 38h
0x140005f28  mov     rax, rdx
0x140005f2b  mov     rdi, rcx
0x140005f2e  test    rdx, rdx
0x140005f31  jz      short loc_140005F83
0x140005f33  cmp     rax, 7FFFFFFFh
0x140005f39  jbe     short loc_140005F42
0x140005f3b  mov     edx, 80070057h
0x140005f40  jmp     short loc_140005F8D
0x140005f42  lea     rbx, [rdx-1]
0x140005f46  mov     [rsp+48h+var_28], 0
0x140005f4f  mov     rdx, rbx; BufferCount
0x140005f52  lea     r9, [rsp+48h+Args]; Args
0x140005f57  call    _vsnwprintf
0x140005f5c  test    eax, eax
0x140005f5e  js      short loc_140005F76
0x140005f60  cdqe
0x140005f62  cmp     rax, rbx
0x140005f65  ja      short loc_140005F76
0x140005f67  xor     edx, edx
0x140005f69  cmp     rax, rbx
0x140005f6c  jnz     short loc_140005F92
0x140005f6e  xor     eax, eax
0x140005f70  mov     [rdi+rbx*2], ax
0x140005f74  jmp     short loc_140005F92
0x140005f76  xor     eax, eax
0x140005f78  mov     edx, 8007007Ah
0x140005f7d  mov     [rdi+rbx*2], ax
0x140005f81  jmp     short loc_140005F92
0x140005f83  mov     edx, 80070057h
0x140005f88  test    rax, rax
0x140005f8b  jz      short loc_140005F92
0x140005f8d  xor     ecx, ecx
0x140005f8f  mov     [rdi], cx
0x140005f92  mov     eax, edx
0x140005f94  add     rsp, 38h
0x140005f98  pop     rdi
0x140005f99  pop     rbx
0x140005f9a  retn
```
