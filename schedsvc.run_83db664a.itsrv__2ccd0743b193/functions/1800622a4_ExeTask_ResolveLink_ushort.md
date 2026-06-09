# ExeTask::ResolveLink(ushort * &)

- ea: `0x1800622a4`
- end: `0x180062647`
- name: `?ResolveLink@ExeTask@@IEAAJAEAPEAG@Z`
- size: `931`
- prototype: `__int64 __fastcall(ExeTask *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002ff98`

## callees

- `0x180001e10`
- `0x1800301f0`
- `0x180030620`
- `0x180032c30`
- `0x1800622a4`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180062334`
- `msvcrt!wcsrchr` at `0x180062555`
- `msvcrt!wcsrchr` at `0x180062334`
- `msvcrt!wcsrchr` at `0x180062555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062612`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062484`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062484`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062301`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062301`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ExeTask::ResolveLink(ExeTask *this, unsigned __int16 **a2)
{
  int v4; // ebx
  const unsigned __int16 ***v5; // rsi
  const wchar_t **v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rdi
  const unsigned __int16 **v9; // rax
  const unsigned __int16 *v10; // r8
  int v11; // r14d
  __int64 v12; // rax
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  unsigned __int16 *v18; // rax
  signed int LastError; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Src[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
  if ( v4 < 0 )
  {
LABEL_56:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v5 = (const unsigned __int16 ***)((char *)this + 48);
  v6 = (const wchar_t **)*((_QWORD *)this + 6);
  if ( v6 )
    v7 = *v6;
  else
    v7 = 0;
  v8 = -1;
  if ( wcsrchr(v7, 0x5Cu) || !_bstr_t::length((ExeTask *)((char *)this + 64)) )
  {
    if ( *v5 )
      v14 = **v5;
    else
      v14 = 0;
    v11 = StringCchCopyW(Src, 0x105u, v14);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
  }
  else
  {
    v9 = (const unsigned __int16 **)*((_QWORD *)this + 8);
    if ( v9 )
      v10 = *v9;
    else
      v10 = 0;
    v11 = StringCchCopyW(Src, 0x105u, v10);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
    v12 = -1;
    do
      ++v12;
    while ( Src[v12] );
    if ( Src[v12] != 92 )
    {
      v11 = StringCchCatW(Src, 0x105u, L"\\");
      if ( v11 < 0 )
      {
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return (unsigned int)v11;
      }
    }
    if ( *v5 )
      v13 = **v5;
    else
      v13 = 0;
    v11 = StringCchCatW(Src, 0x105u, v13);
    if ( v11 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return (unsigned int)v11;
    }
  }
  if ( ExpandEnvironmentStringsW(Src, Dst, 0x105u) - 1 > 0x104 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v21 = 0;
  v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistFile, &v21);
  if ( v4 < 0 )
    goto LABEL_54;
  v4 = (*(__int64 (__fastcall **)(__int64, WCHAR *, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, Dst, 0);
  if ( v4 < 0 )
    goto LABEL_54;
  v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
         ppv,
         Src,
         260,
         0,
         0);
  if ( v4 < 0 )
    goto LABEL_54;
  v16 = -1;
  do
    ++v16;
  while ( Src[v16] );
  if ( !v16 )
  {
    v4 = -2147418113;
    goto LABEL_54;
  }
  _bstr_t::operator=(v5, Src);
  v17 = *v5 ? **v5 : 0LL;
  v18 = wcsrchr(v17, 0x2Eu);
  *a2 = v18;
  if ( v18 )
  {
    do
      ++v8;
    while ( v18[v8] );
    if ( v8 != 1 )
    {
LABEL_54:
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      goto LABEL_56;
    }
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v21 = 0;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 1;
}

```

## disassembly

```asm
0x1800622a4  mov     [rsp-8+arg_10], rbx
0x1800622a9  push    rbp
0x1800622aa  push    rsi
0x1800622ab  push    rdi
0x1800622ac  push    r12
0x1800622ae  push    r13
0x1800622b0  push    r14
0x1800622b2  push    r15
0x1800622b4  lea     rbp, [rsp-370h]
0x1800622bc  sub     rsp, 470h
0x1800622c3  mov     rax, cs:__security_cookie
0x1800622ca  xor     rax, rsp
0x1800622cd  mov     [rbp+3A0h+var_40], rax
0x1800622d4  mov     r15, rdx
0x1800622d7  mov     r14, rcx
0x1800622da  xor     r12d, r12d
0x1800622dd  mov     [rsp+4A0h+var_470], r12
0x1800622e2  lea     rax, [rsp+4A0h+var_470]
0x1800622e7  mov     [rsp+4A0h+ppv], rax; ppv
0x1800622ec  lea     r9, IID_IShellLinkW; riid
0x1800622f3  xor     edx, edx; pUnkOuter
0x1800622f5  lea     r8d, [r12+1]; dwClsContext
0x1800622fa  lea     rcx, CLSID_ShellLink; rclsid
0x180062301  call    cs:__imp_CoCreateInstance
0x180062308  nop     dword ptr [rax+rax+00h]
0x18006230d  mov     ebx, eax
0x18006230f  test    eax, eax
0x180062311  js      loc_1800625CE
0x180062317  lea     rsi, [r14+30h]
0x18006231b  mov     rax, [rsi]
0x18006231e  test    rax, rax
0x180062321  jz      short loc_180062328
0x180062323  mov     rcx, [rax]
0x180062326  jmp     short loc_18006232B
0x180062328  mov     rcx, r12; Str
0x18006232b  mov     r13d, 5Ch ; '\'
0x180062331  mov     edx, r13d; Ch
0x180062334  call    cs:__imp_wcsrchr
0x18006233b  nop     dword ptr [rax+rax+00h]
0x180062340  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180062344  test    rax, rax
0x180062347  jnz     loc_18006242E
0x18006234d  lea     rcx, [r14+40h]; this
0x180062351  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180062356  test    eax, eax
0x180062358  jz      loc_18006242E
0x18006235e  mov     rax, [r14+40h]
0x180062362  test    rax, rax
0x180062365  jz      short loc_18006236C
0x180062367  mov     r8, [rax]
0x18006236a  jmp     short loc_18006236F
0x18006236c  mov     r8, r12; unsigned __int16 *
0x18006236f  mov     ebx, 105h
0x180062374  mov     edx, ebx; unsigned __int64
0x180062376  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18006237b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062380  mov     r14d, eax
0x180062383  test    eax, eax
0x180062385  jns     short loc_1800623A3
0x180062387  mov     rcx, [rsp+4A0h+var_470]
0x18006238c  test    rcx, rcx
0x18006238f  jz      short loc_18006239E
0x180062391  mov     rax, [rcx]
0x180062394  mov     rax, [rax+10h]
0x180062398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006239d  nop
0x18006239e  jmp     loc_18006246D
0x1800623a3  lea     rcx, [rsp+4A0h+Src]
0x1800623a8  mov     rax, rdi
0x1800623ab  inc     rax
0x1800623ae  cmp     [rcx+rax*2], r12w
0x1800623b3  jnz     short loc_1800623AB
0x1800623b5  cmp     [rsp+rax*2+4A0h+Src], r13w
0x1800623bb  jz      short loc_1800623F1
0x1800623bd  lea     r8, asc_1800A7EC0; "\\"
0x1800623c4  mov     rdx, rbx; unsigned __int64
0x1800623c7  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x1800623cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800623d1  mov     r14d, eax
0x1800623d4  test    eax, eax
0x1800623d6  jns     short loc_1800623F1
0x1800623d8  mov     rcx, [rsp+4A0h+var_470]
0x1800623dd  test    rcx, rcx
0x1800623e0  jz      short loc_1800623EF
0x1800623e2  mov     rax, [rcx]
0x1800623e5  mov     rax, [rax+10h]
0x1800623e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623ee  nop
0x1800623ef  jmp     short loc_18006246D
0x1800623f1  mov     rax, [rsi]
0x1800623f4  test    rax, rax
0x1800623f7  jz      short loc_1800623FE
0x1800623f9  mov     r8, [rax]
0x1800623fc  jmp     short loc_180062401
0x1800623fe  mov     r8, r12; unsigned __int16 *
0x180062401  mov     rdx, rbx; unsigned __int64
0x180062404  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x180062409  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006240e  mov     r14d, eax
0x180062411  test    eax, eax
0x180062413  jns     short loc_180062475
0x180062415  mov     rcx, [rsp+4A0h+var_470]
0x18006241a  test    rcx, rcx
0x18006241d  jz      short loc_18006242C
0x18006241f  mov     rax, [rcx]
0x180062422  mov     rax, [rax+10h]
0x180062426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006242b  nop
0x18006242c  jmp     short loc_18006246D
0x18006242e  mov     rax, [rsi]
0x180062431  test    rax, rax
0x180062434  jz      short loc_18006243B
0x180062436  mov     r8, [rax]
0x180062439  jmp     short loc_18006243E
0x18006243b  mov     r8, r12; unsigned __int16 *
0x18006243e  mov     ebx, 105h
0x180062443  mov     edx, ebx; unsigned __int64
0x180062445  lea     rcx, [rsp+4A0h+Src]; unsigned __int16 *
0x18006244a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006244f  mov     r14d, eax
0x180062452  test    eax, eax
0x180062454  jns     short loc_180062475
0x180062456  mov     rcx, [rsp+4A0h+var_470]
0x18006245b  test    rcx, rcx
0x18006245e  jz      short loc_18006246D
0x180062460  mov     rax, [rcx]
0x180062463  mov     rax, [rax+10h]
0x180062467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006246c  nop
0x18006246d  mov     eax, r14d
0x180062470  jmp     loc_1800625E7
0x180062475  mov     r8d, ebx; nSize
0x180062478  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x18006247f  lea     rcx, [rsp+4A0h+Src]; lpSrc
0x180062484  call    cs:__imp_ExpandEnvironmentStringsW
0x18006248b  nop     dword ptr [rax+rax+00h]
0x180062490  dec     eax
0x180062492  mov     r14d, 104h
0x180062498  cmp     eax, r14d
0x18006249b  ja      loc_180062612
0x1800624a1  mov     [rsp+4A0h+var_468], r12
0x1800624a6  mov     rcx, [rsp+4A0h+var_470]
0x1800624ab  mov     rax, [rcx]
0x1800624ae  lea     r8, [rsp+4A0h+var_468]
0x1800624b3  lea     rdx, IID_IPersistFile
0x1800624ba  mov     rax, [rax]
0x1800624bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624c2  mov     ebx, eax
0x1800624c4  test    eax, eax
0x1800624c6  js      loc_1800625B7
0x1800624cc  mov     rcx, [rsp+4A0h+var_468]
0x1800624d1  mov     rax, [rcx]
0x1800624d4  xor     r8d, r8d
0x1800624d7  lea     rdx, [rbp+3A0h+Dst]
0x1800624de  mov     rax, [rax+28h]
0x1800624e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624e7  mov     ebx, eax
0x1800624e9  test    eax, eax
0x1800624eb  js      loc_1800625B7
0x1800624f1  mov     rcx, [rsp+4A0h+var_470]
0x1800624f6  mov     rax, [rcx]
0x1800624f9  mov     dword ptr [rsp+4A0h+ppv], r12d
0x1800624fe  xor     r9d, r9d
0x180062501  mov     r8d, r14d
0x180062504  lea     rdx, [rsp+4A0h+Src]
0x180062509  mov     rax, [rax+18h]
0x18006250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062512  mov     ebx, eax
0x180062514  test    eax, eax
0x180062516  js      loc_1800625B7
0x18006251c  lea     rcx, [rsp+4A0h+Src]
0x180062521  mov     rax, rdi
0x180062524  inc     rax
0x180062527  cmp     [rcx+rax*2], r12w
0x18006252c  jnz     short loc_180062524
0x18006252e  test    rax, rax
0x180062531  jz      short loc_1800625B2
0x180062533  lea     rdx, [rsp+4A0h+Src]
0x180062538  mov     rcx, rsi
0x18006253b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180062540  mov     rcx, [rsi]
0x180062543  test    rcx, rcx
0x180062546  jz      short loc_18006254D
0x180062548  mov     rcx, [rcx]
0x18006254b  jmp     short loc_180062550
0x18006254d  mov     rcx, r12; Str
0x180062550  mov     edx, 2Eh ; '.'; Ch
0x180062555  call    cs:__imp_wcsrchr
0x18006255c  nop     dword ptr [rax+rax+00h]
0x180062561  mov     [r15], rax
0x180062564  test    rax, rax
0x180062567  jz      short loc_180062579
0x180062569  inc     rdi
0x18006256c  cmp     [rax+rdi*2], r12w
0x180062571  jnz     short loc_180062569
0x180062573  cmp     rdi, 1
0x180062577  jnz     short loc_1800625B7
0x180062579  mov     rcx, [rsp+4A0h+var_468]
0x18006257e  test    rcx, rcx
0x180062581  jz      short loc_18006258F
0x180062583  mov     rax, [rcx]
0x180062586  mov     rax, [rax+10h]
0x18006258a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006258f  mov     [rsp+4A0h+var_468], r12
0x180062594  mov     rcx, [rsp+4A0h+var_470]
0x180062599  test    rcx, rcx
0x18006259c  jz      short loc_1800625AB
0x18006259e  mov     rdx, [rcx]
0x1800625a1  mov     rax, [rdx+10h]
0x1800625a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625aa  nop
0x1800625ab  mov     eax, 1
0x1800625b0  jmp     short loc_1800625E7
0x1800625b2  mov     ebx, 8000FFFFh
0x1800625b7  mov     rcx, [rsp+4A0h+var_468]
0x1800625bc  test    rcx, rcx
0x1800625bf  jz      short loc_1800625CE
0x1800625c1  mov     rax, [rcx]
0x1800625c4  mov     rax, [rax+10h]
0x1800625c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625cd  nop
0x1800625ce  mov     rcx, [rsp+4A0h+var_470]
0x1800625d3  test    rcx, rcx
0x1800625d6  jz      short loc_1800625E5
0x1800625d8  mov     rax, [rcx]
0x1800625db  mov     rax, [rax+10h]
0x1800625df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625e4  nop
0x1800625e5  mov     eax, ebx
0x1800625e7  mov     rcx, [rbp+3A0h+var_40]
0x1800625ee  xor     rcx, rsp; StackCookie
0x1800625f1  call    __security_check_cookie
0x1800625f6  mov     rbx, [rsp+4A0h+arg_10]
0x1800625fe  add     rsp, 470h
0x180062605  pop     r15
0x180062607  pop     r14
0x180062609  pop     r13
0x18006260b  pop     r12
0x18006260d  pop     rdi
0x18006260e  pop     rsi
0x18006260f  pop     rbp
0x180062610  retn
0x180062612  call    cs:__imp_GetLastError
0x180062619  nop     dword ptr [rax+rax+00h]
0x18006261e  nop
0x18006261f  mov     ebx, eax
0x180062621  test    eax, eax
0x180062623  jle     short loc_18006262E
0x180062625  movzx   ebx, ax
0x180062628  or      ebx, 80070000h
0x18006262e  mov     rcx, [rsp+4A0h+var_470]
0x180062633  test    rcx, rcx
0x180062636  jz      short loc_180062645
0x180062638  mov     rdx, [rcx]
0x18006263b  mov     rax, [rdx+10h]
0x18006263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062644  nop
0x180062645  jmp     short loc_1800625E5
```
