# VMX_LOG::CopyLog(VMX_LOG *)

- ea: `0x140048cdc`
- end: `0x140048f97`
- name: `?CopyLog@VMX_LOG@@QEAAJPEAV1@@Z`
- size: `699`
- prototype: `__int64 __fastcall(VMX_LOG *__hidden this, struct VMX_LOG *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004e950`

## callees

- `0x1400099d8`
- `0x14001bb80`
- `0x140048cdc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140048d2f`
- `ntoskrnl!ExAllocatePool2` at `0x140048dab`
- `ntoskrnl!ExAllocatePool2` at `0x140048ebb`
- `ntoskrnl!ExAllocatePool2` at `0x140048d2f`
- `ntoskrnl!ExAllocatePool2` at `0x140048dab`
- `ntoskrnl!ExAllocatePool2` at `0x140048ebb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f2f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048f7d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140048f7d`
- `ntoskrnl!IoAllocateMdl` at `0x140048f12`
- `ntoskrnl!IoAllocateMdl` at `0x140048f12`
- `ntoskrnl!IoAllocateIrp` at `0x140048e54`
- `ntoskrnl!IoAllocateIrp` at `0x140048e54`

## pseudocode

```c
__int64 __fastcall VMX_LOG::CopyLog(VMX_LOG *this, struct VMX_LOG *a2)
{
  unsigned int v4; // ebp
  void *Pool2; // rax
  VMX_NOTIFICATION_QUEUE *v6; // rcx
  __int64 v7; // rdx
  int v8; // esi
  size_t v9; // rbp
  void *v10; // rax
  char v11; // r8
  _QWORD *v12; // rbx
  ULONG v13; // esi
  _QWORD *v14; // rdx
  __int64 v15; // r9
  char v16; // al
  ULONG v17; // eax
  PIRP Irp; // rax
  __int64 v19; // rdx
  void *v20; // rax
  void *v21; // rbx
  struct _MDL *Mdl; // rax

  *(_OWORD *)this = *(_OWORD *)a2;
  *((_DWORD *)this + 10) = *((_DWORD *)a2 + 10);
  *((_BYTE *)this + 96) = *((_BYTE *)a2 + 96);
  if ( *((_BYTE *)a2 + 96) )
  {
    *((_QWORD *)this + 9) = *((_QWORD *)a2 + 9);
    *((_DWORD *)this + 20) = *((_DWORD *)a2 + 20);
    v4 = *((_DWORD *)a2 + 11);
    Pool2 = (void *)ExAllocatePool2(66, 8LL * v4, 1649175894);
    *((_QWORD *)this + 7) = Pool2;
    if ( !Pool2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v7 = 18;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v6 + 3), v7, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, 3221225626LL);
      return 3221225626LL;
    }
    memmove(Pool2, *((const void **)a2 + 7), 8LL * v4);
    *((_DWORD *)this + 11) = v4;
    v8 = *((_DWORD *)a2 + 12);
    v9 = (unsigned int)(v8 << 9);
    v10 = (void *)ExAllocatePool2(66, v9, 1917611350);
    *((_QWORD *)this + 8) = v10;
    if ( !v10 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v7 = 19;
      goto LABEL_38;
    }
    memmove(v10, *((const void **)a2 + 8), v9);
    *((_DWORD *)this + 12) = v8;
    v11 = 0;
    v12 = (_QWORD *)((char *)a2 + 16);
    v13 = 512;
    v14 = (_QWORD *)*v12;
    while ( v14 != v12 )
    {
      v15 = v14[3];
      if ( !*(_DWORD *)(v15 + 40) )
      {
        v16 = v11;
        if ( *(char *)(*(_QWORD *)(v15 + 24) + 76LL) > v11 )
          v16 = *(_BYTE *)(*(_QWORD *)(v15 + 24) + 76LL);
        v11 = v16;
      }
      v17 = *(_DWORD *)(v15 + 36);
      v14 = (_QWORD *)*v14;
      if ( v17 <= v13 )
        v17 = v13;
      v13 = v17;
    }
    Irp = IoAllocateIrp(v11 + 1, 0);
    *((_QWORD *)this + 29) = Irp;
    if ( !Irp )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v7 = 20;
      goto LABEL_38;
    }
    v19 = v13;
    if ( v13 < 0x1000 )
      v19 = 4096;
    v20 = (void *)ExAllocatePool2(74, v19, 1967287638);
    v21 = v20;
    if ( !v20 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v7 = 21;
      goto LABEL_38;
    }
    Mdl = IoAllocateMdl(v20, v13, 0, 0, 0);
    *((_QWORD *)this + 30) = Mdl;
    if ( !Mdl )
    {
      ExFreePoolWithTag(v21, 0);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v7 = 22;
      goto LABEL_38;
    }
    MmBuildMdlForNonPagedPool(Mdl);
  }
  return 0;
}

```

## disassembly

```asm
0x140048cdc  push    rbx
0x140048cde  push    rbp
0x140048cdf  push    rsi
0x140048ce0  push    rdi
0x140048ce1  push    r15
0x140048ce3  sub     rsp, 30h
0x140048ce7  movups  xmm0, xmmword ptr [rdx]
0x140048cea  mov     rbx, rdx
0x140048ced  mov     rdi, rcx
0x140048cf0  movdqu  xmmword ptr [rcx], xmm0
0x140048cf4  mov     eax, [rdx+28h]
0x140048cf7  mov     [rcx+28h], eax
0x140048cfa  mov     al, [rdx+60h]
0x140048cfd  mov     [rcx+60h], al
0x140048d00  cmp     byte ptr [rdx+60h], 0
0x140048d04  jz      loc_140048F89
0x140048d0a  mov     rax, [rdx+48h]
0x140048d0e  mov     r8d, 624C6D56h
0x140048d14  mov     [rcx+48h], rax
0x140048d18  mov     eax, [rdx+50h]
0x140048d1b  mov     [rcx+50h], eax
0x140048d1e  mov     ecx, 42h ; 'B'
0x140048d23  mov     ebp, [rdx+2Ch]
0x140048d26  mov     esi, ebp
0x140048d28  shl     rsi, 3
0x140048d2c  mov     rdx, rsi
0x140048d2f  call    cs:__imp_ExAllocatePool2
0x140048d36  nop     dword ptr [rax+rax+00h]
0x140048d3b  mov     [rdi+38h], rax
0x140048d3f  mov     r15d, 0C000009Ah
0x140048d45  test    rax, rax
0x140048d48  jnz     short loc_140048D82
0x140048d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d51  lea     rax, WPP_GLOBAL_Control
0x140048d58  cmp     rcx, rax
0x140048d5b  jz      loc_140048F75
0x140048d61  test    dword ptr [rcx+2Ch], 800h
0x140048d68  jz      loc_140048F75
0x140048d6e  cmp     byte ptr [rcx+29h], 2
0x140048d72  jb      loc_140048F75
0x140048d78  mov     edx, 12h
0x140048d7d  jmp     loc_140048F62
0x140048d82  mov     rdx, [rbx+38h]; Src
0x140048d86  mov     r8, rsi; Size
0x140048d89  mov     rcx, rax; void *
0x140048d8c  call    memmove
0x140048d91  mov     [rdi+2Ch], ebp
0x140048d94  mov     r8d, 724C6D56h
0x140048d9a  mov     esi, [rbx+30h]
0x140048d9d  mov     ecx, 42h ; 'B'
0x140048da2  mov     eax, esi
0x140048da4  shl     eax, 9
0x140048da7  mov     edx, eax
0x140048da9  mov     ebp, eax
0x140048dab  call    cs:__imp_ExAllocatePool2
0x140048db2  nop     dword ptr [rax+rax+00h]
0x140048db7  mov     [rdi+40h], rax
0x140048dbb  test    rax, rax
0x140048dbe  jnz     short loc_140048DF8
0x140048dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140048dc7  lea     rax, WPP_GLOBAL_Control
0x140048dce  cmp     rcx, rax
0x140048dd1  jz      loc_140048F75
0x140048dd7  test    dword ptr [rcx+2Ch], 800h
0x140048dde  jz      loc_140048F75
0x140048de4  cmp     byte ptr [rcx+29h], 2
0x140048de8  jb      loc_140048F75
0x140048dee  mov     edx, 13h
0x140048df3  jmp     loc_140048F62
0x140048df8  mov     rdx, [rbx+40h]; Src
0x140048dfc  mov     r8, rbp; Size
0x140048dff  mov     rcx, rax; void *
0x140048e02  call    memmove
0x140048e07  mov     [rdi+30h], esi
0x140048e0a  xor     r8b, r8b
0x140048e0d  add     rbx, 10h
0x140048e11  mov     esi, 200h
0x140048e16  mov     rdx, [rbx]
0x140048e19  jmp     short loc_140048E49
0x140048e1b  mov     r9, [rdx+18h]
0x140048e1f  cmp     dword ptr [r9+28h], 0
0x140048e24  jnz     short loc_140048E3B
0x140048e26  mov     rax, [r9+18h]
0x140048e2a  movzx   ecx, byte ptr [rax+4Ch]
0x140048e2e  cmp     cl, r8b
0x140048e31  movzx   eax, r8b
0x140048e35  cmovg   eax, ecx
0x140048e38  mov     r8b, al
0x140048e3b  mov     eax, [r9+24h]
0x140048e3f  cmp     eax, esi
0x140048e41  mov     rdx, [rdx]
0x140048e44  cmovbe  eax, esi
0x140048e47  mov     esi, eax
0x140048e49  cmp     rdx, rbx
0x140048e4c  jnz     short loc_140048E1B
0x140048e4e  lea     ecx, [r8+1]; StackSize
0x140048e52  xor     edx, edx; ChargeQuota
0x140048e54  call    cs:__imp_IoAllocateIrp
0x140048e5b  nop     dword ptr [rax+rax+00h]
0x140048e60  mov     [rdi+0E8h], rax
0x140048e67  test    rax, rax
0x140048e6a  jnz     short loc_140048EA4
0x140048e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048e73  lea     rax, WPP_GLOBAL_Control
0x140048e7a  cmp     rcx, rax
0x140048e7d  jz      loc_140048F75
0x140048e83  test    dword ptr [rcx+2Ch], 800h
0x140048e8a  jz      loc_140048F75
0x140048e90  cmp     byte ptr [rcx+29h], 2
0x140048e94  jb      loc_140048F75
0x140048e9a  mov     edx, 14h
0x140048e9f  jmp     loc_140048F62
0x140048ea4  mov     ecx, 1000h
0x140048ea9  mov     edx, esi
0x140048eab  cmp     esi, ecx
0x140048ead  mov     r8d, 75426D56h
0x140048eb3  cmovb   edx, ecx
0x140048eb6  mov     ecx, 4Ah ; 'J'
0x140048ebb  call    cs:__imp_ExAllocatePool2
0x140048ec2  nop     dword ptr [rax+rax+00h]
0x140048ec7  mov     rbx, rax
0x140048eca  test    rax, rax
0x140048ecd  jnz     short loc_140048EFE
0x140048ecf  mov     rcx, cs:WPP_GLOBAL_Control
0x140048ed6  lea     rax, WPP_GLOBAL_Control
0x140048edd  cmp     rcx, rax
0x140048ee0  jz      loc_140048F75
0x140048ee6  test    dword ptr [rcx+2Ch], 800h
0x140048eed  jz      loc_140048F75
0x140048ef3  cmp     byte ptr [rcx+29h], 2
0x140048ef7  jb      short loc_140048F75
0x140048ef9  lea     edx, [rbx+15h]
0x140048efc  jmp     short loc_140048F62
0x140048efe  xor     r9d, r9d; ChargeQuota
0x140048f01  mov     [rsp+58h+Irp], 0; Irp
0x140048f0a  xor     r8d, r8d; SecondaryBuffer
0x140048f0d  mov     edx, esi; Length
0x140048f0f  mov     rcx, rbx; VirtualAddress
0x140048f12  call    cs:__imp_IoAllocateMdl
0x140048f19  nop     dword ptr [rax+rax+00h]
0x140048f1e  mov     [rdi+0F0h], rax
0x140048f25  test    rax, rax
0x140048f28  jnz     short loc_140048F7A
0x140048f2a  xor     edx, edx; Tag
0x140048f2c  mov     rcx, rbx; P
0x140048f2f  call    cs:__imp_ExFreePoolWithTag
0x140048f36  nop     dword ptr [rax+rax+00h]
0x140048f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048f42  lea     rax, WPP_GLOBAL_Control
0x140048f49  cmp     rcx, rax
0x140048f4c  jz      short loc_140048F75
0x140048f4e  test    dword ptr [rcx+2Ch], 800h
0x140048f55  jz      short loc_140048F75
0x140048f57  cmp     byte ptr [rcx+29h], 2
0x140048f5b  jb      short loc_140048F75
0x140048f5d  mov     edx, 16h
0x140048f62  mov     rcx, [rcx+18h]
0x140048f66  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x140048f6d  mov     r9d, r15d
0x140048f70  call    WPP_SF_d
0x140048f75  mov     eax, r15d
0x140048f78  jmp     short loc_140048F8B
0x140048f7a  mov     rcx, rax; MemoryDescriptorList
0x140048f7d  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140048f84  nop     dword ptr [rax+rax+00h]
0x140048f89  xor     eax, eax
0x140048f8b  add     rsp, 30h
0x140048f8f  pop     r15
0x140048f91  pop     rdi
0x140048f92  pop     rsi
0x140048f93  pop     rbp
0x140048f94  pop     rbx
0x140048f95  retn
```
