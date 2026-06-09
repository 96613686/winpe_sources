# RfsCskvLexerGetToken

- ea: `0x14004f2a8`
- end: `0x14004f402`
- name: `RfsCskvLexerGetToken`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004f5b0`

## callees

- `0x14004ee7c`
- `0x14004ef0c`
- `0x14004f050`
- `0x14004f184`
- `0x14004f2a8`
- `0x14004f430`
- `0x14004f4c4`

## import_xrefs

- `ntoskrnl!iswdigit` at `0x14004f3b8`
- `ntoskrnl!iswdigit` at `0x14004f3b8`

## pseudocode

```c
__int64 __fastcall RfsCskvLexerGetToken(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rcx
  __int128 v6; // xmm0
  __int64 v7; // rdx
  wint_t i; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  a2[1] = 0;
  for ( i = 0; (unsigned __int8)RfsCskvLexerStreamPeekChar(a1, &i); RfsCskvLexerStreamGetChar(a1, &i) )
  {
    if ( i > 0x20u )
      break;
    v4 = 0x100002601LL;
    if ( !_bittest64(&v4, i) )
      break;
  }
  if ( !(unsigned __int8)RfsCskvLexerStreamPeekChar(a1, &i) )
  {
    *(_DWORD *)a2 = 0;
    return 0;
  }
  switch ( i )
  {
    case '\'':
    case '"':
      *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)(a1 + 32);
      return RfsCskvLexerGetString(a1, a2);
    case ',':
      RfsCskvLexerStreamGetChar(a1, &i);
      v6 = *(_OWORD *)RfsCskvCommaString;
      *(_DWORD *)a2 = 1;
LABEL_13:
      *(_OWORD *)((char *)a2 + 8) = v6;
      return 0;
    case '=':
      RfsCskvLexerStreamGetChar(a1, &i);
      v6 = *(_OWORD *)RfsCskvEqualsString;
      *(_DWORD *)a2 = 2;
      goto LABEL_13;
    default:
      if ( (unsigned __int16)(i - 65) <= 0x39u && (v7 = 0x3FFFFFF43FFFFFFLL, _bittest64(&v7, (unsigned int)i - 65)) )
      {
        return RfsCskvLexerGetIdentifier(a1, a2);
      }
      else if ( i == 45 || (unsigned __int16)(i - 48) <= 9u || iswdigit(i) )
      {
        return RfsCskvLexerGetNumber(a1, a2);
      }
      else
      {
        return RfsCskvLexerGetError(a1, a2);
      }
  }
}

```

## disassembly

```asm
0x14004f2a8  mov     [rsp+arg_8], rbx
0x14004f2ad  push    rdi
0x14004f2ae  sub     rsp, 20h
0x14004f2b2  xorps   xmm0, xmm0
0x14004f2b5  xor     eax, eax
0x14004f2b7  movups  xmmword ptr [rdx], xmm0
0x14004f2ba  mov     rbx, rdx
0x14004f2bd  mov     rdi, rcx
0x14004f2c0  movups  xmmword ptr [rdx+10h], xmm0
0x14004f2c4  mov     [rsp+28h+arg_0], ax
0x14004f2c9  jmp     short loc_14004F2F5
0x14004f2cb  cmp     [rsp+28h+arg_0], 20h ; ' '
0x14004f2d1  ja      short loc_14004F303
0x14004f2d3  movzx   eax, [rsp+28h+arg_0]
0x14004f2d8  mov     rcx, 100002601h
0x14004f2e2  bt      rcx, rax
0x14004f2e6  jnb     short loc_14004F303
0x14004f2e8  lea     rdx, [rsp+28h+arg_0]
0x14004f2ed  mov     rcx, rdi
0x14004f2f0  call    RfsCskvLexerStreamGetChar
0x14004f2f5  lea     rdx, [rsp+28h+arg_0]
0x14004f2fa  call    RfsCskvLexerStreamPeekChar
0x14004f2ff  test    al, al
0x14004f301  jnz     short loc_14004F2CB
0x14004f303  lea     rdx, [rsp+28h+arg_0]
0x14004f308  mov     rcx, rdi
0x14004f30b  call    RfsCskvLexerStreamPeekChar
0x14004f310  test    al, al
0x14004f312  jnz     short loc_14004F321
0x14004f314  mov     dword ptr [rbx], 0
0x14004f31a  xor     eax, eax
0x14004f31c  jmp     loc_14004F3F6
0x14004f321  movzx   ecx, [rsp+28h+arg_0]; C
0x14004f326  cmp     cx, 27h ; '''
0x14004f32a  jz      loc_14004F3E2
0x14004f330  cmp     cx, 22h ; '"'
0x14004f334  jz      loc_14004F3E2
0x14004f33a  cmp     cx, 2Ch ; ','
0x14004f33e  jnz     short loc_14004F361
0x14004f340  lea     rdx, [rsp+28h+arg_0]
0x14004f345  mov     rcx, rdi
0x14004f348  call    RfsCskvLexerStreamGetChar
0x14004f34d  movups  xmm0, xmmword ptr cs:RfsCskvCommaString
0x14004f354  mov     dword ptr [rbx], 1
0x14004f35a  movdqu  xmmword ptr [rbx+8], xmm0
0x14004f35f  jmp     short loc_14004F31A
0x14004f361  cmp     cx, 3Dh ; '='
0x14004f365  jnz     short loc_14004F383
0x14004f367  lea     rdx, [rsp+28h+arg_0]
0x14004f36c  mov     rcx, rdi
0x14004f36f  call    RfsCskvLexerStreamGetChar
0x14004f374  movups  xmm0, xmmword ptr cs:RfsCskvEqualsString
0x14004f37b  mov     dword ptr [rbx], 2
0x14004f381  jmp     short loc_14004F35A
0x14004f383  lea     eax, [rcx-41h]
0x14004f386  cmp     ax, 39h ; '9'
0x14004f38a  ja      short loc_14004F3A9
0x14004f38c  mov     rdx, 3FFFFFF43FFFFFFh
0x14004f396  bt      rdx, rax
0x14004f39a  jnb     short loc_14004F3A9
0x14004f39c  mov     rdx, rbx
0x14004f39f  mov     rcx, rdi
0x14004f3a2  call    RfsCskvLexerGetIdentifier
0x14004f3a7  jmp     short loc_14004F3F6
0x14004f3a9  cmp     cx, 2Dh ; '-'
0x14004f3ad  jz      short loc_14004F3D5
0x14004f3af  lea     eax, [rcx-30h]
0x14004f3b2  cmp     ax, 9
0x14004f3b6  jbe     short loc_14004F3D5
0x14004f3b8  call    cs:__imp_iswdigit
0x14004f3bf  nop     dword ptr [rax+rax+00h]
0x14004f3c4  test    eax, eax
0x14004f3c6  jnz     short loc_14004F3D5
0x14004f3c8  mov     rdx, rbx
0x14004f3cb  mov     rcx, rdi
0x14004f3ce  call    RfsCskvLexerGetError
0x14004f3d3  jmp     short loc_14004F3F6
0x14004f3d5  mov     rdx, rbx
0x14004f3d8  mov     rcx, rdi
0x14004f3db  call    RfsCskvLexerGetNumber
0x14004f3e0  jmp     short loc_14004F3F6
0x14004f3e2  movups  xmm0, xmmword ptr [rdi+20h]
0x14004f3e6  mov     rdx, rbx
0x14004f3e9  mov     rcx, rdi
0x14004f3ec  movdqu  xmmword ptr [rbx+8], xmm0
0x14004f3f1  call    RfsCskvLexerGetString
0x14004f3f6  mov     rbx, [rsp+28h+arg_8]
0x14004f3fb  add     rsp, 20h
0x14004f3ff  pop     rdi
0x14004f400  retn
```
