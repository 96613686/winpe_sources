# WinBioSrvOpenBiometricSession

- ea: `0x18004e090`
- end: `0x18004e51f`
- name: `WinBioSrvOpenBiometricSession`
- size: `1167`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int *, struct _GUID *, int, void **, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180023d88`
- `0x180026b28`
- `0x180027438`
- `0x18002d3b4`
- `0x180031c30`
- `0x180045ed0`
- `0x18004e090`
- `0x180055878`
- `0x1800559c8`
- `0x180068f60`
- `0x18006a20c`
- `0x180099400`
- `0x180099640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e46b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e46b`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004e3a4`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004e3a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e449`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e449`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e461`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e2ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e2ab`
- `RPCRT4!RpcRevertToSelfEx` at `0x18004e484`
- `RPCRT4!RpcRevertToSelfEx` at `0x18004e484`
- `RPCRT4!RpcImpersonateClient` at `0x18004e434`
- `RPCRT4!RpcImpersonateClient` at `0x18004e434`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18004e3c2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18004e3c2`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x18004e301`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x18004e301`

## string_xrefs

- `0x18004e0ca`: `WinBioSrvOpenBiometricSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinBioSrvOpenBiometricSession(
        void *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        struct _GUID *a7,
        int a8,
        void **a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11)
{
  unsigned __int64 *v12; // rbx
  int v15; // r9d
  unsigned int v16; // ebx
  struct _GUID *v17; // rbx
  unsigned int v18; // esi
  unsigned int v19; // edi
  unsigned __int64 *v20; // rax
  __int64 v22; // rcx
  unsigned int v23; // r8d
  int v24; // edx
  RPC_BINDING_HANDLE v25; // rbx
  RPC_STATUS v26; // eax
  unsigned int v27; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  RPC_STATUS v30; // eax
  signed int v31; // eax
  signed int RpcClientPid; // [rsp+70h] [rbp-90h] BYREF
  DWORD pSessionId; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD dwProcessId; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v35; // [rsp+7Ch] [rbp-84h] BYREF
  int v36; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 *v37; // [rsp+88h] [rbp-78h]
  unsigned int v38; // [rsp+90h] [rbp-70h]
  HANDLE hObject; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID *v40; // [rsp+A0h] [rbp-60h]
  void *v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v43; // [rsp+B8h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE BindingHandle; // [rsp+C0h] [rbp-40h]
  _QWORD *v45; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v46[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v47[96]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v48[528]; // [rsp+150h] [rbp+50h] BYREF
  char v49[32]; // [rsp+360h] [rbp+260h] BYREF

  v12 = a11;
  v40 = a7;
  v46[0] = v49;
  v46[1] = &v36;
  BindingHandle = a1;
  strcpy(v49, "WinBioSrvOpenBiometricSession");
  v46[2] = &RpcClientPid;
  v35 = a2;
  v37 = a11;
  RpcClientPid = 0;
  v36 = 0;
  lambda_018bb5ef1578d90ec3f7529241e6b868_::operator()(v46);
  v36 = 1;
  v45 = v46;
  hObject = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  dwProcessId = 0;
  pSessionId = 0;
  BioPolicy::Refresh((BioPolicy *)v47);
  if ( !v47[8 * (int)BioPolicy::Values::make_index(1)] )
  {
    CEtwEvent::CEtwEvent((CEtwEvent *)v48);
    CEtwEvent::Write(v48, 1020, 1);
    v16 = -2146861006;
    RpcClientPid = -2146861006;
    CEtwEvent::~CEtwEvent((CEtwEvent *)v48);
    goto LABEL_24;
  }
  if ( !a1 )
  {
    RpcClientPid = -2147024890;
LABEL_18:
    if ( (unsigned int)dword_18010F170 > 3 )
    {
      v35 = RpcClientPid;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F170,
        (unsigned int)byte_1800F00FB,
        0,
        v15,
        (__int64)&v35);
    }
    v20 = v37;
    *a9 = 0;
    *a10 = 0;
    *v20 = 0;
    goto LABEL_21;
  }
  v38 = (unsigned __int16)a4;
  if ( (a4 & 0xFFFC) != 0 )
    goto LABEL_17;
  if ( a9 && a10 && a11 )
  {
    v17 = (struct _GUID *)&qword_1800E46D0;
    v18 = HIWORD(a4);
    if ( v40 )
      v17 = v40;
    if ( a3 != 1 )
    {
      if ( a3 == 2 )
      {
        if ( !(unsigned __int8)IsWinBioIsLegacyPresent() || !(unsigned int)WinBioIsLegacy() )
        {
          RpcClientPid = -2146860984;
          goto LABEL_18;
        }
        if ( v18 - 1 <= 1 )
        {
          v19 = a5;
          if ( a5 )
          {
            if ( !a6 )
            {
              RpcClientPid = -2147467261;
              goto LABEL_18;
            }
            if ( *(_QWORD *)&v17->Data1 || *(_QWORD *)v17->Data4 != 0x100000000000000LL )
            {
              v22 = 0;
LABEL_35:
              v23 = a6[v22];
              if ( v23 )
              {
                v24 = v22;
                while ( v23 != a6[v24] || (_DWORD)v22 == v24 )
                {
                  if ( ++v24 >= a5 )
                  {
                    v22 = (unsigned int)(v22 + 1);
                    if ( (unsigned int)v22 < a5 )
                      goto LABEL_35;
                    goto LABEL_41;
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_17;
    }
    if ( v18 || (v19 = a5) != 0 || a6 || *(_QWORD *)&v17->Data1 || *(_QWORD *)v17->Data4 != 0x100000000000000LL )
    {
LABEL_17:
      RpcClientPid = -2147024809;
      goto LABEL_18;
    }
LABEL_41:
    RpcClientPid = GetRpcClientPid(&dwProcessId);
    if ( RpcClientPid >= 0 )
    {
      if ( !ProcessIdToSessionId(dwProcessId, &pSessionId) )
      {
        RpcClientPid = -2147024891;
        goto LABEL_18;
      }
      if ( !pSessionId || pSessionId == WTSGetActiveConsoleSessionId() || a3 == 2 )
      {
        v25 = BindingHandle;
        v26 = RpcImpersonateClient(BindingHandle);
        if ( v26 )
        {
          v27 = v26 | 0x80010000;
        }
        else
        {
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &hObject) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RpcClientPid = LastError;
          }
          v30 = RpcRevertToSelfEx(v25);
          if ( v30 )
          {
            v31 = v30 | 0x80010000;
            RpcClientPid = v31;
          }
          else
          {
            v31 = RpcClientPid;
          }
          if ( v31 < 0 )
            goto LABEL_18;
          v27 = CServer::OpenBiometricSession(
                  dwProcessId,
                  hObject,
                  v35,
                  a3,
                  v18,
                  v38,
                  v19,
                  a6,
                  v40,
                  a8 != 0,
                  &v41,
                  &v42,
                  &v43);
        }
        RpcClientPid = v27;
      }
      else
      {
        CEtwEvent::CEtwEvent((CEtwEvent *)v48);
        CEtwEvent::Write(v48, 1021, 1);
        RpcClientPid = -2146861000;
        CEtwEvent::~CEtwEvent((CEtwEvent *)v48);
      }
    }
    v12 = v37;
  }
  else
  {
    RpcClientPid = -2147467261;
  }
  if ( RpcClientPid < 0 )
    goto LABEL_18;
  *a9 = v41;
  *a10 = v42;
  *v12 = v43;
LABEL_21:
  if ( hObject )
    CloseHandle(hObject);
  v16 = RpcClientPid;
LABEL_24:
  WppTraceUnwinder__lambda_018bb5ef1578d90ec3f7529241e6b868____::_WppTraceUnwinder__lambda_018bb5ef1578d90ec3f7529241e6b868____(&v45);
  return v16;
}

```

## disassembly

```asm
0x18004e090  mov     [rsp-8+arg_18], rbx
0x18004e095  push    rbp
0x18004e096  push    rsi
0x18004e097  push    rdi
0x18004e098  push    r12
0x18004e09a  push    r13
0x18004e09c  push    r14
0x18004e09e  push    r15
0x18004e0a0  lea     rbp, [rsp-290h]
0x18004e0a8  sub     rsp, 390h
0x18004e0af  mov     rax, cs:__security_cookie
0x18004e0b6  xor     rax, rsp
0x18004e0b9  mov     [rbp+2C0h+var_40], rax
0x18004e0c0  mov     rax, [rbp+2C0h+arg_30]
0x18004e0c7  mov     rdi, rcx
0x18004e0ca  movups  xmm0, xmmword ptr cs:aWinbiosrvopenb; "WinBioSrvOpenBiometricSession"
0x18004e0d1  mov     rbx, [rbp+2C0h+arg_50]
0x18004e0d8  mov     esi, r9d
0x18004e0db  movups  xmm1, xmmword ptr cs:aWinbiosrvopenb+0Eh; "iometricSession"
0x18004e0e2  mov     r14, [rbp+2C0h+arg_28]
0x18004e0e9  mov     r15d, r8d
0x18004e0ec  mov     r12, [rbp+2C0h+arg_40]
0x18004e0f3  mov     r13, [rbp+2C0h+arg_48]
0x18004e0fa  mov     [rbp+2C0h+var_320], rax
0x18004e0fe  lea     rax, [rbp+2C0h+var_60]
0x18004e105  mov     [rbp+2C0h+var_2F0], rax
0x18004e109  lea     rax, [rbp+2C0h+var_340]
0x18004e10d  mov     [rbp+2C0h+var_2E8], rax
0x18004e111  lea     rax, [rsp+3C0h+var_350]
0x18004e116  mov     [rbp+2C0h+BindingHandle], rcx
0x18004e11a  lea     rcx, [rbp+2C0h+var_2F0]
0x18004e11e  movups  xmmword ptr [rbp+2C0h+var_60], xmm0
0x18004e125  mov     [rbp+2C0h+var_2E0], rax
0x18004e129  mov     [rsp+3C0h+var_344], edx
0x18004e12d  mov     [rbp+2C0h+var_338], rbx
0x18004e131  mov     [rsp+3C0h+var_350], 0
0x18004e139  mov     [rbp+2C0h+var_340], 0
0x18004e140  movups  xmmword ptr [rbp+2C0h+var_60+0Eh], xmm1
0x18004e147  call    _lambda_018bb5ef1578d90ec3f7529241e6b868___operator__
0x18004e14c  lea     rax, [rbp+2C0h+var_2F0]
0x18004e150  mov     [rbp+2C0h+var_340], 1
0x18004e157  mov     [rbp+2C0h+var_2F8], rax
0x18004e15b  lea     rcx, [rbp+2C0h+var_2D0]; this
0x18004e15f  xor     eax, eax
0x18004e161  mov     [rbp+2C0h+hObject], rax
0x18004e165  mov     [rbp+2C0h+var_318], rax
0x18004e169  mov     [rbp+2C0h+var_310], rax
0x18004e16d  mov     [rbp+2C0h+var_308], rax
0x18004e171  mov     [rsp+3C0h+dwProcessId], eax
0x18004e175  mov     [rsp+3C0h+pSessionId], eax
0x18004e179  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x18004e17e  mov     ecx, 1
0x18004e183  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x18004e188  movsxd  rcx, eax
0x18004e18b  cmp     [rbp+rcx*8+2C0h+var_2D0], 0
0x18004e190  jnz     short loc_18004E1C6
0x18004e192  lea     rcx, [rbp+2C0h+var_270]; this
0x18004e196  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004e19b  mov     edx, 3FCh
0x18004e1a0  lea     rcx, [rbp+2C0h+var_270]
0x18004e1a4  mov     r8d, 1
0x18004e1aa  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004e1af  mov     ebx, 80098032h
0x18004e1b4  lea     rcx, [rbp+2C0h+var_270]; this
0x18004e1b8  mov     [rsp+3C0h+var_350], ebx
0x18004e1bc  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18004e1c1  jmp     loc_18004E2B5
0x18004e1c6  test    rdi, rdi
0x18004e1c9  jnz     short loc_18004E1D5
0x18004e1cb  mov     [rsp+3C0h+var_350], 80070006h
0x18004e1d3  jmp     short loc_18004E254
0x18004e1d5  movzx   eax, si
0x18004e1d8  mov     [rbp+2C0h+var_330], eax
0x18004e1db  test    eax, 0FFFFFFFCh
0x18004e1e0  jnz     short loc_18004E24C
0x18004e1e2  test    r12, r12
0x18004e1e5  jz      loc_18004E512
0x18004e1eb  test    r13, r13
0x18004e1ee  jz      loc_18004E512
0x18004e1f4  test    rbx, rbx
0x18004e1f7  jz      loc_18004E512
0x18004e1fd  mov     rax, [rbp+2C0h+var_320]
0x18004e201  lea     rbx, qword_1800E46D0
0x18004e208  shr     esi, 10h
0x18004e20b  test    rax, rax
0x18004e20e  cmovnz  rbx, rax
0x18004e212  cmp     r15d, 1
0x18004e216  jnz     loc_18004E2EA
0x18004e21c  test    esi, esi
0x18004e21e  jnz     short loc_18004E24C
0x18004e220  mov     edi, [rbp+2C0h+arg_20]
0x18004e226  test    edi, edi
0x18004e228  jnz     short loc_18004E24C
0x18004e22a  test    r14, r14
0x18004e22d  jnz     short loc_18004E24C
0x18004e22f  mov     rax, [rbx]
0x18004e232  cmp     rax, cs:qword_1800E46D0
0x18004e239  jnz     short loc_18004E24C
0x18004e23b  mov     rax, [rbx+8]
0x18004e23f  cmp     rax, cs:qword_1800E46D8
0x18004e246  jz      loc_18004E389
0x18004e24c  mov     [rsp+3C0h+var_350], 80070057h
0x18004e254  mov     eax, cs:dword_18010F170
0x18004e25a  cmp     eax, 3
0x18004e25d  jbe     short loc_18004E287
0x18004e25f  mov     eax, [rsp+3C0h+var_350]
0x18004e263  lea     rdx, byte_1800F00FB
0x18004e26a  mov     [rsp+3C0h+var_344], eax
0x18004e26e  lea     rcx, dword_18010F170
0x18004e275  lea     rax, [rsp+3C0h+var_344]
0x18004e27a  xor     r8d, r8d
0x18004e27d  mov     qword ptr [rsp+3C0h+var_3A0], rax
0x18004e282  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004e287  mov     rax, [rbp+2C0h+var_338]
0x18004e28b  mov     qword ptr [r12], 0
0x18004e293  mov     qword ptr [r13+0], 0
0x18004e29b  mov     qword ptr [rax], 0
0x18004e2a2  mov     rcx, [rbp+2C0h+hObject]; hObject
0x18004e2a6  test    rcx, rcx
0x18004e2a9  jz      short loc_18004E2B1
0x18004e2ab  call    cs:__imp_CloseHandle
0x18004e2b1  mov     ebx, [rsp+3C0h+var_350]
0x18004e2b5  lea     rcx, [rbp+2C0h+var_2F8]
0x18004e2b9  call    WppTraceUnwinder__lambda_018bb5ef1578d90ec3f7529241e6b868_______WppTraceUnwinder__lambda_018bb5ef1578d90ec3f7529241e6b868____
0x18004e2be  mov     eax, ebx
0x18004e2c0  mov     rcx, [rbp+2C0h+var_40]
0x18004e2c7  xor     rcx, rsp; StackCookie
0x18004e2ca  call    __security_check_cookie
0x18004e2cf  mov     rbx, [rsp+3C0h+arg_18]
0x18004e2d7  add     rsp, 390h
0x18004e2de  pop     r15
0x18004e2e0  pop     r14
0x18004e2e2  pop     r13
0x18004e2e4  pop     r12
0x18004e2e6  pop     rdi
0x18004e2e7  pop     rsi
0x18004e2e8  pop     rbp
0x18004e2e9  retn
0x18004e2ea  cmp     r15d, 2
0x18004e2ee  jnz     loc_18004E24C
0x18004e2f4  call    IsWinBioIsLegacyPresent
0x18004e2f9  test    al, al
0x18004e2fb  jz      loc_18004E505
0x18004e301  call    cs:__imp_WinBioIsLegacy
0x18004e307  test    eax, eax
0x18004e309  jz      loc_18004E505
0x18004e30f  lea     eax, [rsi-1]
0x18004e312  cmp     eax, 1
0x18004e315  ja      loc_18004E24C
0x18004e31b  mov     edi, [rbp+2C0h+arg_20]
0x18004e321  test    edi, edi
0x18004e323  jz      loc_18004E24C
0x18004e329  test    r14, r14
0x18004e32c  jnz     short loc_18004E33B
0x18004e32e  mov     [rsp+3C0h+var_350], 80004003h
0x18004e336  jmp     loc_18004E254
0x18004e33b  mov     rax, [rbx]
0x18004e33e  cmp     rax, cs:qword_1800E46D0
0x18004e345  jnz     short loc_18004E358
0x18004e347  mov     rax, [rbx+8]
0x18004e34b  cmp     rax, cs:qword_1800E46D8
0x18004e352  jz      loc_18004E24C
0x18004e358  xor     ecx, ecx
0x18004e35a  test    edi, edi
0x18004e35c  jz      short loc_18004E389
0x18004e35e  mov     r8d, [r14+rcx*4]
0x18004e362  test    r8d, r8d
0x18004e365  jz      loc_18004E24C
0x18004e36b  mov     edx, ecx
0x18004e36d  mov     eax, edx
0x18004e36f  cmp     r8d, [r14+rax*4]
0x18004e373  jnz     short loc_18004E37D
0x18004e375  cmp     ecx, edx
0x18004e377  jnz     loc_18004E24C
0x18004e37d  inc     edx
0x18004e37f  cmp     edx, edi
0x18004e381  jb      short loc_18004E36D
0x18004e383  inc     ecx
0x18004e385  cmp     ecx, edi
0x18004e387  jb      short loc_18004E35E
0x18004e389  lea     rcx, [rsp+3C0h+dwProcessId]
0x18004e38e  call    _GetRpcClientPid
0x18004e393  mov     [rsp+3C0h+var_350], eax
0x18004e397  test    eax, eax
0x18004e399  js      short loc_18004E402
0x18004e39b  mov     ecx, [rsp+3C0h+dwProcessId]; dwProcessId
0x18004e39f  lea     rdx, [rsp+3C0h+pSessionId]; pSessionId
0x18004e3a4  call    cs:__imp_ProcessIdToSessionId
0x18004e3aa  test    eax, eax
0x18004e3ac  jnz     short loc_18004E3BB
0x18004e3ae  mov     [rsp+3C0h+var_350], 80070005h
0x18004e3b6  jmp     loc_18004E254
0x18004e3bb  cmp     [rsp+3C0h+pSessionId], 0
0x18004e3c0  jz      short loc_18004E42D
0x18004e3c2  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18004e3c8  cmp     [rsp+3C0h+pSessionId], eax
0x18004e3cc  jz      short loc_18004E42D
0x18004e3ce  cmp     r15d, 2
0x18004e3d2  jz      short loc_18004E42D
0x18004e3d4  lea     rcx, [rbp+2C0h+var_270]; this
0x18004e3d8  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004e3dd  mov     edx, 3FDh
0x18004e3e2  lea     rcx, [rbp+2C0h+var_270]
0x18004e3e6  mov     r8d, 1
0x18004e3ec  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004e3f1  lea     rcx, [rbp+2C0h+var_270]; this
0x18004e3f5  mov     [rsp+3C0h+var_350], 80098038h
0x18004e3fd  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x18004e402  mov     rbx, [rbp+2C0h+var_338]
0x18004e406  cmp     [rsp+3C0h+var_350], 0
0x18004e40b  jl      loc_18004E254
0x18004e411  mov     rax, [rbp+2C0h+var_318]
0x18004e415  mov     [r12], rax
0x18004e419  mov     rax, [rbp+2C0h+var_310]
0x18004e41d  mov     [r13+0], rax
0x18004e421  mov     rax, [rbp+2C0h+var_308]
0x18004e425  mov     [rbx], rax
0x18004e428  jmp     loc_18004E2A2
0x18004e42d  mov     rbx, [rbp+2C0h+BindingHandle]
0x18004e431  mov     rcx, rbx; BindingHandle
0x18004e434  call    cs:__imp_RpcImpersonateClient
0x18004e43a  test    eax, eax
0x18004e43c  jz      short loc_18004E449
0x18004e43e  or      eax, 80010000h
0x18004e443  mov     [rsp+3C0h+var_350], eax
0x18004e447  jmp     short loc_18004E402
0x18004e449  call    cs:__imp_GetCurrentThread
0x18004e44f  lea     r9, [rbp+2C0h+hObject]; TokenHandle
0x18004e453  mov     edx, 20008h; DesiredAccess
0x18004e458  mov     rcx, rax; ThreadHandle
0x18004e45b  mov     r8d, 1; OpenAsSelf
0x18004e461  call    cs:__imp_OpenThreadToken
0x18004e467  test    eax, eax
0x18004e469  jnz     short loc_18004E481
0x18004e46b  call    cs:__imp_GetLastError
0x18004e471  test    eax, eax
0x18004e473  jle     short loc_18004E47D
0x18004e475  movzx   eax, ax
0x18004e478  or      eax, 80070000h
0x18004e47d  mov     [rsp+3C0h+var_350], eax
0x18004e481  mov     rcx, rbx; BindingHandle
0x18004e484  call    cs:__imp_RpcRevertToSelfEx
0x18004e48a  test    eax, eax
0x18004e48c  jz      short loc_18004E499
0x18004e48e  or      eax, 80010000h
0x18004e493  mov     [rsp+3C0h+var_350], eax
0x18004e497  jmp     short loc_18004E49D
0x18004e499  mov     eax, [rsp+3C0h+var_350]
0x18004e49d  test    eax, eax
0x18004e49f  js      loc_18004E254
0x18004e4a5  cmp     [rbp+2C0h+arg_38], 0
0x18004e4ac  lea     rcx, [rbp+2C0h+var_308]
0x18004e4b0  mov     r8d, [rsp+3C0h+var_344]; unsigned int
0x18004e4b5  mov     r9d, r15d; unsigned int
0x18004e4b8  mov     rdx, [rbp+2C0h+hObject]; void *
0x18004e4bc  setnz   al
0x18004e4bf  mov     [rsp+3C0h+var_360], rcx; unsigned __int64 *
0x18004e4c4  lea     rcx, [rbp+2C0h+var_310]
0x18004e4c8  mov     [rsp+3C0h+var_368], rcx; unsigned __int64 *
0x18004e4cd  lea     rcx, [rbp+2C0h+var_318]
0x18004e4d1  mov     [rsp+3C0h+var_370], rcx; void **
0x18004e4d6  mov     ecx, [rsp+3C0h+dwProcessId]; unsigned int
0x18004e4da  mov     [rsp+3C0h+var_378], al; bool
0x18004e4de  mov     rax, [rbp+2C0h+var_320]
0x18004e4e2  mov     [rsp+3C0h+var_380], rax; struct _GUID *
0x18004e4e7  mov     eax, [rbp+2C0h+var_330]
0x18004e4ea  mov     [rsp+3C0h+var_388], r14; unsigned int *
0x18004e4ef  mov     [rsp+3C0h+var_390], edi; unsigned int
0x18004e4f3  mov     [rsp+3C0h+var_398], eax; unsigned int
0x18004e4f7  mov     [rsp+3C0h+var_3A0], esi; unsigned int
0x18004e4fb  call    ?OpenBiometricSession@CServer@@SAJKPEAXIKKKKPEAKPEAU_GUID@@_NPEAPEAXPEA_K5@Z; CServer::OpenBiometricSession(ulong,void *,uint,ulong,ulong,ulong,ulong,ulong *,_GUID *,bool,void * *,unsigned __int64 *,unsigned __int64 *)
0x18004e500  jmp     loc_18004E443
0x18004e505  mov     [rsp+3C0h+var_350], 80098048h
0x18004e50d  jmp     loc_18004E254
0x18004e512  mov     [rsp+3C0h+var_350], 80004003h
0x18004e51a  jmp     loc_18004E406
```
