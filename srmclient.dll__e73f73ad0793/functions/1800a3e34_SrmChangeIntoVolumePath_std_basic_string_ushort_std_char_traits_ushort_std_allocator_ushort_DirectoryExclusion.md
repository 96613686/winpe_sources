# SrmChangeIntoVolumePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,DirectoryExclusion &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800a3e34`
- end: `0x1800a42c8`
- name: `?SrmChangeIntoVolumePath@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUDirectoryExclusion@@0@Z`
- size: `1172`
- prototype: `__int64 __fastcall(unsigned __int16 *, void *, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a46cc`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x180010bc4`
- `0x1800208e8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x18007cfe0`
- `0x1800a3e34`
- `0x1800a4ca0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!iswalpha` at `0x1800a3fe1`
- `msvcrt!iswalpha` at `0x1800a3fe1`
- `ole32!CoTaskMemFree` at `0x1800a4030`
- `ole32!CoTaskMemFree` at `0x1800a4042`
- `ole32!CoTaskMemFree` at `0x1800a40d3`
- `ole32!CoTaskMemFree` at `0x1800a40e8`
- `ole32!CoTaskMemFree` at `0x1800a41d2`
- `ole32!CoTaskMemFree` at `0x1800a41e5`
- `ole32!CoTaskMemFree` at `0x1800a4213`
- `ole32!CoTaskMemFree` at `0x1800a4226`
- `ole32!CoTaskMemFree` at `0x1800a4030`
- `ole32!CoTaskMemFree` at `0x1800a4042`
- `ole32!CoTaskMemFree` at `0x1800a40d3`
- `ole32!CoTaskMemFree` at `0x1800a40e8`
- `ole32!CoTaskMemFree` at `0x1800a41d2`
- `ole32!CoTaskMemFree` at `0x1800a41e5`
- `ole32!CoTaskMemFree` at `0x1800a4213`
- `ole32!CoTaskMemFree` at `0x1800a4226`

## string_xrefs

- `0x1800a3f45`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x1800a3f63`: `SRMPATHC`
- `0x1800a3f54`: `IsAbsolutePath`
- `0x1800a3e94`: `SrmChangeIntoVolumePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall SrmChangeIntoVolumePath(unsigned __int16 *a1, _DWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // r13
  _DWORD *v4; // r15
  unsigned __int16 *v6; // rbx
  char v7; // bl
  int CanonicalPath; // eax
  char *v9; // rbx
  __int64 v10; // r12
  unsigned __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  _WORD *v15; // rdx
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  int Hr; // eax
  char v20; // al
  unsigned __int8 v21; // [rsp+40h] [rbp-298h]
  LPVOID pv; // [rsp+48h] [rbp-290h] BYREF
  LPVOID v23; // [rsp+50h] [rbp-288h] BYREF
  _DWORD *v24; // [rsp+58h] [rbp-280h]
  _QWORD *v25; // [rsp+60h] [rbp-278h]
  int pExceptionObject; // [rsp+68h] [rbp-270h] BYREF
  int v27; // [rsp+6Ch] [rbp-26Ch] BYREF
  _QWORD *v28; // [rsp+70h] [rbp-268h]
  _QWORD *v29; // [rsp+78h] [rbp-260h]
  const unsigned __int16 **v30; // [rsp+80h] [rbp-258h]
  const unsigned __int16 *v31; // [rsp+88h] [rbp-250h] BYREF
  const wchar_t *v32; // [rsp+90h] [rbp-248h]
  const unsigned __int16 *v33; // [rsp+98h] [rbp-240h]
  __int64 v34; // [rsp+A0h] [rbp-238h]
  int v35; // [rsp+A8h] [rbp-230h]
  _BYTE v36[96]; // [rsp+B0h] [rbp-228h] BYREF
  int v37; // [rsp+110h] [rbp-1C8h]
  _com_error *v38; // [rsp+118h] [rbp-1C0h] BYREF
  const exception *v39; // [rsp+120h] [rbp-1B8h] BYREF
  void **v40; // [rsp+130h] [rbp-1A8h] BYREF
  int v41; // [rsp+138h] [rbp-1A0h]
  unsigned int v42; // [rsp+15Ch] [rbp-17Ch]
  _QWORD v43[22]; // [rsp+1E0h] [rbp-F8h] BYREF

  v3 = a3;
  v4 = a2;
  v29 = a2;
  v28 = a3;
  v24 = a2;
  v25 = a3;
  v30 = &v31;
  v31 = L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp";
  v32 = L"SrmChangeIntoVolumePath";
  v33 = L"PROTFLSC";
  v34 = 0x14000000CCLL;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v40, (const struct CSrmDebugInfo *)&v31, 0);
  v23 = 0;
  pv = 0;
  v21 = SrmIsExclusionPathRecursiveAndRemoveSwitches(a1);
  if ( *((_QWORD *)a1 + 3) < 8u )
    v6 = a1;
  else
    v6 = *(unsigned __int16 **)a1;
  v30 = &v31;
  v31 = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v32 = L"IsAbsolutePath";
  v33 = L"SRMPATHC";
  v34 = 116;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v43, (const struct CSrmDebugInfo *)&v31, 0);
  if ( v6 && (*v6 == 92 && v6[1] == 92 && v6[2] == 63 && v6[3] == 92 || iswalpha(*v6) && v6[1] == 58 && v6[2] == 92) )
  {
    v43[0] = &CSrmFunctionTracer::`vftable';
    v7 = 1;
  }
  else
  {
    v43[0] = &CSrmFunctionTracer::`vftable';
    v7 = 0;
  }
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v43);
  if ( !v7 )
  {
    CoTaskMemFree(0);
    pv = 0;
    CoTaskMemFree(0);
    v23 = 0;
    v40 = &CSrmFunctionTracer::`vftable';
LABEL_44:
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v40);
    return 0;
  }
  try
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(unsigned __int16 **)a1;
    CanonicalPath = SrmGetCanonicalPath(a1, (struct CSrmAutoPWSZ *)&v23, (unsigned __int16 **)&pv);
    v41 = CanonicalPath;
    if ( CanonicalPath < 0 )
    {
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v40, Hr);
      v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v40, 0xE1u, v20, 0);
    }
    v41 = CanonicalPath;
  }
  catch ( long v27 )
  {
    CSrmFunctionTracer::HandleHresultException(
      (CSrmFunctionTracer *)&v40,
      v27,
      L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp",
      L"PROTFLSC",
      L"SrmChangeIntoVolumePath",
      0xE3u,
      v42);
    v3 = v25;
    v4 = v24;
  }
  catch ( _com_error *v38 )
  {
    CSrmFunctionTracer::HandleComException(
      (CSrmFunctionTracer *)&v40,
      v38,
      L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp",
      L"PROTFLSC",
      L"SrmChangeIntoVolumePath",
      0xE3u,
      v42);
  }
  catch ( std::bad_alloc )
  {
    CSrmFunctionTracer::HandleStdBadAllocException(
      (CSrmFunctionTracer *)&v40,
      L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp",
      L"PROTFLSC",
      L"SrmChangeIntoVolumePath",
      0xE3u,
      v42);
    v3 = v25;
    v4 = v24;
  }
  catch ( const exception *v39 )
  {
    CSrmFunctionTracer::HandleStdGenericException(
      (CSrmFunctionTracer *)&v40,
      v39,
      L"base\\fs\\fsrm\\utilities\\scanner\\protecteddirectories.cpp",
      L"PROTFLSC",
      L"SrmChangeIntoVolumePath",
      0xE3u,
      v42);
  }
  if ( v41 < 0 )
  {
    if ( v41 == -2147024882 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v23);
    v23 = 0;
    v40 = &CSrmFunctionTracer::`vftable';
    goto LABEL_44;
  }
  v9 = (char *)v23;
  if ( !v23 )
    goto LABEL_43;
  if ( !*(_WORD *)v23 )
    goto LABEL_43;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)v23 + v11) );
  if ( v11 < 0x31 )
  {
LABEL_43:
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v9);
    v23 = 0;
    v40 = &CSrmFunctionTracer::`vftable';
    goto LABEL_44;
  }
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)pv + v12) );
  std::wstring::assign(v3, pv);
  if ( v3[3] < 8u )
    v14 = v3;
  else
    v14 = (_QWORD *)*v28;
  if ( *((_WORD *)v14 + v3[2] - 1) != 92 )
    std::wstring::append(v3, v13, 92);
  v4[10] = v21 ^ 1;
  v15 = v9 + 96;
  do
    ++v10;
  while ( v15[v10] );
  std::wstring::assign(v4, v15);
  if ( *((_QWORD *)v4 + 3) < 8u )
    v17 = v4;
  else
    v17 = (_DWORD *)*v29;
  if ( *((_WORD *)v17 + *((_QWORD *)v4 + 2) - 1) != 92 )
    std::wstring::append(v4, v16, 92);
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v9);
  v23 = 0;
  v40 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v40);
  return 1;
}

```

## disassembly

```asm
0x1800a3e34  mov     r11, rsp
0x1800a3e37  push    rbx
0x1800a3e38  push    rsi
0x1800a3e39  push    rdi
0x1800a3e3a  push    r12
0x1800a3e3c  push    r13
0x1800a3e3e  push    r14
0x1800a3e40  push    r15
0x1800a3e42  sub     rsp, 2A0h
0x1800a3e49  mov     rax, cs:__security_cookie
0x1800a3e50  xor     rax, rsp
0x1800a3e53  mov     [rsp+2D8h+var_48], rax
0x1800a3e5b  mov     r13, r8
0x1800a3e5e  mov     r15, rdx
0x1800a3e61  mov     r12, rcx
0x1800a3e64  mov     [rsp+2D8h+var_260], rdx
0x1800a3e69  mov     [rsp+2D8h+var_268], r8
0x1800a3e6e  mov     [rsp+2D8h+var_280], rdx
0x1800a3e73  mov     [rsp+2D8h+var_278], r8
0x1800a3e78  lea     rax, [r11-250h]
0x1800a3e7f  mov     [r11-258h], rax
0x1800a3e86  lea     rax, aBaseFsFsrmUtil_7; "base\\fs\\fsrm\\utilities\\scanner\\pro"...
0x1800a3e8d  mov     [r11-250h], rax
0x1800a3e94  lea     rax, aSrmchangeintov; "SrmChangeIntoVolumePath"
0x1800a3e9b  mov     [r11-248h], rax
0x1800a3ea2  lea     rax, aProtflsc; "PROTFLSC"
0x1800a3ea9  mov     [r11-240h], rax
0x1800a3eb0  mov     dword ptr [rsp+2D8h+var_238], 0CCh
0x1800a3ebb  mov     dword ptr [rsp+2D8h+var_238+4], 14h
0x1800a3ec6  mov     esi, 0FFh
0x1800a3ecb  mov     [rsp+2D8h+var_230], esi
0x1800a3ed2  xor     edi, edi
0x1800a3ed4  mov     [rsp+2D8h+var_1C8], 1000000h
0x1800a3edf  lea     r14d, [rdi+60h]
0x1800a3ee3  mov     r8d, r14d; Size
0x1800a3ee6  xor     edx, edx; Val
0x1800a3ee8  lea     rcx, [r11-228h]; void *
0x1800a3eef  call    memset_0
0x1800a3ef4  nop
0x1800a3ef5  xor     r8d, r8d
0x1800a3ef8  lea     rdx, [rsp+2D8h+var_250]
0x1800a3f00  lea     rcx, [rsp+2D8h+var_1A8]
0x1800a3f08  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a3f0d  nop
0x1800a3f0e  mov     [rsp+2D8h+var_288], rdi
0x1800a3f13  mov     [rsp+2D8h+pv], rdi
0x1800a3f18  mov     rcx, r12
0x1800a3f1b  call    ?SrmIsExclusionPathRecursiveAndRemoveSwitches@@YA_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmIsExclusionPathRecursiveAndRemoveSwitches(std::wstring &)
0x1800a3f20  mov     [rsp+2D8h+var_298], al
0x1800a3f24  cmp     qword ptr [r12+18h], 8
0x1800a3f2a  jb      short loc_1800A3F32
0x1800a3f2c  mov     rbx, [r12]
0x1800a3f30  jmp     short loc_1800A3F35
0x1800a3f32  mov     rbx, r12
0x1800a3f35  lea     rax, [rsp+2D8h+var_250]
0x1800a3f3d  mov     [rsp+2D8h+var_258], rax
0x1800a3f45  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x1800a3f4c  mov     [rsp+2D8h+var_250], rax
0x1800a3f54  lea     rax, aIsabsolutepath; "IsAbsolutePath"
0x1800a3f5b  mov     [rsp+2D8h+var_248], rax
0x1800a3f63  lea     rax, aSrmpathc; "SRMPATHC"
0x1800a3f6a  mov     [rsp+2D8h+var_240], rax
0x1800a3f72  mov     [rsp+2D8h+var_238], 74h ; 't'
0x1800a3f7e  mov     [rsp+2D8h+var_230], esi
0x1800a3f85  mov     [rsp+2D8h+var_1C8], 1000000h
0x1800a3f90  mov     r8, r14; Size
0x1800a3f93  xor     edx, edx; Val
0x1800a3f95  lea     rcx, [rsp+2D8h+var_228]; void *
0x1800a3f9d  call    memset_0
0x1800a3fa2  nop
0x1800a3fa3  xor     r8d, r8d
0x1800a3fa6  lea     rdx, [rsp+2D8h+var_250]
0x1800a3fae  lea     rcx, [rsp+2D8h+var_F8]
0x1800a3fb6  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x1800a3fbb  nop
0x1800a3fbc  mov     esi, 5Ch ; '\'
0x1800a3fc1  test    rbx, rbx
0x1800a3fc4  jz      short loc_1800A400B
0x1800a3fc6  cmp     [rbx], si
0x1800a3fc9  jnz     short loc_1800A3FDE
0x1800a3fcb  cmp     [rbx+2], si
0x1800a3fcf  jnz     short loc_1800A3FDE
0x1800a3fd1  cmp     word ptr [rbx+4], 3Fh ; '?'
0x1800a3fd6  jnz     short loc_1800A3FDE
0x1800a3fd8  cmp     [rbx+6], si
0x1800a3fdc  jz      short loc_1800A3FF8
0x1800a3fde  movzx   ecx, word ptr [rbx]; C
0x1800a3fe1  call    cs:__imp_iswalpha
0x1800a3fe7  test    eax, eax
0x1800a3fe9  jz      short loc_1800A400B
0x1800a3feb  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800a3ff0  jnz     short loc_1800A400B
0x1800a3ff2  cmp     [rbx+4], si
0x1800a3ff6  jnz     short loc_1800A400B
0x1800a3ff8  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a3fff  mov     [rsp+2D8h+var_F8], r14
0x1800a4007  mov     bl, 1
0x1800a4009  jmp     short loc_1800A401D
0x1800a400b  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a4012  mov     [rsp+2D8h+var_F8], r14
0x1800a401a  mov     bl, dil
0x1800a401d  lea     rcx, [rsp+2D8h+var_F8]; this
0x1800a4025  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a402a  test    bl, bl
0x1800a402c  jnz     short loc_1800A405F
0x1800a402e  xor     ecx, ecx; pv
0x1800a4030  call    cs:__imp_CoTaskMemFree
0x1800a4036  mov     [rsp+2D8h+pv], rdi
0x1800a403b  mov     [rsp+2D8h+pv], rdi
0x1800a4040  xor     ecx, ecx; pv
0x1800a4042  call    cs:__imp_CoTaskMemFree
0x1800a4048  mov     [rsp+2D8h+var_288], rdi
0x1800a404d  mov     [rsp+2D8h+var_288], rdi
0x1800a4052  mov     [rsp+2D8h+var_1A8], r14
0x1800a405a  jmp     loc_1800A423E
0x1800a405f  cmp     qword ptr [r12+18h], 8
0x1800a4065  jb      short loc_1800A406B
0x1800a4067  mov     r12, [r12]
0x1800a406b  lea     r8, [rsp+2D8h+pv]; unsigned __int16 **
0x1800a4070  lea     rdx, [rsp+2D8h+var_288]; struct CSrmAutoPWSZ *
0x1800a4075  mov     rcx, r12; unsigned __int16 *
0x1800a4078  call    ?SrmGetCanonicalPath@@YAJPEBGAEAVCSrmAutoPWSZ@@PEAPEAG@Z; SrmGetCanonicalPath(ushort const *,CSrmAutoPWSZ &,ushort * *)
0x1800a407d  mov     [rsp+2D8h+var_1A0], eax
0x1800a4084  test    eax, eax
0x1800a4086  js      loc_1800A4270
0x1800a408c  mov     [rsp+2D8h+var_1A0], eax
0x1800a4093  jmp     short loc_1800A40AD
0x1800a4095  mov     r13, [rsp+2D8h+var_278]
0x1800a409a  mov     r15, [rsp+2D8h+var_280]
0x1800a409f  lea     r14, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800a40a6  mov     esi, 5Ch ; '\'
0x1800a40ab  xor     edi, edi
0x1800a40ad  cmp     [rsp+2D8h+var_1A0], edi
0x1800a40b4  jge     short loc_1800A4105
0x1800a40b6  mov     eax, 8007000Eh
0x1800a40bb  cmp     [rsp+2D8h+var_1A0], eax
0x1800a40c2  jz      loc_1800A42B2
0x1800a40c8  jmp     short loc_1800A40CE
0x1800a40ca  jmp     short loc_1800A4095
0x1800a40cc  jmp     short loc_1800A4095
0x1800a40ce  mov     rcx, [rsp+2D8h+pv]; pv
0x1800a40d3  call    cs:__imp_CoTaskMemFree
0x1800a40d9  mov     [rsp+2D8h+pv], rdi
0x1800a40de  mov     [rsp+2D8h+pv], rdi
0x1800a40e3  mov     rcx, [rsp+2D8h+var_288]; pv
0x1800a40e8  call    cs:__imp_CoTaskMemFree
0x1800a40ee  mov     [rsp+2D8h+var_288], rdi
0x1800a40f3  mov     [rsp+2D8h+var_288], rdi
0x1800a40f8  mov     [rsp+2D8h+var_1A8], r14
0x1800a4100  jmp     loc_1800A423E
0x1800a4105  mov     rbx, [rsp+2D8h+var_288]
0x1800a410a  test    rbx, rbx
0x1800a410d  jz      loc_1800A420E
0x1800a4113  cmp     [rbx], di
0x1800a4116  jz      loc_1800A420E
0x1800a411c  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a4120  mov     rax, r12
0x1800a4123  inc     rax
0x1800a4126  cmp     [rbx+rax*2], di
0x1800a412a  jnz     short loc_1800A4123
0x1800a412c  cmp     rax, 31h ; '1'
0x1800a4130  jb      loc_1800A420E
0x1800a4136  mov     r8, r12
0x1800a4139  mov     rax, [rsp+2D8h+pv]
0x1800a413e  inc     r8
0x1800a4141  cmp     [rax+r8*2], di
0x1800a4146  jnz     short loc_1800A413E
0x1800a4148  mov     rdx, rax; Src
0x1800a414b  mov     rcx, r13; void *
0x1800a414e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800a4153  cmp     qword ptr [r13+18h], 8
0x1800a4158  jb      short loc_1800A4164
0x1800a415a  mov     rax, [rsp+2D8h+var_268]
0x1800a415f  mov     rcx, [rax]
0x1800a4162  jmp     short loc_1800A4167
0x1800a4164  mov     rcx, r13
0x1800a4167  mov     rax, [r13+10h]
0x1800a416b  cmp     [rcx+rax*2-2], si
0x1800a4170  jz      short loc_1800A417D
0x1800a4172  mov     r8d, esi
0x1800a4175  mov     rcx, r13
0x1800a4178  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800a417d  movzx   eax, [rsp+2D8h+var_298]
0x1800a4182  xor     eax, 1
0x1800a4185  mov     [r15+28h], eax
0x1800a4189  lea     rdx, [rbx+60h]; Src
0x1800a418d  inc     r12
0x1800a4190  cmp     [rdx+r12*2], di
0x1800a4195  jnz     short loc_1800A418D
0x1800a4197  mov     r8, r12
0x1800a419a  mov     rcx, r15; void *
0x1800a419d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800a41a2  cmp     qword ptr [r15+18h], 8
0x1800a41a7  jb      short loc_1800A41B3
0x1800a41a9  mov     rax, [rsp+2D8h+var_260]
0x1800a41ae  mov     rcx, [rax]
0x1800a41b1  jmp     short loc_1800A41B6
0x1800a41b3  mov     rcx, r15
0x1800a41b6  mov     rax, [r15+10h]
0x1800a41ba  cmp     [rcx+rax*2-2], si
0x1800a41bf  jz      short loc_1800A41CD
0x1800a41c1  mov     r8d, esi
0x1800a41c4  mov     rcx, r15
0x1800a41c7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1800a41cc  nop
0x1800a41cd  mov     rcx, [rsp+2D8h+pv]; pv
0x1800a41d2  call    cs:__imp_CoTaskMemFree
0x1800a41d8  mov     [rsp+2D8h+pv], rdi
0x1800a41dd  mov     [rsp+2D8h+pv], rdi
0x1800a41e2  mov     rcx, rbx; pv
0x1800a41e5  call    cs:__imp_CoTaskMemFree
0x1800a41eb  mov     [rsp+2D8h+var_288], rdi
0x1800a41f0  mov     [rsp+2D8h+var_288], rdi
0x1800a41f5  mov     [rsp+2D8h+var_1A8], r14
0x1800a41fd  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a4205  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a420a  mov     al, 1
0x1800a420c  jmp     short loc_1800A424D
0x1800a420e  mov     rcx, [rsp+2D8h+pv]; pv
0x1800a4213  call    cs:__imp_CoTaskMemFree
0x1800a4219  mov     [rsp+2D8h+pv], rdi
0x1800a421e  mov     [rsp+2D8h+pv], rdi
0x1800a4223  mov     rcx, rbx; pv
0x1800a4226  call    cs:__imp_CoTaskMemFree
0x1800a422c  mov     [rsp+2D8h+var_288], rdi
0x1800a4231  mov     [rsp+2D8h+var_288], rdi
0x1800a4236  mov     [rsp+2D8h+var_1A8], r14
0x1800a423e  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a4246  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800a424b  xor     al, al
0x1800a424d  mov     rcx, [rsp+2D8h+var_48]
0x1800a4255  xor     rcx, rsp; StackCookie
0x1800a4258  call    __security_check_cookie
0x1800a425d  add     rsp, 2A0h
0x1800a4264  pop     r15
0x1800a4266  pop     r14
0x1800a4268  pop     r13
0x1800a426a  pop     r12
0x1800a426c  pop     rdi
0x1800a426d  pop     rsi
0x1800a426e  pop     rbx
0x1800a426f  retn
0x1800a4270  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a4278  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a427d  mov     edx, eax; int
0x1800a427f  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a4287  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800a428c  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a4294  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800a4299  mov     r8d, eax; char
0x1800a429c  xor     r9d, r9d; unsigned __int16 *
0x1800a429f  mov     edx, 0E1h; unsigned int
0x1800a42a4  lea     rcx, [rsp+2D8h+var_1A8]; this
0x1800a42ac  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x1800a42b2  mov     [rsp+2D8h+pExceptionObject], eax
0x1800a42b6  lea     rdx, _TI1J; pThrowInfo
0x1800a42bd  lea     rcx, [rsp+2D8h+pExceptionObject]; pExceptionObject
0x1800a42c2  call    _CxxThrowException_0
```
