# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x1800097b0`
- end: `0x180009834`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `132`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008080`
- `0x18000f3eb`
- `0x18000f4e3`
- `0x18000f617`
- `0x18000f682`

## callees

- `0x1800097b0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800097ef`
- `msvcrt!_vsnwprintf` at `0x1800097ef`

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
0x1800097b0  mov     [rsp+arg_10], r8
0x1800097b5  mov     qword ptr [rsp+Args], r9
0x1800097ba  push    rbx
0x1800097bb  push    rdi
0x1800097bc  sub     rsp, 38h
0x1800097c0  mov     rax, rdx
0x1800097c3  mov     rdi, rcx
0x1800097c6  test    rdx, rdx
0x1800097c9  jz      short loc_18000981C
0x1800097cb  cmp     rax, 7FFFFFFFh
0x1800097d1  jbe     short loc_1800097DA
0x1800097d3  mov     edx, 80070057h
0x1800097d8  jmp     short loc_180009826
0x1800097da  lea     rbx, [rdx-1]
0x1800097de  mov     [rsp+48h+var_28], 0
0x1800097e7  mov     rdx, rbx; BufferCount
0x1800097ea  lea     r9, [rsp+48h+Args]; Args
0x1800097ef  call    cs:__imp__vsnwprintf
0x1800097f5  test    eax, eax
0x1800097f7  js      short loc_18000980F
0x1800097f9  cdqe
0x1800097fb  cmp     rax, rbx
0x1800097fe  ja      short loc_18000980F
0x180009800  xor     edx, edx
0x180009802  cmp     rax, rbx
0x180009805  jnz     short loc_18000982B
0x180009807  xor     eax, eax
0x180009809  mov     [rdi+rbx*2], ax
0x18000980d  jmp     short loc_18000982B
0x18000980f  xor     eax, eax
0x180009811  mov     edx, 8007007Ah
0x180009816  mov     [rdi+rbx*2], ax
0x18000981a  jmp     short loc_18000982B
0x18000981c  mov     edx, 80070057h
0x180009821  test    rax, rax
0x180009824  jz      short loc_18000982B
0x180009826  xor     ecx, ecx
0x180009828  mov     [rdi], cx
0x18000982b  mov     eax, edx
0x18000982d  add     rsp, 38h
0x180009831  pop     rdi
0x180009832  pop     rbx
0x180009833  retn
```
