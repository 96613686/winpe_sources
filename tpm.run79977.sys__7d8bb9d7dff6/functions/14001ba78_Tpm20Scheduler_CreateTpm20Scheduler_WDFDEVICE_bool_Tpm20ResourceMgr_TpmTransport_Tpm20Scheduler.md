# Tpm20Scheduler::CreateTpm20Scheduler(WDFDEVICE__ *,bool,Tpm20ResourceMgr *,TpmTransport *,Tpm20Scheduler * *)

- ea: `0x14001ba78`
- end: `0x14001bded`
- name: `?CreateTpm20Scheduler@Tpm20Scheduler@@SAJPEAUWDFDEVICE__@@_NPEAVTpm20ResourceMgr@@PEAVTpmTransport@@PEAPEAV1@@Z`
- size: `885`
- prototype: `static int(struct WDFDEVICE__ *, bool, struct Tpm20ResourceMgr *, struct TpmTransport *, struct Tpm20Scheduler **)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001483c`

## callees

- `0x1400104b4`
- `0x14001b88c`
- `0x14001ba24`
- `0x14001ba4c`
- `0x14001ba78`
- `0x1400221f8`
- `0x140039740`
- `0x140039780`
- `0x140039b40`
- `0x140045430`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x14001bcf9`
- `ntoskrnl!RtlGetVersion` at `0x14001bcf9`
- `ntoskrnl!ZwClose` at `0x14001bcd1`
- `ntoskrnl!ZwClose` at `0x14001bcd1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001bcb4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001bcb4`
- `ntoskrnl!PsCreateSystemThread` at `0x14001bc77`
- `ntoskrnl!PsCreateSystemThread` at `0x14001bc77`
- `ntoskrnl!RtlGetProductInfo` at `0x14001bd29`
- `ntoskrnl!RtlGetProductInfo` at `0x14001bd29`

## pseudocode

```c
__int64 __fastcall Tpm20Scheduler::CreateTpm20Scheduler(
        struct WDFDEVICE__ *a1,
        bool a2,
        struct Tpm20ResourceMgr *a3,
        struct TpmTransport *a4,
        struct Tpm20Scheduler **a5)
{
  struct TpmSWAntiHammeringMgr *v8; // rbx
  NTSTATUS v10; // edi
  unsigned __int8 *v11; // rax
  struct _KEVENT *v12; // rax
  Tpm20Scheduler *StartContext; // rax
  Tpm20Scheduler *v14; // rsi
  unsigned int v15; // edx
  unsigned int v16; // edx
  ULONG ReturnedProductType; // [rsp+40h] [rbp-C0h] BYREF
  struct WDFWAITLOCK__ *v19; // [rsp+48h] [rbp-B8h] BYREF
  struct WDFWAITLOCK__ *v20; // [rsp+50h] [rbp-B0h] BYREF
  void *ThreadHandle; // [rsp+58h] [rbp-A8h] BYREF
  PVOID Object; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE VersionInformation[284]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 retaddr; // [rsp+248h] [rbp+148h]

  v20 = 0;
  v19 = 0;
  ReturnedProductType = 0;
  ThreadHandle = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset(VersionInformation, 0, sizeof(VersionInformation));
  v27 = 0;
  v24 = 0;
  v25 = 0x100000001LL;
  v23 = 0;
  LODWORD(v23) = 56;
  v26 = (unsigned __int64)a1;
  v10 = (*((__int64 (__fastcall **)(PKDPC, __int128 *, struct WDFWAITLOCK__ **))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 312))(
          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
          &v23,
          &v19);
  if ( v10 < 0 )
    goto LABEL_15;
  v27 = 0;
  v24 = 0;
  v25 = 0x100000001LL;
  v23 = 0;
  LODWORD(v23) = 56;
  v26 = (unsigned __int64)a1;
  v10 = (*((__int64 (__fastcall **)(PKDPC, __int128 *, struct WDFWAITLOCK__ **))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 312))(
          WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
          &v23,
          &v20);
  if ( v10 < 0 )
    goto LABEL_15;
  v11 = TpmAlloc(1, 0x38u, retaddr);
  v8 = (struct TpmSWAntiHammeringMgr *)v11;
  if ( !v11 )
  {
    v8 = 0;
LABEL_14:
    v10 = -1073741670;
    goto LABEL_15;
  }
  *(_QWORD *)v11 = 0;
  *((_DWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 5) = 0;
  *((_DWORD *)v11 + 12) = 0;
  v10 = TpmSWAntiHammeringMgr::Initialize((TpmSWAntiHammeringMgr *)v11);
  if ( v10 < 0 )
    goto LABEL_15;
  v12 = (struct _KEVENT *)AllocatorBaseNonPaged::operator new(0xC8u);
  if ( !v12 )
    goto LABEL_14;
  StartContext = Tpm20Scheduler::Tpm20Scheduler(v12, a2, v19, v20, v8, a3, a4);
  v14 = StartContext;
  if ( !StartContext )
    goto LABEL_14;
  v19 = 0;
  v20 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = PsCreateSystemThread(
          &ThreadHandle,
          0,
          &ObjectAttributes,
          0,
          0,
          (PKSTART_ROUTINE)Tpm20Scheduler::SchedulerThreadWrapper,
          StartContext);
  if ( v10 < 0 )
  {
    Tpm20Scheduler::`scalar deleting destructor'(v14, v15);
    v8 = 0;
  }
  else
  {
    Object = 0;
    v8 = 0;
    ObReferenceObjectByHandle(ThreadHandle, 0x1FFFFFu, 0, 0, &Object, 0);
    *((_QWORD *)v14 + 21) = Object;
    ZwClose(ThreadHandle);
    memset(&VersionInformation[4], 0, 0x118u);
    *(_DWORD *)VersionInformation = 284;
    if ( RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) >= 0
      && RtlGetProductInfo(
           *(ULONG *)&VersionInformation[4],
           *(ULONG *)&VersionInformation[8],
           *(unsigned __int16 *)&VersionInformation[276],
           *(unsigned __int16 *)&VersionInformation[278],
           &ReturnedProductType) )
    {
      *((_DWORD *)v14 + 45) = ReturnedProductType;
    }
    *a5 = v14;
    v10 = 0;
  }
LABEL_15:
  if ( v19 )
  {
    (*((void (__fastcall **)(PKDPC))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 208))(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
    v19 = 0;
  }
  v16 = (unsigned int)v20;
  if ( v20 )
  {
    (*((void (__fastcall **)(PKDPC))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 208))(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
    v20 = 0;
  }
  if ( v8 )
    TpmSWAntiHammeringMgr::`scalar deleting destructor'(v8, v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001ba78  push    rbp
0x14001ba7a  push    rbx
0x14001ba7b  push    rsi
0x14001ba7c  push    rdi
0x14001ba7d  push    r12
0x14001ba7f  push    r13
0x14001ba81  push    r14
0x14001ba83  push    r15
0x14001ba85  lea     rbp, [rsp-108h]
0x14001ba8d  sub     rsp, 208h
0x14001ba94  mov     rax, cs:__security_cookie
0x14001ba9b  xor     rax, rsp
0x14001ba9e  mov     [rbp+140h+var_50], rax
0x14001baa5  mov     r14, [rbp+140h+arg_20]
0x14001baac  xor     eax, eax
0x14001baae  xorps   xmm0, xmm0
0x14001bab1  mov     [rsp+240h+var_1F0], rax
0x14001bab6  mov     r12, r8
0x14001bab9  mov     [rsp+240h+var_1F8], rax
0x14001babe  mov     r15b, dl
0x14001bac1  mov     [rsp+240h+ReturnedProductType], eax
0x14001bac5  mov     rsi, rcx
0x14001bac8  mov     [rsp+240h+ThreadHandle], rax
0x14001bacd  xor     edx, edx; Val
0x14001bacf  lea     rcx, [rbp+140h+VersionInformation]; void *
0x14001bad3  mov     r8d, 11Ch; Size
0x14001bad9  mov     ebx, eax
0x14001badb  movups  xmmword ptr [rbp+140h+ObjectAttributes.Length], xmm0
0x14001badf  mov     r13, r9
0x14001bae2  movups  xmmword ptr [rbp+140h+ObjectAttributes.ObjectName], xmm0
0x14001bae6  movups  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001baea  call    memset
0x14001baef  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001baf6  lea     r8, [rsp+240h+var_1F8]
0x14001bafb  xor     eax, eax
0x14001bafd  lea     rdx, [rsp+240h+var_1D8]
0x14001bb02  mov     [rbp+140h+var_1A8], rax
0x14001bb06  xorps   xmm0, xmm0
0x14001bb09  movups  [rsp+240h+var_1C8], xmm0
0x14001bb0e  lea     eax, [rbx+1]
0x14001bb11  mov     dword ptr [rbp+140h+var_1C8+8], eax
0x14001bb14  mov     dword ptr [rbp+140h+var_1C8+0Ch], eax
0x14001bb17  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001bb1e  movups  [rsp+240h+var_1D8], xmm0
0x14001bb23  mov     dword ptr [rsp+240h+var_1D8], 38h ; '8'
0x14001bb2b  movups  [rbp+140h+var_1B8], xmm0
0x14001bb2f  mov     qword ptr [rbp+140h+var_1B8], rsi
0x14001bb33  mov     rax, [rax+9C0h]
0x14001bb3a  call    _guard_dispatch_icall
0x14001bb3f  mov     edi, eax
0x14001bb41  test    eax, eax
0x14001bb43  js      loc_14001BD60
0x14001bb49  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001bb50  lea     r8, [rsp+240h+var_1F0]
0x14001bb55  xor     eax, eax
0x14001bb57  lea     rdx, [rsp+240h+var_1D8]
0x14001bb5c  mov     [rbp+140h+var_1A8], rax
0x14001bb60  xorps   xmm0, xmm0
0x14001bb63  movups  [rsp+240h+var_1C8], xmm0
0x14001bb68  lea     eax, [rbx+1]
0x14001bb6b  mov     dword ptr [rbp+140h+var_1C8+8], eax
0x14001bb6e  mov     dword ptr [rbp+140h+var_1C8+0Ch], eax
0x14001bb71  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001bb78  movups  [rsp+240h+var_1D8], xmm0
0x14001bb7d  mov     dword ptr [rsp+240h+var_1D8], 38h ; '8'
0x14001bb85  movups  [rbp+140h+var_1B8], xmm0
0x14001bb89  mov     qword ptr [rbp+140h+var_1B8], rsi
0x14001bb8d  mov     rax, [rax+9C0h]
0x14001bb94  call    _guard_dispatch_icall
0x14001bb99  xor     esi, esi
0x14001bb9b  mov     edi, eax
0x14001bb9d  test    eax, eax
0x14001bb9f  js      loc_14001BD60
0x14001bba5  mov     r8, [rbp+148h]; unsigned __int64
0x14001bbac  lea     edx, [rbx+38h]; unsigned __int64
0x14001bbaf  mov     cl, 1; bool
0x14001bbb1  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14001bbb6  mov     rbx, rax
0x14001bbb9  test    rax, rax
0x14001bbbc  jz      loc_14001BD58
0x14001bbc2  mov     [rax], rsi
0x14001bbc5  mov     rcx, rax; this
0x14001bbc8  mov     [rax+8], esi
0x14001bbcb  mov     [rax+20h], rsi
0x14001bbcf  mov     [rax+28h], rsi
0x14001bbd3  mov     [rax+30h], esi
0x14001bbd6  call    ?Initialize@TpmSWAntiHammeringMgr@@QEAAJXZ; TpmSWAntiHammeringMgr::Initialize(void)
0x14001bbdb  mov     edi, eax
0x14001bbdd  test    eax, eax
0x14001bbdf  js      loc_14001BD60
0x14001bbe5  mov     ecx, 0C8h; Size
0x14001bbea  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x14001bbef  test    rax, rax
0x14001bbf2  jz      loc_14001BD5B
0x14001bbf8  mov     r9, [rsp+240h+var_1F0]; struct WDFWAITLOCK__ *
0x14001bbfd  mov     dl, r15b; bool
0x14001bc00  mov     r8, [rsp+240h+var_1F8]; struct WDFWAITLOCK__ *
0x14001bc05  mov     rcx, rax; Event
0x14001bc08  mov     [rsp+240h+StartContext], r13; struct TpmTransport *
0x14001bc0d  mov     [rsp+240h+StartRoutine], r12; struct Tpm20ResourceMgr *
0x14001bc12  mov     [rsp+240h+ClientId], rbx; struct TpmSWAntiHammeringMgr *
0x14001bc17  call    ??0Tpm20Scheduler@@AEAA@_NPEAUWDFWAITLOCK__@@1PEAVTpmSWAntiHammeringMgr@@PEAVTpm20ResourceMgr@@PEAVTpmTransport@@@Z; Tpm20Scheduler::Tpm20Scheduler(bool,WDFWAITLOCK__ *,WDFWAITLOCK__ *,TpmSWAntiHammeringMgr *,Tpm20ResourceMgr *,TpmTransport *)
0x14001bc1c  xor     r15d, r15d
0x14001bc1f  mov     rsi, rax
0x14001bc22  test    rax, rax
0x14001bc25  jz      loc_14001BD5B
0x14001bc2b  mov     [rsp+240h+StartContext], rax; StartContext
0x14001bc30  lea     r8, [rbp+140h+ObjectAttributes]; ObjectAttributes
0x14001bc34  lea     rax, ?SchedulerThreadWrapper@Tpm20Scheduler@@CAXPEAX@Z; Tpm20Scheduler::SchedulerThreadWrapper(void *)
0x14001bc3b  mov     [rsp+240h+var_1F8], r15
0x14001bc40  xorps   xmm0, xmm0
0x14001bc43  mov     [rsp+240h+StartRoutine], rax; StartRoutine
0x14001bc48  xor     r9d, r9d; ProcessHandle
0x14001bc4b  mov     [rsp+240h+ClientId], r15; ClientId
0x14001bc50  xor     edx, edx; DesiredAccess
0x14001bc52  mov     [rsp+240h+var_1F0], r15
0x14001bc57  lea     rcx, [rsp+240h+ThreadHandle]; ThreadHandle
0x14001bc5c  mov     [rbp+140h+ObjectAttributes.Length], 30h ; '0'
0x14001bc63  mov     [rbp+140h+ObjectAttributes.RootDirectory], r15
0x14001bc67  mov     [rbp+140h+ObjectAttributes.Attributes], 200h
0x14001bc6e  mov     [rbp+140h+ObjectAttributes.ObjectName], r15
0x14001bc72  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001bc77  call    cs:__imp_PsCreateSystemThread
0x14001bc7e  nop     dword ptr [rax+rax+00h]
0x14001bc83  mov     edi, eax
0x14001bc85  test    eax, eax
0x14001bc87  js      loc_14001BD4B
0x14001bc8d  mov     rcx, [rsp+240h+ThreadHandle]; Handle
0x14001bc92  lea     rax, [rsp+240h+Object]
0x14001bc97  mov     [rsp+240h+StartRoutine], r15; HandleInformation
0x14001bc9c  xor     r9d, r9d; AccessMode
0x14001bc9f  xor     r8d, r8d; ObjectType
0x14001bca2  mov     [rsp+240h+ClientId], rax; Object
0x14001bca7  mov     edx, 1FFFFFh; DesiredAccess
0x14001bcac  mov     [rsp+240h+Object], r15
0x14001bcb1  mov     ebx, r15d
0x14001bcb4  call    cs:__imp_ObReferenceObjectByHandle
0x14001bcbb  nop     dword ptr [rax+rax+00h]
0x14001bcc0  mov     rax, [rsp+240h+Object]
0x14001bcc5  mov     [rsi+0A8h], rax
0x14001bccc  mov     rcx, [rsp+240h+ThreadHandle]; Handle
0x14001bcd1  call    cs:__imp_ZwClose
0x14001bcd8  nop     dword ptr [rax+rax+00h]
0x14001bcdd  xor     edx, edx; Val
0x14001bcdf  lea     rcx, [rbp+140h+VersionInformation.dwMajorVersion]; void *
0x14001bce3  mov     r8d, 118h; Size
0x14001bce9  call    memset
0x14001bcee  lea     rcx, [rbp+140h+VersionInformation]; lpVersionInformation
0x14001bcf2  mov     [rbp+140h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14001bcf9  call    cs:__imp_RtlGetVersion
0x14001bd00  nop     dword ptr [rax+rax+00h]
0x14001bd05  test    eax, eax
0x14001bd07  js      short loc_14001BD43
0x14001bd09  movzx   r9d, [rbp+140h+var_5A]; SpMinorVersion
0x14001bd11  lea     rax, [rsp+240h+ReturnedProductType]
0x14001bd16  movzx   r8d, [rbp+140h+var_5C]; SpMajorVersion
0x14001bd1e  mov     edx, [rbp+140h+VersionInformation.dwMinorVersion]; OSMinorVersion
0x14001bd21  mov     ecx, [rbp+140h+VersionInformation.dwMajorVersion]; OSMajorVersion
0x14001bd24  mov     [rsp+240h+ClientId], rax; ReturnedProductType
0x14001bd29  call    cs:__imp_RtlGetProductInfo
0x14001bd30  nop     dword ptr [rax+rax+00h]
0x14001bd35  test    al, al
0x14001bd37  jz      short loc_14001BD43
0x14001bd39  mov     eax, [rsp+240h+ReturnedProductType]
0x14001bd3d  mov     [rsi+0B4h], eax
0x14001bd43  mov     [r14], rsi
0x14001bd46  mov     edi, r15d
0x14001bd49  jmp     short loc_14001BD60
0x14001bd4b  mov     rcx, rsi; this
0x14001bd4e  call    ??_GTpm20Scheduler@@AEAAPEAXI@Z; Tpm20Scheduler::`scalar deleting destructor'(uint)
0x14001bd53  mov     rbx, r15
0x14001bd56  jmp     short loc_14001BD60
0x14001bd58  mov     rbx, rsi
0x14001bd5b  mov     edi, 0C000009Ah
0x14001bd60  mov     rdx, [rsp+240h+var_1F8]
0x14001bd65  test    rdx, rdx
0x14001bd68  jz      short loc_14001BD8D
0x14001bd6a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001bd71  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001bd78  mov     rax, [rax+680h]
0x14001bd7f  call    _guard_dispatch_icall
0x14001bd84  mov     [rsp+240h+var_1F8], 0
0x14001bd8d  mov     rdx, [rsp+240h+var_1F0]
0x14001bd92  test    rdx, rdx
0x14001bd95  jz      short loc_14001BDBA
0x14001bd97  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001bd9e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001bda5  mov     rax, [rax+680h]
0x14001bdac  call    _guard_dispatch_icall
0x14001bdb1  mov     [rsp+240h+var_1F0], 0
0x14001bdba  test    rbx, rbx
0x14001bdbd  jz      short loc_14001BDC7
0x14001bdbf  mov     rcx, rbx; this
0x14001bdc2  call    ??_GTpmSWAntiHammeringMgr@@QEAAPEAXI@Z; TpmSWAntiHammeringMgr::`scalar deleting destructor'(uint)
0x14001bdc7  mov     eax, edi
0x14001bdc9  mov     rcx, [rbp+140h+var_50]
0x14001bdd0  xor     rcx, rsp; StackCookie
0x14001bdd3  call    __security_check_cookie
0x14001bdd8  add     rsp, 208h
0x14001bddf  pop     r15
0x14001bde1  pop     r14
0x14001bde3  pop     r13
0x14001bde5  pop     r12
0x14001bde7  pop     rdi
0x14001bde8  pop     rsi
0x14001bde9  pop     rbx
0x14001bdea  pop     rbp
0x14001bdeb  retn
```
