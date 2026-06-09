# VmsPtNicMuxCreateNewMemberAdapter

- ea: `0x14013a750`
- end: `0x14013aaef`
- name: `VmsPtNicMuxCreateNewMemberAdapter`
- size: `927`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140117f40`

## callees

- `0x14002e0f0`
- `0x14003a450`
- `0x14004f5d8`
- `0x140052460`
- `0x14006a330`
- `0x14007a074`
- `0x1400dabf0`
- `0x14013a750`
- `0x14013e3fc`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14013a952`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14013a952`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013a8f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14013a8f3`
- `ntoskrnl!ExAllocatePool2` at `0x14013a833`
- `ntoskrnl!ExAllocatePool2` at `0x14013a833`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x14013a8d8`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x14013a8d8`
- `NDIS!NdisInitializeEvent` at `0x14013a90b`
- `NDIS!NdisInitializeEvent` at `0x14013a90b`

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
0x14013a750  push    rbx
0x14013a752  push    rbp
0x14013a753  push    rsi
0x14013a754  push    rdi
0x14013a755  push    r12
0x14013a757  push    r13
0x14013a759  push    r14
0x14013a75b  push    r15
0x14013a75d  sub     rsp, 68h
0x14013a761  mov     r14, r9
0x14013a764  mov     r15, r8
0x14013a767  mov     rsi, rdx
0x14013a76a  mov     rdi, rcx
0x14013a76d  test    rcx, rcx
0x14013a770  jz      loc_14013AA76
0x14013a776  test    rdx, rdx
0x14013a779  jz      loc_14013AA76
0x14013a77f  test    r9, r9
0x14013a782  jz      loc_14013AA76
0x14013a788  mov     rbx, [rcx+0CF0h]
0x14013a78f  xor     edx, edx
0x14013a791  call    VmsPtCheckIsEmbeddedTeamingEnabled
0x14013a796  test    al, al
0x14013a798  jz      short loc_14013A80B
0x14013a79a  mov     [rsp+0A8h+P], 0
0x14013a7a3  xor     r8d, r8d
0x14013a7a6  lea     rdx, [rsp+0A8h+P]
0x14013a7ab  mov     rcx, rbx
0x14013a7ae  call    VmsPtGetNextMemberAdapterInternal
0x14013a7b3  mov     rbp, [rsp+0A8h+P]
0x14013a7b8  test    al, al
0x14013a7ba  jz      short loc_14013A7D5
0x14013a7bc  mov     rcx, [rbp+7Ch]
0x14013a7c0  sub     rcx, [r15]
0x14013a7c3  jnz     short loc_14013A7D0
0x14013a7c5  mov     rcx, [rbp+84h]
0x14013a7cc  sub     rcx, [r15+8]
0x14013a7d0  test    rcx, rcx
0x14013a7d3  jnz     short loc_14013A7A3
0x14013a7d5  test    rbp, rbp
0x14013a7d8  jz      short loc_14013A80B
0x14013a7da  mov     ebx, 0C001001Eh
0x14013a7df  mov     rcx, cs:VmsIfrNicLog
0x14013a7e6  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a7ed  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14013a7f1  mov     r9d, 28h ; '('
0x14013a7f7  mov     [rsp+0A8h+var_80], r15
0x14013a7fc  mov     [rsp+0A8h+var_88], rax
0x14013a801  call    WPP_RECORDER_SF__guid_d
0x14013a806  jmp     loc_14013A8EE
0x14013a80b  mov     r13, [rsi+8]
0x14013a80f  mov     r8d, 50737356h
0x14013a815  mov     r12d, cs:VmsCacheLineSizeInBytes
0x14013a81c  add     r12d, 10C9h
0x14013a823  movzx   ecx, word ptr [r13+2]
0x14013a828  add     r12d, ecx
0x14013a82b  mov     ecx, 40h ; '@'
0x14013a830  mov     edx, r12d
0x14013a833  call    cs:__imp_ExAllocatePool2
0x14013a83a  nop     dword ptr [rax+rax+00h]
0x14013a83f  mov     rbp, rax
0x14013a842  test    rax, rax
0x14013a845  jnz     short loc_14013A87C
0x14013a847  mov     ebx, 0C000009Ah
0x14013a84c  mov     rcx, cs:VmsIfrLog
0x14013a853  lea     r9d, [rax+29h]
0x14013a857  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a85e  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14013a862  mov     dword ptr [rsp+0A8h+var_80], r12d
0x14013a867  lea     r8d, [rbp+14h]
0x14013a86b  mov     dl, 2
0x14013a86d  mov     [rsp+0A8h+var_88], rax
0x14013a872  call    WPP_RECORDER_SF_ld
0x14013a877  jmp     loc_14013AAB7
0x14013a87c  mov     rcx, [rdi+830h]; Lookaside
0x14013a883  lea     r8, VmsPtNicMuxDeleteVmqGroup
0x14013a88a  add     rax, 0E80h
0x14013a890  mov     r9, rbp
0x14013a893  mov     [rsp+0A8h+var_80], rax; __int64
0x14013a898  xor     edx, edx
0x14013a89a  mov     [rsp+0A8h+var_88], 20h ; ' '; __int64
0x14013a8a3  call    NvIoAllocateWorkItem
0x14013a8a8  mov     ebx, eax
0x14013a8aa  test    eax, eax
0x14013a8ac  jns     short loc_14013A904
0x14013a8ae  mov     rcx, cs:VmsIfrLog
0x14013a8b5  mov     r9d, 2Ah ; '*'
0x14013a8bb  mov     dword ptr [rsp+0A8h+var_80], eax
0x14013a8bf  mov     dl, 2
0x14013a8c1  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013a8c8  mov     [rsp+0A8h+var_88], rax
0x14013a8cd  lea     r8d, [r9-16h]
0x14013a8d1  call    WPP_RECORDER_SF_d
0x14013a8d6  mov     ecx, ebx
0x14013a8d8  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x14013a8df  nop     dword ptr [rax+rax+00h]
0x14013a8e4  mov     ebx, eax
0x14013a8e6  test    eax, eax
0x14013a8e8  jz      loc_14013AADB
0x14013a8ee  xor     edx, edx; Tag
0x14013a8f0  mov     rcx, rbp; P
0x14013a8f3  call    cs:__imp_ExFreePoolWithTag
0x14013a8fa  nop     dword ptr [rax+rax+00h]
0x14013a8ff  jmp     loc_14013AAB7
0x14013a904  lea     rcx, [rbp+868h]; Event
0x14013a90b  call    cs:__imp_NdisInitializeEvent
0x14013a912  nop     dword ptr [rax+rax+00h]
0x14013a917  mov     [rbp+8], rdi
0x14013a91b  lea     rcx, [rbp+18h]; DestinationString
0x14013a91f  mov     eax, [rsi+0A0h]
0x14013a925  mov     rdx, r13; SourceString
0x14013a928  mov     [rbp+68h], eax
0x14013a92b  mov     rax, [rsi+98h]
0x14013a932  mov     [rbp+60h], rax
0x14013a936  lea     rax, [rbp+10C8h]
0x14013a93d  mov     [rbp+20h], rax
0x14013a941  movzx   eax, word ptr [r13+2]
0x14013a946  mov     [rbp+1Ah], ax
0x14013a94a  movzx   eax, word ptr [r13+0]
0x14013a94f  mov     [rcx], ax
0x14013a952  call    cs:__imp_RtlCopyUnicodeString
0x14013a959  nop     dword ptr [rax+rax+00h]
0x14013a95e  mov     eax, [rsi+6Ah]
0x14013a961  lea     rdi, [rbp+7C8h]
0x14013a968  mov     [rbp+28h], eax
0x14013a96b  mov     r8d, 80h; Size
0x14013a971  movzx   eax, word ptr [rsi+6Eh]
0x14013a975  xor     edx, edx; Val
0x14013a977  mov     [rbp+2Ch], ax
0x14013a97b  mov     eax, [rsi+0D4h]
0x14013a981  mov     [rbp+54h], eax
0x14013a984  mov     eax, [rsi+0D0h]
0x14013a98a  mov     [rbp+50h], eax
0x14013a98d  movaps  xmm0, xmmword ptr [r15]
0x14013a991  movdqu  xmmword ptr [rbp+7Ch], xmm0
0x14013a996  mov     eax, [rsi+0B0h]
0x14013a99c  mov     [rbp+78h], eax
0x14013a99f  mov     eax, [rsi+0D8h]
0x14013a9a5  mov     [rbp+58h], eax
0x14013a9a8  mov     eax, [rsi+64h]
0x14013a9ab  mov     [rbp+4Ch], eax
0x14013a9ae  mov     rax, [rsi+38h]
0x14013a9b2  mov     [rbp+40h], rax
0x14013a9b6  mov     rax, [rsi+28h]
0x14013a9ba  mov     [rbp+38h], rax
0x14013a9be  mov     eax, [rsi+24h]
0x14013a9c1  mov     [rbp+30h], eax
0x14013a9c4  mov     rax, [rsi+0A8h]
0x14013a9cb  mov     [rbp+70h], rax
0x14013a9cf  mov     dword ptr [rbp+98h], 280180h
0x14013a9d9  mov     eax, [rsi+48h]
0x14013a9dc  mov     [rbp+9Ch], eax
0x14013a9e2  mov     eax, [rsi+4Ch]
0x14013a9e5  mov     [rbp+0A0h], eax
0x14013a9eb  mov     rax, [rsi+30h]
0x14013a9ef  mov     [rbp+0A8h], rax
0x14013a9f6  mov     rax, [rsi+40h]
0x14013a9fa  lea     rsi, [rbp+7D8h]
0x14013aa01  mov     [rbp+0B0h], rax
0x14013aa08  lea     rcx, [rsi+10h]; void *
0x14013aa0c  lea     rax, [rbp+890h]
0x14013aa13  mov     qword ptr [rbp+0B8h], 4
0x14013aa1e  mov     [rbp+888h], rax
0x14013aa25  lea     rax, [rbp+9A0h]
0x14013aa2c  mov     [rbp+998h], rax
0x14013aa33  mov     dword ptr [rbp+880h], 1000000h
0x14013aa3d  mov     dword ptr [rbp+990h], 2000000h
0x14013aa47  call    memset
0x14013aa4c  mov     dword ptr [rsi+10h], 800280h
0x14013aa53  xor     ebx, ebx
0x14013aa55  mov     dword ptr [rsi+1Ch], 1
0x14013aa5c  mov     dword ptr [rsi+18h], 0
0x14013aa63  mov     [rsi], rdi
0x14013aa66  mov     [rsi+8], rdi
0x14013aa6a  mov     [rdi], rsi
0x14013aa6d  mov     [rdi+8], rsi
0x14013aa71  mov     [r14], rbp
0x14013aa74  jmp     short loc_14013AADB
0x14013aa76  mov     ebx, 0C000000Dh
0x14013aa7b  mov     rcx, cs:VmsIfrNicLog
0x14013aa82  lea     rax, WPP_bef83c877c1a3b62a8aca4af9cf4ecfc_Traceguids
0x14013aa89  mov     dword ptr [rsp+0A8h+var_68], ebx
0x14013aa8d  mov     r9d, 27h ; '''
0x14013aa93  mov     [rsp+0A8h+var_70], r14
0x14013aa98  mov     dl, 2
0x14013aa9a  mov     [rsp+0A8h+var_78], rsi
0x14013aa9f  mov     [rsp+0A8h+var_80], rdi
0x14013aaa4  lea     r8d, [r9-13h]
0x14013aaa8  mov     [rsp+0A8h+var_88], rax
0x14013aaad  call    WPP_RECORDER_SF_qqqd
0x14013aab2  test    r14, r14
0x14013aab5  jz      short loc_14013AABE
0x14013aab7  mov     qword ptr [r14], 0
0x14013aabe  mov     [rsp+0A8h+var_60], ebx
0x14013aac2  mov     [rsp+0A8h+var_68], r14
0x14013aac7  mov     [rsp+0A8h+var_70], r15
0x14013aacc  mov     [rsp+0A8h+var_78], rsi
0x14013aad1  mov     [rsp+0A8h+var_80], rdi
0x14013aad6  call    WPP_RECORDER_SF_qq_guid_qd
0x14013aadb  mov     eax, ebx
0x14013aadd  add     rsp, 68h
0x14013aae1  pop     r15
0x14013aae3  pop     r14
0x14013aae5  pop     r13
0x14013aae7  pop     r12
0x14013aae9  pop     rdi
0x14013aaea  pop     rsi
0x14013aaeb  pop     rbp
0x14013aaec  pop     rbx
0x14013aaed  retn
```
