# LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *,ulong *)

- ea: `0x180116850`
- end: `0x180116a72`
- name: `?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAXPEAK@Z`
- size: `546`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801c89d0`
- `0x1802017d4`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x180029ed4`
- `0x18002f450`
- `0x1800c6774`
- `0x180116850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801168cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011692f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801169d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801168cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011692f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180116987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801169d1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180116921`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801169c7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180116921`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1801169c7`

## pseudocode

```c
__int64 __fastcall LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2, unsigned int *a3)
{
  void *v6; // rax
  void *v7; // rsi
  DWORD LastError; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  void *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  DWORD cbSid; // [rsp+70h] [rbp+18h] BYREF

  cbSid = 0;
  if ( a3 )
    *a3 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
  }
  v6 = (void *)AllocWLMem(0x44u);
  v7 = v6;
  if ( v6 )
  {
    if ( !CreateWellKnownSid(WellKnownSidType, 0, v6, &cbSid) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_32;
        }
        v12 = 26;
LABEL_31:
        WPP_SF_DD(v11[12], v12, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, (unsigned int)WellKnownSidType);
LABEL_32:
        FreeWLMem(v7);
        goto LABEL_36;
      }
      FreeWLMem(v7);
      v13 = (void *)AllocWLMem(cbSid);
      v7 = v13;
      if ( !v13 )
      {
        LastError = GetLastError();
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return LastError;
        if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          goto LABEL_37;
        v10 = 27;
        goto LABEL_12;
      }
      if ( !CreateWellKnownSid(WellKnownSidType, 0, v13, &cbSid) )
      {
        LastError = GetLastError();
        if ( LastError == 122 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14, v16);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_32;
        }
        v12 = 28;
        goto LABEL_31;
      }
      if ( a3 )
        *a3 = cbSid;
    }
    *a2 = v7;
    LastError = 0;
    goto LABEL_36;
  }
  LastError = GetLastError();
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return LastError;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    v10 = 25;
LABEL_12:
    WPP_SF_DD(v9[12], v10, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, 68);
LABEL_36:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_37:
  if ( v9 != &WPP_GLOBAL_Control && *((_BYTE *)v9 + 105) >= 4u && (*((_BYTE *)v9 + 108) & 1) != 0 )
    WPP_SF_d(v9[12], 29, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180116850  mov     [rsp+arg_0], rbx
0x180116855  mov     [rsp+arg_8], rbp
0x18011685a  push    rsi
0x18011685b  push    rdi
0x18011685c  push    r12
0x18011685e  push    r13
0x180116860  push    r14
0x180116862  sub     rsp, 30h
0x180116866  mov     [rsp+58h+cbSid], 0
0x18011686e  mov     rdi, r8
0x180116871  mov     r14, rdx
0x180116874  mov     ebp, ecx
0x180116876  test    r8, r8
0x180116879  jz      short loc_180116882
0x18011687b  mov     dword ptr [r8], 0
0x180116882  mov     rcx, cs:WPP_GLOBAL_Control
0x180116889  lea     r12, WPP_GLOBAL_Control
0x180116890  lea     r13, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x180116897  cmp     rcx, r12
0x18011689a  jz      short loc_1801168B9
0x18011689c  cmp     byte ptr [rcx+69h], 4
0x1801168a0  jb      short loc_1801168B9
0x1801168a2  test    byte ptr [rcx+6Ch], 1
0x1801168a6  jz      short loc_1801168B9
0x1801168a8  mov     rcx, [rcx+60h]
0x1801168ac  mov     edx, 18h
0x1801168b1  mov     r8, r13
0x1801168b4  call    WPP_SF_
0x1801168b9  mov     ecx, 44h ; 'D'; dwBytes
0x1801168be  call    AllocWLMem
0x1801168c3  mov     rsi, rax
0x1801168c6  test    rax, rax
0x1801168c9  jnz     short loc_180116915
0x1801168cb  call    cs:__imp_GetLastError
0x1801168d1  mov     ebx, eax
0x1801168d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801168da  cmp     rcx, r12
0x1801168dd  jz      loc_180116A59
0x1801168e3  cmp     byte ptr [rcx+69h], 1
0x1801168e7  jb      loc_180116A34
0x1801168ed  test    byte ptr [rcx+6Ch], 1
0x1801168f1  jz      loc_180116A34
0x1801168f7  lea     edx, [rsi+19h]
0x1801168fa  mov     rcx, [rcx+60h]
0x1801168fe  mov     r9d, 44h ; 'D'
0x180116904  mov     r8, r13
0x180116907  mov     [rsp+58h+var_38], eax
0x18011690b  call    WPP_SF_DD
0x180116910  jmp     loc_180116A2D
0x180116915  lea     r9, [rsp+58h+cbSid]; cbSid
0x18011691a  mov     r8, rsi; pSid
0x18011691d  xor     edx, edx; DomainSid
0x18011691f  mov     ecx, ebp; WellKnownSidType
0x180116921  call    cs:__imp_CreateWellKnownSid
0x180116927  test    eax, eax
0x180116929  jnz     loc_180116A28
0x18011692f  call    cs:__imp_GetLastError
0x180116935  mov     ebx, eax
0x180116937  cmp     eax, 7Ah ; 'z'
0x18011693a  jz      short loc_18011696E
0x18011693c  mov     rcx, cs:WPP_GLOBAL_Control
0x180116943  cmp     rcx, r12
0x180116946  jz      loc_180116A13
0x18011694c  cmp     byte ptr [rcx+69h], 1
0x180116950  jb      loc_180116A13
0x180116956  test    byte ptr [rcx+6Ch], 1
0x18011695a  jz      loc_180116A13
0x180116960  mov     edx, 1Ah
0x180116965  mov     [rsp+58h+var_38], eax
0x180116969  jmp     loc_180116A04
0x18011696e  mov     rcx, rsi
0x180116971  call    FreeWLMem
0x180116976  mov     ecx, [rsp+58h+cbSid]; dwBytes
0x18011697a  call    AllocWLMem
0x18011697f  mov     rsi, rax
0x180116982  test    rax, rax
0x180116985  jnz     short loc_1801169BB
0x180116987  call    cs:__imp_GetLastError
0x18011698d  mov     ebx, eax
0x18011698f  mov     rcx, cs:WPP_GLOBAL_Control
0x180116996  cmp     rcx, r12
0x180116999  jz      loc_180116A59
0x18011699f  cmp     byte ptr [rcx+69h], 1
0x1801169a3  jb      loc_180116A34
0x1801169a9  test    byte ptr [rcx+6Ch], 1
0x1801169ad  jz      loc_180116A34
0x1801169b3  lea     edx, [rsi+1Bh]
0x1801169b6  jmp     loc_1801168FA
0x1801169bb  lea     r9, [rsp+58h+cbSid]; cbSid
0x1801169c0  mov     r8, rax; pSid
0x1801169c3  xor     edx, edx; DomainSid
0x1801169c5  mov     ecx, ebp; WellKnownSidType
0x1801169c7  call    cs:__imp_CreateWellKnownSid
0x1801169cd  test    eax, eax
0x1801169cf  jnz     short loc_180116A1D
0x1801169d1  call    cs:__imp_GetLastError
0x1801169d7  mov     ebx, eax
0x1801169d9  cmp     eax, 7Ah ; 'z'
0x1801169dc  jnz     short loc_1801169E3
0x1801169de  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "dwRetCode != 122L")
0x1801169e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801169ea  cmp     rcx, r12
0x1801169ed  jz      short loc_180116A13
0x1801169ef  cmp     byte ptr [rcx+69h], 1
0x1801169f3  jb      short loc_180116A13
0x1801169f5  test    byte ptr [rcx+6Ch], 1
0x1801169f9  jz      short loc_180116A13
0x1801169fb  mov     edx, 1Ch
0x180116a00  mov     [rsp+58h+var_38], ebx
0x180116a04  mov     rcx, [rcx+60h]
0x180116a08  mov     r9d, ebp
0x180116a0b  mov     r8, r13
0x180116a0e  call    WPP_SF_DD
0x180116a13  mov     rcx, rsi
0x180116a16  call    FreeWLMem
0x180116a1b  jmp     short loc_180116A2D
0x180116a1d  test    rdi, rdi
0x180116a20  jz      short loc_180116A28
0x180116a22  mov     eax, [rsp+58h+cbSid]
0x180116a26  mov     [rdi], eax
0x180116a28  mov     [r14], rsi
0x180116a2b  xor     ebx, ebx
0x180116a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180116a34  cmp     rcx, r12
0x180116a37  jz      short loc_180116A59
0x180116a39  cmp     byte ptr [rcx+69h], 4
0x180116a3d  jb      short loc_180116A59
0x180116a3f  test    byte ptr [rcx+6Ch], 1
0x180116a43  jz      short loc_180116A59
0x180116a45  mov     rcx, [rcx+60h]
0x180116a49  mov     edx, 1Dh
0x180116a4e  mov     r9d, ebx
0x180116a51  mov     r8, r13
0x180116a54  call    WPP_SF_d
0x180116a59  mov     rbp, [rsp+58h+arg_8]
0x180116a5e  mov     eax, ebx
0x180116a60  mov     rbx, [rsp+58h+arg_0]
0x180116a65  add     rsp, 30h
0x180116a69  pop     r14
0x180116a6b  pop     r13
0x180116a6d  pop     r12
0x180116a6f  pop     rdi
0x180116a70  pop     rsi
0x180116a71  retn
```
