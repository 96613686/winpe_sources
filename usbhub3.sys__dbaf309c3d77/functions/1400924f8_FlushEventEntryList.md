# FlushEventEntryList

- ea: `0x1400924f8`
- end: `0x14009258f`
- name: `FlushEventEntryList`
- size: `151`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140044d2c`

## callees

- `0x140044c88`
- `0x1400924f8`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14009255e`
- `ntoskrnl!EtwWriteTransfer` at `0x14009255e`

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
0x1400924f8  test    rdx, rdx
0x1400924fb  jz      locret_14009258D
0x140092501  mov     [rsp+arg_0], rbx
0x140092506  mov     [rsp+arg_8], rsi
0x14009250b  push    rdi
0x14009250c  sub     rsp, 30h
0x140092510  mov     rdi, rdx
0x140092513  mov     rsi, rcx
0x140092516  movzx   eax, byte ptr [rdi+2Dh]
0x14009251a  mov     edx, 2
0x14009251f  add     eax, edx
0x140092521  cmp     eax, edx
0x140092523  jbe     short loc_140092541
0x140092525  mov     rax, [rdi+10h]
0x140092529  movsxd  rcx, edx
0x14009252c  inc     edx
0x14009252e  add     rcx, rcx
0x140092531  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140092536  movzx   eax, byte ptr [rdi+2Dh]
0x14009253a  add     eax, 2
0x14009253d  cmp     edx, eax
0x14009253f  jl      short loc_140092525
0x140092541  movzx   edx, byte ptr [rdi+2Ch]
0x140092545  xor     r9d, r9d; RelatedActivityId
0x140092548  mov     rax, [rdi+10h]
0x14009254c  xor     r8d, r8d; ActivityId
0x14009254f  mov     [rsp+38h+UserData], rax; UserData
0x140092554  mov     rcx, rsi; RegHandle
0x140092557  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x14009255b  mov     rdx, rdi; EventDescriptor
0x14009255e  call    cs:__imp_EtwWriteTransfer
0x140092565  nop     dword ptr [rax+rax+00h]
0x14009256a  mov     rbx, [rdi+18h]
0x14009256e  mov     rcx, rdi
0x140092571  call    DestroyEventEntry
0x140092576  mov     rdi, rbx
0x140092579  test    rbx, rbx
0x14009257c  jnz     short loc_140092516
0x14009257e  mov     rbx, [rsp+38h+arg_0]
0x140092583  mov     rsi, [rsp+38h+arg_8]
0x140092588  add     rsp, 30h
0x14009258c  pop     rdi
0x14009258d  retn
```
