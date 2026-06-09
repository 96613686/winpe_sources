# FlushEventEntryList

- ea: `0x18000b0d4`
- end: `0x18000b164`
- name: `FlushEventEntryList`
- size: `144`
- prototype: `__int64 __fastcall(REGHANDLE RegHandle, PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b16c`

## callees

- `0x18000b04c`
- `0x18000b0d4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b13a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b13a`

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
0x18000b0d4  test    rdx, rdx
0x18000b0d7  jz      locret_18000B163
0x18000b0dd  mov     [rsp+arg_0], rbx
0x18000b0e2  mov     [rsp+arg_8], rsi
0x18000b0e7  push    rdi
0x18000b0e8  sub     rsp, 30h
0x18000b0ec  mov     rdi, rdx
0x18000b0ef  mov     rsi, rcx
0x18000b0f2  movzx   eax, byte ptr [rdi+2Dh]
0x18000b0f6  mov     edx, 2
0x18000b0fb  add     eax, edx
0x18000b0fd  cmp     eax, edx
0x18000b0ff  jbe     short loc_18000B11D
0x18000b101  mov     rax, [rdi+10h]
0x18000b105  movsxd  rcx, edx
0x18000b108  inc     edx
0x18000b10a  add     rcx, rcx
0x18000b10d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x18000b112  movzx   eax, byte ptr [rdi+2Dh]
0x18000b116  add     eax, 2
0x18000b119  cmp     edx, eax
0x18000b11b  jl      short loc_18000B101
0x18000b11d  movzx   edx, byte ptr [rdi+2Ch]
0x18000b121  xor     r9d, r9d; RelatedActivityId
0x18000b124  mov     rax, [rdi+10h]
0x18000b128  xor     r8d, r8d; ActivityId
0x18000b12b  mov     [rsp+38h+UserData], rax; UserData
0x18000b130  mov     rcx, rsi; RegHandle
0x18000b133  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x18000b137  mov     rdx, rdi; EventDescriptor
0x18000b13a  call    cs:__imp_EventWriteTransfer
0x18000b140  mov     rbx, [rdi+18h]
0x18000b144  mov     rcx, rdi
0x18000b147  call    DestroyEventEntry
0x18000b14c  mov     rdi, rbx
0x18000b14f  test    rbx, rbx
0x18000b152  jnz     short loc_18000B0F2
0x18000b154  mov     rbx, [rsp+38h+arg_0]
0x18000b159  mov     rsi, [rsp+38h+arg_8]
0x18000b15e  add     rsp, 30h
0x18000b162  pop     rdi
0x18000b163  retn
```
