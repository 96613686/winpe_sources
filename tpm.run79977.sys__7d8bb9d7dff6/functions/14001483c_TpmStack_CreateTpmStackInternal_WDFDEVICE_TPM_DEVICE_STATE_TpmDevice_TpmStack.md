# TpmStack::CreateTpmStackInternal(WDFDEVICE__ *,_TPM_DEVICE_STATE *,TpmDevice *,TpmStack * *)

- ea: `0x14001483c`
- end: `0x140014a2c`
- name: `?CreateTpmStackInternal@TpmStack@@CAJPEAUWDFDEVICE__@@PEAU_TPM_DEVICE_STATE@@PEAVTpmDevice@@PEAPEAV1@@Z`
- size: `496`
- prototype: `__int64 __fastcall(struct WDFDEVICE__ *, struct _TPM_DEVICE_STATE *, struct TpmDevice *, struct TpmStack **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140013da0`

## callees

- `0x14001483c`
- `0x14001a0f4`
- `0x14001a5b8`
- `0x14001b3d0`
- `0x14001ba78`
- `0x14001bdf4`
- `0x14001c38c`
- `0x140022cd8`
- `0x140039780`
- `0x140039b40`

## import_xrefs

- `cng!EntropyUnregisterSource` at `0x140014a05`
- `cng!EntropyUnregisterSource` at `0x140014a05`
- `cng!EntropyRegisterCallback` at `0x1400149a6`
- `cng!EntropyRegisterCallback` at `0x1400149a6`
- `cng!EntropyRegisterSource` at `0x1400148d4`
- `cng!EntropyRegisterSource` at `0x1400148d4`

## pseudocode

```c
__int64 __fastcall TpmStack::CreateTpmStackInternal(
        struct WDFDEVICE__ *a1,
        struct _TPM_DEVICE_STATE *a2,
        struct TpmDevice *a3,
        struct TpmStack **a4)
{
  Tpm20ResourceMgr *v4; // rbx
  struct Tpm20Scheduler *v5; // r14
  int v8; // r12d
  NTSTATUS v9; // esi
  int v10; // eax
  struct TpmTransport *v11; // r15
  int v12; // eax
  unsigned int v13; // edx
  int v14; // eax
  _QWORD *v15; // rdi
  ENTROPY_SOURCE_HANDLE v16; // rcx
  struct Tpm20Scheduler *v18; // [rsp+30h] [rbp-20h] BYREF
  struct Tpm20ResourceMgr *v19; // [rsp+38h] [rbp-18h] BYREF
  struct TpmTransport *v20; // [rsp+40h] [rbp-10h] BYREF
  ENTROPY_SOURCE_HANDLE phEntropySource; // [rsp+98h] [rbp+48h] BYREF
  struct TpmStack **v23; // [rsp+A8h] [rbp+58h]

  v23 = a4;
  v4 = 0;
  phEntropySource = 0;
  v5 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  if ( a2 )
    v8 = *(_DWORD *)a2;
  else
    v8 = TpmStack::ObtainRawModeSettting();
  v9 = TpmTransportType::CreateTpmTransport(a1, v8, &v20);
  if ( v9 < 0 )
  {
    v11 = v20;
    goto LABEL_21;
  }
  v10 = TpmTransportType::m_Version;
  if ( TpmTransportType::m_Version == 1 )
  {
    *((_DWORD *)a3 + 2) = v8;
    *((_DWORD *)a3 + 220) = v8;
  }
  v11 = v20;
  if ( v10 != 2 )
    goto LABEL_11;
  v9 = EntropyRegisterSource(&phEntropySource, ENTROPY_SOURCE_TYPE_HIGH_PULL, L"Microsoft Windows TPM driver");
  if ( v9 < 0 )
    goto LABEL_21;
  v12 = Tpm20ResourceMgr::CreateTpm20ResourceMgr(v11, v8 != 0, &v19);
  v4 = v19;
  v9 = v12;
  if ( v12 < 0 )
    goto LABEL_18;
  v14 = Tpm20Scheduler::CreateTpm20Scheduler(a1, v8 != 0, v19, v11, &v18);
  v5 = v18;
  v9 = v14;
  if ( v14 >= 0 )
  {
LABEL_11:
    v15 = (_QWORD *)(*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                     + 202))(
                      WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                      a1,
                      off_140047018);
    memset(v15, 0, 0x40u);
    if ( v15 )
    {
      v16 = phEntropySource;
      v15[4] = a1;
      v15[3] = v16;
      v15[5] = v11;
      *((_DWORD *)v15 + 12) = v8;
      *v15 = a3;
      v15[1] = v4;
      v15[2] = v5;
    }
    if ( !phEntropySource
      || (v9 = EntropyRegisterCallback(phEntropySource, TpmStack::Entropy20TriggerGathering, v15), v9 >= 0) )
    {
      v11 = 0;
      v4 = 0;
      phEntropySource = 0;
      v5 = 0;
      *v23 = (struct TpmStack *)v15;
    }
  }
  if ( v5 )
    Tpm20Scheduler::DeleteTpm20Scheduler(v5);
LABEL_18:
  if ( v4 )
    Tpm20ResourceMgr::`scalar deleting destructor'(v4, v13);
LABEL_21:
  if ( v11 )
    TpmTransport::DeleteTpmTransport(v11);
  if ( phEntropySource )
    EntropyUnregisterSource(phEntropySource);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14001483c  mov     [rsp-38h+arg_10], rbx
0x140014841  mov     [rsp-38h+arg_18], r9
0x140014846  mov     [rsp-38h+arg_0], rcx
0x14001484b  push    rbp
0x14001484c  push    rsi
0x14001484d  push    rdi
0x14001484e  push    r12
0x140014850  push    r13
0x140014852  push    r14
0x140014854  push    r15
0x140014856  mov     rbp, rsp
0x140014859  sub     rsp, 50h
0x14001485d  xor     ebx, ebx
0x14001485f  mov     [rbp+phEntropySource], 0
0x140014867  xor     r14d, r14d
0x14001486a  mov     [rbp+var_18], rbx
0x14001486e  mov     [rbp+var_20], r14
0x140014872  mov     r13, r8
0x140014875  mov     [rbp+var_10], rbx
0x140014879  mov     rdi, rcx
0x14001487c  test    rdx, rdx
0x14001487f  jnz     short loc_14001488B
0x140014881  call    ?ObtainRawModeSettting@TpmStack@@CAHXZ; TpmStack::ObtainRawModeSettting(void)
0x140014886  mov     r12d, eax
0x140014889  jmp     short loc_14001488E
0x14001488b  mov     r12d, [rdx]
0x14001488e  lea     r8, [rbp+var_10]; struct TpmTransport **
0x140014892  mov     edx, r12d; int
0x140014895  mov     rcx, rdi; struct WDFDEVICE__ *
0x140014898  call    ?CreateTpmTransport@TpmTransportType@@SAJPEAUWDFDEVICE__@@HPEAPEAVTpmTransport@@@Z; TpmTransportType::CreateTpmTransport(WDFDEVICE__ *,int,TpmTransport * *)
0x14001489d  mov     esi, eax
0x14001489f  test    eax, eax
0x1400148a1  js      loc_1400149EB
0x1400148a7  mov     eax, cs:?m_Version@TpmTransportType@@0W4VERSION@1@A; TpmTransportType::VERSION TpmTransportType::m_Version
0x1400148ad  cmp     eax, 1
0x1400148b0  jnz     short loc_1400148BD
0x1400148b2  mov     [r13+8], r12d
0x1400148b6  mov     [r13+370h], r12d
0x1400148bd  mov     r15, [rbp+var_10]
0x1400148c1  cmp     eax, 2
0x1400148c4  jnz     short loc_140014936
0x1400148c6  lea     r8, entropySourceName; "Microsoft Windows TPM driver"
0x1400148cd  lea     edx, [rax+1]; entropySourceType
0x1400148d0  lea     rcx, [rbp+phEntropySource]; phEntropySource
0x1400148d4  call    cs:__imp_EntropyRegisterSource
0x1400148db  nop     dword ptr [rax+rax+00h]
0x1400148e0  mov     esi, eax
0x1400148e2  test    eax, eax
0x1400148e4  js      loc_1400149EF
0x1400148ea  test    r12d, r12d
0x1400148ed  lea     r8, [rbp+var_18]; struct Tpm20ResourceMgr **
0x1400148f1  mov     rcx, r15; struct TpmTransport *
0x1400148f4  setnz   r14b
0x1400148f8  mov     dl, r14b; bool
0x1400148fb  call    ?CreateTpm20ResourceMgr@Tpm20ResourceMgr@@SAJPEAVTpmTransport@@_NPEAPEAV1@@Z; Tpm20ResourceMgr::CreateTpm20ResourceMgr(TpmTransport *,bool,Tpm20ResourceMgr * *)
0x140014900  mov     rbx, [rbp+var_18]
0x140014904  mov     esi, eax
0x140014906  test    eax, eax
0x140014908  js      loc_1400149DC
0x14001490e  lea     rax, [rbp+var_20]
0x140014912  mov     r9, r15; struct TpmTransport *
0x140014915  mov     r8, rbx; struct Tpm20ResourceMgr *
0x140014918  mov     [rsp+50h+var_30], rax; struct Tpm20Scheduler **
0x14001491d  mov     dl, r14b; bool
0x140014920  mov     rcx, rdi; struct WDFDEVICE__ *
0x140014923  call    ?CreateTpm20Scheduler@Tpm20Scheduler@@SAJPEAUWDFDEVICE__@@_NPEAVTpm20ResourceMgr@@PEAVTpmTransport@@PEAPEAV1@@Z; Tpm20Scheduler::CreateTpm20Scheduler(WDFDEVICE__ *,bool,Tpm20ResourceMgr *,TpmTransport *,Tpm20Scheduler * *)
0x140014928  mov     r14, [rbp+var_20]
0x14001492c  mov     esi, eax
0x14001492e  test    eax, eax
0x140014930  js      loc_1400149CF
0x140014936  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001493d  mov     rdx, rdi
0x140014940  mov     r8, cs:off_140047018
0x140014947  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001494e  mov     rax, [rax+650h]
0x140014955  call    _guard_dispatch_icall
0x14001495a  xor     edx, edx; Val
0x14001495c  mov     rcx, rax; void *
0x14001495f  mov     rdi, rax
0x140014962  lea     r8d, [rdx+40h]; Size
0x140014966  call    memset
0x14001496b  test    rdi, rdi
0x14001496e  jz      short loc_140014993
0x140014970  mov     rcx, [rbp+phEntropySource]
0x140014974  mov     rax, [rbp+arg_0]
0x140014978  mov     [rdi+20h], rax
0x14001497c  mov     [rdi+18h], rcx
0x140014980  mov     [rdi+28h], r15
0x140014984  mov     [rdi+30h], r12d
0x140014988  mov     [rdi], r13
0x14001498b  mov     [rdi+8], rbx
0x14001498f  mov     [rdi+10h], r14
0x140014993  mov     rcx, [rbp+phEntropySource]
0x140014997  test    rcx, rcx
0x14001499a  jz      short loc_1400149B8
0x14001499c  mov     r8, rdi
0x14001499f  lea     rdx, ?Entropy20TriggerGathering@TpmStack@@CAJPEAU_ENTROPY_SOURCE_STATE@@PEAX@Z; TpmStack::Entropy20TriggerGathering(_ENTROPY_SOURCE_STATE *,void *)
0x1400149a6  call    cs:__imp_EntropyRegisterCallback
0x1400149ad  nop     dword ptr [rax+rax+00h]
0x1400149b2  mov     esi, eax
0x1400149b4  test    eax, eax
0x1400149b6  js      short loc_1400149CF
0x1400149b8  mov     rax, [rbp+arg_18]
0x1400149bc  xor     r15d, r15d
0x1400149bf  xor     ebx, ebx
0x1400149c1  mov     [rbp+phEntropySource], 0
0x1400149c9  xor     r14d, r14d
0x1400149cc  mov     [rax], rdi
0x1400149cf  test    r14, r14
0x1400149d2  jz      short loc_1400149DC
0x1400149d4  mov     rcx, r14; this
0x1400149d7  call    ?DeleteTpm20Scheduler@Tpm20Scheduler@@SAXPEAV1@@Z; Tpm20Scheduler::DeleteTpm20Scheduler(Tpm20Scheduler *)
0x1400149dc  test    rbx, rbx
0x1400149df  jz      short loc_1400149EF
0x1400149e1  mov     rcx, rbx; this
0x1400149e4  call    ??_GTpm20ResourceMgr@@QEAAPEAXI@Z; Tpm20ResourceMgr::`scalar deleting destructor'(uint)
0x1400149e9  jmp     short loc_1400149EF
0x1400149eb  mov     r15, [rbp+var_10]
0x1400149ef  test    r15, r15
0x1400149f2  jz      short loc_1400149FC
0x1400149f4  mov     rcx, r15; struct TpmTransport *
0x1400149f7  call    ?DeleteTpmTransport@TpmTransport@@SAXPEAV1@@Z; TpmTransport::DeleteTpmTransport(TpmTransport *)
0x1400149fc  mov     rcx, [rbp+phEntropySource]; hEntropySource
0x140014a00  test    rcx, rcx
0x140014a03  jz      short loc_140014A11
0x140014a05  call    cs:__imp_EntropyUnregisterSource
0x140014a0c  nop     dword ptr [rax+rax+00h]
0x140014a11  mov     rbx, [rsp+50h+arg_10]
0x140014a19  mov     eax, esi
0x140014a1b  add     rsp, 50h
0x140014a1f  pop     r15
0x140014a21  pop     r14
0x140014a23  pop     r13
0x140014a25  pop     r12
0x140014a27  pop     rdi
0x140014a28  pop     rsi
0x140014a29  pop     rbp
0x140014a2a  retn
```
