# OSF_CASSOCIATION::AllocateOrInitCCall(OSF_BINDING_HANDLE *,_RPC_MESSAGE *,CLIENT_AUTH_INFO *,int,OSF_CCALL * *,int *)

- ea: `0x1800517c8`
- end: `0x180052286`
- name: `?AllocateOrInitCCall@OSF_CASSOCIATION@@QEAAJPEAVOSF_BINDING_HANDLE@@PEAU_RPC_MESSAGE@@PEAUCLIENT_AUTH_INFO@@HPEAPEAVOSF_CCALL@@PEAH@Z`
- size: `2750`
- prototype: `__int64 __usercall@<rax>(OSF_CASSOCIATION *__hidden this@<rcx>, struct OSF_BINDING_HANDLE *@<rdx>, struct _RPC_MESSAGE *@<r8>, struct CLIENT_AUTH_INFO *@<r9>, int, struct OSF_CCALL **, int *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800ad6ec`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x18002b7c0`
- `0x180048ae8`
- `0x180049064`
- `0x180049d2c`
- `0x18004afc8`
- `0x18004b1a8`
- `0x18004bc4c`
- `0x18004cc10`
- `0x18004f480`
- `0x1800514c0`
- `0x1800517c8`
- `0x18005228c`
- `0x1800522e4`
- `0x18005265c`
- `0x1800527e8`
- `0x180052ee4`
- `0x180053bc0`
- `0x180053ca4`
- `0x180054d48`
- `0x1800592d8`
- `0x18005ddc0`
- `0x18005fa6c`
- `0x1800614cc`
- `0x18008f2f0`
- `0x180093e74`
- `0x18009c91c`
- `0x18009ef10`
- `0x1800ab650`
- `0x1800ca025`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180051a30`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ba2`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ca1`
- `ntdll!RtlLeaveCriticalSection` at `0x180051dd7`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ed7`
- `ntdll!RtlLeaveCriticalSection` at `0x18005220b`
- `ntdll!RtlLeaveCriticalSection` at `0x180051a30`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ba2`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ca1`
- `ntdll!RtlLeaveCriticalSection` at `0x180051dd7`
- `ntdll!RtlLeaveCriticalSection` at `0x180051ed7`
- `ntdll!RtlLeaveCriticalSection` at `0x18005220b`
- `ntdll!RtlEnterCriticalSection` at `0x18005183a`
- `ntdll!RtlEnterCriticalSection` at `0x180051ffd`
- `ntdll!RtlEnterCriticalSection` at `0x1800521da`
- `ntdll!RtlEnterCriticalSection` at `0x18005183a`
- `ntdll!RtlEnterCriticalSection` at `0x180051ffd`
- `ntdll!RtlEnterCriticalSection` at `0x1800521da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180051957`

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
  if ( (*((_DWORD *)a4 + 1) == 14 || *((_DWORD *)a4 + 1) == 25) && *(_DWORD *)a4 < 6u )
  {
    (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *, __int64, __int64 *))(*(_QWORD *)v13 + 296LL))(v13, 18, &v78);
    if ( !v78 )
      *(_DWORD *)a4 = 6;
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
      if ( (v19->RpcFlags & 0xA000) != 0 && !memcmp_0(&xmmword_1800E1920, (char *)v21 + 24, 0x14u) )
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
LABEL_49:
      v37 = (unsigned int *)v77;
      if ( v77 )
        goto LABEL_50;
      v52 = (CSECURITY_CONTEXT *)AllocWrapper(0x138u);
      if ( v52 )
      {
        v55 = CSECURITY_CONTEXT::CSECURITY_CONTEXT(v52, v84, v53, v54, &v76);
        v37 = (unsigned int *)v55;
        if ( !v55 )
        {
LABEL_120:
          CCall = 14;
          goto LABEL_50;
        }
        CCall = v76;
        if ( v76 )
        {
          CSECURITY_CONTEXT::`scalar deleting destructor'(v55, v56);
          v37 = 0;
          goto LABEL_50;
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
LABEL_50:
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
LABEL_56:
                  v41 = *v25;
                  if ( !v38 )
                    goto LABEL_57;
LABEL_132:
                  v42 = OSF_CCALL::ActivateCallWithConnection(v41, v36, v9, v71, (_DWORD)v81, v66, v28, v37);
                  goto LABEL_58;
                }
                v63 = *((_QWORD *)v28 + 9);
                if ( v63 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 8LL))(v63);
                *((_QWORD *)v28 + 9) = *v25;
              }
              v41 = *v25;
              goto LABEL_132;
            }
            if ( (v39 & 0x20) != 0 )
            {
              v40 = (CALL *)*((_QWORD *)v28 + 9);
              *v25 = v40;
              CALL::SetActivityIDFromThread(v40);
              v41 = *v25;
LABEL_57:
              v42 = OSF_CCALL::ActivateCall(v41, v82, v36, v9, v71, (_DWORD)v81, v66, v28, v37);
LABEL_58:
              CCall = v42;
              if ( v42 )
                goto LABEL_63;
              if ( (v83->RpcFlags & 0x2000) != 0 )
                _InterlockedOr((volatile signed __int32 *)*v25 + 114, 1u);
              if ( v37 )
              {
                CCall = OSF_CCALL::ReserveSpaceForSecurityIfNecessary(*v25);
                if ( CCall )
                {
LABEL_63:
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
              goto LABEL_56;
          }
          ReleaseBindingListWithException(0, v9);
          if ( v37 )
            CSECURITY_CONTEXT::Unlock((CSECURITY_CONTEXT *)v37);
          return CCall;
        }
        CSECURITY_CONTEXT::`scalar deleting destructor'((CSECURITY_CONTEXT *)v37, v58);
      }
      v37 = 0;
      goto LABEL_120;
    }
    LODWORD(v81) = 2;
    v43 = v83->RpcFlags & 0xA000;
    if ( v73 >= 0 )
    {
      if ( !v43 )
        goto LABEL_73;
      v51 = (int)(v73 + (((char *)v17 - (char *)&v69) >> 2));
    }
    else
    {
      if ( !v43 )
      {
LABEL_73:
        v36 = 0;
        v66 = 0;
        goto LABEL_49;
      }
      v51 = v70;
    }
    v36 = v79[v51];
    v66 = (REFERENCED_OBJECT *)*((_QWORD *)v36 + 6);
    goto LABEL_49;
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
      goto LABEL_34;
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
LABEL_100:
      OSF_CASSOCIATION::ConnectionAborted(v11, v28);
      goto LABEL_35;
    }
    (*(void (__fastcall **)(struct OSF_BINDING_HANDLE *))(*(_QWORD *)v13 + 384LL))(v13);
    CCall = OSF_CCALL::BindToServer(v47, 0);
    if ( CCall )
    {
      OSF_CCALL::FreeCCall(v47, 1727);
      *a7 = 0;
      goto LABEL_34;
    }
    OSF_CCALL::FreeCCall(v47, 0);
    *((_DWORD *)v28 + 28) |= 0x40u;
    CCall = OSF_CCONNECTION::TransAsyncReceive(v28);
    if ( CCall )
      goto LABEL_34;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v11 + 184));
    *((_QWORD *)v11 + 41) = v28;
  }
  v29 = a5;
  CCall = OSF_CASSOCIATION::CreateConnection(v11, v13, v72, v67, a5, v25, v84, 0, &v66);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v11 + 184));
  if ( CCall )
  {
    v28 = v66;
LABEL_34:
    ReleaseBindingListWithException(0, v9);
    goto LABEL_35;
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
    goto LABEL_100;
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
LABEL_35:
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
0x1800517c8  mov     rax, rsp
0x1800517cb  mov     [rax+20h], r9
0x1800517cf  mov     [rax+18h], r8
0x1800517d3  mov     [rax+10h], rdx
0x1800517d7  mov     [rax+8], rcx
0x1800517db  push    rbp
0x1800517dc  push    rbx
0x1800517dd  push    rsi
0x1800517de  push    rdi
0x1800517df  push    r12
0x1800517e1  push    r13
0x1800517e3  push    r14
0x1800517e5  push    r15
0x1800517e7  lea     rbp, [rax-47h]
0x1800517eb  sub     rsp, 0C8h
0x1800517f2  mov     rax, [rbp+3Fh+arg_30]
0x1800517f6  lea     rdi, [rcx+0B8h]
0x1800517fd  mov     esi, [r8+48h]
0x180051801  xor     r12d, r12d
0x180051804  mov     rbx, [r8+28h]
0x180051808  mov     r15, rcx
0x18005180b  xorps   xmm0, xmm0
0x18005180e  mov     [rbp+3Fh+var_94], r12d
0x180051812  mov     rcx, rdi; CriticalSection
0x180051815  mov     [rax], r12d
0x180051818  mov     r14, r9
0x18005181b  mov     [rbp+3Fh+var_7C], r12d
0x18005181f  mov     r13, rdx
0x180051822  mov     [rbp+3Fh+var_74], r12d
0x180051826  movups  xmmword ptr [rbp+3Fh+var_58], xmm0
0x18005182a  mov     [rbp+3Fh+var_A0], r12
0x18005182e  mov     [rbp+3Fh+var_68], r12
0x180051832  mov     [rbp+3Fh+var_60], r12
0x180051836  mov     [rbp+3Fh+CriticalSection], rdi
0x18005183a  call    cs:__imp_RtlEnterCriticalSection
0x180051840  lea     rax, [rbp+3Fh+var_90]
0x180051844  mov     rcx, rbx; struct _RPC_CLIENT_INTERFACE *
0x180051847  mov     [rsp+100h+var_C8], rax; int *
0x18005184c  lea     rdx, [r15+30h]; struct SIMPLE_DICT *
0x180051850  lea     rax, [rbp+3Fh+var_58]
0x180051854  mov     [rsp+100h+var_D0], rax; struct MTSyntaxBinding **
0x180051859  lea     r9, ?CheckOsfBindingForDestruction@@YAHPEAVMTSyntaxBinding@@PEAX@Z; int (*)(struct MTSyntaxBinding *, void *)
0x180051860  lea     rax, [rbp+3Fh+var_94]
0x180051864  mov     [rsp+100h+var_D8], rax; int *
0x180051869  lea     r8, ?CreateOsfBinding@@YAPEAVMTSyntaxBinding@@PEAU_RPC_SYNTAX_IDENTIFIER@@PEAVTRANSFER_SYNTAX_STUB_INFO@@H@Z; struct MTSyntaxBinding *(*)(struct _RPC_SYNTAX_IDENTIFIER *, struct TRANSFER_SYNTAX_STUB_INFO *, int)
0x180051870  mov     [rsp+100h+var_E0], r15; void *
0x180051875  call    ?FindOrCreateBinding@MTSyntaxBinding@@SAJPEAU_RPC_CLIENT_INTERFACE@@PEAVSIMPLE_DICT@@P6APEAV1@PEAU_RPC_SYNTAX_IDENTIFIER@@PEAVTRANSFER_SYNTAX_STUB_INFO@@H@ZP6AHPEAV1@PEAX@Z6PEAHQEAPEAV1@QEAH@Z; MTSyntaxBinding::FindOrCreateBinding(_RPC_CLIENT_INTERFACE *,SIMPLE_DICT *,MTSyntaxBinding * (*)(_RPC_SYNTAX_IDENTIFIER *,TRANSFER_SYNTAX_STUB_INFO *,int),int (*)(MTSyntaxBinding *,void *),void *,int *,MTSyntaxBinding * * const,int * const)
0x18005187a  mov     ebx, eax
0x18005187c  test    eax, eax
0x18005187e  jnz     loc_180051DD4
0x180051884  lea     ecx, [rax+1]
0x180051887  mov     [rbp+3Fh+var_88], 0FFFFFFFFh
0x18005188e  and     esi, 0A000h
0x180051894  mov     [rbp+3Fh+var_98], ecx
0x180051897  mov     [rbp+3Fh+var_80], esi
0x18005189a  mov     ebx, ecx
0x18005189c  mov     eax, ecx
0x18005189e  lock xadd [r15+0B4h], eax
0x1800518a7  add     eax, ecx
0x1800518a9  mov     [rbp+3Fh+var_84], eax
0x1800518ac  test    esi, esi
0x1800518ae  jnz     loc_180051D37
0x1800518b4  cmp     dword ptr [r14+4], 0Eh
0x1800518b9  jz      loc_180051DE2
0x1800518bf  cmp     dword ptr [r14+4], 19h
0x1800518c4  jz      loc_180051DE2
0x1800518ca  mov     edi, [rbp+3Fh+var_94]
0x1800518cd  lea     r14, [rbp+3Fh+var_90]
0x1800518d1  xor     ebx, ebx
0x1800518d3  mov     [rbp+3Fh+var_78], edi
0x1800518d6  test    edi, edi
0x1800518d8  jle     short loc_180051949
0x1800518da  mov     r15, [rbp+3Fh+arg_10]
0x1800518de  or      r13d, 0FFFFFFFFh
0x1800518e2  movsxd  rax, ebx
0x1800518e5  lea     r8, [rbp+3Fh+var_90]
0x1800518e9  mov     rsi, [rbp+rax*8+3Fh+var_58]
0x1800518ee  lea     r8, [r8+rax*4]
0x1800518f2  mov     eax, [rsi+48h]
0x1800518f5  lea     rdx, [rsi+18h]; Buf2
0x1800518f9  mov     ecx, [rdx+20h]
0x1800518fc  test    cl, 2
0x1800518ff  mov     [r8], eax
0x180051902  mov     rax, rsi
0x180051905  cmovz   rax, r12
0x180051909  mov     r12, rax
0x18005190c  mov     eax, 1
0x180051911  test    eax, ecx
0x180051913  cmovz   r8, r14
0x180051917  cmovnz  edi, eax
0x18005191a  test    dword ptr [r15+48h], 0A000h
0x180051922  mov     r14, r8
0x180051925  jnz     loc_180051D7B
0x18005192b  mov     rcx, rsi; this
0x18005192e  call    ?AddReference@OSF_BINDING@@QEAAXXZ; OSF_BINDING::AddReference(void)
0x180051933  inc     ebx
0x180051935  cmp     ebx, [rbp+3Fh+var_94]
0x180051938  jl      short loc_1800518E2
0x18005193a  mov     r15, [rbp+3Fh+arg_0]
0x18005193e  mov     [rbp+3Fh+var_88], r13d
0x180051942  mov     r13, [rbp+3Fh+arg_8]
0x180051946  mov     [rbp+3Fh+var_78], edi
0x180051949  cmp     [rbp+3Fh+arg_20], 0
0x18005194d  mov     rsi, [rbp+3Fh+arg_28]
0x180051951  jnz     loc_180051CF0
0x180051957  call    cs:__imp_GetCurrentThreadId
0x18005195d  mov     ebx, eax
0x18005195f  mov     rax, [rbp+3Fh+arg_10]
0x180051963  test    dword ptr [rax+48h], 2000h
0x18005196a  jnz     loc_180051E1E
0x180051970  mov     ecx, [rbp+3Fh+var_98]
0x180051973  mov     edx, [rbp+3Fh+var_80]
0x180051976  lea     rax, [rbp+3Fh+var_68]
0x18005197a  mov     [rsp+58h], rax
0x18005197f  mov     r8d, ecx
0x180051982  lea     rax, [rbp+3Fh+var_74]
0x180051986  mov     r9d, ebx
0x180051989  mov     [rsp+100h+var_B0], rax
0x18005198e  mov     rcx, r15
0x180051991  lea     rax, [rbp+3Fh+var_7C]
0x180051995  mov     [rsp+100h+var_B8], rax
0x18005199a  lea     rax, [rbp+3Fh+var_A0]
0x18005199e  mov     [rsp+100h+var_C0], rax
0x1800519a3  mov     eax, [r13+1E8h]
0x1800519aa  mov     dword ptr [rsp+100h+var_C8], edi
0x1800519ae  mov     [rsp+100h+var_D0], r14
0x1800519b3  mov     dword ptr [rsp+100h+var_D8], eax
0x1800519b7  mov     rax, [rbp+3Fh+arg_18]
0x1800519bb  mov     [rsp+100h+var_E0], rax
0x1800519c0  call    ?LookForExistingConnection@OSF_CASSOCIATION@@AEAAJHHKPEAUCLIENT_AUTH_INFO@@W4tagNamedPipeType@@PEAHHPEAPEAVOSF_CCONNECTION@@2PEAW4OSF_CCALL_STATE@@PEAPEAVCSECURITY_CONTEXT@@@Z; OSF_CASSOCIATION::LookForExistingConnection(int,int,ulong,CLIENT_AUTH_INFO *,tagNamedPipeType,int *,int,OSF_CCONNECTION * *,int *,OSF_CCALL_STATE *,CSECURITY_CONTEXT * *)
0x1800519c5  mov     [rbp+3Fh+var_70], eax
0x1800519c8  mov     ebx, eax
0x1800519ca  test    eax, eax
0x1800519cc  jnz     loc_180051C9D
0x1800519d2  mov     rdi, [rbp+3Fh+var_A0]
0x1800519d6  test    rdi, rdi
0x1800519d9  jnz     loc_180051B40
0x1800519df  mov     eax, [r15+13Ch]
0x1800519e6  test    al, 10h
0x1800519e8  jnz     loc_180051E4E
0x1800519ee  mov     edi, [rbp+3Fh+arg_20]
0x1800519f1  lea     rax, [rbp+3Fh+var_A0]
0x1800519f5  mov     r9d, [rbp+3Fh+var_98]; int
0x1800519f9  mov     rdx, r13; struct OSF_BINDING_HANDLE *
0x1800519fc  mov     r8d, [rbp+3Fh+var_80]; int
0x180051a00  mov     rcx, r15; this
0x180051a03  mov     [rsp+100h+var_C0], rax; struct OSF_CCONNECTION **
0x180051a08  mov     rax, [rbp+3Fh+arg_18]
0x180051a0c  mov     dword ptr [rsp+100h+var_C8], 0; int
0x180051a14  mov     [rsp+100h+var_D0], rax; struct CLIENT_AUTH_INFO *
0x180051a19  mov     [rsp+100h+var_D8], rsi; struct OSF_CCALL **
0x180051a1e  mov     dword ptr [rsp+100h+var_E0], edi; int
0x180051a22  call    ?CreateConnection@OSF_CASSOCIATION@@AEAAJPEAVOSF_BINDING_HANDLE@@HHHPEAPEAVOSF_CCALL@@PEAUCLIENT_AUTH_INFO@@HPEAPEAVOSF_CCONNECTION@@@Z; OSF_CASSOCIATION::CreateConnection(OSF_BINDING_HANDLE *,int,int,int,OSF_CCALL * *,CLIENT_AUTH_INFO *,int,OSF_CCONNECTION * *)
0x180051a27  lea     rcx, [r15+0B8h]; CriticalSection
0x180051a2e  mov     ebx, eax
0x180051a30  call    cs:__imp_RtlLeaveCriticalSection
0x180051a36  test    ebx, ebx
0x180051a38  jnz     loc_180051AD6
0x180051a3e  lea     ecx, [rbx+1]
0x180051a41  cmp     [rbp+3Fh+var_94], ecx
0x180051a44  jz      loc_180051BD5
0x180051a4a  mov     rax, [rbp+3Fh+arg_10]
0x180051a4e  test    dword ptr [rax+48h], 0A000h
0x180051a55  jnz     loc_180051DC2
0x180051a5b  xor     ebx, ebx
0x180051a5d  xor     r14d, r14d
0x180051a60  mov     rax, [rbp+3Fh+var_68]
0x180051a64  test    edi, edi
0x180051a66  mov     rdi, [rbp+3Fh+var_A0]
0x180051a6a  jnz     loc_180051D98
0x180051a70  mov     [rsp+100h+var_C0], rax
0x180051a75  mov     r9, r12
0x180051a78  mov     eax, [rbp+3Fh+var_84]
0x180051a7b  mov     r8, rbx
0x180051a7e  mov     [rsp+100h+var_C8], rdi
0x180051a83  mov     rdx, r13
0x180051a86  mov     [rsp+100h+var_D0], r14; int
0x180051a8b  mov     dword ptr [rsp+100h+var_D8], ecx; int
0x180051a8f  mov     rcx, [rsi]
0x180051a92  mov     dword ptr [rsp+100h+var_E0], eax
0x180051a96  call    ?ActivateCall@OSF_CCALL@@QEAAJPEAVOSF_BINDING_HANDLE@@PEAVOSF_BINDING@@1KW4OSF_CCALL_STATE@@PEAURPC_DISPATCH_TABLE@@PEAVOSF_CCONNECTION@@PEAVCSECURITY_CONTEXT@@@Z; OSF_CCALL::ActivateCall(OSF_BINDING_HANDLE *,OSF_BINDING *,OSF_BINDING *,ulong,OSF_CCALL_STATE,RPC_DISPATCH_TABLE *,OSF_CCONNECTION *,CSECURITY_CONTEXT *)
0x180051a9b  mov     ebx, eax
0x180051a9d  test    eax, eax
0x180051a9f  jnz     loc_18005200F
0x180051aa5  mov     rax, [rbp+3Fh+arg_10]
0x180051aa9  test    dword ptr [rax+48h], 2000h
0x180051ab0  jnz     loc_18005202E
0x180051ab6  cmp     [rbp+3Fh+var_80], 0
0x180051aba  jnz     loc_18005203E
0x180051ac0  mov     eax, ebx
0x180051ac2  add     rsp, 0C8h
0x180051ac9  pop     r15
0x180051acb  pop     r14
0x180051acd  pop     r13
0x180051acf  pop     r12
0x180051ad1  pop     rdi
0x180051ad2  pop     rsi
0x180051ad3  pop     rbx
0x180051ad4  pop     rbp
0x180051ad5  retn
0x180051ad6  mov     rdi, [rbp+3Fh+var_A0]
0x180051ada  mov     rdx, r12; struct OSF_BINDING *
0x180051add  xor     ecx, ecx; struct OSF_BINDING *
0x180051adf  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x180051ae4  test    rdi, rdi
0x180051ae7  jz      short loc_180051AC0
0x180051ae9  cmp     [rbp+3Fh+arg_20], 0
0x180051aed  jz      short loc_180051B16
0x180051aef  cmp     qword ptr [rdi+48h], 0
0x180051af4  jz      short loc_180051AFE
0x180051af6  mov     qword ptr [rdi+48h], 0
0x180051afe  mov     rax, [rsi]
0x180051b01  cmp     qword ptr [rax+110h], 0
0x180051b09  jz      short loc_180051B16
0x180051b0b  mov     qword ptr [rax+110h], 0
0x180051b16  mov     eax, [rdi+70h]
0x180051b19  test    al, 20h
0x180051b1b  jnz     short loc_180051B25
0x180051b1d  mov     rcx, rdi; this
0x180051b20  call    ?ReleaseCausalOrder@OSF_CCONNECTION@@QEAAXXZ; OSF_CCONNECTION::ReleaseCausalOrder(void)
0x180051b25  test    rdi, rdi
0x180051b28  jz      short loc_180051AC0
0x180051b2a  mov     rax, [rdi]
0x180051b2d  mov     edx, 1
0x180051b32  mov     rcx, rdi
0x180051b35  mov     rax, [rax+8]
0x180051b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b3e  jmp     short loc_180051AC0
0x180051b40  mov     eax, 1
0x180051b45  cmp     [rbp+3Fh+var_78], eax
0x180051b48  jnz     loc_180051D05
0x180051b4e  cmp     [rbp+3Fh+arg_20], 0
0x180051b52  jnz     loc_180051CD6
0x180051b58  lea     rax, [rbp+3Fh+var_90]
0x180051b5c  sub     r14, rax
0x180051b5f  mov     eax, [rbp+3Fh+var_7C]
0x180051b62  sar     r14, 2
0x180051b66  test    eax, eax
0x180051b68  js      short loc_180051B6D
0x180051b6a  add     r14d, eax
0x180051b6d  movsxd  rax, r14d
0x180051b70  mov     rdx, r12; struct OSF_BINDING *
0x180051b73  mov     r13, [rbp+rax*8+3Fh+var_58]
0x180051b78  mov     rcx, r13; struct OSF_BINDING *
0x180051b7b  mov     rax, [r13+30h]
0x180051b7f  mov     [rbp+3Fh+var_A0], rax
0x180051b83  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x180051b88  mov     edx, [rbp+3Fh+var_74]
0x180051b8b  xor     r12d, r12d
0x180051b8e  mov     dword ptr [rbp+3Fh+arg_0], edx
0x180051b91  mov     r14, [rbp+3Fh+var_68]
0x180051b95  test    r14, r14
0x180051b98  jz      loc_1800520E2
0x180051b9e  mov     rcx, [rbp+3Fh+CriticalSection]; CriticalSection
0x180051ba2  call    cs:__imp_RtlLeaveCriticalSection
0x180051ba8  test    ebx, ebx
0x180051baa  jnz     loc_180051CB6
0x180051bb0  mov     r15d, [rbp+3Fh+arg_20]
0x180051bb4  mov     eax, [rdi+70h]
0x180051bb7  test    r15d, r15d
0x180051bba  jnz     loc_1800521C8
0x180051bc0  test    al, 20h
0x180051bc2  jz      short loc_180051BF5
0x180051bc4  mov     rcx, [rdi+48h]; this
0x180051bc8  mov     [rsi], rcx
0x180051bcb  call    ?SetActivityIDFromThread@CALL@@QEAAXXZ; CALL::SetActivityIDFromThread(void)
0x180051bd0  mov     rcx, [rsi]
0x180051bd3  jmp     short loc_180051C16
0x180051bd5  mov     rbx, [rbp+3Fh+var_58]
0x180051bd9  mov     rdx, r12; struct OSF_BINDING *
0x180051bdc  mov     rcx, rbx; struct OSF_BINDING *
0x180051bdf  mov     r14, [rbx+30h]
0x180051be3  call    ?ReleaseBindingListWithException@@YAXPEAVOSF_BINDING@@0@Z; ReleaseBindingListWithException(OSF_BINDING *,OSF_BINDING *)
0x180051be8  xor     r12d, r12d
0x180051beb  lea     ecx, [r12+1]
0x180051bf0  jmp     loc_180051A60
0x180051bf5  mov     rdx, rsi; struct OSF_CCALL **
0x180051bf8  mov     rcx, rdi; this
0x180051bfb  call    ?AllocateCCall@OSF_CCONNECTION@@QEAAJPEAPEAVOSF_CCALL@@@Z; OSF_CCONNECTION::AllocateCCall(OSF_CCALL * *)
0x180051c00  mov     ebx, eax
0x180051c02  test    eax, eax
0x180051c04  jnz     loc_180051CB6
0x180051c0a  mov     rcx, [rsi]
0x180051c0d  test    r15d, r15d
0x180051c10  jnz     loc_180052229
0x180051c16  mov     rax, [rbp+3Fh+var_A0]
0x180051c1a  mov     r9, r12
0x180051c1d  mov     rdx, [rbp+3Fh+arg_8]
0x180051c21  mov     r8, r13
0x180051c24  mov     [rsp+100h+var_C0], r14
0x180051c29  mov     [rsp+100h+var_C8], rdi
0x180051c2e  mov     [rsp+100h+var_D0], rax
0x180051c33  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x180051c36  mov     dword ptr [rsp+100h+var_D8], eax
0x180051c3a  mov     eax, [rbp+3Fh+var_84]
0x180051c3d  mov     dword ptr [rsp+100h+var_E0], eax
0x180051c41  call    ?ActivateCall@OSF_CCALL@@QEAAJPEAVOSF_BINDING_HANDLE@@PEAVOSF_BINDING@@1KW4OSF_CCALL_STATE@@PEAURPC_DISPATCH_TABLE@@PEAVOSF_CCONNECTION@@PEAVCSECURITY_CONTEXT@@@Z; OSF_CCALL::ActivateCall(OSF_BINDING_HANDLE *,OSF_BINDING *,OSF_BINDING *,ulong,OSF_CCALL_STATE,RPC_DISPATCH_TABLE *,OSF_CCONNECTION *,CSECURITY_CONTEXT *)
0x180051c46  mov     ebx, eax
0x180051c48  test    eax, eax
0x180051c4a  jnz     short loc_180051C78
  ... truncated ...
```
