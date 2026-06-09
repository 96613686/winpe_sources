# CDeviceEntry::SyncCreatePDO(void)

- ea: `0x18002c6f8`
- end: `0x18002c9cb`
- name: `?SyncCreatePDO@CDeviceEntry@@AEAAJXZ`
- size: `723`
- prototype: `__int64 __fastcall(CDeviceEntry *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18002cbc0`

## callees

- `0x180007da0`
- `0x18000abc0`
- `0x18000add8`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f75c`
- `0x18002b234`
- `0x18002bc88`
- `0x18002c600`
- `0x18002c624`
- `0x18002c6f8`
- `0x18002c9d4`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c8ab`

## string_xrefs

- `0x18002c871`: `CreatePDO FAILED`

## pseudocode

```c
__int64 __fastcall CDeviceEntry::SyncCreatePDO(CDeviceEntry *this)
{
  CTSCriticalSection *v1; // rbx
  struct IRemoteDevice *v3; // rdi
  bool v4; // zf
  int v5; // esi
  struct IRemoteDevice **v6; // r14
  int *v7; // r15
  bool IsPOSDevice; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  struct IRemoteDevice *v10; // rsi
  int v11; // eax
  int v12; // eax
  int v14; // eax
  int v15; // [rsp+70h] [rbp+40h] BYREF
  struct IRemoteDevice *v16; // [rsp+78h] [rbp+48h] BYREF
  struct IRemoteDevice *v17; // [rsp+80h] [rbp+50h]
  char *v18; // [rsp+88h] [rbp+58h] BYREF

  v1 = (CDeviceEntry *)((char *)this + 128);
  v18 = (char *)this + 128;
  CTSCriticalSection::Lock((CDeviceEntry *)((char *)this + 128));
  v3 = 0;
  v4 = (*((_BYTE *)this + 28) & 4) == 0;
  v16 = 0;
  if ( !v4 )
    goto LABEL_2;
  v15 = 0;
  v6 = (struct IRemoteDevice **)((char *)this + 80);
  (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 10) + 240LL))(*((_QWORD *)this + 10), &v15);
  v7 = (int *)((char *)this + 72);
  if ( (v15 & 1) != 0 )
  {
    *v7 |= 0x100u;
    CTSCriticalSection::UnLock(v1);
    IsPOSDevice = CDeviceEntry::IsPOSDevice(this, *v6);
    CTSCriticalSection::Lock(v1);
    *v7 |= 0x200u;
    if ( (*((_BYTE *)this + 28) & 4) != 0 )
    {
LABEL_2:
      v5 = 1;
      goto LABEL_18;
    }
    if ( !IsPOSDevice )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          17,
          WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      goto LABEL_2;
    }
  }
  *v7 |= 4u;
  v10 = 0;
  v17 = 0;
  if ( *v6 )
  {
    TCntPtr<IDispatch>::SafeRelease(&v16);
    v16 = *v6;
    v3 = v16;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v16);
    v10 = v3;
    v17 = v3;
  }
  CTSCriticalSection::UnLock(v1);
  v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, _QWORD))(*(_QWORD *)v10 + 216LL))(v10, *((_QWORD *)this + 15));
  CTSCriticalSection::Lock(v1);
  if ( v5 < 0
    && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      18,
      (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
      v11,
      (__int64)"CreatePDO FAILED",
      v5);
    v12 = *v7;
LABEL_17:
    *v7 = v12 | 0x10;
    SetLastError(v5);
    CrimsonHelper::RaiseEvent<unsigned short *>(
      &CrimsonHelper::s_instance,
      EVENT_NOTIFY_CREATE_PDO_FAILED,
      *((_QWORD *)this + 12));
    goto LABEL_18;
  }
  v12 = *v7;
  if ( v5 )
    goto LABEL_17;
  v4 = (*((_BYTE *)this + 28) & 4) == 0;
  *v7 = v12 | 8;
  if ( v4 )
  {
    CDeviceEntry::StartTimer((void **)this);
    goto LABEL_18;
  }
  if ( v17 != *v6 )
  {
    TCntPtr<IDispatch>::SafeRelease((char *)this + 80);
    *v6 = v3;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
  }
  TCntPtr<IDispatch>::SafeRelease(&v16);
  v16 = 0;
  TCntPtr<ITSAsyncCallback>::SafeAddRef(&v16);
  v5 = CDeviceEntry::SyncDestroyPDO(this);
  if ( *v6 )
  {
    TCntPtr<IDispatch>::SafeRelease((char *)this + 80);
    *v6 = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
  }
  if ( v5 >= 0 )
    goto LABEL_2;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      19,
      (unsigned int)WPP_9f8b2618b856326daa1832c892715ef0_Traceguids,
      v14,
      (__int64)"SyncDestroyPDO FAILED",
      v5);
  }
LABEL_18:
  TCntPtr<IDispatch>::SafeRelease(&v16);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c6f8  push    rbp
0x18002c6fa  push    rbx
0x18002c6fb  push    rsi
0x18002c6fc  push    rdi
0x18002c6fd  push    r13
0x18002c6ff  push    r14
0x18002c701  push    r15
0x18002c703  mov     rbp, rsp
0x18002c706  sub     rsp, 30h
0x18002c70a  lea     rbx, [rcx+80h]
0x18002c711  mov     r13, rcx
0x18002c714  mov     rcx, rbx; this
0x18002c717  mov     [rbp+arg_18], rbx
0x18002c71b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002c720  xor     edi, edi
0x18002c722  test    byte ptr [r13+1Ch], 4
0x18002c727  mov     [rbp+arg_8], rdi
0x18002c72b  jz      short loc_18002C737
0x18002c72d  mov     esi, 1
0x18002c732  jmp     loc_18002C8C8
0x18002c737  mov     [rbp+arg_0], edi
0x18002c73a  lea     r14, [r13+50h]
0x18002c73e  mov     rcx, [r14]
0x18002c741  lea     rdx, [rbp+arg_0]
0x18002c745  mov     rax, [rcx]
0x18002c748  mov     rax, [rax+0F0h]
0x18002c74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c754  test    byte ptr [rbp+arg_0], 1
0x18002c758  lea     r15, [r13+48h]
0x18002c75c  jz      loc_18002C7E6
0x18002c762  bts     dword ptr [r15], 8
0x18002c767  mov     rcx, rbx; this
0x18002c76a  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18002c76f  mov     rdx, [r14]; struct IRemoteDevice *
0x18002c772  mov     rcx, r13; this
0x18002c775  call    ?IsPOSDevice@CDeviceEntry@@AEAA_NPEAUIRemoteDevice@@@Z; CDeviceEntry::IsPOSDevice(IRemoteDevice *)
0x18002c77a  mov     rcx, rbx; this
0x18002c77d  mov     sil, al
0x18002c780  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002c785  bts     dword ptr [r15], 9
0x18002c78a  test    byte ptr [r13+1Ch], 4
0x18002c78f  jnz     short loc_18002C72D
0x18002c791  test    sil, sil
0x18002c794  jnz     short loc_18002C7E6
0x18002c796  mov     rax, cs:WPP_GLOBAL_Control
0x18002c79d  lea     rbx, WPP_GLOBAL_Control
0x18002c7a4  cmp     rax, rbx
0x18002c7a7  jz      short loc_18002C72D
0x18002c7a9  test    byte ptr [rax+1Ch], 1
0x18002c7ad  jz      loc_18002C72D
0x18002c7b3  cmp     byte ptr [rax+19h], 2
0x18002c7b7  jb      loc_18002C72D
0x18002c7bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7c9  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c7d0  mov     edx, 11h
0x18002c7d5  mov     r9d, eax
0x18002c7d8  mov     rcx, [rcx+10h]
0x18002c7dc  call    WPP_SF_D
0x18002c7e1  jmp     loc_18002C72D
0x18002c7e6  or      dword ptr [r15], 4
0x18002c7ea  xor     esi, esi
0x18002c7ec  mov     [rbp+arg_10], rsi
0x18002c7f0  cmp     [r14], rsi
0x18002c7f3  jz      short loc_18002C815
0x18002c7f5  lea     rcx, [rbp+arg_8]
0x18002c7f9  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002c7fe  mov     rdi, [r14]
0x18002c801  lea     rcx, [rbp+arg_8]
0x18002c805  mov     [rbp+arg_8], rdi
0x18002c809  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002c80e  mov     rsi, rdi
0x18002c811  mov     [rbp+arg_10], rdi
0x18002c815  mov     rcx, rbx; this
0x18002c818  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x18002c81d  mov     rax, [rsi]
0x18002c820  mov     rcx, rsi
0x18002c823  mov     rdx, [r13+78h]
0x18002c827  mov     rax, [rax+0D8h]
0x18002c82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c833  mov     rcx, rbx; this
0x18002c836  mov     esi, eax
0x18002c838  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002c83d  lea     rbx, WPP_GLOBAL_Control
0x18002c844  test    esi, esi
0x18002c846  jns     loc_18002C8EB
0x18002c84c  mov     rax, cs:WPP_GLOBAL_Control
0x18002c853  cmp     rax, rbx
0x18002c856  jz      loc_18002C8EB
0x18002c85c  test    byte ptr [rax+1Ch], 8
0x18002c860  jz      loc_18002C8EB
0x18002c866  cmp     byte ptr [rax+19h], 2
0x18002c86a  jb      short loc_18002C8EB
0x18002c86c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c871  lea     rcx, aCreatepdoFaile; "CreatePDO FAILED"
0x18002c878  mov     [rsp+30h+var_8], esi
0x18002c87c  mov     [rsp+30h+var_10], rcx
0x18002c881  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c888  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c88f  mov     edx, 12h
0x18002c894  mov     r9d, eax
0x18002c897  mov     rcx, [rcx+10h]
0x18002c89b  call    WPP_SF_DsD
0x18002c8a0  mov     eax, [r15]
0x18002c8a3  or      eax, 10h
0x18002c8a6  mov     ecx, esi; dwErrCode
0x18002c8a8  mov     [r15], eax
0x18002c8ab  call    cs:__imp_SetLastError
0x18002c8b1  mov     r8, [r13+60h]
0x18002c8b5  lea     rdx, EVENT_NOTIFY_CREATE_PDO_FAILED
0x18002c8bc  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x18002c8c3  call    ??$RaiseEvent@PEAG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEAG@Z; CrimsonHelper::RaiseEvent<ushort *>(_EVENT_DESCRIPTOR const &,ushort *)
0x18002c8c8  lea     rcx, [rbp+arg_8]
0x18002c8cc  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002c8d1  lea     rcx, [rbp+arg_18]; this
0x18002c8d5  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002c8da  mov     eax, esi
0x18002c8dc  add     rsp, 30h
0x18002c8e0  pop     r15
0x18002c8e2  pop     r14
0x18002c8e4  pop     r13
0x18002c8e6  pop     rdi
0x18002c8e7  pop     rsi
0x18002c8e8  pop     rbx
0x18002c8e9  pop     rbp
0x18002c8ea  retn
0x18002c8eb  mov     eax, [r15]
0x18002c8ee  test    esi, esi
0x18002c8f0  jnz     short loc_18002C8A3
0x18002c8f2  or      eax, 8
0x18002c8f5  test    byte ptr [r13+1Ch], 4
0x18002c8fa  mov     [r15], eax
0x18002c8fd  jz      loc_18002C9BE
0x18002c903  mov     rax, [rbp+arg_10]
0x18002c907  cmp     rax, [r14]
0x18002c90a  jz      short loc_18002C91F
0x18002c90c  mov     rcx, r14
0x18002c90f  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002c914  mov     rcx, r14
0x18002c917  mov     [r14], rdi
0x18002c91a  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002c91f  lea     rcx, [rbp+arg_8]
0x18002c923  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002c928  xor     edi, edi
0x18002c92a  lea     rcx, [rbp+arg_8]
0x18002c92e  mov     [rbp+arg_8], rdi
0x18002c932  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002c937  mov     rcx, r13; this
0x18002c93a  call    ?SyncDestroyPDO@CDeviceEntry@@AEAAJXZ; CDeviceEntry::SyncDestroyPDO(void)
0x18002c93f  mov     esi, eax
0x18002c941  cmp     [r14], rdi
0x18002c944  jz      short loc_18002C959
0x18002c946  mov     rcx, r14
0x18002c949  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002c94e  mov     rcx, r14
0x18002c951  mov     [r14], rdi
0x18002c954  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002c959  test    esi, esi
0x18002c95b  jns     loc_18002C72D
0x18002c961  mov     rax, cs:WPP_GLOBAL_Control
0x18002c968  cmp     rax, rbx
0x18002c96b  jz      loc_18002C8C8
0x18002c971  test    byte ptr [rax+1Ch], 8
0x18002c975  jz      loc_18002C8C8
0x18002c97b  cmp     byte ptr [rax+19h], 2
0x18002c97f  jb      loc_18002C8C8
0x18002c985  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002c98a  lea     rcx, aSyncdestroypdo; "SyncDestroyPDO FAILED"
0x18002c991  mov     [rsp+30h+var_8], esi
0x18002c995  mov     [rsp+30h+var_10], rcx
0x18002c99a  lea     r8, WPP_9f8b2618b856326daa1832c892715ef0_Traceguids
0x18002c9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9a8  mov     edx, 13h
0x18002c9ad  mov     r9d, eax
0x18002c9b0  mov     rcx, [rcx+10h]
0x18002c9b4  call    WPP_SF_DsD
0x18002c9b9  jmp     loc_18002C8C8
0x18002c9be  mov     rcx, r13; Parameter
0x18002c9c1  call    ?StartTimer@CDeviceEntry@@AEAAJXZ; CDeviceEntry::StartTimer(void)
0x18002c9c6  jmp     loc_18002C8C8
```
