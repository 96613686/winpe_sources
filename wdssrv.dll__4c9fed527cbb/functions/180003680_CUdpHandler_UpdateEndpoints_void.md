# CUdpHandler::UpdateEndpoints(void)

- ea: `0x180003680`
- end: `0x18000393d`
- name: `?UpdateEndpoints@CUdpHandler@@QEAAKXZ`
- size: `701`
- prototype: `unsigned int __fastcall(CUdpHandler *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002aa0`
- `0x18000ac40`
- `0x18000cc30`

## callees

- `0x180001984`
- `0x180002358`
- `0x1800023c0`
- `0x1800028d0`
- `0x180002c24`
- `0x180003680`
- `0x180003944`
- `0x180015144`
- `0x18001a474`
- `0x18001c11e`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003700`
- `KERNEL32!LeaveCriticalSection` at `0x180003830`
- `KERNEL32!LeaveCriticalSection` at `0x180003700`
- `KERNEL32!LeaveCriticalSection` at `0x180003830`
- `KERNEL32!EnterCriticalSection` at `0x1800036d8`
- `KERNEL32!EnterCriticalSection` at `0x1800036ee`
- `KERNEL32!EnterCriticalSection` at `0x1800036d8`
- `KERNEL32!EnterCriticalSection` at `0x1800036ee`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800037b0`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800037b0`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800037d5`
- `WdsServerCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x1800037d5`

## pseudocode

```c
__int64 __fastcall CUdpHandler::UpdateEndpoints(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE *p_LockSemaphore; // r14
  unsigned int v2; // esi
  CUdpHandler *v3; // r15
  HANDLE v4; // rbx
  _QWORD *v5; // r14
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  void *v8; // r12
  _QWORD *v9; // rdi
  __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rax
  void *v14; // rax
  void *v15; // r13
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // r14d
  struct CRegUdpEndpoint *v19; // rdi
  struct _RTL_CRITICAL_SECTION *v20; // rdx
  CUdpEndpoint *v21; // rdi
  HANDLE *v23; // [rsp+20h] [rbp-40h] BYREF
  int v24; // [rsp+28h] [rbp-38h]
  void *Src; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+38h] [rbp-28h]
  __int128 v27; // [rsp+48h] [rbp-18h] BYREF
  int v28; // [rsp+5Ch] [rbp-4h]
  CUdpHandler *v29; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+48h]

  v29 = (CUdpHandler *)this;
  p_LockSemaphore = &this->LockSemaphore;
  v2 = 0;
  v23 = &this->LockSemaphore;
  v24 = 0;
  Src = 0;
  v3 = (CUdpHandler *)this;
  v26 = 0;
  if ( _InterlockedExchangeAdd((_DWORD *)&qword_180039280 + 1, 0) )
  {
    v2 = 31;
    goto LABEL_35;
  }
  EnterCriticalSection(this + 1);
  v24 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
  v4 = *p_LockSemaphore;
  LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
  if ( v4 )
  {
    v5 = *p_LockSemaphore;
    if ( v5 )
    {
      v6 = HIDWORD(v26);
      v7 = v26;
      v8 = Src;
      while ( 1 )
      {
        v9 = v5;
        v5 = (_QWORD *)v5[260];
        (*(void (__fastcall **)(_QWORD *))*v9)(v9);
        v2 = 0;
        if ( v6 == v7 )
        {
          v11 = v7 >> 1;
          if ( v7 >> 1 < 0x20 )
            v11 = 32;
          v12 = v7 + v11;
          if ( (unsigned int)v12 < v7 )
          {
            v2 = WIN32_FROM_HRESULT(-2147024362);
            if ( v2 )
              goto LABEL_17;
          }
          else
          {
            v30 = v7 + v11;
            v13 = 8 * v12;
            if ( !is_mul_ok(v12, 8u) )
              v13 = -1;
            v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
            v15 = v14;
            if ( !v14 )
            {
              v2 = 8;
              goto LABEL_17;
            }
            memmove_0(v14, v8, 8LL * v7);
            WdsPrivateHpFree(v8);
            v7 = v30;
            v8 = v15;
            Src = v15;
            LODWORD(v26) = v30;
          }
        }
        v16 = v6++;
        HIDWORD(v26) = v6;
        *((_QWORD *)v8 + v16) = v9;
LABEL_17:
        if ( (unsigned int)ElValidateWin32(v2, v10, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 688) )
        {
LABEL_33:
          if ( v9 )
            (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
          goto LABEL_35;
        }
        if ( !v5 )
        {
          v3 = v29;
          goto LABEL_21;
        }
      }
    }
  }
  v6 = HIDWORD(v26);
  v8 = Src;
LABEL_21:
  v24 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v23 + 2));
  v18 = 0;
  if ( v6 )
  {
    while ( 1 )
    {
      v19 = 0;
      v2 = 0;
      if ( v18 < v6 )
        v19 = (struct CRegUdpEndpoint *)*((_QWORD *)v8 + v18);
      else
        v2 = 1413;
      if ( (unsigned int)ElValidateWin32(v2, v17, "base\\eco\\wds\\wdssrv\\server\\src\\udphandler.cpp", 704) )
        break;
      CUdpHandler::QueryOpenUdpEndpoints(v3, v19);
      v20 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v3 + 11);
      v28 = 0;
      v27 = 0;
      CRegUdpEndpoint::QueryCloseAll((struct _RTL_CRITICAL_SECTION *)v19, v20, (__int64)&v27);
      if ( (_QWORD)v27 )
      {
        v29 = (CUdpHandler *)v27;
        do
        {
          v21 = (CUdpEndpoint *)CList<CUdpEndpoint,CNoLock>::DeleteAt(&v27, &v29);
          CUdpEndpoint::Shutdown(v21);
          if ( v21 )
            (*(void (__fastcall **)(CUdpEndpoint *))(*(_QWORD *)v21 + 8LL))(v21);
        }
        while ( v29 );
      }
      else
      {
        v29 = 0;
      }
      ++v18;
      v9 = 0;
      if ( v18 >= v6 )
        goto LABEL_33;
    }
  }
LABEL_35:
  CDynArray<CProviderEntry *,CDeallocateRelease>::Clear(&Src);
  CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(&v23);
  return v2;
}

```

## disassembly

```asm
0x180003680  mov     [rsp-38h+arg_10], rbx
0x180003685  mov     [rsp-38h+arg_0], rcx
0x18000368a  push    rbp
0x18000368b  push    rsi
0x18000368c  push    rdi
0x18000368d  push    r12
0x18000368f  push    r13
0x180003691  push    r14
0x180003693  push    r15
0x180003695  mov     rbp, rsp
0x180003698  sub     rsp, 60h
0x18000369c  xor     r13d, r13d
0x18000369f  lea     r14, [rcx+18h]
0x1800036a3  mov     esi, r13d
0x1800036a6  mov     [rbp+var_40], r14
0x1800036aa  mov     [rbp+var_38], r13d
0x1800036ae  mov     eax, r13d
0x1800036b1  mov     [rbp+Src], r13
0x1800036b5  mov     r15, rcx
0x1800036b8  mov     [rbp+var_28], r13
0x1800036bc  lock xadd dword ptr cs:qword_180039280+4, eax
0x1800036c4  test    eax, eax
0x1800036c6  jz      short loc_1800036D1
0x1800036c8  lea     esi, [r13+1Fh]
0x1800036cc  jmp     loc_180003910
0x1800036d1  lea     rdi, [r14+10h]
0x1800036d5  mov     rcx, rdi; lpCriticalSection
0x1800036d8  call    cs:__imp_EnterCriticalSection
0x1800036df  nop     dword ptr [rax+rax+00h]
0x1800036e4  mov     rcx, rdi; lpCriticalSection
0x1800036e7  mov     [rbp+var_38], 1
0x1800036ee  call    cs:__imp_EnterCriticalSection
0x1800036f5  nop     dword ptr [rax+rax+00h]
0x1800036fa  mov     rbx, [r14]
0x1800036fd  mov     rcx, rdi; lpCriticalSection
0x180003700  call    cs:__imp_LeaveCriticalSection
0x180003707  nop     dword ptr [rax+rax+00h]
0x18000370c  test    rbx, rbx
0x18000370f  jz      loc_18000381D
0x180003715  mov     r14, [r14]
0x180003718  test    r14, r14
0x18000371b  jz      loc_18000381D
0x180003721  mov     ebx, dword ptr [rbp+var_28+4]
0x180003724  mov     r15d, dword ptr [rbp+var_28]
0x180003728  mov     r12, [rbp+Src]
0x18000372c  mov     rdi, r14
0x18000372f  mov     r14, [r14+820h]
0x180003736  mov     rcx, rdi
0x180003739  mov     rax, [rdi]
0x18000373c  mov     rax, [rax]
0x18000373f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003744  mov     esi, r13d
0x180003747  cmp     ebx, r15d
0x18000374a  jnz     loc_1800037E7
0x180003750  mov     ecx, 20h ; ' '
0x180003755  mov     eax, r15d
0x180003758  shr     eax, 1
0x18000375a  cmp     eax, ecx
0x18000375c  cmovb   eax, ecx
0x18000375f  lea     ecx, [r15+rax]
0x180003763  cmp     ecx, r15d
0x180003766  jb      short loc_1800037D0
0x180003768  mov     [rbp+arg_8], rcx
0x18000376c  mov     eax, 8
0x180003771  mul     rcx
0x180003774  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000377b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003782  cmovo   rax, rcx
0x180003786  mov     rcx, rax; unsigned __int64
0x180003789  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000378e  mov     r13, rax
0x180003791  test    rax, rax
0x180003794  jnz     short loc_18000379B
0x180003796  lea     esi, [rax+8]
0x180003799  jmp     short loc_1800037F2
0x18000379b  mov     r8d, r15d
0x18000379e  mov     rdx, r12; Src
0x1800037a1  shl     r8, 3; Size
0x1800037a5  mov     rcx, r13; void *
0x1800037a8  call    memmove_0
0x1800037ad  mov     rcx, r12
0x1800037b0  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800037b7  nop     dword ptr [rax+rax+00h]
0x1800037bc  mov     r15d, dword ptr [rbp+arg_8]
0x1800037c0  mov     r12, r13
0x1800037c3  mov     [rbp+Src], r13
0x1800037c7  xor     r13d, r13d
0x1800037ca  mov     dword ptr [rbp+var_28], r15d
0x1800037ce  jmp     short loc_1800037E7
0x1800037d0  mov     ecx, 80070216h
0x1800037d5  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800037dc  nop     dword ptr [rax+rax+00h]
0x1800037e1  mov     esi, eax
0x1800037e3  test    eax, eax
0x1800037e5  jnz     short loc_1800037F2
0x1800037e7  mov     eax, ebx
0x1800037e9  inc     ebx
0x1800037eb  mov     dword ptr [rbp+var_28+4], ebx
0x1800037ee  mov     [r12+rax*8], rdi
0x1800037f2  mov     r9d, 2B0h
0x1800037f8  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x1800037ff  mov     ecx, esi
0x180003801  call    ElValidateWin32
0x180003806  test    eax, eax
0x180003808  jnz     loc_1800038FC
0x18000380e  test    r14, r14
0x180003811  jnz     loc_18000372C
0x180003817  mov     r15, [rbp+arg_0]
0x18000381b  jmp     short loc_180003824
0x18000381d  mov     ebx, dword ptr [rbp+var_28+4]
0x180003820  mov     r12, [rbp+Src]
0x180003824  mov     rcx, [rbp+var_40]
0x180003828  add     rcx, 10h; lpCriticalSection
0x18000382c  mov     [rbp+var_38], r13d
0x180003830  call    cs:__imp_LeaveCriticalSection
0x180003837  nop     dword ptr [rax+rax+00h]
0x18000383c  mov     r14d, r13d
0x18000383f  test    ebx, ebx
0x180003841  jz      loc_180003910
0x180003847  mov     rdi, r13
0x18000384a  mov     esi, r13d
0x18000384d  cmp     r14d, ebx
0x180003850  jb      short loc_180003859
0x180003852  mov     esi, 585h
0x180003857  jmp     short loc_180003860
0x180003859  mov     eax, r14d
0x18000385c  mov     rdi, [r12+rax*8]
0x180003860  mov     r9d, 2C0h
0x180003866  lea     r8, aBaseEcoWdsWdss_8; "base\\eco\\wds\\wdssrv\\server\\src\\ud"...
0x18000386d  mov     ecx, esi
0x18000386f  call    ElValidateWin32
0x180003874  test    eax, eax
0x180003876  jnz     loc_180003910
0x18000387c  mov     rdx, rdi; struct CRegUdpEndpoint *
0x18000387f  mov     rcx, r15; this
0x180003882  call    ?QueryOpenUdpEndpoints@CUdpHandler@@AEAAKPEAVCRegUdpEndpoint@@@Z; CUdpHandler::QueryOpenUdpEndpoints(CRegUdpEndpoint *)
0x180003887  mov     rdx, [r15+58h]
0x18000388b  lea     r8, [rbp+var_18]
0x18000388f  xorps   xmm0, xmm0
0x180003892  mov     [rbp+var_4], r13d
0x180003896  mov     rcx, rdi
0x180003899  movdqu  [rbp+var_18], xmm0
0x18000389e  call    ?QueryCloseAll@CRegUdpEndpoint@@QEAAXPEAVCInterfaceMonitor@@PEAV?$CList@VCUdpEndpoint@@VCNoLock@@@@@Z; CRegUdpEndpoint::QueryCloseAll(CInterfaceMonitor *,CList<CUdpEndpoint,CNoLock> *)
0x1800038a3  mov     rax, qword ptr [rbp+var_18]
0x1800038a7  test    rax, rax
0x1800038aa  jnz     short loc_1800038B2
0x1800038ac  mov     [rbp+arg_0], r13
0x1800038b0  jmp     short loc_1800038ED
0x1800038b2  mov     [rbp+arg_0], rax
0x1800038b6  test    rax, rax
0x1800038b9  jz      short loc_1800038ED
0x1800038bb  lea     rdx, [rbp+arg_0]
0x1800038bf  lea     rcx, [rbp+var_18]
0x1800038c3  call    ?DeleteAt@?$CList@VCUdpEndpoint@@VCNoLock@@@@QEAAPEAVCUdpEndpoint@@AEAPEAX@Z; CList<CUdpEndpoint,CNoLock>::DeleteAt(void * &)
0x1800038c8  mov     rcx, rax; this
0x1800038cb  mov     rdi, rax
0x1800038ce  call    ?Shutdown@CUdpEndpoint@@QEAAKXZ; CUdpEndpoint::Shutdown(void)
0x1800038d3  test    rdi, rdi
0x1800038d6  jz      short loc_1800038E7
0x1800038d8  mov     rax, [rdi]
0x1800038db  mov     rcx, rdi
0x1800038de  mov     rax, [rax+8]
0x1800038e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e7  cmp     [rbp+arg_0], r13
0x1800038eb  jnz     short loc_1800038BB
0x1800038ed  inc     r14d
0x1800038f0  mov     rdi, r13
0x1800038f3  cmp     r14d, ebx
0x1800038f6  jb      loc_180003847
0x1800038fc  test    rdi, rdi
0x1800038ff  jz      short loc_180003910
0x180003901  mov     rdx, [rdi]
0x180003904  mov     rcx, rdi
0x180003907  mov     rax, [rdx+8]
0x18000390b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003910  lea     rcx, [rbp+Src]
0x180003914  call    ?Clear@?$CDynArray@PEAUCProviderEntry@@VCDeallocateRelease@@@@QEAAXXZ; CDynArray<CProviderEntry *,CDeallocateRelease>::Clear(void)
0x180003919  lea     rcx, [rbp+var_40]
0x18000391d  call    ??1?$CAutoTypeLock@V?$CList@VCRegUdpEndpoint@@VCCriticalSection@@@@@@QEAA@XZ; CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>::~CAutoTypeLock<CList<CRegUdpEndpoint,CCriticalSection>>(void)
0x180003922  mov     rbx, [rsp+60h+arg_10]
0x18000392a  mov     eax, esi
0x18000392c  add     rsp, 60h
0x180003930  pop     r15
0x180003932  pop     r14
0x180003934  pop     r13
0x180003936  pop     r12
0x180003938  pop     rdi
0x180003939  pop     rsi
0x18000393a  pop     rbp
0x18000393b  retn
```
