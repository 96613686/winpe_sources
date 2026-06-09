# VMX_PHYSICAL_DISK::CreateMetadataPartition(_DRIVE_LAYOUT_INFORMATION_EX *)

- ea: `0x1400452a4`
- end: `0x14004578f`
- name: `?CreateMetadataPartition@VMX_PHYSICAL_DISK@@AEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(VMX_DISK_DEVICE **this, struct _DRIVE_LAYOUT_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140029294`

## callees

- `0x140006c0c`
- `0x1400099d8`
- `0x14001ba60`
- `0x14001bb80`
- `0x14001be80`
- `0x1400342bc`
- `0x1400452a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400452d9`
- `ntoskrnl!ExAllocatePool2` at `0x1400452d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004542f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045483`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045551`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004559f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045668`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400456e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045732`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004542f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045483`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045551`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004559f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045668`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400456e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045732`
- `ntoskrnl!ExUuidCreate` at `0x140045417`
- `ntoskrnl!ExUuidCreate` at `0x140045651`
- `ntoskrnl!ExUuidCreate` at `0x140045417`
- `ntoskrnl!ExUuidCreate` at `0x140045651`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::CreateMetadataPartition(
        VMX_DISK_DEVICE **this,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2)
{
  DWORD PartitionCount; // eax
  size_t v4; // rbx
  _QWORD *Pool2; // rax
  _QWORD *v6; // rdi
  VMX_NOTIFICATION_QUEUE *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _DWORD *v10; // rbx
  unsigned __int64 v11; // rsi
  __int64 v12; // r12
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rbp
  unsigned int v16; // r13d
  __int64 v17; // rcx
  __int64 v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // r14
  unsigned int v22; // r12d
  VMX_NOTIFICATION_QUEUE *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  unsigned __int64 v27; // rbp
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rbx
  NTSTATUS v33; // esi
  unsigned __int64 v35; // [rsp+88h] [rbp+20h]

  PartitionCount = a2->PartitionCount;
  v4 = 144 * PartitionCount + 48;
  Pool2 = (_QWORD *)ExAllocatePool2(258, 144 * PartitionCount + 336, 1632398678);
  v6 = Pool2;
  if ( !Pool2 )
  {
    v7 = WPP_GLOBAL_Control;
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return v8;
    }
    v9 = 71;
LABEL_65:
    WPP_SF_d(*((_QWORD *)v7 + 3), v9, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v8);
    return v8;
  }
  memmove(Pool2, a2, v4);
  memset((char *)v6 + v4, 0, 0x120u);
  v10 = 0;
  v11 = v6[3];
  v12 = *((unsigned int *)v6 + 1);
  v13 = v11;
  v35 = v6[4];
  v14 = v35 + v11;
  v15 = v35 + v11;
  if ( (_DWORD)v12 )
  {
    v16 = 0;
    do
    {
      v17 = 18LL * v16;
      v18 = (__int64)&v6[v17 + 6];
      if ( !memcmp(&v6[v17 + 10], &PARTITION_MSFT_RESERVED_GUID, 0x10u) && !v10 )
        v10 = (_DWORD *)v18;
      v19 = *(_QWORD *)(v18 + 8);
      v20 = v19 + *(_QWORD *)(v18 + 16);
      if ( v19 >= v15 )
        v19 = v15;
      v15 = v19;
      if ( v20 <= v13 )
        v20 = v13;
      ++v16;
      v13 = v20;
    }
    while ( v16 < (unsigned int)v12 );
    v14 = v35 + v11;
  }
  *((_DWORD *)v6 + 1) = v12 + 1;
  v21 = 18 * v12;
  LODWORD(v6[v21 + 6]) = 1;
  v6[v21 + 8] = 0x100000;
  BYTE4(v6[v21 + 9]) = 1;
  *(GUID *)&v6[v21 + 10] = PARTITION_LDM_METADATA_GUID;
  v22 = ExUuidCreate((UUID *)&v6[18 * v12 + 12]);
  if ( (v22 & 0x80000000) != 0 )
  {
    ExFreePoolWithTag(v6, 0);
    return v22;
  }
  v6[v21 + 14] = 0;
  RtlStringCbCopyW((NTSTRSAFE_PWSTR)&v6[v21 + 15], 0x48u, L"LDM metadata partition");
  v22 = -1070071789;
  if ( v10 )
  {
    if ( *((_QWORD *)v10 + 2) < 0x100000u )
    {
      ExFreePoolWithTag(v6, 0);
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v22;
      }
      v25 = 72;
      goto LABEL_45;
    }
    v6[v21 + 7] = *((_QWORD *)v10 + 1);
    v26 = *((_QWORD *)v10 + 2);
    if ( v26 == 0x100000 )
    {
      memset(v10, 0, 0x90u);
      *v10 = 1;
    }
    else
    {
      *((_QWORD *)v10 + 1) += 0x100000LL;
      *((_QWORD *)v10 + 2) = v26 - 0x100000;
    }
    *((_BYTE *)v10 + 28) = 1;
LABEL_55:
    if ( *((_DWORD *)v6 + 1) <= *((_DWORD *)v6 + 10) )
    {
      v8 = VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(this[2], (unsigned int *)v6);
      ExFreePoolWithTag(v6, 0);
      if ( (v8 & 0x80000000) == 0 )
        return v8;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v8;
      }
      v9 = 77;
    }
    else
    {
      ExFreePoolWithTag(v6, 0);
      v7 = WPP_GLOBAL_Control;
      v8 = -1070071792;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return v8;
      }
      v9 = 76;
    }
    goto LABEL_65;
  }
  v27 = v15 - v11;
  v28 = (-(__int64)(v35 < 0x400000000LL) & 0xFFFFFFFFFA000000uLL) + 0x8000000;
  if ( v28 > v27 )
  {
    v29 = v14 - v13;
    if ( v28 <= v14 - v13 )
    {
      v11 = v14 - v28;
      goto LABEL_47;
    }
    if ( v27 < v29 )
    {
      if ( v29 < 0x100000 )
      {
        ExFreePoolWithTag(v6, 0);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return v22;
        }
        v25 = 74;
LABEL_45:
        WPP_SF_d(*((_QWORD *)v24 + 3), v25, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3224895507LL);
        return v22;
      }
      v11 = v13;
      v28 = v14 - v13;
    }
    else
    {
      if ( v27 < 0x100000 )
      {
        ExFreePoolWithTag(v6, 0);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return v22;
        }
        v25 = 73;
        goto LABEL_45;
      }
      v28 = v27;
    }
  }
LABEL_47:
  v30 = v28 - 0x100000;
  v6[v21 + 7] = v11;
  if ( v28 == 0x100000 )
    goto LABEL_55;
  v31 = *((unsigned int *)v6 + 1);
  v32 = 18 * v31;
  *((_DWORD *)v6 + 1) = v31 + 1;
  v6[v32 + 8] = v30;
  v6[v32 + 7] = v11 + 0x100000;
  LODWORD(v6[v32 + 6]) = 1;
  BYTE4(v6[v32 + 9]) = 1;
  *(GUID *)&v6[v32 + 10] = PARTITION_MSFT_RESERVED_GUID;
  v33 = ExUuidCreate((UUID *)&v6[18 * v31 + 12]);
  if ( v33 >= 0 )
  {
    v6[v32 + 14] = 0;
    RtlStringCbCopyW((NTSTRSAFE_PWSTR)&v6[v32 + 15], 0x48u, L"Microsoft reserved partition");
    goto LABEL_55;
  }
  ExFreePoolWithTag(v6, 0);
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      75,
      WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids,
      (unsigned int)v33);
  }
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x1400452a4  mov     [rsp+arg_0], rcx
0x1400452a9  push    rbx
0x1400452aa  push    rbp
0x1400452ab  push    rsi
0x1400452ac  push    rdi
0x1400452ad  push    r12
0x1400452af  push    r13
0x1400452b1  push    r14
0x1400452b3  push    r15
0x1400452b5  sub     rsp, 28h
0x1400452b9  mov     eax, [rdx+4]
0x1400452bc  mov     rsi, rdx
0x1400452bf  mov     ecx, 102h
0x1400452c4  mov     r8d, 614C6D56h
0x1400452ca  lea     ebx, [rax+rax*8]
0x1400452cd  shl     ebx, 4
0x1400452d0  add     ebx, 30h ; '0'
0x1400452d3  lea     edx, [rbx+120h]
0x1400452d9  call    cs:__imp_ExAllocatePool2
0x1400452e0  nop     dword ptr [rax+rax+00h]
0x1400452e5  mov     rdi, rax
0x1400452e8  test    rax, rax
0x1400452eb  jnz     short loc_140045326
0x1400452ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400452f4  lea     rax, WPP_GLOBAL_Control
0x1400452fb  mov     ebx, 0C000009Ah
0x140045300  cmp     rcx, rax
0x140045303  jz      loc_14004577B
0x140045309  mov     eax, [rcx+2Ch]
0x14004530c  test    al, 10h
0x14004530e  jz      loc_14004577B
0x140045314  cmp     byte ptr [rcx+29h], 2
0x140045318  jb      loc_14004577B
0x14004531e  lea     edx, [rdi+47h]
0x140045321  jmp     loc_140045768
0x140045326  mov     r8, rbx; Size
0x140045329  mov     rdx, rsi; Src
0x14004532c  mov     rcx, rdi; void *
0x14004532f  call    memmove
0x140045334  lea     rcx, [rbx+rdi]; void *
0x140045338  xor     edx, edx; Val
0x14004533a  mov     r8d, 120h; Size
0x140045340  call    memset
0x140045345  mov     rax, [rdi+20h]
0x140045349  xor     ebx, ebx
0x14004534b  mov     rsi, [rdi+18h]
0x14004534f  mov     r12d, [rdi+4]
0x140045353  mov     r15, rsi
0x140045356  mov     [rsp+68h+arg_18], rax
0x14004535e  lea     r13, [rax+rsi]
0x140045362  mov     [rsp+68h+arg_10], r13
0x14004536a  mov     rbp, r13
0x14004536d  test    r12d, r12d
0x140045370  jz      short loc_1400453DA
0x140045372  mov     r13d, ebx
0x140045375  mov     eax, r13d
0x140045378  lea     r14, [rdi+30h]
0x14004537c  mov     r8d, 10h; Size
0x140045382  lea     rdx, PARTITION_MSFT_RESERVED_GUID; Buf2
0x140045389  lea     rcx, [rax+rax*8]
0x14004538d  shl     rcx, 4
0x140045391  add     r14, rcx
0x140045394  add     rcx, 50h ; 'P'
0x140045398  add     rcx, rdi; Buf1
0x14004539b  call    memcmp
0x1400453a0  test    eax, eax
0x1400453a2  jnz     short loc_1400453AB
0x1400453a4  test    rbx, rbx
0x1400453a7  cmovz   rbx, r14
0x1400453ab  mov     rcx, [r14+8]
0x1400453af  mov     rdx, [r14+10h]
0x1400453b3  add     rdx, rcx
0x1400453b6  cmp     rcx, rbp
0x1400453b9  cmovnb  rcx, rbp
0x1400453bd  cmp     rdx, r15
0x1400453c0  mov     rbp, rcx
0x1400453c3  cmovbe  rdx, r15
0x1400453c7  inc     r13d
0x1400453ca  mov     r15, rdx
0x1400453cd  cmp     r13d, r12d
0x1400453d0  jb      short loc_140045375
0x1400453d2  mov     r13, [rsp+68h+arg_10]
0x1400453da  lea     eax, [r12+1]
0x1400453df  mov     [rdi+4], eax
0x1400453e2  lea     r14, [r12+r12*8]
0x1400453e6  shl     r14, 4
0x1400453ea  mov     dword ptr [r14+rdi+30h], 1
0x1400453f3  lea     rcx, [r14+60h]
0x1400453f7  mov     qword ptr [r14+rdi+40h], 100000h
0x140045400  add     rcx, rdi; Uuid
0x140045403  mov     byte ptr [r14+rdi+4Ch], 1
0x140045409  movups  xmm0, xmmword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x140045410  movdqu  xmmword ptr [r14+rdi+50h], xmm0
0x140045417  call    cs:__imp_ExUuidCreate
0x14004541e  nop     dword ptr [rax+rax+00h]
0x140045423  mov     r12d, eax
0x140045426  test    eax, eax
0x140045428  jns     short loc_140045443
0x14004542a  xor     edx, edx; Tag
0x14004542c  mov     rcx, rdi; P
0x14004542f  call    cs:__imp_ExFreePoolWithTag
0x140045436  nop     dword ptr [rax+rax+00h]
0x14004543b  mov     eax, r12d
0x14004543e  jmp     loc_14004577D
0x140045443  lea     rcx, [rdi+78h]
0x140045447  mov     qword ptr [r14+rdi+70h], 0
0x140045450  add     rcx, r14; pszDest
0x140045453  lea     r8, aLdmMetadataPar; "LDM metadata partition"
0x14004545a  mov     edx, 48h ; 'H'; cbDest
0x14004545f  call    RtlStringCbCopyW
0x140045464  mov     r12d, 0C0380013h
0x14004546a  test    rbx, rbx
0x14004546d  jz      loc_1400454FA
0x140045473  mov     edx, 100000h
0x140045478  cmp     [rbx+10h], rdx
0x14004547c  jnb     short loc_1400454B9
0x14004547e  xor     edx, edx; Tag
0x140045480  mov     rcx, rdi; P
0x140045483  call    cs:__imp_ExFreePoolWithTag
0x14004548a  nop     dword ptr [rax+rax+00h]
0x14004548f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045496  lea     rax, WPP_GLOBAL_Control
0x14004549d  cmp     rcx, rax
0x1400454a0  jz      short loc_14004543B
0x1400454a2  mov     eax, [rcx+2Ch]
0x1400454a5  test    al, 10h
0x1400454a7  jz      short loc_14004543B
0x1400454a9  cmp     byte ptr [rcx+29h], 2
0x1400454ad  jb      short loc_14004543B
0x1400454af  mov     edx, 48h ; 'H'
0x1400454b4  jmp     loc_1400455DC
0x1400454b9  mov     rax, [rbx+8]
0x1400454bd  mov     [r14+rdi+38h], rax
0x1400454c2  mov     rax, [rbx+10h]
0x1400454c6  cmp     rax, rdx
0x1400454c9  jnz     short loc_1400454E3
0x1400454cb  xor     edx, edx; Val
0x1400454cd  mov     r8d, 90h; Size
0x1400454d3  mov     rcx, rbx; void *
0x1400454d6  call    memset
0x1400454db  mov     dword ptr [rbx], 1
0x1400454e1  jmp     short loc_1400454F1
0x1400454e3  add     [rbx+8], rdx
0x1400454e7  add     rax, 0FFFFFFFFFFF00000h
0x1400454ed  mov     [rbx+10h], rax
0x1400454f1  mov     byte ptr [rbx+1Ch], 1
0x1400454f5  jmp     loc_1400456D5
0x1400454fa  mov     rax, 400000000h
0x140045504  cmp     [rsp+68h+arg_18], rax
0x14004550c  sbb     rax, rax
0x14004550f  sub     rbp, rsi
0x140045512  and     rax, 0FFFFFFFFFA000000h
0x140045518  add     rax, 8000000h
0x14004551e  cmp     rax, rbp
0x140045521  jbe     loc_1400455FA
0x140045527  mov     rcx, r13
0x14004552a  sub     rcx, r15
0x14004552d  cmp     rax, rcx
0x140045530  ja      short loc_14004553D
0x140045532  mov     rsi, r13
0x140045535  sub     rsi, rax
0x140045538  jmp     loc_1400455FA
0x14004553d  mov     edx, 100000h
0x140045542  cmp     rbp, rcx
0x140045545  jb      short loc_140045595
0x140045547  cmp     rbp, rdx
0x14004554a  jnb     short loc_140045590
0x14004554c  xor     edx, edx; Tag
0x14004554e  mov     rcx, rdi; P
0x140045551  call    cs:__imp_ExFreePoolWithTag
0x140045558  nop     dword ptr [rax+rax+00h]
0x14004555d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045564  lea     rax, WPP_GLOBAL_Control
0x14004556b  cmp     rcx, rax
0x14004556e  jz      loc_14004543B
0x140045574  mov     eax, [rcx+2Ch]
0x140045577  test    al, 10h
0x140045579  jz      loc_14004543B
0x14004557f  cmp     byte ptr [rcx+29h], 2
0x140045583  jb      loc_14004543B
0x140045589  mov     edx, 49h ; 'I'
0x14004558e  jmp     short loc_1400455DC
0x140045590  mov     rax, rbp
0x140045593  jmp     short loc_1400455FA
0x140045595  cmp     rcx, rdx
0x140045598  jnb     short loc_1400455F4
0x14004559a  xor     edx, edx; Tag
0x14004559c  mov     rcx, rdi; P
0x14004559f  call    cs:__imp_ExFreePoolWithTag
0x1400455a6  nop     dword ptr [rax+rax+00h]
0x1400455ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455b2  lea     rax, WPP_GLOBAL_Control
0x1400455b9  cmp     rcx, rax
0x1400455bc  jz      loc_14004543B
0x1400455c2  mov     eax, [rcx+2Ch]
0x1400455c5  test    al, 10h
0x1400455c7  jz      loc_14004543B
0x1400455cd  cmp     byte ptr [rcx+29h], 2
0x1400455d1  jb      loc_14004543B
0x1400455d7  mov     edx, 4Ah ; 'J'
0x1400455dc  mov     rcx, [rcx+18h]
0x1400455e0  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x1400455e7  mov     r9d, r12d
0x1400455ea  call    WPP_SF_d
0x1400455ef  jmp     loc_14004543B
0x1400455f4  mov     rsi, r15
0x1400455f7  mov     rax, rcx
0x1400455fa  lea     rcx, [rax-100000h]
0x140045601  mov     [r14+rdi+38h], rsi
0x140045606  test    rcx, rcx
0x140045609  jz      loc_1400456D5
0x14004560f  mov     eax, [rdi+4]
0x140045612  lea     rbx, [rax+rax*8]
0x140045616  shl     rbx, 4
0x14004561a  inc     eax
0x14004561c  mov     [rdi+4], eax
0x14004561f  lea     rax, [rsi+100000h]
0x140045626  mov     [rbx+rdi+40h], rcx
0x14004562b  lea     rcx, [rbx+60h]
0x14004562f  mov     [rbx+rdi+38h], rax
0x140045634  add     rcx, rdi; Uuid
0x140045637  mov     dword ptr [rbx+rdi+30h], 1
0x14004563f  mov     byte ptr [rbx+rdi+4Ch], 1
0x140045644  movups  xmm0, xmmword ptr cs:PARTITION_MSFT_RESERVED_GUID.Data1
0x14004564b  movdqu  xmmword ptr [rbx+rdi+50h], xmm0
0x140045651  call    cs:__imp_ExUuidCreate
0x140045658  nop     dword ptr [rax+rax+00h]
0x14004565d  mov     esi, eax
0x14004565f  test    eax, eax
0x140045661  jns     short loc_1400456B4
0x140045663  xor     edx, edx; Tag
0x140045665  mov     rcx, rdi; P
0x140045668  call    cs:__imp_ExFreePoolWithTag
0x14004566f  nop     dword ptr [rax+rax+00h]
0x140045674  mov     rcx, cs:WPP_GLOBAL_Control
0x14004567b  lea     rax, WPP_GLOBAL_Control
0x140045682  cmp     rcx, rax
0x140045685  jz      short loc_1400456AD
0x140045687  mov     edx, [rcx+2Ch]
0x14004568a  test    dl, 10h
0x14004568d  jz      short loc_1400456AD
0x14004568f  cmp     byte ptr [rcx+29h], 2
0x140045693  jb      short loc_1400456AD
0x140045695  mov     rcx, [rcx+18h]
0x140045699  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x1400456a0  mov     edx, 4Bh ; 'K'
0x1400456a5  mov     r9d, esi
0x1400456a8  call    WPP_SF_d
0x1400456ad  mov     eax, esi
0x1400456af  jmp     loc_14004577D
0x1400456b4  lea     rcx, [rdi+78h]
0x1400456b8  mov     qword ptr [rbx+rdi+70h], 0
0x1400456c1  add     rcx, rbx; pszDest
0x1400456c4  lea     r8, aMicrosoftReser; "Microsoft reserved partition"
0x1400456cb  mov     edx, 48h ; 'H'; cbDest
0x1400456d0  call    RtlStringCbCopyW
0x1400456d5  mov     eax, [rdi+28h]
0x1400456d8  cmp     [rdi+4], eax
0x1400456db  jbe     short loc_14004571A
0x1400456dd  xor     edx, edx; Tag
0x1400456df  mov     rcx, rdi; P
0x1400456e2  call    cs:__imp_ExFreePoolWithTag
0x1400456e9  nop     dword ptr [rax+rax+00h]
0x1400456ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400456f5  lea     rax, WPP_GLOBAL_Control
0x1400456fc  mov     ebx, 0C0380010h
0x140045701  cmp     rcx, rax
0x140045704  jz      short loc_14004577B
0x140045706  mov     eax, [rcx+2Ch]
0x140045709  test    al, 10h
0x14004570b  jz      short loc_14004577B
0x14004570d  cmp     byte ptr [rcx+29h], 2
0x140045711  jb      short loc_14004577B
0x140045713  mov     edx, 4Ch ; 'L'
0x140045718  jmp     short loc_140045768
0x14004571a  mov     rcx, [rsp+68h+arg_0]
0x14004571f  mov     rdx, rdi; InputBuffer
0x140045722  mov     rcx, [rcx+10h]; this
0x140045726  call    ?SetDriveLayoutExSynchronous@VMX_DISK_DEVICE@@QEAAJPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; VMX_DISK_DEVICE::SetDriveLayoutExSynchronous(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14004572b  xor     edx, edx; Tag
0x14004572d  mov     rcx, rdi; P
0x140045730  mov     ebx, eax
0x140045732  call    cs:__imp_ExFreePoolWithTag
0x140045739  nop     dword ptr [rax+rax+00h]
0x14004573e  test    ebx, ebx
0x140045740  jns     short loc_14004577B
0x140045742  mov     rcx, cs:WPP_GLOBAL_Control
0x140045749  lea     rax, WPP_GLOBAL_Control
0x140045750  cmp     rcx, rax
0x140045753  jz      short loc_14004577B
0x140045755  mov     edx, [rcx+2Ch]
0x140045758  test    dl, 10h
0x14004575b  jz      short loc_14004577B
0x14004575d  cmp     byte ptr [rcx+29h], 2
0x140045761  jb      short loc_14004577B
0x140045763  mov     edx, 4Dh ; 'M'
0x140045768  mov     rcx, [rcx+18h]
0x14004576c  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140045773  mov     r9d, ebx
0x140045776  call    WPP_SF_d
  ... truncated ...
```
