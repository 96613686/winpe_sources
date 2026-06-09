# SendProcessEventMessage

- ea: `0x14000b418`
- end: `0x14000b5b2`
- name: `SendProcessEventMessage`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000adf0`

## callees

- `0x140001118`
- `0x1400011b0`
- `0x140001298`
- `0x14000a994`
- `0x14000aec4`
- `0x14000b418`

## import_xrefs

- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b584`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000bcaa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b584`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000bcaa`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b489`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b489`
- `FLTMGR!FltSendMessage` at `0x14000b538`
- `FLTMGR!FltSendMessage` at `0x14000b538`

## pseudocode

```c
__int64 __fastcall SendProcessEventMessage(void *a1, __int64 a2, __int64 a3)
{
  int SessionIdFromProcessId; // eax
  int v6; // ebx
  __int64 v7; // rcx
  NTSTATUS v8; // eax
  PFLT_PORT ClientPort; // [rsp+48h] [rbp-20h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+78h] [rbp+10h] BYREF
  ULONG ReplyLength; // [rsp+80h] [rbp+18h] BYREF
  int SenderBuffer; // [rsp+88h] [rbp+20h] BYREF
  int SenderBuffer_4; // [rsp+8Ch] [rbp+24h]

  v11 = 0;
  if ( !byte_140007138 )
    return 0;
  DbgTrace(2, "UevFilter.SendProcessEventMessage: Entry\n", a3);
  SessionIdFromProcessId = GetSessionIdFromProcessId(a1, &v11);
  v6 = SessionIdFromProcessId;
  if ( SessionIdFromProcessId < 0 )
    DbgTraceFrmtErr(
      "UevFilter.SendProcessEventMessage: Failed to get session ID. Error = 0x%0X.\n",
      SessionIdFromProcessId);
  if ( v6 >= 0 && v11 )
  {
    KeAcquireGuardedMutex(&Mutex);
    if ( P )
    {
      ClientPort = 0;
      if ( (unsigned __int8)FindKeyInFilterHashTable(v7, v11, &ClientPort) && ClientPort )
      {
        SenderBuffer = 2;
        ReplyLength = 0;
        Timeout.QuadPart = -1000000;
        SenderBuffer_4 = (int)a1;
        v8 = FltSendMessage(g_pFilter, &ClientPort, &SenderBuffer, 8u, 0, &ReplyLength, &Timeout);
        v6 = v8;
        if ( v8 < 0 )
          DbgTraceFrmtErr("UevFilter.SendProcessEventMessage: Failed to send message. Error = 0x%0X.\n", v8);
        else
          DbgTraceFrmt(1u, "UevFilter.SendProcessEventMessage: Process %d has started.\n", (_DWORD)a1);
      }
    }
    else
    {
      v6 = -1073741769;
    }
    KeReleaseGuardedMutex(&Mutex);
  }
  DbgTraceFrmt(2u, "UevFilter.SendProcessEventMessage: Exit, retStatus = 0x%0X.\n", v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000b418  mov     [rsp+arg_0], rbx
0x14000b41d  push    rdi
0x14000b41e  sub     rsp, 60h
0x14000b422  mov     rdi, rcx
0x14000b425  mov     [rsp+68h+arg_8], 0
0x14000b42d  cmp     cs:byte_140007138, 0
0x14000b434  jnz     short loc_14000B43D
0x14000b436  xor     eax, eax
0x14000b438  jmp     loc_14000B5A6
0x14000b43d  lea     rdx, aUevfilterSendp_0; "UevFilter.SendProcessEventMessage: Entr"...
0x14000b444  mov     ecx, 2
0x14000b449  call    DbgTrace
0x14000b44e  lea     rdx, [rsp+68h+arg_8]
0x14000b453  mov     rcx, rdi
0x14000b456  call    GetSessionIdFromProcessId
0x14000b45b  mov     ebx, eax
0x14000b45d  test    eax, eax
0x14000b45f  jns     short loc_14000B46F
0x14000b461  mov     edx, eax
0x14000b463  lea     rcx, aUevfilterSendp_1; "UevFilter.SendProcessEventMessage: Fail"...
0x14000b46a  call    DbgTraceFrmtErr
0x14000b46f  test    ebx, ebx
0x14000b471  js      loc_14000B590
0x14000b477  cmp     [rsp+68h+arg_8], 0
0x14000b47c  jz      loc_14000B590
0x14000b482  lea     rcx, Mutex; Mutex
0x14000b489  call    cs:__imp_KeAcquireGuardedMutex
0x14000b490  nop     dword ptr [rax+rax+00h]
0x14000b495  cmp     cs:P, 0
0x14000b49d  jz      loc_14000B574
0x14000b4a3  mov     [rsp+68h+ClientPort], 0
0x14000b4ac  mov     edx, [rsp+68h+arg_8]
0x14000b4b0  lea     r8, [rsp+68h+ClientPort]
0x14000b4b5  call    FindKeyInFilterHashTable
0x14000b4ba  test    al, al
0x14000b4bc  jz      loc_14000B57D
0x14000b4c2  cmp     [rsp+68h+ClientPort], 0
0x14000b4c8  jz      loc_14000B57D
0x14000b4ce  mov     [rsp+68h+SenderBuffer], 2
0x14000b4da  mov     [rsp+68h+arg_10], 0
0x14000b4e5  mov     qword ptr [rsp+68h+var_18], 0
0x14000b4ee  mov     qword ptr [rsp+68h+var_18], 0FFFFFFFFFFF0BDC0h
0x14000b4f7  mov     dword ptr [rsp+68h+SenderBuffer+4], edi
0x14000b4fe  lea     rax, [rsp+68h+var_18]
0x14000b503  mov     [rsp+68h+Timeout], rax; Timeout
0x14000b508  lea     rax, [rsp+68h+arg_10]
0x14000b510  mov     [rsp+68h+ReplyLength], rax; ReplyLength
0x14000b515  mov     [rsp+68h+ReplyBuffer], 0; ReplyBuffer
0x14000b51e  mov     r9d, 8; SenderBufferLength
0x14000b524  lea     r8, [rsp+68h+SenderBuffer]; SenderBuffer
0x14000b52c  lea     rdx, [rsp+68h+ClientPort]; ClientPort
0x14000b531  mov     rcx, cs:g_pFilter; Filter
0x14000b538  call    cs:__imp_FltSendMessage
0x14000b53f  nop     dword ptr [rax+rax+00h]
0x14000b544  mov     ebx, eax
0x14000b546  mov     [rsp+68h+var_28], eax
0x14000b54a  test    eax, eax
0x14000b54c  js      short loc_14000B564
0x14000b54e  mov     r8, rdi
0x14000b551  lea     rdx, aUevfilterSendp; "UevFilter.SendProcessEventMessage: Proc"...
0x14000b558  mov     ecx, 1
0x14000b55d  call    DbgTraceFrmt
0x14000b562  jmp     short loc_14000B57D
0x14000b564  mov     edx, eax
0x14000b566  lea     rcx, aUevfilterSendp_2; "UevFilter.SendProcessEventMessage: Fail"...
0x14000b56d  call    DbgTraceFrmtErr
0x14000b572  jmp     short loc_14000B57D
0x14000b574  mov     ebx, 0C0000037h
0x14000b579  mov     [rsp+68h+var_28], ebx
0x14000b57d  lea     rcx, Mutex; Mutex
0x14000b584  call    cs:__imp_KeReleaseGuardedMutex
0x14000b58b  nop     dword ptr [rax+rax+00h]
0x14000b590  mov     r8d, ebx
0x14000b593  lea     rdx, aUevfilterSendp_3; "UevFilter.SendProcessEventMessage: Exit"...
0x14000b59a  mov     ecx, 2
0x14000b59f  call    DbgTraceFrmt
0x14000b5a4  mov     eax, ebx
0x14000b5a6  mov     rbx, [rsp+68h+arg_0]
0x14000b5ab  add     rsp, 60h
0x14000b5af  pop     rdi
0x14000b5b0  retn
0x14000bc9a  push    rbp
0x14000bc9c  sub     rsp, 40h
0x14000bca0  mov     rbp, rdx
0x14000bca3  lea     rcx, Mutex; Mutex
0x14000bcaa  call    cs:__imp_KeReleaseGuardedMutex
0x14000bcb1  nop     dword ptr [rax+rax+00h]
0x14000bcb6  nop
0x14000bcb7  add     rsp, 40h
0x14000bcbb  pop     rbp
0x14000bcbc  retn
```
