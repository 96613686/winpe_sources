# ScShutdownServiceProcessCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140003000`
- end: `0x140003308`
- name: `?ScShutdownServiceProcessCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `776`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003000`
- `0x140003310`
- `0x140004c98`
- `0x140005600`
- `0x140005824`
- `0x1400070d0`
- `0x140007130`
- `0x1400188fc`
- `0x140020f3c`
- `0x14006dca4`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140003066`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400030ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400031db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140003066`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400030ae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400031db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000308b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003135`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400031fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000308b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140003135`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400031fb`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x140003026`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x140003026`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400032e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400032e5`
- `ntdll!RtlAcquireResourceExclusive` at `0x140003035`
- `ntdll!RtlAcquireResourceExclusive` at `0x140003035`
- `ntdll!RtlReleaseResource` at `0x1400031ae`
- `ntdll!RtlReleaseResource` at `0x1400031ae`

## pseudocode

```c
void __fastcall ScShutdownServiceProcessCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  int v4; // esi
  PTP_CALLBACK_INSTANCE v5; // rdx
  struct _IMAGE_RECORD *i; // rdi
  CServiceRecord *v7; // rbx
  PRPC_ASYNC_STATE v8; // rcx
  int v9; // edx
  int v10; // r8d
  _QWORD *j; // rbx
  RTL_SRWLOCK *v12; // rdi
  _QWORD v13[11]; // [rsp+80h] [rbp-58h] BYREF
  SmartPtrRef *v14; // [rsp+F8h] [rbp+20h] BYREF

  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(v13);
  v4 = 0;
  CallbackMayRunLong(v5);
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  for ( i = qword_1400BC300; i; i = (struct _IMAGE_RECORD *)*((_QWORD *)i + 2) )
  {
    if ( (*((_DWORD *)i + 26) & 0x30) == 0x20 )
    {
      AcquireSRWLockShared(&stru_1400BB330);
      v7 = xmmword_1400BB320;
      v14 = xmmword_1400BB320;
      if ( xmmword_1400BB320 )
        _InterlockedIncrement((volatile signed __int32 *)xmmword_1400BB320 + 3);
      ReleaseSRWLockShared(&stru_1400BB330);
      while ( v7 )
      {
        if ( (*((_BYTE *)v7 + 80) & 0x30) != 0 )
        {
          AcquireSRWLockShared((PSRWLOCK)v7 + 39);
          if ( (struct _IMAGE_RECORD *)(*(__int64 (__fastcall **)(CServiceRecord *))(*(_QWORD *)v7 + 160LL))(v7) == i
            && ((*((_DWORD *)v7 + 21) - 1) & 0xFFFFFFFD) != 0
            && (*((_BYTE *)v7 + 88) & 4) != 0 )
          {
            if ( (unsigned __int8)utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::push_back(
                                    v13,
                                    &v14) )
            {
              ++v4;
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                WPP_SF_S(
                  WPP_GLOBAL_Control->StubInfo,
                  143,
                  WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                  *((_QWORD *)v14 + 7));
              }
            }
          }
          if ( v7 != (CServiceRecord *)-312LL )
            ReleaseSRWLockShared((PSRWLOCK)v7 + 39);
        }
        CServiceDatabase::GetNext((__int64)v8, &v14);
        v7 = v14;
      }
      Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v14);
      if ( v4 )
      {
        *((_DWORD *)i + 26) |= 0x10u;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x8000) != 0 )
        {
          WPP_SF_SdLd(
            WPP_GLOBAL_Control->StubInfo,
            v9,
            v10,
            *((_QWORD *)i + 3),
            *((_DWORD *)i + 11),
            *((_DWORD *)i + 26),
            v4);
        }
        break;
      }
    }
  }
  RtlReleaseResource(&ScServiceRecordLock);
  for ( j = (_QWORD *)v13[0]; j != v13; j = (_QWORD *)*j )
  {
    v12 = (RTL_SRWLOCK *)j[2];
    AcquireSRWLockShared(v12 + 39);
    ScLogStatusChange((struct CServiceRecord *)v12, &SCMEvt_ServiceStatusChange, 0);
    if ( v12 != (RTL_SRWLOCK *)-312LL )
      ReleaseSRWLockShared(v12 + 39);
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x8000) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 145, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v12[7].Ptr);
    }
    if ( (*((unsigned int (__fastcall **)(RTL_SRWLOCK *, _QWORD, __int64))v12->Ptr + 8))(v12, 0, 5) )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 146, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v12[7].Ptr);
    }
    else
    {
      CServiceRecord::SetStatusFlag((CServiceRecord *)v12, 0x2000u);
    }
  }
  CloseThreadpoolWork(Work);
  utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear((__int64)v13);
}

```

## disassembly

```asm
0x140003000  mov     rax, rsp
0x140003003  push    rbx
0x140003004  push    rbp
0x140003005  push    rsi
0x140003006  push    rdi
0x140003007  push    r12
0x140003009  push    r14
0x14000300b  sub     rsp, 0A8h
0x140003012  mov     rdx, rcx
0x140003015  mov     r14, r8
0x140003018  lea     rcx, [rax-58h]
0x14000301c  call    ??0?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA@XZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>(void)
0x140003021  mov     rcx, rdx; pci
0x140003024  xor     esi, esi
0x140003026  call    cs:__imp_CallbackMayRunLong
0x14000302c  mov     dl, 1; Wait
0x14000302e  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140003035  call    cs:__imp_RtlAcquireResourceExclusive
0x14000303b  mov     rdi, cs:qword_1400BC300
0x140003042  lea     r12, WPP_GLOBAL_Control
0x140003049  test    rdi, rdi
0x14000304c  jz      loc_1400031A7
0x140003052  mov     eax, [rdi+68h]
0x140003055  and     al, 30h
0x140003057  cmp     al, 20h ; ' '
0x140003059  jnz     loc_140003166
0x14000305f  lea     rcx, stru_1400BB330; SRWLock
0x140003066  call    cs:__imp_AcquireSRWLockShared
0x14000306c  mov     rbx, qword ptr cs:xmmword_1400BB320
0x140003073  mov     [rsp+0D8h+arg_18], rbx
0x14000307b  test    rbx, rbx
0x14000307e  jz      short loc_140003084
0x140003080  lock inc dword ptr [rbx+0Ch]
0x140003084  lea     rcx, stru_1400BB330; SRWLock
0x14000308b  call    cs:__imp_ReleaseSRWLockShared
0x140003091  test    rbx, rbx
0x140003094  jz      loc_140003155
0x14000309a  test    byte ptr [rbx+50h], 30h
0x14000309e  jz      loc_14000313B
0x1400030a4  lea     rbp, [rbx+138h]
0x1400030ab  mov     rcx, rbp; SRWLock
0x1400030ae  call    cs:__imp_AcquireSRWLockShared
0x1400030b4  mov     rax, [rbx]
0x1400030b7  mov     rcx, rbx
0x1400030ba  mov     rax, [rax+0A0h]
0x1400030c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030c6  cmp     rax, rdi
0x1400030c9  jnz     short loc_14000312D
0x1400030cb  mov     eax, [rbx+54h]
0x1400030ce  dec     eax
0x1400030d0  test    eax, 0FFFFFFFDh
0x1400030d5  jz      short loc_14000312D
0x1400030d7  test    byte ptr [rbx+58h], 4
0x1400030db  jz      short loc_14000312D
0x1400030dd  lea     rdx, [rsp+0D8h+arg_18]
0x1400030e5  lea     rcx, [rsp+0D8h+var_58]
0x1400030ed  call    ?push_back@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAA_NAEBV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::push_back(Microsoft::WRL::ComPtr<CServiceRecord> const &)
0x1400030f2  test    al, al
0x1400030f4  jnz     short loc_14000312B
0x1400030f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030fd  cmp     rcx, r12
0x140003100  jz      short loc_14000312D
0x140003102  test    byte ptr [rcx+1Ch], 1
0x140003106  jz      short loc_14000312D
0x140003108  mov     r9, [rsp+0D8h+arg_18]
0x140003110  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140003117  mov     rcx, [rcx+10h]
0x14000311b  mov     edx, 8Fh
0x140003120  mov     r9, [r9+38h]
0x140003124  call    WPP_SF_S
0x140003129  jmp     short loc_14000312D
0x14000312b  inc     esi
0x14000312d  test    rbp, rbp
0x140003130  jz      short loc_14000313B
0x140003132  mov     rcx, rbp; SRWLock
0x140003135  call    cs:__imp_ReleaseSRWLockShared
0x14000313b  lea     rdx, [rsp+0D8h+arg_18]
0x140003143  call    ?GetNext@CServiceDatabase@@QEAAXAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z; CServiceDatabase::GetNext(Microsoft::WRL::ComPtr<CServiceRecord> &)
0x140003148  mov     rbx, [rsp+0D8h+arg_18]
0x140003150  jmp     loc_140003091
0x140003155  lea     rcx, [rsp+0D8h+arg_18]
0x14000315d  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140003162  test    esi, esi
0x140003164  jnz     short loc_14000316F
0x140003166  mov     rdi, [rdi+10h]
0x14000316a  jmp     loc_140003049
0x14000316f  or      dword ptr [rdi+68h], 10h
0x140003173  mov     eax, [rdi+68h]
0x140003176  mov     rcx, cs:WPP_GLOBAL_Control
0x14000317d  cmp     rcx, r12
0x140003180  jz      short loc_1400031A7
0x140003182  test    dword ptr [rcx+1Ch], 8000h
0x140003189  jz      short loc_1400031A7
0x14000318b  mov     r9, [rdi+18h]
0x14000318f  mov     rcx, [rcx+10h]
0x140003193  mov     dword ptr [rsp+0D8h+var_A8], esi
0x140003197  mov     [rsp+0D8h+var_B0], eax
0x14000319b  mov     eax, [rdi+2Ch]
0x14000319e  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400031a2  call    WPP_SF_SdLd
0x1400031a7  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400031ae  call    cs:__imp_RtlReleaseResource
0x1400031b4  mov     rbx, [rsp+0D8h+var_58]
0x1400031bc  lea     rax, [rsp+0D8h+var_58]
0x1400031c4  cmp     rbx, rax
0x1400031c7  jz      loc_1400032E2
0x1400031cd  mov     rdi, [rbx+10h]
0x1400031d1  lea     rsi, [rdi+138h]
0x1400031d8  mov     rcx, rsi; SRWLock
0x1400031db  call    cs:__imp_AcquireSRWLockShared
0x1400031e1  xor     r8d, r8d; unsigned __int16 *
0x1400031e4  lea     rdx, SCMEvt_ServiceStatusChange; struct _EVENT_DESCRIPTOR *
0x1400031eb  mov     rcx, rdi; struct CServiceRecord *
0x1400031ee  call    ?ScLogStatusChange@@YAXPEAVCServiceRecord@@PEBU_EVENT_DESCRIPTOR@@PEBG@Z; ScLogStatusChange(CServiceRecord *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1400031f3  test    rsi, rsi
0x1400031f6  jz      short loc_140003201
0x1400031f8  mov     rcx, rsi; SRWLock
0x1400031fb  call    cs:__imp_ReleaseSRWLockShared
0x140003201  mov     rcx, cs:WPP_GLOBAL_Control
0x140003208  cmp     rcx, r12
0x14000320b  jz      short loc_14000322F
0x14000320d  test    dword ptr [rcx+1Ch], 8000h
0x140003214  jz      short loc_14000322F
0x140003216  mov     r9, [rdi+38h]
0x14000321a  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140003221  mov     rcx, [rcx+10h]
0x140003225  mov     edx, 91h
0x14000322a  call    WPP_SF_S
0x14000322f  mov     rax, [rdi]
0x140003232  xor     r9d, r9d
0x140003235  mov     [rsp+0D8h+var_70], 0
0x14000323d  xor     edx, edx
0x14000323f  mov     [rsp+0D8h+var_78], 0
0x140003248  mov     rcx, rdi
0x14000324b  mov     [rsp+0D8h+var_80], 0
0x140003254  mov     rax, [rax+40h]
0x140003258  lea     r8d, [r9+5]
0x14000325c  mov     [rsp+0D8h+var_88], 0
0x140003265  mov     [rsp+0D8h+var_90], 0
0x14000326d  mov     [rsp+0D8h+var_98], 0
0x140003275  mov     [rsp+0D8h+var_A0], 0
0x14000327d  mov     [rsp+0D8h+var_A8], 0
0x140003286  mov     [rsp+0D8h+var_B0], 0
0x14000328e  mov     [rsp+0D8h+var_B8], 0
0x140003297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000329c  test    eax, eax
0x14000329e  jz      short loc_1400032CD
0x1400032a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032a7  cmp     rcx, r12
0x1400032aa  jz      short loc_1400032DA
0x1400032ac  test    byte ptr [rcx+1Ch], 1
0x1400032b0  jz      short loc_1400032DA
0x1400032b2  mov     r9, [rdi+38h]
0x1400032b6  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x1400032bd  mov     rcx, [rcx+10h]
0x1400032c1  mov     edx, 92h
0x1400032c6  call    WPP_SF_S
0x1400032cb  jmp     short loc_1400032DA
0x1400032cd  mov     edx, 2000h; unsigned int
0x1400032d2  mov     rcx, rdi; this
0x1400032d5  call    ?SetStatusFlag@CServiceRecord@@QEAAXK@Z; CServiceRecord::SetStatusFlag(ulong)
0x1400032da  mov     rbx, [rbx]
0x1400032dd  jmp     loc_1400031BC
0x1400032e2  mov     rcx, r14; pwk
0x1400032e5  call    cs:__imp_CloseThreadpoolWork
0x1400032eb  lea     rcx, [rsp+0D8h+var_58]
0x1400032f3  call    ?clear@?$list@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@utl@@@utl@@QEAAXXZ; utl::list<Microsoft::WRL::ComPtr<CServiceRecord>,utl::allocator<Microsoft::WRL::ComPtr<CServiceRecord>>>::clear(void)
0x1400032f8  add     rsp, 0A8h
0x1400032ff  pop     r14
0x140003301  pop     r12
0x140003303  pop     rdi
0x140003304  pop     rsi
0x140003305  pop     rbp
0x140003306  pop     rbx
0x140003307  retn
```
