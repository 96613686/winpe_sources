# IPxlatDeleteInstance

- ea: `0x14003476c`
- end: `0x1400348e7`
- name: `IPxlatDeleteInstance`
- size: `379`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140016334`
- `0x1400169e4`
- `0x140016af0`

## callees

- `0x14000caa0`
- `0x14000e390`
- `0x140016ea4`
- `0x140016f08`
- `0x1400185a0`
- `0x14002e008`
- `0x14003476c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400348c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400348c9`

## pseudocode

```c
void __fastcall IPxlatDeleteInstance(_BYTE *P)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  char v8; // si
  int v9; // r14d
  char v10; // bp
  int v11; // r15d
  __int64 v12; // r12
  __int64 v13; // rax
  int v14; // r8d
  _BYTE v15[88]; // [rsp+60h] [rbp-58h] BYREF
  int v16; // [rsp+C8h] [rbp+10h]

  v16 = IPxlatRemoveFiltersForInstance();
  v6 = v16;
  if ( v16 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2, v4);
  if ( (Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_CLAT_Preview2_RandomLocalAddress__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline(
                                     v3,
                                     v2,
                                     v4,
                                     v5);
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v8 = P[104];
      v9 = *((_DWORD *)P + 20);
      v10 = P[122];
      v11 = *((_DWORD *)P + 21);
      v12 = *((_QWORD *)P + 2);
      v13 = IPxlatResolveSyntheticIPv6Address(v15);
      McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNAT_IPXLAT_INSTANCE_DELETION,
        v14,
        v12,
        v11,
        v9,
        v13,
        (__int64)(P + 106),
        v10,
        (__int64)(P + 88),
        v8);
      v6 = v16;
    }
  }
  else if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_IPXLAT_INSTANCE_DELETION,
      (_DWORD)P + 106,
      *((_QWORD *)P + 2),
      *((_DWORD *)P + 21),
      *((_DWORD *)P + 20),
      (__int64)(P + 28),
      (__int64)(P + 106),
      P[122],
      (__int64)(P + 88),
      P[104]);
  }
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_d(1025, 19, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, v6);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14003476c  push    rbx
0x14003476e  push    rbp
0x14003476f  push    rsi
0x140034770  push    rdi
0x140034771  push    r12
0x140034773  push    r13
0x140034775  push    r14
0x140034777  push    r15
0x140034779  sub     rsp, 78h
0x14003477d  mov     r13, rcx
0x140034780  call    IPxlatRemoveFiltersForInstance
0x140034785  mov     [rsp+0B8h+arg_8], eax
0x14003478c  mov     ebx, eax
0x14003478e  test    eax, eax
0x140034790  jns     short loc_140034797
0x140034792  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140034797  mov     eax, cs:Feature_CLAT_Preview2_RandomLocalAddress__private_featureState
0x14003479d  mov     dil, 10h
0x1400347a0  test    dil, al
0x1400347a3  jz      short loc_1400347AA
0x1400347a5  and     eax, 1
0x1400347a8  jmp     short loc_1400347AF
0x1400347aa  call    Feature_CLAT_Preview2_RandomLocalAddress__private_IsEnabledDeviceUsageNoInline
0x1400347af  test    eax, eax
0x1400347b1  jz      loc_14003483C
0x1400347b7  cmp     cs:dword_140027104, 1
0x1400347be  jnz     loc_1400348A2
0x1400347c4  test    cs:Microsoft_Windows_WinNatEnableBits, dil
0x1400347cb  jz      loc_1400348A2
0x1400347d1  movzx   esi, byte ptr [r13+68h]
0x1400347d6  lea     rdx, [r13+50h]
0x1400347da  mov     r14d, [rdx]
0x1400347dd  lea     rcx, [rsp+0B8h+var_58]; void *
0x1400347e2  movzx   ebp, byte ptr [r13+7Ah]
0x1400347e7  lea     rbx, [r13+58h]
0x1400347eb  mov     r15d, [r13+54h]
0x1400347ef  lea     rdi, [r13+6Ah]
0x1400347f3  mov     r12, [r13+10h]
0x1400347f7  call    IPxlatResolveSyntheticIPv6Address
0x1400347fc  mov     [rsp+0B8h+var_68], esi
0x140034800  lea     rdx, WINNAT_IPXLAT_INSTANCE_DELETION
0x140034807  mov     [rsp+0B8h+var_70], rbx
0x14003480c  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140034813  mov     [rsp+0B8h+var_78], ebp
0x140034817  mov     r9, r12
0x14003481a  mov     [rsp+0B8h+var_80], rdi
0x14003481f  mov     [rsp+0B8h+var_88], rax
0x140034824  mov     [rsp+0B8h+var_90], r14d
0x140034829  mov     [rsp+0B8h+var_98], r15d
0x14003482e  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x140034833  mov     ebx, [rsp+0B8h+arg_8]
0x14003483a  jmp     short loc_1400348A2
0x14003483c  cmp     cs:dword_140027104, 1
0x140034843  jnz     short loc_1400348A2
0x140034845  test    cs:Microsoft_Windows_WinNatEnableBits, dil
0x14003484c  jz      short loc_1400348A2
0x14003484e  movzx   eax, byte ptr [r13+68h]
0x140034853  lea     rcx, [r13+58h]
0x140034857  movzx   edx, byte ptr [r13+7Ah]
0x14003485c  lea     r8, [r13+6Ah]
0x140034860  mov     [rsp+0B8h+var_68], eax
0x140034864  lea     r9, [r13+1Ch]
0x140034868  mov     eax, [r13+50h]
0x14003486c  mov     [rsp+0B8h+var_70], rcx
0x140034871  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140034878  mov     [rsp+0B8h+var_78], edx
0x14003487c  lea     rdx, WINNAT_IPXLAT_INSTANCE_DELETION
0x140034883  mov     [rsp+0B8h+var_80], r8
0x140034888  mov     [rsp+0B8h+var_88], r9
0x14003488d  mov     r9, [r13+10h]
0x140034891  mov     [rsp+0B8h+var_90], eax
0x140034895  mov     eax, [r13+54h]
0x140034899  mov     [rsp+0B8h+var_98], eax
0x14003489d  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x1400348a2  test    byte ptr cs:xmmword_1400272E0, 2
0x1400348a9  jz      short loc_1400348C4
0x1400348ab  mov     edx, 13h
0x1400348b0  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x1400348b7  mov     ecx, 401h
0x1400348bc  mov     r9d, ebx
0x1400348bf  call    WPP_SF_d
0x1400348c4  xor     edx, edx; Tag
0x1400348c6  mov     rcx, r13; P
0x1400348c9  call    cs:__imp_ExFreePoolWithTag
0x1400348d0  nop     dword ptr [rax+rax+00h]
0x1400348d5  add     rsp, 78h
0x1400348d9  pop     r15
0x1400348db  pop     r14
0x1400348dd  pop     r13
0x1400348df  pop     r12
0x1400348e1  pop     rdi
0x1400348e2  pop     rsi
0x1400348e3  pop     rbp
0x1400348e4  pop     rbx
0x1400348e5  retn
```
