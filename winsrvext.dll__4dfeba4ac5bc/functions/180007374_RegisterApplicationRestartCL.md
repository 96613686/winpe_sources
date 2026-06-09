# RegisterApplicationRestartCL

- ea: `0x180007374`
- end: `0x180007555`
- name: `RegisterApplicationRestartCL`
- size: `481`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180005474`
- `0x180009688`

## callees

- `0x180004e88`
- `0x180004fb4`
- `0x180006918`
- `0x180007374`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180007445`
- `KERNELBASE!LocalAlloc` at `0x180007445`
- `ntdll!NtOpenProcessToken` at `0x1800073a9`
- `ntdll!NtOpenProcessToken` at `0x1800073a9`
- `ntdll!RtlLeaveCriticalSection` at `0x180007547`
- `ntdll!RtlLeaveCriticalSection` at `0x180007547`
- `ntdll!RtlEnterCriticalSection` at `0x18000751f`
- `ntdll!RtlEnterCriticalSection` at `0x18000751f`
- `ntdll!NtClose` at `0x1800073ca`
- `ntdll!NtClose` at `0x1800074f1`
- `ntdll!NtClose` at `0x1800073ca`
- `ntdll!NtClose` at `0x1800074f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007500`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007500`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180007475`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180007475`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800073f7`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800074a9`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800073f7`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800074a9`

## pseudocode

```c
int __fastcall RegisterApplicationRestartCL(HANDLE hProcess)
{
  _QWORD *v1; // rbx
  int v2; // r14d
  __int64 v4; // rdx
  HLOCAL v5; // rax
  unsigned __int64 v6; // rcx
  void *ProcessImpersonationToken; // rax
  void *v8; // rdi
  int v9; // eax
  DWORD pdwFlags; // [rsp+20h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-18h] BYREF
  _QWORD *v13; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcchSize; // [rsp+78h] [rbp+38h] BYREF
  DWORD dwSize; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  v2 = 786432;
  v13 = 0;
  pcchSize = 0;
  dwSize = 0;
  pdwFlags = 0;
  TokenHandle = 0;
  v16 = 786432;
  if ( NtOpenProcessToken(hProcess, 8u, &TokenHandle) < 0
    || (AppModelPolicy_GetPolicy(TokenHandle, v4, &v16), NtClose(TokenHandle), v2 = v16, v16 != 786433) )
  {
    pcchSize = 0;
    LODWORD(v5) = GetApplicationRestartSettings(hProcess, 0, &pcchSize, &pdwFlags);
    if ( (int)v5 < 0 )
      return (int)v5;
    if ( (pdwFlags & 8) != 0 )
      return (int)v5;
    LODWORD(v5) = pcchSize + 1;
    v6 = 2LL * ++pcchSize;
    if ( v6 > 0xFFFFFFFF )
      return (int)v5;
    LODWORD(v5) = v6 + 536;
    if ( (int)v6 + 536 < (unsigned int)v6 )
      return (int)v5;
    v5 = LocalAlloc(0x40u, (unsigned int)v5);
    v13 = v5;
    v1 = v5;
    if ( !v5 )
      return (int)v5;
    dwSize = 260;
    if ( !QueryFullProcessImageNameW(hProcess, 0, (LPWSTR)v5 + 8, &dwSize) )
      goto LABEL_15;
    *((_WORD *)v1 + dwSize + 8) = 32;
    --pcchSize;
    if ( GetApplicationRestartSettings(hProcess, (PWSTR)v1 + dwSize + 9, &pcchSize, 0) < 0 )
      goto LABEL_15;
  }
  ProcessImpersonationToken = GetProcessImpersonationToken(hProcess);
  v8 = ProcessImpersonationToken;
  if ( !ProcessImpersonationToken )
  {
LABEL_15:
    LODWORD(v5) = (unsigned int)LocalFree(v1);
    return (int)v5;
  }
  if ( v2 == 786433 )
  {
    v9 = BuildPackagedCWARestartProcessInfo(hProcess, (__int64)ProcessImpersonationToken, &v13);
    v1 = v13;
    if ( v9 < 0 || !v13 )
    {
      NtClose(v8);
      goto LABEL_15;
    }
  }
  RtlEnterCriticalSection(&gcsUserSrv);
  *v1 = gprpi;
  v1[1] = v8;
  gprpi = v1;
  LODWORD(v5) = RtlLeaveCriticalSection(&gcsUserSrv);
  return (int)v5;
}

```

## disassembly

```asm
0x180007374  push    rbp
0x180007376  push    rbx
0x180007377  push    rsi
0x180007378  push    rdi
0x180007379  push    r14
0x18000737b  mov     rbp, rsp
0x18000737e  sub     rsp, 40h
0x180007382  xor     ebx, ebx
0x180007384  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180007388  mov     r14d, 0C0000h
0x18000738e  mov     [rbp+var_10], rbx
0x180007392  mov     rsi, rcx
0x180007395  mov     [rbp+pcchSize], ebx
0x180007398  mov     [rbp+dwSize], ebx
0x18000739b  lea     edx, [rbx+8]; DesiredAccess
0x18000739e  mov     [rbp+pdwFlags], ebx
0x1800073a1  mov     [rbp+TokenHandle], rbx
0x1800073a5  mov     [rbp+arg_18], r14d
0x1800073a9  call    cs:__imp_NtOpenProcessToken
0x1800073b0  nop     dword ptr [rax+rax+00h]
0x1800073b5  test    eax, eax
0x1800073b7  js      short loc_1800073E7
0x1800073b9  mov     rcx, [rbp+TokenHandle]
0x1800073bd  lea     r8, [rbp+arg_18]
0x1800073c1  call    AppModelPolicy_GetPolicy
0x1800073c6  mov     rcx, [rbp+TokenHandle]; Handle
0x1800073ca  call    cs:__imp_NtClose
0x1800073d1  nop     dword ptr [rax+rax+00h]
0x1800073d6  mov     r14d, [rbp+arg_18]
0x1800073da  cmp     r14d, 0C0001h
0x1800073e1  jz      loc_1800074B9
0x1800073e7  lea     r9, [rbp+pdwFlags]; pdwFlags
0x1800073eb  mov     [rbp+pcchSize], ebx
0x1800073ee  lea     r8, [rbp+pcchSize]; pcchSize
0x1800073f2  xor     edx, edx; pwzCommandline
0x1800073f4  mov     rcx, rsi; hProcess
0x1800073f7  call    cs:__imp_GetApplicationRestartSettings
0x1800073fe  nop     dword ptr [rax+rax+00h]
0x180007403  test    eax, eax
0x180007405  js      loc_18000750C
0x18000740b  test    byte ptr [rbp+pdwFlags], 8
0x18000740f  jnz     loc_18000750C
0x180007415  mov     eax, [rbp+pcchSize]
0x180007418  mov     edi, 0FFFFFFFFh
0x18000741d  inc     eax
0x18000741f  mov     ecx, eax
0x180007421  add     rcx, rcx
0x180007424  mov     [rbp+pcchSize], eax
0x180007427  cmp     rcx, rdi
0x18000742a  ja      loc_18000750C
0x180007430  lea     eax, [rcx+218h]
0x180007436  cmp     eax, ecx
0x180007438  jb      loc_18000750C
0x18000743e  mov     edx, eax; uBytes
0x180007440  mov     ecx, 40h ; '@'; uFlags
0x180007445  call    cs:__imp_LocalAlloc
0x18000744c  nop     dword ptr [rax+rax+00h]
0x180007451  mov     [rbp+var_10], rax
0x180007455  mov     rbx, rax
0x180007458  test    rax, rax
0x18000745b  jz      loc_18000750C
0x180007461  lea     r8, [rax+10h]; lpExeName
0x180007465  mov     [rbp+dwSize], 104h
0x18000746c  lea     r9, [rbp+dwSize]; lpdwSize
0x180007470  xor     edx, edx; dwFlags
0x180007472  mov     rcx, rsi; hProcess
0x180007475  call    cs:__imp_QueryFullProcessImageNameW
0x18000747c  nop     dword ptr [rax+rax+00h]
0x180007481  test    eax, eax
0x180007483  jz      short loc_1800074FD
0x180007485  mov     eax, [rbp+dwSize]
0x180007488  lea     r8, [rbp+pcchSize]; pcchSize
0x18000748c  xor     r9d, r9d; pdwFlags
0x18000748f  mov     word ptr [rbx+rax*2+10h], 20h ; ' '
0x180007496  mov     ecx, [rbp+dwSize]
0x180007499  add     [rbp+pcchSize], edi
0x18000749c  inc     ecx
0x18000749e  add     rcx, 8
0x1800074a2  lea     rdx, [rbx+rcx*2]; pwzCommandline
0x1800074a6  mov     rcx, rsi; hProcess
0x1800074a9  call    cs:__imp_GetApplicationRestartSettings
0x1800074b0  nop     dword ptr [rax+rax+00h]
0x1800074b5  test    eax, eax
0x1800074b7  js      short loc_1800074FD
0x1800074b9  mov     rcx, rsi
0x1800074bc  call    GetProcessImpersonationToken
0x1800074c1  mov     rdi, rax
0x1800074c4  test    rax, rax
0x1800074c7  jz      short loc_1800074FD
0x1800074c9  cmp     r14d, 0C0001h
0x1800074d0  jnz     short loc_180007518
0x1800074d2  lea     r8, [rbp+var_10]
0x1800074d6  mov     rdx, rax
0x1800074d9  mov     rcx, rsi; hProcess
0x1800074dc  call    BuildPackagedCWARestartProcessInfo
0x1800074e1  mov     rbx, [rbp+var_10]
0x1800074e5  test    eax, eax
0x1800074e7  js      short loc_1800074EE
0x1800074e9  test    rbx, rbx
0x1800074ec  jnz     short loc_180007518
0x1800074ee  mov     rcx, rdi; Handle
0x1800074f1  call    cs:__imp_NtClose
0x1800074f8  nop     dword ptr [rax+rax+00h]
0x1800074fd  mov     rcx, rbx; hMem
0x180007500  call    cs:__imp_LocalFree
0x180007507  nop     dword ptr [rax+rax+00h]
0x18000750c  add     rsp, 40h
0x180007510  pop     r14
0x180007512  pop     rdi
0x180007513  pop     rsi
0x180007514  pop     rbx
0x180007515  pop     rbp
0x180007516  retn
0x180007518  lea     rcx, gcsUserSrv; CriticalSection
0x18000751f  call    cs:__imp_RtlEnterCriticalSection
0x180007526  nop     dword ptr [rax+rax+00h]
0x18000752b  mov     rax, cs:gprpi
0x180007532  lea     rcx, gcsUserSrv; CriticalSection
0x180007539  mov     [rbx], rax
0x18000753c  mov     [rbx+8], rdi
0x180007540  mov     cs:gprpi, rbx
0x180007547  call    cs:__imp_RtlLeaveCriticalSection
0x18000754e  nop     dword ptr [rax+rax+00h]
0x180007553  jmp     short loc_18000750C
```
