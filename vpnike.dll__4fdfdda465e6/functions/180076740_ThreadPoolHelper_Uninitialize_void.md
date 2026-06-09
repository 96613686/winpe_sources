# ThreadPoolHelper::Uninitialize(void)

- ea: `0x180076740`
- end: `0x1800768cd`
- name: `?Uninitialize@ThreadPoolHelper@@UEAAKXZ`
- size: `397`
- prototype: `unsigned int __fastcall(ThreadPoolHelper *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180076114`

## callees

- `0x180007794`
- `0x180076740`
- `0x1800768d4`
- `0x180076b60`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007685f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007685f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180076876`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180076876`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180076855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180076855`

## string_xrefs

- `0x1800767d4`: `ThreadPoolHelper::Uninitialize`
- `0x180076824`: `ThreadPoolHelper::Uninitialize() called when helper is not initialized`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ThreadPoolHelper::Uninitialize(ThreadPoolHelper *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  struct _TP_CLEANUP_GROUP *v4; // rcx
  struct _TP_POOL *v5; // rcx
  __int64 v7; // [rsp+20h] [rbp-48h] BYREF
  __int128 v8; // [rsp+28h] [rbp-40h]
  __int128 v9; // [rsp+38h] [rbp-30h]
  __int64 v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+50h] [rbp-18h]
  int v12; // [rsp+54h] [rbp-14h]
  unsigned int v13; // [rsp+70h] [rbp+8h] BYREF

  v13 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = 0;
  if ( *((_QWORD *)&xmmword_1800AAC70 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v7,
      L"ThreadPoolHelper::Uninitialize",
      &v13,
      TPHTraceFunction);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 24) )
  {
    v4 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 2);
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 2));
      *((_QWORD *)this + 2) = 0;
    }
    v5 = (struct _TP_POOL *)*((_QWORD *)this + 1);
    if ( v5 )
    {
      CloseThreadpool(v5);
      *((_QWORD *)this + 1) = 0;
    }
    *((_DWORD *)this + 24) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    v3 = v13;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) )
      WPP_SF_(v2[2], 16, WPP_86528d92fbe732626663791e96ffd76e_Traceguids);
    if ( (_QWORD)xmmword_1800AAC70 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gTPHTemplateFunc)(
        gTPHEtwContext,
        xmmword_1800AAC70,
        L"ThreadPoolHelper::Uninitialize() called when helper is not initialized");
    v3 = 4317;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v7);
  return v3;
}

```

## disassembly

```asm
0x180076740  mov     [rsp+arg_8], rbx
0x180076745  push    rbp
0x180076746  sub     rsp, 60h
0x18007674a  mov     rbx, rcx
0x18007674d  mov     [rsp+68h+arg_0], 0
0x180076755  lea     rbp, WPP_GLOBAL_Control
0x18007675c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076763  cmp     rcx, rbp
0x180076766  jz      short loc_18007678A
0x180076768  test    byte ptr [rcx+1Ch], 8
0x18007676c  jz      short loc_18007678A
0x18007676e  mov     edx, 0Fh
0x180076773  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x18007677a  mov     rcx, [rcx+10h]
0x18007677e  call    WPP_SF_
0x180076783  mov     rcx, cs:WPP_GLOBAL_Control
0x18007678a  xorps   xmm0, xmm0
0x18007678d  movdqu  [rsp+68h+var_40], xmm0
0x180076793  mov     [rsp+68h+var_48], 0
0x18007679c  xorps   xmm1, xmm1
0x18007679f  movdqu  [rsp+68h+var_30], xmm1
0x1800767a5  mov     [rsp+68h+var_20], 0
0x1800767ae  mov     [rsp+68h+var_18], 0FFFFFFFFh
0x1800767b6  mov     [rsp+68h+var_14], 0
0x1800767be  cmp     qword ptr cs:xmmword_1800AAC70+8, 0
0x1800767c6  jz      short loc_1800767EC
0x1800767c8  lea     r9, TPHTraceFunction; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800767cf  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x1800767d4  lea     rdx, aThreadpoolhelp_1; "ThreadPoolHelper::Uninitialize"
0x1800767db  lea     rcx, [rsp+68h+var_48]; this
0x1800767e0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800767e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800767ec  cmp     dword ptr [rbx+60h], 0
0x1800767f0  jnz     short loc_180076845
0x1800767f2  cmp     rcx, rbp
0x1800767f5  jz      short loc_180076818
0x1800767f7  test    byte ptr [rcx+1Ch], 8
0x1800767fb  jz      short loc_180076818
0x1800767fd  cmp     byte ptr [rcx+19h], 1
0x180076801  jb      short loc_180076818
0x180076803  mov     edx, 10h
0x180076808  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x18007680f  mov     rcx, [rcx+10h]
0x180076813  call    WPP_SF_
0x180076818  mov     rdx, qword ptr cs:xmmword_1800AAC70
0x18007681f  test    rdx, rdx
0x180076822  jz      short loc_18007683E
0x180076824  lea     r8, aThreadpoolhelp_4; "ThreadPoolHelper::Uninitialize() called"...
0x18007682b  mov     rcx, cs:?gTPHEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gTPHEtwContext
0x180076832  mov     rax, cs:?gTPHTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gTPHTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180076839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007683e  mov     ebx, 10DDh
0x180076843  jmp     short loc_1800768B6
0x180076845  mov     rcx, [rbx+10h]; ptpcg
0x180076849  test    rcx, rcx
0x18007684c  jz      short loc_18007686D
0x18007684e  xor     r8d, r8d; pvCleanupContext
0x180076851  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180076855  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18007685b  mov     rcx, [rbx+10h]; ptpcg
0x18007685f  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180076865  mov     qword ptr [rbx+10h], 0
0x18007686d  mov     rcx, [rbx+8]; ptpp
0x180076871  test    rcx, rcx
0x180076874  jz      short loc_180076884
0x180076876  call    cs:__imp_CloseThreadpool
0x18007687c  mov     qword ptr [rbx+8], 0
0x180076884  mov     dword ptr [rbx+60h], 0
0x18007688b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076892  cmp     rcx, rbp
0x180076895  jz      short loc_1800768B2
0x180076897  test    byte ptr [rcx+1Ch], 8
0x18007689b  jz      short loc_1800768B2
0x18007689d  mov     edx, 11h
0x1800768a2  lea     r8, WPP_86528d92fbe732626663791e96ffd76e_Traceguids
0x1800768a9  mov     rcx, [rcx+10h]
0x1800768ad  call    WPP_SF_
0x1800768b2  mov     ebx, [rsp+68h+arg_0]
0x1800768b6  lea     rcx, [rsp+68h+var_48]; this
0x1800768bb  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800768c0  mov     eax, ebx
0x1800768c2  mov     rbx, [rsp+68h+arg_8]
0x1800768c7  add     rsp, 60h
0x1800768cb  pop     rbp
0x1800768cc  retn
```
