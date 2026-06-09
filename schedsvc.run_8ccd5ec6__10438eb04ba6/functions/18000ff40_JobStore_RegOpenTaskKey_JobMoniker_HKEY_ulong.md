# JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)

- ea: `0x18000ff40`
- end: `0x18001037b`
- name: `?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z`
- size: `1083`
- prototype: `__int64 __fastcall(JobStore *__hidden this, struct JobMoniker *, HKEY *, unsigned int)`
- caller_count: `11`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000495c`
- `0x1800104c0`
- `0x180011ed0`
- `0x1800141e0`
- `0x18001d7ac`
- `0x18001e06c`
- `0x180023c4c`
- `0x180027990`
- `0x1800457fc`
- `0x18004e9d0`
- `0x18007103c`

## callees

- `0x18000ff40`
- `0x18002b210`
- `0x18002c2f4`
- `0x18002db40`
- `0x18002db74`
- `0x1800529a0`
- `0x180056714`
- `0x180067290`
- `0x1800829ee`
- `0x180082a40`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010168`
- `msvcrt!memcpy_s` at `0x18001018c`
- `msvcrt!memcpy_s` at `0x180010168`
- `msvcrt!memcpy_s` at `0x18001018c`
- `OLEAUT32!__imp_SysAllocString` at `0x180010094`
- `OLEAUT32!__imp_SysAllocString` at `0x180010094`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001012b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001012b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180010220`
- `OLEAUT32!__imp_SysFreeString` at `0x18001028a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010346`
- `OLEAUT32!__imp_SysFreeString` at `0x1800101ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180010220`
- `OLEAUT32!__imp_SysFreeString` at `0x18001028a`
- `OLEAUT32!__imp_SysFreeString` at `0x180010346`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ffb9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001010a`
- `OLEAUT32!__imp_SysStringLen` at `0x180010146`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ffb9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001010a`
- `OLEAUT32!__imp_SysStringLen` at `0x180010146`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800101f9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800100d6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800100d6`

## string_xrefs

- `0x18001008d`: `TaskCache\Tasks\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobStore::RegOpenTaskKey(HKEY *this, struct JobMoniker *a2, HKEY *a3, REGSAM a4)
{
  REGSAM v4; // r12d
  HKEY *v5; // r15
  HKEY *v7; // r14
  HKEY v8; // rdi
  GUID v9; // xmm6
  OLECHAR **v10; // rcx
  OLECHAR *v11; // rcx
  UINT v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rbx
  int TreeInfo; // esi
  OLECHAR *v17; // rbx
  __int64 v18; // rsi
  signed int v19; // eax
  __int64 v20; // r15
  signed int v21; // r14d
  BSTR v22; // r12
  errno_t v23; // eax
  errno_t v24; // eax
  signed int v25; // ecx
  LSTATUS v26; // eax
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *Path; // rax
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  JobStore *v32; // [rsp+40h] [rbp-C0h]
  HKEY *v33; // [rsp+48h] [rbp-B8h]
  GUID Buf2; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  struct _GUID v36; // [rsp+70h] [rbp-90h] BYREF
  GUID rguid; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int128 v40; // [rsp+B0h] [rbp-50h]
  _BYTE v41[30]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = a4;
  v5 = a3;
  v33 = a3;
  v7 = this;
  v32 = (JobStore *)this;
  v8 = 0;
  v35 = 0;
  rguid = 0;
  v9 = *(GUID *)a2;
  Buf2 = *(GUID *)a2;
  v10 = (OLECHAR **)*((_QWORD *)a2 + 2);
  if ( v10 && ((v11 = *v10) == 0 ? (v12 = 0) : (v12 = SysStringLen(v11)), v12) )
  {
    v13 = (__int64 *)*((_QWORD *)a2 + 2);
    if ( v13 )
      v14 = *v13;
    else
      v14 = 0;
    v15 = (const unsigned __int16 *)(v14 + 14);
  }
  else
  {
    v15 = 0;
  }
  v36 = 0;
  if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
  {
    TreeInfo = JobStore::RegGetTreeInfo((JobStore *)v7, v15, &v36, 0);
    if ( TreeInfo < 0 )
      return (unsigned int)TreeInfo;
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v9 = v36;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        Path = JobMoniker::GetPath(a2);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, Path);
      }
    }
    else if ( memcmp_0(&Buf2, &v36, 0x10u) )
    {
      return (unsigned int)-2147216621;
    }
  }
  rguid = v9;
  v17 = SysAllocString(L"TaskCache\\Tasks\\");
  *(_QWORD *)&v36.Data1 = v17;
  if ( !v17 )
    ATL::PrivateAtlThrow(0x8007000E);
  *(_OWORD *)sz = 0;
  v39 = 0;
  v40 = 0;
  memset(v41, 0, sizeof(v41));
  if ( !StringFromGUID2(&rguid, sz, 39) )
  {
    SysFreeString(v17);
    return (unsigned int)-2147024774;
  }
  v18 = -1;
  do
    ++v18;
  while ( sz[v18] );
  if ( (_DWORD)v18 )
  {
    v19 = SysStringLen(v17);
    v20 = v19;
    v21 = v19 + v18;
    if ( v19 + (int)v18 < v19 )
    {
      v25 = -2147024882;
      v7 = (HKEY *)v32;
      v5 = v33;
      goto LABEL_26;
    }
    v22 = SysAllocStringLen(0, v21);
    if ( !v22 )
    {
      v25 = -2147024882;
      v7 = (HKEY *)v32;
      v5 = v33;
      v4 = a4;
      goto LABEL_26;
    }
    if ( SysStringLen(v17) )
    {
      v23 = memcpy_s(v22, 2LL * v21, v17, 2 * v20);
      ATL::AtlCrtErrorCheck(v23);
    }
    v24 = memcpy_s(&v22[v20], 2LL * (int)v18, sz, 2LL * (int)v18);
    ATL::AtlCrtErrorCheck(v24);
    v22[v21] = 0;
    SysFreeString(v17);
    v17 = v22;
    *(_QWORD *)&v36.Data1 = v22;
    v7 = (HKEY *)v32;
    v5 = v33;
    v4 = a4;
  }
  v25 = 0;
LABEL_26:
  if ( v25 < 0 )
    ATL::PrivateAtlThrow(v25);
  phkResult = 0;
  v26 = RegOpenKeyExW(v7[2], v17, 0, v4, &phkResult);
  TreeInfo = v26;
  if ( !v26 )
  {
    v8 = phkResult;
    phkResult = 0;
    SysFreeString(v17);
LABEL_29:
    *v5 = v8;
    return (unsigned int)TreeInfo;
  }
  if ( v26 > 0 )
    TreeInfo = (unsigned __int16)v26 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = JobMoniker::GetPath(a2);
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)v17,
      (__int64)v28,
      TreeInfo);
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
  SysFreeString(v17);
  if ( TreeInfo >= 0 )
    goto LABEL_29;
  return (unsigned int)TreeInfo;
}

```

## disassembly

```asm
0x18000ff40  push    rbp
0x18000ff42  push    rbx
0x18000ff43  push    rsi
0x18000ff44  push    rdi
0x18000ff45  push    r12
0x18000ff47  push    r13
0x18000ff49  push    r14
0x18000ff4b  push    r15
0x18000ff4d  lea     rbp, [rsp-8]
0x18000ff52  sub     rsp, 108h
0x18000ff59  movaps  [rsp+140h+var_50], xmm6
0x18000ff61  mov     rax, cs:__security_cookie
0x18000ff68  xor     rax, rsp
0x18000ff6b  mov     [rbp+40h+var_60], rax
0x18000ff6f  mov     r12d, r9d
0x18000ff72  mov     [rsp+140h+var_110], r9d
0x18000ff77  mov     r15, r8
0x18000ff7a  mov     [rsp+140h+var_F8], r8
0x18000ff7f  mov     r13, rdx
0x18000ff82  mov     r14, rcx
0x18000ff85  mov     [rsp+140h+var_100], rcx
0x18000ff8a  xor     edi, edi
0x18000ff8c  mov     [rsp+140h+var_E0], rdi
0x18000ff91  xorps   xmm0, xmm0
0x18000ff94  movups  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x18000ff98  movups  xmm6, xmmword ptr [rdx]
0x18000ff9b  movaps  [rsp+140h+Buf2], xmm6
0x18000ffa0  mov     rcx, [rdx+10h]
0x18000ffa4  test    rcx, rcx
0x18000ffa7  jz      loc_18001025A
0x18000ffad  mov     rcx, [rcx]; pbstr
0x18000ffb0  test    rcx, rcx
0x18000ffb3  jz      loc_1800102FB
0x18000ffb9  call    cs:__imp_SysStringLen
0x18000ffc0  nop     dword ptr [rax+rax+00h]
0x18000ffc5  test    eax, eax
0x18000ffc7  jz      loc_18001025A
0x18000ffcd  mov     rax, [r13+10h]
0x18000ffd1  test    rax, rax
0x18000ffd4  jz      loc_180010261
0x18000ffda  mov     rcx, [rax]
0x18000ffdd  lea     rbx, [rcx+0Eh]
0x18000ffe1  xorps   xmm0, xmm0
0x18000ffe4  movups  xmmword ptr [rsp+140h+var_D0.Data1], xmm0
0x18000ffe9  mov     r8d, 10h; Size
0x18000ffef  lea     rdx, [rsp+140h+Buf2]; Buf2
0x18000fff4  lea     rcx, GUID_NULL; Buf1
0x18000fffb  call    memcmp_0
0x180010000  test    eax, eax
0x180010002  jnz     loc_180010088
0x180010008  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18001000b  lea     r8, [rsp+140h+var_D0]; struct _GUID *
0x180010010  mov     rdx, rbx; unsigned __int16 *
0x180010013  mov     rcx, r14; this
0x180010016  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18001001b  mov     esi, eax
0x18001001d  test    eax, eax
0x18001001f  js      loc_18001022F
0x180010025  mov     r8d, 10h; Size
0x18001002b  lea     rdx, [rsp+140h+Buf2]; Buf2
0x180010030  lea     rcx, GUID_NULL; Buf1
0x180010037  call    memcmp_0
0x18001003c  test    eax, eax
0x18001003e  jz      short loc_180010063
0x180010040  mov     r8d, 10h; Size
0x180010046  lea     rdx, [rsp+140h+var_D0]; Buf2
0x18001004b  lea     rcx, [rsp+140h+Buf2]; Buf1
0x180010050  call    memcmp_0
0x180010055  test    eax, eax
0x180010057  jz      short loc_180010088
0x180010059  mov     esi, 80041313h
0x18001005e  jmp     loc_18001022F
0x180010063  movaps  xmm6, xmmword ptr [rsp+140h+var_D0.Data1]
0x180010068  mov     rax, cs:WPP_GLOBAL_Control
0x18001006f  lea     rcx, WPP_GLOBAL_Control
0x180010076  cmp     rax, rcx
0x180010079  jz      short loc_180010088
0x18001007b  test    dword ptr [rax+1Ch], 40000h
0x180010082  jnz     loc_180010302
0x180010088  movdqa  xmmword ptr [rbp+40h+rguid.Data1], xmm6
0x18001008d  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x180010094  call    cs:__imp_SysAllocString
0x18001009b  nop     dword ptr [rax+rax+00h]
0x1800100a0  mov     rbx, rax
0x1800100a3  mov     qword ptr [rsp+140h+var_D0.Data1], rax
0x1800100a8  test    rax, rax
0x1800100ab  jz      loc_180010338
0x1800100b1  xorps   xmm0, xmm0
0x1800100b4  movups  xmmword ptr [rbp+40h+sz], xmm0
0x1800100b8  movups  [rbp+40h+var_A0], xmm0
0x1800100bc  movups  [rbp+40h+var_90], xmm0
0x1800100c0  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x1800100c4  movups  xmmword ptr [rbp+40h+var_80+0Eh], xmm0
0x1800100c8  mov     r8d, 27h ; '''; cchMax
0x1800100ce  lea     rdx, [rbp+40h+sz]; lpsz
0x1800100d2  lea     rcx, [rbp+40h+rguid]; rguid
0x1800100d6  call    cs:__imp_StringFromGUID2
0x1800100dd  nop     dword ptr [rax+rax+00h]
0x1800100e2  test    eax, eax
0x1800100e4  jz      loc_180010343
0x1800100ea  lea     rax, [rbp+40h+sz]
0x1800100ee  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800100f5  inc     rsi
0x1800100f8  cmp     word ptr [rax+rsi*2], 0
0x1800100fd  jnz     short loc_1800100F5
0x1800100ff  test    esi, esi
0x180010101  jz      loc_1800101CF
0x180010107  mov     rcx, rbx; pbstr
0x18001010a  call    cs:__imp_SysStringLen
0x180010111  nop     dword ptr [rax+rax+00h]
0x180010116  movsxd  r15, eax
0x180010119  lea     r14d, [r15+rsi]
0x18001011d  cmp     r14d, r15d
0x180010120  jl      loc_180010268
0x180010126  mov     edx, r14d; ui
0x180010129  xor     ecx, ecx; strIn
0x18001012b  call    cs:__imp_SysAllocStringLen
0x180010132  nop     dword ptr [rax+rax+00h]
0x180010137  mov     r12, rax
0x18001013a  test    rax, rax
0x18001013d  jz      loc_18001035C
0x180010143  mov     rcx, rbx; pbstr
0x180010146  call    cs:__imp_SysStringLen
0x18001014d  nop     dword ptr [rax+rax+00h]
0x180010152  test    eax, eax
0x180010154  jz      short loc_18001017B
0x180010156  mov     r9, r15
0x180010159  add     r9, r9; SourceSize
0x18001015c  movsxd  rdx, r14d
0x18001015f  add     rdx, rdx; DestinationSize
0x180010162  mov     r8, rbx; Source
0x180010165  mov     rcx, r12; Destination
0x180010168  call    cs:__imp_memcpy_s
0x18001016f  nop     dword ptr [rax+rax+00h]
0x180010174  mov     ecx, eax; int
0x180010176  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001017b  movsxd  rdx, esi
0x18001017e  add     rdx, rdx; DestinationSize
0x180010181  lea     rcx, [r12+r15*2]; Destination
0x180010185  mov     r9, rdx; SourceSize
0x180010188  lea     r8, [rbp+40h+sz]; Source
0x18001018c  call    cs:__imp_memcpy_s
0x180010193  nop     dword ptr [rax+rax+00h]
0x180010198  mov     ecx, eax; int
0x18001019a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001019f  movsxd  rcx, r14d
0x1800101a2  xor     eax, eax
0x1800101a4  mov     [r12+rcx*2], ax
0x1800101a9  mov     rcx, rbx; bstrString
0x1800101ac  call    cs:__imp_SysFreeString
0x1800101b3  nop     dword ptr [rax+rax+00h]
0x1800101b8  mov     rbx, r12
0x1800101bb  mov     qword ptr [rsp+140h+var_D0.Data1], rbx
0x1800101c0  mov     r14, [rsp+140h+var_100]
0x1800101c5  mov     r15, [rsp+140h+var_F8]
0x1800101ca  mov     r12d, [rsp+140h+var_110]
0x1800101cf  xor     ecx, ecx; unsigned int
0x1800101d1  test    ecx, ecx
0x1800101d3  js      loc_180010375
0x1800101d9  mov     [rsp+140h+var_108], 0
0x1800101e2  lea     rax, [rsp+140h+var_108]
0x1800101e7  mov     [rsp+140h+phkResult], rax; phkResult
0x1800101ec  mov     r9d, r12d; samDesired
0x1800101ef  xor     r8d, r8d; ulOptions
0x1800101f2  mov     rdx, rbx; lpSubKey
0x1800101f5  mov     rcx, [r14+10h]; hKey
0x1800101f9  call    cs:__imp_RegOpenKeyExW
0x180010200  nop     dword ptr [rax+rax+00h]
0x180010205  mov     esi, eax
0x180010207  test    eax, eax
0x180010209  jnz     loc_18001029C
0x18001020f  mov     rdi, [rsp+140h+var_108]
0x180010214  mov     [rsp+140h+var_108], 0
0x18001021d  mov     rcx, rbx; bstrString
0x180010220  call    cs:__imp_SysFreeString
0x180010227  nop     dword ptr [rax+rax+00h]
0x18001022c  mov     [r15], rdi
0x18001022f  mov     eax, esi
0x180010231  mov     rcx, [rbp+40h+var_60]
0x180010235  xor     rcx, rsp; StackCookie
0x180010238  call    __security_check_cookie
0x18001023d  movaps  xmm6, [rsp+140h+var_50]
0x180010245  add     rsp, 108h
0x18001024c  pop     r15
0x18001024e  pop     r14
0x180010250  pop     r13
0x180010252  pop     r12
0x180010254  pop     rdi
0x180010255  pop     rsi
0x180010256  pop     rbx
0x180010257  pop     rbp
0x180010258  retn
0x18001025a  xor     ebx, ebx
0x18001025c  jmp     loc_18000FFE1
0x180010261  xor     ecx, ecx
0x180010263  jmp     loc_18000FFDD
0x180010268  mov     ecx, 8007000Eh
0x18001026d  mov     r14, [rsp+140h+var_100]
0x180010272  mov     r15, [rsp+140h+var_F8]
0x180010277  jmp     loc_1800101D1
0x18001027c  lea     rcx, [rsp+140h+var_108]; this
0x180010281  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180010286  nop
0x180010287  mov     rcx, rbx; bstrString
0x18001028a  call    cs:__imp_SysFreeString
0x180010291  nop     dword ptr [rax+rax+00h]
0x180010296  test    esi, esi
0x180010298  js      short loc_18001022F
0x18001029a  jmp     short loc_18001022C
0x18001029c  jle     short loc_1800102A7
0x18001029e  movzx   esi, ax
0x1800102a1  or      esi, 80070000h
0x1800102a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800102ae  lea     rcx, WPP_GLOBAL_Control
0x1800102b5  cmp     rax, rcx
0x1800102b8  jz      short loc_18001027C
0x1800102ba  test    dword ptr [rax+1Ch], 40000h
0x1800102c1  jz      short loc_18001027C
0x1800102c3  cmp     byte ptr [rax+19h], 2
0x1800102c7  jb      short loc_18001027C
0x1800102c9  mov     rcx, r13; this
0x1800102cc  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x1800102d1  mov     edx, 2Dh ; '-'
0x1800102d6  mov     [rsp+140h+var_118], esi
0x1800102da  mov     [rsp+140h+phkResult], rax
0x1800102df  mov     r9, rbx
0x1800102e2  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x1800102e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102f0  mov     rcx, [rcx+10h]
0x1800102f4  call    WPP_SF_SSD
0x1800102f9  jmp     short loc_18001027C
0x1800102fb  xor     eax, eax
0x1800102fd  jmp     loc_18000FFC5
0x180010302  cmp     byte ptr [rax+19h], 3
0x180010306  jb      loc_180010088
0x18001030c  mov     rcx, r13; this
0x18001030f  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180010314  mov     edx, 51h ; 'Q'
0x180010319  mov     r9, rax
0x18001031c  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180010323  mov     rcx, cs:WPP_GLOBAL_Control
0x18001032a  mov     rcx, [rcx+10h]
0x18001032e  call    WPP_SF_S
0x180010333  jmp     loc_180010088
0x180010338  mov     ecx, 8007000Eh; unsigned int
0x18001033d  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180010343  mov     rcx, rbx; bstrString
0x180010346  call    cs:__imp_SysFreeString
0x18001034d  nop     dword ptr [rax+rax+00h]
0x180010352  mov     esi, 8007007Ah
0x180010357  jmp     loc_18001022F
0x18001035c  mov     ecx, 8007000Eh
0x180010361  mov     r14, [rsp+140h+var_100]
0x180010366  mov     r15, [rsp+140h+var_F8]
0x18001036b  mov     r12d, [rsp+140h+var_110]
0x180010370  jmp     loc_1800101D1
0x180010375  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
