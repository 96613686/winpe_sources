# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180007d88`
- end: `0x180008188`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@32@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180004790`

## callees

- `0x180007d88`
- `0x180008e60`
- `0x180011de8`
- `0x180011f68`
- `0x1800145d0`
- `0x180019a20`
- `0x18001a80c`
- `0x18005f4fc`
- `0x180060130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007ff3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007ff3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007f31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007f31`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9)
{
  unsigned int v9; // r13d
  unsigned __int8 v10; // r12
  __int64 v11; // rcx
  unsigned __int8 v12; // di
  unsigned __int64 v13; // r9
  char *v14; // rcx
  char v15; // al
  char v18; // r8
  char *v19; // rax
  char v20; // dl
  __int64 v21; // rbx
  signed __int64 v22; // rsi
  int v23; // r14d
  __int64 v24; // rdx
  int v25; // r9d
  volatile signed __int64 *i; // r15
  volatile signed __int64 v27; // r15
  int v28; // eax
  unsigned int j; // r14d
  __int64 v30; // rax
  unsigned __int8 v32; // di
  __int64 v33; // r10
  __int64 v34; // r10
  unsigned int NewEventEntry; // eax
  unsigned int v36; // eax
  int v37; // [rsp+30h] [rbp-C1h]
  signed __int64 v38; // [rsp+38h] [rbp-B9h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-B1h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-A1h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-91h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-81h] BYREF
  int v43; // [rsp+78h] [rbp-79h]
  int v44; // [rsp+7Ch] [rbp-75h]
  __int64 v45; // [rsp+80h] [rbp-71h]
  _QWORD v46[11]; // [rsp+88h] [rbp-69h]

  v46[9] = a9;
  v9 = -1073741811;
  v46[7] = a8;
  v10 = 2;
  v46[10] = 8;
  v46[8] = 4;
  v46[6] = 16;
  v11 = *a7;
  v46[3] = a6;
  v46[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = (ULONGLONG)off_180084010;
  v46[5] = v11;
  v46[4] = 4;
  v46[2] = 8;
  v45 = a4;
  v46[0] = 8;
  UserData.Size = (unsigned __int16)*off_180084010;
  v43 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v44 = 1;
  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180084030 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return v9;
  v12 = 0;
  v13 = (unsigned __int64)&Buf1[v43];
  v14 = (char *)(Buf1 + 2);
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
    v18 = *v14 & 0x7F;
    v19 = v14 + 1;
    v14 += 2;
    if ( *v19 >= 0 )
      break;
    while ( 1 )
    {
      v20 = *v14;
      if ( *v14 >= 0 )
        break;
      if ( v20 != (char)0x80 )
        goto LABEL_12;
      ++v14;
    }
    if ( v18 != 9 || (unsigned __int8)(v20 - 113) > 2u )
      break;
    v30 = 2LL * v12++;
    BYTE5(v46[v30]) = v20;
  }
LABEL_12:
  if ( !v12 )
    return EventWriteTransfer_0(RegHandle, &EventDescriptor, 0, 0, 8u, &UserData);
  v21 = qword_180084038;
  LOBYTE(a2) = 8;
  v38 = 0;
  LOBYTE(v14) = v12;
  v22 = 0;
  v9 = 0;
  v23 = ComputeEventEntryHash(v14, a2, &UserData);
  v37 = v23;
  SRWLock = (PSRWLOCK)(v21 + 264);
  AcquireSRWLockShared((PSRWLOCK)(v21 + 264));
  for ( i = (volatile signed __int64 *)(v21 + 8LL * (v23 & 0x1F));
        ;
        i = (volatile signed __int64 *)((((__int64)v28 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + v27 + 32) )
  {
    if ( !*i )
    {
      if ( *(_DWORD *)(v21 + 256) >= 0x400u )
      {
        ++*(_DWORD *)(v21 + 300);
        v9 = 234;
        goto LABEL_28;
      }
      if ( !v22 )
      {
        LOBYTE(v25) = v12;
        LOBYTE(v24) = 8;
        NewEventEntry = CreateNewEventEntry(
                          (unsigned int)&EventDescriptor,
                          v24,
                          (unsigned int)&UserData,
                          v25,
                          v23,
                          (__int64)&v38);
        v22 = v38;
        v9 = NewEventEntry;
        if ( !v38 )
        {
          if ( NewEventEntry == 8 )
            ++*(_DWORD *)(v21 + 304);
          else
            ++*(_DWORD *)(v21 + 308);
          goto LABEL_28;
        }
      }
      if ( !_InterlockedCompareExchange64(i, v22, 0) )
        break;
    }
    v27 = *i;
    if ( v23 == *(_DWORD *)(v27 + 40) )
    {
      v28 = memcmp_0(&Buf1, (const void *)(*(_QWORD *)(v27 + 16) + 16LL), 8u);
      if ( v28 )
        continue;
      for ( j = *(unsigned __int8 *)(v27 + 45) + 2; j < 8; ++j )
      {
        v24 = *(_QWORD *)(v27 + 16);
        v28 = *(&UserData.Size + 4 * j) - *(_DWORD *)(v24 + 16LL * j + 8);
        if ( v28 )
          goto LABEL_20;
        v28 = memcmp_0(
                *((const void **)&UserData.Ptr + 2 * j),
                *(const void **)(v24 + 16LL * j),
                *(&UserData.Size + 4 * j));
        if ( v28 )
          goto LABEL_20;
      }
      v28 = 0;
LABEL_20:
      v23 = v37;
    }
    else
    {
      v28 = v23 - *(_DWORD *)(v27 + 40);
    }
    if ( !v28 )
    {
      if ( v27 )
      {
        v32 = v12 + 2;
        if ( v32 > 2u )
        {
          v33 = 2;
          do
          {
            AggregateField(
              *(_QWORD *)(*(_QWORD *)(v27 + 16) + 16 * v33),
              **((_QWORD **)&UserData.Ptr + 2 * v33),
              *(unsigned __int8 *)(*(_QWORD *)(v27 + 16) + 16 * v33 + 13));
            ++v10;
            v33 = v34 + 1;
          }
          while ( v10 < v32 );
        }
      }
      goto LABEL_28;
    }
  }
  v22 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(v21 + 256)) == 1 )
    EnableFlushTimer(*(struct _TP_TIMER **)(v21 + 344), *(_DWORD *)(v21 + 352));
  v36 = *(_DWORD *)(v21 + 256);
  if ( *(_DWORD *)(v21 + 288) < v36 )
    *(_DWORD *)(v21 + 288) = v36;
LABEL_28:
  ReleaseSRWLockShared(SRWLock);
  if ( v22 )
    DestroyEventEntry(v22);
  return v9;
}

```

## disassembly

```asm
0x180007d88  push    rbp
0x180007d8a  push    rbx
0x180007d8b  push    rsi
0x180007d8c  push    rdi
0x180007d8d  push    r12
0x180007d8f  push    r13
0x180007d91  push    r14
0x180007d93  push    r15
0x180007d95  lea     rbp, [rsp-7]
0x180007d9a  sub     rsp, 0F8h
0x180007da1  mov     rax, cs:__security_cookie
0x180007da8  xor     rax, rsp
0x180007dab  mov     [rbp+3Fh+var_50], rax
0x180007daf  mov     rax, [rbp+3Fh+arg_40]
0x180007db6  mov     r11d, 8
0x180007dbc  mov     [rbp+3Fh+var_60], rax
0x180007dc0  xor     r10d, r10d
0x180007dc3  mov     rax, [rbp+3Fh+arg_38]
0x180007dca  mov     r13d, 0C000000Dh
0x180007dd0  mov     [rbp+3Fh+var_70], rax
0x180007dd4  mov     rax, [rbp+3Fh+arg_30]
0x180007dd8  lea     r12d, [r11-6]
0x180007ddc  mov     [rbp+3Fh+var_58], r11
0x180007de0  mov     [rbp+3Fh+var_68], 4
0x180007de8  mov     [rbp+3Fh+var_78], 10h
0x180007df0  mov     rcx, [rax]
0x180007df3  mov     rax, [rbp+3Fh+arg_28]
0x180007df7  mov     [rbp+3Fh+var_90], rax
0x180007dfb  mov     rax, [rbp+3Fh+arg_20]
0x180007dff  mov     [rbp+3Fh+var_A0], rax
0x180007e03  movzx   eax, byte ptr [rdx]
0x180007e06  shl     eax, 18h
0x180007e09  mov     dword ptr [rsp+130h+EventDescriptor.Id], eax
0x180007e0d  movzx   eax, word ptr [rdx+1]
0x180007e11  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180007e15  mov     rax, [rdx+3]
0x180007e19  mov     [rsp+130h+EventDescriptor.Keyword], rax
0x180007e1e  mov     rax, cs:off_180084010
0x180007e25  mov     [rsp+130h+var_D0.Ptr], rax
0x180007e2a  mov     [rbp+3Fh+var_80], rcx
0x180007e2e  lea     rcx, [rdx+0Bh]
0x180007e32  mov     [rbp+3Fh+var_88], 4
0x180007e3a  mov     [rbp+3Fh+var_98], r11
0x180007e3e  mov     [rbp+3Fh+var_B0], r9
0x180007e42  mov     [rbp+3Fh+var_A8], r11
0x180007e46  movzx   eax, word ptr [rax]
0x180007e49  mov     [rsp+130h+var_D0.Size], eax
0x180007e4d  movzx   eax, word ptr [rcx]
0x180007e50  mov     [rbp+3Fh+var_B8], eax
0x180007e53  lea     rax, _TraceLoggingMetadataEnd
0x180007e5a  mov     [rsp+130h+Buf1], rcx
0x180007e5f  lea     rcx, _TraceLoggingMetadata
0x180007e66  sub     eax, ecx
0x180007e68  mov     dword ptr [rsp+130h+var_D0.0Ch], r12d
0x180007e6d  mov     [rbp+3Fh+var_B4], 1
0x180007e74  mov     [rsp+130h+var_100], eax
0x180007e78  mov     eax, [rsp+130h+var_100]
0x180007e7c  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180007e83  cmp     cs:qword_180084030, rax
0x180007e8a  jnz     loc_180008002
0x180007e90  mov     rax, [rsp+130h+Buf1]
0x180007e95  mov     dil, r10b
0x180007e98  mov     r9d, [rbp+3Fh+var_B8]
0x180007e9c  add     r9, rax
0x180007e9f  lea     rcx, [rax+2]
0x180007ea3  movzx   eax, byte ptr [rcx]
0x180007ea6  inc     rcx
0x180007ea9  test    al, al
0x180007eab  js      short loc_180007EA3
0x180007ead  mov     al, [rcx]
0x180007eaf  inc     rcx
0x180007eb2  test    al, al
0x180007eb4  jnz     short loc_180007EAD
0x180007eb6  cmp     rcx, r9
0x180007eb9  jnb     short loc_180007EF0
0x180007ebb  mov     al, [rcx]
0x180007ebd  inc     rcx
0x180007ec0  test    al, al
0x180007ec2  jnz     short loc_180007EBB
0x180007ec4  mov     r8b, [rcx]
0x180007ec7  test    r8b, r8b
0x180007eca  jns     short loc_180007EF0
0x180007ecc  and     r8b, 7Fh
0x180007ed0  lea     rax, [rcx+1]
0x180007ed4  add     rcx, r12
0x180007ed7  cmp     [rax], r10b
0x180007eda  jge     short loc_180007EF0
0x180007edc  mov     dl, [rcx]
0x180007ede  test    dl, dl
0x180007ee0  jns     loc_180007FC0
0x180007ee6  cmp     dl, 80h
0x180007ee9  jnz     short loc_180007EF0
0x180007eeb  inc     rcx
0x180007eee  jmp     short loc_180007EDC
0x180007ef0  test    dil, dil
0x180007ef3  jz      loc_18000815A
0x180007ef9  mov     rbx, cs:qword_180084038
0x180007f00  lea     r8, [rsp+130h+var_D0]
0x180007f05  mov     dl, r11b
0x180007f08  mov     [rsp+130h+var_F8], r10
0x180007f0d  mov     cl, dil
0x180007f10  mov     rsi, r10
0x180007f13  mov     r13d, r10d
0x180007f16  call    ComputeEventEntryHash
0x180007f1b  mov     r14d, eax
0x180007f1e  mov     [rsp+130h+var_100], eax
0x180007f22  lea     rax, [rbx+108h]
0x180007f29  mov     rcx, rax; SRWLock
0x180007f2c  mov     [rsp+130h+SRWLock], rax
0x180007f31  call    cs:__imp_AcquireSRWLockShared
0x180007f37  mov     eax, r14d
0x180007f3a  and     eax, 1Fh
0x180007f3d  lea     r15, [rbx+rax*8]
0x180007f41  cmp     qword ptr [r15], 0
0x180007f45  jz      loc_18000805E
0x180007f4b  mov     r15, [r15]
0x180007f4e  cmp     r14d, [r15+28h]
0x180007f52  jnz     short loc_180007FA2
0x180007f54  mov     rdx, [r15+10h]
0x180007f58  lea     rcx, [rsp+130h+Buf1]; Buf1
0x180007f5d  add     rdx, 10h; Buf2
0x180007f61  mov     r8d, 8; Size
0x180007f67  call    memcmp_0
0x180007f6c  test    eax, eax
0x180007f6e  jnz     short loc_180007FAD
0x180007f70  movzx   r14d, byte ptr [r15+2Dh]
0x180007f75  add     r14d, r12d
0x180007f78  cmp     r14d, 8
0x180007f7c  jnb     loc_18000812A
0x180007f82  mov     rdx, [r15+10h]
0x180007f86  mov     ecx, r14d
0x180007f89  shl     rcx, 4
0x180007f8d  mov     eax, [rsp+rcx+130h+var_D0.Size]
0x180007f91  sub     eax, [rdx+rcx+8]
0x180007f95  jz      loc_180008107
0x180007f9b  mov     r14d, [rsp+130h+var_100]
0x180007fa0  jmp     short loc_180007FA9
0x180007fa2  mov     eax, r14d
0x180007fa5  sub     eax, [r15+28h]
0x180007fa9  test    eax, eax
0x180007fab  jz      short loc_180007FE9
0x180007fad  cdqe
0x180007faf  add     r15, 20h ; ' '
0x180007fb3  sar     rax, 3Fh
0x180007fb7  and     rax, 0FFFFFFFFFFFFFFF8h
0x180007fbb  add     r15, rax
0x180007fbe  jmp     short loc_180007F41
0x180007fc0  cmp     r8b, 9
0x180007fc4  jnz     loc_180007EF0
0x180007fca  lea     eax, [rdx-71h]
0x180007fcd  cmp     al, r12b
0x180007fd0  ja      loc_180007EF0
0x180007fd6  movzx   eax, dil
0x180007fda  add     rax, rax
0x180007fdd  inc     dil
0x180007fe0  mov     byte ptr [rbp+rax*8+3Fh+var_A8+5], dl
0x180007fe4  jmp     loc_180007EB6
0x180007fe9  test    r15, r15
0x180007fec  jnz     short loc_180008025
0x180007fee  mov     rcx, [rsp+130h+SRWLock]; SRWLock
0x180007ff3  call    cs:__imp_ReleaseSRWLockShared
0x180007ff9  test    rsi, rsi
0x180007ffc  jnz     loc_18000814D
0x180008002  mov     eax, r13d
0x180008005  mov     rcx, [rbp+3Fh+var_50]
0x180008009  xor     rcx, rsp; StackCookie
0x18000800c  call    __security_check_cookie
0x180008011  add     rsp, 0F8h
0x180008018  pop     r15
0x18000801a  pop     r14
0x18000801c  pop     r13
0x18000801e  pop     r12
0x180008020  pop     rdi
0x180008021  pop     rsi
0x180008022  pop     rbx
0x180008023  pop     rbp
0x180008024  retn
0x180008025  add     dil, r12b
0x180008028  cmp     dil, r12b
0x18000802b  jbe     short loc_180007FEE
0x18000802d  mov     r10, r12
0x180008030  mov     rcx, [r15+10h]
0x180008034  mov     rax, r10
0x180008037  add     rax, rax
0x18000803a  mov     rdx, [rsp+rax*8+130h+var_D0.Ptr]
0x18000803f  movzx   r8d, byte ptr [rcx+rax*8+0Dh]
0x180008045  mov     rcx, [rcx+rax*8]
0x180008049  mov     rdx, [rdx]
0x18000804c  call    AggregateField
0x180008051  inc     r12b
0x180008054  inc     r10
0x180008057  cmp     r12b, dil
0x18000805a  jb      short loc_180008030
0x18000805c  jmp     short loc_180007FEE
0x18000805e  cmp     dword ptr [rbx+100h], 400h
0x180008068  jnb     loc_18000813C
0x18000806e  test    rsi, rsi
0x180008071  jnz     short loc_1800080B7
0x180008073  lea     rax, [rsp+130h+var_F8]
0x180008078  mov     r9b, dil
0x18000807b  mov     [rsp+130h+UserData], rax
0x180008080  lea     r8, [rsp+130h+var_D0]
0x180008085  mov     dl, 8
0x180008087  mov     [rsp+130h+UserDataCount], r14d
0x18000808c  lea     rcx, [rsp+130h+EventDescriptor]
0x180008091  call    CreateNewEventEntry
0x180008096  mov     rsi, [rsp+130h+var_F8]
0x18000809b  mov     r13d, eax
0x18000809e  test    rsi, rsi
0x1800080a1  jnz     short loc_1800080B7
0x1800080a3  cmp     eax, 8
0x1800080a6  jnz     loc_180008131
0x1800080ac  inc     dword ptr [rbx+130h]
0x1800080b2  jmp     loc_180007FEE
0x1800080b7  xor     eax, eax
0x1800080b9  lock cmpxchg [r15], rsi
0x1800080be  jnz     loc_180007F4B
0x1800080c4  xor     esi, esi
0x1800080c6  lea     eax, [rsi+1]
0x1800080c9  lock xadd [rbx+100h], eax
0x1800080d1  inc     eax
0x1800080d3  cmp     eax, 1
0x1800080d6  jnz     short loc_1800080EA
0x1800080d8  mov     edx, [rbx+160h]
0x1800080de  mov     rcx, [rbx+158h]
0x1800080e5  call    EnableFlushTimer
0x1800080ea  mov     eax, [rbx+100h]
0x1800080f0  cmp     [rbx+120h], eax
0x1800080f6  jnb     loc_180007FEE
0x1800080fc  mov     [rbx+120h], eax
0x180008102  jmp     loc_180007FEE
0x180008107  mov     r8d, [rsp+rcx+130h+var_D0.Size]; Size
0x18000810c  mov     rdx, [rdx+rcx]; Buf2
0x180008110  mov     rcx, [rsp+rcx+130h+var_D0.Ptr]; Buf1
0x180008115  call    memcmp_0
0x18000811a  test    eax, eax
0x18000811c  jnz     loc_180007F9B
0x180008122  inc     r14d
0x180008125  jmp     loc_180007F78
0x18000812a  xor     eax, eax
0x18000812c  jmp     loc_180007F9B
0x180008131  inc     dword ptr [rbx+134h]
0x180008137  jmp     loc_180007FEE
0x18000813c  inc     dword ptr [rbx+12Ch]
0x180008142  mov     r13d, 0EAh
0x180008148  jmp     loc_180007FEE
0x18000814d  mov     rcx, rsi
0x180008150  call    DestroyEventEntry
0x180008155  jmp     loc_180008002
0x18000815a  mov     rcx, cs:RegHandle; RegHandle
0x180008161  lea     rax, [rsp+130h+var_D0]
0x180008166  mov     [rsp+130h+UserData], rax; UserData
0x18000816b  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180008170  xor     r9d, r9d; RelatedActivityId
0x180008173  mov     [rsp+130h+UserDataCount], r11d; UserDataCount
0x180008178  xor     r8d, r8d; ActivityId
0x18000817b  call    EventWriteTransfer_0
0x180008180  mov     r13d, eax
0x180008183  jmp     loc_180008002
```
