# CSatelliteCargoContext::SendLogMessage(_GUID const *,CSQLSatelliteConnection *,_SQLSatellite_String const *,ESQLSatelliteLogMessageType,bool)

- ea: `0x100414e30`
- end: `0x1004152e7`
- name: `?SendLogMessage@CSatelliteCargoContext@@SAJPEBU_GUID@@PEAVCSQLSatelliteConnection@@PEBU_SQLSatellite_String@@W4ESQLSatelliteLogMessageType@@_N@Z`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1004069d0`

## callees

- `0x100414e30`
- `0x10041ec10`
- `0x10041f180`
- `0x100455f90`
- `0x100471d80`
- `0x100478330`
- `0x100478670`
- `0x10047a370`
- `0x10047ec50`
- `0x10048823d`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1004151a1`
- `KERNEL32!GetCurrentThreadId` at `0x1004151a1`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100415215`
- `sqldk!?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z` at `0x100415215`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1004152c4`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x1004152c4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100415033`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100415033`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100415027`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100415027`

## pseudocode

```c
__int64 __fastcall CSatelliteCargoContext::SendLogMessage(
        _OWORD *a1,
        CSQLSatelliteConnection *a2,
        __int64 *a3,
        char a4,
        char a5)
{
  CSQLSatelliteConnection *v5; // r13
  int v6; // eax
  char v7; // r12
  bool v8; // zf
  int v9; // eax
  signed int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // r15
  int v13; // r14d
  unsigned int v14; // edi
  unsigned int v15; // esi
  __int64 v16; // rcx
  __int64 Ex2; // rax
  unsigned int v18; // edx
  const void *v19; // r15
  int v20; // r13d
  int v21; // edi
  __int64 v22; // r12
  int *v23; // r14
  _OWORD *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v33; // rbx
  __int64 v34; // rdi
  int v36; // ecx
  int v37; // [rsp+20h] [rbp-E0h]
  void **v38; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h]
  int *v40; // [rsp+40h] [rbp-C0h]
  int v41; // [rsp+48h] [rbp-B8h]
  unsigned int v42; // [rsp+4Ch] [rbp-B4h]
  __int64 v43; // [rsp+50h] [rbp-B0h]
  __int64 v44; // [rsp+58h] [rbp-A8h]
  int v45; // [rsp+60h] [rbp-A0h]
  char v46; // [rsp+64h] [rbp-9Ch]
  const void *v47; // [rsp+65h] [rbp-9Bh]
  unsigned int v48; // [rsp+70h] [rbp-90h]
  int v49; // [rsp+74h] [rbp-8Ch]
  unsigned int v50; // [rsp+78h] [rbp-88h]
  unsigned int v51; // [rsp+7Ch] [rbp-84h]
  __int64 v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  __int128 v54; // [rsp+90h] [rbp-70h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h]
  signed int v56; // [rsp+A8h] [rbp-58h]
  DWORD v57; // [rsp+ACh] [rbp-54h]
  const char *v58; // [rsp+B0h] [rbp-50h]
  int v59; // [rsp+B8h] [rbp-48h]
  _BYTE v60[216]; // [rsp+C0h] [rbp-40h] BYREF
  int v61; // [rsp+198h] [rbp+98h]
  __int64 v62; // [rsp+1A0h] [rbp+A0h]
  unsigned int v65; // [rsp+210h] [rbp+110h]

  v5 = a2;
  v52 = *a3;
  v6 = *((_DWORD *)a3 + 2);
  v7 = a4;
  v8 = 2 * v6 == 0;
  v9 = 2 * v6;
  v65 = 0;
  v51 = v9;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( !v8 )
  {
    while ( 1 )
    {
      v39 = 0;
      HIDWORD(v43) = 0;
      v44 = 0;
      v15 = v9 - v14;
      v47 = 0;
      v50 = v9 - v14;
      v16 = *((_QWORD *)v5 + 8);
      v38 = &CSQLSatelliteMessageLog::`vftable';
      Ex2 = SNIPacketAllocateEx2(v16, 1u, 0);
      if ( !Ex2 || (v18 = *(_DWORD *)(Ex2 + 180), v48 = v18, v18 < 0x80D) )
      {
        v10 = -2147024882;
        goto LABEL_51;
      }
      v53 = Ex2;
      if ( v11 )
        *(_QWORD *)(v12 + 208) = Ex2;
      else
        v11 = Ex2;
      v19 = (const void *)(v52 + v14);
      v49 = v13 + 1;
      v46 = v7;
      v47 = v19;
      if ( v15 <= 0x800 )
      {
        v20 = v15;
        v45 = v15;
      }
      else
      {
        v20 = 2048;
        v45 = 2048;
      }
      v21 = v18 - 24;
      v22 = *(_QWORD *)(Ex2 + 168) + *(unsigned int *)(Ex2 + 184);
      v42 = v18;
      v39 = v22;
      v41 = v18 - 24;
      *(_WORD *)v22 = 1;
      v23 = (int *)(v22 + 24);
      *(_WORD *)(v22 + 2) &= 0x800Bu;
      *(_WORD *)(v22 + 2) |= 0xBu;
      v40 = (int *)(v22 + 24);
      v43 = 2;
      CSQLSatelliteMessage::FireXEvent(&v38, 2);
      if ( v21 < (unsigned int)(v20 + 5) )
        goto LABEL_17;
      *v23 = v20;
      if ( v21 >= 4 )
      {
        v23 = (int *)(v22 + 28);
        v21 -= 4;
        v40 = (int *)(v22 + 28);
        v41 = v21;
      }
      *(_BYTE *)v23 = a4;
      if ( v21 >= 1 )
      {
        v23 = (int *)((char *)v23 + 1);
        --v21;
        v40 = v23;
        v41 = v21;
      }
      memcpy_s(v23, (unsigned int)v21, v19, (unsigned int)v20);
      v10 = 0;
      if ( v20 > v21 )
      {
LABEL_17:
        v10 = -2089418750;
      }
      else
      {
        v40 = (int *)((char *)v23 + v20);
        v41 = v21 - v20;
      }
      HIDWORD(v43) = v10;
      if ( v10 < 0 )
        goto LABEL_51;
      v24 = (_OWORD *)(v22 + 8);
      if ( v22 == -8 )
        goto LABEL_23;
      if ( !a1 )
        break;
      *v24 = *a1;
LABEL_24:
      v25 = 0;
      v26 = _RTDynamicCast_0(
              g_satelliteExecutor,
              0,
              &ISatelliteExecutor `RTTI Type Descriptor',
              &CSatelliteSpeesExecutor `RTTI Type Descriptor',
              0);
      if ( v26 )
      {
        v27 = *(_QWORD *)(v26 + 2080);
        if ( v27 )
          v25 = *(_QWORD *)(v27 + 296);
      }
      v44 = v25;
      *(_WORD *)(v22 + 2) |= 0x8000u;
      if ( (int)v40 - (int)v39 > v48 )
      {
        HIDWORD(v43) = -2089418750;
        v10 = -2089418750;
        goto LABEL_51;
      }
      *(_DWORD *)(v22 + 4) = (_DWORD)v40 - v39;
      CSQLSatelliteMessage::FireXEvent(&v38, 1);
      if ( v25 )
        _InterlockedIncrement64((volatile signed __int64 *)(v25 + 8 * ((*(_WORD *)(v22 + 2) & 0x7FFF) + 52LL) + 8));
      v13 = v49;
      if ( v49 == 1 || (v28 = v20, v50 <= v20) )
      {
        v29 = *(_QWORD *)(v11 + 168) + *(unsigned int *)(v11 + 184);
        if ( !v29 )
        {
          do
          {
            v31 = *(_QWORD *)(v11 + 208);
            *(_QWORD *)(v11 + 208) = 0;
            SNIPacketRelease((struct SNI_Packet *)v11);
            v11 = v31;
          }
          while ( v31 );
          LOWORD(v30) = 1359;
          goto LABEL_42;
        }
        *(_DWORD *)(v11 + 176) = *(_DWORD *)(v29 + 4);
        v30 = CSQLSatelliteConnection::WriteMessage(a2, (struct SNI_Packet *)v11);
        v28 = v20;
        v12 = 0;
        v11 = 0;
        v13 = 0;
        if ( v30 && v30 != 997 )
        {
          if ( v30 <= 0 )
          {
            v10 = v30;
            goto LABEL_43;
          }
LABEL_42:
          v10 = (unsigned __int16)v30 | 0x80070000;
LABEL_43:
          if ( g_extensibilityErrorRingBuffer )
          {
            CurrentThreadId = GetCurrentThreadId();
            v33 = g_extensibilityErrorRingBuffer;
            v57 = CurrentThreadId;
            v55 = 0;
            v58 = "CSatelliteCargoContext::SendLogMessage";
            v54 = 0;
            v56 = v10;
            v59 = 1935;
            v61 = 0;
            v62 = 0;
            if ( *(_QWORD *)(g_extensibilityErrorRingBuffer + 64LL) )
              StackFrames<24>::CaptureCurrent(v60, 1);
            if ( (dword_1005113AC & 0x10) != 0 )
              ExtensibilityErrorRecord::FireMatchingEvent(&v54, v60);
            SOS_RingBuffer::StoreRecordInternalWithoutEvent(v33, &v54, v60);
          }
          v11 = 0;
LABEL_50:
          if ( v10 < 0 )
            goto LABEL_51;
          goto LABEL_52;
        }
      }
      else
      {
        v12 = v53;
      }
      v9 = v51;
      v14 = v28 + v65;
      v5 = a2;
      v65 = v14;
      if ( v51 <= v14 )
        goto LABEL_57;
      v7 = a4;
    }
    *v24 = 0;
LABEL_23:
    *_errno() = 22;
    _invalid_parameter_noinfo();
    goto LABEL_24;
  }
LABEL_57:
  if ( !a5 )
    goto LABEL_50;
  if ( *((int *)v5 + 38) <= 0 )
    goto LABEL_50;
  LOBYTE(v37) = 1;
  v36 = WaitableBase::Wait((char *)v5 + 352, 0xFFFFFFFFLL, (char *)v5 + 224, 0, v37);
  if ( !*((_BYTE *)v5 + 57) && !v36 )
    goto LABEL_50;
  v10 = -2147467260;
LABEL_51:
  _mm_lfence();
  FireTraceEvent(1, (unsigned int)v10, a1, L"SendLogMessage Failed.");
LABEL_52:
  if ( v11 )
  {
    do
    {
      v34 = *(_QWORD *)(v11 + 208);
      *(_QWORD *)(v11 + 208) = 0;
      SNIPacketRelease((struct SNI_Packet *)v11);
      v11 = v34;
    }
    while ( v34 );
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x100414e30  mov     [rsp-8+arg_18], r9b
0x100414e35  mov     [rsp-8+arg_8], rdx
0x100414e3a  mov     [rsp-8+arg_0], rcx
0x100414e3f  push    rbp
0x100414e40  push    rbx
0x100414e41  push    rsi
0x100414e42  push    rdi
0x100414e43  push    r12
0x100414e45  push    r13
0x100414e47  push    r14
0x100414e49  push    r15
0x100414e4b  lea     rbp, [rsp-0B8h]
0x100414e53  sub     rsp, 1B8h
0x100414e5a  mov     rax, [r8]
0x100414e5d  mov     r13, rdx
0x100414e60  xor     edx, edx
0x100414e62  mov     [rbp+0F0h+var_170], rax
0x100414e66  mov     eax, [r8+8]
0x100414e6a  movzx   r12d, r9b
0x100414e6e  add     eax, eax
0x100414e70  mov     [rbp+0F0h+arg_10], edx
0x100414e76  mov     [rsp+1F0h+var_174], eax
0x100414e7a  mov     esi, edx
0x100414e7c  mov     ebx, edx
0x100414e7e  lea     ecx, [rdx+1]
0x100414e81  mov     r15d, edx
0x100414e84  mov     r14d, edx
0x100414e87  mov     edi, edx
0x100414e89  jz      loc_100415291
0x100414e8f  mov     esi, eax
0x100414e91  mov     [rsp+1F0h+var_1B8], rdx
0x100414e96  mov     [rsp+1F0h+var_19C], edx
0x100414e9a  lea     r9, ??_7CSQLSatelliteMessageLog@@6B@; const CSQLSatelliteMessageLog::`vftable'
0x100414ea1  mov     [rsp+1F0h+var_198], rdx
0x100414ea6  sub     esi, edi
0x100414ea8  mov     [rsp+1F0h+var_18B], rdx
0x100414ead  xor     r8d, r8d
0x100414eb0  mov     edx, ecx
0x100414eb2  mov     [rsp+1F0h+var_178], esi
0x100414eb6  mov     rcx, [r13+40h]
0x100414eba  mov     [rsp+1F0h+var_1C0], r9
0x100414ebf  call    SNIPacketAllocateEx2
0x100414ec4  test    rax, rax
0x100414ec7  jz      loc_10041528A
0x100414ecd  mov     edx, [rax+0B4h]
0x100414ed3  mov     [rsp+1F0h+var_180], edx
0x100414ed7  cmp     edx, 80Dh
0x100414edd  jb      loc_10041528A
0x100414ee3  mov     [rbp+0F0h+var_168], rax
0x100414ee7  test    rbx, rbx
0x100414eea  jnz     short loc_100414EF1
0x100414eec  mov     rbx, rax
0x100414eef  jmp     short loc_100414EF8
0x100414ef1  mov     [r15+0D0h], rax
0x100414ef8  inc     r14d
0x100414efb  mov     r15d, edi
0x100414efe  add     r15, [rbp+0F0h+var_170]
0x100414f02  mov     [rsp+1F0h+var_17C], r14d
0x100414f07  mov     [rsp+1F0h+var_18C], r12b
0x100414f0c  mov     [rsp+1F0h+var_18B], r15
0x100414f11  cmp     esi, 800h
0x100414f17  jbe     short loc_100414F26
0x100414f19  mov     r13d, 800h
0x100414f1f  mov     [rsp+1F0h+var_190], r13d
0x100414f24  jmp     short loc_100414F2D
0x100414f26  mov     r13d, esi
0x100414f29  mov     [rsp+1F0h+var_190], esi
0x100414f2d  mov     r12d, [rax+0B8h]
0x100414f34  lea     edi, [rdx-18h]
0x100414f37  mov     rax, [rax+0A8h]
0x100414f3e  mov     ecx, 800Bh
0x100414f43  add     r12, rax
0x100414f46  mov     [rsp+1F0h+var_1A4], edx
0x100414f4a  mov     eax, 1
0x100414f4f  mov     [rsp+1F0h+var_1B8], r12
0x100414f54  mov     [rsp+1F0h+var_1A8], edi
0x100414f58  mov     [r12], ax
0x100414f5d  lea     r14, [r12+18h]
0x100414f62  and     [r12+2], cx
0x100414f68  mov     eax, 2
0x100414f6d  or      word ptr [r12+2], 0Bh
0x100414f74  lea     rcx, [rsp+1F0h+var_1C0]
0x100414f79  mov     edx, eax
0x100414f7b  mov     [rsp+1F0h+var_1B0], r14
0x100414f80  mov     [rsp+50h], rax
0x100414f85  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x100414f8a  lea     eax, [r13+5]
0x100414f8e  cmp     edi, eax
0x100414f90  jb      short loc_100414FF2
0x100414f92  mov     [r14], r13d
0x100414f95  cmp     edi, 4
0x100414f98  jl      short loc_100414FAA
0x100414f9a  add     r14, 4
0x100414f9e  sub     edi, 4
0x100414fa1  mov     [rsp+1F0h+var_1B0], r14
0x100414fa6  mov     [rsp+1F0h+var_1A8], edi
0x100414faa  movzx   eax, [rbp+0F0h+arg_18]
0x100414fb1  mov     [r14], al
0x100414fb4  cmp     edi, 1
0x100414fb7  jl      short loc_100414FC7
0x100414fb9  inc     r14
0x100414fbc  dec     edi
0x100414fbe  mov     [rsp+1F0h+var_1B0], r14
0x100414fc3  mov     [rsp+1F0h+var_1A8], edi
0x100414fc7  mov     r9d, r13d; SourceSize
0x100414fca  mov     r8, r15; Source
0x100414fcd  mov     edx, edi; DestinationSize
0x100414fcf  mov     rcx, r14; Destination
0x100414fd2  call    memcpy_s
0x100414fd7  xor     esi, esi
0x100414fd9  cmp     r13d, edi
0x100414fdc  jg      short loc_100414FF2
0x100414fde  movsxd  rax, r13d
0x100414fe1  add     r14, rax
0x100414fe4  sub     edi, r13d
0x100414fe7  mov     [rsp+1F0h+var_1B0], r14
0x100414fec  mov     [rsp+1F0h+var_1A8], edi
0x100414ff0  jmp     short loc_100414FF7
0x100414ff2  mov     esi, 83760002h
0x100414ff7  mov     [rsp+1F0h+var_19C], esi
0x100414ffb  test    esi, esi
0x100414ffd  js      loc_100415221
0x100415003  lea     rax, [r12+8]
0x100415008  test    rax, rax
0x10041500b  jz      short loc_100415027
0x10041500d  mov     rcx, [rbp+0F0h+arg_0]
0x100415014  test    rcx, rcx
0x100415017  jz      short loc_100415021
0x100415019  movups  xmm0, xmmword ptr [rcx]
0x10041501c  movups  xmmword ptr [rax], xmm0
0x10041501f  jmp     short loc_100415039
0x100415021  xorps   xmm0, xmm0
0x100415024  movups  xmmword ptr [rax], xmm0
0x100415027  call    cs:__imp__errno
0x10041502d  mov     dword ptr [rax], 16h
0x100415033  call    cs:__imp__invalid_parameter_noinfo
0x100415039  mov     rcx, cs:?g_satelliteExecutor@@3PEAVISatelliteExecutor@@EA; ISatelliteExecutor * g_satelliteExecutor
0x100415040  lea     r9, ??_R0?AVCSatelliteSpeesExecutor@@@8; CSatelliteSpeesExecutor `RTTI Type Descriptor'
0x100415047  xor     edi, edi
0x100415049  lea     r8, ??_R0?AVISatelliteExecutor@@@8; ISatelliteExecutor `RTTI Type Descriptor'
0x100415050  xor     edx, edx
0x100415052  mov     [rsp+1F0h+var_1D0], edi
0x100415056  call    __RTDynamicCast_0
0x10041505b  test    rax, rax
0x10041505e  jz      short loc_100415073
0x100415060  mov     rax, [rax+820h]
0x100415067  test    rax, rax
0x10041506a  jz      short loc_100415073
0x10041506c  mov     rdi, [rax+128h]
0x100415073  mov     eax, 8000h
0x100415078  mov     [rsp+1F0h+var_198], rdi
0x10041507d  or      [r12+2], ax
0x100415083  mov     eax, dword ptr [rsp+1F0h+var_1B0]
0x100415087  sub     eax, dword ptr [rsp+1F0h+var_1B8]
0x10041508b  cmp     eax, [rsp+1F0h+var_180]
0x10041508f  ja      loc_10041527B
0x100415095  mov     edx, 1
0x10041509a  mov     [r12+4], eax
0x10041509f  lea     rcx, [rsp+1F0h+var_1C0]
0x1004150a4  call    ?FireXEvent@CSQLSatelliteMessage@@IEAAXW4ESQLSatelliteMessage_OperationCode@@@Z; CSQLSatelliteMessage::FireXEvent(ESQLSatelliteMessage_OperationCode)
0x1004150a9  test    rdi, rdi
0x1004150ac  jz      short loc_1004150CE
0x1004150ae  movzx   edx, word ptr [r12+2]
0x1004150b4  mov     eax, 2
0x1004150b9  cdqe
0x1004150bb  and     edx, 7FFFh
0x1004150c1  imul    rcx, rax, 1Ah
0x1004150c5  add     rdx, rcx
0x1004150c8  lock inc qword ptr [rdi+rdx*8+8]
0x1004150ce  mov     r14d, [rsp+1F0h+var_17C]
0x1004150d3  cmp     r14d, 1
0x1004150d7  jz      short loc_1004150E3
0x1004150d9  mov     ecx, r13d
0x1004150dc  cmp     [rsp+1F0h+var_178], r13d
0x1004150e1  ja      short loc_10041512A
0x1004150e3  mov     eax, [rbx+0B8h]
0x1004150e9  add     rax, [rbx+0A8h]
0x1004150f0  jz      short loc_100415163
0x1004150f2  mov     eax, [rax+4]
0x1004150f5  mov     rdx, rbx; struct SNI_Packet *
0x1004150f8  mov     rcx, [rbp+0F0h+arg_8]; this
0x1004150ff  mov     [rbx+0B0h], eax
0x100415105  call    ?WriteMessage@CSQLSatelliteConnection@@QEAAKPEAVSNI_Packet@@@Z; CSQLSatelliteConnection::WriteMessage(SNI_Packet *)
0x10041510a  xor     edx, edx
0x10041510c  mov     ecx, r13d
0x10041510f  mov     r15d, edx
0x100415112  mov     ebx, edx
0x100415114  mov     r14d, edx
0x100415117  test    eax, eax
0x100415119  jz      short loc_100415130
0x10041511b  cmp     eax, 3E5h
0x100415120  jz      short loc_100415130
0x100415122  test    eax, eax
0x100415124  jg      short loc_10041518A
0x100415126  mov     esi, eax
0x100415128  jmp     short loc_100415193
0x10041512a  mov     r15, [rbp+0F0h+var_168]
0x10041512e  xor     edx, edx
0x100415130  mov     edi, [rbp+0F0h+arg_10]
0x100415136  mov     eax, [rsp+1F0h+var_174]
0x10041513a  add     edi, ecx
0x10041513c  mov     r13, [rbp+0F0h+arg_8]
0x100415143  mov     [rbp+0F0h+arg_10], edi
0x100415149  cmp     eax, edi
0x10041514b  jbe     loc_100415291
0x100415151  movzx   r12d, [rbp+0F0h+arg_18]
0x100415159  mov     ecx, 1
0x10041515e  jmp     loc_100414E8F
0x100415163  mov     rdi, [rbx+0D0h]
0x10041516a  mov     rcx, rbx; struct SNI_Packet *
0x10041516d  mov     qword ptr [rbx+0D0h], 0
0x100415178  call    SNIPacketRelease
0x10041517d  mov     rbx, rdi
0x100415180  test    rdi, rdi
0x100415183  jnz     short loc_100415163
0x100415185  mov     eax, 54Fh
0x10041518a  movzx   esi, ax
0x10041518d  or      esi, 80070000h
0x100415193  cmp     cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A, 0; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x10041519b  jz      loc_10041521B
0x1004151a1  call    cs:__imp_GetCurrentThreadId
0x1004151a7  mov     rbx, cs:?g_extensibilityErrorRingBuffer@@3VExtensibilityErrorRingBuffer@@A; ExtensibilityErrorRingBuffer g_extensibilityErrorRingBuffer
0x1004151ae  xor     ecx, ecx
0x1004151b0  mov     [rbp+0F0h+var_144], eax
0x1004151b3  xorps   xmm0, xmm0
0x1004151b6  lea     rax, aCsatellitecarg; "CSatelliteCargoContext::SendLogMessage"
0x1004151bd  mov     [rbp+0F0h+var_150], rcx
0x1004151c1  mov     [rbp+0F0h+var_140], rax
0x1004151c5  xor     eax, eax
0x1004151c7  movups  [rbp+0F0h+var_160], xmm0
0x1004151cb  mov     [rbp+0F0h+var_148], esi
0x1004151ce  mov     [rbp+0F0h+var_138], 78Fh
0x1004151d5  mov     [rbp+0F0h+var_58], eax
0x1004151db  mov     [rbp+0F0h+var_50], rax
0x1004151e2  cmp     [rbx+40h], rax
0x1004151e6  jz      short loc_1004151F4
0x1004151e8  lea     edx, [rcx+1]
0x1004151eb  lea     rcx, [rbp+0F0h+var_130]
0x1004151ef  call    ?CaptureCurrent@?$StackFrames@$0BI@@@QEAAXI@Z; StackFrames<24>::CaptureCurrent(uint)
0x1004151f4  test    byte ptr cs:dword_1005113AC, 10h
0x1004151fb  jz      short loc_10041520A
0x1004151fd  lea     rdx, [rbp+0F0h+var_130]
0x100415201  lea     rcx, [rbp+0F0h+var_160]
0x100415205  call    ?FireMatchingEvent@ExtensibilityErrorRecord@@QEAAXPEAV?$StackFrames@$0BI@@@@Z; ExtensibilityErrorRecord::FireMatchingEvent(StackFrames<24> *)
0x10041520a  lea     r8, [rbp+0F0h+var_130]
0x10041520e  mov     rcx, rbx
0x100415211  lea     rdx, [rbp+0F0h+var_160]
0x100415215  call    cs:__imp_?StoreRecordInternalWithoutEvent@SOS_RingBuffer@@AEAAXPEAVSOS_RingBufferRecord@@PEAV?$StackFrames@$0BI@@@@Z; SOS_RingBuffer::StoreRecordInternalWithoutEvent(SOS_RingBufferRecord *,StackFrames<24> *)
0x10041521b  xor     ebx, ebx
0x10041521d  test    esi, esi
0x10041521f  jns     short loc_10041523E
0x100415221  lfence
0x100415224  mov     r8, [rbp+0F0h+arg_0]
0x10041522b  lea     r9, aSendlogmessage; "SendLogMessage Failed."
0x100415232  mov     edx, esi
0x100415234  mov     ecx, 1
0x100415239  call    ?FireTraceEvent@@YAXW4ExtensibilityTraceLevel@@JPEBU_GUID@@PEB_WZZ; FireTraceEvent(ExtensibilityTraceLevel,long,_GUID const *,wchar_t const *,...)
0x10041523e  test    rbx, rbx
0x100415241  jz      short loc_100415265
0x100415243  mov     rdi, [rbx+0D0h]
0x10041524a  mov     rcx, rbx; struct SNI_Packet *
0x10041524d  mov     qword ptr [rbx+0D0h], 0
0x100415258  call    SNIPacketRelease
0x10041525d  mov     rbx, rdi
0x100415260  test    rdi, rdi
0x100415263  jnz     short loc_100415243
0x100415265  mov     eax, esi
0x100415267  add     rsp, 1B8h
0x10041526e  pop     r15
0x100415270  pop     r14
0x100415272  pop     r13
0x100415274  pop     r12
0x100415276  pop     rdi
0x100415277  pop     rsi
0x100415278  pop     rbx
0x100415279  pop     rbp
0x10041527a  retn
0x10041527b  mov     [rsp+1F0h+var_19C], 83760002h
0x100415283  mov     esi, 83760002h
0x100415288  jmp     short loc_100415221
0x10041528a  mov     esi, 8007000Eh
0x10041528f  jmp     short loc_100415221
0x100415291  cmp     [rbp+0F0h+arg_20], 0
0x100415298  jz      short loc_10041521D
0x10041529a  mov     eax, [r13+98h]
0x1004152a1  test    eax, eax
0x1004152a3  jle     loc_10041521D
0x1004152a9  lea     r8, [r13+0E0h]
0x1004152b0  mov     byte ptr [rsp+1F0h+var_1D0], 1
0x1004152b5  lea     rcx, [r13+160h]
0x1004152bc  xor     r9d, r9d
0x1004152bf  mov     edx, 0FFFFFFFFh
0x1004152c4  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x1004152ca  mov     ecx, eax
0x1004152cc  movzx   eax, byte ptr [r13+39h]
0x1004152d1  test    al, al
0x1004152d3  jnz     short loc_1004152DD
0x1004152d5  test    ecx, ecx
0x1004152d7  jz      loc_10041521D
0x1004152dd  mov     esi, 80004004h
  ... truncated ...
```
