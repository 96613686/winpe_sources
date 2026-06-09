# VmsOmpDestroyInMemoryPropertiesHashTable

- ea: `0x140107358`
- end: `0x1401074a2`
- name: `VmsOmpDestroyInMemoryPropertiesHashTable`
- size: `330`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140070b04`
- `0x1400fc970`

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x14008497c`
- `0x140107358`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140107423`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140107423`
- `ntoskrnl!RtlDeleteHashTable` at `0x14010748a`
- `ntoskrnl!RtlDeleteHashTable` at `0x14010748a`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010747b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x14010747b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010745f`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x14010745f`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1401073b6`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1401073b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010743a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010744b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010743a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010744b`

## pseudocode

```c
__int64 __fastcall VmsOmpDestroyInMemoryPropertiesHashTable(PRTL_DYNAMIC_HASH_TABLE HashTable, int a2)
{
  int v3; // edx
  unsigned int v4; // esi
  int v5; // edx
  _LIST_ENTRY *Blink; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+40h] [rbp-58h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( !HashTable )
  {
    WPP_RECORDER_SF_s(
      VmsIfrLog,
      a2,
      19,
      109,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      "PropertiesHashTable != NULL");
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  }
  if ( RtlInitEnumerationHashTable(HashTable, &Enumerator) )
  {
    v4 = 0;
    while ( 1 )
    {
      v7 = RtlEnumerateEntryHashTable(HashTable, &Enumerator);
      v8 = v7;
      if ( !v7 )
        break;
      RtlRemoveEntryHashTable(HashTable, v7, 0);
      Blink = v8[3].Linkage.Blink;
      if ( Blink )
        ExFreePoolWithTag(Blink, 0);
      ExFreePoolWithTag(v8, 0);
    }
    RtlEndEnumerationHashTable(HashTable, &Enumerator);
    RtlDeleteHashTable(HashTable);
  }
  else
  {
    v4 = -1073741823;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrLog,
      v3,
      20,
      110,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (char)HashTable,
      1);
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_id(
      VmsIfrLog,
      v5,
      20,
      111,
      (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
      (char)HashTable,
      1);
  }
  return v4;
}

```

## disassembly

```asm
0x140107358  push    rbx
0x14010735a  push    rbp
0x14010735b  push    rsi
0x14010735c  push    rdi
0x14010735d  sub     rsp, 78h
0x140107361  xor     eax, eax
0x140107363  lea     rbp, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x14010736a  mov     qword ptr [rsp+98h+Enumerator.BucketIndex], rax
0x14010736f  xorps   xmm0, xmm0
0x140107372  mov     rbx, rcx
0x140107375  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x14010737a  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x14010737f  test    rcx, rcx
0x140107382  jnz     short loc_1401073AE
0x140107384  lea     rax, aPropertieshash; "PropertiesHashTable != NULL"
0x14010738b  lea     r9d, [rcx+6Dh]
0x14010738f  mov     [rsp+98h+var_70], rax
0x140107394  lea     r8d, [rcx+13h]
0x140107398  mov     [rsp+98h+var_78], rbp
0x14010739d  mov     rcx, cs:VmsIfrLog
0x1401073a4  call    WPP_RECORDER_SF_s
0x1401073a9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "PropertiesHashTable != ((void *)0)")
0x1401073ae  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1401073b3  mov     rcx, rbx; HashTable
0x1401073b6  call    cs:__imp_RtlInitEnumerationHashTable
0x1401073bd  nop     dword ptr [rax+rax+00h]
0x1401073c2  test    al, al
0x1401073c4  jnz     short loc_140107419
0x1401073c6  mov     esi, 0C0000001h
0x1401073cb  mov     rcx, cs:VmsIfrLog
0x1401073d2  mov     r9d, 6Eh ; 'n'
0x1401073d8  mov     [rsp+98h+var_68], esi
0x1401073dc  mov     dl, 2
0x1401073de  mov     [rsp+98h+var_70], rbx
0x1401073e3  mov     [rsp+98h+var_78], rbp
0x1401073e8  lea     edi, [r9-5Ah]
0x1401073ec  mov     r8d, edi
0x1401073ef  call    WPP_RECORDER_SF_id
0x1401073f4  mov     rcx, cs:VmsIfrLog
0x1401073fb  lea     r9d, [rdi+5Bh]
0x1401073ff  mov     [rsp+98h+var_68], esi
0x140107403  mov     r8d, edi
0x140107406  mov     [rsp+98h+var_70], rbx
0x14010740b  mov     dl, 2
0x14010740d  mov     [rsp+98h+var_78], rbp
0x140107412  call    WPP_RECORDER_SF_id
0x140107417  jmp     short loc_140107496
0x140107419  xor     esi, esi
0x14010741b  jmp     short loc_140107457
0x14010741d  xor     r8d, r8d; Context
0x140107420  mov     rdx, rdi; Entry
0x140107423  call    cs:__imp_RtlRemoveEntryHashTable
0x14010742a  nop     dword ptr [rax+rax+00h]
0x14010742f  mov     rcx, [rdi+50h]; P
0x140107433  test    rcx, rcx
0x140107436  jz      short loc_140107446
0x140107438  xor     edx, edx; Tag
0x14010743a  call    cs:__imp_ExFreePoolWithTag
0x140107441  nop     dword ptr [rax+rax+00h]
0x140107446  xor     edx, edx; Tag
0x140107448  mov     rcx, rdi; P
0x14010744b  call    cs:__imp_ExFreePoolWithTag
0x140107452  nop     dword ptr [rax+rax+00h]
0x140107457  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010745c  mov     rcx, rbx; HashTable
0x14010745f  call    cs:__imp_RtlEnumerateEntryHashTable
0x140107466  nop     dword ptr [rax+rax+00h]
0x14010746b  mov     rdi, rax
0x14010746e  mov     rcx, rbx; HashTable
0x140107471  test    rax, rax
0x140107474  jnz     short loc_14010741D
0x140107476  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x14010747b  call    cs:__imp_RtlEndEnumerationHashTable
0x140107482  nop     dword ptr [rax+rax+00h]
0x140107487  mov     rcx, rbx; HashTable
0x14010748a  call    cs:__imp_RtlDeleteHashTable
0x140107491  nop     dword ptr [rax+rax+00h]
0x140107496  mov     eax, esi
0x140107498  add     rsp, 78h
0x14010749c  pop     rdi
0x14010749d  pop     rsi
0x14010749e  pop     rbp
0x14010749f  pop     rbx
0x1401074a0  retn
```
