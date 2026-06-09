# TlgAggregateAbsorbEvent

- ea: `0x18001156c`
- end: `0x180011658`
- name: `TlgAggregateAbsorbEvent`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800114e0`

## callees

- `0x180010290`
- `0x18001156c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011642`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011642`

## pseudocode

```c
ULONG __fastcall TlgAggregateAbsorbEvent(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        unsigned __int8 a3,
        struct _EVENT_DATA_DESCRIPTOR *UserData)
{
  ULONG UserDataCount; // edi
  ULONG result; // eax
  ULONGLONG Ptr; // rax
  unsigned __int8 v9; // r10
  unsigned __int64 v10; // rbx
  char *v11; // rcx
  char v12; // al
  char v15; // r8
  char *v16; // rax
  char v17; // dl
  __int64 v18; // rax

  UserDataCount = a3;
  result = -1073741811;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = UserData[1].Ptr;
    v9 = 0;
    v10 = Ptr + UserData[1].Size;
    v11 = (char *)(Ptr + 2);
    do
      v12 = *v11++;
    while ( v12 < 0 );
    while ( *v11++ )
      ;
    while ( (unsigned __int64)v11 < v10 )
    {
      while ( *v11++ )
        ;
      if ( *v11 >= 0 )
        break;
      v15 = *v11 & 0x7F;
      v16 = v11 + 1;
      v11 += 2;
      if ( *v16 >= 0 )
        break;
      while ( 1 )
      {
        v17 = *v11;
        if ( *v11 >= 0 )
          break;
        if ( v17 != (char)0x80 )
          goto LABEL_15;
        ++v11;
      }
      if ( v15 != 9 || (unsigned __int8)(v17 - 113) > 2u )
        break;
      v18 = v9++;
      UserData[v18 + 2].Reserved1 = v17;
    }
LABEL_15:
    if ( v9 )
      return InsertEventEntryInLookUpTable(a1, (_DWORD)a2, (_BYTE)UserDataCount, (_DWORD)UserData, v9);
    else
      return EventWriteTransfer(*(_QWORD *)(a1 + 32), a2, 0, 0, UserDataCount, UserData);
  }
  return result;
}

```

## disassembly

```asm
0x18001156c  mov     [rsp+arg_0], rbx
0x180011571  mov     [rsp+arg_8], rsi
0x180011576  push    rdi
0x180011577  sub     rsp, 30h
0x18001157b  mov     r11, rcx
0x18001157e  movzx   edi, r8b
0x180011582  lea     rcx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180011589  mov     rsi, rdx
0x18001158c  mov     eax, 0C000000Dh
0x180011591  cmp     [r11+28h], rcx
0x180011595  jnz     loc_180011648
0x18001159b  mov     rax, [r9+10h]
0x18001159f  xor     r10b, r10b
0x1800115a2  mov     ebx, [r9+18h]
0x1800115a6  add     rbx, rax
0x1800115a9  lea     rcx, [rax+2]
0x1800115ad  movzx   eax, byte ptr [rcx]
0x1800115b0  inc     rcx
0x1800115b3  test    al, al
0x1800115b5  js      short loc_1800115AD
0x1800115b7  mov     al, [rcx]
0x1800115b9  inc     rcx
0x1800115bc  test    al, al
0x1800115be  jnz     short loc_1800115B7
0x1800115c0  cmp     rcx, rbx
0x1800115c3  jnb     short loc_180011615
0x1800115c5  mov     al, [rcx]
0x1800115c7  inc     rcx
0x1800115ca  test    al, al
0x1800115cc  jnz     short loc_1800115C5
0x1800115ce  mov     r8b, [rcx]
0x1800115d1  test    r8b, r8b
0x1800115d4  jns     short loc_180011615
0x1800115d6  and     r8b, 7Fh
0x1800115da  lea     rax, [rcx+1]
0x1800115de  add     rcx, 2
0x1800115e2  cmp     byte ptr [rax], 0
0x1800115e5  jge     short loc_180011615
0x1800115e7  mov     dl, [rcx]
0x1800115e9  test    dl, dl
0x1800115eb  jns     short loc_1800115F7
0x1800115ed  cmp     dl, 80h
0x1800115f0  jnz     short loc_180011615
0x1800115f2  inc     rcx
0x1800115f5  jmp     short loc_1800115E7
0x1800115f7  cmp     r8b, 9
0x1800115fb  jnz     short loc_180011615
0x1800115fd  lea     eax, [rdx-71h]
0x180011600  cmp     al, 2
0x180011602  ja      short loc_180011615
0x180011604  movzx   eax, r10b
0x180011608  add     rax, rax
0x18001160b  inc     r10b
0x18001160e  mov     [r9+rax*8+2Dh], dl
0x180011613  jmp     short loc_1800115C0
0x180011615  mov     rdx, rsi; EventDescriptor
0x180011618  test    r10b, r10b
0x18001161b  jz      short loc_18001162F
0x18001161d  mov     r8b, dil
0x180011620  mov     byte ptr [rsp+38h+UserDataCount], r10b
0x180011625  mov     rcx, r11
0x180011628  call    InsertEventEntryInLookUpTable
0x18001162d  jmp     short loc_180011648
0x18001162f  mov     rcx, [r11+20h]; RegHandle
0x180011633  xor     r8d, r8d; ActivityId
0x180011636  mov     [rsp+38h+UserData], r9; UserData
0x18001163b  xor     r9d, r9d; RelatedActivityId
0x18001163e  mov     [rsp+38h+UserDataCount], edi; UserDataCount
0x180011642  call    cs:__imp_EventWriteTransfer
0x180011648  mov     rbx, [rsp+38h+arg_0]
0x18001164d  mov     rsi, [rsp+38h+arg_8]
0x180011652  add     rsp, 30h
0x180011656  pop     rdi
0x180011657  retn
```
