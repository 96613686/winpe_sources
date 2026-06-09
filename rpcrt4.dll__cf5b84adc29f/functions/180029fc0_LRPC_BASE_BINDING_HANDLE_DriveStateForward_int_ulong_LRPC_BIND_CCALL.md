# LRPC_BASE_BINDING_HANDLE::DriveStateForward(int,ulong,LRPC_BIND_CCALL *)

- ea: `0x180029fc0`
- end: `0x18002a874`
- name: `?DriveStateForward@LRPC_BASE_BINDING_HANDLE@@QEAAJHKPEAVLRPC_BIND_CCALL@@@Z`
- size: `2228`
- prototype: `__int64 __fastcall(LRPC_BASE_BINDING_HANDLE *this, int, unsigned int, struct _RPC_CLIENT_INTERFACE **)`
- caller_count: `4`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180034f5c`
- `0x180065660`
- `0x180098aa8`
- `0x1800a3c70`

## callees

- `0x1800080c0`
- `0x1800160b0`
- `0x180022e80`
- `0x180022fb8`
- `0x1800295d8`
- `0x180029c38`
- `0x180029f90`
- `0x180029fc0`
- `0x18002a880`
- `0x18002aa3c`
- `0x18002af34`
- `0x18002af84`
- `0x18002b520`
- `0x1800307e0`
- `0x1800334e4`
- `0x180071ad0`
- `0x180084958`
- `0x180084a14`
- `0x180084af4`
- `0x1800a0230`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002a10b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a2b5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a36d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a392`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a56b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a60d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a6f7`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a10b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a2b5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a36d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a392`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a56b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a60d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a6f7`
- `ntdll!RtlEnterCriticalSection` at `0x18002a013`
- `ntdll!RtlEnterCriticalSection` at `0x18002a530`
- `ntdll!RtlEnterCriticalSection` at `0x18002a013`
- `ntdll!RtlEnterCriticalSection` at `0x18002a530`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a414`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002a414`

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
  int v10; // r8d
  struct LRPC_CASSOCIATION *v11; // rcx
  __int64 v12; // r14
  unsigned int i; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebx
  int v18; // edx
  _QWORD *v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
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
    v11 = (struct LRPC_CASSOCIATION *)*((_QWORD *)this + 61);
    if ( Association != v11 )
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
        v21 = *((unsigned int *)this + 105);
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
          v17 = LRPC_CASSOCIATION::OpenSecurityContextWorker(v11, v21, v22, v20, *((_QWORD *)this + 63));
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
      if ( dword_1800FE624 )
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
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&RpcEtwGuid_Context,
            (unsigned int)RPCLogEvent,
            v10,
            6,
            (__int64)v53);
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
          FreeEEInfoChain();
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
              (LRPC_BASE_BINDING_HANDLE *)((char *)this + 400),
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
          if ( !dword_1800FE624 )
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
          if ( !dword_1800FE624 )
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
0x180029fc0  push    rbp
0x180029fc2  push    rbx
0x180029fc3  push    rsi
0x180029fc4  push    rdi
0x180029fc5  push    r12
0x180029fc7  push    r13
0x180029fc9  push    r14
0x180029fcb  push    r15
0x180029fcd  lea     rbp, [rsp-8]
0x180029fd2  sub     rsp, 108h
0x180029fd9  mov     rax, cs:__security_cookie
0x180029fe0  xor     rax, rsp
0x180029fe3  mov     [rbp+40h+var_50], rax
0x180029fe7  mov     rsi, r9
0x180029fea  mov     [rsp+140h+var_F0], r8d
0x180029fef  mov     r14d, r8d
0x180029ff2  mov     [rsp+140h+var_EC], edx
0x180029ff6  mov     r13d, edx
0x180029ff9  lea     r15, [rcx+130h]
0x18002a000  mov     rdi, rcx
0x18002a003  lea     r12, __ImageBase
0x18002a00a  xor     ebx, ebx
0x18002a00c  nop     dword ptr [rax+00h]
0x18002a010  mov     rcx, r15; CriticalSection
0x18002a013  call    cs:__imp_RtlEnterCriticalSection
0x18002a01a  nop     dword ptr [rax+rax+00h]
0x18002a01f  mov     rcx, rsi; this
0x18002a022  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x18002a027  mov     rcx, [rdi+1E8h]
0x18002a02e  cmp     rax, rcx
0x18002a031  jnz     loc_18002A6EB
0x18002a037  mov     eax, [rsi+2D0h]
0x18002a03d  cmp     [rdi+18Ch], eax
0x18002a043  jnz     short loc_18002A091
0x18002a045  movsxd  r14, dword ptr [rsi+2D4h]
0x18002a04c  cmp     r14d, 9
0x18002a050  jz      loc_18002A13A
0x18002a056  cmp     cs:dword_1800FE624, 0
0x18002a05d  jz      short loc_18002A085
0x18002a05f  mov     eax, ebx
0x18002a061  cmp     eax, 4
0x18002a064  jnb     short loc_18002A078
0x18002a066  movsxd  rcx, eax
0x18002a069  cmp     byte ptr [rcx+r12+0E66D8h], 68h ; 'h'
0x18002a072  jz      short loc_18002A085
0x18002a074  inc     eax
0x18002a076  jmp     short loc_18002A061
0x18002a078  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002a07f  jnz     loc_18002A1F3
0x18002a085  mov     [rdi+18Ch], r14d
0x18002a08c  mov     r14d, [rsp+140h+var_F0]
0x18002a091  mov     edx, [rdi+18Ch]
0x18002a097  xor     r8d, r8d
0x18002a09a  mov     rcx, rsi
0x18002a09d  call    ?NotifyBHStateChange@LRPC_BIND_CCALL@@QEAAJW4tagLrpcBHStates@@PEAPEAVLRPC_CASSOCIATION@@@Z; LRPC_BIND_CCALL::NotifyBHStateChange(tagLrpcBHStates,LRPC_CASSOCIATION * *)
0x18002a0a2  mov     ebx, eax
0x18002a0a4  test    eax, eax
0x18002a0a6  jnz     loc_18002A82F
0x18002a0ac  mov     edx, [rdi+18Ch]
0x18002a0b2  cmp     edx, 9
0x18002a0b5  jz      short loc_18002A0EF
0x18002a0b7  cmp     edx, 6
0x18002a0ba  jz      loc_18002A2B2
0x18002a0c0  lea     eax, [rdx-1]; switch 8 cases
0x18002a0c3  cmp     eax, 7
0x18002a0c6  ja      def_18002A0D9; jumptable 000000018002A0D9 default case, case 6
0x18002a0cc  cdqe
0x18002a0ce  mov     ecx, ds:(jpt_18002A0D9 - 180000000h)[r12+rax*4]
0x18002a0d6  add     rcx, r12
0x18002a0d9  jmp     rcx; switch jump
0x18002a0df  mov     rcx, rdi; jumptable 000000018002A0D9 case 4
0x18002a0e2  call    ?PickAssociation@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::PickAssociation(void)
0x18002a0e7  mov     ebx, eax
0x18002a0e9  test    eax, eax
0x18002a0eb  jz      short loc_18002A091
0x18002a0ed  jmp     short loc_18002A108
0x18002a0ef  test    r13d, r13d
0x18002a0f2  jnz     loc_18002A6AC
0x18002a0f8  xor     ebx, ebx
0x18002a0fa  mov     eax, [rdi+1F0h]
0x18002a100  test    al, 20h
0x18002a102  jnz     loc_18002A7F1
0x18002a108  mov     rcx, r15; CriticalSection
0x18002a10b  call    cs:__imp_RtlLeaveCriticalSection
0x18002a112  nop     dword ptr [rax+rax+00h]
0x18002a117  mov     eax, ebx
0x18002a119  mov     rcx, [rbp+40h+var_50]
0x18002a11d  xor     rcx, rsp; StackCookie
0x18002a120  call    __security_check_cookie
0x18002a125  add     rsp, 108h
0x18002a12c  pop     r15
0x18002a12e  pop     r14
0x18002a130  pop     r13
0x18002a132  pop     r12
0x18002a134  pop     rdi
0x18002a135  pop     rsi
0x18002a136  pop     rbx
0x18002a137  pop     rbp
0x18002a138  retn
0x18002a13a  mov     r8d, [rdi+1F0h]
0x18002a141  lea     r9, [rdi+1A8h]
0x18002a148  mov     rax, [rdi+1F8h]
0x18002a14f  mov     edx, [rdi+1A4h]
0x18002a155  shr     r8d, 1
0x18002a158  and     r8d, 1
0x18002a15c  cmp     dword ptr [rdi+1A0h], 1
0x18002a163  jnz     loc_18002A5EF
0x18002a169  mov     [r9], rbx
0x18002a16c  mov     rax, [r9+8]
0x18002a170  mov     [rax], ebx
0x18002a172  mov     rax, [r9+8]
0x18002a176  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x18002a17e  lea     eax, [rdx-1]
0x18002a181  mov     [r9+34h], eax
0x18002a185  mov     byte ptr [r9+38h], 1
0x18002a18a  mov     [r9+39h], r8b
0x18002a18e  cmp     dword ptr [rdi+1A0h], 1
0x18002a195  jnz     short loc_18002A1DC
0x18002a197  mov     ecx, [rdi+1F0h]
0x18002a19d  mov     rdx, [rdi+1E8h]
0x18002a1a4  shr     ecx, 1
0x18002a1a6  and     ecx, 1
0x18002a1a9  mov     eax, [rdx+0D4h]
0x18002a1af  cmp     [rdi+1A0h], eax
0x18002a1b5  jnz     short loc_18002A1DC
0x18002a1b7  mov     eax, [rdx+0D8h]
0x18002a1bd  cmp     [rdi+1A4h], eax
0x18002a1c3  jnz     short loc_18002A1DC
0x18002a1c5  cmp     ecx, [rdx+0DCh]
0x18002a1cb  jnz     short loc_18002A1DC
0x18002a1cd  mov     eax, [rdi+1F0h]
0x18002a1d3  or      eax, 40h
0x18002a1d6  mov     [rdi+1F0h], eax
0x18002a1dc  mov     rax, [rdi]
0x18002a1df  mov     rcx, rdi
0x18002a1e2  mov     rax, [rax+1F8h]
0x18002a1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1ee  jmp     loc_18002A056
0x18002a1f3  mov     eax, [rdi+18Ch]
0x18002a1f9  lea     rdx, RPCLogEvent
0x18002a200  shl     eax, 10h
0x18002a203  mov     r9d, 6
0x18002a209  movsxd  rcx, eax
0x18002a20c  lea     rax, [rsp+140h+var_100]
0x18002a211  mov     [rbp+40h+var_A0], rax
0x18002a215  or      rcx, r14
0x18002a218  lea     rax, [rsp+140h+var_F8]
0x18002a21d  mov     [rsp+140h+var_D8], rcx
0x18002a222  mov     [rbp+40h+var_90], rax
0x18002a226  lea     rcx, RpcEtwGuid_Context
0x18002a22d  lea     rax, [rsp+140h+var_E8]
0x18002a232  mov     [rsp+140h+var_E0], 22h ; '"'
0x18002a23b  mov     [rbp+40h+var_80], rax
0x18002a23f  lea     rax, [rsp+140h+var_E0]
0x18002a244  mov     [rbp+40h+var_70], rax
0x18002a248  lea     rax, [rsp+140h+var_D8]
0x18002a24d  mov     [rbp+40h+var_60], rax
0x18002a251  lea     rax, [rbp+40h+var_B0]
0x18002a255  mov     [rsp+140h+var_120], rax
0x18002a25a  mov     [rsp+140h+var_E8], rdi
0x18002a25f  mov     [rsp+140h+var_F8], 3Dh ; '='
0x18002a264  mov     [rsp+140h+var_100], 68h ; 'h'
0x18002a269  mov     [rbp+40h+var_98], 1
0x18002a271  mov     [rbp+40h+var_88], 1
0x18002a279  mov     [rbp+40h+var_78], 8
0x18002a281  mov     [rbp+40h+var_68], 8
0x18002a289  mov     [rbp+40h+var_58], 8
0x18002a291  call    McGenEventWrite_EtwEventWriteTransfer
0x18002a296  jmp     loc_18002A085
0x18002a29b  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002a2a2  jnz     loc_18002A595
0x18002a2a8  mov     dword ptr [rdi+18Ch], 6
0x18002a2b2  mov     rcx, r15; CriticalSection
0x18002a2b5  call    cs:__imp_RtlLeaveCriticalSection
0x18002a2bc  nop     dword ptr [rax+rax+00h]
0x18002a2c1  mov     dword ptr [rsi+2D0h], 6
0x18002a2cb  lea     rbx, [rsi+288h]
0x18002a2d2  mov     dword ptr [rsi+2D4h], 7
0x18002a2dc  test    r13d, r13d
0x18002a2df  jnz     loc_18002A66C
0x18002a2e5  mov     rcx, [rbx+40h]
0x18002a2e9  mov     dword ptr [rbx], 1
0x18002a2ef  mov     [rsi+298h], r13d
0x18002a2f6  mov     dword ptr [rbx+38h], 0C0021018h
0x18002a2fd  test    rcx, rcx
0x18002a300  jnz     loc_18002A472
0x18002a306  mov     qword ptr [rbx+20h], 0
0x18002a30e  mov     rcx, rsi; this
0x18002a311  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x18002a316  mov     rcx, [rdi+198h]
0x18002a31d  lea     r8, [rdi+190h]
0x18002a324  mov     [rsp+140h+var_118], rcx; void *
0x18002a329  mov     r9d, r14d; unsigned int
0x18002a32c  mov     [rsp+140h+var_120], r8; struct LPC_NORMALIZED_SID *
0x18002a331  mov     rdx, rbx; struct LRPC_CLIENT_IO *
0x18002a334  mov     r8d, r13d; int
0x18002a337  mov     rcx, rax; this
0x18002a33a  call    ?Connect@LRPC_CASSOCIATION@@QEAAJPEAVLRPC_CLIENT_IO@@HKPEAVLPC_NORMALIZED_SID@@PEAX@Z; LRPC_CASSOCIATION::Connect(LRPC_CLIENT_IO *,int,ulong,LPC_NORMALIZED_SID *,void *)
0x18002a33f  mov     ebx, eax
0x18002a341  test    eax, eax
0x18002a343  jz      loc_18002A00A
0x18002a349  jmp     loc_18002A117
0x18002a34e  test    cs:Microsoft_Windows_RPCEnableBits, 8
0x18002a355  jnz     loc_18002A5C2
0x18002a35b  mov     dword ptr [rdi+18Ch], 8
0x18002a365  test    r13d, r13d; jumptable 000000018002A0D9 case 8
0x18002a368  jnz     short loc_18002A37B
0x18002a36a  mov     rcx, r15; CriticalSection
0x18002a36d  call    cs:__imp_RtlLeaveCriticalSection
0x18002a374  nop     dword ptr [rax+rax+00h]
0x18002a379  jmp     short loc_18002A3A6
0x18002a37b  mov     eax, [rdi+1F0h]
0x18002a381  test    al, 1
0x18002a383  jnz     short loc_18002A36A
0x18002a385  mov     rcx, rdi; this
0x18002a388  call    ?EnableAsyncIfNecessary@LRPC_BASE_BINDING_HANDLE@@QEAAJXZ; LRPC_BASE_BINDING_HANDLE::EnableAsyncIfNecessary(void)
0x18002a38d  mov     rcx, r15; CriticalSection
0x18002a390  mov     ebx, eax
0x18002a392  call    cs:__imp_RtlLeaveCriticalSection
0x18002a399  nop     dword ptr [rax+rax+00h]
0x18002a39e  test    ebx, ebx
0x18002a3a0  jnz     loc_18002A117
0x18002a3a6  lea     r12, [rdi+190h]
0x18002a3ad  mov     dword ptr [rsi+2D0h], 8
0x18002a3b7  mov     dword ptr [rsi+2D4h], 9
0x18002a3c1  cmp     qword ptr [r12], 0
0x18002a3c6  jz      loc_18002A003
0x18002a3cc  lea     r14, [rsi+288h]
0x18002a3d3  mov     rcx, r14; this
0x18002a3d6  test    r13d, r13d
0x18002a3d9  jnz     loc_18002A68D
0x18002a3df  mov     dword ptr [r14], 1
0x18002a3e6  mov     [rsi+298h], r13d
0x18002a3ed  call    ?ReinitCommon@LRPC_CLIENT_IO@@QEAAXXZ; LRPC_CLIENT_IO::ReinitCommon(void)
0x18002a3f2  mov     rcx, rsi; this
0x18002a3f5  call    ?GetAssociation@LRPC_BASE_CCALL@@QEBAPEAVLRPC_CASSOCIATION@@XZ; LRPC_BASE_CCALL::GetAssociation(void)
0x18002a3fa  mov     rdx, [r12]; void *
0x18002a3fe  mov     r13, rax
0x18002a401  lea     r15, [rax+0C0h]
0x18002a408  mov     rcx, [r15]; pSid1
0x18002a40b  test    rcx, rcx
0x18002a40e  jz      loc_18002A517
0x18002a414  call    cs:__imp_EqualSid
0x18002a41b  nop     dword ptr [rax+rax+00h]
0x18002a420  test    eax, eax
0x18002a422  jz      short loc_18002A484
0x18002a424  xor     ebx, ebx
0x18002a426  test    ebx, ebx
0x18002a428  jnz     loc_18002A117
0x18002a42e  mov     r13d, [rsp+140h+var_EC]
0x18002a433  lea     r15, [rdi+130h]
0x18002a43a  mov     r14d, [rsp+140h+var_F0]
0x18002a43f  jmp     loc_18002A003
0x18002a444  cmp     cs:dword_1800FE624, 0; jumptable 000000018002A0D9 case 5
0x18002a44b  jz      loc_18002A2A8
0x18002a451  xor     ecx, ecx
0x18002a453  cmp     ecx, 4
0x18002a456  jnb     loc_18002A29B
0x18002a45c  movsxd  rax, ecx
0x18002a45f  cmp     byte ptr [rax+r12+0E66D8h], 68h ; 'h'
0x18002a468  jz      loc_18002A2A8
0x18002a46e  inc     ecx
0x18002a470  jmp     short loc_18002A453
0x18002a472  call    FreeEEInfoChain
0x18002a477  mov     qword ptr [rbx+40h], 0
0x18002a47f  jmp     loc_18002A306
0x18002a484  mov     eax, [rsp+140h+var_F0]
0x18002a488  mov     r8, r13; struct LRPC_CASSOCIATION *
0x18002a48b  mov     r9d, [rsp+140h+var_EC]; int
0x18002a490  mov     rdx, r12; struct LPC_NORMALIZED_SID *
0x18002a493  mov     dword ptr [rsp+140h+var_118], eax; unsigned int
0x18002a497  mov     rcx, r15; this
0x18002a49a  mov     [rsp+140h+var_120], r14; struct LRPC_CLIENT_IO *
0x18002a49f  call    ?PrepareIterationInternal@LPC_NORMALIZED_SID@@AEAAJPEAV1@PEAVLRPC_CASSOCIATION@@HPEAVLRPC_CLIENT_IO@@K@Z; LPC_NORMALIZED_SID::PrepareIterationInternal(LPC_NORMALIZED_SID *,LRPC_CASSOCIATION *,int,LRPC_CLIENT_IO *,ulong)
0x18002a4a4  mov     ebx, eax
0x18002a4a6  test    eax, eax
0x18002a4a8  jz      loc_18002A7DF
0x18002a4ae  xor     eax, eax
0x18002a4b0  mov     [rsp+140h+var_D0], 3
0x18002a4b8  cmp     [r15], rax
0x18002a4bb  mov     r8d, 488h; unsigned __int16
0x18002a4c1  mov     r9d, 1; int
0x18002a4c7  mov     edx, ebx; int
0x18002a4c9  setnz   al
0x18002a4cc  mov     ecx, 2; unsigned int
0x18002a4d1  mov     [rsp+140h+var_C8], eax
0x18002a4d5  lea     rax, [rsp+140h+var_D0]
0x18002a4da  mov     [rsp+140h+var_120], rax; struct tagParam *
0x18002a4df  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002a4e4  jmp     loc_18002A57F
0x18002a4e9  cmp     cs:dword_1800FE624, 0; jumptable 000000018002A0D9 case 7
0x18002a4f0  jz      loc_18002A35B
0x18002a4f6  xor     ecx, ecx
0x18002a4f8  cmp     ecx, 4
0x18002a4fb  jnb     loc_18002A34E
0x18002a501  movsxd  rax, ecx
0x18002a504  cmp     byte ptr [rax+r12+0E66D8h], 68h ; 'h'
0x18002a50d  jz      loc_18002A35B
0x18002a513  inc     ecx
0x18002a515  jmp     short loc_18002A4F8
  ... truncated ...
```
