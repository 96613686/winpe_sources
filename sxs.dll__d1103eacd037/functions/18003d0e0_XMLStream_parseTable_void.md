# XMLStream::parseTable(void)

- ea: `0x18003d0e0`
- end: `0x18003da10`
- name: `?parseTable@XMLStream@@AEAAJXZ`
- size: `2352`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x1800395e0`
- `0x180039724`
- `0x180039770`
- `0x180039798`
- `0x18003a0a0`
- `0x18003a160`
- `0x18003c5f0`
- `0x18003cae0`
- `0x18003d0e0`
- `0x18003dbe0`
- `0x18003ddc4`
- `0x18003ded8`
- `0x1800698c0`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18003d395`
- `ntdll!RtlCompareUnicodeString` at `0x18003d395`

## string_xrefs

- `0x18003d6ff`: `SXS.DLL: XML Parser found either 0xfffe or 0xffff\n`

## pseudocode

```c
__int64 __fastcall XMLStream::parseTable(BufferedStream **this)
{
  int *v1; // rbx
  int v3; // esi
  __int64 v4; // r14
  unsigned int v5; // ebp
  BufferedStream *v6; // r8
  int v7; // edx
  int v8; // ecx
  int v9; // ecx
  BufferedStream *v10; // rsi
  int v11; // r9d
  __int64 v12; // rdx
  unsigned int v13; // r8d
  int v14; // edx
  __int64 result; // rax
  __int64 v16; // rcx
  int v17; // ecx
  __int64 v18; // rax
  char *v19; // rax
  BufferedStream *v20; // rcx
  WCHAR *v21; // r8
  __int64 v22; // rdx
  int v23; // edx
  int v24; // ecx
  WCHAR *v25; // rax
  BOOLEAN v26; // r8
  int v27; // eax
  __int16 v28; // ax
  BufferedStream *v29; // rbx
  int v30; // r9d
  __int64 v31; // rdx
  unsigned int v32; // r8d
  int v33; // edx
  BufferedStream *v34; // r8
  int v35; // edx
  int v36; // ecx
  int v37; // ecx
  BufferedStream *v38; // r8
  int v39; // edx
  int v40; // ecx
  int v41; // ecx
  BufferedStream *v42; // rbp
  int v43; // r9d
  __int64 v44; // rdx
  int v45; // edx
  int v46; // eax
  int v47; // eax
  char *v48; // rcx
  char *v49; // rax
  bool v50; // zf
  int v51; // eax
  char *v52; // rax
  BufferedStream *v53; // r9
  __int64 v54; // rdx
  BufferedStream *v55; // r8
  int v56; // edx
  int v57; // ecx
  int v58; // ecx
  int v59; // eax
  int v60; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-48h] BYREF

  v1 = (int *)(this + 13);
  v3 = 0;
  while ( 1 )
  {
    if ( v3 || (v1 = (int *)(this + 13), *((_DWORD *)this + 26)) )
    {
      if ( *v1 == 66 )
        return BufferedStream::UnFreeze(this[11]);
      else
        return 0;
    }
    v4 = (__int64)this[21] + 32 * *((__int16 *)this + 4);
    if ( *(_DWORD *)v4 != 3 )
      break;
LABEL_14:
    if ( *((_WORD *)this + 59) == **(_WORD **)(v4 + 8) )
    {
      v10 = this[11];
      v11 = *((_DWORD *)v10 + 8);
      if ( *((_DWORD *)v10 + 4) < v11 )
        goto LABEL_16;
      if ( *((_BYTE *)v10 + 60) )
        goto LABEL_150;
      if ( !*((_BYTE *)v10 + 61) && v11 > 0 )
      {
        v50 = *((_BYTE *)v10 + 62) == 0;
        *((_BYTE *)v10 + 61) = 1;
        v51 = v50 ? BufferedStream::getNewStart(v10) : 0;
        result = XMLStream::ErrorCallback(
                   *((XMLStream **)v10 + 12),
                   (unsigned int)(v51 + *((_DWORD *)v10 + 6) - v11 < 4097) - 1072896512);
        if ( (int)result < 0 )
          return result;
      }
      result = BufferedStream::fillBuffer(v10);
      if ( (int)result < 0 )
        return result;
      if ( *((_BYTE *)v10 + 60) )
      {
LABEL_150:
        *((_BYTE *)this + 126) = 1;
      }
      else
      {
        *((_BYTE *)v10 + 61) = 0;
LABEL_16:
        v12 = *((int *)v10 + 4);
        v13 = *(unsigned __int16 *)(*((_QWORD *)v10 + 1) + 2 * v12);
        v14 = v12 + 1;
        *((_DWORD *)v10 + 4) = v14;
        if ( v13 > 0x20 )
        {
LABEL_29:
          if ( v13 == 65534 || v13 == 0xFFFF )
          {
LABEL_105:
            FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found either 0xfffe or 0xffff\n");
            return 3222070536LL;
          }
        }
        else
        {
          if ( v13 == 32 || v13 == 9 )
            goto LABEL_25;
          if ( v13 == 10 || v13 == 13 )
          {
            if ( v13 == 13 || *((_WORD *)v10 + 18) != 13 )
              ++*((_DWORD *)v10 + 10);
            *((_DWORD *)v10 + 11) = v14;
            *((_WORD *)v10 + 18) = v13;
LABEL_25:
            *((_DWORD *)v10 + 20) = v14;
          }
        }
LABEL_31:
        *((_WORD *)this + 59) = v13;
      }
      v5 = *(_DWORD *)(v4 + 16);
      v3 = 0;
      *((_DWORD *)this + 26) = *(_DWORD *)(v4 + 24);
      goto LABEL_7;
    }
    v5 = *(_DWORD *)(v4 + 20);
    if ( v5 >= 0xC00CE500 && *((_DWORD *)this[11] + 20) == *((_DWORD *)this[11] + 4) )
      return 3222070547LL;
LABEL_7:
    if ( *this != (BufferedStream *)XMLStream::parseTable )
      return 0;
    if ( v5 >= 0xC00CE500 )
      return v5;
    *((_WORD *)this + 4) = v5;
  }
  v5 = *(_DWORD *)(v4 + 16);
  switch ( *(_DWORD *)v4 )
  {
    case 0:
      goto LABEL_38;
    case 1:
      if ( *((_DWORD *)this[11] + 20) != *((_DWORD *)this[11] + 4) )
        return 3222070537LL;
LABEL_38:
      v19 = RawStack::_push((RawStack *)(this + 2));
      if ( !v19 )
        return 2147942414LL;
      *((_WORD *)v19 + 4) = v5;
      *(_QWORD *)v19 = *this;
      *((_QWORD *)v19 + 2) = this[21];
      *((_DWORD *)v19 + 6) = *((_DWORD *)this + 20);
      *((_WORD *)this + 4) = 0;
      *this = (BufferedStream *)XMLStream::skipWhiteSpace;
      result = XMLStream::skipWhiteSpace((XMLStream *)this);
      v3 = result;
      if ( (int)result < 0 )
        return result;
      goto LABEL_7;
    case 2:
      v6 = this[11];
      v7 = *((_DWORD *)v6 + 4);
      v8 = v7 - 1;
      if ( v7 <= 0 )
        v8 = 0;
      *((_DWORD *)v6 + 7) = v8;
      v9 = *((_DWORD *)v6 + 11);
      if ( v9 != v7 )
      {
        *((_DWORD *)v6 + 12) = *((_DWORD *)v6 + 10);
        *((_DWORD *)v6 + 13) = v9;
      }
      goto LABEL_14;
    case 4:
      if ( *((_WORD *)this + 59) != **(_WORD **)(v4 + 8) )
        v5 = *(_DWORD *)(v4 + 20);
      goto LABEL_7;
    case 5:
      v52 = RawStack::_push((RawStack *)(this + 2));
      if ( !v52 )
        return 2147942414LL;
      *((_WORD *)v52 + 4) = v5;
      *(_QWORD *)v52 = *this;
      *((_QWORD *)v52 + 2) = this[21];
      *((_DWORD *)v52 + 6) = *((_DWORD *)this + 20);
      *((_WORD *)this + 4) = 0;
      *this = (BufferedStream *)XMLStream::parseName;
      result = XMLStream::parseName((XMLStream *)this);
      v3 = result;
      if ( (int)result >= 0 )
        goto LABEL_7;
      return result;
    case 6:
      *v1 = *(_DWORD *)(v4 + 20);
      *((_DWORD *)this + 27) = *(_DWORD *)(v4 + 24);
      goto LABEL_7;
    case 9:
      v20 = this[11];
      v21 = (WCHAR *)*((_QWORD *)v20 + 1);
      if ( v21 )
      {
        v22 = *((int *)v20 + 7);
        v21 += v22;
        v23 = *((_DWORD *)v20 + 4) + ~(_DWORD)v22;
      }
      else
      {
        LOWORD(v23) = 0;
      }
      v24 = *(_DWORD *)(v4 + 24);
      v25 = *(WCHAR **)(v4 + 8);
      *(_QWORD *)&String1.Length = 0;
      String1.Buffer = v25;
      String2 = 0;
      if ( v24 >= 0 )
        LOWORD(v24) = 0;
      String2.Buffer = v21;
      v26 = *((_BYTE *)this + 159);
      String1.Length = 2 * (v23 + v24);
      String1.MaximumLength = String1.Length;
      String2.Length = String1.Length;
      String2.MaximumLength = String1.Length;
      if ( RtlCompareUnicodeString(&String1, &String2, v26) )
        goto LABEL_91;
      v27 = *(_DWORD *)(v4 + 24);
      if ( v27 > 0 )
      {
        *v1 = v27;
        *((_DWORD *)this + 27) = 0;
      }
      v5 = *(_DWORD *)(v4 + 16);
      goto LABEL_7;
    case 0xA:
      v46 = *(_DWORD *)(v4 + 24);
      *((_DWORD *)this + 27) = v46;
      if ( !v46 )
      {
        v55 = this[11];
        v56 = *((_DWORD *)v55 + 4);
        v57 = v56 - 1;
        if ( v56 <= 0 )
          v57 = 0;
        *((_DWORD *)v55 + 7) = v57;
        v58 = *((_DWORD *)v55 + 11);
        if ( v58 != v56 )
        {
          *((_DWORD *)v55 + 12) = *((_DWORD *)v55 + 10);
          *((_DWORD *)v55 + 13) = v58;
        }
      }
      v47 = *((_DWORD *)this + 8);
      if ( v47 )
        v48 = (char *)this[3] + (unsigned int)(*((_DWORD *)this + 4) * (v47 - 1));
      else
        v48 = 0;
      if ( !*((_BYTE *)this + 196)
        || *((_BYTE *)this + 197)
        || *(_DWORD *)(v4 + 24)
        || *((_DWORD *)this + 20) == *((_DWORD *)v48 + 6) )
      {
        *this = *(BufferedStream **)v48;
        *((_WORD *)this + 4) = *((_WORD *)v48 + 4);
        this[21] = (BufferedStream *)*((_QWORD *)v48 + 2);
        RawStack::_pop((RawStack *)(this + 2));
        *v1 = *(_DWORD *)(v4 + 20);
        return 0;
      }
      return 3222070619LL;
    case 0x11:
      return XMLStream::push(this, XMLStream::parseComment, (unsigned __int16)v5);
    case 0x12:
      return XMLStream::push(this, XMLStream::parseCondSect, (unsigned __int16)v5);
    case 0x13:
      v16 = *((unsigned __int16 *)this + 59);
      if ( (unsigned __int16)v16 >= 0x80u )
        v17 = isCharAlphaW(v16);
      else
        v17 = *((_DWORD *)&dword_1800980F0 + v16) & 0x14;
      v18 = 16;
      if ( !v17 )
        v18 = 20;
      v5 = *(_DWORD *)(v18 + v4);
      goto LABEL_7;
    case 0x14:
      v49 = RawStack::_push((RawStack *)(this + 2));
      if ( !v49 )
        return 2147942414LL;
      *((_WORD *)v49 + 4) = v5;
      *(_QWORD *)v49 = *this;
      *((_QWORD *)v49 + 2) = this[21];
      *((_DWORD *)v49 + 6) = *((_DWORD *)this + 20);
      *((_WORD *)this + 4) = 0;
      *this = (BufferedStream *)XMLStream::parseEquals;
      result = XMLStream::parseEquals((XMLStream *)this);
      v3 = result;
      if ( (int)result >= 0 )
        goto LABEL_7;
      return result;
    case 0x15:
      v53 = this[11];
      v54 = *((_QWORD *)v53 + 1);
      if ( !v54 )
        return 2147500037LL;
      result = BufferedStream::switchEncoding(
                 this[11],
                 (const unsigned __int16 *)(v54 + 2LL * *((int *)v53 + 7)),
                 ~*((_DWORD *)v53 + 7) + *(_DWORD *)(v4 + 24) + *((_DWORD *)v53 + 4));
      v3 = result;
      if ( (int)result < 0 )
        return result;
      goto LABEL_7;
    case 0x16:
      v38 = this[11];
      v39 = *((_DWORD *)v38 + 4);
      v40 = v39 - 1;
      if ( v39 <= 0 )
        v40 = 0;
      *((_DWORD *)v38 + 7) = v40;
      v41 = *((_DWORD *)v38 + 11);
      if ( v41 != v39 )
      {
        *((_DWORD *)v38 + 12) = *((_DWORD *)v38 + 10);
        *((_DWORD *)v38 + 13) = v41;
      }
      v42 = this[11];
      if ( *((_WORD *)this + 59) != **(_WORD **)(v4 + 8) )
      {
        if ( *((_DWORD *)v42 + 20) != *((_DWORD *)v42 + 4) )
          return 3222070560LL;
LABEL_91:
        v5 = *(_DWORD *)(v4 + 20);
        goto LABEL_7;
      }
      v43 = *((_DWORD *)v42 + 8);
      if ( *((_DWORD *)v42 + 4) >= v43 )
      {
        if ( *((_BYTE *)v42 + 60) )
          goto LABEL_150;
        if ( !*((_BYTE *)v42 + 61) && v43 > 0 )
        {
          v50 = *((_BYTE *)v42 + 62) == 0;
          *((_BYTE *)v42 + 61) = 1;
          v60 = v50 ? BufferedStream::getNewStart(v42) : 0;
          result = XMLStream::ErrorCallback(
                     *((XMLStream **)v42 + 12),
                     (unsigned int)(v60 + *((_DWORD *)v42 + 6) - v43 < 4097) - 1072896512);
          if ( (int)result < 0 )
            return result;
        }
        result = BufferedStream::fillBuffer(v42);
        if ( (int)result < 0 )
          return result;
        if ( *((_BYTE *)v42 + 60) )
          goto LABEL_150;
        *((_BYTE *)v42 + 61) = 0;
      }
      v44 = *((int *)v42 + 4);
      v13 = *(unsigned __int16 *)(*((_QWORD *)v42 + 1) + 2 * v44);
      v45 = v44 + 1;
      *((_DWORD *)v42 + 4) = v45;
      if ( v13 > 0x20 )
        goto LABEL_29;
      if ( v13 == 32 || v13 == 9 )
        goto LABEL_77;
      if ( v13 == 10 || v13 == 13 )
      {
        if ( v13 == 13 || *((_WORD *)v42 + 18) != 13 )
          ++*((_DWORD *)v42 + 10);
        *((_DWORD *)v42 + 11) = v45;
        *((_WORD *)v42 + 18) = v13;
LABEL_77:
        *((_DWORD *)v42 + 20) = v45;
        goto LABEL_31;
      }
      goto LABEL_31;
    case 0x17:
      v28 = *((_WORD *)this + 59);
      if ( v28 != 34 && v28 != 39 )
        return 3222070530LL;
      v29 = this[11];
      *((_WORD *)this + 61) = v28;
      v30 = *((_DWORD *)v29 + 8);
      if ( *((_DWORD *)v29 + 4) < v30 )
        goto LABEL_51;
      if ( *((_BYTE *)v29 + 60) )
        goto LABEL_141;
      if ( !*((_BYTE *)v29 + 61) && v30 > 0 )
      {
        v50 = *((_BYTE *)v29 + 62) == 0;
        *((_BYTE *)v29 + 61) = 1;
        v59 = v50 ? BufferedStream::getNewStart(v29) : 0;
        result = XMLStream::ErrorCallback(
                   *((XMLStream **)v29 + 12),
                   (unsigned int)(v59 + *((_DWORD *)v29 + 6) - v30 < 4097) - 1072896512);
        if ( (int)result < 0 )
          return result;
      }
      result = BufferedStream::fillBuffer(v29);
      if ( (int)result < 0 )
        return result;
      if ( !*((_BYTE *)v29 + 60) )
      {
        *((_BYTE *)v29 + 61) = 0;
LABEL_51:
        v31 = *((int *)v29 + 4);
        v32 = *(unsigned __int16 *)(*((_QWORD *)v29 + 1) + 2 * v31);
        v33 = v31 + 1;
        *((_DWORD *)v29 + 4) = v33;
        if ( v32 > 0x20 )
        {
          if ( v32 - 65534 <= 1 )
            goto LABEL_105;
          goto LABEL_56;
        }
        if ( v32 != 32 && v32 != 9 )
        {
          if ( v32 != 10 && v32 != 13 )
            goto LABEL_56;
          if ( v32 == 13 || *((_WORD *)v29 + 18) != 13 )
            ++*((_DWORD *)v29 + 10);
          *((_DWORD *)v29 + 11) = v33;
          *((_WORD *)v29 + 18) = v32;
        }
        *((_DWORD *)v29 + 20) = v33;
LABEL_56:
        *((_WORD *)this + 59) = v32;
        goto LABEL_57;
      }
LABEL_141:
      *((_BYTE *)this + 126) = 1;
LABEL_57:
      v34 = this[11];
      v35 = *((_DWORD *)v34 + 4);
      v36 = v35 - 1;
      if ( v35 <= 0 )
        v36 = 0;
      *((_DWORD *)v34 + 7) = v36;
      v37 = *((_DWORD *)v34 + 11);
      if ( v37 != v35 )
      {
        *((_DWORD *)v34 + 12) = *((_DWORD *)v34 + 10);
        *((_DWORD *)v34 + 13) = v37;
      }
      *((_BYTE *)this + 198) = *(_DWORD *)(v4 + 20) == 1;
      result = XMLStream::push(this, XMLStream::parseAttrValue, (unsigned __int16)v5);
      break;
    default:
      goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x18003d0e0  mov     r11, rsp
0x18003d0e3  mov     [r11+20h], rbx
0x18003d0e7  push    rsi
0x18003d0e8  push    rdi
0x18003d0e9  push    r12
0x18003d0eb  push    r13
0x18003d0ed  push    r15
0x18003d0ef  sub     rsp, 50h
0x18003d0f3  mov     rax, cs:__security_cookie
0x18003d0fa  xor     rax, rsp
0x18003d0fd  mov     [rsp+78h+var_38], rax
0x18003d102  mov     [r11+10h], rbp
0x18003d106  lea     rbx, [rcx+68h]
0x18003d10a  mov     [r11+18h], r14
0x18003d10e  lea     r15, __ImageBase
0x18003d115  mov     rdi, rcx
0x18003d118  lea     r12, ?parseTable@XMLStream@@AEAAJXZ; XMLStream::parseTable(void)
0x18003d11f  xor     esi, esi
0x18003d121  mov     r13d, 80h
0x18003d127  test    esi, esi
0x18003d129  jnz     loc_18003D22C
0x18003d12f  cmp     [rdi+68h], esi
0x18003d132  lea     rbx, [rdi+68h]
0x18003d136  jnz     loc_18003D22C
0x18003d13c  movsx   r14, word ptr [rdi+8]
0x18003d141  shl     r14, 5
0x18003d145  add     r14, [rdi+0A8h]
0x18003d14c  movsxd  rax, dword ptr [r14]
0x18003d14f  cmp     eax, 3
0x18003d152  jz      short loc_18003D1C0
0x18003d154  mov     ebp, [r14+10h]
0x18003d158  cmp     eax, 17h; switch 24 cases
0x18003d15b  ja      short def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d15d  mov     ecx, ds:(jpt_18003D168 - 180000000h)[r15+rax*4]
0x18003d165  add     rcx, r15
0x18003d168  jmp     rcx; switch jump
0x18003d16e  mov     eax, [r14+14h]; jumptable 000000018003D168 case 6
0x18003d172  mov     [rbx], eax
0x18003d174  mov     eax, [r14+18h]
0x18003d178  mov     [rdi+6Ch], eax
0x18003d17b  cmp     [rdi], r12; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d17e  jnz     loc_18003D235
0x18003d184  cmp     ebp, 0C00CE500h
0x18003d18a  jnb     loc_18003D99B
0x18003d190  mov     [rdi+8], bp
0x18003d194  jmp     short loc_18003D127
0x18003d196  mov     r8, [rdi+58h]; jumptable 000000018003D168 case 2
0x18003d19a  xor     eax, eax
0x18003d19c  mov     edx, [r8+10h]
0x18003d1a0  test    edx, edx
0x18003d1a2  lea     ecx, [rdx-1]
0x18003d1a5  cmovle  ecx, eax
0x18003d1a8  mov     [r8+1Ch], ecx
0x18003d1ac  mov     ecx, [r8+2Ch]
0x18003d1b0  cmp     ecx, edx
0x18003d1b2  jz      short loc_18003D1C0
0x18003d1b4  mov     eax, [r8+28h]
0x18003d1b8  mov     [r8+30h], eax
0x18003d1bc  mov     [r8+34h], ecx
0x18003d1c0  mov     rax, [r14+8]
0x18003d1c4  movzx   ecx, word ptr [rax]
0x18003d1c7  cmp     [rdi+76h], cx
0x18003d1cb  jnz     loc_18003D522
0x18003d1d1  mov     rsi, [rdi+58h]
0x18003d1d5  mov     r9d, [rsi+20h]
0x18003d1d9  cmp     [rsi+10h], r9d
0x18003d1dd  jge     loc_18003D622
0x18003d1e3  movsxd  rdx, dword ptr [rsi+10h]
0x18003d1e7  mov     rax, [rsi+8]
0x18003d1eb  movzx   r8d, word ptr [rax+rdx*2]
0x18003d1f0  inc     edx
0x18003d1f2  mov     [rsi+10h], edx
0x18003d1f5  cmp     r8d, 20h ; ' '
0x18003d1f9  ja      short loc_18003D26A
0x18003d1fb  jz      short loc_18003D227
0x18003d1fd  mov     ecx, r8d
0x18003d200  sub     ecx, 9
0x18003d203  jz      short loc_18003D227
0x18003d205  sub     ecx, 1
0x18003d208  jz      short loc_18003D20F
0x18003d20a  cmp     ecx, 3
0x18003d20d  jnz     short loc_18003D282
0x18003d20f  cmp     r8d, 0Dh
0x18003d213  jz      short loc_18003D21C
0x18003d215  cmp     word ptr [rsi+24h], 0Dh
0x18003d21a  jz      short loc_18003D21F
0x18003d21c  inc     dword ptr [rsi+28h]
0x18003d21f  mov     [rsi+2Ch], edx
0x18003d222  mov     [rsi+24h], r8w
0x18003d227  mov     [rsi+50h], edx
0x18003d22a  jmp     short loc_18003D282
0x18003d22c  cmp     dword ptr [rbx], 42h ; 'B'
0x18003d22f  jz      loc_18003D9A2
0x18003d235  xor     eax, eax
0x18003d237  mov     r14, [rsp+78h+arg_10]
0x18003d23f  mov     rbp, [rsp+78h+arg_8]
0x18003d247  mov     rcx, [rsp+78h+var_38]
0x18003d24c  xor     rcx, rsp; StackCookie
0x18003d24f  call    __security_check_cookie
0x18003d254  mov     rbx, [rsp+78h+arg_18]
0x18003d25c  add     rsp, 50h
0x18003d260  pop     r15
0x18003d262  pop     r13
0x18003d264  pop     r12
0x18003d266  pop     rdi
0x18003d267  pop     rsi
0x18003d268  retn
0x18003d26a  mov     ecx, r8d
0x18003d26d  sub     ecx, 0FFFEh
0x18003d273  jz      loc_18003D6FF
0x18003d279  cmp     ecx, 1
0x18003d27c  jz      loc_18003D6FF
0x18003d282  mov     [rdi+76h], r8w
0x18003d287  mov     ebp, [r14+10h]
0x18003d28b  xor     esi, esi
0x18003d28d  mov     eax, [r14+18h]
0x18003d291  mov     [rdi+68h], eax
0x18003d294  jmp     def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d299  movzx   ecx, word ptr [rdi+76h]; jumptable 000000018003D168 case 19
0x18003d29d  cmp     cx, r13w
0x18003d2a1  jnb     loc_18003D920
0x18003d2a7  mov     ecx, rva dword_1800980F0[r15+rcx*4]
0x18003d2af  and     ecx, 14h
0x18003d2b2  test    ecx, ecx
0x18003d2b4  mov     eax, 10h
0x18003d2b9  mov     ecx, 14h
0x18003d2be  cmovz   eax, ecx
0x18003d2c1  mov     ebp, [rax+r14]
0x18003d2c5  jmp     def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d2ca  lea     rcx, [rdi+10h]; jumptable 000000018003D168 case 0
0x18003d2ce  call    ?_push@RawStack@@IEAAPEADXZ; RawStack::_push(void)
0x18003d2d3  mov     rcx, rax
0x18003d2d6  test    rax, rax
0x18003d2d9  jz      loc_18003D93A
0x18003d2df  mov     [rax+8], bp
0x18003d2e3  mov     rax, [rdi]
0x18003d2e6  mov     [rcx], rax
0x18003d2e9  mov     rax, [rdi+0A8h]
0x18003d2f0  mov     [rcx+10h], rax
0x18003d2f4  mov     eax, [rdi+50h]
0x18003d2f7  mov     [rcx+18h], eax
0x18003d2fa  xor     eax, eax
0x18003d2fc  mov     [rdi+8], ax
0x18003d300  mov     rcx, rdi; this
0x18003d303  lea     rax, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18003d30a  mov     [rdi], rax
0x18003d30d  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18003d312  mov     esi, eax
0x18003d314  test    eax, eax
0x18003d316  js      loc_18003D237
0x18003d31c  jmp     def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d321  mov     rcx, [rdi+58h]; jumptable 000000018003D168 case 9
0x18003d325  mov     r8, [rcx+8]
0x18003d329  test    r8, r8
0x18003d32c  jz      loc_18003D919
0x18003d332  movsxd  rdx, dword ptr [rcx+1Ch]
0x18003d336  lea     r8, [r8+rdx*2]
0x18003d33a  not     edx
0x18003d33c  add     edx, [rcx+10h]
0x18003d33f  mov     ecx, [r14+18h]
0x18003d343  xorps   xmm0, xmm0
0x18003d346  mov     rax, [r14+8]
0x18003d34a  xorps   xmm1, xmm1
0x18003d34d  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x18003d352  mov     [rsp+78h+String1.Buffer], rax
0x18003d357  xor     eax, eax
0x18003d359  test    ecx, ecx
0x18003d35b  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x18003d360  cmovns  cx, ax
0x18003d364  mov     [rsp+78h+String2.Buffer], r8
0x18003d369  movzx   r8d, byte ptr [rdi+9Fh]; CaseInsensitive
0x18003d371  add     cx, dx
0x18003d374  add     cx, cx
0x18003d377  lea     rdx, [rsp+78h+String2]; String2
0x18003d37c  mov     [rsp+78h+String1.Length], cx
0x18003d381  mov     [rsp+78h+String1.MaximumLength], cx
0x18003d386  mov     [rsp+78h+String2.Length], cx
0x18003d38b  mov     [rsp+78h+String2.MaximumLength], cx
0x18003d390  lea     rcx, [rsp+78h+String1]; String1
0x18003d395  call    cs:__imp_RtlCompareUnicodeString
0x18003d39c  nop     dword ptr [rax+rax+00h]
0x18003d3a1  test    eax, eax
0x18003d3a3  jnz     loc_18003D619
0x18003d3a9  mov     eax, [r14+18h]
0x18003d3ad  test    eax, eax
0x18003d3af  jle     short loc_18003D3BA
0x18003d3b1  mov     [rbx], eax
0x18003d3b3  mov     dword ptr [rdi+6Ch], 0
0x18003d3ba  mov     ebp, [r14+10h]
0x18003d3be  jmp     def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d3c3  movzx   eax, word ptr [rdi+76h]; jumptable 000000018003D168 case 23
0x18003d3c7  cmp     ax, 22h ; '"'
0x18003d3cb  jnz     loc_18003D8F0
0x18003d3d1  mov     rbx, [rdi+58h]
0x18003d3d5  mov     [rdi+7Ah], ax
0x18003d3d9  mov     r9d, [rbx+20h]
0x18003d3dd  cmp     [rbx+10h], r9d
0x18003d3e1  jge     loc_18003D7C3
0x18003d3e7  movsxd  rdx, dword ptr [rbx+10h]
0x18003d3eb  mov     rax, [rbx+8]
0x18003d3ef  movzx   r8d, word ptr [rax+rdx*2]
0x18003d3f4  inc     edx
0x18003d3f6  mov     [rbx+10h], edx
0x18003d3f9  mov     ecx, r8d
0x18003d3fc  cmp     r8d, 20h ; ' '
0x18003d400  ja      loc_18003D6EE
0x18003d406  jz      loc_18003D853
0x18003d40c  sub     ecx, 9
0x18003d40f  jz      loc_18003D853
0x18003d415  sub     ecx, 1
0x18003d418  jz      loc_18003D83B
0x18003d41e  cmp     ecx, 3
0x18003d421  jz      loc_18003D83B
0x18003d427  mov     [rdi+76h], r8w
0x18003d42c  mov     r8, [rdi+58h]
0x18003d430  xor     eax, eax
0x18003d432  mov     edx, [r8+10h]
0x18003d436  test    edx, edx
0x18003d438  lea     ecx, [rdx-1]
0x18003d43b  cmovle  ecx, eax
0x18003d43e  mov     [r8+1Ch], ecx
0x18003d442  mov     ecx, [r8+2Ch]
0x18003d446  cmp     ecx, edx
0x18003d448  jz      short loc_18003D456
0x18003d44a  mov     eax, [r8+28h]
0x18003d44e  mov     [r8+30h], eax
0x18003d452  mov     [r8+34h], ecx
0x18003d456  cmp     dword ptr [r14+14h], 1
0x18003d45b  jz      loc_18003D994
0x18003d461  xor     al, al
0x18003d463  movzx   r8d, bp
0x18003d467  mov     [rdi+0C6h], al
0x18003d46d  lea     rdx, ?parseAttrValue@XMLStream@@AEAAJXZ; XMLStream::parseAttrValue(void)
0x18003d474  mov     rcx, rdi
0x18003d477  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x18003d47c  jmp     loc_18003D237
0x18003d481  mov     r8, [rdi+58h]; jumptable 000000018003D168 case 22
0x18003d485  xor     eax, eax
0x18003d487  mov     edx, [r8+10h]
0x18003d48b  test    edx, edx
0x18003d48d  lea     ecx, [rdx-1]
0x18003d490  cmovle  ecx, eax
0x18003d493  mov     [r8+1Ch], ecx
0x18003d497  mov     ecx, [r8+2Ch]
0x18003d49b  cmp     ecx, edx
0x18003d49d  jz      short loc_18003D4AB
0x18003d49f  mov     eax, [r8+28h]
0x18003d4a3  mov     [r8+30h], eax
0x18003d4a7  mov     [r8+34h], ecx
0x18003d4ab  mov     rax, [r14+8]
0x18003d4af  mov     rbp, [rdi+58h]
0x18003d4b3  movzx   ecx, word ptr [rax]
0x18003d4b6  cmp     [rdi+76h], cx
0x18003d4ba  jnz     loc_18003D7AD
0x18003d4c0  mov     r9d, [rbp+20h]
0x18003d4c4  cmp     [rbp+10h], r9d
0x18003d4c8  jge     loc_18003D85B
0x18003d4ce  movsxd  rdx, dword ptr [rbp+10h]
0x18003d4d2  mov     rax, [rbp+8]
0x18003d4d6  movzx   r8d, word ptr [rax+rdx*2]
0x18003d4db  inc     edx
0x18003d4dd  mov     [rbp+10h], edx
0x18003d4e0  cmp     r8d, 20h ; ' '
0x18003d4e4  ja      loc_18003D26A
0x18003d4ea  jz      short loc_18003D51A
0x18003d4ec  mov     ecx, r8d
0x18003d4ef  sub     ecx, 9
0x18003d4f2  jz      short loc_18003D51A
0x18003d4f4  sub     ecx, 1
0x18003d4f7  jz      short loc_18003D502
0x18003d4f9  cmp     ecx, 3
0x18003d4fc  jnz     loc_18003D282
0x18003d502  cmp     r8d, 0Dh
0x18003d506  jz      short loc_18003D50F
0x18003d508  cmp     word ptr [rbp+24h], 0Dh
0x18003d50d  jz      short loc_18003D512
0x18003d50f  inc     dword ptr [rbp+28h]
0x18003d512  mov     [rbp+2Ch], edx
0x18003d515  mov     [rbp+24h], r8w
0x18003d51a  mov     [rbp+50h], edx
0x18003d51d  jmp     loc_18003D282
0x18003d522  mov     ebp, [r14+14h]
0x18003d526  cmp     ebp, 0C00CE500h
0x18003d52c  jb      def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d532  mov     rcx, [rdi+58h]
0x18003d536  mov     eax, [rcx+10h]
0x18003d539  cmp     [rcx+50h], eax
0x18003d53c  jnz     def_18003D168; jumptable 000000018003D168 default case, cases 3,7,8,11-16
0x18003d542  mov     eax, 0C00CE513h
0x18003d547  jmp     loc_18003D237
0x18003d54c  mov     rcx, [rdi+58h]; jumptable 000000018003D168 case 1
0x18003d550  mov     eax, [rcx+10h]
0x18003d553  cmp     [rcx+50h], eax
0x18003d556  jz      loc_18003D2CA; jumptable 000000018003D168 case 0
0x18003d55c  mov     eax, 0C00CE509h
0x18003d561  jmp     loc_18003D237
0x18003d566  mov     eax, [r14+18h]; jumptable 000000018003D168 case 10
0x18003d56a  mov     [rdi+6Ch], eax
0x18003d56d  test    eax, eax
0x18003d56f  jz      loc_18003D760
  ... truncated ...
```
