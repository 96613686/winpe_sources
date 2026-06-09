# _WrapperThreadProc

- ea: `0x180044220`
- end: `0x1800445bd`
- name: `_WrapperThreadProc`
- size: `925`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180019cc0`
- `0x180044220`
- `0x1800445c4`
- `0x1800517b0`
- `0x180068a94`
- `0x180068d9c`
- `0x180093410`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800445b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800445b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18004436c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18004436c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800442ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800442ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004445e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004445e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044533`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180044533`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044588`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044588`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180044409`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180044409`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x1800444d7`
- `ntdll!RtlClearThreadWorkOnBehalfTicket` at `0x1800444d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044436`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044436`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800444cc`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800444cc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004455e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004455e`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800444f2`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x1800444f2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800443f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1800443f0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800443fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1800443fa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1800443e2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1800443e2`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1800444e2`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1800444e2`
- `ext-ms-win-ntuser-keyboard-l1-1-0!ActivateKeyboardLayout` at `0x180044577`
- `ext-ms-win-ntuser-keyboard-l1-1-0!ActivateKeyboardLayout` at `0x180044577`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x18004450f`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x18004450f`

## pseudocode

```c
__int64 __fastcall WrapperThreadProc(_OWORD *Parameter)
{
  __int128 v1; // xmm0
  __int128 v3; // xmm1
  int inited; // edi
  __int128 v5; // xmm0
  IUnknown *v6; // rbx
  __int128 v7; // xmm1
  DWORD v8; // r15d
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  char v11; // si
  int v12; // eax
  DWORD CurrentThreadId; // eax
  __int128 v15; // [rsp+20h] [rbp-69h] BYREF
  HANDLE hEvent[2]; // [rsp+30h] [rbp-59h]
  LPVOID lpTlsValue[2]; // [rsp+40h] [rbp-49h]
  HMODULE hLibModule[2]; // [rsp+50h] [rbp-39h]
  __int128 v19; // [rsp+60h] [rbp-29h]
  HKL hkl[2]; // [rsp+70h] [rbp-19h]
  _QWORD Buf1[2]; // [rsp+80h] [rbp-9h] BYREF
  struct tagMSG Msg; // [rsp+90h] [rbp+7h] BYREF
  int v23; // [rsp+F0h] [rbp+67h] BYREF
  __int64 Buf2; // [rsp+F8h] [rbp+6Fh] BYREF

  v1 = *Parameter;
  v3 = Parameter[1];
  Buf2 = 0;
  v15 = v1;
  inited = -2147467259;
  v5 = Parameter[2];
  v23 = 0;
  *(_OWORD *)hEvent = v3;
  v6 = 0;
  v7 = Parameter[3];
  v8 = 0;
  *(_OWORD *)lpTlsValue = v5;
  v9 = Parameter[4];
  *(_OWORD *)hLibModule = v7;
  v10 = Parameter[5];
  v19 = v9;
  Buf1[0] = *((_QWORD *)Parameter + 12);
  *(_OWORD *)hkl = v10;
  if ( !memcmp_0(Buf1, &Buf2, 8u) )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    RtlSetThreadWorkOnBehalfTicket(Buf1);
  }
  if ( ((__int64)lpTlsValue[0] & 0x8000) != 0 && GetSystemMetrics(82) && (unsigned __int8)IsImmDisableIMEPresent() )
    ImmDisableIME(0);
  if ( ((__int64)lpTlsValue[0] & 0x20) != 0 )
  {
    v6 = (IUnknown *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6[3].lpVtbl = 0;
      v6->lpVtbl = (struct IUnknownVtbl *)&CRefThread::`vftable';
      v6[1].lpVtbl = (struct IUnknownVtbl *)&v23;
      LODWORD(v6[2].lpVtbl) = CurrentThreadId;
      v23 = 1;
      LODWORD(v19) = SHSetThreadRef(v6);
    }
    else
    {
      v23 = 0;
      v6 = 0;
      LODWORD(v19) = -2147024882;
    }
  }
  if ( (int)v19 >= 0 )
  {
    if ( lpTlsValue[1] )
      LODWORD(v19) = !TlsSetValue(*(&dwTlsIndex + 1), lpTlsValue[1]) ? 0x80004005 : 0;
    if ( (int)v19 >= 0 )
    {
      if ( ((__int64)lpTlsValue[0] & 0x400) != 0 )
      {
        LODWORD(Buf2) = 1;
        SystemParametersInfoW(0x104Eu, 0, &Buf2, 0);
        if ( (_DWORD)Buf2 )
          ActivateKeyboardLayout(hkl[0], 0x80u);
      }
      if ( *((_QWORD *)&v15 + 1) )
      {
        inited = InitCOM(&v15);
        if ( (int)v19 >= 0 )
          (*((void (__fastcall **)(HANDLE))&v15 + 1))(hEvent[1]);
      }
    }
  }
  *((_DWORD *)Parameter + 16) = v19;
  SetEvent(hEvent[0]);
  if ( !v11 )
    RtlClearThreadWorkOnBehalfTicket();
  v12 = v19;
  if ( (int)v19 >= 0 )
  {
    if ( !*((_QWORD *)&v15 + 1) )
    {
      inited = InitCOM(&v15);
      v12 = v19;
    }
    if ( v12 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(HANDLE))v15)(hEvent[1]);
      if ( ((__int64)lpTlsValue[0] & 0x20) != 0 )
      {
        if ( v6 )
        {
          ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
          while ( v23 )
          {
            memset(&Msg, 0, sizeof(Msg));
            if ( GetMessageW(&Msg, 0, 0, 0) )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
        }
      }
    }
  }
  if ( lpTlsValue[1] && TlsGetValue(*(&dwTlsIndex + 1)) )
    SHReleaseThreadRef();
  if ( hLibModule[0] )
    (*(void (__fastcall **)(HMODULE))(*(_QWORD *)hLibModule[0] + 16LL))(hLibModule[0]);
  if ( inited >= 0 )
  {
    if ( ((__int64)lpTlsValue[0] & 0x800) != 0 )
    {
      OleUninitialize();
    }
    else if ( ((__int64)lpTlsValue[0] & 0x1008) != 0 )
    {
      if ( !inited )
        CoUninitialize();
    }
    else if ( ((__int64)lpTlsValue[0] & 0x4000) != 0 )
    {
      RoUninitialize();
    }
  }
  if ( hkl[1] )
    FreeLibrary((HMODULE)hkl[1]);
  if ( hLibModule[1] )
    FreeLibraryAndExitThread(hLibModule[1], v8);
  return v8;
}

```

## disassembly

```asm
0x180044220  mov     [rsp-8+arg_10], rbx
0x180044225  mov     [rsp-8+arg_18], rsi
0x18004422a  push    rbp
0x18004422b  push    rdi
0x18004422c  push    r12
0x18004422e  push    r14
0x180044230  push    r15
0x180044232  lea     rbp, [rsp-37h]
0x180044237  sub     rsp, 0C0h
0x18004423e  movups  xmm0, xmmword ptr [rcx]
0x180044241  xor     r12d, r12d
0x180044244  mov     r14, rcx
0x180044247  movups  xmm1, xmmword ptr [rcx+10h]
0x18004424b  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18004424f  mov     [rbp+57h+Buf2], r12
0x180044253  movaps  [rbp+57h+var_C0], xmm0
0x180044257  mov     edi, 80004005h
0x18004425c  movups  xmm0, xmmword ptr [rcx+20h]
0x180044260  lea     r8d, [r12+8]; Size
0x180044265  mov     [rbp+57h+arg_0], r12d
0x180044269  movaps  xmmword ptr [rbp+57h+hEvent], xmm1
0x18004426d  mov     ebx, r12d
0x180044270  movups  xmm1, xmmword ptr [rcx+30h]
0x180044274  mov     r15d, r12d
0x180044277  movaps  xmmword ptr [rbp+57h+lpTlsValue], xmm0
0x18004427b  movups  xmm0, xmmword ptr [rcx+40h]
0x18004427f  movaps  xmmword ptr [rbp+57h+hLibModule], xmm1
0x180044283  movups  xmm1, xmmword ptr [rcx+50h]
0x180044287  movaps  [rbp+57h+var_80], xmm0
0x18004428b  movsd   xmm0, qword ptr [rcx+60h]
0x180044290  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180044294  movsd   [rbp+57h+Buf1], xmm0
0x180044299  movaps  xmmword ptr [rbp+57h+hkl], xmm1
0x18004429d  call    memcmp_0
0x1800442a2  test    eax, eax
0x1800442a4  jnz     loc_180044402
0x1800442aa  mov     sil, 1
0x1800442ad  test    dword ptr [rbp+57h+lpTlsValue], 8000h
0x1800442b4  jnz     loc_1800444ED
0x1800442ba  test    byte ptr [rbp+57h+lpTlsValue], 20h
0x1800442be  jnz     loc_180044441
0x1800442c4  cmp     dword ptr [rbp+57h+var_80], r12d
0x1800442c8  jl      short loc_1800442F4
0x1800442ca  mov     rdx, [rbp+57h+lpTlsValue+8]; lpTlsValue
0x1800442ce  test    rdx, rdx
0x1800442d1  jnz     loc_18004452D
0x1800442d7  cmp     dword ptr [rbp+57h+var_80], r12d
0x1800442db  jl      short loc_1800442F4
0x1800442dd  test    dword ptr [rbp+57h+lpTlsValue], 400h
0x1800442e4  jnz     loc_180044549
0x1800442ea  cmp     qword ptr [rbp+57h+var_C0+8], r12
0x1800442ee  jnz     loc_180044498
0x1800442f4  mov     ecx, dword ptr [rbp+57h+var_80]
0x1800442f7  mov     [r14+40h], ecx
0x1800442fb  mov     rcx, [rbp+57h+hEvent]; hEvent
0x1800442ff  call    cs:__imp_SetEvent
0x180044305  test    sil, sil
0x180044308  jz      loc_1800444D7
0x18004430e  mov     eax, dword ptr [rbp+57h+var_80]
0x180044311  test    eax, eax
0x180044313  jns     short loc_180044373
0x180044315  cmp     [rbp+57h+lpTlsValue+8], r12
0x180044319  jnz     loc_180044582
0x18004431f  mov     rcx, [rbp+57h+hLibModule]
0x180044323  test    rcx, rcx
0x180044326  jnz     loc_1800445A1
0x18004432c  test    edi, edi
0x18004432e  jns     loc_180044414
0x180044334  mov     rcx, [rbp+57h+hkl+8]; hLibModule
0x180044338  test    rcx, rcx
0x18004433b  jnz     loc_1800445B2
0x180044341  mov     rcx, [rbp+57h+hLibModule+8]; hLibModule
0x180044345  test    rcx, rcx
0x180044348  jnz     short loc_180044369
0x18004434a  lea     r11, [rsp+0E0h+var_20]
0x180044352  mov     eax, r15d
0x180044355  mov     rbx, [r11+40h]
0x180044359  mov     rsi, [r11+48h]
0x18004435d  mov     rsp, r11
0x180044360  pop     r15
0x180044362  pop     r14
0x180044364  pop     r12
0x180044366  pop     rdi
0x180044367  pop     rbp
0x180044368  retn
0x180044369  mov     edx, r15d; dwExitCode
0x18004436c  call    cs:__imp_FreeLibraryAndExitThread
0x180044372  int     3; Trap to Debugger
0x180044373  cmp     qword ptr [rbp+57h+var_C0+8], r12
0x180044377  jnz     short loc_180044387
0x180044379  lea     rcx, [rbp+57h+var_C0]
0x18004437d  call    _InitCOM
0x180044382  mov     edi, eax
0x180044384  mov     eax, dword ptr [rbp+57h+var_80]
0x180044387  test    eax, eax
0x180044389  js      short loc_180044315
0x18004438b  mov     rcx, [rbp+57h+hEvent+8]
0x18004438f  mov     rax, qword ptr [rbp+57h+var_C0]
0x180044393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044398  test    byte ptr [rbp+57h+lpTlsValue], 20h
0x18004439c  mov     r15d, eax
0x18004439f  jz      loc_180044315
0x1800443a5  test    rbx, rbx
0x1800443a8  jz      loc_180044315
0x1800443ae  mov     rdx, [rbx]
0x1800443b1  mov     rcx, rbx
0x1800443b4  mov     rax, [rdx+10h]
0x1800443b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443bd  cmp     [rbp+57h+arg_0], r12d
0x1800443c1  jz      loc_180044315
0x1800443c7  xorps   xmm0, xmm0
0x1800443ca  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800443ce  xor     r9d, r9d; wMsgFilterMax
0x1800443d1  xor     r8d, r8d; wMsgFilterMin
0x1800443d4  xor     edx, edx; hWnd
0x1800443d6  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800443da  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x1800443de  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800443e2  call    cs:__imp_GetMessageW
0x1800443e8  test    eax, eax
0x1800443ea  jz      short loc_1800443BD
0x1800443ec  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800443f0  call    cs:__imp_TranslateMessage
0x1800443f6  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800443fa  call    cs:__imp_DispatchMessageW
0x180044400  jmp     short loc_1800443BD
0x180044402  lea     rcx, [rbp+57h+Buf1]
0x180044406  mov     sil, r12b
0x180044409  call    cs:__imp_RtlSetThreadWorkOnBehalfTicket
0x18004440f  jmp     loc_1800442AD
0x180044414  test    dword ptr [rbp+57h+lpTlsValue], 800h
0x18004441b  jnz     loc_1800444E2
0x180044421  test    dword ptr [rbp+57h+lpTlsValue], 1008h
0x180044428  jz      loc_1800444BF
0x18004442e  test    edi, edi
0x180044430  jnz     loc_180044334
0x180044436  call    cs:__imp_CoUninitialize
0x18004443c  jmp     loc_180044334
0x180044441  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044448  mov     ecx, 20h ; ' '; unsigned __int64
0x18004444d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044452  mov     rbx, rax
0x180044455  test    rax, rax
0x180044458  jz      loc_18004451A
0x18004445e  call    cs:__imp_GetCurrentThreadId
0x180044464  mov     [rbx+18h], r12
0x180044468  lea     rcx, ??_7CRefThread@@6B@; const CRefThread::`vftable'
0x18004446f  mov     [rbx], rcx
0x180044472  lea     rcx, [rbp+57h+arg_0]
0x180044476  mov     [rbx+8], rcx
0x18004447a  mov     rcx, rbx; punk
0x18004447d  mov     [rbx+10h], eax
0x180044480  mov     [rbp+57h+arg_0], 1
0x180044487  mov     dword ptr [rbp+57h+var_80], r12d
0x18004448b  call    SHSetThreadRef
0x180044490  mov     dword ptr [rbp+57h+var_80], eax
0x180044493  jmp     loc_1800442C4
0x180044498  lea     rcx, [rbp+57h+var_C0]
0x18004449c  call    _InitCOM
0x1800444a1  mov     edi, eax
0x1800444a3  cmp     dword ptr [rbp+57h+var_80], r12d
0x1800444a7  jl      loc_1800442F4
0x1800444ad  mov     rcx, [rbp+57h+hEvent+8]
0x1800444b1  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x1800444b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444ba  jmp     loc_1800442F4
0x1800444bf  test    dword ptr [rbp+57h+lpTlsValue], 4000h
0x1800444c6  jz      loc_180044334
0x1800444cc  call    cs:__imp_RoUninitialize
0x1800444d2  jmp     loc_180044334
0x1800444d7  call    cs:__imp_RtlClearThreadWorkOnBehalfTicket
0x1800444dd  jmp     loc_18004430E
0x1800444e2  call    cs:__imp_OleUninitialize
0x1800444e8  jmp     loc_180044334
0x1800444ed  mov     ecx, 52h ; 'R'; nIndex
0x1800444f2  call    cs:__imp_GetSystemMetrics
0x1800444f8  test    eax, eax
0x1800444fa  jz      loc_1800442BA
0x180044500  call    IsImmDisableIMEPresent
0x180044505  test    al, al
0x180044507  jz      loc_1800442BA
0x18004450d  xor     ecx, ecx; DWORD
0x18004450f  call    cs:__imp_ImmDisableIME
0x180044515  jmp     loc_1800442BA
0x18004451a  mov     [rbp+57h+arg_0], r12d
0x18004451e  mov     rbx, r12
0x180044521  mov     dword ptr [rbp+57h+var_80], 8007000Eh
0x180044528  jmp     loc_1800442C4
0x18004452d  mov     ecx, dword ptr cs:dwTlsIndex+4; dwTlsIndex
0x180044533  call    cs:__imp_TlsSetValue
0x180044539  neg     eax
0x18004453b  sbb     ecx, ecx
0x18004453d  not     ecx
0x18004453f  and     ecx, edi
0x180044541  mov     dword ptr [rbp+57h+var_80], ecx
0x180044544  jmp     loc_1800442D7
0x180044549  xor     r9d, r9d; fWinIni
0x18004454c  mov     dword ptr [rbp+57h+Buf2], 1
0x180044553  lea     r8, [rbp+57h+Buf2]; pvParam
0x180044557  xor     edx, edx; uiParam
0x180044559  mov     ecx, 104Eh; uiAction
0x18004455e  call    cs:__imp_SystemParametersInfoW
0x180044564  cmp     dword ptr [rbp+57h+Buf2], r12d
0x180044568  jz      loc_1800442EA
0x18004456e  mov     rcx, [rbp+57h+hkl]; hkl
0x180044572  mov     edx, 80h; Flags
0x180044577  call    cs:__imp_ActivateKeyboardLayout
0x18004457d  jmp     loc_1800442EA
0x180044582  mov     ecx, dword ptr cs:dwTlsIndex+4; dwTlsIndex
0x180044588  call    cs:__imp_TlsGetValue
0x18004458e  test    rax, rax
0x180044591  jz      loc_18004431F
0x180044597  call    SHReleaseThreadRef
0x18004459c  jmp     loc_18004431F
0x1800445a1  mov     rax, [rcx]
0x1800445a4  mov     rax, [rax+10h]
0x1800445a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445ad  jmp     loc_18004432C
0x1800445b2  call    cs:__imp_FreeLibrary
0x1800445b8  jmp     loc_180044341
```
