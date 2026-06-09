# FlushEventEntryList

- ea: `0x140025f14`
- end: `0x140025fab`
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
- `0x140025f14`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140025f7a`
- `ntoskrnl!EtwWriteTransfer` at `0x140025f7a`

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
0x140025f14  test    rdx, rdx
0x140025f17  jz      locret_140025FA9
0x140025f1d  mov     [rsp+arg_0], rbx
0x140025f22  mov     [rsp+arg_8], rsi
0x140025f27  push    rdi
0x140025f28  sub     rsp, 30h
0x140025f2c  mov     rdi, rdx
0x140025f2f  mov     rsi, rcx
0x140025f32  movzx   eax, byte ptr [rdi+2Dh]
0x140025f36  mov     edx, 2
0x140025f3b  add     eax, edx
0x140025f3d  cmp     eax, edx
0x140025f3f  jbe     short loc_140025F5D
0x140025f41  mov     rax, [rdi+10h]
0x140025f45  movsxd  rcx, edx
0x140025f48  inc     edx
0x140025f4a  add     rcx, rcx
0x140025f4d  mov     byte ptr [rax+rcx*8+0Dh], 0
0x140025f52  movzx   eax, byte ptr [rdi+2Dh]
0x140025f56  add     eax, 2
0x140025f59  cmp     edx, eax
0x140025f5b  jl      short loc_140025F41
0x140025f5d  movzx   edx, byte ptr [rdi+2Ch]
0x140025f61  xor     r9d, r9d; RelatedActivityId
0x140025f64  mov     rax, [rdi+10h]
0x140025f68  xor     r8d, r8d; ActivityId
0x140025f6b  mov     [rsp+38h+UserData], rax; UserData
0x140025f70  mov     rcx, rsi; RegHandle
0x140025f73  mov     [rsp+38h+UserDataCount], edx; UserDataCount
0x140025f77  mov     rdx, rdi; EventDescriptor
0x140025f7a  call    cs:__imp_EtwWriteTransfer
0x140025f81  nop     dword ptr [rax+rax+00h]
0x140025f86  mov     rbx, [rdi+18h]
0x140025f8a  mov     rcx, rdi
0x140025f8d  call    DestroyEventEntry
0x140025f92  mov     rdi, rbx
0x140025f95  test    rbx, rbx
0x140025f98  jnz     short loc_140025F32
0x140025f9a  mov     rbx, [rsp+38h+arg_0]
0x140025f9f  mov     rsi, [rsp+38h+arg_8]
0x140025fa4  add     rsp, 30h
0x140025fa8  pop     rdi
0x140025fa9  retn
```
