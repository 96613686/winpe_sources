# RtlStringCchPrintfW

- ea: `0x180001d48`
- end: `0x180001dcc`
- name: `RtlStringCchPrintfW`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002cc8`
- `0x18000c73c`
- `0x18000d620`
- `0x18000e8d4`

## callees

- `0x180001d48`

## import_xrefs

- `ntdll!_vsnwprintf` at `0x180001d87`
- `ntdll!_vsnwprintf` at `0x180001d87`

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
0x180001d48  mov     [rsp+arg_10], r8
0x180001d4d  mov     qword ptr [rsp+Args], r9
0x180001d52  push    rbx
0x180001d53  push    rdi
0x180001d54  sub     rsp, 38h
0x180001d58  mov     rax, rdx
0x180001d5b  mov     rdi, rcx
0x180001d5e  test    rdx, rdx
0x180001d61  jz      short loc_180001DB4
0x180001d63  cmp     rax, 7FFFFFFFh
0x180001d69  jbe     short loc_180001D72
0x180001d6b  mov     edx, 0C000000Dh
0x180001d70  jmp     short loc_180001DBE
0x180001d72  lea     rbx, [rdx-1]
0x180001d76  mov     [rsp+48h+var_28], 0
0x180001d7f  mov     rdx, rbx; BufferCount
0x180001d82  lea     r9, [rsp+48h+Args]; Args
0x180001d87  call    cs:__imp__vsnwprintf
0x180001d8d  test    eax, eax
0x180001d8f  js      short loc_180001DA7
0x180001d91  cdqe
0x180001d93  cmp     rax, rbx
0x180001d96  ja      short loc_180001DA7
0x180001d98  xor     edx, edx
0x180001d9a  cmp     rax, rbx
0x180001d9d  jnz     short loc_180001DC3
0x180001d9f  xor     eax, eax
0x180001da1  mov     [rdi+rbx*2], ax
0x180001da5  jmp     short loc_180001DC3
0x180001da7  xor     eax, eax
0x180001da9  mov     edx, 80000005h
0x180001dae  mov     [rdi+rbx*2], ax
0x180001db2  jmp     short loc_180001DC3
0x180001db4  mov     edx, 0C000000Dh
0x180001db9  test    rax, rax
0x180001dbc  jz      short loc_180001DC3
0x180001dbe  xor     ecx, ecx
0x180001dc0  mov     [rdi], cx
0x180001dc3  mov     eax, edx
0x180001dc5  add     rsp, 38h
0x180001dc9  pop     rdi
0x180001dca  pop     rbx
0x180001dcb  retn
```
