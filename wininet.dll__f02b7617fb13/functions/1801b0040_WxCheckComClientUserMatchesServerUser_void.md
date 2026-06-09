# WxCheckComClientUserMatchesServerUser(void)

- ea: `0x1801b0040`
- end: `0x1801b017e`
- name: `?WxCheckComClientUserMatchesServerUser@@YAJXZ`
- size: `318`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180143290`
- `0x1801558b0`
- `0x1801559c0`
- `0x180155a60`

## callees

- `0x180019ac4`
- `0x1800701d0`
- `0x18011fba0`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801b0040`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b009e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b009e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b00b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b00b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b015d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b015d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b00e7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b00ef`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b00e7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801b00ef`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801b0085`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801b0085`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801b0138`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801b0138`

## pseudocode

```c
__int64 WxCheckComClientUserMatchesServerUser(void)
{
  int TokenUserSID; // ebx
  HANDLE CurrentThread; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  int LastError; // eax
  unsigned int v5; // r8d
  PSID pSid2; // [rsp+20h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid1[80]; // [rsp+30h] [rbp-68h] BYREF

  TokenHandle = 0;
  pSid2 = 0;
  memset_0(pSid1, 0, 0x44u);
  TokenUserSID = CoImpersonateClient();
  if ( TokenUserSID >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    {
      CoRevertToSelf();
      TokenUserSID = WxGetTokenUserSID(TokenHandle, pSid1, v5);
      if ( TokenUserSID >= 0 )
      {
        TokenUserSID = WxGetProcessUserSID((struct _SID **)&pSid2);
        if ( TokenUserSID >= 0 )
        {
          if ( EqualSid(pSid1, pSid2) )
          {
            TokenUserSID = 0;
          }
          else
          {
            HIDWORD(pSid2) = 965;
            TokenUserSID = -2147024891;
          }
        }
        else
        {
          HIDWORD(pSid2) = 959;
        }
      }
      else
      {
        HIDWORD(pSid2) = 953;
      }
    }
    else
    {
      LastError = WxGetLastError(v3, v2);
      TokenUserSID = LastError;
      if ( LastError > 0 )
        TokenUserSID = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(pSid2) = 944;
      if ( TokenUserSID >= 0 )
        TokenUserSID = -2147418113;
      CoRevertToSelf();
    }
  }
  else
  {
    HIDWORD(pSid2) = 941;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)TokenUserSID;
}

```

## disassembly

```asm
0x1801b0040  push    rbx
0x1801b0042  sub     rsp, 90h
0x1801b0049  mov     rax, cs:__security_cookie
0x1801b0050  xor     rax, rsp
0x1801b0053  mov     [rsp+98h+var_18], rax
0x1801b005b  xor     edx, edx; Val
0x1801b005d  mov     dword ptr [rsp+98h+pSid2+4], 0
0x1801b0065  lea     rcx, [rsp+98h+pSid1]; void *
0x1801b006a  mov     [rsp+98h+TokenHandle], 0
0x1801b0073  mov     qword ptr [rsp+20h], 0
0x1801b007c  lea     r8d, [rdx+44h]; Size
0x1801b0080  call    memset_0
0x1801b0085  call    cs:__imp_CoImpersonateClient
0x1801b008b  mov     ebx, eax
0x1801b008d  test    eax, eax
0x1801b008f  jns     short loc_1801B009E
0x1801b0091  mov     dword ptr [rsp+98h+pSid2+4], 3ADh
0x1801b0099  jmp     loc_1801B0153
0x1801b009e  call    cs:__imp_GetCurrentThread
0x1801b00a4  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x1801b00a9  mov     edx, 20008h; DesiredAccess
0x1801b00ae  mov     rcx, rax; ThreadHandle
0x1801b00b1  mov     r8d, 1; OpenAsSelf
0x1801b00b7  call    cs:__imp_OpenThreadToken
0x1801b00bd  test    eax, eax
0x1801b00bf  jnz     short loc_1801B00EF
0x1801b00c1  call    WxGetLastError
0x1801b00c6  mov     ebx, eax
0x1801b00c8  test    eax, eax
0x1801b00ca  jle     short loc_1801B00D5
0x1801b00cc  movzx   ebx, ax
0x1801b00cf  or      ebx, 80070000h
0x1801b00d5  test    ebx, ebx
0x1801b00d7  mov     dword ptr [rsp+98h+pSid2+4], 3B0h
0x1801b00df  mov     eax, 8000FFFFh
0x1801b00e4  cmovns  ebx, eax
0x1801b00e7  call    cs:__imp_CoRevertToSelf
0x1801b00ed  jmp     short loc_1801B0153
0x1801b00ef  call    cs:__imp_CoRevertToSelf
0x1801b00f5  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x1801b00fa  lea     rdx, [rsp+98h+pSid1]; pDestinationSid
0x1801b00ff  call    ?WxGetTokenUserSID@@YAJPEAXPEAU_SID@@K@Z; WxGetTokenUserSID(void *,_SID *,ulong)
0x1801b0104  mov     ebx, eax
0x1801b0106  test    eax, eax
0x1801b0108  jns     short loc_1801B0114
0x1801b010a  mov     dword ptr [rsp+98h+pSid2+4], 3B9h
0x1801b0112  jmp     short loc_1801B0153
0x1801b0114  lea     rcx, [rsp+98h+pSid2]; struct _SID **
0x1801b0119  call    ?WxGetProcessUserSID@@YAJPEAPEAU_SID@@@Z; WxGetProcessUserSID(_SID * *)
0x1801b011e  mov     ebx, eax
0x1801b0120  test    eax, eax
0x1801b0122  jns     short loc_1801B012E
0x1801b0124  mov     dword ptr [rsp+98h+pSid2+4], 3BFh
0x1801b012c  jmp     short loc_1801B0153
0x1801b012e  mov     rdx, [rsp+98h+pSid2]; pSid2
0x1801b0133  lea     rcx, [rsp+98h+pSid1]; pSid1
0x1801b0138  call    cs:__imp_EqualSid
0x1801b013e  test    eax, eax
0x1801b0140  jnz     short loc_1801B0151
0x1801b0142  mov     dword ptr [rsp+98h+pSid2+4], 3C5h
0x1801b014a  mov     ebx, 80070005h
0x1801b014f  jmp     short loc_1801B0153
0x1801b0151  xor     ebx, ebx
0x1801b0153  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x1801b0158  test    rcx, rcx
0x1801b015b  jz      short loc_1801B0163
0x1801b015d  call    cs:__imp_CloseHandle
0x1801b0163  mov     eax, ebx
0x1801b0165  mov     rcx, [rsp+98h+var_18]
0x1801b016d  xor     rcx, rsp; StackCookie
0x1801b0170  call    __security_check_cookie
0x1801b0175  add     rsp, 90h
0x1801b017c  pop     rbx
0x1801b017d  retn
```
