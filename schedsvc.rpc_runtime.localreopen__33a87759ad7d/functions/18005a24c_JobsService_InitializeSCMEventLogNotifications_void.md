# JobsService::InitializeSCMEventLogNotifications(void)

- ea: `0x18005a24c`
- end: `0x18005a3d6`
- name: `?InitializeSCMEventLogNotifications@JobsService@@AEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(JobsService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18004f190`

## callees

- `0x180054084`
- `0x18005a24c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a316`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a3b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a3c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a3b7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005a3c5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005a2e9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005a2e9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005a269`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005a269`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18005a3a9`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18005a3a9`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18005a33d`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x18005a33d`

## pseudocode

```c
__int64 __fastcall JobsService::InitializeSCMEventLogNotifications(JobsService *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rdi
  DWORD LastError; // eax
  __int64 v6; // rdx
  signed int v7; // eax
  int v8; // ebx
  __int64 v10; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  v2 = OpenSCManagerW(0, 0, 4u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    LastError = GetLastError();
    v6 = 26;
LABEL_6:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids, LastError);
LABEL_7:
    v7 = GetLastError();
    v8 = v7;
    if ( v7 <= 0 )
      goto LABEL_23;
    v8 = (unsigned __int16)v7;
    goto LABEL_9;
  }
  v4 = OpenServiceW(v2, L"EventLog", 4u);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    LastError = GetLastError();
    v6 = 27;
    goto LABEL_6;
  }
  v8 = SubscribeServiceChangeNotifications(v4, 2, JobsService::SCMEventLogNotificationCallback, this, &v10);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids,
        (unsigned int)v8);
    }
    if ( v8 > 0 )
    {
      v8 = (unsigned __int16)v8;
LABEL_9:
      v8 |= 0x80070000;
    }
  }
  else
  {
    v8 = 0;
    *((_QWORD *)this + 17) = v10;
    v10 = 0;
  }
LABEL_23:
  if ( v10 )
    UnsubscribeServiceChangeNotifications();
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v3 )
    CloseServiceHandle(v3);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005a24c  push    rbx
0x18005a24e  push    rbp
0x18005a24f  push    rsi
0x18005a250  push    rdi
0x18005a251  sub     rsp, 38h
0x18005a255  xor     edx, edx; lpDatabaseName
0x18005a257  mov     [rsp+58h+arg_8], 0
0x18005a260  mov     rbp, rcx
0x18005a263  xor     ecx, ecx; lpMachineName
0x18005a265  lea     r8d, [rdx+4]; dwDesiredAccess
0x18005a269  call    cs:__imp_OpenSCManagerW
0x18005a26f  mov     rsi, rax
0x18005a272  test    rax, rax
0x18005a275  jnz     short loc_18005A2D9
0x18005a277  xor     edi, edi
0x18005a279  mov     rdx, cs:WPP_GLOBAL_Control
0x18005a280  lea     rcx, WPP_GLOBAL_Control
0x18005a287  cmp     rdx, rcx
0x18005a28a  jz      short loc_18005A2BB
0x18005a28c  test    byte ptr [rdx+1Ch], 4
0x18005a290  jz      short loc_18005A2BB
0x18005a292  cmp     byte ptr [rdx+19h], 2
0x18005a296  jb      short loc_18005A2BB
0x18005a298  call    cs:__imp_GetLastError
0x18005a29e  lea     edx, [rsi+1Ah]
0x18005a2a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2a8  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a2af  mov     r9d, eax
0x18005a2b2  mov     rcx, [rcx+10h]
0x18005a2b6  call    WPP_SF_d
0x18005a2bb  call    cs:__imp_GetLastError
0x18005a2c1  mov     ebx, eax
0x18005a2c3  test    eax, eax
0x18005a2c5  jle     loc_18005A39F
0x18005a2cb  movzx   ebx, ax
0x18005a2ce  or      ebx, 80070000h
0x18005a2d4  jmp     loc_18005A39F
0x18005a2d9  mov     r8d, 4; dwDesiredAccess
0x18005a2df  lea     rdx, ServiceName; "EventLog"
0x18005a2e6  mov     rcx, rsi; hSCManager
0x18005a2e9  call    cs:__imp_OpenServiceW
0x18005a2ef  mov     rdi, rax
0x18005a2f2  test    rax, rax
0x18005a2f5  jnz     short loc_18005A321
0x18005a2f7  mov     rdx, cs:WPP_GLOBAL_Control
0x18005a2fe  lea     rcx, WPP_GLOBAL_Control
0x18005a305  cmp     rdx, rcx
0x18005a308  jz      short loc_18005A2BB
0x18005a30a  test    byte ptr [rdx+1Ch], 4
0x18005a30e  jz      short loc_18005A2BB
0x18005a310  cmp     byte ptr [rdx+19h], 2
0x18005a314  jb      short loc_18005A2BB
0x18005a316  call    cs:__imp_GetLastError
0x18005a31c  lea     edx, [rdi+1Bh]
0x18005a31f  jmp     short loc_18005A2A1
0x18005a321  lea     rax, [rsp+58h+arg_8]
0x18005a326  mov     r9, rbp
0x18005a329  lea     r8, ?SCMEventLogNotificationCallback@JobsService@@CAXKPEAX@Z; JobsService::SCMEventLogNotificationCallback(ulong,void *)
0x18005a330  mov     [rsp+58h+var_38], rax
0x18005a335  mov     edx, 2
0x18005a33a  mov     rcx, rdi
0x18005a33d  call    cs:__imp_SubscribeServiceChangeNotifications
0x18005a343  mov     ebx, eax
0x18005a345  test    eax, eax
0x18005a347  jz      short loc_18005A38C
0x18005a349  mov     rax, cs:WPP_GLOBAL_Control
0x18005a350  lea     rcx, WPP_GLOBAL_Control
0x18005a357  cmp     rax, rcx
0x18005a35a  jz      short loc_18005A380
0x18005a35c  test    byte ptr [rax+1Ch], 4
0x18005a360  jz      short loc_18005A380
0x18005a362  cmp     byte ptr [rax+19h], 2
0x18005a366  jb      short loc_18005A380
0x18005a368  mov     rcx, [rax+10h]
0x18005a36c  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x18005a373  mov     edx, 1Ch
0x18005a378  mov     r9d, ebx
0x18005a37b  call    WPP_SF_d
0x18005a380  test    ebx, ebx
0x18005a382  jle     short loc_18005A39F
0x18005a384  movzx   ebx, bx
0x18005a387  jmp     loc_18005A2CE
0x18005a38c  mov     rax, [rsp+58h+arg_8]
0x18005a391  xor     ebx, ebx
0x18005a393  mov     [rbp+88h], rax
0x18005a39a  mov     [rsp+58h+arg_8], rbx
0x18005a39f  mov     rcx, [rsp+58h+arg_8]
0x18005a3a4  test    rcx, rcx
0x18005a3a7  jz      short loc_18005A3AF
0x18005a3a9  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x18005a3af  test    rdi, rdi
0x18005a3b2  jz      short loc_18005A3BD
0x18005a3b4  mov     rcx, rdi; hSCObject
0x18005a3b7  call    cs:__imp_CloseServiceHandle
0x18005a3bd  test    rsi, rsi
0x18005a3c0  jz      short loc_18005A3CB
0x18005a3c2  mov     rcx, rsi; hSCObject
0x18005a3c5  call    cs:__imp_CloseServiceHandle
0x18005a3cb  mov     eax, ebx
0x18005a3cd  add     rsp, 38h
0x18005a3d1  pop     rdi
0x18005a3d2  pop     rsi
0x18005a3d3  pop     rbp
0x18005a3d4  pop     rbx
0x18005a3d5  retn
```
