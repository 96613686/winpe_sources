# CTpSrvDataState::SendODATA(CAutoTypeLock<CCriticalSection> *,unsigned __int64,unsigned __int64)

- ea: `0x180012c98`
- end: `0x1800132c6`
- name: `?SendODATA@CTpSrvDataState@@AEAAKPEAV?$CAutoTypeLock@VCCriticalSection@@@@_K1@Z`
- size: `1582`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011ff0`

## callees

- `0x180012c98`
- `0x180013e34`
- `0x180013eac`
- `0x18001e73c`
- `0x18001e920`
- `0x1800227d4`
- `0x1800229c0`
- `0x1800253a8`
- `0x180025850`
- `0x1800266a0`
- `0x180026d2e`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800130fd`
- `KERNEL32!LeaveCriticalSection` at `0x180013144`
- `KERNEL32!LeaveCriticalSection` at `0x1800130fd`
- `KERNEL32!LeaveCriticalSection` at `0x180013144`
- `KERNEL32!EnterCriticalSection` at `0x18001309b`
- `KERNEL32!EnterCriticalSection` at `0x18001309b`
- `WDSSRV!WdsSendPacketList` at `0x180013179`
- `WDSSRV!WdsSendPacketList` at `0x180013179`

## string_xrefs

- `0x180012f5c`: `onecore\base\eco\wds\wdslib\common\src\bufferpool.cpp`

## pseudocode

```c
__int64 __fastcall CTpSrvDataState::SendODATA(__int64 a1, _DWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned int updated; // edi
  unsigned int v6; // r12d
  void **v7; // r14
  int v9; // r8d
  __int64 v10; // rax
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // r15
  unsigned __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  __int128 v19; // xmm0
  int v20; // r9d
  unsigned __int64 *Next; // r14
  __int64 v22; // rbx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r14
  __int64 v25; // r8
  __int64 v26; // rax
  const char *v27; // rdx
  __int64 v28; // rcx
  __int128 v29; // xmm0
  int v30; // r9d
  __int64 v31; // r15
  unsigned __int64 v32; // rcx
  const char *v33; // rdx
  __int64 v34; // rdi
  void **v35; // rax
  const char *v36; // rdx
  void **v37; // rbx
  const char *v38; // rdx
  __int64 v39; // r14
  int v40; // eax
  unsigned int v41; // eax
  struct CMemoryBuffer *v42; // rcx
  __int64 v43; // r9
  __int64 v44; // r8
  const char *v45; // rdx
  struct _RTL_CRITICAL_SECTION *v46; // rbx
  int v47; // r9d
  struct _WDSMCTP_PK_ODATA *v48; // r14
  int v49; // eax
  int v50; // eax
  __int64 v51; // rcx
  const char *v52; // rdx
  _QWORD *v53; // rax
  _QWORD *v54; // rbx
  _QWORD *v55; // rcx
  _QWORD *v56; // rdx
  __int128 v58; // [rsp+48h] [rbp-69h] BYREF
  int v59; // [rsp+5Ch] [rbp-55h]
  unsigned int v60; // [rsp+60h] [rbp-51h] BYREF
  int v61; // [rsp+64h] [rbp-4Dh] BYREF
  int v62; // [rsp+68h] [rbp-49h] BYREF
  __int128 v63; // [rsp+70h] [rbp-41h] BYREF
  __int64 v64; // [rsp+80h] [rbp-31h]
  struct _WDSMCTP_PK_ODATA *v65; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int64 v66; // [rsp+90h] [rbp-21h]
  __int64 v67; // [rsp+98h] [rbp-19h]
  char v68[24]; // [rsp+A0h] [rbp-11h] BYREF
  char v69[80]; // [rsp+B8h] [rbp+7h] BYREF
  int v70; // [rsp+118h] [rbp+67h]
  LPCRITICAL_SECTION *v71; // [rsp+120h] [rbp+6Fh]

  v71 = (LPCRITICAL_SECTION *)a2;
  updated = 0;
  v65 = 0;
  v6 = 0;
  v60 = 0;
  v7 = 0;
  v70 = 0;
  v59 = 0;
  v9 = *(_DWORD *)(a1 + 392);
  v58 = 0;
  if ( !v9 )
    goto LABEL_7;
  v10 = *(_QWORD *)(a1 + 368);
  v11 = v9 - 1;
  if ( !v10 )
    goto LABEL_7;
  do
  {
    a2 = (_DWORD *)v10;
    v12 = *(_DWORD *)(v10 + 4) - *(_DWORD *)v10 + 1;
    if ( v11 < v12 )
      break;
    v10 = *(_QWORD *)(v10 + 65544);
    v11 -= v12;
    a2 = 0;
  }
  while ( v10 );
  if ( a2 )
    v13 = *(_QWORD *)&a2[2 * v11 + 2 + 2 * *a2];
  else
LABEL_7:
    v13 = 0;
  if ( v13 )
  {
    v14 = *(_QWORD *)(a1 + 448);
    if ( a3 < v14 || a4 < a3 )
    {
      updated = 644;
LABEL_59:
      if ( v7 )
        (*((void (__fastcall **)(void **, _DWORD *))*v7 + 1))(v7, a2);
    }
    else
    {
      v15 = a1 + 360;
      v16 = a3;
      v17 = CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumStart(a1 + 360, v68, (unsigned int)(a3 - v14));
      v19 = *(_OWORD *)v17;
      v64 = *(_QWORD *)(v17 + 16);
      v63 = v19;
      if ( !HIDWORD(v64) )
      {
        do
        {
          Next = (unsigned __int64 *)CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumGetNext(v18, &v63);
          v18 = *Next;
          if ( *Next != v16 )
          {
            WdsAssert(
              "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp",
              0x4DCu,
              "pDataPacket->m_uSequenceNo == uCheck",
              v20,
              0);
            v18 = *Next;
          }
          ++v16;
          if ( v18 > a4 )
            break;
          ++v6;
        }
        while ( !HIDWORD(v64) );
        v15 = a1 + 360;
      }
      v22 = v6;
      if ( v6 <= (*(_DWORD *)(a1 + 472) >> 1) + 1 )
        v23 = v6;
      else
        v23 = (unsigned __int64)*(unsigned int *)(a1 + 472) >> 1;
      v24 = *(_QWORD *)(a1 + 456) + v23;
      v25 = (unsigned int)(a3 - *(_DWORD *)(a1 + 448));
      v66 = v24;
      v26 = CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumStart(v15, v69, v25);
      v29 = *(_OWORD *)v26;
      v64 = *(_QWORD *)(v26 + 16);
      v63 = v29;
      if ( !HIDWORD(v64) )
      {
        while ( 1 )
        {
          v62 = 0;
          v31 = CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumGetNext(v28, &v63);
          v32 = *(_QWORD *)v31;
          if ( *(_QWORD *)v31 != a3 )
          {
            WdsAssert(
              "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp",
              0x507u,
              "pDataPacket->m_uSequenceNo == uCheck",
              v30,
              0);
            v32 = *(_QWORD *)v31;
          }
          ++a3;
          if ( v32 > a4 )
            break;
          if ( v32 > v24 )
          {
            v24 = v22 + *(_QWORD *)(a1 + 456);
            v66 = v24;
          }
          updated = CMcTpConstructor::UpdateODATA(
                      *(CMcTpConstructor **)(a1 + 32),
                      *(struct CMemoryBuffer **)(v31 + 32),
                      _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 2240LL), 0),
                      *(_QWORD *)(a1 + 448),
                      v24,
                      &v62);
          v7 = 0;
          if ( ElValidateWin32(updated, v33, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x520u) )
            goto LABEL_61;
          v34 = *(_QWORD *)(v31 + 32);
          v67 = v34;
          *(_QWORD *)(v31 + 16) = 0;
          v35 = (void **)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
          v37 = v35;
          if ( v35 )
          {
            *((_DWORD *)v35 + 2) = 1;
            *v35 = &CMemoryBuffer::`vftable';
            v35[7] = 0;
            v35[8] = 0;
            v35[3] = 0;
            v35[5] = 0;
            *((_DWORD *)v35 + 12) = 0;
            *((_DWORD *)v35 + 4) = 0;
            v35[4] = 0;
          }
          else
          {
            v37 = 0;
          }
          if ( v37 )
          {
            updated = CMemoryBuffer::Initialize((CMemoryBuffer *)v37, *(_DWORD *)(v34 + 16));
            if ( !ElValidateWin32(updated, v38, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferpool.cpp", 0xAFu) )
            {
              v39 = v67;
              memcpy_0(v37[5], *(const void **)(v67 + 40), *(unsigned int *)(v67 + 16));
              v40 = *(_DWORD *)(v39 + 48);
              v7 = v37;
              *((_DWORD *)v37 + 12) = v40;
              v37 = 0;
            }
            if ( v37 )
              (*((void (__fastcall **)(void **, __int64))*v37 + 2))(v37, 1);
          }
          else
          {
            updated = 8;
          }
          v41 = ElValidateWin32(updated, v36, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x52Fu);
          a2 = 0;
          if ( v41 )
            goto LABEL_59;
          if ( (_QWORD)v58 )
          {
            v7[7] = 0;
            v7[8] = (void *)*((_QWORD *)&v58 + 1);
            *(_QWORD *)(*((_QWORD *)&v58 + 1) + 56LL) = v7;
            *((_QWORD *)&v58 + 1) = v7;
          }
          else
          {
            *((_QWORD *)&v58 + 1) = v7;
            *(_QWORD *)&v58 = v7;
            v7[7] = 0;
            v7[8] = 0;
          }
          ++v59;
          v42 = *(struct CMemoryBuffer **)(v31 + 32);
          v70 += *((_DWORD *)v42 + 12);
          if ( g_ErrLibTraceFunctionEx )
          {
            v43 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 2240LL), 0);
            v44 = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 2216LL), 0);
            g_ErrLibTraceFunctionEx(
              0x400000u,
              L"WDSMCTP[0x%x] ODATA - Client=0x%x, Seq#=%I64u, Trail#=%I64u",
              v44,
              v43,
              *(_QWORD *)v31,
              *(_QWORD *)(a1 + 448));
            v42 = *(struct CMemoryBuffer **)(v31 + 32);
          }
          updated = CMcTpConstructor::GetPacketPtr(v42, &v65, &v60);
          if ( ElValidateWin32(updated, v45, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x544u) )
            goto LABEL_61;
          v46 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 192);
          v61 = 0;
          EnterCriticalSection(v46);
          v48 = v65;
          if ( *((_BYTE *)v65 + 4) != 6 )
            WdsAssert(
              "base\\eco\\wds\\transport\\server\\mc\\tpsrvtxrate.cpp",
              0xEAu,
              "pPacket->bOpCode == WDSMCTP_OP_ODATA",
              v47,
              0);
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**(_QWORD **)(*(_QWORD *)(a1 + 200) + 40LL) + 56LL))(
            *(_QWORD *)(*(_QWORD *)(a1 + 200) + 40LL),
            (__int64)v48 + 35,
            v60 - 35,
            &v61);
          *(_DWORD *)(a1 + 216) += v61;
          LeaveCriticalSection(v46);
          v24 = v66;
          v22 = v6;
          if ( HIDWORD(v64) )
          {
            v22 = v6;
            break;
          }
        }
      }
      *(_QWORD *)(a1 + 456) += v22;
      *(_DWORD *)(a1 + 484) += v6;
      if ( !v6 )
        goto LABEL_57;
      v49 = *((_DWORD *)v71 + 2);
      if ( v49 )
      {
        v50 = v49 - 1;
        *((_DWORD *)v71 + 2) = v50;
        if ( !v50 )
          LeaveCriticalSection(*v71);
      }
      v51 = *(_QWORD *)(a1 + 16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v51 + 2256), 0) )
      {
        updated = 5023;
      }
      else
      {
        updated = WdsSendPacketList(*(_QWORD *)(v51 + 2208), v51 + 48, v51 + 1156, &v58);
        if ( !ElValidateWin32(updated, v52, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x282u) )
          CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 4);
      }
      if ( !ElValidateWin32(updated, v27, "base\\eco\\wds\\transport\\server\\mc\\tpsrvdatastate.cpp", 0x55Bu) )
LABEL_57:
        CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 7);
    }
LABEL_61:
    v53 = (_QWORD *)v58;
    if ( (_QWORD)v58 )
    {
      v54 = (_QWORD *)v58;
      do
      {
        v55 = v54;
        if ( v53 == *((_QWORD **)&v58 + 1) )
        {
          v58 = 0u;
          v54 = 0;
        }
        else if ( v54 == v53 )
        {
          *(_QWORD *)&v58 = v53[7];
          *(_QWORD *)(v58 + 64) = 0;
          v54 = (_QWORD *)v58;
        }
        else if ( v54 == *((_QWORD **)&v58 + 1) )
        {
          *((_QWORD *)&v58 + 1) = *(_QWORD *)(*((_QWORD *)&v58 + 1) + 64LL);
          *(_QWORD *)(*((_QWORD *)&v58 + 1) + 56LL) = 0;
          v54 = 0;
        }
        else
        {
          v56 = v54 + 7;
          v54 = (_QWORD *)v54[7];
          *(_QWORD *)(v55[8] + 56LL) = v54;
          *(_QWORD *)(*v56 + 64LL) = v55[8];
        }
        --v59;
        (*(void (__fastcall **)(_QWORD *))(*v55 + 8LL))(v55);
        v53 = (_QWORD *)v58;
      }
      while ( v54 );
    }
  }
  else
  {
    return 644;
  }
  return updated;
}

```

## disassembly

```asm
0x180012c98  mov     rax, rsp
0x180012c9b  mov     [rax+18h], rbx
0x180012c9f  mov     [rax+20h], r9
0x180012ca3  mov     [rax+10h], rdx
0x180012ca7  push    rbp
0x180012ca8  push    rsi
0x180012ca9  push    rdi
0x180012caa  push    r12
0x180012cac  push    r13
0x180012cae  push    r14
0x180012cb0  push    r15
0x180012cb2  lea     rbp, [rax-5Fh]
0x180012cb6  sub     rsp, 0D0h
0x180012cbd  xor     edi, edi
0x180012cbf  mov     r13, r8
0x180012cc2  and     [rbp+57h+var_80], rdi
0x180012cc6  xor     r12d, r12d
0x180012cc9  and     [rbp+57h+var_A8], edi
0x180012ccc  xor     r14d, r14d
0x180012ccf  and     [rbp+57h+arg_0], edi
0x180012cd2  xorps   xmm0, xmm0
0x180012cd5  and     [rbp+57h+var_AC], edi
0x180012cd8  mov     rsi, rcx
0x180012cdb  mov     r8d, [rcx+188h]
0x180012ce2  movdqu  [rbp+57h+var_C0], xmm0
0x180012ce7  test    r8d, r8d
0x180012cea  jz      short loc_180012D2C
0x180012cec  mov     rax, [rcx+170h]
0x180012cf3  dec     r8d
0x180012cf6  test    rax, rax
0x180012cf9  jz      short loc_180012D2C
0x180012cfb  mov     ecx, [rax+4]
0x180012cfe  mov     rdx, rax
0x180012d01  sub     ecx, [rax]
0x180012d03  inc     ecx
0x180012d05  cmp     r8d, ecx
0x180012d08  jb      short loc_180012D1B
0x180012d0a  mov     rax, [rax+10008h]
0x180012d11  sub     r8d, ecx
0x180012d14  xor     edx, edx
0x180012d16  test    rax, rax
0x180012d19  jnz     short loc_180012CFB
0x180012d1b  test    rdx, rdx
0x180012d1e  jz      short loc_180012D2C
0x180012d20  mov     ecx, [rdx]
0x180012d22  add     ecx, r8d
0x180012d25  mov     rcx, [rdx+rcx*8+8]
0x180012d2a  jmp     short loc_180012D2E
0x180012d2c  xor     ecx, ecx
0x180012d2e  test    rcx, rcx
0x180012d31  jnz     short loc_180012D3D
0x180012d33  mov     edi, 284h
0x180012d38  jmp     loc_1800132A9
0x180012d3d  mov     rax, [rsi+1C0h]
0x180012d44  cmp     r13, rax
0x180012d47  jb      loc_1800131ED
0x180012d4d  cmp     r9, r13
0x180012d50  jb      loc_1800131ED
0x180012d56  mov     r8d, r13d
0x180012d59  lea     r15, [rsi+168h]
0x180012d60  sub     r8d, eax
0x180012d63  lea     rdx, [rbp+57h+var_68]
0x180012d67  mov     rcx, r15
0x180012d6a  mov     rbx, r13
0x180012d6d  call    ?EnumStart@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@QEAA?AUDYNLISTPOS@@K@Z; CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumStart(ulong)
0x180012d72  movsd   xmm1, qword ptr [rax+10h]
0x180012d77  movups  xmm0, xmmword ptr [rax]
0x180012d7a  movsd   [rbp+57h+var_88], xmm1
0x180012d7f  mov     rax, [rbp+57h+var_88]
0x180012d83  shr     rax, 20h
0x180012d87  movups  [rbp+57h+var_98], xmm0
0x180012d8b  test    eax, eax
0x180012d8d  jnz     short loc_180012DDD
0x180012d8f  mov     r15, [rbp+57h+arg_18]
0x180012d93  lea     rdx, [rbp+57h+var_98]
0x180012d97  call    ?EnumGetNext@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@QEAAPEAUDataPacket@CTpSrvDataState@@AEAUDYNLISTPOS@@PEAK@Z; CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumGetNext(DYNLISTPOS &,ulong *)
0x180012d9c  mov     r14, rax
0x180012d9f  mov     rcx, [rax]
0x180012da2  cmp     rcx, rbx
0x180012da5  jz      short loc_180012DC6
0x180012da7  and     dword ptr [rsp+100h+var_E0], edi
0x180012dab  lea     r8, aPdatapacketMUs; "pDataPacket->m_uSequenceNo == uCheck"
0x180012db2  mov     edx, 4DCh; unsigned int
0x180012db7  lea     rcx, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180012dbe  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180012dc3  mov     rcx, [r14]
0x180012dc6  inc     rbx
0x180012dc9  cmp     rcx, r15
0x180012dcc  ja      short loc_180012DD6
0x180012dce  inc     r12d
0x180012dd1  cmp     dword ptr [rbp+57h+var_88+4], edi
0x180012dd4  jz      short loc_180012D93
0x180012dd6  lea     r15, [rsi+168h]
0x180012ddd  mov     ecx, [rsi+1D8h]
0x180012de3  mov     rdx, [rsi+1C8h]
0x180012dea  mov     eax, ecx
0x180012dec  shr     eax, 1
0x180012dee  inc     eax
0x180012df0  mov     ebx, r12d
0x180012df3  cmp     r12d, eax
0x180012df6  jbe     short loc_180012DFF
0x180012df8  mov     eax, ecx
0x180012dfa  shr     rax, 1
0x180012dfd  jmp     short loc_180012E02
0x180012dff  mov     rax, rbx
0x180012e02  lea     r14, [rdx+rax]
0x180012e06  mov     r8d, r13d
0x180012e09  sub     r8d, [rsi+1C0h]
0x180012e10  lea     rdx, [rbp+57h+var_50]
0x180012e14  mov     rcx, r15
0x180012e17  mov     [rbp+57h+var_78], r14
0x180012e1b  call    ?EnumStart@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@QEAA?AUDYNLISTPOS@@K@Z; CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumStart(ulong)
0x180012e20  movsd   xmm1, qword ptr [rax+10h]
0x180012e25  movups  xmm0, xmmword ptr [rax]
0x180012e28  movsd   [rbp+57h+var_88], xmm1
0x180012e2d  mov     rax, [rbp+57h+var_88]
0x180012e31  shr     rax, 20h
0x180012e35  movups  [rbp+57h+var_98], xmm0
0x180012e39  test    eax, eax
0x180012e3b  jnz     loc_180013117
0x180012e41  and     [rbp+57h+var_A0], 0
0x180012e45  lea     rdx, [rbp+57h+var_98]
0x180012e49  call    ?EnumGetNext@?$CDynList@UDataPacket@CTpSrvDataState@@VCNoLock@@@@QEAAPEAUDataPacket@CTpSrvDataState@@AEAUDYNLISTPOS@@PEAK@Z; CDynList<CTpSrvDataState::DataPacket,CNoLock>::EnumGetNext(DYNLISTPOS &,ulong *)
0x180012e4e  mov     r15, rax
0x180012e51  mov     rcx, [rax]
0x180012e54  cmp     rcx, r13
0x180012e57  jz      short loc_180012E79
0x180012e59  and     dword ptr [rsp+100h+var_E0], 0
0x180012e5e  lea     r8, aPdatapacketMUs; "pDataPacket->m_uSequenceNo == uCheck"
0x180012e65  mov     edx, 507h; unsigned int
0x180012e6a  lea     rcx, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180012e71  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180012e76  mov     rcx, [r15]
0x180012e79  inc     r13
0x180012e7c  cmp     rcx, [rbp+57h+arg_18]
0x180012e80  ja      loc_180013117
0x180012e86  cmp     rcx, r14
0x180012e89  jbe     short loc_180012E99
0x180012e8b  mov     r14, [rsi+1C8h]
0x180012e92  add     r14, rbx
0x180012e95  mov     [rbp+57h+var_78], r14
0x180012e99  mov     rax, [rsi+10h]
0x180012e9d  xor     r8d, r8d
0x180012ea0  lock xadd [rax+8C0h], r8d; hostlong
0x180012ea9  mov     r9, [rsi+1C0h]; unsigned __int64
0x180012eb0  lea     rax, [rbp+57h+var_A0]
0x180012eb4  mov     rdx, [r15+20h]; struct CMemoryBuffer *
0x180012eb8  mov     rcx, [rsi+20h]; this
0x180012ebc  mov     [rsp+28h], rax; int *
0x180012ec1  mov     [rsp+100h+var_E0], r14; unsigned __int64
0x180012ec6  call    ?UpdateODATA@CMcTpConstructor@@QEAAKPEAVCMemoryBuffer@@K_K1PEAH@Z; CMcTpConstructor::UpdateODATA(CMemoryBuffer *,ulong,unsigned __int64,unsigned __int64,int *)
0x180012ecb  mov     r9d, 520h; unsigned int
0x180012ed1  lea     r8, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180012ed8  mov     ecx, eax; unsigned int
0x180012eda  mov     edi, eax
0x180012edc  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012ee1  xor     r14d, r14d
0x180012ee4  test    eax, eax
0x180012ee6  jnz     loc_180013207
0x180012eec  mov     rdi, [r15+20h]
0x180012ef0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012ef7  lea     ecx, [rax+48h]; unsigned __int64
0x180012efa  mov     [rbp+57h+var_70], rdi
0x180012efe  mov     [r15+10h], r14
0x180012f02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012f07  mov     rbx, rax
0x180012f0a  test    rax, rax
0x180012f0d  jz      short loc_180012F3E
0x180012f0f  mov     dword ptr [rax+8], 1
0x180012f16  lea     rax, ??_7CMemoryBuffer@@6B@; const CMemoryBuffer::`vftable'
0x180012f1d  mov     [rbx], rax
0x180012f20  mov     [rbx+38h], r14
0x180012f24  mov     [rbx+40h], r14
0x180012f28  mov     [rbx+18h], r14
0x180012f2c  mov     [rbx+28h], r14
0x180012f30  mov     [rbx+30h], r14d
0x180012f34  mov     [rbx+10h], r14d
0x180012f38  mov     [rbx+20h], r14
0x180012f3c  jmp     short loc_180012F41
0x180012f3e  mov     rbx, r14
0x180012f41  test    rbx, rbx
0x180012f44  jnz     short loc_180012F4B
0x180012f46  lea     edi, [rbx+8]
0x180012f49  jmp     short loc_180012FAB
0x180012f4b  mov     edx, [rdi+10h]; unsigned int
0x180012f4e  mov     rcx, rbx; this
0x180012f51  call    ?Initialize@CMemoryBuffer@@QEAAKK@Z; CMemoryBuffer::Initialize(ulong)
0x180012f56  mov     r9d, 0AFh; unsigned int
0x180012f5c  lea     r8, aOnecoreBaseEco_0; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180012f63  mov     ecx, eax; unsigned int
0x180012f65  mov     edi, eax
0x180012f67  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012f6c  test    eax, eax
0x180012f6e  jnz     short loc_180012F91
0x180012f70  mov     r14, [rbp+57h+var_70]
0x180012f74  mov     rcx, [rbx+28h]; void *
0x180012f78  mov     r8d, [r14+10h]; Size
0x180012f7c  mov     rdx, [r14+28h]; Src
0x180012f80  call    memcpy_0
0x180012f85  mov     eax, [r14+30h]
0x180012f89  mov     r14, rbx
0x180012f8c  mov     [rbx+30h], eax
0x180012f8f  xor     ebx, ebx
0x180012f91  test    rbx, rbx
0x180012f94  jz      short loc_180012FAB
0x180012f96  mov     rax, [rbx]
0x180012f99  mov     edx, 1
0x180012f9e  mov     rcx, rbx
0x180012fa1  mov     rax, [rax+10h]
0x180012fa5  call    cs:__guard_dispatch_icall_fptr
0x180012fab  mov     r9d, 52Fh; unsigned int
0x180012fb1  lea     r8, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180012fb8  mov     ecx, edi; unsigned int
0x180012fba  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012fbf  xor     edx, edx
0x180012fc1  test    eax, eax
0x180012fc3  jnz     loc_1800131F2
0x180012fc9  cmp     qword ptr [rbp+57h+var_C0], rdx
0x180012fcd  jnz     short loc_180012FE1
0x180012fcf  mov     qword ptr [rbp+57h+var_C0+8], r14
0x180012fd3  mov     qword ptr [rbp+57h+var_C0], r14
0x180012fd7  mov     [r14+38h], rdx
0x180012fdb  mov     [r14+40h], rdx
0x180012fdf  jmp     short loc_180012FF9
0x180012fe1  mov     [r14+38h], rdx
0x180012fe5  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x180012fe9  mov     [r14+40h], rax
0x180012fed  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x180012ff1  mov     [rax+38h], r14
0x180012ff5  mov     qword ptr [rbp+57h+var_C0+8], r14
0x180012ff9  inc     [rbp+57h+var_AC]
0x180012ffc  mov     eax, [rbp+57h+arg_0]
0x180012fff  mov     rcx, [r15+20h]
0x180013003  add     eax, [rcx+30h]
0x180013006  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, rdx; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001300d  mov     [rbp+57h+arg_0], eax
0x180013010  jz      short loc_180013063
0x180013012  mov     rax, [rsi+10h]
0x180013016  mov     r9d, edx
0x180013019  lock xadd [rax+8C0h], r9d
0x180013022  mov     rax, [rsi+10h]
0x180013026  mov     r8d, edx
0x180013029  lock xadd [rax+8A8h], r8d
0x180013032  mov     rcx, [rsi+1C0h]
0x180013039  lea     rdx, aWdsmctp0xXOdat; "WDSMCTP[0x%x] ODATA - Client=0x%x, Seq#"...
0x180013040  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180013047  mov     [rsp+28h], rcx
0x18001304c  mov     rcx, [r15]
0x18001304f  mov     [rsp+100h+var_E0], rcx; int
0x180013054  mov     ecx, 400000h
0x180013059  call    cs:__guard_dispatch_icall_fptr
0x18001305f  mov     rcx, [r15+20h]; struct CMemoryBuffer *
0x180013063  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x180013067  lea     rdx, [rbp+57h+var_80]; struct _WDSMCTP_PK_ODATA **
0x18001306b  call    ?GetPacketPtr@CMcTpConstructor@@SAKPEAVCMemoryBuffer@@PEAPEAU_WDSMCTP_PK_ODATA@@PEAK@Z; CMcTpConstructor::GetPacketPtr(CMemoryBuffer *,_WDSMCTP_PK_ODATA * *,ulong *)
0x180013070  mov     r9d, 544h; unsigned int
0x180013076  lea     r8, aBaseEcoWdsTran_21; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18001307d  mov     ecx, eax; unsigned int
0x18001307f  mov     edi, eax
0x180013081  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180013086  test    eax, eax
0x180013088  jnz     loc_180013207
0x18001308e  mov     rbx, [rsi+0C0h]
0x180013095  and     [rbp+57h+var_A4], eax
0x180013098  mov     rcx, rbx; lpCriticalSection
0x18001309b  call    cs:__imp_EnterCriticalSection
0x1800130a1  mov     r14, [rbp+57h+var_80]
0x1800130a5  cmp     byte ptr [r14+4], 6
0x1800130aa  jz      short loc_1800130C9
0x1800130ac  and     dword ptr [rsp+100h+var_E0], 0
0x1800130b1  lea     r8, aPpacketBopcode; "pPacket->bOpCode == WDSMCTP_OP_ODATA"
0x1800130b8  mov     edx, 0EAh; unsigned int
0x1800130bd  lea     rcx, aBaseEcoWdsTran; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800130c4  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800130c9  mov     rax, [rsi+0C8h]
0x1800130d0  lea     rdx, [r14+23h]
0x1800130d4  mov     r8d, [rbp+57h+var_A8]
0x1800130d8  lea     r9, [rbp+57h+var_A4]
0x1800130dc  add     r8d, 0FFFFFFDDh
0x1800130e0  mov     rcx, [rax+28h]
0x1800130e4  mov     rax, [rcx]
0x1800130e7  mov     rax, [rax+38h]
0x1800130eb  call    cs:__guard_dispatch_icall_fptr
0x1800130f1  mov     eax, [rbp+57h+var_A4]
0x1800130f4  mov     rcx, rbx; lpCriticalSection
0x1800130f7  add     [rsi+0D8h], eax
0x1800130fd  call    cs:__imp_LeaveCriticalSection
0x180013103  cmp     dword ptr [rbp+57h+var_88+4], 0
0x180013107  mov     r14, [rbp+57h+var_78]
0x18001310b  mov     ebx, r12d
0x18001310e  jz      loc_180012E41
0x180013114  mov     ebx, r12d
0x180013117  add     [rsi+1C8h], rbx
0x18001311e  add     [rsi+1E4h], r12d
0x180013125  test    r12d, r12d
0x180013128  jz      loc_1800131CF
0x18001312e  mov     rcx, [rbp+57h+arg_8]
0x180013132  mov     eax, [rcx+8]
0x180013135  test    eax, eax
0x180013137  jz      short loc_18001314A
  ... truncated ...
```
