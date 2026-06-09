# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18000911c`
- end: `0x180009241`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `293`
- prototype: `int __fastcall(unsigned int, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088f8`

## callees

- `0x18000911c`
- `0x180009248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800091ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000922c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009194`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800091e3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009194`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800091e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009209`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800091ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009209`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009168`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091bb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009168`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091bb`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(unsigned int a1, int a2, DWORD a3, _QWORD *a4)
{
  int result; // eax
  HANDLE v6; // rbp
  HLOCAL v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken(a1, a2, &TokenHandle);
  if ( result < 0 )
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
  return v8;
}

```

## disassembly

```asm
0x18000911c  mov     rax, rsp
0x18000911f  mov     [rax+10h], rbx
0x180009123  mov     [rax+18h], r8d
0x180009127  mov     [rax+8], rcx
0x18000912b  push    rbp
0x18000912c  push    rsi
0x18000912d  push    rdi
0x18000912e  sub     rsp, 30h
0x180009132  lea     r8, [rax+8]; void **
0x180009136  mov     qword ptr [r9], 0
0x18000913d  mov     rsi, r9
0x180009140  mov     qword ptr [rax+8], 0
0x180009148  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18000914d  test    eax, eax
0x18000914f  js      loc_180009234
0x180009155  mov     rbp, [rsp+48h+TokenHandle]
0x18000915a  mov     edx, 800h; uBytes
0x18000915f  mov     ecx, 40h ; '@'; uFlags
0x180009164  mov     [rsp+48h+TokenInformationLength], edx
0x180009168  call    cs:__imp_LocalAlloc
0x18000916e  mov     rdi, rax
0x180009171  test    rax, rax
0x180009174  jz      loc_18000921D
0x18000917a  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000917f  lea     rax, [rsp+48h+TokenInformationLength]
0x180009184  xor     ebx, ebx
0x180009186  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000918b  mov     r8, rdi; TokenInformation
0x18000918e  mov     rcx, rbp; TokenHandle
0x180009191  lea     edx, [rbx+1]; TokenInformationClass
0x180009194  call    cs:__imp_GetTokenInformation
0x18000919a  test    eax, eax
0x18000919c  jnz     short loc_180009218
0x18000919e  call    cs:__imp_GetLastError
0x1800091a4  mov     ebx, eax
0x1800091a6  cmp     eax, 7Ah ; 'z'
0x1800091a9  jnz     short loc_1800091F5
0x1800091ab  mov     rcx, rdi; hMem
0x1800091ae  call    cs:__imp_LocalFree
0x1800091b4  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x1800091b8  lea     ecx, [rbx-3Ah]; uFlags
0x1800091bb  call    cs:__imp_LocalAlloc
0x1800091c1  mov     rdi, rax
0x1800091c4  test    rax, rax
0x1800091c7  jz      short loc_180009211
0x1800091c9  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800091ce  lea     rax, [rsp+48h+TokenInformationLength]
0x1800091d3  xor     ebx, ebx
0x1800091d5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800091da  mov     r8, rdi; TokenInformation
0x1800091dd  mov     rcx, rbp; TokenHandle
0x1800091e0  lea     edx, [rbx+1]; TokenInformationClass
0x1800091e3  call    cs:__imp_GetTokenInformation
0x1800091e9  test    eax, eax
0x1800091eb  jnz     short loc_180009218
0x1800091ed  call    cs:__imp_GetLastError
0x1800091f3  mov     ebx, eax
0x1800091f5  test    eax, eax
0x1800091f7  jle     short loc_180009202
0x1800091f9  movzx   ebx, ax
0x1800091fc  or      ebx, 80070000h
0x180009202  test    ebx, ebx
0x180009204  jns     short loc_180009218
0x180009206  mov     rcx, rdi; hMem
0x180009209  call    cs:__imp_LocalFree
0x18000920f  jmp     short loc_180009222
0x180009211  mov     ebx, 8007000Eh
0x180009216  jmp     short loc_180009206
0x180009218  mov     [rsi], rdi
0x18000921b  jmp     short loc_180009222
0x18000921d  mov     ebx, 8007000Eh
0x180009222  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180009227  test    rcx, rcx
0x18000922a  jz      short loc_180009232
0x18000922c  call    cs:__imp_CloseHandle
0x180009232  mov     eax, ebx
0x180009234  mov     rbx, [rsp+48h+arg_8]
0x180009239  add     rsp, 30h
0x18000923d  pop     rdi
0x18000923e  pop     rsi
0x18000923f  pop     rbp
0x180009240  retn
```
