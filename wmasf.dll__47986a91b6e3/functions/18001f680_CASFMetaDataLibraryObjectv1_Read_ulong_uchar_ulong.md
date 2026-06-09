# CASFMetaDataLibraryObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18001f680`
- end: `0x18001fb0e`
- name: `?Read@CASFMetaDataLibraryObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `1166`
- prototype: `int(CASFMetaDataLibraryObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18000da0c`
- `0x18001f680`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMetaDataLibraryObjectv1::Read(
        CASFMetaDataLibraryObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  struct IWMSCriticalSection *v6; // rdx
  int v9; // edi
  __int128 v10; // xmm0
  unsigned __int64 v11; // rcx
  int v12; // edx
  unsigned __int16 v13; // cx
  int v14; // ebx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r8d
  __int16 *v18; // r11
  __int16 v19; // cx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // r10d
  __int64 v28; // r11
  unsigned __int64 v29; // r13
  __int16 v30; // r10
  size_t v31; // r10
  _WORD *v32; // rax
  _WORD *v33; // r15
  void *v34; // rsi
  size_t v35; // r8
  unsigned __int64 v36; // rbx
  char *v37; // r13
  char *v38; // rdx
  void *v39; // rax
  void *v40; // rcx
  int (__fastcall ***v41)(_QWORD, GUID *, char **); // rcx
  unsigned int v42; // ebx
  unsigned int v44; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int16 v45; // [rsp+34h] [rbp-65h]
  int v46; // [rsp+38h] [rbp-61h]
  size_t Size; // [rsp+40h] [rbp-59h]
  unsigned __int64 v48; // [rsp+48h] [rbp-51h]
  __int128 v49; // [rsp+50h] [rbp-49h]
  __int128 v50; // [rsp+60h] [rbp-39h]
  int v51; // [rsp+70h] [rbp-29h]
  char v52[8]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int8 *v53; // [rsp+80h] [rbp-19h]
  _OWORD v54[2]; // [rsp+90h] [rbp-9h] BYREF
  char *v55; // [rsp+B0h] [rbp+17h] BYREF

  v4 = a2;
  v6 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v53 = a3;
  v51 = v4;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v52, v6);
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = -1072887818;
    goto LABEL_66;
  }
  if ( !a4 )
    goto LABEL_67;
  if ( !(_DWORD)v4 )
  {
LABEL_64:
    *a4 = 26;
    goto LABEL_65;
  }
  if ( !a3 )
  {
LABEL_67:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v52);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_64;
  v9 = (*(__int64 (__fastcall **)(CASFMetaDataLibraryObjectv1 *))(*(_QWORD *)this + 128LL))(this);
  if ( v9 < 0 )
    goto LABEL_66;
  v10 = *(_OWORD *)a3;
  v44 = 24;
  *((_OWORD *)this + 3) = v10;
  v11 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v11;
  if ( v11 >= 0x100000000LL )
  {
    v9 = -1072887821;
    goto LABEL_66;
  }
  if ( v4 < v11 )
  {
    *a4 = *((_DWORD *)this + 16);
LABEL_65:
    v9 = -1072887855;
    goto LABEL_66;
  }
  v9 = -1072887855;
  if ( (unsigned int)CHECK_FOR_SPACE(&v44, 2u, v4) == -1072887855 )
  {
LABEL_58:
    *a4 = v44;
    goto LABEL_66;
  }
  v13 = *((_WORD *)a3 + 12);
  v45 = v13;
  v14 = v12 - 1;
  v55 = (char *)(a3 + 26);
  v15 = 0;
  while ( 1 )
  {
    v46 = v15;
    if ( (unsigned __int16)v15 >= v13 )
    {
      v41 = (int (__fastcall ***)(_QWORD, GUID *, char **))*((_QWORD *)this + 5);
      v42 = v44;
      if ( v41 )
      {
        v55 = 0;
        if ( (**v41)(v41, &IID_IASFReadWriteTracker, &v55) >= 0 )
        {
          (*(void (__fastcall **)(char *, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v55 + 72LL))(
            v55,
            v53,
            v42,
            (char *)this + 48);
          if ( v55 )
            (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
        }
      }
      *a4 = v42;
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v52);
      return 0;
    }
    v16 = CHECK_FOR_SPACE(&v44, 8u, v4);
    if ( v16 == -1072887855 )
      goto LABEL_58;
    v19 = *v18;
    v20 = (unsigned __int16)v18[3];
    v49 = 0;
    LOWORD(v49) = v19;
    WORD1(v49) = v18[1];
    v50 = 0;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          v23 = v22 - 1;
          if ( v23 )
          {
            v24 = v23 - 1;
            if ( v24 )
            {
              v25 = v24 - 1;
              if ( v25 )
              {
                if ( v25 != 1 )
                {
                  v16 = -1072887838;
LABEL_50:
                  v9 = v16;
                  goto LABEL_66;
                }
                v14 = 6;
              }
              else
              {
                v14 = 5;
              }
            }
            else
            {
              v14 = 4;
            }
          }
          else
          {
            v14 = 2;
          }
        }
        else
        {
          v14 = 3;
        }
      }
      else
      {
        v14 = 0;
      }
    }
    DWORD1(v49) = v14;
    if ( v16 < 0 )
      goto LABEL_50;
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, 4u, v17) == -1072887855 )
      goto LABEL_58;
    v29 = *(unsigned int *)(v28 + 8);
    LODWORD(v50) = *(_DWORD *)(v28 + 8);
    if ( v27 && v27 != (_DWORD)v29 )
      goto LABEL_52;
    v30 = *(_WORD *)(v28 + 4);
    if ( (v30 & 1) != 0 || !v30 )
      goto LABEL_52;
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, *(unsigned __int16 *)(v28 + 4), v26) == -1072887855 )
      goto LABEL_58;
    Size = v31;
    v48 = (unsigned __int64)(unsigned int)v31 >> 1;
    v32 = operator new[](saturated_mul(v48, 2u));
    *((_QWORD *)&v49 + 1) = v32;
    v33 = v32;
    if ( !v32 )
      goto LABEL_56;
    v55 += 12;
    memcpy_0(v32, v55, Size);
    v33[v48 - 1] = 0;
    if ( (unsigned int)CHECK_FOR_SPACE(&v44, v29, v4) == -1072887855 )
    {
      operator delete(v33);
      goto LABEL_58;
    }
    if ( v14 == 3 )
    {
      *((_QWORD *)&v50 + 1) = operator new[](4u);
      v34 = (void *)*((_QWORD *)&v50 + 1);
      if ( !*((_QWORD *)&v50 + 1) )
        break;
      v35 = v29;
      v36 = v29;
      v37 = &v55[Size];
      v38 = &v55[Size];
      **((_DWORD **)&v50 + 1) = 0;
      memcpy_0(v34, v38, v35);
      LODWORD(v50) = 4;
      v55 = &v37[v36];
LABEL_41:
      v14 = 1;
      goto LABEL_42;
    }
    v39 = operator new[](v29);
    *((_QWORD *)&v50 + 1) = v39;
    v34 = v39;
    if ( !v39 )
      break;
    memcpy_0(v39, &v55[Size], v29);
    v55 += v29 + Size;
    if ( v14 != 1 )
      goto LABEL_41;
    if ( (v29 & 1) != 0 )
    {
      operator delete(v33);
      operator delete(v34);
LABEL_52:
      v9 = -1072887838;
      goto LABEL_66;
    }
    if ( (_DWORD)v29 )
      *((_WORD *)v34 + (v29 >> 1) - 1) = 0;
LABEL_42:
    v54[0] = v49;
    v54[1] = v50;
    if ( !(unsigned int)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add((char *)this + 80, v54) )
    {
      operator delete(v33);
      v40 = v34;
      goto LABEL_55;
    }
    HIWORD(v15) = HIWORD(v46);
    LODWORD(v4) = v51;
    LOWORD(v15) = v46 + 1;
    v13 = v45;
  }
  v40 = v33;
LABEL_55:
  operator delete(v40);
LABEL_56:
  v9 = -2147024882;
LABEL_66:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v52);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f680  mov     [rsp-8+arg_8], rbx
0x18001f685  push    rbp
0x18001f686  push    rsi
0x18001f687  push    rdi
0x18001f688  push    r12
0x18001f68a  push    r13
0x18001f68c  push    r14
0x18001f68e  push    r15
0x18001f690  lea     rbp, [rsp-27h]
0x18001f695  sub     rsp, 0C0h
0x18001f69c  mov     rax, cs:__security_cookie
0x18001f6a3  xor     rax, rsp
0x18001f6a6  mov     [rbp+57h+var_38], rax
0x18001f6aa  mov     esi, edx
0x18001f6ac  mov     r14, rcx
0x18001f6af  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001f6b3  mov     r12, r9
0x18001f6b6  lea     rcx, [rbp+57h+var_78]; this
0x18001f6ba  mov     [rbp+57h+var_70], r8
0x18001f6be  mov     r15, r8
0x18001f6c1  mov     [rbp+57h+var_80], esi
0x18001f6c4  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001f6c9  cmp     qword ptr [r14+28h], 0
0x18001f6ce  jnz     short loc_18001F6DA
0x18001f6d0  mov     edi, 0C00D07F6h
0x18001f6d5  jmp     loc_18001FACC
0x18001f6da  test    r12, r12
0x18001f6dd  jz      loc_18001FAD9
0x18001f6e3  test    esi, esi
0x18001f6e5  jz      loc_18001FABF
0x18001f6eb  test    r15, r15
0x18001f6ee  jz      loc_18001FAD9
0x18001f6f4  cmp     esi, 1Ah
0x18001f6f7  jb      loc_18001FABF
0x18001f6fd  mov     rax, [r14]
0x18001f700  mov     rcx, r14
0x18001f703  mov     rax, [rax+80h]
0x18001f70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f70f  mov     edi, eax
0x18001f711  test    eax, eax
0x18001f713  js      loc_18001FACC
0x18001f719  movups  xmm0, xmmword ptr [r15]
0x18001f71d  mov     rax, 100000000h
0x18001f727  mov     [rbp+57h+var_C0], 18h
0x18001f72e  movdqu  xmmword ptr [r14+30h], xmm0
0x18001f734  mov     rcx, [r15+10h]
0x18001f738  mov     [r14+40h], rcx
0x18001f73c  cmp     rcx, rax
0x18001f73f  jb      short loc_18001F74B
0x18001f741  mov     edi, 0C00D07F3h
0x18001f746  jmp     loc_18001FACC
0x18001f74b  cmp     rsi, rcx
0x18001f74e  jnb     short loc_18001F75D
0x18001f750  mov     eax, [r14+40h]
0x18001f754  mov     [r12], eax
0x18001f758  jmp     loc_18001FAC7
0x18001f75d  mov     r8d, esi; unsigned int
0x18001f760  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001f764  mov     edx, 2; unsigned int
0x18001f769  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001f76e  mov     edi, 0C00D07D1h
0x18001f773  cmp     eax, edi
0x18001f775  jz      loc_18001FA47
0x18001f77b  movzx   ecx, word ptr [r15+18h]
0x18001f780  lea     r11, [r15+1Ah]
0x18001f784  mov     [rbp+57h+var_BC], cx
0x18001f788  lea     ebx, [rdx-1]
0x18001f78b  mov     [rbp+57h+var_40], r11
0x18001f78f  xor     eax, eax
0x18001f791  mov     [rbp+57h+var_B8], eax
0x18001f794  cmp     ax, cx
0x18001f797  jnb     loc_18001FA50
0x18001f79d  mov     r8d, esi; unsigned int
0x18001f7a0  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001f7a4  mov     edx, 8; unsigned int
0x18001f7a9  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001f7ae  cmp     eax, edi
0x18001f7b0  jz      loc_18001FA47
0x18001f7b6  movzx   ecx, word ptr [r11]
0x18001f7ba  xorps   xmm0, xmm0
0x18001f7bd  movzx   edx, word ptr [r11+6]
0x18001f7c2  xor     r10d, r10d
0x18001f7c5  movups  [rbp+57h+var_A0], xmm0
0x18001f7c9  mov     word ptr [rbp+57h+var_A0], cx
0x18001f7cd  movzx   ecx, word ptr [r11+2]
0x18001f7d2  mov     word ptr [rbp+57h+var_A0+2], cx
0x18001f7d6  movups  [rbp+57h+var_90], xmm0
0x18001f7da  test    edx, edx
0x18001f7dc  jz      short loc_18001F835
0x18001f7de  sub     edx, 1
0x18001f7e1  jz      short loc_18001F833
0x18001f7e3  sub     edx, 1
0x18001f7e6  jz      short loc_18001F82C
0x18001f7e8  sub     edx, 1
0x18001f7eb  jz      short loc_18001F821
0x18001f7ed  sub     edx, 1
0x18001f7f0  jz      short loc_18001F816
0x18001f7f2  sub     edx, 1
0x18001f7f5  jz      short loc_18001F809
0x18001f7f7  cmp     edx, 1
0x18001f7fa  jnz     loc_18001F9FA
0x18001f800  lea     ebx, [rdx+5]
0x18001f803  lea     r10d, [rdx+0Fh]
0x18001f807  jmp     short loc_18001F835
0x18001f809  mov     ebx, 5
0x18001f80e  mov     r10d, 2
0x18001f814  jmp     short loc_18001F835
0x18001f816  mov     ebx, 4
0x18001f81b  lea     r10d, [rbx+4]
0x18001f81f  jmp     short loc_18001F835
0x18001f821  mov     ebx, 2
0x18001f826  lea     r10d, [rbx+2]
0x18001f82a  jmp     short loc_18001F835
0x18001f82c  mov     ebx, 3
0x18001f831  jmp     short loc_18001F80E
0x18001f833  xor     ebx, ebx
0x18001f835  mov     dword ptr [rbp+57h+var_A0+4], ebx
0x18001f838  test    eax, eax
0x18001f83a  js      loc_18001F9FF
0x18001f840  mov     edx, 4; unsigned int
0x18001f845  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001f849  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001f84e  cmp     eax, edi
0x18001f850  jz      loc_18001FA47
0x18001f856  mov     r13d, [r11+8]
0x18001f85a  mov     dword ptr [rbp+57h+var_90], r13d
0x18001f85e  test    r10d, r10d
0x18001f861  jz      short loc_18001F86C
0x18001f863  cmp     r10d, r13d
0x18001f866  jnz     loc_18001FA16
0x18001f86c  movzx   r10d, word ptr [r11+4]
0x18001f871  test    r10b, 1
0x18001f875  jnz     loc_18001FA16
0x18001f87b  xor     eax, eax
0x18001f87d  cmp     ax, r10w
0x18001f881  jz      loc_18001FA16
0x18001f887  mov     edx, r10d; unsigned int
0x18001f88a  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001f88e  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001f893  cmp     eax, edi
0x18001f895  jz      loc_18001FA47
0x18001f89b  mov     ecx, r10d
0x18001f89e  mov     [rbp+57h+Size], r10
0x18001f8a2  shr     rcx, 1
0x18001f8a5  mov     eax, 2
0x18001f8aa  mul     rcx
0x18001f8ad  mov     [rbp+57h+var_A8], rcx
0x18001f8b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f8b8  cmovb   rax, rcx
0x18001f8bc  mov     rcx, rax; unsigned __int64
0x18001f8bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f8c4  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001f8c8  mov     r15, rax
0x18001f8cb  test    rax, rax
0x18001f8ce  jz      loc_18001FA35
0x18001f8d4  mov     rax, [rbp+57h+var_40]
0x18001f8d8  mov     rcx, r15; void *
0x18001f8db  mov     r8, [rbp+57h+Size]; Size
0x18001f8df  add     rax, 0Ch
0x18001f8e3  mov     rdx, rax; Src
0x18001f8e6  mov     [rbp+57h+var_40], rax
0x18001f8ea  call    memcpy_0
0x18001f8ef  mov     rcx, [rbp+57h+var_A8]
0x18001f8f3  xor     eax, eax
0x18001f8f5  mov     r8d, esi; unsigned int
0x18001f8f8  mov     edx, r13d; unsigned int
0x18001f8fb  mov     [r15+rcx*2-2], ax
0x18001f901  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x18001f905  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001f90a  cmp     eax, edi
0x18001f90c  jz      loc_18001FA3F
0x18001f912  cmp     ebx, 3
0x18001f915  jnz     loc_18001F99F
0x18001f91b  lea     ecx, [rbx+1]; unsigned __int64
0x18001f91e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f923  mov     qword ptr [rbp+57h+var_90+8], rax
0x18001f927  mov     rsi, rax
0x18001f92a  test    rax, rax
0x18001f92d  jz      loc_18001FA2D
0x18001f933  mov     r8, r13; Size
0x18001f936  mov     rbx, r13
0x18001f939  mov     r13, [rbp+57h+var_40]
0x18001f93d  xor     eax, eax
0x18001f93f  add     r13, [rbp+57h+Size]
0x18001f943  mov     rcx, rsi; void *
0x18001f946  mov     rdx, r13; Src
0x18001f949  mov     [rsi], eax
0x18001f94b  call    memcpy_0
0x18001f950  lea     rax, [rbx+r13]
0x18001f954  mov     dword ptr [rbp+57h+var_90], 4
0x18001f95b  mov     [rbp+57h+var_40], rax
0x18001f95f  mov     ebx, 1
0x18001f964  movups  xmm0, [rbp+57h+var_A0]
0x18001f968  lea     rcx, [r14+50h]
0x18001f96c  movups  xmm1, [rbp+57h+var_90]
0x18001f970  lea     rdx, [rbp+57h+var_60]
0x18001f974  movaps  [rbp+57h+var_60], xmm0
0x18001f978  movaps  [rbp+57h+var_50], xmm1
0x18001f97c  call    ?Add@?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEAAHUMETADATA_REC@CASFMetaDataObjectBase@@PEAK@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::Add(CASFMetaDataObjectBase::METADATA_REC,ulong *)
0x18001f981  test    eax, eax
0x18001f983  jz      loc_18001FA20
0x18001f989  mov     eax, [rbp+57h+var_B8]
0x18001f98c  mov     esi, [rbp+57h+var_80]
0x18001f98f  add     ax, bx
0x18001f992  mov     r11, [rbp+57h+var_40]
0x18001f996  movzx   ecx, [rbp+57h+var_BC]
0x18001f99a  jmp     loc_18001F791
0x18001f99f  mov     rcx, r13; unsigned __int64
0x18001f9a2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f9a7  mov     qword ptr [rbp+57h+var_90+8], rax
0x18001f9ab  mov     rsi, rax
0x18001f9ae  test    rax, rax
0x18001f9b1  jz      short loc_18001FA2D
0x18001f9b3  mov     rdx, [rbp+57h+var_40]
0x18001f9b7  mov     r8, r13; Size
0x18001f9ba  add     rdx, [rbp+57h+Size]; Src
0x18001f9be  mov     rcx, rax; void *
0x18001f9c1  call    memcpy_0
0x18001f9c6  mov     rax, [rbp+57h+var_40]
0x18001f9ca  mov     rcx, r13
0x18001f9cd  add     rax, [rbp+57h+Size]
0x18001f9d1  add     rax, rcx
0x18001f9d4  mov     [rbp+57h+var_40], rax
0x18001f9d8  cmp     ebx, 1
0x18001f9db  jnz     short loc_18001F95F
0x18001f9dd  test    bl, r13b
0x18001f9e0  jnz     short loc_18001FA06
0x18001f9e2  test    r13d, r13d
0x18001f9e5  jz      loc_18001F964
0x18001f9eb  shr     rcx, 1
0x18001f9ee  xor     eax, eax
0x18001f9f0  mov     [rsi+rcx*2-2], ax
0x18001f9f5  jmp     loc_18001F964
0x18001f9fa  mov     eax, 0C00D07E2h
0x18001f9ff  mov     edi, eax
0x18001fa01  jmp     loc_18001FACC
0x18001fa06  mov     rcx, r15; Block
0x18001fa09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa0e  mov     rcx, rsi; Block
0x18001fa11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa16  mov     edi, 0C00D07E2h
0x18001fa1b  jmp     loc_18001FACC
0x18001fa20  mov     rcx, r15; Block
0x18001fa23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa28  mov     rcx, rsi
0x18001fa2b  jmp     short loc_18001FA30
0x18001fa2d  mov     rcx, r15; Block
0x18001fa30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa35  mov     edi, 8007000Eh
0x18001fa3a  jmp     loc_18001FACC
0x18001fa3f  mov     rcx, r15; Block
0x18001fa42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa47  mov     eax, [rbp+57h+var_C0]
0x18001fa4a  mov     [r12], eax
0x18001fa4e  jmp     short loc_18001FACC
0x18001fa50  mov     rcx, [r14+28h]
0x18001fa54  mov     ebx, [rbp+57h+var_C0]
0x18001fa57  test    rcx, rcx
0x18001fa5a  jz      short loc_18001FAAE
0x18001fa5c  mov     [rbp+57h+var_40], 0
0x18001fa64  lea     r8, [rbp+57h+var_40]
0x18001fa68  mov     rax, [rcx]
0x18001fa6b  lea     rdx, IID_IASFReadWriteTracker
0x18001fa72  mov     rax, [rax]
0x18001fa75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa7a  test    eax, eax
0x18001fa7c  js      short loc_18001FAAE
0x18001fa7e  mov     rcx, [rbp+57h+var_40]
0x18001fa82  lea     r9, [r14+30h]
0x18001fa86  mov     rdx, [rbp+57h+var_70]
0x18001fa8a  mov     r8d, ebx
0x18001fa8d  mov     rax, [rcx]
0x18001fa90  mov     rax, [rax+48h]
0x18001fa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa99  mov     rcx, [rbp+57h+var_40]
0x18001fa9d  test    rcx, rcx
0x18001faa0  jz      short loc_18001FAAE
0x18001faa2  mov     rax, [rcx]
0x18001faa5  mov     rax, [rax+10h]
0x18001faa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faae  lea     rcx, [rbp+57h+var_78]; this
0x18001fab2  mov     [r12], ebx
0x18001fab6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001fabb  xor     eax, eax
0x18001fabd  jmp     short loc_18001FAE7
0x18001fabf  mov     dword ptr [r12], 1Ah
0x18001fac7  mov     edi, 0C00D07D1h
0x18001facc  lea     rcx, [rbp+57h+var_78]; this
0x18001fad0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001fad5  mov     eax, edi
0x18001fad7  jmp     short loc_18001FAE7
0x18001fad9  lea     rcx, [rbp+57h+var_78]; this
0x18001fadd  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001fae2  mov     eax, 80070057h
0x18001fae7  mov     rcx, [rbp+57h+var_38]
0x18001faeb  xor     rcx, rsp; StackCookie
0x18001faee  call    __security_check_cookie
0x18001faf3  mov     rbx, [rsp+0F0h+arg_8]
0x18001fafb  add     rsp, 0C0h
0x18001fb02  pop     r15
  ... truncated ...
```
