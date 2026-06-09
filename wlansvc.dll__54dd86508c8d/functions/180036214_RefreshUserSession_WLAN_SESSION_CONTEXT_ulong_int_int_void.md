# RefreshUserSession(_WLAN_SESSION_CONTEXT *,ulong,int,int,void *)

- ea: `0x180036214`
- end: `0x180036665`
- name: `?RefreshUserSession@@YAKPEAU_WLAN_SESSION_CONTEXT@@KHHPEAX@Z`
- size: `1105`
- prototype: `unsigned int(struct _WLAN_SESSION_CONTEXT *, unsigned int, int, int, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036920`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x18000c800`
- `0x180011530`
- `0x180029ed4`
- `0x1800360b8`
- `0x180036214`
- `0x18003666c`
- `0x18009ae14`
- `0x1800e0c3c`
- `0x180106340`
- `0x180108474`
- `0x180163098`
- `0x180163338`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800364e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800364e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036421`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003651a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003651a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003657c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003657c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800362a0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800362a0`

## pseudocode

```c
__int64 __fastcall RefreshUserSession(struct _WLAN_SESSION_CONTEXT *a1, unsigned int a2, int a3, int a4, PSID pSid1)
{
  PSID Sid; // r14
  unsigned int v6; // ebx
  __int64 v9; // rsi
  DWORD LastError; // eax
  PVOID *v11; // rcx
  DWORD TokenUserInfo; // eax
  struct _WLAN_SESSION_CONTEXT *v13; // rcx
  struct _WLAN_USER_SESSION *UserSession; // rax
  struct _WLAN_SESSION_CONTEXT *v15; // rcx
  __int64 v16; // r8
  struct _WLAN_USER_SESSION *v17; // rdi
  void *v18; // rdx
  PVOID v19; // rcx
  __int64 v20; // rax
  struct _WLAN_USER_SESSION **v21; // rcx
  unsigned int v23; // ecx
  int v24; // [rsp+30h] [rbp-61h] BYREF
  int v25; // [rsp+38h] [rbp-59h] BYREF
  struct _TOKEN_USER *v26; // [rsp+40h] [rbp-51h] BYREF
  void *phToken; // [rsp+48h] [rbp-49h] BYREF
  __int64 v28; // [rsp+50h] [rbp-41h] BYREF
  char v29[16]; // [rsp+60h] [rbp-31h] BYREF
  __int64 *v30; // [rsp+70h] [rbp-21h]
  __int64 v31; // [rsp+78h] [rbp-19h]
  int *v32; // [rsp+80h] [rbp-11h]
  __int64 v33; // [rsp+88h] [rbp-9h]
  int *v34; // [rsp+90h] [rbp-1h]
  __int64 v35; // [rsp+98h] [rbp+7h]

  Sid = pSid1;
  v6 = 0;
  phToken = 0;
  v26 = 0;
  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids);
  }
  if ( pSid1 )
    goto LABEL_33;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || WTSQueryUserToken(v9, &phToken) )
  {
LABEL_25:
    TokenUserInfo = GetTokenUserInfo(phToken, &v26);
    v6 = TokenUserInfo;
    if ( TokenUserInfo )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_48;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        29,
        &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
        TokenUserInfo);
LABEL_47:
      v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_48:
      if ( !v26 )
        goto LABEL_51;
      FreeWLMem(v26);
      goto LABEL_50;
    }
    if ( !g_SessionContext )
    {
      v6 = 5023;
      goto LABEL_47;
    }
    Sid = v26->User.Sid;
LABEL_33:
    EnterCriticalSection(&stru_1802A31E8);
    UserSession = FindUserSession(v13, v9);
    v17 = UserSession;
    if ( !UserSession )
    {
LABEL_45:
      v6 = AddUserSession(v15, Sid, v9, a3, a4);
LABEL_46:
      LeaveCriticalSection(&stru_1802A31E8);
      goto LABEL_47;
    }
    v18 = (void *)*((_QWORD *)UserSession + 2);
    if ( Sid )
    {
      if ( !v18 || !EqualSid(Sid, v18) )
        goto LABEL_36;
    }
    else if ( v18 )
    {
LABEL_36:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          31,
          &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
          *((unsigned int *)v17 + 6));
      }
      if ( (byte_1802A0A43 & 0x10) != 0 )
        McTemplateU0p_EventWriteTransfer(v19, v18, *((unsigned int *)v17 + 6));
      v20 = *(_QWORD *)v17;
      if ( *(struct _WLAN_USER_SESSION **)(*(_QWORD *)v17 + 8LL) != v17
        || (v21 = (struct _WLAN_USER_SESSION **)*((_QWORD *)v17 + 1), *v21 != v17) )
      {
        __fastfail(3u);
      }
      *v21 = (struct _WLAN_USER_SESSION *)v20;
      *(_QWORD *)(v20 + 8) = v21;
      FreeUserSession(v17);
      goto LABEL_45;
    }
    v23 = *((_DWORD *)v17 + 7) & 0xFFFFFFFE ^ (*((_BYTE *)v17 + 28) & 0xFE ^ (unsigned __int8)(2 * a3)) & 2;
    *((_DWORD *)v17 + 7) = v23 ^ ((unsigned __int8)v23 ^ (unsigned __int8)(4 * a4)) & 4;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_lll(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        30,
        &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
        (unsigned int)v9);
    }
    if ( (byte_1802A0A43 & 0x10) != 0 )
    {
      v25 = a4;
      v30 = &v28;
      v24 = a3;
      v32 = &v24;
      v28 = v9;
      v34 = &v25;
      v31 = 8;
      v33 = 4;
      v35 = 4;
      McGenEventWrite_EventWriteTransfer(&WLANSVC_EVT_GUID_Context, WlanSvcSessionRefreshed, v16, 4, v29);
    }
    goto LABEL_46;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError == 1008 || LastError == 1245 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        26,
        &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
        (unsigned int)v9);
      goto LABEL_23;
    }
LABEL_24:
    if ( v6 )
      goto LABEL_51;
    goto LABEL_25;
  }
  if ( LastError != 7022 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        28,
        &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
        (unsigned int)v9);
LABEL_23:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      27,
      &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids,
      (unsigned int)v9);
LABEL_50:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_51:
  if ( phToken )
  {
    CloseHandle(phToken);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 105) >= 4u && (*((_BYTE *)v11 + 108) & 1) != 0 )
    WPP_SF_d(v11[12], 32, &WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180036214  push    rbp
0x180036216  push    rbx
0x180036217  push    rsi
0x180036218  push    rdi
0x180036219  push    r12
0x18003621b  push    r14
0x18003621d  push    r15
0x18003621f  lea     rbp, [rsp-1Fh]
0x180036224  sub     rsp, 0B0h
0x18003622b  mov     rax, cs:__security_cookie
0x180036232  xor     rax, rsp
0x180036235  mov     [rbp+4Fh+var_40], rax
0x180036239  mov     r14, [rbp+4Fh+pSid1]
0x18003623d  xor     ebx, ebx
0x18003623f  mov     [rbp+4Fh+phToken], rbx
0x180036243  mov     r12d, r9d
0x180036246  mov     [rbp+4Fh+var_A0], rbx
0x18003624a  mov     r15d, r8d
0x18003624d  mov     esi, edx
0x18003624f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036256  lea     rax, WPP_GLOBAL_Control
0x18003625d  mov     dil, 1
0x180036260  cmp     rcx, rax
0x180036263  jz      short loc_180036284
0x180036265  cmp     byte ptr [rcx+69h], 4
0x180036269  jb      short loc_180036284
0x18003626b  test    [rcx+6Ch], dil
0x18003626f  jz      short loc_180036284
0x180036271  mov     rcx, [rcx+60h]
0x180036275  lea     edx, [rbx+19h]
0x180036278  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x18003627f  call    WPP_SF_
0x180036284  test    r14, r14
0x180036287  jnz     loc_18003641A
0x18003628d  call    IsWTSEnumerateSessionsWPresent
0x180036292  test    al, al
0x180036294  jz      loc_18003639E
0x18003629a  lea     rdx, [rbp+4Fh+phToken]; phToken
0x18003629e  mov     ecx, esi; SessionId
0x1800362a0  call    cs:__imp_WTSQueryUserToken
0x1800362a6  test    eax, eax
0x1800362a8  jnz     loc_18003639E
0x1800362ae  call    cs:__imp_GetLastError
0x1800362b4  mov     ebx, eax
0x1800362b6  cmp     eax, 3F0h
0x1800362bb  jz      loc_180036358
0x1800362c1  cmp     eax, 4DDh
0x1800362c6  jz      loc_180036358
0x1800362cc  cmp     eax, 1B6Eh
0x1800362d1  jnz     short loc_18003631B
0x1800362d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362da  lea     r14, WPP_GLOBAL_Control
0x1800362e1  cmp     rcx, r14
0x1800362e4  jz      loc_18003650E
0x1800362ea  cmp     byte ptr [rcx+69h], 2
0x1800362ee  jb      loc_18003650E
0x1800362f4  test    [rcx+6Ch], dil
0x1800362f8  jz      loc_18003650E
0x1800362fe  mov     rcx, [rcx+60h]
0x180036302  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x180036309  mov     edx, 1Bh
0x18003630e  mov     r9d, esi
0x180036311  call    WPP_SF_d
0x180036316  jmp     loc_180036507
0x18003631b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036322  lea     r14, WPP_GLOBAL_Control
0x180036329  cmp     rcx, r14
0x18003632c  jz      short loc_180036396
0x18003632e  cmp     [rcx+69h], dil
0x180036332  jb      short loc_180036396
0x180036334  test    [rcx+6Ch], dil
0x180036338  jz      short loc_180036396
0x18003633a  mov     rcx, [rcx+60h]
0x18003633e  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x180036345  mov     edx, 1Ch
0x18003634a  mov     [rsp+0E0h+var_C0], ebx
0x18003634e  mov     r9d, esi
0x180036351  call    WPP_SF_DD
0x180036356  jmp     short loc_18003638F
0x180036358  mov     rcx, cs:WPP_GLOBAL_Control
0x18003635f  lea     r14, WPP_GLOBAL_Control
0x180036366  cmp     rcx, r14
0x180036369  jz      short loc_180036396
0x18003636b  cmp     byte ptr [rcx+69h], 3
0x18003636f  jb      short loc_180036396
0x180036371  test    [rcx+6Ch], dil
0x180036375  jz      short loc_180036396
0x180036377  mov     rcx, [rcx+60h]
0x18003637b  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x180036382  mov     edx, 1Ah
0x180036387  mov     r9d, esi
0x18003638a  call    WPP_SF_d
0x18003638f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036396  test    ebx, ebx
0x180036398  jnz     loc_18003650E
0x18003639e  mov     rcx, [rbp+4Fh+phToken]; TokenHandle
0x1800363a2  lea     rdx, [rbp+4Fh+var_A0]; struct _TOKEN_USER **
0x1800363a6  call    ?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserInfo(void *,_TOKEN_USER * *)
0x1800363ab  mov     ebx, eax
0x1800363ad  test    eax, eax
0x1800363af  jz      short loc_1800363F9
0x1800363b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363b8  lea     r14, WPP_GLOBAL_Control
0x1800363bf  cmp     rcx, r14
0x1800363c2  jz      loc_1800364F6
0x1800363c8  cmp     [rcx+69h], dil
0x1800363cc  jb      loc_1800364F6
0x1800363d2  test    [rcx+6Ch], dil
0x1800363d6  jz      loc_1800364F6
0x1800363dc  mov     rcx, [rcx+60h]
0x1800363e0  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x1800363e7  mov     edx, 1Dh
0x1800363ec  mov     r9d, eax
0x1800363ef  call    WPP_SF_d
0x1800363f4  jmp     loc_1800364EF
0x1800363f9  cmp     cs:?g_SessionContext@@3U_WLAN_SESSION_CONTEXT@@A, 0; _WLAN_SESSION_CONTEXT g_SessionContext
0x180036400  jnz     short loc_180036413
0x180036402  mov     ebx, 139Fh
0x180036407  lea     r14, WPP_GLOBAL_Control
0x18003640e  jmp     loc_1800364EF
0x180036413  mov     rax, [rbp+4Fh+var_A0]
0x180036417  mov     r14, [rax]
0x18003641a  lea     rcx, stru_1802A31E8; lpCriticalSection
0x180036421  call    cs:__imp_EnterCriticalSection
0x180036427  mov     edx, esi; unsigned int
0x180036429  call    ?FindUserSession@@YAPEAU_WLAN_USER_SESSION@@PEAU_WLAN_SESSION_CONTEXT@@K@Z; FindUserSession(_WLAN_SESSION_CONTEXT *,ulong)
0x18003642e  mov     rdi, rax
0x180036431  test    rax, rax
0x180036434  jz      loc_1800364C3
0x18003643a  mov     rdx, [rax+10h]; pSid2
0x18003643e  test    r14, r14
0x180036441  jnz     loc_180036570
0x180036447  test    rdx, rdx
0x18003644a  jz      loc_18003658A
0x180036450  mov     rcx, cs:WPP_GLOBAL_Control
0x180036457  lea     rax, WPP_GLOBAL_Control
0x18003645e  cmp     rcx, rax
0x180036461  jz      short loc_180036488
0x180036463  cmp     byte ptr [rcx+69h], 3
0x180036467  jb      short loc_180036488
0x180036469  test    byte ptr [rcx+6Ch], 1
0x18003646d  jz      short loc_180036488
0x18003646f  mov     r9d, [rdi+18h]
0x180036473  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x18003647a  mov     rcx, [rcx+60h]
0x18003647e  mov     edx, 1Fh
0x180036483  call    WPP_SF_d
0x180036488  test    cs:byte_1802A0A43, 10h
0x18003648f  jz      short loc_18003649A
0x180036491  mov     r8d, [rdi+18h]
0x180036495  call    McTemplateU0p_EventWriteTransfer
0x18003649a  mov     rax, [rdi]
0x18003649d  cmp     [rax+8], rdi
0x1800364a1  jnz     loc_18003665E
0x1800364a7  mov     rcx, [rdi+8]
0x1800364ab  cmp     [rcx], rdi
0x1800364ae  jnz     loc_18003665E
0x1800364b4  mov     [rcx], rax
0x1800364b7  mov     [rax+8], rcx
0x1800364bb  mov     rcx, rdi; struct _WLAN_USER_SESSION *
0x1800364be  call    ?FreeUserSession@@YAXPEAU_WLAN_USER_SESSION@@@Z; FreeUserSession(_WLAN_USER_SESSION *)
0x1800364c3  mov     r9d, r15d; int
0x1800364c6  mov     [rsp+0E0h+var_C0], r12d; int
0x1800364cb  mov     r8d, esi; unsigned int
0x1800364ce  mov     rdx, r14; void *
0x1800364d1  call    ?AddUserSession@@YAKPEAU_WLAN_SESSION_CONTEXT@@PEAXKHH@Z; AddUserSession(_WLAN_SESSION_CONTEXT *,void *,ulong,int,int)
0x1800364d6  mov     ebx, eax
0x1800364d8  lea     r14, WPP_GLOBAL_Control
0x1800364df  lea     rcx, stru_1802A31E8; lpCriticalSection
0x1800364e6  call    cs:__imp_LeaveCriticalSection
0x1800364ec  mov     dil, 1
0x1800364ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364f6  mov     rax, [rbp+4Fh+var_A0]
0x1800364fa  test    rax, rax
0x1800364fd  jz      short loc_18003650E
0x1800364ff  mov     rcx, rax
0x180036502  call    FreeWLMem
0x180036507  mov     rcx, cs:WPP_GLOBAL_Control
0x18003650e  mov     rax, [rbp+4Fh+phToken]
0x180036512  test    rax, rax
0x180036515  jz      short loc_180036527
0x180036517  mov     rcx, rax; hObject
0x18003651a  call    cs:__imp_CloseHandle
0x180036520  mov     rcx, cs:WPP_GLOBAL_Control
0x180036527  cmp     rcx, r14
0x18003652a  jz      short loc_180036550
0x18003652c  cmp     byte ptr [rcx+69h], 4
0x180036530  jb      short loc_180036550
0x180036532  test    [rcx+6Ch], dil
0x180036536  jz      short loc_180036550
0x180036538  mov     rcx, [rcx+60h]
0x18003653c  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x180036543  mov     edx, 20h ; ' '
0x180036548  mov     r9d, ebx
0x18003654b  call    WPP_SF_d
0x180036550  mov     eax, ebx
0x180036552  mov     rcx, [rbp+4Fh+var_40]
0x180036556  xor     rcx, rsp; StackCookie
0x180036559  call    __security_check_cookie
0x18003655e  add     rsp, 0B0h
0x180036565  pop     r15
0x180036567  pop     r14
0x180036569  pop     r12
0x18003656b  pop     rdi
0x18003656c  pop     rsi
0x18003656d  pop     rbx
0x18003656e  pop     rbp
0x18003656f  retn
0x180036570  test    rdx, rdx
0x180036573  jz      loc_180036450
0x180036579  mov     rcx, r14; pSid1
0x18003657c  call    cs:__imp_EqualSid
0x180036582  test    eax, eax
0x180036584  jz      loc_180036450
0x18003658a  mov     eax, [rdi+1Ch]
0x18003658d  lea     ecx, [r15+r15]
0x180036591  and     eax, 0FFFFFFFEh
0x180036594  xor     ecx, eax
0x180036596  and     ecx, 2
0x180036599  xor     ecx, eax
0x18003659b  lea     eax, ds:0[r12*4]
0x1800365a3  xor     eax, ecx
0x1800365a5  and     eax, 4
0x1800365a8  xor     eax, ecx
0x1800365aa  mov     [rdi+1Ch], eax
0x1800365ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365b4  lea     r14, WPP_GLOBAL_Control
0x1800365bb  cmp     rcx, r14
0x1800365be  jz      short loc_1800365EE
0x1800365c0  cmp     byte ptr [rcx+69h], 3
0x1800365c4  jb      short loc_1800365EE
0x1800365c6  test    byte ptr [rcx+6Ch], 1
0x1800365ca  jz      short loc_1800365EE
0x1800365cc  mov     rcx, [rcx+60h]
0x1800365d0  lea     r8, WPP_2c85503cfe9531e76fbba97fd16cb3f4_Traceguids
0x1800365d7  mov     edx, 1Eh
0x1800365dc  mov     [rsp+0E0h+var_B8], r12d
0x1800365e1  mov     r9d, esi
0x1800365e4  mov     [rsp+0E0h+var_C0], r15d
0x1800365e9  call    WPP_SF_lll
0x1800365ee  test    cs:byte_1802A0A43, 10h
0x1800365f5  jz      loc_1800364DF
0x1800365fb  lea     rax, [rbp+4Fh+var_90]
0x1800365ff  mov     [rbp+4Fh+var_A8], r12d
0x180036603  mov     [rbp+4Fh+var_70], rax
0x180036607  lea     rdx, WlanSvcSessionRefreshed
0x18003660e  lea     rax, [rbp+4Fh+var_B0]
0x180036612  mov     [rbp+4Fh+var_B0], r15d
0x180036616  mov     [rbp+4Fh+var_60], rax
0x18003661a  lea     rcx, WLANSVC_EVT_GUID_Context
0x180036621  lea     rax, [rbp+4Fh+var_A8]
0x180036625  mov     [rbp+4Fh+var_90], rsi
0x180036629  mov     [rbp+4Fh+var_50], rax
0x18003662d  mov     r9d, 4
0x180036633  lea     rax, [rbp+4Fh+var_80]
0x180036637  mov     [rbp+4Fh+var_68], 8
0x18003663f  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180036644  mov     [rbp+4Fh+var_58], 4
0x18003664c  mov     [rbp+4Fh+var_48], 4
0x180036654  call    McGenEventWrite_EventWriteTransfer
0x180036659  jmp     loc_1800364DF
0x18003665e  mov     ecx, 3
0x180036663  int     29h; Win8: RtlFailFast(ecx)
```
