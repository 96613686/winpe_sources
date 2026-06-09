# CXVariant::ConvertToNm(CTypeInfo const *,uchar,uchar,bool,uint)

- ea: `0x1004570c0`
- end: `0x10045721b`
- name: `?ConvertToNm@CXVariant@@QEAAJPEBVCTypeInfo@@EE_NI@Z`
- size: `347`
- prototype: `__int64 __fastcall(CXVariant *__hidden this, const struct CTypeInfo *, unsigned __int8, unsigned __int8, bool, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100407540`
- `0x10040d470`
- `0x1004570c0`

## import_xrefs

- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004571a0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x1004571a0`
- `sqldk!SystemThread_TlsIndex` at `0x100457168`
- `sqldk!SystemThread_TlsOffset` at `0x100457171`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045718a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10045718a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXVariant::ConvertToNm(
        __m256i *this,
        const struct CTypeInfo *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        bool a5,
        unsigned int a6)
{
  const struct CTypeInfo *v6; // r14
  __m256i *v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rcx
  __m128i v10; // xmm1
  __m128i v12; // xmm1
  const struct SQLError *CurrentException; // rax
  unsigned int v14; // [rsp+30h] [rbp-78h]
  _BYTE v15[16]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-58h] BYREF
  __m256i v17; // [rsp+68h] [rbp-40h] BYREF

  v6 = a2;
  v7 = this;
  v17.m256i_i32[0] = 3;
  memset(&v17.m256i_u64[1], 0, 20);
  v17 = *this;
  this->m256i_i16[1] &= ~1u;
  try
  {
    v14 = CXVariant::PerformConvertToNm((CXVariant *)this, *(_BYTE *)a2, a3, a4, a5, a6);
  }
  catch ( SQLError v16 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v15, (const struct SQLError *)v16);
      v12 = *(__m128i *)v17.m256i_i8;
      *this = v17;
      v17.m256i_i16[1] = _mm_extract_epi16(v12, 1) & 0xFFFE;
      CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v15);
      ExceptionRethrow(CurrentException);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v15);
    }
    catch ( ShortStackException )
    {
    }
    v7 = this;
    v6 = a2;
  }
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v9 = *(_QWORD *)(v8 + 256);
  if ( !v9 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v9 = *(_QWORD *)(v8 + 256);
  }
  if ( *(_DWORD *)(v9 + 556) )
    ExceptionPostCatchActions((struct Worker *)v9);
  if ( v14 )
  {
    v10 = *(__m128i *)v17.m256i_i8;
    *v7 = v17;
    v17.m256i_i16[1] = _mm_extract_epi16(v10, 1) & 0xFFFE;
  }
  else
  {
    if ( (v17.m256i_i8[2] & 1) != 0 )
      CXVariant::ClearDeep<CTypeInfo>(&v17, v6);
    v17.m256i_i32[0] = 3;
    memset(&v17.m256i_u64[1], 0, 20);
  }
  return v14;
}

```

## disassembly

```asm
0x1004570c0  mov     rax, rsp
0x1004570c3  mov     [rax+10h], rdx
0x1004570c7  mov     [rax+8], rcx
0x1004570cb  push    rdi
0x1004570cc  push    r14
0x1004570ce  push    r15
0x1004570d0  sub     rsp, 90h
0x1004570d7  mov     qword ptr [rax-70h], 0FFFFFFFFFFFFFFFEh
0x1004570df  mov     [rax+18h], rbx
0x1004570e3  mov     [rax+20h], rsi
0x1004570e7  mov     r14, rdx
0x1004570ea  mov     rbx, rcx
0x1004570ed  mov     dword ptr [rax-78h], 64h ; 'd'
0x1004570f4  xor     esi, esi
0x1004570f6  mov     dword ptr [rax-40h], 3
0x1004570fd  xorps   xmm0, xmm0
0x100457100  movdqu  xmmword ptr [rax-38h], xmm0
0x100457105  mov     [rax-28h], esi
0x100457108  movups  xmm0, xmmword ptr [rcx]
0x10045710b  movups  xmmword ptr [rax-40h], xmm0
0x10045710f  movups  xmm1, xmmword ptr [rcx+10h]
0x100457113  movups  xmmword ptr [rax-30h], xmm1
0x100457117  mov     r15d, 0FFFEh
0x10045711d  and     [rcx+2], r15w
0x100457122  mov     eax, [rsp+0A8h+arg_28]
0x100457129  mov     [rsp+0A8h+var_80], eax; unsigned int
0x10045712d  movzx   eax, [rsp+0A8h+arg_20]
0x100457135  mov     [rsp+0A8h+var_88], al; bool
0x100457139  movzx   edx, byte ptr [rdx]; unsigned __int8
0x10045713c  call    ?PerformConvertToNm@CXVariant@@QEAAJEEE_NI@Z; CXVariant::PerformConvertToNm(uchar,uchar,uchar,bool,uint)
0x100457141  mov     [rsp+0A8h+var_78], eax
0x100457145  jmp     short loc_10045715F
0x100457147  xor     esi, esi
0x100457149  mov     r15d, 0FFFEh
0x10045714f  mov     rbx, [rsp+0A8h+arg_0]
0x100457157  mov     r14, [rsp+0A8h+arg_8]
0x10045715f  mov     rdx, gs:58h
0x100457168  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045716f  mov     ecx, [rax]
0x100457171  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100457178  mov     edi, [rax]
0x10045717a  add     rdi, [rdx+rcx*8]
0x10045717e  mov     rcx, [rdi+100h]
0x100457185  test    rcx, rcx
0x100457188  jnz     short loc_100457197
0x10045718a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457190  mov     rcx, [rdi+100h]
0x100457197  cmp     dword ptr [rcx+22Ch], 0
0x10045719e  jz      short loc_1004571A6
0x1004571a0  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x1004571a6  mov     edi, [rsp+0A8h+var_78]
0x1004571aa  test    edi, edi
0x1004571ac  jnz     short loc_1004571DC
0x1004571ae  test    byte ptr [rsp+0A8h+var_40+2], 1
0x1004571b3  jz      short loc_1004571C2
0x1004571b5  mov     rdx, r14
0x1004571b8  lea     rcx, [rsp+0A8h+var_40]
0x1004571bd  call    ??$ClearDeep@VCTypeInfo@@@CXVariant@@IEAAXPEBVCTypeInfo@@@Z; CXVariant::ClearDeep<CTypeInfo>(CTypeInfo const *)
0x1004571c2  mov     dword ptr [rsp+0A8h+var_40], 3
0x1004571ca  xorps   xmm0, xmm0
0x1004571cd  movdqu  [rsp+0A8h+var_40+8], xmm0
0x1004571d3  mov     [rsp+0A8h+var_28], esi
0x1004571da  jmp     short loc_100457200
0x1004571dc  movups  xmm1, [rsp+0A8h+var_40]
0x1004571e1  movups  xmmword ptr [rbx], xmm1
0x1004571e4  movups  xmm0, xmmword ptr [rsp+78h]
0x1004571e9  movups  xmmword ptr [rbx+10h], xmm0
0x1004571ed  pextrw  eax, xmm1, 1
0x1004571f2  mov     word ptr [rsp+0A8h+var_40+2], ax
0x1004571f7  and     ax, r15w
0x1004571fb  mov     word ptr [rsp+0A8h+var_40+2], ax
0x100457200  mov     eax, edi
0x100457202  lea     r11, [rsp+0A8h+var_18]
0x10045720a  mov     rbx, [r11+30h]
0x10045720e  mov     rsi, [r11+38h]
0x100457212  mov     rsp, r11
0x100457215  pop     r15
0x100457217  pop     r14
0x100457219  pop     rdi
0x10045721a  retn
```
