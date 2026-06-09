# CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(INativeConfigurationElementCollection *,INativeConfigurationElementCollection *,int,int *)

- ea: `0x180001010`
- end: `0x1800014df`
- name: `?AreConfigurationCollectionsDifferent@CDetectISAPIConfigContext@@AEAAJPEAVINativeConfigurationElementCollection@@0HPEAH@Z`
- size: `1231`
- prototype: `__int64 __fastcall(CDetectISAPIConfigContext *__hidden this, struct INativeConfigurationElementCollection *, struct INativeConfigurationElementCollection *, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180002268`

## callees

- `0x180001010`
- `0x180003126`
- `0x180003160`
- `0x180004010`

## import_xrefs

- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800012ea`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800013d2`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800012ea`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x1800013d2`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000126f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001356`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000126f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180001356`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001219`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001288`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800012fe`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001374`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001219`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001288`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800012fe`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001374`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800010a0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800010cc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800010a0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800010cc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800014a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800014ad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800014a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800014ad`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180001210`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000127f`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800012f5`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000136b`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180001210`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000127f`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800012f5`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18000136b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001233`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800012a2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001319`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000138f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800013dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800013ea`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001233`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800012a2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001319`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000138f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800013dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800013ea`

## pseudocode

```c
__int64 __fastcall CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(
        CDetectISAPIConfigContext *this,
        struct INativeConfigurationElementCollection *a2,
        struct INativeConfigurationElementCollection *a3,
        int a4,
        int *a5)
{
  int *v5; // r15
  unsigned int v6; // edi
  int v9; // r14d
  int v10; // ebx
  int v11; // esi
  unsigned int v12; // ebx
  _BYTE *v13; // r15
  unsigned int i; // r14d
  BUFFER *Buffer; // rax
  __int64 (__fastcall *v16)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  int v18; // eax
  BUFFER *v19; // rax
  __int64 (__fastcall *v20)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD); // rbx
  unsigned __int16 *v21; // rax
  BUFFER *v22; // rax
  __int64 (__fastcall *v23)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD); // rbx
  unsigned __int16 *v24; // rax
  int v25; // eax
  BUFFER *v26; // rax
  __int64 (__fastcall *v27)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD); // rbx
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rbx
  unsigned __int16 *v30; // rax
  signed __int64 v31; // rbx
  int v32; // ecx
  int v33; // edx
  __int64 v34; // rcx
  unsigned int Size; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  int *v38; // [rsp+50h] [rbp-B0h]
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v42; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+6Ch] [rbp-94h]
  _BYTE v44[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v45[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v46[1536]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v47[256]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v48[272]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v5 = a5;
  v6 = 0;
  v38 = a5;
  v40 = 0;
  v41 = 0;
  v37 = 0;
  v39 = 0;
  v9 = a4;
  v43 = a4;
  v10 = 1;
  v42 = 64;
  memset_0(v48, 0, 0x212u);
  STRU::STRU((STRU *)v45, v48, 0x109u);
  memset_0(v47, 0, sizeof(v47));
  STRU::STRU((STRU *)v44, v47, 0x100u);
  Size = 0;
  if ( a2 && a3 )
  {
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
            a2,
            &v40);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, int *))(*(_QWORD *)a3 + 24LL))(
              a3,
              &v41);
      if ( v11 >= 0 && v40 == v41 )
      {
        if ( v40 )
        {
          v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a2 + 32LL))(
                  a2,
                  0,
                  &v37);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *, unsigned int *))(*(_QWORD *)v37 + 96LL))(v37, v46, &v42);
            if ( v11 >= 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              v10 = 0;
              v37 = 0;
              while ( v6 < v40 )
              {
                v12 = v6;
                if ( v9 )
                  v12 = v40 - v6 - 1;
                v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a2 + 32LL))(
                        a2,
                        v12,
                        &v37);
                if ( v11 < 0
                  || (v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a3 + 32LL))(
                              a3,
                              v12,
                              &v39),
                      v11 < 0) )
                {
LABEL_20:
                  v10 = 1;
                  break;
                }
                v13 = v46;
                for ( i = 0; i < v42; ++i )
                {
                  Buffer = STRU::QueryBuffer((STRU *)v45);
                  Size = BUFFER::QuerySize(Buffer);
                  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v37 + 88LL);
                  Str = STRU::QueryStr((STRU *)v45);
                  v18 = v16(v37, *((_QWORD *)v13 + 1), Str, &Size, 0, 0);
                  v11 = v18;
                  if ( v18 == -2147024774 )
                  {
                    v11 = STRU::Resize((STRU *)v45, Size);
                    if ( v11 < 0 )
                      goto LABEL_20;
                    v19 = STRU::QueryBuffer((STRU *)v45);
                    Size = BUFFER::QuerySize(v19);
                    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v37 + 88LL);
                    v21 = STRU::QueryStr((STRU *)v45);
                    v11 = v20(v37, *((_QWORD *)v13 + 1), v21, &Size, 0, 0);
                    if ( v11 < 0 )
                      goto LABEL_20;
                  }
                  else if ( v18 < 0 )
                  {
                    goto LABEL_20;
                  }
                  STRU::SyncWithBuffer((STRU *)v45);
                  v22 = STRU::QueryBuffer((STRU *)v44);
                  Size = BUFFER::QuerySize(v22);
                  v23 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v39 + 88LL);
                  v24 = STRU::QueryStr((STRU *)v44);
                  v25 = v23(v39, *((_QWORD *)v13 + 1), v24, &Size, 0, 0);
                  v11 = v25;
                  if ( v25 == -2147024774 )
                  {
                    v11 = STRU::Resize((STRU *)v44, Size);
                    if ( v11 < 0 )
                      goto LABEL_20;
                    v26 = STRU::QueryBuffer((STRU *)v44);
                    Size = BUFFER::QuerySize(v26);
                    v27 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v39 + 88LL);
                    v28 = STRU::QueryStr((STRU *)v44);
                    v11 = v27(v39, *((_QWORD *)v13 + 1), v28, &Size, 0, 0);
                    if ( v11 < 0 )
                      goto LABEL_20;
                  }
                  else if ( v25 < 0 )
                  {
                    goto LABEL_20;
                  }
                  STRU::SyncWithBuffer((STRU *)v44);
                  v29 = STRU::QueryStr((STRU *)v44);
                  v30 = STRU::QueryStr((STRU *)v45);
                  v31 = (char *)v29 - (char *)v30;
                  do
                  {
                    v32 = *(unsigned __int16 *)((char *)v30 + v31);
                    v33 = *v30 - v32;
                    if ( v33 )
                      break;
                    ++v30;
                  }
                  while ( v32 );
                  if ( v33 )
                    goto LABEL_20;
                  v13 += 24;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                v10 = 0;
                v37 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                v9 = v43;
                ++v6;
                v39 = 0;
              }
              v5 = v38;
            }
          }
        }
        else
        {
          v10 = 0;
        }
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
  v34 = v37;
  *v5 = v10;
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v37 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  STRU::~STRU((STRU *)v44);
  STRU::~STRU((STRU *)v45);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180001010  mov     [rsp-8+arg_0], rbx
0x180001015  push    rbp
0x180001016  push    rsi
0x180001017  push    rdi
0x180001018  push    r12
0x18000101a  push    r13
0x18000101c  push    r14
0x18000101e  push    r15
0x180001020  lea     rbp, [rsp-0A10h]
0x180001028  sub     rsp, 0B10h
0x18000102f  mov     rax, cs:__security_cookie
0x180001036  xor     rax, rsp
0x180001039  mov     [rbp+0A40h+var_40], rax
0x180001040  mov     r15, [rbp+0A40h+arg_20]
0x180001047  lea     rcx, [rbp+0A40h+var_260]; void *
0x18000104e  xor     edi, edi
0x180001050  mov     [rsp+0B40h+var_AF0], r15
0x180001055  mov     r12, r8
0x180001058  mov     [rsp+0B40h+var_AE0], edi
0x18000105c  mov     r13, rdx
0x18000105f  mov     [rsp+0B40h+var_ADC], edi
0x180001063  xor     edx, edx; Val
0x180001065  mov     [rsp+0B40h+var_AF8], rdi
0x18000106a  mov     r8d, 212h; Size
0x180001070  mov     [rsp+0B40h+var_AE8], rdi
0x180001075  mov     r14d, r9d
0x180001078  mov     [rsp+0B40h+var_AD4], r9d
0x18000107d  mov     ebx, 1
0x180001082  mov     [rsp+0B40h+var_AD8], 40h ; '@'
0x18000108a  call    memset_0
0x18000108f  mov     r8d, 109h
0x180001095  lea     rdx, [rbp+0A40h+var_260]
0x18000109c  lea     rcx, [rbp+0A40h+var_A98]
0x1800010a0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800010a6  xor     edx, edx; Val
0x1800010a8  lea     rcx, [rbp+0A40h+var_460]; void *
0x1800010af  mov     r8d, 200h; Size
0x1800010b5  call    memset_0
0x1800010ba  mov     r8d, 100h
0x1800010c0  lea     rdx, [rbp+0A40h+var_460]
0x1800010c7  lea     rcx, [rsp+0B40h+var_AD0]
0x1800010cc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800010d2  mov     [rsp+0B40h+var_B00], edi
0x1800010d6  test    r13, r13
0x1800010d9  jz      loc_180001458
0x1800010df  test    r12, r12
0x1800010e2  jz      loc_180001458
0x1800010e8  mov     rax, [r13+0]
0x1800010ec  lea     rdx, [rsp+0B40h+var_AE0]
0x1800010f1  mov     rcx, r13
0x1800010f4  mov     rax, [rax+18h]
0x1800010f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010fd  mov     esi, eax
0x1800010ff  test    eax, eax
0x180001101  js      loc_18000145D
0x180001107  mov     rax, [r12]
0x18000110b  lea     rdx, [rsp+0B40h+var_ADC]
0x180001110  mov     rcx, r12
0x180001113  mov     rax, [rax+18h]
0x180001117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000111c  mov     esi, eax
0x18000111e  test    eax, eax
0x180001120  js      loc_18000145D
0x180001126  mov     eax, [rsp+0B40h+var_AE0]
0x18000112a  cmp     eax, [rsp+0B40h+var_ADC]
0x18000112e  jnz     loc_18000145D
0x180001134  cmp     eax, ebx
0x180001136  jb      loc_180001454
0x18000113c  mov     rax, [r13+0]
0x180001140  lea     r8, [rsp+0B40h+var_AF8]
0x180001145  xor     edx, edx
0x180001147  mov     rcx, r13
0x18000114a  mov     rax, [rax+20h]
0x18000114e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001153  mov     esi, eax
0x180001155  test    eax, eax
0x180001157  js      loc_18000145D
0x18000115d  mov     rcx, [rsp+0B40h+var_AF8]
0x180001162  lea     r8, [rsp+0B40h+var_AD8]
0x180001167  lea     rdx, [rbp+0A40h+var_A60]
0x18000116b  mov     rax, [rcx]
0x18000116e  mov     rax, [rax+60h]
0x180001172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001177  mov     esi, eax
0x180001179  test    eax, eax
0x18000117b  js      loc_18000145D
0x180001181  mov     rcx, [rsp+0B40h+var_AF8]
0x180001186  mov     rax, [rcx]
0x180001189  mov     rax, [rax+10h]
0x18000118d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001192  xor     ebx, ebx
0x180001194  mov     [rsp+0B40h+var_AF8], rbx
0x180001199  nop     dword ptr [rax+00000000h]
0x1800011a0  mov     eax, [rsp+0B40h+var_AE0]
0x1800011a4  cmp     edi, eax
0x1800011a6  jnb     loc_1800012D8
0x1800011ac  sub     eax, edi
0x1800011ae  lea     r8, [rsp+0B40h+var_AF8]
0x1800011b3  dec     eax
0x1800011b5  mov     ebx, edi
0x1800011b7  test    r14d, r14d
0x1800011ba  mov     rcx, r13
0x1800011bd  cmovnz  ebx, eax
0x1800011c0  mov     rax, [r13+0]
0x1800011c4  mov     edx, ebx
0x1800011c6  mov     rax, [rax+20h]
0x1800011ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011cf  mov     esi, eax
0x1800011d1  test    eax, eax
0x1800011d3  js      loc_1800012D3
0x1800011d9  mov     rax, [r12]
0x1800011dd  lea     r8, [rsp+0B40h+var_AE8]
0x1800011e2  mov     edx, ebx
0x1800011e4  mov     rcx, r12
0x1800011e7  mov     rax, [rax+20h]
0x1800011eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011f0  mov     esi, eax
0x1800011f2  test    eax, eax
0x1800011f4  js      loc_1800012D3
0x1800011fa  lea     r15, [rbp+0A40h+var_A60]
0x1800011fe  xor     r14d, r14d
0x180001201  cmp     r14d, [rsp+0B40h+var_AD8]
0x180001206  jnb     loc_18000141A
0x18000120c  lea     rcx, [rbp+0A40h+var_A98]
0x180001210  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180001216  mov     rcx, rax
0x180001219  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000121f  mov     [rsp+0B40h+var_B00], eax
0x180001223  mov     rax, [rsp+0B40h+var_AF8]
0x180001228  mov     rcx, [rax]
0x18000122b  mov     rbx, [rcx+58h]
0x18000122f  lea     rcx, [rbp+0A40h+var_A98]
0x180001233  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001239  mov     rdx, [r15+8]
0x18000123d  lea     r9, [rsp+0B40h+var_B00]
0x180001242  xor     ecx, ecx
0x180001244  mov     r8, rax
0x180001247  mov     [rsp+0B40h+var_B18], rcx
0x18000124c  mov     rax, rbx
0x18000124f  mov     [rsp+0B40h+var_B20], rcx
0x180001254  mov     rcx, [rsp+0B40h+var_AF8]
0x180001259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000125e  mov     esi, eax
0x180001260  cmp     eax, 8007007Ah
0x180001265  jnz     short loc_1800012E2
0x180001267  mov     edx, [rsp+0B40h+var_B00]
0x18000126b  lea     rcx, [rbp+0A40h+var_A98]
0x18000126f  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180001275  mov     esi, eax
0x180001277  test    eax, eax
0x180001279  js      short loc_1800012D3
0x18000127b  lea     rcx, [rbp+0A40h+var_A98]
0x18000127f  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180001285  mov     rcx, rax
0x180001288  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000128e  mov     [rsp+0B40h+var_B00], eax
0x180001292  mov     rax, [rsp+0B40h+var_AF8]
0x180001297  mov     rcx, [rax]
0x18000129a  mov     rbx, [rcx+58h]
0x18000129e  lea     rcx, [rbp+0A40h+var_A98]
0x1800012a2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800012a8  mov     rdx, [r15+8]
0x1800012ac  lea     r9, [rsp+0B40h+var_B00]
0x1800012b1  xor     ecx, ecx
0x1800012b3  mov     r8, rax
0x1800012b6  mov     [rsp+0B40h+var_B18], rcx
0x1800012bb  mov     rax, rbx
0x1800012be  mov     [rsp+0B40h+var_B20], rcx
0x1800012c3  mov     rcx, [rsp+0B40h+var_AF8]
0x1800012c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012cd  mov     esi, eax
0x1800012cf  test    eax, eax
0x1800012d1  jns     short loc_1800012E6
0x1800012d3  mov     ebx, 1
0x1800012d8  mov     r15, [rsp+0B40h+var_AF0]
0x1800012dd  jmp     loc_18000145D
0x1800012e2  test    eax, eax
0x1800012e4  js      short loc_1800012D3
0x1800012e6  lea     rcx, [rbp+0A40h+var_A98]
0x1800012ea  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800012f0  lea     rcx, [rsp+0B40h+var_AD0]
0x1800012f5  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x1800012fb  mov     rcx, rax
0x1800012fe  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180001304  mov     [rsp+0B40h+var_B00], eax
0x180001308  mov     rax, [rsp+0B40h+var_AE8]
0x18000130d  mov     rcx, [rax]
0x180001310  mov     rbx, [rcx+58h]
0x180001314  lea     rcx, [rsp+0B40h+var_AD0]
0x180001319  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000131f  mov     rdx, [r15+8]
0x180001323  lea     r9, [rsp+0B40h+var_B00]
0x180001328  xor     ecx, ecx
0x18000132a  mov     r8, rax
0x18000132d  mov     [rsp+0B40h+var_B18], rcx
0x180001332  mov     rax, rbx
0x180001335  mov     [rsp+0B40h+var_B20], rcx
0x18000133a  mov     rcx, [rsp+0B40h+var_AE8]
0x18000133f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001344  mov     esi, eax
0x180001346  cmp     eax, 8007007Ah
0x18000134b  jnz     short loc_1800013C5
0x18000134d  mov     edx, [rsp+0B40h+var_B00]
0x180001351  lea     rcx, [rsp+0B40h+var_AD0]
0x180001356  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000135c  mov     esi, eax
0x18000135e  test    eax, eax
0x180001360  js      loc_1800012D3
0x180001366  lea     rcx, [rsp+0B40h+var_AD0]
0x18000136b  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180001371  mov     rcx, rax
0x180001374  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000137a  mov     [rsp+0B40h+var_B00], eax
0x18000137e  mov     rax, [rsp+0B40h+var_AE8]
0x180001383  mov     rcx, [rax]
0x180001386  mov     rbx, [rcx+58h]
0x18000138a  lea     rcx, [rsp+0B40h+var_AD0]
0x18000138f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001395  mov     rdx, [r15+8]
0x180001399  lea     r9, [rsp+0B40h+var_B00]
0x18000139e  xor     ecx, ecx
0x1800013a0  mov     r8, rax
0x1800013a3  mov     [rsp+0B40h+var_B18], rcx
0x1800013a8  mov     rax, rbx
0x1800013ab  mov     [rsp+0B40h+var_B20], rcx
0x1800013b0  mov     rcx, [rsp+0B40h+var_AE8]
0x1800013b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013ba  mov     esi, eax
0x1800013bc  test    eax, eax
0x1800013be  jns     short loc_1800013CD
0x1800013c0  jmp     loc_1800012D3
0x1800013c5  test    eax, eax
0x1800013c7  js      loc_1800012D3
0x1800013cd  lea     rcx, [rsp+0B40h+var_AD0]
0x1800013d2  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800013d8  lea     rcx, [rsp+0B40h+var_AD0]
0x1800013dd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800013e3  lea     rcx, [rbp+0A40h+var_A98]
0x1800013e7  mov     rbx, rax
0x1800013ea  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800013f0  sub     rbx, rax
0x1800013f3  movzx   edx, word ptr [rax]
0x1800013f6  movzx   ecx, word ptr [rax+rbx]
0x1800013fa  sub     edx, ecx
0x1800013fc  jnz     short loc_180001406
0x1800013fe  add     rax, 2
0x180001402  test    ecx, ecx
0x180001404  jnz     short loc_1800013F3
0x180001406  test    edx, edx
0x180001408  jnz     loc_1800012D3
0x18000140e  add     r15, 18h
0x180001412  inc     r14d
0x180001415  jmp     loc_180001201
0x18000141a  mov     rcx, [rsp+0B40h+var_AF8]
0x18000141f  mov     rax, [rcx]
0x180001422  mov     rax, [rax+10h]
0x180001426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000142b  mov     rcx, [rsp+0B40h+var_AE8]
0x180001430  xor     ebx, ebx
0x180001432  mov     [rsp+0B40h+var_AF8], rbx
0x180001437  mov     rax, [rcx]
0x18000143a  mov     rax, [rax+10h]
0x18000143e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001443  mov     r14d, [rsp+0B40h+var_AD4]
0x180001448  inc     edi
0x18000144a  mov     [rsp+0B40h+var_AE8], rbx
0x18000144f  jmp     loc_1800011A0
0x180001454  mov     ebx, edi
0x180001456  jmp     short loc_18000145D
0x180001458  mov     esi, 80070057h
0x18000145d  mov     rcx, [rsp+0B40h+var_AF8]
0x180001462  mov     [r15], ebx
0x180001465  test    rcx, rcx
0x180001468  jz      short loc_18000147F
0x18000146a  mov     rax, [rcx]
0x18000146d  mov     rax, [rax+10h]
0x180001471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001476  mov     [rsp+0B40h+var_AF8], 0
0x18000147f  mov     rcx, [rsp+0B40h+var_AE8]
0x180001484  test    rcx, rcx
0x180001487  jz      short loc_18000149E
0x180001489  mov     rax, [rcx]
0x18000148c  mov     rax, [rax+10h]
0x180001490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001495  mov     [rsp+0B40h+var_AE8], 0
0x18000149e  lea     rcx, [rsp+0B40h+var_AD0]
0x1800014a3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800014a9  lea     rcx, [rbp+0A40h+var_A98]
0x1800014ad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800014b3  mov     eax, esi
0x1800014b5  mov     rcx, [rbp+0A40h+var_40]
0x1800014bc  xor     rcx, rsp; StackCookie
0x1800014bf  call    __security_check_cookie
0x1800014c4  mov     rbx, [rsp+0B40h+arg_0]
0x1800014cc  add     rsp, 0B10h
0x1800014d3  pop     r15
0x1800014d5  pop     r14
0x1800014d7  pop     r13
0x1800014d9  pop     r12
0x1800014db  pop     rdi
  ... truncated ...
```
