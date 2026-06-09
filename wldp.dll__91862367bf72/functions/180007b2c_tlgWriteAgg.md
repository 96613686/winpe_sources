# _tlgWriteAgg

- ea: `0x180007b2c`
- end: `0x180007fab`
- name: `_tlgWriteAgg`
- size: `1151`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800015e8`
- `0x180001a18`
- `0x1800023c4`
- `0x180007484`
- `0x18000786c`

## callees

- `0x180007b2c`
- `0x180007fc0`
- `0x180019dac`
- `0x1800229ec`
- `0x180022beb`
- `0x18003db88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007d1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007d1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ce2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007ce2`

## pseudocode

```c
__int64 __fastcall tlgWriteAgg(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 a4,
        PEVENT_DATA_DESCRIPTOR a5)
{
  unsigned __int8 v7; // r15
  unsigned int v9; // r12d
  ULONGLONG v10; // rax
  unsigned __int16 *v11; // rdx
  ULONG v12; // ecx
  ULONGLONG Ptr; // rax
  unsigned __int8 v14; // bp
  ULONGLONG v15; // r9
  char *v16; // rcx
  char v17; // al
  char v20; // r8
  char *v21; // rax
  __int64 v22; // rbx
  signed __int64 v23; // rsi
  unsigned int v24; // edx
  unsigned __int64 i; // r8
  int v26; // eax
  unsigned __int8 v27; // r8
  unsigned __int64 k; // r9
  int v29; // eax
  unsigned int v30; // r13d
  int v31; // edx
  int v32; // r9d
  volatile signed __int64 *v33; // rdi
  UCHAR v35; // dl
  __int64 v36; // rax
  volatile signed __int64 v37; // rbp
  __int64 v38; // r13
  int v39; // eax
  unsigned int v40; // eax
  unsigned int m; // edi
  __int64 v42; // r9
  signed __int64 v43; // r8
  __int64 v44; // rax
  int v45; // r10d
  volatile signed __int64 *v46; // rdx
  unsigned int NewEventEntry; // eax
  unsigned int v48; // eax
  signed __int64 v49; // rax
  volatile signed __int64 v50; // rtt
  unsigned int v51; // [rsp+34h] [rbp-64h]
  signed __int64 v52; // [rsp+38h] [rbp-60h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v55; // [rsp+A0h] [rbp+8h]
  unsigned __int8 j; // [rsp+A8h] [rbp+10h]
  unsigned __int8 v57; // [rsp+C0h] [rbp+28h]

  v7 = 2;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  v9 = -1073741811;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  v10 = *(_QWORD *)(a2 + 3);
  v11 = (unsigned __int16 *)(a2 + 11);
  EventDescriptor.Keyword = v10;
  a5->Ptr = *(_QWORD *)(a1 + 8);
  v12 = **(unsigned __int16 **)(a1 + 8);
  a5[1].Ptr = (ULONGLONG)v11;
  a5->Size = v12;
  a5->Reserved = 2;
  a5[1].Size = *v11;
  a5[1].Reserved = 1;
  if ( *(void (__fastcall **)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))(a1 + 40) == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    Ptr = a5[1].Ptr;
    v14 = 0;
    v15 = Ptr + a5[1].Size;
    v16 = (char *)(Ptr + 2);
    do
      v17 = *v16++;
    while ( v17 < 0 );
    while ( *v16++ )
      ;
    while ( (unsigned __int64)v16 < v15 )
    {
      while ( *v16++ )
        ;
      if ( *v16 >= 0 )
        break;
      v20 = *v16 & 0x7F;
      v21 = v16 + 1;
      v16 += 2;
      if ( *v21 >= 0 )
        break;
      while ( 1 )
      {
        v35 = *v16;
        if ( *v16 >= 0 )
          break;
        if ( v35 != 0x80 )
          goto LABEL_9;
        ++v16;
      }
      if ( v20 != 9 || (unsigned __int8)(v35 - 113) > 2u )
        break;
      v36 = v14++;
      a5[v36 + 2].Reserved1 = v35;
    }
LABEL_9:
    v57 = v14;
    if ( v14 )
    {
      v22 = *(_QWORD *)(a1 + 48);
      v23 = 0;
      v9 = 0;
      v52 = 0;
      v24 = 0;
      for ( i = 0; i < 8; ++i )
      {
        v26 = *((unsigned __int8 *)&a5[1].Ptr + i);
        v24 = (1025 * (v24 + v26)) ^ ((1025 * (v24 + v26)) >> 6);
      }
      v55 = v14 + 2;
      v27 = v14 + 2;
      for ( j = a4; v27 < a4; ++v27 )
      {
        for ( k = 0; k < a5[v27].Size; v24 = (1025 * (v24 + v29)) ^ ((1025 * (v24 + v29)) >> 6) )
          v29 = *(unsigned __int8 *)(a5[v27].Ptr + k++);
      }
      v30 = 32769 * ((9 * v24) ^ ((9 * v24) >> 11));
      SRWLock = (PSRWLOCK)(v22 + 264);
      v51 = v30;
      AcquireSRWLockShared((PSRWLOCK)(v22 + 264));
      v33 = (volatile signed __int64 *)(v22 + 8LL * (v30 & 0x1F));
      while ( 1 )
      {
        if ( !*v33 )
        {
          if ( *(_DWORD *)(v22 + 256) >= 0x400u )
          {
            ++*(_DWORD *)(v22 + 300);
            v9 = 234;
            goto LABEL_20;
          }
          if ( !v23 )
          {
            LOBYTE(v31) = j;
            LOBYTE(v32) = v14;
            NewEventEntry = CreateNewEventEntry(
                              (unsigned int)&EventDescriptor,
                              v31,
                              (_DWORD)a5,
                              v32,
                              v30,
                              (__int64)&v52);
            v23 = v52;
            v9 = NewEventEntry;
            if ( !v52 )
            {
              if ( NewEventEntry == 8 )
                ++*(_DWORD *)(v22 + 304);
              else
                ++*(_DWORD *)(v22 + 308);
              goto LABEL_20;
            }
          }
          if ( !_InterlockedCompareExchange64(v33, v23, 0) )
          {
            v23 = 0;
            if ( _InterlockedIncrement((volatile signed __int32 *)(v22 + 256)) == 1 )
              EnableFlushTimer(*(struct _TP_TIMER **)(v22 + 344), *(_DWORD *)(v22 + 352));
            v48 = *(_DWORD *)(v22 + 256);
            if ( *(_DWORD *)(v22 + 288) < v48 )
              *(_DWORD *)(v22 + 288) = v48;
            goto LABEL_20;
          }
        }
        v37 = *v33;
        if ( v30 == *(_DWORD *)(*v33 + 40) )
        {
          v38 = *(_QWORD *)(v37 + 16);
          v39 = memcmp_0(&a5[1], (const void *)(v38 + 16), 8u);
          if ( !v39 )
          {
            v40 = j;
            for ( m = *(unsigned __int8 *)(v37 + 45) + 2; m < v40; ++m )
            {
              v39 = a5[m].Size - *(_DWORD *)(16LL * m + v38 + 8);
              if ( v39 )
                goto LABEL_37;
              v39 = memcmp_0((const void *)a5[m].Ptr, *(const void **)(16LL * m + v38), a5[m].Size);
              if ( v39 )
                goto LABEL_37;
              v40 = j;
            }
            v39 = 0;
          }
LABEL_37:
          v30 = v51;
        }
        else
        {
          v39 = v30 - *(_DWORD *)(v37 + 40);
        }
        if ( !v39 )
          break;
        v33 = (volatile signed __int64 *)(v37 + (((__int64)v39 >> 63) & 0xFFFFFFFFFFFFFFF8uLL) + 32);
        v14 = v57;
      }
      if ( v37 && v55 > 2u )
      {
        v42 = 2;
        do
        {
          v43 = *(_QWORD *)a5[v42].Ptr;
          v44 = *(_QWORD *)(v37 + 16);
          v45 = *(unsigned __int8 *)(v44 + 16 * v42 + 13);
          v46 = *(volatile signed __int64 **)(v44 + 16 * v42);
          if ( v45 == 113 )
          {
            _InterlockedAdd64(v46, v43);
          }
          else if ( (unsigned int)*(unsigned __int8 *)(v44 + 16 * v42 + 13) - 114 < 2 )
          {
            do
            {
              v49 = *v46;
              if ( v45 == 114 )
              {
                if ( v43 >= v49 )
                  break;
              }
              else if ( v43 <= v49 )
              {
                break;
              }
              v50 = *v46;
            }
            while ( v50 != _InterlockedCompareExchange64(v46, v43, v49) );
          }
          ++v7;
          ++v42;
        }
        while ( v7 < v55 );
      }
LABEL_20:
      ReleaseSRWLockShared(SRWLock);
      if ( v23 )
        DestroyEventEntry(v23);
    }
    else
    {
      return EventWriteTransfer_0(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, a4, a5);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180007b2c  mov     [rsp+arg_10], rbx
0x180007b31  push    rbp
0x180007b32  push    rsi
0x180007b33  push    rdi
0x180007b34  push    r12
0x180007b36  push    r13
0x180007b38  push    r14
0x180007b3a  push    r15
0x180007b3c  sub     rsp, 60h
0x180007b40  movzx   eax, byte ptr [rdx]
0x180007b43  mov     r10, rcx
0x180007b46  mov     r14, [rsp+98h+arg_20]
0x180007b4e  mov     r15d, 2
0x180007b54  shl     eax, 18h
0x180007b57  mov     r11d, r9d
0x180007b5a  mov     dword ptr [rsp+98h+EventDescriptor.Id], eax
0x180007b5e  mov     r12d, 0C000000Dh
0x180007b64  movzx   eax, word ptr [rdx+1]
0x180007b68  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180007b6c  lea     r13d, [r15-1]
0x180007b70  mov     rax, [rdx+3]
0x180007b74  add     rdx, 0Bh
0x180007b78  mov     [rsp+98h+EventDescriptor.Keyword], rax
0x180007b7d  mov     rax, [rcx+8]
0x180007b81  mov     [r14], rax
0x180007b84  mov     rax, [rcx+8]
0x180007b88  movzx   ecx, word ptr [rax]
0x180007b8b  mov     [r14+10h], rdx
0x180007b8f  mov     [r14+8], ecx
0x180007b93  mov     [r14+0Ch], r15d
0x180007b97  movzx   eax, word ptr [rdx]
0x180007b9a  lea     rdx, _TraceLoggingMetadata
0x180007ba1  mov     [r14+18h], eax
0x180007ba5  lea     rax, _TraceLoggingMetadataEnd
0x180007bac  sub     eax, edx
0x180007bae  mov     [r14+1Ch], r13d
0x180007bb2  mov     dword ptr [rsp+98h+arg_20], eax
0x180007bb9  mov     eax, dword ptr [rsp+98h+arg_20]
0x180007bc0  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180007bc7  cmp     [r10+28h], rax
0x180007bcb  jnz     loc_180007D2C
0x180007bd1  mov     rax, [r14+10h]
0x180007bd5  xor     bpl, bpl
0x180007bd8  mov     r9d, [r14+18h]
0x180007bdc  add     r9, rax
0x180007bdf  lea     rcx, [rax+2]
0x180007be3  movzx   eax, byte ptr [rcx]
0x180007be6  add     rcx, r13
0x180007be9  test    al, al
0x180007beb  js      short loc_180007BE3
0x180007bed  mov     al, [rcx]
0x180007bef  add     rcx, r13
0x180007bf2  test    al, al
0x180007bf4  jnz     short loc_180007BED
0x180007bf6  cmp     rcx, r9
0x180007bf9  jnb     short loc_180007C22
0x180007bfb  mov     al, [rcx]
0x180007bfd  add     rcx, r13
0x180007c00  test    al, al
0x180007c02  jnz     short loc_180007BFB
0x180007c04  mov     r8b, [rcx]
0x180007c07  test    r8b, r8b
0x180007c0a  jns     short loc_180007C22
0x180007c0c  add     rcx, r13
0x180007c0f  and     r8b, 7Fh
0x180007c13  mov     rax, rcx
0x180007c16  inc     rcx
0x180007c19  cmp     byte ptr [rax], 0
0x180007c1c  jl      loc_180007D47
0x180007c22  mov     byte ptr [rsp+98h+arg_20], bpl
0x180007c2a  test    bpl, bpl
0x180007c2d  jz      loc_180007F11
0x180007c33  mov     rbx, [r10+30h]
0x180007c37  xor     esi, esi
0x180007c39  xor     r12d, r12d
0x180007c3c  mov     [rsp+98h+var_60], rsi
0x180007c41  xor     edx, edx
0x180007c43  xor     r8d, r8d
0x180007c46  movzx   eax, byte ptr [r14+r8+10h]
0x180007c4c  add     r8, r13
0x180007c4f  add     eax, edx
0x180007c51  imul    ecx, eax, 401h
0x180007c57  mov     edx, ecx
0x180007c59  shr     edx, 6
0x180007c5c  xor     edx, ecx
0x180007c5e  cmp     r8, 8
0x180007c62  jb      short loc_180007C46
0x180007c64  lea     eax, [r15+rbp]
0x180007c68  mov     dil, r11b
0x180007c6b  mov     [rsp+98h+arg_0], al
0x180007c72  mov     r8b, al
0x180007c75  mov     [rsp+98h+arg_8], edi
0x180007c7c  cmp     al, r11b
0x180007c7f  jnb     short loc_180007CBD
0x180007c81  movzx   eax, r8b
0x180007c85  xor     r9d, r9d
0x180007c88  add     rax, rax
0x180007c8b  mov     r10d, [r14+rax*8+8]
0x180007c90  mov     r11, [r14+rax*8]
0x180007c94  test    r10, r10
0x180007c97  jz      short loc_180007CB5
0x180007c99  movzx   eax, byte ptr [r11+r9]
0x180007c9e  add     r9, r13
0x180007ca1  add     eax, edx
0x180007ca3  imul    ecx, eax, 401h
0x180007ca9  mov     edx, ecx
0x180007cab  shr     edx, 6
0x180007cae  xor     edx, ecx
0x180007cb0  cmp     r9, r10
0x180007cb3  jb      short loc_180007C99
0x180007cb5  add     r8b, r13b
0x180007cb8  cmp     r8b, dil
0x180007cbb  jb      short loc_180007C81
0x180007cbd  lea     eax, [rdx+rdx*8]
0x180007cc0  mov     ecx, eax
0x180007cc2  shr     ecx, 0Bh
0x180007cc5  xor     ecx, eax
0x180007cc7  lea     rax, [rbx+108h]
0x180007cce  imul    r13d, ecx, 8001h
0x180007cd5  mov     rcx, rax; SRWLock
0x180007cd8  mov     [rsp+98h+SRWLock], rax
0x180007cdd  mov     [rsp+98h+var_64], r13d
0x180007ce2  call    cs:__imp_AcquireSRWLockShared
0x180007ce8  mov     eax, r13d
0x180007ceb  and     eax, 1Fh
0x180007cee  lea     rdi, [rbx+rax*8]
0x180007cf2  cmp     qword ptr [rdi], 0
0x180007cf6  jnz     loc_180007D85
0x180007cfc  cmp     dword ptr [rbx+100h], 400h
0x180007d06  jb      loc_180007E69
0x180007d0c  inc     dword ptr [rbx+12Ch]
0x180007d12  mov     r12d, 0EAh
0x180007d18  mov     rcx, [rsp+98h+SRWLock]; SRWLock
0x180007d1d  call    cs:__imp_ReleaseSRWLockShared
0x180007d23  test    rsi, rsi
0x180007d26  jnz     loc_180007F9E
0x180007d2c  mov     rbx, [rsp+98h+arg_10]
0x180007d34  mov     eax, r12d
0x180007d37  add     rsp, 60h
0x180007d3b  pop     r15
0x180007d3d  pop     r14
0x180007d3f  pop     r13
0x180007d41  pop     r12
0x180007d43  pop     rdi
0x180007d44  pop     rsi
0x180007d45  pop     rbp
0x180007d46  retn
0x180007d47  mov     dl, [rcx]
0x180007d49  test    dl, dl
0x180007d4b  jns     short loc_180007D5B
0x180007d4d  cmp     dl, 80h
0x180007d50  jnz     loc_180007C22
0x180007d56  add     rcx, r13
0x180007d59  jmp     short loc_180007D47
0x180007d5b  cmp     r8b, 9
0x180007d5f  jnz     loc_180007C22
0x180007d65  lea     eax, [rdx-71h]
0x180007d68  cmp     al, r15b
0x180007d6b  ja      loc_180007C22
0x180007d71  movzx   eax, bpl
0x180007d75  add     rax, rax
0x180007d78  add     bpl, r13b
0x180007d7b  mov     [r14+rax*8+2Dh], dl
0x180007d80  jmp     loc_180007BF6
0x180007d85  mov     rbp, [rdi]
0x180007d88  cmp     r13d, [rbp+28h]
0x180007d8c  jnz     loc_180007F06
0x180007d92  mov     r13, [rbp+10h]
0x180007d96  lea     rcx, [r14+10h]; Buf1
0x180007d9a  mov     r8d, 8; Size
0x180007da0  lea     rdx, [r13+10h]; Buf2
0x180007da4  call    memcmp_0
0x180007da9  test    eax, eax
0x180007dab  jnz     short loc_180007DF6
0x180007dad  movzx   edi, byte ptr [rbp+2Dh]
0x180007db1  movzx   eax, byte ptr [rsp+98h+arg_8]
0x180007db9  add     edi, r15d
0x180007dbc  mov     [rsp+98h+var_68], eax
0x180007dc0  cmp     edi, eax
0x180007dc2  jnb     short loc_180007DF4
0x180007dc4  mov     ecx, edi
0x180007dc6  shl     rcx, 4
0x180007dca  mov     eax, [r14+rcx+8]
0x180007dcf  sub     eax, [rcx+r13+8]
0x180007dd4  jnz     short loc_180007DF6
0x180007dd6  mov     r8d, [r14+rcx+8]; Size
0x180007ddb  mov     rdx, [rcx+r13]; Buf2
0x180007ddf  mov     rcx, [r14+rcx]; Buf1
0x180007de3  call    memcmp_0
0x180007de8  test    eax, eax
0x180007dea  jnz     short loc_180007DF6
0x180007dec  mov     eax, [rsp+98h+var_68]
0x180007df0  inc     edi
0x180007df2  jmp     short loc_180007DC0
0x180007df4  xor     eax, eax
0x180007df6  mov     r13d, [rsp+98h+var_64]
0x180007dfb  test    eax, eax
0x180007dfd  jnz     loc_180007EE7
0x180007e03  test    rbp, rbp
0x180007e06  jz      loc_180007D18
0x180007e0c  mov     r11b, [rsp+98h+arg_0]
0x180007e14  cmp     r11b, r15b
0x180007e17  jbe     loc_180007D18
0x180007e1d  mov     r9, r15
0x180007e20  mov     rcx, r9
0x180007e23  add     rcx, rcx
0x180007e26  mov     rax, [r14+rcx*8]
0x180007e2a  mov     r8, [rax]
0x180007e2d  mov     rax, [rbp+10h]
0x180007e31  movzx   r10d, byte ptr [rax+rcx*8+0Dh]
0x180007e37  mov     rdx, [rax+rcx*8]
0x180007e3b  mov     ecx, r10d
0x180007e3e  sub     ecx, 71h ; 'q'
0x180007e41  jz      loc_180007F95
0x180007e47  sub     ecx, 1
0x180007e4a  jz      loc_180007F6C
0x180007e50  cmp     ecx, 1
0x180007e53  jz      loc_180007F6C
0x180007e59  inc     r15b
0x180007e5c  inc     r9
0x180007e5f  cmp     r15b, r11b
0x180007e62  jb      short loc_180007E20
0x180007e64  jmp     loc_180007D18
0x180007e69  test    rsi, rsi
0x180007e6c  jnz     short loc_180007EA5
0x180007e6e  mov     dl, byte ptr [rsp+98h+arg_8]
0x180007e75  lea     rax, [rsp+98h+var_60]
0x180007e7a  mov     [rsp+98h+UserData], rax
0x180007e7f  lea     rcx, [rsp+98h+EventDescriptor]
0x180007e84  mov     r9b, bpl
0x180007e87  mov     [rsp+98h+UserDataCount], r13d
0x180007e8c  mov     r8, r14
0x180007e8f  call    CreateNewEventEntry
0x180007e94  mov     rsi, [rsp+98h+var_60]
0x180007e99  mov     r12d, eax
0x180007e9c  test    rsi, rsi
0x180007e9f  jz      loc_180007F3A
0x180007ea5  xor     eax, eax
0x180007ea7  lock cmpxchg [rdi], rsi
0x180007eac  jnz     loc_180007D85
0x180007eb2  xor     esi, esi
0x180007eb4  lea     eax, [rsi+1]
0x180007eb7  lock xadd [rbx+100h], eax
0x180007ebf  inc     eax
0x180007ec1  cmp     eax, 1
0x180007ec4  jz      loc_180007F55
0x180007eca  mov     eax, [rbx+100h]
0x180007ed0  cmp     [rbx+120h], eax
0x180007ed6  jnb     loc_180007D18
0x180007edc  mov     [rbx+120h], eax
0x180007ee2  jmp     loc_180007D18
0x180007ee7  movsxd  rdi, eax
0x180007eea  sar     rdi, 3Fh
0x180007eee  and     rdi, 0FFFFFFFFFFFFFFF8h
0x180007ef2  add     rdi, 20h ; ' '
0x180007ef6  add     rdi, rbp
0x180007ef9  mov     bpl, byte ptr [rsp+98h+arg_20]
0x180007f01  jmp     loc_180007CF2
0x180007f06  mov     eax, r13d
0x180007f09  sub     eax, [rbp+28h]
0x180007f0c  jmp     loc_180007DFB
0x180007f11  mov     rcx, [r10+20h]; RegHandle
0x180007f15  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x180007f1a  movzx   eax, r11b
0x180007f1e  xor     r9d, r9d; RelatedActivityId
0x180007f21  mov     [rsp+98h+UserData], r14; UserData
0x180007f26  xor     r8d, r8d; ActivityId
0x180007f29  mov     [rsp+98h+UserDataCount], eax; UserDataCount
0x180007f2d  call    EventWriteTransfer_0
0x180007f32  mov     r12d, eax
0x180007f35  jmp     loc_180007D2C
0x180007f3a  cmp     eax, 8
0x180007f3d  jnz     short loc_180007F4A
0x180007f3f  inc     dword ptr [rbx+130h]
0x180007f45  jmp     loc_180007D18
0x180007f4a  inc     dword ptr [rbx+134h]
0x180007f50  jmp     loc_180007D18
0x180007f55  mov     edx, [rbx+160h]
0x180007f5b  mov     rcx, [rbx+158h]
0x180007f62  call    EnableFlushTimer
0x180007f67  jmp     loc_180007ECA
0x180007f6c  mov     rax, [rdx]
0x180007f6f  cmp     r10d, 72h ; 'r'
0x180007f73  jnz     short loc_180007F80
0x180007f75  cmp     r8, rax
0x180007f78  jge     loc_180007E59
0x180007f7e  jmp     short loc_180007F89
0x180007f80  cmp     r8, rax
0x180007f83  jle     loc_180007E59
0x180007f89  lock cmpxchg [rdx], r8
0x180007f8e  jnz     short loc_180007F6C
0x180007f90  jmp     loc_180007E59
0x180007f95  lock add [rdx], r8
0x180007f99  jmp     loc_180007E59
0x180007f9e  mov     rcx, rsi
0x180007fa1  call    DestroyEventEntry
0x180007fa6  jmp     loc_180007D2C
```
