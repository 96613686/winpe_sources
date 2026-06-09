# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000b598`
- end: `0x18000b61b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c90`
- `0x180005060`
- `0x18000e81c`
- `0x18000ed10`
- `0x180016aa8`

## callees

- `0x18000b598`
- `0x18000d7a0`

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
0x18000b598  mov     [rsp+arg_10], r8
0x18000b59d  mov     qword ptr [rsp+Args], r9
0x18000b5a2  push    rbx
0x18000b5a3  push    rdi
0x18000b5a4  sub     rsp, 38h
0x18000b5a8  mov     rax, rdx
0x18000b5ab  mov     rdi, rcx
0x18000b5ae  test    rdx, rdx
0x18000b5b1  jz      short loc_18000B603
0x18000b5b3  cmp     rax, 7FFFFFFFh
0x18000b5b9  jbe     short loc_18000B5C2
0x18000b5bb  mov     edx, 80070057h
0x18000b5c0  jmp     short loc_18000B60D
0x18000b5c2  lea     rbx, [rdx-1]
0x18000b5c6  mov     [rsp+48h+var_28], 0
0x18000b5cf  mov     rdx, rbx; BufferCount
0x18000b5d2  lea     r9, [rsp+48h+Args]; Args
0x18000b5d7  call    _vsnwprintf
0x18000b5dc  test    eax, eax
0x18000b5de  js      short loc_18000B5F6
0x18000b5e0  cdqe
0x18000b5e2  cmp     rax, rbx
0x18000b5e5  ja      short loc_18000B5F6
0x18000b5e7  xor     edx, edx
0x18000b5e9  cmp     rax, rbx
0x18000b5ec  jnz     short loc_18000B612
0x18000b5ee  xor     eax, eax
0x18000b5f0  mov     [rdi+rbx*2], ax
0x18000b5f4  jmp     short loc_18000B612
0x18000b5f6  xor     eax, eax
0x18000b5f8  mov     edx, 8007007Ah
0x18000b5fd  mov     [rdi+rbx*2], ax
0x18000b601  jmp     short loc_18000B612
0x18000b603  mov     edx, 80070057h
0x18000b608  test    rax, rax
0x18000b60b  jz      short loc_18000B612
0x18000b60d  xor     ecx, ecx
0x18000b60f  mov     [rdi], cx
0x18000b612  mov     eax, edx
0x18000b614  add     rsp, 38h
0x18000b618  pop     rdi
0x18000b619  pop     rbx
0x18000b61a  retn
```
