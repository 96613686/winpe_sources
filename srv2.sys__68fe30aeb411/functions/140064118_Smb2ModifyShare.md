# Smb2ModifyShare

- ea: `0x140064118`
- end: `0x14006449b`
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
- `0x140063a7c`
- `0x140064118`
- `0x140076fd0`
- `0x140085d00`
- `0x14008b4f0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400641e8`
- `ntoskrnl!ExAllocatePool2` at `0x14006422b`
- `ntoskrnl!ExAllocatePool2` at `0x1400641e8`
- `ntoskrnl!ExAllocatePool2` at `0x14006422b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006443c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006443c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006427d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14006427d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400642c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064462`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064478`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400642c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064462`
- `ntoskrnl!ExFreePoolWithTag` at `0x140064478`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400641cc`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400641cc`

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
0x140064118  push    rbx
0x14006411a  push    rbp
0x14006411b  push    rsi
0x14006411c  push    rdi
0x14006411d  push    r12
0x14006411f  push    r13
0x140064121  push    r14
0x140064123  push    r15
0x140064125  sub     rsp, 88h
0x14006412c  mov     eax, [rcx+80h]
0x140064132  xor     r13d, r13d
0x140064135  mov     rdi, rcx
0x140064138  mov     qword ptr [rsp+0C8h+var_58], r13
0x14006413d  mov     ecx, 21000h
0x140064142  mov     qword ptr [rsp+0C8h+var_58+8], r13
0x140064147  and     eax, ecx
0x140064149  mov     esi, r13d
0x14006414c  cmp     eax, ecx
0x14006414e  jz      loc_14006446E
0x140064154  mov     ecx, [rdi+98h]
0x14006415a  call    Srv2GetInstance
0x14006415f  mov     r15, rax
0x140064162  test    rax, rax
0x140064165  jz      loc_140064484
0x14006416b  mov     cl, [rdi+32h]
0x14006416e  lea     r8, [rdi+18h]
0x140064172  mov     [rsp+0C8h+var_90], cl
0x140064176  lea     rdx, [rdi+8]
0x14006417a  mov     rcx, [rax+0A0h]
0x140064181  lea     r9, [rsp+0C8h+arg_0]
0x140064189  mov     byte ptr [rsp+0C8h+var_98], r13b
0x14006418e  mov     ebp, r13d
0x140064191  mov     [rsp+0C8h+var_A0], r13
0x140064196  mov     [rsp+0C8h+var_A8], r13
0x14006419b  mov     [rsp+0C8h+arg_0], r13
0x1400641a3  call    Smb2FindShareAndSetServerName
0x1400641a8  mov     rbx, [rsp+0C8h+arg_0]
0x1400641b0  test    rbx, rbx
0x1400641b3  jz      loc_140064450
0x1400641b9  mov     rcx, [rdi+0C0h]; SecurityDescriptor
0x1400641c0  mov     r12d, [rdi+80h]
0x1400641c7  test    rcx, rcx
0x1400641ca  jz      short loc_140064212
0x1400641cc  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400641d3  nop     dword ptr [rax+rax+00h]
0x1400641d8  mov     edx, eax
0x1400641da  mov     r8d, 6832534Ch
0x1400641e0  mov     ecx, 102h
0x1400641e5  mov     r14d, eax
0x1400641e8  call    cs:__imp_ExAllocatePool2
0x1400641ef  nop     dword ptr [rax+rax+00h]
0x1400641f4  mov     rbp, rax
0x1400641f7  test    rax, rax
0x1400641fa  jz      loc_140064448
0x140064200  mov     rdx, [rdi+0C0h]; Src
0x140064207  mov     r8d, r14d; Size
0x14006420a  mov     rcx, rax; void *
0x14006420d  call    memmove
0x140064212  movzx   eax, word ptr [rdi+0C8h]
0x140064219  test    ax, ax
0x14006421c  jz      short loc_140064270
0x14006421e  mov     edx, eax
0x140064220  mov     ecx, 102h
0x140064225  mov     r8d, 6832534Ch
0x14006422b  call    cs:__imp_ExAllocatePool2
0x140064232  nop     dword ptr [rax+rax+00h]
0x140064237  mov     qword ptr [rsp+0C8h+var_58+8], rax
0x14006423c  mov     rsi, rax
0x14006423f  test    rax, rax
0x140064242  jz      loc_140064448
0x140064248  movzx   r8d, word ptr [rdi+0C8h]; Size
0x140064250  mov     rcx, rax; void *
0x140064253  mov     rdx, [rdi+0D0h]; Src
0x14006425a  call    memmove
0x14006425f  movzx   eax, word ptr [rdi+0C8h]
0x140064266  mov     word ptr [rsp+0C8h+var_58+2], ax
0x14006426b  mov     word ptr [rsp+0C8h+var_58], ax
0x140064270  mov     rcx, [rbx]
0x140064273  mov     dl, 1; Wait
0x140064275  add     rcx, 60h ; '`'; Resource
0x140064279  movzx   r14d, r13b
0x14006427d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140064284  nop     dword ptr [rax+rax+00h]
0x140064289  mov     rcx, [rbx+108h]; P
0x140064290  test    rcx, rcx
0x140064293  jz      short loc_1400642A3
0x140064295  xor     edx, edx; Tag
0x140064297  call    cs:__imp_ExFreePoolWithTag
0x14006429e  nop     dword ptr [rax+rax+00h]
0x1400642a3  mov     rcx, [rbx+0C0h]; P
0x1400642aa  mov     edx, 1
0x1400642af  add     [rbx+110h], edx
0x1400642b5  mov     [rbx+108h], rbp
0x1400642bc  mov     rbp, r13
0x1400642bf  test    rcx, rcx
0x1400642c2  jz      short loc_1400642D7
0x1400642c4  xor     edx, edx; Tag
0x1400642c6  call    cs:__imp_ExFreePoolWithTag
0x1400642cd  nop     dword ptr [rax+rax+00h]
0x1400642d2  mov     edx, 1
0x1400642d7  movups  xmm0, [rsp+0C8h+var_58]
0x1400642dc  mov     r8d, r12d
0x1400642df  mov     rsi, r13
0x1400642e2  and     r8d, 0FFFFFFCFh
0x1400642e6  and     r12d, 30h
0x1400642ea  movdqu  xmmword ptr [rbx+0B8h], xmm0
0x1400642f2  mov     [rbx+120h], r8d
0x1400642f9  mov     [rbx+124h], r12d
0x140064300  mov     r10d, [rdi+8Ch]
0x140064307  mov     [rbx+128h], r10d
0x14006430e  cmp     [rbx+114h], r13b
0x140064315  jnz     short loc_14006433C
0x140064317  cmp     [rbx+115h], r13b
0x14006431e  jnz     short loc_14006433C
0x140064320  mov     eax, [rdi+84h]
0x140064326  test    dl, al
0x140064328  jnz     short loc_14006432E
0x14006432a  test    al, 2
0x14006432c  jz      short loc_14006433C
0x14006432e  lea     rax, [rbx+0D0h]
0x140064335  cmp     [rax], rax
0x140064338  cmovnz  r14d, edx
0x14006433c  mov     eax, [rdi+90h]
0x140064342  test    eax, eax
0x140064344  jz      short loc_14006434C
0x140064346  mov     [rbx+12Ch], eax
0x14006434c  mov     eax, [rdi+84h]
0x140064352  and     eax, edx
0x140064354  jz      short loc_14006435B
0x140064356  or      r8d, edx
0x140064359  jmp     short loc_14006435F
0x14006435b  and     r8d, 0FFFFFFFEh
0x14006435f  mov     [rbx+114h], al
0x140064365  mov     eax, r8d
0x140064368  mov     [rbx+120h], r8d
0x14006436f  and     eax, 0FFFFFFFDh
0x140064372  mov     ecx, [rdi+84h]
0x140064378  or      r8d, 2
0x14006437c  bt      ecx, 1
0x140064380  cmovnb  r8d, eax
0x140064384  setb    al
0x140064387  mov     [rbx+120h], r8d
0x14006438e  mov     [rbx+115h], al
0x140064394  mov     eax, [rdi+0D8h]
0x14006439a  mov     [rbx+1A0h], eax
0x1400643a0  movups  xmm0, xmmword ptr [rdi+0DCh]
0x1400643a7  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400643ac  test    cs:byte_14004C339, 20h
0x1400643b3  jz      short loc_140064426
0x1400643b5  mov     eax, [rbx+12Ch]
0x1400643bb  movzx   edx, word ptr [rbx+58h]
0x1400643bf  movzx   ecx, word ptr [rbx+98h]
0x1400643c6  movzx   r9d, word ptr [rbx+48h]
0x1400643cb  mov     [rsp+0C8h+var_60], r10d
0x1400643d0  mov     [rsp+0C8h+var_68], eax
0x1400643d4  mov     eax, [rbx+170h]
0x1400643da  mov     [rsp+0C8h+var_70], r8d
0x1400643df  mov     [rsp+0C8h+var_78], eax
0x1400643e3  mov     rax, [rbx+0A0h]
0x1400643ea  mov     [rsp+0C8h+var_80], r12d
0x1400643ef  mov     [rsp+0C8h+var_88], rax
0x1400643f4  mov     rax, [rbx+60h]
0x1400643f8  shr     dx, 1
0x1400643fb  shr     cx, 1
0x1400643fe  mov     word ptr [rsp+0C8h+var_90], cx
0x140064403  mov     [rsp+0C8h+var_98], rax
0x140064408  mov     rax, [rbx+50h]
0x14006440c  mov     word ptr [rsp+0C8h+var_A0], dx
0x140064411  lea     rdx, SMB2_EVENT_SHARE_MODIFY
0x140064418  shr     r9w, 1
0x14006441c  mov     [rsp+0C8h+var_A8], rax
0x140064421  call    McTemplateK0hzr0hzr2hzr4qqqqq_EtwWriteTransfer
0x140064426  test    r14b, r14b
0x140064429  jz      short loc_140064435
0x14006442b  xor     edx, edx
0x14006442d  mov     rcx, rbx
0x140064430  call    Smb2CloseTreeConnectsOnShare
0x140064435  mov     rcx, [rbx]
0x140064438  add     rcx, 60h ; '`'; Resource
0x14006443c  call    cs:__imp_ExReleaseResourceLite
0x140064443  nop     dword ptr [rax+rax+00h]
0x140064448  mov     rcx, rbx
0x14006444b  call    Smb2DereferenceShare
0x140064450  mov     rcx, r15; Context
0x140064453  call    Srv2DereferenceInstance
0x140064458  test    rbp, rbp
0x14006445b  jz      short loc_14006446E
0x14006445d  xor     edx, edx; Tag
0x14006445f  mov     rcx, rbp; P
0x140064462  call    cs:__imp_ExFreePoolWithTag
0x140064469  nop     dword ptr [rax+rax+00h]
0x14006446e  test    rsi, rsi
0x140064471  jz      short loc_140064484
0x140064473  xor     edx, edx; Tag
0x140064475  mov     rcx, rsi; P
0x140064478  call    cs:__imp_ExFreePoolWithTag
0x14006447f  nop     dword ptr [rax+rax+00h]
0x140064484  xor     eax, eax
0x140064486  add     rsp, 88h
0x14006448d  pop     r15
0x14006448f  pop     r14
0x140064491  pop     r13
0x140064493  pop     r12
0x140064495  pop     rdi
0x140064496  pop     rsi
0x140064497  pop     rbp
0x140064498  pop     rbx
0x140064499  retn
```
