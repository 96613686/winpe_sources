# _ProcessUserSIDInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18008cc70`
- end: `0x18008cf61`
- name: `?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `753`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004efc0`
- `0x18004f7b0`
- `0x18004ffe0`
- `0x180055720`
- `0x180058414`
- `0x18005c104`
- `0x18005c81c`
- `0x180080fb0`
- `0x180081b40`
- `0x18008cae0`
- `0x18008cb94`
- `0x18008cc70`
- `0x18008cf68`
- `0x1800c50e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008cd0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008cd0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008cd1e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008cd1e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008cef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008cef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cd28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ce68`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008ce14`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008ce5e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008ce14`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008ce5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008cf08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008cf08`
- `ntdll!RtlQueryPackageClaims` at `0x18008cec0`
- `ntdll!RtlQueryPackageClaims` at `0x18008cec0`

## pseudocode

```c
_BOOL8 __fastcall _ProcessUserSIDInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  void *v4; // rdx
  int TokenUserSID; // ebx
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  unsigned int v8; // r8d
  int v9; // edi
  signed int v10; // eax
  signed int LastError; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  DWORD v16; // eax
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSourceSid[80]; // [rsp+70h] [rbp-90h] BYREF
  _SID v25; // [rsp+C0h] [rbp-40h] BYREF

  v21[1] = 0;
  v21[0] = 0;
  TokenHandle = 0;
  memset_0(pSourceSid, 0, 0x44u);
  memset_0(&v25, 0, 0x44u);
  v19 = 0;
  v20 = 0;
  v18 = 4096;
  v23 = 0;
  if ( Context )
    *Context = 0;
  TokenUserSID = AutoTokenImpersonate::Impersonate((AutoTokenImpersonate *)v21, v4);
  if ( TokenUserSID < 0 )
  {
    HIDWORD(v18) = 63;
    goto LABEL_40;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    TokenUserSID = WxGetTokenUserSID(TokenHandle, pSourceSid);
    if ( TokenUserSID < 0 )
    {
      HIDWORD(v18) = 67;
      goto LABEL_40;
    }
    TokenUserSID = WxIsTokenAppContainer(TokenHandle, &v19);
    if ( TokenUserSID < 0 )
    {
      HIDWORD(v18) = 69;
      goto LABEL_40;
    }
    v9 = v19;
    if ( v19 )
    {
      TokenUserSID = WxGetTokenAppContainerSID(TokenHandle, &v25, v8);
      if ( TokenUserSID < 0 )
      {
        HIDWORD(v18) = 72;
        goto LABEL_40;
      }
    }
    TokenUserSID = WxGetTokenSessionId(TokenHandle, &v20);
    if ( TokenUserSID < 0 )
    {
      HIDWORD(v18) = 75;
      goto LABEL_40;
    }
    TokenUserSID = WxGetTokenIntegrityLevel(TokenHandle, (unsigned int *)&v18);
    if ( TokenUserSID < 0 )
    {
      HIDWORD(v18) = 77;
      goto LABEL_40;
    }
    if ( CopySid(0x44u, &g_rgbProcessUserSID, pSourceSid) )
    {
      TokenUserSID = 0;
      if ( !v9 || CopySid(0x44u, &g_rgbAppContainerSID, &v25) )
      {
        if ( (unsigned int)Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline() )
        {
          v12 = RtlQueryPackageClaims(TokenHandle, 0, 0, 0, 0, 0, &v23, 0, v18);
          if ( v12 < 0 )
          {
            if ( v12 != -1073741275 )
            {
              TokenUserSID = HRESULT_FROM_NTSTATUS(v12);
              if ( TokenUserSID < 0 )
              {
                HIDWORD(v18) = 107;
                goto LABEL_40;
              }
            }
          }
          else if ( (BYTE3(xmmword_180113B20) & 0x20) != 0 )
          {
            WPP_SF_L(v14, v13, v15, (unsigned int)v23);
          }
        }
        g_dwProcessSessionId = v20;
        goto LABEL_40;
      }
      LastError = GetLastError();
      TokenUserSID = LastError;
      if ( LastError > 0 )
        TokenUserSID = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(v18) = 85;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
    else
    {
      v10 = GetLastError();
      TokenUserSID = v10;
      if ( v10 > 0 )
        TokenUserSID = (unsigned __int16)v10 | 0x80070000;
      HIDWORD(v18) = 79;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
  }
  else
  {
    v7 = GetLastError();
    TokenUserSID = v7;
    if ( v7 > 0 )
      TokenUserSID = (unsigned __int16)v7 | 0x80070000;
    HIDWORD(v18) = 65;
    if ( TokenUserSID >= 0 )
      TokenUserSID = -2147418113;
  }
LABEL_40:
  v16 = WX_WIN32_FROM_HR((unsigned int)TokenUserSID);
  SetLastError(v16);
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  AutoTokenImpersonate::~AutoTokenImpersonate((AutoTokenImpersonate *)v21);
  return TokenUserSID >= 0;
}

```

## disassembly

```asm
0x18008cc70  mov     [rsp-8+arg_0], rbx
0x18008cc75  mov     [rsp-8+arg_8], rsi
0x18008cc7a  push    rbp
0x18008cc7b  push    rdi
0x18008cc7c  push    r14
0x18008cc7e  lea     rbp, [rsp-20h]
0x18008cc83  sub     rsp, 120h
0x18008cc8a  mov     rax, cs:__security_cookie
0x18008cc91  xor     rax, rsp
0x18008cc94  mov     [rbp+30h+var_20], rax
0x18008cc98  xor     esi, esi
0x18008cc9a  lea     rcx, [rsp+130h+pSourceSid]; void *
0x18008cc9f  mov     rbx, r8
0x18008cca2  mov     [rsp+130h+var_EC], esi
0x18008cca6  xor     edx, edx; Val
0x18008cca8  mov     [rsp+130h+var_D8], rsi
0x18008ccad  mov     [rsp+130h+var_E0], rsi
0x18008ccb2  lea     r14d, [rsi+44h]
0x18008ccb6  mov     [rsp+130h+TokenHandle], rsi
0x18008ccbb  mov     r8d, r14d; Size
0x18008ccbe  call    memset_0
0x18008ccc3  mov     r8d, r14d; Size
0x18008ccc6  lea     rcx, [rbp+30h+var_70]; void *
0x18008ccca  xor     edx, edx; Val
0x18008cccc  call    memset_0
0x18008ccd1  mov     [rsp+130h+var_E8], esi
0x18008ccd5  mov     [rsp+130h+var_E4], esi
0x18008ccd9  mov     [rsp+130h+var_F0], 1000h
0x18008cce1  mov     [rsp+130h+var_C8], rsi
0x18008cce6  test    rbx, rbx
0x18008cce9  jz      short loc_18008CCEE
0x18008cceb  mov     [rbx], rsi
0x18008ccee  lea     rcx, [rsp+130h+var_E0]; this
0x18008ccf3  call    ?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z; AutoTokenImpersonate::Impersonate(void *)
0x18008ccf8  mov     ebx, eax
0x18008ccfa  test    eax, eax
0x18008ccfc  jns     short loc_18008CD0B
0x18008ccfe  mov     [rsp+130h+var_EC], 3Fh ; '?'
0x18008cd06  jmp     loc_18008CEE7
0x18008cd0b  call    cs:__imp_GetCurrentProcess
0x18008cd11  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x18008cd16  mov     edx, 20008h; DesiredAccess
0x18008cd1b  mov     rcx, rax; ProcessHandle
0x18008cd1e  call    cs:__imp_OpenProcessToken
0x18008cd24  test    eax, eax
0x18008cd26  jnz     short loc_18008CD54
0x18008cd28  call    cs:__imp_GetLastError
0x18008cd2e  mov     ebx, eax
0x18008cd30  test    eax, eax
0x18008cd32  jle     short loc_18008CD3D
0x18008cd34  movzx   ebx, ax
0x18008cd37  or      ebx, 80070000h
0x18008cd3d  test    ebx, ebx
0x18008cd3f  mov     [rsp+130h+var_EC], 41h ; 'A'
0x18008cd47  mov     eax, 8000FFFFh
0x18008cd4c  cmovns  ebx, eax
0x18008cd4f  jmp     loc_18008CEE7
0x18008cd54  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18008cd59  lea     rdx, [rsp+130h+pSourceSid]; pDestinationSid
0x18008cd5e  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x18008cd63  mov     ebx, eax
0x18008cd65  test    eax, eax
0x18008cd67  jns     short loc_18008CD76
0x18008cd69  mov     [rsp+130h+var_EC], 43h ; 'C'
0x18008cd71  jmp     loc_18008CEE7
0x18008cd76  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18008cd7b  lea     rdx, [rsp+130h+var_E8]; int *
0x18008cd80  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x18008cd85  mov     ebx, eax
0x18008cd87  test    eax, eax
0x18008cd89  jns     short loc_18008CD98
0x18008cd8b  mov     [rsp+130h+var_EC], 45h ; 'E'
0x18008cd93  jmp     loc_18008CEE7
0x18008cd98  mov     edi, [rsp+130h+var_E8]
0x18008cd9c  test    edi, edi
0x18008cd9e  jz      short loc_18008CDC1
0x18008cda0  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18008cda5  lea     rdx, [rbp+30h+var_70]; struct _SID *
0x18008cda9  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x18008cdae  mov     ebx, eax
0x18008cdb0  test    eax, eax
0x18008cdb2  jns     short loc_18008CDC1
0x18008cdb4  mov     [rsp+130h+var_EC], 48h ; 'H'
0x18008cdbc  jmp     loc_18008CEE7
0x18008cdc1  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18008cdc6  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x18008cdcb  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x18008cdd0  mov     ebx, eax
0x18008cdd2  test    eax, eax
0x18008cdd4  jns     short loc_18008CDE3
0x18008cdd6  mov     [rsp+130h+var_EC], 4Bh ; 'K'
0x18008cdde  jmp     loc_18008CEE7
0x18008cde3  mov     rcx, [rsp+130h+TokenHandle]; void *
0x18008cde8  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18008cded  call    ?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenIntegrityLevel(void *,ulong *)
0x18008cdf2  mov     ebx, eax
0x18008cdf4  test    eax, eax
0x18008cdf6  jns     short loc_18008CE05
0x18008cdf8  mov     [rsp+130h+var_EC], 4Dh ; 'M'
0x18008ce00  jmp     loc_18008CEE7
0x18008ce05  lea     r8, [rsp+130h+pSourceSid]; pSourceSid
0x18008ce0a  mov     ecx, r14d; nDestinationSidLength
0x18008ce0d  lea     rdx, ?g_rgbProcessUserSID@@3PAEA; pDestinationSid
0x18008ce14  call    cs:__imp_CopySid
0x18008ce1a  test    eax, eax
0x18008ce1c  jnz     short loc_18008CE4A
0x18008ce1e  call    cs:__imp_GetLastError
0x18008ce24  mov     ebx, eax
0x18008ce26  test    eax, eax
0x18008ce28  jle     short loc_18008CE33
0x18008ce2a  movzx   ebx, ax
0x18008ce2d  or      ebx, 80070000h
0x18008ce33  test    ebx, ebx
0x18008ce35  mov     [rsp+130h+var_EC], 4Fh ; 'O'
0x18008ce3d  mov     eax, 8000FFFFh
0x18008ce42  cmovns  ebx, eax
0x18008ce45  jmp     loc_18008CEE7
0x18008ce4a  mov     ebx, esi
0x18008ce4c  test    edi, edi
0x18008ce4e  jz      short loc_18008CE91
0x18008ce50  lea     r8, [rbp+30h+var_70]; pSourceSid
0x18008ce54  mov     ecx, r14d; nDestinationSidLength
0x18008ce57  lea     rdx, ?g_rgbAppContainerSID@@3PAEA; pDestinationSid
0x18008ce5e  call    cs:__imp_CopySid
0x18008ce64  test    eax, eax
0x18008ce66  jnz     short loc_18008CE91
0x18008ce68  call    cs:__imp_GetLastError
0x18008ce6e  mov     ebx, eax
0x18008ce70  test    eax, eax
0x18008ce72  jle     short loc_18008CE7D
0x18008ce74  movzx   ebx, ax
0x18008ce77  or      ebx, 80070000h
0x18008ce7d  test    ebx, ebx
0x18008ce7f  mov     [rsp+130h+var_EC], 55h ; 'U'
0x18008ce87  mov     eax, 8000FFFFh
0x18008ce8c  cmovns  ebx, eax
0x18008ce8f  jmp     short loc_18008CEE7
0x18008ce91  call    Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline
0x18008ce96  test    eax, eax
0x18008ce98  jz      short loc_18008CEDD
0x18008ce9a  mov     rcx, [rsp+130h+TokenHandle]
0x18008ce9f  lea     rax, [rsp+130h+var_C8]
0x18008cea4  mov     [rsp+130h+var_F8], rsi
0x18008cea9  xor     r9d, r9d
0x18008ceac  mov     [rsp+130h+var_100], rax
0x18008ceb1  xor     r8d, r8d
0x18008ceb4  mov     [rsp+130h+var_108], rsi
0x18008ceb9  xor     edx, edx
0x18008cebb  mov     [rsp+130h+var_110], rsi
0x18008cec0  call    cs:__imp_RtlQueryPackageClaims
0x18008cec6  test    eax, eax
0x18008cec8  js      short loc_18008CF43
0x18008ceca  test    byte ptr cs:xmmword_180113B20+3, 20h
0x18008ced1  jz      short loc_18008CEDD
0x18008ced3  mov     r9d, dword ptr [rsp+130h+var_C8]
0x18008ced8  call    WPP_SF_L
0x18008cedd  mov     eax, [rsp+130h+var_E4]
0x18008cee1  mov     cs:?g_dwProcessSessionId@@3KA, eax; ulong g_dwProcessSessionId
0x18008cee7  mov     ecx, ebx
0x18008cee9  call    WX_WIN32_FROM_HR
0x18008ceee  mov     ecx, eax; dwErrCode
0x18008cef0  call    cs:__imp_SetLastError
0x18008cef6  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x18008cefb  test    ebx, ebx
0x18008cefd  mov     edi, esi
0x18008ceff  setns   dil
0x18008cf03  test    rcx, rcx
0x18008cf06  jz      short loc_18008CF13
0x18008cf08  call    cs:__imp_CloseHandle
0x18008cf0e  mov     [rsp+130h+TokenHandle], rsi
0x18008cf13  lea     rcx, [rsp+130h+var_E0]; this
0x18008cf18  call    ??1AutoTokenImpersonate@@QEAA@XZ; AutoTokenImpersonate::~AutoTokenImpersonate(void)
0x18008cf1d  mov     eax, edi
0x18008cf1f  mov     rcx, [rbp+30h+var_20]
0x18008cf23  xor     rcx, rsp; StackCookie
0x18008cf26  call    __security_check_cookie
0x18008cf2b  lea     r11, [rsp+130h+var_10]
0x18008cf33  mov     rbx, [r11+20h]
0x18008cf37  mov     rsi, [r11+28h]
0x18008cf3b  mov     rsp, r11
0x18008cf3e  pop     r14
0x18008cf40  pop     rdi
0x18008cf41  pop     rbp
0x18008cf42  retn
0x18008cf43  cmp     eax, 0C0000225h
0x18008cf48  jz      short loc_18008CEDD
0x18008cf4a  mov     ecx, eax; int
0x18008cf4c  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18008cf51  mov     ebx, eax
0x18008cf53  test    eax, eax
0x18008cf55  jns     short loc_18008CEDD
0x18008cf57  mov     [rsp+130h+var_EC], 6Bh ; 'k'
0x18008cf5f  jmp     short loc_18008CEE7
```
