# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002ae0`
- end: `0x180002b5e`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `126`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001de4`
- `0x180002660`
- `0x180008790`
- `0x18000a99c`
- `0x18000d094`
- `0x18000f3d8`

## callees

- `0x180002ae0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002b14`
- `msvcrt!_vsnwprintf` at `0x180002b14`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v6 == v4 )
    {
      a1[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180002ae0  mov     [rsp+arg_10], r8
0x180002ae5  mov     qword ptr [rsp+Args], r9
0x180002aea  push    rsi
0x180002aeb  push    rdi
0x180002aec  sub     rsp, 38h
0x180002af0  mov     rsi, rcx
0x180002af3  test    rdx, rdx
0x180002af6  jz      short loc_180002B4D
0x180002af8  cmp     rdx, 7FFFFFFFh
0x180002aff  ja      short loc_180002B35
0x180002b01  mov     [rsp+48h+var_18], rbx
0x180002b06  lea     r9, [rsp+48h+Args]; Args
0x180002b0b  lea     rbx, [rdx-1]
0x180002b0f  xor     edi, edi
0x180002b11  mov     rdx, rbx; BufferCount
0x180002b14  call    cs:__imp__vsnwprintf
0x180002b1a  test    eax, eax
0x180002b1c  js      short loc_180002B42
0x180002b1e  cdqe
0x180002b20  cmp     rax, rbx
0x180002b23  ja      short loc_180002B42
0x180002b25  jz      short loc_180002B3C
0x180002b27  mov     rbx, [rsp+48h+var_18]
0x180002b2c  mov     eax, edi
0x180002b2e  add     rsp, 38h
0x180002b32  pop     rdi
0x180002b33  pop     rsi
0x180002b34  retn
0x180002b35  mov     eax, 80070057h
0x180002b3a  jmp     short loc_180002B57
0x180002b3c  mov     [rsi+rbx*2], di
0x180002b40  jmp     short loc_180002B27
0x180002b42  mov     [rsi+rbx*2], di
0x180002b46  mov     edi, 8007007Ah
0x180002b4b  jmp     short loc_180002B27
0x180002b4d  mov     eax, 80070057h
0x180002b52  test    rdx, rdx
0x180002b55  jz      short loc_180002B2E
0x180002b57  xor     edi, edi
0x180002b59  mov     [rcx], di
0x180002b5c  jmp     short loc_180002B2E
```
