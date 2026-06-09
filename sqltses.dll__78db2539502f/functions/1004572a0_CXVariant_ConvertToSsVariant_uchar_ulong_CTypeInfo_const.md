# CXVariant::ConvertToSsVariant(uchar *,ulong,CTypeInfo const *)

- ea: `0x1004572a0`
- end: `0x1004573de`
- name: `?ConvertToSsVariant@CXVariant@@QEAAJPEAEKPEBVCTypeInfo@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CXVariant *__hidden this, unsigned __int8 *, unsigned int, const struct CTypeInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10040d470`
- `0x1004559f0`
- `0x1004572a0`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100457366`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100457366`
- `sqldk!SystemThread_TlsIndex` at `0x10045732e`
- `sqldk!SystemThread_TlsOffset` at `0x100457337`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457350`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457350`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXVariant::ConvertToSsVariant(
        __m256i *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct CTypeInfo *a4)
{
  const struct CTypeInfo *v4; // r14
  __m256i *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __m128i v8; // xmm1
  __m128i v10; // xmm1
  const struct SQLError *CurrentException; // rax
  unsigned int v12; // [rsp+20h] [rbp-78h]
  _BYTE v13[16]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v14[24]; // [rsp+40h] [rbp-58h] BYREF
  __m256i v15; // [rsp+58h] [rbp-40h] BYREF

  v4 = a4;
  v5 = this;
  v15.m256i_i32[0] = 3;
  memset(&v15.m256i_u64[1], 0, 20);
  v15 = *this;
  this->m256i_i16[1] &= ~1u;
  try
  {
    v12 = CXVariant::PerformConvertToSsVariant((CXVariant *)this, a2, a3, a4);
  }
  catch ( SQLError v14 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v13, (const struct SQLError *)v14);
      v10 = *(__m128i *)v15.m256i_i8;
      *this = v15;
      v15.m256i_i16[1] = _mm_extract_epi16(v10, 1) & 0xFFFE;
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v13);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v13);
    }
    catch ( ShortStackException )
    {
    }
    v5 = this;
    v4 = a4;
  }
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  if ( *(_DWORD *)(v7 + 556) )
    ExceptionPostCatchActions((struct Worker *)v7);
  if ( v12 )
  {
    v8 = *(__m128i *)v15.m256i_i8;
    *v5 = v15;
    v15.m256i_i16[1] = _mm_extract_epi16(v8, 1) & 0xFFFE;
  }
  else
  {
    if ( (v15.m256i_i8[2] & 1) != 0 )
      CXVariant::ClearDeep<CTypeInfo>(&v15, v4);
    v15.m256i_i32[0] = 3;
    memset(&v15.m256i_u64[1], 0, 20);
  }
  return v12;
}

```

## disassembly

```asm
0x1004572a0  mov     rax, rsp
0x1004572a3  mov     [rax+20h], r9
0x1004572a7  mov     [rax+8], rcx
0x1004572ab  push    rdi
0x1004572ac  push    r14
0x1004572ae  push    r15
0x1004572b0  sub     rsp, 80h
0x1004572b7  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFEh
0x1004572bf  mov     [rax+10h], rbx
0x1004572c3  mov     [rax+18h], rsi
0x1004572c7  mov     r14, r9
0x1004572ca  mov     rbx, rcx
0x1004572cd  mov     dword ptr [rax-78h], 64h ; 'd'
0x1004572d4  xor     esi, esi
0x1004572d6  mov     dword ptr [rax-40h], 3
0x1004572dd  xorps   xmm0, xmm0
0x1004572e0  movdqu  xmmword ptr [rax-38h], xmm0
0x1004572e5  mov     [rax-28h], esi
0x1004572e8  movups  xmm0, xmmword ptr [rcx]
0x1004572eb  movups  xmmword ptr [rax-40h], xmm0
0x1004572ef  movups  xmm1, xmmword ptr [rcx+10h]
0x1004572f3  movups  xmmword ptr [rax-30h], xmm1
0x1004572f7  mov     r15d, 0FFFEh
0x1004572fd  and     [rcx+2], r15w
0x100457302  call    ?PerformConvertToSsVariant@CXVariant@@QEAAJPEAEKPEBVCTypeInfo@@@Z; CXVariant::PerformConvertToSsVariant(uchar *,ulong,CTypeInfo const *)
0x100457307  mov     [rsp+98h+var_78], eax
0x10045730b  jmp     short loc_100457325
0x10045730d  xor     esi, esi
0x10045730f  mov     r15d, 0FFFEh
0x100457315  mov     rbx, [rsp+98h+arg_0]
0x10045731d  mov     r14, [rsp+98h+arg_18]
0x100457325  mov     rdx, gs:58h
0x10045732e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457335  mov     ecx, [rax]
0x100457337  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045733e  mov     edi, [rax]
0x100457340  add     rdi, [rdx+rcx*8]
0x100457344  mov     rcx, [rdi+100h]
0x10045734b  test    rcx, rcx
0x10045734e  jnz     short loc_10045735D
0x100457350  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457356  mov     rcx, [rdi+100h]
0x10045735d  cmp     dword ptr [rcx+22Ch], 0
0x100457364  jz      short loc_10045736C
0x100457366  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10045736c  mov     edi, [rsp+98h+var_78]
0x100457370  test    edi, edi
0x100457372  jnz     short loc_10045739F
0x100457374  test    byte ptr [rsp+98h+var_40+2], 1
0x100457379  jz      short loc_100457388
0x10045737b  mov     rdx, r14
0x10045737e  lea     rcx, [rsp+98h+var_40]
0x100457383  call    ??$ClearDeep@VCTypeInfo@@@CXVariant@@IEAAXPEBVCTypeInfo@@@Z; CXVariant::ClearDeep<CTypeInfo>(CTypeInfo const *)
0x100457388  mov     dword ptr [rsp+98h+var_40], 3
0x100457390  xorps   xmm0, xmm0
0x100457393  movdqu  [rsp+98h+var_40+8], xmm0
0x100457399  mov     [rsp+98h+var_28], esi
0x10045739d  jmp     short loc_1004573C3
0x10045739f  movups  xmm1, [rsp+98h+var_40]
0x1004573a4  movups  xmmword ptr [rbx], xmm1
0x1004573a7  movups  xmm0, xmmword ptr [rsp+68h]
0x1004573ac  movups  xmmword ptr [rbx+10h], xmm0
0x1004573b0  pextrw  eax, xmm1, 1
0x1004573b5  mov     word ptr [rsp+98h+var_40+2], ax
0x1004573ba  and     ax, r15w
0x1004573be  mov     word ptr [rsp+98h+var_40+2], ax
0x1004573c3  mov     eax, edi
0x1004573c5  lea     r11, [rsp+98h+var_18]
0x1004573cd  mov     rbx, [r11+28h]
0x1004573d1  mov     rsi, [r11+30h]
0x1004573d5  mov     rsp, r11
0x1004573d8  pop     r15
0x1004573da  pop     r14
0x1004573dc  pop     rdi
0x1004573dd  retn
```
