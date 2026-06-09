# CacheDeleteItem

- ea: `0x18003833c`
- end: `0x1800383f2`
- name: `CacheDeleteItem`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180036f7c`

## callees

- `0x18000d9d0`
- `0x18003833c`
- `0x18003852c`
- `0x1800385f0`
- `0x18003c1f6`
- `0x18003c240`

## pseudocode

```c
unsigned int __fastcall CacheDeleteItem(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax
  int v4; // edx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rax
  UCHAR Buf2[32]; // [rsp+20h] [rbp-48h] BYREF

  v3 = I_CacheHashKeys(a2, a2, Buf2);
  if ( v3 )
    return errcntrctlib::WIN32_FROM_NTSTATUS((errcntrctlib *)v3, v4);
  v6 = Buf2[0] & 0xF;
  v7 = *(_QWORD *)(a1 + 8 * v6);
  if ( !v7 )
    return 1168;
  v8 = 0;
  while ( memcmp_0((const void *)(v7 + 24), Buf2, 0x20u) )
  {
    v8 = v7;
    v7 = *(_QWORD *)(v7 + 16);
    if ( !v7 )
      return 1168;
  }
  v9 = *(_QWORD *)(v7 + 16);
  if ( v8 )
    *(_QWORD *)(v8 + 16) = v9;
  else
    *(_QWORD *)(a1 + 8 * v6) = v9;
  CspFreeH(v7);
  --*(_DWORD *)(a1 + 128);
  return 0;
}

```

## disassembly

```asm
0x18003833c  mov     [rsp+arg_10], rbx
0x180038341  push    rbp
0x180038342  push    rsi
0x180038343  push    rdi
0x180038344  sub     rsp, 50h
0x180038348  mov     rax, cs:__security_cookie
0x18003834f  xor     rax, rsp
0x180038352  mov     [rsp+68h+var_28], rax
0x180038357  mov     rsi, rcx
0x18003835a  lea     r8, [rsp+68h+Buf2]
0x18003835f  mov     rcx, rdx
0x180038362  call    I_CacheHashKeys
0x180038367  test    eax, eax
0x180038369  jz      short loc_180038374
0x18003836b  mov     ecx, eax; this
0x18003836d  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x180038372  jmp     short loc_1800383B0
0x180038374  movzx   edi, [rsp+68h+Buf2]
0x180038379  and     edi, 0Fh
0x18003837c  mov     rbx, [rsi+rdi*8]
0x180038380  test    rbx, rbx
0x180038383  jz      short loc_1800383AB
0x180038385  xor     ebp, ebp
0x180038387  lea     rcx, [rbx+18h]; Buf1
0x18003838b  mov     r8d, 20h ; ' '; Size
0x180038391  lea     rdx, [rsp+68h+Buf2]; Buf2
0x180038396  call    memcmp_0
0x18003839b  test    eax, eax
0x18003839d  jz      short loc_1800383CD
0x18003839f  mov     rbp, rbx
0x1800383a2  mov     rbx, [rbx+10h]
0x1800383a6  test    rbx, rbx
0x1800383a9  jnz     short loc_180038387
0x1800383ab  mov     eax, 490h
0x1800383b0  mov     rcx, [rsp+68h+var_28]
0x1800383b5  xor     rcx, rsp; StackCookie
0x1800383b8  call    __security_check_cookie
0x1800383bd  mov     rbx, [rsp+68h+arg_10]
0x1800383c5  add     rsp, 50h
0x1800383c9  pop     rdi
0x1800383ca  pop     rsi
0x1800383cb  pop     rbp
0x1800383cc  retn
0x1800383cd  mov     rax, [rbx+10h]
0x1800383d1  test    rbp, rbp
0x1800383d4  jnz     short loc_1800383DC
0x1800383d6  mov     [rsi+rdi*8], rax
0x1800383da  jmp     short loc_1800383E0
0x1800383dc  mov     [rbp+10h], rax
0x1800383e0  mov     rcx, rbx
0x1800383e3  call    CspFreeH
0x1800383e8  dec     dword ptr [rsi+80h]
0x1800383ee  xor     eax, eax
0x1800383f0  jmp     short loc_1800383B0
```
