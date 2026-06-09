# ParseXmlPossibleValues(ushort *,POSSIBLE_VALUE * *,ulong *)

- ea: `0x18008cdcc`
- end: `0x18008d662`
- name: `?ParseXmlPossibleValues@@YAJPEAGPEAPEAUPOSSIBLE_VALUE@@PEAK@Z`
- size: `2198`
- prototype: `__int64 __fastcall(BYTE *pInit, struct POSSIBLE_VALUE **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015334`

## callees

- `0x18007e5ac`
- `0x18008cdcc`
- `0x1800b0796`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18008d5e0`
- `KERNEL32!LocalFree` at `0x18008d5eb`
- `KERNEL32!LocalFree` at `0x18008d5f6`
- `KERNEL32!LocalFree` at `0x18008d601`
- `KERNEL32!LocalFree` at `0x18008d615`
- `KERNEL32!LocalFree` at `0x18008d5e0`
- `KERNEL32!LocalFree` at `0x18008d5eb`
- `KERNEL32!LocalFree` at `0x18008d5f6`
- `KERNEL32!LocalFree` at `0x18008d601`
- `KERNEL32!LocalFree` at `0x18008d615`
- `KERNEL32!LocalAlloc` at `0x18008d381`
- `KERNEL32!LocalAlloc` at `0x18008d423`
- `KERNEL32!LocalAlloc` at `0x18008d473`
- `KERNEL32!LocalAlloc` at `0x18008d49e`
- `KERNEL32!LocalAlloc` at `0x18008d4d0`
- `KERNEL32!LocalAlloc` at `0x18008d381`
- `KERNEL32!LocalAlloc` at `0x18008d423`
- `KERNEL32!LocalAlloc` at `0x18008d473`
- `KERNEL32!LocalAlloc` at `0x18008d49e`
- `KERNEL32!LocalAlloc` at `0x18008d4d0`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008ce5a`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008d34a`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008ce5a`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18008d34a`
- `XmlLite!CreateXmlReader` at `0x18008ce85`
- `XmlLite!CreateXmlReader` at `0x18008ce85`

## string_xrefs

- `0x18008cf4b`: `http://schemas.microsoft.com/2010/08/ActiveDirectory/PossibleValues`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ParseXmlPossibleValues(BYTE *pInit, HLOCAL **a2, unsigned int *a3)
{
  unsigned int v4; // r12d
  IStream *v5; // rbx
  unsigned int v6; // edi
  HRESULT v7; // r14d
  __int64 v8; // rax
  unsigned int v9; // r15d
  int v10; // esi
  wchar_t *v11; // rdi
  wchar_t *v12; // rax
  int v13; // ecx
  int v14; // edx
  bool v15; // zf
  signed __int64 v16; // rdx
  int v17; // eax
  int v18; // ecx
  wchar_t *v19; // rdi
  int v20; // esi
  unsigned int v21; // edi
  int v22; // eax
  int v23; // ecx
  wchar_t *v24; // rdi
  IStream *v25; // rdi
  HLOCAL *v26; // rsi
  unsigned int v27; // r15d
  int v28; // edi
  SIZE_T v29; // r14
  unsigned __int16 *v30; // rax
  unsigned int v31; // r14d
  unsigned __int16 *v32; // rax
  wchar_t *v33; // rdi
  int v34; // eax
  __int64 v35; // r15
  unsigned int v37; // [rsp+20h] [rbp-50h]
  void *ppvObject; // [rsp+28h] [rbp-48h] BYREF
  int v39; // [rsp+30h] [rbp-40h]
  int v40; // [rsp+34h] [rbp-3Ch] BYREF
  wchar_t *v41; // [rsp+38h] [rbp-38h] BYREF
  int v42; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v43; // [rsp+48h] [rbp-28h] BYREF
  UINT cbInit; // [rsp+50h] [rbp-20h]
  wchar_t *v45; // [rsp+58h] [rbp-18h]
  wchar_t *String1; // [rsp+60h] [rbp-10h] BYREF
  IStream *v47; // [rsp+68h] [rbp-8h]
  char v50; // [rsp+C8h] [rbp+58h]

  v4 = 0;
  v5 = 0;
  v47 = 0;
  ppvObject = 0;
  v42 = 0;
  String1 = 0;
  v41 = 0;
  v43 = 0;
  v6 = 0;
  v37 = 0;
  v40 = 0;
  if ( !a2 || !a3 )
  {
    v26 = 0;
    v7 = -2147024809;
LABEL_131:
    if ( v26 )
    {
      if ( v6 )
      {
        v35 = 0;
        do
        {
          LocalFree(v26[4 * v35]);
          LocalFree(v26[4 * v35 + 1]);
          LocalFree(v26[4 * v35 + 2]);
          LocalFree(v26[4 * v35 + 3]);
          ++v4;
          ++v35;
        }
        while ( v4 < v37 );
      }
      LocalFree(v26);
    }
    goto LABEL_136;
  }
  v7 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( !pInit )
    goto LABEL_136;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&pInit[2 * v8] );
  cbInit = 2 * v8 + 2;
  v5 = SHCreateMemStream(pInit, cbInit);
  v47 = v5;
  if ( !v5 )
    goto LABEL_7;
  v7 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
    if ( v7 >= 0 )
    {
      v45 = 0;
      v9 = 1;
      v39 = 0;
      v50 = 0;
      v7 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v5);
      if ( v7 >= 0 )
      {
        while ( !(*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v42) )
        {
          v7 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                 ppvObject,
                 &v41,
                 0);
          if ( v7 < 0 )
            goto LABEL_136;
          v7 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 104LL))(
                 ppvObject,
                 &String1,
                 0);
          if ( v7 < 0 )
            goto LABEL_136;
          v10 = wcscmp_0(String1, L"http://schemas.microsoft.com/2010/08/ActiveDirectory/PossibleValues");
          switch ( v42 )
          {
            case 1:
              if ( v50 )
                goto LABEL_27;
              if ( v9 == 1 )
              {
                if ( wcscmp_0(v41, L"PossibleClaimValues") )
                  goto LABEL_27;
                v9 = 2;
              }
              else
              {
                if ( v9 == 2 )
                {
                  if ( v10 )
                    goto LABEL_27;
                  v19 = v41;
                  if ( wcscmp_0(v41, L"IntegerList") )
                  {
                    if ( wcscmp_0(v19, L"UnsignedIntegerList") && wcscmp_0(v19, L"StringList") )
                      goto LABEL_27;
                  }
                  if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
                    goto LABEL_49;
                  v9 = 6;
                  v45 = v41;
                  v41 = 0;
                  goto LABEL_77;
                }
                if ( (v9 & 4) != 0 )
                {
                  if ( wcscmp_0(v41, L"Item") )
                    goto LABEL_27;
                  v9 = 248;
                }
                else
                {
                  if ( (v9 & 0x80u) == 0 )
                    goto LABEL_27;
                  if ( v10 )
                  {
                    if ( (v9 & 0x40) == 0 )
                      goto LABEL_27;
                    v20 = v39;
                    v21 = v9 & 0xFFFFFFC7;
                    v4 = 64;
                    v22 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 160LL))(
                            ppvObject,
                            (unsigned int)(v42 - 1));
                    v9 = v9 & 0xFFFFFEC7 | 0x100;
                    if ( v22 )
                      v9 = v21;
                    v23 = v20 + 1;
                    if ( v22 )
                      v23 = v20;
                    v39 = v23;
                    goto LABEL_77;
                  }
                  if ( (v9 & 0x100) != 0 )
                    goto LABEL_27;
                  v24 = v41;
                  if ( !wcscmp_0(v41, L"ValueGUID") )
                  {
                    if ( (v9 & 8) == 0 )
                      goto LABEL_27;
                    v9 &= ~8u;
                    v4 = 8;
                  }
                  else if ( !wcscmp_0(v24, L"ValueDisplayName") )
                  {
                    if ( (v9 & 0x10) == 0 )
                      goto LABEL_27;
                    v9 &= 0xFFFFFFE7;
                    v4 = 16;
                  }
                  else if ( !wcscmp_0(v24, L"ValueDescription") )
                  {
                    if ( (v9 & 0x20) == 0 )
                      goto LABEL_27;
                    v9 &= 0xFFFFFFC7;
                    v4 = 32;
                  }
                  else
                  {
                    if ( wcscmp_0(v24, L"Value")
                      || v39
                      || (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
                    {
                      goto LABEL_27;
                    }
                    v9 = 4;
                    v4 = 128;
                  }
                  v6 = v37;
                  if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
                    v9 |= 0x100u;
                }
              }
              break;
            case 3:
              if ( (v9 & 0x100) == 0 )
                goto LABEL_27;
              v9 &= ~0x100u;
              break;
            case 15:
              if ( v50 )
                goto LABEL_27;
              if ( v9 == 1 )
              {
                if ( wcscmp_0(v41, L"PossibleClaimValues") )
                  goto LABEL_27;
                v50 = 1;
              }
              else
              {
                v11 = v41;
                if ( v45 )
                {
                  v12 = v41;
                  do
                  {
                    v13 = *(wchar_t *)((char *)v12 + (char *)v45 - (char *)v41);
                    v14 = *v12 - v13;
                    if ( v14 )
                      break;
                    ++v12;
                  }
                  while ( v13 );
                  if ( !v14 )
                  {
                    if ( (v9 & 2) == 0 )
                      goto LABEL_27;
LABEL_49:
                    v9 = 1;
                    goto LABEL_77;
                  }
                }
                if ( !wcscmp_0(v41, L"Item") )
                {
                  if ( v9 != 4 || v4 != 128 )
                    goto LABEL_27;
                  v9 = 6;
                  v6 = ++v37;
                }
                else
                {
                  if ( !wcscmp_0(v11, L"ValueGUID") )
                  {
                    v15 = v4 == 8;
LABEL_38:
                    if ( !v15 )
                      goto LABEL_27;
                    v9 &= ~0x100u;
                    goto LABEL_77;
                  }
                  if ( !wcscmp_0(v11, L"ValueDisplayName") )
                  {
                    v15 = v4 == 16;
                    goto LABEL_38;
                  }
                  if ( !wcscmp_0(v11, L"ValueDescription") )
                  {
                    v15 = v4 == 32;
                    goto LABEL_38;
                  }
                  if ( !wcscmp_0(v11, L"Value") )
                  {
                    if ( (v9 & 0x100) != 0 || v4 != 128 )
                      goto LABEL_27;
                  }
                  else
                  {
                    if ( !v10 )
                      goto LABEL_27;
                    v16 = (char *)v45 - (char *)v11;
                    do
                    {
                      v17 = *(wchar_t *)((char *)v11 + v16);
                      v18 = *v11 - v17;
                      if ( v18 )
                        break;
                      ++v11;
                    }
                    while ( v17 );
                    if ( !v18 )
                      goto LABEL_49;
                    if ( v4 != 64 || !v39 )
                      goto LABEL_27;
                    --v39;
                  }
LABEL_77:
                  v6 = v37;
                }
              }
              break;
          }
        }
        v4 = 0;
        if ( !v50 )
        {
LABEL_27:
          v7 = -2147024809;
          goto LABEL_136;
        }
        if ( !v6 )
          goto LABEL_136;
        v25 = SHCreateMemStream(pInit, cbInit);
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v5 + 16LL))(v5);
        v5 = v25;
        v47 = v25;
        if ( !v25 || (v26 = (HLOCAL *)LocalAlloc(0x40u, 32 * v37)) == 0 )
        {
LABEL_7:
          v7 = -2147024882;
          goto LABEL_136;
        }
        v7 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v25);
        if ( v7 >= 0 )
        {
          v27 = 0;
          v28 = 64;
          while ( 1 )
          {
            do
            {
              while ( 1 )
              {
                if ( (*(unsigned int (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v42) )
                {
                  *a2 = v26;
                  *a3 = v37;
                  goto LABEL_136;
                }
                if ( v42 != 1 )
                  break;
                v7 = (*(__int64 (__fastcall **)(void *, wchar_t **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                       ppvObject,
                       &v41,
                       0);
                if ( v7 < 0 )
                  goto LABEL_128;
                v33 = v41;
                if ( !wcscmp_0(v41, L"ValueGUID") )
                {
                  v28 = 8;
                }
                else if ( !wcscmp_0(v33, L"ValueDisplayName") )
                {
                  v28 = 16;
                }
                else if ( !wcscmp_0(v33, L"ValueDescription") )
                {
                  v28 = 32;
                }
                else
                {
                  v34 = wcscmp_0(v33, L"Value");
                  v28 = 64;
                  if ( !v34 )
                    v28 = 128;
                }
              }
            }
            while ( v42 != 3 );
            v7 = (*(__int64 (__fastcall **)(void *, unsigned __int16 **, int *))(*(_QWORD *)ppvObject + 128LL))(
                   ppvObject,
                   &v43,
                   &v40);
            if ( v7 < 0 )
              goto LABEL_128;
            if ( v28 == 8 )
            {
              v29 = (unsigned int)(2 * v40 + 2);
              v30 = (unsigned __int16 *)LocalAlloc(0x40u, v29);
              v26[4 * v27] = v30;
              goto LABEL_106;
            }
            if ( v28 == 16 )
              break;
            if ( v28 == 32 )
            {
              v29 = (unsigned int)(2 * v40 + 2);
              v30 = (unsigned __int16 *)LocalAlloc(0x40u, v29);
              v26[4 * v27 + 2] = v30;
LABEL_106:
              if ( !v30 )
                goto LABEL_127;
              v7 = StringCbCopyW(v30, v29, v43);
              if ( v7 < 0 )
                goto LABEL_128;
            }
            else if ( v28 == 128 )
            {
              v31 = 2 * v40 + 2;
              v32 = (unsigned __int16 *)LocalAlloc(0x40u, v31);
              v26[4 * v27 + 3] = v32;
              if ( !v32 )
              {
LABEL_127:
                v7 = -2147024882;
                goto LABEL_128;
              }
              v7 = StringCbCopyW(v32, v31, v43);
              if ( v7 < 0 )
                goto LABEL_128;
              ++v27;
            }
          }
          v29 = (unsigned int)(2 * v40 + 2);
          v30 = (unsigned __int16 *)LocalAlloc(0x40u, v29);
          v26[4 * v27 + 1] = v30;
          goto LABEL_106;
        }
LABEL_128:
        v6 = v37;
        goto LABEL_131;
      }
    }
  }
LABEL_136:
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( v5 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18008cdcc  mov     [rsp-38h+arg_0], rbx
0x18008cdd1  mov     [rsp-38h+arg_10], r8
0x18008cdd6  mov     [rsp-38h+arg_8], rdx
0x18008cddb  push    rbp
0x18008cddc  push    rsi
0x18008cddd  push    rdi
0x18008cdde  push    r12
0x18008cde0  push    r13
0x18008cde2  push    r14
0x18008cde4  push    r15
0x18008cde6  mov     rbp, rsp
0x18008cde9  sub     rsp, 70h
0x18008cded  mov     rax, r8
0x18008cdf0  mov     r13, rcx
0x18008cdf3  xor     r12d, r12d
0x18008cdf6  mov     ebx, r12d
0x18008cdf9  mov     [rbp+var_8], rbx
0x18008cdfd  mov     [rbp+ppvObject], r12
0x18008ce01  mov     [rbp+var_30], r12d
0x18008ce05  mov     [rbp+String1], r12
0x18008ce09  mov     [rbp+var_38], r12
0x18008ce0d  mov     [rbp+var_28], r12
0x18008ce11  mov     edi, r12d
0x18008ce14  mov     [rbp+var_50], r12d
0x18008ce18  mov     [rbp+var_3C], r12d
0x18008ce1c  test    rdx, rdx
0x18008ce1f  jz      loc_18008D5BC
0x18008ce25  test    rax, rax
0x18008ce28  jz      loc_18008D5BC
0x18008ce2e  mov     r14d, r12d
0x18008ce31  mov     [rdx], r12
0x18008ce34  mov     [r8], r12d
0x18008ce37  test    rcx, rcx
0x18008ce3a  jz      loc_18008D61C
0x18008ce40  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ce44  inc     rax
0x18008ce47  cmp     [rcx+rax*2], r12w
0x18008ce4c  jnz     short loc_18008CE44
0x18008ce4e  lea     eax, ds:2[rax*2]
0x18008ce55  mov     [rbp+cbInit], eax
0x18008ce58  mov     edx, eax; cbInit
0x18008ce5a  call    cs:__imp_SHCreateMemStream
0x18008ce60  mov     rbx, rax
0x18008ce63  mov     [rbp+var_8], rax
0x18008ce67  test    rax, rax
0x18008ce6a  jnz     short loc_18008CE77
0x18008ce6c  mov     r14d, 8007000Eh
0x18008ce72  jmp     loc_18008D61C
0x18008ce77  xor     r8d, r8d; pMalloc
0x18008ce7a  lea     rdx, [rbp+ppvObject]; ppvObject
0x18008ce7e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18008ce85  call    cs:__imp_CreateXmlReader
0x18008ce8b  mov     r14d, eax
0x18008ce8e  test    eax, eax
0x18008ce90  js      loc_18008D61C
0x18008ce96  mov     rcx, [rbp+ppvObject]
0x18008ce9a  mov     rax, [rcx]
0x18008ce9d  xor     r8d, r8d
0x18008cea0  lea     edx, [r8+4]
0x18008cea4  mov     rax, [rax+28h]
0x18008cea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cead  mov     r14d, eax
0x18008ceb0  test    eax, eax
0x18008ceb2  js      loc_18008D61C
0x18008ceb8  mov     [rbp+var_18], r12
0x18008cebc  mov     r15d, 1
0x18008cec2  mov     [rbp+var_40], 0
0x18008cec9  mov     [rbp+arg_18], 0
0x18008cecd  mov     rcx, [rbp+ppvObject]
0x18008ced1  mov     rax, [rcx]
0x18008ced4  mov     rdx, rbx
0x18008ced7  mov     rax, [rax+18h]
0x18008cedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cee0  mov     r14d, eax
0x18008cee3  test    eax, eax
0x18008cee5  js      loc_18008D61C
0x18008ceeb  mov     rcx, [rbp+ppvObject]
0x18008ceef  mov     rax, [rcx]
0x18008cef2  lea     rdx, [rbp+var_30]
0x18008cef6  mov     rax, [rax+30h]
0x18008cefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ceff  test    eax, eax
0x18008cf01  jnz     loc_18008D32E
0x18008cf07  mov     rcx, [rbp+ppvObject]
0x18008cf0b  mov     rax, [rcx]
0x18008cf0e  xor     r8d, r8d
0x18008cf11  lea     rdx, [rbp+var_38]
0x18008cf15  mov     rax, [rax+70h]
0x18008cf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf1e  mov     r14d, eax
0x18008cf21  test    eax, eax
0x18008cf23  js      loc_18008D61C
0x18008cf29  mov     rcx, [rbp+ppvObject]
0x18008cf2d  mov     rax, [rcx]
0x18008cf30  xor     r8d, r8d
0x18008cf33  lea     rdx, [rbp+String1]
0x18008cf37  mov     rax, [rax+68h]
0x18008cf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf40  mov     r14d, eax
0x18008cf43  test    eax, eax
0x18008cf45  js      loc_18008D61C
0x18008cf4b  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/2010/08/Ac"...
0x18008cf52  mov     rcx, [rbp+String1]; String1
0x18008cf56  call    wcscmp_0
0x18008cf5b  mov     esi, eax
0x18008cf5d  mov     edx, [rbp+var_30]
0x18008cf60  sub     edx, 1
0x18008cf63  jz      loc_18008D108
0x18008cf69  sub     edx, 2
0x18008cf6c  jz      loc_18008D0F3
0x18008cf72  cmp     edx, 0Ch
0x18008cf75  jnz     loc_18008CEEB
0x18008cf7b  cmp     [rbp+arg_18], 0
0x18008cf7f  jnz     short loc_18008CFDC
0x18008cf81  cmp     r15d, 1
0x18008cf85  jnz     short loc_18008CFA4
0x18008cf87  lea     rdx, aPossibleclaimv; "PossibleClaimValues"
0x18008cf8e  mov     rcx, [rbp+var_38]; String1
0x18008cf92  call    wcscmp_0
0x18008cf97  test    eax, eax
0x18008cf99  jnz     short loc_18008CFDC
0x18008cf9b  mov     [rbp+arg_18], r15b
0x18008cf9f  jmp     loc_18008CEEB
0x18008cfa4  mov     rdi, [rbp+var_38]
0x18008cfa8  mov     rcx, [rbp+var_18]
0x18008cfac  test    rcx, rcx
0x18008cfaf  jz      short loc_18008CFE7
0x18008cfb1  mov     rax, rdi
0x18008cfb4  mov     r8, rcx
0x18008cfb7  sub     r8, rdi
0x18008cfba  movzx   edx, word ptr [rax]
0x18008cfbd  movzx   ecx, word ptr [rax+r8]
0x18008cfc2  sub     edx, ecx
0x18008cfc4  jnz     short loc_18008CFCE
0x18008cfc6  add     rax, 2
0x18008cfca  test    ecx, ecx
0x18008cfcc  jnz     short loc_18008CFBA
0x18008cfce  test    edx, edx
0x18008cfd0  jnz     short loc_18008CFE7
0x18008cfd2  test    r15b, 2
0x18008cfd6  jnz     loc_18008D0C9
0x18008cfdc  mov     r14d, 80070057h
0x18008cfe2  jmp     loc_18008D61C
0x18008cfe7  lea     rdx, aItem; "Item"
0x18008cfee  mov     rcx, rdi; String1
0x18008cff1  call    wcscmp_0
0x18008cff6  test    eax, eax
0x18008cff8  jnz     short loc_18008D01A
0x18008cffa  cmp     r15d, 4
0x18008cffe  jnz     short loc_18008CFDC
0x18008d000  cmp     r12d, 80h
0x18008d007  jnz     short loc_18008CFDC
0x18008d009  lea     r15d, [rax+6]
0x18008d00d  mov     edi, [rbp+var_50]
0x18008d010  inc     edi
0x18008d012  mov     [rbp+var_50], edi
0x18008d015  jmp     loc_18008CEEB
0x18008d01a  lea     rdx, aValueguid; "ValueGUID"
0x18008d021  mov     rcx, rdi; String1
0x18008d024  call    wcscmp_0
0x18008d029  test    eax, eax
0x18008d02b  jnz     short loc_18008D033
0x18008d02d  cmp     r12d, 8
0x18008d031  jmp     short loc_18008D063
0x18008d033  lea     rdx, aValuedisplayna_0; "ValueDisplayName"
0x18008d03a  mov     rcx, rdi; String1
0x18008d03d  call    wcscmp_0
0x18008d042  test    eax, eax
0x18008d044  jnz     short loc_18008D04C
0x18008d046  cmp     r12d, 10h
0x18008d04a  jmp     short loc_18008D063
0x18008d04c  lea     rdx, aValuedescripti; "ValueDescription"
0x18008d053  mov     rcx, rdi; String1
0x18008d056  call    wcscmp_0
0x18008d05b  test    eax, eax
0x18008d05d  jnz     short loc_18008D073
0x18008d05f  cmp     r12d, 20h ; ' '
0x18008d063  jnz     loc_18008CFDC
0x18008d069  btr     r15d, 8
0x18008d06e  jmp     loc_18008D233
0x18008d073  lea     rdx, aValue; "Value"
0x18008d07a  mov     rcx, rdi; String1
0x18008d07d  call    wcscmp_0
0x18008d082  test    eax, eax
0x18008d084  jnz     short loc_18008D0A3
0x18008d086  bt      r15d, 8
0x18008d08b  jb      loc_18008CFDC
0x18008d091  cmp     r12d, 80h
0x18008d098  jnz     loc_18008CFDC
0x18008d09e  jmp     loc_18008D233
0x18008d0a3  test    esi, esi
0x18008d0a5  jz      loc_18008CFDC
0x18008d0ab  mov     rdx, [rbp+var_18]
0x18008d0af  sub     rdx, rdi
0x18008d0b2  movzx   ecx, word ptr [rdi]
0x18008d0b5  movzx   eax, word ptr [rdi+rdx]
0x18008d0b9  sub     ecx, eax
0x18008d0bb  jnz     short loc_18008D0C5
0x18008d0bd  add     rdi, 2
0x18008d0c1  test    eax, eax
0x18008d0c3  jnz     short loc_18008D0B2
0x18008d0c5  test    ecx, ecx
0x18008d0c7  jnz     short loc_18008D0D4
0x18008d0c9  mov     r15d, 1
0x18008d0cf  jmp     loc_18008D233
0x18008d0d4  cmp     r12d, 40h ; '@'
0x18008d0d8  jnz     loc_18008CFDC
0x18008d0de  mov     esi, [rbp+var_40]
0x18008d0e1  test    esi, esi
0x18008d0e3  jz      loc_18008CFDC
0x18008d0e9  dec     esi
0x18008d0eb  mov     [rbp+var_40], esi
0x18008d0ee  jmp     loc_18008D233
0x18008d0f3  bt      r15d, 8
0x18008d0f8  jnb     loc_18008CFDC
0x18008d0fe  btr     r15d, 8
0x18008d103  jmp     loc_18008CEEB
0x18008d108  cmp     [rbp+arg_18], 0
0x18008d10c  jnz     loc_18008CFDC
0x18008d112  cmp     r15d, 1
0x18008d116  jnz     short loc_18008D139
0x18008d118  lea     rdx, aPossibleclaimv; "PossibleClaimValues"
0x18008d11f  mov     rcx, [rbp+var_38]; String1
0x18008d123  call    wcscmp_0
0x18008d128  test    eax, eax
0x18008d12a  jnz     loc_18008CFDC
0x18008d130  lea     r15d, [rax+2]
0x18008d134  jmp     loc_18008CEEB
0x18008d139  cmp     r15d, 2
0x18008d13d  jnz     short loc_18008D1B9
0x18008d13f  test    esi, esi
0x18008d141  jnz     loc_18008CFDC
0x18008d147  lea     rdx, aIntegerlist; "IntegerList"
0x18008d14e  mov     rdi, [rbp+var_38]
0x18008d152  mov     rcx, rdi; String1
0x18008d155  call    wcscmp_0
0x18008d15a  test    eax, eax
0x18008d15c  jz      short loc_18008D188
0x18008d15e  lea     rdx, aUnsignedintege; "UnsignedIntegerList"
0x18008d165  mov     rcx, rdi; String1
0x18008d168  call    wcscmp_0
0x18008d16d  test    eax, eax
0x18008d16f  jz      short loc_18008D188
0x18008d171  lea     rdx, aStringlist; "StringList"
0x18008d178  mov     rcx, rdi; String1
0x18008d17b  call    wcscmp_0
0x18008d180  test    eax, eax
0x18008d182  jnz     loc_18008CFDC
0x18008d188  mov     rcx, [rbp+ppvObject]
0x18008d18c  mov     rax, [rcx]
0x18008d18f  mov     rax, [rax+0A0h]
0x18008d196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d19b  test    eax, eax
0x18008d19d  jnz     loc_18008D0C9
0x18008d1a3  lea     r15d, [rax+6]
0x18008d1a7  mov     rax, [rbp+var_38]
0x18008d1ab  mov     [rbp+var_18], rax
0x18008d1af  mov     [rbp+var_38], 0
0x18008d1b7  jmp     short loc_18008D233
0x18008d1b9  test    r15b, 4
0x18008d1bd  jz      short loc_18008D1E2
0x18008d1bf  lea     rdx, aItem; "Item"
0x18008d1c6  mov     rcx, [rbp+var_38]; String1
0x18008d1ca  call    wcscmp_0
0x18008d1cf  test    eax, eax
0x18008d1d1  jnz     loc_18008CFDC
0x18008d1d7  mov     r15d, 0F8h
0x18008d1dd  jmp     loc_18008CEEB
0x18008d1e2  test    r15b, r15b
0x18008d1e5  jns     loc_18008CFDC
0x18008d1eb  xor     r12d, r12d
0x18008d1ee  test    esi, esi
0x18008d1f0  jz      short loc_18008D23B
0x18008d1f2  test    r15b, 40h
0x18008d1f6  jz      loc_18008CFDC
0x18008d1fc  mov     esi, [rbp+var_40]
0x18008d1ff  and     r15d, 0FFFFFFC7h
0x18008d203  mov     edi, r15d
0x18008d206  mov     r12d, 40h ; '@'
0x18008d20c  mov     rcx, [rbp+ppvObject]
0x18008d210  mov     rax, [rcx]
0x18008d213  mov     rax, [rax+0A0h]
0x18008d21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d21f  bts     r15d, 8
0x18008d224  test    eax, eax
0x18008d226  cmovnz  r15d, edi
0x18008d22a  lea     ecx, [rsi+1]
0x18008d22d  cmovnz  ecx, esi
0x18008d230  mov     [rbp+var_40], ecx
0x18008d233  mov     edi, [rbp+var_50]
0x18008d236  jmp     loc_18008CEEB
0x18008d23b  bt      r15d, 8
0x18008d240  jb      loc_18008CFDC
0x18008d246  lea     rdx, aValueguid; "ValueGUID"
0x18008d24d  mov     rdi, [rbp+var_38]
0x18008d251  mov     rcx, rdi; String1
0x18008d254  call    wcscmp_0
0x18008d259  test    eax, eax
0x18008d25b  jnz     short loc_18008D274
0x18008d25d  test    r15b, 8
  ... truncated ...
```
