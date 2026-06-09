# CServerVCChannel::IssueARead(void)

- ea: `0x18002d458`
- end: `0x18002d620`
- name: `?IssueARead@CServerVCChannel@@AEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CServerVCChannel *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180004f50`
- `0x18002d810`

## callees

- `0x180007da0`
- `0x18000abc0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x18002c600`
- `0x18002d458`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d4da`
- `KERNEL32!ReadFileEx` at `0x18002d4d2`
- `KERNEL32!ReadFileEx` at `0x18002d4d2`

## string_xrefs

- `0x18002d562`: `ReadFileEx Failed`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::IssueARead(CServerVCChannel *this)
{
  __int64 v2; // rbx
  signed int LastError; // esi
  DWORD v4; // r8d
  void *v5; // rdx
  void *v6; // rcx
  BOOL File; // edi
  __int64 v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  bool v10; // sf
  unsigned int v11; // eax
  __int64 *v12; // rdi
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  char *v15; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v14 = 0;
  v15 = (char *)this + 56;
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v15);
    LastError = -2147024220;
    goto LABEL_24;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
  v4 = *((_DWORD *)this + 94);
  v5 = (void *)*((_QWORD *)this + 46);
  v6 = (void *)*((_QWORD *)this + 43);
  *((_QWORD *)this + 54) = this;
  File = ReadFileEx(v6, v5, v4, (LPOVERLAPPED)((char *)this + 408), CServerVCChannel::static_ReadCompletionRoutine);
  LastError = GetLastError();
  if ( File )
  {
    LastError = 0;
    goto LABEL_22;
  }
  v8 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      15,
      WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
    v8 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  v10 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = LastError < 0;
  }
  if ( v10 )
  {
    if ( (unsigned int *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 8) != 0 && *(_BYTE *)(v8 + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        16,
        (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
        v11,
        (__int64)"ReadFileEx Failed",
        LastError);
    }
    goto LABEL_17;
  }
  if ( LastError )
  {
LABEL_17:
    v12 = (__int64 *)((char *)this + 72);
    if ( *((_QWORD *)this + 9) )
    {
      TCntPtr<IDispatch>::SafeRelease(&v14);
      v2 = *v12;
      v14 = *v12;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v14);
    }
    if ( *v12 )
    {
      TCntPtr<IDispatch>::SafeRelease((char *)this + 72);
      *v12 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
  }
LABEL_22:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v15);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
LABEL_24:
  TCntPtr<IDispatch>::SafeRelease(&v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002d458  mov     [rsp+arg_10], rbx
0x18002d45d  push    rbp
0x18002d45e  push    rsi
0x18002d45f  push    rdi
0x18002d460  sub     rsp, 30h
0x18002d464  mov     rbp, rcx
0x18002d467  xor     ebx, ebx
0x18002d469  add     rcx, 38h ; '8'; this
0x18002d46d  mov     [rsp+48h+arg_0], rbx
0x18002d472  mov     [rsp+48h+arg_8], rcx
0x18002d477  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18002d47c  test    byte ptr [rbp+24h], 4
0x18002d480  jz      short loc_18002D496
0x18002d482  lea     rcx, [rsp+48h+arg_8]; this
0x18002d487  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002d48c  mov     esi, 800702A4h
0x18002d491  jmp     loc_18002D607
0x18002d496  mov     rcx, [rbp+28h]
0x18002d49a  mov     rax, [rcx]
0x18002d49d  mov     rax, [rax+8]
0x18002d4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4a6  mov     r8d, [rbp+178h]; nNumberOfBytesToRead
0x18002d4ad  lea     r9, [rbp+198h]; lpOverlapped
0x18002d4b4  mov     rdx, [rbp+170h]; lpBuffer
0x18002d4bb  lea     rax, ?static_ReadCompletionRoutine@CServerVCChannel@@CAXKKPEAU_OVERLAPPED@@@Z; CServerVCChannel::static_ReadCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x18002d4c2  mov     rcx, [rbp+158h]; hFile
0x18002d4c9  mov     [r9+18h], rbp
0x18002d4cd  mov     [rsp+48h+lpCompletionRoutine], rax; lpCompletionRoutine
0x18002d4d2  call    cs:__imp_ReadFileEx
0x18002d4d8  mov     edi, eax
0x18002d4da  call    cs:__imp_GetLastError
0x18002d4e0  mov     esi, eax
0x18002d4e2  test    edi, edi
0x18002d4e4  jz      short loc_18002D4ED
0x18002d4e6  xor     esi, esi
0x18002d4e8  jmp     loc_18002D5E9
0x18002d4ed  mov     rax, cs:WPP_GLOBAL_Control
0x18002d4f4  lea     rdi, WPP_GLOBAL_Control
0x18002d4fb  cmp     rax, rdi
0x18002d4fe  jz      short loc_18002D53B
0x18002d500  test    byte ptr [rax+1Ch], 1
0x18002d504  jz      short loc_18002D53B
0x18002d506  cmp     byte ptr [rax+19h], 2
0x18002d50a  jb      short loc_18002D53B
0x18002d50c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d511  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d518  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18002d51f  mov     edx, 0Fh
0x18002d524  mov     dword ptr [rsp+48h+lpCompletionRoutine], esi
0x18002d528  mov     r9d, eax
0x18002d52b  mov     rcx, [rcx+10h]
0x18002d52f  call    WPP_SF_Dd
0x18002d534  mov     rax, cs:WPP_GLOBAL_Control
0x18002d53b  test    esi, esi
0x18002d53d  jle     short loc_18002D54A
0x18002d53f  movzx   esi, si
0x18002d542  or      esi, 80070000h
0x18002d548  test    esi, esi
0x18002d54a  jns     short loc_18002D593
0x18002d54c  cmp     rax, rdi
0x18002d54f  jz      short loc_18002D597
0x18002d551  test    byte ptr [rax+1Ch], 8
0x18002d555  jz      short loc_18002D597
0x18002d557  cmp     byte ptr [rax+19h], 2
0x18002d55b  jb      short loc_18002D597
0x18002d55d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002d562  lea     rcx, aReadfileexFail; "ReadFileEx Failed"
0x18002d569  mov     [rsp+48h+var_20], esi
0x18002d56d  mov     [rsp+48h+lpCompletionRoutine], rcx
0x18002d572  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18002d579  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d580  mov     edx, 10h
0x18002d585  mov     r9d, eax
0x18002d588  mov     rcx, [rcx+10h]
0x18002d58c  call    WPP_SF_DsD
0x18002d591  jmp     short loc_18002D597
0x18002d593  test    esi, esi
0x18002d595  jz      short loc_18002D5E9
0x18002d597  lea     rdi, [rbp+48h]
0x18002d59b  cmp     [rdi], rbx
0x18002d59e  jz      short loc_18002D5BC
0x18002d5a0  lea     rcx, [rsp+48h+arg_0]
0x18002d5a5  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002d5aa  mov     rbx, [rdi]
0x18002d5ad  lea     rcx, [rsp+48h+arg_0]
0x18002d5b2  mov     [rsp+48h+arg_0], rbx
0x18002d5b7  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002d5bc  cmp     qword ptr [rdi], 0
0x18002d5c0  jz      short loc_18002D5D9
0x18002d5c2  mov     rcx, rdi
0x18002d5c5  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002d5ca  mov     rcx, rdi
0x18002d5cd  mov     qword ptr [rdi], 0
0x18002d5d4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18002d5d9  mov     rcx, [rbp+28h]
0x18002d5dd  mov     rax, [rcx]
0x18002d5e0  mov     rax, [rax+10h]
0x18002d5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5e9  lea     rcx, [rsp+48h+arg_8]; this
0x18002d5ee  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18002d5f3  test    rbx, rbx
0x18002d5f6  jz      short loc_18002D607
0x18002d5f8  mov     rcx, [rbx]
0x18002d5fb  mov     rax, [rcx+20h]
0x18002d5ff  mov     rcx, rbx
0x18002d602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d607  lea     rcx, [rsp+48h+arg_0]
0x18002d60c  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002d611  mov     rbx, [rsp+48h+arg_10]
0x18002d616  mov     eax, esi
0x18002d618  add     rsp, 30h
0x18002d61c  pop     rdi
0x18002d61d  pop     rsi
0x18002d61e  pop     rbp
0x18002d61f  retn
```
