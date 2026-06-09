# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400090b0`
- end: `0x140009134`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400054ac`
- `0x140005850`
- `0x14000b434`
- `0x14000c018`

## callees

- `0x1400090b0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400090ef`
- `msvcrt!_vsnwprintf` at `0x1400090ef`

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
0x1400090b0  mov     [rsp+arg_10], r8
0x1400090b5  mov     qword ptr [rsp+Args], r9
0x1400090ba  push    rbx
0x1400090bb  push    rdi
0x1400090bc  sub     rsp, 38h
0x1400090c0  mov     rax, rdx
0x1400090c3  mov     rdi, rcx
0x1400090c6  test    rdx, rdx
0x1400090c9  jz      short loc_14000911C
0x1400090cb  cmp     rax, 7FFFFFFFh
0x1400090d1  jbe     short loc_1400090DA
0x1400090d3  mov     edx, 80070057h
0x1400090d8  jmp     short loc_140009126
0x1400090da  lea     rbx, [rdx-1]
0x1400090de  mov     [rsp+48h+var_28], 0
0x1400090e7  mov     rdx, rbx; BufferCount
0x1400090ea  lea     r9, [rsp+48h+Args]; Args
0x1400090ef  call    cs:__imp__vsnwprintf
0x1400090f5  test    eax, eax
0x1400090f7  js      short loc_14000910F
0x1400090f9  cdqe
0x1400090fb  cmp     rax, rbx
0x1400090fe  ja      short loc_14000910F
0x140009100  xor     edx, edx
0x140009102  cmp     rax, rbx
0x140009105  jnz     short loc_14000912B
0x140009107  xor     eax, eax
0x140009109  mov     [rdi+rbx*2], ax
0x14000910d  jmp     short loc_14000912B
0x14000910f  xor     eax, eax
0x140009111  mov     edx, 8007007Ah
0x140009116  mov     [rdi+rbx*2], ax
0x14000911a  jmp     short loc_14000912B
0x14000911c  mov     edx, 80070057h
0x140009121  test    rax, rax
0x140009124  jz      short loc_14000912B
0x140009126  xor     ecx, ecx
0x140009128  mov     [rdi], cx
0x14000912b  mov     eax, edx
0x14000912d  add     rsp, 38h
0x140009131  pop     rdi
0x140009132  pop     rbx
0x140009133  retn
```
