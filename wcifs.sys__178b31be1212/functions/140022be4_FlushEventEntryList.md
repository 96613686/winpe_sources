# FlushEventEntryList

- ea: `0x140022be4`
- end: `0x140022c7b`
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
- `0x140022be4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140022c4a`
- `ntoskrnl!EtwWriteTransfer` at `0x140022c4a`

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
0x140022be4  test    rdx, rdx
0x140022be7  jz      locret_140022C79
0x140022bed  mov     [rsp+arg_0], rbx
0x140022bf2  mov     [rsp+arg_8], rsi
0x140022bf7  push    rdi
0x140022bf8  sub     rsp, 30h
0x140022bfc  mov     rdi, rdx
0x140022bff  mov     rsi, rcx
0x140022c02  movzx   eax, byte ptr [rdi+2Dh]
0x140022c06  mov     edx, 2
0x140022c0b  add     eax, edx
0x140022c0d  cmp     eax, edx
0x140022c0f  jbe     short loc_140022C2D
0x140022c11  mov     rax, [rdi+10h]
0x140022c15  movsxd  rcx, edx
0x140022c18  inc     edx
0x140022c1a  add     rcx, rcx
0x140022c1d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140022c22  movzx   eax, byte ptr [rdi+2Dh]
0x140022c26  add     eax, 2
0x140022c29  cmp     edx, eax
0x140022c2b  jl      short loc_140022C11
0x140022c2d  movzx   edx, byte ptr [rdi+2Ch]
0x140022c31  xor     r9d, r9d; RelatedActivityId
0x140022c34  mov     rax, [rdi+10h]
0x140022c38  xor     r8d, r8d; ActivityId
0x140022c3b  mov     [rsp+38h+UserData], rax; UserData
0x140022c40  mov     rcx, rsi; RegHandle
0x140022c43  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x140022c47  mov     rdx, rdi; EventDescriptor
0x140022c4a  call    cs:__imp_EtwWriteTransfer
0x140022c51  nop     dword ptr [rax+rax+00h]
0x140022c56  mov     rbx, [rdi+18h]
0x140022c5a  mov     rcx, rdi
0x140022c5d  call    DestroyEventEntry
0x140022c62  mov     rdi, rbx
0x140022c65  test    rbx, rbx
0x140022c68  jnz     short loc_140022C02
0x140022c6a  mov     rbx, [rsp+38h+arg_0]
0x140022c6f  mov     rsi, [rsp+38h+arg_8]
0x140022c74  add     rsp, 30h
0x140022c78  pop     rdi
0x140022c79  retn
```
