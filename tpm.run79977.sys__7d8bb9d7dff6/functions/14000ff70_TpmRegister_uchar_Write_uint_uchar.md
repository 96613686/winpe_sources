# TpmRegister<uchar>::Write(uint,uchar)

- ea: `0x14000ff70`
- end: `0x14000ffe5`
- name: `?Write@?$TpmRegister@E@@QEAAXIE@Z`
- size: `117`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1400183d0`
- `0x140018a30`
- `0x140024f40`
- `0x140024fd4`
- `0x140025090`
- `0x140025250`

## callees

- `0x14000ff70`
- `0x1400193c8`
- `0x14002f754`

## pseudocode

```c
__int64 __fastcall TpmRegister<unsigned char>::Write(unsigned int *a1, __int64 a2, char a3)
{
  __int64 v3; // rdx
  __int64 result; // rax

  v3 = *a1;
  if ( !LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
    return TpmWritePortByte(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters, v3);
  *(_BYTE *)(v3 + *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters) = a3;
  result = Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline();
  if ( (_DWORD)result )
  {
    result = LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) )
    {
      if ( WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey < LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) )
      {
        ++WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey;
      }
      else
      {
        result = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
        WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ff70  sub     rsp, 28h
0x14000ff74  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x14000ff7b  mov     edx, [rcx]
0x14000ff7d  mov     [rsp+28h+arg_8], 0
0x14000ff82  jz      short loc_14000FFD7
0x14000ff84  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000ff8b  mov     [rdx+rax], r8b
0x14000ff8f  call    Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline
0x14000ff94  test    eax, eax
0x14000ff96  jz      short loc_14000FFA2
0x14000ff98  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x14000ff9e  test    eax, eax
0x14000ffa0  jnz     short loc_14000FFA8
0x14000ffa2  add     rsp, 28h
0x14000ffa6  retn
0x14000ffa8  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue+10h
0x14000ffae  cmp     ecx, eax
0x14000ffb0  jb      short loc_14000FFCD
0x14000ffb2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000ffb9  movzx   ecx, byte ptr [rax+18h]
0x14000ffbd  mov     [rsp+28h+arg_8], cl
0x14000ffc1  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, 0
0x14000ffcb  jmp     short loc_14000FFA2
0x14000ffcd  inc     ecx
0x14000ffcf  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, ecx
0x14000ffd5  jmp     short loc_14000FFA2
0x14000ffd7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x14000ffde  call    TpmWritePortByte
0x14000ffe3  jmp     short loc_14000FFA2
```
