# HTTP_USER_REQUEST::_SysSendRequest(PENDING_API_CALL *,CAuthData *,CAuthData *,void *)

- ea: `0x18002e7ec`
- end: `0x18002ecb9`
- name: `?_SysSendRequest@HTTP_USER_REQUEST@@AEAAKPEAVPENDING_API_CALL@@PEAUCAuthData@@1PEAX@Z`
- size: `1229`
- prototype: `__int64 __fastcall(struct HANDLE_OBJECT **this, struct PENDING_API_CALL *, struct CAuthData *, struct CAuthData *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18002fd0c`

## callees

- `0x1800250ec`
- `0x1800252ac`
- `0x180029d50`
- `0x18002d250`
- `0x18002d9c8`
- `0x18002daa4`
- `0x18002dfc0`
- `0x18002e6e8`
- `0x18002e7ec`
- `0x180031490`
- `0x180033ac0`
- `0x180039120`
- `0x18004aa40`
- `0x180081ef4`
- `0x180086f10`
- `0x18009b960`
- `0x18009c93c`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e8d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e973`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e8d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e973`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e934`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea13`
- `webio!__imp_WebRemoveHttpRequestInformationRoutine` at `0x18002e9df`
- `webio!__imp_WebRemoveHttpRequestInformationRoutine` at `0x18002e9df`

## string_xrefs

- `0x18002e882`: `no-cache`
- `0x18002e8ba`: `no-cache`

## pseudocode

```c
__int64 __fastcall HTTP_USER_REQUEST::_SysSendRequest(
        struct HANDLE_OBJECT **this,
        struct PENDING_API_CALL *a2,
        struct CAuthData *a3,
        struct CAuthData *a4,
        void *a5)
{
  HTTP_USER_REQUEST *v5; // rbx
  struct HANDLE_OBJECT *v6; // rcx
  WEBIO_REQUEST *v7; // rsi
  struct PENDING_API_CALL *v8; // rdi
  __int64 v9; // rcx
  CWebIORequestHeadersShim *v10; // rcx
  unsigned int v11; // edi
  WEBIO_REQUEST *v12; // rcx
  _DWORD *v13; // r14
  WEBIO_REQUEST **v14; // rsi
  int v15; // r15d
  WEBIO_REQUEST *v16; // rcx
  struct HANDLE_OBJECT *v17; // rax
  HTTP_USER_REQUEST *v18; // rcx
  WEBIO_REQUEST *v19; // rcx
  struct HANDLE_OBJECT *v20; // rcx
  HANDLE_OBJECT *RootHandle; // rax
  struct HANDLE_OBJECT *v22; // rcx
  HTTP_REQUEST_HANDLE_OBJECT *v23; // rcx
  int v24; // eax
  unsigned __int64 v25; // r15
  unsigned int v26; // r12d
  unsigned __int8 *v27; // r13
  unsigned int DwordOption; // r14d
  HTTP_REQUEST_HANDLE_OBJECT *v29; // rcx
  unsigned int v30; // eax
  _DWORD *v31; // rcx
  int v32; // ebp
  unsigned int v33; // r8d
  unsigned __int16 *v34; // rdi
  unsigned int v35; // esi
  int v36; // ecx
  unsigned int v37; // ebx
  int v38; // eax
  int v39; // eax
  int v41; // [rsp+90h] [rbp-78h]
  int v42; // [rsp+94h] [rbp-74h]
  int v43; // [rsp+98h] [rbp-70h]
  WEBIO_REQUEST *v44; // [rsp+A0h] [rbp-68h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v45; // [rsp+A8h] [rbp-60h]
  WEBIO_REQUEST *v46; // [rsp+B0h] [rbp-58h]

  v5 = (HTTP_USER_REQUEST *)this;
  v6 = this[4];
  v7 = 0;
  v44 = 0;
  v8 = a2;
  if ( !*((_DWORD *)GetRootHandle(v6) + 92) && *((_QWORD *)v5 + 1087) )
  {
    HTTP_USER_REQUEST::_TweenerFinishLogon(v5);
    HTTP_USER_REQUEST::_TweenerClose(v5);
  }
  v9 = *((_QWORD *)v5 + 4);
  if ( (*(_DWORD *)(v9 + 672) & 0x100) != 0 )
  {
    if ( !(unsigned int)CWebIORequestHeadersShim::IsHeaderPresent((CWebIORequestHeadersShim *)(v9 + 680), 0x31u) )
      CWebIORequestHeadersShim::SetHeader(
        (CWebIORequestHeadersShim *)(*((_QWORD *)v5 + 4) + 680LL),
        0x31u,
        "no-cache",
        8u);
    if ( (unsigned int)CRequestParameters::IsRequest1_1((CRequestParameters *)(*((_QWORD *)v5 + 4) + 680LL))
      && !(unsigned int)CWebIORequestHeadersShim::IsHeaderPresent(v10, 0x11u) )
    {
      CWebIORequestHeadersShim::SetHeader(
        (CWebIORequestHeadersShim *)(*((_QWORD *)v5 + 4) + 680LL),
        0x11u,
        "no-cache",
        8u);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v5 + 6);
  if ( *((_DWORD *)v5 + 15) )
  {
    v11 = 0;
LABEL_22:
    *((_DWORD *)v5 + 14) = 5;
    LeaveCriticalSection((LPCRITICAL_SECTION)v5 + 6);
LABEL_23:
    if ( v7 )
    {
      WEBIO_REQUEST::CancelRequest(v7, 0x2EF1u);
      WebRemoveHttpRequestInformationRoutine(*((_QWORD *)v7 + 23), 0);
      v17 = *(struct HANDLE_OBJECT **)v7;
      v18 = v7;
LABEL_47:
      (*((void (__fastcall **)(HTTP_USER_REQUEST *))v17 + 1))(v18);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  v12 = (WEBIO_REQUEST *)*((_QWORD *)v5 + 24);
  v13 = (_DWORD *)((char *)v5 + 200);
  v14 = (WEBIO_REQUEST **)((char *)v8 + 128);
  if ( v12 )
  {
    v15 = 0;
    *v13 = 0;
    WEBIO_REQUEST::ReInitialize(v12);
    v16 = (WEBIO_REQUEST *)*((_QWORD *)v5 + 24);
    *v14 = v16;
    (**(void (__fastcall ***)(WEBIO_REQUEST *))v16)(v16);
  }
  else
  {
    v15 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v5 + 6);
  if ( v15 )
  {
    v11 = HTTP_USER_REQUEST::_CreateWebioRequest(v5, &v44);
    if ( v11 )
    {
      HTTP_USER_REQUEST::_TransitToState(v5, 5);
      v7 = v44;
      goto LABEL_23;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)v5 + 6);
    if ( *((_DWORD *)v5 + 15) )
    {
      if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
        WPP_SF_q(769, 60, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
      v7 = v44;
      goto LABEL_22;
    }
    v19 = v44;
    *((_QWORD *)v5 + 24) = v44;
    *v14 = v19;
    (**(void (__fastcall ***)(WEBIO_REQUEST *))v19)(v19);
    *v13 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v5 + 6);
    v8 = a2;
  }
  v20 = (struct HANDLE_OBJECT *)*((_QWORD *)v5 + 4);
  *((_DWORD *)v5 + 57) = 0;
  if ( (*((_DWORD *)v20 + 168) & 0xA00) != 0 || *((_DWORD *)v8 + 24) != *((_QWORD *)v8 + 13) )
  {
    *((_DWORD *)v5 + 2136) = 0;
  }
  else
  {
    *((_DWORD *)v5 + 2136) = 1;
    *((_QWORD *)v5 + 1069) = *((_QWORD *)v8 + 11);
    *((_DWORD *)v5 + 2140) = *((_DWORD *)v8 + 24);
    *((_QWORD *)v5 + 1071) = *((_QWORD *)v8 + 13);
  }
  RootHandle = GetRootHandle(v20);
  if ( (unsigned int)HANDLE_OBJECT::IsInvalidated(RootHandle) )
  {
    if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
      WPP_SF_q(769, 61, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    HTTP_USER_REQUEST::_TransitToState(v5, 5);
    v11 = 12017;
    goto LABEL_50;
  }
  (**(void (__fastcall ***)(HTTP_USER_REQUEST *))v5)(v5);
  HTTP_USER_REQUEST::_TransitToState(v5, 2);
  v22 = (struct HANDLE_OBJECT *)*((_QWORD *)v5 + 4);
  if ( (*((_DWORD *)v22 + 168) & 0x40000) != 0
    || *((_DWORD *)v5 + 2664)
    || (v42 = 0, *((_DWORD *)GetRootHandle(v22) + 151)) )
  {
    v42 = 1;
  }
  v23 = (HTTP_REQUEST_HANDLE_OBJECT *)*((_QWORD *)v5 + 4);
  v46 = *v14;
  v43 = *((_DWORD *)v5 + 2675);
  v24 = (*((_DWORD *)v23 + 168) >> 9) & 1;
  v45 = v23;
  LODWORD(v44) = v24;
  if ( *((_DWORD *)v5 + 2656) || (v41 = 0, *((_DWORD *)v5 + 2662)) )
    v41 = 1;
  v25 = *((_QWORD *)v8 + 13);
  v26 = *((_DWORD *)v8 + 24);
  v27 = (unsigned __int8 *)*((_QWORD *)v8 + 11);
  DwordOption = HTTP_REQUEST_HANDLE_OBJECT::GetDwordOption(v23, 6u);
  v30 = HTTP_REQUEST_HANDLE_OBJECT::GetDwordOption(v29, 5u);
  v32 = v31[104];
  v33 = v31[240];
  v34 = (unsigned __int16 *)*((_QWORD *)v5 + 13);
  v35 = v30;
  v36 = v31[243];
  if ( !v32 )
    v32 = 1;
  v37 = v33 | 4;
  if ( (v36 & 1) != 0 )
    v37 = v33;
  v38 = HTTP_USER_REQUEST::_AutoLogonAllowed((HTTP_USER_REQUEST *)this, 1u);
  v39 = WEBIO_REQUEST::SendRequest(
          v46,
          v42,
          a3,
          v38,
          a4,
          v37,
          (HTTP_REQUEST_HANDLE_OBJECT *)((char *)v45 + 680),
          v34,
          a5,
          v32,
          v35,
          DwordOption,
          v27,
          v26,
          v25,
          v41,
          (int)v44,
          v43);
  v5 = (HTTP_USER_REQUEST *)this;
  v11 = v39;
  if ( v39 != 997 )
  {
    HTTP_USER_REQUEST::_PostProcessSendRequest((HTTP_USER_REQUEST *)this, v39, a2);
    v17 = *this;
    v18 = (HTTP_USER_REQUEST *)this;
    goto LABEL_47;
  }
LABEL_48:
  if ( v11 && v11 != 997 )
LABEL_50:
    HTTP_USER_REQUEST::_SafeDetachSysReq((struct _RTL_CRITICAL_SECTION *)v5);
  return v11;
}

```

## disassembly

```asm
0x18002e7ec  mov     rax, rsp
0x18002e7ef  mov     [rax+20h], r9
0x18002e7f3  mov     [rax+18h], r8
0x18002e7f7  mov     [rax+10h], rdx
0x18002e7fb  mov     [rax+8], rcx
0x18002e7ff  push    rbx
0x18002e800  push    rbp
0x18002e801  push    rsi
0x18002e802  push    rdi
0x18002e803  push    r12
0x18002e805  push    r13
0x18002e807  push    r14
0x18002e809  push    r15
0x18002e80b  sub     rsp, 0C8h
0x18002e812  mov     rbx, rcx
0x18002e815  xor     r12d, r12d
0x18002e818  mov     rcx, [rcx+20h]; struct HANDLE_OBJECT *
0x18002e81c  mov     esi, r12d
0x18002e81f  mov     [rax-68h], r12
0x18002e823  mov     rdi, rdx
0x18002e826  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x18002e82b  cmp     [rax+170h], r12d
0x18002e832  jnz     short loc_18002E84D
0x18002e834  cmp     [rbx+21F8h], r12
0x18002e83b  jz      short loc_18002E84D
0x18002e83d  mov     rcx, rbx; this
0x18002e840  call    ?_TweenerFinishLogon@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_TweenerFinishLogon(void)
0x18002e845  mov     rcx, rbx; this
0x18002e848  call    ?_TweenerClose@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_TweenerClose(void)
0x18002e84d  mov     rcx, [rbx+20h]
0x18002e851  test    dword ptr [rcx+2A0h], 100h
0x18002e85b  jz      short loc_18002E8CE
0x18002e85d  mov     ebp, 31h ; '1'
0x18002e862  add     rcx, 2A8h; this
0x18002e869  mov     edx, ebp; unsigned int
0x18002e86b  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x18002e870  lea     r14d, [rbp-29h]
0x18002e874  mov     r15d, 2A8h
0x18002e87a  test    eax, eax
0x18002e87c  jnz     short loc_18002E896
0x18002e87e  mov     rcx, [rbx+20h]
0x18002e882  lea     r8, aNoCache; "no-cache"
0x18002e889  add     rcx, r15; this
0x18002e88c  mov     r9d, r14d; unsigned __int16
0x18002e88f  mov     edx, ebp; unsigned int
0x18002e891  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x18002e896  mov     rcx, [rbx+20h]
0x18002e89a  add     rcx, r15; this
0x18002e89d  call    ?IsRequest1_1@CRequestParameters@@QEBAHXZ; CRequestParameters::IsRequest1_1(void)
0x18002e8a2  test    eax, eax
0x18002e8a4  jz      short loc_18002E8CE
0x18002e8a6  mov     ebp, 11h
0x18002e8ab  mov     edx, ebp; unsigned int
0x18002e8ad  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x18002e8b2  test    eax, eax
0x18002e8b4  jnz     short loc_18002E8CE
0x18002e8b6  mov     rcx, [rbx+20h]
0x18002e8ba  lea     r8, aNoCache; "no-cache"
0x18002e8c1  add     rcx, r15; this
0x18002e8c4  mov     r9d, r14d; unsigned __int16
0x18002e8c7  mov     edx, ebp; unsigned int
0x18002e8c9  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x18002e8ce  lea     rbp, [rbx+0F0h]
0x18002e8d5  mov     rcx, rbp; lpCriticalSection
0x18002e8d8  call    cs:__imp_EnterCriticalSection
0x18002e8de  cmp     [rbx+3Ch], r12d
0x18002e8e2  jz      short loc_18002E8EC
0x18002e8e4  mov     edi, r12d
0x18002e8e7  jmp     loc_18002E9A9
0x18002e8ec  mov     rcx, [rbx+0C0h]; this
0x18002e8f3  lea     r14, [rbx+0C8h]
0x18002e8fa  lea     rsi, [rdi+80h]
0x18002e901  mov     r13d, 1
0x18002e907  test    rcx, rcx
0x18002e90a  jnz     short loc_18002E911
0x18002e90c  mov     r15d, r13d
0x18002e90f  jmp     short loc_18002E931
0x18002e911  mov     r15d, r12d
0x18002e914  mov     [r14], r12d
0x18002e917  call    ?ReInitialize@WEBIO_REQUEST@@QEAAXXZ; WEBIO_REQUEST::ReInitialize(void)
0x18002e91c  mov     rcx, [rbx+0C0h]
0x18002e923  mov     [rsi], rcx
0x18002e926  mov     rax, [rcx]
0x18002e929  mov     rax, [rax]
0x18002e92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e931  mov     rcx, rbp; lpCriticalSection
0x18002e934  call    cs:__imp_LeaveCriticalSection
0x18002e93a  test    r15d, r15d
0x18002e93d  jz      loc_18002EA21
0x18002e943  lea     rdx, [rsp+108h+var_68]; struct WEBIO_REQUEST **
0x18002e94b  mov     rcx, rbx; this
0x18002e94e  call    ?_CreateWebioRequest@HTTP_USER_REQUEST@@AEAAKPEAPEAVWEBIO_REQUEST@@@Z; HTTP_USER_REQUEST::_CreateWebioRequest(WEBIO_REQUEST * *)
0x18002e953  mov     edi, eax
0x18002e955  test    eax, eax
0x18002e957  jz      short loc_18002E970
0x18002e959  mov     edx, 5
0x18002e95e  mov     rcx, rbx
0x18002e961  call    ?_TransitToState@HTTP_USER_REQUEST@@AEAAXW4_STATE@1@@Z; HTTP_USER_REQUEST::_TransitToState(HTTP_USER_REQUEST::_STATE)
0x18002e966  mov     rsi, [rsp+108h+var_68]
0x18002e96e  jmp     short loc_18002E9C0
0x18002e970  mov     rcx, rbp; lpCriticalSection
0x18002e973  call    cs:__imp_EnterCriticalSection
0x18002e979  cmp     [rbx+3Ch], r12d
0x18002e97d  jz      short loc_18002E9F0
0x18002e97f  test    byte ptr cs:xmmword_180107A50+8, 2
0x18002e986  jz      short loc_18002E9A1
0x18002e988  mov     edx, 3Ch ; '<'
0x18002e98d  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x18002e994  mov     ecx, 301h
0x18002e999  mov     r9, rbx
0x18002e99c  call    WPP_SF_q
0x18002e9a1  mov     rsi, [rsp+108h+var_68]
0x18002e9a9  mov     eax, 38h ; '8'
0x18002e9ae  mov     rcx, rbx
0x18002e9b1  mov     rcx, rbp; lpCriticalSection
0x18002e9b4  lea     edx, [rax-33h]
0x18002e9b7  mov     [rbx+rax], edx
0x18002e9ba  call    cs:__imp_LeaveCriticalSection
0x18002e9c0  test    rsi, rsi
0x18002e9c3  jz      loc_18002EC8F
0x18002e9c9  mov     edx, 2EF1h; unsigned int
0x18002e9ce  mov     rcx, rsi; this
0x18002e9d1  call    ?CancelRequest@WEBIO_REQUEST@@QEAAXK@Z; WEBIO_REQUEST::CancelRequest(ulong)
0x18002e9d6  mov     rcx, [rsi+0B8h]
0x18002e9dd  xor     edx, edx
0x18002e9df  call    cs:__imp_WebRemoveHttpRequestInformationRoutine
0x18002e9e5  mov     rax, [rsi]
0x18002e9e8  mov     rcx, rsi
0x18002e9eb  jmp     loc_18002EC86
0x18002e9f0  mov     rcx, [rsp+108h+var_68]
0x18002e9f8  mov     [rbx+0C0h], rcx
0x18002e9ff  mov     [rsi], rcx
0x18002ea02  mov     rax, [rcx]
0x18002ea05  mov     rax, [rax]
0x18002ea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea0d  mov     rcx, rbp; lpCriticalSection
0x18002ea10  mov     [r14], r12d
0x18002ea13  call    cs:__imp_LeaveCriticalSection
0x18002ea19  mov     rdi, [rsp+108h+arg_8]
0x18002ea21  mov     rcx, [rbx+20h]; struct HANDLE_OBJECT *
0x18002ea25  mov     [rbx+0E4h], r12d
0x18002ea2c  test    dword ptr [rcx+2A0h], 0A00h
0x18002ea36  jnz     short loc_18002EA69
0x18002ea38  mov     eax, [rdi+60h]
0x18002ea3b  cmp     rax, [rdi+68h]
0x18002ea3f  jnz     short loc_18002EA69
0x18002ea41  mov     [rbx+2160h], r13d
0x18002ea48  mov     rax, [rdi+58h]
0x18002ea4c  mov     [rbx+2168h], rax
0x18002ea53  mov     eax, [rdi+60h]
0x18002ea56  mov     [rbx+2170h], eax
0x18002ea5c  mov     rax, [rdi+68h]
0x18002ea60  mov     [rbx+2178h], rax
0x18002ea67  jmp     short loc_18002EA70
0x18002ea69  mov     [rbx+2160h], r12d
0x18002ea70  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x18002ea75  mov     rcx, rax; this
0x18002ea78  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x18002ea7d  test    eax, eax
0x18002ea7f  jz      short loc_18002EABA
0x18002ea81  test    byte ptr cs:xmmword_180107A50+8, 2
0x18002ea88  jz      short loc_18002EAA3
0x18002ea8a  mov     edx, 3Dh ; '='
0x18002ea8f  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x18002ea96  mov     ecx, 301h
0x18002ea9b  mov     r9, rbx
0x18002ea9e  call    WPP_SF_q
0x18002eaa3  mov     edx, 5
0x18002eaa8  mov     rcx, rbx
0x18002eaab  call    ?_TransitToState@HTTP_USER_REQUEST@@AEAAXW4_STATE@1@@Z; HTTP_USER_REQUEST::_TransitToState(HTTP_USER_REQUEST::_STATE)
0x18002eab0  mov     edi, 2EF1h
0x18002eab5  jmp     loc_18002EC9B
0x18002eaba  mov     rax, [rbx]
0x18002eabd  mov     rcx, rbx
0x18002eac0  mov     rax, [rax]
0x18002eac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac8  mov     edx, 2
0x18002eacd  mov     rcx, rbx
0x18002ead0  call    ?_TransitToState@HTTP_USER_REQUEST@@AEAAXW4_STATE@1@@Z; HTTP_USER_REQUEST::_TransitToState(HTTP_USER_REQUEST::_STATE)
0x18002ead5  mov     rcx, [rbx+20h]; struct HANDLE_OBJECT *
0x18002ead9  test    dword ptr [rcx+2A0h], 40000h
0x18002eae3  jnz     short loc_18002EB04
0x18002eae5  cmp     [rbx+29A0h], r12d
0x18002eaec  jnz     short loc_18002EB04
0x18002eaee  mov     [rsp+108h+var_74], r12d
0x18002eaf6  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x18002eafb  cmp     [rax+25Ch], r12d
0x18002eb02  jz      short loc_18002EB0C
0x18002eb04  mov     [rsp+108h+var_74], r13d
0x18002eb0c  mov     rax, [rsi]
0x18002eb0f  mov     rcx, [rbx+20h]; this
0x18002eb13  mov     [rsp+108h+var_58], rax
0x18002eb1b  mov     eax, [rbx+29CCh]
0x18002eb21  mov     [rsp+108h+var_70], eax
0x18002eb28  mov     eax, [rcx+2A0h]
0x18002eb2e  shr     eax, 9
0x18002eb31  and     eax, r13d
0x18002eb34  mov     [rsp+108h+var_60], rcx
0x18002eb3c  mov     dword ptr [rsp+108h+var_68], eax
0x18002eb43  cmp     [rbx+2980h], r12d
0x18002eb4a  jnz     short loc_18002EB5D
0x18002eb4c  mov     [rsp+108h+var_78], r12d
0x18002eb54  cmp     [rbx+2998h], r12d
0x18002eb5b  jz      short loc_18002EB65
0x18002eb5d  mov     [rsp+108h+var_78], r13d
0x18002eb65  mov     r15, [rdi+68h]
0x18002eb69  mov     edx, 6; unsigned int
0x18002eb6e  mov     r12d, [rdi+60h]
0x18002eb72  mov     r13, [rdi+58h]
0x18002eb76  call    ?GetDwordOption@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKK@Z; HTTP_REQUEST_HANDLE_OBJECT::GetDwordOption(ulong)
0x18002eb7b  mov     edx, 5; unsigned int
0x18002eb80  mov     r14d, eax
0x18002eb83  call    ?GetDwordOption@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKK@Z; HTTP_REQUEST_HANDLE_OBJECT::GetDwordOption(ulong)
0x18002eb88  mov     ebp, [rcx+1A0h]
0x18002eb8e  mov     edx, 1; unsigned int
0x18002eb93  mov     r8d, [rcx+3C0h]
0x18002eb9a  test    ebp, ebp
0x18002eb9c  mov     rdi, [rbx+68h]
0x18002eba0  mov     esi, eax
0x18002eba2  mov     ecx, [rcx+3CCh]
0x18002eba8  cmovz   ebp, edx
0x18002ebab  mov     ebx, r8d
0x18002ebae  or      ebx, 4
0x18002ebb1  test    dl, cl
0x18002ebb3  mov     rcx, [rsp+108h+arg_0]; this
0x18002ebbb  cmovnz  ebx, r8d
0x18002ebbf  call    ?_AutoLogonAllowed@HTTP_USER_REQUEST@@AEAAHK@Z; HTTP_USER_REQUEST::_AutoLogonAllowed(ulong)
0x18002ebc4  mov     ecx, [rsp+108h+var_70]
0x18002ebcb  mov     r8, [rsp+108h+arg_20]
0x18002ebd3  mov     r9, [rsp+108h+var_60]
0x18002ebdb  mov     edx, [rsp+108h+var_74]; int
0x18002ebe2  add     r9, 2A8h
0x18002ebe9  mov     [rsp+108h+var_80], ecx; int
0x18002ebf0  mov     ecx, dword ptr [rsp+108h+var_68]
0x18002ebf7  mov     [rsp+108h+var_88], ecx; int
0x18002ebfe  mov     ecx, [rsp+108h+var_78]
0x18002ec05  mov     [rsp+108h+var_90], ecx; int
0x18002ec09  mov     rcx, [rsp+108h+arg_18]
0x18002ec11  mov     [rsp+108h+var_98], r15; unsigned __int64
0x18002ec16  mov     [rsp+108h+var_A0], r12d; unsigned int
0x18002ec1b  mov     [rsp+108h+var_A8], r13; unsigned __int8 *
0x18002ec20  mov     [rsp+108h+var_B0], r14d; unsigned int
0x18002ec25  mov     [rsp+108h+var_B8], esi; unsigned int
0x18002ec29  mov     [rsp+108h+var_C0], ebp; int
0x18002ec2d  mov     [rsp+108h+var_C8], r8; void *
0x18002ec32  mov     r8, [rsp+108h+arg_10]; struct CAuthData *
0x18002ec3a  mov     [rsp+108h+var_D0], rdi; unsigned __int16 *
0x18002ec3f  mov     [rsp+108h+var_D8], r9; struct CRequestParameters *
0x18002ec44  mov     r9d, eax; int
0x18002ec47  mov     [rsp+108h+var_E0], ebx; unsigned int
0x18002ec4b  mov     [rsp+108h+var_E8], rcx; struct CAuthData *
0x18002ec50  mov     rcx, [rsp+108h+var_58]; this
0x18002ec58  call    ?SendRequest@WEBIO_REQUEST@@QEAAKHPEAUCAuthData@@H0KPEAVCRequestParameters@@PEAGPEAXHKKQEAEK_KHHH@Z; WEBIO_REQUEST::SendRequest(int,CAuthData *,int,CAuthData *,ulong,CRequestParameters *,ushort *,void *,int,ulong,ulong,uchar * const,ulong,unsigned __int64,int,int,int)
0x18002ec5d  mov     rbx, [rsp+108h+arg_0]
0x18002ec65  mov     edi, eax
0x18002ec67  cmp     eax, 3E5h
0x18002ec6c  jz      short loc_18002EC8F
0x18002ec6e  mov     r8, [rsp+108h+arg_8]; struct PENDING_API_CALL *
0x18002ec76  mov     edx, eax; unsigned int
0x18002ec78  mov     rcx, rbx; this
0x18002ec7b  call    ?_PostProcessSendRequest@HTTP_USER_REQUEST@@AEAAXKPEAVPENDING_API_CALL@@@Z; HTTP_USER_REQUEST::_PostProcessSendRequest(ulong,PENDING_API_CALL *)
0x18002ec80  mov     rax, [rbx]
0x18002ec83  mov     rcx, rbx
0x18002ec86  mov     rax, [rax+8]
0x18002ec8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec8f  test    edi, edi
0x18002ec91  jz      short loc_18002ECA3
0x18002ec93  cmp     edi, 3E5h
0x18002ec99  jz      short loc_18002ECA3
0x18002ec9b  mov     rcx, rbx; this
0x18002ec9e  call    ?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_SafeDetachSysReq(void)
0x18002eca3  mov     eax, edi
0x18002eca5  add     rsp, 0C8h
0x18002ecac  pop     r15
0x18002ecae  pop     r14
0x18002ecb0  pop     r13
0x18002ecb2  pop     r12
0x18002ecb4  pop     rdi
0x18002ecb5  pop     rsi
0x18002ecb6  pop     rbp
0x18002ecb7  pop     rbx
0x18002ecb8  retn
```
