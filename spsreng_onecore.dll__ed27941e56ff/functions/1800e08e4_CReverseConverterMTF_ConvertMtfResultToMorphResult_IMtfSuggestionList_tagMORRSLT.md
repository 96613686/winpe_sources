# CReverseConverterMTF::ConvertMtfResultToMorphResult(IMtfSuggestionList *,tagMORRSLT * *)

- ea: `0x1800e08e4`
- end: `0x1800e0c9c`
- name: `?ConvertMtfResultToMorphResult@CReverseConverterMTF@@CAJPEAUIMtfSuggestionList@@PEAPEAUtagMORRSLT@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(struct IMtfSuggestionList *, struct tagMORRSLT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e0cb0`

## callees

- `0x1800040b8`
- `0x18005b268`
- `0x1800e08e4`
- `0x1800e0f54`
- `0x1800e108c`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800e0b06`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800e0b78`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800e0b06`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800e0b78`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e09d9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e09e5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e0aeb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e0b5d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e09d9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e09e5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e0aeb`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e0b5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0c11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0c11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReverseConverterMTF::ConvertMtfResultToMorphResult(
        struct IMtfSuggestionList *a1,
        struct tagMORRSLT **a2)
{
  int Win32Error; // ebx
  unsigned __int16 v3; // di
  __int16 v4; // bx
  __int16 v5; // ax
  int v6; // eax
  _QWORD *v7; // rdi
  unsigned __int64 v8; // r15
  _WORD *v9; // r12
  unsigned __int64 v10; // r14
  _WORD *v11; // r13
  int v12; // eax
  unsigned __int16 v13; // si
  int v14; // eax
  __int16 v15; // dx
  _WORD *v16; // rcx
  unsigned __int16 v17; // si
  __int16 v18; // r8
  __int64 v19; // rcx
  unsigned __int16 i; // ax
  int v21; // r8d
  __int64 v23; // [rsp+20h] [rbp-A9h] BYREF
  __int64 v24; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v25; // [rsp+30h] [rbp-99h] BYREF
  _WORD *v26; // [rsp+38h] [rbp-91h]
  __int64 v27; // [rsp+40h] [rbp-89h]
  __int64 v28; // [rsp+48h] [rbp-81h]
  BSTR v29[2]; // [rsp+50h] [rbp-79h] BYREF
  BSTR v30[2]; // [rsp+60h] [rbp-69h]
  __int128 v31; // [rsp+70h] [rbp-59h]
  __int64 v32; // [rsp+80h] [rbp-49h]
  int v33; // [rsp+90h] [rbp-39h] BYREF
  BSTR v34; // [rsp+98h] [rbp-31h]
  BSTR pbstr; // [rsp+A0h] [rbp-29h]
  unsigned int v36; // [rsp+130h] [rbp+67h] BYREF
  struct tagMORRSLT **v37; // [rsp+138h] [rbp+6Fh]
  LPVOID pv; // [rsp+140h] [rbp+77h] BYREF
  int v39; // [rsp+148h] [rbp+7Fh]

  v37 = a2;
  pv = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  if ( a1 )
  {
    Win32Error = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, _QWORD, __int64 *))(*(_QWORD *)a1 + 32LL))(
                   a1,
                   0,
                   &v25);
    if ( Win32Error >= 0 )
    {
      Win32Error = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
                     v25,
                     &GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a,
                     &v24);
      if ( Win32Error >= 0 )
      {
        v36 = 0;
        Win32Error = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 56LL))(v24, &v36);
        if ( Win32Error >= 0 )
        {
          v3 = v36;
          memset_0(&v33, 0, 0x48u);
          v33 = 3;
          Win32Error = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 40LL))(v24, &v33);
          if ( Win32Error >= 0 )
          {
            v4 = SysStringLen(pbstr);
            v5 = SysStringLen(v34);
            v6 = CReverseConverterMTF::InitializeOutputStruct(v5, v4, v3, (struct tagMORRSLT **)&pv);
            v7 = pv;
            Win32Error = v6;
            if ( v6 < 0 )
              goto LABEL_34;
            v8 = *(_QWORD *)((char *)pv + 4);
            v9 = (_WORD *)*((_QWORD *)pv + 4);
            v10 = *(_QWORD *)((char *)pv + 14);
            v11 = (_WORD *)*((_QWORD *)pv + 7);
            v26 = (_WORD *)*((_QWORD *)pv + 5);
            v12 = 0;
            LODWORD(pv) = 0;
            while ( 1 )
            {
              v39 = v12;
              if ( (unsigned __int16)v12 >= v36 )
                break;
              Win32Error = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 64LL))(
                             v24,
                             (unsigned __int16)v12,
                             &v23);
              if ( Win32Error < 0 )
                goto LABEL_34;
              if ( v23 )
              {
                if ( v8 < *(_QWORD *)((char *)v7 + 4)
                  || v8 >= *(_QWORD *)((char *)v7 + 14)
                  || v10 < *(_QWORD *)((char *)v7 + 14)
                  || v10 >= v7[3] )
                {
LABEL_33:
                  Win32Error = -2147467259;
                  goto LABEL_34;
                }
                *(_OWORD *)v29 = 0;
                v32 = 0;
                LODWORD(v29[0]) = 19;
                *(_OWORD *)v30 = 0;
                v31 = 0;
                Win32Error = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v23 + 40LL))(v23, v29);
                if ( Win32Error < 0 )
                  goto LABEL_34;
                if ( v23 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                  v23 = 0;
                }
                v13 = SysStringLen(v30[0]);
                v27 = v13;
                v14 = _o_wcscpy_s(v10, v13 + 1LL, v30[0]);
                if ( v14 )
                  goto LABEL_43;
                v15 = (__int16)pv;
                v11[1] = (__int64)(unsigned int)(v10 - *(_DWORD *)((char *)v7 + 14)) >> 1;
                v16 = v26;
                v11[3] = v13;
                while ( (unsigned __int16)v14 < v13 )
                {
                  if ( (unsigned __int64)v16 < v7[5] || (unsigned __int64)v16 >= v7[7] )
                    goto LABEL_33;
                  *v16++ = v15;
                  v26 = v16;
                  LOWORD(v14) = v14 + 1;
                }
                v17 = SysStringLen(v29[1]);
                v28 = v17;
                if ( (unsigned int)_o_wcscpy_s(v8, v17 + 1LL, v29[1]) )
                {
LABEL_43:
                  Win32Error = SpHrFromLastWin32Error();
                  break;
                }
                v18 = (__int16)pv;
                *v11 = (__int64)(unsigned int)(v8 - *((_DWORD *)v7 + 1)) >> 1;
                v19 = (unsigned __int16)v11[1];
                v11[2] = v17;
                *(_WORD *)(v7[3] + 2 * v19) = v19;
                for ( i = 0; i < v17; ++i )
                {
                  if ( (unsigned __int64)v9 < v7[4] || (unsigned __int64)v9 >= v7[5] )
                    goto LABEL_33;
                  *v9++ = v18;
                }
                v11[6] = CReverseConverterMTF::MtfPartOfSpeechToIME(WORD5(v31));
                v11 += 12;
                LOWORD(v21) = v21 + 1;
                LODWORD(pv) = v21;
                v10 += 2 * v27;
                v8 += 2 * v28;
              }
              HIWORD(v12) = HIWORD(v39);
              LOWORD(v12) = v39 + 1;
            }
            if ( Win32Error < 0 )
            {
LABEL_34:
              if ( v7 )
                CoTaskMemFree(v7);
            }
            else
            {
              *v37 = (struct tagMORRSLT *)v7;
            }
          }
        }
      }
    }
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v23 = 0;
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v24 = 0;
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x1800e08e4  mov     [rsp-8+arg_8], rdx
0x1800e08e9  push    rbp
0x1800e08ea  push    rbx
0x1800e08eb  push    rsi
0x1800e08ec  push    rdi
0x1800e08ed  push    r12
0x1800e08ef  push    r13
0x1800e08f1  push    r14
0x1800e08f3  push    r15
0x1800e08f5  lea     rbp, [rsp-1Fh]
0x1800e08fa  sub     rsp, 0E8h
0x1800e0901  mov     [rbp+57h+pv], 0
0x1800e0909  mov     [rsp+120h+var_F0], 0
0x1800e0912  mov     [rsp+120h+var_F8], 0
0x1800e091b  mov     [rsp+120h+var_100], 0
0x1800e0924  test    rcx, rcx
0x1800e0927  jnz     short loc_1800E0933
0x1800e0929  mov     ebx, 80004005h
0x1800e092e  jmp     loc_1800E0C6B
0x1800e0933  mov     rax, [rcx]
0x1800e0936  lea     r8, [rsp+120h+var_F0]
0x1800e093b  xor     edx, edx
0x1800e093d  mov     rax, [rax+20h]
0x1800e0941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0946  mov     ebx, eax
0x1800e0948  test    eax, eax
0x1800e094a  js      loc_1800E0C17
0x1800e0950  mov     rcx, [rsp+120h+var_F0]
0x1800e0955  lea     r8, [rsp+120h+var_F8]
0x1800e095a  lea     rdx, _GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a
0x1800e0961  mov     rax, [rcx]
0x1800e0964  mov     rax, [rax]
0x1800e0967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e096c  mov     ebx, eax
0x1800e096e  test    eax, eax
0x1800e0970  js      loc_1800E0C17
0x1800e0976  mov     rcx, [rsp+120h+var_F8]
0x1800e097b  lea     rdx, [rbp+57h+arg_0]
0x1800e097f  mov     [rbp+57h+arg_0], 0
0x1800e0986  mov     rax, [rcx]
0x1800e0989  mov     rax, [rax+38h]
0x1800e098d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0992  mov     ebx, eax
0x1800e0994  test    eax, eax
0x1800e0996  js      loc_1800E0C17
0x1800e099c  movzx   edi, word ptr [rbp+57h+arg_0]
0x1800e09a0  lea     rcx, [rbp+57h+var_90]; void *
0x1800e09a4  xor     edx, edx; Val
0x1800e09a6  lea     r8d, [rdx+48h]; Size
0x1800e09aa  call    memset_0
0x1800e09af  mov     rcx, [rsp+120h+var_F8]
0x1800e09b4  lea     rdx, [rbp+57h+var_90]
0x1800e09b8  mov     [rbp+57h+var_90], 3
0x1800e09bf  mov     rax, [rcx]
0x1800e09c2  mov     rax, [rax+28h]
0x1800e09c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e09cb  mov     ebx, eax
0x1800e09cd  test    eax, eax
0x1800e09cf  js      loc_1800E0C17
0x1800e09d5  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1800e09d9  call    cs:__imp_SysStringLen
0x1800e09df  mov     rcx, [rbp+57h+var_88]; pbstr
0x1800e09e3  mov     ebx, eax
0x1800e09e5  call    cs:__imp_SysStringLen
0x1800e09eb  lea     r9, [rbp+57h+pv]; struct tagMORRSLT **
0x1800e09ef  movzx   r8d, di; unsigned __int16
0x1800e09f3  mov     ecx, eax; unsigned __int16
0x1800e09f5  movzx   edx, bx; unsigned __int16
0x1800e09f8  call    ?InitializeOutputStruct@CReverseConverterMTF@@CAJGGGPEAPEAUtagMORRSLT@@@Z; CReverseConverterMTF::InitializeOutputStruct(ushort,ushort,ushort,tagMORRSLT * *)
0x1800e09fd  mov     rdi, [rbp+57h+pv]
0x1800e0a01  mov     ebx, eax
0x1800e0a03  test    eax, eax
0x1800e0a05  js      loc_1800E0C09
0x1800e0a0b  mov     rax, [rdi+28h]
0x1800e0a0f  mov     r15, [rdi+4]
0x1800e0a13  mov     r12, [rdi+20h]
0x1800e0a17  mov     r14, [rdi+0Eh]
0x1800e0a1b  mov     r13, [rdi+38h]
0x1800e0a1f  mov     [rsp+120h+var_E8], rax
0x1800e0a24  xor     eax, eax
0x1800e0a26  mov     dword ptr [rbp+57h+pv], 0
0x1800e0a2d  movzx   edx, ax
0x1800e0a30  mov     [rbp+57h+arg_18], eax
0x1800e0a33  cmp     edx, [rbp+57h+arg_0]
0x1800e0a36  jnb     loc_1800E0C88
0x1800e0a3c  mov     rcx, [rsp+120h+var_F8]
0x1800e0a41  lea     r8, [rsp+120h+var_100]
0x1800e0a46  mov     rax, [rcx]
0x1800e0a49  mov     rax, [rax+40h]
0x1800e0a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0a52  mov     ebx, eax
0x1800e0a54  test    eax, eax
0x1800e0a56  js      loc_1800E0C09
0x1800e0a5c  mov     rcx, [rsp+120h+var_100]
0x1800e0a61  test    rcx, rcx
0x1800e0a64  jz      loc_1800E0BF9
0x1800e0a6a  cmp     r15, [rdi+4]
0x1800e0a6e  jb      loc_1800E0C04
0x1800e0a74  cmp     r15, [rdi+0Eh]
0x1800e0a78  jnb     loc_1800E0C04
0x1800e0a7e  cmp     r14, [rdi+0Eh]
0x1800e0a82  jb      loc_1800E0C04
0x1800e0a88  cmp     r14, [rdi+18h]
0x1800e0a8c  jnb     loc_1800E0C04
0x1800e0a92  xorps   xmm0, xmm0
0x1800e0a95  lea     rdx, [rbp+57h+var_D0]
0x1800e0a99  xor     eax, eax
0x1800e0a9b  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x1800e0a9f  mov     [rbp+57h+var_A0], rax
0x1800e0aa3  mov     dword ptr [rbp+57h+var_D0], 13h
0x1800e0aaa  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1800e0aae  movups  [rbp+57h+var_B0], xmm0
0x1800e0ab2  mov     rax, [rcx]
0x1800e0ab5  mov     rax, [rax+28h]
0x1800e0ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0abe  mov     ebx, eax
0x1800e0ac0  test    eax, eax
0x1800e0ac2  js      loc_1800E0C09
0x1800e0ac8  mov     rcx, [rsp+120h+var_100]
0x1800e0acd  test    rcx, rcx
0x1800e0ad0  jz      short loc_1800E0AE7
0x1800e0ad2  mov     rax, [rcx]
0x1800e0ad5  mov     rax, [rax+10h]
0x1800e0ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0ade  mov     [rsp+120h+var_100], 0
0x1800e0ae7  mov     rcx, [rbp+57h+var_C0]; pbstr
0x1800e0aeb  call    cs:__imp_SysStringLen
0x1800e0af1  mov     r8, [rbp+57h+var_C0]
0x1800e0af5  mov     rcx, r14
0x1800e0af8  mov     esi, eax
0x1800e0afa  movzx   eax, ax
0x1800e0afd  mov     [rsp+120h+var_E0], rax
0x1800e0b02  lea     rdx, [rax+1]
0x1800e0b06  call    cs:__imp__o_wcscpy_s
0x1800e0b0c  test    eax, eax
0x1800e0b0e  jnz     loc_1800E0C81
0x1800e0b14  mov     edx, dword ptr [rbp+57h+pv]
0x1800e0b17  mov     ecx, r14d
0x1800e0b1a  sub     ecx, [rdi+0Eh]
0x1800e0b1d  sar     rcx, 1
0x1800e0b20  mov     [r13+2], cx
0x1800e0b25  mov     rcx, [rsp+120h+var_E8]
0x1800e0b2a  mov     [r13+6], si
0x1800e0b2f  cmp     ax, si
0x1800e0b32  jnb     short loc_1800E0B59
0x1800e0b34  cmp     rcx, [rdi+28h]
0x1800e0b38  jb      loc_1800E0C04
0x1800e0b3e  cmp     rcx, [rdi+38h]
0x1800e0b42  jnb     loc_1800E0C04
0x1800e0b48  mov     [rcx], dx
0x1800e0b4b  add     rcx, 2
0x1800e0b4f  mov     [rsp+120h+var_E8], rcx
0x1800e0b54  inc     ax
0x1800e0b57  jmp     short loc_1800E0B2F
0x1800e0b59  mov     rcx, [rbp+57h+var_D0+8]; pbstr
0x1800e0b5d  call    cs:__imp_SysStringLen
0x1800e0b63  mov     r8, [rbp+57h+var_D0+8]
0x1800e0b67  mov     rcx, r15
0x1800e0b6a  mov     esi, eax
0x1800e0b6c  movzx   eax, ax
0x1800e0b6f  mov     [rsp+120h+var_D8], rax
0x1800e0b74  lea     rdx, [rax+1]
0x1800e0b78  call    cs:__imp__o_wcscpy_s
0x1800e0b7e  test    eax, eax
0x1800e0b80  jnz     loc_1800E0C81
0x1800e0b86  mov     r8d, dword ptr [rbp+57h+pv]
0x1800e0b8a  mov     ecx, r15d
0x1800e0b8d  sub     ecx, [rdi+4]
0x1800e0b90  sar     rcx, 1
0x1800e0b93  mov     [r13+0], cx
0x1800e0b98  movzx   ecx, word ptr [r13+2]
0x1800e0b9d  mov     [r13+4], si
0x1800e0ba2  mov     rax, [rdi+18h]
0x1800e0ba6  mov     [rax+rcx*2], cx
0x1800e0baa  xor     eax, eax
0x1800e0bac  cmp     ax, si
0x1800e0baf  jnb     short loc_1800E0BCB
0x1800e0bb1  cmp     r12, [rdi+20h]
0x1800e0bb5  jb      short loc_1800E0C04
0x1800e0bb7  cmp     r12, [rdi+28h]
0x1800e0bbb  jnb     short loc_1800E0C04
0x1800e0bbd  mov     [r12], r8w
0x1800e0bc2  add     r12, 2
0x1800e0bc6  inc     ax
0x1800e0bc9  jmp     short loc_1800E0BAC
0x1800e0bcb  mov     ecx, dword ptr [rbp+57h+var_B0+8]
0x1800e0bce  shr     ecx, 10h; unsigned __int16
0x1800e0bd1  call    ?MtfPartOfSpeechToIME@CReverseConverterMTF@@CAGG@Z; CReverseConverterMTF::MtfPartOfSpeechToIME(ushort)
0x1800e0bd6  mov     [r13+0Ch], ax
0x1800e0bdb  add     r13, 18h
0x1800e0bdf  mov     rax, [rsp+120h+var_E0]
0x1800e0be4  inc     r8w
0x1800e0be8  mov     dword ptr [rbp+57h+pv], r8d
0x1800e0bec  lea     r14, [r14+rax*2]
0x1800e0bf0  mov     rax, [rsp+120h+var_D8]
0x1800e0bf5  lea     r15, [r15+rax*2]
0x1800e0bf9  mov     eax, [rbp+57h+arg_18]
0x1800e0bfc  inc     ax
0x1800e0bff  jmp     loc_1800E0A2D
0x1800e0c04  mov     ebx, 80004005h
0x1800e0c09  test    rdi, rdi
0x1800e0c0c  jz      short loc_1800E0C17
0x1800e0c0e  mov     rcx, rdi; pv
0x1800e0c11  call    cs:__imp_CoTaskMemFree
0x1800e0c17  mov     rcx, [rsp+120h+var_100]
0x1800e0c1c  test    rcx, rcx
0x1800e0c1f  jz      short loc_1800E0C36
0x1800e0c21  mov     rax, [rcx]
0x1800e0c24  mov     rax, [rax+10h]
0x1800e0c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0c2d  mov     [rsp+120h+var_100], 0
0x1800e0c36  mov     rcx, [rsp+120h+var_F8]
0x1800e0c3b  test    rcx, rcx
0x1800e0c3e  jz      short loc_1800E0C55
0x1800e0c40  mov     rax, [rcx]
0x1800e0c43  mov     rax, [rax+10h]
0x1800e0c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0c4c  mov     [rsp+120h+var_F8], 0
0x1800e0c55  mov     rcx, [rsp+120h+var_F0]
0x1800e0c5a  test    rcx, rcx
0x1800e0c5d  jz      short loc_1800E0C6B
0x1800e0c5f  mov     rax, [rcx]
0x1800e0c62  mov     rax, [rax+10h]
0x1800e0c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0c6b  mov     eax, ebx
0x1800e0c6d  add     rsp, 0E8h
0x1800e0c74  pop     r15
0x1800e0c76  pop     r14
0x1800e0c78  pop     r13
0x1800e0c7a  pop     r12
0x1800e0c7c  pop     rdi
0x1800e0c7d  pop     rsi
0x1800e0c7e  pop     rbx
0x1800e0c7f  pop     rbp
0x1800e0c80  retn
0x1800e0c81  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x1800e0c86  mov     ebx, eax
0x1800e0c88  test    ebx, ebx
0x1800e0c8a  js      loc_1800E0C09
0x1800e0c90  mov     rax, [rbp+57h+arg_8]
0x1800e0c94  mov     [rax], rdi
0x1800e0c97  jmp     loc_1800E0C17
```
