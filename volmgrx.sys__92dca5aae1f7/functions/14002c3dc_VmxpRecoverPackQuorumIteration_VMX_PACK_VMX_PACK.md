# VmxpRecoverPackQuorumIteration(VMX_PACK *,VMX_PACK * *)

- ea: `0x14002c3dc`
- end: `0x14002caf2`
- name: `?VmxpRecoverPackQuorumIteration@@YAJPEAVVMX_PACK@@PEAPEAV1@@Z`
- size: `1814`
- prototype: `__int64 __fastcall(struct VMX_PACK *, struct VMX_PACK **)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003acf0`

## callees

- `0x140005f80`
- `0x140008d00`
- `0x140008dc8`
- `0x140008eec`
- `0x140009670`
- `0x140009718`
- `0x1400097c0`
- `0x1400099d8`
- `0x14001be80`
- `0x14002b0c4`
- `0x14002c3dc`
- `0x14002d3ec`
- `0x14003d81c`
- `0x140041d3c`
- `0x14004e3ac`
- `0x14004e950`
- `0x1400531c8`
- `0x140054b2c`
- `0x140054b48`
- `0x140054c24`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002c558`
- `ntoskrnl!ExAllocatePool2` at `0x14002c558`
- `ntoskrnl!ExUuidCreate` at `0x14002c499`
- `ntoskrnl!ExUuidCreate` at `0x14002c499`

## pseudocode

```c
__int64 __fastcall VmxpRecoverPackQuorumIteration(struct VMX_PACK *a1, struct VMX_PACK **a2)
{
  __int64 v3; // rcx
  _QWORD *v4; // r15
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  const char *v8; // rbp
  unsigned int v9; // ebx
  VMX_NOTIFICATION_QUEUE *v10; // r10
  __int64 v11; // rdx
  __int64 *v13; // r12
  unsigned int v14; // r10d
  __int64 *i; // rcx
  __int64 v16; // rdx
  __int64 Pool2; // rax
  VMX_NOTIFICATION_QUEUE *v18; // r10
  __int64 v19; // rdx
  unsigned int v20; // edx
  __int64 *v21; // r14
  __int64 v22; // r13
  __int64 v23; // rbx
  __int64 v24; // rbp
  unsigned int v25; // r15d
  __int64 v26; // rax
  __int64 v27; // rcx
  __int128 v28; // xmm1
  __int64 v29; // r14
  VMX_PACK *v30; // rax
  VMX_PACK *v31; // rbx
  unsigned int v32; // edx
  int v33; // ebp
  VMX_NOTIFICATION_QUEUE *v34; // r10
  __int64 v35; // rdx
  struct _GUID *v36; // rax
  unsigned int v37; // edx
  char *v38; // rax
  VMX_GLOBAL_DATA **v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  _QWORD *v43; // rax
  void **v44; // rcx
  unsigned int v45; // edx
  struct VMX_PACK *v46; // rax
  struct VMX_PACK **v47; // rcx
  unsigned int v48; // edx
  unsigned int v49; // edx
  _QWORD *v50; // rcx
  void **v51; // rax
  unsigned int v52; // [rsp+70h] [rbp+8h]
  struct _GUID *v54; // [rsp+80h] [rbp+18h]
  _QWORD *v55; // [rsp+88h] [rbp+20h]

  *a2 = a1;
  if ( VMX_PACK::QuorumInSync(a1) )
    return 0;
  v4 = *(_QWORD **)(v3 + 16);
  v55 = v4;
  v5 = v4[1];
  v6 = VMX_ALLOCATED_OBJECT::operator new(184, 258, 2018798934);
  v7 = v6;
  if ( !v6 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v19 = 51;
    goto LABEL_104;
  }
  v8 = (const char *)(v5 + 24);
  *(_OWORD *)v6 = 0;
  *(_OWORD *)(v6 + 16) = 0;
  *(_OWORD *)(v6 + 32) = 0;
  *(_QWORD *)(v6 + 48) = 0;
  *(_WORD *)(v6 + 48) = 1;
  *(_DWORD *)(v6 + 160) = 0;
  *(_QWORD *)(v6 + 168) = 0;
  *(_WORD *)(v6 + 176) = 0;
  *(_QWORD *)(v6 + 56) = a1;
  *(_OWORD *)(v6 + 64) = *(_OWORD *)(v5 + 8);
  RtlStringCbCopyA((NTSTRSAFE_PSTR)(v6 + 80), 0x20u, (NTSTRSAFE_PCSTR)(v5 + 24));
  v54 = (struct _GUID *)(v7 + 112);
  v9 = ExUuidCreate((UUID *)(v7 + 112));
  if ( (v9 & 0x80000000) != 0 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
    {
      v11 = 52;
      goto LABEL_8;
    }
    return v9;
  }
  RtlStringCbCopyA((NTSTRSAFE_PSTR)(v7 + 128), 0x20u, v8);
  v13 = v4 + 2;
  v14 = 0;
  for ( i = (__int64 *)v4[2]; i != v13; i = (__int64 *)*i )
  {
    if ( *((_WORD *)i + 16) == 4 )
    {
      v16 = *(_QWORD *)(i[5] + 128);
      if ( v16 )
      {
        if ( *(_BYTE *)(v16 + 125) )
          ++v14;
      }
    }
  }
  *(_DWORD *)(v7 + 160) = v14;
  Pool2 = ExAllocatePool2(258, 48LL * v14, 538996054);
  *(_QWORD *)(v7 + 168) = Pool2;
  if ( !Pool2 )
  {
    VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v19 = 53;
LABEL_104:
    WPP_SF_d(*((_QWORD *)v18 + 3), v19, WPP_2f8af752156e3401cd435973c831895d_Traceguids, 3221225626LL);
    return 3221225626LL;
  }
  v20 = 0;
  v21 = (__int64 *)*v13;
  v52 = 0;
  while ( 1 )
  {
    if ( v21 == v13 )
    {
      if ( VMX_PACK::QuorumInSync(a1) )
      {
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
        return 0;
      }
      v29 = 64;
      v30 = (VMX_PACK *)VMX_ALLOCATED_OBJECT::operator new(64, 258, 1632660822);
      v31 = v30;
      if ( !v30 )
      {
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return 3221225626LL;
        }
        v19 = 56;
        goto LABEL_104;
      }
      memset(v30, 0, 0x40u);
      v33 = VMX_PACK::CopyPack(v31, a1);
      if ( v33 < 0 )
      {
        VMX_PACK::`scalar deleting destructor'(v31, v32);
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v33;
        }
        v35 = 57;
LABEL_52:
        WPP_SF_d(*((_QWORD *)v34 + 3), v35, WPP_2f8af752156e3401cd435973c831895d_Traceguids, (unsigned int)v33);
        return (unsigned int)v33;
      }
      v36 = (struct _GUID *)*((_QWORD *)v31 + 3);
      if ( v36 )
        *v36 = *v54;
      v33 = VmxpWritePendingPrimaryPackId(v54);
      if ( v33 < 0 )
      {
        VMX_PACK::`scalar deleting destructor'(v31, v37);
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
        {
          return (unsigned int)v33;
        }
        v35 = 58;
        goto LABEL_52;
      }
      v38 = (char *)Global + 200;
      v39 = (VMX_GLOBAL_DATA **)*((_QWORD *)Global + 26);
      if ( *v39 != (VMX_GLOBAL_DATA *)((char *)Global + 200) )
        goto LABEL_95;
      *(_QWORD *)v31 = v38;
      *((_QWORD *)v31 + 1) = v39;
      *v39 = v31;
      *((_QWORD *)v38 + 1) = v31;
      v40 = *((_QWORD *)v31 + 2);
      *((_QWORD *)v31 + 6) = v7;
      v41 = *(_QWORD *)(v40 + 8);
      if ( *(_WORD *)(v41 + 72) != 3 )
        v29 = 56;
      *(_QWORD *)v7 = *(_QWORD *)(v29 + v41) + 1LL;
      v42 = *((_QWORD *)v31 + 6);
      *(_OWORD *)(v42 + 8) = *(_OWORD *)(v41 + 144);
      *(_OWORD *)(v42 + 20) = *(_OWORD *)(v41 + 156);
      v33 = VMX_PACK::RecoverPackTargetTransaction(v31);
      if ( v33 < 0 )
      {
        VMX_CONFIG::AbortRecords(*((VMX_CONFIG **)v31 + 2));
        *((_QWORD *)v31 + 6) = 0;
      }
      else
      {
        v33 = VMX_PACK::CommitChangeIdentityTransaction(v31);
        if ( v33 >= 0 )
        {
          if ( (int)VmxpWritePrimaryPackId((struct _GUID *)((char *)Global + 232)) >= 0 )
            VmxpDeletePendingPrimaryPackId();
          if ( !*((_DWORD *)v31 + 9) )
          {
            v43 = *(_QWORD **)v31;
            if ( *(VMX_PACK **)(*(_QWORD *)v31 + 8LL) != v31 )
              goto LABEL_95;
            v44 = (void **)*((_QWORD *)v31 + 1);
            if ( *v44 != v31 )
              goto LABEL_95;
            *v44 = v43;
            v43[1] = v44;
            VmxpSendPackDepartNotifications(v31);
            VMX_PACK::`scalar deleting destructor'(v31, v45);
            v31 = 0;
          }
          VMX_PACK::RecoverPackSourceCleanup(a1, (struct VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
          if ( *((_BYTE *)a1 + 56) )
            VMX_PACK::Offline(a1);
          if ( *((_DWORD *)a1 + 9) )
          {
LABEL_78:
            VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
            *a2 = v31;
            if ( v31 )
            {
              if ( VMX_PACK::QuorumInSync(v31) )
                return 0;
              v10 = WPP_GLOBAL_Control;
              v9 = -1070071755;
              if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
              {
                return v9;
              }
              v11 = 61;
            }
            else
            {
              v10 = WPP_GLOBAL_Control;
              v9 = -1070071767;
              if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
              {
                return v9;
              }
              v11 = 60;
            }
LABEL_8:
            WPP_SF_d(*((_QWORD *)v10 + 3), v11, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v9);
            return v9;
          }
          v46 = *(struct VMX_PACK **)a1;
          if ( *(struct VMX_PACK **)(*(_QWORD *)a1 + 8LL) == a1 )
          {
            v47 = (struct VMX_PACK **)*((_QWORD *)a1 + 1);
            if ( *v47 == a1 )
            {
              *v47 = v46;
              *((_QWORD *)v46 + 1) = v47;
              VmxpSendPackDepartNotifications(a1);
              VMX_PACK::`scalar deleting destructor'(a1, v48);
              goto LABEL_78;
            }
          }
LABEL_95:
          __fastfail(3u);
        }
      }
      VMX_PACK::UpdateCounters(a1);
      VmxpDeletePendingPrimaryPackId();
      v50 = *(_QWORD **)v31;
      if ( *(VMX_PACK **)(*(_QWORD *)v31 + 8LL) == v31 )
      {
        v51 = (void **)*((_QWORD *)v31 + 1);
        if ( *v51 == v31 )
        {
          *v51 = v50;
          v50[1] = v51;
          VMX_PACK::`scalar deleting destructor'(v31, v49);
          VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
          {
            return (unsigned int)v33;
          }
          v35 = 59;
          goto LABEL_52;
        }
      }
      goto LABEL_95;
    }
    if ( *((_WORD *)v21 + 16) != 4 )
      goto LABEL_33;
    v22 = v21[5];
    v23 = *(_QWORD *)(v22 + 128);
    if ( !v23 || !*(_BYTE *)(v23 + 125) )
      goto LABEL_33;
    v24 = *(_QWORD *)(v23 + 104);
    if ( !v24 || *(_BYTE *)(v24 + 17) )
      break;
    if ( !*(_BYTE *)(v24 + 19) )
    {
      v25 = VMX_CONFIG::SynchronizeConfigCopy((VMX_CONFIG *)v4, *(struct VMX_CONFIG_COPY **)(v23 + 104));
      VMX_PACK::UpdateCounters(a1);
      if ( !*(_BYTE *)(v24 + 19) )
      {
        *(_BYTE *)(v23 + 125) = 0;
        VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 55, WPP_2f8af752156e3401cd435973c831895d_Traceguids, v25);
        }
        return v25;
      }
      v20 = v52;
      v4 = v55;
    }
    v26 = *(_QWORD *)(v7 + 168);
    v27 = 6LL * v20++;
    v52 = v20;
    *(_OWORD *)(v26 + 8 * v27) = *(_OWORD *)(v22 + 72);
    v28 = *(_OWORD *)(v22 + 72);
    *(_QWORD *)(v26 + 8 * v27 + 32) = v23;
    *(_BYTE *)(v26 + 8 * v27 + 40) = 0;
    *(_OWORD *)(v26 + 8 * v27 + 16) = v28;
LABEL_33:
    v21 = (__int64 *)*v21;
  }
  *(_BYTE *)(v23 + 125) = 0;
  VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'((VMX_CHANGE_IDENTITY_TRANSACTION *)v7);
  v10 = WPP_GLOBAL_Control;
  v9 = -1070071806;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v11 = 54;
    goto LABEL_8;
  }
  return v9;
}

```

## disassembly

```asm
0x14002c3dc  mov     [rsp+arg_8], rdx
0x14002c3e1  push    rbx
0x14002c3e2  push    rbp
0x14002c3e3  push    rsi
0x14002c3e4  push    rdi
0x14002c3e5  push    r12
0x14002c3e7  push    r13
0x14002c3e9  push    r14
0x14002c3eb  push    r15
0x14002c3ed  sub     rsp, 28h
0x14002c3f1  mov     rsi, rcx
0x14002c3f4  mov     [rdx], rcx
0x14002c3f7  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14002c3fc  xor     r14d, r14d
0x14002c3ff  test    al, al
0x14002c401  jnz     loc_14002C71D
0x14002c407  mov     r15, [rcx+10h]
0x14002c40b  mov     edx, 102h; unsigned __int64
0x14002c410  mov     r8d, 78546D56h; unsigned int
0x14002c416  mov     [rsp+68h+arg_18], r15
0x14002c41e  mov     rbx, [r15+8]
0x14002c422  lea     ecx, [rdx-4Ah]; unsigned __int64
0x14002c425  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002c42a  mov     rdi, rax
0x14002c42d  test    rax, rax
0x14002c430  jz      loc_14002CAAB
0x14002c436  xorps   xmm0, xmm0
0x14002c439  lea     rbp, [rbx+18h]
0x14002c43d  movups  xmmword ptr [rdi], xmm0
0x14002c440  xor     eax, eax
0x14002c442  lea     r12d, [r14+20h]
0x14002c446  movups  xmmword ptr [rdi+10h], xmm0
0x14002c44a  lea     rcx, [rdi+50h]; pszDest
0x14002c44e  mov     r8, rbp; pszSrc
0x14002c451  movups  xmmword ptr [rdi+20h], xmm0
0x14002c455  mov     [rdi+30h], rax
0x14002c459  mov     edx, r12d; cbDest
0x14002c45c  mov     word ptr [rdi+30h], 1
0x14002c462  mov     [rdi+0A0h], r14d
0x14002c469  mov     [rdi+0A8h], r14
0x14002c470  mov     [rdi+0B0h], r14w
0x14002c478  mov     [rdi+38h], rsi
0x14002c47c  movups  xmm0, xmmword ptr [rbx+8]
0x14002c480  movdqu  xmmword ptr [rdi+40h], xmm0
0x14002c485  call    RtlStringCbCopyA
0x14002c48a  lea     r13, [rdi+70h]
0x14002c48e  mov     rcx, r13; Uuid
0x14002c491  mov     [rsp+68h+arg_10], r13
0x14002c499  call    cs:__imp_ExUuidCreate
0x14002c4a0  nop     dword ptr [rax+rax+00h]
0x14002c4a5  mov     ebx, eax
0x14002c4a7  test    eax, eax
0x14002c4a9  jns     short loc_14002C4F4
0x14002c4ab  mov     rcx, rdi; this
0x14002c4ae  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c4b3  mov     r10, cs:WPP_GLOBAL_Control
0x14002c4ba  lea     rcx, WPP_GLOBAL_Control
0x14002c4c1  cmp     r10, rcx
0x14002c4c4  jz      short loc_14002C4ED
0x14002c4c6  mov     edx, [r10+2Ch]
0x14002c4ca  test    dl, 8
0x14002c4cd  jz      short loc_14002C4ED
0x14002c4cf  cmp     byte ptr [r10+29h], 2
0x14002c4d4  jb      short loc_14002C4ED
0x14002c4d6  lea     edx, [r14+34h]
0x14002c4da  mov     rcx, [r10+18h]
0x14002c4de  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002c4e5  mov     r9d, ebx
0x14002c4e8  call    WPP_SF_d
0x14002c4ed  mov     eax, ebx
0x14002c4ef  jmp     loc_14002C71F
0x14002c4f4  lea     rcx, [rdi+80h]; pszDest
0x14002c4fb  mov     r8, rbp; pszSrc
0x14002c4fe  mov     rdx, r12; cbDest
0x14002c501  call    RtlStringCbCopyA
0x14002c506  lea     r12, [r15+10h]
0x14002c50a  mov     r10d, r14d
0x14002c50d  mov     rcx, [r12]
0x14002c511  jmp     short loc_14002C536
0x14002c513  cmp     word ptr [rcx+20h], 4
0x14002c518  jnz     short loc_14002C533
0x14002c51a  mov     rax, [rcx+28h]
0x14002c51e  mov     rdx, [rax+80h]
0x14002c525  test    rdx, rdx
0x14002c528  jz      short loc_14002C533
0x14002c52a  cmp     [rdx+7Dh], r14b
0x14002c52e  jz      short loc_14002C533
0x14002c530  inc     r10d
0x14002c533  mov     rcx, [rcx]
0x14002c536  cmp     rcx, r12
0x14002c539  jnz     short loc_14002C513
0x14002c53b  mov     eax, r10d
0x14002c53e  mov     ecx, 102h
0x14002c543  mov     r8d, 20206D56h
0x14002c549  mov     [rdi+0A0h], r10d
0x14002c550  lea     rdx, [rax+rax*2]
0x14002c554  shl     rdx, 4
0x14002c558  call    cs:__imp_ExAllocatePool2
0x14002c55f  nop     dword ptr [rax+rax+00h]
0x14002c564  mov     [rdi+0A8h], rax
0x14002c56b  test    rax, rax
0x14002c56e  jnz     short loc_14002C5B0
0x14002c570  mov     rcx, rdi; this
0x14002c573  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c578  mov     r10, cs:WPP_GLOBAL_Control
0x14002c57f  lea     rcx, WPP_GLOBAL_Control
0x14002c586  cmp     r10, rcx
0x14002c589  jz      loc_14002CAE8
0x14002c58f  mov     eax, [r10+2Ch]
0x14002c593  test    al, 8
0x14002c595  jz      loc_14002CAE8
0x14002c59b  cmp     byte ptr [r10+29h], 2
0x14002c5a0  jb      loc_14002CAE8
0x14002c5a6  mov     edx, 35h ; '5'
0x14002c5ab  jmp     loc_14002CAD2
0x14002c5b0  mov     edx, r14d; unsigned int
0x14002c5b3  mov     r14, [r12]
0x14002c5b7  mov     [rsp+68h+arg_0], edx
0x14002c5bb  cmp     r14, r12
0x14002c5be  jz      loc_14002C706
0x14002c5c4  cmp     word ptr [r14+20h], 4
0x14002c5ca  jnz     loc_14002C66A
0x14002c5d0  mov     r13, [r14+28h]
0x14002c5d4  xor     r8d, r8d
0x14002c5d7  mov     rbx, [r13+80h]
0x14002c5de  test    rbx, rbx
0x14002c5e1  jz      loc_14002C66A
0x14002c5e7  cmp     [rbx+7Dh], r8b
0x14002c5eb  jz      short loc_14002C66A
0x14002c5ed  mov     rbp, [rbx+68h]
0x14002c5f1  test    rbp, rbp
0x14002c5f4  jz      loc_14002C6BD
0x14002c5fa  cmp     [rbp+11h], r8b
0x14002c5fe  jnz     loc_14002C6BD
0x14002c604  cmp     [rbp+13h], r8b
0x14002c608  jnz     short loc_14002C635
0x14002c60a  mov     rdx, rbp; struct VMX_CONFIG_COPY *
0x14002c60d  mov     rcx, r15; this
0x14002c610  call    ?SynchronizeConfigCopy@VMX_CONFIG@@QEAAJPEAVVMX_CONFIG_COPY@@@Z; VMX_CONFIG::SynchronizeConfigCopy(VMX_CONFIG_COPY *)
0x14002c615  mov     rcx, rsi; this
0x14002c618  mov     r15d, eax
0x14002c61b  call    ?UpdateCounters@VMX_PACK@@QEAAXXZ; VMX_PACK::UpdateCounters(void)
0x14002c620  xor     r8d, r8d
0x14002c623  cmp     [rbp+13h], r8b
0x14002c627  jz      short loc_14002C672
0x14002c629  mov     edx, [rsp+68h+arg_0]
0x14002c62d  mov     r15, [rsp+68h+arg_18]
0x14002c635  movups  xmm0, xmmword ptr [r13+48h]
0x14002c63a  mov     eax, edx
0x14002c63c  lea     rcx, [rax+rax*2]
0x14002c640  mov     rax, [rdi+0A8h]
0x14002c647  add     rcx, rcx
0x14002c64a  inc     edx
0x14002c64c  mov     [rsp+68h+arg_0], edx
0x14002c650  movdqu  xmmword ptr [rax+rcx*8], xmm0
0x14002c655  movups  xmm1, xmmword ptr [r13+48h]
0x14002c65a  mov     [rax+rcx*8+20h], rbx
0x14002c65f  mov     [rax+rcx*8+28h], r8b
0x14002c664  movdqu  xmmword ptr [rax+rcx*8+10h], xmm1
0x14002c66a  mov     r14, [r14]
0x14002c66d  jmp     loc_14002C5BB
0x14002c672  mov     rcx, rdi; this
0x14002c675  mov     [rbx+7Dh], r8b
0x14002c679  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c67e  mov     r10, cs:WPP_GLOBAL_Control
0x14002c685  lea     rcx, WPP_GLOBAL_Control
0x14002c68c  cmp     r10, rcx
0x14002c68f  jz      short loc_14002C6B8
0x14002c691  mov     eax, [r10+2Ch]
0x14002c695  test    al, 8
0x14002c697  jz      short loc_14002C6B8
0x14002c699  cmp     byte ptr [r10+29h], 2
0x14002c69e  jb      short loc_14002C6B8
0x14002c6a0  mov     rcx, [r10+18h]
0x14002c6a4  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002c6ab  mov     edx, 37h ; '7'
0x14002c6b0  mov     r9d, r15d
0x14002c6b3  call    WPP_SF_d
0x14002c6b8  mov     eax, r15d
0x14002c6bb  jmp     short loc_14002C71F
0x14002c6bd  mov     rcx, rdi; this
0x14002c6c0  mov     [rbx+7Dh], r8b
0x14002c6c4  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c6c9  mov     r10, cs:WPP_GLOBAL_Control
0x14002c6d0  lea     rcx, WPP_GLOBAL_Control
0x14002c6d7  mov     ebx, 0C0380002h
0x14002c6dc  cmp     r10, rcx
0x14002c6df  jz      loc_14002C4ED
0x14002c6e5  mov     eax, [r10+2Ch]
0x14002c6e9  test    al, 8
0x14002c6eb  jz      loc_14002C4ED
0x14002c6f1  cmp     byte ptr [r10+29h], 2
0x14002c6f6  jb      loc_14002C4ED
0x14002c6fc  mov     edx, 36h ; '6'
0x14002c701  jmp     loc_14002C4DA
0x14002c706  mov     rcx, rsi; this
0x14002c709  call    ?QuorumInSync@VMX_PACK@@QEAAEXZ; VMX_PACK::QuorumInSync(void)
0x14002c70e  xor     r15d, r15d
0x14002c711  test    al, al
0x14002c713  jz      short loc_14002C731
0x14002c715  mov     rcx, rdi; this
0x14002c718  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c71d  xor     eax, eax
0x14002c71f  add     rsp, 28h
0x14002c723  pop     r15
0x14002c725  pop     r14
0x14002c727  pop     r13
0x14002c729  pop     r12
0x14002c72b  pop     rdi
0x14002c72c  pop     rsi
0x14002c72d  pop     rbp
0x14002c72e  pop     rbx
0x14002c72f  retn
0x14002c731  mov     r14d, 40h ; '@'
0x14002c737  mov     edx, 102h; unsigned __int64
0x14002c73c  mov     ecx, r14d; unsigned __int64
0x14002c73f  mov     r8d, 61506D56h; unsigned int
0x14002c745  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x14002c74a  mov     rbx, rax
0x14002c74d  test    rax, rax
0x14002c750  jz      loc_14002CA7A
0x14002c756  mov     r8d, r14d; Size
0x14002c759  xor     edx, edx; Val
0x14002c75b  mov     rcx, rax; void *
0x14002c75e  call    memset
0x14002c763  mov     rdx, rsi; struct VMX_PACK *
0x14002c766  mov     rcx, rbx; this
0x14002c769  call    ?CopyPack@VMX_PACK@@QEAAJPEAV1@@Z; VMX_PACK::CopyPack(VMX_PACK *)
0x14002c76e  mov     ebp, eax
0x14002c770  test    eax, eax
0x14002c772  jns     short loc_14002C7C4
0x14002c774  mov     rcx, rbx; this
0x14002c777  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002c77c  mov     rcx, rdi; this
0x14002c77f  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c784  mov     r10, cs:WPP_GLOBAL_Control
0x14002c78b  lea     rcx, WPP_GLOBAL_Control
0x14002c792  cmp     r10, rcx
0x14002c795  jz      short loc_14002C7BD
0x14002c797  mov     eax, [r10+2Ch]
0x14002c79b  test    al, 8
0x14002c79d  jz      short loc_14002C7BD
0x14002c79f  cmp     byte ptr [r10+29h], 2
0x14002c7a4  jb      short loc_14002C7BD
0x14002c7a6  lea     edx, [r14-7]
0x14002c7aa  mov     rcx, [r10+18h]
0x14002c7ae  lea     r8, WPP_2f8af752156e3401cd435973c831895d_Traceguids
0x14002c7b5  mov     r9d, ebp
0x14002c7b8  call    WPP_SF_d
0x14002c7bd  mov     eax, ebp
0x14002c7bf  jmp     loc_14002C71F
0x14002c7c4  mov     rax, [rbx+18h]
0x14002c7c8  mov     r13, [rsp+68h+arg_10]
0x14002c7d0  test    rax, rax
0x14002c7d3  jz      short loc_14002C7DE
0x14002c7d5  movups  xmm0, xmmword ptr [r13+0]
0x14002c7da  movdqu  xmmword ptr [rax], xmm0
0x14002c7de  mov     rcx, r13; struct _GUID *
0x14002c7e1  call    ?VmxpWritePendingPrimaryPackId@@YAJPEAU_GUID@@@Z; VmxpWritePendingPrimaryPackId(_GUID *)
0x14002c7e6  mov     ebp, eax
0x14002c7e8  test    eax, eax
0x14002c7ea  jns     short loc_14002C825
0x14002c7ec  mov     rcx, rbx; this
0x14002c7ef  call    ??_GVMX_PACK@@QEAAPEAXI@Z; VMX_PACK::`scalar deleting destructor'(uint)
0x14002c7f4  mov     rcx, rdi; this
0x14002c7f7  call    ??_GVMX_CHANGE_IDENTITY_TRANSACTION@@QEAAPEAXI@Z; VMX_CHANGE_IDENTITY_TRANSACTION::`scalar deleting destructor'(uint)
0x14002c7fc  mov     r10, cs:WPP_GLOBAL_Control
0x14002c803  lea     rcx, WPP_GLOBAL_Control
0x14002c80a  cmp     r10, rcx
0x14002c80d  jz      short loc_14002C7BD
0x14002c80f  mov     eax, [r10+2Ch]
0x14002c813  test    al, 8
0x14002c815  jz      short loc_14002C7BD
0x14002c817  cmp     byte ptr [r10+29h], 2
0x14002c81c  jb      short loc_14002C7BD
0x14002c81e  mov     edx, 3Ah ; ':'
0x14002c823  jmp     short loc_14002C7AA
0x14002c825  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x14002c82c  mov     r12d, 3
0x14002c832  add     rax, 0C8h
0x14002c838  mov     rcx, [rax+8]
0x14002c83c  cmp     [rcx], rax
0x14002c83f  jnz     loc_14002CA75
0x14002c845  mov     [rbx], rax
0x14002c848  lea     edx, [r12+35h]
0x14002c84d  mov     [rbx+8], rcx
0x14002c851  mov     [rcx], rbx
0x14002c854  mov     [rax+8], rbx
0x14002c858  mov     rax, [rbx+10h]
0x14002c85c  mov     [rbx+30h], rdi
0x14002c860  mov     rcx, [rax+8]
0x14002c864  cmp     [rcx+48h], r12w
0x14002c869  cmovnz  r14, rdx
0x14002c86d  mov     rax, [r14+rcx]
0x14002c871  inc     rax
0x14002c874  mov     [rdi], rax
0x14002c877  movups  xmm0, xmmword ptr [rcx+90h]
0x14002c87e  mov     rax, [rbx+30h]
0x14002c882  movups  xmmword ptr [rax+8], xmm0
0x14002c886  movups  xmm1, xmmword ptr [rcx+9Ch]
  ... truncated ...
```
