# _UpdatePicturePasswordLinks(IPicturePasswordTaskHandler *,CPrivateNotificationWindow *)

- ea: `0x18002aa1c`
- end: `0x18002ac1f`
- name: `?_UpdatePicturePasswordLinks@@YAXPEAUIPicturePasswordTaskHandler@@PEAVCPrivateNotificationWindow@@@Z`
- size: `515`
- prototype: `void __fastcall(struct IPicturePasswordTaskHandler *, struct CPrivateNotificationWindow *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800290d0`
- `0x180029180`
- `0x180029450`

## callees

- `0x18002aa1c`
- `0x1800640fc`
- `0x18006ebfc`
- `0x180078010`

## import_xrefs

- `SHELL32!__imp_SHTestTokenMembership` at `0x18002aab9`
- `SHELL32!__imp_SHTestTokenMembership` at `0x18002aab9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aae1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aae1`
- `ntdll!WinSqmSetDWORD` at `0x18002ab1c`
- `ntdll!WinSqmSetDWORD` at `0x18002ab1c`
- `USER32!GetSystemMetrics` at `0x18002aa4e`
- `USER32!GetSystemMetrics` at `0x18002aa58`
- `USER32!GetSystemMetrics` at `0x18002aa4e`
- `USER32!GetSystemMetrics` at `0x18002aa58`
- `USER32!GetAutoRotationState` at `0x18002aa67`
- `USER32!GetAutoRotationState` at `0x18002aa67`

## string_xrefs

- `0x18002ab67`: `idPicturePasswordConfig`

## pseudocode

```c
void __fastcall _UpdatePicturePasswordLinks(
        struct IPicturePasswordTaskHandler *a1,
        struct CPrivateNotificationWindow *a2)
{
  unsigned __int8 v4; // r15
  unsigned __int8 v5; // bp
  unsigned __int8 v6; // r14
  int SystemMetrics; // ebx
  int v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  bool v12; // bl
  tagAR_STATE pState; // [rsp+70h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  pState = AR_ENABLED;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  SystemMetrics = GetSystemMetrics(1);
  if ( GetSystemMetrics(0) < SystemMetrics && (!GetAutoRotationState(&pState) || (pState & 0x10) != 0) )
    goto LABEL_19;
  v8 = VerifyConvenienceLogonMethodAllowed(0);
  if ( v8 < 0 )
  {
    if ( v8 == -2147023636 )
    {
      v5 = 1;
      v6 = 1;
    }
  }
  else
  {
    ppv = a1;
    if ( a1 )
    {
      (*(void (__fastcall **)(struct IPicturePasswordTaskHandler *))(*(_QWORD *)a1 + 8LL))(a1);
      v9 = ppv;
      if ( ppv )
        goto LABEL_10;
    }
    if ( !SHTestTokenMembership(0, 0x222u) )
      CoCreateInstance(&CLSID_PicturePasswordEnrollmentHandler, 0, 1u, &GUID_46aca899_50f6_4a46_a9e3_273705ca4914, &ppv);
    v9 = ppv;
    if ( ppv )
    {
LABEL_10:
      v10 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 24LL))(v9);
      if ( v10 )
      {
        if ( v10 != 1 )
          goto LABEL_15;
        v5 = 1;
        v11 = 0;
      }
      else
      {
        v4 = 1;
        v11 = 1;
      }
      WinSqmSetDWORD(0, 8863, v11);
LABEL_15:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
LABEL_19:
  CPrivateNotificationWindow::PostNotification(a2, 0x401u, v5, (__int64)L"idPicturePasswordSetup");
  CPrivateNotificationWindow::PostNotification(a2, 0x401u, v4, (__int64)L"idPicturePasswordConfig");
  CPrivateNotificationWindow::PostNotification(a2, 0x405u, v4, 0);
  v12 = v5 || v4;
  CPrivateNotificationWindow::PostNotification(a2, 0x401u, v12, (__int64)L"idPicturePassword");
  if ( v12 )
  {
    CPrivateNotificationWindow::PostNotification(a2, 0x401u, v12, (__int64)L"idSignInOptionsGroup");
    if ( v6 )
      CPrivateNotificationWindow::PostNotification(a2, 0x401u, 1u, (__int64)L"idUAMSettingsPageGPRestrictionsText");
    CPrivateNotificationWindow::PostNotification(a2, 0x402u, v6 ^ 1LL, (__int64)L"idPicturePassword");
  }
}

```

## disassembly

```asm
0x18002aa1c  mov     [rsp+arg_0], rbx
0x18002aa21  mov     [rsp+arg_8], rbp
0x18002aa26  push    rsi
0x18002aa27  push    rdi
0x18002aa28  push    r13
0x18002aa2a  push    r14
0x18002aa2c  push    r15
0x18002aa2e  sub     rsp, 30h
0x18002aa32  mov     rdi, rcx
0x18002aa35  mov     [rsp+58h+pState], 0
0x18002aa3d  mov     ecx, 1; nIndex
0x18002aa42  mov     rsi, rdx
0x18002aa45  xor     r15b, r15b
0x18002aa48  xor     bpl, bpl
0x18002aa4b  xor     r14b, r14b
0x18002aa4e  call    cs:__imp_GetSystemMetrics
0x18002aa54  xor     ecx, ecx; nIndex
0x18002aa56  mov     ebx, eax
0x18002aa58  call    cs:__imp_GetSystemMetrics
0x18002aa5e  cmp     eax, ebx
0x18002aa60  jge     short loc_18002AA80
0x18002aa62  lea     rcx, [rsp+58h+pState]; pState
0x18002aa67  call    cs:__imp_GetAutoRotationState
0x18002aa6d  test    eax, eax
0x18002aa6f  jz      loc_18002AB47
0x18002aa75  test    byte ptr [rsp+58h+pState], 10h
0x18002aa7a  jnz     loc_18002AB47
0x18002aa80  xor     ecx, ecx
0x18002aa82  call    ?VerifyConvenienceLogonMethodAllowed@@YAJW4ConvenienceLogonMethod@@@Z; VerifyConvenienceLogonMethodAllowed(ConvenienceLogonMethod)
0x18002aa87  test    eax, eax
0x18002aa89  js      loc_18002AB3A
0x18002aa8f  mov     [rsp+58h+arg_18], rdi
0x18002aa94  test    rdi, rdi
0x18002aa97  jz      short loc_18002AAB2
0x18002aa99  mov     rax, [rdi]
0x18002aa9c  mov     rcx, rdi
0x18002aa9f  mov     rax, [rax+8]
0x18002aaa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaa8  mov     rcx, [rsp+58h+arg_18]
0x18002aaad  test    rcx, rcx
0x18002aab0  jnz     short loc_18002AAF1
0x18002aab2  mov     edx, 222h; ulRID
0x18002aab7  xor     ecx, ecx; hToken
0x18002aab9  call    cs:__imp_SHTestTokenMembership
0x18002aabf  test    eax, eax
0x18002aac1  jnz     short loc_18002AAE7
0x18002aac3  xor     edx, edx; pUnkOuter
0x18002aac5  lea     rax, [rsp+58h+arg_18]
0x18002aaca  lea     r9, _GUID_46aca899_50f6_4a46_a9e3_273705ca4914; riid
0x18002aad1  mov     [rsp+58h+ppv], rax; ppv
0x18002aad6  lea     rcx, CLSID_PicturePasswordEnrollmentHandler; rclsid
0x18002aadd  lea     r8d, [rdx+1]; dwClsContext
0x18002aae1  call    cs:__imp_CoCreateInstance
0x18002aae7  mov     rcx, [rsp+58h+arg_18]
0x18002aaec  test    rcx, rcx
0x18002aaef  jz      short loc_18002AB47
0x18002aaf1  mov     rax, [rcx]
0x18002aaf4  mov     rax, [rax+18h]
0x18002aaf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aafd  test    eax, eax
0x18002aaff  jnz     short loc_18002AB0A
0x18002ab01  mov     r15b, 1
0x18002ab04  lea     r8d, [rax+1]
0x18002ab08  jmp     short loc_18002AB15
0x18002ab0a  cmp     eax, 1
0x18002ab0d  jnz     short loc_18002AB22
0x18002ab0f  mov     bpl, al
0x18002ab12  xor     r8d, r8d
0x18002ab15  mov     edx, 229Fh
0x18002ab1a  xor     ecx, ecx
0x18002ab1c  call    cs:__imp_WinSqmSetDWORD
0x18002ab22  mov     rcx, [rsp+58h+arg_18]
0x18002ab27  test    rcx, rcx
0x18002ab2a  jz      short loc_18002AB47
0x18002ab2c  mov     rax, [rcx]
0x18002ab2f  mov     rax, [rax+10h]
0x18002ab33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab38  jmp     short loc_18002AB47
0x18002ab3a  cmp     eax, 800704ECh
0x18002ab3f  jnz     short loc_18002AB47
0x18002ab41  mov     bpl, 1
0x18002ab44  mov     r14b, bpl
0x18002ab47  mov     r13d, 401h
0x18002ab4d  movzx   r8d, bpl; unsigned __int64
0x18002ab51  mov     edx, r13d; unsigned int
0x18002ab54  lea     r9, aIdpicturepassw_0; "idPicturePasswordSetup"
0x18002ab5b  mov     rcx, rsi; this
0x18002ab5e  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002ab63  movzx   ebx, r15b
0x18002ab67  lea     r9, aIdpicturepassw_1; "idPicturePasswordConfig"
0x18002ab6e  mov     r8d, ebx; unsigned __int64
0x18002ab71  mov     edx, r13d; unsigned int
0x18002ab74  mov     rcx, rsi; this
0x18002ab77  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002ab7c  xor     r9d, r9d; __int64
0x18002ab7f  lea     edx, [r13+4]; unsigned int
0x18002ab83  mov     r8d, ebx; unsigned __int64
0x18002ab86  mov     rcx, rsi; this
0x18002ab89  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002ab8e  test    bpl, bpl
0x18002ab91  jnz     short loc_18002AB9C
0x18002ab93  test    r15b, r15b
0x18002ab96  jnz     short loc_18002AB9C
0x18002ab98  xor     bl, bl
0x18002ab9a  jmp     short loc_18002AB9E
0x18002ab9c  mov     bl, 1
0x18002ab9e  movzx   edi, bl
0x18002aba1  lea     r9, aIdpicturepassw_3; "idPicturePassword"
0x18002aba8  mov     r8d, edi; unsigned __int64
0x18002abab  mov     edx, r13d; unsigned int
0x18002abae  mov     rcx, rsi; this
0x18002abb1  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002abb6  test    bl, bl
0x18002abb8  jz      short loc_18002AC08
0x18002abba  lea     r9, aIdsigninoption; "idSignInOptionsGroup"
0x18002abc1  mov     r8d, edi; unsigned __int64
0x18002abc4  mov     edx, r13d; unsigned int
0x18002abc7  mov     rcx, rsi; this
0x18002abca  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002abcf  test    r14b, r14b
0x18002abd2  jz      short loc_18002ABEC
0x18002abd4  lea     r9, aIduamsettingsp; "idUAMSettingsPageGPRestrictionsText"
0x18002abdb  mov     r8d, 1; unsigned __int64
0x18002abe1  mov     edx, r13d; unsigned int
0x18002abe4  mov     rcx, rsi; this
0x18002abe7  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002abec  movzx   r8d, r14b
0x18002abf0  lea     r9, aIdpicturepassw_3; "idPicturePassword"
0x18002abf7  xor     r8, 1; unsigned __int64
0x18002abfb  mov     edx, 402h; unsigned int
0x18002ac00  mov     rcx, rsi; this
0x18002ac03  call    ?PostNotification@CPrivateNotificationWindow@@QEAA_NI_K_J@Z; CPrivateNotificationWindow::PostNotification(uint,unsigned __int64,__int64)
0x18002ac08  mov     rbx, [rsp+58h+arg_0]
0x18002ac0d  mov     rbp, [rsp+58h+arg_8]
0x18002ac12  add     rsp, 30h
0x18002ac16  pop     r15
0x18002ac18  pop     r14
0x18002ac1a  pop     r13
0x18002ac1c  pop     rdi
0x18002ac1d  pop     rsi
0x18002ac1e  retn
```
