# HTTP_REQUEST_HANDLE_OBJECT::HTTP_REQUEST_HANDLE_OBJECT(INTERNET_CONNECT_HANDLE_OBJECT *,void *,ulong)

- ea: `0x1800122a0`
- end: `0x180012aaa`
- name: `??0HTTP_REQUEST_HANDLE_OBJECT@@QEAA@PEAVINTERNET_CONNECT_HANDLE_OBJECT@@PEAXK@Z`
- size: `2058`
- prototype: `HTTP_REQUEST_HANDLE_OBJECT *__fastcall(HTTP_REQUEST_HANDLE_OBJECT *this, struct INTERNET_CONNECT_HANDLE_OBJECT *, void *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180013e44`

## callees

- `0x1800122a0`
- `0x180012ab0`
- `0x180012ad0`
- `0x1800a3da8`
- `0x1800a3db4`
- `0x1800cdd7c`
- `0x1800cf58c`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001249a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001249a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012651`

## pseudocode

```c
HTTP_REQUEST_HANDLE_OBJECT *__fastcall HTTP_REQUEST_HANDLE_OBJECT::HTTP_REQUEST_HANDLE_OBJECT(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        struct INTERNET_CONNECT_HANDLE_OBJECT *a2,
        void *a3,
        int a4)
{
  unsigned __int64 v7; // rdx
  void *v8; // r13
  int v9; // ecx
  unsigned int v10; // r12d
  const void *v11; // r15
  __int64 v12; // rdi
  void *v13; // rcx
  int v14; // ecx
  const void *v15; // r15
  __int64 v16; // rdi
  void *v17; // rcx
  bool v18; // zf
  __int64 v19; // rdi
  int v20; // eax
  int v21; // esi
  signed __int32 v22; // ebp
  DWORD CurrentProcessId; // edi
  DWORD CurrentThreadId; // eax
  __int64 v25; // rdi
  unsigned int v27; // ebp
  void *v28; // rax
  unsigned int v29; // ebp
  void *v30; // r12
  void *v31; // rax
  unsigned __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  __int64 v35; // [rsp+20h] [rbp-38h]

  INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(this, a2);
  v8 = 0;
  *(_QWORD *)this = &INTERNET_CONNECT_HANDLE_OBJECT::`vftable';
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 53) = 0;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 10, WPP_b99d9a08caaa3540d9ac478cfb7595e4_Traceguids);
  v9 = *((_DWORD *)a2 + 96);
  v10 = 87;
  v11 = (const void *)*((_QWORD *)a2 + 47);
  v12 = (unsigned int)(v9 - 1);
  if ( !v9 )
    v12 = 0;
  if ( !v11 )
  {
LABEL_6:
    v13 = (void *)*((_QWORD *)this + 47);
    if ( v13 )
      operator delete(v13, v7);
    *((_QWORD *)this + 47) = 0;
    *((_QWORD *)this + 48) = 0;
    goto LABEL_9;
  }
  v27 = v12 + 1;
  if ( (unsigned int)v12 >= (int)v12 + 1 )
  {
    v33 = 87;
    goto LABEL_61;
  }
  if ( v27 > 0x7FFFFFFF )
  {
    *((_DWORD *)this + 18) = 13;
    goto LABEL_9;
  }
  if ( (_DWORD)v12 == -1 )
    goto LABEL_6;
  if ( v27 > *((_DWORD *)this + 97) )
  {
    v28 = operator new[](saturated_mul(v27, 2u));
    if ( v28 )
    {
      v8 = (void *)*((_QWORD *)this + 47);
      *((_QWORD *)this + 47) = v28;
      *((_DWORD *)this + 97) = v27;
      goto LABEL_41;
    }
    v33 = 8;
LABEL_61:
    *((_DWORD *)this + 18) = v33;
    goto LABEL_9;
  }
LABEL_41:
  if ( (_DWORD)v12 )
    memcpy_0(*((void **)this + 47), v11, 2LL * (unsigned int)v12);
  v7 = *((_QWORD *)this + 47);
  *(_WORD *)(v7 + 2 * v12) = 0;
  *((_DWORD *)this + 96) = v27;
  if ( v8 )
    operator delete(v8, v7);
LABEL_9:
  v14 = *((_DWORD *)a2 + 100);
  v15 = (const void *)*((_QWORD *)a2 + 49);
  v16 = (unsigned int)(v14 - 1);
  if ( !v14 )
    v16 = 0;
  if ( !v15 )
    goto LABEL_12;
  v29 = v16 + 1;
  if ( (unsigned int)v16 >= (int)v16 + 1 )
  {
    v34 = 87;
LABEL_63:
    *((_DWORD *)this + 18) = v34;
    goto LABEL_16;
  }
  if ( v29 <= 0x7FFFFFFF )
  {
    if ( (_DWORD)v16 == -1 )
    {
LABEL_12:
      v17 = (void *)*((_QWORD *)this + 49);
      if ( v17 )
        operator delete(v17, v7);
      *((_QWORD *)this + 49) = 0;
      *((_QWORD *)this + 50) = 0;
LABEL_15:
      v10 = 0;
      goto LABEL_16;
    }
    v30 = 0;
    if ( v29 <= *((_DWORD *)this + 101) )
    {
LABEL_52:
      if ( (_DWORD)v16 )
        memcpy_0(*((void **)this + 49), v15, 2LL * (unsigned int)v16);
      v32 = *((_QWORD *)this + 49);
      *(_WORD *)(v32 + 2 * v16) = 0;
      *((_DWORD *)this + 100) = v29;
      if ( v30 )
        operator delete(v30, v32);
      goto LABEL_15;
    }
    v31 = operator new[](saturated_mul(v29, 2u));
    if ( v31 )
    {
      v30 = (void *)*((_QWORD *)this + 49);
      *((_QWORD *)this + 49) = v31;
      *((_DWORD *)this + 101) = v29;
      goto LABEL_52;
    }
    v34 = 8;
    v10 = 8;
    goto LABEL_63;
  }
  v10 = 13;
  *((_DWORD *)this + 18) = 13;
LABEL_16:
  *((_DWORD *)this + 102) = *((_DWORD *)a2 + 102);
  *((_WORD *)this + 206) = *((_WORD *)a2 + 206);
  *((_DWORD *)this + 104) = *((_DWORD *)a2 + 104);
  *((_DWORD *)this + 105) = *((_DWORD *)a2 + 105);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 11, WPP_b99d9a08caaa3540d9ac478cfb7595e4_Traceguids, v10, v35);
  *(_QWORD *)this = &HTTP_REQUEST_HANDLE_OBJECT::`vftable'{for `INTERNET_CONNECT_HANDLE_OBJECT'};
  *((_QWORD *)this + 54) = &HTTP_REQUEST_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'};
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 67) = 0;
  CUnicodeString::CUnicodeString((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 544));
  CUnicodeString::CUnicodeString((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 560));
  CUnicodeString::CUnicodeString((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 576));
  CUnicodeString::CUnicodeString((HTTP_REQUEST_HANDLE_OBJECT *)((char *)this + 592));
  *((_QWORD *)this + 85) = (char *)this + 752;
  *((_QWORD *)this + 87) = 0;
  *((_DWORD *)this + 176) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 712));
  *(_OWORD *)*((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 127) = qword_1800E7D10;
  *((_QWORD *)this + 128) = 0;
  *((_QWORD *)this + 129) = qword_1800E7D10;
  *((_QWORD *)this + 130) = 0;
  *((_QWORD *)this + 135) = qword_1800E7D10;
  *((_QWORD *)this + 136) = 0;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
  {
    LODWORD(v35) = *((_DWORD *)a2 + 35);
    WPP_SF_qD(1032, 10, WPP_7006f7fc48e1328070e0d88382e485e0_Traceguids, this);
  }
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  v18 = *((_DWORD *)this + 35) == 0;
  *((_DWORD *)this + 116) = 0;
  *((_DWORD *)this + 110) = 1;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_DWORD *)this + 168) = a4 | 0x400000;
  if ( v18 )
    *((_DWORD *)this + 35) = a4 & 0x10000000;
  v18 = GlobalEnableBranchCache == 0;
  *((_WORD *)this + 338) = 0x8000;
  *((_QWORD *)this + 101) = 0;
  *(_QWORD *)((char *)this + 828) = 0;
  *(_QWORD *)((char *)this + 820) = 0;
  *((_BYTE *)this + 816) = 0;
  *((_DWORD *)this + 248) = 0;
  if ( v18 )
    goto LABEL_59;
  v19 = *((_QWORD *)this + 3);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19) != 1952804425 )
    v19 = *(_QWORD *)(v19 + 24);
  if ( *(_DWORD *)(v19 + 772) )
LABEL_59:
    v20 = 0;
  else
    v20 = 1;
  *((_DWORD *)this + 249) = v20;
  *((_DWORD *)this + 152) = 0x2000;
  *((_DWORD *)this + 153) = 0x2000;
  *((_DWORD *)this + 10) = 1902465608;
  if ( this != (HTTP_REQUEST_HANDLE_OBJECT *)-184LL )
  {
    v21 = *((_DWORD *)this + 8);
    v22 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    CurrentProcessId = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)this + 46) = v21;
    *((_DWORD *)this + 48) = CurrentProcessId ^ (CurrentThreadId << 16);
    *((_DWORD *)this + 47) = v22;
    *((_DWORD *)this + 49) = (_DWORD)this;
  }
  *((_DWORD *)this + 209) = 0;
  *((_DWORD *)this + 211) = 0;
  *((_OWORD *)this + 53) = 0;
  *((_OWORD *)this + 54) = 0;
  *((_OWORD *)this + 55) = 0;
  *((_QWORD *)this + 112) = 0;
  *((_QWORD *)this + 110) = (char *)this + 840;
  *((_DWORD *)this + 212) = 56;
  *((_QWORD *)this + 83) = 0;
  *(_QWORD *)((char *)this + 972) = 0;
  *((_DWORD *)this + 245) = 0;
  *((_DWORD *)this + 226) = 0;
  v25 = *((_QWORD *)a2 + 3);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25) != 1952804425 )
    v25 = *(_QWORD *)(v25 + 24);
  v18 = (*((_DWORD *)this + 168) & 0x800000) == 0;
  *((_DWORD *)this + 227) = *(_DWORD *)(v25 + 380);
  *((_DWORD *)this + 228) = *(_DWORD *)(v25 + 384);
  *((_DWORD *)this + 229) = *(_DWORD *)(v25 + 388);
  *((_DWORD *)this + 230) = *(_DWORD *)(v25 + 392);
  *((_DWORD *)this + 231) = *(_DWORD *)(v25 + 396);
  *((_DWORD *)this + 232) = *(_DWORD *)(v25 + 400);
  *((_DWORD *)this + 233) = *(_DWORD *)(v25 + 404);
  *((_DWORD *)this + 234) = *(_DWORD *)(v25 + 408);
  *((_DWORD *)this + 235) = *(_DWORD *)(v25 + 412);
  *((_DWORD *)this + 236) = *(_DWORD *)(v25 + 416);
  *((_DWORD *)this + 237) = *(_DWORD *)(v25 + 420);
  *((_DWORD *)this + 238) = *(_DWORD *)(v25 + 424);
  *((_DWORD *)this + 239) = *(_DWORD *)(v25 + 428);
  *((_DWORD *)this + 241) = *(_DWORD *)(v25 + 432);
  *((_DWORD *)this + 242) = *(_DWORD *)(v25 + 436);
  *((_DWORD *)this + 240) = 0;
  if ( !v18 && !*((_DWORD *)this + 18) && *(_DWORD *)(v25 + 448) == 2 )
    *(_DWORD *)(v25 + 448) = 1;
  *((_QWORD *)this + 125) = 0;
  *((_DWORD *)this + 252) = 0;
  *((_QWORD *)this + 123) = 0;
  *(_QWORD *)((char *)this + 468) = 0;
  *(_OWORD *)((char *)this + 1048) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_DWORD *)this + 268) = 0;
  *((_DWORD *)this + 274) = 0;
  *(_OWORD *)((char *)this + 1100) = 0;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_d(1032, 11, WPP_7006f7fc48e1328070e0d88382e485e0_Traceguids, *((unsigned int *)this + 18), v35);
  return this;
}

```

## disassembly

```asm
0x1800122a0  push    rbx
0x1800122a2  sub     rsp, 50h
0x1800122a6  mov     [rsp+58h+arg_8], rsi
0x1800122ab  mov     rbx, rcx
0x1800122ae  mov     [rsp+58h+arg_10], rdi
0x1800122b3  mov     esi, r9d
0x1800122b6  mov     [rsp+58h+var_10], r12
0x1800122bb  mov     [rsp+58h+var_18], r13
0x1800122c0  mov     [rsp+58h+var_20], r14
0x1800122c5  mov     r14, rdx
0x1800122c8  mov     [rsp+58h+var_28], r15
0x1800122cd  call    ??0INTERNET_HANDLE_BASE@@QEAA@PEAV0@@Z; INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(INTERNET_HANDLE_BASE *)
0x1800122d2  xor     r13d, r13d
0x1800122d5  lea     rax, ??_7INTERNET_CONNECT_HANDLE_OBJECT@@6B@; const INTERNET_CONNECT_HANDLE_OBJECT::`vftable'
0x1800122dc  mov     [rbx], rax
0x1800122df  mov     [rbx+178h], r13
0x1800122e6  mov     [rbx+180h], r13
0x1800122ed  mov     [rbx+188h], r13
0x1800122f4  mov     [rbx+190h], r13
0x1800122fb  mov     [rbx+1A8h], r13
0x180012302  test    byte ptr cs:xmmword_180107A60+1, 1
0x180012309  jnz     loc_180012A26
0x18001230f  mov     ecx, [r14+180h]
0x180012316  mov     r12d, 57h ; 'W'
0x18001231c  mov     r15, [r14+178h]
0x180012323  test    ecx, ecx
0x180012325  mov     [rsp+58h+arg_0], rbp
0x18001232a  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180012331  lea     edi, [rcx-1]
0x180012334  cmovz   edi, r13d
0x180012338  test    r15, r15
0x18001233b  jnz     loc_18001283F
0x180012341  mov     rcx, [rbx+178h]; void *
0x180012348  test    rcx, rcx
0x18001234b  jnz     loc_180012A12
0x180012351  mov     [rbx+178h], r13
0x180012358  mov     [rbx+180h], r13
0x18001235f  mov     ecx, [r14+190h]
0x180012366  test    ecx, ecx
0x180012368  mov     r15, [r14+188h]
0x18001236f  lea     edi, [rcx-1]
0x180012372  cmovz   edi, r13d
0x180012376  test    r15, r15
0x180012379  jnz     loc_1800128D6
0x18001237f  mov     rcx, [rbx+188h]; void *
0x180012386  test    rcx, rcx
0x180012389  jnz     loc_180012A1C
0x18001238f  mov     [rbx+188h], r13
0x180012396  mov     qword ptr [rbx+190h], 0
0x1800123a1  mov     r12d, r13d
0x1800123a4  mov     eax, [r14+198h]
0x1800123ab  mov     [rbx+198h], eax
0x1800123b1  movzx   eax, word ptr [r14+19Ch]
0x1800123b9  mov     [rbx+19Ch], ax
0x1800123c0  mov     eax, [r14+1A0h]
0x1800123c7  mov     [rbx+1A0h], eax
0x1800123cd  mov     eax, [r14+1A4h]
0x1800123d4  mov     [rbx+1A4h], eax
0x1800123da  test    byte ptr cs:xmmword_180107A60+1, 1
0x1800123e1  jnz     loc_180012A44
0x1800123e7  lea     rax, ??_7HTTP_REQUEST_HANDLE_OBJECT@@6BINTERNET_CONNECT_HANDLE_OBJECT@@@; const HTTP_REQUEST_HANDLE_OBJECT::`vftable'{for `INTERNET_CONNECT_HANDLE_OBJECT'}
0x1800123ee  mov     [rbx], rax
0x1800123f1  lea     rcx, [rbx+220h]; this
0x1800123f8  lea     rax, ??_7HTTP_REQUEST_HANDLE_OBJECT@@6BIHttpAsyncCallback@@@; const HTTP_REQUEST_HANDLE_OBJECT::`vftable'{for `IHttpAsyncCallback'}
0x1800123ff  mov     [rbx+1B0h], rax
0x180012406  mov     [rbx+1E0h], r13
0x18001240d  mov     qword ptr [rbx+1E8h], 0
0x180012418  mov     [rbx+1F0h], r13
0x18001241f  mov     qword ptr [rbx+1F8h], 0
0x18001242a  mov     [rbx+200h], r13
0x180012431  mov     qword ptr [rbx+208h], 0
0x18001243c  mov     [rbx+210h], r13
0x180012443  mov     qword ptr [rbx+218h], 0
0x18001244e  call    ??0CUnicodeString@@QEAA@XZ; CUnicodeString::CUnicodeString(void)
0x180012453  lea     rcx, [rbx+230h]; this
0x18001245a  call    ??0CUnicodeString@@QEAA@XZ; CUnicodeString::CUnicodeString(void)
0x18001245f  lea     rcx, [rbx+240h]; this
0x180012466  call    ??0CUnicodeString@@QEAA@XZ; CUnicodeString::CUnicodeString(void)
0x18001246b  lea     rcx, [rbx+250h]; this
0x180012472  call    ??0CUnicodeString@@QEAA@XZ; CUnicodeString::CUnicodeString(void)
0x180012477  lea     rax, [rbx+2F0h]
0x18001247e  mov     [rbx+2A8h], rax
0x180012485  lea     rcx, [rbx+2C8h]; lpCriticalSection
0x18001248c  mov     [rbx+2B8h], r13
0x180012493  mov     [rbx+2C0h], r13d
0x18001249a  call    cs:__imp_InitializeCriticalSection
0x1800124a0  mov     rax, [rbx+2A8h]
0x1800124a7  xorps   xmm0, xmm0
0x1800124aa  mov     r12, [rsp+58h+var_10]
0x1800124af  movups  xmmword ptr [rax], xmm0
0x1800124b2  mov     qword ptr [rbx+2B0h], 0
0x1800124bd  lea     rax, qword_1800E7D10
0x1800124c4  mov     [rbx+308h], r13
0x1800124cb  mov     qword ptr [rbx+310h], 0
0x1800124d6  mov     [rbx+318h], r13
0x1800124dd  mov     qword ptr [rbx+320h], 0
0x1800124e8  mov     [rbx+3F8h], rax
0x1800124ef  mov     [rbx+400h], r13
0x1800124f6  mov     [rbx+408h], rax
0x1800124fd  mov     [rbx+410h], r13
0x180012504  mov     [rbx+438h], rax
0x18001250b  mov     [rbx+440h], r13
0x180012512  test    byte ptr cs:xmmword_180107A60+1, 1
0x180012519  jnz     loc_180012A62
0x18001251f  mov     eax, esi
0x180012521  mov     [rbx+1C0h], r13
0x180012528  bts     eax, 16h
0x18001252c  mov     [rbx+1C8h], r13
0x180012533  cmp     dword ptr [rbx+8Ch], 0
0x18001253a  mov     [rbx+1D0h], r13d
0x180012541  mov     dword ptr [rbx+1B8h], 1
0x18001254b  mov     qword ptr [rbx+290h], 0
0x180012556  mov     [rbx+268h], r13
0x18001255d  mov     [rbx+270h], r13
0x180012564  mov     qword ptr [rbx+278h], 0
0x18001256f  mov     qword ptr [rbx+280h], 0
0x18001257a  mov     [rbx+288h], r13
0x180012581  mov     [rbx+2A0h], eax
0x180012587  jnz     short loc_180012595
0x180012589  and     esi, 10000000h
0x18001258f  mov     [rbx+8Ch], esi
0x180012595  cmp     cs:?GlobalEnableBranchCache@@3KA, 0; ulong GlobalEnableBranchCache
0x18001259c  mov     word ptr [rbx+2A4h], 8000h
0x1800125a5  mov     qword ptr [rbx+328h], 0
0x1800125b0  mov     qword ptr [rbx+33Ch], 0
0x1800125bb  mov     qword ptr [rbx+334h], 0
0x1800125c6  mov     byte ptr [rbx+330h], 0
0x1800125cd  mov     [rbx+3E0h], r13d
0x1800125d4  jz      loc_1800129A1
0x1800125da  mov     rdi, [rbx+18h]
0x1800125de  mov     rcx, rdi
0x1800125e1  mov     rax, [rdi]
0x1800125e4  mov     rax, [rax+8]
0x1800125e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ed  cmp     eax, 74656E49h
0x1800125f2  jz      short loc_1800125F8
0x1800125f4  mov     rdi, [rdi+18h]
0x1800125f8  cmp     dword ptr [rdi+304h], 0
0x1800125ff  jnz     loc_1800129A1
0x180012605  mov     eax, 1
0x18001260a  lea     r15, [rbx+0B8h]
0x180012611  mov     [rbx+3E4h], eax
0x180012617  mov     dword ptr [rbx+260h], 2000h
0x180012621  mov     dword ptr [rbx+264h], 2000h
0x18001262b  mov     dword ptr [rbx+28h], 71655248h
0x180012632  test    r15, r15
0x180012635  jz      short loc_18001266B
0x180012637  mov     esi, [rbx+20h]
0x18001263a  mov     ebp, 1
0x18001263f  lock xadd cs:?g_dwActivityIdCount@@3KC, ebp; ulong volatile g_dwActivityIdCount
0x180012647  inc     ebp
0x180012649  call    cs:__imp_GetCurrentProcessId
0x18001264f  mov     edi, eax
0x180012651  call    cs:__imp_GetCurrentThreadId
0x180012657  shl     eax, 10h
0x18001265a  xor     eax, edi
0x18001265c  mov     [r15], esi
0x18001265f  mov     [r15+8], eax
0x180012663  mov     [r15+4], ebp
0x180012667  mov     [r15+0Ch], ebx
0x18001266b  mov     [rbx+344h], r13d
0x180012672  xor     eax, eax
0x180012674  mov     [rbx+34Ch], r13d
0x18001267b  xorps   xmm0, xmm0
0x18001267e  movups  xmmword ptr [rbx+350h], xmm0
0x180012685  movups  xmmword ptr [rbx+360h], xmm0
0x18001268c  movups  xmmword ptr [rbx+370h], xmm0
0x180012693  mov     [rbx+380h], rax
0x18001269a  lea     rax, [rbx+348h]
0x1800126a1  mov     [rbx+370h], rax
0x1800126a8  mov     dword ptr [rbx+350h], 38h ; '8'
0x1800126b2  mov     qword ptr [rbx+298h], 0
0x1800126bd  mov     qword ptr [rbx+3CCh], 0
0x1800126c8  mov     [rbx+3D4h], r13d
0x1800126cf  mov     [rbx+388h], r13d
0x1800126d6  mov     rdi, [r14+18h]
0x1800126da  mov     rcx, rdi
0x1800126dd  mov     rax, [rdi]
0x1800126e0  mov     rax, [rax+8]
0x1800126e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126e9  mov     r15, [rsp+58h+var_28]
0x1800126ee  mov     r14, [rsp+58h+var_20]
0x1800126f3  mov     rsi, [rsp+58h+arg_8]
0x1800126f8  mov     rbp, [rsp+58h+arg_0]
0x1800126fd  cmp     eax, 74656E49h
0x180012702  jz      short loc_180012708
0x180012704  mov     rdi, [rdi+18h]
0x180012708  test    dword ptr [rbx+2A0h], 800000h
0x180012712  mov     eax, [rdi+17Ch]
0x180012718  mov     [rbx+38Ch], eax
0x18001271e  mov     eax, [rdi+180h]
0x180012724  mov     [rbx+390h], eax
0x18001272a  mov     eax, [rdi+184h]
0x180012730  mov     [rbx+394h], eax
0x180012736  mov     eax, [rdi+188h]
0x18001273c  mov     [rbx+398h], eax
0x180012742  mov     eax, [rdi+18Ch]
0x180012748  mov     [rbx+39Ch], eax
0x18001274e  mov     eax, [rdi+190h]
0x180012754  mov     [rbx+3A0h], eax
0x18001275a  mov     eax, [rdi+194h]
0x180012760  mov     [rbx+3A4h], eax
0x180012766  mov     eax, [rdi+198h]
0x18001276c  mov     [rbx+3A8h], eax
0x180012772  mov     eax, [rdi+19Ch]
0x180012778  mov     [rbx+3ACh], eax
0x18001277e  mov     eax, [rdi+1A0h]
0x180012784  mov     [rbx+3B0h], eax
0x18001278a  mov     eax, [rdi+1A4h]
0x180012790  mov     [rbx+3B4h], eax
0x180012796  mov     eax, [rdi+1A8h]
0x18001279c  mov     [rbx+3B8h], eax
0x1800127a2  mov     eax, [rdi+1ACh]
0x1800127a8  mov     [rbx+3BCh], eax
0x1800127ae  mov     eax, [rdi+1B0h]
0x1800127b4  mov     [rbx+3C4h], eax
0x1800127ba  mov     eax, [rdi+1B4h]
0x1800127c0  mov     [rbx+3C8h], eax
0x1800127c6  mov     [rbx+3C0h], r13d
0x1800127cd  jnz     loc_18001297B
0x1800127d3  mov     rdi, [rsp+58h+arg_10]
0x1800127d8  xorps   xmm0, xmm0
0x1800127db  mov     [rbx+3E8h], r13
0x1800127e2  xor     eax, eax
0x1800127e4  mov     [rbx+3F0h], r13d
0x1800127eb  mov     qword ptr [rbx+3D8h], 0
0x1800127f6  mov     qword ptr [rbx+1D4h], 0
0x180012801  movups  xmmword ptr [rbx+418h], xmm0
0x180012808  mov     [rbx+428h], rax
0x18001280f  mov     [rbx+430h], r13d
0x180012816  mov     [rbx+448h], r13d
0x18001281d  mov     r13, [rsp+58h+var_18]
0x180012822  movups  xmmword ptr [rbx+44Ch], xmm0
0x180012829  test    byte ptr cs:xmmword_180107A60+1, 1
0x180012830  jnz     loc_180012A8B
0x180012836  mov     rax, rbx
0x180012839  add     rsp, 50h
0x18001283d  pop     rbx
0x18001283e  retn
0x18001283f  lea     ebp, [rdi+1]
0x180012842  cmp     edi, ebp
0x180012844  jnb     loc_1800129D3
0x18001284a  cmp     ebp, 7FFFFFFFh
0x180012850  ja      loc_1800129F5
0x180012856  test    ebp, ebp
0x180012858  jz      loc_180012341
0x18001285e  cmp     ebp, [rbx+184h]
0x180012864  jbe     short loc_180012899
0x180012866  mov     ecx, ebp
0x180012868  mov     eax, 2
0x18001286d  mul     rcx
0x180012870  cmovb   rax, r8
0x180012874  mov     rcx, rax; unsigned __int64
0x180012877  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001287c  test    rax, rax
0x18001287f  jz      loc_1800129B6
0x180012885  mov     r13, [rbx+178h]
0x18001288c  mov     [rbx+178h], rax
0x180012893  mov     [rbx+184h], ebp
0x180012899  test    edi, edi
0x18001289b  jz      short loc_1800128B2
0x18001289d  mov     rcx, [rbx+178h]; void *
0x1800128a4  mov     rdx, r15; Src
0x1800128a7  mov     r8d, edi
0x1800128aa  add     r8, r8; Size
0x1800128ad  call    memcpy_0
0x1800128b2  mov     rdx, [rbx+178h]; unsigned __int64
0x1800128b9  xor     eax, eax
0x1800128bb  mov     [rdx+rdi*2], ax
0x1800128bf  mov     [rbx+180h], ebp
0x1800128c5  test    r13, r13
0x1800128c8  jnz     loc_1800129A9
0x1800128ce  xor     r13d, r13d
0x1800128d1  jmp     loc_18001235F
0x1800128d6  lea     ebp, [rdi+1]
0x1800128d9  cmp     edi, ebp
0x1800128db  jnb     loc_1800129E4
0x1800128e1  cmp     ebp, 7FFFFFFFh
0x1800128e7  ja      loc_180012A02
0x1800128ed  test    ebp, ebp
0x1800128ef  jz      loc_18001237F
0x1800128f5  mov     r12, r13
0x1800128f8  cmp     ebp, [rbx+194h]
0x1800128fe  jbe     short loc_18001293A
0x180012900  mov     ecx, ebp
0x180012902  mov     eax, 2
0x180012907  mul     rcx
0x18001290a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012911  cmovb   rax, rcx
0x180012915  mov     rcx, rax; unsigned __int64
0x180012918  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001291d  test    rax, rax
0x180012920  jz      loc_1800129C3
0x180012926  mov     r12, [rbx+188h]
0x18001292d  mov     [rbx+188h], rax
0x180012934  mov     [rbx+194h], ebp
0x18001293a  test    edi, edi
0x18001293c  jz      short loc_180012953
0x18001293e  mov     rcx, [rbx+188h]; void *
0x180012945  mov     rdx, r15; Src
  ... truncated ...
```
