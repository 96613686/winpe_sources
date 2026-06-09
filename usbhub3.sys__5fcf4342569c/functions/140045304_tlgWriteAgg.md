# _tlgWriteAgg

- ea: `0x140045304`
- end: `0x140045451`
- name: `_tlgWriteAgg`
- size: `333`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a308`
- `0x140087aa8`
- `0x14008d9e0`

## callees

- `0x140044e4c`
- `0x140045304`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14004543f`
- `ntoskrnl!EtwWriteTransfer` at `0x14004543f`

## pseudocode

```c
NTSTATUS __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  int v6; // r8d
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rdx
  NTSTATUS result; // eax
  unsigned __int64 Ptr; // rax
  unsigned __int8 v11; // r9
  unsigned __int64 v12; // r10
  char *v13; // rcx
  char v14; // al
  char v17; // al
  char v18; // dl
  __int64 v19; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-18h] BYREF

  v6 = (int)UserData;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v7 = *(_QWORD *)(a2 + 3);
  v8 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v7;
  UserData->Ptr = (unsigned __int64)off_14006B2D8;
  UserData->Size = *(unsigned __int16 *)off_14006B2D8;
  UserData->Reserved = 2;
  UserData[1].Ptr = (unsigned __int64)v8;
  UserData[1].Size = *v8;
  UserData[1].Reserved = 1;
  result = -1073741811;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_14006B2F8 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v11 = 0;
    v12 = Ptr + UserData[1].Size;
    v13 = (char *)(Ptr + 2);
    do
      v14 = *v13++;
    while ( v14 < 0 );
    while ( *v13++ )
      ;
    while ( (unsigned __int64)v13 < v12 )
    {
      while ( *v13++ )
        ;
      if ( *v13 >= 0 )
        break;
      v17 = *v13 & 0x7F;
      if ( v13[1] >= 0 )
        break;
      for ( v13 += 2; ; ++v13 )
      {
        v18 = *v13;
        if ( *v13 >= 0 )
          break;
        if ( v18 != (char)0x80 )
          goto LABEL_17;
      }
      if ( v17 != 9 || (unsigned __int8)(v18 - 113) > 2u )
        break;
      v19 = v11++;
      UserData[v19 + 2].Reserved1 = v18;
    }
LABEL_17:
    if ( v11 )
    {
      LOBYTE(v6) = a4;
      return InsertEventEntryInLookUpTable((_DWORD)v13, (unsigned int)&EventDescriptor, v6, (_DWORD)UserData, v11);
    }
    else
    {
      return EtwWriteTransfer(qword_14006B2F0, &EventDescriptor, 0, 0, a4, UserData);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140045304  mov     [rsp+arg_10], r8
0x140045309  sub     rsp, 48h
0x14004530d  movzx   eax, byte ptr [rdx]
0x140045310  mov     r11d, r9d
0x140045313  mov     r8, [rsp+48h+arg_20]
0x140045318  shl     eax, 18h
0x14004531b  mov     dword ptr [rsp+48h+EventDescriptor.Id], eax
0x14004531f  movzx   eax, word ptr [rdx+1]
0x140045323  mov     dword ptr [rsp+48h+EventDescriptor.Level], eax
0x140045327  mov     rax, [rdx+3]
0x14004532b  add     rdx, 0Bh
0x14004532f  mov     [rsp+48h+EventDescriptor.Keyword], rax
0x140045334  mov     rax, cs:off_14006B2D8
0x14004533b  mov     [r8], rax
0x14004533e  mov     rax, cs:off_14006B2D8
0x140045345  movzx   ecx, word ptr [rax]
0x140045348  mov     [r8+8], ecx
0x14004534c  lea     rcx, _TraceLoggingMetadata
0x140045353  mov     dword ptr [r8+0Ch], 2
0x14004535b  mov     [r8+10h], rdx
0x14004535f  movzx   eax, word ptr [rdx]
0x140045362  mov     [r8+18h], eax
0x140045366  lea     rax, _TraceLoggingMetadataEnd
0x14004536d  sub     eax, ecx
0x14004536f  mov     dword ptr [r8+1Ch], 1
0x140045377  mov     dword ptr [rsp+48h+arg_10], eax
0x14004537b  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140045382  mov     eax, dword ptr [rsp+48h+arg_10]
0x140045386  cmp     cs:qword_14006B2F8, rcx
0x14004538d  mov     eax, 0C000000Dh
0x140045392  jnz     loc_14004544B
0x140045398  mov     rax, [r8+10h]
0x14004539c  xor     r9b, r9b
0x14004539f  mov     r10d, [r8+18h]
0x1400453a3  add     r10, rax
0x1400453a6  lea     rcx, [rax+2]
0x1400453aa  movzx   eax, byte ptr [rcx]
0x1400453ad  inc     rcx
0x1400453b0  test    al, al
0x1400453b2  js      short loc_1400453AA
0x1400453b4  mov     al, [rcx]
0x1400453b6  inc     rcx
0x1400453b9  test    al, al
0x1400453bb  jnz     short loc_1400453B4
0x1400453bd  jmp     short loc_140045404
0x1400453bf  mov     al, [rcx]
0x1400453c1  inc     rcx
0x1400453c4  test    al, al
0x1400453c6  jnz     short loc_1400453BF
0x1400453c8  mov     al, [rcx]
0x1400453ca  test    al, al
0x1400453cc  jns     short loc_140045409
0x1400453ce  and     al, 7Fh
0x1400453d0  cmp     byte ptr [rcx+1], 0
0x1400453d4  jge     short loc_140045409
0x1400453d6  add     rcx, 2
0x1400453da  jmp     short loc_1400453E4
0x1400453dc  cmp     dl, 80h
0x1400453df  jnz     short loc_140045409
0x1400453e1  inc     rcx
0x1400453e4  mov     dl, [rcx]
0x1400453e6  test    dl, dl
0x1400453e8  js      short loc_1400453DC
0x1400453ea  cmp     al, 9
0x1400453ec  jnz     short loc_140045409
0x1400453ee  lea     eax, [rdx-71h]
0x1400453f1  cmp     al, 2
0x1400453f3  ja      short loc_140045409
0x1400453f5  movzx   eax, r9b
0x1400453f9  add     rax, rax
0x1400453fc  inc     r9b
0x1400453ff  mov     [r8+rax*8+2Dh], dl
0x140045404  cmp     rcx, r10
0x140045407  jb      short loc_1400453BF
0x140045409  lea     rdx, [rsp+48h+EventDescriptor]; EventDescriptor
0x14004540e  test    r9b, r9b
0x140045411  jz      short loc_140045425
0x140045413  mov     byte ptr [rsp+48h+UserDataCount], r9b
0x140045418  mov     r9, r8
0x14004541b  mov     r8b, r11b
0x14004541e  call    InsertEventEntryInLookUpTable
0x140045423  jmp     short loc_14004544B
0x140045425  mov     rcx, cs:qword_14006B2F0; RegHandle
0x14004542c  xor     r9d, r9d; RelatedActivityId
0x14004542f  mov     [rsp+48h+UserData], r8; UserData
0x140045434  xor     r8d, r8d; ActivityId
0x140045437  movzx   eax, r11b
0x14004543b  mov     [rsp+48h+UserDataCount], eax; UserDataCount
0x14004543f  call    cs:__imp_EtwWriteTransfer
0x140045446  nop     dword ptr [rax+rax+00h]
0x14004544b  add     rsp, 48h
0x14004544f  retn
```
