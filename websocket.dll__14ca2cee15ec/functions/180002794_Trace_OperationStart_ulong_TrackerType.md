# Trace::OperationStart(ulong,TrackerType)

- ea: `0x180002794`
- end: `0x180002817`
- name: `?OperationStart@Trace@@SAXKW4TrackerType@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009cf4`
- `0x18000a00c`
- `0x18000a13c`

## callees

- `0x180001670`
- `0x180002794`
- `0x180002a00`

## pseudocode

```c
ULONG __fastcall Trace::OperationStart(__int64 a1, int a2)
{
  ULONG result; // eax
  int v3; // [rsp+30h] [rbp-58h] BYREF
  int v4; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-48h] BYREF
  int *v6; // [rsp+50h] [rbp-38h]
  __int64 v7; // [rsp+58h] [rbp-30h]
  int *v8; // [rsp+60h] [rbp-28h]
  __int64 v9; // [rsp+68h] [rbp-20h]

  if ( Trace::s_fInitialized )
  {
    if ( (Microsoft_Windows_Websocket_Protocol_ComponentEnableBits & 2) != 0 )
    {
      v4 = a2;
      v6 = &v3;
      v3 = a1;
      v8 = &v4;
      v7 = 4;
      v9 = 4;
      return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WSPC_OPERATION_START, 0, 3u, &v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002794  mov     r11, rsp
0x180002797  sub     rsp, 88h
0x18000279e  mov     rax, cs:__security_cookie
0x1800027a5  xor     rax, rsp
0x1800027a8  mov     [rsp+88h+var_18], rax
0x1800027ad  xor     r8d, r8d
0x1800027b0  cmp     cs:?s_fInitialized@Trace@@0HA, r8d; int Trace::s_fInitialized
0x1800027b7  jz      short loc_180002802
0x1800027b9  test    cs:Microsoft_Windows_Websocket_Protocol_ComponentEnableBits, 2
0x1800027c0  jz      short loc_180002802
0x1800027c2  lea     rax, [r11-58h]
0x1800027c6  mov     [rsp+88h+var_50], edx
0x1800027ca  mov     [r11-38h], rax
0x1800027ce  lea     r9d, [r8+3]
0x1800027d2  lea     rax, [r11-50h]
0x1800027d6  mov     [rsp+88h+var_58], ecx
0x1800027da  mov     [r11-28h], rax
0x1800027de  lea     rdx, WSPC_OPERATION_START
0x1800027e5  lea     rax, [r11-48h]
0x1800027e9  mov     qword ptr [r11-30h], 4
0x1800027f1  mov     [r11-68h], rax
0x1800027f5  mov     qword ptr [r11-20h], 4
0x1800027fd  call    McGenEventWrite_EventWriteTransfer
0x180002802  mov     rcx, [rsp+88h+var_18]
0x180002807  xor     rcx, rsp; StackCookie
0x18000280a  call    __security_check_cookie
0x18000280f  add     rsp, 88h
0x180002816  retn
```
