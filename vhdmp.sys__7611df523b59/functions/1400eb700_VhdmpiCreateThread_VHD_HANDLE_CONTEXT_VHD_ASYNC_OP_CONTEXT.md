# VhdmpiCreateThread(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_CONTEXT *)

- ea: `0x1400eb700`
- end: `0x1400ebb79`
- name: `?VhdmpiCreateThread@@YAXPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_CONTEXT@@@Z`
- size: `1145`
- prototype: `void __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _VHD_ASYNC_OP_CONTEXT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001b7fc`
- `0x14001bc68`
- `0x14001dbb4`
- `0x140023560`
- `0x140029070`
- `0x140033514`
- `0x140035e94`
- `0x14005d7c0`
- `0x1400a1a6c`
- `0x1400e84cc`
- `0x1400eb700`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400eb821`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb9c3`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb821`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb9c3`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eb74a`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eb74a`

## string_xrefs

- `0x1400eb8fb`: `Create`
- `0x1400eba35`: `Create`
- `0x1400eb7e9`: `VhdmpiCreateThread: LUN: 0x%p`
- `0x1400eb82d`: `VhdmpiCreateThread: failed to client (0x%08x)`
- `0x1400eb9fb`: `VhdmpiCreateThread: failed to client (0x%08x)`
- `0x1400eb7f0`: `VhdmpiCreateThread`
- `0x1400eb87e`: `VhdmpiCreateThread`
- `0x1400eba13`: `VhdmpiCreateThread`
- `0x1400eba9c`: `VhdmpiCreateThread`
- `0x1400eba7d`: `VhdmpiCreateThread: LUN: 0x%p returning (0x%08x)`
- `0x1400eb8d8`: `VhdmpiCreateThread: CreateVhd failed (0x%08x)`

## pseudocode

```c
void __fastcall VhdmpiCreateThread(struct _VHD_HANDLE_CONTEXT *a1, struct _VHD_ASYNC_OP_CONTEXT *a2)
{
  __int64 v2; // rsi
  int *v5; // r12
  __int64 v6; // r9
  const wchar_t *v7; // rcx
  int v8; // edx
  void *v9; // rdx
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  char *v12; // r8
  int v13; // ebx
  int v14; // ecx
  char v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // edx
  int v21; // r8d
  __int64 v22; // rcx
  int *v23; // rax
  const wchar_t *v24; // [rsp+40h] [rbp-30h] BYREF
  int *v25; // [rsp+48h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-20h] BYREF
  const GUID *v27; // [rsp+60h] [rbp-10h]

  v2 = *((_QWORD *)a2 + 40);
  v27 = 0;
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v27 = (const GUID *)((char *)a2 + 144);
  v5 = (int *)L"Unknown";
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v7 = L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v7 = (const wchar_t *)*((_QWORD *)a2 + 21);
    v24 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&dword_14007C8AC,
      (__int64)&ActivityId,
      v6,
      &v24);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    TraceEvents((int)"VhdmpiCreateThread", 2105, v8 - 4, v8, "VhdmpiCreateThread: LUN: 0x%p", v2);
  v9 = (void *)*((_QWORD *)a1 + 2);
  if ( !v9 )
    v9 = (void *)*((_QWORD *)a1 + 4);
  v10 = PsImpersonateClient(KeGetCurrentThread(), v9, 0, 0, SecurityDelegation);
  v12 = "VhdmpiCreateThread: failed to client (0x%08x)";
  v13 = v10;
  if ( v10 >= 0 )
  {
    v15 = 1;
    v13 = VhdmpiCreateNewVhd(&ActivityId, a1, a2);
    if ( v13 >= 0 )
    {
      if ( (Microsoft_Windows_VHDMPEnableBits & 8) != 0 )
        McTemplateK0szq_EtwWriteTransfer(
          v14,
          (unsigned int)VhdMetaOpsSuccess,
          (_DWORD)v12,
          (unsigned int)"Create",
          *(_QWORD *)(*(_QWORD *)(v2 + 144) + 120LL),
          0);
      VhdmpiAcquirePassiveLock(VhdmpControlExtension + 192, v11, v12);
      v16 = *(_QWORD *)(v2 + 144);
      v17 = VhdmpControlExtension;
      *(_BYTE *)(v2 + 85) = 0;
      *(_BYTE *)(v16 + 973) = 0;
      VhdmpiReleasePassiveLock(v17 + 192);
      if ( **(_DWORD **)a2 != 2955872 )
      {
        *((_DWORD *)a1 + 1) &= ~4u;
        v18 = *((_QWORD *)a1 + 38);
        if ( v18 )
        {
          *(_BYTE *)(v18 + 5650) = 0;
          *(_BYTE *)(*((_QWORD *)a1 + 38) + 5528LL) = 0;
        }
      }
    }
    else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    {
      TraceEvents((int)"VhdmpiCreateThread", 2129, 2, v11, "VhdmpiCreateThread: CreateVhd failed (0x%08x)", v13);
    }
  }
  else
  {
    v14 = dword_140087708;
    v15 = 0;
    if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      TraceEvents((int)"VhdmpiCreateThread", 2118, 2, v11, v12, v13);
  }
  *((_DWORD *)a2 + 3) = v13;
  if ( v13 < 0 )
  {
    v19 = *((_QWORD *)a1 + 7);
    if ( v19 )
    {
      if ( v19 == v2 )
        VhdmpiBlockVirtualDiskOperations(v2, v11, v12);
    }
  }
  if ( v15 )
  {
    LODWORD(v12) = PsImpersonateClient(KeGetCurrentThread(), 0, 0, 0, SecurityDelegation);
    if ( (int)v12 < 0 )
    {
      v14 = dword_140087708;
      if ( (unsigned int)dword_140087708 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
          TraceEvents(
            (int)"VhdmpiCreateThread",
            2200,
            v20 - 6,
            v20,
            "VhdmpiCreateThread: failed to client (0x%08x)",
            (char)v12);
      }
    }
  }
  if ( v13 < 0 && (Microsoft_Windows_VHDMPEnableBits & 4) != 0 )
    McTemplateK0szq_EtwWriteTransfer(
      v14,
      (unsigned int)VhdMetaOpsError,
      (_DWORD)v12,
      (unsigned int)"Create",
      *(_QWORD *)(*(_QWORD *)(v2 + 144) + 120LL),
      v13);
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    TraceEvents((int)"VhdmpiCreateThread", 2219, 4, v21, "VhdmpiCreateThread: LUN: 0x%p returning (0x%08x)", v2);
  VhdmpiWaitUntilBackingStoreWritesAreFinished(*(_QWORD *)(v2 + 144));
  if ( v13 < 0 && (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    LODWORD(v24) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>();
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 0x10000) )
  {
    v23 = (int *)*((_QWORD *)a2 + 21);
    LODWORD(v24) = v13;
    if ( v23 )
      v5 = v23;
    v25 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned __int8 *)byte_14007C81B,
      &ActivityId,
      v27,
      &v25,
      (__int64)&v24);
  }
}

```

## disassembly

```asm
0x1400eb700  mov     [rsp-28h+arg_10], rbx
0x1400eb705  mov     [rsp-28h+arg_18], rsi
0x1400eb70a  push    rbp
0x1400eb70b  push    rdi
0x1400eb70c  push    r12
0x1400eb70e  push    r14
0x1400eb710  push    r15
0x1400eb712  mov     rbp, rsp
0x1400eb715  sub     rsp, 70h
0x1400eb719  mov     rax, cs:__security_cookie
0x1400eb720  xor     rax, rsp
0x1400eb723  mov     [rbp+var_8], rax
0x1400eb727  mov     rsi, [rdx+140h]
0x1400eb72e  xor     eax, eax
0x1400eb730  mov     r15, rdx
0x1400eb733  mov     [rbp+var_10], rax
0x1400eb737  mov     rdi, rcx
0x1400eb73a  lea     rdx, [rbp+ActivityId]; ActivityId
0x1400eb73e  xorps   xmm0, xmm0
0x1400eb741  lea     ebx, [rax+3]
0x1400eb744  mov     ecx, ebx; ControlCode
0x1400eb746  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1400eb74a  call    cs:__imp_EtwActivityIdControl
0x1400eb751  nop     dword ptr [rax+rax+00h]
0x1400eb756  mov     eax, cs:dword_1400876D0
0x1400eb75c  lea     r9, [r15+90h]
0x1400eb763  mov     [rbp+var_10], r9
0x1400eb767  lea     r12, aUnknown; "Unknown"
0x1400eb76e  cmp     eax, 4
0x1400eb771  jbe     short loc_1400EB7B6
0x1400eb773  mov     edx, 10000h
0x1400eb778  lea     rcx, dword_1400876D0
0x1400eb77f  call    _tlgKeywordOn
0x1400eb784  test    al, al
0x1400eb786  jz      short loc_1400EB7B6
0x1400eb788  mov     rax, [r15+0A8h]
0x1400eb78f  lea     r8, [rbp+ActivityId]
0x1400eb793  test    rax, rax
0x1400eb796  lea     rdx, dword_14007C8AC
0x1400eb79d  mov     rcx, r12
0x1400eb7a0  cmovnz  rcx, rax
0x1400eb7a4  lea     rax, [rbp+var_30]
0x1400eb7a8  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb7ad  mov     [rbp+var_30], rcx
0x1400eb7b1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400eb7b6  mov     eax, cs:dword_140087708
0x1400eb7bc  mov     edx, 8
0x1400eb7c1  cmp     eax, 4
0x1400eb7c4  jbe     short loc_1400EB801
0x1400eb7c6  lea     rcx, dword_140087708
0x1400eb7cd  call    _tlgKeywordOn
0x1400eb7d2  test    al, al
0x1400eb7d4  jz      short loc_1400EB801
0x1400eb7d6  mov     ecx, 839h
0x1400eb7db  mov     qword ptr [rsp+70h+var_48], rsi; char
0x1400eb7e0  mov     r9d, edx; int
0x1400eb7e3  lea     r8d, [rdx-4]; int
0x1400eb7e7  mov     edx, ecx; int
0x1400eb7e9  lea     rax, aVhdmpicreateth_0; "VhdmpiCreateThread: LUN: 0x%p"
0x1400eb7f0  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eb7f7  mov     qword ptr [rsp+70h+ImpersonationLevel], rax; char *
0x1400eb7fc  call    TraceEvents
0x1400eb801  mov     rdx, [rdi+10h]
0x1400eb805  test    rdx, rdx
0x1400eb808  jnz     short loc_1400EB80E
0x1400eb80a  mov     rdx, [rdi+20h]; Token
0x1400eb80e  mov     rcx, gs:188h; Thread
0x1400eb817  xor     r9d, r9d; EffectiveOnly
0x1400eb81a  xor     r8d, r8d; CopyOnOpen
0x1400eb81d  mov     [rsp+70h+ImpersonationLevel], ebx; ImpersonationLevel
0x1400eb821  call    cs:__imp_PsImpersonateClient
0x1400eb828  nop     dword ptr [rax+rax+00h]
0x1400eb82d  lea     r8, aVhdmpicreateth_3; "VhdmpiCreateThread: failed to client (0"...
0x1400eb834  mov     ebx, eax
0x1400eb836  test    eax, eax
0x1400eb838  jns     short loc_1400EB88F
0x1400eb83a  mov     ecx, cs:dword_140087708
0x1400eb840  xor     r14b, r14b
0x1400eb843  cmp     ecx, 2
0x1400eb846  jbe     loc_1400EB987
0x1400eb84c  mov     edx, 8
0x1400eb851  lea     rcx, dword_140087708
0x1400eb858  call    _tlgKeywordOn
0x1400eb85d  test    al, al
0x1400eb85f  jz      loc_1400EB987
0x1400eb865  mov     eax, 846h
0x1400eb86a  mov     dword ptr [rsp+70h+var_48], ebx; char
0x1400eb86e  mov     r9d, edx; int
0x1400eb871  mov     qword ptr [rsp+70h+ImpersonationLevel], r8; char *
0x1400eb876  mov     edx, eax; int
0x1400eb878  mov     r8d, 2; int
0x1400eb87e  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eb885  call    TraceEvents
0x1400eb88a  jmp     loc_1400EB987
0x1400eb88f  mov     r8, r15; struct _VHD_CREATE_CONTEXT *
0x1400eb892  lea     rcx, [rbp+ActivityId]; struct _GUID *
0x1400eb896  mov     rdx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400eb899  mov     r14b, 1
0x1400eb89c  call    ?VhdmpiCreateNewVhd@@YAJAEBU_GUID@@PEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_CREATE_CONTEXT@@@Z; VhdmpiCreateNewVhd(_GUID const &,_VHD_HANDLE_CONTEXT *,_VHD_CREATE_CONTEXT *)
0x1400eb8a1  mov     ebx, eax
0x1400eb8a3  test    eax, eax
0x1400eb8a5  jns     short loc_1400EB8EB
0x1400eb8a7  mov     eax, cs:dword_140087708
0x1400eb8ad  cmp     eax, 2
0x1400eb8b0  jbe     loc_1400EB987
0x1400eb8b6  mov     edx, 8
0x1400eb8bb  lea     rcx, dword_140087708
0x1400eb8c2  call    _tlgKeywordOn
0x1400eb8c7  test    al, al
0x1400eb8c9  jz      loc_1400EB987
0x1400eb8cf  mov     ecx, 851h
0x1400eb8d4  mov     dword ptr [rsp+70h+var_48], ebx
0x1400eb8d8  lea     rax, aVhdmpicreateth_2; "VhdmpiCreateThread: CreateVhd failed (0"...
0x1400eb8df  mov     r9d, edx
0x1400eb8e2  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb8e7  mov     edx, ecx
0x1400eb8e9  jmp     short loc_1400EB878
0x1400eb8eb  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400eb8f2  jz      short loc_1400EB91F
0x1400eb8f4  mov     rax, [rsi+90h]
0x1400eb8fb  lea     r9, aCreate; "Create"
0x1400eb902  mov     dword ptr [rsp+70h+var_48], 0
0x1400eb90a  lea     rdx, VhdMetaOpsSuccess
0x1400eb911  mov     rax, [rax+78h]
0x1400eb915  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb91a  call    McTemplateK0szq_EtwWriteTransfer
0x1400eb91f  mov     rcx, cs:VhdmpControlExtension
0x1400eb926  add     rcx, 0C0h
0x1400eb92d  call    VhdmpiAcquirePassiveLock
0x1400eb932  mov     rax, [rsi+90h]
0x1400eb939  mov     rcx, cs:VhdmpControlExtension
0x1400eb940  mov     byte ptr [rsi+55h], 0
0x1400eb944  add     rcx, 0C0h
0x1400eb94b  mov     byte ptr [rax+3CDh], 0
0x1400eb952  call    VhdmpiReleasePassiveLock
0x1400eb957  mov     rax, [r15]
0x1400eb95a  cmp     dword ptr [rax], 2D1A60h
0x1400eb960  jz      short loc_1400EB987
0x1400eb962  and     dword ptr [rdi+4], 0FFFFFFFBh
0x1400eb966  mov     rax, [rdi+130h]
0x1400eb96d  test    rax, rax
0x1400eb970  jz      short loc_1400EB987
0x1400eb972  mov     byte ptr [rax+1612h], 0
0x1400eb979  mov     rax, [rdi+130h]
0x1400eb980  mov     byte ptr [rax+1598h], 0
0x1400eb987  mov     [r15+0Ch], ebx
0x1400eb98b  test    ebx, ebx
0x1400eb98d  jns     short loc_1400EB9A5
0x1400eb98f  mov     rax, [rdi+38h]
0x1400eb993  test    rax, rax
0x1400eb996  jz      short loc_1400EB9A5
0x1400eb998  cmp     rax, rsi
0x1400eb99b  jnz     short loc_1400EB9A5
0x1400eb99d  mov     rcx, rsi
0x1400eb9a0  call    VhdmpiBlockVirtualDiskOperations
0x1400eb9a5  test    r14b, r14b
0x1400eb9a8  jz      short loc_1400EBA21
0x1400eb9aa  mov     rcx, gs:188h; Thread
0x1400eb9b3  xor     r9d, r9d; EffectiveOnly
0x1400eb9b6  xor     r8d, r8d; CopyOnOpen
0x1400eb9b9  mov     [rsp+70h+ImpersonationLevel], 3; ImpersonationLevel
0x1400eb9c1  xor     edx, edx; Token
0x1400eb9c3  call    cs:__imp_PsImpersonateClient
0x1400eb9ca  nop     dword ptr [rax+rax+00h]
0x1400eb9cf  mov     r8d, eax
0x1400eb9d2  test    eax, eax
0x1400eb9d4  jns     short loc_1400EBA21
0x1400eb9d6  mov     ecx, cs:dword_140087708
0x1400eb9dc  cmp     ecx, 2
0x1400eb9df  jbe     short loc_1400EBA21
0x1400eb9e1  mov     edx, 8
0x1400eb9e6  lea     rcx, dword_140087708
0x1400eb9ed  call    _tlgKeywordOn
0x1400eb9f2  test    al, al
0x1400eb9f4  jz      short loc_1400EBA21
0x1400eb9f6  mov     dword ptr [rsp+70h+var_48], r8d; char
0x1400eb9fb  lea     rcx, aVhdmpicreateth_3; "VhdmpiCreateThread: failed to client (0"...
0x1400eba02  mov     eax, 898h
0x1400eba07  mov     qword ptr [rsp+70h+ImpersonationLevel], rcx; char *
0x1400eba0c  mov     r9d, edx; int
0x1400eba0f  lea     r8d, [rdx-6]; int
0x1400eba13  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eba1a  mov     edx, eax; int
0x1400eba1c  call    TraceEvents
0x1400eba21  test    ebx, ebx
0x1400eba23  jns     short loc_1400EBA55
0x1400eba25  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400eba2c  jz      short loc_1400EBA55
0x1400eba2e  mov     rax, [rsi+90h]
0x1400eba35  lea     r9, aCreate; "Create"
0x1400eba3c  mov     dword ptr [rsp+70h+var_48], ebx
0x1400eba40  lea     rdx, VhdMetaOpsError
0x1400eba47  mov     rax, [rax+78h]
0x1400eba4b  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eba50  call    McTemplateK0szq_EtwWriteTransfer
0x1400eba55  mov     eax, cs:dword_140087708
0x1400eba5b  cmp     eax, 4
0x1400eba5e  jbe     short loc_1400EBAA8
0x1400eba60  mov     r8d, 8
0x1400eba66  lea     rcx, dword_140087708
0x1400eba6d  mov     edx, r8d
0x1400eba70  call    _tlgKeywordOn
0x1400eba75  test    al, al
0x1400eba77  jz      short loc_1400EBAA8
0x1400eba79  mov     [rsp+70h+var_40], ebx
0x1400eba7d  lea     rax, aVhdmpicreateth_1; "VhdmpiCreateThread: LUN: 0x%p returning"...
0x1400eba84  mov     r9d, r8d; int
0x1400eba87  mov     qword ptr [rsp+70h+var_48], rsi; char
0x1400eba8c  mov     r8d, 4; int
0x1400eba92  mov     qword ptr [rsp+70h+ImpersonationLevel], rax; char *
0x1400eba97  mov     edx, 8ABh; int
0x1400eba9c  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400ebaa3  call    TraceEvents
0x1400ebaa8  mov     rcx, [rsi+90h]
0x1400ebaaf  call    VhdmpiWaitUntilBackingStoreWritesAreFinished
0x1400ebab4  test    ebx, ebx
0x1400ebab6  jns     short loc_1400EBAF8
0x1400ebab8  mov     eax, cs:dword_1400876D0
0x1400ebabe  cmp     eax, 2
0x1400ebac1  jbe     short loc_1400EBAF8
0x1400ebac3  mov     edx, 10000h
0x1400ebac8  lea     rcx, dword_1400876D0
0x1400ebacf  call    _tlgKeywordOn
0x1400ebad4  test    al, al
0x1400ebad6  jz      short loc_1400EBAF8
0x1400ebad8  mov     r9, [rbp+var_10]
0x1400ebadc  lea     rax, [rbp+var_30]
0x1400ebae0  lea     r8, [rbp+ActivityId]
0x1400ebae4  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400ebae9  lea     rdx, byte_14007C84F
0x1400ebaf0  mov     dword ptr [rbp+var_30], ebx
0x1400ebaf3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400ebaf8  mov     eax, cs:dword_1400876D0
0x1400ebafe  cmp     eax, 4
0x1400ebb01  jbe     short loc_1400EBB53
0x1400ebb03  mov     edx, 10000h
0x1400ebb08  lea     rcx, dword_1400876D0
0x1400ebb0f  call    _tlgKeywordOn
0x1400ebb14  test    al, al
0x1400ebb16  jz      short loc_1400EBB53
0x1400ebb18  mov     rax, [r15+0A8h]
0x1400ebb1f  lea     r8, [rbp+ActivityId]
0x1400ebb23  mov     r9, [rbp+var_10]
0x1400ebb27  lea     rdx, byte_14007C81B
0x1400ebb2e  test    rax, rax
0x1400ebb31  mov     dword ptr [rbp+var_30], ebx
0x1400ebb34  cmovnz  r12, rax
0x1400ebb38  lea     rax, [rbp+var_30]
0x1400ebb3c  mov     qword ptr [rsp+70h+var_48], rax
0x1400ebb41  lea     rax, [rbp+var_28]
0x1400ebb45  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400ebb4a  mov     [rbp+var_28], r12
0x1400ebb4e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebb53  mov     rcx, [rbp+var_8]
0x1400ebb57  xor     rcx, rsp; StackCookie
0x1400ebb5a  call    __security_check_cookie
0x1400ebb5f  lea     r11, [rsp+70h+var_s0]
0x1400ebb64  mov     rbx, [r11+40h]
0x1400ebb68  mov     rsi, [r11+48h]
0x1400ebb6c  mov     rsp, r11
0x1400ebb6f  pop     r15
0x1400ebb71  pop     r14
0x1400ebb73  pop     r12
0x1400ebb75  pop     rdi
0x1400ebb76  pop     rbp
0x1400ebb77  retn
```
