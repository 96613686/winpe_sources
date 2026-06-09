# GetWinStationInformation(void *,ulong,_WINSTATIONINFORMATIONW *,ulong,ulong *)

- ea: `0x1800049a0`
- end: `0x18000505a`
- name: `?GetWinStationInformation@@YAJPEAXKPEAU_WINSTATIONINFORMATIONW@@KPEAK@Z`
- size: `1722`
- prototype: `__int64 __usercall@<rax>(CPublicBinding *this@<rcx>, unsigned int@<edx>, struct _WINSTATIONINFORMATIONW *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009dec`

## callees

- `0x180002014`
- `0x1800032b4`
- `0x180003d24`
- `0x180003e78`
- `0x180004558`
- `0x1800045d0`
- `0x1800049a0`
- `0x180005060`
- `0x180005180`
- `0x180005280`
- `0x180005b40`
- `0x1800066d0`
- `0x1800075a0`
- `0x180007690`
- `0x180007fe0`
- `0x180020c90`
- `0x180022bb8`
- `0x180023768`
- `0x1800249e8`
- `0x180024a1c`
- `0x18002e180`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004d11`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004d11`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004cab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004cab`
- `ntdll!NtQuerySystemTime` at `0x180004e27`
- `ntdll!NtQuerySystemTime` at `0x180004e27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004c7c`
- `RPCRT4!RpcBindingFree` at `0x180004cc0`
- `RPCRT4!RpcBindingFree` at `0x180004cd7`
- `RPCRT4!RpcBindingFree` at `0x18000502e`
- `RPCRT4!RpcBindingFree` at `0x18000503f`
- `RPCRT4!RpcBindingFree` at `0x180004cc0`
- `RPCRT4!RpcBindingFree` at `0x180004cd7`
- `RPCRT4!RpcBindingFree` at `0x18000502e`
- `RPCRT4!RpcBindingFree` at `0x18000503f`

## string_xrefs

- `0x180004e58`: `StringCchCopy failed: %x`
- `0x180004c41`: `StringCchCopy failed: 0x%x in %s`
- `0x180004f14`: `Session.Open failed: 0x%x in %s`
- `0x180004fa2`: `GetProtocolStatus failed: 0x%x`
- `0x180005007`: `_GetSessionProtocolLastInputTime`
- `0x180005011`: `GetSessionProtocolLastInputTime failed: 0x%x in %s`
- `0x180005022`: `_GetSessionProtocolLastInputTime failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetWinStationInformation(
        CPublicBinding *this,
        unsigned int a2,
        struct _WINSTATIONINFORMATIONW *a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct _WINSTATIONINFORMATIONW *v5; // r12
  unsigned int v6; // edi
  CPublicBinding *v7; // rbx
  int v9; // r13d
  __int64 v10; // rsi
  CPublicBinding *v11; // rax
  _WORD *v12; // rax
  _WORD *v13; // r9
  __int64 v14; // rcx
  int *v15; // rdx
  __int64 v16; // r10
  _WORD *v17; // rcx
  int v18; // edi
  void *UnifiedRpcBinding; // rax
  _WORD *v20; // rcx
  _WORD *v21; // r8
  __int64 v22; // rdx
  BYTE *v23; // r10
  __int64 v24; // r9
  BYTE *v25; // rcx
  unsigned int ProtocolStatus; // edi
  __int64 v27; // rdx
  BYTE *v28; // r9
  BYTE *v29; // rcx
  const char *v30; // rdx
  void *v31; // rcx
  void *v32; // rcx
  int State; // eax
  int Times; // eax
  union _LARGE_INTEGER *v36; // rsi
  LONGLONG v37; // r15
  struct _PROTOCOLSTATUS *v38; // r14
  unsigned int v39; // r12d
  int SessionProtocolLastInputTime; // eax
  void *v41; // rax
  int v42; // eax
  struct _PROTOCOLSTATUS *v43; // r8
  void *v44; // r14
  int LastInputTime; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v49; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v50[4]; // [rsp+40h] [rbp-C0h] BYREF
  CPublicBinding *v51; // [rsp+48h] [rbp-B8h]
  void *v52; // [rsp+50h] [rbp-B0h]
  unsigned int *v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+68h] [rbp-98h]
  __int128 v56; // [rsp+70h] [rbp-90h]
  __int128 v57; // [rsp+80h] [rbp-80h]
  __int128 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+A0h] [rbp-60h]
  char v60[208]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+178h] [rbp+78h]

  v53 = a5;
  v5 = a3;
  v6 = a2;
  v52 = this;
  v7 = this;
  v59 = 0;
  hMem = 0;
  v49 = 0;
  v54 = 0;
  v55 = -1;
  v61 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  memset_0(v60, 0, sizeof(v60));
  *(_QWORD *)v50 = 0;
  v9 = 0;
  v10 = 2147483646;
  if ( v7 )
  {
LABEL_15:
    v51 = v7;
    goto LABEL_16;
  }
  v11 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    v9 = 1;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 5) = 0;
    *((_QWORD *)v11 + 6) = 1;
    *((_QWORD *)v11 + 7) = 0;
    v12 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)v7 + 5) = v12;
    v13 = v12;
    if ( v12 )
    {
      v14 = 2147483646;
      v15 = &dword_18003FF34;
      v16 = 1;
      do
      {
        if ( !v14 )
          break;
        if ( !*(_WORD *)v15 )
          break;
        *v13 = *(_WORD *)v15;
        v15 = (int *)((char *)v15 + 2);
        ++v13;
        --v14;
        --v16;
      }
      while ( v16 );
      v17 = v13 - 1;
      v18 = -2147024774;
      if ( v16 )
      {
        v17 = v13;
        v18 = 0;
      }
      *v17 = 0;
      if ( v16 )
      {
        if ( !*((_QWORD *)v7 + 3) && !*((_DWORD *)v7 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle(v7) == -2147023174 )
            *((_DWORD *)v7 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle(v7);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v18);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v18);
      }
      v6 = a2;
    }
    *(_DWORD *)&v50[2] = 1;
    goto LABEL_15;
  }
  v7 = 0;
  v51 = 0;
  SetLastError(0xEu);
  _DbgPrintMessage(8, "new CPublicBinding");
LABEL_16:
  if ( a4 >= 0x4C0 )
  {
    memset_0(v5, 0, sizeof(struct _WINSTATIONINFORMATIONW));
    if ( v7 )
    {
      if ( *((_QWORD *)v7 + 3) )
        UnifiedRpcBinding = CPublicBinding::GetUnifiedRpcBinding(v7);
      else
        UnifiedRpcBinding = CPublicBinding::GetLSMBinding((RPC_BINDING_HANDLE *)v7);
    }
    else
    {
      UnifiedRpcBinding = 0;
    }
    if ( (int)CSmartSession::GetSessionInformation((CSmartSession *)&v54, v6, UnifiedRpcBinding) < 0 )
    {
      v41 = (void *)CSmartPublicBinding::operator void *(v50);
      v42 = CSmartSession::Open((CSmartSession *)&v54, v6, v41);
      ProtocolStatus = v42;
      if ( v42 < 0 )
      {
        _DbgPrintMessage(8, "Session.Open failed: 0x%x in %s", v42, "GetWinStationInformation");
        goto LABEL_40;
      }
    }
    if ( (int)CSmartSession::GetUserNameW((CSmartSession *)&v54, (unsigned __int16 **)&hMem, (unsigned __int16 **)&v49) >= 0
      && (v20 = hMem) != 0
      && (v21 = v49) != 0 )
    {
      v22 = 2147483646;
      v23 = &v5->Reserved3[1084];
      v24 = 21;
      do
      {
        if ( !v22 )
          break;
        if ( !*v20 )
          break;
        *(_WORD *)v23 = *v20++;
        v23 += 2;
        --v22;
        --v24;
      }
      while ( v24 );
      v25 = v23 - 2;
      ProtocolStatus = -2147024774;
      if ( v24 )
      {
        v25 = v23;
        ProtocolStatus = 0;
      }
      *(_WORD *)v25 = 0;
      if ( !v24 )
        goto LABEL_38;
      v27 = 18;
      v28 = &v5->Reserved3[1048];
      do
      {
        if ( !v10 )
          break;
        if ( !*v21 )
          break;
        *(_WORD *)v28 = *v21++;
        v28 += 2;
        --v10;
        --v27;
      }
      while ( v27 );
      v29 = v28 - 2;
      ProtocolStatus = -2147024774;
      if ( v27 )
      {
        v29 = v28;
        ProtocolStatus = 0;
      }
      *(_WORD *)v29 = 0;
      if ( !v27 )
      {
LABEL_38:
        v30 = "StringCchCopy failed: 0x%x in %s";
LABEL_39:
        _DbgPrintMessage(8, v30, ProtocolStatus, "GetWinStationInformation", a2);
        goto LABEL_40;
      }
    }
    else
    {
      *(_WORD *)&v5->Reserved3[1084] = 0;
      *(_WORD *)&v5->Reserved3[1048] = 0;
    }
    State = CSmartSession::GetState((CSmartSession *)&v54, (int *)v5);
    ProtocolStatus = State;
    if ( State < 0 )
    {
      _DbgPrintMessage(8, "GetState failed: 0x%x in %s", (unsigned int)State, "GetWinStationInformation");
      goto LABEL_40;
    }
    if ( (int)CSmartSession::GetTerminalName((CSmartSession *)&v54, (unsigned __int16 *)&v5->Reserved2[4]) < 0 )
      *(_WORD *)&v5->Reserved2[4] = 0;
    Times = CSmartSession::GetTimes(
              (CSmartSession *)&v54,
              (union _LARGE_INTEGER *)&v5->Reserved3[4],
              (union _LARGE_INTEGER *)&v5->Reserved3[12],
              (union _LARGE_INTEGER *)&v5->Reserved3[28]);
    ProtocolStatus = Times;
    if ( Times < 0 )
    {
      _DbgPrintMessage(8, "GetTimes failed: 0x%x in %s", (unsigned int)Times, "GetWinStationInformation");
      goto LABEL_40;
    }
    v36 = (union _LARGE_INTEGER *)&v5->Reserved3[20];
    v37 = *(_QWORD *)&v5->Reserved3[12];
    v38 = (struct _PROTOCOLSTATUS *)&v5->Reserved3[36];
    if ( *(_DWORD *)v5->Reserved2 != 4 )
    {
      v39 = v55;
      SessionProtocolLastInputTime = GetSessionProtocolLastInputTime(v52, v55, v38, v36);
      ProtocolStatus = SessionProtocolLastInputTime;
      if ( SessionProtocolLastInputTime == -2147023151 )
      {
        v43 = v38;
        v44 = v52;
        ProtocolStatus = GetProtocolStatus(v52, v39, v43);
        if ( (int)(ProtocolStatus + 0x80000000) < 0 || ProtocolStatus == -2147467262 )
        {
          LastInputTime = GetLastInputTime(v44, v39, v36);
          ProtocolStatus = LastInputTime;
          if ( LastInputTime >= 0 )
            goto LABEL_80;
          if ( LastInputTime == -2147467262
            || LastInputTime == -2147022646
            || LastInputTime == -2147023174
            || LastInputTime == -2147023179 )
          {
            v36->QuadPart = v37;
            goto LABEL_80;
          }
          _DbgPrintMessage(8, "GetLastInputTime failed: 0x%x", LastInputTime);
        }
        else
        {
          _DbgPrintMessage(8, "GetProtocolStatus failed: 0x%x", ProtocolStatus);
        }
        goto LABEL_99;
      }
      if ( SessionProtocolLastInputTime != -2147467262
        && SessionProtocolLastInputTime != -2147022646
        && SessionProtocolLastInputTime != -2147023174
        && SessionProtocolLastInputTime != -2147023179 )
      {
        if ( SessionProtocolLastInputTime >= 0 )
        {
LABEL_80:
          v5 = a3;
          goto LABEL_71;
        }
        _DbgPrintMessage(
          8,
          "GetSessionProtocolLastInputTime failed: 0x%x in %s",
          SessionProtocolLastInputTime,
          "_GetSessionProtocolLastInputTime");
LABEL_99:
        v30 = "_GetSessionProtocolLastInputTime failed: 0x%x in %s";
        goto LABEL_39;
      }
      v5 = a3;
    }
    memset_0(v38, 0, 0x3F4u);
    v36->QuadPart = v37;
LABEL_71:
    NtQuerySystemTime((PLARGE_INTEGER)&v5->Reserved3[1132]);
    ProtocolStatus = 0;
    v5->LogonId = a2;
    *v53 = 1216;
    goto LABEL_40;
  }
  ProtocolStatus = -2147024809;
LABEL_40:
  if ( hMem )
    LocalFree(hMem);
  if ( v49 )
    LocalFree(v49);
  if ( v9 && v7 )
  {
    CPublicBinding::CloseSessionContextHandle(v7);
    v31 = (void *)*((_QWORD *)v7 + 5);
    if ( v31 )
      operator delete[](v31);
    if ( *(_QWORD *)v7 )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7);
    if ( *((_QWORD *)v7 + 1) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 1);
    if ( *((_QWORD *)v7 + 2) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 2);
    if ( *((_QWORD *)v7 + 3) )
      RpcBindingFree((RPC_BINDING_HANDLE *)v7 + 3);
    v32 = (void *)*((_QWORD *)v7 + 4);
    if ( v32 )
      Legacy_WinStationCloseServer(v32);
    operator delete(v7);
  }
  CSmartSession::~CSmartSession((CSmartSession *)&v54);
  return ProtocolStatus;
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp-8+arg_18], rbx
0x1800049a5  push    rbp
0x1800049a6  push    rsi
0x1800049a7  push    rdi
0x1800049a8  push    r12
0x1800049aa  push    r13
0x1800049ac  push    r14
0x1800049ae  push    r15
0x1800049b0  lea     rbp, [rsp-90h]
0x1800049b8  sub     rsp, 190h
0x1800049bf  mov     rax, cs:__security_cookie
0x1800049c6  xor     rax, rsp
0x1800049c9  mov     [rbp+0C0h+var_40], rax
0x1800049d0  mov     rax, [rbp+0C0h+arg_20]
0x1800049d7  xor     r15d, r15d
0x1800049da  xorps   xmm0, xmm0
0x1800049dd  mov     [rsp+1C0h+var_168], rax
0x1800049e2  xor     eax, eax
0x1800049e4  mov     [rsp+1C0h+var_198], r8
0x1800049e9  mov     r12, r8
0x1800049ec  mov     [rsp+1C0h+var_1A0], edx
0x1800049f0  mov     edi, edx
0x1800049f2  mov     [rsp+1C0h+var_170], rcx
0x1800049f7  mov     rbx, rcx
0x1800049fa  mov     [rbp+0C0h+var_120], rax
0x1800049fe  xor     edx, edx; Val
0x180004a00  mov     [rsp+1C0h+hMem], r15
0x180004a05  mov     r8d, 0D0h; Size
0x180004a0b  mov     [rsp+1C0h+var_188], r15
0x180004a10  lea     rcx, [rbp+0C0h+var_118]; void *
0x180004a14  mov     [rsp+1C0h+var_160], r15
0x180004a19  mov     r14d, r9d
0x180004a1c  mov     [rsp+1C0h+var_158], 0FFFFFFFFh
0x180004a24  mov     [rbp+0C0h+var_48], r15
0x180004a28  movups  [rsp+1C0h+var_150], xmm0
0x180004a2d  movups  [rbp+0C0h+var_140], xmm0
0x180004a31  movups  [rbp+0C0h+var_130], xmm0
0x180004a35  call    memset_0
0x180004a3a  mov     qword ptr [rsp+1C0h+var_180], r15
0x180004a3f  mov     r13d, r15d
0x180004a42  mov     esi, 7FFFFFFEh
0x180004a47  test    rbx, rbx
0x180004a4a  jnz     loc_180004B18
0x180004a50  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a57  mov     ecx, 40h ; '@'; unsigned __int64
0x180004a5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004a61  mov     rbx, rax
0x180004a64  test    rax, rax
0x180004a67  jz      loc_180004F33
0x180004a6d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a74  mov     [rax], r15
0x180004a77  mov     ecx, 2; unsigned __int64
0x180004a7c  mov     [rax+8], r15
0x180004a80  mov     [rax+10h], r15
0x180004a84  mov     r13d, 1
0x180004a8a  mov     [rax+18h], r15
0x180004a8e  mov     [rax+20h], r15
0x180004a92  mov     [rax+28h], r15
0x180004a96  mov     qword ptr [rax+30h], 1
0x180004a9e  mov     [rax+38h], r15
0x180004aa2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004aa7  mov     [rbx+28h], rax
0x180004aab  mov     r9, rax
0x180004aae  test    rax, rax
0x180004ab1  jz      short loc_180004B13
0x180004ab3  mov     ecx, esi
0x180004ab5  lea     rdx, dword_18003FF34
0x180004abc  mov     r10d, r13d
0x180004abf  nop
0x180004ac0  test    rcx, rcx
0x180004ac3  jz      short loc_180004AE1
0x180004ac5  movzx   eax, word ptr [rdx]
0x180004ac8  test    ax, ax
0x180004acb  jz      short loc_180004AE1
0x180004acd  mov     [r9], ax
0x180004ad1  add     rdx, 2
0x180004ad5  add     r9, 2
0x180004ad9  dec     rcx
0x180004adc  sub     r10, r13
0x180004adf  jnz     short loc_180004AC0
0x180004ae1  test    r10, r10
0x180004ae4  lea     rcx, [r9-2]
0x180004ae8  mov     edi, 8007007Ah
0x180004aed  cmovnz  rcx, r9
0x180004af1  cmovnz  edi, r15d
0x180004af5  mov     [rcx], r15w
0x180004af9  jz      loc_180004E4E
0x180004aff  cmp     [rbx+18h], r15
0x180004b03  jnz     short loc_180004B0F
0x180004b05  cmp     [rbx+30h], r15d
0x180004b09  jz      loc_180004E6E
0x180004b0f  mov     edi, [rsp+1C0h+var_1A0]
0x180004b13  mov     dword ptr [rsp+1C0h+var_180+4], r13d
0x180004b18  mov     [rsp+1C0h+var_178], rbx
0x180004b1d  cmp     r14d, 4C0h
0x180004b24  jb      loc_180004F62
0x180004b2a  xor     edx, edx; Val
0x180004b2c  mov     r8d, 4C0h; Size
0x180004b32  mov     rcx, r12; void *
0x180004b35  call    memset_0
0x180004b3a  test    rbx, rbx
0x180004b3d  jz      loc_180004EDF
0x180004b43  mov     rcx, rbx; Binding
0x180004b46  cmp     [rbx+18h], r15
0x180004b4a  jz      loc_180004D54
0x180004b50  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180004b55  mov     r8, rax; void *
0x180004b58  lea     rcx, [rsp+1C0h+var_160]; this
0x180004b5d  mov     edx, edi; unsigned int
0x180004b5f  call    ?GetSessionInformation@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::GetSessionInformation(ulong,void *)
0x180004b64  test    eax, eax
0x180004b66  js      loc_180004EE7
0x180004b6c  lea     r8, [rsp+1C0h+var_188]; unsigned __int16 **
0x180004b71  lea     rdx, [rsp+1C0h+hMem]; unsigned __int16 **
0x180004b76  lea     rcx, [rsp+1C0h+var_160]; this
0x180004b7b  call    ?GetUserNameW@CSmartSession@@QEAAJPEAPEAG0@Z; CSmartSession::GetUserNameW(ushort * *,ushort * *)
0x180004b80  test    eax, eax
0x180004b82  js      loc_180004D5E
0x180004b88  mov     rcx, [rsp+1C0h+hMem]
0x180004b8d  test    rcx, rcx
0x180004b90  jz      loc_180004D5E
0x180004b96  mov     r8, [rsp+1C0h+var_188]
0x180004b9b  test    r8, r8
0x180004b9e  jz      loc_180004D5E
0x180004ba4  mov     rdx, rsi
0x180004ba7  lea     r10, [r12+488h]
0x180004baf  mov     r9d, 15h
0x180004bb5  test    rdx, rdx
0x180004bb8  jz      short loc_180004BD7
0x180004bba  movzx   eax, word ptr [rcx]
0x180004bbd  test    ax, ax
0x180004bc0  jz      short loc_180004BD7
0x180004bc2  mov     [r10], ax
0x180004bc6  add     rcx, 2
0x180004bca  add     r10, 2
0x180004bce  dec     rdx
0x180004bd1  sub     r9, 1
0x180004bd5  jnz     short loc_180004BB5
0x180004bd7  test    r9, r9
0x180004bda  lea     rcx, [r10-2]
0x180004bde  mov     edi, 8007007Ah
0x180004be3  cmovnz  rcx, r10
0x180004be7  cmovnz  edi, r15d
0x180004beb  mov     [rcx], r15w
0x180004bef  jz      short loc_180004C41
0x180004bf1  mov     edx, 12h
0x180004bf6  lea     r9, [r12+464h]
0x180004bfe  xchg    ax, ax
0x180004c00  test    rsi, rsi
0x180004c03  jz      short loc_180004C23
0x180004c05  movzx   eax, word ptr [r8]
0x180004c09  test    ax, ax
0x180004c0c  jz      short loc_180004C23
0x180004c0e  mov     [r9], ax
0x180004c12  add     r8, 2
0x180004c16  add     r9, 2
0x180004c1a  dec     rsi
0x180004c1d  sub     rdx, 1
0x180004c21  jnz     short loc_180004C00
0x180004c23  test    rdx, rdx
0x180004c26  lea     rcx, [r9-2]
0x180004c2a  mov     edi, 8007007Ah
0x180004c2f  cmovnz  rcx, r9
0x180004c33  cmovnz  edi, r15d
0x180004c37  mov     [rcx], r15w
0x180004c3b  jnz     loc_180004D70
0x180004c41  lea     rdx, aStringcchcopyF_0; "StringCchCopy failed: 0x%x in %s"
0x180004c48  mov     r8d, edi
0x180004c4b  lea     r9, aGetwinstationi; "GetWinStationInformation"
0x180004c52  mov     ecx, 8; int
0x180004c57  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004c5c  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180004c61  test    rcx, rcx
0x180004c64  jz      short loc_180004C72
0x180004c66  call    cs:__imp_LocalFree
0x180004c6d  nop     dword ptr [rax+rax+00h]
0x180004c72  mov     rcx, [rsp+1C0h+var_188]; hMem
0x180004c77  test    rcx, rcx
0x180004c7a  jz      short loc_180004C88
0x180004c7c  call    cs:__imp_LocalFree
0x180004c83  nop     dword ptr [rax+rax+00h]
0x180004c88  test    r13d, r13d
0x180004c8b  jz      loc_180004D1D
0x180004c91  test    rbx, rbx
0x180004c94  jz      loc_180004D1D
0x180004c9a  mov     rcx, rbx; this
0x180004c9d  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180004ca2  mov     rcx, [rbx+28h]
0x180004ca6  test    rcx, rcx
0x180004ca9  jz      short loc_180004CB7
0x180004cab  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004cb2  nop     dword ptr [rax+rax+00h]
0x180004cb7  cmp     qword ptr [rbx], 0
0x180004cbb  jz      short loc_180004CCC
0x180004cbd  mov     rcx, rbx; Binding
0x180004cc0  call    cs:__imp_RpcBindingFree
0x180004cc7  nop     dword ptr [rax+rax+00h]
0x180004ccc  cmp     qword ptr [rbx+8], 0
0x180004cd1  lea     rcx, [rbx+8]; Binding
0x180004cd5  jz      short loc_180004CE3
0x180004cd7  call    cs:__imp_RpcBindingFree
0x180004cde  nop     dword ptr [rax+rax+00h]
0x180004ce3  cmp     qword ptr [rbx+10h], 0
0x180004ce8  lea     rcx, [rbx+10h]; Binding
0x180004cec  jnz     loc_18000502E
0x180004cf2  cmp     qword ptr [rbx+18h], 0
0x180004cf7  lea     rcx, [rbx+18h]; Binding
0x180004cfb  jnz     loc_18000503F
0x180004d01  mov     rcx, [rbx+20h]; void *
0x180004d05  test    rcx, rcx
0x180004d08  jnz     loc_180005050
0x180004d0e  mov     rcx, rbx
0x180004d11  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004d18  nop     dword ptr [rax+rax+00h]
0x180004d1d  lea     rcx, [rsp+1C0h+var_160]; this
0x180004d22  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180004d27  mov     eax, edi
0x180004d29  mov     rcx, [rbp+0C0h+var_40]
0x180004d30  xor     rcx, rsp; StackCookie
0x180004d33  call    __security_check_cookie
0x180004d38  mov     rbx, [rsp+1C0h+arg_18]
0x180004d40  add     rsp, 190h
0x180004d47  pop     r15
0x180004d49  pop     r14
0x180004d4b  pop     r13
0x180004d4d  pop     r12
0x180004d4f  pop     rdi
0x180004d50  pop     rsi
0x180004d51  pop     rbp
0x180004d52  retn
0x180004d54  call    ?GetLSMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetLSMBinding(void)
0x180004d59  jmp     loc_180004B55
0x180004d5e  mov     [r12+488h], r15w
0x180004d67  mov     [r12+464h], r15w
0x180004d70  mov     rdx, r12; int *
0x180004d73  lea     rcx, [rsp+1C0h+var_160]; this
0x180004d78  call    ?GetState@CSmartSession@@QEAAJPEAJ@Z; CSmartSession::GetState(long *)
0x180004d7d  mov     edi, eax
0x180004d7f  test    eax, eax
0x180004d81  js      loc_180004ED0
0x180004d87  lea     rdx, [r12+4]; unsigned __int16 *
0x180004d8c  lea     rcx, [rsp+1C0h+var_160]; this
0x180004d91  call    ?GetTerminalName@CSmartSession@@QEAAJPEAG@Z; CSmartSession::GetTerminalName(ushort *)
0x180004d96  test    eax, eax
0x180004d98  js      loc_180004F6C
0x180004d9e  lea     r9, [r12+68h]; union _LARGE_INTEGER *
0x180004da3  lea     rdx, [r12+50h]; union _LARGE_INTEGER *
0x180004da8  lea     r8, [r12+58h]; union _LARGE_INTEGER *
0x180004dad  lea     rcx, [rsp+1C0h+var_160]; this
0x180004db2  call    ?GetTimes@CSmartSession@@QEAAJPEAT_LARGE_INTEGER@@00@Z; CSmartSession::GetTimes(_LARGE_INTEGER *,_LARGE_INTEGER *,_LARGE_INTEGER *)
0x180004db7  mov     edi, eax
0x180004db9  test    eax, eax
0x180004dbb  js      loc_180004EC1
0x180004dc1  cmp     dword ptr [r12], 4
0x180004dc6  lea     rsi, [r12+60h]
0x180004dcb  mov     r15, [r12+58h]
0x180004dd0  lea     r14, [r12+70h]
0x180004dd5  jz      short loc_180004E0C
0x180004dd7  mov     r12d, [rsp+1C0h+var_158]
0x180004ddc  mov     r9, rsi; union _LARGE_INTEGER *
0x180004ddf  mov     rcx, [rsp+1C0h+var_170]; void *
0x180004de4  mov     edx, r12d; unsigned int
0x180004de7  mov     r8, r14; struct _PROTOCOLSTATUS *
0x180004dea  call    ?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z; GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)
0x180004def  mov     edi, eax
0x180004df1  cmp     eax, 800706D1h
0x180004df6  jz      loc_180004F77
0x180004dfc  cmp     eax, 80004002h
0x180004e01  jnz     loc_180004E8E
0x180004e07  mov     r12, [rsp+1C0h+var_198]
0x180004e0c  xor     edx, edx; Val
0x180004e0e  mov     r8d, 3F4h; Size
0x180004e14  mov     rcx, r14; void *
0x180004e17  call    memset_0
0x180004e1c  mov     [rsi], r15
0x180004e1f  lea     rcx, [r12+4B8h]; SystemTime
0x180004e27  call    cs:__imp_NtQuerySystemTime
0x180004e2e  nop     dword ptr [rax+rax+00h]
0x180004e33  mov     eax, [rsp+1C0h+var_1A0]
0x180004e37  xor     edi, edi
0x180004e39  mov     [r12+48h], eax
0x180004e3e  mov     rax, [rsp+1C0h+var_168]
0x180004e43  mov     dword ptr [rax], 4C0h
0x180004e49  jmp     loc_180004C5C
0x180004e4e  mov     ecx, edi; int
0x180004e50  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180004e55  mov     r8d, edi
0x180004e58  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180004e5f  mov     ecx, 8; int
0x180004e64  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004e69  jmp     loc_180004B0F
0x180004e6e  mov     rcx, rbx; this
0x180004e71  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180004e76  cmp     eax, 800706BAh
0x180004e7b  jz      loc_180004F2A
0x180004e81  mov     rcx, rbx; this
0x180004e84  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180004e89  jmp     loc_180004B0F
0x180004e8e  cmp     eax, 800708CAh
0x180004e93  jz      loc_180004E07
  ... truncated ...
```
