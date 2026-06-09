# CRemoteMachine::Activate(ACTIVATION_PARAMS *,ushort *)

- ea: `0x1800f8b2c`
- end: `0x1800f9475`
- name: `?Activate@CRemoteMachine@@QEAAJPEAUACTIVATION_PARAMS@@PEAG@Z`
- size: `2377`
- prototype: `__int64 __fastcall(CRemoteMachine *__hidden this, struct ACTIVATION_PARAMS *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fab44`

## callees

- `0x180018d24`
- `0x180018d8c`
- `0x18001a374`
- `0x180034260`
- `0x180034ce4`
- `0x180046930`
- `0x180046994`
- `0x1800835c0`
- `0x18008578c`
- `0x1800b7ac0`
- `0x1800c5c38`
- `0x1800c6e78`
- `0x1800ca28c`
- `0x1800f8688`
- `0x1800f8b2c`
- `0x1800f9490`
- `0x1800f9a30`
- `0x1800f9b6c`
- `0x1800fa084`
- `0x1800fa1b0`
- `0x1800fb0f4`
- `0x180112d84`
- `0x180114010`

## import_xrefs

- `RPCRT4!RpcBindingReset` at `0x1800f9060`
- `RPCRT4!RpcBindingReset` at `0x1800f9060`
- `RPCRT4!RpcBindingFree` at `0x1800f8e2b`
- `RPCRT4!RpcBindingFree` at `0x1800f9045`
- `RPCRT4!RpcBindingFree` at `0x1800f912d`
- `RPCRT4!RpcBindingFree` at `0x1800f943a`
- `RPCRT4!RpcBindingFree` at `0x1800f8e2b`
- `RPCRT4!RpcBindingFree` at `0x1800f9045`
- `RPCRT4!RpcBindingFree` at `0x1800f912d`
- `RPCRT4!RpcBindingFree` at `0x1800f943a`
- `RPCRT4!RpcBindingCopy` at `0x1800f8d1b`
- `RPCRT4!RpcBindingCopy` at `0x1800f901d`
- `RPCRT4!RpcBindingCopy` at `0x1800f8d1b`
- `RPCRT4!RpcBindingCopy` at `0x1800f901d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8c16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f9348`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8c16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f9348`

## string_xrefs

- `0x1800f8dae`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f8ec2`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f8fbd`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f9117`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f9139`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f92db`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f93b6`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`

## pseudocode

```c
int __fastcall CRemoteMachine::Activate(
        const unsigned __int16 **this,
        struct ACTIVATION_PARAMS *a2,
        unsigned __int16 *a3)
{
  _DWORD *v3; // rax
  unsigned __int16 *v4; // r12
  unsigned __int16 v7; // r15
  int result; // eax
  struct CMachineBinding *v9; // rax
  struct CMachineBinding *v10; // rdi
  unsigned __int64 v11; // rax
  void *v12; // rax
  int v13; // eax
  int v14; // r14d
  const WCHAR *v15; // r13
  __int64 v16; // rax
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdi
  RPC_STATUS v20; // r14d
  unsigned __int16 v21; // di
  __int64 v22; // rax
  const unsigned __int16 *v23; // r12
  const WCHAR *v24; // rdi
  CGuidStr *v25; // rax
  int v26; // ecx
  int v27; // r11d
  int v28; // edi
  __int64 v29; // rax
  const unsigned __int16 *v30; // r14
  CGuidStr *v31; // rax
  int v32; // r11d
  int v33; // ecx
  int v34; // r15d
  RPC_STATUS v35; // edi
  __int64 v36; // rax
  const unsigned __int16 *v37; // r12
  const WCHAR *v38; // r14
  CGuidStr *v39; // rax
  int v40; // r11d
  int v41; // ecx
  unsigned int v42; // r15d
  RPC_BINDING_HANDLE *v43; // rcx
  RPC_BINDING_HANDLE *v44; // rcx
  RPC_BINDING_HANDLE *v45; // rax
  __int64 v46; // rax
  const unsigned __int16 *v47; // r15
  const WCHAR *v48; // r14
  CGuidStr *v49; // rax
  int v50; // ecx
  int v51; // r11d
  int v52; // r8d
  unsigned __int16 v53; // r14
  unsigned int v54; // ecx
  __int64 v55; // rax
  const unsigned __int16 *v56; // r14
  __int64 v57; // rax
  __int64 v58; // rax
  const unsigned __int16 *v59; // r15
  const WCHAR *v60; // r14
  CGuidStr *v61; // rax
  int v62; // r11d
  int v63; // ecx
  CDualStringArray *v64; // rcx
  _DWORD *v65; // rdx
  __int64 v66; // rax
  CDualStringArray *v67; // rcx
  CSharedLock *v68; // rcx
  CGuidStr *v69; // rax
  int v70; // r11d
  int v71; // ecx
  __int64 v72; // [rsp+30h] [rbp-D0h]
  __int64 v73; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v74; // [rsp+50h] [rbp-B0h]
  int v75; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int AuthnLevel; // [rsp+58h] [rbp-A8h] BYREF
  RPC_BINDING_HANDLE DestinationBinding; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v79; // [rsp+70h] [rbp-90h]
  void **v80; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v81; // [rsp+88h] [rbp-78h]
  int v82; // [rsp+98h] [rbp-68h]
  int v83; // [rsp+A8h] [rbp-58h]
  __int64 v84; // [rsp+B0h] [rbp-50h]
  __int128 v85; // [rsp+C0h] [rbp-40h]
  __int64 v86; // [rsp+D0h] [rbp-30h]
  int v87; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v88; // [rsp+E0h] [rbp-20h]
  _BYTE v89[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v90[80]; // [rsp+140h] [rbp+40h] BYREF

  v3 = (_DWORD *)*((_QWORD *)a2 + 3);
  v79 = a3;
  v4 = a3;
  DestinationBinding = 0;
  v75 = -2147024882;
  AuthnLevel = 0;
  if ( v3 )
  {
    if ( *v3 == -1 )
      *v3 = 9;
    v7 = **((_WORD **)a2 + 3);
  }
  else
  {
    v7 = -1;
  }
  result = CRemoteMachine::GetAuthnLevel((CRemoteMachine *)this, a2, &AuthnLevel);
  v75 = result;
  if ( result >= 0 )
  {
    v9 = CRemoteMachine::LookupBinding(
           (CRemoteMachine *)this,
           (void *)(*((_QWORD *)a2 + 2) + 156LL),
           v7,
           AuthnLevel,
           *((struct _COAUTHINFO **)a2 + 3));
    v10 = v9;
    if ( !v9 )
    {
      v14 = 1766;
LABEL_20:
      v74 = 0;
      if ( AuthnLevel < 2 )
        AuthnLevel = 5;
      v15 = &Class;
      if ( v14 == 1722 || v14 == 1753 )
      {
        CRemoteMachine::FlushBindings((CRemoteMachine *)this);
        goto LABEL_50;
      }
      CSharedLock::LockShared(gpRemoteMachineLock);
      v16 = (__int64)this[6];
      v17 = (const unsigned __int16 *)(v16 - 16);
      v18 = -v16;
      v19 = (unsigned __int64)v17 & -(__int64)(v18 != 0);
      if ( v19 )
      {
        v20 = RpcBindingCopy(
                *(RPC_BINDING_HANDLE *)(((unsigned __int64)v17 & -(__int64)(v18 != 0)) + 0x28),
                &DestinationBinding);
        if ( !v20 )
        {
          v21 = *(_WORD *)(v19 + 56);
          v74 = v21;
LABEL_36:
          CSharedLock::UnlockShared((CSharedLock *)gpRemoteMachineLock);
          if ( DestinationBinding )
          {
            v28 = CRemoteMachine::PickAuthnAndActivate(
                    (CRemoteMachine *)this,
                    a2,
                    v4,
                    &DestinationBinding,
                    v7,
                    AuthnLevel,
                    v21,
                    &v75);
            if ( !v28 )
              return v75;
            RpcBindingFree(&DestinationBinding);
            DestinationBinding = 0;
            if ( v28 != 1722 && v28 != 1753 )
            {
              if ( dword_1801574B8
                || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_1801574B8) )
              {
                v29 = *((_QWORD *)a2 + 1);
                v30 = this[3];
                if ( v29 )
                  v15 = *(const WCHAR **)(v29 + 384);
                v31 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v73) = v28;
                LODWORD(v72) = v32;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v33,
                  (unsigned int)"CRemoteMachine::Activate",
                  909,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  v31,
                  v72,
                  v15,
                  v30,
                  v73);
              }
              if ( v28 == 5 )
                return -2147024891;
              LogRemoteSideUnreachable(a2, this[3], 0, 0xFFFFFFFF);
              return -2147023174;
            }
          }
LABEL_50:
          v81 = 0;
          v80 = &CRemActPPing::`vftable';
          v34 = 0;
          v88 = this[3];
          v82 = 0;
          v83 = 1722;
          v84 = 0;
          v85 = 0;
          v86 = 0;
          v87 = 0;
LABEL_51:
          v35 = CParallelPing::Ping((CParallelPing *)&v80);
          if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
          {
            v36 = *((_QWORD *)a2 + 1);
            v37 = this[3];
            if ( v36 )
              v38 = *(const WCHAR **)(v36 + 384);
            else
              v38 = &Class;
            v39 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
            LODWORD(v73) = v35;
            LODWORD(v72) = v40;
            ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
              v41,
              (unsigned int)"CRemoteMachine::Activate",
              940,
              3,
              (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
              v39,
              v72,
              v38,
              v37,
              v73);
          }
          if ( v35 == 1717 )
          {
            if ( v34 )
            {
              v53 = v74;
              goto LABEL_84;
            }
            v42 = 0;
            if ( v81 )
            {
              while ( 1 )
              {
                Binding = 0;
                v43 = *((_QWORD *)&v85 + 1) ? *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v85 + 1) + 8LL * v42) : 0LL;
                v35 = RpcBindingCopy(*v43, &Binding);
                if ( v35 )
                  break;
                if ( *((_QWORD *)&v85 + 1) )
                  v44 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v85 + 1) + 8LL * v42);
                else
                  v44 = 0;
                v35 = RpcBindingFree(v44);
                if ( v35 )
                {
                  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v57 = *((_QWORD *)a2 + 1);
                    v47 = this[3];
                    if ( v57 )
                      v48 = *(const WCHAR **)(v57 + 384);
                    else
                      v48 = &Class;
                    v49 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
                    v52 = 969;
LABEL_81:
                    LODWORD(v73) = v35;
                    LODWORD(v72) = v51;
                    ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                      v50,
                      (unsigned int)"CRemoteMachine::Activate",
                      v52,
                      0,
                      (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                      v49,
                      v72,
                      v48,
                      v47,
                      v73);
                  }
LABEL_82:
                  RpcBindingFree(&Binding);
                  goto LABEL_83;
                }
                v35 = RpcBindingReset(Binding);
                if ( v35 )
                {
                  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v46 = *((_QWORD *)a2 + 1);
                    v47 = this[3];
                    if ( v46 )
                      v48 = *(const WCHAR **)(v46 + 384);
                    else
                      v48 = &Class;
                    v49 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
                    v52 = 981;
                    goto LABEL_81;
                  }
                  goto LABEL_82;
                }
                if ( *((_QWORD *)&v85 + 1) )
                  v45 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v85 + 1) + 8LL * v42);
                else
                  v45 = 0;
                ++v42;
                *v45 = Binding;
                if ( v42 >= v81 )
                {
                  v34 = 1;
                  goto LABEL_51;
                }
              }
              if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v58 = *((_QWORD *)a2 + 1);
                v59 = this[3];
                if ( v58 )
                  v60 = *(const WCHAR **)(v58 + 384);
                else
                  v60 = &Class;
                v61 = CGuidStr::CGuidStr((CGuidStr *)v90, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v73) = v35;
                LODWORD(v72) = v62;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v63,
                  (unsigned int)"CRemoteMachine::Activate",
                  957,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  v61,
                  v72,
                  v60,
                  v59,
                  v73);
              }
            }
          }
          else if ( !v35 )
          {
            CSharedLock::LockExclusive((CSharedLock *)gpRemoteMachineLock);
            v64 = (CDualStringArray *)this[5];
            if ( v64 )
            {
              this[5] = 0;
              CDualStringArray::Release(v64);
            }
            Binding = 0;
            DestinationBinding = *(RPC_BINDING_HANDLE *)v86;
            *(_QWORD *)v86 = 0;
            v65 = HeapAlloc(g_hHeap, 0, 0x10u);
            if ( v65 )
            {
              v66 = v85;
              *(_QWORD *)&v85 = 0;
              *(_QWORD *)v65 = v66;
              v65[2] = 1;
            }
            else
            {
              v65 = 0;
            }
            ObjectLibrary::ReferencedPtr<CDualStringArray>::Attach(&Binding, v65);
            v67 = (CDualStringArray *)this[5];
            this[5] = (const unsigned __int16 *)Binding;
            if ( v67 )
              CDualStringArray::Release(v67);
            v68 = (CSharedLock *)gpRemoteMachineLock;
            v53 = *(_WORD *)(v86 + 16);
            *((_DWORD *)this + 19) = *(_DWORD *)(v86 + 8);
            CSharedLock::UnlockExclusive(v68);
            goto LABEL_84;
          }
LABEL_83:
          v53 = v74;
LABEL_84:
          CParallelPing::Reset((CParallelPing *)&v80);
          CParallelPing::~CParallelPing((CParallelPing *)&v80);
          if ( v35 )
            goto LABEL_128;
          if ( !DestinationBinding )
            return v75;
          v75 = CRemoteMachine::GetAuthnLevel((CRemoteMachine *)this, a2, &AuthnLevel);
          if ( v75 >= 0 )
          {
            v54 = AuthnLevel;
            if ( AuthnLevel < 2 )
            {
              v54 = 5;
              AuthnLevel = 5;
            }
            v35 = CRemoteMachine::PickAuthnAndActivate(
                    (CRemoteMachine *)this,
                    a2,
                    v79,
                    &DestinationBinding,
                    0,
                    v54,
                    v53,
                    &v75);
            if ( v35 )
            {
LABEL_128:
              if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v55 = *((_QWORD *)a2 + 1);
                v56 = this[3];
                if ( v55 )
                  v15 = *(const WCHAR **)(v55 + 384);
                v69 = CGuidStr::CGuidStr((CGuidStr *)v90, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v73) = v35;
                LODWORD(v72) = v70;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v71,
                  (unsigned int)"CRemoteMachine::Activate",
                  1051,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  v69,
                  v72,
                  v15,
                  v56,
                  v73);
              }
              if ( v35 == 5 )
              {
                v75 = -2147024891;
              }
              else
              {
                LogRemoteSideUnreachable(a2, this[3], 0, 0xFFFFFFFF);
                v75 = -2147023174;
              }
            }
          }
          if ( DestinationBinding )
            RpcBindingFree(&DestinationBinding);
          return v75;
        }
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v22 = *((_QWORD *)a2 + 1);
          v23 = this[3];
          if ( v22 )
            v24 = *(const WCHAR **)(v22 + 384);
          else
            v24 = &Class;
          v25 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
          ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
            v26,
            (unsigned int)"CRemoteMachine::Activate",
            877,
            0,
            (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
            v25,
            v27,
            v24,
            v23,
            v20);
          v4 = v79;
        }
        DestinationBinding = 0;
      }
      v21 = 0;
      goto LABEL_36;
    }
    v7 = *((_WORD *)v9 + 29);
    *((_DWORD *)a2 + 10) = 0;
    *((_QWORD *)a2 + 6) = 0;
    if ( *((_DWORD *)v9 + 18) )
    {
      v11 = *((unsigned int *)v9 + 18);
      if ( v11 >= v11 + 7
        || (v12 = HeapAlloc(g_hHeap, 0, (v11 + 7) & 0xFFFFFFFFFFFFFFF8uLL), (*((_QWORD *)a2 + 6) = v12) == 0) )
      {
        v14 = 8;
LABEL_17:
        CRemoteMachine::RemoveBinding((CRemoteMachine *)this, v10);
LABEL_18:
        (*(void (__fastcall **)(struct CMachineBinding *))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_20;
      }
      memcpy_0(v12, *((const void **)v10 + 10), *((unsigned int *)v10 + 18));
      *((_DWORD *)a2 + 10) = *((_DWORD *)v10 + 18);
    }
    v13 = CRemoteMachine::CallRemoteMachine(
            (CRemoteMachine *)this,
            *((void **)v10 + 5),
            *((_WORD *)v10 + 28),
            a2,
            v4,
            &v75);
    v14 = v13;
    if ( !v13 )
    {
      *((_WORD *)a2 + 18) = v7;
      (*(void (__fastcall **)(struct CMachineBinding *))(*(_QWORD *)v10 + 16LL))(v10);
      return v75;
    }
    if ( v13 == 5 || v13 == 1825 )
      goto LABEL_18;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x1800f8b2c  mov     [rsp-8+arg_18], rbx
0x1800f8b31  push    rbp
0x1800f8b32  push    rsi
0x1800f8b33  push    rdi
0x1800f8b34  push    r12
0x1800f8b36  push    r13
0x1800f8b38  push    r14
0x1800f8b3a  push    r15
0x1800f8b3c  lea     rbp, [rsp-0A0h]
0x1800f8b44  sub     rsp, 1A0h
0x1800f8b4b  mov     rax, cs:__security_cookie
0x1800f8b52  xor     rax, rsp
0x1800f8b55  mov     [rbp+0D0h+var_40], rax
0x1800f8b5c  mov     rax, [rdx+18h]
0x1800f8b60  xor     r13d, r13d
0x1800f8b63  mov     [rsp+1D0h+var_160], r8
0x1800f8b68  mov     r12, r8
0x1800f8b6b  mov     [rsp+1D0h+DestinationBinding], r13
0x1800f8b70  mov     rbx, rdx
0x1800f8b73  mov     [rsp+1D0h+var_17C], 8007000Eh
0x1800f8b7b  mov     rsi, rcx
0x1800f8b7e  mov     [rsp+1D0h+AuthnLevel], r13d
0x1800f8b83  test    rax, rax
0x1800f8b86  jz      short loc_1800F8B9D
0x1800f8b88  cmp     dword ptr [rax], 0FFFFFFFFh
0x1800f8b8b  jnz     short loc_1800F8B93
0x1800f8b8d  mov     dword ptr [rax], 9
0x1800f8b93  mov     rax, [rdx+18h]
0x1800f8b97  movzx   r15d, word ptr [rax]
0x1800f8b9b  jmp     short loc_1800F8BA3
0x1800f8b9d  mov     r15d, 0FFFFh
0x1800f8ba3  lea     r8, [rsp+1D0h+AuthnLevel]; unsigned int *
0x1800f8ba8  call    ?GetAuthnLevel@CRemoteMachine@@AEAAJPEAUACTIVATION_PARAMS@@PEAK@Z; CRemoteMachine::GetAuthnLevel(ACTIVATION_PARAMS *,ulong *)
0x1800f8bad  mov     [rsp+1D0h+var_17C], eax
0x1800f8bb1  test    eax, eax
0x1800f8bb3  js      loc_1800F944A
0x1800f8bb9  mov     rdx, [rbx+10h]
0x1800f8bbd  movzx   r8d, r15w; unsigned __int16
0x1800f8bc1  mov     rax, [rbx+18h]
0x1800f8bc5  add     rdx, 9Ch; void *
0x1800f8bcc  mov     r9d, [rsp+1D0h+AuthnLevel]; unsigned int
0x1800f8bd1  mov     rcx, rsi; this
0x1800f8bd4  mov     [rsp+1D0h+var_1B0], rax; struct _COAUTHINFO *
0x1800f8bd9  call    ?LookupBinding@CRemoteMachine@@AEAAPEAVCMachineBinding@@PEAXGKPEAU_COAUTHINFO@@@Z; CRemoteMachine::LookupBinding(void *,ushort,ulong,_COAUTHINFO *)
0x1800f8bde  mov     rdi, rax
0x1800f8be1  test    rax, rax
0x1800f8be4  jz      loc_1800F8CB4
0x1800f8bea  movzx   r15d, word ptr [rax+3Ah]
0x1800f8bef  mov     [rbx+28h], r13d
0x1800f8bf3  mov     [rbx+30h], r13
0x1800f8bf7  cmp     [rax+48h], r13d
0x1800f8bfb  jz      short loc_1800F8C41
0x1800f8bfd  mov     eax, [rax+48h]
0x1800f8c00  lea     r8, [rax+7]
0x1800f8c04  cmp     rax, r8
0x1800f8c07  ja      short loc_1800F8C84
0x1800f8c09  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f8c10  and     r8, 0FFFFFFFFFFFFFFF8h; dwBytes
0x1800f8c14  xor     edx, edx; dwFlags
0x1800f8c16  call    cs:__imp_HeapAlloc
0x1800f8c1d  nop     dword ptr [rax+rax+00h]
0x1800f8c22  mov     [rbx+30h], rax
0x1800f8c26  test    rax, rax
0x1800f8c29  jz      short loc_1800F8C84
0x1800f8c2b  mov     r8d, [rdi+48h]; Size
0x1800f8c2f  mov     rcx, rax; void *
0x1800f8c32  mov     rdx, [rdi+50h]; Src
0x1800f8c36  call    memcpy_0
0x1800f8c3b  mov     eax, [rdi+48h]
0x1800f8c3e  mov     [rbx+28h], eax
0x1800f8c41  movzx   r8d, word ptr [rdi+38h]; unsigned __int16
0x1800f8c46  lea     rax, [rsp+1D0h+var_17C]
0x1800f8c4b  mov     rdx, [rdi+28h]; void *
0x1800f8c4f  mov     r9, rbx; struct ACTIVATION_PARAMS *
0x1800f8c52  mov     [rsp+1D0h+var_1A8], rax; int *
0x1800f8c57  mov     rcx, rsi; this
0x1800f8c5a  mov     [rsp+1D0h+var_1B0], r12; unsigned __int16 *
0x1800f8c5f  call    ?CallRemoteMachine@CRemoteMachine@@AEAAJPEAXGPEAUACTIVATION_PARAMS@@PEAGPEAJ@Z; CRemoteMachine::CallRemoteMachine(void *,ushort,ACTIVATION_PARAMS *,ushort *,long *)
0x1800f8c64  mov     r14d, eax
0x1800f8c67  test    eax, eax
0x1800f8c69  jnz     short loc_1800F8C8C
0x1800f8c6b  mov     [rbx+24h], r15w
0x1800f8c70  mov     rcx, rdi
0x1800f8c73  mov     rax, [rdi]
0x1800f8c76  mov     rax, [rax+10h]
0x1800f8c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8c7f  jmp     loc_1800F9446
0x1800f8c84  mov     r14d, 8
0x1800f8c8a  jmp     short loc_1800F8C98
0x1800f8c8c  cmp     eax, 5
0x1800f8c8f  jz      short loc_1800F8CA3
0x1800f8c91  cmp     eax, 721h
0x1800f8c96  jz      short loc_1800F8CA3
0x1800f8c98  mov     rdx, rdi; struct CMachineBinding *
0x1800f8c9b  mov     rcx, rsi; this
0x1800f8c9e  call    ?RemoveBinding@CRemoteMachine@@AEAAXPEAVCMachineBinding@@@Z; CRemoteMachine::RemoveBinding(CMachineBinding *)
0x1800f8ca3  mov     rax, [rdi]
0x1800f8ca6  mov     rcx, rdi
0x1800f8ca9  mov     rax, [rax+10h]
0x1800f8cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8cb2  jmp     short loc_1800F8CBA
0x1800f8cb4  mov     r14d, 6E6h
0x1800f8cba  cmp     [rsp+1D0h+AuthnLevel], 2
0x1800f8cbf  mov     dword ptr [rsp+1D0h+var_180], r13d
0x1800f8cc4  jnb     short loc_1800F8CCE
0x1800f8cc6  mov     [rsp+1D0h+AuthnLevel], 5
0x1800f8cce  lea     r13, Class
0x1800f8cd5  cmp     r14d, 6BAh
0x1800f8cdc  jz      loc_1800F8EFF
0x1800f8ce2  cmp     r14d, 6D9h
0x1800f8ce9  jz      loc_1800F8EFF
0x1800f8cef  mov     rcx, cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA; lpCriticalSection
0x1800f8cf6  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x1800f8cfb  mov     rax, [rsi+30h]
0x1800f8cff  lea     rcx, [rax-10h]
0x1800f8d03  neg     rax
0x1800f8d06  sbb     rdi, rdi
0x1800f8d09  and     rdi, rcx
0x1800f8d0c  jz      loc_1800F8DCD
0x1800f8d12  mov     rcx, [rdi+28h]; SourceBinding
0x1800f8d16  lea     rdx, [rsp+1D0h+DestinationBinding]; DestinationBinding
0x1800f8d1b  call    cs:__imp_RpcBindingCopy
0x1800f8d22  nop     dword ptr [rax+rax+00h]
0x1800f8d27  mov     r14d, eax
0x1800f8d2a  test    eax, eax
0x1800f8d2c  jnz     short loc_1800F8D3B
0x1800f8d2e  movzx   edi, word ptr [rdi+38h]
0x1800f8d32  mov     dword ptr [rsp+1D0h+var_180], edi
0x1800f8d36  jmp     loc_1800F8DD1
0x1800f8d3b  mov     eax, cs:dword_1801574B8
0x1800f8d41  test    eax, eax
0x1800f8d43  jnz     short loc_1800F8D58
0x1800f8d45  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f8d4b  jz      short loc_1800F8DC4
0x1800f8d4d  xor     ecx, ecx
0x1800f8d4f  call    IsWppLevelEnabled
0x1800f8d54  test    al, al
0x1800f8d56  jz      short loc_1800F8DC4
0x1800f8d58  mov     rax, [rbx+8]
0x1800f8d5c  mov     r12, [rsi+18h]
0x1800f8d60  test    rax, rax
0x1800f8d63  jz      short loc_1800F8D72
0x1800f8d65  mov     r11d, [rax+58h]
0x1800f8d69  mov     rdi, [rax+180h]
0x1800f8d70  jmp     short loc_1800F8D78
0x1800f8d72  mov     rdi, r13
0x1800f8d75  xor     r11d, r11d
0x1800f8d78  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f8d7c  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f8d80  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f8d85  mov     dword ptr [rsp+1D0h+var_188], r14d
0x1800f8d8a  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f8d91  mov     [rsp+1D0h+var_190], r12
0x1800f8d96  xor     r9d, r9d
0x1800f8d99  mov     [rsp+1D0h+var_198], rdi
0x1800f8d9e  mov     r8d, 36Dh
0x1800f8da4  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f8da9  mov     [rsp+1D0h+var_1A8], rax
0x1800f8dae  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f8db5  mov     [rsp+1D0h+var_1B0], rax
0x1800f8dba  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f8dbf  mov     r12, [rsp+1D0h+var_160]
0x1800f8dc4  mov     [rsp+1D0h+DestinationBinding], 0
0x1800f8dcd  mov     edi, dword ptr [rsp+1D0h+var_180]
0x1800f8dd1  mov     rcx, cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA; this
0x1800f8dd8  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x1800f8ddd  cmp     [rsp+1D0h+DestinationBinding], 0
0x1800f8de3  jz      loc_1800F8F07
0x1800f8de9  lea     rax, [rsp+1D0h+var_17C]
0x1800f8dee  mov     r8, r12; unsigned __int16 *
0x1800f8df1  mov     [rsp+1D0h+var_198], rax; int *
0x1800f8df6  lea     r9, [rsp+1D0h+DestinationBinding]; void **
0x1800f8dfb  mov     eax, [rsp+1D0h+AuthnLevel]
0x1800f8dff  mov     rdx, rbx; struct ACTIVATION_PARAMS *
0x1800f8e02  mov     [rsp+1D0h+var_1A0], di; unsigned __int16
0x1800f8e07  mov     rcx, rsi; this
0x1800f8e0a  mov     dword ptr [rsp+1D0h+var_1A8], eax; AuthnLevel
0x1800f8e0e  mov     word ptr [rsp+1D0h+var_1B0], r15w; unsigned __int16
0x1800f8e14  call    ?PickAuthnAndActivate@CRemoteMachine@@AEAAJPEAUACTIVATION_PARAMS@@PEAGPEAPEAXGKGPEAJ@Z; CRemoteMachine::PickAuthnAndActivate(ACTIVATION_PARAMS *,ushort *,void * *,ushort,ulong,ushort,long *)
0x1800f8e19  xor     r12d, r12d
0x1800f8e1c  mov     edi, eax
0x1800f8e1e  test    eax, eax
0x1800f8e20  jz      loc_1800F9446
0x1800f8e26  lea     rcx, [rsp+1D0h+DestinationBinding]; Binding
0x1800f8e2b  call    cs:__imp_RpcBindingFree
0x1800f8e32  nop     dword ptr [rax+rax+00h]
0x1800f8e37  mov     [rsp+1D0h+DestinationBinding], r12
0x1800f8e3c  cmp     edi, 6BAh
0x1800f8e42  jz      loc_1800F8F0A
0x1800f8e48  cmp     edi, 6D9h
0x1800f8e4e  jz      loc_1800F8F0A
0x1800f8e54  mov     ecx, cs:dword_1801574B8
0x1800f8e5a  test    ecx, ecx
0x1800f8e5c  jnz     short loc_1800F8E70
0x1800f8e5e  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f8e65  jz      short loc_1800F8ED3
0x1800f8e67  call    IsWppLevelEnabled
0x1800f8e6c  test    al, al
0x1800f8e6e  jz      short loc_1800F8ED3
0x1800f8e70  mov     rax, [rbx+8]
0x1800f8e74  mov     r14, [rsi+18h]
0x1800f8e78  test    rax, rax
0x1800f8e7b  jz      short loc_1800F8E8A
0x1800f8e7d  mov     r11d, [rax+58h]
0x1800f8e81  mov     r13, [rax+180h]
0x1800f8e88  jmp     short loc_1800F8E8D
0x1800f8e8a  mov     r11d, r12d
0x1800f8e8d  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f8e91  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f8e95  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f8e9a  mov     dword ptr [rsp+1D0h+var_188], edi
0x1800f8e9e  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f8ea5  mov     [rsp+1D0h+var_190], r14
0x1800f8eaa  xor     r9d, r9d
0x1800f8ead  mov     [rsp+1D0h+var_198], r13
0x1800f8eb2  mov     r8d, 38Dh
0x1800f8eb8  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f8ebd  mov     [rsp+1D0h+var_1A8], rax
0x1800f8ec2  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f8ec9  mov     [rsp+1D0h+var_1B0], rax
0x1800f8ece  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f8ed3  cmp     edi, 5
0x1800f8ed6  jnz     short loc_1800F8EE2
0x1800f8ed8  mov     eax, 80070005h
0x1800f8edd  jmp     loc_1800F944A
0x1800f8ee2  mov     rdx, [rsi+18h]; unsigned __int16 *
0x1800f8ee6  or      r9d, 0FFFFFFFFh; unsigned int
0x1800f8eea  xor     r8d, r8d; unsigned int
0x1800f8eed  mov     rcx, rbx; struct ACTIVATION_PARAMS *
0x1800f8ef0  call    ?LogRemoteSideUnreachable@@YAXPEAUACTIVATION_PARAMS@@PEBGKK@Z; LogRemoteSideUnreachable(ACTIVATION_PARAMS *,ushort const *,ulong,ulong)
0x1800f8ef5  mov     eax, 800706BAh
0x1800f8efa  jmp     loc_1800F944A
0x1800f8eff  mov     rcx, rsi; this
0x1800f8f02  call    ?FlushBindings@CRemoteMachine@@AEAAXXZ; CRemoteMachine::FlushBindings(void)
0x1800f8f07  xor     r12d, r12d
0x1800f8f0a  lea     rax, ??_7CRemActPPing@@6B@; const CRemActPPing::`vftable'
0x1800f8f11  mov     [rbp+0D0h+var_148], r12d
0x1800f8f15  mov     [rbp+0D0h+var_150], rax
0x1800f8f19  xorps   xmm0, xmm0
0x1800f8f1c  mov     rax, [rsi+18h]
0x1800f8f20  mov     r15d, r12d
0x1800f8f23  mov     [rbp+0D0h+var_F0], rax
0x1800f8f27  mov     [rbp+0D0h+var_138], r12d
0x1800f8f2b  mov     [rbp+0D0h+var_128], 6BAh
0x1800f8f32  mov     [rbp+0D0h+var_120], r12
0x1800f8f36  movdqa  [rbp+0D0h+var_110], xmm0
0x1800f8f3b  mov     [rbp+0D0h+var_100], r12
0x1800f8f3f  mov     [rbp+0D0h+var_F8], r12d
0x1800f8f43  lea     rcx, [rbp+0D0h+var_150]; this
0x1800f8f47  call    ?Ping@CParallelPing@@QEAAJXZ; CParallelPing::Ping(void)
0x1800f8f4c  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f8f53  mov     edi, eax
0x1800f8f55  jz      short loc_1800F8FD1
0x1800f8f57  mov     ecx, 3
0x1800f8f5c  call    IsWppLevelEnabled
0x1800f8f61  test    al, al
0x1800f8f63  jz      short loc_1800F8FD1
0x1800f8f65  mov     rax, [rbx+8]
0x1800f8f69  mov     r12, [rsi+18h]
0x1800f8f6d  test    rax, rax
0x1800f8f70  jz      short loc_1800F8F7F
0x1800f8f72  mov     r11d, [rax+58h]
0x1800f8f76  mov     r14, [rax+180h]
0x1800f8f7d  jmp     short loc_1800F8F85
0x1800f8f7f  mov     r14, r13
0x1800f8f82  xor     r11d, r11d
0x1800f8f85  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f8f89  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f8f8d  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f8f92  mov     dword ptr [rsp+1D0h+var_188], edi
0x1800f8f96  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f8f9d  mov     [rsp+1D0h+var_190], r12
0x1800f8fa2  mov     r9d, 3
0x1800f8fa8  mov     [rsp+1D0h+var_198], r14
0x1800f8fad  mov     r8d, 3ACh
0x1800f8fb3  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f8fb8  mov     [rsp+1D0h+var_1A8], rax
0x1800f8fbd  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f8fc4  mov     [rsp+1D0h+var_1B0], rax
0x1800f8fc9  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f8fce  xor     r12d, r12d
0x1800f8fd1  cmp     edi, 6B5h
0x1800f8fd7  jnz     loc_1800F9301
0x1800f8fdd  test    r15d, r15d
0x1800f8fe0  jnz     loc_1800F93B1
0x1800f8fe6  mov     r15d, r12d
0x1800f8fe9  cmp     [rbp+0D0h+var_148], r12d
0x1800f8fed  jbe     loc_1800F9139
0x1800f8ff3  mov     eax, r15d
0x1800f8ff6  mov     [rsp+1D0h+Binding], r12
0x1800f8ffb  lea     r14, ds:0[rax*8]
0x1800f9003  mov     rax, qword ptr [rbp+0D0h+var_110+8]
0x1800f9007  test    rax, rax
0x1800f900a  jz      short loc_1800F9012
0x1800f900c  mov     rcx, [rax+r14]
0x1800f9010  jmp     short loc_1800F9015
0x1800f9012  mov     rcx, r12
0x1800f9015  mov     rcx, [rcx]; SourceBinding
0x1800f9018  lea     rdx, [rsp+1D0h+Binding]; DestinationBinding
0x1800f901d  call    cs:__imp_RpcBindingCopy
  ... truncated ...
```
