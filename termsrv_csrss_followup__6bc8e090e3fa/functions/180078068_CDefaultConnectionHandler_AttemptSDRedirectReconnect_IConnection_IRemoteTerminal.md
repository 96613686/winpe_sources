# CDefaultConnectionHandler::AttemptSDRedirectReconnect(IConnection *,IRemoteTerminal *)

- ea: `0x180078068`
- end: `0x18007866b`
- name: `?AttemptSDRedirectReconnect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800799f0`

## callees

- `0x1800016a8`
- `0x180009940`
- `0x180012c90`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x180015310`
- `0x18002558c`
- `0x18003440c`
- `0x18003444c`
- `0x180051e44`
- `0x18005497c`
- `0x180078068`
- `0x1800c3afc`
- `0x1800c3bc8`
- `0x1800c3db4`
- `0x1800ce010`

## string_xrefs

- `0x180078604`: `Task completed successfully`
- `0x1800780c9`: `Attempting SD redirect reconnect`
- `0x1800780b6`: `CDefaultConnectionHandler::AttemptSDRedirectReconnect`
- `0x1800780bd`: `Session Directory Redirect`
- `0x1800782f4`: `Session Directory Redirect`
- `0x18007812e`: `AttemptSDRedirectReconnect`
- `0x1800781e8`: `AttemptSDRedirectReconnect`
- `0x1800782a0`: `AttemptSDRedirectReconnect`
- `0x1800783df`: `AttemptSDRedirectReconnect`
- `0x18007841f`: `AttemptSDRedirectReconnect`
- `0x18007846d`: `AttemptSDRedirectReconnect`
- `0x180078531`: `AttemptSDRedirectReconnect`
- `0x180078578`: `AttemptSDRedirectReconnect`
- `0x18007862a`: `AttemptSDRedirectReconnect`
- `0x18007853c`: `ptrStorage->Remove`
- `0x1800785e4`: `Autoreconnect connection broker connection to session %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDefaultConnectionHandler::AttemptSDRedirectReconnect(
        CDefaultConnectionHandler *this,
        struct IConnection *a2,
        struct IRemoteTerminal *a3,
        int a4)
{
  int v6; // ecx
  int SessionList; // edi
  int v8; // r8d
  int v9; // r9d
  const char **v10; // rax
  __int16 *v11; // rdx
  CSessionKey *v12; // rax
  CSessionKey *v13; // rax
  struct CSessionKey *v14; // rbx
  const char *v15; // rax
  char *v16; // rdx
  int v17; // esi
  const char *v18; // rax
  char *v19; // rdx
  __int16 *v20; // rdx
  _BYTE *v21; // rcx
  __int64 v22; // rax
  unsigned int v24; // esi
  int v25; // edx
  const char *v26; // rax
  __int64 *v27; // rdx
  const char **v28; // [rsp+28h] [rbp-41h]
  const char **v29; // [rsp+38h] [rbp-31h]
  const char *v30; // [rsp+40h] [rbp-29h] BYREF
  const char *v31; // [rsp+48h] [rbp-21h] BYREF
  const char *v32; // [rsp+50h] [rbp-19h] BYREF
  __int64 v33; // [rsp+58h] [rbp-11h] BYREF
  void *Block; // [rsp+60h] [rbp-9h]
  struct ITSObjectStorage *v35; // [rsp+68h] [rbp-1h] BYREF
  CSessionKey *v36; // [rsp+70h] [rbp+7h] BYREF
  struct CSessionKey *v37; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v38; // [rsp+80h] [rbp+17h] BYREF
  struct ISessionList *v39[7]; // [rsp+88h] [rbp+1Fh] BYREF
  unsigned int v40; // [rsp+D0h] [rbp+67h] BYREF
  int v41; // [rsp+D4h] [rbp+6Bh]
  const char *v42; // [rsp+D8h] [rbp+6Fh] BYREF
  struct ITSSession *v43; // [rsp+E8h] [rbp+7Fh] BYREF

  v41 = HIDWORD(this);
  v40 = 0;
  v43 = 0;
  v39[0] = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v33 = 0;
  Block = 0;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v42 = "Attempting SD redirect reconnect";
    v32 = "CDefaultConnectionHandler::AttemptSDRedirectReconnect";
    v30 = "Session Directory Redirect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_180112DA3,
      (_DWORD)a3,
      a4,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v42);
  }
  SessionList = (*(__int64 (__fastcall **)(struct IConnection *, __int64 *))(*(_QWORD *)a2 + 544LL))(a2, &v33);
  if ( SessionList < 0 )
  {
    v6 = dword_18012E170;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v30 = "AttemptSDRedirectReconnect";
      v32 = "GetClearTextUserPassword";
      v31 = "Warning HResult failed";
      v29 = &v30;
      v28 = &v32;
      v10 = &v31;
      v11 = word_180112D5A;
LABEL_14:
      LODWORD(v42) = SessionList;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v10,
        (__int64)v28,
        (__int64)&v42,
        (__int64)v29);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  if ( !Block || !(_WORD)v33 )
  {
    if ( (unsigned int)dword_18012E170 <= 4 )
      goto LABEL_19;
    v15 = "password is NULL";
    v16 = byte_180112D2B;
    goto LABEL_18;
  }
  v12 = (CSessionKey *)operator new(0x6C8u, (const struct std::nothrow_t *)std::nothrow);
  v42 = (const char *)v12;
  if ( v12 )
    v13 = CSessionKey::CSessionKey(v12, (unsigned __int8 *)Block, (unsigned __int16)v33);
  else
    v13 = 0;
  SmartPtr<ITerminal>::operator=(&v37, v13);
  v14 = v37;
  if ( !v37 )
  {
    SessionList = -2147024882;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v31 = "AttemptSDRedirectReconnect";
      v30 = "new CSessionKey()";
      v32 = "Warning HResult failed";
      v29 = &v31;
      v28 = &v30;
      v10 = &v32;
      v11 = word_180112CE2;
      goto LABEL_14;
    }
LABEL_24:
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_27;
    v30 = "Session Directory Redirect";
    v20 = (__int16 *)&dword_180112A0C;
    goto LABEL_26;
  }
  if ( !*((_DWORD *)v37 + 400) )
  {
    if ( (unsigned int)dword_18012E170 <= 4 )
    {
LABEL_19:
      SessionList = -2147467263;
      goto LABEL_24;
    }
    v15 = "invalid session key";
    v16 = byte_180112CB3;
LABEL_18:
    v42 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v6,
      (_DWORD)v16,
      v8,
      v9,
      (__int64)&v42);
    goto LABEL_19;
  }
  v17 = *((_DWORD *)v37 + 404);
  SessionList = CHelper::GetSessionList(v39);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "GetSessionList";
    v19 = (char *)word_180112C6A;
LABEL_23:
    v30 = v18;
    v32 = "Warning HResult failed";
    LODWORD(v42) = SessionList;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v6,
      (_DWORD)v19,
      v8,
      v9,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v42,
      (__int64)&v31);
    goto LABEL_24;
  }
  v24 = v17 & 0x7FFFFFFF;
  SessionList = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, struct ITSSession **))(*(_QWORD *)v39[0] + 24LL))(
                  v39[0],
                  v24,
                  &v43);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "FindSessionById";
    v19 = byte_180112C21;
    goto LABEL_23;
  }
  SessionList = CHelper::GetStorageForSessionObject(v43, v25, &v35);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "GetStorageForSessionObject";
    v19 = (char *)&unk_180112BD8;
    goto LABEL_23;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSObjectStorage *, GUID *, __int64 *))(*(_QWORD *)v35 + 32LL))(
                  v35,
                  &IID_SessionKey,
                  &v38);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "ptrStorage->Get(IID_SessionKey)";
    v19 = &byte_180112B8F;
    goto LABEL_23;
  }
  SmartPtr<ITerminal>::operator=(&v36, v38);
  if ( (unsigned int)CSessionKey::IsExpired(v36) )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
    {
LABEL_46:
      SessionList = -2147467263;
      goto LABEL_24;
    }
    v26 = "Session key expired";
    v27 = qword_180112B60;
LABEL_45:
    v42 = v26;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v6,
      (_DWORD)v27,
      v8,
      v9,
      (__int64)&v42);
    goto LABEL_46;
  }
  if ( !(unsigned int)CSessionKey::Equals(v36, v14) )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_46;
    v26 = "Session key does not match";
    v27 = (__int64 *)byte_180112B31;
    goto LABEL_45;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSObjectStorage *, GUID *))(*(_QWORD *)v35 + 40LL))(
                  v35,
                  &IID_SessionKey);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "ptrStorage->Remove";
    v19 = (char *)&unk_180112AE8;
    goto LABEL_23;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)v43 + 88LL))(v43, &v40);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "getState";
    v19 = &byte_180112A9F;
    goto LABEL_23;
  }
  if ( (unsigned int)IsLoggedOnState(v40) )
    (*(void (__fastcall **)(struct ITSSession *, __int64))(*(_QWORD *)v43 + 56LL))(v43, 5);
  SessionList = (*(__int64 (__fastcall **)(struct ITSSession *, struct IRemoteTerminal *, _QWORD, _QWORD))(*(_QWORD *)v43 + 48LL))(
                  v43,
                  a3,
                  0,
                  0);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "Session->Reconnect( Terminal )";
    v19 = (char *)&word_180112A56;
    goto LABEL_23;
  }
  if ( (g_DebugTraceComponent & 4) != 0 )
    _DbgPrintMessage(2, "Autoreconnect connection broker connection to session %d", v24);
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v30 = "Task completed successfully";
    v20 = word_1801129CA;
LABEL_26:
    LODWORD(v42) = SessionList;
    v31 = "CDefaultConnectionHandler::AttemptSDRedirectReconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (_DWORD)v20,
      v8,
      v9,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&v42);
  }
LABEL_27:
  v21 = Block;
  if ( Block )
  {
    v22 = (unsigned __int16)v33;
    if ( (_WORD)v33 )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
      v21 = Block;
    }
    operator delete(v21);
  }
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v35);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v36);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v37);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(v39);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
  return (unsigned int)SessionList;
}

```

## disassembly

```asm
0x180078068  mov     [rsp-8+arg_0], rcx
0x18007806d  push    rbp
0x18007806e  push    rbx
0x18007806f  push    rsi
0x180078070  push    rdi
0x180078071  push    r13
0x180078073  push    r14
0x180078075  push    r15
0x180078077  lea     rbp, [rsp-27h]
0x18007807c  sub     rsp, 90h
0x180078083  mov     r14, r8
0x180078086  mov     rbx, rdx
0x180078089  xor     r15d, r15d
0x18007808c  mov     dword ptr [rbp+57h+arg_0], r15d
0x180078090  mov     [rbp+57h+arg_18], r15
0x180078094  mov     [rbp+57h+var_38], r15
0x180078098  mov     [rbp+57h+var_40], r15
0x18007809c  mov     [rbp+57h+var_48], r15
0x1800780a0  mov     [rbp+57h+var_50], r15
0x1800780a4  mov     [rbp+57h+var_58], r15
0x1800780a8  mov     [rbp+57h+var_68], r15
0x1800780ac  mov     [rbp+57h+Block], r15
0x1800780b0  mov     eax, cs:dword_18012E170
0x1800780b6  lea     r13, aCdefaultconnec_4; "CDefaultConnectionHandler::AttemptSDRed"...
0x1800780bd  lea     rsi, aSessionDirecto_1; "Session Directory Redirect"
0x1800780c4  cmp     eax, 4
0x1800780c7  jbe     short loc_180078103
0x1800780c9  lea     rax, aAttemptingSdRe_0; "Attempting SD redirect reconnect"
0x1800780d0  mov     [rbp+57h+arg_8], rax
0x1800780d4  mov     [rbp+57h+var_70], r13
0x1800780d8  mov     [rbp+57h+var_80], rsi
0x1800780dc  lea     rax, [rbp+57h+arg_8]
0x1800780e0  mov     [rsp+0C0h+var_90], rax
0x1800780e5  lea     rax, [rbp+57h+var_70]
0x1800780e9  mov     [rsp+0C0h+var_98], rax
0x1800780ee  lea     rax, [rbp+57h+var_80]
0x1800780f2  mov     [rsp+0C0h+var_A0], rax
0x1800780f7  lea     rdx, byte_180112DA3
0x1800780fe  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180078103  mov     rax, [rbx]
0x180078106  lea     rdx, [rbp+57h+var_68]
0x18007810a  mov     rcx, rbx
0x18007810d  mov     rax, [rax+220h]
0x180078114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078119  mov     edi, eax
0x18007811b  test    eax, eax
0x18007811d  jns     short loc_18007817A
0x18007811f  mov     ecx, cs:dword_18012E170
0x180078125  cmp     ecx, 3
0x180078128  jbe     loc_1800782FB
0x18007812e  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180078135  mov     [rbp+57h+var_80], rax
0x180078139  lea     rax, aGetcleartextus; "GetClearTextUserPassword"
0x180078140  mov     [rbp+57h+var_70], rax
0x180078144  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007814b  mov     [rbp+57h+var_78], rax
0x18007814f  lea     rax, [rbp+57h+var_80]
0x180078153  mov     [rsp+0C0h+var_88], rax
0x180078158  lea     rax, [rbp+57h+arg_8]
0x18007815c  mov     [rsp+0C0h+var_90], rax
0x180078161  lea     rax, [rbp+57h+var_70]
0x180078165  mov     [rsp+0C0h+var_98], rax
0x18007816a  lea     rax, [rbp+57h+var_78]
0x18007816e  lea     rdx, word_180112D5A
0x180078175  jmp     loc_18007822F
0x18007817a  cmp     [rbp+57h+Block], r15
0x18007817e  jz      loc_180078648
0x180078184  cmp     word ptr [rbp+57h+var_68], r15w
0x180078189  jz      loc_180078648
0x18007818f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180078196  mov     ecx, 6C8h; unsigned __int64
0x18007819b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800781a0  mov     [rbp+57h+arg_8], rax
0x1800781a4  test    rax, rax
0x1800781a7  jz      short loc_1800781BC
0x1800781a9  movzx   r8d, word ptr [rbp+57h+var_68]; unsigned int
0x1800781ae  mov     rdx, [rbp+57h+Block]; unsigned __int8 *
0x1800781b2  mov     rcx, rax; this
0x1800781b5  call    ??0CSessionKey@@QEAA@PEAEK@Z; CSessionKey::CSessionKey(uchar *,ulong)
0x1800781ba  jmp     short loc_1800781BF
0x1800781bc  mov     rax, r15
0x1800781bf  mov     rdx, rax
0x1800781c2  lea     rcx, [rbp+57h+var_48]
0x1800781c6  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x1800781cb  mov     rbx, [rbp+57h+var_48]
0x1800781cf  test    rbx, rbx
0x1800781d2  jnz     short loc_180078241
0x1800781d4  mov     edi, 8007000Eh
0x1800781d9  mov     eax, cs:dword_18012E170
0x1800781df  cmp     eax, 3
0x1800781e2  jbe     loc_1800782FB
0x1800781e8  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x1800781ef  mov     [rbp+57h+var_78], rax
0x1800781f3  lea     rax, aNewCsessionkey; "new CSessionKey()"
0x1800781fa  mov     [rbp+57h+var_80], rax
0x1800781fe  lea     rax, aWarningHresult; "Warning HResult failed"
0x180078205  mov     [rbp+57h+var_70], rax
0x180078209  lea     rax, [rbp+57h+var_78]
0x18007820d  mov     [rsp+0C0h+var_88], rax
0x180078212  lea     rax, [rbp+57h+arg_8]
0x180078216  mov     [rsp+0C0h+var_90], rax
0x18007821b  lea     rax, [rbp+57h+var_80]
0x18007821f  mov     [rsp+0C0h+var_98], rax
0x180078224  lea     rax, [rbp+57h+var_70]
0x180078228  lea     rdx, word_180112CE2
0x18007822f  mov     [rsp+0C0h+var_A0], rax
0x180078234  mov     dword ptr [rbp+57h+arg_8], edi
0x180078237  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007823c  jmp     loc_1800782FB
0x180078241  cmp     [rbx+640h], r15d
0x180078248  jnz     short loc_18007827C
0x18007824a  mov     eax, cs:dword_18012E170
0x180078250  cmp     eax, 4
0x180078253  jbe     short loc_180078275
0x180078255  lea     rax, aInvalidSession_0; "invalid session key"
0x18007825c  lea     rdx, byte_180112CB3
0x180078263  mov     [rbp+57h+arg_8], rax
0x180078267  lea     rax, [rbp+57h+arg_8]
0x18007826b  mov     [rsp+0C0h+var_A0], rax
0x180078270  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180078275  mov     edi, 80004001h
0x18007827a  jmp     short loc_1800782FB
0x18007827c  mov     esi, [rbx+650h]
0x180078282  lea     rcx, [rbp+57h+var_38]; struct ISessionList **
0x180078286  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x18007828b  mov     edi, eax
0x18007828d  test    eax, eax
0x18007828f  jns     loc_1800783B0
0x180078295  mov     eax, cs:dword_18012E170
0x18007829b  cmp     eax, 3
0x18007829e  jbe     short loc_1800782F4
0x1800782a0  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x1800782a7  mov     [rbp+57h+var_78], rax
0x1800782ab  lea     rax, aGetsessionlist_1; "GetSessionList"
0x1800782b2  lea     rdx, word_180112C6A
0x1800782b9  mov     [rbp+57h+var_80], rax
0x1800782bd  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800782c4  mov     [rbp+57h+var_70], rax
0x1800782c8  lea     rax, [rbp+57h+var_78]
0x1800782cc  mov     [rsp+0C0h+var_88], rax
0x1800782d1  lea     rax, [rbp+57h+arg_8]
0x1800782d5  mov     [rsp+0C0h+var_90], rax
0x1800782da  lea     rax, [rbp+57h+var_80]
0x1800782de  mov     [rsp+0C0h+var_98], rax
0x1800782e3  lea     rax, [rbp+57h+var_70]
0x1800782e7  mov     dword ptr [rbp+57h+arg_8], edi
0x1800782ea  mov     [rsp+0C0h+var_A0], rax
0x1800782ef  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800782f4  lea     rsi, aSessionDirecto_1; "Session Directory Redirect"
0x1800782fb  mov     eax, cs:dword_18012E170
0x180078301  cmp     eax, 3
0x180078304  jbe     short loc_180078338
0x180078306  mov     [rbp+57h+var_80], rsi
0x18007830a  lea     rdx, dword_180112A0C
0x180078311  lea     rax, [rbp+57h+arg_8]
0x180078315  mov     [rsp+0C0h+var_90], rax
0x18007831a  lea     rax, [rbp+57h+var_78]
0x18007831e  mov     [rsp+0C0h+var_98], rax
0x180078323  lea     rax, [rbp+57h+var_80]
0x180078327  mov     [rsp+0C0h+var_A0], rax
0x18007832c  mov     dword ptr [rbp+57h+arg_8], edi
0x18007832f  mov     [rbp+57h+var_78], r13
0x180078333  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180078338  mov     rcx, [rbp+57h+Block]
0x18007833c  test    rcx, rcx
0x18007833f  jz      short loc_180078360
0x180078341  movzx   eax, word ptr [rbp+57h+var_68]
0x180078345  test    rax, rax
0x180078348  jz      short loc_18007835A
0x18007834a  mov     [rcx], r15b
0x18007834d  inc     rcx
0x180078350  sub     rax, 1
0x180078354  jnz     short loc_18007834A
0x180078356  mov     rcx, [rbp+57h+Block]; Block
0x18007835a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007835f  nop
0x180078360  lea     rcx, [rbp+57h+var_58]; void *
0x180078364  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180078369  nop
0x18007836a  lea     rcx, [rbp+57h+var_50]; void *
0x18007836e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180078373  nop
0x180078374  lea     rcx, [rbp+57h+var_48]; void *
0x180078378  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18007837d  nop
0x18007837e  lea     rcx, [rbp+57h+var_40]; void *
0x180078382  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180078387  nop
0x180078388  lea     rcx, [rbp+57h+var_38]; void *
0x18007838c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180078391  nop
0x180078392  lea     rcx, [rbp+57h+arg_18]; void *
0x180078396  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18007839b  mov     eax, edi
0x18007839d  add     rsp, 90h
0x1800783a4  pop     r15
0x1800783a6  pop     r14
0x1800783a8  pop     r13
0x1800783aa  pop     rdi
0x1800783ab  pop     rsi
0x1800783ac  pop     rbx
0x1800783ad  pop     rbp
0x1800783ae  retn
0x1800783b0  btr     esi, 1Fh
0x1800783b4  mov     rcx, [rbp+57h+var_38]
0x1800783b8  mov     rax, [rcx]
0x1800783bb  lea     r8, [rbp+57h+arg_18]
0x1800783bf  mov     edx, esi
0x1800783c1  mov     rax, [rax+18h]
0x1800783c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783ca  mov     edi, eax
0x1800783cc  test    eax, eax
0x1800783ce  jns     short loc_1800783FD
0x1800783d0  mov     eax, cs:dword_18012E170
0x1800783d6  cmp     eax, 3
0x1800783d9  jbe     loc_1800782F4
0x1800783df  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x1800783e6  mov     [rbp+57h+var_78], rax
0x1800783ea  lea     rax, aFindsessionbyi; "FindSessionById"
0x1800783f1  lea     rdx, byte_180112C21
0x1800783f8  jmp     loc_1800782B9
0x1800783fd  lea     r8, [rbp+57h+var_58]; struct ITSObjectStorage **
0x180078401  mov     rcx, [rbp+57h+arg_18]; struct ITSSession *
0x180078405  call    ?GetStorageForSessionObject@CHelper@@SAJPEAUITSSession@@HPEAPEAVITSObjectStorage@@@Z; CHelper::GetStorageForSessionObject(ITSSession *,int,ITSObjectStorage * *)
0x18007840a  mov     edi, eax
0x18007840c  test    eax, eax
0x18007840e  jns     short loc_18007843D
0x180078410  mov     eax, cs:dword_18012E170
0x180078416  cmp     eax, 3
0x180078419  jbe     loc_1800782F4
0x18007841f  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180078426  mov     [rbp+57h+var_78], rax
0x18007842a  lea     rax, aGetstoragefors; "GetStorageForSessionObject"
0x180078431  lea     rdx, unk_180112BD8
0x180078438  jmp     loc_1800782B9
0x18007843d  mov     rcx, [rbp+57h+var_58]
0x180078441  mov     rax, [rcx]
0x180078444  lea     r8, [rbp+57h+var_40]
0x180078448  lea     rdx, ?IID_SessionKey@@3U_GUID@@B; _GUID const IID_SessionKey
0x18007844f  mov     rax, [rax+20h]
0x180078453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078458  mov     edi, eax
0x18007845a  test    eax, eax
0x18007845c  jns     short loc_18007848B
0x18007845e  mov     eax, cs:dword_18012E170
0x180078464  cmp     eax, 3
0x180078467  jbe     loc_1800782F4
0x18007846d  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180078474  mov     [rbp+57h+var_78], rax
0x180078478  lea     rax, aPtrstorageGetI; "ptrStorage->Get(IID_SessionKey)"
0x18007847f  lea     rdx, byte_180112B8F
0x180078486  jmp     loc_1800782B9
0x18007848b  mov     rdx, [rbp+57h+var_40]
0x18007848f  lea     rcx, [rbp+57h+var_50]
0x180078493  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180078498  mov     rcx, [rbp+57h+var_50]; this
0x18007849c  call    ?IsExpired@CSessionKey@@QEBAHXZ; CSessionKey::IsExpired(void)
0x1800784a1  test    eax, eax
0x1800784a3  jz      short loc_1800784DA
0x1800784a5  mov     eax, cs:dword_18012E170
0x1800784ab  cmp     eax, 3
0x1800784ae  jbe     short loc_1800784D0
0x1800784b0  lea     rax, aSessionKeyExpi; "Session key expired"
0x1800784b7  lea     rdx, qword_180112B60
0x1800784be  mov     [rbp+57h+arg_8], rax
0x1800784c2  lea     rax, [rbp+57h+arg_8]
0x1800784c6  mov     [rsp+0C0h+var_A0], rax
0x1800784cb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800784d0  mov     edi, 80004001h
0x1800784d5  jmp     loc_1800782F4
0x1800784da  mov     rdx, rbx; struct CSessionKey *
0x1800784dd  mov     rcx, [rbp+57h+var_50]; this
0x1800784e1  call    ?Equals@CSessionKey@@QEBAHAEBV1@@Z; CSessionKey::Equals(CSessionKey const &)
0x1800784e6  test    eax, eax
0x1800784e8  jnz     short loc_180078505
0x1800784ea  mov     eax, cs:dword_18012E170
0x1800784f0  cmp     eax, 3
0x1800784f3  jbe     short loc_1800784D0
0x1800784f5  lea     rax, aSessionKeyDoes; "Session key does not match"
0x1800784fc  lea     rdx, byte_180112B31
0x180078503  jmp     short loc_1800784BE
0x180078505  mov     rcx, [rbp+57h+var_58]
0x180078509  mov     rax, [rcx]
0x18007850c  lea     rdx, ?IID_SessionKey@@3U_GUID@@B; _GUID const IID_SessionKey
0x180078513  mov     rax, [rax+28h]
0x180078517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007851c  mov     edi, eax
0x18007851e  test    eax, eax
0x180078520  jns     short loc_18007854F
0x180078522  mov     eax, cs:dword_18012E170
0x180078528  cmp     eax, 3
0x18007852b  jbe     loc_1800782F4
0x180078531  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180078538  mov     [rbp+57h+var_78], rax
0x18007853c  lea     rax, aPtrstorageRemo_1; "ptrStorage->Remove"
0x180078543  lea     rdx, unk_180112AE8
0x18007854a  jmp     loc_1800782B9
0x18007854f  mov     rcx, [rbp+57h+arg_18]
0x180078553  mov     rax, [rcx]
0x180078556  lea     rdx, [rbp+57h+arg_0]
  ... truncated ...
```
