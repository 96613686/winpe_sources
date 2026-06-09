# SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x180035c04`
- end: `0x180035d2a`
- name: `??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035da0`

## callees

- `0x18000d0d0`
- `0x180035c04`
- `0x180035d30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ce7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035d17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035d03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035ca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035d03`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035c8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035cdd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035c8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035cdd`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_MANDATORY_LABEL>(HANDLE TokenHandle, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  __int64 result; // rax
  signed int v7; // ebx
  void *v8; // rdi
  signed int LastError; // eax
  void *v10; // rcx
  int v11; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  hObject = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    result = SHOpenEffectiveToken(0, a2, &hObject);
    if ( (int)result < 0 )
      return result;
    v5 = hObject;
  }
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v7 = CTLocalAllocPolicy::Alloc(TokenHandle, 0x40u, 0x800u, &TokenInformation);
  if ( v7 >= 0 )
  {
    v8 = TokenInformation;
    if ( GetTokenInformation(v5, TokenIntegrityLevel, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v8);
      v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, TokenInformationLength, &TokenInformation);
      v8 = TokenInformation;
      v7 = v11;
      if ( v11 < 0 )
      {
LABEL_13:
        LocalFree(v8);
        goto LABEL_15;
      }
      if ( GetTokenInformation(
             v5,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
LABEL_14:
        *a4 = v8;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v7 = LastError;
    }
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_13;
    goto LABEL_14;
  }
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180035c04  mov     [rsp-28h+TokenInformationLength], r8d
0x180035c09  push    rbp
0x180035c0a  push    rbx
0x180035c0b  push    rsi
0x180035c0c  push    rdi
0x180035c0d  push    r14
0x180035c0f  mov     rbp, rsp
0x180035c12  sub     rsp, 30h
0x180035c16  mov     qword ptr [r9], 0
0x180035c1d  mov     r14, r9
0x180035c20  mov     [rbp+hObject], 0
0x180035c28  mov     rsi, rcx
0x180035c2b  test    rcx, rcx
0x180035c2e  jnz     short loc_180035C45
0x180035c30  lea     r8, [rbp+hObject]; void **
0x180035c34  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180035c39  test    eax, eax
0x180035c3b  js      loc_180035D1F
0x180035c41  mov     rsi, [rbp+hObject]
0x180035c45  mov     r8d, 800h; unsigned __int64
0x180035c4b  mov     [rbp+TokenInformation], 0
0x180035c53  lea     r9, [rbp+TokenInformation]; void **
0x180035c57  mov     [rbp+TokenInformationLength], r8d
0x180035c5b  mov     edx, 40h ; '@'; unsigned int
0x180035c60  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180035c65  mov     ebx, eax
0x180035c67  test    eax, eax
0x180035c69  js      loc_180035D0E
0x180035c6f  mov     rdi, [rbp+TokenInformation]
0x180035c73  lea     rax, [rbp+TokenInformationLength]
0x180035c77  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180035c7b  mov     r8, rdi; TokenInformation
0x180035c7e  mov     edx, 19h; TokenInformationClass
0x180035c83  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180035c88  mov     rcx, rsi; TokenHandle
0x180035c8b  call    cs:__imp_GetTokenInformation
0x180035c91  test    eax, eax
0x180035c93  jnz     short loc_180035D0B
0x180035c95  call    cs:__imp_GetLastError
0x180035c9b  mov     ebx, eax
0x180035c9d  cmp     eax, 7Ah ; 'z'
0x180035ca0  jnz     short loc_180035CEF
0x180035ca2  mov     rcx, rdi; hMem
0x180035ca5  call    cs:__imp_LocalFree
0x180035cab  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180035caf  lea     r9, [rbp+TokenInformation]; void **
0x180035cb3  lea     edx, [rbx-3Ah]; unsigned int
0x180035cb6  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180035cbb  mov     rdi, [rbp+TokenInformation]
0x180035cbf  mov     ebx, eax
0x180035cc1  test    eax, eax
0x180035cc3  js      short loc_180035D00
0x180035cc5  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180035cc9  lea     rax, [rbp+TokenInformationLength]
0x180035ccd  mov     r8, rdi; TokenInformation
0x180035cd0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180035cd5  mov     edx, 19h; TokenInformationClass
0x180035cda  mov     rcx, rsi; TokenHandle
0x180035cdd  call    cs:__imp_GetTokenInformation
0x180035ce3  test    eax, eax
0x180035ce5  jnz     short loc_180035D0B
0x180035ce7  call    cs:__imp_GetLastError
0x180035ced  mov     ebx, eax
0x180035cef  test    eax, eax
0x180035cf1  jle     short loc_180035CFC
0x180035cf3  movzx   ebx, ax
0x180035cf6  or      ebx, 80070000h
0x180035cfc  test    ebx, ebx
0x180035cfe  jns     short loc_180035D0B
0x180035d00  mov     rcx, rdi; hMem
0x180035d03  call    cs:__imp_LocalFree
0x180035d09  jmp     short loc_180035D0E
0x180035d0b  mov     [r14], rdi
0x180035d0e  mov     rcx, [rbp+hObject]; hObject
0x180035d12  test    rcx, rcx
0x180035d15  jz      short loc_180035D1D
0x180035d17  call    cs:__imp_CloseHandle
0x180035d1d  mov     eax, ebx
0x180035d1f  add     rsp, 30h
0x180035d23  pop     r14
0x180035d25  pop     rdi
0x180035d26  pop     rsi
0x180035d27  pop     rbx
0x180035d28  pop     rbp
0x180035d29  retn
```
