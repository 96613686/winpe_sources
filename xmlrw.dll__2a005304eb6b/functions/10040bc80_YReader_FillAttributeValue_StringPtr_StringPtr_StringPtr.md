# YReader::FillAttributeValue(StringPtr *,StringPtr *,StringPtr *)

- ea: `0x10040bc80`
- end: `0x10040bfae`
- name: `?FillAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z`
- size: `814`
- prototype: `void __fastcall(YReader *this, struct StringPtr *, unsigned __int16 **, struct StringPtr *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x10040bb50`

## callees

- `0x100401780`
- `0x10040bb50`
- `0x10040bc80`
- `0x100417b10`

## pseudocode

```c
void __fastcall YReader::FillAttributeValue(
        YReader *this,
        struct StringPtr *a2,
        unsigned __int16 **a3,
        struct StringPtr *a4)
{
  unsigned __int16 *v5; // rbx
  __int64 v7; // r10
  unsigned __int16 *v9; // r11
  unsigned __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int16 v13; // cx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // r10
  __int64 v18; // r8
  unsigned __int16 *v19; // r9
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // ecx
  unsigned int v23; // r10d
  _WORD *v24; // r11
  int v25; // eax
  unsigned __int16 v26; // cx
  unsigned __int16 *v27; // rdx
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rax
  unsigned __int16 *v30; // [rsp+20h] [rbp-38h] BYREF
  int v31; // [rsp+28h] [rbp-30h]

  v5 = *a3;
  v7 = *(_QWORD *)a4;
  v9 = (unsigned __int16 *)(*(_QWORD *)a4 + 2LL * *((unsigned int *)a4 + 2));
  v10 = (unsigned __int64)&(*a3)[*((unsigned int *)a3 + 2)];
  if ( (unsigned __int64)*a3 < v10 )
  {
    v11 = 65530;
    v12 = 32;
    while ( 1 )
    {
      v13 = *v5;
      if ( *v5 != 38 )
      {
        if ( ((v13 - 9) & 0xFFFA) != 0 || v13 == 14 )
        {
          if ( v13 == 60 )
          {
            MXRRaiseException(-1072894426);
            __debugbreak();
          }
          *v9 = v13;
        }
        else
        {
          *v9 = 32;
        }
        ++v9;
        goto LABEL_47;
      }
      v14 = ++v5;
      if ( (unsigned __int64)v5 >= v10 )
      {
        MXRRaiseException(-1072894420);
        JUMPOUT(0x10040BFADLL);
      }
      if ( *v5 != 35 )
      {
        _mm_lfence();
        v26 = *v5;
        v27 = v5;
        v28 = *v5;
        v30 = v5;
        v31 = 0;
        if ( (*((_BYTE *)(&g_apCharTables)[v28 >> 8] + (unsigned __int8)v26) & 4) == 0 )
        {
          MXRRaiseException(-1072894420);
          __debugbreak();
        }
        while ( 1 )
        {
          if ( (unsigned __int64)++v5 >= v10 )
          {
LABEL_51:
            MXRRaiseException(-1072894430);
            __debugbreak();
          }
          v29 = *v5;
          if ( (_DWORD)v29 == 59 )
            break;
          if ( (*((_BYTE *)(&g_apCharTables)[v29 >> 8] + (unsigned __int8)v29) & 8) == 0 )
            goto LABEL_51;
        }
        *((_DWORD *)a4 + 2) = ((__int64)v9 - *(_QWORD *)a2) >> 1;
        v31 = v5 - v27;
        YReader::ExpandAttributeValue(this, a2, (struct StringPtr *)&v30, a4);
        v12 = 32;
        v11 = 65530;
        v9 = (unsigned __int16 *)(*(_QWORD *)a4 + 2LL * *((unsigned int *)a4 + 2));
        goto LABEL_47;
      }
      v15 = ++v5;
      while ( 1 )
      {
        if ( (unsigned __int64)v5 >= v10 )
        {
          MXRRaiseException(-1072894430);
          __debugbreak();
        }
        if ( *v5 == 59 )
          break;
        ++v5;
      }
      v16 = 0;
      v17 = v5 - v15;
      if ( *v15 == 120 )
      {
        v18 = (unsigned int)(v17 - 1);
        v19 = v14 + 2;
        if ( (_DWORD)v17 != 1 )
        {
          do
          {
            v12 = *v19++;
            v18 = (unsigned int)(v18 - 1);
            if ( (unsigned __int16)(v12 - 48) > 9u )
            {
              if ( (unsigned __int16)(v12 - 97) > 5u )
              {
                if ( (unsigned __int16)(v12 - 65) > 5u )
                {
                  v21 = -1072894425;
LABEL_54:
                  _mm_lfence();
                  MXRRaiseException(v21);
                  __debugbreak();
                }
                v20 = 16 * v16 - 55;
              }
              else
              {
                v20 = 16 * v16 - 87;
              }
            }
            else
            {
              v20 = 16 * v16 - 48;
            }
            v16 = (unsigned int)(v12 + v20);
            if ( (unsigned int)v16 > 0x10FFFF )
            {
              v21 = -1072894421;
              goto LABEL_54;
            }
          }
          while ( (_DWORD)v18 );
        }
        v21 = VerifyXmlChar(v16, v12, v18);
        if ( v21 )
        {
          if ( v21 < 0 )
            goto LABEL_54;
          goto LABEL_34;
        }
      }
      else
      {
        if ( (_DWORD)v17 )
        {
          LODWORD(v12) = v5 - v15;
          while ( 1 )
          {
            v11 = *v15++;
            v12 = (unsigned int)(v12 - 1);
            if ( (unsigned __int16)(v11 - 48) > 9u )
              break;
            v16 = (unsigned int)(v11 + 2 * (5 * v16 - 24));
            if ( (unsigned int)v16 > 0x10FFFF )
            {
              v25 = -1072894421;
              goto LABEL_57;
            }
            if ( !(_DWORD)v12 )
              goto LABEL_28;
          }
          v25 = -1072894424;
LABEL_57:
          _mm_lfence();
          MXRRaiseException(v25);
          __debugbreak();
        }
LABEL_28:
        v25 = VerifyXmlChar(v16, v12, v11);
        if ( v25 )
        {
          if ( v25 < 0 )
            goto LABEL_57;
          goto LABEL_34;
        }
      }
      if ( v22 <= 0xFFFF )
      {
        v23 = 1;
      }
      else
      {
        v23 = 2;
        v24[1] = v22 & 0x3FF | 0xDC00;
        LOWORD(v22) = (v22 >> 10) - 10304;
      }
      *v24 = v22;
LABEL_34:
      v12 = 32;
      v11 = 65530;
      v9 = &v24[v23];
LABEL_47:
      if ( (unsigned __int64)++v5 >= v10 )
      {
        v7 = *(_QWORD *)a4;
        break;
      }
    }
  }
  *((_DWORD *)a4 + 2) = ((__int64)v9 - v7) >> 1;
}

```

## disassembly

```asm
0x10040bc80  mov     [rsp+arg_0], rbx
0x10040bc85  mov     [rsp+arg_8], rbp
0x10040bc8a  mov     [rsp+arg_10], rsi
0x10040bc8f  push    rdi
0x10040bc90  push    r12
0x10040bc92  push    r13
0x10040bc94  push    r14
0x10040bc96  push    r15
0x10040bc98  sub     rsp, 30h
0x10040bc9c  mov     eax, [r9+8]
0x10040bca0  mov     rsi, r9
0x10040bca3  mov     rbx, [r8]
0x10040bca6  mov     rbp, rdx
0x10040bca9  mov     r10, [r9]
0x10040bcac  mov     r14, rcx
0x10040bcaf  lea     r11, [r10+rax*2]
0x10040bcb3  mov     eax, [r8+8]
0x10040bcb7  lea     rdi, [rbx+rax*2]
0x10040bcbb  cmp     rbx, rdi
0x10040bcbe  jnb     loc_10040BF22
0x10040bcc4  xor     r12d, r12d
0x10040bcc7  lea     r15, ?g_apCharTables@@3PAPEAEA; uchar * near * g_apCharTables
0x10040bcce  mov     r13d, 3FFh
0x10040bcd4  mov     r8d, 0FFFAh
0x10040bcda  lea     edx, [r12+20h]
0x10040bcdf  nop
0x10040bce0  movzx   ecx, word ptr [rbx]
0x10040bce3  cmp     cx, 26h ; '&'
0x10040bce7  jnz     loc_10040BEEF
0x10040bced  add     rbx, 2
0x10040bcf1  mov     rax, rbx
0x10040bcf4  cmp     rbx, rdi
0x10040bcf7  jnb     loc_10040BFA3
0x10040bcfd  cmp     word ptr [rbx], 23h ; '#'
0x10040bd01  jnz     loc_10040BE57
0x10040bd07  add     rbx, 2
0x10040bd0b  mov     r9, rbx
0x10040bd0e  xchg    ax, ax
0x10040bd10  cmp     rbx, rdi
0x10040bd13  jnb     loc_10040BF8D
0x10040bd19  cmp     word ptr [rbx], 3Bh ; ';'
0x10040bd1d  jz      short loc_10040BD25
0x10040bd1f  add     rbx, 2
0x10040bd23  jmp     short loc_10040BD10
0x10040bd25  mov     r10, rbx
0x10040bd28  mov     ecx, r12d
0x10040bd2b  sub     r10, r9
0x10040bd2e  sar     r10, 1
0x10040bd31  cmp     word ptr [r9], 78h ; 'x'
0x10040bd36  jnz     short loc_10040BDB7
0x10040bd38  lea     r8d, [r10-1]
0x10040bd3c  lea     r9, [rax+4]
0x10040bd40  test    r8d, r8d
0x10040bd43  jz      short loc_10040BDA3
0x10040bd45  nop     word ptr [rax+rax+00000000h]
0x10040bd50  movzx   edx, word ptr [r9]
0x10040bd54  lea     r9, [r9+2]
0x10040bd58  dec     r8d
0x10040bd5b  lea     eax, [rdx-30h]
0x10040bd5e  cmp     ax, 9
0x10040bd62  ja      short loc_10040BD6C
0x10040bd64  shl     ecx, 4
0x10040bd67  add     ecx, 0FFFFFFD0h
0x10040bd6a  jmp     short loc_10040BD90
0x10040bd6c  lea     eax, [rdx-61h]
0x10040bd6f  cmp     ax, 5
0x10040bd73  ja      short loc_10040BD7D
0x10040bd75  shl     ecx, 4
0x10040bd78  add     ecx, 0FFFFFFA9h
0x10040bd7b  jmp     short loc_10040BD90
0x10040bd7d  lea     eax, [rdx-41h]
0x10040bd80  cmp     ax, 5
0x10040bd84  ja      loc_10040BF66
0x10040bd8a  shl     ecx, 4
0x10040bd8d  add     ecx, 0FFFFFFC9h
0x10040bd90  add     ecx, edx
0x10040bd92  cmp     ecx, 10FFFFh
0x10040bd98  ja      loc_10040BF5F
0x10040bd9e  test    r8d, r8d
0x10040bda1  jnz     short loc_10040BD50
0x10040bda3  call    VerifyXmlChar
0x10040bda8  test    eax, eax
0x10040bdaa  jz      short loc_10040BDFB
0x10040bdac  js      loc_10040BF6B
0x10040bdb2  jmp     loc_10040BE40
0x10040bdb7  test    r10d, r10d
0x10040bdba  jz      short loc_10040BDF2
0x10040bdbc  mov     edx, r10d
0x10040bdbf  nop
0x10040bdc0  movzx   r8d, word ptr [r9]
0x10040bdc4  lea     r9, [r9+2]
0x10040bdc8  dec     edx
0x10040bdca  lea     eax, [r8-30h]
0x10040bdce  cmp     ax, 9
0x10040bdd2  ja      loc_10040BF7D
0x10040bdd8  lea     ecx, [rcx+rcx*4]
0x10040bddb  lea     ecx, [rcx-18h]
0x10040bdde  lea     ecx, [r8+rcx*2]
0x10040bde2  cmp     ecx, 10FFFFh
0x10040bde8  ja      loc_10040BF76
0x10040bdee  test    edx, edx
0x10040bdf0  jnz     short loc_10040BDC0
0x10040bdf2  call    VerifyXmlChar
0x10040bdf7  test    eax, eax
0x10040bdf9  jnz     short loc_10040BE3A
0x10040bdfb  cmp     ecx, 0FFFFh
0x10040be01  jbe     short loc_10040BE2E
0x10040be03  movzx   eax, cx
0x10040be06  mov     edx, 0DC00h
0x10040be0b  and     ax, r13w
0x10040be0f  shr     ecx, 0Ah
0x10040be12  or      ax, dx
0x10040be15  mov     r10d, 2
0x10040be1b  mov     [r11+2], ax
0x10040be20  mov     eax, 2840h
0x10040be25  sub     cx, ax
0x10040be28  mov     [r11], cx
0x10040be2c  jmp     short loc_10040BE40
0x10040be2e  mov     r10d, 1
0x10040be34  mov     [r11], cx
0x10040be38  jmp     short loc_10040BE40
0x10040be3a  js      loc_10040BF82
0x10040be40  mov     eax, r10d
0x10040be43  mov     edx, 20h ; ' '
0x10040be48  mov     r8d, 0FFFAh
0x10040be4e  lea     r11, [r11+rax*2]
0x10040be52  jmp     loc_10040BF12
0x10040be57  lfence
0x10040be5a  movzx   ecx, word ptr [rbx]
0x10040be5d  mov     rdx, rbx
0x10040be60  mov     eax, ecx
0x10040be62  mov     [rsp+58h+var_38], rbx
0x10040be67  shr     rax, 8
0x10040be6b  movzx   ecx, cl
0x10040be6e  mov     [rsp+58h+var_30], r12d
0x10040be73  mov     rax, [r15+rax*8]
0x10040be77  test    byte ptr [rcx+rax], 4
0x10040be7b  jz      loc_10040BF98
0x10040be81  add     rbx, 2
0x10040be85  cmp     rbx, rdi
0x10040be88  jnb     loc_10040BF54
0x10040be8e  movzx   eax, word ptr [rbx]
0x10040be91  cmp     eax, 3Bh ; ';'
0x10040be94  jz      short loc_10040BEAD
0x10040be96  movzx   ecx, al
0x10040be99  shr     rax, 8
0x10040be9d  mov     rax, [r15+rax*8]
0x10040bea1  test    byte ptr [rcx+rax], 8
0x10040bea5  jz      loc_10040BF54
0x10040beab  jmp     short loc_10040BE81
0x10040bead  sub     r11, [rbp+0]
0x10040beb1  lea     r8, [rsp+58h+var_38]; struct StringPtr *
0x10040beb6  sar     r11, 1
0x10040beb9  mov     rax, rbx
0x10040bebc  sub     rax, rdx
0x10040bebf  mov     [rsi+8], r11d
0x10040bec3  sar     rax, 1
0x10040bec6  mov     r9, rsi; struct StringPtr *
0x10040bec9  mov     rdx, rbp; struct StringPtr *
0x10040becc  mov     [rsp+58h+var_30], eax
0x10040bed0  mov     rcx, r14; this
0x10040bed3  call    ?ExpandAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z; YReader::ExpandAttributeValue(StringPtr *,StringPtr *,StringPtr *)
0x10040bed8  mov     ecx, [rsi+8]
0x10040bedb  mov     edx, 20h ; ' '
0x10040bee0  mov     rax, [rsi]
0x10040bee3  mov     r8d, 0FFFAh
0x10040bee9  lea     r11, [rax+rcx*2]
0x10040beed  jmp     short loc_10040BF12
0x10040beef  lea     eax, [rcx-9]
0x10040bef2  test    r8w, ax
0x10040bef6  jnz     short loc_10040BF04
0x10040bef8  cmp     cx, 0Eh
0x10040befc  jz      short loc_10040BF04
0x10040befe  mov     [r11], dx
0x10040bf02  jmp     short loc_10040BF0E
0x10040bf04  cmp     cx, 3Ch ; '<'
0x10040bf08  jz      short loc_10040BF49
0x10040bf0a  mov     [r11], cx
0x10040bf0e  add     r11, 2
0x10040bf12  add     rbx, 2
0x10040bf16  cmp     rbx, rdi
0x10040bf19  jb      loc_10040BCE0
0x10040bf1f  mov     r10, [rsi]
0x10040bf22  mov     rbx, [rsp+58h+arg_0]
0x10040bf27  sub     r11, r10
0x10040bf2a  mov     rbp, [rsp+58h+arg_8]
0x10040bf2f  sar     r11, 1
0x10040bf32  mov     [rsi+8], r11d
0x10040bf36  mov     rsi, [rsp+58h+arg_10]
0x10040bf3b  add     rsp, 30h
0x10040bf3f  pop     r15
0x10040bf41  pop     r14
0x10040bf43  pop     r13
0x10040bf45  pop     r12
0x10040bf47  pop     rdi
0x10040bf48  retn
0x10040bf49  mov     ecx, 0C00CEE26h; int
0x10040bf4e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bf53  int     3; Trap to Debugger
0x10040bf54  mov     ecx, 0C00CEE22h; int
0x10040bf59  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bf5e  int     3; Trap to Debugger
0x10040bf5f  mov     eax, 0C00CEE2Bh
0x10040bf64  jmp     short loc_10040BF6B
0x10040bf66  mov     eax, 0C00CEE27h
0x10040bf6b  lfence
0x10040bf6e  mov     ecx, eax; int
0x10040bf70  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bf75  int     3; Trap to Debugger
0x10040bf76  mov     eax, 0C00CEE2Bh
0x10040bf7b  jmp     short loc_10040BF82
0x10040bf7d  mov     eax, 0C00CEE28h
0x10040bf82  lfence
0x10040bf85  mov     ecx, eax; int
0x10040bf87  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bf8c  int     3; Trap to Debugger
0x10040bf8d  mov     ecx, 0C00CEE22h; int
0x10040bf92  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bf97  int     3; Trap to Debugger
0x10040bf98  mov     ecx, 0C00CEE2Ch; int
0x10040bf9d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bfa2  int     3; Trap to Debugger
0x10040bfa3  mov     ecx, 0C00CEE2Ch; int
0x10040bfa8  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
