# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000ab00`
- end: `0x18000ab73`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `115`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800096e8`
- `0x18000d39c`
- `0x18000d638`
- `0x18000d754`
- `0x18000d8c4`
- `0x18000d980`
- `0x18000db14`
- `0x18000f9f8`

## callees

- `0x18000ab00`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000ab41`
- `msvcrt!_vsnwprintf` at `0x18000ab41`

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
0x18000ab00  mov     [rsp+arg_10], r8
0x18000ab05  mov     qword ptr [rsp+Args], r9
0x18000ab0a  push    rbx
0x18000ab0b  push    rsi
0x18000ab0c  push    rdi
0x18000ab0d  push    r14
0x18000ab0f  sub     rsp, 38h
0x18000ab13  lea     rax, [rdx-1]
0x18000ab17  xor     ebx, ebx
0x18000ab19  mov     r14, rcx
0x18000ab1c  cmp     rax, 7FFFFFFEh
0x18000ab22  jbe     short loc_18000AB33
0x18000ab24  mov     edi, 80070057h
0x18000ab29  test    rdx, rdx
0x18000ab2c  jz      short loc_18000AB66
0x18000ab2e  mov     [rcx], bx
0x18000ab31  jmp     short loc_18000AB66
0x18000ab33  lea     rsi, [rdx-1]
0x18000ab37  mov     edi, ebx
0x18000ab39  mov     rdx, rsi; BufferCount
0x18000ab3c  lea     r9, [rsp+58h+Args]; Args
0x18000ab41  call    cs:__imp__vsnwprintf
0x18000ab48  nop     dword ptr [rax+rax+00h]
0x18000ab4d  test    eax, eax
0x18000ab4f  js      short loc_18000AB5C
0x18000ab51  cdqe
0x18000ab53  cmp     rax, rsi
0x18000ab56  ja      short loc_18000AB5C
0x18000ab58  jnz     short loc_18000AB66
0x18000ab5a  jmp     short loc_18000AB61
0x18000ab5c  mov     edi, 8007007Ah
0x18000ab61  mov     [r14+rsi*2], bx
0x18000ab66  mov     eax, edi
0x18000ab68  add     rsp, 38h
0x18000ab6c  pop     r14
0x18000ab6e  pop     rdi
0x18000ab6f  pop     rsi
0x18000ab70  pop     rbx
0x18000ab71  retn
```
