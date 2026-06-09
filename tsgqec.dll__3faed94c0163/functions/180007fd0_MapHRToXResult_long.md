# MapHRToXResult(long)

- ea: `0x180007fd0`
- end: `0x1800084e3`
- name: `?MapHRToXResult@@YA?AW4_XResult32@@J@Z`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d50`

## callees

- `0x180007fd0`

## pseudocode

```c
__int64 __fastcall MapHRToXResult(int a1)
{
  __int64 result; // rax
  unsigned int v2; // edx
  bool v3; // zf
  unsigned int v4; // eax

  if ( a1 >= 0 )
    return 0;
  if ( a1 <= -2146893022 )
  {
    if ( a1 == -2146893022 )
      return 44;
    if ( a1 > -2147012851 )
    {
      if ( a1 > -2146893048 )
      {
        if ( a1 > -2146893041 )
        {
          switch ( a1 )
          {
            case -2146893040:
              return 119;
            case -2146893039:
              return 39;
            case -2146893033:
              return 120;
            case -2146893032:
              return 121;
            case -2146893024:
              return 122;
          }
          v2 = -1;
          v3 = a1 == -2146893023;
          v4 = 123;
        }
        else
        {
          switch ( a1 )
          {
            case -2146893041:
              return 118;
            case -2146893047:
              return 114;
            case -2146893046:
              return 115;
            case -2146893045:
              return 116;
            case -2146893044:
              return 37;
            case -2146893043:
              return 117;
          }
          v2 = -1;
          v3 = a1 == -2146893042;
          v4 = 40;
        }
      }
      else
      {
        if ( a1 == -2146893048 )
          return 113;
        if ( a1 > -2146893055 )
        {
          switch ( a1 )
          {
            case -2146893054:
              return 43;
            case -2146893053:
              return 169;
            case -2146893052:
              return 36;
            case -2146893051:
              return 110;
            case -2146893050:
              return 111;
          }
          v2 = -1;
          v3 = a1 == -2146893049;
          v4 = 112;
        }
        else
        {
          switch ( a1 )
          {
            case -2146893055:
              return 109;
            case -2147012746:
              return 75;
            case -2147012744:
              return 164;
            case -2147012727:
              return 68;
            case -2147012721:
              return 84;
            case -2147012717:
              return 65;
          }
          v2 = -1;
          v3 = a1 == -2146893056;
          v4 = 108;
        }
      }
      goto LABEL_106;
    }
    if ( a1 == -2147012851 )
      return 64;
    if ( a1 > -2147022646 )
    {
      if ( a1 > -2147012892 )
      {
        switch ( a1 )
        {
          case -2147012889:
            return 104;
          case -2147012879:
            return 163;
          case -2147012877:
            return 165;
          case -2147012866:
            return 24;
          case -2147012864:
            return 63;
        }
        v2 = -1;
        v3 = a1 == -2147012859;
        v4 = 66;
        goto LABEL_106;
      }
      if ( a1 == -2147012892 )
        return 166;
      if ( a1 == -2147020579 )
        return 72;
      if ( (unsigned int)(a1 + 2147014843) > 1 )
      {
        if ( a1 == -2147014836 )
          return 53;
        if ( a1 == -2147013895 )
          return 54;
        v2 = -1;
        v3 = a1 == -2147012894;
        v4 = 105;
        goto LABEL_106;
      }
    }
    else
    {
      if ( a1 == -2147022646 )
        return 103;
      if ( a1 <= -2147024888 )
      {
        if ( a1 != -2147024888 )
        {
          if ( a1 == -2147467263 )
            return 12;
          if ( a1 == -2147467262 )
            return 2;
          if ( a1 != -2147467259 )
          {
            if ( a1 == -2147418113 )
              return 8;
            if ( a1 == -2147024894 )
              return 3;
            v2 = -1;
            v3 = a1 == -2147024891;
            v4 = 26;
LABEL_106:
            if ( v3 )
              return v4;
            return v2;
          }
          return 0xFFFFFFFFLL;
        }
        return 1;
      }
      switch ( a1 )
      {
        case -2147024882:
          return 1;
        case -2147024832:
          return 168;
        case -2147024809:
          return 4;
        case -2147024703:
          return 167;
        case -2147024637:
          return 71;
      }
      if ( a1 != -2147023660 )
        return 0xFFFFFFFFLL;
    }
    return 55;
  }
  if ( a1 > -2146892957 )
  {
    switch ( a1 )
    {
      case -2146892951:
        return 85;
      case -2146885628:
        return 106;
      case -2146885616:
        return 47;
      case -2146885613:
        return 48;
      case -2146762482:
        return 46;
      case -2146762481:
        return 45;
      case -1072860839:
        return 170;
      default:
        result = 49;
        if ( a1 != -805306333 )
          return 0xFFFFFFFFLL;
        break;
    }
  }
  else if ( a1 == -2146892957 )
  {
    return 38;
  }
  else
  {
    switch ( a1 )
    {
      case -2146893020:
        result = 42;
        break;
      case -2146893019:
        result = 124;
        break;
      case -2146893018:
        result = 125;
        break;
      case -2146893017:
        result = 32;
        break;
      case -2146893016:
        result = 31;
        break;
      case -2146893015:
        result = 126;
        break;
      case -2146893008:
        result = 127;
        break;
      case -2146893007:
        result = 128;
        break;
      case -2146893006:
        result = 129;
        break;
      case -2146893005:
        result = 130;
        break;
      case -2146893004:
        result = 131;
        break;
      case -2146893003:
        result = 132;
        break;
      case -2146893002:
        result = 133;
        break;
      case -2146893001:
        result = 134;
        break;
      case -2146893000:
        result = 135;
        break;
      case -2146892999:
        result = 136;
        break;
      case -2146892998:
        result = 137;
        break;
      case -2146892997:
        result = 138;
        break;
      case -2146892996:
        result = 139;
        break;
      case -2146892995:
        result = 140;
        break;
      case -2146892994:
        result = 141;
        break;
      case -2146892993:
        result = 142;
        break;
      case -2146892992:
        result = 143;
        break;
      case -2146892991:
        result = 144;
        break;
      case -2146892990:
        result = 145;
        break;
      case -2146892989:
        result = 146;
        break;
      case -2146892987:
        result = 147;
        break;
      case -2146892986:
        result = 148;
        break;
      case -2146892985:
        result = 149;
        break;
      case -2146892984:
        result = 150;
        break;
      case -2146892983:
        result = 33;
        break;
      case -2146892976:
        result = 35;
        break;
      case -2146892975:
        result = 151;
        break;
      case -2146892974:
        result = 152;
        break;
      case -2146892973:
        result = 153;
        break;
      case -2146892972:
        result = 154;
        break;
      case -2146892971:
        result = 155;
        break;
      case -2146892970:
        result = 156;
        break;
      case -2146892969:
        result = 157;
        break;
      case -2146892968:
        result = 158;
        break;
      case -2146892967:
        result = 159;
        break;
      case -2146892966:
        result = 160;
        break;
      case -2146892965:
        result = 161;
        break;
      case -2146892963:
        result = 162;
        break;
      case -2146892962:
        result = 34;
        break;
      case -2146892961:
        result = 41;
        break;
      default:
        return 0xFFFFFFFFLL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007fd0  test    ecx, ecx
0x180007fd2  js      short loc_180007FD7
0x180007fd4  xor     eax, eax
0x180007fd6  retn
0x180007fd7  mov     eax, 80090322h
0x180007fdc  cmp     ecx, eax
0x180007fde  jg      loc_18000831D
0x180007fe4  jz      loc_180008317
0x180007fea  mov     eax, 80072F0Dh
0x180007fef  cmp     ecx, eax
0x180007ff1  jg      loc_180008182
0x180007ff7  jz      loc_18000817C
0x180007ffd  mov     eax, 800708CAh
0x180008002  cmp     ecx, eax
0x180008004  jg      loc_1800080CE
0x18000800a  jz      loc_1800080C8
0x180008010  mov     eax, 80070008h
0x180008015  cmp     ecx, eax
0x180008017  jg      short loc_180008074
0x180008019  jz      loc_1800080C2
0x18000801f  cmp     ecx, 80004001h
0x180008025  jz      short loc_18000806E
0x180008027  cmp     ecx, 80004002h
0x18000802d  jz      short loc_180008068
0x18000802f  cmp     ecx, 80004005h
0x180008035  jz      short def_180008353; jumptable 0000000180008353 default case, cases -2146893014--2146893009,-2146892988,-2146892982--2146892977,-2146892964
0x180008037  cmp     ecx, 8000FFFFh
0x18000803d  jz      short loc_18000805E
0x18000803f  cmp     ecx, 80070002h
0x180008045  jz      short loc_180008058
0x180008047  or      edx, 0FFFFFFFFh
0x18000804a  cmp     ecx, 80070005h
0x180008050  lea     eax, [rdx+1Bh]
0x180008053  jmp     loc_1800082F3
0x180008058  mov     eax, 3
0x18000805d  retn
0x18000805e  mov     eax, 8
0x180008063  retn
0x180008064  or      eax, 0FFFFFFFFh; jumptable 0000000180008353 default case, cases -2146893014--2146893009,-2146892988,-2146892982--2146892977,-2146892964
0x180008067  retn
0x180008068  mov     eax, 2
0x18000806d  retn
0x18000806e  mov     eax, 0Ch
0x180008073  retn
0x180008074  cmp     ecx, 8007000Eh
0x18000807a  jz      short loc_1800080C2
0x18000807c  cmp     ecx, 80070040h
0x180008082  jz      short loc_1800080BC
0x180008084  cmp     ecx, 80070057h
0x18000808a  jz      short loc_1800080B6
0x18000808c  cmp     ecx, 800700C1h
0x180008092  jz      short loc_1800080B0
0x180008094  cmp     ecx, 80070103h
0x18000809a  jz      short loc_1800080AA
0x18000809c  cmp     ecx, 800704D4h
0x1800080a2  jnz     short def_180008353; jumptable 0000000180008353 default case, cases -2146893014--2146893009,-2146892988,-2146892982--2146892977,-2146892964
0x1800080a4  mov     eax, 37h ; '7'
0x1800080a9  retn
0x1800080aa  mov     eax, 47h ; 'G'
0x1800080af  retn
0x1800080b0  mov     eax, 0A7h
0x1800080b5  retn
0x1800080b6  mov     eax, 4
0x1800080bb  retn
0x1800080bc  mov     eax, 0A8h
0x1800080c1  retn
0x1800080c2  mov     eax, 1
0x1800080c7  retn
0x1800080c8  mov     eax, 67h ; 'g'
0x1800080cd  retn
0x1800080ce  mov     eax, 80072EE4h
0x1800080d3  cmp     ecx, eax
0x1800080d5  jg      short loc_180008125
0x1800080d7  jz      short loc_18000811F
0x1800080d9  cmp     ecx, 800710DDh
0x1800080df  jz      short loc_180008119
0x1800080e1  lea     eax, [rcx+7FF8D8BBh]
0x1800080e7  cmp     eax, 1
0x1800080ea  jbe     short loc_1800080A4
0x1800080ec  cmp     ecx, 8007274Ch
0x1800080f2  jz      short loc_180008113
0x1800080f4  cmp     ecx, 80072AF9h
0x1800080fa  jz      short loc_18000810D
0x1800080fc  or      edx, 0FFFFFFFFh
0x1800080ff  cmp     ecx, 80072EE2h
0x180008105  lea     eax, [rdx+6Ah]
0x180008108  jmp     loc_1800082F3
0x18000810d  mov     eax, 36h ; '6'
0x180008112  retn
0x180008113  mov     eax, 35h ; '5'
0x180008118  retn
0x180008119  mov     eax, 48h ; 'H'
0x18000811e  retn
0x18000811f  mov     eax, 0A6h
0x180008124  retn
0x180008125  cmp     ecx, 80072EE7h
0x18000812b  jz      short loc_180008176
0x18000812d  cmp     ecx, 80072EF1h
0x180008133  jz      short loc_180008170
0x180008135  cmp     ecx, 80072EF3h
0x18000813b  jz      short loc_18000816A
0x18000813d  cmp     ecx, 80072EFEh
0x180008143  jz      short loc_180008164
0x180008145  cmp     ecx, 80072F00h
0x18000814b  jz      short loc_18000815E
0x18000814d  or      edx, 0FFFFFFFFh
0x180008150  cmp     ecx, 80072F05h
0x180008156  lea     eax, [rdx+43h]
0x180008159  jmp     loc_1800082F3
0x18000815e  mov     eax, 3Fh ; '?'
0x180008163  retn
0x180008164  mov     eax, 18h
0x180008169  retn
0x18000816a  mov     eax, 0A5h
0x18000816f  retn
0x180008170  mov     eax, 0A3h
0x180008175  retn
0x180008176  mov     eax, 68h ; 'h'
0x18000817b  retn
0x18000817c  mov     eax, 40h ; '@'
0x180008181  retn
0x180008182  mov     eax, 80090308h
0x180008187  cmp     ecx, eax
0x180008189  jg      loc_18000825A
0x18000818f  jz      loc_180008254
0x180008195  mov     eax, 80090301h
0x18000819a  cmp     ecx, eax
0x18000819c  jg      short loc_1800081FD
0x18000819e  jz      short loc_1800081F7
0x1800081a0  cmp     ecx, 80072F76h
0x1800081a6  jz      short loc_1800081F1
0x1800081a8  cmp     ecx, 80072F78h
0x1800081ae  jz      short loc_1800081EB
0x1800081b0  cmp     ecx, 80072F89h
0x1800081b6  jz      short loc_1800081E5
0x1800081b8  cmp     ecx, 80072F8Fh
0x1800081be  jz      short loc_1800081DF
0x1800081c0  cmp     ecx, 80072F93h
0x1800081c6  jz      short loc_1800081D9
0x1800081c8  or      edx, 0FFFFFFFFh
0x1800081cb  cmp     ecx, 80090300h
0x1800081d1  lea     eax, [rdx+6Dh]
0x1800081d4  jmp     loc_1800082F3
0x1800081d9  mov     eax, 41h ; 'A'
0x1800081de  retn
0x1800081df  mov     eax, 54h ; 'T'
0x1800081e4  retn
0x1800081e5  mov     eax, 44h ; 'D'
0x1800081ea  retn
0x1800081eb  mov     eax, 0A4h
0x1800081f0  retn
0x1800081f1  mov     eax, 4Bh ; 'K'
0x1800081f6  retn
0x1800081f7  mov     eax, 6Dh ; 'm'
0x1800081fc  retn
0x1800081fd  cmp     ecx, 80090302h
0x180008203  jz      short loc_18000824E
0x180008205  cmp     ecx, 80090303h
0x18000820b  jz      short loc_180008248
0x18000820d  cmp     ecx, 80090304h
0x180008213  jz      short loc_180008242
0x180008215  cmp     ecx, 80090305h
0x18000821b  jz      short loc_18000823C
0x18000821d  cmp     ecx, 80090306h
0x180008223  jz      short loc_180008236
0x180008225  or      edx, 0FFFFFFFFh
0x180008228  cmp     ecx, 80090307h
0x18000822e  lea     eax, [rdx+71h]
0x180008231  jmp     loc_1800082F3
0x180008236  mov     eax, 6Fh ; 'o'
0x18000823b  retn
0x18000823c  mov     eax, 6Eh ; 'n'
0x180008241  retn
0x180008242  mov     eax, 24h ; '$'
0x180008247  retn
0x180008248  mov     eax, 0A9h
0x18000824d  retn
0x18000824e  mov     eax, 2Bh ; '+'
0x180008253  retn
0x180008254  mov     eax, 71h ; 'q'
0x180008259  retn
0x18000825a  mov     eax, 8009030Fh
0x18000825f  cmp     ecx, eax
0x180008261  jg      short loc_1800082BF
0x180008263  jz      short loc_1800082B9
0x180008265  cmp     ecx, 80090309h
0x18000826b  jz      short loc_1800082B3
0x18000826d  cmp     ecx, 8009030Ah
0x180008273  jz      short loc_1800082AD
0x180008275  cmp     ecx, 8009030Bh
0x18000827b  jz      short loc_1800082A7
0x18000827d  cmp     ecx, 8009030Ch
0x180008283  jz      short loc_1800082A1
0x180008285  cmp     ecx, 8009030Dh
0x18000828b  jz      short loc_18000829B
0x18000828d  or      edx, 0FFFFFFFFh
0x180008290  cmp     ecx, 8009030Eh
0x180008296  lea     eax, [rdx+29h]
0x180008299  jmp     short loc_1800082F3
0x18000829b  mov     eax, 75h ; 'u'
0x1800082a0  retn
0x1800082a1  mov     eax, 25h ; '%'
0x1800082a6  retn
0x1800082a7  mov     eax, 74h ; 't'
0x1800082ac  retn
0x1800082ad  mov     eax, 73h ; 's'
0x1800082b2  retn
0x1800082b3  mov     eax, 72h ; 'r'
0x1800082b8  retn
0x1800082b9  mov     eax, 76h ; 'v'
0x1800082be  retn
0x1800082bf  cmp     ecx, 80090310h
0x1800082c5  jz      short loc_180008311
0x1800082c7  cmp     ecx, 80090311h
0x1800082cd  jz      short loc_18000830B
0x1800082cf  cmp     ecx, 80090317h
0x1800082d5  jz      short loc_180008305
0x1800082d7  cmp     ecx, 80090318h
0x1800082dd  jz      short loc_1800082FF
0x1800082df  cmp     ecx, 80090320h
0x1800082e5  jz      short loc_1800082F9
0x1800082e7  or      edx, 0FFFFFFFFh
0x1800082ea  cmp     ecx, 80090321h
0x1800082f0  lea     eax, [rdx+7Ch]
0x1800082f3  cmovz   edx, eax
0x1800082f6  mov     eax, edx
0x1800082f8  retn
0x1800082f9  mov     eax, 7Ah ; 'z'
0x1800082fe  retn
0x1800082ff  mov     eax, 79h ; 'y'
0x180008304  retn
0x180008305  mov     eax, 78h ; 'x'
0x18000830a  retn
0x18000830b  mov     eax, 27h ; '''
0x180008310  retn
0x180008311  mov     eax, 77h ; 'w'
0x180008316  retn
0x180008317  mov     eax, 2Ch ; ','
0x18000831c  retn
0x18000831d  mov     eax, 80090363h
0x180008322  cmp     ecx, eax
0x180008324  jg      loc_18000846F
0x18000832a  jz      loc_180008469
0x180008330  add     ecx, 7FF6FCDCh; switch 60 cases
0x180008336  cmp     ecx, 3Bh
0x180008339  ja      def_180008353; jumptable 0000000180008353 default case, cases -2146893014--2146893009,-2146892988,-2146892982--2146892977,-2146892964
0x18000833f  movsxd  rax, ecx
0x180008342  lea     rdx, cs:180000000h
0x180008349  mov     ecx, ds:(jpt_180008353 - 180000000h)[rdx+rax*4]
0x180008350  add     rcx, rdx
0x180008353  jmp     rcx; switch jump
0x180008355  mov     eax, 1Fh; jumptable 0000000180008353 case -2146893016
0x18000835a  retn
0x18000835b  mov     eax, 20h ; ' '; jumptable 0000000180008353 case -2146893017
0x180008360  retn
0x180008361  mov     eax, 21h ; '!'; jumptable 0000000180008353 case -2146892983
0x180008366  retn
0x180008367  mov     eax, 22h ; '"'; jumptable 0000000180008353 case -2146892962
0x18000836c  retn
0x18000836d  mov     eax, 23h ; '#'; jumptable 0000000180008353 case -2146892976
0x180008372  retn
0x180008373  mov     eax, 29h ; ')'; jumptable 0000000180008353 case -2146892961
0x180008378  retn
0x180008379  mov     eax, 2Ah ; '*'; jumptable 0000000180008353 case -2146893020
0x18000837e  retn
0x18000837f  mov     eax, 7Ch ; '|'; jumptable 0000000180008353 case -2146893019
0x180008384  retn
0x180008385  mov     eax, 7Dh ; '}'; jumptable 0000000180008353 case -2146893018
0x18000838a  retn
0x18000838b  mov     eax, 7Eh ; '~'; jumptable 0000000180008353 case -2146893015
0x180008390  retn
0x180008391  mov     eax, 7Fh; jumptable 0000000180008353 case -2146893008
0x180008396  retn
0x180008397  mov     eax, 80h; jumptable 0000000180008353 case -2146893007
0x18000839c  retn
0x18000839d  mov     eax, 81h; jumptable 0000000180008353 case -2146893006
0x1800083a2  retn
0x1800083a3  mov     eax, 82h; jumptable 0000000180008353 case -2146893005
0x1800083a8  retn
0x1800083a9  mov     eax, 83h; jumptable 0000000180008353 case -2146893004
0x1800083ae  retn
0x1800083af  mov     eax, 84h; jumptable 0000000180008353 case -2146893003
0x1800083b4  retn
0x1800083b5  mov     eax, 85h; jumptable 0000000180008353 case -2146893002
0x1800083ba  retn
0x1800083bb  mov     eax, 86h; jumptable 0000000180008353 case -2146893001
0x1800083c0  retn
0x1800083c1  mov     eax, 87h; jumptable 0000000180008353 case -2146893000
0x1800083c6  retn
0x1800083c7  mov     eax, 88h; jumptable 0000000180008353 case -2146892999
0x1800083cc  retn
0x1800083cd  mov     eax, 89h; jumptable 0000000180008353 case -2146892998
0x1800083d2  retn
0x1800083d3  mov     eax, 8Ah; jumptable 0000000180008353 case -2146892997
0x1800083d8  retn
0x1800083d9  mov     eax, 8Bh; jumptable 0000000180008353 case -2146892996
0x1800083de  retn
0x1800083df  mov     eax, 8Ch; jumptable 0000000180008353 case -2146892995
0x1800083e4  retn
0x1800083e5  mov     eax, 8Dh; jumptable 0000000180008353 case -2146892994
  ... truncated ...
```
