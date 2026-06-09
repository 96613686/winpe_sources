# WinHvpDeleteVpObject

- ea: `0x14002648c`
- end: `0x1400264d9`
- name: `WinHvpDeleteVpObject`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140007310`
- `0x14001d9e0`

## callees

- `0x140002454`
- `0x1400025e0`
- `0x1400042dc`
- `0x14001b1e4`
- `0x14002648c`

## pseudocode

```c
__int64 __fastcall WinHvpDeleteVpObject(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  result = WinHvpReferenceVp(a1, a2, &v3);
  if ( (int)result >= 0 )
  {
    if ( (int)WinHvpTerminateVpDispatchLoop(v3) >= 0 )
    {
      WinHvpRemoveVpFromPartition(v3);
      WinHvpDereferenceVp(v3);
    }
    return WinHvpDereferenceVp(v3);
  }
  return result;
}

```

## disassembly

```asm
0x14002648c  sub     rsp, 28h
0x140026490  lea     r8, [rsp+28h+arg_10]
0x140026495  mov     [rsp+28h+arg_10], 0
0x14002649e  call    WinHvpReferenceVp
0x1400264a3  test    eax, eax
0x1400264a5  js      short loc_1400264D3
0x1400264a7  mov     rcx, [rsp+28h+arg_10]
0x1400264ac  call    WinHvpTerminateVpDispatchLoop
0x1400264b1  test    eax, eax
0x1400264b3  js      short loc_1400264C9
0x1400264b5  mov     rcx, [rsp+28h+arg_10]
0x1400264ba  call    WinHvpRemoveVpFromPartition
0x1400264bf  mov     rcx, [rsp+28h+arg_10]
0x1400264c4  call    WinHvpDereferenceVp
0x1400264c9  mov     rcx, [rsp+28h+arg_10]
0x1400264ce  call    WinHvpDereferenceVp
0x1400264d3  add     rsp, 28h
0x1400264d7  retn
```
