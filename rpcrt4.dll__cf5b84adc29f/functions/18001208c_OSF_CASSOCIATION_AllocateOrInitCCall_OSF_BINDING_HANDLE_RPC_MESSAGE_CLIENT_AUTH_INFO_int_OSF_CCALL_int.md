# OSF_CASSOCIATION::AllocateOrInitCCall(OSF_BINDING_HANDLE *,_RPC_MESSAGE *,CLIENT_AUTH_INFO *,int,OSF_CCALL * *,int *)

- ea: `0x18001208c`
- end: `0x180012b85`
- name: `?AllocateOrInitCCall@OSF_CASSOCIATION@@QEAAJPEAVOSF_BINDING_HANDLE@@PEAU_RPC_MESSAGE@@PEAUCLIENT_AUTH_INFO@@HPEAPEAVOSF_CCALL@@PEAH@Z`
- size: `2809`
- prototype: `__int64 __fastcall(OSF_CASSOCIATION *this, struct OSF_BINDING_HANDLE *, struct _RPC_MESSAGE *, struct CLIENT_AUTH_INFO *, int, struct OSF_CCALL **, int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b127c`

## callees

- `0x18000fd70`
- `0x180011d80`
- `0x18001208c`
- `0x180012b8c`
- `0x180012bf0`
- `0x180012f68`
- `0x1800131cc`
- `0x180013244`
- `0x180013958`
- `0x180014230`
- `0x180014414`
- `0x180014c1c`
- `0x180016600`
- `0x180022e80`
- `0x180023020`
- `0x18002cab0`
- `0x18005bed4`
- `0x18005d198`
- `0x1800618dc`
- `0x1800661c8`
- `0x180066c10`
- `0x180068e80`
- `0x18006998c`
- `0x18006a050`
- `0x18006e470`
- `0x180093410`
- `0x1800936d8`
- `0x1800966dc`
- `0x1800970ac`
- `0x1800a26ac`
- `0x1800af070`
- `0x1800cec85`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800122fb`
- `ntdll!RtlLeaveCriticalSection` at `0x180012477`
- `ntdll!RtlLeaveCriticalSection` at `0x18001257c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800126b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800127be`
- `ntdll!RtlLeaveCriticalSection` at `0x180012b04`
- `ntdll!RtlLeaveCriticalSection` at `0x1800122fb`
- `ntdll!RtlLeaveCriticalSection` at `0x180012477`
- `ntdll!RtlLeaveCriticalSection` at `0x18001257c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800126b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800127be`
- `ntdll!RtlLeaveCriticalSection` at `0x180012b04`
- `ntdll!RtlEnterCriticalSection` at `0x1800120fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800128ea`
- `ntdll!RtlEnterCriticalSection` at `0x180012acd`
- `ntdll!RtlEnterCriticalSection` at `0x1800120fe`
- `ntdll!RtlEnterCriticalSection` at `0x1800128ea`
- `ntdll!RtlEnterCriticalSection` at `0x180012acd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001221c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001221c`

## pseudocode

```c
__int64 __fastcall OSF_CASSOCIATION::AllocateOrInitCCall(
        OSF_CASSOCIATION *this,
        struct OSF_BINDING_HANDLE *a2,
        struct _RPC_MESSAGE *a3,
        struct CLIENT_AUTH_INFO *a4,
        int a5,
        struct OSF_CCALL **a6,
        int *a7)
{
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  unsigned int RpcFlags; // esi
  struct OSF_BINDING *v9; // r12
  struct _RPC_CLIENT_INTERFACE *RpcInterfaceInformation; // rbx
  struct OSF_CCONNECTION *v11; // r15
  struct OSF_BINDING_HANDLE *v13; // r13
  unsigned int CCall; // ebx
  int v15; // esi
  int v16; // edi
  struct OSF_CCALL **v17; // r14
  int v18; // ebx
  struct _RPC_MESSAGE *v19; // r15
  int v20; // r13d
  struct MTSyntaxBinding *v21; // rsi
  _DWORD *v22; // r8
  int v23; // ecx
  struct MTSyntaxBinding *v24; // rax
  OSF_CCALL **v25; // rsi
  DWORD CurrentThreadId; // ebx
  unsigned int v27; // ecx
  REFERENCED_OBJECT *v28; // rdi
  int v29; // edi
  struct MTSyntaxBinding *v30; // rbx
  __int64 v31; // r14
  bool v32; // zf
  unsigned int v33; // eax
  __int64 v35; // r14
  struct MTSyntaxBinding *v36; // r13
  unsigned int *v37; // r14
  int v38; // r15d
  int v39; // eax
  CALL *v40; // rcx
  OSF_CCALL *v41; // rcx
  unsigned int v42; // eax
  int v43; // eax
  __int64 v44; // rax
  OSF_BINDING *i; // r14
  signed __int32 v46; // eax
  struct OSF_CCALL *v47; // r14
  struct OSF_BINDING *v48; // rdx
  struct OSF_BINDING *v49; // rdx
  OSF_CCALL *v50; // rbx
  __int64 v51; // rax
  CSECURITY_CONTEXT *v52; // rax
  unsigned int v53; // r8d
  int v54; // r9d
  CSECURITY_CONTEXT *v55; // rax
  unsigned int v56; // edx
  unsigned int v57; // eax
  unsigned int v58; // edx
  int v59; // eax
  unsigned int v60; // edx
  int v61; // eax
  __int64 v62; // rcx
  __int64 v63; // rcx
  int v64; // [rsp+30h] [rbp-99h]
  int v65; // [rsp+38h] [rbp-91h]
  REFERENCED_OBJECT *v66; // [rsp+68h] [rbp-61h] BYREF
  int v67; // [rsp+70h] [rbp-59h]
  int v68; // [rsp+74h] [rbp-55h] BYREF
  struct OSF_CCALL *v69; // [rsp+78h] [rbp-51h] BYREF
  int v70; // [rsp+80h] [rbp-49h]
  unsigned __int32 v71; // [rsp+84h] [rbp-45h]
  int v72; // [rsp+88h] [rbp-41h]
  int v73; // [rsp+8Ch] [rbp-3Dh] BYREF
  int v74; // [rsp+90h] [rbp-39h]
  int v75; // [rsp+94h] [rbp-35h] BYREF
  int v76; // [rsp+98h] [rbp-31h] BYREF
  CSECURITY_CONTEXT *v77; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-21h] BYREF
  struct MTSyntaxBinding *v79[2]; // [rsp+B0h] [rbp-19h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+C0h] [rbp-9h]
  struct OSF_CCONNECTION *v81; // [rsp+118h] [rbp+4Fh] BYREF
  struct OSF_BINDING_HANDLE *v82; // [rsp+120h] [rbp+57h]
  struct _RPC_MESSAGE *v83; // [rsp+128h] [rbp+5Fh]
  struct CLIENT_AUTH_INFO *v84; // [rsp+130h] [rbp+67h]

  v84 = a4;
  v83 = a3;
  v82 = a2;
  v81 = this;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  RpcFlags = a3->RpcFlags;
  v9 = 0;
  RpcInterfaceInformation = (struct _RPC_CLIENT_INTERFACE *)a3->RpcInterfaceInformation;
  v11 = this;
  v68 = 0;
  *a7 = 0;
  v73 = 0;
  v13 = a2;
  v75 = 0;
  *(_OWORD *)v79 = 0;
  v66 = 0;
  v77 = 0;
  v78 = 0;
  CriticalSection = (PRTL_CRITICAL_SECTION)((char *)this + 184);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 184));
  CCall = MTSyntaxBinding::FindOrCreateBinding(
            RpcInterfaceInformation,
            (struct OSF_CCONNECTION *)((char *)v11 + 48),
            (struct MTSyntaxBinding *(*)(struct _RPC_SYNTAX_IDENTIFIER *, struct TRANSFER_SYNTAX_STUB_INFO *, int))CreateOsfBinding,
            (int (*)(struct MTSyntaxBinding *, void *))CheckOsfBindingForDestruction,
            v11,
            &v68,
            v79,
            (int *const)&v69);
  if ( CCall )
  {
    RtlLeaveCriticalSection(v7);
    return CCall;
  }
  v70 = -1;
  v15 = RpcFlags & 0xA000;
  v67 = 1;
  v72 = v15;
  v71 = _InterlockedIncrement((volatile signed __int32 *)v11 + 45);
  if ( v15 && (v83->RpcFlags & 0x2000) == 0 )
  {
    v44 = *(_QWORD *)v13;
    v69 = 0;
    (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *, __int64, struct OSF_CCALL **))(v44 + 296))(v13, 9, &v69);
    v67 = v69 != 0;
  }
  if ( (unsigned int)IsCertBasedAuthnService(*((_DWORD *)a4 + 1)) )
  {
    if ( *(_DWORD *)a4 < 6u )
    {
      (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *, __int64, __int64 *))(*(_QWORD *)v13 + 296LL))(v13, 18, &v78);
      if ( !v78 )
        *(_DWORD *)a4 = 6;
    }
  }
  v16 = v68;
  v17 = &v69;
  v18 = 0;
  v74 = v68;
  if ( v68 > 0 )
  {
    v19 = v83;
    v20 = -1;
    do
    {
      v21 = v79[v18];
      v22 = (_DWORD *)&v69 + v18;
      v23 = *((_DWORD *)v21 + 14);
      *v22 = *((_DWORD *)v21 + 18);
      v24 = v21;
      if ( (v23 & 2) == 0 )
        v24 = v9;
      v9 = v24;
      if ( (v23 & 1) != 0 )
        v16 = 1;
      else
        v22 = v17;
      v17 = (struct OSF_CCALL **)v22;
      if ( (v19->RpcFlags & 0xA000) != 0 && !memcmp_0(&xmmword_1800E67F0, (char *)v21 + 24, 0x14u) )
        v20 = v18;
      OSF_BINDING::AddReference(v21);
      ++v18;
    }
    while ( v18 < v68 );
    v11 = v81;
    v70 = v20;
    v13 = v82;
    v74 = v16;
  }
  v25 = a6;
  if ( a5 )
    CurrentThreadId = *(_DWORD *)(*((_QWORD *)*a6 + 78) + 328LL);
  else
    CurrentThreadId = GetCurrentThreadId();
  if ( (v83->RpcFlags & 0x2000) != 0 )
  {
    (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *, __int64, __int64 *))(*(_QWORD *)v13 + 296LL))(v13, 18, &v78);
    v27 = v67;
    if ( v78 )
      v27 = 0;
    v67 = v27;
  }
  else
  {
    v27 = v67;
  }
  v76 = OSF_CASSOCIATION::LookForExistingConnection(
          v11,
          (unsigned int)v72,
          v27,
          CurrentThreadId,
          v84,
          *((_DWORD *)v13 + 122),
          v17,
          v16,
          &v66,
          &v73,
          &v75,
          &v77);
  CCall = v76;
  if ( v76 )
  {
    RtlLeaveCriticalSection(CriticalSection);
    ReleaseBindingListWithException(0, v9);
    return CCall;
  }
  v28 = v66;
  if ( v66 )
  {
    if ( v74 == 1 )
    {
      if ( a5 && v68 > 1 )
        v17 = (struct OSF_CCALL **)((char *)&v69 + 4 * v70);
      v35 = ((char *)v17 - (char *)&v69) >> 2;
      if ( v73 >= 0 )
        LODWORD(v35) = v73 + v35;
      v36 = v79[(int)v35];
      v66 = (REFERENCED_OBJECT *)*((_QWORD *)v36 + 6);
      ReleaseBindingListWithException(v36, v9);
      v9 = 0;
      LODWORD(v81) = v75;
LABEL_48:
      v37 = (unsigned int *)v77;
      if ( v77 )
        goto LABEL_49;
      v52 = (CSECURITY_CONTEXT *)AllocWrapper(0x138u);
      if ( v52 )
      {
        v55 = CSECURITY_CONTEXT::CSECURITY_CONTEXT(v52, v84, v53, v54, &v76);
        v37 = (unsigned int *)v55;
        if ( !v55 )
        {
LABEL_119:
          CCall = 14;
          goto LABEL_49;
        }
        CCall = v76;
        if ( v76 )
        {
          CSECURITY_CONTEXT::`scalar deleting destructor'(v55, v56);
          v37 = 0;
          goto LABEL_49;
        }
        v57 = SIMPLE_DICT::Insert((REFERENCED_OBJECT *)((char *)v28 + 360), v55);
        v37[52] = v57;
        if ( v57 != -1 )
        {
          v59 = *((_DWORD *)v11 + 79);
          fEnableIdleConnectionCleanup = 1;
          if ( (v59 & 2) == 0 )
          {
            if ( (unsigned int)EnableGCOnCounter(0x1388u, &EnableLingeredAssociationCleanupCount) )
            {
              SIMPLE_DICT::Delete((REFERENCED_OBJECT *)((char *)v28 + 360), v37[52]);
              CSECURITY_CONTEXT::`scalar deleting destructor'((CSECURITY_CONTEXT *)v37, v60);
              v37 = 0;
              CCall = 14;
            }
            else
            {
              v61 = *((_DWORD *)v11 + 79) | 2;
              LODWORD(v81) = 2;
              *((_DWORD *)v11 + 79) = v61;
            }
          }
          CSECURITY_CONTEXT::Lock((CSECURITY_CONTEXT *)v37);
LABEL_49:
          RtlLeaveCriticalSection(CriticalSection);
          if ( !CCall )
          {
            v38 = a5;
            v39 = *((_DWORD *)v28 + 28);
            if ( a5 )
            {
              if ( (v39 & 0x20) != 0 )
              {
                RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v28 + 216));
                v62 = *((_QWORD *)v28 + 9);
                if ( v62 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 8LL))(v62, 1);
                *((_QWORD *)v28 + 9) = *v25;
                *((_QWORD *)v28 + 4) = *v25;
                RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v28 + 216));
              }
              else
              {
                if ( !_InterlockedCompareExchange((volatile signed __int32 *)v28 + 16, 0, 1) )
                {
LABEL_55:
                  v41 = *v25;
                  if ( !v38 )
                    goto LABEL_56;
LABEL_131:
                  v42 = OSF_CCALL::ActivateCallWithConnection(v41, v36, v9, v71, (_DWORD)v81, v66, v28, v37);
                  goto LABEL_57;
                }
                v63 = *((_QWORD *)v28 + 9);
                if ( v63 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 8LL))(v63);
                *((_QWORD *)v28 + 9) = *v25;
              }
              v41 = *v25;
              goto LABEL_131;
            }
            if ( (v39 & 0x20) != 0 )
            {
              v40 = (CALL *)*((_QWORD *)v28 + 9);
              *v25 = v40;
              CALL::SetActivityIDFromThread(v40);
              v41 = *v25;
LABEL_56:
              v42 = OSF_CCALL::ActivateCall(v41, v82, v36, v9, v71, (_DWORD)v81, v66, v28, v37);
LABEL_57:
              CCall = v42;
              if ( v42 )
                goto LABEL_62;
              if ( (v83->RpcFlags & 0x2000) != 0 )
                _InterlockedOr((volatile signed __int32 *)*v25 + 114, 1u);
              if ( v37 )
              {
                CCall = OSF_CCALL::ReserveSpaceForSecurityIfNecessary(*v25);
                if ( CCall )
                {
LABEL_62:
                  if ( !v38 )
                  {
                    OSF_CCALL::FreeCCall(*v25, 1727);
                    *a7 = 1;
                  }
                }
              }
              return CCall;
            }
            CCall = OSF_CCONNECTION::AllocateCCall(v28, v25);
            if ( !CCall )
              goto LABEL_55;
          }
          ReleaseBindingListWithException(0, v9);
          if ( v37 )
            CSECURITY_CONTEXT::Unlock((CSECURITY_CONTEXT *)v37);
          return CCall;
        }
        CSECURITY_CONTEXT::`scalar deleting destructor'((CSECURITY_CONTEXT *)v37, v58);
      }
      v37 = 0;
      goto LABEL_119;
    }
    LODWORD(v81) = 2;
    v43 = v83->RpcFlags & 0xA000;
    if ( v73 >= 0 )
    {
      if ( !v43 )
        goto LABEL_72;
      v51 = (int)(v73 + (((char *)v17 - (char *)&v69) >> 2));
    }
    else
    {
      if ( !v43 )
      {
LABEL_72:
        v36 = 0;
        v66 = 0;
        goto LABEL_48;
      }
      v51 = v70;
    }
    v36 = v79[v51];
    v66 = (REFERENCED_OBJECT *)*((_QWORD *)v36 + 6);
    goto LABEL_48;
  }
  if ( (*((_DWORD *)v11 + 79) & 0x10) != 0 && !*((_QWORD *)v11 + 41) )
  {
    v69 = 0;
    v81 = 0;
    CCall = OSF_CASSOCIATION::CreateConnection(v11, v13, 0, 1, 0, &v69, v84, 1, &v81);
    if ( !CCall )
    {
      for ( i = v9; i; i = (OSF_BINDING *)*((_QWORD *)i + 8) )
        OSF_BINDING::AddReference(i);
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v11 + 184));
    if ( CCall )
      goto LABEL_33;
    v46 = _InterlockedIncrement((volatile signed __int32 *)v11 + 45);
    v28 = v81;
    v47 = v69;
    CCall = OSF_CCALL::ActivateCall(v69, v13, 0, v9, v46, 1, 0, v81, v77);
    if ( CCall )
    {
      v48 = (struct OSF_BINDING *)*((_QWORD *)v47 + 38);
      if ( v48 )
        ReleaseBindingListWithException(0, v48);
      else
        OSF_BINDING::RemoveReference(*((OSF_BINDING **)v47 + 37));
      ReleaseBindingListWithException(0, v9);
      *((_QWORD *)v47 + 34) = 0;
LABEL_99:
      OSF_CASSOCIATION::ConnectionAborted(v11, v28);
      goto LABEL_34;
    }
    (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *))(*(_QWORD *)v13 + 384LL))(v13);
    CCall = OSF_CCALL::BindToServer(v47, 0);
    if ( CCall )
    {
      OSF_CCALL::FreeCCall(v47, 1727);
      *a7 = 0;
      goto LABEL_33;
    }
    OSF_CCALL::FreeCCall(v47, 0);
    *((_DWORD *)v28 + 28) |= 0x40u;
    CCall = OSF_CCONNECTION::TransAsyncReceive(v28);
    if ( CCall )
      goto LABEL_33;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v11 + 184));
    *((_QWORD *)v11 + 41) = v28;
  }
  v29 = a5;
  CCall = OSF_CASSOCIATION::CreateConnection(v11, v13, v72, v67, a5, v25, v84, 0, &v66);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v11 + 184));
  if ( CCall )
  {
    v28 = v66;
LABEL_33:
    ReleaseBindingListWithException(0, v9);
    goto LABEL_34;
  }
  if ( v68 == 1 )
  {
    v30 = v79[0];
    v31 = *((_QWORD *)v79[0] + 6);
    ReleaseBindingListWithException(v79[0], v9);
    v9 = 0;
  }
  else if ( (v83->RpcFlags & 0xA000) != 0 )
  {
    v30 = v79[v70];
    v31 = *((_QWORD *)v30 + 6);
  }
  else
  {
    v30 = 0;
    v31 = 0;
  }
  v32 = v29 == 0;
  v28 = v66;
  if ( v32 )
    v33 = OSF_CCALL::ActivateCall(*v25, v13, v30, v9, v71, 1, v31, v66, v77);
  else
    v33 = OSF_CCALL::ActivateCallWithConnection(*v25, v30, v9, v71, 1, v31, v66, v77);
  CCall = v33;
  if ( v33 )
  {
    v49 = (struct OSF_BINDING *)*((_QWORD *)*v25 + 38);
    if ( v49 )
      ReleaseBindingListWithException(0, v49);
    else
      OSF_BINDING::RemoveReference(*((OSF_BINDING **)*v25 + 37));
    *((_QWORD *)*v25 + 34) = 0;
    goto LABEL_99;
  }
  if ( (v83->RpcFlags & 0x2000) != 0 )
    _InterlockedOr((volatile signed __int32 *)*v25 + 114, 1u);
  if ( v72 )
  {
    OSF_BINDING_HANDLE::AddReference(v13);
    REFERENCED_OBJECT::AddReference(v28);
    REFERENCED_OBJECT::AddReference(*v25);
    v50 = *v25;
    LogEvent(0x6Eu, 0x4Eu, v28, *v25, 0, v64, v65);
    CCall = RPC_THREAD_POOL::TrySubmitWork(OsfBindToServer, v50);
    if ( CCall )
    {
      OSF_BINDING_HANDLE::BindingFree(v13);
      OSF_CASSOCIATION::ConnectionAborted(v11, v28);
      (*(void (__fastcall **)(OSF_CCALL *))(*(_QWORD *)*v25 + 32LL))(*v25);
LABEL_34:
      if ( v28 )
      {
        if ( a5 )
        {
          if ( *((_QWORD *)v28 + 9) )
            *((_QWORD *)v28 + 9) = 0;
          if ( *((_QWORD *)*v25 + 34) )
            *((_QWORD *)*v25 + 34) = 0;
        }
        if ( (*((_DWORD *)v28 + 28) & 0x20) == 0 )
          OSF_CCONNECTION::ReleaseCausalOrder(v28);
        (*(void (__fastcall **)(REFERENCED_OBJECT *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 1);
      }
    }
  }
  return CCall;
}

```

## disassembly

```asm
0x18001208c  mov     rax, rsp
0x18001208f  mov     [rax+20h], r9
0x180012093  mov     [rax+18h], r8
0x180012097  mov     [rax+10h], rdx
0x18001209b  mov     [rax+8], rcx
0x18001209f  push    rbp
0x1800120a0  push    rbx
0x1800120a1  push    rsi
0x1800120a2  push    rdi
0x1800120a3  push    r12
0x1800120a5  push    r13
0x1800120a7  push    r14
0x1800120a9  push    r15
0x1800120ab  lea     rbp, [rax-47h]
0x1800120af  sub     rsp, 0C8h
0x1800120b6  mov     rax, [rbp+3Fh+arg_30]
0x1800120ba  lea     rdi, [rcx+0B8h]
0x1800120c1  mov     esi, [r8+48h]
0x1800120c5  xor     r12d, r12d
0x1800120c8  mov     rbx, [r8+28h]
0x1800120cc  mov     r15, rcx
0x1800120cf  xorps   xmm0, xmm0
0x1800120d2  mov     [rbp+3Fh+var_94], r12d
0x1800120d6  mov     rcx, rdi; CriticalSection
0x1800120d9  mov     [rax], r12d
0x1800120dc  mov     r14, r9
0x1800120df  mov     [rbp+3Fh+var_7C], r12d
0x1800120e3  mov     r13, rdx
0x1800120e6  mov     [rbp+3Fh+var_74], r12d
0x1800120ea  movups  xmmword ptr [rbp+3Fh+var_58], xmm0
0x1800120ee  mov     [rbp+3Fh+var_A0], r12
0x1800120f2  mov     [rbp+3Fh+var_68], r12
0x1800120f6  mov     [rbp+3Fh+var_60], r12
0x1800120fa  mov     [rbp+3Fh+CriticalSection], rdi
0x1800120fe  call    cs:__imp_RtlEnterCriticalSection
0x180012105  nop     dword ptr [rax+rax+00h]
0x18001210a  lea     rax, [rbp+3Fh+var_90]
0x18001210e  mov     rcx, rbx; struct _RPC_CLIENT_INTERFACE *
0x180012111  mov     [rsp+100h+var_C8], rax; int *
0x180012116  lea     rdx, [r15+30h]; struct SIMPLE_DICT *
0x18001211a  lea     rax, [rbp+3Fh+var_58]
0x18001211e  mov     [rsp+100h+var_D0], rax; struct MTSyntaxBinding **
0x180012123  lea     r9, ?CheckOsfBindingForDestruction@@YAHPEAVMTSyntaxBinding@@PEAX@Z; int (*)(struct MTSyntaxBinding *, void *)
0x18001212a  lea     rax, [rbp+3Fh+var_94]
0x18001212e  mov     [rsp+100h+var_D8], rax; int *
0x180012133  lea     r8, ?CreateOsfBinding@@YAPEAVMTSyntaxBinding@@PEAU_RPC_SYNTAX_IDENTIFIER@@PEAVTRANSFER_SYNTAX_STUB_INFO@@H@Z; struct MTSyntaxBinding *(*)(struct _RPC_SYNTAX_IDENTIFIER *, struct TRANSFER_SYNTAX_STUB_INFO *, int)
0x18001213a  mov     [rsp+100h+var_E0], r15; void *
0x18001213f  call    ?FindOrCreateBinding@MTSyntaxBinding@@SAJPEAU_RPC_CLIENT_INTERFACE@@PEAVSIMPLE_DICT@@P6APEAV1@PEAU_RPC_SYNTAX_IDENTIFIER@@PEAVTRANSFER_SYNTAX_STUB_INFO@@H@ZP6AHPEAV1@PEAX@Z6PEAHQEAPEAV1@QEAH@Z; MTSyntaxBinding::FindOrCreateBinding(_RPC_CLIENT_INTERFACE *,SIMPLE_DICT *,MTSyntaxBinding * (*)(_RPC_SYNTAX_IDENTIFIER *,TRANSFER_SYNTAX_STUB_INFO *,int),int (*)(MTSyntaxBinding *,void *),void *,int *,MTSyntaxBinding * * const,int * const)
0x180012144  mov     ebx, eax
0x180012146  test    eax, eax
0x180012148  jnz     loc_1800126B5
0x18001214e  lea     ecx, [rax+1]
0x180012151  mov     [rbp+3Fh+var_88], 0FFFFFFFFh
0x180012158  and     esi, 0A000h
0x18001215e  mov     [rbp+3Fh+var_98], ecx
0x180012161  mov     [rbp+3Fh+var_80], esi
0x180012164  mov     ebx, ecx
0x180012166  mov     eax, ecx
0x180012168  lock xadd [r15+0B4h], eax
0x180012171  add     eax, ecx
0x180012173  mov     [rbp+3Fh+var_84], eax
0x180012176  test    esi, esi
0x180012178  jnz     loc_180012618
0x18001217e  mov     ecx, [r14+4]; unsigned int
0x180012182  call    ?IsCertBasedAuthnService@@YAHK@Z; IsCertBasedAuthnService(ulong)
0x180012187  test    eax, eax
0x180012189  jnz     loc_1800126C9
0x18001218f  mov     edi, [rbp+3Fh+var_94]
0x180012192  lea     r14, [rbp+3Fh+var_90]
0x180012196  xor     ebx, ebx
0x180012198  mov     [rbp+3Fh+var_78], edi
0x18001219b  test    edi, edi
0x18001219d  jle     short loc_18001220E
0x18001219f  mov     r15, [rbp+3Fh+arg_10]
0x1800121a3  or      r13d, 0FFFFFFFFh
0x1800121a7  movsxd  rax, ebx
0x1800121aa  lea     r8, [rbp+3Fh+var_90]
0x1800121ae  mov     rsi, [rbp+rax*8+3Fh+var_58]
0x1800121b3  lea     r8, [r8+rax*4]
0x1800121b7  mov     eax, [rsi+48h]
0x1800121ba  lea     rdx, [rsi+18h]; Buf2
0x1800121be  mov     ecx, [rdx+20h]
0x1800121c1  test    cl, 2
0x1800121c4  mov     [r8], eax
0x1800121c7  mov     rax, rsi
0x1800121ca  cmovz   rax, r12
0x1800121ce  mov     r12, rax
0x1800121d1  mov     eax, 1
0x1800121d6  test    eax, ecx
0x1800121d8  cmovz   r8, r14
0x1800121dc  cmovnz  edi, eax
0x1800121df  test    dword ptr [r15+48h], 0A000h
0x1800121e7  mov     r14, r8
0x1800121ea  jnz     loc_18001265C
0x1800121f0  mov     rcx, rsi; this
0x1800121f3  call    ?AddReference@OSF_BINDING@@QEAAXXZ; OSF_BINDING::AddReference(void)
0x1800121f8  inc     ebx
0x1800121fa  cmp     ebx, [rbp+3Fh+var_94]
0x1800121fd  jl      short loc_1800121A7
0x1800121ff  mov     r15, [rbp+3Fh+arg_0]
0x180012203  mov     [rbp+3Fh+var_88], r13d
0x180012207  mov     r13, [rbp+3Fh+arg_8]
0x18001220b  mov     [rbp+3Fh+var_78], edi
0x18001220e  cmp     [rbp+3Fh+arg_20], 0
0x180012212  mov     rsi, [rbp+3Fh+arg_28]
0x180012216  jnz     loc_1800125D1
0x18001221c  call    cs:__imp_GetCurrentThreadId
0x180012223  nop     dword ptr [rax+rax+00h]
0x180012228  mov     ebx, eax
0x18001222a  mov     rax, [rbp+3Fh+arg_10]
0x18001222e  test    dword ptr [rax+48h], 2000h
0x180012235  jnz     loc_180012705
0x18001223b  mov     ecx, [rbp+3Fh+var_98]
0x18001223e  mov     edx, [rbp+3Fh+var_80]
0x180012241  lea     rax, [rbp+3Fh+var_68]
0x180012245  mov     [rsp+58h], rax
0x18001224a  mov     r8d, ecx
0x18001224d  lea     rax, [rbp+3Fh+var_74]
0x180012251  mov     r9d, ebx
0x180012254  mov     [rsp+100h+var_B0], rax
0x180012259  mov     rcx, r15
0x18001225c  lea     rax, [rbp+3Fh+var_7C]
0x180012260  mov     [rsp+100h+var_B8], rax
0x180012265  lea     rax, [rbp+3Fh+var_A0]
0x180012269  mov     [rsp+100h+var_C0], rax
0x18001226e  mov     eax, [r13+1E8h]
0x180012275  mov     dword ptr [rsp+100h+var_C8], edi
0x180012279  mov     [rsp+100h+var_D0], r14
0x18001227e  mov     dword ptr [rsp+100h+var_D8], eax
0x180012282  mov     rax, [rbp+3Fh+arg_18]
0x180012286  mov     [rsp+100h+var_E0], rax
0x18001228b  call    ?LookForExistingConnection@OSF_CASSOCIATION@@AEAAJHHKPEAUCLIENT_AUTH_INFO@@W4tagNamedPipeType@@PEAHHPEAPEAVOSF_CCONNECTION@@2PEAW4OSF_CCALL_STATE@@PEAPEAVCSECURITY_CONTEXT@@@Z; OSF_CASSOCIATION::LookForExistingConnection(int,int,ulong,CLIENT_AUTH_INFO *,tagNamedPipeType,int *,int,OSF_CCONNECTION * *,int *,OSF_CCALL_STATE *,CSECURITY_CONTEXT * *)
0x180012290  mov     [rbp+3Fh+var_70], eax
0x180012293  mov     ebx, eax
0x180012295  test    eax, eax
0x180012297  jnz     loc_180012578
0x18001229d  mov     rdi, [rbp+3Fh+var_A0]
0x1800122a1  test    rdi, rdi
0x1800122a4  jnz     loc_180012415
0x1800122aa  mov     eax, [r15+13Ch]
0x1800122b1  test    al, 10h
0x1800122b3  jnz     loc_180012735
0x1800122b9  mov     edi, [rbp+3Fh+arg_20]
0x1800122bc  lea     rax, [rbp+3Fh+var_A0]
0x1800122c0  mov     r9d, [rbp+3Fh+var_98]; int
0x1800122c4  mov     rdx, r13; struct OSF_BINDING_HANDLE *
0x1800122c7  mov     r8d, [rbp+3Fh+var_80]; int
0x1800122cb  mov     rcx, r15; this
0x1800122ce  mov     [rsp+100h+var_C0], rax; struct OSF_CCONNECTION **
0x1800122d3  mov     rax, [rbp+3Fh+arg_18]
0x1800122d7  mov     dword ptr [rsp+100h+var_C8], 0; int
0x1800122df  mov     [rsp+100h+var_D0], rax; struct CLIENT_AUTH_INFO *
0x1800122e4  mov     [rsp+100h+var_D8], rsi; struct OSF_CCALL **
0x1800122e9  mov     dword ptr [rsp+100h+var_E0], edi; int
0x1800122ed  call    ?CreateConnection@OSF_CASSOCIATION@@AEAAJPEAVOSF_BINDING_HANDLE@@HHHPEAPEAVOSF_CCALL@@PEAUCLIENT_AUTH_INFO@@HPEAPEAVOSF_CCONNECTION@@@Z; OSF_CASSOCIATION::CreateConnection(OSF_BINDING_HANDLE *,int,int,int,OSF_CCALL * *,CLIENT_AUTH_INFO *,int,OSF_CCONNECTION * *)
0x1800122f2  lea     rcx, [r15+0B8h]; CriticalSection
0x1800122f9  mov     ebx, eax
0x1800122fb  call    cs:__imp_RtlLeaveCriticalSection
0x180012302  nop     dword ptr [rax+rax+00h]
0x180012307  test    ebx, ebx
0x180012309  jnz     loc_1800123A8
0x18001230f  lea     ecx, [rbx+1]
0x180012312  cmp     [rbp+3Fh+var_94], ecx
0x180012315  jz      loc_1800124B0
0x18001231b  mov     rax, [rbp+3Fh+arg_10]
0x18001231f  test    dword ptr [rax+48h], 0A000h
0x180012326  jnz     loc_1800126A3
0x18001232c  xor     ebx, ebx
0x18001232e  xor     r14d, r14d
0x180012331  mov     rax, [rbp+3Fh+var_68]
0x180012335  test    edi, edi
0x180012337  mov     rdi, [rbp+3Fh+var_A0]
0x18001233b  jnz     loc_180012679
0x180012341  mov     [rsp+100h+var_C0], rax
0x180012346  mov     r9, r12
0x180012349  mov     eax, [rbp+3Fh+var_84]
0x18001234c  mov     r8, rbx
0x18001234f  mov     [rsp+100h+var_C8], rdi
0x180012354  mov     rdx, r13
0x180012357  mov     [rsp+100h+var_D0], r14; int
0x18001235c  mov     dword ptr [rsp+100h+var_D8], ecx; int
0x180012360  mov     rcx, [rsi]
0x180012363  mov     dword ptr [rsp+100h+var_E0], eax
0x180012367  call    ?ActivateCall@OSF_CCALL@@QEAAJPEAVOSF_BINDING_HANDLE@@PEAVOSF_BINDING@@1KW4OSF_CCALL_STATE@@PEAURPC_DISPATCH_TABLE@@PEAVOSF_CCONNECTION@@PEAVCSECURITY_CONTEXT@@@Z; OSF_CCALL::ActivateCall(OSF_BINDING_HANDLE *,OSF_BINDING *,OSF_BINDING *,ulong,OSF_CCALL_STATE,RPC_DISPATCH_TABLE *,OSF_CCONNECTION *,CSECURITY_CONTEXT *)
0x18001236c  mov     ebx, eax
0x18001236e  test    eax, eax
0x180012370  jnz     loc_180012902
0x180012376  mov     rax, [rbp+3Fh+arg_10]
0x18001237a  test    dword ptr [rax+48h], 2000h
0x180012381  jnz     loc_180012921
0x180012387  cmp     [rbp+3Fh+var_80], 0
0x18001238b  jnz     loc_180012931
0x180012391  mov     eax, ebx
0x180012393  add     rsp, 0C8h
0x18001239a  pop     r15
0x18001239c  pop     r14
0x18001239e  pop     r13
0x1800123a0  pop     r12
0x1800123a2  pop     rdi
0x1800123a3  pop     rsi
0x1800123a4  pop     rbx
0x1800123a5  pop     rbp
0x1800123a6  retn
0x1800123a8  mov     rdi, [rbp+3Fh+var_A0]
0x1800123ac  mov     rdx, r12; struct OSF_BINDING *
0x1800123af  xor     ecx, ecx; struct OSF_BINDING *
0x1800123b1  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x1800123b6  test    rdi, rdi
0x1800123b9  jz      short loc_180012391
0x1800123bb  cmp     [rbp+3Fh+arg_20], 0
0x1800123bf  jz      short loc_1800123E8
0x1800123c1  cmp     qword ptr [rdi+48h], 0
0x1800123c6  jz      short loc_1800123D0
0x1800123c8  mov     qword ptr [rdi+48h], 0
0x1800123d0  mov     rax, [rsi]
0x1800123d3  cmp     qword ptr [rax+110h], 0
0x1800123db  jz      short loc_1800123E8
0x1800123dd  mov     qword ptr [rax+110h], 0
0x1800123e8  mov     eax, [rdi+70h]
0x1800123eb  test    al, 20h
0x1800123ed  jnz     short loc_1800123F7
0x1800123ef  mov     rcx, rdi; this
0x1800123f2  call    ?ReleaseCausalOrder@OSF_CCONNECTION@@QEAAXXZ; OSF_CCONNECTION::ReleaseCausalOrder(void)
0x1800123f7  test    rdi, rdi
0x1800123fa  jz      short loc_180012391
0x1800123fc  mov     rax, [rdi]
0x1800123ff  mov     edx, 1
0x180012404  mov     rcx, rdi
0x180012407  mov     rax, [rax+8]
0x18001240b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012410  jmp     loc_180012391
0x180012415  mov     eax, 1
0x18001241a  cmp     [rbp+3Fh+var_78], eax
0x18001241d  jnz     loc_1800125E6
0x180012423  cmp     [rbp+3Fh+arg_20], 0
0x180012427  jnz     loc_1800125B7
0x18001242d  lea     rax, [rbp+3Fh+var_90]
0x180012431  sub     r14, rax
0x180012434  mov     eax, [rbp+3Fh+var_7C]
0x180012437  sar     r14, 2
0x18001243b  test    eax, eax
0x18001243d  js      short loc_180012442
0x18001243f  add     r14d, eax
0x180012442  movsxd  rax, r14d
0x180012445  mov     rdx, r12; struct OSF_BINDING *
0x180012448  mov     r13, [rbp+rax*8+3Fh+var_58]
0x18001244d  mov     rcx, r13; struct OSF_BINDING *
0x180012450  mov     rax, [r13+30h]
0x180012454  mov     [rbp+3Fh+var_A0], rax
0x180012458  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x18001245d  mov     edx, [rbp+3Fh+var_74]
0x180012460  xor     r12d, r12d
0x180012463  mov     dword ptr [rbp+3Fh+arg_0], edx
0x180012466  mov     r14, [rbp+3Fh+var_68]
0x18001246a  test    r14, r14
0x18001246d  jz      loc_1800129D5
0x180012473  mov     rcx, [rbp+3Fh+CriticalSection]; CriticalSection
0x180012477  call    cs:__imp_RtlLeaveCriticalSection
0x18001247e  nop     dword ptr [rax+rax+00h]
0x180012483  test    ebx, ebx
0x180012485  jnz     loc_180012597
0x18001248b  mov     r15d, [rbp+3Fh+arg_20]
0x18001248f  mov     eax, [rdi+70h]
0x180012492  test    r15d, r15d
0x180012495  jnz     loc_180012ABB
0x18001249b  test    al, 20h
0x18001249d  jz      short loc_1800124D0
0x18001249f  mov     rcx, [rdi+48h]; this
0x1800124a3  mov     [rsi], rcx
0x1800124a6  call    ?SetActivityIDFromThread@CALL@@QEAAXXZ; CALL::SetActivityIDFromThread(void)
0x1800124ab  mov     rcx, [rsi]
0x1800124ae  jmp     short loc_1800124F1
0x1800124b0  mov     rbx, [rbp+3Fh+var_58]
0x1800124b4  mov     rdx, r12; struct OSF_BINDING *
0x1800124b7  mov     rcx, rbx; struct OSF_BINDING *
0x1800124ba  mov     r14, [rbx+30h]
0x1800124be  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x1800124c3  xor     r12d, r12d
0x1800124c6  lea     ecx, [r12+1]
0x1800124cb  jmp     loc_180012331
0x1800124d0  mov     rdx, rsi; struct OSF_CCALL **
0x1800124d3  mov     rcx, rdi; this
0x1800124d6  call    ?AllocateCCall@OSF_CCONNECTION@@QEAAJPEAPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AllocateCCall(OSF_CCALL * *)
0x1800124db  mov     ebx, eax
0x1800124dd  test    eax, eax
0x1800124df  jnz     loc_180012597
0x1800124e5  mov     rcx, [rsi]
0x1800124e8  test    r15d, r15d
0x1800124eb  jnz     loc_180012B28
0x1800124f1  mov     rax, [rbp+3Fh+var_A0]
0x1800124f5  mov     r9, r12
0x1800124f8  mov     rdx, [rbp+3Fh+arg_8]
0x1800124fc  mov     r8, r13
0x1800124ff  mov     [rsp+100h+var_C0], r14
0x180012504  mov     [rsp+100h+var_C8], rdi
0x180012509  mov     [rsp+100h+var_D0], rax
0x18001250e  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x180012511  mov     dword ptr [rsp+100h+var_D8], eax
0x180012515  mov     eax, [rbp+3Fh+var_84]
0x180012518  mov     dword ptr [rsp+100h+var_E0], eax
  ... truncated ...
```
