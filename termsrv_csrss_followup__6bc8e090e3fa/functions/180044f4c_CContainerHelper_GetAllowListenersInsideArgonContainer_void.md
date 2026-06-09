# CContainerHelper::GetAllowListenersInsideArgonContainer(void)

- ea: `0x180044f4c`
- end: `0x1800450f6`
- name: `?GetAllowListenersInsideArgonContainer@CContainerHelper@@CAKXZ`
- size: `426`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800492d0`

## callees

- `0x180033f60`
- `0x180044f4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800450b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800450b6`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180044fb7`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180044fb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ff6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045091`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044ff6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800450d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800450d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044f95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180044f95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045045`

## string_xrefs

- `0x180044fef`: `AllowListenersInsideArgonContainer`

## pseudocode

```c
__int64 CContainerHelper::GetAllowListenersInsideArgonContainer(void)
{
  int v0; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD Type; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-38h] BYREF
  BYTE v7[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v8; // [rsp+60h] [rbp-20h]
  __int16 v9; // [rsp+70h] [rbp-10h]

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
  {
    cbData = 0;
    Type = 0;
    phkResult = 0;
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"AllowListenersInsideArgonContainer", 0, &Type, Data, &cbData) || Type != 4 )
      {
        v0 = 0;
        *(_DWORD *)Data = 0;
      }
      else
      {
        v0 = *(_DWORD *)Data;
      }
      if ( v0 )
      {
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                0,
                0x20019u,
                &phkResult) )
        {
          cbData = 34;
          v9 = 0;
          *(_OWORD *)v7 = 0;
          v8 = 0;
          if ( !RegQueryValueExW(phkResult, L"EditionID", 0, &Type, v7, &cbData)
            && Type == 1
            && !(unsigned int)_o__wcsnicmp(v7, L"ContainerOSPlus", 15) )
          {
            *(_DWORD *)Data = 1;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x180044f4c  push    rbp
0x180044f4e  mov     rbp, rsp
0x180044f51  sub     rsp, 80h
0x180044f58  mov     rax, cs:__security_cookie
0x180044f5f  xor     rax, rsp
0x180044f62  mov     [rbp+var_8], rax
0x180044f66  lea     rax, [rbp+hKey]
0x180044f6a  mov     [rbp+hKey], 0
0x180044f72  mov     r9d, 20019h; samDesired
0x180044f78  mov     [rsp+80h+phkResult], rax; phkResult
0x180044f7d  xor     r8d, r8d; ulOptions
0x180044f80  mov     dword ptr [rbp+Data], 0
0x180044f87  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180044f8e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044f95  call    cs:__imp_RegOpenKeyExW
0x180044f9c  nop     dword ptr [rax+rax+00h]
0x180044fa1  test    eax, eax
0x180044fa3  jnz     loc_1800450DD
0x180044fa9  mov     [rbp+cbData], eax
0x180044fac  mov     [rbp+Type], eax
0x180044faf  mov     [rbp+var_38], 0
0x180044fb7  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180044fbe  nop     dword ptr [rax+rax+00h]
0x180044fc3  test    eax, eax
0x180044fc5  jz      loc_1800450CD
0x180044fcb  mov     rcx, [rbp+hKey]; hKey
0x180044fcf  lea     rax, [rbp+cbData]
0x180044fd3  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180044fd8  lea     r9, [rbp+Type]; lpType
0x180044fdc  lea     rax, [rbp+Data]
0x180044fe0  mov     [rbp+cbData], 4
0x180044fe7  xor     r8d, r8d; lpReserved
0x180044fea  mov     [rsp+80h+phkResult], rax; lpData
0x180044fef  lea     rdx, aAllowlisteners; "AllowListenersInsideArgonContainer"
0x180044ff6  call    cs:__imp_RegQueryValueExW
0x180044ffd  nop     dword ptr [rax+rax+00h]
0x180045002  test    eax, eax
0x180045004  jnz     short loc_180045011
0x180045006  cmp     [rbp+Type], 4
0x18004500a  jnz     short loc_180045011
0x18004500c  mov     eax, dword ptr [rbp+Data]
0x18004500f  jmp     short loc_180045016
0x180045011  xor     eax, eax
0x180045013  mov     dword ptr [rbp+Data], eax
0x180045016  test    eax, eax
0x180045018  jz      loc_1800450CD
0x18004501e  lea     rax, [rbp+var_38]
0x180045022  mov     dword ptr [rbp+Data], 0
0x180045029  mov     r9d, 20019h; samDesired
0x18004502f  mov     [rsp+80h+phkResult], rax; phkResult
0x180045034  xor     r8d, r8d; ulOptions
0x180045037  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18004503e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045045  call    cs:__imp_RegOpenKeyExW
0x18004504c  nop     dword ptr [rax+rax+00h]
0x180045051  test    eax, eax
0x180045053  jnz     short loc_1800450CD
0x180045055  mov     rcx, [rbp+var_38]; hKey
0x180045059  lea     r9, [rbp+Type]; lpType
0x18004505d  xor     eax, eax
0x18004505f  mov     [rbp+cbData], 22h ; '"'
0x180045066  mov     [rbp+var_10], ax
0x18004506a  lea     rdx, aEditionid; "EditionID"
0x180045071  xorps   xmm0, xmm0
0x180045074  lea     rax, [rbp+cbData]
0x180045078  mov     [rsp+80h+lpcbData], rax; lpcbData
0x18004507d  xor     r8d, r8d; lpReserved
0x180045080  lea     rax, [rbp+var_30]
0x180045084  mov     [rsp+80h+phkResult], rax; lpData
0x180045089  movups  xmmword ptr [rbp+var_30], xmm0
0x18004508d  movups  [rbp+var_20], xmm0
0x180045091  call    cs:__imp_RegQueryValueExW
0x180045098  nop     dword ptr [rax+rax+00h]
0x18004509d  test    eax, eax
0x18004509f  jnz     short loc_1800450CD
0x1800450a1  cmp     [rbp+Type], 1
0x1800450a5  jnz     short loc_1800450CD
0x1800450a7  lea     r8d, [rax+0Fh]
0x1800450ab  lea     rdx, aContainerosplu; "ContainerOSPlus"
0x1800450b2  lea     rcx, [rbp+var_30]
0x1800450b6  call    cs:__imp__o__wcsnicmp
0x1800450bd  nop     dword ptr [rax+rax+00h]
0x1800450c2  test    eax, eax
0x1800450c4  jnz     short loc_1800450CD
0x1800450c6  mov     dword ptr [rbp+Data], 1
0x1800450cd  mov     rcx, [rbp+hKey]; hKey
0x1800450d1  call    cs:__imp_RegCloseKey
0x1800450d8  nop     dword ptr [rax+rax+00h]
0x1800450dd  mov     eax, dword ptr [rbp+Data]
0x1800450e0  mov     rcx, [rbp+var_8]
0x1800450e4  xor     rcx, rsp; StackCookie
0x1800450e7  call    __security_check_cookie
0x1800450ec  add     rsp, 80h
0x1800450f3  pop     rbp
0x1800450f4  retn
```
