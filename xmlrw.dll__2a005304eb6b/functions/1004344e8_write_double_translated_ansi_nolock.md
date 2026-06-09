# write_double_translated_ansi_nolock

- ea: `0x1004344e8`
- end: `0x10043495d`
- name: `write_double_translated_ansi_nolock`
- size: `1141`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x100434e28`

## callees

- `0x100425d50`
- `0x100426580`
- `0x10042d4f0`
- `0x100430244`
- `0x100432868`
- `0x1004344e8`
- `0x100436cc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043492b`
- `KERNEL32!GetLastError` at `0x10043492b`
- `KERNEL32!WriteFile` at `0x10043482f`
- `KERNEL32!WriteFile` at `0x100434875`
- `KERNEL32!WriteFile` at `0x10043482f`
- `KERNEL32!WriteFile` at `0x100434875`
- `KERNEL32!GetConsoleOutputCP` at `0x100434567`
- `KERNEL32!GetConsoleOutputCP` at `0x100434567`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(__int64 a1, int a2, _BYTE *a3, int a4, __int64 a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  struct _Mbstatet *v12; // r10
  int v13; // ecx
  __int64 v14; // r9
  int v15; // edx
  unsigned int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // rdx
  signed __int64 v22; // r8
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r8
  unsigned int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  wchar_t *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // r9
  struct __crt_cached_ptd_host *v41; // [rsp+30h] [rbp-89h]
  __int16 v42[2]; // [rsp+48h] [rbp-71h] BYREF
  int v43; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-61h]
  struct _Mbstatet *v46; // [rsp+60h] [rbp-59h]
  unsigned __int64 v47; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v49; // [rsp+74h] [rbp-45h]
  _BYTE *v50; // [rsp+78h] [rbp-41h]
  __int64 v51; // [rsp+80h] [rbp-39h]
  unsigned __int64 v52; // [rsp+88h] [rbp-31h] BYREF
  wchar_t v53[4]; // [rsp+90h] [rbp-29h] BYREF
  wchar_t v54[4]; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h]
  __int64 v57; // [rsp+B0h] [rbp-9h]
  _BYTE v58[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v59[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v57 = -2;
  v5 = a3;
  v50 = a3;
  v6 = a2;
  v46 = (struct _Mbstatet *)a5;
  v8 = (__int64)a2 >> 6;
  v51 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(_pioinfo[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v45 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = (struct _Mbstatet *)a5;
  if ( !*(_BYTE *)(a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow((__crt_cached_ptd_host *)v46);
    v12 = v46;
  }
  v13 = *(_DWORD *)(*(_QWORD *)&v12[3] + 12LL);
  v49 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v50 < v10 )
  {
    v14 = v6 >> 6;
    v56 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v42[0]) = *v5;
      v43 = 0;
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
        do
        {
          if ( !*v19 )
            break;
          ++v17;
          ++v18;
          ++v19;
        }
        while ( v18 < 5 );
        if ( v18 <= 0 )
        {
          v26 = *((char *)lookuptrailbytes + (unsigned __int8)*v5);
          v27 = v45 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v51;
              do
              {
                *(_BYTE *)(v38 + _pioinfo[v39] + 8 * v9 + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v47 = 0;
          *(_QWORD *)v54 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v54,
                 (const char **)v28,
                 (unsigned __int64)&v47,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v51;
        }
        else
        {
          v20 = *((char *)lookuptrailbytes + *(unsigned __int8 *)(_pioinfo[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v47) = v20 - v17;
          v21 = v45 - (_QWORD)v5;
          v22 = (int)v47;
          if ( (int)v47 > (__int64)(v45 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + _pioinfo[v8] + 8 * v9 + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(_pioinfo[v14] + 8 * v9 + 62);
          do
            v58[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memmove(&v58[v18], v5, v22);
            v12 = v46;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + _pioinfo[v8] + 8 * v9 + 62) = 0;
          v52 = 0;
          *(_QWORD *)v53 = v58;
          v16 = (v20 == 4) + 1;
          if ( __crt_mbstring::__mbsrtowcs_utf8(
                 (__crt_mbstring *)&v43,
                 v53,
                 (const char **)v16,
                 (unsigned __int64)&v52,
                 v12,
                 v41) == -1 )
            return a1;
          v5 += (int)v47 - 1;
        }
      }
      else
      {
        v29 = _pioinfo[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v59[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v59[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = (wchar_t *)v59;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**(_QWORD **)&v12[3] + 2 * v33) >= 0 )
        {
          v31 = 1;
          v32 = (wchar_t *)v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal((__crt_mbstring *)&v43, v32, (char *)v31, (__crt_cached_ptd_host *)v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v45 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(_pioinfo[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(
                             (__crt_mbstring *)&v43,
                             (wchar_t *)v5,
                             (char *)2,
                             (__crt_cached_ptd_host *)v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v43, v16, (unsigned int)Buffer, 5, 0, 0);
      v35 = v34;
      if ( !v34 )
        return a1;
      v36 = hFile;
      if ( !WriteFile(hFile, Buffer, v34, &NumberOfBytesWritten, 0) )
      {
LABEL_48:
        *(_DWORD *)a1 = GetLastError();
        return a1;
      }
      v15 = *(_DWORD *)(a1 + 8) + (_DWORD)v5 - (_DWORD)v50;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v42[0]) == 10 )
      {
        v42[0] = 13;
        if ( !WriteFile(v36, v42, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v45 )
        return a1;
      v12 = v46;
      v14 = v56;
      v13 = v49;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1004344e8  mov     rax, rsp
0x1004344eb  push    rbp
0x1004344ec  push    rsi
0x1004344ed  push    rdi
0x1004344ee  push    r12
0x1004344f0  push    r13
0x1004344f2  push    r14
0x1004344f4  push    r15
0x1004344f6  lea     rbp, [rax-57h]
0x1004344fa  sub     rsp, 0D0h
0x100434501  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x100434509  mov     [rax+8], rbx
0x10043450d  mov     rax, cs:__security_cookie
0x100434514  xor     rax, rsp
0x100434517  mov     [rbp+4Fh+var_38], rax
0x10043451b  mov     rsi, r8
0x10043451e  mov     [rbp+4Fh+var_90], r8
0x100434522  movsxd  r14, edx
0x100434525  mov     rbx, rcx
0x100434528  mov     rax, [rbp+4Fh+arg_20]
0x10043452c  mov     [rbp+4Fh+var_A8], rax
0x100434530  mov     rax, r14
0x100434533  mov     r13, r14
0x100434536  sar     r13, 6
0x10043453a  mov     [rbp+4Fh+var_88], r13
0x10043453e  lea     rcx, __ImageBase
0x100434545  and     eax, 3Fh
0x100434548  lea     r15, [rax+rax*8]
0x10043454c  mov     rax, rva __pioinfo[rcx+r13*8]
0x100434554  mov     rax, [rax+r15*8+28h]
0x100434559  mov     [rbp+4Fh+hFile], rax
0x10043455d  mov     r12d, r9d
0x100434560  add     r12, r8
0x100434563  mov     [rbp+4Fh+var_B0], r12
0x100434567  call    cs:__imp_GetConsoleOutputCP
0x10043456d  mov     [rbp+4Fh+var_98], eax
0x100434570  xor     edi, edi
0x100434572  mov     r10, [rbp+4Fh+var_A8]
0x100434576  cmp     [r10+28h], dil
0x10043457a  jnz     short loc_100434588
0x10043457c  mov     rcx, r10; this
0x10043457f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100434584  mov     r10, [rbp+4Fh+var_A8]
0x100434588  mov     rcx, [r10+18h]
0x10043458c  mov     ecx, [rcx+0Ch]
0x10043458f  mov     [rbp+4Fh+var_94], ecx
0x100434592  xor     eax, eax
0x100434594  mov     [rbx], rax
0x100434597  mov     [rbx+8], eax
0x10043459a  cmp     [rbp+4Fh+var_90], r12
0x10043459e  jnb     loc_100434933
0x1004345a4  mov     r9, r14
0x1004345a7  sar     r9, 6
0x1004345ab  mov     [rbp+4Fh+var_60], r9
0x1004345af  mov     edx, edi
0x1004345b1  mov     al, [rsi]
0x1004345b3  mov     byte ptr [rbp+4Fh+var_C0], al
0x1004345b6  mov     [rbp+4Fh+var_BC], edi
0x1004345b9  mov     r12d, 1
0x1004345bf  lea     r11, __ImageBase
0x1004345c6  cmp     ecx, 0FDE9h
0x1004345cc  jnz     loc_10043474D
0x1004345d2  mov     edx, edi
0x1004345d4  mov     r14, rdi
0x1004345d7  lea     rcx, ds:3Eh[r15*8]
0x1004345df  add     rcx, rva __pioinfo[r11+r9*8]
0x1004345e7  cmp     [rcx], dil
0x1004345ea  jz      short loc_1004345FA
0x1004345ec  inc     edx
0x1004345ee  inc     r14
0x1004345f1  inc     rcx
0x1004345f4  cmp     r14, 5
0x1004345f8  jl      short loc_1004345E7
0x1004345fa  test    r14, r14
0x1004345fd  jle     loc_1004346E3
0x100434603  mov     rax, rva __pioinfo[r11+r13*8]
0x10043460b  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x100434611  movsx   r12d, byte ptr [rcx+r11+4E8D0h]
0x10043461a  inc     r12d
0x10043461d  mov     eax, r12d
0x100434620  sub     eax, edx
0x100434622  mov     dword ptr [rbp+4Fh+var_A0], eax
0x100434625  mov     rdx, [rbp+4Fh+var_B0]
0x100434629  sub     rdx, rsi
0x10043462c  movsxd  r8, eax; Size
0x10043462f  cmp     r8, rdx
0x100434632  jg      loc_1004348B0
0x100434638  mov     rcx, rdi
0x10043463b  lea     rdx, ds:3Eh[r15*8]
0x100434643  add     rdx, rva __pioinfo[r11+r9*8]
0x10043464b  mov     al, [rdx]
0x10043464d  mov     [rbp+rcx+4Fh+var_50], al
0x100434651  inc     rcx
0x100434654  inc     rdx
0x100434657  cmp     rcx, r14
0x10043465a  jl      short loc_10043464B
0x10043465c  test    r8, r8
0x10043465f  jle     short loc_10043467B
0x100434661  lea     rcx, [rbp+4Fh+var_50]
0x100434665  add     rcx, r14; void *
0x100434668  mov     rdx, rsi; Src
0x10043466b  call    memmove
0x100434670  mov     r10, [rbp+4Fh+var_A8]
0x100434674  lea     r11, __ImageBase
0x10043467b  mov     rdx, rdi
0x10043467e  mov     rcx, rva __pioinfo[r11+r13*8]
0x100434686  add     rcx, rdx
0x100434689  mov     [rcx+r15*8+3Eh], dil
0x10043468e  inc     rdx
0x100434691  cmp     rdx, r14
0x100434694  jl      short loc_10043467E
0x100434696  mov     [rbp+4Fh+var_80], rdi
0x10043469a  lea     rax, [rbp+4Fh+var_50]
0x10043469e  mov     qword ptr [rbp+4Fh+var_78], rax
0x1004346a2  mov     eax, edi
0x1004346a4  cmp     r12d, 4
0x1004346a8  setz    al
0x1004346ab  inc     eax
0x1004346ad  mov     r12d, eax
0x1004346b0  mov     r8d, eax; char **
0x1004346b3  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x1004346b8  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x1004346bc  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x1004346c0  lea     rcx, [rbp+4Fh+var_BC]; this
0x1004346c4  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x1004346c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004346cd  jz      loc_100434933
0x1004346d3  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x1004346d6  dec     eax
0x1004346d8  movsxd  rcx, eax
0x1004346db  add     rsi, rcx
0x1004346de  jmp     loc_1004347DE
0x1004346e3  movzx   eax, byte ptr [rsi]
0x1004346e6  movsx   r13, byte ptr [rax+r11+4E8D0h]
0x1004346ef  lea     ecx, [r13+1]
0x1004346f3  mov     r8, [rbp+4Fh+var_B0]
0x1004346f7  sub     r8, rsi
0x1004346fa  movsxd  rax, ecx
0x1004346fd  cmp     rax, r8
0x100434700  jg      loc_1004348DE
0x100434706  mov     [rbp+4Fh+var_A0], rdi
0x10043470a  mov     qword ptr [rbp+4Fh+var_70], rsi
0x10043470e  mov     eax, edi
0x100434710  cmp     ecx, 4
0x100434713  setz    al
0x100434716  inc     eax
0x100434718  mov     r14d, eax
0x10043471b  mov     r8d, eax; char **
0x10043471e  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x100434723  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x100434727  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x10043472b  lea     rcx, [rbp+4Fh+var_BC]; this
0x10043472f  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100434734  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100434738  jz      loc_100434933
0x10043473e  add     rsi, r13
0x100434741  mov     r12d, r14d
0x100434744  mov     r13, [rbp+4Fh+var_88]
0x100434748  jmp     loc_1004347DE
0x10043474d  mov     r8, rva __pioinfo[r11+r13*8]
0x100434755  mov     cl, [r8+r15*8+3Dh]
0x10043475a  test    cl, 4
0x10043475d  jz      short loc_100434780
0x10043475f  mov     al, [r8+r15*8+3Eh]
0x100434764  mov     [rbp+4Fh+var_48], al
0x100434767  mov     al, [rsi]
0x100434769  mov     [rbp+4Fh+var_47], al
0x10043476c  and     cl, 0FBh
0x10043476f  mov     [r8+r15*8+3Dh], cl
0x100434774  mov     r8d, 2
0x10043477a  lea     rdx, [rbp+4Fh+var_48]
0x10043477e  jmp     short loc_1004347C9
0x100434780  movzx   r9d, byte ptr [rsi]
0x100434784  mov     rax, [r10+18h]
0x100434788  mov     rcx, [rax]
0x10043478b  cmp     [rcx+r9*2], di
0x100434790  jge     short loc_1004347C3
0x100434792  lea     r14, [rsi+1]
0x100434796  cmp     r14, [rbp+4Fh+var_B0]
0x10043479a  jnb     loc_100434910
0x1004347a0  mov     r9, r10; __crt_cached_ptd_host *
0x1004347a3  mov     r8d, 2; char *
0x1004347a9  mov     rdx, rsi; wchar_t *
0x1004347ac  lea     rcx, [rbp+4Fh+var_BC]; this
0x1004347b0  call    _mbtowc_internal
0x1004347b5  cmp     eax, 0FFFFFFFFh
0x1004347b8  jz      loc_100434933
0x1004347be  mov     rsi, r14
0x1004347c1  jmp     short loc_1004347DE
0x1004347c3  mov     r8, r12; char *
0x1004347c6  mov     rdx, rsi; wchar_t *
0x1004347c9  mov     r9, r10; __crt_cached_ptd_host *
0x1004347cc  lea     rcx, [rbp+4Fh+var_BC]; this
0x1004347d0  call    _mbtowc_internal
0x1004347d5  cmp     eax, 0FFFFFFFFh
0x1004347d8  jz      loc_100434933
0x1004347de  inc     rsi
0x1004347e1  mov     [rsp+38h], rdi
0x1004347e6  mov     [rsp+100h+var_D0], rdi
0x1004347eb  mov     dword ptr [rsp+100h+var_D8], 5
0x1004347f3  lea     rax, [rbp+4Fh+Buffer]
0x1004347f7  mov     [rsp+100h+lpOverlapped], rax
0x1004347fc  mov     r9d, r12d
0x1004347ff  lea     r8, [rbp+4Fh+var_BC]
0x100434803  xor     edx, edx
0x100434805  mov     ecx, [rbp+4Fh+var_98]
0x100434808  call    __acrt_WideCharToMultiByte
0x10043480d  mov     r14d, eax
0x100434810  test    eax, eax
0x100434812  jz      loc_100434933
0x100434818  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x10043481d  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100434821  mov     r8d, eax; nNumberOfBytesToWrite
0x100434824  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x100434828  mov     r12, [rbp+4Fh+hFile]
0x10043482c  mov     rcx, r12; hFile
0x10043482f  call    cs:__imp_WriteFile
0x100434835  test    eax, eax
0x100434837  jz      loc_10043492B
0x10043483d  mov     edx, esi
0x10043483f  sub     edx, dword ptr [rbp+4Fh+var_90]
0x100434842  add     edx, [rbx+8]
0x100434845  mov     [rbx+4], edx
0x100434848  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x10043484c  jb      loc_100434933
0x100434852  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x100434856  jnz     short loc_100434896
0x100434858  mov     eax, 0Dh
0x10043485d  mov     [rbp+4Fh+var_C0], ax
0x100434861  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x100434866  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x10043486a  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x10043486e  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x100434872  mov     rcx, r12; hFile
0x100434875  call    cs:__imp_WriteFile
0x10043487b  test    eax, eax
0x10043487d  jz      loc_10043492B
0x100434883  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x100434887  jb      loc_100434933
0x10043488d  inc     dword ptr [rbx+8]
0x100434890  inc     dword ptr [rbx+4]
0x100434893  mov     edx, [rbx+4]
0x100434896  cmp     rsi, [rbp+4Fh+var_B0]
0x10043489a  jnb     loc_100434933
0x1004348a0  mov     r10, [rbp+4Fh+var_A8]
0x1004348a4  mov     r9, [rbp+4Fh+var_60]
0x1004348a8  mov     ecx, [rbp+4Fh+var_94]
0x1004348ab  jmp     loc_1004345B1
0x1004348b0  test    rdx, rdx
0x1004348b3  jle     short loc_1004348D9
0x1004348b5  sub     rsi, r14
0x1004348b8  mov     rcx, rva __pioinfo[r11+r13*8]
0x1004348c0  add     rcx, r14
0x1004348c3  mov     al, [rsi+r14]
0x1004348c7  mov     [rcx+r15*8+3Eh], al
0x1004348cc  inc     edi
0x1004348ce  inc     r14
0x1004348d1  movsxd  rax, edi
0x1004348d4  cmp     rax, rdx
0x1004348d7  jl      short loc_1004348B8
0x1004348d9  add     [rbx+4], edx
0x1004348dc  jmp     short loc_100434933
0x1004348de  test    r8, r8
0x1004348e1  jle     short loc_10043490A
0x1004348e3  mov     rdx, rdi
0x1004348e6  mov     r9, [rbp+4Fh+var_88]
0x1004348ea  mov     rcx, rva __pioinfo[r11+r9*8]
0x1004348f2  add     rcx, rdx
0x1004348f5  mov     al, [rdx+rsi]
0x1004348f8  mov     [rcx+r15*8+3Eh], al
0x1004348fd  inc     edi
0x1004348ff  inc     rdx
0x100434902  movsxd  rax, edi
0x100434905  cmp     rax, r8
0x100434908  jl      short loc_1004348EA
0x10043490a  add     [rbx+4], r8d
0x10043490e  jmp     short loc_100434933
0x100434910  mov     [r8+r15*8+3Eh], r9b
0x100434915  mov     rax, rva __pioinfo[r11+r13*8]
0x10043491d  or      byte ptr [rax+r15*8+3Dh], 4
0x100434923  lea     eax, [rdx+1]
0x100434926  mov     [rbx+4], eax
0x100434929  jmp     short loc_100434933
0x10043492b  call    cs:__imp_GetLastError
0x100434931  mov     [rbx], eax
0x100434933  mov     rax, rbx
0x100434936  mov     rcx, [rbp+4Fh+var_38]
0x10043493a  xor     rcx, rsp; StackCookie
0x10043493d  call    __security_check_cookie
0x100434942  mov     rbx, [rsp+100h+arg_0]
0x10043494a  add     rsp, 0D0h
0x100434951  pop     r15
0x100434953  pop     r14
0x100434955  pop     r13
0x100434957  pop     r12
0x100434959  pop     rdi
0x10043495a  pop     rsi
0x10043495b  pop     rbp
0x10043495c  retn
```
