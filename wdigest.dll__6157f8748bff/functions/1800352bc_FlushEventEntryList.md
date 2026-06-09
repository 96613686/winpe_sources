# FlushEventEntryList

- ea: `0x1800352bc`
- end: `0x18003534c`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035354`

## callees

- `0x180035234`
- `0x1800352bc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035322`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180035322`

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
      EventWriteTransfer(RegHandle, v2, 0, 0, BYTE4(v2[2].Keyword), *(PEVENT_DATA_DESCRIPTOR *)&v2[1].Id);
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
0x1800352bc  test    rdx, rdx
0x1800352bf  jz      locret_18003534B
0x1800352c5  mov     [rsp+arg_0], rbx
0x1800352ca  mov     [rsp+arg_8], rsi
0x1800352cf  push    rdi
0x1800352d0  sub     rsp, 30h
0x1800352d4  mov     rdi, rdx
0x1800352d7  mov     rsi, rcx
0x1800352da  movzx   eax, byte ptr [rdi+2Dh]
0x1800352de  mov     edx, 2
0x1800352e3  add     eax, edx
0x1800352e5  cmp     eax, edx
0x1800352e7  jbe     short loc_180035305
0x1800352e9  mov     rax, [rdi+10h]
0x1800352ed  movsxd  rcx, edx
0x1800352f0  inc     edx
0x1800352f2  add     rcx, rcx
0x1800352f5  mov     byte ptr [rax+rcx*8+0Dh], 0
0x1800352fa  movzx   eax, byte ptr [rdi+2Dh]
0x1800352fe  add     eax, 2
0x180035301  cmp     edx, eax
0x180035303  jl      short loc_1800352E9
0x180035305  movzx   edx, byte ptr [rdi+2Ch]
0x180035309  xor     r9d, r9d; RelatedActivityId
0x18003530c  mov     rax, [rdi+10h]
0x180035310  xor     r8d, r8d; ActivityId
0x180035313  mov     [rsp+38h+UserData], rax; UserData
0x180035318  mov     rcx, rsi; RegHandle
0x18003531b  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18003531f  mov     rdx, rdi; EventDescriptor
0x180035322  call    cs:__imp_EventWriteTransfer
0x180035328  mov     rbx, [rdi+18h]
0x18003532c  mov     rcx, rdi
0x18003532f  call    DestroyEventEntry
0x180035334  mov     rdi, rbx
0x180035337  test    rbx, rbx
0x18003533a  jnz     short loc_1800352DA
0x18003533c  mov     rbx, [rsp+38h+arg_0]
0x180035341  mov     rsi, [rsp+38h+arg_8]
0x180035346  add     rsp, 30h
0x18003534a  pop     rdi
0x18003534b  retn
```
