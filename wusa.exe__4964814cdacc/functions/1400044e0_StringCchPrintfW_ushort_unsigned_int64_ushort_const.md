# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400044e0`
- end: `0x140004564`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1400026bc`
- `0x14000539c`
- `0x140005c70`
- `0x1400075b0`
- `0x14000ab54`
- `0x14000afc0`
- `0x14000b84c`
- `0x14000d620`
- `0x140010800`
- `0x14001181c`
- `0x140012b00`
- `0x140013490`
- `0x1400135a4`

## callees

- `0x1400044e0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000451f`
- `msvcrt!_vsnwprintf` at `0x14000451f`

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
0x1400044e0  mov     [rsp+arg_10], r8
0x1400044e5  mov     qword ptr [rsp+Args], r9
0x1400044ea  push    rbx
0x1400044eb  push    rdi
0x1400044ec  sub     rsp, 38h
0x1400044f0  mov     rax, rdx
0x1400044f3  mov     rdi, rcx
0x1400044f6  test    rdx, rdx
0x1400044f9  jz      short loc_14000454C
0x1400044fb  cmp     rax, 7FFFFFFFh
0x140004501  jbe     short loc_14000450A
0x140004503  mov     edx, 80070057h
0x140004508  jmp     short loc_140004556
0x14000450a  lea     rbx, [rdx-1]
0x14000450e  mov     [rsp+48h+var_28], 0
0x140004517  mov     rdx, rbx; BufferCount
0x14000451a  lea     r9, [rsp+48h+Args]; Args
0x14000451f  call    cs:__imp__vsnwprintf
0x140004525  test    eax, eax
0x140004527  js      short loc_14000453F
0x140004529  cdqe
0x14000452b  cmp     rax, rbx
0x14000452e  ja      short loc_14000453F
0x140004530  xor     edx, edx
0x140004532  cmp     rax, rbx
0x140004535  jnz     short loc_14000455B
0x140004537  xor     eax, eax
0x140004539  mov     [rdi+rbx*2], ax
0x14000453d  jmp     short loc_14000455B
0x14000453f  xor     eax, eax
0x140004541  mov     edx, 8007007Ah
0x140004546  mov     [rdi+rbx*2], ax
0x14000454a  jmp     short loc_14000455B
0x14000454c  mov     edx, 80070057h
0x140004551  test    rax, rax
0x140004554  jz      short loc_14000455B
0x140004556  xor     ecx, ecx
0x140004558  mov     [rdi], cx
0x14000455b  mov     eax, edx
0x14000455d  add     rsp, 38h
0x140004561  pop     rdi
0x140004562  pop     rbx
0x140004563  retn
```
