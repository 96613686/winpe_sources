# COleScript::ParseScriptTextCore(ushort const *,ushort const *,IUnknown *,ushort const *,unsigned __int64,ulong,ulong,tagVARIANT *,tagEXCEPINFO *)

- ea: `0x1800126a0`
- end: `0x180012c52`
- name: `?ParseScriptTextCore@COleScript@@QEAAJPEBG0PEAUIUnknown@@0_KKKPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z`
- size: `1458`
- prototype: `__int64 __fastcall(COleScript *this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, wchar_t *, unsigned __int64, unsigned int, __int16, struct tagVARIANT *pvarg, struct tagEXCEPINFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180012630`

## callees

- `0x180011650`
- `0x18001199c`
- `0x1800126a0`
- `0x180012c58`
- `0x180013328`
- `0x18001467c`
- `0x18001b5d0`
- `0x18003d310`
- `0x18003d39c`
- `0x18003e63c`
- `0x180040a9c`
- `0x180056eec`
- `0x18005908c`
- `0x18007941e`
- `0x180079490`

## import_xrefs

- `msvcrt!_wcsdup` at `0x1800127fc`
- `msvcrt!_wcsdup` at `0x1800127fc`
- `msvcrt!free` at `0x180012c2d`
- `msvcrt!free` at `0x180012c2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c05`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c41`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c05`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c41`
- `OLEAUT32!__imp_VariantInit` at `0x180012960`
- `OLEAUT32!__imp_VariantInit` at `0x180012960`
- `KERNEL32!GetCurrentThreadId` at `0x1800126f6`
- `KERNEL32!GetCurrentThreadId` at `0x1800126f6`

## pseudocode

```c
__int64 __fastcall COleScript::ParseScriptTextCore(
        COleScript *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4,
        wchar_t *a5,
        unsigned __int64 a6,
        unsigned int a7,
        __int16 a8,
        struct tagVARIANT *pvarg,
        struct tagEXCEPINFO *a10)
{
  struct tagVARIANT *v11; // r13
  COleScript *v13; // r14
  int v14; // ebx
  signed int v15; // r15d
  __int64 v16; // rbx
  unsigned int v17; // ecx
  struct NamedItem *v18; // rax
  _WORD *v19; // r14
  const unsigned __int16 *v20; // r8
  int v21; // r13d
  __int64 v22; // rdi
  int v23; // edx
  int v24; // edx
  wchar_t *v25; // rax
  struct tagEXCEPINFO *v26; // rbx
  int ScriptBody; // eax
  void *v28; // rsi
  int HasCode; // edi
  __int64 v31; // rdi
  OLECHAR *v32; // rax
  int v33; // r13d
  int v34; // eax
  __int64 v35; // rax
  unsigned __int16 *v36; // rcx
  int v37; // eax
  __int64 v38; // rax
  int v39; // r13d
  CSession *v40; // rcx
  struct RuntimeScriptException *v41; // rax
  struct RuntimeScriptException *v42; // rbx
  OLECHAR *v43; // rcx
  unsigned int v44; // [rsp+40h] [rbp-79h] BYREF
  struct NamedItem *v45; // [rsp+48h] [rbp-71h]
  void *Block; // [rsp+50h] [rbp-69h]
  char *v47; // [rsp+58h] [rbp-61h] BYREF
  __int64 v48; // [rsp+60h] [rbp-59h]
  int v49; // [rsp+68h] [rbp-51h]
  COleScript *v50; // [rsp+70h] [rbp-49h]
  BSTR bstrString; // [rsp+78h] [rbp-41h]
  struct tagEXCEPINFO *v52; // [rsp+80h] [rbp-39h]
  wchar_t *String2; // [rsp+88h] [rbp-31h]
  struct tagVARIANT *v54; // [rsp+90h] [rbp-29h]
  unsigned __int64 v55; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v56; // [rsp+A0h] [rbp-19h]
  __int64 v57; // [rsp+A4h] [rbp-15h]
  int v58; // [rsp+ACh] [rbp-Dh]
  unsigned int v59; // [rsp+B0h] [rbp-9h]
  int v60; // [rsp+B4h] [rbp-5h]

  v11 = pvarg;
  v13 = this;
  v14 = *((_DWORD *)this + 61);
  String2 = a5;
  v54 = pvarg;
  v52 = a10;
  v50 = this;
  if ( GetCurrentThreadId() == v14 )
  {
    bstrString = 0;
    if ( pvarg )
      VariantInit(pvarg);
    if ( a10 )
      *a10 = (struct tagEXCEPINFO)zmmword_1800800C0;
    v15 = a8 & 0x7E3;
    if ( pvarg || (a8 & 1) == 0 && (unsigned int)(*((_DWORD *)v13 + 39) - 1) <= 2 )
      v15 |= 0x80000000;
    v16 = -1;
    if ( *((_DWORD *)v13 + 162) )
    {
      v31 = -1;
      do
        ++v31;
      while ( a2[v31] );
      v44 = v31;
      v32 = _SysAllocStringLen(0, v31);
      bstrString = v32;
      if ( (_DWORD)v31 && !v32 )
        return (unsigned int)-2147024882;
      HasCode = DecodeScriptCore(a2, v31, v32, v31, &v44);
      if ( HasCode < 0 )
      {
LABEL_31:
        if ( bstrString )
          SysFreeString(bstrString);
        return (unsigned int)HasCode;
      }
      a2 = bstrString;
      bstrString[v44] = 0;
    }
    if ( !a2 || !*a2 )
    {
      v26 = v52;
      v28 = 0;
      HasCode = 0;
      goto LABEL_28;
    }
    v17 = 0;
    v18 = 0;
    v44 = 0;
    v45 = 0;
    if ( a3 && *a3 )
    {
      v18 = NamedItemList::Find((COleScript *)((char *)v13 + 280), a3);
      v45 = v18;
      if ( !v18 )
      {
        HasCode = -2147024809;
        goto LABEL_31;
      }
      v17 = *((_DWORD *)v18 + 13);
      v44 = v17;
    }
    v19 = (_WORD *)*((_QWORD *)v13 + 21);
    v20 = 0;
    Block = 0;
    v21 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    if ( v19 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v19[v22] );
      if ( (int)v22 < 0 )
        goto LABEL_16;
    }
    else
    {
      LODWORD(v22) = 0;
    }
    if ( (unsigned int)BuildString::FEnsureSpace((BuildString *)&v47, v22) )
    {
      v33 = HIDWORD(v48);
      Block = v47;
      memcpy_0(&v47[2 * SHIDWORD(v48)], v19, 2LL * (unsigned int)v22);
      v20 = (const unsigned __int16 *)Block;
      v21 = v22 + v33;
      v18 = v45;
      HIDWORD(v48) = v21;
      if ( Block )
        *((_WORD *)Block + v21) = 0;
    }
    else
    {
      v20 = (const unsigned __int16 *)v47;
      v21 = HIDWORD(v48);
      v18 = v45;
      Block = v47;
    }
    v17 = v44;
LABEL_16:
    v23 = v21 + 3;
    if ( v21 + 3 > v21 )
    {
      if ( v23 < (int)v48
        || (v34 = BuildString::FEnsureSpace((BuildString *)&v47, v23),
            v20 = (const unsigned __int16 *)v47,
            v21 = HIDWORD(v48),
            Block = v47,
            v34) )
      {
        v35 = v21;
        v21 += 3;
        HIDWORD(v48) = v21;
        v36 = (unsigned __int16 *)&v20[v35];
        *(_DWORD *)v36 = *(_DWORD *)L" - ";
        v36[2] = asc_1800826C8[2];
        if ( v20 )
          v20[v21] = 0;
      }
      v18 = v45;
      v17 = v44;
    }
    if ( a3 )
    {
      BuildString::AppendSz((BuildString *)&v47, a3, -1);
      BuildString::AppendCh((BuildString *)&v47, 0x20u);
      v20 = (const unsigned __int16 *)v47;
      v21 = HIDWORD(v48);
      v18 = v45;
      v17 = v44;
      Block = v47;
    }
    v24 = v21 + 12;
    if ( v21 + 12 <= v21 )
      goto LABEL_20;
    if ( v24 >= (int)v48 )
    {
      v37 = BuildString::FEnsureSpace((BuildString *)&v47, v24);
      v20 = (const unsigned __int16 *)v47;
      v17 = v44;
      Block = v47;
      if ( !v37 )
      {
LABEL_65:
        v18 = v45;
LABEL_20:
        if ( v49 )
          goto LABEL_69;
        if ( !v20 )
        {
          v25 = _wcsdup(&String);
          v17 = v44;
          v20 = v25;
          Block = v25;
          v18 = v45;
        }
        v47 = 0;
        v48 = 0;
        v49 = 0;
        if ( !v20 )
        {
LABEL_69:
          HasCode = -2147024882;
          BuildString::Reset((BuildString *)&v47);
          goto LABEL_31;
        }
        v13 = v50;
        if ( v18 && (*((_BYTE *)v18 + 56) & 2) == 0 )
        {
          HasCode = COleScript::RegisterNamedItemHasCode(v50, v18);
          if ( HasCode < 0 )
          {
            v28 = Block;
LABEL_79:
            free(v28);
            goto LABEL_31;
          }
          v20 = (const unsigned __int16 *)Block;
          v17 = v44;
        }
        v55 = a6;
        v56 = a7;
        v57 = 0;
        do
          ++v16;
        while ( a2[v16] );
        v58 = v16;
        v26 = v52;
        v59 = v17;
        v60 = 0;
        ScriptBody = COleScript::CreateScriptBody(v13, a2, v15, (struct SRCINFO *)&v55, String2, v20, v52, 0);
        v28 = Block;
        HasCode = ScriptBody;
        v11 = v54;
LABEL_28:
        if ( v15 < 0 && HasCode >= 0 )
          HasCode = COleScript::ExecutePendingScripts(v13, v11, v26);
        if ( (v15 & 0x400) != 0 )
        {
          v40 = (CSession *)*((_QWORD *)v13 + 80);
          if ( v40 )
          {
            v41 = CSession::PseGet(v40);
            v42 = v41;
            if ( v41 )
            {
              v43 = (OLECHAR *)*((_QWORD *)v41 + 3);
              if ( v43 )
                SysFreeString(v43);
              *((_QWORD *)v42 + 3) = _SysAllocString(L"Script error");
            }
          }
        }
        if ( !v28 )
          goto LABEL_31;
        goto LABEL_79;
      }
      v21 = HIDWORD(v48);
    }
    v38 = v21;
    v39 = v21 + 12;
    HIDWORD(v48) = v39;
    *(_OWORD *)&v20[v38] = *(_OWORD *)L"script block";
    *(_QWORD *)&v20[v38 + 8] = *(_QWORD *)L"lock";
    if ( v20 )
    {
      v20[v39] = 0;
      v17 = v44;
    }
    goto LABEL_65;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800126a0  push    rbp
0x1800126a2  push    rbx
0x1800126a3  push    rsi
0x1800126a4  push    rdi
0x1800126a5  push    r12
0x1800126a7  push    r13
0x1800126a9  push    r14
0x1800126ab  lea     rbp, [rsp-7]
0x1800126b0  sub     rsp, 0C0h
0x1800126b7  mov     rax, cs:__security_cookie
0x1800126be  xor     rax, rsp
0x1800126c1  mov     [rbp+37h+var_38], rax
0x1800126c5  mov     rax, [rbp+37h+arg_20]
0x1800126c9  mov     r12, r8
0x1800126cc  mov     r13, [rbp+37h+pvarg]
0x1800126d3  mov     rsi, rdx
0x1800126d6  mov     rdi, [rbp+37h+arg_48]
0x1800126dd  mov     r14, rcx
0x1800126e0  mov     ebx, [rcx+0F4h]
0x1800126e6  mov     [rbp+37h+var_68], rax
0x1800126ea  mov     [rbp+37h+var_60], r13
0x1800126ee  mov     [rbp+37h+var_70], rdi
0x1800126f2  mov     [rbp+37h+var_80], rcx
0x1800126f6  call    cs:__imp_GetCurrentThreadId
0x1800126fd  nop     dword ptr [rax+rax+00h]
0x180012702  cmp     eax, ebx
0x180012704  jnz     loc_180012953
0x18001270a  xor     r9d, r9d
0x18001270d  mov     [rsp+0F0h+arg_18], r15
0x180012715  mov     [rbp+37h+bstrString], r9
0x180012719  test    r13, r13
0x18001271c  jnz     loc_18001295D
0x180012722  test    rdi, rdi
0x180012725  jnz     loc_180012923
0x18001272b  mov     r15d, dword ptr [rbp+37h+arg_38]
0x18001272f  and     r15d, 7E3h
0x180012736  test    r13, r13
0x180012739  jz      loc_180012974
0x18001273f  bts     r15d, 1Fh
0x180012744  cmp     dword ptr [r14+288h], 0
0x18001274c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180012753  jnz     loc_180012995
0x180012759  test    rsi, rsi
0x18001275c  jz      loc_180012BAF
0x180012762  cmp     r9w, [rsi]
0x180012766  jz      loc_180012BAF
0x18001276c  mov     ecx, r9d
0x18001276f  mov     rax, r9
0x180012772  mov     [rbp+37h+var_B0], ecx
0x180012775  mov     [rbp+37h+var_A8], rax
0x180012779  test    r12, r12
0x18001277c  jnz     loc_1800128F4
0x180012782  mov     r14, [r14+0A8h]
0x180012789  mov     r8, r9
0x18001278c  mov     [rbp+37h+Block], r9
0x180012790  mov     r13d, r9d
0x180012793  mov     [rbp+37h+var_98], r9
0x180012797  mov     [rbp+37h+var_90], 0
0x18001279f  mov     [rbp+37h+var_88], r9d
0x1800127a3  test    r14, r14
0x1800127a6  jz      loc_180012A0A
0x1800127ac  mov     rdi, rbx
0x1800127af  nop
0x1800127b0  inc     rdi
0x1800127b3  cmp     word ptr [r14+rdi*2], 0
0x1800127b9  jnz     short loc_1800127B0
0x1800127bb  test    edi, edi
0x1800127bd  jns     loc_180012A0D
0x1800127c3  lea     edx, [r13+3]; int
0x1800127c7  cmp     edx, r13d
0x1800127ca  jge     loc_180012A76
0x1800127d0  test    r12, r12
0x1800127d3  jnz     loc_180012AD3
0x1800127d9  lea     edx, [r13+0Ch]; int
0x1800127dd  cmp     edx, r13d
0x1800127e0  jge     loc_180012B0B
0x1800127e6  cmp     [rbp+37h+var_88], 0
0x1800127ea  jnz     loc_180012B9C
0x1800127f0  test    r8, r8
0x1800127f3  jnz     short loc_180012819
0x1800127f5  lea     rcx, String; String
0x1800127fc  call    cs:__imp__wcsdup
0x180012803  nop     dword ptr [rax+rax+00h]
0x180012808  mov     ecx, [rbp+37h+var_B0]
0x18001280b  xor     r9d, r9d
0x18001280e  mov     r8, rax
0x180012811  mov     [rbp+37h+Block], rax
0x180012815  mov     rax, [rbp+37h+var_A8]
0x180012819  mov     [rbp+37h+var_98], r9
0x18001281d  mov     [rbp+37h+var_90], 0
0x180012825  mov     [rbp+37h+var_88], r9d
0x180012829  test    r8, r8
0x18001282c  jz      loc_180012B9C
0x180012832  mov     r14, [rbp+37h+var_80]
0x180012836  test    rax, rax
0x180012839  jnz     loc_180012B6E
0x18001283f  mov     rax, [rbp+37h+arg_28]
0x180012843  mov     [rbp+37h+var_58], rax
0x180012847  mov     eax, [rbp+37h+arg_30]
0x18001284a  mov     [rbp+37h+var_50], eax
0x18001284d  mov     [rbp+37h+var_4C], 0
0x180012855  inc     rbx
0x180012858  cmp     word ptr [rsi+rbx*2], 0
0x18001285d  jnz     short loc_180012855
0x18001285f  mov     rax, [rbp+37h+var_68]
0x180012863  mov     rdx, rsi; unsigned __int16 *
0x180012866  mov     [rsp+0F0h+var_B8], r9; unsigned __int16 *
0x18001286b  mov     [rbp+37h+var_44], ebx
0x18001286e  mov     rbx, [rbp+37h+var_70]
0x180012872  mov     [rsp+0F0h+var_C0], rbx; struct tagEXCEPINFO *
0x180012877  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x18001287c  mov     r8d, r15d; unsigned int
0x18001287f  mov     [rbp+37h+var_40], ecx
0x180012882  mov     rcx, r14; this
0x180012885  mov     [rbp+37h+var_3C], r9d
0x180012889  lea     r9, [rbp+37h+var_58]; struct SRCINFO *
0x18001288d  mov     [rsp+0F0h+String2], rax; String2
0x180012892  call    ?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@0@Z; COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,ushort const *)
0x180012897  mov     rsi, [rbp+37h+Block]
0x18001289b  mov     edi, eax
0x18001289d  mov     r13, [rbp+37h+var_60]
0x1800128a1  test    r15d, r15d
0x1800128a4  js      loc_180012BBE
0x1800128aa  bt      r15d, 0Ah
0x1800128af  jb      loc_180012BDB
0x1800128b5  test    rsi, rsi
0x1800128b8  jnz     loc_180012C2A
0x1800128be  mov     rax, [rbp+37h+bstrString]
0x1800128c2  test    rax, rax
0x1800128c5  jnz     loc_180012C3E
0x1800128cb  mov     r15, [rsp+0F0h+arg_18]
0x1800128d3  mov     eax, edi
0x1800128d5  mov     rcx, [rbp+37h+var_38]
0x1800128d9  xor     rcx, rsp; StackCookie
0x1800128dc  call    __security_check_cookie
0x1800128e1  add     rsp, 0C0h
0x1800128e8  pop     r14
0x1800128ea  pop     r13
0x1800128ec  pop     r12
0x1800128ee  pop     rdi
0x1800128ef  pop     rsi
0x1800128f0  pop     rbx
0x1800128f1  pop     rbp
0x1800128f2  retn
0x1800128f4  cmp     word ptr [r12], 0
0x1800128fa  jz      loc_180012782
0x180012900  lea     rcx, [r14+118h]; this
0x180012907  mov     rdx, r12; unsigned __int16 *
0x18001290a  call    ?Find@NamedItemList@@QEAAPEAUNamedItem@@PEBG@Z; NamedItemList::Find(ushort const *)
0x18001290f  mov     [rbp+37h+var_A8], rax
0x180012913  test    rax, rax
0x180012916  jnz     loc_1800129FC
0x18001291c  mov     edi, 80070057h
0x180012921  jmp     short loc_1800128BE
0x180012923  movaps  xmm0, xmmword ptr cs:zmmword_1800800C0
0x18001292a  movaps  xmm1, xmmword ptr cs:zmmword_1800800C0+10h
0x180012931  movups  xmmword ptr [rdi], xmm0
0x180012934  movaps  xmm0, xmmword ptr cs:zmmword_1800800C0+20h
0x18001293b  movups  xmmword ptr [rdi+10h], xmm1
0x18001293f  movaps  xmm1, xmmword ptr cs:zmmword_1800800C0+30h
0x180012946  movups  xmmword ptr [rdi+20h], xmm0
0x18001294a  movups  xmmword ptr [rdi+30h], xmm1
0x18001294e  jmp     loc_18001272B
0x180012953  mov     eax, 8000FFFFh
0x180012958  jmp     loc_1800128D5
0x18001295d  mov     rcx, r13; pvarg
0x180012960  call    cs:__imp_VariantInit
0x180012967  nop     dword ptr [rax+rax+00h]
0x18001296c  xor     r9d, r9d
0x18001296f  jmp     loc_180012722
0x180012974  test    r15b, 1
0x180012978  jnz     loc_180012744
0x18001297e  mov     eax, [r14+9Ch]
0x180012985  dec     eax
0x180012987  cmp     eax, 2
0x18001298a  ja      loc_180012744
0x180012990  jmp     loc_18001273F
0x180012995  mov     rdi, rbx
0x180012998  inc     rdi
0x18001299b  cmp     word ptr [rsi+rdi*2], 0
0x1800129a0  jnz     short loc_180012998
0x1800129a2  mov     edx, edi; unsigned int
0x1800129a4  mov     [rbp+37h+var_B0], edi
0x1800129a7  xor     ecx, ecx; unsigned __int16 *
0x1800129a9  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x1800129ae  mov     [rbp+37h+bstrString], rax
0x1800129b2  test    edi, edi
0x1800129b4  jz      short loc_1800129C5
0x1800129b6  test    rax, rax
0x1800129b9  jnz     short loc_1800129C5
0x1800129bb  mov     edi, 8007000Eh
0x1800129c0  jmp     loc_1800128CB
0x1800129c5  lea     rcx, [rbp+37h+var_B0]
0x1800129c9  mov     r9d, edi; unsigned int
0x1800129cc  mov     [rsp+0F0h+String2], rcx; unsigned int *
0x1800129d1  mov     r8, rax; unsigned __int16 *
0x1800129d4  mov     rcx, rsi; unsigned __int16 *
0x1800129d7  mov     edx, edi; unsigned int
0x1800129d9  call    ?DecodeScriptCore@@YAJPEBGKPEAGKPEAK@Z; DecodeScriptCore(ushort const *,ulong,ushort *,ulong,ulong *)
0x1800129de  mov     edi, eax
0x1800129e0  test    eax, eax
0x1800129e2  js      loc_1800128BE
0x1800129e8  mov     ecx, [rbp+37h+var_B0]
0x1800129eb  xor     r9d, r9d
0x1800129ee  mov     rsi, [rbp+37h+bstrString]
0x1800129f2  mov     [rsi+rcx*2], r9w
0x1800129f7  jmp     loc_180012759
0x1800129fc  mov     ecx, [rax+34h]
0x1800129ff  xor     r9d, r9d
0x180012a02  mov     [rbp+37h+var_B0], ecx
0x180012a05  jmp     loc_180012782
0x180012a0a  mov     edi, r9d
0x180012a0d  mov     edx, edi; int
0x180012a0f  lea     rcx, [rbp+37h+var_98]; this
0x180012a13  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180012a18  test    eax, eax
0x180012a1a  jz      short loc_180012A5B
0x180012a1c  mov     rcx, [rbp+37h+var_98]
0x180012a20  mov     rdx, r14; Src
0x180012a23  movsxd  r13, dword ptr [rbp+37h+var_90+4]
0x180012a27  mov     [rbp+37h+Block], rcx
0x180012a2b  mov     r8d, edi
0x180012a2e  add     r8, r8; Size
0x180012a31  lea     rcx, [rcx+r13*2]; void *
0x180012a35  call    memcpy_0
0x180012a3a  mov     r8, [rbp+37h+Block]
0x180012a3e  add     r13d, edi
0x180012a41  mov     rax, [rbp+37h+var_A8]
0x180012a45  xor     r9d, r9d
0x180012a48  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180012a4c  test    r8, r8
0x180012a4f  jz      short loc_180012A6E
0x180012a51  movsxd  rcx, r13d
0x180012a54  mov     [r8+rcx*2], r9w
0x180012a59  jmp     short loc_180012A6E
0x180012a5b  mov     r8, [rbp+37h+var_98]
0x180012a5f  xor     r9d, r9d
0x180012a62  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180012a66  mov     rax, [rbp+37h+var_A8]
0x180012a6a  mov     [rbp+37h+Block], r8
0x180012a6e  mov     ecx, [rbp+37h+var_B0]
0x180012a71  jmp     loc_1800127C3
0x180012a76  cmp     edx, dword ptr [rbp+37h+var_90]
0x180012a79  jl      short loc_180012A97
0x180012a7b  lea     rcx, [rbp+37h+var_98]; this
0x180012a7f  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180012a84  mov     r8, [rbp+37h+var_98]
0x180012a88  xor     r9d, r9d
0x180012a8b  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180012a8f  mov     [rbp+37h+Block], r8
0x180012a93  test    eax, eax
0x180012a95  jz      short loc_180012AC7
0x180012a97  movsxd  rax, r13d
0x180012a9a  add     r13d, 3
0x180012a9e  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180012aa2  lea     rcx, [r8+rax*2]
0x180012aa6  mov     rax, qword ptr cs:asc_1800826C8; " - "
0x180012aad  mov     [rcx], eax
0x180012aaf  movzx   eax, word ptr cs:asc_1800826C8+4; " "
0x180012ab6  mov     [rcx+4], ax
0x180012aba  test    r8, r8
0x180012abd  jz      short loc_180012AC7
0x180012abf  movsxd  rcx, r13d
0x180012ac2  mov     [r8+rcx*2], r9w
0x180012ac7  mov     rax, [rbp+37h+var_A8]
0x180012acb  mov     ecx, [rbp+37h+var_B0]
0x180012ace  jmp     loc_1800127D0
0x180012ad3  mov     r8d, ebx; int
0x180012ad6  lea     rcx, [rbp+37h+var_98]; this
0x180012ada  mov     rdx, r12; unsigned __int16 *
0x180012add  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180012ae2  mov     edx, 20h ; ' '; unsigned __int16
0x180012ae7  lea     rcx, [rbp+37h+var_98]; this
0x180012aeb  call    ?AppendCh@BuildString@@QEAAJG@Z; BuildString::AppendCh(ushort)
0x180012af0  mov     r8, [rbp+37h+var_98]
0x180012af4  xor     r9d, r9d
0x180012af7  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180012afb  mov     rax, [rbp+37h+var_A8]
0x180012aff  mov     ecx, [rbp+37h+var_B0]
0x180012b02  mov     [rbp+37h+Block], r8
0x180012b06  jmp     loc_1800127D9
0x180012b0b  cmp     edx, dword ptr [rbp+37h+var_90]
0x180012b0e  jl      short loc_180012B2F
0x180012b10  lea     rcx, [rbp+37h+var_98]; this
0x180012b14  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180012b19  mov     r8, [rbp+37h+var_98]
0x180012b1d  xor     r9d, r9d
0x180012b20  mov     ecx, [rbp+37h+var_B0]
0x180012b23  mov     [rbp+37h+Block], r8
0x180012b27  test    eax, eax
0x180012b29  jz      short loc_180012B65
0x180012b2b  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180012b2f  movups  xmm0, xmmword ptr cs:aScriptBlock; "script block"
0x180012b36  movsxd  rax, r13d
0x180012b39  add     r13d, 0Ch
0x180012b3d  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180012b41  movups  xmmword ptr [r8+rax*2], xmm0
0x180012b46  movsd   xmm1, qword ptr cs:aScriptBlock+10h; "lock"
0x180012b4e  movsd   qword ptr [r8+rax*2+10h], xmm1
0x180012b55  test    r8, r8
  ... truncated ...
```
