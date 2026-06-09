# _CoalesceOptionalSProps

- ea: `0x180009f94`
- end: `0x18000a56f`
- name: `_CoalesceOptionalSProps`
- size: `1499`
- prototype: `__int64 __usercall@<rax>(struct IContactProperties *@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ac04`

## callees

- `0x180001610`
- `0x18000161c`
- `0x1800027dc`
- `0x180006f7c`
- `0x180008f74`
- `0x180009428`
- `0x180009f94`
- `0x180013168`
- `0x180013be0`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000a1c8`
- `KERNEL32!CompareStringW` at `0x18000a24a`
- `KERNEL32!CompareStringW` at `0x18000a32c`
- `KERNEL32!CompareStringW` at `0x18000a517`
- `KERNEL32!CompareStringW` at `0x18000a1c8`
- `KERNEL32!CompareStringW` at `0x18000a24a`
- `KERNEL32!CompareStringW` at `0x18000a32c`
- `KERNEL32!CompareStringW` at `0x18000a517`

## pseudocode

```c
__int64 __fastcall CoalesceOptionalSProps(
        struct IContactProperties *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int *a8)
{
  const unsigned __int16 **v12; // r8
  unsigned int v13; // r9d
  int ArrayNodeCount; // ebx
  int v15; // eax
  unsigned int v16; // r14d
  unsigned int v17; // eax
  _DWORD *v18; // rdx
  __int64 v19; // rcx
  _DWORD *v20; // rax
  _DWORD *v21; // rdi
  int v22; // ecx
  unsigned int i; // eax
  int StringFromIProperties; // eax
  __int64 j; // rbx
  const WCHAR *v26; // r8
  bool v27; // zf
  __int64 v28; // r8
  __int64 v29; // rax
  const WCHAR *lpString2; // rax
  __int64 v31; // r12
  __int64 v32; // rbx
  __int64 v33; // r9
  struct IContactProperties *v34; // r8
  const WCHAR *v35; // rax
  void *v36; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned int v40; // esi
  _DWORD *v41; // rax
  unsigned int k; // r13d
  int v43; // eax
  const WCHAR *v44; // r8
  unsigned int v45; // edx
  int v46; // [rsp+30h] [rbp-D0h]
  unsigned int v47; // [rsp+34h] [rbp-CCh] BYREF
  int v48; // [rsp+38h] [rbp-C8h]
  int v49; // [rsp+3Ch] [rbp-C4h]
  unsigned int v50; // [rsp+40h] [rbp-C0h]
  __int64 v51; // [rsp+48h] [rbp-B8h]
  void *Block; // [rsp+50h] [rbp-B0h]
  struct IContactProperties *v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h]
  int v55; // [rsp+68h] [rbp-98h] BYREF
  PCNZWCH lpString1[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v57; // [rsp+88h] [rbp-78h]
  unsigned int *v58; // [rsp+90h] [rbp-70h]
  unsigned __int16 v59[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v60[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v57 = a7;
  v54 = a3;
  v53 = a1;
  v58 = a8;
  v47 = 0;
  memset_0(v59, 0, 0x208u);
  STRW::STRW((STRW *)&v55, v60, 0x104u);
  ArrayNodeCount = GetArrayNodeCount(a1, (const unsigned __int16 *)&v47, v12, v13, &v47);
  if ( ArrayNodeCount >= 0 )
  {
    if ( a2 )
    {
      v15 = *(_DWORD *)(a2 + 8);
      if ( v15 )
      {
        if ( !a3 || (v48 = 1, *(_DWORD *)(a3 + 8) != v15) )
          v48 = 0;
        if ( a6 )
          v49 = *(_DWORD *)(a6 + 8);
        else
          v49 = v15;
        v16 = v47;
        v17 = v15 + 1;
        if ( v17 > v47 )
          v16 = v17;
        Block = operator new(saturated_mul(v17, 4u));
        v18 = Block;
        if ( !Block )
        {
LABEL_13:
          ArrayNodeCount = -2147024882;
          goto LABEL_65;
        }
        v19 = 0;
        if ( *(_DWORD *)(a2 + 8) != -1 )
        {
          do
          {
            v18[v19] = 0;
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (unsigned int)v19 < *(_DWORD *)(a2 + 8) + 1 );
        }
        v20 = operator new(saturated_mul(v16, 0x18u));
        v21 = v20;
        if ( v20 )
        {
          `vector constructor iterator'(v20, 0x18u, v16, (void *(*)(void *))_MailConverter::_MailConverter);
          v22 = 0;
          v46 = 0;
          for ( i = 0; ; i = v50 )
          {
            LODWORD(v51) = i;
            if ( i >= v47 )
              break;
            v50 = i + 1;
            ArrayNodeCount = StringCchPrintfW(v59, 0x104u, L"EmailAddressCollection/EmailAddress[%d]/Address", i + 1);
            if ( ArrayNodeCount < 0 )
              goto LABEL_47;
            StringFromIProperties = GetStringFromIProperties(v53, v59, (struct STRW *)&v55);
            ArrayNodeCount = StringFromIProperties;
            if ( StringFromIProperties != -2147024893 )
            {
              if ( StringFromIProperties < 0 )
                goto LABEL_47;
              for ( j = 0; (unsigned int)j < *(_DWORD *)(a2 + 8); j = (unsigned int)(j + 1) )
              {
                if ( !*((_DWORD *)Block + j) )
                {
                  v26 = &Str;
                  if ( v55 )
                    v26 = lpString1[0];
                  if ( CompareStringW(0x7Fu, 1u, v26, -1, *(PCNZWCH *)(*(_QWORD *)(a2 + 16) + 8 * j), -1) == 2 )
                  {
                    v27 = v48 == 0;
                    *((_DWORD *)Block + j) = 1;
                    v28 = 3LL * (unsigned int)v51;
                    v21[2 * v28] = 0;
                    v29 = *(_QWORD *)(a2 + 16);
                    v51 = v28;
                    *(_QWORD *)&v21[2 * v28 + 2] = *(_QWORD *)(v29 + 8 * j);
                    if ( !v27 )
                      *(_QWORD *)&v21[2 * v28 + 4] = *(_QWORD *)(*(_QWORD *)(v54 + 16) + 8 * j);
                    if ( (_DWORD)j != v49 )
                      break;
                    if ( a4 )
                    {
                      lpString2 = *(const WCHAR **)(a4 + 8);
                      if ( lpString2 )
                      {
                        if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*(_QWORD *)(a2 + 16) + 8 * j), -1, lpString2, -1) != 2 )
                          break;
                        v28 = v51;
                      }
                    }
                    v22 = 1;
                    v21[2 * v28 + 1] = 1;
                    v46 = 1;
                    goto LABEL_38;
                  }
                }
              }
            }
            v22 = v46;
LABEL_38:
            ;
          }
          v31 = 0;
          v32 = 0;
          while ( 1 )
          {
            if ( (unsigned int)v31 >= *(_DWORD *)(a2 + 8) || (unsigned int)v32 >= v16 )
            {
              if ( !v22 && a4 && *(_QWORD *)(a4 + 8) )
              {
                while ( 1 )
                {
                  if ( (unsigned int)v32 >= v16 )
                  {
LABEL_46:
                    ArrayNodeCount = -2147418113;
                    goto LABEL_47;
                  }
                  if ( v21[6 * v32] )
                    break;
                  v32 = (unsigned int)(v32 + 1);
                }
                v38 = 3 * v32;
                v21[2 * v38 + 1] = 1;
                v21[2 * v38] = 1;
                *(_QWORD *)&v21[2 * v38 + 2] = *(_QWORD *)(a4 + 8);
                if ( a5 )
                {
                  v39 = *(_QWORD *)(a5 + 8);
                  if ( v39 )
LABEL_72:
                    *(_QWORD *)&v21[2 * v38 + 4] = v39;
                }
              }
              goto LABEL_62;
            }
            if ( !*((_DWORD *)Block + v31) )
            {
              v33 = *(_QWORD *)(*(_QWORD *)(a2 + 16) + 8 * v31);
              if ( v33 )
                break;
            }
LABEL_58:
            v31 = (unsigned int)(v31 + 1);
          }
          while ( !v21[6 * v32] )
          {
            v32 = (unsigned int)(v32 + 1);
            if ( (unsigned int)v32 >= v16 )
              goto LABEL_46;
          }
          v27 = v48 == 0;
          v34 = (struct IContactProperties *)(3 * v32);
          v53 = v34;
          *(_QWORD *)&v21[2 * (_QWORD)v34 + 2] = v33;
          if ( !v27 )
            *(_QWORD *)&v21[6 * v32 + 4] = *(_QWORD *)(*(_QWORD *)(v54 + 16) + 8 * v31);
          if ( (_DWORD)v31 == v49 )
          {
            if ( !a4 )
              goto LABEL_55;
            v35 = *(const WCHAR **)(a4 + 8);
            if ( !v35 )
              goto LABEL_55;
            if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*(_QWORD *)(a2 + 16) + 8 * v31), -1, v35, -1) == 2 )
            {
              v34 = v53;
LABEL_55:
              v22 = 1;
              v21[2 * (_QWORD)v34 + 1] = 1;
              v46 = 1;
LABEL_57:
              v32 = (unsigned int)(v32 + 1);
              goto LABEL_58;
            }
          }
          v22 = v46;
          goto LABEL_57;
        }
        v36 = Block;
        ArrayNodeCount = -2147024882;
LABEL_64:
        operator delete(v36);
        goto LABEL_65;
      }
    }
    v21 = 0;
    v16 = 0;
    Block = 0;
    if ( !a4 || !*(_QWORD *)(a4 + 8) )
      goto LABEL_62;
    v16 = v47 + 1;
    v40 = v47 + 1;
    v41 = operator new(saturated_mul(v47 + 1, 0x18u));
    v21 = v41;
    if ( !v41 )
      goto LABEL_13;
    `vector constructor iterator'(v41, 0x18u, v40, (void *(*)(void *))_MailConverter::_MailConverter);
    LODWORD(v51) = 0;
    for ( k = 0; k < v47; k = v50 )
    {
      v50 = k + 1;
      ArrayNodeCount = StringCchPrintfW(v59, 0x104u, L"EmailAddressCollection/EmailAddress[%d]/Address", k + 1);
      if ( ArrayNodeCount < 0 )
        goto LABEL_47;
      v43 = GetStringFromIProperties(v53, v59, (struct STRW *)&v55);
      ArrayNodeCount = 0;
      if ( v43 != -2147024893 )
        ArrayNodeCount = v43;
      if ( ArrayNodeCount < 0 )
      {
LABEL_47:
        operator delete(v21);
        goto LABEL_63;
      }
      v44 = &Str;
      if ( v55 )
        v44 = lpString1[0];
      if ( CompareStringW(0x7Fu, 1u, v44, -1, *(PCNZWCH *)(a4 + 8), -1) == 2 )
      {
        v45 = k;
        v21[6 * k] = 0;
        goto LABEL_89;
      }
    }
    v45 = v51;
LABEL_89:
    v38 = 3LL * v45;
    v21[2 * v38 + 1] = 1;
    *(_QWORD *)&v21[2 * v38 + 2] = *(_QWORD *)(a4 + 8);
    if ( a5 )
    {
      v39 = *(_QWORD *)(a5 + 8);
      goto LABEL_72;
    }
LABEL_62:
    ArrayNodeCount = 0;
    *v57 = v21;
    *v58 = v16;
LABEL_63:
    v36 = Block;
    if ( Block )
      goto LABEL_64;
  }
LABEL_65:
  v55 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpString1);
  return (unsigned int)ArrayNodeCount;
}

```

## disassembly

```asm
0x180009f94  mov     [rsp-8+arg_10], rbx
0x180009f99  push    rbp
0x180009f9a  push    rsi
0x180009f9b  push    rdi
0x180009f9c  push    r12
0x180009f9e  push    r13
0x180009fa0  push    r14
0x180009fa2  push    r15
0x180009fa4  lea     rbp, [rsp-3D0h]
0x180009fac  sub     rsp, 4D0h
0x180009fb3  mov     rax, cs:__security_cookie
0x180009fba  xor     rax, rsp
0x180009fbd  mov     [rbp+400h+var_40], rax
0x180009fc4  mov     rax, [rbp+400h+arg_30]
0x180009fcb  mov     rdi, r8
0x180009fce  mov     [rbp+400h+var_478], rax
0x180009fd2  mov     r13, rdx
0x180009fd5  mov     rax, [rbp+400h+arg_38]
0x180009fdc  mov     rbx, rcx
0x180009fdf  mov     [rsp+500h+var_4A0], r8
0x180009fe4  xor     edx, edx; Val
0x180009fe6  mov     [rsp+500h+var_4A8], rcx
0x180009feb  mov     r8d, 208h; Size
0x180009ff1  lea     rcx, [rbp+400h+var_460]; void *
0x180009ff5  mov     [rbp+400h+var_470], rax
0x180009ff9  mov     r15, r9
0x180009ffc  mov     [rsp+500h+var_4CC], 0
0x18000a004  call    memset_0
0x18000a009  mov     r8d, 104h; unsigned int
0x18000a00f  lea     rdx, [rbp+400h+var_250]; unsigned __int16 *
0x18000a016  lea     rcx, [rsp+500h+var_498]; this
0x18000a01b  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18000a020  lea     rdx, [rsp+500h+var_4CC]; unsigned __int16 *
0x18000a025  mov     rcx, rbx; struct IContactProperties *
0x18000a028  mov     [rsp+500h+lpString2], rdx; unsigned int *
0x18000a02d  call    ?GetArrayNodeCount@@YAJPEAUIContactProperties@@PEBGPEAPEBGKPEAK@Z; GetArrayNodeCount(IContactProperties *,ushort const *,ushort const * *,ulong,ulong *)
0x18000a032  mov     ebx, eax
0x18000a034  test    eax, eax
0x18000a036  js      loc_18000A389
0x18000a03c  test    r13, r13
0x18000a03f  jz      loc_18000A427
0x18000a045  mov     eax, [r13+8]
0x18000a049  test    eax, eax
0x18000a04b  jz      loc_18000A427
0x18000a051  mov     esi, 1
0x18000a056  test    rdi, rdi
0x18000a059  jz      short loc_18000A064
0x18000a05b  mov     [rsp+500h+var_4C8], esi
0x18000a05f  cmp     [rdi+8], eax
0x18000a062  jz      short loc_18000A06C
0x18000a064  mov     [rsp+500h+var_4C8], 0
0x18000a06c  mov     rcx, [rbp+400h+arg_28]
0x18000a073  test    rcx, rcx
0x18000a076  jz      short loc_18000A081
0x18000a078  mov     ebx, [rcx+8]
0x18000a07b  mov     [rsp+500h+var_4C4], ebx
0x18000a07f  jmp     short loc_18000A085
0x18000a081  mov     [rsp+500h+var_4C4], eax
0x18000a085  mov     r14d, [rsp+500h+var_4CC]
0x18000a08a  inc     eax
0x18000a08c  cmp     eax, r14d
0x18000a08f  mov     ecx, eax
0x18000a091  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000a098  cmova   r14d, eax
0x18000a09c  mov     eax, 4
0x18000a0a1  mul     rcx
0x18000a0a4  cmovb   rax, r12
0x18000a0a8  mov     rcx, rax; Size
0x18000a0ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0b0  mov     [rsp+500h+Block], rax
0x18000a0b5  mov     rdx, rax
0x18000a0b8  test    rax, rax
0x18000a0bb  jnz     short loc_18000A0C7
0x18000a0bd  mov     ebx, 8007000Eh
0x18000a0c2  jmp     loc_18000A389
0x18000a0c7  mov     eax, [r13+8]
0x18000a0cb  xor     ecx, ecx
0x18000a0cd  add     eax, esi
0x18000a0cf  jz      short loc_18000A0E4
0x18000a0d1  mov     dword ptr [rdx+rcx*4], 0
0x18000a0d8  add     ecx, esi
0x18000a0da  mov     eax, [r13+8]
0x18000a0de  add     eax, esi
0x18000a0e0  cmp     ecx, eax
0x18000a0e2  jb      short loc_18000A0D1
0x18000a0e4  mov     ecx, r14d
0x18000a0e7  mov     ebx, 18h
0x18000a0ec  mov     eax, ebx
0x18000a0ee  mul     rcx
0x18000a0f1  cmovb   rax, r12
0x18000a0f5  mov     rcx, rax; Size
0x18000a0f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0fd  mov     rdi, rax
0x18000a100  test    rax, rax
0x18000a103  jz      loc_18000A418
0x18000a109  lea     r9, ??0_MailConverter@@QEAA@XZ; void *(*)(void *)
0x18000a110  mov     r8d, r14d; unsigned __int64
0x18000a113  mov     edx, ebx; unsigned __int64
0x18000a115  mov     rcx, rax; void *
0x18000a118  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18000a11d  xor     ecx, ecx
0x18000a11f  mov     [rsp+500h+var_4D0], ecx
0x18000a123  xor     eax, eax
0x18000a125  mov     dword ptr [rsp+500h+var_4B8], eax
0x18000a129  cmp     eax, [rsp+500h+var_4CC]
0x18000a12d  jnb     loc_18000A274
0x18000a133  inc     eax
0x18000a135  lea     r8, aEmailaddressco; "EmailAddressCollection/EmailAddress[%d]"...
0x18000a13c  mov     r9d, eax
0x18000a13f  mov     [rsp+500h+var_4C0], eax
0x18000a143  mov     edx, 104h; unsigned __int64
0x18000a148  lea     rcx, [rbp+400h+var_460]; unsigned __int16 *
0x18000a14c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a151  mov     ebx, eax
0x18000a153  test    eax, eax
0x18000a155  js      loc_18000A2C3
0x18000a15b  mov     rcx, [rsp+500h+var_4A8]; struct IContactProperties *
0x18000a160  lea     r8, [rsp+500h+var_498]; struct STRW *
0x18000a165  lea     rdx, [rbp+400h+var_460]; unsigned __int16 *
0x18000a169  call    ?GetStringFromIProperties@@YAJPEAUIContactProperties@@PEBGPEAVSTRW@@@Z; GetStringFromIProperties(IContactProperties *,ushort const *,STRW *)
0x18000a16e  mov     ebx, eax
0x18000a170  cmp     eax, 80070003h
0x18000a175  jz      loc_18000A267
0x18000a17b  test    eax, eax
0x18000a17d  js      loc_18000A2C3
0x18000a183  xor     ebx, ebx
0x18000a185  cmp     ebx, [r13+8]
0x18000a189  jnb     loc_18000A267
0x18000a18f  mov     rax, [rsp+500h+Block]
0x18000a194  cmp     dword ptr [rax+rbx*4], 0
0x18000a198  jnz     short loc_18000A1D3
0x18000a19a  mov     rax, [r13+10h]
0x18000a19e  lea     r8, Str
0x18000a1a5  cmp     [rsp+500h+var_498], 0
0x18000a1aa  mov     r9d, r12d; cchCount1
0x18000a1ad  mov     [rsp+500h+cchCount2], r12d; cchCount2
0x18000a1b2  mov     edx, esi; dwCmpFlags
0x18000a1b4  cmovnz  r8, [rsp+500h+lpString1]; lpString1
0x18000a1ba  mov     rcx, [rax+rbx*8]
0x18000a1be  mov     [rsp+500h+lpString2], rcx; lpString2
0x18000a1c3  mov     ecx, 7Fh; Locale
0x18000a1c8  call    cs:__imp_CompareStringW
0x18000a1ce  cmp     eax, 2
0x18000a1d1  jz      short loc_18000A1D7
0x18000a1d3  add     ebx, esi
0x18000a1d5  jmp     short loc_18000A185
0x18000a1d7  cmp     [rsp+500h+var_4C8], 0
0x18000a1dc  mov     rax, [rsp+500h+Block]
0x18000a1e1  mov     [rax+rbx*4], esi
0x18000a1e4  mov     eax, dword ptr [rsp+500h+var_4B8]
0x18000a1e8  lea     r8, [rax+rax*2]
0x18000a1ec  mov     dword ptr [rdi+r8*8], 0
0x18000a1f4  mov     rax, [r13+10h]
0x18000a1f8  mov     [rsp+500h+var_4B8], r8
0x18000a1fd  mov     rcx, [rax+rbx*8]
0x18000a201  mov     [rdi+r8*8+8], rcx
0x18000a206  jz      short loc_18000A21A
0x18000a208  mov     rax, [rsp+500h+var_4A0]
0x18000a20d  mov     rax, [rax+10h]
0x18000a211  mov     rcx, [rax+rbx*8]
0x18000a215  mov     [rdi+r8*8+10h], rcx
0x18000a21a  cmp     ebx, [rsp+500h+var_4C4]
0x18000a21e  jnz     short loc_18000A267
0x18000a220  test    r15, r15
0x18000a223  jz      short loc_18000A25A
0x18000a225  mov     rax, [r15+8]
0x18000a229  test    rax, rax
0x18000a22c  jz      short loc_18000A25A
0x18000a22e  mov     r8, [r13+10h]
0x18000a232  mov     r9d, r12d; cchCount1
0x18000a235  mov     [rsp+500h+cchCount2], r12d; cchCount2
0x18000a23a  mov     edx, esi; dwCmpFlags
0x18000a23c  mov     ecx, 7Fh; Locale
0x18000a241  mov     [rsp+500h+lpString2], rax; lpString2
0x18000a246  mov     r8, [r8+rbx*8]; lpString1
0x18000a24a  call    cs:__imp_CompareStringW
0x18000a250  cmp     eax, 2
0x18000a253  jnz     short loc_18000A267
0x18000a255  mov     r8, [rsp+500h+var_4B8]
0x18000a25a  mov     ecx, esi
0x18000a25c  mov     [rdi+r8*8+4], esi
0x18000a261  mov     [rsp+500h+var_4D0], ecx
0x18000a265  jmp     short loc_18000A26B
0x18000a267  mov     ecx, [rsp+500h+var_4D0]
0x18000a26b  mov     eax, [rsp+500h+var_4C0]
0x18000a26f  jmp     loc_18000A125
0x18000a274  xor     r12d, r12d
0x18000a277  xor     ebx, ebx
0x18000a279  cmp     r12d, [r13+8]
0x18000a27d  jnb     loc_18000A357
0x18000a283  cmp     ebx, r14d
0x18000a286  jnb     loc_18000A357
0x18000a28c  mov     rax, [rsp+500h+Block]
0x18000a291  cmp     dword ptr [rax+r12*4], 0
0x18000a296  jnz     loc_18000A34F
0x18000a29c  mov     rax, [r13+10h]
0x18000a2a0  mov     r9, [rax+r12*8]
0x18000a2a4  test    r9, r9
0x18000a2a7  jz      loc_18000A34F
0x18000a2ad  lea     rcx, [rbx+rbx*2]
0x18000a2b1  cmp     dword ptr [rdi+rcx*8], 0
0x18000a2b5  jnz     short loc_18000A2D0
0x18000a2b7  add     ebx, esi
0x18000a2b9  cmp     ebx, r14d
0x18000a2bc  jb      short loc_18000A2AD
0x18000a2be  mov     ebx, 8000FFFFh
0x18000a2c3  mov     rcx, rdi; Block
0x18000a2c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a2cb  jmp     loc_18000A377
0x18000a2d0  cmp     [rsp+500h+var_4C8], 0
0x18000a2d5  lea     r8, [rbx+rbx*2]
0x18000a2d9  mov     [rsp+500h+var_4A8], r8
0x18000a2de  mov     [rdi+r8*8+8], r9
0x18000a2e3  jz      short loc_18000A2F7
0x18000a2e5  mov     rax, [rsp+500h+var_4A0]
0x18000a2ea  mov     rax, [rax+10h]
0x18000a2ee  mov     rcx, [rax+r12*8]
0x18000a2f2  mov     [rdi+r8*8+10h], rcx
0x18000a2f7  cmp     r12d, [rsp+500h+var_4C4]
0x18000a2fc  jnz     short loc_18000A349
0x18000a2fe  test    r15, r15
0x18000a301  jz      short loc_18000A33C
0x18000a303  mov     rax, [r15+8]
0x18000a307  test    rax, rax
0x18000a30a  jz      short loc_18000A33C
0x18000a30c  mov     r8, [r13+10h]
0x18000a310  or      r9d, 0FFFFFFFFh; cchCount1
0x18000a314  mov     [rsp+500h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000a31c  mov     edx, esi; dwCmpFlags
0x18000a31e  mov     ecx, 7Fh; Locale
0x18000a323  mov     [rsp+500h+lpString2], rax; lpString2
0x18000a328  mov     r8, [r8+r12*8]; lpString1
0x18000a32c  call    cs:__imp_CompareStringW
0x18000a332  cmp     eax, 2
0x18000a335  jnz     short loc_18000A349
0x18000a337  mov     r8, [rsp+500h+var_4A8]
0x18000a33c  mov     ecx, esi
0x18000a33e  mov     [rdi+r8*8+4], esi
0x18000a343  mov     [rsp+500h+var_4D0], ecx
0x18000a347  jmp     short loc_18000A34D
0x18000a349  mov     ecx, [rsp+500h+var_4D0]
0x18000a34d  inc     ebx
0x18000a34f  add     r12d, esi
0x18000a352  jmp     loc_18000A279
0x18000a357  test    ecx, ecx
0x18000a359  jnz     short loc_18000A367
0x18000a35b  test    r15, r15
0x18000a35e  jz      short loc_18000A367
0x18000a360  cmp     qword ptr [r15+8], 0
0x18000a365  jnz     short loc_18000A3D3
0x18000a367  mov     rax, [rbp+400h+var_478]
0x18000a36b  xor     ebx, ebx
0x18000a36d  mov     [rax], rdi
0x18000a370  mov     rax, [rbp+400h+var_470]
0x18000a374  mov     [rax], r14d
0x18000a377  mov     rax, [rsp+500h+Block]
0x18000a37c  test    rax, rax
0x18000a37f  jz      short loc_18000A389
0x18000a381  mov     rcx, rax; Block
0x18000a384  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a389  lea     rcx, [rsp+500h+lpString1]; this
0x18000a38e  mov     [rsp+500h+var_498], 0
0x18000a396  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18000a39b  mov     eax, ebx
0x18000a39d  mov     rcx, [rbp+400h+var_40]
0x18000a3a4  xor     rcx, rsp; StackCookie
0x18000a3a7  call    __security_check_cookie
0x18000a3ac  mov     rbx, [rsp+500h+arg_10]
0x18000a3b4  add     rsp, 4D0h
0x18000a3bb  pop     r15
0x18000a3bd  pop     r14
0x18000a3bf  pop     r13
0x18000a3c1  pop     r12
0x18000a3c3  pop     rdi
0x18000a3c4  pop     rsi
0x18000a3c5  pop     rbp
0x18000a3c6  retn
0x18000a3c7  lea     rcx, [rbx+rbx*2]
0x18000a3cb  cmp     dword ptr [rdi+rcx*8], 0
0x18000a3cf  jnz     short loc_18000A3DD
0x18000a3d1  add     ebx, esi
0x18000a3d3  cmp     ebx, r14d
0x18000a3d6  jb      short loc_18000A3C7
0x18000a3d8  jmp     loc_18000A2BE
0x18000a3dd  lea     rcx, [rbx+rbx*2]
0x18000a3e1  mov     [rdi+rcx*8+4], esi
0x18000a3e5  mov     [rdi+rcx*8], esi
0x18000a3e8  mov     rax, [r15+8]
0x18000a3ec  mov     [rdi+rcx*8+8], rax
0x18000a3f1  mov     rax, [rbp+400h+arg_20]
0x18000a3f8  test    rax, rax
0x18000a3fb  jz      loc_18000A367
0x18000a401  mov     rax, [rax+8]
0x18000a405  test    rax, rax
0x18000a408  jz      loc_18000A367
0x18000a40e  mov     [rdi+rcx*8+10h], rax
0x18000a413  jmp     loc_18000A367
0x18000a418  mov     rax, [rsp+500h+Block]
0x18000a41d  mov     ebx, 8007000Eh
0x18000a422  jmp     loc_18000A381
  ... truncated ...
```
