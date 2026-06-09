# ATL::AtlCreateTargetDC(HDC__ *,tagDVTARGETDEVICE *)

- ea: `0x180002fd8`
- end: `0x1800033fe`
- name: `?AtlCreateTargetDC@ATL@@YAPEAUHDC__@@PEAU2@PEAUtagDVTARGETDEVICE@@@Z`
- size: `1062`
- prototype: `HDC __fastcall(HDC, struct tagDVTARGETDEVICE *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007ca0`

## callees

- `0x180002fd8`
- `0x180003404`
- `0x180003b70`
- `0x1800099ac`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!free` at `0x180003397`
- `msvcrt!free` at `0x180003397`
- `msvcrt!malloc` at `0x1800030c1`
- `msvcrt!malloc` at `0x1800031b3`
- `msvcrt!malloc` at `0x180003299`
- `msvcrt!malloc` at `0x180003358`
- `msvcrt!malloc` at `0x1800030c1`
- `msvcrt!malloc` at `0x1800031b3`
- `msvcrt!malloc` at `0x180003299`
- `msvcrt!malloc` at `0x180003358`
- `GDI32!GetDeviceCaps` at `0x1800033b1`
- `GDI32!GetDeviceCaps` at `0x1800033b1`
- `GDI32!CreateDCA` at `0x180003386`
- `GDI32!CreateDCA` at `0x1800033d0`
- `GDI32!CreateDCA` at `0x180003386`
- `GDI32!CreateDCA` at `0x1800033d0`
- `KERNEL32!WideCharToMultiByte` at `0x180003103`
- `KERNEL32!WideCharToMultiByte` at `0x1800031f5`
- `KERNEL32!WideCharToMultiByte` at `0x1800032db`
- `KERNEL32!WideCharToMultiByte` at `0x180003103`
- `KERNEL32!WideCharToMultiByte` at `0x1800031f5`
- `KERNEL32!WideCharToMultiByte` at `0x1800032db`

## pseudocode

```c
HDC __fastcall ATL::AtlCreateTargetDC(HDC a1, struct tagDVTARGETDEVICE *a2)
{
  _QWORD *v4; // rbx
  const struct _devicemodeW *v5; // r14
  __int64 tdDriverNameOffset; // r12
  __int64 tdDeviceNameOffset; // r13
  const WCHAR *v8; // r12
  __int64 v9; // rax
  __int64 cbMultiByte; // r15
  unsigned __int64 v11; // rax
  void *v12; // rsp
  CHAR *lpMultiByteStr; // rsi
  _QWORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned __int64 v17; // rax
  void *v18; // rsp
  CHAR *v19; // rsi
  _QWORD *v20; // rax
  const CHAR *v21; // r13
  const WCHAR *v22; // r12
  __int64 v23; // rax
  __int64 v24; // r15
  unsigned __int64 v25; // rax
  void *v26; // rsp
  CHAR *v27; // rsi
  _QWORD *v28; // rax
  const CHAR *v29; // rdi
  const DEVMODEA *v30; // rax
  ATL::_ATL_SAFE_ALLOCA_IMPL *v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  void *v34; // rsp
  void *v35; // rsp
  struct _devicemodeA *v36; // rcx
  _QWORD *v37; // rax
  HDC DCA; // rdi
  void *v39; // rcx
  CHAR MultiByteStr[2]; // [rsp+40h] [rbp+0h] BYREF
  LPCSTR pwszDriver; // [rsp+48h] [rbp+8h]

  if ( !a2 )
  {
    if ( !a1 || GetDeviceCaps(a1, 2) == 5 )
      return CreateDCA("DISPLAY", 0, 0, 0);
    else
      return a1;
  }
  v4 = 0;
  if ( a2->tdExtDevmodeOffset )
    v5 = (const struct _devicemodeW *)((char *)a2 + a2->tdExtDevmodeOffset);
  else
    v5 = 0;
  tdDriverNameOffset = a2->tdDriverNameOffset;
  tdDeviceNameOffset = a2->tdDeviceNameOffset;
  *(_WORD *)MultiByteStr = a2->tdPortNameOffset;
  v8 = (const WCHAR *)((char *)a2 + tdDriverNameOffset);
  if ( !v8 )
    goto LABEL_22;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  cbMultiByte = 2LL * ((int)v9 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) <= 0xFFFFFFFF )
  {
    if ( (int)cbMultiByte <= 1024
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte, 0) )
    {
      v11 = (int)cbMultiByte + 15LL;
      if ( v11 < (int)cbMultiByte )
        v11 = 0xFFFFFFFFFFFFFF0LL;
      v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
      lpMultiByteStr = MultiByteStr;
    }
    else
    {
      if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
        goto LABEL_74;
      v14 = malloc((int)cbMultiByte + 16LL);
      if ( v14 )
      {
        *v14 = 0;
        lpMultiByteStr = (CHAR *)(v14 + 2);
        v4 = v14;
      }
      else
      {
        lpMultiByteStr = 0;
      }
    }
    if ( lpMultiByteStr )
    {
      *lpMultiByteStr = 0;
      pwszDriver = (LPCSTR)((unsigned __int64)lpMultiByteStr
                          & -(__int64)(WideCharToMultiByte(3u, 0, v8, -1, lpMultiByteStr, cbMultiByte, 0, 0) != 0));
    }
    else
    {
      pwszDriver = 0;
    }
  }
  else
  {
LABEL_22:
    pwszDriver = 0;
  }
  if ( !(struct tagDVTARGETDEVICE *)((char *)a2 + tdDeviceNameOffset) )
    goto LABEL_38;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)((char *)&a2->tdSize + 2 * v15 + tdDeviceNameOffset) );
  v16 = 2LL * ((int)v15 + 1);
  if ( (unsigned __int64)(v16 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_38;
  if ( (int)v16 <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v16, 0) )
  {
    v17 = (int)v16 + 15LL;
    if ( v17 < (int)v16 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
    v19 = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)v16 < 0x10 )
      goto LABEL_74;
    v20 = malloc((int)v16 + 16LL);
    if ( v20 )
    {
      *v20 = v4;
      v19 = (CHAR *)(v20 + 2);
      v4 = v20;
    }
    else
    {
      v19 = 0;
    }
  }
  if ( v19 )
  {
    *v19 = 0;
    v21 = (const CHAR *)((unsigned __int64)v19
                       & -(__int64)(WideCharToMultiByte(
                                      3u,
                                      0,
                                      (LPCWCH)((char *)a2 + tdDeviceNameOffset),
                                      -1,
                                      v19,
                                      v16,
                                      0,
                                      0) != 0));
  }
  else
  {
LABEL_38:
    v21 = 0;
  }
  v22 = (const WCHAR *)((char *)a2 + *(unsigned __int16 *)MultiByteStr);
  if ( !v22 )
    goto LABEL_54;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  v24 = 2LL * ((int)v23 + 1);
  if ( (unsigned __int64)(v24 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_54;
  if ( (int)v24 > 1024
    || !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v24, 0) )
  {
    if ( (unsigned __int64)~(__int64)(int)v24 >= 0x10 )
    {
      v28 = malloc((int)v24 + 16LL);
      if ( v28 )
      {
        *v28 = v4;
        v27 = (CHAR *)(v28 + 2);
        v4 = v28;
      }
      else
      {
        v27 = 0;
      }
      goto LABEL_52;
    }
LABEL_74:
    ATL::AtlThrowImpl(-2147024809);
  }
  v25 = (int)v24 + 15LL;
  if ( v25 < (int)v24 )
    v25 = 0xFFFFFFFFFFFFFF0LL;
  v26 = alloca(v25 & 0xFFFFFFFFFFFFFFF0uLL);
  v27 = MultiByteStr;
LABEL_52:
  if ( !v27 )
  {
LABEL_54:
    v29 = 0;
    goto LABEL_55;
  }
  *v27 = 0;
  v29 = (const CHAR *)((unsigned __int64)v27 & -(__int64)(WideCharToMultiByte(3u, 0, v22, -1, v27, v24, 0, 0) != 0));
LABEL_55:
  if ( v5 )
  {
    v31 = (ATL::_ATL_SAFE_ALLOCA_IMPL *)(v5->dmDriverExtra + 156LL);
    if ( (unsigned __int64)v31 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(v31, 0) )
    {
      v32 = v5->dmDriverExtra + 171LL;
      if ( v32 <= (unsigned __int64)v5->dmDriverExtra + 156 )
        v32 = 0xFFFFFFFFFFFFFF0LL;
      v33 = v32 & 0xFFFFFFFFFFFFFFF0uLL;
      v34 = alloca(v33);
      v35 = alloca(v33);
      v36 = (struct _devicemodeA *)MultiByteStr;
    }
    else
    {
      v37 = malloc(v5->dmDriverExtra + 172LL);
      if ( v37 )
      {
        *v37 = v4;
        v36 = (struct _devicemodeA *)(v37 + 2);
        v4 = v37;
      }
      else
      {
        v36 = 0;
      }
    }
    v30 = AtlDevModeW2A(v36, v5);
  }
  else
  {
    v30 = 0;
  }
  DCA = CreateDCA(pwszDriver, v21, v29, v30);
  while ( v4 )
  {
    v39 = v4;
    v4 = (_QWORD *)*v4;
    free(v39);
  }
  return DCA;
}

```

## disassembly

```asm
0x180002fd8  push    rbp
0x180002fda  push    rbx
0x180002fdb  push    rsi
0x180002fdc  push    rdi
0x180002fdd  push    r12
0x180002fdf  push    r13
0x180002fe1  push    r14
0x180002fe3  push    r15
0x180002fe5  sub     rsp, 68h
0x180002fe9  lea     rbp, [rsp+40h]
0x180002fee  mov     rax, cs:__security_cookie
0x180002ff5  xor     rax, rbp
0x180002ff8  mov     [rbp+60h+var_50], rax
0x180002ffc  mov     rdi, rdx
0x180002fff  mov     rbx, rcx
0x180003002  xor     edx, edx; unsigned __int64
0x180003004  test    rdi, rdi
0x180003007  jz      loc_1800033A7
0x18000300d  mov     ebx, edx
0x18000300f  cmp     [rdi+0Ah], dx
0x180003013  jnz     short loc_18000301A
0x180003015  mov     r14d, edx
0x180003018  jmp     short loc_180003022
0x18000301a  movzx   r14d, word ptr [rdi+0Ah]
0x18000301f  add     r14, rdi
0x180003022  movzx   r12d, word ptr [rdi+4]
0x180003027  mov     r8d, 80000000h
0x18000302d  movzx   eax, word ptr [rdi+8]
0x180003031  mov     r9d, 0FFFFFFFFh
0x180003037  movzx   r13d, word ptr [rdi+6]
0x18000303c  mov     word ptr [rbp+60h+MultiByteStr], ax
0x180003040  add     r12, rdi
0x180003043  jz      loc_18000312B
0x180003049  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000304d  inc     rax
0x180003050  cmp     [r12+rax*2], dx
0x180003055  jnz     short loc_18000304D
0x180003057  inc     eax
0x180003059  movsxd  rcx, eax
0x18000305c  lea     r15, [rcx+rcx]
0x180003060  lea     rax, [r15+r8]
0x180003064  cmp     rax, r9
0x180003067  ja      loc_18000312B
0x18000306d  movsxd  rsi, r15d
0x180003070  cmp     r15d, 400h
0x180003077  jg      short loc_1800030AD
0x180003079  mov     rcx, rsi; this
0x18000307c  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003081  xor     edx, edx
0x180003083  test    al, al
0x180003085  jz      short loc_1800030AD
0x180003087  lea     rax, [rsi+0Fh]
0x18000308b  cmp     rax, rsi
0x18000308e  ja      short loc_18000309A
0x180003090  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000309a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000309e  call    _alloca_probe
0x1800030a3  sub     rsp, rax
0x1800030a6  lea     rsi, [rsp+0A0h+MultiByteStr]
0x1800030ab  jmp     short loc_1800030DC
0x1800030ad  mov     rax, rsi
0x1800030b0  not     rax
0x1800030b3  cmp     rax, 10h
0x1800030b7  jb      loc_1800033F3
0x1800030bd  lea     rcx, [rsi+10h]; Size
0x1800030c1  call    cs:__imp_malloc
0x1800030c7  xor     edx, edx
0x1800030c9  test    rax, rax
0x1800030cc  jnz     short loc_1800030D2
0x1800030ce  mov     esi, edx
0x1800030d0  jmp     short loc_1800030DC
0x1800030d2  mov     [rax], rdx
0x1800030d5  lea     rsi, [rax+10h]
0x1800030d9  mov     rbx, rax
0x1800030dc  test    rsi, rsi
0x1800030df  jz      short loc_180003119
0x1800030e1  mov     [rsp+0A0h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800030e6  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800030ea  mov     [rsp+0A0h+lpDefaultChar], rdx; lpDefaultChar
0x1800030ef  mov     r8, r12; lpWideCharStr
0x1800030f2  mov     [rsi], dl
0x1800030f4  xor     edx, edx; dwFlags
0x1800030f6  mov     [rsp+0A0h+cbMultiByte], r15d; cbMultiByte
0x1800030fb  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpMultiByteStr
0x180003100  lea     ecx, [rdx+3]; CodePage
0x180003103  call    cs:__imp_WideCharToMultiByte
0x180003109  neg     eax
0x18000310b  sbb     rcx, rcx
0x18000310e  and     rcx, rsi
0x180003111  mov     [rbp+60h+pwszDriver], rcx
0x180003115  xor     edx, edx
0x180003117  jmp     short loc_18000311D
0x180003119  mov     [rbp+60h+pwszDriver], rdx
0x18000311d  mov     r8d, 80000000h
0x180003123  mov     r9d, 0FFFFFFFFh
0x180003129  jmp     short loc_18000312F
0x18000312b  mov     [rbp+60h+pwszDriver], rdx
0x18000312f  mov     r12, r13
0x180003132  add     r12, rdi
0x180003135  jz      loc_180003207
0x18000313b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000313f  inc     rax
0x180003142  cmp     [r12+rax*2], dx
0x180003147  jnz     short loc_18000313F
0x180003149  inc     eax
0x18000314b  movsxd  rcx, eax
0x18000314e  lea     r15, [rcx+rcx]
0x180003152  lea     rax, [r15+r8]
0x180003156  cmp     rax, r9
0x180003159  ja      loc_180003207
0x18000315f  movsxd  rsi, r15d
0x180003162  cmp     r15d, 400h
0x180003169  jg      short loc_18000319F
0x18000316b  mov     rcx, rsi; this
0x18000316e  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003173  xor     edx, edx
0x180003175  test    al, al
0x180003177  jz      short loc_18000319F
0x180003179  lea     rax, [rsi+0Fh]
0x18000317d  cmp     rax, rsi
0x180003180  ja      short loc_18000318C
0x180003182  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000318c  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003190  call    _alloca_probe
0x180003195  sub     rsp, rax
0x180003198  lea     rsi, [rsp+0A0h+MultiByteStr]
0x18000319d  jmp     short loc_1800031CE
0x18000319f  mov     rax, rsi
0x1800031a2  not     rax
0x1800031a5  cmp     rax, 10h
0x1800031a9  jb      loc_1800033F3
0x1800031af  lea     rcx, [rsi+10h]; Size
0x1800031b3  call    cs:__imp_malloc
0x1800031b9  xor     edx, edx
0x1800031bb  test    rax, rax
0x1800031be  jnz     short loc_1800031C4
0x1800031c0  mov     esi, edx
0x1800031c2  jmp     short loc_1800031CE
0x1800031c4  mov     [rax], rbx
0x1800031c7  lea     rsi, [rax+10h]
0x1800031cb  mov     rbx, rax
0x1800031ce  test    rsi, rsi
0x1800031d1  jz      short loc_180003207
0x1800031d3  mov     [rsp+0A0h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800031d8  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800031dc  mov     [rsp+0A0h+lpDefaultChar], rdx; lpDefaultChar
0x1800031e1  mov     r8, r12; lpWideCharStr
0x1800031e4  mov     [rsi], dl
0x1800031e6  xor     edx, edx; dwFlags
0x1800031e8  mov     [rsp+0A0h+cbMultiByte], r15d; cbMultiByte
0x1800031ed  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800031f2  lea     ecx, [rdx+3]; CodePage
0x1800031f5  call    cs:__imp_WideCharToMultiByte
0x1800031fb  neg     eax
0x1800031fd  sbb     r13, r13
0x180003200  and     r13, rsi
0x180003203  xor     edx, edx
0x180003205  jmp     short loc_18000320A
0x180003207  mov     r13, rdx
0x18000320a  movzx   r12d, word ptr [rbp+60h+MultiByteStr]
0x18000320f  add     r12, rdi
0x180003212  jz      loc_1800032ED
0x180003218  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000321c  inc     rax
0x18000321f  cmp     [r12+rax*2], dx
0x180003224  jnz     short loc_18000321C
0x180003226  inc     eax
0x180003228  movsxd  rcx, eax
0x18000322b  mov     eax, 80000000h
0x180003230  lea     r15, [rcx+rcx]
0x180003234  mov     ecx, 0FFFFFFFFh
0x180003239  add     rax, r15
0x18000323c  cmp     rax, rcx
0x18000323f  ja      loc_1800032ED
0x180003245  movsxd  rdi, r15d
0x180003248  cmp     r15d, 400h
0x18000324f  jg      short loc_180003285
0x180003251  mov     rcx, rdi; this
0x180003254  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003259  xor     edx, edx
0x18000325b  test    al, al
0x18000325d  jz      short loc_180003285
0x18000325f  lea     rax, [rdi+0Fh]
0x180003263  cmp     rax, rdi
0x180003266  ja      short loc_180003272
0x180003268  mov     rax, 0FFFFFFFFFFFFFF0h
0x180003272  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003276  call    _alloca_probe
0x18000327b  sub     rsp, rax
0x18000327e  lea     rsi, [rsp+0A0h+MultiByteStr]
0x180003283  jmp     short loc_1800032B4
0x180003285  mov     rax, rdi
0x180003288  not     rax
0x18000328b  cmp     rax, 10h
0x18000328f  jb      loc_1800033F3
0x180003295  lea     rcx, [rdi+10h]; Size
0x180003299  call    cs:__imp_malloc
0x18000329f  xor     edx, edx
0x1800032a1  test    rax, rax
0x1800032a4  jnz     short loc_1800032AA
0x1800032a6  mov     esi, edx
0x1800032a8  jmp     short loc_1800032B4
0x1800032aa  mov     [rax], rbx
0x1800032ad  lea     rsi, [rax+10h]
0x1800032b1  mov     rbx, rax
0x1800032b4  test    rsi, rsi
0x1800032b7  jz      short loc_1800032ED
0x1800032b9  mov     [rsp+0A0h+lpUsedDefaultChar], rdx; lpUsedDefaultChar
0x1800032be  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800032c2  mov     [rsp+0A0h+lpDefaultChar], rdx; lpDefaultChar
0x1800032c7  mov     r8, r12; lpWideCharStr
0x1800032ca  mov     [rsi], dl
0x1800032cc  xor     edx, edx; dwFlags
0x1800032ce  mov     [rsp+0A0h+cbMultiByte], r15d; cbMultiByte
0x1800032d3  mov     [rsp+0A0h+lpMultiByteStr], rsi; lpMultiByteStr
0x1800032d8  lea     ecx, [rdx+3]; CodePage
0x1800032db  call    cs:__imp_WideCharToMultiByte
0x1800032e1  neg     eax
0x1800032e3  sbb     rdi, rdi
0x1800032e6  and     rdi, rsi
0x1800032e9  xor     edx, edx
0x1800032eb  jmp     short loc_1800032F0
0x1800032ed  mov     rdi, rdx
0x1800032f0  test    r14, r14
0x1800032f3  jnz     short loc_1800032FA
0x1800032f5  mov     rax, rdx
0x1800032f8  jmp     short loc_180003379
0x1800032fa  movzx   ecx, word ptr [r14+46h]
0x1800032ff  add     rcx, 9Ch; this
0x180003306  cmp     rcx, 400h
0x18000330d  ja      short loc_18000334C
0x18000330f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180003314  test    al, al
0x180003316  jz      short loc_18000334C
0x180003318  movzx   eax, word ptr [r14+46h]
0x18000331d  add     rax, 9Ch
0x180003323  lea     rcx, [rax+0Fh]
0x180003327  cmp     rcx, rax
0x18000332a  ja      short loc_180003336
0x18000332c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180003336  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000333a  mov     rax, rcx
0x18000333d  call    _alloca_probe
0x180003342  sub     rsp, rcx
0x180003345  lea     rcx, [rsp+0A0h+MultiByteStr]
0x18000334a  jmp     short loc_180003371
0x18000334c  movzx   ecx, word ptr [r14+46h]
0x180003351  add     rcx, 0ACh; Size
0x180003358  call    cs:__imp_malloc
0x18000335e  test    rax, rax
0x180003361  jnz     short loc_180003367
0x180003363  xor     ecx, ecx
0x180003365  jmp     short loc_180003371
0x180003367  mov     [rax], rbx
0x18000336a  lea     rcx, [rax+10h]; struct _devicemodeA *
0x18000336e  mov     rbx, rax
0x180003371  mov     rdx, r14; struct _devicemodeW *
0x180003374  call    ?AtlDevModeW2A@@YAPEAU_devicemodeA@@PEAU1@PEBU_devicemodeW@@@Z; AtlDevModeW2A(_devicemodeA *,_devicemodeW const *)
0x180003379  mov     rcx, [rbp+60h+pwszDriver]; pwszDriver
0x18000337d  mov     r9, rax; pdm
0x180003380  mov     r8, rdi; pszPort
0x180003383  mov     rdx, r13; pwszDevice
0x180003386  call    cs:__imp_CreateDCA
0x18000338c  mov     rdi, rax
0x18000338f  jmp     short loc_18000339D
0x180003391  mov     rcx, rbx; Block
0x180003394  mov     rbx, [rbx]
0x180003397  call    cs:__imp_free
0x18000339d  test    rbx, rbx
0x1800033a0  jnz     short loc_180003391
0x1800033a2  mov     rax, rdi
0x1800033a5  jmp     short loc_1800033D6
0x1800033a7  test    rbx, rbx
0x1800033aa  jz      short loc_1800033C1
0x1800033ac  mov     edx, 2; index
0x1800033b1  call    cs:__imp_GetDeviceCaps
0x1800033b7  cmp     eax, 5
0x1800033ba  jz      short loc_1800033C1
0x1800033bc  mov     rax, rbx
0x1800033bf  jmp     short loc_1800033D6
0x1800033c1  xor     r9d, r9d; pdm
0x1800033c4  lea     rcx, pwszDriver; "DISPLAY"
0x1800033cb  xor     r8d, r8d; pszPort
0x1800033ce  xor     edx, edx; pwszDevice
0x1800033d0  call    cs:__imp_CreateDCA
0x1800033d6  mov     rcx, [rbp+60h+var_50]
0x1800033da  xor     rcx, rbp; StackCookie
0x1800033dd  call    __security_check_cookie
0x1800033e2  lea     rsp, [rbp+28h]
0x1800033e6  pop     r15
0x1800033e8  pop     r14
0x1800033ea  pop     r13
0x1800033ec  pop     r12
0x1800033ee  pop     rdi
0x1800033ef  pop     rsi
0x1800033f0  pop     rbx
0x1800033f1  pop     rbp
0x1800033f2  retn
0x1800033f3  mov     ecx, 80070057h; int
0x1800033f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
