# CXVariant::ConvertToR8ForHistogram(CTypeInfo const *)

- ea: `0x1004110d0`
- end: `0x1004111c0`
- name: `?ConvertToR8ForHistogram@CXVariant@@QEAAJPEBVCTypeInfo@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CXVariant *__hidden this, const struct CTypeInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10040d470`
- `0x1004110d0`
- `0x1004111d0`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10045724c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10045724c`
- `sqldk!SystemThread_TlsIndex` at `0x100411143`
- `sqldk!SystemThread_TlsOffset` at `0x10041114c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457239`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457239`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXVariant::ConvertToR8ForHistogram(__m256i *this, const struct CTypeInfo *a2)
{
  const struct CTypeInfo *v2; // r14
  __m256i *v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rcx
  __m128i v7; // xmm1
  __m128i v8; // xmm1
  const struct SQLError *CurrentException; // rax
  unsigned int v10; // [rsp+20h] [rbp-78h]
  _BYTE v11[16]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v12[24]; // [rsp+40h] [rbp-58h] BYREF
  __m256i v13; // [rsp+58h] [rbp-40h] BYREF

  v2 = a2;
  v3 = this;
  v13.m256i_i32[0] = 3;
  memset(&v13.m256i_u64[1], 0, 20);
  v13 = *this;
  this->m256i_i16[1] &= ~1u;
  try
  {
    v10 = CXVariant::PerformConvertToR8((CXVariant *)this, a2);
  }
  catch ( SQLError v12 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v11, (const struct SQLError *)v12);
      v8 = *(__m128i *)v13.m256i_i8;
      *this = v13;
      v13.m256i_i16[1] = _mm_extract_epi16(v8, 1) & 0xFFFE;
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v11);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v11);
    }
    catch ( ShortStackException )
    {
    }
    v3 = this;
    v2 = a2;
  }
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  if ( *(_DWORD *)(v5 + 556) )
    ExceptionPostCatchActions((struct Worker *)v5);
  if ( v10 )
  {
    v7 = *(__m128i *)v13.m256i_i8;
    *v3 = v13;
    v13.m256i_i16[1] = _mm_extract_epi16(v7, 1) & 0xFFFE;
  }
  else
  {
    if ( (v13.m256i_i8[2] & 1) != 0 )
      CXVariant::ClearDeep<CTypeInfo>(&v13, v2);
    v13.m256i_i32[0] = 3;
    memset(&v13.m256i_u64[1], 0, 20);
  }
  return v10;
}

```

## disassembly

```asm
0x1004110d0  mov     rax, rsp
0x1004110d3  mov     [rax+10h], rdx
0x1004110d7  mov     [rax+8], rcx
0x1004110db  push    rdi
0x1004110dc  push    r14
0x1004110de  push    r15
0x1004110e0  sub     rsp, 80h
0x1004110e7  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFEh
0x1004110ef  mov     [rax+18h], rbx
0x1004110f3  mov     [rax+20h], rsi
0x1004110f7  mov     r14, rdx
0x1004110fa  mov     rbx, rcx
0x1004110fd  xor     edi, edi
0x1004110ff  mov     [rax-78h], edi
0x100411102  mov     dword ptr [rax-40h], 3
0x100411109  xorps   xmm0, xmm0
0x10041110c  movdqu  xmmword ptr [rax-38h], xmm0
0x100411111  mov     [rax-28h], edi
0x100411114  movups  xmm0, xmmword ptr [rcx]
0x100411117  movups  xmmword ptr [rax-40h], xmm0
0x10041111b  movups  xmm1, xmmword ptr [rcx+10h]
0x10041111f  movups  xmmword ptr [rax-30h], xmm1
0x100411123  mov     r15d, 0FFFEh
0x100411129  and     [rcx+2], r15w
0x10041112e  call    ?PerformConvertToR8@CXVariant@@QEAAJPEBVCTypeInfo@@@Z; CXVariant::PerformConvertToR8(CTypeInfo const *)
0x100411133  mov     [rsp+98h+var_78], eax
0x100411137  jmp     short loc_10041113A
0x10041113a  mov     rdx, gs:58h
0x100411143  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041114a  mov     ecx, [rax]
0x10041114c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100411153  mov     esi, [rax]
0x100411155  add     rsi, [rdx+rcx*8]
0x100411159  mov     rcx, [rsi+100h]
0x100411160  test    rcx, rcx
0x100411163  jz      loc_100457239
0x100411169  cmp     dword ptr [rcx+22Ch], 0
0x100411170  jnz     loc_10045724C
0x100411176  mov     esi, [rsp+98h+var_78]
0x10041117a  test    esi, esi
0x10041117c  jnz     loc_10045726D
0x100411182  test    byte ptr [rsp+98h+var_40+2], 1
0x100411187  jnz     loc_100457259
0x10041118d  mov     dword ptr [rsp+98h+var_40], 3
0x100411195  xorps   xmm0, xmm0
0x100411198  movdqu  [rsp+98h+var_40+8], xmm0
0x10041119e  mov     [rsp+98h+var_28], edi
0x1004111a2  jmp     short loc_1004111A5
0x1004111a5  mov     eax, esi
0x1004111a7  lea     r11, [rsp+98h+var_18]
0x1004111af  mov     rbx, [r11+30h]
0x1004111b3  mov     rsi, [r11+38h]
0x1004111b7  mov     rsp, r11
0x1004111ba  pop     r15
0x1004111bc  pop     r14
0x1004111be  pop     rdi
0x1004111bf  retn
0x10045721b  xor     edi, edi
0x10045721d  mov     r15d, 0FFFEh
0x100457223  mov     rbx, [rsp+98h+arg_0]
0x10045722b  mov     r14, [rsp+98h+arg_8]
0x100457233  jmp     loc_10041113A
0x100457239  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10045723f  mov     rcx, [rsi+100h]
0x100457246  jmp     loc_100411169
0x10045724c  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100457252  nop
0x100457253  jmp     loc_100411176
0x100457259  mov     rdx, r14
0x10045725c  lea     rcx, [rsp+98h+var_40]
0x100457261  call    ??$ClearDeep@VCTypeInfo@@@CXVariant@@IEAAXPEBVCTypeInfo@@@Z; CXVariant::ClearDeep<CTypeInfo>(CTypeInfo const *)
0x100457266  nop
0x100457267  jmp     loc_10041118D
0x10045726d  movups  xmm1, [rsp+98h+var_40]
0x100457272  movups  xmmword ptr [rbx], xmm1
0x100457275  movups  xmm0, xmmword ptr [rsp+68h]
0x10045727a  movups  xmmword ptr [rbx+10h], xmm0
0x10045727e  pextrw  eax, xmm1, 1
0x100457283  mov     word ptr [rsp+98h+var_40+2], ax
0x100457288  and     ax, r15w
0x10045728c  mov     word ptr [rsp+98h+var_40+2], ax
0x100457291  jmp     loc_1004111A5
```
