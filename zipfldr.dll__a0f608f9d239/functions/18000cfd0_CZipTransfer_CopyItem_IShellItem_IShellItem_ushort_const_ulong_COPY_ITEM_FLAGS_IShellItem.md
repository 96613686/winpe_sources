# CZipTransfer::CopyItem(IShellItem *,IShellItem *,ushort const *,ulong,COPY_ITEM_FLAGS,IShellItem * *)

- ea: `0x18000cfd0`
- end: `0x18000d23b`
- name: `?CopyItem@CZipTransfer@@UEAAJPEAUIShellItem@@0PEBGKW4COPY_ITEM_FLAGS@@PEAPEAU2@@Z`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000ca94`
- `0x18000cfd0`
- `0x18000d244`
- `0x18000ed28`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18000d1ba`
- `SHELL32!SHCreateItemFromParsingName` at `0x18000d1ba`
- `SHELL32!__imp_ILFree` at `0x18000d1f4`
- `SHELL32!__imp_ILFree` at `0x18000d220`
- `SHELL32!__imp_ILFree` at `0x18000d1f4`
- `SHELL32!__imp_ILFree` at `0x18000d220`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d1d8`

## pseudocode

```c
__int64 __fastcall CZipTransfer::CopyItem(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, IBindCtx **),
        __int64 *a3,
        const unsigned __int16 *a4,
        __int16 a5,
        __int64 a6,
        void **ppv)
{
  int ZipToFile; // ebx
  __int64 v11; // rax
  const struct CArchiveIDList *v12; // rdi
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // r9d
  struct IBindCtx *v16; // rcx
  unsigned int v17; // edx
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  IBindCtx *pbc; // [rsp+58h] [rbp-A8h] BYREF
  LPITEMIDLIST pidl; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  pidl = 0;
  v22 = 0;
  pbc = 0;
  *ppv = 0;
  ZipToFile = (**a2)(a2, &GUID_b3a4b685_b685_4805_99d9_5dead2873236, &pbc);
  if ( ZipToFile >= 0 )
  {
    pv = 0;
    ZipToFile = ((__int64 (__fastcall *)(IBindCtx *, _QWORD, LPVOID *, LPITEMIDLIST *))pbc->lpVtbl->RevokeObjectBound)(
                  pbc,
                  0,
                  &pv,
                  &pidl);
    if ( ZipToFile >= 0 )
    {
      ZipToFile = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))pv)(
                    pv,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    &v22);
      if ( ZipToFile < 0 )
      {
        ILFree(pidl);
        pidl = 0;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
    if ( ZipToFile >= 0 )
    {
      v11 = *a3;
      pv = 0;
      ZipToFile = (*(__int64 (__fastcall **)(__int64 *, __int64, LPVOID *))(v11 + 40))(a3, 2147844096LL, &pv);
      if ( ZipToFile >= 0 )
      {
        v12 = CArchiveIDList::_IsValidID(pidl);
        if ( v12 )
        {
          v13 = (2 * (a5 & 2)) | 8;
          if ( !*(_DWORD *)(a1 + 80) )
            v13 = 2 * (a5 & 2);
          v14 = v13 | 0x10;
          if ( (a5 & 0x2000) == 0 )
            v14 = v13;
          v15 = v14 | 0x20;
          if ( (a5 & 0x8000) == 0 )
            v15 = v14;
          ZipToFile = ExtractZipToFile(
                        *(HWND *)(a1 + 40),
                        v12,
                        *(struct CZipFolder **)(a1 + 88),
                        v15,
                        (unsigned __int16 *)pv,
                        a4,
                        *(struct ITransferAdviseSink **)(a1 + 32),
                        pszPath);
          if ( ZipToFile >= 0 )
          {
            v17 = *((_DWORD *)v12 + 8);
            pbc = 0;
            ZipToFile = SHCreateFileSysBindCtxFromAttributes(v16, v17, &pbc);
            if ( ZipToFile >= 0 )
            {
              ZipToFile = SHCreateItemFromParsingName(pszPath, pbc, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, ppv);
              ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
            }
          }
        }
        else
        {
          ZipToFile = -2147024809;
        }
        CoTaskMemFree(pv);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      ILFree(pidl);
    }
  }
  return (unsigned int)ZipToFile;
}

```

## disassembly

```asm
0x18000cfd0  push    rbp
0x18000cfd2  push    rbx
0x18000cfd3  push    rsi
0x18000cfd4  push    rdi
0x18000cfd5  push    r14
0x18000cfd7  push    r15
0x18000cfd9  lea     rbp, [rsp-198h]
0x18000cfe1  sub     rsp, 298h
0x18000cfe8  mov     rax, cs:__security_cookie
0x18000cfef  xor     rax, rsp
0x18000cff2  mov     [rbp+1C0h+var_40], rax
0x18000cff9  mov     rsi, [rbp+1C0h+ppv]
0x18000d000  mov     r10, rdx
0x18000d003  mov     rdi, r8
0x18000d006  mov     [rsp+2C0h+pidl], 0
0x18000d00f  mov     r14, rcx
0x18000d012  mov     [rsp+2C0h+var_258], 0
0x18000d01b  lea     r8, [rsp+2C0h+pbc]
0x18000d020  mov     [rsp+2C0h+pbc], 0
0x18000d029  mov     qword ptr [rsi], 0
0x18000d030  mov     rcx, r10
0x18000d033  mov     rax, [rdx]
0x18000d036  mov     r15, r9
0x18000d039  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x18000d040  mov     rax, [rax]
0x18000d043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d048  mov     ebx, eax
0x18000d04a  test    eax, eax
0x18000d04c  js      loc_18000D1FA
0x18000d052  mov     rcx, [rsp+2C0h+pbc]
0x18000d057  lea     r9, [rsp+2C0h+pidl]
0x18000d05c  mov     [rsp+2C0h+pv], 0
0x18000d065  lea     r8, [rsp+2C0h+pv]
0x18000d06a  xor     edx, edx
0x18000d06c  mov     rax, [rcx]
0x18000d06f  mov     rax, [rax+20h]
0x18000d073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d078  mov     ebx, eax
0x18000d07a  test    eax, eax
0x18000d07c  js      short loc_18000D0B5
0x18000d07e  mov     rcx, [rsp+2C0h+pv]
0x18000d083  lea     r8, [rsp+2C0h+var_258]
0x18000d088  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x18000d08f  mov     rax, [rcx]
0x18000d092  mov     rax, [rax]
0x18000d095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d09a  mov     ebx, eax
0x18000d09c  test    eax, eax
0x18000d09e  js      loc_18000D21B
0x18000d0a4  mov     rcx, [rsp+2C0h+pv]
0x18000d0a9  mov     rax, [rcx]
0x18000d0ac  mov     rax, [rax+10h]
0x18000d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b5  mov     rcx, [rsp+2C0h+pbc]
0x18000d0ba  mov     rax, [rcx]
0x18000d0bd  mov     rax, [rax+10h]
0x18000d0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0c6  test    ebx, ebx
0x18000d0c8  js      loc_18000D1FA
0x18000d0ce  mov     rax, [rdi]
0x18000d0d1  lea     r8, [rsp+2C0h+pv]
0x18000d0d6  mov     edx, 80058000h
0x18000d0db  mov     [rsp+2C0h+pv], 0
0x18000d0e4  mov     rcx, rdi
0x18000d0e7  mov     rax, [rax+28h]
0x18000d0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0f0  mov     ebx, eax
0x18000d0f2  test    eax, eax
0x18000d0f4  js      loc_18000D1DE
0x18000d0fa  mov     rcx, [rsp+2C0h+pidl]; struct _ITEMIDLIST *
0x18000d0ff  call    ?_IsValidID@CArchiveIDList@@SAPEBV1@PEFBU_ITEMIDLIST@@@Z; CArchiveIDList::_IsValidID(_ITEMIDLIST const *)
0x18000d104  mov     rdi, rax
0x18000d107  test    rax, rax
0x18000d10a  jz      loc_18000D234
0x18000d110  mov     ecx, dword ptr [rbp+1C0h+arg_20]
0x18000d116  lea     rax, [rsp+2C0h+pszPath]
0x18000d11b  and     ecx, 2
0x18000d11e  mov     [rsp+2C0h+var_288], rax; unsigned __int16 *
0x18000d123  mov     rax, [r14+20h]
0x18000d127  add     ecx, ecx
0x18000d129  mov     edx, ecx
0x18000d12b  mov     [rsp+2C0h+var_290], rax; struct ITransferAdviseSink *
0x18000d130  mov     rax, [rsp+2C0h+pv]
0x18000d135  or      edx, 8
0x18000d138  cmp     dword ptr [r14+50h], 0
0x18000d13d  mov     [rsp+2C0h+var_298], r15; unsigned __int16 *
0x18000d142  cmovz   edx, ecx
0x18000d145  mov     [rsp+2C0h+var_2A0], rax; unsigned __int16 *
0x18000d14a  mov     rcx, [r14+28h]; HWND
0x18000d14e  mov     r8d, edx
0x18000d151  or      r8d, 10h
0x18000d155  test    dword ptr [rbp+1C0h+arg_20], 2000h
0x18000d15f  cmovz   r8d, edx
0x18000d163  mov     rdx, rdi; struct CArchiveIDList *
0x18000d166  mov     r9d, r8d
0x18000d169  or      r9d, 20h
0x18000d16d  test    dword ptr [rbp+1C0h+arg_20], 8000h
0x18000d177  cmovz   r9d, r8d; unsigned int
0x18000d17b  mov     r8, [r14+58h]; struct CZipFolder *
0x18000d17f  call    ?ExtractZipToFile@@YAJPEAUHWND__@@PEBVCArchiveIDList@@PEAVCZipFolder@@KPEBG3PEAUITransferAdviseSink@@PEAGK@Z; ExtractZipToFile(HWND__ *,CArchiveIDList const *,CZipFolder *,ulong,ushort const *,ushort const *,ITransferAdviseSink *,ushort *,ulong)
0x18000d184  mov     ebx, eax
0x18000d186  test    eax, eax
0x18000d188  js      short loc_18000D1D3
0x18000d18a  mov     edx, [rdi+20h]; unsigned int
0x18000d18d  lea     r8, [rsp+2C0h+pbc]; struct IBindCtx **
0x18000d192  mov     [rsp+2C0h+pbc], 0
0x18000d19b  call    ?SHCreateFileSysBindCtxFromAttributes@@YAJPEAUIBindCtx@@KPEAPEAU1@@Z; SHCreateFileSysBindCtxFromAttributes(IBindCtx *,ulong,IBindCtx * *)
0x18000d1a0  mov     ebx, eax
0x18000d1a2  test    eax, eax
0x18000d1a4  js      short loc_18000D1D3
0x18000d1a6  mov     rdx, [rsp+2C0h+pbc]; pbc
0x18000d1ab  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000d1b2  mov     r9, rsi; ppv
0x18000d1b5  lea     rcx, [rsp+2C0h+pszPath]; pszPath
0x18000d1ba  call    cs:__imp_SHCreateItemFromParsingName
0x18000d1c0  mov     rcx, [rsp+2C0h+pbc]
0x18000d1c5  mov     ebx, eax
0x18000d1c7  mov     rax, [rcx]
0x18000d1ca  mov     rax, [rax+10h]
0x18000d1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d3  mov     rcx, [rsp+2C0h+pv]; pv
0x18000d1d8  call    cs:__imp_CoTaskMemFree
0x18000d1de  mov     rcx, [rsp+2C0h+var_258]
0x18000d1e3  mov     rax, [rcx]
0x18000d1e6  mov     rax, [rax+10h]
0x18000d1ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ef  mov     rcx, [rsp+2C0h+pidl]; pidl
0x18000d1f4  call    cs:__imp_ILFree
0x18000d1fa  mov     eax, ebx
0x18000d1fc  mov     rcx, [rbp+1C0h+var_40]
0x18000d203  xor     rcx, rsp; StackCookie
0x18000d206  call    __security_check_cookie
0x18000d20b  add     rsp, 298h
0x18000d212  pop     r15
0x18000d214  pop     r14
0x18000d216  pop     rdi
0x18000d217  pop     rsi
0x18000d218  pop     rbx
0x18000d219  pop     rbp
0x18000d21a  retn
0x18000d21b  mov     rcx, [rsp+2C0h+pidl]; pidl
0x18000d220  call    cs:__imp_ILFree
0x18000d226  mov     [rsp+2C0h+pidl], 0
0x18000d22f  jmp     loc_18000D0A4
0x18000d234  mov     ebx, 80070057h
0x18000d239  jmp     short loc_18000D1D3
```
