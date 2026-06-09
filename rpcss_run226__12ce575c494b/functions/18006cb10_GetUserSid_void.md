# GetUserSid(void *)

- ea: `0x18006cb10`
- end: `0x18006cd46`
- name: `?GetUserSid@@YAPEAXPEAX@Z`
- size: `566`
- prototype: `void *__fastcall(HANDLE TokenHandle)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005c80`
- `0x18004cd64`
- `0x180052210`
- `0x18005d8e0`
- `0x180071294`
- `0x180081d3c`
- `0x180082d68`
- `0x1800e8838`
- `0x1800ef93c`
- `0x1800fb694`

## callees

- `0x180034540`
- `0x18006cb10`
- `0x18007e3d4`
- `0x1800b27e0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18006cca9`
- `ntdll!RtlCopySid` at `0x18006cca9`
- `ntdll!RtlLengthSid` at `0x18006cc73`
- `ntdll!RtlLengthSid` at `0x18006cc73`
- `ntdll!NtQueryInformationToken` at `0x18006cb52`
- `ntdll!NtQueryInformationToken` at `0x18006cbfb`
- `ntdll!NtQueryInformationToken` at `0x18006cb52`
- `ntdll!NtQueryInformationToken` at `0x18006cbfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cc5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ccc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cd1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cc5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006ccc2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006cd1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cbcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cc8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cbcd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006cc8a`

## string_xrefs

- `0x18006cbae`: `onecore\com\combase\catalog\services.cxx`
- `0x18006cc44`: `onecore\com\combase\catalog\services.cxx`
- `0x18006cd07`: `onecore\com\combase\catalog\services.cxx`
- `0x18006cba7`: `GetUserSid`
- `0x18006cc3d`: `GetUserSid`
- `0x18006cd00`: `GetUserSid`

## pseudocode

```c
void *__fastcall GetUserSid(HANDLE TokenHandle)
{
  NTSTATUS InformationToken; // eax
  NTSTATUS v3; // r8d
  PSID *v4; // rbx
  int v5; // esi
  NTSTATUS v6; // r8d
  void *v8; // rax
  void *v9; // rdi
  NTSTATUS v10; // ebp
  ULONG TokenInformationLength[4]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE TokenInformation[112]; // [rsp+40h] [rbp-A8h] BYREF

  TokenInformationLength[0] = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x64u, TokenInformationLength);
  v3 = InformationToken;
  if ( InformationToken >= 0 )
  {
    v5 = 0;
    v4 = (PSID *)TokenInformation;
  }
  else
  {
    if ( InformationToken != -1073741789 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (unsigned int)"GetUserSid",
          1809,
          0,
          (__int64)L"%!STATUS!",
          v3);
      return 0;
    }
    v4 = (PSID *)HeapAlloc(g_hHeap, 0, TokenInformationLength[0]);
    if ( !v4 )
      return 0;
    v5 = 1;
    v6 = NtQueryInformationToken(TokenHandle, TokenUser, v4, TokenInformationLength[0], TokenInformationLength);
    if ( v6 < 0 )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
        ComTraceMessageT<long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (unsigned int)"GetUserSid",
          1842,
          0,
          (__int64)L"%!STATUS!",
          v6);
LABEL_13:
      HeapFree(g_hHeap, 0, v4);
      return 0;
    }
  }
  TokenInformationLength[0] = RtlLengthSid(*v4);
  v8 = HeapAlloc(g_hHeap, 0, TokenInformationLength[0]);
  v9 = v8;
  if ( !v8 )
  {
    if ( v5 != 1 )
      return 0;
    goto LABEL_13;
  }
  v10 = RtlCopySid(TokenInformationLength[0], v8, *v4);
  if ( v5 == 1 )
    HeapFree(g_hHeap, 0, v4);
  if ( v10 < 0 )
  {
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
      ComTraceMessageT<long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
        (unsigned int)"GetUserSid",
        1876,
        0,
        (__int64)L"%!STATUS!",
        v10);
    HeapFree(g_hHeap, 0, v9);
    return 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18006cb10  push    rbx
0x18006cb12  push    rbp
0x18006cb13  push    rsi
0x18006cb14  push    rdi
0x18006cb15  sub     rsp, 0C8h
0x18006cb1c  mov     rax, cs:__security_cookie
0x18006cb23  xor     rax, rsp
0x18006cb26  mov     [rsp+0E8h+var_38], rax
0x18006cb2e  mov     r9d, 64h ; 'd'; TokenInformationLength
0x18006cb34  mov     [rsp+0E8h+TokenInformationLength], 0
0x18006cb3c  lea     rax, [rsp+0E8h+TokenInformationLength]
0x18006cb41  mov     rdi, rcx
0x18006cb44  lea     r8, [rsp+0E8h+TokenInformation]; TokenInformation
0x18006cb49  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x18006cb4e  lea     edx, [r9-63h]; TokenInformationClass
0x18006cb52  call    cs:__imp_NtQueryInformationToken
0x18006cb58  mov     r8d, eax
0x18006cb5b  test    eax, eax
0x18006cb5d  jns     loc_18006CC69
0x18006cb63  cmp     eax, 0C0000023h
0x18006cb68  jz      short loc_18006CBBF
0x18006cb6a  mov     ecx, cs:dword_18014E4B8
0x18006cb70  test    ecx, ecx
0x18006cb72  jnz     short loc_18006CB8D
0x18006cb74  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18006cb7a  jz      loc_18006CC62
0x18006cb80  call    IsWppLevelEnabled
0x18006cb85  test    al, al
0x18006cb87  jz      loc_18006CC62
0x18006cb8d  mov     [rsp+0E8h+var_C0], r8d
0x18006cb92  lea     rax, aStatus; "%!STATUS!"
0x18006cb99  mov     r8d, 711h
0x18006cb9f  mov     [rsp+0E8h+ReturnLength], rax
0x18006cba4  xor     r9d, r9d
0x18006cba7  lea     rdx, aGetusersid; "GetUserSid"
0x18006cbae  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18006cbb5  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18006cbba  jmp     loc_18006CC62
0x18006cbbf  mov     r8d, [rsp+0E8h+TokenInformationLength]; dwBytes
0x18006cbc4  xor     edx, edx; dwFlags
0x18006cbc6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006cbcd  call    cs:__imp_HeapAlloc
0x18006cbd3  mov     rbx, rax
0x18006cbd6  test    rax, rax
0x18006cbd9  jz      loc_18006CC62
0x18006cbdf  mov     r9d, [rsp+0E8h+TokenInformationLength]; TokenInformationLength
0x18006cbe4  lea     rax, [rsp+0E8h+TokenInformationLength]
0x18006cbe9  mov     esi, 1
0x18006cbee  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x18006cbf3  mov     edx, esi; TokenInformationClass
0x18006cbf5  mov     r8, rbx; TokenInformation
0x18006cbf8  mov     rcx, rdi; TokenHandle
0x18006cbfb  call    cs:__imp_NtQueryInformationToken
0x18006cc01  mov     r8d, eax
0x18006cc04  test    eax, eax
0x18006cc06  jns     short loc_18006CC70
0x18006cc08  mov     ecx, cs:dword_18014E4B8
0x18006cc0e  test    ecx, ecx
0x18006cc10  jnz     short loc_18006CC23
0x18006cc12  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18006cc18  jz      short loc_18006CC50
0x18006cc1a  call    IsWppLevelEnabled
0x18006cc1f  test    al, al
0x18006cc21  jz      short loc_18006CC50
0x18006cc23  mov     [rsp+0E8h+var_C0], r8d
0x18006cc28  lea     rax, aStatus; "%!STATUS!"
0x18006cc2f  mov     r8d, 732h
0x18006cc35  mov     [rsp+0E8h+ReturnLength], rax
0x18006cc3a  xor     r9d, r9d
0x18006cc3d  lea     rdx, aGetusersid; "GetUserSid"
0x18006cc44  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18006cc4b  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18006cc50  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006cc57  mov     r8, rbx; lpMem
0x18006cc5a  xor     edx, edx; dwFlags
0x18006cc5c  call    cs:__imp_HeapFree
0x18006cc62  xor     eax, eax
0x18006cc64  jmp     loc_18006CD2A
0x18006cc69  xor     esi, esi
0x18006cc6b  lea     rbx, [rsp+0E8h+TokenInformation]
0x18006cc70  mov     rcx, [rbx]; Sid
0x18006cc73  call    cs:__imp_RtlLengthSid
0x18006cc79  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006cc80  xor     edx, edx; dwFlags
0x18006cc82  mov     r8d, eax; dwBytes
0x18006cc85  mov     [rsp+0E8h+TokenInformationLength], r8d
0x18006cc8a  call    cs:__imp_HeapAlloc
0x18006cc90  mov     rdi, rax
0x18006cc93  test    rax, rax
0x18006cc96  jnz     short loc_18006CC9F
0x18006cc98  cmp     esi, 1
0x18006cc9b  jnz     short loc_18006CC62
0x18006cc9d  jmp     short loc_18006CC50
0x18006cc9f  mov     r8, [rbx]; SourceSid
0x18006cca2  mov     rdx, rdi; DestinationSid
0x18006cca5  mov     ecx, [rsp+0E8h+TokenInformationLength]; DestinationSidLength
0x18006cca9  call    cs:__imp_RtlCopySid
0x18006ccaf  mov     ebp, eax
0x18006ccb1  cmp     esi, 1
0x18006ccb4  jnz     short loc_18006CCC8
0x18006ccb6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006ccbd  mov     r8, rbx; lpMem
0x18006ccc0  xor     edx, edx; dwFlags
0x18006ccc2  call    cs:__imp_HeapFree
0x18006ccc8  test    ebp, ebp
0x18006ccca  jns     short loc_18006CD27
0x18006cccc  mov     ecx, cs:dword_18014E4B8
0x18006ccd2  test    ecx, ecx
0x18006ccd4  jnz     short loc_18006CCE7
0x18006ccd6  cmp     cs:?gfEnableTracing@@3HA, ecx; int gfEnableTracing
0x18006ccdc  jz      short loc_18006CD13
0x18006ccde  call    IsWppLevelEnabled
0x18006cce3  test    al, al
0x18006cce5  jz      short loc_18006CD13
0x18006cce7  lea     rax, aStatus; "%!STATUS!"
0x18006ccee  mov     [rsp+0E8h+var_C0], ebp
0x18006ccf2  xor     r9d, r9d
0x18006ccf5  mov     [rsp+0E8h+ReturnLength], rax
0x18006ccfa  mov     r8d, 754h
0x18006cd00  lea     rdx, aGetusersid; "GetUserSid"
0x18006cd07  lea     rcx, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18006cd0e  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18006cd13  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006cd1a  mov     r8, rdi; lpMem
0x18006cd1d  xor     edx, edx; dwFlags
0x18006cd1f  call    cs:__imp_HeapFree
0x18006cd25  xor     edi, edi
0x18006cd27  mov     rax, rdi
0x18006cd2a  mov     rcx, [rsp+0E8h+var_38]
0x18006cd32  xor     rcx, rsp; StackCookie
0x18006cd35  call    __security_check_cookie
0x18006cd3a  add     rsp, 0C8h
0x18006cd41  pop     rdi
0x18006cd42  pop     rsi
0x18006cd43  pop     rbp
0x18006cd44  pop     rbx
0x18006cd45  retn
```
