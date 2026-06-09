# VmsOmpCreateIpHashTable

- ea: `0x14010df4c`
- end: `0x14010e1a4`
- name: `VmsOmpCreateIpHashTable`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e740`

## callees

- `0x1400247dc`
- `0x140027a64`
- `0x14002e0f0`
- `0x14003a450`
- `0x14008497c`
- `0x14010df4c`
- `0x14010e1ac`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14010e0da`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14010e0da`
- `ntoskrnl!RtlCreateHashTable` at `0x14010e032`
- `ntoskrnl!RtlCreateHashTable` at `0x14010e032`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010e170`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010e170`
- `ntoskrnl!ExAllocatePool2` at `0x14010dfce`
- `ntoskrnl!ExAllocatePool2` at `0x14010e08c`
- `ntoskrnl!ExAllocatePool2` at `0x14010dfce`
- `ntoskrnl!ExAllocatePool2` at `0x14010e08c`

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
0x14010df4c  mov     r11, rsp
0x14010df4f  mov     [r11+10h], rbx
0x14010df53  mov     [r11+18h], rbp
0x14010df57  push    rsi
0x14010df58  push    rdi
0x14010df59  push    r12
0x14010df5b  push    r14
0x14010df5d  push    r15
0x14010df5f  sub     rsp, 40h
0x14010df63  mov     rsi, rcx
0x14010df66  movzx   r15d, r9w
0x14010df6a  movzx   r12d, r8w
0x14010df6e  mov     r14, rdx
0x14010df71  mov     qword ptr [r11+8], 0
0x14010df79  lea     rcx, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010df80  test    rsi, rsi
0x14010df83  jnz     short loc_14010DFAD
0x14010df85  lea     rax, aIptableNull; "IpTable != NULL"
0x14010df8c  mov     [r11-40h], rax
0x14010df90  lea     r9d, [rsi+0Fh]
0x14010df94  mov     [r11-48h], rcx
0x14010df98  lea     r8d, [rsi+13h]
0x14010df9c  mov     rcx, cs:VmsIfrLog
0x14010dfa3  call    WPP_RECORDER_SF_s
0x14010dfa8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "IpTable != ((void *)0)")
0x14010dfad  mov     edx, 28h ; '('
0x14010dfb2  mov     [rsp+68h+HashTable], 0
0x14010dfbb  mov     r8d, 624F7356h
0x14010dfc1  mov     qword ptr [rsi], 0
0x14010dfc8  xor     bpl, bpl
0x14010dfcb  lea     ecx, [rdx+18h]
0x14010dfce  call    cs:__imp_ExAllocatePool2
0x14010dfd5  nop     dword ptr [rax+rax+00h]
0x14010dfda  mov     [rsp+68h+HashTable], rax
0x14010dfdf  test    rax, rax
0x14010dfe2  jnz     short loc_14010E023
0x14010dfe4  mov     eax, 0C000009Ah
0x14010dfe9  xor     dil, dil
0x14010dfec  mov     ebx, eax
0x14010dfee  mov     rcx, cs:VmsIfrLog
0x14010dff5  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010dffc  mov     [rsp+68h+var_38], eax
0x14010e000  mov     r9d, 10h
0x14010e006  mov     dword ptr [rsp+68h+var_40], 28h ; '('
0x14010e00e  mov     dl, 2
0x14010e010  mov     [rsp+68h+var_48], rsi
0x14010e015  lea     r8d, [r9+4]
0x14010e019  call    WPP_RECORDER_SF_ld
0x14010e01e  jmp     loc_14010E128
0x14010e023  xor     r8d, r8d; Flags
0x14010e026  lea     rcx, [rsp+68h+HashTable]; HashTable
0x14010e02b  xor     edx, edx; Shift
0x14010e02d  mov     edi, 1
0x14010e032  call    cs:__imp_RtlCreateHashTable
0x14010e039  nop     dword ptr [rax+rax+00h]
0x14010e03e  test    al, al
0x14010e040  jnz     short loc_14010E072
0x14010e042  mov     ebx, 0C0000001h
0x14010e047  mov     rcx, cs:VmsIfrLog
0x14010e04e  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010e055  lea     r9d, [rdi+10h]
0x14010e059  mov     dword ptr [rsp+68h+var_40], ebx
0x14010e05d  lea     r8d, [rdi+13h]
0x14010e061  mov     [rsp+68h+var_48], rsi
0x14010e066  mov     dl, 2
0x14010e068  call    WPP_RECORDER_SF_d
0x14010e06d  jmp     loc_14010E128
0x14010e072  xor     ebx, ebx
0x14010e074  cmp     bx, r12w
0x14010e078  jnb     loc_14010E17E
0x14010e07e  mov     edx, 20h ; ' '
0x14010e083  mov     r8d, 624F7356h
0x14010e089  lea     ecx, [rdx+20h]
0x14010e08c  call    cs:__imp_ExAllocatePool2
0x14010e093  nop     dword ptr [rax+rax+00h]
0x14010e098  mov     r11, rax
0x14010e09b  test    rax, rax
0x14010e09e  jz      short loc_14010E0EE
0x14010e0a0  xor     r8d, r8d
0x14010e0a3  mov     [rax+18h], r14
0x14010e0a7  xor     r9d, r9d
0x14010e0aa  test    r15d, r15d
0x14010e0ad  jz      short loc_14010E0CB
0x14010e0af  movzx   edx, byte ptr [r9+r14]
0x14010e0b4  add     r9d, edi
0x14010e0b7  imul    rax, r8, 25h ; '%'
0x14010e0bb  add     rdx, rax
0x14010e0be  mov     r8, rdx
0x14010e0c1  cmp     r9d, r15d
0x14010e0c4  jb      short loc_14010E0AF
0x14010e0c6  test    rdx, rdx
0x14010e0c9  jnz     short loc_14010E0CF
0x14010e0cb  or      r8, 0FFFFFFFFFFFFFFFFh; Signature
0x14010e0cf  mov     rcx, [rsp+68h+HashTable]; HashTable
0x14010e0d4  xor     r9d, r9d; Context
0x14010e0d7  mov     rdx, r11; Entry
0x14010e0da  call    cs:__imp_RtlInsertEntryHashTable
0x14010e0e1  nop     dword ptr [rax+rax+00h]
0x14010e0e6  add     r14, r15
0x14010e0e9  add     bx, di
0x14010e0ec  jmp     short loc_14010E074
0x14010e0ee  mov     eax, 0C000009Ah
0x14010e0f3  mov     bpl, dil
0x14010e0f6  mov     ebx, eax
0x14010e0f8  mov     rcx, cs:VmsIfrLog
0x14010e0ff  lea     rsi, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010e106  mov     [rsp+68h+var_38], eax
0x14010e10a  mov     r9d, 12h
0x14010e110  mov     dword ptr [rsp+68h+var_40], 20h ; ' '
0x14010e118  mov     dl, 2
0x14010e11a  mov     [rsp+68h+var_48], rsi
0x14010e11f  lea     r8d, [r9+2]
0x14010e123  call    WPP_RECORDER_SF_ld
0x14010e128  mov     rcx, cs:VmsIfrLog
0x14010e12f  mov     r9d, 13h
0x14010e135  mov     [rsp+68h+var_30], ebx
0x14010e139  mov     dl, 2
0x14010e13b  mov     [rsp+68h+var_38], r12d
0x14010e140  mov     [rsp+68h+var_40], r14
0x14010e145  lea     r8d, [r9+1]
0x14010e149  mov     [rsp+68h+var_48], rsi
0x14010e14e  call    WPP_RECORDER_SF_qdd
0x14010e153  test    bpl, bpl
0x14010e156  jz      short loc_14010E164
0x14010e158  lea     rcx, [rsp+68h+HashTable]
0x14010e15d  call    VmsOmpDestroyIpHashTable
0x14010e162  jmp     short loc_14010E188
0x14010e164  test    dil, dil
0x14010e167  jz      short loc_14010E188
0x14010e169  mov     rcx, [rsp+68h+HashTable]; P
0x14010e16e  xor     edx, edx; Tag
0x14010e170  call    cs:__imp_ExFreePoolWithTag
0x14010e177  nop     dword ptr [rax+rax+00h]
0x14010e17c  jmp     short loc_14010E188
0x14010e17e  mov     rcx, [rsp+68h+HashTable]
0x14010e183  xor     ebx, ebx
0x14010e185  mov     [rsi], rcx
0x14010e188  lea     r11, [rsp+68h+var_28]
0x14010e18d  mov     eax, ebx
0x14010e18f  mov     rbx, [r11+38h]
0x14010e193  mov     rbp, [r11+40h]
0x14010e197  mov     rsp, r11
0x14010e19a  pop     r15
0x14010e19c  pop     r14
0x14010e19e  pop     r12
0x14010e1a0  pop     rdi
0x14010e1a1  pop     rsi
0x14010e1a2  retn
```
