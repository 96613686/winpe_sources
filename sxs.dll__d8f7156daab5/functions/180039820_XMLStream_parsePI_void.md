# XMLStream::parsePI(void)

- ea: `0x180039820`
- end: `0x180039d88`
- name: `?parsePI@XMLStream@@AEAAJXZ`
- size: `1384`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a990`

## callees

- `0x180038100`
- `0x180038170`
- `0x1800389f8`
- `0x1800395e0`
- `0x180039770`
- `0x180039798`
- `0x180039820`
- `0x180039f20`
- `0x18003a160`
- `0x18003cae0`
- `0x18005336c`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800399b1`
- `ntdll!RtlCompareUnicodeString` at `0x1800399b1`

## pseudocode

```c
__int64 __fastcall XMLStream::parsePI(XMLStream *this)
{
  int v1; // eax
  __int64 result; // rax
  _DWORD *v4; // rdx
  int v5; // ecx
  int v6; // eax
  int v7; // r8d
  __int64 v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  int v11; // eax
  RawStack *v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rdx
  int v15; // ecx
  int v16; // eax
  int v17; // r8d
  unsigned __int16 v18; // cx
  unsigned __int16 *v19; // rdx
  int v20; // eax
  unsigned int v21; // r8d
  UNICODE_STRING String2; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF

  v1 = *((__int16 *)this + 4);
  if ( *((_WORD *)this + 4) )
  {
    if ( v1 == 10 )
    {
      v11 = *((_DWORD *)this + 8);
      v12 = (XMLStream *)((char *)this + 16);
      if ( v11 )
        v13 = *((_QWORD *)v12 + 1) + (unsigned int)(*(_DWORD *)v12 * (v11 - 1));
      else
        v13 = 0;
      if ( *((_BYTE *)this + 196) && !*((_BYTE *)this + 197) && *((_DWORD *)this + 20) != *(_DWORD *)(v13 + 24) )
        return 3222070619LL;
      *(_QWORD *)this = *(_QWORD *)v13;
      *((_WORD *)this + 4) = *(_WORD *)(v13 + 8);
      *((_QWORD *)this + 21) = *(_QWORD *)(v13 + 16);
      RawStack::_pop(v12);
      return BufferedStream::UnFreeze(*((BufferedStream **)this + 11));
    }
    if ( v1 == 7 )
    {
      result = BufferedStream::nextChar(
                 *((BufferedStream **)this + 11),
                 (unsigned __int16 *)this + 59,
                 (bool *)this + 126);
      if ( (_DWORD)result )
        return result;
      if ( ((*((_WORD *)this + 59) - 77) & 0xFFDF) == 0 )
      {
        *((_WORD *)this + 4) = 8;
LABEL_15:
        result = BufferedStream::nextChar(
                   *((BufferedStream **)this + 11),
                   (unsigned __int16 *)this + 59,
                   (bool *)this + 126);
        if ( (_DWORD)result )
          return result;
        if ( ((*((_WORD *)this + 59) - 76) & 0xFFDF) == 0 )
        {
          *((_WORD *)this + 4) = 9;
LABEL_18:
          result = BufferedStream::nextChar(
                     *((BufferedStream **)this + 11),
                     (unsigned __int16 *)this + 59,
                     (bool *)this + 126);
          if ( (_DWORD)result )
            return result;
          v8 = *((_QWORD *)this + 11);
          if ( *(_DWORD *)(v8 + 80) == *(_DWORD *)(v8 + 16) )
          {
            if ( *((_BYTE *)this + 159) )
              goto LABEL_24;
            v9 = *(_QWORD *)(v8 + 8);
            v10 = 0;
            if ( v9 )
              v10 = (WCHAR *)(v9 + 2LL * *(int *)(v8 + 28));
            *(_QWORD *)&String1.Length = 393222;
            String1.Buffer = L"xml";
            *(_QWORD *)&String2.Length = 393222;
            String2.Buffer = v10;
            if ( RtlCompareUnicodeString(&String1, &String2, 0) )
              return 3222070646LL;
LABEL_24:
            result = XMLStream::push(this, XMLStream::parseTable, 10);
            if ( (int)result >= 0 )
              *((_QWORD *)this + 21) = qword_1800707F0;
            return result;
          }
          if ( !(unsigned int)isNameChar(*((_WORD *)this + 59)) && *((_WORD *)this + 59) != 58 )
            return 3222070535LL;
        }
      }
      *((_WORD *)this + 4) = 11;
      return 0;
    }
    switch ( *((_WORD *)this + 4) )
    {
      case 1:
        goto LABEL_82;
      case 2:
        goto LABEL_85;
      case 3:
        if ( *((_WORD *)this + 59) == 63 )
        {
          result = BufferedStream::nextChar(
                     *((BufferedStream **)this + 11),
                     (unsigned __int16 *)this + 59,
                     (bool *)this + 126);
          if ( (_DWORD)result )
            return result;
          if ( *((_WORD *)this + 59) == 62 )
          {
            *((_WORD *)this + 4) = 6;
            return 0;
          }
          return 3222070538LL;
        }
        result = XMLStream::push(this, XMLStream::skipWhiteSpace, 4);
        if ( (int)result < 0 )
          return result;
        result = XMLStream::skipWhiteSpace(this);
        if ( (int)result < 0 )
          return result;
        *((_WORD *)this + 4) = 4;
LABEL_38:
        v14 = (_DWORD *)*((_QWORD *)this + 11);
        v15 = v14[4];
        v16 = v15 - 1;
        if ( v15 <= 0 )
          v16 = 0;
        v17 = v14[11];
        v14[7] = v16;
        if ( v17 != v15 )
        {
          v14[12] = v14[10];
          v14[13] = v17;
        }
        *((_WORD *)this + 4) = 5;
LABEL_53:
        while ( 2 )
        {
          if ( !*((_BYTE *)this + 126) )
          {
            v18 = *((_WORD *)this + 59);
            if ( v18 != 63 )
            {
              if ( !(unsigned int)isCharData(v18) )
                return 3222070554LL;
              result = BufferedStream::nextChar(*((BufferedStream **)this + 11), v19, (bool *)this + 126);
              if ( (_DWORD)result )
                return result;
              continue;
            }
            result = BufferedStream::nextChar(
                       *((BufferedStream **)this + 11),
                       (unsigned __int16 *)this + 59,
                       (bool *)this + 126);
            if ( (_DWORD)result )
              return result;
          }
          break;
        }
        *((_WORD *)this + 4) = 6;
LABEL_61:
        if ( *((_BYTE *)this + 126) )
          return 3222070621LL;
        if ( *((_WORD *)this + 59) != 62 )
        {
          *((_WORD *)this + 4) = 5;
          return 0;
        }
        result = BufferedStream::nextChar(
                   *((BufferedStream **)this + 11),
                   (unsigned __int16 *)this + 59,
                   (bool *)this + 126);
        if ( !(_DWORD)result )
        {
          *((_DWORD *)this + 27) = -2;
          *((_DWORD *)this + 26) = 64;
          result = XMLStream::pop(this, 1);
          if ( (int)result >= 0 )
            return BufferedStream::UnFreeze(*((BufferedStream **)this + 11));
        }
        return result;
      case 4:
        goto LABEL_38;
      case 5:
        goto LABEL_53;
      case 6:
        goto LABEL_61;
      case 8:
        goto LABEL_15;
      case 9:
        goto LABEL_18;
      case 0xB:
        if ( *((_WORD *)this + 59) == 58 )
        {
          result = BufferedStream::nextChar(
                     *((BufferedStream **)this + 11),
                     (unsigned __int16 *)this + 59,
                     (bool *)this + 126);
          if ( (_DWORD)result )
            return result;
        }
        *((_WORD *)this + 4) = 12;
LABEL_70:
        if ( !(unsigned int)isNameChar(*((_WORD *)this + 59)) )
        {
          *((_WORD *)this + 4) = 2;
          return 0;
        }
        result = XMLStream::push(this, XMLStream::parseName, 2);
        if ( (int)result >= 0 )
        {
          *((_WORD *)this + 4) = 1;
          v20 = XMLStream::parseName(this);
          v21 = 0;
          if ( v20 < 0 )
            v21 = v20;
          result = v21;
        }
        break;
      case 0xC:
        goto LABEL_70;
      default:
        return 3222070546LL;
    }
  }
  else
  {
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 59,
               (bool *)this + 126);
    if ( !(_DWORD)result )
    {
      result = BufferedStream::Freeze(*((BufferedStream **)this + 11));
      if ( (int)result >= 0 )
      {
        v4 = (_DWORD *)*((_QWORD *)this + 11);
        v5 = v4[4];
        v6 = v5 - 1;
        if ( v5 <= 0 )
          v6 = 0;
        v7 = v4[11];
        v4[7] = v6;
        if ( v7 != v5 )
        {
          v4[12] = v4[10];
          v4[13] = v7;
        }
        if ( ((*((_WORD *)this + 59) - 88) & 0xFFDF) == 0 )
        {
          *((_WORD *)this + 4) = 7;
          return 0;
        }
        *((_WORD *)this + 4) = 1;
LABEL_82:
        result = XMLStream::push(this, XMLStream::parseName, 2);
        if ( (int)result >= 0 )
        {
          result = XMLStream::parseName(this);
          if ( (int)result >= 0 )
          {
            *((_WORD *)this + 4) = 2;
LABEL_85:
            if ( *((_BYTE *)this + 126) )
              return 3222070621LL;
            if ( *((_WORD *)this + 59) != 63
              && *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) != *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
            {
              return 3222070533LL;
            }
            *((_DWORD *)this + 26) = 3;
            *((_WORD *)this + 4) = 3;
            return 0;
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
0x180039820  mov     [rsp+arg_8], rbx
0x180039825  mov     [rsp+arg_10], rsi
0x18003982a  push    rdi
0x18003982b  sub     rsp, 50h
0x18003982f  mov     rax, cs:__security_cookie
0x180039836  xor     rax, rsp
0x180039839  mov     [rsp+58h+var_18], rax
0x18003983e  movsx   eax, word ptr [rcx+8]
0x180039842  mov     rbx, rcx
0x180039845  test    eax, eax
0x180039847  jnz     loc_1800398D4
0x18003984d  lea     r8, [rcx+7Eh]; bool *
0x180039851  lea     rdx, [rcx+76h]; unsigned __int16 *
0x180039855  mov     rcx, [rcx+58h]; this
0x180039859  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x18003985e  test    eax, eax
0x180039860  jnz     short loc_1800398B6
0x180039862  mov     rcx, [rbx+58h]; this
0x180039866  call    ?Freeze@BufferedStream@@QEAAJXZ; BufferedStream::Freeze(void)
0x18003986b  test    eax, eax
0x18003986d  js      short loc_1800398B6
0x18003986f  mov     rdx, [rbx+58h]
0x180039873  xor     r8d, r8d
0x180039876  mov     ecx, [rdx+10h]
0x180039879  test    ecx, ecx
0x18003987b  lea     eax, [rcx-1]
0x18003987e  cmovle  eax, r8d
0x180039882  mov     r8d, [rdx+2Ch]
0x180039886  mov     [rdx+1Ch], eax
0x180039889  cmp     r8d, ecx
0x18003988c  jz      short loc_180039898
0x18003988e  mov     eax, [rdx+28h]
0x180039891  mov     [rdx+30h], eax
0x180039894  mov     [rdx+34h], r8d
0x180039898  movzx   eax, word ptr [rbx+76h]
0x18003989c  mov     edi, 0FFDFh
0x1800398a1  sub     ax, 58h ; 'X'
0x1800398a5  test    di, ax
0x1800398a8  jnz     loc_180039CF0
0x1800398ae  mov     word ptr [rbx+8], 7
0x1800398b4  xor     eax, eax
0x1800398b6  mov     rcx, [rsp+58h+var_18]
0x1800398bb  xor     rcx, rsp; StackCookie
0x1800398be  call    __security_check_cookie
0x1800398c3  mov     rbx, [rsp+58h+arg_8]
0x1800398c8  mov     rsi, [rsp+58h+arg_10]
0x1800398cd  add     rsp, 50h
0x1800398d1  pop     rdi
0x1800398d2  retn
0x1800398d4  cmp     eax, 0Ah
0x1800398d7  jz      loc_1800399F5
0x1800398dd  mov     edi, 0FFDFh
0x1800398e2  cmp     eax, 7
0x1800398e5  jz      loc_180039A4A
0x1800398eb  dec     eax; switch 12 cases
0x1800398ed  cmp     eax, 0Bh
0x1800398f0  ja      def_180039909; jumptable 0000000180039909 default case, cases 7,10
0x1800398f6  lea     rdx, __ImageBase
0x1800398fd  cdqe
0x1800398ff  mov     ecx, ds:(jpt_180039909 - 180000000h)[rdx+rax*4]
0x180039906  add     rcx, rdx
0x180039909  jmp     rcx; switch jump
0x18003990f  mov     rcx, [rbx+58h]; jumptable 0000000180039909 case 8
0x180039913  lea     r8, [rbx+7Eh]; bool *
0x180039917  lea     rdx, [rbx+76h]; unsigned __int16 *
0x18003991b  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039920  test    eax, eax
0x180039922  jnz     short loc_1800398B6
0x180039924  movzx   eax, word ptr [rbx+76h]
0x180039928  sub     ax, 4Ch ; 'L'
0x18003992c  test    di, ax
0x18003992f  jnz     loc_180039A8C
0x180039935  mov     word ptr [rbx+8], 9
0x18003993b  mov     rcx, [rbx+58h]; jumptable 0000000180039909 case 9
0x18003993f  lea     r8, [rbx+7Eh]; bool *
0x180039943  lea     rdx, [rbx+76h]; unsigned __int16 *
0x180039947  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x18003994c  test    eax, eax
0x18003994e  jnz     loc_1800398B6
0x180039954  mov     rcx, [rbx+58h]
0x180039958  mov     eax, [rcx+10h]
0x18003995b  cmp     [rcx+50h], eax
0x18003995e  jnz     loc_180039A7B
0x180039964  cmp     byte ptr [rbx+9Fh], 0
0x18003996b  jnz     short loc_1800399C5
0x18003996d  mov     rdx, [rcx+8]
0x180039971  xor     r8d, r8d; CaseInsensitive
0x180039974  mov     eax, r8d
0x180039977  test    rdx, rdx
0x18003997a  jz      short loc_180039984
0x18003997c  movsxd  rax, dword ptr [rcx+1Ch]
0x180039980  lea     rax, [rdx+rax*2]
0x180039984  lea     rcx, aXml; "xml"
0x18003998b  mov     qword ptr [rsp+58h+String1.Length], 60006h
0x180039994  mov     [rsp+58h+String1.Buffer], rcx
0x180039999  lea     rdx, [rsp+58h+String2]; String2
0x18003999e  lea     rcx, [rsp+58h+String1]; String1
0x1800399a3  mov     qword ptr [rsp+58h+String2.Length], 60006h
0x1800399ac  mov     [rsp+58h+String2.Buffer], rax
0x1800399b1  call    cs:__imp_RtlCompareUnicodeString
0x1800399b8  nop     dword ptr [rax+rax+00h]
0x1800399bd  test    eax, eax
0x1800399bf  jnz     loc_180039AA9
0x1800399c5  mov     r8d, 0Ah
0x1800399cb  lea     rdx, ?parseTable@XMLStream@@AEAAJXZ; XMLStream::parseTable(void)
0x1800399d2  mov     rcx, rbx
0x1800399d5  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x1800399da  test    eax, eax
0x1800399dc  js      loc_1800398B6
0x1800399e2  lea     rcx, qword_1800707F0
0x1800399e9  mov     [rbx+0A8h], rcx
0x1800399f0  jmp     loc_1800398B6
0x1800399f5  mov     eax, [rcx+20h]
0x1800399f8  add     rcx, 10h; this
0x1800399fc  test    eax, eax
0x1800399fe  jz      loc_180039A97
0x180039a04  lea     r8d, [rax-1]
0x180039a08  imul    r8d, [rcx]
0x180039a0c  add     r8, [rcx+8]
0x180039a10  cmp     byte ptr [rbx+0C4h], 0
0x180039a17  jnz     loc_180039CCC
0x180039a1d  mov     rax, [r8]
0x180039a20  mov     [rbx], rax
0x180039a23  movzx   eax, word ptr [r8+8]
0x180039a28  mov     [rbx+8], ax
0x180039a2c  mov     rax, [r8+10h]
0x180039a30  mov     [rbx+0A8h], rax
0x180039a37  call    ?_pop@RawStack@@IEAAPEADXZ; RawStack::_pop(void)
0x180039a3c  mov     rcx, [rbx+58h]; this
0x180039a40  call    ?UnFreeze@BufferedStream@@QEAAJXZ; BufferedStream::UnFreeze(void)
0x180039a45  jmp     loc_1800398B6
0x180039a4a  lea     r8, [rcx+7Eh]; bool *
0x180039a4e  lea     rdx, [rcx+76h]; unsigned __int16 *
0x180039a52  mov     rcx, [rcx+58h]; this
0x180039a56  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039a5b  test    eax, eax
0x180039a5d  jnz     loc_1800398B6
0x180039a63  movzx   eax, word ptr [rbx+76h]
0x180039a67  sub     ax, 4Dh ; 'M'
0x180039a6b  test    di, ax
0x180039a6e  jnz     short loc_180039A8C
0x180039a70  mov     word ptr [rbx+8], 8
0x180039a76  jmp     loc_18003990F; jumptable 0000000180039909 case 8
0x180039a7b  movzx   ecx, word ptr [rbx+76h]; unsigned __int16
0x180039a7f  call    ?isNameChar@@YAHG@Z; isNameChar(ushort)
0x180039a84  test    eax, eax
0x180039a86  jz      loc_180039CB7
0x180039a8c  mov     word ptr [rbx+8], 0Bh
0x180039a92  jmp     loc_1800398B4
0x180039a97  xor     r8d, r8d
0x180039a9a  jmp     loc_180039A10
0x180039a9f  mov     eax, 0C00CE512h; jumptable 0000000180039909 default case, cases 7,10
0x180039aa4  jmp     loc_1800398B6
0x180039aa9  mov     eax, 0C00CE576h
0x180039aae  jmp     loc_1800398B6
0x180039ab3  mov     rdx, [rbx+58h]; jumptable 0000000180039909 case 4
0x180039ab7  xor     r8d, r8d
0x180039aba  mov     ecx, [rdx+10h]
0x180039abd  test    ecx, ecx
0x180039abf  lea     eax, [rcx-1]
0x180039ac2  cmovle  eax, r8d
0x180039ac6  mov     r8d, [rdx+2Ch]
0x180039aca  mov     [rdx+1Ch], eax
0x180039acd  cmp     r8d, ecx
0x180039ad0  jz      short loc_180039ADC
0x180039ad2  mov     eax, [rdx+28h]
0x180039ad5  mov     [rdx+30h], eax
0x180039ad8  mov     [rdx+34h], r8d
0x180039adc  mov     edi, 5
0x180039ae1  mov     [rbx+8], di
0x180039ae5  jmp     loc_180039B7D
0x180039aea  mov     rcx, [rbx+58h]
0x180039aee  mov     eax, [rcx+10h]
0x180039af1  cmp     [rcx+50h], eax
0x180039af4  jz      loc_180039D3A
0x180039afa  mov     eax, 0C00CE505h
0x180039aff  jmp     loc_1800398B6
0x180039b04  cmp     word ptr [rbx+76h], 3Fh ; '?'; jumptable 0000000180039909 case 3
0x180039b09  jnz     short loc_180039B40
0x180039b0b  mov     rcx, [rbx+58h]; this
0x180039b0f  lea     r8, [rbx+7Eh]; bool *
0x180039b13  lea     rdx, [rbx+76h]; unsigned __int16 *
0x180039b17  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039b1c  test    eax, eax
0x180039b1e  jnz     loc_1800398B6
0x180039b24  cmp     word ptr [rbx+76h], 3Eh ; '>'
0x180039b29  jnz     short loc_180039B36
0x180039b2b  mov     word ptr [rbx+8], 6
0x180039b31  jmp     loc_1800398B4
0x180039b36  mov     eax, 0C00CE50Ah
0x180039b3b  jmp     loc_1800398B6
0x180039b40  mov     edi, 4
0x180039b45  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180039b4c  mov     r8d, edi
0x180039b4f  mov     rcx, rbx
0x180039b52  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180039b57  test    eax, eax
0x180039b59  js      loc_1800398B6
0x180039b5f  mov     rcx, rbx; this
0x180039b62  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180039b67  test    eax, eax
0x180039b69  js      loc_1800398B6
0x180039b6f  mov     [rbx+8], di
0x180039b73  jmp     loc_180039AB3; jumptable 0000000180039909 case 4
0x180039b78  mov     edi, 5; jumptable 0000000180039909 case 5
0x180039b7d  cmp     byte ptr [rbx+7Eh], 0
0x180039b81  jnz     short loc_180039BCF
0x180039b83  movzx   ecx, word ptr [rbx+76h]; unsigned __int16
0x180039b87  lea     rdx, [rbx+76h]; unsigned __int16 *
0x180039b8b  cmp     cx, 3Fh ; '?'
0x180039b8f  jz      short loc_180039BBA
0x180039b91  call    ?isCharData@@YAHG@Z; isCharData(ushort)
0x180039b96  test    eax, eax
0x180039b98  jz      short loc_180039BB0
0x180039b9a  mov     rcx, [rbx+58h]; this
0x180039b9e  lea     r8, [rbx+7Eh]; bool *
0x180039ba2  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039ba7  test    eax, eax
0x180039ba9  jz      short loc_180039B7D
0x180039bab  jmp     loc_1800398B6
0x180039bb0  mov     eax, 0C00CE51Ah
0x180039bb5  jmp     loc_1800398B6
0x180039bba  mov     rcx, [rbx+58h]; this
0x180039bbe  lea     r8, [rbx+7Eh]; bool *
0x180039bc2  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039bc7  test    eax, eax
0x180039bc9  jnz     loc_1800398B6
0x180039bcf  mov     word ptr [rbx+8], 6
0x180039bd5  jmp     short loc_180039BDC
0x180039bd7  mov     edi, 5; jumptable 0000000180039909 case 6
0x180039bdc  cmp     byte ptr [rbx+7Eh], 0
0x180039be0  lea     r8, [rbx+7Eh]; bool *
0x180039be4  jnz     loc_180039D4B
0x180039bea  cmp     word ptr [rbx+76h], 3Eh ; '>'
0x180039bef  lea     rdx, [rbx+76h]; unsigned __int16 *
0x180039bf3  jnz     short loc_180039C34
0x180039bf5  mov     rcx, [rbx+58h]; this
0x180039bf9  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039bfe  test    eax, eax
0x180039c00  jnz     loc_1800398B6
0x180039c06  mov     dl, 1; bool
0x180039c08  mov     dword ptr [rbx+6Ch], 0FFFFFFFEh
0x180039c0f  mov     rcx, rbx; this
0x180039c12  mov     dword ptr [rbx+68h], 40h ; '@'
0x180039c19  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x180039c1e  test    eax, eax
0x180039c20  js      loc_1800398B6
0x180039c26  mov     rcx, [rbx+58h]; this
0x180039c2a  call    ?UnFreeze@BufferedStream@@QEAAJXZ; BufferedStream::UnFreeze(void)
0x180039c2f  jmp     loc_1800398B6
0x180039c34  mov     [rbx+8], di
0x180039c38  jmp     loc_1800398B4
0x180039c3d  cmp     word ptr [rbx+76h], 3Ah ; ':'; jumptable 0000000180039909 case 11
0x180039c42  lea     rdx, [rbx+76h]; unsigned __int16 *
0x180039c46  jnz     short loc_180039C5D
0x180039c48  mov     rcx, [rbx+58h]; this
0x180039c4c  lea     r8, [rbx+7Eh]; bool *
0x180039c50  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180039c55  test    eax, eax
0x180039c57  jnz     loc_1800398B6
0x180039c5d  mov     word ptr [rbx+8], 0Ch
0x180039c63  movzx   ecx, word ptr [rbx+76h]; jumptable 0000000180039909 case 12
0x180039c67  call    ?isNameChar@@YAHG@Z; isNameChar(ushort)
0x180039c6c  test    eax, eax
0x180039c6e  jz      short loc_180039CAC
0x180039c70  mov     r8d, 2
0x180039c76  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180039c7d  mov     rcx, rbx
0x180039c80  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180039c85  test    eax, eax
0x180039c87  js      loc_1800398B6
0x180039c8d  mov     rcx, rbx; this
0x180039c90  mov     word ptr [rbx+8], 1
0x180039c96  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180039c9b  xor     r8d, r8d
0x180039c9e  test    eax, eax
0x180039ca0  cmovs   r8d, eax
0x180039ca4  mov     eax, r8d
0x180039ca7  jmp     loc_1800398B6
0x180039cac  mov     word ptr [rbx+8], 2
0x180039cb2  jmp     loc_1800398B4
0x180039cb7  cmp     word ptr [rbx+76h], 3Ah ; ':'
0x180039cbc  jz      loc_180039A8C
0x180039cc2  mov     eax, 0C00CE507h
0x180039cc7  jmp     loc_1800398B6
0x180039ccc  cmp     byte ptr [rbx+0C5h], 0
0x180039cd3  jnz     loc_180039A1D
0x180039cd9  mov     eax, [r8+18h]
0x180039cdd  cmp     [rbx+50h], eax
0x180039ce0  jz      loc_180039A1D
0x180039ce6  mov     eax, 0C00CE55Bh
0x180039ceb  jmp     loc_1800398B6
0x180039cf0  mov     word ptr [rbx+8], 1
0x180039cf6  mov     edi, 2; jumptable 0000000180039909 case 1
0x180039cfb  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180039d02  mov     r8d, edi
0x180039d05  mov     rcx, rbx
0x180039d08  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180039d0d  test    eax, eax
0x180039d0f  js      loc_1800398B6
  ... truncated ...
```
