# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000b520`
- end: `0x18000b59e`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `126`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e28`
- `0x180005660`
- `0x18000cebc`
- `0x18000feb0`

## callees

- `0x18000b520`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000b554`
- `msvcrt!_vsnwprintf` at `0x18000b554`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rdi
  unsigned int v5; // ebx
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
0x18000b520  mov     [rsp+arg_10], r8
0x18000b525  mov     qword ptr [rsp+Args], r9
0x18000b52a  push    rbx
0x18000b52b  push    rsi
0x18000b52c  sub     rsp, 38h
0x18000b530  mov     rsi, rcx
0x18000b533  test    rdx, rdx
0x18000b536  jz      short loc_18000B58D
0x18000b538  cmp     rdx, 7FFFFFFFh
0x18000b53f  ja      short loc_18000B580
0x18000b541  mov     [rsp+48h+var_18], rdi
0x18000b546  lea     r9, [rsp+48h+Args]; Args
0x18000b54b  lea     rdi, [rdx-1]
0x18000b54f  xor     ebx, ebx
0x18000b551  mov     rdx, rdi; BufferCount
0x18000b554  call    cs:__imp__vsnwprintf
0x18000b55a  test    eax, eax
0x18000b55c  js      short loc_18000B575
0x18000b55e  cdqe
0x18000b560  cmp     rax, rdi
0x18000b563  ja      short loc_18000B575
0x18000b565  jz      short loc_18000B587
0x18000b567  mov     rdi, [rsp+48h+var_18]
0x18000b56c  mov     eax, ebx
0x18000b56e  add     rsp, 38h
0x18000b572  pop     rsi
0x18000b573  pop     rbx
0x18000b574  retn
0x18000b575  mov     [rsi+rdi*2], bx
0x18000b579  mov     ebx, 8007007Ah
0x18000b57e  jmp     short loc_18000B567
0x18000b580  mov     eax, 80070057h
0x18000b585  jmp     short loc_18000B597
0x18000b587  mov     [rsi+rdi*2], bx
0x18000b58b  jmp     short loc_18000B567
0x18000b58d  mov     eax, 80070057h
0x18000b592  test    rdx, rdx
0x18000b595  jz      short loc_18000B56E
0x18000b597  xor     ebx, ebx
0x18000b599  mov     [rcx], bx
0x18000b59c  jmp     short loc_18000B56E
```
