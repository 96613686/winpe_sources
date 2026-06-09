# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400068c0`
- end: `0x140006944`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bd0`
- `0x1400055d8`

## callees

- `0x1400068c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400068ff`
- `msvcrt!_vsnwprintf` at `0x1400068ff`

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
0x1400068c0  mov     [rsp+arg_10], r8
0x1400068c5  mov     qword ptr [rsp+Args], r9
0x1400068ca  push    rbx
0x1400068cb  push    rdi
0x1400068cc  sub     rsp, 38h
0x1400068d0  mov     rax, rdx
0x1400068d3  mov     rdi, rcx
0x1400068d6  test    rdx, rdx
0x1400068d9  jz      short loc_14000692C
0x1400068db  cmp     rax, 7FFFFFFFh
0x1400068e1  jbe     short loc_1400068EA
0x1400068e3  mov     edx, 80070057h
0x1400068e8  jmp     short loc_140006936
0x1400068ea  lea     rbx, [rdx-1]
0x1400068ee  mov     [rsp+48h+var_28], 0
0x1400068f7  mov     rdx, rbx; BufferCount
0x1400068fa  lea     r9, [rsp+48h+Args]; Args
0x1400068ff  call    cs:__imp__vsnwprintf
0x140006905  test    eax, eax
0x140006907  js      short loc_14000691F
0x140006909  cdqe
0x14000690b  cmp     rax, rbx
0x14000690e  ja      short loc_14000691F
0x140006910  xor     edx, edx
0x140006912  cmp     rax, rbx
0x140006915  jnz     short loc_14000693B
0x140006917  xor     eax, eax
0x140006919  mov     [rdi+rbx*2], ax
0x14000691d  jmp     short loc_14000693B
0x14000691f  xor     eax, eax
0x140006921  mov     edx, 8007007Ah
0x140006926  mov     [rdi+rbx*2], ax
0x14000692a  jmp     short loc_14000693B
0x14000692c  mov     edx, 80070057h
0x140006931  test    rax, rax
0x140006934  jz      short loc_14000693B
0x140006936  xor     ecx, ecx
0x140006938  mov     [rdi], cx
0x14000693b  mov     eax, edx
0x14000693d  add     rsp, 38h
0x140006941  pop     rdi
0x140006942  pop     rbx
0x140006943  retn
```
