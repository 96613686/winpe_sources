# SrmGetDirectoryExclusionsForVolume(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800a46cc`
- end: `0x1800a4c99`
- name: `?SrmGetDirectoryExclusionsForVolume@@YAXPEBGAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV12@2@Z`
- size: `1485`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, service_task`

## callers

- `0x1800a44f4`

## callees

- `0x180001350`
- `0x18000cd60`
- `0x18000ead4`
- `0x18000eef4`
- `0x180010bc4`
- `0x18001a370`
- `0x18001af28`
- `0x1800208e8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073f54`
- `0x180074048`
- `0x1800a3b84`
- `0x1800a3c00`
- `0x1800a3e34`
- `0x1800a46cc`
- `0x1800a4ca0`
- `0x1800a4d60`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800a48c5`
- `msvcrt!_wcsnicmp` at `0x1800a48c5`
- `ole32!CoTaskMemFree` at `0x1800a4839`
- `ole32!CoTaskMemFree` at `0x1800a4a1d`
- `ole32!CoTaskMemFree` at `0x1800a4839`
- `ole32!CoTaskMemFree` at `0x1800a4a1d`

## string_xrefs

- `0x1800a4720`: `SrmGetDirectoryExclusionsForVolume`
- `0x1800a4a46`: `SrmGetDirectoryExclusionsForVolume`
- `0x1800a4ac3`: `Protected directory: <%s>`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall SrmGetDirectoryExclusionsForVolume(_WORD *a1, __int64 *a2, const unsigned __int16 **a3, __int64 a4)
{
  __int64 i; // rbx
  const WCHAR *v8; // rdx
  LPVOID v9; // rdi
  void *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // r8
  wchar_t **v14; // rdx
  const wchar_t *v15; // r10
  const wchar_t *v16; // rcx
  unsigned __int8 v17; // al
  int v18; // edi
  __int64 v19; // rax
  __int64 v20; // rdx
  void **v21; // rcx
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r8
  void **v24; // rdx
  _WORD *v25; // r10
  __int64 *v26; // rbx
  const unsigned __int16 **v27; // r15
  __int64 *v28; // rdi
  _WORD *v29; // rdx
  __int64 *v30; // rdi
  _WORD *v31; // rdx
  _WORD *v32; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 **v35; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v36; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v37; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v38; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+60h] [rbp-A0h]
  int v40; // [rsp+64h] [rbp-9Ch]
  int v41; // [rsp+68h] [rbp-98h]
  _BYTE v42[96]; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+D0h] [rbp-30h]
  __int128 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-18h]
  wchar_t *String1[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v47; // [rsp+108h] [rbp+8h]
  unsigned __int64 v48; // [rsp+110h] [rbp+10h]
  void *v49[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v50; // [rsp+130h] [rbp+30h]
  unsigned __int64 v51; // [rsp+138h] [rbp+38h]
  int v52; // [rsp+148h] [rbp+48h]
  void *v53[2]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v54; // [rsp+160h] [rbp+60h]
  unsigned __int64 v55; // [rsp+168h] [rbp+68h]
  void *Block[2]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v57; // [rsp+188h] [rbp+88h]
  unsigned __int64 v58; // [rsp+190h] [rbp+90h]
  void *v59[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v60; // [rsp+1B8h] [rbp+B8h]
  _QWORD v61[22]; // [rsp+1D0h] [rbp+D0h] BYREF

  v35 = a3;
  pv = &v36;
  v36 = L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp";
  v37 = L"SrmGetDirectoryExclusionsForVolume";
  v38 = L"PROTFLSC";
  v39 = 271;
  v40 = 20;
  v41 = 255;
  v43 = 0x1000000;
  memset_0(v42, 0, sizeof(v42));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v61, (const struct CSrmDebugInfo *)&v36, 0);
  v32 = a1;
  CSrmFunctionTracer::Trace((CSrmFunctionTracer *)v61, 0x8Cu, 0x111u, L"Input volume name is %s");
  v51 = 7;
  v50 = 0;
  LOWORD(v49[0]) = 0;
  v55 = 7;
  v54 = 0;
  LOWORD(v53[0]) = 0;
  v44 = 0;
  v45 = 0;
  for ( i = *a2; i != a2[1]; i += 40 )
  {
    v34 = 0;
    std::wstring::wstring(String1, i);
    pv = 0;
    v8 = (const WCHAR *)String1;
    if ( v48 >= 8 )
      v8 = String1[0];
    CSrmAutoPWSZ::ExpandEnvironmentStringsW((CSrmAutoPWSZ *)&pv, v8);
    v9 = pv;
    if ( pv )
    {
      v11 = -1;
      do
        ++v11;
      while ( *((_WORD *)pv + v11) );
      std::wstring::assign(String1, pv);
      v10 = v9;
    }
    else
    {
      v10 = 0;
    }
    CoTaskMemFree(v10);
    pv = 0;
    v12 = 13;
    if ( v47 >= 0xD )
    {
      v13 = 13;
    }
    else
    {
      v12 = v47;
      v13 = v47;
    }
    v14 = String1;
    if ( v48 >= 8 )
      v14 = (wchar_t **)String1[0];
    v15 = L"[AllVolumes]\\";
    if ( v13 )
    {
      while ( *(_WORD *)v14 == *v15 )
      {
        v14 = (wchar_t **)((char *)v14 + 2);
        ++v15;
        if ( !--v13 )
          goto LABEL_18;
      }
LABEL_31:
      if ( !SrmChangeIntoVolumePath((unsigned __int16 *)String1, v49, v53) )
        goto LABEL_43;
      v22 = -1;
      do
        ++v22;
      while ( a1[v22] );
      v23 = v22;
      if ( v54 < v22 )
        v23 = v54;
      v24 = v53;
      if ( v55 >= 8 )
        v24 = (void **)v53[0];
      v25 = a1;
      if ( !v23 )
      {
LABEL_41:
        if ( v54 != v22 )
          goto LABEL_43;
        goto LABEL_42;
      }
      while ( *(_WORD *)v24 == *v25 )
      {
        v24 = (void **)((char *)v24 + 2);
        ++v25;
        if ( !--v23 )
          goto LABEL_41;
      }
      goto LABEL_43;
    }
LABEL_18:
    if ( v12 != 13 )
      goto LABEL_31;
    if ( v47 >= 0xD )
    {
      v16 = (const wchar_t *)String1;
      if ( v48 >= 8 )
        v16 = String1[0];
      if ( !_wcsnicmp(v16, L"[AllVolumes]\\", 0xDu) )
      {
        v17 = SrmIsExclusionPathRecursiveAndRemoveSwitches(String1);
        v18 = v17;
        if ( v47 != 14 || !v17 )
        {
          std::wstring::assign(v49, (void *)L"\\");
          v19 = std::wstring::substr(String1, Block, 13, -1);
          std::wstring::append(v49, v19, 0, -1, v32);
          if ( v58 >= 8 )
            operator delete(Block[0]);
          v58 = 7;
          v57 = 0;
          LOWORD(Block[0]) = 0;
          v52 = v18 ^ 1;
          v21 = v49;
          if ( v51 >= 8 )
            v21 = (void **)v49[0];
          if ( *((_WORD *)v21 + v50 - 1) != 92 )
            std::wstring::append(v49, v20, 92);
LABEL_42:
          std::vector<DirectoryExclusion>::push_back(&v44, v49);
        }
      }
    }
LABEL_43:
    if ( v48 >= 8 )
      operator delete(String1[0]);
    v48 = 7;
    v47 = 0;
    LOWORD(String1[0]) = 0;
    CoTaskMemFree(0);
    v34 = 0;
  }
  v26 = (__int64 *)v44;
  v27 = v35;
  while ( v26 != *((__int64 **)&v44 + 1) )
  {
    if ( (v26[5] & 1) != 0 )
    {
      if ( (unsigned __int64)v26[3] < 8 )
        v28 = v26;
      else
        v28 = (__int64 *)*v26;
      v35 = &v36;
      v36 = L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp";
      v37 = L"SrmGetDirectoryExclusionsForVolume";
      v38 = L"PROTFLSC";
      v39 = 325;
      v40 = 20;
      v41 = 255;
      v43 = 0x1000000;
      memset_0(v42, 0, sizeof(v42));
      CSrmFunctionTracer::Trace(v61, &v36, L"Protected directory: <%s>", v28);
      if ( (unsigned __int64)v26[3] < 8 )
        v29 = v26;
      else
        v29 = (_WORD *)*v26;
      std::wstring::wstring(v59, v29);
      std::vector<std::wstring>::push_back(a4, v59);
      if ( v60 >= 8 )
        operator delete(v59[0]);
      v60 = 7;
      v59[2] = 0;
      LOWORD(v59[0]) = 0;
    }
    else
    {
      if ( (unsigned __int64)v26[3] < 8 )
        v30 = v26;
      else
        v30 = (__int64 *)*v26;
      pv = &v36;
      v36 = L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp";
      v37 = L"SrmGetDirectoryExclusionsForVolume";
      v38 = L"PROTFLSC";
      v39 = 330;
      v40 = 20;
      v41 = 255;
      v43 = 0x1000000;
      memset_0(v42, 0, sizeof(v42));
      CSrmFunctionTracer::Trace(v61, &v36, L"Protected namespace: <%s>", v30);
      if ( (unsigned __int64)v26[3] < 8 )
        v31 = v26;
      else
        v31 = (_WORD *)*v26;
      std::wstring::wstring(Block, v31);
      std::vector<std::wstring>::push_back(v27, Block);
      if ( v58 >= 8 )
        operator delete(Block[0]);
      v58 = 7;
      v57 = 0;
      LOWORD(Block[0]) = 0;
    }
    v26 += 6;
  }
  std::vector<DirectoryExclusion>::~vector<DirectoryExclusion>((__int64)&v44);
  if ( v55 >= 8 )
    operator delete(v53[0]);
  v55 = 7;
  v54 = 0;
  LOWORD(v53[0]) = 0;
  if ( v51 >= 8 )
    operator delete(v49[0]);
  v51 = 7;
  v50 = 0;
  LOWORD(v49[0]) = 0;
  v61[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v61);
}

```

## disassembly

```asm
0x1800a46cc  mov     [rsp-8+arg_8], rbx
0x1800a46d1  push    rbp
0x1800a46d2  push    rsi
0x1800a46d3  push    rdi
0x1800a46d4  push    r12
0x1800a46d6  push    r13
0x1800a46d8  push    r14
0x1800a46da  push    r15
0x1800a46dc  lea     rbp, [rsp-190h]
0x1800a46e4  sub     rsp, 290h
0x1800a46eb  mov     rax, cs:__security_cookie
0x1800a46f2  xor     rax, rsp
0x1800a46f5  mov     [rbp+1C0h+var_40], rax
0x1800a46fc  mov     r12, r9
0x1800a46ff  mov     [rsp+2C0h+var_280], r8
0x1800a4704  mov     r14, rdx
0x1800a4707  mov     rsi, rcx
0x1800a470a  lea     rax, [rsp+2C0h+var_278]
0x1800a470f  mov     [rsp+2C0h+pv], rax
0x1800a4714  lea     rax, aBaseFsFsrmUtil_7; "base\\fs\\fsrm\\utilities\\scanner\\pro"...
0x1800a471b  mov     [rsp+2C0h+var_278], rax
0x1800a4720  lea     rax, aSrmgetdirector; "SrmGetDirectoryExclusionsForVolume"
0x1800a4727  mov     [rsp+2C0h+var_270], rax
0x1800a472c  lea     rax, aProtflsc; "PROTFLSC"
0x1800a4733  mov     [rsp+2C0h+var_268], rax
0x1800a4738  mov     [rsp+2C0h+var_260], 10Fh
0x1800a4740  mov     [rsp+2C0h+var_25C], 14h
0x1800a4748  mov     [rsp+2C0h+var_258], 0FFh
0x1800a4750  xor     r13d, r13d
0x1800a4753  mov     [rbp+1C0h+var_1F0], 1000000h
0x1800a475a  xor     edx, edx; Val
0x1800a475c  lea     r8d, [r13+60h]; Size
0x1800a4760  lea     rcx, [rsp+2C0h+var_250]; void *
0x1800a4765  call    memset_0
0x1800a476a  nop
0x1800a476b  xor     r8d, r8d
0x1800a476e  lea     rdx, [rsp+2C0h+var_278]
0x1800a4773  lea     rcx, [rbp+1C0h+var_F0]
0x1800a477a  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a477f  nop
0x1800a4780  mov     [rsp+2C0h+var_2A0], rsi
0x1800a4785  lea     r9, aInputVolumeNam; "Input volume name is %s"
0x1800a478c  mov     edx, 8Ch; unsigned int
0x1800a4791  mov     r8d, 111h; unsigned int
0x1800a4797  lea     rcx, [rbp+1C0h+var_F0]; this
0x1800a479e  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x1800a47a3  lea     edi, [r13+7]
0x1800a47a7  mov     [rbp+1C0h+var_188], rdi
0x1800a47ab  mov     [rbp+1C0h+var_190], r13
0x1800a47af  mov     word ptr [rbp+1C0h+var_1A0], r13w
0x1800a47b4  mov     [rbp+1C0h+var_158], rdi
0x1800a47b8  mov     [rbp+1C0h+var_160], r13
0x1800a47bc  mov     word ptr [rbp+1C0h+var_170], r13w
0x1800a47c1  xorps   xmm0, xmm0
0x1800a47c4  movdqu  [rbp+1C0h+var_1E8], xmm0
0x1800a47c9  mov     [rbp+1C0h+var_1D8], r13
0x1800a47cd  mov     rbx, [r14]
0x1800a47d0  lea     r15d, [r13+5Ch]
0x1800a47d4  cmp     rbx, [r14+8]
0x1800a47d8  jz      loc_1800A4A36
0x1800a47de  mov     [rsp+2C0h+var_288], r13
0x1800a47e3  mov     rdx, rbx
0x1800a47e6  lea     rcx, [rbp+1C0h+String1]
0x1800a47ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a47ef  nop
0x1800a47f0  mov     [rsp+2C0h+pv], r13
0x1800a47f5  lea     rdx, [rbp+1C0h+String1]
0x1800a47f9  cmp     [rbp+1C0h+var_1B0], 8
0x1800a47fe  cmovnb  rdx, [rbp+1C0h+String1]; lpSrc
0x1800a4803  lea     rcx, [rsp+2C0h+pv]; this
0x1800a4808  call    ?ExpandEnvironmentStringsW@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::ExpandEnvironmentStringsW(ushort const *)
0x1800a480d  mov     rdi, [rsp+2C0h+pv]
0x1800a4812  test    rdi, rdi
0x1800a4815  jnz     short loc_1800A481B
0x1800a4817  xor     ecx, ecx
0x1800a4819  jmp     short loc_1800A4839
0x1800a481b  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a481f  inc     r8
0x1800a4822  cmp     [rdi+r8*2], r13w
0x1800a4827  jnz     short loc_1800A481F
0x1800a4829  mov     rdx, rdi; Src
0x1800a482c  lea     rcx, [rbp+1C0h+String1]; void *
0x1800a4830  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800a4835  nop
0x1800a4836  mov     rcx, rdi; pv
0x1800a4839  call    cs:__imp_CoTaskMemFree
0x1800a483f  mov     [rsp+2C0h+pv], r13
0x1800a4844  mov     [rsp+2C0h+pv], r13
0x1800a4849  mov     r11d, 0Dh
0x1800a484f  mov     ecx, r11d
0x1800a4852  mov     r9, [rbp+1C0h+var_1B8]
0x1800a4856  cmp     r9, r11
0x1800a4859  jnb     short loc_1800A4863
0x1800a485b  mov     rcx, r9
0x1800a485e  mov     r8, rcx
0x1800a4861  jmp     short loc_1800A4866
0x1800a4863  mov     r8, r11
0x1800a4866  lea     rdx, [rbp+1C0h+String1]
0x1800a486a  cmp     [rbp+1C0h+var_1B0], 8
0x1800a486f  cmovnb  rdx, [rbp+1C0h+String1]
0x1800a4874  lea     r10, aAllvolumes; "[AllVolumes]\\"
0x1800a487b  test    r8, r8
0x1800a487e  jz      short loc_1800A489B
0x1800a4880  movzx   eax, word ptr [r10]
0x1800a4884  cmp     [rdx], ax
0x1800a4887  jnz     loc_1800A4988
0x1800a488d  add     rdx, 2
0x1800a4891  add     r10, 2
0x1800a4895  sub     r8, 1
0x1800a4899  jnz     short loc_1800A4880
0x1800a489b  cmp     rcx, r11
0x1800a489e  jnz     loc_1800A4988
0x1800a48a4  cmp     r9, r11
0x1800a48a7  jb      loc_1800A49F9
0x1800a48ad  lea     rcx, [rbp+1C0h+String1]
0x1800a48b1  cmp     [rbp+1C0h+var_1B0], 8
0x1800a48b6  cmovnb  rcx, [rbp+1C0h+String1]; String1
0x1800a48bb  mov     r8, r11; MaxCount
0x1800a48be  lea     rdx, aAllvolumes; "[AllVolumes]\\"
0x1800a48c5  call    cs:__imp__wcsnicmp
0x1800a48cb  test    eax, eax
0x1800a48cd  jnz     loc_1800A49F9
0x1800a48d3  lea     rcx, [rbp+1C0h+String1]
0x1800a48d7  call    ?SrmIsExclusionPathRecursiveAndRemoveSwitches@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmIsExclusionPathRecursiveAndRemoveSwitches(std::wstring &)
0x1800a48dc  movzx   edi, al
0x1800a48df  cmp     [rbp+1C0h+var_1B8], 0Eh
0x1800a48e4  jnz     short loc_1800A48EE
0x1800a48e6  test    al, al
0x1800a48e8  jnz     loc_1800A49F9
0x1800a48ee  mov     r8d, 1
0x1800a48f4  lea     rdx, psz; "\\"
0x1800a48fb  lea     rcx, [rbp+1C0h+var_1A0]; void *
0x1800a48ff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800a4904  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a4908  lea     r8d, [r9+0Eh]
0x1800a490c  lea     rdx, [rbp+1C0h+Block]
0x1800a4910  lea     rcx, [rbp+1C0h+String1]
0x1800a4914  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800a4919  nop
0x1800a491a  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800a491e  xor     r8d, r8d
0x1800a4921  mov     rdx, rax
0x1800a4924  lea     rcx, [rbp+1C0h+var_1A0]
0x1800a4928  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800a492d  nop
0x1800a492e  cmp     [rbp+1C0h+var_130], 8
0x1800a4936  jb      short loc_1800A4941
0x1800a4938  mov     rcx, [rbp+1C0h+Block]; Block
0x1800a493c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a4941  mov     [rbp+1C0h+var_130], 7
0x1800a494c  mov     [rbp+1C0h+var_138], r13
0x1800a4953  mov     word ptr [rbp+1C0h+Block], r13w
0x1800a4958  mov     eax, edi
0x1800a495a  xor     eax, 1
0x1800a495d  mov     [rbp+1C0h+var_178], eax
0x1800a4960  lea     rcx, [rbp+1C0h+var_1A0]
0x1800a4964  cmp     [rbp+1C0h+var_188], 8
0x1800a4969  cmovnb  rcx, [rbp+1C0h+var_1A0]
0x1800a496e  mov     rax, [rbp+1C0h+var_190]
0x1800a4972  cmp     [rcx+rax*2-2], r15w
0x1800a4978  jz      short loc_1800A49EB
0x1800a497a  mov     r8d, r15d
0x1800a497d  lea     rcx, [rbp+1C0h+var_1A0]
0x1800a4981  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800a4986  jmp     short loc_1800A49EB
0x1800a4988  lea     r8, [rbp+1C0h+var_170]; void *
0x1800a498c  lea     rdx, [rbp+1C0h+var_1A0]; void *
0x1800a4990  lea     rcx, [rbp+1C0h+String1]; unsigned __int16 *
0x1800a4994  call    ?SrmChangeIntoVolumePath@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUDirectoryExclusion@@0@Z; SrmChangeIntoVolumePath(std::wstring &,DirectoryExclusion &,std::wstring &)
0x1800a4999  test    al, al
0x1800a499b  jz      short loc_1800A49F9
0x1800a499d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a49a1  inc     rcx
0x1800a49a4  cmp     [rsi+rcx*2], r13w
0x1800a49a9  jnz     short loc_1800A49A1
0x1800a49ab  mov     r9, [rbp+1C0h+var_160]
0x1800a49af  mov     r8, rcx
0x1800a49b2  cmp     r9, rcx
0x1800a49b5  cmovb   r8, r9
0x1800a49b9  lea     rdx, [rbp+1C0h+var_170]
0x1800a49bd  cmp     [rbp+1C0h+var_158], 8
0x1800a49c2  cmovnb  rdx, [rbp+1C0h+var_170]
0x1800a49c7  mov     r10, rsi
0x1800a49ca  test    r8, r8
0x1800a49cd  jz      short loc_1800A49E6
0x1800a49cf  movzx   eax, word ptr [r10]
0x1800a49d3  cmp     [rdx], ax
0x1800a49d6  jnz     short loc_1800A49F9
0x1800a49d8  add     rdx, 2
0x1800a49dc  add     r10, 2
0x1800a49e0  sub     r8, 1
0x1800a49e4  jnz     short loc_1800A49CF
0x1800a49e6  cmp     r9, rcx
0x1800a49e9  jnz     short loc_1800A49F9
0x1800a49eb  lea     rdx, [rbp+1C0h+var_1A0]
0x1800a49ef  lea     rcx, [rbp+1C0h+var_1E8]
0x1800a49f3  call    ?push_back@?$vector@UDirectoryExclusion@@V?$allocator@UDirectoryExclusion@@@std@@@std@@QEAAXAEBUDirectoryExclusion@@@Z; std::vector<DirectoryExclusion>::push_back(DirectoryExclusion const &)
0x1800a49f8  nop
0x1800a49f9  cmp     [rbp+1C0h+var_1B0], 8
0x1800a49fe  jb      short loc_1800A4A09
0x1800a4a00  mov     rcx, [rbp+1C0h+String1]; Block
0x1800a4a04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a4a09  mov     edi, 7
0x1800a4a0e  mov     [rbp+1C0h+var_1B0], rdi
0x1800a4a12  mov     [rbp+1C0h+var_1B8], r13
0x1800a4a16  mov     word ptr [rbp+1C0h+String1], r13w
0x1800a4a1b  xor     ecx, ecx; pv
0x1800a4a1d  call    cs:__imp_CoTaskMemFree
0x1800a4a23  mov     [rsp+2C0h+var_288], r13
0x1800a4a28  mov     [rsp+2C0h+var_288], r13
0x1800a4a2d  add     rbx, 28h ; '('
0x1800a4a31  jmp     loc_1800A47D4
0x1800a4a36  mov     rbx, qword ptr [rbp+1C0h+var_1E8]
0x1800a4a3a  mov     r15, [rsp+2C0h+var_280]
0x1800a4a3f  lea     rsi, aBaseFsFsrmUtil_7; "base\\fs\\fsrm\\utilities\\scanner\\pro"...
0x1800a4a46  lea     r14, aSrmgetdirector; "SrmGetDirectoryExclusionsForVolume"
0x1800a4a4d  cmp     rbx, qword ptr [rbp+1C0h+var_1E8+8]
0x1800a4a51  jz      loc_1800A4C11
0x1800a4a57  test    byte ptr [rbx+28h], 1
0x1800a4a5b  jz      loc_1800A4B3D
0x1800a4a61  cmp     qword ptr [rbx+18h], 8
0x1800a4a66  jb      short loc_1800A4A6D
0x1800a4a68  mov     rdi, [rbx]
0x1800a4a6b  jmp     short loc_1800A4A70
0x1800a4a6d  mov     rdi, rbx
0x1800a4a70  lea     rax, [rsp+2C0h+var_278]
0x1800a4a75  mov     [rsp+2C0h+var_280], rax
0x1800a4a7a  mov     [rsp+2C0h+var_278], rsi
0x1800a4a7f  mov     [rsp+2C0h+var_270], r14
0x1800a4a84  lea     rax, aProtflsc; "PROTFLSC"
0x1800a4a8b  mov     [rsp+2C0h+var_268], rax
0x1800a4a90  mov     [rsp+2C0h+var_260], 145h
0x1800a4a98  mov     [rsp+2C0h+var_25C], 14h
0x1800a4aa0  mov     [rsp+2C0h+var_258], 0FFh
0x1800a4aa8  mov     [rbp+1C0h+var_1F0], 1000000h
0x1800a4aaf  xor     edx, edx; Val
0x1800a4ab1  lea     r8d, [rdx+60h]; Size
0x1800a4ab5  lea     rcx, [rsp+2C0h+var_250]; void *
0x1800a4aba  call    memset_0
0x1800a4abf  nop
0x1800a4ac0  mov     r9, rdi
0x1800a4ac3  lea     r8, aProtectedDirec; "Protected directory: <%s>"
0x1800a4aca  lea     rdx, [rsp+2C0h+var_278]
0x1800a4acf  lea     rcx, [rbp+1C0h+var_F0]
0x1800a4ad6  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800a4adb  cmp     qword ptr [rbx+18h], 8
0x1800a4ae0  jb      short loc_1800A4AE7
0x1800a4ae2  mov     rdx, [rbx]
0x1800a4ae5  jmp     short loc_1800A4AEA
0x1800a4ae7  mov     rdx, rbx
0x1800a4aea  lea     rcx, [rbp+1C0h+var_120]; void *
0x1800a4af1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800a4af6  nop
0x1800a4af7  lea     rdx, [rbp+1C0h+var_120]
0x1800a4afe  mov     rcx, r12
0x1800a4b01  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800a4b06  nop
0x1800a4b07  cmp     [rbp+1C0h+var_108], 8
0x1800a4b0f  jb      short loc_1800A4B1D
0x1800a4b11  mov     rcx, [rbp+1C0h+var_120]; Block
0x1800a4b18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a4b1d  mov     edi, 7
0x1800a4b22  mov     [rbp+1C0h+var_108], rdi
0x1800a4b29  mov     [rbp+1C0h+var_110], r13
0x1800a4b30  mov     word ptr [rbp+1C0h+var_120], r13w
0x1800a4b38  jmp     loc_1800A4C08
0x1800a4b3d  cmp     qword ptr [rbx+18h], 8
0x1800a4b42  jb      short loc_1800A4B49
0x1800a4b44  mov     rdi, [rbx]
0x1800a4b47  jmp     short loc_1800A4B4C
0x1800a4b49  mov     rdi, rbx
0x1800a4b4c  lea     rax, [rsp+2C0h+var_278]
0x1800a4b51  mov     [rsp+2C0h+pv], rax
0x1800a4b56  mov     [rsp+2C0h+var_278], rsi
0x1800a4b5b  mov     [rsp+2C0h+var_270], r14
0x1800a4b60  lea     rax, aProtflsc; "PROTFLSC"
0x1800a4b67  mov     [rsp+2C0h+var_268], rax
0x1800a4b6c  mov     [rsp+2C0h+var_260], 14Ah
0x1800a4b74  mov     [rsp+2C0h+var_25C], 14h
0x1800a4b7c  mov     [rsp+2C0h+var_258], 0FFh
0x1800a4b84  mov     [rbp+1C0h+var_1F0], 1000000h
0x1800a4b8b  xor     edx, edx; Val
0x1800a4b8d  lea     r8d, [rdx+60h]; Size
0x1800a4b91  lea     rcx, [rsp+2C0h+var_250]; void *
0x1800a4b96  call    memset_0
0x1800a4b9b  nop
0x1800a4b9c  mov     r9, rdi
0x1800a4b9f  lea     r8, aProtectedNames; "Protected namespace: <%s>"
0x1800a4ba6  lea     rdx, [rsp+2C0h+var_278]
0x1800a4bab  lea     rcx, [rbp+1C0h+var_F0]
0x1800a4bb2  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x1800a4bb7  cmp     qword ptr [rbx+18h], 8
0x1800a4bbc  jb      short loc_1800A4BC3
0x1800a4bbe  mov     rdx, [rbx]
0x1800a4bc1  jmp     short loc_1800A4BC6
0x1800a4bc3  mov     rdx, rbx
0x1800a4bc6  lea     rcx, [rbp+1C0h+Block]; void *
0x1800a4bca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800a4bcf  nop
0x1800a4bd0  lea     rdx, [rbp+1C0h+Block]
  ... truncated ...
```
