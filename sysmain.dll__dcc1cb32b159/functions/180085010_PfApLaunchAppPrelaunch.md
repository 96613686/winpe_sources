# PfApLaunchAppPrelaunch

- ea: `0x180085010`
- end: `0x180085216`
- name: `PfApLaunchAppPrelaunch`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180079fb0`

## callees

- `0x18004ff64`
- `0x180056fa4`
- `0x180084f6c`
- `0x180085010`
- `0x1800b64c0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800850b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800850b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800851c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800851c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800850ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800850ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180085097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180085097`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800850f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800850f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800851e7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800851e7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180085069`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180085069`

## pseudocode

```c
__int64 __fastcall PfApLaunchAppPrelaunch(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  int v6; // r15d
  int v9; // ebx
  HANDLE CurrentThread; // rax
  signed int AppUserModelId; // eax
  bool v12; // cc
  __int64 v13; // rdx
  __int64 v14; // r9
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  unsigned int TokenInformation; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v18[2]; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+4Ch] [rbp-B4h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[272]; // [rsp+60h] [rbp-A0h] BYREF

  TokenInformation = 0;
  v18[0] = 0;
  v19 = 0;
  TokenHandle = 0;
  v6 = 0;
  v21 = 0;
  v9 = CoInitializeEx(0, 0);
  if ( v9 < 0 )
    goto LABEL_18;
  v6 = 1;
  if ( a4 )
  {
    v9 = PfApLaunchAppDebugModeControl(a1, a3, 0);
    goto LABEL_18;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle)
    && GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, v18) )
  {
    v13 = -1;
    v18[1] = 130;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(a2 + 2 * v14) );
    do
      ++v13;
    while ( *(_WORD *)(a1 + 2 * v13) );
    ReturnLength = (PDWORD)v22;
    AppUserModelId = PfsGetAppUserModelId(a1, v13, a2);
    v9 = AppUserModelId;
    v12 = AppUserModelId <= 0;
    if ( !AppUserModelId )
    {
      AppUserModelId = ConnectToPreLauncherInSession(TokenInformation, &v21);
      v9 = AppUserModelId;
      v12 = AppUserModelId <= 0;
      if ( !AppUserModelId )
      {
        v9 = PfApLaunchAppDebugModeControl(a1, a3, 1);
        if ( v9 >= 0 )
        {
          LODWORD(ReturnLength) = 2;
          v9 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, PDWORD, int *))(*(_QWORD *)v21 + 24LL))(
                 v21,
                 v22,
                 0,
                 0,
                 ReturnLength,
                 &v19);
          if ( v9 >= 0 )
            v9 = 0;
          else
            PfApLaunchAppDebugModeControl(a1, a3, 0);
        }
        goto LABEL_18;
      }
    }
  }
  else
  {
    AppUserModelId = GetLastError();
    v9 = AppUserModelId;
    v12 = AppUserModelId <= 0;
  }
  if ( !v12 )
    v9 = (unsigned __int16)AppUserModelId | 0x80070000;
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v6 )
    CoUninitialize();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180085010  mov     [rsp-8+arg_18], rbx
0x180085015  push    rbp
0x180085016  push    rsi
0x180085017  push    rdi
0x180085018  push    r12
0x18008501a  push    r13
0x18008501c  push    r14
0x18008501e  push    r15
0x180085020  lea     rbp, [rsp-80h]
0x180085025  sub     rsp, 180h
0x18008502c  mov     rax, cs:__security_cookie
0x180085033  xor     rax, rsp
0x180085036  mov     [rbp+0B0h+var_40], rax
0x18008503a  xor     r13d, r13d
0x18008503d  mov     r12, rdx
0x180085040  mov     rdi, rcx
0x180085043  mov     [rsp+1B0h+TokenInformation], r13d
0x180085048  xor     edx, edx; dwCoInit
0x18008504a  mov     [rsp+1B0h+var_16C], r13d
0x18008504f  xor     ecx, ecx; pvReserved
0x180085051  mov     [rsp+1B0h+var_164], r13d
0x180085056  mov     [rsp+1B0h+TokenHandle], r13
0x18008505b  mov     r15d, r13d
0x18008505e  mov     [rsp+1B0h+var_158], r13
0x180085063  mov     r14d, r9d
0x180085066  mov     rsi, r8
0x180085069  call    cs:__imp_CoInitializeEx
0x18008506f  mov     ebx, eax
0x180085071  test    eax, eax
0x180085073  js      loc_1800851BC
0x180085079  lea     r15d, [r13+1]
0x18008507d  test    r14d, r14d
0x180085080  jz      short loc_180085097
0x180085082  xor     r8d, r8d
0x180085085  mov     rdx, rsi
0x180085088  mov     rcx, rdi
0x18008508b  call    PfApLaunchAppDebugModeControl
0x180085090  mov     ebx, eax
0x180085092  jmp     loc_1800851BC
0x180085097  call    cs:__imp_GetCurrentThread
0x18008509d  lea     r9, [rsp+1B0h+TokenHandle]; TokenHandle
0x1800850a2  xor     r8d, r8d; OpenAsSelf
0x1800850a5  mov     rcx, rax; ThreadHandle
0x1800850a8  mov     edx, 20008h; DesiredAccess
0x1800850ad  call    cs:__imp_OpenThreadToken
0x1800850b3  test    eax, eax
0x1800850b5  jnz     short loc_1800850D5
0x1800850b7  call    cs:__imp_GetLastError
0x1800850bd  mov     ebx, eax
0x1800850bf  test    eax, eax
0x1800850c1  jle     loc_1800851BC
0x1800850c7  movzx   ebx, ax
0x1800850ca  or      ebx, 80070000h
0x1800850d0  jmp     loc_1800851BC
0x1800850d5  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x1800850da  lea     rax, [rsp+1B0h+var_16C]
0x1800850df  mov     r9d, 4; TokenInformationLength
0x1800850e5  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x1800850ea  lea     r8, [rsp+1B0h+TokenInformation]; TokenInformation
0x1800850ef  lea     edx, [r9+8]; TokenInformationClass
0x1800850f3  call    cs:__imp_GetTokenInformation
0x1800850f9  test    eax, eax
0x1800850fb  jz      short loc_1800850B7
0x1800850fd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180085101  mov     [rsp+1B0h+var_168], 82h
0x180085109  mov     r9, rdx
0x18008510c  inc     r9
0x18008510f  cmp     [r12+r9*2], r13w
0x180085114  jnz     short loc_18008510C
0x180085116  inc     rdx
0x180085119  cmp     [rdi+rdx*2], r13w
0x18008511e  jnz     short loc_180085116
0x180085120  lea     rax, [rsp+1B0h+var_168]
0x180085125  mov     r8, r12
0x180085128  mov     [rsp+1B0h+var_188], rax
0x18008512d  mov     rcx, rdi
0x180085130  lea     rax, [rsp+1B0h+var_150]
0x180085135  mov     [rsp+1B0h+ReturnLength], rax
0x18008513a  call    PfsGetAppUserModelId
0x18008513f  mov     ebx, eax
0x180085141  test    eax, eax
0x180085143  jnz     loc_1800850C1
0x180085149  mov     ecx, [rsp+1B0h+TokenInformation]
0x18008514d  lea     rdx, [rsp+1B0h+var_158]
0x180085152  call    ConnectToPreLauncherInSession
0x180085157  mov     ebx, eax
0x180085159  test    eax, eax
0x18008515b  jnz     loc_1800850C1
0x180085161  mov     r8d, r15d
0x180085164  mov     rdx, rsi
0x180085167  mov     rcx, rdi
0x18008516a  call    PfApLaunchAppDebugModeControl
0x18008516f  mov     ebx, eax
0x180085171  test    eax, eax
0x180085173  js      short loc_1800851BC
0x180085175  mov     rcx, [rsp+1B0h+var_158]
0x18008517a  lea     rdx, [rsp+1B0h+var_164]
0x18008517f  mov     [rsp+1B0h+var_188], rdx
0x180085184  xor     r9d, r9d
0x180085187  xor     r8d, r8d
0x18008518a  mov     dword ptr [rsp+1B0h+ReturnLength], 2
0x180085192  lea     rdx, [rsp+1B0h+var_150]
0x180085197  mov     rax, [rcx]
0x18008519a  mov     rax, [rax+18h]
0x18008519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800851a3  mov     ebx, eax
0x1800851a5  test    eax, eax
0x1800851a7  jns     short loc_1800851B9
0x1800851a9  xor     r8d, r8d
0x1800851ac  mov     rdx, rsi
0x1800851af  mov     rcx, rdi
0x1800851b2  call    PfApLaunchAppDebugModeControl
0x1800851b7  jmp     short loc_1800851BC
0x1800851b9  mov     ebx, r13d
0x1800851bc  mov     rcx, [rsp+1B0h+TokenHandle]; hObject
0x1800851c1  test    rcx, rcx
0x1800851c4  jz      short loc_1800851CC
0x1800851c6  call    cs:__imp_CloseHandle
0x1800851cc  mov     rcx, [rsp+1B0h+var_158]
0x1800851d1  test    rcx, rcx
0x1800851d4  jz      short loc_1800851E2
0x1800851d6  mov     rax, [rcx]
0x1800851d9  mov     rax, [rax+10h]
0x1800851dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800851e2  test    r15d, r15d
0x1800851e5  jz      short loc_1800851ED
0x1800851e7  call    cs:__imp_CoUninitialize
0x1800851ed  mov     eax, ebx
0x1800851ef  mov     rcx, [rbp+0B0h+var_40]
0x1800851f3  xor     rcx, rsp; StackCookie
0x1800851f6  call    __security_check_cookie
0x1800851fb  mov     rbx, [rsp+1B0h+arg_18]
0x180085203  add     rsp, 180h
0x18008520a  pop     r15
0x18008520c  pop     r14
0x18008520e  pop     r13
0x180085210  pop     r12
0x180085212  pop     rdi
0x180085213  pop     rsi
0x180085214  pop     rbp
0x180085215  retn
```
