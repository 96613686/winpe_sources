# ICCInspector::Initialize(uchar const *,ulong)

- ea: `0x18003ca60`
- end: `0x18003cd68`
- name: `?Initialize@ICCInspector@@QEAAJPEBEK@Z`
- size: `776`
- prototype: `__int64 __fastcall(ICCInspector *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002af00`

## callees

- `0x180035e50`
- `0x18003ca60`
- `0x18003cd70`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x18003cb1e`
- `mscms!GetColorProfileHeader` at `0x18003cb1e`
- `mscms!IsColorProfileValid` at `0x18003cadb`
- `mscms!IsColorProfileValid` at `0x18003cadb`
- `mscms!CloseColorProfile` at `0x18003cd41`
- `mscms!CloseColorProfile` at `0x18003cd41`
- `mscms!OpenColorProfileW` at `0x18003cab3`
- `mscms!OpenColorProfileW` at `0x18003cab3`

## pseudocode

```c
__int64 __fastcall ICCInspector::Initialize(ICCInspector *this, unsigned __int8 *a2, DWORD a3)
{
  HPROFILE v4; // rax
  void *v5; // rdi
  char v7; // al
  unsigned int v8; // ebx
  __int64 v9; // xmm1_8
  BOOL pbValid; // [rsp+20h] [rbp-E0h] BYREF
  PROFILE pProfile; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  double v13; // [rsp+50h] [rbp-B0h]
  __int128 v14; // [rsp+58h] [rbp-A8h] BYREF
  double v15; // [rsp+68h] [rbp-98h]
  __int128 v16; // [rsp+70h] [rbp-90h] BYREF
  double v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+88h] [rbp-78h] BYREF
  double v19; // [rsp+98h] [rbp-68h]
  PROFILEHEADER pHeader; // [rsp+A0h] [rbp-60h] BYREF

  pProfile.pProfileData = a2;
  pProfile.cbDataSize = a3;
  *(_QWORD *)&pProfile.dwType = 2;
  *(&pProfile.cbDataSize + 1) = 0;
  v4 = OpenColorProfileW(&pProfile, 1u, 1u, 3u);
  v5 = v4;
  if ( !v4 )
    return 2147942487LL;
  pbValid = 0;
  if ( IsColorProfileValid(v4, &pbValid) )
  {
    if ( pbValid )
    {
      memset(&pHeader, 0, sizeof(pHeader));
      if ( GetColorProfileHeader(v5, &pHeader) )
      {
        if ( pHeader.phSignature == 1633907568 )
        {
          v7 = 1;
LABEL_10:
          *(_BYTE *)this = v7;
          v13 = 0.0;
          v12 = 0;
          v8 = 0;
          if ( ICCInspector::ReadXYZNumber(this, v5, 0x7258595Au, (struct CIEXYZNumber *)&v12) )
          {
            v15 = 0.0;
            v14 = 0;
            if ( ICCInspector::ReadXYZNumber(this, v5, 0x6758595Au, (struct CIEXYZNumber *)&v14) )
            {
              v17 = 0.0;
              v16 = 0;
              if ( ICCInspector::ReadXYZNumber(this, v5, 0x6258595Au, (struct CIEXYZNumber *)&v16) )
              {
                v19 = 0.0;
                v18 = 0;
                if ( ICCInspector::ReadXYZNumber(this, v5, 0x77747074u, (struct CIEXYZNumber *)&v18) )
                {
                  COERCE_DOUBLE(v9 = _mm_load_si128((const __m128i *)&_xmm).m128i_i64[0]);
                  if ( COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)&v12 - 0.673492) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*((double *)&v12 + 1) - 0.279022) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v13 - -0.001938) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)&v14 - 0.165634) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*((double *)&v14 + 1) - 0.675354) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v15 - 0.029999) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)&v16 - 0.125076) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*((double *)&v16 + 1) - 0.045609) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v17 - 0.796829) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*(double *)&v18 - 0.9505) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(*((double *)&v18 + 1) - 1.0) & v9) <= 0.01
                    && COERCE_DOUBLE(COERCE_UNSIGNED_INT64(v19 - 1.089005) & v9) <= 0.01 )
                  {
                    *((_BYTE *)this + 1) = 1;
                  }
                }
              }
            }
          }
          goto LABEL_28;
        }
        if ( pHeader.phSignature == 1886610273 )
        {
          v7 = 0;
          goto LABEL_10;
        }
      }
    }
  }
  v8 = -2147024809;
LABEL_28:
  CloseColorProfile(v5);
  return v8;
}

```

## disassembly

```asm
0x18003ca60  mov     [rsp-8+arg_18], rbx
0x18003ca65  push    rbp
0x18003ca66  push    rsi
0x18003ca67  push    rdi
0x18003ca68  lea     rbp, [rsp-30h]
0x18003ca6d  sub     rsp, 130h
0x18003ca74  mov     rax, cs:__security_cookie
0x18003ca7b  xor     rax, rsp
0x18003ca7e  mov     [rbp+40h+var_20], rax
0x18003ca82  mov     [rsp+140h+pProfile.pProfileData], rdx
0x18003ca87  mov     rsi, rcx
0x18003ca8a  mov     edx, 1; dwDesiredAccess
0x18003ca8f  mov     [rsp+140h+pProfile.cbDataSize], r8d
0x18003ca94  mov     r8d, edx; dwShareMode
0x18003ca97  mov     qword ptr [rsp+140h+pProfile.dwType], 2
0x18003caa0  mov     r9d, 3; dwCreationMode
0x18003caa6  mov     dword ptr [rsp+140h+pProfile+14h], 0
0x18003caae  lea     rcx, [rsp+140h+pProfile]; pProfile
0x18003cab3  call    cs:__imp_OpenColorProfileW
0x18003cab9  mov     rdi, rax
0x18003cabc  test    rax, rax
0x18003cabf  jnz     short loc_18003CACB
0x18003cac1  mov     eax, 80070057h
0x18003cac6  jmp     loc_18003CD49
0x18003cacb  lea     rdx, [rsp+140h+pbValid]; pbValid
0x18003cad0  mov     [rsp+140h+pbValid], 0
0x18003cad8  mov     rcx, rdi; hProfile
0x18003cadb  call    cs:__imp_IsColorProfileValid
0x18003cae1  test    eax, eax
0x18003cae3  jz      loc_18003CD39
0x18003cae9  cmp     [rsp+140h+pbValid], 0
0x18003caee  jz      loc_18003CD39
0x18003caf4  xorps   xmm0, xmm0
0x18003caf7  lea     rdx, [rbp+40h+pHeader]; pHeader
0x18003cafb  mov     rcx, rdi; hProfile
0x18003cafe  movups  xmmword ptr [rbp+40h+pHeader.phSize], xmm0
0x18003cb02  movups  xmmword ptr [rbp+40h+pHeader.phDataColorSpace], xmm0
0x18003cb06  movups  xmmword ptr [rbp+40h+pHeader.phDateTime+8], xmm0
0x18003cb0a  movups  xmmword ptr [rbp+40h+pHeader.phManufacturer], xmm0
0x18003cb0e  movups  xmmword ptr [rbp+40h+pHeader.phRenderingIntent], xmm0
0x18003cb12  movups  xmmword ptr [rbp+40h+pHeader.phCreator], xmm0
0x18003cb16  movups  xmmword ptr [rbp+40h+pHeader.phReserved+0Ch], xmm0
0x18003cb1a  movups  xmmword ptr [rbp+40h+pHeader.phReserved+1Ch], xmm0
0x18003cb1e  call    cs:__imp_GetColorProfileHeader
0x18003cb24  test    eax, eax
0x18003cb26  jz      loc_18003CD39
0x18003cb2c  mov     eax, [rbp+40h+pHeader.phSignature]
0x18003cb2f  cmp     eax, 61637370h
0x18003cb34  jnz     short loc_18003CB3A
0x18003cb36  mov     al, 1
0x18003cb38  jmp     short loc_18003CB47
0x18003cb3a  cmp     eax, 70736361h
0x18003cb3f  jnz     loc_18003CD39
0x18003cb45  xor     al, al
0x18003cb47  mov     [rsi], al
0x18003cb49  lea     r9, [rsp+140h+var_100]; struct CIEXYZNumber *
0x18003cb4e  xor     eax, eax
0x18003cb50  xorps   xmm0, xmm0
0x18003cb53  mov     r8d, 7258595Ah; unsigned int
0x18003cb59  mov     [rsp+140h+var_F0], rax
0x18003cb5e  mov     rdx, rdi; void *
0x18003cb61  mov     rcx, rsi; this
0x18003cb64  movups  [rsp+140h+var_100], xmm0
0x18003cb69  xor     ebx, ebx
0x18003cb6b  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003cb70  test    al, al
0x18003cb72  jz      loc_18003CD3E
0x18003cb78  xorps   xmm0, xmm0
0x18003cb7b  lea     r9, [rsp+140h+var_E8]; struct CIEXYZNumber *
0x18003cb80  xor     eax, eax
0x18003cb82  mov     r8d, 6758595Ah; unsigned int
0x18003cb88  mov     rdx, rdi; void *
0x18003cb8b  mov     [rsp+140h+var_D8], rax
0x18003cb90  mov     rcx, rsi; this
0x18003cb93  movups  [rsp+140h+var_E8], xmm0
0x18003cb98  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003cb9d  test    al, al
0x18003cb9f  jz      loc_18003CD3E
0x18003cba5  xorps   xmm0, xmm0
0x18003cba8  lea     r9, [rsp+140h+var_D0]; struct CIEXYZNumber *
0x18003cbad  xor     eax, eax
0x18003cbaf  mov     r8d, 6258595Ah; unsigned int
0x18003cbb5  mov     rdx, rdi; void *
0x18003cbb8  mov     [rbp+40h+var_C0], rax
0x18003cbbc  mov     rcx, rsi; this
0x18003cbbf  movups  [rsp+140h+var_D0], xmm0
0x18003cbc4  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003cbc9  test    al, al
0x18003cbcb  jz      loc_18003CD3E
0x18003cbd1  xorps   xmm0, xmm0
0x18003cbd4  lea     r9, [rbp+40h+var_B8]; struct CIEXYZNumber *
0x18003cbd8  xor     eax, eax
0x18003cbda  mov     r8d, 77747074h; unsigned int
0x18003cbe0  mov     rdx, rdi; void *
0x18003cbe3  mov     [rbp+40h+var_A8], rax
0x18003cbe7  mov     rcx, rsi; this
0x18003cbea  movups  [rbp+40h+var_B8], xmm0
0x18003cbee  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003cbf3  test    al, al
0x18003cbf5  jz      loc_18003CD3E
0x18003cbfb  movsd   xmm0, qword ptr [rsp+140h+var_100]
0x18003cc01  subsd   xmm0, cs:__real@3fe58d3f1843c3a4
0x18003cc09  movdqa  xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18003cc11  movsd   xmm2, cs:__real@3f847ae147ae147b
0x18003cc19  andps   xmm0, xmm1
0x18003cc1c  comisd  xmm2, xmm0
0x18003cc20  jb      loc_18003CD3E
0x18003cc26  movsd   xmm0, qword ptr [rsp+140h+var_100+8]
0x18003cc2c  subsd   xmm0, cs:__real@3fd1db7f1737542a
0x18003cc34  andps   xmm0, xmm1
0x18003cc37  comisd  xmm2, xmm0
0x18003cc3b  jb      loc_18003CD3E
0x18003cc41  movsd   xmm0, [rsp+140h+var_F0]
0x18003cc47  subsd   xmm0, cs:__real@bf5fc08fa7a85016
0x18003cc4f  andps   xmm0, xmm1
0x18003cc52  comisd  xmm2, xmm0
0x18003cc56  jb      loc_18003CD3E
0x18003cc5c  movsd   xmm0, qword ptr [rsp+140h+var_E8]
0x18003cc62  subsd   xmm0, cs:__real@3fc5337eb28d8666
0x18003cc6a  andps   xmm0, xmm1
0x18003cc6d  comisd  xmm2, xmm0
0x18003cc71  jb      loc_18003CD3E
0x18003cc77  movsd   xmm0, qword ptr [rsp+140h+var_E8+8]
0x18003cc7d  subsd   xmm0, cs:__real@3fe59c7ffde7210c
0x18003cc85  andps   xmm0, xmm1
0x18003cc88  comisd  xmm2, xmm0
0x18003cc8c  jb      loc_18003CD3E
0x18003cc92  movsd   xmm0, [rsp+140h+var_D8]
0x18003cc98  subsd   xmm0, cs:__real@3f9eb80ecfa69be1
0x18003cca0  andps   xmm0, xmm1
0x18003cca3  comisd  xmm2, xmm0
0x18003cca7  jb      loc_18003CD3E
0x18003ccad  movsd   xmm0, qword ptr [rsp+140h+var_D0]
0x18003ccb3  subsd   xmm0, cs:__real@3fc0027d88c1db01
0x18003ccbb  andps   xmm0, xmm1
0x18003ccbe  comisd  xmm2, xmm0
0x18003ccc2  jb      short loc_18003CD3E
0x18003ccc4  movsd   xmm0, qword ptr [rsp+140h+var_D0+8]
0x18003ccca  subsd   xmm0, cs:__real@3fa75a1016ce789e
0x18003ccd2  andps   xmm0, xmm1
0x18003ccd5  comisd  xmm2, xmm0
0x18003ccd9  jb      short loc_18003CD3E
0x18003ccdb  movsd   xmm0, [rbp+40h+var_C0]
0x18003cce0  subsd   xmm0, cs:__real@3fe97f9f87f023ea
0x18003cce8  andps   xmm0, xmm1
0x18003cceb  comisd  xmm2, xmm0
0x18003ccef  jb      short loc_18003CD3E
0x18003ccf1  movsd   xmm0, qword ptr [rbp+40h+var_B8]
0x18003ccf6  subsd   xmm0, cs:__real@3fee6a7ef9db22d1
0x18003ccfe  andps   xmm0, xmm1
0x18003cd01  comisd  xmm2, xmm0
0x18003cd05  jb      short loc_18003CD3E
0x18003cd07  movsd   xmm0, qword ptr [rbp+40h+var_B8+8]
0x18003cd0c  subsd   xmm0, cs:__real@3ff0000000000000
0x18003cd14  andps   xmm0, xmm1
0x18003cd17  comisd  xmm2, xmm0
0x18003cd1b  jb      short loc_18003CD3E
0x18003cd1d  movsd   xmm0, [rbp+40h+var_A8]
0x18003cd22  subsd   xmm0, cs:__real@3ff16c9081c2e33f
0x18003cd2a  andps   xmm0, xmm1
0x18003cd2d  comisd  xmm2, xmm0
0x18003cd31  jb      short loc_18003CD3E
0x18003cd33  mov     byte ptr [rsi+1], 1
0x18003cd37  jmp     short loc_18003CD3E
0x18003cd39  mov     ebx, 80070057h
0x18003cd3e  mov     rcx, rdi; hProfile
0x18003cd41  call    cs:__imp_CloseColorProfile
0x18003cd47  mov     eax, ebx
0x18003cd49  mov     rcx, [rbp+40h+var_20]
0x18003cd4d  xor     rcx, rsp; StackCookie
0x18003cd50  call    __security_check_cookie
0x18003cd55  mov     rbx, [rsp+140h+arg_18]
0x18003cd5d  add     rsp, 130h
0x18003cd64  pop     rdi
0x18003cd65  pop     rsi
0x18003cd66  pop     rbp
0x18003cd67  retn
```
