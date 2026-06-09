# XMLEscapeW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180082484`
- end: `0x18008288b`
- name: `?XMLEscapeW@@YAJPEAG_KPEBG@Z`
- size: `1031`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056538`

## callees

- `0x18000c8f0`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800822a8`
- `0x180082484`

## string_xrefs

- `0x180082581`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180082600`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180082682`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180082704`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180082782`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`
- `0x180082814`: `onecoreuap\base\diagnosis\platform\notifications\prov\common\utilities.cpp`

## pseudocode

```c
__int64 __fastcall XMLEscapeW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, unsigned __int64 a4)
{
  PVOID v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  __int64 v10; // rsi
  const unsigned __int16 *v11; // r8
  int v12; // eax
  PVOID *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids);
  }
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v7 = 0;
  v8 = 126;
  v9 = a1;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (unsigned __int16 *)((char *)v9 + 1);
    --v8;
  }
  while ( v8 );
  v10 = 0;
  if ( !*a3 )
  {
LABEL_68:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_69:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 && *((_BYTE *)v13 + 25) >= 6u )
      WPP_SF_d(v13[2], 23, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, v7);
    return v7;
  }
  while ( 1 )
  {
    v11 = &a3[v10];
    if ( *v11 == 34 )
      break;
    switch ( *v11 )
    {
      case '&':
        v18 = StringCchCatW(a1, 0x7Eu, L"&amp;");
        v7 = v18;
        if ( v18 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
              (unsigned int)v18);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2C,
            (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
            (const char *)v7);
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_69;
          v14 = 12;
LABEL_67:
          WPP_SF_d(v13[2], v14, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, v7);
          goto LABEL_68;
        }
        break;
      case '\'':
        v17 = StringCchCatW(a1, 0x7Eu, L"&apos;");
        v7 = v17;
        if ( v17 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
              (unsigned int)v17);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x48,
            (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
            (const char *)v7);
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_69;
          v14 = 20;
          goto LABEL_67;
        }
        break;
      case '<':
        v16 = StringCchCatW(a1, 0x7Eu, L"&lt;");
        v7 = v16;
        if ( v16 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              15,
              WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
              (unsigned int)v16);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3A,
            (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
            (const char *)v7);
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_69;
          v14 = 16;
          goto LABEL_67;
        }
        break;
      case '>':
        v15 = StringCchCatW(a1, 0x7Eu, L"&gt;");
        v7 = v15;
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
              (unsigned int)v15);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41,
            (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
            (const char *)v7);
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_69;
          v14 = 18;
          goto LABEL_67;
        }
        break;
      default:
        v12 = StringCchCatNW(a1, 0x7Eu, v11, a4);
        v7 = v12;
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
              (unsigned int)v12);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4F,
            (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
            (const char *)v7);
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v7;
          if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_69;
          v14 = 22;
          goto LABEL_67;
        }
        break;
    }
LABEL_58:
    if ( !a3[++v10] )
      goto LABEL_68;
  }
  v19 = StringCchCatW(a1, 0x7Eu, L"&quot;");
  v7 = v19;
  if ( v19 >= 0 )
    goto LABEL_58;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
      (unsigned int)v19);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x33,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\common\\utilities.cpp",
    (const char *)v7);
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_69;
    v14 = 14;
    goto LABEL_67;
  }
  return v7;
}

```

## disassembly

```asm
0x180082484  push    rbx
0x180082486  push    rbp
0x180082487  push    rsi
0x180082488  push    rdi
0x180082489  push    r12
0x18008248b  push    r14
0x18008248d  push    r15; int
0x18008248f  sub     rsp, 20h
0x180082493  mov     r14, r8
0x180082496  mov     rdi, rcx
0x180082499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824a0  lea     rbp, WPP_GLOBAL_Control
0x1800824a7  lea     r15, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids
0x1800824ae  cmp     rcx, rbp
0x1800824b1  jz      short loc_1800824D0
0x1800824b3  test    byte ptr [rcx+1Ch], 20h
0x1800824b7  jz      short loc_1800824D0
0x1800824b9  cmp     byte ptr [rcx+19h], 6
0x1800824bd  jb      short loc_1800824D0
0x1800824bf  mov     rcx, [rcx+10h]
0x1800824c3  mov     edx, 0Ah
0x1800824c8  mov     r8, r15
0x1800824cb  call    WPP_SF_
0x1800824d0  xor     r12d, r12d
0x1800824d3  test    rdi, rdi
0x1800824d6  jnz     short loc_1800824DD
0x1800824d8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800824dd  test    r14, r14
0x1800824e0  jnz     short loc_1800824E7
0x1800824e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800824e7  mov     edx, 7Eh ; '~'; unsigned __int64
0x1800824ec  mov     ebx, r12d
0x1800824ef  mov     ecx, edx
0x1800824f1  mov     rax, rdi
0x1800824f4  mov     [rax], r12b
0x1800824f7  inc     rax
0x1800824fa  sub     rcx, 1
0x1800824fe  jnz     short loc_1800824F4
0x180082500  mov     rsi, r12
0x180082503  cmp     [r14], r12w
0x180082507  jz      loc_18008284E
0x18008250d  lea     r8, [r14+rsi*2]; unsigned __int16 *
0x180082511  movzx   ecx, word ptr [r8]
0x180082515  sub     ecx, 22h ; '"'
0x180082518  jz      loc_1800827BA
0x18008251e  sub     ecx, 4
0x180082521  jz      loc_18008273C
0x180082527  sub     ecx, 1
0x18008252a  jz      loc_1800826BA
0x180082530  sub     ecx, 15h
0x180082533  jz      loc_180082638
0x180082539  cmp     ecx, 2
0x18008253c  mov     rcx, rdi; unsigned __int16 *
0x18008253f  jz      short loc_1800825B9
0x180082541  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180082546  mov     ebx, eax
0x180082548  test    eax, eax
0x18008254a  jns     loc_1800827CF
0x180082550  mov     rcx, cs:WPP_GLOBAL_Control
0x180082557  cmp     rcx, rbp
0x18008255a  jz      short loc_18008257C
0x18008255c  test    byte ptr [rcx+1Ch], 20h
0x180082560  jz      short loc_18008257C
0x180082562  cmp     byte ptr [rcx+19h], 2
0x180082566  jb      short loc_18008257C
0x180082568  mov     rcx, [rcx+10h]
0x18008256c  mov     edx, 15h
0x180082571  mov     r9d, eax
0x180082574  mov     r8, r15
0x180082577  call    WPP_SF_d
0x18008257c  mov     rcx, [rsp+58h]; this
0x180082581  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082588  mov     r9d, ebx; char *
0x18008258b  mov     edx, 4Fh ; 'O'; void *
0x180082590  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082595  mov     rcx, cs:WPP_GLOBAL_Control
0x18008259c  cmp     rcx, rbp
0x18008259f  jz      loc_18008287A
0x1800825a5  test    byte ptr [rcx+1Ch], 80h
0x1800825a9  jz      loc_180082855
0x1800825af  mov     edx, 16h
0x1800825b4  jmp     loc_18008283F
0x1800825b9  lea     r8, aGt; "&gt;"
0x1800825c0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800825c5  mov     ebx, eax
0x1800825c7  test    eax, eax
0x1800825c9  jns     loc_1800827CF
0x1800825cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800825d6  cmp     rcx, rbp
0x1800825d9  jz      short loc_1800825FB
0x1800825db  test    byte ptr [rcx+1Ch], 20h
0x1800825df  jz      short loc_1800825FB
0x1800825e1  cmp     byte ptr [rcx+19h], 2
0x1800825e5  jb      short loc_1800825FB
0x1800825e7  mov     rcx, [rcx+10h]
0x1800825eb  mov     edx, 11h
0x1800825f0  mov     r9d, eax
0x1800825f3  mov     r8, r15
0x1800825f6  call    WPP_SF_d
0x1800825fb  mov     rcx, [rsp+58h]; this
0x180082600  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082607  mov     r9d, ebx; char *
0x18008260a  mov     edx, 41h ; 'A'; void *
0x18008260f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082614  mov     rcx, cs:WPP_GLOBAL_Control
0x18008261b  cmp     rcx, rbp
0x18008261e  jz      loc_18008287A
0x180082624  test    byte ptr [rcx+1Ch], 80h
0x180082628  jz      loc_180082855
0x18008262e  mov     edx, 12h
0x180082633  jmp     loc_18008283F
0x180082638  lea     r8, aLt; "&lt;"
0x18008263f  mov     rcx, rdi; unsigned __int16 *
0x180082642  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180082647  mov     ebx, eax
0x180082649  test    eax, eax
0x18008264b  jns     loc_1800827CF
0x180082651  mov     rcx, cs:WPP_GLOBAL_Control
0x180082658  cmp     rcx, rbp
0x18008265b  jz      short loc_18008267D
0x18008265d  test    byte ptr [rcx+1Ch], 20h
0x180082661  jz      short loc_18008267D
0x180082663  cmp     byte ptr [rcx+19h], 2
0x180082667  jb      short loc_18008267D
0x180082669  mov     rcx, [rcx+10h]
0x18008266d  mov     edx, 0Fh
0x180082672  mov     r9d, eax
0x180082675  mov     r8, r15
0x180082678  call    WPP_SF_d
0x18008267d  mov     rcx, [rsp+58h]; this
0x180082682  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082689  mov     r9d, ebx; char *
0x18008268c  mov     edx, 3Ah ; ':'; void *
0x180082691  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082696  mov     rcx, cs:WPP_GLOBAL_Control
0x18008269d  cmp     rcx, rbp
0x1800826a0  jz      loc_18008287A
0x1800826a6  test    byte ptr [rcx+1Ch], 80h
0x1800826aa  jz      loc_180082855
0x1800826b0  mov     edx, 10h
0x1800826b5  jmp     loc_18008283F
0x1800826ba  lea     r8, aApos; "&apos;"
0x1800826c1  mov     rcx, rdi; unsigned __int16 *
0x1800826c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800826c9  mov     ebx, eax
0x1800826cb  test    eax, eax
0x1800826cd  jns     loc_1800827CF
0x1800826d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800826da  cmp     rcx, rbp
0x1800826dd  jz      short loc_1800826FF
0x1800826df  test    byte ptr [rcx+1Ch], 20h
0x1800826e3  jz      short loc_1800826FF
0x1800826e5  cmp     byte ptr [rcx+19h], 2
0x1800826e9  jb      short loc_1800826FF
0x1800826eb  mov     rcx, [rcx+10h]
0x1800826ef  mov     edx, 13h
0x1800826f4  mov     r9d, eax
0x1800826f7  mov     r8, r15
0x1800826fa  call    WPP_SF_d
0x1800826ff  mov     rcx, [rsp+58h]; this
0x180082704  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008270b  mov     r9d, ebx; char *
0x18008270e  mov     edx, 48h ; 'H'; void *
0x180082713  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082718  mov     rcx, cs:WPP_GLOBAL_Control
0x18008271f  cmp     rcx, rbp
0x180082722  jz      loc_18008287A
0x180082728  test    byte ptr [rcx+1Ch], 80h
0x18008272c  jz      loc_180082855
0x180082732  mov     edx, 14h
0x180082737  jmp     loc_18008283F
0x18008273c  lea     r8, aAmp; "&amp;"
0x180082743  mov     rcx, rdi; unsigned __int16 *
0x180082746  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008274b  mov     ebx, eax
0x18008274d  test    eax, eax
0x18008274f  jns     short loc_1800827CF
0x180082751  mov     rcx, cs:WPP_GLOBAL_Control
0x180082758  cmp     rcx, rbp
0x18008275b  jz      short loc_18008277D
0x18008275d  test    byte ptr [rcx+1Ch], 20h
0x180082761  jz      short loc_18008277D
0x180082763  cmp     byte ptr [rcx+19h], 2
0x180082767  jb      short loc_18008277D
0x180082769  mov     rcx, [rcx+10h]
0x18008276d  mov     edx, 0Bh
0x180082772  mov     r9d, eax
0x180082775  mov     r8, r15
0x180082778  call    WPP_SF_d
0x18008277d  mov     rcx, [rsp+58h]; this
0x180082782  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180082789  mov     r9d, ebx; char *
0x18008278c  mov     edx, 2Ch ; ','; void *
0x180082791  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082796  mov     rcx, cs:WPP_GLOBAL_Control
0x18008279d  cmp     rcx, rbp
0x1800827a0  jz      loc_18008287A
0x1800827a6  test    byte ptr [rcx+1Ch], 80h
0x1800827aa  jz      loc_180082855
0x1800827b0  mov     edx, 0Ch
0x1800827b5  jmp     loc_18008283F
0x1800827ba  lea     r8, aQuot; "&quot;"
0x1800827c1  mov     rcx, rdi; unsigned __int16 *
0x1800827c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800827c9  mov     ebx, eax
0x1800827cb  test    eax, eax
0x1800827cd  js      short loc_1800827E3
0x1800827cf  inc     rsi
0x1800827d2  cmp     [r14+rsi*2], r12w
0x1800827d7  jz      short loc_18008284E
0x1800827d9  mov     edx, 7Eh ; '~'
0x1800827de  jmp     loc_18008250D
0x1800827e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800827ea  cmp     rcx, rbp
0x1800827ed  jz      short loc_18008280F
0x1800827ef  test    byte ptr [rcx+1Ch], 20h
0x1800827f3  jz      short loc_18008280F
0x1800827f5  cmp     byte ptr [rcx+19h], 2
0x1800827f9  jb      short loc_18008280F
0x1800827fb  mov     rcx, [rcx+10h]
0x1800827ff  mov     edx, 0Dh
0x180082804  mov     r9d, ebx
0x180082807  mov     r8, r15
0x18008280a  call    WPP_SF_d
0x18008280f  mov     rcx, [rsp+58h]; this
0x180082814  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008281b  mov     r9d, ebx; char *
0x18008281e  mov     edx, 33h ; '3'; void *
0x180082823  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082828  mov     rcx, cs:WPP_GLOBAL_Control
0x18008282f  cmp     rcx, rbp
0x180082832  jz      short loc_18008287A
0x180082834  test    byte ptr [rcx+1Ch], 80h
0x180082838  jz      short loc_180082855
0x18008283a  mov     edx, 0Eh
0x18008283f  mov     rcx, [rcx+10h]
0x180082843  mov     r9d, ebx
0x180082846  mov     r8, r15
0x180082849  call    WPP_SF_d
0x18008284e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082855  cmp     rcx, rbp
0x180082858  jz      short loc_18008287A
0x18008285a  test    byte ptr [rcx+1Ch], 20h
0x18008285e  jz      short loc_18008287A
0x180082860  cmp     byte ptr [rcx+19h], 6
0x180082864  jb      short loc_18008287A
0x180082866  mov     rcx, [rcx+10h]
0x18008286a  mov     edx, 17h
0x18008286f  mov     r9d, ebx
0x180082872  mov     r8, r15
0x180082875  call    WPP_SF_d
0x18008287a  mov     eax, ebx
0x18008287c  add     rsp, 20h
0x180082880  pop     r15
0x180082882  pop     r14
0x180082884  pop     r12
0x180082886  pop     rdi
0x180082887  pop     rsi
0x180082888  pop     rbp
0x180082889  pop     rbx
0x18008288a  retn
```
