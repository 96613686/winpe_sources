# VidNotificationDispatcher::RegisterMmioHandler(unsigned __int64,unsigned __int64,void *,IVndCallback &,int,void * &)

- ea: `0x140033e9c`
- end: `0x14003417c`
- name: `?RegisterMmioHandler@VidNotificationDispatcher@@QEAAJ_K0PEAXAEAUIVndCallback@@HAEAPEAX@Z`
- size: `736`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, void *@<r9>, struct IVndCallback *, int, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027f780`

## callees

- `0x140033e9c`
- `0x140035238`
- `0x140035514`
- `0x140035620`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x1400cb87c`
- `0x14011ee30`
- `0x1402816b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400340c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033ee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033ee0`
- `vid!VidCreateMmioGpaRange` at `0x1400340b3`
- `vid!VidCreateMmioGpaRange` at `0x1400340b3`

## string_xrefs

- `0x14003416a`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VidNotificationDispatcher::RegisterMmioHandler(
        VidNotificationDispatcher *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        void *a4,
        struct IVndCallback *a5,
        int a6,
        void **a7)
{
  volatile signed __int32 *v11; // rdi
  DWORD CurrentThreadId; // esi
  __int64 v13; // r8
  unsigned __int32 v14; // eax
  unsigned __int32 v15; // edx
  signed int v16; // ebx
  __int64 v17; // rcx
  __int64 HandlerContext; // rsi
  signed int LastError; // eax
  _OWORD *v20; // rax
  _QWORD *v21; // rax
  signed int v22; // eax
  bool v23; // sf
  unsigned int v25; // [rsp+20h] [rbp-88h]
  _QWORD v26[3]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v27[88]; // [rsp+50h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v26[0] = a7;
  v11 = (volatile signed __int32 *)((char *)this + 5824);
  CurrentThreadId = GetCurrentThreadId();
  v14 = _InterlockedCompareExchange(v11, 1, 0);
  if ( v14 )
  {
    if ( *((_DWORD *)v11 + 1) == CurrentThreadId )
    {
      _InterlockedAdd(v11 + 2, 1u);
      goto LABEL_8;
    }
    do
    {
      while ( (v14 & 1) != 0 || v14 >= 4 )
      {
        LOBYTE(v13) = 1;
        if ( !(unsigned int)RrwpLockWait(v11, 0xFFFFFFFFLL, v13) )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2FE,
            (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
            (const char *)0x102,
            v25);
        _m_prefetchw((const void *)v11);
        v14 = *v11;
      }
      v15 = v14;
      v14 = _InterlockedCompareExchange(v11, v14 + 1, v14);
    }
    while ( v14 != v15 );
  }
  _InterlockedExchange(v11 + 1, CurrentThreadId);
LABEL_8:
  v26[2] = v11;
  if ( (unsigned int)VidNotificationDispatcher::VerifyUnhandledMmioRange(this, a2, a3) )
  {
    HandlerContext = VidNotificationDispatcher::CreateHandlerContext(this, 0, a4, a5);
    if ( !HandlerContext )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x291,
        (unsigned int)"onecore\\vm\\worker\\vidpartition\\vnd.cpp",
        (const char *)0x8000FFFFLL,
        a6);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402E5730);
      goto LABEL_32;
    }
    v20 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v20 )
    {
      *v20 = 0;
      v20[1] = 0;
    }
    *(_QWORD *)(HandlerContext + 192) = v20;
    if ( !v20 )
    {
      v16 = -2147024882;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecore\\vm\\worker\\vidpartition\\vnd.cpp",
        (const char *)0x8000FFFFLL,
        a6);
      if ( (unsigned int)VmlIsDebugTraceEnabled(0) )
        VmlDebugTraceEx(0, &off_1402E5820);
      goto LABEL_35;
    }
    *(_QWORD *)(HandlerContext + 176) = a2;
    *(_QWORD *)(HandlerContext + 184) = a3;
    v21 = v20 + 1;
    v21[1] = v21;
    *v21 = v21;
    if ( (unsigned int)VidCreateMmioGpaRange(*((_QWORD *)this + 5), a2, a3, HandlerContext, HandlerContext + 112) )
    {
      *(_QWORD *)v26[0] = HandlerContext;
      *(_DWORD *)(HandlerContext + 136) = 1;
      _InterlockedExchange((volatile __int32 *)this + 192, 1);
      v26[0] = a2;
      v26[1] = HandlerContext;
      std::_Tree<std::_Tmap_traits<unsigned __int64,VND_HANDLER_CONTEXT *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,VND_HANDLER_CONTEXT *>>,0>>::_Emplace<std::pair<unsigned __int64,VND_HANDLER_CONTEXT *>>(
        (char *)this + 80,
        v27,
        v26);
      v16 = 0;
      goto LABEL_37;
    }
    v22 = GetLastError();
    v16 = v22;
    if ( (v22 & 0x1FFF0000) != 0 )
    {
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v16 = v22 & 0xFFFFFFF | 0x80000000;
        goto LABEL_32;
      }
    }
    else
    {
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v16 = (unsigned __int16)v22 | 0x80070000;
LABEL_32:
        v23 = v16 < 0;
      }
    }
    if ( !v23 || !HandlerContext )
      goto LABEL_37;
LABEL_35:
    VidNotificationDispatcher::DeleteHandlerContext(this, (struct VND_HANDLER_CONTEXT *)HandlerContext);
    goto LABEL_37;
  }
  v16 = -2147024883;
  if ( g_BreakOnChildAssert )
    v17 = 0;
  else
    v17 = 0x4000;
  if ( (unsigned int)VmlIsDebugTraceEnabled(v17) )
    VmlDebugTraceEx(g_BreakOnChildAssert == 0 ? 0x4000 : 0, &off_1402E5748);
LABEL_37:
  RrwLockRelease(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140033e9c  push    rbx
0x140033e9e  push    rbp
0x140033e9f  push    rsi
0x140033ea0  push    rdi
0x140033ea1  push    r12
0x140033ea3  push    r13
0x140033ea5  push    r14
0x140033ea7  push    r15
0x140033ea9  sub     rsp, 68h
0x140033ead  mov     r12, r9
0x140033eb0  mov     r15, r8
0x140033eb3  mov     r14, rdx
0x140033eb6  mov     rbp, rcx
0x140033eb9  mov     r13, [rsp+0A8h+arg_20]
0x140033ec1  mov     eax, [rsp+0A8h+arg_28]
0x140033ec8  mov     [rsp+0A8h+var_78], eax
0x140033ecc  mov     rax, [rsp+0A8h+arg_30]
0x140033ed4  mov     [rsp+0A8h+var_70], rax
0x140033ed9  lea     rdi, [rcx+16C0h]
0x140033ee0  call    cs:__imp_GetCurrentThreadId
0x140033ee7  nop     dword ptr [rax+rax+00h]
0x140033eec  mov     esi, eax
0x140033eee  mov     ebx, 1
0x140033ef3  xor     eax, eax
0x140033ef5  lock cmpxchg [rdi], ebx
0x140033ef9  jz      short loc_140033F1E
0x140033efb  mov     ecx, [rdi+4]
0x140033efe  cmp     ecx, esi
0x140033f00  jnz     short loc_140033F08
0x140033f02  lock add [rdi+8], ebx
0x140033f06  jmp     short loc_140033F21
0x140033f08  test    bl, al
0x140033f0a  jnz     short loc_140033F4E
0x140033f0c  cmp     eax, 4
0x140033f0f  jnb     short loc_140033F4E
0x140033f11  mov     edx, eax
0x140033f13  lea     ecx, [rax+1]
0x140033f16  lock cmpxchg [rdi], ecx
0x140033f1a  cmp     eax, edx
0x140033f1c  jnz     short loc_140033F08
0x140033f1e  xchg    esi, [rdi+4]
0x140033f21  mov     [rsp+0A8h+var_60], rdi
0x140033f26  mov     r8, r15; unsigned __int64
0x140033f29  mov     rdx, r14; unsigned __int64
0x140033f2c  mov     rcx, rbp; this
0x140033f2f  call    ?VerifyUnhandledMmioRange@VidNotificationDispatcher@@QEAAH_K0@Z; VidNotificationDispatcher::VerifyUnhandledMmioRange(unsigned __int64,unsigned __int64)
0x140033f34  test    eax, eax
0x140033f36  jnz     short loc_140033F99
0x140033f38  mov     ebx, 8007000Dh
0x140033f3d  mov     esi, 4000h
0x140033f42  cmp     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x140033f48  jz      short loc_140033F6B
0x140033f4a  xor     ecx, ecx
0x140033f4c  jmp     short loc_140033F6D
0x140033f4e  mov     r8b, bl
0x140033f51  or      edx, 0FFFFFFFFh
0x140033f54  mov     rcx, rdi
0x140033f57  call    RrwpLockWait
0x140033f5c  test    eax, eax
0x140033f5e  jz      loc_14003415C
0x140033f64  prefetchw byte ptr [rdi]
0x140033f67  mov     eax, [rdi]
0x140033f69  jmp     short loc_140033F08
0x140033f6b  mov     ecx, esi
0x140033f6d  call    VmlIsDebugTraceEnabled
0x140033f72  test    eax, eax
0x140033f74  jz      loc_140034140
0x140033f7a  mov     eax, cs:?g_BreakOnChildAssert@@3HA; int g_BreakOnChildAssert
0x140033f80  neg     eax
0x140033f82  sbb     ecx, ecx
0x140033f84  not     ecx
0x140033f86  and     ecx, esi
0x140033f88  lea     rdx, off_1402E5748; "Unexpected error.\n"
0x140033f8f  call    VmlDebugTraceEx
0x140033f94  jmp     loc_140034140
0x140033f99  mov     eax, [rsp+0A8h+var_78]
0x140033f9d  mov     [rsp+0A8h+var_88], eax; int
0x140033fa1  mov     r9, r13
0x140033fa4  mov     r8, r12
0x140033fa7  xor     edx, edx
0x140033fa9  mov     rcx, rbp
0x140033fac  call    ?CreateHandlerContext@VidNotificationDispatcher@@AEAAPEAUVND_HANDLER_CONTEXT@@W4_VND_HANDLER_TYPE@@PEAXPEAUIVndCallback@@H@Z; VidNotificationDispatcher::CreateHandlerContext(_VND_HANDLER_TYPE,void *,IVndCallback *,int)
0x140033fb1  mov     rsi, rax
0x140033fb4  test    rax, rax
0x140033fb7  jnz     short loc_140034015
0x140033fb9  call    cs:__imp_GetLastError
0x140033fc0  nop     dword ptr [rax+rax+00h]
0x140033fc5  mov     ebx, eax
0x140033fc7  test    eax, eax
0x140033fc9  jle     short loc_140033FD4
0x140033fcb  movzx   ebx, ax
0x140033fce  or      ebx, 80070000h
0x140033fd4  mov     rcx, [rsp+0A8h]; this
0x140033fdc  mov     r9d, 8000FFFFh; char *
0x140033fe2  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x140033fe9  mov     edx, 291h; void *
0x140033fee  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140033ff3  xor     ecx, ecx
0x140033ff5  call    VmlIsDebugTraceEnabled
0x140033ffa  test    eax, eax
0x140033ffc  jz      loc_1400340F7
0x140034002  lea     rdx, off_1402E5730; "Unexpected error.\n"
0x140034009  xor     ecx, ecx
0x14003400b  call    VmlDebugTraceEx
0x140034010  jmp     loc_1400340F7
0x140034015  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003401c  mov     ecx, 20h ; ' '; unsigned __int64
0x140034021  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140034026  test    rax, rax
0x140034029  jz      short loc_140034035
0x14003402b  xorps   xmm0, xmm0
0x14003402e  movups  xmmword ptr [rax], xmm0
0x140034031  movups  xmmword ptr [rax+10h], xmm0
0x140034035  mov     [rsi+0C0h], rax
0x14003403c  test    rax, rax
0x14003403f  jnz     short loc_140034084
0x140034041  mov     ebx, 8007000Eh
0x140034046  mov     rcx, [rsp+0A8h]; this
0x14003404e  mov     r9d, 8000FFFFh; char *
0x140034054  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x14003405b  mov     edx, 299h; void *
0x140034060  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140034065  xor     ecx, ecx
0x140034067  call    VmlIsDebugTraceEnabled
0x14003406c  test    eax, eax
0x14003406e  jz      loc_140034100
0x140034074  lea     rdx, off_1402E5820; "Unexpected error.\n"
0x14003407b  xor     ecx, ecx
0x14003407d  call    VmlDebugTraceEx
0x140034082  jmp     short loc_140034100
0x140034084  mov     [rsi+0B0h], r14
0x14003408b  mov     [rsi+0B8h], r15
0x140034092  add     rax, 10h
0x140034096  mov     [rax+8], rax
0x14003409a  mov     [rax], rax
0x14003409d  lea     rax, [rsi+70h]
0x1400340a1  mov     qword ptr [rsp+0A8h+var_88], rax
0x1400340a6  mov     r9, rsi
0x1400340a9  mov     r8, r15
0x1400340ac  mov     rdx, r14
0x1400340af  mov     rcx, [rbp+28h]
0x1400340b3  call    cs:__imp_VidCreateMmioGpaRange
0x1400340ba  nop     dword ptr [rax+rax+00h]
0x1400340bf  test    eax, eax
0x1400340c1  jnz     short loc_14003410D
0x1400340c3  call    cs:__imp_GetLastError
0x1400340ca  nop     dword ptr [rax+rax+00h]
0x1400340cf  mov     ebx, eax
0x1400340d1  test    eax, 1FFF0000h
0x1400340d6  jnz     short loc_1400340E7
0x1400340d8  test    eax, eax
0x1400340da  jle     short loc_1400340F9
0x1400340dc  movzx   ebx, bx
0x1400340df  or      ebx, 80070000h
0x1400340e5  jmp     short loc_1400340F7
0x1400340e7  test    ebx, ebx
0x1400340e9  jle     short loc_1400340F9
0x1400340eb  and     ebx, 0FFFFFFFh
0x1400340f1  or      ebx, 80000000h
0x1400340f7  test    ebx, ebx
0x1400340f9  jns     short loc_140034140
0x1400340fb  test    rsi, rsi
0x1400340fe  jz      short loc_140034140
0x140034100  mov     rdx, rsi; struct VND_HANDLER_CONTEXT *
0x140034103  mov     rcx, rbp; this
0x140034106  call    ?DeleteHandlerContext@VidNotificationDispatcher@@AEAAXPEAUVND_HANDLER_CONTEXT@@@Z; VidNotificationDispatcher::DeleteHandlerContext(VND_HANDLER_CONTEXT *)
0x14003410b  jmp     short loc_140034140
0x14003410d  mov     rax, [rsp+0A8h+var_70]
0x140034112  mov     [rax], rsi
0x140034115  mov     [rsi+88h], ebx
0x14003411b  xchg    ebx, [rbp+300h]
0x140034121  mov     [rsp+0A8h+var_70], r14
0x140034126  mov     [rsp+0A8h+var_68], rsi
0x14003412b  lea     rcx, [rbp+50h]
0x14003412f  lea     r8, [rsp+0A8h+var_70]
0x140034134  lea     rdx, [rsp+0A8h+var_58]
0x140034139  call    ??$_Emplace@U?$pair@_KPEAUVND_HANDLER_CONTEXT@@@std@@@?$_Tree@V?$_Tmap_traits@_KPEAUVND_HANDLER_CONTEXT@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAUVND_HANDLER_CONTEXT@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,VND_HANDLER_CONTEXT *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,VND_HANDLER_CONTEXT *>>,0>>::_Emplace<std::pair<unsigned __int64,VND_HANDLER_CONTEXT *>>(std::pair<unsigned __int64,VND_HANDLER_CONTEXT *> &&)
0x14003413e  xor     ebx, ebx
0x140034140  mov     rcx, rdi
0x140034143  call    RrwLockRelease
0x140034148  mov     eax, ebx
0x14003414a  add     rsp, 68h
0x14003414e  pop     r15
0x140034150  pop     r14
0x140034152  pop     r13
0x140034154  pop     r12
0x140034156  pop     rdi
0x140034157  pop     rsi
0x140034158  pop     rbp
0x140034159  pop     rbx
0x14003415a  retn
0x14003415c  mov     rcx, [rsp+0A8h]; this
0x140034164  mov     r9d, 102h; char *
0x14003416a  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140034171  mov     edx, 2FEh; void *
0x140034176  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
