# _InvokeLocalServer(ushort const *)

- ea: `0x140007098`
- end: `0x1400072d9`
- name: `?_InvokeLocalServer@@YAXPEBG@Z`
- size: `577`
- prototype: `void __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140007798`

## callees

- `0x140002be0`
- `0x14000678c`
- `0x140007098`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000725e`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x14000725e`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400070fc`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400070fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000713a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000713a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400070b5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400070b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400072c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400072c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400071b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400071b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007229`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007229`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007187`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007218`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007187`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140007218`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000719d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000719d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400072b6`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x140007299`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x140007299`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14000727d`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14000727d`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x140007287`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x140007287`

## pseudocode

```c
void __fastcall _InvokeLocalServer(LPCWSTR lpName)
{
  int *v2; // rbx
  DWORD CurrentThreadId; // ebx
  int v4; // edi
  HANDLE EventW; // rax
  void *v6; // rbx
  LPVOID ppv; // [rsp+50h] [rbp-19h] BYREF
  int v8; // [rsp+58h] [rbp-11h] BYREF
  __int64 v9; // [rsp+60h] [rbp-9h]
  MSG Msg; // [rsp+68h] [rbp-1h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    if ( CoInitializeSecurity(&CLSID_CreateObjectLocalServer, 0, 0, 0, 0, 0, 0, 8u, 0) >= 0 )
    {
      v8 = 1;
      v9 = 2;
      ppv = 0;
      if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
      {
        v2 = &v8;
        do
        {
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
            ppv,
            (unsigned int)*v2,
            *((_QWORD *)v2 + 1));
          v2 += 4;
        }
        while ( v2 != (int *)&Msg );
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      g_hConnected = CreateEventW(0, 1, 0, 0);
      if ( g_hConnected )
      {
        CurrentThreadId = GetCurrentThreadId();
        InitOnceExecuteOnce(
          &Microsoft::WRL::Details::OutOfProcModuleBase<CSingleUseOutOfProcModule>::initOnceOutOfProc_,
          _lambda_f1e7f17610f55d1f3f4cf582571324a1_::_lambda_invoker_cdecl_,
          0,
          0);
        byte_140012570 = 1;
        if ( !qword_140012568 )
        {
          byte_140012598 = 1;
          qword_140012580 = (__int64)off_14000D098;
          qword_140012568 = (__int64)&qword_140012580;
          byte_140012588 = 0;
          dword_140012590 = CurrentThreadId;
        }
        v4 = Microsoft::WRL::Details::RegisterObjects<2>(&Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_);
        EventW = CreateEventW(0, 0, 0, lpName);
        v6 = EventW;
        if ( EventW )
        {
          SetEvent(EventW);
          CloseHandle(v6);
        }
        if ( v4 >= 0 )
        {
          LODWORD(ppv) = 0;
          if ( !CoWaitForMultipleHandles(0, 0x7530u, 1u, &g_hConnected, (LPDWORD)&ppv) )
          {
            memset(&Msg, 0, sizeof(Msg));
            while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
          Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects((Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_);
        }
        CloseHandle(g_hConnected);
        g_hConnected = 0;
      }
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x140007098  push    rbp
0x14000709a  push    rbx
0x14000709b  push    rsi
0x14000709c  push    rdi
0x14000709d  lea     rbp, [rsp-3Fh]
0x1400070a2  sub     rsp, 0A8h
0x1400070a9  mov     rsi, rcx
0x1400070ac  mov     ebx, 2
0x1400070b1  mov     edx, ebx; dwCoInit
0x1400070b3  xor     ecx, ecx; pvReserved
0x1400070b5  call    cs:__imp_CoInitializeEx
0x1400070bb  test    eax, eax
0x1400070bd  js      loc_1400072CD
0x1400070c3  mov     [rsp+0C0h+pReserved3], 0; pReserved3
0x1400070cc  lea     rcx, CLSID_CreateObjectLocalServer; pSecDesc
0x1400070d3  mov     [rsp+0C0h+dwCapabilities], 8; dwCapabilities
0x1400070db  xor     r9d, r9d; pReserved1
0x1400070de  mov     [rsp+0C0h+pAuthList], 0; pAuthList
0x1400070e7  xor     r8d, r8d; asAuthSvc
0x1400070ea  mov     [rsp+0C0h+dwImpLevel], 0; dwImpLevel
0x1400070f2  xor     edx, edx; cAuthSvc
0x1400070f4  mov     [rsp+0C0h+dwAuthnLevel], 0; dwAuthnLevel
0x1400070fc  call    cs:__imp_CoInitializeSecurity
0x140007102  test    eax, eax
0x140007104  js      loc_1400072C7
0x14000710a  lea     rax, [rbp+57h+ppv]
0x14000710e  mov     [rbp+57h+var_68], 1
0x140007115  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000711c  mov     qword ptr [rsp+0C0h+dwAuthnLevel], rax; ppv
0x140007121  xor     edx, edx; pUnkOuter
0x140007123  mov     [rbp+57h+var_60], rbx
0x140007127  lea     r8d, [rbx-1]; dwClsContext
0x14000712b  mov     [rbp+57h+ppv], 0
0x140007133  lea     rcx, CLSID_GlobalOptions; rclsid
0x14000713a  call    cs:__imp_CoCreateInstance
0x140007140  test    eax, eax
0x140007142  js      short loc_14000717B
0x140007144  lea     rbx, [rbp+57h+var_68]
0x140007148  mov     rcx, [rbp+57h+ppv]
0x14000714c  mov     r8, [rbx+8]
0x140007150  mov     edx, [rbx]
0x140007152  mov     rax, [rcx]
0x140007155  mov     rax, [rax+18h]
0x140007159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000715e  lea     rax, [rbp+57h+Msg]
0x140007162  add     rbx, 10h
0x140007166  cmp     rbx, rax
0x140007169  jnz     short loc_140007148
0x14000716b  mov     rcx, [rbp+57h+ppv]
0x14000716f  mov     rax, [rcx]
0x140007172  mov     rax, [rax+10h]
0x140007176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000717b  xor     r9d, r9d; lpName
0x14000717e  xor     r8d, r8d; bInitialState
0x140007181  xor     ecx, ecx; lpEventAttributes
0x140007183  lea     edx, [r9+1]; bManualReset
0x140007187  call    cs:__imp_CreateEventW
0x14000718d  mov     cs:?g_hConnected@@3PEAXEA, rax; void * g_hConnected
0x140007194  test    rax, rax
0x140007197  jz      loc_1400072C7
0x14000719d  call    cs:__imp_GetCurrentThreadId
0x1400071a3  xor     r9d, r9d; Context
0x1400071a6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f1e7f17610f55d1f3f4cf582571324a1_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1400071ad  xor     r8d, r8d; Parameter
0x1400071b0  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VCSingleUseOutOfProcModule@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1400071b7  mov     ebx, eax
0x1400071b9  call    cs:__imp_InitOnceExecuteOnce
0x1400071bf  cmp     cs:qword_140012568, 0
0x1400071c7  mov     cs:byte_140012570, 1
0x1400071ce  jnz     short loc_140007200
0x1400071d0  lea     rax, off_14000D098
0x1400071d7  mov     cs:byte_140012598, 1
0x1400071de  mov     cs:qword_140012580, rax
0x1400071e5  lea     rax, qword_140012580
0x1400071ec  mov     cs:qword_140012568, rax
0x1400071f3  mov     cs:byte_140012588, 0
0x1400071fa  mov     cs:dword_140012590, ebx
0x140007200  lea     rcx, ?instance_@?$StaticStorage@VCSingleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int> Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_
0x140007207  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x14000720c  mov     r9, rsi; lpName
0x14000720f  xor     r8d, r8d; bInitialState
0x140007212  xor     edx, edx; bManualReset
0x140007214  xor     ecx, ecx; lpEventAttributes
0x140007216  mov     edi, eax
0x140007218  call    cs:__imp_CreateEventW
0x14000721e  mov     rbx, rax
0x140007221  test    rax, rax
0x140007224  jz      short loc_140007238
0x140007226  mov     rcx, rax; hEvent
0x140007229  call    cs:__imp_SetEvent
0x14000722f  mov     rcx, rbx; hObject
0x140007232  call    cs:__imp_CloseHandle
0x140007238  test    edi, edi
0x14000723a  js      short loc_1400072AF
0x14000723c  xor     ecx, ecx; dwFlags
0x14000723e  mov     dword ptr [rbp+57h+ppv], 0
0x140007245  lea     rax, [rbp+57h+ppv]
0x140007249  mov     edx, 7530h; dwTimeout
0x14000724e  lea     r9, ?g_hConnected@@3PEAXEA; pHandles
0x140007255  mov     qword ptr [rsp+0C0h+dwAuthnLevel], rax; lpdwindex
0x14000725a  lea     r8d, [rcx+1]; cHandles
0x14000725e  call    cs:__imp_CoWaitForMultipleHandles
0x140007264  test    eax, eax
0x140007266  jnz     short loc_1400072A3
0x140007268  xorps   xmm0, xmm0
0x14000726b  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14000726f  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x140007273  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140007277  jmp     short loc_14000728D
0x140007279  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14000727d  call    cs:__imp_TranslateMessage
0x140007283  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140007287  call    cs:__imp_DispatchMessageW
0x14000728d  xor     r9d, r9d; wMsgFilterMax
0x140007290  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140007294  xor     r8d, r8d; wMsgFilterMin
0x140007297  xor     edx, edx; hWnd
0x140007299  call    cs:__imp_GetMessageW
0x14000729f  test    eax, eax
0x1400072a1  jg      short loc_140007279
0x1400072a3  lea     rcx, ?instance_@?$StaticStorage@VCSingleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; this
0x1400072aa  call    ?UnregisterObjects@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@QEAAJPEBG@Z; Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects(ushort const *)
0x1400072af  mov     rcx, cs:?g_hConnected@@3PEAXEA; hObject
0x1400072b6  call    cs:__imp_CloseHandle
0x1400072bc  mov     cs:?g_hConnected@@3PEAXEA, 0; void * g_hConnected
0x1400072c7  call    cs:__imp_CoUninitialize
0x1400072cd  add     rsp, 0A8h
0x1400072d4  pop     rdi
0x1400072d5  pop     rsi
0x1400072d6  pop     rbx
0x1400072d7  pop     rbp
0x1400072d8  retn
```
