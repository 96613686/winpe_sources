# EncodingWriter::ResolveErrors(wchar_t const *,uint,uchar const *,uint)

- ea: `0x100423260`
- end: `0x100423641`
- name: `?ResolveErrors@EncodingWriter@@IEAAJPEB_WIPEBEI@Z`
- size: `993`
- prototype: `__int64 __usercall@<rax>(EncodingWriter *__hidden this@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x100423100`

## callees

- `0x100401520`
- `0x100420450`
- `0x100423100`
- `0x100423260`
- `0x100426580`
- `0x1004394f0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004233e6`
- `KERNEL32!HeapAlloc` at `0x1004233e6`
- `KERNEL32!HeapFree` at `0x1004233a0`
- `KERNEL32!HeapFree` at `0x1004233a0`

## pseudocode

```c
__int64 __fastcall EncodingWriter::ResolveErrors(
        EncodingWriter *this,
        const wchar_t *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  bool v5; // zf
  __int64 v10; // rbx
  int CharsetInfo; // eax
  int (*v12)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *); // rax
  unsigned int v13; // ebx
  void *v14; // r8
  struct IMalloc *v15; // rcx
  __int64 result; // rax
  struct IMalloc *v17; // rcx
  LPVOID v18; // rax
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(int *, __int64, const unsigned __int8 *, unsigned int *, _WORD *, unsigned int *); // rax
  _WORD *v21; // rsi
  const wchar_t *v22; // rdx
  unsigned int v23; // r8d
  unsigned int i; // ebx
  unsigned int v25; // ebx
  __int64 v26; // rax
  unsigned int v27; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-7Dh] BYREF
  unsigned int Size; // [rsp+48h] [rbp-79h] BYREF
  unsigned int Size_4; // [rsp+4Ch] [rbp-75h] BYREF
  int v31; // [rsp+50h] [rbp-71h] BYREF
  int v32; // [rsp+54h] [rbp-6Dh] BYREF
  unsigned int v33; // [rsp+58h] [rbp-69h] BYREF
  _BYTE Buf2[32]; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v35[64]; // [rsp+80h] [rbp-41h] BYREF

  v5 = *((_QWORD *)this + 11) == 0;
  v32 = 0;
  if ( v5 )
  {
    v10 = *((_QWORD *)this + 2);
    CharsetInfo = CharEncoder::getCharsetInfo(*(const wchar_t **)(v10 + 16), &Size_4, &v33);
    if ( CharsetInfo < 0 )
    {
      if ( CharsetInfo != -1 || CanConvertToUnicode(Size_4) )
      {
        _mm_lfence();
        return 3222070638LL;
      }
      v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))CharEncoder::wideCharFromMultiByteMlang;
    }
    else
    {
      switch ( Size_4 )
      {
        case 0x4B0u:
          v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))CharEncoder::wideCharFromUtf16Bigendian;
          if ( *(_BYTE *)(v10 + 24) )
            v12 = CharEncoder::wideCharFromUtf16Littleendian;
          break;
        case 0x2EE0u:
          v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))CharEncoder::wideCharFromUcs4Littleendian;
          if ( !*(_BYTE *)(v10 + 24) )
            v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))CharEncoder::wideCharFromUcs4Bigendian;
          break;
        case 0x10001u:
          v12 = CharEncoder::wideCharFromUcs2Littleendian;
          if ( !*(_BYTE *)(v10 + 24) )
            v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))CharEncoder::wideCharFromUcs2Bigendian;
          break;
        default:
          v12 = (int (*)(unsigned int *, unsigned int, unsigned __int8 *, unsigned int *, wchar_t *, unsigned int *))*(&off_100445AE8 + 5 * CharsetInfo);
          break;
      }
    }
    *((_QWORD *)this + 11) = v12;
  }
  v13 = 2 * a3;
  if ( *((_DWORD *)this + 18) >= 2 * a3 )
    goto LABEL_36;
  v14 = (void *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v15 || (v15 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v15->lpVtbl->Free)(v15, *((_QWORD *)this + 8));
    else
      HeapFree(g_hHeap, 0, v14);
  }
  v17 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v17 )
  {
    _mm_lfence();
  }
  else
  {
    v5 = g_pMalloc == 0;
    _mm_lfence();
    if ( v5 )
    {
      v18 = HeapAlloc(g_hHeap, 0, v13);
      goto LABEL_33;
    }
    v17 = g_pMalloc;
  }
  v18 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))v17->lpVtbl->Alloc)(v17, v13);
LABEL_33:
  *((_QWORD *)this + 8) = v18;
  if ( !v18 )
    return 2147942414LL;
  *((_DWORD *)this + 18) = v13;
LABEL_36:
  v19 = *((unsigned int *)this + 6);
  v20 = (__int64 (__fastcall *)(int *, __int64, const unsigned __int8 *, unsigned int *, _WORD *, unsigned int *))*((_QWORD *)this + 11);
  v21 = (_WORD *)*((_QWORD *)this + 8);
  v27 = a3;
  result = v20(&v32, v19, a4, &a5, v21, &v27);
  if ( (int)result < 0 )
    goto LABEL_37;
  v22 = a2;
  if ( a3 )
  {
    v23 = v27;
    do
    {
      if ( *a2 == *v21 )
      {
        ++a2;
        --a3;
        ++v21;
        --v23;
      }
      else
      {
        result = EncodingWriter::WriteString(this, v22, a2 - v22);
        _mm_lfence();
        if ( (int)result < 0 )
          return result;
        if ( *v21 == asc_100444F80[0] )
        {
          v25 = 2 - ((unsigned __int16)(*a2 + 10240) > 0x3FFu);
          result = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**((_QWORD **)this + 10) + 8LL))(
                     *((_QWORD *)this + 10),
                     a2);
          if ( (int)result < 0 )
            goto LABEL_37;
          a3 -= v25;
          v23 = v27 - v25;
          v26 = 2LL * v25;
          v21 = (_WORD *)((char *)v21 + v26);
          a2 = (const wchar_t *)((char *)a2 + v26);
          v22 = a2;
        }
        else
        {
          for ( i = 1; ; ++i )
          {
            v31 = 64;
            Size = 16;
            v28 = i;
            if ( i > a3 )
              return 2147500037LL;
            result = (*((__int64 (__fastcall **)(char *, _QWORD, const wchar_t *, unsigned int *, _BYTE *, int *))this
                      + 12))(
                       (char *)this + 32,
                       *((unsigned int *)this + 6),
                       a2,
                       &v28,
                       v35,
                       &v31);
            _mm_lfence();
            if ( (int)result < 0 )
              return result;
            result = (*((__int64 (__fastcall **)(int *, _QWORD, _BYTE *, int *, _BYTE *, unsigned int *))this + 11))(
                       &v32,
                       *((unsigned int *)this + 6),
                       v35,
                       &v31,
                       Buf2,
                       &Size);
            if ( (int)result < 0 )
              goto LABEL_37;
            if ( Size <= v27 && !memcmp(v21, Buf2, Size) )
              break;
          }
          _mm_lfence();
          result = EncodingWriter::WriteString(this, v21, v28);
          if ( (int)result < 0 )
            goto LABEL_37;
          a3 -= v28;
          v23 = v27 - Size;
          a2 += v28;
          v22 = a2;
          v21 += Size;
        }
      }
      v27 = v23;
    }
    while ( a3 );
  }
  result = EncodingWriter::WriteString(this, v22, a2 - v22);
  if ( (int)result >= 0 )
    return 0;
LABEL_37:
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x100423260  push    rbp
0x100423262  push    rbx
0x100423263  push    rdi
0x100423264  push    r12
0x100423266  push    r14
0x100423268  push    r15
0x10042326a  lea     rbp, [rsp-27h]
0x10042326f  sub     rsp, 0E8h
0x100423276  mov     rax, cs:__security_cookie
0x10042327d  xor     rax, rsp
0x100423280  mov     [rbp+4Fh+var_50], rax
0x100423284  cmp     qword ptr [rcx+58h], 0
0x100423289  mov     r12, r9
0x10042328c  mov     r14d, r8d
0x10042328f  mov     [rbp+4Fh+var_BC], 0
0x100423296  mov     r15, rdx
0x100423299  mov     rdi, rcx
0x10042329c  jnz     loc_10042334D
0x1004232a2  mov     rbx, [rcx+10h]
0x1004232a6  lea     r8, [rbp+4Fh+var_B8]; unsigned int *
0x1004232aa  lea     rdx, [rbp+4Fh+Size+4]; unsigned int *
0x1004232ae  mov     rcx, [rbx+10h]; wchar_t *
0x1004232b2  call    ?getCharsetInfo@CharEncoder@@SAHPEB_WPEAI1@Z; CharEncoder::getCharsetInfo(wchar_t const *,uint *,uint *)
0x1004232b7  test    eax, eax
0x1004232b9  js      short loc_100423331
0x1004232bb  mov     ecx, dword ptr [rbp+4Fh+Size+4]
0x1004232be  cmp     ecx, 4B0h
0x1004232c4  jz      short loc_100423319
0x1004232c6  cmp     ecx, 2EE0h
0x1004232cc  jz      short loc_100423301
0x1004232ce  cmp     ecx, 10001h
0x1004232d4  jz      short loc_1004232E9
0x1004232d6  cdqe
0x1004232d8  lea     rcx, [rax+rax*4]
0x1004232dc  lea     rax, off_100445AE8
0x1004232e3  mov     rax, [rax+rcx*8]
0x1004232e7  jmp     short loc_100423349
0x1004232e9  cmp     byte ptr [rbx+18h], 0
0x1004232ed  lea     rax, ?wideCharFromUcs2Littleendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUcs2Littleendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x1004232f4  lea     rcx, ?wideCharFromUcs2Bigendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUcs2Bigendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x1004232fb  cmovz   rax, rcx
0x1004232ff  jmp     short loc_100423349
0x100423301  cmp     byte ptr [rbx+18h], 0
0x100423305  lea     rax, ?wideCharFromUcs4Littleendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUcs4Littleendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x10042330c  lea     rcx, ?wideCharFromUcs4Bigendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUcs4Bigendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x100423313  cmovz   rax, rcx
0x100423317  jmp     short loc_100423349
0x100423319  cmp     byte ptr [rbx+18h], 0
0x10042331d  lea     rax, ?wideCharFromUtf16Bigendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUtf16Bigendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x100423324  lea     rcx, ?wideCharFromUtf16Littleendian@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromUtf16Littleendian(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x10042332b  cmovnz  rax, rcx
0x10042332f  jmp     short loc_100423349
0x100423331  cmp     eax, 0FFFFFFFFh
0x100423334  jnz     short loc_10042338A
0x100423336  mov     ecx, dword ptr [rbp+4Fh+Size+4]; unsigned int
0x100423339  call    ?CanConvertToUnicode@@YAJI@Z; CanConvertToUnicode(uint)
0x10042333e  test    eax, eax
0x100423340  jnz     short loc_10042338A
0x100423342  lea     rax, ?wideCharFromMultiByteMlang@CharEncoder@@SAJPEAKIPEAEPEAIPEA_W2@Z; CharEncoder::wideCharFromMultiByteMlang(ulong *,uint,uchar *,uint *,wchar_t *,uint *)
0x100423349  mov     [rdi+58h], rax
0x10042334d  lea     ebx, [r14+r14]
0x100423351  cmp     [rdi+48h], ebx
0x100423354  jnb     loc_100423402
0x10042335a  mov     r8, [rdi+40h]; lpMem
0x10042335e  test    r8, r8
0x100423361  jz      short loc_1004233A6
0x100423363  mov     rcx, [rdi+8]
0x100423367  test    rcx, rcx
0x10042336a  jnz     short loc_100423378
0x10042336c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100423373  test    rcx, rcx
0x100423376  jz      short loc_100423397
0x100423378  mov     rax, [rcx]
0x10042337b  mov     rdx, r8
0x10042337e  mov     rax, [rax+28h]
0x100423382  call    cs:__guard_dispatch_icall_fptr
0x100423388  jmp     short loc_1004233A6
0x10042338a  lfence
0x10042338d  mov     eax, 0C00CE56Eh
0x100423392  jmp     loc_100423624
0x100423397  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10042339e  xor     edx, edx; dwFlags
0x1004233a0  call    cs:__imp_HeapFree
0x1004233a6  mov     rcx, [rdi+8]
0x1004233aa  mov     r8d, ebx; dwBytes
0x1004233ad  test    rcx, rcx
0x1004233b0  jz      short loc_1004233B7
0x1004233b2  lfence
0x1004233b5  jmp     short loc_1004233CB
0x1004233b7  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x1004233bf  lfence
0x1004233c2  jz      short loc_1004233DD
0x1004233c4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004233cb  mov     rax, [rcx]
0x1004233ce  mov     rdx, r8
0x1004233d1  mov     rax, [rax+18h]
0x1004233d5  call    cs:__guard_dispatch_icall_fptr
0x1004233db  jmp     short loc_1004233EC
0x1004233dd  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004233e4  xor     edx, edx; dwFlags
0x1004233e6  call    cs:__imp_HeapAlloc
0x1004233ec  mov     [rdi+40h], rax
0x1004233f0  test    rax, rax
0x1004233f3  jnz     short loc_1004233FF
0x1004233f5  mov     eax, 8007000Eh
0x1004233fa  jmp     loc_100423624
0x1004233ff  mov     [rdi+48h], ebx
0x100423402  mov     edx, [rdi+18h]
0x100423405  lea     rax, [rsp+110h+var_D0]
0x10042340a  mov     [rsp+110h+var_E8], rax
0x10042340f  lea     r9, [rbp+4Fh+arg_20]
0x100423413  mov     rax, [rdi+58h]
0x100423417  lea     rcx, [rbp+4Fh+var_BC]
0x10042341b  mov     [rsp+110h+var_30], rsi
0x100423423  mov     r8, r12
0x100423426  mov     rsi, [rdi+40h]
0x10042342a  mov     [rsp+110h+var_D0], r14d
0x10042342f  mov     [rsp+110h+var_F0], rsi
0x100423434  call    cs:__guard_dispatch_icall_fptr
0x10042343a  test    eax, eax
0x10042343c  jns     short loc_100423446
0x10042343e  lfence
0x100423441  jmp     loc_10042361C
0x100423446  mov     [rsp+110h+var_38], r13
0x10042344e  mov     rdx, r15; wchar_t *
0x100423451  test    r14d, r14d
0x100423454  jz      loc_1004235F1
0x10042345a  mov     r8d, [rsp+110h+var_D0]
0x10042345f  mov     r12d, 2800h
0x100423465  mov     r13d, 3FFh
0x10042346b  nop     dword ptr [rax+rax+00h]
0x100423470  movzx   eax, word ptr [rsi]
0x100423473  cmp     [r15], ax
0x100423477  jz      loc_1004235D5
0x10042347d  mov     r8, r15
0x100423480  mov     rcx, rdi; this
0x100423483  sub     r8, rdx
0x100423486  sar     r8, 1; unsigned int
0x100423489  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x10042348e  lfence
0x100423491  test    eax, eax
0x100423493  js      loc_100423614
0x100423499  movzx   eax, word ptr cs:asc_100444F80; "?"
0x1004234a0  cmp     [rsi], ax
0x1004234a3  jz      loc_100423591
0x1004234a9  mov     ebx, 1
0x1004234ae  xchg    ax, ax
0x1004234b0  mov     [rbp+4Fh+var_C0], 40h ; '@'
0x1004234b7  mov     dword ptr [rbp+4Fh+Size], 10h
0x1004234be  mov     [rbp+4Fh+var_CC], ebx
0x1004234c1  cmp     ebx, r14d
0x1004234c4  ja      loc_10042360B
0x1004234ca  mov     edx, [rdi+18h]
0x1004234cd  lea     rax, [rbp+4Fh+var_C0]
0x1004234d1  mov     [rsp+110h+var_E8], rax
0x1004234d6  lea     rcx, [rdi+20h]
0x1004234da  lea     rax, [rbp+4Fh+var_90]
0x1004234de  mov     r8, r15
0x1004234e1  mov     [rsp+110h+var_F0], rax
0x1004234e6  lea     r9, [rbp+4Fh+var_CC]
0x1004234ea  mov     rax, [rdi+60h]
0x1004234ee  call    cs:__guard_dispatch_icall_fptr
0x1004234f4  lfence
0x1004234f7  test    eax, eax
0x1004234f9  js      loc_100423614
0x1004234ff  mov     edx, [rdi+18h]
0x100423502  lea     rax, [rbp+4Fh+Size]
0x100423506  mov     [rsp+110h+var_E8], rax
0x10042350b  lea     r9, [rbp+4Fh+var_C0]
0x10042350f  lea     rax, [rbp+4Fh+Buf2]
0x100423513  mov     [rsp+110h+var_F0], rax
0x100423518  lea     r8, [rbp+4Fh+var_90]
0x10042351c  mov     rax, [rdi+58h]
0x100423520  lea     rcx, [rbp+4Fh+var_BC]
0x100423524  call    cs:__guard_dispatch_icall_fptr
0x10042352a  test    eax, eax
0x10042352c  js      loc_100423606
0x100423532  mov     eax, dword ptr [rbp+4Fh+Size]
0x100423535  cmp     eax, [rsp+110h+var_D0]
0x100423539  ja      short loc_10042354E
0x10042353b  mov     r8d, eax; Size
0x10042353e  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x100423542  mov     rcx, rsi; Buf1
0x100423545  call    memcmp
0x10042354a  test    eax, eax
0x10042354c  jz      short loc_100423555
0x10042354e  inc     ebx
0x100423550  jmp     loc_1004234B0
0x100423555  lfence
0x100423558  mov     r8d, [rbp+4Fh+var_CC]; unsigned int
0x10042355c  mov     rdx, rsi; wchar_t *
0x10042355f  mov     rcx, rdi; this
0x100423562  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x100423567  test    eax, eax
0x100423569  js      loc_100423606
0x10042356f  mov     edx, [rbp+4Fh+var_CC]
0x100423572  mov     ecx, dword ptr [rbp+4Fh+Size]
0x100423575  mov     eax, edx
0x100423577  mov     r8d, [rsp+110h+var_D0]
0x10042357c  sub     r14d, edx
0x10042357f  add     rax, rax
0x100423582  sub     r8d, ecx
0x100423585  add     r15, rax
0x100423588  mov     rdx, r15
0x10042358b  lea     rsi, [rsi+rcx*2]
0x10042358f  jmp     short loc_1004235E3
0x100423591  movzx   eax, word ptr [r15]
0x100423595  mov     rdx, r15
0x100423598  mov     rcx, [rdi+50h]
0x10042359c  add     ax, r12w
0x1004235a0  cmp     r13w, ax
0x1004235a4  sbb     ebx, ebx
0x1004235a6  mov     rax, [rcx]
0x1004235a9  add     ebx, 2
0x1004235ac  mov     rax, [rax+8]
0x1004235b0  call    cs:__guard_dispatch_icall_fptr
0x1004235b6  test    eax, eax
0x1004235b8  js      short loc_100423606
0x1004235ba  mov     r8d, [rsp+110h+var_D0]
0x1004235bf  sub     r14d, ebx
0x1004235c2  mov     eax, ebx
0x1004235c4  sub     r8d, ebx
0x1004235c7  add     rax, rax
0x1004235ca  add     rsi, rax
0x1004235cd  add     r15, rax
0x1004235d0  mov     rdx, r15
0x1004235d3  jmp     short loc_1004235E3
0x1004235d5  add     r15, 2
0x1004235d9  dec     r14d
0x1004235dc  add     rsi, 2
0x1004235e0  dec     r8d
0x1004235e3  mov     [rsp+110h+var_D0], r8d
0x1004235e8  test    r14d, r14d
0x1004235eb  jnz     loc_100423470
0x1004235f1  sub     r15, rdx
0x1004235f4  mov     rcx, rdi; this
0x1004235f7  sar     r15, 1
0x1004235fa  mov     r8d, r15d; unsigned int
0x1004235fd  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x100423602  test    eax, eax
0x100423604  jns     short loc_100423612
0x100423606  lfence
0x100423609  jmp     short loc_100423614
0x10042360b  mov     eax, 80004005h
0x100423610  jmp     short loc_100423614
0x100423612  xor     eax, eax
0x100423614  mov     r13, [rsp+110h+var_38]
0x10042361c  mov     rsi, [rsp+110h+var_30]
0x100423624  mov     rcx, [rbp+4Fh+var_50]
0x100423628  xor     rcx, rsp; StackCookie
0x10042362b  call    __security_check_cookie
0x100423630  add     rsp, 0E8h
0x100423637  pop     r15
0x100423639  pop     r14
0x10042363b  pop     r12
0x10042363d  pop     rdi
0x10042363e  pop     rbx
0x10042363f  pop     rbp
0x100423640  retn
```
