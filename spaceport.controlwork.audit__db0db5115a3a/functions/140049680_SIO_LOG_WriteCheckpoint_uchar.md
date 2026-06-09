# SIO_LOG::WriteCheckpoint(uchar)

- ea: `0x140049680`
- end: `0x140049aac`
- name: `?WriteCheckpoint@SIO_LOG@@QEAAJE@Z`
- size: `1068`
- prototype: `__int64 __fastcall(SIO_LOG *__hidden this, unsigned __int8)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x140028e80`
- `0x14002f50c`
- `0x1400b0ff0`

## callees

- `0x140005eb0`
- `0x140007fa0`
- `0x14000a070`
- `0x14001c9a0`
- `0x1400268c0`
- `0x140048cb0`
- `0x140049680`
- `0x140049ab4`
- `0x140058290`
- `0x140067fc0`
- `0x140068000`
- `0x1400681c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140049a58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a58`
- `HAL!KeQueryPerformanceCounter` at `0x1400496ee`
- `HAL!KeQueryPerformanceCounter` at `0x140049a01`
- `HAL!KeQueryPerformanceCounter` at `0x1400496ee`
- `HAL!KeQueryPerformanceCounter` at `0x140049a01`

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
0x140049680  push    rbp
0x140049682  push    rbx
0x140049683  push    rsi
0x140049684  push    rdi
0x140049685  push    r12
0x140049687  push    r13
0x140049689  push    r14
0x14004968b  push    r15
0x14004968d  lea     rbp, [rsp-0C8h]
0x140049695  sub     rsp, 1C8h
0x14004969c  mov     rax, cs:__security_cookie
0x1400496a3  xor     rax, rsp
0x1400496a6  mov     [rbp+100h+var_48], rax
0x1400496ad  xor     eax, eax
0x1400496af  mov     [rsp+200h+var_1D0], dl
0x1400496b3  xorps   xmm1, xmm1
0x1400496b6  mov     [rsp+200h+Src], rax
0x1400496bb  mov     r14, rcx
0x1400496be  mov     [rbp+100h+var_50], rax
0x1400496c5  xorps   xmm0, xmm0
0x1400496c8  lea     rcx, [rsp+200h+var_1A0]; this
0x1400496cd  movups  [rsp+200h+var_1C0], xmm0
0x1400496d2  movups  [rbp+100h+var_80], xmm1
0x1400496d9  movups  [rbp+100h+var_70], xmm1
0x1400496e0  movups  [rbp+100h+var_60], xmm1
0x1400496e7  call    ??0SIO_LOG_PACKET@@QEAA@XZ; SIO_LOG_PACKET::SIO_LOG_PACKET(void)
0x1400496ec  xor     ecx, ecx; PerformanceFrequency
0x1400496ee  call    cs:__imp_KeQueryPerformanceCounter
0x1400496f5  nop     dword ptr [rax+rax+00h]
0x1400496fa  mov     rcx, cs:?SL_LSN_NULL@@3T_SL_LSN@@B; _SL_LSN const SL_LSN_NULL
0x140049701  mov     rdi, rax
0x140049704  mov     [rsp+200h+var_1C8], rcx
0x140049709  mov     eax, 1
0x14004970e  lock xadd [r14+100h], eax
0x140049717  inc     eax
0x140049719  cmp     eax, 1
0x14004971c  jz      short loc_140049728
0x14004971e  mov     esi, 0C0000001h
0x140049723  jmp     loc_140049A4C
0x140049728  cmp     byte ptr [r14+0FCh], 0
0x140049730  jz      short loc_14004973C
0x140049732  mov     esi, 0C00000BBh
0x140049737  jmp     loc_140049A4C
0x14004973c  mov     rcx, [r14+28h]; void *
0x140049740  lea     r9, [rsp+200h+var_1C8]; union _SL_LSN *
0x140049745  or      [rbp+100h+var_154], 8
0x140049749  xor     r8d, r8d; union _SL_LSN *
0x14004974c  mov     [rsp+200h+var_1D8], 0; unsigned __int64 *
0x140049755  xor     edx, edx; union _SL_LSN *
0x140049757  mov     [rsp+200h+var_1E0], 0; unsigned __int64 *
0x140049760  call    ?SlLogGetLogInfo@@YAJPEAXPEAT_SL_LSN@@11PEA_K2@Z; SlLogGetLogInfo(void *,_SL_LSN *,_SL_LSN *,_SL_LSN *,unsigned __int64 *,unsigned __int64 *)
0x140049765  mov     esi, eax
0x140049767  test    eax, eax
0x140049769  js      loc_140049A32
0x14004976f  mov     rax, [r14+108h]
0x140049776  lea     r15, [r14+0B8h]
0x14004977d  mov     rbx, [rsp+200h+var_1C8]
0x140049782  xor     r9d, r9d; unsigned int
0x140049785  mov     qword ptr [rbp+100h+var_70], rax
0x14004978c  xor     r8d, r8d; unsigned __int8
0x14004978f  mov     rax, [r15+8]
0x140049793  mov     edx, 58587053h; unsigned int
0x140049798  mov     qword ptr [rbp+100h+var_60], rax
0x14004979f  mov     ecx, 28000h; unsigned __int64
0x1400497a4  mov     eax, [r14+0C8h]
0x1400497ab  mov     dword ptr [rbp+100h+var_60+8], eax
0x1400497b1  mov     eax, [r14+0CCh]
0x1400497b8  mov     dword ptr [rbp+100h+var_60+0Ch], eax
0x1400497be  mov     qword ptr [rbp+100h+var_70+8], rbx
0x1400497c5  mov     dword ptr [rbp+100h+var_50], 1000h
0x1400497cf  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400497d4  mov     [rsp+200h+Src], rax
0x1400497d9  test    rax, rax
0x1400497dc  jnz     short loc_1400497E8
0x1400497de  mov     esi, 0C000009Ah
0x1400497e3  jmp     loc_140049A4C
0x1400497e8  mov     r9, [r14+8]
0x1400497ec  lea     rdx, [rsp+200h+var_1C0]
0x1400497f1  mov     dword ptr [rsp+200h+var_1C0+8], 0
0x1400497f9  lea     rax, [rbp+100h+var_80]
0x140049800  mov     qword ptr [rsp+200h+var_1C0], rax
0x140049805  xor     r8d, r8d
0x140049808  mov     [rsp+200h+var_1E0], rdx
0x14004980d  mov     rcx, [r9+188h]
0x140049814  mov     r9, [r9+70h]
0x140049818  lea     edx, [r8+10h]
0x14004981c  mov     rax, [rcx]
0x14004981f  mov     rax, [rax+60h]
0x140049823  call    _guard_dispatch_icall
0x140049828  mov     esi, eax
0x14004982a  test    eax, eax
0x14004982c  js      loc_140049A32
0x140049832  mov     edx, dword ptr [rsp+200h+var_1C0+8]
0x140049836  test    edx, edx
0x140049838  jz      loc_14004971E
0x14004983e  mov     rax, [r14+10h]
0x140049842  mov     dword ptr [rbp+100h+var_50], edx
0x140049848  mov     ecx, [rax+84h]
0x14004984e  lea     eax, [rdx+rdx*4]
0x140049851  lea     r12d, ds:0FFFFFFFFFFFFFFFFh[rax*8]
0x140049859  xor     edx, edx
0x14004985b  add     r12d, ecx
0x14004985e  mov     eax, r12d
0x140049861  div     ecx
0x140049863  mov     rax, [r14+28h]
0x140049867  sub     r12d, edx
0x14004986a  xor     edx, edx
0x14004986c  mov     r8d, [rax+0E48h]
0x140049873  mov     eax, r12d
0x140049876  div     r8d
0x140049879  xor     edx, edx
0x14004987b  lea     r9d, [r12+38h]
0x140049880  lea     r13d, [r8+1]
0x140049884  lea     ecx, ds:0C8h[rax*2]
0x14004988b  mov     eax, ecx
0x14004988d  div     r8d
0x140049890  neg     r8d
0x140049893  lea     ecx, [rcx+rax*2]
0x140049896  add     r13d, ecx
0x140049899  lea     rcx, [rbp+100h+var_130]
0x14004989d  and     r13d, r8d
0x1400498a0  xor     r8d, r8d
0x1400498a3  add     r9d, r13d
0x1400498a6  lea     edx, [r8+3]
0x1400498aa  call    ?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z; SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)
0x1400498af  mov     esi, eax
0x1400498b1  test    eax, eax
0x1400498b3  js      loc_140049A32
0x1400498b9  mov     rax, [rbp+100h+var_128]
0x1400498bd  mov     rdx, [rsp+200h+Src]; Src
0x1400498c2  mov     esi, [rax+2Ch]
0x1400498c5  add     rsi, [rax+20h]
0x1400498c9  mov     eax, r13d
0x1400498cc  add     rsi, rax
0x1400498cf  mov     eax, dword ptr [rbp+100h+var_50]
0x1400498d5  mov     rcx, rsi; void *
0x1400498d8  lea     r8, [rax+rax*4]
0x1400498dc  shl     r8, 3; Size
0x1400498e0  call    memmove
0x1400498e5  movups  xmm0, [rbp+100h+var_80]
0x1400498ec  lea     rdx, [rsp+200h+var_1A0]; struct SIO_LOG_PACKET *
0x1400498f1  mov     rcx, r14; this
0x1400498f4  movups  xmmword ptr [r12+rsi], xmm0
0x1400498f9  movups  xmm1, [rbp+100h+var_70]
0x140049900  movups  xmmword ptr [r12+rsi+10h], xmm1
0x140049906  movups  xmm0, [rbp+100h+var_60]
0x14004990d  movups  xmmword ptr [r12+rsi+20h], xmm0
0x140049913  movsd   xmm1, [rbp+100h+var_50]
0x14004991b  movsd   qword ptr [r12+rsi+30h], xmm1
0x140049922  mov     dword ptr [r12+rsi], 105h
0x14004992a  mov     [r12+rsi+4], r13d
0x14004992f  mov     [r12+rsi+8], r12d
0x140049934  mov     eax, dword ptr [rbp+100h+var_50]
0x14004993a  mov     [r12+rsi+30h], eax
0x14004993f  mov     [rbp+100h+var_110], r12d
0x140049943  mov     [rbp+100h+var_F8], 4
0x140049947  mov     [rbp+100h+var_F6], 0Eh
0x14004994b  mov     [rbp+100h+var_B8], r14
0x14004994f  mov     [rbp+100h+var_B0], r14
0x140049953  mov     [rbp+100h+var_98], r13d
0x140049957  mov     [rbp+100h+var_94], 38h ; '8'
0x14004995f  call    ?WriteSynchronous@SIO_LOG@@IEAAJPEAVSIO_LOG_PACKET@@@Z; SIO_LOG::WriteSynchronous(SIO_LOG_PACKET *)
0x140049964  mov     esi, eax
0x140049966  test    eax, eax
0x140049968  js      loc_140049A32
0x14004996e  mov     rax, [r14+0C0h]
0x140049975  lea     rdx, [rsp+200h+var_1A0]; void *
0x14004997a  mov     [r14+0D0h], rax
0x140049981  mov     r8, r15; void *
0x140049984  mov     eax, [r14+0C8h]
0x14004998b  mov     [r14+0D8h], eax
0x140049992  mov     eax, [r14+0CCh]
0x140049999  mov     [r14+0DCh], eax
0x1400499a0  mov     rax, [rbp+100h+var_A8]
0x1400499a4  mov     [r14+0CCh], r12d
0x1400499ab  mov     r12b, [rsp+200h+var_1D0]
0x1400499b0  mov     [r14+0C0h], rax
0x1400499b7  mov     [r14+108h], rbx
0x1400499be  mov     dword ptr [r15], 28h ; '('
0x1400499c5  mov     [r14+0C8h], r13d
0x1400499cc  mov     rax, [r14+10h]
0x1400499d0  mov     [rbp+100h+var_F6], 9
0x1400499d4  mov     byte ptr [rsp+200h+var_1E0], r12b; unsigned __int8
0x1400499d9  mov     rcx, [rax+188h]
0x1400499e0  mov     [rbp+100h+var_B0], rcx
0x1400499e4  mov     rcx, [r14+28h]; struct _LOG_HANDLE *
0x1400499e8  call    ?SlLogSetHostInfo@@YAJPEAX00KE@Z; SlLogSetHostInfo(void *,void *,void *,ulong,uchar)
0x1400499ed  mov     esi, eax
0x1400499ef  test    eax, eax
0x1400499f1  js      short loc_140049A32
0x1400499f3  mov     rbx, [r14+50h]
0x1400499f7  lock inc dword ptr [rbx+24h]
0x1400499fb  lock inc dword ptr [rbx+1Ch]
0x1400499ff  xor     ecx, ecx; PerformanceFrequency
0x140049a01  call    cs:__imp_KeQueryPerformanceCounter
0x140049a08  nop     dword ptr [rax+rax+00h]
0x140049a0d  sub     rax, rdi
0x140049a10  lock add [rbx+30h], rax
0x140049a15  test    r12b, r12b
0x140049a18  jz      short loc_140049A4C
0x140049a1a  mov     rcx, r14; this
0x140049a1d  call    ?FlushSynchronous@SIO_LOG@@QEAAJXZ; SIO_LOG::FlushSynchronous(void)
0x140049a22  mov     esi, eax
0x140049a24  test    eax, eax
0x140049a26  js      short loc_140049A32
0x140049a28  lock dec dword ptr [r14+100h]
0x140049a30  jmp     short loc_140049A4C
0x140049a32  cmp     esi, 0C0E70013h
0x140049a38  jnz     short loc_140049A4C
0x140049a3a  mov     rcx, [r14+8]
0x140049a3e  xor     edx, edx
0x140049a40  mov     rax, [rcx]
0x140049a43  mov     rax, [rax+60h]
0x140049a47  call    _guard_dispatch_icall
0x140049a4c  mov     rcx, [rsp+200h+Src]; P
0x140049a51  test    rcx, rcx
0x140049a54  jz      short loc_140049A64
0x140049a56  xor     edx, edx; Tag
0x140049a58  call    cs:__imp_ExFreePoolWithTag
0x140049a5f  nop     dword ptr [rax+rax+00h]
0x140049a64  test    esi, esi
0x140049a66  jns     short loc_140049A70
0x140049a68  lock dec dword ptr [r14+100h]
0x140049a70  lea     rax, ??_7SC_PACKET@@6B@; const SC_PACKET::`vftable'
0x140049a77  lea     rcx, [rsp+200h+var_1A0]; this
0x140049a7c  mov     [rsp+200h+var_1A0], rax
0x140049a81  call    ??1SIO_LOG_PACKET@@UEAA@XZ; SIO_LOG_PACKET::~SIO_LOG_PACKET(void)
0x140049a86  mov     eax, esi
0x140049a88  mov     rcx, [rbp+100h+var_48]
0x140049a8f  xor     rcx, rsp; StackCookie
0x140049a92  call    __security_check_cookie
0x140049a97  add     rsp, 1C8h
0x140049a9e  pop     r15
0x140049aa0  pop     r14
0x140049aa2  pop     r13
0x140049aa4  pop     r12
0x140049aa6  pop     rdi
0x140049aa7  pop     rsi
0x140049aa8  pop     rbx
0x140049aa9  pop     rbp
0x140049aaa  retn
```
