# QueryLocalUserServiceName

- ea: `0x180039910`
- end: `0x180039bf9`
- name: `QueryLocalUserServiceName`
- size: `745`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a17c`
- `0x18000afb0`
- `0x18000b460`
- `0x18000e110`
- `0x180017544`
- `0x180039910`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800399d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800399d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800399bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800399bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800399e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800399e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800399f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800399f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039a70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039b9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039bad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039bcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039b9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039bad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039bcd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039a2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039a4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039aa4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039a2e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039a4f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039aa4`

## pseudocode

```c
__int64 __fastcall QueryLocalUserServiceName(__int64 a1, unsigned __int16 *a2, int *a3)
{
  LPWSTR v5; // r14
  PSID *v6; // rsi
  int v7; // r15d
  SC_HANDLE v8; // r13
  DWORD LastError; // edi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD v12; // eax
  __int64 v13; // rax
  int v14; // r11d
  DWORD ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-78h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-74h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-68h] BYREF
  DWORD v22[4]; // [rsp+58h] [rbp-60h] BYREF
  PSID *v23; // [rsp+68h] [rbp-50h]
  SC_HANDLE v24; // [rsp+70h] [rbp-48h]
  int v27; // [rsp+D8h] [rbp+20h]

  hMem = 0;
  v5 = 0;
  StringSid = 0;
  TokenInformation = 0;
  TokenHandle = 0;
  TokenInformationLength = 4;
  v6 = 0;
  ReturnLength = 0;
  v22[0] = 0;
  v7 = 257;
  v27 = 257;
  v22[2] = 257;
  v8 = OpenSCManagerA(0, 0, 1u);
  v24 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    goto LABEL_31;
  }
  if ( a1 && a3 && (a2 || !*a3) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_9;
    }
    if ( !GetTokenInformation(
            TokenHandle,
            TokenSessionId,
            &TokenInformation,
            TokenInformationLength,
            &TokenInformationLength)
      || !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) && (GetLastError() != 122 || !ReturnLength) )
    {
      goto LABEL_9;
    }
    v6 = (PSID *)LocalAlloc(0, ReturnLength);
    v23 = v6;
    if ( !v6 )
    {
      LastError = 8;
      goto LABEL_11;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v6, ReturnLength, v22) )
    {
LABEL_9:
      v12 = GetLastError();
LABEL_10:
      LastError = v12;
LABEL_11:
      v7 = 257;
      goto LABEL_31;
    }
    if ( !ConvertSidToStringSidW(*v6, &StringSid) )
    {
      v12 = GetLastError();
      v5 = StringSid;
      goto LABEL_10;
    }
    v5 = StringSid;
    LastError = RQueryUserServiceName((_DWORD)v8, a1, (_DWORD)StringSid, TokenInformation, (__int64)&hMem);
    v22[1] = LastError;
    if ( !LastError )
    {
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)hMem + v13) );
      v14 = v13 + 1;
      v27 = v13 + 1;
      if ( (int)v13 + 1 > (unsigned int)*a3 )
      {
        LastError = 122;
LABEL_26:
        v7 = v14;
        goto LABEL_31;
      }
      if ( (int)StringCchCopyW(a2, (unsigned int)*a3, (const unsigned __int16 *)hMem) < 0 )
      {
        LastError = 8;
        goto LABEL_26;
      }
    }
    v7 = v27;
  }
  else
  {
    LastError = 87;
  }
LABEL_31:
  if ( v5 )
    LocalFree(v5);
  if ( v6 )
    LocalFree(v6);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    CloseServiceHandle(v8);
  *a3 = v7;
  return LastError;
}

```

## disassembly

```asm
0x180039910  mov     rax, rsp
0x180039913  mov     [rax+18h], r8
0x180039917  mov     [rax+10h], rdx
0x18003991b  mov     [rax+8], rcx
0x18003991f  push    rbx
0x180039920  push    rsi
0x180039921  push    rdi
0x180039922  push    r12
0x180039924  push    r13
0x180039926  push    r14
0x180039928  push    r15
0x18003992a  sub     rsp, 80h
0x180039931  mov     r12, r8
0x180039934  mov     rdi, rdx
0x180039937  xor     ebx, ebx
0x180039939  mov     [rax-68h], rbx
0x18003993d  mov     r14d, ebx
0x180039940  mov     [rax-70h], rbx
0x180039944  mov     [rax-74h], ebx
0x180039947  mov     [rax-80h], rbx
0x18003994b  mov     dword ptr [rax-78h], 4
0x180039952  mov     esi, ebx
0x180039954  mov     [rsp+0B8h+var_88], ebx
0x180039958  mov     [rax-60h], ebx
0x18003995b  mov     r15d, 101h
0x180039961  mov     [rsp+0B8h+arg_18], r15d
0x180039969  mov     [rsp+0B8h+var_58], r15d
0x18003996e  xor     edx, edx; lpDatabaseName
0x180039970  xor     ecx, ecx; lpMachineName
0x180039972  lea     r8d, [rbx+1]; dwDesiredAccess
0x180039976  call    OpenSCManagerA
0x18003997b  mov     r13, rax
0x18003997e  mov     [rsp+0B8h+var_48], rax
0x180039983  test    rax, rax
0x180039986  jnz     short loc_180039995
0x180039988  call    cs:__imp_GetLastError
0x18003998e  mov     edi, eax
0x180039990  jmp     loc_180039B97
0x180039995  cmp     [rsp+0B8h+arg_0], rbx
0x18003999d  jz      loc_180039B92
0x1800399a3  test    r12, r12
0x1800399a6  jz      loc_180039B92
0x1800399ac  test    rdi, rdi
0x1800399af  jnz     short loc_1800399BB
0x1800399b1  cmp     [r12], ebx
0x1800399b5  jnz     loc_180039B92
0x1800399bb  call    cs:__imp_GetCurrentThread
0x1800399c1  mov     rcx, rax; ThreadHandle
0x1800399c4  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800399c9  mov     edi, 1
0x1800399ce  mov     r8d, edi; OpenAsSelf
0x1800399d1  lea     r15d, [rdi+7]
0x1800399d5  mov     edx, r15d; DesiredAccess
0x1800399d8  call    cs:__imp_OpenThreadToken
0x1800399de  test    eax, eax
0x1800399e0  jnz     short loc_180039A10
0x1800399e2  call    cs:__imp_GetCurrentProcess
0x1800399e8  mov     rcx, rax; ProcessHandle
0x1800399eb  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800399f0  mov     edx, r15d; DesiredAccess
0x1800399f3  call    cs:__imp_OpenProcessToken
0x1800399f9  test    eax, eax
0x1800399fb  jnz     short loc_180039A10
0x1800399fd  call    cs:__imp_GetLastError
0x180039a03  mov     edi, eax
0x180039a05  mov     r15d, 101h
0x180039a0b  jmp     loc_180039B97
0x180039a10  lea     rax, [rsp+0B8h+TokenInformationLength]
0x180039a15  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180039a1a  mov     r9d, [rsp+0B8h+TokenInformationLength]; TokenInformationLength
0x180039a1f  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180039a24  mov     edx, 0Ch; TokenInformationClass
0x180039a29  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039a2e  call    cs:__imp_GetTokenInformation
0x180039a34  test    eax, eax
0x180039a36  jz      short loc_1800399FD
0x180039a38  lea     rax, [rsp+0B8h+var_88]
0x180039a3d  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180039a42  xor     r9d, r9d; TokenInformationLength
0x180039a45  xor     r8d, r8d; TokenInformation
0x180039a48  mov     edx, edi; TokenInformationClass
0x180039a4a  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039a4f  call    cs:__imp_GetTokenInformation
0x180039a55  test    eax, eax
0x180039a57  jnz     short loc_180039A6A
0x180039a59  call    cs:__imp_GetLastError
0x180039a5f  cmp     eax, 7Ah ; 'z'
0x180039a62  jnz     short loc_1800399FD
0x180039a64  cmp     [rsp+0B8h+var_88], ebx
0x180039a68  jz      short loc_1800399FD
0x180039a6a  mov     edx, [rsp+0B8h+var_88]; uBytes
0x180039a6e  xor     ecx, ecx; uFlags
0x180039a70  call    cs:__imp_LocalAlloc
0x180039a76  mov     rsi, rax
0x180039a79  mov     [rsp+0B8h+var_50], rax
0x180039a7e  test    rax, rax
0x180039a81  jnz     short loc_180039A8B
0x180039a83  mov     edi, r15d
0x180039a86  jmp     loc_180039A05
0x180039a8b  lea     rax, [rsp+0B8h+var_60]
0x180039a90  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180039a95  mov     r9d, [rsp+0B8h+var_88]; TokenInformationLength
0x180039a9a  mov     r8, rsi; TokenInformation
0x180039a9d  mov     edx, edi; TokenInformationClass
0x180039a9f  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180039aa4  call    cs:__imp_GetTokenInformation
0x180039aaa  test    eax, eax
0x180039aac  jz      loc_1800399FD
0x180039ab2  lea     rdx, [rsp+0B8h+StringSid]; StringSid
0x180039ab7  mov     rcx, [rsi]; Sid
0x180039aba  call    ConvertSidToStringSidW
0x180039abf  test    eax, eax
0x180039ac1  jnz     short loc_180039AD3
0x180039ac3  call    cs:__imp_GetLastError
0x180039ac9  mov     r14, [rsp+0B8h+StringSid]
0x180039ace  jmp     loc_180039A03
0x180039ad3  lea     rax, [rsp+0B8h+hMem]
0x180039ad8  mov     [rsp+0B8h+ReturnLength], rax
0x180039add  mov     r9d, [rsp+0B8h+TokenInformation]
0x180039ae2  mov     r14, [rsp+0B8h+StringSid]
0x180039ae7  mov     r8, r14
0x180039aea  mov     rdx, [rsp+0B8h+arg_0]
0x180039af2  mov     rcx, r13
0x180039af5  call    RQueryUserServiceName
0x180039afa  mov     edi, eax
0x180039afc  mov     [rsp+0B8h+var_5C], eax
0x180039b00  jmp     short loc_180039B37
0x180039b02  mov     ecx, eax; unsigned int
0x180039b04  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180039b09  mov     edi, eax
0x180039b0b  mov     [rsp+0B8h+var_5C], eax
0x180039b0f  xor     ebx, ebx
0x180039b11  lea     r15d, [rbx+8]
0x180039b15  mov     r12, [rsp+0B8h+arg_10]
0x180039b1d  mov     r14, [rsp+0B8h+StringSid]
0x180039b22  mov     rsi, [rsp+0B8h+var_50]
0x180039b27  mov     eax, [rsp+0B8h+var_58]
0x180039b2b  mov     [rsp+0B8h+arg_18], eax
0x180039b32  mov     r13, [rsp+0B8h+var_48]
0x180039b37  test    edi, edi
0x180039b39  jnz     short loc_180039B88
0x180039b3b  mov     rcx, [rsp+0B8h+hMem]
0x180039b40  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039b44  inc     rax
0x180039b47  cmp     [rcx+rax*2], bx
0x180039b4b  jnz     short loc_180039B44
0x180039b4d  lea     r11d, [rax+1]
0x180039b51  mov     [rsp+0B8h+arg_18], r11d
0x180039b59  cmp     r11d, [r12]
0x180039b5d  jbe     short loc_180039B69
0x180039b5f  mov     edi, 7Ah ; 'z'
0x180039b64  mov     r15d, r11d
0x180039b67  jmp     short loc_180039B97
0x180039b69  mov     edx, [r12]; unsigned __int64
0x180039b6d  mov     r8, [rsp+0B8h+hMem]; unsigned __int16 *
0x180039b72  mov     rcx, [rsp+0B8h+arg_8]; unsigned __int16 *
0x180039b7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039b7f  test    eax, eax
0x180039b81  jns     short loc_180039B88
0x180039b83  mov     edi, r15d
0x180039b86  jmp     short loc_180039B64
0x180039b88  mov     r15d, [rsp+0B8h+arg_18]
0x180039b90  jmp     short loc_180039B97
0x180039b92  mov     edi, 57h ; 'W'
0x180039b97  test    r14, r14
0x180039b9a  jz      short loc_180039BA5
0x180039b9c  mov     rcx, r14; hMem
0x180039b9f  call    cs:__imp_LocalFree
0x180039ba5  test    rsi, rsi
0x180039ba8  jz      short loc_180039BB3
0x180039baa  mov     rcx, rsi; hMem
0x180039bad  call    cs:__imp_LocalFree
0x180039bb3  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180039bb8  test    rcx, rcx
0x180039bbb  jz      short loc_180039BC3
0x180039bbd  call    cs:__imp_CloseHandle
0x180039bc3  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180039bc8  test    rcx, rcx
0x180039bcb  jz      short loc_180039BD3
0x180039bcd  call    cs:__imp_LocalFree
0x180039bd3  test    r13, r13
0x180039bd6  jz      short loc_180039BE0
0x180039bd8  mov     rcx, r13; hSCObject
0x180039bdb  call    CloseServiceHandle
0x180039be0  mov     [r12], r15d
0x180039be4  mov     eax, edi
0x180039be6  add     rsp, 80h
0x180039bed  pop     r15
0x180039bef  pop     r14
0x180039bf1  pop     r13
0x180039bf3  pop     r12
0x180039bf5  pop     rdi
0x180039bf6  pop     rsi
0x180039bf7  pop     rbx
0x180039bf8  retn
0x18005048a  push    rbp
0x18005048c  sub     rsp, 30h
0x180050490  mov     rbp, rdx
0x180050493  mov     rcx, [rcx]
0x180050496  mov     ecx, [rcx]; ExceptionCode
0x180050498  call    cs:__imp_I_RpcExceptionFilter
0x18005049e  nop
0x18005049f  add     rsp, 30h
0x1800504a3  pop     rbp
0x1800504a4  retn
```
