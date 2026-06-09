# PnPServices::CHandleNotif::HandleBroadcastHandleEvent(PnPServices::CPnPDeviceEvent *)

- ea: `0x180002e70`
- end: `0x1800033dd`
- name: `?HandleBroadcastHandleEvent@CHandleNotif@PnPServices@@SAJPEAVCPnPDeviceEvent@2@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(struct PnPServices::CPnPDeviceEvent *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800016f0`

## callees

- `0x180002e70`
- `0x180003570`
- `0x180015f50`
- `0x180018de0`
- `0x18001b404`
- `0x180025b2c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003233`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003233`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003244`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ed5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002fda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800031ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003085`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003085`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800032c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033b6`

## pseudocode

```c
__int64 __fastcall PnPServices::CHandleNotif::HandleBroadcastHandleEvent(struct PnPServices::CPnPDeviceEvent *a1)
{
  CRefCounted *v1; // rbp
  _DWORD *v2; // rax
  _DWORD *v3; // r13
  __int64 v4; // rdx
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  __int64 v6; // rdi
  __int64 i; // rbx
  __int64 v8; // rdx
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rdx
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // rbp
  int v17; // edi
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rdx
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  __int64 v22; // rbx
  struct PnPServices::CPnPDeviceEvent *v23; // r13
  const struct _GUID *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r15
  struct _RTL_CRITICAL_SECTION *v29; // r12
  struct _RTL_CRITICAL_SECTION *v30; // rcx
  _DWORD *v31; // rax
  _DWORD *v32; // r14
  unsigned int v33; // ebp
  HANDLE ProcessHeap; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // r13
  unsigned int v37; // ebx
  volatile signed __int32 **v38; // rdi
  volatile signed __int32 *Ptr; // rax
  struct _RTL_CRITICAL_SECTION *v40; // rcx
  unsigned int v41; // ebp
  __int64 v42; // rbx
  __int64 v43; // rax
  CRefCounted *v44; // rdi
  __int64 v46; // rdx
  struct _RTL_CRITICAL_SECTION *v47; // rcx
  __int64 v49; // [rsp+80h] [rbp+18h]
  __int64 v50; // [rsp+88h] [rbp+20h]

  v1 = PnPServices::g_pnelHandleNotif;
  v50 = *((_QWORD *)a1 + 5);
  v2 = operator new(0x28u);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v2[2] = 1;
  *((_QWORD *)v2 + 2) = 0;
  *(_QWORD *)v2 = &CNamedElemEnum<PnPServices::CHandleNotif>::`vftable';
  *((_QWORD *)v2 + 4) = 0;
  v4 = *((_QWORD *)v1 + 3);
  v5 = (struct _RTL_CRITICAL_SECTION *)(v4 + 8);
  if ( !v4 )
    v5 = 0;
  EnterCriticalSection(v5);
  v6 = *((_QWORD *)v1 + 2);
  if ( !v6 )
    goto LABEL_101;
  if ( !*(_QWORD *)(v6 + 16) )
  {
    v6 = *(_QWORD *)(v6 + 32);
    if ( v6 )
    {
      while ( !*(_QWORD *)(v6 + 16) )
      {
        v6 = *(_QWORD *)(v6 + 32);
        if ( !v6 )
          goto LABEL_12;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
LABEL_12:
      if ( v6 )
        goto LABEL_13;
    }
LABEL_101:
    (**(void (__fastcall ***)(_DWORD *, __int64))v3)(v3, 1);
    v46 = *((_QWORD *)v1 + 3);
    v47 = (struct _RTL_CRITICAL_SECTION *)(v46 + 8);
    if ( !v46 )
      v47 = 0;
    LeaveCriticalSection(v47);
    return 2147500037LL;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
LABEL_13:
  for ( i = v6; ; v6 = i )
  {
    i = *(_QWORD *)(i + 32);
    if ( !i )
      break;
    while ( !*(_QWORD *)(i + 16) )
    {
      i = *(_QWORD *)(i + 32);
      if ( !i )
        goto LABEL_17;
    }
    _InterlockedIncrement((volatile signed __int32 *)(i + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
  }
LABEL_17:
  v8 = *((_QWORD *)v1 + 3);
  _InterlockedIncrement((volatile signed __int32 *)(v8 + 64));
  *((_QWORD *)v3 + 4) = v8;
  v9 = (struct _RTL_CRITICAL_SECTION *)(v8 + 8);
  v3[6] = 1;
  if ( !v8 )
    v9 = 0;
  EnterCriticalSection(v9);
  *((_QWORD *)v3 + 2) = v6;
  _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v10 = *((_QWORD *)v3 + 4);
  v11 = (struct _RTL_CRITICAL_SECTION *)(v10 + 8);
  if ( !v10 )
    v11 = 0;
  LeaveCriticalSection(v11);
  CRefCounted::Release((CRefCounted *)v6);
  v12 = *((_QWORD *)v1 + 3);
  v13 = (struct _RTL_CRITICAL_SECTION *)(v12 + 8);
  if ( !v12 )
    v13 = 0;
  LeaveCriticalSection(v13);
  v14 = 0;
  v49 = 0;
  while ( 1 )
  {
    v15 = *((_QWORD *)v3 + 4);
    v16 = 0;
    v17 = 1;
    v18 = (struct _RTL_CRITICAL_SECTION *)(v15 + 8);
    if ( !v15 )
      v18 = 0;
    EnterCriticalSection(v18);
    v19 = *((_QWORD *)v3 + 2);
    if ( v19 )
    {
      if ( v3[6] && *(_QWORD *)(v19 + 16) )
        goto LABEL_38;
      v19 = *(_QWORD *)(v19 + 24);
      if ( v19 )
      {
        while ( !*(_QWORD *)(v19 + 16) )
        {
          v19 = *(_QWORD *)(v19 + 24);
          if ( !v19 )
            goto LABEL_37;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
      }
LABEL_37:
      CRefCounted::Release(*((CRefCounted **)v3 + 2));
      *((_QWORD *)v3 + 2) = v19;
      if ( v19 )
      {
LABEL_38:
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v19 + 16) + 24LL));
        v16 = *(_QWORD *)(v19 + 16);
        v17 = 0;
      }
      v3[6] = 0;
    }
    v20 = *((_QWORD *)v3 + 4);
    v21 = (struct _RTL_CRITICAL_SECTION *)(v20 + 8);
    if ( !v20 )
      v21 = 0;
    LeaveCriticalSection(v21);
    if ( v17 != 1 )
      break;
    v22 = v49;
LABEL_52:
    if ( v17 == 1 )
      goto LABEL_53;
  }
  if ( v50 == *(_QWORD *)(v16 + 112) )
  {
    v14 = 1;
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 24));
    v22 = v16;
    v49 = v16;
  }
  else
  {
    v22 = v49;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 24), 0xFFFFFFFF) == 1 && v16 != -16 )
    (**(void (__fastcall ***)(__int64, __int64))(v16 + 16))(v16 + 16, 1);
  v17 = 0;
  if ( !v14 )
    goto LABEL_52;
LABEL_53:
  if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(_DWORD *, __int64))v3)(v3, 1);
  if ( v14 )
  {
    v23 = a1;
    if ( *((_DWORD *)a1 + 4) == 32769
      || *((_DWORD *)a1 + 4) == 32770
      || *((_DWORD *)a1 + 4) == 32771
      || *((_DWORD *)a1 + 4) == 32772 )
    {
      if ( (unsigned int)(*((_DWORD *)a1 + 4) - 32771) <= 1 )
        CRegisterNotification::_Unregister((CRegisterNotification *)(v22 + 104));
LABEL_75:
      v28 = v22 + 40;
      v17 = 0;
      v29 = (struct _RTL_CRITICAL_SECTION *)(v22 + 48);
      v30 = (struct _RTL_CRITICAL_SECTION *)(v22 + 48);
      if ( v22 == -40 )
        v30 = 0;
      EnterCriticalSection(v30);
      v31 = operator new(0x20u);
      v32 = v31;
      if ( v31 )
      {
        v31[2] = 1;
        *(_QWORD *)v31 = &CGrowableArrayEnum<PnPServices::IPnPDeviceEventCB>::`vftable';
        v31[4] = 0;
        *((_QWORD *)v31 + 3) = 0;
        v33 = **(_DWORD **)(v22 + 32);
        if ( v33 )
        {
          ProcessHeap = GetProcessHeap();
          v35 = HeapAlloc(ProcessHeap, 8u, 8LL * v33);
          v36 = v35;
          if ( v35 )
          {
            v37 = 0;
            v38 = (volatile signed __int32 **)v35;
            do
            {
              Ptr = (volatile signed __int32 *)g_pfn_DPA_GetPtr(*(HDPA *)(v49 + 32), v37);
              *v38 = Ptr;
              _InterlockedIncrement(Ptr + 2);
              ++v37;
              ++v38;
            }
            while ( v37 < v33 );
            v29 = (struct _RTL_CRITICAL_SECTION *)(v28 + 8);
            *((_QWORD *)v32 + 3) = v36;
            v17 = 0;
            v23 = a1;
            v32[4] = v33;
          }
          else
          {
            v17 = -2147024882;
            (**(void (__fastcall ***)(_DWORD *, __int64))v32)(v32, 1);
            v23 = a1;
            v32 = 0;
          }
        }
      }
      else
      {
        v32 = 0;
        v17 = -2147024882;
      }
      v40 = 0;
      if ( v28 )
        v40 = v29;
      LeaveCriticalSection(v40);
      if ( v17 >= 0 )
      {
        v41 = v32[4];
        v42 = 0;
        while ( (unsigned int)v42 < v41 )
        {
          if ( (unsigned int)v42 >= v32[4]
            || (_InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)v32 + 3) + 8 * v42) + 8LL)),
                v43 = *((_QWORD *)v32 + 3),
                (v44 = *(CRefCounted **)(8 * v42 + v43)) == 0) )
          {
            v17 = -2147467259;
            break;
          }
          (*(void (__fastcall **)(_QWORD, struct PnPServices::CPnPDeviceEvent *))(*(_QWORD *)v44 + 8LL))(
            *(_QWORD *)(8 * v42 + v43),
            v23);
          CRefCounted::Release(v44);
          v42 = (unsigned int)(v42 + 1);
          v17 = 0;
        }
        if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(_DWORD *, __int64))v32)(v32, 1);
      }
      v22 = v49;
    }
    else
    {
      if ( *((_DWORD *)a1 + 4) != 32774 )
        goto LABEL_75;
      v24 = (const struct _GUID *)((char *)a1 + 20);
      v25 = *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1 - *(_QWORD *)((char *)a1 + 20);
      if ( *(_QWORD *)&GUID_IO_VOLUME_LOCK.Data1 == *(_QWORD *)((char *)a1 + 20) )
        v25 = *(_QWORD *)GUID_IO_VOLUME_LOCK.Data4 - *(_QWORD *)((char *)a1 + 28);
      if ( !v25 )
        goto LABEL_70;
      v26 = *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1 - *(_QWORD *)&v24->Data1;
      if ( *(_QWORD *)&GUID_IO_VOLUME_LOCK_FAILED.Data1 == *(_QWORD *)&v24->Data1 )
        v26 = *(_QWORD *)GUID_IO_VOLUME_LOCK_FAILED.Data4 - *(_QWORD *)((char *)a1 + 28);
      if ( !v26 )
        goto LABEL_70;
      v27 = *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1 - *(_QWORD *)&v24->Data1;
      if ( *(_QWORD *)&GUID_IO_VOLUME_UNLOCK.Data1 == *(_QWORD *)&v24->Data1 )
        v27 = *(_QWORD *)GUID_IO_VOLUME_UNLOCK.Data4 - *(_QWORD *)((char *)a1 + 28);
      if ( !v27 )
LABEL_70:
        v17 = PnPServices::CHandleNotif::_HandleDeviceLockUnlock((PnPServices::CHandleNotif *)v22, v24);
      if ( v17 >= 0 )
        goto LABEL_75;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 24), 0xFFFFFFFF) == 1 && v22 != -16 )
      (**(void (__fastcall ***)(__int64, __int64))(v22 + 16))(v22 + 16, 1);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180002e70  mov     [rsp+arg_0], rcx
0x180002e75  push    rbx
0x180002e76  push    rbp
0x180002e77  push    rdi
0x180002e78  push    r13
0x180002e7a  push    r14
0x180002e7c  sub     rsp, 40h
0x180002e80  mov     rax, [rcx+28h]
0x180002e84  mov     ecx, 28h ; '('; Size
0x180002e89  mov     rbp, cs:?g_pnelHandleNotif@PnPServices@@3PEAV?$CNamedElemList@VCHandleNotif@PnPServices@@@@EA; CNamedElemList<PnPServices::CHandleNotif> * PnPServices::g_pnelHandleNotif
0x180002e90  mov     [rsp+68h+arg_18], rax
0x180002e98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e9d  mov     r13, rax
0x180002ea0  test    rax, rax
0x180002ea3  jz      loc_1800033CA
0x180002ea9  xor     r14d, r14d
0x180002eac  mov     dword ptr [rax+8], 1
0x180002eb3  lea     rax, ??_7?$CNamedElemEnum@VCHandleNotif@PnPServices@@@@6B@; const CNamedElemEnum<PnPServices::CHandleNotif>::`vftable'
0x180002eba  mov     [r13+10h], r14
0x180002ebe  mov     [r13+0], rax
0x180002ec2  mov     [r13+20h], r14
0x180002ec6  mov     rdx, [rbp+18h]
0x180002eca  test    rdx, rdx
0x180002ecd  lea     rcx, [rdx+8]
0x180002ed1  cmovz   rcx, r14; lpCriticalSection
0x180002ed5  call    cs:__imp_EnterCriticalSection
0x180002edb  mov     rdi, [rbp+10h]
0x180002edf  test    rdi, rdi
0x180002ee2  jz      loc_18000338E
0x180002ee8  cmp     [rdi+10h], r14
0x180002eec  jz      short loc_180002EF4
0x180002eee  lock inc dword ptr [rdi+8]
0x180002ef2  jmp     short loc_180002F1F
0x180002ef4  mov     rdi, [rdi+20h]
0x180002ef8  test    rdi, rdi
0x180002efb  jz      loc_18000338E
0x180002f01  cmp     [rdi+10h], r14
0x180002f05  jnz     short loc_180002F12
0x180002f07  mov     rdi, [rdi+20h]
0x180002f0b  test    rdi, rdi
0x180002f0e  jnz     short loc_180002F01
0x180002f10  jmp     short loc_180002F16
0x180002f12  lock inc dword ptr [rdi+8]
0x180002f16  test    rdi, rdi
0x180002f19  jz      loc_18000338E
0x180002f1f  mov     [rsp+68h+var_30], rsi
0x180002f24  mov     rbx, rdi
0x180002f27  mov     [rsp+68h+var_38], r12
0x180002f2c  mov     esi, 0FFFFFFFFh
0x180002f31  mov     [rsp+68h+var_40], r15
0x180002f36  mov     rbx, [rbx+20h]
0x180002f3a  test    rbx, rbx
0x180002f3d  jz      short loc_180002F53
0x180002f3f  nop
0x180002f40  cmp     [rbx+10h], r14
0x180002f44  jnz     loc_180003013
0x180002f4a  mov     rbx, [rbx+20h]
0x180002f4e  test    rbx, rbx
0x180002f51  jnz     short loc_180002F40
0x180002f53  mov     rdx, [rbp+18h]
0x180002f57  lock inc dword ptr [rdx+40h]
0x180002f5b  test    rdx, rdx
0x180002f5e  mov     [r13+20h], rdx
0x180002f62  lea     rcx, [rdx+8]
0x180002f66  mov     dword ptr [r13+18h], 1
0x180002f6e  cmovz   rcx, r14; lpCriticalSection
0x180002f72  call    cs:__imp_EnterCriticalSection
0x180002f78  mov     [r13+10h], rdi
0x180002f7c  test    rdi, rdi
0x180002f7f  jz      short loc_180002F85
0x180002f81  lock inc dword ptr [rdi+8]
0x180002f85  mov     rdx, [r13+20h]
0x180002f89  test    rdx, rdx
0x180002f8c  lea     rcx, [rdx+8]
0x180002f90  cmovz   rcx, r14; lpCriticalSection
0x180002f94  call    cs:__imp_LeaveCriticalSection
0x180002f9a  mov     rcx, rdi; this
0x180002f9d  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002fa2  mov     rdx, [rbp+18h]
0x180002fa6  test    rdx, rdx
0x180002fa9  lea     rcx, [rdx+8]
0x180002fad  cmovz   rcx, r14; lpCriticalSection
0x180002fb1  call    cs:__imp_LeaveCriticalSection
0x180002fb7  xor     r15d, r15d
0x180002fba  mov     [rsp+68h+arg_10], r14
0x180002fc2  mov     rdx, [r13+20h]
0x180002fc6  xor     eax, eax
0x180002fc8  xor     ebp, ebp
0x180002fca  mov     edi, 1
0x180002fcf  test    rdx, rdx
0x180002fd2  lea     rcx, [rdx+8]
0x180002fd6  cmovz   rcx, rax; lpCriticalSection
0x180002fda  call    cs:__imp_EnterCriticalSection
0x180002fe0  mov     rbx, [r13+10h]
0x180002fe4  test    rbx, rbx
0x180002fe7  jz      loc_180003074
0x180002fed  cmp     [r13+18h], ebp
0x180002ff1  jz      short loc_180002FF9
0x180002ff3  cmp     [rbx+10h], rbp
0x180002ff7  jnz     short loc_180003062
0x180002ff9  mov     rbx, [rbx+18h]
0x180002ffd  test    rbx, rbx
0x180003000  jz      short loc_180003050
0x180003002  cmp     [rbx+10h], rbp
0x180003006  jnz     short loc_18000304C
0x180003008  mov     rbx, [rbx+18h]
0x18000300c  test    rbx, rbx
0x18000300f  jnz     short loc_180003002
0x180003011  jmp     short loc_180003050
0x180003013  lock inc dword ptr [rbx+8]
0x180003017  test    rbx, rbx
0x18000301a  jz      loc_180002F53
0x180003020  mov     eax, esi
0x180003022  lock xadd [rdi+8], eax
0x180003027  cmp     eax, 1
0x18000302a  jnz     short loc_180003044
0x18000302c  test    rdi, rdi
0x18000302f  jz      short loc_180003044
0x180003031  mov     rax, [rdi]
0x180003034  mov     edx, 1
0x180003039  mov     rcx, rdi
0x18000303c  mov     rax, [rax]
0x18000303f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003044  mov     rdi, rbx
0x180003047  jmp     loc_180002F36
0x18000304c  lock inc dword ptr [rbx+8]
0x180003050  mov     rcx, [r13+10h]; this
0x180003054  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180003059  mov     [r13+10h], rbx
0x18000305d  test    rbx, rbx
0x180003060  jz      short loc_180003070
0x180003062  mov     rax, [rbx+10h]
0x180003066  lock inc dword ptr [rax+18h]
0x18000306a  mov     rbp, [rbx+10h]
0x18000306e  xor     edi, edi
0x180003070  mov     [r13+18h], r14d
0x180003074  mov     rdx, [r13+20h]
0x180003078  xor     eax, eax
0x18000307a  test    rdx, rdx
0x18000307d  lea     rcx, [rdx+8]
0x180003081  cmovz   rcx, rax; lpCriticalSection
0x180003085  call    cs:__imp_LeaveCriticalSection
0x18000308b  cmp     edi, 1
0x18000308e  jz      short loc_1800030EB
0x180003090  mov     rax, [rsp+68h+arg_18]
0x180003098  cmp     rax, [rbp+70h]
0x18000309c  jnz     short loc_1800030B5
0x18000309e  mov     r15d, 1
0x1800030a4  lock inc dword ptr [rbp+18h]
0x1800030a8  mov     rbx, rbp
0x1800030ab  mov     [rsp+68h+arg_10], rbx
0x1800030b3  jmp     short loc_1800030BD
0x1800030b5  mov     rbx, [rsp+68h+arg_10]
0x1800030bd  lea     rcx, [rbp+10h]
0x1800030c1  mov     eax, esi
0x1800030c3  lock xadd [rcx+8], eax
0x1800030c8  cmp     eax, 1
0x1800030cb  jnz     short loc_1800030E2
0x1800030cd  test    rcx, rcx
0x1800030d0  jz      short loc_1800030E2
0x1800030d2  mov     rax, [rcx]
0x1800030d5  mov     edx, 1
0x1800030da  mov     rax, [rax]
0x1800030dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e2  xor     edi, edi
0x1800030e4  test    r15d, r15d
0x1800030e7  jnz     short loc_1800030FC
0x1800030e9  jmp     short loc_1800030F3
0x1800030eb  mov     rbx, [rsp+68h+arg_10]
0x1800030f3  cmp     edi, 1
0x1800030f6  jnz     loc_180002FC2
0x1800030fc  mov     eax, esi
0x1800030fe  lock xadd [r13+8], eax
0x180003104  cmp     eax, 1
0x180003107  jnz     short loc_18000311D
0x180003109  mov     rax, [r13+0]
0x18000310d  mov     edx, 1
0x180003112  mov     rcx, r13
0x180003115  mov     rax, [rax]
0x180003118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000311d  test    r15d, r15d
0x180003120  jz      loc_180003371
0x180003126  mov     r13, [rsp+68h+arg_0]
0x18000312b  mov     ecx, [r13+10h]
0x18000312f  mov     eax, ecx
0x180003131  sub     eax, 8001h
0x180003136  jz      loc_1800031C0
0x18000313c  sub     eax, 1
0x18000313f  jz      short loc_1800031C0
0x180003141  sub     eax, 1
0x180003144  jz      short loc_1800031C0
0x180003146  sub     eax, 1
0x180003149  jz      short loc_1800031C0
0x18000314b  cmp     eax, 2
0x18000314e  jnz     loc_1800031D6
0x180003154  mov     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data1
0x18000315b  lea     rdx, [r13+14h]; struct _GUID *
0x18000315f  sub     rax, [rdx]
0x180003162  jnz     short loc_18000316F
0x180003164  mov     rax, qword ptr cs:GUID_IO_VOLUME_LOCK.Data4
0x18000316b  sub     rax, [rdx+8]
0x18000316f  test    rax, rax
0x180003172  jz      short loc_1800031AC
0x180003174  mov     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data1
0x18000317b  sub     rax, [rdx]
0x18000317e  jnz     short loc_18000318B
0x180003180  mov     rax, qword ptr cs:GUID_IO_VOLUME_LOCK_FAILED.Data4
0x180003187  sub     rax, [rdx+8]
0x18000318b  test    rax, rax
0x18000318e  jz      short loc_1800031AC
0x180003190  mov     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data1
0x180003197  sub     rax, [rdx]
0x18000319a  jnz     short loc_1800031A7
0x18000319c  mov     rax, qword ptr cs:GUID_IO_VOLUME_UNLOCK.Data4
0x1800031a3  sub     rax, [rdx+8]
0x1800031a7  test    rax, rax
0x1800031aa  jnz     short loc_1800031B6
0x1800031ac  mov     rcx, rbx; this
0x1800031af  call    ?_HandleDeviceLockUnlock@CHandleNotif@PnPServices@@AEAAJPEBU_GUID@@@Z; PnPServices::CHandleNotif::_HandleDeviceLockUnlock(_GUID const *)
0x1800031b4  mov     edi, eax
0x1800031b6  test    edi, edi
0x1800031b8  js      loc_180003351
0x1800031be  jmp     short loc_1800031D6
0x1800031c0  sub     ecx, 8003h
0x1800031c6  jz      short loc_1800031CD
0x1800031c8  cmp     ecx, 1
0x1800031cb  jnz     short loc_1800031D6
0x1800031cd  lea     rcx, [rbx+68h]; this
0x1800031d1  call    ?_Unregister@CRegisterNotification@@IEAAJXZ; CRegisterNotification::_Unregister(void)
0x1800031d6  lea     r15, [rbx+28h]
0x1800031da  xor     edi, edi
0x1800031dc  lea     r12, [r15+8]
0x1800031e0  test    r15, r15
0x1800031e3  mov     rcx, r12
0x1800031e6  cmovz   rcx, rdi; lpCriticalSection
0x1800031ea  call    cs:__imp_EnterCriticalSection
0x1800031f0  mov     ecx, 20h ; ' '; Size
0x1800031f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800031fa  mov     r14, rax
0x1800031fd  test    rax, rax
0x180003200  jz      loc_1800032B8
0x180003206  mov     dword ptr [rax+8], 1
0x18000320d  lea     rax, ??_7?$CGrowableArrayEnum@VIPnPDeviceEventCB@PnPServices@@@@6B@; const CGrowableArrayEnum<PnPServices::IPnPDeviceEventCB>::`vftable'
0x180003214  mov     [r14], rax
0x180003217  mov     [r14+10h], edi
0x18000321b  mov     [r14+18h], rdi
0x18000321f  mov     rax, [rbx+20h]
0x180003223  mov     ebp, [rax]
0x180003225  test    ebp, ebp
0x180003227  jz      loc_1800032C0
0x18000322d  mov     ebx, ebp
0x18000322f  shl     rbx, 3
0x180003233  call    cs:__imp_GetProcessHeap
0x180003239  mov     r8, rbx; dwBytes
0x18000323c  mov     edx, 8; dwFlags
0x180003241  mov     rcx, rax; hHeap
0x180003244  call    cs:__imp_HeapAlloc
0x18000324a  mov     r13, rax
0x18000324d  test    rax, rax
0x180003250  jz      short loc_180003296
0x180003252  xor     ebx, ebx
0x180003254  mov     rdi, rax
0x180003257  test    ebp, ebp
0x180003259  jz      short loc_180003285
0x18000325b  mov     r12, [rsp+68h+arg_10]
0x180003263  mov     rcx, [r12+20h]; hdpa
0x180003268  mov     edx, ebx; i
0x18000326a  call    cs:g_pfn_DPA_GetPtr
0x180003270  mov     [rdi], rax
0x180003273  lock inc dword ptr [rax+8]
0x180003277  inc     ebx
0x180003279  lea     rdi, [rdi+8]
0x18000327d  cmp     ebx, ebp
0x18000327f  jb      short loc_180003263
0x180003281  lea     r12, [r15+8]
0x180003285  mov     [r14+18h], r13
0x180003289  xor     edi, edi
0x18000328b  mov     r13, [rsp+68h+arg_0]
0x180003290  mov     [r14+10h], ebp
0x180003294  jmp     short loc_1800032C0
0x180003296  mov     rax, [r14]
0x180003299  mov     edx, 1
0x18000329e  mov     rcx, r14
0x1800032a1  mov     edi, 8007000Eh
0x1800032a6  mov     rax, [rax]
0x1800032a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ae  mov     r13, [rsp+68h+arg_0]
0x1800032b3  xor     r14d, r14d
0x1800032b6  jmp     short loc_1800032C0
0x1800032b8  mov     r14, rdi
0x1800032bb  mov     edi, 8007000Eh
0x1800032c0  xor     ecx, ecx
0x1800032c2  test    r15, r15
0x1800032c5  cmovnz  rcx, r12; lpCriticalSection
0x1800032c9  call    cs:__imp_LeaveCriticalSection
0x1800032cf  test    edi, edi
0x1800032d1  js      short loc_180003349
0x1800032d3  mov     ebp, [r14+10h]
0x1800032d7  xor     ebx, ebx
0x1800032d9  cmp     ebx, ebp
  ... truncated ...
```
