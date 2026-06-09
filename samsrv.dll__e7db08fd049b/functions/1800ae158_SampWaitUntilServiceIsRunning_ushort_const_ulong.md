# SampWaitUntilServiceIsRunning(ushort const *,ulong)

- ea: `0x1800ae158`
- end: `0x1800ae2c7`
- name: `?SampWaitUntilServiceIsRunning@@YAEPEBGK@Z`
- size: `367`
- prototype: `unsigned __int8 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18008e510`

## callees

- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x180039ef8`
- `0x1800ae158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800ae23c`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1800ae23c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae25e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae25e`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800ae228`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800ae228`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ae1f9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800ae1f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ae26c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ae27a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ae26c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800ae27a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ae1de`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800ae1de`

## pseudocode

```c
bool __fastcall SampWaitUntilServiceIsRunning(const unsigned __int16 *a1)
{
  SC_HANDLE v1; // rdi
  bool v2; // bl
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+30h] [rbp-88h] BYREF

  v1 = 0;
  v2 = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_Sd(
      WPP_GLOBAL_Control[3].Buffer,
      229,
      (unsigned int)WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      (unsigned int)L"RpcEptMapper",
      192);
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v3 = OpenSCManagerW(0, 0, 0x80000000);
  v4 = v3;
  if ( v3 )
  {
    v1 = OpenServiceW(v3, L"RpcEptMapper", 0x80000000);
    if ( v1 )
    {
      pNotifyBuffer.dwVersion = 2;
      pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
      if ( !NotifyServiceStatusChangeW(v1, 8u, &pNotifyBuffer) && SleepEx(0x927C0u, 1) == 192 )
        v2 = pNotifyBuffer.dwNotificationStatus == 0;
    }
  }
  if ( pNotifyBuffer.pszServiceNames )
    LocalFree(pNotifyBuffer.pszServiceNames);
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v4 )
    CloseServiceHandle(v4);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 230, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x1800ae158  push    rbx
0x1800ae15a  push    rbp
0x1800ae15b  push    rsi
0x1800ae15c  push    rdi
0x1800ae15d  sub     rsp, 98h
0x1800ae164  mov     rax, cs:__security_cookie
0x1800ae16b  xor     rax, rsp
0x1800ae16e  mov     [rsp+0B8h+var_38], rax
0x1800ae176  xor     edi, edi
0x1800ae178  lea     rcx, [rsp+0B8h+pNotifyBuffer]; void *
0x1800ae17d  xor     bl, bl
0x1800ae17f  xor     edx, edx; Val
0x1800ae181  lea     esi, [rdi+50h]
0x1800ae184  mov     r8d, esi; Size
0x1800ae187  call    memset_0
0x1800ae18c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae193  test    byte ptr [rcx+44h], 20h
0x1800ae197  jz      short loc_1800AE1C3
0x1800ae199  cmp     byte ptr [rcx+41h], 4
0x1800ae19d  jb      short loc_1800AE1C3
0x1800ae19f  mov     rcx, [rcx+38h]
0x1800ae1a3  lea     r9, ServiceName; "RpcEptMapper"
0x1800ae1aa  mov     edx, 0E5h
0x1800ae1af  mov     [rsp+0B8h+var_98], 927C0h
0x1800ae1b7  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ae1be  call    WPP_SF_Sd
0x1800ae1c3  mov     r8, rsi; Size
0x1800ae1c6  lea     rcx, [rsp+0B8h+pNotifyBuffer]; void *
0x1800ae1cb  xor     edx, edx; Val
0x1800ae1cd  call    memset_0
0x1800ae1d2  mov     ebp, 80000000h
0x1800ae1d7  xor     edx, edx; lpDatabaseName
0x1800ae1d9  mov     r8d, ebp; dwDesiredAccess
0x1800ae1dc  xor     ecx, ecx; lpMachineName
0x1800ae1de  call    cs:__imp_OpenSCManagerW
0x1800ae1e4  mov     rsi, rax
0x1800ae1e7  test    rax, rax
0x1800ae1ea  jz      short loc_1800AE254
0x1800ae1ec  mov     r8d, ebp; dwDesiredAccess
0x1800ae1ef  lea     rdx, ServiceName; "RpcEptMapper"
0x1800ae1f6  mov     rcx, rax; hSCManager
0x1800ae1f9  call    cs:__imp_OpenServiceW
0x1800ae1ff  mov     rdi, rax
0x1800ae202  test    rax, rax
0x1800ae205  jz      short loc_1800AE254
0x1800ae207  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800ae20e  mov     [rsp+0B8h+pNotifyBuffer.dwVersion], 2
0x1800ae216  lea     r8, [rsp+0B8h+pNotifyBuffer]; pNotifyBuffer
0x1800ae21b  mov     [rsp+0B8h+pNotifyBuffer.pfnNotifyCallback], rax
0x1800ae220  mov     edx, 8; dwNotifyMask
0x1800ae225  mov     rcx, rdi; hService
0x1800ae228  call    cs:__imp_NotifyServiceStatusChangeW
0x1800ae22e  test    eax, eax
0x1800ae230  jnz     short loc_1800AE254
0x1800ae232  lea     ebp, [rax+1]
0x1800ae235  mov     ecx, 927C0h; dwMilliseconds
0x1800ae23a  mov     edx, ebp; bAlertable
0x1800ae23c  call    cs:__imp_SleepEx
0x1800ae242  cmp     eax, 0C0h
0x1800ae247  jnz     short loc_1800AE254
0x1800ae249  cmp     [rsp+0B8h+pNotifyBuffer.dwNotificationStatus], 0
0x1800ae24e  movzx   ebx, bl
0x1800ae251  cmovz   ebx, ebp
0x1800ae254  mov     rcx, [rsp+0B8h+pNotifyBuffer.pszServiceNames]; hMem
0x1800ae259  test    rcx, rcx
0x1800ae25c  jz      short loc_1800AE264
0x1800ae25e  call    cs:__imp_LocalFree
0x1800ae264  test    rdi, rdi
0x1800ae267  jz      short loc_1800AE272
0x1800ae269  mov     rcx, rdi; hSCObject
0x1800ae26c  call    cs:__imp_CloseServiceHandle
0x1800ae272  test    rsi, rsi
0x1800ae275  jz      short loc_1800AE280
0x1800ae277  mov     rcx, rsi; hSCObject
0x1800ae27a  call    cs:__imp_CloseServiceHandle
0x1800ae280  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae287  test    dword ptr [rcx+44h], 20000h
0x1800ae28e  jz      short loc_1800AE2A9
0x1800ae290  mov     rcx, [rcx+38h]
0x1800ae294  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800ae29b  movzx   r9d, bl
0x1800ae29f  mov     edx, 0E6h
0x1800ae2a4  call    WPP_SF_d
0x1800ae2a9  mov     al, bl
0x1800ae2ab  mov     rcx, [rsp+0B8h+var_38]
0x1800ae2b3  xor     rcx, rsp; StackCookie
0x1800ae2b6  call    __security_check_cookie
0x1800ae2bb  add     rsp, 98h
0x1800ae2c2  pop     rdi
0x1800ae2c3  pop     rsi
0x1800ae2c4  pop     rbp
0x1800ae2c5  pop     rbx
0x1800ae2c6  retn
```
