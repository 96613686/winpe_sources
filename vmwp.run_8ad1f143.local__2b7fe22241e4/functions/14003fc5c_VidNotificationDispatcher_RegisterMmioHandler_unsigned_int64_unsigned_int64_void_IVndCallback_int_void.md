# VidNotificationDispatcher::RegisterMmioHandler(unsigned __int64,unsigned __int64,void *,IVndCallback &,int,void * &)

- ea: `0x14003fc5c`
- end: `0x14003ff3c`
- name: `?RegisterMmioHandler@VidNotificationDispatcher@@QEAAJ_K0PEAXAEAUIVndCallback@@HAEAPEAX@Z`
- size: `736`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned __int64@<r8>, void *@<r9>, struct IVndCallback *, int, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140279620`

## callees

- `0x14003fc5c`
- `0x140040ff8`
- `0x1400412d4`
- `0x1400413e0`
- `0x140041a5c`
- `0x140042260`
- `0x14005497c`
- `0x140078cb8`
- `0x14009d7cc`
- `0x1400db410`
- `0x140132d50`
- `0x14027b3a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fe83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fd79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fe83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fca0`
- `vid!VidCreateMmioGpaRange` at `0x14003fe73`
- `vid!VidCreateMmioGpaRange` at `0x14003fe73`

## string_xrefs

- `0x14003ff2a`: `onecore\vm\common\vml\VmReaderWriterLock.h`

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
        VmlDebugTraceEx(0, &off_1402DC178);
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
        VmlDebugTraceEx(0, &off_1402DC268);
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
    VmlDebugTraceEx(g_BreakOnChildAssert == 0 ? 0x4000 : 0, &off_1402DC190);
LABEL_37:
  RrwLockRelease(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14003fc5c  push    rbx
0x14003fc5e  push    rbp
0x14003fc5f  push    rsi
0x14003fc60  push    rdi
0x14003fc61  push    r12
0x14003fc63  push    r13
0x14003fc65  push    r14
0x14003fc67  push    r15
0x14003fc69  sub     rsp, 68h
0x14003fc6d  mov     r12, r9
0x14003fc70  mov     r15, r8
0x14003fc73  mov     r14, rdx
0x14003fc76  mov     rbp, rcx
0x14003fc79  mov     r13, [rsp+0A8h+arg_20]
0x14003fc81  mov     eax, [rsp+0A8h+arg_28]
0x14003fc88  mov     [rsp+0A8h+var_78], eax
0x14003fc8c  mov     rax, [rsp+0A8h+arg_30]
0x14003fc94  mov     [rsp+0A8h+var_70], rax
0x14003fc99  lea     rdi, [rcx+16C0h]
0x14003fca0  call    cs:__imp_GetCurrentThreadId
0x14003fca7  nop     dword ptr [rax+rax+00h]
0x14003fcac  mov     esi, eax
0x14003fcae  mov     ebx, 1
0x14003fcb3  xor     eax, eax
0x14003fcb5  lock cmpxchg [rdi], ebx
0x14003fcb9  jz      short loc_14003FCDE
0x14003fcbb  mov     ecx, [rdi+4]
0x14003fcbe  cmp     ecx, esi
0x14003fcc0  jnz     short loc_14003FCC8
0x14003fcc2  lock add [rdi+8], ebx
0x14003fcc6  jmp     short loc_14003FCE1
0x14003fcc8  test    bl, al
0x14003fcca  jnz     short loc_14003FD0E
0x14003fccc  cmp     eax, 4
0x14003fccf  jnb     short loc_14003FD0E
0x14003fcd1  mov     edx, eax
0x14003fcd3  lea     ecx, [rax+1]
0x14003fcd6  lock cmpxchg [rdi], ecx
0x14003fcda  cmp     eax, edx
0x14003fcdc  jnz     short loc_14003FCC8
0x14003fcde  xchg    esi, [rdi+4]
0x14003fce1  mov     [rsp+0A8h+var_60], rdi
0x14003fce6  mov     r8, r15; unsigned __int64
0x14003fce9  mov     rdx, r14; unsigned __int64
0x14003fcec  mov     rcx, rbp; this
0x14003fcef  call    ?VerifyUnhandledMmioRange@VidNotificationDispatcher@@QEAAH_K0@Z; VidNotificationDispatcher::VerifyUnhandledMmioRange(unsigned __int64,unsigned __int64)
0x14003fcf4  test    eax, eax
0x14003fcf6  jnz     short loc_14003FD59
0x14003fcf8  mov     ebx, 8007000Dh
0x14003fcfd  mov     esi, 4000h
0x14003fd02  cmp     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x14003fd08  jz      short loc_14003FD2B
0x14003fd0a  xor     ecx, ecx
0x14003fd0c  jmp     short loc_14003FD2D
0x14003fd0e  mov     r8b, bl
0x14003fd11  or      edx, 0FFFFFFFFh
0x14003fd14  mov     rcx, rdi
0x14003fd17  call    RrwpLockWait
0x14003fd1c  test    eax, eax
0x14003fd1e  jz      loc_14003FF1C
0x14003fd24  prefetchw byte ptr [rdi]
0x14003fd27  mov     eax, [rdi]
0x14003fd29  jmp     short loc_14003FCC8
0x14003fd2b  mov     ecx, esi
0x14003fd2d  call    VmlIsDebugTraceEnabled
0x14003fd32  test    eax, eax
0x14003fd34  jz      loc_14003FF00
0x14003fd3a  mov     eax, cs:?g_BreakOnChildAssert@@3HA; int g_BreakOnChildAssert
0x14003fd40  neg     eax
0x14003fd42  sbb     ecx, ecx
0x14003fd44  not     ecx
0x14003fd46  and     ecx, esi
0x14003fd48  lea     rdx, off_1402DC190; "Unexpected error.\n"
0x14003fd4f  call    VmlDebugTraceEx
0x14003fd54  jmp     loc_14003FF00
0x14003fd59  mov     eax, [rsp+0A8h+var_78]
0x14003fd5d  mov     [rsp+0A8h+var_88], eax; int
0x14003fd61  mov     r9, r13
0x14003fd64  mov     r8, r12
0x14003fd67  xor     edx, edx
0x14003fd69  mov     rcx, rbp
0x14003fd6c  call    ?CreateHandlerContext@VidNotificationDispatcher@@AEAAPEAUVND_HANDLER_CONTEXT@@W4_VND_HANDLER_TYPE@@PEAXPEAUIVndCallback@@H@Z; VidNotificationDispatcher::CreateHandlerContext(_VND_HANDLER_TYPE,void *,IVndCallback *,int)
0x14003fd71  mov     rsi, rax
0x14003fd74  test    rax, rax
0x14003fd77  jnz     short loc_14003FDD5
0x14003fd79  call    cs:__imp_GetLastError
0x14003fd80  nop     dword ptr [rax+rax+00h]
0x14003fd85  mov     ebx, eax
0x14003fd87  test    eax, eax
0x14003fd89  jle     short loc_14003FD94
0x14003fd8b  movzx   ebx, ax
0x14003fd8e  or      ebx, 80070000h
0x14003fd94  mov     rcx, [rsp+0A8h]; this
0x14003fd9c  mov     r9d, 8000FFFFh; char *
0x14003fda2  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x14003fda9  mov     edx, 291h; void *
0x14003fdae  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14003fdb3  xor     ecx, ecx
0x14003fdb5  call    VmlIsDebugTraceEnabled
0x14003fdba  test    eax, eax
0x14003fdbc  jz      loc_14003FEB7
0x14003fdc2  lea     rdx, off_1402DC178; "Unexpected error.\n"
0x14003fdc9  xor     ecx, ecx
0x14003fdcb  call    VmlDebugTraceEx
0x14003fdd0  jmp     loc_14003FEB7
0x14003fdd5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003fddc  mov     ecx, 20h ; ' '; unsigned __int64
0x14003fde1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003fde6  test    rax, rax
0x14003fde9  jz      short loc_14003FDF5
0x14003fdeb  xorps   xmm0, xmm0
0x14003fdee  movups  xmmword ptr [rax], xmm0
0x14003fdf1  movups  xmmword ptr [rax+10h], xmm0
0x14003fdf5  mov     [rsi+0C0h], rax
0x14003fdfc  test    rax, rax
0x14003fdff  jnz     short loc_14003FE44
0x14003fe01  mov     ebx, 8007000Eh
0x14003fe06  mov     rcx, [rsp+0A8h]; this
0x14003fe0e  mov     r9d, 8000FFFFh; char *
0x14003fe14  lea     r8, aOnecoreVmWorke_76; "onecore\\vm\\worker\\vidpartition\\vnd."...
0x14003fe1b  mov     edx, 299h; void *
0x14003fe20  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14003fe25  xor     ecx, ecx
0x14003fe27  call    VmlIsDebugTraceEnabled
0x14003fe2c  test    eax, eax
0x14003fe2e  jz      loc_14003FEC0
0x14003fe34  lea     rdx, off_1402DC268; "Unexpected error.\n"
0x14003fe3b  xor     ecx, ecx
0x14003fe3d  call    VmlDebugTraceEx
0x14003fe42  jmp     short loc_14003FEC0
0x14003fe44  mov     [rsi+0B0h], r14
0x14003fe4b  mov     [rsi+0B8h], r15
0x14003fe52  add     rax, 10h
0x14003fe56  mov     [rax+8], rax
0x14003fe5a  mov     [rax], rax
0x14003fe5d  lea     rax, [rsi+70h]
0x14003fe61  mov     qword ptr [rsp+0A8h+var_88], rax
0x14003fe66  mov     r9, rsi
0x14003fe69  mov     r8, r15
0x14003fe6c  mov     rdx, r14
0x14003fe6f  mov     rcx, [rbp+28h]
0x14003fe73  call    cs:__imp_VidCreateMmioGpaRange
0x14003fe7a  nop     dword ptr [rax+rax+00h]
0x14003fe7f  test    eax, eax
0x14003fe81  jnz     short loc_14003FECD
0x14003fe83  call    cs:__imp_GetLastError
0x14003fe8a  nop     dword ptr [rax+rax+00h]
0x14003fe8f  mov     ebx, eax
0x14003fe91  test    eax, 1FFF0000h
0x14003fe96  jnz     short loc_14003FEA7
0x14003fe98  test    eax, eax
0x14003fe9a  jle     short loc_14003FEB9
0x14003fe9c  movzx   ebx, bx
0x14003fe9f  or      ebx, 80070000h
0x14003fea5  jmp     short loc_14003FEB7
0x14003fea7  test    ebx, ebx
0x14003fea9  jle     short loc_14003FEB9
0x14003feab  and     ebx, 0FFFFFFFh
0x14003feb1  or      ebx, 80000000h
0x14003feb7  test    ebx, ebx
0x14003feb9  jns     short loc_14003FF00
0x14003febb  test    rsi, rsi
0x14003febe  jz      short loc_14003FF00
0x14003fec0  mov     rdx, rsi; struct VND_HANDLER_CONTEXT *
0x14003fec3  mov     rcx, rbp; this
0x14003fec6  call    ?DeleteHandlerContext@VidNotificationDispatcher@@AEAAXPEAUVND_HANDLER_CONTEXT@@@Z; VidNotificationDispatcher::DeleteHandlerContext(VND_HANDLER_CONTEXT *)
0x14003fecb  jmp     short loc_14003FF00
0x14003fecd  mov     rax, [rsp+0A8h+var_70]
0x14003fed2  mov     [rax], rsi
0x14003fed5  mov     [rsi+88h], ebx
0x14003fedb  xchg    ebx, [rbp+300h]
0x14003fee1  mov     [rsp+0A8h+var_70], r14
0x14003fee6  mov     [rsp+0A8h+var_68], rsi
0x14003feeb  lea     rcx, [rbp+50h]
0x14003feef  lea     r8, [rsp+0A8h+var_70]
0x14003fef4  lea     rdx, [rsp+0A8h+var_58]
0x14003fef9  call    ??$_Emplace@U?$pair@_KPEAUVND_HANDLER_CONTEXT@@@std@@@?$_Tree@V?$_Tmap_traits@_KPEAUVND_HANDLER_CONTEXT@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KPEAUVND_HANDLER_CONTEXT@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KPEAUVND_HANDLER_CONTEXT@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,VND_HANDLER_CONTEXT *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,VND_HANDLER_CONTEXT *>>,0>>::_Emplace<std::pair<unsigned __int64,VND_HANDLER_CONTEXT *>>(std::pair<unsigned __int64,VND_HANDLER_CONTEXT *> &&)
0x14003fefe  xor     ebx, ebx
0x14003ff00  mov     rcx, rdi
0x14003ff03  call    RrwLockRelease
0x14003ff08  mov     eax, ebx
0x14003ff0a  add     rsp, 68h
0x14003ff0e  pop     r15
0x14003ff10  pop     r14
0x14003ff12  pop     r13
0x14003ff14  pop     r12
0x14003ff16  pop     rdi
0x14003ff17  pop     rsi
0x14003ff18  pop     rbp
0x14003ff19  pop     rbx
0x14003ff1a  retn
0x14003ff1c  mov     rcx, [rsp+0A8h]; this
0x14003ff24  mov     r9d, 102h; char *
0x14003ff2a  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x14003ff31  mov     edx, 2FEh; void *
0x14003ff36  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
