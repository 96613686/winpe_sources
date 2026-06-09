# FlushEventEntryList

- ea: `0x140025f64`
- end: `0x140025ffb`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f9d0`

## callees

- `0x14000f948`
- `0x140025f64`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140025fca`
- `ntoskrnl!EtwWriteTransfer` at `0x140025fca`

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
0x140025f64  test    rdx, rdx
0x140025f67  jz      locret_140025FF9
0x140025f6d  mov     [rsp+arg_0], rbx
0x140025f72  mov     [rsp+arg_8], rsi
0x140025f77  push    rdi
0x140025f78  sub     rsp, 30h
0x140025f7c  mov     rdi, rdx
0x140025f7f  mov     rsi, rcx
0x140025f82  movzx   eax, byte ptr [rdi+2Dh]
0x140025f86  mov     edx, 2
0x140025f8b  add     eax, edx
0x140025f8d  cmp     eax, edx
0x140025f8f  jbe     short loc_140025FAD
0x140025f91  mov     rax, [rdi+10h]
0x140025f95  movsxd  rcx, edx
0x140025f98  inc     edx
0x140025f9a  add     rcx, rcx
0x140025f9d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140025fa2  movzx   eax, byte ptr [rdi+2Dh]
0x140025fa6  add     eax, 2
0x140025fa9  cmp     edx, eax
0x140025fab  jl      short loc_140025F91
0x140025fad  movzx   edx, byte ptr [rdi+2Ch]
0x140025fb1  xor     r9d, r9d; RelatedActivityId
0x140025fb4  mov     rax, [rdi+10h]
0x140025fb8  xor     r8d, r8d; ActivityId
0x140025fbb  mov     [rsp+38h+UserData], rax; UserData
0x140025fc0  mov     rcx, rsi; RegHandle
0x140025fc3  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x140025fc7  mov     rdx, rdi; EventDescriptor
0x140025fca  call    cs:__imp_EtwWriteTransfer
0x140025fd1  nop     dword ptr [rax+rax+00h]
0x140025fd6  mov     rbx, [rdi+18h]
0x140025fda  mov     rcx, rdi
0x140025fdd  call    DestroyEventEntry
0x140025fe2  mov     rdi, rbx
0x140025fe5  test    rbx, rbx
0x140025fe8  jnz     short loc_140025F82
0x140025fea  mov     rbx, [rsp+38h+arg_0]
0x140025fef  mov     rsi, [rsp+38h+arg_8]
0x140025ff4  add     rsp, 30h
0x140025ff8  pop     rdi
0x140025ff9  retn
```
