# PortConnectHandler_0

- ea: `0x14000b160`
- end: `0x14000b279`
- name: `PortConnectHandler_0`
- size: `281`
- prototype: `NTSTATUS __stdcall(PFLT_PORT ClientPort, PVOID ServerPortCookie, PVOID ConnectionContext, ULONG SizeOfContext, PVOID *ConnectionPortCookie)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x140001298`
- `0x14000a84c`
- `0x14000a994`
- `0x14000aec4`
- `0x14000b160`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b19d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000b19d`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b239`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000b239`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b1d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000b1d9`

## string_xrefs

- `0x14000b21a`: `UevFilter.PortConnectHandler: Session ID %d already exists in table.\n`

## pseudocode

```c
__int64 __fastcall PortConnectHandler_0(
        PFLT_PORT ClientPort,
        PVOID ServerPortCookie,
        PVOID ConnectionContext,
        ULONG SizeOfContext,
        PVOID *ConnectionPortCookie)
{
  PVOID *v6; // rdi
  HANDLE CurrentProcessId; // rax
  int SessionIdFromProcessId; // ebx
  __int64 v9; // rcx
  unsigned __int64 v10; // rsi
  __int64 v11; // rcx
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF

  DbgTrace(2, "UevFilter.PortConnectHandler: Entry\n");
  if ( ClientPort && (v6 = ConnectionPortCookie) != 0 )
  {
    v13 = 0;
    CurrentProcessId = PsGetCurrentProcessId();
    SessionIdFromProcessId = GetSessionIdFromProcessId(CurrentProcessId, &v13);
    if ( SessionIdFromProcessId >= 0 )
    {
      KeAcquireGuardedMutex(&Mutex);
      if ( P )
      {
        v10 = v13;
        if ( (unsigned __int8)FindKeyInFilterHashTable(v9, v13, 0) )
        {
          DbgTraceFrmtErr("UevFilter.PortConnectHandler: Session ID %d already exists in table.\n");
          SessionIdFromProcessId = -1073741752;
        }
        else
        {
          SessionIdFromProcessId = AddFilterHashTableEntry(v11, (unsigned int)v10, ClientPort);
          if ( SessionIdFromProcessId >= 0 )
            *v6 = (PVOID)v10;
        }
      }
      else
      {
        SessionIdFromProcessId = -1073741769;
      }
      KeReleaseGuardedMutex(&Mutex);
    }
    else
    {
      DbgTraceFrmtErr("UevFilter.PortConnectHandler: Failed to get session ID. Error = 0x%0X.\n");
    }
  }
  else
  {
    DbgTraceErr("UevFilter.PortConnectHandler: Invalid parameter.\n");
    SessionIdFromProcessId = -1073741811;
  }
  DbgTraceFrmt(2, "UevFilter.PortConnectHandler: Exit. Error = 0%0X\n", SessionIdFromProcessId);
  return (unsigned int)SessionIdFromProcessId;
}

```

## disassembly

```asm
0x14000b160  push    rbx
0x14000b162  push    rsi
0x14000b163  push    rdi
0x14000b164  push    r14
0x14000b166  sub     rsp, 28h
0x14000b16a  mov     r14, rcx
0x14000b16d  lea     rdx, aUevfilterPortc_2; "UevFilter.PortConnectHandler: Entry\n"
0x14000b174  mov     ecx, 2
0x14000b179  call    DbgTrace
0x14000b17e  test    r14, r14
0x14000b181  jz      loc_14000B247
0x14000b187  mov     rdi, [rsp+48h+ConnectionPortCookie]
0x14000b18c  test    rdi, rdi
0x14000b18f  jz      loc_14000B247
0x14000b195  mov     [rsp+48h+arg_0], 0
0x14000b19d  call    cs:__imp_PsGetCurrentProcessId
0x14000b1a4  nop     dword ptr [rax+rax+00h]
0x14000b1a9  mov     rcx, rax
0x14000b1ac  lea     rdx, [rsp+48h+arg_0]
0x14000b1b1  call    GetSessionIdFromProcessId
0x14000b1b6  mov     ebx, eax
0x14000b1b8  test    eax, eax
0x14000b1ba  jns     short loc_14000B1CA
0x14000b1bc  mov     edx, eax
0x14000b1be  lea     rcx, aUevfilterPortc_3; "UevFilter.PortConnectHandler: Failed to"...
0x14000b1c5  call    DbgTraceFrmtErr
0x14000b1ca  test    ebx, ebx
0x14000b1cc  js      loc_14000B258
0x14000b1d2  lea     rcx, Mutex; Mutex
0x14000b1d9  call    cs:__imp_KeAcquireGuardedMutex
0x14000b1e0  nop     dword ptr [rax+rax+00h]
0x14000b1e5  cmp     cs:P, 0
0x14000b1ed  jz      short loc_14000B22D
0x14000b1ef  mov     esi, [rsp+48h+arg_0]
0x14000b1f3  xor     r8d, r8d
0x14000b1f6  mov     edx, esi
0x14000b1f8  call    FindKeyInFilterHashTable
0x14000b1fd  test    al, al
0x14000b1ff  jnz     short loc_14000B216
0x14000b201  mov     r8, r14
0x14000b204  mov     edx, esi
0x14000b206  call    AddFilterHashTableEntry
0x14000b20b  mov     ebx, eax
0x14000b20d  test    eax, eax
0x14000b20f  js      short loc_14000B232
0x14000b211  mov     [rdi], rsi
0x14000b214  jmp     short loc_14000B232
0x14000b216  mov     edx, [rsp+48h+arg_0]
0x14000b21a  lea     rcx, aUevfilterPortc_6; "UevFilter.PortConnectHandler: Session I"...
0x14000b221  call    DbgTraceFrmtErr
0x14000b226  mov     ebx, 0C0000048h
0x14000b22b  jmp     short loc_14000B232
0x14000b22d  mov     ebx, 0C0000037h
0x14000b232  lea     rcx, Mutex; Mutex
0x14000b239  call    cs:__imp_KeReleaseGuardedMutex
0x14000b240  nop     dword ptr [rax+rax+00h]
0x14000b245  jmp     short loc_14000B258
0x14000b247  lea     rcx, aUevfilterPortc_1; "UevFilter.PortConnectHandler: Invalid p"...
0x14000b24e  call    DbgTraceErr
0x14000b253  mov     ebx, 0C000000Dh
0x14000b258  mov     r8d, ebx
0x14000b25b  lea     rdx, aUevfilterPortc; "UevFilter.PortConnectHandler: Exit. Err"...
0x14000b262  mov     ecx, 2
0x14000b267  call    DbgTraceFrmt
0x14000b26c  mov     eax, ebx
0x14000b26e  add     rsp, 28h
0x14000b272  pop     r14
0x14000b274  pop     rdi
0x14000b275  pop     rsi
0x14000b276  pop     rbx
0x14000b277  retn
0x14000bc40  push    rbp
0x14000bc42  sub     rsp, 20h
0x14000bc46  mov     rbp, rdx
0x14000bc49  lea     rcx, Mutex; Mutex
0x14000bc50  call    cs:__imp_KeReleaseGuardedMutex
0x14000bc57  nop     dword ptr [rax+rax+00h]
0x14000bc5c  nop
0x14000bc5d  add     rsp, 20h
0x14000bc61  pop     rbp
0x14000bc62  retn
```
