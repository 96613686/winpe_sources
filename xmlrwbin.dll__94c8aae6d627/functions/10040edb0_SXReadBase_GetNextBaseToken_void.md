# SXReadBase::GetNextBaseToken(void)

- ea: `0x10040edb0`
- end: `0x10040f586`
- name: `?GetNextBaseToken@SXReadBase@@IEAAEXZ`
- size: `2006`
- prototype: `unsigned __int8 __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x100404f80`

## callees

- `0x100401350`
- `0x100406550`
- `0x100406be0`
- `0x100407050`
- `0x10040ed00`
- `0x10040edb0`
- `0x10040f590`
- `0x10040f9a0`
- `0x10040fbf0`
- `0x10040ff60`
- `0x100410010`
- `0x1004100d0`
- `0x100410e60`
- `0x100411000`
- `0x100411160`
- `0x100411650`
- `0x100424580`

## pseudocode

```c
unsigned __int8 __fastcall SXReadBase::GetNextBaseToken(SXReadBase *this)
{
  unsigned __int8 v2; // bp
  unsigned __int8 *v3; // rax
  unsigned int v4; // edi
  __int64 v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned int Mb32; // eax
  unsigned int v12; // eax
  int v14; // eax
  __int64 v15; // rsi
  __int64 v16; // rax
  struct CStringPtr **v17; // rdi
  unsigned int v18; // eax
  _DWORD *v19; // rdi
  struct CStringPtr *v20; // rdx
  int v21; // eax
  __int64 v22; // r14
  int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // edi
  unsigned int v26; // eax
  unsigned __int8 *WCharBuffer; // rax
  unsigned int v28; // esi
  unsigned int v29; // edi
  unsigned int v30; // eax
  unsigned __int8 *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax

  if ( !*((_DWORD *)this + 279) )
  {
    SXReadBase::CheckPreamble(this);
    *((_DWORD *)this + 279) = 1;
  }
  *((_QWORD *)this + 146) = 0;
  *((_QWORD *)this + 144) = 0;
  *((_DWORD *)this + 287) = 0;
  RStringPtr::assign((SXReadBase *)((char *)this + 1176), 0);
  RStringPtr::assign((SXReadBase *)((char *)this + 1184), 0);
  RStringPtr::assign((SXReadBase *)((char *)this + 1192), 0);
  *((_QWORD *)this + 151) = 0;
  *((_DWORD *)this + 304) = 0;
  *((_QWORD *)this + 164) = 0;
  *((_QWORD *)this + 165) = 0;
  *((_QWORD *)this + 166) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_DWORD *)this + 334) = 0;
  *((_QWORD *)this + 169) = 0;
  *((_DWORD *)this + 340) = 0;
  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 160) = 0;
  *((_DWORD *)this + 322) = 0;
  *((_QWORD *)this + 162) = 0;
  *((_DWORD *)this + 316) = 0;
  *((_DWORD *)this + 290) = 0;
  while ( 2 )
  {
    if ( *((_QWORD *)this + 178) != *((_QWORD *)this + 179) || SXReadBase::Pull(this) )
    {
      v3 = (unsigned __int8 *)*((_QWORD *)this + 178);
      v2 = *v3;
      *((_QWORD *)this + 178) = v3 + 1;
    }
    else
    {
      v2 = 0;
    }
    if ( *((_BYTE *)this + 1448) )
      return 0;
    switch ( v2 )
    {
      case 1u:
      case 2u:
      case 3u:
      case 4u:
      case 5u:
      case 6u:
      case 7u:
      case 8u:
      case 9u:
      case 0xAu:
      case 0xBu:
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0xFu:
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
      case 0x14u:
      case 0x16u:
      case 0x17u:
      case 0x18u:
      case 0x1Bu:
      case 0x80u:
      case 0x81u:
      case 0x82u:
      case 0x83u:
      case 0x84u:
      case 0x85u:
      case 0x86u:
      case 0x87u:
      case 0x88u:
      case 0x89u:
      case 0x8Au:
      case 0x8Bu:
        if ( *((_DWORD *)this + 282) )
          goto LABEL_26;
        v8 = *((_DWORD *)this + 280);
        if ( v8 == 2 )
          goto LABEL_26;
        if ( v8 )
          goto LABEL_80;
        *((_DWORD *)this + 280) = 2;
LABEL_26:
        v9 = v2 - 100;
        if ( v2 < 0x80u )
          v9 = v2;
        if ( v9 >= 0x2A )
          goto LABEL_80;
        v10 = *((unsigned __int8 *)&SXFormatDataByType + 8 * (int)v9);
        if ( (v10 & 0x40) == 0 )
          goto LABEL_34;
        if ( v10 == 65 )
        {
          Mb32 = SXReadBase::GetMb32(this);
          v10 = 2 * Mb32;
          if ( Mb32 > 2 * Mb32 )
          {
LABEL_78:
            MXRRaiseException(-2147352566);
            __debugbreak();
          }
        }
        else
        {
          v10 = SXReadBase::GetMb32(this);
        }
LABEL_34:
        v12 = *((_DWORD *)this + 174);
        *((_DWORD *)this + 290) = v10;
        if ( v12 && v10 > v12 )
          goto LABEL_79;
        *((_DWORD *)this + 305) = v2;
        *((_QWORD *)this + 137) = 0;
        *((_DWORD *)this + 276) = v10;
        _mm_lfence();
        return v2;
      case 0x8Cu:
      case 0xF1u:
        goto LABEL_75;
      case 0xE9u:
        v7 = *((_QWORD *)this + 90);
        if ( v7 )
        {
          *((_QWORD *)this + 90) = *(_QWORD *)(v7 + 168);
          (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
        }
        else
        {
          *((_QWORD *)this + 90) = 0;
        }
        SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 90);
        continue;
      case 0xEAu:
        v4 = SXReadBase::GetMb32(this);
        if ( v4 )
        {
          while ( 1 )
          {
            v5 = v4;
            v6 = *((_DWORD *)this + 358) - *((_DWORD *)this + 356);
            if ( v6 < v4 )
              v5 = v6;
            *((_QWORD *)this + 178) += v5;
            v4 -= v5;
            if ( !v4 )
              break;
            if ( !SXReadBase::Pull(this) )
            {
              MXRRaiseException(-1072896679);
              __debugbreak();
            }
          }
        }
        continue;
      case 0xEBu:
        v32 = *((_QWORD *)this + 90);
        v33 = *(_QWORD *)(v32 + 168);
        if ( !v33 )
          goto LABEL_80;
        if ( v32 )
        {
          *((_QWORD *)this + 90) = v33;
          (**(void (__fastcall ***)(__int64, __int64))v32)(v32, 1);
          _mm_lfence();
          return v2;
        }
        else
        {
          *((_QWORD *)this + 90) = 0;
LABEL_75:
          _mm_lfence();
          return v2;
        }
      case 0xECu:
        SXReadBase::CheckPreamble(this);
        SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 90);
        _mm_lfence();
        return v2;
      case 0xEFu:
        SXReadBase::TokenT(this);
        continue;
      case 0xF0u:
        SXReadBase::NameT(this);
        continue;
      case 0xF2u:
        if ( *((_DWORD *)this + 282) )
          goto LABEL_53;
        v23 = *((_DWORD *)this + 280);
        if ( v23 == 2 )
          goto LABEL_53;
        if ( v23 )
          goto LABEL_80;
        *((_DWORD *)this + 280) = 2;
LABEL_53:
        v24 = SXReadBase::GetMb32(this);
        v25 = 2 * v24;
        if ( 2 * v24 < v24 )
          goto LABEL_78;
        v26 = *((_DWORD *)this + 174);
        if ( v26 && v25 > v26 )
        {
LABEL_79:
          MXRRaiseException(-1072897499);
          __debugbreak();
        }
        _mm_lfence();
        if ( v25 )
        {
          WCharBuffer = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, 0, v24);
          *((_QWORD *)this + 144) = WCharBuffer;
          SXReadBase::GetBytes(this, WCharBuffer, v25);
        }
        else
        {
          *((_QWORD *)this + 144) = SXReadBase::GetWCharBuffer(this, 0, 2u);
        }
        *((_DWORD *)this + 287) = v24;
        _mm_lfence();
        return v2;
      case 0xF3u:
        v28 = SXReadBase::GetMb32(this);
        v29 = 2 * v28;
        if ( 2 * v28 < v28 )
          goto LABEL_78;
        v30 = *((_DWORD *)this + 174);
        if ( v30 && v29 > v30 )
          goto LABEL_79;
        _mm_lfence();
        if ( v29 )
        {
          v31 = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, 0, v28);
          *((_QWORD *)this + 88) = v31;
          SXReadBase::GetBytes(this, v31, v29);
        }
        else
        {
          *((_QWORD *)this + 88) = SXReadBase::GetWCharBuffer(this, 0, 2u);
        }
        *((_DWORD *)this + 178) = v28;
        _mm_lfence();
        return v2;
      case 0xF4u:
        SXReadBase::PiT(this);
        _mm_lfence();
        return v2;
      case 0xF7u:
        v21 = *((_DWORD *)this + 282);
        if ( v21 <= 0 )
          goto LABEL_80;
        v22 = *((_QWORD *)this + 93) + 32LL * (unsigned int)--*((_DWORD *)this + 188);
        *((_DWORD *)this + 282) = v21 - 1;
        RStringPtr::assign((SXReadBase *)((char *)this + 1184), *(struct CStringPtr **)(v22 + 8));
        RStringPtr::assign((SXReadBase *)((char *)this + 1176), *(struct CStringPtr **)v22);
        RStringPtr::assign((SXReadBase *)((char *)this + 1192), *(struct CStringPtr **)(v22 + 16));
        *((_DWORD *)this + 300) = *(_DWORD *)(v22 + 24);
        *((_QWORD *)this + 151) = SXReadBase::GetQName(
                                    this,
                                    (SXReadBase *)((char *)this + 1184),
                                    (SXReadBase *)((char *)this + 1192),
                                    0,
                                    (int *)this + 304);
        RStringPtr::assign((RStringPtr *)v22, 0);
        RStringPtr::assign((RStringPtr *)(v22 + 8), 0);
        RStringPtr::assign((RStringPtr *)(v22 + 16), 0);
        _mm_lfence();
        return v2;
      case 0xF8u:
        if ( *((_DWORD *)this + 282) )
          goto LABEL_43;
        v14 = *((_DWORD *)this + 280);
        if ( v14 )
        {
          if ( v14 == 1 )
          {
            if ( *((_BYTE *)this + 1124) )
              goto LABEL_80;
            *((_BYTE *)this + 1124) = 1;
          }
        }
        else
        {
          *((_DWORD *)this + 280) = 2;
        }
LABEL_43:
        v15 = (unsigned int)SXReadBase::GetMb32(this);
        v16 = *((_QWORD *)this + 90);
        if ( (unsigned int)v15 >= *(_DWORD *)(v16 + 116) )
        {
LABEL_80:
          MXRRaiseException(-2147467259);
          __debugbreak();
        }
        _mm_lfence();
        v17 = (struct CStringPtr **)(*(_QWORD *)(v16 + 120) + 40 * v15);
        RStringPtr::assign((SXReadBase *)((char *)this + 1176), *v17);
        RStringPtr::assign((SXReadBase *)((char *)this + 1184), v17[1]);
        RStringPtr::assign((SXReadBase *)((char *)this + 1192), v17[2]);
        *((_DWORD *)this + 300) = v15;
        *((_QWORD *)this + 151) = SXReadBase::GetQName(
                                    this,
                                    (SXReadBase *)((char *)this + 1184),
                                    (SXReadBase *)((char *)this + 1192),
                                    0,
                                    (int *)this + 304);
        v18 = *((_DWORD *)this + 188);
        if ( *((_DWORD *)this + 189) == v18 )
        {
          _stack<ELEMENT_DATA,10>::grow((char *)this + 728, 0);
          v18 = *((_DWORD *)this + 188);
        }
        v19 = (_DWORD *)(*((_QWORD *)this + 93) + 32LL * v18);
        *((_DWORD *)this + 188) = v18 + 1;
        *(_OWORD *)v19 = 0;
        *((_OWORD *)v19 + 1) = 0;
        v20 = (struct CStringPtr *)*((_QWORD *)this + 147);
        ++*((_DWORD *)this + 282);
        RStringPtr::assign((RStringPtr *)v19, v20);
        RStringPtr::assign((RStringPtr *)(v19 + 2), *((struct CStringPtr **)this + 148));
        RStringPtr::assign((RStringPtr *)(v19 + 4), *((struct CStringPtr **)this + 149));
        v19[6] = *((_DWORD *)this + 300);
        _mm_lfence();
        return v2;
      case 0xFCu:
        SXReadBase::DocTypeT(this);
        _mm_lfence();
        return v2;
      case 0xFEu:
        SXReadBase::XmlDeclT(this);
        _mm_lfence();
        return v2;
      default:
        goto LABEL_80;
    }
  }
}

```

## disassembly

```asm
0x10040edb0  mov     [rsp+arg_8], rbx
0x10040edb5  mov     [rsp+arg_10], rsi
0x10040edba  push    rdi
0x10040edbb  push    r12
0x10040edbd  push    r13
0x10040edbf  push    r14
0x10040edc1  push    r15
0x10040edc3  sub     rsp, 30h
0x10040edc7  cmp     dword ptr [rcx+45Ch], 0
0x10040edce  mov     rbx, rcx
0x10040edd1  jnz     short loc_10040EDE2
0x10040edd3  call    ?CheckPreamble@SXReadBase@@IEAAXXZ; SXReadBase::CheckPreamble(void)
0x10040edd8  mov     dword ptr [rbx+45Ch], 1
0x10040ede2  xor     esi, esi
0x10040ede4  lea     rcx, [rbx+498h]; this
0x10040edeb  xor     edx, edx; struct CStringPtr *
0x10040eded  mov     [rbx+490h], rsi
0x10040edf4  mov     [rbx+480h], rsi
0x10040edfb  mov     [rbx+47Ch], esi
0x10040ee01  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040ee06  lea     r15, [rbx+4A0h]
0x10040ee0d  xor     edx, edx; struct CStringPtr *
0x10040ee0f  mov     rcx, r15; this
0x10040ee12  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040ee17  lea     r12, [rbx+4A8h]
0x10040ee1e  xor     edx, edx; struct CStringPtr *
0x10040ee20  mov     rcx, r12; this
0x10040ee23  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040ee28  lea     r14, [rbx+4C0h]
0x10040ee2f  mov     [rbx+4B8h], rsi
0x10040ee36  mov     [r14], esi
0x10040ee39  mov     [rbx+520h], rsi
0x10040ee40  mov     [rbx+528h], rsi
0x10040ee47  mov     [rbx+530h], rsi
0x10040ee4e  mov     [rbx+540h], rsi
0x10040ee55  mov     [rbx+538h], esi
0x10040ee5b  mov     [rbx+548h], rsi
0x10040ee62  mov     [rbx+550h], esi
0x10040ee68  mov     [rbx+4E8h], rsi
0x10040ee6f  mov     [rbx+500h], rsi
0x10040ee76  mov     [rbx+508h], esi
0x10040ee7c  mov     [rbx+510h], rsi
0x10040ee83  mov     [rbx+4F0h], esi
0x10040ee89  mov     [rbx+488h], esi
0x10040ee8f  mov     [rsp+58h+arg_0], rbp
0x10040ee94  nop     dword ptr [rax+00h]
0x10040ee98  nop     dword ptr [rax+rax+00000000h]
0x10040eea0  mov     rax, [rbx+598h]
0x10040eea7  cmp     [rbx+590h], rax
0x10040eeae  jnz     short loc_10040EEC1
0x10040eeb0  mov     rcx, rbx; this
0x10040eeb3  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040eeb8  test    al, al
0x10040eeba  jnz     short loc_10040EEC1
0x10040eebc  xor     bpl, bpl
0x10040eebf  jmp     short loc_10040EED5
0x10040eec1  mov     rax, [rbx+590h]
0x10040eec8  movzx   ebp, byte ptr [rax]
0x10040eecb  inc     rax
0x10040eece  mov     [rbx+590h], rax
0x10040eed5  cmp     [rbx+5A8h], sil
0x10040eedc  jnz     loc_10040F3FD
0x10040eee2  movzx   edi, bpl
0x10040eee6  lea     eax, [rdi-1]; switch 254 cases
0x10040eee9  cmp     eax, 0FDh
0x10040eeee  ja      def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040eef4  lea     rdx, __ImageBase
0x10040eefb  cdqe
0x10040eefd  movzx   eax, ds:(byte_10040F488 - 100400000h)[rdx+rax]
0x10040ef05  mov     ecx, ds:(jpt_10040EF0F - 100400000h)[rdx+rax*4]
0x10040ef0c  add     rcx, rdx
0x10040ef0f  jmp     rcx; switch jump
0x10040ef11  mov     rcx, rbx; jumptable 000000010040EF0F case 240
0x10040ef14  call    ?NameT@SXReadBase@@IEAAXXZ; SXReadBase::NameT(void)
0x10040ef19  jmp     short loc_10040EEA0
0x10040ef1b  mov     rcx, rbx; jumptable 000000010040EF0F case 239
0x10040ef1e  call    ?TokenT@SXReadBase@@IEAAXXZ; SXReadBase::TokenT(void)
0x10040ef23  jmp     loc_10040EEA0
0x10040ef28  mov     rcx, rbx; jumptable 000000010040EF0F case 234
0x10040ef2b  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040ef30  mov     edi, eax
0x10040ef32  test    eax, eax
0x10040ef34  jz      loc_10040EEA0
0x10040ef3a  nop     word ptr [rax+rax+00h]
0x10040ef40  mov     edx, [rbx+598h]
0x10040ef46  mov     ecx, edi
0x10040ef48  sub     edx, [rbx+590h]
0x10040ef4e  cmp     edx, edi
0x10040ef50  cmovb   ecx, edx
0x10040ef53  add     [rbx+590h], rcx
0x10040ef5a  sub     edi, ecx
0x10040ef5c  jz      loc_10040EEA0
0x10040ef62  mov     rcx, rbx; this
0x10040ef65  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040ef6a  test    al, al
0x10040ef6c  jz      loc_10040F41C
0x10040ef72  jmp     short loc_10040EF40
0x10040ef74  mov     rcx, [rbx+2D0h]; jumptable 000000010040EF0F case 233
0x10040ef7b  test    rcx, rcx
0x10040ef7e  jz      short loc_10040EFA1
0x10040ef80  mov     rax, [rcx+0A8h]
0x10040ef87  mov     edx, 1
0x10040ef8c  mov     [rbx+2D0h], rax
0x10040ef93  mov     rax, [rcx]
0x10040ef96  mov     rax, [rax]
0x10040ef99  call    cs:__guard_dispatch_icall_fptr
0x10040ef9f  jmp     short loc_10040EFA8
0x10040efa1  mov     [rbx+2D0h], rsi
0x10040efa8  mov     rcx, [rbx+8]; struct IMalloc *
0x10040efac  lea     rdx, [rbx+2D0h]; struct SXTokenTable **
0x10040efb3  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x10040efb8  jmp     loc_10040EEA0
0x10040efbd  cmp     [rbx+468h], esi; jumptable 000000010040EF0F cases 1-20,22-24,27,128-139
0x10040efc3  jnz     short loc_10040EFE2
0x10040efc5  mov     eax, [rbx+460h]
0x10040efcb  cmp     eax, 2
0x10040efce  jz      short loc_10040EFE2
0x10040efd0  test    eax, eax
0x10040efd2  jnz     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040efd8  mov     dword ptr [rbx+460h], 2
0x10040efe2  cmp     bpl, 80h
0x10040efe6  lea     eax, [rdi-64h]
0x10040efe9  cmovb   eax, edi
0x10040efec  cmp     eax, 2Ah ; '*'
0x10040efef  jnb     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040eff5  cdqe
0x10040eff7  movzx   ecx, rva ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A[rdx+rax*8]; SXFORMATTYPEDATA near * SXFormatDataByType ...
0x10040efff  test    cl, 40h
0x10040f002  jz      short loc_10040F024
0x10040f004  cmp     ecx, 41h ; 'A'
0x10040f007  mov     rcx, rbx; this
0x10040f00a  jnz     short loc_10040F01D
0x10040f00c  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f011  lea     ecx, [rax+rax]
0x10040f014  cmp     eax, ecx
0x10040f016  jbe     short loc_10040F024
0x10040f018  jmp     loc_10040F427
0x10040f01d  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f022  mov     ecx, eax
0x10040f024  mov     eax, [rbx+2B8h]
0x10040f02a  mov     [rbx+488h], ecx
0x10040f030  test    eax, eax
0x10040f032  jz      short loc_10040F03C
0x10040f034  cmp     ecx, eax
0x10040f036  ja      loc_10040F432
0x10040f03c  mov     [rbx+4C4h], edi
0x10040f042  mov     [rbx+448h], rsi
0x10040f049  mov     [rbx+450h], ecx
0x10040f04f  lfence
0x10040f052  movzx   eax, bpl
0x10040f056  jmp     loc_10040F3FF
0x10040f05b  cmp     [rbx+468h], esi; jumptable 000000010040EF0F case 248
0x10040f061  jnz     short loc_10040F091
0x10040f063  mov     eax, [rbx+460h]
0x10040f069  test    eax, eax
0x10040f06b  jnz     short loc_10040F079
0x10040f06d  mov     dword ptr [rbx+460h], 2
0x10040f077  jmp     short loc_10040F091
0x10040f079  cmp     eax, 1
0x10040f07c  jnz     short loc_10040F091
0x10040f07e  cmp     [rbx+464h], sil
0x10040f085  jnz     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040f08b  mov     [rbx+464h], al
0x10040f091  mov     rcx, rbx; this
0x10040f094  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f099  mov     esi, eax
0x10040f09b  mov     rax, [rbx+2D0h]
0x10040f0a2  cmp     esi, [rax+74h]
0x10040f0a5  jnb     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040f0ab  lfence
0x10040f0ae  mov     rcx, [rax+78h]
0x10040f0b2  lea     rdx, [rsi+rsi*4]
0x10040f0b6  lea     rdi, [rcx+rdx*8]
0x10040f0ba  mov     rdx, [rcx+rdx*8]; struct CStringPtr *
0x10040f0be  lea     rcx, [rbx+498h]; this
0x10040f0c5  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f0ca  mov     rdx, [rdi+8]; struct CStringPtr *
0x10040f0ce  mov     rcx, r15; this
0x10040f0d1  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f0d6  mov     rdx, [rdi+10h]; struct CStringPtr *
0x10040f0da  mov     rcx, r12; this
0x10040f0dd  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f0e2  xor     r9d, r9d; int
0x10040f0e5  mov     [rbx+4B0h], esi
0x10040f0eb  mov     r8, r12; struct RStringPtr *
0x10040f0ee  mov     [rsp+58h+var_38], r14; int *
0x10040f0f3  mov     rdx, r15; struct RStringPtr *
0x10040f0f6  mov     rcx, rbx; this
0x10040f0f9  call    ?GetQName@SXReadBase@@IEAAPEA_WAEAVRStringPtr@@0HPEAH@Z; SXReadBase::GetQName(RStringPtr &,RStringPtr &,int,int *)
0x10040f0fe  lea     rsi, [rbx+2D8h]
0x10040f105  mov     [rbx+4B8h], rax
0x10040f10c  mov     eax, [rsi+18h]
0x10040f10f  cmp     [rsi+1Ch], eax
0x10040f112  jnz     short loc_10040F121
0x10040f114  xor     edx, edx
0x10040f116  mov     rcx, rsi
0x10040f119  call    ?grow@?$_stack@UELEMENT_DATA@@$09@@AEAAXI@Z; _stack<ELEMENT_DATA,10>::grow(uint)
0x10040f11e  mov     eax, [rsi+18h]
0x10040f121  mov     edi, eax
0x10040f123  xorps   xmm0, xmm0
0x10040f126  shl     rdi, 5
0x10040f12a  add     rdi, [rsi+10h]
0x10040f12e  inc     eax
0x10040f130  mov     rcx, rdi; this
0x10040f133  mov     [rsi+18h], eax
0x10040f136  movups  xmmword ptr [rdi], xmm0
0x10040f139  movups  xmmword ptr [rdi+10h], xmm0
0x10040f13d  mov     rdx, [rbx+498h]; struct CStringPtr *
0x10040f144  inc     dword ptr [rbx+468h]
0x10040f14a  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f14f  mov     rdx, [r15]; struct CStringPtr *
0x10040f152  lea     rcx, [rdi+8]; this
0x10040f156  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f15b  mov     rdx, [r12]; struct CStringPtr *
0x10040f15f  lea     rcx, [rdi+10h]; this
0x10040f163  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f168  mov     eax, [rbx+4B0h]
0x10040f16e  mov     [rdi+18h], eax
0x10040f171  lfence
0x10040f174  movzx   eax, bpl
0x10040f178  jmp     loc_10040F3FF
0x10040f17d  mov     eax, [rbx+468h]; jumptable 000000010040EF0F case 247
0x10040f183  test    eax, eax
0x10040f185  jle     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040f18b  dec     dword ptr [rbx+2F0h]
0x10040f191  mov     rcx, r15; this
0x10040f194  mov     r14d, [rbx+2F0h]
0x10040f19b  shl     r14, 5
0x10040f19f  add     r14, [rbx+2E8h]
0x10040f1a6  dec     eax
0x10040f1a8  mov     [rbx+468h], eax
0x10040f1ae  mov     rdx, [r14+8]; struct CStringPtr *
0x10040f1b2  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f1b7  mov     rdx, [r14]; struct CStringPtr *
0x10040f1ba  lea     rcx, [rbx+498h]; this
0x10040f1c1  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f1c6  mov     rdx, [r14+10h]; struct CStringPtr *
0x10040f1ca  mov     rcx, r12; this
0x10040f1cd  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f1d2  mov     eax, [r14+18h]
0x10040f1d6  xor     r9d, r9d; int
0x10040f1d9  mov     [rbx+4B0h], eax
0x10040f1df  mov     r8, r12; struct RStringPtr *
0x10040f1e2  lea     rax, [rbx+4C0h]
0x10040f1e9  mov     rdx, r15; struct RStringPtr *
0x10040f1ec  mov     rcx, rbx; this
0x10040f1ef  mov     [rsp+58h+var_38], rax; int *
0x10040f1f4  call    ?GetQName@SXReadBase@@IEAAPEA_WAEAVRStringPtr@@0HPEAH@Z; SXReadBase::GetQName(RStringPtr &,RStringPtr &,int,int *)
0x10040f1f9  xor     edx, edx; struct CStringPtr *
0x10040f1fb  mov     [rbx+4B8h], rax
0x10040f202  mov     rcx, r14; this
0x10040f205  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f20a  xor     edx, edx; struct CStringPtr *
0x10040f20c  lea     rcx, [r14+8]; this
0x10040f210  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f215  xor     edx, edx; struct CStringPtr *
0x10040f217  lea     rcx, [r14+10h]; this
0x10040f21b  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040f220  lfence
0x10040f223  movzx   eax, bpl
0x10040f227  jmp     loc_10040F3FF
0x10040f22c  cmp     [rbx+468h], esi; jumptable 000000010040EF0F case 242
0x10040f232  jnz     short loc_10040F251
0x10040f234  mov     eax, [rbx+460h]
0x10040f23a  cmp     eax, 2
0x10040f23d  jz      short loc_10040F251
0x10040f23f  test    eax, eax
0x10040f241  jnz     def_10040EF0F; jumptable 000000010040EF0F default case, cases 21,25,26,28-127,141-232,237,238,245,246,249-251,253
0x10040f247  mov     dword ptr [rbx+460h], 2
0x10040f251  mov     rcx, rbx; this
0x10040f254  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f259  mov     esi, eax
0x10040f25b  lea     edi, [rax+rax]
0x10040f25e  cmp     edi, eax
0x10040f260  jb      loc_10040F427
0x10040f266  mov     eax, [rbx+2B8h]
0x10040f26c  test    eax, eax
0x10040f26e  jz      short loc_10040F278
0x10040f270  cmp     edi, eax
0x10040f272  ja      loc_10040F432
0x10040f278  lfence
0x10040f27b  xor     edx, edx; int
0x10040f27d  mov     rcx, rbx; this
0x10040f280  test    edi, edi
0x10040f282  jz      short loc_10040F2B3
0x10040f284  mov     r8d, esi; unsigned int
0x10040f287  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040f28c  mov     r8d, edi; unsigned int
0x10040f28f  mov     [rbx+480h], rax
0x10040f296  mov     rdx, rax; unsigned __int8 *
0x10040f299  mov     rcx, rbx; this
0x10040f29c  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040f2a1  mov     [rbx+47Ch], esi
0x10040f2a7  lfence
0x10040f2aa  movzx   eax, bpl
0x10040f2ae  jmp     loc_10040F3FF
0x10040f2b3  mov     r8d, 2; unsigned int
0x10040f2b9  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040f2be  mov     [rbx+480h], rax
0x10040f2c5  mov     [rbx+47Ch], esi
  ... truncated ...
```
