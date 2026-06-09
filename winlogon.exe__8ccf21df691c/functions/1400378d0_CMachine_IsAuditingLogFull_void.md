# CMachine::IsAuditingLogFull(void)

- ea: `0x1400378d0`
- end: `0x1400379fd`
- name: `?IsAuditingLogFull@CMachine@@QEAAHXZ`
- size: `301`
- prototype: `__int64 __fastcall(CMachine *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140044c90`
- `0x140047370`
- `0x14006cf20`
- `0x140072040`

## callees

- `0x1400057f4`
- `0x1400378d0`
- `0x140055494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003797c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400379c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003797c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400379c9`
- `api-ms-win-eventlog-legacy-l1-1-0!GetEventLogInformation` at `0x14003792f`
- `api-ms-win-eventlog-legacy-l1-1-0!GetEventLogInformation` at `0x14003792f`
- `ext-ms-win-advapi32-eventlog-l1-1-0!CloseEventLog` at `0x140037946`
- `ext-ms-win-advapi32-eventlog-l1-1-0!CloseEventLog` at `0x140037946`
- `ext-ms-win-advapi32-eventlog-l1-1-0!OpenEventLogW` at `0x1400378fb`
- `ext-ms-win-advapi32-eventlog-l1-1-0!OpenEventLogW` at `0x1400378fb`

## string_xrefs

- `0x1400378eb`: `Security`

## pseudocode

```c
_BOOL8 __fastcall CMachine::IsAuditingLogFull(CMachine *this)
{
  BOOL v1; // ebx
  HANDLE v2; // rdi
  DWORD LastError; // eax
  DWORD v5; // eax
  CMachine *Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+48h] [rbp+10h] BYREF

  Buffer = this;
  if ( !(unsigned __int8)IsOpenEventLogWPresent() )
    return 0;
  v1 = 0;
  v2 = OpenEventLogW(0, L"Security");
  if ( v2 )
  {
    LODWORD(Buffer) = 0;
    pcbBytesNeeded = 0;
    if ( GetEventLogInformation(v2, 0, &Buffer, 4u, &pcbBytesNeeded) )
    {
      v1 = (_DWORD)Buffer != 0;
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_eb0c35367490364a64ba65f1cb81d003_Traceguids, LastError);
    }
    CloseEventLog(v2);
  }
  else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_eb0c35367490364a64ba65f1cb81d003_Traceguids, v5);
  }
  return v1;
}

```

## disassembly

```asm
0x1400378d0  mov     [rsp+Buffer], rcx
0x1400378d5  sub     rsp, 38h
0x1400378d9  call    IsOpenEventLogWPresent
0x1400378de  test    al, al
0x1400378e0  jz      loc_1400379A3
0x1400378e6  mov     [rsp+38h+arg_10], rbx
0x1400378eb  lea     rdx, aSecurity; "Security"
0x1400378f2  xor     ecx, ecx; lpUNCServerName
0x1400378f4  mov     [rsp+38h+var_8], rdi
0x1400378f9  xor     ebx, ebx
0x1400378fb  call    cs:__imp_OpenEventLogW
0x140037901  mov     rdi, rax
0x140037904  test    rax, rax
0x140037907  jz      loc_1400379AA
0x14003790d  lea     rax, [rsp+38h+arg_8]
0x140037912  mov     dword ptr [rsp+38h+Buffer], ebx
0x140037916  mov     r9d, 4; cbBufSize
0x14003791c  mov     [rsp+38h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140037921  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x140037926  mov     [rsp+38h+arg_8], ebx
0x14003792a  xor     edx, edx; dwInfoLevel
0x14003792c  mov     rcx, rdi; hEventLog
0x14003792f  call    cs:__imp_GetEventLogInformation
0x140037935  test    eax, eax
0x140037937  jz      short loc_14003795D
0x140037939  cmp     dword ptr [rsp+38h+Buffer], ebx
0x14003793d  jnz     loc_1400379F3
0x140037943  mov     rcx, rdi; hEventLog
0x140037946  call    cs:__imp_CloseEventLog
0x14003794c  mov     rdi, [rsp+38h+var_8]
0x140037951  mov     eax, ebx
0x140037953  mov     rbx, [rsp+38h+arg_10]
0x140037958  add     rsp, 38h
0x14003795c  retn
0x14003795d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037964  lea     rax, WPP_GLOBAL_Control
0x14003796b  cmp     rcx, rax
0x14003796e  jz      short loc_140037943
0x140037970  test    byte ptr [rcx+1Ch], 8
0x140037974  jz      short loc_140037943
0x140037976  cmp     byte ptr [rcx+19h], 2
0x14003797a  jb      short loc_140037943
0x14003797c  call    cs:__imp_GetLastError
0x140037982  mov     rcx, cs:WPP_GLOBAL_Control
0x140037989  lea     r8, WPP_eb0c35367490364a64ba65f1cb81d003_Traceguids
0x140037990  mov     edx, 0Bh
0x140037995  mov     r9d, eax
0x140037998  mov     rcx, [rcx+10h]
0x14003799c  call    WPP_SF_d
0x1400379a1  jmp     short loc_140037943
0x1400379a3  xor     eax, eax
0x1400379a5  add     rsp, 38h
0x1400379a9  retn
0x1400379aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400379b1  lea     rax, WPP_GLOBAL_Control
0x1400379b8  cmp     rcx, rax
0x1400379bb  jz      short loc_14003794C
0x1400379bd  test    byte ptr [rcx+1Ch], 8
0x1400379c1  jz      short loc_14003794C
0x1400379c3  cmp     byte ptr [rcx+19h], 2
0x1400379c7  jb      short loc_14003794C
0x1400379c9  call    cs:__imp_GetLastError
0x1400379cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400379d6  lea     r8, WPP_eb0c35367490364a64ba65f1cb81d003_Traceguids
0x1400379dd  mov     edx, 0Ch
0x1400379e2  mov     r9d, eax
0x1400379e5  mov     rcx, [rcx+10h]
0x1400379e9  call    WPP_SF_d
0x1400379ee  jmp     loc_14003794C
0x1400379f3  mov     ebx, 1
0x1400379f8  jmp     loc_140037943
```
