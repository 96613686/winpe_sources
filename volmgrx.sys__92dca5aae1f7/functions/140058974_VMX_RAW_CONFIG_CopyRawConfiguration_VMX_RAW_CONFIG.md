# VMX_RAW_CONFIG::CopyRawConfiguration(VMX_RAW_CONFIG *)

- ea: `0x140058974`
- end: `0x140058b94`
- name: `?CopyRawConfiguration@VMX_RAW_CONFIG@@QEAAJPEAV1@@Z`
- size: `544`
- prototype: `__int64 __fastcall(VMX_RAW_CONFIG *__hidden this, struct VMX_RAW_CONFIG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14003e124`

## callees

- `0x140005f80`
- `0x1400099d8`
- `0x14001bb80`
- `0x140058974`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140058ae5`
- `ntoskrnl!ExAllocatePool2` at `0x140058ae5`

## pseudocode

```c
__int64 __fastcall VMX_RAW_CONFIG::CopyRawConfiguration(VMX_RAW_CONFIG *this, struct VMX_RAW_CONFIG *a2)
{
  __int64 ***v2; // rbx
  char *v4; // r14
  char *i; // rsi
  _OWORD *v7; // rax
  __int64 ****v8; // rcx
  VMX_NOTIFICATION_QUEUE *v9; // rcx
  __int64 v10; // rdx
  void *Pool2; // rax
  __int64 **j; // rdx
  __int64 k; // rax
  __int64 v15; // rcx
  __int64 v16; // rax

  v2 = (__int64 ***)((char *)this + 112);
  v4 = (char *)a2 + 112;
  *(_OWORD *)this = *(_OWORD *)a2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  *((_OWORD *)this + 9) = *((_OWORD *)a2 + 9);
  *((_OWORD *)this + 10) = *((_OWORD *)a2 + 10);
  *((_OWORD *)this + 11) = *((_OWORD *)a2 + 11);
  *((_QWORD *)this + 24) = *((_QWORD *)a2 + 24);
  *((_QWORD *)this + 15) = (char *)this + 112;
  *((_QWORD *)this + 14) = (char *)this + 112;
  *((_QWORD *)this + 17) = 0;
  for ( i = (char *)*((_QWORD *)a2 + 14); i != v4; i = *(char **)i )
  {
    v7 = VMX_ALLOCATED_OBJECT::operator new(0x38u, 0x102u, 0x72526D56u);
    if ( !v7 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v10 = 22;
        goto LABEL_16;
      }
      return 3221225626LL;
    }
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_DWORD *)v7 + 8) = -1;
    *v7 = *(_OWORD *)i;
    v7[1] = *((_OWORD *)i + 1);
    v7[2] = *((_OWORD *)i + 2);
    *((_QWORD *)v7 + 6) = 0;
    v8 = (__int64 ****)v2[1];
    if ( *v8 != v2 )
      __fastfail(3u);
    *(_QWORD *)v7 = v2;
    *((_QWORD *)v7 + 1) = v8;
    *v8 = (__int64 ***)v7;
    v2[1] = (__int64 **)v7;
  }
  Pool2 = (void *)ExAllocatePool2(258, 24LL * *((unsigned int *)this + 33), 1816292694);
  *((_QWORD *)this + 17) = Pool2;
  if ( !Pool2 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v10 = 24;
LABEL_16:
      WPP_SF_d(*((_QWORD *)v9 + 3), v10, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3221225626LL);
    }
    return 3221225626LL;
  }
  memmove(Pool2, *((const void **)a2 + 17), 24LL * *((unsigned int *)this + 33));
  for ( j = *v2; j != (__int64 **)v2; j = (__int64 **)*j )
  {
    for ( k = *((unsigned int *)j + 8); (_DWORD)k != -1; k = *(unsigned int *)(v16 + 8 * v15 + 8) )
    {
      v15 = 3 * k;
      v16 = *((_QWORD *)this + 17);
      *(_QWORD *)(v16 + 8 * v15) = j;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140058974  push    rbx
0x140058976  push    rbp
0x140058977  push    rsi
0x140058978  push    rdi
0x140058979  push    r14
0x14005897b  sub     rsp, 20h
0x14005897f  movups  xmm0, xmmword ptr [rdx]
0x140058982  lea     rbx, [rcx+70h]
0x140058986  mov     rbp, rdx
0x140058989  lea     r14, [rdx+70h]
0x14005898d  mov     rdi, rcx
0x140058990  movups  xmmword ptr [rcx], xmm0
0x140058993  movups  xmm1, xmmword ptr [rdx+10h]
0x140058997  movups  xmmword ptr [rcx+10h], xmm1
0x14005899b  movups  xmm0, xmmword ptr [rdx+20h]
0x14005899f  movups  xmmword ptr [rcx+20h], xmm0
0x1400589a3  movups  xmm1, xmmword ptr [rdx+30h]
0x1400589a7  movups  xmmword ptr [rcx+30h], xmm1
0x1400589ab  movups  xmm0, xmmword ptr [rdx+40h]
0x1400589af  movups  xmmword ptr [rcx+40h], xmm0
0x1400589b3  movups  xmm1, xmmword ptr [rdx+50h]
0x1400589b7  movups  xmmword ptr [rcx+50h], xmm1
0x1400589bb  movups  xmm0, xmmword ptr [rdx+60h]
0x1400589bf  movups  xmmword ptr [rcx+60h], xmm0
0x1400589c3  movups  xmm1, xmmword ptr [rdx+70h]
0x1400589c7  movups  xmmword ptr [rcx+70h], xmm1
0x1400589cb  movups  xmm0, xmmword ptr [rdx+80h]
0x1400589d2  movups  xmmword ptr [rcx+80h], xmm0
0x1400589d9  movups  xmm1, xmmword ptr [rdx+90h]
0x1400589e0  movups  xmmword ptr [rcx+90h], xmm1
0x1400589e7  movups  xmm0, xmmword ptr [rdx+0A0h]
0x1400589ee  movups  xmmword ptr [rcx+0A0h], xmm0
0x1400589f5  movups  xmm1, xmmword ptr [rdx+0B0h]
0x1400589fc  movups  xmmword ptr [rcx+0B0h], xmm1
0x140058a03  mov     rax, [rdx+0C0h]
0x140058a0a  mov     [rcx+0C0h], rax
0x140058a11  mov     [rbx+8], rbx
0x140058a15  mov     [rbx], rbx
0x140058a18  mov     qword ptr [rcx+88h], 0
0x140058a23  mov     rsi, [r14]
0x140058a26  cmp     rsi, r14
0x140058a29  jz      loc_140058ACC
0x140058a2f  mov     edx, 102h; unsigned __int64
0x140058a34  mov     ecx, 38h ; '8'; unsigned __int64
0x140058a39  mov     r8d, 72526D56h; unsigned int
0x140058a3f  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140058a44  test    rax, rax
0x140058a47  jz      short loc_140058AA1
0x140058a49  xorps   xmm0, xmm0
0x140058a4c  xor     ecx, ecx
0x140058a4e  movups  xmmword ptr [rax], xmm0
0x140058a51  movups  xmmword ptr [rax+10h], xmm0
0x140058a55  movups  xmmword ptr [rax+20h], xmm0
0x140058a59  mov     [rax+30h], rcx
0x140058a5d  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x140058a64  movups  xmm0, xmmword ptr [rsi]
0x140058a67  movups  xmmword ptr [rax], xmm0
0x140058a6a  movups  xmm1, xmmword ptr [rsi+10h]
0x140058a6e  movups  xmmword ptr [rax+10h], xmm1
0x140058a72  movups  xmm0, xmmword ptr [rsi+20h]
0x140058a76  movups  xmmword ptr [rax+20h], xmm0
0x140058a7a  mov     [rax+30h], rcx
0x140058a7e  mov     rcx, [rbx+8]
0x140058a82  cmp     [rcx], rbx
0x140058a85  jnz     short loc_140058A9A
0x140058a87  mov     [rax], rbx
0x140058a8a  mov     [rax+8], rcx
0x140058a8e  mov     [rcx], rax
0x140058a91  mov     [rbx+8], rax
0x140058a95  mov     rsi, [rsi]
0x140058a98  jmp     short loc_140058A26
0x140058a9a  mov     ecx, 3
0x140058a9f  int     29h; Win8: RtlFailFast(ecx)
0x140058aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140058aa8  lea     rax, WPP_GLOBAL_Control
0x140058aaf  cmp     rcx, rax
0x140058ab2  jz      loc_140058B3B
0x140058ab8  mov     eax, [rcx+2Ch]
0x140058abb  test    al, 40h
0x140058abd  jz      short loc_140058B3B
0x140058abf  cmp     byte ptr [rcx+29h], 2
0x140058ac3  jb      short loc_140058B3B
0x140058ac5  mov     edx, 16h
0x140058aca  jmp     short loc_140058B25
0x140058acc  mov     eax, [rdi+84h]
0x140058ad2  mov     ecx, 102h
0x140058ad7  mov     r8d, 6C426D56h
0x140058add  lea     rdx, [rax+rax*2]
0x140058ae1  shl     rdx, 3
0x140058ae5  call    cs:__imp_ExAllocatePool2
0x140058aec  nop     dword ptr [rax+rax+00h]
0x140058af1  mov     [rdi+88h], rax
0x140058af8  mov     rcx, rax; void *
0x140058afb  test    rax, rax
0x140058afe  jnz     short loc_140058B42
0x140058b00  mov     rcx, cs:WPP_GLOBAL_Control
0x140058b07  lea     rax, WPP_GLOBAL_Control
0x140058b0e  cmp     rcx, rax
0x140058b11  jz      short loc_140058B3B
0x140058b13  mov     eax, [rcx+2Ch]
0x140058b16  test    al, 40h
0x140058b18  jz      short loc_140058B3B
0x140058b1a  cmp     byte ptr [rcx+29h], 2
0x140058b1e  jb      short loc_140058B3B
0x140058b20  mov     edx, 18h
0x140058b25  mov     rcx, [rcx+18h]
0x140058b29  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x140058b30  mov     r9d, 0C000009Ah
0x140058b36  call    WPP_SF_d
0x140058b3b  mov     eax, 0C000009Ah
0x140058b40  jmp     short loc_140058B88
0x140058b42  mov     eax, [rdi+84h]
0x140058b48  mov     rdx, [rbp+88h]; Src
0x140058b4f  lea     r8, [rax+rax*2]
0x140058b53  shl     r8, 3; Size
0x140058b57  call    memmove
0x140058b5c  mov     rdx, [rbx]
0x140058b5f  jmp     short loc_140058B81
0x140058b61  mov     eax, [rdx+20h]
0x140058b64  jmp     short loc_140058B79
0x140058b66  lea     rcx, [rax+rax*2]
0x140058b6a  mov     rax, [rdi+88h]
0x140058b71  mov     [rax+rcx*8], rdx
0x140058b75  mov     eax, [rax+rcx*8+8]
0x140058b79  cmp     eax, 0FFFFFFFFh
0x140058b7c  jnz     short loc_140058B66
0x140058b7e  mov     rdx, [rdx]
0x140058b81  cmp     rdx, rbx
0x140058b84  jnz     short loc_140058B61
0x140058b86  xor     eax, eax
0x140058b88  add     rsp, 20h
0x140058b8c  pop     r14
0x140058b8e  pop     rdi
0x140058b8f  pop     rsi
0x140058b90  pop     rbp
0x140058b91  pop     rbx
0x140058b92  retn
```
