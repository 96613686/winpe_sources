# VmsOmNicStoreConfig

- ea: `0x140106848`
- end: `0x140106f30`
- name: `VmsOmNicStoreConfig`
- size: `1768`
- prototype: ``
- caller_count: `7`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007cd4c`
- `0x1400f610c`
- `0x1400ff21c`
- `0x1400ff5a8`
- `0x140102c3c`
- `0x140103530`
- `0x140117f40`

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
- `0x1400a6d5c`
- `0x1400a6dd8`
- `0x1400a6e48`
- `0x1400a6ec4`
- `0x1401058c4`
- `0x140105de8`
- `0x140106848`
- `0x1401177e4`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140106a6d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106a84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106aa7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ac1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ae7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b33`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b55`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106a6d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106a84`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106aa7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ac1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106ae7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b33`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106b55`
- `ntoskrnl!KeReleaseMutex` at `0x140106eb8`
- `ntoskrnl!KeReleaseMutex` at `0x140106eb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401069fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401069fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106ee9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140106ee9`
- `NDIS!NdisReleaseRWLock` at `0x140106b76`
- `NDIS!NdisReleaseRWLock` at `0x140106b76`

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
0x140106848  mov     [rsp-8+arg_18], rbx
0x14010684d  push    rbp
0x14010684e  push    rsi
0x14010684f  push    rdi
0x140106850  push    r12
0x140106852  push    r13
0x140106854  push    r14
0x140106856  push    r15
0x140106858  lea     rbp, [rsp-710h]
0x140106860  sub     rsp, 810h
0x140106867  mov     rax, cs:__security_cookie
0x14010686e  xor     rax, rsp
0x140106871  mov     [rbp+740h+var_40], rax
0x140106878  xor     r12d, r12d
0x14010687b  mov     [rsp+840h+var_7D0], r8d
0x140106880  xor     eax, eax
0x140106882  mov     [rbp+740h+SourceString], rdx
0x140106886  mov     r15, rdx
0x140106889  mov     [rsp+840h+var_7F0], r12d
0x14010688e  mov     rdi, rcx
0x140106891  mov     [rbp+740h+var_7C0], r12
0x140106895  mov     r14d, 0FEh
0x14010689b  mov     [rbp+740h+var_758], r12d
0x14010689f  mov     r8d, r14d; Size
0x1401068a2  mov     [rbp+740h+var_754], r12w
0x1401068a7  xor     edx, edx; Val
0x1401068a9  mov     [rbp+740h+var_750], r12d
0x1401068ad  lea     rcx, [rbp+740h+var_740]; void *
0x1401068b1  mov     [rbp+740h+var_74C], r12w
0x1401068b6  mov     esi, r12d
0x1401068b9  mov     word ptr [rsp+840h+LockState.OldIrql], ax
0x1401068be  mov     [rsp+840h+LockState.Flags], al
0x1401068c2  mov     r13d, r12d
0x1401068c5  mov     [rbp+740h+P], r12
0x1401068c9  mov     [rsp+840h+var_7C8], r12
0x1401068ce  mov     [rsp+840h+var_7EC], r12b
0x1401068d3  call    memset
0x1401068d8  lea     rax, [rbp+740h+var_740]
0x1401068dc  mov     qword ptr [rbp+740h+DestinationString.Length], 0FE0000h
0x1401068e4  mov     r8d, r14d; Size
0x1401068e7  mov     [rbp+740h+DestinationString.Buffer], rax
0x1401068eb  xor     edx, edx; Val
0x1401068ed  lea     rcx, [rbp+740h+var_640]; void *
0x1401068f4  call    memset
0x1401068f9  lea     rax, [rbp+740h+var_640]
0x140106900  mov     qword ptr [rbp+740h+var_778.Length], 0FE0000h
0x140106908  xor     edx, edx; Val
0x14010690a  mov     [rbp+740h+var_778.Buffer], rax
0x14010690e  mov     r8d, 1FEh; Size
0x140106914  lea     rcx, [rbp+740h+var_240]; void *
0x14010691b  call    memset
0x140106920  lea     rax, [rbp+740h+var_240]
0x140106927  mov     qword ptr [rsp+840h+var_7E0.Length], 1FE0000h
0x140106930  mov     r8d, r14d; Size
0x140106933  mov     [rsp+840h+var_7E0.Buffer], rax
0x140106938  xor     edx, edx; Val
0x14010693a  lea     rcx, [rbp+740h+var_540]; void *
0x140106941  call    memset
0x140106946  lea     rax, [rbp+740h+var_540]
0x14010694d  mov     qword ptr [rbp+740h+var_768.Length], 0FE0000h
0x140106955  mov     r8d, r14d; Size
0x140106958  mov     [rbp+740h+var_768.Buffer], rax
0x14010695c  xor     edx, edx; Val
0x14010695e  lea     rcx, [rbp+740h+var_440]; void *
0x140106965  call    memset
0x14010696a  lea     rax, [rbp+740h+var_440]
0x140106971  mov     qword ptr [rbp+740h+var_798.Length], 0FE0000h
0x140106979  mov     r8d, r14d; Size
0x14010697c  mov     [rbp+740h+var_798.Buffer], rax
0x140106980  xor     edx, edx; Val
0x140106982  lea     rcx, [rbp+740h+var_340]; void *
0x140106989  call    memset
0x14010698e  lea     ebx, [r12+5]
0x140106993  mov     qword ptr [rbp+740h+var_788.Length], 0FE0000h
0x14010699b  lea     rax, [rbp+740h+var_340]
0x1401069a2  lea     rcx, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x1401069a9  mov     [rbp+740h+var_788.Buffer], rax
0x1401069ad  cmp     [rdi+750h], ebx
0x1401069b3  jnz     short loc_1401069E9
0x1401069b5  lea     rax, aNicTypeVmsnice; "Nic->Type != VmsNicExtDefault"
0x1401069bc  mov     [rsp+840h+var_818], rax
0x1401069c1  lea     r9d, [r12+40h]
0x1401069c6  mov     [rsp+840h+Timeout], rcx
0x1401069cb  lea     r8d, [r12+13h]
0x1401069d0  mov     rcx, cs:VmsIfrLog
0x1401069d7  call    WPP_RECORDER_SF_s
0x1401069dc  cmp     [rdi+750h], ebx
0x1401069e2  jnz     short loc_1401069E9
0x1401069e4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->Type != VmsNicExtDefault")
0x1401069e9  lea     rcx, [rdi+478h]; Object
0x1401069f0  mov     [rsp+840h+Timeout], r12; Timeout
0x1401069f5  xor     r9d, r9d; Alertable
0x1401069f8  xor     r8d, r8d; WaitMode
0x1401069fb  xor     edx, edx; WaitReason
0x1401069fd  call    cs:__imp_KeWaitForSingleObject
0x140106a04  nop     dword ptr [rax+rax+00h]
0x140106a09  mov     r14d, [rdi+750h]
0x140106a10  mov     r12d, [rdi+4B0h]
0x140106a17  cmp     r14d, 2
0x140106a1b  jnz     short loc_140106A50
0x140106a1d  test    r14b, r12b
0x140106a20  jnz     short loc_140106A50
0x140106a22  lea     r9, [rsp+840h+var_7C8]
0x140106a27  mov     rdx, rdi
0x140106a2a  lea     r8d, [r14+44h]
0x140106a2e  mov     rcx, r15
0x140106a31  call    VmsPtNicMuxFindMemberAdapterByName
0x140106a36  mov     r13, [rsp+840h+var_7C8]
0x140106a3b  mov     [rsp+840h+var_7F0], eax
0x140106a3f  test    eax, eax
0x140106a41  jz      short loc_140106A4B
0x140106a43  xor     r12d, r12d
0x140106a46  jmp     loc_140106E37
0x140106a4b  mov     [rsp+840h+var_7EC], 1
0x140106a50  xor     r8d, r8d
0x140106a53  lea     rdx, [rsp+840h+LockState]
0x140106a58  mov     rcx, rdi
0x140106a5b  xor     ebx, ebx
0x140106a5d  xor     r15d, r15d
0x140106a60  call    VmsOmObjectLockExclusive
0x140106a65  mov     rdx, [rbp+740h+SourceString]; SourceString
0x140106a69  lea     rcx, [rbp+740h+DestinationString]; DestinationString
0x140106a6d  call    cs:__imp_RtlCopyUnicodeString
0x140106a74  nop     dword ptr [rax+rax+00h]
0x140106a79  lea     rdx, [rdi+158h]; SourceString
0x140106a80  lea     rcx, [rbp+740h+var_778]; DestinationString
0x140106a84  call    cs:__imp_RtlCopyUnicodeString
0x140106a8b  nop     dword ptr [rax+rax+00h]
0x140106a90  cmp     r14d, 2
0x140106a94  jnz     short loc_140106AB5
0x140106a96  test    r13, r13
0x140106a99  jz      short loc_140106AB5
0x140106a9b  lea     rdx, [r13+990h]; SourceString
0x140106aa2  lea     rcx, [rsp+840h+var_7E0]; DestinationString
0x140106aa7  call    cs:__imp_RtlCopyUnicodeString
0x140106aae  nop     dword ptr [rax+rax+00h]
0x140106ab3  jmp     short loc_140106B1B
0x140106ab5  lea     rdx, [rdi+268h]; SourceString
0x140106abc  lea     rcx, [rsp+840h+var_7E0]; DestinationString
0x140106ac1  call    cs:__imp_RtlCopyUnicodeString
0x140106ac8  nop     dword ptr [rax+rax+00h]
0x140106acd  cmp     r14d, 1
0x140106ad1  jnz     short loc_140106B1B
0x140106ad3  mov     r15, [rdi+0CF0h]
0x140106ada  test    r15, r15
0x140106add  jz      short loc_140106B1B
0x140106adf  lea     rdx, [r15+60h]; SourceString
0x140106ae3  lea     rcx, [rbp+740h+var_768]; DestinationString
0x140106ae7  call    cs:__imp_RtlCopyUnicodeString
0x140106aee  nop     dword ptr [rax+rax+00h]
0x140106af3  mov     eax, [rdi+838h]
0x140106af9  mov     [rbp+740h+var_750], eax
0x140106afc  movzx   eax, word ptr [rdi+83Ch]
0x140106b03  mov     [rbp+740h+var_74C], ax
0x140106b07  mov     eax, [rdi+0D08h]
0x140106b0d  mov     [rbp+740h+var_758], eax
0x140106b10  movzx   eax, word ptr [rdi+0D0Ch]
0x140106b17  mov     [rbp+740h+var_754], ax
0x140106b1b  cmp     dword ptr [rdi+758h], 1
0x140106b22  jnz     short loc_140106B61
0x140106b24  mov     rdx, [rdi+7C0h]
0x140106b2b  lea     rcx, [rbp+740h+var_788]; DestinationString
0x140106b2f  add     rdx, 48h ; 'H'; SourceString
0x140106b33  call    cs:__imp_RtlCopyUnicodeString
0x140106b3a  nop     dword ptr [rax+rax+00h]
0x140106b3f  mov     rax, [rdi+7C0h]
0x140106b46  lea     rcx, [rbp+740h+var_798]; DestinationString
0x140106b4a  mov     rdx, [rax+4D8h]
0x140106b51  add     rdx, 48h ; 'H'; SourceString
0x140106b55  call    cs:__imp_RtlCopyUnicodeString
0x140106b5c  nop     dword ptr [rax+rax+00h]
0x140106b61  mov     rcx, [rdi+38h]; Lock
0x140106b65  lea     rdx, [rsp+840h+LockState]; LockState
0x140106b6a  mov     [rdi+4B0h], ebx
0x140106b70  mov     [rdi+4B4h], bl
0x140106b76  call    cs:__imp_NdisReleaseRWLock
0x140106b7d  nop     dword ptr [rax+rax+00h]
0x140106b82  test    r12b, 2
0x140106b86  jz      short loc_140106BB8
0x140106b88  cmp     r14d, 1
0x140106b8c  jnz     loc_140106A43
0x140106b92  lea     r8, [rbp+740h+DestinationString]
0x140106b96  xor     edx, edx
0x140106b98  xor     ecx, ecx
0x140106b9a  call    VmsOmDeleteObjectRegistryKey
0x140106b9f  mov     [rsp+840h+var_7F0], eax
0x140106ba3  cmp     eax, 0C0000034h
0x140106ba8  jnz     short loc_140106BAE
0x140106baa  mov     [rsp+840h+var_7F0], ebx
0x140106bae  mov     ebx, 0Ah
0x140106bb3  jmp     loc_140106A43
0x140106bb8  lea     r9, [rbp+740h+var_7C0]
0x140106bbc  xor     edx, edx
0x140106bbe  lea     r8, [rbp+740h+DestinationString]
0x140106bc2  xor     ecx, ecx
0x140106bc4  call    VmsOmCreateObjectRegistryKey
0x140106bc9  mov     rsi, [rbp+740h+var_7C0]
0x140106bcd  xor     r12d, r12d
0x140106bd0  mov     [rsp+840h+var_7F0], eax
0x140106bd4  test    eax, eax
0x140106bd6  jz      short loc_140106BE2
0x140106bd8  lea     ebx, [r12+0Fh]
0x140106bdd  jmp     loc_140106E37
0x140106be2  lea     r8, [rbp+740h+var_798]
0x140106be6  mov     rcx, rsi
0x140106be9  lea     rdx, VmsOmSwitchNameStr
0x140106bf0  call    VmsCsAttrValueWriteString
0x140106bf5  mov     [rsp+840h+var_7F0], eax
0x140106bf9  test    eax, eax
0x140106bfb  jz      short loc_140106C07
0x140106bfd  mov     ebx, 14h
0x140106c02  jmp     loc_140106E37
0x140106c07  lea     r8, [rbp+740h+var_788]
0x140106c0b  mov     rcx, rsi
0x140106c0e  lea     rdx, VmsOmPortNameStr
0x140106c15  call    VmsCsAttrValueWriteString
0x140106c1a  mov     [rsp+840h+var_7F0], eax
0x140106c1e  test    eax, eax
0x140106c20  jz      short loc_140106C2C
0x140106c22  mov     ebx, 19h
0x140106c27  jmp     loc_140106E37
0x140106c2c  mov     r8d, r14d
0x140106c2f  lea     rdx, VmsOmNicTypeStr
0x140106c36  mov     rcx, rsi
0x140106c39  call    VmsCsAttrValueWriteULong
0x140106c3e  mov     [rsp+840h+var_7F0], eax
0x140106c42  test    eax, eax
0x140106c44  jz      short loc_140106C50
0x140106c46  mov     ebx, 1Eh
0x140106c4b  jmp     loc_140106E37
0x140106c50  cmp     r14d, 2
0x140106c54  jnz     loc_140106D07
0x140106c5a  cmp     [rsp+840h+var_7E0.Length], r12w
0x140106c60  jz      short loc_140106C87
0x140106c62  lea     r8, [rsp+840h+var_7E0]
0x140106c67  mov     rcx, rsi
0x140106c6a  lea     rdx, VmsOmFriendlyNameStr
0x140106c71  call    VmsCsAttrValueWriteString
0x140106c76  mov     [rsp+840h+var_7F0], eax
0x140106c7a  test    eax, eax
0x140106c7c  jz      short loc_140106C87
0x140106c7e  lea     ebx, [r14+21h]
0x140106c82  jmp     loc_140106E37
0x140106c87  lea     r8, [rbp+740h+P]
0x140106c8b  mov     rcx, rsi
0x140106c8e  lea     rdx, VmsOmNicVlanIDStr
0x140106c95  call    VmsCsAttrValueReadString
0x140106c9a  mov     [rsp+840h+var_7F0], eax
0x140106c9e  test    eax, eax
0x140106ca0  jz      loc_140106E37
0x140106ca6  mov     rcx, [rbp+740h+SourceString]; __int64
0x140106caa  mov     [rsp+840h+var_7F0], r12d
0x140106caf  mov     rdx, [r13+90h]; DeviceObject
0x140106cb6  call    VmsPtGetVlanIDFromNdisDeviceRegkey
0x140106cbb  mov     r14, rax
0x140106cbe  test    rax, rax
0x140106cc1  jz      loc_140106E37
0x140106cc7  cmp     [rax], r12w
0x140106ccb  jz      short loc_140106CF1
0x140106ccd  mov     r8, rax
0x140106cd0  lea     rdx, VmsOmNicVlanIDStr
0x140106cd7  mov     rcx, rsi
0x140106cda  call    VmsCsAttrValueWriteString
0x140106cdf  mov     [rsp+840h+var_7F0], eax
0x140106ce3  test    eax, eax
0x140106ce5  jz      short loc_140106CF1
0x140106ce7  mov     ebx, 28h ; '('
0x140106cec  jmp     loc_140106E37
0x140106cf1  xor     edx, edx; Tag
0x140106cf3  mov     rcx, r14; P
0x140106cf6  call    cs:__imp_ExFreePoolWithTag
0x140106cfd  nop     dword ptr [rax+rax+00h]
0x140106d02  jmp     loc_140106E37
0x140106d07  mov     eax, 1
0x140106d0c  cmp     r14d, eax
0x140106d0f  jnz     loc_140106E37
0x140106d15  mov     r14d, r12d
0x140106d18  test    r15, r15
0x140106d1b  jz      short loc_140106D28
0x140106d1d  cmp     [r15+3ACh], r12b
0x140106d24  cmovnz  r14d, eax
0x140106d28  lea     r8, [rbp+740h+var_778]
0x140106d2c  mov     rcx, rsi
0x140106d2f  lea     rdx, VmsOmOriginalNameStr
0x140106d36  call    VmsCsAttrValueWriteString
0x140106d3b  mov     [rsp+840h+var_7F0], eax
0x140106d3f  test    eax, eax
0x140106d41  jz      short loc_140106D4D
0x140106d43  mov     ebx, 32h ; '2'
0x140106d48  jmp     loc_140106E37
0x140106d4d  lea     r8, [rsp+840h+var_7E0]
0x140106d52  mov     rcx, rsi
0x140106d55  lea     rdx, VmsOmFriendlyNameStr
0x140106d5c  call    VmsCsAttrValueWriteString
0x140106d61  mov     [rsp+840h+var_7F0], eax
0x140106d65  test    eax, eax
0x140106d67  jz      short loc_140106D73
0x140106d69  mov     ebx, 37h ; '7'
0x140106d6e  jmp     loc_140106E37
0x140106d73  lea     r8, [rbp+740h+var_768]
  ... truncated ...
```
