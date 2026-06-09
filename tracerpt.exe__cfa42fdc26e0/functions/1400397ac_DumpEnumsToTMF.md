# DumpEnumsToTMF

- ea: `0x1400397ac`
- end: `0x140039a75`
- name: `DumpEnumsToTMF`
- size: `713`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14003a0cc`

## callees

- `0x1400020e4`
- `0x140002bf0`
- `0x140038850`
- `0x140038dd0`
- `0x1400395b4`
- `0x1400397ac`
- `0x140041010`

## import_xrefs

- `msvcrt!_wfsopen` at `0x1400398d1`
- `msvcrt!_wfsopen` at `0x1400398d1`
- `msvcrt!fprintf` at `0x1400398ad`
- `msvcrt!fprintf` at `0x140039905`
- `msvcrt!fprintf` at `0x1400398ad`
- `msvcrt!fprintf` at `0x140039905`
- `msvcrt!fclose` at `0x1400397df`
- `msvcrt!fclose` at `0x1400399e7`
- `msvcrt!fclose` at `0x140039a16`
- `msvcrt!fclose` at `0x1400397df`
- `msvcrt!fclose` at `0x1400399e7`
- `msvcrt!fclose` at `0x140039a16`

## string_xrefs

- `0x1400398a6`: `WPPFMT : error : File + Path\n`

## pseudocode

```c
void __fastcall DumpEnumsToTMF(__int64 a1)
{
  unsigned int v1; // r15d
  FILE *v3; // rcx
  int v4; // r14d
  __int64 v5; // rsi
  __int64 v6; // rdi
  signed int v7; // eax
  FILE *v8; // rax
  unsigned __int16 v9; // bp
  __int64 v10; // r14
  _QWORD *v11; // r13
  __int64 v12; // r12
  wchar_t *FileName[2]; // [rsp+20h] [rbp-58h] BYREF
  _WORD v14[36]; // [rsp+30h] [rbp-48h] BYREF
  int v15; // [rsp+88h] [rbp+10h]

  v1 = 0;
  if ( PostProcessEnums )
  {
    v3 = TraceFileP;
    if ( TraceFileP )
    {
      fclose(TraceFileP);
      v3 = 0;
      TraceFileP = 0;
    }
    FileName[0] = v14;
    v4 = 0;
    v14[0] = 0;
    FileName[1] = v14;
    v15 = 0;
    if ( NextFreeGuid )
    {
      while ( 1 )
      {
        v5 = *(_QWORD *)&GuidHead.Data1;
        v6 = 56LL * (unsigned __int16)v4;
        if ( *(_QWORD *)(a1 + 32) || v3 )
          break;
        if ( SingleFile )
          v7 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                 (__int64)FileName,
                 g_SingleFileName,
                 ((char *)off_140060A08 - (_BYTE *)g_SingleFileName) >> 1) == 0
             ? 0x8007000E
             : 0;
        else
          v7 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                 FileName,
                 L"%ls\\%hs.tmf",
                 *(_QWORD *)(a1 + 16),
                 v6 + *(_QWORD *)&GuidHead.Data1 + 12LL);
        if ( v7 >= 0 )
        {
          TraceFileP = _wfsopen(FileName[0], L"a", 16);
          v3 = TraceFileP;
          if ( TraceFileP )
            break;
        }
        else
        {
          v8 = _acrt_iob_func(2u);
          fprintf(v8, "WPPFMT : error : File + Path\n");
          v3 = TraceFileP;
        }
LABEL_27:
        LOWORD(v4) = v4 + 1;
        v15 = v4;
        if ( (unsigned __int16)v4 >= NextFreeGuid )
          goto LABEL_28;
      }
      if ( SingleFile )
      {
        fprintf(v3, "%hs %ls\n", (const char *)(v6 + v5 + 12), *(const wchar_t **)(a1 + 8));
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 32) )
        {
LABEL_18:
          v9 = 0;
          if ( *(_WORD *)(v6 + v5 + 10) )
          {
            v10 = *(_QWORD *)(v6 + v5);
            do
            {
              v11 = EnumHead;
              v12 = 3LL * *(unsigned int *)(v10 + 4LL * v9);
              BufferPrintf(a1, "#enumv %hs\n{\n", *((const char **)EnumHead + 3 * *(unsigned int *)(v10 + 4LL * v9)));
              if ( LODWORD(v11[v12 + 2]) )
              {
                do
                {
                  BufferPrintf(
                    a1,
                    "%ls,0x%I64X\n",
                    *(const wchar_t **)(v11[v12 + 1] + 16LL * v1),
                    *(_QWORD *)(v11[v12 + 1] + 16LL * v1 + 8));
                  ++v1;
                }
                while ( v1 < LODWORD(v11[v12 + 2]) );
              }
              BufferPrintf(a1, "}\n");
              ++v9;
              v1 = 0;
            }
            while ( v9 < *(_WORD *)(v6 + v5 + 10) );
            v3 = TraceFileP;
            v4 = v15;
          }
          if ( !SingleFile && v3 )
          {
            fclose(v3);
            v3 = 0;
            TraceFileP = 0;
          }
          goto LABEL_27;
        }
        BufferPrintf(a1, "%hs %ls\n", (const char *)(v6 + v5 + 12), *(const wchar_t **)(a1 + 8));
      }
      v3 = TraceFileP;
      goto LABEL_18;
    }
LABEL_28:
    if ( v3 )
    {
      fclose(v3);
      TraceFileP = 0;
    }
    if ( *(_QWORD *)(a1 + 32) && *(_DWORD *)(a1 + 44) )
      (*(void (__fastcall **)(_QWORD))(a1 + 24))(**(_QWORD **)a1);
    if ( FileName[0] != v14 )
      operator delete(FileName[0], (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x1400397ac  mov     [rsp+arg_0], rbx
0x1400397b1  push    rbp
0x1400397b2  push    rsi
0x1400397b3  push    rdi
0x1400397b4  push    r12
0x1400397b6  push    r13
0x1400397b8  push    r14
0x1400397ba  push    r15
0x1400397bc  sub     rsp, 40h
0x1400397c0  xor     r15d, r15d
0x1400397c3  mov     rbx, rcx
0x1400397c6  cmp     cs:?PostProcessEnums@@3_NA, r15b; bool PostProcessEnums
0x1400397cd  jz      loc_140039A5D
0x1400397d3  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; Stream
0x1400397da  test    rcx, rcx
0x1400397dd  jz      short loc_1400397EF
0x1400397df  call    cs:__imp_fclose
0x1400397e5  mov     ecx, r15d
0x1400397e8  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rcx; _iobuf * TraceFileP
0x1400397ef  cmp     r15w, cs:?NextFreeGuid@@3GA; ushort NextFreeGuid
0x1400397f7  lea     rax, [rsp+78h+var_48]
0x1400397fc  mov     [rsp+78h+FileName], rax
0x140039801  mov     r14d, r15d
0x140039804  lea     rax, [rsp+78h+var_48]
0x140039809  mov     [rsp+78h+var_48], r15w
0x14003980f  mov     [rsp+78h+var_50], rax
0x140039814  mov     [rsp+78h+arg_8], r15d
0x14003981c  jnb     loc_140039A11
0x140039822  mov     r12d, 1
0x140039828  mov     rsi, qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1; GUID_POST_PROCESS_DATA * GuidHead ...
0x14003982f  movzx   eax, r14w
0x140039833  imul    rdi, rax, 38h ; '8'
0x140039837  cmp     [rbx+20h], r15
0x14003983b  jnz     loc_1400398EA
0x140039841  test    rcx, rcx
0x140039844  jnz     loc_1400398EA
0x14003984a  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x140039851  lea     rcx, [rsp+78h+FileName]
0x140039856  jz      short loc_14003987E
0x140039858  mov     r8, cs:off_140060A08
0x14003985f  mov     rdx, cs:?g_SingleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_SingleFileName
0x140039866  sub     r8, rdx
0x140039869  sar     r8, 1
0x14003986c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140039871  neg     al
0x140039873  sbb     eax, eax
0x140039875  not     eax
0x140039877  and     eax, 8007000Eh
0x14003987c  jmp     short loc_140039895
0x14003987e  mov     r8, [rbx+10h]
0x140039882  lea     r9, [rsi+0Ch]
0x140039886  add     r9, rdi
0x140039889  lea     rdx, aLsHsTmf; "%ls\\%hs.tmf"
0x140039890  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x140039895  test    eax, eax
0x140039897  jns     short loc_1400398BF
0x140039899  mov     ecx, 2; Ix
0x14003989e  call    __acrt_iob_func
0x1400398a3  mov     rcx, rax; Stream
0x1400398a6  lea     rdx, aWppfmtErrorFil_0; "WPPFMT : error : File + Path\n"
0x1400398ad  call    cs:__imp_fprintf
0x1400398b3  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x1400398ba  jmp     loc_1400399F7
0x1400398bf  mov     rcx, [rsp+78h+FileName]; FileName
0x1400398c4  lea     rdx, aA; "a"
0x1400398cb  mov     r8d, 10h; ShFlag
0x1400398d1  call    cs:__imp__wfsopen
0x1400398d7  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rax; _iobuf * TraceFileP
0x1400398de  mov     rcx, rax; Stream
0x1400398e1  test    rax, rax
0x1400398e4  jz      loc_1400399F7
0x1400398ea  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x1400398f1  jz      short loc_14003990D
0x1400398f3  mov     r9, [rbx+8]
0x1400398f7  lea     r8, [rsi+0Ch]
0x1400398fb  add     r8, rdi
0x1400398fe  lea     rdx, aHsLs; "%hs %ls\n"
0x140039905  call    cs:__imp_fprintf
0x14003990b  jmp     short loc_14003992D
0x14003990d  cmp     [rbx+20h], r15
0x140039911  jz      short loc_140039934
0x140039913  mov     r9, [rbx+8]
0x140039917  lea     r8, [rsi+0Ch]
0x14003991b  add     r8, rdi
0x14003991e  lea     rdx, aHsLs; "%hs %ls\n"
0x140039925  mov     rcx, rbx
0x140039928  call    BufferPrintf
0x14003992d  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x140039934  mov     ebp, r15d
0x140039937  mov     rax, [rdi+rsi]
0x14003993b  cmp     r15w, [rdi+rsi+0Ah]
0x140039941  jnb     loc_1400399D9
0x140039947  mov     r14, rax
0x14003994a  mov     r13, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x140039951  lea     rdx, aEnumvHs; "#enumv %hs\n{\n"
0x140039958  movzx   eax, bp
0x14003995b  mov     ecx, [r14+rax*4]
0x14003995f  lea     r12, [rcx+rcx*2]
0x140039963  mov     rcx, rbx
0x140039966  mov     r8, [r13+r12*8+0]
0x14003996b  call    BufferPrintf
0x140039970  cmp     dword ptr [r13+r12*8+10h], 0
0x140039976  jbe     short loc_1400399A5
0x140039978  mov     r8, [r13+r12*8+8]
0x14003997d  lea     rdx, aLs0xI64x; "%ls,0x%I64X\n"
0x140039984  mov     eax, r15d
0x140039987  mov     rcx, rbx
0x14003998a  add     rax, rax
0x14003998d  mov     r9, [r8+rax*8+8]
0x140039992  mov     r8, [r8+rax*8]
0x140039996  call    BufferPrintf
0x14003999b  inc     r15d
0x14003999e  cmp     r15d, [r13+r12*8+10h]
0x1400399a3  jb      short loc_140039978
0x1400399a5  lea     rdx, asc_140059C38; "}\n"
0x1400399ac  mov     rcx, rbx
0x1400399af  call    BufferPrintf
0x1400399b4  mov     r12d, 1
0x1400399ba  add     bp, r12w
0x1400399be  lea     r15d, [r12-1]
0x1400399c3  cmp     bp, [rdi+rsi+0Ah]
0x1400399c8  jb      short loc_14003994A
0x1400399ca  mov     rcx, cs:?TraceFileP@@3PEAU_iobuf@@EA; Stream
0x1400399d1  mov     r14d, [rsp+78h+arg_8]
0x1400399d9  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x1400399e0  jnz     short loc_1400399F7
0x1400399e2  test    rcx, rcx
0x1400399e5  jz      short loc_1400399F7
0x1400399e7  call    cs:__imp_fclose
0x1400399ed  mov     rcx, r15; Stream
0x1400399f0  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rcx; _iobuf * TraceFileP
0x1400399f7  add     r14w, r12w
0x1400399fb  cmp     r14w, cs:?NextFreeGuid@@3GA; ushort NextFreeGuid
0x140039a03  mov     [rsp+78h+arg_8], r14d
0x140039a0b  jb      loc_140039828
0x140039a11  test    rcx, rcx
0x140039a14  jz      short loc_140039A23
0x140039a16  call    cs:__imp_fclose
0x140039a1c  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, r15; _iobuf * TraceFileP
0x140039a23  mov     r8, [rbx+20h]
0x140039a27  test    r8, r8
0x140039a2a  jz      short loc_140039A42
0x140039a2c  mov     edx, [rbx+2Ch]
0x140039a2f  test    edx, edx
0x140039a31  jz      short loc_140039A42
0x140039a33  mov     rcx, [rbx]
0x140039a36  mov     rax, [rbx+18h]
0x140039a3a  mov     rcx, [rcx]
0x140039a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039a42  mov     rcx, [rsp+78h+FileName]; void *
0x140039a47  lea     rax, [rsp+78h+var_48]
0x140039a4c  cmp     rcx, rax
0x140039a4f  jz      short loc_140039A5D
0x140039a51  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039a58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140039a5d  mov     rbx, [rsp+78h+arg_0]
0x140039a65  add     rsp, 40h
0x140039a69  pop     r15
0x140039a6b  pop     r14
0x140039a6d  pop     r13
0x140039a6f  pop     r12
0x140039a71  pop     rdi
0x140039a72  pop     rsi
0x140039a73  pop     rbp
0x140039a74  retn
```
