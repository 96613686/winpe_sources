# CBridgeWindow::SetHostedWindow(HWND__ *)

- ea: `0x1800414e0`
- end: `0x1800416fe`
- name: `?SetHostedWindow@CBridgeWindow@@UEAAJPEAUHWND__@@@Z`
- size: `542`
- prototype: `int(CBridgeWindow *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013f14`
- `0x1800414e0`
- `0x180041704`
- `0x180059b4c`
- `0x18005cb3c`
- `0x18005ecdc`
- `0x18005edb4`
- `0x18005f5dc`
- `0x18005f938`
- `0x18005ff1c`
- `0x18005ffcc`
- `0x180060f9c`
- `0x1800dfe54`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004158e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004158e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800415e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800415e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041620`
- `USER32!GetWindowThreadProcessId` at `0x180041582`
- `USER32!GetWindowThreadProcessId` at `0x180041582`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004163e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004163e`

## pseudocode

```c
__int64 __fastcall CBridgeWindow::SetHostedWindow(CBridgeWindow *this, CallerIdentity *a2)
{
  CBridgeWindow *v2; // r14
  int started; // ebx
  __int64 v6; // rcx
  HWND v7; // rdx
  int v8; // eax
  bool v9; // al
  unsigned __int16 **v10; // r8
  __int64 v11; // rcx
  unsigned __int16 **v12; // r8
  __int64 v13; // rbx
  struct CCrashDetector::CHandler *v14; // rax
  DWORD dwProcessId; // [rsp+60h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  v2 = (CBridgeWindow *)((char *)this - 48);
  if ( *((_QWORD *)this + 8) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
    }
    v6 = *((_QWORD *)this + 37);
    v7 = (HWND)*((_QWORD *)this + 8);
    if ( v6 )
      v8 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v6 + 40LL))(v6, v7);
    else
      v8 = _SetOwnerWindow((HWND)a2, v7);
    started = v8;
    if ( v8 >= 0 )
    {
      dwProcessId = 0;
      GetWindowThreadProcessId((HWND)a2, &dwProcessId);
      v9 = dwProcessId != GetCurrentProcessId();
      *((_BYTE *)this + 99) = v9;
      if ( v9 )
        CBridgeWindow::_AttachOrDetachInputQueues(v2, 0, (HWND)a2, 0);
      started = CBridgeWindow::_EnsureRegisteredPLMExemption(v2, (HWND)a2);
      if ( started >= 0 )
      {
        started = 0;
        hMem = 0;
        if ( !*((_QWORD *)this + 34) )
        {
          LocalFree(0);
          if ( CallerIdentity::GetPsmKeyFromWindow(a2, (HWND)&hMem, v10) >= 0 )
          {
            Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease((char *)this + 272);
            started = CBridgeWindow::_BeginTaskCompletion(v11, (HWND)a2, 0x100000u, (_QWORD *)this + 34);
          }
        }
        LocalFree(hMem);
        if ( started >= 0 )
        {
          CoTaskMemFree(*((LPVOID *)this + 19));
          CallerIdentity::GetImmersiveAppIdFromWindow(a2, (HWND)this + 38, v12);
          hMem = 0;
          if ( *((_QWORD *)this + 32)
            && (int)WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(
                      (char *)this + 256,
                      &hMem) >= 0
            && hMem )
          {
            (*(void (__fastcall **)(HLOCAL, CallerIdentity *))(*(_QWORD *)hMem + 24LL))(hMem, a2);
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&hMem);
          v13 = *((_QWORD *)this + 8);
          v14 = (struct CCrashDetector::CHandler *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v14 )
          {
            *((_QWORD *)v14 + 1) = v13;
            *(_QWORD *)v14 = off_1800F0D50;
          }
          started = CCrashDetector::_StartMonitoringThreadOfWindow((char *)this + 304, (HWND)a2, v14);
          if ( started >= 0 )
          {
            *((_QWORD *)this + 18) = a2;
            CBridgeWindow::_SyncWindowPosition(v2);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800414e0  mov     [rsp+arg_8], rbx
0x1800414e5  push    rbp
0x1800414e6  push    rsi
0x1800414e7  push    rdi
0x1800414e8  push    r14
0x1800414ea  push    r15
0x1800414ec  sub     rsp, 30h
0x1800414f0  lea     r14, [rcx-30h]
0x1800414f4  mov     rdi, rdx
0x1800414f7  mov     r9, [r14+70h]
0x1800414fb  mov     rsi, rcx
0x1800414fe  test    r9, r9
0x180041501  jnz     short loc_18004150D
0x180041503  mov     ebx, 8000FFFFh
0x180041508  jmp     loc_1800416EA
0x18004150d  mov     rcx, cs:WPP_GLOBAL_Control
0x180041514  lea     rax, WPP_GLOBAL_Control
0x18004151b  cmp     rcx, rax
0x18004151e  jz      short loc_18004153F
0x180041520  test    byte ptr [rcx+1Ch], 1
0x180041524  jz      short loc_18004153F
0x180041526  cmp     byte ptr [rcx+19h], 4
0x18004152a  jb      short loc_18004153F
0x18004152c  mov     rcx, [rcx+10h]
0x180041530  mov     edx, 0Bh
0x180041535  mov     [rsp+58h+var_38], rdi
0x18004153a  call    WPP_SF_qq
0x18004153f  mov     rcx, [rsi+128h]
0x180041546  lea     r15, [rsi+40h]
0x18004154a  mov     rdx, [r15]; hWnd
0x18004154d  test    rcx, rcx
0x180041550  jnz     short loc_18004155C
0x180041552  mov     rcx, rdi; hWndInsertAfter
0x180041555  call    ?_SetOwnerWindow@@YAJPEAUHWND__@@0@Z; _SetOwnerWindow(HWND__ *,HWND__ *)
0x18004155a  jmp     short loc_180041568
0x18004155c  mov     rax, [rcx]
0x18004155f  mov     rax, [rax+28h]
0x180041563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041568  mov     ebx, eax
0x18004156a  test    eax, eax
0x18004156c  js      loc_1800416EA
0x180041572  lea     rdx, [rsp+58h+dwProcessId]; lpdwProcessId
0x180041577  mov     [rsp+58h+dwProcessId], 0
0x18004157f  mov     rcx, rdi; hWnd
0x180041582  call    cs:__imp_GetWindowThreadProcessId
0x180041589  nop     dword ptr [rax+rax+00h]
0x18004158e  call    cs:__imp_GetCurrentProcessId
0x180041595  nop     dword ptr [rax+rax+00h]
0x18004159a  cmp     [rsp+58h+dwProcessId], eax
0x18004159e  setnz   al
0x1800415a1  mov     [rsi+63h], al
0x1800415a4  test    al, al
0x1800415a6  jz      short loc_1800415B8
0x1800415a8  xor     r9d, r9d; bool
0x1800415ab  mov     r8, rdi; HWND
0x1800415ae  xor     edx, edx; bool
0x1800415b0  mov     rcx, r14; this
0x1800415b3  call    ?_AttachOrDetachInputQueues@CBridgeWindow@@AEAAJ_NPEAUHWND__@@0@Z; CBridgeWindow::_AttachOrDetachInputQueues(bool,HWND__ *,bool)
0x1800415b8  mov     rdx, rdi; HWND
0x1800415bb  mov     rcx, r14; this
0x1800415be  call    ?_EnsureRegisteredPLMExemption@CBridgeWindow@@AEAAJPEAUHWND__@@@Z; CBridgeWindow::_EnsureRegisteredPLMExemption(HWND__ *)
0x1800415c3  mov     ebx, eax
0x1800415c5  test    eax, eax
0x1800415c7  js      loc_1800416EA
0x1800415cd  xor     ebx, ebx
0x1800415cf  lea     rbp, [rsi+110h]
0x1800415d6  mov     [rsp+58h+hMem], rbx
0x1800415db  cmp     [rbp+0], rbx
0x1800415df  jnz     short loc_18004161B
0x1800415e1  xor     ecx, ecx; hMem
0x1800415e3  call    cs:__imp_LocalFree
0x1800415ea  nop     dword ptr [rax+rax+00h]
0x1800415ef  lea     rdx, [rsp+58h+hMem]; HWND
0x1800415f4  mov     rcx, rdi; this
0x1800415f7  call    ?GetPsmKeyFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetPsmKeyFromWindow(HWND__ *,ushort * *)
0x1800415fc  test    eax, eax
0x1800415fe  js      short loc_18004161B
0x180041600  mov     rcx, rbp
0x180041603  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180041608  mov     r9, rbp
0x18004160b  mov     r8d, 100000h
0x180041611  mov     rdx, rdi
0x180041614  call    ?_BeginTaskCompletion@CBridgeWindow@@AEAAJPEAUHWND__@@W4PLM_TASKCOMPLETION_CATEGORY_FLAGS@@PEAPEAUIOSTaskCompletion@@@Z; CBridgeWindow::_BeginTaskCompletion(HWND__ *,PLM_TASKCOMPLETION_CATEGORY_FLAGS,IOSTaskCompletion * *)
0x180041619  mov     ebx, eax
0x18004161b  mov     rcx, [rsp+58h+hMem]; hMem
0x180041620  call    cs:__imp_LocalFree
0x180041627  nop     dword ptr [rax+rax+00h]
0x18004162c  test    ebx, ebx
0x18004162e  js      loc_1800416EA
0x180041634  lea     rbx, [rsi+98h]
0x18004163b  mov     rcx, [rbx]; pv
0x18004163e  call    cs:__imp_CoTaskMemFree
0x180041645  nop     dword ptr [rax+rax+00h]
0x18004164a  mov     rdx, rbx; HWND
0x18004164d  mov     rcx, rdi; this
0x180041650  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x180041655  lea     rcx, [rsi+100h]
0x18004165c  mov     [rsp+58h+hMem], 0
0x180041665  cmp     qword ptr [rcx], 0
0x180041669  jz      short loc_180041692
0x18004166b  lea     rdx, [rsp+58h+hMem]
0x180041670  call    ??$WeakRefAs@V?$ComPtrRef@V?$ComPtr@UIHostedApplicationEventSink@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@@YAJAEBVWeakRef@WRL@Microsoft@@V?$ComPtrRef@V?$ComPtr@UIHostedApplicationEventSink@@@WRL@Microsoft@@@Details@12@@Z; WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(Microsoft::WRL::WeakRef const &,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>)
0x180041675  test    eax, eax
0x180041677  js      short loc_180041692
0x180041679  mov     rcx, [rsp+58h+hMem]
0x18004167e  test    rcx, rcx
0x180041681  jz      short loc_180041692
0x180041683  mov     rax, [rcx]
0x180041686  mov     rdx, rdi
0x180041689  mov     rax, [rax+18h]
0x18004168d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041692  lea     rcx, [rsp+58h+hMem]
0x180041697  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18004169c  mov     rbx, [r15]
0x18004169f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800416a6  mov     ecx, 10h; unsigned __int64
0x1800416ab  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800416b0  test    rax, rax
0x1800416b3  jz      short loc_1800416C3
0x1800416b5  lea     rcx, off_1800F0D50
0x1800416bc  mov     [rax+8], rbx
0x1800416c0  mov     [rax], rcx
0x1800416c3  mov     r8, rax; struct CCrashDetector::CHandler *
0x1800416c6  lea     rcx, [rsi+130h]; pv
0x1800416cd  mov     rdx, rdi; hWnd
0x1800416d0  call    ?_StartMonitoringThreadOfWindow@CCrashDetector@@AEAAJPEAUHWND__@@PEAVCHandler@1@@Z; CCrashDetector::_StartMonitoringThreadOfWindow(HWND__ *,CCrashDetector::CHandler *)
0x1800416d5  mov     ebx, eax
0x1800416d7  test    eax, eax
0x1800416d9  js      short loc_1800416EA
0x1800416db  mov     rcx, r14; this
0x1800416de  mov     [rsi+90h], rdi
0x1800416e5  call    ?_SyncWindowPosition@CBridgeWindow@@AEAAXXZ; CBridgeWindow::_SyncWindowPosition(void)
0x1800416ea  mov     eax, ebx
0x1800416ec  mov     rbx, [rsp+58h+arg_8]
0x1800416f1  add     rsp, 30h
0x1800416f5  pop     r15
0x1800416f7  pop     r14
0x1800416f9  pop     rdi
0x1800416fa  pop     rsi
0x1800416fb  pop     rbp
0x1800416fc  retn
```
