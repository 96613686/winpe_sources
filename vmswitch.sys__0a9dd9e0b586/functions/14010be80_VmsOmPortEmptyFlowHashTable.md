# VmsOmPortEmptyFlowHashTable

- ea: `0x14010be80`
- end: `0x14010bf9f`
- name: `VmsOmPortEmptyFlowHashTable`
- size: `287`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14010e698`
- `0x140157e80`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x140046f1c`
- `0x14008497c`
- `0x14010be80`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010bf46`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14010bf46`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010bf87`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010bf87`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010bf6b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010bf6b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010bede`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x14010bede`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010bf57`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010bf57`

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
0x14010be80  push    rbx
0x14010be82  push    rbp
0x14010be83  push    rsi
0x14010be84  push    rdi
0x14010be85  sub     rsp, 78h
0x14010be89  xor     eax, eax
0x14010be8b  lea     rbp, WPP_2ef67749ba943892c5000d964b576d2d_Traceguids
0x14010be92  mov     qword ptr [rsp+98h+Enumerator.BucketIndex], rax
0x14010be97  xorps   xmm0, xmm0
0x14010be9a  mov     rbx, rcx
0x14010be9d  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x14010bea2  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x14010bea7  test    rcx, rcx
0x14010beaa  jnz     short loc_14010BED6
0x14010beac  lea     rax, aFlowhashtableN; "FlowHashTable != NULL"
0x14010beb3  lea     r9d, [rcx+64h]
0x14010beb7  mov     [rsp+98h+var_70], rax
0x14010bebc  lea     r8d, [rcx+13h]
0x14010bec0  mov     [rsp+98h+var_78], rbp
0x14010bec5  mov     rcx, cs:VmsIfrLog
0x14010becc  call    WPP_RECORDER_SF_s
0x14010bed1  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "FlowHashTable != ((void *)0)")
0x14010bed6  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010bedb  mov     rcx, rbx; HashTable
0x14010bede  call    cs:__imp_RtlInitEnumerationHashTable
0x14010bee5  nop     dword ptr [rax+rax+00h]
0x14010beea  test    al, al
0x14010beec  jnz     short loc_14010BF3C
0x14010beee  mov     esi, 0C0000001h
0x14010bef3  mov     rcx, cs:VmsIfrLog
0x14010befa  mov     r9d, 65h ; 'e'
0x14010bf00  mov     dword ptr [rsp+98h+var_70], esi
0x14010bf04  mov     dl, 2
0x14010bf06  mov     [rsp+98h+var_78], rbp
0x14010bf0b  lea     edi, [r9-51h]
0x14010bf0f  mov     r8d, edi
0x14010bf12  call    WPP_RECORDER_SF_d
0x14010bf17  mov     rcx, cs:VmsIfrLog
0x14010bf1e  lea     r9d, [rdi+52h]
0x14010bf22  mov     [rsp+98h+var_68], esi
0x14010bf26  mov     r8d, edi
0x14010bf29  mov     [rsp+98h+var_70], rbx
0x14010bf2e  mov     dl, 2
0x14010bf30  mov     [rsp+98h+var_78], rbp
0x14010bf35  call    WPP_RECORDER_SF_id
0x14010bf3a  jmp     short loc_14010BF93
0x14010bf3c  xor     esi, esi
0x14010bf3e  jmp     short loc_14010BF63
0x14010bf40  xor     r8d, r8d; Context
0x14010bf43  mov     rdx, rdi; Entry
0x14010bf46  call    cs:__imp_RtlRemoveEntryHashTable
0x14010bf4d  nop     dword ptr [rax+rax+00h]
0x14010bf52  xor     edx, edx; Tag
0x14010bf54  mov     rcx, rdi; P
0x14010bf57  call    cs:__imp_ExFreePoolWithTag
0x14010bf5e  nop     dword ptr [rax+rax+00h]
0x14010bf63  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010bf68  mov     rcx, rbx; HashTable
0x14010bf6b  call    cs:__imp_RtlEnumerateEntryHashTable
0x14010bf72  nop     dword ptr [rax+rax+00h]
0x14010bf77  mov     rdi, rax
0x14010bf7a  mov     rcx, rbx; HashTable
0x14010bf7d  test    rax, rax
0x14010bf80  jnz     short loc_14010BF40
0x14010bf82  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010bf87  call    cs:__imp_RtlEndEnumerationHashTable
0x14010bf8e  nop     dword ptr [rax+rax+00h]
0x14010bf93  mov     eax, esi
0x14010bf95  add     rsp, 78h
0x14010bf99  pop     rdi
0x14010bf9a  pop     rsi
0x14010bf9b  pop     rbp
0x14010bf9c  pop     rbx
0x14010bf9d  retn
```
