# COleScript::ParseScriptTextCore(ushort const *,ushort const *,IUnknown *,ushort const *,unsigned __int64,ulong,ulong,tagVARIANT *,tagEXCEPINFO *)

- ea: `0x180017b40`
- end: `0x1800180d4`
- name: `?ParseScriptTextCore@COleScript@@QEAAJPEBG0PEAUIUnknown@@0_KKKPEAUtagVARIANT@@PEAUtagEXCEPINFO@@@Z`
- size: `1428`
- prototype: `int(COleScript *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned int, struct tagVARIANT *, struct tagEXCEPINFO *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180017ad0`

## callees

- `0x180017b40`
- `0x1800180dc`
- `0x180018778`
- `0x180019a24`
- `0x18003512c`
- `0x180035154`
- `0x180037914`
- `0x18003bc44`
- `0x18003bcd0`
- `0x18003d140`
- `0x18003f1fc`
- `0x18005559c`
- `0x180057604`
- `0x18007672e`
- `0x1800767a0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180017c9c`
- `msvcrt!_wcsdup` at `0x180017c9c`
- `msvcrt!free` at `0x1800180bb`
- `msvcrt!free` at `0x1800180bb`
- `OLEAUT32!__imp_SysFreeString` at `0x180018099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180c9`
- `OLEAUT32!__imp_SysFreeString` at `0x180018099`
- `OLEAUT32!__imp_SysFreeString` at `0x1800180c9`
- `OLEAUT32!__imp_VariantInit` at `0x180017dfa`
- `OLEAUT32!__imp_VariantInit` at `0x180017dfa`
- `KERNEL32!GetCurrentThreadId` at `0x180017b96`
- `KERNEL32!GetCurrentThreadId` at `0x180017b96`

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
      *a10 = (struct tagEXCEPINFO)zmmword_18007D260;
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
        v36[2] = asc_18007F6D8[2];
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
0x180017b40  push    rbp
0x180017b42  push    rbx
0x180017b43  push    rsi
0x180017b44  push    rdi
0x180017b45  push    r12
0x180017b47  push    r13
0x180017b49  push    r14
0x180017b4b  lea     rbp, [rsp-7]
0x180017b50  sub     rsp, 0C0h
0x180017b57  mov     rax, cs:__security_cookie
0x180017b5e  xor     rax, rsp
0x180017b61  mov     [rbp+37h+var_38], rax
0x180017b65  mov     rax, [rbp+37h+arg_20]
0x180017b69  mov     r12, r8
0x180017b6c  mov     r13, [rbp+37h+pvarg]
0x180017b73  mov     rsi, rdx
0x180017b76  mov     rdi, [rbp+37h+arg_48]
0x180017b7d  mov     r14, rcx
0x180017b80  mov     ebx, [rcx+0F4h]
0x180017b86  mov     [rbp+37h+var_68], rax
0x180017b8a  mov     [rbp+37h+var_60], r13
0x180017b8e  mov     [rbp+37h+var_70], rdi
0x180017b92  mov     [rbp+37h+var_80], rcx
0x180017b96  call    cs:__imp_GetCurrentThreadId
0x180017b9c  cmp     eax, ebx
0x180017b9e  jnz     loc_180017DED
0x180017ba4  xor     r9d, r9d
0x180017ba7  mov     [rsp+0F0h+arg_18], r15
0x180017baf  mov     [rbp+37h+bstrString], r9
0x180017bb3  test    r13, r13
0x180017bb6  jnz     loc_180017DF7
0x180017bbc  test    rdi, rdi
0x180017bbf  jnz     loc_180017DBD
0x180017bc5  mov     r15d, dword ptr [rbp+37h+arg_38]
0x180017bc9  and     r15d, 7E3h
0x180017bd0  test    r13, r13
0x180017bd3  jz      loc_180017E08
0x180017bd9  bts     r15d, 1Fh
0x180017bde  cmp     dword ptr [r14+288h], 0
0x180017be6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180017bed  jnz     loc_180017E29
0x180017bf3  test    rsi, rsi
0x180017bf6  jz      loc_180018043
0x180017bfc  cmp     r9w, [rsi]
0x180017c00  jz      loc_180018043
0x180017c06  mov     ecx, r9d
0x180017c09  mov     rax, r9
0x180017c0c  mov     [rbp+37h+var_B0], ecx
0x180017c0f  mov     [rbp+37h+var_A8], rax
0x180017c13  test    r12, r12
0x180017c16  jnz     loc_180017D8E
0x180017c1c  mov     r14, [r14+0A8h]
0x180017c23  mov     r8, r9
0x180017c26  mov     [rbp+37h+Block], r9
0x180017c2a  mov     r13d, r9d
0x180017c2d  mov     [rbp+37h+var_98], r9
0x180017c31  mov     [rbp+37h+var_90], 0
0x180017c39  mov     [rbp+37h+var_88], r9d
0x180017c3d  test    r14, r14
0x180017c40  jz      loc_180017E9E
0x180017c46  mov     rdi, rbx
0x180017c49  nop     dword ptr [rax+00000000h]
0x180017c50  inc     rdi
0x180017c53  cmp     word ptr [r14+rdi*2], 0
0x180017c59  jnz     short loc_180017C50
0x180017c5b  test    edi, edi
0x180017c5d  jns     loc_180017EA1
0x180017c63  lea     edx, [r13+3]; int
0x180017c67  cmp     edx, r13d
0x180017c6a  jge     loc_180017F0A
0x180017c70  test    r12, r12
0x180017c73  jnz     loc_180017F67
0x180017c79  lea     edx, [r13+0Ch]; int
0x180017c7d  cmp     edx, r13d
0x180017c80  jge     loc_180017F9F
0x180017c86  cmp     [rbp+37h+var_88], 0
0x180017c8a  jnz     loc_180018030
0x180017c90  test    r8, r8
0x180017c93  jnz     short loc_180017CB3
0x180017c95  lea     rcx, String; String
0x180017c9c  call    cs:__imp__wcsdup
0x180017ca2  mov     ecx, [rbp+37h+var_B0]
0x180017ca5  xor     r9d, r9d
0x180017ca8  mov     r8, rax
0x180017cab  mov     [rbp+37h+Block], rax
0x180017caf  mov     rax, [rbp+37h+var_A8]
0x180017cb3  mov     [rbp+37h+var_98], r9
0x180017cb7  mov     [rbp+37h+var_90], 0
0x180017cbf  mov     [rbp+37h+var_88], r9d
0x180017cc3  test    r8, r8
0x180017cc6  jz      loc_180018030
0x180017ccc  mov     r14, [rbp+37h+var_80]
0x180017cd0  test    rax, rax
0x180017cd3  jnz     loc_180018002
0x180017cd9  mov     rax, [rbp+37h+arg_28]
0x180017cdd  mov     [rbp+37h+var_58], rax
0x180017ce1  mov     eax, [rbp+37h+arg_30]
0x180017ce4  mov     [rbp+37h+var_50], eax
0x180017ce7  mov     [rbp+37h+var_4C], 0
0x180017cef  nop
0x180017cf0  inc     rbx
0x180017cf3  cmp     word ptr [rsi+rbx*2], 0
0x180017cf8  jnz     short loc_180017CF0
0x180017cfa  mov     rax, [rbp+37h+var_68]
0x180017cfe  mov     rdx, rsi; unsigned __int16 *
0x180017d01  mov     [rsp+0F0h+var_B8], r9; unsigned __int16 *
0x180017d06  mov     [rbp+37h+var_44], ebx
0x180017d09  mov     rbx, [rbp+37h+var_70]
0x180017d0d  mov     [rsp+0F0h+var_C0], rbx; struct tagEXCEPINFO *
0x180017d12  mov     [rsp+0F0h+var_C8], r8; unsigned __int16 *
0x180017d17  mov     r8d, r15d; unsigned int
0x180017d1a  mov     [rbp+37h+var_40], ecx
0x180017d1d  mov     rcx, r14; this
0x180017d20  mov     [rbp+37h+var_3C], r9d
0x180017d24  lea     r9, [rbp+37h+var_58]; struct SRCINFO *
0x180017d28  mov     [rsp+0F0h+String2], rax; String2
0x180017d2d  call    ?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@0@Z; COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,ushort const *)
0x180017d32  mov     rsi, [rbp+37h+Block]
0x180017d36  mov     edi, eax
0x180017d38  mov     r13, [rbp+37h+var_60]
0x180017d3c  test    r15d, r15d
0x180017d3f  js      loc_180018052
0x180017d45  bt      r15d, 0Ah
0x180017d4a  jb      loc_18001806F
0x180017d50  test    rsi, rsi
0x180017d53  jnz     loc_1800180B8
0x180017d59  mov     rax, [rbp+37h+bstrString]
0x180017d5d  test    rax, rax
0x180017d60  jnz     loc_1800180C6
0x180017d66  mov     r15, [rsp+0F0h+arg_18]
0x180017d6e  mov     eax, edi
0x180017d70  mov     rcx, [rbp+37h+var_38]
0x180017d74  xor     rcx, rsp; StackCookie
0x180017d77  call    __security_check_cookie
0x180017d7c  add     rsp, 0C0h
0x180017d83  pop     r14
0x180017d85  pop     r13
0x180017d87  pop     r12
0x180017d89  pop     rdi
0x180017d8a  pop     rsi
0x180017d8b  pop     rbx
0x180017d8c  pop     rbp
0x180017d8d  retn
0x180017d8e  cmp     word ptr [r12], 0
0x180017d94  jz      loc_180017C1C
0x180017d9a  lea     rcx, [r14+118h]; this
0x180017da1  mov     rdx, r12; unsigned __int16 *
0x180017da4  call    ?Find@NamedItemList@@QEAAPEAUNamedItem@@PEBG@Z; NamedItemList::Find(ushort const *)
0x180017da9  mov     [rbp+37h+var_A8], rax
0x180017dad  test    rax, rax
0x180017db0  jnz     loc_180017E90
0x180017db6  mov     edi, 80070057h
0x180017dbb  jmp     short loc_180017D59
0x180017dbd  movaps  xmm0, xmmword ptr cs:zmmword_18007D260
0x180017dc4  movaps  xmm1, xmmword ptr cs:zmmword_18007D260+10h
0x180017dcb  movups  xmmword ptr [rdi], xmm0
0x180017dce  movaps  xmm0, xmmword ptr cs:zmmword_18007D260+20h
0x180017dd5  movups  xmmword ptr [rdi+10h], xmm1
0x180017dd9  movaps  xmm1, xmmword ptr cs:zmmword_18007D260+30h
0x180017de0  movups  xmmword ptr [rdi+20h], xmm0
0x180017de4  movups  xmmword ptr [rdi+30h], xmm1
0x180017de8  jmp     loc_180017BC5
0x180017ded  mov     eax, 8000FFFFh
0x180017df2  jmp     loc_180017D70
0x180017df7  mov     rcx, r13; pvarg
0x180017dfa  call    cs:__imp_VariantInit
0x180017e00  xor     r9d, r9d
0x180017e03  jmp     loc_180017BBC
0x180017e08  test    r15b, 1
0x180017e0c  jnz     loc_180017BDE
0x180017e12  mov     eax, [r14+9Ch]
0x180017e19  dec     eax
0x180017e1b  cmp     eax, 2
0x180017e1e  ja      loc_180017BDE
0x180017e24  jmp     loc_180017BD9
0x180017e29  mov     rdi, rbx
0x180017e2c  inc     rdi
0x180017e2f  cmp     word ptr [rsi+rdi*2], 0
0x180017e34  jnz     short loc_180017E2C
0x180017e36  mov     edx, edi; unsigned int
0x180017e38  mov     [rbp+37h+var_B0], edi
0x180017e3b  xor     ecx, ecx; unsigned __int16 *
0x180017e3d  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180017e42  mov     [rbp+37h+bstrString], rax
0x180017e46  test    edi, edi
0x180017e48  jz      short loc_180017E59
0x180017e4a  test    rax, rax
0x180017e4d  jnz     short loc_180017E59
0x180017e4f  mov     edi, 8007000Eh
0x180017e54  jmp     loc_180017D66
0x180017e59  lea     rcx, [rbp+37h+var_B0]
0x180017e5d  mov     r9d, edi; unsigned int
0x180017e60  mov     [rsp+0F0h+String2], rcx; unsigned int *
0x180017e65  mov     r8, rax; unsigned __int16 *
0x180017e68  mov     rcx, rsi; unsigned __int16 *
0x180017e6b  mov     edx, edi; unsigned int
0x180017e6d  call    ?DecodeScriptCore@@YAJPEBGKPEAGKPEAK@Z; DecodeScriptCore(ushort const *,ulong,ushort *,ulong,ulong *)
0x180017e72  mov     edi, eax
0x180017e74  test    eax, eax
0x180017e76  js      loc_180017D59
0x180017e7c  mov     ecx, [rbp+37h+var_B0]
0x180017e7f  xor     r9d, r9d
0x180017e82  mov     rsi, [rbp+37h+bstrString]
0x180017e86  mov     [rsi+rcx*2], r9w
0x180017e8b  jmp     loc_180017BF3
0x180017e90  mov     ecx, [rax+34h]
0x180017e93  xor     r9d, r9d
0x180017e96  mov     [rbp+37h+var_B0], ecx
0x180017e99  jmp     loc_180017C1C
0x180017e9e  mov     edi, r9d
0x180017ea1  mov     edx, edi; int
0x180017ea3  lea     rcx, [rbp+37h+var_98]; this
0x180017ea7  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017eac  test    eax, eax
0x180017eae  jz      short loc_180017EEF
0x180017eb0  mov     rcx, [rbp+37h+var_98]
0x180017eb4  mov     rdx, r14; Src
0x180017eb7  movsxd  r13, dword ptr [rbp+37h+var_90+4]
0x180017ebb  mov     [rbp+37h+Block], rcx
0x180017ebf  mov     r8d, edi
0x180017ec2  add     r8, r8; Size
0x180017ec5  lea     rcx, [rcx+r13*2]; void *
0x180017ec9  call    memcpy_0
0x180017ece  mov     r8, [rbp+37h+Block]
0x180017ed2  add     r13d, edi
0x180017ed5  mov     rax, [rbp+37h+var_A8]
0x180017ed9  xor     r9d, r9d
0x180017edc  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180017ee0  test    r8, r8
0x180017ee3  jz      short loc_180017F02
0x180017ee5  movsxd  rcx, r13d
0x180017ee8  mov     [r8+rcx*2], r9w
0x180017eed  jmp     short loc_180017F02
0x180017eef  mov     r8, [rbp+37h+var_98]
0x180017ef3  xor     r9d, r9d
0x180017ef6  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180017efa  mov     rax, [rbp+37h+var_A8]
0x180017efe  mov     [rbp+37h+Block], r8
0x180017f02  mov     ecx, [rbp+37h+var_B0]
0x180017f05  jmp     loc_180017C63
0x180017f0a  cmp     edx, dword ptr [rbp+37h+var_90]
0x180017f0d  jl      short loc_180017F2B
0x180017f0f  lea     rcx, [rbp+37h+var_98]; this
0x180017f13  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017f18  mov     r8, [rbp+37h+var_98]
0x180017f1c  xor     r9d, r9d
0x180017f1f  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180017f23  mov     [rbp+37h+Block], r8
0x180017f27  test    eax, eax
0x180017f29  jz      short loc_180017F5B
0x180017f2b  movsxd  rax, r13d
0x180017f2e  add     r13d, 3
0x180017f32  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180017f36  lea     rcx, [r8+rax*2]
0x180017f3a  mov     rax, qword ptr cs:asc_18007F6D8; " - "
0x180017f41  mov     [rcx], eax
0x180017f43  movzx   eax, word ptr cs:asc_18007F6D8+4; " "
0x180017f4a  mov     [rcx+4], ax
0x180017f4e  test    r8, r8
0x180017f51  jz      short loc_180017F5B
0x180017f53  movsxd  rcx, r13d
0x180017f56  mov     [r8+rcx*2], r9w
0x180017f5b  mov     rax, [rbp+37h+var_A8]
0x180017f5f  mov     ecx, [rbp+37h+var_B0]
0x180017f62  jmp     loc_180017C70
0x180017f67  mov     r8d, ebx; int
0x180017f6a  lea     rcx, [rbp+37h+var_98]; this
0x180017f6e  mov     rdx, r12; unsigned __int16 *
0x180017f71  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180017f76  mov     edx, 20h ; ' '; unsigned __int16
0x180017f7b  lea     rcx, [rbp+37h+var_98]; this
0x180017f7f  call    ?AppendCh@BuildString@@QEAAJG@Z; BuildString::AppendCh(ushort)
0x180017f84  mov     r8, [rbp+37h+var_98]
0x180017f88  xor     r9d, r9d
0x180017f8b  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180017f8f  mov     rax, [rbp+37h+var_A8]
0x180017f93  mov     ecx, [rbp+37h+var_B0]
0x180017f96  mov     [rbp+37h+Block], r8
0x180017f9a  jmp     loc_180017C79
0x180017f9f  cmp     edx, dword ptr [rbp+37h+var_90]
0x180017fa2  jl      short loc_180017FC3
0x180017fa4  lea     rcx, [rbp+37h+var_98]; this
0x180017fa8  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180017fad  mov     r8, [rbp+37h+var_98]
0x180017fb1  xor     r9d, r9d
0x180017fb4  mov     ecx, [rbp+37h+var_B0]
0x180017fb7  mov     [rbp+37h+Block], r8
0x180017fbb  test    eax, eax
0x180017fbd  jz      short loc_180017FF9
0x180017fbf  mov     r13d, dword ptr [rbp+37h+var_90+4]
0x180017fc3  movups  xmm0, xmmword ptr cs:aScriptBlock; "script block"
0x180017fca  movsxd  rax, r13d
0x180017fcd  add     r13d, 0Ch
0x180017fd1  mov     dword ptr [rbp+37h+var_90+4], r13d
0x180017fd5  movups  xmmword ptr [r8+rax*2], xmm0
0x180017fda  movsd   xmm1, qword ptr cs:aScriptBlock+10h; "lock"
0x180017fe2  movsd   qword ptr [r8+rax*2+10h], xmm1
0x180017fe9  test    r8, r8
0x180017fec  jz      short loc_180017FF9
0x180017fee  movsxd  rcx, r13d
  ... truncated ...
```
