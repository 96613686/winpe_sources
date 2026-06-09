# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800079c4`
- end: `0x180007d81`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@22@Z`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015580`

## callees

- `0x1800079c4`
- `0x180008e60`
- `0x180011de8`
- `0x180011f68`
- `0x1800145d0`
- `0x180019a20`
- `0x18001a80c`
- `0x18005f4fc`
- `0x180060130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007c27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007c27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007b2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007b2a`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned __int8 v6; // r13
  unsigned int v7; // r12d
  unsigned __int8 v8; // di
  unsigned __int64 v9; // r9
  char *v10; // rcx
  char v11; // al
  char v14; // r8
  char *v15; // rax
  char v16; // dl
  __int64 v17; // rbx
  signed __int64 v18; // rsi
  __int64 v19; // rdx
  int v20; // r9d
  int v21; // ecx
  volatile signed __int64 *i; // r14
  volatile signed __int64 v23; // r15
  int v24; // eax
  unsigned int j; // r14d
  __int64 v26; // rax
  unsigned __int8 v27; // di
  __int64 v28; // r10
  __int64 v29; // r10
  unsigned int NewEventEntry; // eax
  unsigned int v32; // eax
  int v33; // [rsp+30h] [rbp-89h]
  signed __int64 v34; // [rsp+38h] [rbp-81h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-69h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-49h] BYREF
  int v39; // [rsp+78h] [rbp-41h]
  int v40; // [rsp+7Ch] [rbp-3Dh]
  __int64 v41; // [rsp+80h] [rbp-39h]
  _QWORD v42[5]; // [rsp+88h] [rbp-31h]

  v42[3] = a6;
  v6 = 2;
  v7 = -1073741811;
  v42[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180084010;
  v42[4] = 8;
  v42[2] = 8;
  v41 = a4;
  v42[0] = 8;
  UserData.Size = (unsigned __int16)*off_180084010;
  v39 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v40 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180084030 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    v8 = 0;
    v9 = (unsigned __int64)&Buf1[v39];
    v10 = (char *)(Buf1 + 2);
    do
      v11 = *v10++;
    while ( v11 < 0 );
    while ( *v10++ )
      ;
    while ( (unsigned __int64)v10 < v9 )
    {
      while ( *v10++ )
        ;
      if ( *v10 >= 0 )
        break;
      v14 = *v10 & 0x7F;
      v15 = v10 + 1;
      v10 += 2;
      if ( *v15 >= 0 )
        break;
      while ( 1 )
      {
        v16 = *v10;
        if ( *v10 >= 0 )
          break;
        if ( v16 != (char)0x80 )
          goto LABEL_12;
        ++v10;
      }
      if ( v14 != 9 || (unsigned __int8)(v16 - 113) > 2u )
        break;
      v26 = 2LL * v8++;
      BYTE5(v42[v26]) = v16;
    }
LABEL_12:
    if ( v8 )
    {
      v17 = qword_180084038;
      v18 = 0;
      LOBYTE(a2) = 5;
      LOBYTE(v10) = v8;
      v34 = 0;
      v7 = 0;
      v33 = ComputeEventEntryHash(v10, a2, &UserData);
      SRWLock = (PSRWLOCK)(v17 + 264);
      AcquireSRWLockShared((PSRWLOCK)(v17 + 264));
      v21 = v33;
      for ( i = (volatile signed __int64 *)(v17 + 8LL * (v33 & 0x1F));
            ;
            i = (volatile signed __int64 *)(v23 + (((__int64)v24 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32) )
      {
        if ( !*i )
        {
          if ( *(_DWORD *)(v17 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v17 + 300);
            v7 = 234;
            goto LABEL_31;
          }
          if ( !v18 )
          {
            LOBYTE(v20) = v8;
            LOBYTE(v19) = 5;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v19,
                              (unsigned int)&UserData,
                              v20,
                              v21,
                              (__int64)&v34);
            v18 = v34;
            v7 = NewEventEntry;
            if ( !v34 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v17 + 304);
              else
                ++*(_DWORD *)(v17 + 308);
              goto LABEL_31;
            }
            v21 = v33;
          }
          if ( !_InterlockedCompareExchange64(i, v18, 0) )
            break;
        }
        v23 = *i;
        if ( v21 == *(_DWORD *)(*i + 40) )
        {
          v24 = memcmp_0(&Buf1, (const void *)(*(_QWORD *)(v23 + 16) + 16LL), 8u);
          if ( !v24 )
          {
            for ( j = *(unsigned __int8 *)(v23 + 45) + 2; j < 5; ++j )
            {
              v19 = *(_QWORD *)(v23 + 16);
              v24 = *(&UserData.Size + 4 * j) - *(_DWORD *)(16LL * j + v19 + 8);
              if ( v24 )
                goto LABEL_23;
              v24 = memcmp_0(
                      *((const void **)&UserData.Ptr + 2 * j),
                      *(const void **)(16LL * j + v19),
                      *(&UserData.Size + 4 * j));
              if ( v24 )
                goto LABEL_23;
            }
            v24 = 0;
          }
LABEL_23:
          v21 = v33;
        }
        else
        {
          v24 = v21 - *(_DWORD *)(v23 + 40);
        }
        if ( !v24 )
        {
          if ( v23 )
          {
            v27 = v8 + 2;
            if ( v27 > 2u )
            {
              v28 = 2;
              do
              {
                AggregateField(
                  *(_QWORD *)(*(_QWORD *)(v23 + 16) + 16 * v28),
                  **((_QWORD **)&UserData.Ptr + 2 * v28),
                  *(unsigned __int8 *)(*(_QWORD *)(v23 + 16) + 16 * v28 + 13));
                ++v6;
                v28 = v29 + 1;
              }
              while ( v6 < v27 );
            }
          }
          goto LABEL_31;
        }
      }
      v18 = 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(v17 + 256)) == 1 )
        EnableFlushTimer(*(struct _TP_TIMER **)(v17 + 344), *(_DWORD *)(v17 + 352));
      v32 = *(_DWORD *)(v17 + 256);
      if ( *(_DWORD *)(v17 + 288) < v32 )
        *(_DWORD *)(v17 + 288) = v32;
LABEL_31:
      ReleaseSRWLockShared(SRWLock);
      if ( v18 )
        DestroyEventEntry(v18);
    }
    else
    {
      return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800079c4  push    rbp
0x1800079c6  push    rbx
0x1800079c7  push    rsi
0x1800079c8  push    rdi
0x1800079c9  push    r12
0x1800079cb  push    r13
0x1800079cd  push    r14
0x1800079cf  push    r15
0x1800079d1  lea     rbp, [rsp-0Fh]
0x1800079d6  sub     rsp, 0C8h
0x1800079dd  mov     rax, cs:__security_cookie
0x1800079e4  xor     rax, rsp
0x1800079e7  mov     [rbp+47h+var_50], rax
0x1800079eb  mov     rax, [rbp+47h+arg_28]
0x1800079ef  lea     rcx, [rdx+0Bh]
0x1800079f3  mov     [rbp+47h+var_60], rax
0x1800079f7  mov     r13d, 2
0x1800079fd  mov     rax, [rbp+47h+arg_20]
0x180007a01  mov     r12d, 0C000000Dh
0x180007a07  mov     [rbp+47h+var_70], rax
0x180007a0b  movzx   eax, byte ptr [rdx]
0x180007a0e  shl     eax, 18h
0x180007a11  mov     dword ptr [rbp+47h+EventDescriptor.Id], eax
0x180007a14  movzx   eax, word ptr [rdx+1]
0x180007a18  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x180007a1b  mov     rax, [rdx+3]
0x180007a1f  mov     [rbp+47h+EventDescriptor.Keyword], rax
0x180007a23  mov     rax, cs:off_180084010
0x180007a2a  mov     [rbp+47h+var_A0.Ptr], rax
0x180007a2e  mov     [rbp+47h+var_58], 8
0x180007a36  mov     [rbp+47h+var_68], 8
0x180007a3e  mov     [rbp+47h+var_80], r9
0x180007a42  mov     [rbp+47h+var_78], 8
0x180007a4a  movzx   eax, word ptr [rax]
0x180007a4d  mov     [rbp+47h+var_A0.Size], eax
0x180007a50  movzx   eax, word ptr [rcx]
0x180007a53  mov     [rbp+47h+var_88], eax
0x180007a56  lea     rax, _TraceLoggingMetadataEnd
0x180007a5d  mov     [rbp+47h+Buf1], rcx
0x180007a61  lea     rcx, _TraceLoggingMetadata
0x180007a68  sub     eax, ecx
0x180007a6a  mov     dword ptr [rbp+47h+var_A0.0Ch], r13d
0x180007a6e  mov     [rbp+47h+var_84], 1
0x180007a75  mov     [rsp+100h+var_D0], eax
0x180007a79  mov     eax, [rsp+100h+var_D0]
0x180007a7d  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180007a84  cmp     cs:qword_180084030, rax
0x180007a8b  jnz     loc_180007C36
0x180007a91  mov     rax, [rbp+47h+Buf1]
0x180007a95  xor     dil, dil
0x180007a98  mov     r9d, [rbp+47h+var_88]
0x180007a9c  add     r9, rax
0x180007a9f  lea     rcx, [rax+2]
0x180007aa3  movzx   eax, byte ptr [rcx]
0x180007aa6  inc     rcx
0x180007aa9  test    al, al
0x180007aab  js      short loc_180007AA3
0x180007aad  mov     al, [rcx]
0x180007aaf  inc     rcx
0x180007ab2  test    al, al
0x180007ab4  jnz     short loc_180007AAD
0x180007ab6  cmp     rcx, r9
0x180007ab9  jnb     short loc_180007AF0
0x180007abb  mov     al, [rcx]
0x180007abd  inc     rcx
0x180007ac0  test    al, al
0x180007ac2  jnz     short loc_180007ABB
0x180007ac4  mov     r8b, [rcx]
0x180007ac7  test    r8b, r8b
0x180007aca  jns     short loc_180007AF0
0x180007acc  and     r8b, 7Fh
0x180007ad0  lea     rax, [rcx+1]
0x180007ad4  add     rcx, r13
0x180007ad7  cmp     byte ptr [rax], 0
0x180007ada  jge     short loc_180007AF0
0x180007adc  mov     dl, [rcx]
0x180007ade  test    dl, dl
0x180007ae0  jns     loc_180007BBE
0x180007ae6  cmp     dl, 80h
0x180007ae9  jnz     short loc_180007AF0
0x180007aeb  inc     rcx
0x180007aee  jmp     short loc_180007ADC
0x180007af0  test    dil, dil
0x180007af3  jz      loc_180007D52
0x180007af9  mov     rbx, cs:qword_180084038
0x180007b00  lea     r8, [rbp+47h+var_A0]
0x180007b04  xor     esi, esi
0x180007b06  mov     dl, 5
0x180007b08  mov     cl, dil
0x180007b0b  mov     [rsp+100h+var_C8], rsi
0x180007b10  xor     r12d, r12d
0x180007b13  call    ComputeEventEntryHash
0x180007b18  mov     [rsp+100h+var_D0], eax
0x180007b1c  lea     rax, [rbx+108h]
0x180007b23  mov     rcx, rax; SRWLock
0x180007b26  mov     [rbp+47h+SRWLock], rax
0x180007b2a  call    cs:__imp_AcquireSRWLockShared
0x180007b30  mov     ecx, [rsp+100h+var_D0]
0x180007b34  mov     eax, ecx
0x180007b36  and     eax, 1Fh
0x180007b39  lea     r14, [rbx+rax*8]
0x180007b3d  cmp     qword ptr [r14], 0
0x180007b41  jz      loc_180007C59
0x180007b47  mov     r15, [r14]
0x180007b4a  cmp     ecx, [r15+28h]
0x180007b4e  jz      short loc_180007B72
0x180007b50  mov     eax, ecx
0x180007b52  sub     eax, [r15+28h]
0x180007b56  test    eax, eax
0x180007b58  jz      loc_180007BE7
0x180007b5e  movsxd  r14, eax
0x180007b61  sar     r14, 3Fh
0x180007b65  and     r14, 0FFFFFFFFFFFFFFF8h
0x180007b69  add     r14, 20h ; ' '
0x180007b6d  add     r14, r15
0x180007b70  jmp     short loc_180007B3D
0x180007b72  mov     rdx, [r15+10h]
0x180007b76  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180007b7a  add     rdx, 10h; Buf2
0x180007b7e  mov     r8d, 8; Size
0x180007b84  call    memcmp_0
0x180007b89  test    eax, eax
0x180007b8b  jnz     short loc_180007BB8
0x180007b8d  movzx   r14d, byte ptr [r15+2Dh]
0x180007b92  add     r14d, r13d
0x180007b95  cmp     r14d, 5
0x180007b99  jnb     loc_180007D12
0x180007b9f  mov     rdx, [r15+10h]
0x180007ba3  mov     ecx, r14d
0x180007ba6  shl     rcx, 4
0x180007baa  mov     eax, [rbp+rcx+47h+var_A0.Size]
0x180007bae  sub     eax, [rcx+rdx+8]
0x180007bb2  jz      loc_180007CEF
0x180007bb8  mov     ecx, [rsp+100h+var_D0]
0x180007bbc  jmp     short loc_180007B56
0x180007bbe  cmp     r8b, 9
0x180007bc2  jnz     loc_180007AF0
0x180007bc8  lea     eax, [rdx-71h]
0x180007bcb  cmp     al, r13b
0x180007bce  ja      loc_180007AF0
0x180007bd4  movzx   eax, dil
0x180007bd8  add     rax, rax
0x180007bdb  inc     dil
0x180007bde  mov     byte ptr [rbp+rax*8+47h+var_78+5], dl
0x180007be2  jmp     loc_180007AB6
0x180007be7  test    r15, r15
0x180007bea  jz      short loc_180007C23
0x180007bec  add     dil, r13b
0x180007bef  cmp     dil, r13b
0x180007bf2  jbe     short loc_180007C23
0x180007bf4  mov     r10, r13
0x180007bf7  mov     rcx, [r15+10h]
0x180007bfb  mov     rax, r10
0x180007bfe  add     rax, rax
0x180007c01  mov     rdx, [rbp+rax*8+47h+var_A0.Ptr]
0x180007c06  movzx   r8d, byte ptr [rcx+rax*8+0Dh]
0x180007c0c  mov     rcx, [rcx+rax*8]
0x180007c10  mov     rdx, [rdx]
0x180007c13  call    AggregateField
0x180007c18  inc     r13b
0x180007c1b  inc     r10
0x180007c1e  cmp     r13b, dil
0x180007c21  jb      short loc_180007BF7
0x180007c23  mov     rcx, [rbp+47h+SRWLock]; SRWLock
0x180007c27  call    cs:__imp_ReleaseSRWLockShared
0x180007c2d  test    rsi, rsi
0x180007c30  jnz     loc_180007D45
0x180007c36  mov     eax, r12d
0x180007c39  mov     rcx, [rbp+47h+var_50]
0x180007c3d  xor     rcx, rsp; StackCookie
0x180007c40  call    __security_check_cookie
0x180007c45  add     rsp, 0C8h
0x180007c4c  pop     r15
0x180007c4e  pop     r14
0x180007c50  pop     r13
0x180007c52  pop     r12
0x180007c54  pop     rdi
0x180007c55  pop     rsi
0x180007c56  pop     rbx
0x180007c57  pop     rbp
0x180007c58  retn
0x180007c59  cmp     dword ptr [rbx+100h], 400h
0x180007c63  jnb     loc_180007D34
0x180007c69  test    rsi, rsi
0x180007c6c  jnz     short loc_180007C9F
0x180007c6e  lea     rax, [rsp+100h+var_C8]
0x180007c73  mov     r9b, dil
0x180007c76  mov     [rsp+100h+UserData], rax
0x180007c7b  lea     r8, [rbp+47h+var_A0]
0x180007c7f  mov     [rsp+100h+UserDataCount], ecx
0x180007c83  mov     dl, 5
0x180007c85  lea     rcx, [rbp+47h+EventDescriptor]
0x180007c89  call    CreateNewEventEntry
0x180007c8e  mov     rsi, [rsp+100h+var_C8]
0x180007c93  mov     r12d, eax
0x180007c96  test    rsi, rsi
0x180007c99  jz      short loc_180007D19
0x180007c9b  mov     ecx, [rsp+100h+var_D0]
0x180007c9f  xor     eax, eax
0x180007ca1  lock cmpxchg [r14], rsi
0x180007ca6  jnz     loc_180007B47
0x180007cac  xor     esi, esi
0x180007cae  lea     eax, [rsi+1]
0x180007cb1  lock xadd [rbx+100h], eax
0x180007cb9  inc     eax
0x180007cbb  cmp     eax, 1
0x180007cbe  jnz     short loc_180007CD2
0x180007cc0  mov     edx, [rbx+160h]
0x180007cc6  mov     rcx, [rbx+158h]
0x180007ccd  call    EnableFlushTimer
0x180007cd2  mov     eax, [rbx+100h]
0x180007cd8  cmp     [rbx+120h], eax
0x180007cde  jnb     loc_180007C23
0x180007ce4  mov     [rbx+120h], eax
0x180007cea  jmp     loc_180007C23
0x180007cef  mov     r8d, [rbp+rcx+47h+var_A0.Size]; Size
0x180007cf4  mov     rdx, [rcx+rdx]; Buf2
0x180007cf8  mov     rcx, [rbp+rcx+47h+var_A0.Ptr]; Buf1
0x180007cfd  call    memcmp_0
0x180007d02  test    eax, eax
0x180007d04  jnz     loc_180007BB8
0x180007d0a  inc     r14d
0x180007d0d  jmp     loc_180007B95
0x180007d12  xor     eax, eax
0x180007d14  jmp     loc_180007BB8
0x180007d19  cmp     eax, 8
0x180007d1c  jnz     short loc_180007D29
0x180007d1e  inc     dword ptr [rbx+130h]
0x180007d24  jmp     loc_180007C23
0x180007d29  inc     dword ptr [rbx+134h]
0x180007d2f  jmp     loc_180007C23
0x180007d34  inc     dword ptr [rbx+12Ch]
0x180007d3a  mov     r12d, 0EAh
0x180007d40  jmp     loc_180007C23
0x180007d45  mov     rcx, rsi
0x180007d48  call    DestroyEventEntry
0x180007d4d  jmp     loc_180007C36
0x180007d52  mov     rcx, cs:RegHandle; RegHandle
0x180007d59  lea     rax, [rbp+47h+var_A0]
0x180007d5d  mov     [rsp+100h+UserData], rax; UserData
0x180007d62  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x180007d66  xor     r9d, r9d; RelatedActivityId
0x180007d69  mov     [rsp+100h+UserDataCount], 5; UserDataCount
0x180007d71  xor     r8d, r8d; ActivityId
0x180007d74  call    EventWriteTransfer_0
0x180007d79  mov     r12d, eax
0x180007d7c  jmp     loc_180007C36
```
