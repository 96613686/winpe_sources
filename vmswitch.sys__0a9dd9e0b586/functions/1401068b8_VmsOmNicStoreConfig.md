# VmsOmNicStoreConfig

- ea: `0x1401068b8`
- end: `0x140106fa0`
- name: `VmsOmNicStoreConfig`
- size: `1768`
- prototype: ``
- caller_count: `7`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007cd4c`
- `0x1400f617c`
- `0x1400ff28c`
- `0x1400ff618`
- `0x140102cac`
- `0x1401035a0`
- `0x140117fb0`

## callees

- `0x14001484c`
- `0x140027a64`
- `0x14002e45c`
- `0x140066a64`
- `0x14006b084`
- `0x14006bbf8`
- `0x14008497c`
- `0x140089a04`
- `0x14008d760`
- `0x1400a6dcc`
- `0x1400a6e48`
- `0x1400a6eb8`
- `0x1400a6f34`
- `0x140105934`
- `0x140105e58`
- `0x1401068b8`
- `0x140117854`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140106add`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106af4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b17`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b57`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ba3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106bc5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106add`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106af4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b17`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b31`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b57`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ba3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106bc5`
- `ntoskrnl!KeReleaseMutex` at `0x140106f28`
- `ntoskrnl!KeReleaseMutex` at `0x140106f28`
- `ntoskrnl!KeWaitForSingleObject` at `0x140106a6d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140106a6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106f59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106d66`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106f59`
- `NDIS!NdisReleaseRWLock` at `0x140106be6`
- `NDIS!NdisReleaseRWLock` at `0x140106be6`

## pseudocode

```c
__int64 __fastcall VmsOmNicStoreConfig(__int64 a1, const UNICODE_STRING *a2, int a3)
{
  __int64 v5; // rsi
  __int64 v6; // r13
  int v7; // edx
  char v8; // bl
  unsigned int v9; // r14d
  int v10; // r12d
  unsigned int MemberAdapterByName; // eax
  int v12; // edx
  __int64 v13; // r15
  struct _NDIS_RW_LOCK_EX *v14; // rcx
  unsigned int v15; // eax
  _WORD *VlanIDFromNdisDeviceRegkey; // rax
  void *v17; // r14
  BOOL v18; // r14d
  __int64 v19; // rdx
  unsigned int v21; // [rsp+50h] [rbp-B0h]
  char v22; // [rsp+54h] [rbp-ACh]
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  PCUNICODE_STRING SourceString; // [rsp+98h] [rbp-68h]
  PVOID P; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v31; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v32; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING v33; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v34; // [rsp+D8h] [rbp-28h] BYREF
  int v35; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v36; // [rsp+ECh] [rbp-14h]
  int v37; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v38; // [rsp+F4h] [rbp-Ch]
  _BYTE v39[256]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v40[256]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v41[256]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v42[256]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v43[256]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v44[512]; // [rsp+600h] [rbp+500h] BYREF

  v25 = a3;
  SourceString = a2;
  v21 = 0;
  v27 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v5 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = 0;
  P = 0;
  v26 = 0;
  v22 = 0;
  memset(v39, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v39;
  memset(v40, 0, 0xFEu);
  *(_QWORD *)&v33.Length = 16646144;
  v33.Buffer = (wchar_t *)v40;
  memset(v44, 0, 0x1FEu);
  *(_QWORD *)&v24.Length = 33423360;
  v24.Buffer = (wchar_t *)v44;
  memset(v41, 0, 0xFEu);
  *(_QWORD *)&v34.Length = 16646144;
  v34.Buffer = (wchar_t *)v41;
  memset(v42, 0, 0xFEu);
  *(_QWORD *)&v31.Length = 16646144;
  v31.Buffer = (wchar_t *)v42;
  memset(v43, 0, 0xFEu);
  v8 = 5;
  *(_QWORD *)&v32.Length = 16646144;
  v32.Buffer = (wchar_t *)v43;
  if ( *(_DWORD *)(a1 + 1872) == 5 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      v7,
      19,
      64,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (__int64)"Nic->Type != VmsNicExtDefault");
    if ( *(_DWORD *)(a1 + 1872) == 5 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  KeWaitForSingleObject((PVOID)(a1 + 1144), Executive, 0, 0, 0);
  v9 = *(_DWORD *)(a1 + 1872);
  v10 = *(_DWORD *)(a1 + 1200);
  if ( v9 == 2 && (v10 & 2) == 0 )
  {
    MemberAdapterByName = VmsPtNicMuxFindMemberAdapterByName(a2, a1, 70, &v26);
    v6 = v26;
    v21 = MemberAdapterByName;
    if ( MemberAdapterByName )
      goto LABEL_58;
    v22 = 1;
  }
  v8 = 0;
  v13 = 0;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  RtlCopyUnicodeString(&DestinationString, SourceString);
  RtlCopyUnicodeString(&v33, (PCUNICODE_STRING)(a1 + 344));
  if ( v9 == 2 && v6 )
  {
    RtlCopyUnicodeString(&v24, (PCUNICODE_STRING)(v6 + 2448));
  }
  else
  {
    RtlCopyUnicodeString(&v24, (PCUNICODE_STRING)(a1 + 616));
    if ( v9 == 1 )
    {
      v13 = *(_QWORD *)(a1 + 3312);
      if ( v13 )
      {
        RtlCopyUnicodeString(&v34, (PCUNICODE_STRING)(v13 + 96));
        v37 = *(_DWORD *)(a1 + 2104);
        v38 = *(_WORD *)(a1 + 2108);
        v35 = *(_DWORD *)(a1 + 3336);
        v36 = *(_WORD *)(a1 + 3340);
      }
    }
  }
  if ( *(_DWORD *)(a1 + 1880) == 1 )
  {
    RtlCopyUnicodeString(&v32, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 1984) + 72LL));
    RtlCopyUnicodeString(&v31, (PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(a1 + 1984) + 1240LL) + 72LL));
  }
  v14 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 56);
  *(_DWORD *)(a1 + 1200) = 0;
  *(_BYTE *)(a1 + 1204) = 0;
  NdisReleaseRWLock(v14, &LockState);
  if ( (v10 & 2) != 0 )
  {
    if ( v9 == 1 )
    {
      v21 = VmsOmDeleteObjectRegistryKey(0, 0, &DestinationString);
      if ( v21 == -1073741772 )
        v21 = 0;
      v8 = 10;
    }
  }
  else
  {
    v15 = VmsOmCreateObjectRegistryKey(0, 0, &DestinationString, &v27);
    v5 = v27;
    v21 = v15;
    if ( v15 )
    {
      v8 = 15;
    }
    else
    {
      v21 = VmsCsAttrValueWriteString(v27, &VmsOmSwitchNameStr, &v31);
      if ( v21 )
      {
        v8 = 20;
      }
      else
      {
        v21 = VmsCsAttrValueWriteString(v5, &VmsOmPortNameStr, &v32);
        if ( v21 )
        {
          v8 = 25;
        }
        else
        {
          v21 = VmsCsAttrValueWriteULong(v5, &VmsOmNicTypeStr, v9);
          if ( v21 )
          {
            v8 = 30;
          }
          else if ( v9 == 2 )
          {
            if ( v24.Length && (v21 = VmsCsAttrValueWriteString(v5, &VmsOmFriendlyNameStr, &v24)) != 0 )
            {
              v8 = 35;
            }
            else
            {
              v21 = VmsCsAttrValueReadString(v5, &VmsOmNicVlanIDStr, &P);
              if ( v21 )
              {
                v21 = 0;
                VlanIDFromNdisDeviceRegkey = (_WORD *)VmsPtGetVlanIDFromNdisDeviceRegkey(
                                                        (__int64)SourceString,
                                                        *(PDEVICE_OBJECT *)(v6 + 144));
                v17 = VlanIDFromNdisDeviceRegkey;
                if ( VlanIDFromNdisDeviceRegkey )
                {
                  if ( *VlanIDFromNdisDeviceRegkey
                    && (v21 = VmsCsAttrValueWriteString(v5, &VmsOmNicVlanIDStr, VlanIDFromNdisDeviceRegkey)) != 0 )
                  {
                    v8 = 40;
                  }
                  else
                  {
                    ExFreePoolWithTag(v17, 0);
                  }
                }
              }
            }
          }
          else if ( v9 == 1 )
          {
            v18 = 0;
            if ( v13 )
              v18 = *(_BYTE *)(v13 + 940) != 0;
            v21 = VmsCsAttrValueWriteString(v5, &VmsOmOriginalNameStr, &v33);
            if ( v21 )
            {
              v8 = 50;
            }
            else
            {
              v21 = VmsCsAttrValueWriteString(v5, &VmsOmFriendlyNameStr, &v24);
              if ( v21 )
              {
                v8 = 55;
              }
              else
              {
                v21 = VmsCsAttrValueWriteString(v5, &VmsOmMiniportDeviceGuidStr, &v34);
                if ( v21 )
                {
                  v8 = 60;
                }
                else
                {
                  v21 = VmsCsAttrValueWriteBinary(v5, &VmsOmNicCurrentMacAddressStr, &v35, 6);
                  if ( v21 )
                  {
                    v8 = 65;
                  }
                  else
                  {
                    v21 = VmsCsAttrValueWriteBinary(v5, &VmsOmNicPermanentMacAddressStr, &v37, 6);
                    if ( v21 )
                    {
                      v8 = 70;
                    }
                    else
                    {
                      v21 = VmsCsAttrValueWriteULong(v5, VmsOmIsLightWeightNicStr, v18);
                      if ( v21 )
                      {
                        v8 = 75;
                      }
                      else if ( v18 )
                      {
                        v21 = VmsCsAttrValueWriteULong(v5, VmsOmIsLightWeightNicEnableStr, *(_DWORD *)(v13 + 32) != 2);
                        if ( v21 )
                          v8 = 80;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_58:
  if ( v21 )
  {
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qZDd(
      VmsIfrNicLog,
      v12,
      20,
      65,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      a1,
      (__int64)&v24,
      v8,
      v21);
    VmsEtwTraceSwitchFailure(&VM_FAILED_TO_STORE_CONFIG_FOR_NIC, v8, (__int64)&DestinationString, (__int64)&v24);
  }
  if ( v5 )
    VmsCsKeyClose(v5);
  KeReleaseMutex((PRKMUTEX)(a1 + 1144), 0);
  if ( v22 )
    VmsOmNicDecrementControlCount(a1, *(unsigned __int16 *)(v6 + 16), 70);
  if ( P )
    ExFreePoolWithTag(P, 0);
  LOBYTE(v19) = v25;
  VmsOmpObjectDereference(a1, v19);
  return v21;
}

```

## disassembly

```asm
0x1401068b8  mov     [rsp-8+arg_18], rbx
0x1401068bd  push    rbp
0x1401068be  push    rsi
0x1401068bf  push    rdi
0x1401068c0  push    r12
0x1401068c2  push    r13
0x1401068c4  push    r14
0x1401068c6  push    r15
0x1401068c8  lea     rbp, [rsp-710h]
0x1401068d0  sub     rsp, 810h
0x1401068d7  mov     rax, cs:__security_cookie
0x1401068de  xor     rax, rsp
0x1401068e1  mov     [rbp+740h+var_40], rax
0x1401068e8  xor     r12d, r12d
0x1401068eb  mov     [rsp+840h+var_7D0], r8d
0x1401068f0  xor     eax, eax
0x1401068f2  mov     [rbp+740h+SourceString], rdx
0x1401068f6  mov     r15, rdx
0x1401068f9  mov     [rsp+840h+var_7F0], r12d
0x1401068fe  mov     rdi, rcx
0x140106901  mov     [rbp+740h+var_7C0], r12
0x140106905  mov     r14d, 0FEh
0x14010690b  mov     [rbp+740h+var_758], r12d
0x14010690f  mov     r8d, r14d; Size
0x140106912  mov     [rbp+740h+var_754], r12w
0x140106917  xor     edx, edx; Val
0x140106919  mov     [rbp+740h+var_750], r12d
0x14010691d  lea     rcx, [rbp+740h+var_740]; void *
0x140106921  mov     [rbp+740h+var_74C], r12w
0x140106926  mov     esi, r12d
0x140106929  mov     word ptr [rsp+840h+LockState.OldIrql], ax
0x14010692e  mov     [rsp+840h+LockState.Flags], al
0x140106932  mov     r13d, r12d
0x140106935  mov     [rbp+740h+P], r12
0x140106939  mov     [rsp+840h+var_7C8], r12
0x14010693e  mov     [rsp+840h+var_7EC], r12b
0x140106943  call    memset
0x140106948  lea     rax, [rbp+740h+var_740]
0x14010694c  mov     qword ptr [rbp+740h+DestinationString.Length], 0FE0000h
0x140106954  mov     r8d, r14d; Size
0x140106957  mov     [rbp+740h+DestinationString.Buffer], rax
0x14010695b  xor     edx, edx; Val
0x14010695d  lea     rcx, [rbp+740h+var_640]; void *
0x140106964  call    memset
0x140106969  lea     rax, [rbp+740h+var_640]
0x140106970  mov     qword ptr [rbp+740h+var_778.Length], 0FE0000h
0x140106978  xor     edx, edx; Val
0x14010697a  mov     [rbp+740h+var_778.Buffer], rax
0x14010697e  mov     r8d, 1FEh; Size
0x140106984  lea     rcx, [rbp+740h+var_240]; void *
0x14010698b  call    memset
0x140106990  lea     rax, [rbp+740h+var_240]
0x140106997  mov     qword ptr [rsp+840h+var_7E0.Length], 1FE0000h
0x1401069a0  mov     r8d, r14d; Size
0x1401069a3  mov     [rsp+840h+var_7E0.Buffer], rax
0x1401069a8  xor     edx, edx; Val
0x1401069aa  lea     rcx, [rbp+740h+var_540]; void *
0x1401069b1  call    memset
0x1401069b6  lea     rax, [rbp+740h+var_540]
0x1401069bd  mov     qword ptr [rbp+740h+var_768.Length], 0FE0000h
0x1401069c5  mov     r8d, r14d; Size
0x1401069c8  mov     [rbp+740h+var_768.Buffer], rax
0x1401069cc  xor     edx, edx; Val
0x1401069ce  lea     rcx, [rbp+740h+var_440]; void *
0x1401069d5  call    memset
0x1401069da  lea     rax, [rbp+740h+var_440]
0x1401069e1  mov     qword ptr [rbp+740h+var_798.Length], 0FE0000h
0x1401069e9  mov     r8d, r14d; Size
0x1401069ec  mov     [rbp+740h+var_798.Buffer], rax
0x1401069f0  xor     edx, edx; Val
0x1401069f2  lea     rcx, [rbp+740h+var_340]; void *
0x1401069f9  call    memset
0x1401069fe  lea     ebx, [r12+5]
0x140106a03  mov     qword ptr [rbp+740h+var_788.Length], 0FE0000h
0x140106a0b  lea     rax, [rbp+740h+var_340]
0x140106a12  lea     rcx, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140106a19  mov     [rbp+740h+var_788.Buffer], rax
0x140106a1d  cmp     [rdi+750h], ebx
0x140106a23  jnz     short loc_140106A59
0x140106a25  lea     rax, aNicTypeVmsnice; "Nic->Type != VmsNicExtDefault"
0x140106a2c  mov     [rsp+840h+var_818], rax
0x140106a31  lea     r9d, [r12+40h]
0x140106a36  mov     [rsp+840h+Timeout], rcx
0x140106a3b  lea     r8d, [r12+13h]
0x140106a40  mov     rcx, cs:VmsIfrLog
0x140106a47  call    WPP_RECORDER_SF_s
0x140106a4c  cmp     [rdi+750h], ebx
0x140106a52  jnz     short loc_140106A59
0x140106a54  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->Type != VmsNicExtDefault")
0x140106a59  lea     rcx, [rdi+478h]; Object
0x140106a60  mov     [rsp+840h+Timeout], r12; Timeout
0x140106a65  xor     r9d, r9d; Alertable
0x140106a68  xor     r8d, r8d; WaitMode
0x140106a6b  xor     edx, edx; WaitReason
0x140106a6d  call    cs:__imp_KeWaitForSingleObject
0x140106a74  nop     dword ptr [rax+rax+00h]
0x140106a79  mov     r14d, [rdi+750h]
0x140106a80  mov     r12d, [rdi+4B0h]
0x140106a87  cmp     r14d, 2
0x140106a8b  jnz     short loc_140106AC0
0x140106a8d  test    r14b, r12b
0x140106a90  jnz     short loc_140106AC0
0x140106a92  lea     r9, [rsp+840h+var_7C8]
0x140106a97  mov     rdx, rdi
0x140106a9a  lea     r8d, [r14+44h]
0x140106a9e  mov     rcx, r15
0x140106aa1  call    VmsPtNicMuxFindMemberAdapterByName
0x140106aa6  mov     r13, [rsp+840h+var_7C8]
0x140106aab  mov     [rsp+840h+var_7F0], eax
0x140106aaf  test    eax, eax
0x140106ab1  jz      short loc_140106ABB
0x140106ab3  xor     r12d, r12d
0x140106ab6  jmp     loc_140106EA7
0x140106abb  mov     [rsp+840h+var_7EC], 1
0x140106ac0  xor     r8d, r8d
0x140106ac3  lea     rdx, [rsp+840h+LockState]
0x140106ac8  mov     rcx, rdi
0x140106acb  xor     ebx, ebx
0x140106acd  xor     r15d, r15d
0x140106ad0  call    VmsOmObjectLockExclusive
0x140106ad5  mov     rdx, [rbp+740h+SourceString]; SourceString
0x140106ad9  lea     rcx, [rbp+740h+DestinationString]; DestinationString
0x140106add  call    cs:__imp_RtlCopyUnicodeString
0x140106ae4  nop     dword ptr [rax+rax+00h]
0x140106ae9  lea     rdx, [rdi+158h]; SourceString
0x140106af0  lea     rcx, [rbp+740h+var_778]; DestinationString
0x140106af4  call    cs:__imp_RtlCopyUnicodeString
0x140106afb  nop     dword ptr [rax+rax+00h]
0x140106b00  cmp     r14d, 2
0x140106b04  jnz     short loc_140106B25
0x140106b06  test    r13, r13
0x140106b09  jz      short loc_140106B25
0x140106b0b  lea     rdx, [r13+990h]; SourceString
0x140106b12  lea     rcx, [rsp+840h+var_7E0]; DestinationString
0x140106b17  call    cs:__imp_RtlCopyUnicodeString
0x140106b1e  nop     dword ptr [rax+rax+00h]
0x140106b23  jmp     short loc_140106B8B
0x140106b25  lea     rdx, [rdi+268h]; SourceString
0x140106b2c  lea     rcx, [rsp+840h+var_7E0]; DestinationString
0x140106b31  call    cs:__imp_RtlCopyUnicodeString
0x140106b38  nop     dword ptr [rax+rax+00h]
0x140106b3d  cmp     r14d, 1
0x140106b41  jnz     short loc_140106B8B
0x140106b43  mov     r15, [rdi+0CF0h]
0x140106b4a  test    r15, r15
0x140106b4d  jz      short loc_140106B8B
0x140106b4f  lea     rdx, [r15+60h]; SourceString
0x140106b53  lea     rcx, [rbp+740h+var_768]; DestinationString
0x140106b57  call    cs:__imp_RtlCopyUnicodeString
0x140106b5e  nop     dword ptr [rax+rax+00h]
0x140106b63  mov     eax, [rdi+838h]
0x140106b69  mov     [rbp+740h+var_750], eax
0x140106b6c  movzx   eax, word ptr [rdi+83Ch]
0x140106b73  mov     [rbp+740h+var_74C], ax
0x140106b77  mov     eax, [rdi+0D08h]
0x140106b7d  mov     [rbp+740h+var_758], eax
0x140106b80  movzx   eax, word ptr [rdi+0D0Ch]
0x140106b87  mov     [rbp+740h+var_754], ax
0x140106b8b  cmp     dword ptr [rdi+758h], 1
0x140106b92  jnz     short loc_140106BD1
0x140106b94  mov     rdx, [rdi+7C0h]
0x140106b9b  lea     rcx, [rbp+740h+var_788]; DestinationString
0x140106b9f  add     rdx, 48h ; 'H'; SourceString
0x140106ba3  call    cs:__imp_RtlCopyUnicodeString
0x140106baa  nop     dword ptr [rax+rax+00h]
0x140106baf  mov     rax, [rdi+7C0h]
0x140106bb6  lea     rcx, [rbp+740h+var_798]; DestinationString
0x140106bba  mov     rdx, [rax+4D8h]
0x140106bc1  add     rdx, 48h ; 'H'; SourceString
0x140106bc5  call    cs:__imp_RtlCopyUnicodeString
0x140106bcc  nop     dword ptr [rax+rax+00h]
0x140106bd1  mov     rcx, [rdi+38h]; Lock
0x140106bd5  lea     rdx, [rsp+840h+LockState]; LockState
0x140106bda  mov     [rdi+4B0h], ebx
0x140106be0  mov     [rdi+4B4h], bl
0x140106be6  call    cs:__imp_NdisReleaseRWLock
0x140106bed  nop     dword ptr [rax+rax+00h]
0x140106bf2  test    r12b, 2
0x140106bf6  jz      short loc_140106C28
0x140106bf8  cmp     r14d, 1
0x140106bfc  jnz     loc_140106AB3
0x140106c02  lea     r8, [rbp+740h+DestinationString]
0x140106c06  xor     edx, edx
0x140106c08  xor     ecx, ecx
0x140106c0a  call    VmsOmDeleteObjectRegistryKey
0x140106c0f  mov     [rsp+840h+var_7F0], eax
0x140106c13  cmp     eax, 0C0000034h
0x140106c18  jnz     short loc_140106C1E
0x140106c1a  mov     [rsp+840h+var_7F0], ebx
0x140106c1e  mov     ebx, 0Ah
0x140106c23  jmp     loc_140106AB3
0x140106c28  lea     r9, [rbp+740h+var_7C0]
0x140106c2c  xor     edx, edx
0x140106c2e  lea     r8, [rbp+740h+DestinationString]
0x140106c32  xor     ecx, ecx
0x140106c34  call    VmsOmCreateObjectRegistryKey
0x140106c39  mov     rsi, [rbp+740h+var_7C0]
0x140106c3d  xor     r12d, r12d
0x140106c40  mov     [rsp+840h+var_7F0], eax
0x140106c44  test    eax, eax
0x140106c46  jz      short loc_140106C52
0x140106c48  lea     ebx, [r12+0Fh]
0x140106c4d  jmp     loc_140106EA7
0x140106c52  lea     r8, [rbp+740h+var_798]
0x140106c56  mov     rcx, rsi
0x140106c59  lea     rdx, VmsOmSwitchNameStr
0x140106c60  call    VmsCsAttrValueWriteString
0x140106c65  mov     [rsp+840h+var_7F0], eax
0x140106c69  test    eax, eax
0x140106c6b  jz      short loc_140106C77
0x140106c6d  mov     ebx, 14h
0x140106c72  jmp     loc_140106EA7
0x140106c77  lea     r8, [rbp+740h+var_788]
0x140106c7b  mov     rcx, rsi
0x140106c7e  lea     rdx, VmsOmPortNameStr
0x140106c85  call    VmsCsAttrValueWriteString
0x140106c8a  mov     [rsp+840h+var_7F0], eax
0x140106c8e  test    eax, eax
0x140106c90  jz      short loc_140106C9C
0x140106c92  mov     ebx, 19h
0x140106c97  jmp     loc_140106EA7
0x140106c9c  mov     r8d, r14d
0x140106c9f  lea     rdx, VmsOmNicTypeStr
0x140106ca6  mov     rcx, rsi
0x140106ca9  call    VmsCsAttrValueWriteULong
0x140106cae  mov     [rsp+840h+var_7F0], eax
0x140106cb2  test    eax, eax
0x140106cb4  jz      short loc_140106CC0
0x140106cb6  mov     ebx, 1Eh
0x140106cbb  jmp     loc_140106EA7
0x140106cc0  cmp     r14d, 2
0x140106cc4  jnz     loc_140106D77
0x140106cca  cmp     [rsp+840h+var_7E0.Length], r12w
0x140106cd0  jz      short loc_140106CF7
0x140106cd2  lea     r8, [rsp+840h+var_7E0]
0x140106cd7  mov     rcx, rsi
0x140106cda  lea     rdx, VmsOmFriendlyNameStr
0x140106ce1  call    VmsCsAttrValueWriteString
0x140106ce6  mov     [rsp+840h+var_7F0], eax
0x140106cea  test    eax, eax
0x140106cec  jz      short loc_140106CF7
0x140106cee  lea     ebx, [r14+21h]
0x140106cf2  jmp     loc_140106EA7
0x140106cf7  lea     r8, [rbp+740h+P]
0x140106cfb  mov     rcx, rsi
0x140106cfe  lea     rdx, VmsOmNicVlanIDStr
0x140106d05  call    VmsCsAttrValueReadString
0x140106d0a  mov     [rsp+840h+var_7F0], eax
0x140106d0e  test    eax, eax
0x140106d10  jz      loc_140106EA7
0x140106d16  mov     rcx, [rbp+740h+SourceString]; __int64
0x140106d1a  mov     [rsp+840h+var_7F0], r12d
0x140106d1f  mov     rdx, [r13+90h]; DeviceObject
0x140106d26  call    VmsPtGetVlanIDFromNdisDeviceRegkey
0x140106d2b  mov     r14, rax
0x140106d2e  test    rax, rax
0x140106d31  jz      loc_140106EA7
0x140106d37  cmp     [rax], r12w
0x140106d3b  jz      short loc_140106D61
0x140106d3d  mov     r8, rax
0x140106d40  lea     rdx, VmsOmNicVlanIDStr
0x140106d47  mov     rcx, rsi
0x140106d4a  call    VmsCsAttrValueWriteString
0x140106d4f  mov     [rsp+840h+var_7F0], eax
0x140106d53  test    eax, eax
0x140106d55  jz      short loc_140106D61
0x140106d57  mov     ebx, 28h ; '('
0x140106d5c  jmp     loc_140106EA7
0x140106d61  xor     edx, edx; Tag
0x140106d63  mov     rcx, r14; P
0x140106d66  call    cs:__imp_ExFreePoolWithTag
0x140106d6d  nop     dword ptr [rax+rax+00h]
0x140106d72  jmp     loc_140106EA7
0x140106d77  mov     eax, 1
0x140106d7c  cmp     r14d, eax
0x140106d7f  jnz     loc_140106EA7
0x140106d85  mov     r14d, r12d
0x140106d88  test    r15, r15
0x140106d8b  jz      short loc_140106D98
0x140106d8d  cmp     [r15+3ACh], r12b
0x140106d94  cmovnz  r14d, eax
0x140106d98  lea     r8, [rbp+740h+var_778]
0x140106d9c  mov     rcx, rsi
0x140106d9f  lea     rdx, VmsOmOriginalNameStr
0x140106da6  call    VmsCsAttrValueWriteString
0x140106dab  mov     [rsp+840h+var_7F0], eax
0x140106daf  test    eax, eax
0x140106db1  jz      short loc_140106DBD
0x140106db3  mov     ebx, 32h ; '2'
0x140106db8  jmp     loc_140106EA7
0x140106dbd  lea     r8, [rsp+840h+var_7E0]
0x140106dc2  mov     rcx, rsi
0x140106dc5  lea     rdx, VmsOmFriendlyNameStr
0x140106dcc  call    VmsCsAttrValueWriteString
0x140106dd1  mov     [rsp+840h+var_7F0], eax
0x140106dd5  test    eax, eax
0x140106dd7  jz      short loc_140106DE3
0x140106dd9  mov     ebx, 37h ; '7'
0x140106dde  jmp     loc_140106EA7
0x140106de3  lea     r8, [rbp+740h+var_768]
  ... truncated ...
```
