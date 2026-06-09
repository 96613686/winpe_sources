# CDlpManager::AsyncSerializeEnable(void)

- ea: `0x180048290`
- end: `0x1800485d9`
- name: `?AsyncSerializeEnable@CDlpManager@@UEAAJXZ`
- size: `841`
- prototype: `__int64 __fastcall(CDlpManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001cd24`
- `0x18001fd60`
- `0x180048290`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180048516`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180048516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004853d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004853d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048399`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048440`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048399`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180048440`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800485c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004852b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800483ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048455`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004852b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDlpManager::AsyncSerializeEnable(CDlpManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  signed int v3; // edi
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // eax
  HANDLE EventW; // rbx
  void *v8; // rcx
  signed int v9; // eax
  HANDLE v10; // rbx
  void *v11; // rcx
  signed int v12; // eax
  HANDLE Thread; // rbx
  void *v14; // rcx
  signed int LastError; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-58h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-50h]
  char *v19; // [rsp+38h] [rbp-40h]
  unsigned int v20; // [rsp+80h] [rbp+8h] BYREF

  v19 = (char *)this + 248;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 256));
  v20 = 0;
  v3 = 0;
  if ( (*((_BYTE *)this + 856) & 1) == 0 )
    goto LABEL_44;
  v3 = CDword::Increment((CDlpManager *)((char *)this + 760), &v20);
  if ( v3 >= 0 )
  {
    if ( v20 != 1 )
      goto LABEL_44;
    EventW = CreateEventW(0, 0, 0, 0);
    v8 = (void *)*((_QWORD *)this + 84);
    if ( v8 )
      CloseHandle(v8);
    if ( EventW )
    {
      *((_QWORD *)this + 84) = EventW;
      v10 = CreateEventW(0, 1, 0, 0);
      v11 = (void *)*((_QWORD *)this + 85);
      if ( v11 )
        CloseHandle(v11);
      if ( v10 )
      {
        *((_QWORD *)this + 85) = v10;
        *((_QWORD *)this + 103) = this;
        *((_QWORD *)this + 104) = *((_QWORD *)this + 84);
        *((_QWORD *)this + 105) = v10;
        Thread = CreateThread(0, 0, CDlpManager::SerializeThreadProc, (char *)this + 824, 0, 0);
        v14 = (void *)*((_QWORD *)this + 86);
        if ( v14 )
          CloseHandle(v14);
        if ( Thread )
        {
          *((_QWORD *)this + 86) = Thread;
          goto LABEL_44;
        }
        *((_QWORD *)this + 86) = 0;
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_44;
        v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v5 = 0;
        if ( v3 >= 0 || !v4 )
          goto LABEL_8;
        LODWORD(lpThreadId) = v3;
        LODWORD(dwCreationFlags) = 488;
      }
      else
      {
        *((_QWORD *)this + 85) = 0;
        v12 = GetLastError();
        v3 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
          goto LABEL_44;
        v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
        v5 = 0;
        if ( v3 >= 0 || !v4 )
          goto LABEL_8;
        LODWORD(lpThreadId) = v3;
        LODWORD(dwCreationFlags) = 474;
      }
    }
    else
    {
      *((_QWORD *)this + 84) = 0;
      v9 = GetLastError();
      v3 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
        goto LABEL_44;
      v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
      v5 = 0;
      if ( v3 >= 0 || !v4 )
        goto LABEL_8;
      LODWORD(lpThreadId) = v3;
      LODWORD(dwCreationFlags) = 471;
    }
LABEL_6:
    v6 = CDlpLogT<CEmptyType>::DlpLogFormat(
           v4,
           4,
           L"%s(%d): Result = 0x%X",
           L"CDlpManager::AsyncSerializeEnable",
           dwCreationFlags,
           lpThreadId,
           &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
           v19);
    v5 = (unsigned int)v6;
    if ( v6 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
    goto LABEL_8;
  }
  if ( (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80) )
  {
    v4 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 10) + 16LL))((char *)this + 80);
    v5 = 0;
    if ( v4 )
    {
      LODWORD(lpThreadId) = v3;
      LODWORD(dwCreationFlags) = 465;
      goto LABEL_6;
    }
LABEL_8:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  }
LABEL_44:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v3);
  LeaveCriticalSection(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180048290  mov     r11, rsp
0x180048293  push    rbx
0x180048294  push    rbp
0x180048295  push    rsi
0x180048296  push    rdi
0x180048297  sub     rsp, 58h
0x18004829b  mov     rsi, rcx
0x18004829e  mov     qword ptr [r11-30h], 0
0x1800482a6  xorps   xmm0, xmm0
0x1800482a9  xor     eax, eax
0x1800482ab  movups  [rsp+78h+var_48], xmm0
0x1800482b0  mov     [r11-38h], rax
0x1800482b4  lea     rax, [rcx+0F8h]
0x1800482bb  mov     [r11-40h], rax
0x1800482bf  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x1800482c6  mov     [r11-48h], rcx
0x1800482ca  lea     rbp, [rax+8]
0x1800482ce  mov     rcx, rbp; lpCriticalSection
0x1800482d1  call    cs:__imp_EnterCriticalSection
0x1800482d7  mov     [rsp+78h+var_38], 1
0x1800482df  mov     [rsp+78h+arg_0], 0
0x1800482ea  xor     edi, edi
0x1800482ec  test    byte ptr [rsi+358h], 1
0x1800482f3  jz      loc_1800485AD
0x1800482f9  lea     rcx, [rsi+2F8h]; this
0x180048300  lea     rdx, [rsp+78h+arg_0]; unsigned int *
0x180048308  call    ?Increment@CDword@@QEAAJPEAK@Z; CDword::Increment(ulong *)
0x18004830d  mov     edi, eax
0x18004830f  test    eax, eax
0x180048311  jns     short loc_180048381
0x180048313  mov     rdx, [rsi+50h]
0x180048317  lea     rcx, [rsi+50h]
0x18004831b  mov     rax, [rdx+10h]
0x18004831f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048324  test    rax, rax
0x180048327  jz      loc_1800485AD
0x18004832d  mov     rax, [rsi+50h]
0x180048331  lea     rcx, [rsi+50h]
0x180048335  mov     rax, [rax+10h]
0x180048339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004833e  xor     ecx, ecx
0x180048340  test    rax, rax
0x180048343  jz      short loc_180048377
0x180048345  mov     dword ptr [rsp+78h+lpThreadId], edi
0x180048349  mov     dword ptr [rsp+78h+dwCreationFlags], 1D1h
0x180048351  lea     r9, aCdlpmanagerAsy; "CDlpManager::AsyncSerializeEnable"
0x180048358  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004835f  mov     edx, 4
0x180048364  mov     rcx, rax
0x180048367  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18004836c  test    eax, eax
0x18004836e  mov     ecx, eax
0x180048370  jns     short loc_180048377
0x180048372  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180048377  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004837c  jmp     loc_1800485AD
0x180048381  cmp     [rsp+78h+arg_0], 1
0x180048389  jnz     loc_1800485AD
0x18004838f  xor     r9d, r9d; lpName
0x180048392  xor     r8d, r8d; bInitialState
0x180048395  xor     edx, edx; bManualReset
0x180048397  xor     ecx, ecx; lpEventAttributes
0x180048399  call    cs:__imp_CreateEventW
0x18004839f  mov     rbx, rax
0x1800483a2  mov     rcx, [rsi+2A0h]; hObject
0x1800483a9  test    rcx, rcx
0x1800483ac  jz      short loc_1800483B4
0x1800483ae  call    cs:__imp_CloseHandle
0x1800483b4  test    rbx, rbx
0x1800483b7  jnz     short loc_18004842D
0x1800483b9  mov     [rsi+2A0h], rbx
0x1800483c0  call    cs:__imp_GetLastError
0x1800483c6  mov     edi, eax
0x1800483c8  test    eax, eax
0x1800483ca  jnz     short loc_1800483D3
0x1800483cc  mov     edi, 80004005h
0x1800483d1  jmp     short loc_1800483DE
0x1800483d3  jle     short loc_1800483DE
0x1800483d5  movzx   edi, ax
0x1800483d8  or      edi, 80070000h
0x1800483de  mov     rax, [rsi+50h]
0x1800483e2  lea     rcx, [rsi+50h]
0x1800483e6  mov     rax, [rax+10h]
0x1800483ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483ef  test    rax, rax
0x1800483f2  jz      loc_1800485AD
0x1800483f8  mov     rax, [rsi+50h]
0x1800483fc  lea     rcx, [rsi+50h]
0x180048400  mov     rax, [rax+10h]
0x180048404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048409  xor     ecx, ecx
0x18004840b  test    edi, edi
0x18004840d  jns     loc_180048377
0x180048413  test    rax, rax
0x180048416  jz      loc_180048377
0x18004841c  mov     dword ptr [rsp+78h+lpThreadId], edi
0x180048420  mov     dword ptr [rsp+78h+dwCreationFlags], 1D7h
0x180048428  jmp     loc_180048351
0x18004842d  mov     [rsi+2A0h], rbx
0x180048434  xor     r9d, r9d; lpName
0x180048437  xor     r8d, r8d; bInitialState
0x18004843a  lea     edx, [r9+1]; bManualReset
0x18004843e  xor     ecx, ecx; lpEventAttributes
0x180048440  call    cs:__imp_CreateEventW
0x180048446  mov     rbx, rax
0x180048449  mov     rcx, [rsi+2A8h]; hObject
0x180048450  test    rcx, rcx
0x180048453  jz      short loc_18004845B
0x180048455  call    cs:__imp_CloseHandle
0x18004845b  test    rbx, rbx
0x18004845e  jnz     short loc_1800484D4
0x180048460  mov     [rsi+2A8h], rbx
0x180048467  call    cs:__imp_GetLastError
0x18004846d  mov     edi, eax
0x18004846f  test    eax, eax
0x180048471  jnz     short loc_18004847A
0x180048473  mov     edi, 80004005h
0x180048478  jmp     short loc_180048485
0x18004847a  jle     short loc_180048485
0x18004847c  movzx   edi, ax
0x18004847f  or      edi, 80070000h
0x180048485  mov     rax, [rsi+50h]
0x180048489  lea     rcx, [rsi+50h]
0x18004848d  mov     rax, [rax+10h]
0x180048491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048496  test    rax, rax
0x180048499  jz      loc_1800485AD
0x18004849f  mov     rax, [rsi+50h]
0x1800484a3  lea     rcx, [rsi+50h]
0x1800484a7  mov     rax, [rax+10h]
0x1800484ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484b0  xor     ecx, ecx
0x1800484b2  test    edi, edi
0x1800484b4  jns     loc_180048377
0x1800484ba  test    rax, rax
0x1800484bd  jz      loc_180048377
0x1800484c3  mov     dword ptr [rsp+78h+lpThreadId], edi
0x1800484c7  mov     dword ptr [rsp+78h+dwCreationFlags], 1DAh
0x1800484cf  jmp     loc_180048351
0x1800484d4  mov     [rsi+2A8h], rbx
0x1800484db  lea     r9, [rsi+338h]; lpParameter
0x1800484e2  mov     [r9], rsi
0x1800484e5  mov     rax, [rsi+2A0h]
0x1800484ec  mov     [rsi+340h], rax
0x1800484f3  mov     [rsi+348h], rbx
0x1800484fa  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x180048503  mov     dword ptr [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18004850b  lea     r8, ?SerializeThreadProc@CDlpManager@@SAKPEAX@Z; lpStartAddress
0x180048512  xor     edx, edx; dwStackSize
0x180048514  xor     ecx, ecx; lpThreadAttributes
0x180048516  call    cs:__imp_CreateThread
0x18004851c  mov     rbx, rax
0x18004851f  mov     rcx, [rsi+2B0h]; hObject
0x180048526  test    rcx, rcx
0x180048529  jz      short loc_180048531
0x18004852b  call    cs:__imp_CloseHandle
0x180048531  test    rbx, rbx
0x180048534  jnz     short loc_1800485A6
0x180048536  mov     [rsi+2B0h], rbx
0x18004853d  call    cs:__imp_GetLastError
0x180048543  mov     edi, eax
0x180048545  test    eax, eax
0x180048547  jnz     short loc_180048550
0x180048549  mov     edi, 80004005h
0x18004854e  jmp     short loc_18004855B
0x180048550  jle     short loc_18004855B
0x180048552  movzx   edi, ax
0x180048555  or      edi, 80070000h
0x18004855b  mov     rax, [rsi+50h]
0x18004855f  lea     rcx, [rsi+50h]
0x180048563  mov     rax, [rax+10h]
0x180048567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004856c  test    rax, rax
0x18004856f  jz      short loc_1800485AD
0x180048571  mov     rax, [rsi+50h]
0x180048575  lea     rcx, [rsi+50h]
0x180048579  mov     rax, [rax+10h]
0x18004857d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048582  xor     ecx, ecx
0x180048584  test    edi, edi
0x180048586  jns     loc_180048377
0x18004858c  test    rax, rax
0x18004858f  jz      loc_180048377
0x180048595  mov     dword ptr [rsp+78h+lpThreadId], edi
0x180048599  mov     dword ptr [rsp+78h+dwCreationFlags], 1E8h
0x1800485a1  jmp     loc_180048351
0x1800485a6  mov     [rsi+2B0h], rbx
0x1800485ad  mov     ecx, edi
0x1800485af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800485b4  nop
0x1800485b5  mov     eax, [rsp+78h+var_38]
0x1800485b9  test    eax, eax
0x1800485bb  jz      short loc_1800485CE
0x1800485bd  mov     rcx, rbp; lpCriticalSection
0x1800485c0  call    cs:__imp_LeaveCriticalSection
0x1800485c6  mov     [rsp+78h+var_38], 0
0x1800485ce  mov     eax, edi
0x1800485d0  add     rsp, 58h
0x1800485d4  pop     rdi
0x1800485d5  pop     rsi
0x1800485d6  pop     rbp
0x1800485d7  pop     rbx
0x1800485d8  retn
```
