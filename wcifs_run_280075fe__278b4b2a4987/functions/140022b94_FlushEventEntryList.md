# FlushEventEntryList

- ea: `0x140022b94`
- end: `0x140022c2b`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007588`

## callees

- `0x14000745c`
- `0x140022b94`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140022bfa`
- `ntoskrnl!EtwWriteTransfer` at `0x140022bfa`

## pseudocode

```c
__int64 __fastcall FlushEventEntryList(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)
{
  PCEVENT_DESCRIPTOR v2; // rdi
  int v4; // edx
  __int64 v5; // rcx
  const EVENT_DESCRIPTOR *Keyword; // rbx
  __int64 result; // rax

  if ( EventDescriptor )
  {
    v2 = EventDescriptor;
    do
    {
      v4 = 2;
      if ( (unsigned int)BYTE5(v2[2].Keyword) + 2 > 2 )
      {
        do
        {
          v5 = v4++;
          *(_BYTE *)(*(_QWORD *)&v2[1].Id + 16 * v5 + 13) = 0;
        }
        while ( v4 < BYTE5(v2[2].Keyword) + 2 );
      }
      EtwWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
      Keyword = (const EVENT_DESCRIPTOR *)v2[1].Keyword;
      result = DestroyEventEntry(v2);
      v2 = Keyword;
    }
    while ( Keyword );
  }
  return result;
}

```

## disassembly

```asm
0x140022b94  test    rdx, rdx
0x140022b97  jz      locret_140022C29
0x140022b9d  mov     [rsp+arg_0], rbx
0x140022ba2  mov     [rsp+arg_8], rsi
0x140022ba7  push    rdi
0x140022ba8  sub     rsp, 30h
0x140022bac  mov     rdi, rdx
0x140022baf  mov     rsi, rcx
0x140022bb2  movzx   eax, byte ptr [rdi+2Dh]
0x140022bb6  mov     edx, 2
0x140022bbb  add     eax, edx
0x140022bbd  cmp     eax, edx
0x140022bbf  jbe     short loc_140022BDD
0x140022bc1  mov     rax, [rdi+10h]
0x140022bc5  movsxd  rcx, edx
0x140022bc8  inc     edx
0x140022bca  add     rcx, rcx
0x140022bcd  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140022bd2  movzx   eax, byte ptr [rdi+2Dh]
0x140022bd6  add     eax, 2
0x140022bd9  cmp     edx, eax
0x140022bdb  jl      short loc_140022BC1
0x140022bdd  movzx   edx, byte ptr [rdi+2Ch]
0x140022be1  xor     r9d, r9d; RelatedActivityId
0x140022be4  mov     rax, [rdi+10h]
0x140022be8  xor     r8d, r8d; ActivityId
0x140022beb  mov     [rsp+38h+UserData], rax; UserData
0x140022bf0  mov     rcx, rsi; RegHandle
0x140022bf3  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x140022bf7  mov     rdx, rdi; EventDescriptor
0x140022bfa  call    cs:__imp_EtwWriteTransfer
0x140022c01  nop     dword ptr [rax+rax+00h]
0x140022c06  mov     rbx, [rdi+18h]
0x140022c0a  mov     rcx, rdi
0x140022c0d  call    DestroyEventEntry
0x140022c12  mov     rdi, rbx
0x140022c15  test    rbx, rbx
0x140022c18  jnz     short loc_140022BB2
0x140022c1a  mov     rbx, [rsp+38h+arg_0]
0x140022c1f  mov     rsi, [rsp+38h+arg_8]
0x140022c24  add     rsp, 30h
0x140022c28  pop     rdi
0x140022c29  retn
```
