# CWebCrawler::OnOleCommandTargetExec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x180021070`
- end: `0x1800215d3`
- name: `?OnOleCommandTargetExec@CWebCrawler@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `1379`
- prototype: `__int64 __fastcall(CWebCrawler *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x180008648`
- `0x18001ba08`
- `0x18001ba40`
- `0x18001eae4`
- `0x1800200d8`
- `0x1800204ac`
- `0x180021070`
- `0x180021e10`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180021288`
- `KERNEL32!LocalAlloc` at `0x18002152e`
- `KERNEL32!LocalAlloc` at `0x180021288`
- `KERNEL32!LocalAlloc` at `0x18002152e`
- `KERNEL32!LocalFree` at `0x1800212d2`
- `KERNEL32!LocalFree` at `0x180021581`
- `KERNEL32!LocalFree` at `0x18002158f`
- `KERNEL32!LocalFree` at `0x1800212d2`
- `KERNEL32!LocalFree` at `0x180021581`
- `KERNEL32!LocalFree` at `0x18002158f`
- `SHLWAPI!SHStrDupW` at `0x180021481`
- `SHLWAPI!SHStrDupW` at `0x180021481`
- `SHLWAPI!StrDupW` at `0x180021152`
- `SHLWAPI!StrDupW` at `0x180021152`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180021546`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x180021546`
- `ole32!CoTaskMemFree` at `0x1800214e7`
- `ole32!CoTaskMemFree` at `0x18002156d`
- `ole32!CoTaskMemFree` at `0x1800214e7`
- `ole32!CoTaskMemFree` at `0x18002156d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800212c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180021391`
- `OLEAUT32!__imp_SysAllocString` at `0x180021498`
- `OLEAUT32!__imp_SysAllocString` at `0x1800212c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180021391`
- `OLEAUT32!__imp_SysAllocString` at `0x180021498`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800213f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180021503`
- `OLEAUT32!__imp_SysFreeString` at `0x1800212b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800213f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180021503`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180021520`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180021520`

## pseudocode

```c
__int64 __fastcall CWebCrawler::OnOleCommandTargetExec(
        CWebCrawler *this,
        const struct _GUID *a2,
        int a3,
        int a4,
        struct tagVARIANT *a5)
{
  const OLECHAR *v5; // r13
  unsigned int v7; // ebx
  __int64 v8; // rax
  bool v9; // zf
  unsigned __int16 *v10; // r14
  unsigned int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned __int16 *v15; // rdi
  __int64 v16; // rcx
  unsigned __int64 v17; // rsi
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // r12
  BSTR v22; // rsi
  CWebCrawler *v23; // rbx
  OLECHAR v24; // r15
  const OLECHAR *v25; // rcx
  int v26; // ecx
  int v27; // eax
  void *v28; // rbx
  int v29; // eax
  OLECHAR *v30; // rdi
  int v31; // esi
  CHAR *v32; // rax
  char *v33; // rdi
  BSTR v35; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v36; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  CWebCrawler *v38; // [rsp+58h] [rbp-A8h]
  _DWORD v39[8]; // [rsp+60h] [rbp-A0h]
  _WORD v40[4]; // [rsp+80h] [rbp-80h]
  BSTR bstrString[2]; // [rsp+88h] [rbp-78h]
  __int16 v42; // [rsp+98h] [rbp-68h]
  OLECHAR *v43; // [rsp+A0h] [rbp-60h]
  __int16 v44; // [rsp+E0h] [rbp-20h]
  LPCWSTR psz; // [rsp+E8h] [rbp-18h]
  __int16 v46; // [rsp+F8h] [rbp-8h]
  OLECHAR *v47; // [rsp+100h] [rbp+0h]
  __int16 v48; // [rsp+110h] [rbp+10h]
  BSTR bstr; // [rsp+118h] [rbp+18h]
  _DWORD v50[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v51[34]; // [rsp+140h] [rbp+40h]

  v5 = 0;
  v38 = this;
  v37 = 0;
  v7 = -2147221248;
  if ( a2 )
  {
    v8 = *(_QWORD *)&a2->Data1 - CGID_JavaParambagCompatHack;
    if ( *(_QWORD *)&a2->Data1 == CGID_JavaParambagCompatHack )
      v8 = *(_QWORD *)a2->Data4 - 0xBCEBD00AA0082BBLL;
    if ( !v8 && !a3 && a4 == 2 && (*((_BYTE *)this + 24) & 0x10) != 0 )
    {
      v9 = a5->vt == 13;
      v35 = 0;
      if ( v9 )
      {
        if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 *))a5->llVal)(a5->llVal, &IID_IPropertyBag2, &v37) >= 0 )
        {
          if ( CWebCrawler::GetRealUrl((CWebCrawler *)((char *)this - 112), *((_DWORD *)this + 62), &v35) >= 0 )
            v10 = v35;
          else
            v10 = StrDupW(&Default);
          v11 = 0;
          do
          {
            v12 = (int)v11++;
            v39[v12] = -2147467259;
            v13 = 5 * v12;
            v50[2 * v13] = 1;
            *(_QWORD *)&v50[2 * v13 + 1] = 8;
            v51[v13] = 0;
            *(GUID *)&v51[v13 + 1] = GUID_NULL;
            v14 = 3 * v12;
            v40[4 * v14] = 0;
            bstrString[v14] = 0;
          }
          while ( v11 < 7 );
          v51[0] = L"CODEBASE";
          v51[5] = L"CABBASE";
          v51[10] = L"CABINETS";
          v51[15] = L"ARCHIVE";
          v51[20] = L"USESLIBRARY";
          v51[25] = L"USESLIBRARYCODEBASE";
          v51[30] = L"USESLIBRARYVERSION";
          (*(void (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v37 + 24LL))(v37, 7, v50);
          v15 = 0;
          if ( v39[0] >= 0 && v40[0] == 8 )
          {
            v15 = bstrString[0];
            if ( bstrString[0] )
            {
              v16 = -1;
              do
                ++v16;
              while ( bstrString[0][v16] );
              if ( (_DWORD)v16 )
              {
                if ( bstrString[0][(int)v16 - 1] != 47 )
                {
                  v17 = (int)v16 + 2;
                  v18 = (unsigned __int16 *)LocalAlloc(0, 2 * v17);
                  v19 = v18;
                  if ( v18 )
                  {
                    StringCchCopyW(v18, v17, v15);
                    StringCchCatW(v19, v17, L"/");
                    SysFreeString(v15);
                    bstrString[0] = SysAllocString(v19);
                    v15 = bstrString[0];
                    LocalFree(v19);
                  }
                }
              }
            }
          }
          if ( v39[1] >= 0 && v42 == 8 )
          {
            v35 = v43;
            if ( (int)CombineBaseAndRelativeURLs(v10, v15, &v35) >= 0 )
              (*(void (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 16LL))(
                *((_QWORD *)this + 6),
                v35,
                0,
                0);
          }
          v20 = 2;
          v36 = (BSTR)2;
          do
          {
            if ( (int)v39[v20] >= 0 )
            {
              v21 = 3 * v20;
              if ( v40[12 * v20] == 8 )
              {
                v22 = bstrString[3 * v20];
                if ( v22 )
                {
                  v23 = v38;
                  do
                  {
                    v24 = *v22;
                    if ( !*v22 || (unsigned __int16)(v24 - 43) <= 1u )
                    {
                      if ( v5 )
                        v25 = v5;
                      else
                        v25 = bstrString[v21];
                      v5 = v22 + 1;
                      *v22 = 0;
                      v35 = SysAllocString(v25);
                      if ( (int)CombineBaseAndRelativeURLs(v10, v15, &v35) >= 0 )
                      {
                        v26 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64, _QWORD))(**((_QWORD **)v23 + 6) + 16LL))(
                                *((_QWORD *)v23 + 6),
                                v35,
                                0x10000000,
                                0);
                        v27 = *((_DWORD *)v23 + 54);
                        if ( v27 > 0 && v26 == 2 )
                          *((_DWORD *)v23 + 54) = v27 + 1;
                      }
                      if ( v35 )
                        SysFreeString(v35);
                      if ( !v24 )
                        break;
                    }
                    ++v22;
                  }
                  while ( v22 );
                  v20 = (__int64)v36;
                }
                v5 = 0;
              }
            }
            v36 = (BSTR)++v20;
          }
          while ( v20 != 4 );
          if ( v39[4] >= 0 && v44 == 8 && v39[5] >= 0 && v46 == 8 )
          {
            v28 = operator new(0x18u);
            if ( v28 )
            {
              *(_OWORD *)v28 = 0;
              *((_QWORD *)v28 + 2) = 0;
              SHStrDupW(psz, (LPWSTR *)v28);
              *((_DWORD *)v28 + 4) = 0;
              *((_DWORD *)v28 + 3) = -1;
              *((_DWORD *)v28 + 2) = -1;
              v36 = SysAllocString(v47);
              v29 = CombineBaseAndRelativeURLs(v10, v15, &v36);
              v30 = v36;
              if ( v29 < 0
                || (*(unsigned int (__fastcall **)(_QWORD, BSTR, void *, _QWORD))(**((_QWORD **)v38 + 10) + 16LL))(
                     *((_QWORD *)v38 + 10),
                     v36,
                     v28,
                     0) != 2 )
              {
                if ( *(_QWORD *)v28 )
                {
                  CoTaskMemFree(*(LPVOID *)v28);
                  *(_QWORD *)v28 = 0;
                }
                operator delete(v28);
                v28 = 0;
              }
              if ( v30 )
                SysFreeString(v30);
              if ( v28 )
              {
                if ( v39[6] >= 0 && v48 == 8 )
                {
                  v31 = SysStringByteLen(bstr) + 1;
                  v32 = (CHAR *)LocalAlloc(0, v31);
                  v33 = v32;
                  if ( v32 )
                  {
                    SHUnicodeToAnsi(bstr, v32, v31);
                    if ( (int)GetVersionFromString(v33, (unsigned int *)v28 + 2, (unsigned int *)v28 + 3) < 0 )
                    {
                      ResultFromKnownLastError();
                      if ( *(_QWORD *)v28 )
                      {
                        CoTaskMemFree(*(LPVOID *)v28);
                        *(_QWORD *)v28 = 0;
                      }
                      operator delete(v28);
                    }
                    LocalFree(v33);
                  }
                }
              }
            }
          }
          if ( v10 )
            LocalFree(v10);
          v7 = 0;
        }
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180021070  push    rbp
0x180021072  push    rbx
0x180021073  push    rsi
0x180021074  push    rdi
0x180021075  push    r12
0x180021077  push    r13
0x180021079  push    r14
0x18002107b  push    r15
0x18002107d  lea     rbp, [rsp-168h]
0x180021085  sub     rsp, 268h
0x18002108c  mov     rax, cs:__security_cookie
0x180021093  xor     rax, rsp
0x180021096  mov     [rbp+1A0h+var_50], rax
0x18002109d  xor     r13d, r13d
0x1800210a0  mov     [rsp+2A0h+var_248], rcx
0x1800210a5  mov     [rsp+2A0h+var_250], r13
0x1800210aa  mov     r15, rcx
0x1800210ad  mov     rcx, [rbp+1A0h+arg_20]
0x1800210b4  mov     ebx, 80040100h
0x1800210b9  test    rdx, rdx
0x1800210bc  jz      loc_1800215AE
0x1800210c2  mov     rax, [rdx]
0x1800210c5  sub     rax, cs:CGID_JavaParambagCompatHack
0x1800210cc  jnz     short loc_1800210D9
0x1800210ce  mov     rax, [rdx+8]
0x1800210d2  sub     rax, cs:qword_18002E7F0
0x1800210d9  test    rax, rax
0x1800210dc  jnz     loc_1800215AE
0x1800210e2  test    r8d, r8d
0x1800210e5  jnz     loc_1800215AE
0x1800210eb  cmp     r9d, 2
0x1800210ef  jnz     loc_1800215AE
0x1800210f5  test    byte ptr [r15+18h], 10h
0x1800210fa  jz      loc_1800215AE
0x180021100  cmp     word ptr [rcx], 0Dh
0x180021104  mov     [rsp+2A0h+var_260], r13
0x180021109  jnz     loc_1800215AE
0x18002110f  mov     rcx, [rcx+8]
0x180021113  lea     r8, [rsp+2A0h+var_250]
0x180021118  lea     rdx, IID_IPropertyBag2
0x18002111f  mov     rax, [rcx]
0x180021122  mov     rax, [rax]
0x180021125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002112a  test    eax, eax
0x18002112c  js      loc_180021598
0x180021132  mov     edx, [r15+0F8h]; int
0x180021139  lea     r8, [rsp+2A0h+var_260]; unsigned __int16 **
0x18002113e  lea     rcx, [r15-70h]; this
0x180021142  call    ?GetRealUrl@CWebCrawler@@IEAAJHPEAPEAG@Z; CWebCrawler::GetRealUrl(int,ushort * *)
0x180021147  test    eax, eax
0x180021149  jns     short loc_18002115D
0x18002114b  lea     rcx, Default; pszSrch
0x180021152  call    cs:__imp_StrDupW
0x180021158  mov     r14, rax
0x18002115b  jmp     short loc_180021162
0x18002115d  mov     r14, [rsp+2A0h+var_260]
0x180021162  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021169  mov     r9d, 1
0x18002116f  mov     r8d, r13d
0x180021172  lea     r12d, [r9+7]
0x180021176  movsxd  rdx, r8d
0x180021179  add     r8d, r9d
0x18002117c  mov     [rsp+rdx*4+2A0h+var_240], 80004005h
0x180021184  lea     rcx, [rdx+rdx*4]
0x180021188  mov     [rbp+rcx*8+1A0h+var_170], r9d
0x18002118d  mov     [rbp+rcx*8+1A0h+var_16C], r12
0x180021192  mov     [rbp+rcx*8+1A0h+var_160], r13
0x180021197  movdqu  [rbp+rcx*8+1A0h+var_158], xmm0
0x18002119d  lea     rcx, [rdx+rdx*2]
0x1800211a1  mov     [rbp+rcx*8+1A0h+var_220], r13w
0x1800211a7  mov     [rbp+rcx*8+1A0h+bstrString], r13
0x1800211ac  cmp     r8d, 7
0x1800211b0  jb      short loc_180021176
0x1800211b2  mov     rcx, [rsp+2A0h+var_250]
0x1800211b7  lea     rax, aCodebase; "CODEBASE"
0x1800211be  mov     [rbp+1A0h+var_160], rax
0x1800211c2  lea     r8, [rsp+2A0h+var_240]
0x1800211c7  mov     [rsp+2A0h+var_278], r8
0x1800211cc  lea     rax, aCabbase; "CABBASE"
0x1800211d3  mov     [rbp+1A0h+var_138], rax
0x1800211d7  lea     r8, [rbp+1A0h+var_220]
0x1800211db  lea     rax, aCabinets; "CABINETS"
0x1800211e2  mov     [rsp+2A0h+var_280], r8
0x1800211e7  mov     [rbp+1A0h+var_110], rax
0x1800211ee  lea     r8, [rbp+1A0h+var_170]
0x1800211f2  lea     rax, aArchive; "ARCHIVE"
0x1800211f9  xor     r9d, r9d
0x1800211fc  mov     [rbp+1A0h+var_E8], rax
0x180021203  lea     rax, aUseslibrary; "USESLIBRARY"
0x18002120a  mov     [rbp+1A0h+var_C0], rax
0x180021211  lea     rax, aUseslibrarycod; "USESLIBRARYCODEBASE"
0x180021218  mov     [rbp+1A0h+var_98], rax
0x18002121f  lea     rax, aUseslibraryver; "USESLIBRARYVERSION"
0x180021226  mov     [rbp+1A0h+var_70], rax
0x18002122d  lea     edx, [r9+7]
0x180021231  mov     rax, [rcx]
0x180021234  mov     rax, [rax+18h]
0x180021238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002123d  mov     rdi, r13
0x180021240  cmp     [rsp+2A0h+var_240], r13d
0x180021245  jl      loc_1800212D8
0x18002124b  cmp     [rbp+1A0h+var_220], r12w
0x180021250  jnz     loc_1800212D8
0x180021256  mov     rdi, [rbp+1A0h+bstrString]
0x18002125a  test    rdi, rdi
0x18002125d  jz      short loc_1800212D8
0x18002125f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180021263  inc     rcx
0x180021266  cmp     [rdi+rcx*2], r13w
0x18002126b  jnz     short loc_180021263
0x18002126d  test    ecx, ecx
0x18002126f  jz      short loc_1800212D8
0x180021271  movsxd  rax, ecx
0x180021274  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x18002127a  jz      short loc_1800212D8
0x18002127c  lea     eax, [rcx+2]
0x18002127f  xor     ecx, ecx; uFlags
0x180021281  movsxd  rsi, eax
0x180021284  lea     rdx, [rsi+rsi]; uBytes
0x180021288  call    cs:__imp_LocalAlloc
0x18002128e  mov     rbx, rax
0x180021291  test    rax, rax
0x180021294  jz      short loc_1800212D8
0x180021296  mov     r8, rdi; unsigned __int16 *
0x180021299  mov     rdx, rsi; unsigned __int64
0x18002129c  mov     rcx, rax; unsigned __int16 *
0x18002129f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800212a4  lea     r8, asc_18002E67C; "/"
0x1800212ab  mov     rdx, rsi; unsigned __int64
0x1800212ae  mov     rcx, rbx; unsigned __int16 *
0x1800212b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800212b6  mov     rcx, rdi; bstrString
0x1800212b9  call    cs:__imp_SysFreeString
0x1800212bf  mov     rcx, rbx; psz
0x1800212c2  call    cs:__imp_SysAllocString
0x1800212c8  mov     rcx, rbx; hMem
0x1800212cb  mov     [rbp+1A0h+bstrString], rax
0x1800212cf  mov     rdi, rax
0x1800212d2  call    cs:__imp_LocalFree
0x1800212d8  cmp     [rsp+2A0h+var_23C], r13d
0x1800212dd  jl      short loc_18002131E
0x1800212df  cmp     [rbp+1A0h+var_208], r12w
0x1800212e4  jnz     short loc_18002131E
0x1800212e6  mov     rax, [rbp+1A0h+var_200]
0x1800212ea  lea     r8, [rsp+2A0h+var_260]; unsigned __int16 **
0x1800212ef  mov     rdx, rdi; unsigned __int16 *
0x1800212f2  mov     [rsp+2A0h+var_260], rax
0x1800212f7  mov     rcx, r14; unsigned __int16 *
0x1800212fa  call    ?CombineBaseAndRelativeURLs@@YAJPEBG0PEAPEAG@Z; CombineBaseAndRelativeURLs(ushort const *,ushort const *,ushort * *)
0x1800212ff  test    eax, eax
0x180021301  js      short loc_18002131E
0x180021303  mov     rcx, [r15+30h]
0x180021307  xor     r9d, r9d
0x18002130a  mov     rdx, [rsp+2A0h+var_260]
0x18002130f  xor     r8d, r8d
0x180021312  mov     rax, [rcx]
0x180021315  mov     rax, [rax+10h]
0x180021319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002131e  mov     ebx, 2
0x180021323  mov     [rsp+2A0h+var_258], rbx
0x180021328  cmp     [rsp+rbx*4+2A0h+var_240], r13d
0x18002132d  jl      loc_180021418
0x180021333  lea     r12, [rbx+rbx*2]
0x180021337  mov     eax, 8
0x18002133c  cmp     [rbp+r12*8+1A0h+var_220], ax
0x180021342  jnz     loc_180021418
0x180021348  mov     rsi, [rbp+r12*8+1A0h+bstrString]
0x18002134d  xor     eax, eax
0x18002134f  test    rsi, rsi
0x180021352  jz      loc_180021415
0x180021358  mov     rbx, [rsp+2A0h+var_248]
0x18002135d  movzx   r15d, word ptr [rsi]
0x180021361  test    r15w, r15w
0x180021365  jz      short loc_18002137B
0x180021367  lea     eax, [r15-2Bh]
0x18002136b  mov     ecx, 1
0x180021370  cmp     ax, cx
0x180021373  ja      loc_180021404
0x180021379  xor     eax, eax
0x18002137b  test    r13, r13
0x18002137e  jnz     short loc_180021387
0x180021380  mov     rcx, [rbp+r12*8+1A0h+bstrString]
0x180021385  jmp     short loc_18002138A
0x180021387  mov     rcx, r13; psz
0x18002138a  lea     r13, [rsi+2]
0x18002138e  mov     [rsi], ax
0x180021391  call    cs:__imp_SysAllocString
0x180021397  lea     r8, [rsp+2A0h+var_260]; unsigned __int16 **
0x18002139c  mov     rdx, rdi; unsigned __int16 *
0x18002139f  mov     rcx, r14; unsigned __int16 *
0x1800213a2  mov     [rsp+2A0h+var_260], rax
0x1800213a7  call    ?CombineBaseAndRelativeURLs@@YAJPEBG0PEAPEAG@Z; CombineBaseAndRelativeURLs(ushort const *,ushort const *,ushort * *)
0x1800213ac  test    eax, eax
0x1800213ae  js      short loc_1800213E7
0x1800213b0  mov     rcx, [rbx+30h]
0x1800213b4  xor     r9d, r9d
0x1800213b7  mov     rdx, [rsp+2A0h+var_260]
0x1800213bc  mov     r8d, 10000000h
0x1800213c2  mov     rax, [rcx]
0x1800213c5  mov     rax, [rax+10h]
0x1800213c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213ce  mov     ecx, eax
0x1800213d0  mov     eax, [rbx+0D8h]
0x1800213d6  test    eax, eax
0x1800213d8  jle     short loc_1800213E7
0x1800213da  cmp     ecx, 2
0x1800213dd  jnz     short loc_1800213E7
0x1800213df  inc     eax
0x1800213e1  mov     [rbx+0D8h], eax
0x1800213e7  mov     rax, [rsp+2A0h+var_260]
0x1800213ec  test    rax, rax
0x1800213ef  jz      short loc_1800213FA
0x1800213f1  mov     rcx, rax; bstrString
0x1800213f4  call    cs:__imp_SysFreeString
0x1800213fa  xor     eax, eax
0x1800213fc  test    r15w, r15w
0x180021400  jz      short loc_180021410
0x180021402  jmp     short loc_180021406
0x180021404  xor     eax, eax
0x180021406  add     rsi, 2
0x18002140a  jnz     loc_18002135D
0x180021410  mov     rbx, [rsp+2A0h+var_258]
0x180021415  xor     r13d, r13d
0x180021418  inc     rbx
0x18002141b  mov     [rsp+2A0h+var_258], rbx
0x180021420  cmp     rbx, 4
0x180021424  jnz     loc_180021328
0x18002142a  cmp     [rsp+2A0h+var_230], r13d
0x18002142f  jl      loc_180021587
0x180021435  lea     r12d, [rbx+4]
0x180021439  cmp     [rbp+1A0h+var_1C0], r12w
0x18002143e  jnz     loc_180021587
0x180021444  cmp     [rsp+2A0h+var_22C], r13d
0x180021449  jl      loc_180021587
0x18002144f  cmp     [rbp+1A0h+var_1A8], r12w
0x180021454  jnz     loc_180021587
0x18002145a  lea     ecx, [rbx+14h]; dwBytes
0x18002145d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021462  mov     rbx, rax
0x180021465  test    rax, rax
0x180021468  jz      loc_180021587
0x18002146e  xorps   xmm0, xmm0
0x180021471  xor     eax, eax
0x180021473  movups  xmmword ptr [rbx], xmm0
0x180021476  mov     [rbx+10h], rax
0x18002147a  mov     rdx, rbx; ppwsz
0x18002147d  mov     rcx, [rbp+1A0h+psz]; psz
0x180021481  call    cs:__imp_SHStrDupW
0x180021487  or      eax, 0FFFFFFFFh
0x18002148a  mov     [rbx+10h], r13d
0x18002148e  mov     [rbx+0Ch], eax
0x180021491  mov     [rbx+8], eax
0x180021494  mov     rcx, [rbp+1A0h+var_1A0]; psz
0x180021498  call    cs:__imp_SysAllocString
0x18002149e  lea     r8, [rsp+2A0h+var_258]; unsigned __int16 **
0x1800214a3  mov     rdx, rdi; unsigned __int16 *
0x1800214a6  mov     rcx, r14; unsigned __int16 *
0x1800214a9  mov     [rsp+2A0h+var_258], rax
0x1800214ae  call    ?CombineBaseAndRelativeURLs@@YAJPEBG0PEAPEAG@Z; CombineBaseAndRelativeURLs(ushort const *,ushort const *,ushort * *)
0x1800214b3  mov     rdi, [rsp+2A0h+var_258]
0x1800214b8  test    eax, eax
0x1800214ba  js      short loc_1800214DF
0x1800214bc  mov     rcx, [rsp+2A0h+var_248]
0x1800214c1  xor     r9d, r9d
0x1800214c4  mov     r8, rbx
0x1800214c7  mov     rdx, rdi
0x1800214ca  mov     rcx, [rcx+50h]
0x1800214ce  mov     rax, [rcx]
0x1800214d1  mov     rax, [rax+10h]
0x1800214d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214da  cmp     eax, 2
0x1800214dd  jz      short loc_1800214FB
0x1800214df  mov     rcx, [rbx]; pv
0x1800214e2  test    rcx, rcx
0x1800214e5  jz      short loc_1800214F0
0x1800214e7  call    cs:__imp_CoTaskMemFree
0x1800214ed  mov     [rbx], r13
0x1800214f0  mov     rcx, rbx; lpMem
0x1800214f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800214f8  mov     rbx, r13
0x1800214fb  test    rdi, rdi
0x1800214fe  jz      short loc_180021509
0x180021500  mov     rcx, rdi; bstrString
0x180021503  call    cs:__imp_SysFreeString
0x180021509  test    rbx, rbx
0x18002150c  jz      short loc_180021587
0x18002150e  cmp     [rsp+2A0h+var_228], r13d
0x180021513  jl      short loc_180021587
0x180021515  cmp     [rbp+1A0h+var_190], r12w
0x18002151a  jnz     short loc_180021587
0x18002151c  mov     rcx, [rbp+1A0h+bstr]; bstr
0x180021520  call    cs:__imp_SysStringByteLen
0x180021526  xor     ecx, ecx; uFlags
0x180021528  lea     esi, [rax+1]
0x18002152b  movsxd  rdx, esi; uBytes
0x18002152e  call    cs:__imp_LocalAlloc
0x180021534  mov     rdi, rax
0x180021537  test    rax, rax
0x18002153a  jz      short loc_180021587
0x18002153c  mov     rcx, [rbp+1A0h+bstr]; pwszSrc
  ... truncated ...
```
