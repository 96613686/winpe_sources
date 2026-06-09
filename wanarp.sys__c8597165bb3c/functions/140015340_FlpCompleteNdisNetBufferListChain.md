# FlpCompleteNdisNetBufferListChain

- ea: `0x140015340`
- end: `0x140015435`
- name: `FlpCompleteNdisNetBufferListChain`
- size: `245`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferLists)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400152e0`

## callees

- `0x140015340`

## import_xrefs

- `NETIO!NetioFreeMdl` at `0x14001540c`
- `NETIO!NetioFreeMdl` at `0x14001540c`
- `NDIS!NdisAdjustNetBufferCurrentMdl` at `0x140015424`
- `NDIS!NdisAdjustNetBufferCurrentMdl` at `0x140015424`
- `NDIS!NdisReturnNetBufferLists` at `0x1400153e0`
- `NDIS!NdisReturnNetBufferLists` at `0x1400153e0`

## pseudocode

```c
void __fastcall FlpCompleteNdisNetBufferListChain(PNET_BUFFER_LIST NetBufferLists, __int64 a2, unsigned __int8 a3)
{
  ULONG v4; // r15d
  PNET_BUFFER_LIST Alignment; // r14
  char v6; // r12
  PNET_BUFFER i; // rbx
  int v8; // esi
  bool v9; // zf
  int v10; // esi
  PMDL v11; // rcx
  ULONG v12; // eax
  PNET_BUFFER_LIST v13; // rax
  NDIS_HANDLE v14; // rcx
  PMDL MdlChain; // rcx

  v4 = a3;
  Alignment = NetBufferLists;
  v6 = *((_BYTE *)NetBufferLists->ProtocolReserved[3] + 4);
  do
  {
    for ( i = Alignment->FirstNetBuffer; i; i = (PNET_BUFFER)i->Link.Alignment )
    {
      v8 = i->DataLength + i->DataOffset - LODWORD(i->ProtocolReserved[0]) - HIDWORD(i->ProtocolReserved[0]);
      v9 = LODWORD(i->ProtocolReserved[1]) + v8 == 0;
      v10 = LODWORD(i->ProtocolReserved[1]) + v8;
      LODWORD(i->ProtocolReserved[1]) = 0;
      if ( !v9 )
      {
        do
        {
          MdlChain = i->MdlChain;
          i->MdlChain = MdlChain->Next;
          v10 -= MdlChain->ByteCount;
          NetioFreeMdl();
        }
        while ( v10 );
      }
      v11 = i->MdlChain;
      i->DataLength = HIDWORD(i->ProtocolReserved[0]);
      v12 = (ULONG)i->ProtocolReserved[0];
      i->DataOffset = v12;
      i->Link.Region = (ULONGLONG)v11;
      i->CurrentMdlOffset = v12;
      if ( v11 && v12 > v11->ByteCount )
        NdisAdjustNetBufferCurrentMdl(i);
    }
    Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
  }
  while ( Alignment );
  v13 = NetBufferLists;
  do
  {
    _InterlockedIncrement(&glReturnedNbls);
    v13 = (PNET_BUFFER_LIST)v13->Link.Alignment;
  }
  while ( v13 );
  v14 = (NDIS_HANDLE)qword_1400099E8;
  if ( !v6 )
    v14 = NdisBindingHandle;
  NdisReturnNetBufferLists(v14, NetBufferLists, v4);
}

```

## disassembly

```asm
0x140015340  push    rbx
0x140015342  push    rbp
0x140015343  push    rsi
0x140015344  push    rdi
0x140015345  push    r12
0x140015347  push    r13
0x140015349  push    r14
0x14001534b  push    r15
0x14001534d  sub     rsp, 28h
0x140015351  mov     rax, [rcx+58h]
0x140015355  mov     rbp, rcx
0x140015358  movzx   r15d, r8b
0x14001535c  mov     r14, rcx
0x14001535f  xor     r13d, r13d
0x140015362  movzx   r12d, byte ptr [rax+4]
0x140015367  mov     rbx, [r14+8]
0x14001536b  test    rbx, rbx
0x14001536e  jz      short loc_1400153AE
0x140015370  mov     esi, [rbx+28h]
0x140015373  sub     esi, [rbx+50h]
0x140015376  sub     esi, [rbx+54h]
0x140015379  add     esi, [rbx+18h]
0x14001537c  add     esi, [rbx+58h]
0x14001537f  mov     [rbx+58h], r13d
0x140015383  jnz     short loc_1400153FE
0x140015385  mov     eax, [rbx+54h]
0x140015388  mov     rcx, [rbx+20h]
0x14001538c  mov     [rbx+18h], eax
0x14001538f  mov     eax, [rbx+50h]
0x140015392  mov     [rbx+28h], eax
0x140015395  mov     [rbx+8], rcx
0x140015399  mov     [rbx+10h], eax
0x14001539c  test    rcx, rcx
0x14001539f  jz      short loc_1400153A6
0x1400153a1  cmp     eax, [rcx+28h]
0x1400153a4  ja      short loc_140015421
0x1400153a6  mov     rbx, [rbx]
0x1400153a9  test    rbx, rbx
0x1400153ac  jnz     short loc_140015370
0x1400153ae  mov     r14, [r14]
0x1400153b1  test    r14, r14
0x1400153b4  jnz     short loc_140015367
0x1400153b6  mov     rax, rbp
0x1400153b9  lock inc cs:glReturnedNbls
0x1400153c0  mov     rax, [rax]
0x1400153c3  test    rax, rax
0x1400153c6  jnz     short loc_1400153B9
0x1400153c8  mov     rcx, cs:qword_1400099E8
0x1400153cf  test    r12b, r12b
0x1400153d2  mov     r8d, r15d; ReturnFlags
0x1400153d5  mov     rdx, rbp; NetBufferLists
0x1400153d8  cmovz   rcx, cs:NdisBindingHandle; NdisBindingHandle
0x1400153e0  call    cs:__imp_NdisReturnNetBufferLists
0x1400153e7  nop     dword ptr [rax+rax+00h]
0x1400153ec  add     rsp, 28h
0x1400153f0  pop     r15
0x1400153f2  pop     r14
0x1400153f4  pop     r13
0x1400153f6  pop     r12
0x1400153f8  pop     rdi
0x1400153f9  pop     rsi
0x1400153fa  pop     rbp
0x1400153fb  pop     rbx
0x1400153fc  retn
0x1400153fe  mov     rcx, [rbx+20h]
0x140015402  mov     rax, [rcx]
0x140015405  mov     [rbx+20h], rax
0x140015409  sub     esi, [rcx+28h]
0x14001540c  call    cs:__imp_NetioFreeMdl
0x140015413  nop     dword ptr [rax+rax+00h]
0x140015418  test    esi, esi
0x14001541a  jnz     short loc_1400153FE
0x14001541c  jmp     loc_140015385
0x140015421  mov     rcx, rbx; NetBuffer
0x140015424  call    cs:__imp_NdisAdjustNetBufferCurrentMdl
0x14001542b  nop     dword ptr [rax+rax+00h]
0x140015430  jmp     loc_1400153A6
```
