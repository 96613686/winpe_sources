# CASFMetaDataObjectBase::GetDescriptorByName(ushort *,ushort,ushort const *,__MIDL___MIDL_itf_asfv2_0000_0000_0001 *,ulong,uchar *,ulong *,ushort *)

- ea: `0x180025460`
- end: `0x180025759`
- name: `?GetDescriptorByName@CASFMetaDataObjectBase@@UEAAJPEAGGPEBGPEAW4__MIDL___MIDL_itf_asfv2_0000_0000_0001@@KPEAEPEAK0@Z`
- size: `761`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned __int16 *, unsigned __int16, const unsigned __int16 *, enum __MIDL___MIDL_itf_asfv2_0000_0000_0001 *, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180024b8c`
- `0x180025460`
- `0x18003f2a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025546`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025600`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025546`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025600`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::GetDescriptorByName(
        struct IWMSCriticalSection **this,
        unsigned __int16 *a2,
        __int16 a3,
        const unsigned __int16 *a4,
        enum __MIDL___MIDL_itf_asfv2_0000_0000_0001 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        unsigned __int16 *a9)
{
  unsigned __int16 *v9; // r13
  unsigned int v11; // ebx
  int v12; // r12d
  unsigned __int16 v13; // r14
  unsigned __int16 v14; // r15
  __m128i v15; // xmm7
  __m128i v16; // xmm6
  char *v17; // rdi
  unsigned __int16 v18; // bx
  __int64 v19; // rax
  __m128i *v20; // rax
  unsigned int v21; // ecx
  unsigned __int16 v22; // r15
  char *v23; // rax
  unsigned __int16 v24; // bx
  __int64 v25; // rax
  __m128i *v26; // rax
  unsigned int *v27; // rax
  unsigned int v28; // r15d
  unsigned __int16 v29; // bx
  const void *v30; // rdx
  _BYTE v32[8]; // [rsp+28h] [rbp-71h] BYREF
  _BYTE v33[32]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v34[32]; // [rsp+50h] [rbp-49h] BYREF

  v9 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v32, this[4]);
  if ( !this[5] )
  {
    v11 = -1072887818;
LABEL_36:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v32);
    return v11;
  }
  if ( a5 && a8 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    if ( !*((_DWORD *)this + 200) )
    {
LABEL_35:
      v11 = -1072887824;
      goto LABEL_36;
    }
    v17 = (char *)(this + 10);
    while ( !v12 )
    {
      v18 = *v9;
      v17 = (char *)(this + 10);
      if ( *(_WORD *)(CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v33, v14) + 2) == v18
        && *(_WORD *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v34, v14) == a3
        && (v19 = CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v33, v14),
            !(unsigned int)_o__wcsicmp(*(_QWORD *)(v19 + 8), a4)) )
      {
        v20 = (__m128i *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v34, v14);
        v12 = 1;
        v13 = v14;
        v15 = *v20;
        v16 = v20[1];
        v9 = a2;
        *a2 = *(_WORD *)(CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v34, v14) + 2);
      }
      else
      {
        v9 = a2;
      }
      v21 = *((_DWORD *)this + 200);
      if ( ++v14 >= v21 )
      {
        if ( !v12 )
        {
          v22 = 0;
          v23 = (char *)(this + 10);
          if ( !v21 )
            goto LABEL_35;
          while ( !v12 )
          {
            v24 = *v9;
            if ( *(_WORD *)(CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](v23, v34, v22) + 2) != v24
              || (v25 = CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v33, v22),
                  (unsigned int)_o__wcsicmp(*(_QWORD *)(v25 + 8), a4)) )
            {
              v9 = a2;
            }
            else
            {
              v26 = (__m128i *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](v17, v34, v22);
              v13 = v22;
              v12 = 1;
              v15 = *v26;
              v16 = v26[1];
              v9 = a2;
              *a2 = *(_WORD *)(CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](v17, v34, v22) + 2);
            }
            ++v22;
            v23 = (char *)(this + 10);
            if ( (unsigned int)v22 >= *((_DWORD *)this + 200) )
            {
              if ( !v12 )
                goto LABEL_35;
              goto LABEL_23;
            }
          }
        }
        break;
      }
    }
LABEL_23:
    v27 = a8;
    v28 = _mm_cvtsi128_si32(v16);
    *(_DWORD *)a5 = _mm_cvtsi128_si32(_mm_srli_si128(v15, 4));
    *a8 = v28;
    if ( a9 )
    {
      v29 = 0;
      for ( *a9 = 0; v29 < v13; ++v29 )
      {
        if ( *(_WORD *)(CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](v17, v34, v29) + 2) == *v9 )
          ++*a9;
      }
      v27 = a8;
    }
    if ( a7 )
    {
      if ( a6 < *v27 )
      {
        v11 = -1072887855;
        goto LABEL_36;
      }
      v30 = (const void *)_mm_srli_si128(v16, 8).m128i_u64[0];
      if ( v30 )
        memcpy_0(a7, v30, v28);
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v32);
    return 0;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v32);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180025460  mov     rax, rsp
0x180025463  mov     [rax+20h], r9
0x180025467  mov     [rax+18h], r8w
0x18002546c  mov     [rax+10h], rdx
0x180025470  push    rbp
0x180025471  push    rbx
0x180025472  push    rsi
0x180025473  push    rdi
0x180025474  push    r12
0x180025476  push    r13
0x180025478  push    r14
0x18002547a  push    r15
0x18002547c  lea     rbp, [rax-47h]
0x180025480  sub     rsp, 98h
0x180025487  mov     r13, rdx
0x18002548a  movaps  xmmword ptr [rax-58h], xmm6
0x18002548e  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180025492  mov     rsi, rcx
0x180025495  lea     rcx, [rbp+3Fh+var_B0]; this
0x180025499  movaps  xmmword ptr [rax-68h], xmm7
0x18002549d  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800254a2  cmp     qword ptr [rsi+28h], 0
0x1800254a7  jnz     short loc_1800254B3
0x1800254a9  mov     ebx, 0C00D07F6h
0x1800254ae  jmp     loc_18002571D
0x1800254b3  cmp     [rbp+3Fh+arg_20], 0
0x1800254b8  jz      loc_18002572A
0x1800254be  cmp     [rbp+3Fh+arg_38], 0
0x1800254c6  jz      loc_18002572A
0x1800254cc  xor     r12d, r12d
0x1800254cf  xor     r14d, r14d
0x1800254d2  xor     r15d, r15d
0x1800254d5  xorps   xmm7, xmm7
0x1800254d8  xorps   xmm6, xmm6
0x1800254db  cmp     [rsi+320h], r12d
0x1800254e2  jbe     loc_180025718
0x1800254e8  lea     rdi, [rsi+50h]
0x1800254ec  test    r12d, r12d
0x1800254ef  jnz     loc_18002566C
0x1800254f5  movzx   ebx, word ptr [r13+0]
0x1800254fa  lea     rdi, [rsi+50h]
0x1800254fe  movzx   r13d, r15w
0x180025502  lea     rdx, [rbp+3Fh+var_A8]
0x180025506  mov     r8d, r13d
0x180025509  mov     rcx, rdi
0x18002550c  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025511  cmp     [rax+2], bx
0x180025515  jnz     short loc_18002558E
0x180025517  mov     r8d, r13d
0x18002551a  lea     rdx, [rbp+3Fh+var_88]
0x18002551e  mov     rcx, rdi
0x180025521  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025526  movzx   ecx, [rbp+3Fh+arg_10]
0x18002552a  cmp     [rax], cx
0x18002552d  jnz     short loc_18002558E
0x18002552f  mov     r8d, r13d
0x180025532  lea     rdx, [rbp+3Fh+var_A8]
0x180025536  mov     rcx, rdi
0x180025539  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x18002553e  mov     rdx, [rbp+3Fh+arg_18]
0x180025542  mov     rcx, [rax+8]
0x180025546  call    cs:__imp__o__wcsicmp
0x18002554c  test    eax, eax
0x18002554e  jnz     short loc_18002558E
0x180025550  mov     r8d, r13d
0x180025553  lea     rdx, [rbp+3Fh+var_88]
0x180025557  mov     rcx, rdi
0x18002555a  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x18002555f  mov     r8d, r13d
0x180025562  lea     rdx, [rbp+3Fh+var_88]
0x180025566  mov     rcx, rdi
0x180025569  mov     r12d, 1
0x18002556f  movzx   r14d, r15w
0x180025573  movups  xmm7, xmmword ptr [rax]
0x180025576  movups  xmm6, xmmword ptr [rax+10h]
0x18002557a  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x18002557f  mov     r13, [rbp+3Fh+arg_8]
0x180025583  movzx   ecx, word ptr [rax+2]
0x180025587  mov     [r13+0], cx
0x18002558c  jmp     short loc_180025592
0x18002558e  mov     r13, [rbp+3Fh+arg_8]
0x180025592  mov     ecx, [rsi+320h]
0x180025598  inc     r15w
0x18002559c  movzx   eax, r15w
0x1800255a0  cmp     eax, ecx
0x1800255a2  jb      loc_1800254EC
0x1800255a8  test    r12d, r12d
0x1800255ab  jnz     loc_18002566C
0x1800255b1  xor     r15d, r15d
0x1800255b4  mov     rax, rdi
0x1800255b7  test    ecx, ecx
0x1800255b9  jz      loc_180025718
0x1800255bf  test    r12d, r12d
0x1800255c2  jnz     loc_18002566C
0x1800255c8  movzx   ebx, word ptr [r13+0]
0x1800255cd  lea     rdx, [rbp+3Fh+var_88]
0x1800255d1  movzx   r13d, r15w
0x1800255d5  mov     rcx, rax
0x1800255d8  mov     r8d, r13d
0x1800255db  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x1800255e0  cmp     [rax+2], bx
0x1800255e4  jnz     short loc_180025648
0x1800255e6  mov     rbx, rdi
0x1800255e9  lea     rdx, [rbp+3Fh+var_A8]
0x1800255ed  mov     rcx, rbx
0x1800255f0  mov     r8d, r13d
0x1800255f3  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x1800255f8  mov     rdx, [rbp+3Fh+arg_18]
0x1800255fc  mov     rcx, [rax+8]
0x180025600  call    cs:__imp__o__wcsicmp
0x180025606  test    eax, eax
0x180025608  jnz     short loc_180025648
0x18002560a  mov     r8d, r13d
0x18002560d  lea     rdx, [rbp+3Fh+var_88]
0x180025611  mov     rcx, rbx
0x180025614  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025619  mov     r8d, r13d
0x18002561c  lea     rdx, [rbp+3Fh+var_88]
0x180025620  mov     rcx, rbx
0x180025623  movzx   r14d, r15w
0x180025627  mov     r12d, 1
0x18002562d  movups  xmm7, xmmword ptr [rax]
0x180025630  movups  xmm6, xmmword ptr [rax+10h]
0x180025634  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025639  mov     r13, [rbp+3Fh+arg_8]
0x18002563d  movzx   ecx, word ptr [rax+2]
0x180025641  mov     [r13+0], cx
0x180025646  jmp     short loc_18002564C
0x180025648  mov     r13, [rbp+3Fh+arg_8]
0x18002564c  inc     r15w
0x180025650  movzx   eax, r15w
0x180025654  cmp     eax, [rsi+320h]
0x18002565a  mov     rax, rdi
0x18002565d  jb      loc_1800255BF
0x180025663  test    r12d, r12d
0x180025666  jz      loc_180025718
0x18002566c  mov     rcx, [rbp+3Fh+arg_20]
0x180025670  mov     rax, [rbp+3Fh+arg_38]
0x180025677  mov     rsi, [rbp+3Fh+arg_40]
0x18002567e  movd    r15d, xmm6
0x180025683  psrldq  xmm7, 4
0x180025688  movd    dword ptr [rcx], xmm7
0x18002568c  mov     [rax], r15d
0x18002568f  mov     [rbp+3Fh+arg_0], r15d
0x180025693  test    rsi, rsi
0x180025696  jz      short loc_1800256DD
0x180025698  xor     eax, eax
0x18002569a  xor     ebx, ebx
0x18002569c  mov     [rsi], ax
0x18002569f  cmp     ax, r14w
0x1800256a3  jnb     short loc_1800256D6
0x1800256a5  lea     r15d, [rax+1]
0x1800256a9  movzx   r8d, bx
0x1800256ad  lea     rdx, [rbp+3Fh+var_88]
0x1800256b1  mov     rcx, rdi
0x1800256b4  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x1800256b9  movzx   ecx, word ptr [rax+2]
0x1800256bd  cmp     cx, [r13+0]
0x1800256c2  jnz     short loc_1800256C8
0x1800256c4  add     [rsi], r15w
0x1800256c8  add     bx, r15w
0x1800256cc  cmp     bx, r14w
0x1800256d0  jb      short loc_1800256A9
0x1800256d2  mov     r15d, [rbp+3Fh+arg_0]
0x1800256d6  mov     rax, [rbp+3Fh+arg_38]
0x1800256dd  mov     rcx, [rbp+3Fh+arg_30]; void *
0x1800256e1  test    rcx, rcx
0x1800256e4  jz      short loc_18002570B
0x1800256e6  mov     eax, [rax]
0x1800256e8  cmp     [rbp+3Fh+arg_28], eax
0x1800256eb  jnb     short loc_1800256F4
0x1800256ed  mov     ebx, 0C00D07D1h
0x1800256f2  jmp     short loc_18002571D
0x1800256f4  psrldq  xmm6, 8
0x1800256f9  movq    rdx, xmm6; Src
0x1800256fe  test    rdx, rdx
0x180025701  jz      short loc_18002570B
0x180025703  mov     r8d, r15d; Size
0x180025706  call    memcpy_0
0x18002570b  lea     rcx, [rbp+3Fh+var_B0]; this
0x18002570f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025714  xor     eax, eax
0x180025716  jmp     short loc_180025738
0x180025718  mov     ebx, 0C00D07F0h
0x18002571d  lea     rcx, [rbp+3Fh+var_B0]; this
0x180025721  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025726  mov     eax, ebx
0x180025728  jmp     short loc_180025738
0x18002572a  lea     rcx, [rbp+3Fh+var_B0]; this
0x18002572e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025733  mov     eax, 80070057h
0x180025738  movaps  xmm6, [rsp+0D0h+var_58+8]
0x180025740  movaps  xmm7, [rsp+0D0h+var_68+8]
0x180025745  add     rsp, 98h
0x18002574c  pop     r15
0x18002574e  pop     r14
0x180025750  pop     r13
0x180025752  pop     r12
0x180025754  pop     rdi
0x180025755  pop     rsi
0x180025756  pop     rbx
0x180025757  pop     rbp
0x180025758  retn
```
