# CHostObj::GetObjectA(ushort *,ushort *,ushort *,IDispatch * *)

- ea: `0x14000f700`
- end: `0x14000faed`
- name: `?GetObjectA@CHostObj@@UEAAJPEAG00PEAPEAUIDispatch@@@Z`
- size: `1005`
- prototype: `__int64 __usercall@<rax>(CHostObj *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, struct IDispatch **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140009a90`
- `0x14000a098`
- `0x14000e9f4`
- `0x14000f2f0`
- `0x14000f700`
- `0x1400144dc`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `ole32!MkParseDisplayName` at `0x14000f9a9`
- `ole32!MkParseDisplayName` at `0x14000f9a9`
- `ole32!CreateBindCtx` at `0x14000f8e1`
- `ole32!CreateBindCtx` at `0x14000f8e1`

## string_xrefs

- `0x14000f778`: `WScript.CreateObject`
- `0x14000faa8`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::GetObjectA(
        CHostObj *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        struct IDispatch **a5)
{
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  HRESULT v13; // edi
  LPBC v14; // rcx
  int v15; // ebx
  LPBC v16; // rcx
  void (*Release)(void); // rax
  void (*v18)(void); // rax
  __int64 v19; // rdx
  struct IMoniker *v20; // rcx
  unsigned __int16 *v21; // rax
  void (*v22)(void); // rax
  HRESULT v23; // eax
  int v24; // eax
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  LPMONIKER ppmk; // [rsp+38h] [rbp-C8h] BYREF
  struct IDispatch *v27; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pchEaten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v30; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR szUserName[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( !a5 )
    return 2147500035LL;
  v10 = *((_QWORD *)this + 16);
  v11 = *(_QWORD *)(v10 + 32);
  if ( v11 )
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
  else
    v12 = *(_DWORD *)(v10 + 8);
  if ( v12 )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Fu, a3);
    return 2147942405LL;
  }
  if ( a2 )
    a2 &= -(__int64)(*(_WORD *)a2 != 0);
  if ( a4 )
    a4 &= -(__int64)(*(_WORD *)a4 != 0);
  if ( a3 )
    a3 &= -(__int64)(*(_WORD *)a3 != 0);
  v27 = 0;
  v30 = 0;
  if ( a3 )
  {
    ppbc = 0;
    result = CHostObj::CreateObjectHelper(this, (unsigned __int16 *)a3, &v30, (LPVOID *)&ppbc);
    if ( (int)result < 0 )
      return result;
    if ( a2 )
    {
      ppmk = 0;
      v13 = ((__int64 (__fastcall *)(LPBC, GUID *, LPMONIKER *))ppbc->lpVtbl->QueryInterface)(
              ppbc,
              &IID_IPersistFile,
              &ppmk);
      if ( v13 < 0 )
      {
        v14 = ppbc;
LABEL_19:
        ((void (__fastcall *)(LPBC))v14->lpVtbl->Release)(v14);
        return (unsigned int)v13;
      }
      v15 = ((__int64 (__fastcall *)(LPMONIKER, unsigned __int64, __int64))ppmk->lpVtbl->Load)(ppmk, a2, 2);
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
      if ( v15 < 0 )
      {
        v16 = ppbc;
LABEL_23:
        Release = (void (*)(void))v16->lpVtbl->Release;
        goto LABEL_24;
      }
    }
    v15 = ((__int64 (__fastcall *)(LPBC, GUID *, struct IDispatch **))ppbc->lpVtbl->QueryInterface)(
            ppbc,
            &IID_IDispatch,
            &v27);
    v18 = (void (*)(void))ppbc->lpVtbl->Release;
    goto LABEL_60;
  }
  if ( !a2 )
    return 2147942487LL;
  ppbc = 0;
  v13 = CreateBindCtx(0, &ppbc);
  if ( v13 < 0 )
  {
    v14 = ppbc;
    if ( !ppbc )
      return (unsigned int)v13;
    goto LABEL_19;
  }
  v20 = (struct IMoniker *)*(unsigned __int16 *)a2;
  ppmk = 0;
  if ( !(_WORD)v20 )
    goto LABEL_36;
  v21 = (unsigned __int16 *)a2;
  while ( (_WORD)v20 != 58 )
  {
    v20 = (struct IMoniker *)*++v21;
    if ( !(_WORD)v20 )
      goto LABEL_36;
  }
  if ( v21 && (((unsigned __int64)v21 - a2) & 0xFFFFFFFFFFFFFFFEuLL) != 2 )
  {
    v23 = CreateAMoniker(v20, (const unsigned __int16 *)a2, &ppmk);
  }
  else
  {
LABEL_36:
    v29 = 0;
    v15 = FileNameToFullPathName((LPCWCH)a2, v19, szUserName, &v29);
    if ( v15 < 0 )
    {
      if ( !ppmk )
      {
LABEL_40:
        if ( !ppbc )
          return (unsigned int)v15;
        Release = (void (*)(void))ppbc->lpVtbl->Release;
LABEL_24:
        Release();
        return (unsigned int)v15;
      }
      v22 = (void (*)(void))ppmk->lpVtbl->Release;
LABEL_39:
      v22();
      goto LABEL_40;
    }
    pchEaten = 0;
    v23 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
  }
  v15 = v23;
  if ( v23 < 0 )
  {
    if ( !ppmk )
      goto LABEL_40;
    v22 = (void (*)(void))ppmk->lpVtbl->Release;
    goto LABEL_39;
  }
  v24 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, struct IDispatch **))ppmk->lpVtbl->BindToObject)(
          ppmk,
          ppbc,
          0,
          &IID_IDispatch,
          &v27);
  v15 = v24;
  if ( v24 == -2146697211 )
  {
    v15 = -2147221014;
    goto LABEL_52;
  }
  if ( v24 < 0 )
  {
LABEL_52:
    if ( ppmk )
      ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    v16 = ppbc;
    if ( !ppbc )
      return (unsigned int)v15;
    goto LABEL_23;
  }
  v15 = ((__int64 (__fastcall *)(LPMONIKER, struct _GUID *))ppmk->lpVtbl->GetClassID)(ppmk, &v30);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  if ( !ppbc )
    goto LABEL_61;
  v18 = (void (*)(void))ppbc->lpVtbl->Release;
LABEL_60:
  v18();
LABEL_61:
  if ( v15 < 0 )
    return (unsigned int)v15;
  if ( a4 && (int)ConnectObject(&v30, v27, a4) < 0 )
  {
    ((void (__fastcall *)(struct IDispatch *))v27->lpVtbl->Release)(v27);
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
    return 2147614729LL;
  }
  else
  {
    *a5 = v27;
    return 0;
  }
}

```

## disassembly

```asm
0x14000f700  push    rbp
0x14000f702  push    rbx
0x14000f703  push    rsi
0x14000f704  push    rdi
0x14000f705  push    r12
0x14000f707  push    r14
0x14000f709  push    r15
0x14000f70b  lea     rbp, [rsp-190h]
0x14000f713  sub     rsp, 290h
0x14000f71a  mov     rax, cs:__security_cookie
0x14000f721  xor     rax, rsp
0x14000f724  mov     [rbp+1C0h+var_40], rax
0x14000f72b  mov     r15, [rbp+1C0h+arg_20]
0x14000f732  xor     r12d, r12d
0x14000f735  mov     rsi, r9
0x14000f738  mov     rdi, r8
0x14000f73b  mov     rbx, rdx
0x14000f73e  mov     r14, rcx
0x14000f741  test    r15, r15
0x14000f744  jnz     short loc_14000F750
0x14000f746  mov     eax, 80004003h
0x14000f74b  jmp     loc_14000FACC
0x14000f750  mov     rax, [rcx+80h]
0x14000f757  mov     rcx, [rax+20h]
0x14000f75b  test    rcx, rcx
0x14000f75e  jz      short loc_14000F76E
0x14000f760  mov     rax, [rcx]
0x14000f763  mov     rax, [rax+18h]
0x14000f767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f76c  jmp     short loc_14000F771
0x14000f76e  mov     eax, [rax+8]
0x14000f771  test    eax, eax
0x14000f773  jz      short loc_14000F79B
0x14000f775  mov     r9, rdi
0x14000f778  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000f77f  mov     r8d, 0C1Fh; unsigned int
0x14000f785  lea     rcx, IID_IHost; struct _GUID *
0x14000f78c  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000f791  mov     eax, 80070005h
0x14000f796  jmp     loc_14000FACC
0x14000f79b  test    rbx, rbx
0x14000f79e  jz      short loc_14000F7AC
0x14000f7a0  movzx   eax, word ptr [rbx]
0x14000f7a3  neg     ax
0x14000f7a6  sbb     rcx, rcx
0x14000f7a9  and     rbx, rcx
0x14000f7ac  test    rsi, rsi
0x14000f7af  jz      short loc_14000F7BD
0x14000f7b1  movzx   eax, word ptr [rsi]
0x14000f7b4  neg     ax
0x14000f7b7  sbb     rcx, rcx
0x14000f7ba  and     rsi, rcx
0x14000f7bd  test    rdi, rdi
0x14000f7c0  jz      short loc_14000F7CE
0x14000f7c2  movzx   eax, word ptr [rdi]
0x14000f7c5  neg     ax
0x14000f7c8  sbb     rdx, rdx
0x14000f7cb  and     rdi, rdx
0x14000f7ce  mov     [rsp+2C0h+var_280], r12
0x14000f7d3  xorps   xmm0, xmm0
0x14000f7d6  movups  xmmword ptr [rsp+2C0h+var_268.Data1], xmm0
0x14000f7db  test    rdi, rdi
0x14000f7de  jz      loc_14000F8C6
0x14000f7e4  lea     r9, [rsp+2C0h+ppbc]; struct IUnknown **
0x14000f7e9  mov     [rsp+2C0h+ppbc], r12
0x14000f7ee  lea     r8, [rsp+2C0h+var_268]; struct _GUID *
0x14000f7f3  mov     rdx, rdi; unsigned __int16 *
0x14000f7f6  mov     rcx, r14; this
0x14000f7f9  call    ?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z; CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)
0x14000f7fe  test    eax, eax
0x14000f800  js      loc_14000FACC
0x14000f806  test    rbx, rbx
0x14000f809  jz      loc_14000F897
0x14000f80f  mov     rcx, [rsp+2C0h+ppbc]
0x14000f814  lea     r8, [rsp+2C0h+ppmk]
0x14000f819  mov     [rsp+2C0h+ppmk], r12
0x14000f81e  lea     rdx, IID_IPersistFile
0x14000f825  mov     rax, [rcx]
0x14000f828  mov     rax, [rax]
0x14000f82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f830  mov     edi, eax
0x14000f832  test    eax, eax
0x14000f834  jns     short loc_14000F84E
0x14000f836  mov     rcx, [rsp+2C0h+ppbc]
0x14000f83b  mov     rdx, [rcx]
0x14000f83e  mov     rax, [rdx+10h]
0x14000f842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f847  mov     eax, edi
0x14000f849  jmp     loc_14000FACC
0x14000f84e  mov     rcx, [rsp+2C0h+ppmk]
0x14000f853  mov     r8d, 2
0x14000f859  mov     rdx, rbx
0x14000f85c  mov     rax, [rcx]
0x14000f85f  mov     rax, [rax+28h]
0x14000f863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f868  mov     rcx, [rsp+2C0h+ppmk]
0x14000f86d  mov     ebx, eax
0x14000f86f  mov     rdx, [rcx]
0x14000f872  mov     rax, [rdx+10h]
0x14000f876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f87b  test    ebx, ebx
0x14000f87d  jns     short loc_14000F897
0x14000f87f  mov     rcx, [rsp+2C0h+ppbc]
0x14000f884  mov     rdx, [rcx]
0x14000f887  mov     rax, [rdx+10h]
0x14000f88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f890  mov     eax, ebx
0x14000f892  jmp     loc_14000FACC
0x14000f897  mov     rcx, [rsp+2C0h+ppbc]
0x14000f89c  lea     r8, [rsp+2C0h+var_280]
0x14000f8a1  lea     rdx, IID_IDispatch
0x14000f8a8  mov     rax, [rcx]
0x14000f8ab  mov     rax, [rax]
0x14000f8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f8b3  mov     rcx, [rsp+2C0h+ppbc]
0x14000f8b8  mov     ebx, eax
0x14000f8ba  mov     rdx, [rcx]
0x14000f8bd  mov     rax, [rdx+10h]
0x14000f8c1  jmp     loc_14000FA69
0x14000f8c6  test    rbx, rbx
0x14000f8c9  jnz     short loc_14000F8D5
0x14000f8cb  mov     eax, 80070057h
0x14000f8d0  jmp     loc_14000FACC
0x14000f8d5  lea     rdx, [rsp+2C0h+ppbc]; ppbc
0x14000f8da  mov     [rsp+2C0h+ppbc], r12
0x14000f8df  xor     ecx, ecx; reserved
0x14000f8e1  call    cs:__imp_CreateBindCtx
0x14000f8e7  mov     edi, eax
0x14000f8e9  test    eax, eax
0x14000f8eb  jns     short loc_14000F900
0x14000f8ed  mov     rcx, [rsp+2C0h+ppbc]
0x14000f8f2  test    rcx, rcx
0x14000f8f5  jz      loc_14000F847
0x14000f8fb  jmp     loc_14000F83B
0x14000f900  movzx   ecx, word ptr [rbx]; struct IMoniker *
0x14000f903  mov     [rsp+2C0h+ppmk], r12
0x14000f908  test    cx, cx
0x14000f90b  jz      short loc_14000F922
0x14000f90d  mov     rax, rbx
0x14000f910  cmp     cx, 3Ah ; ':'
0x14000f914  jz      short loc_14000F96F
0x14000f916  add     rax, 2
0x14000f91a  movzx   ecx, word ptr [rax]
0x14000f91d  test    cx, cx
0x14000f920  jnz     short loc_14000F910
0x14000f922  lea     r9, [rsp+2C0h+var_270]; unsigned __int16 **
0x14000f927  mov     [rsp+2C0h+var_270], r12
0x14000f92c  lea     r8, [rsp+2C0h+szUserName]; unsigned __int16 *
0x14000f931  mov     rcx, rbx; lpWideCharStr
0x14000f934  call    ?FileNameToFullPathName@@YAJPEBGKPEAGPEAPEAG@Z; FileNameToFullPathName(ushort const *,ulong,ushort *,ushort * *)
0x14000f939  mov     ebx, eax
0x14000f93b  test    eax, eax
0x14000f93d  jns     short loc_14000F990
0x14000f93f  mov     rcx, [rsp+2C0h+ppmk]
0x14000f944  test    rcx, rcx
0x14000f947  jz      short loc_14000F955
0x14000f949  mov     rdx, [rcx]
0x14000f94c  mov     rax, [rdx+10h]
0x14000f950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f955  mov     rcx, [rsp+2C0h+ppbc]
0x14000f95a  test    rcx, rcx
0x14000f95d  jz      loc_14000F890
0x14000f963  mov     rax, [rcx]
0x14000f966  mov     rax, [rax+10h]
0x14000f96a  jmp     loc_14000F88B
0x14000f96f  test    rax, rax
0x14000f972  jz      short loc_14000F922
0x14000f974  sub     rax, rbx
0x14000f977  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000f97b  cmp     rax, 2
0x14000f97f  jz      short loc_14000F922
0x14000f981  lea     r8, [rsp+2C0h+ppmk]; struct IMoniker **
0x14000f986  mov     rdx, rbx; unsigned __int16 *
0x14000f989  call    ?CreateAMoniker@@YAJPEAUIMoniker@@PEBGPEAPEAU1@@Z; CreateAMoniker(IMoniker *,ushort const *,IMoniker * *)
0x14000f98e  jmp     short loc_14000F9AF
0x14000f990  mov     rcx, [rsp+2C0h+ppbc]; pbc
0x14000f995  lea     r9, [rsp+2C0h+ppmk]; ppmk
0x14000f99a  lea     r8, [rsp+2C0h+pchEaten]; pchEaten
0x14000f99f  mov     [rsp+2C0h+pchEaten], r12d
0x14000f9a4  lea     rdx, [rsp+2C0h+szUserName]; szUserName
0x14000f9a9  call    cs:__imp_MkParseDisplayName
0x14000f9af  mov     rcx, [rsp+2C0h+ppmk]
0x14000f9b4  mov     ebx, eax
0x14000f9b6  test    eax, eax
0x14000f9b8  jns     short loc_14000F9C8
0x14000f9ba  test    rcx, rcx
0x14000f9bd  jz      short loc_14000F955
0x14000f9bf  mov     rax, [rcx]
0x14000f9c2  mov     rax, [rax+10h]
0x14000f9c6  jmp     short loc_14000F950
0x14000f9c8  mov     rax, [rcx]
0x14000f9cb  lea     rdx, [rsp+2C0h+var_280]
0x14000f9d0  mov     [rsp+2C0h+var_2A0], rdx
0x14000f9d5  lea     r9, IID_IDispatch
0x14000f9dc  mov     rdx, [rsp+2C0h+ppbc]
0x14000f9e1  xor     r8d, r8d
0x14000f9e4  mov     rax, [rax+40h]
0x14000f9e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9ed  mov     ebx, eax
0x14000f9ef  cmp     eax, 800C0005h
0x14000f9f4  jnz     short loc_14000F9FD
0x14000f9f6  mov     ebx, 800401EAh
0x14000f9fb  jmp     short loc_14000FA01
0x14000f9fd  test    eax, eax
0x14000f9ff  jns     short loc_14000FA2A
0x14000fa01  mov     rcx, [rsp+2C0h+ppmk]
0x14000fa06  test    rcx, rcx
0x14000fa09  jz      short loc_14000FA17
0x14000fa0b  mov     rax, [rcx]
0x14000fa0e  mov     rax, [rax+10h]
0x14000fa12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa17  mov     rcx, [rsp+2C0h+ppbc]
0x14000fa1c  test    rcx, rcx
0x14000fa1f  jz      loc_14000F890
0x14000fa25  jmp     loc_14000F884
0x14000fa2a  mov     rcx, [rsp+2C0h+ppmk]
0x14000fa2f  lea     rdx, [rsp+2C0h+var_268]
0x14000fa34  mov     rax, [rcx]
0x14000fa37  mov     rax, [rax+18h]
0x14000fa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa40  mov     rcx, [rsp+2C0h+ppmk]
0x14000fa45  mov     ebx, eax
0x14000fa47  test    rcx, rcx
0x14000fa4a  jz      short loc_14000FA58
0x14000fa4c  mov     rax, [rcx]
0x14000fa4f  mov     rax, [rax+10h]
0x14000fa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa58  mov     rcx, [rsp+2C0h+ppbc]
0x14000fa5d  test    rcx, rcx
0x14000fa60  jz      short loc_14000FA6E
0x14000fa62  mov     rax, [rcx]
0x14000fa65  mov     rax, [rax+10h]
0x14000fa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa6e  test    ebx, ebx
0x14000fa70  js      loc_14000F890
0x14000fa76  test    rsi, rsi
0x14000fa79  jz      short loc_14000FAC2
0x14000fa7b  mov     rdx, [rsp+2C0h+var_280]
0x14000fa80  lea     rcx, [rsp+2C0h+var_268]
0x14000fa85  mov     r8, rsi
0x14000fa88  call    ConnectObject
0x14000fa8d  test    eax, eax
0x14000fa8f  jns     short loc_14000FAC2
0x14000fa91  mov     rcx, [rsp+2C0h+var_280]
0x14000fa96  mov     rax, [rcx]
0x14000fa99  mov     rax, [rax+10h]
0x14000fa9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000faa2  mov     r8d, 0C1Eh; unsigned int
0x14000faa8  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000faaf  lea     rcx, IID_IHost; struct _GUID *
0x14000fab6  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000fabb  mov     eax, 80020009h
0x14000fac0  jmp     short loc_14000FACC
0x14000fac2  mov     rax, [rsp+2C0h+var_280]
0x14000fac7  mov     [r15], rax
0x14000faca  xor     eax, eax
0x14000facc  mov     rcx, [rbp+1C0h+var_40]
0x14000fad3  xor     rcx, rsp; StackCookie
0x14000fad6  call    __security_check_cookie
0x14000fadb  add     rsp, 290h
0x14000fae2  pop     r15
0x14000fae4  pop     r14
0x14000fae6  pop     r12
0x14000fae8  pop     rdi
0x14000fae9  pop     rsi
0x14000faea  pop     rbx
0x14000faeb  pop     rbp
0x14000faec  retn
```
