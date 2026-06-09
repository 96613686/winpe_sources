# FilterBusDriverReadyCallbackRoutine

- ea: `0x1400033f0`
- end: `0x14000362c`
- name: `FilterBusDriverReadyCallbackRoutine`
- size: `572`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x14000228c`
- `0x1400033f0`
- `0x1400053c8`
- `0x140009e70`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000db14`
- `0x14000f110`

## pseudocode

```c
__int64 __fastcall FilterBusDriverReadyCallbackRoutine(char *NotificationStructure, __int64 Context, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+30h] [rbp-38h] BYREF
  int v9; // [rsp+38h] [rbp-30h]

  v8 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v4 = *(_QWORD *)(NotificationStructure + 4);
  v5 = *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1 - v4;
  if ( *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1 == v4 )
    v5 = *(_QWORD *)GUID_DEVICE_INTERFACE_ARRIVAL.Data4 - *(_QWORD *)(NotificationStructure + 12);
  if ( v5 )
  {
    v6 = *(_QWORD *)&GUID_DEVICE_INTERFACE_REMOVAL.Data1 - v4;
    if ( *(_QWORD *)&GUID_DEVICE_INTERFACE_REMOVAL.Data1 == v4 )
      v6 = *(_QWORD *)GUID_DEVICE_INTERFACE_REMOVAL.Data4 - *(_QWORD *)(NotificationStructure + 12);
    if ( v6 )
    {
      TraceAssert("FALSE", "onecoreuap\\net\\vwifi\\filter\\filter.c", 667);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF__guid_(
          WPP_GLOBAL_Control->AttachedDevice,
          51,
          WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
          NotificationStructure + 4);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      FilterRemoveMapping(*((PCUNICODE_STRING *)NotificationStructure + 5), Context, a3);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    if ( (unsigned int)SendIoctlToBus(*((PUNICODE_STRING *)NotificationStructure + 5), 0x2A4008u, 0, 0, &v8, 0xCu) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
    else if ( (_DWORD)v8 == 12 )
    {
      FilterAddMapping(HIDWORD(v8), v9, *((const UNICODE_STRING **)NotificationStructure + 5));
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400033f0  mov     [rsp+arg_8], rbx
0x1400033f5  mov     [rsp+arg_10], rbp
0x1400033fa  push    rsi
0x1400033fb  push    rdi
0x1400033fc  push    r14
0x1400033fe  sub     rsp, 50h
0x140003402  mov     rax, cs:__security_cookie
0x140003409  xor     rax, rsp
0x14000340c  mov     [rsp+68h+var_28], rax
0x140003411  xor     eax, eax
0x140003413  mov     rsi, rcx
0x140003416  mov     [rsp+68h+var_38], rax
0x14000341b  mov     [rsp+68h+var_30], eax
0x14000341f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003426  lea     rbp, WPP_GLOBAL_Control
0x14000342d  lea     r14, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140003434  cmp     rcx, rbp
0x140003437  jz      short loc_140003451
0x140003439  mov     eax, [rcx+2Ch]
0x14000343c  test    al, 20h
0x14000343e  jz      short loc_140003451
0x140003440  mov     rcx, [rcx+18h]
0x140003444  mov     edx, 2Eh ; '.'
0x140003449  mov     r8, r14
0x14000344c  call    WPP_SF_
0x140003451  mov     rcx, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x140003458  mov     rax, [rsi+4]
0x14000345c  sub     rcx, rax
0x14000345f  jnz     short loc_14000346C
0x140003461  mov     rcx, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x140003468  sub     rcx, [rsi+0Ch]
0x14000346c  test    rcx, rcx
0x14000346f  jnz     loc_140003552
0x140003475  mov     rcx, cs:WPP_GLOBAL_Control
0x14000347c  cmp     rcx, rbp
0x14000347f  jz      short loc_140003499
0x140003481  mov     eax, [rcx+2Ch]
0x140003484  test    al, 4
0x140003486  jz      short loc_140003499
0x140003488  mov     rcx, [rcx+18h]
0x14000348c  mov     edx, 2Fh ; '/'
0x140003491  mov     r8, r14
0x140003494  call    WPP_SF_
0x140003499  mov     rcx, [rsi+28h]; ObjectName
0x14000349d  lea     rax, [rsp+68h+var_38]
0x1400034a2  mov     [rsp+68h+var_40], 0Ch; ULONG
0x1400034aa  xor     r9d, r9d; InputBufferLength
0x1400034ad  xor     r8d, r8d; InputBuffer
0x1400034b0  mov     [rsp+68h+var_48], rax; PVOID
0x1400034b5  mov     edx, 2A4008h; IoControlCode
0x1400034ba  call    SendIoctlToBus
0x1400034bf  mov     edi, eax
0x1400034c1  test    eax, eax
0x1400034c3  jz      short loc_1400034FB
0x1400034c5  mov     r10, cs:WPP_GLOBAL_Control
0x1400034cc  cmp     r10, rbp
0x1400034cf  jz      loc_140003607
0x1400034d5  mov     ecx, [r10+2Ch]
0x1400034d9  test    cl, 1
0x1400034dc  jz      loc_1400035E0
0x1400034e2  mov     rcx, [r10+18h]
0x1400034e6  mov     edx, 30h ; '0'
0x1400034eb  mov     r9d, eax
0x1400034ee  mov     r8, r14
0x1400034f1  call    WPP_SF_d
0x1400034f6  jmp     loc_1400035E0
0x1400034fb  mov     r9d, dword ptr [rsp+68h+var_38]
0x140003500  cmp     r9d, 0Ch
0x140003504  jz      short loc_14000353C
0x140003506  mov     rcx, cs:WPP_GLOBAL_Control
0x14000350d  cmp     rcx, rbp
0x140003510  jz      loc_140003607
0x140003516  mov     eax, [rcx+2Ch]
0x140003519  mov     edi, 0C0230015h
0x14000351e  test    al, 1
0x140003520  jz      loc_1400035E0
0x140003526  mov     rcx, [rcx+18h]
0x14000352a  mov     edx, 31h ; '1'
0x14000352f  mov     r8, r14
0x140003532  call    WPP_SF_d
0x140003537  jmp     loc_1400035E0
0x14000353c  mov     r8, [rsi+28h]
0x140003540  mov     edx, [rsp+68h+var_30]
0x140003544  mov     ecx, dword ptr [rsp+68h+var_38+4]
0x140003548  call    FilterAddMapping
0x14000354d  jmp     loc_1400035E0
0x140003552  mov     rcx, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data1
0x140003559  xor     edi, edi
0x14000355b  sub     rcx, rax
0x14000355e  jnz     short loc_14000356B
0x140003560  mov     rcx, qword ptr cs:GUID_DEVICE_INTERFACE_REMOVAL.Data4
0x140003567  sub     rcx, [rsi+0Ch]
0x14000356b  test    rcx, rcx
0x14000356e  jnz     short loc_14000359F
0x140003570  mov     rcx, cs:WPP_GLOBAL_Control
0x140003577  cmp     rcx, rbp
0x14000357a  jz      short loc_140003594
0x14000357c  mov     eax, [rcx+2Ch]
0x14000357f  test    al, 4
0x140003581  jz      short loc_140003594
0x140003583  mov     rcx, [rcx+18h]
0x140003587  mov     edx, 32h ; '2'
0x14000358c  mov     r8, r14
0x14000358f  call    WPP_SF_
0x140003594  mov     rcx, [rsi+28h]; SourceString
0x140003598  call    FilterRemoveMapping
0x14000359d  jmp     short loc_1400035E0
0x14000359f  mov     r8d, 29Bh
0x1400035a5  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400035ac  lea     rcx, aFalse; "FALSE"
0x1400035b3  call    TraceAssert
0x1400035b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035bf  cmp     rcx, rbp
0x1400035c2  jz      short loc_140003607
0x1400035c4  mov     eax, [rcx+2Ch]
0x1400035c7  test    al, 4
0x1400035c9  jz      short loc_1400035E0
0x1400035cb  mov     rcx, [rcx+18h]
0x1400035cf  lea     r9, [rsi+4]
0x1400035d3  mov     edx, 33h ; '3'
0x1400035d8  mov     r8, r14
0x1400035db  call    WPP_SF__guid_
0x1400035e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400035e7  cmp     rcx, rbp
0x1400035ea  jz      short loc_140003607
0x1400035ec  mov     eax, [rcx+2Ch]
0x1400035ef  test    al, 20h
0x1400035f1  jz      short loc_140003607
0x1400035f3  mov     rcx, [rcx+18h]
0x1400035f7  mov     edx, 34h ; '4'
0x1400035fc  mov     r9d, edi
0x1400035ff  mov     r8, r14
0x140003602  call    WPP_SF_d
0x140003607  xor     eax, eax
0x140003609  mov     rcx, [rsp+68h+var_28]
0x14000360e  xor     rcx, rsp; StackCookie
0x140003611  call    __security_check_cookie
0x140003616  lea     r11, [rsp+68h+var_18]
0x14000361b  mov     rbx, [r11+28h]
0x14000361f  mov     rbp, [r11+30h]
0x140003623  mov     rsp, r11
0x140003626  pop     r14
0x140003628  pop     rdi
0x140003629  pop     rsi
0x14000362a  retn
```
