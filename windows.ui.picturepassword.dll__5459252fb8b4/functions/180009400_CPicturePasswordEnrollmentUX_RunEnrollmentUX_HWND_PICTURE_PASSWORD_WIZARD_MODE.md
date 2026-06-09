# CPicturePasswordEnrollmentUX::RunEnrollmentUX(HWND__ *,PICTURE_PASSWORD_WIZARD_MODE)

- ea: `0x180009400`
- end: `0x180009517`
- name: `?RunEnrollmentUX@CPicturePasswordEnrollmentUX@@UEAAJPEAUHWND__@@W4PICTURE_PASSWORD_WIZARD_MODE@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(__int64, HWND, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002610`
- `0x1800057ac`
- `0x180005d10`
- `0x180005db8`
- `0x180009400`
- `0x180009b6c`
- `0x180009d00`
- `0x180010fd0`

## import_xrefs

- `DUI70!UnInitThread` at `0x1800094bd`
- `DUI70!UnInitThread` at `0x1800094bd`
- `DUI70!UnInitProcessPriv` at `0x1800094ca`
- `DUI70!UnInitProcessPriv` at `0x1800094ca`
- `DUI70!InitThread` at `0x1800094a5`
- `DUI70!InitThread` at `0x1800094a5`
- `DUI70!InitProcessPriv` at `0x180009494`
- `DUI70!InitProcessPriv` at `0x180009494`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowEnabled` at `0x180009463`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowEnabled` at `0x180009463`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnableWindow` at `0x180009472`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnableWindow` at `0x180009472`

## pseudocode

```c
__int64 __fastcall CPicturePasswordEnrollmentUX::RunEnrollmentUX(__int64 a1, HWND a2, unsigned int a3)
{
  __int64 v5; // r8
  int inited; // ebx
  _QWORD v8[2]; // [rsp+30h] [rbp-188h] BYREF
  char v9; // [rsp+40h] [rbp-178h]
  _QWORD v10[42]; // [rsp+50h] [rbp-168h] BYREF

  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v10);
  v10[0] = &PicturePasswordTelemetry::RunEnrollmentUX::`vftable';
  PicturePasswordTelemetry::RunEnrollmentUX::StartActivity((PicturePasswordTelemetry::RunEnrollmentUX *)v10);
  v8[1] = a2;
  v8[0] = &CAutoDisableWindow::`vftable';
  v9 = 0;
  if ( IsWindowEnabled(a2) )
  {
    EnableWindow(a2, 0);
    v9 = 1;
  }
  LOBYTE(v5) = 1;
  inited = InitProcessPriv(14, &_ImageBase, v5);
  if ( inited >= 0 )
  {
    inited = InitThread(65538);
    if ( inited >= 0 )
    {
      inited = RunPicturePasswordEnrollmentUX(a2, a3);
      UnInitThread();
    }
    UnInitProcessPriv(&_ImageBase);
  }
  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v10,
    (unsigned int)inited);
  CAutoDisableWindow::~CAutoDisableWindow((CAutoDisableWindow *)v8);
  PicturePasswordTelemetry::RunEnrollmentUX::~RunEnrollmentUX((PicturePasswordTelemetry::RunEnrollmentUX *)v10);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180009400  mov     [rsp+arg_0], rbx
0x180009405  mov     [rsp+arg_18], rsi
0x18000940a  push    rdi
0x18000940b  sub     rsp, 1B0h
0x180009412  mov     rax, cs:__security_cookie
0x180009419  xor     rax, rsp
0x18000941c  mov     [rsp+1B8h+var_18], rax
0x180009424  lea     rcx, [rsp+1B8h+var_168]; struct wil::details::IFailureCallback *
0x180009429  mov     esi, r8d
0x18000942c  mov     rdi, rdx
0x18000942f  call    ??0?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180009434  lea     rax, ??_7RunEnrollmentUX@PicturePasswordTelemetry@@6B@; const PicturePasswordTelemetry::RunEnrollmentUX::`vftable'
0x18000943b  lea     rcx, [rsp+1B8h+var_168]; this
0x180009440  mov     [rsp+1B8h+var_168], rax
0x180009445  call    ?StartActivity@RunEnrollmentUX@PicturePasswordTelemetry@@QEAAXXZ; PicturePasswordTelemetry::RunEnrollmentUX::StartActivity(void)
0x18000944a  lea     rax, ??_7CAutoDisableWindow@@6B@; const CAutoDisableWindow::`vftable'
0x180009451  mov     [rsp+1B8h+var_180], rdi
0x180009456  mov     rcx, rdi; hWnd
0x180009459  mov     [rsp+1B8h+var_188], rax
0x18000945e  mov     [rsp+1B8h+var_178], 0
0x180009463  call    cs:__imp_IsWindowEnabled
0x180009469  test    eax, eax
0x18000946b  jz      short loc_18000947D
0x18000946d  xor     edx, edx; bEnable
0x18000946f  mov     rcx, rdi; hWnd
0x180009472  call    cs:__imp_EnableWindow
0x180009478  mov     [rsp+1B8h+var_178], 1
0x18000947d  mov     r9b, 1
0x180009480  mov     [rsp+1B8h+var_198], 1
0x180009485  mov     r8b, r9b
0x180009488  lea     rdx, __ImageBase
0x18000948f  mov     ecx, 0Eh
0x180009494  call    cs:__imp_InitProcessPriv
0x18000949a  mov     ebx, eax
0x18000949c  test    eax, eax
0x18000949e  js      short loc_1800094D0
0x1800094a0  mov     ecx, 10002h
0x1800094a5  call    cs:__imp_InitThread
0x1800094ab  mov     ebx, eax
0x1800094ad  test    eax, eax
0x1800094af  js      short loc_1800094C3
0x1800094b1  mov     edx, esi
0x1800094b3  mov     rcx, rdi
0x1800094b6  call    ?RunPicturePasswordEnrollmentUX@@YAJPEAUHWND__@@W4PICTURE_PASSWORD_WIZARD_MODE@@@Z; RunPicturePasswordEnrollmentUX(HWND__ *,PICTURE_PASSWORD_WIZARD_MODE)
0x1800094bb  mov     ebx, eax
0x1800094bd  call    cs:__imp_UnInitThread
0x1800094c3  lea     rcx, __ImageBase
0x1800094ca  call    cs:__imp_UnInitProcessPriv
0x1800094d0  mov     edx, ebx
0x1800094d2  lea     rcx, [rsp+1B8h+var_168]
0x1800094d7  call    ?Stop@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800094dc  lea     rcx, [rsp+1B8h+var_188]; this
0x1800094e1  call    ??1CAutoDisableWindow@@UEAA@XZ; CAutoDisableWindow::~CAutoDisableWindow(void)
0x1800094e6  lea     rcx, [rsp+1B8h+var_168]; this
0x1800094eb  call    ??1RunEnrollmentUX@PicturePasswordTelemetry@@QEAA@XZ; PicturePasswordTelemetry::RunEnrollmentUX::~RunEnrollmentUX(void)
0x1800094f0  mov     eax, ebx
0x1800094f2  mov     rcx, [rsp+1B8h+var_18]
0x1800094fa  xor     rcx, rsp; StackCookie
0x1800094fd  call    __security_check_cookie
0x180009502  lea     r11, [rsp+1B8h+var_8]
0x18000950a  mov     rbx, [r11+10h]
0x18000950e  mov     rsi, [r11+28h]
0x180009512  mov     rsp, r11
0x180009515  pop     rdi
0x180009516  retn
```
