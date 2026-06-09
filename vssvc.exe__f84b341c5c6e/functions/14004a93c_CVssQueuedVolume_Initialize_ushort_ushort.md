# CVssQueuedVolume::Initialize(ushort *,ushort *)

- ea: `0x14004a93c`
- end: `0x14004abed`
- name: `?Initialize@CVssQueuedVolume@@QEAAJPEAG0@Z`
- size: `689`
- prototype: `int(CVssQueuedVolume *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400a0a18`

## callees

- `0x140010170`
- `0x1400137c0`
- `0x140013b00`
- `0x14001e700`
- `0x140027cb0`
- `0x140049ec4`
- `0x14004a93c`
- `0x140091560`
- `0x1400921dc`
- `0x1400a16f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004aa0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004aaa2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004aa0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004aaa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aa1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004aab1`

## string_xrefs

- `0x14004aa7a`: `CreateEvent( NULL, TRUE, FALSE, NULL ) for FinishCurrentEvent`
- `0x14004ab0f`: `CreateEvent( NULL, FALSE, FALSE, NULL ) for FlushCompletedEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssQueuedVolume::Initialize(unsigned __int16 **this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int16 *EventW; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned __int16 v13; // cx
  unsigned __int16 *v14; // rax
  unsigned int v15; // ebx
  int v17; // [rsp+48h] [rbp-380h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-378h] BYREF
  const unsigned __int16 *v19; // [rsp+58h] [rbp-370h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-368h]
  int v21; // [rsp+68h] [rbp-360h]
  int v22; // [rsp+6Ch] [rbp-35Ch]
  int v23; // [rsp+70h] [rbp-358h]
  _BYTE v24[120]; // [rsp+78h] [rbp-350h] BYREF
  int v25; // [rsp+F0h] [rbp-2D8h]
  LPVOID v26; // [rsp+100h] [rbp-2C8h] BYREF
  unsigned int v27; // [rsp+108h] [rbp-2C0h]
  unsigned int v28; // [rsp+124h] [rbp-2A4h]
  _com_error *v29; // [rsp+170h] [rbp-258h] BYREF
  const std::exception *v30; // [rsp+178h] [rbp-250h] BYREF
  unsigned __int16 v31[264]; // [rsp+180h] [rbp-248h] BYREF

  v18 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
  v19 = L"CVssQueuedVolume::Initialize";
  v20 = L"CORLOVLC";
  v21 = 128;
  v22 = 1;
  v23 = 255;
  v25 = 0x1000000;
  memset_0(v24, 0, sizeof(v24));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v26, (__int64)&v18, 0);
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v26, this + 9, a2);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v26, this + 10, a3);
    EventW = (unsigned __int16 *)CreateEventW(0, 0, 0, 0);
    this[8] = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v18 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v19 = L"CVssQueuedVolume::Initialize";
      v20 = L"CORLOVLC";
      v21 = 141;
      v22 = 1;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(
        &v26,
        &v18,
        v8,
        L"CreateEvent( NULL, TRUE, FALSE, NULL ) for FinishCurrentEvent");
    }
    v9 = (unsigned __int16 *)CreateEventW(0, 1, 0, 0);
    this[7] = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v18 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v19 = L"CVssQueuedVolume::Initialize";
      v20 = L"CORLOVLC";
      v21 = 147;
      v22 = 1;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CVssFunctionTracer::TranslateGenericError(
        &v26,
        &v18,
        v11,
        L"CreateEvent( NULL, FALSE, FALSE, NULL ) for FlushCompletedEvent");
    }
    v12 = StringCchPrintfW(v31, 0x104u, L"Lovelace(%s)", this[10]);
    if ( v12 == -2147024774 )
      v12 = 0;
    v27 = v12;
    v13 = v31[0];
    if ( v31[0] )
    {
      v14 = v31;
      do
      {
        if ( v13 == 92 )
          *v14 = 95;
        v13 = *++v14;
      }
      while ( *v14 );
    }
    CVssDiag::Initialize((CVssDiag *)(this + 46), v31);
    v27 = CVssQueuedVolume::InitializeFlushLevel((CVssQueuedVolume *)this);
  }
  catch ( long v17 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v26,
      v17,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolume::Initialize",
      0xAAu,
      v28);
  }
  catch ( _com_error *v29 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v26,
      v29,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolume::Initialize",
      0xAAu,
      v28);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v26,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolume::Initialize",
      0xAAu,
      v28);
  }
  catch ( const std::exception *v30 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v26,
      v30,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolume::Initialize",
      0xAAu,
      v28);
  }
  v15 = v27;
  CVssFunctionTracer::~CVssFunctionTracer(&v26);
  return v15;
}

```

## disassembly

```asm
0x14004a93c  mov     [rsp+arg_18], rbx
0x14004a941  push    rsi
0x14004a942  push    rdi
0x14004a943  push    r12
0x14004a945  push    r13
0x14004a947  push    r14
0x14004a949  sub     rsp, 3A0h
0x14004a950  mov     rax, cs:__security_cookie
0x14004a957  xor     rax, rsp
0x14004a95a  mov     [rsp+3C8h+var_38], rax
0x14004a962  mov     rsi, r8
0x14004a965  mov     rdi, rdx
0x14004a968  mov     rbx, rcx
0x14004a96b  lea     r12, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x14004a972  mov     [rsp+3C8h+var_378], r12
0x14004a977  lea     r13, aCvssqueuedvolu_6; "CVssQueuedVolume::Initialize"
0x14004a97e  mov     [rsp+3C8h+var_370], r13
0x14004a983  lea     rax, aCorlovlc; "CORLOVLC"
0x14004a98a  mov     [rsp+3C8h+var_368], rax
0x14004a98f  mov     [rsp+3C8h+var_360], 80h
0x14004a997  mov     [rsp+3C8h+var_35C], 1
0x14004a99f  mov     [rsp+3C8h+var_358], 0FFh
0x14004a9a7  xor     r14d, r14d
0x14004a9aa  mov     [rsp+3C8h+var_2D8], 1000000h
0x14004a9b5  xor     edx, edx; Val
0x14004a9b7  lea     r8d, [r14+78h]; Size
0x14004a9bb  lea     rcx, [rsp+3C8h+var_350]; void *
0x14004a9c0  call    memset_0
0x14004a9c5  xor     r8d, r8d
0x14004a9c8  lea     rdx, [rsp+3C8h+var_378]
0x14004a9cd  lea     rcx, [rsp+3C8h+var_2C8]
0x14004a9d5  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14004a9da  nop
0x14004a9db  lea     rdx, [rbx+48h]; unsigned __int16 **
0x14004a9df  mov     r8, rdi; unsigned __int16 *
0x14004a9e2  lea     rcx, [rsp+3C8h+var_2C8]; struct CVssFunctionTracer *
0x14004a9ea  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x14004a9ef  mov     r8, rsi; unsigned __int16 *
0x14004a9f2  lea     rdx, [rbx+50h]; unsigned __int16 **
0x14004a9f6  lea     rcx, [rsp+3C8h+var_2C8]; struct CVssFunctionTracer *
0x14004a9fe  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x14004aa03  xor     r9d, r9d; lpName
0x14004aa06  xor     r8d, r8d; bInitialState
0x14004aa09  xor     edx, edx; bManualReset
0x14004aa0b  xor     ecx, ecx; lpEventAttributes
0x14004aa0d  call    cs:__imp_CreateEventW
0x14004aa13  mov     [rbx+40h], rax
0x14004aa17  test    rax, rax
0x14004aa1a  jnz     short loc_14004AA96
0x14004aa1c  call    cs:__imp_GetLastError
0x14004aa22  mov     ebx, eax
0x14004aa24  test    eax, eax
0x14004aa26  jle     short loc_14004AA31
0x14004aa28  movzx   ebx, ax
0x14004aa2b  or      ebx, 80070000h
0x14004aa31  mov     [rsp+3C8h+var_378], r12
0x14004aa36  mov     [rsp+3C8h+var_370], r13
0x14004aa3b  lea     rax, aCorlovlc; "CORLOVLC"
0x14004aa42  mov     [rsp+3C8h+var_368], rax
0x14004aa47  mov     [rsp+3C8h+var_360], 8Dh
0x14004aa4f  mov     [rsp+3C8h+var_35C], 1
0x14004aa57  mov     [rsp+3C8h+var_358], 0FFh
0x14004aa5f  mov     [rsp+3C8h+var_2D8], 1000000h
0x14004aa6a  xor     edx, edx; Val
0x14004aa6c  lea     r8d, [rdx+78h]; Size
0x14004aa70  lea     rcx, [rsp+3C8h+var_350]; void *
0x14004aa75  call    memset_0
0x14004aa7a  lea     r9, aCreateeventNul; "CreateEvent( NULL, TRUE, FALSE, NULL ) "...
0x14004aa81  mov     r8d, ebx
0x14004aa84  lea     rdx, [rsp+3C8h+var_378]
0x14004aa89  lea     rcx, [rsp+3C8h+var_2C8]
0x14004aa91  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14004aa96  xor     r9d, r9d; lpName
0x14004aa99  xor     r8d, r8d; bInitialState
0x14004aa9c  lea     edx, [r9+1]; bManualReset
0x14004aaa0  xor     ecx, ecx; lpEventAttributes
0x14004aaa2  call    cs:__imp_CreateEventW
0x14004aaa8  mov     [rbx+38h], rax
0x14004aaac  test    rax, rax
0x14004aaaf  jnz     short loc_14004AB2B
0x14004aab1  call    cs:__imp_GetLastError
0x14004aab7  mov     ebx, eax
0x14004aab9  test    eax, eax
0x14004aabb  jle     short loc_14004AAC6
0x14004aabd  movzx   ebx, ax
0x14004aac0  or      ebx, 80070000h
0x14004aac6  mov     [rsp+3C8h+var_378], r12
0x14004aacb  mov     [rsp+3C8h+var_370], r13
0x14004aad0  lea     rax, aCorlovlc; "CORLOVLC"
0x14004aad7  mov     [rsp+3C8h+var_368], rax
0x14004aadc  mov     [rsp+3C8h+var_360], 93h
0x14004aae4  mov     [rsp+3C8h+var_35C], 1
0x14004aaec  mov     [rsp+3C8h+var_358], 0FFh
0x14004aaf4  mov     [rsp+3C8h+var_2D8], 1000000h
0x14004aaff  xor     edx, edx; Val
0x14004ab01  lea     r8d, [rdx+78h]; Size
0x14004ab05  lea     rcx, [rsp+3C8h+var_350]; void *
0x14004ab0a  call    memset_0
0x14004ab0f  lea     r9, aCreateeventNul_2; "CreateEvent( NULL, FALSE, FALSE, NULL )"...
0x14004ab16  mov     r8d, ebx
0x14004ab19  lea     rdx, [rsp+3C8h+var_378]
0x14004ab1e  lea     rcx, [rsp+3C8h+var_2C8]
0x14004ab26  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x14004ab2b  mov     r9, [rbx+50h]
0x14004ab2f  lea     r8, aLovelaceS; "Lovelace(%s)"
0x14004ab36  mov     edx, 104h; unsigned __int64
0x14004ab3b  lea     rcx, [rsp+3C8h+var_248]; unsigned __int16 *
0x14004ab43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004ab48  cmp     eax, 8007007Ah
0x14004ab4d  cmovz   eax, r14d
0x14004ab51  mov     [rsp+3C8h+var_2C0], eax
0x14004ab58  movzx   ecx, [rsp+3C8h+var_248]
0x14004ab60  test    cx, cx
0x14004ab63  jz      short loc_14004AB84
0x14004ab65  lea     rax, [rsp+3C8h+var_248]
0x14004ab6d  cmp     cx, 5Ch ; '\'
0x14004ab71  jnz     short loc_14004AB78
0x14004ab73  mov     word ptr [rax], 5Fh ; '_'
0x14004ab78  add     rax, 2
0x14004ab7c  movzx   ecx, word ptr [rax]
0x14004ab7f  test    cx, cx
0x14004ab82  jnz     short loc_14004AB6D
0x14004ab84  lea     rcx, [rbx+170h]; this
0x14004ab8b  lea     rdx, [rsp+3C8h+var_248]; unsigned __int16 *
0x14004ab93  call    ?Initialize@CVssDiag@@QEAAXPEBG@Z; CVssDiag::Initialize(ushort const *)
0x14004ab98  mov     rcx, rbx; this
0x14004ab9b  call    ?InitializeFlushLevel@CVssQueuedVolume@@AEAAJXZ; CVssQueuedVolume::InitializeFlushLevel(void)
0x14004aba0  mov     [rsp+3C8h+var_2C0], eax
0x14004aba7  jmp     short loc_14004ABAF
0x14004aba9  jmp     short loc_14004ABAF
0x14004abab  jmp     short loc_14004ABAF
0x14004abad  jmp     short $+2
0x14004abaf  mov     ebx, [rsp+3C8h+var_2C0]
0x14004abb6  lea     rcx, [rsp+3C8h+var_2C8]; this
0x14004abbe  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14004abc3  mov     eax, ebx
0x14004abc5  mov     rcx, [rsp+3C8h+var_38]
0x14004abcd  xor     rcx, rsp; StackCookie
0x14004abd0  call    __security_check_cookie
0x14004abd5  mov     rbx, [rsp+3C8h+arg_18]
0x14004abdd  add     rsp, 3A0h
0x14004abe4  pop     r14
0x14004abe6  pop     r13
0x14004abe8  pop     r12
0x14004abea  pop     rdi
0x14004abeb  pop     rsi
0x14004abec  retn
```
