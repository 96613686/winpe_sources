# _tlgWriteAgg

- ea: `0x180008a30`
- end: `0x180008e4f`
- name: `_tlgWriteAgg`
- size: `1055`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007938`
- `0x18000d2b0`
- `0x180015890`

## callees

- `0x180008a30`
- `0x180008e60`
- `0x180011de8`
- `0x180011f68`
- `0x1800145d0`
- `0x18001a80c`
- `0x18005f4fc`
- `0x180060130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008c72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008bb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008bb0`

## pseudocode

```c
ULONG __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  PEVENT_DATA_DESCRIPTOR v6; // r12
  __int64 v7; // r15
  PEVENT_DATA_DESCRIPTOR v8; // rdi
  unsigned __int8 v9; // bp
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  unsigned __int8 v12; // r13
  ULONGLONG v13; // r9
  char *v14; // rcx
  char v15; // al
  char *v18; // rax
  char v19; // r8
  UCHAR v20; // dl
  __int64 v21; // rax
  RTL_SRWLOCK *v22; // r14
  int v23; // esi
  volatile signed __int64 *i; // rbx
  volatile signed __int64 v25; // rbx
  int v26; // ecx
  __int64 v27; // r14
  int v28; // eax
  unsigned int v29; // edi
  __int64 v30; // rdx
  int v31; // ebx
  unsigned __int8 v33; // r13
  char v34; // r10
  unsigned int Ptr; // eax
  signed __int64 v36; // [rsp+30h] [rbp-68h] BYREF
  RTL_SRWLOCK *v37; // [rsp+38h] [rbp-60h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-50h] BYREF
  int NewEventEntry; // [rsp+A0h] [rbp+8h]
  signed __int64 v41; // [rsp+A8h] [rbp+10h]

  v6 = UserData;
  v7 = 2;
  v8 = UserData + 1;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  v9 = a4;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  UserData->Ptr = *(_QWORD *)(a1 + 8);
  UserData->Size = **(unsigned __int16 **)(a1 + 8);
  UserData->Reserved = 2;
  UserData[1].Ptr = (ULONGLONG)v11;
  UserData[1].Size = *v11;
  UserData[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) != TlgAggregateInternalRegisteredProviderEtwCallback )
    return -1073741811;
  v12 = 0;
  v13 = UserData[1].Ptr + UserData[1].Size;
  v14 = (char *)(v8->Ptr + 2);
  do
    v15 = *v14++;
  while ( v15 < 0 );
  while ( *v14++ )
    ;
  while ( (unsigned __int64)v14 < v13 )
  {
    while ( *v14++ )
      ;
    if ( *v14 >= 0 )
      break;
    v18 = v14 + 1;
    v19 = *v14 & 0x7F;
    v14 += 2;
    if ( *v18 >= 0 )
      break;
    while ( 1 )
    {
      v20 = *v14;
      if ( *v14 >= 0 )
        break;
      if ( v20 != 0x80 )
        goto LABEL_15;
      ++v14;
    }
    if ( v19 != 9 || (unsigned __int8)(v20 - 113) > 2u )
      break;
    v21 = v12++;
    UserData[v21 + 2].Reserved1 = v20;
  }
LABEL_15:
  if ( !v12 )
    return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, v9, UserData);
  v37 = *(RTL_SRWLOCK **)(a1 + 48);
  v22 = v37;
  v41 = 0;
  v36 = 0;
  NewEventEntry = 0;
  v23 = ComputeEventEntryHash(v12, v9, UserData);
  SRWLock = v37 + 33;
  AcquireSRWLockShared(v37 + 33);
  for ( i = (volatile signed __int64 *)&v37[v23 & 0x1F];
        ;
        i = (volatile signed __int64 *)((((__int64)v28 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v25 + 32) )
  {
    if ( !*i )
    {
      if ( LODWORD(v22[32].Ptr) >= 0x400 )
      {
        ++HIDWORD(v22[37].Ptr);
        v31 = 234;
        goto LABEL_30;
      }
      if ( !v41 )
      {
        NewEventEntry = CreateNewEventEntry((unsigned int)&EventDescriptor, v9, (_DWORD)v6, v12, v23, (__int64)&v36);
        v41 = v36;
        if ( !v36 )
        {
          v31 = NewEventEntry;
          if ( NewEventEntry == 8 )
            ++LODWORD(v22[38].Ptr);
          else
            ++HIDWORD(v22[38].Ptr);
          goto LABEL_30;
        }
      }
      if ( !_InterlockedCompareExchange64(i, v41, 0) )
        break;
    }
    v25 = *i;
    v26 = *(_DWORD *)(v25 + 40);
    if ( v23 == v26 )
    {
      v27 = *(_QWORD *)(v25 + 16);
      v28 = memcmp_0(v8, (const void *)(v27 + 16), 8u);
      if ( !v28 )
      {
        v29 = *(unsigned __int8 *)(v25 + 45) + 2;
        v6 = UserData;
        while ( v29 < a4 )
        {
          v30 = v27 + 16LL * v29;
          v28 = UserData[v29].Size - *(_DWORD *)(v30 + 8);
          if ( v28 )
            goto LABEL_23;
          v28 = memcmp_0((const void *)UserData[v29].Ptr, *(const void **)v30, UserData[v29].Size);
          if ( v28 )
            goto LABEL_23;
          ++v29;
        }
        v28 = 0;
LABEL_23:
        v9 = a4;
        v8 = UserData + 1;
      }
      v22 = v37;
    }
    else
    {
      v28 = v23 - v26;
    }
    if ( !v28 )
    {
      if ( v25 )
      {
        v33 = v12 + 2;
        if ( v33 > 2u )
        {
          do
          {
            AggregateField(
              *(_QWORD *)(*(_QWORD *)(v25 + 16) + 16 * v7),
              *(_QWORD *)v6[v7].Ptr,
              *(unsigned __int8 *)(*(_QWORD *)(v25 + 16) + 16 * v7 + 13));
            ++v7;
          }
          while ( (unsigned __int8)(v34 + 1) < v33 );
        }
      }
      v31 = NewEventEntry;
      goto LABEL_30;
    }
  }
  v41 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)&v22[32]) == 1 )
    EnableFlushTimer((struct _TP_TIMER *)v22[43].Ptr, (unsigned int)v22[44].Ptr);
  Ptr = (unsigned int)v22[32].Ptr;
  v31 = NewEventEntry;
  if ( LODWORD(v22[36].Ptr) < Ptr )
    LODWORD(v22[36].Ptr) = Ptr;
LABEL_30:
  ReleaseSRWLockShared(SRWLock);
  if ( v41 )
    DestroyEventEntry(v41);
  return v31;
}

```

## disassembly

```asm
0x180008a30  mov     [rsp+arg_18], r9d
0x180008a35  push    rbp
0x180008a36  push    rdi
0x180008a37  push    r12
0x180008a39  push    r15
0x180008a3b  sub     rsp, 78h
0x180008a3f  movzx   eax, byte ptr [rdx]
0x180008a42  mov     r10, rcx
0x180008a45  mov     r12, [rsp+98h+arg_20]
0x180008a4d  mov     r15d, 2
0x180008a53  shl     eax, 18h
0x180008a56  lea     rdi, [r12+10h]
0x180008a5b  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x180008a5f  mov     ebp, r9d
0x180008a62  movzx   eax, word ptr [rdx+1]
0x180008a66  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180008a6a  mov     rax, [rdx+3]
0x180008a6e  add     rdx, 0Bh
0x180008a72  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x180008a77  mov     rax, [rcx+8]
0x180008a7b  mov     [r12], rax
0x180008a7f  mov     rax, [rcx+8]
0x180008a83  movzx   ecx, word ptr [rax]
0x180008a86  mov     [r12+8], ecx
0x180008a8b  lea     rcx, _TraceLoggingMetadata
0x180008a92  mov     [r12+0Ch], r15d
0x180008a97  mov     [rdi], rdx
0x180008a9a  movzx   eax, word ptr [rdx]
0x180008a9d  mov     [r12+18h], eax
0x180008aa2  lea     rax, _TraceLoggingMetadataEnd
0x180008aa9  sub     eax, ecx
0x180008aab  mov     dword ptr [r12+1Ch], 1
0x180008ab4  mov     [rsp+98h+arg_0], eax
0x180008abb  mov     eax, [rsp+98h+arg_0]
0x180008ac2  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180008ac9  cmp     [r10+28h], rax
0x180008acd  jnz     loc_180008E45
0x180008ad3  mov     rax, [rdi]
0x180008ad6  mov     r9d, [rdi+8]
0x180008ada  mov     [rsp+98h+var_30], r13
0x180008adf  xor     r13b, r13b
0x180008ae2  add     r9, rax
0x180008ae5  lea     rcx, [rax+2]
0x180008ae9  movzx   eax, byte ptr [rcx]
0x180008aec  inc     rcx
0x180008aef  test    al, al
0x180008af1  js      short loc_180008AE9
0x180008af3  movzx   eax, byte ptr [rcx]
0x180008af6  inc     rcx
0x180008af9  test    al, al
0x180008afb  jnz     short loc_180008AF3
0x180008afd  cmp     rcx, r9
0x180008b00  jnb     short loc_180008B55
0x180008b02  movzx   eax, byte ptr [rcx]
0x180008b05  inc     rcx
0x180008b08  test    al, al
0x180008b0a  jnz     short loc_180008B02
0x180008b0c  movzx   r8d, byte ptr [rcx]
0x180008b10  test    r8b, r8b
0x180008b13  jns     short loc_180008B55
0x180008b15  lea     rax, [rcx+1]
0x180008b19  and     r8b, 7Fh
0x180008b1d  add     rcx, r15
0x180008b20  cmp     byte ptr [rax], 0
0x180008b23  jge     short loc_180008B55
0x180008b25  movzx   edx, byte ptr [rcx]
0x180008b28  test    dl, dl
0x180008b2a  jns     short loc_180008B36
0x180008b2c  cmp     dl, 80h
0x180008b2f  jnz     short loc_180008B55
0x180008b31  inc     rcx
0x180008b34  jmp     short loc_180008B25
0x180008b36  cmp     r8b, 9
0x180008b3a  jnz     short loc_180008B55
0x180008b3c  lea     eax, [rdx-71h]
0x180008b3f  cmp     al, r15b
0x180008b42  ja      short loc_180008B55
0x180008b44  movzx   eax, r13b
0x180008b48  add     rax, rax
0x180008b4b  inc     r13b
0x180008b4e  mov     [r12+rax*8+2Dh], dl
0x180008b53  jmp     short loc_180008AFD
0x180008b55  test    r13b, r13b
0x180008b58  jz      loc_180008E1F
0x180008b5e  xor     eax, eax
0x180008b60  mov     [rsp+98h+arg_10], rbx
0x180008b68  mov     [rsp+98h+var_28], rsi
0x180008b6d  mov     r8, r12
0x180008b70  mov     [rsp+98h+var_38], r14
0x180008b75  movzx   edx, bpl
0x180008b79  mov     r14, [r10+30h]
0x180008b7d  movzx   ecx, r13b
0x180008b81  mov     [rsp+98h+var_60], r14
0x180008b86  mov     [rsp+98h+arg_8], rax
0x180008b8e  mov     [rsp+98h+var_68], rax
0x180008b93  mov     [rsp+98h+arg_0], eax
0x180008b9a  call    ComputeEventEntryHash
0x180008b9f  mov     esi, eax
0x180008ba1  lea     rax, [r14+108h]
0x180008ba8  mov     rcx, rax; SRWLock
0x180008bab  mov     [rsp+98h+SRWLock], rax
0x180008bb0  call    cs:__imp_AcquireSRWLockShared
0x180008bb6  mov     eax, esi
0x180008bb8  and     eax, 1Fh
0x180008bbb  lea     rbx, [r14+rax*8]
0x180008bbf  nop
0x180008bc0  cmp     qword ptr [rbx], 0
0x180008bc4  jz      loc_180008CF0
0x180008bca  mov     rbx, [rbx]
0x180008bcd  mov     ecx, [rbx+28h]
0x180008bd0  cmp     esi, ecx
0x180008bd2  jnz     loc_180008C5B
0x180008bd8  mov     r14, [rbx+10h]
0x180008bdc  mov     r8d, 8; Size
0x180008be2  mov     rcx, rdi; Buf1
0x180008be5  lea     rdx, [r14+10h]; Buf2
0x180008be9  call    memcmp_0
0x180008bee  test    eax, eax
0x180008bf0  jnz     short loc_180008C3B
0x180008bf2  movzx   edi, byte ptr [rbx+2Dh]
0x180008bf6  movzx   ebp, byte ptr [rsp+98h+arg_18]
0x180008bfe  add     edi, r15d
0x180008c01  mov     r12, [rsp+98h+arg_20]
0x180008c09  cmp     edi, ebp
0x180008c0b  jnb     loc_180008DEE
0x180008c11  mov     eax, edi
0x180008c13  add     rax, rax
0x180008c16  mov     r8d, [r12+rax*8+8]; Size
0x180008c1b  lea     rcx, [r12+rax*8]
0x180008c1f  lea     rdx, [r14+rax*8]
0x180008c23  mov     eax, r8d
0x180008c26  sub     eax, [rdx+8]
0x180008c29  jz      loc_180008DD4
0x180008c2f  mov     ebp, [rsp+98h+arg_18]
0x180008c36  lea     rdi, [r12+10h]
0x180008c3b  mov     r14, [rsp+98h+var_60]
0x180008c40  test    eax, eax
0x180008c42  jz      short loc_180008C61
0x180008c44  movsxd  rcx, eax
0x180008c47  add     rbx, 20h ; ' '
0x180008c4b  sar     rcx, 3Fh
0x180008c4f  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180008c53  add     rbx, rcx
0x180008c56  jmp     loc_180008BC0
0x180008c5b  mov     eax, esi
0x180008c5d  sub     eax, ecx
0x180008c5f  jmp     short loc_180008C40
0x180008c61  test    rbx, rbx
0x180008c64  jnz     short loc_180008CAD
0x180008c66  mov     ebx, [rsp+98h+arg_0]
0x180008c6d  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x180008c72  call    cs:__imp_ReleaseSRWLockShared
0x180008c78  mov     rax, [rsp+98h+arg_8]
0x180008c80  mov     r14, [rsp+98h+var_38]
0x180008c85  mov     rsi, [rsp+98h+var_28]
0x180008c8a  test    rax, rax
0x180008c8d  jnz     loc_180008E12
0x180008c93  mov     eax, ebx
0x180008c95  mov     rbx, [rsp+98h+arg_10]
0x180008c9d  mov     r13, [rsp+98h+var_30]
0x180008ca2  add     rsp, 78h
0x180008ca6  pop     r15
0x180008ca8  pop     r12
0x180008caa  pop     rdi
0x180008cab  pop     rbp
0x180008cac  retn
0x180008cad  add     r13b, r15b
0x180008cb0  movzx   r10d, r15b
0x180008cb4  cmp     r13b, r15b
0x180008cb7  jbe     short loc_180008C66
0x180008cb9  nop     dword ptr [rax+00000000h]
0x180008cc0  mov     rax, [rbx+10h]
0x180008cc4  mov     rcx, r15
0x180008cc7  add     rcx, rcx
0x180008cca  mov     rdx, [r12+rcx*8]
0x180008cce  movzx   r8d, byte ptr [rax+rcx*8+0Dh]
0x180008cd4  mov     rcx, [rax+rcx*8]
0x180008cd8  mov     rdx, [rdx]
0x180008cdb  call    AggregateField
0x180008ce0  inc     r10b
0x180008ce3  inc     r15
0x180008ce6  cmp     r10b, r13b
0x180008ce9  jb      short loc_180008CC0
0x180008ceb  jmp     loc_180008C66
0x180008cf0  cmp     dword ptr [r14+100h], 400h
0x180008cfb  jnb     loc_180008E01
0x180008d01  cmp     [rsp+98h+arg_8], 0
0x180008d0a  jnz     short loc_180008D64
0x180008d0c  lea     rax, [rsp+98h+var_68]
0x180008d11  movzx   r9d, r13b
0x180008d15  mov     [rsp+98h+UserData], rax
0x180008d1a  lea     rcx, [rsp+98h+EventDescriptor]
0x180008d1f  mov     r8, r12
0x180008d22  mov     [rsp+98h+UserDataCount], esi
0x180008d26  movzx   edx, bpl
0x180008d2a  call    CreateNewEventEntry
0x180008d2f  mov     [rsp+98h+arg_0], eax
0x180008d36  mov     rax, [rsp+98h+var_68]
0x180008d3b  mov     [rsp+98h+arg_8], rax
0x180008d43  test    rax, rax
0x180008d46  jnz     short loc_180008D64
0x180008d48  mov     ebx, [rsp+98h+arg_0]
0x180008d4f  cmp     ebx, 8
0x180008d52  jnz     loc_180008DF5
0x180008d58  inc     dword ptr [r14+130h]
0x180008d5f  jmp     loc_180008C6D
0x180008d64  mov     rcx, [rsp+98h+arg_8]
0x180008d6c  xor     eax, eax
0x180008d6e  lock cmpxchg [rbx], rcx
0x180008d73  jnz     loc_180008BCA
0x180008d79  mov     [rsp+98h+arg_8], 0
0x180008d85  mov     eax, 1
0x180008d8a  lock xadd [r14+100h], eax
0x180008d93  inc     eax
0x180008d95  cmp     eax, 1
0x180008d98  jnz     short loc_180008DAD
0x180008d9a  mov     edx, [r14+160h]
0x180008da1  mov     rcx, [r14+158h]
0x180008da8  call    EnableFlushTimer
0x180008dad  mov     eax, [r14+100h]
0x180008db4  mov     ebx, [rsp+98h+arg_0]
0x180008dbb  cmp     [r14+120h], eax
0x180008dc2  jnb     loc_180008C6D
0x180008dc8  mov     [r14+120h], eax
0x180008dcf  jmp     loc_180008C6D
0x180008dd4  mov     rdx, [rdx]; Buf2
0x180008dd7  mov     rcx, [rcx]; Buf1
0x180008dda  call    memcmp_0
0x180008ddf  test    eax, eax
0x180008de1  jnz     loc_180008C2F
0x180008de7  inc     edi
0x180008de9  jmp     loc_180008C09
0x180008dee  xor     eax, eax
0x180008df0  jmp     loc_180008C2F
0x180008df5  inc     dword ptr [r14+134h]
0x180008dfc  jmp     loc_180008C6D
0x180008e01  inc     dword ptr [r14+12Ch]
0x180008e08  mov     ebx, 0EAh
0x180008e0d  jmp     loc_180008C6D
0x180008e12  mov     rcx, rax
0x180008e15  call    DestroyEventEntry
0x180008e1a  jmp     loc_180008C93
0x180008e1f  mov     rcx, [r10+20h]; RegHandle
0x180008e23  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x180008e28  movzx   eax, bpl
0x180008e2c  xor     r9d, r9d; RelatedActivityId
0x180008e2f  mov     [rsp+98h+UserData], r12; UserData
0x180008e34  xor     r8d, r8d; ActivityId
0x180008e37  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x180008e3b  call    EventWriteTransfer_0
0x180008e40  jmp     loc_180008C9D
0x180008e45  mov     eax, 0C000000Dh
0x180008e4a  jmp     loc_180008CA2
```
