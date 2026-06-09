# ThreadPoolHelper::Initialize(ulong,ulong)

- ea: `0x180076140`
- end: `0x1800764cf`
- name: `?Initialize@ThreadPoolHelper@@UEAAKKK@Z`
- size: `911`
- prototype: `__int64 __fastcall(ThreadPoolHelper *this, DWORD, DWORD)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007794`
- `0x1800077bc`
- `0x180076140`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18007641d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18007641d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007644e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007644e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180076468`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180076468`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180076445`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180076445`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180076410`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180076410`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180076359`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180076359`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800762b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800762b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007636f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007636f`

## string_xrefs

- `0x180076209`: `ThreadPoolHelper::Initialize`
- `0x180076258`: `ThreadPoolHelper::Initialize() called when helper is already initialized`
- `0x180076319`: `Thread Pool Creation Failed with error = %d`
- `0x1800763cb`: `Thread Pool Cleanup Group creation Failed with error = %d`

## pseudocode

```c
__int64 __fastcall ThreadPoolHelper::Initialize(ThreadPoolHelper *this, DWORD a2, DWORD a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  PTP_POOL Threadpool; // rax
  DWORD LastError; // eax
  PVOID *v10; // rcx
  PTP_CLEANUP_GROUP *v11; // rsi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD v13; // eax
  struct _TP_POOL *v14; // rcx
  unsigned int v16; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v18; // [rsp+30h] [rbp-D0h]
  __int128 v19; // [rsp+40h] [rbp-C0h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v16 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_1800AAC70 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"ThreadPoolHelper::Initialize",
      &v16,
      TPHTraceFunction);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 24) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_(v6[2], 11, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    if ( (_QWORD)xmmword_1800AAC70 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gTPHTemplateFunc)(
        gTPHEtwContext,
        xmmword_1800AAC70,
        L"ThreadPoolHelper::Initialize() called when helper is already initialized");
    v7 = 4317;
    goto LABEL_42;
  }
  *((_DWORD *)this + 6) = 3;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 21) = 1;
  *((_DWORD *)this + 22) = 72;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 1) = Threadpool;
  if ( !Threadpool )
  {
    LastError = GetLastError();
    v16 = LastError;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_86528d92fbe732626663791e96ffd76e_Traceguids, LastError);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800AAC70 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Thread Pool Creation Failed with error = %d", v16);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gTPHTemplateFunc)(
        gTPHEtwContext,
        xmmword_1800AAC70,
        &v23);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
    goto LABEL_31;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  v11 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
  *((_QWORD *)this + 2) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v14 = (struct _TP_POOL *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 4) = v14;
    *((_QWORD *)this + 5) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 6) = 0;
    SetThreadpoolThreadMaximum(v14, a2);
    SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 1), a3);
    goto LABEL_30;
  }
  v13 = GetLastError();
  v16 = v13;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_86528d92fbe732626663791e96ffd76e_Traceguids, v13);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (_QWORD)xmmword_1800AAC70 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Thread Pool Cleanup Group creation Failed with error = %d", v16);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gTPHTemplateFunc)(
      gTPHEtwContext,
      xmmword_1800AAC70,
      &v23);
LABEL_30:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_31:
  if ( v16 )
  {
    if ( *v11 )
    {
      CloseThreadpoolCleanupGroupMembers(*v11, 1, 0);
      CloseThreadpoolCleanupGroup(*v11);
      *v11 = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*((_QWORD *)this + 1) )
      goto LABEL_38;
    CloseThreadpool(*((PTP_POOL *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  else
  {
    *((_DWORD *)this + 24) = 1;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_38:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_(v10[2], 14, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
  v7 = v16;
LABEL_42:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v7;
}

```

## disassembly

```asm
0x180076140  push    rbp
0x180076142  push    rbx
0x180076143  push    rsi
0x180076144  push    rdi
0x180076145  push    r12
0x180076147  push    r14
0x180076149  push    r15
0x18007614b  lea     rbp, [rsp-770h]
0x180076153  sub     rsp, 870h
0x18007615a  mov     rax, cs:__security_cookie
0x180076161  xor     rax, rsp
0x180076164  mov     [rbp+7A0h+var_40], rax
0x18007616b  mov     r15d, r8d
0x18007616e  mov     r14d, edx
0x180076171  mov     rbx, rcx
0x180076174  xor     r12d, r12d
0x180076177  mov     [rsp+8A0h+var_880], r12d
0x18007617c  mov     [rsp+8A0h+var_840], r12d
0x180076181  xor     edx, edx; Val
0x180076183  mov     r8d, 7FCh; Size
0x180076189  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18007618e  call    memset_0
0x180076193  lea     rdi, WPP_GLOBAL_Control
0x18007619a  lea     rsi, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x1800761a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761a8  cmp     rcx, rdi
0x1800761ab  jz      short loc_1800761CB
0x1800761ad  test    byte ptr [rcx+1Ch], 8
0x1800761b1  jz      short loc_1800761CB
0x1800761b3  lea     edx, [r12+0Ah]
0x1800761b8  mov     r8, rsi
0x1800761bb  mov     rcx, [rcx+10h]
0x1800761bf  call    WPP_SF_
0x1800761c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800761cb  xorps   xmm0, xmm0
0x1800761ce  movdqu  [rsp+8A0h+var_870], xmm0
0x1800761d4  mov     [rsp+8A0h+var_878], r12
0x1800761d9  xorps   xmm1, xmm1
0x1800761dc  movdqu  [rsp+8A0h+var_860], xmm1
0x1800761e2  mov     [rsp+8A0h+var_850], r12
0x1800761e7  mov     [rsp+8A0h+var_848], 0FFFFFFFFh
0x1800761ef  mov     [rsp+8A0h+var_844], r12d
0x1800761f4  cmp     qword ptr cs:xmmword_1800AAC70+8, r12
0x1800761fb  jz      short loc_180076221
0x1800761fd  lea     r9, TPHTraceFunction; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180076204  lea     r8, [rsp+8A0h+var_880]; unsigned int *
0x180076209  lea     rdx, aThreadpoolhelp_3; "ThreadPoolHelper::Initialize"
0x180076210  lea     rcx, [rsp+8A0h+var_878]; this
0x180076215  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18007621a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076221  cmp     [rbx+60h], r12d
0x180076225  jz      short loc_18007627C
0x180076227  cmp     rcx, rdi
0x18007622a  jz      short loc_18007624C
0x18007622c  test    byte ptr [rcx+1Ch], 8
0x180076230  jz      short loc_18007624C
0x180076232  mov     edi, 1
0x180076237  cmp     [rcx+19h], dil
0x18007623b  jb      short loc_18007624C
0x18007623d  lea     edx, [rdi+0Ah]
0x180076240  mov     r8, rsi
0x180076243  mov     rcx, [rcx+10h]
0x180076247  call    WPP_SF_
0x18007624c  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x180076253  test    rdx, rdx
0x180076256  jz      short loc_180076272
0x180076258  lea     r8, aThreadpoolhelp_7; "ThreadPoolHelper::Initialize() called w"...
0x18007625f  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x180076266  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18007626d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076272  mov     ebx, 10DDh
0x180076277  jmp     loc_1800764A2
0x18007627c  mov     dword ptr [rbx+18h], 3
0x180076283  mov     [rbx+20h], r12
0x180076287  mov     [rbx+28h], r12
0x18007628b  mov     [rbx+30h], r12
0x18007628f  mov     [rbx+38h], r12
0x180076293  mov     [rbx+40h], r12
0x180076297  mov     [rbx+48h], r12
0x18007629b  mov     [rbx+50h], r12d
0x18007629f  mov     edi, 1
0x1800762a4  mov     [rbx+54h], edi
0x1800762a7  mov     dword ptr [rbx+58h], 48h ; 'H'
0x1800762ae  xor     ecx, ecx; reserved
0x1800762b0  call    cs:__imp_CreateThreadpool
0x1800762b6  mov     [rbx+8], rax
0x1800762ba  test    rax, rax
0x1800762bd  jnz     loc_180076359
0x1800762c3  call    cs:__imp_GetLastError
0x1800762c9  mov     [rsp+8A0h+var_880], eax
0x1800762cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800762d4  lea     r14, WPP_GLOBAL_Control
0x1800762db  cmp     rcx, r14
0x1800762de  jz      short loc_180076305
0x1800762e0  test    byte ptr [rcx+1Ch], 8
0x1800762e4  jz      short loc_180076305
0x1800762e6  cmp     [rcx+19h], dil
0x1800762ea  jb      short loc_180076305
0x1800762ec  lea     edx, [rdi+0Bh]
0x1800762ef  mov     r9d, eax
0x1800762f2  mov     r8, rsi
0x1800762f5  mov     rcx, [rcx+10h]
0x1800762f9  call    WPP_SF_d
0x1800762fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180076305  cmp     qword ptr cs:xmmword_1800AAC70, r12
0x18007630c  jz      short loc_180076350
0x18007630e  mov     word ptr [rsp+8A0h+var_840], r12w
0x180076314  mov     r8d, [rsp+8A0h+var_880]
0x180076319  lea     rdx, aThreadPoolCrea; "Thread Pool Creation Failed with error "...
0x180076320  lea     rcx, [rsp+8A0h+var_840]
0x180076325  call    FormatRRASErrorString
0x18007632a  lea     r8, [rsp+8A0h+var_840]
0x18007632f  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x180076336  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x18007633d  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180076344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076349  mov     rcx, cs:WPP_GLOBAL_Control
0x180076350  lea     rsi, [rbx+10h]
0x180076354  jmp     loc_180076431
0x180076359  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18007635f  lea     rsi, [rbx+10h]
0x180076363  mov     [rsi], rax
0x180076366  test    rax, rax
0x180076369  jnz     loc_1800763FD
0x18007636f  call    cs:__imp_GetLastError
0x180076375  mov     [rsp+8A0h+var_880], eax
0x180076379  mov     rcx, cs:WPP_GLOBAL_Control
0x180076380  lea     r14, WPP_GLOBAL_Control
0x180076387  cmp     rcx, r14
0x18007638a  jz      short loc_1800763B7
0x18007638c  test    byte ptr [rcx+1Ch], 8
0x180076390  jz      short loc_1800763B7
0x180076392  cmp     [rcx+19h], dil
0x180076396  jb      short loc_1800763B7
0x180076398  mov     edx, 0Dh
0x18007639d  mov     r9d, eax
0x1800763a0  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x1800763a7  mov     rcx, [rcx+10h]
0x1800763ab  call    WPP_SF_d
0x1800763b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800763b7  cmp     qword ptr cs:xmmword_1800AAC70, r12
0x1800763be  jz      short loc_180076431
0x1800763c0  mov     word ptr [rsp+8A0h+var_840], r12w
0x1800763c6  mov     r8d, [rsp+8A0h+var_880]
0x1800763cb  lea     rdx, aThreadPoolClea; "Thread Pool Cleanup Group creation Fail"...
0x1800763d2  lea     rcx, [rsp+8A0h+var_840]
0x1800763d7  call    FormatRRASErrorString
0x1800763dc  lea     r8, [rsp+8A0h+var_840]
0x1800763e1  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x1800763e8  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x1800763ef  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800763f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763fb  jmp     short loc_18007642A
0x1800763fd  mov     rcx, [rbx+8]; ptpp
0x180076401  mov     [rbx+20h], rcx
0x180076405  mov     [rbx+28h], rax
0x180076409  mov     [rbx+30h], r12
0x18007640d  mov     edx, r14d; cthrdMost
0x180076410  call    cs:__imp_SetThreadpoolThreadMaximum
0x180076416  mov     edx, r15d; cthrdMic
0x180076419  mov     rcx, [rbx+8]; ptpp
0x18007641d  call    cs:__imp_SetThreadpoolThreadMinimum
0x180076423  lea     r14, WPP_GLOBAL_Control
0x18007642a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076431  cmp     [rsp+8A0h+var_880], r12d
0x180076436  jz      short loc_180076474
0x180076438  cmp     [rsi], r12
0x18007643b  jz      short loc_18007645E
0x18007643d  xor     r8d, r8d; pvCleanupContext
0x180076440  mov     edx, edi; fCancelPendingCallbacks
0x180076442  mov     rcx, [rsi]; ptpcg
0x180076445  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18007644b  mov     rcx, [rsi]; ptpcg
0x18007644e  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180076454  mov     [rsi], r12
0x180076457  mov     rcx, cs:WPP_GLOBAL_Control
0x18007645e  cmp     [rbx+8], r12
0x180076462  jz      short loc_18007647E
0x180076464  mov     rcx, [rbx+8]; ptpp
0x180076468  call    cs:__imp_CloseThreadpool
0x18007646e  mov     [rbx+8], r12
0x180076472  jmp     short loc_180076477
0x180076474  mov     [rbx+60h], edi
0x180076477  mov     rcx, cs:WPP_GLOBAL_Control
0x18007647e  cmp     rcx, r14
0x180076481  jz      short loc_18007649E
0x180076483  test    byte ptr [rcx+1Ch], 8
0x180076487  jz      short loc_18007649E
0x180076489  mov     edx, 0Eh
0x18007648e  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x180076495  mov     rcx, [rcx+10h]
0x180076499  call    WPP_SF_
0x18007649e  mov     ebx, [rsp+8A0h+var_880]
0x1800764a2  lea     rcx, [rsp+8A0h+var_878]; this
0x1800764a7  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800764ac  mov     eax, ebx
0x1800764ae  mov     rcx, [rbp+7A0h+var_40]
0x1800764b5  xor     rcx, rsp; StackCookie
0x1800764b8  call    __security_check_cookie
0x1800764bd  add     rsp, 870h
0x1800764c4  pop     r15
0x1800764c6  pop     r14
0x1800764c8  pop     r12
0x1800764ca  pop     rdi
0x1800764cb  pop     rsi
0x1800764cc  pop     rbx
0x1800764cd  pop     rbp
0x1800764ce  retn
```
