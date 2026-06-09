# CRecoMaster::DoSemanticInterpretation(ISpPhrase *,int)

- ea: `0x18012f1a0`
- end: `0x18012f44c`
- name: `?DoSemanticInterpretation@CRecoMaster@@UEAAJPEAUISpPhrase@@H@Z`
- size: `684`
- prototype: `__int64 __fastcall(CRecoMaster *__hidden this, struct ISpPhrase *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000bec4`
- `0x18000e518`
- `0x180013ec0`
- `0x180045938`
- `0x18012b7bc`
- `0x18012f1a0`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012f1d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18012f1d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f2bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f2f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f372`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f2bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f2f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012f372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012f3c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012f3c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f21f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18012f21f`

## string_xrefs

- `0x18012f24b`: `Queue a semantic interpretation task`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRecoMaster::DoSemanticInterpretation(CRecoMaster *this, struct ISpPhrase *a2, int a3)
{
  HRESULT Win32Error; // ebx
  HANDLE EventW; // r14
  GUID *v8; // rcx
  void *v9; // rax
  DWORD v10; // eax
  DWORD v11; // edi
  int v12; // ecx
  __int64 v13; // rcx
  _QWORD v15[2]; // [rsp+40h] [rbp-10h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF
  struct IUnknown *ppv; // [rsp+98h] [rbp+48h] BYREF

  Win32Error = 0;
  v16 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    Win32Error = SpHrFromLastWin32Error();
  ppv = 0;
  if ( Win32Error < 0 )
    goto LABEL_27;
  v8 = &CLSID_SpW3CSemanticInterpretation;
  if ( !a3 )
    v8 = &CLSID_SpMSSemanticInterpretation;
  Win32Error = CoCreateInstance(v8, 0, 0x17u, &GUID_c073e8bd_00b7_4c20_99af_daadadcacdab, (LPVOID *)&ppv);
  if ( Win32Error < 0 )
    goto LABEL_27;
  *((_QWORD *)this + 124) = a2;
  if ( *((struct IUnknown **)this + 126) != ppv )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 126, ppv);
  DoTraceMessage(16, "Queue a semantic interpretation task");
  Win32Error = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, HANDLE, char *, int *))(**((_QWORD **)this + 95) + 40LL))(
                 *((_QWORD *)this + 95),
                 ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
                 &CRecoMaster::SMLId,
                 EventW,
                 (char *)this + 104,
                 &v16);
  if ( Win32Error < 0 )
    goto LABEL_27;
  v9 = (void *)((__int64 (__fastcall *)(struct IUnknown *))ppv->lpVtbl[1].Release)(ppv);
  v10 = WaitForSingleObject(v9, 0xEA60u);
  v11 = v10;
  if ( v10 == 258 )
  {
    DoTraceMessage(16, "jscript engine initialization has timed out");
    goto LABEL_19;
  }
  if ( !v10 )
  {
    v11 = WaitForSingleObject(EventW, 1000 * *((_DWORD *)this + 256));
    if ( v11 == 258 )
    {
      DoTraceMessage(16, "execution of jscript has timed out");
LABEL_19:
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl[1].AddRef)(ppv);
      ATL::CComQIPtr<_ISpSMLBuilder,&__s_GUID const _GUID_3c0d6362_cdc7_4ee6_b30e_6a065d3b0367>::CComQIPtr<_ISpSMLBuilder,&__s_GUID const _GUID_3c0d6362_cdc7_4ee6_b30e_6a065d3b0367>(
        v15,
        a2);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v15[0] + 192LL))(v15[0], 1);
      Win32Error = -2147024638;
      ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v15);
      goto LABEL_20;
    }
  }
  if ( v11 == -1 )
  {
    Win32Error = SpHrFromLastWin32Error();
    if ( Win32Error < 0 )
      goto LABEL_27;
  }
  else if ( v11 )
  {
    if ( v11 != 258 )
    {
      Win32Error = -2147418113;
      goto LABEL_27;
    }
    goto LABEL_19;
  }
LABEL_20:
  if ( WaitForSingleObject(EventW, 0xFFFFFFFF) != -1 )
    goto LABEL_23;
  if ( Win32Error < 0 )
  {
LABEL_27:
    DoTraceMessage(4, "Semantic interpretation failed, hr = 0x%X", Win32Error);
    goto LABEL_28;
  }
  Win32Error = SpHrFromLastWin32Error();
LABEL_23:
  if ( Win32Error < 0 )
    goto LABEL_27;
  v12 = *((_DWORD *)this + 254);
  if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147200921 )
  {
    Win32Error = *((_DWORD *)this + 254);
    goto LABEL_27;
  }
LABEL_28:
  if ( EventW )
    CloseHandle(EventW);
  *((_QWORD *)this + 124) = 0;
  *((_DWORD *)this + 250) = 0;
  v13 = *((_QWORD *)this + 126);
  if ( v13 )
  {
    *((_QWORD *)this + 126) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *((_DWORD *)this + 254) = 0;
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18012f1a0  mov     [rsp-28h+arg_8], rbx
0x18012f1a5  mov     [rsp-28h+arg_10], rsi
0x18012f1aa  push    rbp
0x18012f1ab  push    rdi
0x18012f1ac  push    r13
0x18012f1ae  push    r14
0x18012f1b0  push    r15
0x18012f1b2  mov     rbp, rsp
0x18012f1b5  sub     rsp, 50h
0x18012f1b9  mov     edi, r8d
0x18012f1bc  mov     r15, rdx
0x18012f1bf  mov     rsi, rcx
0x18012f1c2  xor     ebx, ebx
0x18012f1c4  mov     [rbp+arg_0], ebx
0x18012f1c7  xor     r9d, r9d; lpName
0x18012f1ca  xor     r8d, r8d; bInitialState
0x18012f1cd  lea     edx, [rbx+1]; bManualReset
0x18012f1d0  xor     ecx, ecx; lpEventAttributes
0x18012f1d2  call    cs:__imp_CreateEventW
0x18012f1d8  mov     r14, rax
0x18012f1db  test    rax, rax
0x18012f1de  jnz     short loc_18012F1E7
0x18012f1e0  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18012f1e5  mov     ebx, eax
0x18012f1e7  mov     [rbp+arg_18], 0
0x18012f1ef  test    ebx, ebx
0x18012f1f1  js      loc_18012F3A7
0x18012f1f7  lea     rax, [rbp+arg_18]
0x18012f1fb  lea     r9, _GUID_c073e8bd_00b7_4c20_99af_daadadcacdab; riid
0x18012f202  xor     edx, edx; pUnkOuter
0x18012f204  lea     r8d, [rdx+17h]; dwClsContext
0x18012f208  mov     [rsp+50h+ppv], rax; ppv
0x18012f20d  test    edi, edi
0x18012f20f  lea     rcx, CLSID_SpW3CSemanticInterpretation
0x18012f216  jnz     short loc_18012F21F
0x18012f218  lea     rcx, CLSID_SpMSSemanticInterpretation; rclsid
0x18012f21f  call    cs:__imp_CoCreateInstance
0x18012f225  mov     ebx, eax
0x18012f227  test    eax, eax
0x18012f229  js      loc_18012F3A7
0x18012f22f  mov     [rsi+3E0h], r15
0x18012f236  lea     rcx, [rsi+3F0h]; struct IUnknown **
0x18012f23d  mov     rdx, [rbp+arg_18]; struct IUnknown *
0x18012f241  cmp     [rcx], rdx
0x18012f244  jz      short loc_18012F24B
0x18012f246  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18012f24b  lea     rdx, aQueueASemantic; "Queue a semantic interpretation task"
0x18012f252  mov     ecx, 10h; int
0x18012f257  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18012f25c  mov     rcx, [rsi+2F8h]
0x18012f263  mov     r9, [rcx]
0x18012f266  lea     r10, [rsi+68h]
0x18012f26a  mov     rax, rsi
0x18012f26d  lea     r8, [rsi+10h]
0x18012f271  neg     rax
0x18012f274  sbb     rdx, rdx
0x18012f277  and     rdx, r8
0x18012f27a  mov     rax, [r9+28h]
0x18012f27e  lea     r8, [rbp+arg_0]
0x18012f282  mov     [rsp+50h+var_28], r8
0x18012f287  mov     [rsp+50h+ppv], r10
0x18012f28c  mov     r9, r14
0x18012f28f  lea     r8, ?SMLId@CRecoMaster@@2W4CompletionPortTaskId@1@B; CRecoMaster::CompletionPortTaskId const CRecoMaster::SMLId
0x18012f296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f29b  mov     ebx, eax
0x18012f29d  test    eax, eax
0x18012f29f  js      loc_18012F3A7
0x18012f2a5  mov     rcx, [rbp+arg_18]
0x18012f2a9  mov     rax, [rcx]
0x18012f2ac  mov     rax, [rax+28h]
0x18012f2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f2b5  mov     rcx, rax; hHandle
0x18012f2b8  mov     edx, 0EA60h; dwMilliseconds
0x18012f2bd  call    cs:__imp_WaitForSingleObject
0x18012f2c3  mov     edi, eax
0x18012f2c5  mov     r13d, 102h
0x18012f2cb  cmp     eax, r13d
0x18012f2ce  jnz     short loc_18012F2E3
0x18012f2d0  lea     rdx, aJscriptEngineI; "jscript engine initialization has timed"...
0x18012f2d7  mov     ecx, 10h; int
0x18012f2dc  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18012f2e1  jmp     short loc_18012F327
0x18012f2e3  test    eax, eax
0x18012f2e5  jnz     short loc_18012F30A
0x18012f2e7  imul    edx, [rsi+400h], 3E8h; dwMilliseconds
0x18012f2f1  mov     rcx, r14; hHandle
0x18012f2f4  call    cs:__imp_WaitForSingleObject
0x18012f2fa  mov     edi, eax
0x18012f2fc  cmp     eax, r13d
0x18012f2ff  jnz     short loc_18012F30A
0x18012f301  lea     rdx, aExecutionOfJsc; "execution of jscript has timed out"
0x18012f308  jmp     short loc_18012F2D7
0x18012f30a  cmp     edi, 0FFFFFFFFh
0x18012f30d  jnz     loc_18012F430
0x18012f313  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18012f318  mov     ebx, eax
0x18012f31a  test    eax, eax
0x18012f31c  js      loc_18012F3A7
0x18012f322  cmp     edi, r13d
0x18012f325  jnz     short loc_18012F36A
0x18012f327  mov     rcx, [rbp+arg_18]
0x18012f32b  mov     rax, [rcx]
0x18012f32e  mov     rax, [rax+20h]
0x18012f332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f337  mov     rdx, r15
0x18012f33a  lea     rcx, [rbp+var_10]
0x18012f33e  call    ??0?$CComQIPtr@U_ISpSMLBuilder@@$1?_GUID_3c0d6362_cdc7_4ee6_b30e_6a065d3b0367@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<_ISpSMLBuilder,&__s_GUID const _GUID_3c0d6362_cdc7_4ee6_b30e_6a065d3b0367>::CComQIPtr<_ISpSMLBuilder,&__s_GUID const _GUID_3c0d6362_cdc7_4ee6_b30e_6a065d3b0367>(IUnknown *)
0x18012f343  nop
0x18012f344  mov     rcx, [rbp+var_10]
0x18012f348  mov     rax, [rcx]
0x18012f34b  mov     edx, 1
0x18012f350  mov     rax, [rax+0C0h]
0x18012f357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f35c  mov     ebx, 80070102h
0x18012f361  lea     rcx, [rbp+var_10]
0x18012f365  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18012f36a  or      edi, 0FFFFFFFFh
0x18012f36d  mov     edx, edi; dwMilliseconds
0x18012f36f  mov     rcx, r14; hHandle
0x18012f372  call    cs:__imp_WaitForSingleObject
0x18012f378  cmp     eax, edi
0x18012f37a  jnz     short loc_18012F387
0x18012f37c  test    ebx, ebx
0x18012f37e  js      short loc_18012F3A7
0x18012f380  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18012f385  mov     ebx, eax
0x18012f387  test    ebx, ebx
0x18012f389  js      short loc_18012F3A7
0x18012f38b  mov     ecx, [rsi+3F8h]
0x18012f391  mov     edx, 80000000h
0x18012f396  lea     eax, [rcx+rdx]
0x18012f399  test    edx, eax
0x18012f39b  jnz     short loc_18012F3BB
0x18012f39d  cmp     ecx, 80045067h
0x18012f3a3  jz      short loc_18012F3BB
0x18012f3a5  mov     ebx, ecx
0x18012f3a7  mov     r8d, ebx
0x18012f3aa  lea     rdx, aSemanticInterp_0; "Semantic interpretation failed, hr = 0x"...
0x18012f3b1  mov     ecx, 4; int
0x18012f3b6  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x18012f3bb  test    r14, r14
0x18012f3be  jz      short loc_18012F3C9
0x18012f3c0  mov     rcx, r14; hObject
0x18012f3c3  call    cs:__imp_CloseHandle
0x18012f3c9  mov     qword ptr [rsi+3E0h], 0
0x18012f3d4  mov     dword ptr [rsi+3E8h], 0
0x18012f3de  mov     rcx, [rsi+3F0h]
0x18012f3e5  test    rcx, rcx
0x18012f3e8  jz      short loc_18012F402
0x18012f3ea  mov     qword ptr [rsi+3F0h], 0
0x18012f3f5  mov     rax, [rcx]
0x18012f3f8  mov     rax, [rax+10h]
0x18012f3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012f401  nop
0x18012f402  mov     dword ptr [rsi+3F8h], 0
0x18012f40c  lea     rcx, [rbp+arg_18]
0x18012f410  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x18012f415  mov     eax, ebx
0x18012f417  lea     r11, [rsp+50h+var_s0]
0x18012f41c  mov     rbx, [r11+38h]
0x18012f420  mov     rsi, [r11+40h]
0x18012f424  mov     rsp, r11
0x18012f427  pop     r15
0x18012f429  pop     r14
0x18012f42b  pop     r13
0x18012f42d  pop     rdi
0x18012f42e  pop     rbp
0x18012f42f  retn
0x18012f430  test    edi, edi
0x18012f432  jz      loc_18012F322
0x18012f438  cmp     edi, r13d
0x18012f43b  jz      loc_18012F327
0x18012f441  mov     ebx, 8000FFFFh
0x18012f446  jmp     loc_18012F3A7
```
