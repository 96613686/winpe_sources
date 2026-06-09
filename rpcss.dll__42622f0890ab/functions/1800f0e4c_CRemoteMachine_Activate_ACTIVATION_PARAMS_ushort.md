# CRemoteMachine::Activate(ACTIVATION_PARAMS *,ushort *)

- ea: `0x1800f0e4c`
- end: `0x1800f175e`
- name: `?Activate@CRemoteMachine@@QEAAJPEAUACTIVATION_PARAMS@@PEAG@Z`
- size: `2322`
- prototype: `__int64 __fastcall(CRemoteMachine *__hidden this, struct ACTIVATION_PARAMS *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f2da4`

## callees

- `0x180014b80`
- `0x180014be0`
- `0x180016160`
- `0x180034540`
- `0x18003e920`
- `0x18003e97c`
- `0x180070040`
- `0x18007ec90`
- `0x180081494`
- `0x1800b27e0`
- `0x1800c013c`
- `0x1800c1320`
- `0x1800c4468`
- `0x1800f09fc`
- `0x1800f0e4c`
- `0x1800f1780`
- `0x1800f1cfc`
- `0x1800f1e30`
- `0x1800f2304`
- `0x1800f2430`
- `0x1800f3354`
- `0x18010a084`
- `0x18010b010`

## import_xrefs

- `RPCRT4!RpcBindingReset` at `0x1800f1362`
- `RPCRT4!RpcBindingReset` at `0x1800f1362`
- `RPCRT4!RpcBindingFree` at `0x1800f113f`
- `RPCRT4!RpcBindingFree` at `0x1800f134d`
- `RPCRT4!RpcBindingFree` at `0x1800f1429`
- `RPCRT4!RpcBindingFree` at `0x1800f172a`
- `RPCRT4!RpcBindingFree` at `0x1800f113f`
- `RPCRT4!RpcBindingFree` at `0x1800f134d`
- `RPCRT4!RpcBindingFree` at `0x1800f1429`
- `RPCRT4!RpcBindingFree` at `0x1800f172a`
- `RPCRT4!RpcBindingCopy` at `0x1800f1035`
- `RPCRT4!RpcBindingCopy` at `0x1800f132b`
- `RPCRT4!RpcBindingCopy` at `0x1800f1035`
- `RPCRT4!RpcBindingCopy` at `0x1800f132b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0f36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f163e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f0f36`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f163e`

## string_xrefs

- `0x1800f10c2`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f11d0`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f12cb`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f1413`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f142f`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f15d1`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`
- `0x1800f16a6`: `CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!`

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
  __int64 v23; // r12
  const WCHAR *v24; // rdi
  CGuidStr *v25; // rax
  int v26; // r11d
  int v27; // ecx
  unsigned int v28; // edi
  __int64 v29; // rax
  __int64 v30; // r14
  CGuidStr *v31; // rax
  int v32; // r11d
  int v33; // ecx
  int v34; // r15d
  unsigned int v35; // edi
  __int64 v36; // rax
  __int64 v37; // r12
  const WCHAR *v38; // r14
  CGuidStr *v39; // rax
  int v40; // r11d
  int v41; // ecx
  unsigned int v42; // r15d
  RPC_BINDING_HANDLE *v43; // rcx
  RPC_BINDING_HANDLE *v44; // rcx
  RPC_BINDING_HANDLE *v45; // rax
  __int64 v46; // rax
  __int64 v47; // r15
  const WCHAR *v48; // r14
  CGuidStr *v49; // rax
  int v50; // ecx
  int v51; // r11d
  unsigned int v52; // r8d
  unsigned __int16 v53; // r14
  unsigned int v54; // ecx
  __int64 v55; // rax
  __int64 v56; // r14
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r15
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
  unsigned __int16 v73; // [rsp+50h] [rbp-B0h]
  int v74; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int AuthnLevel; // [rsp+58h] [rbp-A8h] BYREF
  RPC_BINDING_HANDLE DestinationBinding; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v78; // [rsp+70h] [rbp-90h]
  void **v79; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v80; // [rsp+88h] [rbp-78h]
  int v81; // [rsp+98h] [rbp-68h]
  int v82; // [rsp+A8h] [rbp-58h]
  __int64 v83; // [rsp+B0h] [rbp-50h]
  __int128 v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+D0h] [rbp-30h]
  int v86; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v87; // [rsp+E0h] [rbp-20h]
  _BYTE v88[80]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v89[80]; // [rsp+140h] [rbp+40h] BYREF

  v3 = (_DWORD *)*((_QWORD *)a2 + 3);
  v78 = a3;
  v4 = a3;
  DestinationBinding = 0;
  v74 = -2147024882;
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
  v74 = result;
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
      v73 = 0;
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
          v73 = v21;
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
                    &v74);
            if ( !v28 )
              return v74;
            RpcBindingFree(&DestinationBinding);
            DestinationBinding = 0;
            if ( v28 != 1722 && v28 != 1753 )
            {
              if ( dword_18014E4B8
                || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
              {
                v29 = *((_QWORD *)a2 + 1);
                v30 = (__int64)this[3];
                if ( v29 )
                  v15 = *(const WCHAR **)(v29 + 384);
                v31 = CGuidStr::CGuidStr((CGuidStr *)v88, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v72) = v32;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v33,
                  (__int64)"CRemoteMachine::Activate",
                  0x38Du,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  (__int64)v31,
                  v72,
                  (__int64)v15,
                  v30,
                  v28);
              }
              if ( v28 == 5 )
                return -2147024891;
              LogRemoteSideUnreachable(a2, this[3], 0, 0xFFFFFFFF);
              return -2147023174;
            }
          }
LABEL_50:
          v80 = 0;
          v79 = &CRemActPPing::`vftable';
          v34 = 0;
          v87 = this[3];
          v81 = 0;
          v82 = 1722;
          v83 = 0;
          v84 = 0;
          v85 = 0;
          v86 = 0;
LABEL_51:
          v35 = CParallelPing::Ping((CParallelPing *)&v79);
          if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
          {
            v36 = *((_QWORD *)a2 + 1);
            v37 = (__int64)this[3];
            if ( v36 )
              v38 = *(const WCHAR **)(v36 + 384);
            else
              v38 = &Class;
            v39 = CGuidStr::CGuidStr((CGuidStr *)v88, (const struct _GUID *)((char *)a2 + 60));
            LODWORD(v72) = v40;
            ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
              v41,
              (__int64)"CRemoteMachine::Activate",
              0x3ACu,
              3,
              (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
              (__int64)v39,
              v72,
              (__int64)v38,
              v37,
              v35);
          }
          if ( v35 == 1717 )
          {
            if ( v34 )
            {
              v53 = v73;
              goto LABEL_84;
            }
            v42 = 0;
            if ( v80 )
            {
              while ( 1 )
              {
                Binding = 0;
                v43 = *((_QWORD *)&v84 + 1) ? *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v84 + 1) + 8LL * v42) : 0LL;
                v35 = RpcBindingCopy(*v43, &Binding);
                if ( v35 )
                  break;
                if ( *((_QWORD *)&v84 + 1) )
                  v44 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v84 + 1) + 8LL * v42);
                else
                  v44 = 0;
                v35 = RpcBindingFree(v44);
                if ( v35 )
                {
                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v57 = *((_QWORD *)a2 + 1);
                    v47 = (__int64)this[3];
                    if ( v57 )
                      v48 = *(const WCHAR **)(v57 + 384);
                    else
                      v48 = &Class;
                    v49 = CGuidStr::CGuidStr((CGuidStr *)v88, (const struct _GUID *)((char *)a2 + 60));
                    v52 = 969;
LABEL_81:
                    LODWORD(v72) = v51;
                    ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                      v50,
                      (__int64)"CRemoteMachine::Activate",
                      v52,
                      0,
                      (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                      (__int64)v49,
                      v72,
                      (__int64)v48,
                      v47,
                      v35);
                  }
LABEL_82:
                  RpcBindingFree(&Binding);
                  goto LABEL_83;
                }
                v35 = RpcBindingReset(Binding);
                if ( v35 )
                {
                  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
                  {
                    v46 = *((_QWORD *)a2 + 1);
                    v47 = (__int64)this[3];
                    if ( v46 )
                      v48 = *(const WCHAR **)(v46 + 384);
                    else
                      v48 = &Class;
                    v49 = CGuidStr::CGuidStr((CGuidStr *)v88, (const struct _GUID *)((char *)a2 + 60));
                    v52 = 981;
                    goto LABEL_81;
                  }
                  goto LABEL_82;
                }
                if ( *((_QWORD *)&v84 + 1) )
                  v45 = *(RPC_BINDING_HANDLE **)(*((_QWORD *)&v84 + 1) + 8LL * v42);
                else
                  v45 = 0;
                ++v42;
                *v45 = Binding;
                if ( v42 >= v80 )
                {
                  v34 = 1;
                  goto LABEL_51;
                }
              }
              if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v58 = *((_QWORD *)a2 + 1);
                v59 = (__int64)this[3];
                if ( v58 )
                  v60 = *(const WCHAR **)(v58 + 384);
                else
                  v60 = &Class;
                v61 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v72) = v62;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v63,
                  (__int64)"CRemoteMachine::Activate",
                  0x3BDu,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  (__int64)v61,
                  v72,
                  (__int64)v60,
                  v59,
                  v35);
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
            DestinationBinding = *(RPC_BINDING_HANDLE *)v85;
            *(_QWORD *)v85 = 0;
            v65 = HeapAlloc(g_hHeap, 0, 0x10u);
            if ( v65 )
            {
              v66 = v84;
              *(_QWORD *)&v84 = 0;
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
            v53 = *(_WORD *)(v85 + 16);
            *((_DWORD *)this + 19) = *(_DWORD *)(v85 + 8);
            CSharedLock::UnlockExclusive(v68);
            goto LABEL_84;
          }
LABEL_83:
          v53 = v73;
LABEL_84:
          CParallelPing::Reset((CParallelPing *)&v79);
          CParallelPing::~CParallelPing((CParallelPing *)&v79);
          if ( v35 )
            goto LABEL_128;
          if ( !DestinationBinding )
            return v74;
          v74 = CRemoteMachine::GetAuthnLevel((CRemoteMachine *)this, a2, &AuthnLevel);
          if ( v74 >= 0 )
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
                    v78,
                    &DestinationBinding,
                    0,
                    v54,
                    v53,
                    &v74);
            if ( v35 )
            {
LABEL_128:
              if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v55 = *((_QWORD *)a2 + 1);
                v56 = (__int64)this[3];
                if ( v55 )
                  v15 = *(const WCHAR **)(v55 + 384);
                v69 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v72) = v70;
                ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
                  v71,
                  (__int64)"CRemoteMachine::Activate",
                  0x41Bu,
                  0,
                  (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
                  (__int64)v69,
                  v72,
                  (__int64)v15,
                  v56,
                  v35);
              }
              if ( v35 == 5 )
              {
                v74 = -2147024891;
              }
              else
              {
                LogRemoteSideUnreachable(a2, this[3], 0, 0xFFFFFFFF);
                v74 = -2147023174;
              }
            }
          }
          if ( DestinationBinding )
            RpcBindingFree(&DestinationBinding);
          return v74;
        }
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v22 = *((_QWORD *)a2 + 1);
          v23 = (__int64)this[3];
          if ( v22 )
            v24 = *(const WCHAR **)(v22 + 384);
          else
            v24 = &Class;
          v25 = CGuidStr::CGuidStr((CGuidStr *)v88, (const struct _GUID *)((char *)a2 + 60));
          LODWORD(v72) = v26;
          ComTraceMessageT<unsigned short *,unsigned long,unsigned short const *,unsigned short *,long>(
            v27,
            (__int64)"CRemoteMachine::Activate",
            0x36Du,
            0,
            (__int64)L"CLSID:%ws Client PID:%x Client:%ws RSN:%ws %!WINERROR!",
            (__int64)v25,
            v72,
            (__int64)v24,
            v23,
            v20);
          v4 = v78;
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
            &v74);
    v14 = v13;
    if ( !v13 )
    {
      *((_WORD *)a2 + 18) = v7;
      (*(void (__fastcall **)(struct CMachineBinding *))(*(_QWORD *)v10 + 16LL))(v10);
      return v74;
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
0x1800f0e4c  mov     [rsp-8+arg_18], rbx
0x1800f0e51  push    rbp
0x1800f0e52  push    rsi
0x1800f0e53  push    rdi
0x1800f0e54  push    r12
0x1800f0e56  push    r13
0x1800f0e58  push    r14
0x1800f0e5a  push    r15
0x1800f0e5c  lea     rbp, [rsp-0A0h]
0x1800f0e64  sub     rsp, 1A0h
0x1800f0e6b  mov     rax, cs:__security_cookie
0x1800f0e72  xor     rax, rsp
0x1800f0e75  mov     [rbp+0D0h+var_40], rax
0x1800f0e7c  mov     rax, [rdx+18h]
0x1800f0e80  xor     r13d, r13d
0x1800f0e83  mov     [rsp+1D0h+var_160], r8
0x1800f0e88  mov     r12, r8
0x1800f0e8b  mov     [rsp+1D0h+DestinationBinding], r13
0x1800f0e90  mov     rbx, rdx
0x1800f0e93  mov     [rsp+1D0h+var_17C], 8007000Eh
0x1800f0e9b  mov     rsi, rcx
0x1800f0e9e  mov     [rsp+1D0h+AuthnLevel], r13d
0x1800f0ea3  test    rax, rax
0x1800f0ea6  jz      short loc_1800F0EBD
0x1800f0ea8  cmp     dword ptr [rax], 0FFFFFFFFh
0x1800f0eab  jnz     short loc_1800F0EB3
0x1800f0ead  mov     dword ptr [rax], 9
0x1800f0eb3  mov     rax, [rdx+18h]
0x1800f0eb7  movzx   r15d, word ptr [rax]
0x1800f0ebb  jmp     short loc_1800F0EC3
0x1800f0ebd  mov     r15d, 0FFFFh
0x1800f0ec3  lea     r8, [rsp+1D0h+AuthnLevel]; unsigned int *
0x1800f0ec8  call    ?GetAuthnLevel@CRemoteMachine@@AEAAJPEAUACTIVATION_PARAMS@@PEAK@Z; CRemoteMachine::GetAuthnLevel(ACTIVATION_PARAMS *,ulong *)
0x1800f0ecd  mov     [rsp+1D0h+var_17C], eax
0x1800f0ed1  test    eax, eax
0x1800f0ed3  js      loc_1800F1734
0x1800f0ed9  mov     rdx, [rbx+10h]
0x1800f0edd  movzx   r8d, r15w; unsigned __int16
0x1800f0ee1  mov     rax, [rbx+18h]
0x1800f0ee5  add     rdx, 9Ch; void *
0x1800f0eec  mov     r9d, [rsp+1D0h+AuthnLevel]; unsigned int
0x1800f0ef1  mov     rcx, rsi; this
0x1800f0ef4  mov     [rsp+1D0h+var_1B0], rax; struct _COAUTHINFO *
0x1800f0ef9  call    ?LookupBinding@CRemoteMachine@@AEAAPEAVCMachineBinding@@PEAXGKPEAU_COAUTHINFO@@@Z; CRemoteMachine::LookupBinding(void *,ushort,ulong,_COAUTHINFO *)
0x1800f0efe  mov     rdi, rax
0x1800f0f01  test    rax, rax
0x1800f0f04  jz      loc_1800F0FCE
0x1800f0f0a  movzx   r15d, word ptr [rax+3Ah]
0x1800f0f0f  mov     [rbx+28h], r13d
0x1800f0f13  mov     [rbx+30h], r13
0x1800f0f17  cmp     [rax+48h], r13d
0x1800f0f1b  jz      short loc_1800F0F5B
0x1800f0f1d  mov     eax, [rax+48h]
0x1800f0f20  lea     r8, [rax+7]
0x1800f0f24  cmp     rax, r8
0x1800f0f27  ja      short loc_1800F0F9E
0x1800f0f29  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800f0f30  and     r8, 0FFFFFFFFFFFFFFF8h; dwBytes
0x1800f0f34  xor     edx, edx; dwFlags
0x1800f0f36  call    cs:__imp_HeapAlloc
0x1800f0f3c  mov     [rbx+30h], rax
0x1800f0f40  test    rax, rax
0x1800f0f43  jz      short loc_1800F0F9E
0x1800f0f45  mov     r8d, [rdi+48h]; Size
0x1800f0f49  mov     rcx, rax; void *
0x1800f0f4c  mov     rdx, [rdi+50h]; Src
0x1800f0f50  call    memcpy_0
0x1800f0f55  mov     eax, [rdi+48h]
0x1800f0f58  mov     [rbx+28h], eax
0x1800f0f5b  movzx   r8d, word ptr [rdi+38h]; unsigned __int16
0x1800f0f60  lea     rax, [rsp+1D0h+var_17C]
0x1800f0f65  mov     rdx, [rdi+28h]; void *
0x1800f0f69  mov     r9, rbx; struct ACTIVATION_PARAMS *
0x1800f0f6c  mov     [rsp+1D0h+var_1A8], rax; int *
0x1800f0f71  mov     rcx, rsi; this
0x1800f0f74  mov     [rsp+1D0h+var_1B0], r12; unsigned __int16 *
0x1800f0f79  call    ?CallRemoteMachine@CRemoteMachine@@AEAAJPEAXGPEAUACTIVATION_PARAMS@@PEAGPEAJ@Z; CRemoteMachine::CallRemoteMachine(void *,ushort,ACTIVATION_PARAMS *,ushort *,long *)
0x1800f0f7e  mov     r14d, eax
0x1800f0f81  test    eax, eax
0x1800f0f83  jnz     short loc_1800F0FA6
0x1800f0f85  mov     [rbx+24h], r15w
0x1800f0f8a  mov     rcx, rdi
0x1800f0f8d  mov     rax, [rdi]
0x1800f0f90  mov     rax, [rax+10h]
0x1800f0f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f99  jmp     loc_1800F1730
0x1800f0f9e  mov     r14d, 8
0x1800f0fa4  jmp     short loc_1800F0FB2
0x1800f0fa6  cmp     eax, 5
0x1800f0fa9  jz      short loc_1800F0FBD
0x1800f0fab  cmp     eax, 721h
0x1800f0fb0  jz      short loc_1800F0FBD
0x1800f0fb2  mov     rdx, rdi; struct CMachineBinding *
0x1800f0fb5  mov     rcx, rsi; this
0x1800f0fb8  call    ?RemoveBinding@CRemoteMachine@@AEAAXPEAVCMachineBinding@@@Z; CRemoteMachine::RemoveBinding(CMachineBinding *)
0x1800f0fbd  mov     rax, [rdi]
0x1800f0fc0  mov     rcx, rdi
0x1800f0fc3  mov     rax, [rax+10h]
0x1800f0fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0fcc  jmp     short loc_1800F0FD4
0x1800f0fce  mov     r14d, 6E6h
0x1800f0fd4  cmp     [rsp+1D0h+AuthnLevel], 2
0x1800f0fd9  mov     dword ptr [rsp+1D0h+var_180], r13d
0x1800f0fde  jnb     short loc_1800F0FE8
0x1800f0fe0  mov     [rsp+1D0h+AuthnLevel], 5
0x1800f0fe8  lea     r13, Class
0x1800f0fef  cmp     r14d, 6BAh
0x1800f0ff6  jz      loc_1800F120D
0x1800f0ffc  cmp     r14d, 6D9h
0x1800f1003  jz      loc_1800F120D
0x1800f1009  mov     rcx, cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA; lpCriticalSection
0x1800f1010  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x1800f1015  mov     rax, [rsi+30h]
0x1800f1019  lea     rcx, [rax-10h]
0x1800f101d  neg     rax
0x1800f1020  sbb     rdi, rdi
0x1800f1023  and     rdi, rcx
0x1800f1026  jz      loc_1800F10E1
0x1800f102c  mov     rcx, [rdi+28h]; SourceBinding
0x1800f1030  lea     rdx, [rsp+1D0h+DestinationBinding]; DestinationBinding
0x1800f1035  call    cs:__imp_RpcBindingCopy
0x1800f103b  mov     r14d, eax
0x1800f103e  test    eax, eax
0x1800f1040  jnz     short loc_1800F104F
0x1800f1042  movzx   edi, word ptr [rdi+38h]
0x1800f1046  mov     dword ptr [rsp+1D0h+var_180], edi
0x1800f104a  jmp     loc_1800F10E5
0x1800f104f  mov     eax, cs:dword_18014E4B8
0x1800f1055  test    eax, eax
0x1800f1057  jnz     short loc_1800F106C
0x1800f1059  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x1800f105f  jz      short loc_1800F10D8
0x1800f1061  xor     ecx, ecx
0x1800f1063  call    IsWppLevelEnabled
0x1800f1068  test    al, al
0x1800f106a  jz      short loc_1800F10D8
0x1800f106c  mov     rax, [rbx+8]
0x1800f1070  mov     r12, [rsi+18h]
0x1800f1074  test    rax, rax
0x1800f1077  jz      short loc_1800F1086
0x1800f1079  mov     r11d, [rax+58h]
0x1800f107d  mov     rdi, [rax+180h]
0x1800f1084  jmp     short loc_1800F108C
0x1800f1086  mov     rdi, r13
0x1800f1089  xor     r11d, r11d
0x1800f108c  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f1090  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f1094  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f1099  mov     [rsp+1D0h+var_188], r14d
0x1800f109e  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f10a5  mov     [rsp+1D0h+var_190], r12
0x1800f10aa  xor     r9d, r9d
0x1800f10ad  mov     [rsp+1D0h+var_198], rdi
0x1800f10b2  mov     r8d, 36Dh
0x1800f10b8  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f10bd  mov     [rsp+1D0h+var_1A8], rax
0x1800f10c2  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f10c9  mov     [rsp+1D0h+var_1B0], rax
0x1800f10ce  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f10d3  mov     r12, [rsp+1D0h+var_160]
0x1800f10d8  mov     [rsp+1D0h+DestinationBinding], 0
0x1800f10e1  mov     edi, dword ptr [rsp+1D0h+var_180]
0x1800f10e5  mov     rcx, cs:?gpRemoteMachineLock@@3PEAVCSharedLock@@EA; this
0x1800f10ec  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x1800f10f1  cmp     [rsp+1D0h+DestinationBinding], 0
0x1800f10f7  jz      loc_1800F1215
0x1800f10fd  lea     rax, [rsp+1D0h+var_17C]
0x1800f1102  mov     r8, r12; unsigned __int16 *
0x1800f1105  mov     [rsp+1D0h+var_198], rax; int *
0x1800f110a  lea     r9, [rsp+1D0h+DestinationBinding]; void **
0x1800f110f  mov     eax, [rsp+1D0h+AuthnLevel]
0x1800f1113  mov     rdx, rbx; struct ACTIVATION_PARAMS *
0x1800f1116  mov     [rsp+1D0h+var_1A0], di; unsigned __int16
0x1800f111b  mov     rcx, rsi; this
0x1800f111e  mov     dword ptr [rsp+1D0h+var_1A8], eax; AuthnLevel
0x1800f1122  mov     word ptr [rsp+1D0h+var_1B0], r15w; unsigned __int16
0x1800f1128  call    ?PickAuthnAndActivate@CRemoteMachine@@AEAAJPEAUACTIVATION_PARAMS@@PEAGPEAPEAXGKGPEAJ@Z; CRemoteMachine::PickAuthnAndActivate(ACTIVATION_PARAMS *,ushort *,void * *,ushort,ulong,ushort,long *)
0x1800f112d  xor     r12d, r12d
0x1800f1130  mov     edi, eax
0x1800f1132  test    eax, eax
0x1800f1134  jz      loc_1800F1730
0x1800f113a  lea     rcx, [rsp+1D0h+DestinationBinding]; Binding
0x1800f113f  call    cs:__imp_RpcBindingFree
0x1800f1145  mov     [rsp+1D0h+DestinationBinding], r12
0x1800f114a  cmp     edi, 6BAh
0x1800f1150  jz      loc_1800F1218
0x1800f1156  cmp     edi, 6D9h
0x1800f115c  jz      loc_1800F1218
0x1800f1162  mov     ecx, cs:dword_18014E4B8
0x1800f1168  test    ecx, ecx
0x1800f116a  jnz     short loc_1800F117E
0x1800f116c  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f1173  jz      short loc_1800F11E1
0x1800f1175  call    IsWppLevelEnabled
0x1800f117a  test    al, al
0x1800f117c  jz      short loc_1800F11E1
0x1800f117e  mov     rax, [rbx+8]
0x1800f1182  mov     r14, [rsi+18h]
0x1800f1186  test    rax, rax
0x1800f1189  jz      short loc_1800F1198
0x1800f118b  mov     r11d, [rax+58h]
0x1800f118f  mov     r13, [rax+180h]
0x1800f1196  jmp     short loc_1800F119B
0x1800f1198  mov     r11d, r12d
0x1800f119b  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f119f  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f11a3  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f11a8  mov     [rsp+1D0h+var_188], edi
0x1800f11ac  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f11b3  mov     [rsp+1D0h+var_190], r14
0x1800f11b8  xor     r9d, r9d
0x1800f11bb  mov     [rsp+1D0h+var_198], r13
0x1800f11c0  mov     r8d, 38Dh
0x1800f11c6  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f11cb  mov     [rsp+1D0h+var_1A8], rax
0x1800f11d0  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f11d7  mov     [rsp+1D0h+var_1B0], rax
0x1800f11dc  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f11e1  cmp     edi, 5
0x1800f11e4  jnz     short loc_1800F11F0
0x1800f11e6  mov     eax, 80070005h
0x1800f11eb  jmp     loc_1800F1734
0x1800f11f0  mov     rdx, [rsi+18h]; unsigned __int16 *
0x1800f11f4  or      r9d, 0FFFFFFFFh; unsigned int
0x1800f11f8  xor     r8d, r8d; unsigned int
0x1800f11fb  mov     rcx, rbx; struct ACTIVATION_PARAMS *
0x1800f11fe  call    ?LogRemoteSideUnreachable@@YAXPEAUACTIVATION_PARAMS@@PEBGKK@Z; LogRemoteSideUnreachable(ACTIVATION_PARAMS *,ushort const *,ulong,ulong)
0x1800f1203  mov     eax, 800706BAh
0x1800f1208  jmp     loc_1800F1734
0x1800f120d  mov     rcx, rsi; this
0x1800f1210  call    ?FlushBindings@CRemoteMachine@@AEAAXXZ; CRemoteMachine::FlushBindings(void)
0x1800f1215  xor     r12d, r12d
0x1800f1218  lea     rax, ??_7CRemActPPing@@6B@; const CRemActPPing::`vftable'
0x1800f121f  mov     [rbp+0D0h+var_148], r12d
0x1800f1223  mov     [rbp+0D0h+var_150], rax
0x1800f1227  xorps   xmm0, xmm0
0x1800f122a  mov     rax, [rsi+18h]
0x1800f122e  mov     r15d, r12d
0x1800f1231  mov     [rbp+0D0h+var_F0], rax
0x1800f1235  mov     [rbp+0D0h+var_138], r12d
0x1800f1239  mov     [rbp+0D0h+var_128], 6BAh
0x1800f1240  mov     [rbp+0D0h+var_120], r12
0x1800f1244  movdqa  [rbp+0D0h+var_110], xmm0
0x1800f1249  mov     [rbp+0D0h+var_100], r12
0x1800f124d  mov     [rbp+0D0h+var_F8], r12d
0x1800f1251  lea     rcx, [rbp+0D0h+var_150]; this
0x1800f1255  call    ?Ping@CParallelPing@@QEAAJXZ; CParallelPing::Ping(void)
0x1800f125a  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800f1261  mov     edi, eax
0x1800f1263  jz      short loc_1800F12DF
0x1800f1265  mov     ecx, 3
0x1800f126a  call    IsWppLevelEnabled
0x1800f126f  test    al, al
0x1800f1271  jz      short loc_1800F12DF
0x1800f1273  mov     rax, [rbx+8]
0x1800f1277  mov     r12, [rsi+18h]
0x1800f127b  test    rax, rax
0x1800f127e  jz      short loc_1800F128D
0x1800f1280  mov     r11d, [rax+58h]
0x1800f1284  mov     r14, [rax+180h]
0x1800f128b  jmp     short loc_1800F1293
0x1800f128d  mov     r14, r13
0x1800f1290  xor     r11d, r11d
0x1800f1293  lea     rdx, [rbx+3Ch]; struct _GUID *
0x1800f1297  lea     rcx, [rbp+0D0h+var_E0]; this
0x1800f129b  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800f12a0  mov     [rsp+1D0h+var_188], edi
0x1800f12a4  lea     rdx, aCremotemachine_0; "CRemoteMachine::Activate"
0x1800f12ab  mov     [rsp+1D0h+var_190], r12
0x1800f12b0  mov     r9d, 3
0x1800f12b6  mov     [rsp+1D0h+var_198], r14
0x1800f12bb  mov     r8d, 3ACh
0x1800f12c1  mov     dword ptr [rsp+1D0h+var_1A0], r11d
0x1800f12c6  mov     [rsp+1D0h+var_1A8], rax
0x1800f12cb  lea     rax, aClsidWsClientP_0; "CLSID:%ws Client PID:%x Client:%ws RSN:"...
0x1800f12d2  mov     [rsp+1D0h+var_1B0], rax
0x1800f12d7  call    ??$ComTraceMessageT@PEAGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGK23J@Z; ComTraceMessageT<ushort *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ulong,ushort const *,ushort *,long)
0x1800f12dc  xor     r12d, r12d
0x1800f12df  cmp     edi, 6B5h
0x1800f12e5  jnz     loc_1800F15F7
0x1800f12eb  test    r15d, r15d
0x1800f12ee  jnz     loc_1800F16A1
0x1800f12f4  mov     r15d, r12d
0x1800f12f7  cmp     [rbp+0D0h+var_148], r12d
0x1800f12fb  jbe     loc_1800F142F
0x1800f1301  mov     eax, r15d
0x1800f1304  mov     [rsp+1D0h+Binding], r12
0x1800f1309  lea     r14, ds:0[rax*8]
0x1800f1311  mov     rax, qword ptr [rbp+0D0h+var_110+8]
0x1800f1315  test    rax, rax
0x1800f1318  jz      short loc_1800F1320
0x1800f131a  mov     rcx, [rax+r14]
0x1800f131e  jmp     short loc_1800F1323
0x1800f1320  mov     rcx, r12
0x1800f1323  mov     rcx, [rcx]; SourceBinding
0x1800f1326  lea     rdx, [rsp+1D0h+Binding]; DestinationBinding
0x1800f132b  call    cs:__imp_RpcBindingCopy
0x1800f1331  mov     edi, eax
0x1800f1333  test    eax, eax
0x1800f1335  jnz     loc_1800F1566
  ... truncated ...
```
