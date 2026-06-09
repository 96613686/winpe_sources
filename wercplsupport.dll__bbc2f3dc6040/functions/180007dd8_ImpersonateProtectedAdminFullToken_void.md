# ImpersonateProtectedAdminFullToken(void)

- ea: `0x180007dd8`
- end: `0x180007fda`
- name: `?ImpersonateProtectedAdminFullToken@@YAJXZ`
- size: `514`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007fe0`

## callees

- `0x180002850`
- `0x180002a48`
- `0x180006c9c`
- `0x180007dd8`
- `0x180011f0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007f5a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007e47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007e5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007e5b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007df0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180007df0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007eb5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007ec0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007eb5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180007ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fcc`

## pseudocode

```c
__int64 ImpersonateProtectedAdminFullToken(void)
{
  int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  void **v3; // rbx
  HANDLE CurrentThread; // rax
  signed int v5; // eax
  void **v6; // rax
  int v7; // ebx
  signed int LastError; // eax
  HANDLE hToken; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  hObject = 0;
  hToken = 0;
  v0 = CoImpersonateClient();
  if ( v0 >= 0 )
  {
    v3 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xF01FFu, 0, v3) )
    {
      CoRevertToSelf();
      v6 = (void **)tlx::replace<tlx::file_handle_traits>(&hToken);
      v7 = LUAGetElevatedToken(hObject, v6);
      if ( v7 >= 0 )
      {
        if ( hToken == (HANDLE)-1LL || (char *)hToken + 1 == HANDLE_FLAG_INHERIT )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids);
          v0 = -2147467259;
        }
        else if ( ImpersonateLoggedOnUser(hToken) )
        {
          v0 = 0;
        }
        else
        {
          LastError = GetLastError();
          v0 = LastError;
          if ( LastError > 0 )
            v0 = (unsigned __int16)LastError | 0x80070000;
          if ( v0 >= 0 )
            v0 = -2147467259;
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v2 = 14;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v0 = v7 | 0x10000000;
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v2 = 12;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v5 = GetLastError();
      v0 = v5;
      if ( v5 > 0 )
        v0 = (unsigned __int16)v5 | 0x80070000;
      if ( v0 >= 0 )
        v0 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids,
          (unsigned int)v0);
      CoRevertToSelf();
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 10;
LABEL_5:
      WPP_SF_d(v1[2], v2, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids, (unsigned int)v0);
    }
  }
  if ( (unsigned __int64)hToken + 1 > 1 )
    CloseHandle(hToken);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180007dd8  push    rbx
0x180007dda  sub     rsp, 20h
0x180007dde  mov     [rsp+28h+hObject], 0
0x180007de7  mov     [rsp+28h+hToken], 0
0x180007df0  call    cs:__imp_CoImpersonateClient
0x180007df6  mov     ebx, eax
0x180007df8  test    eax, eax
0x180007dfa  jns     short loc_180007E3A
0x180007dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e03  lea     rax, WPP_GLOBAL_Control
0x180007e0a  cmp     rcx, rax
0x180007e0d  jz      loc_180007FA8
0x180007e13  test    byte ptr [rcx+1Ch], 1
0x180007e17  jz      loc_180007FA8
0x180007e1d  mov     edx, 0Ah
0x180007e22  mov     rcx, [rcx+10h]
0x180007e26  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180007e2d  mov     r9d, ebx
0x180007e30  call    WPP_SF_d
0x180007e35  jmp     loc_180007FA8
0x180007e3a  lea     rcx, [rsp+28h+hObject]
0x180007e3f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180007e44  mov     rbx, rax
0x180007e47  call    cs:__imp_GetCurrentThread
0x180007e4d  mov     r9, rbx; TokenHandle
0x180007e50  xor     r8d, r8d; OpenAsSelf
0x180007e53  mov     rcx, rax; ThreadHandle
0x180007e56  mov     edx, 0F01FFh; DesiredAccess
0x180007e5b  call    cs:__imp_OpenThreadToken
0x180007e61  test    eax, eax
0x180007e63  jnz     short loc_180007EC0
0x180007e65  call    cs:__imp_GetLastError
0x180007e6b  mov     ebx, eax
0x180007e6d  test    eax, eax
0x180007e6f  jle     short loc_180007E7A
0x180007e71  movzx   ebx, ax
0x180007e74  or      ebx, 80070000h
0x180007e7a  test    ebx, ebx
0x180007e7c  mov     eax, 80004005h
0x180007e81  cmovns  ebx, eax
0x180007e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e8b  lea     rax, WPP_GLOBAL_Control
0x180007e92  cmp     rcx, rax
0x180007e95  jz      short loc_180007EB5
0x180007e97  test    byte ptr [rcx+1Ch], 1
0x180007e9b  jz      short loc_180007EB5
0x180007e9d  mov     rcx, [rcx+10h]
0x180007ea1  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180007ea8  mov     edx, 0Bh
0x180007ead  mov     r9d, ebx
0x180007eb0  call    WPP_SF_d
0x180007eb5  call    cs:__imp_CoRevertToSelf
0x180007ebb  jmp     loc_180007FA8
0x180007ec0  call    cs:__imp_CoRevertToSelf
0x180007ec6  lea     rcx, [rsp+28h+hToken]
0x180007ecb  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180007ed0  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x180007ed5  mov     rdx, rax; NewTokenHandle
0x180007ed8  call    LUAGetElevatedToken
0x180007edd  mov     ebx, eax
0x180007edf  test    eax, eax
0x180007ee1  jns     short loc_180007F12
0x180007ee3  bts     ebx, 1Ch
0x180007ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eee  lea     rax, WPP_GLOBAL_Control
0x180007ef5  cmp     rcx, rax
0x180007ef8  jz      loc_180007FA8
0x180007efe  test    byte ptr [rcx+1Ch], 1
0x180007f02  jz      loc_180007FA8
0x180007f08  mov     edx, 0Ch
0x180007f0d  jmp     loc_180007E22
0x180007f12  mov     rax, [rsp+28h+hToken]
0x180007f17  inc     rax
0x180007f1a  cmp     rax, 1
0x180007f1e  ja      short loc_180007F55
0x180007f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f27  lea     rax, WPP_GLOBAL_Control
0x180007f2e  cmp     rcx, rax
0x180007f31  jz      short loc_180007F4E
0x180007f33  test    byte ptr [rcx+1Ch], 1
0x180007f37  jz      short loc_180007F4E
0x180007f39  mov     rcx, [rcx+10h]
0x180007f3d  lea     r8, WPP_7e3bbdf5c65235aea29c330bbc287d86_Traceguids
0x180007f44  mov     edx, 0Dh
0x180007f49  call    WPP_SF_
0x180007f4e  mov     ebx, 80004005h
0x180007f53  jmp     short loc_180007FA8
0x180007f55  mov     rcx, [rsp+28h+hToken]; hToken
0x180007f5a  call    cs:__imp_ImpersonateLoggedOnUser
0x180007f60  test    eax, eax
0x180007f62  jnz     short loc_180007FA6
0x180007f64  call    cs:__imp_GetLastError
0x180007f6a  mov     ebx, eax
0x180007f6c  test    eax, eax
0x180007f6e  jle     short loc_180007F79
0x180007f70  movzx   ebx, ax
0x180007f73  or      ebx, 80070000h
0x180007f79  test    ebx, ebx
0x180007f7b  mov     eax, 80004005h
0x180007f80  cmovns  ebx, eax
0x180007f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f8a  lea     rax, WPP_GLOBAL_Control
0x180007f91  cmp     rcx, rax
0x180007f94  jz      short loc_180007FA8
0x180007f96  test    byte ptr [rcx+1Ch], 1
0x180007f9a  jz      short loc_180007FA8
0x180007f9c  mov     edx, 0Eh
0x180007fa1  jmp     loc_180007E22
0x180007fa6  xor     ebx, ebx
0x180007fa8  mov     rcx, [rsp+28h+hToken]; hObject
0x180007fad  lea     rax, [rcx+1]
0x180007fb1  cmp     rax, 1
0x180007fb5  jbe     short loc_180007FBD
0x180007fb7  call    cs:__imp_CloseHandle
0x180007fbd  mov     rcx, [rsp+28h+hObject]; hObject
0x180007fc2  lea     rax, [rcx+1]
0x180007fc6  cmp     rax, 1
0x180007fca  jbe     short loc_180007FD2
0x180007fcc  call    cs:__imp_CloseHandle
0x180007fd2  mov     eax, ebx
0x180007fd4  add     rsp, 20h
0x180007fd8  pop     rbx
0x180007fd9  retn
```
