# CDefaultConnectionHandler::AttemptSDRedirectReconnect(IConnection *,IRemoteTerminal *)

- ea: `0x180074ae0`
- end: `0x1800750e2`
- name: `?AttemptSDRedirectReconnect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `1538`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180076420`

## callees

- `0x180001688`
- `0x18000a210`
- `0x180012480`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800148f0`
- `0x1800241f0`
- `0x18003269c`
- `0x1800326dc`
- `0x18004f7a4`
- `0x180052248`
- `0x180074ae0`
- `0x1800bdb78`
- `0x1800bdc48`
- `0x1800bde30`
- `0x1800c8010`

## string_xrefs

- `0x18007507b`: `Task completed successfully`
- `0x180074b41`: `Attempting SD redirect reconnect`
- `0x180074b2e`: `CDefaultConnectionHandler::AttemptSDRedirectReconnect`
- `0x180074b35`: `Session Directory Redirect`
- `0x180074d6c`: `Session Directory Redirect`
- `0x180074ba6`: `AttemptSDRedirectReconnect`
- `0x180074c60`: `AttemptSDRedirectReconnect`
- `0x180074d18`: `AttemptSDRedirectReconnect`
- `0x180074e56`: `AttemptSDRedirectReconnect`
- `0x180074e96`: `AttemptSDRedirectReconnect`
- `0x180074ee4`: `AttemptSDRedirectReconnect`
- `0x180074fa8`: `AttemptSDRedirectReconnect`
- `0x180074fef`: `AttemptSDRedirectReconnect`
- `0x1800750a1`: `AttemptSDRedirectReconnect`
- `0x180074fb3`: `ptrStorage->Remove`
- `0x18007505b`: `Autoreconnect connection broker connection to session %d`

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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v42 = "Attempting SD redirect reconnect";
    v32 = "CDefaultConnectionHandler::AttemptSDRedirectReconnect";
    v30 = "Session Directory Redirect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)byte_18010CD23,
      (_DWORD)a3,
      a4,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v42);
  }
  SessionList = (*(__int64 (__fastcall **)(struct IConnection *, __int64 *))(*(_QWORD *)a2 + 544LL))(a2, &v33);
  if ( SessionList < 0 )
  {
    v6 = dword_180128170;
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v30 = "AttemptSDRedirectReconnect";
      v32 = "GetClearTextUserPassword";
      v31 = "Warning HResult failed";
      v29 = &v30;
      v28 = &v32;
      v10 = &v31;
      v11 = word_18010CCDA;
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
    if ( (unsigned int)dword_180128170 <= 4 )
      goto LABEL_19;
    v15 = "password is NULL";
    v16 = byte_18010CCAB;
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
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v31 = "AttemptSDRedirectReconnect";
      v30 = "new CSessionKey()";
      v32 = "Warning HResult failed";
      v29 = &v31;
      v28 = &v30;
      v10 = &v32;
      v11 = word_18010CC62;
      goto LABEL_14;
    }
LABEL_24:
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_27;
    v30 = "Session Directory Redirect";
    v20 = (__int16 *)&dword_18010C98C;
    goto LABEL_26;
  }
  if ( !*((_DWORD *)v37 + 400) )
  {
    if ( (unsigned int)dword_180128170 <= 4 )
    {
LABEL_19:
      SessionList = -2147467263;
      goto LABEL_24;
    }
    v15 = "invalid session key";
    v16 = byte_18010CC33;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "GetSessionList";
    v19 = (char *)word_18010CBEA;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "FindSessionById";
    v19 = byte_18010CBA1;
    goto LABEL_23;
  }
  SessionList = CHelper::GetStorageForSessionObject(v43, v25, &v35);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "GetStorageForSessionObject";
    v19 = (char *)&unk_18010CB58;
    goto LABEL_23;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSObjectStorage *, GUID *, __int64 *))(*(_QWORD *)v35 + 32LL))(
                  v35,
                  &IID_SessionKey,
                  &v38);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "ptrStorage->Get(IID_SessionKey)";
    v19 = &byte_18010CB0F;
    goto LABEL_23;
  }
  SmartPtr<ITerminal>::operator=(&v36, v38);
  if ( (unsigned int)CSessionKey::IsExpired(v36) )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
    {
LABEL_46:
      SessionList = -2147467263;
      goto LABEL_24;
    }
    v26 = "Session key expired";
    v27 = qword_18010CAE0;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_46;
    v26 = "Session key does not match";
    v27 = (__int64 *)byte_18010CAB1;
    goto LABEL_45;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSObjectStorage *, GUID *))(*(_QWORD *)v35 + 40LL))(
                  v35,
                  &IID_SessionKey);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "ptrStorage->Remove";
    v19 = (char *)&unk_18010CA68;
    goto LABEL_23;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)v43 + 88LL))(v43, &v40);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "getState";
    v19 = &byte_18010CA1F;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_24;
    v31 = "AttemptSDRedirectReconnect";
    v18 = "Session->Reconnect( Terminal )";
    v19 = (char *)&word_18010C9D6;
    goto LABEL_23;
  }
  if ( (g_DebugTraceComponent & 4) != 0 )
    _DbgPrintMessage(2, "Autoreconnect connection broker connection to session %d", v24);
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v30 = "Task completed successfully";
    v20 = word_18010C94A;
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
0x180074ae0  mov     [rsp-8+arg_0], rcx
0x180074ae5  push    rbp
0x180074ae6  push    rbx
0x180074ae7  push    rsi
0x180074ae8  push    rdi
0x180074ae9  push    r13
0x180074aeb  push    r14
0x180074aed  push    r15
0x180074aef  lea     rbp, [rsp-27h]
0x180074af4  sub     rsp, 90h
0x180074afb  mov     r14, r8
0x180074afe  mov     rbx, rdx
0x180074b01  xor     r15d, r15d
0x180074b04  mov     dword ptr [rbp+57h+arg_0], r15d
0x180074b08  mov     [rbp+57h+arg_18], r15
0x180074b0c  mov     [rbp+57h+var_38], r15
0x180074b10  mov     [rbp+57h+var_40], r15
0x180074b14  mov     [rbp+57h+var_48], r15
0x180074b18  mov     [rbp+57h+var_50], r15
0x180074b1c  mov     [rbp+57h+var_58], r15
0x180074b20  mov     [rbp+57h+var_68], r15
0x180074b24  mov     [rbp+57h+Block], r15
0x180074b28  mov     eax, cs:dword_180128170
0x180074b2e  lea     r13, aCdefaultconnec_4; "CDefaultConnectionHandler::AttemptSDRed"...
0x180074b35  lea     rsi, aSessionDirecto_1; "Session Directory Redirect"
0x180074b3c  cmp     eax, 4
0x180074b3f  jbe     short loc_180074B7B
0x180074b41  lea     rax, aAttemptingSdRe_0; "Attempting SD redirect reconnect"
0x180074b48  mov     [rbp+57h+arg_8], rax
0x180074b4c  mov     [rbp+57h+var_70], r13
0x180074b50  mov     [rbp+57h+var_80], rsi
0x180074b54  lea     rax, [rbp+57h+arg_8]
0x180074b58  mov     [rsp+0C0h+var_90], rax
0x180074b5d  lea     rax, [rbp+57h+var_70]
0x180074b61  mov     [rsp+0C0h+var_98], rax
0x180074b66  lea     rax, [rbp+57h+var_80]
0x180074b6a  mov     [rsp+0C0h+var_A0], rax
0x180074b6f  lea     rdx, byte_18010CD23
0x180074b76  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180074b7b  mov     rax, [rbx]
0x180074b7e  lea     rdx, [rbp+57h+var_68]
0x180074b82  mov     rcx, rbx
0x180074b85  mov     rax, [rax+220h]
0x180074b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b91  mov     edi, eax
0x180074b93  test    eax, eax
0x180074b95  jns     short loc_180074BF2
0x180074b97  mov     ecx, cs:dword_180128170
0x180074b9d  cmp     ecx, 3
0x180074ba0  jbe     loc_180074D73
0x180074ba6  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074bad  mov     [rbp+57h+var_80], rax
0x180074bb1  lea     rax, aGetcleartextus; "GetClearTextUserPassword"
0x180074bb8  mov     [rbp+57h+var_70], rax
0x180074bbc  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074bc3  mov     [rbp+57h+var_78], rax
0x180074bc7  lea     rax, [rbp+57h+var_80]
0x180074bcb  mov     [rsp+0C0h+var_88], rax
0x180074bd0  lea     rax, [rbp+57h+arg_8]
0x180074bd4  mov     [rsp+0C0h+var_90], rax
0x180074bd9  lea     rax, [rbp+57h+var_70]
0x180074bdd  mov     [rsp+0C0h+var_98], rax
0x180074be2  lea     rax, [rbp+57h+var_78]
0x180074be6  lea     rdx, word_18010CCDA
0x180074bed  jmp     loc_180074CA7
0x180074bf2  cmp     [rbp+57h+Block], r15
0x180074bf6  jz      loc_1800750BF
0x180074bfc  cmp     word ptr [rbp+57h+var_68], r15w
0x180074c01  jz      loc_1800750BF
0x180074c07  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074c0e  mov     ecx, 6C8h; unsigned __int64
0x180074c13  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180074c18  mov     [rbp+57h+arg_8], rax
0x180074c1c  test    rax, rax
0x180074c1f  jz      short loc_180074C34
0x180074c21  movzx   r8d, word ptr [rbp+57h+var_68]; unsigned int
0x180074c26  mov     rdx, [rbp+57h+Block]; unsigned __int8 *
0x180074c2a  mov     rcx, rax; this
0x180074c2d  call    ??0CSessionKey@@QEAA@PEAEK@Z; CSessionKey::CSessionKey(uchar *,ulong)
0x180074c32  jmp     short loc_180074C37
0x180074c34  mov     rax, r15
0x180074c37  mov     rdx, rax
0x180074c3a  lea     rcx, [rbp+57h+var_48]
0x180074c3e  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180074c43  mov     rbx, [rbp+57h+var_48]
0x180074c47  test    rbx, rbx
0x180074c4a  jnz     short loc_180074CB9
0x180074c4c  mov     edi, 8007000Eh
0x180074c51  mov     eax, cs:dword_180128170
0x180074c57  cmp     eax, 3
0x180074c5a  jbe     loc_180074D73
0x180074c60  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074c67  mov     [rbp+57h+var_78], rax
0x180074c6b  lea     rax, aNewCsessionkey; "new CSessionKey()"
0x180074c72  mov     [rbp+57h+var_80], rax
0x180074c76  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074c7d  mov     [rbp+57h+var_70], rax
0x180074c81  lea     rax, [rbp+57h+var_78]
0x180074c85  mov     [rsp+0C0h+var_88], rax
0x180074c8a  lea     rax, [rbp+57h+arg_8]
0x180074c8e  mov     [rsp+0C0h+var_90], rax
0x180074c93  lea     rax, [rbp+57h+var_80]
0x180074c97  mov     [rsp+0C0h+var_98], rax
0x180074c9c  lea     rax, [rbp+57h+var_70]
0x180074ca0  lea     rdx, word_18010CC62
0x180074ca7  mov     [rsp+0C0h+var_A0], rax
0x180074cac  mov     dword ptr [rbp+57h+arg_8], edi
0x180074caf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180074cb4  jmp     loc_180074D73
0x180074cb9  cmp     [rbx+640h], r15d
0x180074cc0  jnz     short loc_180074CF4
0x180074cc2  mov     eax, cs:dword_180128170
0x180074cc8  cmp     eax, 4
0x180074ccb  jbe     short loc_180074CED
0x180074ccd  lea     rax, aInvalidSession_0; "invalid session key"
0x180074cd4  lea     rdx, byte_18010CC33
0x180074cdb  mov     [rbp+57h+arg_8], rax
0x180074cdf  lea     rax, [rbp+57h+arg_8]
0x180074ce3  mov     [rsp+0C0h+var_A0], rax
0x180074ce8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180074ced  mov     edi, 80004001h
0x180074cf2  jmp     short loc_180074D73
0x180074cf4  mov     esi, [rbx+650h]
0x180074cfa  lea     rcx, [rbp+57h+var_38]; struct ISessionList **
0x180074cfe  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180074d03  mov     edi, eax
0x180074d05  test    eax, eax
0x180074d07  jns     loc_180074E27
0x180074d0d  mov     eax, cs:dword_180128170
0x180074d13  cmp     eax, 3
0x180074d16  jbe     short loc_180074D6C
0x180074d18  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074d1f  mov     [rbp+57h+var_78], rax
0x180074d23  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180074d2a  lea     rdx, word_18010CBEA
0x180074d31  mov     [rbp+57h+var_80], rax
0x180074d35  lea     rax, aWarningHresult; "Warning HResult failed"
0x180074d3c  mov     [rbp+57h+var_70], rax
0x180074d40  lea     rax, [rbp+57h+var_78]
0x180074d44  mov     [rsp+0C0h+var_88], rax
0x180074d49  lea     rax, [rbp+57h+arg_8]
0x180074d4d  mov     [rsp+0C0h+var_90], rax
0x180074d52  lea     rax, [rbp+57h+var_80]
0x180074d56  mov     [rsp+0C0h+var_98], rax
0x180074d5b  lea     rax, [rbp+57h+var_70]
0x180074d5f  mov     dword ptr [rbp+57h+arg_8], edi
0x180074d62  mov     [rsp+0C0h+var_A0], rax
0x180074d67  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180074d6c  lea     rsi, aSessionDirecto_1; "Session Directory Redirect"
0x180074d73  mov     eax, cs:dword_180128170
0x180074d79  cmp     eax, 3
0x180074d7c  jbe     short loc_180074DB0
0x180074d7e  mov     [rbp+57h+var_80], rsi
0x180074d82  lea     rdx, dword_18010C98C
0x180074d89  lea     rax, [rbp+57h+arg_8]
0x180074d8d  mov     [rsp+0C0h+var_90], rax
0x180074d92  lea     rax, [rbp+57h+var_78]
0x180074d96  mov     [rsp+0C0h+var_98], rax
0x180074d9b  lea     rax, [rbp+57h+var_80]
0x180074d9f  mov     [rsp+0C0h+var_A0], rax
0x180074da4  mov     dword ptr [rbp+57h+arg_8], edi
0x180074da7  mov     [rbp+57h+var_78], r13
0x180074dab  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180074db0  mov     rcx, [rbp+57h+Block]
0x180074db4  test    rcx, rcx
0x180074db7  jz      short loc_180074DD8
0x180074db9  movzx   eax, word ptr [rbp+57h+var_68]
0x180074dbd  test    rax, rax
0x180074dc0  jz      short loc_180074DD2
0x180074dc2  mov     [rcx], r15b
0x180074dc5  inc     rcx
0x180074dc8  sub     rax, 1
0x180074dcc  jnz     short loc_180074DC2
0x180074dce  mov     rcx, [rbp+57h+Block]; Block
0x180074dd2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074dd7  nop
0x180074dd8  lea     rcx, [rbp+57h+var_58]; void *
0x180074ddc  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074de1  nop
0x180074de2  lea     rcx, [rbp+57h+var_50]; void *
0x180074de6  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074deb  nop
0x180074dec  lea     rcx, [rbp+57h+var_48]; void *
0x180074df0  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074df5  nop
0x180074df6  lea     rcx, [rbp+57h+var_40]; void *
0x180074dfa  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074dff  nop
0x180074e00  lea     rcx, [rbp+57h+var_38]; void *
0x180074e04  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074e09  nop
0x180074e0a  lea     rcx, [rbp+57h+arg_18]; void *
0x180074e0e  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180074e13  mov     eax, edi
0x180074e15  add     rsp, 90h
0x180074e1c  pop     r15
0x180074e1e  pop     r14
0x180074e20  pop     r13
0x180074e22  pop     rdi
0x180074e23  pop     rsi
0x180074e24  pop     rbx
0x180074e25  pop     rbp
0x180074e26  retn
0x180074e27  btr     esi, 1Fh
0x180074e2b  mov     rcx, [rbp+57h+var_38]
0x180074e2f  mov     rax, [rcx]
0x180074e32  lea     r8, [rbp+57h+arg_18]
0x180074e36  mov     edx, esi
0x180074e38  mov     rax, [rax+18h]
0x180074e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e41  mov     edi, eax
0x180074e43  test    eax, eax
0x180074e45  jns     short loc_180074E74
0x180074e47  mov     eax, cs:dword_180128170
0x180074e4d  cmp     eax, 3
0x180074e50  jbe     loc_180074D6C
0x180074e56  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074e5d  mov     [rbp+57h+var_78], rax
0x180074e61  lea     rax, aFindsessionbyi; "FindSessionById"
0x180074e68  lea     rdx, byte_18010CBA1
0x180074e6f  jmp     loc_180074D31
0x180074e74  lea     r8, [rbp+57h+var_58]; struct ITSObjectStorage **
0x180074e78  mov     rcx, [rbp+57h+arg_18]; struct ITSSession *
0x180074e7c  call    ?GetStorageForSessionObject@CHelper@@SAJPEAUITSSession@@HPEAPEAVITSObjectStorage@@@Z; CHelper::GetStorageForSessionObject(ITSSession *,int,ITSObjectStorage * *)
0x180074e81  mov     edi, eax
0x180074e83  test    eax, eax
0x180074e85  jns     short loc_180074EB4
0x180074e87  mov     eax, cs:dword_180128170
0x180074e8d  cmp     eax, 3
0x180074e90  jbe     loc_180074D6C
0x180074e96  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074e9d  mov     [rbp+57h+var_78], rax
0x180074ea1  lea     rax, aGetstoragefors; "GetStorageForSessionObject"
0x180074ea8  lea     rdx, unk_18010CB58
0x180074eaf  jmp     loc_180074D31
0x180074eb4  mov     rcx, [rbp+57h+var_58]
0x180074eb8  mov     rax, [rcx]
0x180074ebb  lea     r8, [rbp+57h+var_40]
0x180074ebf  lea     rdx, ?IID_SessionKey@@3U_GUID@@B; _GUID const IID_SessionKey
0x180074ec6  mov     rax, [rax+20h]
0x180074eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ecf  mov     edi, eax
0x180074ed1  test    eax, eax
0x180074ed3  jns     short loc_180074F02
0x180074ed5  mov     eax, cs:dword_180128170
0x180074edb  cmp     eax, 3
0x180074ede  jbe     loc_180074D6C
0x180074ee4  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074eeb  mov     [rbp+57h+var_78], rax
0x180074eef  lea     rax, aPtrstorageGetI; "ptrStorage->Get(IID_SessionKey)"
0x180074ef6  lea     rdx, byte_18010CB0F
0x180074efd  jmp     loc_180074D31
0x180074f02  mov     rdx, [rbp+57h+var_40]
0x180074f06  lea     rcx, [rbp+57h+var_50]
0x180074f0a  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180074f0f  mov     rcx, [rbp+57h+var_50]; this
0x180074f13  call    ?IsExpired@CSessionKey@@QEBAHXZ; CSessionKey::IsExpired(void)
0x180074f18  test    eax, eax
0x180074f1a  jz      short loc_180074F51
0x180074f1c  mov     eax, cs:dword_180128170
0x180074f22  cmp     eax, 3
0x180074f25  jbe     short loc_180074F47
0x180074f27  lea     rax, aSessionKeyExpi; "Session key expired"
0x180074f2e  lea     rdx, qword_18010CAE0
0x180074f35  mov     [rbp+57h+arg_8], rax
0x180074f39  lea     rax, [rbp+57h+arg_8]
0x180074f3d  mov     [rsp+0C0h+var_A0], rax
0x180074f42  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180074f47  mov     edi, 80004001h
0x180074f4c  jmp     loc_180074D6C
0x180074f51  mov     rdx, rbx; struct CSessionKey *
0x180074f54  mov     rcx, [rbp+57h+var_50]; this
0x180074f58  call    ?Equals@CSessionKey@@QEBAHAEBV1@@Z; CSessionKey::Equals(CSessionKey const &)
0x180074f5d  test    eax, eax
0x180074f5f  jnz     short loc_180074F7C
0x180074f61  mov     eax, cs:dword_180128170
0x180074f67  cmp     eax, 3
0x180074f6a  jbe     short loc_180074F47
0x180074f6c  lea     rax, aSessionKeyDoes; "Session key does not match"
0x180074f73  lea     rdx, byte_18010CAB1
0x180074f7a  jmp     short loc_180074F35
0x180074f7c  mov     rcx, [rbp+57h+var_58]
0x180074f80  mov     rax, [rcx]
0x180074f83  lea     rdx, ?IID_SessionKey@@3U_GUID@@B; _GUID const IID_SessionKey
0x180074f8a  mov     rax, [rax+28h]
0x180074f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f93  mov     edi, eax
0x180074f95  test    eax, eax
0x180074f97  jns     short loc_180074FC6
0x180074f99  mov     eax, cs:dword_180128170
0x180074f9f  cmp     eax, 3
0x180074fa2  jbe     loc_180074D6C
0x180074fa8  lea     rax, aAttemptsdredir_0; "AttemptSDRedirectReconnect"
0x180074faf  mov     [rbp+57h+var_78], rax
0x180074fb3  lea     rax, aPtrstorageRemo_1; "ptrStorage->Remove"
0x180074fba  lea     rdx, unk_18010CA68
0x180074fc1  jmp     loc_180074D31
0x180074fc6  mov     rcx, [rbp+57h+arg_18]
0x180074fca  mov     rax, [rcx]
0x180074fcd  lea     rdx, [rbp+57h+arg_0]
  ... truncated ...
```
