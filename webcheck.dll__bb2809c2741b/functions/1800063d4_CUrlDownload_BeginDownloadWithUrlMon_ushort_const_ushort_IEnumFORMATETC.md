# CUrlDownload::BeginDownloadWithUrlMon(ushort const *,ushort *,IEnumFORMATETC *)

- ea: `0x1800063d4`
- end: `0x18000665d`
- name: `?BeginDownloadWithUrlMon@CUrlDownload@@IEAAJPEBGPEAGPEAUIEnumFORMATETC@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CUrlDownload *__hidden this, const unsigned __int16 *, unsigned __int16 *, struct IEnumFORMATETC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800060f8`

## callees

- `0x1800063d4`
- `0x180007a54`
- `0x1800085c0`
- `0x18001ba08`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!StrDupW` at `0x1800064d1`
- `SHLWAPI!StrDupW` at `0x1800064d1`
- `ole32!CreateBindCtx` at `0x1800064f2`
- `ole32!CreateBindCtx` at `0x1800064f2`
- `urlmon!CreateURLMonikerEx` at `0x18000641b`
- `urlmon!CreateURLMonikerEx` at `0x18000641b`
- `urlmon!RegisterBindStatusCallback` at `0x180006513`
- `urlmon!RegisterBindStatusCallback` at `0x180006513`

## pseudocode

```c
__int64 __fastcall CUrlDownload::BeginDownloadWithUrlMon(
        CUrlDownload *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IEnumFORMATETC *a4)
{
  HRESULT v6; // edi
  __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  BOOL v14; // edx
  LPMONIKER v15; // rcx
  __int64 v17; // rcx
  LPMONIKER ppmk; // [rsp+30h] [rbp-10h] BYREF
  __int64 v19; // [rsp+38h] [rbp-8h] BYREF
  LPBC ppbc; // [rsp+78h] [rbp+38h] BYREF

  v19 = 0;
  ppmk = 0;
  ppbc = 0;
  v6 = CreateURLMonikerEx(0, a2, &ppmk, 1u);
  if ( v6 >= 0 )
  {
    v7 = *((_QWORD *)this + 20);
    if ( v7 )
    {
      *(_QWORD *)(v7 + 80) = 0;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 16LL))(*((_QWORD *)this + 20));
      *((_QWORD *)this + 20) = 0;
    }
    v8 = operator new(0x60u);
    v9 = v8;
    if ( v8 )
    {
      v10 = *((_DWORD *)this + 180);
      v11 = *((_DWORD *)this + 179);
      *v8 = &CUrlDownload_BSC::`vftable'{for `IBindStatusCallback'};
      v8[1] = &CUrlDownload_BSC::`vftable'{for `IHttpNegotiate'};
      v8[2] = &CUrlDownload_BSC::`vftable'{for `IAuthenticate'};
      v8[5] = 0;
      v8[6] = 0;
      v8[7] = 0;
      _InterlockedAdd((volatile signed __int32 *)&g_cObj, 1u);
      *((_DWORD *)v8 + 6) = 1;
      *((_DWORD *)v8 + 16) = v11;
      *((_DWORD *)v8 + 17) = v10;
      if ( a3 )
      {
        v8[6] = StrDupW(a3);
        if ( *((_DWORD *)v9 + 16) != 1 )
          *((_DWORD *)v9 + 16) = 1;
      }
      *((_QWORD *)this + 20) = v9;
      v6 = CreateBindCtx(0, &ppbc);
      if ( v6 >= 0 )
      {
        v6 = RegisterBindStatusCallback(ppbc, *((IBindStatusCallback **)this + 20), 0, 0);
        if ( v6 >= 0 )
        {
          *(_QWORD *)(*((_QWORD *)this + 20) + 80LL) = this;
          *((_DWORD *)this + 42) = 1;
          *((_DWORD *)this + 178) = -2146693121;
          CUrlDownload::StartTimer(this);
          v12 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, __int64 *))ppmk->lpVtbl->BindToStorage)(
                  ppmk,
                  ppbc,
                  0,
                  &IID_IStream,
                  &v19);
          v13 = *((_DWORD *)this + 178);
          if ( v13 != -2146693121 )
          {
            v14 = v12 < 0 || v13 < 0;
            CUrlDownload::OnDownloadComplete(this, v14);
          }
          v15 = ppmk;
          *((_DWORD *)this + 178) = 0;
          ((void (__fastcall *)(LPMONIKER))v15->lpVtbl->Release)(v15);
          ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          return 0;
        }
      }
    }
    else
    {
      *((_QWORD *)this + 20) = 0;
      v6 = -2147024882;
    }
  }
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( ppmk )
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v17 = *((_QWORD *)this + 20);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 20) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800063d4  mov     [rsp-18h+arg_0], rbx
0x1800063d9  mov     [rsp-18h+arg_8], rsi
0x1800063de  mov     [rsp-18h+ppbc], r9
0x1800063e3  push    rbp
0x1800063e4  push    rdi
0x1800063e5  push    r15
0x1800063e7  mov     rbp, rsp
0x1800063ea  sub     rsp, 40h
0x1800063ee  mov     rsi, r8
0x1800063f1  mov     [rbp+var_8], 0
0x1800063f9  mov     rbx, rcx
0x1800063fc  mov     [rbp+ppmk], 0
0x180006404  mov     r15d, 1
0x18000640a  mov     [rbp+ppbc], 0
0x180006412  mov     r9d, r15d; dwFlags
0x180006415  lea     r8, [rbp+ppmk]; ppmk
0x180006419  xor     ecx, ecx; pMkCtx
0x18000641b  call    cs:__imp_CreateURLMonikerEx
0x180006421  mov     edi, eax
0x180006423  test    eax, eax
0x180006425  js      loc_1800065E6
0x18000642b  mov     rax, [rbx+0A0h]
0x180006432  test    rax, rax
0x180006435  jz      short loc_18000645D
0x180006437  mov     qword ptr [rax+50h], 0
0x18000643f  mov     rcx, [rbx+0A0h]
0x180006446  mov     rax, [rcx]
0x180006449  mov     rax, [rax+10h]
0x18000644d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006452  mov     qword ptr [rbx+0A0h], 0
0x18000645d  mov     ecx, 60h ; '`'; dwBytes
0x180006462  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006467  mov     rdi, rax
0x18000646a  test    rax, rax
0x18000646d  jz      loc_1800065D6
0x180006473  mov     edx, [rbx+2D0h]
0x180006479  lea     rax, ??_7CUrlDownload_BSC@@6BIBindStatusCallback@@@; const CUrlDownload_BSC::`vftable'{for `IBindStatusCallback'}
0x180006480  mov     ecx, [rbx+2CCh]
0x180006486  mov     [rdi], rax
0x180006489  lea     rax, ??_7CUrlDownload_BSC@@6BIHttpNegotiate@@@; const CUrlDownload_BSC::`vftable'{for `IHttpNegotiate'}
0x180006490  mov     [rdi+8], rax
0x180006494  lea     rax, ??_7CUrlDownload_BSC@@6BIAuthenticate@@@; const CUrlDownload_BSC::`vftable'{for `IAuthenticate'}
0x18000649b  mov     [rdi+10h], rax
0x18000649f  mov     qword ptr [rdi+28h], 0
0x1800064a7  mov     qword ptr [rdi+30h], 0
0x1800064af  mov     qword ptr [rdi+38h], 0
0x1800064b7  lock add cs:?g_cObj@@3KA, r15d; ulong g_cObj
0x1800064bf  mov     [rdi+18h], r15d
0x1800064c3  mov     [rdi+40h], ecx
0x1800064c6  mov     [rdi+44h], edx
0x1800064c9  test    rsi, rsi
0x1800064cc  jz      short loc_1800064E5
0x1800064ce  mov     rcx, rsi; pszSrch
0x1800064d1  call    cs:__imp_StrDupW
0x1800064d7  mov     [rdi+30h], rax
0x1800064db  cmp     [rdi+40h], r15d
0x1800064df  jz      short loc_1800064E5
0x1800064e1  mov     [rdi+40h], r15d
0x1800064e5  lea     rdx, [rbp+ppbc]; ppbc
0x1800064e9  mov     [rbx+0A0h], rdi
0x1800064f0  xor     ecx, ecx; reserved
0x1800064f2  call    cs:__imp_CreateBindCtx
0x1800064f8  mov     edi, eax
0x1800064fa  test    eax, eax
0x1800064fc  js      loc_1800065E6
0x180006502  mov     rdx, [rbx+0A0h]; pBSCb
0x180006509  xor     r9d, r9d; dwReserved
0x18000650c  mov     rcx, [rbp+ppbc]; pBC
0x180006510  xor     r8d, r8d; ppBSCBPrev
0x180006513  call    cs:__imp_RegisterBindStatusCallback
0x180006519  mov     edi, eax
0x18000651b  test    eax, eax
0x18000651d  js      loc_1800065E6
0x180006523  mov     rax, [rbx+0A0h]
0x18000652a  mov     rcx, rbx; this
0x18000652d  mov     [rax+50h], rbx
0x180006531  mov     [rbx+0A8h], r15d
0x180006538  mov     dword ptr [rbx+2C8h], 800C0FFFh
0x180006542  call    ?StartTimer@CUrlDownload@@IEAAXXZ; CUrlDownload::StartTimer(void)
0x180006547  mov     rcx, [rbp+ppmk]
0x18000654b  lea     rdx, [rbp+var_8]
0x18000654f  mov     [rsp+40h+var_20], rdx
0x180006554  lea     r9, IID_IStream
0x18000655b  mov     rdx, [rbp+ppbc]
0x18000655f  xor     r8d, r8d
0x180006562  mov     rax, [rcx]
0x180006565  mov     rax, [rax+48h]
0x180006569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656e  mov     ecx, [rbx+2C8h]
0x180006574  cmp     ecx, 800C0FFFh
0x18000657a  jz      short loc_180006593
0x18000657c  test    eax, eax
0x18000657e  js      short loc_180006588
0x180006580  test    ecx, ecx
0x180006582  js      short loc_180006588
0x180006584  xor     edx, edx
0x180006586  jmp     short loc_18000658B
0x180006588  mov     edx, r15d; int
0x18000658b  mov     rcx, rbx; this
0x18000658e  call    ?OnDownloadComplete@CUrlDownload@@IEAAJH@Z; CUrlDownload::OnDownloadComplete(int)
0x180006593  mov     rcx, [rbp+ppmk]
0x180006597  mov     dword ptr [rbx+2C8h], 0
0x1800065a1  mov     rax, [rcx]
0x1800065a4  mov     rax, [rax+10h]
0x1800065a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ad  mov     rcx, [rbp+ppbc]
0x1800065b1  mov     rax, [rcx]
0x1800065b4  mov     rax, [rax+10h]
0x1800065b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065bd  mov     rcx, [rbp+var_8]
0x1800065c1  test    rcx, rcx
0x1800065c4  jz      short loc_1800065D2
0x1800065c6  mov     rax, [rcx]
0x1800065c9  mov     rax, [rax+10h]
0x1800065cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065d2  xor     eax, eax
0x1800065d4  jmp     short loc_18000664A
0x1800065d6  mov     qword ptr [rbx+0A0h], 0
0x1800065e1  mov     edi, 8007000Eh
0x1800065e6  mov     rcx, [rbp+ppbc]
0x1800065ea  test    rcx, rcx
0x1800065ed  jz      short loc_1800065FB
0x1800065ef  mov     rax, [rcx]
0x1800065f2  mov     rax, [rax+10h]
0x1800065f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065fb  mov     rcx, [rbp+ppmk]
0x1800065ff  test    rcx, rcx
0x180006602  jz      short loc_180006610
0x180006604  mov     rax, [rcx]
0x180006607  mov     rax, [rax+10h]
0x18000660b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006610  mov     rcx, [rbp+var_8]
0x180006614  test    rcx, rcx
0x180006617  jz      short loc_180006625
0x180006619  mov     rax, [rcx]
0x18000661c  mov     rax, [rax+10h]
0x180006620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006625  mov     rcx, [rbx+0A0h]
0x18000662c  test    rcx, rcx
0x18000662f  jz      short loc_180006648
0x180006631  mov     rax, [rcx]
0x180006634  mov     rax, [rax+10h]
0x180006638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000663d  mov     qword ptr [rbx+0A0h], 0
0x180006648  mov     eax, edi
0x18000664a  mov     rbx, [rsp+40h+arg_0]
0x18000664f  mov     rsi, [rsp+40h+arg_8]
0x180006654  add     rsp, 40h
0x180006658  pop     r15
0x18000665a  pop     rdi
0x18000665b  pop     rbp
0x18000665c  retn
```
