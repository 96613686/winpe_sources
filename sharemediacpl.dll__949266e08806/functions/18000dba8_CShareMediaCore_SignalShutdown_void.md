# CShareMediaCore::SignalShutdown(void)

- ea: `0x18000dba8`
- end: `0x18000dc41`
- name: `?SignalShutdown@CShareMediaCore@@QEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bd4c`
- `0x18000f1cc`
- `0x18000fd88`
- `0x1800137e0`

## callees

- `0x180003860`
- `0x180003888`
- `0x180009cac`
- `0x180009d40`
- `0x18000dba8`
- `0x18000dc48`
- `0x18000de3c`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::SignalShutdown(CShareWithList **this)
{
  CShareWithList *v2; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Cu, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  CShareMediaCore::EndDeviceEnumeration((CShareMediaCore *)this);
  CShareMediaCore::EndNetworkStateChangeThread((HANDLE *)this);
  v2 = this[7];
  if ( v2 )
  {
    CShareWithList::SignalShutdown(v2);
    CShareWithList::StopDeviceListening(this[7]);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Du, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000dba8  mov     [rsp+arg_0], rbx
0x18000dbad  push    rdi
0x18000dbae  sub     rsp, 20h
0x18000dbb2  mov     rbx, rcx
0x18000dbb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbbc  lea     rdi, WPP_GLOBAL_Control
0x18000dbc3  cmp     rcx, rdi
0x18000dbc6  jz      short loc_18000DBE3
0x18000dbc8  test    byte ptr [rcx+1Ch], 20h
0x18000dbcc  jz      short loc_18000DBE3
0x18000dbce  mov     rcx, [rcx+10h]
0x18000dbd2  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000dbd9  mov     edx, 1Ch
0x18000dbde  call    WPP_SF_
0x18000dbe3  mov     rcx, rbx; this
0x18000dbe6  call    ?EndDeviceEnumeration@CShareMediaCore@@QEAAJXZ; CShareMediaCore::EndDeviceEnumeration(void)
0x18000dbeb  mov     rcx, rbx; this
0x18000dbee  call    ?EndNetworkStateChangeThread@CShareMediaCore@@QEAAJXZ; CShareMediaCore::EndNetworkStateChangeThread(void)
0x18000dbf3  mov     rcx, [rbx+38h]; this
0x18000dbf7  test    rcx, rcx
0x18000dbfa  jz      short loc_18000DC0A
0x18000dbfc  call    ?SignalShutdown@CShareWithList@@QEAAJXZ; CShareWithList::SignalShutdown(void)
0x18000dc01  mov     rcx, [rbx+38h]; this
0x18000dc05  call    ?StopDeviceListening@CShareWithList@@QEAAJXZ; CShareWithList::StopDeviceListening(void)
0x18000dc0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc11  cmp     rcx, rdi
0x18000dc14  jz      short loc_18000DC34
0x18000dc16  test    byte ptr [rcx+1Ch], 20h
0x18000dc1a  jz      short loc_18000DC34
0x18000dc1c  mov     rcx, [rcx+10h]
0x18000dc20  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000dc27  mov     edx, 1Dh
0x18000dc2c  xor     r9d, r9d
0x18000dc2f  call    WPP_SF_d
0x18000dc34  mov     rbx, [rsp+28h+arg_0]
0x18000dc39  xor     eax, eax
0x18000dc3b  add     rsp, 20h
0x18000dc3f  pop     rdi
0x18000dc40  retn
```
