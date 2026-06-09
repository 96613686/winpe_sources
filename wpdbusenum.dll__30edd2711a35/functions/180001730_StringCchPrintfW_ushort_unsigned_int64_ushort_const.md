# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180001730`
- end: `0x1800017b1`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `129`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x180002c70`
- `0x1800069d0`
- `0x180008128`
- `0x18000b998`
- `0x1800106e0`
- `0x180010f60`

## callees

- `0x180001730`
- `0x18000a1a0`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rsi
  unsigned int v6; // ebx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = a2 - 1;
    v6 = 0;
    v7 = vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v7 < 0 || v7 > v5 )
    {
      a1[v5] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v7 == v5 )
    {
      a1[v5] = 0;
    }
    return v6;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001730  mov     [rsp+arg_10], r8
0x180001735  mov     qword ptr [rsp+Args], r9
0x18000173a  push    rbx
0x18000173b  push    rdi
0x18000173c  sub     rsp, 38h
0x180001740  mov     rdi, rcx
0x180001743  test    rdx, rdx
0x180001746  jz      short loc_18000179B
0x180001748  cmp     rdx, 7FFFFFFFh
0x18000174f  jbe     short loc_180001758
0x180001751  mov     eax, 80070057h
0x180001756  jmp     short loc_1800017A5
0x180001758  mov     [rsp+48h+var_18], rsi
0x18000175d  lea     r9, [rsp+48h+Args]; Args
0x180001762  lea     rsi, [rdx-1]
0x180001766  xor     ebx, ebx
0x180001768  mov     rdx, rsi; BufferCount
0x18000176b  call    _vsnwprintf
0x180001770  test    eax, eax
0x180001772  js      short loc_180001784
0x180001774  movsxd  rcx, eax
0x180001777  cmp     rcx, rsi
0x18000177a  ja      short loc_180001784
0x18000177c  jnz     short loc_18000178D
0x18000177e  mov     [rdi+rsi*2], bx
0x180001782  jmp     short loc_18000178D
0x180001784  mov     [rdi+rsi*2], bx
0x180001788  mov     ebx, 8007007Ah
0x18000178d  mov     rsi, [rsp+48h+var_18]
0x180001792  mov     eax, ebx
0x180001794  add     rsp, 38h
0x180001798  pop     rdi
0x180001799  pop     rbx
0x18000179a  retn
0x18000179b  mov     eax, 80070057h
0x1800017a0  test    rdx, rdx
0x1800017a3  jz      short loc_1800017AA
0x1800017a5  xor     ebx, ebx
0x1800017a7  mov     [rcx], bx
0x1800017aa  add     rsp, 38h
0x1800017ae  pop     rdi
0x1800017af  pop     rbx
0x1800017b0  retn
```
