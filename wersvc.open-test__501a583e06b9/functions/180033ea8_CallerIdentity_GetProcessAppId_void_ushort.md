# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x180033ea8`
- end: `0x1800340ac`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `516`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, _QWORD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f988`

## callees

- `0x180003998`
- `0x18000cb10`
- `0x18002dad8`
- `0x180033c70`
- `0x180033d7c`
- `0x180033ea8`
- `0x1800340b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033ed7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033eee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033f2e`
- `ntdll!RtlFreeHeap` at `0x180034041`
- `ntdll!RtlFreeHeap` at `0x18003406d`
- `ntdll!RtlFreeHeap` at `0x180034094`
- `ntdll!RtlFreeHeap` at `0x180034041`
- `ntdll!RtlFreeHeap` at `0x18003406d`
- `ntdll!RtlFreeHeap` at `0x180034094`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  signed int LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  PVOID v9; // r8
  const unsigned __int16 *v10; // rcx
  int v11; // eax
  void *v12; // rbx
  unsigned int AppUserModelId; // eax
  unsigned int v14; // edi
  PVOID P[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *TokenHandle; // [rsp+40h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+18h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v7 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_8;
    }
    v7 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open(
                (HANDLE)v7,
                P,
                (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
                v5,
                (bool *)P[0]);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
  {
    v9 = P[0];
    if ( !P[0] )
      return (unsigned int)LastError;
LABEL_28:
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    return (unsigned int)LastError;
  }
  if ( LastError < 0 )
  {
    v8 = 165;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)P[0]);
LABEL_15:
    v9 = P[0];
    goto LABEL_28;
  }
  LODWORD(TokenHandle) = 0;
  if ( (unsigned int)ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                       (ARI::ProcessToken::AutoSysAppId *)P,
                       0,
                       (unsigned int *)&TokenHandle,
                       0) != 122 )
  {
    LastError = -2147418113;
    v8 = 168;
    goto LABEL_14;
  }
  pv = 0;
  CoTaskMemFree_0(0);
  v11 = CoAllocStringLen(v10, (unsigned int)TokenHandle, (unsigned __int16 **)&pv);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v11,
      (int)P[0]);
    CoTaskMemFree_0(pv);
    goto LABEL_15;
  }
  v12 = pv;
  AppUserModelId = ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                     (ARI::ProcessToken::AutoSysAppId *)P,
                     (unsigned int)TokenHandle,
                     (unsigned int *)&TokenHandle,
                     (unsigned __int16 *)pv);
  if ( AppUserModelId )
  {
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
            (const char *)AppUserModelId,
            (unsigned int)P[0]);
    CoTaskMemFree_0(v12);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v14;
  }
  else
  {
    *a2 = v12;
    CoTaskMemFree_0(0);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180033ea8  mov     [rsp-8+arg_10], rbx
0x180033ead  mov     [rsp-8+arg_18], rdi
0x180033eb2  push    rbp
0x180033eb3  mov     rbp, rsp
0x180033eb6  sub     rsp, 30h
0x180033eba  xorps   xmm0, xmm0
0x180033ebd  mov     qword ptr [rdx], 0
0x180033ec4  movdqu  xmmword ptr [rbp+P], xmm0
0x180033ec9  mov     rdi, rdx
0x180033ecc  mov     [rbp+TokenHandle], 0
0x180033ed4  mov     rbx, rcx
0x180033ed7  call    cs:__imp_GetCurrentProcess
0x180033edd  cmp     rbx, rax
0x180033ee0  jz      short loc_180033F0A
0x180033ee2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180033ee6  mov     edx, 8; DesiredAccess
0x180033eeb  mov     rcx, rbx; ProcessHandle
0x180033eee  call    cs:__imp_OpenProcessToken
0x180033ef4  test    eax, eax
0x180033ef6  jnz     short loc_180033F04
0x180033ef8  call    cs:__imp_GetLastError
0x180033efe  mov     ebx, eax
0x180033f00  test    eax, eax
0x180033f02  jnz     short loc_180033F34
0x180033f04  mov     rcx, [rbp+TokenHandle]
0x180033f08  jmp     short loc_180033F15
0x180033f0a  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180033f11  mov     [rbp+TokenHandle], rcx
0x180033f15  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x180033f19  lea     rdx, [rbp+P]; void *
0x180033f1d  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x180033f22  mov     rcx, [rbp+TokenHandle]; hObject
0x180033f26  mov     ebx, eax
0x180033f28  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180033f2c  jz      short loc_180033F34
0x180033f2e  call    cs:__imp_CloseHandle
0x180033f34  test    ebx, ebx
0x180033f36  jle     short loc_180033F41
0x180033f38  movzx   ebx, bx
0x180033f3b  or      ebx, 80070000h
0x180033f41  cmp     ebx, 80070490h
0x180033f47  jz      loc_180034077
0x180033f4d  cmp     ebx, 80070005h
0x180033f53  jz      loc_180034077
0x180033f59  test    ebx, ebx
0x180033f5b  jns     short loc_180033F7E
0x180033f5d  mov     edx, 0A5h; void *
0x180033f62  mov     rcx, [rbp+8]; this
0x180033f66  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180033f6d  mov     r9d, ebx; char *
0x180033f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f75  mov     r8, [rbp+P]
0x180033f79  jmp     loc_180034080
0x180033f7e  xor     r9d, r9d; unsigned __int16 *
0x180033f81  mov     dword ptr [rbp+TokenHandle], 0
0x180033f88  lea     r8, [rbp+TokenHandle]; unsigned int *
0x180033f8c  xor     edx, edx; unsigned int
0x180033f8e  lea     rcx, [rbp+P]; this
0x180033f92  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x180033f97  cmp     eax, 7Ah ; 'z'
0x180033f9a  jz      short loc_180033FA8
0x180033f9c  mov     ebx, 8000FFFFh
0x180033fa1  mov     edx, 0A8h
0x180033fa6  jmp     short loc_180033F62
0x180033fa8  xor     ecx, ecx; pv
0x180033faa  mov     [rbp+pv], 0
0x180033fb2  call    CoTaskMemFree_0
0x180033fb7  mov     edx, dword ptr [rbp+TokenHandle]; unsigned __int64
0x180033fba  lea     r8, [rbp+pv]; unsigned __int16 **
0x180033fbe  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x180033fc3  mov     ebx, eax
0x180033fc5  test    eax, eax
0x180033fc7  jns     short loc_180033FEC
0x180033fc9  mov     rcx, [rbp+8]; this
0x180033fcd  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180033fd4  mov     r9d, eax; char *
0x180033fd7  mov     edx, 0ABh; void *
0x180033fdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033fe1  mov     rcx, [rbp+pv]; pv
0x180033fe5  call    CoTaskMemFree_0
0x180033fea  jmp     short loc_180033F75
0x180033fec  mov     rbx, [rbp+pv]
0x180033ff0  lea     r8, [rbp+TokenHandle]; unsigned int *
0x180033ff4  mov     edx, dword ptr [rbp+TokenHandle]; unsigned int
0x180033ff7  lea     rcx, [rbp+P]; this
0x180033ffb  mov     r9, rbx; unsigned __int16 *
0x180033ffe  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x180034003  test    eax, eax
0x180034005  jz      short loc_18003404B
0x180034007  mov     rcx, [rbp+8]; this
0x18003400b  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180034012  mov     r9d, eax; char *
0x180034015  mov     edx, 0ACh; void *
0x18003401a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003401f  mov     rcx, rbx; pv
0x180034022  mov     edi, eax
0x180034024  call    CoTaskMemFree_0
0x180034029  mov     r8, [rbp+P]; P
0x18003402d  test    r8, r8
0x180034030  jz      short loc_180034047
0x180034032  mov     rcx, gs:60h
0x18003403b  xor     edx, edx; Flags
0x18003403d  mov     rcx, [rcx+30h]; HeapHandle
0x180034041  call    cs:__imp_RtlFreeHeap
0x180034047  mov     eax, edi
0x180034049  jmp     short loc_18003409C
0x18003404b  xor     ecx, ecx; pv
0x18003404d  mov     [rdi], rbx
0x180034050  call    CoTaskMemFree_0
0x180034055  mov     r8, [rbp+P]; P
0x180034059  test    r8, r8
0x18003405c  jz      short loc_180034073
0x18003405e  mov     rcx, gs:60h
0x180034067  xor     edx, edx; Flags
0x180034069  mov     rcx, [rcx+30h]; HeapHandle
0x18003406d  call    cs:__imp_RtlFreeHeap
0x180034073  xor     eax, eax
0x180034075  jmp     short loc_18003409C
0x180034077  mov     r8, [rbp+P]; P
0x18003407b  test    r8, r8
0x18003407e  jz      short loc_18003409A
0x180034080  test    r8, r8
0x180034083  jz      short loc_18003409A
0x180034085  mov     rcx, gs:60h
0x18003408e  xor     edx, edx; Flags
0x180034090  mov     rcx, [rcx+30h]; HeapHandle
0x180034094  call    cs:__imp_RtlFreeHeap
0x18003409a  mov     eax, ebx
0x18003409c  mov     rbx, [rsp+30h+arg_10]
0x1800340a1  mov     rdi, [rsp+30h+arg_18]
0x1800340a6  add     rsp, 30h
0x1800340aa  pop     rbp
0x1800340ab  retn
```
