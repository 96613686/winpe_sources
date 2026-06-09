# RtlStringCchPrintfW

- ea: `0x180007940`
- end: `0x1800079cb`
- name: `RtlStringCchPrintfW`
- size: `139`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006b7c`
- `0x1800080b0`

## callees

- `0x180007940`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x18000797f`
- `ntdll!_vsnwprintf` at `0x18000797f`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
        v4 = -2147483643;
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
      v4 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x180007940  mov     [rsp+arg_10], r8
0x180007945  mov     qword ptr [rsp+Args], r9
0x18000794a  push    rbx
0x18000794b  push    rdi
0x18000794c  sub     rsp, 38h
0x180007950  mov     rax, rdx
0x180007953  mov     rdi, rcx
0x180007956  test    rdx, rdx
0x180007959  jz      short loc_1800079B2
0x18000795b  cmp     rax, 7FFFFFFFh
0x180007961  jbe     short loc_18000796A
0x180007963  mov     edx, 0C000000Dh
0x180007968  jmp     short loc_1800079BC
0x18000796a  lea     rbx, [rdx-1]
0x18000796e  mov     [rsp+48h+var_28], 0
0x180007977  mov     rdx, rbx; BufferCount
0x18000797a  lea     r9, [rsp+48h+Args]; Args
0x18000797f  call    cs:__imp__vsnwprintf
0x180007986  nop     dword ptr [rax+rax+00h]
0x18000798b  test    eax, eax
0x18000798d  js      short loc_1800079A5
0x18000798f  cdqe
0x180007991  cmp     rax, rbx
0x180007994  ja      short loc_1800079A5
0x180007996  xor     edx, edx
0x180007998  cmp     rax, rbx
0x18000799b  jnz     short loc_1800079C1
0x18000799d  xor     eax, eax
0x18000799f  mov     [rdi+rbx*2], ax
0x1800079a3  jmp     short loc_1800079C1
0x1800079a5  xor     eax, eax
0x1800079a7  mov     edx, 80000005h
0x1800079ac  mov     [rdi+rbx*2], ax
0x1800079b0  jmp     short loc_1800079C1
0x1800079b2  mov     edx, 0C000000Dh
0x1800079b7  test    rax, rax
0x1800079ba  jz      short loc_1800079C1
0x1800079bc  xor     ecx, ecx
0x1800079be  mov     [rdi], cx
0x1800079c1  mov     eax, edx
0x1800079c3  add     rsp, 38h
0x1800079c7  pop     rdi
0x1800079c8  pop     rbx
0x1800079c9  retn
```
