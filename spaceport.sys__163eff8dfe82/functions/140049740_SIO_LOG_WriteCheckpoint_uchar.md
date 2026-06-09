# SIO_LOG::WriteCheckpoint(uchar)

- ea: `0x140049740`
- end: `0x140049b6c`
- name: `?WriteCheckpoint@SIO_LOG@@QEAAJE@Z`
- size: `1068`
- prototype: `__int64 __fastcall(SIO_LOG *__hidden this, unsigned __int8)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x140028e80`
- `0x14002f57c`
- `0x1400b1190`

## callees

- `0x140005eb0`
- `0x140007fa0`
- `0x14000a070`
- `0x14001c9a0`
- `0x1400268c0`
- `0x140048d70`
- `0x140049740`
- `0x140049b74`
- `0x140058390`
- `0x140068110`
- `0x140068150`
- `0x140068300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140049b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049b18`
- `HAL!KeQueryPerformanceCounter` at `0x1400497ae`
- `HAL!KeQueryPerformanceCounter` at `0x140049ac1`
- `HAL!KeQueryPerformanceCounter` at `0x1400497ae`
- `HAL!KeQueryPerformanceCounter` at `0x140049ac1`

## pseudocode

```c
__int64 __fastcall SIO_LOG::WriteCheckpoint(SIO_LOG *this, unsigned __int8 a2)
{
  LARGE_INTEGER PerformanceCounter; // rdi
  int LogInfo; // esi
  void *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // r9
  __int64 v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // ett
  __int64 v11; // r12
  unsigned int v12; // r8d
  unsigned int v13; // ecx
  unsigned int v14; // r13d
  char *v15; // rsi
  unsigned int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h]
  _QWORD v25[9]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+ACh] [rbp-54h]
  _BYTE v27[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+F0h] [rbp-10h]
  char v30; // [rsp+108h] [rbp+8h]
  char v31; // [rsp+10Ah] [rbp+Ah]
  SIO_LOG *v32; // [rsp+148h] [rbp+48h]
  SIO_LOG *v33; // [rsp+150h] [rbp+50h]
  __int64 v34; // [rsp+158h] [rbp+58h]
  unsigned int v35; // [rsp+168h] [rbp+68h]
  __int64 v36; // [rsp+16Ch] [rbp+6Ch]
  __int128 v37; // [rsp+180h] [rbp+80h] BYREF
  __int128 v38; // [rsp+190h] [rbp+90h]
  __int128 v39; // [rsp+1A0h] [rbp+A0h]
  __int64 v40; // [rsp+1B0h] [rbp+B0h]

  Src = 0;
  v40 = 0;
  v23 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  SIO_LOG_PACKET::SIO_LOG_PACKET((SIO_LOG_PACKET *)v25);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v22 = SL_LSN_NULL;
  if ( _InterlockedIncrement((volatile signed __int32 *)this + 64) != 1 )
    goto LABEL_2;
  if ( *((_BYTE *)this + 252) )
  {
    LogInfo = -1073741637;
    goto LABEL_18;
  }
  v5 = (void *)*((_QWORD *)this + 5);
  v26 |= 8u;
  LogInfo = SlLogGetLogInfo(v5, 0, 0, (union _SL_LSN *)&v22, 0, 0);
  if ( LogInfo < 0 )
    goto LABEL_16;
  v6 = v22;
  *(_QWORD *)&v38 = *((_QWORD *)this + 33);
  v39 = *((_OWORD *)this + 12);
  *((_QWORD *)&v38 + 1) = v22;
  LODWORD(v40) = 4096;
  Src = SC_ENV::Allocate(0x28000u, 0x58587053u, 0, 0);
  if ( !Src )
  {
    LogInfo = -1073741670;
    goto LABEL_18;
  }
  v7 = *((_QWORD *)this + 1);
  DWORD2(v23) = 0;
  *(_QWORD *)&v23 = &v37;
  LogInfo = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int128 *))(**(_QWORD **)(v7 + 392) + 96LL))(
              *(_QWORD *)(v7 + 392),
              16,
              0,
              *(_QWORD *)(v7 + 112),
              &v23);
  if ( LogInfo < 0 )
    goto LABEL_16;
  if ( !DWORD2(v23) )
  {
LABEL_2:
    LogInfo = -1073741823;
    goto LABEL_18;
  }
  v8 = *((_QWORD *)this + 2);
  LODWORD(v40) = DWORD2(v23);
  v9 = *(_DWORD *)(v8 + 132);
  v10 = v9 + 40 * DWORD2(v23) - 1;
  v11 = v10 - v10 % v9;
  v12 = *(_DWORD *)(*((_QWORD *)this + 5) + 3656LL);
  v13 = 2 * ((v10 - v10 % v9) / v12) + 200;
  v14 = -v12 & (v13 + 2 * (v13 / v12) + v12 + 1);
  LogInfo = SC_BUFFER::Initialize((__int64)v27, 3, 0, v14 + v11 + 56);
  if ( LogInfo < 0 )
    goto LABEL_16;
  v15 = (char *)(v14 + *(_QWORD *)(v28 + 32) + *(unsigned int *)(v28 + 44));
  memmove(v15, Src, 40LL * (unsigned int)v40);
  *(_OWORD *)&v15[v11] = v37;
  *(_OWORD *)&v15[v11 + 16] = v38;
  *(_OWORD *)&v15[v11 + 32] = v39;
  *(_QWORD *)&v15[v11 + 48] = v40;
  *(_DWORD *)&v15[v11] = 261;
  *(_DWORD *)&v15[v11 + 4] = v14;
  *(_DWORD *)&v15[v11 + 8] = v11;
  *(_DWORD *)&v15[v11 + 48] = v40;
  v29 = v11;
  v30 = 4;
  v31 = 14;
  v32 = this;
  v33 = this;
  v35 = v14;
  v36 = 56;
  LogInfo = SIO_LOG::WriteSynchronous(this, (struct SIO_LOG_PACKET *)v25);
  if ( LogInfo < 0 )
    goto LABEL_16;
  *((_QWORD *)this + 26) = *((_QWORD *)this + 24);
  *((_DWORD *)this + 54) = *((_DWORD *)this + 50);
  *((_DWORD *)this + 55) = *((_DWORD *)this + 51);
  v17 = v34;
  *((_DWORD *)this + 51) = v11;
  *((_QWORD *)this + 24) = v17;
  *((_QWORD *)this + 33) = v6;
  *((_DWORD *)this + 46) = 40;
  *((_DWORD *)this + 50) = v14;
  v18 = *((_QWORD *)this + 2);
  v31 = 9;
  v33 = *(SIO_LOG **)(v18 + 392);
  LogInfo = SlLogSetHostInfo(*((struct _LOG_HANDLE **)this + 5), v25, (char *)this + 184, v16, a2);
  if ( LogInfo < 0 )
    goto LABEL_16;
  v19 = *((_QWORD *)this + 10);
  _InterlockedIncrement((volatile signed __int32 *)(v19 + 36));
  _InterlockedIncrement((volatile signed __int32 *)(v19 + 28));
  _InterlockedAdd64(
    (volatile signed __int64 *)(v19 + 48),
    *(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart);
  if ( !a2 )
    goto LABEL_18;
  LogInfo = SIO_LOG::FlushSynchronous(this);
  if ( LogInfo < 0 )
  {
LABEL_16:
    if ( LogInfo == -1058602989 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1), 0);
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 64);
  }
LABEL_18:
  if ( Src )
    ExFreePoolWithTag(Src, 0);
  if ( LogInfo < 0 )
    _InterlockedDecrement((volatile signed __int32 *)this + 64);
  v25[0] = &SC_PACKET::`vftable';
  SIO_LOG_PACKET::~SIO_LOG_PACKET((SIO_LOG_PACKET *)v25);
  return (unsigned int)LogInfo;
}

```

## disassembly

```asm
0x140049740  push    rbp
0x140049742  push    rbx
0x140049743  push    rsi
0x140049744  push    rdi
0x140049745  push    r12
0x140049747  push    r13
0x140049749  push    r14
0x14004974b  push    r15
0x14004974d  lea     rbp, [rsp-0C8h]
0x140049755  sub     rsp, 1C8h
0x14004975c  mov     rax, cs:__security_cookie
0x140049763  xor     rax, rsp
0x140049766  mov     [rbp+100h+var_48], rax
0x14004976d  xor     eax, eax
0x14004976f  mov     [rsp+200h+var_1D0], dl
0x140049773  xorps   xmm1, xmm1
0x140049776  mov     [rsp+200h+Src], rax
0x14004977b  mov     r14, rcx
0x14004977e  mov     [rbp+100h+var_50], rax
0x140049785  xorps   xmm0, xmm0
0x140049788  lea     rcx, [rsp+200h+var_1A0]; this
0x14004978d  movups  [rsp+200h+var_1C0], xmm0
0x140049792  movups  [rbp+100h+var_80], xmm1
0x140049799  movups  [rbp+100h+var_70], xmm1
0x1400497a0  movups  [rbp+100h+var_60], xmm1
0x1400497a7  call    ??0SIO_LOG_PACKET@@QEAA@XZ; SIO_LOG_PACKET::SIO_LOG_PACKET(void)
0x1400497ac  xor     ecx, ecx; PerformanceFrequency
0x1400497ae  call    cs:__imp_KeQueryPerformanceCounter
0x1400497b5  nop     dword ptr [rax+rax+00h]
0x1400497ba  mov     rcx, cs:?SL_LSN_NULL@@3T_SL_LSN@@B; _SL_LSN const SL_LSN_NULL
0x1400497c1  mov     rdi, rax
0x1400497c4  mov     [rsp+200h+var_1C8], rcx
0x1400497c9  mov     eax, 1
0x1400497ce  lock xadd [r14+100h], eax
0x1400497d7  inc     eax
0x1400497d9  cmp     eax, 1
0x1400497dc  jz      short loc_1400497E8
0x1400497de  mov     esi, 0C0000001h
0x1400497e3  jmp     loc_140049B0C
0x1400497e8  cmp     byte ptr [r14+0FCh], 0
0x1400497f0  jz      short loc_1400497FC
0x1400497f2  mov     esi, 0C00000BBh
0x1400497f7  jmp     loc_140049B0C
0x1400497fc  mov     rcx, [r14+28h]; void *
0x140049800  lea     r9, [rsp+200h+var_1C8]; union _SL_LSN *
0x140049805  or      [rbp+100h+var_154], 8
0x140049809  xor     r8d, r8d; union _SL_LSN *
0x14004980c  mov     [rsp+200h+var_1D8], 0; unsigned __int64 *
0x140049815  xor     edx, edx; union _SL_LSN *
0x140049817  mov     [rsp+200h+var_1E0], 0; unsigned __int64 *
0x140049820  call    ?SlLogGetLogInfo@@YAJPEAXPEAT_SL_LSN@@11PEA_K2@Z; SlLogGetLogInfo(void *,_SL_LSN *,_SL_LSN *,_SL_LSN *,unsigned __int64 *,unsigned __int64 *)
0x140049825  mov     esi, eax
0x140049827  test    eax, eax
0x140049829  js      loc_140049AF2
0x14004982f  mov     rax, [r14+108h]
0x140049836  lea     r15, [r14+0B8h]
0x14004983d  mov     rbx, [rsp+200h+var_1C8]
0x140049842  xor     r9d, r9d; unsigned int
0x140049845  mov     qword ptr [rbp+100h+var_70], rax
0x14004984c  xor     r8d, r8d; unsigned __int8
0x14004984f  mov     rax, [r15+8]
0x140049853  mov     edx, 58587053h; unsigned int
0x140049858  mov     qword ptr [rbp+100h+var_60], rax
0x14004985f  mov     ecx, 28000h; unsigned __int64
0x140049864  mov     eax, [r14+0C8h]
0x14004986b  mov     dword ptr [rbp+100h+var_60+8], eax
0x140049871  mov     eax, [r14+0CCh]
0x140049878  mov     dword ptr [rbp+100h+var_60+0Ch], eax
0x14004987e  mov     qword ptr [rbp+100h+var_70+8], rbx
0x140049885  mov     dword ptr [rbp+100h+var_50], 1000h
0x14004988f  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x140049894  mov     [rsp+200h+Src], rax
0x140049899  test    rax, rax
0x14004989c  jnz     short loc_1400498A8
0x14004989e  mov     esi, 0C000009Ah
0x1400498a3  jmp     loc_140049B0C
0x1400498a8  mov     r9, [r14+8]
0x1400498ac  lea     rdx, [rsp+200h+var_1C0]
0x1400498b1  mov     dword ptr [rsp+200h+var_1C0+8], 0
0x1400498b9  lea     rax, [rbp+100h+var_80]
0x1400498c0  mov     qword ptr [rsp+200h+var_1C0], rax
0x1400498c5  xor     r8d, r8d
0x1400498c8  mov     [rsp+200h+var_1E0], rdx
0x1400498cd  mov     rcx, [r9+188h]
0x1400498d4  mov     r9, [r9+70h]
0x1400498d8  lea     edx, [r8+10h]
0x1400498dc  mov     rax, [rcx]
0x1400498df  mov     rax, [rax+60h]
0x1400498e3  call    _guard_dispatch_icall
0x1400498e8  mov     esi, eax
0x1400498ea  test    eax, eax
0x1400498ec  js      loc_140049AF2
0x1400498f2  mov     edx, dword ptr [rsp+200h+var_1C0+8]
0x1400498f6  test    edx, edx
0x1400498f8  jz      loc_1400497DE
0x1400498fe  mov     rax, [r14+10h]
0x140049902  mov     dword ptr [rbp+100h+var_50], edx
0x140049908  mov     ecx, [rax+84h]
0x14004990e  lea     eax, [rdx+rdx*4]
0x140049911  lea     r12d, ds:0FFFFFFFFFFFFFFFFh[rax*8]
0x140049919  xor     edx, edx
0x14004991b  add     r12d, ecx
0x14004991e  mov     eax, r12d
0x140049921  div     ecx
0x140049923  mov     rax, [r14+28h]
0x140049927  sub     r12d, edx
0x14004992a  xor     edx, edx
0x14004992c  mov     r8d, [rax+0E48h]
0x140049933  mov     eax, r12d
0x140049936  div     r8d
0x140049939  xor     edx, edx
0x14004993b  lea     r9d, [r12+38h]
0x140049940  lea     r13d, [r8+1]
0x140049944  lea     ecx, ds:0C8h[rax*2]
0x14004994b  mov     eax, ecx
0x14004994d  div     r8d
0x140049950  neg     r8d
0x140049953  lea     ecx, [rcx+rax*2]
0x140049956  add     r13d, ecx
0x140049959  lea     rcx, [rbp+100h+var_130]
0x14004995d  and     r13d, r8d
0x140049960  xor     r8d, r8d
0x140049963  add     r9d, r13d
0x140049966  lea     edx, [r8+3]
0x14004996a  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x14004996f  mov     esi, eax
0x140049971  test    eax, eax
0x140049973  js      loc_140049AF2
0x140049979  mov     rax, [rbp+100h+var_128]
0x14004997d  mov     rdx, [rsp+200h+Src]; Src
0x140049982  mov     esi, [rax+2Ch]
0x140049985  add     rsi, [rax+20h]
0x140049989  mov     eax, r13d
0x14004998c  add     rsi, rax
0x14004998f  mov     eax, dword ptr [rbp+100h+var_50]
0x140049995  mov     rcx, rsi; void *
0x140049998  lea     r8, [rax+rax*4]
0x14004999c  shl     r8, 3; Size
0x1400499a0  call    memmove
0x1400499a5  movups  xmm0, [rbp+100h+var_80]
0x1400499ac  lea     rdx, [rsp+200h+var_1A0]; struct SIO_LOG_PACKET *
0x1400499b1  mov     rcx, r14; this
0x1400499b4  movups  xmmword ptr [r12+rsi], xmm0
0x1400499b9  movups  xmm1, [rbp+100h+var_70]
0x1400499c0  movups  xmmword ptr [r12+rsi+10h], xmm1
0x1400499c6  movups  xmm0, [rbp+100h+var_60]
0x1400499cd  movups  xmmword ptr [r12+rsi+20h], xmm0
0x1400499d3  movsd   xmm1, [rbp+100h+var_50]
0x1400499db  movsd   qword ptr [r12+rsi+30h], xmm1
0x1400499e2  mov     dword ptr [r12+rsi], 105h
0x1400499ea  mov     [r12+rsi+4], r13d
0x1400499ef  mov     [r12+rsi+8], r12d
0x1400499f4  mov     eax, dword ptr [rbp+100h+var_50]
0x1400499fa  mov     [r12+rsi+30h], eax
0x1400499ff  mov     [rbp+100h+var_110], r12d
0x140049a03  mov     [rbp+100h+var_F8], 4
0x140049a07  mov     [rbp+100h+var_F6], 0Eh
0x140049a0b  mov     [rbp+100h+var_B8], r14
0x140049a0f  mov     [rbp+100h+var_B0], r14
0x140049a13  mov     [rbp+100h+var_98], r13d
0x140049a17  mov     [rbp+100h+var_94], 38h ; '8'
0x140049a1f  call    ?WriteSynchronous@SIO_LOG@@IEAAJPEAVSIO_LOG_PACKET@@@Z; SIO_LOG::WriteSynchronous(SIO_LOG_PACKET *)
0x140049a24  mov     esi, eax
0x140049a26  test    eax, eax
0x140049a28  js      loc_140049AF2
0x140049a2e  mov     rax, [r14+0C0h]
0x140049a35  lea     rdx, [rsp+200h+var_1A0]; void *
0x140049a3a  mov     [r14+0D0h], rax
0x140049a41  mov     r8, r15; void *
0x140049a44  mov     eax, [r14+0C8h]
0x140049a4b  mov     [r14+0D8h], eax
0x140049a52  mov     eax, [r14+0CCh]
0x140049a59  mov     [r14+0DCh], eax
0x140049a60  mov     rax, [rbp+100h+var_A8]
0x140049a64  mov     [r14+0CCh], r12d
0x140049a6b  mov     r12b, [rsp+200h+var_1D0]
0x140049a70  mov     [r14+0C0h], rax
0x140049a77  mov     [r14+108h], rbx
0x140049a7e  mov     dword ptr [r15], 28h ; '('
0x140049a85  mov     [r14+0C8h], r13d
0x140049a8c  mov     rax, [r14+10h]
0x140049a90  mov     [rbp+100h+var_F6], 9
0x140049a94  mov     byte ptr [rsp+200h+var_1E0], r12b; unsigned __int8
0x140049a99  mov     rcx, [rax+188h]
0x140049aa0  mov     [rbp+100h+var_B0], rcx
0x140049aa4  mov     rcx, [r14+28h]; struct _LOG_HANDLE *
0x140049aa8  call    ?SlLogSetHostInfo@@YAJPEAX00KE@Z; SlLogSetHostInfo(void *,void *,void *,ulong,uchar)
0x140049aad  mov     esi, eax
0x140049aaf  test    eax, eax
0x140049ab1  js      short loc_140049AF2
0x140049ab3  mov     rbx, [r14+50h]
0x140049ab7  lock inc dword ptr [rbx+24h]
0x140049abb  lock inc dword ptr [rbx+1Ch]
0x140049abf  xor     ecx, ecx; PerformanceFrequency
0x140049ac1  call    cs:__imp_KeQueryPerformanceCounter
0x140049ac8  nop     dword ptr [rax+rax+00h]
0x140049acd  sub     rax, rdi
0x140049ad0  lock add [rbx+30h], rax
0x140049ad5  test    r12b, r12b
0x140049ad8  jz      short loc_140049B0C
0x140049ada  mov     rcx, r14; this
0x140049add  call    ?FlushSynchronous@SIO_LOG@@QEAAJXZ; SIO_LOG::FlushSynchronous(void)
0x140049ae2  mov     esi, eax
0x140049ae4  test    eax, eax
0x140049ae6  js      short loc_140049AF2
0x140049ae8  lock dec dword ptr [r14+100h]
0x140049af0  jmp     short loc_140049B0C
0x140049af2  cmp     esi, 0C0E70013h
0x140049af8  jnz     short loc_140049B0C
0x140049afa  mov     rcx, [r14+8]
0x140049afe  xor     edx, edx
0x140049b00  mov     rax, [rcx]
0x140049b03  mov     rax, [rax+60h]
0x140049b07  call    _guard_dispatch_icall
0x140049b0c  mov     rcx, [rsp+200h+Src]; P
0x140049b11  test    rcx, rcx
0x140049b14  jz      short loc_140049B24
0x140049b16  xor     edx, edx; Tag
0x140049b18  call    cs:__imp_ExFreePoolWithTag
0x140049b1f  nop     dword ptr [rax+rax+00h]
0x140049b24  test    esi, esi
0x140049b26  jns     short loc_140049B30
0x140049b28  lock dec dword ptr [r14+100h]
0x140049b30  lea     rax, ??_7SC_PACKET@@6B@; const SC_PACKET::`vftable'
0x140049b37  lea     rcx, [rsp+200h+var_1A0]; this
0x140049b3c  mov     [rsp+200h+var_1A0], rax
0x140049b41  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x140049b46  mov     eax, esi
0x140049b48  mov     rcx, [rbp+100h+var_48]
0x140049b4f  xor     rcx, rsp; StackCookie
0x140049b52  call    __security_check_cookie
0x140049b57  add     rsp, 1C8h
0x140049b5e  pop     r15
0x140049b60  pop     r14
0x140049b62  pop     r13
0x140049b64  pop     r12
0x140049b66  pop     rdi
0x140049b67  pop     rsi
0x140049b68  pop     rbx
0x140049b69  pop     rbp
0x140049b6a  retn
```
