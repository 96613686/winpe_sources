# HTTP_USER_REQUEST::_OnAsyncReadData(PENDING_API_CALL *,ulong,ulong)

- ea: `0x180035500`
- end: `0x1800359c7`
- name: `?_OnAsyncReadData@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KK@Z`
- size: `1223`
- prototype: `void __fastcall(HTTP_USER_REQUEST *this, struct PENDING_API_CALL *, int, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180096720`

## callees

- `0x180010f50`
- `0x1800250ec`
- `0x180026680`
- `0x18002e6e8`
- `0x1800354c0`
- `0x180035500`
- `0x1800364d0`
- `0x180036644`
- `0x180036970`
- `0x1800460c4`
- `0x180090610`
- `0x1800a1d10`
- `0x1800b7d40`
- `0x1800d4f90`
- `0x1800d58c0`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035572`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003571b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035572`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003571b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035818`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035818`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035828`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035828`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800357dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800357dd`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800356c3`
- `webio!__imp_WebQueryHttpRequestOption` at `0x1800356c3`

## pseudocode

```c
void __fastcall HTTP_USER_REQUEST::_OnAsyncReadData(
        HTTP_USER_REQUEST *this,
        struct PENDING_API_CALL *a2,
        int a3,
        int a4)
{
  __int64 v4; // r13
  struct _RTL_CRITICAL_SECTION *v5; // r12
  __int64 v10; // rdx
  WEBIO_REQUEST *v11; // rcx
  int v12; // r8d
  int v13; // r14d
  __int64 v14; // rcx
  struct _GUID *v15; // rax
  __int64 v16; // rdx
  struct _GUID *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  void (__fastcall *v20)(__int64, __int64, __int64, int *, int); // rax
  __int64 v21; // rcx
  int v22; // ebx
  void *v23; // rcx
  unsigned int StreamErrorCode; // eax
  int HeaderWithToken; // eax
  unsigned int v26[2]; // [rsp+20h] [rbp-49h]
  _BYTE v27[8]; // [rsp+40h] [rbp-29h] BYREF
  int v28[2]; // [rsp+48h] [rbp-21h] BYREF
  struct _GUID v29; // [rsp+50h] [rbp-19h] BYREF
  struct _GUID v30; // [rsp+60h] [rbp-9h] BYREF
  int v31; // [rsp+70h] [rbp+7h]
  __int128 v32; // [rsp+78h] [rbp+Fh]

  v4 = *((_QWORD *)a2 + 16);
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 240);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
  if ( *((_DWORD *)a2 + 7) )
  {
    if ( *((_DWORD *)a2 + 7) == 1 )
    {
      *((_DWORD *)this + 14) = 5;
      a3 = 12017;
    }
  }
  else
  {
    *((_DWORD *)a2 + 7) = 2;
  }
  (**(void (__fastcall ***)(struct PENDING_API_CALL *))a2)(a2);
  LeaveCriticalSection(v5);
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_q(1025, 76, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
  if ( a3 == 12030 && *((_DWORD *)this + 2671) )
  {
    StreamErrorCode = WEBIO_REQUEST::GetStreamErrorCode(*((WEBIO_REQUEST **)a2 + 16), (unsigned __int64 *)this + 1336);
    if ( StreamErrorCode && (xmmword_180107A60 & 2) != 0 )
      WPP_SF_d(1025, 78, WPP_29ecff532d3a35783d73db4432e82274_Traceguids, StreamErrorCode, *(_QWORD *)v26);
    *((_DWORD *)this + 2674) = 1;
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_iq((_DWORD)v11, v10, v12, *((_QWORD *)this + 1336), (__int64)this);
    goto LABEL_9;
  }
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_q(1025, 77, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
  v28[0] = 0;
  v13 = 12152;
  if ( a3 != 12152 )
  {
LABEL_9:
    v13 = a3;
    if ( a3 )
      goto LABEL_23;
    goto LABEL_10;
  }
  if ( CWebIOResponseHeadersShim::IsHeaderPresent((HTTP_USER_REQUEST *)((char *)this + 120), v10, v28) )
  {
    v13 = 12004;
    goto LABEL_23;
  }
  *(_DWORD *)v29.Data4 = 7;
  *(_QWORD *)&v29.Data1 = "chunked";
  HeaderWithToken = CWebIOResponseHeadersShim::FindHeaderWithToken((char *)this + 120, v10, &v29);
  if ( v28[0] && !HeaderWithToken )
  {
    *((_DWORD *)this + 21) = 1;
    a4 = 0;
    HTTP_USER_REQUEST::_SafeDetachSysReq(this);
    v13 = 0;
LABEL_10:
    if ( (*((_BYTE *)a2 + 56) & 0xC0) != 0 )
    {
      v28[0] = a4;
      v31 = 0;
      v30 = 0;
      if ( !*((_DWORD *)a2 + 10) || (v22 = *((_DWORD *)a2 + 11), GetCurrentThreadId() == v22) )
      {
        v14 = 16;
        v15 = &v30;
        v16 = 16;
        do
        {
          LOBYTE(v15->Data1) = 0;
          v15 = (struct _GUID *)((char *)v15 + 1);
          --v16;
        }
        while ( v16 );
        v31 = 0;
        v17 = &v30;
        v32 = 0;
        v29 = 0;
        do
        {
          LOBYTE(v17->Data1) = 0;
          v17 = (struct _GUID *)((char *)v17 + 1);
          --v14;
        }
        while ( v14 );
        WxEtwGetActivityId(&v29);
        WxEtwSetActivityId(&WinHttpEtwNullActivityId);
        v18 = *((_QWORD *)a2 + 8);
        v19 = *((_QWORD *)this + 4);
        v20 = (void (__fastcall *)(__int64, __int64, __int64, int *, int))*((_QWORD *)a2 + 6);
        v30 = v29;
        v31 = 1;
        v20(v19, v18, 128, v28, 4);
        if ( v31 )
          WxEtwSetActivityId(&v30);
      }
      else
      {
        v23 = (void *)*((_QWORD *)a2 + 9);
        *((_QWORD *)a2 + 19) = v28;
        *((_DWORD *)a2 + 35) = 1;
        *((_DWORD *)a2 + 36) = 128;
        *((_DWORD *)a2 + 40) = 4;
        SetEvent(v23);
        WaitForSingleObjectEx(*((HANDLE *)a2 + 10), 0xFFFFFFFF, 0);
        *(_QWORD *)((char *)a2 + 140) = 0;
        *((_QWORD *)a2 + 19) = 0;
        *((_DWORD *)a2 + 40) = 0;
      }
    }
    v11 = (WEBIO_REQUEST *)*((_QWORD *)a2 + 16);
    if ( *((_DWORD *)v11 + 181) )
    {
      WEBIO_REQUEST::GetRequestTimes(v11, (HTTP_USER_REQUEST *)((char *)this + 9048));
      WEBIO_REQUEST::GetRequestStats(*((WEBIO_REQUEST **)a2 + 16), (HTTP_USER_REQUEST *)((char *)this + 9584));
      v21 = *((_QWORD *)a2 + 16);
      v27[0] = 0;
      *(_QWORD *)v28 = 0;
      if ( !(unsigned int)WebQueryHttpRequestOption(*(_QWORD *)(v21 + 184), 16391, v27, 1, v28)
        && v27[0]
        && (*((_DWORD *)a2 + 14) & 0x300) != 0 )
      {
        HTTP_USER_REQUEST::_IndicateInformational(this, a2, 0x100u, 0, 0);
        HTTP_USER_REQUEST::_IndicateInformational(this, a2, 0x200u, 0, 0);
      }
    }
    if ( *(_DWORD *)(*((_QWORD *)a2 + 16) + 724LL) )
      *((_DWORD *)this + 21) = 1;
  }
LABEL_23:
  if ( (xmmword_180107A60 & 2) != 0 )
    WPP_SF_qqdd((_DWORD)v11, v10, v12, (_DWORD)this, *((_QWORD *)a2 + 14));
  EnterCriticalSection(v5);
  *((_QWORD *)this + 36) = 0;
  (*(void (__fastcall **)(struct PENDING_API_CALL *))(*(_QWORD *)a2 + 8LL))(a2);
  LeaveCriticalSection(v5);
  *((_DWORD *)a2 + 8) = v13;
  if ( v13 )
  {
    HTTP_USER_REQUEST::_TransitToState(this, 5);
    HTTP_USER_REQUEST::_SafeDetachSysReq(this);
  }
  else
  {
    *((_DWORD *)a2 + 31) += a4;
    *((_DWORD *)a2 + 9) = *((_DWORD *)a2 + 31);
    *((_DWORD *)a2 + 34) = *(_DWORD *)(v4 + 724);
  }
  HTTP_USER_REQUEST::_IndicateIoCompletion((HTTP_REQUEST_HANDLE_OBJECT **)this, a2, *((_DWORD *)a2 + 8));
  (*(void (__fastcall **)(struct PENDING_API_CALL *))(*(_QWORD *)a2 + 8LL))(a2);
}

```

## disassembly

```asm
0x180035500  mov     [rsp-8+arg_10], rbx
0x180035505  push    rbp
0x180035506  push    rsi
0x180035507  push    rdi
0x180035508  push    r12
0x18003550a  push    r13
0x18003550c  push    r14
0x18003550e  push    r15
0x180035510  lea     rbp, [rsp-27h]
0x180035515  sub     rsp, 90h
0x18003551c  mov     rax, cs:__security_cookie
0x180035523  xor     rax, rsp
0x180035526  mov     [rbp+57h+var_38], rax
0x18003552a  mov     r13, [rdx+80h]
0x180035531  lea     r12, [rcx+0F0h]
0x180035538  mov     rsi, rcx
0x18003553b  mov     r15d, r9d
0x18003553e  mov     rcx, r12; lpCriticalSection
0x180035541  mov     ebx, r8d
0x180035544  mov     rdi, rdx
0x180035547  call    cs:__imp_EnterCriticalSection
0x18003554d  xor     r14d, r14d
0x180035550  cmp     [rdi+1Ch], r14d
0x180035554  jnz     loc_180035849
0x18003555a  mov     dword ptr [rdi+1Ch], 2
0x180035561  mov     rax, [rdi]
0x180035564  mov     rcx, rdi
0x180035567  mov     rax, [rax]
0x18003556a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003556f  mov     rcx, r12; lpCriticalSection
0x180035572  call    cs:__imp_LeaveCriticalSection
0x180035578  test    byte ptr cs:xmmword_180107A60, 2
0x18003557f  jnz     loc_1800358D6
0x180035585  cmp     ebx, 2EFEh
0x18003558b  jz      loc_180035864
0x180035591  test    byte ptr cs:xmmword_180107A60, 2
0x180035598  jnz     loc_1800358F4
0x18003559e  mov     [rbp+57h+var_78], r14d
0x1800355a2  mov     r14d, 2F78h
0x1800355a8  cmp     ebx, r14d
0x1800355ab  jz      loc_180035912
0x1800355b1  mov     r14d, ebx
0x1800355b4  test    ebx, ebx
0x1800355b6  jnz     loc_180035929
0x1800355bc  xor     ebx, ebx
0x1800355be  test    byte ptr [rdi+38h], 0C0h
0x1800355c2  jz      loc_180035668
0x1800355c8  xor     eax, eax
0x1800355ca  mov     [rbp+57h+var_78], r15d
0x1800355ce  xorps   xmm0, xmm0
0x1800355d1  mov     [rbp+57h+var_50], eax
0x1800355d4  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800355d8  cmp     [rdi+28h], ebx
0x1800355db  jnz     loc_1800357DA
0x1800355e1  mov     ecx, 10h
0x1800355e6  lea     rax, [rbp+57h+var_60]
0x1800355ea  mov     edx, ecx
0x1800355ec  mov     [rax], bl
0x1800355ee  inc     rax
0x1800355f1  sub     rdx, 1
0x1800355f5  jnz     short loc_1800355EC
0x1800355f7  xorps   xmm0, xmm0
0x1800355fa  mov     [rbp+57h+var_50], ebx
0x1800355fd  xorps   xmm1, xmm1
0x180035600  lea     rax, [rbp+57h+var_60]
0x180035604  movups  [rbp+57h+var_48], xmm0
0x180035608  movups  xmmword ptr [rbp+57h+var_70.Data1], xmm1
0x18003560c  mov     [rax], bl
0x18003560e  inc     rax
0x180035611  sub     rcx, 1
0x180035615  jnz     short loc_18003560C
0x180035617  lea     rcx, [rbp+57h+var_70]; struct _GUID *
0x18003561b  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180035620  lea     rcx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; struct _GUID *
0x180035627  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x18003562c  movups  xmm0, xmmword ptr [rbp+57h+var_70.Data1]
0x180035630  mov     rdx, [rdi+40h]
0x180035634  lea     r9, [rbp+57h+var_78]
0x180035638  mov     rcx, [rsi+20h]
0x18003563c  mov     r8d, 80h
0x180035642  mov     rax, [rdi+30h]
0x180035646  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18003564b  mov     [rbp+57h+var_50], 1
0x180035652  mov     [rsp+0C0h+var_A0], 4
0x18003565a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003565f  cmp     [rbp+57h+var_50], ebx
0x180035662  jnz     loc_1800357CC
0x180035668  mov     rcx, [rdi+80h]; this
0x18003566f  cmp     [rcx+2D4h], ebx
0x180035675  jz      short loc_1800356D6
0x180035677  lea     rdx, [rsi+2358h]; struct _WINHTTP_REQUEST_TIMES *
0x18003567e  call    ?GetRequestTimes@WEBIO_REQUEST@@QEAAKPEAU_WINHTTP_REQUEST_TIMES@@@Z; WEBIO_REQUEST::GetRequestTimes(_WINHTTP_REQUEST_TIMES *)
0x180035683  mov     rcx, [rdi+80h]; this
0x18003568a  lea     rdx, [rsi+2570h]; struct _WINHTTP_REQUEST_STATS *
0x180035691  call    ?GetRequestStats@WEBIO_REQUEST@@QEAAKPEAU_WINHTTP_REQUEST_STATS@@@Z; WEBIO_REQUEST::GetRequestStats(_WINHTTP_REQUEST_STATS *)
0x180035696  mov     rcx, [rdi+80h]
0x18003569d  lea     rax, [rbp+57h+var_78]
0x1800356a1  mov     r9d, 1
0x1800356a7  mov     [rbp+57h+var_80], bl
0x1800356aa  lea     r8, [rbp+57h+var_80]
0x1800356ae  mov     qword ptr [rbp+57h+var_78], rbx
0x1800356b2  mov     edx, 4007h
0x1800356b7  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800356bc  mov     rcx, [rcx+0B8h]
0x1800356c3  call    cs:__imp_WebQueryHttpRequestOption
0x1800356c9  test    eax, eax
0x1800356cb  jnz     short loc_1800356D6
0x1800356cd  cmp     [rbp+57h+var_80], bl
0x1800356d0  jnz     loc_18003578A
0x1800356d6  mov     rax, [rdi+80h]
0x1800356dd  cmp     [rax+2D4h], ebx
0x1800356e3  jz      short loc_1800356EC
0x1800356e5  mov     dword ptr [rsi+54h], 1
0x1800356ec  test    byte ptr cs:xmmword_180107A60, 2
0x1800356f3  jnz     loc_180035989
0x1800356f9  mov     rcx, r12; lpCriticalSection
0x1800356fc  call    cs:__imp_EnterCriticalSection
0x180035702  mov     [rsi+120h], rbx
0x180035709  mov     rcx, rdi
0x18003570c  mov     rax, [rdi]
0x18003570f  mov     rax, [rax+8]
0x180035713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035718  mov     rcx, r12; lpCriticalSection
0x18003571b  call    cs:__imp_LeaveCriticalSection
0x180035721  mov     [rdi+20h], r14d
0x180035725  test    r14d, r14d
0x180035728  jnz     loc_1800359AD
0x18003572e  add     [rdi+7Ch], r15d
0x180035732  mov     eax, [rdi+7Ch]
0x180035735  mov     [rdi+24h], eax
0x180035738  mov     eax, [r13+2D4h]
0x18003573f  mov     [rdi+88h], eax
0x180035745  mov     r8d, [rdi+20h]; unsigned int
0x180035749  mov     rdx, rdi; struct PENDING_API_CALL *
0x18003574c  mov     rcx, rsi; this
0x18003574f  call    ?_IndicateIoCompletion@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@K@Z; HTTP_USER_REQUEST::_IndicateIoCompletion(PENDING_API_CALL *,ulong)
0x180035754  mov     rax, [rdi]
0x180035757  mov     rcx, rdi
0x18003575a  mov     rax, [rax+8]
0x18003575e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035763  mov     rcx, [rbp+57h+var_38]
0x180035767  xor     rcx, rsp; StackCookie
0x18003576a  call    __security_check_cookie
0x18003576f  mov     rbx, [rsp+0C0h+arg_10]
0x180035777  add     rsp, 90h
0x18003577e  pop     r15
0x180035780  pop     r14
0x180035782  pop     r13
0x180035784  pop     r12
0x180035786  pop     rdi
0x180035787  pop     rsi
0x180035788  pop     rbp
0x180035789  retn
0x18003578a  test    dword ptr [rdi+38h], 300h
0x180035791  jz      loc_1800356D6
0x180035797  xor     r9d, r9d; void *
0x18003579a  mov     [rsp+0C0h+var_A0], ebx; unsigned int
0x18003579e  mov     r8d, 100h; unsigned int
0x1800357a4  mov     rdx, rdi; struct PENDING_API_CALL *
0x1800357a7  mov     rcx, rsi; this
0x1800357aa  call    ?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z; HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)
0x1800357af  xor     r9d, r9d; void *
0x1800357b2  mov     [rsp+0C0h+var_A0], ebx; unsigned int
0x1800357b6  mov     r8d, 200h; unsigned int
0x1800357bc  mov     rdx, rdi; struct PENDING_API_CALL *
0x1800357bf  mov     rcx, rsi; this
0x1800357c2  call    ?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z; HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)
0x1800357c7  jmp     loc_1800356D6
0x1800357cc  lea     rcx, [rbp+57h+var_60]; struct _GUID *
0x1800357d0  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x1800357d5  jmp     loc_180035668
0x1800357da  mov     ebx, [rdi+2Ch]
0x1800357dd  call    cs:__imp_GetCurrentThreadId
0x1800357e3  cmp     eax, ebx
0x1800357e5  jz      loc_180035982
0x1800357eb  mov     rcx, [rdi+48h]; hEvent
0x1800357ef  lea     rax, [rbp+57h+var_78]
0x1800357f3  mov     [rdi+98h], rax
0x1800357fa  mov     dword ptr [rdi+8Ch], 1
0x180035804  mov     dword ptr [rdi+90h], 80h
0x18003580e  mov     dword ptr [rdi+0A0h], 4
0x180035818  call    cs:__imp_SetEvent
0x18003581e  mov     rcx, [rdi+50h]; hHandle
0x180035822  xor     r8d, r8d; bAlertable
0x180035825  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035828  call    cs:__imp_WaitForSingleObjectEx
0x18003582e  xor     ebx, ebx
0x180035830  mov     [rdi+8Ch], rbx
0x180035837  mov     [rdi+98h], rbx
0x18003583e  mov     [rdi+0A0h], ebx
0x180035844  jmp     loc_180035668
0x180035849  cmp     dword ptr [rdi+1Ch], 1
0x18003584d  jnz     loc_180035561
0x180035853  mov     dword ptr [rsi+38h], 5
0x18003585a  mov     ebx, 2EF1h
0x18003585f  jmp     loc_180035561
0x180035864  cmp     [rsi+29BCh], r14d
0x18003586b  jz      loc_180035591
0x180035871  mov     rcx, [rdi+80h]; this
0x180035878  lea     r14, [rsi+29C0h]
0x18003587f  mov     rdx, r14; unsigned __int64 *
0x180035882  call    ?GetStreamErrorCode@WEBIO_REQUEST@@QEAAKPEA_K@Z; WEBIO_REQUEST::GetStreamErrorCode(unsigned __int64 *)
0x180035887  test    eax, eax
0x180035889  jz      short loc_1800358AD
0x18003588b  test    byte ptr cs:xmmword_180107A60, 2
0x180035892  jz      short loc_1800358AD
0x180035894  mov     edx, 4Eh ; 'N'
0x180035899  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x1800358a0  mov     ecx, 401h
0x1800358a5  mov     r9d, eax
0x1800358a8  call    WPP_SF_d
0x1800358ad  mov     dword ptr [rsi+29C8h], 1
0x1800358b7  test    byte ptr cs:xmmword_180107A60, 2
0x1800358be  jz      loc_1800355B1
0x1800358c4  mov     r9, [r14]
0x1800358c7  mov     qword ptr [rsp+0C0h+var_A0], rsi
0x1800358cc  call    WPP_SF_iq
0x1800358d1  jmp     loc_1800355B1
0x1800358d6  mov     edx, 4Ch ; 'L'
0x1800358db  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x1800358e2  mov     ecx, 401h
0x1800358e7  mov     r9, rsi
0x1800358ea  call    WPP_SF_q
0x1800358ef  jmp     loc_180035585
0x1800358f4  mov     edx, 4Dh ; 'M'
0x1800358f9  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180035900  mov     ecx, 401h
0x180035905  mov     r9, rsi
0x180035908  call    WPP_SF_q
0x18003590d  jmp     loc_18003559E
0x180035912  lea     r8, [rbp+57h+var_78]; int *
0x180035916  lea     rcx, [rsi+78h]; this
0x18003591a  call    ?IsHeaderPresent@CWebIOResponseHeadersShim@@QEAAKKPEAH@Z; CWebIOResponseHeadersShim::IsHeaderPresent(ulong,int *)
0x18003591f  test    eax, eax
0x180035921  jz      short loc_180035930
0x180035923  mov     r14d, 2EE4h
0x180035929  xor     ebx, ebx
0x18003592b  jmp     loc_1800356EC
0x180035930  lea     rax, aChunked; "chunked"
0x180035937  mov     dword ptr [rbp+57h+var_70.Data4], 7
0x18003593e  mov     qword ptr [rbp+57h+var_70.Data1], rax
0x180035942  lea     r8, [rbp+57h+var_70]
0x180035946  mov     eax, dword ptr [rbp+57h+var_70.Data4+4]
0x180035949  lea     rcx, [rsi+78h]
0x18003594d  mov     dword ptr [rbp+57h+var_70.Data4+4], eax
0x180035950  call    ?FindHeaderWithToken@CWebIOResponseHeadersShim@@QEBAHKU?$string@D@@@Z; CWebIOResponseHeadersShim::FindHeaderWithToken(ulong,string<char>)
0x180035955  xor     ebx, ebx
0x180035957  cmp     [rbp+57h+var_78], ebx
0x18003595a  jz      loc_1800356EC
0x180035960  test    eax, eax
0x180035962  jnz     loc_1800356EC
0x180035968  mov     rcx, rsi; this
0x18003596b  mov     dword ptr [rsi+54h], 1
0x180035972  mov     r15d, ebx
0x180035975  call    ?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_SafeDetachSysReq(void)
0x18003597a  mov     r14d, ebx
0x18003597d  jmp     loc_1800355BE
0x180035982  xor     ebx, ebx
0x180035984  jmp     loc_1800355E1
0x180035989  mov     eax, [rdi+7Ch]
0x18003598c  mov     r9, rsi
0x18003598f  mov     [rsp+0C0h+var_90], eax
0x180035993  mov     eax, [rdi+78h]
0x180035996  mov     [rsp+0C0h+var_98], eax
0x18003599a  mov     rax, [rdi+70h]
0x18003599e  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800359a3  call    WPP_SF_qqdd
0x1800359a8  jmp     loc_1800356F9
0x1800359ad  mov     edx, 5
0x1800359b2  mov     rcx, rsi
0x1800359b5  call    ?_TransitToState@HTTP_USER_REQUEST@@AEAAXW4_STATE@1@@Z; HTTP_USER_REQUEST::_TransitToState(HTTP_USER_REQUEST::_STATE)
0x1800359ba  mov     rcx, rsi; this
0x1800359bd  call    ?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_SafeDetachSysReq(void)
0x1800359c2  jmp     loc_180035745
```
