# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18002f56c`
- end: `0x18002f687`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800234f0`

## callees

- `0x18002dc08`
- `0x18002f56c`
- `0x18002f690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f674`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f5eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f63a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f5eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f63a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f660`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f660`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(void *a1, __int64 a2, DWORD a3, _QWORD *a4)
{
  __int64 result; // rax
  unsigned int v6; // edx
  void *v7; // rcx
  HANDLE v8; // r14
  signed int v9; // ebx
  void *v10; // rdi
  signed int LastError; // eax
  unsigned int v12; // edx
  void *v13; // rcx
  int v14; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  TokenInformation = a1;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken((__int64)a1, a2, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v8 = TokenHandle;
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v9 = CTLocalAllocPolicy::Alloc(v7, v6, 0x800u, &TokenInformation);
  if ( v9 >= 0 )
  {
    v10 = TokenInformation;
    if ( GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v14 = CTLocalAllocPolicy::Alloc(v13, v12, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v9 = v14;
      if ( v14 < 0 )
      {
LABEL_11:
        LocalFree(v10);
        goto LABEL_13;
      }
      if ( GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_12:
        *a4 = v10;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_11;
    goto LABEL_12;
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002f56c  mov     [rsp-28h+TokenInformationLength], r8d
0x18002f571  mov     [rsp-28h+TokenInformation], rcx
0x18002f576  push    rbp
0x18002f577  push    rbx
0x18002f578  push    rsi
0x18002f579  push    rdi
0x18002f57a  push    r14
0x18002f57c  mov     rbp, rsp
0x18002f57f  sub     rsp, 30h
0x18002f583  lea     r8, [rbp+TokenHandle]; void **
0x18002f587  mov     qword ptr [r9], 0
0x18002f58e  mov     rsi, r9
0x18002f591  mov     [rbp+TokenHandle], 0
0x18002f599  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18002f59e  test    eax, eax
0x18002f5a0  js      loc_18002F67C
0x18002f5a6  mov     r14, [rbp+TokenHandle]
0x18002f5aa  lea     r9, [rbp+TokenInformation]; void **
0x18002f5ae  mov     r8d, 800h; unsigned __int64
0x18002f5b4  mov     [rbp+TokenInformation], 0
0x18002f5bc  mov     [rbp+TokenInformationLength], r8d
0x18002f5c0  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002f5c5  mov     ebx, eax
0x18002f5c7  test    eax, eax
0x18002f5c9  js      loc_18002F66B
0x18002f5cf  mov     rdi, [rbp+TokenInformation]
0x18002f5d3  lea     rax, [rbp+TokenInformationLength]
0x18002f5d7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002f5db  mov     r8, rdi; TokenInformation
0x18002f5de  mov     edx, 1; TokenInformationClass
0x18002f5e3  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002f5e8  mov     rcx, r14; TokenHandle
0x18002f5eb  call    cs:__imp_GetTokenInformation
0x18002f5f1  test    eax, eax
0x18002f5f3  jnz     short loc_18002F668
0x18002f5f5  call    cs:__imp_GetLastError
0x18002f5fb  mov     ebx, eax
0x18002f5fd  cmp     eax, 7Ah ; 'z'
0x18002f600  jnz     short loc_18002F64C
0x18002f602  mov     rcx, rdi; hMem
0x18002f605  call    cs:__imp_LocalFree
0x18002f60b  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18002f60f  lea     r9, [rbp+TokenInformation]; void **
0x18002f613  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002f618  mov     rdi, [rbp+TokenInformation]
0x18002f61c  mov     ebx, eax
0x18002f61e  test    eax, eax
0x18002f620  js      short loc_18002F65D
0x18002f622  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002f626  lea     rax, [rbp+TokenInformationLength]
0x18002f62a  mov     r8, rdi; TokenInformation
0x18002f62d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002f632  mov     edx, 1; TokenInformationClass
0x18002f637  mov     rcx, r14; TokenHandle
0x18002f63a  call    cs:__imp_GetTokenInformation
0x18002f640  test    eax, eax
0x18002f642  jnz     short loc_18002F668
0x18002f644  call    cs:__imp_GetLastError
0x18002f64a  mov     ebx, eax
0x18002f64c  test    eax, eax
0x18002f64e  jle     short loc_18002F659
0x18002f650  movzx   ebx, ax
0x18002f653  or      ebx, 80070000h
0x18002f659  test    ebx, ebx
0x18002f65b  jns     short loc_18002F668
0x18002f65d  mov     rcx, rdi; hMem
0x18002f660  call    cs:__imp_LocalFree
0x18002f666  jmp     short loc_18002F66B
0x18002f668  mov     [rsi], rdi
0x18002f66b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002f66f  test    rcx, rcx
0x18002f672  jz      short loc_18002F67A
0x18002f674  call    cs:__imp_CloseHandle
0x18002f67a  mov     eax, ebx
0x18002f67c  add     rsp, 30h
0x18002f680  pop     r14
0x18002f682  pop     rdi
0x18002f683  pop     rsi
0x18002f684  pop     rbx
0x18002f685  pop     rbp
0x18002f686  retn
```
