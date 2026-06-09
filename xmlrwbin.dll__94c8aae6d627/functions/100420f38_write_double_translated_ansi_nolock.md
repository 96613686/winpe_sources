# write_double_translated_ansi_nolock

- ea: `0x100420f38`
- end: `0x1004213ad`
- name: `write_double_translated_ansi_nolock`
- size: `1141`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x100421878`

## callees

- `0x100415d60`
- `0x100416590`
- `0x10041b270`
- `0x10041dcb4`
- `0x10041f2d8`
- `0x100420f38`
- `0x100421d38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042137b`
- `KERNEL32!GetLastError` at `0x10042137b`
- `KERNEL32!WriteFile` at `0x10042127f`
- `KERNEL32!WriteFile` at `0x1004212c5`
- `KERNEL32!WriteFile` at `0x10042127f`
- `KERNEL32!WriteFile` at `0x1004212c5`
- `KERNEL32!GetConsoleOutputCP` at `0x100420fb7`
- `KERNEL32!GetConsoleOutputCP` at `0x100420fb7`

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
0x100420f38  mov     rax, rsp
0x100420f3b  push    rbp
0x100420f3c  push    rsi
0x100420f3d  push    rdi
0x100420f3e  push    r12
0x100420f40  push    r13
0x100420f42  push    r14
0x100420f44  push    r15
0x100420f46  lea     rbp, [rax-57h]
0x100420f4a  sub     rsp, 0D0h
0x100420f51  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x100420f59  mov     [rax+8], rbx
0x100420f5d  mov     rax, cs:__security_cookie
0x100420f64  xor     rax, rsp
0x100420f67  mov     [rbp+4Fh+var_38], rax
0x100420f6b  mov     rsi, r8
0x100420f6e  mov     [rbp+4Fh+var_90], r8
0x100420f72  movsxd  r14, edx
0x100420f75  mov     rbx, rcx
0x100420f78  mov     rax, [rbp+4Fh+arg_20]
0x100420f7c  mov     [rbp+4Fh+var_A8], rax
0x100420f80  mov     rax, r14
0x100420f83  mov     r13, r14
0x100420f86  sar     r13, 6
0x100420f8a  mov     [rbp+4Fh+var_88], r13
0x100420f8e  lea     rcx, __ImageBase
0x100420f95  and     eax, 3Fh
0x100420f98  lea     r15, [rax+rax*8]
0x100420f9c  mov     rax, rva __pioinfo[rcx+r13*8]
0x100420fa4  mov     rax, [rax+r15*8+28h]
0x100420fa9  mov     [rbp+4Fh+hFile], rax
0x100420fad  mov     r12d, r9d
0x100420fb0  add     r12, r8
0x100420fb3  mov     [rbp+4Fh+var_B0], r12
0x100420fb7  call    cs:__imp_GetConsoleOutputCP
0x100420fbd  mov     [rbp+4Fh+var_98], eax
0x100420fc0  xor     edi, edi
0x100420fc2  mov     r10, [rbp+4Fh+var_A8]
0x100420fc6  cmp     [r10+28h], dil
0x100420fca  jnz     short loc_100420FD8
0x100420fcc  mov     rcx, r10; this
0x100420fcf  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100420fd4  mov     r10, [rbp+4Fh+var_A8]
0x100420fd8  mov     rcx, [r10+18h]
0x100420fdc  mov     ecx, [rcx+0Ch]
0x100420fdf  mov     [rbp+4Fh+var_94], ecx
0x100420fe2  xor     eax, eax
0x100420fe4  mov     [rbx], rax
0x100420fe7  mov     [rbx+8], eax
0x100420fea  cmp     [rbp+4Fh+var_90], r12
0x100420fee  jnb     loc_100421383
0x100420ff4  mov     r9, r14
0x100420ff7  sar     r9, 6
0x100420ffb  mov     [rbp+4Fh+var_60], r9
0x100420fff  mov     edx, edi
0x100421001  mov     al, [rsi]
0x100421003  mov     byte ptr [rbp+4Fh+var_C0], al
0x100421006  mov     [rbp+4Fh+var_BC], edi
0x100421009  mov     r12d, 1
0x10042100f  lea     r11, __ImageBase
0x100421016  cmp     ecx, 0FDE9h
0x10042101c  jnz     loc_10042119D
0x100421022  mov     edx, edi
0x100421024  mov     r14, rdi
0x100421027  lea     rcx, ds:3Eh[r15*8]
0x10042102f  add     rcx, rva __pioinfo[r11+r9*8]
0x100421037  cmp     [rcx], dil
0x10042103a  jz      short loc_10042104A
0x10042103c  inc     edx
0x10042103e  inc     r14
0x100421041  inc     rcx
0x100421044  cmp     r14, 5
0x100421048  jl      short loc_100421037
0x10042104a  test    r14, r14
0x10042104d  jle     loc_100421133
0x100421053  mov     rax, rva __pioinfo[r11+r13*8]
0x10042105b  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x100421061  movsx   r12d, byte ptr [rcx+r11+348D0h]
0x10042106a  inc     r12d
0x10042106d  mov     eax, r12d
0x100421070  sub     eax, edx
0x100421072  mov     dword ptr [rbp+4Fh+var_A0], eax
0x100421075  mov     rdx, [rbp+4Fh+var_B0]
0x100421079  sub     rdx, rsi
0x10042107c  movsxd  r8, eax; Size
0x10042107f  cmp     r8, rdx
0x100421082  jg      loc_100421300
0x100421088  mov     rcx, rdi
0x10042108b  lea     rdx, ds:3Eh[r15*8]
0x100421093  add     rdx, rva __pioinfo[r11+r9*8]
0x10042109b  mov     al, [rdx]
0x10042109d  mov     [rbp+rcx+4Fh+var_50], al
0x1004210a1  inc     rcx
0x1004210a4  inc     rdx
0x1004210a7  cmp     rcx, r14
0x1004210aa  jl      short loc_10042109B
0x1004210ac  test    r8, r8
0x1004210af  jle     short loc_1004210CB
0x1004210b1  lea     rcx, [rbp+4Fh+var_50]
0x1004210b5  add     rcx, r14; void *
0x1004210b8  mov     rdx, rsi; Src
0x1004210bb  call    memmove
0x1004210c0  mov     r10, [rbp+4Fh+var_A8]
0x1004210c4  lea     r11, __ImageBase
0x1004210cb  mov     rdx, rdi
0x1004210ce  mov     rcx, rva __pioinfo[r11+r13*8]
0x1004210d6  add     rcx, rdx
0x1004210d9  mov     [rcx+r15*8+3Eh], dil
0x1004210de  inc     rdx
0x1004210e1  cmp     rdx, r14
0x1004210e4  jl      short loc_1004210CE
0x1004210e6  mov     [rbp+4Fh+var_80], rdi
0x1004210ea  lea     rax, [rbp+4Fh+var_50]
0x1004210ee  mov     qword ptr [rbp+4Fh+var_78], rax
0x1004210f2  mov     eax, edi
0x1004210f4  cmp     r12d, 4
0x1004210f8  setz    al
0x1004210fb  inc     eax
0x1004210fd  mov     r12d, eax
0x100421100  mov     r8d, eax; char **
0x100421103  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x100421108  lea     r9, [rbp+4Fh+var_80]; unsigned __int64
0x10042110c  lea     rdx, [rbp+4Fh+var_78]; wchar_t *
0x100421110  lea     rcx, [rbp+4Fh+var_BC]; this
0x100421114  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100421119  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10042111d  jz      loc_100421383
0x100421123  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x100421126  dec     eax
0x100421128  movsxd  rcx, eax
0x10042112b  add     rsi, rcx
0x10042112e  jmp     loc_10042122E
0x100421133  movzx   eax, byte ptr [rsi]
0x100421136  movsx   r13, byte ptr [rax+r11+348D0h]
0x10042113f  lea     ecx, [r13+1]
0x100421143  mov     r8, [rbp+4Fh+var_B0]
0x100421147  sub     r8, rsi
0x10042114a  movsxd  rax, ecx
0x10042114d  cmp     rax, r8
0x100421150  jg      loc_10042132E
0x100421156  mov     [rbp+4Fh+var_A0], rdi
0x10042115a  mov     qword ptr [rbp+4Fh+var_70], rsi
0x10042115e  mov     eax, edi
0x100421160  cmp     ecx, 4
0x100421163  setz    al
0x100421166  inc     eax
0x100421168  mov     r14d, eax
0x10042116b  mov     r8d, eax; char **
0x10042116e  mov     [rsp+100h+lpOverlapped], r10; struct _Mbstatet *
0x100421173  lea     r9, [rbp+4Fh+var_A0]; unsigned __int64
0x100421177  lea     rdx, [rbp+4Fh+var_70]; wchar_t *
0x10042117b  lea     rcx, [rbp+4Fh+var_BC]; this
0x10042117f  call    ?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x100421184  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100421188  jz      loc_100421383
0x10042118e  add     rsi, r13
0x100421191  mov     r12d, r14d
0x100421194  mov     r13, [rbp+4Fh+var_88]
0x100421198  jmp     loc_10042122E
0x10042119d  mov     r8, rva __pioinfo[r11+r13*8]
0x1004211a5  mov     cl, [r8+r15*8+3Dh]
0x1004211aa  test    cl, 4
0x1004211ad  jz      short loc_1004211D0
0x1004211af  mov     al, [r8+r15*8+3Eh]
0x1004211b4  mov     [rbp+4Fh+var_48], al
0x1004211b7  mov     al, [rsi]
0x1004211b9  mov     [rbp+4Fh+var_47], al
0x1004211bc  and     cl, 0FBh
0x1004211bf  mov     [r8+r15*8+3Dh], cl
0x1004211c4  mov     r8d, 2
0x1004211ca  lea     rdx, [rbp+4Fh+var_48]
0x1004211ce  jmp     short loc_100421219
0x1004211d0  movzx   r9d, byte ptr [rsi]
0x1004211d4  mov     rax, [r10+18h]
0x1004211d8  mov     rcx, [rax]
0x1004211db  cmp     [rcx+r9*2], di
0x1004211e0  jge     short loc_100421213
0x1004211e2  lea     r14, [rsi+1]
0x1004211e6  cmp     r14, [rbp+4Fh+var_B0]
0x1004211ea  jnb     loc_100421360
0x1004211f0  mov     r9, r10; __crt_cached_ptd_host *
0x1004211f3  mov     r8d, 2; char *
0x1004211f9  mov     rdx, rsi; wchar_t *
0x1004211fc  lea     rcx, [rbp+4Fh+var_BC]; this
0x100421200  call    _mbtowc_internal
0x100421205  cmp     eax, 0FFFFFFFFh
0x100421208  jz      loc_100421383
0x10042120e  mov     rsi, r14
0x100421211  jmp     short loc_10042122E
0x100421213  mov     r8, r12; char *
0x100421216  mov     rdx, rsi; wchar_t *
0x100421219  mov     r9, r10; __crt_cached_ptd_host *
0x10042121c  lea     rcx, [rbp+4Fh+var_BC]; this
0x100421220  call    _mbtowc_internal
0x100421225  cmp     eax, 0FFFFFFFFh
0x100421228  jz      loc_100421383
0x10042122e  inc     rsi
0x100421231  mov     [rsp+38h], rdi
0x100421236  mov     [rsp+100h+var_D0], rdi
0x10042123b  mov     dword ptr [rsp+100h+var_D8], 5
0x100421243  lea     rax, [rbp+4Fh+Buffer]
0x100421247  mov     [rsp+100h+lpOverlapped], rax
0x10042124c  mov     r9d, r12d
0x10042124f  lea     r8, [rbp+4Fh+var_BC]
0x100421253  xor     edx, edx
0x100421255  mov     ecx, [rbp+4Fh+var_98]
0x100421258  call    __acrt_WideCharToMultiByte
0x10042125d  mov     r14d, eax
0x100421260  test    eax, eax
0x100421262  jz      loc_100421383
0x100421268  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x10042126d  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100421271  mov     r8d, eax; nNumberOfBytesToWrite
0x100421274  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x100421278  mov     r12, [rbp+4Fh+hFile]
0x10042127c  mov     rcx, r12; hFile
0x10042127f  call    cs:__imp_WriteFile
0x100421285  test    eax, eax
0x100421287  jz      loc_10042137B
0x10042128d  mov     edx, esi
0x10042128f  sub     edx, dword ptr [rbp+4Fh+var_90]
0x100421292  add     edx, [rbx+8]
0x100421295  mov     [rbx+4], edx
0x100421298  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x10042129c  jb      loc_100421383
0x1004212a2  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x1004212a6  jnz     short loc_1004212E6
0x1004212a8  mov     eax, 0Dh
0x1004212ad  mov     [rbp+4Fh+var_C0], ax
0x1004212b1  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x1004212b6  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1004212ba  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x1004212be  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x1004212c2  mov     rcx, r12; hFile
0x1004212c5  call    cs:__imp_WriteFile
0x1004212cb  test    eax, eax
0x1004212cd  jz      loc_10042137B
0x1004212d3  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x1004212d7  jb      loc_100421383
0x1004212dd  inc     dword ptr [rbx+8]
0x1004212e0  inc     dword ptr [rbx+4]
0x1004212e3  mov     edx, [rbx+4]
0x1004212e6  cmp     rsi, [rbp+4Fh+var_B0]
0x1004212ea  jnb     loc_100421383
0x1004212f0  mov     r10, [rbp+4Fh+var_A8]
0x1004212f4  mov     r9, [rbp+4Fh+var_60]
0x1004212f8  mov     ecx, [rbp+4Fh+var_94]
0x1004212fb  jmp     loc_100421001
0x100421300  test    rdx, rdx
0x100421303  jle     short loc_100421329
0x100421305  sub     rsi, r14
0x100421308  mov     rcx, rva __pioinfo[r11+r13*8]
0x100421310  add     rcx, r14
0x100421313  mov     al, [rsi+r14]
0x100421317  mov     [rcx+r15*8+3Eh], al
0x10042131c  inc     edi
0x10042131e  inc     r14
0x100421321  movsxd  rax, edi
0x100421324  cmp     rax, rdx
0x100421327  jl      short loc_100421308
0x100421329  add     [rbx+4], edx
0x10042132c  jmp     short loc_100421383
0x10042132e  test    r8, r8
0x100421331  jle     short loc_10042135A
0x100421333  mov     rdx, rdi
0x100421336  mov     r9, [rbp+4Fh+var_88]
0x10042133a  mov     rcx, rva __pioinfo[r11+r9*8]
0x100421342  add     rcx, rdx
0x100421345  mov     al, [rdx+rsi]
0x100421348  mov     [rcx+r15*8+3Eh], al
0x10042134d  inc     edi
0x10042134f  inc     rdx
0x100421352  movsxd  rax, edi
0x100421355  cmp     rax, r8
0x100421358  jl      short loc_10042133A
0x10042135a  add     [rbx+4], r8d
0x10042135e  jmp     short loc_100421383
0x100421360  mov     [r8+r15*8+3Eh], r9b
0x100421365  mov     rax, rva __pioinfo[r11+r13*8]
0x10042136d  or      byte ptr [rax+r15*8+3Dh], 4
0x100421373  lea     eax, [rdx+1]
0x100421376  mov     [rbx+4], eax
0x100421379  jmp     short loc_100421383
0x10042137b  call    cs:__imp_GetLastError
0x100421381  mov     [rbx], eax
0x100421383  mov     rax, rbx
0x100421386  mov     rcx, [rbp+4Fh+var_38]
0x10042138a  xor     rcx, rsp; StackCookie
0x10042138d  call    __security_check_cookie
0x100421392  mov     rbx, [rsp+100h+arg_0]
0x10042139a  add     rsp, 0D0h
0x1004213a1  pop     r15
0x1004213a3  pop     r14
0x1004213a5  pop     r13
0x1004213a7  pop     r12
0x1004213a9  pop     rdi
0x1004213aa  pop     rsi
0x1004213ab  pop     rbp
0x1004213ac  retn
```
