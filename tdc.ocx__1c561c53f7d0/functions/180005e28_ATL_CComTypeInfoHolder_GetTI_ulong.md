# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180005e28`
- end: `0x1800061f4`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `972`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800059c0`
- `0x180005ca0`
- `0x180006200`
- `0x1800071c0`

## callees

- `0x1800011b8`
- `0x180001ff8`
- `0x180003b70`
- `0x180005e28`
- `0x1800073dc`
- `0x1800099ac`
- `0x180014270`
- `0x180014300`
- `0x180015010`

## import_xrefs

- `msvcrt!free` at `0x18000600b`
- `msvcrt!free` at `0x18000601e`
- `msvcrt!free` at `0x18000600b`
- `msvcrt!free` at `0x18000601e`
- `msvcrt!malloc` at `0x180005fad`
- `msvcrt!malloc` at `0x180005fad`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180005ffb`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180005ffb`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006054`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006054`
- `KERNEL32!LeaveCriticalSection` at `0x18000602c`
- `KERNEL32!LeaveCriticalSection` at `0x180006137`
- `KERNEL32!LeaveCriticalSection` at `0x1800061b4`
- `KERNEL32!LeaveCriticalSection` at `0x18000602c`
- `KERNEL32!LeaveCriticalSection` at `0x180006137`
- `KERNEL32!LeaveCriticalSection` at `0x1800061b4`
- `KERNEL32!EnterCriticalSection` at `0x180005e84`
- `KERNEL32!EnterCriticalSection` at `0x180006121`
- `KERNEL32!EnterCriticalSection` at `0x180005e84`
- `KERNEL32!EnterCriticalSection` at `0x180006121`
- `KERNEL32!GetModuleFileNameA` at `0x180005f10`
- `KERNEL32!GetModuleFileNameA` at `0x180005f10`
- `KERNEL32!MultiByteToWideChar` at `0x180005fea`
- `KERNEL32!MultiByteToWideChar` at `0x180005fea`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  struct _RTL_CRITICAL_SECTION *v5; // r12
  __int64 v6; // rcx
  WORD *v7; // rdx
  HRESULT NameCache; // esi
  DWORD ModuleFileNameA; // eax
  __int64 v10; // rax
  int v11; // ecx
  _QWORD *v12; // rbx
  unsigned __int64 v13; // rsi
  __int64 v14; // rax
  void *v15; // rsp
  WCHAR *lpWideCharStr; // r14
  _QWORD *v17; // rax
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rdx
  int (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v22; // rcx
  unsigned __int64 v23; // r15
  _QWORD *v24; // r14
  struct ITypeInfo *v25; // rdx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp+8h] BYREF
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp+10h] BYREF
  __int64 v29; // [rsp+48h] [rbp+18h] BYREF
  CHAR Filename[272]; // [rsp+50h] [rbp+20h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_53;
  }
  v6 = *((_QWORD *)this + 1);
  pptlib = 0;
  if ( ATL::CAtlModule::m_libid.Data1 != *(_DWORD *)v6
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)(v6 + 4)
    || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)(v6 + 8)
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)(v6 + 12) )
  {
    v7 = (WORD *)((char *)this + 16);
LABEL_35:
    NameCache = LoadRegTypeLib((const GUID *const)v6, *v7, *((_WORD *)this + 9), lcid, &pptlib);
    goto LABEL_36;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_35;
  NameCache = -2147467259;
  ModuleFileNameA = GetModuleFileNameA(hInstance, Filename, 0x104u);
  if ( ModuleFileNameA && ModuleFileNameA != 260 )
  {
    v10 = -1;
    do
      ++v10;
    while ( Filename[v10] );
    v11 = 2 * v10 + 2;
    if ( (unsigned __int64)(2LL * (int)v10 + 2147483650LL) <= 0xFFFFFFFF )
    {
      v12 = 0;
      v13 = v11;
      if ( v11 <= 1024
        && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v11, 0xFFFFFFFF) )
      {
        v14 = v13 + 15;
        if ( v13 + 15 < v13 )
          v14 = 0xFFFFFFFFFFFFFF0LL;
        v15 = alloca(v14 & 0xFFFFFFFFFFFFFFF0uLL);
        lpWideCharStr = WideCharStr;
      }
      else
      {
        if ( ~v13 < 0x10 )
          ATL::AtlThrowImpl(-2147024809);
        v17 = malloc(v13 + 16);
        if ( v17 )
        {
          *v17 = 0;
          lpWideCharStr = (WCHAR *)(v17 + 2);
          v12 = v17;
        }
        else
        {
          lpWideCharStr = 0;
        }
      }
      if ( lpWideCharStr )
      {
        *lpWideCharStr = 0;
        if ( MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v13 >> 1) )
        {
          NameCache = LoadTypeLib(lpWideCharStr, &pptlib);
          while ( v12 )
          {
            v18 = v12;
            v12 = (_QWORD *)*v12;
            free(v18);
          }
LABEL_36:
          if ( NameCache >= 0 )
          {
            v20 = *(_QWORD *)this;
            v28 = 0;
            NameCache = ((__int64 (__fastcall *)(ITypeLib *, __int64, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                          pptlib,
                          v20,
                          &v28);
            if ( NameCache >= 0 )
            {
              v21 = v28;
              *(_QWORD *)WideCharStr = v28;
              if ( v28 )
              {
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[1])(v28);
                v21 = v28;
              }
              v29 = 0;
              if ( (**v21)(v21, &GUID_00020412_0000_0000_c000_000000000046, &v29) >= 0 )
                ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(WideCharStr, &v29);
              v22 = 0;
              *((_QWORD *)this + 3) = *(_QWORD *)WideCharStr;
              *(_QWORD *)WideCharStr = 0;
              v23 = ((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0);
              if ( v23 )
              {
                v24 = operator new(0x18u);
                if ( v24 )
                {
                  v24[1] = this;
                  *v24 = ATL::CComTypeInfoHolder::Cleanup;
                  EnterCriticalSection((LPCRITICAL_SECTION)(v23 + 16));
                  v24[2] = *(_QWORD *)(v23 + 8);
                  *(_QWORD *)(v23 + 8) = v24;
                  LeaveCriticalSection((LPCRITICAL_SECTION)(v23 + 16));
                }
                v22 = *(_QWORD *)WideCharStr;
              }
              if ( v29 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                v22 = *(_QWORD *)WideCharStr;
              }
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
            ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
            if ( v28 )
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
          }
          goto LABEL_53;
        }
      }
      while ( v12 )
      {
        v19 = v12;
        v12 = (_QWORD *)*v12;
        free(v19);
      }
    }
    LeaveCriticalSection(v5);
    return 2147942414LL;
  }
LABEL_53:
  v25 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v25 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v25);
  }
  LeaveCriticalSection(v5);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180005e28  push    rbp
0x180005e2a  push    rdi
0x180005e2b  push    r12
0x180005e2d  push    r14
0x180005e2f  push    r15
0x180005e31  sub     rsp, 170h
0x180005e38  lea     rbp, [rsp+30h]
0x180005e3d  mov     [rbp+160h+arg_10], rbx
0x180005e44  mov     [rbp+160h+arg_18], rsi
0x180005e4b  mov     rax, cs:__security_cookie
0x180005e52  xor     rax, rbp
0x180005e55  mov     [rbp+160h+var_30], rax
0x180005e5c  cmp     qword ptr [rcx+18h], 0
0x180005e61  mov     ebx, edx
0x180005e63  mov     rdi, rcx
0x180005e66  jz      short loc_180005E76
0x180005e68  cmp     qword ptr [rcx+28h], 0
0x180005e6d  jz      short loc_180005E76
0x180005e6f  xor     eax, eax
0x180005e71  jmp     loc_1800061BC
0x180005e76  mov     r12, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005e7d  add     r12, 18h
0x180005e81  mov     rcx, r12; lpCriticalSection
0x180005e84  call    cs:__imp_EnterCriticalSection
0x180005e8a  cmp     qword ptr [rdi+18h], 0
0x180005e8f  jnz     loc_180006195
0x180005e95  mov     rcx, [rdi+8]; rguid
0x180005e99  mov     [rbp+160h+pptlib], 0
0x180005ea1  mov     eax, [rcx]
0x180005ea3  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180005ea9  jnz     loc_18000603C
0x180005eaf  mov     eax, [rcx+4]
0x180005eb2  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180005eb8  jnz     loc_18000603C
0x180005ebe  mov     eax, [rcx+8]
0x180005ec1  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180005ec7  jnz     loc_18000603C
0x180005ecd  mov     eax, [rcx+0Ch]
0x180005ed0  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180005ed6  jnz     loc_18000603C
0x180005edc  lea     rdx, [rdi+10h]
0x180005ee0  mov     eax, 0FFFFh
0x180005ee5  cmp     [rdx], ax
0x180005ee8  jnz     loc_180006040
0x180005eee  cmp     [rdi+12h], ax
0x180005ef2  jnz     loc_180006040
0x180005ef8  mov     rcx, cs:hInstance; hModule
0x180005eff  lea     rdx, [rbp+160h+Filename]; lpFilename
0x180005f03  mov     ebx, 104h
0x180005f08  mov     esi, 80004005h
0x180005f0d  mov     r8d, ebx; nSize
0x180005f10  call    cs:__imp_GetModuleFileNameA
0x180005f16  test    eax, eax
0x180005f18  jz      loc_180006197
0x180005f1e  cmp     eax, ebx
0x180005f20  jz      loc_180006197
0x180005f26  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005f2a  lea     rcx, [rbp+160h+Filename]
0x180005f2e  mov     rax, r15
0x180005f31  inc     rax
0x180005f34  cmp     byte ptr [rcx+rax], 0
0x180005f38  jnz     short loc_180005F31
0x180005f3a  cdqe
0x180005f3c  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180005f41  lea     rcx, ds:2[rax*2]
0x180005f49  mov     eax, 80000000h
0x180005f4e  add     rax, rcx
0x180005f51  cmp     rax, rdx
0x180005f54  ja      loc_180006029
0x180005f5a  xor     ebx, ebx
0x180005f5c  movsxd  rsi, ecx
0x180005f5f  cmp     ecx, 400h
0x180005f65  jg      short loc_180005F99
0x180005f67  mov     rcx, rsi; this
0x180005f6a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180005f6f  test    al, al
0x180005f71  jz      short loc_180005F99
0x180005f73  lea     rax, [rsi+0Fh]
0x180005f77  cmp     rax, rsi
0x180005f7a  ja      short loc_180005F86
0x180005f7c  mov     rax, 0FFFFFFFFFFFFFF0h
0x180005f86  and     rax, 0FFFFFFFFFFFFFFF0h
0x180005f8a  call    _alloca_probe
0x180005f8f  sub     rsp, rax
0x180005f92  lea     r14, [rsp+190h+WideCharStr]
0x180005f97  jmp     short loc_180005FC7
0x180005f99  mov     rax, rsi
0x180005f9c  not     rax
0x180005f9f  cmp     rax, 10h
0x180005fa3  jb      loc_1800061E9
0x180005fa9  lea     rcx, [rsi+10h]; Size
0x180005fad  call    cs:__imp_malloc
0x180005fb3  test    rax, rax
0x180005fb6  jnz     short loc_180005FBD
0x180005fb8  xor     r14d, r14d
0x180005fbb  jmp     short loc_180005FC7
0x180005fbd  mov     [rax], rbx
0x180005fc0  lea     r14, [rax+10h]
0x180005fc4  mov     rbx, rax
0x180005fc7  test    r14, r14
0x180005fca  jz      short loc_180006024
0x180005fcc  xor     eax, eax
0x180005fce  shr     rsi, 1
0x180005fd1  mov     [rsp+190h+cchWideChar], esi; cchWideChar
0x180005fd5  lea     r8, [rbp+160h+Filename]; lpMultiByteStr
0x180005fd9  mov     r9d, r15d; cbMultiByte
0x180005fdc  mov     [r14], ax
0x180005fe0  xor     edx, edx; dwFlags
0x180005fe2  mov     [rsp+190h+lpWideCharStr], r14; lpWideCharStr
0x180005fe7  lea     ecx, [rax+3]; CodePage
0x180005fea  call    cs:__imp_MultiByteToWideChar
0x180005ff0  test    eax, eax
0x180005ff2  jz      short loc_180006024
0x180005ff4  lea     rdx, [rbp+160h+pptlib]; pptlib
0x180005ff8  mov     rcx, r14; szFile
0x180005ffb  call    cs:__imp_LoadTypeLib
0x180006001  mov     esi, eax
0x180006003  jmp     short loc_180006011
0x180006005  mov     rcx, rbx; Block
0x180006008  mov     rbx, [rbx]
0x18000600b  call    cs:__imp_free
0x180006011  test    rbx, rbx
0x180006014  jnz     short loc_180006005
0x180006016  jmp     short loc_18000605C
0x180006018  mov     rcx, rbx; Block
0x18000601b  mov     rbx, [rbx]
0x18000601e  call    cs:__imp_free
0x180006024  test    rbx, rbx
0x180006027  jnz     short loc_180006018
0x180006029  mov     rcx, r12; lpCriticalSection
0x18000602c  call    cs:__imp_LeaveCriticalSection
0x180006032  mov     eax, 8007000Eh
0x180006037  jmp     loc_1800061BC
0x18000603c  lea     rdx, [rdi+10h]
0x180006040  movzx   r8d, word ptr [rdi+12h]; wVerMinor
0x180006045  lea     rax, [rbp+160h+pptlib]
0x180006049  movzx   edx, word ptr [rdx]; wVerMajor
0x18000604c  mov     r9d, ebx; lcid
0x18000604f  mov     [rsp+190h+lpWideCharStr], rax; pptlib
0x180006054  call    cs:__imp_LoadRegTypeLib
0x18000605a  mov     esi, eax
0x18000605c  test    esi, esi
0x18000605e  js      loc_180006197
0x180006064  mov     rcx, [rbp+160h+pptlib]
0x180006068  lea     r8, [rbp+160h+var_150]
0x18000606c  mov     rdx, [rdi]
0x18000606f  mov     [rbp+160h+var_150], 0
0x180006077  mov     rax, [rcx]
0x18000607a  mov     rax, [rax+30h]
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  mov     esi, eax
0x180006085  test    eax, eax
0x180006087  js      loc_18000616E
0x18000608d  mov     rcx, [rbp+160h+var_150]
0x180006091  mov     qword ptr [rbp+160h+WideCharStr], rcx
0x180006095  test    rcx, rcx
0x180006098  jz      short loc_1800060AA
0x18000609a  mov     rax, [rcx]
0x18000609d  mov     rax, [rax+8]
0x1800060a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a6  mov     rcx, [rbp+160h+var_150]
0x1800060aa  mov     [rbp+160h+var_148], 0
0x1800060b2  lea     r8, [rbp+160h+var_148]
0x1800060b6  mov     rax, [rcx]
0x1800060b9  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x1800060c0  mov     rax, [rax]
0x1800060c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c8  test    eax, eax
0x1800060ca  js      short loc_1800060D9
0x1800060cc  lea     rdx, [rbp+160h+var_148]
0x1800060d0  lea     rcx, [rbp+160h+WideCharStr]
0x1800060d4  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x1800060d9  mov     rax, qword ptr [rbp+160h+WideCharStr]
0x1800060dd  xor     ecx, ecx
0x1800060df  mov     [rdi+18h], rax
0x1800060e3  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800060ea  mov     qword ptr [rbp+160h+WideCharStr], rcx
0x1800060ee  lea     rdx, [rax+8]
0x1800060f2  neg     rax
0x1800060f5  sbb     r15, r15
0x1800060f8  and     r15, rdx
0x1800060fb  jz      short loc_180006141
0x1800060fd  mov     ecx, 18h; Size
0x180006102  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006107  mov     r14, rax
0x18000610a  test    rax, rax
0x18000610d  jz      short loc_18000613D
0x18000610f  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x180006116  mov     [r14+8], rdi
0x18000611a  lea     rcx, [r15+10h]; lpCriticalSection
0x18000611e  mov     [r14], rax
0x180006121  call    cs:__imp_EnterCriticalSection
0x180006127  mov     rcx, [r15+8]
0x18000612b  mov     [r14+10h], rcx
0x18000612f  lea     rcx, [r15+10h]; lpCriticalSection
0x180006133  mov     [r15+8], r14
0x180006137  call    cs:__imp_LeaveCriticalSection
0x18000613d  mov     rcx, qword ptr [rbp+160h+WideCharStr]
0x180006141  mov     rdx, [rbp+160h+var_148]
0x180006145  test    rdx, rdx
0x180006148  jz      short loc_18000615D
0x18000614a  mov     rax, [rdx]
0x18000614d  mov     rcx, rdx
0x180006150  mov     rax, [rax+10h]
0x180006154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006159  mov     rcx, qword ptr [rbp+160h+WideCharStr]
0x18000615d  test    rcx, rcx
0x180006160  jz      short loc_18000616E
0x180006162  mov     rax, [rcx]
0x180006165  mov     rax, [rax+10h]
0x180006169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616e  mov     rcx, [rbp+160h+pptlib]
0x180006172  mov     rax, [rcx]
0x180006175  mov     rax, [rax+10h]
0x180006179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617e  mov     rcx, [rbp+160h+var_150]
0x180006182  test    rcx, rcx
0x180006185  jz      short loc_180006197
0x180006187  mov     rax, [rcx]
0x18000618a  mov     rax, [rax+10h]
0x18000618e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006193  jmp     short loc_180006197
0x180006195  xor     esi, esi
0x180006197  mov     rdx, [rdi+18h]; struct ITypeInfo *
0x18000619b  test    rdx, rdx
0x18000619e  jz      short loc_1800061B1
0x1800061a0  cmp     qword ptr [rdi+28h], 0
0x1800061a5  jnz     short loc_1800061B1
0x1800061a7  mov     rcx, rdi; this
0x1800061aa  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x1800061af  mov     esi, eax
0x1800061b1  mov     rcx, r12; lpCriticalSection
0x1800061b4  call    cs:__imp_LeaveCriticalSection
0x1800061ba  mov     eax, esi
0x1800061bc  mov     rcx, [rbp+160h+var_30]
0x1800061c3  xor     rcx, rbp; StackCookie
0x1800061c6  call    __security_check_cookie
0x1800061cb  mov     rbx, [rbp+160h+arg_10]
0x1800061d2  mov     rsi, [rbp+160h+arg_18]
0x1800061d9  lea     rsp, [rbp+140h]
0x1800061e0  pop     r15
0x1800061e2  pop     r14
0x1800061e4  pop     r12
0x1800061e6  pop     rdi
0x1800061e7  pop     rbp
0x1800061e8  retn
0x1800061e9  mov     ecx, 80070057h; int
0x1800061ee  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
