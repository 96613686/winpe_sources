# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000d9dc`
- end: `0x18000da4f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `115`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000794c`
- `0x180007d44`
- `0x180013fb8`
- `0x180014c24`
- `0x180018cdc`

## callees

- `0x18000d9dc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000da1d`
- `msvcrt!_vsnwprintf` at `0x18000da1d`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edi
  unsigned __int64 v5; // rsi
  int v6; // eax
  va_list Args; // [rsp+78h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = a2 - 1;
    v4 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
    }
    else if ( v6 != v5 )
    {
      return v4;
    }
    a1[v5] = 0;
    return v4;
  }
  v4 = -2147024809;
  if ( a2 )
    *a1 = 0;
  return v4;
}

```

## disassembly

```asm
0x18000d9dc  mov     [rsp+arg_10], r8
0x18000d9e1  mov     qword ptr [rsp+Args], r9
0x18000d9e6  push    rbx
0x18000d9e7  push    rsi
0x18000d9e8  push    rdi
0x18000d9e9  push    r14
0x18000d9eb  sub     rsp, 38h
0x18000d9ef  lea     rax, [rdx-1]
0x18000d9f3  xor     ebx, ebx
0x18000d9f5  mov     r14, rcx
0x18000d9f8  cmp     rax, 7FFFFFFEh
0x18000d9fe  jbe     short loc_18000DA0F
0x18000da00  mov     edi, 80070057h
0x18000da05  test    rdx, rdx
0x18000da08  jz      short loc_18000DA42
0x18000da0a  mov     [rcx], bx
0x18000da0d  jmp     short loc_18000DA42
0x18000da0f  lea     rsi, [rdx-1]
0x18000da13  mov     edi, ebx
0x18000da15  mov     rdx, rsi; BufferCount
0x18000da18  lea     r9, [rsp+58h+Args]; Args
0x18000da1d  call    cs:__imp__vsnwprintf
0x18000da24  nop     dword ptr [rax+rax+00h]
0x18000da29  test    eax, eax
0x18000da2b  js      short loc_18000DA38
0x18000da2d  cdqe
0x18000da2f  cmp     rax, rsi
0x18000da32  ja      short loc_18000DA38
0x18000da34  jnz     short loc_18000DA42
0x18000da36  jmp     short loc_18000DA3D
0x18000da38  mov     edi, 8007007Ah
0x18000da3d  mov     [r14+rsi*2], bx
0x18000da42  mov     eax, edi
0x18000da44  add     rsp, 38h
0x18000da48  pop     r14
0x18000da4a  pop     rdi
0x18000da4b  pop     rsi
0x18000da4c  pop     rbx
0x18000da4d  retn
```
