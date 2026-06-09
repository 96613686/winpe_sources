# VbsStrComp(VAR *,int,VAR *)

- ea: `0x1800184c0`
- end: `0x180018a8d`
- name: `?VbsStrComp@@YAJPEAVVAR@@H0@Z`
- size: `1485`
- prototype: `__int64 __fastcall(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015fec`
- `0x180016a60`
- `0x1800184c0`
- `0x180018aa0`
- `0x1800252c0`
- `0x180026150`
- `0x18004237c`
- `0x1800439c8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180018a7c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800187aa`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800187aa`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800187c5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800187c5`
- `KERNEL32!CompareStringA` at `0x180018a39`
- `KERNEL32!CompareStringA` at `0x180018a39`
- `KERNEL32!CompareStringW` at `0x180018702`
- `KERNEL32!CompareStringW` at `0x180018702`
- `KERNEL32!WideCharToMultiByte` at `0x1800189d9`
- `KERNEL32!WideCharToMultiByte` at `0x180018a05`
- `KERNEL32!WideCharToMultiByte` at `0x1800189d9`
- `KERNEL32!WideCharToMultiByte` at `0x180018a05`
- `KERNEL32!IsValidLocale` at `0x1800188f0`
- `KERNEL32!IsValidLocale` at `0x1800188f0`
- `KERNEL32!TlsGetValue` at `0x180018518`
- `KERNEL32!TlsGetValue` at `0x180018518`
- `KERNEL32!SetLastError` at `0x180018a54`
- `KERNEL32!SetLastError` at `0x180018a54`

## pseudocode

```c
__int64 __fastcall VbsStrComp(struct VAR *a1, int a2, struct VAR *a3)
{
  struct VAR *v3; // rdi
  LCID Val; // eax
  LCID DefaultLocale; // esi
  int v6; // r14d
  _QWORD *Value; // rax
  __int64 v8; // rsi
  __int16 v9; // ax
  struct IDispatch **v10; // rcx
  VARTYPE v11; // r9
  __int16 v12; // r12
  __int64 v13; // r15
  struct IDispatch **v14; // rbx
  char v15; // r13
  unsigned __int16 v16; // ax
  DWORD v17; // r10d
  __int64 v18; // r11
  unsigned int v19; // r8d
  unsigned int v20; // r13d
  unsigned int v21; // ebx
  _WORD *v22; // rcx
  unsigned int v23; // eax
  _WORD *v24; // rdx
  bool v25; // cf
  int v26; // r8d
  int cchCount2; // r13d
  int v28; // eax
  const unsigned __int16 *v29; // r8
  int v30; // r9d
  int v31; // eax
  bool v32; // zf
  unsigned __int16 v34; // ax
  UINT v35; // edx
  const unsigned __int16 *v36; // r8
  int v37; // r9d
  BSTR v38; // rax
  struct VAR *v39; // rax
  struct VAR *v40; // rax
  int Default; // eax
  const unsigned __int16 *v42; // r8
  int v43; // r9d
  int v44; // eax
  const unsigned __int16 *v45; // r8
  int v46; // r9d
  __int64 v47; // rcx
  unsigned __int8 v48; // al
  int v49; // edi
  CHAR *v50; // rax
  const CHAR *v51; // rbx
  DWORD v52; // ecx
  const CHAR *v53; // rbp
  int v54; // eax
  int v55; // edi
  int v56; // eax
  CHAR *lpString2; // [rsp+20h] [rbp-78h]
  __int64 lpWideCharStr; // [rsp+40h] [rbp-58h]
  char v60; // [rsp+A8h] [rbp+10h]
  struct IDispatch **cchWideChar; // [rsp+B0h] [rbp+18h] BYREF
  DWORD dwCmpFlags; // [rsp+B8h] [rbp+20h]

  v3 = a3;
  if ( (unsigned int)(a2 - 2) > 1 )
    return 2148139458LL;
  if ( a2 != 3 )
  {
    DefaultLocale = 0;
    goto LABEL_4;
  }
  Val = VAR::UlGetVal(a3);
  v3 = (struct VAR *)((char *)v3 + 24);
  DefaultLocale = Val;
  if ( Val < 2 )
  {
LABEL_4:
    v6 = DefaultLocale;
    Value = TlsGetValue(g_luTls);
    if ( Value && (v8 = Value[3]) != 0 )
      DefaultLocale = *(_DWORD *)(v8 + 188);
    else
      DefaultLocale = GetDefaultLocale();
    goto LABEL_7;
  }
  v6 = 1;
  if ( !IsValidLocale(Val, 1u) )
    return 2148139013LL;
LABEL_7:
  v9 = *(_WORD *)v3;
  if ( *(_WORD *)v3 == 16396 || v9 == 74 )
  {
    v10 = (struct IDispatch **)*((_QWORD *)v3 + 1);
    v9 = *(_WORD *)v10;
  }
  else
  {
    v10 = (struct IDispatch **)v3;
  }
  cchWideChar = v10;
  if ( v9 == 9 )
  {
    Default = VAR::ObjGetDefault(v10[1], (struct VAR **)&cchWideChar);
    if ( Default < 0 )
      RaiseErrorHr(Default, 0, v42, v43);
    v10 = cchWideChar;
  }
  v11 = 8;
  v12 = -1;
  if ( *(_WORD *)v10 == 8 )
  {
    v13 = (__int64)v10[1];
  }
  else
  {
    if ( *(_WORD *)v10 == 1 )
    {
      v13 = -1;
      v14 = (struct IDispatch **)((char *)v3 + 24);
LABEL_16:
      v15 = 0;
      goto LABEL_17;
    }
    v39 = VAR::PvarConvert((VAR *)v10, 8u);
    v11 = 8;
    v13 = *((_QWORD *)v39 + 1);
  }
  v14 = (struct IDispatch **)((char *)v3 + 24);
  if ( !v13 || v13 == -1 || v3 == (struct VAR *)-24LL )
    goto LABEL_16;
  v34 = *(_WORD *)v14;
  if ( *(_WORD *)v14 == 16396 || v34 == 74 )
    v34 = **((_WORD **)v3 + 4);
  if ( v34 == 8 || (v34 & 0x4000) == 0 && (unsigned int)VAR::IsSimpleType(v34) )
    goto LABEL_16;
  v35 = SysStringByteLen((BSTR)v13);
  v38 = 0;
  if ( v35 < 0x7FFFFFFD )
    v38 = SysAllocStringByteLen((LPCSTR)v13, v35);
  if ( !v38 )
    RaiseErrorHr(-2146828281, 0, v36, v37);
  v13 = (__int64)v38;
  v15 = 1;
  v11 = 8;
LABEL_17:
  v16 = *(_WORD *)v14;
  v60 = v15;
  if ( *(_WORD *)v14 == 16396 || v16 == 74 )
  {
    v14 = (struct IDispatch **)*((_QWORD *)v3 + 4);
    v16 = *(_WORD *)v14;
  }
  cchWideChar = v14;
  if ( v16 == 9 )
  {
    v44 = VAR::ObjGetDefault(v14[1], (struct VAR **)&cchWideChar);
    if ( v44 < 0 )
      RaiseErrorHr(v44, 0, v45, v46);
    v14 = cchWideChar;
    v11 = 8;
  }
  v17 = 1;
  if ( v11 == *(_WORD *)v14 )
  {
    v18 = (__int64)v14[1];
  }
  else
  {
    if ( *(_WORD *)v14 == 1 )
    {
      v18 = -1;
      lpWideCharStr = -1;
      goto LABEL_23;
    }
    v40 = VAR::PvarConvert((VAR *)v14, v11);
    v17 = 1;
    v18 = *((_QWORD *)v40 + 1);
  }
  lpWideCharStr = v18;
LABEL_23:
  if ( v13 == -1 || v18 == -1 )
  {
    v32 = v15 == 0;
    *(_WORD *)a1 = 1;
    goto LABEL_51;
  }
  if ( v18 )
    v19 = *(_DWORD *)(v18 - 4);
  else
    v19 = 0;
  LODWORD(cchWideChar) = v19;
  if ( v13 )
    v20 = *(_DWORD *)(v13 - 4);
  else
    v20 = 0;
  v21 = v19;
  if ( v19 >= v20 )
    v21 = v20;
  if ( !v21 )
  {
LABEL_39:
    if ( v19 >= v20 )
    {
      if ( v19 <= v20 )
      {
        v12 = 2;
        if ( v19 == v20 )
          v12 = 0;
      }
      else
      {
        v12 = 1;
      }
    }
    goto LABEL_50;
  }
  if ( !v6 )
  {
    v22 = (_WORD *)v13;
    v23 = v21 >> 1;
    v24 = (_WORD *)v18;
    while ( v23 )
    {
      v25 = *v24 < *v22;
      if ( *v24 != *v22 )
        goto LABEL_91;
      --v23;
      ++v24;
      ++v22;
    }
    if ( (v21 & 1) == 0
      || (v47 = v21 - 1, v48 = *(_BYTE *)(v47 + v18), v25 = v48 < *(_BYTE *)(v47 + v13), v48 == *(_BYTE *)(v47 + v13)) )
    {
      v19 = (unsigned int)cchWideChar;
      goto LABEL_39;
    }
LABEL_91:
    if ( !v25 )
      v12 = 1;
    goto LABEL_50;
  }
  if ( g_fFarEast )
    v17 = 131073;
  dwCmpFlags = v17;
  if ( g_fJapan )
  {
    v17 |= 0x10000u;
    dwCmpFlags = v17;
  }
  v26 = v19 >> 1;
  cchCount2 = v20 >> 1;
  LODWORD(cchWideChar) = v26;
  if ( !g_fAnsiOs )
  {
    v28 = CompareStringW(DefaultLocale, v17, (PCNZWCH)v18, v26, (PCNZWCH)v13, cchCount2);
    goto LABEL_48;
  }
  if ( !v26 || !cchCount2 )
  {
    v52 = 87;
    goto LABEL_102;
  }
  v49 = 2 * v26;
  v50 = (CHAR *)MemAlloc(2 * cchCount2 + 2 * v26);
  v51 = v50;
  if ( !v50 )
  {
    v52 = 14;
LABEL_102:
    SetLastError(v52);
    goto LABEL_77;
  }
  v53 = &v50[v49];
  v54 = WideCharToMultiByte(0, 0, (LPCWCH)lpWideCharStr, (int)cchWideChar, v50, v49, 0, 0);
  lpString2 = (CHAR *)&v51[v49];
  v55 = v54;
  v56 = WideCharToMultiByte(0, 0, (LPCWCH)v13, cchCount2, lpString2, 2 * cchCount2, 0, 0);
  if ( !v55 || !v56 )
LABEL_77:
    RaiseErrorHr(-2146828283, 0, v29, v30);
  v28 = CompareStringA(DefaultLocale, dwCmpFlags, v51, v55, v53, v56);
LABEL_48:
  v31 = v28 - 2;
  if ( v31 == -2 )
    goto LABEL_77;
  v12 = v31;
LABEL_50:
  v32 = v60 == 0;
  *((_WORD *)a1 + 4) = v12;
  *(_WORD *)a1 = 2;
LABEL_51:
  if ( !v32 )
    SysFreeString((BSTR)v13);
  return 0;
}

```

## disassembly

```asm
0x1800184c0  mov     r11, rsp
0x1800184c3  mov     [r11+8], rcx
0x1800184c7  push    rdi
0x1800184c8  sub     rsp, 90h
0x1800184cf  lea     eax, [rdx-2]
0x1800184d2  mov     rdi, r8
0x1800184d5  cmp     eax, 1
0x1800184d8  ja      loc_18001885E
0x1800184de  mov     [r11-10h], rbx
0x1800184e2  mov     ebx, 1
0x1800184e7  mov     [r11-20h], rsi
0x1800184eb  mov     [r11-38h], r14
0x1800184ef  cmp     edx, 3
0x1800184f2  jnz     loc_180018803
0x1800184f8  mov     rcx, r8; this
0x1800184fb  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x180018500  add     rdi, 18h
0x180018504  mov     esi, eax
0x180018506  cmp     eax, 2
0x180018509  jnb     loc_1800188E9
0x18001850f  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180018515  mov     r14d, esi
0x180018518  call    cs:__imp_TlsGetValue
0x18001851f  nop     dword ptr [rax+rax+00h]
0x180018524  test    rax, rax
0x180018527  jz      loc_1800187E7
0x18001852d  mov     rsi, [rax+18h]
0x180018531  test    rsi, rsi
0x180018534  jz      loc_1800187E7
0x18001853a  mov     esi, [rsi+0BCh]
0x180018540  movzx   eax, word ptr [rdi]
0x180018543  mov     [rsp+98h+var_18], rbp
0x18001854b  mov     ebp, 400Ch
0x180018550  cmp     ax, bp
0x180018553  jz      loc_18001880A
0x180018559  cmp     ax, 4Ah ; 'J'
0x18001855d  jz      loc_18001880A
0x180018563  mov     rcx, rdi; this
0x180018566  mov     edx, 9
0x18001856b  mov     [rsp+98h+cchWideChar], rcx
0x180018573  cmp     dx, ax
0x180018576  jz      loc_18001889F
0x18001857c  movzx   eax, word ptr [rcx]
0x18001857f  mov     r9d, 8
0x180018585  mov     [rsp+98h+var_28], r12
0x18001858a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180018591  mov     [rsp+98h+var_30], r13
0x180018596  mov     [rsp+98h+var_40], r15
0x18001859b  cmp     r9w, ax
0x18001859f  jnz     loc_180018822
0x1800185a5  mov     r15, [rcx+8]
0x1800185a9  lea     rbx, [rdi+18h]
0x1800185ad  test    r15, r15
0x1800185b0  jz      short loc_1800185C0
0x1800185b2  cmp     r15, r12
0x1800185b5  jz      short loc_1800185C0
0x1800185b7  test    rbx, rbx
0x1800185ba  jnz     loc_180018770
0x1800185c0  xor     r13b, r13b
0x1800185c3  movzx   eax, word ptr [rbx]
0x1800185c6  mov     [rsp+98h+arg_8], r13b
0x1800185ce  cmp     ax, bp
0x1800185d1  jz      loc_180018816
0x1800185d7  cmp     ax, 4Ah ; 'J'
0x1800185db  jz      loc_180018816
0x1800185e1  mov     ecx, 9
0x1800185e6  mov     [rsp+98h+cchWideChar], rbx
0x1800185ee  cmp     cx, ax
0x1800185f1  jz      loc_1800188C1
0x1800185f7  movzx   eax, word ptr [rbx]
0x1800185fa  mov     r10d, 1
0x180018600  cmp     r9w, ax
0x180018604  jnz     loc_18001883E
0x18001860a  mov     r11, [rbx+8]
0x18001860e  mov     [rsp+98h+lpWideCharStr], r11
0x180018613  cmp     r15, r12
0x180018616  jz      loc_180018A65
0x18001861c  cmp     r11, r12
0x18001861f  jz      loc_180018A65
0x180018625  test    r11, r11
0x180018628  jz      loc_1800187F3
0x18001862e  mov     r8d, [r11-4]
0x180018632  mov     dword ptr [rsp+98h+cchWideChar], r8d
0x18001863a  test    r15, r15
0x18001863d  jz      loc_1800187FB
0x180018643  mov     r13d, [r15-4]
0x180018647  cmp     r8d, r13d
0x18001864a  mov     ebx, r8d
0x18001864d  mov     edi, 2
0x180018652  cmovnb  ebx, r13d
0x180018656  test    ebx, ebx
0x180018658  jz      short loc_18001869D
0x18001865a  test    r14d, r14d
0x18001865d  jnz     short loc_1800186AD
0x18001865f  mov     eax, ebx
0x180018661  mov     rcx, r15
0x180018664  shr     eax, 1
0x180018666  mov     rdx, r11
0x180018669  nop     dword ptr [rax+00000000h]
0x180018670  test    eax, eax
0x180018672  jz      short loc_18001868C
0x180018674  movzx   r8d, word ptr [rdx]
0x180018678  cmp     r8w, [rcx]
0x18001867c  jnz     loc_180018958
0x180018682  dec     eax
0x180018684  add     rdx, rdi
0x180018687  add     rcx, rdi
0x18001868a  jmp     short loc_180018670
0x18001868c  test    bl, 1
0x18001868f  jnz     loc_180018944
0x180018695  mov     r8d, dword ptr [rsp+98h+cchWideChar]
0x18001869d  cmp     r8d, r13d
0x1800186a0  jb      short loc_18001871D
0x1800186a2  jbe     loc_180018933
0x1800186a8  mov     r12d, r10d
0x1800186ab  jmp     short loc_18001871D
0x1800186ad  cmp     cs:?g_fFarEast@@3HA, 0; int g_fFarEast
0x1800186b4  mov     eax, 20001h
0x1800186b9  cmovnz  r10d, eax
0x1800186bd  cmp     cs:?g_fJapan@@3HA, 0; int g_fJapan
0x1800186c4  mov     [rsp+98h+dwCmpFlags], r10d
0x1800186cc  jnz     loc_180018961
0x1800186d2  shr     r8d, 1
0x1800186d5  shr     r13d, 1
0x1800186d8  cmp     cs:?g_fAnsiOs@@3HA, 0; int g_fAnsiOs
0x1800186df  mov     dword ptr [rsp+98h+cchWideChar], r8d
0x1800186e7  jnz     loc_180018973
0x1800186ed  mov     r9d, r8d; cchCount1
0x1800186f0  mov     [rsp+98h+cchCount2], r13d; cchCount2
0x1800186f5  mov     r8, r11; lpString1
0x1800186f8  mov     [rsp+98h+lpString2], r15; lpString2
0x1800186fd  mov     edx, r10d; dwCmpFlags
0x180018700  mov     ecx, esi; Locale
0x180018702  call    cs:__imp_CompareStringW
0x180018709  nop     dword ptr [rax+rax+00h]
0x18001870e  add     eax, 0FFFFFFFEh
0x180018711  cmp     eax, 0FFFFFFFEh
0x180018714  jz      loc_180018892
0x18001871a  mov     r12d, eax
0x18001871d  mov     rax, [rsp+98h+arg_0]
0x180018725  cmp     [rsp+98h+arg_8], 0
0x18001872d  mov     [rax+8], r12w
0x180018732  mov     [rax], di
0x180018735  jnz     loc_180018A79
0x18001873b  mov     r12, [rsp+98h+var_28]
0x180018740  xor     eax, eax
0x180018742  mov     r13, [rsp+98h+var_30]
0x180018747  mov     r15, [rsp+98h+var_40]
0x18001874c  mov     rbp, [rsp+98h+var_18]
0x180018754  mov     rsi, [rsp+98h+var_20]
0x180018759  mov     r14, [rsp+98h+var_38]
0x18001875e  mov     rbx, [rsp+98h+var_10]
0x180018766  add     rsp, 90h
0x18001876d  pop     rdi
0x18001876e  retn
0x180018770  movzx   eax, word ptr [rbx]
0x180018773  cmp     ax, bp
0x180018776  jz      loc_18001886D
0x18001877c  cmp     ax, 4Ah ; 'J'
0x180018780  jz      loc_18001886D
0x180018786  cmp     ax, 8
0x18001878a  jz      loc_1800185C0
0x180018790  bt      ax, 0Eh
0x180018795  jb      short loc_1800187A7
0x180018797  movzx   ecx, ax; int
0x18001879a  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18001879f  test    eax, eax
0x1800187a1  jnz     loc_1800185C0
0x1800187a7  mov     rcx, r15; bstr
0x1800187aa  call    cs:__imp_SysStringByteLen
0x1800187b1  nop     dword ptr [rax+rax+00h]
0x1800187b6  mov     edx, eax; len
0x1800187b8  xor     eax, eax
0x1800187ba  cmp     edx, 7FFFFFFDh
0x1800187c0  jnb     short loc_1800187D1
0x1800187c2  mov     rcx, r15; psz
0x1800187c5  call    cs:__imp_SysAllocStringByteLen
0x1800187cc  nop     dword ptr [rax+rax+00h]
0x1800187d1  test    rax, rax
0x1800187d4  jnz     loc_180018918
0x1800187da  xor     edx, edx; struct VAR *
0x1800187dc  mov     ecx, 800A0007h; int
0x1800187e1  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x1800187e7  call    ?GetDefaultLocale@@YAKXZ; GetDefaultLocale(void)
0x1800187ec  mov     esi, eax
0x1800187ee  jmp     loc_180018540
0x1800187f3  xor     r8d, r8d
0x1800187f6  jmp     loc_180018632
0x1800187fb  xor     r13d, r13d
0x1800187fe  jmp     loc_180018647
0x180018803  xor     esi, esi
0x180018805  jmp     loc_18001850F
0x18001880a  mov     rcx, [rdi+8]
0x18001880e  movzx   eax, word ptr [rcx]
0x180018811  jmp     loc_180018566
0x180018816  mov     rbx, [rdi+20h]
0x18001881a  movzx   eax, word ptr [rbx]
0x18001881d  jmp     loc_1800185E1
0x180018822  cmp     bx, ax
0x180018825  jz      short loc_180018879
0x180018827  mov     edx, r9d; vt
0x18001882a  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x18001882f  mov     r9d, 8
0x180018835  mov     r15, [rax+8]
0x180018839  jmp     loc_1800185A9
0x18001883e  cmp     r10w, ax
0x180018842  jz      short loc_180018885
0x180018844  mov     edx, r9d; vt
0x180018847  mov     rcx, rbx; this
0x18001884a  call    ?PvarConvert@VAR@@QEAAPEAV1@H@Z; VAR::PvarConvert(int)
0x18001884f  mov     r10d, 1
0x180018855  mov     r11, [rax+8]
0x180018859  jmp     loc_18001860E
0x18001885e  mov     eax, 800A01C2h
0x180018863  add     rsp, 90h
0x18001886a  pop     rdi
0x18001886b  retn
0x18001886d  mov     rax, [rdi+20h]
0x180018871  movzx   eax, word ptr [rax]
0x180018874  jmp     loc_180018786
0x180018879  mov     r15, r12
0x18001887c  lea     rbx, [rdi+18h]
0x180018880  jmp     loc_1800185C0
0x180018885  mov     r11, r12
0x180018888  mov     [rsp+98h+lpWideCharStr], r12
0x18001888d  jmp     loc_180018613
0x180018892  xor     edx, edx; struct VAR *
0x180018894  mov     ecx, 800A0005h; int
0x180018899  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x18001889f  mov     rcx, [rcx+8]; struct IDispatch *
0x1800188a3  lea     rdx, [rsp+98h+cchWideChar]; struct VAR **
0x1800188ab  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x1800188b0  test    eax, eax
0x1800188b2  js      short loc_18001890E
0x1800188b4  mov     rcx, [rsp+98h+cchWideChar]
0x1800188bc  jmp     loc_18001857C
0x1800188c1  mov     rcx, [rbx+8]; struct IDispatch *
0x1800188c5  lea     rdx, [rsp+98h+cchWideChar]; struct VAR **
0x1800188cd  call    ?ObjGetDefault@VAR@@SAJPEAUIDispatch@@PEAPEAV1@@Z; VAR::ObjGetDefault(IDispatch *,VAR * *)
0x1800188d2  test    eax, eax
0x1800188d4  js      short loc_180018929
0x1800188d6  mov     rbx, [rsp+98h+cchWideChar]
0x1800188de  mov     r9d, 8
0x1800188e4  jmp     loc_1800185F7
0x1800188e9  mov     edx, ebx; dwFlags
0x1800188eb  mov     ecx, eax; Locale
0x1800188ed  mov     r14d, ebx
0x1800188f0  call    cs:__imp_IsValidLocale
0x1800188f7  nop     dword ptr [rax+rax+00h]
0x1800188fc  test    eax, eax
0x1800188fe  jnz     loc_180018540
0x180018904  mov     eax, 800A0005h
0x180018909  jmp     loc_180018754
0x18001890e  xor     edx, edx; struct VAR *
0x180018910  mov     ecx, eax; int
0x180018912  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180018918  mov     r15, rax
0x18001891b  mov     r13b, 1
0x18001891e  mov     r9d, 8
0x180018924  jmp     loc_1800185C3
0x180018929  xor     edx, edx; struct VAR *
0x18001892b  mov     ecx, eax; int
0x18001892d  call    ?RaiseErrorHr@@YAXJPEAVVAR@@PEBGJ@Z; RaiseErrorHr(long,VAR *,ushort const *,long)
0x180018933  xor     eax, eax
0x180018935  mov     r12d, edi
0x180018938  cmp     r8d, r13d
0x18001893b  cmovz   r12d, eax
0x18001893f  jmp     loc_18001871D
0x180018944  lea     eax, [rbx-1]
0x180018947  mov     ecx, eax
0x180018949  movzx   eax, byte ptr [rax+r11]
0x18001894e  cmp     al, [rcx+r15]
0x180018952  jz      loc_180018695
0x180018958  cmovnb  r12d, r10d
0x18001895c  jmp     loc_18001871D
0x180018961  bts     r10d, 10h
0x180018966  mov     [rsp+98h+dwCmpFlags], r10d
0x18001896e  jmp     loc_1800186D2
0x180018973  test    r8d, r8d
0x180018976  jz      loc_180018A4F
0x18001897c  test    r13d, r13d
0x18001897f  jz      loc_180018A4F
0x180018985  lea     edi, [r8+r8]
0x180018989  lea     r14d, ds:0[r13*2]
0x180018991  lea     ecx, [r14+rdi]; unsigned int
0x180018995  call    ?MemAlloc@@YAPEAXI@Z; MemAlloc(uint)
0x18001899a  mov     rbx, rax
0x18001899d  test    rax, rax
0x1800189a0  jnz     short loc_1800189AC
0x1800189a2  mov     ecx, 0Eh
0x1800189a7  jmp     loc_180018A54
0x1800189ac  mov     r9d, dword ptr [rsp+98h+cchWideChar]; cchWideChar
0x1800189b4  xor     r12d, r12d
0x1800189b7  mov     r8, [rsp+98h+lpWideCharStr]; lpWideCharStr
0x1800189bc  xor     edx, edx; dwFlags
0x1800189be  mov     [rsp+98h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1800189c3  xor     ecx, ecx; CodePage
0x1800189c5  mov     [rsp+98h+lpDefaultChar], r12; lpDefaultChar
0x1800189ca  movsxd  rbp, edi
0x1800189cd  mov     [rsp+98h+cchCount2], edi; cbMultiByte
  ... truncated ...
```
