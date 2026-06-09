# TpmRegister<ulong>::Write(uint,ulong)

- ea: `0x140018978`
- end: `0x140018a26`
- name: `?Write@?$TpmRegister@K@@QEAAXIK@Z`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140024fd4`
- `0x140025090`

## callees

- `0x140018978`
- `0x1400193c8`
- `0x14002f754`

## pseudocode

```c
__int64 __fastcall TpmRegister<unsigned long>::Write(unsigned int *a1, __int64 a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax
  __int64 v5; // rsi
  unsigned int i; // r11d
  int v7; // r11d

  v3 = *a1;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    *(_DWORD *)(v3 + *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters) = a3;
    result = Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline();
    if ( (_DWORD)result && LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) )
    {
      if ( WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey < LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) )
      {
        return ++WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey;
      }
      else
      {
        result = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
        WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey = 0;
      }
    }
  }
  else
  {
    v5 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters;
    for ( i = 0; i < 4; i = v7 + 1 )
      result = TpmWritePortByte(v5, i + (unsigned int)v3);
  }
  return result;
}

```

## disassembly

```asm
0x140018978  mov     [rsp+arg_0], rbx
0x14001897d  mov     [rsp+arg_10], rsi
0x140018982  push    rdi
0x140018983  sub     rsp, 20h
0x140018987  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x14001898e  mov     ebx, r8d
0x140018991  mov     edi, [rcx]
0x140018993  mov     [rsp+28h+arg_8], 0
0x14001899b  jz      short loc_1400189E8
0x14001899d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400189a4  mov     [rdi+rax], ebx
0x1400189a7  call    Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline
0x1400189ac  test    eax, eax
0x1400189ae  jz      short loc_140018A15
0x1400189b0  mov     ecx, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x1400189b6  test    ecx, ecx
0x1400189b8  jz      short loc_140018A15
0x1400189ba  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400189c0  cmp     eax, ecx
0x1400189c2  jb      short loc_1400189DE
0x1400189c4  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400189cb  mov     ecx, [rax+18h]
0x1400189ce  mov     [rsp+28h+arg_8], ecx
0x1400189d2  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, 0
0x1400189dc  jmp     short loc_140018A15
0x1400189de  inc     eax
0x1400189e0  mov     dword ptr cs:WPP_MAIN_CB.Queue+10h, eax
0x1400189e6  jmp     short loc_140018A15
0x1400189e8  mov     rsi, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400189ef  xor     r11d, r11d
0x1400189f2  lea     ecx, ds:0[r11*8]
0x1400189fa  mov     r8d, ebx
0x1400189fd  shr     r8d, cl
0x140018a00  lea     edx, [r11+rdi]
0x140018a04  mov     rcx, rsi
0x140018a07  call    TpmWritePortByte
0x140018a0c  inc     r11d
0x140018a0f  cmp     r11d, 4
0x140018a13  jb      short loc_1400189F2
0x140018a15  mov     rbx, [rsp+28h+arg_0]
0x140018a1a  mov     rsi, [rsp+28h+arg_10]
0x140018a1f  add     rsp, 20h
0x140018a23  pop     rdi
0x140018a24  retn
```
