# IsGameManager::GetGameRelated(ulong,ulong *,KnownGameList::GMRelatedProcess * *)

- ea: `0x180017410`
- end: `0x18001777b`
- name: `?GetGameRelated@IsGameManager@@UEAAJKPEAKPEAPEAUGMRelatedProcess@KnownGameList@@@Z`
- size: `875`
- prototype: `__int64 __fastcall(IsGameManager *__hidden this, unsigned int, unsigned int *, struct KnownGameList::GMRelatedProcess **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180017410`
- `0x180017784`
- `0x180017fcc`
- `0x1800237c8`
- `0x180031c70`
- `0x1800c0170`
- `0x1802789e0`
- `0x18027de60`
- `0x18027e52c`
- `0x180356360`
- `0x180356edc`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001758b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001757d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001758b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001774d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017623`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180017737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18001774d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001776b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001776b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017773`

## string_xrefs

- `0x18001749b`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x1800175be`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x180017655`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x1800176c6`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
__int64 __fastcall IsGameManager::GetGameRelated(
        IsGameManager *this,
        unsigned int a2,
        unsigned int *a3,
        struct KnownGameList::GMRelatedProcess **a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 *v11; // rcx
  unsigned int v12; // r15d
  __int64 v13; // rax
  unsigned int v14; // esi
  int StringFromGameConfigStore; // eax
  __int64 v16; // rdx
  HSTRING v17; // rdi
  int GlobalStringFromGameConfigStore; // eax
  HSTRING v19; // rbx
  unsigned int v20; // r12d
  HSTRING v21; // rdi
  void *v22; // rcx
  void *v23; // rcx
  UINT32 StringLen; // ebx
  AutoGameProfile *StringRawBuffer; // rax
  int GameRelatedFromGcsData; // eax
  UINT32 v27; // esi
  AutoGameProfile *v28; // rax
  int v29; // eax
  void *v30; // rcx
  _QWORD *v31; // rax
  void *v32; // rcx
  char *v33; // r14
  struct KnownGameList::GMRelatedProcess **v34; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v36; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v39; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v42; // [rsp+70h] [rbp-90h]
  struct KnownGameList::GMRelatedProcess **v43; // [rsp+80h] [rbp-80h]
  _BYTE v44[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v45; // [rsp+92h] [rbp-6Eh]
  _BYTE Source[620]; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v47; // [rsp+300h] [rbp+200h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v43 = a4;
  memset_0(v44, 0, 0x270u);
  v38 = 624;
  *a3 = 0;
  *a4 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
         *((_QWORD *)this + 2),
         4,
         v44,
         &v38);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 542;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)v8,
      (int)v34);
    return v8;
  }
  if ( v38 > 0x270 )
  {
    v8 = -2147418113;
    v9 = 544;
    goto LABEL_3;
  }
  v11 = (__int64 *)*((_QWORD *)this + 2);
  pv = 0;
  v47 = xmmword_180769B30;
  v36 = 0;
  v12 = 0;
  v13 = *v11;
  v14 = 0;
  v39 = 0;
  v40 = 0;
  if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int128 *))(v13 + 32))(v11, a2, &v47) >= 0 )
  {
    *(_OWORD *)v41 = v47;
    string = 0;
    StringFromGameConfigStore = IsGameManager::GetStringFromGameConfigStore(this, v41, 22, &string);
    v17 = string;
    if ( StringFromGameConfigStore >= 0 && WindowsGetStringLen(string) )
    {
      *(_QWORD *)&v41[2] = 0;
      *(_QWORD *)v41 = &pv;
      v42 = 1;
      StringLen = WindowsGetStringLen(v17);
      StringRawBuffer = (AutoGameProfile *)WindowsGetStringRawBuffer(v17, 0);
      GameRelatedFromGcsData = AutoGameProfile::GetGameRelatedFromGcsData(
                                 StringRawBuffer,
                                 (const unsigned __int16 *)StringLen,
                                 (unsigned int)&v39,
                                 &v41[2],
                                 v34);
      if ( GameRelatedFromGcsData < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)GameRelatedFromGcsData,
          (int)v34);
      wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v41);
      v12 = v39;
    }
    string = 0;
    GlobalStringFromGameConfigStore = IsGameManager::GetGlobalStringFromGameConfigStore(this, v16, &string);
    v19 = string;
    if ( GlobalStringFromGameConfigStore >= 0 && WindowsGetStringLen(string) )
    {
      *(_QWORD *)&v41[2] = 0;
      *(_QWORD *)v41 = &v36;
      v42 = 1;
      v27 = WindowsGetStringLen(v19);
      v28 = (AutoGameProfile *)WindowsGetStringRawBuffer(v19, 0);
      v29 = AutoGameProfile::GetGameRelatedFromGcsData(
              v28,
              (const unsigned __int16 *)v27,
              (unsigned int)&v40,
              &v41[2],
              v34);
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x23D,
          (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
          (const char *)(unsigned int)v29,
          (int)v34);
      wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(v41);
      v14 = v40;
    }
    if ( v19 )
      WindowsDeleteString(v19);
    if ( v17 )
      WindowsDeleteString(v17);
  }
  v20 = v12 + v14 + v45;
  wil::make_unique_cotaskmem_nothrow<KnownGameList::GMRelatedProcess [0]>(&string, v20);
  v21 = string;
  if ( !string )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x244,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)0x8007000ELL,
      (int)v34);
    v22 = v36;
    v36 = 0;
    if ( v22 )
      CoTaskMemFree(v22);
    v23 = pv;
    pv = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    return v8;
  }
  memcpy_s_0(string, 62LL * v45, Source, 62LL * v45);
  v33 = (char *)v21 + 62 * v45;
  if ( v12 )
  {
    memcpy_s_0((char *)v21 + 62 * v45, 62LL * v12, pv, 62LL * v12);
    v33 += 62 * v12;
  }
  if ( v14 )
    memcpy_s_0(v33, 62LL * v14, v36, 62LL * v14);
  v30 = v36;
  v31 = v43;
  *a3 = v20;
  v36 = 0;
  *v31 = v21;
  if ( v30 )
    CoTaskMemFree(v30);
  v32 = pv;
  pv = 0;
  if ( v32 )
    CoTaskMemFree(v32);
  return 0;
}

```

## disassembly

```asm
0x180017410  push    rbp
0x180017412  push    rbx
0x180017413  push    rsi
0x180017414  push    rdi
0x180017415  push    r12
0x180017417  push    r13
0x180017419  push    r14
0x18001741b  push    r15
0x18001741d  lea     rbp, [rsp-228h]
0x180017425  sub     rsp, 328h
0x18001742c  mov     rax, cs:__security_cookie
0x180017433  xor     rax, rsp
0x180017436  mov     [rbp+260h+var_50], rax
0x18001743d  mov     rbx, r9
0x180017440  mov     r13, r8
0x180017443  mov     edi, edx
0x180017445  mov     [rbp+260h+var_2E0], rbx
0x180017449  mov     r14, rcx
0x18001744c  mov     esi, 270h
0x180017451  mov     r8d, esi; Size
0x180017454  lea     rcx, [rbp+260h+var_2D0]; void *
0x180017458  xor     edx, edx; Val
0x18001745a  call    memset_0
0x18001745f  xor     r12d, r12d
0x180017462  mov     [rsp+360h+var_318], esi
0x180017466  mov     [r13+0], r12d
0x18001746a  lea     r9, [rsp+360h+var_318]
0x18001746f  mov     [rbx], r12
0x180017472  lea     r8, [rbp+260h+var_2D0]
0x180017476  mov     rcx, [r14+10h]
0x18001747a  lea     edx, [r12+4]
0x18001747f  mov     rax, [rcx]
0x180017482  mov     rax, [rax+50h]
0x180017486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001748b  mov     ebx, eax
0x18001748d  test    eax, eax
0x18001748f  jns     short loc_1800174CF
0x180017491  lea     edx, [rsi-52h]; void *
0x180017494  mov     rcx, [rbp+268h]; this
0x18001749b  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1800174a2  mov     r9d, ebx; char *
0x1800174a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174aa  mov     eax, ebx
0x1800174ac  mov     rcx, [rbp+260h+var_50]
0x1800174b3  xor     rcx, rsp; StackCookie
0x1800174b6  call    __security_check_cookie
0x1800174bb  add     rsp, 328h
0x1800174c2  pop     r15
0x1800174c4  pop     r14
0x1800174c6  pop     r13
0x1800174c8  pop     r12
0x1800174ca  pop     rdi
0x1800174cb  pop     rsi
0x1800174cc  pop     rbx
0x1800174cd  pop     rbp
0x1800174ce  retn
0x1800174cf  cmp     [rsp+360h+var_318], esi
0x1800174d3  ja      loc_180017725
0x1800174d9  movups  xmm0, cs:xmmword_180769B30
0x1800174e0  mov     rcx, [r14+10h]
0x1800174e4  lea     r8, [rbp+260h+var_60]
0x1800174eb  mov     [rsp+360h+pv], r12
0x1800174f0  mov     edx, edi
0x1800174f2  movdqu  [rbp+260h+var_60], xmm0
0x1800174fa  mov     [rsp+360h+var_328], r12
0x1800174ff  mov     r15d, r12d
0x180017502  mov     rax, [rcx]
0x180017505  mov     esi, r12d
0x180017508  mov     [rsp+360h+var_314], r12d
0x18001750d  mov     [rsp+360h+var_310], r12d
0x180017512  mov     rax, [rax+20h]
0x180017516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001751b  test    eax, eax
0x18001751d  js      short loc_180017591
0x18001751f  movaps  xmm0, [rbp+260h+var_60]
0x180017526  lea     r9, [rsp+360h+string]
0x18001752b  mov     r8d, 16h
0x180017531  movdqa  xmmword ptr [rsp+360h+var_300], xmm0
0x180017537  lea     rdx, [rsp+360h+var_300]
0x18001753c  mov     [rsp+360h+string], r12
0x180017541  mov     rcx, r14
0x180017544  call    ?GetStringFromGameConfigStore@IsGameManager@@AEAAJU_GUID@@W4GameProperty_t@ExecutionModel@@PEAVString@Internal@Windows@@@Z; IsGameManager::GetStringFromGameConfigStore(_GUID,ExecutionModel::GameProperty_t,Windows::Internal::String *)
0x180017549  mov     rdi, [rsp+360h+string]
0x18001754e  test    eax, eax
0x180017550  jns     loc_180017734
0x180017556  lea     r8, [rsp+360h+string]
0x18001755b  mov     [rsp+360h+string], r12
0x180017560  mov     rcx, r14
0x180017563  call    ?GetGlobalStringFromGameConfigStore@IsGameManager@@AEAAJW4GlobalProperty_t@ExecutionModel@@PEAVString@Internal@Windows@@@Z; IsGameManager::GetGlobalStringFromGameConfigStore(ExecutionModel::GlobalProperty_t,Windows::Internal::String *)
0x180017568  mov     rbx, [rsp+360h+string]
0x18001756d  test    eax, eax
0x18001756f  jns     loc_18001774A
0x180017575  test    rbx, rbx
0x180017578  jz      short loc_180017583
0x18001757a  mov     rcx, rbx; string
0x18001757d  call    cs:__imp_WindowsDeleteString
0x180017583  test    rdi, rdi
0x180017586  jz      short loc_180017591
0x180017588  mov     rcx, rdi; string
0x18001758b  call    cs:__imp_WindowsDeleteString
0x180017591  movzx   r12d, [rbp+260h+var_2CE]
0x180017596  lea     rcx, [rsp+360h+string]
0x18001759b  add     r12d, esi
0x18001759e  add     r12d, r15d
0x1800175a1  mov     edx, r12d
0x1800175a4  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@UGMRelatedProcess@KnownGameList@@@wil@@YA?AV?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<KnownGameList::GMRelatedProcess [0]>(unsigned __int64)
0x1800175a9  mov     rdi, [rsp+360h+string]
0x1800175ae  test    rdi, rdi
0x1800175b1  jnz     loc_1806EC3B4
0x1800175b7  mov     rcx, [rbp+268h]; this
0x1800175be  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1800175c5  mov     ebx, 8007000Eh
0x1800175ca  mov     edx, 244h; void *
0x1800175cf  mov     r9d, ebx; char *
0x1800175d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800175d7  mov     rcx, [rsp+360h+var_328]; pv
0x1800175dc  mov     [rsp+360h+var_328], rdi
0x1800175e1  test    rcx, rcx
0x1800175e4  jnz     loc_180017760
0x1800175ea  mov     rcx, [rsp+360h+pv]; pv
0x1800175ef  mov     [rsp+360h+pv], 0
0x1800175f8  test    rcx, rcx
0x1800175fb  jz      loc_1800174AA
0x180017601  call    cs:__imp_CoTaskMemFree
0x180017607  jmp     loc_1800174AA
0x18001760c  lea     rax, [rsp+360h+pv]
0x180017611  mov     qword ptr [rsp+360h+var_300+8], r12
0x180017616  mov     rcx, rdi; string
0x180017619  mov     qword ptr [rsp+360h+var_300], rax
0x18001761e  mov     [rsp+360h+var_2F0], 1
0x180017623  call    cs:__imp_WindowsGetStringLen
0x180017629  xor     edx, edx; length
0x18001762b  mov     rcx, rdi; string
0x18001762e  mov     ebx, eax
0x180017630  call    cs:__imp_WindowsGetStringRawBuffer
0x180017636  lea     r9, [rsp+360h+var_300+8]; unsigned int *
0x18001763b  mov     edx, ebx; unsigned __int16 *
0x18001763d  mov     rcx, rax; this
0x180017640  lea     r8, [rsp+360h+var_314]; unsigned int
0x180017645  call    ?GetGameRelatedFromGcsData@AutoGameProfile@@YAJPEBGKPEAKPEAPEAUGMRelatedProcess@KnownGameList@@@Z; AutoGameProfile::GetGameRelatedFromGcsData(ushort const *,ulong,ulong *,KnownGameList::GMRelatedProcess * *)
0x18001764a  test    eax, eax
0x18001764c  jns     short loc_180017669
0x18001764e  mov     rcx, [rbp+268h]; this
0x180017655  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18001765c  mov     r9d, eax; char *
0x18001765f  mov     edx, 232h; void *
0x180017664  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017669  lea     rcx, [rsp+360h+var_300]
0x18001766e  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180017673  mov     r15d, [rsp+360h+var_314]
0x180017678  jmp     loc_180017556
0x18001767d  lea     rax, [rsp+360h+var_328]
0x180017682  mov     qword ptr [rsp+360h+var_300+8], r12
0x180017687  mov     rcx, rbx; string
0x18001768a  mov     qword ptr [rsp+360h+var_300], rax
0x18001768f  mov     [rsp+360h+var_2F0], 1
0x180017694  call    cs:__imp_WindowsGetStringLen
0x18001769a  xor     edx, edx; length
0x18001769c  mov     rcx, rbx; string
0x18001769f  mov     esi, eax
0x1800176a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800176a7  lea     r9, [rsp+360h+var_300+8]; unsigned int *
0x1800176ac  mov     edx, esi; unsigned __int16 *
0x1800176ae  mov     rcx, rax; this
0x1800176b1  lea     r8, [rsp+360h+var_310]; unsigned int
0x1800176b6  call    ?GetGameRelatedFromGcsData@AutoGameProfile@@YAJPEBGKPEAKPEAPEAUGMRelatedProcess@KnownGameList@@@Z; AutoGameProfile::GetGameRelatedFromGcsData(ushort const *,ulong,ulong *,KnownGameList::GMRelatedProcess * *)
0x1800176bb  test    eax, eax
0x1800176bd  jns     short loc_1800176DA
0x1800176bf  mov     rcx, [rbp+268h]; this
0x1800176c6  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x1800176cd  mov     r9d, eax; char *
0x1800176d0  mov     edx, 23Dh; void *
0x1800176d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800176da  lea     rcx, [rsp+360h+var_300]
0x1800176df  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800176e4  mov     esi, [rsp+360h+var_310]
0x1800176e8  jmp     loc_180017575
0x1800176ed  mov     rcx, [rsp+360h+var_328]; pv
0x1800176f2  mov     rax, [rbp+260h+var_2E0]
0x1800176f6  mov     [r13+0], r12d
0x1800176fa  mov     [rsp+360h+var_328], 0
0x180017703  mov     [rax], rdi
0x180017706  test    rcx, rcx
0x180017709  jnz     short loc_18001776B
0x18001770b  mov     rcx, [rsp+360h+pv]; pv
0x180017710  mov     [rsp+360h+pv], 0
0x180017719  test    rcx, rcx
0x18001771c  jnz     short loc_180017773
0x18001771e  xor     eax, eax
0x180017720  jmp     loc_1800174AC
0x180017725  mov     ebx, 8000FFFFh
0x18001772a  mov     edx, 220h
0x18001772f  jmp     loc_180017494
0x180017734  mov     rcx, rdi; string
0x180017737  call    cs:__imp_WindowsGetStringLen
0x18001773d  test    eax, eax
0x18001773f  jz      loc_180017556
0x180017745  jmp     loc_18001760C
0x18001774a  mov     rcx, rbx; string
0x18001774d  call    cs:__imp_WindowsGetStringLen
0x180017753  test    eax, eax
0x180017755  jz      loc_180017575
0x18001775b  jmp     loc_18001767D
0x180017760  call    cs:__imp_CoTaskMemFree
0x180017766  jmp     loc_1800175EA
0x18001776b  call    cs:__imp_CoTaskMemFree
0x180017771  jmp     short loc_18001770B
0x180017773  call    cs:__imp_CoTaskMemFree
0x180017779  jmp     short loc_18001771E
0x1806ec3b4  movzx   eax, [rbp+260h+var_2CE]
0x1806ec3b8  lea     r8, [rbp+260h+Source]; Source
0x1806ec3bc  imul    rdx, rax, 3Eh ; '>'; DestinationSize
0x1806ec3c0  mov     rcx, rdi; Destination
0x1806ec3c3  mov     r9, rdx; SourceSize
0x1806ec3c6  call    memcpy_s_0
0x1806ec3cb  movzx   eax, [rbp+260h+var_2CE]
0x1806ec3cf  imul    r14, rax, 3Eh ; '>'
0x1806ec3d3  add     r14, rdi
0x1806ec3d6  test    r15d, r15d
0x1806ec3d9  jz      short loc_1806EC3F8
0x1806ec3db  mov     r8, [rsp+360h+pv]; Source
0x1806ec3e0  mov     rcx, r14; Destination
0x1806ec3e3  mov     eax, r15d
0x1806ec3e6  imul    rbx, rax, 3Eh ; '>'
0x1806ec3ea  mov     r9, rbx; SourceSize
0x1806ec3ed  mov     rdx, rbx; DestinationSize
0x1806ec3f0  call    memcpy_s_0
0x1806ec3f5  add     r14, rbx
0x1806ec3f8  test    esi, esi
0x1806ec3fa  jz      loc_1800176ED
0x1806ec400  mov     r8, [rsp+360h+var_328]; Source
0x1806ec405  mov     rcx, r14; Destination
0x1806ec408  mov     eax, esi
0x1806ec40a  imul    rdx, rax, 3Eh ; '>'; DestinationSize
0x1806ec40e  mov     r9, rdx; SourceSize
0x1806ec411  call    memcpy_s_0
0x1806ec416  nop
0x1806ec417  jmp     loc_1800176ED
```
