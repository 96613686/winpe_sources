# WPDLibLogDeviceAccessEnforcementForUserSessions

- ea: `0x180014048`
- end: `0x180014149`
- name: `WPDLibLogDeviceAccessEnforcementForUserSessions`
- size: `257`
- prototype: `void __fastcall(__int64, void *, struct _SP_DEVINFO_DATA *, struct _ACL *, int, PEXPLICIT_ACCESS_W pListOfExplicitEntries)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eda4`

## callees

- `0x180006090`
- `0x180013038`
- `0x180014048`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001411f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001411f`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18001409a`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18001409a`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800140b9`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x1800140b9`
- `WTSAPI32!WTSFreeMemory` at `0x18001412e`
- `WTSAPI32!WTSFreeMemory` at `0x18001412e`

## pseudocode

```c
void __fastcall WPDLibLogDeviceAccessEnforcementForUserSessions(
        __int64 a1,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        struct _ACL *a4,
        int a5,
        PEXPLICIT_ACCESS_W pListOfExplicitEntries)
{
  DWORD v8; // edx
  __int64 v9; // rbx
  int v10; // edi
  struct _WTS_SESSION_INFOW *v11; // r9
  __int64 v12; // rcx
  ULONG *v13; // r9
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-10h] BYREF
  DWORD pCount; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+74h] [rbp+24h]
  ULONG pcCountOfExplicitEntries; // [rsp+88h] [rbp+38h] BYREF

  if ( a4 )
  {
    v16 = HIDWORD(a1);
    ppSessionInfo = 0;
    pListOfExplicitEntries = 0;
    pCount = 0;
    pcCountOfExplicitEntries = 0;
    if ( !GetExplicitEntriesFromAclW(a4, &pcCountOfExplicitEntries, &pListOfExplicitEntries) )
    {
      if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
      {
        v8 = pCount;
        v9 = 0;
        if ( pCount )
        {
          v10 = a5;
          do
          {
            v11 = &ppSessionInfo[v9];
            if ( v11->SessionId && (unsigned int)SessionNotActive((unsigned int)v11->State) )
            {
              LogDeviceAccessEnforcementForUserSession(
                v12,
                a2,
                a3,
                v13,
                pcCountOfExplicitEntries,
                (__int64)pListOfExplicitEntries,
                v10);
              v8 = pCount;
            }
            v9 = (unsigned int)(v9 + 1);
          }
          while ( (unsigned int)v9 < v8 );
        }
      }
    }
    if ( pListOfExplicitEntries )
      LocalFree(pListOfExplicitEntries);
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
  }
}

```

## disassembly

```asm
0x180014048  test    r9, r9
0x18001404b  jz      locret_180014148
0x180014051  mov     [rsp-18h+arg_8], rbx
0x180014056  mov     [rsp-18h+arg_10], rsi
0x18001405b  mov     qword ptr [rsp-18h+arg_0], rcx
0x180014060  push    rbp
0x180014061  push    rdi
0x180014062  push    r14
0x180014064  mov     rbp, rsp
0x180014067  sub     rsp, 50h
0x18001406b  mov     rsi, r8
0x18001406e  mov     [rbp+ppSessionInfo], 0
0x180014076  mov     r14, rdx
0x180014079  mov     [rbp+pListOfExplicitEntries], 0
0x180014081  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180014085  mov     [rbp+arg_0], 0
0x18001408c  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x180014090  mov     [rbp+pcCountOfExplicitEntries], 0
0x180014097  mov     rcx, r9; pacl
0x18001409a  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800140a0  test    eax, eax
0x1800140a2  jnz     short loc_180014116
0x1800140a4  xor     edx, edx; Reserved
0x1800140a6  lea     rax, [rbp+arg_0]
0x1800140aa  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x1800140ae  mov     [rsp+50h+pCount], rax; pCount
0x1800140b3  xor     ecx, ecx; hServer
0x1800140b5  lea     r8d, [rdx+1]; Version
0x1800140b9  call    cs:__imp_WTSEnumerateSessionsW
0x1800140bf  test    eax, eax
0x1800140c1  jz      short loc_180014116
0x1800140c3  mov     edx, [rbp+arg_0]
0x1800140c6  xor     ebx, ebx
0x1800140c8  test    edx, edx
0x1800140ca  jz      short loc_180014116
0x1800140cc  mov     edi, [rbp+arg_20]
0x1800140cf  mov     rax, [rbp+ppSessionInfo]
0x1800140d3  lea     rcx, [rbx+rbx*2]
0x1800140d7  lea     r9, [rax+rcx*8]
0x1800140db  cmp     dword ptr [r9], 0
0x1800140df  jz      short loc_180014110
0x1800140e1  mov     ecx, [r9+10h]
0x1800140e5  call    SessionNotActive
0x1800140ea  test    eax, eax
0x1800140ec  jz      short loc_180014110
0x1800140ee  mov     rax, [rbp+pListOfExplicitEntries]
0x1800140f2  mov     r8, rsi
0x1800140f5  mov     [rsp+50h+var_20], edi
0x1800140f9  mov     rdx, r14
0x1800140fc  mov     [rsp+50h+var_28], rax
0x180014101  mov     eax, [rbp+pcCountOfExplicitEntries]
0x180014104  mov     dword ptr [rsp+50h+pCount], eax
0x180014108  call    LogDeviceAccessEnforcementForUserSession
0x18001410d  mov     edx, [rbp+arg_0]
0x180014110  inc     ebx
0x180014112  cmp     ebx, edx
0x180014114  jb      short loc_1800140CF
0x180014116  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x18001411a  test    rcx, rcx
0x18001411d  jz      short loc_180014125
0x18001411f  call    cs:__imp_LocalFree
0x180014125  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180014129  test    rcx, rcx
0x18001412c  jz      short loc_180014134
0x18001412e  call    cs:__imp_WTSFreeMemory
0x180014134  lea     r11, [rsp+50h+var_s0]
0x180014139  mov     rbx, [r11+28h]
0x18001413d  mov     rsi, [r11+30h]
0x180014141  mov     rsp, r11
0x180014144  pop     r14
0x180014146  pop     rdi
0x180014147  pop     rbp
0x180014148  retn
```
