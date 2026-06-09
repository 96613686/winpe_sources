# CWmiArbitrator::MapProviderToTask(ulong,IWbemContext *,IWbemServices *,CProviderSink *)

- ea: `0x180039134`
- end: `0x180039449`
- name: `?MapProviderToTask@CWmiArbitrator@@QEAAJKPEAUIWbemContext@@PEAUIWbemServices@@PEAVCProviderSink@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CWmiArbitrator *__hidden this, unsigned int, struct IWbemContext *, struct IWbemServices *, struct CProviderSink *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800385c0`
- `0x180039450`

## callees

- `0x18000b140`
- `0x1800360e4`
- `0x180039134`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039174`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180039174`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800391a2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800391a2`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180039226`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180039226`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800391f7`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800391f7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003924e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180039340`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800393ed`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18003924e`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180039340`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800393ed`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003923b`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18003923b`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180039213`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180039213`
- `wbemcomn!GetMemLogObject` at `0x1800392a1`
- `wbemcomn!GetMemLogObject` at `0x1800392ea`
- `wbemcomn!GetMemLogObject` at `0x180039353`
- `wbemcomn!GetMemLogObject` at `0x180039369`
- `wbemcomn!GetMemLogObject` at `0x18003939e`
- `wbemcomn!GetMemLogObject` at `0x1800393f8`
- `wbemcomn!GetMemLogObject` at `0x1800392a1`
- `wbemcomn!GetMemLogObject` at `0x1800392ea`
- `wbemcomn!GetMemLogObject` at `0x180039353`
- `wbemcomn!GetMemLogObject` at `0x180039369`
- `wbemcomn!GetMemLogObject` at `0x18003939e`
- `wbemcomn!GetMemLogObject` at `0x1800393f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800392b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800392fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003935e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039379`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800393ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039408`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800392b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800392fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003935e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039379`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800393ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039408`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWmiArbitrator::MapProviderToTask(
        CWmiArbitrator *this,
        __int64 a2,
        struct IWbemContext *a3,
        struct IWbemServices *a4,
        struct CProviderSink *a5)
{
  struct CProviderSink *v6; // rsi
  _QWORD *Value; // rax
  __int64 v8; // rbx
  __int64 v9; // rbx
  STaskProvider *v10; // rax
  STaskProvider *v11; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  CClientCnt *v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v19; // rax
  unsigned int v20; // edx
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CClientCnt *v23; // rcx
  __int64 v24; // rdx
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CWmiArbitrator *v27; // [rsp+40h] [rbp+8h] BYREF

  v27 = this;
  if ( !a3 || (v6 = a5) == 0 || !a4 )
  {
    MemLogObject = GetMemLogObject();
    v13 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v13;
    }
    v16 = 57;
    v17 = 2147749896LL;
    goto LABEL_20;
  }
  Value = TlsGetValue(g_QueueTlsIndex);
  if ( !Value || (v8 = Value[1]) == 0 )
  {
    v26 = GetMemLogObject();
    v13 = -2147217407;
    CMemoryLog::Write(v26, -2147217407);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v13;
    }
    v16 = 58;
    v17 = 2147749889LL;
    goto LABEL_20;
  }
  v9 = *(_QWORD *)(v8 + 32);
  if ( v9 )
  {
    v10 = (STaskProvider *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v11 = v10;
    v27 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
    }
    else
    {
      v11 = 0;
    }
    if ( !v11 )
    {
      v19 = GetMemLogObject();
      v13 = -2147217402;
      CMemoryLog::Write(v19, -2147217402);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v13;
      }
      v16 = 59;
      v17 = 2147749894LL;
      goto LABEL_20;
    }
    ((void (__fastcall *)(struct IWbemServices *))a4->lpVtbl->AddRef)(a4);
    *(_QWORD *)v11 = a4;
    _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
    *((_QWORD *)v11 + 1) = v6;
    CInCritSec::CInCritSec((CInCritSec *)&v27, (struct _RTL_CRITICAL_SECTION *)(v9 + 272));
    if ( *(_DWORD *)(v9 + 16) == 1 )
    {
      CInCritSec::~CInCritSec((CInCritSec *)&v27);
      v13 = -2147217358;
LABEL_31:
      STaskProvider::`scalar deleting destructor'(v11, v20);
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v13);
LABEL_14:
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v13;
      }
      v16 = 60;
      v17 = v13;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v14 + 2), v16, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids, v17);
      return v13;
    }
    v12 = CFlexArray::Size((CFlexArray *)(v9 + 40));
    if ( CFlexArray::InsertAt((CFlexArray *)(v9 + 352), v12 + 1, 0) )
    {
      v22 = GetMemLogObject();
      v13 = -2147217402;
      CMemoryLog::Write(v22, -2147217402);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v24 = 31;
    }
    else
    {
      if ( !CFlexArray::Add((CFlexArray *)(v9 + 40), v11) )
      {
        CInCritSec::~CInCritSec((CInCritSec *)&v27);
        v13 = 0;
        goto LABEL_14;
      }
      v25 = GetMemLogObject();
      v13 = -2147217402;
      CMemoryLog::Write(v25, -2147217402);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_41;
      }
      v24 = 32;
    }
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids, 2147749894LL);
LABEL_41:
    CInCritSec::~CInCritSec((CInCritSec *)&v27);
    goto LABEL_31;
  }
  return 0;
}

```

## disassembly

```asm
0x180039134  mov     [rsp+arg_8], rbx
0x180039139  mov     [rsp+arg_10], rbp
0x18003913e  mov     [rsp+arg_0], rcx
0x180039143  push    rsi
0x180039144  push    rdi
0x180039145  push    r14
0x180039147  sub     rsp, 20h
0x18003914b  mov     r14, r9
0x18003914e  test    r8, r8
0x180039151  jz      loc_1800392A1
0x180039157  mov     rsi, [rsp+38h+arg_20]
0x18003915c  test    rsi, rsi
0x18003915f  jz      loc_1800392A1
0x180039165  test    r9, r9
0x180039168  jz      loc_1800392A1
0x18003916e  mov     ecx, cs:?g_QueueTlsIndex@@3VCTLS@@A; dwTlsIndex
0x180039174  call    cs:__imp_TlsGetValue
0x18003917a  test    rax, rax
0x18003917d  jz      loc_1800393F8
0x180039183  mov     rbx, [rax+8]
0x180039187  test    rbx, rbx
0x18003918a  jz      loc_1800393F8
0x180039190  mov     rbx, [rbx+20h]
0x180039194  test    rbx, rbx
0x180039197  jz      loc_18003927D
0x18003919d  mov     ecx, 10h
0x1800391a2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800391a8  mov     rdi, rax
0x1800391ab  mov     [rsp+38h+arg_0], rax
0x1800391b0  test    rax, rax
0x1800391b3  jz      loc_1800392E3
0x1800391b9  mov     qword ptr [rax], 0
0x1800391c0  mov     qword ptr [rax+8], 0
0x1800391c8  test    rdi, rdi
0x1800391cb  jz      loc_1800392EA
0x1800391d1  mov     rax, [r14]
0x1800391d4  mov     rcx, r14
0x1800391d7  mov     rax, [rax+8]
0x1800391db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391e0  mov     [rdi], r14
0x1800391e3  lock inc dword ptr [rsi+8]
0x1800391e7  mov     [rdi+8], rsi
0x1800391eb  lea     rdx, [rbx+110h]
0x1800391f2  lea     rcx, [rsp+38h+arg_0]
0x1800391f7  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800391fd  nop
0x1800391fe  lea     rsi, WPP_GLOBAL_Control
0x180039205  cmp     dword ptr [rbx+10h], 1
0x180039209  jz      loc_18003933B
0x18003920f  lea     rcx, [rbx+28h]
0x180039213  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180039219  lea     edx, [rax+1]
0x18003921c  lea     rcx, [rbx+160h]
0x180039223  xor     r8d, r8d
0x180039226  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18003922c  test    eax, eax
0x18003922e  jnz     loc_180039369
0x180039234  mov     rdx, rdi
0x180039237  lea     rcx, [rbx+28h]
0x18003923b  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180039241  test    eax, eax
0x180039243  jnz     loc_18003939E
0x180039249  lea     rcx, [rsp+38h+arg_0]
0x18003924e  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180039254  xor     ebx, ebx
0x180039256  mov     rcx, cs:WPP_GLOBAL_Control
0x18003925d  cmp     rcx, rsi
0x180039260  jz      short loc_180039268
0x180039262  test    byte ptr [rcx+1Ch], 1
0x180039266  jnz     short loc_180039281
0x180039268  mov     eax, ebx
0x18003926a  mov     rbx, [rsp+38h+arg_8]
0x18003926f  mov     rbp, [rsp+38h+arg_10]
0x180039274  add     rsp, 20h
0x180039278  pop     r14
0x18003927a  pop     rdi
0x18003927b  pop     rsi
0x18003927c  retn
0x18003927d  xor     eax, eax
0x18003927f  jmp     short loc_18003926A
0x180039281  cmp     byte ptr [rcx+19h], 2
0x180039285  jb      short loc_180039268
0x180039287  mov     edx, 3Ch ; '<'
0x18003928c  mov     r9d, ebx
0x18003928f  lea     r8, WPP_a64fd86e59563ee6e85d17b4dd415fcc_Traceguids
0x180039296  mov     rcx, [rcx+10h]
0x18003929a  call    WPP_SF_d
0x18003929f  jmp     short loc_180039268
0x1800392a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800392a7  mov     ebx, 80041008h
0x1800392ac  mov     edx, ebx
0x1800392ae  mov     rcx, rax
0x1800392b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800392b7  lea     rsi, WPP_GLOBAL_Control
0x1800392be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392c5  cmp     rcx, rsi
0x1800392c8  jz      short loc_180039268
0x1800392ca  test    byte ptr [rcx+1Ch], 1
0x1800392ce  jz      short loc_180039268
0x1800392d0  cmp     byte ptr [rcx+19h], 2
0x1800392d4  jb      short loc_180039268
0x1800392d6  mov     edx, 39h ; '9'
0x1800392db  mov     r9d, 80041008h
0x1800392e1  jmp     short loc_18003928F
0x1800392e3  xor     edi, edi
0x1800392e5  jmp     loc_1800391C8
0x1800392ea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800392f0  mov     ebx, 80041006h
0x1800392f5  mov     edx, ebx
0x1800392f7  mov     rcx, rax
0x1800392fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039300  lea     rsi, WPP_GLOBAL_Control
0x180039307  mov     rcx, cs:WPP_GLOBAL_Control
0x18003930e  cmp     rcx, rsi
0x180039311  jz      loc_180039268
0x180039317  test    byte ptr [rcx+1Ch], 1
0x18003931b  jz      loc_180039268
0x180039321  cmp     byte ptr [rcx+19h], 2
0x180039325  jb      loc_180039268
0x18003932b  mov     edx, 3Bh ; ';'
0x180039330  mov     r9d, 80041006h
0x180039336  jmp     loc_18003928F
0x18003933b  lea     rcx, [rsp+38h+arg_0]
0x180039340  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180039346  mov     ebx, 80041032h
0x18003934b  mov     rcx, rdi; this
0x18003934e  call    ??_GSTaskProvider@@QEAAPEAXI@Z; STaskProvider::`scalar deleting destructor'(uint)
0x180039353  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180039359  mov     edx, ebx
0x18003935b  mov     rcx, rax
0x18003935e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039364  jmp     loc_180039256
0x180039369  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003936f  mov     ebx, 80041006h
0x180039374  mov     edx, ebx
0x180039376  mov     rcx, rax
0x180039379  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003937f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039386  cmp     rcx, rsi
0x180039389  jz      short loc_1800393E8
0x18003938b  test    byte ptr [rcx+1Ch], 1
0x18003938f  jz      short loc_1800393E8
0x180039391  cmp     byte ptr [rcx+19h], 2
0x180039395  jb      short loc_1800393E8
0x180039397  mov     edx, 1Fh
0x18003939c  jmp     short loc_1800393D1
0x18003939e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800393a4  mov     ebx, 80041006h
0x1800393a9  mov     edx, ebx
0x1800393ab  mov     rcx, rax
0x1800393ae  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800393b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393bb  cmp     rcx, rsi
0x1800393be  jz      short loc_1800393E8
0x1800393c0  test    byte ptr [rcx+1Ch], 1
0x1800393c4  jz      short loc_1800393E8
0x1800393c6  cmp     byte ptr [rcx+19h], 2
0x1800393ca  jb      short loc_1800393E8
0x1800393cc  mov     edx, 20h ; ' '
0x1800393d1  mov     r9d, 80041006h
0x1800393d7  lea     r8, WPP_84b7b39b00a13273f9b8d757c3084cc7_Traceguids
0x1800393de  mov     rcx, [rcx+10h]
0x1800393e2  call    WPP_SF_d
0x1800393e7  nop
0x1800393e8  lea     rcx, [rsp+38h+arg_0]
0x1800393ed  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800393f3  jmp     loc_18003934B
0x1800393f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800393fe  mov     ebx, 80041001h
0x180039403  mov     edx, ebx
0x180039405  mov     rcx, rax
0x180039408  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003940e  lea     rsi, WPP_GLOBAL_Control
0x180039415  mov     rcx, cs:WPP_GLOBAL_Control
0x18003941c  cmp     rcx, rsi
0x18003941f  jz      loc_180039268
0x180039425  test    byte ptr [rcx+1Ch], 1
0x180039429  jz      loc_180039268
0x18003942f  cmp     byte ptr [rcx+19h], 2
0x180039433  jb      loc_180039268
0x180039439  mov     edx, 3Ah ; ':'
0x18003943e  mov     r9d, 80041001h
0x180039444  jmp     loc_18003928F
```
