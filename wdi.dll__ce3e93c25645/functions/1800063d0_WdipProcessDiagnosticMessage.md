# WdipProcessDiagnosticMessage

- ea: `0x1800063d0`
- end: `0x1800067b5`
- name: `WdipProcessDiagnosticMessage`
- size: `997`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800067c0`

## callees

- `0x180001010`
- `0x180001080`
- `0x1800011d0`
- `0x180002ba0`
- `0x180003f40`
- `0x1800063d0`
- `0x180006f10`
- `0x1800079a0`
- `0x180007b00`
- `0x18000f1c2`
- `0x18000f1f0`
- `0x180010010`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x1800064e9`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x1800064e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800066bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800065b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800066bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006530`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800066a2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006530`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800066a2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800065a5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000669c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800065a5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000669c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006447`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006447`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006488`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006570`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006411`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000645b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000649c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006411`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000645b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000649c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000657e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000657e`

## pseudocode

```c
__int64 __fastcall WdipProcessDiagnosticMessage(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  void *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  HANDLE v8; // rax
  _OWORD *v9; // rax
  HANDLE v10; // rax
  _OWORD *v11; // rax
  __int64 v12; // rax
  int Args; // eax
  HANDLE v14; // rax
  bool v15; // zf
  unsigned int v16; // esi
  __int64 v17; // rax
  int v19; // [rsp+30h] [rbp-48h] BYREF
  GUID ActivityId; // [rsp+38h] [rbp-40h] BYREF

  ActivityId = 0;
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0x1B0u);
  v6 = (__int64)v5;
  if ( !v5 )
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
      (int)L"WdipProcessDiagnosticMessage",
      103,
      (int)L"Error = %d",
      14);
    goto LABEL_12;
  }
  memset_0(v5, 0, 0x1B0u);
  v8 = GetProcessHeap();
  v9 = HeapAlloc(v8, 8u, 0x10u);
  *(_QWORD *)(v6 + 24) = v9;
  if ( !v9 )
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
      (int)L"WdipProcessDiagnosticMessage",
      111,
      (int)L"Error = %d",
      14);
    goto LABEL_12;
  }
  *v9 = 0;
  v10 = GetProcessHeap();
  v11 = HeapAlloc(v10, 8u, 0x10u);
  *(_QWORD *)(v6 + 32) = v11;
  if ( !v11 )
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
      (int)L"WdipProcessDiagnosticMessage",
      116,
      (int)L"Error = %d",
      14);
    goto LABEL_12;
  }
  v7 = 0;
  *v11 = 0;
  *(_QWORD *)(v6 + 48) = a1;
  *(_QWORD *)(v6 + 40) = a2;
  if ( a2 != -80 )
    *(_OWORD *)v6 = *(_OWORD *)(a2 + 80);
  if ( *(_DWORD *)(a2 + 44) != 3 )
  {
    v12 = AlpcMaxAllowedMessageLength();
    Args = WdipReadParameterCollectionFromMessageBuffer(*(_QWORD *)(v6 + 24), *(_QWORD *)(v6 + 40), v12);
    v7 = Args;
    if ( Args < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\sessions.cpp",
        (int)L"WdipProcessDiagnosticMessage",
        141,
        (int)L"Error = %d",
        Args);
LABEL_12:
      RevertToSelf();
      *(_DWORD *)(a2 + 112) = v7;
      WdipDiagnosticResponse(a1, v6, a2);
      if ( v6 )
      {
        if ( *(_QWORD *)(v6 + 32) )
          WdipDeleteParameterCollection((_QWORD *)(v6 + 32));
        if ( *(_QWORD *)(v6 + 24) )
          WdipDeleteParameterCollection((_QWORD *)(v6 + 24));
        v14 = GetProcessHeap();
        HeapFree(v14, 0, (LPVOID)v6);
      }
      return v7;
    }
  }
  if ( *(_QWORD *)(v6 + 40) != -64 )
    ActivityId = *(GUID *)(*(_QWORD *)(v6 + 40) + 64LL);
  EventActivityIdControl(4u, &ActivityId);
  ++*(_DWORD *)(v6 + 56);
  EnterCriticalSection(&g_csWDI);
  *(_QWORD *)(v6 + 64) = g_pWdiInstanceHead;
  g_pWdiInstanceHead = (LPVOID)v6;
  LeaveCriticalSection(&g_csWDI);
  switch ( *(_DWORD *)(*(_QWORD *)(v6 + 40) + 44LL) )
  {
    case 3:
      v15 = (*(_BYTE *)(a1 + 80) & 0x10) == 0;
      v16 = 255;
      v19 = 255;
      if ( v15 )
      {
        WdipLowerPagePriorityThread(&v19);
        v16 = v19;
      }
      *(_DWORD *)(*(_QWORD *)(v6 + 40) + 112LL) = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 40))(v6, 2);
      if ( (*(_BYTE *)(a1 + 80) & 0x10) == 0 )
        WdipRevertPagePriorityThread(v16);
      v17 = *(_QWORD *)(v6 + 40);
      if ( *(_DWORD *)(v17 + 44) != 1 )
        *(_DWORD *)(v17 + 44) = 2;
      *(_DWORD *)(*(_QWORD *)(v6 + 40) + 124LL) = 208;
      break;
    case 4:
      WdipHandleInstance(3u, a1, v6);
      break;
    case 8:
      WdipHandleInstance(4u, a1, v6);
      break;
    case 0x1E:
      WdipHandleInstance(5u, a1, v6);
      break;
  }
  EventActivityIdControl(2u, &ActivityId);
  RevertToSelf();
  WdipDiagnosticResponse(a1, v6, a2);
  EnterCriticalSection(&g_csWDI);
  *(_QWORD *)(v6 + 40) = v6 + 184;
  *(_OWORD *)(v6 + 184) = *(_OWORD *)a2;
  *(_OWORD *)(v6 + 200) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(v6 + 216) = *(_OWORD *)(a2 + 32);
  *(_OWORD *)(v6 + 232) = *(_OWORD *)(a2 + 48);
  *(_OWORD *)(v6 + 248) = *(_OWORD *)(a2 + 64);
  *(_OWORD *)(v6 + 264) = *(_OWORD *)(a2 + 80);
  *(_OWORD *)(v6 + 280) = *(_OWORD *)(a2 + 96);
  *(_OWORD *)(v6 + 296) = *(_OWORD *)(a2 + 112);
  *(_OWORD *)(v6 + 312) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(v6 + 328) = *(_OWORD *)(a2 + 144);
  *(_OWORD *)(v6 + 344) = *(_OWORD *)(a2 + 160);
  *(_OWORD *)(v6 + 360) = *(_OWORD *)(a2 + 176);
  *(_OWORD *)(v6 + 376) = *(_OWORD *)(a2 + 192);
  *(_OWORD *)(v6 + 392) = *(_OWORD *)(a2 + 208);
  *(_OWORD *)(v6 + 408) = *(_OWORD *)(a2 + 224);
  *(_QWORD *)(v6 + 424) = *(_QWORD *)(a2 + 240);
  WdipReleaseInstance((LPVOID)v6);
  LeaveCriticalSection(&g_csWDI);
  return v7;
}

```

## disassembly

```asm
0x1800063d0  mov     [rsp+arg_10], rbx
0x1800063d5  push    rbp
0x1800063d6  push    rsi
0x1800063d7  push    rdi
0x1800063d8  push    r14
0x1800063da  push    r15
0x1800063dc  sub     rsp, 50h
0x1800063e0  mov     rax, cs:__security_cookie
0x1800063e7  xor     rax, rsp
0x1800063ea  mov     [rsp+78h+var_30], rax
0x1800063ef  xorps   xmm0, xmm0
0x1800063f2  mov     rbp, rdx
0x1800063f5  movups  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x1800063fa  mov     r14, rcx
0x1800063fd  call    cs:__imp_GetProcessHeap
0x180006403  mov     edx, 8; dwFlags
0x180006408  mov     r8d, 1B0h; dwBytes
0x18000640e  mov     rcx, rax; hHeap
0x180006411  call    cs:__imp_HeapAlloc
0x180006417  mov     rbx, rax
0x18000641a  test    rax, rax
0x18000641d  jnz     short loc_180006437
0x18000641f  mov     edi, 8007000Eh
0x180006424  mov     dword ptr [rsp+78h+Args], 0Eh
0x18000642c  mov     r8d, 67h ; 'g'
0x180006432  jmp     loc_180006516
0x180006437  xor     edx, edx; Val
0x180006439  mov     r8d, 1B0h; Size
0x18000643f  mov     rcx, rbx; void *
0x180006442  call    memset_0
0x180006447  call    cs:__imp_GetProcessHeap
0x18000644d  mov     edx, 8; dwFlags
0x180006452  mov     r8d, 10h; dwBytes
0x180006458  mov     rcx, rax; hHeap
0x18000645b  call    cs:__imp_HeapAlloc
0x180006461  mov     [rbx+18h], rax
0x180006465  test    rax, rax
0x180006468  jnz     short loc_180006482
0x18000646a  mov     edi, 8007000Eh
0x18000646f  mov     dword ptr [rsp+78h+Args], 0Eh
0x180006477  mov     r8d, 6Fh ; 'o'
0x18000647d  jmp     loc_180006516
0x180006482  xorps   xmm0, xmm0
0x180006485  movups  xmmword ptr [rax], xmm0
0x180006488  call    cs:__imp_GetProcessHeap
0x18000648e  mov     edx, 8; dwFlags
0x180006493  mov     r8d, 10h; dwBytes
0x180006499  mov     rcx, rax; hHeap
0x18000649c  call    cs:__imp_HeapAlloc
0x1800064a2  mov     [rbx+20h], rax
0x1800064a6  test    rax, rax
0x1800064a9  jnz     short loc_1800064C0
0x1800064ab  mov     edi, 8007000Eh
0x1800064b0  mov     dword ptr [rsp+78h+Args], 0Eh
0x1800064b8  mov     r8d, 74h ; 't'
0x1800064be  jmp     short loc_180006516
0x1800064c0  xorps   xmm0, xmm0
0x1800064c3  xor     edi, edi
0x1800064c5  movups  xmmword ptr [rax], xmm0
0x1800064c8  lea     rax, [rbp+50h]
0x1800064cc  mov     [rbx+30h], r14
0x1800064d0  mov     [rbx+28h], rbp
0x1800064d4  test    rax, rax
0x1800064d7  jz      short loc_1800064DF
0x1800064d9  movups  xmm0, xmmword ptr [rax]
0x1800064dc  movups  xmmword ptr [rbx], xmm0
0x1800064df  cmp     dword ptr [rbp+2Ch], 3
0x1800064e3  jz      loc_180006589
0x1800064e9  call    cs:__imp_AlpcMaxAllowedMessageLength
0x1800064ef  mov     rdx, [rbx+28h]
0x1800064f3  mov     r8, rax
0x1800064f6  mov     rcx, [rbx+18h]
0x1800064fa  call    WdipReadParameterCollectionFromMessageBuffer
0x1800064ff  mov     edi, eax
0x180006501  test    eax, eax
0x180006503  jns     loc_180006589
0x180006509  movzx   ecx, ax
0x18000650c  mov     r8d, 8Dh; int
0x180006512  mov     dword ptr [rsp+78h+Args], ecx; Args
0x180006516  lea     r9, aErrorD_0; "Error = %d"
0x18000651d  lea     rdx, aWdipprocessdia; "WdipProcessDiagnosticMessage"
0x180006524  lea     rcx, aClientcoreBase_3; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000652b  call    WdipTraceError
0x180006530  call    cs:__imp_RevertToSelf
0x180006536  mov     r8, rbp
0x180006539  mov     [rbp+70h], edi
0x18000653c  mov     rdx, rbx
0x18000653f  mov     rcx, r14
0x180006542  call    WdipDiagnosticResponse
0x180006547  test    rbx, rbx
0x18000654a  jz      loc_180006792
0x180006550  cmp     qword ptr [rbx+20h], 0
0x180006555  lea     rcx, [rbx+20h]
0x180006559  jz      short loc_180006560
0x18000655b  call    WdipDeleteParameterCollection
0x180006560  cmp     qword ptr [rbx+18h], 0
0x180006565  jz      short loc_180006570
0x180006567  lea     rcx, [rbx+18h]
0x18000656b  call    WdipDeleteParameterCollection
0x180006570  call    cs:__imp_GetProcessHeap
0x180006576  mov     r8, rbx; lpMem
0x180006579  xor     edx, edx; dwFlags
0x18000657b  mov     rcx, rax; hHeap
0x18000657e  call    cs:__imp_HeapFree
0x180006584  jmp     loc_180006792
0x180006589  mov     rax, [rbx+28h]
0x18000658d  add     rax, 40h ; '@'
0x180006591  jz      short loc_18000659B
0x180006593  movups  xmm0, xmmword ptr [rax]
0x180006596  movups  xmmword ptr [rsp+78h+ActivityId.Data1], xmm0
0x18000659b  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x1800065a0  mov     ecx, 4; ControlCode
0x1800065a5  call    cs:__imp_EventActivityIdControl
0x1800065ab  inc     dword ptr [rbx+38h]
0x1800065ae  lea     rcx, g_csWDI; lpCriticalSection
0x1800065b5  call    cs:__imp_EnterCriticalSection
0x1800065bb  mov     rax, cs:g_pWdiInstanceHead
0x1800065c2  lea     rcx, g_csWDI; lpCriticalSection
0x1800065c9  mov     [rbx+40h], rax
0x1800065cd  mov     cs:g_pWdiInstanceHead, rbx
0x1800065d4  call    cs:__imp_LeaveCriticalSection
0x1800065da  mov     rcx, [rbx+28h]
0x1800065de  mov     edx, [rcx+2Ch]
0x1800065e1  sub     edx, 3
0x1800065e4  jz      short loc_180006632
0x1800065e6  sub     edx, 1
0x1800065e9  jz      short loc_180006620
0x1800065eb  sub     edx, 4
0x1800065ee  jz      short loc_18000660E
0x1800065f0  cmp     edx, 16h
0x1800065f3  jnz     loc_180006692
0x1800065f9  mov     r8, rbx
0x1800065fc  mov     rdx, r14
0x1800065ff  mov     ecx, 5
0x180006604  call    WdipHandleInstance
0x180006609  jmp     loc_180006692
0x18000660e  mov     r8, rbx
0x180006611  mov     rdx, r14
0x180006614  mov     ecx, 4
0x180006619  call    WdipHandleInstance
0x18000661e  jmp     short loc_180006692
0x180006620  mov     r8, rbx
0x180006623  mov     rdx, r14
0x180006626  mov     ecx, 3
0x18000662b  call    WdipHandleInstance
0x180006630  jmp     short loc_180006692
0x180006632  test    byte ptr [r14+50h], 10h
0x180006637  mov     esi, 0FFh
0x18000663c  mov     [rsp+78h+var_48], esi
0x180006640  jnz     short loc_180006650
0x180006642  lea     rcx, [rsp+78h+var_48]
0x180006647  call    WdipLowerPagePriorityThread
0x18000664c  mov     esi, [rsp+78h+var_48]
0x180006650  mov     rax, [r14+28h]
0x180006654  mov     edx, 2
0x180006659  mov     rcx, rbx
0x18000665c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006661  mov     rdx, [rbx+28h]
0x180006665  mov     [rdx+70h], eax
0x180006668  test    byte ptr [r14+50h], 10h
0x18000666d  jnz     short loc_180006676
0x18000666f  mov     ecx, esi
0x180006671  call    WdipRevertPagePriorityThread
0x180006676  mov     rax, [rbx+28h]
0x18000667a  cmp     dword ptr [rax+2Ch], 1
0x18000667e  jz      short loc_180006687
0x180006680  mov     dword ptr [rax+2Ch], 2
0x180006687  mov     rax, [rbx+28h]
0x18000668b  mov     dword ptr [rax+7Ch], 0D0h
0x180006692  lea     rdx, [rsp+78h+ActivityId]; ActivityId
0x180006697  mov     ecx, 2; ControlCode
0x18000669c  call    cs:__imp_EventActivityIdControl
0x1800066a2  call    cs:__imp_RevertToSelf
0x1800066a8  mov     r8, rbp
0x1800066ab  mov     rdx, rbx
0x1800066ae  mov     rcx, r14
0x1800066b1  call    WdipDiagnosticResponse
0x1800066b6  lea     rcx, g_csWDI; lpCriticalSection
0x1800066bd  call    cs:__imp_EnterCriticalSection
0x1800066c3  lea     rdx, [rbx+0B8h]
0x1800066ca  mov     rcx, rbx; lpMem
0x1800066cd  mov     [rbx+28h], rdx
0x1800066d1  movups  xmm0, xmmword ptr [rbp+0]
0x1800066d5  movups  xmmword ptr [rdx], xmm0
0x1800066d8  movups  xmm1, xmmword ptr [rbp+10h]
0x1800066dc  movups  xmmword ptr [rdx+10h], xmm1
0x1800066e0  movups  xmm0, xmmword ptr [rbp+20h]
0x1800066e4  movups  xmmword ptr [rdx+20h], xmm0
0x1800066e8  movups  xmm1, xmmword ptr [rbp+30h]
0x1800066ec  movups  xmmword ptr [rdx+30h], xmm1
0x1800066f0  movups  xmm0, xmmword ptr [rbp+40h]
0x1800066f4  movups  xmmword ptr [rdx+40h], xmm0
0x1800066f8  movups  xmm1, xmmword ptr [rbp+50h]
0x1800066fc  movups  xmmword ptr [rdx+50h], xmm1
0x180006700  movups  xmm0, xmmword ptr [rbp+60h]
0x180006704  movups  xmmword ptr [rdx+60h], xmm0
0x180006708  movups  xmm1, xmmword ptr [rbp+70h]
0x18000670c  movups  xmmword ptr [rdx+70h], xmm1
0x180006710  movups  xmm0, xmmword ptr [rbp+80h]
0x180006717  movups  xmmword ptr [rdx+80h], xmm0
0x18000671e  movups  xmm1, xmmword ptr [rbp+90h]
0x180006725  movups  xmmword ptr [rdx+90h], xmm1
0x18000672c  movups  xmm0, xmmword ptr [rbp+0A0h]
0x180006733  movups  xmmword ptr [rdx+0A0h], xmm0
0x18000673a  movups  xmm1, xmmword ptr [rbp+0B0h]
0x180006741  movups  xmmword ptr [rdx+0B0h], xmm1
0x180006748  movups  xmm0, xmmword ptr [rbp+0C0h]
0x18000674f  movups  xmmword ptr [rdx+0C0h], xmm0
0x180006756  movups  xmm1, xmmword ptr [rbp+0D0h]
0x18000675d  movups  xmmword ptr [rdx+0D0h], xmm1
0x180006764  movups  xmm0, xmmword ptr [rbp+0E0h]
0x18000676b  movups  xmmword ptr [rdx+0E0h], xmm0
0x180006772  mov     rax, [rbp+0F0h]
0x180006779  mov     [rdx+0F0h], rax
0x180006780  call    WdipReleaseInstance
0x180006785  lea     rcx, g_csWDI; lpCriticalSection
0x18000678c  call    cs:__imp_LeaveCriticalSection
0x180006792  mov     eax, edi
0x180006794  mov     rcx, [rsp+78h+var_30]
0x180006799  xor     rcx, rsp; StackCookie
0x18000679c  call    __security_check_cookie
0x1800067a1  mov     rbx, [rsp+78h+arg_10]
0x1800067a9  add     rsp, 50h
0x1800067ad  pop     r15
0x1800067af  pop     r14
0x1800067b1  pop     rdi
0x1800067b2  pop     rsi
0x1800067b3  pop     rbp
0x1800067b4  retn
```
