# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140002860`
- end: `0x1400028eb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a40`

## callees

- `0x140002860`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000289f`
- `msvcrt!_vsnwprintf` at `0x14000289f`

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
0x140002860  mov     [rsp+arg_10], r8
0x140002865  mov     qword ptr [rsp+Args], r9
0x14000286a  push    rbx
0x14000286b  push    rdi
0x14000286c  sub     rsp, 38h
0x140002870  mov     rax, rdx
0x140002873  mov     rdi, rcx
0x140002876  test    rdx, rdx
0x140002879  jz      short loc_1400028D2
0x14000287b  cmp     rax, 7FFFFFFFh
0x140002881  jbe     short loc_14000288A
0x140002883  mov     edx, 80070057h
0x140002888  jmp     short loc_1400028DC
0x14000288a  lea     rbx, [rdx-1]
0x14000288e  mov     [rsp+48h+var_28], 0
0x140002897  mov     rdx, rbx; BufferCount
0x14000289a  lea     r9, [rsp+48h+Args]; Args
0x14000289f  call    cs:__imp__vsnwprintf
0x1400028a6  nop     dword ptr [rax+rax+00h]
0x1400028ab  test    eax, eax
0x1400028ad  js      short loc_1400028C5
0x1400028af  cdqe
0x1400028b1  cmp     rax, rbx
0x1400028b4  ja      short loc_1400028C5
0x1400028b6  xor     edx, edx
0x1400028b8  cmp     rax, rbx
0x1400028bb  jnz     short loc_1400028E1
0x1400028bd  xor     eax, eax
0x1400028bf  mov     [rdi+rbx*2], ax
0x1400028c3  jmp     short loc_1400028E1
0x1400028c5  xor     eax, eax
0x1400028c7  mov     edx, 8007007Ah
0x1400028cc  mov     [rdi+rbx*2], ax
0x1400028d0  jmp     short loc_1400028E1
0x1400028d2  mov     edx, 80070057h
0x1400028d7  test    rax, rax
0x1400028da  jz      short loc_1400028E1
0x1400028dc  xor     ecx, ecx
0x1400028de  mov     [rdi], cx
0x1400028e1  mov     eax, edx
0x1400028e3  add     rsp, 38h
0x1400028e7  pop     rdi
0x1400028e8  pop     rbx
0x1400028e9  retn
```
