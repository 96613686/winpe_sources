# CWmiFinalizer::Indicate(long,IWbemClassObject * *)

- ea: `0x180005ba0`
- end: `0x18000619c`
- name: `?Indicate@CWmiFinalizer@@QEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `1532`
- prototype: `__int64 __fastcall(CWmiFinalizer *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180005a60`

## callees

- `0x180004de8`
- `0x180005ba0`
- `0x1800061b0`
- `0x1800067c4`
- `0x180006b9c`
- `0x18000898c`
- `0x180009b90`
- `0x18000a3c0`
- `0x18000aa90`
- `0x18000b104`
- `0x18000b140`
- `0x18000b46c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c75`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005c75`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180005bf7`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180005bf7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005c14`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000604a`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005c14`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000604a`
- `wbemcomn!GetMemLogObject` at `0x180005dfb`
- `wbemcomn!GetMemLogObject` at `0x180005e93`
- `wbemcomn!GetMemLogObject` at `0x180005ffa`
- `wbemcomn!GetMemLogObject` at `0x18000605a`
- `wbemcomn!GetMemLogObject` at `0x1800060ab`
- `wbemcomn!GetMemLogObject` at `0x1800060fc`
- `wbemcomn!GetMemLogObject` at `0x18000614b`
- `wbemcomn!GetMemLogObject` at `0x180005dfb`
- `wbemcomn!GetMemLogObject` at `0x180005e93`
- `wbemcomn!GetMemLogObject` at `0x180005ffa`
- `wbemcomn!GetMemLogObject` at `0x18000605a`
- `wbemcomn!GetMemLogObject` at `0x1800060ab`
- `wbemcomn!GetMemLogObject` at `0x1800060fc`
- `wbemcomn!GetMemLogObject` at `0x18000614b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005e06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005e9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006008`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006068`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800060b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006159`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005e06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005e9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006008`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006068`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800060b9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006159`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWmiFinalizer::Indicate(CWmiFinalizer *this, int a2, struct IWbemClassObject **a3)
{
  int v6; // esi
  int i; // ecx
  int j; // ebp
  struct IWbemClassObject **v9; // rdi
  _QWORD *v10; // rbx
  struct IWbemClassObject *v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rdi
  __int64 v15; // rcx
  int v16; // ebx
  int v17; // edi
  CMemoryLog *v19; // rax
  IUnknown *v20; // rax
  struct IWbemObjectSink *v21; // rbx
  int v22; // eax
  CMemoryLog *v23; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  IUnknown *v29; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, this, a2);
  }
  if ( *((_DWORD *)this + 165) )
    return 2147749938LL;
  CInCritSec::CInCritSec((CInCritSec *)&v29, (struct _RTL_CRITICAL_SECTION *)((char *)this + 568));
  if ( *((_BYTE *)this + 520) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217386);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, 2147749910LL);
    }
    CInCritSec::~CInCritSec((CInCritSec *)&v29);
    return 2147749910LL;
  }
  CInCritSec::~CInCritSec((CInCritSec *)&v29);
  v6 = 0;
  for ( i = 0; i != a2; ++i )
  {
    if ( !a3[i] )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217393);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, 2147749903LL);
      }
      return 2147749903LL;
    }
  }
  if ( *((_DWORD *)this + 44) != 1 || *((_DWORD *)this + 35) )
  {
    LODWORD(v29) = 0;
    for ( j = 0; ; ++j )
    {
      if ( j == a2 )
      {
        v17 = (int)v29;
        goto LABEL_33;
      }
      v9 = &a3[j];
      if ( *v9 )
      {
        v10 = CWin32DefaultArena::WbemMemAlloc(0x50u);
        v30 = v10;
        if ( v10 )
        {
          v11 = *v9;
          *v10 = &CWmiFinalizerObj::`vftable';
          v10[1] = v11;
          *((_DWORD *)v10 + 4) = 1;
          v10[3] = 0;
          *((_DWORD *)v10 + 8) = 0;
          *((_DWORD *)v10 + 9) = 266240;
          v10[5] = 0;
          v10[6] = this;
          *((_DWORD *)v10 + 19) = 0;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids);
          }
          v12 = v10[1];
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
            if ( v11 )
            {
              v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *))v11->lpVtbl[3].PutMethod)(v11);
              *((_DWORD *)v10 + 18) = v13;
              v14 = v10[6];
              if ( v14 )
              {
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    39,
                    WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids,
                    v10[6]);
                }
                v15 = *(_QWORD *)(v14 + 192);
                if ( v15 )
                  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 152LL))(
                         v15,
                         0,
                         v13,
                         *(_QWORD *)(v14 + 184));
                _InterlockedAdd((volatile signed __int32 *)(v14 + 612), v13);
                if ( v6 < 0 )
                {
                  v27 = GetMemLogObject();
                  CMemoryLog::Write(v27, v6);
                }
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    40,
                    WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids,
                    (unsigned int)v6);
                }
                *((_DWORD *)v10 + 9) = v6;
                v6 = 0;
              }
            }
            else
            {
              *((_DWORD *)v10 + 18) = 0;
            }
          }
        }
        else
        {
          v10 = 0;
        }
        if ( !v10 )
        {
          v28 = GetMemLogObject();
          CMemoryLog::Write(v28, -2147217402);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              71,
              WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids,
              2147749894LL);
          }
          return 2147749894LL;
        }
        v16 = CWmiFinalizer::QueueOperation(this, (struct CWmiFinalizerObj *)v10);
        if ( v16 < 0 )
        {
          v19 = GetMemLogObject();
          CMemoryLog::Write(v19, v16);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              72,
              WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids,
              (unsigned int)v16);
          }
          return (unsigned int)v16;
        }
      }
    }
  }
  v20 = (IUnknown *)CWmiFinalizer::ReturnProtectedDestinationSink(this);
  v21 = (struct IWbemObjectSink *)v20;
  if ( !v20 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  v29 = v20;
  v22 = CWmiFinalizer::DoIndicate(this, v20, a2, a3);
  v17 = v22;
  if ( v22 >= 0 )
  {
    if ( *((_DWORD *)this + 165) == 1 )
      goto LABEL_51;
    if ( *((_DWORD *)this + 166) != 1 )
      goto LABEL_44;
  }
  if ( v22 == -2147217358 )
    goto LABEL_58;
LABEL_51:
  if ( *((_DWORD *)this + 165) )
  {
LABEL_58:
    CWmiFinalizer::DoSetStatus(this, v21, 0, -2147217358, 0, 0, 0);
    goto LABEL_59;
  }
  CWmiFinalizer::DoSetStatusCancel(this, v21, v22);
LABEL_59:
  v17 = -2147217358;
  ((void (__fastcall *)(struct IWbemObjectSink *))v21->lpVtbl->Release)(v21);
  v21 = 0;
  v29 = 0;
  CWmiFinalizer::ReleaseDestinationSink(this);
  *((_DWORD *)this + 192) = 1878;
  CWmiFinalizer::CancelCall(this);
LABEL_44:
  if ( v21 )
    ((void (__fastcall *)(struct IWbemObjectSink *))v21->lpVtbl->Release)(v21);
  v29 = 0;
  if ( v17 < 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, v17);
  }
LABEL_33:
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids,
      (unsigned int)v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180005ba0  mov     [rsp+arg_8], rbx
0x180005ba5  push    rbp
0x180005ba6  push    rsi
0x180005ba7  push    rdi
0x180005ba8  push    r12
0x180005baa  push    r13
0x180005bac  push    r14
0x180005bae  push    r15
0x180005bb0  sub     rsp, 40h
0x180005bb4  mov     r12, r8
0x180005bb7  mov     r15d, edx
0x180005bba  mov     r13, rcx
0x180005bbd  lea     r14, WPP_GLOBAL_Control
0x180005bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bcb  cmp     rcx, r14
0x180005bce  jz      short loc_180005BDA
0x180005bd0  test    byte ptr [rcx+1Ch], 1
0x180005bd4  jnz     loc_180005F18
0x180005bda  cmp     dword ptr [r13+294h], 0
0x180005be2  jnz     loc_180005EA9
0x180005be8  lea     rdx, [r13+238h]
0x180005bef  lea     rcx, [rsp+78h+arg_0]
0x180005bf7  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180005bfd  nop
0x180005bfe  cmp     byte ptr [r13+208h], 0
0x180005c06  jnz     loc_180005FFA
0x180005c0c  lea     rcx, [rsp+78h+arg_0]
0x180005c14  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180005c1a  xor     esi, esi
0x180005c1c  mov     ecx, esi
0x180005c1e  xchg    ax, ax
0x180005c20  cmp     ecx, r15d
0x180005c23  jz      short loc_180005C36
0x180005c25  movsxd  rax, ecx
0x180005c28  cmp     [r12+rax*8], rsi
0x180005c2c  jz      loc_18000605A
0x180005c32  inc     ecx
0x180005c34  jmp     short loc_180005C20
0x180005c36  cmp     dword ptr [r13+0B0h], 1
0x180005c3e  jnz     short loc_180005C4D
0x180005c40  cmp     [r13+8Ch], esi
0x180005c47  jz      loc_180005E20
0x180005c4d  mov     dword ptr [rsp+78h+arg_0], esi
0x180005c54  mov     ebp, esi
0x180005c56  cmp     ebp, r15d
0x180005c59  jz      loc_180005DB6
0x180005c5f  movsxd  rax, ebp
0x180005c62  lea     rdi, [r12+rax*8]
0x180005c66  cmp     qword ptr [rdi], 0
0x180005c6a  jz      loc_180005DAF
0x180005c70  mov     ecx, 50h ; 'P'
0x180005c75  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005c7b  mov     rbx, rax
0x180005c7e  mov     [rsp+78h+arg_18], rax
0x180005c86  test    rax, rax
0x180005c89  jz      loc_180006112
0x180005c8f  mov     rdi, [rdi]
0x180005c92  lea     rax, ??_7CWmiFinalizerObj@@6B@; const CWmiFinalizerObj::`vftable'
0x180005c99  mov     [rbx], rax
0x180005c9c  mov     [rbx+8], rdi
0x180005ca0  mov     dword ptr [rbx+10h], 1
0x180005ca7  mov     [rbx+18h], rsi
0x180005cab  mov     [rbx+20h], esi
0x180005cae  mov     dword ptr [rbx+24h], 41000h
0x180005cb5  mov     [rbx+28h], rsi
0x180005cb9  mov     [rbx+30h], r13
0x180005cbd  mov     [rbx+4Ch], esi
0x180005cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cc7  cmp     rcx, r14
0x180005cca  jz      short loc_180005CD6
0x180005ccc  test    byte ptr [rcx+1Ch], 1
0x180005cd0  jnz     loc_180005EF4
0x180005cd6  mov     rcx, [rbx+8]
0x180005cda  test    rcx, rcx
0x180005cdd  jz      loc_180005D95
0x180005ce3  mov     rax, [rcx]
0x180005ce6  mov     rax, [rax+8]
0x180005cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cef  test    rdi, rdi
0x180005cf2  jz      loc_180005DF6
0x180005cf8  mov     rax, [rdi]
0x180005cfb  mov     rcx, rdi
0x180005cfe  mov     rax, [rax+328h]
0x180005d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d0a  mov     r14d, eax
0x180005d0d  mov     [rbx+48h], eax
0x180005d10  mov     rdi, [rbx+30h]
0x180005d14  test    rdi, rdi
0x180005d17  jz      loc_180005DED
0x180005d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d24  lea     rax, WPP_GLOBAL_Control
0x180005d2b  cmp     rcx, rax
0x180005d2e  jz      short loc_180005D3A
0x180005d30  test    byte ptr [rcx+1Ch], 1
0x180005d34  jnz     loc_180005EB3
0x180005d3a  mov     rcx, [rdi+0C0h]
0x180005d41  test    rcx, rcx
0x180005d44  jz      short loc_180005D63
0x180005d46  mov     rax, [rcx]
0x180005d49  mov     r9, [rdi+0B8h]
0x180005d50  mov     r8d, r14d
0x180005d53  xor     edx, edx
0x180005d55  mov     rax, [rax+98h]
0x180005d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d61  mov     esi, eax
0x180005d63  lock add [rdi+264h], r14d
0x180005d6b  test    esi, esi
0x180005d6d  js      loc_1800060FC
0x180005d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d7a  lea     r14, WPP_GLOBAL_Control
0x180005d81  cmp     rcx, r14
0x180005d84  jz      short loc_180005D90
0x180005d86  test    byte ptr [rcx+1Ch], 1
0x180005d8a  jnz     loc_180005FAC
0x180005d90  mov     [rbx+24h], esi
0x180005d93  xor     esi, esi
0x180005d95  test    rbx, rbx
0x180005d98  jz      loc_18000614B
0x180005d9e  mov     rdx, rbx; struct CWmiFinalizerObj *
0x180005da1  mov     rcx, r13; this
0x180005da4  call    ?QueueOperation@CWmiFinalizer@@IEAAJPEAVCWmiFinalizerObj@@@Z; CWmiFinalizer::QueueOperation(CWmiFinalizerObj *)
0x180005da9  mov     ebx, eax
0x180005dab  test    eax, eax
0x180005dad  js      short loc_180005DFB
0x180005daf  inc     ebp
0x180005db1  jmp     loc_180005C56
0x180005db6  mov     edi, dword ptr [rsp+78h+arg_0]
0x180005dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc4  cmp     rcx, r14
0x180005dc7  jz      short loc_180005DD3
0x180005dc9  test    byte ptr [rcx+1Ch], 1
0x180005dcd  jnz     loc_180005FD3
0x180005dd3  mov     eax, edi
0x180005dd5  mov     rbx, [rsp+78h+arg_8]
0x180005ddd  add     rsp, 40h
0x180005de1  pop     r15
0x180005de3  pop     r14
0x180005de5  pop     r13
0x180005de7  pop     r12
0x180005de9  pop     rdi
0x180005dea  pop     rsi
0x180005deb  pop     rbp
0x180005dec  retn
0x180005ded  lea     r14, WPP_GLOBAL_Control
0x180005df4  jmp     short loc_180005D95
0x180005df6  mov     [rbx+48h], esi
0x180005df9  jmp     short loc_180005D95
0x180005dfb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005e01  mov     edx, ebx
0x180005e03  mov     rcx, rax
0x180005e06  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180005e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e13  cmp     rcx, r14
0x180005e16  jnz     loc_18000611A
0x180005e1c  mov     eax, ebx
0x180005e1e  jmp     short loc_180005DD5
0x180005e20  mov     rcx, r13; this
0x180005e23  call    ?ReturnProtectedDestinationSink@CWmiFinalizer@@QEAAPEAUIWbemObjectSink@@XZ; CWmiFinalizer::ReturnProtectedDestinationSink(void)
0x180005e28  mov     rbx, rax
0x180005e2b  test    rax, rax
0x180005e2e  jz      loc_1800060AB
0x180005e34  mov     [rsp+78h+arg_0], rax
0x180005e3c  mov     r9, r12; struct IWbemClassObject **
0x180005e3f  mov     r8d, r15d; int
0x180005e42  mov     rdx, rax; pProxy
0x180005e45  mov     rcx, r13; this
0x180005e48  call    ?DoIndicate@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@HPEAPEAUIWbemClassObject@@@Z; CWmiFinalizer::DoIndicate(IWbemObjectSink *,int,IWbemClassObject * *)
0x180005e4d  mov     edi, eax
0x180005e4f  test    eax, eax
0x180005e51  js      loc_180005F44
0x180005e57  cmp     dword ptr [r13+294h], 1
0x180005e5f  jz      short loc_180005EDA
0x180005e61  cmp     dword ptr [r13+298h], 1
0x180005e69  jz      loc_180005F44
0x180005e6f  test    rbx, rbx
0x180005e72  jz      short loc_180005E83
0x180005e74  mov     rax, [rbx]
0x180005e77  mov     rcx, rbx
0x180005e7a  mov     rax, [rax+10h]
0x180005e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e83  mov     [rsp+78h+arg_0], rsi
0x180005e8b  test    edi, edi
0x180005e8d  jns     loc_180005DBD
0x180005e93  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005e99  mov     edx, edi
0x180005e9b  mov     rcx, rax
0x180005e9e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180005ea4  jmp     loc_180005DBD
0x180005ea9  mov     eax, 80041032h
0x180005eae  jmp     loc_180005DD5
0x180005eb3  cmp     byte ptr [rcx+19h], 5
0x180005eb7  jb      loc_180005D3A
0x180005ebd  mov     edx, 27h ; '''
0x180005ec2  mov     r9, rdi
0x180005ec5  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180005ecc  mov     rcx, [rcx+10h]
0x180005ed0  call    WPP_SF_q
0x180005ed5  jmp     loc_180005D3A
0x180005eda  cmp     dword ptr [r13+294h], 0
0x180005ee2  jnz     short loc_180005F4B
0x180005ee4  mov     r8d, eax; int
0x180005ee7  mov     rdx, rbx; struct IWbemObjectSink *
0x180005eea  mov     rcx, r13; this
0x180005eed  call    ?DoSetStatusCancel@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@J@Z; CWmiFinalizer::DoSetStatusCancel(IWbemObjectSink *,long)
0x180005ef2  jmp     short loc_180005F6D
0x180005ef4  cmp     byte ptr [rcx+19h], 5
0x180005ef8  jb      loc_180005CD6
0x180005efe  mov     edx, 11Ch
0x180005f03  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180005f0a  mov     rcx, [rcx+10h]
0x180005f0e  call    WPP_SF_
0x180005f13  jmp     loc_180005CD6
0x180005f18  cmp     byte ptr [rcx+19h], 5
0x180005f1c  jb      loc_180005BDA
0x180005f22  mov     edx, 43h ; 'C'
0x180005f27  mov     dword ptr [rsp+78h+var_58], r15d
0x180005f2c  mov     r9, r13
0x180005f2f  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180005f36  mov     rcx, [rcx+10h]
0x180005f3a  call    WPP_SF_qd
0x180005f3f  jmp     loc_180005BDA
0x180005f44  cmp     eax, 80041032h
0x180005f49  jnz     short loc_180005EDA
0x180005f4b  mov     [rsp+78h+var_48], esi; int
0x180005f4f  mov     [rsp+78h+var_50], rsi; struct IWbemClassObject *
0x180005f54  mov     [rsp+78h+var_58], rsi; unsigned __int16 *
0x180005f59  mov     r9d, 80041032h; int
0x180005f5f  xor     r8d, r8d; int
0x180005f62  mov     rdx, rbx; struct IWbemObjectSink *
0x180005f65  mov     rcx, r13; this
0x180005f68  call    ?DoSetStatus@CWmiFinalizer@@QEAAJPEAUIWbemObjectSink@@JJPEAGPEAUIWbemClassObject@@H@Z; CWmiFinalizer::DoSetStatus(IWbemObjectSink *,long,long,ushort *,IWbemClassObject *,int)
0x180005f6d  mov     edi, 80041032h
0x180005f72  mov     rax, [rbx]
0x180005f75  mov     rcx, rbx
0x180005f78  mov     rax, [rax+10h]
0x180005f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f81  mov     rbx, rsi
0x180005f84  mov     [rsp+78h+arg_0], rbx
0x180005f8c  mov     rcx, r13; this
0x180005f8f  call    ?ReleaseDestinationSink@CWmiFinalizer@@QEAAJXZ; CWmiFinalizer::ReleaseDestinationSink(void)
0x180005f94  mov     dword ptr [r13+300h], 756h
0x180005f9f  mov     rcx, r13; this
0x180005fa2  call    ?CancelCall@CWmiFinalizer@@IEAAJXZ; CWmiFinalizer::CancelCall(void)
0x180005fa7  jmp     loc_180005E6F
0x180005fac  cmp     byte ptr [rcx+19h], 2
0x180005fb0  jb      loc_180005D90
0x180005fb6  mov     edx, 28h ; '('
0x180005fbb  mov     r9d, esi
0x180005fbe  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180005fc5  mov     rcx, [rcx+10h]
0x180005fc9  call    WPP_SF_d
0x180005fce  jmp     loc_180005D90
0x180005fd3  cmp     byte ptr [rcx+19h], 2
0x180005fd7  jb      loc_180005DD3
0x180005fdd  mov     edx, 49h ; 'I'
0x180005fe2  mov     r9d, edi
0x180005fe5  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180005fec  mov     rcx, [rcx+10h]
0x180005ff0  call    WPP_SF_d
0x180005ff5  jmp     loc_180005DD3
0x180005ffa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180006000  mov     edx, 80041016h
0x180006005  mov     rcx, rax
0x180006008  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000600e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006015  cmp     rcx, r14
0x180006018  jz      short loc_180006042
0x18000601a  test    byte ptr [rcx+1Ch], 1
0x18000601e  jz      short loc_180006042
0x180006020  cmp     byte ptr [rcx+19h], 2
0x180006024  jb      short loc_180006042
0x180006026  mov     edx, 44h ; 'D'
0x18000602b  mov     r9d, 80041016h
0x180006031  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180006038  mov     rcx, [rcx+10h]
0x18000603c  call    WPP_SF_d
0x180006041  nop
0x180006042  lea     rcx, [rsp+78h+arg_0]
0x18000604a  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180006050  mov     eax, 80041016h
0x180006055  jmp     loc_180005DD5
0x18000605a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180006060  mov     edx, 8004100Fh
0x180006065  mov     rcx, rax
0x180006068  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000606e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006075  cmp     rcx, r14
0x180006078  jz      short loc_1800060A1
0x18000607a  test    byte ptr [rcx+1Ch], 1
0x18000607e  jz      short loc_1800060A1
0x180006080  cmp     byte ptr [rcx+19h], 2
0x180006084  jb      short loc_1800060A1
0x180006086  mov     edx, 45h ; 'E'
0x18000608b  mov     r9d, 8004100Fh
0x180006091  lea     r8, WPP_4f6dc932c79c3f24434e511ac572aad9_Traceguids
0x180006098  mov     rcx, [rcx+10h]
0x18000609c  call    WPP_SF_d
0x1800060a1  mov     eax, 8004100Fh
0x1800060a6  jmp     loc_180005DD5
0x1800060ab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
  ... truncated ...
```
