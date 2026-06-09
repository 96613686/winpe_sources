# WcInitializeDirectoryTable

- ea: `0x14001e80c`
- end: `0x14001e944`
- name: `WcInitializeDirectoryTable`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000696c`
- `0x140020e60`

## callees

- `0x1400020c4`
- `0x14001e80c`

## import_xrefs

- `ntoskrnl!RtlCreateHashTableEx` at `0x14001e829`
- `ntoskrnl!RtlCreateHashTableEx` at `0x14001e829`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001e91c`
- `ntoskrnl!RtlDeleteHashTable` at `0x14001e91c`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001e92f`
- `ntoskrnl!ExInitializeResourceLite` at `0x14001e92f`
- `ntoskrnl!ExAllocatePool2` at `0x14001e8a9`
- `ntoskrnl!ExAllocatePool2` at `0x14001e8a9`

## pseudocode

```c
__int64 __fastcall WcInitializeDirectoryTable(__int64 a1, __int64 a2)
{
  int v3; // edx
  unsigned int v4; // ebx
  struct _ERESOURCE *Pool2; // rax
  int v6; // edx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+50h] [rbp+8h] BYREF

  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(a1 + 72);
  if ( (unsigned __int8)RtlCreateHashTableEx(&HashTable, a2, 0, 0) )
  {
    Pool2 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 2037138263);
    *(_QWORD *)(a1 + 64) = Pool2;
    if ( Pool2 )
    {
      v4 = 0;
      ExInitializeResourceLite(Pool2);
    }
    else
    {
      v4 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_sDd(
          wil_details_featureDescriptors_a->DeviceExtension,
          v6,
          11,
          204,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          129,
          154);
      }
      RtlDeleteHashTable(HashTable);
    }
  }
  else
  {
    v4 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_sDd(
        wil_details_featureDescriptors_a->DeviceExtension,
        v3,
        11,
        203,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        118,
        154);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14001e80c  push    rbx
0x14001e80e  sub     rsp, 40h
0x14001e812  lea     rax, [rcx+48h]
0x14001e816  mov     rbx, rcx
0x14001e819  lea     rcx, [rsp+48h+HashTable]
0x14001e81e  mov     [rsp+48h+HashTable], rax
0x14001e823  xor     r9d, r9d
0x14001e826  xor     r8d, r8d
0x14001e829  call    cs:__imp_RtlCreateHashTableEx
0x14001e830  nop     dword ptr [rax+rax+00h]
0x14001e835  test    al, al
0x14001e837  jnz     short loc_14001E89B
0x14001e839  mov     eax, 0C000009Ah
0x14001e83e  mov     ebx, eax
0x14001e840  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e847  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e84e  jz      loc_14001E93B
0x14001e854  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001e85b  mov     r9d, 0CBh
0x14001e861  mov     [rsp+48h+var_10], eax
0x14001e865  mov     r8d, 0Bh
0x14001e86b  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e872  mov     [rsp+48h+var_18], 2476h
0x14001e87a  mov     [rsp+48h+var_20], rax
0x14001e87f  mov     dl, 2
0x14001e881  mov     rcx, [rcx+40h]
0x14001e885  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e88c  mov     [rsp+48h+var_28], rax
0x14001e891  call    WPP_RECORDER_SF_sDd
0x14001e896  jmp     loc_14001E93B
0x14001e89b  mov     edx, 68h ; 'h'
0x14001e8a0  mov     r8d, 796C4357h
0x14001e8a6  lea     ecx, [rdx-28h]
0x14001e8a9  call    cs:__imp_ExAllocatePool2
0x14001e8b0  nop     dword ptr [rax+rax+00h]
0x14001e8b5  mov     [rbx+40h], rax
0x14001e8b9  test    rax, rax
0x14001e8bc  jnz     short loc_14001E92A
0x14001e8be  mov     eax, 0C000009Ah
0x14001e8c3  mov     ebx, eax
0x14001e8c5  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001e8cc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001e8d3  jz      short loc_14001E917
0x14001e8d5  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001e8dc  mov     r9d, 0CCh
0x14001e8e2  mov     [rsp+48h+var_10], eax
0x14001e8e6  mov     r8d, 0Bh
0x14001e8ec  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e8f3  mov     [rsp+48h+var_18], 2481h
0x14001e8fb  mov     [rsp+48h+var_20], rax
0x14001e900  mov     dl, 2
0x14001e902  mov     rcx, [rcx+40h]
0x14001e906  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e90d  mov     [rsp+48h+var_28], rax
0x14001e912  call    WPP_RECORDER_SF_sDd
0x14001e917  mov     rcx, [rsp+48h+HashTable]; HashTable
0x14001e91c  call    cs:__imp_RtlDeleteHashTable
0x14001e923  nop     dword ptr [rax+rax+00h]
0x14001e928  jmp     short loc_14001E93B
0x14001e92a  xor     ebx, ebx
0x14001e92c  mov     rcx, rax; Resource
0x14001e92f  call    cs:__imp_ExInitializeResourceLite
0x14001e936  nop     dword ptr [rax+rax+00h]
0x14001e93b  mov     eax, ebx
0x14001e93d  add     rsp, 40h
0x14001e941  pop     rbx
0x14001e942  retn
```
