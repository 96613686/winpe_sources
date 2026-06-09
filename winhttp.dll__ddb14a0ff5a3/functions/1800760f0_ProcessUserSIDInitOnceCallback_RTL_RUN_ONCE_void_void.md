# _ProcessUserSIDInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800760f0`
- end: `0x1800763e1`
- name: `?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `753`
- prototype: `_BOOL8 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180041eb0`
- `0x180058f80`
- `0x1800760f0`
- `0x1800763e8`
- `0x1800764d0`
- `0x1800765a0`
- `0x1800766cc`
- `0x1800767d0`
- `0x180076998`
- `0x180089764`
- `0x18009ae90`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800dabdc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076294`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800762e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180076294`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800762e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007618b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007618b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007619e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007619e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007638e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007638e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800761a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007629e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800761a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007629e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800762f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800763a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800763a6`
- `ntdll!RtlQueryPackageClaims` at `0x18007634a`
- `ntdll!RtlQueryPackageClaims` at `0x18007634a`

## pseudocode

```c
_BOOL8 __fastcall _ProcessUserSIDInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  void *v4; // rdx
  signed int TokenUserSID; // ebx
  HANDLE CurrentProcess; // rax
  unsigned int v7; // r8d
  signed int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  signed int v11; // eax
  signed int LastError; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  DWORD v17; // eax
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSourceSid[80]; // [rsp+70h] [rbp-90h] BYREF
  _SID v26; // [rsp+C0h] [rbp-40h] BYREF

  v22[1] = 0;
  v22[0] = 0;
  TokenHandle = 0;
  memset_0(pSourceSid, 0, 0x44u);
  memset_0(&v26, 0, 0x44u);
  v20 = 0;
  v21 = 0;
  v19 = 4096;
  v24 = 0;
  if ( Context )
    *Context = 0;
  TokenUserSID = AutoTokenImpersonate::Impersonate((AutoTokenImpersonate *)v22, v4);
  if ( TokenUserSID >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      TokenUserSID = WxGetTokenUserSID(TokenHandle, pSourceSid, v7);
      if ( TokenUserSID >= 0 )
      {
        TokenUserSID = WxIsTokenAppContainer(TokenHandle, &v20);
        if ( TokenUserSID >= 0 )
        {
          v10 = v20;
          if ( v20 && (TokenUserSID = WxGetTokenAppContainerSID(TokenHandle, &v26, v9), TokenUserSID < 0) )
          {
            HIDWORD(v19) = 72;
          }
          else
          {
            TokenUserSID = WxGetTokenSessionId(TokenHandle, &v21);
            if ( TokenUserSID >= 0 )
            {
              TokenUserSID = WxGetTokenIntegrityLevel(TokenHandle, (unsigned int *)&v19);
              if ( TokenUserSID >= 0 )
              {
                if ( CopySid(0x44u, &g_rgbProcessUserSID, pSourceSid) )
                {
                  TokenUserSID = 0;
                  if ( !v10 || (g_fIsProcessAppContainer = 1, CopySid(0x44u, &g_rgbAppContainerSID, &v26)) )
                  {
                    if ( (unsigned int)Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline() )
                    {
                      v13 = RtlQueryPackageClaims(TokenHandle, 0, 0, 0, 0, 0, &v24, 0, v19);
                      if ( v13 < 0 )
                      {
                        if ( v13 != -1073741275 )
                        {
                          TokenUserSID = HRESULT_FROM_NTSTATUS(v13);
                          if ( TokenUserSID < 0 )
                            HIDWORD(v19) = 107;
                        }
                      }
                      else if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
                      {
                        WPP_SF_L(v15, v14, v16, (unsigned int)v24);
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    TokenUserSID = LastError;
                    if ( LastError > 0 )
                      TokenUserSID = (unsigned __int16)LastError | 0x80070000;
                    HIDWORD(v19) = 85;
                    if ( TokenUserSID >= 0 )
                      TokenUserSID = -2147418113;
                  }
                }
                else
                {
                  v11 = GetLastError();
                  TokenUserSID = v11;
                  if ( v11 > 0 )
                    TokenUserSID = (unsigned __int16)v11 | 0x80070000;
                  HIDWORD(v19) = 79;
                  if ( TokenUserSID >= 0 )
                    TokenUserSID = -2147418113;
                }
              }
              else
              {
                HIDWORD(v19) = 77;
              }
            }
            else
            {
              HIDWORD(v19) = 75;
            }
          }
        }
        else
        {
          HIDWORD(v19) = 69;
        }
      }
      else
      {
        HIDWORD(v19) = 67;
      }
    }
    else
    {
      v8 = GetLastError();
      TokenUserSID = v8;
      if ( v8 > 0 )
        TokenUserSID = (unsigned __int16)v8 | 0x80070000;
      HIDWORD(v19) = 65;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
    }
  }
  else
  {
    HIDWORD(v19) = 63;
  }
  v17 = WX_WIN32_FROM_HR((unsigned int)TokenUserSID);
  SetLastError(v17);
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  AutoTokenImpersonate::~AutoTokenImpersonate(v22);
  return TokenUserSID >= 0;
}

```

## disassembly

```asm
0x1800760f0  mov     [rsp-8+arg_0], rbx
0x1800760f5  mov     [rsp-8+arg_8], rsi
0x1800760fa  push    rbp
0x1800760fb  push    rdi
0x1800760fc  push    r14
0x1800760fe  lea     rbp, [rsp-20h]
0x180076103  sub     rsp, 120h
0x18007610a  mov     rax, cs:__security_cookie
0x180076111  xor     rax, rsp
0x180076114  mov     [rbp+30h+var_20], rax
0x180076118  xor     esi, esi
0x18007611a  lea     rcx, [rsp+130h+pSourceSid]; void *
0x18007611f  mov     rbx, r8
0x180076122  mov     [rsp+130h+var_EC], esi
0x180076126  xor     edx, edx; Val
0x180076128  mov     [rsp+130h+var_D8], rsi
0x18007612d  mov     [rsp+130h+var_E0], rsi
0x180076132  lea     r14d, [rsi+44h]
0x180076136  mov     [rsp+130h+TokenHandle], rsi
0x18007613b  mov     r8d, r14d; Size
0x18007613e  call    memset_0
0x180076143  mov     r8d, r14d; Size
0x180076146  lea     rcx, [rbp+30h+var_70]; void *
0x18007614a  xor     edx, edx; Val
0x18007614c  call    memset_0
0x180076151  mov     [rsp+130h+var_E8], esi
0x180076155  mov     [rsp+130h+var_E4], esi
0x180076159  mov     [rsp+130h+var_F0], 1000h
0x180076161  mov     [rsp+130h+var_C8], rsi
0x180076166  test    rbx, rbx
0x180076169  jz      short loc_18007616E
0x18007616b  mov     [rbx], rsi
0x18007616e  lea     rcx, [rsp+130h+var_E0]; this
0x180076173  call    ?Impersonate@AutoTokenImpersonate@@QEAAJPEAX@Z; AutoTokenImpersonate::Impersonate(void *)
0x180076178  mov     ebx, eax
0x18007617a  test    eax, eax
0x18007617c  jns     short loc_18007618B
0x18007617e  mov     [rsp+130h+var_EC], 3Fh ; '?'
0x180076186  jmp     loc_180076385
0x18007618b  call    cs:__imp_GetCurrentProcess
0x180076191  lea     r8, [rsp+130h+TokenHandle]; TokenHandle
0x180076196  mov     edx, 20008h; DesiredAccess
0x18007619b  mov     rcx, rax; ProcessHandle
0x18007619e  call    cs:__imp_OpenProcessToken
0x1800761a4  test    eax, eax
0x1800761a6  jnz     short loc_1800761D4
0x1800761a8  call    cs:__imp_GetLastError
0x1800761ae  mov     ebx, eax
0x1800761b0  test    eax, eax
0x1800761b2  jle     short loc_1800761BD
0x1800761b4  movzx   ebx, ax
0x1800761b7  or      ebx, 80070000h
0x1800761bd  test    ebx, ebx
0x1800761bf  mov     [rsp+130h+var_EC], 41h ; 'A'
0x1800761c7  mov     eax, 8000FFFFh
0x1800761cc  cmovns  ebx, eax
0x1800761cf  jmp     loc_180076385
0x1800761d4  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x1800761d9  lea     rdx, [rsp+130h+pSourceSid]; pDestinationSid
0x1800761de  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x1800761e3  mov     ebx, eax
0x1800761e5  test    eax, eax
0x1800761e7  jns     short loc_1800761F6
0x1800761e9  mov     [rsp+130h+var_EC], 43h ; 'C'
0x1800761f1  jmp     loc_180076385
0x1800761f6  mov     rcx, [rsp+130h+TokenHandle]; void *
0x1800761fb  lea     rdx, [rsp+130h+var_E8]; int *
0x180076200  call    ?WxIsTokenAppContainer@@YAJPEAXPEAH@Z; WxIsTokenAppContainer(void *,int *)
0x180076205  mov     ebx, eax
0x180076207  test    eax, eax
0x180076209  jns     short loc_180076218
0x18007620b  mov     [rsp+130h+var_EC], 45h ; 'E'
0x180076213  jmp     loc_180076385
0x180076218  mov     edi, [rsp+130h+var_E8]
0x18007621c  test    edi, edi
0x18007621e  jz      short loc_180076241
0x180076220  mov     rcx, [rsp+130h+TokenHandle]; void *
0x180076225  lea     rdx, [rbp+30h+var_70]; struct _SID *
0x180076229  call    ?WxGetTokenAppContainerSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenAppContainerSID(void *,_SID *,ulong)
0x18007622e  mov     ebx, eax
0x180076230  test    eax, eax
0x180076232  jns     short loc_180076241
0x180076234  mov     [rsp+130h+var_EC], 48h ; 'H'
0x18007623c  jmp     loc_180076385
0x180076241  mov     rcx, [rsp+130h+TokenHandle]; void *
0x180076246  lea     rdx, [rsp+130h+var_E4]; unsigned int *
0x18007624b  call    ?WxGetTokenSessionId@@YAJPEAXPEAK@Z; WxGetTokenSessionId(void *,ulong *)
0x180076250  mov     ebx, eax
0x180076252  test    eax, eax
0x180076254  jns     short loc_180076263
0x180076256  mov     [rsp+130h+var_EC], 4Bh ; 'K'
0x18007625e  jmp     loc_180076385
0x180076263  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180076268  lea     rdx, [rsp+130h+var_F0]; unsigned int *
0x18007626d  call    ?WxGetTokenIntegrityLevel@@YAJPEAXPEAK@Z; WxGetTokenIntegrityLevel(void *,ulong *)
0x180076272  mov     ebx, eax
0x180076274  test    eax, eax
0x180076276  jns     short loc_180076285
0x180076278  mov     [rsp+130h+var_EC], 4Dh ; 'M'
0x180076280  jmp     loc_180076385
0x180076285  lea     r8, [rsp+130h+pSourceSid]; pSourceSid
0x18007628a  mov     ecx, r14d; nDestinationSidLength
0x18007628d  lea     rdx, ?g_rgbProcessUserSID@@3PAEA; pDestinationSid
0x180076294  call    cs:__imp_CopySid
0x18007629a  test    eax, eax
0x18007629c  jnz     short loc_1800762CA
0x18007629e  call    cs:__imp_GetLastError
0x1800762a4  mov     ebx, eax
0x1800762a6  test    eax, eax
0x1800762a8  jle     short loc_1800762B3
0x1800762aa  movzx   ebx, ax
0x1800762ad  or      ebx, 80070000h
0x1800762b3  test    ebx, ebx
0x1800762b5  mov     [rsp+130h+var_EC], 4Fh ; 'O'
0x1800762bd  mov     eax, 8000FFFFh
0x1800762c2  cmovns  ebx, eax
0x1800762c5  jmp     loc_180076385
0x1800762ca  mov     ebx, esi
0x1800762cc  test    edi, edi
0x1800762ce  jz      short loc_18007631B
0x1800762d0  lea     r8, [rbp+30h+var_70]; pSourceSid
0x1800762d4  mov     cs:?g_fIsProcessAppContainer@@3HA, 1; int g_fIsProcessAppContainer
0x1800762de  lea     rdx, ?g_rgbAppContainerSID@@3PAEA; pDestinationSid
0x1800762e5  mov     ecx, r14d; nDestinationSidLength
0x1800762e8  call    cs:__imp_CopySid
0x1800762ee  test    eax, eax
0x1800762f0  jnz     short loc_18007631B
0x1800762f2  call    cs:__imp_GetLastError
0x1800762f8  mov     ebx, eax
0x1800762fa  test    eax, eax
0x1800762fc  jle     short loc_180076307
0x1800762fe  movzx   ebx, ax
0x180076301  or      ebx, 80070000h
0x180076307  test    ebx, ebx
0x180076309  mov     [rsp+130h+var_EC], 55h ; 'U'
0x180076311  mov     eax, 8000FFFFh
0x180076316  cmovns  ebx, eax
0x180076319  jmp     short loc_180076385
0x18007631b  call    Feature_WinInetCacheAppBrokerForUWPMediumIL__private_IsEnabledDeviceUsageNoInline
0x180076320  test    eax, eax
0x180076322  jz      short loc_180076385
0x180076324  mov     rcx, [rsp+130h+TokenHandle]
0x180076329  lea     rax, [rsp+130h+var_C8]
0x18007632e  mov     [rsp+130h+var_F8], rsi
0x180076333  xor     r9d, r9d
0x180076336  mov     [rsp+130h+var_100], rax
0x18007633b  xor     r8d, r8d
0x18007633e  mov     [rsp+130h+var_108], rsi
0x180076343  xor     edx, edx
0x180076345  mov     [rsp+130h+var_110], rsi
0x18007634a  call    cs:__imp_RtlQueryPackageClaims
0x180076350  test    eax, eax
0x180076352  js      short loc_180076369
0x180076354  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18007635b  jz      short loc_180076385
0x18007635d  mov     r9d, dword ptr [rsp+130h+var_C8]
0x180076362  call    WPP_SF_L
0x180076367  jmp     short loc_180076385
0x180076369  cmp     eax, 0C0000225h
0x18007636e  jz      short loc_180076385
0x180076370  mov     ecx, eax; int
0x180076372  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180076377  mov     ebx, eax
0x180076379  test    eax, eax
0x18007637b  jns     short loc_180076385
0x18007637d  mov     [rsp+130h+var_EC], 6Bh ; 'k'
0x180076385  mov     ecx, ebx
0x180076387  call    WX_WIN32_FROM_HR
0x18007638c  mov     ecx, eax; dwErrCode
0x18007638e  call    cs:__imp_SetLastError
0x180076394  mov     rcx, [rsp+130h+TokenHandle]; hObject
0x180076399  test    ebx, ebx
0x18007639b  mov     edi, esi
0x18007639d  setns   dil
0x1800763a1  test    rcx, rcx
0x1800763a4  jz      short loc_1800763B1
0x1800763a6  call    cs:__imp_CloseHandle
0x1800763ac  mov     [rsp+130h+TokenHandle], rsi
0x1800763b1  lea     rcx, [rsp+130h+var_E0]; this
0x1800763b6  call    ??1AutoTokenImpersonate@@QEAA@XZ; AutoTokenImpersonate::~AutoTokenImpersonate(void)
0x1800763bb  mov     eax, edi
0x1800763bd  mov     rcx, [rbp+30h+var_20]
0x1800763c1  xor     rcx, rsp; StackCookie
0x1800763c4  call    __security_check_cookie
0x1800763c9  lea     r11, [rsp+130h+var_10]
0x1800763d1  mov     rbx, [r11+20h]
0x1800763d5  mov     rsi, [r11+28h]
0x1800763d9  mov     rsp, r11
0x1800763dc  pop     r14
0x1800763de  pop     rdi
0x1800763df  pop     rbp
0x1800763e0  retn
```
