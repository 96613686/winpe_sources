# ScCheckServiceLogonSid

- ea: `0x140020e68`
- end: `0x140020f33`
- name: `ScCheckServiceLogonSid`
- size: `203`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140039100`

## callees

- `0x140004c58`
- `0x140020e68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020f0c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140020eb4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140020eb4`
- `ntdll!RtlReleaseSRWLockShared` at `0x140020ed7`
- `ntdll!RtlReleaseSRWLockShared` at `0x140020ed7`
- `ntdll!RtlAcquireSRWLockShared` at `0x140020e8c`
- `ntdll!RtlAcquireSRWLockShared` at `0x140020e8c`

## pseudocode

```c
__int64 __fastcall ScCheckServiceLogonSid(HANDLE TokenHandle, _DWORD *a2)
{
  void **i; // rdx
  void **v5; // rdi
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  RtlAcquireSRWLockShared(&g_ScServiceChannelLock);
  for ( i = (void **)g_ScServiceChannelContextListHead; ; i = v5 )
  {
    if ( i == (void **)&g_ScServiceChannelContextListHead )
    {
      *a2 = 5;
      return RtlReleaseSRWLockShared(&g_ScServiceChannelLock);
    }
    v5 = (void **)*i;
    if ( !CheckTokenMembership(TokenHandle, i[10], &IsMember) )
      break;
    if ( IsMember == 1 )
      return RtlReleaseSRWLockShared(&g_ScServiceChannelLock);
  }
  *a2 = 5;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 139, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, LastError);
  }
  return RtlReleaseSRWLockShared(&g_ScServiceChannelLock);
}

```

## disassembly

```asm
0x140020e68  mov     [rsp+arg_0], rbx
0x140020e6d  mov     [rsp+arg_8], rsi
0x140020e72  push    rdi
0x140020e73  sub     rsp, 20h
0x140020e77  mov     rsi, rcx
0x140020e7a  mov     [rsp+28h+IsMember], 0
0x140020e82  lea     rcx, g_ScServiceChannelLock
0x140020e89  mov     rbx, rdx
0x140020e8c  call    cs:__imp_RtlAcquireSRWLockShared
0x140020e92  mov     rdx, cs:g_ScServiceChannelContextListHead
0x140020e99  lea     rax, g_ScServiceChannelContextListHead
0x140020ea0  cmp     rdx, rax
0x140020ea3  jz      short loc_140020ECA
0x140020ea5  mov     rdi, [rdx]
0x140020ea8  lea     r8, [rsp+28h+IsMember]; IsMember
0x140020ead  mov     rdx, [rdx+50h]; SidToCheck
0x140020eb1  mov     rcx, rsi; TokenHandle
0x140020eb4  call    cs:__imp_CheckTokenMembership
0x140020eba  test    eax, eax
0x140020ebc  jz      short loc_140020EED
0x140020ebe  cmp     [rsp+28h+IsMember], 1
0x140020ec3  jz      short loc_140020ED0
0x140020ec5  mov     rdx, rdi
0x140020ec8  jmp     short loc_140020E99
0x140020eca  mov     dword ptr [rbx], 5
0x140020ed0  lea     rcx, g_ScServiceChannelLock
0x140020ed7  call    cs:__imp_RtlReleaseSRWLockShared
0x140020edd  mov     rbx, [rsp+28h+arg_0]
0x140020ee2  mov     rsi, [rsp+28h+arg_8]
0x140020ee7  add     rsp, 20h
0x140020eeb  pop     rdi
0x140020eec  retn
0x140020eed  mov     dword ptr [rbx], 5
0x140020ef3  mov     rax, cs:WPP_GLOBAL_Control
0x140020efa  lea     rcx, WPP_GLOBAL_Control
0x140020f01  cmp     rax, rcx
0x140020f04  jz      short loc_140020ED0
0x140020f06  test    byte ptr [rax+1Ch], 1
0x140020f0a  jz      short loc_140020ED0
0x140020f0c  call    cs:__imp_GetLastError
0x140020f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f19  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140020f20  mov     edx, 8Bh
0x140020f25  mov     r9d, eax
0x140020f28  mov     rcx, [rcx+10h]
0x140020f2c  call    WPP_SF_d
0x140020f31  jmp     short loc_140020ED0
```
