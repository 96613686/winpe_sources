# SHRemoveWindowSubclass

- ea: `0x18008f240`
- end: `0x18008f39d`
- name: `SHRemoveWindowSubclass`
- size: `349`
- prototype: `__int64 __fastcall(HWND, void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180039de4`
- `0x18005b98c`
- `0x180066910`
- `0x18008d42c`
- `0x18008d458`
- `0x18008d828`
- `0x18008e1a0`
- `0x18008e518`
- `0x18008f240`
- `0x18009313c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f2de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008f2de`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18008f274`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18008f2bb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18008f274`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18008f2bb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18008f2f8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x18008f2f8`

## string_xrefs

- `0x18008f27c`: `SHRemoveWindowSubclass`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall SHRemoveWindowSubclass(HWND a1, void *a2, unsigned __int64 a3)
{
  int v6; // edi
  BOOL v7; // ebx
  bool v8; // di
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  struct SUBCLASS_HEADER *PropW; // rax
  struct SUBCLASS_HEADER *v12; // rbx
  struct SUBCLASS_CALL *v13; // rax
  __int64 v14; // rdx
  _QWORD v16[42]; // [rsp+30h] [rbp-188h] BYREF

  v6 = (unsigned __int8)IsWindowOnCurrentThread(a1);
  v7 = IsWindow(a1);
  wil::ActivityBase<SHCoreLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SHCoreLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v16);
  v16[0] = &SHCoreTelemetry::SHRemoveWindowSubclass::`vftable';
  SHCoreTelemetry::SHRemoveWindowSubclass::StartActivity(
    (SHCoreTelemetry::SHRemoveWindowSubclass *)v16,
    a1,
    a2,
    a3,
    v7,
    v6);
  v8 = 0;
  if ( IsWindow(a1) && a2 )
  {
    if ( !IsWindowOnCurrentThread(a1) )
    {
      CurrentThreadId = GetCurrentThreadId();
      MicrosoftTelemetryAssertTriggeredArgs(v10, (unsigned int)a1, CurrentThreadId);
    }
    PropW = (struct SUBCLASS_HEADER *)GetPropW(a1, L"SHCore.Subclass.Data");
    v12 = PropW;
    if ( PropW )
    {
      v13 = FindCallRecord(
              PropW,
              (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64))a2,
              a3);
      if ( v13 )
      {
        *(_QWORD *)v13 = 0;
        v14 = (v13 - v12 - 24) / 24;
        if ( !*((_DWORD *)v12 + 2) || (unsigned int)v14 < *((_DWORD *)v12 + 2) )
          *((_DWORD *)v12 + 2) = v14;
        v8 = 1;
        CompactSubclassHeader(a1, v12, 1);
      }
    }
  }
  SHCoreTelemetry::SHRemoveWindowSubclass::Stop((SHCoreTelemetry::SHRemoveWindowSubclass *)v16, v8);
  SHCoreTelemetry::SHRemoveWindowSubclass::~SHRemoveWindowSubclass((SHCoreTelemetry::SHRemoveWindowSubclass *)v16);
  return v8;
}

```

## disassembly

```asm
0x18008f240  push    rbx
0x18008f242  push    rbp
0x18008f243  push    rsi
0x18008f244  push    rdi
0x18008f245  push    r14
0x18008f247  sub     rsp, 190h
0x18008f24e  mov     rax, cs:__security_cookie
0x18008f255  xor     rax, rsp
0x18008f258  mov     [rsp+1B8h+var_38], rax
0x18008f260  mov     r14, r8
0x18008f263  mov     rbp, rdx
0x18008f266  mov     rsi, rcx
0x18008f269  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x18008f26e  movzx   edi, al
0x18008f271  mov     rcx, rsi; hWnd
0x18008f274  call    cs:__imp_IsWindow
0x18008f27a  mov     ebx, eax
0x18008f27c  lea     rdx, aShremovewindow; "SHRemoveWindowSubclass"
0x18008f283  lea     rcx, [rsp+1B8h+var_188]; struct wil::details::IFailureCallback *
0x18008f288  call    ??0?$ActivityBase@VSHCoreLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SHCoreLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SHCoreLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18008f28d  lea     rax, ??_7SHRemoveWindowSubclass@SHCoreTelemetry@@6B@; const SHCoreTelemetry::SHRemoveWindowSubclass::`vftable'
0x18008f294  mov     [rsp+1B8h+var_188], rax
0x18008f299  mov     [rsp+1B8h+var_190], edi; int
0x18008f29d  mov     [rsp+1B8h+var_198], ebx; int
0x18008f2a1  mov     r9, r14; unsigned __int64
0x18008f2a4  mov     r8, rbp; void *
0x18008f2a7  mov     rdx, rsi; void *
0x18008f2aa  lea     rcx, [rsp+1B8h+var_188]; this
0x18008f2af  call    ?StartActivity@SHRemoveWindowSubclass@SHCoreTelemetry@@QEAAXPEAX0_KHH@Z; SHCoreTelemetry::SHRemoveWindowSubclass::StartActivity(void *,void *,unsigned __int64,int,int)
0x18008f2b4  nop
0x18008f2b5  xor     dil, dil
0x18008f2b8  mov     rcx, rsi; hWnd
0x18008f2bb  call    cs:__imp_IsWindow
0x18008f2c1  test    eax, eax
0x18008f2c3  jz      loc_18008F364
0x18008f2c9  test    rbp, rbp
0x18008f2cc  jz      loc_18008F364
0x18008f2d2  mov     rcx, rsi; hWnd
0x18008f2d5  call    ?IsWindowOnCurrentThread@@YA_NPEAUHWND__@@@Z; IsWindowOnCurrentThread(HWND__ *)
0x18008f2da  test    al, al
0x18008f2dc  jnz     short loc_18008F2EE
0x18008f2de  call    cs:__imp_GetCurrentThreadId
0x18008f2e4  mov     edx, esi
0x18008f2e6  mov     r8d, eax
0x18008f2e9  call    MicrosoftTelemetryAssertTriggeredArgs
0x18008f2ee  lea     rdx, aShcoreSubclass_5; "SHCore.Subclass.Data"
0x18008f2f5  mov     rcx, rsi; hWnd
0x18008f2f8  call    cs:__imp_GetPropW
0x18008f2fe  mov     rbx, rax
0x18008f301  test    rax, rax
0x18008f304  jz      short loc_18008F364
0x18008f306  mov     r8, r14; unsigned __int64
0x18008f309  mov     rdx, rbp; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64, unsigned __int64, unsigned __int64)
0x18008f30c  mov     rcx, rax; struct SUBCLASS_HEADER *
0x18008f30f  call    ?FindCallRecord@@YAPEAUSUBCLASS_CALL@@PEAUSUBCLASS_HEADER@@P6A_JPEAUHWND__@@I_K_J22@Z2@Z; FindCallRecord(SUBCLASS_HEADER *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64),unsigned __int64)
0x18008f314  mov     rdx, rax
0x18008f317  test    rax, rax
0x18008f31a  jz      short loc_18008F364
0x18008f31c  mov     qword ptr [rax], 0
0x18008f323  sub     rdx, rbx
0x18008f326  sub     rdx, 18h
0x18008f32a  mov     rax, 2AAAAAAAAAAAAAABh
0x18008f334  imul    rdx
0x18008f337  sar     rdx, 2
0x18008f33b  mov     rax, rdx
0x18008f33e  shr     rax, 3Fh
0x18008f342  add     rdx, rax
0x18008f345  cmp     dword ptr [rbx+8], 0
0x18008f349  jz      short loc_18008F350
0x18008f34b  cmp     edx, [rbx+8]
0x18008f34e  jnb     short loc_18008F353
0x18008f350  mov     [rbx+8], edx
0x18008f353  mov     dil, 1
0x18008f356  mov     r8b, dil; bool
0x18008f359  mov     rdx, rbx; struct SUBCLASS_HEADER *
0x18008f35c  mov     rcx, rsi; HWND
0x18008f35f  call    ?CompactSubclassHeader@@YAXPEAUHWND__@@PEAUSUBCLASS_HEADER@@_N@Z; CompactSubclassHeader(HWND__ *,SUBCLASS_HEADER *,bool)
0x18008f364  mov     dl, dil; bool
0x18008f367  lea     rcx, [rsp+1B8h+var_188]; this
0x18008f36c  call    ?Stop@SHRemoveWindowSubclass@SHCoreTelemetry@@QEAAX_N@Z; SHCoreTelemetry::SHRemoveWindowSubclass::Stop(bool)
0x18008f371  lea     rcx, [rsp+1B8h+var_188]; this
0x18008f376  call    ??1SHRemoveWindowSubclass@SHCoreTelemetry@@QEAA@XZ; SHCoreTelemetry::SHRemoveWindowSubclass::~SHRemoveWindowSubclass(void)
0x18008f37b  movzx   eax, dil
0x18008f37f  mov     rcx, [rsp+1B8h+var_38]
0x18008f387  xor     rcx, rsp; StackCookie
0x18008f38a  call    __security_check_cookie
0x18008f38f  add     rsp, 190h
0x18008f396  pop     r14
0x18008f398  pop     rdi
0x18008f399  pop     rsi
0x18008f39a  pop     rbp
0x18008f39b  pop     rbx
0x18008f39c  retn
```
