# CTokenActivation::CSmartCardDetector::Invoke(void)

- ea: `0x180039398`
- end: `0x1800396bd`
- name: `?Invoke@CSmartCardDetector@CTokenActivation@@QEAAJXZ`
- size: `805`
- prototype: `__int64 __fastcall(CTokenActivation::CSmartCardDetector *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003a240`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800376c0`
- `0x180038028`
- `0x180039398`
- `0x180039bf8`
- `0x180039cc0`
- `0x18003c52a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039468`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003967a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039468`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003967a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039669`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003968e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039669`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003968e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003947c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003947c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039571`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039571`
- `USER32!SendMessageW` at `0x1800395b4`
- `USER32!SendMessageW` at `0x1800395b4`
- `USER32!FindWindowW` at `0x180039596`
- `USER32!FindWindowW` at `0x180039596`
- `WinSCard!SCardGetStatusChangeW` at `0x1800394cf`
- `WinSCard!SCardGetStatusChangeW` at `0x18003951c`
- `WinSCard!SCardGetStatusChangeW` at `0x1800394cf`
- `WinSCard!SCardGetStatusChangeW` at `0x18003951c`
- `WinSCard!SCardFreeMemory` at `0x180039626`
- `WinSCard!SCardFreeMemory` at `0x180039626`
- `WinSCard!SCardEstablishContext` at `0x1800393d0`
- `WinSCard!SCardEstablishContext` at `0x1800393d0`
- `WinSCard!SCardReleaseContext` at `0x1800396a3`
- `WinSCard!SCardReleaseContext` at `0x1800396a3`
- `WinSCard!SCardListReadersW` at `0x1800393fe`
- `WinSCard!SCardListReadersW` at `0x1800393fe`

## pseudocode

```c
__int64 __fastcall CTokenActivation::CSmartCardDetector::Invoke(CTokenActivation::CSmartCardDetector *this)
{
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v1; // rbx
  int SmartCardCertificates; // eax
  unsigned int v4; // edi
  __int64 v5; // rcx
  signed int v6; // esi
  __int64 v7; // rdi
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // r8
  const WCHAR *v13; // rax
  __int64 v14; // rcx
  signed int v15; // edx
  __int64 v16; // r8
  __int64 v17; // rcx
  DWORD v18; // eax
  unsigned int v19; // eax
  unsigned __int64 v20; // rcx
  HWND WindowW; // rax
  CTokenActivation *v22; // rcx
  __int64 v23; // rdx
  void *v24; // rsi
  HANDLE v25; // rax
  HANDLE v26; // rax
  WCHAR mszReaders[4]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v29; // [rsp+28h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-10h]
  DWORD pcchReaders; // [rsp+78h] [rbp+38h] BYREF
  int v32; // [rsp+80h] [rbp+40h] BYREF
  SCARDCONTEXT phContext; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  phContext = 0;
  pcchReaders = 0;
  v29 = 0;
  lpMem = 0;
  v32 = 0;
  *(_QWORD *)mszReaders = 0;
  SmartCardCertificates = SCardEstablishContext(0, 0, 0, &phContext);
  v4 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
  pcchReaders = -1;
  v4 = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2146435026 )
    goto LABEL_37;
  if ( !*(_QWORD *)mszReaders )
  {
    v4 = 0;
    goto LABEL_41;
  }
  SmartCardCertificates = CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(
                            *(char **)mszReaders,
                            2 * pcchReaders,
                            (__int64)&v29,
                            &v32);
  v4 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
  v6 = HIDWORD(v29);
  v7 = SHIDWORD(v29);
  v8 = (__int64)SHIDWORD(v29) << 6;
  if ( !is_mul_ok(SHIDWORD(v29), 0x40u) )
    v8 = -1;
  ProcessHeap = GetProcessHeap();
  v10 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)HeapAlloc(ProcessHeap, 0, v8);
  v1 = v10;
  if ( !v10 )
  {
    v4 = -2147024882;
LABEL_37:
    v5 = v4;
    goto LABEL_38;
  }
  memset_0(v10, 0, v7 << 6);
  v11 = 0;
  if ( v6 > 0 )
  {
    v12 = lpMem;
    do
    {
      v13 = (const WCHAR *)v12[v11];
      v14 = (unsigned int)v11;
      v11 = (unsigned int)(v11 + 1);
      v1[v14].szReader = v13;
    }
    while ( (int)v11 < v6 );
  }
  SmartCardCertificates = SCardGetStatusChangeW(phContext, 0, v1, v6);
  v4 = SmartCardCertificates;
  if ( SmartCardCertificates < 0 )
    goto LABEL_2;
  v15 = 0;
  if ( v6 > 0 )
  {
    v16 = 0;
    do
    {
      ++v15;
      v17 = v16++ << 6;
      v18 = *(DWORD *)((char *)&v1->dwEventState + v17);
      *(DWORD *)((char *)&v1->dwCurrentState + v17) = v18;
      *(DWORD *)((char *)&v1->dwEventState + v17) = v18 & 0xFFFFFFCD | 0x22;
    }
    while ( v15 < v6 );
  }
  while ( 1 )
  {
    SmartCardCertificates = SCardGetStatusChangeW(phContext, 0, v1, v6);
    v4 = SmartCardCertificates;
    if ( SmartCardCertificates != -2146435062 )
    {
      if ( SmartCardCertificates )
      {
        if ( SmartCardCertificates < 0 )
          goto LABEL_2;
        goto LABEL_26;
      }
      v19 = 0;
      if ( v6 > 0 )
        break;
    }
LABEL_26:
    if ( WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 10) + 152LL) + 8LL), 0x3E8u) != 258 )
      goto LABEL_35;
  }
  while ( 1 )
  {
    v20 = (unsigned __int64)v19 << 6;
    if ( (*((_BYTE *)&v1->dwCurrentState + v20) & 0x10) != 0 && (*((_BYTE *)&v1->dwEventState + v20) & 0x20) != 0 )
      break;
    if ( (int)++v19 >= v6 )
      goto LABEL_26;
  }
  WindowW = FindWindowW(0, *(LPCWSTR *)(*((_QWORD *)this + 10) + 256LL));
  if ( WindowW )
    SendMessageW(WindowW, 0x10u, 0, 0);
  SmartCardCertificates = CTokenActivation::GetSmartCardCertificates(*((CTokenActivation **)this + 10));
  v4 = SmartCardCertificates;
  if ( SmartCardCertificates >= 0 )
  {
    v22 = (CTokenActivation *)*((_QWORD *)this + 10);
    v23 = *((_QWORD *)v22 + 28);
    if ( !v23
      || !*(_DWORD *)v23
      || (SmartCardCertificates = CTokenActivation::SetSelectedCert(v22, *(const struct _CERT_CONTEXT **)(v23 + 8)),
          v4 = SmartCardCertificates,
          SmartCardCertificates >= 0) )
    {
      *(_DWORD *)(*((_QWORD *)this + 10) + 248LL) = 1;
LABEL_35:
      v4 = 0;
      goto LABEL_39;
    }
  }
LABEL_2:
  v5 = (unsigned int)SmartCardCertificates;
LABEL_38:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_39:
  if ( *(_QWORD *)mszReaders )
  {
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
    *(_QWORD *)mszReaders = 0;
  }
LABEL_41:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize((__int64)&v29, 0);
  v24 = lpMem;
  if ( lpMem )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
  if ( v1 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v1);
  }
  if ( phContext )
    SCardReleaseContext(phContext);
  return v4;
}

```

## disassembly

```asm
0x180039398  push    rbp
0x18003939a  push    rbx
0x18003939b  push    rsi
0x18003939c  push    rdi
0x18003939d  push    r14
0x18003939f  mov     rbp, rsp
0x1800393a2  sub     rsp, 40h
0x1800393a6  xor     ebx, ebx
0x1800393a8  mov     [rbp+phContext], 0
0x1800393b0  mov     r14, rcx
0x1800393b3  mov     [rbp+pcchReaders], ebx
0x1800393b6  xor     ecx, ecx; dwScope
0x1800393b8  mov     [rbp+var_18], rbx
0x1800393bc  lea     r9, [rbp+phContext]; phContext
0x1800393c0  mov     [rbp+lpMem], rbx
0x1800393c4  xor     r8d, r8d; pvReserved2
0x1800393c7  mov     [rbp+arg_10], ebx
0x1800393ca  xor     edx, edx; pvReserved1
0x1800393cc  mov     qword ptr [rbp+mszReaders], rbx
0x1800393d0  call    cs:__imp_SCardEstablishContext
0x1800393d7  nop     dword ptr [rax+rax+00h]
0x1800393dc  mov     edi, eax
0x1800393de  test    eax, eax
0x1800393e0  jns     short loc_1800393E9
0x1800393e2  mov     ecx, eax
0x1800393e4  jmp     loc_180039614
0x1800393e9  mov     rcx, [rbp+phContext]; hContext
0x1800393ed  lea     r9, [rbp+pcchReaders]; pcchReaders
0x1800393f1  lea     r8, [rbp+mszReaders]; mszReaders
0x1800393f5  mov     [rbp+pcchReaders], 0FFFFFFFFh
0x1800393fc  xor     edx, edx; mszGroups
0x1800393fe  call    cs:__imp_SCardListReadersW
0x180039405  nop     dword ptr [rax+rax+00h]
0x18003940a  mov     ecx, 80000000h
0x18003940f  mov     edi, eax
0x180039411  add     eax, ecx
0x180039413  test    ecx, eax
0x180039415  jnz     short loc_180039423
0x180039417  cmp     edi, 8010002Eh
0x18003941d  jnz     loc_180039612
0x180039423  mov     rcx, qword ptr [rbp+mszReaders]; Src
0x180039427  test    rcx, rcx
0x18003942a  jnz     short loc_180039433
0x18003942c  xor     edi, edi
0x18003942e  jmp     loc_18003963A
0x180039433  mov     edx, [rbp+pcchReaders]
0x180039436  lea     r9, [rbp+arg_10]
0x18003943a  add     edx, edx
0x18003943c  lea     r8, [rbp+var_18]
0x180039440  call    ?Create@?$CRegType@V?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@@@SAJPEBXKPEAV?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@PEAH@Z; CRegType<CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>>::Create(void const *,ulong,CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault> *,int *)
0x180039445  mov     edi, eax
0x180039447  test    eax, eax
0x180039449  js      short loc_1800393E2
0x18003944b  movsxd  rsi, dword ptr [rbp+var_18+4]
0x18003944f  mov     eax, 40h ; '@'
0x180039454  mul     rsi
0x180039457  mov     rdi, rsi
0x18003945a  mov     rbx, rax
0x18003945d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180039464  cmovb   rbx, rax
0x180039468  call    cs:__imp_GetProcessHeap
0x18003946f  nop     dword ptr [rax+rax+00h]
0x180039474  mov     r8, rbx; dwBytes
0x180039477  xor     edx, edx; dwFlags
0x180039479  mov     rcx, rax; hHeap
0x18003947c  call    cs:__imp_HeapAlloc
0x180039483  nop     dword ptr [rax+rax+00h]
0x180039488  mov     rbx, rax
0x18003948b  test    rax, rax
0x18003948e  jz      loc_18003960D
0x180039494  shl     rdi, 6
0x180039498  xor     edx, edx; Val
0x18003949a  mov     r8, rdi; Size
0x18003949d  mov     rcx, rax; void *
0x1800394a0  call    memset_0
0x1800394a5  xor     edx, edx
0x1800394a7  test    esi, esi
0x1800394a9  jle     short loc_1800394C3
0x1800394ab  mov     r8, [rbp+lpMem]
0x1800394af  mov     rax, [r8+rdx*8]
0x1800394b3  mov     ecx, edx
0x1800394b5  inc     edx
0x1800394b7  shl     rcx, 6
0x1800394bb  mov     [rcx+rbx], rax
0x1800394bf  cmp     edx, esi
0x1800394c1  jl      short loc_1800394AF
0x1800394c3  mov     rcx, [rbp+phContext]; hContext
0x1800394c7  mov     r9d, esi; cReaders
0x1800394ca  mov     r8, rbx; rgReaderStates
0x1800394cd  xor     edx, edx; dwTimeout
0x1800394cf  call    cs:__imp_SCardGetStatusChangeW
0x1800394d6  nop     dword ptr [rax+rax+00h]
0x1800394db  mov     edi, eax
0x1800394dd  test    eax, eax
0x1800394df  js      loc_1800393E2
0x1800394e5  xor     edx, edx
0x1800394e7  test    esi, esi
0x1800394e9  jle     short loc_180039510
0x1800394eb  xor     r8d, r8d
0x1800394ee  mov     rcx, r8
0x1800394f1  inc     edx
0x1800394f3  shl     rcx, 6
0x1800394f7  inc     r8
0x1800394fa  mov     eax, [rcx+rbx+14h]
0x1800394fe  mov     [rcx+rbx+10h], eax
0x180039502  and     eax, 0FFFFFFEFh
0x180039505  or      eax, 22h
0x180039508  mov     [rcx+rbx+14h], eax
0x18003950c  cmp     edx, esi
0x18003950e  jl      short loc_1800394EE
0x180039510  mov     rcx, [rbp+phContext]; hContext
0x180039514  mov     r9d, esi; cReaders
0x180039517  mov     r8, rbx; rgReaderStates
0x18003951a  xor     edx, edx; dwTimeout
0x18003951c  call    cs:__imp_SCardGetStatusChangeW
0x180039523  nop     dword ptr [rax+rax+00h]
0x180039528  mov     edi, eax
0x18003952a  cmp     eax, 8010000Ah
0x18003952f  jz      short loc_18003955D
0x180039531  test    eax, eax
0x180039533  jz      short loc_18003953D
0x180039535  js      loc_1800393E2
0x18003953b  jmp     short loc_18003955D
0x18003953d  xor     eax, eax
0x18003953f  test    esi, esi
0x180039541  jle     short loc_18003955D
0x180039543  mov     ecx, eax
0x180039545  shl     rcx, 6
0x180039549  test    byte ptr [rcx+rbx+10h], 10h
0x18003954e  jz      short loc_180039557
0x180039550  test    byte ptr [rcx+rbx+14h], 20h
0x180039555  jnz     short loc_180039589
0x180039557  inc     eax
0x180039559  cmp     eax, esi
0x18003955b  jl      short loc_180039543
0x18003955d  mov     rax, [r14+50h]
0x180039561  mov     edx, 3E8h; dwMilliseconds
0x180039566  mov     rcx, [rax+98h]
0x18003956d  mov     rcx, [rcx+8]; hHandle
0x180039571  call    cs:__imp_WaitForSingleObject
0x180039578  nop     dword ptr [rax+rax+00h]
0x18003957d  cmp     eax, 102h
0x180039582  jz      short loc_180039510
0x180039584  jmp     loc_180039609
0x180039589  mov     rax, [r14+50h]
0x18003958d  xor     ecx, ecx; lpClassName
0x18003958f  mov     rdx, [rax+100h]; lpWindowName
0x180039596  call    cs:__imp_FindWindowW
0x18003959d  nop     dword ptr [rax+rax+00h]
0x1800395a2  test    rax, rax
0x1800395a5  jz      short loc_1800395C0
0x1800395a7  xor     r9d, r9d; lParam
0x1800395aa  xor     r8d, r8d; wParam
0x1800395ad  mov     rcx, rax; hWnd
0x1800395b0  lea     edx, [r9+10h]; Msg
0x1800395b4  call    cs:__imp_SendMessageW
0x1800395bb  nop     dword ptr [rax+rax+00h]
0x1800395c0  mov     rcx, [r14+50h]; this
0x1800395c4  call    ?GetSmartCardCertificates@CTokenActivation@@IEAAJXZ; CTokenActivation::GetSmartCardCertificates(void)
0x1800395c9  mov     edi, eax
0x1800395cb  test    eax, eax
0x1800395cd  js      loc_1800393E2
0x1800395d3  mov     rcx, [r14+50h]; this
0x1800395d7  mov     rdx, [rcx+0E0h]
0x1800395de  test    rdx, rdx
0x1800395e1  jz      short loc_1800395FB
0x1800395e3  cmp     dword ptr [rdx], 0
0x1800395e6  jz      short loc_1800395FB
0x1800395e8  mov     rdx, [rdx+8]; struct _CERT_CONTEXT *
0x1800395ec  call    ?SetSelectedCert@CTokenActivation@@IEAAJPEBU_CERT_CONTEXT@@@Z; CTokenActivation::SetSelectedCert(_CERT_CONTEXT const *)
0x1800395f1  mov     edi, eax
0x1800395f3  test    eax, eax
0x1800395f5  js      loc_1800393E2
0x1800395fb  mov     rax, [r14+50h]
0x1800395ff  mov     dword ptr [rax+0F8h], 1
0x180039609  xor     edi, edi
0x18003960b  jmp     short loc_180039619
0x18003960d  mov     edi, 8007000Eh
0x180039612  mov     ecx, edi
0x180039614  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039619  mov     rdx, qword ptr [rbp+mszReaders]; pvMem
0x18003961d  test    rdx, rdx
0x180039620  jz      short loc_18003963A
0x180039622  mov     rcx, [rbp+phContext]; hContext
0x180039626  call    cs:__imp_SCardFreeMemory
0x18003962d  nop     dword ptr [rax+rax+00h]
0x180039632  mov     qword ptr [rbp+mszReaders], 0
0x18003963a  mov     ecx, edi
0x18003963c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039641  xor     edx, edx
0x180039643  lea     rcx, [rbp+var_18]
0x180039647  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18003964c  mov     rsi, [rbp+lpMem]
0x180039650  test    rsi, rsi
0x180039653  jz      short loc_180039675
0x180039655  call    cs:__imp_GetProcessHeap
0x18003965c  nop     dword ptr [rax+rax+00h]
0x180039661  mov     r8, rsi; lpMem
0x180039664  xor     edx, edx; dwFlags
0x180039666  mov     rcx, rax; hHeap
0x180039669  call    cs:__imp_HeapFree
0x180039670  nop     dword ptr [rax+rax+00h]
0x180039675  test    rbx, rbx
0x180039678  jz      short loc_18003969A
0x18003967a  call    cs:__imp_GetProcessHeap
0x180039681  nop     dword ptr [rax+rax+00h]
0x180039686  mov     r8, rbx; lpMem
0x180039689  xor     edx, edx; dwFlags
0x18003968b  mov     rcx, rax; hHeap
0x18003968e  call    cs:__imp_HeapFree
0x180039695  nop     dword ptr [rax+rax+00h]
0x18003969a  mov     rcx, [rbp+phContext]; hContext
0x18003969e  test    rcx, rcx
0x1800396a1  jz      short loc_1800396AF
0x1800396a3  call    cs:__imp_SCardReleaseContext
0x1800396aa  nop     dword ptr [rax+rax+00h]
0x1800396af  mov     eax, edi
0x1800396b1  add     rsp, 40h
0x1800396b5  pop     r14
0x1800396b7  pop     rdi
0x1800396b8  pop     rsi
0x1800396b9  pop     rbx
0x1800396ba  pop     rbp
0x1800396bb  retn
```
