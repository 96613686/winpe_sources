# LRPC_BASE_BINDING_HANDLE::DriveStateForward(int,ulong,LRPC_BIND_CCALL *)

- ea: `0x180028d70`
- end: `0x1800295e4`
- name: `?DriveStateForward@LRPC_BASE_BINDING_HANDLE@@QEAAJHKPEAVLRPC_BIND_CCALL@@@Z`
- size: `2164`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *__hidden this, int, unsigned int, struct LRPC_BIND_CCALL *)`
- caller_count: `4`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005ef40`
- `0x18008cb2c`
- `0x180095398`
- `0x1800a05d0`

## callees

- `0x180021ce0`
- `0x180021e18`
- `0x1800283bc`
- `0x180028a00`
- `0x180028d40`
- `0x180028d70`
- `0x1800295f0`
- `0x180029798`
- `0x180029c78`
- `0x180029cc4`
- `0x18002a2a0`
- `0x18002f460`
- `0x180032074`
- `0x18004c884`
- `0x180067d38`
- `0x180072be0`
- `0x180083094`
- `0x18008314c`
- `0x180083220`
- `0x18009cfb0`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180028eb1`
- `ntdll!RtlLeaveCriticalSection` at `0x180029054`
- `ntdll!RtlLeaveCriticalSection` at `0x180029106`
- `ntdll!RtlLeaveCriticalSection` at `0x180029125`
- `ntdll!RtlLeaveCriticalSection` at `0x1800292ec`
- `ntdll!RtlLeaveCriticalSection` at `0x180029388`
- `ntdll!RtlLeaveCriticalSection` at `0x18002946c`
- `ntdll!RtlLeaveCriticalSection` at `0x180028eb1`
- `ntdll!RtlLeaveCriticalSection` at `0x180029054`
- `ntdll!RtlLeaveCriticalSection` at `0x180029106`
- `ntdll!RtlLeaveCriticalSection` at `0x180029125`
- `ntdll!RtlLeaveCriticalSection` at `0x1800292ec`
- `ntdll!RtlLeaveCriticalSection` at `0x180029388`
- `ntdll!RtlLeaveCriticalSection` at `0x18002946c`
- `ntdll!RtlEnterCriticalSection` at `0x180028dc3`
- `ntdll!RtlEnterCriticalSection` at `0x1800292b7`
- `ntdll!RtlEnterCriticalSection` at `0x180028dc3`
- `ntdll!RtlEnterCriticalSection` at `0x1800292b7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291a1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291a1`

## pseudocode

```c
__int64 __fastcall LRPC_BASE_BINDING_HANDLE::DriveStateForward(
        LRPC_BASE_BINDING_HANDLE *this,
        int a2,
        unsigned int a3,
        struct _RPC_CLIENT_INTERFACE **a4)
{
  unsigned int v5; // r14d
  int v6; // r13d
  struct _RTL_CRITICAL_SECTION *v7; // r15
  struct LRPC_CASSOCIATION *Association; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r14
  unsigned int i; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebx
  int v18; // edx
  _QWORD *v20; // r9
  int v21; // edx
  int v22; // r8d
  _DWORD *v23; // rdx
  __int64 v24; // rcx
  _DWORD *v25; // rbx
  struct _RPC_CLIENT_INTERFACE *v26; // rcx
  LRPC_CASSOCIATION *v27; // rax
  PSID *v28; // r12
  _DWORD *v29; // r14
  LRPC_CLIENT_IO *v30; // rcx
  struct LRPC_CASSOCIATION *v31; // rax
  PSID v32; // rdx
  struct LRPC_CASSOCIATION *v33; // r13
  LPC_NORMALIZED_SID *v34; // r15
  void *v35; // rcx
  unsigned int v36; // ecx
  LPC_NORMALIZED_SID *v37; // rcx
  unsigned int v38; // ecx
  int v39; // eax
  void *v40; // rbx
  LRPC_CLIENT_IO *v41; // rcx
  EP_LOOKUP_DATA *v42; // rcx
  int v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+30h] [rbp-D0h]
  char v45; // [rsp+40h] [rbp-C0h] BYREF
  char v46; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v47; // [rsp+50h] [rbp-B0h]
  int v48; // [rsp+54h] [rbp-ACh]
  unsigned __int16 *v49; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v52[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v53[16]; // [rsp+90h] [rbp-70h] BYREF
  char *v54; // [rsp+A0h] [rbp-60h]
  __int64 v55; // [rsp+A8h] [rbp-58h]
  char *v56; // [rsp+B0h] [rbp-50h]
  __int64 v57; // [rsp+B8h] [rbp-48h]
  unsigned __int16 **v58; // [rsp+C0h] [rbp-40h]
  __int64 v59; // [rsp+C8h] [rbp-38h]
  __int64 *v60; // [rsp+D0h] [rbp-30h]
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 *v62; // [rsp+E0h] [rbp-20h]
  __int64 v63; // [rsp+E8h] [rbp-18h]

  v47 = a3;
  v5 = a3;
  v48 = a2;
  v6 = a2;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  while ( 1 )
  {
    RtlEnterCriticalSection(v7);
    Association = LRPC_BASE_CCALL::GetAssociation((LRPC_BASE_CCALL *)a4);
    v11 = *((_QWORD *)this + 61);
    if ( Association != (struct LRPC_CASSOCIATION *)v11 )
    {
      if ( Association )
        break;
    }
    if ( *((_DWORD *)this + 99) == *((_DWORD *)a4 + 180) )
    {
      v12 = *((int *)a4 + 181);
      if ( (_DWORD)v12 == 9 )
      {
        v20 = (_QWORD *)((char *)this + 424);
        v21 = *((_DWORD *)this + 105);
        v22 = (*((_DWORD *)this + 124) >> 1) & 1;
        if ( *((_DWORD *)this + 104) == 1 )
        {
          *v20 = 0;
          **((_DWORD **)this + 54) = 0;
          *(_QWORD *)(*((_QWORD *)this + 54) + 16LL) = -2;
          *((_DWORD *)this + 119) = v21 - 1;
          *((_BYTE *)this + 480) = 1;
          *((_BYTE *)this + 481) = v22;
        }
        else
        {
          v17 = LRPC_CASSOCIATION::OpenSecurityContextWorker(
                  v11,
                  v21,
                  (*((_DWORD *)this + 124) & 2) != 0,
                  (__int64)v20,
                  *((_QWORD *)this + 63));
          if ( v17 )
            goto LABEL_22;
        }
        if ( *((_DWORD *)this + 104) == 1 )
        {
          v23 = (_DWORD *)*((_QWORD *)this + 61);
          if ( *((_DWORD *)this + 104) == v23[53]
            && *((_DWORD *)this + 105) == v23[54]
            && ((*((_DWORD *)this + 124) >> 1) & 1) == v23[55] )
          {
            *((_DWORD *)this + 124) |= 0x40u;
          }
        }
        (*(void (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(*(_QWORD *)this + 504LL))(this);
      }
      if ( dword_1800F9624 )
      {
        for ( i = 0; i < 4; ++i )
        {
          if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
            goto LABEL_12;
        }
        if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
        {
          v24 = (int)(*((_DWORD *)this + 99) << 16);
          v54 = &v45;
          v51 = v12 | v24;
          v56 = &v46;
          v50 = 34;
          v58 = &v49;
          v60 = &v50;
          v62 = &v51;
          v49 = (unsigned __int16 *)this;
          v46 = 61;
          v45 = 104;
          v55 = 1;
          v57 = 1;
          v59 = 8;
          v61 = 8;
          v63 = 8;
          McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, v10, 6, (__int64)v53);
        }
      }
LABEL_12:
      *((_DWORD *)this + 99) = v12;
      v5 = v47;
    }
LABEL_13:
    v14 = LRPC_BIND_CCALL::NotifyBHStateChange(a4, *((unsigned int *)this + 99), 0);
    v17 = v14;
    if ( v14 )
    {
      RpcpErrorAddRecord(2u, v14, 0x399u, 0, 0);
      goto LABEL_22;
    }
    v18 = *((_DWORD *)this + 99);
    if ( v18 == 9 )
    {
      if ( !v6 || (*((_DWORD *)this + 124) & 1) != 0 )
        v17 = 0;
      else
        v17 = LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(this);
      if ( (*((_DWORD *)this + 124) & 0x20) != 0 && (*(_DWORD *)(*((_QWORD *)this + 61) + 208LL) & 4) != 0 )
        _InterlockedOr((volatile signed __int32 *)(*((_QWORD *)this + 61) + 208LL), 4u);
LABEL_22:
      RtlLeaveCriticalSection(v7);
      return v17;
    }
    if ( v18 == 6 )
    {
LABEL_35:
      RtlLeaveCriticalSection(v7);
      *((_DWORD *)a4 + 180) = 6;
      v25 = a4 + 81;
      *((_DWORD *)a4 + 181) = 7;
      if ( v6 )
      {
        LRPC_CLIENT_IO::ReinitCommon((LRPC_CLIENT_IO *)(a4 + 81));
        *v25 = 3;
        a4[82] = (struct _RPC_CLIENT_INTERFACE *)LrpcBHDriveStateForwardRoutine;
      }
      else
      {
        v26 = a4[89];
        *v25 = 1;
        *((_DWORD *)a4 + 166) = 0;
        *((_DWORD *)a4 + 176) = -1073606632;
        if ( v26 )
        {
          FreeEEInfoChain(v26);
          a4[89] = 0;
        }
        a4[85] = 0;
      }
      v27 = LRPC_BASE_CCALL::GetAssociation((LRPC_BASE_CCALL *)a4);
      v17 = LRPC_CASSOCIATION::Connect(
              v27,
              (struct LRPC_CLIENT_IO *)(a4 + 81),
              v6,
              v5,
              (PSID *)this + 50,
              *((void **)this + 51));
      if ( v17 )
        return v17;
    }
    else
    {
      switch ( v18 )
      {
        case 1:
        case 3:
          RtlLeaveCriticalSection(v7);
          v41 = (LRPC_CLIENT_IO *)(a4 + 81);
          if ( v6 )
          {
            LRPC_CLIENT_IO::ReinitCommon(v41);
            *((_DWORD *)a4 + 162) = 3;
            a4[82] = (struct _RPC_CLIENT_INTERFACE *)LrpcBHDriveStateForwardRoutine;
          }
          else
          {
            *((_DWORD *)a4 + 162) = 1;
            *((_DWORD *)a4 + 166) = 0;
            LRPC_CLIENT_IO::ReinitCommon(v41);
          }
          v17 = LRPC_BASE_BINDING_HANDLE::ResolveEndpoint(this, (struct LRPC_CLIENT_IO *)(a4 + 81), a4[80], v6, v5);
          if ( v17 )
            return v17;
          continue;
        case 2:
          v42 = (EP_LOOKUP_DATA *)*((_QWORD *)this + 9);
          v49 = 0;
          v17 = EP_LOOKUP_DATA::ReturnLookupValues(v42, &v49);
          if ( v17 )
            goto LABEL_22;
          (*(void (__fastcall **)(LRPC_BASE_BINDING_HANDLE *))(*(_QWORD *)this + 392LL))(this);
          (*(void (__fastcall **)(LRPC_BASE_BINDING_HANDLE *, unsigned __int16 *))(*(_QWORD *)this + 408LL))(this, v49);
          LogEvent(0x68u, 0x3Du, this, (void *)0x22, (int)(*((_DWORD *)this + 99) << 16) | 4LL, v43, v44);
          *((_DWORD *)this + 99) = 4;
          goto LABEL_13;
        case 4:
          v17 = LRPC_BASE_BINDING_HANDLE::PickAssociation(this);
          if ( v17 )
            goto LABEL_22;
          goto LABEL_13;
        case 5:
          if ( !dword_1800F9624 )
            goto LABEL_34;
          v36 = 0;
          while ( 2 )
          {
            if ( v36 >= 4 )
            {
              if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
              {
                LOBYTE(v16) = 61;
                LOBYTE(v15) = 104;
                McTemplateU0uuxxx_EtwEventWriteTransfer(v36, v18 << 16, v15, v16, (char)this, 34, 6);
              }
            }
            else if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[v36] != 104 )
            {
              ++v36;
              continue;
            }
            break;
          }
LABEL_34:
          *((_DWORD *)this + 99) = 6;
          goto LABEL_35;
        case 7:
          if ( !dword_1800F9624 )
            goto LABEL_43;
          v38 = 0;
          break;
        case 8:
          goto LABEL_44;
        default:
          v17 = 1766;
          goto LABEL_22;
      }
      while ( v38 < 4 )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[v38] == 104 )
          goto LABEL_43;
        ++v38;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        LOBYTE(v16) = 61;
        LOBYTE(v15) = 104;
        McTemplateU0uuxxx_EtwEventWriteTransfer(v38, v18 << 16, v15, v16, (char)this, 34, 8);
      }
LABEL_43:
      *((_DWORD *)this + 99) = 8;
LABEL_44:
      if ( !v6 || (*((_DWORD *)this + 124) & 1) != 0 )
      {
        RtlLeaveCriticalSection(v7);
      }
      else
      {
        v17 = LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(this);
        RtlLeaveCriticalSection(v7);
        if ( v17 )
          return v17;
      }
      v28 = (PSID *)((char *)this + 400);
      *((_DWORD *)a4 + 180) = 8;
      *((_DWORD *)a4 + 181) = 9;
      if ( *((_QWORD *)this + 50) )
      {
        v29 = a4 + 81;
        v30 = (LRPC_CLIENT_IO *)(a4 + 81);
        if ( v6 )
        {
          LRPC_CLIENT_IO::ReinitCommon(v30);
          *v29 = 3;
          a4[82] = (struct _RPC_CLIENT_INTERFACE *)LrpcBHDriveStateForwardRoutine;
        }
        else
        {
          *v29 = 1;
          *((_DWORD *)a4 + 166) = 0;
          LRPC_CLIENT_IO::ReinitCommon(v30);
        }
        v31 = LRPC_BASE_CCALL::GetAssociation((LRPC_BASE_CCALL *)a4);
        v32 = *v28;
        v33 = v31;
        v34 = (struct LRPC_CASSOCIATION *)((char *)v31 + 192);
        v35 = (void *)*((_QWORD *)v31 + 24);
        if ( v35 )
        {
          if ( EqualSid(v35, v32) )
          {
            v17 = 0;
            goto LABEL_54;
          }
          v17 = LPC_NORMALIZED_SID::PrepareIterationInternal(
                  v34,
                  (LRPC_BASE_BINDING_HANDLE *)((char *)this + 400),
                  v33,
                  v48,
                  (struct LRPC_CLIENT_IO *)(a4 + 81),
                  v47);
          if ( v17 )
          {
LABEL_62:
            v52[0] = 3;
            v52[2] = *(_QWORD *)v34 != 0;
            RpcpErrorAddRecord(2u, v17, 0x488u, 1, (struct tagParam *)v52);
            goto LABEL_74;
          }
          goto LABEL_93;
        }
        v39 = LRPC_CASSOCIATION::AlpcVerifyServerSid(v31, v32);
        v17 = v39;
        if ( v39 )
        {
          if ( v39 != -1073606633 )
            goto LABEL_62;
          v17 = LPC_NORMALIZED_SID::PrepareIterationInternal(
                  v34,
                  (LRPC_BASE_BINDING_HANDLE *)((char *)this + 400),
                  v33,
                  v48,
                  (struct LRPC_CLIENT_IO *)(a4 + 81),
                  v47);
          if ( v17 )
            goto LABEL_62;
LABEL_93:
          v17 = LPC_NORMALIZED_SID::IterateAndVerify(v37, (LRPC_BASE_BINDING_HANDLE *)((char *)this + 400), v33);
          goto LABEL_73;
        }
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v33 + 144));
        if ( !*(_QWORD *)v34 )
        {
          v40 = DuplicateSID(*v28);
          if ( v40 )
          {
            LPC_NORMALIZED_SID::FreeOldSid(v34);
            *(_QWORD *)v34 = v40;
            v17 = 0;
          }
          else
          {
            v17 = 14;
          }
        }
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v33 + 144));
LABEL_73:
        if ( v17 )
          goto LABEL_62;
LABEL_74:
        if ( v17 == -1073606633 )
          return 5;
LABEL_54:
        if ( v17 )
          return v17;
        v6 = v48;
        v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
        v5 = v47;
      }
    }
  }
  RtlLeaveCriticalSection(v7);
  RpcpErrorAddRecord(2u, -1073606609, 0x398u, 0, 0);
  return 3221360687LL;
}

```

## disassembly

```asm
0x180028d70  push    rbp
0x180028d72  push    rbx
0x180028d73  push    rsi
0x180028d74  push    rdi
0x180028d75  push    r12
0x180028d77  push    r13
0x180028d79  push    r14
0x180028d7b  push    r15
0x180028d7d  lea     rbp, [rsp-8]
0x180028d82  sub     rsp, 108h
0x180028d89  mov     rax, cs:__security_cookie
0x180028d90  xor     rax, rsp
0x180028d93  mov     [rbp+40h+var_50], rax
0x180028d97  mov     rsi, r9
0x180028d9a  mov     [rsp+140h+var_F0], r8d
0x180028d9f  mov     r14d, r8d
0x180028da2  mov     [rsp+140h+var_EC], edx
0x180028da6  mov     r13d, edx
0x180028da9  lea     r15, [rcx+130h]
0x180028db0  mov     rdi, rcx
0x180028db3  lea     r12, __ImageBase
0x180028dba  xor     ebx, ebx
0x180028dbc  nop     dword ptr [rax+00h]
0x180028dc0  mov     rcx, r15; CriticalSection
0x180028dc3  call    cs:__imp_RtlEnterCriticalSection
0x180028dc9  mov     rcx, rsi; this
0x180028dcc  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x180028dd1  mov     rcx, [rdi+1E8h]
0x180028dd8  cmp     rax, rcx
0x180028ddb  jnz     loc_180029460
0x180028de1  mov     eax, [rsi+2D0h]
0x180028de7  cmp     [rdi+18Ch], eax
0x180028ded  jnz     short loc_180028E3B
0x180028def  movsxd  r14, dword ptr [rsi+2D4h]
0x180028df6  cmp     r14d, 9
0x180028dfa  jz      loc_180028ED9
0x180028e00  cmp     cs:dword_1800F9624, 0
0x180028e07  jz      short loc_180028E2F
0x180028e09  mov     eax, ebx
0x180028e0b  cmp     eax, 4
0x180028e0e  jnb     short loc_180028E22
0x180028e10  movsxd  rcx, eax
0x180028e13  cmp     byte ptr [rcx+r12+0E1808h], 68h ; 'h'
0x180028e1c  jz      short loc_180028E2F
0x180028e1e  inc     eax
0x180028e20  jmp     short loc_180028E0B
0x180028e22  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180028e29  jnz     loc_180028F92
0x180028e2f  mov     [rdi+18Ch], r14d
0x180028e36  mov     r14d, [rsp+140h+var_F0]
0x180028e3b  mov     edx, [rdi+18Ch]
0x180028e41  xor     r8d, r8d
0x180028e44  mov     rcx, rsi
0x180028e47  call    ?NotifyBHStateChange@LRPC_BIND_CCALL@@QEAAJW4tagLrpcBHStates@@PEAPEAVLRPC_CASSOCIATION@@@Z; LRPC_BIND_CCALL::NotifyBHStateChange(tagLrpcBHStates,LRPC_CASSOCIATION * *)
0x180028e4c  mov     ebx, eax
0x180028e4e  test    eax, eax
0x180028e50  jnz     loc_18002959E
0x180028e56  mov     edx, [rdi+18Ch]
0x180028e5c  cmp     edx, 9
0x180028e5f  jz      short loc_180028E95
0x180028e61  cmp     edx, 6
0x180028e64  jz      loc_180029051
0x180028e6a  lea     eax, [rdx-1]; switch 8 cases
0x180028e6d  cmp     eax, 7
0x180028e70  ja      def_180028E83; jumptable 0000000180028E83 default case, case 6
0x180028e76  cdqe
0x180028e78  mov     ecx, ds:(jpt_180028E83 - 180000000h)[r12+rax*4]
0x180028e80  add     rcx, r12
0x180028e83  jmp     rcx; switch jump
0x180028e85  mov     rcx, rdi; jumptable 0000000180028E83 case 4
0x180028e88  call    ?PickAssociation@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::PickAssociation(void)
0x180028e8d  mov     ebx, eax
0x180028e8f  test    eax, eax
0x180028e91  jz      short loc_180028E3B
0x180028e93  jmp     short loc_180028EAE
0x180028e95  test    r13d, r13d
0x180028e98  jnz     loc_180029421
0x180028e9e  xor     ebx, ebx
0x180028ea0  mov     eax, [rdi+1F0h]
0x180028ea6  test    al, 20h
0x180028ea8  jnz     loc_180029560
0x180028eae  mov     rcx, r15; CriticalSection
0x180028eb1  call    cs:__imp_RtlLeaveCriticalSection
0x180028eb7  mov     eax, ebx
0x180028eb9  mov     rcx, [rbp+40h+var_50]
0x180028ebd  xor     rcx, rsp; StackCookie
0x180028ec0  call    __security_check_cookie
0x180028ec5  add     rsp, 108h
0x180028ecc  pop     r15
0x180028ece  pop     r14
0x180028ed0  pop     r13
0x180028ed2  pop     r12
0x180028ed4  pop     rdi
0x180028ed5  pop     rsi
0x180028ed6  pop     rbx
0x180028ed7  pop     rbp
0x180028ed8  retn
0x180028ed9  mov     r8d, [rdi+1F0h]
0x180028ee0  lea     r9, [rdi+1A8h]
0x180028ee7  mov     rax, [rdi+1F8h]
0x180028eee  mov     edx, [rdi+1A4h]
0x180028ef4  shr     r8d, 1
0x180028ef7  and     r8d, 1
0x180028efb  cmp     dword ptr [rdi+1A0h], 1
0x180028f02  jnz     loc_18002936A
0x180028f08  mov     [r9], rbx
0x180028f0b  mov     rax, [r9+8]
0x180028f0f  mov     [rax], ebx
0x180028f11  mov     rax, [r9+8]
0x180028f15  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x180028f1d  lea     eax, [rdx-1]
0x180028f20  mov     [r9+34h], eax
0x180028f24  mov     byte ptr [r9+38h], 1
0x180028f29  mov     [r9+39h], r8b
0x180028f2d  cmp     dword ptr [rdi+1A0h], 1
0x180028f34  jnz     short loc_180028F7B
0x180028f36  mov     ecx, [rdi+1F0h]
0x180028f3c  mov     rdx, [rdi+1E8h]
0x180028f43  shr     ecx, 1
0x180028f45  and     ecx, 1
0x180028f48  mov     eax, [rdx+0D4h]
0x180028f4e  cmp     [rdi+1A0h], eax
0x180028f54  jnz     short loc_180028F7B
0x180028f56  mov     eax, [rdx+0D8h]
0x180028f5c  cmp     [rdi+1A4h], eax
0x180028f62  jnz     short loc_180028F7B
0x180028f64  cmp     ecx, [rdx+0DCh]
0x180028f6a  jnz     short loc_180028F7B
0x180028f6c  mov     eax, [rdi+1F0h]
0x180028f72  or      eax, 40h
0x180028f75  mov     [rdi+1F0h], eax
0x180028f7b  mov     rax, [rdi]
0x180028f7e  mov     rcx, rdi
0x180028f81  mov     rax, [rax+1F8h]
0x180028f88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f8d  jmp     loc_180028E00
0x180028f92  mov     eax, [rdi+18Ch]
0x180028f98  lea     rdx, RPCLogEvent
0x180028f9f  shl     eax, 10h
0x180028fa2  mov     r9d, 6
0x180028fa8  movsxd  rcx, eax
0x180028fab  lea     rax, [rsp+140h+var_100]
0x180028fb0  mov     [rbp+40h+var_A0], rax
0x180028fb4  or      rcx, r14
0x180028fb7  lea     rax, [rsp+140h+var_F8]
0x180028fbc  mov     [rsp+140h+var_D8], rcx
0x180028fc1  mov     [rbp+40h+var_90], rax
0x180028fc5  lea     rcx, RpcEtwGuid_Context
0x180028fcc  lea     rax, [rsp+140h+var_E8]
0x180028fd1  mov     [rsp+140h+var_E0], 22h ; '"'
0x180028fda  mov     [rbp+40h+var_80], rax
0x180028fde  lea     rax, [rsp+140h+var_E0]
0x180028fe3  mov     [rbp+40h+var_70], rax
0x180028fe7  lea     rax, [rsp+140h+var_D8]
0x180028fec  mov     [rbp+40h+var_60], rax
0x180028ff0  lea     rax, [rbp+40h+var_B0]
0x180028ff4  mov     [rsp+140h+var_120], rax
0x180028ff9  mov     [rsp+140h+var_E8], rdi
0x180028ffe  mov     [rsp+140h+var_F8], 3Dh ; '='
0x180029003  mov     [rsp+140h+var_100], 68h ; 'h'
0x180029008  mov     [rbp+40h+var_98], 1
0x180029010  mov     [rbp+40h+var_88], 1
0x180029018  mov     [rbp+40h+var_78], 8
0x180029020  mov     [rbp+40h+var_68], 8
0x180029028  mov     [rbp+40h+var_58], 8
0x180029030  call    McGenEventWrite_EtwEventWriteTransfer
0x180029035  jmp     loc_180028E2F
0x18002903a  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x180029041  jnz     loc_180029310
0x180029047  mov     dword ptr [rdi+18Ch], 6
0x180029051  mov     rcx, r15; CriticalSection
0x180029054  call    cs:__imp_RtlLeaveCriticalSection
0x18002905a  mov     dword ptr [rsi+2D0h], 6
0x180029064  lea     rbx, [rsi+288h]
0x18002906b  mov     dword ptr [rsi+2D4h], 7
0x180029075  test    r13d, r13d
0x180029078  jnz     loc_1800293E1
0x18002907e  mov     rcx, [rbx+40h]
0x180029082  mov     dword ptr [rbx], 1
0x180029088  mov     [rsi+298h], r13d
0x18002908f  mov     dword ptr [rbx+38h], 0C0021018h
0x180029096  test    rcx, rcx
0x180029099  jnz     loc_1800291F9
0x18002909f  mov     qword ptr [rbx+20h], 0
0x1800290a7  mov     rcx, rsi; this
0x1800290aa  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x1800290af  mov     rcx, [rdi+198h]
0x1800290b6  lea     r8, [rdi+190h]
0x1800290bd  mov     [rsp+140h+var_118], rcx; void *
0x1800290c2  mov     r9d, r14d; unsigned int
0x1800290c5  mov     [rsp+140h+var_120], r8; struct LPC_NORMALIZED_SID *
0x1800290ca  mov     rdx, rbx; struct LRPC_CLIENT_IO *
0x1800290cd  mov     r8d, r13d; int
0x1800290d0  mov     rcx, rax; this
0x1800290d3  call    ?Connect@LRPC_CASSOCIATION@@QEAAJPEAVLRPC_CLIENT_IO@@HKPEAVLPC_NORMALIZED_SID@@PEAX@Z; LRPC_CASSOCIATION::Connect(LRPC_CLIENT_IO *,int,ulong,LPC_NORMALIZED_SID *,void *)
0x1800290d8  mov     ebx, eax
0x1800290da  test    eax, eax
0x1800290dc  jz      loc_180028DBA
0x1800290e2  jmp     loc_180028EB7
0x1800290e7  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x1800290ee  jnz     loc_18002933D
0x1800290f4  mov     dword ptr [rdi+18Ch], 8
0x1800290fe  test    r13d, r13d; jumptable 0000000180028E83 case 8
0x180029101  jnz     short loc_18002910E
0x180029103  mov     rcx, r15; CriticalSection
0x180029106  call    cs:__imp_RtlLeaveCriticalSection
0x18002910c  jmp     short loc_180029133
0x18002910e  mov     eax, [rdi+1F0h]
0x180029114  test    al, 1
0x180029116  jnz     short loc_180029103
0x180029118  mov     rcx, rdi; this
0x18002911b  call    ?EnableAsyncIfNecessary@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(void)
0x180029120  mov     rcx, r15; CriticalSection
0x180029123  mov     ebx, eax
0x180029125  call    cs:__imp_RtlLeaveCriticalSection
0x18002912b  test    ebx, ebx
0x18002912d  jnz     loc_180028EB7
0x180029133  lea     r12, [rdi+190h]
0x18002913a  mov     dword ptr [rsi+2D0h], 8
0x180029144  mov     dword ptr [rsi+2D4h], 9
0x18002914e  cmp     qword ptr [r12], 0
0x180029153  jz      loc_180028DB3
0x180029159  lea     r14, [rsi+288h]
0x180029160  mov     rcx, r14; this
0x180029163  test    r13d, r13d
0x180029166  jnz     loc_180029402
0x18002916c  mov     dword ptr [r14], 1
0x180029173  mov     [rsi+298h], r13d
0x18002917a  call    ?ReinitCommon@LRPC_CLIENT_IO@@QEAAXXZ; LRPC_CLIENT_IO::ReinitCommon(void)
0x18002917f  mov     rcx, rsi; this
0x180029182  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x180029187  mov     rdx, [r12]; void *
0x18002918b  mov     r13, rax
0x18002918e  lea     r15, [rax+0C0h]
0x180029195  mov     rcx, [r15]; pSid1
0x180029198  test    rcx, rcx
0x18002919b  jz      loc_18002929E
0x1800291a1  call    cs:__imp_EqualSid
0x1800291a7  test    eax, eax
0x1800291a9  jz      short loc_18002920B
0x1800291ab  xor     ebx, ebx
0x1800291ad  test    ebx, ebx
0x1800291af  jnz     loc_180028EB7
0x1800291b5  mov     r13d, [rsp+140h+var_EC]
0x1800291ba  lea     r15, [rdi+130h]
0x1800291c1  mov     r14d, [rsp+140h+var_F0]
0x1800291c6  jmp     loc_180028DB3
0x1800291cb  cmp     cs:dword_1800F9624, 0; jumptable 0000000180028E83 case 5
0x1800291d2  jz      loc_180029047
0x1800291d8  xor     ecx, ecx
0x1800291da  cmp     ecx, 4
0x1800291dd  jnb     loc_18002903A
0x1800291e3  movsxd  rax, ecx
0x1800291e6  cmp     byte ptr [rax+r12+0E1808h], 68h ; 'h'
0x1800291ef  jz      loc_180029047
0x1800291f5  inc     ecx
0x1800291f7  jmp     short loc_1800291DA
0x1800291f9  call    FreeEEInfoChain
0x1800291fe  mov     qword ptr [rbx+40h], 0
0x180029206  jmp     loc_18002909F
0x18002920b  mov     eax, [rsp+140h+var_F0]
0x18002920f  mov     r8, r13; struct LRPC_CASSOCIATION *
0x180029212  mov     r9d, [rsp+140h+var_EC]; int
0x180029217  mov     rdx, r12; struct LPC_NORMALIZED_SID *
0x18002921a  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x18002921e  mov     rcx, r15; this
0x180029221  mov     [rsp+140h+var_120], r14; struct LRPC_CLIENT_IO *
0x180029226  call    ?PrepareIterationInternal@LPC_NORMALIZED_SID@@AEAAJPEAV1@PEAVLRPC_CASSOCIATION@@HPEAVLRPC_CLIENT_IO@@K@Z; LPC_NORMALIZED_SID::PrepareIterationInternal(LPC_NORMALIZED_SID *,LRPC_CASSOCIATION *,int,LRPC_CLIENT_IO *,ulong)
0x18002922b  mov     ebx, eax
0x18002922d  test    eax, eax
0x18002922f  jz      loc_18002954E
0x180029235  xor     eax, eax
0x180029237  mov     [rsp+140h+var_D0], 3
0x18002923f  cmp     [r15], rax
0x180029242  mov     r8d, 488h; unsigned __int16
0x180029248  mov     r9d, 1; int
0x18002924e  mov     edx, ebx; int
0x180029250  setnz   al
0x180029253  mov     ecx, 2; unsigned int
0x180029258  mov     [rsp+140h+var_C8], eax
0x18002925c  lea     rax, [rsp+140h+var_D0]
0x180029261  mov     [rsp+140h+var_120], rax; struct tagParam *
0x180029266  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002926b  jmp     loc_1800292FA
0x180029270  cmp     cs:dword_1800F9624, 0; jumptable 0000000180028E83 case 7
0x180029277  jz      loc_1800290F4
0x18002927d  xor     ecx, ecx
0x18002927f  cmp     ecx, 4
0x180029282  jnb     loc_1800290E7
0x180029288  movsxd  rax, ecx
0x18002928b  cmp     byte ptr [rax+r12+0E1808h], 68h ; 'h'
0x180029294  jz      loc_1800290F4
0x18002929a  inc     ecx
0x18002929c  jmp     short loc_18002927F
0x18002929e  mov     rcx, r13; this
0x1800292a1  call    ?AlpcVerifyServerSid@LRPC_CASSOCIATION@@QEAAJPEAX@Z; LRPC_CASSOCIATION::AlpcVerifyServerSid(void *)
0x1800292a6  mov     ebx, eax
0x1800292a8  test    eax, eax
0x1800292aa  jnz     loc_180029519
0x1800292b0  lea     rcx, [r13+90h]; CriticalSection
  ... truncated ...
```
