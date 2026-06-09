# SLDepositTokenActivationResponse

- ea: `0x18003d2a0`
- end: `0x18003d8ec`
- name: `SLDepositTokenActivationResponse`
- size: `1612`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: ``

## callees

- `0x180004590`
- `0x180004ca0`
- `0x180006808`
- `0x180006c10`
- `0x18000760c`
- `0x180007638`
- `0x180016a0c`
- `0x180016b38`
- `0x180034f88`
- `0x180036550`
- `0x180036618`
- `0x1800369e0`
- `0x180036e68`
- `0x180039cec`
- `0x18003a27c`
- `0x18003b004`
- `0x18003b14c`
- `0x18003b178`
- `0x18003b228`
- `0x18003b354`
- `0x18003b79c`
- `0x18003b7f8`
- `0x18003b944`
- `0x18003c0d8`
- `0x18003c974`
- `0x18003cb14`
- `0x18003cc14`
- `0x18003cc9c`
- `0x18003cfdc`
- `0x18003d2a0`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`
- `0x18006ef3a`
- `0x18006ef80`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d7df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003d7df`
- `sppc!SLpDepositTokenActivationResponse` at `0x18003d75b`
- `sppc!SLpDepositTokenActivationResponse` at `0x18003d75b`
- `sppc!SLpGetTokenActivationGrantInfo` at `0x18003d5cd`
- `sppc!SLpGetTokenActivationGrantInfo` at `0x18003d5cd`
- `sppc!SLSetGenuineInformation` at `0x18003d7d1`
- `sppc!SLSetGenuineInformation` at `0x18003d7ff`
- `sppc!SLSetGenuineInformation` at `0x18003d841`
- `sppc!SLSetGenuineInformation` at `0x18003d7d1`
- `sppc!SLSetGenuineInformation` at `0x18003d7ff`
- `sppc!SLSetGenuineInformation` at `0x18003d841`

## string_xrefs

- `0x18003d7bc`: `SL_LAST_ACT_ATTEMPT_HRESULT`
- `0x18003d7f5`: `SL_LAST_ACT_ATTEMPT_TIME`
- `0x18003d837`: `SL_LAST_ACT_ATTEMPT_SERVER_FLAGS`

## pseudocode

```c
__int64 __fastcall SLDepositTokenActivationResponse(
        __int64 a1,
        const SLID *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8)
{
  int v12; // edi
  const wchar_t *v13; // rbx
  int TokenActivationGrantInfo; // eax
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rbx
  int v18; // esi
  int v19; // r14d
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rbx
  int v29; // eax
  int v31; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v33; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v34; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE pbValue[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v36; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v37[8]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h]
  _QWORD v52[10]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v53[16]; // [rsp+110h] [rbp+10h] BYREF

  v51 = a1;
  pCertContext = 0;
  v43 = 0;
  pChainContext = 0;
  v45 = 0;
  v33 = 0;
  memset(v52, 0, 0x48u);
  v49 = 0;
  v31 = 0;
  v41 = 0;
  v32 = 0;
  v48 = 0;
  v36 = 0;
  v40 = 0;
  v47 = 0;
  v46 = 0;
  v39 = 0;
  v34 = 0;
  v38 = 0;
  *(_DWORD *)pbValue = 0;
  SystemTimeAsFileTime = 0;
  *(_DWORD *)v37 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    sub_180004CA0(2147942487LL);
    goto LABEL_3;
  }
  TokenActivationGrantInfo = sub_180006808(a2, &v38);
  v12 = TokenActivationGrantInfo;
  if ( TokenActivationGrantInfo >= 0 )
  {
    if ( !a1 )
      goto LABEL_7;
    if ( !a3 )
      goto LABEL_7;
    sub_180043088(&dword_180082C04, qword_18008CB58);
    if ( !a4 || !a5 )
      goto LABEL_7;
    if ( !a6 )
    {
      v12 = -2147024809;
      sub_1800427F4(qword_1800824A0, qword_18008CFD0);
      goto LABEL_8;
    }
    sub_18004362C(&dword_180081DB4, byte_18008E278);
    if ( !a7 )
    {
      v12 = -2147024809;
      sub_180004CA0(2147942487LL);
      sub_180043364(qword_1800830F8, byte_18008D9F0);
      goto LABEL_57;
    }
    if ( !a8 )
    {
LABEL_7:
      v12 = -2147024809;
LABEL_8:
      sub_180004CA0(2147942487LL);
      goto LABEL_57;
    }
    TokenActivationGrantInfo = sub_180036E68(a8, a7, &pChainContext, &pCertContext);
    v12 = TokenActivationGrantInfo;
    if ( TokenActivationGrantInfo >= 0 )
    {
      v15 = sub_18003CB14(a6, a5, &v45, &v33);
      v12 = v15;
      if ( v15 == -2147024883 )
      {
LABEL_19:
        v12 = -1073417465;
LABEL_21:
        v16 = v12;
        goto LABEL_56;
      }
      if ( v15 < 0 )
        goto LABEL_21;
      TokenActivationGrantInfo = sub_18003C974(v52, v45, v33);
      v12 = TokenActivationGrantInfo;
      if ( TokenActivationGrantInfo >= 0 )
      {
        TokenActivationGrantInfo = sub_180036550(v52, a4, a3);
        v12 = TokenActivationGrantInfo;
        if ( TokenActivationGrantInfo >= 0 )
        {
          v12 = sub_18003CC9C(pChainContext);
          if ( v12 < 0 )
          {
            sub_180043900(&dword_180082634, &dword_18008D0CC);
            goto LABEL_21;
          }
          TokenActivationGrantInfo = sub_180036618(pCertContext);
          v12 = TokenActivationGrantInfo;
          if ( TokenActivationGrantInfo >= 0 )
          {
            TokenActivationGrantInfo = sub_18003B004(v52, &v49, &v31);
            v12 = TokenActivationGrantInfo;
            if ( TokenActivationGrantInfo >= 0 )
            {
              v17 = v52[0];
              v18 = 0;
              v19 = 0;
              if ( v52[0] && LODWORD(v52[7]) )
              {
                v18 = v52[6];
                v12 = 0;
                v19 = v52[7];
              }
              else
              {
                v12 = -2147418113;
                sub_180004CA0(2147549183LL);
              }
              sub_180006C10((unsigned int)v12);
              if ( v12 < 0 )
                goto LABEL_21;
              if ( v17 )
              {
                LODWORD(v17) = *(unsigned __int8 *)(v17 + 8);
                v12 = 0;
              }
              else
              {
                v12 = -2147418113;
                sub_180004CA0(2147549183LL);
              }
              sub_180006C10((unsigned int)v12);
              if ( v12 < 0 )
                goto LABEL_21;
              TokenActivationGrantInfo = sub_18003CFDC(v43, v49, v31, v18, v19);
              v12 = TokenActivationGrantInfo;
              if ( TokenActivationGrantInfo >= 0 )
              {
                v20 = v51;
                TokenActivationGrantInfo = SLpGetTokenActivationGrantInfo(v51, a2, &v32, &v41, &v36, &v48);
                v12 = TokenActivationGrantInfo;
                if ( TokenActivationGrantInfo >= 0 )
                {
                  v21 = sub_18003CC14(v32, v41, v36, v48);
                  v12 = v21;
                  if ( v21 == -2147024883 )
                    goto LABEL_19;
                  if ( v21 < 0 )
                    goto LABEL_21;
                  v24 = sub_1800369E0(v23, v22, &v40);
                  v12 = v24;
                  if ( v24 < 0 )
                  {
                    v16 = v24;
                    sub_180043EAC(byte_1800830C0, byte_18008D9C0);
                    goto LABEL_56;
                  }
                  TokenActivationGrantInfo = sub_18003A27C(v40, v41, v32);
                  v12 = TokenActivationGrantInfo;
                  if ( TokenActivationGrantInfo >= 0 )
                  {
                    TokenActivationGrantInfo = sub_180039CEC(
                                                 v40,
                                                 (_DWORD)pCertContext,
                                                 v17,
                                                 (_DWORD)pChainContext,
                                                 (__int64)&v47);
                    v12 = TokenActivationGrantInfo;
                    if ( TokenActivationGrantInfo >= 0 )
                    {
                      v27 = sub_1800369E0(v26, v25, &v46);
                      v12 = v27;
                      if ( v27 < 0 )
                      {
                        v16 = v27;
                        sub_180042ACC(byte_1800847C0, byte_18008CE60);
                        goto LABEL_56;
                      }
                      v28 = v46;
                      v31 = 82;
                      v29 = sub_18003B79C(v46, &v31, v45, v33);
                      v12 = v29;
                      if ( v29 < 0 )
                        sub_180004CA0((unsigned int)v29);
                      sub_180006C10((unsigned int)v12);
                      if ( v12 < 0 )
                        goto LABEL_21;
                      TokenActivationGrantInfo = sub_18003B944(v28, v47);
                      v12 = TokenActivationGrantInfo;
                      if ( TokenActivationGrantInfo >= 0 )
                      {
                        TokenActivationGrantInfo = sub_18003B7F8(v28, v43);
                        v12 = TokenActivationGrantInfo;
                        if ( TokenActivationGrantInfo >= 0 )
                        {
                          TokenActivationGrantInfo = sub_18003B354(v28, &v39, &v34);
                          v12 = TokenActivationGrantInfo;
                          if ( TokenActivationGrantInfo >= 0 )
                          {
                            TokenActivationGrantInfo = sub_18003C0D8(v34, v39, 16, v53);
                            v12 = TokenActivationGrantInfo;
                            if ( TokenActivationGrantInfo >= 0 )
                            {
                              TokenActivationGrantInfo = SLpDepositTokenActivationResponse(v20, a2, v34, v39, 16, v53);
                              v12 = TokenActivationGrantInfo;
                              if ( TokenActivationGrantInfo >= 0 )
                                goto LABEL_59;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v16 = TokenActivationGrantInfo;
LABEL_56:
  sub_180004CA0(v16);
  if ( v12 >= 0 )
  {
LABEL_59:
    sub_180016A0C(0, 1073754144, v38);
    goto LABEL_60;
  }
LABEL_57:
  v13 = v38;
  if ( v38 )
  {
    sub_180042DB0(qword_180084B90, &dword_18008D6F4);
    goto LABEL_4;
  }
LABEL_3:
  v13 = L"(null)";
LABEL_4:
  sub_180016B38(1, 3221237794LL, (unsigned int)v12, v13);
LABEL_60:
  *(_DWORD *)pbValue = v12;
  if ( SLSetGenuineInformation(a2, L"SL_LAST_ACT_ATTEMPT_HRESULT", SL_DATA_BINARY, 4u, pbValue) >= 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    SLSetGenuineInformation(a2, L"SL_LAST_ACT_ATTEMPT_TIME", SL_DATA_BINARY, 8u, (const BYTE *)&SystemTimeAsFileTime);
    if ( *(int *)pbValue >= 0 )
    {
      *(_DWORD *)v37 = -2147483647;
      sub_180042514(qword_180081158, byte_18008DA88);
      SLSetGenuineInformation(a2, L"SL_LAST_ACT_ATTEMPT_SERVER_FLAGS", SL_DATA_BINARY, 4u, v37);
    }
  }
  sub_180006C10((unsigned int)v12);
  sub_180007638(&v38);
  sub_180007638(&v39);
  sub_180004590(&v46);
  sub_18003B228(&v47);
  sub_180004590(&v40);
  sub_180007638(&v48);
  sub_180007638(&v41);
  sub_18000760C(v52);
  sub_18003B14C(&pChainContext);
  sub_180034F88(&v43);
  sub_180043BD8(byte_180081C10, qword_18008D8D0);
  sub_18003B178(&pCertContext);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003d2a0  push    rbp
0x18003d2a2  push    rbx
0x18003d2a3  push    rsi
0x18003d2a4  push    rdi
0x18003d2a5  push    r12
0x18003d2a7  push    r13
0x18003d2a9  push    r14
0x18003d2ab  push    r15
0x18003d2ad  lea     rbp, [rsp-38h]
0x18003d2b2  sub     rsp, 138h
0x18003d2b9  mov     rax, cs:__security_cookie
0x18003d2c0  xor     rax, rsp
0x18003d2c3  mov     [rbp+70h+var_50], rax
0x18003d2c7  mov     rsi, [rbp+70h+arg_28]
0x18003d2ce  xor     edi, edi
0x18003d2d0  mov     r14, [rbp+70h+arg_38]
0x18003d2d7  mov     r15d, r8d
0x18003d2da  mov     r13, rdx
0x18003d2dd  mov     [rbp+70h+var_B8], rcx
0x18003d2e1  mov     rbx, rcx
0x18003d2e4  mov     [rbp+70h+pCertContext], rdi
0x18003d2e8  lea     r8d, [rdi+48h]; Size
0x18003d2ec  mov     [rsp+170h+var_F8], rdi
0x18003d2f1  xor     edx, edx; Val
0x18003d2f3  mov     [rsp+170h+pChainContext], rdi
0x18003d2f8  lea     rcx, [rbp+70h+var_B0]; void *
0x18003d2fc  mov     [rbp+70h+var_E8], rdi
0x18003d300  mov     r12, r9
0x18003d303  mov     [rsp+170h+var_138], edi
0x18003d307  call    memset
0x18003d30c  mov     [rbp+70h+var_C8], rdi
0x18003d310  mov     [rsp+170h+var_140], edi
0x18003d314  mov     [rsp+170h+var_108], rdi
0x18003d319  mov     [rsp+170h+var_13C], edi
0x18003d31d  mov     [rbp+70h+var_D0], rdi
0x18003d321  mov     [rsp+170h+var_12C], edi
0x18003d325  mov     [rsp+170h+var_110], rdi
0x18003d32a  mov     [rbp+70h+var_D8], rdi
0x18003d32e  mov     [rbp+70h+var_E0], rdi
0x18003d332  mov     [rsp+170h+var_118], rdi
0x18003d337  mov     [rsp+170h+var_134], edi
0x18003d33b  mov     [rsp+170h+var_120], rdi
0x18003d340  mov     dword ptr [rsp+170h+var_130], edi
0x18003d344  mov     qword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18003d348  mov     dword ptr [rsp+170h+var_128], edi
0x18003d34c  test    r13, r13
0x18003d34f  jnz     short loc_18003D380
0x18003d351  mov     ebx, 80070057h
0x18003d356  mov     ecx, ebx
0x18003d358  mov     edi, ebx
0x18003d35a  call    sub_180004CA0
0x18003d35f  lea     rbx, aNull_0; "(null)"
0x18003d366  mov     ecx, 1
0x18003d36b  mov     r9, rbx
0x18003d36e  mov     r8d, edi
0x18003d371  mov     edx, 0C0003022h
0x18003d376  call    sub_180016B38
0x18003d37b  jmp     loc_18003D7AB
0x18003d380  lea     rdx, [rsp+170h+var_120]
0x18003d385  mov     rcx, r13
0x18003d388  call    sub_180006808
0x18003d38d  mov     edi, eax
0x18003d38f  test    eax, eax
0x18003d391  js      loc_18003D767
0x18003d397  test    rbx, rbx
0x18003d39a  jnz     short loc_18003D3AF
0x18003d39c  mov     ebx, 80070057h
0x18003d3a1  mov     edi, ebx
0x18003d3a3  mov     ecx, ebx
0x18003d3a5  call    sub_180004CA0
0x18003d3aa  jmp     loc_18003D774
0x18003d3af  test    r15d, r15d
0x18003d3b2  jz      short loc_18003D39C
0x18003d3b4  lea     rdx, qword_18008CB58
0x18003d3bb  lea     rcx, dword_180082C04
0x18003d3c2  call    sub_180043088
0x18003d3c7  test    r12, r12
0x18003d3ca  jz      short loc_18003D39C
0x18003d3cc  mov     ebx, [rbp+70h+arg_20]
0x18003d3d2  test    ebx, ebx
0x18003d3d4  jz      short loc_18003D39C
0x18003d3d6  test    rsi, rsi
0x18003d3d9  jnz     short loc_18003D3F7
0x18003d3db  mov     ebx, 80070057h
0x18003d3e0  lea     rdx, qword_18008CFD0
0x18003d3e7  lea     rcx, qword_1800824A0
0x18003d3ee  mov     edi, ebx
0x18003d3f0  call    sub_1800427F4
0x18003d3f5  jmp     short loc_18003D3A3
0x18003d3f7  lea     rdx, byte_18008E278
0x18003d3fe  lea     rcx, dword_180081DB4
0x18003d405  call    sub_18004362C
0x18003d40a  mov     edx, [rbp+70h+arg_30]
0x18003d410  test    edx, edx
0x18003d412  jnz     short loc_18003D43A
0x18003d414  mov     ebx, 80070057h
0x18003d419  mov     ecx, ebx
0x18003d41b  mov     edi, ebx
0x18003d41d  call    sub_180004CA0
0x18003d422  lea     rdx, byte_18008D9F0
0x18003d429  lea     rcx, qword_1800830F8
0x18003d430  call    sub_180043364
0x18003d435  jmp     loc_18003D774
0x18003d43a  test    r14, r14
0x18003d43d  jz      loc_18003D39C
0x18003d443  lea     r9, [rbp+70h+pCertContext]
0x18003d447  mov     rcx, r14
0x18003d44a  lea     r8, [rsp+170h+pChainContext]
0x18003d44f  call    sub_180036E68
0x18003d454  mov     edi, eax
0x18003d456  test    eax, eax
0x18003d458  js      loc_18003D767
0x18003d45e  lea     r9, [rsp+170h+var_138]
0x18003d463  mov     edx, ebx
0x18003d465  lea     r8, [rbp+70h+var_E8]
0x18003d469  mov     rcx, rsi
0x18003d46c  call    sub_18003CB14
0x18003d471  mov     edi, eax
0x18003d473  cmp     eax, 8007000Dh
0x18003d478  jnz     short loc_18003D481
0x18003d47a  mov     edi, 0C004F307h
0x18003d47f  jmp     short loc_18003D485
0x18003d481  test    eax, eax
0x18003d483  jns     short loc_18003D48C
0x18003d485  mov     ebx, edi
0x18003d487  jmp     loc_18003D769
0x18003d48c  mov     r8d, [rsp+170h+var_138]
0x18003d491  lea     rcx, [rbp+70h+var_B0]
0x18003d495  mov     rdx, [rbp+70h+var_E8]
0x18003d499  call    sub_18003C974
0x18003d49e  mov     edi, eax
0x18003d4a0  test    eax, eax
0x18003d4a2  js      loc_18003D767
0x18003d4a8  mov     r8d, r15d
0x18003d4ab  lea     rcx, [rbp+70h+var_B0]
0x18003d4af  mov     rdx, r12
0x18003d4b2  call    sub_180036550
0x18003d4b7  mov     edi, eax
0x18003d4b9  test    eax, eax
0x18003d4bb  js      loc_18003D767
0x18003d4c1  mov     rcx, [rsp+170h+pChainContext]; pChainContext
0x18003d4c6  call    sub_18003CC9C
0x18003d4cb  mov     edi, eax
0x18003d4cd  test    eax, eax
0x18003d4cf  jns     short loc_18003D4E6
0x18003d4d1  lea     rdx, dword_18008D0CC
0x18003d4d8  lea     rcx, dword_180082634
0x18003d4df  call    sub_180043900
0x18003d4e4  jmp     short loc_18003D485
0x18003d4e6  mov     rcx, [rbp+70h+pCertContext]; pCertContext
0x18003d4ea  lea     rdx, [rsp+170h+var_F8]
0x18003d4ef  call    sub_180036618
0x18003d4f4  mov     edi, eax
0x18003d4f6  test    eax, eax
0x18003d4f8  js      loc_18003D767
0x18003d4fe  lea     r8, [rsp+170h+var_140]
0x18003d503  lea     rdx, [rbp+70h+var_C8]
0x18003d507  lea     rcx, [rbp+70h+var_B0]
0x18003d50b  call    sub_18003B004
0x18003d510  mov     edi, eax
0x18003d512  test    eax, eax
0x18003d514  js      loc_18003D767
0x18003d51a  mov     rbx, [rbp+70h+var_B0]
0x18003d51e  xor     esi, esi
0x18003d520  xor     r14d, r14d
0x18003d523  mov     r15d, 8000FFFFh
0x18003d529  test    rbx, rbx
0x18003d52c  jnz     short loc_18003D53B
0x18003d52e  mov     ecx, r15d
0x18003d531  mov     edi, r15d
0x18003d534  call    sub_180004CA0
0x18003d539  jmp     short loc_18003D54B
0x18003d53b  mov     eax, [rbp+70h+var_78]
0x18003d53e  test    eax, eax
0x18003d540  jz      short loc_18003D52E
0x18003d542  mov     rsi, [rbp+70h+var_80]
0x18003d546  xor     edi, edi
0x18003d548  mov     r14d, eax
0x18003d54b  mov     ecx, edi
0x18003d54d  call    sub_180006C10
0x18003d552  test    edi, edi
0x18003d554  js      loc_18003D485
0x18003d55a  test    rbx, rbx
0x18003d55d  jnz     short loc_18003D56C
0x18003d55f  mov     ecx, r15d
0x18003d562  mov     edi, r15d
0x18003d565  call    sub_180004CA0
0x18003d56a  jmp     short loc_18003D572
0x18003d56c  movzx   ebx, byte ptr [rbx+8]
0x18003d570  xor     edi, edi
0x18003d572  mov     ecx, edi
0x18003d574  call    sub_180006C10
0x18003d579  test    edi, edi
0x18003d57b  js      loc_18003D485
0x18003d581  mov     r8d, [rsp+170h+var_140]
0x18003d586  mov     r9, rsi
0x18003d589  mov     rdx, [rbp+70h+var_C8]
0x18003d58d  mov     rcx, [rsp+170h+var_F8]
0x18003d592  mov     dword ptr [rsp+170h+pbValue], r14d
0x18003d597  call    sub_18003CFDC
0x18003d59c  mov     edi, eax
0x18003d59e  test    eax, eax
0x18003d5a0  js      loc_18003D767
0x18003d5a6  mov     rsi, [rbp+70h+var_B8]
0x18003d5aa  lea     rax, [rbp+70h+var_D0]
0x18003d5ae  mov     [rsp+170h+var_148], rax
0x18003d5b3  lea     r9, [rsp+170h+var_108]
0x18003d5b8  lea     rax, [rsp+170h+var_12C]
0x18003d5bd  mov     rdx, r13
0x18003d5c0  lea     r8, [rsp+170h+var_13C]
0x18003d5c5  mov     [rsp+170h+pbValue], rax
0x18003d5ca  mov     rcx, rsi
0x18003d5cd  call    cs:SLpGetTokenActivationGrantInfo
0x18003d5d3  mov     edi, eax
0x18003d5d5  test    eax, eax
0x18003d5d7  js      loc_18003D767
0x18003d5dd  mov     r9, [rbp+70h+var_D0]
0x18003d5e1  mov     r8d, [rsp+170h+var_12C]
0x18003d5e6  mov     rdx, [rsp+170h+var_108]
0x18003d5eb  mov     ecx, [rsp+170h+var_13C]
0x18003d5ef  call    sub_18003CC14
0x18003d5f4  mov     edi, eax
0x18003d5f6  cmp     eax, 8007000Dh
0x18003d5fb  jz      loc_18003D47A
0x18003d601  test    eax, eax
0x18003d603  js      loc_18003D485
0x18003d609  lea     r8, [rsp+170h+var_110]
0x18003d60e  call    sub_1800369E0
0x18003d613  mov     edi, eax
0x18003d615  test    eax, eax
0x18003d617  jns     short loc_18003D633
0x18003d619  lea     rdx, byte_18008D9C0
0x18003d620  mov     ebx, eax
0x18003d622  lea     rcx, byte_1800830C0
0x18003d629  call    sub_180043EAC
0x18003d62e  jmp     loc_18003D769
0x18003d633  mov     r8d, [rsp+170h+var_13C]
0x18003d638  mov     rdx, [rsp+170h+var_108]
0x18003d63d  mov     rcx, [rsp+170h+var_110]
0x18003d642  call    sub_18003A27C
0x18003d647  mov     edi, eax
0x18003d649  test    eax, eax
0x18003d64b  js      loc_18003D767
0x18003d651  mov     r9, [rsp+170h+pChainContext]
0x18003d656  lea     rax, [rbp+70h+var_D8]
0x18003d65a  mov     rdx, [rbp+70h+pCertContext]
0x18003d65e  mov     r8d, ebx
0x18003d661  mov     rcx, [rsp+170h+var_110]
0x18003d666  mov     [rsp+170h+pbValue], rax
0x18003d66b  call    sub_180039CEC
0x18003d670  mov     edi, eax
0x18003d672  test    eax, eax
0x18003d674  js      loc_18003D767
0x18003d67a  lea     r8, [rbp+70h+var_E0]
0x18003d67e  call    sub_1800369E0
0x18003d683  mov     edi, eax
0x18003d685  test    eax, eax
0x18003d687  jns     short loc_18003D6A3
0x18003d689  lea     rdx, byte_18008CE60
0x18003d690  mov     ebx, eax
0x18003d692  lea     rcx, byte_1800847C0
0x18003d699  call    sub_180042ACC
0x18003d69e  jmp     loc_18003D769
0x18003d6a3  mov     rbx, [rbp+70h+var_E0]
0x18003d6a7  lea     rdx, [rsp+170h+var_140]
0x18003d6ac  mov     r9d, [rsp+170h+var_138]
0x18003d6b1  mov     rcx, rbx
0x18003d6b4  mov     r8, [rbp+70h+var_E8]
0x18003d6b8  mov     [rsp+170h+var_140], 52h ; 'R'
0x18003d6c0  call    sub_18003B79C
0x18003d6c5  mov     edi, eax
0x18003d6c7  test    eax, eax
0x18003d6c9  jns     short loc_18003D6D2
0x18003d6cb  mov     ecx, eax
0x18003d6cd  call    sub_180004CA0
0x18003d6d2  mov     ecx, edi
0x18003d6d4  call    sub_180006C10
0x18003d6d9  test    edi, edi
0x18003d6db  js      loc_18003D485
0x18003d6e1  mov     rdx, [rbp+70h+var_D8]
0x18003d6e5  mov     rcx, rbx
0x18003d6e8  call    sub_18003B944
0x18003d6ed  mov     edi, eax
0x18003d6ef  test    eax, eax
0x18003d6f1  js      short loc_18003D767
0x18003d6f3  mov     rdx, [rsp+170h+var_F8]
0x18003d6f8  mov     rcx, rbx
0x18003d6fb  call    sub_18003B7F8
0x18003d700  mov     edi, eax
0x18003d702  test    eax, eax
0x18003d704  js      short loc_18003D767
0x18003d706  lea     r8, [rsp+170h+var_134]
0x18003d70b  mov     rcx, rbx
0x18003d70e  lea     rdx, [rsp+170h+var_118]
0x18003d713  call    sub_18003B354
0x18003d718  mov     edi, eax
0x18003d71a  test    eax, eax
0x18003d71c  js      short loc_18003D767
0x18003d71e  mov     rdx, [rsp+170h+var_118]
0x18003d723  lea     r9, [rbp+70h+var_60]
  ... truncated ...
```
