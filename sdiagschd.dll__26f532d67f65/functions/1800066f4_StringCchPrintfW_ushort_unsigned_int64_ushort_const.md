# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800066f4`
- end: `0x180006767`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `115`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b70`
- `0x180006ba8`
- `0x180007c60`
- `0x180009600`

## callees

- `0x1800066f4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006735`
- `msvcrt!_vsnwprintf` at `0x180006735`

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
0x1800066f4  mov     [rsp+arg_10], r8
0x1800066f9  mov     qword ptr [rsp+Args], r9
0x1800066fe  push    rbx
0x1800066ff  push    rsi
0x180006700  push    rdi
0x180006701  push    r14
0x180006703  sub     rsp, 38h
0x180006707  lea     rax, [rdx-1]
0x18000670b  xor     ebx, ebx
0x18000670d  mov     r14, rcx
0x180006710  cmp     rax, 7FFFFFFEh
0x180006716  jbe     short loc_180006727
0x180006718  mov     edi, 80070057h
0x18000671d  test    rdx, rdx
0x180006720  jz      short loc_18000675A
0x180006722  mov     [rcx], bx
0x180006725  jmp     short loc_18000675A
0x180006727  lea     rsi, [rdx-1]
0x18000672b  mov     edi, ebx
0x18000672d  mov     rdx, rsi; BufferCount
0x180006730  lea     r9, [rsp+58h+Args]; Args
0x180006735  call    cs:__imp__vsnwprintf
0x18000673c  nop     dword ptr [rax+rax+00h]
0x180006741  test    eax, eax
0x180006743  js      short loc_180006750
0x180006745  cdqe
0x180006747  cmp     rax, rsi
0x18000674a  ja      short loc_180006750
0x18000674c  jnz     short loc_18000675A
0x18000674e  jmp     short loc_180006755
0x180006750  mov     edi, 8007007Ah
0x180006755  mov     [r14+rsi*2], bx
0x18000675a  mov     eax, edi
0x18000675c  add     rsp, 38h
0x180006760  pop     r14
0x180006762  pop     rdi
0x180006763  pop     rsi
0x180006764  pop     rbx
0x180006765  retn
```
