# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180006dc0`
- end: `0x18000747d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U?$_tlgWrapSz@G@@U2@U4@U4@U4@U4@U4@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@333AEBU?$_tlgWrapSz@G@@355555222@Z`
- size: `1725`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d9b4`

## callees

- `0x180006dc0`
- `0x180007fc0`
- `0x180019dac`
- `0x180021ec0`
- `0x1800229ec`
- `0x180022beb`
- `0x18003db88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800071b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800071b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007179`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007179`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        int **a13,
        int **a14,
        int **a15,
        int **a16,
        int **a17,
        __int64 a18,
        __int64 a19,
        __int64 a20)
{
  __int64 v22; // rcx
  unsigned __int8 v23; // di
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  int *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  int *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  int *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  int *v39; // rdx
  int v40; // ecx
  unsigned int v41; // r13d
  __int64 v42; // rcx
  unsigned __int8 v43; // r12
  unsigned __int64 v44; // r9
  char *v45; // rcx
  char v46; // al
  char v49; // r8
  char *v50; // rax
  __int64 v51; // rbx
  signed __int64 v52; // r14
  unsigned int v53; // edx
  unsigned __int64 i; // r8
  int v55; // eax
  unsigned __int8 j; // r8
  unsigned __int64 k; // r9
  int v58; // eax
  __int64 v59; // rdx
  int v60; // r9d
  unsigned int v61; // ecx
  volatile signed __int64 *m; // rsi
  char v64; // dl
  __int64 v65; // rax
  volatile signed __int64 v66; // r15
  int v67; // eax
  unsigned int n; // esi
  __int64 v69; // r9
  signed __int64 v70; // r8
  __int64 v71; // rax
  int v72; // r10d
  volatile signed __int64 *v73; // rdx
  signed __int64 v74; // rax
  unsigned int NewEventEntry; // eax
  unsigned int v76; // eax
  volatile signed __int64 v77; // rtt
  unsigned __int8 v78; // [rsp+30h] [rbp-D0h]
  unsigned int v79; // [rsp+34h] [rbp-CCh]
  signed __int64 v80; // [rsp+38h] [rbp-C8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *Buf1; // [rsp+70h] [rbp-90h] BYREF
  int v85; // [rsp+78h] [rbp-88h]
  int v86; // [rsp+7Ch] [rbp-84h]
  __int64 v87; // [rsp+80h] [rbp-80h]
  _QWORD v88[14]; // [rsp+88h] [rbp-78h]
  int v89; // [rsp+F8h] [rbp-8h]
  int v90; // [rsp+FCh] [rbp-4h]
  __int64 v91; // [rsp+100h] [rbp+0h]
  __int64 v92; // [rsp+108h] [rbp+8h]
  int *v93; // [rsp+110h] [rbp+10h]
  int v94; // [rsp+118h] [rbp+18h]
  int v95; // [rsp+11Ch] [rbp+1Ch]
  int *v96; // [rsp+120h] [rbp+20h]
  int v97; // [rsp+128h] [rbp+28h]
  int v98; // [rsp+12Ch] [rbp+2Ch]
  int *v99; // [rsp+130h] [rbp+30h]
  int v100; // [rsp+138h] [rbp+38h]
  int v101; // [rsp+13Ch] [rbp+3Ch]
  int *v102; // [rsp+140h] [rbp+40h]
  int v103; // [rsp+148h] [rbp+48h]
  int v104; // [rsp+14Ch] [rbp+4Ch]
  int *v105; // [rsp+150h] [rbp+50h]
  int v106; // [rsp+158h] [rbp+58h]
  int v107; // [rsp+15Ch] [rbp+5Ch]
  __int64 v108; // [rsp+160h] [rbp+60h]
  __int64 v109; // [rsp+168h] [rbp+68h]
  __int64 v110; // [rsp+170h] [rbp+70h]
  __int64 v111; // [rsp+178h] [rbp+78h]
  __int64 v112; // [rsp+180h] [rbp+80h]
  __int64 v113; // [rsp+188h] [rbp+88h]

  v112 = a20;
  v110 = a19;
  v22 = -1;
  v108 = a18;
  v23 = 2;
  v113 = 8;
  v111 = 8;
  v109 = 8;
  v24 = *a17;
  if ( *a17 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_1800457FC;
    v26 = 2;
  }
  v106 = v26;
  v105 = v24;
  v107 = 0;
  v27 = *a16;
  if ( *a16 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v27 + v28) );
    v29 = 2 * v28 + 2;
  }
  else
  {
    v27 = &dword_1800457FC;
    v29 = 2;
  }
  v103 = v29;
  v102 = v27;
  v104 = 0;
  v30 = *a15;
  if ( *a15 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_1800457FC;
    v32 = 2;
  }
  v100 = v32;
  v99 = v30;
  v101 = 0;
  v33 = *a14;
  if ( *a14 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &dword_1800457FC;
    v35 = 2;
  }
  v97 = v35;
  v96 = v33;
  v98 = 0;
  v36 = *a13;
  if ( *a13 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &dword_1800457FC;
    v38 = 2;
  }
  v94 = v38;
  v91 = a12;
  v93 = v36;
  v95 = 0;
  v92 = 4;
  v39 = *a11;
  if ( *a11 )
  {
    do
      ++v22;
    while ( *((_WORD *)v39 + v22) );
    v40 = 2 * v22 + 2;
  }
  else
  {
    v39 = &dword_1800457FC;
    v40 = 2;
  }
  v88[11] = a10;
  v41 = -1073741811;
  v88[9] = a9;
  v88[7] = a8;
  v89 = v40;
  v88[13] = v39;
  v90 = 0;
  v42 = *a7;
  v88[3] = a6;
  v88[1] = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v88[5] = v42;
  v88[12] = 4;
  v88[10] = 4;
  v88[8] = 4;
  v88[6] = 16;
  v88[4] = 4;
  v88[2] = 4;
  v87 = a4;
  v88[0] = 8;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v85 = *(unsigned __int16 *)(a2 + 11);
  Buf1 = a2 + 11;
  UserData.Reserved = 2;
  v86 = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    v43 = 0;
    v44 = (unsigned __int64)&Buf1[v85];
    v45 = (char *)(Buf1 + 2);
    do
      v46 = *v45++;
    while ( v46 < 0 );
    while ( *v45++ )
      ;
    while ( (unsigned __int64)v45 < v44 )
    {
      while ( *v45++ )
        ;
      if ( *v45 >= 0 )
        break;
      v49 = *v45 & 0x7F;
      v50 = v45 + 1;
      v45 += 2;
      if ( *v50 >= 0 )
        break;
      while ( 1 )
      {
        v64 = *v45;
        if ( *v45 >= 0 )
          break;
        if ( v64 != (char)0x80 )
          goto LABEL_32;
        ++v45;
      }
      if ( v49 != 9 || (unsigned __int8)(v64 - 113) > 2u )
        break;
      v65 = 2LL * v43++;
      BYTE5(v88[v65]) = v64;
    }
LABEL_32:
    if ( v43 )
    {
      v51 = *(_QWORD *)(a1 + 48);
      v52 = 0;
      v80 = 0;
      v41 = 0;
      v53 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v55 = *((unsigned __int8 *)&Buf1 + i);
        v53 = (1025 * (v53 + v55)) ^ ((1025 * (v53 + v55)) >> 6);
      }
      v78 = v43 + 2;
      for ( j = v43 + 2; j < 0x13u; ++j )
      {
        for ( k = 0; k < *(&UserData.Size + 4 * j); v53 = (1025 * (v53 + v58)) ^ ((1025 * (v53 + v58)) >> 6) )
        {
          v58 = *(unsigned __int8 *)(k + *(&UserData.Ptr + 2 * j));
          ++k;
        }
      }
      v79 = 32769 * ((9 * v53) ^ ((9 * v53) >> 11));
      SRWLock = (PSRWLOCK)(v51 + 264);
      AcquireSRWLockShared((PSRWLOCK)(v51 + 264));
      v61 = v79;
      for ( m = (volatile signed __int64 *)(v51 + 8LL * (v79 & 0x1F));
            ;
            m = (volatile signed __int64 *)(v66 + 32 + (((__int64)v67 >> 63) & 0xFFFFFFFFFFFFFFF8uLL)) )
      {
        if ( !*m )
        {
          if ( *(_DWORD *)(v51 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v51 + 300);
            v41 = 234;
            goto LABEL_43;
          }
          if ( !v52 )
          {
            LOBYTE(v60) = v43;
            LOBYTE(v59) = 19;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v59,
                              (unsigned int)&UserData,
                              v60,
                              v61,
                              (__int64)&v80);
            v52 = v80;
            v41 = NewEventEntry;
            if ( !v80 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v51 + 304);
              else
                ++*(_DWORD *)(v51 + 308);
              goto LABEL_43;
            }
            v61 = v79;
          }
          if ( !_InterlockedCompareExchange64(m, v52, 0) )
          {
            v52 = 0;
            if ( _InterlockedIncrement((volatile signed __int32 *)(v51 + 256)) == 1 )
              EnableFlushTimer(*(struct _TP_TIMER **)(v51 + 344), *(_DWORD *)(v51 + 352));
            v76 = *(_DWORD *)(v51 + 256);
            if ( *(_DWORD *)(v51 + 288) < v76 )
              *(_DWORD *)(v51 + 288) = v76;
            goto LABEL_43;
          }
        }
        v66 = *m;
        if ( v61 == *(_DWORD *)(*m + 40) )
        {
          v67 = memcmp_0(&Buf1, (const void *)(*(_QWORD *)(v66 + 16) + 16LL), 8u);
          if ( !v67 )
          {
            for ( n = *(unsigned __int8 *)(v66 + 45) + 2; n < 0x13; ++n )
            {
              v59 = *(_QWORD *)(v66 + 16);
              v67 = *(&UserData.Size + 4 * n) - *(_DWORD *)(16LL * n + v59 + 8);
              if ( v67 )
                goto LABEL_60;
              v67 = memcmp_0(
                      *((const void **)&UserData.Ptr + 2 * n),
                      *(const void **)(16LL * n + v59),
                      *(&UserData.Size + 4 * n));
              if ( v67 )
                goto LABEL_60;
            }
            v67 = 0;
          }
LABEL_60:
          v61 = v79;
        }
        else
        {
          v67 = v61 - *(_DWORD *)(v66 + 40);
        }
        if ( !v67 )
          break;
      }
      if ( v66 && v78 > 2u )
      {
        v69 = 2;
        do
        {
          v70 = **((_QWORD **)&UserData.Ptr + 2 * v69);
          v71 = *(_QWORD *)(v66 + 16);
          v72 = *(unsigned __int8 *)(v71 + 16 * v69 + 13);
          v73 = *(volatile signed __int64 **)(v71 + 16 * v69);
          if ( v72 == 113 )
          {
            _InterlockedAdd64(v73, v70);
          }
          else if ( (unsigned int)*(unsigned __int8 *)(v71 + 16 * v69 + 13) - 114 <= 1 )
          {
            do
            {
              v74 = *v73;
              if ( v72 == 114 )
              {
                if ( v70 >= v74 )
                  break;
              }
              else if ( v70 <= v74 )
              {
                break;
              }
              v77 = *v73;
            }
            while ( v77 != _InterlockedCompareExchange64(v73, v70, v74) );
          }
          ++v23;
          ++v69;
        }
        while ( v23 < v78 );
      }
LABEL_43:
      ReleaseSRWLockShared(SRWLock);
      if ( v52 )
        DestroyEventEntry(v52);
    }
    else
    {
      return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 0x13u, &UserData);
    }
  }
  return v41;
}

```

## disassembly

```asm
0x180006dc0  push    rbp
0x180006dc2  push    rbx
0x180006dc3  push    rsi
0x180006dc4  push    rdi
0x180006dc5  push    r12
0x180006dc7  push    r13
0x180006dc9  push    r14
0x180006dcb  push    r15
0x180006dcd  lea     rbp, [rsp-0A8h]
0x180006dd5  sub     rsp, 1A8h
0x180006ddc  mov     rax, cs:__security_cookie
0x180006de3  xor     rax, rsp
0x180006de6  mov     [rbp+0E0h+var_50], rax
0x180006ded  mov     rax, [rbp+0E0h+arg_98]
0x180006df4  lea     r11, dword_1800457FC
0x180006dfb  mov     [rbp+0E0h+var_60], rax
0x180006e02  xor     r15d, r15d
0x180006e05  mov     rax, [rbp+0E0h+arg_90]
0x180006e0c  mov     r8, rdx
0x180006e0f  mov     [rbp+0E0h+var_70], rax
0x180006e13  mov     r10, rcx
0x180006e16  mov     rax, [rbp+0E0h+arg_88]
0x180006e1d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006e21  mov     [rbp+0E0h+var_80], rax
0x180006e25  lea     edi, [r15+2]
0x180006e29  mov     rax, [rbp+0E0h+arg_80]
0x180006e30  mov     [rbp+0E0h+var_58], 8
0x180006e3b  mov     [rbp+0E0h+var_68], 8
0x180006e43  mov     [rbp+0E0h+var_78], 8
0x180006e4b  mov     rdx, [rax]
0x180006e4e  test    rdx, rdx
0x180006e51  jz      loc_1800073E0
0x180006e57  mov     rax, rcx
0x180006e5a  inc     rax
0x180006e5d  cmp     [rdx+rax*2], r15w
0x180006e62  jnz     short loc_180006E5A
0x180006e64  lea     eax, ds:2[rax*2]
0x180006e6b  mov     [rbp+0E0h+var_88], eax
0x180006e6e  mov     rax, [rbp+0E0h+arg_78]
0x180006e75  mov     [rbp+0E0h+var_90], rdx
0x180006e79  mov     [rbp+0E0h+var_84], r15d
0x180006e7d  mov     rdx, [rax]
0x180006e80  test    rdx, rdx
0x180006e83  jz      loc_1800073EA
0x180006e89  mov     rax, rcx
0x180006e8c  inc     rax
0x180006e8f  cmp     [rdx+rax*2], r15w
0x180006e94  jnz     short loc_180006E8C
0x180006e96  lea     eax, ds:2[rax*2]
0x180006e9d  mov     [rbp+0E0h+var_98], eax
0x180006ea0  mov     rax, [rbp+0E0h+arg_70]
0x180006ea7  mov     [rbp+0E0h+var_A0], rdx
0x180006eab  mov     [rbp+0E0h+var_94], r15d
0x180006eaf  mov     rdx, [rax]
0x180006eb2  test    rdx, rdx
0x180006eb5  jz      loc_1800073F4
0x180006ebb  mov     rax, rcx
0x180006ebe  inc     rax
0x180006ec1  cmp     [rdx+rax*2], r15w
0x180006ec6  jnz     short loc_180006EBE
0x180006ec8  lea     eax, ds:2[rax*2]
0x180006ecf  mov     [rbp+0E0h+var_A8], eax
0x180006ed2  mov     rax, [rbp+0E0h+arg_68]
0x180006ed9  mov     [rbp+0E0h+var_B0], rdx
0x180006edd  mov     [rbp+0E0h+var_A4], r15d
0x180006ee1  mov     rdx, [rax]
0x180006ee4  test    rdx, rdx
0x180006ee7  jz      loc_1800073FE
0x180006eed  mov     rax, rcx
0x180006ef0  inc     rax
0x180006ef3  cmp     [rdx+rax*2], r15w
0x180006ef8  jnz     short loc_180006EF0
0x180006efa  lea     eax, ds:2[rax*2]
0x180006f01  mov     [rbp+0E0h+var_B8], eax
0x180006f04  mov     rax, [rbp+0E0h+arg_60]
0x180006f0b  mov     [rbp+0E0h+var_C0], rdx
0x180006f0f  mov     [rbp+0E0h+var_B4], r15d
0x180006f13  mov     rdx, [rax]
0x180006f16  test    rdx, rdx
0x180006f19  jz      loc_180007408
0x180006f1f  mov     rax, rcx
0x180006f22  inc     rax
0x180006f25  cmp     [rdx+rax*2], r15w
0x180006f2a  jnz     short loc_180006F22
0x180006f2c  lea     eax, ds:2[rax*2]
0x180006f33  mov     [rbp+0E0h+var_C8], eax
0x180006f36  mov     rax, [rbp+0E0h+arg_58]
0x180006f3d  mov     [rbp+0E0h+var_E0], rax
0x180006f41  mov     rax, [rbp+0E0h+arg_50]
0x180006f48  mov     [rbp+0E0h+var_D0], rdx
0x180006f4c  mov     [rbp+0E0h+var_C4], r15d
0x180006f50  mov     [rbp+0E0h+var_D8], 4
0x180006f58  mov     rdx, [rax]
0x180006f5b  test    rdx, rdx
0x180006f5e  jz      loc_180007412
0x180006f64  inc     rcx
0x180006f67  cmp     [rdx+rcx*2], r15w
0x180006f6c  jnz     short loc_180006F64
0x180006f6e  lea     ecx, ds:2[rcx*2]
0x180006f75  mov     rax, [rbp+0E0h+arg_48]
0x180006f7c  mov     esi, 1
0x180006f81  mov     [rbp+0E0h+var_100], rax
0x180006f85  mov     r13d, 0C000000Dh
0x180006f8b  mov     rax, [rbp+0E0h+arg_40]
0x180006f92  mov     [rbp+0E0h+var_110], rax
0x180006f96  mov     rax, [rbp+0E0h+arg_38]
0x180006f9d  mov     [rbp+0E0h+var_120], rax
0x180006fa1  mov     rax, [rbp+0E0h+arg_30]
0x180006fa8  mov     [rbp+0E0h+var_E8], ecx
0x180006fab  mov     [rbp+0E0h+var_F0], rdx
0x180006faf  mov     [rbp+0E0h+var_E4], r15d
0x180006fb3  mov     rcx, [rax]
0x180006fb6  mov     rax, [rbp+0E0h+arg_28]
0x180006fbd  mov     [rbp+0E0h+var_140], rax
0x180006fc1  mov     rax, [rbp+0E0h+arg_20]
0x180006fc8  mov     [rbp+0E0h+var_150], rax
0x180006fcc  movzx   eax, byte ptr [r8]
0x180006fd0  shl     eax, 18h
0x180006fd3  mov     dword ptr [rsp+1E0h+EventDescriptor.Id], eax
0x180006fd7  movzx   eax, word ptr [r8+1]
0x180006fdc  mov     dword ptr [rsp+1E0h+EventDescriptor.Level], eax
0x180006fe0  mov     rax, [r8+3]
0x180006fe4  mov     [rsp+1E0h+EventDescriptor.Keyword], rax
0x180006fe9  mov     rax, [r10+8]
0x180006fed  mov     [rsp+1E0h+var_180.Ptr], rax
0x180006ff2  mov     [rbp+0E0h+var_130], rcx
0x180006ff6  lea     rcx, [r8+0Bh]
0x180006ffa  mov     [rbp+0E0h+var_F8], 4
0x180007002  mov     [rbp+0E0h+var_108], 4
0x18000700a  mov     [rbp+0E0h+var_118], 4
0x180007012  mov     [rbp+0E0h+var_128], 10h
0x18000701a  mov     [rbp+0E0h+var_138], 4
0x180007022  mov     [rbp+0E0h+var_148], 4
0x18000702a  mov     [rbp+0E0h+var_160], r9
0x18000702e  mov     [rbp+0E0h+var_158], 8
0x180007036  movzx   eax, word ptr [rax]
0x180007039  mov     [rsp+1E0h+var_180.Size], eax
0x18000703d  movzx   eax, word ptr [rcx]
0x180007040  mov     [rsp+1E0h+var_168], eax
0x180007044  lea     rax, _TraceLoggingMetadataEnd
0x18000704b  mov     [rsp+1E0h+Buf1], rcx
0x180007050  lea     rcx, _TraceLoggingMetadata
0x180007057  sub     eax, ecx
0x180007059  mov     dword ptr [rsp+1E0h+var_180.0Ch], edi
0x18000705d  mov     [rsp+1E0h+var_164], esi
0x180007061  mov     [rsp+1E0h+var_1AC], eax
0x180007065  mov     eax, [rsp+1E0h+var_1AC]
0x180007069  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180007070  cmp     [r10+28h], rax
0x180007074  jnz     loc_1800071C5
0x18000707a  mov     rax, [rsp+1E0h+Buf1]
0x18000707f  mov     r12b, r15b
0x180007082  mov     r9d, [rsp+1E0h+var_168]
0x180007087  add     r9, rax
0x18000708a  lea     rcx, [rax+2]
0x18000708e  movzx   eax, byte ptr [rcx]
0x180007091  add     rcx, rsi
0x180007094  test    al, al
0x180007096  js      short loc_18000708E
0x180007098  mov     al, [rcx]
0x18000709a  add     rcx, rsi
0x18000709d  test    al, al
0x18000709f  jnz     short loc_180007098
0x1800070a1  cmp     rcx, r9
0x1800070a4  jnb     short loc_1800070CD
0x1800070a6  mov     al, [rcx]
0x1800070a8  add     rcx, rsi
0x1800070ab  test    al, al
0x1800070ad  jnz     short loc_1800070A6
0x1800070af  mov     r8b, [rcx]
0x1800070b2  test    r8b, r8b
0x1800070b5  jns     short loc_1800070CD
0x1800070b7  add     rcx, rsi
0x1800070ba  and     r8b, 7Fh
0x1800070be  mov     rax, rcx
0x1800070c1  inc     rcx
0x1800070c4  cmp     [rax], r15b
0x1800070c7  jl      loc_1800071EB
0x1800070cd  test    r12b, r12b
0x1800070d0  jz      loc_1800073B2
0x1800070d6  mov     rbx, [r10+30h]
0x1800070da  mov     r14, r15
0x1800070dd  mov     [rsp+1E0h+var_1A8], r15
0x1800070e2  mov     r13d, r15d
0x1800070e5  mov     edx, r15d
0x1800070e8  mov     r8, r15
0x1800070eb  movzx   eax, byte ptr [rsp+r8+1E0h+Buf1]
0x1800070f1  add     r8, rsi
0x1800070f4  add     eax, edx
0x1800070f6  imul    ecx, eax, 401h
0x1800070fc  mov     edx, ecx
0x1800070fe  shr     edx, 6
0x180007101  xor     edx, ecx
0x180007103  cmp     r8, 8
0x180007107  jb      short loc_1800070EB
0x180007109  lea     eax, [rdi+r12]
0x18000710d  mov     [rsp+1E0h+var_1B0], al
0x180007111  mov     r8b, al
0x180007114  cmp     al, 13h
0x180007116  jnb     short loc_180007156
0x180007118  movzx   eax, r8b
0x18000711c  mov     r9, r15
0x18000711f  add     rax, rax
0x180007122  mov     r10d, [rsp+rax*8+1E0h+var_180.Size]
0x180007127  mov     r11, [rsp+rax*8+1E0h+var_180.Ptr]
0x18000712c  test    r10, r10
0x18000712f  jz      short loc_18000714D
0x180007131  movzx   eax, byte ptr [r9+r11]
0x180007136  add     r9, rsi
0x180007139  add     eax, edx
0x18000713b  imul    ecx, eax, 401h
0x180007141  mov     edx, ecx
0x180007143  shr     edx, 6
0x180007146  xor     edx, ecx
0x180007148  cmp     r9, r10
0x18000714b  jb      short loc_180007131
0x18000714d  add     r8b, sil
0x180007150  cmp     r8b, 13h
0x180007154  jb      short loc_180007118
0x180007156  lea     eax, [rdx+rdx*8]
0x180007159  mov     ecx, eax
0x18000715b  shr     ecx, 0Bh
0x18000715e  xor     ecx, eax
0x180007160  imul    eax, ecx, 8001h
0x180007166  mov     [rsp+1E0h+var_1AC], eax
0x18000716a  lea     rax, [rbx+108h]
0x180007171  mov     rcx, rax; SRWLock
0x180007174  mov     [rsp+1E0h+SRWLock], rax
0x180007179  call    cs:__imp_AcquireSRWLockShared
0x18000717f  mov     ecx, [rsp+1E0h+var_1AC]
0x180007183  mov     eax, ecx
0x180007185  and     eax, 1Fh
0x180007188  lea     rsi, [rbx+rax*8]
0x18000718c  cmp     [rsi], r15
0x18000718f  jnz     loc_180007228
0x180007195  cmp     dword ptr [rbx+100h], 400h
0x18000719f  jb      loc_18000730C
0x1800071a5  inc     dword ptr [rbx+12Ch]
0x1800071ab  mov     r13d, 0EAh
0x1800071b1  mov     rcx, [rsp+1E0h+SRWLock]; SRWLock
0x1800071b6  call    cs:__imp_ReleaseSRWLockShared
0x1800071bc  test    r14, r14
0x1800071bf  jnz     loc_180007470
0x1800071c5  mov     eax, r13d
0x1800071c8  mov     rcx, [rbp+0E0h+var_50]
0x1800071cf  xor     rcx, rsp; StackCookie
0x1800071d2  call    __security_check_cookie
0x1800071d7  add     rsp, 1A8h
0x1800071de  pop     r15
0x1800071e0  pop     r14
0x1800071e2  pop     r13
0x1800071e4  pop     r12
0x1800071e6  pop     rdi
0x1800071e7  pop     rsi
0x1800071e8  pop     rbx
0x1800071e9  pop     rbp
0x1800071ea  retn
0x1800071eb  mov     dl, [rcx]
0x1800071ed  test    dl, dl
0x1800071ef  jns     short loc_1800071FF
0x1800071f1  cmp     dl, 80h
0x1800071f4  jnz     loc_1800070CD
0x1800071fa  add     rcx, rsi
0x1800071fd  jmp     short loc_1800071EB
0x1800071ff  cmp     r8b, 9
0x180007203  jnz     loc_1800070CD
0x180007209  lea     eax, [rdx-71h]
0x18000720c  cmp     al, dil
0x18000720f  ja      loc_1800070CD
0x180007215  movzx   eax, r12b
0x180007219  add     rax, rax
0x18000721c  add     r12b, sil
0x18000721f  mov     byte ptr [rbp+rax*8+0E0h+var_158+5], dl
0x180007223  jmp     loc_1800070A1
0x180007228  mov     r15, [rsi]
0x18000722b  cmp     ecx, [r15+28h]
0x18000722f  jnz     loc_1800073A7
0x180007235  mov     rdx, [r15+10h]
0x180007239  lea     rcx, [rsp+1E0h+Buf1]; Buf1
0x18000723e  add     rdx, 10h; Buf2
0x180007242  mov     r8d, 8; Size
0x180007248  call    memcmp_0
0x18000724d  test    eax, eax
0x18000724f  jnz     short loc_18000728E
0x180007251  movzx   esi, byte ptr [r15+2Dh]
0x180007256  add     esi, edi
0x180007258  cmp     esi, 13h
0x18000725b  jnb     short loc_18000728C
0x18000725d  mov     rdx, [r15+10h]
0x180007261  mov     ecx, esi
0x180007263  shl     rcx, 4
0x180007267  mov     eax, [rsp+rcx+1E0h+var_180.Size]
0x18000726b  sub     eax, [rcx+rdx+8]
0x18000726f  jnz     short loc_18000728E
0x180007271  mov     r8d, [rsp+rcx+1E0h+var_180.Size]; Size
0x180007276  mov     rdx, [rcx+rdx]; Buf2
0x18000727a  mov     rcx, [rsp+rcx+1E0h+var_180.Ptr]; Buf1
0x18000727f  call    memcmp_0
0x180007284  test    eax, eax
0x180007286  jnz     short loc_18000728E
  ... truncated ...
```
