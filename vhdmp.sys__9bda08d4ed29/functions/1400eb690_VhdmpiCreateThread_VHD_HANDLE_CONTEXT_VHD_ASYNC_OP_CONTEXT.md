# VhdmpiCreateThread(_VHD_HANDLE_CONTEXT *,_VHD_ASYNC_OP_CONTEXT *)

- ea: `0x1400eb690`
- end: `0x1400ebb09`
- name: `?VhdmpiCreateThread@@YAXPEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_ASYNC_OP_CONTEXT@@@Z`
- size: `1145`
- prototype: `void __fastcall(struct _VHD_HANDLE_CONTEXT *, struct _VHD_ASYNC_OP_CONTEXT *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400010d0`
- `0x140001130`
- `0x14001bc1c`
- `0x14001c088`
- `0x14001dfd4`
- `0x140023980`
- `0x140029590`
- `0x1400339d4`
- `0x140036284`
- `0x14005dbb0`
- `0x1400a1a6c`
- `0x1400e845c`
- `0x1400eb690`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x1400eb7b1`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb953`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb7b1`
- `ntoskrnl!PsImpersonateClient` at `0x1400eb953`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eb6da`
- `ntoskrnl!EtwActivityIdControl` at `0x1400eb6da`

## string_xrefs

- `0x1400eb88b`: `Create`
- `0x1400eb9c5`: `Create`
- `0x1400eb780`: `VhdmpiCreateThread`
- `0x1400eb80e`: `VhdmpiCreateThread`
- `0x1400eb9a3`: `VhdmpiCreateThread`
- `0x1400eba2c`: `VhdmpiCreateThread`
- `0x1400eb779`: `VhdmpiCreateThread: LUN: 0x%p`
- `0x1400eb868`: `VhdmpiCreateThread: CreateVhd failed (0x%08x)`
- `0x1400eb7bd`: `VhdmpiCreateThread: failed to client (0x%08x)`
- `0x1400eb98b`: `VhdmpiCreateThread: failed to client (0x%08x)`
- `0x1400eba0d`: `VhdmpiCreateThread: LUN: 0x%p returning (0x%08x)`

## pseudocode

```c
void __fastcall VhdmpiCreateThread(struct _VHD_HANDLE_CONTEXT *a1, struct _VHD_ASYNC_OP_CONTEXT *a2)
{
  __int64 v2; // rsi
  const wchar_t *v5; // r12
  int v6; // r9d
  const wchar_t *v7; // rcx
  unsigned int v8; // edx
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
  NTSTATUS v20; // eax
  int v21; // ecx
  int v22; // ecx
  const wchar_t *v23; // rax
  char v24[8]; // [rsp+28h] [rbp-48h]
  const wchar_t *v25; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v26; // [rsp+48h] [rbp-28h] BYREF
  GUID ActivityId; // [rsp+50h] [rbp-20h] BYREF
  char *v28; // [rsp+60h] [rbp-10h]

  v2 = *((_QWORD *)a2 + 40);
  v28 = 0;
  ActivityId = 0;
  EtwActivityIdControl(3u, &ActivityId);
  v28 = (char *)a2 + 144;
  v5 = L"Unknown";
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v7 = L"Unknown";
    if ( *((_QWORD *)a2 + 21) )
      v7 = (const wchar_t *)*((_QWORD *)a2 + 21);
    v25 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&byte_14007C877,
      (unsigned int)&ActivityId,
      v6,
      (__int64)&v25);
  }
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents("VhdmpiCreateThread", 0x839u, v8 - 4, v8, "VhdmpiCreateThread: LUN: 0x%p", (const void *)v2);
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
      VhdmpiAcquirePassiveLock(VhdmpControlExtension + 192);
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
    else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    {
      *(_DWORD *)v24 = v13;
      TraceEvents(
        "VhdmpiCreateThread",
        0x851u,
        2u,
        v11,
        "VhdmpiCreateThread: CreateVhd failed (0x%08x)",
        *(_QWORD *)v24);
    }
  }
  else
  {
    v14 = dword_1400876D0;
    v15 = 0;
    if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    {
      *(_DWORD *)v24 = v13;
      TraceEvents("VhdmpiCreateThread", 0x846u, 2u, v11, v12, *(_QWORD *)v24);
    }
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
    v20 = PsImpersonateClient(KeGetCurrentThread(), 0, 0, 0, SecurityDelegation);
    v12 = (char *)(unsigned int)v20;
    if ( v20 < 0 )
    {
      v14 = dword_1400876D0;
      if ( (unsigned int)dword_1400876D0 > 2 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
          TraceEvents(
            "VhdmpiCreateThread",
            0x898u,
            v11 - 6,
            v11,
            "VhdmpiCreateThread: failed to client (0x%08x)",
            (_DWORD)v12);
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
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    TraceEvents(
      "VhdmpiCreateThread",
      0x8ABu,
      4u,
      (unsigned int)v12,
      "VhdmpiCreateThread: LUN: 0x%p returning (0x%08x)",
      (const void *)v2,
      v13);
  VhdmpiWaitUntilBackingStoreWritesAreFinished(*(_QWORD *)(v2 + 144), v11, v12);
  if ( v13 < 0 && (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    LODWORD(v25) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_14007C81B,
      (unsigned int)&ActivityId,
      (_DWORD)v28,
      (__int64)&v25);
  }
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 0x10000) )
  {
    v23 = (const wchar_t *)*((_QWORD *)a2 + 21);
    LODWORD(v25) = v13;
    if ( v23 )
      v5 = v23;
    v26 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)byte_14007C843,
      (unsigned int)&ActivityId,
      (_DWORD)v28,
      (__int64)&v26,
      (__int64)&v25);
  }
}

```

## disassembly

```asm
0x1400eb690  mov     [rsp-28h+arg_10], rbx
0x1400eb695  mov     [rsp-28h+arg_18], rsi
0x1400eb69a  push    rbp
0x1400eb69b  push    rdi
0x1400eb69c  push    r12
0x1400eb69e  push    r14
0x1400eb6a0  push    r15
0x1400eb6a2  mov     rbp, rsp
0x1400eb6a5  sub     rsp, 70h
0x1400eb6a9  mov     rax, cs:__security_cookie
0x1400eb6b0  xor     rax, rsp
0x1400eb6b3  mov     [rbp+var_8], rax
0x1400eb6b7  mov     rsi, [rdx+140h]
0x1400eb6be  xor     eax, eax
0x1400eb6c0  mov     r15, rdx
0x1400eb6c3  mov     [rbp+var_10], rax
0x1400eb6c7  mov     rdi, rcx
0x1400eb6ca  lea     rdx, [rbp+ActivityId]; ActivityId
0x1400eb6ce  xorps   xmm0, xmm0
0x1400eb6d1  lea     ebx, [rax+3]
0x1400eb6d4  mov     ecx, ebx; ControlCode
0x1400eb6d6  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1400eb6da  call    cs:__imp_EtwActivityIdControl
0x1400eb6e1  nop     dword ptr [rax+rax+00h]
0x1400eb6e6  mov     eax, cs:dword_140087708
0x1400eb6ec  lea     r9, [r15+90h]
0x1400eb6f3  mov     [rbp+var_10], r9
0x1400eb6f7  lea     r12, aUnknown; "Unknown"
0x1400eb6fe  cmp     eax, 4
0x1400eb701  jbe     short loc_1400EB746
0x1400eb703  mov     edx, 10000h
0x1400eb708  lea     rcx, dword_140087708
0x1400eb70f  call    _tlgKeywordOn
0x1400eb714  test    al, al
0x1400eb716  jz      short loc_1400EB746
0x1400eb718  mov     rax, [r15+0A8h]
0x1400eb71f  lea     r8, [rbp+ActivityId]
0x1400eb723  test    rax, rax
0x1400eb726  lea     rdx, byte_14007C877
0x1400eb72d  mov     rcx, r12
0x1400eb730  cmovnz  rcx, rax
0x1400eb734  lea     rax, [rbp+var_30]
0x1400eb738  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb73d  mov     [rbp+var_30], rcx
0x1400eb741  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400eb746  mov     eax, cs:dword_1400876D0
0x1400eb74c  mov     edx, 8
0x1400eb751  cmp     eax, 4
0x1400eb754  jbe     short loc_1400EB791
0x1400eb756  lea     rcx, dword_1400876D0
0x1400eb75d  call    _tlgKeywordOn
0x1400eb762  test    al, al
0x1400eb764  jz      short loc_1400EB791
0x1400eb766  mov     ecx, 839h
0x1400eb76b  mov     qword ptr [rsp+70h+var_48], rsi; char
0x1400eb770  mov     r9d, edx; int
0x1400eb773  lea     r8d, [rdx-4]; int
0x1400eb777  mov     edx, ecx; int
0x1400eb779  lea     rax, aVhdmpicreateth_0; "VhdmpiCreateThread: LUN: 0x%p"
0x1400eb780  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eb787  mov     qword ptr [rsp+70h+ImpersonationLevel], rax; char *
0x1400eb78c  call    TraceEvents
0x1400eb791  mov     rdx, [rdi+10h]
0x1400eb795  test    rdx, rdx
0x1400eb798  jnz     short loc_1400EB79E
0x1400eb79a  mov     rdx, [rdi+20h]; Token
0x1400eb79e  mov     rcx, gs:188h; Thread
0x1400eb7a7  xor     r9d, r9d; EffectiveOnly
0x1400eb7aa  xor     r8d, r8d; CopyOnOpen
0x1400eb7ad  mov     [rsp+70h+ImpersonationLevel], ebx; ImpersonationLevel
0x1400eb7b1  call    cs:__imp_PsImpersonateClient
0x1400eb7b8  nop     dword ptr [rax+rax+00h]
0x1400eb7bd  lea     r8, aVhdmpicreateth_3; "VhdmpiCreateThread: failed to client (0"...
0x1400eb7c4  mov     ebx, eax
0x1400eb7c6  test    eax, eax
0x1400eb7c8  jns     short loc_1400EB81F
0x1400eb7ca  mov     ecx, cs:dword_1400876D0
0x1400eb7d0  xor     r14b, r14b
0x1400eb7d3  cmp     ecx, 2
0x1400eb7d6  jbe     loc_1400EB917
0x1400eb7dc  mov     edx, 8
0x1400eb7e1  lea     rcx, dword_1400876D0
0x1400eb7e8  call    _tlgKeywordOn
0x1400eb7ed  test    al, al
0x1400eb7ef  jz      loc_1400EB917
0x1400eb7f5  mov     eax, 846h
0x1400eb7fa  mov     dword ptr [rsp+70h+var_48], ebx; char
0x1400eb7fe  mov     r9d, edx; int
0x1400eb801  mov     qword ptr [rsp+70h+ImpersonationLevel], r8; char *
0x1400eb806  mov     edx, eax; int
0x1400eb808  mov     r8d, 2; int
0x1400eb80e  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eb815  call    TraceEvents
0x1400eb81a  jmp     loc_1400EB917
0x1400eb81f  mov     r8, r15; struct _VHD_CREATE_CONTEXT *
0x1400eb822  lea     rcx, [rbp+ActivityId]; struct _GUID *
0x1400eb826  mov     rdx, rdi; struct _VHD_HANDLE_CONTEXT *
0x1400eb829  mov     r14b, 1
0x1400eb82c  call    ?VhdmpiCreateNewVhd@@YAJAEBU_GUID@@PEAU_VHD_HANDLE_CONTEXT@@PEAU_VHD_CREATE_CONTEXT@@@Z; VhdmpiCreateNewVhd(_GUID const &,_VHD_HANDLE_CONTEXT *,_VHD_CREATE_CONTEXT *)
0x1400eb831  mov     ebx, eax
0x1400eb833  test    eax, eax
0x1400eb835  jns     short loc_1400EB87B
0x1400eb837  mov     eax, cs:dword_1400876D0
0x1400eb83d  cmp     eax, 2
0x1400eb840  jbe     loc_1400EB917
0x1400eb846  mov     edx, 8
0x1400eb84b  lea     rcx, dword_1400876D0
0x1400eb852  call    _tlgKeywordOn
0x1400eb857  test    al, al
0x1400eb859  jz      loc_1400EB917
0x1400eb85f  mov     ecx, 851h
0x1400eb864  mov     dword ptr [rsp+70h+var_48], ebx
0x1400eb868  lea     rax, aVhdmpicreateth_2; "VhdmpiCreateThread: CreateVhd failed (0"...
0x1400eb86f  mov     r9d, edx
0x1400eb872  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb877  mov     edx, ecx
0x1400eb879  jmp     short loc_1400EB808
0x1400eb87b  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 8
0x1400eb882  jz      short loc_1400EB8AF
0x1400eb884  mov     rax, [rsi+90h]
0x1400eb88b  lea     r9, aCreate; "Create"
0x1400eb892  mov     dword ptr [rsp+70h+var_48], 0
0x1400eb89a  lea     rdx, VhdMetaOpsSuccess
0x1400eb8a1  mov     rax, [rax+78h]
0x1400eb8a5  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb8aa  call    McTemplateK0szq_EtwWriteTransfer
0x1400eb8af  mov     rcx, cs:VhdmpControlExtension
0x1400eb8b6  add     rcx, 0C0h
0x1400eb8bd  call    VhdmpiAcquirePassiveLock
0x1400eb8c2  mov     rax, [rsi+90h]
0x1400eb8c9  mov     rcx, cs:VhdmpControlExtension
0x1400eb8d0  mov     byte ptr [rsi+55h], 0
0x1400eb8d4  add     rcx, 0C0h
0x1400eb8db  mov     byte ptr [rax+3CDh], 0
0x1400eb8e2  call    VhdmpiReleasePassiveLock
0x1400eb8e7  mov     rax, [r15]
0x1400eb8ea  cmp     dword ptr [rax], 2D1A60h
0x1400eb8f0  jz      short loc_1400EB917
0x1400eb8f2  and     dword ptr [rdi+4], 0FFFFFFFBh
0x1400eb8f6  mov     rax, [rdi+130h]
0x1400eb8fd  test    rax, rax
0x1400eb900  jz      short loc_1400EB917
0x1400eb902  mov     byte ptr [rax+1612h], 0
0x1400eb909  mov     rax, [rdi+130h]
0x1400eb910  mov     byte ptr [rax+1598h], 0
0x1400eb917  mov     [r15+0Ch], ebx
0x1400eb91b  test    ebx, ebx
0x1400eb91d  jns     short loc_1400EB935
0x1400eb91f  mov     rax, [rdi+38h]
0x1400eb923  test    rax, rax
0x1400eb926  jz      short loc_1400EB935
0x1400eb928  cmp     rax, rsi
0x1400eb92b  jnz     short loc_1400EB935
0x1400eb92d  mov     rcx, rsi
0x1400eb930  call    VhdmpiBlockVirtualDiskOperations
0x1400eb935  test    r14b, r14b
0x1400eb938  jz      short loc_1400EB9B1
0x1400eb93a  mov     rcx, gs:188h; Thread
0x1400eb943  xor     r9d, r9d; EffectiveOnly
0x1400eb946  xor     r8d, r8d; CopyOnOpen
0x1400eb949  mov     [rsp+70h+ImpersonationLevel], 3; ImpersonationLevel
0x1400eb951  xor     edx, edx; Token
0x1400eb953  call    cs:__imp_PsImpersonateClient
0x1400eb95a  nop     dword ptr [rax+rax+00h]
0x1400eb95f  mov     r8d, eax
0x1400eb962  test    eax, eax
0x1400eb964  jns     short loc_1400EB9B1
0x1400eb966  mov     ecx, cs:dword_1400876D0
0x1400eb96c  cmp     ecx, 2
0x1400eb96f  jbe     short loc_1400EB9B1
0x1400eb971  mov     edx, 8
0x1400eb976  lea     rcx, dword_1400876D0
0x1400eb97d  call    _tlgKeywordOn
0x1400eb982  test    al, al
0x1400eb984  jz      short loc_1400EB9B1
0x1400eb986  mov     dword ptr [rsp+70h+var_48], r8d; char
0x1400eb98b  lea     rcx, aVhdmpicreateth_3; "VhdmpiCreateThread: failed to client (0"...
0x1400eb992  mov     eax, 898h
0x1400eb997  mov     qword ptr [rsp+70h+ImpersonationLevel], rcx; char *
0x1400eb99c  mov     r9d, edx; int
0x1400eb99f  lea     r8d, [rdx-6]; int
0x1400eb9a3  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eb9aa  mov     edx, eax; int
0x1400eb9ac  call    TraceEvents
0x1400eb9b1  test    ebx, ebx
0x1400eb9b3  jns     short loc_1400EB9E5
0x1400eb9b5  test    byte ptr cs:Microsoft_Windows_VHDMPEnableBits, 4
0x1400eb9bc  jz      short loc_1400EB9E5
0x1400eb9be  mov     rax, [rsi+90h]
0x1400eb9c5  lea     r9, aCreate; "Create"
0x1400eb9cc  mov     dword ptr [rsp+70h+var_48], ebx
0x1400eb9d0  lea     rdx, VhdMetaOpsError
0x1400eb9d7  mov     rax, [rax+78h]
0x1400eb9db  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eb9e0  call    McTemplateK0szq_EtwWriteTransfer
0x1400eb9e5  mov     eax, cs:dword_1400876D0
0x1400eb9eb  cmp     eax, 4
0x1400eb9ee  jbe     short loc_1400EBA38
0x1400eb9f0  mov     r8d, 8
0x1400eb9f6  lea     rcx, dword_1400876D0
0x1400eb9fd  mov     edx, r8d
0x1400eba00  call    _tlgKeywordOn
0x1400eba05  test    al, al
0x1400eba07  jz      short loc_1400EBA38
0x1400eba09  mov     [rsp+70h+var_40], ebx
0x1400eba0d  lea     rax, aVhdmpicreateth_1; "VhdmpiCreateThread: LUN: 0x%p returning"...
0x1400eba14  mov     r9d, r8d; int
0x1400eba17  mov     qword ptr [rsp+70h+var_48], rsi; char
0x1400eba1c  mov     r8d, 4; int
0x1400eba22  mov     qword ptr [rsp+70h+ImpersonationLevel], rax; char *
0x1400eba27  mov     edx, 8ABh; int
0x1400eba2c  lea     rcx, aVhdmpicreateth; "VhdmpiCreateThread"
0x1400eba33  call    TraceEvents
0x1400eba38  mov     rcx, [rsi+90h]
0x1400eba3f  call    VhdmpiWaitUntilBackingStoreWritesAreFinished
0x1400eba44  test    ebx, ebx
0x1400eba46  jns     short loc_1400EBA88
0x1400eba48  mov     eax, cs:dword_140087708
0x1400eba4e  cmp     eax, 2
0x1400eba51  jbe     short loc_1400EBA88
0x1400eba53  mov     edx, 10000h
0x1400eba58  lea     rcx, dword_140087708
0x1400eba5f  call    _tlgKeywordOn
0x1400eba64  test    al, al
0x1400eba66  jz      short loc_1400EBA88
0x1400eba68  mov     r9, [rbp+var_10]
0x1400eba6c  lea     rax, [rbp+var_30]
0x1400eba70  lea     r8, [rbp+ActivityId]
0x1400eba74  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400eba79  lea     rdx, byte_14007C81B
0x1400eba80  mov     dword ptr [rbp+var_30], ebx
0x1400eba83  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1400eba88  mov     eax, cs:dword_140087708
0x1400eba8e  cmp     eax, 4
0x1400eba91  jbe     short loc_1400EBAE3
0x1400eba93  mov     edx, 10000h
0x1400eba98  lea     rcx, dword_140087708
0x1400eba9f  call    _tlgKeywordOn
0x1400ebaa4  test    al, al
0x1400ebaa6  jz      short loc_1400EBAE3
0x1400ebaa8  mov     rax, [r15+0A8h]
0x1400ebaaf  lea     r8, [rbp+ActivityId]
0x1400ebab3  mov     r9, [rbp+var_10]
0x1400ebab7  lea     rdx, byte_14007C843
0x1400ebabe  test    rax, rax
0x1400ebac1  mov     dword ptr [rbp+var_30], ebx
0x1400ebac4  cmovnz  r12, rax
0x1400ebac8  lea     rax, [rbp+var_30]
0x1400ebacc  mov     qword ptr [rsp+70h+var_48], rax
0x1400ebad1  lea     rax, [rbp+var_28]
0x1400ebad5  mov     qword ptr [rsp+70h+ImpersonationLevel], rax
0x1400ebada  mov     [rbp+var_28], r12
0x1400ebade  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400ebae3  mov     rcx, [rbp+var_8]
0x1400ebae7  xor     rcx, rsp; StackCookie
0x1400ebaea  call    __security_check_cookie
0x1400ebaef  lea     r11, [rsp+70h+var_s0]
0x1400ebaf4  mov     rbx, [r11+40h]
0x1400ebaf8  mov     rsi, [r11+48h]
0x1400ebafc  mov     rsp, r11
0x1400ebaff  pop     r15
0x1400ebb01  pop     r14
0x1400ebb03  pop     r12
0x1400ebb05  pop     rdi
0x1400ebb06  pop     rbp
0x1400ebb07  retn
```
