# Smb2ModifyShare

- ea: `0x140064168`
- end: `0x1400644eb`
- name: `Smb2ModifyShare`
- size: `899`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140059540`

## callees

- `0x14000c450`
- `0x1400280ac`
- `0x140038680`
- `0x140063acc`
- `0x140064168`
- `0x140076fd0`
- `0x140085d00`
- `0x14008b4f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140064238`
- `ntoskrnl!ExAllocatePool2` at `0x14006427b`
- `ntoskrnl!ExAllocatePool2` at `0x140064238`
- `ntoskrnl!ExAllocatePool2` at `0x14006427b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006448c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006448c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400642cd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400642cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400642e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064316`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400644b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400644c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400642e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064316`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400644b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400644c8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006421c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006421c`

## pseudocode

```c
__int64 __fastcall Smb2ModifyShare(__int64 a1)
{
  void *v2; // rsi
  __int64 Instance; // rax
  void *v4; // r15
  __int64 v5; // rcx
  void *v6; // rbp
  __int64 v7; // rbx
  void *v8; // rcx
  int v9; // r12d
  ULONG v10; // r14d
  void *Pool2; // rax
  void *v12; // rax
  char v13; // r14
  void *v14; // rcx
  void *v15; // rcx
  unsigned int v16; // r8d
  int v17; // r12d
  int v18; // r10d
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // eax
  int v24; // ecx
  int v25; // r8d
  char v27; // [rsp+38h] [rbp-90h]
  __int128 v28; // [rsp+70h] [rbp-58h]
  __int64 v29; // [rsp+D0h] [rbp+8h] BYREF

  v28 = 0u;
  v2 = 0;
  if ( (*(_DWORD *)(a1 + 128) & 0x21000) != 0x21000 )
  {
    Instance = Srv2GetInstance(*(unsigned int *)(a1 + 152));
    v4 = (void *)Instance;
    if ( !Instance )
      return 0;
    v27 = *(_BYTE *)(a1 + 50);
    v5 = *(_QWORD *)(Instance + 160);
    v6 = 0;
    v29 = 0;
    Smb2FindShareAndSetServerName(v5, a1 + 8, a1 + 24, &v29, 0, 0, 0, v27);
    v7 = v29;
    if ( !v29 )
      goto LABEL_33;
    v8 = *(void **)(a1 + 192);
    v9 = *(_DWORD *)(a1 + 128);
    if ( v8 )
    {
      v10 = RtlLengthSecurityDescriptor(v8);
      Pool2 = (void *)ExAllocatePool2(258, v10, 1748128588);
      v6 = Pool2;
      if ( !Pool2 )
        goto LABEL_32;
      memmove(Pool2, *(const void **)(a1 + 192), v10);
    }
    if ( !*(_WORD *)(a1 + 200) )
    {
LABEL_10:
      v13 = 0;
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)v7 + 96LL), 1u);
      v14 = *(void **)(v7 + 264);
      if ( v14 )
        ExFreePoolWithTag(v14, 0);
      v15 = *(void **)(v7 + 192);
      ++*(_DWORD *)(v7 + 272);
      *(_QWORD *)(v7 + 264) = v6;
      v6 = 0;
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      v2 = 0;
      v16 = v9 & 0xFFFFFFCF;
      v17 = v9 & 0x30;
      *(_OWORD *)(v7 + 184) = v28;
      *(_DWORD *)(v7 + 288) = v16;
      *(_DWORD *)(v7 + 292) = v17;
      v18 = *(_DWORD *)(a1 + 140);
      *(_DWORD *)(v7 + 296) = v18;
      if ( !*(_BYTE *)(v7 + 276) && !*(_BYTE *)(v7 + 277) )
      {
        v19 = *(_DWORD *)(a1 + 132);
        if ( ((v19 & 1) != 0 || (v19 & 2) != 0) && *(_QWORD *)(v7 + 208) != v7 + 208 )
          v13 = 1;
      }
      v20 = *(_DWORD *)(a1 + 144);
      if ( v20 )
        *(_DWORD *)(v7 + 300) = v20;
      v21 = *(_DWORD *)(a1 + 132) & 1;
      if ( v21 )
        v22 = v16 | 1;
      else
        v22 = v16 & 0xFFFFFFFE;
      *(_BYTE *)(v7 + 276) = v21;
      *(_DWORD *)(v7 + 288) = v22;
      v23 = v22 & 0xFFFFFFFD;
      v24 = *(_DWORD *)(a1 + 132);
      v25 = v22 | 2;
      if ( (v24 & 2) == 0 )
        v25 = v23;
      *(_DWORD *)(v7 + 288) = v25;
      *(_BYTE *)(v7 + 277) = (v24 & 2) != 0;
      *(_DWORD *)(v7 + 416) = *(_DWORD *)(a1 + 216);
      *(_OWORD *)(v7 + 40) = *(_OWORD *)(a1 + 220);
      if ( (byte_14004C339 & 0x20) != 0 )
        McTemplateK0hzr0hzr2hzr4qqqqq_EtwWriteTransfer(
          *(_WORD *)(v7 + 152) >> 1,
          (unsigned int)SMB2_EVENT_SHARE_MODIFY,
          v25,
          *(_WORD *)(v7 + 72) >> 1,
          *(_QWORD *)(v7 + 80),
          *(_WORD *)(v7 + 88) >> 1,
          *(_QWORD *)(v7 + 96),
          *(_WORD *)(v7 + 152) >> 1,
          *(_QWORD *)(v7 + 160),
          v17,
          *(_DWORD *)(v7 + 368),
          v25,
          *(_DWORD *)(v7 + 300),
          v18);
      if ( v13 )
        Smb2CloseTreeConnectsOnShare(v7, 0);
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)v7 + 96LL));
      goto LABEL_32;
    }
    v12 = (void *)ExAllocatePool2(258, *(unsigned __int16 *)(a1 + 200), 1748128588);
    *((_QWORD *)&v28 + 1) = v12;
    v2 = v12;
    if ( v12 )
    {
      memmove(v12, *(const void **)(a1 + 208), *(unsigned __int16 *)(a1 + 200));
      WORD1(v28) = *(_WORD *)(a1 + 200);
      LOWORD(v28) = WORD1(v28);
      goto LABEL_10;
    }
LABEL_32:
    Smb2DereferenceShare(v7);
LABEL_33:
    Srv2DereferenceInstance(v4);
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  return 0;
}

```

## disassembly

```asm
0x140064168  push    rbx
0x14006416a  push    rbp
0x14006416b  push    rsi
0x14006416c  push    rdi
0x14006416d  push    r12
0x14006416f  push    r13
0x140064171  push    r14
0x140064173  push    r15
0x140064175  sub     rsp, 88h
0x14006417c  mov     eax, [rcx+80h]
0x140064182  xor     r13d, r13d
0x140064185  mov     rdi, rcx
0x140064188  mov     qword ptr [rsp+0C8h+var_58], r13
0x14006418d  mov     ecx, 21000h
0x140064192  mov     qword ptr [rsp+0C8h+var_58+8], r13
0x140064197  and     eax, ecx
0x140064199  mov     esi, r13d
0x14006419c  cmp     eax, ecx
0x14006419e  jz      loc_1400644BE
0x1400641a4  mov     ecx, [rdi+98h]
0x1400641aa  call    Srv2GetInstance
0x1400641af  mov     r15, rax
0x1400641b2  test    rax, rax
0x1400641b5  jz      loc_1400644D4
0x1400641bb  mov     cl, [rdi+32h]
0x1400641be  lea     r8, [rdi+18h]
0x1400641c2  mov     [rsp+0C8h+var_90], cl
0x1400641c6  lea     rdx, [rdi+8]
0x1400641ca  mov     rcx, [rax+0A0h]
0x1400641d1  lea     r9, [rsp+0C8h+arg_0]
0x1400641d9  mov     byte ptr [rsp+0C8h+var_98], r13b
0x1400641de  mov     ebp, r13d
0x1400641e1  mov     [rsp+0C8h+var_A0], r13
0x1400641e6  mov     [rsp+0C8h+var_A8], r13
0x1400641eb  mov     [rsp+0C8h+arg_0], r13
0x1400641f3  call    Smb2FindShareAndSetServerName
0x1400641f8  mov     rbx, [rsp+0C8h+arg_0]
0x140064200  test    rbx, rbx
0x140064203  jz      loc_1400644A0
0x140064209  mov     rcx, [rdi+0C0h]; SecurityDescriptor
0x140064210  mov     r12d, [rdi+80h]
0x140064217  test    rcx, rcx
0x14006421a  jz      short loc_140064262
0x14006421c  call    cs:__imp_RtlLengthSecurityDescriptor
0x140064223  nop     dword ptr [rax+rax+00h]
0x140064228  mov     edx, eax
0x14006422a  mov     r8d, 6832534Ch
0x140064230  mov     ecx, 102h
0x140064235  mov     r14d, eax
0x140064238  call    cs:__imp_ExAllocatePool2
0x14006423f  nop     dword ptr [rax+rax+00h]
0x140064244  mov     rbp, rax
0x140064247  test    rax, rax
0x14006424a  jz      loc_140064498
0x140064250  mov     rdx, [rdi+0C0h]; Src
0x140064257  mov     r8d, r14d; Size
0x14006425a  mov     rcx, rax; void *
0x14006425d  call    memmove
0x140064262  movzx   eax, word ptr [rdi+0C8h]
0x140064269  test    ax, ax
0x14006426c  jz      short loc_1400642C0
0x14006426e  mov     edx, eax
0x140064270  mov     ecx, 102h
0x140064275  mov     r8d, 6832534Ch
0x14006427b  call    cs:__imp_ExAllocatePool2
0x140064282  nop     dword ptr [rax+rax+00h]
0x140064287  mov     qword ptr [rsp+0C8h+var_58+8], rax
0x14006428c  mov     rsi, rax
0x14006428f  test    rax, rax
0x140064292  jz      loc_140064498
0x140064298  movzx   r8d, word ptr [rdi+0C8h]; Size
0x1400642a0  mov     rcx, rax; void *
0x1400642a3  mov     rdx, [rdi+0D0h]; Src
0x1400642aa  call    memmove
0x1400642af  movzx   eax, word ptr [rdi+0C8h]
0x1400642b6  mov     word ptr [rsp+0C8h+var_58+2], ax
0x1400642bb  mov     word ptr [rsp+0C8h+var_58], ax
0x1400642c0  mov     rcx, [rbx]
0x1400642c3  mov     dl, 1; Wait
0x1400642c5  add     rcx, 60h ; '`'; Resource
0x1400642c9  movzx   r14d, r13b
0x1400642cd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400642d4  nop     dword ptr [rax+rax+00h]
0x1400642d9  mov     rcx, [rbx+108h]; P
0x1400642e0  test    rcx, rcx
0x1400642e3  jz      short loc_1400642F3
0x1400642e5  xor     edx, edx; Tag
0x1400642e7  call    cs:__imp_ExFreePoolWithTag
0x1400642ee  nop     dword ptr [rax+rax+00h]
0x1400642f3  mov     rcx, [rbx+0C0h]; P
0x1400642fa  mov     edx, 1
0x1400642ff  add     [rbx+110h], edx
0x140064305  mov     [rbx+108h], rbp
0x14006430c  mov     rbp, r13
0x14006430f  test    rcx, rcx
0x140064312  jz      short loc_140064327
0x140064314  xor     edx, edx; Tag
0x140064316  call    cs:__imp_ExFreePoolWithTag
0x14006431d  nop     dword ptr [rax+rax+00h]
0x140064322  mov     edx, 1
0x140064327  movups  xmm0, [rsp+0C8h+var_58]
0x14006432c  mov     r8d, r12d
0x14006432f  mov     rsi, r13
0x140064332  and     r8d, 0FFFFFFCFh
0x140064336  and     r12d, 30h
0x14006433a  movdqu  xmmword ptr [rbx+0B8h], xmm0
0x140064342  mov     [rbx+120h], r8d
0x140064349  mov     [rbx+124h], r12d
0x140064350  mov     r10d, [rdi+8Ch]
0x140064357  mov     [rbx+128h], r10d
0x14006435e  cmp     [rbx+114h], r13b
0x140064365  jnz     short loc_14006438C
0x140064367  cmp     [rbx+115h], r13b
0x14006436e  jnz     short loc_14006438C
0x140064370  mov     eax, [rdi+84h]
0x140064376  test    dl, al
0x140064378  jnz     short loc_14006437E
0x14006437a  test    al, 2
0x14006437c  jz      short loc_14006438C
0x14006437e  lea     rax, [rbx+0D0h]
0x140064385  cmp     [rax], rax
0x140064388  cmovnz  r14d, edx
0x14006438c  mov     eax, [rdi+90h]
0x140064392  test    eax, eax
0x140064394  jz      short loc_14006439C
0x140064396  mov     [rbx+12Ch], eax
0x14006439c  mov     eax, [rdi+84h]
0x1400643a2  and     eax, edx
0x1400643a4  jz      short loc_1400643AB
0x1400643a6  or      r8d, edx
0x1400643a9  jmp     short loc_1400643AF
0x1400643ab  and     r8d, 0FFFFFFFEh
0x1400643af  mov     [rbx+114h], al
0x1400643b5  mov     eax, r8d
0x1400643b8  mov     [rbx+120h], r8d
0x1400643bf  and     eax, 0FFFFFFFDh
0x1400643c2  mov     ecx, [rdi+84h]
0x1400643c8  or      r8d, 2
0x1400643cc  bt      ecx, 1
0x1400643d0  cmovnb  r8d, eax
0x1400643d4  setb    al
0x1400643d7  mov     [rbx+120h], r8d
0x1400643de  mov     [rbx+115h], al
0x1400643e4  mov     eax, [rdi+0D8h]
0x1400643ea  mov     [rbx+1A0h], eax
0x1400643f0  movups  xmm0, xmmword ptr [rdi+0DCh]
0x1400643f7  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400643fc  test    cs:byte_14004C339, 20h
0x140064403  jz      short loc_140064476
0x140064405  mov     eax, [rbx+12Ch]
0x14006440b  movzx   edx, word ptr [rbx+58h]
0x14006440f  movzx   ecx, word ptr [rbx+98h]
0x140064416  movzx   r9d, word ptr [rbx+48h]
0x14006441b  mov     [rsp+0C8h+var_60], r10d
0x140064420  mov     [rsp+0C8h+var_68], eax
0x140064424  mov     eax, [rbx+170h]
0x14006442a  mov     [rsp+0C8h+var_70], r8d
0x14006442f  mov     [rsp+0C8h+var_78], eax
0x140064433  mov     rax, [rbx+0A0h]
0x14006443a  mov     [rsp+0C8h+var_80], r12d
0x14006443f  mov     [rsp+0C8h+var_88], rax
0x140064444  mov     rax, [rbx+60h]
0x140064448  shr     dx, 1
0x14006444b  shr     cx, 1
0x14006444e  mov     word ptr [rsp+0C8h+var_90], cx
0x140064453  mov     [rsp+0C8h+var_98], rax
0x140064458  mov     rax, [rbx+50h]
0x14006445c  mov     word ptr [rsp+0C8h+var_A0], dx
0x140064461  lea     rdx, SMB2_EVENT_SHARE_MODIFY
0x140064468  shr     r9w, 1
0x14006446c  mov     [rsp+0C8h+var_A8], rax
0x140064471  call    McTemplateK0hzr0hzr2hzr4qqqqq_EtwWriteTransfer
0x140064476  test    r14b, r14b
0x140064479  jz      short loc_140064485
0x14006447b  xor     edx, edx
0x14006447d  mov     rcx, rbx
0x140064480  call    Smb2CloseTreeConnectsOnShare
0x140064485  mov     rcx, [rbx]
0x140064488  add     rcx, 60h ; '`'; Resource
0x14006448c  call    cs:__imp_ExReleaseResourceLite
0x140064493  nop     dword ptr [rax+rax+00h]
0x140064498  mov     rcx, rbx
0x14006449b  call    Smb2DereferenceShare
0x1400644a0  mov     rcx, r15; Context
0x1400644a3  call    Srv2DereferenceInstance
0x1400644a8  test    rbp, rbp
0x1400644ab  jz      short loc_1400644BE
0x1400644ad  xor     edx, edx; Tag
0x1400644af  mov     rcx, rbp; P
0x1400644b2  call    cs:__imp_ExFreePoolWithTag
0x1400644b9  nop     dword ptr [rax+rax+00h]
0x1400644be  test    rsi, rsi
0x1400644c1  jz      short loc_1400644D4
0x1400644c3  xor     edx, edx; Tag
0x1400644c5  mov     rcx, rsi; P
0x1400644c8  call    cs:__imp_ExFreePoolWithTag
0x1400644cf  nop     dword ptr [rax+rax+00h]
0x1400644d4  xor     eax, eax
0x1400644d6  add     rsp, 88h
0x1400644dd  pop     r15
0x1400644df  pop     r14
0x1400644e1  pop     r13
0x1400644e3  pop     r12
0x1400644e5  pop     rdi
0x1400644e6  pop     rsi
0x1400644e7  pop     rbp
0x1400644e8  pop     rbx
0x1400644e9  retn
```
