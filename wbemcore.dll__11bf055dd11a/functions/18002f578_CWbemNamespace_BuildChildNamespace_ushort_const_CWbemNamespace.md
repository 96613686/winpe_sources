# CWbemNamespace::BuildChildNamespace(ushort const *,CWbemNamespace * *)

- ea: `0x18002f578`
- end: `0x18002f9f9`
- name: `?BuildChildNamespace@CWbemNamespace@@IEAAJPEBGPEAPEAV1@@Z`
- size: `1153`
- prototype: `int(CWbemNamespace *__hidden this, const unsigned __int16 *, struct CWbemNamespace **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180049d34`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18001cce0`
- `0x18001d390`
- `0x18002a998`
- `0x18002dd24`
- `0x18002f578`
- `0x180036db0`
- `0x180087094`
- `0x180089ccc`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002f678`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002f678`
- `wbemcomn!GetMemLogObject` at `0x18002f5e1`
- `wbemcomn!GetMemLogObject` at `0x18002f69c`
- `wbemcomn!GetMemLogObject` at `0x18002f72f`
- `wbemcomn!GetMemLogObject` at `0x18002f7af`
- `wbemcomn!GetMemLogObject` at `0x18002f833`
- `wbemcomn!GetMemLogObject` at `0x18002f906`
- `wbemcomn!GetMemLogObject` at `0x18002f9a2`
- `wbemcomn!GetMemLogObject` at `0x18002f5e1`
- `wbemcomn!GetMemLogObject` at `0x18002f69c`
- `wbemcomn!GetMemLogObject` at `0x18002f72f`
- `wbemcomn!GetMemLogObject` at `0x18002f7af`
- `wbemcomn!GetMemLogObject` at `0x18002f833`
- `wbemcomn!GetMemLogObject` at `0x18002f906`
- `wbemcomn!GetMemLogObject` at `0x18002f9a2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f5f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f6ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f73a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f7ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f83e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f911`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f9ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f5f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f6ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f73a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f7ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f83e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f911`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f9ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CWbemNamespace::BuildChildNamespace(
        CWbemNamespace *this,
        const unsigned __int16 *a2,
        struct CWbemNamespace **a3)
{
  const unsigned __int16 *v3; // rsi
  volatile signed __int32 *Instance; // rdi
  CMemoryLog *MemLogObject; // rax
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // r13
  void *v13; // rax
  unsigned __int16 *v14; // r12
  CMemoryLog *v15; // rax
  const unsigned __int16 *v16; // r8
  int v17; // esi
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  int v22; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v25; // [rsp+D8h] [rbp+20h] BYREF

  v3 = a2;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  Instance = (volatile signed __int32 *)CWbemNamespace::CreateInstance();
  if ( !Instance )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  v8 = 2;
  v9 = *((_QWORD *)this + 12);
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v9 + 2 * v10) );
    v8 = v10 + 2;
  }
  v11 = -1;
  do
    ++v11;
  while ( v3[v11] );
  v12 = (unsigned int)(v8 + v11);
  v13 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v12, 2u));
  std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(&v25, (__int64)v13);
  v14 = v25;
  if ( !v25 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>((void **)&v25);
    CWbemNamespace::Release((CWbemNamespace *)Instance);
    return 2147749894LL;
  }
  *v25 = 0;
  v16 = (const unsigned __int16 *)*((_QWORD *)this + 12);
  if ( v16 )
  {
    v17 = StringCchCopyW(v14, v12, v16);
    if ( v17 < 0 )
    {
      v18 = GetMemLogObject();
      CMemoryLog::Write(v18, v17);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          177,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v17);
      }
LABEL_45:
      std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>((void **)&v25);
      CWbemNamespace::Release((CWbemNamespace *)Instance);
      return (unsigned int)v17;
    }
    v17 = StringCchCatW(v14, v12, L"\\");
    if ( v17 < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, v17);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          178,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v17);
      }
      goto LABEL_45;
    }
    v3 = a2;
  }
  v17 = StringCchCatW(v14, v12, v3);
  if ( v17 < 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, v17);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        179,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v17);
    }
    goto LABEL_45;
  }
  v17 = CWbemNamespace::Initialize(
          (CWbemNamespace *)Instance,
          v14,
          *((unsigned __int16 **)this + 14),
          0,
          0,
          *((_DWORD *)this + 32),
          1,
          *((const unsigned __int16 **)this + 35),
          *((const unsigned __int16 **)this + 36),
          *((_DWORD *)this + 76),
          *((_QWORD *)this + 37),
          v22,
          *((struct IWmiDbSession **)this + 5),
          0);
  if ( v17 < 0 )
  {
    v21 = GetMemLogObject();
    CMemoryLog::Write(v21, v17);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v17);
    }
    goto LABEL_45;
  }
  _InterlockedIncrement(Instance + 6);
  *a3 = (struct CWbemNamespace *)Instance;
  std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>((void **)&v25);
  CWbemNamespace::Release((CWbemNamespace *)Instance);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (unsigned int)v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18002f578  mov     [rsp+arg_10], r8
0x18002f57d  mov     [rsp+arg_8], rdx
0x18002f582  push    rbx
0x18002f583  push    rsi
0x18002f584  push    rdi
0x18002f585  push    r12
0x18002f587  push    r13
0x18002f589  push    r14
0x18002f58b  push    r15
0x18002f58d  sub     rsp, 80h
0x18002f594  mov     rsi, rdx
0x18002f597  mov     r15, rcx
0x18002f59a  lea     r14, WPP_GLOBAL_Control
0x18002f5a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5a8  cmp     rcx, r14
0x18002f5ab  jz      short loc_18002F5D2
0x18002f5ad  test    byte ptr [rcx+1Ch], 1
0x18002f5b1  jz      short loc_18002F5D2
0x18002f5b3  cmp     byte ptr [rcx+19h], 5
0x18002f5b7  jb      short loc_18002F5D2
0x18002f5b9  mov     edx, 0AEh
0x18002f5be  mov     r9, rsi
0x18002f5c1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f5c8  mov     rcx, [rcx+10h]
0x18002f5cc  call    WPP_SF_S
0x18002f5d1  nop
0x18002f5d2  call    ?CreateInstance@CWbemNamespace@@SAPEAV1@XZ; CWbemNamespace::CreateInstance(void)
0x18002f5d7  mov     rdi, rax
0x18002f5da  xor     ebx, ebx
0x18002f5dc  test    rax, rax
0x18002f5df  jnz     short loc_18002F631
0x18002f5e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f5e7  mov     esi, 80041006h
0x18002f5ec  mov     edx, esi
0x18002f5ee  mov     rcx, rax
0x18002f5f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f5f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5fe  cmp     rcx, r14
0x18002f601  jz      short loc_18002F62A
0x18002f603  test    byte ptr [rcx+1Ch], 1
0x18002f607  jz      short loc_18002F62A
0x18002f609  cmp     byte ptr [rcx+19h], 2
0x18002f60d  jb      short loc_18002F62A
0x18002f60f  mov     edx, 0AFh
0x18002f614  mov     r9d, 80041006h
0x18002f61a  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f621  mov     rcx, [rcx+10h]
0x18002f625  call    WPP_SF_d
0x18002f62a  mov     eax, esi
0x18002f62c  jmp     loc_18002F9E5
0x18002f631  mov     [rsp+0B8h+var_40], rdi
0x18002f636  mov     r8d, 2
0x18002f63c  mov     rdx, [r15+60h]
0x18002f640  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002f644  test    rdx, rdx
0x18002f647  jz      short loc_18002F659
0x18002f649  mov     rax, rcx
0x18002f64c  inc     rax
0x18002f64f  cmp     [rdx+rax*2], bx
0x18002f653  jnz     short loc_18002F64C
0x18002f655  lea     r8d, [rax+2]
0x18002f659  mov     rax, rcx
0x18002f65c  inc     rax
0x18002f65f  cmp     [rsi+rax*2], bx
0x18002f663  jnz     short loc_18002F65C
0x18002f665  lea     r13d, [r8+rax]
0x18002f669  mov     eax, 2
0x18002f66e  mul     r13
0x18002f671  cmovb   rax, rcx
0x18002f675  mov     rcx, rax
0x18002f678  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002f67e  mov     rdx, rax
0x18002f681  lea     rcx, [rsp+0B8h+arg_18]
0x18002f689  call    ??0?$unique_ptr@$$BY0A@PEAUIWbemClassObject@@U?$default_delete@$$BY0A@PEAUIWbemClassObject@@@std@@@std@@QEAA@PEAPEAUIWbemClassObject@@@Z; std::unique_ptr<IWbemClassObject * [0]>::unique_ptr<IWbemClassObject * [0]>(IWbemClassObject * *)
0x18002f68e  nop
0x18002f68f  mov     r12, [rsp+0B8h+arg_18]
0x18002f697  test    r12, r12
0x18002f69a  jnz     short loc_18002F708
0x18002f69c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f6a2  mov     esi, 80041006h
0x18002f6a7  mov     edx, esi
0x18002f6a9  mov     rcx, rax
0x18002f6ac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6b9  cmp     rcx, r14
0x18002f6bc  jz      short loc_18002F6E6
0x18002f6be  test    byte ptr [rcx+1Ch], 1
0x18002f6c2  jz      short loc_18002F6E6
0x18002f6c4  cmp     byte ptr [rcx+19h], 2
0x18002f6c8  jb      short loc_18002F6E6
0x18002f6ca  mov     edx, 0B0h
0x18002f6cf  mov     r9d, 80041006h
0x18002f6d5  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f6dc  mov     rcx, [rcx+10h]
0x18002f6e0  call    WPP_SF_d
0x18002f6e5  nop
0x18002f6e6  lea     rcx, [rsp+0B8h+arg_18]
0x18002f6ee  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f6f3  nop
0x18002f6f4  mov     rcx, rdi; this
0x18002f6f7  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f6fc  mov     [rsp+0B8h+var_40], rbx
0x18002f701  mov     eax, esi
0x18002f703  jmp     loc_18002F9E5
0x18002f708  mov     [r12], bx
0x18002f70d  mov     r8, [r15+60h]; unsigned __int16 *
0x18002f711  test    r8, r8
0x18002f714  jz      loc_18002F81B
0x18002f71a  mov     rdx, r13; unsigned __int64
0x18002f71d  mov     rcx, r12; unsigned __int16 *
0x18002f720  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002f725  mov     esi, eax
0x18002f727  mov     [rsp+0B8h+var_48], eax
0x18002f72b  test    eax, eax
0x18002f72d  jns     short loc_18002F793
0x18002f72f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f735  mov     edx, esi
0x18002f737  mov     rcx, rax
0x18002f73a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f740  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f747  cmp     rcx, r14
0x18002f74a  jz      short loc_18002F771
0x18002f74c  test    byte ptr [rcx+1Ch], 1
0x18002f750  jz      short loc_18002F771
0x18002f752  cmp     byte ptr [rcx+19h], 2
0x18002f756  jb      short loc_18002F771
0x18002f758  mov     edx, 0B1h
0x18002f75d  mov     r9d, esi
0x18002f760  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f767  mov     rcx, [rcx+10h]
0x18002f76b  call    WPP_SF_d
0x18002f770  nop
0x18002f771  lea     rcx, [rsp+0B8h+arg_18]
0x18002f779  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f77e  nop
0x18002f77f  mov     rcx, rdi; this
0x18002f782  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f787  mov     [rsp+0B8h+var_40], rbx
0x18002f78c  mov     eax, esi
0x18002f78e  jmp     loc_18002F9E5
0x18002f793  lea     r8, Delimiter; "\\"
0x18002f79a  mov     rdx, r13; unsigned __int64
0x18002f79d  mov     rcx, r12; unsigned __int16 *
0x18002f7a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f7a5  mov     esi, eax
0x18002f7a7  mov     [rsp+0B8h+var_48], eax
0x18002f7ab  test    eax, eax
0x18002f7ad  jns     short loc_18002F813
0x18002f7af  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f7b5  mov     edx, esi
0x18002f7b7  mov     rcx, rax
0x18002f7ba  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7c7  cmp     rcx, r14
0x18002f7ca  jz      short loc_18002F7F1
0x18002f7cc  test    byte ptr [rcx+1Ch], 1
0x18002f7d0  jz      short loc_18002F7F1
0x18002f7d2  cmp     byte ptr [rcx+19h], 2
0x18002f7d6  jb      short loc_18002F7F1
0x18002f7d8  mov     edx, 0B2h
0x18002f7dd  mov     r9d, esi
0x18002f7e0  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f7e7  mov     rcx, [rcx+10h]
0x18002f7eb  call    WPP_SF_d
0x18002f7f0  nop
0x18002f7f1  lea     rcx, [rsp+0B8h+arg_18]
0x18002f7f9  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f7fe  nop
0x18002f7ff  mov     rcx, rdi; this
0x18002f802  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f807  mov     [rsp+0B8h+var_40], rbx
0x18002f80c  mov     eax, esi
0x18002f80e  jmp     loc_18002F9E5
0x18002f813  mov     rsi, [rsp+0B8h+arg_8]
0x18002f81b  mov     r8, rsi; unsigned __int16 *
0x18002f81e  mov     rdx, r13; unsigned __int64
0x18002f821  mov     rcx, r12; unsigned __int16 *
0x18002f824  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f829  mov     esi, eax
0x18002f82b  mov     [rsp+0B8h+var_48], eax
0x18002f82f  test    eax, eax
0x18002f831  jns     short loc_18002F897
0x18002f833  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f839  mov     edx, esi
0x18002f83b  mov     rcx, rax
0x18002f83e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f844  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f84b  cmp     rcx, r14
0x18002f84e  jz      short loc_18002F875
0x18002f850  test    byte ptr [rcx+1Ch], 1
0x18002f854  jz      short loc_18002F875
0x18002f856  cmp     byte ptr [rcx+19h], 2
0x18002f85a  jb      short loc_18002F875
0x18002f85c  mov     edx, 0B3h
0x18002f861  mov     r9d, esi
0x18002f864  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f86b  mov     rcx, [rcx+10h]
0x18002f86f  call    WPP_SF_d
0x18002f874  nop
0x18002f875  lea     rcx, [rsp+0B8h+arg_18]
0x18002f87d  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f882  nop
0x18002f883  mov     rcx, rdi; this
0x18002f886  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f88b  mov     [rsp+0B8h+var_40], rbx
0x18002f890  mov     eax, esi
0x18002f892  jmp     loc_18002F9E5
0x18002f897  mov     [rsp+0B8h+var_50], ebx; unsigned int
0x18002f89b  mov     rax, [r15+28h]
0x18002f89f  mov     [rsp+0B8h+var_58], rax; struct IWmiDbSession *
0x18002f8a4  mov     rax, [r15+128h]
0x18002f8ab  mov     [rsp+0B8h+var_68], rax; unsigned __int64
0x18002f8b0  mov     eax, [r15+130h]
0x18002f8b7  mov     [rsp+0B8h+var_70], eax; unsigned int
0x18002f8bb  mov     rax, [r15+120h]
0x18002f8c2  mov     [rsp+0B8h+var_78], rax; unsigned __int16 *
0x18002f8c7  mov     rax, [r15+118h]
0x18002f8ce  mov     [rsp+0B8h+var_80], rax; unsigned __int16 *
0x18002f8d3  mov     [rsp+0B8h+var_88], 1; int
0x18002f8db  mov     eax, [r15+80h]
0x18002f8e2  mov     [rsp+0B8h+var_90], eax; int
0x18002f8e6  mov     [rsp+0B8h+var_98], ebx; unsigned int
0x18002f8ea  xor     r9d, r9d; unsigned int
0x18002f8ed  mov     r8, [r15+70h]; unsigned __int16 *
0x18002f8f1  mov     rdx, r12; unsigned __int16 *
0x18002f8f4  mov     rcx, rdi; this
0x18002f8f7  call    ?Initialize@CWbemNamespace@@QEAAJPEAG0KKHHPEBG1K_KHPEAUIWmiDbSession@@K@Z; CWbemNamespace::Initialize(ushort *,ushort *,ulong,ulong,int,int,ushort const *,ushort const *,ulong,unsigned __int64,int,IWmiDbSession *,ulong)
0x18002f8fc  mov     esi, eax
0x18002f8fe  mov     [rsp+0B8h+var_48], eax
0x18002f902  test    eax, eax
0x18002f904  jns     short loc_18002F967
0x18002f906  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f90c  mov     edx, esi
0x18002f90e  mov     rcx, rax
0x18002f911  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f91e  cmp     rcx, r14
0x18002f921  jz      short loc_18002F948
0x18002f923  test    byte ptr [rcx+1Ch], 1
0x18002f927  jz      short loc_18002F948
0x18002f929  cmp     byte ptr [rcx+19h], 2
0x18002f92d  jb      short loc_18002F948
0x18002f92f  mov     edx, 0B4h
0x18002f934  mov     r9d, esi
0x18002f937  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f93e  mov     rcx, [rcx+10h]
0x18002f942  call    WPP_SF_d
0x18002f947  nop
0x18002f948  lea     rcx, [rsp+0B8h+arg_18]
0x18002f950  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f955  nop
0x18002f956  mov     rcx, rdi; this
0x18002f959  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f95e  mov     [rsp+0B8h+var_40], rbx
0x18002f963  mov     eax, esi
0x18002f965  jmp     short loc_18002F9E5
0x18002f967  lock inc dword ptr [rdi+18h]
0x18002f96b  mov     rax, [rsp+0B8h+arg_10]
0x18002f973  mov     [rax], rdi
0x18002f976  lea     rcx, [rsp+0B8h+arg_18]
0x18002f97e  call    ??1?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::~unique_ptr<IUnknown * [0]>(void)
0x18002f983  nop
0x18002f984  mov     rcx, rdi; this
0x18002f987  call    ?Release@CWbemNamespace@@UEAAKXZ; CWbemNamespace::Release(void)
0x18002f98c  mov     [rsp+0B8h+var_40], rbx
0x18002f991  jmp     short loc_18002F99E
0x18002f993  lea     r14, WPP_GLOBAL_Control
0x18002f99a  mov     esi, [rsp+0B8h+var_48]
0x18002f99e  test    esi, esi
0x18002f9a0  jns     short loc_18002F9B3
0x18002f9a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002f9a8  mov     edx, esi
0x18002f9aa  mov     rcx, rax
0x18002f9ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f9b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f9ba  cmp     rcx, r14
0x18002f9bd  jz      short loc_18002F9E3
0x18002f9bf  test    byte ptr [rcx+1Ch], 1
0x18002f9c3  jz      short loc_18002F9E3
0x18002f9c5  cmp     byte ptr [rcx+19h], 2
0x18002f9c9  jb      short loc_18002F9E3
0x18002f9cb  mov     edx, 0B5h
0x18002f9d0  mov     r9d, esi
0x18002f9d3  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002f9da  mov     rcx, [rcx+10h]
0x18002f9de  call    WPP_SF_d
0x18002f9e3  mov     eax, esi
0x18002f9e5  add     rsp, 80h
0x18002f9ec  pop     r15
0x18002f9ee  pop     r14
0x18002f9f0  pop     r13
0x18002f9f2  pop     r12
0x18002f9f4  pop     rdi
0x18002f9f5  pop     rsi
0x18002f9f6  pop     rbx
0x18002f9f7  retn
```
