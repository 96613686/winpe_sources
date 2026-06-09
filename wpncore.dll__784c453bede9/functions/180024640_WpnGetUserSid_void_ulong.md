# WpnGetUserSid(void *,ulong)

- ea: `0x180024640`
- end: `0x18002483b`
- name: `?WpnGetUserSid@@YAJPEAXK@Z`
- size: `507`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `14`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800189f8`
- `0x1800200b4`
- `0x180022ccc`
- `0x180024240`
- `0x180032b54`
- `0x180043814`
- `0x180044ff8`
- `0x18005df3c`
- `0x1800730b4`
- `0x18007dbb8`
- `0x18009aa6c`
- `0x1800d5a08`
- `0x1800d8d0c`
- `0x1800ed99c`

## callees

- `0x180024640`
- `0x18002ee38`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800bc541`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002476f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002476f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002466f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002466f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024682`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800246f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800246f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800246ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800246ae`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800246c1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800246c1`

## string_xrefs

- `0x180024726`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x180024783`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`
- `0x1800247ff`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnlib.cpp`

## pseudocode

```c
__int64 __fastcall WpnGetUserSid(void *a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LengthSid; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  signed int v9; // eax
  __int64 v10; // r9
  int ReturnLength; // [rsp+20h] [rbp-98h]
  int ReturnLengtha; // [rsp+20h] [rbp-98h]
  DWORD v13; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  TokenHandle = 0;
  v13 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x47D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)v4,
      ReturnLength);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_5;
    v8 = 42;
LABEL_22:
    v10 = v4;
LABEL_23:
    WPP_SF_d(v7[2], v8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids, v10);
    goto LABEL_5;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x54u, &v13) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( (v4 & 0x80000000) == 0 )
      v4 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x485,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
      (const char *)v4,
      ReturnLengtha);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_5;
    v8 = 43;
    goto LABEL_22;
  }
  LengthSid = GetLengthSid(TokenInformation);
  if ( LengthSid <= 0x44 )
  {
    memcpy_0(a1, TokenInformation, LengthSid);
    v4 = 0;
    goto LABEL_5;
  }
  v4 = -2147024774;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x48B,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnlib.cpp",
    (const char *)0x8007007ALL,
    ReturnLengtha);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v8 = 44;
    v10 = 2147942522LL;
    goto LABEL_23;
  }
LABEL_5:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180024640  push    rbx
0x180024642  sub     rsp, 0B0h
0x180024649  mov     rax, cs:__security_cookie
0x180024650  xor     rax, rsp
0x180024653  mov     [rsp+0B8h+var_18], rax
0x18002465b  mov     rbx, rcx
0x18002465e  mov     [rsp+0B8h+TokenHandle], 0
0x180024667  mov     [rsp+0B8h+var_88], 0
0x18002466f  call    cs:__imp_GetCurrentProcess
0x180024675  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x18002467a  mov     edx, 20008h; DesiredAccess
0x18002467f  mov     rcx, rax; ProcessHandle
0x180024682  call    cs:__imp_OpenProcessToken
0x180024688  test    eax, eax
0x18002468a  jz      loc_180024712
0x180024690  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180024695  lea     rax, [rsp+0B8h+var_88]
0x18002469a  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800246a0  mov     qword ptr [rsp+0B8h+ReturnLength], rax; int
0x1800246a5  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800246aa  lea     edx, [r9-53h]; TokenInformationClass
0x1800246ae  call    cs:__imp_GetTokenInformation
0x1800246b4  test    eax, eax
0x1800246b6  jz      loc_18002476F
0x1800246bc  mov     rcx, [rsp+0B8h+TokenInformation]; pSid
0x1800246c1  call    cs:__imp_GetLengthSid
0x1800246c7  cmp     eax, 44h ; 'D'
0x1800246ca  ja      loc_1800247F7
0x1800246d0  mov     rdx, [rsp+0B8h+TokenInformation]; Src
0x1800246d5  mov     rcx, rbx; void *
0x1800246d8  mov     r8d, eax; Size
0x1800246db  call    memcpy_0
0x1800246e0  xor     ebx, ebx
0x1800246e2  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800246e7  lea     rdx, [rcx-1]
0x1800246eb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800246ef  ja      short loc_1800246F7
0x1800246f1  call    cs:__imp_CloseHandle
0x1800246f7  mov     eax, ebx
0x1800246f9  mov     rcx, [rsp+0B8h+var_18]
0x180024701  xor     rcx, rsp; StackCookie
0x180024704  call    __security_check_cookie
0x180024709  add     rsp, 0B0h
0x180024710  pop     rbx
0x180024711  retn
0x180024712  call    cs:__imp_GetLastError
0x180024718  mov     ebx, eax
0x18002471a  test    eax, eax
0x18002471c  jg      short loc_180024764
0x18002471e  mov     rcx, [rsp+0B8h]; this
0x180024726  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002472d  test    ebx, ebx
0x18002472f  mov     eax, 80004005h
0x180024734  mov     edx, 47Dh; void *
0x180024739  cmovns  ebx, eax
0x18002473c  mov     r9d, ebx; char *
0x18002473f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024744  mov     rcx, cs:WPP_GLOBAL_Control
0x18002474b  lea     rax, WPP_GLOBAL_Control
0x180024752  cmp     rcx, rax
0x180024755  jz      short loc_1800246E2
0x180024757  test    byte ptr [rcx+1Ch], 80h
0x18002475b  jz      short loc_1800246E2
0x18002475d  mov     edx, 2Ah ; '*'
0x180024762  jmp     short loc_1800247C7
0x180024764  movzx   ebx, ax
0x180024767  or      ebx, 80070000h
0x18002476d  jmp     short loc_18002471E
0x18002476f  call    cs:__imp_GetLastError
0x180024775  mov     ebx, eax
0x180024777  test    eax, eax
0x180024779  jg      short loc_1800247CC
0x18002477b  mov     rcx, [rsp+0B8h]; this
0x180024783  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002478a  test    ebx, ebx
0x18002478c  mov     eax, 80004005h
0x180024791  mov     edx, 485h; void *
0x180024796  cmovns  ebx, eax
0x180024799  mov     r9d, ebx; char *
0x18002479c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800247a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247a8  lea     rax, WPP_GLOBAL_Control
0x1800247af  cmp     rcx, rax
0x1800247b2  jz      loc_1800246E2
0x1800247b8  test    byte ptr [rcx+1Ch], 80h
0x1800247bc  jz      loc_1800246E2
0x1800247c2  mov     edx, 2Bh ; '+'
0x1800247c7  mov     r9d, ebx
0x1800247ca  jmp     short loc_1800247E2
0x1800247cc  movzx   ebx, ax
0x1800247cf  or      ebx, 80070000h
0x1800247d5  jmp     short loc_18002477B
0x1800247d7  mov     edx, 2Ch ; ','
0x1800247dc  mov     r9d, 8007007Ah
0x1800247e2  mov     rcx, [rcx+10h]
0x1800247e6  lea     r8, WPP_dc39e499189d3acee5756cf962abbe12_Traceguids
0x1800247ed  call    WPP_SF_d
0x1800247f2  jmp     loc_1800246E2
0x1800247f7  mov     rcx, [rsp+0B8h]; this
0x1800247ff  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180024806  mov     ebx, 8007007Ah
0x18002480b  mov     edx, 48Bh; void *
0x180024810  mov     r9d, ebx; char *
0x180024813  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024818  mov     rcx, cs:WPP_GLOBAL_Control
0x18002481f  lea     rax, WPP_GLOBAL_Control
0x180024826  cmp     rcx, rax
0x180024829  jz      loc_1800246E2
0x18002482f  test    byte ptr [rcx+1Ch], 80h
0x180024833  jz      loc_1800246E2
0x180024839  jmp     short loc_1800247D7
```
