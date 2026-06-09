# GetOperandValue

- ea: `0x1800092d0`
- end: `0x18000996a`
- name: `GetOperandValue`
- size: `1690`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008740`
- `0x1800092d0`

## callees

- `0x180006540`
- `0x1800092d0`
- `0x180009970`
- `0x180009bf0`
- `0x180009c40`
- `0x180017128`
- `0x180021d84`
- `0x18002210c`
- `0x180022190`
- `0x18002220c`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_errno` at `0x180009794`
- `api-ms-win-core-crt-l1-1-0!_errno` at `0x1800097da`
- `api-ms-win-core-crt-l1-1-0!_errno` at `0x1800097f5`
- `api-ms-win-core-crt-l1-1-0!_errno` at `0x180009794`
- `api-ms-win-core-crt-l1-1-0!_errno` at `0x1800097da`
- `api-ms-win-core-crt-l1-1-0!_errno` at `0x1800097f5`
- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x1800097a6`
- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x180009828`
- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x1800097a6`
- `api-ms-win-core-crt-l1-1-0!_wcstoui64` at `0x180009828`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009362`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800095c6`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180009362`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800095c6`
- `ntdll!RtlLengthSid` at `0x18000969b`
- `ntdll!RtlLengthSid` at `0x18000969b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009332`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800094ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009701`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009332`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800094ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009701`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800098b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009957`

## pseudocode

```c
__int64 __fastcall GetOperandValue(
        wchar_t *a1,
        char a2,
        char a3,
        HLOCAL *a4,
        unsigned int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9)
{
  unsigned int *v10; // rsi
  PSID v14; // rdi
  HLOCAL v15; // rax
  unsigned int AttributeName; // ebx
  _BYTE *v17; // rax
  char v18; // r13
  unsigned int i; // ecx
  _DWORD *v20; // rbx
  char v21; // al
  __int64 v22; // rcx
  _DWORD *v23; // rdx
  unsigned int v24; // r10d
  unsigned int v25; // r9d
  unsigned int v26; // r13d
  __int64 v27; // r8
  char v28; // r10
  __int64 v29; // rcx
  wchar_t v30; // dx
  __int64 v31; // rdi
  PSID v32; // rsi
  PSID v33; // rcx
  _DWORD *v34; // rdi
  ULONG v35; // eax
  bool v36; // zf
  unsigned int v37; // r13d
  __int64 v38; // r12
  int j; // esi
  __int64 v40; // r12
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rsi
  wchar_t v43; // ax
  unsigned __int64 v44; // rax
  __int16 v45; // r12
  char v46; // r15
  unsigned __int64 *v47; // rcx
  char v49; // [rsp+58h] [rbp-21h] BYREF
  char v50[3]; // [rsp+59h] [rbp-20h] BYREF
  unsigned int v51; // [rsp+5Ch] [rbp-1Dh] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  PSID Sid; // [rsp+68h] [rbp-11h] BYREF
  wchar_t *EndPtr; // [rsp+70h] [rbp-9h] BYREF
  __int64 v55; // [rsp+78h] [rbp-1h] BYREF
  char v56; // [rsp+D0h] [rbp+57h] BYREF

  v10 = a5;
  v51 = 0;
  v50[0] = 0;
  v49 = 0;
  v14 = 0;
  EndPtr = 0;
  Sid = 0;
  v56 = 0;
  hMem = 0;
  v55 = 0;
  *a5 = 0;
  v15 = LocalAlloc(0x40u, 0x10u);
  *a4 = v15;
  if ( !v15 )
  {
LABEL_2:
    AttributeName = 8;
    goto LABEL_89;
  }
  if ( a2 || !_wcsnicmp(a1, L"@", 1u) )
  {
    AttributeName = GetAttributeName(a1);
    if ( !AttributeName )
      goto LABEL_90;
    goto LABEL_89;
  }
  if ( *a1 == 34 )
  {
    AttributeName = GetStringOperandValue(a1, a4, v10);
    if ( !AttributeName )
      goto LABEL_90;
    goto LABEL_89;
  }
  AttributeName = 0;
  if ( *a1 == 123 )
  {
    v17 = *a4;
    v18 = 0;
    LOBYTE(a5) = 0;
    v17[1] = 80;
    v51 = 1;
    for ( i = 1; a1[i]; i = ++v51 )
    {
      AttributeName = GetNextNoneWhiteSpace(a1, &v51);
      if ( AttributeName )
        goto LABEL_89;
      if ( a1[v51] == 123 )
        goto LABEL_41;
      AttributeName = GetOperandValue(
                        (unsigned int)a1 + 2 * v51,
                        0,
                        0,
                        (unsigned int)&hMem,
                        (__int64)v10,
                        a6,
                        a7,
                        a8,
                        a9);
      if ( AttributeName )
        goto LABEL_89;
      v20 = hMem;
      if ( a3 )
      {
        if ( v18 && v18 != *((_BYTE *)hMem + 1) )
          goto LABEL_41;
        LOBYTE(a5) = *((_BYTE *)hMem + 1);
      }
      v21 = IsValueSizeFixed(*((unsigned __int8 *)hMem + 1));
      v23 = *a4;
      v50[0] = v21;
      v24 = 1;
      if ( !v21 )
        v24 = 5;
      if ( *((_QWORD *)v23 + 1) )
      {
        v25 = v23[1] + v20[1];
        if ( v25 < v23[1] || (v26 = v25 + v24, v25 + v24 < v25) )
        {
LABEL_35:
          AttributeName = 534;
          goto LABEL_89;
        }
        *((_QWORD *)v23 + 1) = SddlpReAlloc(v22, v26);
        if ( !*((_QWORD *)*a4 + 1) )
          goto LABEL_2;
      }
      else
      {
        v26 = v24 + v20[1];
        if ( v26 < v24 )
          goto LABEL_35;
        *((_QWORD *)*a4 + 1) = LocalAlloc(0x40u, v26);
      }
      v27 = *((_QWORD *)*a4 + 1);
      if ( !v27 )
        goto LABEL_2;
      v28 = v50[0];
      *(_BYTE *)(*((unsigned int *)*a4 + 1) + v27) = *((_BYTE *)hMem + 1);
      if ( !v28 )
        *(_DWORD *)(*((unsigned int *)*a4 + 1) + *((_QWORD *)*a4 + 1) + 1LL) = *((_DWORD *)hMem + 1);
      v29 = 1;
      if ( !v28 )
        v29 = 5;
      memcpy_0(
        (void *)(*((_QWORD *)*a4 + 1) + *((unsigned int *)*a4 + 1) + v29),
        *((const void **)hMem + 1),
        *((unsigned int *)hMem + 1));
      *((_DWORD *)*a4 + 1) = v26;
      FreeOperandValue(hMem);
      v51 += *v10;
      hMem = 0;
      AttributeName = GetNextNoneWhiteSpace(a1, &v51);
      if ( AttributeName )
        goto LABEL_89;
      v30 = a1[v51];
      if ( v30 != 44 )
      {
        if ( v30 != 125 )
          goto LABEL_41;
        *v10 = v51 + 1;
        break;
      }
      v18 = (char)a5;
    }
  }
  else
  {
    if ( !_wcsnicmp(a1, L"SID", 3u) )
    {
      v51 = 3;
      AttributeName = GetNextNoneWhiteSpace(a1, &v51);
      if ( !AttributeName )
      {
        if ( a1[v51] == 40 )
        {
          v31 = v51 + 1;
          AttributeName = LocalGetSidForString(
                            2 * (int)v31 + (int)a1,
                            (unsigned int)&Sid,
                            (unsigned int)&v55,
                            (unsigned int)&v56,
                            a6,
                            a7,
                            a8,
                            a9);
          if ( !AttributeName )
          {
            v51 = v31 + ((v55 - 2 * v31 - (__int64)a1) >> 1);
            AttributeName = GetNextNoneWhiteSpace(a1, &v51);
            if ( !AttributeName )
            {
              if ( a1[v51] == 41 )
              {
                *v10 = v51 + 1;
                v32 = Sid;
                v33 = Sid;
                *((_BYTE *)*a4 + 1) = 81;
                v34 = *a4;
                v35 = RtlLengthSid(v33);
                v36 = v56 == 0;
                v34[1] = v35;
                v14 = 0;
                *((_QWORD *)*a4 + 1) = v32;
                *(_BYTE *)*a4 = v36;
                goto LABEL_90;
              }
              AttributeName = 1336;
            }
          }
          v14 = Sid;
        }
        else
        {
LABEL_41:
          AttributeName = 1336;
        }
      }
      goto LABEL_89;
    }
    GetBinaryOperandLen(a1, &v51);
    if ( *a1 != 35 )
    {
      v40 = v51;
      if ( v51 )
      {
        *v10 = v51;
        *_errno() = 0;
        v41 = _wcstoui64(a1, &EndPtr, 0);
        v42 = v41;
        if ( EndPtr != a1 || v41 )
        {
          if ( EndPtr == &a1[v40] )
          {
            if ( *_errno() != 34 || v42 == -1 )
            {
              if ( *_errno() != 34 || v42 != -1 )
              {
                v43 = *a1;
                if ( *a1 == 45 )
                {
                  v44 = _wcstoui64(++a1, &EndPtr, 0);
                  if ( v44 >= v42 && v44 )
                  {
                    AttributeName = 1336;
                    goto LABEL_89;
                  }
                  v43 = *a1;
                  v45 = 2;
                }
                else if ( v43 == 43 )
                {
                  v43 = a1[1];
                  ++a1;
                  v45 = 1;
                }
                else
                {
                  v45 = 3;
                }
                if ( v43 == 48 )
                {
                  if ( a1 + 1 >= EndPtr || ((a1[1] - 88) & 0xFFDF) != 0 )
                    v46 = 1;
                  else
                    v46 = 3;
                }
                else
                {
                  v46 = 2;
                }
                *((_BYTE *)*a4 + 1) = 4;
                *((_DWORD *)*a4 + 1) = 10;
                *((_QWORD *)*a4 + 1) = LocalAlloc(0x40u, *((unsigned int *)*a4 + 1));
                v47 = (unsigned __int64 *)*((_QWORD *)*a4 + 1);
                if ( v47 )
                {
                  *v47 = v42;
                  *(_WORD *)(*((_QWORD *)*a4 + 1) + 8LL) = v45;
                  *(_BYTE *)(*((_QWORD *)*a4 + 1) + 9LL) = v46;
                  goto LABEL_90;
                }
                AttributeName = 8;
                goto LABEL_89;
              }
              AttributeName = 1336;
            }
            else
            {
              AttributeName = 1336;
            }
          }
          else
          {
            AttributeName = 1336;
          }
        }
        else
        {
          AttributeName = 1336;
        }
      }
      else
      {
        AttributeName = 1336;
      }
LABEL_89:
      FreeOperandValue(*a4);
      *a4 = 0;
      goto LABEL_90;
    }
    v37 = v51;
    if ( v51 < 2 )
    {
      AttributeName = 1336;
      goto LABEL_89;
    }
    *v10 = v51;
    LODWORD(v38) = v37 >> 1;
    *((_BYTE *)*a4 + 1) = 24;
    *((_DWORD *)*a4 + 1) = v37 >> 1;
    *((_QWORD *)*a4 + 1) = LocalAlloc(0x40u, v37 >> 1);
    if ( !*((_QWORD *)*a4 + 1) )
    {
      AttributeName = 8;
      goto LABEL_89;
    }
    for ( j = v37 - 1; j >= 1; j -= 2 )
    {
      if ( !(unsigned __int8)GetDigitFromChar(a1[j], v50) || !(unsigned __int8)GetDigitFromChar(a1[j - 1], &v49) )
        goto LABEL_2;
      v38 = (unsigned int)(v38 - 1);
      *(_BYTE *)(v38 + *((_QWORD *)*a4 + 1)) = v50[0] | (16 * v49);
    }
  }
LABEL_90:
  if ( hMem )
    FreeOperandValue(hMem);
  if ( v14 && v56 )
    LocalFree(v14);
  return AttributeName;
}

```

## disassembly

```asm
0x1800092d0  mov     rax, rsp
0x1800092d3  push    rbp
0x1800092d4  push    rbx
0x1800092d5  push    rdi
0x1800092d6  lea     rbp, [rax-37h]
0x1800092da  sub     rsp, 90h
0x1800092e1  mov     [rax+8], rsi
0x1800092e5  movzx   ebx, dl
0x1800092e8  mov     rsi, [rbp+2Fh+arg_20]
0x1800092ec  mov     edx, 10h; uBytes
0x1800092f1  mov     [rax+10h], r12
0x1800092f5  movzx   r12d, r8b
0x1800092f9  mov     [rax+18h], r13
0x1800092fd  mov     [rax-20h], r14
0x180009301  mov     r14, r9
0x180009304  mov     [rax-28h], r15
0x180009308  xor     eax, eax
0x18000930a  mov     r15, rcx
0x18000930d  mov     [rbp+2Fh+var_4C], eax
0x180009310  mov     ecx, 40h ; '@'; uFlags
0x180009315  mov     [rbp+2Fh+var_4F], al
0x180009318  mov     [rbp+2Fh+var_50], al
0x18000931b  mov     edi, eax
0x18000931d  mov     [rbp+2Fh+EndPtr], rax
0x180009321  mov     [rbp+2Fh+Sid], rax
0x180009325  mov     [rbp+2Fh+arg_18], al
0x180009328  mov     [rbp+2Fh+hMem], rax
0x18000932c  mov     [rbp+2Fh+var_30], rax
0x180009330  mov     [rsi], eax
0x180009332  call    cs:__imp_LocalAlloc
0x180009338  mov     [r14], rax
0x18000933b  test    rax, rax
0x18000933e  jnz     short loc_18000934A
0x180009340  mov     ebx, 8
0x180009345  jmp     loc_180009904
0x18000934a  test    bl, bl
0x18000934c  jnz     loc_1800098F0
0x180009352  mov     r8d, 1; MaxCount
0x180009358  lea     rdx, asc_18005FD14; "@"
0x18000935f  mov     rcx, r15; String1
0x180009362  call    cs:__imp__wcsnicmp
0x180009368  test    eax, eax
0x18000936a  jz      loc_1800098F0
0x180009370  movzx   eax, word ptr [r15]
0x180009374  cmp     ax, 22h ; '"'
0x180009378  jnz     short loc_180009397
0x18000937a  mov     r8, rsi
0x18000937d  mov     rdx, r14
0x180009380  mov     rcx, r15
0x180009383  call    GetStringOperandValue
0x180009388  mov     ebx, eax
0x18000938a  test    eax, eax
0x18000938c  jz      loc_180009913
0x180009392  jmp     loc_180009904
0x180009397  xor     ebx, ebx
0x180009399  cmp     ax, 7Bh ; '{'
0x18000939d  jnz     loc_1800095B3
0x1800093a3  mov     rax, [r14]
0x1800093a6  xor     r13b, r13b
0x1800093a9  mov     byte ptr [rbp+2Fh+arg_20], r13b
0x1800093ad  mov     byte ptr [rax+1], 50h ; 'P'
0x1800093b1  mov     eax, 1
0x1800093b6  mov     [rbp+2Fh+var_4C], eax
0x1800093b9  mov     ecx, eax
0x1800093bb  mov     eax, ecx
0x1800093bd  cmp     [r15+rax*2], di
0x1800093c2  jz      loc_180009913
0x1800093c8  lea     rdx, [rbp+2Fh+var_4C]
0x1800093cc  mov     rcx, r15
0x1800093cf  call    GetNextNoneWhiteSpace
0x1800093d4  mov     ebx, eax
0x1800093d6  test    eax, eax
0x1800093d8  jnz     loc_180009904
0x1800093de  mov     eax, [rbp+2Fh+var_4C]
0x1800093e1  cmp     word ptr [r15+rax*2], 7Bh ; '{'
0x1800093e7  lea     rcx, [r15+rax*2]
0x1800093eb  jz      loc_1800095F9
0x1800093f1  movzx   eax, [rbp+2Fh+arg_40]
0x1800093f5  lea     r9, [rbp+2Fh+hMem]
0x1800093f9  mov     [rsp+40h], al
0x1800093fd  xor     r8d, r8d
0x180009400  mov     rax, [rbp+2Fh+arg_38]
0x180009404  xor     edx, edx
0x180009406  mov     qword ptr [rsp+0A0h+var_68], rax
0x18000940b  mov     rax, [rbp+2Fh+arg_30]
0x18000940f  mov     [rsp+0A0h+var_70], rax
0x180009414  mov     rax, [rbp+2Fh+arg_28]
0x180009418  mov     [rsp+0A0h+var_78], rax
0x18000941d  mov     [rsp+0A0h+var_80], rsi
0x180009422  call    GetOperandValue
0x180009427  mov     ebx, eax
0x180009429  test    eax, eax
0x18000942b  jnz     loc_180009904
0x180009431  mov     rbx, [rbp+2Fh+hMem]
0x180009435  test    r12b, r12b
0x180009438  jz      short loc_180009450
0x18000943a  test    r13b, r13b
0x18000943d  jz      short loc_180009449
0x18000943f  cmp     r13b, [rbx+1]
0x180009443  jnz     loc_1800095F9
0x180009449  movzx   eax, byte ptr [rbx+1]
0x18000944d  mov     byte ptr [rbp+2Fh+arg_20], al
0x180009450  movzx   ecx, byte ptr [rbx+1]
0x180009454  call    IsValueSizeFixed
0x180009459  mov     rdx, [r14]
0x18000945c  test    al, al
0x18000945e  mov     [rbp+2Fh+var_4F], al
0x180009461  mov     r10d, 1
0x180009467  mov     eax, 5
0x18000946c  cmovz   r10d, eax
0x180009470  mov     r8, [rdx+8]
0x180009474  test    r8, r8
0x180009477  jz      short loc_1800094B6
0x180009479  mov     r9d, [rbx+4]
0x18000947d  add     r9d, [rdx+4]
0x180009481  cmp     r9d, [rdx+4]
0x180009485  jb      loc_180009599
0x18000948b  lea     r13d, [r9+r10]
0x18000948f  cmp     r13d, r9d
0x180009492  jb      loc_180009599
0x180009498  mov     rbx, rdx
0x18000949b  mov     edx, r13d
0x18000949e  call    SddlpReAlloc
0x1800094a3  mov     [rbx+8], rax
0x1800094a7  mov     rax, [r14]
0x1800094aa  cmp     [rax+8], rdi
0x1800094ae  jz      loc_180009340
0x1800094b4  jmp     short loc_1800094DB
0x1800094b6  mov     r13d, [rbx+4]
0x1800094ba  add     r13d, r10d
0x1800094bd  cmp     r13d, r10d
0x1800094c0  jb      loc_180009599
0x1800094c6  mov     edx, r13d; uBytes
0x1800094c9  mov     ecx, 40h ; '@'; uFlags
0x1800094ce  call    cs:__imp_LocalAlloc
0x1800094d4  mov     rcx, [r14]
0x1800094d7  mov     [rcx+8], rax
0x1800094db  mov     rax, [r14]
0x1800094de  mov     r8, [rax+8]
0x1800094e2  test    r8, r8
0x1800094e5  jz      loc_180009340
0x1800094eb  mov     edx, [rax+4]
0x1800094ee  mov     rax, [rbp+2Fh+hMem]
0x1800094f2  movzx   r10d, [rbp+2Fh+var_4F]
0x1800094f7  movzx   ecx, byte ptr [rax+1]
0x1800094fb  mov     [rdx+r8], cl
0x1800094ff  test    r10b, r10b
0x180009502  jnz     short loc_18000951B
0x180009504  mov     rax, [r14]
0x180009507  mov     r8d, [rax+4]
0x18000950b  mov     rdx, [rax+8]
0x18000950f  mov     rax, [rbp+2Fh+hMem]
0x180009513  mov     ecx, [rax+4]
0x180009516  mov     [r8+rdx+1], ecx
0x18000951b  mov     r9, [r14]
0x18000951e  test    r10b, r10b
0x180009521  mov     rdx, [rbp+2Fh+hMem]
0x180009525  mov     eax, 5
0x18000952a  mov     ecx, 1
0x18000952f  cmovz   ecx, eax
0x180009532  mov     eax, [r9+4]
0x180009536  mov     r8d, [rdx+4]; Size
0x18000953a  add     rcx, rax
0x18000953d  add     rcx, [r9+8]; void *
0x180009541  mov     rdx, [rdx+8]; Src
0x180009545  call    memcpy_0
0x18000954a  mov     rax, [r14]
0x18000954d  mov     [rax+4], r13d
0x180009551  mov     rcx, [rbp+2Fh+hMem]; hMem
0x180009555  call    FreeOperandValue
0x18000955a  mov     eax, [rbp+2Fh+var_4C]
0x18000955d  lea     rdx, [rbp+2Fh+var_4C]
0x180009561  add     eax, [rsi]
0x180009563  mov     rcx, r15
0x180009566  mov     [rbp+2Fh+var_4C], eax
0x180009569  mov     [rbp+2Fh+hMem], rdi
0x18000956d  call    GetNextNoneWhiteSpace
0x180009572  mov     ebx, eax
0x180009574  test    eax, eax
0x180009576  jnz     loc_180009904
0x18000957c  mov     ecx, [rbp+2Fh+var_4C]
0x18000957f  movzx   edx, word ptr [r15+rcx*2]
0x180009584  cmp     dx, 2Ch ; ','
0x180009588  jnz     short loc_1800095A3
0x18000958a  movzx   r13d, byte ptr [rbp+2Fh+arg_20]
0x18000958f  inc     ecx
0x180009591  mov     [rbp+2Fh+var_4C], ecx
0x180009594  jmp     loc_1800093BB
0x180009599  mov     ebx, 216h
0x18000959e  jmp     loc_180009904
0x1800095a3  cmp     dx, 7Dh ; '}'
0x1800095a7  jnz     short loc_1800095F9
0x1800095a9  lea     eax, [rcx+1]
0x1800095ac  mov     [rsi], eax
0x1800095ae  jmp     loc_180009913
0x1800095b3  mov     r13d, 3
0x1800095b9  lea     rdx, aSid_0; "SID"
0x1800095c0  mov     r8d, r13d; MaxCount
0x1800095c3  mov     rcx, r15; String1
0x1800095c6  call    cs:__imp__wcsnicmp
0x1800095cc  lea     rdx, [rbp+2Fh+var_4C]
0x1800095d0  mov     rcx, r15
0x1800095d3  test    eax, eax
0x1800095d5  jnz     loc_1800096BE
0x1800095db  mov     [rbp+2Fh+var_4C], r13d
0x1800095df  call    GetNextNoneWhiteSpace
0x1800095e4  mov     ebx, eax
0x1800095e6  test    eax, eax
0x1800095e8  jnz     loc_180009904
0x1800095ee  mov     ecx, [rbp+2Fh+var_4C]
0x1800095f1  cmp     word ptr [r15+rcx*2], 28h ; '('
0x1800095f7  jz      short loc_180009603
0x1800095f9  mov     ebx, 538h
0x1800095fe  jmp     loc_180009904
0x180009603  movzx   eax, [rbp+2Fh+arg_40]
0x180009607  lea     edi, [rcx+1]
0x18000960a  mov     [rsp+0A0h+var_68], al
0x18000960e  lea     r12, [rdi+rdi]
0x180009612  mov     rax, [rbp+2Fh+arg_38]
0x180009616  lea     rcx, [r12+r15]
0x18000961a  mov     [rsp+0A0h+var_70], rax
0x18000961f  lea     r9, [rbp+2Fh+arg_18]
0x180009623  mov     rax, [rbp+2Fh+arg_30]
0x180009627  lea     r8, [rbp+2Fh+var_30]
0x18000962b  mov     [rsp+0A0h+var_78], rax
0x180009630  lea     rdx, [rbp+2Fh+Sid]
0x180009634  mov     rax, [rbp+2Fh+arg_28]
0x180009638  mov     [rsp+0A0h+var_80], rax
0x18000963d  call    LocalGetSidForString
0x180009642  mov     ebx, eax
0x180009644  test    eax, eax
0x180009646  jnz     short loc_18000967C
0x180009648  mov     rax, [rbp+2Fh+var_30]
0x18000964c  lea     rdx, [rbp+2Fh+var_4C]
0x180009650  sub     rax, r12
0x180009653  mov     rcx, r15
0x180009656  sub     rax, r15
0x180009659  sar     rax, 1
0x18000965c  add     eax, edi
0x18000965e  mov     [rbp+2Fh+var_4C], eax
0x180009661  call    GetNextNoneWhiteSpace
0x180009666  mov     ebx, eax
0x180009668  test    eax, eax
0x18000966a  jnz     short loc_18000967C
0x18000966c  mov     ecx, [rbp+2Fh+var_4C]
0x18000966f  cmp     word ptr [r15+rcx*2], 29h ; ')'
0x180009675  jz      short loc_180009685
0x180009677  mov     ebx, 538h
0x18000967c  mov     rdi, [rbp+2Fh+Sid]
0x180009680  jmp     loc_180009904
0x180009685  lea     eax, [rcx+1]
0x180009688  mov     [rsi], eax
0x18000968a  mov     rax, [r14]
0x18000968d  mov     rsi, [rbp+2Fh+Sid]
0x180009691  mov     rcx, rsi; Sid
0x180009694  mov     byte ptr [rax+1], 51h ; 'Q'
0x180009698  mov     rdi, [r14]
0x18000969b  call    cs:__imp_RtlLengthSid
0x1800096a1  cmp     [rbp+2Fh+arg_18], 0
0x1800096a5  mov     [rdi+4], eax
0x1800096a8  mov     rax, [r14]
0x1800096ab  setz    cl
0x1800096ae  xor     edi, edi
0x1800096b0  mov     [rax+8], rsi
0x1800096b4  mov     rax, [r14]
0x1800096b7  mov     [rax], cl
0x1800096b9  jmp     loc_180009913
0x1800096be  call    GetBinaryOperandLen
0x1800096c3  cmp     word ptr [r15], 23h ; '#'
0x1800096c8  jnz     loc_18000977E
0x1800096ce  mov     r13d, [rbp+2Fh+var_4C]
0x1800096d2  cmp     r13d, 2
0x1800096d6  jnb     short loc_1800096E2
0x1800096d8  mov     ebx, 538h
0x1800096dd  jmp     loc_180009904
0x1800096e2  mov     [rsi], r13d
0x1800096e5  mov     r12d, r13d
0x1800096e8  mov     rax, [r14]
0x1800096eb  mov     ecx, 40h ; '@'; uFlags
0x1800096f0  shr     r12d, 1
0x1800096f3  mov     edx, r12d; uBytes
0x1800096f6  mov     byte ptr [rax+1], 18h
0x1800096fa  mov     rax, [r14]
0x1800096fd  mov     [rax+4], r12d
0x180009701  call    cs:__imp_LocalAlloc
0x180009707  mov     rcx, [r14]
0x18000970a  mov     [rcx+8], rax
0x18000970e  mov     rax, [r14]
0x180009711  cmp     [rax+8], rbx
0x180009715  jnz     short loc_180009721
0x180009717  mov     ebx, 8
0x18000971c  jmp     loc_180009904
0x180009721  lea     esi, [r13-1]
0x180009725  cmp     esi, 1
0x180009728  jl      loc_180009913
0x18000972e  movsxd  rax, esi
0x180009731  lea     rdx, [rbp+2Fh+var_4F]
0x180009735  movzx   ecx, word ptr [r15+rax*2]
0x18000973a  lea     r13, [r15+rax*2]
0x18000973e  call    GetDigitFromChar
  ... truncated ...
```
