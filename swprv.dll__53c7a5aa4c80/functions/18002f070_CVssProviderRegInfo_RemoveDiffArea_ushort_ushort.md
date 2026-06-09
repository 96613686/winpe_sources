# CVssProviderRegInfo::RemoveDiffArea(ushort *,ushort *)

- ea: `0x18002f070`
- end: `0x18002f59f`
- name: `?RemoveDiffArea@CVssProviderRegInfo@@AEAAXPEAG0@Z`
- size: `1327`
- prototype: `void(CVssProviderRegInfo *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x18002edd8`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800110a8`
- `0x18002f070`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x180037e24`
- `0x18003847c`
- `0x18003a05c`

## string_xrefs

- `0x18002f0b9`: `CVssProviderRegInfo::RemoveDiffArea`
- `0x18002f35b`: `CVssProviderRegInfo::RemoveDiffArea`
- `0x18002f474`: `CVssProviderRegInfo::RemoveDiffArea`
- `0x18002f32b`: `SYSTEM\CurrentControlSet\Services\VSS\Volumes\Associations`
- `0x18002f44b`: `SYSTEM\CurrentControlSet\Services\VSS\Volumes\Associations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVssProviderRegInfo::RemoveDiffArea(
        CVssProviderRegInfo *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned int v5; // [rsp+20h] [rbp-130h]
  __int64 v6; // [rsp+20h] [rbp-130h]
  __int64 v7; // [rsp+20h] [rbp-130h]
  int v8; // [rsp+28h] [rbp-128h]
  __int64 v9; // [rsp+28h] [rbp-128h]
  __int64 v10; // [rsp+28h] [rbp-128h]
  int v11; // [rsp+30h] [rbp-120h]
  __int64 v12; // [rsp+30h] [rbp-120h]
  __int64 v13; // [rsp+30h] [rbp-120h]
  int v14; // [rsp+38h] [rbp-118h]
  __int64 v15; // [rsp+38h] [rbp-118h]
  __int64 v16; // [rsp+38h] [rbp-118h]
  int v17; // [rsp+40h] [rbp-110h]
  __int64 v18; // [rsp+40h] [rbp-110h]
  __int64 v19; // [rsp+40h] [rbp-110h]
  int v20; // [rsp+48h] [rbp-108h]
  __int64 v21; // [rsp+48h] [rbp-108h]
  __int64 v22; // [rsp+48h] [rbp-108h]
  int v23; // [rsp+50h] [rbp-100h]
  __int64 v24; // [rsp+50h] [rbp-100h]
  __int64 v25; // [rsp+50h] [rbp-100h]
  int v26; // [rsp+58h] [rbp-F8h]
  __int64 v27; // [rsp+58h] [rbp-F8h]
  __int64 v28; // [rsp+58h] [rbp-F8h]
  int v29; // [rsp+60h] [rbp-F0h]
  __int64 v30; // [rsp+60h] [rbp-F0h]
  __int64 v31; // [rsp+60h] [rbp-F0h]
  int v32; // [rsp+68h] [rbp-E8h]
  __int64 v33; // [rsp+68h] [rbp-E8h]
  int v34; // [rsp+70h] [rbp-E0h]
  __int64 v35; // [rsp+70h] [rbp-E0h]
  unsigned int Data1; // [rsp+78h] [rbp-D8h]
  int Data2; // [rsp+80h] [rbp-D0h]
  int Data3; // [rsp+88h] [rbp-C8h]
  int v39; // [rsp+90h] [rbp-C0h]
  int v40; // [rsp+98h] [rbp-B8h]
  int v41; // [rsp+A0h] [rbp-B0h]
  int v42; // [rsp+A8h] [rbp-A8h]
  int v43; // [rsp+B0h] [rbp-A0h]
  int v44; // [rsp+B8h] [rbp-98h]
  int v45; // [rsp+C0h] [rbp-90h]
  int v46; // [rsp+C8h] [rbp-88h]
  const wchar_t *v48; // [rsp+E0h] [rbp-70h] BYREF
  const wchar_t *v49; // [rsp+E8h] [rbp-68h]
  const wchar_t *v50; // [rsp+F0h] [rbp-60h]
  int v51; // [rsp+F8h] [rbp-58h]
  int v52; // [rsp+FCh] [rbp-54h]
  int v53; // [rsp+100h] [rbp-50h]
  _BYTE v54[120]; // [rsp+108h] [rbp-48h] BYREF
  int v55; // [rsp+180h] [rbp+30h]
  HKEY v56[4]; // [rsp+188h] [rbp+38h] BYREF
  unsigned __int16 *v57; // [rsp+1A8h] [rbp+58h]
  LPVOID v58[14]; // [rsp+1B0h] [rbp+60h] BYREF
  struct _GUID v59; // [rsp+220h] [rbp+D0h] BYREF
  struct _GUID v60; // [rsp+230h] [rbp+E0h] BYREF

  v57 = a3;
  v48 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
  v49 = L"CVssProviderRegInfo::RemoveDiffArea";
  v50 = L"SPRREGMC";
  v51 = 138;
  v52 = 2;
  v53 = 255;
  v55 = 0x1000000;
  memset_0(v54, 0, sizeof(v54));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v58, (__int64)&v48, 0);
  v59 = 0;
  v60 = 0;
  if ( !GetVolumeGuid(a2, &v59) )
  {
    v48 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v49 = L"CVssProviderRegInfo::RemoveDiffArea";
    v50 = L"SPRREGMC";
    v51 = 146;
    v52 = 2;
    v53 = 255;
    v55 = 0x1000000;
    memset_0(v54, 0, sizeof(v54));
    CVssFunctionTracer::Throw(v58, &v48, 2147942487LL, L"The volume %s does not represent a volume name", a2);
  }
  if ( !GetVolumeGuid(a3, &v60) )
  {
    v48 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v49 = L"CVssProviderRegInfo::RemoveDiffArea";
    v50 = L"SPRREGMC";
    v51 = 148;
    v52 = 2;
    v53 = 255;
    v55 = 0x1000000;
    memset_0(v54, 0, sizeof(v54));
    CVssFunctionTracer::Throw(v58, &v48, 2147942487LL, L"The volume %s does not represent a volume name", a3);
  }
  v56[3] = 0;
  v56[2] = (HKEY)&CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  v56[1] = 0;
  v56[0] = (HKEY)983103;
  v46 = v60.Data4[7];
  v45 = v60.Data4[6];
  v44 = v60.Data4[5];
  v43 = v60.Data4[4];
  v42 = v60.Data4[3];
  v41 = v60.Data4[2];
  v40 = v60.Data4[1];
  v39 = v60.Data4[0];
  Data3 = v60.Data3;
  Data2 = v60.Data2;
  Data1 = v60.Data1;
  v34 = v59.Data4[7];
  v32 = v59.Data4[6];
  v29 = v59.Data4[5];
  v26 = v59.Data4[4];
  v23 = v59.Data4[3];
  v20 = v59.Data4[2];
  v17 = v59.Data4[1];
  v14 = v59.Data4[0];
  v11 = v59.Data3;
  v8 = v59.Data2;
  v5 = v59.Data1;
  if ( !CVssRegistryKey::Open(
          (REGSAM *)v56,
          HKEY_LOCAL_MACHINE,
          L"%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Volumes\\Associations",
          v5,
          v8,
          v11,
          v14,
          v17,
          v20,
          v23,
          v26,
          v29,
          v32,
          v34,
          Data1,
          Data2,
          Data3,
          v39,
          v40,
          v41,
          v42,
          v43,
          v44,
          v45,
          v46) )
  {
    v48 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v49 = L"CVssProviderRegInfo::RemoveDiffArea";
    v50 = L"SPRREGMC";
    v51 = 154;
    v52 = 2;
    v53 = 255;
    v55 = 0x1000000;
    memset_0(v54, 0, sizeof(v54));
    CVssFunctionTracer::Throw(v58, &v48, 2147754760LL, L"An association between %s and %s does not exist", a2, v57);
  }
  LODWORD(v35) = v59.Data4[7];
  LODWORD(v33) = v59.Data4[6];
  LODWORD(v30) = v59.Data4[5];
  LODWORD(v27) = v59.Data4[4];
  LODWORD(v24) = v59.Data4[3];
  LODWORD(v21) = v59.Data4[2];
  LODWORD(v18) = v59.Data4[1];
  LODWORD(v15) = v59.Data4[0];
  LODWORD(v12) = v59.Data3;
  LODWORD(v9) = v59.Data2;
  LODWORD(v6) = v59.Data1;
  if ( !CVssRegistryKey::Open(
          (REGSAM *)v56,
          HKEY_LOCAL_MACHINE,
          L"%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          L"SYSTEM\\CurrentControlSet\\Services\\VSS\\Volumes\\Associations",
          v6,
          v9,
          v12,
          v15,
          v18,
          v21,
          v24,
          v27,
          v30,
          v33,
          v35) )
  {
    v48 = L"base\\stor\\vss\\modules\\softprv\\src\\diffreg.cxx";
    v49 = L"CVssProviderRegInfo::RemoveDiffArea";
    v50 = L"SPRREGMC";
    v51 = 162;
    v52 = 2;
    v53 = 255;
    v55 = 0x1000000;
    memset_0(v54, 0, sizeof(v54));
    CVssFunctionTracer::Throw(v58, &v48, 2147754760LL, L"The association key does not exists for volume %s", a2);
  }
  LODWORD(v31) = v60.Data4[7];
  LODWORD(v28) = v60.Data4[6];
  LODWORD(v25) = v60.Data4[5];
  LODWORD(v22) = v60.Data4[4];
  LODWORD(v19) = v60.Data4[3];
  LODWORD(v16) = v60.Data4[2];
  LODWORD(v13) = v60.Data4[1];
  LODWORD(v10) = v60.Data4[0];
  LODWORD(v7) = v60.Data3;
  CVssRegistryKey::DeleteSubkey(
    v56,
    L"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    v60.Data1,
    v60.Data2,
    v7,
    v10,
    v13,
    v16,
    v19,
    v22,
    v25,
    v28,
    v31);
  CVssRegistryKey::~CVssRegistryKey((CVssRegistryKey *)v56);
  CVssFunctionTracer::~CVssFunctionTracer(v58);
}

```

## disassembly

```asm
0x18002f070  mov     [rsp-8+arg_0], rbx
0x18002f075  push    rbp
0x18002f076  push    rsi
0x18002f077  push    rdi
0x18002f078  push    r12
0x18002f07a  push    r13
0x18002f07c  push    r14
0x18002f07e  push    r15
0x18002f080  lea     rbp, [rsp-100h]
0x18002f088  sub     rsp, 250h
0x18002f08f  mov     rax, cs:__security_cookie
0x18002f096  xor     rax, rsp
0x18002f099  mov     [rbp+130h+var_40], rax
0x18002f0a0  mov     rdi, r8
0x18002f0a3  mov     [rbp+130h+var_D8], r8
0x18002f0a7  mov     rbx, rdx
0x18002f0aa  mov     [rbp+130h+var_1A8], rdx
0x18002f0ae  lea     r14, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002f0b5  mov     [rbp+130h+var_1A0], r14
0x18002f0b9  lea     r15, aCvssproviderre_1; "CVssProviderRegInfo::RemoveDiffArea"
0x18002f0c0  mov     [rbp+130h+var_198], r15
0x18002f0c4  lea     r12, aSprregmc; "SPRREGMC"
0x18002f0cb  mov     [rbp+130h+var_190], r12
0x18002f0cf  mov     [rbp+130h+var_188], 8Ah
0x18002f0d6  mov     r13d, 2
0x18002f0dc  mov     [rbp+130h+var_184], r13d
0x18002f0e0  mov     [rbp+130h+var_180], 0FFh
0x18002f0e7  xor     esi, esi
0x18002f0e9  mov     [rbp+130h+var_100], 1000000h
0x18002f0f0  xor     edx, edx; Val
0x18002f0f2  lea     r8d, [r13+76h]; Size
0x18002f0f6  lea     rcx, [rbp+130h+var_178]; void *
0x18002f0fa  call    memset_0
0x18002f0ff  xor     r8d, r8d
0x18002f102  lea     rdx, [rbp+130h+var_1A0]
0x18002f106  lea     rcx, [rbp+130h+var_D0]
0x18002f10a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18002f10f  nop
0x18002f110  xorps   xmm0, xmm0
0x18002f113  movups  xmmword ptr [rbp+130h+var_60.Data1], xmm0
0x18002f11a  xorps   xmm1, xmm1
0x18002f11d  movups  xmmword ptr [rbp+130h+var_50.Data1], xmm1
0x18002f124  lea     rdx, [rbp+130h+var_60]; struct _GUID *
0x18002f12b  mov     rcx, rbx; unsigned __int16 *
0x18002f12e  call    ?GetVolumeGuid@@YA_NPEBGAEAU_GUID@@@Z; GetVolumeGuid(ushort const *,_GUID &)
0x18002f133  test    al, al
0x18002f135  jnz     short loc_18002F18B
0x18002f137  mov     [rbp+130h+var_1A0], r14
0x18002f13b  mov     [rbp+130h+var_198], r15
0x18002f13f  mov     [rbp+130h+var_190], r12
0x18002f143  mov     [rbp+130h+var_188], 92h
0x18002f14a  mov     [rbp+130h+var_184], r13d
0x18002f14e  mov     [rbp+130h+var_180], 0FFh
0x18002f155  mov     [rbp+130h+var_100], 1000000h
0x18002f15c  xor     edx, edx; Val
0x18002f15e  lea     r8d, [r13+76h]; Size
0x18002f162  lea     rcx, [rbp+130h+var_178]; void *
0x18002f166  call    memset_0
0x18002f16b  mov     [rsp+280h+var_260], rbx
0x18002f170  lea     r9, aTheVolumeSDoes; "The volume %s does not represent a volu"...
0x18002f177  mov     r8d, 80070057h
0x18002f17d  lea     rdx, [rbp+130h+var_1A0]
0x18002f181  lea     rcx, [rbp+130h+var_D0]
0x18002f185  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002f18b  lea     rdx, [rbp+130h+var_50]; struct _GUID *
0x18002f192  mov     rcx, rdi; unsigned __int16 *
0x18002f195  call    ?GetVolumeGuid@@YA_NPEBGAEAU_GUID@@@Z; GetVolumeGuid(ushort const *,_GUID &)
0x18002f19a  test    al, al
0x18002f19c  jnz     short loc_18002F1F2
0x18002f19e  mov     [rbp+130h+var_1A0], r14
0x18002f1a2  mov     [rbp+130h+var_198], r15
0x18002f1a6  mov     [rbp+130h+var_190], r12
0x18002f1aa  mov     [rbp+130h+var_188], 94h
0x18002f1b1  mov     [rbp+130h+var_184], r13d
0x18002f1b5  mov     [rbp+130h+var_180], 0FFh
0x18002f1bc  mov     [rbp+130h+var_100], 1000000h
0x18002f1c3  xor     edx, edx; Val
0x18002f1c5  lea     r8d, [rdx+78h]; Size
0x18002f1c9  lea     rcx, [rbp+130h+var_178]; void *
0x18002f1cd  call    memset_0
0x18002f1d2  mov     [rsp+280h+var_260], rdi
0x18002f1d7  lea     r9, aTheVolumeSDoes; "The volume %s does not represent a volu"...
0x18002f1de  mov     r8d, 80070057h
0x18002f1e4  lea     rdx, [rbp+130h+var_1A0]
0x18002f1e8  lea     rcx, [rbp+130h+var_D0]
0x18002f1ec  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002f1f2  mov     [rbp+130h+var_E0], rsi
0x18002f1f6  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x18002f1fd  mov     [rbp+130h+var_E8], rax
0x18002f201  mov     [rbp+130h+var_F0], rsi
0x18002f205  mov     [rbp+130h+var_F8], 0F003Fh
0x18002f20d  movzx   eax, [rbp+130h+var_50.Data4+7]
0x18002f214  movzx   ecx, [rbp+130h+var_50.Data4+6]
0x18002f21b  movzx   edx, [rbp+130h+var_50.Data4+5]
0x18002f222  movzx   r8d, [rbp+130h+var_50.Data4+4]
0x18002f22a  movzx   r9d, [rbp+130h+var_50.Data4+3]
0x18002f232  movzx   r10d, [rbp+130h+var_50.Data4+2]
0x18002f23a  movzx   r11d, [rbp+130h+var_50.Data4+1]
0x18002f242  movzx   ebx, [rbp+130h+var_50.Data4]
0x18002f249  movzx   edi, [rbp+130h+var_50.Data3]
0x18002f250  movzx   esi, [rbp+130h+var_50.Data2]
0x18002f257  movzx   r15d, [rbp+130h+var_60.Data4+6]
0x18002f25f  movzx   r12d, [rbp+130h+var_60.Data4+5]
0x18002f267  movzx   r13d, [rbp+130h+var_60.Data4+4]
0x18002f26f  mov     [rsp+280h+var_1B8], eax
0x18002f276  mov     [rsp+280h+var_1C0], ecx
0x18002f27d  mov     [rsp+280h+var_1C8], edx
0x18002f284  mov     [rsp+280h+var_1D0], r8d
0x18002f28c  mov     [rsp+280h+var_1D8], r9d
0x18002f294  mov     [rsp+280h+var_1E0], r10d
0x18002f29c  mov     [rsp+280h+var_1E8], r11d
0x18002f2a4  mov     [rsp+280h+var_1F0], ebx
0x18002f2ab  mov     [rsp+280h+var_1F8], edi
0x18002f2b2  mov     [rsp+280h+var_200], esi
0x18002f2b9  mov     eax, [rbp+130h+var_50.Data1]
0x18002f2bf  mov     [rsp+280h+var_208], eax
0x18002f2c3  movzx   r14d, [rbp+130h+var_60.Data4+7]
0x18002f2cb  mov     dword ptr [rsp+280h+var_210], r14d
0x18002f2d0  mov     dword ptr [rsp+280h+var_218], r15d
0x18002f2d5  mov     dword ptr [rsp+280h+var_220], r12d
0x18002f2da  mov     dword ptr [rsp+280h+var_228], r13d
0x18002f2df  movzx   eax, [rbp+130h+var_60.Data4+3]
0x18002f2e6  mov     dword ptr [rsp+280h+var_230], eax
0x18002f2ea  movzx   eax, [rbp+130h+var_60.Data4+2]
0x18002f2f1  mov     dword ptr [rsp+280h+var_238], eax
0x18002f2f5  movzx   eax, [rbp+130h+var_60.Data4+1]
0x18002f2fc  mov     dword ptr [rsp+280h+var_240], eax
0x18002f300  movzx   eax, [rbp+130h+var_60.Data4]
0x18002f307  mov     dword ptr [rsp+280h+var_248], eax
0x18002f30b  movzx   eax, [rbp+130h+var_60.Data3]
0x18002f312  mov     dword ptr [rsp+280h+var_250], eax
0x18002f316  movzx   eax, [rbp+130h+var_60.Data2]
0x18002f31d  mov     dword ptr [rsp+280h+var_258], eax
0x18002f321  mov     eax, [rbp+130h+var_60.Data1]
0x18002f327  mov     dword ptr [rsp+280h+var_260], eax
0x18002f32b  lea     r9, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18002f332  lea     r8, aS8x4x4x2x2x2x2; "%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x18002f339  mov     r12, 0FFFFFFFF80000002h
0x18002f340  mov     rdx, r12; hKey
0x18002f343  lea     rcx, [rbp+130h+var_F8]; this
0x18002f347  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18002f34c  test    al, al
0x18002f34e  jnz     short loc_18002F3C9
0x18002f350  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002f357  mov     [rbp+130h+var_1A0], rax
0x18002f35b  lea     rax, aCvssproviderre_1; "CVssProviderRegInfo::RemoveDiffArea"
0x18002f362  mov     [rbp+130h+var_198], rax
0x18002f366  lea     rax, aSprregmc; "SPRREGMC"
0x18002f36d  mov     [rbp+130h+var_190], rax
0x18002f371  mov     [rbp+130h+var_188], 9Ah
0x18002f378  mov     [rbp+130h+var_184], 2
0x18002f37f  mov     [rbp+130h+var_180], 0FFh
0x18002f386  mov     [rbp+130h+var_100], 1000000h
0x18002f38d  xor     edx, edx; Val
0x18002f38f  lea     r8d, [rdx+78h]; Size
0x18002f393  lea     rcx, [rbp+130h+var_178]; void *
0x18002f397  call    memset_0
0x18002f39c  mov     rax, [rbp+130h+var_D8]
0x18002f3a0  mov     [rsp+280h+var_258], rax
0x18002f3a5  mov     rax, [rbp+130h+var_1A8]
0x18002f3a9  mov     [rsp+280h+var_260], rax
0x18002f3ae  lea     r9, aAnAssociationB; "An association between %s and %s does n"...
0x18002f3b5  mov     r8d, 80042308h
0x18002f3bb  lea     rdx, [rbp+130h+var_1A0]
0x18002f3bf  lea     rcx, [rbp+130h+var_D0]
0x18002f3c3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002f3c9  movzx   eax, [rbp+130h+var_60.Data4+7]
0x18002f3d0  movzx   ecx, [rbp+130h+var_60.Data4+6]
0x18002f3d7  movzx   r8d, [rbp+130h+var_60.Data4+5]
0x18002f3df  movzx   r10d, [rbp+130h+var_60.Data4+4]
0x18002f3e7  movzx   r11d, [rbp+130h+var_60.Data4+3]
0x18002f3ef  movzx   ebx, [rbp+130h+var_60.Data4+2]
0x18002f3f6  movzx   edi, [rbp+130h+var_60.Data4+1]
0x18002f3fd  movzx   esi, [rbp+130h+var_60.Data4]
0x18002f404  movzx   r14d, [rbp+130h+var_60.Data3]
0x18002f40c  movzx   r15d, [rbp+130h+var_60.Data2]
0x18002f414  mov     dword ptr [rsp+280h+var_210], eax
0x18002f418  mov     dword ptr [rsp+280h+var_218], ecx
0x18002f41c  mov     dword ptr [rsp+280h+var_220], r8d
0x18002f421  mov     dword ptr [rsp+280h+var_228], r10d
0x18002f426  mov     dword ptr [rsp+280h+var_230], r11d
0x18002f42b  mov     dword ptr [rsp+280h+var_238], ebx
0x18002f42f  mov     dword ptr [rsp+280h+var_240], edi
0x18002f433  mov     dword ptr [rsp+280h+var_248], esi
0x18002f437  mov     dword ptr [rsp+280h+var_250], r14d
0x18002f43c  mov     dword ptr [rsp+280h+var_258], r15d
0x18002f441  mov     eax, [rbp+130h+var_60.Data1]
0x18002f447  mov     dword ptr [rsp+280h+var_260], eax
0x18002f44b  lea     r9, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\VS"...
0x18002f452  lea     r8, aS8x4x4x2x2x2x2_0; "%s\\{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%."...
0x18002f459  mov     rdx, r12; hKey
0x18002f45c  lea     rcx, [rbp+130h+var_F8]; this
0x18002f460  call    ?Open@CVssRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CVssRegistryKey::Open(HKEY__ *,ushort const *,...)
0x18002f465  test    al, al
0x18002f467  jnz     short loc_18002F4D9
0x18002f469  lea     rax, aBaseStorVssMod_16; "base\\stor\\vss\\modules\\softprv\\src"...
0x18002f470  mov     [rbp+130h+var_1A0], rax
0x18002f474  lea     rax, aCvssproviderre_1; "CVssProviderRegInfo::RemoveDiffArea"
0x18002f47b  mov     [rbp+130h+var_198], rax
0x18002f47f  lea     rax, aSprregmc; "SPRREGMC"
0x18002f486  mov     [rbp+130h+var_190], rax
0x18002f48a  mov     [rbp+130h+var_188], 0A2h
0x18002f491  mov     [rbp+130h+var_184], 2
0x18002f498  mov     [rbp+130h+var_180], 0FFh
0x18002f49f  mov     [rbp+130h+var_100], 1000000h
0x18002f4a6  xor     edx, edx; Val
0x18002f4a8  lea     r8d, [rdx+78h]; Size
0x18002f4ac  lea     rcx, [rbp+130h+var_178]; void *
0x18002f4b0  call    memset_0
0x18002f4b5  mov     rax, [rbp+130h+var_1A8]
0x18002f4b9  mov     [rsp+280h+var_260], rax
0x18002f4be  lea     r9, aTheAssociation; "The association key does not exists for"...
0x18002f4c5  mov     r8d, 80042308h
0x18002f4cb  lea     rdx, [rbp+130h+var_1A0]
0x18002f4cf  lea     rcx, [rbp+130h+var_D0]
0x18002f4d3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18002f4d9  movzx   eax, [rbp+130h+var_50.Data4+7]
0x18002f4e0  movzx   ecx, [rbp+130h+var_50.Data4+6]
0x18002f4e7  movzx   edx, [rbp+130h+var_50.Data4+5]
0x18002f4ee  movzx   r8d, [rbp+130h+var_50.Data4+4]
0x18002f4f6  movzx   r10d, [rbp+130h+var_50.Data4+3]
0x18002f4fe  movzx   r11d, [rbp+130h+var_50.Data4+2]
0x18002f506  movzx   ebx, [rbp+130h+var_50.Data4+1]
0x18002f50d  movzx   edi, [rbp+130h+var_50.Data4]
0x18002f514  movzx   esi, [rbp+130h+var_50.Data3]
0x18002f51b  movzx   r9d, [rbp+130h+var_50.Data2]
0x18002f523  mov     dword ptr [rsp+280h+var_220], eax
0x18002f527  mov     dword ptr [rsp+280h+var_228], ecx
0x18002f52b  mov     dword ptr [rsp+280h+var_230], edx
0x18002f52f  mov     dword ptr [rsp+280h+var_238], r8d
0x18002f534  mov     dword ptr [rsp+280h+var_240], r10d
0x18002f539  mov     dword ptr [rsp+280h+var_248], r11d
0x18002f53e  mov     dword ptr [rsp+280h+var_250], ebx
0x18002f542  mov     dword ptr [rsp+280h+var_258], edi
0x18002f546  mov     dword ptr [rsp+280h+var_260], esi
0x18002f54a  mov     r8d, [rbp+130h+var_50.Data1]
0x18002f551  lea     rdx, a8x4x4x2x2x2x2x; "{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%."...
0x18002f558  lea     rcx, [rbp+130h+var_F8]; this
0x18002f55c  call    ?DeleteSubkey@CVssRegistryKey@@QEAAXPEBGZZ; CVssRegistryKey::DeleteSubkey(ushort const *,...)
0x18002f561  nop
0x18002f562  lea     rcx, [rbp+130h+var_F8]; this
0x18002f566  call    ??1CVssRegistryKey@@QEAA@XZ; CVssRegistryKey::~CVssRegistryKey(void)
0x18002f56b  nop
0x18002f56c  lea     rcx, [rbp+130h+var_D0]; this
0x18002f570  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18002f575  mov     rcx, [rbp+130h+var_40]
0x18002f57c  xor     rcx, rsp; StackCookie
0x18002f57f  call    __security_check_cookie
0x18002f584  mov     rbx, [rsp+280h+arg_0]
0x18002f58c  add     rsp, 250h
0x18002f593  pop     r15
0x18002f595  pop     r14
0x18002f597  pop     r13
0x18002f599  pop     r12
0x18002f59b  pop     rdi
0x18002f59c  pop     rsi
0x18002f59d  pop     rbp
0x18002f59e  retn
```
