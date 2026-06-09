# ThreadPoolHelper::QueueWorkItem(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,ulong)

- ea: `0x1800764e0`
- end: `0x18007672b`
- name: `?QueueWorkItem@ThreadPoolHelper@@UEAAKP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1K@Z`
- size: `587`
- prototype: `__int64 __fastcall(ThreadPoolHelper *this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180007794`
- `0x1800077bc`
- `0x1800764e0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800766d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800766d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007662d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007662d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800766c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800766c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007663f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007663f`

## string_xrefs

- `0x1800765af`: `ThreadPoolHelper::QueueWorkItem`
- `0x1800765ff`: `ThreadPoolHelper::QueueWorkItem() called when helper is not initialized`
- `0x180076693`: `ThreadPoolHelper::QueueWorkItem() CreateThreadpoolWork failed with error = %d`

## pseudocode

```c
__int64 __fastcall ThreadPoolHelper::QueueWorkItem(
        ThreadPoolHelper *this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *),
        void *a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v9; // rbx
  DWORD LastError; // eax
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+30h] [rbp-D0h]
  __int128 v15; // [rsp+40h] [rbp-C0h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v12 = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_1800AAC70 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"ThreadPoolHelper::QueueWorkItem",
      &v12,
      TPHTraceFunction);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)this + 24) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_(v6[2], 19, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    if ( (_QWORD)xmmword_1800AAC70 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gTPHTemplateFunc)(
        gTPHEtwContext,
        xmmword_1800AAC70,
        L"ThreadPoolHelper::QueueWorkItem() called when helper is not initialized");
    v7 = 4317;
    goto LABEL_25;
  }
  ThreadpoolWork = CreateThreadpoolWork(a2, a3, (PTP_CALLBACK_ENVIRON)((char *)this + 24));
  v9 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    goto LABEL_24;
  }
  LastError = GetLastError();
  v7 = LastError;
  v12 = LastError;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_86528d92fbe732626663791e96ffd76e_Traceguids, LastError);
    v7 = v12;
  }
  if ( (_QWORD)xmmword_1800AAC70 )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"ThreadPoolHelper::QueueWorkItem() CreateThreadpoolWork failed with error = %d", v7);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gTPHTemplateFunc)(
      gTPHEtwContext,
      xmmword_1800AAC70,
      &v19);
LABEL_24:
    v7 = v12;
  }
LABEL_25:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v7;
}

```

## disassembly

```asm
0x1800764e0  push    rbp
0x1800764e2  push    rbx
0x1800764e3  push    rsi
0x1800764e4  push    rdi
0x1800764e5  push    r13
0x1800764e7  lea     rbp, [rsp-770h]
0x1800764ef  sub     rsp, 870h
0x1800764f6  mov     rax, cs:__security_cookie
0x1800764fd  xor     rax, rsp
0x180076500  mov     [rbp+790h+var_30], rax
0x180076507  mov     rsi, r8
0x18007650a  mov     rdi, rdx
0x18007650d  mov     rbx, rcx
0x180076510  mov     [rsp+890h+var_870], 0
0x180076518  xor     eax, eax
0x18007651a  mov     [rsp+890h+var_830], eax
0x18007651e  xor     edx, edx; Val
0x180076520  mov     r8d, 7FCh; Size
0x180076526  lea     rcx, [rsp+890h+var_82C]; void *
0x18007652b  call    memset_0
0x180076530  lea     r13, WPP_GLOBAL_Control
0x180076537  mov     rcx, cs:WPP_GLOBAL_Control
0x18007653e  cmp     rcx, r13
0x180076541  jz      short loc_180076565
0x180076543  test    byte ptr [rcx+1Ch], 8
0x180076547  jz      short loc_180076565
0x180076549  mov     edx, 12h
0x18007654e  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x180076555  mov     rcx, [rcx+10h]
0x180076559  call    WPP_SF_
0x18007655e  mov     rcx, cs:WPP_GLOBAL_Control
0x180076565  xorps   xmm0, xmm0
0x180076568  movdqu  [rsp+890h+var_860], xmm0
0x18007656e  mov     [rsp+890h+var_868], 0
0x180076577  xorps   xmm1, xmm1
0x18007657a  movdqu  [rsp+890h+var_850], xmm1
0x180076580  mov     [rsp+890h+var_840], 0
0x180076589  mov     [rsp+890h+var_838], 0FFFFFFFFh
0x180076591  mov     [rsp+890h+var_834], 0
0x180076599  cmp     qword ptr cs:xmmword_1800AAC70+8, 0
0x1800765a1  jz      short loc_1800765C7
0x1800765a3  lea     r9, TPHTraceFunction; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800765aa  lea     r8, [rsp+890h+var_870]; unsigned int *
0x1800765af  lea     rdx, aThreadpoolhelp_2; "ThreadPoolHelper::QueueWorkItem"
0x1800765b6  lea     rcx, [rsp+890h+var_868]; this
0x1800765bb  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800765c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800765c7  cmp     dword ptr [rbx+60h], 0
0x1800765cb  jnz     short loc_180076623
0x1800765cd  cmp     rcx, r13
0x1800765d0  jz      short loc_1800765F3
0x1800765d2  test    byte ptr [rcx+1Ch], 8
0x1800765d6  jz      short loc_1800765F3
0x1800765d8  cmp     byte ptr [rcx+19h], 1
0x1800765dc  jb      short loc_1800765F3
0x1800765de  mov     edx, 13h
0x1800765e3  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x1800765ea  mov     rcx, [rcx+10h]
0x1800765ee  call    WPP_SF_
0x1800765f3  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x1800765fa  test    rdx, rdx
0x1800765fd  jz      short loc_180076619
0x1800765ff  lea     r8, aThreadpoolhelp_6; "ThreadPoolHelper::QueueWorkItem() calle"...
0x180076606  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x18007660d  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180076614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076619  mov     ebx, 10DDh
0x18007661e  jmp     loc_180076702
0x180076623  lea     r8, [rbx+18h]; pcbe
0x180076627  mov     rdx, rsi; pv
0x18007662a  mov     rcx, rdi; pfnwk
0x18007662d  call    cs:__imp_CreateThreadpoolWork
0x180076633  mov     rbx, rax
0x180076636  test    rax, rax
0x180076639  jnz     loc_1800766C5
0x18007663f  call    cs:__imp_GetLastError
0x180076645  mov     ebx, eax
0x180076647  mov     [rsp+890h+var_870], eax
0x18007664b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076652  cmp     rcx, r13
0x180076655  jz      short loc_18007667F
0x180076657  test    byte ptr [rcx+1Ch], 8
0x18007665b  jz      short loc_18007667F
0x18007665d  cmp     byte ptr [rcx+19h], 1
0x180076661  jb      short loc_18007667F
0x180076663  mov     edx, 14h
0x180076668  mov     r9d, eax
0x18007666b  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x180076672  mov     rcx, [rcx+10h]
0x180076676  call    WPP_SF_d
0x18007667b  mov     ebx, [rsp+890h+var_870]
0x18007667f  cmp     qword ptr cs:xmmword_1800AAC70, 0
0x180076687  jz      short loc_180076702
0x180076689  xor     eax, eax
0x18007668b  mov     word ptr [rsp+890h+var_830], ax
0x180076690  mov     r8d, ebx
0x180076693  lea     rdx, aThreadpoolhelp_5; "ThreadPoolHelper::QueueWorkItem() Creat"...
0x18007669a  lea     rcx, [rsp+890h+var_830]
0x18007669f  call    FormatRRASErrorString
0x1800766a4  lea     r8, [rsp+890h+var_830]
0x1800766a9  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x1800766b0  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x1800766b7  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800766be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766c3  jmp     short loc_1800766FE
0x1800766c5  mov     rcx, rbx; pwk
0x1800766c8  call    cs:__imp_SubmitThreadpoolWork
0x1800766ce  mov     rcx, rbx; pwk
0x1800766d1  call    cs:__imp_CloseThreadpoolWork
0x1800766d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800766de  cmp     rcx, r13
0x1800766e1  jz      short loc_1800766FE
0x1800766e3  test    byte ptr [rcx+1Ch], 8
0x1800766e7  jz      short loc_1800766FE
0x1800766e9  mov     edx, 15h
0x1800766ee  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x1800766f5  mov     rcx, [rcx+10h]
0x1800766f9  call    WPP_SF_
0x1800766fe  mov     ebx, [rsp+890h+var_870]
0x180076702  lea     rcx, [rsp+890h+var_868]; this
0x180076707  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18007670c  mov     eax, ebx
0x18007670e  mov     rcx, [rbp+790h+var_30]
0x180076715  xor     rcx, rsp; StackCookie
0x180076718  call    __security_check_cookie
0x18007671d  add     rsp, 870h
0x180076724  pop     r13
0x180076726  pop     rdi
0x180076727  pop     rsi
0x180076728  pop     rbx
0x180076729  pop     rbp
0x18007672a  retn
```
