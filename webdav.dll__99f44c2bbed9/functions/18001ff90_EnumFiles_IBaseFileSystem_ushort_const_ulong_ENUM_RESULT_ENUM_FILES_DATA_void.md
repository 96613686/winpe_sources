# EnumFiles(IBaseFileSystem *,ushort const *,ulong,ENUM_RESULT (*)(ENUM_FILES_DATA *),void *)

- ea: `0x18001ff90`
- end: `0x1800202f6`
- name: `?EnumFiles@@YAJPEAVIBaseFileSystem@@PEBGKP6A?AW4ENUM_RESULT@@PEAUENUM_FILES_DATA@@@ZPEAX@Z`
- size: `870`
- prototype: `__int64 __fastcall(struct IBaseFileSystem *, const unsigned __int16 *, unsigned int, enum ENUM_RESULT (__high *)(struct ENUM_FILES_DATA *), void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001af58`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x18001ff90`
- `0x1800202fc`
- `0x180020368`
- `0x18002055c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002008f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002008f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020221`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020221`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ffff`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001ffff`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800202b8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800202b8`

## pseudocode

```c
__int64 __fastcall EnumFiles(
        struct IBaseFileSystem *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        enum ENUM_RESULT (__high *a4)(struct ENUM_FILES_DATA *),
        void *a5)
{
  const unsigned __int16 *v5; // rsi
  char *v7; // rax
  char *v8; // rbx
  _DWORD *v9; // r12
  _DWORD *v10; // r14
  unsigned int v11; // eax
  signed int LastError; // eax
  signed int v13; // edi
  __int64 *v14; // rcx
  __int64 v15; // r15
  __int64 v16; // rdi
  __int64 v17; // rax
  unsigned __int16 *v18; // rdi
  int v19; // ecx
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  __int16 v22; // ax
  const unsigned __int16 **v23; // rsi
  const unsigned __int16 *v24; // rcx
  bool v25; // zf
  _DWORD *v26; // rsi
  unsigned int v28; // [rsp+28h] [rbp-49h]
  unsigned __int64 v29; // [rsp+30h] [rbp-41h] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-39h] BYREF
  const unsigned __int16 **v31; // [rsp+40h] [rbp-31h]
  _DWORD *v32; // [rsp+48h] [rbp-29h]
  _WIN32_FILE_ATTRIBUTE_DATA v33; // [rsp+50h] [rbp-21h] BYREF

  v5 = a2;
  memset(&v33, 0, sizeof(v33));
  if ( !a1 || !a2 )
    return 2147942487LL;
  v7 = (char *)operator new(0x102D0u);
  v8 = v7;
  if ( v7 )
  {
    STRU::STRU((STRU *)(v7 + 664));
    *((_QWORD *)v8 + 74) = a1;
    *((_QWORD *)v8 + 75) = v8 + 720;
    v31 = (const unsigned __int16 **)(v8 + 640);
    *((_QWORD *)v8 + 79) = &DeleteCallback;
    v9 = v8 + 656;
    *((_DWORD *)v8 + 164) = 59;
    v32 = v8 + 660;
    v10 = v8 + 624;
    *((_DWORD *)v8 + 165) = 1;
    *((_QWORD *)v8 + 77) = a5;
    *((_DWORD *)v8 + 156) = 0;
    v11 = (*(__int64 (__fastcall **)(struct IBaseFileSystem *, const unsigned __int16 *, __int64, char *, char *))(*(_QWORD *)a1 + 64LL))(
            a1,
            v5,
            0x8000,
            v8 + 720,
            v8 + 640);
    if ( !v11 )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_42;
    }
    if ( v11 >= 0x8000 )
    {
      v13 = -2147024809;
LABEL_42:
      STRU::~STRU((STRU *)(v8 + 664));
      operator delete(v8);
      return (unsigned int)v13;
    }
    v14 = (__int64 *)*((_QWORD *)v8 + 74);
    v15 = 0x8000LL - v11;
    v29 = v15;
    v16 = v11 + 360LL;
    v17 = *v14;
    v18 = (unsigned __int16 *)&v8[2 * v16];
    v30 = v18;
    if ( (*(unsigned int (__fastcall **)(__int64 *, char *, _QWORD, _WIN32_FILE_ATTRIBUTE_DATA *))(v17 + 88))(
           v14,
           v8 + 720,
           0,
           &v33)
      && (v33.dwFileAttributes & 0x10) != 0
      || !*v31 )
    {
      if ( *(v18 - 1) != 92 )
      {
        v13 = StringCchCopyExW(v18, v15, L"\\", &v30, &v29, v28);
        if ( v13 < 0 )
          goto LABEL_42;
        v18 = v30;
        v15 = v29;
      }
      *v31 = v18;
      v13 = StringCchCopyExW(v18, v15, L"*", &v30, &v29, v28);
      if ( v13 < 0 )
        goto LABEL_42;
      v18 = v30;
      v15 = v29;
    }
    else
    {
      *v9 &= ~0x20u;
    }
    if ( (*(_BYTE *)v9 & 0x20) == 0 )
      ++*v10;
    v19 = *v5;
    v20 = v5 + 1;
    if ( !(_WORD)v19 )
      goto LABEL_31;
    do
    {
      if ( (unsigned __int16)(v19 - 47) <= 0x2Du )
      {
        v21 = 0x200000000801LL;
        if ( _bittest64(&v21, (unsigned int)(v19 - 47)) )
          v5 = v20;
      }
      v22 = v19;
      v19 = *v20++;
    }
    while ( (_WORD)v19 );
    if ( *v5 == 46 && (!v5[1] || v5[1] == 46 && !v5[2])
      || v22 != 46
      || (v13 = StringCchCopyExW(v18, v15, L".", &v30, &v29, v28), v13 >= 0) )
    {
LABEL_31:
      v23 = v31;
      v13 = STRU::Copy((STRU *)(v8 + 664), *v31);
      if ( v13 >= 0 )
      {
        v24 = *v23;
        *((_QWORD *)v8 + 76) = *v23;
        v25 = (*(_BYTE *)v9 & 0x20) == 0;
        *((_QWORD *)v8 + 81) = 0x8000 - (((char *)v24 - v8 - 720) >> 1);
        if ( v25 )
        {
          v13 = EnumFilesWorker((LPWIN32_FIND_DATAW)v8);
        }
        else
        {
          v13 = 0;
          if ( (*(_BYTE *)v9 & 2) == 0 )
            MakeRootCallback((struct ENUM_WORKER_DATA *)v8, &v33);
          v26 = v32;
          ++*v10;
          if ( *v26 == 1 )
            v13 = EnumFilesWorker((LPWIN32_FIND_DATAW)v8);
          --*v10;
          if ( v13 >= 0 && *v26 == 1 && (*(_BYTE *)v9 & 2) != 0 )
            MakeRootCallback((struct ENUM_WORKER_DATA *)v8, &v33);
        }
      }
    }
    goto LABEL_42;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x18001ff90  push    rbp
0x18001ff92  push    rbx
0x18001ff93  push    rsi
0x18001ff94  push    rdi
0x18001ff95  push    r12
0x18001ff97  push    r13
0x18001ff99  push    r14
0x18001ff9b  push    r15
0x18001ff9d  lea     rbp, [rsp-17h]
0x18001ffa2  sub     rsp, 88h
0x18001ffa9  mov     rax, cs:__security_cookie
0x18001ffb0  xor     rax, rsp
0x18001ffb3  mov     [rbp+4Fh+var_48], rax
0x18001ffb7  xor     eax, eax
0x18001ffb9  xorps   xmm0, xmm0
0x18001ffbc  xor     r15d, r15d
0x18001ffbf  mov     [rbp+4Fh+var_70.nFileSizeLow], eax
0x18001ffc2  mov     rsi, rdx
0x18001ffc5  mov     rdi, rcx
0x18001ffc8  movups  xmmword ptr [rbp+4Fh+var_70.dwFileAttributes], xmm0
0x18001ffcc  movups  xmmword ptr [rbp+4Fh+var_70.ftLastAccessTime.dwHighDateTime], xmm0
0x18001ffd0  test    rcx, rcx
0x18001ffd3  jz      loc_1800202D1
0x18001ffd9  test    rdx, rdx
0x18001ffdc  jz      loc_1800202D1
0x18001ffe2  mov     ecx, 102D0h; Size
0x18001ffe7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ffec  mov     rbx, rax
0x18001ffef  test    rax, rax
0x18001fff2  jz      loc_1800202CA
0x18001fff8  lea     rcx, [rax+298h]
0x18001ffff  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180020005  lea     rdx, [rbx+2D0h]
0x18002000c  mov     [rbx+250h], rdi
0x180020013  mov     [rbx+258h], rdx
0x18002001a  lea     rcx, [rbx+280h]
0x180020021  lea     rax, ?DeleteCallback@@YA?AW4ENUM_RESULT@@PEAUENUM_FILES_DATA@@@Z; DeleteCallback(ENUM_FILES_DATA *)
0x180020028  mov     [rbp+4Fh+var_80], rcx
0x18002002c  mov     [rbx+278h], rax
0x180020033  lea     r12, [rbx+290h]
0x18002003a  lea     rax, [rbx+294h]
0x180020041  mov     dword ptr [r12], 3Bh ; ';'
0x180020049  mov     [rbp+4Fh+var_78], rax
0x18002004d  lea     r14, [rbx+270h]
0x180020054  mov     dword ptr [rax], 1
0x18002005a  mov     r9, rdx
0x18002005d  mov     rax, [rbp+4Fh+arg_20]
0x180020061  mov     r13d, 8000h
0x180020067  mov     [rbx+268h], rax
0x18002006e  mov     r8d, r13d
0x180020071  mov     [r14], r15d
0x180020074  mov     rdx, rsi
0x180020077  mov     rax, [rdi]
0x18002007a  mov     [rsp+0C0h+var_A0], rcx
0x18002007f  mov     rcx, rdi
0x180020082  mov     rax, [rax+40h]
0x180020086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002008b  test    eax, eax
0x18002008d  jnz     short loc_1800200AD
0x18002008f  call    cs:__imp_GetLastError
0x180020095  mov     edi, eax
0x180020097  test    eax, eax
0x180020099  jle     loc_1800202B1
0x18002009f  movzx   edi, ax
0x1800200a2  or      edi, 80070000h
0x1800200a8  jmp     loc_1800202B1
0x1800200ad  cmp     eax, r13d
0x1800200b0  jb      short loc_1800200BC
0x1800200b2  mov     edi, 80070057h
0x1800200b7  jmp     loc_1800202B1
0x1800200bc  mov     rcx, [rbx+250h]
0x1800200c3  lea     r9, [rbp+4Fh+var_70]
0x1800200c7  mov     eax, eax
0x1800200c9  lea     rdx, [rbx+2D0h]
0x1800200d0  mov     r15, r13
0x1800200d3  xor     r8d, r8d
0x1800200d6  sub     r15, rax
0x1800200d9  mov     [rbp+4Fh+var_90], r15
0x1800200dd  lea     rdi, [rax+168h]
0x1800200e4  mov     rax, [rcx]
0x1800200e7  lea     rdi, [rbx+rdi*2]
0x1800200eb  mov     [rbp+4Fh+var_88], rdi
0x1800200ef  mov     rax, [rax+58h]
0x1800200f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200f8  xor     r9d, r9d
0x1800200fb  test    eax, eax
0x1800200fd  jz      short loc_180020105
0x1800200ff  test    byte ptr [rbp+4Fh+var_70.dwFileAttributes], 10h
0x180020103  jnz     short loc_18002010E
0x180020105  mov     rax, [rbp+4Fh+var_80]
0x180020109  cmp     [rax], r9
0x18002010c  jnz     short loc_180020183
0x18002010e  cmp     word ptr [rdi-2], 5Ch ; '\'
0x180020113  jz      short loc_180020146
0x180020115  lea     rax, [rbp+4Fh+var_90]
0x180020119  mov     rdx, r15; unsigned __int64
0x18002011c  lea     r9, [rbp+4Fh+var_88]; unsigned __int16 **
0x180020120  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x180020125  lea     r8, asc_180025EA0; "\\"
0x18002012c  mov     rcx, rdi; unsigned __int16 *
0x18002012f  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180020134  mov     edi, eax
0x180020136  test    eax, eax
0x180020138  js      loc_1800202B1
0x18002013e  mov     rdi, [rbp+4Fh+var_88]
0x180020142  mov     r15, [rbp+4Fh+var_90]
0x180020146  mov     rax, [rbp+4Fh+var_80]
0x18002014a  lea     r9, [rbp+4Fh+var_88]; unsigned __int16 **
0x18002014e  lea     r8, asc_180026D28; "*"
0x180020155  mov     rdx, r15; unsigned __int64
0x180020158  mov     rcx, rdi; unsigned __int16 *
0x18002015b  mov     [rax], rdi
0x18002015e  lea     rax, [rbp+4Fh+var_90]
0x180020162  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x180020167  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18002016c  xor     r9d, r9d
0x18002016f  mov     edi, eax
0x180020171  test    eax, eax
0x180020173  js      loc_1800202B1
0x180020179  mov     rdi, [rbp+4Fh+var_88]
0x18002017d  mov     r15, [rbp+4Fh+var_90]
0x180020181  jmp     short loc_180020188
0x180020183  and     dword ptr [r12], 0FFFFFFDFh
0x180020188  test    byte ptr [r12], 20h
0x18002018d  jnz     short loc_180020192
0x18002018f  inc     dword ptr [r14]
0x180020192  movzx   ecx, word ptr [rsi]
0x180020195  lea     rdx, [rsi+2]
0x180020199  test    cx, cx
0x18002019c  jz      short loc_180020213
0x18002019e  lea     eax, [rcx-2Fh]
0x1800201a1  cmp     ax, 2Dh ; '-'
0x1800201a5  ja      short loc_1800201BA
0x1800201a7  mov     r8, 200000000801h
0x1800201b1  bt      r8, rax
0x1800201b5  jnb     short loc_1800201BA
0x1800201b7  mov     rsi, rdx
0x1800201ba  movzx   eax, cx
0x1800201bd  movzx   ecx, word ptr [rdx]
0x1800201c0  add     rdx, 2
0x1800201c4  test    cx, cx
0x1800201c7  jnz     short loc_18002019E
0x1800201c9  cmp     word ptr [rsi], 2Eh ; '.'
0x1800201cd  jnz     short loc_1800201E4
0x1800201cf  cmp     [rsi+2], r9w
0x1800201d4  jz      short loc_180020213
0x1800201d6  cmp     word ptr [rsi+2], 2Eh ; '.'
0x1800201db  jnz     short loc_1800201E4
0x1800201dd  cmp     [rsi+4], r9w
0x1800201e2  jz      short loc_180020213
0x1800201e4  cmp     ax, 2Eh ; '.'
0x1800201e8  jnz     short loc_180020213
0x1800201ea  lea     rax, [rbp+4Fh+var_90]
0x1800201ee  mov     rdx, r15; unsigned __int64
0x1800201f1  lea     r9, [rbp+4Fh+var_88]; unsigned __int16 **
0x1800201f5  mov     [rsp+0C0h+var_A0], rax; unsigned __int64 *
0x1800201fa  lea     r8, asc_180027680; "."
0x180020201  mov     rcx, rdi; unsigned __int16 *
0x180020204  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180020209  mov     edi, eax
0x18002020b  test    eax, eax
0x18002020d  js      loc_1800202B1
0x180020213  mov     rsi, [rbp+4Fh+var_80]
0x180020217  lea     rcx, [rbx+298h]
0x18002021e  mov     rdx, [rsi]
0x180020221  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180020227  mov     edi, eax
0x180020229  test    eax, eax
0x18002022b  js      loc_1800202B1
0x180020231  mov     rcx, [rsi]
0x180020234  mov     rax, rcx
0x180020237  mov     [rbx+260h], rcx
0x18002023e  sub     rax, rbx
0x180020241  sub     rax, 2D0h
0x180020247  sar     rax, 1
0x18002024a  sub     r13, rax
0x18002024d  test    byte ptr [r12], 20h
0x180020252  mov     [rbx+288h], r13
0x180020259  jz      short loc_1800202A7
0x18002025b  xor     edi, edi
0x18002025d  test    byte ptr [r12], 2
0x180020262  jnz     short loc_180020270
0x180020264  lea     rdx, [rbp+4Fh+var_70]; struct _WIN32_FILE_ATTRIBUTE_DATA *
0x180020268  mov     rcx, rbx; struct ENUM_WORKER_DATA *
0x18002026b  call    ?MakeRootCallback@@YAXPEAVENUM_WORKER_DATA@@PEAU_WIN32_FILE_ATTRIBUTE_DATA@@@Z; MakeRootCallback(ENUM_WORKER_DATA *,_WIN32_FILE_ATTRIBUTE_DATA *)
0x180020270  mov     rsi, [rbp+4Fh+var_78]
0x180020274  inc     dword ptr [r14]
0x180020277  cmp     dword ptr [rsi], 1
0x18002027a  jnz     short loc_180020286
0x18002027c  mov     rcx, rbx; lpFindFileData
0x18002027f  call    ?EnumFilesWorker@@YAJPEAVENUM_WORKER_DATA@@@Z; EnumFilesWorker(ENUM_WORKER_DATA *)
0x180020284  mov     edi, eax
0x180020286  dec     dword ptr [r14]
0x180020289  test    edi, edi
0x18002028b  js      short loc_1800202B1
0x18002028d  cmp     dword ptr [rsi], 1
0x180020290  jnz     short loc_1800202B1
0x180020292  test    byte ptr [r12], 2
0x180020297  jz      short loc_1800202B1
0x180020299  lea     rdx, [rbp+4Fh+var_70]; struct _WIN32_FILE_ATTRIBUTE_DATA *
0x18002029d  mov     rcx, rbx; struct ENUM_WORKER_DATA *
0x1800202a0  call    ?MakeRootCallback@@YAXPEAVENUM_WORKER_DATA@@PEAU_WIN32_FILE_ATTRIBUTE_DATA@@@Z; MakeRootCallback(ENUM_WORKER_DATA *,_WIN32_FILE_ATTRIBUTE_DATA *)
0x1800202a5  jmp     short loc_1800202B1
0x1800202a7  mov     rcx, rbx; lpFindFileData
0x1800202aa  call    ?EnumFilesWorker@@YAJPEAVENUM_WORKER_DATA@@@Z; EnumFilesWorker(ENUM_WORKER_DATA *)
0x1800202af  mov     edi, eax
0x1800202b1  lea     rcx, [rbx+298h]
0x1800202b8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800202be  mov     rcx, rbx; Block
0x1800202c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800202c6  mov     eax, edi
0x1800202c8  jmp     short loc_1800202D6
0x1800202ca  mov     eax, 80070008h
0x1800202cf  jmp     short loc_1800202D6
0x1800202d1  mov     eax, 80070057h
0x1800202d6  mov     rcx, [rbp+4Fh+var_48]
0x1800202da  xor     rcx, rsp; StackCookie
0x1800202dd  call    __security_check_cookie
0x1800202e2  add     rsp, 88h
0x1800202e9  pop     r15
0x1800202eb  pop     r14
0x1800202ed  pop     r13
0x1800202ef  pop     r12
0x1800202f1  pop     rdi
0x1800202f2  pop     rsi
0x1800202f3  pop     rbx
0x1800202f4  pop     rbp
0x1800202f5  retn
```
