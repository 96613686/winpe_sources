# ComputeService::Client::NotificationCallbacks::OnNotificationPending(ComputeService::Client::NotificationCallbacks::NotificationContext *)

- ea: `0x18003941c`
- end: `0x18003959b`
- name: `?OnNotificationPending@NotificationCallbacks@Client@ComputeService@@AEAAXPEAUNotificationContext@123@@Z`
- size: `383`
- prototype: `void(ComputeService::Client::NotificationCallbacks *__hidden this, struct ComputeService::Client::NotificationCallbacks::NotificationContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180039d40`

## callees

- `0x180002f50`
- `0x180012048`
- `0x18001c460`
- `0x180039354`
- `0x18003941c`
- `0x180039bd8`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039556`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180039556`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003956d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003956d`

## string_xrefs

- `0x1800394bf`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Client::NotificationCallbacks::OnNotificationPending(
        ComputeService::Client::NotificationCallbacks *this,
        struct ComputeService::Client::NotificationCallbacks::NotificationContext *a2)
{
  struct ComputeService::Client::NotificationCallbacks::NotificationContext *v2; // rbx
  char v4; // di
  char v5; // si
  int v6; // eax
  ComputeService::Client::NotificationCallbacks *v7; // rcx
  void (__fastcall *v8)(__int128 *, void **, _QWORD); // rax
  HLOCAL v9; // rdi
  DWORD LastError; // ebx
  char v11; // [rsp+30h] [rbp-68h]
  void *p_hMem; // [rsp+38h] [rbp-60h] BYREF
  struct ComputeService::Client::NotificationCallbacks::NotificationContext *v14; // [rsp+40h] [rbp-58h]
  __int128 *v15; // [rsp+48h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-48h] BYREF
  __int128 v17; // [rsp+58h] [rbp-40h] BYREF
  __int64 v18; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = a2;
  v14 = a2;
  if ( ComputeService::Client::NotificationCallbacks::StartCallback(this, a2) )
  {
    try
    {
      v17 = 0;
      v18 = 0;
      v4 = 1;
      v11 = 1;
      v5 = 1;
      hMem = 0;
      p_hMem = &hMem;
      v15 = &v17;
      v6 = ComputeService::Client::InvokeRpcFunction<long (*)(void *,void * *,void * *),void * &,void * *,void * *>(
             *((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))this + 2),
             v2,
             &v15,
             &p_hMem);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v6,
          (int)"Failed to query notification for handle %p",
          *(const char **)v2);
        v4 = 0;
        v11 = 0;
      }
    }
    catch ( ... )
    {
      *((_QWORD *)&v17 + 1) = 0x1000000;
      *(_QWORD *)&v17 = -1;
      v9 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v9);
        SetLastError(LastError);
      }
      hMem = 0;
      v4 = v11;
      v5 = 0;
      v2 = v14;
    }
    if ( v4 )
    {
      v8 = (void (__fastcall *)(__int128 *, void **, _QWORD))*((_QWORD *)v2 + 2);
      if ( v8 )
      {
        p_hMem = hMem;
        hMem = 0;
        v8(&v17, &p_hMem, *((_QWORD *)v2 + 3));
      }
      else
      {
        (*((void (__fastcall **)(_QWORD, _QWORD, _QWORD, HLOCAL))v2 + 1))(
          DWORD2(v17),
          *((_QWORD *)v2 + 3),
          HIDWORD(v17),
          hMem);
      }
    }
    if ( ComputeService::Client::NotificationCallbacks::CompleteCallback(v7, v2) && v5 )
      SetThreadpoolWait(*((PTP_WAIT *)v2 + 5), *((HANDLE *)v2 + 4), 0);
    if ( hMem )
      LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x18003941c  mov     [rsp+arg_10], rbx
0x180039421  push    rsi
0x180039422  push    rdi
0x180039423  push    r14
0x180039425  sub     rsp, 80h
0x18003942c  mov     rax, cs:__security_cookie
0x180039433  xor     rax, rsp
0x180039436  mov     [rsp+98h+var_28], rax
0x18003943b  mov     rbx, rdx
0x18003943e  mov     r14, rcx
0x180039441  mov     [rsp+98h+var_58], rdx
0x180039446  call    ?StartCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::StartCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x18003944b  test    al, al
0x18003944d  jz      loc_180039579
0x180039453  xorps   xmm0, xmm0
0x180039456  xor     eax, eax
0x180039458  movups  [rsp+98h+var_40], xmm0
0x18003945d  mov     [rsp+98h+var_30], rax
0x180039462  mov     dil, 1
0x180039465  mov     [rsp+98h+var_68], dil
0x18003946a  mov     sil, dil
0x18003946d  mov     [rsp+98h+hMem], rax
0x180039472  lea     rax, [rsp+98h+hMem]
0x180039477  mov     [rsp+98h+var_60], rax
0x18003947c  lea     rax, [rsp+98h+var_40]
0x180039481  mov     [rsp+98h+var_50], rax
0x180039486  lea     r9, [rsp+98h+var_60]
0x18003948b  lea     r8, [rsp+98h+var_50]
0x180039490  mov     rdx, rbx
0x180039493  mov     rcx, [r14+10h]
0x180039497  call    ??$InvokeRpcFunction@P6AJPEAXPEAPEAX1@ZAEAPEAXPEAPEAXPEAPEAX@Client@ComputeService@@YA?A_TP6AJPEAXPEAPEAX1@ZAEAPEAX$$QEAPEAPEAX4@Z
0x18003949c  test    eax, eax
0x18003949e  jns     short loc_1800394D8
0x1800394a0  mov     rcx, [rsp+98h]; this
0x1800394a8  mov     rdx, [rbx]
0x1800394ab  mov     [rsp+98h+var_70], rdx; char *
0x1800394b0  lea     rdx, aFailedToQueryN; "Failed to query notification for handle"...
0x1800394b7  mov     qword ptr [rsp+98h+var_78], rdx; int
0x1800394bc  mov     r9d, eax; char *
0x1800394bf  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x1800394c6  mov     edx, 1A2h; void *
0x1800394cb  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800394d0  xor     dil, dil
0x1800394d3  mov     [rsp+98h+var_68], dil
0x1800394d8  jmp     short loc_1800394E9
0x1800394da  mov     dil, [rsp+98h+var_68]
0x1800394df  mov     sil, [rsp+98h+var_67]
0x1800394e4  mov     rbx, [rsp+98h+var_58]
0x1800394e9  test    dil, dil
0x1800394ec  jz      short loc_18003953A
0x1800394ee  mov     rax, [rbx+10h]
0x1800394f2  test    rax, rax
0x1800394f5  jz      short loc_18003951F
0x1800394f7  mov     rcx, [rsp+98h+hMem]
0x1800394fc  mov     [rsp+98h+var_60], rcx
0x180039501  mov     [rsp+98h+hMem], 0
0x18003950a  mov     r8, [rbx+18h]
0x18003950e  lea     rdx, [rsp+98h+var_60]
0x180039513  lea     rcx, [rsp+98h+var_40]
0x180039518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003951d  jmp     short loc_18003953A
0x18003951f  mov     r9, [rsp+98h+hMem]
0x180039524  mov     r8d, dword ptr [rsp+98h+var_40+0Ch]
0x180039529  mov     rdx, [rbx+18h]
0x18003952d  mov     ecx, dword ptr [rsp+98h+var_40+8]
0x180039531  mov     rax, [rbx+8]
0x180039535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003953a  mov     rdx, rbx; struct ComputeService::Client::NotificationCallbacks::NotificationContext *
0x18003953d  call    ?CompleteCallback@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::CompleteCallback(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x180039542  test    al, al
0x180039544  jz      short loc_180039563
0x180039546  test    sil, sil
0x180039549  jz      short loc_180039563
0x18003954b  xor     r8d, r8d; pftTimeout
0x18003954e  mov     rdx, [rbx+20h]; h
0x180039552  mov     rcx, [rbx+28h]; pwa
0x180039556  call    cs:__imp_SetThreadpoolWait
0x18003955d  nop     dword ptr [rax+rax+00h]
0x180039562  nop
0x180039563  mov     rcx, [rsp+98h+hMem]; hMem
0x180039568  test    rcx, rcx
0x18003956b  jz      short loc_180039579
0x18003956d  call    cs:__imp_LocalFree
0x180039574  nop     dword ptr [rax+rax+00h]
0x180039579  mov     rcx, [rsp+98h+var_28]
0x18003957e  xor     rcx, rsp; StackCookie
0x180039581  call    __security_check_cookie
0x180039586  mov     rbx, [rsp+98h+arg_10]
0x18003958e  add     rsp, 80h
0x180039595  pop     r14
0x180039597  pop     rdi
0x180039598  pop     rsi
0x180039599  retn
```
