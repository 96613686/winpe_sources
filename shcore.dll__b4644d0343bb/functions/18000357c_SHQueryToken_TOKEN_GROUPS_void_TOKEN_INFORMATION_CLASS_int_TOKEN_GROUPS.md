# SHQueryToken<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_GROUPS * *)

- ea: `0x18000357c`
- end: `0x18000369e`
- name: `??$SHQueryToken@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800034dc`

## callees

- `0x18000357c`
- `0x1800036a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800035f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003621`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000365f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000365f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003645`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003645`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003650`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800035ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003687`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800035ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003687`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_GROUPS>(__int64 a1, __int64 a2, DWORD a3, _QWORD *a4)
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
  result = SHOpenEffectiveToken(a1, a2, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v6 = TokenHandle;
  TokenInformationLength = 2048;
  v7 = LocalAlloc(0x40u, 0x800u);
  if ( !v7 )
  {
    v8 = -2147024882;
    goto LABEL_9;
  }
  v8 = 0;
  if ( !GetTokenInformation(v6, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 122 )
      goto LABEL_5;
    LocalFree(v7);
    v7 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
    {
      v8 = -2147024882;
      goto LABEL_15;
    }
    v8 = 0;
    if ( !GetTokenInformation(v6, TokenGroups, v7, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v8 = LastError;
LABEL_5:
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        goto LABEL_8;
LABEL_15:
      LocalFree(v7);
      goto LABEL_9;
    }
  }
LABEL_8:
  *a4 = v7;
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000357c  mov     rax, rsp
0x18000357f  mov     [rax+10h], rbx
0x180003583  mov     [rax+18h], r8d
0x180003587  mov     [rax+8], rcx
0x18000358b  push    rbp
0x18000358c  push    rsi
0x18000358d  push    rdi
0x18000358e  sub     rsp, 30h
0x180003592  lea     r8, [rax+8]; void **
0x180003596  mov     qword ptr [r9], 0
0x18000359d  mov     rsi, r9
0x1800035a0  mov     qword ptr [rax+8], 0
0x1800035a8  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800035ad  test    eax, eax
0x1800035af  js      short loc_180003629
0x1800035b1  mov     rbp, [rsp+48h+TokenHandle]
0x1800035b6  mov     edx, 800h; uBytes
0x1800035bb  mov     ecx, 40h ; '@'; uFlags
0x1800035c0  mov     [rsp+48h+TokenInformationLength], edx
0x1800035c4  call    cs:__imp_LocalAlloc
0x1800035ca  mov     rdi, rax
0x1800035cd  test    rax, rax
0x1800035d0  jz      short loc_180003636
0x1800035d2  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800035d7  lea     rax, [rsp+48h+TokenInformationLength]
0x1800035dc  xor     ebx, ebx
0x1800035de  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800035e3  mov     r8, rdi; TokenInformation
0x1800035e6  mov     rcx, rbp; TokenHandle
0x1800035e9  lea     edx, [rbx+2]; TokenInformationClass
0x1800035ec  call    cs:__imp_GetTokenInformation
0x1800035f2  test    eax, eax
0x1800035f4  jnz     short loc_180003614
0x1800035f6  call    cs:__imp_GetLastError
0x1800035fc  mov     ebx, eax
0x1800035fe  cmp     eax, 7Ah ; 'z'
0x180003601  jz      short loc_18000364D
0x180003603  test    eax, eax
0x180003605  jle     short loc_180003610
0x180003607  movzx   ebx, ax
0x18000360a  or      ebx, 80070000h
0x180003610  test    ebx, ebx
0x180003612  js      short loc_180003642
0x180003614  mov     [rsi], rdi
0x180003617  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000361c  test    rcx, rcx
0x18000361f  jz      short loc_180003627
0x180003621  call    cs:__imp_CloseHandle
0x180003627  mov     eax, ebx
0x180003629  mov     rbx, [rsp+48h+arg_8]
0x18000362e  add     rsp, 30h
0x180003632  pop     rdi
0x180003633  pop     rsi
0x180003634  pop     rbp
0x180003635  retn
0x180003636  mov     ebx, 8007000Eh
0x18000363b  jmp     short loc_180003617
0x18000363d  mov     ebx, 8007000Eh
0x180003642  mov     rcx, rdi; hMem
0x180003645  call    cs:__imp_LocalFree
0x18000364b  jmp     short loc_180003617
0x18000364d  mov     rcx, rdi; hMem
0x180003650  call    cs:__imp_LocalFree
0x180003656  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x18000365a  mov     ecx, 40h ; '@'; uFlags
0x18000365f  call    cs:__imp_LocalAlloc
0x180003665  mov     rdi, rax
0x180003668  test    rax, rax
0x18000366b  jz      short loc_18000363D
0x18000366d  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180003672  lea     rax, [rsp+48h+TokenInformationLength]
0x180003677  xor     ebx, ebx
0x180003679  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000367e  mov     r8, rdi; TokenInformation
0x180003681  mov     rcx, rbp; TokenHandle
0x180003684  lea     edx, [rbx+2]; TokenInformationClass
0x180003687  call    cs:__imp_GetTokenInformation
0x18000368d  test    eax, eax
0x18000368f  jnz     short loc_180003614
0x180003691  call    cs:__imp_GetLastError
0x180003697  mov     ebx, eax
0x180003699  jmp     loc_180003603
```
