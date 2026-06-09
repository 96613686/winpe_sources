# SxspResolvePartialReferenceWithProcessArchitecture(ulong,ulong,_ACTCTXGENCTX *,CAssemblyReference const &,CProbedAssemblyInformation &,CGenericStringBuffer<64,CUnicodeCharTraits> &,ushort const *,unsigned __int64,bool,bool &)

- ea: `0x180017dc0`
- end: `0x18001972e`
- name: `?SxspResolvePartialReferenceWithProcessArchitecture@@YAHKKPEAU_ACTCTXGENCTX@@AEBVCAssemblyReference@@AEAVCProbedAssemblyInformation@@AEAV?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@PEBG_K_NAEA_N@Z`
- size: `6510`
- prototype: `__int64 __fastcall(int, int, int, int, CAssemblyReference *, __int64, __int64, unsigned __int64, char, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, installer_update`

## callers

- `0x180016870`

## callees

- `0x1800075a0`
- `0x18000cd10`
- `0x18000df40`
- `0x18000dffc`
- `0x1800176b0`
- `0x180017910`
- `0x180017dc0`
- `0x180019740`
- `0x180019cc0`
- `0x18001c2c8`
- `0x18001e5c0`
- `0x18004c178`
- `0x18004e0c0`
- `0x180050d7c`
- `0x18005b8a0`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a0dd`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180017fd7`
- `ntdll!EtwEventWrite` at `0x180018608`
- `ntdll!EtwEventWrite` at `0x1800186d5`
- `ntdll!EtwEventWrite` at `0x180018bf0`
- `ntdll!EtwEventWrite` at `0x180018c8b`
- `ntdll!EtwEventWrite` at `0x180018d54`
- `ntdll!EtwEventWrite` at `0x180017fd7`
- `ntdll!EtwEventWrite` at `0x180018608`
- `ntdll!EtwEventWrite` at `0x1800186d5`
- `ntdll!EtwEventWrite` at `0x180018bf0`
- `ntdll!EtwEventWrite` at `0x180018c8b`
- `ntdll!EtwEventWrite` at `0x180018d54`
- `ntdll!RtlPopFrame` at `0x1800180ab`
- `ntdll!RtlPopFrame` at `0x1800181af`
- `ntdll!RtlPopFrame` at `0x1800182fe`
- `ntdll!RtlPopFrame` at `0x180018474`
- `ntdll!RtlPopFrame` at `0x1800184b7`
- `ntdll!RtlPopFrame` at `0x1800186f2`
- `ntdll!RtlPopFrame` at `0x18001888f`
- `ntdll!RtlPopFrame` at `0x1800188d2`
- `ntdll!RtlPopFrame` at `0x180018a75`
- `ntdll!RtlPopFrame` at `0x180018aa4`
- `ntdll!RtlPopFrame` at `0x180018ca8`
- `ntdll!RtlPopFrame` at `0x180018da8`
- `ntdll!RtlPopFrame` at `0x180019168`
- `ntdll!RtlPopFrame` at `0x180019192`
- `ntdll!RtlPopFrame` at `0x180019203`
- `ntdll!RtlPopFrame` at `0x18001922d`
- `ntdll!RtlPopFrame` at `0x1800193d3`
- `ntdll!RtlPopFrame` at `0x180019462`
- `ntdll!RtlPopFrame` at `0x180019563`
- `ntdll!RtlPopFrame` at `0x18001958d`
- `ntdll!RtlPopFrame` at `0x1800195cd`
- `ntdll!RtlPopFrame` at `0x18001960a`
- `ntdll!RtlPopFrame` at `0x1800180ab`
- `ntdll!RtlPopFrame` at `0x1800181af`
- `ntdll!RtlPopFrame` at `0x1800182fe`
- `ntdll!RtlPopFrame` at `0x180018474`
- `ntdll!RtlPopFrame` at `0x1800184b7`
- `ntdll!RtlPopFrame` at `0x1800186f2`
- `ntdll!RtlPopFrame` at `0x18001888f`
- `ntdll!RtlPopFrame` at `0x1800188d2`
- `ntdll!RtlPopFrame` at `0x180018a75`
- `ntdll!RtlPopFrame` at `0x180018aa4`
- `ntdll!RtlPopFrame` at `0x180018ca8`
- `ntdll!RtlPopFrame` at `0x180018da8`
- `ntdll!RtlPopFrame` at `0x180019168`
- `ntdll!RtlPopFrame` at `0x180019192`
- `ntdll!RtlPopFrame` at `0x180019203`
- `ntdll!RtlPopFrame` at `0x18001922d`
- `ntdll!RtlPopFrame` at `0x1800193d3`
- `ntdll!RtlPopFrame` at `0x180019462`
- `ntdll!RtlPopFrame` at `0x180019563`
- `ntdll!RtlPopFrame` at `0x18001958d`
- `ntdll!RtlPopFrame` at `0x1800195cd`
- `ntdll!RtlPopFrame` at `0x18001960a`
- `ntdll!RtlPushFrame` at `0x180017e6a`
- `ntdll!RtlPushFrame` at `0x18001802a`
- `ntdll!RtlPushFrame` at `0x180018103`
- `ntdll!RtlPushFrame` at `0x18001823f`
- `ntdll!RtlPushFrame` at `0x180018358`
- `ntdll!RtlPushFrame` at `0x180018516`
- `ntdll!RtlPushFrame` at `0x180018764`
- `ntdll!RtlPushFrame` at `0x18001895e`
- `ntdll!RtlPushFrame` at `0x180017e6a`
- `ntdll!RtlPushFrame` at `0x18001802a`
- `ntdll!RtlPushFrame` at `0x180018103`
- `ntdll!RtlPushFrame` at `0x18001823f`
- `ntdll!RtlPushFrame` at `0x180018358`
- `ntdll!RtlPushFrame` at `0x180018516`
- `ntdll!RtlPushFrame` at `0x180018764`
- `ntdll!RtlPushFrame` at `0x18001895e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001931b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001941d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001951f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001931b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001941d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001951f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800195f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001807e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800180c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001812f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800181e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018283`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001848a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001879e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001884a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001890d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001898c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018b33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018bfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018de6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019004`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019027`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800191be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019256`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017fe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001807e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800180c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001812f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800181e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018264`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018283`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018431`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001848a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800184cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018616`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018722`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001879e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001884a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800188f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001890d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001898c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018a32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018aea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018b33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018bfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018de6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018e68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018f75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018fc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019004`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019027`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800191be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019256`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800192ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019381`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800194ce`

## pseudocode

```c
__int64 __fastcall SxspResolvePartialReferenceWithProcessArchitecture(
        int a1,
        unsigned int a2,
        __int64 a3,
        const struct _ASSEMBLY_IDENTITY **a4,
        CAssemblyReference *a5,
        __int64 a6,
        unsigned __int16 *a7,
        unsigned __int64 a8,
        char a9,
        _BYTE *a10)
{
  CAssemblyReference *v10; // r12
  _BYTE *v12; // rsi
  __int64 v13; // r14
  char v14; // r15
  unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  bool v18; // zf
  int v19; // ebx
  char v20; // bl
  int v21; // edi
  unsigned int i; // r13d
  __int64 v23; // rax
  unsigned __int64 v24; // rbx
  __int64 v25; // r12
  __int64 v26; // rax
  const void *v27; // r15
  unsigned __int64 v28; // rsi
  unsigned __int64 v29; // rdi
  char *v30; // rsi
  unsigned __int64 v31; // rbx
  size_t v32; // rbx
  int v33; // ebx
  CAssemblyReference *v34; // rdi
  unsigned __int64 v35; // rsi
  unsigned __int16 *v36; // rbx
  __int64 v37; // rdi
  const char *v38; // rcx
  int v39; // ebx
  int v40; // ebx
  __int64 v41; // rax
  const wchar_t *v42; // rbx
  int v43; // edi
  __int64 v44; // r8
  __int64 v45; // rax
  int v46; // ebx
  const char *v47; // rcx
  unsigned __int16 *v48; // rdi
  __int64 v49; // rbx
  const char *v50; // rcx
  int v51; // ebx
  int v52; // ebx
  __int64 v53; // rsi
  unsigned __int16 *v54; // rbx
  const char *v55; // rcx
  __int64 v56; // rdi
  const char *v57; // rcx
  int v58; // ebx
  int v59; // ebx
  int v60; // edi
  unsigned __int64 v61; // rdx
  unsigned __int64 v62; // rdx
  int v63; // ebx
  unsigned int v64; // ebx
  char *v66; // r14
  unsigned __int64 v67; // rbx
  size_t v68; // rbx
  void *v69; // rax
  unsigned __int16 *v70; // r9
  DWORD LastError; // eax
  DWORD v72; // eax
  DWORD v73; // eax
  DWORD v74; // eax
  DWORD v75; // eax
  DWORD v76; // eax
  DWORD v77; // eax
  DWORD v78; // eax
  DWORD v79; // eax
  DWORD v80; // eax
  DWORD v81; // eax
  DWORD v82; // eax
  unsigned __int64 v84; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v85; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v86; // [rsp+58h] [rbp-A8h]
  CAssemblyReference *v87; // [rsp+60h] [rbp-A0h]
  __int64 v88; // [rsp+68h] [rbp-98h]
  __int64 v89; // [rsp+70h] [rbp-90h]
  _BYTE *v90; // [rsp+78h] [rbp-88h]
  void *v91; // [rsp+80h] [rbp-80h] BYREF
  int v92; // [rsp+88h] [rbp-78h] BYREF
  int v93; // [rsp+90h] [rbp-70h] BYREF
  int v94; // [rsp+94h] [rbp-6Ch]
  __int64 v95; // [rsp+98h] [rbp-68h]
  struct _TEB_ACTIVE_FRAME v96; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v97; // [rsp+B8h] [rbp-48h]
  int v98; // [rsp+C0h] [rbp-40h]
  void **v99; // [rsp+C8h] [rbp-38h]
  int v100; // [rsp+D0h] [rbp-30h] BYREF
  struct _TEB_ACTIVE_FRAME v101; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h]
  int v103; // [rsp+F8h] [rbp-8h]
  void **v104; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v105; // [rsp+108h] [rbp+8h] BYREF
  __int64 v106; // [rsp+110h] [rbp+10h]
  int v107; // [rsp+118h] [rbp+18h] BYREF
  int v108; // [rsp+120h] [rbp+20h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+128h] [rbp+28h] BYREF
  __int64 v110; // [rsp+140h] [rbp+40h]
  int v111; // [rsp+148h] [rbp+48h]
  int *v112; // [rsp+150h] [rbp+50h]
  void **v113; // [rsp+160h] [rbp+60h] BYREF
  int v114; // [rsp+168h] [rbp+68h]
  void *Src; // [rsp+170h] [rbp+70h]
  unsigned __int64 v116; // [rsp+178h] [rbp+78h]
  unsigned __int64 v117; // [rsp+180h] [rbp+80h]
  __int16 v118; // [rsp+188h] [rbp+88h] BYREF
  __int128 v119; // [rsp+210h] [rbp+110h] BYREF
  __int128 v120; // [rsp+220h] [rbp+120h]
  __int128 v121; // [rsp+230h] [rbp+130h]
  unsigned __int16 *v122; // [rsp+240h] [rbp+140h]
  void **v123; // [rsp+260h] [rbp+160h] BYREF
  __int64 v124; // [rsp+268h] [rbp+168h]
  const wchar_t *v125; // [rsp+270h] [rbp+170h]
  __int64 v126; // [rsp+278h] [rbp+178h]
  void **v127; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v128; // [rsp+2B8h] [rbp+1B8h]

  v10 = a5;
  v12 = a10;
  v13 = a3;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CF40;
  v100 = a1;
  v112 = &v107;
  v89 = a3;
  v87 = a5;
  v88 = a6;
  v86 = a7;
  v90 = a10;
  v107 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v110 = 544438355;
  v111 = 666;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v85 = 0;
  v113 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  v84 = 0;
  v114 = 0;
  Src = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  Src = (void *)CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(&v113);
  v116 = ((__int64 (__fastcall *)(void ***))v113[3])(&v113);
  if ( (unsigned int)Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline() )
    memset_0(Src, 0, 2 * v116);
  v14 = a9;
  if ( a9 )
    v15 = *(unsigned __int16 **)(a6 + 16);
  else
    v15 = a7;
  v108 = *(_DWORD *)(v13 + 1304);
  v92 = v108;
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v105 = (unsigned __int16 *)0x670004000000D0LL;
    v106 = 256;
    v16 = 1;
    *(_QWORD *)&v119 = &v92;
    *((_QWORD *)&v119 + 1) = 4;
    if ( v15 )
    {
      *(_QWORD *)&v120 = v15;
      v17 = -1;
      do
        v18 = v15[++v17] == 0;
      while ( !v18 );
      *((_QWORD *)&v120 + 1) = (unsigned int)(2 * v17 + 2);
      v16 = 2;
    }
    EtwEventWrite(g_hTraceHandle, &v105, v16, &v119);
  }
  *a10 = 0;
  SetLastError(0);
  v96.Flags = 1;
  v92 = 0;
  v96.Previous = 0;
  v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CF60;
  v99 = (void **)&v92;
  v97 = 544438355;
  v98 = 212;
  RtlPushFrame(&v96);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  SetLastError(0);
  if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                       1u,
                       *a4,
                       (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                       (const unsigned __int16 **)&v85,
                       &v84) )
  {
    SetLastError(0);
    *(_DWORD *)v99 = 1;
  }
  else
  {
    *(_DWORD *)v99 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800785A8);
  }
  v19 = *(_DWORD *)v99;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v96);
    if ( v19 )
      goto LABEL_22;
LABEL_180:
    *v112 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006DDB8);
    goto LABEL_128;
  }
  if ( !v19 )
  {
    LastError = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    RtlPopFrame(&v96);
    goto LABEL_180;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v96);
LABEL_22:
  SetLastError(0);
  v101.Flags = 1;
  v101.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CF80;
  v102 = 544438355;
  v20 = 0;
  v104 = (void **)&v92;
  v92 = 0;
  v101.Previous = 0;
  v103 = 283;
  RtlPushFrame(&v101);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v18 = *a4 == 0;
  v105 = 0;
  v91 = 0;
  if ( v18 )
  {
LABEL_181:
    SetLastError(0x54Fu);
    *(_DWORD *)v104 = 0;
    goto LABEL_31;
  }
  SetLastError(0);
  if ( (unsigned int)SxspGetAssemblyIdentityAttributeValue(
                       1u,
                       *a4,
                       (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_language,
                       (const unsigned __int16 **)&v105,
                       (unsigned __int64 *)&v91) )
  {
    if ( v91 != (void *)1 )
    {
LABEL_30:
      SetLastError(0);
      *(_DWORD *)v104 = 1;
      goto LABEL_31;
    }
    if ( v105 )
    {
      if ( *v105 == 42 )
        v20 = 1;
      goto LABEL_30;
    }
    goto LABEL_181;
  }
  *(_DWORD *)v104 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078528);
LABEL_31:
  v21 = *(_DWORD *)v104;
  if ( !g_FusionEnterExitTracingEnabled )
  {
    RtlPopFrame(&v101);
    if ( v21 )
      goto LABEL_33;
LABEL_186:
    *v112 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077E20);
    goto LABEL_128;
  }
  if ( !v21 )
  {
    v72 = GetLastError();
    FusionpTraceCallWin32UnsuccessfulExit(v72, 0);
    RtlPopFrame(&v101);
    goto LABEL_186;
  }
  FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&v101);
LABEL_33:
  if ( !v20 )
  {
    if ( a9 )
    {
      SetLastError(0);
      if ( !(unsigned int)CAssemblyReference::SetProcessorArchitecture(
                            a5,
                            *(const unsigned __int16 **)(a6 + 16),
                            *(_QWORD *)(a6 + 32)) )
      {
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077E00);
        goto LABEL_128;
      }
    }
    SetLastError(0);
    v70 = L"Neutral";
    if ( v85 )
      v70 = v85;
    if ( !(unsigned int)SxspResolvePartialReferenceWithCulture(a2, v13, a5, v70, 0, 0, a10) )
    {
      *v112 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077DE0);
      goto LABEL_128;
    }
    if ( !*a10 )
    {
      if ( a9 )
      {
        SetLastError(0);
        if ( !(unsigned int)CAssemblyReference::SetProcessorArchitecture(a5, v86, a8) )
        {
          *v112 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077DC0);
          goto LABEL_128;
        }
      }
    }
    goto LABEL_127;
  }
  for ( i = 0; i < *(_DWORD *)(v13 + 16); ++i )
  {
    if ( !v14 )
      goto LABEL_37;
    SetLastError(0);
    v96.Flags = 1;
    v92 = 0;
    v96.Previous = 0;
    v53 = *(_QWORD *)(v88 + 32);
    v54 = *(unsigned __int16 **)(v88 + 16);
    v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D660;
    v99 = (void **)&v92;
    v97 = 544438355;
    v98 = 416;
    RtlPushFrame(&v96);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    if ( !v54 && v53 )
    {
      v98 = 418;
      FusionpTraceParameterCheck(v55);
      SetLastError(0x57u);
      *(_DWORD *)v99 = 0;
      goto LABEL_110;
    }
    if ( !*(_QWORD *)v10 )
    {
      SetLastError(0x54Fu);
      *(_DWORD *)v99 = 0;
      goto LABEL_110;
    }
    SetLastError(0);
    v56 = *(_QWORD *)v10;
    v101.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDE0;
    LODWORD(v91) = 0;
    v104 = &v91;
    v101.Flags = 1;
    v101.Previous = 0;
    v102 = 544438355;
    v103 = 25;
    CFrame::BaseEnter((CFrame *)&v101);
    v122 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    if ( v56 )
    {
      if ( v54 || !v53 )
      {
        *((_QWORD *)&v121 + 1) = L"processorArchitecture";
        *(_QWORD *)&v120 = 21;
        v122 = v54;
        *((_QWORD *)&v120 + 1) = v53;
        SetLastError(0);
        if ( (unsigned int)SxsInsertAssemblyIdentityAttribute(1, v56, &v119) )
        {
          LODWORD(v91) = 1;
        }
        else
        {
          *(_DWORD *)v104 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D140);
        }
        goto LABEL_107;
      }
      v103 = 36;
    }
    else
    {
      v103 = 30;
    }
    FusionpTraceParameterCheck(v57);
    SetLastError(0x57u);
    *(_DWORD *)v104 = 0;
LABEL_107:
    v58 = (int)v91;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v104 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v73 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v73, 0);
      }
    }
    RtlPopFrame(&v101);
    if ( v58 )
    {
      v92 = 1;
    }
    else
    {
      *(_DWORD *)v99 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078468);
    }
LABEL_110:
    v59 = v92;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v99 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v74 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v74, 0);
      }
    }
    RtlPopFrame(&v96);
    if ( !v59 )
    {
      *v112 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18006D6C0);
      goto LABEL_128;
    }
LABEL_37:
    SetLastError(0);
    v23 = *(_QWORD *)(v13 + 32);
    v92 = 0;
    v96.Flags = 1;
    v96.Previous = 0;
    v24 = *(unsigned int *)(v23 + 4LL * i);
    v25 = 8LL * i;
    v26 = *(_QWORD *)(v13 + 24);
    v97 = 544438355;
    v98 = 210;
    v27 = *(const void **)(v25 + v26);
    v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`2'::__stc;
    v99 = (void **)&v92;
    RtlPushFrame(&v96);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    if ( v114 )
    {
      SetLastError(0x54Fu);
      *(_DWORD *)v99 = 0;
      goto LABEL_47;
    }
    SetLastError(0);
    v28 = v24 + 1;
    v29 = v24;
    if ( v24 + 1 > v116 )
    {
      SetLastError(0);
      if ( v28 > v116 )
      {
        v91 = 0;
        if ( !((unsigned int (__fastcall *)(void ***, unsigned __int64, void **))*v113)(&v113, v28, &v91) )
        {
          *(_DWORD *)v99 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign'::`41'::__callsite);
          goto LABEL_47;
        }
        v66 = (char *)v91;
        if ( Src )
        {
          v67 = v117;
          if ( v117 >= v28 )
            v67 = v29;
          v68 = 2 * v67;
          memcpy_0(v91, Src, v68);
          *(_WORD *)&v66[v68] = 0;
        }
        else
        {
          *(_WORD *)v91 = 0;
        }
        if ( Src )
        {
          v69 = (void *)((__int64 (__fastcall *)(void ***))v113[2])(&v113);
          if ( Src != v69 )
            ((void (__fastcall *)(void ***))v113[1])(&v113);
        }
        v13 = v89;
        Src = v91;
        v116 = v28;
      }
    }
    SetLastError(0);
    if ( v116 )
    {
      v30 = (char *)Src;
      if ( v27 )
      {
        if ( v29 >= v116 )
          v31 = v116 - 1;
        else
          v31 = v29;
        v32 = 2 * v31;
        memcpy_0(Src, v27, v32);
        *(_WORD *)&v30[v32] = 0;
      }
      else
      {
        *(_WORD *)Src = 0;
      }
    }
    v117 = v29;
    SetLastError(0);
    *(_DWORD *)v99 = 1;
LABEL_47:
    v33 = *(_DWORD *)v99;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( !v33 )
      {
        v78 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v78, 0);
        RtlPopFrame(&v96);
LABEL_228:
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077DA0);
        goto LABEL_128;
      }
      FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&v96);
    }
    else
    {
      RtlPopFrame(&v96);
      if ( !v33 )
        goto LABEL_228;
    }
    SetLastError(0);
    v96.Flags = 1;
    v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CEC0;
    v97 = 544438355;
    v99 = &v91;
    LODWORD(v91) = 0;
    v96.Previous = 0;
    v98 = 230;
    RtlPushFrame(&v96);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v34 = v87;
    if ( !*(_QWORD *)v87 )
    {
      SetLastError(0x54Fu);
      *(_DWORD *)v99 = 0;
      goto LABEL_59;
    }
    SetLastError(0);
    v35 = v117;
    v36 = (unsigned __int16 *)Src;
    v37 = *(_QWORD *)v34;
    v101.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDE0;
    v104 = (void **)&v92;
    v92 = 0;
    v101.Flags = 1;
    v101.Previous = 0;
    v102 = 544438355;
    v103 = 25;
    CFrame::BaseEnter((CFrame *)&v101);
    v122 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    if ( v37 )
    {
      if ( v36 || !v35 )
      {
        *((_QWORD *)&v121 + 1) = L"language";
        *(_QWORD *)&v120 = 8;
        v122 = v36;
        *((_QWORD *)&v120 + 1) = v35;
        SetLastError(0);
        if ( (unsigned int)SxsInsertAssemblyIdentityAttribute(1, v37, &v119) )
        {
          v92 = 1;
        }
        else
        {
          *(_DWORD *)v104 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D140);
        }
        goto LABEL_56;
      }
      v103 = 36;
    }
    else
    {
      v103 = 30;
    }
    FusionpTraceParameterCheck(v38);
    SetLastError(0x57u);
    *(_DWORD *)v104 = 0;
LABEL_56:
    v39 = v92;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v104 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v75 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v75, 0);
      }
    }
    RtlPopFrame(&v101);
    if ( v39 )
    {
      SetLastError(0);
      *(_DWORD *)v99 = 1;
    }
    else
    {
      *(_DWORD *)v99 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078588);
    }
LABEL_59:
    v40 = *(_DWORD *)v99;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( !v40 )
      {
        v79 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v79, 0);
        RtlPopFrame(&v96);
LABEL_230:
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077D80);
        goto LABEL_128;
      }
      FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&v96);
    }
    else
    {
      RtlPopFrame(&v96);
      if ( !v40 )
        goto LABEL_230;
    }
    SetLastError(0);
    v41 = *(_QWORD *)(v13 + 24);
    v92 = 0;
    v96.Flags = 1;
    v96.Previous = 0;
    v42 = *(const wchar_t **)(v25 + v41);
    v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CEA0;
    v99 = (void **)&v92;
    v97 = 544438355;
    v98 = 792;
    RtlPushFrame(&v96);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    v18 = g_TraceEnabled == 0;
    v12 = v90;
    *v90 = 0;
    v43 = *(_DWORD *)(v13 + 1304);
    LODWORD(v91) = v43;
    if ( !v18
      && (unsigned __int8)(g_TraceLevel - 1) > 2u
      && (g_OrKeywordMask & 0x100) != 0
      && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
    {
      v105 = (unsigned __int16 *)0x670004000000CALL;
      v123 = &v91;
      v44 = 1;
      v106 = 256;
      v124 = 4;
      if ( v42 )
      {
        v125 = v42;
        v45 = -1;
        do
          v18 = v42[++v45] == 0;
        while ( !v18 );
        v126 = (unsigned int)(2 * v45 + 2);
        v44 = 2;
      }
      EtwEventWrite(g_hTraceHandle, &v105, v44, &v123);
    }
    SetLastError(0);
    v10 = v87;
    if ( (unsigned int)CProbedAssemblyInformation::ProbeAssembly(v87, a2, v13, 2, i, v12) )
    {
      v46 = 1;
      v92 = 1;
    }
    else
    {
      *(_DWORD *)v99 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C60);
      v46 = v92;
    }
    LODWORD(v91) = v43;
    if ( g_TraceEnabled
      && (unsigned __int8)(g_TraceLevel - 1) > 2u
      && (g_OrKeywordMask & 0x100) != 0
      && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
    {
      v127 = &v91;
      v93 = 203;
      v94 = 6750212;
      v95 = 256;
      v128 = 4;
      EtwEventWrite(g_hTraceHandle, &v93, 1, &v127);
    }
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v99 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v76 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v76, 0);
      }
    }
    RtlPopFrame(&v96);
    if ( !v46 )
    {
      *v112 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077D60);
      goto LABEL_128;
    }
    if ( *v12 )
      goto LABEL_127;
    v14 = a9;
    if ( a9 )
    {
      SetLastError(0);
      if ( !(unsigned int)CAssemblyReference::SetProcessorArchitecture(v10, v86, a8) )
      {
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077D40);
        goto LABEL_128;
      }
    }
    SetLastError(0);
    v101.Flags = 1;
    v101.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CEE0;
    v102 = 544438355;
    v104 = &v91;
    LODWORD(v91) = 0;
    v101.Previous = 0;
    v103 = 251;
    RtlPushFrame(&v101);
    if ( g_FusionEnterExitTracingEnabled )
      FusionpTraceCallEntry();
    if ( !*(_QWORD *)v10 )
    {
      SetLastError(0x54Fu);
      *(_DWORD *)v104 = 0;
      goto LABEL_95;
    }
    v48 = v85;
    if ( v84 && !v85 )
    {
      v103 = 254;
      FusionpTraceParameterCheck(v47);
      SetLastError(0x57u);
      *(_DWORD *)v104 = 0;
      goto LABEL_95;
    }
    SetLastError(0);
    v49 = *(_QWORD *)v10;
    v96.Flags = 1;
    v92 = 0;
    v96.Previous = 0;
    v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CDE0;
    v99 = (void **)&v92;
    v97 = 544438355;
    v98 = 25;
    CFrame::BaseEnter((CFrame *)&v96);
    v122 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    if ( v49 )
    {
      if ( v48 || !v84 )
      {
        *((_QWORD *)&v121 + 1) = L"language";
        *((_QWORD *)&v120 + 1) = v84;
        *(_QWORD *)&v120 = 8;
        v122 = v48;
        SetLastError(0);
        if ( (unsigned int)SxsInsertAssemblyIdentityAttribute(1, v49, &v119) )
        {
          v92 = 1;
        }
        else
        {
          *(_DWORD *)v99 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007D140);
        }
        goto LABEL_92;
      }
      v98 = 36;
    }
    else
    {
      v98 = 30;
    }
    FusionpTraceParameterCheck(v50);
    SetLastError(0x57u);
    *(_DWORD *)v99 = 0;
LABEL_92:
    v51 = v92;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( *(_DWORD *)v99 )
      {
        FusionpTraceCallSuccessfulExit(0);
      }
      else
      {
        v77 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v77, 0);
      }
    }
    RtlPopFrame(&v96);
    if ( v51 )
    {
      SetLastError(0);
      *(_DWORD *)v104 = 1;
    }
    else
    {
      *(_DWORD *)v104 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078568);
    }
LABEL_95:
    v52 = *(_DWORD *)v104;
    if ( g_FusionEnterExitTracingEnabled )
    {
      if ( !v52 )
      {
        v80 = GetLastError();
        FusionpTraceCallWin32UnsuccessfulExit(v80, 0);
        RtlPopFrame(&v101);
LABEL_232:
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077D20);
        goto LABEL_128;
      }
      FusionpTraceCallSuccessfulExit(0);
      RtlPopFrame(&v101);
    }
    else
    {
      RtlPopFrame(&v101);
      if ( !v52 )
        goto LABEL_232;
    }
  }
  if ( *v12 || (v100 & 2) != 0 )
  {
LABEL_127:
    v107 = 1;
    goto LABEL_128;
  }
  if ( v14
    && (SetLastError(0),
        !(unsigned int)CAssemblyReference::SetProcessorArchitecture(
                         v10,
                         *(const unsigned __int16 **)(v88 + 16),
                         *(_QWORD *)(v88 + 32))) )
  {
    *v112 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077D00);
  }
  else
  {
    SetLastError(0);
    if ( (unsigned int)CAssemblyReference::ClearLanguage(v10) )
    {
      SetLastError(0);
      v92 = 0;
      v96.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CEA0;
      v96.Flags = 1;
      v99 = (void **)&v92;
      v96.Previous = 0;
      v97 = 544438355;
      v98 = 792;
      CFrame::BaseEnter((CFrame *)&v96);
      *v12 = 0;
      v60 = *(_DWORD *)(v13 + 1304);
      v100 = v60;
      if ( (unsigned int)IsEventEnabled(4u, v61) )
      {
        v93 = 202;
        v125 = L"Neutral";
        v94 = 6750212;
        v95 = 256;
        v123 = (void **)&v100;
        v124 = 4;
        v126 = 16;
        EtwEventWrite(g_hTraceHandle, &v93, 2, &v123);
      }
      SetLastError(0);
      if ( (unsigned int)CProbedAssemblyInformation::ProbeAssembly(v10, a2, v13, 1, 0, v12) )
      {
        v63 = 1;
        v92 = 1;
      }
      else
      {
        *(_DWORD *)v99 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C60);
        v63 = v92;
      }
      v100 = v60;
      if ( (unsigned int)IsEventEnabled(4u, v62) )
      {
        v127 = (void **)&v100;
        v93 = 203;
        v94 = 6750212;
        v95 = 256;
        v128 = 4;
        EtwEventWrite(g_hTraceHandle, &v93, 1, &v127);
      }
      if ( g_FusionEnterExitTracingEnabled )
      {
        if ( *(_DWORD *)v99 )
        {
          FusionpTraceCallSuccessfulExit(0);
        }
        else
        {
          v81 = GetLastError();
          FusionpTraceCallWin32UnsuccessfulExit(v81, 0);
        }
      }
      RtlPopFrame(&v96);
      if ( v63 )
      {
        if ( *v12 )
          goto LABEL_127;
        if ( v14 && (SetLastError(0), !(unsigned int)CAssemblyReference::SetProcessorArchitecture(v10, v86, a8)) )
        {
          *v112 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077CA0);
        }
        else
        {
          SetLastError(0);
          if ( (unsigned int)CAssemblyReference::SetLanguage(v10, v85, v84) )
            goto LABEL_127;
          *v112 = 0;
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C80);
        }
      }
      else
      {
        *v112 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077CC0);
      }
    }
    else
    {
      *v112 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077CE0);
    }
  }
LABEL_128:
  v64 = v107;
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v127 = (void **)&v108;
    v93 = 209;
    v94 = 6750212;
    v95 = 256;
    v128 = 4;
    EtwEventWrite(g_hTraceHandle, &v93, 1, &v127);
  }
  v113 = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( Src != &v118 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v113);
  v113 = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  Src = 0;
  v116 = 0;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v112 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      v82 = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(v82, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v64;
}

```

## disassembly

```asm
0x180017dc0  mov     [rsp-8+arg_0], rbx
0x180017dc5  push    rbp
0x180017dc6  push    rsi
0x180017dc7  push    rdi
0x180017dc8  push    r12
0x180017dca  push    r13
0x180017dcc  push    r14
0x180017dce  push    r15
0x180017dd0  lea     rbp, [rsp-210h]
0x180017dd8  sub     rsp, 310h
0x180017ddf  mov     rax, cs:__security_cookie
0x180017de6  xor     rax, rsp
0x180017de9  mov     [rbp+240h+var_40], rax
0x180017df0  mov     r12, [rbp+240h+arg_20]
0x180017df7  lea     rax, qword_18006CF40
0x180017dfe  mov     r13, [rbp+240h+arg_28]
0x180017e05  xor     r15d, r15d
0x180017e08  mov     rbx, [rbp+240h+arg_30]
0x180017e0f  mov     rdi, r9
0x180017e12  mov     rsi, [rbp+240h+arg_48]
0x180017e19  mov     r14, r8
0x180017e1c  mov     [rbp+240h+Frame.Context], rax
0x180017e20  lea     rax, [rbp+240h+var_228]
0x180017e24  mov     [rbp+240h+var_270], ecx
0x180017e27  lea     rcx, [rbp+240h+Frame]; Frame
0x180017e2b  mov     [rbp+240h+var_1F0], rax
0x180017e2f  mov     [rsp+340h+var_2D0], r8
0x180017e34  mov     [rsp+340h+var_300], edx
0x180017e38  mov     [rsp+340h+var_2E0], r12
0x180017e3d  mov     [rsp+340h+var_2D8], r13
0x180017e42  mov     [rsp+340h+var_2E8], rbx
0x180017e47  mov     [rsp+340h+var_2C8], rsi
0x180017e4c  mov     [rbp+240h+var_228], r15d
0x180017e50  mov     [rbp+240h+Frame.Flags], 1
0x180017e57  mov     [rbp+240h+Frame.Previous], r15
0x180017e5b  mov     [rbp+240h+var_200], 20737853h
0x180017e63  mov     [rbp+240h+var_1F8], 29Ah
0x180017e6a  call    cs:__imp_RtlPushFrame
0x180017e71  nop     dword ptr [rax+rax+00h]
0x180017e76  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180017e7d  jnz     loc_180018F8D
0x180017e83  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180017e8a  mov     [rsp+340h+var_2F0], r15
0x180017e8f  lea     rcx, [rbp+240h+var_1E0]
0x180017e93  mov     [rbp+240h+var_1E0], rax
0x180017e97  mov     [rsp+340h+var_2F8], r15
0x180017e9c  mov     [rbp+240h+var_1D8], r15d
0x180017ea0  mov     [rbp+240h+Src], r15
0x180017ea4  mov     [rbp+240h+var_1C8], r15
0x180017ea8  mov     [rbp+240h+var_1C0], r15
0x180017eaf  mov     [rbp+240h+var_1B8], r15w
0x180017eb7  call    ?GetInlineBuffer@?$CGenericStringBuffer@$00VCUnicodeCharTraits@@@@MEBAPEAGXZ; CGenericStringBuffer<1,CUnicodeCharTraits>::GetInlineBuffer(void)
0x180017ebc  mov     [rbp+240h+Src], rax
0x180017ec0  lea     rcx, [rbp+240h+var_1E0]
0x180017ec4  mov     rax, [rbp+240h+var_1E0]
0x180017ec8  mov     rax, [rax+18h]
0x180017ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ed1  mov     [rbp+240h+var_1C8], rax
0x180017ed5  call    Feature_Servicing_SxS_NullTerminateFix__private_IsEnabledDeviceUsageNoInline
0x180017eda  test    eax, eax
0x180017edc  jz      short loc_180017EF0
0x180017ede  mov     r8, [rbp+240h+var_1C8]
0x180017ee2  xor     edx, edx; Val
0x180017ee4  mov     rcx, [rbp+240h+Src]; void *
0x180017ee8  add     r8, r8; Size
0x180017eeb  call    memset_0
0x180017ef0  movzx   r15d, [rbp+240h+arg_40]
0x180017ef8  test    r15b, r15b
0x180017efb  jz      loc_180018F3F
0x180017f01  mov     rdx, [r13+10h]
0x180017f05  cmp     cs:?g_TraceEnabled@@3KA, 0; ulong g_TraceEnabled
0x180017f0c  mov     eax, [r14+518h]
0x180017f13  mov     [rbp+240h+var_220], eax
0x180017f16  mov     [rbp+240h+var_2B8], eax
0x180017f19  jz      loc_180017FE3
0x180017f1f  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x180017f26  dec     al
0x180017f28  cmp     al, 2
0x180017f2a  jbe     loc_180017FE3
0x180017f30  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x180017f3b  jz      loc_180017FE3
0x180017f41  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x180017f48  and     eax, 100h
0x180017f4d  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x180017f54  jnz     loc_180017FE3
0x180017f5a  xor     ecx, ecx
0x180017f5c  mov     dword ptr [rbp+240h+var_238], 0D0h
0x180017f63  mov     dword ptr [rbp+240h+var_238+4], 670004h
0x180017f6a  lea     rax, [rbp+240h+var_2B8]
0x180017f6e  mov     [rbp+240h+var_230], 100h
0x180017f76  mov     r8d, 1
0x180017f7c  mov     qword ptr [rbp+240h+var_130], rax
0x180017f83  mov     qword ptr [rbp+240h+var_130+8], 4
0x180017f8e  test    rdx, rdx
0x180017f91  jz      short loc_180017FC5
0x180017f93  mov     qword ptr [rbp+240h+var_120], rdx
0x180017f9a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180017fa1  cmp     [rdx+rax*2+2], cx
0x180017fa6  lea     rax, [rax+1]
0x180017faa  jnz     short loc_180017FA1
0x180017fac  lea     eax, ds:2[rax*2]
0x180017fb3  mov     dword ptr [rbp+240h+var_120+0Ch], ecx
0x180017fb9  mov     dword ptr [rbp+240h+var_120+8], eax
0x180017fbf  mov     r8d, 2
0x180017fc5  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x180017fcc  lea     r9, [rbp+240h+var_130]
0x180017fd3  lea     rdx, [rbp+240h+var_238]
0x180017fd7  call    cs:__imp_EtwEventWrite
0x180017fde  nop     dword ptr [rax+rax+00h]
0x180017fe3  xor     ecx, ecx; dwErrCode
0x180017fe5  mov     byte ptr [rsi], 0
0x180017fe8  call    cs:__imp_SetLastError
0x180017fef  nop     dword ptr [rax+rax+00h]
0x180017ff4  xor     eax, eax
0x180017ff6  mov     [rbp+240h+var_2A0.Flags], 1
0x180017ffd  mov     [rbp+240h+var_2B8], eax
0x180018000  lea     rcx, [rbp+240h+var_2A0]; Frame
0x180018004  mov     [rbp+240h+var_2A0.Previous], rax
0x180018008  lea     rax, qword_18006CF60
0x18001800f  mov     [rbp+240h+var_2A0.Context], rax
0x180018013  lea     rax, [rbp+240h+var_2B8]
0x180018017  mov     [rbp+240h+var_278], rax
0x18001801b  mov     [rbp+240h+var_288], 20737853h
0x180018023  mov     [rbp+240h+var_280], 0D4h
0x18001802a  call    cs:__imp_RtlPushFrame
0x180018031  nop     dword ptr [rax+rax+00h]
0x180018036  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001803d  jnz     loc_180018F97
0x180018043  xor     ecx, ecx; dwErrCode
0x180018045  call    cs:__imp_SetLastError
0x18001804c  nop     dword ptr [rax+rax+00h]
0x180018051  mov     rdx, [rdi]; struct _ASSEMBLY_IDENTITY *
0x180018054  lea     rax, [rsp+340h+var_2F8]
0x180018059  lea     r9, [rsp+340h+var_2F0]; unsigned __int16 **
0x18001805e  mov     [rsp+340h+var_320], rax; unsigned __int64 *
0x180018063  lea     r8, s_IdentityAttribute_language; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18001806a  mov     ecx, 1; unsigned int
0x18001806f  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180018074  test    eax, eax
0x180018076  jz      loc_18001913E
0x18001807c  xor     ecx, ecx; dwErrCode
0x18001807e  call    cs:__imp_SetLastError
0x180018085  nop     dword ptr [rax+rax+00h]
0x18001808a  mov     rax, [rbp+240h+var_278]
0x18001808e  mov     dword ptr [rax], 1
0x180018094  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001809b  mov     rax, [rbp+240h+var_278]
0x18001809f  mov     ebx, [rax]
0x1800180a1  jnz     loc_180019159
0x1800180a7  lea     rcx, [rbp+240h+var_2A0]; Frame
0x1800180ab  call    cs:__imp_RtlPopFrame
0x1800180b2  nop     dword ptr [rax+rax+00h]
0x1800180b7  test    ebx, ebx
0x1800180b9  jz      loc_18001919E
0x1800180bf  xor     ecx, ecx; dwErrCode
0x1800180c1  call    cs:__imp_SetLastError
0x1800180c8  nop     dword ptr [rax+rax+00h]
0x1800180cd  lea     rax, qword_18006CF80
0x1800180d4  mov     [rbp+240h+var_268.Flags], 1
0x1800180db  mov     [rbp+240h+var_268.Context], rax
0x1800180df  lea     rcx, [rbp+240h+var_268]; Frame
0x1800180e3  lea     rax, [rbp+240h+var_2B8]
0x1800180e7  mov     [rbp+240h+var_250], 20737853h
0x1800180ef  xor     ebx, ebx
0x1800180f1  mov     [rbp+240h+var_240], rax
0x1800180f5  mov     [rbp+240h+var_2B8], ebx
0x1800180f8  mov     [rbp+240h+var_268.Previous], rbx
0x1800180fc  mov     [rbp+240h+var_248], 11Bh
0x180018103  call    cs:__imp_RtlPushFrame
0x18001810a  nop     dword ptr [rax+rax+00h]
0x18001810f  cmp     cs:g_FusionEnterExitTracingEnabled, bl
0x180018115  jnz     loc_180018FA1
0x18001811b  cmp     qword ptr [rdi], 0
0x18001811f  mov     [rbp+240h+var_238], rbx
0x180018123  mov     [rbp+240h+var_2C0], rbx
0x180018127  jz      loc_1800191B9
0x18001812d  xor     ecx, ecx; dwErrCode
0x18001812f  call    cs:__imp_SetLastError
0x180018136  nop     dword ptr [rax+rax+00h]
0x18001813b  mov     rdx, [rdi]; struct _ASSEMBLY_IDENTITY *
0x18001813e  lea     rax, [rbp+240h+var_2C0]
0x180018142  lea     r9, [rbp+240h+var_238]; unsigned __int16 **
0x180018146  mov     [rsp+340h+var_320], rax; unsigned __int64 *
0x18001814b  lea     r8, s_IdentityAttribute_language; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180018152  mov     ecx, 1; unsigned int
0x180018157  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18001815c  test    eax, eax
0x18001815e  jz      loc_1800191D9
0x180018164  cmp     [rbp+240h+var_2C0], 1
0x180018169  jnz     short loc_180018180
0x18001816b  mov     rax, [rbp+240h+var_238]
0x18001816f  test    rax, rax
0x180018172  jz      loc_1800191B9
0x180018178  cmp     word ptr [rax], 2Ah ; '*'
0x18001817c  jnz     short loc_180018180
0x18001817e  mov     bl, 1
0x180018180  xor     ecx, ecx; dwErrCode
0x180018182  call    cs:__imp_SetLastError
0x180018189  nop     dword ptr [rax+rax+00h]
0x18001818e  mov     rax, [rbp+240h+var_240]
0x180018192  mov     dword ptr [rax], 1
0x180018198  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18001819f  mov     rax, [rbp+240h+var_240]
0x1800181a3  mov     edi, [rax]
0x1800181a5  jnz     loc_1800191F4
0x1800181ab  lea     rcx, [rbp+240h+var_268]; Frame
0x1800181af  call    cs:__imp_RtlPopFrame
0x1800181b6  nop     dword ptr [rax+rax+00h]
0x1800181bb  test    edi, edi
0x1800181bd  jz      loc_180019239
0x1800181c3  test    bl, bl
0x1800181c5  jz      loc_18001901C
0x1800181cb  xor     edi, edi
0x1800181cd  mov     r13d, edi
0x1800181d0  cmp     r13d, [r14+10h]
0x1800181d4  jnb     loc_180018AD0
0x1800181da  test    r15b, r15b
0x1800181dd  jnz     loc_18001890B
0x1800181e3  xor     ecx, ecx; dwErrCode
0x1800181e5  call    cs:__imp_SetLastError
0x1800181ec  nop     dword ptr [rax+rax+00h]
0x1800181f1  mov     rax, [r14+20h]
0x1800181f5  mov     ecx, r13d
0x1800181f8  mov     [rbp+240h+var_2B8], edi
0x1800181fb  mov     [rbp+240h+var_2A0.Flags], 1
0x180018202  mov     [rbp+240h+var_2A0.Previous], rdi
0x180018206  mov     ebx, [rax+rcx*4]
0x180018209  lea     r12, ds:0[rcx*8]
0x180018211  mov     rax, [r14+18h]
0x180018215  lea     rcx, [rbp+240h+var_2A0]; Frame
0x180018219  mov     [rbp+240h+var_288], 20737853h
0x180018221  mov     [rbp+240h+var_280], 0D2h
0x180018228  mov     r15, [r12+rax]
0x18001822c  lea     rax, ?__stc@?1??Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)'::`2'::__stc
0x180018233  mov     [rbp+240h+var_2A0.Context], rax
0x180018237  lea     rax, [rbp+240h+var_2B8]
0x18001823b  mov     [rbp+240h+var_278], rax
0x18001823f  call    cs:__imp_RtlPushFrame
0x180018246  nop     dword ptr [rax+rax+00h]
0x18001824b  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180018252  jnz     loc_180018F21
0x180018258  cmp     [rbp+240h+var_1D8], 0
0x18001825c  jnz     loc_18001937C
0x180018262  xor     ecx, ecx; dwErrCode
0x180018264  call    cs:__imp_SetLastError
0x18001826b  nop     dword ptr [rax+rax+00h]
0x180018270  lea     rsi, [rbx+1]
0x180018274  mov     rdi, rbx
0x180018277  cmp     rsi, [rbp+240h+var_1C8]
0x18001827b  ja      loc_180018E66
0x180018281  xor     ecx, ecx; dwErrCode
0x180018283  call    cs:__imp_SetLastError
0x18001828a  nop     dword ptr [rax+rax+00h]
0x18001828f  mov     rax, [rbp+240h+var_1C8]
0x180018293  test    rax, rax
0x180018296  jz      short loc_1800182C8
0x180018298  mov     rsi, [rbp+240h+Src]
0x18001829c  test    r15, r15
0x18001829f  jz      loc_180018F47
0x1800182a5  cmp     rdi, rax
0x1800182a8  jnb     loc_1800193B7
0x1800182ae  mov     rbx, rdi
0x1800182b1  add     rbx, rbx
0x1800182b4  mov     rdx, r15; Src
0x1800182b7  mov     r8, rbx; Size
0x1800182ba  mov     rcx, rsi; void *
0x1800182bd  call    memcpy_0
0x1800182c2  xor     eax, eax
0x1800182c4  mov     [rsi+rbx], ax
0x1800182c8  xor     ecx, ecx; dwErrCode
0x1800182ca  mov     [rbp+240h+var_1C0], rdi
0x1800182d1  call    cs:__imp_SetLastError
0x1800182d8  nop     dword ptr [rax+rax+00h]
0x1800182dd  mov     rax, [rbp+240h+var_278]
0x1800182e1  mov     dword ptr [rax], 1
0x1800182e7  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x1800182ee  mov     rax, [rbp+240h+var_278]
0x1800182f2  mov     ebx, [rax]
0x1800182f4  jnz     loc_1800193C0
0x1800182fa  lea     rcx, [rbp+240h+var_2A0]; Frame
0x1800182fe  call    cs:__imp_RtlPopFrame
0x180018305  nop     dword ptr [rax+rax+00h]
0x18001830a  test    ebx, ebx
0x18001830c  jz      loc_180019599
0x180018312  xor     ecx, ecx; dwErrCode
0x180018314  call    cs:__imp_SetLastError
0x18001831b  nop     dword ptr [rax+rax+00h]
0x180018320  lea     rax, qword_18006CEC0
0x180018327  mov     [rbp+240h+var_2A0.Flags], 1
0x18001832e  mov     [rbp+240h+var_2A0.Context], rax
0x180018332  lea     rcx, [rbp+240h+var_2A0]; Frame
0x180018336  lea     rax, [rbp+240h+var_2C0]
0x18001833a  mov     [rbp+240h+var_288], 20737853h
0x180018342  xor     r15d, r15d
0x180018345  mov     [rbp+240h+var_278], rax
0x180018349  mov     dword ptr [rbp+240h+var_2C0], r15d
0x18001834d  mov     [rbp+240h+var_2A0.Previous], r15
0x180018351  mov     [rbp+240h+var_280], 0E6h
0x180018358  call    cs:__imp_RtlPushFrame
0x18001835f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
