# VmsCdpTeamMappingPropertySet

- ea: `0x1400e66e0`
- end: `0x1400e6d92`
- name: `VmsCdpTeamMappingPropertySet`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x1400e6180`

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
- `0x1400e60ac`
- `0x1400e66e0`
- `0x1400e6ed0`
- `0x1400e6fb4`
- `0x1400fe760`
- `0x1401bbcb0`
- `0x1401bc040`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e69f6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6a0d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6cb0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6cc7`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e69f6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6a0d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6cb0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e6cc7`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6b58`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6d46`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6b58`
- `ntoskrnl!KeReleaseMutex` at `0x1400e6d46`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6957`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400e6957`
- `NDIS!NdisReleaseRWLock` at `0x1400e6abd`
- `NDIS!NdisReleaseRWLock` at `0x1400e6b43`
- `NDIS!NdisReleaseRWLock` at `0x1400e6be3`
- `NDIS!NdisReleaseRWLock` at `0x1400e6c42`
- `NDIS!NdisReleaseRWLock` at `0x1400e6d09`
- `NDIS!NdisReleaseRWLock` at `0x1400e6abd`
- `NDIS!NdisReleaseRWLock` at `0x1400e6b43`
- `NDIS!NdisReleaseRWLock` at `0x1400e6be3`
- `NDIS!NdisReleaseRWLock` at `0x1400e6c42`
- `NDIS!NdisReleaseRWLock` at `0x1400e6d09`

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
0x1400e66e0  mov     [rsp-8+arg_8], rbx
0x1400e66e5  push    rbp
0x1400e66e6  push    rsi
0x1400e66e7  push    rdi
0x1400e66e8  push    r12
0x1400e66ea  push    r13
0x1400e66ec  push    r14
0x1400e66ee  push    r15
0x1400e66f0  lea     rbp, [rsp-4D0h]
0x1400e66f8  sub     rsp, 5D0h
0x1400e66ff  mov     rax, cs:__security_cookie
0x1400e6706  xor     rax, rsp
0x1400e6709  mov     [rbp+500h+var_40], rax
0x1400e6710  mov     r12, [rbp+500h+arg_28]
0x1400e6717  xor     eax, eax
0x1400e6719  mov     rdi, r8
0x1400e671c  mov     [rsp+600h+var_5A0], r8
0x1400e6721  mov     [rsp+600h+var_5A4], dx
0x1400e6726  mov     rsi, rcx
0x1400e6729  mov     ebx, 0FEh
0x1400e672e  mov     word ptr [rsp+600h+var_5A8.OldIrql], ax
0x1400e6733  mov     r8d, ebx; Size
0x1400e6736  mov     [rsp+600h+var_5A8.Flags], al
0x1400e673a  xor     edx, edx; Val
0x1400e673c  mov     word ptr [rsp+600h+LockState.OldIrql], ax
0x1400e6741  lea     rcx, [rbp+500h+var_540]; void *
0x1400e6745  mov     [rsp+600h+LockState.Flags], al
0x1400e6749  mov     r15, r9
0x1400e674c  call    memset
0x1400e6751  lea     rax, [rbp+500h+var_540]
0x1400e6755  mov     qword ptr [rsp+600h+DestinationString.Length], 0FE0000h
0x1400e675e  mov     r8d, ebx; Size
0x1400e6761  mov     [rsp+600h+DestinationString.Buffer], rax
0x1400e6766  xor     edx, edx; Val
0x1400e6768  lea     rcx, [rbp+500h+var_440]; void *
0x1400e676f  xor     r13d, r13d
0x1400e6772  call    memset
0x1400e6777  lea     rax, [rbp+500h+var_440]
0x1400e677e  mov     qword ptr [rbp+500h+var_580.Length], 0FE0000h
0x1400e6786  mov     r8d, ebx; Size
0x1400e6789  mov     [rbp+500h+var_580.Buffer], rax
0x1400e678d  xor     edx, edx; Val
0x1400e678f  lea     rcx, [rbp+500h+var_340]; void *
0x1400e6796  call    memset
0x1400e679b  lea     rax, [rbp+500h+var_340]
0x1400e67a2  mov     qword ptr [rbp+500h+SourceString.Length], 0FE0000h
0x1400e67aa  mov     r8d, ebx; Size
0x1400e67ad  mov     [rbp+500h+SourceString.Buffer], rax
0x1400e67b1  xor     edx, edx; Val
0x1400e67b3  lea     rcx, [rbp+500h+var_240]; void *
0x1400e67ba  call    memset
0x1400e67bf  lea     rax, [rbp+500h+var_240]
0x1400e67c6  mov     qword ptr [rbp+500h+var_560.Length], 0FE0000h
0x1400e67ce  mov     r8d, ebx; Size
0x1400e67d1  mov     [rbp+500h+var_560.Buffer], rax
0x1400e67d5  xor     edx, edx; Val
0x1400e67d7  lea     rcx, [rbp+500h+var_140]; void *
0x1400e67de  call    memset
0x1400e67e3  mov     qword ptr [rbp+500h+var_550.Length], 0FE0000h
0x1400e67eb  lea     rax, [rbp+500h+var_140]
0x1400e67f2  mov     [rbp+500h+var_550.Buffer], rax
0x1400e67f6  mov     r14d, r13d
0x1400e67f9  mov     [r12], r13d
0x1400e67fd  mov     [rsp+600h+var_5B0], r13b
0x1400e6802  test    r15, r15
0x1400e6805  jz      loc_1400E6C50
0x1400e680b  test    rdi, rdi
0x1400e680e  jz      loc_1400E6C50
0x1400e6814  movzx   eax, word ptr [r15]
0x1400e6818  lea     edi, [rbx-7Eh]
0x1400e681b  mov     r8d, eax
0x1400e681e  cmp     ax, di
0x1400e6821  jb      short loc_1400E6826
0x1400e6823  mov     r8d, edi; cchToCopy
0x1400e6826  lea     rax, [r15+2]
0x1400e682a  mov     rdx, rax; pszSrc
0x1400e682d  mov     [rsp+600h+var_598], rax
0x1400e6832  lea     rcx, [rsp+600h+DestinationString]; DestinationString
0x1400e6837  call    RtlUnicodeStringCchCopyStringN
0x1400e683c  mov     ebx, eax
0x1400e683e  test    eax, eax
0x1400e6840  jns     short loc_1400E6884
0x1400e6842  mov     dword ptr [r12], 1
0x1400e684a  mov     rcx, cs:VmsIfrPortLog
0x1400e6851  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6858  mov     dword ptr [rsp+600h+var_5D0], eax
0x1400e685c  mov     r9d, 0Fh
0x1400e6862  mov     rax, [rsp+600h+var_598]
0x1400e6867  mov     dl, 2
0x1400e6869  mov     [rsp+600h+var_5D8], rax
0x1400e686e  mov     [rsp+600h+Timeout], rdi
0x1400e6873  lea     edi, [r9+5]
0x1400e6877  mov     r8d, edi
0x1400e687a  call    WPP_RECORDER_SF_Sd
0x1400e687f  jmp     loc_1400E6C90
0x1400e6884  lea     rdx, [rsp+600h+DestinationString]
0x1400e6889  lea     rcx, [rbp+500h+SourceString]
0x1400e688d  call    VmsUtilUpcaseUnicodeString
0x1400e6892  mov     ebx, eax
0x1400e6894  xor     eax, eax
0x1400e6896  test    ebx, ebx
0x1400e6898  jns     short loc_1400E68AA
0x1400e689a  mov     dword ptr [r12], 1
0x1400e68a2  lea     edi, [rax+32h]
0x1400e68a5  jmp     loc_1400E6C90
0x1400e68aa  movzx   eax, word ptr [r15+102h]
0x1400e68b2  cmp     ax, di
0x1400e68b5  jnb     short loc_1400E68B9
0x1400e68b7  mov     edi, eax
0x1400e68b9  lea     rax, [r15+104h]
0x1400e68c0  mov     r8, rdi; cchToCopy
0x1400e68c3  mov     rdx, rax; pszSrc
0x1400e68c6  mov     [rsp+600h+var_598], rax
0x1400e68cb  lea     rcx, [rbp+500h+var_580]; DestinationString
0x1400e68cf  call    RtlUnicodeStringCchCopyStringN
0x1400e68d4  xor     edi, edi
0x1400e68d6  mov     ebx, eax
0x1400e68d8  test    eax, eax
0x1400e68da  jns     short loc_1400E691E
0x1400e68dc  mov     dword ptr [r12], 1
0x1400e68e4  mov     rcx, cs:VmsIfrPortLog
0x1400e68eb  lea     r9d, [rdi+10h]
0x1400e68ef  mov     dword ptr [rsp+600h+var_5D0], eax
0x1400e68f3  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e68fa  mov     rax, [rsp+600h+var_598]
0x1400e68ff  lea     r8d, [r9+4]
0x1400e6903  mov     [rsp+600h+var_5D8], rax
0x1400e6908  mov     dl, 2
0x1400e690a  mov     [rsp+600h+Timeout], rdi
0x1400e690f  call    WPP_RECORDER_SF_Sd
0x1400e6914  mov     edi, 3Ch ; '<'
0x1400e6919  jmp     loc_1400E6C90
0x1400e691e  lea     rdx, [rbp+500h+var_580]
0x1400e6922  lea     rcx, [rbp+500h+var_560]
0x1400e6926  call    VmsUtilUpcaseUnicodeString
0x1400e692b  mov     ebx, eax
0x1400e692d  test    eax, eax
0x1400e692f  jns     short loc_1400E6943
0x1400e6931  mov     dword ptr [r12], 1
0x1400e6939  mov     edi, 46h ; 'F'
0x1400e693e  jmp     loc_1400E6C90
0x1400e6943  xor     r9d, r9d; Alertable
0x1400e6946  mov     [rsp+600h+Timeout], rdi; Timeout
0x1400e694b  xor     r8d, r8d; WaitMode
0x1400e694e  lea     rcx, VmsOmIoctlMutex; Object
0x1400e6955  xor     edx, edx; WaitReason
0x1400e6957  call    cs:__imp_KeWaitForSingleObject
0x1400e695e  nop     dword ptr [rax+rax+00h]
0x1400e6963  xor     r8d, r8d
0x1400e6966  mov     [rsp+600h+var_5B0], 1
0x1400e696b  lea     rdx, [rsp+600h+LockState]
0x1400e6970  mov     rcx, rsi
0x1400e6973  call    VmsOmObjectLockExclusive
0x1400e6978  mov     rdx, [rsi+4D8h]
0x1400e697f  test    rdx, rdx
0x1400e6982  jz      loc_1400E6BF7
0x1400e6988  xor     ecx, ecx
0x1400e698a  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e698f  test    al, al
0x1400e6991  jz      loc_1400E6BF7
0x1400e6997  cmp     [rsi+2CA0h], rdi
0x1400e699e  jz      short loc_1400E69A9
0x1400e69a0  cmp     [rsi+2C9Ah], di
0x1400e69a7  jnz     short loc_1400E69C1
0x1400e69a9  lea     rax, [rsi+2CA8h]
0x1400e69b0  mov     dword ptr [rsi+2C98h], 1000000h
0x1400e69ba  mov     [rsi+2CA0h], rax
0x1400e69c1  cmp     [rsi+2DB0h], rdi
0x1400e69c8  jz      short loc_1400E69D3
0x1400e69ca  cmp     [rsi+2DAAh], di
0x1400e69d1  jnz     short loc_1400E69EB
0x1400e69d3  lea     rax, [rsi+2DB8h]
0x1400e69da  mov     dword ptr [rsi+2DA8h], 1000000h
0x1400e69e4  mov     [rsi+2DB0h], rax
0x1400e69eb  lea     rcx, [rsi+2C98h]; DestinationString
0x1400e69f2  lea     rdx, [rbp+500h+SourceString]; SourceString
0x1400e69f6  call    cs:__imp_RtlCopyUnicodeString
0x1400e69fd  nop     dword ptr [rax+rax+00h]
0x1400e6a02  lea     rcx, [rsi+2DA8h]; DestinationString
0x1400e6a09  lea     rdx, [rbp+500h+var_560]; SourceString
0x1400e6a0d  call    cs:__imp_RtlCopyUnicodeString
0x1400e6a14  nop     dword ptr [rax+rax+00h]
0x1400e6a19  movzx   r14d, [rsp+600h+var_5A4]
0x1400e6a1f  mov     eax, 200h
0x1400e6a24  mov     ebx, edi
0x1400e6a26  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6a2d  cmp     r14w, ax
0x1400e6a31  jb      short loc_1400E6A69
0x1400e6a33  mov     edx, [r15+204h]
0x1400e6a3a  xor     r8d, r8d
0x1400e6a3d  mov     ebx, edx
0x1400e6a3f  test    edx, edx
0x1400e6a41  jz      short loc_1400E6A69
0x1400e6a43  mov     eax, [rsi+2928h]
0x1400e6a49  cmp     ax, 3
0x1400e6a4d  jnz     short loc_1400E6A69
0x1400e6a4f  mov     ebx, r8d
0x1400e6a52  mov     [rsp+600h+var_5D0], rsi
0x1400e6a57  lea     r9d, [r8+12h]
0x1400e6a5b  mov     dword ptr [rsp+600h+var_5D8], edx
0x1400e6a5f  mov     [rsp+600h+Timeout], rdi
0x1400e6a64  call    WPP_RECORDER_SF_Dq
0x1400e6a69  mov     r8d, [rbp+500h+arg_20]
0x1400e6a70  mov     eax, 208h
0x1400e6a75  mov     [rsi+2EBCh], ebx
0x1400e6a7b  cmp     [rbp+500h+arg_20], eax
0x1400e6a81  jb      short loc_1400E6A86
0x1400e6a83  mov     r8d, eax; Size
0x1400e6a86  lea     rcx, [rsi+2A8Ch]; void *
0x1400e6a8d  mov     rdx, r15; Src
0x1400e6a90  call    memmove
0x1400e6a95  mov     r15, [rsp+600h+var_5A0]
0x1400e6a9a  lea     rdx, [rsp+600h+LockState]; LockState
0x1400e6a9f  mov     rcx, [rsi+38h]; Lock
0x1400e6aa3  mov     [rsi+2C90h], ebx
0x1400e6aa9  mov     [rsi+2A7Ah], r14w
0x1400e6ab1  movups  xmm0, xmmword ptr [r15]
0x1400e6ab5  movdqu  xmmword ptr [rsi+2A7Ch], xmm0
0x1400e6abd  call    cs:__imp_NdisReleaseRWLock
0x1400e6ac4  nop     dword ptr [rax+rax+00h]
0x1400e6ac9  mov     r14, [rsi+4E8h]
0x1400e6ad0  xor     ebx, ebx
0x1400e6ad2  test    r14, r14
0x1400e6ad5  jz      loc_1400E6B93
0x1400e6adb  xor     r8d, r8d
0x1400e6ade  lea     rdx, [rsp+600h+var_5A8]
0x1400e6ae3  mov     rcx, r14
0x1400e6ae6  call    VmsOmObjectLockExclusive
0x1400e6aeb  xor     edx, edx
0x1400e6aed  lea     r8d, [rbx+2Ch]
0x1400e6af1  mov     rcx, r14
0x1400e6af4  call    VmsOmNicIncrementControlCount
0x1400e6af9  mov     rdx, [r14+760h]
0x1400e6b00  test    rdx, rdx
0x1400e6b03  jz      loc_1400E6B9F
0x1400e6b09  xor     ecx, ecx
0x1400e6b0b  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x1400e6b10  test    al, al
0x1400e6b12  jz      loc_1400E6B9F
0x1400e6b18  mov     rbx, [r14+0FC8h]
0x1400e6b1f  xor     edx, edx
0x1400e6b21  mov     rdi, [r14+760h]
0x1400e6b28  mov     r8, rbx
0x1400e6b2b  mov     rcx, r14
0x1400e6b2e  mov     r13b, 1
0x1400e6b31  call    VmsOmNicCopyDataUnsafe
0x1400e6b36  or      dword ptr [rbx+4], 4
0x1400e6b3a  lea     rdx, [rsp+600h+var_5A8]; LockState
0x1400e6b3f  mov     rcx, [r14+38h]; Lock
0x1400e6b43  call    cs:__imp_NdisReleaseRWLock
0x1400e6b4a  nop     dword ptr [rax+rax+00h]
0x1400e6b4f  xor     edx, edx; Wait
0x1400e6b51  lea     rcx, VmsOmIoctlMutex; Mutex
0x1400e6b58  call    cs:__imp_KeReleaseMutex
0x1400e6b5f  nop     dword ptr [rax+rax+00h]
0x1400e6b64  xor     eax, eax
0x1400e6b66  mov     r9d, 10294h; int
0x1400e6b6c  mov     [rsp+600h+var_5D0], rax; __int64
0x1400e6b71  xor     r8d, r8d; int
0x1400e6b74  mov     [rsp+600h+var_5D8], 1; __int64
0x1400e6b7d  mov     rdx, rdi; int
0x1400e6b80  mov     rcx, r14; int
0x1400e6b83  mov     [rsp+600h+Timeout], rbx; Src
0x1400e6b88  mov     [rsp+600h+var_5B0], al
0x1400e6b8c  call    VmsOmNicSendMultipleOids
0x1400e6b91  xor     ebx, ebx
0x1400e6b93  mov     byte ptr [rsi+2EB8h], 1
0x1400e6b9a  jmp     loc_1400E6D34
0x1400e6b9f  mov     dword ptr [r12], 4
0x1400e6ba7  mov     ebx, 0C000000Dh
0x1400e6bac  mov     rax, [r14+760h]
0x1400e6bb3  mov     r9d, 13h
0x1400e6bb9  mov     rcx, cs:VmsIfrPortLog
0x1400e6bc0  mov     dl, 2
0x1400e6bc2  mov     [rsp+600h+var_5D8], rax
0x1400e6bc7  mov     [rsp+600h+Timeout], rdi
0x1400e6bcc  lea     r8d, [r9+1]
0x1400e6bd0  call    WPP_RECORDER_SF_I
0x1400e6bd5  mov     rcx, [r14+38h]; Lock
0x1400e6bd9  lea     rdx, [rsp+600h+var_5A8]; LockState
0x1400e6bde  mov     edi, 5Ah ; 'Z'
0x1400e6be3  call    cs:__imp_NdisReleaseRWLock
0x1400e6bea  nop     dword ptr [rax+rax+00h]
0x1400e6bef  mov     r13b, 1
0x1400e6bf2  jmp     loc_1400E6C95
0x1400e6bf7  mov     dword ptr [r12], 4
0x1400e6bff  mov     ebx, 0C000000Dh
0x1400e6c04  mov     rax, [rsi+4D8h]
0x1400e6c0b  lea     rdi, WPP_3d3d57eee05435368a815376f6674fae_Traceguids
0x1400e6c12  mov     rcx, cs:VmsIfrPortLog
0x1400e6c19  mov     r9d, 11h
0x1400e6c1f  mov     [rsp+600h+var_5D8], rax
0x1400e6c24  mov     dl, 2
0x1400e6c26  mov     [rsp+600h+Timeout], rdi
0x1400e6c2b  lea     r8d, [r9+3]
0x1400e6c2f  call    WPP_RECORDER_SF_I
0x1400e6c34  mov     rcx, [rsi+38h]; Lock
0x1400e6c38  lea     rdx, [rsp+600h+LockState]; LockState
0x1400e6c3d  mov     edi, 50h ; 'P'
0x1400e6c42  call    cs:__imp_NdisReleaseRWLock
  ... truncated ...
```
