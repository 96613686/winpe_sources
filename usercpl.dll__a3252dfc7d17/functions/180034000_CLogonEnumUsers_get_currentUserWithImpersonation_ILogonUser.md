# CLogonEnumUsers::get_currentUserWithImpersonation(ILogonUser * *)

- ea: `0x180034000`
- end: `0x1800341f8`
- name: `?get_currentUserWithImpersonation@CLogonEnumUsers@@UEAAJPEAPEAUILogonUser@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(CLogonEnumUsers *__hidden this, struct ILogonUser **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800338b8`
- `0x180034000`
- `0x18006d368`
- `0x18006d53c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034109`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800340d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034109`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800340ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800340ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800340ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800340ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800340ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800340ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800340b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800340b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034199`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034199`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003402f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003402f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003414c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003414c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034171`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034171`

## pseudocode

```c
__int64 __fastcall CLogonEnumUsers::get_currentUserWithImpersonation(CLogonEnumUsers *this, struct ILogonUser **a2)
{
  int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v8; // eax
  bool v9; // sf
  int v10; // eax
  int v11; // ecx
  void *v12; // rcx
  void *ppInterface; // [rsp+48h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+30h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  ppInterface = 0;
  if ( CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface) )
  {
    v4 = (*(__int64 (__fastcall **)(CLogonEnumUsers *, struct ILogonUser **))(*(_QWORD *)this + 32LL))(this, a2);
  }
  else
  {
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
    {
      v4 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( v4 < 0 )
        goto LABEL_28;
      v4 = (*(__int64 (__fastcall **)(CLogonEnumUsers *, struct ILogonUser **))(*(_QWORD *)this + 32LL))(this, a2);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
        || v4 >= 0
        || !(unsigned int)LUAIsShadowAdminEnabled() )
      {
        goto LABEL_25;
      }
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
        goto LABEL_16;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
          goto LABEL_16;
        v8 = GetLastError();
        v9 = v8 < 0;
        if ( v8 <= 0 )
        {
LABEL_15:
          if ( v9 )
          {
LABEL_23:
            if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(TokenHandle);
LABEL_25:
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
            goto LABEL_28;
          }
LABEL_16:
          hToken = 0;
          if ( (int)LUAGetStandardToken(TokenHandle, &hToken) >= 0 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
            if ( ImpersonateLoggedOnUser(hToken) )
            {
              v10 = (*(__int64 (__fastcall **)(CLogonEnumUsers *, struct ILogonUser **))(*(_QWORD *)this + 32LL))(
                      this,
                      a2);
              v11 = 0;
              if ( v10 < 0 )
                v11 = v4;
              v4 = v11;
              RevertToSelf();
            }
          }
          if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hToken);
          goto LABEL_23;
        }
        LastError = (unsigned __int16)v8 | 0x80070000;
      }
      v9 = LastError < 0;
      goto LABEL_15;
    }
    v4 = -2147418113;
  }
LABEL_28:
  v12 = ppInterface;
  ppInterface = 0;
  if ( v12 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180034000  mov     [rsp-18h+arg_0], rbx
0x180034005  push    rbp
0x180034006  push    rsi
0x180034007  push    rdi
0x180034008  mov     rbp, rsp
0x18003400b  sub     rsp, 20h
0x18003400f  mov     rsi, rdx
0x180034012  mov     qword ptr [rdx], 0
0x180034019  mov     rdi, rcx
0x18003401c  mov     [rbp+ppInterface], 0
0x180034024  lea     rdx, [rbp+ppInterface]; ppInterface
0x180034028  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x18003402f  call    cs:__imp_CoGetCallContext
0x180034035  test    eax, eax
0x180034037  jnz     loc_1800341B8
0x18003403d  mov     rcx, [rbp+ppInterface]
0x180034041  mov     rax, [rcx]
0x180034044  mov     rax, [rax+30h]
0x180034048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003404d  test    eax, eax
0x18003404f  jnz     loc_1800341B1
0x180034055  mov     rcx, [rbp+ppInterface]
0x180034059  mov     rax, [rcx]
0x18003405c  mov     rax, [rax+20h]
0x180034060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034065  mov     ebx, eax
0x180034067  test    eax, eax
0x180034069  js      loc_1800341CC
0x18003406f  mov     rax, [rdi]
0x180034072  mov     rdx, rsi
0x180034075  mov     rcx, rdi
0x180034078  mov     rax, [rax+20h]
0x18003407c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034081  mov     ebx, eax
0x180034083  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18003408a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18003408f  test    al, al
0x180034091  jz      loc_18003419F
0x180034097  test    ebx, ebx
0x180034099  jns     loc_18003419F
0x18003409f  call    LUAIsShadowAdminEnabled
0x1800340a4  test    eax, eax
0x1800340a6  jz      loc_18003419F
0x1800340ac  mov     [rbp+TokenHandle], 0
0x1800340b4  call    cs:__imp_GetCurrentThread
0x1800340ba  mov     edx, 0Ah; DesiredAccess
0x1800340bf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800340c3  mov     rcx, rax; ThreadHandle
0x1800340c6  lea     r8d, [rdx-9]; OpenAsSelf
0x1800340ca  call    cs:__imp_OpenThreadToken
0x1800340d0  test    eax, eax
0x1800340d2  jnz     short loc_18003411F
0x1800340d4  call    cs:__imp_GetLastError
0x1800340da  test    eax, eax
0x1800340dc  jle     short loc_1800340E6
0x1800340de  movzx   eax, ax
0x1800340e1  or      eax, 80070000h
0x1800340e6  cmp     eax, 800703F0h
0x1800340eb  jnz     short loc_18003411B
0x1800340ed  call    cs:__imp_GetCurrentProcess
0x1800340f3  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800340f7  mov     edx, 0Ah; DesiredAccess
0x1800340fc  mov     rcx, rax; ProcessHandle
0x1800340ff  call    cs:__imp_OpenProcessToken
0x180034105  test    eax, eax
0x180034107  jnz     short loc_18003411F
0x180034109  call    cs:__imp_GetLastError
0x18003410f  test    eax, eax
0x180034111  jle     short loc_18003411D
0x180034113  movzx   eax, ax
0x180034116  or      eax, 80070000h
0x18003411b  test    eax, eax
0x18003411d  js      short loc_18003418B
0x18003411f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180034123  lea     rdx, [rbp+hToken]; NewTokenHandle
0x180034127  mov     [rbp+hToken], 0
0x18003412f  call    LUAGetStandardToken
0x180034134  test    eax, eax
0x180034136  js      short loc_180034177
0x180034138  mov     rcx, [rbp+ppInterface]
0x18003413c  mov     rax, [rcx]
0x18003413f  mov     rax, [rax+28h]
0x180034143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034148  mov     rcx, [rbp+hToken]; hToken
0x18003414c  call    cs:__imp_ImpersonateLoggedOnUser
0x180034152  test    eax, eax
0x180034154  jz      short loc_180034177
0x180034156  mov     rax, [rdi]
0x180034159  mov     rdx, rsi
0x18003415c  mov     rcx, rdi
0x18003415f  mov     rax, [rax+20h]
0x180034163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034168  xor     ecx, ecx
0x18003416a  test    eax, eax
0x18003416c  cmovs   ecx, ebx
0x18003416f  mov     ebx, ecx
0x180034171  call    cs:__imp_RevertToSelf
0x180034177  mov     rcx, [rbp+hToken]; hObject
0x18003417b  lea     rax, [rcx-1]
0x18003417f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034183  ja      short loc_18003418B
0x180034185  call    cs:__imp_CloseHandle
0x18003418b  mov     rcx, [rbp+TokenHandle]; hObject
0x18003418f  lea     rax, [rcx-1]
0x180034193  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034197  ja      short loc_18003419F
0x180034199  call    cs:__imp_CloseHandle
0x18003419f  mov     rcx, [rbp+ppInterface]
0x1800341a3  mov     rax, [rcx]
0x1800341a6  mov     rax, [rax+28h]
0x1800341aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341af  jmp     short loc_1800341CC
0x1800341b1  mov     ebx, 8000FFFFh
0x1800341b6  jmp     short loc_1800341CC
0x1800341b8  mov     rax, [rdi]
0x1800341bb  mov     rdx, rsi
0x1800341be  mov     rcx, rdi
0x1800341c1  mov     rax, [rax+20h]
0x1800341c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341ca  mov     ebx, eax
0x1800341cc  mov     rcx, [rbp+ppInterface]
0x1800341d0  mov     [rbp+ppInterface], 0
0x1800341d8  test    rcx, rcx
0x1800341db  jz      short loc_1800341E9
0x1800341dd  mov     rax, [rcx]
0x1800341e0  mov     rax, [rax+10h]
0x1800341e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341e9  mov     eax, ebx
0x1800341eb  mov     rbx, [rsp+20h+arg_0]
0x1800341f0  add     rsp, 20h
0x1800341f4  pop     rdi
0x1800341f5  pop     rsi
0x1800341f6  pop     rbp
0x1800341f7  retn
```
