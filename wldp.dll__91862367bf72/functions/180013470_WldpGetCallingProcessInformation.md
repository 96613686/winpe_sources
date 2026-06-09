# WldpGetCallingProcessInformation

- ea: `0x180013470`
- end: `0x1800138fa`
- name: `WldpGetCallingProcessInformation`
- size: `1162`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cd18`
- `0x18001d9b4`

## callees

- `0x180013470`
- `0x180013970`
- `0x180013a24`
- `0x18001f8c4`
- `0x1800201d4`
- `0x1800206f4`
- `0x180021ec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800134da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800134da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800134d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800134d1`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x1800134f0`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleInformation` at `0x1800134f0`

## string_xrefs

- `0x1800137ec`: `onecore\base\ngscb\wldp\dll\tracelogging.cpp`
- `0x180013806`: `onecore\base\ngscb\wldp\dll\tracelogging.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall WldpGetCallingProcessInformation(__m128i *a1)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  int OriginalFilenameAndVersionFromImageBase; // eax
  __m128i *v6; // rbx
  __m128i si128; // xmm6
  unsigned __int64 v8; // rdx
  __m128i *v9; // rbx
  unsigned __int64 v10; // rdx
  __m128i *v11; // rbx
  unsigned __int64 v12; // rdx
  __m128i *v13; // rbx
  unsigned __int64 v14; // rdx
  __m128i *v15; // rbx
  unsigned __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v25[2]; // [rsp+A0h] [rbp-60h] BYREF
  _MODULEINFO modinfo; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v27; // [rsp+C8h] [rbp-38h] BYREF
  __m128i v28; // [rsp+D8h] [rbp-28h]
  __m128i v29; // [rsp+E8h] [rbp-18h] BYREF
  __m128i v30; // [rsp+F8h] [rbp-8h]
  __m128i v31; // [rsp+108h] [rbp+8h] BYREF
  __m128i v32; // [rsp+118h] [rbp+18h]
  __m128i v33; // [rsp+128h] [rbp+28h] BYREF
  __m128i v34; // [rsp+138h] [rbp+38h]
  __m128i v35; // [rsp+148h] [rbp+48h] BYREF
  __m128i v36; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v21 = 0;
  *(_OWORD *)v22 = 0;
  *(_OWORD *)v25 = 0;
  *(_OWORD *)v23 = 0;
  *(_OWORD *)v24 = 0;
  v19 = 0;
  v20 = 0;
  memset(&modinfo, 0, sizeof(modinfo));
  ModuleHandleW = GetModuleHandleW(0);
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetModuleInformation(CurrentProcess, ModuleHandleW, &modinfo, 0x18u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x211,
             (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\tracelogging.cpp",
             v4);
  OriginalFilenameAndVersionFromImageBase = SIPolicyGetOriginalFilenameAndVersionFromImageBase(
                                              modinfo.lpBaseOfDll,
                                              modinfo.SizeOfImage,
                                              (__int64)&v19,
                                              (__int64)v23,
                                              (__int64)&v20,
                                              (__int64)v22,
                                              (__int64)v25,
                                              (__int64)v24);
  if ( (unsigned int)(OriginalFilenameAndVersionFromImageBase + 1073741687) <= 2
    || OriginalFilenameAndVersionFromImageBase == -1073741793
    || OriginalFilenameAndVersionFromImageBase == -1073741308 )
  {
    OriginalFilenameAndVersionFromImageBase = -1073741275;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x21E,
             (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\tracelogging.cpp",
             (const char *)(unsigned int)OriginalFilenameAndVersionFromImageBase,
             v18);
  }
  if ( OriginalFilenameAndVersionFromImageBase < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x21E,
             (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\tracelogging.cpp",
             (const char *)(unsigned int)OriginalFilenameAndVersionFromImageBase,
             v18);
  a1->m128i_i64[0] = v19;
  a1->m128i_i64[1] = v20;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v27,
    *((_QWORD *)&v21 + 1),
    (unsigned __int64)(unsigned __int16)v21 >> 1);
  v6 = a1 + 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( &a1[1] != &v27 )
  {
    v8 = a1[2].m128i_u64[1];
    if ( v8 > 7 )
      std::_Deallocate<16>(v6->m128i_i64[0], 2 * v8 + 2);
    *v6 = v27;
    a1[2] = v28;
    v28 = si128;
    v27.m128i_i16[0] = 0;
  }
  if ( v28.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v27.m128i_i64[0], 2 * v28.m128i_i64[1] + 2);
  v28 = si128;
  v27.m128i_i16[0] = 0;
  v29 = 0;
  v30 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v29, v22[1], (unsigned __int64)LOWORD(v22[0]) >> 1);
  v9 = a1 + 3;
  if ( &a1[3] != &v29 )
  {
    v10 = a1[4].m128i_u64[1];
    if ( v10 > 7 )
      std::_Deallocate<16>(v9->m128i_i64[0], 2 * v10 + 2);
    *v9 = v29;
    a1[4] = v30;
    v30 = si128;
    v29.m128i_i16[0] = 0;
  }
  if ( v30.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v29.m128i_i64[0], 2 * v30.m128i_i64[1] + 2);
  v30 = si128;
  v29.m128i_i16[0] = 0;
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v31, v23[1], (unsigned __int64)LOWORD(v23[0]) >> 1);
  v11 = a1 + 5;
  if ( &a1[5] != &v31 )
  {
    v12 = a1[6].m128i_u64[1];
    if ( v12 > 7 )
      std::_Deallocate<16>(v11->m128i_i64[0], 2 * v12 + 2);
    *v11 = v31;
    a1[6] = v32;
    v32 = si128;
    v31.m128i_i16[0] = 0;
  }
  if ( v32.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v31.m128i_i64[0], 2 * v32.m128i_i64[1] + 2);
  v32 = si128;
  v31.m128i_i16[0] = 0;
  v33 = 0;
  v34 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v33, v24[1], (unsigned __int64)LOWORD(v24[0]) >> 1);
  v13 = a1 + 7;
  if ( &a1[7] != &v33 )
  {
    v14 = a1[8].m128i_u64[1];
    if ( v14 > 7 )
      std::_Deallocate<16>(v13->m128i_i64[0], 2 * v14 + 2);
    *v13 = v33;
    a1[8] = v34;
    v34 = si128;
    v33.m128i_i16[0] = 0;
  }
  if ( v34.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v33.m128i_i64[0], 2 * v34.m128i_i64[1] + 2);
  v34 = si128;
  v33.m128i_i16[0] = 0;
  v35 = 0;
  v36 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v35, v25[1], (unsigned __int64)LOWORD(v25[0]) >> 1);
  v15 = a1 + 9;
  if ( &a1[9] != &v35 )
  {
    v16 = a1[10].m128i_u64[1];
    if ( v16 > 7 )
      std::_Deallocate<16>(v15->m128i_i64[0], 2 * v16 + 2);
    *v15 = v35;
    a1[10] = v36;
    v36 = si128;
    v35.m128i_i16[0] = 0;
  }
  if ( v36.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v35.m128i_i64[0], 2 * v36.m128i_i64[1] + 2);
  v36 = si128;
  v35.m128i_i16[0] = 0;
  return 0;
}

```

## disassembly

```asm
0x180013470  push    rbp
0x180013472  push    rbx
0x180013473  push    rsi
0x180013474  push    rdi
0x180013475  lea     rbp, [rsp-88h]
0x18001347d  sub     rsp, 188h
0x180013484  movaps  [rsp+1A0h+var_30], xmm6
0x18001348c  mov     rax, cs:__security_cookie
0x180013493  xor     rax, rsp
0x180013496  mov     [rbp+0A0h+var_38], rax
0x18001349a  mov     rdi, rcx
0x18001349d  xorps   xmm0, xmm0
0x1800134a0  movups  [rsp+1A0h+var_140], xmm0
0x1800134a5  xorps   xmm1, xmm1
0x1800134a8  movups  xmmword ptr [rsp+1A0h+var_130], xmm1
0x1800134ad  movups  xmmword ptr [rbp+0A0h+var_100], xmm0
0x1800134b1  movups  xmmword ptr [rbp+0A0h+var_120], xmm1
0x1800134b5  movups  xmmword ptr [rbp+0A0h+var_110], xmm0
0x1800134b9  xor     esi, esi
0x1800134bb  mov     [rsp+1A0h+var_150], rsi
0x1800134c0  mov     [rsp+1A0h+var_148], rsi
0x1800134c5  xor     eax, eax
0x1800134c7  movups  xmmword ptr [rbp+0A0h+modinfo.lpBaseOfDll], xmm0
0x1800134cb  mov     [rbp+0A0h+modinfo.EntryPoint], rax
0x1800134cf  xor     ecx, ecx; lpModuleName
0x1800134d1  call    cs:__imp_GetModuleHandleW
0x1800134d7  mov     rbx, rax
0x1800134da  call    cs:__imp_GetCurrentProcess
0x1800134e0  mov     r9d, 18h; cb
0x1800134e6  lea     r8, [rbp+0A0h+modinfo]; lpmodinfo
0x1800134ea  mov     rdx, rbx; hModule
0x1800134ed  mov     rcx, rax; hProcess
0x1800134f0  call    cs:__imp_K32GetModuleInformation
0x1800134f6  test    eax, eax
0x1800134f8  jz      loc_1800137FF
0x1800134fe  lea     rax, [rbp+0A0h+var_110]
0x180013502  mov     [rsp+1A0h+var_158], rax; __int64
0x180013507  lea     rax, [rbp+0A0h+var_100]
0x18001350b  mov     [rsp+1A0h+var_160], rax; __int64
0x180013510  lea     rax, [rsp+1A0h+var_130]
0x180013515  mov     [rsp+1A0h+var_168], rax; __int64
0x18001351a  lea     rax, [rsp+1A0h+var_148]
0x18001351f  mov     [rsp+1A0h+var_170], rax; __int64
0x180013524  lea     rax, [rbp+0A0h+var_120]
0x180013528  mov     [rsp+1A0h+var_178], rax; __int64
0x18001352d  lea     rax, [rsp+1A0h+var_150]
0x180013532  mov     [rsp+1A0h+var_180], rax; int
0x180013537  lea     r9, [rsp+1A0h+var_140]
0x18001353c  mov     edx, [rbp+0A0h+modinfo.SizeOfImage]; Size
0x18001353f  mov     rcx, [rbp+0A0h+modinfo.lpBaseOfDll]; BaseAddress
0x180013543  call    SIPolicyGetOriginalFilenameAndVersionFromImageBase
0x180013548  lea     ecx, [rax+3FFFFF77h]
0x18001354e  cmp     ecx, 2
0x180013551  jbe     loc_1800138F0
0x180013557  cmp     eax, 0C000001Fh
0x18001355c  jz      loc_1800138F0
0x180013562  cmp     eax, 0C0000204h
0x180013567  jz      loc_1800138F0
0x18001356d  test    eax, eax
0x18001356f  js      loc_1800137E2
0x180013575  mov     rax, [rsp+1A0h+var_150]
0x18001357a  mov     [rdi], rax
0x18001357d  mov     rax, [rsp+1A0h+var_148]
0x180013582  mov     [rdi+8], rax
0x180013586  xorps   xmm0, xmm0
0x180013589  movups  [rbp+0A0h+var_D8], xmm0
0x18001358d  xorps   xmm1, xmm1
0x180013590  movdqu  [rbp+0A0h+var_C8], xmm1
0x180013595  movzx   r8d, word ptr [rsp+1A0h+var_140]
0x18001359b  shr     r8, 1
0x18001359e  mov     rdx, qword ptr [rsp+1A0h+var_140+8]
0x1800135a3  lea     rcx, [rbp+0A0h+var_D8]
0x1800135a7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800135ac  nop
0x1800135ad  lea     rbx, [rdi+10h]
0x1800135b1  lea     rax, [rbp+0A0h+var_D8]
0x1800135b5  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800135bd  cmp     rbx, rax
0x1800135c0  jz      short loc_1800135E8
0x1800135c2  mov     rdx, [rbx+18h]
0x1800135c6  cmp     rdx, 7
0x1800135ca  ja      loc_180013819
0x1800135d0  movups  xmm0, [rbp+0A0h+var_D8]
0x1800135d4  movups  xmmword ptr [rbx], xmm0
0x1800135d7  movups  xmm1, [rbp+0A0h+var_C8]
0x1800135db  movups  xmmword ptr [rbx+10h], xmm1
0x1800135df  movdqu  [rbp+0A0h+var_C8], xmm6
0x1800135e4  mov     word ptr [rbp+0A0h+var_D8], si
0x1800135e8  mov     rdx, qword ptr [rbp+0A0h+var_C8+8]
0x1800135ec  cmp     rdx, 7
0x1800135f0  ja      loc_18001382E
0x1800135f6  movdqu  [rbp+0A0h+var_C8], xmm6
0x1800135fb  mov     word ptr [rbp+0A0h+var_D8], si
0x1800135ff  xorps   xmm0, xmm0
0x180013602  movups  [rbp+0A0h+var_B8], xmm0
0x180013606  xorps   xmm1, xmm1
0x180013609  movdqu  [rbp+0A0h+var_A8], xmm1
0x18001360e  movzx   r8d, word ptr [rsp+1A0h+var_130]
0x180013614  shr     r8, 1
0x180013617  mov     rdx, [rsp+1A0h+var_130+8]
0x18001361c  lea     rcx, [rbp+0A0h+var_B8]
0x180013620  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013625  nop
0x180013626  lea     rbx, [rdi+30h]
0x18001362a  lea     rax, [rbp+0A0h+var_B8]
0x18001362e  cmp     rbx, rax
0x180013631  jz      short loc_180013659
0x180013633  mov     rdx, [rbx+18h]
0x180013637  cmp     rdx, 7
0x18001363b  ja      loc_180013844
0x180013641  movups  xmm0, [rbp+0A0h+var_B8]
0x180013645  movups  xmmword ptr [rbx], xmm0
0x180013648  movups  xmm1, [rbp+0A0h+var_A8]
0x18001364c  movups  xmmword ptr [rbx+10h], xmm1
0x180013650  movdqu  [rbp+0A0h+var_A8], xmm6
0x180013655  mov     word ptr [rbp+0A0h+var_B8], si
0x180013659  mov     rdx, qword ptr [rbp+0A0h+var_A8+8]
0x18001365d  cmp     rdx, 7
0x180013661  ja      loc_180013859
0x180013667  movdqu  [rbp+0A0h+var_A8], xmm6
0x18001366c  mov     word ptr [rbp+0A0h+var_B8], si
0x180013670  xorps   xmm0, xmm0
0x180013673  movups  [rbp+0A0h+var_98], xmm0
0x180013677  xorps   xmm1, xmm1
0x18001367a  movdqu  [rbp+0A0h+var_88], xmm1
0x18001367f  movzx   r8d, word ptr [rbp+0A0h+var_120]
0x180013684  shr     r8, 1
0x180013687  mov     rdx, [rbp+0A0h+var_120+8]
0x18001368b  lea     rcx, [rbp+0A0h+var_98]
0x18001368f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013694  nop
0x180013695  lea     rbx, [rdi+50h]
0x180013699  lea     rax, [rbp+0A0h+var_98]
0x18001369d  cmp     rbx, rax
0x1800136a0  jz      short loc_1800136C8
0x1800136a2  mov     rdx, [rbx+18h]
0x1800136a6  cmp     rdx, 7
0x1800136aa  ja      loc_18001386F
0x1800136b0  movups  xmm0, [rbp+0A0h+var_98]
0x1800136b4  movups  xmmword ptr [rbx], xmm0
0x1800136b7  movups  xmm1, [rbp+0A0h+var_88]
0x1800136bb  movups  xmmword ptr [rbx+10h], xmm1
0x1800136bf  movdqu  [rbp+0A0h+var_88], xmm6
0x1800136c4  mov     word ptr [rbp+0A0h+var_98], si
0x1800136c8  mov     rdx, qword ptr [rbp+0A0h+var_88+8]
0x1800136cc  cmp     rdx, 7
0x1800136d0  ja      loc_180013884
0x1800136d6  movdqu  [rbp+0A0h+var_88], xmm6
0x1800136db  mov     word ptr [rbp+0A0h+var_98], si
0x1800136df  xorps   xmm0, xmm0
0x1800136e2  movups  [rbp+0A0h+var_78], xmm0
0x1800136e6  xorps   xmm1, xmm1
0x1800136e9  movdqu  [rbp+0A0h+var_68], xmm1
0x1800136ee  movzx   r8d, word ptr [rbp+0A0h+var_110]
0x1800136f3  shr     r8, 1
0x1800136f6  mov     rdx, [rbp+0A0h+var_110+8]
0x1800136fa  lea     rcx, [rbp+0A0h+var_78]
0x1800136fe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013703  nop
0x180013704  lea     rbx, [rdi+70h]
0x180013708  lea     rax, [rbp+0A0h+var_78]
0x18001370c  cmp     rbx, rax
0x18001370f  jz      short loc_180013737
0x180013711  mov     rdx, [rbx+18h]
0x180013715  cmp     rdx, 7
0x180013719  ja      loc_18001389A
0x18001371f  movups  xmm0, [rbp+0A0h+var_78]
0x180013723  movups  xmmword ptr [rbx], xmm0
0x180013726  movups  xmm1, [rbp+0A0h+var_68]
0x18001372a  movups  xmmword ptr [rbx+10h], xmm1
0x18001372e  movdqu  [rbp+0A0h+var_68], xmm6
0x180013733  mov     word ptr [rbp+0A0h+var_78], si
0x180013737  mov     rdx, qword ptr [rbp+0A0h+var_68+8]
0x18001373b  cmp     rdx, 7
0x18001373f  ja      loc_1800138AF
0x180013745  movdqu  [rbp+0A0h+var_68], xmm6
0x18001374a  mov     word ptr [rbp+0A0h+var_78], si
0x18001374e  xorps   xmm0, xmm0
0x180013751  movups  [rbp+0A0h+var_58], xmm0
0x180013755  xorps   xmm1, xmm1
0x180013758  movdqu  [rbp+0A0h+var_48], xmm1
0x18001375d  movzx   r8d, word ptr [rbp+0A0h+var_100]
0x180013762  shr     r8, 1
0x180013765  mov     rdx, [rbp+0A0h+var_100+8]
0x180013769  lea     rcx, [rbp+0A0h+var_58]
0x18001376d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180013772  nop
0x180013773  lea     rbx, [rdi+90h]
0x18001377a  lea     rax, [rbp+0A0h+var_58]
0x18001377e  cmp     rbx, rax
0x180013781  jz      short loc_1800137A9
0x180013783  mov     rdx, [rbx+18h]
0x180013787  cmp     rdx, 7
0x18001378b  ja      loc_1800138C5
0x180013791  movups  xmm0, [rbp+0A0h+var_58]
0x180013795  movups  xmmword ptr [rbx], xmm0
0x180013798  movups  xmm1, [rbp+0A0h+var_48]
0x18001379c  movups  xmmword ptr [rbx+10h], xmm1
0x1800137a0  movdqu  [rbp+0A0h+var_48], xmm6
0x1800137a5  mov     word ptr [rbp+0A0h+var_58], si
0x1800137a9  mov     rdx, qword ptr [rbp+0A0h+var_48+8]
0x1800137ad  cmp     rdx, 7
0x1800137b1  ja      loc_1800138DA
0x1800137b7  movdqu  [rbp+0A0h+var_48], xmm6
0x1800137bc  mov     word ptr [rbp+0A0h+var_58], si
0x1800137c0  xor     eax, eax
0x1800137c2  mov     rcx, [rbp+0A0h+var_38]
0x1800137c6  xor     rcx, rsp; StackCookie
0x1800137c9  call    __security_check_cookie
0x1800137ce  movaps  xmm6, [rsp+1A0h+var_30]
0x1800137d6  add     rsp, 188h
0x1800137dd  pop     rdi
0x1800137de  pop     rsi
0x1800137df  pop     rbx
0x1800137e0  pop     rbp
0x1800137e1  retn
0x1800137e2  mov     rcx, [rbp+0A8h]; this
0x1800137e9  mov     r9d, eax; char *
0x1800137ec  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\wldp\\dll\\tracel"...
0x1800137f3  mov     edx, 21Eh; void *
0x1800137f8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800137fd  jmp     short loc_1800137C2
0x1800137ff  mov     rcx, [rbp+0A8h]; this
0x180013806  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\wldp\\dll\\tracel"...
0x18001380d  mov     edx, 211h; void *
0x180013812  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013817  jmp     short loc_1800137C2
0x180013819  lea     rdx, ds:2[rdx*2]
0x180013821  mov     rcx, [rbx]
0x180013824  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013829  jmp     loc_1800135D0
0x18001382e  lea     rdx, ds:2[rdx*2]
0x180013836  mov     rcx, qword ptr [rbp+0A0h+var_D8]
0x18001383a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001383f  jmp     loc_1800135F6
0x180013844  lea     rdx, ds:2[rdx*2]
0x18001384c  mov     rcx, [rbx]
0x18001384f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013854  jmp     loc_180013641
0x180013859  lea     rdx, ds:2[rdx*2]
0x180013861  mov     rcx, qword ptr [rbp+0A0h+var_B8]
0x180013865  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001386a  jmp     loc_180013667
0x18001386f  lea     rdx, ds:2[rdx*2]
0x180013877  mov     rcx, [rbx]
0x18001387a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001387f  jmp     loc_1800136B0
0x180013884  lea     rdx, ds:2[rdx*2]
0x18001388c  mov     rcx, qword ptr [rbp+0A0h+var_98]
0x180013890  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013895  jmp     loc_1800136D6
0x18001389a  lea     rdx, ds:2[rdx*2]
0x1800138a2  mov     rcx, [rbx]
0x1800138a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800138aa  jmp     loc_18001371F
0x1800138af  lea     rdx, ds:2[rdx*2]
0x1800138b7  mov     rcx, qword ptr [rbp+0A0h+var_78]
0x1800138bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800138c0  jmp     loc_180013745
0x1800138c5  lea     rdx, ds:2[rdx*2]
0x1800138cd  mov     rcx, [rbx]
0x1800138d0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800138d5  jmp     loc_180013791
0x1800138da  lea     rdx, ds:2[rdx*2]
0x1800138e2  mov     rcx, qword ptr [rbp+0A0h+var_58]
0x1800138e6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800138eb  jmp     loc_1800137B7
0x1800138f0  mov     eax, 0C0000225h
0x1800138f5  jmp     loc_1800137E2
```
