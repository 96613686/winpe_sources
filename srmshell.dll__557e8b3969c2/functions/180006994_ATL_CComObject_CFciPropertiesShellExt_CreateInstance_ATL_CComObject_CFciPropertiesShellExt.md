# ATL::CComObject<CFciPropertiesShellExt>::CreateInstance(ATL::CComObject<CFciPropertiesShellExt> * *)

- ea: `0x180006994`
- end: `0x180006a5d`
- name: `?CreateInstance@?$CComObject@VCFciPropertiesShellExt@@@ATL@@SAJPEAPEAV12@@Z`
- size: `201`
- prototype: `__int64 __fastcall(CFciPropertiesShellExt **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dd70`

## callees

- `0x180001264`
- `0x180004780`
- `0x180006994`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::CreateInstance(CFciPropertiesShellExt **a1)
{
  CFciPropertiesShellExt **v1; // rdi
  unsigned int v3; // esi
  CFciPropertiesShellExt *v4; // rax
  CFciPropertiesShellExt *v5; // rbx
  _QWORD *v6; // rcx
  int v7; // ecx
  CFciPropertiesShellExt *v8; // [rsp+20h] [rbp-28h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  try
  {
    v4 = (CFciPropertiesShellExt *)operator new(0x288u);
    v5 = v4;
    if ( v4 )
    {
      CFciPropertiesShellExt::CFciPropertiesShellExt(v4);
      *v6 = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'};
      v6[1] = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v8 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v8;
  }
  if ( v5 )
  {
    v7 = *((_DWORD *)v5 + 4);
    if ( v7 != 0x7FFFFFFF )
    {
      *((_DWORD *)v5 + 4) = v7 + 1;
      if ( v7 != 2147483646 )
        *((_DWORD *)v5 + 4) = v7;
    }
    v3 = 0;
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180006994  mov     [rsp+arg_0], rcx
0x180006999  push    rbx
0x18000699a  push    rsi
0x18000699b  push    rdi
0x18000699c  sub     rsp, 30h
0x1800069a0  mov     rdi, rcx
0x1800069a3  test    rcx, rcx
0x1800069a6  jnz     short loc_1800069B2
0x1800069a8  mov     eax, 80004003h
0x1800069ad  jmp     loc_180006A55
0x1800069b2  mov     qword ptr [rcx], 0
0x1800069b9  mov     esi, 8007000Eh
0x1800069be  mov     [rsp+48h+arg_8], esi
0x1800069c2  mov     [rsp+48h+var_28], 0
0x1800069cb  mov     ecx, 288h; Size
0x1800069d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800069d5  mov     rbx, rax
0x1800069d8  mov     [rsp+48h+arg_10], rax
0x1800069dd  test    rax, rax
0x1800069e0  jz      short loc_180006A16
0x1800069e2  mov     rcx, rax; this
0x1800069e5  call    ??0CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::CFciPropertiesShellExt(void)
0x1800069ea  nop
0x1800069eb  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'}
0x1800069f2  mov     [rcx], rax
0x1800069f5  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'}
0x1800069fc  mov     [rcx+8], rax
0x180006a00  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006a07  mov     rax, [rcx]
0x180006a0a  mov     rax, [rax+8]
0x180006a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a13  nop
0x180006a14  jmp     short loc_180006A18
0x180006a16  xor     ebx, ebx
0x180006a18  mov     [rsp+48h+var_28], rbx
0x180006a1d  jmp     short loc_180006A2D
0x180006a1f  mov     rdi, [rsp+48h+arg_0]
0x180006a24  mov     esi, [rsp+48h+arg_8]
0x180006a28  mov     rbx, [rsp+48h+var_28]
0x180006a2d  test    rbx, rbx
0x180006a30  jz      short loc_180006A50
0x180006a32  mov     ecx, [rbx+10h]
0x180006a35  cmp     ecx, 7FFFFFFFh
0x180006a3b  jz      short loc_180006A4E
0x180006a3d  lea     eax, [rcx+1]
0x180006a40  mov     [rbx+10h], eax
0x180006a43  cmp     ecx, 7FFFFFFEh
0x180006a49  jz      short loc_180006A4E
0x180006a4b  mov     [rbx+10h], ecx
0x180006a4e  xor     esi, esi
0x180006a50  mov     [rdi], rbx
0x180006a53  mov     eax, esi
0x180006a55  add     rsp, 30h
0x180006a59  pop     rdi
0x180006a5a  pop     rsi
0x180006a5b  pop     rbx
0x180006a5c  retn
```
