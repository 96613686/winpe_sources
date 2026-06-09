# VmsOmpCreateIpHashTable

- ea: `0x14010dedc`
- end: `0x14010e134`
- name: `VmsOmpCreateIpHashTable`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e6d0`

## callees

- `0x1400247dc`
- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14008497c`
- `0x14010dedc`
- `0x14010e13c`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14010e06a`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14010e06a`
- `ntoskrnl!RtlCreateHashTable` at `0x14010dfc2`
- `ntoskrnl!RtlCreateHashTable` at `0x14010dfc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010e100`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010e100`
- `ntoskrnl!ExAllocatePool2` at `0x14010df5e`
- `ntoskrnl!ExAllocatePool2` at `0x14010e01c`
- `ntoskrnl!ExAllocatePool2` at `0x14010df5e`
- `ntoskrnl!ExAllocatePool2` at `0x14010e01c`

## pseudocode

```c
__int64 __fastcall VmsOmpCreateIpHashTable(
        PRTL_DYNAMIC_HASH_TABLE *a1,
        _LIST_ENTRY *a2,
        unsigned __int16 a3,
        unsigned __int16 a4)
{
  __int64 v5; // r15
  _LIST_ENTRY *v7; // r14
  char v8; // bp
  int v9; // edx
  char v10; // di
  unsigned int v11; // ebx
  int v12; // edx
  int v13; // edx
  unsigned __int16 i; // bx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *Pool2; // rax
  int v16; // edx
  ULONG_PTR v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  ULONG_PTR v20; // rdx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+70h] [rbp+8h] BYREF

  v5 = a4;
  v7 = a2;
  HashTable = 0;
  if ( !a1 )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      (_DWORD)a2,
      19,
      15,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      "IpTable != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  HashTable = 0;
  *a1 = 0;
  v8 = 0;
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)ExAllocatePool2(64, 40, 1649374038);
  if ( !HashTable )
  {
    v10 = 0;
    v11 = -1073741670;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v9, 20, 16, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, 40, 154);
    goto LABEL_16;
  }
  v10 = 1;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    v11 = -1073741823;
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v13, 20, 17, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, 1);
LABEL_16:
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_qdd(
      VmsIfrLog,
      v12,
      20,
      19,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      (char)v7,
      a3,
      v11);
    if ( v8 )
    {
      VmsOmpDestroyIpHashTable(&HashTable);
    }
    else if ( v10 )
    {
      ExFreePoolWithTag(HashTable, 0);
    }
    return v11;
  }
  for ( i = 0; i < a3; ++i )
  {
    Pool2 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)ExAllocatePool2(64, 32, 1649374038);
    if ( !Pool2 )
    {
      v8 = 1;
      v11 = -1073741670;
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_ld(VmsIfrLog, v16, 20, 18, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, 32, 154);
      goto LABEL_16;
    }
    v17 = 0;
    Pool2[1].Linkage.Flink = v7;
    v18 = 0;
    if ( !(_DWORD)v5 )
      goto LABEL_13;
    do
    {
      v19 = *((unsigned __int8 *)&v7->Flink + v18);
      v18 = (unsigned int)(v18 + 1);
      v20 = 37 * v17 + v19;
      v17 = v20;
    }
    while ( (unsigned int)v18 < (unsigned int)v5 );
    if ( !v20 )
LABEL_13:
      v17 = -1;
    RtlInsertEntryHashTable(HashTable, Pool2, v17, 0);
    v7 = (_LIST_ENTRY *)((char *)v7 + v5);
  }
  v11 = 0;
  *a1 = HashTable;
  return v11;
}

```

## disassembly

```asm
0x14010dedc  mov     r11, rsp
0x14010dedf  mov     [r11+10h], rbx
0x14010dee3  mov     [r11+18h], rbp
0x14010dee7  push    rsi
0x14010dee8  push    rdi
0x14010dee9  push    r12
0x14010deeb  push    r14
0x14010deed  push    r15
0x14010deef  sub     rsp, 40h
0x14010def3  mov     rsi, rcx
0x14010def6  movzx   r15d, r9w
0x14010defa  movzx   r12d, r8w
0x14010defe  mov     r14, rdx
0x14010df01  mov     qword ptr [r11+8], 0
0x14010df09  lea     rcx, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010df10  test    rsi, rsi
0x14010df13  jnz     short loc_14010DF3D
0x14010df15  lea     rax, aIptableNull; "IpTable != NULL"
0x14010df1c  mov     [r11-40h], rax
0x14010df20  lea     r9d, [rsi+0Fh]
0x14010df24  mov     [r11-48h], rcx
0x14010df28  lea     r8d, [rsi+13h]
0x14010df2c  mov     rcx, cs:VmsIfrLog
0x14010df33  call    WPP_RECORDER_SF_s
0x14010df38  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "IpTable != ((void *)0)")
0x14010df3d  mov     edx, 28h ; '('
0x14010df42  mov     [rsp+68h+HashTable], 0
0x14010df4b  mov     r8d, 624F7356h
0x14010df51  mov     qword ptr [rsi], 0
0x14010df58  xor     bpl, bpl
0x14010df5b  lea     ecx, [rdx+18h]
0x14010df5e  call    cs:__imp_ExAllocatePool2
0x14010df65  nop     dword ptr [rax+rax+00h]
0x14010df6a  mov     [rsp+68h+HashTable], rax
0x14010df6f  test    rax, rax
0x14010df72  jnz     short loc_14010DFB3
0x14010df74  mov     eax, 0C000009Ah
0x14010df79  xor     dil, dil
0x14010df7c  mov     ebx, eax
0x14010df7e  mov     rcx, cs:VmsIfrLog
0x14010df85  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010df8c  mov     [rsp+68h+var_38], eax
0x14010df90  mov     r9d, 10h
0x14010df96  mov     dword ptr [rsp+68h+var_40], 28h ; '('
0x14010df9e  mov     dl, 2
0x14010dfa0  mov     [rsp+68h+var_48], rsi
0x14010dfa5  lea     r8d, [r9+4]
0x14010dfa9  call    WPP_RECORDER_SF_ld
0x14010dfae  jmp     loc_14010E0B8
0x14010dfb3  xor     r8d, r8d; Flags
0x14010dfb6  lea     rcx, [rsp+68h+HashTable]; HashTable
0x14010dfbb  xor     edx, edx; Shift
0x14010dfbd  mov     edi, 1
0x14010dfc2  call    cs:__imp_RtlCreateHashTable
0x14010dfc9  nop     dword ptr [rax+rax+00h]
0x14010dfce  test    al, al
0x14010dfd0  jnz     short loc_14010E002
0x14010dfd2  mov     ebx, 0C0000001h
0x14010dfd7  mov     rcx, cs:VmsIfrLog
0x14010dfde  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010dfe5  lea     r9d, [rdi+10h]
0x14010dfe9  mov     dword ptr [rsp+68h+var_40], ebx
0x14010dfed  lea     r8d, [rdi+13h]
0x14010dff1  mov     [rsp+68h+var_48], rsi
0x14010dff6  mov     dl, 2
0x14010dff8  call    WPP_RECORDER_SF_d
0x14010dffd  jmp     loc_14010E0B8
0x14010e002  xor     ebx, ebx
0x14010e004  cmp     bx, r12w
0x14010e008  jnb     loc_14010E10E
0x14010e00e  mov     edx, 20h ; ' '
0x14010e013  mov     r8d, 624F7356h
0x14010e019  lea     ecx, [rdx+20h]
0x14010e01c  call    cs:__imp_ExAllocatePool2
0x14010e023  nop     dword ptr [rax+rax+00h]
0x14010e028  mov     r11, rax
0x14010e02b  test    rax, rax
0x14010e02e  jz      short loc_14010E07E
0x14010e030  xor     r8d, r8d
0x14010e033  mov     [rax+18h], r14
0x14010e037  xor     r9d, r9d
0x14010e03a  test    r15d, r15d
0x14010e03d  jz      short loc_14010E05B
0x14010e03f  movzx   edx, byte ptr [r9+r14]
0x14010e044  add     r9d, edi
0x14010e047  imul    rax, r8, 25h ; '%'
0x14010e04b  add     rdx, rax
0x14010e04e  mov     r8, rdx
0x14010e051  cmp     r9d, r15d
0x14010e054  jb      short loc_14010E03F
0x14010e056  test    rdx, rdx
0x14010e059  jnz     short loc_14010E05F
0x14010e05b  or      r8, 0FFFFFFFFFFFFFFFFh; Signature
0x14010e05f  mov     rcx, [rsp+68h+HashTable]; HashTable
0x14010e064  xor     r9d, r9d; Context
0x14010e067  mov     rdx, r11; Entry
0x14010e06a  call    cs:__imp_RtlInsertEntryHashTable
0x14010e071  nop     dword ptr [rax+rax+00h]
0x14010e076  add     r14, r15
0x14010e079  add     bx, di
0x14010e07c  jmp     short loc_14010E004
0x14010e07e  mov     eax, 0C000009Ah
0x14010e083  mov     bpl, dil
0x14010e086  mov     ebx, eax
0x14010e088  mov     rcx, cs:VmsIfrLog
0x14010e08f  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010e096  mov     [rsp+68h+var_38], eax
0x14010e09a  mov     r9d, 12h
0x14010e0a0  mov     dword ptr [rsp+68h+var_40], 20h ; ' '
0x14010e0a8  mov     dl, 2
0x14010e0aa  mov     [rsp+68h+var_48], rsi
0x14010e0af  lea     r8d, [r9+2]
0x14010e0b3  call    WPP_RECORDER_SF_ld
0x14010e0b8  mov     rcx, cs:VmsIfrLog
0x14010e0bf  mov     r9d, 13h
0x14010e0c5  mov     [rsp+68h+var_30], ebx
0x14010e0c9  mov     dl, 2
0x14010e0cb  mov     [rsp+68h+var_38], r12d
0x14010e0d0  mov     [rsp+68h+var_40], r14
0x14010e0d5  lea     r8d, [r9+1]
0x14010e0d9  mov     [rsp+68h+var_48], rsi
0x14010e0de  call    WPP_RECORDER_SF_qdd
0x14010e0e3  test    bpl, bpl
0x14010e0e6  jz      short loc_14010E0F4
0x14010e0e8  lea     rcx, [rsp+68h+HashTable]
0x14010e0ed  call    VmsOmpDestroyIpHashTable
0x14010e0f2  jmp     short loc_14010E118
0x14010e0f4  test    dil, dil
0x14010e0f7  jz      short loc_14010E118
0x14010e0f9  mov     rcx, [rsp+68h+HashTable]; P
0x14010e0fe  xor     edx, edx; Tag
0x14010e100  call    cs:__imp_ExFreePoolWithTag
0x14010e107  nop     dword ptr [rax+rax+00h]
0x14010e10c  jmp     short loc_14010E118
0x14010e10e  mov     rcx, [rsp+68h+HashTable]
0x14010e113  xor     ebx, ebx
0x14010e115  mov     [rsi], rcx
0x14010e118  lea     r11, [rsp+68h+var_28]
0x14010e11d  mov     eax, ebx
0x14010e11f  mov     rbx, [r11+38h]
0x14010e123  mov     rbp, [r11+40h]
0x14010e127  mov     rsp, r11
0x14010e12a  pop     r15
0x14010e12c  pop     r14
0x14010e12e  pop     r12
0x14010e130  pop     rdi
0x14010e131  pop     rsi
0x14010e132  retn
```
