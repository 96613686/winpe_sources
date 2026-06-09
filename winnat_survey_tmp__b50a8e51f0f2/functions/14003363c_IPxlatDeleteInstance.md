# IPxlatDeleteInstance

- ea: `0x14003363c`
- end: `0x1400336fa`
- name: `IPxlatDeleteInstance`
- size: `190`
- prototype: `void __fastcall(__int64 P)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400159b4`
- `0x140015dac`
- `0x140015eb8`

## callees

- `0x14000caa0`
- `0x14001623c`
- `0x14001784c`
- `0x14002d008`
- `0x14003363c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400336e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400336e2`

## pseudocode

```c
void __fastcall IPxlatDeleteInstance(__int64 P)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // edi

  v4 = IPxlatRemoveFiltersForInstance(P);
  if ( v4 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v3, v2);
  if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_IPXLAT_INSTANCE_DELETION,
      P + 106,
      *(_QWORD *)(P + 16),
      *(_DWORD *)(P + 84),
      *(_DWORD *)(P + 80),
      P + 28,
      P + 106,
      *(_BYTE *)(P + 122),
      P + 88,
      *(_BYTE *)(P + 104));
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_d(1025, 17, WPP_24083f43286932c6336729c882afb6f6_Traceguids, (unsigned int)v4);
  ExFreePoolWithTag((PVOID)P, 0);
}

```

## disassembly

```asm
0x14003363c  mov     [rsp+arg_0], rbx
0x140033641  push    rdi
0x140033642  sub     rsp, 60h
0x140033646  mov     rbx, rcx
0x140033649  call    IPxlatRemoveFiltersForInstance
0x14003364e  mov     edi, eax
0x140033650  test    eax, eax
0x140033652  jns     short loc_140033659
0x140033654  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033659  cmp     cs:dword_140026104, 1
0x140033660  jnz     short loc_1400336BB
0x140033662  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140033669  jz      short loc_1400336BB
0x14003366b  movzx   eax, byte ptr [rbx+68h]
0x14003366f  lea     rcx, [rbx+58h]
0x140033673  movzx   edx, byte ptr [rbx+7Ah]
0x140033677  lea     r8, [rbx+6Ah]
0x14003367b  mov     [rsp+68h+var_18], eax
0x14003367f  lea     r9, [rbx+1Ch]
0x140033683  mov     eax, [rbx+50h]
0x140033686  mov     [rsp+68h+var_20], rcx
0x14003368b  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140033692  mov     [rsp+68h+var_28], edx
0x140033696  lea     rdx, WINNAT_IPXLAT_INSTANCE_DELETION
0x14003369d  mov     [rsp+68h+var_30], r8
0x1400336a2  mov     [rsp+68h+var_38], r9
0x1400336a7  mov     r9, [rbx+10h]
0x1400336ab  mov     [rsp+68h+var_40], eax
0x1400336af  mov     eax, [rbx+54h]
0x1400336b2  mov     [rsp+68h+var_48], eax
0x1400336b6  call    McTemplateK0xqqb16b16qb16q_EtwWriteTransfer
0x1400336bb  test    byte ptr cs:xmmword_1400262E0, 2
0x1400336c2  jz      short loc_1400336DD
0x1400336c4  mov     edx, 11h
0x1400336c9  lea     r8, WPP_24083f43286932c6336729c882afb6f6_Traceguids
0x1400336d0  mov     ecx, 401h
0x1400336d5  mov     r9d, edi
0x1400336d8  call    WPP_SF_d
0x1400336dd  xor     edx, edx; Tag
0x1400336df  mov     rcx, rbx; P
0x1400336e2  call    cs:__imp_ExFreePoolWithTag
0x1400336e9  nop     dword ptr [rax+rax+00h]
0x1400336ee  mov     rbx, [rsp+68h+arg_0]
0x1400336f3  add     rsp, 60h
0x1400336f7  pop     rdi
0x1400336f8  retn
```
