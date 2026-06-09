# ICCInspector::Initialize(uchar const *,ulong)

- ea: `0x18003d270`
- end: `0x18003d591`
- name: `?Initialize@ICCInspector@@QEAAJPEBEK@Z`
- size: `801`
- prototype: `__int64 __fastcall(ICCInspector *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b180`

## callees

- `0x180036420`
- `0x18003d270`
- `0x18003d5a0`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x18003d33a`
- `mscms!GetColorProfileHeader` at `0x18003d33a`
- `mscms!IsColorProfileValid` at `0x18003d2f1`
- `mscms!IsColorProfileValid` at `0x18003d2f1`
- `mscms!CloseColorProfile` at `0x18003d563`
- `mscms!CloseColorProfile` at `0x18003d563`
- `mscms!OpenColorProfileW` at `0x18003d2c3`
- `mscms!OpenColorProfileW` at `0x18003d2c3`

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
0x18003d270  mov     [rsp-8+arg_18], rbx
0x18003d275  push    rbp
0x18003d276  push    rsi
0x18003d277  push    rdi
0x18003d278  lea     rbp, [rsp-30h]
0x18003d27d  sub     rsp, 130h
0x18003d284  mov     rax, cs:__security_cookie
0x18003d28b  xor     rax, rsp
0x18003d28e  mov     [rbp+40h+var_20], rax
0x18003d292  mov     [rsp+140h+pProfile.pProfileData], rdx
0x18003d297  mov     rsi, rcx
0x18003d29a  mov     edx, 1; dwDesiredAccess
0x18003d29f  mov     [rsp+140h+pProfile.cbDataSize], r8d
0x18003d2a4  mov     r8d, edx; dwShareMode
0x18003d2a7  mov     qword ptr [rsp+140h+pProfile.dwType], 2
0x18003d2b0  mov     r9d, 3; dwCreationMode
0x18003d2b6  mov     dword ptr [rsp+140h+pProfile+14h], 0
0x18003d2be  lea     rcx, [rsp+140h+pProfile]; pProfile
0x18003d2c3  call    cs:__imp_OpenColorProfileW
0x18003d2ca  nop     dword ptr [rax+rax+00h]
0x18003d2cf  mov     rdi, rax
0x18003d2d2  test    rax, rax
0x18003d2d5  jnz     short loc_18003D2E1
0x18003d2d7  mov     eax, 80070057h
0x18003d2dc  jmp     loc_18003D571
0x18003d2e1  lea     rdx, [rsp+140h+pbValid]; pbValid
0x18003d2e6  mov     [rsp+140h+pbValid], 0
0x18003d2ee  mov     rcx, rdi; hProfile
0x18003d2f1  call    cs:__imp_IsColorProfileValid
0x18003d2f8  nop     dword ptr [rax+rax+00h]
0x18003d2fd  test    eax, eax
0x18003d2ff  jz      loc_18003D55B
0x18003d305  cmp     [rsp+140h+pbValid], 0
0x18003d30a  jz      loc_18003D55B
0x18003d310  xorps   xmm0, xmm0
0x18003d313  lea     rdx, [rbp+40h+pHeader]; pHeader
0x18003d317  mov     rcx, rdi; hProfile
0x18003d31a  movups  xmmword ptr [rbp+40h+pHeader.phSize], xmm0
0x18003d31e  movups  xmmword ptr [rbp+40h+pHeader.phDataColorSpace], xmm0
0x18003d322  movups  xmmword ptr [rbp+40h+pHeader.phDateTime+8], xmm0
0x18003d326  movups  xmmword ptr [rbp+40h+pHeader.phManufacturer], xmm0
0x18003d32a  movups  xmmword ptr [rbp+40h+pHeader.phRenderingIntent], xmm0
0x18003d32e  movups  xmmword ptr [rbp+40h+pHeader.phCreator], xmm0
0x18003d332  movups  xmmword ptr [rbp+40h+pHeader.phReserved+0Ch], xmm0
0x18003d336  movups  xmmword ptr [rbp+40h+pHeader.phReserved+1Ch], xmm0
0x18003d33a  call    cs:__imp_GetColorProfileHeader
0x18003d341  nop     dword ptr [rax+rax+00h]
0x18003d346  test    eax, eax
0x18003d348  jz      loc_18003D55B
0x18003d34e  mov     eax, [rbp+40h+pHeader.phSignature]
0x18003d351  cmp     eax, 61637370h
0x18003d356  jnz     short loc_18003D35C
0x18003d358  mov     al, 1
0x18003d35a  jmp     short loc_18003D369
0x18003d35c  cmp     eax, 70736361h
0x18003d361  jnz     loc_18003D55B
0x18003d367  xor     al, al
0x18003d369  mov     [rsi], al
0x18003d36b  lea     r9, [rsp+140h+var_100]; struct CIEXYZNumber *
0x18003d370  xor     eax, eax
0x18003d372  xorps   xmm0, xmm0
0x18003d375  mov     r8d, 7258595Ah; unsigned int
0x18003d37b  mov     [rsp+140h+var_F0], rax
0x18003d380  mov     rdx, rdi; void *
0x18003d383  mov     rcx, rsi; this
0x18003d386  movups  [rsp+140h+var_100], xmm0
0x18003d38b  xor     ebx, ebx
0x18003d38d  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003d392  test    al, al
0x18003d394  jz      loc_18003D560
0x18003d39a  xorps   xmm0, xmm0
0x18003d39d  lea     r9, [rsp+140h+var_E8]; struct CIEXYZNumber *
0x18003d3a2  xor     eax, eax
0x18003d3a4  mov     r8d, 6758595Ah; unsigned int
0x18003d3aa  mov     rdx, rdi; void *
0x18003d3ad  mov     [rsp+140h+var_D8], rax
0x18003d3b2  mov     rcx, rsi; this
0x18003d3b5  movups  [rsp+140h+var_E8], xmm0
0x18003d3ba  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003d3bf  test    al, al
0x18003d3c1  jz      loc_18003D560
0x18003d3c7  xorps   xmm0, xmm0
0x18003d3ca  lea     r9, [rsp+140h+var_D0]; struct CIEXYZNumber *
0x18003d3cf  xor     eax, eax
0x18003d3d1  mov     r8d, 6258595Ah; unsigned int
0x18003d3d7  mov     rdx, rdi; void *
0x18003d3da  mov     [rbp+40h+var_C0], rax
0x18003d3de  mov     rcx, rsi; this
0x18003d3e1  movups  [rsp+140h+var_D0], xmm0
0x18003d3e6  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003d3eb  test    al, al
0x18003d3ed  jz      loc_18003D560
0x18003d3f3  xorps   xmm0, xmm0
0x18003d3f6  lea     r9, [rbp+40h+var_B8]; struct CIEXYZNumber *
0x18003d3fa  xor     eax, eax
0x18003d3fc  mov     r8d, 77747074h; unsigned int
0x18003d402  mov     rdx, rdi; void *
0x18003d405  mov     [rbp+40h+var_A8], rax
0x18003d409  mov     rcx, rsi; this
0x18003d40c  movups  [rbp+40h+var_B8], xmm0
0x18003d410  call    ?ReadXYZNumber@ICCInspector@@AEAA_NPEAXKPEAUCIEXYZNumber@@@Z; ICCInspector::ReadXYZNumber(void *,ulong,CIEXYZNumber *)
0x18003d415  test    al, al
0x18003d417  jz      loc_18003D560
0x18003d41d  movsd   xmm0, qword ptr [rsp+140h+var_100]
0x18003d423  subsd   xmm0, cs:__real@3fe58d3f1843c3a4
0x18003d42b  movdqa  xmm1, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x18003d433  movsd   xmm2, cs:__real@3f847ae147ae147b
0x18003d43b  andps   xmm0, xmm1
0x18003d43e  comisd  xmm2, xmm0
0x18003d442  jb      loc_18003D560
0x18003d448  movsd   xmm0, qword ptr [rsp+140h+var_100+8]
0x18003d44e  subsd   xmm0, cs:__real@3fd1db7f1737542a
0x18003d456  andps   xmm0, xmm1
0x18003d459  comisd  xmm2, xmm0
0x18003d45d  jb      loc_18003D560
0x18003d463  movsd   xmm0, [rsp+140h+var_F0]
0x18003d469  subsd   xmm0, cs:__real@bf5fc08fa7a85016
0x18003d471  andps   xmm0, xmm1
0x18003d474  comisd  xmm2, xmm0
0x18003d478  jb      loc_18003D560
0x18003d47e  movsd   xmm0, qword ptr [rsp+140h+var_E8]
0x18003d484  subsd   xmm0, cs:__real@3fc5337eb28d8666
0x18003d48c  andps   xmm0, xmm1
0x18003d48f  comisd  xmm2, xmm0
0x18003d493  jb      loc_18003D560
0x18003d499  movsd   xmm0, qword ptr [rsp+140h+var_E8+8]
0x18003d49f  subsd   xmm0, cs:__real@3fe59c7ffde7210c
0x18003d4a7  andps   xmm0, xmm1
0x18003d4aa  comisd  xmm2, xmm0
0x18003d4ae  jb      loc_18003D560
0x18003d4b4  movsd   xmm0, [rsp+140h+var_D8]
0x18003d4ba  subsd   xmm0, cs:__real@3f9eb80ecfa69be1
0x18003d4c2  andps   xmm0, xmm1
0x18003d4c5  comisd  xmm2, xmm0
0x18003d4c9  jb      loc_18003D560
0x18003d4cf  movsd   xmm0, qword ptr [rsp+140h+var_D0]
0x18003d4d5  subsd   xmm0, cs:__real@3fc0027d88c1db01
0x18003d4dd  andps   xmm0, xmm1
0x18003d4e0  comisd  xmm2, xmm0
0x18003d4e4  jb      short loc_18003D560
0x18003d4e6  movsd   xmm0, qword ptr [rsp+140h+var_D0+8]
0x18003d4ec  subsd   xmm0, cs:__real@3fa75a1016ce789e
0x18003d4f4  andps   xmm0, xmm1
0x18003d4f7  comisd  xmm2, xmm0
0x18003d4fb  jb      short loc_18003D560
0x18003d4fd  movsd   xmm0, [rbp+40h+var_C0]
0x18003d502  subsd   xmm0, cs:__real@3fe97f9f87f023ea
0x18003d50a  andps   xmm0, xmm1
0x18003d50d  comisd  xmm2, xmm0
0x18003d511  jb      short loc_18003D560
0x18003d513  movsd   xmm0, qword ptr [rbp+40h+var_B8]
0x18003d518  subsd   xmm0, cs:__real@3fee6a7ef9db22d1
0x18003d520  andps   xmm0, xmm1
0x18003d523  comisd  xmm2, xmm0
0x18003d527  jb      short loc_18003D560
0x18003d529  movsd   xmm0, qword ptr [rbp+40h+var_B8+8]
0x18003d52e  subsd   xmm0, cs:__real@3ff0000000000000
0x18003d536  andps   xmm0, xmm1
0x18003d539  comisd  xmm2, xmm0
0x18003d53d  jb      short loc_18003D560
0x18003d53f  movsd   xmm0, [rbp+40h+var_A8]
0x18003d544  subsd   xmm0, cs:__real@3ff16c9081c2e33f
0x18003d54c  andps   xmm0, xmm1
0x18003d54f  comisd  xmm2, xmm0
0x18003d553  jb      short loc_18003D560
0x18003d555  mov     byte ptr [rsi+1], 1
0x18003d559  jmp     short loc_18003D560
0x18003d55b  mov     ebx, 80070057h
0x18003d560  mov     rcx, rdi; hProfile
0x18003d563  call    cs:__imp_CloseColorProfile
0x18003d56a  nop     dword ptr [rax+rax+00h]
0x18003d56f  mov     eax, ebx
0x18003d571  mov     rcx, [rbp+40h+var_20]
0x18003d575  xor     rcx, rsp; StackCookie
0x18003d578  call    __security_check_cookie
0x18003d57d  mov     rbx, [rsp+140h+arg_18]
0x18003d585  add     rsp, 130h
0x18003d58c  pop     rdi
0x18003d58d  pop     rsi
0x18003d58e  pop     rbp
0x18003d58f  retn
```
