# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800050cc`
- end: `0x18000514f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003220`
- `0x1800039f0`
- `0x1800047c0`
- `0x180005df0`
- `0x180006fbc`
- `0x18001721c`

## callees

- `0x180001f28`
- `0x1800050cc`

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
0x1800050cc  mov     [rsp+arg_10], r8
0x1800050d1  mov     qword ptr [rsp+Args], r9
0x1800050d6  push    rbx
0x1800050d7  push    rdi
0x1800050d8  sub     rsp, 38h
0x1800050dc  mov     rax, rdx
0x1800050df  mov     rdi, rcx
0x1800050e2  test    rdx, rdx
0x1800050e5  jz      short loc_180005137
0x1800050e7  cmp     rax, 7FFFFFFFh
0x1800050ed  jbe     short loc_1800050F6
0x1800050ef  mov     edx, 80070057h
0x1800050f4  jmp     short loc_180005141
0x1800050f6  lea     rbx, [rdx-1]
0x1800050fa  mov     [rsp+48h+var_28], 0
0x180005103  mov     rdx, rbx; BufferCount
0x180005106  lea     r9, [rsp+48h+Args]; Args
0x18000510b  call    _vsnwprintf
0x180005110  test    eax, eax
0x180005112  js      short loc_18000512A
0x180005114  cdqe
0x180005116  cmp     rax, rbx
0x180005119  ja      short loc_18000512A
0x18000511b  xor     edx, edx
0x18000511d  cmp     rax, rbx
0x180005120  jnz     short loc_180005146
0x180005122  xor     eax, eax
0x180005124  mov     [rdi+rbx*2], ax
0x180005128  jmp     short loc_180005146
0x18000512a  xor     eax, eax
0x18000512c  mov     edx, 8007007Ah
0x180005131  mov     [rdi+rbx*2], ax
0x180005135  jmp     short loc_180005146
0x180005137  mov     edx, 80070057h
0x18000513c  test    rax, rax
0x18000513f  jz      short loc_180005146
0x180005141  xor     ecx, ecx
0x180005143  mov     [rdi], cx
0x180005146  mov     eax, edx
0x180005148  add     rsp, 38h
0x18000514c  pop     rdi
0x18000514d  pop     rbx
0x18000514e  retn
```
