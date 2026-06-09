# NvmeNamespaceFlushWorker

- ea: `0x1400452a0`
- end: `0x14004590b`
- name: `NvmeNamespaceFlushWorker`
- size: `1643`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400452a0`
- `0x140045920`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14014b400`
- `0x14014b800`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140045652`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140045652`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400458be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400458be`
- `ntoskrnl!IofCompleteRequest` at `0x1400454ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400454ae`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400458ce`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400458ce`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400458fa`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400458fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400454c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400454c4`

## pseudocode

```c
void __fastcall NvmeNamespaceFlushWorker(PVOID IoObject, char *Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v3; // rdi
  _DWORD *v5; // rax
  __int16 v6; // ax
  __int64 v7; // rax
  int v8; // eax
  char v9; // cl
  _BYTE *v10; // r9
  unsigned __int8 v11; // r10
  char v12; // bp
  unsigned __int64 v13; // rcx
  char v14; // si
  __int64 v15; // rdx
  char v16; // r11
  char v17; // r8
  _BYTE *v18; // rax
  char *v19; // r8
  unsigned int v20; // eax
  char v21; // al
  unsigned int v22; // r15d
  KIRQL v23; // al
  _QWORD *v24; // rcx
  char *v25; // rdx
  KIRQL v26; // r9
  __int64 v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD **v31; // rdx
  _QWORD *v32; // rax
  _QWORD *v33; // r8
  _QWORD *v34; // r8
  __int64 v35; // r8
  int v36; // ecx
  __int64 v37; // r14
  char v38; // r12
  char *v39; // r11
  __int64 v40; // rdx
  __int64 *v41; // rdx
  int *v42; // rax
  int v43; // ecx
  bool v44; // zf
  __int64 v45; // rdi
  unsigned __int64 v46; // rsi
  _QWORD *v47; // rax
  _QWORD *v48; // r8
  _QWORD *v49; // r8
  char v50; // di
  __int64 v51; // rdx
  _QWORD **v52; // rdx
  __int128 v53; // [rsp+60h] [rbp-48h] BYREF

  v3 = *((_QWORD *)Context + 68);
  memset_0(*(void **)v3, 0, 0x10B0u);
  v5 = *(_DWORD **)v3;
  v5[1025] = *((_DWORD *)Context + 14);
  *((_BYTE *)v5 + 4096) = 0;
  *(_DWORD *)(*(_QWORD *)v3 + 4256LL) &= ~1u;
  *(_DWORD *)(*(_QWORD *)v3 + 4256LL) |= 0x20u;
  *(_DWORD *)(*(_QWORD *)v3 + 4256LL) &= ~2u;
  *(_QWORD *)(*(_QWORD *)v3 + 4184LL) = *((_QWORD *)Context + 71);
  *(_QWORD *)(*(_QWORD *)v3 + 4192LL) = NvmeNamespaceFlushCommandCompletion;
  *(_QWORD *)(*(_QWORD *)v3 + 4200LL) = v3;
  *(_QWORD *)(*(_QWORD *)v3 + 4216LL) = Context;
  *(_QWORD *)(*(_QWORD *)v3 + 4240LL) = v3;
  *(_DWORD *)(v3 + 64) |= 1u;
  v6 = *(_WORD *)(v3 + 68);
  if ( (unsigned __int16)v6 <= 0xAu )
    v6 = 10;
  *(_WORD *)(v3 + 68) = v6;
  v7 = *(_QWORD *)(*((_QWORD *)Context + 2) + 1056LL);
  if ( v7 && (*(_DWORD *)(v7 + 24) & 0x20000000) != 0 )
    *(_DWORD *)(*(_QWORD *)v3 + 4256LL) |= 0x100u;
  v8 = NvmeControllerProcessCommand(*((PVOID *)Context + 2));
  if ( v8 >= 0 )
    return;
  *(_DWORD *)(v3 + 64) &= ~1u;
  v44 = StorEtwLoggingEnabled == 0;
  *(_DWORD *)(*((_QWORD *)Context + 71) + 48LL) = v8;
  *(_QWORD *)(*((_QWORD *)Context + 71) + 56LL) = 0;
  v45 = *((_QWORD *)Context + 71);
  *(_BYTE *)(v45 + 141) = -84;
  *(_DWORD *)(v45 + 48) = v8;
  if ( v44 )
    goto LABEL_23;
  v53 = 0;
  IoGetActivityIdIrp(v45, &v53);
  v40 = *(_QWORD *)(v45 + 184);
  if ( *(_BYTE *)v40 == 14 )
  {
    if ( (byte_140177432 & 8) == 0 )
      goto LABEL_23;
    v41 = EventNonReadWriteRequestComplete;
    goto LABEL_65;
  }
  if ( *(_BYTE *)v40 != 15 )
  {
    if ( *(_BYTE *)v40 != 27 )
      goto LABEL_23;
    if ( *(_BYTE *)(v40 + 1) == 7 && !*(_DWORD *)(v40 + 8) )
    {
      if ( (byte_140177432 & 0x40) != 0 )
      {
        v42 = *(int **)(v45 + 56);
        if ( v42 )
          v43 = *v42;
        else
          v43 = 0;
        McTemplateK0pqd_EtwWriteTransfer(v43, v40, (unsigned int)&v53, v45, v43, *(_DWORD *)(v45 + 48));
      }
      goto LABEL_23;
    }
    if ( (byte_140177432 & 0x20) == 0 )
      goto LABEL_23;
    v41 = EventPnpRequestComplete;
LABEL_65:
    McTemplateK0pd_EtwWriteTransfer(v13, v41, &v53, v45, *(_DWORD *)(v45 + 48));
    goto LABEL_23;
  }
  if ( byte_140177431 >= 0 )
    goto LABEL_23;
  v15 = *(_QWORD *)(v40 + 8);
  if ( *(_BYTE *)(v15 + 2) != 40 )
  {
    v9 = *(_BYTE *)(v15 + 72);
    v10 = *(_BYTE **)(v15 + 32);
    v11 = *(_BYTE *)(v15 + 11);
    v12 = *(_BYTE *)(v15 + 4);
    if ( !*(_BYTE *)(v15 + 2) )
      goto LABEL_9;
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v15 + 20) )
    goto LABEL_23;
  v22 = *(_DWORD *)(v15 + 56);
  if ( !v22 )
    goto LABEL_23;
  v11 = 0;
  v39 = 0;
  v12 = 0;
  v10 = 0;
  v37 = 0;
  v38 = 0;
  while ( 1 )
  {
    v13 = *(unsigned int *)(v15 + 4 * v37 + 120);
    if ( (unsigned int)v13 >= 0x80 )
    {
      v46 = *(unsigned int *)(v15 + 16);
      if ( (unsigned int)v13 < (unsigned int)v46 )
        break;
    }
LABEL_41:
    v37 = (unsigned int)(v37 + 1);
    if ( (unsigned int)v37 >= v22 )
      goto LABEL_42;
  }
  v35 = *(unsigned int *)(v15 + 4 * v37 + 120);
  v36 = *(_DWORD *)(v13 + v15) - 64;
  if ( v36 )
  {
    LODWORD(v13) = v36 - 1;
    if ( (_DWORD)v13 )
    {
      if ( (_DWORD)v13 == 1 )
      {
        LODWORD(v13) = v35 + 40;
        if ( v35 + 40 <= v46 )
        {
          if ( *(_DWORD *)(v35 + v15 + 12) )
            v39 = (char *)(v35 + v15 + 32);
          v10 = *(_BYTE **)(v35 + v15 + 24);
          goto LABEL_53;
        }
      }
    }
    else
    {
      LODWORD(v13) = v35 + 56;
      if ( v35 + 56 <= v46 )
      {
        v38 = 1;
        if ( *(_BYTE *)(v35 + v15 + 10) )
          v39 = (char *)(v35 + v15 + 24);
        v12 = *(_BYTE *)(v35 + v15 + 8);
        v10 = *(_BYTE **)(v35 + v15 + 16);
        v11 = *(_BYTE *)(v35 + v15 + 9);
      }
    }
    goto LABEL_40;
  }
  LODWORD(v13) = v35 + 40;
  if ( v35 + 40 > v46 )
  {
LABEL_40:
    if ( v38 )
      goto LABEL_42;
    goto LABEL_41;
  }
  if ( *(_BYTE *)(v35 + v15 + 10) )
    v39 = (char *)(v35 + v15 + 24);
  v10 = *(_BYTE **)(v35 + v15 + 16);
LABEL_53:
  v11 = *(_BYTE *)(v35 + v15 + 9);
  v12 = *(_BYTE *)(v35 + v15 + 8);
LABEL_42:
  if ( !v39 )
    goto LABEL_23;
  v9 = *v39;
LABEL_9:
  LOBYTE(v13) = v9 - 8;
  if ( (v13 & 0x5D) != 0 )
    goto LABEL_23;
  v14 = *(_BYTE *)(v15 + 3);
  if ( v14 == 1 || !v10 || !v11 )
    goto LABEL_78;
  LOBYTE(v15) = 0;
  v16 = 0;
  v17 = 0;
  v13 = (unsigned __int64)&v10[v11];
  v18 = v10 + 8;
  if ( (unsigned __int8)((*v10 & 0x7F) - 114) <= 1u )
  {
    if ( (unsigned __int64)v18 <= v13 )
    {
      v16 = v10[2];
      LOBYTE(v15) = v10[1] & 0xF;
      v17 = v10[3];
      goto LABEL_21;
    }
    goto LABEL_91;
  }
  if ( (unsigned __int64)v18 > v13 )
  {
LABEL_91:
    v21 = 0;
    goto LABEL_92;
  }
  v19 = v10 + 13;
  LOBYTE(v15) = v10[2] & 0xF;
  v20 = v11;
  if ( (unsigned int)(unsigned __int8)v10[7] + 8 <= v11 )
    v20 = (unsigned __int8)v10[7] + 8;
  v13 = (unsigned __int64)&v10[v20];
  if ( (unsigned __int64)v19 <= v13 )
    v16 = v10[12];
  if ( (unsigned __int64)(v10 + 14) > v13 )
    v17 = 0;
  else
    v17 = *v19;
LABEL_21:
  v21 = 1;
LABEL_92:
  if ( !v21 )
  {
LABEL_78:
    LOBYTE(v15) = 0;
    v16 = 0;
    v17 = 0;
  }
  McTemplateK0pduuuuup_EtwWriteTransfer(
    v13,
    v15,
    (unsigned int)&v53,
    v45,
    *(_DWORD *)(v45 + 48),
    v14,
    v12,
    v15,
    v16,
    v17,
    v45);
LABEL_23:
  IofCompleteRequest((PIRP)v45, 1);
  v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 70);
  v24 = Context + 576;
  *((_QWORD *)Context + 71) = 0;
  v25 = (char *)*((_QWORD *)Context + 72);
  v26 = v23;
  if ( v25 == Context + 576 )
  {
    v51 = *((_QWORD *)Context + 74);
    if ( v51 )
    {
      *((_QWORD *)Context + 71) = v51;
      v52 = (_QWORD **)(Context + 600);
      *((_QWORD *)Context + 74) = 0;
      while ( 1 )
      {
        v47 = *v52;
        if ( *v52 == v52 )
          goto LABEL_96;
        if ( (_QWORD **)v47[1] != v52 )
          goto LABEL_25;
        v48 = (_QWORD *)*v47;
        if ( *(_QWORD **)(*v47 + 8LL) != v47 )
          goto LABEL_25;
        *v52 = v48;
        v48[1] = v52;
        v49 = (_QWORD *)*((_QWORD *)Context + 73);
        if ( (_QWORD *)*v49 != v24 )
          goto LABEL_25;
        *v47 = v24;
        v47[1] = v49;
        *v49 = v47;
        *((_QWORD *)Context + 73) = v47;
      }
    }
    v50 = 0;
    if ( *((char **)Context + 75) != Context + 600 )
      *((_DWORD *)Context + 154) |= 1u;
  }
  else
  {
    if ( *((_QWORD **)v25 + 1) != v24 )
      goto LABEL_25;
    v27 = *(_QWORD *)v25;
    if ( *(char **)(*(_QWORD *)v25 + 8LL) != v25 )
      goto LABEL_25;
    *v24 = v27;
    *(_QWORD *)(v27 + 8) = v24;
    *((_QWORD *)Context + 71) = v25 - 168;
    *((_QWORD *)v25 + 1) = v25;
    *(_QWORD *)v25 = v25;
    v28 = *((_QWORD *)Context + 74);
    if ( v28 )
    {
      v29 = (_QWORD *)*((_QWORD *)Context + 73);
      if ( (_QWORD *)*v29 == v24 )
      {
        v30 = (_QWORD *)(v28 + 168);
        *v30 = v24;
        v30[1] = v29;
        *v29 = v30;
        *((_QWORD *)Context + 73) = v30;
        goto LABEL_30;
      }
LABEL_25:
      __fastfail(3u);
    }
LABEL_30:
    v31 = (_QWORD **)(Context + 600);
    while ( 1 )
    {
      v32 = *v31;
      if ( *v31 == v31 )
        break;
      if ( (_QWORD **)v32[1] != v31 )
        goto LABEL_25;
      v33 = (_QWORD *)*v32;
      if ( *(_QWORD **)(*v32 + 8LL) != v32 )
        goto LABEL_25;
      *v31 = v33;
      v33[1] = v31;
      v34 = (_QWORD *)*((_QWORD *)Context + 73);
      if ( (_QWORD *)*v34 != v24 )
        goto LABEL_25;
      *v32 = v24;
      v32[1] = v34;
      *v34 = v32;
      *((_QWORD *)Context + 73) = v32;
    }
LABEL_96:
    v50 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 70, v26);
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 15));
  if ( v50 )
    IoQueueWorkItemEx(*((PIO_WORKITEM *)Context + 69), NvmeNamespaceFlushWorker, DelayedWorkQueue, Context);
}

```

## disassembly

```asm
0x1400452a0  mov     [rsp+arg_0], rbx
0x1400452a5  mov     [rsp+arg_10], rbp
0x1400452aa  push    rsi
0x1400452ab  push    rdi
0x1400452ac  push    r12
0x1400452ae  push    r14
0x1400452b0  push    r15
0x1400452b2  sub     rsp, 80h
0x1400452b9  mov     rax, cs:__security_cookie
0x1400452c0  xor     rax, rsp
0x1400452c3  mov     [rsp+0A8h+var_38], rax
0x1400452c8  mov     rdi, [rdx+220h]
0x1400452cf  mov     rbx, rdx
0x1400452d2  xor     edx, edx; Val
0x1400452d4  mov     r8d, 10B0h; Size
0x1400452da  mov     rcx, [rdi]; void *
0x1400452dd  call    memset_0
0x1400452e2  mov     ecx, [rbx+38h]
0x1400452e5  mov     esi, 0FFFFFFFEh
0x1400452ea  mov     rax, [rdi]
0x1400452ed  mov     [rax+1004h], ecx
0x1400452f3  mov     byte ptr [rax+1000h], 0
0x1400452fa  mov     rax, [rdi]
0x1400452fd  mov     ecx, [rax+10A0h]
0x140045303  mov     rax, [rdi]
0x140045306  and     ecx, esi
0x140045308  mov     [rax+10A0h], ecx
0x14004530e  mov     rax, [rdi]
0x140045311  mov     ecx, [rax+10A0h]
0x140045317  mov     rax, [rdi]
0x14004531a  or      ecx, 20h
0x14004531d  mov     [rax+10A0h], ecx
0x140045323  mov     rax, [rdi]
0x140045326  mov     ecx, [rax+10A0h]
0x14004532c  mov     rax, [rdi]
0x14004532f  and     ecx, 0FFFFFFFDh
0x140045332  mov     [rax+10A0h], ecx
0x140045338  mov     rax, [rbx+238h]
0x14004533f  mov     rcx, [rdi]
0x140045342  mov     [rcx+1058h], rax
0x140045349  lea     rcx, NvmeNamespaceFlushCommandCompletion
0x140045350  mov     rax, [rdi]
0x140045353  mov     [rax+1060h], rcx
0x14004535a  mov     ecx, 0Ah
0x14004535f  mov     rax, [rdi]
0x140045362  mov     [rax+1068h], rdi
0x140045369  mov     rax, [rdi]
0x14004536c  mov     [rax+1078h], rbx
0x140045373  mov     rax, [rdi]
0x140045376  mov     [rax+1090h], rdi
0x14004537d  or      dword ptr [rdi+40h], 1
0x140045381  movzx   eax, word ptr [rdi+44h]
0x140045385  cmp     ax, cx
0x140045388  jbe     loc_14004581E
0x14004538e  mov     [rdi+44h], ax
0x140045392  mov     rax, [rbx+10h]
0x140045396  mov     rax, [rax+420h]
0x14004539d  test    rax, rax
0x1400453a0  jz      short loc_1400453AF
0x1400453a2  test    dword ptr [rax+18h], 20000000h
0x1400453a9  jnz     loc_140045825
0x1400453af  mov     rcx, [rbx+10h]; SystemArgument2
0x1400453b3  mov     rdx, rdi
0x1400453b6  call    NvmeControllerProcessCommand
0x1400453bb  test    eax, eax
0x1400453bd  js      loc_140045717
0x1400453c3  mov     rcx, [rsp+0A8h+var_38]
0x1400453c8  xor     rcx, rsp; StackCookie
0x1400453cb  call    __security_check_cookie
0x1400453d0  lea     r11, [rsp+0A8h+var_28]
0x1400453d8  mov     rbx, [r11+30h]
0x1400453dc  mov     rbp, [r11+40h]
0x1400453e0  mov     rsp, r11
0x1400453e3  pop     r15
0x1400453e5  pop     r14
0x1400453e7  pop     r12
0x1400453e9  pop     rdi
0x1400453ea  pop     rsi
0x1400453eb  retn
0x1400453ed  mov     cl, [rdx+48h]
0x1400453f0  mov     r9, [rdx+20h]
0x1400453f4  mov     r10b, [rdx+0Bh]
0x1400453f8  mov     bpl, [rdx+4]
0x1400453fc  test    eax, eax
0x1400453fe  jnz     loc_1400454A9
0x140045404  sub     cl, 8
0x140045407  test    cl, 5Dh
0x14004540a  jnz     loc_1400454A9
0x140045410  mov     sil, [rdx+3]
0x140045414  cmp     sil, 1
0x140045418  jz      loc_140045777
0x14004541e  test    r9, r9
0x140045421  jz      loc_140045777
0x140045427  test    r10b, r10b
0x14004542a  jz      loc_140045777
0x140045430  mov     al, [r9]
0x140045433  xor     dl, dl
0x140045435  and     al, 7Fh
0x140045437  movzx   ecx, r10b
0x14004543b  sub     al, 72h ; 'r'
0x14004543d  xor     r11b, r11b
0x140045440  xor     r8b, r8b
0x140045443  add     rcx, r9
0x140045446  cmp     al, 1
0x140045448  lea     rax, [r9+8]
0x14004544c  jbe     loc_14004585F
0x140045452  cmp     rax, rcx
0x140045455  ja      loc_140045878
0x14004545b  movzx   ecx, byte ptr [r9+7]
0x140045460  lea     r8, [r9+0Dh]
0x140045464  mov     dl, [r9+2]
0x140045468  add     ecx, 8
0x14004546b  and     dl, 0Fh
0x14004546e  movzx   eax, r10b
0x140045472  cmp     ecx, eax
0x140045474  cmovbe  eax, ecx
0x140045477  mov     ecx, eax
0x140045479  add     rcx, r9
0x14004547c  cmp     r8, rcx
0x14004547f  ja      short loc_140045485
0x140045481  mov     r11b, [r9+0Ch]
0x140045485  lea     rax, [r9+0Eh]
0x140045489  cmp     rax, rcx
0x14004548c  ja      loc_140045857
0x140045492  mov     r8b, [r8]
0x140045495  mov     al, 1
0x140045497  jmp     loc_14004587A
0x14004549c  mov     r15d, [rdx+38h]
0x1400454a0  test    r15d, r15d
0x1400454a3  jnz     loc_140045840
0x1400454a9  mov     dl, 1; PriorityBoost
0x1400454ab  mov     rcx, rdi; Irp
0x1400454ae  call    cs:__imp_IofCompleteRequest
0x1400454b5  nop     dword ptr [rax+rax+00h]
0x1400454ba  lea     rsi, [rbx+230h]
0x1400454c1  mov     rcx, rsi; SpinLock
0x1400454c4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400454cb  nop     dword ptr [rax+rax+00h]
0x1400454d0  lea     rcx, [rbx+240h]
0x1400454d7  mov     qword ptr [rbx+238h], 0
0x1400454e2  mov     rdx, [rcx]
0x1400454e5  mov     r9b, al
0x1400454e8  cmp     rdx, rcx
0x1400454eb  jz      loc_140045887
0x1400454f1  cmp     [rdx+8], rcx
0x1400454f5  jz      short loc_1400454FE
0x1400454f7  mov     ecx, 3
0x1400454fc  int     29h; Win8: RtlFailFast(ecx)
0x1400454fe  mov     rax, [rdx]
0x140045501  cmp     [rax+8], rdx
0x140045505  jnz     short loc_1400454F7
0x140045507  mov     [rcx], rax
0x14004550a  mov     [rax+8], rcx
0x14004550e  lea     rax, [rdx-0A8h]
0x140045515  mov     [rbx+238h], rax
0x14004551c  mov     [rdx+8], rdx
0x140045520  mov     [rdx], rdx
0x140045523  mov     rax, [rbx+250h]
0x14004552a  test    rax, rax
0x14004552d  jz      short loc_14004554C
0x14004552f  mov     rdx, [rcx+8]
0x140045533  cmp     [rdx], rcx
0x140045536  jnz     short loc_1400454F7
0x140045538  add     rax, 0A8h
0x14004553e  mov     [rax], rcx
0x140045541  mov     [rax+8], rdx
0x140045545  mov     [rdx], rax
0x140045548  mov     [rcx+8], rax
0x14004554c  lea     rdx, [rbx+258h]
0x140045553  mov     rax, [rdx]
0x140045556  cmp     rax, rdx
0x140045559  jz      loc_1400458B5
0x14004555f  cmp     [rax+8], rdx
0x140045563  jnz     short loc_1400454F7
0x140045565  mov     r8, [rax]
0x140045568  cmp     [r8+8], rax
0x14004556c  jnz     short loc_1400454F7
0x14004556e  mov     [rdx], r8
0x140045571  mov     [r8+8], rdx
0x140045575  mov     r8, [rbx+248h]
0x14004557c  cmp     [r8], rcx
0x14004557f  jnz     loc_1400454F7
0x140045585  mov     [rax], rcx
0x140045588  mov     [rax+8], r8
0x14004558c  mov     [r8], rax
0x14004558f  mov     [rcx+8], rax
0x140045593  jmp     short loc_140045553
0x140045595  mov     r8, rcx
0x140045598  mov     ecx, [rcx+rdx]
0x14004559b  sub     ecx, 40h ; '@'
0x14004559e  jz      short loc_140045601
0x1400455a0  sub     ecx, 1
0x1400455a3  jz      short loc_1400455D5
0x1400455a5  cmp     ecx, 1
0x1400455a8  jnz     short loc_1400455B3
0x1400455aa  lea     rcx, [r8+28h]
0x1400455ae  cmp     rcx, rsi
0x1400455b1  jbe     short loc_140045631
0x1400455b3  test    r12b, r12b
0x1400455b6  jnz     short loc_1400455C4
0x1400455b8  inc     r14d
0x1400455bb  cmp     r14d, r15d
0x1400455be  jb      loc_140045756
0x1400455c4  test    r11, r11
0x1400455c7  jz      loc_1400454A9
0x1400455cd  mov     cl, [r11]
0x1400455d0  jmp     loc_140045404
0x1400455d5  lea     rcx, [r8+38h]
0x1400455d9  cmp     rcx, rsi
0x1400455dc  ja      short loc_1400455B3
0x1400455de  cmp     byte ptr [r8+rdx+0Ah], 0
0x1400455e4  mov     r12b, 1
0x1400455e7  jbe     short loc_1400455F0
0x1400455e9  lea     r11, [rdx+18h]
0x1400455ed  add     r11, r8
0x1400455f0  mov     bpl, [r8+rdx+8]
0x1400455f5  mov     r9, [r8+rdx+10h]
0x1400455fa  mov     r10b, [r8+rdx+9]
0x1400455ff  jmp     short loc_1400455B3
0x140045601  lea     rcx, [r8+28h]
0x140045605  cmp     rcx, rsi
0x140045608  ja      short loc_1400455B3
0x14004560a  cmp     byte ptr [r8+rdx+0Ah], 0
0x140045610  jbe     short loc_140045619
0x140045612  lea     r11, [rdx+18h]
0x140045616  add     r11, r8
0x140045619  mov     r9, [r8+rdx+10h]
0x14004561e  jmp     short loc_140045625
0x140045620  mov     r9, [r8+rdx+18h]
0x140045625  mov     r10b, [r8+rdx+9]
0x14004562a  mov     bpl, [r8+rdx+8]
0x14004562f  jmp     short loc_1400455C4
0x140045631  cmp     dword ptr [r8+rdx+0Ch], 0
0x140045637  jbe     short loc_140045620
0x140045639  lea     r11, [rdx+20h]
0x14004563d  add     r11, r8
0x140045640  jmp     short loc_140045620
0x140045642  xorps   xmm0, xmm0
0x140045645  lea     rdx, [rsp+0A8h+var_48]
0x14004564a  mov     rcx, rdi
0x14004564d  movups  [rsp+0A8h+var_48], xmm0
0x140045652  call    cs:__imp_IoGetActivityIdIrp
0x140045659  nop     dword ptr [rax+rax+00h]
0x14004565e  mov     rdx, [rdi+0B8h]
0x140045665  movzx   eax, byte ptr [rdx]
0x140045668  sub     eax, 0Eh
0x14004566b  jz      short loc_14004569D
0x14004566d  sub     eax, 1
0x140045670  jz      short loc_1400456EB
0x140045672  cmp     eax, 0Ch
0x140045675  jnz     loc_1400454A9
0x14004567b  cmp     byte ptr [rdx+1], 7
0x14004567f  jnz     short loc_140045687
0x140045681  cmp     dword ptr [rdx+8], 0
0x140045685  jz      short loc_1400456CA
0x140045687  test    cs:byte_140177432, 20h
0x14004568e  jz      loc_1400454A9
0x140045694  lea     rdx, EventPnpRequestComplete
0x14004569b  jmp     short loc_1400456B1
0x14004569d  test    cs:byte_140177432, 8
0x1400456a4  jz      loc_1400454A9
0x1400456aa  lea     rdx, EventNonReadWriteRequestComplete
0x1400456b1  mov     eax, [rdi+30h]
0x1400456b4  lea     r8, [rsp+0A8h+var_48]
0x1400456b9  mov     r9, rdi
0x1400456bc  mov     [rsp+0A8h+var_88], eax
0x1400456c0  call    McTemplateK0pd_EtwWriteTransfer
0x1400456c5  jmp     loc_1400454A9
0x1400456ca  test    cs:byte_140177432, 40h
0x1400456d1  jz      loc_1400454A9
0x1400456d7  mov     rax, [rdi+38h]
0x1400456db  test    rax, rax
0x1400456de  jz      loc_140152CBE
0x1400456e4  mov     ecx, [rax]
0x1400456e6  jmp     loc_140152CC0
0x1400456eb  cmp     cs:byte_140177431, 0
0x1400456f2  jge     loc_1400454A9
0x1400456f8  mov     rdx, [rdx+8]
0x1400456fc  movzx   eax, byte ptr [rdx+2]
0x140045700  cmp     al, 28h ; '('
0x140045702  jnz     loc_1400453ED
0x140045708  cmp     dword ptr [rdx+14h], 0
0x14004570c  jnz     loc_1400454A9
0x140045712  jmp     loc_14004549C
0x140045717  and     [rdi+40h], esi
0x14004571a  cmp     cs:StorEtwLoggingEnabled, 0
0x140045721  mov     rcx, [rbx+238h]
0x140045728  mov     [rcx+30h], eax
0x14004572b  mov     rcx, [rbx+238h]
0x140045732  mov     qword ptr [rcx+38h], 0
0x14004573a  mov     rdi, [rbx+238h]
0x140045741  mov     byte ptr [rdi+8Dh], 0ACh
0x140045748  mov     [rdi+30h], eax
0x14004574b  jz      loc_1400454A9
0x140045751  jmp     loc_140045642
0x140045756  mov     ecx, [rdx+r14*4+78h]
0x14004575b  cmp     ecx, 80h
0x140045761  jb      loc_1400455B8
0x140045767  mov     esi, [rdx+10h]
0x14004576a  cmp     ecx, esi
  ... truncated ...
```
