# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005684`
- end: `0x180005708`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000383c`
- `0x180006604`
- `0x180009600`
- `0x18001a148`

## callees

- `0x180005684`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800056c3`
- `msvcrt!_vsnwprintf` at `0x1800056c3`

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
0x180005684  mov     [rsp+arg_10], r8
0x180005689  mov     qword ptr [rsp+Args], r9
0x18000568e  push    rbx
0x18000568f  push    rdi
0x180005690  sub     rsp, 38h
0x180005694  mov     rax, rdx
0x180005697  mov     rdi, rcx
0x18000569a  test    rdx, rdx
0x18000569d  jz      short loc_1800056F0
0x18000569f  cmp     rax, 7FFFFFFFh
0x1800056a5  jbe     short loc_1800056AE
0x1800056a7  mov     edx, 80070057h
0x1800056ac  jmp     short loc_1800056FA
0x1800056ae  lea     rbx, [rdx-1]
0x1800056b2  mov     [rsp+48h+var_28], 0
0x1800056bb  mov     rdx, rbx; BufferCount
0x1800056be  lea     r9, [rsp+48h+Args]; Args
0x1800056c3  call    cs:__imp__vsnwprintf
0x1800056c9  test    eax, eax
0x1800056cb  js      short loc_1800056E3
0x1800056cd  cdqe
0x1800056cf  cmp     rax, rbx
0x1800056d2  ja      short loc_1800056E3
0x1800056d4  xor     edx, edx
0x1800056d6  cmp     rax, rbx
0x1800056d9  jnz     short loc_1800056FF
0x1800056db  xor     eax, eax
0x1800056dd  mov     [rdi+rbx*2], ax
0x1800056e1  jmp     short loc_1800056FF
0x1800056e3  xor     eax, eax
0x1800056e5  mov     edx, 8007007Ah
0x1800056ea  mov     [rdi+rbx*2], ax
0x1800056ee  jmp     short loc_1800056FF
0x1800056f0  mov     edx, 80070057h
0x1800056f5  test    rax, rax
0x1800056f8  jz      short loc_1800056FF
0x1800056fa  xor     ecx, ecx
0x1800056fc  mov     [rdi], cx
0x1800056ff  mov     eax, edx
0x180005701  add     rsp, 38h
0x180005705  pop     rdi
0x180005706  pop     rbx
0x180005707  retn
```
