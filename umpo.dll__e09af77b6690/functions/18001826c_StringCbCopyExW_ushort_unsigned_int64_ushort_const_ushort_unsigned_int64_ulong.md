# StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18001826c`
- end: `0x180018307`
- name: `?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `155`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018418`

## callees

- `0x18001826c`
- `0x18001839c`

## pseudocode

```c
__int64 __fastcall StringCbCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v6; // rbx
  char v7; // di
  HRESULT v9; // edx
  unsigned __int64 v10; // rbx
  size_t v12; // [rsp+20h] [rbp-38h]
  size_t pcchNewDestLength; // [rsp+68h] [rbp+10h] BYREF

  v6 = a2 >> 1;
  v7 = a2;
  if ( a2 >> 1 )
  {
    if ( v6 <= 0x7FFFFFFF )
    {
      pcchNewDestLength = 0;
      v9 = StringCopyWorkerW_0(a1, a2 >> 1, &pcchNewDestLength, a3, v12);
      v10 = v6 - pcchNewDestLength;
      if ( v9 >= 0 || v9 == -2147024774 )
      {
        if ( a4 )
          *a4 = &a1[pcchNewDestLength];
        if ( a5 )
          *a5 = (v7 & 1) + 2 * v10;
      }
    }
    else
    {
      v9 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001826c  push    rbx
0x18001826e  push    rsi
0x18001826f  push    rdi
0x180018270  push    r14
0x180018272  sub     rsp, 38h
0x180018276  mov     rbx, rdx
0x180018279  mov     rsi, r9
0x18001827c  shr     rbx, 1
0x18001827f  mov     rdi, rdx
0x180018282  mov     r14, rcx
0x180018285  jz      short loc_1800182EB
0x180018287  cmp     rbx, 7FFFFFFFh
0x18001828e  jbe     short loc_180018297
0x180018290  mov     edx, 80070057h
0x180018295  jmp     short loc_1800182F5
0x180018297  mov     r9, r8; pszSrc
0x18001829a  mov     [rsp+58h+pcchNewDestLength], 0
0x1800182a3  lea     r8, [rsp+58h+pcchNewDestLength]; pcchNewDestLength
0x1800182a8  mov     rdx, rbx; cchDest
0x1800182ab  call    StringCopyWorkerW_0
0x1800182b0  mov     edx, eax
0x1800182b2  mov     rax, [rsp+58h+pcchNewDestLength]
0x1800182b7  sub     rbx, rax
0x1800182ba  lea     rcx, [r14+rax*2]
0x1800182be  test    edx, edx
0x1800182c0  jns     short loc_1800182CA
0x1800182c2  cmp     edx, 8007007Ah
0x1800182c8  jnz     short loc_1800182FB
0x1800182ca  test    rsi, rsi
0x1800182cd  jz      short loc_1800182D2
0x1800182cf  mov     [rsi], rcx
0x1800182d2  mov     rcx, [rsp+58h+arg_20]
0x1800182da  test    rcx, rcx
0x1800182dd  jz      short loc_1800182FB
0x1800182df  and     edi, 1
0x1800182e2  lea     rax, [rdi+rbx*2]
0x1800182e6  mov     [rcx], rax
0x1800182e9  jmp     short loc_1800182FB
0x1800182eb  mov     edx, 80070057h
0x1800182f0  test    rbx, rbx
0x1800182f3  jz      short loc_1800182FB
0x1800182f5  xor     ecx, ecx
0x1800182f7  mov     [r14], cx
0x1800182fb  mov     eax, edx
0x1800182fd  add     rsp, 38h
0x180018301  pop     r14
0x180018303  pop     rdi
0x180018304  pop     rsi
0x180018305  pop     rbx
0x180018306  retn
```
