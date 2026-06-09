# RADIUSAccounting::StopInterimAccouting(void)

- ea: `0x180061288`
- end: `0x180061456`
- name: `?StopInterimAccouting@RADIUSAccounting@@IEAAXXZ`
- size: `462`
- prototype: `void __fastcall(RADIUSAccounting *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18005f9b4`
- `0x180060f70`

## callees

- `0x180007794`
- `0x1800077bc`
- `0x180061288`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006137e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006137e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180061374`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180061374`

## string_xrefs

- `0x1800613cd`: `(Ignoring)DeleteTimerQueueTimer failed with error: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RADIUSAccounting::StopInterimAccouting(RADIUSAccounting *this)
{
  PVOID *v2; // rbx
  void *v3; // rdx
  DWORD LastError; // eax
  DWORD v5; // ebx
  __int64 v6; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v7; // [rsp+28h] [rbp-D8h]
  __int128 v8; // [rsp+38h] [rbp-C8h]
  __int64 v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+54h] [rbp-ACh]
  int v12; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  v7 = 0;
  v6 = 0;
  v8 = 0;
  v9 = 0;
  v10 = -1;
  v11 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v6,
      L"RADIUSAccounting::StopInterimAccouting",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    if ( !DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids, LastError);
      }
      if ( (_QWORD)xmmword_1800AABC0 )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"(Ignoring)DeleteTimerQueueTimer failed with error: %x", v5);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
          gBaseEtwContext,
          xmmword_1800AABC0,
          &v12);
      }
    }
    *((_QWORD *)this + 3) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x20000000) != 0 )
    WPP_SF_(v2[2], 34, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v6);
}

```

## disassembly

```asm
0x180061288  push    rbp
0x18006128a  push    rbx
0x18006128b  push    rdi
0x18006128c  push    r15
0x18006128e  lea     rbp, [rsp-778h]
0x180061296  sub     rsp, 878h
0x18006129d  mov     rax, cs:__security_cookie
0x1800612a4  xor     rax, rsp
0x1800612a7  mov     [rbp+790h+var_30], rax
0x1800612ae  mov     rdi, rcx
0x1800612b1  lea     r15, WPP_GLOBAL_Control
0x1800612b8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800612bf  cmp     rbx, r15
0x1800612c2  jz      short loc_1800612E9
0x1800612c4  test    dword ptr [rbx+1Ch], 20000000h
0x1800612cb  jz      short loc_1800612E9
0x1800612cd  mov     edx, 20h ; ' '
0x1800612d2  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x1800612d9  mov     rcx, [rbx+10h]
0x1800612dd  call    WPP_SF_
0x1800612e2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800612e9  xor     eax, eax
0x1800612eb  mov     [rsp+890h+var_830], eax
0x1800612ef  xor     edx, edx; Val
0x1800612f1  mov     r8d, 7FCh; Size
0x1800612f7  lea     rcx, [rsp+890h+var_82C]; void *
0x1800612fc  call    memset_0
0x180061301  xorps   xmm0, xmm0
0x180061304  movdqu  [rsp+890h+var_868], xmm0
0x18006130a  mov     [rsp+890h+var_870], 0
0x180061313  xorps   xmm1, xmm1
0x180061316  movdqu  [rsp+890h+var_858], xmm1
0x18006131c  mov     [rsp+890h+var_848], 0
0x180061325  mov     [rsp+890h+var_840], 0FFFFFFFFh
0x18006132d  mov     [rsp+890h+var_83C], 0
0x180061335  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18006133d  jz      short loc_180061361
0x18006133f  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180061346  xor     r8d, r8d; unsigned int *
0x180061349  lea     rdx, aRadiusaccounti_1; "RADIUSAccounting::StopInterimAccouting"
0x180061350  lea     rcx, [rsp+890h+var_870]; this
0x180061355  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18006135a  mov     rbx, cs:WPP_GLOBAL_Control
0x180061361  mov     rdx, [rdi+18h]; Timer
0x180061365  test    rdx, rdx
0x180061368  jz      loc_18006140C
0x18006136e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180061372  xor     ecx, ecx; TimerQueue
0x180061374  call    cs:__imp_DeleteTimerQueueTimer
0x18006137a  test    eax, eax
0x18006137c  jnz     short loc_1800613FD
0x18006137e  call    cs:__imp_GetLastError
0x180061384  mov     ebx, eax
0x180061386  mov     rcx, cs:WPP_GLOBAL_Control
0x18006138d  cmp     rcx, r15
0x180061390  jz      short loc_1800613B9
0x180061392  test    dword ptr [rcx+1Ch], 20000000h
0x180061399  jz      short loc_1800613B9
0x18006139b  cmp     byte ptr [rcx+19h], 1
0x18006139f  jb      short loc_1800613B9
0x1800613a1  mov     edx, 21h ; '!'
0x1800613a6  mov     r9d, eax
0x1800613a9  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x1800613b0  mov     rcx, [rcx+10h]
0x1800613b4  call    WPP_SF_d
0x1800613b9  cmp     qword ptr cs:xmmword_1800AABC0, 0
0x1800613c1  jz      short loc_1800613FD
0x1800613c3  xor     eax, eax
0x1800613c5  mov     word ptr [rsp+890h+var_830], ax
0x1800613ca  mov     r8d, ebx
0x1800613cd  lea     rdx, aIgnoringDelete; "(Ignoring)DeleteTimerQueueTimer failed "...
0x1800613d4  lea     rcx, [rsp+890h+var_830]
0x1800613d9  call    FormatRRASErrorString
0x1800613de  lea     r8, [rsp+890h+var_830]
0x1800613e3  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x1800613ea  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x1800613f1  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800613f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800613fd  mov     qword ptr [rdi+18h], 0
0x180061405  mov     rbx, cs:WPP_GLOBAL_Control
0x18006140c  cmp     rbx, r15
0x18006140f  jz      short loc_180061430
0x180061411  test    dword ptr [rbx+1Ch], 20000000h
0x180061418  jz      short loc_180061430
0x18006141a  mov     edx, 22h ; '"'
0x18006141f  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x180061426  mov     rcx, [rbx+10h]
0x18006142a  call    WPP_SF_
0x18006142f  nop
0x180061430  lea     rcx, [rsp+890h+var_870]; this
0x180061435  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18006143a  mov     rcx, [rbp+790h+var_30]
0x180061441  xor     rcx, rsp; StackCookie
0x180061444  call    __security_check_cookie
0x180061449  add     rsp, 878h
0x180061450  pop     r15
0x180061452  pop     rdi
0x180061453  pop     rbx
0x180061454  pop     rbp
0x180061455  retn
```
