# IsSASRequired(ulong)

- ea: `0x1800bb61c`
- end: `0x1800bb721`
- name: `?IsSASRequired@@YAHK@Z`
- size: `261`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180060a78`

## callees

- `0x180026b28`
- `0x180027438`
- `0x180068f60`
- `0x18006a20c`
- `0x1800bb61c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800bb666`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800bb666`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800bb670`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800bb670`
- `ntdll!RtlGetNtProductType` at `0x1800bb688`
- `ntdll!RtlGetNtProductType` at `0x1800bb688`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x1800bb652`
- `ext-ms-win-biometrics-winbio-l1-2-0!WinBioIsLegacy` at `0x1800bb652`
- `wkscli!NetGetJoinInformation` at `0x1800bb6a5`
- `wkscli!NetGetJoinInformation` at `0x1800bb6a5`
- `netutils!NetApiBufferFree` at `0x1800bb6b3`
- `netutils!NetApiBufferFree` at `0x1800bb6b3`

## pseudocode

```c
_BOOL8 __fastcall IsSASRequired(DWORD dwProcessId)
{
  int v2; // ebx
  DWORD pSessionId; // [rsp+20h] [rbp-39h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+24h] [rbp-35h] BYREF
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+28h] [rbp-31h] BYREF
  LPWSTR NameBuffer; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v8[96]; // [rsp+40h] [rbp-19h] BYREF

  pSessionId = 0;
  if ( (unsigned __int8)IsWinBioIsLegacyPresent()
    && (unsigned int)WinBioIsLegacy()
    && (!ProcessIdToSessionId(dwProcessId, &pSessionId) || WTSGetActiveConsoleSessionId() == pSessionId) )
  {
    ProductType = NtProductWinNt;
    v2 = 0;
    RtlGetNtProductType(&ProductType);
    if ( ProductType == NtProductWinNt )
    {
      BufferType = NetSetupUnknownStatus;
      NameBuffer = 0;
      if ( NetGetJoinInformation(0, &NameBuffer, &BufferType) )
      {
        v2 = 1;
      }
      else
      {
        NetApiBufferFree(NameBuffer);
        LOBYTE(v2) = BufferType != NetSetupDomainName;
      }
    }
    BioPolicy::Refresh((BioPolicy *)v8);
    if ( *(_DWORD *)&v8[8 * (int)BioPolicy::Values::make_index(6) + 4] != 1 )
      v2 = (unsigned __int8)v8[8 * (int)BioPolicy::Values::make_index(6)];
  }
  else
  {
    v2 = 1;
  }
  return v2 == 0;
}

```

## disassembly

```asm
0x1800bb61c  mov     [rsp-8+arg_8], rbx
0x1800bb621  push    rbp
0x1800bb622  lea     rbp, [rsp-57h]
0x1800bb627  sub     rsp, 0B0h
0x1800bb62e  mov     rax, cs:__security_cookie
0x1800bb635  xor     rax, rsp
0x1800bb638  mov     [rbp+57h+var_10], rax
0x1800bb63c  mov     ebx, ecx
0x1800bb63e  mov     [rbp+57h+pSessionId], 0
0x1800bb645  call    IsWinBioIsLegacyPresent
0x1800bb64a  test    al, al
0x1800bb64c  jz      loc_1800BB6F8
0x1800bb652  call    cs:__imp_WinBioIsLegacy
0x1800bb658  test    eax, eax
0x1800bb65a  jz      loc_1800BB6F8
0x1800bb660  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x1800bb664  mov     ecx, ebx; dwProcessId
0x1800bb666  call    cs:__imp_ProcessIdToSessionId
0x1800bb66c  test    eax, eax
0x1800bb66e  jz      short loc_1800BB67B
0x1800bb670  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800bb676  cmp     eax, [rbp+57h+pSessionId]
0x1800bb679  jnz     short loc_1800BB6F8
0x1800bb67b  lea     rcx, [rbp+57h+ProductType]; ProductType
0x1800bb67f  mov     [rbp+57h+ProductType], 1
0x1800bb686  xor     ebx, ebx
0x1800bb688  call    cs:__imp_RtlGetNtProductType
0x1800bb68e  cmp     [rbp+57h+ProductType], 1
0x1800bb692  jnz     short loc_1800BB6C7
0x1800bb694  lea     r8, [rbp+57h+BufferType]; BufferType
0x1800bb698  mov     [rbp+57h+BufferType], ebx
0x1800bb69b  lea     rdx, [rbp+57h+NameBuffer]; lpNameBuffer
0x1800bb69f  mov     [rbp+57h+NameBuffer], rbx
0x1800bb6a3  xor     ecx, ecx; lpServer
0x1800bb6a5  call    cs:__imp_NetGetJoinInformation
0x1800bb6ab  test    eax, eax
0x1800bb6ad  jnz     short loc_1800BB6C2
0x1800bb6af  mov     rcx, [rbp+57h+NameBuffer]; Buffer
0x1800bb6b3  call    cs:__imp_NetApiBufferFree
0x1800bb6b9  cmp     [rbp+57h+BufferType], 3
0x1800bb6bd  setnz   bl
0x1800bb6c0  jmp     short loc_1800BB6C7
0x1800bb6c2  mov     ebx, 1
0x1800bb6c7  lea     rcx, [rbp+57h+var_70]; this
0x1800bb6cb  call    ?Refresh@BioPolicy@@QEAAJXZ; BioPolicy::Refresh(void)
0x1800bb6d0  mov     ecx, 6
0x1800bb6d5  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x1800bb6da  movsxd  rdx, eax
0x1800bb6dd  cmp     [rbp+rdx*8+57h+var_6C], 1
0x1800bb6e2  jz      short loc_1800BB6FD
0x1800bb6e4  mov     ecx, 6
0x1800bb6e9  call    ?make_index@Values@BioPolicy@@SAHW4type@12@@Z; BioPolicy::Values::make_index(BioPolicy::Values::type)
0x1800bb6ee  movsxd  rcx, eax
0x1800bb6f1  movzx   ebx, [rbp+rcx*8+57h+var_70]
0x1800bb6f6  jmp     short loc_1800BB6FD
0x1800bb6f8  mov     ebx, 1
0x1800bb6fd  xor     eax, eax
0x1800bb6ff  test    ebx, ebx
0x1800bb701  setz    al
0x1800bb704  mov     rcx, [rbp+57h+var_10]
0x1800bb708  xor     rcx, rsp; StackCookie
0x1800bb70b  call    __security_check_cookie
0x1800bb710  mov     rbx, [rsp+0B0h+arg_8]
0x1800bb718  add     rsp, 0B0h
0x1800bb71f  pop     rbp
0x1800bb720  retn
```
