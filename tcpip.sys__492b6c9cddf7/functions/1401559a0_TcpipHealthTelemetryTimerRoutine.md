# TcpipHealthTelemetryTimerRoutine

- ea: `0x1401559a0`
- end: `0x140155c5f`
- name: `TcpipHealthTelemetryTimerRoutine`
- size: `703`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400fd5a4`
- `0x1401281e0`
- `0x1401559a0`
- `0x14015b77c`
- `0x140166604`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140155a76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155bb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155a76`
- `ntoskrnl!KeReleaseSpinLock` at `0x140155bb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401559ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401559ee`
- `NETIO!NetioOpenKey` at `0x140155bd9`
- `NETIO!NetioOpenKey` at `0x140155bd9`
- `NETIO!NetioTimerWorkItemStart` at `0x140155c31`
- `NETIO!NetioTimerWorkItemStart` at `0x140155c31`
- `NETIO!NetioCloseKey` at `0x140155c19`
- `NETIO!NetioCloseKey` at `0x140155c19`
- `NETIO!NetioWriteKey` at `0x140155c08`
- `NETIO!NetioWriteKey` at `0x140155c08`

## string_xrefs

- `0x140155bd2`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters`

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
  return NetioTimerWorkItemStart(qword_1402243D0, 3600000);
}

```

## disassembly

```asm
0x1401559a0  mov     [rsp-8+arg_0], rbx
0x1401559a5  mov     [rsp-8+arg_8], rdi
0x1401559aa  push    rbp
0x1401559ab  lea     rbp, [rsp-40h]
0x1401559b0  sub     rsp, 140h
0x1401559b7  mov     rax, cs:__security_cookie
0x1401559be  xor     rax, rsp
0x1401559c1  mov     [rbp+40h+var_10], rax
0x1401559c5  xorps   xmm0, xmm0
0x1401559c8  lea     rdi, WPP_MAIN_CB.SectorSize
0x1401559cf  movups  [rbp+40h+var_C0], xmm0
0x1401559d3  mov     rbx, 0FFFFF78000000014h
0x1401559dd  xor     eax, eax
0x1401559df  movups  [rsp+140h+var_D0], xmm0
0x1401559e4  mov     rcx, rdi; SpinLock
0x1401559e7  movups  [rbp+40h+var_C0+0Ch], xmm0
0x1401559eb  mov     rbx, [rbx]
0x1401559ee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1401559f5  nop     dword ptr [rax+rax+00h]
0x1401559fa  movups  xmm2, xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData
0x140155a01  mov     dl, al; NewIrql
0x140155a03  movups  xmm0, xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x140155a0a  movups  xmm1, xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140155a11  movups  [rsp+140h+var_D0], xmm2
0x140155a16  psrldq  xmm2, 8
0x140155a1b  movq    r8, xmm2
0x140155a20  movups  [rbp+40h+var_C0], xmm0
0x140155a24  movups  [rbp+40h+var_B0], xmm1
0x140155a28  cmp     rbx, r8
0x140155a2b  jle     loc_140155BB0
0x140155a31  mov     rax, rbx
0x140155a34  sub     rax, r8
0x140155a37  mov     r8, 0C92A69C000h
0x140155a41  cmp     rax, r8
0x140155a44  jb      loc_140155BB0
0x140155a4a  xorps   xmm0, xmm0
0x140155a4d  mov     rcx, rdi; SpinLock
0x140155a50  movups  xmmword ptr cs:WPP_MAIN_CB.Dpc.DpcData, xmm0
0x140155a57  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData, 1
0x140155a61  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rbx
0x140155a68  movups  xmmword ptr cs:WPP_MAIN_CB.SecurityDescriptor, xmm0
0x140155a6f  movups  xmmword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, xmm0
0x140155a76  call    cs:__imp_KeReleaseSpinLock
0x140155a7d  nop     dword ptr [rax+rax+00h]
0x140155a82  mov     eax, cs:dword_1402201F8
0x140155a88  cmp     eax, 5
0x140155a8b  jbe     loc_140155B91
0x140155a91  mov     rdx, 400000000000h
0x140155a9b  lea     rcx, dword_1402201F8
0x140155aa2  call    _tlgKeywordOn
0x140155aa7  test    al, al
0x140155aa9  jz      loc_140155B91
0x140155aaf  lea     rax, [rsp+140h+var_108]
0x140155ab4  mov     [rsp+140h+var_108], 800h
0x140155abd  mov     [rbp+40h+var_80], rax
0x140155ac1  mov     rax, qword ptr [rbp+40h+var_C0]
0x140155ac5  mov     qword ptr [rsp+140h+var_100], rax
0x140155aca  lea     rax, [rsp+140h+var_100]
0x140155acf  mov     [rbp+40h+var_70], rax
0x140155ad3  mov     rax, qword ptr [rbp+40h+var_C0+8]
0x140155ad7  mov     qword ptr [rsp+140h+var_100+8], rax
0x140155adc  lea     rax, [rsp+140h+var_100+8]
0x140155ae1  mov     [rbp+40h+var_60], rax
0x140155ae5  mov     rax, qword ptr [rbp+40h+var_B0]
0x140155ae9  mov     qword ptr [rsp+140h+var_F0], rax
0x140155aee  lea     rax, [rsp+140h+var_F0]
0x140155af3  mov     [rbp+40h+var_50], rax
0x140155af7  mov     rax, qword ptr [rbp+40h+var_B0+8]
0x140155afb  mov     qword ptr [rsp+140h+var_F0+8], rax
0x140155b00  lea     rax, [rsp+140h+var_F0+8]
0x140155b05  mov     [rbp+40h+var_40], rax
0x140155b09  mov     [rbp+40h+var_78], 8
0x140155b11  mov     [rbp+40h+var_68], 8
0x140155b19  mov     [rbp+40h+var_58], 8
0x140155b21  mov     [rbp+40h+var_48], 8
0x140155b29  mov     [rbp+40h+var_38], 8
0x140155b31  call    TcpGetAverageInSegSize
0x140155b36  mov     [rsp+140h+var_E0], rax
0x140155b3b  lea     rax, [rsp+140h+var_E0]
0x140155b40  mov     [rbp+40h+var_30], rax
0x140155b44  mov     [rbp+40h+var_28], 8
0x140155b4c  call    UdpGetAverageInNetBufferSize
0x140155b51  mov     [rsp+140h+var_D8], rax
0x140155b56  lea     rdx, byte_1401F1D69
0x140155b5d  lea     rax, [rsp+140h+var_D8]
0x140155b62  mov     [rbp+40h+var_18], 8
0x140155b6a  mov     [rbp+40h+var_20], rax
0x140155b6e  lea     rcx, dword_1402201F8
0x140155b75  lea     rax, [rbp+40h+var_A0]
0x140155b79  xor     r9d, r9d
0x140155b7c  mov     [rsp+140h+var_118], rax
0x140155b81  xor     r8d, r8d
0x140155b84  mov     [rsp+140h+var_120], 9
0x140155b8c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140155b91  xorps   xmm0, xmm0
0x140155b94  movups  [rsp+140h+var_D0], xmm0
0x140155b99  mov     dword ptr [rsp+140h+var_D0], 1
0x140155ba1  mov     qword ptr [rsp+140h+var_D0+8], rbx
0x140155ba6  movups  [rbp+40h+var_C0], xmm0
0x140155baa  movups  [rbp+40h+var_B0], xmm0
0x140155bae  jmp     short loc_140155BBF
0x140155bb0  mov     rcx, rdi; SpinLock
0x140155bb3  call    cs:__imp_KeReleaseSpinLock
0x140155bba  nop     dword ptr [rax+rax+00h]
0x140155bbf  lea     r8, [rsp+140h+var_110]
0x140155bc4  mov     [rsp+140h+var_110], 0
0x140155bcd  mov     edx, 40000000h
0x140155bd2  lea     rcx, aRegistryMachin_9; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140155bd9  call    cs:__imp_NetioOpenKey
0x140155be0  nop     dword ptr [rax+rax+00h]
0x140155be5  test    eax, eax
0x140155be7  js      short loc_140155C25
0x140155be9  mov     rcx, [rsp+140h+var_110]
0x140155bee  lea     r9, [rsp+140h+var_D0]
0x140155bf3  mov     r8d, 3
0x140155bf9  mov     [rsp+140h+var_120], 30h ; '0'
0x140155c01  lea     rdx, aHealth; "Health"
0x140155c08  call    cs:__imp_NetioWriteKey
0x140155c0f  nop     dword ptr [rax+rax+00h]
0x140155c14  lea     rcx, [rsp+140h+var_110]
0x140155c19  call    cs:__imp_NetioCloseKey
0x140155c20  nop     dword ptr [rax+rax+00h]
0x140155c25  mov     edx, 36EE80h
0x140155c2a  lea     rcx, qword_1402243D0
0x140155c31  call    cs:__imp_NetioTimerWorkItemStart
0x140155c38  nop     dword ptr [rax+rax+00h]
0x140155c3d  mov     rcx, [rbp+40h+var_10]
0x140155c41  xor     rcx, rsp; StackCookie
0x140155c44  call    __security_check_cookie
0x140155c49  lea     r11, [rsp+140h+var_s0]
0x140155c51  mov     rbx, [r11+10h]
0x140155c55  mov     rdi, [r11+18h]
0x140155c59  mov     rsp, r11
0x140155c5c  pop     rbp
0x140155c5d  retn
```
