# CCmPrimitives::CalculateSha_internal(CSbSafeBuffer const *,CSbSafeBuffer const *,CSbSafeBuffer *,CCmPrimitives::tagCmPrimitvesShaRunMode)

- ea: `0x180009694`
- end: `0x180009bd8`
- name: `?CalculateSha_internal@CCmPrimitives@@AEAAJPEBVCSbSafeBuffer@@0PEAV2@W4tagCmPrimitvesShaRunMode@1@@Z`
- size: `1348`
- prototype: `__int64 __fastcall(__int64, CSbSafeBuffer *, CSbSafeBuffer *, CSbSafeBuffer *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180005b0c`
- `0x180009538`

## callees

- `0x18000265c`
- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180009694`
- `0x18000a350`
- `0x18000a6d4`
- `0x18000a808`
- `0x180053004`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009bb0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009bbe`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009bb0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009bbe`
- `bcrypt!BCryptDestroyHash` at `0x180009b6b`
- `bcrypt!BCryptDestroyHash` at `0x180009b6b`
- `bcrypt!BCryptGetProperty` at `0x18000981a`
- `bcrypt!BCryptGetProperty` at `0x18000981a`
- `bcrypt!BCryptCreateHash` at `0x180009984`
- `bcrypt!BCryptCreateHash` at `0x1800099ef`
- `bcrypt!BCryptCreateHash` at `0x180009984`
- `bcrypt!BCryptCreateHash` at `0x1800099ef`
- `bcrypt!BCryptFinishHash` at `0x180009ad8`
- `bcrypt!BCryptFinishHash` at `0x180009ad8`
- `bcrypt!BCryptHashData` at `0x180009a92`
- `bcrypt!BCryptHashData` at `0x180009a92`

## pseudocode

```c
__int64 __fastcall CCmPrimitives::CalculateSha_internal(
        __int64 a1,
        CSbSafeBuffer *a2,
        CSbSafeBuffer *a3,
        CSbSafeBuffer *a4,
        int a5)
{
  BCRYPT_HANDLE v6; // rax
  int v7; // edi
  _BYTE *v8; // r10
  const char *Indent; // rax
  __int64 v10; // r10
  __int64 v11; // rdx
  const char *v12; // r9
  PUCHAR v14; // r15
  unsigned __int8 *v15; // r14
  NTSTATUS Property; // eax
  unsigned int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  unsigned __int64 v23; // rcx
  PUCHAR v24; // rcx
  size_t v25; // r13
  unsigned __int64 v26; // rcx
  int v27; // eax
  unsigned __int64 v28; // r8
  CSbSafeBuffer *v29; // r13
  int v30; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // r8
  NTSTATUS v35; // eax
  __int64 v36; // r8
  __int64 v37; // rax
  ULONG dwFlags; // [rsp+28h] [rbp-90h]
  ULONG pcbResult; // [rsp+40h] [rbp-78h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-70h] BYREF
  PUCHAR pbHashObject; // [rsp+50h] [rbp-68h]
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-60h]
  PUCHAR v43; // [rsp+60h] [rbp-58h]
  unsigned __int8 *v44; // [rsp+68h] [rbp-50h]
  std::bad_alloc *v45; // [rsp+70h] [rbp-48h] BYREF
  ULONG pbOutput; // [rsp+C0h] [rbp+8h] BYREF
  int v47; // [rsp+C4h] [rbp+Ch]
  CSbSafeBuffer *v48; // [rsp+C8h] [rbp+10h]
  CSbSafeBuffer *v49; // [rsp+D0h] [rbp+18h]
  CSbSafeBuffer *v50; // [rsp+D8h] [rbp+20h]

  v50 = a4;
  v49 = a3;
  v48 = a2;
  v47 = HIDWORD(a1);
  phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  v6 = ::hObject;
  v7 = a5;
  if ( !a5 )
    v6 = phAlgorithm;
  hObject = v6;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v10 + 16), 44, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, Indent);
    v8 = WPP_GLOBAL_Control;
    v6 = hObject;
    a3 = v49;
    a4 = v50;
  }
  if ( !a2 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 45;
    v12 = "pInput";
LABEL_23:
    WPP_SF_s(*((_QWORD *)v8 + 2), v11, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, v12);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 46;
    v12 = "pDigest";
    goto LABEL_23;
  }
  if ( !v6 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 47;
    v12 = "hAlg";
    goto LABEL_23;
  }
  if ( !v7 && !a3 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 2u )
      return 2147500035LL;
    v11 = 48;
    v12 = "pKey";
    goto LABEL_23;
  }
  v14 = 0;
  v43 = 0;
  v15 = 0;
  v44 = 0;
  pcbResult = 4;
  Property = BCryptGetProperty(v6, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v17 = Property | 0x10000000;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_85;
    v19 = 49;
    goto LABEL_29;
  }
  if ( !v7 )
  {
    v20 = (_QWORD *)*((_QWORD *)v49 + 3);
    if ( v20 )
      v14 = (PUCHAR)(v20[1] - *v20);
  }
  v21 = (_QWORD *)*((_QWORD *)a2 + 3);
  v22 = v21 + 1;
  if ( v21 )
    v23 = *v22 - *v21;
  else
    v23 = 0;
  if ( v23 <= (unsigned __int64)v14 )
  {
    v24 = v14;
  }
  else if ( v21 )
  {
    v24 = (PUCHAR)(*v22 - *v21);
  }
  else
  {
    v24 = 0;
  }
  v25 = *(_QWORD *)&::pbOutput;
  if ( (unsigned __int64)v24 > *(_QWORD *)&::pbOutput )
  {
    if ( v21 )
      v26 = *v22 - *v21;
    else
      v26 = 0;
    if ( v26 <= (unsigned __int64)v14 )
    {
      v25 = (size_t)v14;
    }
    else if ( v21 )
    {
      v25 = *v22 - *v21;
    }
    else
    {
      v25 = 0;
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v15 = (unsigned __int8 *)operator new[](v25);
    v44 = v15;
    pbHashObject = (PUCHAR)operator new[](pbOutput);
    v43 = pbHashObject;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v45) )
    {
      a5 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v37 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v45 + 8LL))(v45);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, v37);
      }
      v17 = a5;
      v14 = v43;
      v15 = v44;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180009B49);
      goto LABEL_85;
    }
  }
  if ( v7 )
  {
    v14 = pbHashObject;
    Property = BCryptCreateHash(hObject, &phHash, pbHashObject, pbOutput, 0, 0, 0);
    if ( Property < 0 )
    {
      v17 = Property | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_85;
      v19 = 53;
      goto LABEL_29;
    }
  }
  else
  {
    v27 = ((int (__stdcall *)(CSbSafeBuffer *, unsigned __int8 *, unsigned __int64))CSbSafeBuffer::CopyToBuffer)(
            v49,
            v15,
            (unsigned __int64)v14);
    v17 = v27;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids,
          (unsigned int)v27);
      goto LABEL_56;
    }
    dwFlags = (unsigned int)v14;
    v14 = pbHashObject;
    Property = BCryptCreateHash(hObject, &phHash, pbHashObject, pbOutput, v15, dwFlags, 0);
    if ( Property < 0 )
    {
      v17 = Property | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_85;
      v19 = 52;
      goto LABEL_29;
    }
  }
  v28 = v25;
  v29 = v48;
  v30 = ((int (__stdcall *)(CSbSafeBuffer *, unsigned __int8 *, unsigned __int64))CSbSafeBuffer::CopyToBuffer)(
          v48,
          v15,
          v28);
  v17 = v30;
  if ( v30 >= 0 )
  {
    v33 = (_QWORD *)*((_QWORD *)v29 + 3);
    if ( v33 )
      v34 = v33[1] - *v33;
    else
      LODWORD(v34) = 0;
    Property = BCryptHashData(phHash, v15, v34, 0);
    if ( Property >= 0 )
    {
      Property = BCryptFinishHash(phHash, v15, ::pbOutput, 0);
      if ( Property >= 0 )
      {
        v30 = CSbSafeBuffer::CopyFromBuffer(v50, v15, *(unsigned __int64 *)&::pbOutput);
        v17 = v30;
        if ( v30 < 0 )
        {
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v32 = 57;
            goto LABEL_69;
          }
        }
LABEL_56:
        v14 = pbHashObject;
        goto LABEL_85;
      }
      v17 = Property | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_85;
      v19 = 56;
    }
    else
    {
      v17 = Property | 0x10000000;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_85;
      v19 = 55;
    }
LABEL_29:
    WPP_SF_Dd(v18[2], v19, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, (unsigned int)Property, v17);
    goto LABEL_85;
  }
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_56;
  v32 = 54;
LABEL_69:
  WPP_SF_d(v31[2], v32, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, (unsigned int)v30);
LABEL_85:
  if ( phHash )
  {
    v35 = BCryptDestroyHash(phHash);
    if ( v35 < 0 )
    {
      v17 = v35 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v36, phHash, v35, v35 | 0x10000000);
    }
  }
  if ( v14 )
    operator delete[](v14);
  if ( v15 )
    operator delete[](v15);
  return v17;
}

```

## disassembly

```asm
0x180009694  mov     rax, rsp
0x180009697  mov     [rax+20h], r9
0x18000969b  mov     [rax+18h], r8
0x18000969f  mov     [rax+10h], rdx
0x1800096a3  mov     [rax+8], rcx
0x1800096a7  push    rsi
0x1800096a8  push    rdi
0x1800096a9  push    r12
0x1800096ab  push    r13
0x1800096ad  push    r14
0x1800096af  push    r15
0x1800096b1  sub     rsp, 88h
0x1800096b8  mov     r13, rdx
0x1800096bb  mov     qword ptr [rax-70h], 0
0x1800096c3  mov     dword ptr [rax+8], 0
0x1800096ca  mov     dword ptr [rax-78h], 0
0x1800096d1  mov     rax, cs:hObject
0x1800096d8  mov     edi, [rsp+0B8h+arg_20]
0x1800096df  test    edi, edi
0x1800096e1  cmovz   rax, cs:phAlgorithm
0x1800096e9  mov     [rsp+0B8h+hObject], rax
0x1800096ee  lea     rsi, WPP_GLOBAL_Control
0x1800096f5  mov     r10, cs:WPP_GLOBAL_Control
0x1800096fc  cmp     r10, rsi
0x1800096ff  jz      short loc_18000974B
0x180009701  cmp     byte ptr [r10+19h], 6
0x180009706  jb      short loc_18000974B
0x180009708  mov     ecx, 1; int
0x18000970d  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180009712  mov     edx, 2Ch ; ','
0x180009717  mov     r9, rax
0x18000971a  lea     r12, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids
0x180009721  mov     r8, r12
0x180009724  mov     rcx, [r10+10h]
0x180009728  call    WPP_SF_s
0x18000972d  mov     r10, cs:WPP_GLOBAL_Control
0x180009734  mov     rax, [rsp+0B8h+hObject]
0x180009739  mov     r8, [rsp+0B8h+arg_10]
0x180009741  mov     r9, [rsp+0B8h+arg_18]
0x180009749  jmp     short loc_180009752
0x18000974b  lea     r12, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids
0x180009752  test    r13, r13
0x180009755  jnz     short loc_180009770
0x180009757  cmp     r10, rsi
0x18000975a  jz      short loc_1800097D6
0x18000975c  cmp     byte ptr [r10+19h], 2
0x180009761  jb      short loc_1800097D6
0x180009763  lea     edx, [r13+2Dh]
0x180009767  lea     r9, aPinput; "pInput"
0x18000976e  jmp     short loc_1800097CA
0x180009770  test    r9, r9
0x180009773  jnz     short loc_18000978E
0x180009775  cmp     r10, rsi
0x180009778  jz      short loc_1800097D6
0x18000977a  cmp     byte ptr [r10+19h], 2
0x18000977f  jb      short loc_1800097D6
0x180009781  lea     edx, [r9+2Eh]
0x180009785  lea     r9, aPdigest; "pDigest"
0x18000978c  jmp     short loc_1800097CA
0x18000978e  test    rax, rax
0x180009791  jnz     short loc_1800097AB
0x180009793  cmp     r10, rsi
0x180009796  jz      short loc_1800097D6
0x180009798  cmp     byte ptr [r10+19h], 2
0x18000979d  jb      short loc_1800097D6
0x18000979f  lea     edx, [rax+2Fh]
0x1800097a2  lea     r9, aHalg; "hAlg"
0x1800097a9  jmp     short loc_1800097CA
0x1800097ab  test    edi, edi
0x1800097ad  jnz     short loc_1800097E0
0x1800097af  test    r8, r8
0x1800097b2  jnz     short loc_1800097E0
0x1800097b4  cmp     r10, rsi
0x1800097b7  jz      short loc_1800097D6
0x1800097b9  cmp     byte ptr [r10+19h], 2
0x1800097be  jb      short loc_1800097D6
0x1800097c0  lea     edx, [rdi+30h]
0x1800097c3  lea     r9, aPkey; "pKey"
0x1800097ca  mov     r8, r12
0x1800097cd  mov     rcx, [r10+10h]
0x1800097d1  call    WPP_SF_s
0x1800097d6  mov     eax, 80004003h
0x1800097db  jmp     loc_180009BC6
0x1800097e0  xor     r15d, r15d
0x1800097e3  mov     [rsp+0B8h+var_58], r15
0x1800097e8  xor     r14d, r14d
0x1800097eb  mov     [rsp+0B8h+var_50], r14
0x1800097f0  lea     r9d, [r15+4]; cbOutput
0x1800097f4  mov     [rsp+0B8h+var_78], r9d
0x1800097f9  mov     [rsp+0B8h+dwFlags], r14d; dwFlags
0x1800097fe  lea     rcx, [rsp+0B8h+var_78]
0x180009803  mov     [rsp+0B8h+pcbResult], rcx; pcbResult
0x180009808  lea     r8, [rsp+0B8h+pbOutput]; pbOutput
0x180009810  lea     rdx, aObjectlength; "ObjectLength"
0x180009817  mov     rcx, rax; hObject
0x18000981a  call    cs:__imp_BCryptGetProperty
0x180009820  test    eax, eax
0x180009822  jns     short loc_180009860
0x180009824  mov     edi, eax
0x180009826  bts     edi, 1Ch
0x18000982a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009831  cmp     rcx, rsi
0x180009834  jz      loc_180009B61
0x18000983a  cmp     byte ptr [rcx+19h], 2
0x18000983e  jb      loc_180009B61
0x180009844  lea     edx, [r15+31h]
0x180009848  mov     dword ptr [rsp+0B8h+pcbResult], edi
0x18000984c  mov     r9d, eax
0x18000984f  mov     r8, r12
0x180009852  mov     rcx, [rcx+10h]
0x180009856  call    WPP_SF_Dd
0x18000985b  jmp     loc_180009B61
0x180009860  test    edi, edi
0x180009862  jnz     short loc_18000987C
0x180009864  mov     rax, [rsp+0B8h+arg_10]
0x18000986c  mov     rax, [rax+18h]
0x180009870  test    rax, rax
0x180009873  jz      short loc_18000987C
0x180009875  mov     r15, [rax+8]
0x180009879  sub     r15, [rax]
0x18000987c  mov     rax, [r13+18h]
0x180009880  lea     rdx, [rax+8]
0x180009884  test    rax, rax
0x180009887  jz      short loc_180009891
0x180009889  mov     rcx, [rdx]
0x18000988c  sub     rcx, [rax]
0x18000988f  jmp     short loc_180009893
0x180009891  xor     ecx, ecx
0x180009893  cmp     rcx, r15
0x180009896  jbe     short loc_1800098A9
0x180009898  test    rax, rax
0x18000989b  jz      short loc_1800098A5
0x18000989d  mov     rcx, [rdx]
0x1800098a0  sub     rcx, [rax]
0x1800098a3  jmp     short loc_1800098AC
0x1800098a5  xor     ecx, ecx
0x1800098a7  jmp     short loc_1800098AC
0x1800098a9  mov     rcx, r15
0x1800098ac  mov     r13, cs:pbOutput
0x1800098b3  cmp     rcx, r13
0x1800098b6  jbe     short loc_1800098E1
0x1800098b8  test    rax, rax
0x1800098bb  jz      short loc_1800098C5
0x1800098bd  mov     rcx, [rdx]
0x1800098c0  sub     rcx, [rax]
0x1800098c3  jmp     short loc_1800098C7
0x1800098c5  xor     ecx, ecx
0x1800098c7  cmp     rcx, r15
0x1800098ca  jbe     short loc_1800098DE
0x1800098cc  test    rax, rax
0x1800098cf  jz      short loc_1800098D9
0x1800098d1  mov     r13, [rdx]
0x1800098d4  sub     r13, [rax]
0x1800098d7  jmp     short loc_1800098E1
0x1800098d9  xor     r13d, r13d
0x1800098dc  jmp     short loc_1800098E1
0x1800098de  mov     r13, r15
0x1800098e1  mov     rcx, r13; unsigned __int64
0x1800098e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800098e9  mov     r14, rax
0x1800098ec  mov     [rsp+0B8h+var_50], rax
0x1800098f1  mov     ecx, [rsp+0B8h+pbOutput]; unsigned __int64
0x1800098f8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800098fd  mov     [rsp+0B8h+pbHashObject], rax
0x180009902  mov     [rsp+0B8h+var_58], rax
0x180009907  test    edi, edi
0x180009909  jnz     loc_1800099BC
0x18000990f  mov     r8, r15; unsigned __int64
0x180009912  mov     rdx, r14; unsigned __int8 *
0x180009915  mov     rcx, [rsp+0B8h+arg_10]; this
0x18000991d  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x180009922  mov     edi, eax
0x180009924  test    eax, eax
0x180009926  jns     short loc_180009958
0x180009928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000992f  cmp     rcx, rsi
0x180009932  jz      short loc_18000994E
0x180009934  cmp     byte ptr [rcx+19h], 2
0x180009938  jb      short loc_18000994E
0x18000993a  mov     edx, 33h ; '3'
0x18000993f  mov     r9d, eax
0x180009942  mov     r8, r12
0x180009945  mov     rcx, [rcx+10h]
0x180009949  call    WPP_SF_d
0x18000994e  mov     r15, [rsp+0B8h+pbHashObject]
0x180009953  jmp     loc_180009B61
0x180009958  mov     [rsp+0B8h+var_88], 0; dwFlags
0x180009960  mov     [rsp+0B8h+dwFlags], r15d; cbSecret
0x180009965  mov     [rsp+0B8h+pcbResult], r14; pbSecret
0x18000996a  mov     r9d, [rsp+0B8h+pbOutput]; cbHashObject
0x180009972  mov     r15, [rsp+0B8h+pbHashObject]
0x180009977  mov     r8, r15; pbHashObject
0x18000997a  lea     rdx, [rsp+0B8h+phHash]; phHash
0x18000997f  mov     rcx, [rsp+0B8h+hObject]; hAlgorithm
0x180009984  call    cs:__imp_BCryptCreateHash
0x18000998a  test    eax, eax
0x18000998c  jns     loc_180009A23
0x180009992  mov     edi, eax
0x180009994  bts     edi, 1Ch
0x180009998  mov     rcx, cs:WPP_GLOBAL_Control
0x18000999f  cmp     rcx, rsi
0x1800099a2  jz      loc_180009B61
0x1800099a8  cmp     byte ptr [rcx+19h], 2
0x1800099ac  jb      loc_180009B61
0x1800099b2  mov     edx, 34h ; '4'
0x1800099b7  jmp     loc_180009848
0x1800099bc  mov     [rsp+0B8h+var_88], 0; dwFlags
0x1800099c4  mov     [rsp+0B8h+dwFlags], 0; cbSecret
0x1800099cc  mov     [rsp+0B8h+pcbResult], 0; pbSecret
0x1800099d5  mov     r9d, [rsp+0B8h+pbOutput]; cbHashObject
0x1800099dd  mov     r15, [rsp+0B8h+pbHashObject]
0x1800099e2  mov     r8, r15; pbHashObject
0x1800099e5  lea     rdx, [rsp+0B8h+phHash]; phHash
0x1800099ea  mov     rcx, [rsp+0B8h+hObject]; hAlgorithm
0x1800099ef  call    cs:__imp_BCryptCreateHash
0x1800099f5  test    eax, eax
0x1800099f7  jns     short loc_180009A23
0x1800099f9  mov     edi, eax
0x1800099fb  bts     edi, 1Ch
0x1800099ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a06  cmp     rcx, rsi
0x180009a09  jz      loc_180009B61
0x180009a0f  cmp     byte ptr [rcx+19h], 2
0x180009a13  jb      loc_180009B61
0x180009a19  mov     edx, 35h ; '5'
0x180009a1e  jmp     loc_180009848
0x180009a23  mov     r8, r13; unsigned __int64
0x180009a26  mov     rdx, r14; unsigned __int8 *
0x180009a29  mov     r13, [rsp+0B8h+arg_8]
0x180009a31  mov     rcx, r13; this
0x180009a34  call    ?CopyToBuffer@CSbSafeBuffer@@QEBAJPEAE_K@Z; CSbSafeBuffer::CopyToBuffer(uchar *,unsigned __int64)
0x180009a39  mov     edi, eax
0x180009a3b  test    eax, eax
0x180009a3d  jns     short loc_180009A72
0x180009a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a46  cmp     rcx, rsi
0x180009a49  jz      loc_18000994E
0x180009a4f  cmp     byte ptr [rcx+19h], 2
0x180009a53  jb      loc_18000994E
0x180009a59  mov     edx, 36h ; '6'
0x180009a5e  mov     r9d, eax
0x180009a61  mov     r8, r12
0x180009a64  mov     rcx, [rcx+10h]
0x180009a68  call    WPP_SF_d
0x180009a6d  jmp     loc_180009B61
0x180009a72  mov     rax, [r13+18h]
0x180009a76  test    rax, rax
0x180009a79  jz      short loc_180009A84
0x180009a7b  mov     r8, [rax+8]
0x180009a7f  sub     r8, [rax]
0x180009a82  jmp     short loc_180009A87
0x180009a84  xor     r8d, r8d; cbInput
0x180009a87  xor     r9d, r9d; dwFlags
0x180009a8a  mov     rdx, r14; pbInput
0x180009a8d  mov     rcx, [rsp+0B8h+phHash]; hHash
0x180009a92  call    cs:__imp_BCryptHashData
0x180009a98  test    eax, eax
0x180009a9a  jns     short loc_180009AC6
0x180009a9c  mov     edi, eax
0x180009a9e  bts     edi, 1Ch
0x180009aa2  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aa9  cmp     rcx, rsi
0x180009aac  jz      loc_180009B61
0x180009ab2  cmp     byte ptr [rcx+19h], 2
0x180009ab6  jb      loc_180009B61
0x180009abc  mov     edx, 37h ; '7'
0x180009ac1  jmp     loc_180009848
0x180009ac6  xor     r9d, r9d; dwFlags
0x180009ac9  mov     r8d, dword ptr cs:pbOutput; cbOutput
0x180009ad0  mov     rdx, r14; pbOutput
0x180009ad3  mov     rcx, [rsp+0B8h+phHash]; hHash
0x180009ad8  call    cs:__imp_BCryptFinishHash
0x180009ade  test    eax, eax
0x180009ae0  jns     short loc_180009B04
0x180009ae2  mov     edi, eax
0x180009ae4  bts     edi, 1Ch
0x180009ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aef  cmp     rcx, rsi
0x180009af2  jz      short loc_180009B61
0x180009af4  cmp     byte ptr [rcx+19h], 2
0x180009af8  jb      short loc_180009B61
0x180009afa  mov     edx, 38h ; '8'
0x180009aff  jmp     loc_180009848
0x180009b04  mov     r8, cs:pbOutput; unsigned __int64
0x180009b0b  mov     rdx, r14; unsigned __int8 *
0x180009b0e  mov     rcx, [rsp+0B8h+arg_18]; this
0x180009b16  call    ?CopyFromBuffer@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::CopyFromBuffer(uchar const *,unsigned __int64)
0x180009b1b  mov     edi, eax
0x180009b1d  test    eax, eax
0x180009b1f  jns     loc_18000994E
0x180009b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b2c  cmp     rcx, rsi
0x180009b2f  jz      loc_18000994E
0x180009b35  cmp     byte ptr [rcx+19h], 2
0x180009b39  jb      loc_18000994E
0x180009b3f  mov     edx, 39h ; '9'
0x180009b44  jmp     loc_180009A5E
0x180009b49  lea     rsi, WPP_GLOBAL_Control
0x180009b50  mov     edi, [rsp+0B8h+arg_20]
0x180009b57  mov     r15, [rsp+0B8h+var_58]
  ... truncated ...
```
