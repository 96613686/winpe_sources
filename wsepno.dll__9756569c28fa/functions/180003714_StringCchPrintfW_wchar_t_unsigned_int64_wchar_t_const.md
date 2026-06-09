# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180003714`
- end: `0x180003797`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x18000558c`
- `0x18000595c`
- `0x1800068e0`
- `0x180006b50`
- `0x18000890c`
- `0x18000b4e8`
- `0x18000d000`
- `0x18000d0dc`
- `0x18000d2f8`
- `0x18000d918`
- `0x18000da10`
- `0x18000db44`
- `0x18000dbaf`
- `0x18000de35`
- `0x18000e0b8`
- `0x18000e117`
- `0x18000e176`
- `0x18000e27b`
- `0x18000e4fe`
- `0x18000e55d`
- `0x18000e5bc`
- `0x18000e61b`

## callees

- `0x18000220c`
- `0x180003714`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
0x180003714  mov     [rsp+arg_10], r8
0x180003719  mov     qword ptr [rsp+Args], r9
0x18000371e  push    rbx
0x18000371f  push    rdi
0x180003720  sub     rsp, 38h
0x180003724  mov     rax, rdx
0x180003727  mov     rdi, rcx
0x18000372a  test    rdx, rdx
0x18000372d  jz      short loc_18000377F
0x18000372f  cmp     rax, 7FFFFFFFh
0x180003735  jbe     short loc_18000373E
0x180003737  mov     edx, 80070057h
0x18000373c  jmp     short loc_180003789
0x18000373e  lea     rbx, [rdx-1]
0x180003742  mov     [rsp+48h+var_28], 0
0x18000374b  mov     rdx, rbx; BufferCount
0x18000374e  lea     r9, [rsp+48h+Args]; Args
0x180003753  call    _vsnwprintf
0x180003758  test    eax, eax
0x18000375a  js      short loc_180003772
0x18000375c  cdqe
0x18000375e  cmp     rax, rbx
0x180003761  ja      short loc_180003772
0x180003763  xor     edx, edx
0x180003765  cmp     rax, rbx
0x180003768  jnz     short loc_18000378E
0x18000376a  xor     eax, eax
0x18000376c  mov     [rdi+rbx*2], ax
0x180003770  jmp     short loc_18000378E
0x180003772  xor     eax, eax
0x180003774  mov     edx, 8007007Ah
0x180003779  mov     [rdi+rbx*2], ax
0x18000377d  jmp     short loc_18000378E
0x18000377f  mov     edx, 80070057h
0x180003784  test    rax, rax
0x180003787  jz      short loc_18000378E
0x180003789  xor     ecx, ecx
0x18000378b  mov     [rdi], cx
0x18000378e  mov     eax, edx
0x180003790  add     rsp, 38h
0x180003794  pop     rdi
0x180003795  pop     rbx
0x180003796  retn
```
