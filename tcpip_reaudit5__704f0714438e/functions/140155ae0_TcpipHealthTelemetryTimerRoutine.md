# TcpipHealthTelemetryTimerRoutine

- ea: `0x140155ae0`
- end: `0x140155d9f`
- name: `TcpipHealthTelemetryTimerRoutine`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400fd6e4`
- `0x140128320`
- `0x140155ae0`
- `0x14015b8bc`
- `0x140166744`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140155bb6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155cf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155bb6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155cf3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140155b2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140155b2e`
- `NETIO!NetioOpenKey` at `0x140155d19`
- `NETIO!NetioOpenKey` at `0x140155d19`
- `NETIO!NetioTimerWorkItemStart` at `0x140155d71`
- `NETIO!NetioTimerWorkItemStart` at `0x140155d71`
- `NETIO!NetioCloseKey` at `0x140155d59`
- `NETIO!NetioCloseKey` at `0x140155d59`
- `NETIO!NetioWriteKey` at `0x140155d48`
- `NETIO!NetioWriteKey` at `0x140155d48`

## string_xrefs

- `0x140155d12`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 TcpipHealthTelemetryTimerRoutine()
{
  signed __int64 v0; // rbx
  KIRQL v1; // dl
  signed __int64 v2; // xmm2_8
  __int64 v4; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v5; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v6; // [rsp+40h] [rbp-C0h] BYREF
  LIST_ENTRY v7; // [rsp+50h] [rbp-B0h] BYREF
  __int64 AverageInSegSize; // [rsp+60h] [rbp-A0h] BYREF
  __int64 AverageInNetBufferSize; // [rsp+68h] [rbp-98h] BYREF
  __int128 v10; // [rsp+70h] [rbp-90h] BYREF
  __int128 v11; // [rsp+80h] [rbp-80h]
  LIST_ENTRY WaitListHead; // [rsp+90h] [rbp-70h]
  char v13[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v14; // [rsp+C0h] [rbp-40h]
  __int64 v15; // [rsp+C8h] [rbp-38h]
  __int128 *v16; // [rsp+D0h] [rbp-30h]
  __int64 v17; // [rsp+D8h] [rbp-28h]
  char *v18; // [rsp+E0h] [rbp-20h]
  __int64 v19; // [rsp+E8h] [rbp-18h]
  LIST_ENTRY *v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]
  struct _LIST_ENTRY **p_Blink; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int64 *p_AverageInSegSize; // [rsp+110h] [rbp+10h]
  __int64 v25; // [rsp+118h] [rbp+18h]
  __int64 *p_AverageInNetBufferSize; // [rsp+120h] [rbp+20h]
  __int64 v27; // [rsp+128h] [rbp+28h]

  v0 = MEMORY[0xFFFFF78000000014];
  v1 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.SectorSize);
  v10 = *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcData;
  v2 = _mm_srli_si128(*(__m128i *)&WPP_MAIN_CB.Dpc.DpcData, 8).m128i_u64[0];
  v11 = *(_OWORD *)&WPP_MAIN_CB.SecurityDescriptor;
  WaitListHead = WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  if ( v0 <= v2 || (unsigned __int64)(v0 - v2) < 0xC92A69C000LL )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.SectorSize, v1);
  }
  else
  {
    *(_OWORD *)&WPP_MAIN_CB.Dpc.DpcData = 0;
    LODWORD(WPP_MAIN_CB.Dpc.DpcData) = 1;
    *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = v0;
    *(_OWORD *)&WPP_MAIN_CB.SecurityDescriptor = 0;
    WPP_MAIN_CB.DeviceLock.Header.WaitListHead = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.SectorSize, v1);
    if ( (unsigned int)dword_1402201F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1402201F8, 0x400000000000LL) )
    {
      v5 = 2048;
      v14 = &v5;
      v6 = v11;
      v16 = &v6;
      v18 = (char *)&v6 + 8;
      v7 = WaitListHead;
      v20 = &v7;
      p_Blink = &v7.Blink;
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
      tlgWriteTransfer_EtwWriteTransfer(&dword_1402201F8, byte_1401F1D69, 0, 0, 9, v13, v4);
    }
    *(_QWORD *)&v10 = 1;
    *((_QWORD *)&v10 + 1) = v0;
    v11 = 0;
    WaitListHead = 0;
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
  return NetioTimerWorkItemStart(qword_140224390, 3600000);
}

```

## disassembly

```asm
0x140155ae0  mov     [rsp-8+arg_0], rbx
0x140155ae5  mov     [rsp-8+arg_8], rdi
0x140155aea  push    rbp
0x140155aeb  lea     rbp, [rsp-40h]
0x140155af0  sub     rsp, 140h
0x140155af7  mov     rax, cs:__security_cookie
0x140155afe  xor     rax, rsp
0x140155b01  mov     [rbp+40h+var_10], rax
0x140155b05  xorps   xmm0, xmm0
0x140155b08  lea     rdi, WPP_MAIN_CB.SectorSize
0x140155b0f  movups  [rbp+40h+var_C0], xmm0
0x140155b13  mov     rbx, 0FFFFF78000000014h
0x140155b1d  xor     eax, eax
0x140155b1f  movups  [rsp+140h+var_D0], xmm0
0x140155b24  mov     rcx, rdi; SpinLock
0x140155b27  movups  [rbp+40h+var_C0+0Ch], xmm0
0x140155b2b  mov     rbx, [rbx]
0x140155b2e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140155b35  nop     dword ptr [rax+rax+00h]
0x140155b3a  movups  xmm2, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData
0x140155b41  mov     dl, al; NewIrql
0x140155b43  movups  xmm0, xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x140155b4a  movups  xmm1, xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140155b51  movups  [rsp+140h+var_D0], xmm2
0x140155b56  psrldq  xmm2, 8
0x140155b5b  movq    r8, xmm2
0x140155b60  movups  [rbp+40h+var_C0], xmm0
0x140155b64  movups  [rbp+40h+var_B0], xmm1
0x140155b68  cmp     rbx, r8
0x140155b6b  jle     loc_140155CF0
0x140155b71  mov     rax, rbx
0x140155b74  sub     rax, r8
0x140155b77  mov     r8, 0C92A69C000h
0x140155b81  cmp     rax, r8
0x140155b84  jb      loc_140155CF0
0x140155b8a  xorps   xmm0, xmm0
0x140155b8d  mov     rcx, rdi; SpinLock
0x140155b90  movups  xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData, xmm0
0x140155b97  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, 1
0x140155ba1  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rbx
0x140155ba8  movups  xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor, xmm0
0x140155baf  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, xmm0
0x140155bb6  call    cs:__imp_KeReleaseSpinLock
0x140155bbd  nop     dword ptr [rax+rax+00h]
0x140155bc2  mov     eax, cs:dword_1402201F8
0x140155bc8  cmp     eax, 5
0x140155bcb  jbe     loc_140155CD1
0x140155bd1  mov     rdx, 400000000000h
0x140155bdb  lea     rcx, dword_1402201F8
0x140155be2  call    _tlgKeywordOn
0x140155be7  test    al, al
0x140155be9  jz      loc_140155CD1
0x140155bef  lea     rax, [rsp+140h+var_108]
0x140155bf4  mov     [rsp+140h+var_108], 800h
0x140155bfd  mov     [rbp+40h+var_80], rax
0x140155c01  mov     rax, qword ptr [rbp+40h+var_C0]
0x140155c05  mov     qword ptr [rsp+140h+var_100], rax
0x140155c0a  lea     rax, [rsp+140h+var_100]
0x140155c0f  mov     [rbp+40h+var_70], rax
0x140155c13  mov     rax, qword ptr [rbp+40h+var_C0+8]
0x140155c17  mov     qword ptr [rsp+140h+var_100+8], rax
0x140155c1c  lea     rax, [rsp+140h+var_100+8]
0x140155c21  mov     [rbp+40h+var_60], rax
0x140155c25  mov     rax, qword ptr [rbp+40h+var_B0]
0x140155c29  mov     qword ptr [rsp+140h+var_F0], rax
0x140155c2e  lea     rax, [rsp+140h+var_F0]
0x140155c33  mov     [rbp+40h+var_50], rax
0x140155c37  mov     rax, qword ptr [rbp+40h+var_B0+8]
0x140155c3b  mov     qword ptr [rsp+140h+var_F0+8], rax
0x140155c40  lea     rax, [rsp+140h+var_F0+8]
0x140155c45  mov     [rbp+40h+var_40], rax
0x140155c49  mov     [rbp+40h+var_78], 8
0x140155c51  mov     [rbp+40h+var_68], 8
0x140155c59  mov     [rbp+40h+var_58], 8
0x140155c61  mov     [rbp+40h+var_48], 8
0x140155c69  mov     [rbp+40h+var_38], 8
0x140155c71  call    TcpGetAverageInSegSize
0x140155c76  mov     [rsp+140h+var_E0], rax
0x140155c7b  lea     rax, [rsp+140h+var_E0]
0x140155c80  mov     [rbp+40h+var_30], rax
0x140155c84  mov     [rbp+40h+var_28], 8
0x140155c8c  call    UdpGetAverageInNetBufferSize
0x140155c91  mov     [rsp+140h+var_D8], rax
0x140155c96  lea     rdx, byte_1401F1D69
0x140155c9d  lea     rax, [rsp+140h+var_D8]
0x140155ca2  mov     [rbp+40h+var_18], 8
0x140155caa  mov     [rbp+40h+var_20], rax
0x140155cae  lea     rcx, dword_1402201F8
0x140155cb5  lea     rax, [rbp+40h+var_A0]
0x140155cb9  xor     r9d, r9d
0x140155cbc  mov     [rsp+140h+var_118], rax
0x140155cc1  xor     r8d, r8d
0x140155cc4  mov     [rsp+140h+var_120], 9
0x140155ccc  call    _tlgWriteTransfer_EtwWriteTransfer
0x140155cd1  xorps   xmm0, xmm0
0x140155cd4  movups  [rsp+140h+var_D0], xmm0
0x140155cd9  mov     dword ptr [rsp+140h+var_D0], 1
0x140155ce1  mov     qword ptr [rsp+140h+var_D0+8], rbx
0x140155ce6  movups  [rbp+40h+var_C0], xmm0
0x140155cea  movups  [rbp+40h+var_B0], xmm0
0x140155cee  jmp     short loc_140155CFF
0x140155cf0  mov     rcx, rdi; SpinLock
0x140155cf3  call    cs:__imp_KeReleaseSpinLock
0x140155cfa  nop     dword ptr [rax+rax+00h]
0x140155cff  lea     r8, [rsp+140h+var_110]
0x140155d04  mov     [rsp+140h+var_110], 0
0x140155d0d  mov     edx, 40000000h
0x140155d12  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140155d19  call    cs:__imp_NetioOpenKey
0x140155d20  nop     dword ptr [rax+rax+00h]
0x140155d25  test    eax, eax
0x140155d27  js      short loc_140155D65
0x140155d29  mov     rcx, [rsp+140h+var_110]
0x140155d2e  lea     r9, [rsp+140h+var_D0]
0x140155d33  mov     r8d, 3
0x140155d39  mov     [rsp+140h+var_120], 30h ; '0'
0x140155d41  lea     rdx, aHealth; "Health"
0x140155d48  call    cs:__imp_NetioWriteKey
0x140155d4f  nop     dword ptr [rax+rax+00h]
0x140155d54  lea     rcx, [rsp+140h+var_110]
0x140155d59  call    cs:__imp_NetioCloseKey
0x140155d60  nop     dword ptr [rax+rax+00h]
0x140155d65  mov     edx, 36EE80h
0x140155d6a  lea     rcx, qword_140224390
0x140155d71  call    cs:__imp_NetioTimerWorkItemStart
0x140155d78  nop     dword ptr [rax+rax+00h]
0x140155d7d  mov     rcx, [rbp+40h+var_10]
0x140155d81  xor     rcx, rsp; StackCookie
0x140155d84  call    __security_check_cookie
0x140155d89  lea     r11, [rsp+140h+var_s0]
0x140155d91  mov     rbx, [r11+10h]
0x140155d95  mov     rdi, [r11+18h]
0x140155d99  mov     rsp, r11
0x140155d9c  pop     rbp
0x140155d9d  retn
```
