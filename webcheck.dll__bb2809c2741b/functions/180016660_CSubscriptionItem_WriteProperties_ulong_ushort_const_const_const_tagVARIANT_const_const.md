# CSubscriptionItem::WriteProperties(ulong,ushort const * const * const,tagVARIANT const * const)

- ea: `0x180016660`
- end: `0x18001694f`
- name: `?WriteProperties@CSubscriptionItem@@UEAAJKQEBQEBGQEBUtagVARIANT@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(CSubscriptionItem *__hidden this, unsigned int, const unsigned __int16 *const *const, const struct tagVARIANT *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x1800165d0`
- `0x180016660`
- `0x180019948`
- `0x18001ba08`
- `0x18001ba40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001686a`
- `msvcrt!memcpy_s` at `0x1800168b8`
- `msvcrt!memcpy_s` at `0x18001686a`
- `msvcrt!memcpy_s` at `0x1800168b8`
- `SHLWAPI!StrCmpIW` at `0x18001671f`
- `SHLWAPI!StrCmpIW` at `0x180016776`
- `SHLWAPI!StrCmpIW` at `0x18001671f`
- `SHLWAPI!StrCmpIW` at `0x180016776`
- `ADVAPI32!RegCloseKey` at `0x180016921`
- `ADVAPI32!RegCloseKey` at `0x180016921`
- `ADVAPI32!RegSetValueExW` at `0x180016764`
- `ADVAPI32!RegSetValueExW` at `0x180016764`
- `ADVAPI32!RegDeleteValueW` at `0x180016702`
- `ADVAPI32!RegDeleteValueW` at `0x180016702`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800167d4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800167d4`

## pseudocode

```c
__int64 __fastcall CSubscriptionItem::WriteProperties(
        CSubscriptionItem *this,
        unsigned int a2,
        const unsigned __int16 *const *const a3,
        const struct tagVARIANT *const a4)
{
  const struct tagVARIANT *v4; // rsi
  unsigned int v6; // edi
  unsigned int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r15
  const struct tagVARIANT *v10; // rsi
  const BYTE *lpData; // rcx
  __int64 v12; // rax
  unsigned int vt; // ecx
  UINT v14; // r14d
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  OLECHAR *bstrVal; // rcx
  unsigned int v22; // ebp
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rdi
  unsigned int v30; // edx
  unsigned int v31; // edx
  unsigned int v32; // edx
  unsigned int v33; // edx
  unsigned int v34; // edx
  unsigned int v35; // edx
  unsigned int v36; // edx
  void *v37; // rcx
  const struct tagVARIANT *pvarVal; // r8
  rsize_t v39; // rdx
  rsize_t v40; // r9
  unsigned int v41; // edx
  unsigned int v42; // edx
  unsigned int v43; // edx
  unsigned int v44; // edx
  unsigned int v45; // edx
  unsigned int i; // [rsp+30h] [rbp-48h]
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF

  v4 = a4;
  v6 = a2;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  hKey = 0;
  if ( OpenItemKey((const struct _GUID *)((char *)this + 12), 0, 0x20006u, &hKey) )
  {
    v7 = 0;
    v8 = 0;
    for ( i = 0; v7 < v6; i = v7 )
    {
      if ( v8 )
        break;
      v9 = v7;
      v10 = &v4[v7];
      if ( v10->vt )
      {
        if ( v10->vt == 8 && !StrCmpIW(a3[v7], L"Name") )
        {
          lpData = v10->pbVal;
          if ( lpData )
          {
            v12 = -1;
            do
              ++v12;
            while ( *(_WORD *)&lpData[2 * v12] );
          }
          else
          {
            LODWORD(v12) = 0;
          }
          RegSetValueExW(hKey, 0, 0, 1u, lpData, 2 * v12 + 2);
        }
        if ( !StrCmpIW(a3[v9], L"Password") )
        {
          v8 = -2147467259;
          if ( v10->vt != 8 )
            v8 = -2147024809;
          goto LABEL_65;
        }
        if ( !v10 )
        {
          v8 = -2147024809;
          goto LABEL_65;
        }
        vt = v10->vt;
        v14 = 0;
        if ( vt > 0xA )
        {
          v23 = vt - 11;
          if ( !v23
            || (v24 = v23 - 5) == 0
            || (v25 = v24 - 1) == 0
            || (v26 = v25 - 1) == 0
            || (v27 = v26 - 1) == 0
            || v27 - 3 < 2 )
          {
LABEL_41:
            v22 = 20;
            goto LABEL_42;
          }
        }
        else
        {
          if ( vt == 10 )
            goto LABEL_41;
          v15 = vt - 2;
          if ( !v15 )
            goto LABEL_41;
          v16 = v15 - 1;
          if ( !v16 )
            goto LABEL_41;
          v17 = v16 - 1;
          if ( !v17 )
            goto LABEL_41;
          v18 = v17 - 1;
          if ( !v18 )
            goto LABEL_41;
          v19 = v18 - 1;
          if ( !v19 )
            goto LABEL_41;
          v20 = v19 - 1;
          if ( !v20 )
            goto LABEL_41;
          if ( v20 == 1 )
          {
            bstrVal = v10->bstrVal;
            if ( bstrVal )
              v14 = SysStringByteLen(bstrVal);
            v22 = v14 + 24;
LABEL_42:
            v28 = (unsigned __int8 *)operator new(v22);
            v29 = v28;
            if ( v28 )
            {
              *(_DWORD *)v28 = 1262702413;
              v30 = v10->vt;
              if ( v30 > 0xA )
              {
                v41 = v30 - 11;
                if ( v41 )
                {
                  v42 = v41 - 5;
                  if ( v42 )
                  {
                    v43 = v42 - 1;
                    if ( v43 )
                    {
                      v44 = v43 - 1;
                      if ( v44 )
                      {
                        v45 = v44 - 1;
                        if ( v45 )
                        {
                          if ( v45 - 3 > 1 )
                            goto LABEL_61;
                        }
                      }
                    }
                  }
                }
              }
              else if ( v30 != 10 )
              {
                v31 = v30 - 2;
                if ( v31 )
                {
                  v32 = v31 - 1;
                  if ( v32 )
                  {
                    v33 = v32 - 1;
                    if ( v33 )
                    {
                      v34 = v33 - 1;
                      if ( v34 )
                      {
                        v35 = v34 - 1;
                        if ( v35 )
                        {
                          v36 = v35 - 1;
                          if ( v36 )
                          {
                            if ( v36 == 1 )
                            {
                              memcpy_s(v28 + 4, 0x10u, v10, 0x10u);
                              *((_DWORD *)v29 + 5) = v14;
                              v37 = v29 + 24;
                              pvarVal = v10->pvarVal;
                              v39 = v14;
                              v40 = v14;
                              goto LABEL_60;
                            }
                            goto LABEL_61;
                          }
                        }
                      }
                    }
                  }
                }
              }
              v37 = v28 + 4;
              pvarVal = v10;
              v40 = 16;
              v39 = 16;
LABEL_60:
              memcpy_s(v37, v39, pvarVal, v40);
LABEL_61:
              v8 = CSubscriptionItem::Write(this, hKey, a3[v9], v29, v22);
              operator delete(v29);
            }
            else
            {
              v8 = -2147024882;
            }
            v6 = a2;
            goto LABEL_65;
          }
        }
        v8 = -2147467263;
      }
      else
      {
        RegDeleteValueW(hKey, a3[v7]);
      }
LABEL_65:
      v4 = a4;
      v7 = i + 1;
    }
    RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v8;
}

```

## disassembly

```asm
0x180016660  mov     rax, rsp
0x180016663  mov     [rax+18h], rbx
0x180016667  mov     [rax+20h], r9
0x18001666b  mov     [rax+10h], edx
0x18001666e  mov     [rax+8], rcx
0x180016672  push    rbp
0x180016673  push    rsi
0x180016674  push    rdi
0x180016675  push    r12
0x180016677  push    r13
0x180016679  push    r14
0x18001667b  push    r15
0x18001667d  sub     rsp, 40h
0x180016681  xor     ebp, ebp
0x180016683  mov     rsi, r9
0x180016686  mov     r13, r8
0x180016689  mov     edi, edx
0x18001668b  test    edx, edx
0x18001668d  jz      loc_180016932
0x180016693  test    r8, r8
0x180016696  jz      loc_180016932
0x18001669c  test    r9, r9
0x18001669f  jz      loc_180016932
0x1800166a5  add     rcx, 0Ch; struct _GUID *
0x1800166a9  mov     [rax-40h], rbp
0x1800166ad  lea     r9, [rax-40h]; HKEY *
0x1800166b1  xor     edx, edx; int
0x1800166b3  mov     r8d, 20006h; unsigned int
0x1800166b9  call    ?OpenItemKey@@YAHPEBU_GUID@@HKPEAPEAUHKEY__@@@Z; OpenItemKey(_GUID const *,int,ulong,HKEY__ * *)
0x1800166be  test    eax, eax
0x1800166c0  jz      loc_180016929
0x1800166c6  mov     eax, ebp
0x1800166c8  mov     ebx, ebp
0x1800166ca  mov     [rsp+78h+var_48], eax
0x1800166ce  test    edi, edi
0x1800166d0  jz      loc_18001691C
0x1800166d6  lea     r14d, [rbp+8]
0x1800166da  mov     r12d, 80070057h
0x1800166e0  test    ebx, ebx
0x1800166e2  jnz     loc_18001691C
0x1800166e8  mov     r15d, eax
0x1800166eb  lea     rax, [r15+r15*2]
0x1800166ef  lea     rsi, [rsi+rax*8]
0x1800166f3  cmp     [rsi], bp
0x1800166f6  jnz     short loc_18001670D
0x1800166f8  mov     rdx, [r13+r15*8+0]; lpValueName
0x1800166fd  mov     rcx, [rsp+78h+hKey]; hKey
0x180016702  call    cs:__imp_RegDeleteValueW
0x180016708  jmp     loc_1800168F9
0x18001670d  cmp     r14w, [rsi]
0x180016711  jnz     short loc_18001676A
0x180016713  mov     rcx, [r13+r15*8+0]; psz1
0x180016718  lea     rdx, ?c_szPropName@@3QBGB; "Name"
0x18001671f  call    cs:__imp_StrCmpIW
0x180016725  test    eax, eax
0x180016727  jnz     short loc_18001676A
0x180016729  mov     rcx, [rsi+8]
0x18001672d  test    rcx, rcx
0x180016730  jz      short loc_180016741
0x180016732  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016736  inc     rax
0x180016739  cmp     [rcx+rax*2], bp
0x18001673d  jnz     short loc_180016736
0x18001673f  jmp     short loc_180016744
0x180016741  mov     rax, rbp
0x180016744  lea     eax, ds:2[rax*2]
0x18001674b  mov     r9d, 1; dwType
0x180016751  mov     [rsp+78h+cbData], eax; cbData
0x180016755  xor     r8d, r8d; Reserved
0x180016758  mov     [rsp+78h+lpData], rcx; lpData
0x18001675d  xor     edx, edx; lpValueName
0x18001675f  mov     rcx, [rsp+78h+hKey]; hKey
0x180016764  call    cs:__imp_RegSetValueExW
0x18001676a  mov     rcx, [r13+r15*8+0]; psz1
0x18001676f  lea     rdx, ?c_szPropPassword@@3QBGB; "Password"
0x180016776  call    cs:__imp_StrCmpIW
0x18001677c  test    eax, eax
0x18001677e  jnz     short loc_180016792
0x180016780  cmp     r14w, [rsi]
0x180016784  mov     ebx, 80004005h
0x180016789  cmovnz  ebx, r12d
0x18001678d  jmp     loc_1800168F9
0x180016792  test    rsi, rsi
0x180016795  jz      loc_1800168F6
0x18001679b  movzx   ecx, word ptr [rsi]
0x18001679e  mov     r14d, ebp
0x1800167a1  cmp     ecx, 0Ah
0x1800167a4  ja      short loc_1800167E3
0x1800167a6  jz      short loc_180016810
0x1800167a8  sub     ecx, 2
0x1800167ab  jz      short loc_180016810
0x1800167ad  sub     ecx, 1
0x1800167b0  jz      short loc_180016810
0x1800167b2  sub     ecx, 1
0x1800167b5  jz      short loc_180016810
0x1800167b7  sub     ecx, 1
0x1800167ba  jz      short loc_180016810
0x1800167bc  sub     ecx, 1
0x1800167bf  jz      short loc_180016810
0x1800167c1  sub     ecx, 1
0x1800167c4  jz      short loc_180016810
0x1800167c6  cmp     ecx, 1
0x1800167c9  jnz     short loc_180016806
0x1800167cb  mov     rcx, [rsi+8]; bstr
0x1800167cf  test    rcx, rcx
0x1800167d2  jz      short loc_1800167DD
0x1800167d4  call    cs:__imp_SysStringByteLen
0x1800167da  mov     r14d, eax
0x1800167dd  lea     ebp, [r14+18h]
0x1800167e1  jmp     short loc_180016815
0x1800167e3  sub     ecx, 0Bh
0x1800167e6  jz      short loc_180016810
0x1800167e8  sub     ecx, 5
0x1800167eb  jz      short loc_180016810
0x1800167ed  sub     ecx, 1
0x1800167f0  jz      short loc_180016810
0x1800167f2  sub     ecx, 1
0x1800167f5  jz      short loc_180016810
0x1800167f7  sub     ecx, 1
0x1800167fa  jz      short loc_180016810
0x1800167fc  sub     ecx, 3
0x1800167ff  jz      short loc_180016810
0x180016801  cmp     ecx, 1
0x180016804  jz      short loc_180016810
0x180016806  mov     ebx, 80004001h
0x18001680b  jmp     loc_1800168F9
0x180016810  mov     ebp, 14h
0x180016815  mov     ecx, ebp; dwBytes
0x180016817  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001681c  mov     rdi, rax
0x18001681f  test    rax, rax
0x180016822  jz      loc_1800168EF
0x180016828  mov     dword ptr [rax], 4B434F4Dh
0x18001682e  movzx   edx, word ptr [rsi]
0x180016831  cmp     edx, 0Ah
0x180016834  ja      short loc_180016884
0x180016836  jz      short loc_1800168A7
0x180016838  sub     edx, 2
0x18001683b  jz      short loc_1800168A7
0x18001683d  sub     edx, 1
0x180016840  jz      short loc_1800168A7
0x180016842  sub     edx, 1
0x180016845  jz      short loc_1800168A7
0x180016847  sub     edx, 1
0x18001684a  jz      short loc_1800168A7
0x18001684c  sub     edx, 1
0x18001684f  jz      short loc_1800168A7
0x180016851  sub     edx, 1
0x180016854  jz      short loc_1800168A7
0x180016856  cmp     edx, 1
0x180016859  jnz     short loc_1800168BE
0x18001685b  lea     eax, [rdx+0Fh]
0x18001685e  mov     r8, rsi; Source
0x180016861  mov     r9d, eax; SourceSize
0x180016864  lea     rcx, [rdi+4]; Destination
0x180016868  mov     edx, eax; DestinationSize
0x18001686a  call    cs:__imp_memcpy_s
0x180016870  mov     [rdi+14h], r14d
0x180016874  lea     rcx, [rdi+18h]
0x180016878  mov     r8, [rsi+8]
0x18001687c  mov     edx, r14d
0x18001687f  mov     r9d, r14d
0x180016882  jmp     short loc_1800168B8
0x180016884  sub     edx, 0Bh
0x180016887  jz      short loc_1800168A7
0x180016889  sub     edx, 5
0x18001688c  jz      short loc_1800168A7
0x18001688e  sub     edx, 1
0x180016891  jz      short loc_1800168A7
0x180016893  sub     edx, 1
0x180016896  jz      short loc_1800168A7
0x180016898  sub     edx, 1
0x18001689b  jz      short loc_1800168A7
0x18001689d  sub     edx, 3
0x1800168a0  jz      short loc_1800168A7
0x1800168a2  cmp     edx, 1
0x1800168a5  jnz     short loc_1800168BE
0x1800168a7  lea     rcx, [rax+4]; Destination
0x1800168ab  mov     r8, rsi; Source
0x1800168ae  mov     eax, 10h
0x1800168b3  mov     r9d, eax; SourceSize
0x1800168b6  mov     edx, eax; DestinationSize
0x1800168b8  call    cs:__imp_memcpy_s
0x1800168be  mov     r8, [r13+r15*8+0]; unsigned __int16 *
0x1800168c3  mov     r9, rdi; unsigned __int8 *
0x1800168c6  mov     rdx, [rsp+78h+hKey]; HKEY
0x1800168cb  mov     rcx, [rsp+78h+arg_0]; this
0x1800168d3  mov     dword ptr [rsp+78h+lpData], ebp; unsigned int
0x1800168d7  call    ?Write@CSubscriptionItem@@QEAAJPEAUHKEY__@@PEBGPEBEK@Z; CSubscriptionItem::Write(HKEY__ *,ushort const *,uchar const *,ulong)
0x1800168dc  mov     rcx, rdi; lpMem
0x1800168df  mov     ebx, eax
0x1800168e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800168e6  mov     edi, [rsp+78h+arg_8]
0x1800168ed  jmp     short loc_1800168F9
0x1800168ef  mov     ebx, 8007000Eh
0x1800168f4  jmp     short loc_1800168E6
0x1800168f6  mov     ebx, r12d
0x1800168f9  mov     eax, [rsp+78h+var_48]
0x1800168fd  mov     ebp, 0
0x180016902  mov     rsi, [rsp+78h+arg_18]
0x18001690a  inc     eax
0x18001690c  mov     [rsp+78h+var_48], eax
0x180016910  lea     r14d, [rbp+8]
0x180016914  cmp     eax, edi
0x180016916  jb      loc_1800166E0
0x18001691c  mov     rcx, [rsp+78h+hKey]; hKey
0x180016921  call    cs:__imp_RegCloseKey
0x180016927  jmp     short loc_18001692E
0x180016929  mov     ebx, 80004005h
0x18001692e  mov     eax, ebx
0x180016930  jmp     short loc_180016937
0x180016932  mov     eax, 80070057h
0x180016937  mov     rbx, [rsp+78h+arg_10]
0x18001693f  add     rsp, 40h
0x180016943  pop     r15
0x180016945  pop     r14
0x180016947  pop     r13
0x180016949  pop     r12
0x18001694b  pop     rdi
0x18001694c  pop     rsi
0x18001694d  pop     rbp
0x18001694e  retn
```
