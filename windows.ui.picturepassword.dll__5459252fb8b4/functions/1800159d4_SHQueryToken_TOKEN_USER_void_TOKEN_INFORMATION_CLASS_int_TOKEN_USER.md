# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800159d4`
- end: `0x180015af9`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `293`
- prototype: `int __fastcall(void *, DWORD, int, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104d0`
- `0x180015c90`

## callees

- `0x1800159d4`
- `0x180015b00`
- `0x180015b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ab6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ad2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015a5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015aac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015a5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015aac`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(void *a1, DWORD a2, int a3, _QWORD *a4)
{
  int result; // eax
  void *v6; // rcx
  HANDLE v7; // r14
  signed int v8; // ebx
  void *v9; // rdi
  signed int LastError; // eax
  void *v11; // rcx
  int v12; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  TokenInformation = a1;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken((unsigned int)a1, a3, &TokenHandle);
  if ( result < 0 )
    return result;
  v7 = TokenHandle;
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v8 = CTLocalAllocPolicy::Alloc(v6, 0x40u, 0x800u, &TokenInformation);
  if ( v8 >= 0 )
  {
    v9 = TokenInformation;
    if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v9);
      v12 = CTLocalAllocPolicy::Alloc(v11, 0x40u, TokenInformationLength, &TokenInformation);
      v9 = TokenInformation;
      v8 = v12;
      if ( v12 < 0 )
      {
LABEL_11:
        LocalFree(v9);
        goto LABEL_13;
      }
      if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_12:
        *a4 = v9;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v8 = LastError;
    }
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_11;
    goto LABEL_12;
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x1800159d4  mov     [rsp-28h+TokenInformationLength], edx
0x1800159d8  mov     [rsp-28h+TokenInformation], rcx
0x1800159dd  push    rbp
0x1800159de  push    rbx
0x1800159df  push    rsi
0x1800159e0  push    rdi
0x1800159e1  push    r14
0x1800159e3  mov     rbp, rsp
0x1800159e6  sub     rsp, 30h
0x1800159ea  mov     edx, r8d; int
0x1800159ed  mov     qword ptr [r9], 0
0x1800159f4  lea     r8, [rbp+TokenHandle]; void **
0x1800159f8  mov     [rbp+TokenHandle], 0
0x180015a00  mov     rsi, r9
0x180015a03  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180015a08  test    eax, eax
0x180015a0a  js      loc_180015AEE
0x180015a10  mov     r14, [rbp+TokenHandle]
0x180015a14  lea     r9, [rbp+TokenInformation]; void **
0x180015a18  mov     r8d, 800h; unsigned __int64
0x180015a1e  mov     [rbp+TokenInformation], 0
0x180015a26  mov     edx, 40h ; '@'; unsigned int
0x180015a2b  mov     [rbp+TokenInformationLength], r8d
0x180015a2f  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015a34  mov     ebx, eax
0x180015a36  test    eax, eax
0x180015a38  js      loc_180015ADD
0x180015a3e  mov     rdi, [rbp+TokenInformation]
0x180015a42  lea     rax, [rbp+TokenInformationLength]
0x180015a46  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180015a4a  mov     r8, rdi; TokenInformation
0x180015a4d  mov     edx, 1; TokenInformationClass
0x180015a52  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015a57  mov     rcx, r14; TokenHandle
0x180015a5a  call    cs:__imp_GetTokenInformation
0x180015a60  test    eax, eax
0x180015a62  jnz     short loc_180015ADA
0x180015a64  call    cs:__imp_GetLastError
0x180015a6a  mov     ebx, eax
0x180015a6c  cmp     eax, 7Ah ; 'z'
0x180015a6f  jnz     short loc_180015ABE
0x180015a71  mov     rcx, rdi; hMem
0x180015a74  call    cs:__imp_LocalFree
0x180015a7a  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180015a7e  lea     r9, [rbp+TokenInformation]; void **
0x180015a82  lea     edx, [rbx-3Ah]; unsigned int
0x180015a85  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015a8a  mov     rdi, [rbp+TokenInformation]
0x180015a8e  mov     ebx, eax
0x180015a90  test    eax, eax
0x180015a92  js      short loc_180015ACF
0x180015a94  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180015a98  lea     rax, [rbp+TokenInformationLength]
0x180015a9c  mov     r8, rdi; TokenInformation
0x180015a9f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180015aa4  mov     edx, 1; TokenInformationClass
0x180015aa9  mov     rcx, r14; TokenHandle
0x180015aac  call    cs:__imp_GetTokenInformation
0x180015ab2  test    eax, eax
0x180015ab4  jnz     short loc_180015ADA
0x180015ab6  call    cs:__imp_GetLastError
0x180015abc  mov     ebx, eax
0x180015abe  test    eax, eax
0x180015ac0  jle     short loc_180015ACB
0x180015ac2  movzx   ebx, ax
0x180015ac5  or      ebx, 80070000h
0x180015acb  test    ebx, ebx
0x180015acd  jns     short loc_180015ADA
0x180015acf  mov     rcx, rdi; hMem
0x180015ad2  call    cs:__imp_LocalFree
0x180015ad8  jmp     short loc_180015ADD
0x180015ada  mov     [rsi], rdi
0x180015add  mov     rcx, [rbp+TokenHandle]; hObject
0x180015ae1  test    rcx, rcx
0x180015ae4  jz      short loc_180015AEC
0x180015ae6  call    cs:__imp_CloseHandle
0x180015aec  mov     eax, ebx
0x180015aee  add     rsp, 30h
0x180015af2  pop     r14
0x180015af4  pop     rdi
0x180015af5  pop     rsi
0x180015af6  pop     rbx
0x180015af7  pop     rbp
0x180015af8  retn
```
