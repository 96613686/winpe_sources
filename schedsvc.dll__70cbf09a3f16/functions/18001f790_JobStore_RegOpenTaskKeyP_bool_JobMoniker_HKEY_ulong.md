# JobStore::RegOpenTaskKeyP(bool,JobMoniker &,HKEY__ * *,ulong)

- ea: `0x18001f790`
- end: `0x18001fc4d`
- name: `?RegOpenTaskKeyP@JobStore@@AEAAJ_NAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z`
- size: `1213`
- prototype: `__int64 __fastcall(HKEY *this, char, struct JobMoniker *, HKEY *, REGSAM samDesired)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c840`

## callees

- `0x18001ec90`
- `0x18001f790`
- `0x18001fc54`
- `0x18001fdb0`
- `0x180021300`
- `0x18002132c`
- `0x1800504b4`
- `0x180053e54`
- `0x18006420c`
- `0x18006d9f4`
- `0x180070288`
- `0x18007e67e`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001f9a3`
- `msvcrt!memcpy_s` at `0x18001f9c1`
- `msvcrt!memcpy_s` at `0x18001f9a3`
- `msvcrt!memcpy_s` at `0x18001f9c1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f8ee`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001f972`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001f972`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb18`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fc1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb18`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fc1c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f804`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f957`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f987`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f804`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f957`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f987`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa1f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f929`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f929`

## string_xrefs

- `0x18001f8e7`: `TaskCache\Tasks\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobStore::RegOpenTaskKeyP(HKEY *this, char a2, struct JobMoniker *a3, HKEY *a4, REGSAM samDesired)
{
  HKEY *v5; // r14
  HKEY *v8; // rsi
  GUID v9; // xmm6
  OLECHAR **v10; // rcx
  OLECHAR *v11; // rcx
  UINT v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rbx
  int TreeInfo; // ebx
  _DWORD *v17; // rax
  OLECHAR *v18; // rbx
  __int64 v19; // rdi
  signed int v20; // eax
  __int64 v21; // rsi
  signed int v22; // r14d
  BSTR v23; // r15
  errno_t v24; // eax
  errno_t v25; // eax
  signed int v26; // ecx
  LSTATUS v27; // eax
  unsigned int v28; // edi
  HKEY v29; // rax
  __int64 result; // rax
  const unsigned __int16 *v31; // rax
  const unsigned __int16 *Path; // rax
  const unsigned __int16 *v33; // rax
  HKEY phkResult; // [rsp+30h] [rbp-A1h] BYREF
  JobStore *v35; // [rsp+38h] [rbp-99h]
  HKEY *v36; // [rsp+40h] [rbp-91h]
  GUID Buf2; // [rsp+50h] [rbp-81h] BYREF
  struct _GUID v38; // [rsp+60h] [rbp-71h] BYREF
  GUID rguid; // [rsp+70h] [rbp-61h] BYREF
  OLECHAR sz[8]; // [rsp+80h] [rbp-51h] BYREF
  __int128 v41; // [rsp+90h] [rbp-41h]
  __int128 v42; // [rsp+A0h] [rbp-31h]
  _BYTE v43[30]; // [rsp+B0h] [rbp-21h] BYREF

  v5 = a4;
  v36 = a4;
  v8 = this;
  v35 = (JobStore *)this;
  rguid = 0;
  v9 = *(GUID *)a3;
  Buf2 = *(GUID *)a3;
  v10 = (OLECHAR **)*((_QWORD *)a3 + 2);
  if ( v10 && ((v11 = *v10) == 0 ? (v12 = 0) : (v12 = SysStringLen(v11)), v12) )
  {
    v13 = (__int64 *)*((_QWORD *)a3 + 2);
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
  v38 = 0;
  if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) && a2 != 1 )
    goto LABEL_13;
  TreeInfo = JobStore::RegGetTreeInfo((JobStore *)v8, v15, &v38, 0);
  if ( TreeInfo < 0 )
  {
    v17 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      v9 = v38;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_16;
      }
      Path = JobMoniker::GetPath(a3);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, Path);
LABEL_13:
      v17 = WPP_GLOBAL_Control;
LABEL_16:
      rguid = v9;
      TreeInfo = 0;
      goto LABEL_17;
    }
    if ( !memcmp_0(&Buf2, &v38, 0x10u) )
      goto LABEL_13;
    rguid = v38;
    TreeInfo = -2147216621;
    v17 = WPP_GLOBAL_Control;
  }
LABEL_17:
  if ( !a2 )
    goto LABEL_18;
  if ( TreeInfo != -2147216621 )
  {
    if ( !(unsigned int)JobStore::IsMigrationCleanupCompleted((JobStore *)v8) )
      TreeInfo = JobStore::MigrateDynamicTaskInfo((JobStore *)v8, a3, &rguid);
LABEL_18:
    if ( TreeInfo < 0 )
      return (unsigned int)TreeInfo;
    v18 = SysAllocString(L"TaskCache\\Tasks\\");
    *(_QWORD *)&v38.Data1 = v18;
    if ( !v18 )
      ATL::PrivateAtlThrow(0x8007000E);
    *(_OWORD *)sz = 0;
    v41 = 0;
    v42 = 0;
    memset(v43, 0, sizeof(v43));
    if ( !StringFromGUID2(&rguid, sz, 39) )
    {
      SysFreeString(v18);
      return 2147942522LL;
    }
    v19 = -1;
    do
      ++v19;
    while ( sz[v19] );
    if ( (_DWORD)v19 )
    {
      v20 = SysStringLen(v18);
      v21 = v20;
      v22 = v20 + v19;
      if ( v20 + (int)v19 < v20 )
      {
        v26 = -2147024882;
        v8 = (HKEY *)v35;
        v5 = v36;
        goto LABEL_30;
      }
      v23 = SysAllocStringLen(0, v22);
      if ( !v23 )
      {
        v26 = -2147024882;
        v8 = (HKEY *)v35;
        v5 = v36;
        goto LABEL_30;
      }
      if ( SysStringLen(v18) )
      {
        v24 = memcpy_s(v23, 2LL * v22, v18, 2 * v21);
        ATL::AtlCrtErrorCheck(v24);
      }
      v25 = memcpy_s(&v23[v21], 2LL * (int)v19, sz, 2LL * (int)v19);
      ATL::AtlCrtErrorCheck(v25);
      v23[v22] = 0;
      SysFreeString(v18);
      v18 = v23;
      *(_QWORD *)&v38.Data1 = v23;
      v8 = (HKEY *)v35;
      v5 = v36;
    }
    v26 = 0;
LABEL_30:
    if ( v26 < 0 )
      ATL::PrivateAtlThrow(v26);
    phkResult = 0;
    v27 = RegOpenKeyExW(v8[2], v18, 0, samDesired, &phkResult);
    v28 = v27;
    if ( v27 )
    {
      if ( v27 > 0 )
        v28 = (unsigned __int16)v27 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = JobMoniker::GetPath(a3);
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          (_DWORD)v18,
          (__int64)v31,
          v28);
      }
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
      SysFreeString(v18);
      return v28;
    }
    else
    {
      v29 = phkResult;
      phkResult = 0;
      *v5 = v29;
      SysFreeString(v18);
      return 0;
    }
  }
  if ( v17 != (_DWORD *)&WPP_GLOBAL_Control && (v17[7] & 0x40000) != 0 && *((_BYTE *)v17 + 25) >= 4u )
  {
    v33 = JobMoniker::GetPath(a3);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, v33);
  }
  JobStore::MigrateDynamicTaskInfo((JobStore *)v8, a3, &rguid);
  result = JobStore::RemoveTaskEntryP((JobStore *)v8, (OLECHAR ***)a3, 2);
  if ( (int)result >= 0 )
    return 2147750670LL;
  return result;
}

```

## disassembly

```asm
0x18001f790  mov     [rsp-8+arg_8], rbx
0x18001f795  push    rbp
0x18001f796  push    rsi
0x18001f797  push    rdi
0x18001f798  push    r12
0x18001f79a  push    r13
0x18001f79c  push    r14
0x18001f79e  push    r15
0x18001f7a0  lea     rbp, [rsp-1Fh]
0x18001f7a5  sub     rsp, 0F0h
0x18001f7ac  movaps  [rsp+120h+var_40], xmm6
0x18001f7b4  mov     rax, cs:__security_cookie
0x18001f7bb  xor     rax, rsp
0x18001f7be  mov     [rbp+4Fh+var_50], rax
0x18001f7c2  mov     r14, r9
0x18001f7c5  mov     [rsp+120h+var_E0], r9
0x18001f7ca  mov     r13, r8
0x18001f7cd  movzx   edi, dl
0x18001f7d0  mov     rsi, rcx
0x18001f7d3  mov     [rsp+120h+var_E8], rcx
0x18001f7d8  xorps   xmm0, xmm0
0x18001f7db  movups  xmmword ptr [rbp+4Fh+rguid.Data1], xmm0
0x18001f7df  movups  xmm6, xmmword ptr [r8]
0x18001f7e3  movaps  [rsp+120h+Buf2], xmm6
0x18001f7e8  mov     rcx, [r8+10h]
0x18001f7ec  xor     r12d, r12d
0x18001f7ef  test    rcx, rcx
0x18001f7f2  jz      loc_18001FA76
0x18001f7f8  mov     rcx, [rcx]; pbstr
0x18001f7fb  test    rcx, rcx
0x18001f7fe  jz      loc_18001FB25
0x18001f804  call    cs:__imp_SysStringLen
0x18001f80a  test    eax, eax
0x18001f80c  jz      loc_18001FA76
0x18001f812  mov     rax, [r13+10h]
0x18001f816  test    rax, rax
0x18001f819  jz      loc_18001FA7E
0x18001f81f  mov     rcx, [rax]
0x18001f822  lea     rbx, [rcx+0Eh]
0x18001f826  xorps   xmm0, xmm0
0x18001f829  movups  xmmword ptr [rbp+4Fh+var_C0.Data1], xmm0
0x18001f82d  mov     r8d, 10h; Size
0x18001f833  lea     rdx, [rsp+120h+Buf2]; Buf2
0x18001f838  lea     rcx, GUID_NULL; Buf1
0x18001f83f  call    memcmp_0
0x18001f844  lea     r15, WPP_GLOBAL_Control
0x18001f84b  test    eax, eax
0x18001f84d  jz      short loc_18001F855
0x18001f84f  cmp     dil, 1
0x18001f853  jnz     short loc_18001F8A8
0x18001f855  xor     r9d, r9d; enum JobStore::TaskIndex *
0x18001f858  lea     r8, [rbp+4Fh+var_C0]; struct _GUID *
0x18001f85c  mov     rdx, rbx; unsigned __int16 *
0x18001f85f  mov     rcx, rsi; this
0x18001f862  call    ?RegGetTreeInfo@JobStore@@QEBAJPEBGPEAU_GUID@@PEAW4TaskIndex@1@@Z; JobStore::RegGetTreeInfo(ushort const *,_GUID *,JobStore::TaskIndex *)
0x18001f867  mov     ebx, eax
0x18001f869  test    eax, eax
0x18001f86b  js      loc_18001FB2D
0x18001f871  mov     r8d, 10h; Size
0x18001f877  lea     rdx, [rsp+120h+Buf2]; Buf2
0x18001f87c  lea     rcx, GUID_NULL; Buf1
0x18001f883  call    memcmp_0
0x18001f888  test    eax, eax
0x18001f88a  jz      short loc_18001F8B1
0x18001f88c  mov     r8d, 10h; Size
0x18001f892  lea     rdx, [rbp+4Fh+var_C0]; Buf2
0x18001f896  lea     rcx, [rsp+120h+Buf2]; Buf1
0x18001f89b  call    memcmp_0
0x18001f8a0  test    eax, eax
0x18001f8a2  jnz     loc_18001FA9A
0x18001f8a8  mov     rax, cs:WPP_GLOBAL_Control
0x18001f8af  jmp     short loc_18001F8CE
0x18001f8b1  movaps  xmm6, xmmword ptr [rbp+4Fh+var_C0.Data1]
0x18001f8b5  mov     rax, cs:WPP_GLOBAL_Control
0x18001f8bc  cmp     rax, r15
0x18001f8bf  jz      short loc_18001F8CE
0x18001f8c1  test    dword ptr [rax+1Ch], 40000h
0x18001f8c8  jnz     loc_18001FB39
0x18001f8ce  movdqa  xmmword ptr [rbp+4Fh+rguid.Data1], xmm6
0x18001f8d3  mov     ebx, r12d
0x18001f8d6  test    dil, dil
0x18001f8d9  jnz     loc_18001FB6F
0x18001f8df  test    ebx, ebx
0x18001f8e1  js      loc_18001FC07
0x18001f8e7  lea     rcx, aTaskcacheTasks; "TaskCache\\Tasks\\"
0x18001f8ee  call    cs:__imp_SysAllocString
0x18001f8f4  mov     rbx, rax
0x18001f8f7  mov     qword ptr [rbp+4Fh+var_C0.Data1], rax
0x18001f8fb  test    rax, rax
0x18001f8fe  jz      loc_18001FC0E
0x18001f904  xorps   xmm0, xmm0
0x18001f907  movups  xmmword ptr [rbp+4Fh+sz], xmm0
0x18001f90b  movups  [rbp+4Fh+var_90], xmm0
0x18001f90f  movups  [rbp+4Fh+var_80], xmm0
0x18001f913  movups  xmmword ptr [rbp+4Fh+var_70], xmm0
0x18001f917  movups  xmmword ptr [rbp+4Fh+var_70+0Eh], xmm0
0x18001f91b  mov     r8d, 27h ; '''; cchMax
0x18001f921  lea     rdx, [rbp+4Fh+sz]; lpsz
0x18001f925  lea     rcx, [rbp+4Fh+rguid]; rguid
0x18001f929  call    cs:__imp_StringFromGUID2
0x18001f92f  test    eax, eax
0x18001f931  jz      loc_18001FC19
0x18001f937  lea     rax, [rbp+4Fh+sz]
0x18001f93b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001f942  inc     rdi
0x18001f945  cmp     word ptr [rax+rdi*2], 0
0x18001f94a  jnz     short loc_18001F942
0x18001f94c  test    edi, edi
0x18001f94e  jz      loc_18001F9F7
0x18001f954  mov     rcx, rbx; pbstr
0x18001f957  call    cs:__imp_SysStringLen
0x18001f95d  movsxd  rsi, eax
0x18001f960  lea     r14d, [rsi+rdi]
0x18001f964  cmp     r14d, esi
0x18001f967  jl      loc_18001FA86
0x18001f96d  mov     edx, r14d; ui
0x18001f970  xor     ecx, ecx; strIn
0x18001f972  call    cs:__imp_SysAllocStringLen
0x18001f978  mov     r15, rax
0x18001f97b  test    rax, rax
0x18001f97e  jz      loc_18001FC2C
0x18001f984  mov     rcx, rbx; pbstr
0x18001f987  call    cs:__imp_SysStringLen
0x18001f98d  test    eax, eax
0x18001f98f  jz      short loc_18001F9B0
0x18001f991  mov     r9, rsi
0x18001f994  add     r9, r9; SourceSize
0x18001f997  movsxd  rdx, r14d
0x18001f99a  add     rdx, rdx; DestinationSize
0x18001f99d  mov     r8, rbx; Source
0x18001f9a0  mov     rcx, r15; Destination
0x18001f9a3  call    cs:__imp_memcpy_s
0x18001f9a9  mov     ecx, eax; int
0x18001f9ab  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001f9b0  movsxd  rdx, edi
0x18001f9b3  add     rdx, rdx; DestinationSize
0x18001f9b6  lea     rcx, [r15+rsi*2]; Destination
0x18001f9ba  mov     r9, rdx; SourceSize
0x18001f9bd  lea     r8, [rbp+4Fh+sz]; Source
0x18001f9c1  call    cs:__imp_memcpy_s
0x18001f9c7  mov     ecx, eax; int
0x18001f9c9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001f9ce  movsxd  rax, r14d
0x18001f9d1  mov     [r15+rax*2], r12w
0x18001f9d6  mov     rcx, rbx; bstrString
0x18001f9d9  call    cs:__imp_SysFreeString
0x18001f9df  mov     rbx, r15
0x18001f9e2  mov     qword ptr [rbp+4Fh+var_C0.Data1], rbx
0x18001f9e6  mov     rsi, [rsp+120h+var_E8]
0x18001f9eb  mov     r14, [rsp+120h+var_E0]
0x18001f9f0  lea     r15, WPP_GLOBAL_Control
0x18001f9f7  mov     ecx, r12d; unsigned int
0x18001f9fa  test    ecx, ecx
0x18001f9fc  js      loc_18001FC47
0x18001fa02  mov     [rsp+120h+var_F0], r12
0x18001fa07  lea     rax, [rsp+120h+var_F0]
0x18001fa0c  mov     [rsp+120h+phkResult], rax; phkResult
0x18001fa11  mov     r9d, [rbp+4Fh+samDesired]; samDesired
0x18001fa15  xor     r8d, r8d; ulOptions
0x18001fa18  mov     rdx, rbx; lpSubKey
0x18001fa1b  mov     rcx, [rsi+10h]; hKey
0x18001fa1f  call    cs:__imp_RegOpenKeyExW
0x18001fa25  mov     edi, eax
0x18001fa27  test    eax, eax
0x18001fa29  jnz     loc_18001FAB4
0x18001fa2f  mov     rax, [rsp+120h+var_F0]
0x18001fa34  mov     [rsp+120h+var_F0], r12
0x18001fa39  mov     [r14], rax
0x18001fa3c  mov     rcx, rbx; bstrString
0x18001fa3f  call    cs:__imp_SysFreeString
0x18001fa45  xor     eax, eax
0x18001fa47  mov     rcx, [rbp+4Fh+var_50]
0x18001fa4b  xor     rcx, rsp; StackCookie
0x18001fa4e  call    __security_check_cookie
0x18001fa53  mov     rbx, [rsp+120h+arg_8]
0x18001fa5b  movaps  xmm6, [rsp+120h+var_40]
0x18001fa63  add     rsp, 0F0h
0x18001fa6a  pop     r15
0x18001fa6c  pop     r14
0x18001fa6e  pop     r13
0x18001fa70  pop     r12
0x18001fa72  pop     rdi
0x18001fa73  pop     rsi
0x18001fa74  pop     rbp
0x18001fa75  retn
0x18001fa76  mov     rbx, r12
0x18001fa79  jmp     loc_18001F826
0x18001fa7e  mov     rcx, r12
0x18001fa81  jmp     loc_18001F822
0x18001fa86  mov     ecx, 8007000Eh
0x18001fa8b  mov     rsi, [rsp+120h+var_E8]
0x18001fa90  mov     r14, [rsp+120h+var_E0]
0x18001fa95  jmp     loc_18001F9FA
0x18001fa9a  movaps  xmm0, xmmword ptr [rbp+4Fh+var_C0.Data1]
0x18001fa9e  movdqa  xmmword ptr [rbp+4Fh+rguid.Data1], xmm0
0x18001faa3  mov     ebx, 80041313h
0x18001faa8  mov     rax, cs:WPP_GLOBAL_Control
0x18001faaf  jmp     loc_18001F8D6
0x18001fab4  jle     short loc_18001FABF
0x18001fab6  movzx   edi, ax
0x18001fab9  or      edi, 80070000h
0x18001fabf  mov     rax, cs:WPP_GLOBAL_Control
0x18001fac6  cmp     rax, r15
0x18001fac9  jz      short loc_18001FB0A
0x18001facb  test    dword ptr [rax+1Ch], 40000h
0x18001fad2  jz      short loc_18001FB0A
0x18001fad4  cmp     byte ptr [rax+19h], 2
0x18001fad8  jb      short loc_18001FB0A
0x18001fada  mov     rcx, r13; this
0x18001fadd  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18001fae2  mov     edx, 2Dh ; '-'
0x18001fae7  mov     [rsp+120h+var_F8], edi
0x18001faeb  mov     [rsp+120h+phkResult], rax
0x18001faf0  mov     r9, rbx
0x18001faf3  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18001fafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb01  mov     rcx, [rcx+10h]
0x18001fb05  call    WPP_SF_SSD
0x18001fb0a  lea     rcx, [rsp+120h+var_F0]; this
0x18001fb0f  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18001fb14  nop
0x18001fb15  mov     rcx, rbx; bstrString
0x18001fb18  call    cs:__imp_SysFreeString
0x18001fb1e  mov     eax, edi
0x18001fb20  jmp     loc_18001FA47
0x18001fb25  mov     eax, r12d
0x18001fb28  jmp     loc_18001F80A
0x18001fb2d  mov     rax, cs:WPP_GLOBAL_Control
0x18001fb34  jmp     loc_18001F8D6
0x18001fb39  cmp     byte ptr [rax+19h], 3
0x18001fb3d  jb      loc_18001F8CE
0x18001fb43  mov     rcx, r13; this
0x18001fb46  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18001fb4b  mov     edx, 51h ; 'Q'
0x18001fb50  mov     r9, rax
0x18001fb53  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18001fb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb61  mov     rcx, [rcx+10h]
0x18001fb65  call    WPP_SF_S
0x18001fb6a  jmp     loc_18001F8A8
0x18001fb6f  cmp     ebx, 80041313h
0x18001fb75  jnz     short loc_18001FBE1
0x18001fb77  cmp     rax, r15
0x18001fb7a  jz      short loc_18001FBB2
0x18001fb7c  test    dword ptr [rax+1Ch], 40000h
0x18001fb83  jz      short loc_18001FBB2
0x18001fb85  cmp     byte ptr [rax+19h], 4
0x18001fb89  jb      short loc_18001FBB2
0x18001fb8b  mov     rcx, r13; this
0x18001fb8e  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x18001fb93  mov     edx, 2Ch ; ','
0x18001fb98  mov     r9, rax
0x18001fb9b  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18001fba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fba9  mov     rcx, [rcx+10h]
0x18001fbad  call    WPP_SF_S
0x18001fbb2  lea     r8, [rbp+4Fh+rguid]; struct _GUID *
0x18001fbb6  mov     rdx, r13; struct JobMoniker *
0x18001fbb9  mov     rcx, rsi; this
0x18001fbbc  call    ?MigrateDynamicTaskInfo@JobStore@@AEAAJAEBVJobMoniker@@AEBU_GUID@@@Z; JobStore::MigrateDynamicTaskInfo(JobMoniker const &,_GUID const &)
0x18001fbc1  mov     r8d, 2
0x18001fbc7  mov     rdx, r13
0x18001fbca  mov     rcx, rsi
0x18001fbcd  call    ?RemoveTaskEntryP@JobStore@@AEBAJAEBVJobMoniker@@W4REMOVE_TASK_TYPE@1@@Z; JobStore::RemoveTaskEntryP(JobMoniker const &,JobStore::REMOVE_TASK_TYPE)
0x18001fbd2  mov     ecx, 8004130Eh
0x18001fbd7  test    eax, eax
0x18001fbd9  cmovns  eax, ecx
0x18001fbdc  jmp     loc_18001FA47
0x18001fbe1  mov     rcx, rsi; this
0x18001fbe4  call    ?IsMigrationCleanupCompleted@JobStore@@QEBAHXZ; JobStore::IsMigrationCleanupCompleted(void)
0x18001fbe9  test    eax, eax
0x18001fbeb  jnz     loc_18001F8DF
0x18001fbf1  lea     r8, [rbp+4Fh+rguid]; struct _GUID *
0x18001fbf5  mov     rdx, r13; struct JobMoniker *
0x18001fbf8  mov     rcx, rsi; this
0x18001fbfb  call    ?MigrateDynamicTaskInfo@JobStore@@AEAAJAEBVJobMoniker@@AEBU_GUID@@@Z; JobStore::MigrateDynamicTaskInfo(JobMoniker const &,_GUID const &)
0x18001fc00  mov     ebx, eax
0x18001fc02  jmp     loc_18001F8DF
0x18001fc07  mov     eax, ebx
0x18001fc09  jmp     loc_18001FA47
0x18001fc0e  mov     ecx, 8007000Eh; unsigned int
0x18001fc13  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18001fc19  mov     rcx, rbx; bstrString
0x18001fc1c  call    cs:__imp_SysFreeString
0x18001fc22  mov     eax, 8007007Ah
0x18001fc27  jmp     loc_18001FA47
0x18001fc2c  mov     ecx, 8007000Eh
0x18001fc31  mov     rsi, [rsp+120h+var_E8]
0x18001fc36  mov     r14, [rsp+120h+var_E0]
0x18001fc3b  lea     r15, WPP_GLOBAL_Control
0x18001fc42  jmp     loc_18001F9FA
0x18001fc47  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
