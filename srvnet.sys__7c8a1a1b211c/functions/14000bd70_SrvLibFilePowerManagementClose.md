# SrvLibFilePowerManagementClose

- ea: `0x14000bd70`
- end: `0x14000be15`
- name: `SrvLibFilePowerManagementClose`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000bd70`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14000bdf9`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000bdf9`
- `ntoskrnl!PoClearPowerRequest` at `0x14000bdd9`
- `ntoskrnl!PoClearPowerRequest` at `0x14000bdd9`

## pseudocode

```c
NTSTATUS __fastcall SrvLibFilePowerManagementClose(volatile signed __int32 *a1)
{
  NTSTATUS result; // eax
  _LARGE_INTEGER Interval; // [rsp+38h] [rbp+10h] BYREF

  result = _InterlockedCompareExchange(a1, 0, 3);
  if ( result )
  {
    for ( result = _InterlockedCompareExchange(a1, 2, 3); result == 1; result = _InterlockedCompareExchange(a1, 2, 3) )
    {
      Interval.QuadPart = -200000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    if ( result == 2 && SrvPowerOpenFileRequest )
    {
      result = _InterlockedExchangeAdd(&SrvPowerOpenFileCount, 0xFFFFFFFF);
      if ( result == 1 )
        return PoClearPowerRequest(SrvPowerOpenFileRequest, PowerRequestSystemRequired);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000bd70  push    rbx
0x14000bd72  sub     rsp, 20h
0x14000bd76  mov     rbx, rcx
0x14000bd79  mov     eax, 3
0x14000bd7e  xor     ecx, ecx
0x14000bd80  lock cmpxchg [rbx], ecx
0x14000bd84  test    eax, eax
0x14000bd86  jz      short loc_14000BDC6
0x14000bd88  mov     [rsp+28h+arg_0], rdi
0x14000bd8d  mov     eax, 3
0x14000bd92  mov     edi, 2
0x14000bd97  lock cmpxchg [rbx], edi
0x14000bd9b  cmp     eax, 1
0x14000bd9e  jz      short loc_14000BDE7
0x14000bda0  mov     rdi, [rsp+28h+arg_0]
0x14000bda5  cmp     eax, 2
0x14000bda8  jnz     short loc_14000BDC6
0x14000bdaa  cmp     cs:SrvPowerOpenFileRequest, 0
0x14000bdb2  jz      short loc_14000BDC6
0x14000bdb4  mov     eax, 0FFFFFFFFh
0x14000bdb9  lock xadd cs:SrvPowerOpenFileCount, eax
0x14000bdc1  cmp     eax, 1
0x14000bdc4  jz      short loc_14000BDCD
0x14000bdc6  add     rsp, 20h
0x14000bdca  pop     rbx
0x14000bdcb  retn
0x14000bdcd  mov     rcx, cs:SrvPowerOpenFileRequest; PowerRequest
0x14000bdd4  mov     edx, 1; Type
0x14000bdd9  call    cs:__imp_PoClearPowerRequest
0x14000bde0  nop     dword ptr [rax+rax+00h]
0x14000bde5  jmp     short loc_14000BDC6
0x14000bde7  lea     r8, [rsp+28h+Interval]; Interval
0x14000bdec  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFCF2C0h
0x14000bdf5  xor     edx, edx; Alertable
0x14000bdf7  xor     ecx, ecx; WaitMode
0x14000bdf9  call    cs:__imp_KeDelayExecutionThread
0x14000be00  nop     dword ptr [rax+rax+00h]
0x14000be05  mov     eax, 3
0x14000be0a  lock cmpxchg [rbx], edi
0x14000be0e  cmp     eax, 1
0x14000be11  jz      short loc_14000BDE7
0x14000be13  jmp     short loc_14000BDA0
```
