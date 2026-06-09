# CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertificateMsg(void)

- ea: `0x180030370`
- end: `0x180030813`
- name: `?GenerateCertificateMsg@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@QEAAKXZ`
- size: `1187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033188`

## callees

- `0x180030370`
- `0x180030820`
- `0x1800308a0`
- `0x180091010`

## import_xrefs

- `CRYPT32!CertCompareCertificateName` at `0x1800307b3`
- `CRYPT32!CertCompareCertificateName` at `0x1800307b3`

## pseudocode

```c
__int64 __fastcall CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertificateMsg(__int64 a1)
{
  unsigned __int16 v1; // di
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  char v8; // al
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  struct _CRYPTOAPI_BLOB *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 *v16; // rsi
  __int64 v17; // rsi
  unsigned int i; // edi
  __int64 v19; // r14
  char v20; // r12
  unsigned int v21; // r15d
  __int64 v22; // rcx
  __int64 v23; // r14
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int cbData; // eax
  unsigned __int16 v27; // si
  __int64 v28; // rcx
  BYTE *pbData; // rdi
  __int64 v30; // rcx
  _WORD v31[2]; // [rsp+20h] [rbp-40h] BYREF
  _WORD v32[10]; // [rsp+24h] [rbp-3Ch] BYREF
  char v33; // [rsp+80h] [rbp+20h] BYREF
  char v34; // [rsp+88h] [rbp+28h] BYREF
  char v35; // [rsp+90h] [rbp+30h] BYREF
  __int16 v36; // [rsp+98h] [rbp+38h] BYREF

  v1 = *(_WORD *)(a1 + 104);
  if ( v1 < 4u )
    return 87;
  v3 = *(_QWORD *)(a1 + 24);
  v34 = 11;
  result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v3 + 32LL))(v3, 1, &v34);
  if ( !(_DWORD)result )
  {
    v5 = *(_QWORD *)(a1 + 24);
    v35 = 0;
    result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v5 + 32LL))(v5, 1, &v35);
    if ( !(_DWORD)result )
    {
      v6 = *(_QWORD *)(a1 + 24);
      v36 = __ROR2__(v1 - 4, 8);
      result = (*(__int64 (__fastcall **)(__int64, __int64, __int16 *))(*(_QWORD *)v6 + 32LL))(v6, 2, &v36);
      if ( !(_DWORD)result )
      {
        v7 = *(_QWORD *)(a1 + 8);
        v8 = (*(_DWORD *)(v7 + 88) & 0x40051555) != 0 ? 0 : *(_BYTE *)(v7 + 2952);
        v9 = *(_QWORD *)(a1 + 24);
        v33 = v8;
        result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v9 + 32LL))(v9, 1, &v33);
        if ( !(_DWORD)result )
        {
          if ( !v33 )
            goto LABEL_73;
          if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 2944LL) )
            return 2148074244LL;
          result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 32LL))(*(_QWORD *)(a1 + 24));
          if ( !(_DWORD)result )
          {
LABEL_73:
            v10 = *(_QWORD *)(a1 + 24);
            v34 = 0;
            result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v10 + 32LL))(v10, 1, &v34);
            if ( !(_DWORD)result )
            {
              v11 = *(_QWORD *)(a1 + 24);
              v36 = __ROR2__(*(_WORD *)(a1 + 38), 8);
              result = (*(__int64 (__fastcall **)(__int64, __int64, __int16 *))(*(_QWORD *)v11 + 32LL))(v11, 2, &v36);
              if ( !(_DWORD)result )
              {
                v14 = *(_QWORD *)(a1 + 40);
                if ( !v14 )
                {
                  result = 1359;
                  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 88LL) & 0x40051555) == 0 )
                    result = 0;
                  goto LABEL_40;
                }
                v15 = *(_QWORD *)(v14 + 64);
                if ( v15 )
                {
                  v16 = *(__int64 **)(v15 + 16);
                  if ( v16 )
                  {
                    if ( *(_DWORD *)(v15 + 12) )
                    {
                      v17 = *v16;
                      if ( v17 && *(_QWORD *)(v17 + 16) && *(_DWORD *)(v17 + 12) )
                      {
                        for ( i = 0; ; ++i )
                        {
                          v13 = 65530;
                          if ( i >= *(_DWORD *)(v17 + 12) )
                            return (*(__int64 (__fastcall **)(_QWORD, struct _CRYPTOAPI_BLOB *, __int64))(**(_QWORD **)(a1 + 24) + 40LL))(
                                     *(_QWORD *)(a1 + 24),
                                     v12,
                                     v13);
                          v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v17 + 16) + 8LL * i) + 8LL);
                          if ( !v19 )
                            return 87;
                          v12 = *(struct _CRYPTOAPI_BLOB **)(v19 + 24);
                          if ( !v12 )
                            return 87;
                          if ( !*(_BYTE *)(a1 + 48) )
                          {
                            if ( !i )
                              goto LABEL_24;
                            if ( CertCompareCertificateName(*(_DWORD *)v19, v12 + 3, v12 + 5) )
                              return (*(__int64 (__fastcall **)(_QWORD, struct _CRYPTOAPI_BLOB *, __int64))(**(_QWORD **)(a1 + 24) + 40LL))(
                                       *(_QWORD *)(a1 + 24),
                                       v12,
                                       v13);
                            v13 = 65530;
                          }
                          if ( i )
                          {
                            v20 = 0;
                            goto LABEL_25;
                          }
LABEL_24:
                          v20 = 1;
LABEL_25:
                          v21 = *(_DWORD *)(v19 + 16);
                          if ( v21 > 0xFFFA || v20 && 65530 - (unsigned __int16)v21 < *(unsigned __int16 *)(a1 + 122) )
                            goto LABEL_67;
                          v22 = *(_QWORD *)(a1 + 24);
                          v23 = *(_QWORD *)(v19 + 8);
                          v35 = 0;
                          result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v22 + 32LL))(
                                     v22,
                                     1,
                                     &v35);
                          if ( (_DWORD)result )
                            return result;
                          v24 = *(_QWORD *)(a1 + 24);
                          v31[0] = __ROR2__(v21, 8);
                          result = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v24 + 32LL))(
                                     v24,
                                     2,
                                     v31);
                          if ( (_DWORD)result )
                            return result;
                          if ( v23 )
                          {
                            result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 24) + 32LL))(
                                       *(_QWORD *)(a1 + 24),
                                       (unsigned __int16)v21,
                                       v23);
                            if ( (_DWORD)result )
                              return result;
                          }
                          v25 = *(_QWORD *)(a1 + 24);
                          if ( v20 )
                          {
                            v32[0] = __ROR2__(*(_WORD *)(a1 + 122), 8);
                            result = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v25 + 32LL))(
                                       v25,
                                       2,
                                       v32);
                            if ( (_DWORD)result )
                              return result;
                            if ( *(_WORD *)(a1 + 122) )
                            {
                              if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 88LL) & 0x40051555) != 0 )
                              {
                                if ( *(_WORD *)(a1 + 120) )
                                {
                                  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
                                  if ( (_DWORD)result )
                                    return result;
                                }
                              }
                              LOBYTE(v12) = 11;
                              result = CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateGenericExtensions(
                                         a1,
                                         v12);
                            }
                            else
                            {
                              result = 0;
                            }
                          }
                          else
                          {
                            v32[0] = 0;
                            result = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v25 + 32LL))(
                                       v25,
                                       2,
                                       v32);
                          }
                          if ( (_DWORD)result )
                            return result;
                        }
                      }
                      return 87;
                    }
                  }
                }
                v12 = *(struct _CRYPTOAPI_BLOB **)(v14 + 32);
                if ( !v12 )
                  return 87;
                cbData = v12[1].cbData;
                if ( cbData > 0xFFFA )
                {
LABEL_67:
                  result = 87;
                  goto LABEL_40;
                }
                v27 = v12[1].cbData;
                if ( 65530 - (unsigned __int16)cbData < *(unsigned __int16 *)(a1 + 122) )
                {
                  result = 87;
                  goto LABEL_40;
                }
                v28 = *(_QWORD *)(a1 + 24);
                pbData = v12->pbData;
                v35 = 0;
                result = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v28 + 32LL))(v28, 1, &v35);
                if ( !(_DWORD)result )
                {
                  v30 = *(_QWORD *)(a1 + 24);
                  v32[0] = __ROR2__(v27, 8);
                  result = (*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v30 + 32LL))(v30, 2, v32);
                  if ( !(_DWORD)result )
                  {
                    if ( !pbData
                      || (result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, BYTE *))(**(_QWORD **)(a1 + 24) + 32LL))(
                                     *(_QWORD *)(a1 + 24),
                                     v27,
                                     pbData),
                          !(_DWORD)result) )
                    {
                      result = CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertificateEntryExtensions(a1);
                      if ( !(_DWORD)result )
                        return (*(__int64 (__fastcall **)(_QWORD, struct _CRYPTOAPI_BLOB *, __int64))(**(_QWORD **)(a1 + 24) + 40LL))(
                                 *(_QWORD *)(a1 + 24),
                                 v12,
                                 v13);
LABEL_40:
                      if ( (_DWORD)result )
                        return result;
                      return (*(__int64 (__fastcall **)(_QWORD, struct _CRYPTOAPI_BLOB *, __int64))(**(_QWORD **)(a1 + 24)
                                                                                                  + 40LL))(
                               *(_QWORD *)(a1 + 24),
                               v12,
                               v13);
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
  return result;
}

```

## disassembly

```asm
0x180030370  push    rbp
0x180030372  push    rbx
0x180030373  push    rdi
0x180030374  mov     rbp, rsp
0x180030377  sub     rsp, 60h
0x18003037b  movzx   edi, word ptr [rcx+68h]
0x18003037f  mov     rbx, rcx
0x180030382  cmp     di, 4
0x180030386  jb      loc_180030761
0x18003038c  mov     rcx, [rcx+18h]
0x180030390  lea     r8, [rbp+arg_8]
0x180030394  mov     [rbp+arg_8], 0Bh
0x180030398  mov     edx, 1
0x18003039d  mov     rax, [rcx]
0x1800303a0  mov     rax, [rax+20h]
0x1800303a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a9  test    eax, eax
0x1800303ab  jnz     loc_18003067F
0x1800303b1  mov     rcx, [rbx+18h]
0x1800303b5  lea     r8, [rbp+arg_10]
0x1800303b9  mov     [rbp+arg_10], al
0x1800303bc  mov     edx, 1
0x1800303c1  mov     rax, [rcx]
0x1800303c4  mov     rax, [rax+20h]
0x1800303c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303cd  test    eax, eax
0x1800303cf  jnz     loc_18003067F
0x1800303d5  mov     rcx, [rbx+18h]
0x1800303d9  lea     r8, [rbp+arg_18]
0x1800303dd  sub     di, 4
0x1800303e1  mov     edx, 2
0x1800303e6  ror     di, 8
0x1800303ea  mov     [rbp+arg_18], di
0x1800303ee  mov     rax, [rcx]
0x1800303f1  mov     rax, [rax+20h]
0x1800303f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303fa  test    eax, eax
0x1800303fc  jnz     loc_18003067F
0x180030402  mov     rax, [rbx+8]
0x180030406  test    dword ptr [rax+58h], 40051555h
0x18003040d  jbe     loc_180030687
0x180030413  xor     al, al
0x180030415  mov     rcx, [rbx+18h]
0x180030419  lea     r8, [rbp+arg_0]
0x18003041d  mov     [rbp+arg_0], al
0x180030420  mov     edx, 1
0x180030425  mov     rax, [rcx]
0x180030428  mov     rax, [rax+20h]
0x18003042c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030431  test    eax, eax
0x180030433  jnz     loc_18003067F
0x180030439  movzx   edx, [rbp+arg_0]
0x18003043d  test    dl, dl
0x18003043f  jnz     loc_18003078A
0x180030445  mov     rcx, [rbx+18h]
0x180030449  lea     r8, [rbp+arg_8]
0x18003044d  mov     [rsp+60h+var_8], rsi
0x180030452  mov     edx, 1
0x180030457  mov     [rsp+60h+var_10], r12
0x18003045c  mov     [rbp+arg_8], 0
0x180030460  mov     rax, [rcx]
0x180030463  mov     [rsp+60h+var_18], r13
0x180030468  mov     [rsp+60h+var_20], r14
0x18003046d  mov     [rsp+60h+var_28], r15
0x180030472  mov     rax, [rax+20h]
0x180030476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003047b  test    eax, eax
0x18003047d  jnz     loc_180030666
0x180030483  movzx   eax, word ptr [rbx+26h]
0x180030487  lea     r8, [rbp+arg_18]
0x18003048b  mov     rcx, [rbx+18h]
0x18003048f  mov     edx, 2
0x180030494  ror     ax, 8
0x180030498  mov     [rbp+arg_18], ax
0x18003049c  mov     rax, [rcx]
0x18003049f  mov     rax, [rax+20h]
0x1800304a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304a8  test    eax, eax
0x1800304aa  jnz     loc_180030666
0x1800304b0  mov     rcx, [rbx+28h]
0x1800304b4  test    rcx, rcx
0x1800304b7  jz      loc_180030638
0x1800304bd  mov     rax, [rcx+40h]
0x1800304c1  test    rax, rax
0x1800304c4  jz      loc_180030693
0x1800304ca  mov     rsi, [rax+10h]
0x1800304ce  test    rsi, rsi
0x1800304d1  jz      loc_180030693
0x1800304d7  cmp     dword ptr [rax+0Ch], 0
0x1800304db  jz      loc_180030693
0x1800304e1  mov     rsi, [rsi]
0x1800304e4  test    rsi, rsi
0x1800304e7  jz      loc_18003069C
0x1800304ed  cmp     qword ptr [rsi+10h], 0
0x1800304f2  jz      loc_18003069C
0x1800304f8  cmp     dword ptr [rsi+0Ch], 0
0x1800304fc  jz      loc_18003069C
0x180030502  xor     r13d, r13d
0x180030505  mov     edi, r13d
0x180030508  mov     r8d, 0FFFAh
0x18003050e  cmp     edi, [rsi+0Ch]
0x180030511  jnb     loc_180030656
0x180030517  mov     rax, [rsi+10h]
0x18003051b  mov     ecx, edi
0x18003051d  mov     rcx, [rax+rcx*8]
0x180030521  mov     r14, [rcx+8]
0x180030525  test    r14, r14
0x180030528  jz      loc_18003069C
0x18003052e  mov     rdx, [r14+18h]
0x180030532  test    rdx, rdx
0x180030535  jz      loc_18003069C
0x18003053b  cmp     [rbx+30h], r13b
0x18003053f  jnz     loc_180030751
0x180030545  test    edi, edi
0x180030547  jnz     loc_1800307A8
0x18003054d  mov     r12b, 1
0x180030550  mov     r15d, [r14+10h]
0x180030554  cmp     r15d, r8d
0x180030557  ja      loc_1800307FF
0x18003055d  test    r12b, r12b
0x180030560  jz      short loc_180030577
0x180030562  movzx   eax, r15w
0x180030566  mov     ecx, r8d
0x180030569  sub     ecx, eax
0x18003056b  movzx   eax, word ptr [rbx+7Ah]
0x18003056f  cmp     ecx, eax
0x180030571  jl      loc_1800307FF
0x180030577  mov     rcx, [rbx+18h]
0x18003057b  lea     r8, [rbp+arg_10]
0x18003057f  mov     r14, [r14+8]
0x180030583  mov     edx, 1
0x180030588  mov     [rbp+arg_10], r13b
0x18003058c  mov     rax, [rcx]
0x18003058f  mov     rax, [rax+20h]
0x180030593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030598  test    eax, eax
0x18003059a  jnz     loc_180030666
0x1800305a0  mov     rcx, [rbx+18h]
0x1800305a4  lea     r8, [rbp+var_40]
0x1800305a8  movzx   eax, r15w
0x1800305ac  mov     edx, 2
0x1800305b1  ror     ax, 8
0x1800305b5  mov     [rbp+var_40], ax
0x1800305b9  mov     rax, [rcx]
0x1800305bc  mov     rax, [rax+20h]
0x1800305c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305c5  test    eax, eax
0x1800305c7  jnz     loc_180030666
0x1800305cd  test    r14, r14
0x1800305d0  jz      short loc_1800305ED
0x1800305d2  mov     rcx, [rbx+18h]
0x1800305d6  mov     r8, r14
0x1800305d9  movzx   edx, r15w
0x1800305dd  mov     rax, [rcx]
0x1800305e0  mov     rax, [rax+20h]
0x1800305e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305e9  test    eax, eax
0x1800305eb  jnz     short loc_180030666
0x1800305ed  mov     rcx, [rbx+18h]
0x1800305f1  mov     edx, 2
0x1800305f6  lea     r8, [rbp+var_3C]
0x1800305fa  test    r12b, r12b
0x1800305fd  jz      loc_1800307E9
0x180030603  movzx   eax, word ptr [rbx+7Ah]
0x180030607  ror     ax, 8
0x18003060b  mov     [rbp+var_3C], ax
0x18003060f  mov     rax, [rcx]
0x180030612  mov     rax, [rax+20h]
0x180030616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003061b  test    eax, eax
0x18003061d  jnz     short loc_180030666
0x18003061f  cmp     [rbx+7Ah], r13w
0x180030624  jnz     loc_18003076E
0x18003062a  mov     eax, r13d
0x18003062d  test    eax, eax
0x18003062f  jnz     short loc_180030666
0x180030631  inc     edi
0x180030633  jmp     loc_180030508
0x180030638  mov     rax, [rbx+8]
0x18003063c  mov     r13d, 0
0x180030642  test    dword ptr [rax+58h], 40051555h
0x180030649  mov     eax, 54Fh
0x18003064e  cmovbe  eax, r13d
0x180030652  test    eax, eax
0x180030654  jnz     short loc_180030666
0x180030656  mov     rcx, [rbx+18h]
0x18003065a  mov     rax, [rcx]
0x18003065d  mov     rax, [rax+28h]
0x180030661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030666  mov     r14, [rsp+60h+var_20]
0x18003066b  mov     r13, [rsp+60h+var_18]
0x180030670  mov     r12, [rsp+60h+var_10]
0x180030675  mov     rsi, [rsp+60h+var_8]
0x18003067a  mov     r15, [rsp+60h+var_28]
0x18003067f  add     rsp, 60h
0x180030683  pop     rdi
0x180030684  pop     rbx
0x180030685  pop     rbp
0x180030686  retn
0x180030687  movzx   eax, byte ptr [rax+0B88h]
0x18003068e  jmp     loc_180030415
0x180030693  mov     rdx, [rcx+20h]
0x180030697  test    rdx, rdx
0x18003069a  jnz     short loc_1800306A3
0x18003069c  mov     eax, 57h ; 'W'
0x1800306a1  jmp     short loc_180030666
0x1800306a3  mov     eax, [rdx+10h]
0x1800306a6  mov     ecx, 0FFFAh
0x1800306ab  cmp     eax, ecx
0x1800306ad  ja      loc_1800307FF
0x1800306b3  movzx   esi, ax
0x1800306b6  movzx   eax, word ptr [rbx+7Ah]
0x1800306ba  sub     ecx, esi
0x1800306bc  cmp     ecx, eax
0x1800306be  jl      loc_180030809
0x1800306c4  mov     rcx, [rbx+18h]
0x1800306c8  lea     r8, [rbp+arg_10]
0x1800306cc  mov     rdi, [rdx+8]
0x1800306d0  mov     edx, 1
0x1800306d5  mov     [rbp+arg_10], 0
0x1800306d9  mov     rax, [rcx]
0x1800306dc  mov     rax, [rax+20h]
0x1800306e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306e5  test    eax, eax
0x1800306e7  jnz     loc_180030666
0x1800306ed  mov     rcx, [rbx+18h]
0x1800306f1  lea     r8, [rbp+var_3C]
0x1800306f5  movzx   eax, si
0x1800306f8  mov     edx, 2
0x1800306fd  ror     ax, 8
0x180030701  mov     [rbp+var_3C], ax
0x180030705  mov     rax, [rcx]
0x180030708  mov     rax, [rax+20h]
0x18003070c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030711  test    eax, eax
0x180030713  jnz     loc_180030666
0x180030719  test    rdi, rdi
0x18003071c  jz      short loc_18003073C
0x18003071e  mov     rcx, [rbx+18h]
0x180030722  mov     r8, rdi
0x180030725  movzx   edx, si
0x180030728  mov     rax, [rcx]
0x18003072b  mov     rax, [rax+20h]
0x18003072f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030734  test    eax, eax
0x180030736  jnz     loc_180030666
0x18003073c  mov     rcx, rbx
0x18003073f  call    ?GenerateCertificateEntryExtensions@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@IEAAKXZ; CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateCertificateEntryExtensions(void)
0x180030744  test    eax, eax
0x180030746  jz      loc_180030656
0x18003074c  jmp     loc_180030652
0x180030751  test    edi, edi
0x180030753  jz      loc_18003054D
0x180030759  xor     r12b, r12b
0x18003075c  jmp     loc_180030550
0x180030761  mov     eax, 57h ; 'W'
0x180030766  add     rsp, 60h
0x18003076a  pop     rdi
0x18003076b  pop     rbx
0x18003076c  pop     rbp
0x18003076d  retn
0x18003076e  mov     rax, [rbx+8]
0x180030772  test    dword ptr [rax+58h], 40051555h
0x180030779  ja      short loc_1800307C9
0x18003077b  mov     dl, 0Bh
0x18003077d  mov     rcx, rbx
0x180030780  call    ?GenerateGenericExtensions@?$CTls13Handshake@VCTls13ServerContext@@VCTls13ExtServer@@@@IEAAKW4eTlsHandshakeType@@@Z; CTls13Handshake<CTls13ServerContext,CTls13ExtServer>::GenerateGenericExtensions(eTlsHandshakeType)
0x180030785  jmp     loc_18003062D
0x18003078a  mov     rax, [rbx+8]
0x18003078e  mov     r8, [rax+0B80h]
0x180030795  test    r8, r8
0x180030798  jnz     loc_18008DD36
0x18003079e  mov     eax, 80090304h
0x1800307a3  jmp     loc_18003067F
0x1800307a8  mov     ecx, [r14]; dwCertEncodingType
0x1800307ab  lea     r8, [rdx+50h]; pCertName2
0x1800307af  add     rdx, 30h ; '0'; pCertName1
0x1800307b3  call    cs:__imp_CertCompareCertificateName
0x1800307b9  test    eax, eax
0x1800307bb  jnz     loc_180030656
0x1800307c1  mov     r8d, 0FFFAh
0x1800307c7  jmp     short loc_180030751
0x1800307c9  cmp     [rbx+78h], r13w
0x1800307ce  jbe     short loc_18003077B
0x1800307d0  mov     rax, [rbx]
0x1800307d3  mov     rcx, rbx
0x1800307d6  mov     rax, [rax+10h]
0x1800307da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307df  test    eax, eax
0x1800307e1  jnz     loc_180030666
0x1800307e7  jmp     short loc_18003077B
0x1800307e9  mov     [rbp+var_3C], r13w
0x1800307ee  mov     rax, [rcx]
0x1800307f1  mov     rax, [rax+20h]
0x1800307f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307fa  jmp     loc_18003062D
0x1800307ff  mov     eax, 57h ; 'W'
0x180030804  jmp     loc_180030652
0x180030809  mov     eax, 57h ; 'W'
0x18003080e  jmp     loc_180030652
  ... truncated ...
```
