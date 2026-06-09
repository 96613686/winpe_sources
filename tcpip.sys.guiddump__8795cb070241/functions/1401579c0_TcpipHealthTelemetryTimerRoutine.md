# TcpipHealthTelemetryTimerRoutine

- ea: `0x1401579c0`
- end: `0x140157c7f`
- name: `TcpipHealthTelemetryTimerRoutine`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x140108a60`
- `0x140131ee0`
- `0x1401579c0`
- `0x14015d64c`
- `0x1401683c4`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140157a96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157bd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157a96`
- `ntoskrnl!KeReleaseSpinLock` at `0x140157bd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140157a0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140157a0e`
- `NETIO!NetioOpenKey` at `0x140157bf9`
- `NETIO!NetioOpenKey` at `0x140157bf9`
- `NETIO!NetioTimerWorkItemStart` at `0x140157c51`
- `NETIO!NetioTimerWorkItemStart` at `0x140157c51`
- `NETIO!NetioCloseKey` at `0x140157c39`
- `NETIO!NetioCloseKey` at `0x140157c39`
- `NETIO!NetioWriteKey` at `0x140157c28`
- `NETIO!NetioWriteKey` at `0x140157c28`

## string_xrefs

- `0x140157bf2`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 TcpipHealthTelemetryTimerRoutine()
{
  struct _LIST_ENTRY *v0; // rbx
  KIRQL v1; // dl
  signed __int64 v2; // xmm2_8
  __int64 v4; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v5; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v6; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v7; // [rsp+50h] [rbp-B0h] BYREF
  __int64 AverageInSegSize; // [rsp+60h] [rbp-A0h] BYREF
  __int64 AverageInNetBufferSize; // [rsp+68h] [rbp-98h] BYREF
  __int128 v10; // [rsp+70h] [rbp-90h] BYREF
  __int128 v11; // [rsp+80h] [rbp-80h]
  __int128 v12; // [rsp+90h] [rbp-70h]
  _BYTE v13[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v14; // [rsp+C0h] [rbp-40h]
  __int64 v15; // [rsp+C8h] [rbp-38h]
  __int128 *v16; // [rsp+D0h] [rbp-30h]
  __int64 v17; // [rsp+D8h] [rbp-28h]
  char *v18; // [rsp+E0h] [rbp-20h]
  __int64 v19; // [rsp+E8h] [rbp-18h]
  __int128 *v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]
  char *v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int64 *p_AverageInSegSize; // [rsp+110h] [rbp+10h]
  __int64 v25; // [rsp+118h] [rbp+18h]
  __int64 *p_AverageInNetBufferSize; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]

  v0 = (struct _LIST_ENTRY *)MEMORY[0xFFFFF78000000014];
  v1 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DpcListEntry);
  v10 = *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Type;
  v2 = _mm_srli_si128(*(__m128i *)&WPP_MAIN_CB.DeviceQueue.Type, 8).m128i_u64[0];
  v11 = *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink;
  v12 = *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Busy;
  if ( (__int64)v0 <= v2 || (unsigned __int64)v0 - v2 < 0xC92A69C000LL )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DpcListEntry, v1);
  }
  else
  {
    *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
    *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 1;
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink = v0;
    *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink = 0;
    *(_OWORD *)&WPP_MAIN_CB.DeviceQueue.Busy = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DpcListEntry, v1);
    if ( (unsigned int)dword_1402241F8 > 5 && tlgKeywordOn((__int64)&dword_1402241F8, 0x400000000000LL) )
    {
      v5 = 2048;
      v14 = &v5;
      v6 = v11;
      v16 = &v6;
      v18 = (char *)&v6 + 8;
      v7 = v12;
      v20 = &v7;
      v22 = (char *)&v7 + 8;
      v15 = 8;
      v17 = 8;
      v19 = 8;
      v21 = 8;
      v23 = 8;
      AverageInSegSize = TcpGetAverageInSegSize();
      p_AverageInSegSize = &AverageInSegSize;
      v25 = 8;
      AverageInNetBufferSize = UdpGetAverageInNetBufferSize();
      v27 = 8;
      p_AverageInNetBufferSize = &AverageInNetBufferSize;
      tlgWriteTransfer_EtwWriteTransfer(&dword_1402241F8, byte_1401F58E9, 0, 0, 9, v13, v4);
    }
    *(_QWORD *)&v10 = 1;
    *((_QWORD *)&v10 + 1) = v0;
    v11 = 0;
    v12 = 0;
  }
  v4 = 0;
  if ( (int)NetioOpenKey(
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters",
              0x40000000,
              &v4) >= 0 )
  {
    NetioWriteKey(v4, L"Health", 3, &v10, 48);
    NetioCloseKey(&v4);
  }
  return NetioTimerWorkItemStart(qword_140228410, 3600000);
}

```

## disassembly

```asm
0x1401579c0  mov     [rsp-8+arg_0], rbx
0x1401579c5  mov     [rsp-8+arg_8], rdi
0x1401579ca  push    rbp
0x1401579cb  lea     rbp, [rsp-40h]
0x1401579d0  sub     rsp, 140h
0x1401579d7  mov     rax, cs:__security_cookie
0x1401579de  xor     rax, rsp
0x1401579e1  mov     [rbp+40h+var_10], rax
0x1401579e5  xorps   xmm0, xmm0
0x1401579e8  lea     rdi, WPP_MAIN_CB.Dpc.DpcListEntry
0x1401579ef  movups  [rbp+40h+var_C0], xmm0
0x1401579f3  mov     rbx, 0FFFFF78000000014h
0x1401579fd  xor     eax, eax
0x1401579ff  movups  [rsp+140h+var_D0], xmm0
0x140157a04  mov     rcx, rdi; SpinLock
0x140157a07  movups  [rbp+40h+var_C0+0Ch], xmm0
0x140157a0b  mov     rbx, [rbx]
0x140157a0e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140157a15  nop     dword ptr [rax+rax+00h]
0x140157a1a  movups  xmm2, xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140157a21  mov     dl, al; NewIrql
0x140157a23  movups  xmm0, xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140157a2a  movups  xmm1, xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x140157a31  movups  [rsp+140h+var_D0], xmm2
0x140157a36  psrldq  xmm2, 8
0x140157a3b  movq    r8, xmm2
0x140157a40  movups  [rbp+40h+var_C0], xmm0
0x140157a44  movups  [rbp+40h+var_B0], xmm1
0x140157a48  cmp     rbx, r8
0x140157a4b  jle     loc_140157BD0
0x140157a51  mov     rax, rbx
0x140157a54  sub     rax, r8
0x140157a57  mov     r8, 0C92A69C000h
0x140157a61  cmp     rax, r8
0x140157a64  jb      loc_140157BD0
0x140157a6a  xorps   xmm0, xmm0
0x140157a6d  mov     rcx, rdi; SpinLock
0x140157a70  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, xmm0
0x140157a77  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 1
0x140157a81  mov     cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, rbx
0x140157a88  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, xmm0
0x140157a8f  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, xmm0
0x140157a96  call    cs:__imp_KeReleaseSpinLock
0x140157a9d  nop     dword ptr [rax+rax+00h]
0x140157aa2  mov     eax, cs:dword_1402241F8
0x140157aa8  cmp     eax, 5
0x140157aab  jbe     loc_140157BB1
0x140157ab1  mov     rdx, 400000000000h
0x140157abb  lea     rcx, dword_1402241F8
0x140157ac2  call    _tlgKeywordOn
0x140157ac7  test    al, al
0x140157ac9  jz      loc_140157BB1
0x140157acf  lea     rax, [rsp+140h+var_108]
0x140157ad4  mov     [rsp+140h+var_108], 800h
0x140157add  mov     [rbp+40h+var_80], rax
0x140157ae1  mov     rax, qword ptr [rbp+40h+var_C0]
0x140157ae5  mov     qword ptr [rsp+140h+var_100], rax
0x140157aea  lea     rax, [rsp+140h+var_100]
0x140157aef  mov     [rbp+40h+var_70], rax
0x140157af3  mov     rax, qword ptr [rbp+40h+var_C0+8]
0x140157af7  mov     qword ptr [rsp+140h+var_100+8], rax
0x140157afc  lea     rax, [rsp+140h+var_100+8]
0x140157b01  mov     [rbp+40h+var_60], rax
0x140157b05  mov     rax, qword ptr [rbp+40h+var_B0]
0x140157b09  mov     qword ptr [rsp+140h+var_F0], rax
0x140157b0e  lea     rax, [rsp+140h+var_F0]
0x140157b13  mov     [rbp+40h+var_50], rax
0x140157b17  mov     rax, qword ptr [rbp+40h+var_B0+8]
0x140157b1b  mov     qword ptr [rsp+140h+var_F0+8], rax
0x140157b20  lea     rax, [rsp+140h+var_F0+8]
0x140157b25  mov     [rbp+40h+var_40], rax
0x140157b29  mov     [rbp+40h+var_78], 8
0x140157b31  mov     [rbp+40h+var_68], 8
0x140157b39  mov     [rbp+40h+var_58], 8
0x140157b41  mov     [rbp+40h+var_48], 8
0x140157b49  mov     [rbp+40h+var_38], 8
0x140157b51  call    TcpGetAverageInSegSize
0x140157b56  mov     [rsp+140h+var_E0], rax
0x140157b5b  lea     rax, [rsp+140h+var_E0]
0x140157b60  mov     [rbp+40h+var_30], rax
0x140157b64  mov     [rbp+40h+var_28], 8
0x140157b6c  call    UdpGetAverageInNetBufferSize
0x140157b71  mov     [rsp+140h+var_D8], rax
0x140157b76  lea     rdx, byte_1401F58E9
0x140157b7d  lea     rax, [rsp+140h+var_D8]
0x140157b82  mov     [rbp+40h+var_18], 8
0x140157b8a  mov     [rbp+40h+var_20], rax
0x140157b8e  lea     rcx, dword_1402241F8
0x140157b95  lea     rax, [rbp+40h+var_A0]
0x140157b99  xor     r9d, r9d
0x140157b9c  mov     [rsp+140h+var_118], rax
0x140157ba1  xor     r8d, r8d
0x140157ba4  mov     [rsp+140h+var_120], 9
0x140157bac  call    _tlgWriteTransfer_EtwWriteTransfer
0x140157bb1  xorps   xmm0, xmm0
0x140157bb4  movups  [rsp+140h+var_D0], xmm0
0x140157bb9  mov     dword ptr [rsp+140h+var_D0], 1
0x140157bc1  mov     qword ptr [rsp+140h+var_D0+8], rbx
0x140157bc6  movups  [rbp+40h+var_C0], xmm0
0x140157bca  movups  [rbp+40h+var_B0], xmm0
0x140157bce  jmp     short loc_140157BDF
0x140157bd0  mov     rcx, rdi; SpinLock
0x140157bd3  call    cs:__imp_KeReleaseSpinLock
0x140157bda  nop     dword ptr [rax+rax+00h]
0x140157bdf  lea     r8, [rsp+140h+var_110]
0x140157be4  mov     [rsp+140h+var_110], 0
0x140157bed  mov     edx, 40000000h
0x140157bf2  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140157bf9  call    cs:__imp_NetioOpenKey
0x140157c00  nop     dword ptr [rax+rax+00h]
0x140157c05  test    eax, eax
0x140157c07  js      short loc_140157C45
0x140157c09  mov     rcx, [rsp+140h+var_110]
0x140157c0e  lea     r9, [rsp+140h+var_D0]
0x140157c13  mov     r8d, 3
0x140157c19  mov     [rsp+140h+var_120], 30h ; '0'
0x140157c21  lea     rdx, aHealth; "Health"
0x140157c28  call    cs:__imp_NetioWriteKey
0x140157c2f  nop     dword ptr [rax+rax+00h]
0x140157c34  lea     rcx, [rsp+140h+var_110]
0x140157c39  call    cs:__imp_NetioCloseKey
0x140157c40  nop     dword ptr [rax+rax+00h]
0x140157c45  mov     edx, 36EE80h
0x140157c4a  lea     rcx, qword_140228410
0x140157c51  call    cs:__imp_NetioTimerWorkItemStart
0x140157c58  nop     dword ptr [rax+rax+00h]
0x140157c5d  mov     rcx, [rbp+40h+var_10]
0x140157c61  xor     rcx, rsp; StackCookie
0x140157c64  call    __security_check_cookie
0x140157c69  lea     r11, [rsp+140h+var_s0]
0x140157c71  mov     rbx, [r11+10h]
0x140157c75  mov     rdi, [r11+18h]
0x140157c79  mov     rsp, r11
0x140157c7c  pop     rbp
0x140157c7d  retn
```
