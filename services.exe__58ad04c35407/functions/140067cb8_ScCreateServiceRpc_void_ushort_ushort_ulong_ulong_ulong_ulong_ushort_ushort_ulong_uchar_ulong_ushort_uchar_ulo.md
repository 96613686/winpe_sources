# ScCreateServiceRpc(void *,ushort *,ushort *,ulong,ulong,ulong,ulong,ushort *,ushort *,ulong *,uchar *,ulong,ushort *,uchar *,ulong,void * *,ushort)

- ea: `0x140067cb8`
- end: `0x140068112`
- name: `?ScCreateServiceRpc@@YAKPEAXPEAG1KKKK11PEAKPEAEK13KPEAPEAXG@Z`
- size: `1114`
- prototype: `__int64 __fastcall(ACCESS_MASK *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned __int8 *, unsigned int, unsigned __int16 *, unsigned __int8 *, unsigned int, void **, unsigned __int16)`
- caller_count: `4`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14006a7b0`
- `0x14006a860`
- `0x14006a920`
- `0x140074c30`

## callees

- `0x140004c58`
- `0x140007130`
- `0x1400083f0`
- `0x140017160`
- `0x140017230`
- `0x140019014`
- `0x14001a2e0`
- `0x14001c100`
- `0x14001f7c0`
- `0x14001f99c`
- `0x140020dbc`
- `0x140031144`
- `0x140032be0`
- `0x1400432dc`
- `0x140066ef4`
- `0x140067cb8`
- `0x14006af80`
- `0x14007bffc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067e67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140067e49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140067e49`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140067d9d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140067d9d`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140067e5a`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x140067e5a`
- `ntdll!RtlAreAllAccessesGranted` at `0x140067d6f`
- `ntdll!RtlAreAllAccessesGranted` at `0x140067d6f`
- `ntdll!RtlFreeHeap` at `0x14006806d`
- `ntdll!RtlFreeHeap` at `0x14006806d`

## pseudocode

```c
__int64 __fastcall ScCreateServiceRpc(
        ACCESS_MASK *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned int *a10,
        unsigned __int8 *a11,
        unsigned int a12,
        unsigned __int16 *a13,
        unsigned __int8 *a14,
        unsigned int a15,
        void **a16,
        unsigned __int16 a17)
{
  DWORD LastError; // ebx
  unsigned int v20; // eax
  RPC_STATUS v21; // r12d
  PRPC_ASYNC_STATE v22; // rcx
  unsigned __int16 v23; // r14
  char v24; // r8
  HANDLE CurrentProcess; // rax
  unsigned int v26; // edx
  unsigned int ServiceHandle; // eax
  struct _SC_HANDLE_STRUCT *v28; // r12
  PRPC_ASYNC_STATE v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned int IsValidWow64Type; // eax
  struct CServiceRecord *v33; // rdx
  struct _SC_HANDLE_STRUCT *v34; // rax
  _WORD v36[2]; // [rsp+A8h] [rbp-19h] BYREF
  __int16 v37; // [rsp+ACh] [rbp-15h] BYREF
  unsigned int Pid; // [rsp+B0h] [rbp-11h] BYREF
  struct CServiceRecord *v39; // [rsp+B8h] [rbp-9h] BYREF
  PVOID P; // [rsp+C0h] [rbp-1h] BYREF

  v39 = 0;
  P = 0;
  Pid = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
  {
    LastError = 1115;
    goto LABEL_61;
  }
  v20 = ScMarkContextHandleSessionStrict(0);
  LastError = v20;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 39, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v20);
    goto LABEL_61;
  }
  if ( !(unsigned int)ScIsValidScManagerHandle(a1) )
  {
    LastError = 6;
    goto LABEL_61;
  }
  if ( !RtlAreAllAccessesGranted(a1[2], 2u) )
  {
    LastError = 5;
    goto LABEL_61;
  }
  if ( !(unsigned int)ScIsValidServiceName(a2) )
  {
    LastError = 123;
    goto LABEL_61;
  }
  v21 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v22 = WPP_GLOBAL_Control;
  v23 = a17;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
  {
    v24 = 0;
    if ( !v21 )
      v24 = Pid;
    WPP_SF_SLd(
      WPP_GLOBAL_Control->StubInfo,
      40,
      (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
      (_DWORD)a2,
      a17,
      v24);
    v22 = WPP_GLOBAL_Control;
  }
  LastError = 87;
  if ( !a16 )
  {
    if ( v22 != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(v22->UserInfo) & 1) != 0 )
      WPP_SF_(v22->StubInfo, 41, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids);
    goto LABEL_61;
  }
  if ( !a17 )
    goto LABEL_27;
  v37 = 0;
  v36[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !(unsigned int)IsWow64Process2(CurrentProcess, &v37, v36) )
  {
    LastError = GetLastError();
    goto LABEL_61;
  }
  if ( a17 == v36[0] )
  {
    v23 = 0;
    goto LABEL_27;
  }
  if ( (a5 & 0x30) != 0 )
  {
    IsValidWow64Type = ScIsValidWow64Type(a17);
    LastError = IsValidWow64Type;
    if ( IsValidWow64Type )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_dSd(
          WPP_GLOBAL_Control->StubInfo,
          42,
          (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
          a17,
          (__int64)a2,
          IsValidWow64Type);
      goto LABEL_61;
    }
LABEL_27:
    v26 = 0;
    if ( !v21 )
      v26 = Pid;
    ServiceHandle = ScCreateServiceHandle(0, v26, (struct _SC_HANDLE_STRUCT **)&P);
    v28 = (struct _SC_HANDLE_STRUCT *)P;
    LastError = ServiceHandle;
    if ( ServiceHandle )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_52;
      v30 = 44;
    }
    else
    {
      ServiceHandle = ScGrantAccess((struct _SC_HANDLE_STRUCT *)P, a4);
      LastError = ServiceHandle;
      if ( !ServiceHandle )
      {
        Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v39);
        LastError = ScCreateService(
                      a1,
                      g_PrimaryConfigRoot,
                      a2,
                      a3,
                      a5,
                      a6,
                      a7,
                      a8,
                      a9,
                      a10,
                      a11,
                      a12,
                      a13,
                      a14,
                      a15,
                      v23,
                      0,
                      0,
                      0,
                      &v39);
        if ( !LastError )
        {
          v33 = v39;
          v39 = 0;
          ScSetAndIncrementServiceHandlesCount(v28, v33);
          *a16 = v28;
          if ( (a5 & 0x30) != 0 )
            ScUpdateServiceSidCache(a2, 1);
          ScDrainRemoteNotifyQueues();
          goto LABEL_56;
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
LABEL_52:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
          *a16 = 0;
LABEL_56:
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x100) != 0 )
          {
            v34 = 0;
            if ( !LastError )
              v34 = v28;
            WPP_SF_dq(WPP_GLOBAL_Control->StubInfo, 47, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, LastError, v34);
          }
          goto LABEL_61;
        }
        v30 = 46;
        v31 = LastError;
LABEL_51:
        WPP_SF_d(v29->StubInfo, v30, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids, v31);
        goto LABEL_52;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_52;
      v30 = 45;
    }
    v31 = ServiceHandle;
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_dSd(
      WPP_GLOBAL_Control->StubInfo,
      43,
      (unsigned int)WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids,
      a17,
      (__int64)a2,
      87);
LABEL_61:
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v39);
  return LastError;
}

```

## disassembly

```asm
0x140067cb8  mov     rax, rsp
0x140067cbb  mov     [rax+8], rbx
0x140067cbf  mov     [rax+20h], r9d
0x140067cc3  mov     [rax+18h], r8
0x140067cc7  push    rbp
0x140067cc8  push    rsi
0x140067cc9  push    rdi
0x140067cca  push    r12
0x140067ccc  push    r13
0x140067cce  push    r14
0x140067cd0  push    r15
0x140067cd2  lea     rbp, [rax-3Fh]
0x140067cd6  sub     rsp, 0C0h
0x140067cdd  xor     edi, edi
0x140067cdf  mov     r15, rdx
0x140067ce2  mov     [rbp+37h+var_40], rdi
0x140067ce6  mov     r13, rcx
0x140067ce9  mov     [rbp+37h+P], rdi
0x140067ced  mov     [rbp+37h+Pid], edi
0x140067cf0  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140067cf5  cmp     cs:?ScShutdownInProgress@@3KA, edi; ulong ScShutdownInProgress
0x140067cfb  jz      short loc_140067D07
0x140067cfd  mov     ebx, 45Bh
0x140067d02  jmp     loc_1400680EC
0x140067d07  xor     ecx, ecx; int *
0x140067d09  call    ?ScMarkContextHandleSessionStrict@@YAKPEAH@Z; ScMarkContextHandleSessionStrict(int *)
0x140067d0e  mov     ebx, eax
0x140067d10  test    eax, eax
0x140067d12  jz      short loc_140067D52
0x140067d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140067d1b  lea     rdi, WPP_GLOBAL_Control
0x140067d22  cmp     rcx, rdi
0x140067d25  jz      loc_1400680EC
0x140067d2b  test    byte ptr [rcx+1Ch], 1
0x140067d2f  jz      loc_1400680EC
0x140067d35  mov     rcx, [rcx+10h]
0x140067d39  lea     r8, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140067d40  mov     edx, 27h ; '''
0x140067d45  mov     r9d, eax
0x140067d48  call    WPP_SF_d
0x140067d4d  jmp     loc_1400680EC
0x140067d52  mov     rcx, r13; void *
0x140067d55  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x140067d5a  test    eax, eax
0x140067d5c  jnz     short loc_140067D66
0x140067d5e  lea     ebx, [rax+6]
0x140067d61  jmp     loc_1400680EC
0x140067d66  mov     ecx, [r13+8]; GrantedAccess
0x140067d6a  mov     edx, 2; DesiredAccess
0x140067d6f  call    cs:__imp_RtlAreAllAccessesGranted
0x140067d75  test    al, al
0x140067d77  jnz     short loc_140067D83
0x140067d79  mov     ebx, 5
0x140067d7e  jmp     loc_1400680EC
0x140067d83  mov     rcx, r15; unsigned __int16 *
0x140067d86  call    ?ScIsValidServiceName@@YAHPEBG@Z; ScIsValidServiceName(ushort const *)
0x140067d8b  test    eax, eax
0x140067d8d  jnz     short loc_140067D97
0x140067d8f  lea     ebx, [rax+7Bh]
0x140067d92  jmp     loc_1400680EC
0x140067d97  lea     rdx, [rbp+37h+Pid]; Pid
0x140067d9b  xor     ecx, ecx; Binding
0x140067d9d  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x140067da3  mov     r12d, eax
0x140067da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140067dad  lea     rdi, WPP_GLOBAL_Control
0x140067db4  movzx   r14d, [rbp+37h+arg_80]
0x140067dbc  lea     rsi, WPP_119db94a907b38ec33df27ba8ada49ba_Traceguids
0x140067dc3  cmp     rcx, rdi
0x140067dc6  jz      short loc_140067E01
0x140067dc8  test    dword ptr [rcx+1Ch], 100h
0x140067dcf  jz      short loc_140067E01
0x140067dd1  mov     rcx, [rcx+10h]
0x140067dd5  xor     eax, eax
0x140067dd7  mov     r8d, eax
0x140067dda  test    r12d, r12d
0x140067ddd  mov     r9, r15
0x140067de0  cmovz   r8d, [rbp+37h+Pid]
0x140067de5  mov     [rsp+0F0h+var_C8], r8d
0x140067dea  lea     edx, [rax+28h]
0x140067ded  mov     r8, rsi
0x140067df0  mov     [rsp+0F0h+var_D0], r14d
0x140067df5  call    WPP_SF_SLd
0x140067dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e01  xor     r8d, r8d
0x140067e04  mov     ebx, 57h ; 'W'
0x140067e09  cmp     [rbp+37h+arg_78], r8
0x140067e10  jnz     short loc_140067E39
0x140067e12  cmp     rcx, rdi
0x140067e15  jz      loc_1400680EC
0x140067e1b  test    byte ptr [rcx+1Ch], 1
0x140067e1f  jz      loc_1400680EC
0x140067e25  mov     rcx, [rcx+10h]
0x140067e29  lea     edx, [rbx-2Eh]
0x140067e2c  mov     r8, rsi
0x140067e2f  call    WPP_SF_
0x140067e34  jmp     loc_1400680EC
0x140067e39  test    r14w, r14w
0x140067e3d  jz      short loc_140067E7E
0x140067e3f  mov     [rbp+37h+var_4C], r8w
0x140067e44  mov     [rbp+37h+var_50], r8w
0x140067e49  call    cs:__imp_GetCurrentProcess
0x140067e4f  mov     rcx, rax
0x140067e52  lea     r8, [rbp+37h+var_50]
0x140067e56  lea     rdx, [rbp+37h+var_4C]
0x140067e5a  call    cs:__imp_IsWow64Process2
0x140067e60  xor     r8d, r8d
0x140067e63  test    eax, eax
0x140067e65  jnz     short loc_140067E74
0x140067e67  call    cs:__imp_GetLastError
0x140067e6d  mov     ebx, eax
0x140067e6f  jmp     loc_1400680EC
0x140067e74  cmp     r14w, [rbp+37h+var_50]
0x140067e79  jnz     short loc_140067EC8
0x140067e7b  mov     r14d, r8d
0x140067e7e  mov     edx, r8d
0x140067e81  test    r12d, r12d
0x140067e84  lea     r8, [rbp+37h+P]; struct _SC_HANDLE_STRUCT **
0x140067e88  cmovz   edx, [rbp+37h+Pid]; unsigned int
0x140067e8c  xor     ecx, ecx; struct CServiceRecord *
0x140067e8e  call    ?ScCreateServiceHandle@@YAKPEAVCServiceRecord@@KPEAPEAU_SC_HANDLE_STRUCT@@@Z; ScCreateServiceHandle(CServiceRecord *,ulong,_SC_HANDLE_STRUCT * *)
0x140067e93  mov     r12, [rbp+37h+P]
0x140067e97  mov     ebx, eax
0x140067e99  test    eax, eax
0x140067e9b  jz      loc_140067F40
0x140067ea1  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ea8  cmp     rcx, rdi
0x140067eab  jz      loc_14006805B
0x140067eb1  test    byte ptr [rcx+1Ch], 1
0x140067eb5  jz      loc_14006805B
0x140067ebb  mov     edx, 2Ch ; ','
0x140067ec0  mov     r9d, eax
0x140067ec3  jmp     loc_14006804F
0x140067ec8  test    byte ptr [rbp+37h+arg_20], 30h
0x140067ecc  jz      short loc_140067F1B
0x140067ece  movzx   ecx, r14w; unsigned __int16
0x140067ed2  call    ?ScIsValidWow64Type@@YAKG@Z; ScIsValidWow64Type(ushort)
0x140067ed7  xor     r8d, r8d
0x140067eda  mov     ebx, eax
0x140067edc  test    eax, eax
0x140067ede  jz      short loc_140067E7E
0x140067ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ee7  cmp     rcx, rdi
0x140067eea  jz      loc_1400680EC
0x140067ef0  test    byte ptr [rcx+1Ch], 1
0x140067ef4  jz      loc_1400680EC
0x140067efa  lea     edx, [r8+2Ah]
0x140067efe  mov     [rsp+0F0h+var_C8], eax
0x140067f02  mov     rcx, [rcx+10h]
0x140067f06  mov     r9d, r14d
0x140067f09  mov     r8, rsi
0x140067f0c  mov     qword ptr [rsp+0F0h+var_D0], r15
0x140067f11  call    WPP_SF_dSd
0x140067f16  jmp     loc_1400680EC
0x140067f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f22  cmp     rcx, rdi
0x140067f25  jz      loc_1400680EC
0x140067f2b  test    byte ptr [rcx+1Ch], 1
0x140067f2f  jz      loc_1400680EC
0x140067f35  mov     edx, 2Bh ; '+'
0x140067f3a  mov     [rsp+0F0h+var_C8], ebx
0x140067f3e  jmp     short loc_140067F02
0x140067f40  mov     edx, [rbp+37h+arg_18]; unsigned int
0x140067f43  mov     rcx, r12; struct _SC_HANDLE_STRUCT *
0x140067f46  call    ?ScGrantAccess@@YAKPEAU_SC_HANDLE_STRUCT@@K@Z; ScGrantAccess(_SC_HANDLE_STRUCT *,ulong)
0x140067f4b  mov     ebx, eax
0x140067f4d  test    eax, eax
0x140067f4f  jz      short loc_140067F75
0x140067f51  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f58  cmp     rcx, rdi
0x140067f5b  jz      loc_14006805B
0x140067f61  test    byte ptr [rcx+1Ch], 1
0x140067f65  jz      loc_14006805B
0x140067f6b  mov     edx, 2Dh ; '-'
0x140067f70  jmp     loc_140067EC0
0x140067f75  lea     rcx, [rbp+37h+var_40]
0x140067f79  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140067f7e  mov     r9, [rbp+37h+arg_10]; unsigned __int16 *
0x140067f82  lea     rax, [rbp+37h+var_40]
0x140067f86  mov     rdx, cs:?g_PrimaryConfigRoot@@3PEAU_SERVICE_CONFIG_ROOT@@EA; struct _SERVICE_CONFIG_ROOT *
0x140067f8d  mov     r8, r15; unsigned __int16 *
0x140067f90  mov     [rsp+98h], rax; struct CServiceRecord **
0x140067f98  mov     rcx, r13; void *
0x140067f9b  xor     eax, eax
0x140067f9d  mov     [rsp+0F0h+var_60], rax; struct CServiceRecord *
0x140067fa5  mov     [rsp+0F0h+var_68], eax; unsigned int
0x140067fac  mov     [rsp+0F0h+var_70], rax; unsigned __int64
0x140067fb4  mov     eax, [rbp+37h+arg_70]
0x140067fba  mov     [rsp+0F0h+var_78], r14w; unsigned __int16
0x140067fc0  mov     r14d, [rbp+37h+arg_20]
0x140067fc4  mov     [rsp+0F0h+var_80], eax; unsigned int
0x140067fc8  mov     rax, [rbp+37h+arg_68]
0x140067fcf  mov     [rsp+0F0h+var_88], rax; unsigned __int8 *
0x140067fd4  mov     rax, [rbp+37h+arg_60]
0x140067fdb  mov     [rsp+0F0h+var_90], rax; unsigned __int16 *
0x140067fe0  mov     eax, [rbp+37h+arg_58]
0x140067fe6  mov     [rsp+0F0h+var_98], eax; unsigned int
0x140067fea  mov     rax, [rbp+37h+arg_50]
0x140067ff1  mov     [rsp+0F0h+var_A0], rax; unsigned __int8 *
0x140067ff6  mov     rax, [rbp+37h+arg_48]
0x140067ffd  mov     [rsp+0F0h+var_A8], rax; unsigned int *
0x140068002  mov     rax, [rbp+37h+arg_40]
0x140068009  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x14006800e  mov     rax, [rbp+37h+arg_38]
0x140068012  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x140068017  mov     eax, [rbp+37h+arg_30]
0x14006801a  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x14006801e  mov     eax, [rbp+37h+arg_28]
0x140068021  mov     [rsp+0F0h+var_C8], eax; unsigned int
0x140068025  mov     [rsp+0F0h+var_D0], r14d; unsigned int
0x14006802a  call    ?ScCreateService@@YAKPEAXPEAU_SERVICE_CONFIG_ROOT@@PEAG2KKK22PEAKPEAEK24KG_KKPEAVCServiceRecord@@PEAPEAV2@@Z; ScCreateService(void *,_SERVICE_CONFIG_ROOT *,ushort *,ushort *,ulong,ulong,ulong,ushort *,ushort *,ulong *,uchar *,ulong,ushort *,uchar *,ulong,ushort,unsigned __int64,ulong,CServiceRecord *,CServiceRecord * *)
0x14006802f  mov     ebx, eax
0x140068031  xor     eax, eax
0x140068033  test    ebx, ebx
0x140068035  jz      short loc_140068081
0x140068037  mov     rcx, cs:WPP_GLOBAL_Control
0x14006803e  cmp     rcx, rdi
0x140068041  jz      short loc_14006805B
0x140068043  test    byte ptr [rcx+1Ch], 1
0x140068047  jz      short loc_14006805B
0x140068049  lea     edx, [rax+2Eh]
0x14006804c  mov     r9d, ebx
0x14006804f  mov     rcx, [rcx+10h]
0x140068053  mov     r8, rsi
0x140068056  call    WPP_SF_d
0x14006805b  mov     rcx, gs:60h
0x140068064  mov     r8, r12; P
0x140068067  xor     edx, edx; Flags
0x140068069  mov     rcx, [rcx+30h]; HeapHandle
0x14006806d  call    cs:__imp_RtlFreeHeap
0x140068073  mov     rax, [rbp+37h+arg_78]
0x14006807a  xor     edx, edx
0x14006807c  mov     [rax], rdx
0x14006807f  jmp     short loc_1400680B5
0x140068081  mov     rdx, [rbp+37h+var_40]; struct CServiceRecord *
0x140068085  mov     rcx, r12; struct _SC_HANDLE_STRUCT *
0x140068088  mov     [rbp+37h+var_40], rax
0x14006808c  call    ?ScSetAndIncrementServiceHandlesCount@@YAXPEAU_SC_HANDLE_STRUCT@@PEAVCServiceRecord@@@Z; ScSetAndIncrementServiceHandlesCount(_SC_HANDLE_STRUCT *,CServiceRecord *)
0x140068091  mov     rax, [rbp+37h+arg_78]
0x140068098  mov     [rax], r12
0x14006809b  test    r14b, 30h
0x14006809f  jz      short loc_1400680AE
0x1400680a1  mov     edx, 1; int
0x1400680a6  mov     rcx, r15; SourceString
0x1400680a9  call    ?ScUpdateServiceSidCache@@YAXPEBGH@Z; ScUpdateServiceSidCache(ushort const *,int)
0x1400680ae  call    ?ScDrainRemoteNotifyQueues@@YAXXZ; ScDrainRemoteNotifyQueues(void)
0x1400680b3  xor     edx, edx
0x1400680b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400680bc  cmp     rcx, rdi
0x1400680bf  jz      short loc_1400680EC
0x1400680c1  test    dword ptr [rcx+1Ch], 100h
0x1400680c8  jz      short loc_1400680EC
0x1400680ca  mov     rcx, [rcx+10h]
0x1400680ce  mov     rax, rdx
0x1400680d1  test    ebx, ebx
0x1400680d3  mov     edx, 2Fh ; '/'
0x1400680d8  mov     r9d, ebx
0x1400680db  mov     r8, rsi
0x1400680de  cmovz   rax, r12
0x1400680e2  mov     qword ptr [rsp+0F0h+var_D0], rax
0x1400680e7  call    WPP_SF_dq
0x1400680ec  lea     rcx, [rbp+37h+var_40]
0x1400680f0  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400680f5  mov     eax, ebx
0x1400680f7  mov     rbx, [rsp+0F0h+arg_0]
0x1400680ff  add     rsp, 0C0h
0x140068106  pop     r15
0x140068108  pop     r14
0x14006810a  pop     r13
0x14006810c  pop     r12
0x14006810e  pop     rdi
0x14006810f  pop     rsi
0x140068110  pop     rbp
0x140068111  retn
```
