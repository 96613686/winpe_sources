# SXReader::ParseSXStream(void)

- ea: `0x100404f80`
- end: `0x100405780`
- name: `?ParseSXStream@SXReader@@AEAAXXZ`
- size: `2048`
- prototype: `void __fastcall(SXReader *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x100404ec0`

## callees

- `0x100401350`
- `0x100404f80`
- `0x100405790`
- `0x100406be0`
- `0x100407050`
- `0x10040eb50`
- `0x10040edb0`
- `0x100410d20`
- `0x100411160`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x100405474`
- `KERNEL32!HeapFree` at `0x100405474`

## pseudocode

```c
void __fastcall SXReader::ParseSXStream(SXReader *this)
{
  char *v1; // rsi
  __int128 v3; // xmm0
  __int64 v4; // rcx
  int v5; // eax
  unsigned __int8 NextBaseToken; // di
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r8
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v24; // esi
  _DWORD *v25; // rdi
  __int64 v26; // rax
  unsigned int v27; // ecx
  unsigned int Mb32; // eax
  __int64 v29; // rdx
  __int64 *v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  int v39; // eax
  int v40; // esi
  LPVOID *v41; // rdi
  struct IMalloc *v42; // rcx
  bool v43; // zf
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // [rsp+50h] [rbp-48h] BYREF
  int v53; // [rsp+58h] [rbp-40h]
  __int64 v54; // [rsp+60h] [rbp-38h]
  int v55; // [rsp+68h] [rbp-30h]
  __int64 v56; // [rsp+70h] [rbp-28h]
  int v57; // [rsp+78h] [rbp-20h]

  v1 = (char *)this + 656;
  *((_OWORD *)this + 40) = *(_OWORD *)&CodeStringPtr::empty;
  *((_WORD *)this + 328) = 0;
  *((_DWORD *)this + 172) = 0;
  *((_DWORD *)this + 286) = 0;
  *((_OWORD *)this + 38) = *(_OWORD *)&CodeStringPtr::empty;
  v3 = *(_OWORD *)&CodeStringPtr::empty;
  *((_DWORD *)this + 279) = 0;
  *((_OWORD *)this + 39) = v3;
  SXReadBase::Clear(this);
  SXReadBase::XmlNsReset(this);
  SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 90);
  v4 = *((_QWORD *)this + 185);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 24LL))(v4, (char *)this + 1464);
    if ( v5 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v5);
      __debugbreak();
    }
  }
  NextBaseToken = SXReadBase::GetNextBaseToken(this);
  if ( NextBaseToken == 0xFE )
  {
    *((_DWORD *)this + 154) = *((_DWORD *)this + 172);
    *((_QWORD *)this + 78) = *((_QWORD *)this + 142);
    *((_DWORD *)this + 158) = *((_DWORD *)this + 286);
    *((_QWORD *)this + 76) = v1;
    NextBaseToken = SXReadBase::GetNextBaseToken(this);
  }
  v7 = *((_QWORD *)this + 185);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
    if ( v8 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v8);
      __debugbreak();
    }
  }
  if ( NextBaseToken )
  {
    while ( 2 )
    {
      switch ( NextBaseToken )
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
          v19 = *((_QWORD *)this + 187);
          if ( v19 )
          {
            v20 = NextBaseToken - 100;
            if ( NextBaseToken < 0x80u )
              v20 = NextBaseToken;
            v21 = *((unsigned __int8 *)&SXFormatDataByType + 8 * v20);
            if ( (v21 & 0x40) != 0 )
            {
              v22 = *((_DWORD *)this + 174);
              v21 = *((unsigned int *)this + 290);
              if ( v22 )
              {
                if ( (unsigned int)v21 > v22 )
                {
                  MXRRaiseException(-1072897499);
                  __debugbreak();
                }
              }
            }
            v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *))(*(_QWORD *)v19 + 24LL))(
                    v19,
                    NextBaseToken,
                    v21,
                    (char *)this + 1080);
            if ( v23 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v23);
              __debugbreak();
            }
          }
          if ( !*((_QWORD *)this + 137) )
          {
            v24 = *((_DWORD *)this + 276);
            v25 = (_DWORD *)*((_QWORD *)this + 136);
            if ( v24 )
            {
              while ( 1 )
              {
                v26 = v24;
                v27 = v25[358] - v25[356];
                if ( v27 < v24 )
                  v26 = v27;
                *((_QWORD *)v25 + 178) += v26;
                v24 -= v26;
                if ( !v24 )
                  break;
                if ( !SXReadBase::Pull((SXReadBase *)v25) )
                {
                  MXRRaiseException(-1072896679);
                  __debugbreak();
                }
              }
            }
          }
          goto LABEL_63;
        case 0x8Cu:
          Mb32 = SXReadBase::GetMb32(this);
          v29 = *((_QWORD *)this + 90);
          if ( Mb32 >= *(_DWORD *)(v29 + 116) )
            goto LABEL_83;
          v30 = (__int64 *)(*(_QWORD *)(v29 + 120) + 40LL * Mb32);
          if ( *((_QWORD *)this + 187) )
          {
            _mm_lfence();
            v31 = *v30;
            v52 = *v30 + 24;
            v32 = *(_DWORD *)(v31 + 16);
            v33 = v30[1];
            v53 = v32;
            v54 = v33 + 24;
            v34 = *(_DWORD *)(v33 + 16);
            v35 = v30[2];
            v55 = v34;
            v56 = v35 + 24;
            v57 = *(_DWORD *)(v35 + 16);
            *((_QWORD *)this + 137) = &v52;
            *((_DWORD *)this + 276) = 48;
            v36 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, char *))(**((_QWORD **)this + 187) + 24LL))(
                    *((_QWORD *)this + 187),
                    141,
                    48,
                    (char *)this + 1080);
            if ( v36 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v36);
              __debugbreak();
            }
            *((_QWORD *)this + 137) = 0;
            *((_DWORD *)this + 276) = 0;
          }
LABEL_63:
          NextBaseToken = SXReadBase::GetNextBaseToken(this);
          if ( !NextBaseToken )
            break;
          continue;
        case 0xEBu:
          v48 = *((_QWORD *)this + 187);
          if ( v48 )
          {
            v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 48LL))(v48);
            if ( v49 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v49);
              __debugbreak();
            }
          }
          goto LABEL_63;
        case 0xECu:
          v46 = *((_QWORD *)this + 187);
          if ( v46 )
          {
            v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 40LL))(v46);
            if ( v47 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v47);
              __debugbreak();
            }
          }
          goto LABEL_63;
        case 0xF1u:
          v17 = *((_QWORD *)this + 186);
          if ( v17 )
          {
            v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 64LL))(v17);
            if ( v18 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v18);
              __debugbreak();
            }
          }
          *((_BYTE *)this + 1476) = 0;
          goto LABEL_63;
        case 0xF2u:
          if ( !*((_BYTE *)this + 1476) )
          {
            v13 = *((_QWORD *)this + 186);
            if ( v13 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 56LL))(v13);
              if ( v14 < 0 )
              {
                _mm_lfence();
                MXRRaiseException(v14);
                __debugbreak();
              }
              *((_BYTE *)this + 1476) = 1;
            }
          }
          v15 = *((_QWORD *)this + 185);
          if ( v15 )
          {
            v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 80LL))(
                    v15,
                    *((_QWORD *)this + 144),
                    *((unsigned int *)this + 287));
            if ( v16 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v16);
              __debugbreak();
            }
          }
          goto LABEL_63;
        case 0xF3u:
          v9 = *((_QWORD *)this + 186);
          if ( v9 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 72LL))(
                    v9,
                    *((_QWORD *)this + 88),
                    *((unsigned int *)this + 178));
            if ( v10 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v10);
              __debugbreak();
            }
          }
          goto LABEL_63;
        case 0xF4u:
          v11 = *((_QWORD *)this + 185);
          if ( v11 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v11 + 96LL))(
                    v11,
                    *((_QWORD *)this + 164),
                    *((unsigned int *)this + 330),
                    *((_QWORD *)this + 168),
                    *((_DWORD *)this + 334));
            if ( v12 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v12);
              __debugbreak();
            }
          }
          goto LABEL_63;
        case 0xF7u:
          v37 = *((_QWORD *)this + 185);
          if ( v37 )
          {
            v38 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v37 + 72LL))(
                    v37,
                    *((_QWORD *)this + 147) + 24LL,
                    *(unsigned int *)(*((_QWORD *)this + 147) + 16LL),
                    *((_QWORD *)this + 149) + 24LL,
                    *(_DWORD *)(*((_QWORD *)this + 149) + 16LL),
                    *((_QWORD *)this + 151),
                    *((_DWORD *)this + 304));
            if ( v38 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v38);
              __debugbreak();
            }
          }
          v39 = *((_DWORD *)this + 30);
          v40 = *((_DWORD *)this + 282) + 1;
          if ( v39 )
          {
            do
            {
              v41 = (LPVOID *)(*((_QWORD *)this + 14) + 48LL * (unsigned int)(v39 - 1));
              if ( *((_DWORD *)v41 + 7) < v40 )
                break;
              (*(void (__fastcall **)(SXReader *, LPVOID, _QWORD, LPVOID, _DWORD))(*(_QWORD *)this + 32LL))(
                this,
                *v41,
                *((unsigned int *)v41 + 2),
                v41[2],
                *((_DWORD *)v41 + 6));
              *(_DWORD *)(*((_QWORD *)this + 11) + 4LL * (unsigned int)(*((_DWORD *)v41 + 9) % *((_DWORD *)this + 21))) = *((_DWORD *)v41 + 10);
              if ( *v41 )
              {
                v42 = (struct IMalloc *)*((_QWORD *)this + 1);
                if ( v42 || (v42 = g_pMalloc) != 0 )
                  ((void (__fastcall *)(struct IMalloc *, LPVOID))v42->lpVtbl->Free)(v42, *v41);
                else
                  HeapFree(g_hHeap, 0, *v41);
              }
              v43 = (*((_DWORD *)this + 30))-- == 1;
              v39 = *((_DWORD *)this + 30);
            }
            while ( !v43 );
          }
          goto LABEL_63;
        case 0xF8u:
          SXReader::ElementT(this);
          goto LABEL_63;
        case 0xFCu:
          v44 = *((_QWORD *)this + 187);
          if ( v44 )
          {
            v45 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)v44 + 32LL))(
                    v44,
                    *((_QWORD *)this + 169),
                    *((unsigned int *)this + 340),
                    *((_QWORD *)this + 173),
                    *((_DWORD *)this + 348),
                    *((_QWORD *)this + 175),
                    *((_DWORD *)this + 352),
                    *((_QWORD *)this + 171),
                    *((_DWORD *)this + 344));
            if ( v45 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v45);
              __debugbreak();
            }
          }
          goto LABEL_63;
        default:
LABEL_83:
          MXRRaiseException(-2147467259);
          __debugbreak();
      }
      break;
    }
  }
  v50 = *((_QWORD *)this + 185);
  if ( v50 )
  {
    v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 40LL))(v50);
    if ( v51 < 0 )
    {
      _mm_lfence();
      MXRRaiseException(v51);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x100404f80  mov     [rsp+arg_10], rbx
0x100404f85  push    rsi
0x100404f86  push    r14
0x100404f88  push    r15
0x100404f8a  sub     rsp, 80h
0x100404f91  movups  xmm0, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100404f98  xor     r15d, r15d
0x100404f9b  lea     rsi, [rcx+290h]
0x100404fa2  mov     rbx, rcx
0x100404fa5  movups  xmmword ptr [rcx+280h], xmm0
0x100404fac  mov     [rsi], r15w
0x100404fb0  mov     [rcx+2B0h], r15d
0x100404fb7  mov     [rcx+478h], r15d
0x100404fbe  movups  xmm0, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100404fc5  movups  xmmword ptr [rcx+260h], xmm0
0x100404fcc  movups  xmm0, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100404fd3  mov     [rcx+45Ch], r15d
0x100404fda  movups  xmmword ptr [rcx+270h], xmm0
0x100404fe1  call    ?Clear@SXReadBase@@IEAAXXZ; SXReadBase::Clear(void)
0x100404fe6  mov     rcx, rbx; this
0x100404fe9  call    ?XmlNsReset@SXReadBase@@IEAAXXZ; SXReadBase::XmlNsReset(void)
0x100404fee  mov     rcx, [rbx+8]; struct IMalloc *
0x100404ff2  lea     rdx, [rbx+2D0h]; struct SXTokenTable **
0x100404ff9  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x100404ffe  mov     rcx, [rbx+5C8h]
0x100405005  test    rcx, rcx
0x100405008  jz      short loc_100405026
0x10040500a  mov     rax, [rcx]
0x10040500d  lea     rdx, [rbx+5B8h]
0x100405014  mov     rax, [rax+18h]
0x100405018  call    cs:__guard_dispatch_icall_fptr
0x10040501e  test    eax, eax
0x100405020  js      loc_100405597
0x100405026  mov     rcx, rbx; this
0x100405029  mov     [rsp+98h+arg_8], rdi
0x100405031  call    ?GetNextBaseToken@SXReadBase@@IEAAEXZ; SXReadBase::GetNextBaseToken(void)
0x100405036  movzx   edi, al
0x100405039  cmp     al, 0FEh
0x10040503b  jnz     short loc_100405075
0x10040503d  mov     eax, [rbx+2B0h]
0x100405043  mov     rcx, rbx; this
0x100405046  mov     [rbx+268h], eax
0x10040504c  mov     rax, [rbx+470h]
0x100405053  mov     [rbx+270h], rax
0x10040505a  mov     eax, [rbx+478h]
0x100405060  mov     [rbx+278h], eax
0x100405066  mov     [rbx+260h], rsi
0x10040506d  call    ?GetNextBaseToken@SXReadBase@@IEAAEXZ; SXReadBase::GetNextBaseToken(void)
0x100405072  movzx   edi, al
0x100405075  mov     rcx, [rbx+5C8h]
0x10040507c  test    rcx, rcx
0x10040507f  jz      short loc_100405096
0x100405081  mov     rax, [rcx]
0x100405084  mov     rax, [rax+20h]
0x100405088  call    cs:__guard_dispatch_icall_fptr
0x10040508e  test    eax, eax
0x100405090  js      loc_1004055A2
0x100405096  mov     [rsp+98h+arg_0], rbp
0x10040509e  test    dil, dil
0x1004050a1  jz      loc_100405555
0x1004050a7  lea     rbp, __ImageBase
0x1004050ae  xchg    ax, ax
0x1004050b0  movzx   edx, dil
0x1004050b4  lea     eax, [rdx-1]; switch 252 cases
0x1004050b7  cmp     eax, 0FBh
0x1004050bc  ja      def_1004050D6; jumptable 00000001004050D6 default case, cases 21,25,26,28-127,141-234,237-240,245,246,249-251
0x1004050c2  cdqe
0x1004050c4  movzx   eax, ds:(byte_100405684 - 100400000h)[rax+rbp]
0x1004050cc  mov     ecx, ss:(jpt_1004050D6 - 100400000h)[rbp+rax*4]
0x1004050d3  add     rcx, rbp
0x1004050d6  jmp     rcx; switch jump
0x1004050d8  mov     rcx, [rbx+5D0h]; jumptable 00000001004050D6 case 243
0x1004050df  test    rcx, rcx
0x1004050e2  jz      loc_100405542
0x1004050e8  mov     rax, [rcx]
0x1004050eb  mov     r8d, [rbx+2C8h]
0x1004050f2  mov     rdx, [rbx+2C0h]
0x1004050f9  mov     rax, [rax+48h]
0x1004050fd  call    cs:__guard_dispatch_icall_fptr
0x100405103  test    eax, eax
0x100405105  js      loc_1004055AD
0x10040510b  jmp     loc_100405542
0x100405110  mov     rcx, [rbx+5C8h]; jumptable 00000001004050D6 case 244
0x100405117  test    rcx, rcx
0x10040511a  jz      loc_100405542
0x100405120  mov     edx, [rbx+538h]
0x100405126  mov     rax, [rcx]
0x100405129  mov     r9, [rbx+540h]
0x100405130  mov     r8d, [rbx+528h]
0x100405137  mov     [rsp+98h+var_78], edx
0x10040513b  mov     rax, [rax+60h]
0x10040513f  mov     rdx, [rbx+520h]
0x100405146  call    cs:__guard_dispatch_icall_fptr
0x10040514c  test    eax, eax
0x10040514e  js      loc_1004055B8
0x100405154  jmp     loc_100405542
0x100405159  cmp     [rbx+5C4h], r15b; jumptable 00000001004050D6 case 242
0x100405160  jnz     short loc_10040518A
0x100405162  mov     rcx, [rbx+5D0h]
0x100405169  test    rcx, rcx
0x10040516c  jz      short loc_10040518A
0x10040516e  mov     rax, [rcx]
0x100405171  mov     rax, [rax+38h]
0x100405175  call    cs:__guard_dispatch_icall_fptr
0x10040517b  test    eax, eax
0x10040517d  js      loc_1004055FA
0x100405183  mov     byte ptr [rbx+5C4h], 1
0x10040518a  mov     rcx, [rbx+5C8h]
0x100405191  test    rcx, rcx
0x100405194  jz      loc_100405542
0x10040519a  mov     rax, [rcx]
0x10040519d  mov     r8d, [rbx+47Ch]
0x1004051a4  mov     rdx, [rbx+480h]
0x1004051ab  mov     rax, [rax+50h]
0x1004051af  call    cs:__guard_dispatch_icall_fptr
0x1004051b5  test    eax, eax
0x1004051b7  js      loc_1004055C3
0x1004051bd  jmp     loc_100405542
0x1004051c2  mov     rcx, [rbx+5D0h]; jumptable 00000001004050D6 case 241
0x1004051c9  test    rcx, rcx
0x1004051cc  jz      short loc_1004051E3
0x1004051ce  mov     rax, [rcx]
0x1004051d1  mov     rax, [rax+40h]
0x1004051d5  call    cs:__guard_dispatch_icall_fptr
0x1004051db  test    eax, eax
0x1004051dd  js      loc_100405605
0x1004051e3  mov     [rbx+5C4h], r15b
0x1004051ea  jmp     loc_100405542
0x1004051ef  mov     rcx, rbx; jumptable 00000001004050D6 case 248
0x1004051f2  call    ?ElementT@SXReader@@AEAAXXZ; SXReader::ElementT(void)
0x1004051f7  jmp     loc_100405542
0x1004051fc  mov     rcx, [rbx+5D8h]; jumptable 00000001004050D6 cases 1-20,22-24,27,128-139
0x100405203  test    rcx, rcx
0x100405206  jz      short loc_100405259
0x100405208  cmp     dil, 80h
0x10040520c  lea     eax, [rdx-64h]
0x10040520f  cmovb   eax, edx
0x100405212  cdqe
0x100405214  movzx   r8d, ss:rva ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A[rbp+rax*8]; SXFORMATTYPEDATA near * SXFormatDataByType ...
0x10040521d  test    r8b, 40h
0x100405221  jz      short loc_10040523D
0x100405223  mov     eax, [rbx+2B8h]
0x100405229  mov     r8d, [rbx+488h]
0x100405230  test    eax, eax
0x100405232  jz      short loc_10040523D
0x100405234  cmp     r8d, eax
0x100405237  ja      loc_100405610
0x10040523d  mov     rax, [rcx]
0x100405240  lea     r9, [rbx+438h]
0x100405247  mov     rax, [rax+18h]
0x10040524b  call    cs:__guard_dispatch_icall_fptr
0x100405251  test    eax, eax
0x100405253  js      loc_10040561B
0x100405259  cmp     [rbx+448h], r15
0x100405260  jnz     loc_100405542
0x100405266  mov     esi, [rbx+450h]
0x10040526c  mov     rdi, [rbx+440h]
0x100405273  test    esi, esi
0x100405275  jz      loc_100405542
0x10040527b  nop     dword ptr [rax+rax+00h]
0x100405280  mov     ecx, [rdi+598h]
0x100405286  mov     eax, esi
0x100405288  sub     ecx, [rdi+590h]
0x10040528e  cmp     ecx, esi
0x100405290  cmovb   eax, ecx
0x100405293  add     [rdi+590h], rax
0x10040529a  sub     esi, eax
0x10040529c  jz      loc_100405542
0x1004052a2  mov     rcx, rdi; this
0x1004052a5  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x1004052aa  test    al, al
0x1004052ac  jz      loc_1004055CE
0x1004052b2  jmp     short loc_100405280
0x1004052b4  mov     rcx, rbx; jumptable 00000001004050D6 case 140
0x1004052b7  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x1004052bc  mov     rdx, [rbx+2D0h]
0x1004052c3  cmp     eax, [rdx+74h]
0x1004052c6  jnb     def_1004050D6; jumptable 00000001004050D6 default case, cases 21,25,26,28-127,141-234,237-240,245,246,249-251
0x1004052cc  mov     eax, eax
0x1004052ce  lea     rcx, [rax+rax*4]
0x1004052d2  mov     rax, [rdx+78h]
0x1004052d6  lea     rdx, [rax+rcx*8]
0x1004052da  cmp     [rbx+5D8h], r15
0x1004052e1  jz      loc_100405542
0x1004052e7  lfence
0x1004052ea  mov     rcx, [rdx]
0x1004052ed  lea     r9, [rbx+438h]
0x1004052f4  lea     rax, [rcx+18h]
0x1004052f8  mov     [rsp+98h+var_48], rax
0x1004052fd  mov     eax, [rcx+10h]
0x100405300  mov     rcx, [rdx+8]
0x100405304  mov     [rsp+98h+var_40], eax
0x100405308  lea     rax, [rcx+18h]
0x10040530c  mov     [rsp+98h+var_38], rax
0x100405311  mov     eax, [rcx+10h]
0x100405314  mov     rcx, [rdx+10h]
0x100405318  mov     edx, 8Dh
0x10040531d  mov     [rsp+98h+var_30], eax
0x100405321  lea     rax, [rcx+18h]
0x100405325  mov     [rsp+98h+var_28], rax
0x10040532a  lea     r8d, [rdx-5Dh]
0x10040532e  mov     eax, [rcx+10h]
0x100405331  mov     [rsp+98h+var_20], eax
0x100405335  lea     rax, [rsp+98h+var_48]
0x10040533a  mov     [rbx+448h], rax
0x100405341  mov     dword ptr [rbx+450h], 30h ; '0'
0x10040534b  mov     rcx, [rbx+5D8h]
0x100405352  mov     rax, [rcx]
0x100405355  mov     rax, [rax+18h]
0x100405359  call    cs:__guard_dispatch_icall_fptr
0x10040535f  test    eax, eax
0x100405361  js      loc_100405626
0x100405367  mov     [rbx+448h], r15
0x10040536e  mov     [rbx+450h], r15d
0x100405375  jmp     loc_100405542
0x10040537a  mov     rcx, [rbx+5C8h]; jumptable 00000001004050D6 case 247
0x100405381  test    rcx, rcx
0x100405384  jz      short loc_1004053D6
0x100405386  mov     r8, [rbx+498h]
0x10040538d  mov     r11, [rbx+4A8h]
0x100405394  mov     r10d, [rbx+4C0h]
0x10040539b  mov     rax, [rcx]
0x10040539e  mov     [rsp+98h+var_68], r10d
0x1004053a3  lea     rdx, [r8+18h]
0x1004053a7  mov     r10, [rbx+4B8h]
0x1004053ae  lea     r9, [r11+18h]
0x1004053b2  mov     r8d, [r8+10h]
0x1004053b6  mov     rax, [rax+48h]
0x1004053ba  mov     [rsp+98h+var_70], r10
0x1004053bf  mov     r10d, [r11+10h]
0x1004053c3  mov     [rsp+98h+var_78], r10d
0x1004053c8  call    cs:__guard_dispatch_icall_fptr
0x1004053ce  test    eax, eax
0x1004053d0  js      loc_100405631
0x1004053d6  mov     esi, [rbx+468h]
0x1004053dc  mov     eax, [rbx+78h]
0x1004053df  inc     esi
0x1004053e1  test    eax, eax
0x1004053e3  jz      loc_100405542
0x1004053e9  nop     dword ptr [rax+00000000h]
0x1004053f0  lea     eax, [rax-1]
0x1004053f3  lea     rdi, [rax+rax*2]
0x1004053f7  shl     rdi, 4
0x1004053fb  add     rdi, [rbx+70h]
0x1004053ff  cmp     [rdi+1Ch], esi
0x100405402  jl      loc_100405542
0x100405408  mov     ecx, [rdi+18h]
0x10040540b  mov     rax, [rbx]
0x10040540e  mov     r9, [rdi+10h]
0x100405412  mov     r8d, [rdi+8]
0x100405416  mov     rdx, [rdi]
0x100405419  mov     rax, [rax+20h]
0x10040541d  mov     [rsp+98h+var_78], ecx
0x100405421  mov     rcx, rbx
0x100405424  call    cs:__guard_dispatch_icall_fptr
0x10040542a  mov     eax, [rdi+24h]
0x10040542d  xor     edx, edx
0x10040542f  div     dword ptr [rbx+54h]
0x100405432  mov     rcx, [rbx+58h]
0x100405436  mov     eax, [rdi+28h]
0x100405439  mov     [rcx+rdx*4], eax
0x10040543c  mov     r8, [rdi]; lpMem
0x10040543f  test    r8, r8
0x100405442  jz      short loc_10040547A
0x100405444  mov     rcx, [rbx+8]
0x100405448  test    rcx, rcx
0x10040544b  jnz     short loc_100405459
0x10040544d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100405454  test    rcx, rcx
0x100405457  jz      short loc_10040546B
0x100405459  mov     rax, [rcx]
0x10040545c  mov     rdx, r8
0x10040545f  mov     rax, [rax+28h]
0x100405463  call    cs:__guard_dispatch_icall_fptr
0x100405469  jmp     short loc_10040547A
0x10040546b  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100405472  xor     edx, edx; dwFlags
0x100405474  call    cs:__imp_HeapFree
0x10040547a  add     dword ptr [rbx+78h], 0FFFFFFFFh
0x10040547e  mov     eax, [rbx+78h]
0x100405481  jnz     loc_1004053F0
0x100405487  jmp     loc_100405542
0x10040548c  mov     rcx, [rbx+5D8h]; jumptable 00000001004050D6 case 252
0x100405493  test    rcx, rcx
0x100405496  jz      loc_100405542
0x10040549c  mov     edx, [rbx+560h]
0x1004054a2  mov     rax, [rcx]
0x1004054a5  mov     r9, [rbx+568h]
0x1004054ac  mov     r8d, [rbx+550h]
0x1004054b3  mov     [rsp+98h+var_58], edx
0x1004054b7  mov     rdx, [rbx+558h]
0x1004054be  mov     rax, [rax+20h]
0x1004054c2  mov     [rsp+98h+var_60], rdx
0x1004054c7  mov     edx, [rbx+580h]
0x1004054cd  mov     [rsp+98h+var_68], edx
0x1004054d1  mov     rdx, [rbx+578h]
0x1004054d8  mov     [rsp+98h+var_70], rdx
0x1004054dd  mov     edx, [rbx+570h]
0x1004054e3  mov     [rsp+98h+var_78], edx
0x1004054e7  mov     rdx, [rbx+548h]
  ... truncated ...
```
