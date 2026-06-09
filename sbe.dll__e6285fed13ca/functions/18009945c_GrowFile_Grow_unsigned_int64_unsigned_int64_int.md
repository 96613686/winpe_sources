# GrowFile::Grow(unsigned __int64,unsigned __int64 *,int)

- ea: `0x18009945c`
- end: `0x180099864`
- name: `?Grow@GrowFile@@QEAAJ_KPEA_KH@Z`
- size: `1032`
- prototype: `__int64 __fastcall(GrowFile *__hidden this, unsigned __int64, unsigned __int64 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180098e24`

## callees

- `0x1800017e0`
- `0x180062710`
- `0x1800627f0`
- `0x180086014`
- `0x18009945c`
- `0x180099998`
- `0x180099b08`
- `0x180099e08`
- `0x180099e9c`
- `0x18009a5f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180099848`
- `KERNEL32!LeaveCriticalSection` at `0x180099848`
- `KERNEL32!EnterCriticalSection` at `0x180099484`
- `KERNEL32!EnterCriticalSection` at `0x180099484`
- `KERNEL32!GetLastError` at `0x18009953b`
- `KERNEL32!GetLastError` at `0x1800997f0`
- `KERNEL32!GetLastError` at `0x18009953b`
- `KERNEL32!GetLastError` at `0x1800997f0`
- `KERNEL32!SetFileValidData` at `0x1800997e6`
- `KERNEL32!SetFileValidData` at `0x1800997e6`
- `KERNEL32!GetFileSizeEx` at `0x180099531`
- `KERNEL32!GetFileSizeEx` at `0x180099531`

## pseudocode

```c
Grow *__fastcall GrowFile::Grow(Grow *this, unsigned __int64 a2, unsigned __int64 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  void *v6; // r8
  unsigned int v7; // r8d
  signed int v8; // edi
  unsigned __int64 v9; // rdx
  struct CEhEventTracer *v10; // rcx
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  SAL2 *v13; // rcx
  signed int LastError; // eax
  __int64 v15; // rax
  __int64 *v16; // r14
  unsigned __int64 SystemTime; // rax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  bool v21; // zf
  signed int v22; // eax
  _BYTE v24[120]; // [rsp+20h] [rbp-F8h] BYREF
  void *v25; // [rsp+98h] [rbp-80h]
  LARGE_INTEGER FileSize; // [rsp+130h] [rbp+18h] BYREF

  FileSize.QuadPart = (LONGLONG)a3;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1360);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 34);
  GrowFile::FragInfo::FragInfo((GrowFile::FragInfo *)v24, this, *((_DWORD *)this + 332), a2);
  v6 = (void *)*((_QWORD *)this + 33);
  if ( v6 == (void *)-1LL )
  {
    v7 = 400;
LABEL_3:
    v8 = -2147418113;
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      v7);
    goto LABEL_51;
  }
  if ( !*((_DWORD *)this + 337) )
  {
    v7 = 401;
    goto LABEL_3;
  }
  if ( a2 % *((unsigned int *)this + 330) )
  {
    v8 = -2147024809;
    v10 = (Grow *)((char *)this + 168);
    v11 = -2147024809;
    v12 = 407;
LABEL_8:
    SBEBasicTracers::EtwTraceError(v10, "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp", v12, v11);
    goto LABEL_51;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v6, &FileSize) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v10 = (Grow *)((char *)this + 88);
    v11 = v8;
    v12 = 417;
    goto LABEL_8;
  }
  v15 = *((_QWORD *)this + 181);
  if ( FileSize.QuadPart != v15 )
  {
    v8 = -2147418113;
    v10 = (Grow *)((char *)this + 88);
    v11 = -2147418113;
    v12 = 418;
    goto LABEL_8;
  }
  if ( v15 != *((_QWORD *)this + 182) )
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      0x1A5u);
  v16 = (__int64 *)((char *)this + 1456);
  if ( *((_QWORD *)this + 178) )
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      0x1A8u);
  else
    v16 = (__int64 *)((char *)this + 1456);
  if ( *((_QWORD *)this + 180) )
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      0x1A9u);
  if ( *((_QWORD *)this + 179) )
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      0x1AAu);
  SystemTime = SAL2::GetSystemTime(v13);
  v18 = *v16;
  *((_QWORD *)this + 175) = SystemTime;
  *((_QWORD *)this + 180) = a2;
  v8 = 1;
  *((_QWORD *)this + 178) = v24;
  *((_QWORD *)this + 179) = a2 + v18;
  *((_QWORD *)this + 177) = 0;
  if ( *((_DWORD *)this + 338) && *((_DWORD *)this + 368) < 2u )
  {
    v19 = GrowFile::INextMethod(this, 0x28u);
    v8 = v19;
    if ( v19 < 0 )
    {
      v12 = 451;
LABEL_28:
      v11 = v19;
      v10 = (Grow *)((char *)this + 168);
      goto LABEL_8;
    }
    v19 = GrowFile::IGrowMethod1(this, 3u);
    v8 = v19;
    if ( v19 < 0 )
    {
      v12 = 452;
      goto LABEL_28;
    }
    if ( v19 )
    {
      v19 = GrowFile::INextMethod(this, 0x28u);
      v8 = v19;
      if ( v19 < 0 )
      {
        v12 = 458;
        goto LABEL_28;
      }
      v19 = GrowFile::IGrowMethod2(this);
      v8 = v19;
      if ( v19 < 0 )
      {
        v12 = 459;
        goto LABEL_28;
      }
      if ( v19 )
      {
        v19 = GrowFile::INextMethod(this, 5u);
        v8 = v19;
        if ( v19 < 0 )
        {
          v12 = 465;
          goto LABEL_28;
        }
        v19 = GrowFile::IGrowMethod1(this, 1u);
        v8 = v19;
        if ( v19 < 0 )
        {
          v12 = 466;
          goto LABEL_28;
        }
      }
    }
  }
  if ( *((_DWORD *)this + 355) > 0x64u )
    SBEBasicTracers::EtwTraceAssert(
      (Grow *)((char *)this + 168),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      0x1DFu);
  if ( v8 )
  {
    v20 = GrowFile::INextMethod(this, 1u);
    v8 = v20;
    if ( v20 < 0 )
    {
      v12 = 484;
LABEL_46:
      v11 = v20;
      v10 = (Grow *)((char *)this + 168);
      goto LABEL_8;
    }
    v20 = GrowFile::ISetFileSize(this, *((_QWORD *)this + 179), *((struct GrowFile::FragInfo **)this + 178));
    v8 = v20;
    if ( v20 < 0 )
    {
      v12 = 485;
      goto LABEL_46;
    }
    if ( !*(_DWORD *)(*((_QWORD *)this + 178) + 80LL) )
    {
      ++*((_DWORD *)this + 369);
      v8 = 1;
      ++*((_DWORD *)this + 368);
    }
  }
LABEL_51:
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 176) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 180) = 0;
  v21 = v8 == 0;
  if ( v8 >= 0 )
  {
    if ( !*((_DWORD *)this + 339) || SetFileValidData(*((HANDLE *)this + 33), *((_QWORD *)this + 181)) )
    {
      *((_QWORD *)this + 182) = *((_QWORD *)this + 181);
    }
    else
    {
      v22 = GetLastError();
      v8 = v22;
      if ( v22 > 0 )
        v8 = (unsigned __int16)v22 | 0x80070000;
    }
    v21 = v8 == 0;
  }
  if ( v21 )
  {
    *((_DWORD *)this + 368) = 0;
  }
  else if ( v8 < 0 )
  {
    GrowFile::ISetFileSize(this, *((_QWORD *)this + 182), 0);
  }
  operator delete(v25, v9);
  LeaveCriticalSection(v3);
  return (Grow *)(unsigned int)v8;
}

```

## disassembly

```asm
0x18009945c  mov     qword ptr [rsp+FileSize], r8
0x180099461  push    rbx
0x180099462  push    rbp
0x180099463  push    rsi
0x180099464  push    rdi
0x180099465  push    r12
0x180099467  push    r13
0x180099469  push    r14
0x18009946b  push    r15
0x18009946d  sub     rsp, 0D8h
0x180099474  lea     r12, [rcx+550h]
0x18009947b  mov     rbx, rcx
0x18009947e  mov     rcx, r12; lpCriticalSection
0x180099481  mov     r15, rdx
0x180099484  call    cs:__imp_EnterCriticalSection
0x18009948a  mov     r8d, [rbx+530h]; unsigned int
0x180099491  lea     rcx, [rsp+118h+var_F8]; this
0x180099496  mov     r9, r15; unsigned __int64
0x180099499  mov     rdx, rbx; struct GrowFile *
0x18009949c  call    ??0FragInfo@GrowFile@@QEAA@PEAV1@K_K@Z; GrowFile::FragInfo::FragInfo(GrowFile *,ulong,unsigned __int64)
0x1800994a1  mov     r8, [rbx+108h]
0x1800994a8  xor     r13d, r13d
0x1800994ab  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800994af  jnz     short loc_1800994D1
0x1800994b1  mov     r8d, 190h; unsigned int
0x1800994b7  lea     rcx, [rbx+58h]; struct CEhEventTracer *
0x1800994bb  mov     edi, 8000FFFFh
0x1800994c0  lea     rdx, aMultimediaDsho_1; "multimedia\\dshow\\filters\\sbe\\sal\\g"...
0x1800994c7  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800994cc  jmp     loc_1800997A1
0x1800994d1  cmp     [rbx+544h], r13d
0x1800994d8  jnz     short loc_1800994E2
0x1800994da  mov     r8d, 191h
0x1800994e0  jmp     short loc_1800994B7
0x1800994e2  mov     ecx, [rbx+528h]
0x1800994e8  xor     edx, edx
0x1800994ea  mov     rax, r15
0x1800994ed  div     rcx
0x1800994f0  test    rdx, rdx
0x1800994f3  jz      short loc_18009951E
0x1800994f5  mov     edi, 80070057h
0x1800994fa  lea     rcx, [rbx+0A8h]; struct CEhEventTracer *
0x180099501  mov     r9d, 80070057h; unsigned int
0x180099507  mov     r8d, 197h; unsigned int
0x18009950d  lea     rdx, aMultimediaDsho_1; "multimedia\\dshow\\filters\\sbe\\sal\\g"...
0x180099514  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180099519  jmp     loc_1800997A1
0x18009951e  lea     rdx, [rsp+118h+FileSize]; lpFileSize
0x180099526  mov     qword ptr [rsp+118h+FileSize], r13
0x18009952e  mov     rcx, r8; hFile
0x180099531  call    cs:__imp_GetFileSizeEx
0x180099537  test    eax, eax
0x180099539  jnz     short loc_18009955F
0x18009953b  call    cs:__imp_GetLastError
0x180099541  mov     edi, eax
0x180099543  test    eax, eax
0x180099545  jle     short loc_180099550
0x180099547  movzx   edi, ax
0x18009954a  or      edi, 80070000h
0x180099550  lea     rcx, [rbx+58h]
0x180099554  mov     r9d, edi
0x180099557  mov     r8d, 1A1h
0x18009955d  jmp     short loc_18009950D
0x18009955f  mov     rax, [rbx+5A8h]
0x180099566  cmp     qword ptr [rsp+118h+FileSize], rax
0x18009956e  jz      short loc_180099587
0x180099570  mov     edi, 8000FFFFh
0x180099575  lea     rcx, [rbx+58h]
0x180099579  mov     r9d, 8000FFFFh
0x18009957f  mov     r8d, 1A2h
0x180099585  jmp     short loc_18009950D
0x180099587  lea     rbp, [rbx+5B0h]
0x18009958e  lea     rsi, aMultimediaDsho_1; "multimedia\\dshow\\filters\\sbe\\sal\\g"...
0x180099595  lea     rdi, [rbx+58h]
0x180099599  cmp     rax, [rbp+0]
0x18009959d  jz      short loc_1800995B9
0x18009959f  mov     r8d, 1A5h; unsigned int
0x1800995a5  mov     rdx, rsi; char *
0x1800995a8  mov     rcx, rdi; struct CEhEventTracer *
0x1800995ab  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800995b0  lea     r14, [rbx+5B0h]
0x1800995b7  jmp     short loc_1800995BC
0x1800995b9  mov     r14, rbp
0x1800995bc  cmp     [rbx+590h], r13
0x1800995c3  jz      short loc_1800995D8
0x1800995c5  mov     r8d, 1A8h; unsigned int
0x1800995cb  mov     rdx, rsi; char *
0x1800995ce  mov     rcx, rdi; struct CEhEventTracer *
0x1800995d1  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800995d6  jmp     short loc_1800995DB
0x1800995d8  mov     r14, rbp
0x1800995db  cmp     [rbx+5A0h], r13
0x1800995e2  jz      short loc_1800995F5
0x1800995e4  mov     r8d, 1A9h; unsigned int
0x1800995ea  mov     rdx, rsi; char *
0x1800995ed  mov     rcx, rdi; struct CEhEventTracer *
0x1800995f0  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800995f5  cmp     [rbx+598h], r13
0x1800995fc  jz      short loc_18009960F
0x1800995fe  mov     r8d, 1AAh; unsigned int
0x180099604  mov     rdx, rsi; char *
0x180099607  mov     rcx, rdi; struct CEhEventTracer *
0x18009960a  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x18009960f  call    ?GetSystemTime@SAL2@@YA_KXZ; SAL2::GetSystemTime(void)
0x180099614  mov     rcx, [r14]
0x180099617  mov     r14d, 1
0x18009961d  add     rcx, r15
0x180099620  mov     [rbx+578h], rax
0x180099627  lea     rax, [rsp+118h+var_F8]
0x18009962c  mov     [rbx+5A0h], r15
0x180099633  mov     edi, r14d
0x180099636  mov     [rbx+590h], rax
0x18009963d  mov     [rbx+598h], rcx
0x180099644  mov     [rbx+588h], r13
0x18009964b  cmp     [rbx+548h], r13d
0x180099652  jz      loc_180099715
0x180099658  cmp     dword ptr [rbx+5C0h], 2
0x18009965f  jnb     loc_180099715
0x180099665  lea     ebp, [r14+27h]
0x180099669  mov     rcx, rbx; this
0x18009966c  mov     edx, ebp; unsigned int
0x18009966e  call    ?INextMethod@GrowFile@@AEAAJK@Z; GrowFile::INextMethod(ulong)
0x180099673  mov     edi, eax
0x180099675  test    eax, eax
0x180099677  jns     short loc_180099691
0x180099679  mov     r8d, 1C3h
0x18009967f  mov     r9d, eax
0x180099682  lea     rcx, [rbx+0A8h]
0x180099689  mov     rdx, rsi
0x18009968c  jmp     loc_180099514
0x180099691  mov     edx, 3; unsigned int
0x180099696  mov     rcx, rbx; this
0x180099699  call    ?IGrowMethod1@GrowFile@@AEAAJK@Z; GrowFile::IGrowMethod1(ulong)
0x18009969e  mov     edi, eax
0x1800996a0  test    eax, eax
0x1800996a2  jns     short loc_1800996AC
0x1800996a4  mov     r8d, 1C4h
0x1800996aa  jmp     short loc_18009967F
0x1800996ac  jz      short loc_180099715
0x1800996ae  mov     edx, ebp; unsigned int
0x1800996b0  mov     rcx, rbx; this
0x1800996b3  call    ?INextMethod@GrowFile@@AEAAJK@Z; GrowFile::INextMethod(ulong)
0x1800996b8  mov     edi, eax
0x1800996ba  test    eax, eax
0x1800996bc  jns     short loc_1800996C6
0x1800996be  mov     r8d, 1CAh
0x1800996c4  jmp     short loc_18009967F
0x1800996c6  mov     rcx, rbx; this
0x1800996c9  call    ?IGrowMethod2@GrowFile@@AEAAJXZ; GrowFile::IGrowMethod2(void)
0x1800996ce  mov     edi, eax
0x1800996d0  test    eax, eax
0x1800996d2  jns     short loc_1800996DC
0x1800996d4  mov     r8d, 1CBh
0x1800996da  jmp     short loc_18009967F
0x1800996dc  jz      short loc_180099715
0x1800996de  mov     edx, 5; unsigned int
0x1800996e3  mov     rcx, rbx; this
0x1800996e6  call    ?INextMethod@GrowFile@@AEAAJK@Z; GrowFile::INextMethod(ulong)
0x1800996eb  mov     edi, eax
0x1800996ed  test    eax, eax
0x1800996ef  jns     short loc_1800996F9
0x1800996f1  mov     r8d, 1D1h
0x1800996f7  jmp     short loc_18009967F
0x1800996f9  mov     edx, r14d; unsigned int
0x1800996fc  mov     rcx, rbx; this
0x1800996ff  call    ?IGrowMethod1@GrowFile@@AEAAJK@Z; GrowFile::IGrowMethod1(ulong)
0x180099704  mov     edi, eax
0x180099706  test    eax, eax
0x180099708  jns     short loc_180099715
0x18009970a  mov     r8d, 1D2h
0x180099710  jmp     loc_18009967F
0x180099715  cmp     dword ptr [rbx+58Ch], 64h ; 'd'
0x18009971c  lea     rbp, [rbx+0A8h]
0x180099723  jbe     short loc_180099736
0x180099725  mov     r8d, 1DFh; unsigned int
0x18009972b  mov     rdx, rsi; char *
0x18009972e  mov     rcx, rbp; struct CEhEventTracer *
0x180099731  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180099736  test    edi, edi
0x180099738  jz      short loc_1800997A1
0x18009973a  mov     edx, r14d; unsigned int
0x18009973d  mov     rcx, rbx; this
0x180099740  call    ?INextMethod@GrowFile@@AEAAJK@Z; GrowFile::INextMethod(ulong)
0x180099745  mov     edi, eax
0x180099747  test    eax, eax
0x180099749  jns     short loc_18009975F
0x18009974b  mov     r8d, 1E4h
0x180099751  mov     r9d, eax
0x180099754  mov     rdx, rsi
0x180099757  mov     rcx, rbp
0x18009975a  jmp     loc_180099514
0x18009975f  mov     r8, [rbx+590h]; struct GrowFile::FragInfo *
0x180099766  mov     rcx, rbx; this
0x180099769  mov     rdx, [rbx+598h]; unsigned __int64
0x180099770  call    ?ISetFileSize@GrowFile@@AEAAJ_KPEAVFragInfo@1@@Z; GrowFile::ISetFileSize(unsigned __int64,GrowFile::FragInfo *)
0x180099775  mov     edi, eax
0x180099777  test    eax, eax
0x180099779  jns     short loc_180099783
0x18009977b  mov     r8d, 1E5h
0x180099781  jmp     short loc_180099751
0x180099783  mov     rax, [rbx+590h]
0x18009978a  cmp     [rax+50h], r13d
0x18009978e  jnz     short loc_1800997A1
0x180099790  add     [rbx+5C4h], r14d
0x180099797  mov     edi, r14d
0x18009979a  add     [rbx+5C0h], r14d
0x1800997a1  mov     [rbx+578h], r13
0x1800997a8  mov     [rbx+580h], r13
0x1800997af  mov     [rbx+588h], r13
0x1800997b6  mov     [rbx+590h], r13
0x1800997bd  mov     [rbx+598h], r13
0x1800997c4  mov     [rbx+5A0h], r13
0x1800997cb  test    edi, edi
0x1800997cd  js      short loc_180099817
0x1800997cf  cmp     [rbx+54Ch], r13d
0x1800997d6  jz      short loc_180099807
0x1800997d8  mov     rdx, [rbx+5A8h]; ValidDataLength
0x1800997df  mov     rcx, [rbx+108h]; hFile
0x1800997e6  call    cs:__imp_SetFileValidData
0x1800997ec  test    eax, eax
0x1800997ee  jnz     short loc_180099807
0x1800997f0  call    cs:__imp_GetLastError
0x1800997f6  mov     edi, eax
0x1800997f8  test    eax, eax
0x1800997fa  jle     short loc_180099815
0x1800997fc  movzx   edi, ax
0x1800997ff  or      edi, 80070000h
0x180099805  jmp     short loc_180099815
0x180099807  mov     rax, [rbx+5A8h]
0x18009980e  mov     [rbx+5B0h], rax
0x180099815  test    edi, edi
0x180099817  jnz     short loc_180099822
0x180099819  mov     [rbx+5C0h], r13d
0x180099820  jmp     short loc_180099838
0x180099822  test    edi, edi
0x180099824  jns     short loc_180099838
0x180099826  mov     rdx, [rbx+5B0h]; unsigned __int64
0x18009982d  xor     r8d, r8d; struct GrowFile::FragInfo *
0x180099830  mov     rcx, rbx; this
0x180099833  call    ?ISetFileSize@GrowFile@@AEAAJ_KPEAVFragInfo@1@@Z; GrowFile::ISetFileSize(unsigned __int64,GrowFile::FragInfo *)
0x180099838  mov     rcx, [rsp+118h+var_80]; void *
0x180099840  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099845  mov     rcx, r12; lpCriticalSection
0x180099848  call    cs:__imp_LeaveCriticalSection
0x18009984e  mov     eax, edi
0x180099850  add     rsp, 0D8h
0x180099857  pop     r15
0x180099859  pop     r14
0x18009985b  pop     r13
0x18009985d  pop     r12
0x18009985f  pop     rdi
0x180099860  pop     rsi
0x180099861  pop     rbp
0x180099862  pop     rbx
0x180099863  retn
```
