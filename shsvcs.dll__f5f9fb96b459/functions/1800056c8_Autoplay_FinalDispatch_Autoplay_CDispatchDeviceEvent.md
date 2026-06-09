# Autoplay::_FinalDispatch(Autoplay::CDispatchDeviceEvent *)

- ea: `0x1800056c8`
- end: `0x180005996`
- name: `?_FinalDispatch@Autoplay@@YAJPEAVCDispatchDeviceEvent@1@@Z`
- size: `718`
- prototype: `__int64 __fastcall(Autoplay *__hidden this, struct Autoplay::CDispatchDeviceEvent *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180004b50`

## callees

- `0x180003570`
- `0x1800056c8`
- `0x1800059a0`
- `0x180006060`
- `0x1800137e0`
- `0x180013cc0`
- `0x180013f74`
- `0x1800169e0`
- `0x180017bb0`
- `0x180017f0c`
- `0x18001b3f8`
- `0x18001b404`
- `0x180023260`
- `0x18002a494`
- `0x18002e828`
- `0x180032c6a`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800058cf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005752`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005752`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000588b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800058c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000588b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800058c4`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005772`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180005772`

## pseudocode

```c
__int64 __fastcall Autoplay::_FinalDispatch(Autoplay *this, struct Autoplay::CDispatchDeviceEvent *a2)
{
  struct Autoplay::IDeviceProperties *v2; // r14
  HRESULT Token; // ebx
  int v5; // esi
  int DeviceHandlerHelper; // eax
  unsigned int v7; // r8d
  int v8; // eax
  int AlreadyRunningHandlerHelper; // eax
  unsigned int v10; // edx
  PHKEY v11; // rdi
  HANDLE v12; // rax
  __int64 v13; // rcx
  CThreadTaskRegister *v14; // rax
  CThreadTaskRegister *v15; // rbx
  int v16; // edi
  const unsigned __int16 *v18; // [rsp+30h] [rbp-D0h] BYREF
  int *v19; // [rsp+38h] [rbp-C8h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-C0h] BYREF
  void **v21; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  PHKEY Block[18]; // [rsp+60h] [rbp-A0h] BYREF
  struct IRunningObjectTable v25; // [rsp+F0h] [rbp-10h] BYREF

  v2 = (struct Autoplay::IDeviceProperties *)*((_QWORD *)this + 85);
  HIDWORD(v18) = 0;
  (*(void (__fastcall **)(struct Autoplay::IDeviceProperties *, char *))(*(_QWORD *)v2 + 16LL))(v2, (char *)&v18 + 4);
  hToken = 0;
  v21 = &CImpersonateSessionUser::`vftable';
  v23 = HIDWORD(v18);
  Token = CImpersonateSessionUser::_GetToken((CImpersonateSessionUser *)&v21, &hToken);
  if ( Token < 0 )
  {
    v5 = 0;
    goto LABEL_23;
  }
  v5 = 0;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    Token = -2147467259;
LABEL_23:
    v12 = hToken;
    goto LABEL_24;
  }
  LODWORD(v18) = 0;
  ppbc = 0;
  Token = CreateBindCtx(0, &ppbc);
  if ( Token >= 0 )
  {
    v19 = 0;
    Token = ((__int64 (__fastcall *)(LPBC, int **))ppbc->lpVtbl->GetRunningObjectTable)(ppbc, &v19);
    if ( Token >= 0 )
    {
      *(_OWORD *)Block = 0;
      DeviceHandlerHelper = Settings::CHandlerEnum::Init(
                              (Settings::CHandlerEnum *)Block,
                              v2,
                              (const unsigned __int16 *)this + 276);
      Token = DeviceHandlerHelper;
LABEL_9:
      if ( DeviceHandlerHelper >= 0 )
      {
        do
        {
          v8 = Settings::CHandlerFromDeviceHandlerEnum::Next(Block[0], (unsigned __int16 *)&v25, v7);
          Token = v8;
          if ( v8 < 0 )
            break;
          if ( v8 == 1 )
          {
            DeviceHandlerHelper = Settings::CHandlerEnum::_NextDeviceHandlerHelper((Settings::CHandlerEnum *)Block);
            Token = DeviceHandlerHelper;
            if ( DeviceHandlerHelper == 1 )
              break;
            goto LABEL_9;
          }
          AlreadyRunningHandlerHelper = Autoplay::_FindAlreadyRunningHandlerHelper(
                                          (Autoplay *)HIDWORD(v18),
                                          (struct IHWEventHandler *)this + 4,
                                          (const unsigned __int16 *)this + 276,
                                          (const unsigned __int16 *)&v18,
                                          v19,
                                          &v25,
                                          v18);
          v5 = (int)v18;
          Token = AlreadyRunningHandlerHelper;
        }
        while ( !(_DWORD)v18 && AlreadyRunningHandlerHelper >= 0 && AlreadyRunningHandlerHelper != 1 );
      }
      (*(void (__fastcall **)(int *))(*(_QWORD *)v19 + 16LL))(v19);
      v11 = Block[0];
      if ( Block[0] )
      {
        Settings::CHandlerFromDeviceHandlerEnum::Cleanup((Settings::CHandlerFromDeviceHandlerEnum *)Block[0]);
        operator delete(v11);
      }
      if ( Block[1] )
        Settings::CMultiDeviceGroupDeviceHandlerEnum::`scalar deleting destructor'(
          (Settings::CMultiDeviceGroupDeviceHandlerEnum *)Block[1],
          v10);
    }
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  }
  v12 = hToken;
  if ( hToken )
  {
    RevertToSelf();
    CloseHandle(hToken);
    v12 = 0;
    hToken = 0;
  }
LABEL_24:
  v21 = &CImpersonateTokenBased::`vftable';
  if ( v12 )
  {
    RevertToSelf();
    CloseHandle(hToken);
  }
  v13 = *((_QWORD *)this + 85);
  LODWORD(v18) = 0;
  if ( Token < 0 )
    v5 = 0;
  (*(void (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v13 + 16LL))(v13, &v18);
  _GiveAllowForegroundToShell((unsigned int)v18);
  v14 = (CThreadTaskRegister *)operator new(0x4F0u);
  v15 = v14;
  if ( v14 )
  {
    memset_0(v14, 0, 0x4F0u);
    *((_DWORD *)v15 + 2) = 1;
    *(_QWORD *)v15 = &Autoplay::CThreadTaskCreateAndCallEventHandler::`vftable';
    *((_DWORD *)v15 + 4) = -2147418113;
    v16 = CThreadTaskRegister::RegisterWithService(v15);
    if ( v16 >= 0 )
    {
      v16 = Autoplay::CThreadTaskPromptUser::Init(v15, this, v5);
      if ( v16 >= 0 )
        v16 = CThreadTask::Run(v15);
    }
    CRefCounted::Release(v15);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800056c8  push    rbp
0x1800056ca  push    rbx
0x1800056cb  push    rsi
0x1800056cc  push    rdi
0x1800056cd  push    r14
0x1800056cf  push    r15
0x1800056d1  lea     rbp, [rsp-0C8h]
0x1800056d9  sub     rsp, 1C8h
0x1800056e0  mov     rax, cs:__security_cookie
0x1800056e7  xor     rax, rsp
0x1800056ea  mov     [rbp+0F0h+var_40], rax
0x1800056f1  mov     r14, [rcx+2A8h]
0x1800056f8  lea     rdx, [rsp+1F0h+var_1BC]
0x1800056fd  mov     r15, rcx
0x180005700  mov     dword ptr [rsp+1F0h+var_1BC], 0
0x180005708  mov     rcx, r14
0x18000570b  mov     rax, [r14]
0x18000570e  mov     rax, [rax+10h]
0x180005712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005717  lea     rax, ??_7CImpersonateSessionUser@@6B@; const CImpersonateSessionUser::`vftable'
0x18000571e  mov     [rsp+1F0h+hToken], 0
0x180005727  mov     [rsp+1F0h+var_1A8], rax
0x18000572c  lea     rdx, [rsp+1F0h+hToken]; void **
0x180005731  mov     eax, dword ptr [rsp+1F0h+var_1BC]
0x180005735  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18000573a  mov     [rsp+1F0h+var_198], eax
0x18000573e  call    ?_GetToken@CImpersonateSessionUser@@MEAAJPEAPEAX@Z; CImpersonateSessionUser::_GetToken(void * *)
0x180005743  mov     ebx, eax
0x180005745  test    eax, eax
0x180005747  js      loc_1800058AC
0x18000574d  mov     rcx, [rsp+1F0h+hToken]; hToken
0x180005752  call    cs:__imp_ImpersonateLoggedOnUser
0x180005758  xor     esi, esi
0x18000575a  test    eax, eax
0x18000575c  jz      loc_1800058A5
0x180005762  lea     rdx, [rsp+1F0h+ppbc]; ppbc
0x180005767  mov     [rsp+1F0h+var_1C0], esi
0x18000576b  xor     ecx, ecx; reserved
0x18000576d  mov     [rsp+1F0h+ppbc], rsi
0x180005772  call    cs:__imp_CreateBindCtx
0x180005778  mov     ebx, eax
0x18000577a  test    eax, eax
0x18000577c  js      loc_180005881
0x180005782  mov     rcx, [rsp+1F0h+ppbc]
0x180005787  lea     rdx, [rsp+1F0h+var_1BC+4]
0x18000578c  mov     qword ptr [rsp+1F0h+var_1BC+4], rsi
0x180005791  mov     rax, [rcx]
0x180005794  mov     rax, [rax+40h]
0x180005798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000579d  mov     ebx, eax
0x18000579f  test    eax, eax
0x1800057a1  js      loc_180005870
0x1800057a7  xorps   xmm0, xmm0
0x1800057aa  lea     rdi, [r15+228h]
0x1800057b1  mov     r8, rdi; unsigned __int16 *
0x1800057b4  movdqa  xmmword ptr [rsp+1F0h+Block], xmm0
0x1800057ba  mov     rdx, r14; struct Autoplay::IDeviceProperties *
0x1800057bd  lea     rcx, [rsp+1F0h+Block]; this
0x1800057c2  call    ?Init@CHandlerEnum@Settings@@QEAAJPEAVIDeviceProperties@Autoplay@@PEBG@Z; Settings::CHandlerEnum::Init(Autoplay::IDeviceProperties *,ushort const *)
0x1800057c7  mov     ebx, eax
0x1800057c9  jmp     short loc_1800057F5
0x1800057cb  mov     rcx, [rsp+1F0h+Block]; phkResult
0x1800057d0  lea     rdx, [rbp+0F0h+var_100]; unsigned __int16 *
0x1800057d4  call    ?Next@CHandlerFromDeviceHandlerEnum@Settings@@QEAAJPEAGK@Z; Settings::CHandlerFromDeviceHandlerEnum::Next(ushort *,ulong)
0x1800057d9  mov     ebx, eax
0x1800057db  test    eax, eax
0x1800057dd  js      short loc_180005836
0x1800057df  cmp     eax, 1
0x1800057e2  jnz     short loc_1800057FB
0x1800057e4  lea     rcx, [rsp+1F0h+Block]; this
0x1800057e9  call    ?_NextDeviceHandlerHelper@CHandlerEnum@Settings@@AEAAJXZ; Settings::CHandlerEnum::_NextDeviceHandlerHelper(void)
0x1800057ee  mov     ebx, eax
0x1800057f0  cmp     eax, 1
0x1800057f3  jz      short loc_180005836
0x1800057f5  test    eax, eax
0x1800057f7  jns     short loc_1800057CB
0x1800057f9  jmp     short loc_180005836
0x1800057fb  mov     ecx, dword ptr [rsp+1F0h+var_1BC]; this
0x1800057ff  lea     rax, [rbp+0F0h+var_100]
0x180005803  mov     [rsp+1F0h+var_1C8], rax; struct IRunningObjectTable *
0x180005808  lea     rdx, [r15+20h]; struct IHWEventHandler *
0x18000580c  mov     rax, qword ptr [rsp+1F0h+var_1BC+4]
0x180005811  lea     r9, [rsp+1F0h+var_1C0]; unsigned __int16 *
0x180005816  mov     r8, rdi; unsigned __int16 *
0x180005819  mov     [rsp+1F0h+var_1D0], rax; int *
0x18000581e  call    ?_FindAlreadyRunningHandlerHelper@Autoplay@@YAJKPEBG0PEAHPEAUIRunningObjectTable@@0@Z; Autoplay::_FindAlreadyRunningHandlerHelper(ulong,ushort const *,ushort const *,int *,IRunningObjectTable *,ushort const *)
0x180005823  mov     esi, [rsp+1F0h+var_1C0]
0x180005827  mov     ebx, eax
0x180005829  test    esi, esi
0x18000582b  jnz     short loc_180005836
0x18000582d  test    eax, eax
0x18000582f  js      short loc_180005836
0x180005831  cmp     eax, 1
0x180005834  jnz     short loc_1800057CB
0x180005836  mov     rcx, qword ptr [rsp+1F0h+var_1BC+4]
0x18000583b  mov     rax, [rcx]
0x18000583e  mov     rax, [rax+10h]
0x180005842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005847  mov     rdi, [rsp+1F0h+Block]
0x18000584c  test    rdi, rdi
0x18000584f  jz      short loc_180005861
0x180005851  mov     rcx, rdi; this
0x180005854  call    ?Cleanup@CHandlerFromDeviceHandlerEnum@Settings@@QEAAJXZ; Settings::CHandlerFromDeviceHandlerEnum::Cleanup(void)
0x180005859  mov     rcx, rdi; Block
0x18000585c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005861  mov     rcx, [rsp+1F0h+Block+8]; this
0x180005866  test    rcx, rcx
0x180005869  jz      short loc_180005870
0x18000586b  call    ??_GCMultiDeviceGroupDeviceHandlerEnum@Settings@@QEAAPEAXI@Z; Settings::CMultiDeviceGroupDeviceHandlerEnum::`scalar deleting destructor'(uint)
0x180005870  mov     rcx, [rsp+1F0h+ppbc]
0x180005875  mov     rax, [rcx]
0x180005878  mov     rax, [rax+10h]
0x18000587c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005881  mov     rax, [rsp+1F0h+hToken]
0x180005886  test    rax, rax
0x180005889  jz      short loc_1800058B3
0x18000588b  call    cs:__imp_RevertToSelf
0x180005891  mov     rcx, [rsp+1F0h+hToken]; hObject
0x180005896  call    cs:__imp_CloseHandle
0x18000589c  xor     eax, eax
0x18000589e  mov     [rsp+1F0h+hToken], rax
0x1800058a3  jmp     short loc_1800058B3
0x1800058a5  mov     ebx, 80004005h
0x1800058aa  jmp     short loc_1800058AE
0x1800058ac  xor     esi, esi
0x1800058ae  mov     rax, [rsp+1F0h+hToken]
0x1800058b3  lea     rcx, ??_7CImpersonateTokenBased@@6B@; const CImpersonateTokenBased::`vftable'
0x1800058ba  mov     [rsp+1F0h+var_1A8], rcx
0x1800058bf  test    rax, rax
0x1800058c2  jz      short loc_1800058D5
0x1800058c4  call    cs:__imp_RevertToSelf
0x1800058ca  mov     rcx, [rsp+1F0h+hToken]; hObject
0x1800058cf  call    cs:__imp_CloseHandle
0x1800058d5  mov     rcx, [r15+2A8h]
0x1800058dc  lea     rdx, [rsp+1F0h+var_1C0]
0x1800058e1  xor     eax, eax
0x1800058e3  mov     [rsp+1F0h+var_1C0], eax
0x1800058e7  test    ebx, ebx
0x1800058e9  cmovs   esi, eax
0x1800058ec  mov     rax, [rcx]
0x1800058ef  mov     rax, [rax+10h]
0x1800058f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f8  mov     ecx, [rsp+1F0h+var_1C0]; unsigned int
0x1800058fc  call    ?_GiveAllowForegroundToShell@@YAJK@Z; _GiveAllowForegroundToShell(ulong)
0x180005901  mov     edi, 4F0h
0x180005906  mov     ecx, edi; Size
0x180005908  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000590d  mov     rbx, rax
0x180005910  test    rax, rax
0x180005913  jz      short loc_180005970
0x180005915  mov     r8d, edi; Size
0x180005918  xor     edx, edx; Val
0x18000591a  mov     rcx, rax; void *
0x18000591d  call    memset_0
0x180005922  lea     rax, ??_7CThreadTaskCreateAndCallEventHandler@Autoplay@@6B@; const Autoplay::CThreadTaskCreateAndCallEventHandler::`vftable'
0x180005929  mov     dword ptr [rbx+8], 1
0x180005930  mov     rcx, rbx; this
0x180005933  mov     [rbx], rax
0x180005936  mov     dword ptr [rbx+10h], 8000FFFFh
0x18000593d  call    ?RegisterWithService@CThreadTaskRegister@@QEAAJXZ; CThreadTaskRegister::RegisterWithService(void)
0x180005942  mov     edi, eax
0x180005944  test    eax, eax
0x180005946  js      short loc_180005966
0x180005948  mov     r8d, esi; int
0x18000594b  mov     rdx, r15; struct Autoplay::CDispatchDeviceEvent *
0x18000594e  mov     rcx, rbx; this
0x180005951  call    ?Init@CThreadTaskPromptUser@Autoplay@@QEAAJPEAVCDispatchDeviceEvent@2@H@Z; Autoplay::CThreadTaskPromptUser::Init(Autoplay::CDispatchDeviceEvent *,int)
0x180005956  mov     edi, eax
0x180005958  test    eax, eax
0x18000595a  js      short loc_180005966
0x18000595c  mov     rcx, rbx; Context
0x18000595f  call    ?Run@CThreadTask@@QEAAJXZ; CThreadTask::Run(void)
0x180005964  mov     edi, eax
0x180005966  mov     rcx, rbx; this
0x180005969  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18000596e  jmp     short loc_180005975
0x180005970  mov     edi, 8007000Eh
0x180005975  mov     eax, edi
0x180005977  mov     rcx, [rbp+0F0h+var_40]
0x18000597e  xor     rcx, rsp; StackCookie
0x180005981  call    __security_check_cookie
0x180005986  add     rsp, 1C8h
0x18000598d  pop     r15
0x18000598f  pop     r14
0x180005991  pop     rdi
0x180005992  pop     rsi
0x180005993  pop     rbx
0x180005994  pop     rbp
0x180005995  retn
```
