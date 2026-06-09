# WinHvCreateEventLogBuffer

- ea: `0x140023820`
- end: `0x140023888`
- name: `WinHvCreateEventLogBuffer`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140004408`
- `0x140004564`
- `0x140005810`
- `0x140007530`
- `0x140023820`

## pseudocode

```c
__int64 __fastcall WinHvCreateEventLogBuffer(__int64 a1, __int64 a2, unsigned int a3)
{
  int v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  __int64 result; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = WinHvpInitializeFastHypercall(v8);
  v8[1] = v5;
  v8[0] = v4;
  WinHvpSetProximityDomain(&v9, v6);
  result = WinHvGetPartitionId(&v10);
  if ( (int)result >= 0 )
    return WinHvpFastAllocatingHypercall(v10, a3, 98, v8);
  return result;
}

```

## disassembly

```asm
0x140023820  push    rbx
0x140023822  sub     rsp, 30h
0x140023826  mov     eax, ecx
0x140023828  mov     [rsp+38h+var_10], 0
0x140023831  lea     rcx, [rsp+38h+var_18]
0x140023836  mov     [rsp+38h+arg_18], 0
0x14002383f  mov     ebx, r8d
0x140023842  call    WinHvpInitializeFastHypercall
0x140023847  mov     [rsp+38h+var_14], edx
0x14002384b  lea     rcx, [rsp+38h+var_10]
0x140023850  mov     edx, r8d
0x140023853  mov     [rsp+38h+var_18], eax
0x140023857  call    WinHvpSetProximityDomain
0x14002385c  lea     rcx, [rsp+38h+arg_18]
0x140023861  call    WinHvGetPartitionId
0x140023866  test    eax, eax
0x140023868  js      short loc_140023881
0x14002386a  mov     rcx, [rsp+38h+arg_18]
0x14002386f  lea     r9, [rsp+38h+var_18]
0x140023874  mov     r8d, 62h ; 'b'
0x14002387a  mov     edx, ebx
0x14002387c  call    WinHvpFastAllocatingHypercall
0x140023881  add     rsp, 30h
0x140023885  pop     rbx
0x140023886  retn
```
