# VmsOmPortEmptyFlowHashTable

- ea: `0x14010be10`
- end: `0x14010bf2f`
- name: `VmsOmPortEmptyFlowHashTable`
- size: `287`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e628`
- `0x140157e10`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x140046f1c`
- `0x14008497c`
- `0x14010be10`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010bed6`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010bed6`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010bf17`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010bf17`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010befb`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010befb`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010be6e`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010be6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010bee7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010bee7`

## pseudocode

```c
__int64 __fastcall VmsOmPortEmptyFlowHashTable(PRTL_DYNAMIC_HASH_TABLE HashTable, int a2)
{
  int v3; // edx
  unsigned int v4; // esi
  int v5; // edx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v6; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+40h] [rbp-58h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( !HashTable )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      100,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      "FlowHashTable != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( RtlInitEnumerationHashTable(HashTable, &Enumerator) )
  {
    v4 = 0;
    while ( 1 )
    {
      v6 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
      v7 = v6;
      if ( !v6 )
        break;
      RtlRemoveEntryHashTable(HashTable, v6, 0);
      ExFreePoolWithTag(v7, 0);
    }
    RtlEndEnumerationHashTable(HashTable, &Enumerator);
  }
  else
  {
    v4 = -1073741823;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(VmsIfrLog, v3, 20, 101, (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids, 1);
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrLog,
      v5,
      20,
      102,
      (__int64)WPP_2ef67749ba943892c5000d964b576d2d_Traceguids,
      (char)HashTable,
      1);
  }
  return v4;
}

```

## disassembly

```asm
0x14010be10  push    rbx
0x14010be12  push    rbp
0x14010be13  push    rsi
0x14010be14  push    rdi
0x14010be15  sub     rsp, 78h
0x14010be19  xor     eax, eax
0x14010be1b  lea     rbp, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010be22  mov     qword ptr [rsp+98h+Enumerator.BucketIndex], rax
0x14010be27  xorps   xmm0, xmm0
0x14010be2a  mov     rbx, rcx
0x14010be2d  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x14010be32  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x14010be37  test    rcx, rcx
0x14010be3a  jnz     short loc_14010BE66
0x14010be3c  lea     rax, aFlowhashtableN; "FlowHashTable != NULL"
0x14010be43  lea     r9d, [rcx+64h]
0x14010be47  mov     [rsp+98h+var_70], rax
0x14010be4c  lea     r8d, [rcx+13h]
0x14010be50  mov     [rsp+98h+var_78], rbp
0x14010be55  mov     rcx, cs:VmsIfrLog
0x14010be5c  call    WPP_RECORDER_SF_s
0x14010be61  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FlowHashTable != ((void *)0)")
0x14010be66  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010be6b  mov     rcx, rbx; HashTable
0x14010be6e  call    cs:__imp_RtlInitEnumerationHashTable
0x14010be75  nop     dword ptr [rax+rax+00h]
0x14010be7a  test    al, al
0x14010be7c  jnz     short loc_14010BECC
0x14010be7e  mov     esi, 0C0000001h
0x14010be83  mov     rcx, cs:VmsIfrLog
0x14010be8a  mov     r9d, 65h ; 'e'
0x14010be90  mov     dword ptr [rsp+98h+var_70], esi
0x14010be94  mov     dl, 2
0x14010be96  mov     [rsp+98h+var_78], rbp
0x14010be9b  lea     edi, [r9-51h]
0x14010be9f  mov     r8d, edi
0x14010bea2  call    WPP_RECORDER_SF_d
0x14010bea7  mov     rcx, cs:VmsIfrLog
0x14010beae  lea     r9d, [rdi+52h]
0x14010beb2  mov     [rsp+98h+var_68], esi
0x14010beb6  mov     r8d, edi
0x14010beb9  mov     [rsp+98h+var_70], rbx
0x14010bebe  mov     dl, 2
0x14010bec0  mov     [rsp+98h+var_78], rbp
0x14010bec5  call    WPP_RECORDER_SF_id
0x14010beca  jmp     short loc_14010BF23
0x14010becc  xor     esi, esi
0x14010bece  jmp     short loc_14010BEF3
0x14010bed0  xor     r8d, r8d; Context
0x14010bed3  mov     rdx, rdi; Entry
0x14010bed6  call    cs:__imp_RtlRemoveEntryHashTable
0x14010bedd  nop     dword ptr [rax+rax+00h]
0x14010bee2  xor     edx, edx; Tag
0x14010bee4  mov     rcx, rdi; P
0x14010bee7  call    cs:__imp_ExFreePoolWithTag
0x14010beee  nop     dword ptr [rax+rax+00h]
0x14010bef3  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010bef8  mov     rcx, rbx; HashTable
0x14010befb  call    cs:__imp_RtlEnumerateEntryHashTable
0x14010bf02  nop     dword ptr [rax+rax+00h]
0x14010bf07  mov     rdi, rax
0x14010bf0a  mov     rcx, rbx; HashTable
0x14010bf0d  test    rax, rax
0x14010bf10  jnz     short loc_14010BED0
0x14010bf12  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010bf17  call    cs:__imp_RtlEndEnumerationHashTable
0x14010bf1e  nop     dword ptr [rax+rax+00h]
0x14010bf23  mov     eax, esi
0x14010bf25  add     rsp, 78h
0x14010bf29  pop     rdi
0x14010bf2a  pop     rsi
0x14010bf2b  pop     rbp
0x14010bf2c  pop     rbx
0x14010bf2d  retn
```
