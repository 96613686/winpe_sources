# GetNodeValue

- ea: `0x180038658`
- end: `0x180038cfa`
- name: `GetNodeValue`
- size: `1698`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038d00`
- `0x180039704`

## callees

- `0x18000a684`
- `0x18000a9b4`
- `0x18000f6d0`
- `0x18001e424`
- `0x180031d8c`
- `0x1800383f0`
- `0x180038578`
- `0x180038658`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038b50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038b50`
- `RPCRT4!UuidFromStringW` at `0x180038a4c`
- `RPCRT4!UuidFromStringW` at `0x180038a4c`
- `OLEAUT32!__imp_SysStringLen` at `0x180038a06`
- `OLEAUT32!__imp_SysStringLen` at `0x180038b3e`
- `OLEAUT32!__imp_SysStringLen` at `0x180038c36`
- `OLEAUT32!__imp_SysStringLen` at `0x180038a06`
- `OLEAUT32!__imp_SysStringLen` at `0x180038b3e`
- `OLEAUT32!__imp_SysStringLen` at `0x180038c36`
- `OLEAUT32!__imp_VariantInit` at `0x1800386b1`
- `OLEAUT32!__imp_VariantInit` at `0x1800386b1`
- `OLEAUT32!__imp_VariantClear` at `0x180038cb7`
- `OLEAUT32!__imp_VariantClear` at `0x180038cb7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180038837`
- `OLEAUT32!__imp_VariantChangeType` at `0x180038837`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180038bed`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180038bed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetNodeValue(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  unsigned int v9; // eax
  UUID *v10; // rsi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v12; // ebx
  int v13; // r8d
  VARTYPE v14; // r9
  OLECHAR *bstrVal; // rdi
  HRESULT v16; // eax
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  size_t v34; // r14
  unsigned int v35; // r15d
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  bool v43; // zf
  size_t v44; // r14
  const WCHAR *v45; // r15
  unsigned int i; // edi
  UINT v47; // eax
  LONG lVal; // eax
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // ecx
  OLECHAR *v57; // r15
  SIZE_T v58; // r14
  OLECHAR *v59; // rax
  UINT v60; // r15d
  int v61; // ecx
  unsigned __int8 *v62; // r15
  UINT v63; // eax
  int v64; // r13d
  OLECHAR *v65; // r8
  OLECHAR *v66; // r9
  __int64 v67; // r10
  unsigned __int8 *v68; // rax
  BSTR pbstr; // [rsp+30h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-28h] BYREF
  __int64 v72; // [rsp+50h] [rbp-10h] BYREF

  v9 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( !*(_BYTE *)(a2 + 33) )
    v9 = *(_DWORD *)(a2 + 28);
  v10 = (UUID *)(a3 + v9);
  v72 = 0;
  VariantInit(&pvarg);
  v11 = **a1;
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  v12 = v11(a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60, &v72);
  if ( v12 < 0 )
    goto LABEL_136;
  if ( *(int *)(a2 + 24) <= 4 )
  {
LABEL_7:
    v12 = 0;
    goto LABEL_136;
  }
  if ( *(int *)(a2 + 24) >= 20 )
  {
    if ( *(_DWORD *)(a2 + 24) == 24 )
    {
      pbstr = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v72 + 272LL))(v72, &pbstr);
      if ( v12 >= 0 )
      {
LABEL_11:
        pvarg.vt = 8;
        bstrVal = pbstr;
        pvarg.llVal = (LONGLONG)pbstr;
        goto LABEL_17;
      }
    }
  }
  else
  {
    if ( a4 )
    {
      pbstr = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v72 + 208LL))(v72, &pbstr);
      if ( v12 < 0 )
        goto LABEL_136;
      goto LABEL_11;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v72 + 64LL))(v72, &pvarg);
    if ( v12 < 0 )
      goto LABEL_136;
  }
  bstrVal = pvarg.bstrVal;
LABEL_17:
  if ( v12 == 1 )
  {
    if ( *(_BYTE *)(a2 + 32) )
    {
      v12 = -2145124339;
      goto LABEL_136;
    }
    if ( !*(_BYTE *)(a2 + 34) )
      goto LABEL_7;
    v16 = SetNodeDefaultValue(a2, a3);
    goto LABEL_118;
  }
  v17 = *(_DWORD *)(a2 + 24);
  if ( v17 > 14 )
  {
    v36 = v17 - 15;
    if ( !v36 )
      goto LABEL_32;
    v37 = v36 - 1;
    if ( !v37 )
      goto LABEL_32;
    v38 = v37 - 1;
    if ( !v38 )
      goto LABEL_32;
    v39 = v38 - 1;
    if ( !v39 )
      goto LABEL_32;
    v40 = v39 - 1;
    if ( v40 )
    {
      v41 = v40 - 2;
      if ( !v41 )
        goto LABEL_36;
      v42 = v41 - 1;
      if ( !v42 || (unsigned int)(v42 - 1) < 2 )
        goto LABEL_36;
      goto LABEL_63;
    }
  }
  else
  {
    if ( v17 == 14 )
      goto LABEL_32;
    v18 = v17 - 5;
    if ( !v18 )
    {
      v14 = 3;
      goto LABEL_33;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v14 = 19;
      goto LABEL_33;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v14 = 21;
      goto LABEL_33;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
LABEL_32:
      v14 = 8;
      goto LABEL_33;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_32;
      v24 = v23 - 1;
      if ( !v24 || (unsigned int)(v24 - 1) <= 1 )
        goto LABEL_32;
LABEL_63:
      v12 = -2147024809;
      goto LABEL_136;
    }
  }
  v14 = 11;
LABEL_33:
  if ( pvarg.vt != v14 )
  {
    v12 = VariantChangeType(&pvarg, &pvarg, 0, v14);
    if ( v12 < 0 )
      goto LABEL_136;
    bstrVal = pvarg.bstrVal;
  }
LABEL_36:
  v25 = *(_DWORD *)(a2 + 24);
  if ( v25 > 14 )
  {
    v49 = v25 - 15;
    if ( !v49 )
      goto LABEL_110;
    v50 = v49 - 1;
    if ( !v50 )
    {
      v61 = 0;
      v62 = 0;
      if ( bstrVal )
      {
        v63 = SysStringLen(bstrVal);
        v64 = v63;
        v65 = bstrVal;
        v66 = bstrVal;
        v67 = v63 + 1;
        do
        {
          *(_BYTE *)v66 = *(_BYTE *)v65++;
          v66 = (OLECHAR *)((char *)v66 + 1);
          --v67;
        }
        while ( v67 );
        LODWORD(pbstr) = 3 * ((v63 >> 2) + 1);
        v68 = (unsigned __int8 *)SafeSusComAlloc((int)pbstr, 1);
        v62 = v68;
        if ( !v68 )
          goto LABEL_135;
        if ( !(unsigned int)ATL::Base64Decode((const char *)bstrVal, v64, v68, (int *)&pbstr) )
        {
          CoTaskMemFree(v62);
          goto LABEL_88;
        }
        v61 = (int)pbstr;
      }
      *(_DWORD *)(a3 + *(_QWORD *)a2) = v61;
      *(_QWORD *)&v10->Data1 = v62;
      goto LABEL_136;
    }
    v51 = v50 - 1;
    if ( !v51 )
    {
      v60 = SysStringByteLen(bstrVal) + 2;
      memset(v10, 0, *(_QWORD *)a2);
      if ( !bstrVal )
        goto LABEL_78;
      if ( (unsigned __int64)v60 > *(_QWORD *)a2 )
        goto LABEL_88;
      memmove(v10, bstrVal, v60);
      goto LABEL_136;
    }
    v52 = v51 - 1;
    if ( !v52 )
    {
      if ( !bstrVal )
        goto LABEL_78;
      v12 = ConvertStringVerToFileVerW(bstrVal, (unsigned __int64 *)&v10->Data1, v13, v14);
      if ( v12 < 0 )
        goto LABEL_88;
      goto LABEL_136;
    }
    v53 = v52 - 1;
    if ( !v53 )
    {
      if ( pvarg.iVal )
        v10->Data1 |= *(_DWORD *)a2;
      goto LABEL_136;
    }
    v54 = v53 - 2;
    if ( v54 )
    {
      v55 = v54 - 1;
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( v56 )
        {
          if ( v56 != 1 )
            goto LABEL_136;
LABEL_110:
          v57 = (OLECHAR *)&dword_180068CEC;
          if ( bstrVal )
            v57 = bstrVal;
          v58 = 2 * SysStringLen(v57) + 2;
          v59 = (OLECHAR *)CoTaskMemAlloc(v58);
          bstrVal = v59;
          if ( v59 )
          {
            memmove(v59, v57, (unsigned int)v58);
            goto LABEL_114;
          }
LABEL_135:
          v12 = -2147024882;
          goto LABEL_136;
        }
        v16 = DspParseSpecialData(v72, (_DWORD)v10, (int)a3 + *(_DWORD *)a2, a5, 0);
      }
      else
      {
        v16 = DspParseSpecialData(v72, (int)v10 + 8, (_DWORD)v10, a5, 1);
      }
    }
    else
    {
      v16 = DspParseSpecialData(v72, (_DWORD)v10, (int)a3 + *(_DWORD *)a2, a5, 1);
    }
LABEL_118:
    v12 = v16;
    goto LABEL_136;
  }
  if ( v25 == 14 )
  {
    v34 = *(_QWORD *)a2;
    if ( bstrVal )
    {
      v35 = 0;
      if ( *(_DWORD *)(v34 + 8) )
      {
        while ( (unsigned int)AsciiStringCompareI(bstrVal, *(PCNZWCH *)(*(_QWORD *)v34 + 16LL * v35)) )
        {
          if ( ++v35 >= *(_DWORD *)(v34 + 8) )
            goto LABEL_67;
        }
        if ( *(_DWORD *)(*(_QWORD *)v34 + 16LL * v35 + 8) == 2 )
          v10->Data1 |= 0x1000u;
      }
      goto LABEL_67;
    }
LABEL_88:
    v12 = -2145124338;
    goto LABEL_136;
  }
  v26 = v25 - 5;
  if ( !v26 || (v27 = v26 - 1) == 0 )
  {
    lVal = pvarg.lVal;
    goto LABEL_93;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
LABEL_114:
    *(_QWORD *)&v10->Data1 = bstrVal;
    goto LABEL_136;
  }
  v29 = v28 - 1;
  if ( !v29 )
  {
    if ( bstrVal )
    {
      v12 = StringToFileTime(bstrVal, v10, 0);
      v43 = v12 == -2147024809;
LABEL_68:
      if ( !v43 )
        goto LABEL_136;
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  v30 = v29 - 1;
  if ( !v30 )
  {
    lVal = pvarg.iVal != 0;
LABEL_93:
    v10->Data1 = lVal;
    goto LABEL_136;
  }
  v31 = v30 - 1;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( !v33 )
      {
        v44 = *(_QWORD *)a2;
        v45 = (const WCHAR *)&dword_180068CEC;
        if ( bstrVal )
          v45 = bstrVal;
        for ( i = 0; i < *(_DWORD *)(v44 + 8); ++i )
        {
          if ( !(unsigned int)AsciiStringCompareI(v45, *(PCNZWCH *)(*(_QWORD *)v44 + 16LL * i)) )
            break;
        }
        if ( i != *(_DWORD *)(v44 + 8) )
        {
          v10->Data1 = *(_DWORD *)(*(_QWORD *)v44 + 16LL * i + 8);
          goto LABEL_136;
        }
        goto LABEL_88;
      }
      if ( v33 != 1 )
        goto LABEL_136;
      v34 = *(_QWORD *)a2;
      if ( bstrVal )
      {
        v35 = 0;
        if ( *(_DWORD *)(v34 + 8) )
        {
          while ( (unsigned int)AsciiStringCompareI(bstrVal, *(PCNZWCH *)(*(_QWORD *)v34 + 16LL * v35)) )
          {
            if ( ++v35 >= *(_DWORD *)(v34 + 8) )
              goto LABEL_67;
          }
          if ( *(_DWORD *)(*(_QWORD *)v34 + 16LL * v35 + 8) == 1 )
            v10->Data1 |= 0x800u;
        }
LABEL_67:
        v43 = v35 == *(_DWORD *)(v34 + 8);
        goto LABEL_68;
      }
      goto LABEL_88;
    }
  }
  if ( !bstrVal )
  {
LABEL_78:
    v12 = *(_BYTE *)(a2 + 32) != 0 ? 0x8024000D : 0;
    goto LABEL_136;
  }
  v47 = SysStringLen(bstrVal);
  if ( *(_DWORD *)(a2 + 24) == 11 )
  {
    if ( v47 == 38 && *bstrVal == 123 && bstrVal[37] == 125 )
    {
      bstrVal[37] = 0;
      ++bstrVal;
    }
    else
    {
      v12 = -2145124338;
    }
  }
  else if ( v47 != 36 )
  {
    goto LABEL_88;
  }
  if ( v12 >= 0 && UuidFromStringW(bstrVal, v10) )
    goto LABEL_88;
LABEL_136:
  VariantClear(&pvarg);
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180038658  mov     [rsp-38h+arg_18], rbx
0x18003865d  push    rbp
0x18003865e  push    rsi
0x18003865f  push    rdi
0x180038660  push    r12
0x180038662  push    r13
0x180038664  push    r14
0x180038666  push    r15
0x180038668  mov     rbp, rsp
0x18003866b  sub     rsp, 60h
0x18003866f  mov     rax, cs:__security_cookie
0x180038676  xor     rax, rsp
0x180038679  mov     [rbp+var_8], rax
0x18003867d  mov     r15d, r9d
0x180038680  mov     r12, r8
0x180038683  mov     r14, rdx
0x180038686  mov     rbx, rcx
0x180038689  mov     r13, [rbp+arg_20]
0x18003868d  xorps   xmm0, xmm0
0x180038690  xor     eax, eax
0x180038692  movups  xmmword ptr [rbp+pvarg], xmm0
0x180038696  mov     qword ptr [rbp+pvarg+10h], rax
0x18003869a  xor     ecx, ecx
0x18003869c  cmp     [rdx+21h], cl
0x18003869f  jnz     short loc_1800386A4
0x1800386a1  mov     eax, [rdx+1Ch]
0x1800386a4  mov     esi, eax
0x1800386a6  add     rsi, r12
0x1800386a9  mov     [rbp+var_10], rcx
0x1800386ad  lea     rcx, [rbp+pvarg]; pvarg
0x1800386b1  call    cs:__imp_VariantInit
0x1800386b7  mov     rax, [rbx]
0x1800386ba  mov     rdi, [rax]
0x1800386bd  mov     rcx, [rbp+var_10]
0x1800386c1  test    rcx, rcx
0x1800386c4  jz      short loc_1800386D8
0x1800386c6  mov     rax, [rcx]
0x1800386c9  mov     rax, [rax+10h]
0x1800386cd  call    _guard_dispatch_icall
0x1800386d2  xor     eax, eax
0x1800386d4  mov     [rbp+var_10], rax
0x1800386d8  lea     r8, [rbp+var_10]
0x1800386dc  lea     rdx, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60
0x1800386e3  mov     rcx, rbx
0x1800386e6  mov     rax, rdi
0x1800386e9  call    _guard_dispatch_icall
0x1800386ee  mov     ebx, eax
0x1800386f0  xor     edx, edx
0x1800386f2  test    eax, eax
0x1800386f4  js      loc_180038CB3
0x1800386fa  cmp     dword ptr [r14+18h], 4
0x1800386ff  jg      short loc_180038708
0x180038701  mov     ebx, edx
0x180038703  jmp     loc_180038CB3
0x180038708  mov     edi, 8
0x18003870d  cmp     dword ptr [r14+18h], 14h
0x180038712  jge     short loc_18003876C
0x180038714  mov     rcx, [rbp+var_10]
0x180038718  test    r15d, r15d
0x18003871b  jz      short loc_18003874E
0x18003871d  mov     [rbp+pbstr], rdx
0x180038721  mov     rax, [rcx]
0x180038724  lea     rdx, [rbp+pbstr]
0x180038728  mov     rax, [rax+0D0h]
0x18003872f  call    _guard_dispatch_icall
0x180038734  mov     ebx, eax
0x180038736  xor     edx, edx
0x180038738  test    eax, eax
0x18003873a  js      loc_180038CB3
0x180038740  mov     word ptr [rbp+pvarg], di
0x180038744  mov     rdi, [rbp+pbstr]
0x180038748  mov     qword ptr [rbp+pvarg+8], rdi
0x18003874c  jmp     short loc_18003879A
0x18003874e  mov     rax, [rcx]
0x180038751  lea     rdx, [rbp+pvarg]
0x180038755  mov     rax, [rax+40h]
0x180038759  call    _guard_dispatch_icall
0x18003875e  mov     ebx, eax
0x180038760  xor     edx, edx
0x180038762  test    eax, eax
0x180038764  js      loc_180038CB3
0x18003876a  jmp     short loc_180038796
0x18003876c  cmp     dword ptr [r14+18h], 18h
0x180038771  jnz     short loc_180038796
0x180038773  mov     [rbp+pbstr], rdx
0x180038777  mov     rcx, [rbp+var_10]
0x18003877b  mov     rax, [rcx]
0x18003877e  lea     rdx, [rbp+pbstr]
0x180038782  mov     rax, [rax+110h]
0x180038789  call    _guard_dispatch_icall
0x18003878e  mov     ebx, eax
0x180038790  xor     edx, edx
0x180038792  test    eax, eax
0x180038794  jns     short loc_180038740
0x180038796  mov     rdi, qword ptr [rbp+pvarg+8]
0x18003879a  cmp     ebx, 1
0x18003879d  jnz     short loc_1800387C9
0x18003879f  cmp     [r14+20h], dl
0x1800387a3  jz      short loc_1800387AF
0x1800387a5  mov     ebx, 8024000Dh
0x1800387aa  jmp     loc_180038CB3
0x1800387af  cmp     [r14+22h], dl
0x1800387b3  jz      loc_180038701
0x1800387b9  mov     rdx, r12
0x1800387bc  mov     rcx, r14
0x1800387bf  call    SetNodeDefaultValue
0x1800387c4  jmp     loc_180038BAC
0x1800387c9  mov     ecx, [r14+18h]
0x1800387cd  mov     r15d, 0Bh
0x1800387d3  cmp     ecx, 0Eh
0x1800387d6  jg      loc_180038916
0x1800387dc  jz      short loc_18003881F
0x1800387de  sub     ecx, 5
0x1800387e1  jz      loc_18003890B
0x1800387e7  sub     ecx, 1
0x1800387ea  jz      loc_180038900
0x1800387f0  sub     ecx, 1
0x1800387f3  jz      loc_1800388F5
0x1800387f9  sub     ecx, 1
0x1800387fc  jz      short loc_18003881F
0x1800387fe  sub     ecx, 1
0x180038801  jz      loc_18003896D
0x180038807  sub     ecx, 1
0x18003880a  jz      short loc_18003881F
0x18003880c  sub     ecx, 1
0x18003880f  jz      short loc_18003881F
0x180038811  sub     ecx, 1
0x180038814  jz      short loc_18003881F
0x180038816  cmp     ecx, 1
0x180038819  jnz     loc_180038963
0x18003881f  mov     r9d, 8; vt
0x180038825  cmp     word ptr [rbp+pvarg], r9w
0x18003882a  jz      short loc_18003884D
0x18003882c  xor     r8d, r8d; wFlags
0x18003882f  lea     rdx, [rbp+pvarg]; pvarSrc
0x180038833  lea     rcx, [rbp+pvarg]; pvargDest
0x180038837  call    cs:__imp_VariantChangeType
0x18003883d  mov     ebx, eax
0x18003883f  xor     edx, edx
0x180038841  test    eax, eax
0x180038843  js      loc_180038CB3
0x180038849  mov     rdi, qword ptr [rbp+pvarg+8]
0x18003884d  mov     ecx, [r14+18h]
0x180038851  cmp     ecx, 0Eh
0x180038854  jg      loc_180038AEC
0x18003885a  jz      loc_180038A98
0x180038860  sub     ecx, 5
0x180038863  jz      loc_180038A8E
0x180038869  sub     ecx, 1
0x18003886c  jz      loc_180038A8E
0x180038872  sub     ecx, 1
0x180038875  jz      loc_180038B70
0x18003887b  sub     ecx, 1
0x18003887e  jz      loc_180038A6F
0x180038884  sub     ecx, 1
0x180038887  jz      loc_180038A64
0x18003888d  sub     ecx, 1
0x180038890  jz      loc_1800389EA
0x180038896  sub     ecx, 1
0x180038899  jz      loc_1800389EA
0x18003889f  sub     ecx, 1
0x1800388a2  jz      loc_180038994
0x1800388a8  cmp     ecx, 1
0x1800388ab  jnz     loc_180038CB3
0x1800388b1  mov     r14, [r14]
0x1800388b4  test    rdi, rdi
0x1800388b7  jz      loc_180038A5A
0x1800388bd  mov     r15d, edx
0x1800388c0  cmp     [r14+8], edx
0x1800388c4  jbe     loc_180038985
0x1800388ca  mov     r12d, r15d
0x1800388cd  add     r12, r12
0x1800388d0  mov     rdx, [r14]
0x1800388d3  mov     rdx, [rdx+r12*8]; lpString2
0x1800388d7  mov     rcx, rdi; lpString1
0x1800388da  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1800388df  test    eax, eax
0x1800388e1  jz      loc_180038976
0x1800388e7  inc     r15d
0x1800388ea  cmp     r15d, [r14+8]
0x1800388ee  jb      short loc_1800388CA
0x1800388f0  jmp     loc_180038985
0x1800388f5  mov     r9d, 15h
0x1800388fb  jmp     loc_180038825
0x180038900  mov     r9d, 13h
0x180038906  jmp     loc_180038825
0x18003890b  mov     r9d, 3
0x180038911  jmp     loc_180038825
0x180038916  sub     ecx, 0Fh
0x180038919  jz      loc_18003881F
0x18003891f  sub     ecx, 1
0x180038922  jz      loc_18003881F
0x180038928  sub     ecx, 1
0x18003892b  jz      loc_18003881F
0x180038931  sub     ecx, 1
0x180038934  jz      loc_18003881F
0x18003893a  sub     ecx, 1
0x18003893d  jz      short loc_18003896D
0x18003893f  sub     ecx, 2
0x180038942  jz      loc_18003884D
0x180038948  sub     ecx, 1
0x18003894b  jz      loc_18003884D
0x180038951  sub     ecx, 1
0x180038954  jz      loc_18003884D
0x18003895a  cmp     ecx, 1
0x18003895d  jz      loc_18003884D
0x180038963  mov     ebx, 80070057h
0x180038968  jmp     loc_180038CB3
0x18003896d  movzx   r9d, r15w
0x180038971  jmp     loc_180038825
0x180038976  mov     rax, [r14]
0x180038979  cmp     dword ptr [rax+r12*8+8], 1
0x18003897f  jnz     short loc_180038985
0x180038981  bts     dword ptr [rsi], 0Bh
0x180038985  cmp     r15d, [r14+8]
0x180038989  jnz     loc_180038CB3
0x18003898f  jmp     loc_180038A5A
0x180038994  mov     r14, [r14]
0x180038997  lea     r15, dword_180068CEC
0x18003899e  test    rdi, rdi
0x1800389a1  cmovnz  r15, rdi
0x1800389a5  mov     edi, edx
0x1800389a7  cmp     [r14+8], edx
0x1800389ab  jbe     short loc_1800389CD
0x1800389ad  mov     eax, edi
0x1800389af  add     rax, rax
0x1800389b2  mov     rdx, [r14]
0x1800389b5  mov     rdx, [rdx+rax*8]; lpString2
0x1800389b9  mov     rcx, r15; lpString1
0x1800389bc  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x1800389c1  test    eax, eax
0x1800389c3  jz      short loc_1800389CD
0x1800389c5  inc     edi
0x1800389c7  cmp     edi, [r14+8]
0x1800389cb  jb      short loc_1800389AD
0x1800389cd  cmp     edi, [r14+8]
0x1800389d1  jz      loc_180038A5A
0x1800389d7  mov     ecx, edi
0x1800389d9  add     rcx, rcx
0x1800389dc  mov     rax, [r14]
0x1800389df  mov     ecx, [rax+rcx*8+8]
0x1800389e3  mov     [rsi], ecx
0x1800389e5  jmp     loc_180038CB3
0x1800389ea  test    rdi, rdi
0x1800389ed  jnz     short loc_180038A03
0x1800389ef  mov     al, [r14+20h]
0x1800389f3  neg     al
0x1800389f5  sbb     ecx, ecx
0x1800389f7  mov     ebx, 8024000Dh
0x1800389fc  and     ebx, ecx
0x1800389fe  jmp     loc_180038CB3
0x180038a03  mov     rcx, rdi; pbstr
0x180038a06  call    cs:__imp_SysStringLen
0x180038a0c  cmp     [r14+18h], r15d
0x180038a10  jnz     short loc_180038A39
0x180038a12  cmp     eax, 26h ; '&'
0x180038a15  jnz     short loc_180038A32
0x180038a17  cmp     word ptr [rdi], 7Bh ; '{'
0x180038a1b  jnz     short loc_180038A32
0x180038a1d  cmp     word ptr [rdi+4Ah], 7Dh ; '}'
0x180038a22  jnz     short loc_180038A32
0x180038a24  xor     r13d, r13d
0x180038a27  mov     [rdi+4Ah], r13w
0x180038a2c  add     rdi, 2
0x180038a30  jmp     short loc_180038A3E
0x180038a32  mov     ebx, 8024000Eh
0x180038a37  jmp     short loc_180038A3E
0x180038a39  cmp     eax, 24h ; '$'
0x180038a3c  jnz     short loc_180038A5A
0x180038a3e  test    ebx, ebx
0x180038a40  js      loc_180038CB3
0x180038a46  mov     rdx, rsi; Uuid
0x180038a49  mov     rcx, rdi; StringUuid
0x180038a4c  call    cs:__imp_UuidFromStringW
0x180038a52  test    eax, eax
0x180038a54  jz      loc_180038CB3
0x180038a5a  mov     ebx, 8024000Eh
0x180038a5f  jmp     loc_180038CB3
0x180038a64  mov     eax, edx
0x180038a66  cmp     word ptr [rbp+pvarg+8], dx
0x180038a6a  setnz   al
0x180038a6d  jmp     short loc_180038A91
0x180038a6f  test    rdi, rdi
0x180038a72  jz      short loc_180038A5A
0x180038a74  xor     r8d, r8d
0x180038a77  mov     rdx, rsi
0x180038a7a  mov     rcx, rdi
0x180038a7d  call    StringToFileTime
0x180038a82  mov     ebx, eax
0x180038a84  cmp     eax, 80070057h
0x180038a89  jmp     loc_180038989
0x180038a8e  mov     eax, dword ptr [rbp+pvarg+8]
0x180038a91  mov     [rsi], eax
0x180038a93  jmp     loc_180038CB3
0x180038a98  mov     r14, [r14]
0x180038a9b  test    rdi, rdi
0x180038a9e  jz      short loc_180038A5A
0x180038aa0  mov     r15d, edx
0x180038aa3  cmp     [r14+8], edx
0x180038aa7  jbe     loc_180038985
  ... truncated ...
```
