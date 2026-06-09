# VmsPtNicMuxCreateNewMemberAdapter

- ea: `0x14013a7c0`
- end: `0x14013ab5f`
- name: `VmsPtNicMuxCreateNewMemberAdapter`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140117fb0`

## callees

- `0x14002e0f0`
- `0x14003a450`
- `0x14004f5d8`
- `0x140052460`
- `0x14006a330`
- `0x14007a074`
- `0x1400dac60`
- `0x14013a7c0`
- `0x14013e46c`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14013a9c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14013a9c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013a963`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013a963`
- `ntoskrnl!ExAllocatePool2` at `0x14013a8a3`
- `ntoskrnl!ExAllocatePool2` at `0x14013a8a3`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x14013a948`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x14013a948`
- `NDIS!NdisInitializeEvent` at `0x14013a97b`
- `NDIS!NdisInitializeEvent` at `0x14013a97b`

## pseudocode

```c
__int64 __fastcall VmsPtNicMuxCreateNewMemberAdapter(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v6; // rsi
  __int64 v8; // rbx
  char NextMemberAdapterInternal; // al
  int v10; // edx
  int v11; // r8d
  char *v12; // rbp
  __int64 v13; // rcx
  unsigned int v14; // ebx
  const UNICODE_STRING *v15; // r13
  unsigned int v16; // r12d
  __int64 Pool2; // rax
  int v18; // edx
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int WorkItem; // eax
  int v24; // edx
  unsigned int v25; // ebx
  int v27; // [rsp+20h] [rbp-88h]
  PVOID P[11]; // [rsp+50h] [rbp-58h] BYREF

  v6 = a2;
  if ( !a1 || !a2 || !a4 )
  {
    v14 = -1073741811;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_qqqd(
      VmsIfrNicLog,
      a2,
      20,
      39,
      (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
      a1,
      v6,
      (char)a4,
      13);
    if ( !a4 )
    {
LABEL_20:
      WPP_RECORDER_SF_qq_guid_qd(v20, v19, v21, v22, v27, a1, v6, (__int64)a3, (char)a4, v14);
      return v14;
    }
LABEL_19:
    *a4 = 0;
    goto LABEL_20;
  }
  v8 = *(_QWORD *)(a1 + 3312);
  if ( (unsigned __int8)VmsPtCheckIsEmbeddedTeamingEnabled(a1, 0) )
  {
    P[0] = 0;
    do
    {
      NextMemberAdapterInternal = VmsPtGetNextMemberAdapterInternal(v8, P, 0);
      v12 = (char *)P[0];
      if ( !NextMemberAdapterInternal )
        break;
      v13 = *(_QWORD *)((char *)P[0] + 124) - *a3;
      if ( !v13 )
        v13 = *(_QWORD *)((char *)P[0] + 132) - a3[1];
    }
    while ( v13 );
    if ( P[0] )
    {
      v14 = -1073676258;
      WPP_RECORDER_SF__guid_d(
        VmsIfrNicLog,
        v10,
        v11,
        40,
        (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids,
        (__int64)a3,
        30);
LABEL_16:
      ExFreePoolWithTag(v12, 0);
      goto LABEL_19;
    }
  }
  v15 = *(const UNICODE_STRING **)(v6 + 8);
  v16 = v15->MaximumLength + VmsCacheLineSizeInBytes + 4297;
  Pool2 = ExAllocatePool2(64, v16, 1349743446);
  v12 = (char *)Pool2;
  if ( !Pool2 )
  {
    v14 = -1073741670;
    LOBYTE(v18) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v18, 20, 41, (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids, v16, 154);
    goto LABEL_19;
  }
  WorkItem = NvIoAllocateWorkItem(
               *(PNPAGED_LOOKASIDE_LIST *)(a1 + 2096),
               0,
               (__int64)VmsPtNicMuxDeleteVmqGroup,
               (void *(__fastcall *)(_POOL_TYPE, unsigned __int64, unsigned int, _LOOKASIDE_LIST_EX *))Pool2,
               32,
               (volatile __int64 *)(Pool2 + 3712));
  v25 = WorkItem;
  if ( WorkItem >= 0 )
  {
    NdisInitializeEvent((PNDIS_EVENT)(v12 + 2152));
    *((_QWORD *)v12 + 1) = a1;
    *((_DWORD *)v12 + 26) = *(_DWORD *)(v6 + 160);
    *((_QWORD *)v12 + 12) = *(_QWORD *)(v6 + 152);
    *((_QWORD *)v12 + 4) = v12 + 4296;
    *((_WORD *)v12 + 13) = v15->MaximumLength;
    *((_WORD *)v12 + 12) = v15->Length;
    RtlCopyUnicodeString((PUNICODE_STRING)(v12 + 24), v15);
    *((_DWORD *)v12 + 10) = *(_DWORD *)(v6 + 106);
    *((_WORD *)v12 + 22) = *(_WORD *)(v6 + 110);
    *((_DWORD *)v12 + 21) = *(_DWORD *)(v6 + 212);
    *((_DWORD *)v12 + 20) = *(_DWORD *)(v6 + 208);
    *(_OWORD *)(v12 + 124) = *(_OWORD *)a3;
    *((_DWORD *)v12 + 30) = *(_DWORD *)(v6 + 176);
    *((_DWORD *)v12 + 22) = *(_DWORD *)(v6 + 216);
    *((_DWORD *)v12 + 19) = *(_DWORD *)(v6 + 100);
    *((_QWORD *)v12 + 8) = *(_QWORD *)(v6 + 56);
    *((_QWORD *)v12 + 7) = *(_QWORD *)(v6 + 40);
    *((_DWORD *)v12 + 12) = *(_DWORD *)(v6 + 36);
    *((_QWORD *)v12 + 14) = *(_QWORD *)(v6 + 168);
    *((_DWORD *)v12 + 38) = 2621824;
    *((_DWORD *)v12 + 39) = *(_DWORD *)(v6 + 72);
    *((_DWORD *)v12 + 40) = *(_DWORD *)(v6 + 76);
    *((_QWORD *)v12 + 21) = *(_QWORD *)(v6 + 48);
    *((_QWORD *)v12 + 22) = *(_QWORD *)(v6 + 64);
    *((_QWORD *)v12 + 23) = 4;
    *((_QWORD *)v12 + 273) = v12 + 2192;
    *((_QWORD *)v12 + 307) = v12 + 2464;
    *((_DWORD *)v12 + 544) = 0x1000000;
    *((_DWORD *)v12 + 612) = 0x2000000;
    memset(v12 + 2024, 0, 0x80u);
    *((_DWORD *)v12 + 506) = 8389248;
    v14 = 0;
    *((_DWORD *)v12 + 509) = 1;
    *((_DWORD *)v12 + 508) = 0;
    *((_QWORD *)v12 + 251) = v12 + 1992;
    *((_QWORD *)v12 + 252) = v12 + 1992;
    *((_QWORD *)v12 + 249) = v12 + 2008;
    *((_QWORD *)v12 + 250) = v12 + 2008;
    *a4 = v12;
  }
  else
  {
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v24, 20, 42, (__int64)WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids, WorkItem);
    v14 = NdisConvertNtStatusToNdisStatus(v25);
    if ( v14 )
      goto LABEL_16;
  }
  return v14;
}

```

## disassembly

```asm
0x14013a7c0  push    rbx
0x14013a7c2  push    rbp
0x14013a7c3  push    rsi
0x14013a7c4  push    rdi
0x14013a7c5  push    r12
0x14013a7c7  push    r13
0x14013a7c9  push    r14
0x14013a7cb  push    r15
0x14013a7cd  sub     rsp, 68h
0x14013a7d1  mov     r14, r9
0x14013a7d4  mov     r15, r8
0x14013a7d7  mov     rsi, rdx
0x14013a7da  mov     rdi, rcx
0x14013a7dd  test    rcx, rcx
0x14013a7e0  jz      loc_14013AAE6
0x14013a7e6  test    rdx, rdx
0x14013a7e9  jz      loc_14013AAE6
0x14013a7ef  test    r9, r9
0x14013a7f2  jz      loc_14013AAE6
0x14013a7f8  mov     rbx, [rcx+0CF0h]
0x14013a7ff  xor     edx, edx
0x14013a801  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14013a806  test    al, al
0x14013a808  jz      short loc_14013A87B
0x14013a80a  mov     [rsp+0A8h+P], 0
0x14013a813  xor     r8d, r8d
0x14013a816  lea     rdx, [rsp+0A8h+P]
0x14013a81b  mov     rcx, rbx
0x14013a81e  call    VmsPtGetNextMemberAdapterInternal
0x14013a823  mov     rbp, [rsp+0A8h+P]
0x14013a828  test    al, al
0x14013a82a  jz      short loc_14013A845
0x14013a82c  mov     rcx, [rbp+7Ch]
0x14013a830  sub     rcx, [r15]
0x14013a833  jnz     short loc_14013A840
0x14013a835  mov     rcx, [rbp+84h]
0x14013a83c  sub     rcx, [r15+8]
0x14013a840  test    rcx, rcx
0x14013a843  jnz     short loc_14013A813
0x14013a845  test    rbp, rbp
0x14013a848  jz      short loc_14013A87B
0x14013a84a  mov     ebx, 0C001001Eh
0x14013a84f  mov     rcx, cs:VmsIfrNicLog
0x14013a856  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a85d  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14013a861  mov     r9d, 28h ; '('
0x14013a867  mov     [rsp+0A8h+var_80], r15
0x14013a86c  mov     [rsp+0A8h+var_88], rax
0x14013a871  call    WPP_RECORDER_SF__guid_d
0x14013a876  jmp     loc_14013A95E
0x14013a87b  mov     r13, [rsi+8]
0x14013a87f  mov     r8d, 50737356h
0x14013a885  mov     r12d, cs:VmsCacheLineSizeInBytes
0x14013a88c  add     r12d, 10C9h
0x14013a893  movzx   ecx, word ptr [r13+2]
0x14013a898  add     r12d, ecx
0x14013a89b  mov     ecx, 40h ; '@'
0x14013a8a0  mov     edx, r12d
0x14013a8a3  call    cs:__imp_ExAllocatePool2
0x14013a8aa  nop     dword ptr [rax+rax+00h]
0x14013a8af  mov     rbp, rax
0x14013a8b2  test    rax, rax
0x14013a8b5  jnz     short loc_14013A8EC
0x14013a8b7  mov     ebx, 0C000009Ah
0x14013a8bc  mov     rcx, cs:VmsIfrLog
0x14013a8c3  lea     r9d, [rax+29h]
0x14013a8c7  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a8ce  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14013a8d2  mov     dword ptr [rsp+0A8h+var_80], r12d
0x14013a8d7  lea     r8d, [rbp+14h]
0x14013a8db  mov     dl, 2
0x14013a8dd  mov     [rsp+0A8h+var_88], rax
0x14013a8e2  call    WPP_RECORDER_SF_ld
0x14013a8e7  jmp     loc_14013AB27
0x14013a8ec  mov     rcx, [rdi+830h]; Lookaside
0x14013a8f3  lea     r8, VmsPtNicMuxDeleteVmqGroup
0x14013a8fa  add     rax, 0E80h
0x14013a900  mov     r9, rbp
0x14013a903  mov     [rsp+0A8h+var_80], rax; __int64
0x14013a908  xor     edx, edx
0x14013a90a  mov     [rsp+0A8h+var_88], 20h ; ' '; __int64
0x14013a913  call    NvIoAllocateWorkItem
0x14013a918  mov     ebx, eax
0x14013a91a  test    eax, eax
0x14013a91c  jns     short loc_14013A974
0x14013a91e  mov     rcx, cs:VmsIfrLog
0x14013a925  mov     r9d, 2Ah ; '*'
0x14013a92b  mov     dword ptr [rsp+0A8h+var_80], eax
0x14013a92f  mov     dl, 2
0x14013a931  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a938  mov     [rsp+0A8h+var_88], rax
0x14013a93d  lea     r8d, [r9-16h]
0x14013a941  call    WPP_RECORDER_SF_d
0x14013a946  mov     ecx, ebx
0x14013a948  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x14013a94f  nop     dword ptr [rax+rax+00h]
0x14013a954  mov     ebx, eax
0x14013a956  test    eax, eax
0x14013a958  jz      loc_14013AB4B
0x14013a95e  xor     edx, edx; Tag
0x14013a960  mov     rcx, rbp; P
0x14013a963  call    cs:__imp_ExFreePoolWithTag
0x14013a96a  nop     dword ptr [rax+rax+00h]
0x14013a96f  jmp     loc_14013AB27
0x14013a974  lea     rcx, [rbp+868h]; Event
0x14013a97b  call    cs:__imp_NdisInitializeEvent
0x14013a982  nop     dword ptr [rax+rax+00h]
0x14013a987  mov     [rbp+8], rdi
0x14013a98b  lea     rcx, [rbp+18h]; DestinationString
0x14013a98f  mov     eax, [rsi+0A0h]
0x14013a995  mov     rdx, r13; SourceString
0x14013a998  mov     [rbp+68h], eax
0x14013a99b  mov     rax, [rsi+98h]
0x14013a9a2  mov     [rbp+60h], rax
0x14013a9a6  lea     rax, [rbp+10C8h]
0x14013a9ad  mov     [rbp+20h], rax
0x14013a9b1  movzx   eax, word ptr [r13+2]
0x14013a9b6  mov     [rbp+1Ah], ax
0x14013a9ba  movzx   eax, word ptr [r13+0]
0x14013a9bf  mov     [rcx], ax
0x14013a9c2  call    cs:__imp_RtlCopyUnicodeString
0x14013a9c9  nop     dword ptr [rax+rax+00h]
0x14013a9ce  mov     eax, [rsi+6Ah]
0x14013a9d1  lea     rdi, [rbp+7C8h]
0x14013a9d8  mov     [rbp+28h], eax
0x14013a9db  mov     r8d, 80h; Size
0x14013a9e1  movzx   eax, word ptr [rsi+6Eh]
0x14013a9e5  xor     edx, edx; Val
0x14013a9e7  mov     [rbp+2Ch], ax
0x14013a9eb  mov     eax, [rsi+0D4h]
0x14013a9f1  mov     [rbp+54h], eax
0x14013a9f4  mov     eax, [rsi+0D0h]
0x14013a9fa  mov     [rbp+50h], eax
0x14013a9fd  movaps  xmm0, xmmword ptr [r15]
0x14013aa01  movdqu  xmmword ptr [rbp+7Ch], xmm0
0x14013aa06  mov     eax, [rsi+0B0h]
0x14013aa0c  mov     [rbp+78h], eax
0x14013aa0f  mov     eax, [rsi+0D8h]
0x14013aa15  mov     [rbp+58h], eax
0x14013aa18  mov     eax, [rsi+64h]
0x14013aa1b  mov     [rbp+4Ch], eax
0x14013aa1e  mov     rax, [rsi+38h]
0x14013aa22  mov     [rbp+40h], rax
0x14013aa26  mov     rax, [rsi+28h]
0x14013aa2a  mov     [rbp+38h], rax
0x14013aa2e  mov     eax, [rsi+24h]
0x14013aa31  mov     [rbp+30h], eax
0x14013aa34  mov     rax, [rsi+0A8h]
0x14013aa3b  mov     [rbp+70h], rax
0x14013aa3f  mov     dword ptr [rbp+98h], 280180h
0x14013aa49  mov     eax, [rsi+48h]
0x14013aa4c  mov     [rbp+9Ch], eax
0x14013aa52  mov     eax, [rsi+4Ch]
0x14013aa55  mov     [rbp+0A0h], eax
0x14013aa5b  mov     rax, [rsi+30h]
0x14013aa5f  mov     [rbp+0A8h], rax
0x14013aa66  mov     rax, [rsi+40h]
0x14013aa6a  lea     rsi, [rbp+7D8h]
0x14013aa71  mov     [rbp+0B0h], rax
0x14013aa78  lea     rcx, [rsi+10h]; void *
0x14013aa7c  lea     rax, [rbp+890h]
0x14013aa83  mov     qword ptr [rbp+0B8h], 4
0x14013aa8e  mov     [rbp+888h], rax
0x14013aa95  lea     rax, [rbp+9A0h]
0x14013aa9c  mov     [rbp+998h], rax
0x14013aaa3  mov     dword ptr [rbp+880h], 1000000h
0x14013aaad  mov     dword ptr [rbp+990h], 2000000h
0x14013aab7  call    memset
0x14013aabc  mov     dword ptr [rsi+10h], 800280h
0x14013aac3  xor     ebx, ebx
0x14013aac5  mov     dword ptr [rsi+1Ch], 1
0x14013aacc  mov     dword ptr [rsi+18h], 0
0x14013aad3  mov     [rsi], rdi
0x14013aad6  mov     [rsi+8], rdi
0x14013aada  mov     [rdi], rsi
0x14013aadd  mov     [rdi+8], rsi
0x14013aae1  mov     [r14], rbp
0x14013aae4  jmp     short loc_14013AB4B
0x14013aae6  mov     ebx, 0C000000Dh
0x14013aaeb  mov     rcx, cs:VmsIfrNicLog
0x14013aaf2  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013aaf9  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14013aafd  mov     r9d, 27h ; '''
0x14013ab03  mov     [rsp+0A8h+var_70], r14
0x14013ab08  mov     dl, 2
0x14013ab0a  mov     [rsp+0A8h+var_78], rsi
0x14013ab0f  mov     [rsp+0A8h+var_80], rdi
0x14013ab14  lea     r8d, [r9-13h]
0x14013ab18  mov     [rsp+0A8h+var_88], rax
0x14013ab1d  call    WPP_RECORDER_SF_qqqd
0x14013ab22  test    r14, r14
0x14013ab25  jz      short loc_14013AB2E
0x14013ab27  mov     qword ptr [r14], 0
0x14013ab2e  mov     [rsp+0A8h+var_60], ebx
0x14013ab32  mov     [rsp+0A8h+var_68], r14
0x14013ab37  mov     [rsp+0A8h+var_70], r15
0x14013ab3c  mov     [rsp+0A8h+var_78], rsi
0x14013ab41  mov     [rsp+0A8h+var_80], rdi
0x14013ab46  call    WPP_RECORDER_SF_qq_guid_qd
0x14013ab4b  mov     eax, ebx
0x14013ab4d  add     rsp, 68h
0x14013ab51  pop     r15
0x14013ab53  pop     r14
0x14013ab55  pop     r13
0x14013ab57  pop     r12
0x14013ab59  pop     rdi
0x14013ab5a  pop     rsi
0x14013ab5b  pop     rbp
0x14013ab5c  pop     rbx
0x14013ab5d  retn
```
