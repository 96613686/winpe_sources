# CDlpTransportBits::Initialize(IDlpTransportFactory *,IBackgroundCopyManager *)

- ea: `0x180065f64`
- end: `0x1800665c0`
- name: `?Initialize@CDlpTransportBits@@QEAAJPEAVIDlpTransportFactory@@PEAUIBackgroundCopyManager@@@Z`
- size: `1628`
- prototype: `__int64 __fastcall(CDlpTransportBits *__hidden this, struct IDlpTransportFactory *, struct IBackgroundCopyManager *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004ed40`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001cdb0`
- `0x18001ce28`
- `0x18001fd60`
- `0x18005a960`
- `0x180065f64`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006617f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006617f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065ff1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066451`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065ff1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066451`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066017`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800664eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066017`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800664eb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006608b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006608b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800665a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800665a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066194`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDlpTransportBits::Initialize(
        CDlpTransportBits *this,
        struct IDlpTransportFactory *a2,
        struct IBackgroundCopyManager *a3)
{
  int v5; // edi
  signed int BitsCopyManager; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // r14
  int v10; // ebx
  HRESULT v11; // eax
  HANDLE EventW; // rbx
  void *v13; // rcx
  signed int LastError; // eax
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+28h] [rbp-40h]
  struct IBackgroundCopyManager *v22; // [rsp+78h] [rbp+10h] BYREF
  int v23; // [rsp+80h] [rbp+18h]
  int v24; // [rsp+84h] [rbp+1Ch]

  v24 = HIDWORD(a3);
  v5 = 0;
  v23 = 0;
  v22 = 0;
  if ( !a2 )
  {
    BitsCopyManager = -2147024809;
    if ( !(*(__int64 (__fastcall **)(char *, _QWORD, struct IBackgroundCopyManager *))(*((_QWORD *)this + 21) + 16LL))(
            (char *)this + 168,
            0,
            a3) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = -2147024809;
    v20 = 223;
    goto LABEL_77;
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v10 = *((_DWORD *)this + 54);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection(v9);
  if ( v10 != -21037378 )
  {
    BitsCopyManager = -2147023649;
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = -2147023649;
    v20 = 228;
    goto LABEL_77;
  }
  BitsCopyManager = 0;
  v11 = CoInitializeEx(0, 0);
  if ( v11 < 0 )
  {
    if ( v11 != -2147417850 )
    {
      BitsCopyManager = v11;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    }
  }
  else
  {
    v5 = 1;
    v23 = 1;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 232;
    goto LABEL_77;
  }
  BitsCopyManager = CDlpTransportBits::GetBitsCopyManager(this, &v22);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 244;
    goto LABEL_77;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v13 = (void *)*((_QWORD *)this + 73);
  if ( v13 )
    CloseHandle(v13);
  if ( !EventW )
  {
    *((_QWORD *)this + 73) = 0;
    LastError = GetLastError();
    BitsCopyManager = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        BitsCopyManager = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      BitsCopyManager = -2147467259;
    }
    if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
    {
      v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
      v8 = 0;
      if ( BitsCopyManager < 0 && v7 )
      {
        v21 = BitsCopyManager;
        v20 = 249;
        goto LABEL_77;
      }
      goto LABEL_79;
    }
    goto LABEL_80;
  }
  *((_QWORD *)this + 73) = EventW;
  *(_QWORD *)((char *)this + 652) = 3;
  BitsCopyManager = CExclusiveAcquireLock::Init((CDlpTransportBits *)((char *)this + 288));
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 261;
    goto LABEL_77;
  }
  BitsCopyManager = CDword::Init((CDlpTransportBits *)((char *)this + 392), 0);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 262;
    goto LABEL_77;
  }
  BitsCopyManager = CDword::Init((CDlpTransportBits *)((char *)this + 456), 0);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 263;
    goto LABEL_77;
  }
  BitsCopyManager = CDword::Init((CDlpTransportBits *)((char *)this + 520), 0);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 264;
    goto LABEL_77;
  }
  v15 = CExclusiveAcquireLock::Init((CDlpTransportBits *)((char *)this + 120));
  BitsCopyManager = v15;
  if ( v15 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( BitsCopyManager < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
      goto LABEL_80;
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( !v7 )
      goto LABEL_79;
    v21 = BitsCopyManager;
    v20 = 268;
    goto LABEL_77;
  }
  *((_QWORD *)this + 11) = a2;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  EnterCriticalSection(v9);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v16 = *((_DWORD *)this + 54);
  switch ( v16 )
  {
    case 0:
    case -21037378:
      goto LABEL_70;
    case -858993460:
      BitsCopyManager = -1048575735;
      goto LABEL_68;
    case -1:
      BitsCopyManager = -1048575734;
      goto LABEL_68;
    case -1073741824:
      BitsCopyManager = -2147023661;
LABEL_68:
      v17 = BitsCopyManager;
      goto LABEL_69;
  }
  if ( v16 == 1 || v16 == 2 || v16 == 3 || v16 != 4 && v16 != 6 )
  {
    v17 = -2147019873;
    BitsCopyManager = -2147019873;
LABEL_69:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
    goto LABEL_71;
  }
LABEL_70:
  *((_DWORD *)this + 54) = 0;
  BitsCopyManager = 0;
LABEL_71:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  LeaveCriticalSection(v9);
  if ( BitsCopyManager < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(BitsCopyManager);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( BitsCopyManager < 0 && (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168) )
  {
    v7 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 21) + 16LL))((char *)this + 168);
    v8 = 0;
    if ( v7 )
    {
      v21 = BitsCopyManager;
      v20 = 277;
LABEL_77:
      v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v7,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpTransportBits::Initialize",
              v20,
              v21);
      v8 = (unsigned int)v18;
      if ( v18 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
    }
LABEL_79:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  }
LABEL_80:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)BitsCopyManager);
  if ( v22 )
    ((void (__fastcall *)(struct IBackgroundCopyManager *))v22->lpVtbl->Release)(v22);
  if ( v5 )
    CoUninitialize();
  return (unsigned int)BitsCopyManager;
}

```

## disassembly

```asm
0x180065f64  mov     rax, rsp
0x180065f67  mov     [rax+8], rbx
0x180065f6b  mov     [rax+20h], rbp
0x180065f6f  mov     [rax+18h], r8
0x180065f73  push    rsi
0x180065f74  push    rdi
0x180065f75  push    r14
0x180065f77  sub     rsp, 50h
0x180065f7b  mov     rbp, rdx
0x180065f7e  mov     rsi, rcx
0x180065f81  xor     edi, edi
0x180065f83  mov     [rax+18h], edi
0x180065f86  mov     [rax+10h], rdi
0x180065f8a  test    rdx, rdx
0x180065f8d  jnz     short loc_180065FE7
0x180065f8f  mov     ebx, 80070057h
0x180065f94  mov     rax, [rcx+0A8h]
0x180065f9b  add     rcx, 0A8h
0x180065fa2  mov     rax, [rax+10h]
0x180065fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fab  test    rax, rax
0x180065fae  jz      loc_180066580
0x180065fb4  mov     rax, [rsi+0A8h]
0x180065fbb  lea     rcx, [rsi+0A8h]
0x180065fc2  mov     rax, [rax+10h]
0x180065fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065fcb  xor     ecx, ecx
0x180065fcd  test    rax, rax
0x180065fd0  jz      loc_18006657B
0x180065fd6  mov     [rsp+68h+var_40], ebx
0x180065fda  mov     [rsp+68h+var_48], 0DFh
0x180065fe2  jmp     loc_180066555
0x180065fe7  lea     r14, [rcx+0E8h]
0x180065fee  mov     rcx, r14; lpCriticalSection
0x180065ff1  call    cs:__imp_EnterCriticalSection
0x180065ff7  mov     [rsp+68h+var_28], 1
0x180065fff  mov     ebx, [rsi+0D8h]
0x180066005  xor     ecx, ecx
0x180066007  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006600c  mov     eax, [rsp+68h+var_28]
0x180066010  test    eax, eax
0x180066012  jz      short loc_180066025
0x180066014  mov     rcx, r14; lpCriticalSection
0x180066017  call    cs:__imp_LeaveCriticalSection
0x18006601d  mov     [rsp+68h+var_28], 0
0x180066025  cmp     ebx, 0FEBEFEBEh
0x18006602b  jz      short loc_180066085
0x18006602d  mov     ebx, 800704DFh
0x180066032  mov     rax, [rsi+0A8h]
0x180066039  lea     rcx, [rsi+0A8h]
0x180066040  mov     rax, [rax+10h]
0x180066044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066049  test    rax, rax
0x18006604c  jz      loc_180066580
0x180066052  mov     rax, [rsi+0A8h]
0x180066059  lea     rcx, [rsi+0A8h]
0x180066060  mov     rax, [rax+10h]
0x180066064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066069  xor     ecx, ecx
0x18006606b  test    rax, rax
0x18006606e  jz      loc_18006657B
0x180066074  mov     [rsp+68h+var_40], ebx
0x180066078  mov     [rsp+68h+var_48], 0E4h
0x180066080  jmp     loc_180066555
0x180066085  xor     ebx, ebx
0x180066087  xor     edx, edx; dwCoInit
0x180066089  xor     ecx, ecx; pvReserved
0x18006608b  call    cs:__imp_CoInitializeEx
0x180066091  test    eax, eax
0x180066093  js      short loc_1800660A1
0x180066095  lea     edi, [rbx+1]
0x180066098  mov     [rsp+68h+arg_10], edi
0x18006609f  jmp     short loc_1800660B1
0x1800660a1  cmp     eax, 80010106h
0x1800660a6  jz      short loc_1800660B1
0x1800660a8  mov     ebx, eax
0x1800660aa  mov     ecx, eax
0x1800660ac  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800660b1  mov     ecx, ebx
0x1800660b3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800660b8  test    ebx, ebx
0x1800660ba  jns     short loc_18006610F
0x1800660bc  mov     rax, [rsi+0A8h]
0x1800660c3  lea     rcx, [rsi+0A8h]
0x1800660ca  mov     rax, [rax+10h]
0x1800660ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660d3  test    rax, rax
0x1800660d6  jz      loc_180066580
0x1800660dc  mov     rax, [rsi+0A8h]
0x1800660e3  lea     rcx, [rsi+0A8h]
0x1800660ea  mov     rax, [rax+10h]
0x1800660ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800660f3  xor     ecx, ecx
0x1800660f5  test    rax, rax
0x1800660f8  jz      loc_18006657B
0x1800660fe  mov     [rsp+68h+var_40], ebx
0x180066102  mov     [rsp+68h+var_48], 0E8h
0x18006610a  jmp     loc_180066555
0x18006610f  lea     rdx, [rsp+68h+arg_8]; struct IBackgroundCopyManager **
0x180066114  mov     rcx, rsi; this
0x180066117  call    ?GetBitsCopyManager@CDlpTransportBits@@AEAAJPEAPEAUIBackgroundCopyManager@@@Z; CDlpTransportBits::GetBitsCopyManager(IBackgroundCopyManager * *)
0x18006611c  mov     ebx, eax
0x18006611e  test    eax, eax
0x180066120  jns     short loc_180066175
0x180066122  mov     rdx, [rsi+0A8h]
0x180066129  lea     rcx, [rsi+0A8h]
0x180066130  mov     rax, [rdx+10h]
0x180066134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066139  test    rax, rax
0x18006613c  jz      loc_180066580
0x180066142  mov     rax, [rsi+0A8h]
0x180066149  lea     rcx, [rsi+0A8h]
0x180066150  mov     rax, [rax+10h]
0x180066154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066159  xor     ecx, ecx
0x18006615b  test    rax, rax
0x18006615e  jz      loc_18006657B
0x180066164  mov     [rsp+68h+var_40], ebx
0x180066168  mov     [rsp+68h+var_48], 0F4h
0x180066170  jmp     loc_180066555
0x180066175  xor     r9d, r9d; lpName
0x180066178  xor     r8d, r8d; bInitialState
0x18006617b  xor     edx, edx; bManualReset
0x18006617d  xor     ecx, ecx; lpEventAttributes
0x18006617f  call    cs:__imp_CreateEventW
0x180066185  mov     rbx, rax
0x180066188  mov     rcx, [rsi+248h]; hObject
0x18006618f  test    rcx, rcx
0x180066192  jz      short loc_18006619A
0x180066194  call    cs:__imp_CloseHandle
0x18006619a  test    rbx, rbx
0x18006619d  jnz     loc_180066223
0x1800661a3  mov     [rsi+248h], rbx
0x1800661aa  call    cs:__imp_GetLastError
0x1800661b0  mov     ebx, eax
0x1800661b2  test    eax, eax
0x1800661b4  jnz     short loc_1800661BD
0x1800661b6  mov     ebx, 80004005h
0x1800661bb  jmp     short loc_1800661C8
0x1800661bd  jle     short loc_1800661C8
0x1800661bf  movzx   ebx, ax
0x1800661c2  or      ebx, 80070000h
0x1800661c8  mov     rax, [rsi+0A8h]
0x1800661cf  lea     rcx, [rsi+0A8h]
0x1800661d6  mov     rax, [rax+10h]
0x1800661da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661df  test    rax, rax
0x1800661e2  jz      loc_180066580
0x1800661e8  mov     rax, [rsi+0A8h]
0x1800661ef  lea     rcx, [rsi+0A8h]
0x1800661f6  mov     rax, [rax+10h]
0x1800661fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661ff  xor     ecx, ecx
0x180066201  test    ebx, ebx
0x180066203  jns     loc_18006657B
0x180066209  test    rax, rax
0x18006620c  jz      loc_18006657B
0x180066212  mov     [rsp+68h+var_40], ebx
0x180066216  mov     [rsp+68h+var_48], 0F9h
0x18006621e  jmp     loc_180066555
0x180066223  mov     [rsi+248h], rbx
0x18006622a  mov     qword ptr [rsi+28Ch], 3
0x180066235  lea     rcx, [rsi+120h]; this
0x18006623c  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x180066241  mov     ebx, eax
0x180066243  test    eax, eax
0x180066245  jns     short loc_18006629A
0x180066247  mov     rax, [rsi+0A8h]
0x18006624e  lea     rcx, [rsi+0A8h]
0x180066255  mov     rax, [rax+10h]
0x180066259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006625e  test    rax, rax
0x180066261  jz      loc_180066580
0x180066267  mov     rax, [rsi+0A8h]
0x18006626e  lea     rcx, [rsi+0A8h]
0x180066275  mov     rax, [rax+10h]
0x180066279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006627e  xor     ecx, ecx
0x180066280  test    rax, rax
0x180066283  jz      loc_18006657B
0x180066289  mov     [rsp+68h+var_40], ebx
0x18006628d  mov     [rsp+68h+var_48], 105h
0x180066295  jmp     loc_180066555
0x18006629a  lea     rcx, [rsi+188h]; this
0x1800662a1  xor     edx, edx; unsigned int
0x1800662a3  call    ?Init@CDword@@QEAAJK@Z; CDword::Init(ulong)
0x1800662a8  mov     ebx, eax
0x1800662aa  test    eax, eax
0x1800662ac  jns     short loc_180066301
0x1800662ae  mov     rax, [rsi+0A8h]
0x1800662b5  lea     rcx, [rsi+0A8h]
0x1800662bc  mov     rax, [rax+10h]
0x1800662c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662c5  test    rax, rax
0x1800662c8  jz      loc_180066580
0x1800662ce  mov     rax, [rsi+0A8h]
0x1800662d5  lea     rcx, [rsi+0A8h]
0x1800662dc  mov     rax, [rax+10h]
0x1800662e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662e5  xor     ecx, ecx
0x1800662e7  test    rax, rax
0x1800662ea  jz      loc_18006657B
0x1800662f0  mov     [rsp+68h+var_40], ebx
0x1800662f4  mov     [rsp+68h+var_48], 106h
0x1800662fc  jmp     loc_180066555
0x180066301  lea     rcx, [rsi+1C8h]; this
0x180066308  xor     edx, edx; unsigned int
0x18006630a  call    ?Init@CDword@@QEAAJK@Z; CDword::Init(ulong)
0x18006630f  mov     ebx, eax
0x180066311  test    eax, eax
0x180066313  jns     short loc_180066368
0x180066315  mov     rax, [rsi+0A8h]
0x18006631c  lea     rcx, [rsi+0A8h]
0x180066323  mov     rax, [rax+10h]
0x180066327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006632c  test    rax, rax
0x18006632f  jz      loc_180066580
0x180066335  mov     rax, [rsi+0A8h]
0x18006633c  lea     rcx, [rsi+0A8h]
0x180066343  mov     rax, [rax+10h]
0x180066347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006634c  xor     ecx, ecx
0x18006634e  test    rax, rax
0x180066351  jz      loc_18006657B
0x180066357  mov     [rsp+68h+var_40], ebx
0x18006635b  mov     [rsp+68h+var_48], 107h
0x180066363  jmp     loc_180066555
0x180066368  lea     rcx, [rsi+208h]; this
0x18006636f  xor     edx, edx; unsigned int
0x180066371  call    ?Init@CDword@@QEAAJK@Z; CDword::Init(ulong)
0x180066376  mov     ebx, eax
0x180066378  test    eax, eax
0x18006637a  jns     short loc_1800663CF
0x18006637c  mov     rax, [rsi+0A8h]
0x180066383  lea     rcx, [rsi+0A8h]
0x18006638a  mov     rax, [rax+10h]
0x18006638e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066393  test    rax, rax
0x180066396  jz      loc_180066580
0x18006639c  mov     rax, [rsi+0A8h]
0x1800663a3  lea     rcx, [rsi+0A8h]
0x1800663aa  mov     rax, [rax+10h]
0x1800663ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663b3  xor     ecx, ecx
0x1800663b5  test    rax, rax
0x1800663b8  jz      loc_18006657B
0x1800663be  mov     [rsp+68h+var_40], ebx
0x1800663c2  mov     [rsp+68h+var_48], 108h
0x1800663ca  jmp     loc_180066555
0x1800663cf  lea     rcx, [rsi+78h]; this
0x1800663d3  call    ?Init@CExclusiveAcquireLock@@QEAAJXZ; CExclusiveAcquireLock::Init(void)
0x1800663d8  mov     ebx, eax
0x1800663da  test    eax, eax
0x1800663dc  jns     short loc_1800663E5
0x1800663de  mov     ecx, eax
0x1800663e0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800663e5  mov     ecx, ebx
0x1800663e7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800663ec  test    ebx, ebx
0x1800663ee  jns     short loc_180066443
0x1800663f0  mov     rax, [rsi+0A8h]
0x1800663f7  lea     rcx, [rsi+0A8h]
0x1800663fe  mov     rax, [rax+10h]
0x180066402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066407  test    rax, rax
0x18006640a  jz      loc_180066580
0x180066410  mov     rax, [rsi+0A8h]
0x180066417  lea     rcx, [rsi+0A8h]
0x18006641e  mov     rax, [rax+10h]
0x180066422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066427  xor     ecx, ecx
0x180066429  test    rax, rax
0x18006642c  jz      loc_18006657B
0x180066432  mov     [rsp+68h+var_40], ebx
0x180066436  mov     [rsp+68h+var_48], 10Ch
0x18006643e  jmp     loc_180066555
0x180066443  mov     [rsi+58h], rbp
0x180066447  xor     ecx, ecx
0x180066449  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006644e  mov     rcx, r14; lpCriticalSection
0x180066451  call    cs:__imp_EnterCriticalSection
0x180066457  mov     [rsp+68h+var_28], 1
0x18006645f  xor     ecx, ecx
0x180066461  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066466  mov     eax, [rsi+0D8h]
0x18006646c  test    eax, eax
0x18006646e  jz      short loc_1800664CD
0x180066470  cmp     eax, 0FEBEFEBEh
0x180066475  jz      short loc_1800664CD
0x180066477  cmp     eax, 0CCCCCCCCh
0x18006647c  jz      short loc_1800664BF
0x18006647e  cmp     eax, 0FFFFFFFFh
0x180066481  jz      short loc_1800664B8
0x180066483  cmp     eax, 0C0000000h
0x180066488  jz      short loc_1800664B1
0x18006648a  cmp     eax, 1
0x18006648d  jz      short loc_1800664A8
0x18006648f  cmp     eax, 2
0x180066492  jz      short loc_1800664A8
0x180066494  cmp     eax, 3
  ... truncated ...
```
