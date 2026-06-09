# ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)

- ea: `0x18002e1ec`
- end: `0x18002e532`
- name: `?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z`
- size: `838`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002e538`

## callees

- `0x180002590`
- `0x180002ffa`
- `0x180003088`
- `0x1800030f4`
- `0x18000ee14`
- `0x18002e1ec`
- `0x18002eb04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e50b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e50b`

## pseudocode

```c
__int64 __fastcall ATL::EscapeXML(const unsigned __int16 *a1, int a2, unsigned __int16 *a3, int a4)
{
  int v6; // r15d
  const unsigned __int16 *v7; // r14
  unsigned int v8; // esi
  unsigned __int16 v9; // bp
  int v10; // edx
  int v11; // ecx
  unsigned __int16 v12; // ax
  size_t v13; // r8
  const wchar_t *v14; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  wchar_t Buffer[8]; // [rsp+20h] [rbp-58h] BYREF
  int v19; // [rsp+30h] [rbp-48h]

  v6 = a2;
  v7 = a1;
  if ( !a1 )
    ATL::AtlThrowImpl(-2147467259);
  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v10 = *v7;
      if ( v10 == 34 )
        break;
      switch ( *v7 )
      {
        case '&':
          if ( a3 && a4 > 4 )
          {
            v13 = 2LL * a4;
            if ( v13 < 0xA )
            {
              memset_0(a3, 0, v13);
              *(_DWORD *)_o__errno(v17, v16) = 34;
              invalid_parameter_noinfo();
              ATL::AtlThrowImpl(-2147024809);
            }
            *(_QWORD *)a3 = *(_QWORD *)L"&amp;";
            a3[4] = aAmp[4];
            a3 += 5;
          }
          v11 = 5;
          break;
        case '\'':
          goto LABEL_46;
        case '<':
        case '>':
          if ( a3 && a4 > 3 )
          {
            *a3 = 38;
            v12 = 108;
            if ( *v7 != 60 )
              v12 = 103;
            a3[1] = v12;
            *((_DWORD *)a3 + 1) = 3866740;
            a3 += 4;
          }
          v11 = 4;
          break;
        default:
          if ( (unsigned __int16)(v10 + 10240) <= 0x3FFu )
          {
            if ( v9 )
            {
              if ( a3 && a4 > 7 )
              {
                swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
                *(_OWORD *)a3 = *(_OWORD *)Buffer;
                a3 += 8;
                LOWORD(v10) = *v7;
              }
              v11 = 8;
            }
            else
            {
              v11 = 0;
            }
            v9 = v10;
            break;
          }
          if ( v9 )
          {
            if ( (unsigned __int16)(v10 + 9216) <= 0x3FFu )
            {
              if ( a3 && a4 > 9 )
              {
                swprintf_s(Buffer, 0xBu, L"&#x%06X;", v10 - 56613888 + (v9 << 10));
                *(_OWORD *)a3 = *(_OWORD *)Buffer;
                *((_DWORD *)a3 + 4) = v19;
                a3 += 10;
              }
              v11 = 10;
              v9 = 0;
              break;
            }
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
              a3 += 8;
            }
            v8 += 8;
            a4 -= 8;
            v9 = 0;
          }
          if ( (unsigned __int16)(*v7 - 32) > 0x5Eu )
          {
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", *v7);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
              a3 += 8;
            }
            v11 = 8;
          }
          else
          {
            if ( a3 && a4 > 0 )
              *a3++ = *v7;
            v11 = 1;
          }
          break;
      }
LABEL_52:
      a4 -= v11;
      v8 += v11;
      if ( !--v6 )
      {
        if ( v9 )
        {
          if ( (unsigned __int16)(v9 - 32) > 0x5Eu )
          {
            if ( a3 && a4 > 7 )
            {
              swprintf_s(Buffer, 9u, L"&#x%04X;", v9);
              *(_OWORD *)a3 = *(_OWORD *)Buffer;
            }
            a4 -= 8;
            v8 += 8;
          }
          else
          {
            if ( a3 && a4 > 0 )
              *a3 = v9;
            --a4;
            ++v8;
          }
        }
        goto LABEL_64;
      }
      ++v7;
    }
LABEL_46:
    if ( a3 && a4 > 5 )
    {
      v14 = L"&apos;";
      if ( v10 != 39 )
        v14 = (const wchar_t *)L"&quot;";
      ATL::Checked::memcpy_s(
        (ATL::Checked *)a3,
        (void *)(2LL * a4),
        (unsigned __int64)v14,
        (const void *)0xC,
        *(unsigned __int64 *)Buffer);
      a3 += 6;
    }
    v11 = 6;
    goto LABEL_52;
  }
LABEL_64:
  if ( a3 && a4 < 0 )
    return 0;
  return v8;
}

```

## disassembly

```asm
0x18002e1ec  push    rbx
0x18002e1ee  push    rbp
0x18002e1ef  push    rsi
0x18002e1f0  push    rdi
0x18002e1f1  push    r12
0x18002e1f3  push    r14
0x18002e1f5  push    r15
0x18002e1f7  sub     rsp, 40h
0x18002e1fb  mov     rax, cs:__security_cookie
0x18002e202  xor     rax, rsp
0x18002e205  mov     [rsp+78h+var_40], rax
0x18002e20a  mov     edi, r9d
0x18002e20d  mov     rbx, r8
0x18002e210  mov     r15d, edx
0x18002e213  mov     r14, rcx
0x18002e216  xor     r12d, r12d
0x18002e219  test    rcx, rcx
0x18002e21c  jz      loc_18002E527
0x18002e222  mov     esi, r12d
0x18002e225  mov     ebp, r12d
0x18002e228  test    edx, edx
0x18002e22a  jz      loc_18002E4D8
0x18002e230  mov     r8d, 3FFh
0x18002e236  movzx   edx, word ptr [r14]
0x18002e23a  mov     ecx, edx
0x18002e23c  sub     ecx, 22h ; '"'
0x18002e23f  jz      loc_18002E436
0x18002e245  sub     ecx, 4
0x18002e248  jz      loc_18002E3FA
0x18002e24e  sub     ecx, 1
0x18002e251  jz      loc_18002E436
0x18002e257  sub     ecx, 15h
0x18002e25a  jz      loc_18002E3C4
0x18002e260  cmp     ecx, 2
0x18002e263  jz      loc_18002E3C4
0x18002e269  mov     eax, 2800h
0x18002e26e  add     eax, edx
0x18002e270  cmp     ax, r8w
0x18002e274  ja      short loc_18002E2C2
0x18002e276  test    bp, bp
0x18002e279  jz      short loc_18002E2B7
0x18002e27b  test    rbx, rbx
0x18002e27e  jz      short loc_18002E2B0
0x18002e280  cmp     edi, 7
0x18002e283  jle     short loc_18002E2B0
0x18002e285  movzx   r9d, bp
0x18002e289  lea     r8, aX04x; "&#x%04X;"
0x18002e290  mov     edx, 9; BufferCount
0x18002e295  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18002e29a  call    swprintf_s
0x18002e29f  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x18002e2a4  movdqu  xmmword ptr [rbx], xmm0
0x18002e2a8  add     rbx, 10h
0x18002e2ac  movzx   edx, word ptr [r14]
0x18002e2b0  mov     ecx, 8
0x18002e2b5  jmp     short loc_18002E2BA
0x18002e2b7  mov     ecx, r12d
0x18002e2ba  movzx   ebp, dx
0x18002e2bd  jmp     loc_18002E472
0x18002e2c2  test    bp, bp
0x18002e2c5  jz      loc_18002E363
0x18002e2cb  mov     eax, 2400h
0x18002e2d0  add     eax, edx
0x18002e2d2  cmp     ax, r8w
0x18002e2d6  ja      short loc_18002E329
0x18002e2d8  test    rbx, rbx
0x18002e2db  jz      short loc_18002E31C
0x18002e2dd  cmp     edi, 9
0x18002e2e0  jle     short loc_18002E31C
0x18002e2e2  movzx   r9d, bp
0x18002e2e6  shl     r9d, 0Ah
0x18002e2ea  add     edx, 0FCA02400h
0x18002e2f0  add     r9d, edx
0x18002e2f3  lea     r8, aX06x; "&#x%06X;"
0x18002e2fa  mov     edx, 0Bh; BufferCount
0x18002e2ff  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18002e304  call    swprintf_s
0x18002e309  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x18002e30e  movups  xmmword ptr [rbx], xmm0
0x18002e311  mov     eax, [rsp+78h+var_48]
0x18002e315  mov     [rbx+10h], eax
0x18002e318  add     rbx, 14h
0x18002e31c  mov     ecx, 0Ah
0x18002e321  mov     ebp, r12d
0x18002e324  jmp     loc_18002E472
0x18002e329  test    rbx, rbx
0x18002e32c  jz      short loc_18002E35A
0x18002e32e  cmp     edi, 7
0x18002e331  jle     short loc_18002E35A
0x18002e333  movzx   r9d, bp
0x18002e337  lea     r8, aX04x; "&#x%04X;"
0x18002e33e  mov     edx, 9; BufferCount
0x18002e343  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18002e348  call    swprintf_s
0x18002e34d  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x18002e352  movdqu  xmmword ptr [rbx], xmm0
0x18002e356  add     rbx, 10h
0x18002e35a  add     esi, 8
0x18002e35d  sub     edi, 8
0x18002e360  mov     ebp, r12d
0x18002e363  movzx   ecx, word ptr [r14]
0x18002e367  lea     eax, [rcx-20h]
0x18002e36a  cmp     ax, 5Eh ; '^'
0x18002e36e  ja      short loc_18002E38A
0x18002e370  test    rbx, rbx
0x18002e373  jz      short loc_18002E380
0x18002e375  test    edi, edi
0x18002e377  jle     short loc_18002E380
0x18002e379  mov     [rbx], cx
0x18002e37c  add     rbx, 2
0x18002e380  mov     ecx, 1
0x18002e385  jmp     loc_18002E472
0x18002e38a  test    rbx, rbx
0x18002e38d  jz      short loc_18002E3BA
0x18002e38f  cmp     edi, 7
0x18002e392  jle     short loc_18002E3BA
0x18002e394  mov     r9d, ecx
0x18002e397  lea     r8, aX04x; "&#x%04X;"
0x18002e39e  mov     edx, 9; BufferCount
0x18002e3a3  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18002e3a8  call    swprintf_s
0x18002e3ad  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x18002e3b2  movdqu  xmmword ptr [rbx], xmm0
0x18002e3b6  add     rbx, 10h
0x18002e3ba  mov     ecx, 8
0x18002e3bf  jmp     loc_18002E472
0x18002e3c4  test    rbx, rbx
0x18002e3c7  jz      short loc_18002E3F3
0x18002e3c9  cmp     edi, 3
0x18002e3cc  jle     short loc_18002E3F3
0x18002e3ce  mov     word ptr [rbx], 26h ; '&'
0x18002e3d3  mov     eax, 6Ch ; 'l'
0x18002e3d8  lea     ecx, [rax-5]
0x18002e3db  cmp     word ptr [r14], 3Ch ; '<'
0x18002e3e0  cmovnz  ax, cx
0x18002e3e4  mov     [rbx+2], ax
0x18002e3e8  mov     dword ptr [rbx+4], 3B0074h
0x18002e3ef  add     rbx, 8
0x18002e3f3  mov     ecx, 4
0x18002e3f8  jmp     short loc_18002E472
0x18002e3fa  test    rbx, rbx
0x18002e3fd  jz      short loc_18002E42F
0x18002e3ff  cmp     edi, 4
0x18002e402  jle     short loc_18002E42F
0x18002e404  movsxd  r8, edi
0x18002e407  add     r8, r8; Size
0x18002e40a  cmp     r8, 0Ah
0x18002e40e  jb      loc_18002E501
0x18002e414  movsd   xmm0, qword ptr cs:aAmp; "&amp;"
0x18002e41c  movsd   qword ptr [rbx], xmm0
0x18002e420  movzx   eax, word ptr cs:aAmp+8; ";"
0x18002e427  mov     [rbx+8], ax
0x18002e42b  add     rbx, 0Ah
0x18002e42f  mov     ecx, 5
0x18002e434  jmp     short loc_18002E472
0x18002e436  test    rbx, rbx
0x18002e439  jz      short loc_18002E46D
0x18002e43b  cmp     edi, 5
0x18002e43e  jle     short loc_18002E46D
0x18002e440  lea     rax, aQuot; "&quot;"
0x18002e447  lea     r8, aApos; "&apos;"
0x18002e44e  cmp     edx, 27h ; '''
0x18002e451  cmovnz  r8, rax; unsigned __int64
0x18002e455  movsxd  rdx, edi
0x18002e458  add     rdx, rdx; void *
0x18002e45b  mov     r9d, 0Ch; void *
0x18002e461  mov     rcx, rbx; this
0x18002e464  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18002e469  add     rbx, 0Ch
0x18002e46d  mov     ecx, 6
0x18002e472  sub     edi, ecx
0x18002e474  add     esi, ecx
0x18002e476  sub     r15d, 1
0x18002e47a  jz      short loc_18002E485
0x18002e47c  add     r14, 2
0x18002e480  jmp     loc_18002E230
0x18002e485  test    bp, bp
0x18002e488  jz      short loc_18002E4D8
0x18002e48a  lea     eax, [rbp-20h]
0x18002e48d  cmp     ax, 5Eh ; '^'
0x18002e491  ja      short loc_18002E4A5
0x18002e493  test    rbx, rbx
0x18002e496  jz      short loc_18002E49F
0x18002e498  test    edi, edi
0x18002e49a  jle     short loc_18002E49F
0x18002e49c  mov     [rbx], bp
0x18002e49f  dec     edi
0x18002e4a1  inc     esi
0x18002e4a3  jmp     short loc_18002E4D8
0x18002e4a5  test    rbx, rbx
0x18002e4a8  jz      short loc_18002E4D2
0x18002e4aa  cmp     edi, 7
0x18002e4ad  jle     short loc_18002E4D2
0x18002e4af  movzx   r9d, bp
0x18002e4b3  lea     r8, aX04x; "&#x%04X;"
0x18002e4ba  mov     edx, 9; BufferCount
0x18002e4bf  lea     rcx, [rsp+78h+Buffer]; Buffer
0x18002e4c4  call    swprintf_s
0x18002e4c9  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x18002e4ce  movdqu  xmmword ptr [rbx], xmm0
0x18002e4d2  sub     edi, 8
0x18002e4d5  add     esi, 8
0x18002e4d8  test    rbx, rbx
0x18002e4db  jz      short loc_18002E4E3
0x18002e4dd  test    edi, edi
0x18002e4df  cmovs   esi, r12d
0x18002e4e3  mov     eax, esi
0x18002e4e5  mov     rcx, [rsp+78h+var_40]
0x18002e4ea  xor     rcx, rsp; StackCookie
0x18002e4ed  call    __security_check_cookie
0x18002e4f2  add     rsp, 40h
0x18002e4f6  pop     r15
0x18002e4f8  pop     r14
0x18002e4fa  pop     r12
0x18002e4fc  pop     rdi
0x18002e4fd  pop     rsi
0x18002e4fe  pop     rbp
0x18002e4ff  pop     rbx
0x18002e500  retn
0x18002e501  xor     edx, edx; Val
0x18002e503  mov     rcx, rbx; void *
0x18002e506  call    memset_0
0x18002e50b  call    cs:__imp__o__errno
0x18002e511  mov     dword ptr [rax], 22h ; '"'
0x18002e517  call    _invalid_parameter_noinfo
0x18002e51c  mov     ecx, 80070057h; int
0x18002e521  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002e527  mov     ecx, 80004005h; int
0x18002e52c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
