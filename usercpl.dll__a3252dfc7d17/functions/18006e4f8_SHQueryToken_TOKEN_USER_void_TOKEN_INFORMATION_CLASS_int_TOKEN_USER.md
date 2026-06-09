# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18006e4f8`
- end: `0x18006e622`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(__int64, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180073c3c`

## callees

- `0x18006e4f8`
- `0x18006e74c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e57f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e57f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e5ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e60d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e60d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e575`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e5c4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e575`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006e5c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e549`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e59c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e549`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006e59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e58f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e5ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e58f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e5ea`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, int a2, DWORD a3, _QWORD *a4)
{
  __int64 result; // rax
  HANDLE v6; // rbp
  HLOCAL v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken(8u, a2, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v6 = TokenHandle;
  TokenInformationLength = 2048;
  v7 = LocalAlloc(0x40u, 0x800u);
  if ( !v7 )
  {
    v8 = -2147024882;
    goto LABEL_15;
  }
  v8 = 0;
  if ( GetTokenInformation(v6, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_13;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 122 )
    goto LABEL_8;
  LocalFree(v7);
  v7 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v7 )
  {
    v8 = 0;
    if ( GetTokenInformation(v6, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_13;
    LastError = GetLastError();
    v8 = LastError;
LABEL_8:
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_11;
LABEL_13:
    *a4 = v7;
    goto LABEL_15;
  }
  v8 = -2147024882;
LABEL_11:
  LocalFree(v7);
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006e4f8  mov     rax, rsp
0x18006e4fb  mov     [rax+10h], rbx
0x18006e4ff  mov     [rax+18h], r8d
0x18006e503  mov     [rax+8], rcx
0x18006e507  push    rbp
0x18006e508  push    rsi
0x18006e509  push    rdi
0x18006e50a  sub     rsp, 30h
0x18006e50e  lea     r8, [rax+8]; void **
0x18006e512  mov     qword ptr [r9], 0
0x18006e519  mov     ecx, 8; DesiredAccess
0x18006e51e  mov     qword ptr [rax+8], 0
0x18006e526  mov     rsi, r9
0x18006e529  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18006e52e  test    eax, eax
0x18006e530  js      loc_18006E615
0x18006e536  mov     rbp, [rsp+48h+TokenHandle]
0x18006e53b  mov     edx, 800h; uBytes
0x18006e540  mov     ecx, 40h ; '@'; uFlags
0x18006e545  mov     [rsp+48h+TokenInformationLength], edx
0x18006e549  call    cs:__imp_LocalAlloc
0x18006e54f  mov     rdi, rax
0x18006e552  test    rax, rax
0x18006e555  jz      loc_18006E5FE
0x18006e55b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18006e560  lea     rax, [rsp+48h+TokenInformationLength]
0x18006e565  xor     ebx, ebx
0x18006e567  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18006e56c  mov     r8, rdi; TokenInformation
0x18006e56f  mov     rcx, rbp; TokenHandle
0x18006e572  lea     edx, [rbx+1]; TokenInformationClass
0x18006e575  call    cs:__imp_GetTokenInformation
0x18006e57b  test    eax, eax
0x18006e57d  jnz     short loc_18006E5F9
0x18006e57f  call    cs:__imp_GetLastError
0x18006e585  mov     ebx, eax
0x18006e587  cmp     eax, 7Ah ; 'z'
0x18006e58a  jnz     short loc_18006E5D6
0x18006e58c  mov     rcx, rdi; hMem
0x18006e58f  call    cs:__imp_LocalFree
0x18006e595  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x18006e599  lea     ecx, [rbx-3Ah]; uFlags
0x18006e59c  call    cs:__imp_LocalAlloc
0x18006e5a2  mov     rdi, rax
0x18006e5a5  test    rax, rax
0x18006e5a8  jz      short loc_18006E5F2
0x18006e5aa  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18006e5af  lea     rax, [rsp+48h+TokenInformationLength]
0x18006e5b4  xor     ebx, ebx
0x18006e5b6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18006e5bb  mov     r8, rdi; TokenInformation
0x18006e5be  mov     rcx, rbp; TokenHandle
0x18006e5c1  lea     edx, [rbx+1]; TokenInformationClass
0x18006e5c4  call    cs:__imp_GetTokenInformation
0x18006e5ca  test    eax, eax
0x18006e5cc  jnz     short loc_18006E5F9
0x18006e5ce  call    cs:__imp_GetLastError
0x18006e5d4  mov     ebx, eax
0x18006e5d6  test    eax, eax
0x18006e5d8  jle     short loc_18006E5E3
0x18006e5da  movzx   ebx, ax
0x18006e5dd  or      ebx, 80070000h
0x18006e5e3  test    ebx, ebx
0x18006e5e5  jns     short loc_18006E5F9
0x18006e5e7  mov     rcx, rdi; hMem
0x18006e5ea  call    cs:__imp_LocalFree
0x18006e5f0  jmp     short loc_18006E603
0x18006e5f2  mov     ebx, 8007000Eh
0x18006e5f7  jmp     short loc_18006E5E7
0x18006e5f9  mov     [rsi], rdi
0x18006e5fc  jmp     short loc_18006E603
0x18006e5fe  mov     ebx, 8007000Eh
0x18006e603  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18006e608  test    rcx, rcx
0x18006e60b  jz      short loc_18006E613
0x18006e60d  call    cs:__imp_CloseHandle
0x18006e613  mov     eax, ebx
0x18006e615  mov     rbx, [rsp+48h+arg_8]
0x18006e61a  add     rsp, 30h
0x18006e61e  pop     rdi
0x18006e61f  pop     rsi
0x18006e620  pop     rbp
0x18006e621  retn
```
