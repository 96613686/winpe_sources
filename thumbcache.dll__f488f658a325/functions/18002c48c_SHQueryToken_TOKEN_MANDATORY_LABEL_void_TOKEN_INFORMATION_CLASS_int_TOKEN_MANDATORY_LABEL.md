# SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x18002c48c`
- end: `0x18002c5b6`
- name: `??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c424`

## callees

- `0x18002c48c`
- `0x18002c5bc`
- `0x18002ca40`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c5ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c4c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c4c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c537`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c55e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c537`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c55e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c4ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c593`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c4ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c593`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_MANDATORY_LABEL>(HANDLE TokenHandle, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  void *v6; // rdi
  signed int v7; // ebx
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  int v12; // eax
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
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v6 = TokenInformation;
  if ( !TokenInformation )
  {
    v7 = -2147024882;
    goto LABEL_5;
  }
  v7 = 0;
  if ( !GetTokenInformation(v5, TokenIntegrityLevel, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v6);
      v12 = CTLocalAllocPolicy::Alloc(v11, v10, TokenInformationLength, &TokenInformation);
      v6 = TokenInformation;
      v7 = v12;
      if ( v12 < 0 )
        goto LABEL_13;
      if ( GetTokenInformation(
             v5,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        goto LABEL_4;
      }
      LastError = GetLastError();
      v7 = LastError;
    }
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_4;
LABEL_13:
    LocalFree(v6);
    goto LABEL_5;
  }
LABEL_4:
  *a4 = v6;
LABEL_5:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002c48c  mov     [rsp-28h+TokenInformationLength], r8d
0x18002c491  push    rbp
0x18002c492  push    rbx
0x18002c493  push    rsi
0x18002c494  push    rdi
0x18002c495  push    r14
0x18002c497  mov     rbp, rsp
0x18002c49a  sub     rsp, 30h
0x18002c49e  mov     qword ptr [r9], 0
0x18002c4a5  mov     r14, r9
0x18002c4a8  mov     [rbp+hObject], 0
0x18002c4b0  mov     rsi, rcx
0x18002c4b3  test    rcx, rcx
0x18002c4b6  jz      short loc_18002C51D
0x18002c4b8  mov     edx, 800h; uBytes
0x18002c4bd  mov     ecx, 40h ; '@'; uFlags
0x18002c4c2  mov     [rbp+TokenInformationLength], edx
0x18002c4c5  call    cs:__imp_LocalAlloc
0x18002c4cb  mov     [rbp+TokenInformation], rax
0x18002c4cf  mov     rdi, rax
0x18002c4d2  test    rax, rax
0x18002c4d5  jz      short loc_18002C516
0x18002c4d7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002c4db  lea     rax, [rbp+TokenInformationLength]
0x18002c4df  xor     ebx, ebx
0x18002c4e1  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002c4e6  mov     r8, rdi; TokenInformation
0x18002c4e9  mov     rcx, rsi; TokenHandle
0x18002c4ec  lea     edx, [rbx+19h]; TokenInformationClass
0x18002c4ef  call    cs:__imp_GetTokenInformation
0x18002c4f5  test    eax, eax
0x18002c4f7  jz      short loc_18002C54E
0x18002c4f9  mov     [r14], rdi
0x18002c4fc  mov     rcx, [rbp+hObject]; unsigned int
0x18002c500  test    rcx, rcx
0x18002c503  jnz     loc_18002C5AB
0x18002c509  mov     eax, ebx
0x18002c50b  add     rsp, 30h
0x18002c50f  pop     r14
0x18002c511  pop     rdi
0x18002c512  pop     rsi
0x18002c513  pop     rbx
0x18002c514  pop     rbp
0x18002c515  retn
0x18002c516  mov     ebx, 8007000Eh
0x18002c51b  jmp     short loc_18002C4FC
0x18002c51d  lea     r8, [rbp+hObject]; void **
0x18002c521  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18002c526  test    eax, eax
0x18002c528  js      short loc_18002C50B
0x18002c52a  mov     rsi, [rbp+hObject]
0x18002c52e  jmp     short loc_18002C4B8
0x18002c530  test    ebx, ebx
0x18002c532  jns     short loc_18002C4F9
0x18002c534  mov     rcx, rdi; hMem
0x18002c537  call    cs:__imp_LocalFree
0x18002c53d  jmp     short loc_18002C4FC
0x18002c53f  test    eax, eax
0x18002c541  jle     short loc_18002C530
0x18002c543  movzx   ebx, ax
0x18002c546  or      ebx, 80070000h
0x18002c54c  jmp     short loc_18002C530
0x18002c54e  call    cs:__imp_GetLastError
0x18002c554  mov     ebx, eax
0x18002c556  cmp     eax, 7Ah ; 'z'
0x18002c559  jnz     short loc_18002C53F
0x18002c55b  mov     rcx, rdi; hMem
0x18002c55e  call    cs:__imp_LocalFree
0x18002c564  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18002c568  lea     r9, [rbp+TokenInformation]; void **
0x18002c56c  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002c571  mov     rdi, [rbp+TokenInformation]
0x18002c575  mov     ebx, eax
0x18002c577  test    eax, eax
0x18002c579  js      short loc_18002C534
0x18002c57b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002c57f  lea     rax, [rbp+TokenInformationLength]
0x18002c583  mov     r8, rdi; TokenInformation
0x18002c586  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002c58b  mov     edx, 19h; TokenInformationClass
0x18002c590  mov     rcx, rsi; TokenHandle
0x18002c593  call    cs:__imp_GetTokenInformation
0x18002c599  test    eax, eax
0x18002c59b  jnz     loc_18002C4F9
0x18002c5a1  call    cs:__imp_GetLastError
0x18002c5a7  mov     ebx, eax
0x18002c5a9  jmp     short loc_18002C53F
0x18002c5ab  call    cs:__imp_CloseHandle
0x18002c5b1  jmp     loc_18002C509
```
