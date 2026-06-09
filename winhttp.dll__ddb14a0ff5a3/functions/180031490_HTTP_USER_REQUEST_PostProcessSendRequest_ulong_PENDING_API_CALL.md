# HTTP_USER_REQUEST::_PostProcessSendRequest(ulong,PENDING_API_CALL *)

- ea: `0x180031490`
- end: `0x18003175e`
- name: `?_PostProcessSendRequest@HTTP_USER_REQUEST@@AEAAXKPEAVPENDING_API_CALL@@@Z`
- size: `718`
- prototype: `void __fastcall(HTTP_USER_REQUEST *this, int, struct PENDING_API_CALL *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18002e7ec`
- `0x1800967f0`

## callees

- `0x180026680`
- `0x180030730`
- `0x180031490`
- `0x180031770`
- `0x180033190`
- `0x1800354c0`
- `0x180091540`
- `0x1800a1d10`
- `0x1800b67d4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003164e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800316c8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003164e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800316c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003165e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800316d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003165e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800316d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003161a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003168d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003161a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003168d`

## pseudocode

```c
void __fastcall HTTP_USER_REQUEST::_PostProcessSendRequest(
        HTTP_USER_REQUEST *this,
        int a2,
        struct PENDING_API_CALL *a3)
{
  struct WEBIO_REQUEST *v3; // rbx
  char *v7; // r15
  _QWORD *v8; // r12
  _QWORD *v9; // r13
  int v10; // ebx
  void *v11; // rcx
  int v12; // ebx
  void *v13; // rcx
  int v14; // [rsp+30h] [rbp-30h] BYREF
  struct WEBIO_REQUEST *v15; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v16; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+50h] [rbp-10h] BYREF

  v3 = (struct WEBIO_REQUEST *)*((_QWORD *)a3 + 16);
  v14 = 0;
  v15 = v3;
  if ( !a2 )
  {
    if ( *((_DWORD *)this + 57) )
    {
      *((_DWORD *)a3 + 9) = *((_DWORD *)a3 + 24);
      if ( *((_QWORD *)a3 + 11) )
      {
        if ( (*((_BYTE *)a3 + 56) & 0x30) != 0 )
        {
          v16 = 0;
          v17 = 0;
          if ( !*((_DWORD *)a3 + 10) || (v10 = *((_DWORD *)a3 + 11), GetCurrentThreadId() == v10) )
          {
            WinHttpEtwBeginActivityIdInternal(&WinHttpEtwNullActivityId, 0, &v16, &v17);
            v7 = (char *)a3 + 48;
            v8 = (_QWORD *)((char *)a3 + 64);
            v9 = (_QWORD *)((char *)this + 32);
            (*((void (__fastcall **)(_QWORD, _QWORD, __int64))a3 + 6))(*((_QWORD *)this + 4), *((_QWORD *)a3 + 8), 16);
            if ( v17 )
              WxEtwSetActivityId(&v16);
          }
          else
          {
            v11 = (void *)*((_QWORD *)a3 + 9);
            *((_DWORD *)a3 + 35) = 1;
            *((_DWORD *)a3 + 36) = 16;
            *((_QWORD *)a3 + 19) = 0;
            *((_DWORD *)a3 + 40) = 0;
            SetEvent(v11);
            WaitForSingleObjectEx(*((HANDLE *)a3 + 10), 0xFFFFFFFF, 0);
            *(_QWORD *)((char *)a3 + 140) = 0;
            v8 = (_QWORD *)((char *)a3 + 64);
            *((_QWORD *)a3 + 19) = 0;
            v9 = (_QWORD *)((char *)this + 32);
            *((_DWORD *)a3 + 40) = 0;
            v7 = (char *)a3 + 48;
          }
          v14 = *((_DWORD *)a3 + 9);
          v16 = 0;
          v17 = 0;
          if ( !*((_DWORD *)a3 + 10) || (v12 = *((_DWORD *)a3 + 11), GetCurrentThreadId() == v12) )
          {
            WinHttpEtwBeginActivityIdInternal(&WinHttpEtwNullActivityId, 0, &v16, &v17);
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64, int *, int))v7)(*v9, *v8, 32, &v14, 4);
            if ( v17 )
              WxEtwSetActivityId(&v16);
          }
          else
          {
            v13 = (void *)*((_QWORD *)a3 + 9);
            *((_QWORD *)a3 + 19) = &v14;
            *((_DWORD *)a3 + 35) = 1;
            *((_DWORD *)a3 + 36) = 32;
            *((_DWORD *)a3 + 40) = 4;
            SetEvent(v13);
            WaitForSingleObjectEx(*((HANDLE *)a3 + 10), 0xFFFFFFFF, 0);
            *(_QWORD *)((char *)a3 + 140) = 0;
            *((_QWORD *)a3 + 19) = 0;
            *((_DWORD *)a3 + 40) = 0;
          }
          v3 = v15;
        }
      }
    }
  }
  HTTP_USER_REQUEST::_UpdateConnectionState(this, a3, 0);
  if ( a2 == 12044 )
  {
    HTTP_USER_REQUEST::_PostProcessClientCertNeeded(this, a3);
  }
  else if ( a2 == 12175 )
  {
    HTTP_USER_REQUEST::_ProcessTlsHandshakeFailure(this, v3);
    if ( (*((_DWORD *)a3 + 14) & 0x10000) != 0 )
    {
      if ( *((_QWORD *)a3 + 6) )
      {
        LODWORD(v15) = 0;
        LODWORD(v15) = WEBIO_REQUEST::GetCallbackStatusSecureFailureErrors(v3);
        HTTP_USER_REQUEST::_IndicateInformational(this, a3, 0x10000u, &v15, 4u);
      }
    }
  }
}

```

## disassembly

```asm
0x180031490  mov     [rsp-38h+arg_8], rbx
0x180031495  push    rbp
0x180031496  push    rsi
0x180031497  push    rdi
0x180031498  push    r12
0x18003149a  push    r13
0x18003149c  push    r14
0x18003149e  push    r15
0x1800314a0  mov     rbp, rsp
0x1800314a3  sub     rsp, 60h
0x1800314a7  mov     rax, cs:__security_cookie
0x1800314ae  xor     rax, rsp
0x1800314b1  mov     [rbp+var_8], rax
0x1800314b5  mov     rbx, [r8+80h]
0x1800314bc  xor     r15d, r15d
0x1800314bf  mov     [rbp+var_30], r15d
0x1800314c3  mov     rdi, r8
0x1800314c6  mov     [rbp+var_28], rbx
0x1800314ca  mov     r14d, edx
0x1800314cd  mov     rsi, rcx
0x1800314d0  test    edx, edx
0x1800314d2  jnz     short loc_1800314EB
0x1800314d4  cmp     [rcx+0E4h], r15d
0x1800314db  jz      short loc_1800314EB
0x1800314dd  mov     eax, [r8+60h]
0x1800314e1  mov     [r8+24h], eax
0x1800314e5  cmp     [r8+58h], r15
0x1800314e9  jnz     short loc_180031537
0x1800314eb  xor     r8d, r8d; int
0x1800314ee  mov     rdx, rdi; struct PENDING_API_CALL *
0x1800314f1  mov     rcx, rsi; this
0x1800314f4  call    ?_UpdateConnectionState@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@H@Z; HTTP_USER_REQUEST::_UpdateConnectionState(PENDING_API_CALL *,int)
0x1800314f9  cmp     r14d, 2F0Ch
0x180031500  jz      loc_18003174E
0x180031506  cmp     r14d, 2F8Fh
0x18003150d  jz      loc_1800316FB
0x180031513  mov     rcx, [rbp+var_8]
0x180031517  xor     rcx, rsp; StackCookie
0x18003151a  call    __security_check_cookie
0x18003151f  mov     rbx, [rsp+60h+arg_8]
0x180031527  add     rsp, 60h
0x18003152b  pop     r15
0x18003152d  pop     r14
0x18003152f  pop     r13
0x180031531  pop     r12
0x180031533  pop     rdi
0x180031534  pop     rsi
0x180031535  pop     rbp
0x180031536  retn
0x180031537  test    byte ptr [r8+38h], 30h
0x18003153c  jz      short loc_1800314EB
0x18003153e  xor     eax, eax
0x180031540  xorps   xmm0, xmm0
0x180031543  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180031547  mov     [rbp+var_10], eax
0x18003154a  cmp     [r8+28h], r15d
0x18003154e  jnz     loc_180031616
0x180031554  lea     r9, [rbp+var_10]; int *
0x180031558  xor     edx, edx; unsigned int
0x18003155a  lea     r8, [rbp+var_20]; struct _GUID *
0x18003155e  lea     rcx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; struct _GUID *
0x180031565  call    ?WinHttpEtwBeginActivityIdInternal@@YAXPEBU_GUID@@KPEAU1@PEAH@Z; WinHttpEtwBeginActivityIdInternal(_GUID const *,ulong,_GUID *,int *)
0x18003156a  xor     r9d, r9d
0x18003156d  mov     [rsp+60h+var_40], 0
0x180031575  lea     r15, [rdi+30h]
0x180031579  mov     rax, [r15]
0x18003157c  lea     r12, [rdi+40h]
0x180031580  mov     rdx, [r12]
0x180031584  lea     r13, [rsi+20h]
0x180031588  mov     rcx, [r13+0]
0x18003158c  lea     r8d, [r9+10h]
0x180031590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031595  cmp     [rbp+var_10], 0
0x180031599  jnz     short loc_180031600
0x18003159b  mov     eax, [rdi+24h]
0x18003159e  xorps   xmm0, xmm0
0x1800315a1  mov     [rbp+var_30], eax
0x1800315a4  xor     eax, eax
0x1800315a6  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x1800315aa  mov     [rbp+var_10], eax
0x1800315ad  cmp     [rdi+28h], eax
0x1800315b0  jnz     loc_18003168A
0x1800315b6  lea     r9, [rbp+var_10]; int *
0x1800315ba  xor     edx, edx; unsigned int
0x1800315bc  lea     r8, [rbp+var_20]; struct _GUID *
0x1800315c0  lea     rcx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; struct _GUID *
0x1800315c7  call    ?WinHttpEtwBeginActivityIdInternal@@YAXPEBU_GUID@@KPEAU1@PEAH@Z; WinHttpEtwBeginActivityIdInternal(_GUID const *,ulong,_GUID *,int *)
0x1800315cc  mov     rdx, [r12]
0x1800315d0  lea     r9, [rbp+var_30]
0x1800315d4  mov     rcx, [r13+0]
0x1800315d8  mov     r8d, 20h ; ' '
0x1800315de  mov     rax, [r15]
0x1800315e1  mov     [rsp+60h+var_40], 4
0x1800315e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315ee  xor     r15d, r15d
0x1800315f1  cmp     [rbp+var_10], r15d
0x1800315f5  jnz     short loc_18003160B
0x1800315f7  mov     rbx, [rbp+var_28]
0x1800315fb  jmp     loc_1800314EB
0x180031600  lea     rcx, [rbp+var_20]; struct _GUID *
0x180031604  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x180031609  jmp     short loc_18003159B
0x18003160b  lea     rcx, [rbp+var_20]; struct _GUID *
0x18003160f  call    ?WxEtwSetActivityId@@YAXPEBU_GUID@@@Z; WxEtwSetActivityId(_GUID const *)
0x180031614  jmp     short loc_1800315F7
0x180031616  mov     ebx, [r8+2Ch]
0x18003161a  call    cs:__imp_GetCurrentThreadId
0x180031620  cmp     eax, ebx
0x180031622  jz      loc_180031554
0x180031628  mov     rcx, [rdi+48h]; hEvent
0x18003162c  mov     dword ptr [rdi+8Ch], 1
0x180031636  mov     dword ptr [rdi+90h], 10h
0x180031640  mov     [rdi+98h], r15
0x180031647  mov     [rdi+0A0h], r15d
0x18003164e  call    cs:__imp_SetEvent
0x180031654  mov     rcx, [rdi+50h]; hHandle
0x180031658  xor     r8d, r8d; bAlertable
0x18003165b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003165e  call    cs:__imp_WaitForSingleObjectEx
0x180031664  mov     [rdi+8Ch], r15
0x18003166b  lea     r12, [rdi+40h]
0x18003166f  mov     [rdi+98h], r15
0x180031676  lea     r13, [rsi+20h]
0x18003167a  mov     [rdi+0A0h], r15d
0x180031681  lea     r15, [rdi+30h]
0x180031685  jmp     loc_18003159B
0x18003168a  mov     ebx, [rdi+2Ch]
0x18003168d  call    cs:__imp_GetCurrentThreadId
0x180031693  cmp     eax, ebx
0x180031695  jz      loc_1800315B6
0x18003169b  mov     rcx, [rdi+48h]; hEvent
0x18003169f  lea     rax, [rbp+var_30]
0x1800316a3  mov     [rdi+98h], rax
0x1800316aa  mov     dword ptr [rdi+8Ch], 1
0x1800316b4  mov     dword ptr [rdi+90h], 20h ; ' '
0x1800316be  mov     dword ptr [rdi+0A0h], 4
0x1800316c8  call    cs:__imp_SetEvent
0x1800316ce  mov     rcx, [rdi+50h]; hHandle
0x1800316d2  xor     r8d, r8d; bAlertable
0x1800316d5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800316d8  call    cs:__imp_WaitForSingleObjectEx
0x1800316de  xor     r15d, r15d
0x1800316e1  mov     [rdi+8Ch], r15
0x1800316e8  mov     [rdi+98h], r15
0x1800316ef  mov     [rdi+0A0h], r15d
0x1800316f6  jmp     loc_1800315F7
0x1800316fb  mov     rdx, rbx; struct WEBIO_REQUEST *
0x1800316fe  mov     rcx, rsi; this
0x180031701  call    ?_ProcessTlsHandshakeFailure@HTTP_USER_REQUEST@@AEAAXPEAVWEBIO_REQUEST@@@Z; HTTP_USER_REQUEST::_ProcessTlsHandshakeFailure(WEBIO_REQUEST *)
0x180031706  mov     r14d, 10000h
0x18003170c  test    [rdi+38h], r14d
0x180031710  jz      loc_180031513
0x180031716  cmp     [rdi+30h], r15
0x18003171a  jz      loc_180031513
0x180031720  mov     rcx, rbx; this
0x180031723  mov     dword ptr [rbp+var_28], r15d
0x180031727  call    ?GetCallbackStatusSecureFailureErrors@WEBIO_REQUEST@@QEAAKXZ; WEBIO_REQUEST::GetCallbackStatusSecureFailureErrors(void)
0x18003172c  lea     r9, [rbp+var_28]; void *
0x180031730  mov     dword ptr [rbp+var_28], eax
0x180031733  mov     r8d, r14d; unsigned int
0x180031736  mov     [rsp+60h+var_40], 4; unsigned int
0x18003173e  mov     rdx, rdi; struct PENDING_API_CALL *
0x180031741  mov     rcx, rsi; this
0x180031744  call    ?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z; HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)
0x180031749  jmp     loc_180031513
0x18003174e  mov     rdx, rdi; struct PENDING_API_CALL *
0x180031751  mov     rcx, rsi; this
0x180031754  call    ?_PostProcessClientCertNeeded@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@@Z; HTTP_USER_REQUEST::_PostProcessClientCertNeeded(PENDING_API_CALL *)
0x180031759  jmp     loc_180031513
```
