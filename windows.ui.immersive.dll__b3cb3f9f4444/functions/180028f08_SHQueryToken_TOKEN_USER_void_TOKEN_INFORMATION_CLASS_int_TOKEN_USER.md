# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x180028f08`
- end: `0x18002905e`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dca54`

## callees

- `0x180028f08`
- `0x180029064`
- `0x180032e68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029001`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029023`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028f89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028ff1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028f89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028ff1`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(void *a1, DWORD a2, int a3, _QWORD *a4)
{
  __int64 result; // rax
  HANDLE v6; // r14
  void *v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  void *v10; // rcx
  int v11; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  TokenInformation = a1;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken((__int64)a1, a3, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v6 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v7 = TokenInformation;
  if ( !TokenInformation )
  {
    v8 = -2147024882;
    goto LABEL_14;
  }
  v8 = 0;
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_12;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 122 )
    goto LABEL_8;
  LocalFree(v7);
  v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, TokenInformationLength, &TokenInformation);
  v7 = TokenInformation;
  v8 = v11;
  if ( v11 >= 0 )
  {
    if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v8 = LastError;
LABEL_8:
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_11;
LABEL_12:
    *a4 = v7;
    goto LABEL_14;
  }
LABEL_11:
  LocalFree(v7);
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028f08  mov     [rsp-28h+TokenInformationLength], edx
0x180028f0c  mov     [rsp-28h+TokenInformation], rcx
0x180028f11  push    rbp
0x180028f12  push    rbx
0x180028f13  push    rsi
0x180028f14  push    rdi
0x180028f15  push    r14
0x180028f17  mov     rbp, rsp
0x180028f1a  sub     rsp, 30h
0x180028f1e  mov     edx, r8d; int
0x180028f21  mov     qword ptr [r9], 0
0x180028f28  lea     r8, [rbp+TokenHandle]; void **
0x180028f2c  mov     [rbp+TokenHandle], 0
0x180028f34  mov     rsi, r9
0x180028f37  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180028f3c  test    eax, eax
0x180028f3e  js      loc_180029052
0x180028f44  mov     r14, [rbp+TokenHandle]
0x180028f48  mov     edx, 800h; uBytes
0x180028f4d  mov     ecx, 40h ; '@'; uFlags
0x180028f52  mov     [rbp+TokenInformationLength], edx
0x180028f55  call    cs:__imp_LocalAlloc
0x180028f5c  nop     dword ptr [rax+rax+00h]
0x180028f61  mov     [rbp+TokenInformation], rax
0x180028f65  mov     rdi, rax
0x180028f68  test    rax, rax
0x180028f6b  jz      loc_180029036
0x180028f71  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028f75  lea     rax, [rbp+TokenInformationLength]
0x180028f79  xor     ebx, ebx
0x180028f7b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180028f80  mov     r8, rdi; TokenInformation
0x180028f83  mov     rcx, r14; TokenHandle
0x180028f86  lea     edx, [rbx+1]; TokenInformationClass
0x180028f89  call    cs:__imp_GetTokenInformation
0x180028f90  nop     dword ptr [rax+rax+00h]
0x180028f95  test    eax, eax
0x180028f97  jnz     loc_180029031
0x180028f9d  call    cs:__imp_GetLastError
0x180028fa4  nop     dword ptr [rax+rax+00h]
0x180028fa9  mov     ebx, eax
0x180028fab  cmp     eax, 7Ah ; 'z'
0x180028fae  jnz     short loc_18002900F
0x180028fb0  mov     rcx, rdi; hMem
0x180028fb3  call    cs:__imp_LocalFree
0x180028fba  nop     dword ptr [rax+rax+00h]
0x180028fbf  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180028fc3  lea     r9, [rbp+TokenInformation]; void **
0x180028fc7  lea     edx, [rbx-3Ah]; unsigned int
0x180028fca  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180028fcf  mov     rdi, [rbp+TokenInformation]
0x180028fd3  mov     ebx, eax
0x180028fd5  test    eax, eax
0x180028fd7  js      short loc_180029020
0x180028fd9  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028fdd  lea     rax, [rbp+TokenInformationLength]
0x180028fe1  mov     r8, rdi; TokenInformation
0x180028fe4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180028fe9  mov     edx, 1; TokenInformationClass
0x180028fee  mov     rcx, r14; TokenHandle
0x180028ff1  call    cs:__imp_GetTokenInformation
0x180028ff8  nop     dword ptr [rax+rax+00h]
0x180028ffd  test    eax, eax
0x180028fff  jnz     short loc_180029031
0x180029001  call    cs:__imp_GetLastError
0x180029008  nop     dword ptr [rax+rax+00h]
0x18002900d  mov     ebx, eax
0x18002900f  test    eax, eax
0x180029011  jle     short loc_18002901C
0x180029013  movzx   ebx, ax
0x180029016  or      ebx, 80070000h
0x18002901c  test    ebx, ebx
0x18002901e  jns     short loc_180029031
0x180029020  mov     rcx, rdi; hMem
0x180029023  call    cs:__imp_LocalFree
0x18002902a  nop     dword ptr [rax+rax+00h]
0x18002902f  jmp     short loc_18002903B
0x180029031  mov     [rsi], rdi
0x180029034  jmp     short loc_18002903B
0x180029036  mov     ebx, 8007000Eh
0x18002903b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002903f  test    rcx, rcx
0x180029042  jz      short loc_180029050
0x180029044  call    cs:__imp_CloseHandle
0x18002904b  nop     dword ptr [rax+rax+00h]
0x180029050  mov     eax, ebx
0x180029052  add     rsp, 30h
0x180029056  pop     r14
0x180029058  pop     rdi
0x180029059  pop     rsi
0x18002905a  pop     rbx
0x18002905b  pop     rbp
0x18002905c  retn
```
