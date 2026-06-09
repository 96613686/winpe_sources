# CTEsConvertToWstr<167,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10041b930`
- end: `0x10041bb22`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0KH@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x10041b910`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100410bc0`
- `0x100411950`
- `0x10041b930`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10070e38c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10070e38c`
- `sqldk!SystemThread_TlsIndex` at `0x10070e2c8`
- `sqldk!SystemThread_TlsOffset` at `0x10070e2d1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070e2ec`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070e2ec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070e3cb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070e3cb`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10041b9db`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070e1a3`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070e1d1`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10041b9db`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070e1a3`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070e1d1`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10041b9eb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070e1af`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070e1dd`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10041b9eb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070e1af`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070e1dd`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e18b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e1c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e1f4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e18b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e1c2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070e1f4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070e406`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070e42f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070e406`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070e42f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070e415`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070e415`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int16 __fastcall CTEsConvertToWstr<167,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // r12d
  char v9; // r13
  __int64 v10; // rax
  __int64 v11; // rax
  bool v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rcx
  struct CSessionTraceFlags *v15; // rax
  __int64 v16; // rdx
  unsigned __int8 *v17; // r8
  __int64 v18; // r13
  bool v19; // al
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct CSessionTraceFlags *v23; // rax
  struct CSessionTraceFlags *v24; // rax
  __int64 v25; // rax
  unsigned __int16 v26; // ax
  const struct CDefaultCollation *v27; // r15
  __int64 v28; // r9
  const struct CTypeInfo *v29; // r14
  __int64 v30; // rdi
  __int64 v31; // rdx
  wchar_t *v32; // rsi
  unsigned int v33; // eax
  unsigned __int64 v34; // rdi
  char v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 *v38; // [rsp+68h] [rbp-98h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[16]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v41; // [rsp+A0h] [rbp-60h]
  int v42; // [rsp+A4h] [rbp-5Ch]
  __int64 v43; // [rsp+B0h] [rbp-50h]
  wchar_t *v44; // [rsp+B8h] [rbp-48h]
  _BYTE v45[208]; // [rsp+C0h] [rbp-40h] BYREF

  v43 = -2;
  v4 = a1[4];
  v5 = *(unsigned int *)(v4 + 8);
  v6 = 0;
  if ( (int)v5 > 0 )
    LOBYTE(v6) = *(_BYTE *)(a2 + 32) == 3;
  v7 = *(unsigned __int8 *)(v4 + 26);
  v8 = *((_DWORD *)&x_uiCodePage + v7);
  if ( !v8 )
  {
    if ( (int)v5 <= 0 )
      v8 = *(_DWORD *)(a2 + 40);
    else
      v8 = *(_DWORD *)(a2 + 72);
  }
  if ( (_DWORD)v6 )
  {
    *(_BYTE *)a2 = 3;
  }
  else
  {
    v9 = *(_BYTE *)(v4 + 16);
    v36 = v9;
    v10 = a1[9];
    v12 = 0;
    if ( v10 )
    {
      v11 = *(_QWORD *)(v10 + 408);
      if ( v11 )
      {
        if ( *(_QWORD *)(v11 + 424) )
          v12 = 1;
      }
    }
    if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v6, v5) + 57) & 0x10) != 0
       || (v15 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v15, 0x1CCu))
      && v9 == 1
      && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v14, v13) + 57) & 8) == 0
       && ((v23 = PSessTraceFlags()) == 0 || !CSessionTraceFlags::CheckSessionTraceInternal(v23, 0x1CBu))
       && v12
       || ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v22, v21) + 57) & 8) != 0
        || (v24 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v24, 0x1CBu))
       && !v12) )
    {
      v36 = 2;
    }
    v37 = *(unsigned __int8 *)(v4 + 15);
    v16 = *(unsigned __int16 *)(a1[4] + 18LL);
    v17 = *(unsigned __int8 **)(a1[7] + 8 * v16);
    v38 = v17;
    v7 = a1[2];
    v18 = *(unsigned __int16 *)(*(_QWORD *)(v7 + 32) + 2 * v16);
    if ( *(_BYTE *)a2 )
    {
      *(_QWORD *)(a2 + 8) = v17;
      *(_QWORD *)(a2 + 16) = v18;
    }
    else
    {
      v39.m256i_i32[0] = 59139;
      memset(&v39.m256i_u64[1], 0, 20);
      CTypeInfo::InitWithMaxLen((CTypeInfo *)v40, 0xE7u, v18);
      if ( v40[0] == 98 )
        v41 = 2;
      if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v40[0]))
        || ((v40[0] - 35) & 0xBF) == 0 )
      {
        v19 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v40);
        v20 = v42;
        if ( v19 )
          v20 = -1;
        v42 = v20;
      }
      CXVariant::CopyFromPbInternal((CXVariant *)&v39, v38, v18, (const struct CTypeInfo *)v40, 0);
      CXVariant::WstrConvertFromStr(&v39, *(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16), v37, v8, v36);
      *(__m256i *)a2 = v39;
      LOWORD(v7) = -2;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
    if ( *(_BYTE *)(v4 + 16) == 1 )
    {
      LOWORD(v7) = *(_WORD *)(a2 + 2) >> 12;
      if ( (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
      {
        v25 = 0;
        v37 = 0;
        if ( !v12 )
        {
LABEL_51:
          LOWORD(v7) = ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v25, v45);
          return v7;
        }
        (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
          x_pContextProvider,
          &v38);
        (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider + 8LL))(
          x_pContextProvider,
          v38);
        v26 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
        v27 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                                  x_pIDbTableProvider,
                                                  v26);
        v28 = a1[4];
        v29 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v28 + 24));
        v30 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v31 = *(_QWORD *)(v30 + 256);
        if ( !v31 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v31 = *(_QWORD *)(v30 + 256);
          v28 = a1[4];
        }
        v32 = CXVariant::PwchConvertToStringInternal(
                *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v28 + 12)),
                *(struct IMemObj **)(v31 + 1000),
                &v37,
                *(struct IMemObj **)(v31 + 1000),
                v29,
                v27,
                2,
                0,
                0,
                0,
                0,
                0);
        v44 = v32;
        if ( v32 )
        {
          v33 = v37;
          if ( v37 >= 0x64 )
            v33 = 100;
          v37 = v33;
        }
        else
        {
          v33 = 0;
          v37 = 0;
        }
        v34 = 2LL * v33;
        if ( v34 )
        {
          if ( v32 && v34 <= 0xC8 )
          {
            memmove(v45, v32, 2LL * v33);
          }
          else
          {
            memset_0(v45, 0, 0xC8u);
            if ( v32 )
            {
              if ( v34 <= 0xC8 )
                goto LABEL_50;
              *_errno() = 34;
            }
            else
            {
              *_errno() = 22;
            }
            _invalid_parameter_noinfo();
          }
        }
LABEL_50:
        operator delete[](v32);
        v25 = v37;
        goto LABEL_51;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x10041b930  push    rbp
0x10041b932  push    rsi
0x10041b933  push    rdi
0x10041b934  push    r12
0x10041b936  push    r13
0x10041b938  push    r14
0x10041b93a  push    r15
0x10041b93c  lea     rbp, [rsp-0A0h]
0x10041b944  sub     rsp, 1A0h
0x10041b94b  mov     [rbp+0D0h+var_120], 0FFFFFFFFFFFFFFFEh
0x10041b953  mov     [rsp+1D0h+arg_10], rbx
0x10041b95b  mov     rax, cs:__security_cookie
0x10041b962  xor     rax, rsp
0x10041b965  mov     [rbp+0D0h+var_40], rax
0x10041b96c  mov     rdi, rdx
0x10041b96f  mov     rsi, rcx
0x10041b972  mov     r14, [rcx+20h]
0x10041b976  mov     edx, [r14+8]
0x10041b97a  xor     ebx, ebx
0x10041b97c  mov     ecx, ebx
0x10041b97e  test    edx, edx
0x10041b980  jg      loc_10070E14D
0x10041b986  movzx   eax, byte ptr [r14+1Ah]
0x10041b98b  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10041b992  mov     r12d, ds:rva ?x_uiCodePage@@3QBIB[r8+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x10041b99a  test    r12d, r12d
0x10041b99d  jz      loc_10070E15A
0x10041b9a3  test    ecx, ecx
0x10041b9a5  jnz     loc_10070E171
0x10041b9ab  movzx   r13d, byte ptr [r14+10h]
0x10041b9b0  mov     [rsp+1D0h+var_170], r13b
0x10041b9b5  mov     rax, [rsi+48h]
0x10041b9b9  test    rax, rax
0x10041b9bc  jz      short loc_10041B9D8
0x10041b9be  mov     rax, [rax+198h]
0x10041b9c5  test    rax, rax
0x10041b9c8  jz      short loc_10041B9D8
0x10041b9ca  cmp     qword ptr [rax+1A8h], 0
0x10041b9d2  jnz     loc_10070E17A
0x10041b9d8  xor     r15b, r15b
0x10041b9db  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10041b9e1  test    byte ptr [rax+39h], 10h
0x10041b9e5  jnz     loc_10070E199
0x10041b9eb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10041b9f1  test    rax, rax
0x10041b9f4  jnz     loc_10070E183
0x10041b9fa  movzx   eax, byte ptr [r14+0Fh]
0x10041b9ff  mov     [rsp+1D0h+var_16C], eax
0x10041ba03  mov     rax, [rsi+20h]
0x10041ba07  movzx   edx, word ptr [rax+12h]
0x10041ba0b  mov     rax, [rsi+38h]
0x10041ba0f  mov     r8, [rax+rdx*8]
0x10041ba13  mov     [rsp+1D0h+var_168], r8
0x10041ba18  mov     rax, [rsi+10h]
0x10041ba1c  mov     rcx, [rax+20h]
0x10041ba20  movzx   r13d, word ptr [rcx+rdx*2]
0x10041ba25  cmp     byte ptr [rdi], 0
0x10041ba28  jnz     loc_10070E216
0x10041ba2e  mov     dword ptr [rsp+1D0h+var_160], 0E703h
0x10041ba36  xorps   xmm0, xmm0
0x10041ba39  movdqu  [rsp+1D0h+var_160+8], xmm0
0x10041ba3f  mov     [rbp+0D0h+var_148], ebx
0x10041ba42  mov     r8d, r13d; int
0x10041ba45  mov     dl, 0E7h; unsigned __int8
0x10041ba47  lea     rcx, [rbp+0D0h+var_140]; this
0x10041ba4b  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10041ba50  movzx   edx, [rbp+0D0h+var_140]
0x10041ba54  cmp     dl, 62h ; 'b'
0x10041ba57  jz      loc_10070E224
0x10041ba5d  lea     r8, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10041ba64  movzx   ecx, byte ptr [rdx+r8+45AE60h]
0x10041ba6d  cmp     byte ptr [rcx+r8+45AFC0h], 0
0x10041ba76  jz      loc_10070E233
0x10041ba7c  lea     rcx, [rbp+0D0h+var_140]; this
0x10041ba80  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10041ba85  mov     ecx, [rbp+0D0h+var_12C]
0x10041ba88  mov     edx, 0FFFFFFFFh
0x10041ba8d  test    al, al
0x10041ba8f  cmovnz  ecx, edx
0x10041ba92  mov     [rbp+0D0h+var_12C], ecx
0x10041ba95  mov     dword ptr [rsp+1D0h+var_1B0], ebx; int
0x10041ba99  lea     r9, [rbp+0D0h+var_140]; struct CTypeInfo *
0x10041ba9d  mov     r8d, r13d; unsigned int
0x10041baa0  mov     rdx, [rsp+1D0h+var_168]; unsigned __int8 *
0x10041baa5  lea     rcx, [rsp+1D0h+var_160]; this
0x10041baaa  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10041baaf  movzx   eax, [rsp+1D0h+var_170]
0x10041bab4  mov     byte ptr [rsp+1D0h+var_1A8], al
0x10041bab8  mov     dword ptr [rsp+1D0h+var_1B0], r12d
0x10041babd  mov     r9d, [rsp+1D0h+var_16C]
0x10041bac2  mov     r8d, [rdi+10h]
0x10041bac6  mov     rdx, [rdi+8]
0x10041baca  lea     rcx, [rsp+1D0h+var_160]
0x10041bacf  call    ?WstrConvertFromStr@CXVariant@@QEAAJPEBDKW4EPadding@@IW4EErrorHandling@@@Z; CXVariant::WstrConvertFromStr(char const *,ulong,EPadding,uint,EErrorHandling)
0x10041bad4  movups  xmm0, [rsp+1D0h+var_160]
0x10041bad9  movups  xmmword ptr [rdi], xmm0
0x10041badc  movups  xmm1, xmmword ptr [rbp-80h]
0x10041bae0  movups  xmmword ptr [rdi+10h], xmm1
0x10041bae4  mov     eax, 0FFFEh
0x10041bae9  and     [rdi+2], ax
0x10041baed  cmp     byte ptr [r14+10h], 1
0x10041baf2  jz      loc_10070E245
0x10041baf8  mov     rcx, [rbp+0D0h+var_40]
0x10041baff  xor     rcx, rsp; StackCookie
0x10041bb02  call    __security_check_cookie
0x10041bb07  mov     rbx, [rsp+1D0h+arg_10]
0x10041bb0f  add     rsp, 1A0h
0x10041bb16  pop     r15
0x10041bb18  pop     r14
0x10041bb1a  pop     r13
0x10041bb1c  pop     r12
0x10041bb1e  pop     rdi
0x10041bb1f  pop     rsi
0x10041bb20  pop     rbp
0x10041bb21  retn
0x10070e14d  cmp     byte ptr [rdi+20h], 3
0x10070e151  setz    cl
0x10070e154  jmp     loc_10041B986
0x10070e15a  test    edx, edx
0x10070e15c  jle     short loc_10070E167
0x10070e15e  mov     r12d, [rdi+48h]
0x10070e162  jmp     loc_10041B9A3
0x10070e167  mov     r12d, [rdi+28h]
0x10070e16b  jmp     loc_10041B9A3
0x10070e171  mov     byte ptr [rdi], 3
0x10070e174  jmp     loc_10041BAF8
0x10070e17a  mov     r15b, 1
0x10070e17d  jmp     loc_10041B9DB
0x10070e183  mov     edx, 1CCh
0x10070e188  mov     rcx, rax
0x10070e18b  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070e191  test    eax, eax
0x10070e193  jz      loc_10041B9FA
0x10070e199  cmp     r13b, 1
0x10070e19d  jnz     loc_10041B9FA
0x10070e1a3  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070e1a9  test    byte ptr [rax+39h], 8
0x10070e1ad  jnz     short loc_10070E1D1
0x10070e1af  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070e1b5  test    rax, rax
0x10070e1b8  jz      short loc_10070E1CC
0x10070e1ba  mov     edx, 1CBh
0x10070e1bf  mov     rcx, rax
0x10070e1c2  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070e1c8  test    eax, eax
0x10070e1ca  jnz     short loc_10070E1D1
0x10070e1cc  test    r15b, r15b
0x10070e1cf  jnz     short loc_10070E20B
0x10070e1d1  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070e1d7  test    byte ptr [rax+39h], 8
0x10070e1db  jnz     short loc_10070E202
0x10070e1dd  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070e1e3  test    rax, rax
0x10070e1e6  jz      loc_10041B9FA
0x10070e1ec  mov     edx, 1CBh
0x10070e1f1  mov     rcx, rax
0x10070e1f4  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070e1fa  test    eax, eax
0x10070e1fc  jz      loc_10041B9FA
0x10070e202  test    r15b, r15b
0x10070e205  jnz     loc_10041B9FA
0x10070e20b  mov     [rsp+1D0h+var_170], 2
0x10070e210  jmp     loc_10041B9FA
0x10070e216  mov     [rdi+8], r8
0x10070e21a  mov     [rdi+10h], r13
0x10070e21e  jmp     loc_10041BAED
0x10070e224  mov     eax, 2
0x10070e229  mov     [rbp+0D0h+var_130], ax
0x10070e22d  jmp     loc_10041BA5D
0x10070e233  sub     dl, 23h ; '#'
0x10070e236  test    dl, 0BFh
0x10070e239  jz      loc_10041BA7C
0x10070e23f  jmp     loc_10041BA95
0x10070e245  movzx   eax, word ptr [rdi+2]
0x10070e249  shr     ax, 0Ch
0x10070e24d  test    al, 1
0x10070e24f  jz      loc_10041BAF8
0x10070e255  mov     eax, ebx
0x10070e257  mov     [rsp+1D0h+var_16C], eax
0x10070e25b  test    r15b, r15b
0x10070e25e  jz      loc_10070E396
0x10070e264  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070e26b  mov     rax, [rcx]
0x10070e26e  lea     rdx, [rsp+1D0h+var_168]
0x10070e273  call    qword ptr [rax]
0x10070e275  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070e27c  mov     rax, [rcx]
0x10070e27f  mov     rdx, [rsp+1D0h+var_168]
0x10070e284  call    qword ptr [rax+8]
0x10070e287  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10070e28e  mov     rax, [rcx]
0x10070e291  call    qword ptr [rax]
0x10070e293  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10070e29a  mov     r8, [rcx]
0x10070e29d  movzx   edx, ax
0x10070e2a0  call    qword ptr [r8+8]
0x10070e2a4  mov     r15, rax
0x10070e2a7  mov     r9, [rsi+20h]
0x10070e2ab  movzx   r14d, word ptr [r9+18h]
0x10070e2b0  shl     r14, 5
0x10070e2b4  mov     rcx, [rsi+10h]
0x10070e2b8  add     r14, [rcx+0A8h]
0x10070e2bf  mov     r8, gs:58h
0x10070e2c8  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10070e2cf  mov     edx, [rcx]
0x10070e2d1  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10070e2d8  mov     edi, [rcx]
0x10070e2da  add     rdi, [r8+rdx*8]
0x10070e2de  mov     rdx, [rdi+100h]
0x10070e2e5  test    rdx, rdx
0x10070e2e8  jnz     short loc_10070E2FD
0x10070e2ea  xor     ecx, ecx
0x10070e2ec  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10070e2f2  mov     rdx, [rdi+100h]
0x10070e2f9  mov     r9, [rsi+20h]
0x10070e2fd  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10070e304  mov     ecx, [r9+0Ch]
0x10070e308  mov     rax, [rsi+30h]
0x10070e30c  mov     [rsp+1D0h+var_178], ebx; int
0x10070e310  mov     [rsp+1D0h+var_180], ebx; unsigned int
0x10070e314  mov     [rsp+1D0h+var_188], rbx; wchar_t *
0x10070e319  mov     [rsp+1D0h+var_190], ebx; unsigned int
0x10070e31d  mov     [rsp+1D0h+Src], rbx; Src
0x10070e322  mov     [rsp+1D0h+var_1A0], 2; int
0x10070e32a  mov     [rsp+1D0h+var_1A8], r15; struct CDefaultCollation *
0x10070e32f  mov     [rsp+1D0h+var_1B0], r14; struct CTypeInfo *
0x10070e334  mov     r9, rdx; struct IMemObj *
0x10070e337  lea     r8, [rsp+1D0h+var_16C]; unsigned int *
0x10070e33c  mov     rcx, [rax+rcx*8]; this
0x10070e340  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10070e345  mov     rsi, rax
0x10070e348  mov     [rbp+0D0h+var_118], rax
0x10070e34c  test    rax, rax
0x10070e34f  jnz     loc_10070E3D8
0x10070e355  mov     eax, ebx
0x10070e357  mov     [rsp+1D0h+var_16C], ebx
0x10070e35b  jmp     short loc_10070E35E
0x10070e35e  mov     edi, eax
0x10070e360  add     rdi, rdi
0x10070e363  jz      short loc_10070E389
0x10070e365  test    rsi, rsi
0x10070e368  jz      loc_10070E3F0
0x10070e36e  cmp     rdi, 0C8h
0x10070e375  ja      short loc_10070E3F0
0x10070e377  mov     r8, rdi; Size
0x10070e37a  mov     rdx, rsi; Src
0x10070e37d  lea     rcx, [rbp+0D0h+var_110]; void *
0x10070e381  call    memmove
0x10070e386  jmp     short loc_10070E389
0x10070e389  mov     rcx, rsi
0x10070e38c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10070e392  mov     eax, [rsp+1D0h+var_16C]
0x10070e396  add     rax, rax
0x10070e399  lea     rcx, [rbp+0D0h+var_110]
0x10070e39d  mov     [rsp+1D0h+var_188], rcx
0x10070e3a2  mov     qword ptr [rsp+1D0h+var_190], rax
0x10070e3a7  mov     [rsp+1D0h+Src], rbx
0x10070e3ac  mov     qword ptr [rsp+1D0h+var_1A0], rbx
0x10070e3b1  mov     [rsp+1D0h+var_1A8], rbx
0x10070e3b6  mov     [rsp+1D0h+var_1B0], rbx
0x10070e3bb  mov     edx, 1Ch
0x10070e3c0  lea     ecx, [rdx-2]
0x10070e3c3  lea     r9d, [rdx-1Ah]
0x10070e3c7  lea     r8d, [rdx-0Ch]
0x10070e3cb  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10070e3d1  nop
0x10070e3d2  jmp     loc_10041BAF8
0x10070e3d8  mov     eax, [rsp+1D0h+var_16C]
0x10070e3dc  mov     ecx, 64h ; 'd'
0x10070e3e1  cmp     eax, ecx
0x10070e3e3  cmovnb  eax, ecx
0x10070e3e6  mov     [rsp+1D0h+var_16C], eax
0x10070e3ea  jmp     loc_10070E35E
0x10070e3f0  xor     edx, edx; Val
0x10070e3f2  mov     r8d, 0C8h; Size
0x10070e3f8  lea     rcx, [rbp+0D0h+var_110]; void *
0x10070e3fc  call    memset_0
0x10070e401  test    rsi, rsi
0x10070e404  jnz     short loc_10070E422
0x10070e406  call    cs:__imp__errno
0x10070e40c  mov     dword ptr [rax], 16h
0x10070e412  jmp     short loc_10070E415
0x10070e415  call    cs:__imp__invalid_parameter_noinfo
0x10070e41b  nop
0x10070e41c  jmp     loc_10070E389
0x10070e422  cmp     rdi, 0C8h
0x10070e429  jbe     loc_10070E389
0x10070e42f  call    cs:__imp__errno
0x10070e435  mov     dword ptr [rax], 22h ; '"'
0x10070e43b  jmp     short loc_10070E415
```
