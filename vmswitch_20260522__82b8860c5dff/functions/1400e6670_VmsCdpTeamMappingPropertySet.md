# VmsCdpTeamMappingPropertySet

- ea: `0x1400e6670`
- end: `0x1400e6d22`
- name: `VmsCdpTeamMappingPropertySet`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1400e6110`

## callees

- `0x140034ecc`
- `0x1400361dc`
- `0x14003c378`
- `0x14004f5d8`
- `0x14006b084`
- `0x1400893c8`
- `0x140089a04`
- `0x14008a258`
- `0x14008c82c`
- `0x1400e603c`
- `0x1400e6670`
- `0x1400e6e60`
- `0x1400e6f44`
- `0x1400fe6f0`
- `0x1401bbc40`
- `0x1401bbfc0`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6986`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e699d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6c40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6c57`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6986`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e699d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6c40`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6c57`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6ae8`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6cd6`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6ae8`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6cd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e68e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e68e7`
- `NDIS!NdisReleaseRWLock` at `0x1400e6a4d`
- `NDIS!NdisReleaseRWLock` at `0x1400e6ad3`
- `NDIS!NdisReleaseRWLock` at `0x1400e6b73`
- `NDIS!NdisReleaseRWLock` at `0x1400e6bd2`
- `NDIS!NdisReleaseRWLock` at `0x1400e6c99`
- `NDIS!NdisReleaseRWLock` at `0x1400e6a4d`
- `NDIS!NdisReleaseRWLock` at `0x1400e6ad3`
- `NDIS!NdisReleaseRWLock` at `0x1400e6b73`
- `NDIS!NdisReleaseRWLock` at `0x1400e6bd2`
- `NDIS!NdisReleaseRWLock` at `0x1400e6c99`

## pseudocode

```c
__int64 __fastcall VmsCdpTeamMappingPropertySet(
        __int64 a1,
        unsigned __int16 a2,
        _OWORD *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        _DWORD *a6)
{
  char v9; // r13
  int v10; // edx
  __int64 v11; // r14
  size_t v12; // rdi
  size_t v13; // r8
  NTSTATUS v14; // eax
  int v15; // edx
  int v16; // ebx
  char v17; // di
  NTSTATUS v18; // eax
  int v19; // edx
  __int64 v20; // rdx
  int v21; // ecx
  unsigned __int16 v22; // r14
  int v23; // ebx
  int v24; // edx
  size_t v25; // r8
  _OWORD *v26; // r15
  struct _NDIS_RW_LOCK_EX *v27; // rcx
  __int64 v28; // rdx
  _DWORD *v29; // rbx
  __int64 v30; // rdi
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int Timeout; // [rsp+20h] [rbp-E0h]
  char v37; // [rsp+50h] [rbp-B0h]
  struct _LOCK_STATE_EX LockState; // [rsp+54h] [rbp-ACh] BYREF
  struct _LOCK_STATE_EX v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v40; // [rsp+5Ch] [rbp-A4h]
  _OWORD *v41; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v42; // [rsp+68h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v44; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING SourceString; // [rsp+90h] [rbp-70h] BYREF
  UNICODE_STRING v46; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING v47; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v48[256]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v50[256]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v51[256]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v52[256]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v41 = a3;
  v40 = a2;
  *(_WORD *)&v39.OldIrql = 0;
  v39.Flags = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  memset(v48, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v48;
  v9 = 0;
  memset(v49, 0, 0xFEu);
  *(_QWORD *)&v44.Length = 16646144;
  v44.Buffer = (wchar_t *)v49;
  memset(v50, 0, 0xFEu);
  *(_QWORD *)&SourceString.Length = 16646144;
  SourceString.Buffer = (wchar_t *)v50;
  memset(v51, 0, 0xFEu);
  *(_QWORD *)&v46.Length = 16646144;
  v46.Buffer = (wchar_t *)v51;
  memset(v52, 0, 0xFEu);
  *(_QWORD *)&v47.Length = 16646144;
  v47.Buffer = (wchar_t *)v52;
  v11 = 0;
  *a6 = 0;
  v37 = 0;
  if ( !a4 || !a3 )
  {
    *a6 = 1;
    v16 = -1073741811;
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_qq(
      VmsIfrPortLog,
      v10,
      20,
      14,
      (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
      (char)a4,
      (char)a3);
    v17 = 10;
    goto LABEL_37;
  }
  v12 = 128;
  v13 = *a4;
  if ( *a4 >= 0x80u )
    v13 = 128;
  v42 = a4 + 1;
  v14 = RtlUnicodeStringCchCopyStringN(&DestinationString, a4 + 1, v13);
  v16 = v14;
  if ( v14 < 0 )
  {
    *a6 = 1;
    LOBYTE(v15) = 2;
    v17 = 20;
    WPP_RECORDER_SF_Sd(
      VmsIfrPortLog,
      v15,
      20,
      15,
      (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
      (__int64)v42,
      v14);
LABEL_37:
    v26 = v41;
    goto LABEL_38;
  }
  v16 = VmsUtilUpcaseUnicodeString(&SourceString, &DestinationString);
  if ( v16 < 0 )
  {
    *a6 = 1;
    v17 = 50;
    goto LABEL_37;
  }
  if ( a4[129] < 0x80u )
    v12 = a4[129];
  v42 = a4 + 130;
  v18 = RtlUnicodeStringCchCopyStringN(&v44, a4 + 130, v12);
  v16 = v18;
  if ( v18 < 0 )
  {
    *a6 = 1;
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_Sd(
      VmsIfrPortLog,
      v19,
      20,
      16,
      (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
      (__int64)v42,
      v18);
    v17 = 60;
    goto LABEL_37;
  }
  v16 = VmsUtilUpcaseUnicodeString(&v46, &v44);
  if ( v16 < 0 )
  {
    *a6 = 1;
    v17 = 70;
    goto LABEL_37;
  }
  KeWaitForSingleObject(&VmsOmIoctlMutex, Executive, 0, 0, 0);
  v37 = 1;
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  v20 = *(_QWORD *)(a1 + 1240);
  if ( !v20 || !(unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(0, v20) )
  {
    *a6 = 4;
    v16 = -1073741811;
    LOBYTE(v20) = 2;
    WPP_RECORDER_SF_I(
      VmsIfrPortLog,
      v20,
      20,
      17,
      (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
      *(_QWORD *)(a1 + 1240));
    v17 = 80;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
    goto LABEL_37;
  }
  if ( !*(_QWORD *)(a1 + 11424) || !*(_WORD *)(a1 + 11418) )
  {
    *(_DWORD *)(a1 + 11416) = 0x1000000;
    *(_QWORD *)(a1 + 11424) = a1 + 11432;
  }
  if ( !*(_QWORD *)(a1 + 11696) || !*(_WORD *)(a1 + 11690) )
  {
    *(_DWORD *)(a1 + 11688) = 0x1000000;
    *(_QWORD *)(a1 + 11696) = a1 + 11704;
  }
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11416), &SourceString);
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11688), &v46);
  v22 = v40;
  v23 = 0;
  if ( v40 >= 0x200u )
  {
    v24 = *((_DWORD *)a4 + 129);
    v23 = v24;
    if ( v24 )
    {
      if ( (unsigned __int16)*(_DWORD *)(a1 + 10536) == 3 )
      {
        v23 = 0;
        WPP_RECORDER_SF_Dq(v21, v24, 0, 18, (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids, v24, a1);
      }
    }
  }
  v25 = a5;
  *(_DWORD *)(a1 + 11964) = v23;
  if ( a5 >= 0x208 )
    v25 = 520;
  memmove((void *)(a1 + 10892), a4, v25);
  v26 = v41;
  v27 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 56);
  *(_DWORD *)(a1 + 11408) = v23;
  *(_WORD *)(a1 + 10874) = v22;
  *(_OWORD *)(a1 + 10876) = *v26;
  NdisReleaseRWLock(v27, &LockState);
  v11 = *(_QWORD *)(a1 + 1256);
  v16 = 0;
  if ( !v11 )
  {
LABEL_33:
    *(_BYTE *)(a1 + 11960) = 1;
    goto LABEL_39;
  }
  VmsOmObjectLockExclusive(*(_QWORD *)(a1 + 1256), &v39, 0);
  VmsOmNicIncrementControlCount(v11, 0, 44);
  v28 = *(_QWORD *)(v11 + 1888);
  if ( v28 && (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(0, v28) )
  {
    v29 = *(_DWORD **)(v11 + 4040);
    v30 = *(_QWORD *)(v11 + 1888);
    v9 = 1;
    VmsOmNicCopyDataUnsafe(v11, 0, v29);
    v29[1] |= 4u;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 56), &v39);
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
    v37 = 0;
    VmsOmNicSendMultipleOids(v11, v30, 0, 66196, v29, 1, 0);
    v16 = 0;
    goto LABEL_33;
  }
  *a6 = 4;
  v16 = -1073741811;
  LOBYTE(v28) = 2;
  WPP_RECORDER_SF_I(
    VmsIfrPortLog,
    v28,
    20,
    19,
    (__int64)WPP_3d3d57eee05435368a815376f6674fae_Traceguids,
    *(_QWORD *)(v11 + 1888));
  v17 = 90;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 56), &v39);
  v9 = 1;
LABEL_38:
  VmsOmObjectLockExclusive(a1, &LockState, 0);
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11416), &v47);
  RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 11688), &v47);
  memset((void *)(a1 + 10892), 0, 0x208u);
  *(_WORD *)(a1 + 10874) = 0;
  *(_OWORD *)(a1 + 10876) = 0;
  *(_BYTE *)(a1 + 11960) = 0;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 56), &LockState);
  WPP_RECORDER_SF_q_guid_LDd(v32, v31, v33, v34, Timeout, a1, (__int64)v26, *a6, v17, v16);
LABEL_39:
  if ( v37 )
    KeReleaseMutex(&VmsOmIoctlMutex, 0);
  if ( v9 )
    VmsOmNicDecrementControlCount(v11, 0, 44);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400e6670  mov     [rsp-8+arg_8], rbx
0x1400e6675  push    rbp
0x1400e6676  push    rsi
0x1400e6677  push    rdi
0x1400e6678  push    r12
0x1400e667a  push    r13
0x1400e667c  push    r14
0x1400e667e  push    r15
0x1400e6680  lea     rbp, [rsp-4D0h]
0x1400e6688  sub     rsp, 5D0h
0x1400e668f  mov     rax, cs:__security_cookie
0x1400e6696  xor     rax, rsp
0x1400e6699  mov     [rbp+500h+var_40], rax
0x1400e66a0  mov     r12, [rbp+500h+arg_28]
0x1400e66a7  xor     eax, eax
0x1400e66a9  mov     rdi, r8
0x1400e66ac  mov     [rsp+600h+var_5A0], r8
0x1400e66b1  mov     [rsp+600h+var_5A4], dx
0x1400e66b6  mov     rsi, rcx
0x1400e66b9  mov     ebx, 0FEh
0x1400e66be  mov     word ptr [rsp+600h+var_5A8.OldIrql], ax
0x1400e66c3  mov     r8d, ebx; Size
0x1400e66c6  mov     [rsp+600h+var_5A8.Flags], al
0x1400e66ca  xor     edx, edx; Val
0x1400e66cc  mov     word ptr [rsp+600h+LockState.OldIrql], ax
0x1400e66d1  lea     rcx, [rbp+500h+var_540]; void *
0x1400e66d5  mov     [rsp+600h+LockState.Flags], al
0x1400e66d9  mov     r15, r9
0x1400e66dc  call    memset
0x1400e66e1  lea     rax, [rbp+500h+var_540]
0x1400e66e5  mov     qword ptr [rsp+600h+DestinationString.Length], 0FE0000h
0x1400e66ee  mov     r8d, ebx; Size
0x1400e66f1  mov     [rsp+600h+DestinationString.Buffer], rax
0x1400e66f6  xor     edx, edx; Val
0x1400e66f8  lea     rcx, [rbp+500h+var_440]; void *
0x1400e66ff  xor     r13d, r13d
0x1400e6702  call    memset
0x1400e6707  lea     rax, [rbp+500h+var_440]
0x1400e670e  mov     qword ptr [rbp+500h+var_580.Length], 0FE0000h
0x1400e6716  mov     r8d, ebx; Size
0x1400e6719  mov     [rbp+500h+var_580.Buffer], rax
0x1400e671d  xor     edx, edx; Val
0x1400e671f  lea     rcx, [rbp+500h+var_340]; void *
0x1400e6726  call    memset
0x1400e672b  lea     rax, [rbp+500h+var_340]
0x1400e6732  mov     qword ptr [rbp+500h+SourceString.Length], 0FE0000h
0x1400e673a  mov     r8d, ebx; Size
0x1400e673d  mov     [rbp+500h+SourceString.Buffer], rax
0x1400e6741  xor     edx, edx; Val
0x1400e6743  lea     rcx, [rbp+500h+var_240]; void *
0x1400e674a  call    memset
0x1400e674f  lea     rax, [rbp+500h+var_240]
0x1400e6756  mov     qword ptr [rbp+500h+var_560.Length], 0FE0000h
0x1400e675e  mov     r8d, ebx; Size
0x1400e6761  mov     [rbp+500h+var_560.Buffer], rax
0x1400e6765  xor     edx, edx; Val
0x1400e6767  lea     rcx, [rbp+500h+var_140]; void *
0x1400e676e  call    memset
0x1400e6773  mov     qword ptr [rbp+500h+var_550.Length], 0FE0000h
0x1400e677b  lea     rax, [rbp+500h+var_140]
0x1400e6782  mov     [rbp+500h+var_550.Buffer], rax
0x1400e6786  mov     r14d, r13d
0x1400e6789  mov     [r12], r13d
0x1400e678d  mov     [rsp+600h+var_5B0], r13b
0x1400e6792  test    r15, r15
0x1400e6795  jz      loc_1400E6BE0
0x1400e679b  test    rdi, rdi
0x1400e679e  jz      loc_1400E6BE0
0x1400e67a4  movzx   eax, word ptr [r15]
0x1400e67a8  lea     edi, [rbx-7Eh]
0x1400e67ab  mov     r8d, eax
0x1400e67ae  cmp     ax, di
0x1400e67b1  jb      short loc_1400E67B6
0x1400e67b3  mov     r8d, edi; cchToCopy
0x1400e67b6  lea     rax, [r15+2]
0x1400e67ba  mov     rdx, rax; pszSrc
0x1400e67bd  mov     [rsp+600h+var_598], rax
0x1400e67c2  lea     rcx, [rsp+600h+DestinationString]; DestinationString
0x1400e67c7  call    RtlUnicodeStringCchCopyStringN
0x1400e67cc  mov     ebx, eax
0x1400e67ce  test    eax, eax
0x1400e67d0  jns     short loc_1400E6814
0x1400e67d2  mov     dword ptr [r12], 1
0x1400e67da  mov     rcx, cs:VmsIfrPortLog
0x1400e67e1  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e67e8  mov     dword ptr [rsp+600h+var_5D0], eax
0x1400e67ec  mov     r9d, 0Fh
0x1400e67f2  mov     rax, [rsp+600h+var_598]
0x1400e67f7  mov     dl, 2
0x1400e67f9  mov     [rsp+600h+var_5D8], rax
0x1400e67fe  mov     [rsp+600h+Timeout], rdi
0x1400e6803  lea     edi, [r9+5]
0x1400e6807  mov     r8d, edi
0x1400e680a  call    WPP_RECORDER_SF_Sd
0x1400e680f  jmp     loc_1400E6C20
0x1400e6814  lea     rdx, [rsp+600h+DestinationString]
0x1400e6819  lea     rcx, [rbp+500h+SourceString]
0x1400e681d  call    VmsUtilUpcaseUnicodeString
0x1400e6822  mov     ebx, eax
0x1400e6824  xor     eax, eax
0x1400e6826  test    ebx, ebx
0x1400e6828  jns     short loc_1400E683A
0x1400e682a  mov     dword ptr [r12], 1
0x1400e6832  lea     edi, [rax+32h]
0x1400e6835  jmp     loc_1400E6C20
0x1400e683a  movzx   eax, word ptr [r15+102h]
0x1400e6842  cmp     ax, di
0x1400e6845  jnb     short loc_1400E6849
0x1400e6847  mov     edi, eax
0x1400e6849  lea     rax, [r15+104h]
0x1400e6850  mov     r8, rdi; cchToCopy
0x1400e6853  mov     rdx, rax; pszSrc
0x1400e6856  mov     [rsp+600h+var_598], rax
0x1400e685b  lea     rcx, [rbp+500h+var_580]; DestinationString
0x1400e685f  call    RtlUnicodeStringCchCopyStringN
0x1400e6864  xor     edi, edi
0x1400e6866  mov     ebx, eax
0x1400e6868  test    eax, eax
0x1400e686a  jns     short loc_1400E68AE
0x1400e686c  mov     dword ptr [r12], 1
0x1400e6874  mov     rcx, cs:VmsIfrPortLog
0x1400e687b  lea     r9d, [rdi+10h]
0x1400e687f  mov     dword ptr [rsp+600h+var_5D0], eax
0x1400e6883  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e688a  mov     rax, [rsp+600h+var_598]
0x1400e688f  lea     r8d, [r9+4]
0x1400e6893  mov     [rsp+600h+var_5D8], rax
0x1400e6898  mov     dl, 2
0x1400e689a  mov     [rsp+600h+Timeout], rdi
0x1400e689f  call    WPP_RECORDER_SF_Sd
0x1400e68a4  mov     edi, 3Ch ; '<'
0x1400e68a9  jmp     loc_1400E6C20
0x1400e68ae  lea     rdx, [rbp+500h+var_580]
0x1400e68b2  lea     rcx, [rbp+500h+var_560]
0x1400e68b6  call    VmsUtilUpcaseUnicodeString
0x1400e68bb  mov     ebx, eax
0x1400e68bd  test    eax, eax
0x1400e68bf  jns     short loc_1400E68D3
0x1400e68c1  mov     dword ptr [r12], 1
0x1400e68c9  mov     edi, 46h ; 'F'
0x1400e68ce  jmp     loc_1400E6C20
0x1400e68d3  xor     r9d, r9d; Alertable
0x1400e68d6  mov     [rsp+600h+Timeout], rdi; Timeout
0x1400e68db  xor     r8d, r8d; WaitMode
0x1400e68de  lea     rcx, VmsOmIoctlMutex; Object
0x1400e68e5  xor     edx, edx; WaitReason
0x1400e68e7  call    cs:__imp_KeWaitForSingleObject
0x1400e68ee  nop     dword ptr [rax+rax+00h]
0x1400e68f3  xor     r8d, r8d
0x1400e68f6  mov     [rsp+600h+var_5B0], 1
0x1400e68fb  lea     rdx, [rsp+600h+LockState]
0x1400e6900  mov     rcx, rsi
0x1400e6903  call    VmsOmObjectLockExclusive
0x1400e6908  mov     rdx, [rsi+4D8h]
0x1400e690f  test    rdx, rdx
0x1400e6912  jz      loc_1400E6B87
0x1400e6918  xor     ecx, ecx
0x1400e691a  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e691f  test    al, al
0x1400e6921  jz      loc_1400E6B87
0x1400e6927  cmp     [rsi+2CA0h], rdi
0x1400e692e  jz      short loc_1400E6939
0x1400e6930  cmp     [rsi+2C9Ah], di
0x1400e6937  jnz     short loc_1400E6951
0x1400e6939  lea     rax, [rsi+2CA8h]
0x1400e6940  mov     dword ptr [rsi+2C98h], 1000000h
0x1400e694a  mov     [rsi+2CA0h], rax
0x1400e6951  cmp     [rsi+2DB0h], rdi
0x1400e6958  jz      short loc_1400E6963
0x1400e695a  cmp     [rsi+2DAAh], di
0x1400e6961  jnz     short loc_1400E697B
0x1400e6963  lea     rax, [rsi+2DB8h]
0x1400e696a  mov     dword ptr [rsi+2DA8h], 1000000h
0x1400e6974  mov     [rsi+2DB0h], rax
0x1400e697b  lea     rcx, [rsi+2C98h]; DestinationString
0x1400e6982  lea     rdx, [rbp+500h+SourceString]; SourceString
0x1400e6986  call    cs:__imp_RtlCopyUnicodeString
0x1400e698d  nop     dword ptr [rax+rax+00h]
0x1400e6992  lea     rcx, [rsi+2DA8h]; DestinationString
0x1400e6999  lea     rdx, [rbp+500h+var_560]; SourceString
0x1400e699d  call    cs:__imp_RtlCopyUnicodeString
0x1400e69a4  nop     dword ptr [rax+rax+00h]
0x1400e69a9  movzx   r14d, [rsp+600h+var_5A4]
0x1400e69af  mov     eax, 200h
0x1400e69b4  mov     ebx, edi
0x1400e69b6  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e69bd  cmp     r14w, ax
0x1400e69c1  jb      short loc_1400E69F9
0x1400e69c3  mov     edx, [r15+204h]
0x1400e69ca  xor     r8d, r8d
0x1400e69cd  mov     ebx, edx
0x1400e69cf  test    edx, edx
0x1400e69d1  jz      short loc_1400E69F9
0x1400e69d3  mov     eax, [rsi+2928h]
0x1400e69d9  cmp     ax, 3
0x1400e69dd  jnz     short loc_1400E69F9
0x1400e69df  mov     ebx, r8d
0x1400e69e2  mov     [rsp+600h+var_5D0], rsi
0x1400e69e7  lea     r9d, [r8+12h]
0x1400e69eb  mov     dword ptr [rsp+600h+var_5D8], edx
0x1400e69ef  mov     [rsp+600h+Timeout], rdi
0x1400e69f4  call    WPP_RECORDER_SF_Dq
0x1400e69f9  mov     r8d, [rbp+500h+arg_20]
0x1400e6a00  mov     eax, 208h
0x1400e6a05  mov     [rsi+2EBCh], ebx
0x1400e6a0b  cmp     [rbp+500h+arg_20], eax
0x1400e6a11  jb      short loc_1400E6A16
0x1400e6a13  mov     r8d, eax; Size
0x1400e6a16  lea     rcx, [rsi+2A8Ch]; void *
0x1400e6a1d  mov     rdx, r15; Src
0x1400e6a20  call    memmove
0x1400e6a25  mov     r15, [rsp+600h+var_5A0]
0x1400e6a2a  lea     rdx, [rsp+600h+LockState]; LockState
0x1400e6a2f  mov     rcx, [rsi+38h]; Lock
0x1400e6a33  mov     [rsi+2C90h], ebx
0x1400e6a39  mov     [rsi+2A7Ah], r14w
0x1400e6a41  movups  xmm0, xmmword ptr [r15]
0x1400e6a45  movdqu  xmmword ptr [rsi+2A7Ch], xmm0
0x1400e6a4d  call    cs:__imp_NdisReleaseRWLock
0x1400e6a54  nop     dword ptr [rax+rax+00h]
0x1400e6a59  mov     r14, [rsi+4E8h]
0x1400e6a60  xor     ebx, ebx
0x1400e6a62  test    r14, r14
0x1400e6a65  jz      loc_1400E6B23
0x1400e6a6b  xor     r8d, r8d
0x1400e6a6e  lea     rdx, [rsp+600h+var_5A8]
0x1400e6a73  mov     rcx, r14
0x1400e6a76  call    VmsOmObjectLockExclusive
0x1400e6a7b  xor     edx, edx
0x1400e6a7d  lea     r8d, [rbx+2Ch]
0x1400e6a81  mov     rcx, r14
0x1400e6a84  call    VmsOmNicIncrementControlCount
0x1400e6a89  mov     rdx, [r14+760h]
0x1400e6a90  test    rdx, rdx
0x1400e6a93  jz      loc_1400E6B2F
0x1400e6a99  xor     ecx, ecx
0x1400e6a9b  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e6aa0  test    al, al
0x1400e6aa2  jz      loc_1400E6B2F
0x1400e6aa8  mov     rbx, [r14+0FC8h]
0x1400e6aaf  xor     edx, edx
0x1400e6ab1  mov     rdi, [r14+760h]
0x1400e6ab8  mov     r8, rbx
0x1400e6abb  mov     rcx, r14
0x1400e6abe  mov     r13b, 1
0x1400e6ac1  call    VmsOmNicCopyDataUnsafe
0x1400e6ac6  or      dword ptr [rbx+4], 4
0x1400e6aca  lea     rdx, [rsp+600h+var_5A8]; LockState
0x1400e6acf  mov     rcx, [r14+38h]; Lock
0x1400e6ad3  call    cs:__imp_NdisReleaseRWLock
0x1400e6ada  nop     dword ptr [rax+rax+00h]
0x1400e6adf  xor     edx, edx; Wait
0x1400e6ae1  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e6ae8  call    cs:__imp_KeReleaseMutex
0x1400e6aef  nop     dword ptr [rax+rax+00h]
0x1400e6af4  xor     eax, eax
0x1400e6af6  mov     r9d, 10294h; int
0x1400e6afc  mov     [rsp+600h+var_5D0], rax; __int64
0x1400e6b01  xor     r8d, r8d; int
0x1400e6b04  mov     [rsp+600h+var_5D8], 1; __int64
0x1400e6b0d  mov     rdx, rdi; int
0x1400e6b10  mov     rcx, r14; int
0x1400e6b13  mov     [rsp+600h+Timeout], rbx; Src
0x1400e6b18  mov     [rsp+600h+var_5B0], al
0x1400e6b1c  call    VmsOmNicSendMultipleOids
0x1400e6b21  xor     ebx, ebx
0x1400e6b23  mov     byte ptr [rsi+2EB8h], 1
0x1400e6b2a  jmp     loc_1400E6CC4
0x1400e6b2f  mov     dword ptr [r12], 4
0x1400e6b37  mov     ebx, 0C000000Dh
0x1400e6b3c  mov     rax, [r14+760h]
0x1400e6b43  mov     r9d, 13h
0x1400e6b49  mov     rcx, cs:VmsIfrPortLog
0x1400e6b50  mov     dl, 2
0x1400e6b52  mov     [rsp+600h+var_5D8], rax
0x1400e6b57  mov     [rsp+600h+Timeout], rdi
0x1400e6b5c  lea     r8d, [r9+1]
0x1400e6b60  call    WPP_RECORDER_SF_I
0x1400e6b65  mov     rcx, [r14+38h]; Lock
0x1400e6b69  lea     rdx, [rsp+600h+var_5A8]; LockState
0x1400e6b6e  mov     edi, 5Ah ; 'Z'
0x1400e6b73  call    cs:__imp_NdisReleaseRWLock
0x1400e6b7a  nop     dword ptr [rax+rax+00h]
0x1400e6b7f  mov     r13b, 1
0x1400e6b82  jmp     loc_1400E6C25
0x1400e6b87  mov     dword ptr [r12], 4
0x1400e6b8f  mov     ebx, 0C000000Dh
0x1400e6b94  mov     rax, [rsi+4D8h]
0x1400e6b9b  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6ba2  mov     rcx, cs:VmsIfrPortLog
0x1400e6ba9  mov     r9d, 11h
0x1400e6baf  mov     [rsp+600h+var_5D8], rax
0x1400e6bb4  mov     dl, 2
0x1400e6bb6  mov     [rsp+600h+Timeout], rdi
0x1400e6bbb  lea     r8d, [r9+3]
0x1400e6bbf  call    WPP_RECORDER_SF_I
0x1400e6bc4  mov     rcx, [rsi+38h]; Lock
0x1400e6bc8  lea     rdx, [rsp+600h+LockState]; LockState
0x1400e6bcd  mov     edi, 50h ; 'P'
0x1400e6bd2  call    cs:__imp_NdisReleaseRWLock
  ... truncated ...
```
