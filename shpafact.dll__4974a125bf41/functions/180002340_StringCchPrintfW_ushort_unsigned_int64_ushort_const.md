# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002340`
- end: `0x1800023c4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002460`
- `0x180002dec`
- `0x180003060`

## callees

- `0x180002340`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000237f`
- `msvcrt!_vsnwprintf` at `0x18000237f`

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
0x180002340  mov     [rsp+arg_10], r8
0x180002345  mov     qword ptr [rsp+Args], r9
0x18000234a  push    rbx
0x18000234b  push    rdi
0x18000234c  sub     rsp, 38h
0x180002350  mov     rax, rdx
0x180002353  mov     rdi, rcx
0x180002356  test    rdx, rdx
0x180002359  jz      short loc_1800023AC
0x18000235b  cmp     rax, 7FFFFFFFh
0x180002361  jbe     short loc_18000236A
0x180002363  mov     edx, 80070057h
0x180002368  jmp     short loc_1800023B6
0x18000236a  lea     rbx, [rdx-1]
0x18000236e  mov     [rsp+48h+var_28], 0
0x180002377  mov     rdx, rbx; BufferCount
0x18000237a  lea     r9, [rsp+48h+Args]; Args
0x18000237f  call    cs:__imp__vsnwprintf
0x180002385  test    eax, eax
0x180002387  js      short loc_18000239F
0x180002389  cdqe
0x18000238b  cmp     rax, rbx
0x18000238e  ja      short loc_18000239F
0x180002390  xor     edx, edx
0x180002392  cmp     rax, rbx
0x180002395  jnz     short loc_1800023BB
0x180002397  xor     eax, eax
0x180002399  mov     [rdi+rbx*2], ax
0x18000239d  jmp     short loc_1800023BB
0x18000239f  xor     eax, eax
0x1800023a1  mov     edx, 8007007Ah
0x1800023a6  mov     [rdi+rbx*2], ax
0x1800023aa  jmp     short loc_1800023BB
0x1800023ac  mov     edx, 80070057h
0x1800023b1  test    rax, rax
0x1800023b4  jz      short loc_1800023BB
0x1800023b6  xor     ecx, ecx
0x1800023b8  mov     [rdi], cx
0x1800023bb  mov     eax, edx
0x1800023bd  add     rsp, 38h
0x1800023c1  pop     rdi
0x1800023c2  pop     rbx
0x1800023c3  retn
```
