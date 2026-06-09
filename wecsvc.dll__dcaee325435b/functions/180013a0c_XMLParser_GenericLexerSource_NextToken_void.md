# XMLParser<GenericLexerSource>::NextToken(void)

- ea: `0x180013a0c`
- end: `0x180013d5a`
- name: `?NextToken@?$XMLParser@VGenericLexerSource@@@@QEAA?AW4XmlTokenType@@XZ`
- size: `846`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001351c`

## callees

- `0x18000195c`
- `0x180013310`
- `0x1800133f8`
- `0x180013794`
- `0x180013a0c`
- `0x180013d60`
- `0x18001fe1f`

## import_xrefs

- `msvcrt!iswspace` at `0x180013af2`
- `msvcrt!iswspace` at `0x180013af2`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::NextToken(__int64 a1)
{
  unsigned int v2; // edx
  unsigned int v3; // ebx
  wint_t *i; // rsi
  unsigned int v5; // edx
  int v7; // eax
  __int64 v8; // rsi
  unsigned int v9; // edx
  _BYTE pExceptionObject[64]; // [rsp+20h] [rbp-40h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF

  while ( 1 )
  {
    while ( 1 )
    {
      v12 = 0;
      if ( !(unsigned __int8)GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::NextToken(a1 + 64, &v12)
        || (v3 = v12) == 0 )
      {
        *(_DWORD *)(a1 + 360) = 2;
        wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
        throw (wmi::GenericException *)pExceptionObject;
      }
      if ( v12 > 8 )
        break;
      if ( v12 != 8 )
      {
        switch ( v12 )
        {
          case 1:
            v7 = *(_DWORD *)(a1 + 360);
            if ( v7 )
            {
              if ( v7 == 2 )
              {
                wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
                throw (wmi::GenericException *)pExceptionObject;
              }
            }
            else
            {
              *(_DWORD *)(a1 + 360) = 1;
            }
            ++*(_DWORD *)(a1 + 52);
            *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * *(int *)(a1 + 100)) = 0;
            XMLParser<GenericLexerSource>::OpenStartElementTag(a1, *(_QWORD *)(a1 + 88));
            goto LABEL_51;
          case 2:
            *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * *(int *)(a1 + 100)) = 0;
            XMLParser<GenericLexerSource>::EndElementTag(a1, *(_QWORD *)(a1 + 88));
            break;
          case 3:
            goto LABEL_51;
          case 4:
            --*(_DWORD *)(a1 + 44);
            break;
          case 5:
          case 6:
            goto LABEL_51;
          case 7:
            if ( *(_DWORD *)(a1 + 360) != 1 )
            {
              *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * *(int *)(a1 + 100)) = 0;
              for ( i = *(wint_t **)(a1 + 88); *i; ++i )
              {
                if ( !iswspace(*i) )
                {
                  wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v5);
                  throw (wmi::GenericException *)pExceptionObject;
                }
              }
            }
            goto LABEL_51;
          default:
            goto LABEL_55;
        }
        if ( (*(_DWORD *)(a1 + 52))-- == 1 )
          *(_DWORD *)(a1 + 360) = 2;
        goto LABEL_51;
      }
    }
    if ( v12 == 9 )
      break;
    if ( v12 == 11 )
    {
      if ( *(_DWORD *)(a1 + 360) != 1 )
      {
        wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
        throw (wmi::GenericException *)pExceptionObject;
      }
      *(_WORD *)(*(_QWORD *)(a1 + 88) + 2LL * *(int *)(a1 + 100)) = 0;
      v8 = *(_QWORD *)(a1 + 88);
      if ( (*(_WORD *)v8 != 103 || *(_WORD *)(v8 + 2) != 116 || *(_WORD *)(v8 + 4))
        && (*(_WORD *)v8 != 108 || *(_WORD *)(v8 + 2) != 116 || *(_WORD *)(v8 + 4))
        && wcscmp_0(*(const wchar_t **)(a1 + 88), L"amp")
        && wcscmp_0((const wchar_t *)v8, L"apos")
        && wcscmp_0((const wchar_t *)v8, L"quot") )
      {
        wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v9);
        throw (wmi::GenericException *)pExceptionObject;
      }
      goto LABEL_51;
    }
    if ( v12 == 12 )
    {
      if ( *(_DWORD *)(a1 + 360) != 1 )
      {
        wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
        throw (wmi::GenericException *)pExceptionObject;
      }
      goto LABEL_51;
    }
    if ( v12 != 13 && v12 != 14 )
    {
      if ( v12 == 15 )
      {
        if ( *(_DWORD *)(a1 + 360) != 2 )
        {
          wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
          throw (wmi::GenericException *)pExceptionObject;
        }
        goto LABEL_51;
      }
LABEL_55:
      wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
      throw (wmi::GenericException *)pExceptionObject;
    }
    if ( *(_DWORD *)(a1 + 360) == 1 )
      goto LABEL_51;
  }
  if ( *(_DWORD *)(a1 + 360) != 1 )
  {
    wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v2);
    throw (wmi::GenericException *)pExceptionObject;
  }
  v3 = 9;
LABEL_51:
  *(_DWORD *)(a1 + 48) = v3;
  return v3;
}

```

## disassembly

```asm
0x180013a0c  mov     [rsp-18h+arg_8], rbx
0x180013a11  mov     [rsp-18h+arg_10], rsi
0x180013a16  push    rbp
0x180013a17  push    rdi
0x180013a18  push    r14
0x180013a1a  mov     rbp, rsp
0x180013a1d  sub     rsp, 60h
0x180013a21  mov     rdi, rcx
0x180013a24  xor     r14d, r14d
0x180013a27  lea     rdx, [rbp+arg_0]
0x180013a2b  mov     [rbp+arg_0], r14d
0x180013a2f  lea     rcx, [rdi+40h]
0x180013a33  call    ?NextToken@?$GenericLexer@V?$XmlTokenizer@VGenericLexerSource@@@@VGenericLexerSource@@@@QEAA_NAEAK@Z; GenericLexer<XmlTokenizer<GenericLexerSource>,GenericLexerSource>::NextToken(ulong &)
0x180013a38  test    al, al
0x180013a3a  jz      loc_180013C66
0x180013a40  mov     ebx, [rbp+arg_0]
0x180013a43  test    ebx, ebx
0x180013a45  jz      loc_180013C66
0x180013a4b  cmp     ebx, 8
0x180013a4e  jg      short loc_180013AB2
0x180013a50  jz      short loc_180013A27
0x180013a52  mov     ecx, ebx
0x180013a54  sub     ecx, 1
0x180013a57  jz      loc_180013B48
0x180013a5d  sub     ecx, 1
0x180013a60  jz      loc_180013B2D
0x180013a66  sub     ecx, 1
0x180013a69  jz      loc_180013C4C
0x180013a6f  sub     ecx, 1
0x180013a72  jz      loc_180013B11
0x180013a78  sub     ecx, 1
0x180013a7b  jz      loc_180013C4C
0x180013a81  sub     ecx, 1
0x180013a84  jz      loc_180013C4C
0x180013a8a  cmp     ecx, 1
0x180013a8d  jnz     loc_180013CBE
0x180013a93  cmp     [rdi+168h], ecx
0x180013a99  jz      loc_180013C4C
0x180013a9f  movsxd  rdx, dword ptr [rdi+64h]
0x180013aa3  mov     rcx, [rdi+58h]
0x180013aa7  mov     [rcx+rdx*2], r14w
0x180013aac  mov     rsi, [rdi+58h]
0x180013ab0  jmp     short loc_180013B04
0x180013ab2  mov     ecx, ebx
0x180013ab4  sub     ecx, 9
0x180013ab7  jz      loc_180013C3A
0x180013abd  sub     ecx, 2
0x180013ac0  jz      loc_180013BB5
0x180013ac6  sub     ecx, 1
0x180013ac9  jz      loc_180013BA3
0x180013acf  sub     ecx, 1
0x180013ad2  jz      short loc_180013ADD
0x180013ad4  sub     ecx, 1
0x180013ad7  jnz     loc_180013B88
0x180013add  cmp     dword ptr [rdi+168h], 1
0x180013ae4  jnz     loc_180013A27
0x180013aea  jmp     loc_180013C4C
0x180013aef  movzx   ecx, ax; C
0x180013af2  call    cs:__imp_iswspace
0x180013af8  test    eax, eax
0x180013afa  jz      loc_180013C8A
0x180013b00  add     rsi, 2
0x180013b04  movzx   eax, word ptr [rsi]
0x180013b07  test    ax, ax
0x180013b0a  jnz     short loc_180013AEF
0x180013b0c  jmp     loc_180013C4C
0x180013b11  dec     dword ptr [rdi+2Ch]
0x180013b14  add     dword ptr [rdi+34h], 0FFFFFFFFh
0x180013b18  jnz     loc_180013C4C
0x180013b1e  mov     dword ptr [rdi+168h], 2
0x180013b28  jmp     loc_180013C4C
0x180013b2d  movsxd  rdx, dword ptr [rdi+64h]
0x180013b31  mov     rcx, [rdi+58h]
0x180013b35  mov     [rcx+rdx*2], r14w
0x180013b3a  mov     rcx, rdi
0x180013b3d  mov     rdx, [rdi+58h]
0x180013b41  call    ?EndElementTag@?$XMLParser@VGenericLexerSource@@@@AEAAXPEBG@Z; XMLParser<GenericLexerSource>::EndElementTag(ushort const *)
0x180013b46  jmp     short loc_180013B14
0x180013b48  mov     eax, [rdi+168h]
0x180013b4e  test    eax, eax
0x180013b50  jnz     short loc_180013B5E
0x180013b52  mov     dword ptr [rdi+168h], 1
0x180013b5c  jmp     short loc_180013B67
0x180013b5e  cmp     eax, 2
0x180013b61  jz      loc_180013CA4
0x180013b67  inc     dword ptr [rdi+34h]
0x180013b6a  movsxd  rdx, dword ptr [rdi+64h]
0x180013b6e  mov     rcx, [rdi+58h]
0x180013b72  mov     [rcx+rdx*2], r14w
0x180013b77  mov     rcx, rdi
0x180013b7a  mov     rdx, [rdi+58h]
0x180013b7e  call    ?OpenStartElementTag@?$XMLParser@VGenericLexerSource@@@@AEAAXPEBG@Z; XMLParser<GenericLexerSource>::OpenStartElementTag(ushort const *)
0x180013b83  jmp     loc_180013C4C
0x180013b88  cmp     ecx, 1
0x180013b8b  jnz     loc_180013CBE
0x180013b91  cmp     dword ptr [rdi+168h], 2
0x180013b98  jnz     loc_180013CD8
0x180013b9e  jmp     loc_180013C4C
0x180013ba3  cmp     dword ptr [rdi+168h], 1
0x180013baa  jnz     loc_180013CF2
0x180013bb0  jmp     loc_180013C4C
0x180013bb5  cmp     dword ptr [rdi+168h], 1
0x180013bbc  jnz     loc_180013D26
0x180013bc2  movsxd  rdx, dword ptr [rdi+64h]
0x180013bc6  mov     rcx, [rdi+58h]
0x180013bca  mov     [rcx+rdx*2], r14w
0x180013bcf  mov     rsi, [rdi+58h]
0x180013bd3  cmp     word ptr [rsi], 67h ; 'g'
0x180013bd7  jnz     short loc_180013BE7
0x180013bd9  cmp     word ptr [rsi+2], 74h ; 't'
0x180013bde  jnz     short loc_180013BE7
0x180013be0  cmp     [rsi+4], r14w
0x180013be5  jz      short loc_180013C4C
0x180013be7  cmp     word ptr [rsi], 6Ch ; 'l'
0x180013beb  jnz     short loc_180013BFB
0x180013bed  cmp     word ptr [rsi+2], 74h ; 't'
0x180013bf2  jnz     short loc_180013BFB
0x180013bf4  cmp     [rsi+4], r14w
0x180013bf9  jz      short loc_180013C4C
0x180013bfb  lea     rdx, aAmp; "amp"
0x180013c02  mov     rcx, rsi; String1
0x180013c05  call    wcscmp_0
0x180013c0a  test    eax, eax
0x180013c0c  jz      short loc_180013C4C
0x180013c0e  lea     rdx, aApos; "apos"
0x180013c15  mov     rcx, rsi; String1
0x180013c18  call    wcscmp_0
0x180013c1d  test    eax, eax
0x180013c1f  jz      short loc_180013C4C
0x180013c21  lea     rdx, aQuot; "quot"
0x180013c28  mov     rcx, rsi; String1
0x180013c2b  call    wcscmp_0
0x180013c30  test    eax, eax
0x180013c32  jnz     loc_180013D0C
0x180013c38  jmp     short loc_180013C4C
0x180013c3a  cmp     dword ptr [rdi+168h], 1
0x180013c41  jnz     loc_180013D40
0x180013c47  mov     ebx, 9
0x180013c4c  lea     r11, [rsp+60h+var_s0]
0x180013c51  mov     [rdi+30h], ebx
0x180013c54  mov     rsi, [r11+30h]
0x180013c58  mov     eax, ebx
0x180013c5a  mov     rbx, [r11+28h]
0x180013c5e  mov     rsp, r11
0x180013c61  pop     r14
0x180013c63  pop     rdi
0x180013c64  pop     rbp
0x180013c65  retn
0x180013c66  lea     rcx, [rbp+pExceptionObject]; this
0x180013c6a  mov     dword ptr [rdi+168h], 2
0x180013c74  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013c79  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013c80  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013c84  call    _CxxThrowException_0
0x180013c8a  lea     rcx, [rbp+pExceptionObject]; this
0x180013c8e  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013c93  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013c9a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013c9e  call    _CxxThrowException_0
0x180013ca4  lea     rcx, [rbp+pExceptionObject]; this
0x180013ca8  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013cad  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013cb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013cb8  call    _CxxThrowException_0
0x180013cbe  lea     rcx, [rbp+pExceptionObject]; this
0x180013cc2  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013cc7  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013cce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013cd2  call    _CxxThrowException_0
0x180013cd8  lea     rcx, [rbp+pExceptionObject]; this
0x180013cdc  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013ce1  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013ce8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013cec  call    _CxxThrowException_0
0x180013cf2  lea     rcx, [rbp+pExceptionObject]; this
0x180013cf6  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013cfb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013d02  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013d06  call    _CxxThrowException_0
0x180013d0c  lea     rcx, [rbp+pExceptionObject]; this
0x180013d10  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013d15  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013d1c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013d20  call    _CxxThrowException_0
0x180013d26  lea     rcx, [rbp+pExceptionObject]; this
0x180013d2a  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013d2f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013d36  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013d3a  call    _CxxThrowException_0
0x180013d40  lea     rcx, [rbp+pExceptionObject]; this
0x180013d44  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013d49  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180013d50  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013d54  call    _CxxThrowException_0
```
