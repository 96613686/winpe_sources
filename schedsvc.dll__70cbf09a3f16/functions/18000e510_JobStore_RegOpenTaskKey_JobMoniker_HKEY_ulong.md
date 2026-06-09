# JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)

- ea: `0x18000e510`
- end: `0x18000e8fc`
- name: `?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z`
- size: `1004`
- prototype: `__int64 __fastcall(HKEY *this, struct JobMoniker *, HKEY *, REGSAM)`
- caller_count: `11`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x18000c3c0`
- `0x18001b0d0`
- `0x1800213f8`
- `0x180021ca0`
- `0x180023b60`
- `0x180029978`
- `0x18002d7ec`
- `0x1800438bc`
- `0x18004c6d0`
- `0x18006d94c`

## callees

- `0x18000e510`
- `0x18001ec90`
- `0x18001fc54`
- `0x180021300`
- `0x18002132c`
- `0x1800504b4`
- `0x180053e54`
- `0x18006420c`
- `0x18007e67e`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e714`
- `msvcrt!memcpy_s` at `0x18000e732`
- `msvcrt!memcpy_s` at `0x18000e714`
- `msvcrt!memcpy_s` at `0x18000e732`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e65e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e65e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e6e3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000e6e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e74c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e817`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e74c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e7b4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e817`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e8cd`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e589`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6c8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6f8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e589`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6c8`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e6f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e793`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e69a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000e69a`

## string_xrefs

- `0x18000e657`: `TaskCache\Tasks\`

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
0x18000e510  push    rbp
0x18000e512  push    rbx
0x18000e513  push    rsi
0x18000e514  push    rdi
0x18000e515  push    r12
0x18000e517  push    r13
0x18000e519  push    r14
0x18000e51b  push    r15
0x18000e51d  lea     rbp, [rsp-8]
0x18000e522  sub     rsp, 108h
0x18000e529  movaps  [rsp+140h+var_50], xmm6
0x18000e531  mov     rax, cs:__security_cookie
0x18000e538  xor     rax, rsp
0x18000e53b  mov     [rbp+40h+var_60], rax
0x18000e53f  mov     r12d, r9d
0x18000e542  mov     [rsp+140h+var_110], r9d
0x18000e547  mov     r15, r8
0x18000e54a  mov     [rsp+140h+var_F8], r8
0x18000e54f  mov     r13, rdx
0x18000e552  mov     r14, rcx
0x18000e555  mov     [rsp+140h+var_100], rcx
0x18000e55a  xor     edi, edi
0x18000e55c  mov     [rsp+140h+var_E0], rdi
0x18000e561  xorps   xmm0, xmm0
0x18000e564  movups  xmmword ptr [rbp+40h+rguid.Data1], xmm0
0x18000e568  movups  xmm6, xmmword ptr [rdx]
0x18000e56b  movaps  [rsp+140h+Buf2], xmm6
0x18000e570  mov     rcx, [rdx+10h]
0x18000e574  test    rcx, rcx
0x18000e577  jz      loc_18000E7E7
0x18000e57d  mov     rcx, [rcx]; pbstr
0x18000e580  test    rcx, rcx
0x18000e583  jz      loc_18000E882
0x18000e589  call    cs:__imp_SysStringLen
0x18000e58f  test    eax, eax
0x18000e591  jz      loc_18000E7E7
0x18000e597  mov     rax, [r13+10h]
0x18000e59b  test    rax, rax
0x18000e59e  jz      loc_18000E7EE
0x18000e5a4  mov     rcx, [rax]
0x18000e5a7  lea     rbx, [rcx+0Eh]
0x18000e5ab  xorps   xmm0, xmm0
0x18000e5ae  movups  xmmword ptr [rsp+140h+var_D0.Data1], xmm0
0x18000e5b3  mov     r8d, 10h; Size
0x18000e5b9  lea     rdx, [rsp+140h+Buf2]; Buf2
0x18000e5be  lea     rcx, GUID_NULL; Buf1
0x18000e5c5  call    memcmp_0
0x18000e5ca  test    eax, eax
0x18000e5cc  jnz     loc_18000E652
0x18000e5d2  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18000e5d5  lea     r8, [rsp+140h+var_D0]; struct _GUID *
0x18000e5da  mov     rdx, rbx; unsigned __int16 *
0x18000e5dd  mov     rcx, r14; this
0x18000e5e0  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18000e5e5  mov     esi, eax
0x18000e5e7  test    eax, eax
0x18000e5e9  js      loc_18000E7BD
0x18000e5ef  mov     r8d, 10h; Size
0x18000e5f5  lea     rdx, [rsp+140h+Buf2]; Buf2
0x18000e5fa  lea     rcx, GUID_NULL; Buf1
0x18000e601  call    memcmp_0
0x18000e606  test    eax, eax
0x18000e608  jz      short loc_18000E62D
0x18000e60a  mov     r8d, 10h; Size
0x18000e610  lea     rdx, [rsp+140h+var_D0]; Buf2
0x18000e615  lea     rcx, [rsp+140h+Buf2]; Buf1
0x18000e61a  call    memcmp_0
0x18000e61f  test    eax, eax
0x18000e621  jz      short loc_18000E652
0x18000e623  mov     esi, 80041313h
0x18000e628  jmp     loc_18000E7BD
0x18000e62d  movaps  xmm6, xmmword ptr [rsp+140h+var_D0.Data1]
0x18000e632  mov     rax, cs:WPP_GLOBAL_Control
0x18000e639  lea     rcx, WPP_GLOBAL_Control
0x18000e640  cmp     rax, rcx
0x18000e643  jz      short loc_18000E652
0x18000e645  test    dword ptr [rax+1Ch], 40000h
0x18000e64c  jnz     loc_18000E889
0x18000e652  movdqa  xmmword ptr [rbp+40h+rguid.Data1], xmm6
0x18000e657  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x18000e65e  call    cs:__imp_SysAllocString
0x18000e664  mov     rbx, rax
0x18000e667  mov     qword ptr [rsp+140h+var_D0.Data1], rax
0x18000e66c  test    rax, rax
0x18000e66f  jz      loc_18000E8BF
0x18000e675  xorps   xmm0, xmm0
0x18000e678  movups  xmmword ptr [rbp+40h+sz], xmm0
0x18000e67c  movups  [rbp+40h+var_A0], xmm0
0x18000e680  movups  [rbp+40h+var_90], xmm0
0x18000e684  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x18000e688  movups  xmmword ptr [rbp+40h+var_80+0Eh], xmm0
0x18000e68c  mov     r8d, 27h ; '''; cchMax
0x18000e692  lea     rdx, [rbp+40h+sz]; lpsz
0x18000e696  lea     rcx, [rbp+40h+rguid]; rguid
0x18000e69a  call    cs:__imp_StringFromGUID2
0x18000e6a0  test    eax, eax
0x18000e6a2  jz      loc_18000E8CA
0x18000e6a8  lea     rax, [rbp+40h+sz]
0x18000e6ac  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000e6b3  inc     rsi
0x18000e6b6  cmp     word ptr [rax+rsi*2], 0
0x18000e6bb  jnz     short loc_18000E6B3
0x18000e6bd  test    esi, esi
0x18000e6bf  jz      loc_18000E769
0x18000e6c5  mov     rcx, rbx; pbstr
0x18000e6c8  call    cs:__imp_SysStringLen
0x18000e6ce  movsxd  r15, eax
0x18000e6d1  lea     r14d, [r15+rsi]
0x18000e6d5  cmp     r14d, r15d
0x18000e6d8  jl      loc_18000E7F5
0x18000e6de  mov     edx, r14d; ui
0x18000e6e1  xor     ecx, ecx; strIn
0x18000e6e3  call    cs:__imp_SysAllocStringLen
0x18000e6e9  mov     r12, rax
0x18000e6ec  test    rax, rax
0x18000e6ef  jz      loc_18000E8DD
0x18000e6f5  mov     rcx, rbx; pbstr
0x18000e6f8  call    cs:__imp_SysStringLen
0x18000e6fe  test    eax, eax
0x18000e700  jz      short loc_18000E721
0x18000e702  mov     r9, r15
0x18000e705  add     r9, r9; SourceSize
0x18000e708  movsxd  rdx, r14d
0x18000e70b  add     rdx, rdx; DestinationSize
0x18000e70e  mov     r8, rbx; Source
0x18000e711  mov     rcx, r12; Destination
0x18000e714  call    cs:__imp_memcpy_s
0x18000e71a  mov     ecx, eax; int
0x18000e71c  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000e721  movsxd  rdx, esi
0x18000e724  add     rdx, rdx; DestinationSize
0x18000e727  lea     rcx, [r12+r15*2]; Destination
0x18000e72b  mov     r9, rdx; SourceSize
0x18000e72e  lea     r8, [rbp+40h+sz]; Source
0x18000e732  call    cs:__imp_memcpy_s
0x18000e738  mov     ecx, eax; int
0x18000e73a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000e73f  movsxd  rcx, r14d
0x18000e742  xor     eax, eax
0x18000e744  mov     [r12+rcx*2], ax
0x18000e749  mov     rcx, rbx; bstrString
0x18000e74c  call    cs:__imp_SysFreeString
0x18000e752  mov     rbx, r12
0x18000e755  mov     qword ptr [rsp+140h+var_D0.Data1], rbx
0x18000e75a  mov     r14, [rsp+140h+var_100]
0x18000e75f  mov     r15, [rsp+140h+var_F8]
0x18000e764  mov     r12d, [rsp+140h+var_110]
0x18000e769  xor     ecx, ecx; unsigned int
0x18000e76b  test    ecx, ecx
0x18000e76d  js      loc_18000E8F6
0x18000e773  mov     [rsp+140h+var_108], 0
0x18000e77c  lea     rax, [rsp+140h+var_108]
0x18000e781  mov     [rsp+140h+phkResult], rax; phkResult
0x18000e786  mov     r9d, r12d; samDesired
0x18000e789  xor     r8d, r8d; ulOptions
0x18000e78c  mov     rdx, rbx; lpSubKey
0x18000e78f  mov     rcx, [r14+10h]; hKey
0x18000e793  call    cs:__imp_RegOpenKeyExW
0x18000e799  mov     esi, eax
0x18000e79b  test    eax, eax
0x18000e79d  jnz     loc_18000E823
0x18000e7a3  mov     rdi, [rsp+140h+var_108]
0x18000e7a8  mov     [rsp+140h+var_108], 0
0x18000e7b1  mov     rcx, rbx; bstrString
0x18000e7b4  call    cs:__imp_SysFreeString
0x18000e7ba  mov     [r15], rdi
0x18000e7bd  mov     eax, esi
0x18000e7bf  mov     rcx, [rbp+40h+var_60]
0x18000e7c3  xor     rcx, rsp; StackCookie
0x18000e7c6  call    __security_check_cookie
0x18000e7cb  movaps  xmm6, [rsp+140h+var_50]
0x18000e7d3  add     rsp, 108h
0x18000e7da  pop     r15
0x18000e7dc  pop     r14
0x18000e7de  pop     r13
0x18000e7e0  pop     r12
0x18000e7e2  pop     rdi
0x18000e7e3  pop     rsi
0x18000e7e4  pop     rbx
0x18000e7e5  pop     rbp
0x18000e7e6  retn
0x18000e7e7  xor     ebx, ebx
0x18000e7e9  jmp     loc_18000E5AB
0x18000e7ee  xor     ecx, ecx
0x18000e7f0  jmp     loc_18000E5A7
0x18000e7f5  mov     ecx, 8007000Eh
0x18000e7fa  mov     r14, [rsp+140h+var_100]
0x18000e7ff  mov     r15, [rsp+140h+var_F8]
0x18000e804  jmp     loc_18000E76B
0x18000e809  lea     rcx, [rsp+140h+var_108]; this
0x18000e80e  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000e813  nop
0x18000e814  mov     rcx, rbx; bstrString
0x18000e817  call    cs:__imp_SysFreeString
0x18000e81d  test    esi, esi
0x18000e81f  js      short loc_18000E7BD
0x18000e821  jmp     short loc_18000E7BA
0x18000e823  jle     short loc_18000E82E
0x18000e825  movzx   esi, ax
0x18000e828  or      esi, 80070000h
0x18000e82e  mov     rax, cs:WPP_GLOBAL_Control
0x18000e835  lea     rcx, WPP_GLOBAL_Control
0x18000e83c  cmp     rax, rcx
0x18000e83f  jz      short loc_18000E809
0x18000e841  test    dword ptr [rax+1Ch], 40000h
0x18000e848  jz      short loc_18000E809
0x18000e84a  cmp     byte ptr [rax+19h], 2
0x18000e84e  jb      short loc_18000E809
0x18000e850  mov     rcx, r13; this
0x18000e853  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18000e858  mov     edx, 2Dh ; '-'
0x18000e85d  mov     [rsp+140h+var_118], esi
0x18000e861  mov     [rsp+140h+phkResult], rax
0x18000e866  mov     r9, rbx
0x18000e869  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18000e870  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e877  mov     rcx, [rcx+10h]
0x18000e87b  call    WPP_SF_SSD
0x18000e880  jmp     short loc_18000E809
0x18000e882  xor     eax, eax
0x18000e884  jmp     loc_18000E58F
0x18000e889  cmp     byte ptr [rax+19h], 3
0x18000e88d  jb      loc_18000E652
0x18000e893  mov     rcx, r13; this
0x18000e896  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18000e89b  mov     edx, 51h ; 'Q'
0x18000e8a0  mov     r9, rax
0x18000e8a3  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18000e8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8b1  mov     rcx, [rcx+10h]
0x18000e8b5  call    WPP_SF_S
0x18000e8ba  jmp     loc_18000E652
0x18000e8bf  mov     ecx, 8007000Eh; unsigned int
0x18000e8c4  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18000e8ca  mov     rcx, rbx; bstrString
0x18000e8cd  call    cs:__imp_SysFreeString
0x18000e8d3  mov     esi, 8007007Ah
0x18000e8d8  jmp     loc_18000E7BD
0x18000e8dd  mov     ecx, 8007000Eh
0x18000e8e2  mov     r14, [rsp+140h+var_100]
0x18000e8e7  mov     r15, [rsp+140h+var_F8]
0x18000e8ec  mov     r12d, [rsp+140h+var_110]
0x18000e8f1  jmp     loc_18000E76B
0x18000e8f6  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
