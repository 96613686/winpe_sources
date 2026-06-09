# VmsOmpDestroyInMemoryPropertiesHashTable

- ea: `0x1401073c8`
- end: `0x140107512`
- name: `VmsOmpDestroyInMemoryPropertiesHashTable`
- size: `330`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140070b04`
- `0x1400fc9e0`

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x14008497c`
- `0x1401073c8`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140107493`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140107493`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401074fa`
- `ntoskrnl!RtlDeleteHashTable` at `0x1401074fa`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401074eb`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1401074eb`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1401074cf`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1401074cf`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140107426`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140107426`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401074aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401074bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401074aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401074bb`

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
0x1401073c8  push    rbx
0x1401073ca  push    rbp
0x1401073cb  push    rsi
0x1401073cc  push    rdi
0x1401073cd  sub     rsp, 78h
0x1401073d1  xor     eax, eax
0x1401073d3  lea     rbp, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x1401073da  mov     qword ptr [rsp+98h+Enumerator.BucketIndex], rax
0x1401073df  xorps   xmm0, xmm0
0x1401073e2  mov     rbx, rcx
0x1401073e5  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x1401073ea  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x1401073ef  test    rcx, rcx
0x1401073f2  jnz     short loc_14010741E
0x1401073f4  lea     rax, aPropertieshash; "PropertiesHashTable != NULL"
0x1401073fb  lea     r9d, [rcx+6Dh]
0x1401073ff  mov     [rsp+98h+var_70], rax
0x140107404  lea     r8d, [rcx+13h]
0x140107408  mov     [rsp+98h+var_78], rbp
0x14010740d  mov     rcx, cs:VmsIfrLog
0x140107414  call    WPP_RECORDER_SF_s
0x140107419  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "PropertiesHashTable != ((void *)0)")
0x14010741e  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x140107423  mov     rcx, rbx; HashTable
0x140107426  call    cs:__imp_RtlInitEnumerationHashTable
0x14010742d  nop     dword ptr [rax+rax+00h]
0x140107432  test    al, al
0x140107434  jnz     short loc_140107489
0x140107436  mov     esi, 0C0000001h
0x14010743b  mov     rcx, cs:VmsIfrLog
0x140107442  mov     r9d, 6Eh ; 'n'
0x140107448  mov     [rsp+98h+var_68], esi
0x14010744c  mov     dl, 2
0x14010744e  mov     [rsp+98h+var_70], rbx
0x140107453  mov     [rsp+98h+var_78], rbp
0x140107458  lea     edi, [r9-5Ah]
0x14010745c  mov     r8d, edi
0x14010745f  call    WPP_RECORDER_SF_id
0x140107464  mov     rcx, cs:VmsIfrLog
0x14010746b  lea     r9d, [rdi+5Bh]
0x14010746f  mov     [rsp+98h+var_68], esi
0x140107473  mov     r8d, edi
0x140107476  mov     [rsp+98h+var_70], rbx
0x14010747b  mov     dl, 2
0x14010747d  mov     [rsp+98h+var_78], rbp
0x140107482  call    WPP_RECORDER_SF_id
0x140107487  jmp     short loc_140107506
0x140107489  xor     esi, esi
0x14010748b  jmp     short loc_1401074C7
0x14010748d  xor     r8d, r8d; Context
0x140107490  mov     rdx, rdi; Entry
0x140107493  call    cs:__imp_RtlRemoveEntryHashTable
0x14010749a  nop     dword ptr [rax+rax+00h]
0x14010749f  mov     rcx, [rdi+50h]; P
0x1401074a3  test    rcx, rcx
0x1401074a6  jz      short loc_1401074B6
0x1401074a8  xor     edx, edx; Tag
0x1401074aa  call    cs:__imp_ExFreePoolWithTag
0x1401074b1  nop     dword ptr [rax+rax+00h]
0x1401074b6  xor     edx, edx; Tag
0x1401074b8  mov     rcx, rdi; P
0x1401074bb  call    cs:__imp_ExFreePoolWithTag
0x1401074c2  nop     dword ptr [rax+rax+00h]
0x1401074c7  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1401074cc  mov     rcx, rbx; HashTable
0x1401074cf  call    cs:__imp_RtlEnumerateEntryHashTable
0x1401074d6  nop     dword ptr [rax+rax+00h]
0x1401074db  mov     rdi, rax
0x1401074de  mov     rcx, rbx; HashTable
0x1401074e1  test    rax, rax
0x1401074e4  jnz     short loc_14010748D
0x1401074e6  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1401074eb  call    cs:__imp_RtlEndEnumerationHashTable
0x1401074f2  nop     dword ptr [rax+rax+00h]
0x1401074f7  mov     rcx, rbx; HashTable
0x1401074fa  call    cs:__imp_RtlDeleteHashTable
0x140107501  nop     dword ptr [rax+rax+00h]
0x140107506  mov     eax, esi
0x140107508  add     rsp, 78h
0x14010750c  pop     rdi
0x14010750d  pop     rsi
0x14010750e  pop     rbp
0x14010750f  pop     rbx
0x140107510  retn
```
