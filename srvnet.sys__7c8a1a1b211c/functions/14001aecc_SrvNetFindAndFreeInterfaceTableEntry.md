# SrvNetFindAndFreeInterfaceTableEntry

- ea: `0x14001aecc`
- end: `0x14001af90`
- name: `SrvNetFindAndFreeInterfaceTableEntry`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010d94`

## callees

- `0x14001aecc`
- `0x14001b370`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001af14`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14001af14`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001aef7`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14001aef7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001af78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001af78`

## pseudocode

```c
char __fastcall SrvNetFindAndFreeInterfaceTableEntry(__int64 a1, ULONG_PTR a2, int a3)
{
  char v4; // bp
  struct _RTL_DYNAMIC_HASH_TABLE *v5; // rdi
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v6; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v7; // rbx
  int v8; // r8d
  const char *v9; // rax

  v4 = a1;
  v5 = (struct _RTL_DYNAMIC_HASH_TABLE *)((a3 != 0 ? 0x28 : 0) + a1 + 288);
  v6 = RtlLookupEntryHashTable(v5, a2, 0);
  v7 = v6;
  if ( v6 )
  {
    RtlRemoveEntryHashTable(v5, v6, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = "(IPV4)";
      if ( a3 )
        v9 = "(IPV6)";
      WPP_SF_Dsqq(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)"(IPV6)",
        v8,
        v7[1].Linkage.Flink->Flink,
        (__int64)v9,
        (char)v7[1].Linkage.Flink,
        v4);
    }
    ExFreePoolWithTag(v7, 0);
    LOBYTE(v6) = 1;
  }
  return (char)v6;
}

```

## disassembly

```asm
0x14001aecc  push    rbx
0x14001aece  push    rbp
0x14001aecf  push    rsi
0x14001aed0  push    rdi
0x14001aed1  sub     rsp, 48h
0x14001aed5  mov     eax, r8d
0x14001aed8  lea     rdi, [rcx+120h]
0x14001aedf  neg     eax
0x14001aee1  mov     esi, r8d
0x14001aee4  mov     rbp, rcx
0x14001aee7  sbb     r9, r9
0x14001aeea  xor     r8d, r8d; Context
0x14001aeed  and     r9d, 28h
0x14001aef1  add     rdi, r9
0x14001aef4  mov     rcx, rdi; HashTable
0x14001aef7  call    cs:__imp_RtlLookupEntryHashTable
0x14001aefe  nop     dword ptr [rax+rax+00h]
0x14001af03  mov     rbx, rax
0x14001af06  test    rax, rax
0x14001af09  jz      short loc_14001AF86
0x14001af0b  xor     r8d, r8d; Context
0x14001af0e  mov     rdx, rax; Entry
0x14001af11  mov     rcx, rdi; HashTable
0x14001af14  call    cs:__imp_RtlRemoveEntryHashTable
0x14001af1b  nop     dword ptr [rax+rax+00h]
0x14001af20  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001af27  lea     rax, WPP_GLOBAL_Control
0x14001af2e  cmp     rcx, rax
0x14001af31  jz      short loc_14001AF73
0x14001af33  mov     eax, [rcx+2Ch]
0x14001af36  test    al, 10h
0x14001af38  jz      short loc_14001AF73
0x14001af3a  cmp     byte ptr [rcx+29h], 2
0x14001af3e  jb      short loc_14001AF73
0x14001af40  mov     r9, [rbx+18h]
0x14001af44  lea     rdx, aIpv6; "(IPV6)"
0x14001af4b  mov     rcx, [rcx+18h]
0x14001af4f  lea     rax, aIpv4; "(IPV4)"
0x14001af56  test    esi, esi
0x14001af58  mov     [rsp+68h+var_38], rbp
0x14001af5d  mov     [rsp+68h+var_40], r9
0x14001af62  mov     r9d, [r9]
0x14001af65  cmovnz  rax, rdx
0x14001af69  mov     [rsp+68h+var_48], rax
0x14001af6e  call    WPP_SF_Dsqq
0x14001af73  xor     edx, edx; Tag
0x14001af75  mov     rcx, rbx; P
0x14001af78  call    cs:__imp_ExFreePoolWithTag
0x14001af7f  nop     dword ptr [rax+rax+00h]
0x14001af84  mov     al, 1
0x14001af86  add     rsp, 48h
0x14001af8a  pop     rdi
0x14001af8b  pop     rsi
0x14001af8c  pop     rbp
0x14001af8d  pop     rbx
0x14001af8e  retn
```
