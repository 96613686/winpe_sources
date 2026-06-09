# BaseProtocolEngine::Uninitialize(void)

- ea: `0x18005e3f0`
- end: `0x18005e5e4`
- name: `?Uninitialize@BaseProtocolEngine@@QEAAKXZ`
- size: `500`
- prototype: `unsigned int __fastcall(BaseProtocolEngine *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006d90`
- `0x18005e008`
- `0x18005e148`

## callees

- `0x180001564`
- `0x180007794`
- `0x18005e3f0`
- `0x180076114`
- `0x1800768d4`
- `0x180076b60`
- `0x18007a010`

## string_xrefs

- `0x18005e47f`: `BaseProtocolEngine::Uninitialize`
- `0x18005e4d5`: `BaseProtocolEngine is not intialized. Invalid operation`
- `0x18005e55b`: `ThreadPool failed to Uninitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BaseProtocolEngine::Uninitialize(BaseProtocolEngine *this)
{
  PVOID *v2; // rcx
  __int64 v3; // rcx
  void *v4; // rdi
  unsigned int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-48h] BYREF
  __int128 v8; // [rsp+28h] [rbp-40h]
  __int128 v9; // [rsp+38h] [rbp-30h]
  __int64 v10; // [rsp+48h] [rbp-20h]
  int v11; // [rsp+50h] [rbp-18h]
  int v12; // [rsp+54h] [rbp-14h]
  unsigned int v13; // [rsp+90h] [rbp+28h] BYREF

  v13 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = 0;
  v7 = 0;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  v12 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v7,
      L"BaseProtocolEngine::Uninitialize",
      &v13,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 8) )
  {
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids);
        }
        if ( (_QWORD)xmmword_1800AABC0 )
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
            gBaseEtwContext,
            xmmword_1800AABC0,
            L"ThreadPool failed to Uninitialize");
      }
      v4 = (void *)*((_QWORD *)this + 3);
      if ( v4 )
      {
        ThreadPoolHelper::~ThreadPoolHelper(*((ThreadPoolHelper **)this + 3));
        operator delete(v4);
      }
      *((_QWORD *)this + 3) = 0;
    }
    *((_QWORD *)this + 2) = 0;
    *((_DWORD *)this + 8) = 0;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) )
    {
      WPP_SF_(v2[2], 17, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800AABC0 )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
        gBaseEtwContext,
        xmmword_1800AABC0,
        L"BaseProtocolEngine is not intialized. Invalid operation");
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = 4317;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_(v2[2], 19, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids);
  v5 = v13;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18005e3f0  push    rbp
0x18005e3f2  push    rbx
0x18005e3f3  push    rdi
0x18005e3f4  push    r15
0x18005e3f6  mov     rbp, rsp
0x18005e3f9  sub     rsp, 68h
0x18005e3fd  mov     rbx, rcx
0x18005e400  mov     [rbp+arg_0], 0
0x18005e407  lea     r15, WPP_GLOBAL_Control
0x18005e40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e415  cmp     rcx, r15
0x18005e418  jz      short loc_18005E43C
0x18005e41a  test    byte ptr [rcx+1Ch], 1
0x18005e41e  jz      short loc_18005E43C
0x18005e420  mov     edx, 10h
0x18005e425  lea     r8, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids
0x18005e42c  mov     rcx, [rcx+10h]
0x18005e430  call    WPP_SF_
0x18005e435  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e43c  xorps   xmm0, xmm0
0x18005e43f  movdqu  [rbp+var_40], xmm0
0x18005e444  mov     [rbp+var_48], 0
0x18005e44c  xorps   xmm1, xmm1
0x18005e44f  movdqu  [rbp+var_30], xmm1
0x18005e454  mov     [rbp+var_20], 0
0x18005e45c  mov     [rbp+var_18], 0FFFFFFFFh
0x18005e463  mov     [rbp+var_14], 0
0x18005e46a  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18005e472  jz      short loc_18005E496
0x18005e474  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18005e47b  lea     r8, [rbp+arg_0]; unsigned int *
0x18005e47f  lea     rdx, aBaseprotocolen_0; "BaseProtocolEngine::Uninitialize"
0x18005e486  lea     rcx, [rbp+var_48]; this
0x18005e48a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18005e48f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e496  cmp     dword ptr [rbx+20h], 0
0x18005e49a  jnz     short loc_18005E502
0x18005e49c  cmp     rcx, r15
0x18005e49f  jz      short loc_18005E4C9
0x18005e4a1  test    byte ptr [rcx+1Ch], 1
0x18005e4a5  jz      short loc_18005E4C9
0x18005e4a7  cmp     byte ptr [rcx+19h], 1
0x18005e4ab  jb      short loc_18005E4C9
0x18005e4ad  mov     edx, 11h
0x18005e4b2  lea     r8, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids
0x18005e4b9  mov     rcx, [rcx+10h]
0x18005e4bd  call    WPP_SF_
0x18005e4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e4c9  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005e4d0  test    rdx, rdx
0x18005e4d3  jz      short loc_18005E4F6
0x18005e4d5  lea     r8, aBaseprotocolen_2; "BaseProtocolEngine is not intialized. I"...
0x18005e4dc  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005e4e3  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e4f6  mov     [rbp+arg_0], 10DDh
0x18005e4fd  jmp     loc_18005E5AC
0x18005e502  mov     rcx, [rbx+18h]
0x18005e506  test    rcx, rcx
0x18005e509  jz      loc_18005E596
0x18005e50f  mov     rax, [rcx]
0x18005e512  mov     rax, [rax+8]
0x18005e516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e51b  mov     [rbp+arg_0], eax
0x18005e51e  test    eax, eax
0x18005e520  jz      short loc_18005E575
0x18005e522  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e529  cmp     rcx, r15
0x18005e52c  jz      short loc_18005E54F
0x18005e52e  test    byte ptr [rcx+1Ch], 1
0x18005e532  jz      short loc_18005E54F
0x18005e534  cmp     byte ptr [rcx+19h], 1
0x18005e538  jb      short loc_18005E54F
0x18005e53a  mov     edx, 12h
0x18005e53f  lea     r8, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids
0x18005e546  mov     rcx, [rcx+10h]
0x18005e54a  call    WPP_SF_
0x18005e54f  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005e556  test    rdx, rdx
0x18005e559  jz      short loc_18005E575
0x18005e55b  lea     r8, aThreadpoolFail; "ThreadPool failed to Uninitialize"
0x18005e562  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005e569  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e575  mov     rdi, [rbx+18h]
0x18005e579  test    rdi, rdi
0x18005e57c  jz      short loc_18005E58E
0x18005e57e  mov     rcx, rdi; this
0x18005e581  call    ??1ThreadPoolHelper@@QEAA@XZ; ThreadPoolHelper::~ThreadPoolHelper(void)
0x18005e586  mov     rcx, rdi; Block
0x18005e589  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e58e  mov     qword ptr [rbx+18h], 0
0x18005e596  mov     qword ptr [rbx+10h], 0
0x18005e59e  mov     dword ptr [rbx+20h], 0
0x18005e5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e5ac  cmp     rcx, r15
0x18005e5af  jz      short loc_18005E5CC
0x18005e5b1  test    byte ptr [rcx+1Ch], 1
0x18005e5b5  jz      short loc_18005E5CC
0x18005e5b7  mov     edx, 13h
0x18005e5bc  lea     r8, WPP_80d5af5ed9fb312d7684d6cfdd7cc3ec_Traceguids
0x18005e5c3  mov     rcx, [rcx+10h]
0x18005e5c7  call    WPP_SF_
0x18005e5cc  mov     ebx, [rbp+arg_0]
0x18005e5cf  lea     rcx, [rbp+var_48]; this
0x18005e5d3  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18005e5d8  mov     eax, ebx
0x18005e5da  add     rsp, 68h
0x18005e5de  pop     r15
0x18005e5e0  pop     rdi
0x18005e5e1  pop     rbx
0x18005e5e2  pop     rbp
0x18005e5e3  retn
```
