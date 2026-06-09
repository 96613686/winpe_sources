# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140002628`
- end: `0x1400026ac`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027b0`

## callees

- `0x140002628`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140002667`
- `msvcrt!_vsnwprintf` at `0x140002667`

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
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
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
0x140002628  mov     [rsp+arg_10], r8
0x14000262d  mov     qword ptr [rsp+Args], r9
0x140002632  push    rbx
0x140002633  push    rdi
0x140002634  sub     rsp, 38h
0x140002638  mov     rax, rdx
0x14000263b  mov     rdi, rcx
0x14000263e  test    rdx, rdx
0x140002641  jz      short loc_140002694
0x140002643  cmp     rax, 7FFFFFFFh
0x140002649  jbe     short loc_140002652
0x14000264b  mov     edx, 80070057h
0x140002650  jmp     short loc_14000269E
0x140002652  lea     rbx, [rdx-1]
0x140002656  mov     [rsp+48h+var_28], 0
0x14000265f  mov     rdx, rbx; BufferCount
0x140002662  lea     r9, [rsp+48h+Args]; Args
0x140002667  call    cs:__imp__vsnwprintf
0x14000266d  test    eax, eax
0x14000266f  js      short loc_140002687
0x140002671  cdqe
0x140002673  cmp     rax, rbx
0x140002676  ja      short loc_140002687
0x140002678  xor     edx, edx
0x14000267a  cmp     rax, rbx
0x14000267d  jnz     short loc_1400026A3
0x14000267f  xor     eax, eax
0x140002681  mov     [rdi+rbx*2], ax
0x140002685  jmp     short loc_1400026A3
0x140002687  xor     eax, eax
0x140002689  mov     edx, 8007007Ah
0x14000268e  mov     [rdi+rbx*2], ax
0x140002692  jmp     short loc_1400026A3
0x140002694  mov     edx, 80070057h
0x140002699  test    rax, rax
0x14000269c  jz      short loc_1400026A3
0x14000269e  xor     ecx, ecx
0x1400026a0  mov     [rdi], cx
0x1400026a3  mov     eax, edx
0x1400026a5  add     rsp, 38h
0x1400026a9  pop     rdi
0x1400026aa  pop     rbx
0x1400026ab  retn
```
