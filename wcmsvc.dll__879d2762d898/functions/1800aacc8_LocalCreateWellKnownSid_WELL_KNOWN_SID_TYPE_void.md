# LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x1800aacc8`
- end: `0x1800aaef2`
- name: `?LocalCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `554`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800adf74`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x180017ad0`
- `0x18001f7d0`
- `0x18003a08c`
- `0x18003b208`
- `0x180084f50`
- `0x1800aacc8`
- `0x1800add00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aad4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aada5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aadfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aae43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aad4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aada5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aadfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aae43`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aad97`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aae39`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aad97`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800aae39`

## string_xrefs

- `0x1800aad19`: `LocalCreateWellKnownSid`
- `0x1800aaeb4`: `LocalCreateWellKnownSid`

## pseudocode

```c
__int64 __fastcall LocalCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  void *v4; // rax
  void *v5; // rdi
  DWORD LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  void *v11; // rax
  DWORD cbSid; // [rsp+30h] [rbp-28h] BYREF

  cbSid = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      35,
      WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      "LocalCreateWellKnownSid");
  }
  *a2 = 0;
  v4 = (void *)WcmAlloc(0x44u);
  v5 = v4;
  if ( v4 )
  {
    if ( !CreateWellKnownSid(WellKnownSidType, 0, v4, &cbSid) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v10 = 37;
LABEL_29:
        WPP_SF_DD(*(_QWORD *)(v9 + 16), v10, WPP_59cb1c30c417333f98d499625c161da5_Traceguids);
LABEL_30:
        WcmFree(v5);
        goto LABEL_32;
      }
      WcmFree(v5);
      v11 = (void *)WcmAlloc(cbSid);
      v5 = v11;
      if ( !v11 )
      {
        LastError = GetLastError();
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return LastError;
        if ( !*(_BYTE *)(WPP_GLOBAL_Control + 25LL) || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_33;
        v8 = 38;
        goto LABEL_10;
      }
      if ( !CreateWellKnownSid(WellKnownSidType, 0, v11, &cbSid) )
      {
        LastError = GetLastError();
        if ( LastError == 122 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v9 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
          goto LABEL_30;
        }
        v10 = 39;
        goto LABEL_29;
      }
    }
    *a2 = v5;
    LastError = 0;
    goto LABEL_32;
  }
  LastError = GetLastError();
  v7 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return LastError;
  if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v8 = 36;
LABEL_10:
    WPP_SF_dD(*(_QWORD *)(v7 + 16), v8);
LABEL_32:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && *(_BYTE *)(v7 + 25) >= 5u && (*(_BYTE *)(v7 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v7 + 16),
      40,
      (unsigned int)WPP_59cb1c30c417333f98d499625c161da5_Traceguids,
      (unsigned int)"LocalCreateWellKnownSid",
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800aacc8  mov     [rsp+arg_10], rbx
0x1800aaccd  mov     [rsp+arg_18], rbp
0x1800aacd2  push    rsi
0x1800aacd3  push    rdi
0x1800aacd4  push    r15
0x1800aacd6  sub     rsp, 40h
0x1800aacda  mov     rax, cs:__security_cookie
0x1800aace1  xor     rax, rsp
0x1800aace4  mov     [rsp+58h+var_20], rax
0x1800aace9  mov     rsi, rdx
0x1800aacec  mov     [rsp+58h+cbSid], 0
0x1800aacf4  mov     ebp, ecx
0x1800aacf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aacfd  lea     r15, WPP_GLOBAL_Control
0x1800aad04  cmp     rcx, r15
0x1800aad07  jz      short loc_1800AAD31
0x1800aad09  cmp     byte ptr [rcx+19h], 5
0x1800aad0d  jb      short loc_1800AAD31
0x1800aad0f  test    byte ptr [rcx+1Ch], 1
0x1800aad13  jz      short loc_1800AAD31
0x1800aad15  mov     rcx, [rcx+10h]
0x1800aad19  lea     r9, aLocalcreatewel; "LocalCreateWellKnownSid"
0x1800aad20  mov     edx, 23h ; '#'
0x1800aad25  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aad2c  call    WPP_SF_s
0x1800aad31  mov     ecx, 44h ; 'D'; dwBytes
0x1800aad36  mov     qword ptr [rsi], 0
0x1800aad3d  call    WcmAlloc
0x1800aad42  mov     rdi, rax
0x1800aad45  test    rax, rax
0x1800aad48  jnz     short loc_1800AAD8B
0x1800aad4a  call    cs:__imp_GetLastError
0x1800aad50  mov     ebx, eax
0x1800aad52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aad59  cmp     rcx, r15
0x1800aad5c  jz      loc_1800AAED0
0x1800aad62  cmp     byte ptr [rcx+19h], 1
0x1800aad66  jb      loc_1800AAE9F
0x1800aad6c  test    byte ptr [rcx+1Ch], 1
0x1800aad70  jz      loc_1800AAE9F
0x1800aad76  lea     edx, [rdi+24h]
0x1800aad79  mov     rcx, [rcx+10h]
0x1800aad7d  mov     [rsp+58h+var_38], eax
0x1800aad81  call    WPP_SF_dD
0x1800aad86  jmp     loc_1800AAE98
0x1800aad8b  lea     r9, [rsp+58h+cbSid]; cbSid
0x1800aad90  mov     r8, rdi; pSid
0x1800aad93  xor     edx, edx; DomainSid
0x1800aad95  mov     ecx, ebp; WellKnownSidType
0x1800aad97  call    cs:__imp_CreateWellKnownSid
0x1800aad9d  test    eax, eax
0x1800aad9f  jnz     loc_1800AAE93
0x1800aada5  call    cs:__imp_GetLastError
0x1800aadab  mov     ebx, eax
0x1800aadad  cmp     eax, 7Ah ; 'z'
0x1800aadb0  jz      short loc_1800AADE4
0x1800aadb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aadb9  cmp     rcx, r15
0x1800aadbc  jz      loc_1800AAE89
0x1800aadc2  cmp     byte ptr [rcx+19h], 1
0x1800aadc6  jb      loc_1800AAE89
0x1800aadcc  test    byte ptr [rcx+1Ch], 1
0x1800aadd0  jz      loc_1800AAE89
0x1800aadd6  mov     edx, 25h ; '%'
0x1800aaddb  mov     [rsp+58h+var_38], eax
0x1800aaddf  jmp     loc_1800AAE76
0x1800aade4  mov     rcx, rdi; lpMem
0x1800aade7  call    WcmFree
0x1800aadec  mov     ecx, [rsp+58h+cbSid]; dwBytes
0x1800aadf0  call    WcmAlloc
0x1800aadf5  mov     rdi, rax
0x1800aadf8  test    rax, rax
0x1800aadfb  jnz     short loc_1800AAE2D
0x1800aadfd  call    cs:__imp_GetLastError
0x1800aae03  mov     ebx, eax
0x1800aae05  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aae0c  cmp     rcx, r15
0x1800aae0f  jz      loc_1800AAED0
0x1800aae15  cmp     byte ptr [rcx+19h], 1
0x1800aae19  jb      loc_1800AAE9F
0x1800aae1f  test    byte ptr [rcx+1Ch], 1
0x1800aae23  jz      short loc_1800AAE9F
0x1800aae25  lea     edx, [rdi+26h]
0x1800aae28  jmp     loc_1800AAD79
0x1800aae2d  lea     r9, [rsp+58h+cbSid]; cbSid
0x1800aae32  mov     r8, rax; pSid
0x1800aae35  xor     edx, edx; DomainSid
0x1800aae37  mov     ecx, ebp; WellKnownSidType
0x1800aae39  call    cs:__imp_CreateWellKnownSid
0x1800aae3f  test    eax, eax
0x1800aae41  jnz     short loc_1800AAE93
0x1800aae43  call    cs:__imp_GetLastError
0x1800aae49  mov     ebx, eax
0x1800aae4b  cmp     eax, 7Ah ; 'z'
0x1800aae4e  jnz     short loc_1800AAE55
0x1800aae50  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800aae55  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aae5c  cmp     rcx, r15
0x1800aae5f  jz      short loc_1800AAE89
0x1800aae61  cmp     byte ptr [rcx+19h], 1
0x1800aae65  jb      short loc_1800AAE89
0x1800aae67  test    byte ptr [rcx+1Ch], 1
0x1800aae6b  jz      short loc_1800AAE89
0x1800aae6d  mov     edx, 27h ; '''
0x1800aae72  mov     [rsp+58h+var_38], ebx
0x1800aae76  mov     rcx, [rcx+10h]
0x1800aae7a  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aae81  mov     r9d, ebp
0x1800aae84  call    WPP_SF_DD
0x1800aae89  mov     rcx, rdi; lpMem
0x1800aae8c  call    WcmFree
0x1800aae91  jmp     short loc_1800AAE98
0x1800aae93  mov     [rsi], rdi
0x1800aae96  xor     ebx, ebx
0x1800aae98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aae9f  cmp     rcx, r15
0x1800aaea2  jz      short loc_1800AAED0
0x1800aaea4  cmp     byte ptr [rcx+19h], 5
0x1800aaea8  jb      short loc_1800AAED0
0x1800aaeaa  test    byte ptr [rcx+1Ch], 1
0x1800aaeae  jz      short loc_1800AAED0
0x1800aaeb0  mov     rcx, [rcx+10h]
0x1800aaeb4  lea     r9, aLocalcreatewel; "LocalCreateWellKnownSid"
0x1800aaebb  mov     edx, 28h ; '('
0x1800aaec0  mov     [rsp+58h+var_38], ebx
0x1800aaec4  lea     r8, WPP_59cb1c30c417333f98d499625c161da5_Traceguids
0x1800aaecb  call    WPP_SF_sL
0x1800aaed0  mov     eax, ebx
0x1800aaed2  mov     rcx, [rsp+58h+var_20]
0x1800aaed7  xor     rcx, rsp; StackCookie
0x1800aaeda  call    __security_check_cookie
0x1800aaedf  mov     rbx, [rsp+58h+arg_10]
0x1800aaee4  mov     rbp, [rsp+58h+arg_18]
0x1800aaee9  add     rsp, 40h
0x1800aaeed  pop     r15
0x1800aaeef  pop     rdi
0x1800aaef0  pop     rsi
0x1800aaef1  retn
```
