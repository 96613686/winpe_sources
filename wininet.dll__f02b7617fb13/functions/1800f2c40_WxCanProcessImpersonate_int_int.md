# WxCanProcessImpersonate(int *,int *)

- ea: `0x1800f2c40`
- end: `0x1800f2f25`
- name: `?WxCanProcessImpersonate@@YAJPEAH0@Z`
- size: `741`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008380`
- `0x180099100`
- `0x1800f2b0c`

## callees

- `0x180025980`
- `0x180027ec0`
- `0x1800701d0`
- `0x1800f2c40`
- `0x18014a7a0`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2cee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2cee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2cc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2cc9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2ce0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2ce0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f2d12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f2d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f2cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f2cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2de4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2de4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f2d3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f2d7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f2d3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f2d7b`

## pseudocode

```c
__int64 __fastcall WxCanProcessImpersonate(int *a1, int *a2)
{
  DWORD v4; // esi
  __int64 v5; // rbx
  HANDLE CurrentThread; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  HANDLE CurrentProcess; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _DWORD *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 i; // rcx
  signed int v18; // edi
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 Heap; // rax
  int LastError; // eax
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD TokenInformation[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  _BYTE v32[512]; // [rsp+90h] [rbp-70h] BYREF

  TokenHandle = 0;
  hObject = 0;
  v4 = 504;
  v31 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v30 = 0;
  memset_0(v32, 0, 0x1F8u);
  v5 = 0;
  *a1 = 0;
  *a2 = 0;
  v25 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
  {
    *a1 = 1;
    *a2 = 1;
    v18 = 0;
    goto LABEL_17;
  }
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &hObject) )
    {
      if ( GetTokenInformation(hObject, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
      {
        if ( HIDWORD(v30) > 0x28 )
        {
          v4 = 12 * (HIDWORD(v30) + 2);
          Heap = WxAllocateHeapEx(v4, v4);
          v14 = (_DWORD *)Heap;
          if ( !Heap )
          {
            v18 = -2147024882;
LABEL_15:
            if ( v5 )
              WxFreeHeapEx(&v25);
            goto LABEL_17;
          }
          v5 = Heap;
          v25 = Heap;
        }
        else
        {
          v14 = v32;
        }
        ReturnLength = 0;
        if ( GetTokenInformation(hObject, TokenPrivileges, v14, v4, &ReturnLength) )
        {
          for ( i = 0; (unsigned int)i < *v14; i = (unsigned int)(i + 1) )
          {
            if ( v14[3 * i + 1] == 29 && !v14[3 * i + 2] )
            {
              if ( (v14[3 * i + 3] & 4) == 0 )
                *a1 = 1;
              break;
            }
          }
          v18 = 0;
        }
        else
        {
          LastError = WxGetLastError(v16, v15);
          v18 = LastError;
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0x80070000;
          if ( v18 >= 0 )
            v18 = -2147418113;
        }
        goto LABEL_15;
      }
      v22 = WxGetLastError(v13, v12);
      v18 = v22;
      if ( v22 > 0 )
        v18 = (unsigned __int16)v22 | 0x80070000;
      if ( v18 >= 0 )
        v18 = -2147418113;
    }
    else
    {
      v20 = WxGetLastError(v11, v10);
      v18 = v20;
      if ( v20 > 0 )
        v18 = (unsigned __int16)v20 | 0x80070000;
      if ( v18 >= 0 )
        v18 = -2147418113;
    }
  }
  else
  {
    v21 = WxGetLastError(v8, v7);
    v18 = v21;
    if ( v21 > 0 )
      v18 = (unsigned __int16)v21 | 0x80070000;
    if ( v18 >= 0 )
      v18 = -2147418113;
  }
LABEL_17:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800f2c40  mov     [rsp-8+arg_10], rbx
0x1800f2c45  mov     [rsp-8+arg_18], rsi
0x1800f2c4a  push    rbp
0x1800f2c4b  push    rdi
0x1800f2c4c  push    r14
0x1800f2c4e  lea     rbp, [rsp-1A0h]
0x1800f2c56  sub     rsp, 2A0h
0x1800f2c5d  mov     rax, cs:__security_cookie
0x1800f2c64  xor     rax, rsp
0x1800f2c67  mov     [rbp+1B0h+var_20], rax
0x1800f2c6e  xorps   xmm0, xmm0
0x1800f2c71  mov     [rsp+2B0h+var_27C], 0
0x1800f2c79  mov     rdi, rdx
0x1800f2c7c  mov     [rsp+2B0h+TokenHandle], 0
0x1800f2c85  mov     r14, rcx
0x1800f2c88  mov     [rsp+2B0h+hObject], 0
0x1800f2c91  xor     eax, eax
0x1800f2c93  lea     rcx, [rbp+1B0h+var_220]; void *
0x1800f2c97  mov     esi, 1F8h
0x1800f2c9c  mov     [rbp+1B0h+var_228], rax
0x1800f2ca0  mov     r8d, esi; Size
0x1800f2ca3  xor     edx, edx; Val
0x1800f2ca5  movups  [rsp+2B0h+TokenInformation], xmm0
0x1800f2caa  movups  [rsp+2B0h+var_248], xmm0
0x1800f2caf  movups  [rsp+2B0h+var_238], xmm0
0x1800f2cb4  call    memset_0
0x1800f2cb9  xor     ebx, ebx
0x1800f2cbb  mov     [r14], ebx
0x1800f2cbe  mov     [rdi], ebx
0x1800f2cc0  mov     [rsp+2B0h+var_278], rbx
0x1800f2cc5  mov     [rsp+2B0h+var_270], ebx
0x1800f2cc9  call    cs:__imp_GetCurrentThread
0x1800f2ccf  lea     r9, [rsp+2B0h+TokenHandle]; TokenHandle
0x1800f2cd4  mov     edx, 20008h; DesiredAccess
0x1800f2cd9  mov     rcx, rax; ThreadHandle
0x1800f2cdc  lea     r8d, [rbx+1]; OpenAsSelf
0x1800f2ce0  call    cs:__imp_OpenThreadToken
0x1800f2ce6  test    eax, eax
0x1800f2ce8  jnz     loc_1800F2E13
0x1800f2cee  call    cs:__imp_GetLastError
0x1800f2cf4  cmp     eax, 3F0h
0x1800f2cf9  jnz     loc_1800F2E5F
0x1800f2cff  call    cs:__imp_GetCurrentProcess
0x1800f2d05  lea     r8, [rsp+2B0h+hObject]; TokenHandle
0x1800f2d0a  mov     edx, 20008h; DesiredAccess
0x1800f2d0f  mov     rcx, rax; ProcessHandle
0x1800f2d12  call    cs:__imp_OpenProcessToken
0x1800f2d18  test    eax, eax
0x1800f2d1a  jz      loc_1800F2E34
0x1800f2d20  mov     rcx, [rsp+2B0h+hObject]; TokenHandle
0x1800f2d25  lea     rax, [rsp+2B0h+var_270]
0x1800f2d2a  lea     r9d, [rbx+38h]; TokenInformationLength
0x1800f2d2e  mov     [rsp+2B0h+ReturnLength], rax; ReturnLength
0x1800f2d33  lea     r8, [rsp+2B0h+TokenInformation]; TokenInformation
0x1800f2d38  lea     edx, [rbx+0Ah]; TokenInformationClass
0x1800f2d3b  call    cs:__imp_GetTokenInformation
0x1800f2d41  test    eax, eax
0x1800f2d43  jz      loc_1800F2E8A
0x1800f2d49  mov     eax, dword ptr [rbp+1B0h+var_238+0Ch]
0x1800f2d4c  cmp     eax, 28h ; '('
0x1800f2d4f  ja      loc_1800F2EB5
0x1800f2d55  lea     rdi, [rbp+1B0h+var_220]
0x1800f2d59  mov     rcx, [rsp+2B0h+hObject]; TokenHandle
0x1800f2d5e  lea     rax, [rsp+2B0h+var_270]
0x1800f2d63  mov     r9d, esi; TokenInformationLength
0x1800f2d66  mov     [rsp+2B0h+ReturnLength], rax; ReturnLength
0x1800f2d6b  mov     r8, rdi; TokenInformation
0x1800f2d6e  mov     [rsp+2B0h+var_270], 0
0x1800f2d76  mov     edx, 3; TokenInformationClass
0x1800f2d7b  call    cs:__imp_GetTokenInformation
0x1800f2d81  test    eax, eax
0x1800f2d83  jz      loc_1800F2EFA
0x1800f2d89  xor     ecx, ecx
0x1800f2d8b  cmp     ecx, [rdi]
0x1800f2d8d  jnb     short loc_1800F2DB0
0x1800f2d8f  lea     rdx, [rcx+rcx*2]
0x1800f2d93  cmp     dword ptr [rdi+rdx*4+4], 1Dh
0x1800f2d98  jz      loc_1800F2E24
0x1800f2d9e  inc     ecx
0x1800f2da0  jmp     short loc_1800F2D8B
0x1800f2da2  test    byte ptr [rdi+rdx*4+0Ch], 4
0x1800f2da7  jnz     short loc_1800F2DB0
0x1800f2da9  mov     dword ptr [r14], 1
0x1800f2db0  xor     edi, edi
0x1800f2db2  test    rbx, rbx
0x1800f2db5  jz      short loc_1800F2DC1
0x1800f2db7  lea     rcx, [rsp+2B0h+var_278]
0x1800f2dbc  call    WxFreeHeapEx
0x1800f2dc1  mov     rcx, [rsp+2B0h+hObject]; hObject
0x1800f2dc6  test    rcx, rcx
0x1800f2dc9  jz      short loc_1800F2DDA
0x1800f2dcb  call    cs:__imp_CloseHandle
0x1800f2dd1  mov     [rsp+2B0h+hObject], 0
0x1800f2dda  mov     rcx, [rsp+2B0h+TokenHandle]; hObject
0x1800f2ddf  test    rcx, rcx
0x1800f2de2  jz      short loc_1800F2DEA
0x1800f2de4  call    cs:__imp_CloseHandle
0x1800f2dea  mov     eax, edi
0x1800f2dec  mov     rcx, [rbp+1B0h+var_20]
0x1800f2df3  xor     rcx, rsp; StackCookie
0x1800f2df6  call    __security_check_cookie
0x1800f2dfb  lea     r11, [rsp+2B0h+var_10]
0x1800f2e03  mov     rbx, [r11+30h]
0x1800f2e07  mov     rsi, [r11+38h]
0x1800f2e0b  mov     rsp, r11
0x1800f2e0e  pop     r14
0x1800f2e10  pop     rdi
0x1800f2e11  pop     rbp
0x1800f2e12  retn
0x1800f2e13  mov     dword ptr [r14], 1
0x1800f2e1a  mov     dword ptr [rdi], 1
0x1800f2e20  xor     edi, edi
0x1800f2e22  jmp     short loc_1800F2DC1
0x1800f2e24  cmp     dword ptr [rdi+rdx*4+8], 0
0x1800f2e29  jnz     loc_1800F2D9E
0x1800f2e2f  jmp     loc_1800F2DA2
0x1800f2e34  call    WxGetLastError
0x1800f2e39  mov     edi, eax
0x1800f2e3b  test    eax, eax
0x1800f2e3d  jle     short loc_1800F2E48
0x1800f2e3f  movzx   edi, ax
0x1800f2e42  or      edi, 80070000h
0x1800f2e48  test    edi, edi
0x1800f2e4a  mov     [rsp+2B0h+var_27C], 32Ch
0x1800f2e52  mov     eax, 8000FFFFh
0x1800f2e57  cmovns  edi, eax
0x1800f2e5a  jmp     loc_1800F2DC1
0x1800f2e5f  call    WxGetLastError
0x1800f2e64  mov     edi, eax
0x1800f2e66  test    eax, eax
0x1800f2e68  jle     short loc_1800F2E73
0x1800f2e6a  movzx   edi, ax
0x1800f2e6d  or      edi, 80070000h
0x1800f2e73  test    edi, edi
0x1800f2e75  mov     [rsp+2B0h+var_27C], 327h
0x1800f2e7d  mov     eax, 8000FFFFh
0x1800f2e82  cmovns  edi, eax
0x1800f2e85  jmp     loc_1800F2DC1
0x1800f2e8a  call    WxGetLastError
0x1800f2e8f  mov     edi, eax
0x1800f2e91  test    eax, eax
0x1800f2e93  jle     short loc_1800F2E9E
0x1800f2e95  movzx   edi, ax
0x1800f2e98  or      edi, 80070000h
0x1800f2e9e  test    edi, edi
0x1800f2ea0  mov     [rsp+2B0h+var_27C], 32Dh
0x1800f2ea8  mov     eax, 8000FFFFh
0x1800f2ead  cmovns  edi, eax
0x1800f2eb0  jmp     loc_1800F2DC1
0x1800f2eb5  add     eax, 2
0x1800f2eb8  mov     [rsp+2B0h+var_27C], ebx
0x1800f2ebc  lea     ecx, [rax+rax*2]
0x1800f2ebf  shl     ecx, 2
0x1800f2ec2  mov     edx, ecx
0x1800f2ec4  mov     esi, ecx
0x1800f2ec6  call    WxAllocateHeapEx
0x1800f2ecb  mov     rdi, rax
0x1800f2ece  test    rax, rax
0x1800f2ed1  jnz     short loc_1800F2EED
0x1800f2ed3  mov     [rsp+2B0h+var_27C], 34h ; '4'
0x1800f2edb  mov     edi, 8007000Eh
0x1800f2ee0  mov     [rsp+2B0h+var_27C], 336h
0x1800f2ee8  jmp     loc_1800F2DB2
0x1800f2eed  mov     rbx, rax
0x1800f2ef0  mov     [rsp+2B0h+var_278], rax
0x1800f2ef5  jmp     loc_1800F2D59
0x1800f2efa  call    WxGetLastError
0x1800f2eff  mov     edi, eax
0x1800f2f01  test    eax, eax
0x1800f2f03  jle     short loc_1800F2F0E
0x1800f2f05  movzx   edi, ax
0x1800f2f08  or      edi, 80070000h
0x1800f2f0e  test    edi, edi
0x1800f2f10  mov     [rsp+2B0h+var_27C], 340h
0x1800f2f18  mov     eax, 8000FFFFh
0x1800f2f1d  cmovns  edi, eax
0x1800f2f20  jmp     loc_1800F2DB2
```
