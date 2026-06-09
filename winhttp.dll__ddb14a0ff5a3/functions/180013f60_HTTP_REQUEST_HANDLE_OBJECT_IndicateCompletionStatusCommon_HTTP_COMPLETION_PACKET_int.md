# HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(HTTP_COMPLETION_PACKET *,int)

- ea: `0x180013f60`
- end: `0x1800141d9`
- name: `?IndicateCompletionStatusCommon@HTTP_REQUEST_HANDLE_OBJECT@@AEAAKPEAUHTTP_COMPLETION_PACKET@@H@Z`
- size: `633`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, struct HTTP_COMPLETION_PACKET *, int)`
- caller_count: `5`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027880`
- `0x1800347e0`
- `0x1800364d0`
- `0x18003a2b0`
- `0x18003bcd0`

## callees

- `0x180010f50`
- `0x180013680`
- `0x180013f60`
- `0x1800141e0`
- `0x180014740`
- `0x180015aa0`
- `0x180032c78`
- `0x180033a70`
- `0x1800809a8`
- `0x180098320`
- `0x1800a1d10`
- `0x1800a3da8`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013fc5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fae`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180014119`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180014119`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014013`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        struct HTTP_COMPLETION_PACKET *a2,
        int a3)
{
  void (__fastcall *v3)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // rax
  DWORD LastError; // esi
  struct _INTERNET_THREAD_INFO *ThreadInfo; // rbx
  unsigned int v9; // esi
  void *v10; // rcx
  __int64 v12; // rbp
  unsigned int v13; // eax
  __int64 v14; // r8
  DWORD CurrentThreadId; // eax
  __int64 v16; // [rsp+20h] [rbp-78h]
  char *v17; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[16]; // [rsp+40h] [rbp-58h] BYREF
  char **v20; // [rsp+50h] [rbp-48h]
  __int64 v21; // [rsp+58h] [rbp-40h]
  int *v22; // [rsp+60h] [rbp-38h]
  __int64 v23; // [rsp+68h] [rbp-30h]

  v3 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))a2;
  if ( *(void (**)(void *, unsigned __int64, unsigned int, void *, unsigned int))a2 == HTTP_USER_REQUEST::PrvResendStatusCallback )
  {
    v3(0, *((_QWORD *)a2 + 1), *((unsigned int *)a2 + 5), *((_QWORD *)a2 + 3), *((_DWORD *)a2 + 8));
    HTTP_COMPLETION_PACKET::`scalar deleting destructor'(a2);
    return 0;
  }
  if ( !v3 )
    return 0;
  LastError = GetLastError();
  if ( InternetTlsIndex == -1 || (ThreadInfo = (struct _INTERNET_THREAD_INFO *)TlsGetValue(InternetTlsIndex)) == 0 )
  {
    if ( (BYTE1(xmmword_180107A60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 15, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids, CurrentThreadId, v16);
    }
    ThreadInfo = InternetCreateThreadInfo();
    if ( !ThreadInfo && (BYTE1(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_(1037, 16, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids);
  }
  SetLastError(LastError);
  if ( !a3 || ThreadInfo && *((_DWORD *)ThreadInfo + 6) <= 2u )
  {
    v9 = 0;
    if ( ThreadInfo )
    {
      ++*((_DWORD *)ThreadInfo + 6);
      HTTP_REQUEST_HANDLE_OBJECT::_SafeAppCallback(this, a2);
      --*((_DWORD *)ThreadInfo + 6);
    }
    else
    {
      HTTP_REQUEST_HANDLE_OBJECT::_SafeAppCallback(this, a2);
    }
    v10 = (void *)*((_QWORD *)a2 + 10);
    *((_QWORD *)a2 + 8) = &HTTP_THREAD_POOL::CONTEXT::`vftable';
    if ( v10 )
    {
      CloseHandle(v10);
      *((_QWORD *)a2 + 10) = 0;
    }
    operator delete(a2);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
    v12 = qword_180107DE8;
    v13 = CaptureImpersonationToken((void **)a2 + 10);
    if ( v13 )
    {
      v9 = SET_WINHTTP_ERROR_FROM_WIN32(v13);
      HTTP_COMPLETION_PACKET::`scalar deleting destructor'(a2);
    }
    else
    {
      WxEtwGetActivityId((struct _GUID *)a2 + 6);
      *((_QWORD *)a2 + 9) = (char *)this + 432;
      *((_QWORD *)a2 + 11) = a2;
      v9 = 0;
      HANDLE_OBJECT::Reference(this);
      *((_QWORD *)a2 + 7) = v12;
      if ( (Microsoft_Windows_WinHttpEnableBits & 8) != 0 )
      {
        v18 = 2;
        v17 = (char *)a2 + 64;
        v21 = 8;
        v20 = &v17;
        v23 = 4;
        v22 = &v18;
        McGenEventWrite_EtwEventWriteTransfer(
          WINHTTP_ETW_PROVIDER_ID_Context,
          (__int64)QueueThreadAction,
          v14,
          3,
          (__int64)v19);
      }
      InterlockedPushEntrySList((PSLIST_HEADER)(v12 + 96), (PSLIST_ENTRY)a2 + 7);
      WxSubmitThreadpoolWork(*(struct _TP_WORK **)(v12 + 88));
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180013f60  mov     [rsp+arg_18], rbx
0x180013f65  push    rbp
0x180013f66  push    rdi
0x180013f67  push    r14
0x180013f69  sub     rsp, 80h
0x180013f70  mov     rax, cs:__security_cookie
0x180013f77  xor     rax, rsp
0x180013f7a  mov     [rsp+98h+var_28], rax
0x180013f7f  mov     rax, [rdx]
0x180013f82  mov     r14, rcx
0x180013f85  lea     rcx, ?PrvResendStatusCallback@HTTP_USER_REQUEST@@SAXPEAX_KK0K@Z; HTTP_USER_REQUEST::PrvResendStatusCallback(void *,unsigned __int64,ulong,void *,ulong)
0x180013f8c  xor     ebx, ebx
0x180013f8e  mov     ebp, r8d
0x180013f91  mov     rdi, rdx
0x180013f94  cmp     rax, rcx
0x180013f97  jz      loc_18001412D
0x180013f9d  test    rax, rax
0x180013fa0  jz      loc_18001414F
0x180013fa6  mov     [rsp+98h+arg_10], rsi
0x180013fae  call    cs:__imp_GetLastError
0x180013fb4  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x180013fba  mov     esi, eax
0x180013fbc  cmp     ecx, 0FFFFFFFFh
0x180013fbf  jz      loc_180014160
0x180013fc5  call    cs:__imp_TlsGetValue
0x180013fcb  mov     rbx, rax
0x180013fce  test    rax, rax
0x180013fd1  jz      loc_180014160
0x180013fd7  mov     ecx, esi; dwErrCode
0x180013fd9  call    cs:__imp_SetLastError
0x180013fdf  test    ebp, ebp
0x180013fe1  jnz     short loc_180014055
0x180013fe3  xor     esi, esi
0x180013fe5  mov     rdx, rdi; struct HTTP_COMPLETION_PACKET *
0x180013fe8  mov     rcx, r14; this
0x180013feb  test    rbx, rbx
0x180013fee  jz      loc_180014156
0x180013ff4  inc     dword ptr [rbx+18h]
0x180013ff7  call    ?_SafeAppCallback@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXPEAUHTTP_COMPLETION_PACKET@@@Z; HTTP_REQUEST_HANDLE_OBJECT::_SafeAppCallback(HTTP_COMPLETION_PACKET *)
0x180013ffc  dec     dword ptr [rbx+18h]
0x180013fff  mov     rcx, [rdi+50h]; hObject
0x180014003  lea     rax, ??_7CONTEXT@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::CONTEXT::`vftable'
0x18001400a  mov     [rdi+40h], rax
0x18001400e  test    rcx, rcx
0x180014011  jz      short loc_18001401D
0x180014013  call    cs:__imp_CloseHandle
0x180014019  mov     [rdi+50h], rsi
0x18001401d  mov     edx, 80h; unsigned __int64
0x180014022  mov     rcx, rdi; void *
0x180014025  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001402a  mov     eax, esi
0x18001402c  mov     rsi, [rsp+98h+arg_10]
0x180014034  mov     rcx, [rsp+98h+var_28]
0x180014039  xor     rcx, rsp; StackCookie
0x18001403c  call    __security_check_cookie
0x180014041  mov     rbx, [rsp+98h+arg_18]
0x180014049  add     rsp, 80h
0x180014050  pop     r14
0x180014052  pop     rdi
0x180014053  pop     rbp
0x180014054  retn
0x180014055  test    rbx, rbx
0x180014058  jz      short loc_180014060
0x18001405a  cmp     dword ptr [rbx+18h], 2
0x18001405e  jbe     short loc_180013FE3
0x180014060  mov     rcx, [r14+18h]
0x180014064  mov     rax, [rcx]
0x180014067  mov     rax, [rax+8]
0x18001406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014070  mov     rbp, cs:qword_180107DE8
0x180014077  lea     rcx, [rdi+50h]; void **
0x18001407b  call    ?CaptureImpersonationToken@@YAKPEAPEAX@Z; CaptureImpersonationToken(void * *)
0x180014080  test    eax, eax
0x180014082  jnz     loc_1800141C3
0x180014088  lea     rcx, [rdi+60h]; struct _GUID *
0x18001408c  lea     rbx, [r14+1B0h]
0x180014093  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180014098  mov     [rdi+48h], rbx
0x18001409c  mov     [rdi+58h], rdi
0x1800140a0  mov     rcx, r14; this
0x1800140a3  xor     esi, esi
0x1800140a5  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x1800140aa  mov     [rdi+38h], rbp
0x1800140ae  test    cs:Microsoft_Windows_WinHttpEnableBits, 8
0x1800140b5  jz      short loc_180014111
0x1800140b7  lea     rax, [rdi+40h]
0x1800140bb  mov     [rsp+98h+var_60], 2
0x1800140c3  mov     [rsp+98h+var_68], rax
0x1800140c8  lea     rdx, QueueThreadAction
0x1800140cf  lea     rax, [rsp+98h+var_68]
0x1800140d4  mov     [rsp+98h+var_40], 8
0x1800140dd  mov     [rsp+98h+var_48], rax
0x1800140e2  lea     rcx, WINHTTP_ETW_PROVIDER_ID_Context
0x1800140e9  lea     rax, [rsp+98h+var_60]
0x1800140ee  mov     [rsp+98h+var_30], 4
0x1800140f7  mov     [rsp+98h+var_38], rax
0x1800140fc  mov     r9d, 3
0x180014102  lea     rax, [rsp+98h+var_58]
0x180014107  mov     [rsp+98h+var_78], rax
0x18001410c  call    McGenEventWrite_EtwEventWriteTransfer
0x180014111  lea     rdx, [rdi+70h]; ListEntry
0x180014115  lea     rcx, [rbp+60h]; ListHead
0x180014119  call    cs:__imp_InterlockedPushEntrySList
0x18001411f  mov     rcx, [rbp+58h]; struct _TP_WORK *
0x180014123  call    ?WxSubmitThreadpoolWork@@YAXPEAU_TP_WORK@@@Z; WxSubmitThreadpoolWork(_TP_WORK *)
0x180014128  jmp     loc_18001402A
0x18001412d  mov     ecx, [rdx+20h]
0x180014130  mov     r9, [rdx+18h]
0x180014134  mov     r8d, [rdx+14h]
0x180014138  mov     rdx, [rdx+8]
0x18001413c  mov     dword ptr [rsp+98h+var_78], ecx
0x180014140  xor     ecx, ecx
0x180014142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014147  mov     rcx, rdi; this
0x18001414a  call    ??_GHTTP_COMPLETION_PACKET@@QEAAPEAXI@Z; HTTP_COMPLETION_PACKET::`scalar deleting destructor'(uint)
0x18001414f  mov     eax, ebx
0x180014151  jmp     loc_180014034
0x180014156  call    ?_SafeAppCallback@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXPEAUHTTP_COMPLETION_PACKET@@@Z; HTTP_REQUEST_HANDLE_OBJECT::_SafeAppCallback(HTTP_COMPLETION_PACKET *)
0x18001415b  jmp     loc_180013FFF
0x180014160  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180014167  jnz     short loc_1800141A2
0x180014169  call    ?InternetCreateThreadInfo@@YAPEAU_INTERNET_THREAD_INFO@@XZ; InternetCreateThreadInfo(void)
0x18001416e  mov     rbx, rax
0x180014171  test    rax, rax
0x180014174  jnz     loc_180013FD7
0x18001417a  test    byte ptr cs:xmmword_180107A60+1, 20h
0x180014181  jz      loc_180013FD7
0x180014187  mov     edx, 10h
0x18001418c  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x180014193  mov     ecx, 40Dh
0x180014198  call    WPP_SF_
0x18001419d  jmp     loc_180013FD7
0x1800141a2  call    cs:__imp_GetCurrentThreadId
0x1800141a8  mov     edx, 0Fh
0x1800141ad  lea     r8, WPP_05d0af452eab3f6ec364fa2eb55c9577_Traceguids
0x1800141b4  mov     r9d, eax
0x1800141b7  mov     ecx, 40Dh
0x1800141bc  call    WPP_SF_d
0x1800141c1  jmp     short loc_180014169
0x1800141c3  mov     ecx, eax; unsigned int
0x1800141c5  call    ?SET_WINHTTP_ERROR_FROM_WIN32@@YAKK@Z; SET_WINHTTP_ERROR_FROM_WIN32(ulong)
0x1800141ca  mov     rcx, rdi; this
0x1800141cd  mov     esi, eax
0x1800141cf  call    ??_GHTTP_COMPLETION_PACKET@@QEAAPEAXI@Z; HTTP_COMPLETION_PACKET::`scalar deleting destructor'(uint)
0x1800141d4  jmp     loc_18001402A
```
