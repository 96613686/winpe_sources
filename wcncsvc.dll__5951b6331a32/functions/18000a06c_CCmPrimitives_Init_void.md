# CCmPrimitives::Init(void)

- ea: `0x18000a06c`
- end: `0x18000a347`
- name: `?Init@CCmPrimitives@@QEAAJXZ`
- size: `731`
- prototype: `__int64 __fastcall(CCmPrimitives *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800075a4`

## callees

- `0x180004f2c`
- `0x180004fb8`
- `0x180005014`
- `0x18000a06c`
- `0x180053004`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18000a19d`
- `bcrypt!BCryptGetProperty` at `0x18000a19d`
- `bcrypt!BCryptSetProperty` at `0x18000a2cf`
- `bcrypt!BCryptSetProperty` at `0x18000a2cf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a0da`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a136`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a1e9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a232`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a27b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a0da`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a136`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a1e9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a232`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a27b`

## pseudocode

```c
__int64 __fastcall CCmPrimitives::Init(CCmPrimitives *this)
{
  const char *Indent; // rax
  __int64 v2; // r10
  NTSTATUS Property; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // r10
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // r10
  CCmPrimitives *pcbResult; // [rsp+40h] [rbp+8h] BYREF

  pcbResult = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v2 + 16), 11, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, Indent);
  }
  Property = BCryptOpenAlgorithmProvider(&CCmWcnCrypto::m_Primitives, L"RNG", L"Microsoft Primitive Provider", 0);
  if ( Property >= 0 )
  {
    Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", L"Microsoft Primitive Provider", 0);
    if ( Property >= 0 )
    {
      LODWORD(pcbResult) = 8;
      Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 8u, (ULONG *)&pcbResult, 0);
      if ( Property >= 0 )
      {
        Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 8u);
        if ( Property >= 0 )
        {
          Property = BCryptOpenAlgorithmProvider(&qword_1800756D0, L"DH", L"Microsoft Primitive Provider", 0);
          if ( Property >= 0 )
          {
            Property = BCryptOpenAlgorithmProvider(&qword_1800756D8, L"AES", L"Microsoft Primitive Provider", 0);
            if ( Property >= 0 )
            {
              Property = BCryptSetProperty(qword_1800756D8, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
              if ( Property >= 0 )
              {
                v4 = 0;
                goto LABEL_34;
              }
              v4 = Property | 0x10000000;
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v4;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_35;
              v6 = 18;
            }
            else
            {
              v4 = Property | 0x10000000;
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v4;
              if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_35;
              v6 = 17;
            }
          }
          else
          {
            v4 = Property | 0x10000000;
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return v4;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_35;
            v6 = 16;
          }
        }
        else
        {
          v4 = Property | 0x10000000;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v4;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_35;
          v6 = 15;
        }
      }
      else
      {
        v4 = Property | 0x10000000;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v4;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_35;
        v6 = 14;
      }
    }
    else
    {
      v4 = Property | 0x10000000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_35;
      v6 = 13;
    }
LABEL_8:
    WPP_SF_Dd(v5[2], v6, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, (unsigned int)Property, v4);
LABEL_34:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v4 = Property | 0x10000000;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 12;
    goto LABEL_8;
  }
LABEL_35:
  if ( v5 != &WPP_GLOBAL_Control && ((v4 & 0x80000000) != 0 || *((_BYTE *)v5 + 25) >= 6u) )
  {
    v7 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v8 + 16), 19, (unsigned int)WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids, v7, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18000a06c  mov     [rsp+arg_8], rbx
0x18000a071  mov     [rsp+arg_10], rsi
0x18000a076  mov     [rsp+arg_0], rcx
0x18000a07b  push    rdi
0x18000a07c  sub     rsp, 30h
0x18000a080  mov     r10, cs:WPP_GLOBAL_Control
0x18000a087  lea     rdi, WPP_GLOBAL_Control
0x18000a08e  lea     rsi, WPP_a14166c1862b3eee56055812cdd2e8c0_Traceguids
0x18000a095  cmp     r10, rdi
0x18000a098  jz      short loc_18000A0BF
0x18000a09a  cmp     byte ptr [r10+19h], 6
0x18000a09f  jb      short loc_18000A0BF
0x18000a0a1  mov     ecx, 1; int
0x18000a0a6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000a0ab  mov     rcx, [r10+10h]
0x18000a0af  mov     edx, 0Bh
0x18000a0b4  mov     r9, rax
0x18000a0b7  mov     r8, rsi
0x18000a0ba  call    WPP_SF_s
0x18000a0bf  lea     rbx, pszImplementation; "Microsoft Primitive Provider"
0x18000a0c6  xor     r9d, r9d; dwFlags
0x18000a0c9  mov     r8, rbx; pszImplementation
0x18000a0cc  lea     rdx, pszAlgId; "RNG"
0x18000a0d3  lea     rcx, ?m_Primitives@CCmWcnCrypto@@0VCCmPrimitives@@A; phAlgorithm
0x18000a0da  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a0e0  test    eax, eax
0x18000a0e2  jns     short loc_18000A122
0x18000a0e4  mov     ebx, eax
0x18000a0e6  bts     ebx, 1Ch
0x18000a0ea  mov     r10, cs:WPP_GLOBAL_Control
0x18000a0f1  cmp     r10, rdi
0x18000a0f4  jz      loc_18000A335
0x18000a0fa  cmp     byte ptr [r10+19h], 2
0x18000a0ff  jb      loc_18000A305
0x18000a105  mov     edx, 0Ch
0x18000a10a  mov     rcx, [r10+10h]
0x18000a10e  mov     r9d, eax
0x18000a111  mov     r8, rsi
0x18000a114  mov     dword ptr [rsp+38h+pcbResult], ebx
0x18000a118  call    WPP_SF_Dd
0x18000a11d  jmp     loc_18000A2FE
0x18000a122  xor     r9d, r9d; dwFlags
0x18000a125  lea     rdx, aSha256; "SHA256"
0x18000a12c  mov     r8, rbx; pszImplementation
0x18000a12f  lea     rcx, hObject; phAlgorithm
0x18000a136  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a13c  test    eax, eax
0x18000a13e  jns     short loc_18000A168
0x18000a140  mov     ebx, eax
0x18000a142  bts     ebx, 1Ch
0x18000a146  mov     r10, cs:WPP_GLOBAL_Control
0x18000a14d  cmp     r10, rdi
0x18000a150  jz      loc_18000A335
0x18000a156  cmp     byte ptr [r10+19h], 2
0x18000a15b  jb      loc_18000A305
0x18000a161  mov     edx, 0Dh
0x18000a166  jmp     short loc_18000A10A
0x18000a168  mov     rcx, cs:hObject; hObject
0x18000a16f  lea     rax, [rsp+38h+arg_0]
0x18000a174  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18000a17c  lea     r8, pbOutput; pbOutput
0x18000a183  mov     r9d, 8; cbOutput
0x18000a189  mov     [rsp+38h+pcbResult], rax; pcbResult
0x18000a18e  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000a195  mov     dword ptr [rsp+38h+arg_0], 8
0x18000a19d  call    cs:__imp_BCryptGetProperty
0x18000a1a3  test    eax, eax
0x18000a1a5  jns     short loc_18000A1D2
0x18000a1a7  mov     ebx, eax
0x18000a1a9  bts     ebx, 1Ch
0x18000a1ad  mov     r10, cs:WPP_GLOBAL_Control
0x18000a1b4  cmp     r10, rdi
0x18000a1b7  jz      loc_18000A335
0x18000a1bd  cmp     byte ptr [r10+19h], 2
0x18000a1c2  jb      loc_18000A305
0x18000a1c8  mov     edx, 0Eh
0x18000a1cd  jmp     loc_18000A10A
0x18000a1d2  mov     r9d, 8; dwFlags
0x18000a1d8  lea     rdx, aSha256; "SHA256"
0x18000a1df  mov     r8, rbx; pszImplementation
0x18000a1e2  lea     rcx, phAlgorithm; phAlgorithm
0x18000a1e9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a1ef  test    eax, eax
0x18000a1f1  jns     short loc_18000A21E
0x18000a1f3  mov     ebx, eax
0x18000a1f5  bts     ebx, 1Ch
0x18000a1f9  mov     r10, cs:WPP_GLOBAL_Control
0x18000a200  cmp     r10, rdi
0x18000a203  jz      loc_18000A335
0x18000a209  cmp     byte ptr [r10+19h], 2
0x18000a20e  jb      loc_18000A305
0x18000a214  mov     edx, 0Fh
0x18000a219  jmp     loc_18000A10A
0x18000a21e  xor     r9d, r9d; dwFlags
0x18000a221  lea     rdx, aDh; "DH"
0x18000a228  mov     r8, rbx; pszImplementation
0x18000a22b  lea     rcx, qword_1800756D0; phAlgorithm
0x18000a232  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a238  test    eax, eax
0x18000a23a  jns     short loc_18000A267
0x18000a23c  mov     ebx, eax
0x18000a23e  bts     ebx, 1Ch
0x18000a242  mov     r10, cs:WPP_GLOBAL_Control
0x18000a249  cmp     r10, rdi
0x18000a24c  jz      loc_18000A335
0x18000a252  cmp     byte ptr [r10+19h], 2
0x18000a257  jb      loc_18000A305
0x18000a25d  mov     edx, 10h
0x18000a262  jmp     loc_18000A10A
0x18000a267  xor     r9d, r9d; dwFlags
0x18000a26a  lea     rdx, aAes; "AES"
0x18000a271  mov     r8, rbx; pszImplementation
0x18000a274  lea     rcx, qword_1800756D8; phAlgorithm
0x18000a27b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a281  test    eax, eax
0x18000a283  jns     short loc_18000A2AC
0x18000a285  mov     ebx, eax
0x18000a287  bts     ebx, 1Ch
0x18000a28b  mov     r10, cs:WPP_GLOBAL_Control
0x18000a292  cmp     r10, rdi
0x18000a295  jz      loc_18000A335
0x18000a29b  cmp     byte ptr [r10+19h], 2
0x18000a2a0  jb      short loc_18000A305
0x18000a2a2  mov     edx, 11h
0x18000a2a7  jmp     loc_18000A10A
0x18000a2ac  mov     rcx, cs:qword_1800756D8; hObject
0x18000a2b3  lea     r8, pbInput; "ChainingModeCBC"
0x18000a2ba  mov     r9d, 20h ; ' '; cbInput
0x18000a2c0  mov     dword ptr [rsp+38h+pcbResult], 0; dwFlags
0x18000a2c8  lea     rdx, aChainingmode; "ChainingMode"
0x18000a2cf  call    cs:__imp_BCryptSetProperty
0x18000a2d5  test    eax, eax
0x18000a2d7  jns     short loc_18000A2FC
0x18000a2d9  mov     ebx, eax
0x18000a2db  bts     ebx, 1Ch
0x18000a2df  mov     r10, cs:WPP_GLOBAL_Control
0x18000a2e6  cmp     r10, rdi
0x18000a2e9  jz      short loc_18000A335
0x18000a2eb  cmp     byte ptr [r10+19h], 2
0x18000a2f0  jb      short loc_18000A305
0x18000a2f2  mov     edx, 12h
0x18000a2f7  jmp     loc_18000A10A
0x18000a2fc  xor     ebx, ebx
0x18000a2fe  mov     r10, cs:WPP_GLOBAL_Control
0x18000a305  cmp     r10, rdi
0x18000a308  jz      short loc_18000A335
0x18000a30a  test    ebx, ebx
0x18000a30c  js      short loc_18000A315
0x18000a30e  cmp     byte ptr [r10+19h], 6
0x18000a313  jb      short loc_18000A335
0x18000a315  or      ecx, 0FFFFFFFFh; int
0x18000a318  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000a31d  mov     rcx, [r10+10h]
0x18000a321  mov     edx, 13h
0x18000a326  mov     r9, rax
0x18000a329  mov     dword ptr [rsp+38h+pcbResult], ebx
0x18000a32d  mov     r8, rsi
0x18000a330  call    WPP_SF_sd
0x18000a335  mov     rsi, [rsp+38h+arg_10]
0x18000a33a  mov     eax, ebx
0x18000a33c  mov     rbx, [rsp+38h+arg_8]
0x18000a341  add     rsp, 30h
0x18000a345  pop     rdi
0x18000a346  retn
```
