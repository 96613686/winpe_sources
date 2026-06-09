# HUBPDO_PublishBillboardDetails

- ea: `0x14008292c`
- end: `0x140082bd1`
- name: `HUBPDO_PublishBillboardDetails`
- size: `677`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140016160`

## callees

- `0x1400024b8`
- `0x14000cbb4`
- `0x140045570`
- `0x14008292c`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x140082a0f`
- `ntoskrnl!RtlInitializeBitMap` at `0x140082a0f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140082b5a`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140082b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082bb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082bb5`
- `ntoskrnl!ExAllocatePool2` at `0x14008299d`
- `ntoskrnl!ExAllocatePool2` at `0x14008299d`

## pseudocode

```c
void __fastcall HUBPDO_PublishBillboardDetails(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // r12
  __int64 v5; // rsi
  unsigned int v6; // r14d
  _BYTE *Pool2; // rax
  int v8; // edx
  _WORD *v9; // rdi
  __int64 i; // r10
  int DeviceInterfaceForBillboard; // edx
  int v12; // r9d
  int updated; // r8d
  __int64 v14; // [rsp+28h] [rbp-48h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+40h] [rbp-30h] BYREF
  __int128 v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  LODWORD(v17) = 0;
  v16 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1632))(WdfDriverGlobals, a1);
  v3 = *(_QWORD *)(a1 + 24);
  v4 = v2;
  v5 = **(_QWORD **)(v3 + 2656);
  v6 = 8 * *(unsigned __int8 *)(v5 + 4) + 4;
  Pool2 = (_BYTE *)ExAllocatePool2(256, v6, 1681082453);
  v9 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = *(_BYTE *)(v5 + 4);
    Pool2[1] = *(_BYTE *)(v5 + 5);
    RtlInitializeBitMap(&BitMapHeader, (PULONG)(v5 + 8), 0x20u);
    for ( i = 0; (unsigned int)i < *(unsigned __int8 *)(v5 + 4); i = (unsigned int)(i + 1) )
    {
      v9[4 * i + 2] = *(_WORD *)(v5 + 4 * i + 44);
      LOBYTE(v9[4 * i + 3]) = *(_BYTE *)(v5 + 4 * i + 46);
      *(_DWORD *)&v9[4 * i + 4] = _bittest64((const signed __int64 *)BitMapHeader.Buffer, (unsigned int)(2 * i))
                                | (2 * _bittest64(
                                         (const signed __int64 *)BitMapHeader.Buffer,
                                         (unsigned int)(2 * i + 1)));
    }
    *((_QWORD *)&v16 + 1) = DEVPKEY_Device_UsbBillboardInfo;
    *(_QWORD *)&v16 = 24;
    v17 = 0;
    DeviceInterfaceForBillboard = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, __int64, unsigned int, _WORD *))(WdfFunctions_01015 + 3480))(
                                    WdfDriverGlobals,
                                    v4,
                                    &v16,
                                    4099,
                                    v6,
                                    v9);
    if ( DeviceInterfaceForBillboard >= 0 )
    {
      DeviceInterfaceForBillboard = HUBFDO_CreateDeviceInterfaceForBillboard(
                                      *(_QWORD *)v3,
                                      *(_WORD *)(a1 + 48),
                                      (_QWORD *)(v3 + 2664),
                                      (_BYTE *)(v3 + 2672),
                                      v6,
                                      (__int64)v9);
      if ( DeviceInterfaceForBillboard >= 0 )
      {
        updated = ZwUpdateWnfStateData(&WNF_USB_BILLBOARD_CHANGE, 0, 0, 0, 0, 0, 0);
        if ( updated >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_17;
        v12 = 100;
        LODWORD(v14) = updated;
        goto LABEL_16;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v12 = 99;
        goto LABEL_9;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 98;
LABEL_9:
      LODWORD(v14) = DeviceInterfaceForBillboard;
LABEL_16:
      LOBYTE(DeviceInterfaceForBillboard) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 1432LL),
        DeviceInterfaceForBillboard,
        2,
        v12,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v14);
    }
LABEL_17:
    ExFreePoolWithTag(v9, 0x64334855u);
    return;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 1432LL),
      v8,
      2,
      97,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      v6);
  }
}

```

## disassembly

```asm
0x14008292c  push    rbp
0x14008292e  push    rbx
0x14008292f  push    rsi
0x140082930  push    rdi
0x140082931  push    r12
0x140082933  push    r14
0x140082935  push    r15
0x140082937  mov     rbp, rsp
0x14008293a  sub     rsp, 70h
0x14008293e  xor     eax, eax
0x140082940  xorps   xmm0, xmm0
0x140082943  mov     qword ptr [rbp+BitMapHeader+4], rax
0x140082947  mov     r15, rcx
0x14008294a  mov     [rbp-30h], rax
0x14008294e  mov     rdx, rcx
0x140082951  mov     rcx, cs:WdfDriverGlobals
0x140082958  mov     dword ptr [rbp+var_10], eax
0x14008295b  mov     rax, cs:WdfFunctions_01015
0x140082962  movups  [rbp+var_20], xmm0
0x140082966  mov     rax, [rax+660h]
0x14008296d  call    _guard_dispatch_icall
0x140082972  mov     rbx, [r15+18h]
0x140082976  mov     r12, rax
0x140082979  mov     ecx, 100h
0x14008297e  mov     r8d, 64334855h
0x140082984  mov     rax, [rbx+0A60h]
0x14008298b  mov     rsi, [rax]
0x14008298e  movzx   eax, byte ptr [rsi+4]
0x140082992  lea     r14d, ds:4[rax*8]
0x14008299a  mov     edx, r14d
0x14008299d  call    cs:__imp_ExAllocatePool2
0x1400829a4  nop     dword ptr [rax+rax+00h]
0x1400829a9  mov     rdi, rax
0x1400829ac  test    rax, rax
0x1400829af  jnz     short loc_1400829F6
0x1400829b1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400829b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400829bf  jz      loc_140082BC1
0x1400829c5  mov     rcx, [rbx+8]
0x1400829c9  lea     r8d, [rdi+2]
0x1400829cd  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400829d4  mov     dword ptr [rsp+70h+var_48], r14d
0x1400829d9  lea     r9d, [rdi+61h]
0x1400829dd  mov     [rsp+70h+var_50], rax
0x1400829e2  mov     dl, r8b
0x1400829e5  mov     rcx, [rcx+598h]
0x1400829ec  call    WPP_RECORDER_SF_d
0x1400829f1  jmp     loc_140082BC1
0x1400829f6  mov     al, [rsi+4]
0x1400829f9  lea     rdx, [rsi+8]; BitMapBuffer
0x1400829fd  mov     [rdi], al
0x1400829ff  lea     rcx, [rbp+BitMapHeader]; BitMapHeader
0x140082a03  mov     al, [rsi+5]
0x140082a06  mov     r8d, 20h ; ' '; SizeOfBitMap
0x140082a0c  mov     [rdi+1], al
0x140082a0f  call    cs:__imp_RtlInitializeBitMap
0x140082a16  nop     dword ptr [rax+rax+00h]
0x140082a1b  xor     r10d, r10d
0x140082a1e  cmp     [rsi+4], r10b
0x140082a22  jbe     short loc_140082A76
0x140082a24  movzx   eax, word ptr [rsi+r10*4+2Ch]
0x140082a2a  lea     r8d, [r10+r10]
0x140082a2e  mov     [rdi+r10*8+4], ax
0x140082a34  lea     ecx, [r8+1]
0x140082a38  mov     al, [rsi+r10*4+2Eh]
0x140082a3d  mov     [rdi+r10*8+6], al
0x140082a42  mov     rax, [rbp+BitMapHeader.Buffer]
0x140082a46  bt      [rax], rcx
0x140082a4a  mov     rax, [rbp+BitMapHeader.Buffer]
0x140082a4e  mov     ecx, r8d
0x140082a51  setb    dl
0x140082a54  bt      [rax], rcx
0x140082a58  movzx   ecx, dl
0x140082a5b  setb    al
0x140082a5e  add     ecx, ecx
0x140082a60  movzx   eax, al
0x140082a63  or      ecx, eax
0x140082a65  mov     [rdi+r10*8+8], ecx
0x140082a6a  inc     r10d
0x140082a6d  movzx   eax, byte ptr [rsi+4]
0x140082a71  cmp     r10d, eax
0x140082a74  jb      short loc_140082A24
0x140082a76  mov     rcx, cs:WdfDriverGlobals
0x140082a7d  lea     rax, DEVPKEY_Device_UsbBillboardInfo
0x140082a84  mov     qword ptr [rbp+var_20+8], rax
0x140082a88  lea     r8, [rbp+var_20]
0x140082a8c  mov     rax, cs:WdfFunctions_01015
0x140082a93  mov     r9d, 1003h
0x140082a99  mov     qword ptr [rbp+var_20], 18h
0x140082aa1  mov     rdx, r12
0x140082aa4  mov     [rbp+var_10], 0
0x140082aac  mov     [rsp+70h+var_48], rdi
0x140082ab1  mov     rax, [rax+0D98h]
0x140082ab8  mov     dword ptr [rsp+70h+var_50], r14d
0x140082abd  call    _guard_dispatch_icall
0x140082ac2  mov     edx, eax
0x140082ac4  test    eax, eax
0x140082ac6  jns     short loc_140082AEB
0x140082ac8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082acf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082ad6  jz      loc_140082BAD
0x140082adc  mov     r9d, 62h ; 'b'
0x140082ae2  mov     dword ptr [rsp+70h+var_48], edx
0x140082ae6  jmp     loc_140082B88
0x140082aeb  movzx   edx, word ptr [r15+30h]
0x140082af0  lea     r9, [rbx+0A70h]
0x140082af7  mov     rcx, [rbx]
0x140082afa  lea     r8, [rbx+0A68h]
0x140082b01  mov     [rsp+70h+var_48], rdi
0x140082b06  mov     dword ptr [rsp+70h+var_50], r14d
0x140082b0b  call    HUBFDO_CreateDeviceInterfaceForBillboard
0x140082b10  mov     edx, eax
0x140082b12  test    eax, eax
0x140082b14  jns     short loc_140082B32
0x140082b16  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082b1d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082b24  jz      loc_140082BAD
0x140082b2a  mov     r9d, 63h ; 'c'
0x140082b30  jmp     short loc_140082AE2
0x140082b32  mov     [rsp+70h+var_40], 0
0x140082b3a  lea     rcx, WNF_USB_BILLBOARD_CHANGE
0x140082b41  mov     dword ptr [rsp+70h+var_48], 0
0x140082b49  xor     r9d, r9d
0x140082b4c  xor     r8d, r8d
0x140082b4f  mov     [rsp+70h+var_50], 0
0x140082b58  xor     edx, edx
0x140082b5a  call    cs:__imp_ZwUpdateWnfStateData
0x140082b61  nop     dword ptr [rax+rax+00h]
0x140082b66  mov     r8d, eax
0x140082b69  test    eax, eax
0x140082b6b  jns     short loc_140082BAD
0x140082b6d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082b74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082b7b  jz      short loc_140082BAD
0x140082b7d  mov     r9d, 64h ; 'd'
0x140082b83  mov     dword ptr [rsp+70h+var_48], r8d
0x140082b88  mov     rcx, [rbx+8]
0x140082b8c  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140082b93  mov     r8d, 2
0x140082b99  mov     [rsp+70h+var_50], rax
0x140082b9e  mov     dl, r8b
0x140082ba1  mov     rcx, [rcx+598h]
0x140082ba8  call    WPP_RECORDER_SF_d
0x140082bad  mov     edx, 64334855h; Tag
0x140082bb2  mov     rcx, rdi; P
0x140082bb5  call    cs:__imp_ExFreePoolWithTag
0x140082bbc  nop     dword ptr [rax+rax+00h]
0x140082bc1  add     rsp, 70h
0x140082bc5  pop     r15
0x140082bc7  pop     r14
0x140082bc9  pop     r12
0x140082bcb  pop     rdi
0x140082bcc  pop     rsi
0x140082bcd  pop     rbx
0x140082bce  pop     rbp
0x140082bcf  retn
```
