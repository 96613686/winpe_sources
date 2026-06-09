# ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013a58`
- end: `0x180013b60`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCFciPropertiesShellExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013800`

## callees

- `0x180001264`
- `0x180004780`
- `0x180013a58`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CFciPropertiesShellExt>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CFciPropertiesShellExt *v7; // rax
  CFciPropertiesShellExt *v8; // rbx
  _QWORD *v9; // rcx
  int v10; // ecx
  CFciPropertiesShellExt *v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  try
  {
    v7 = (CFciPropertiesShellExt *)operator new(0x288u);
    v8 = v7;
    if ( v7 )
    {
      CFciPropertiesShellExt::CFciPropertiesShellExt(v7);
      *v9 = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'};
      v9[1] = &ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v8 = 0;
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v10 = *((_DWORD *)v8 + 4);
    if ( v10 != 0x7FFFFFFF )
    {
      *((_DWORD *)v8 + 4) = v10 + 1;
      if ( v10 != 2147483646 )
        *((_DWORD *)v8 + 4) = v10;
    }
    v6 = (**(__int64 (__fastcall ***)(CFciPropertiesShellExt *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(CFciPropertiesShellExt *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180013a58  mov     [rsp+arg_10], r8
0x180013a5d  mov     [rsp+arg_8], rdx
0x180013a62  mov     [rsp+arg_0], rcx
0x180013a67  push    rbx
0x180013a68  push    rsi
0x180013a69  push    rdi
0x180013a6a  push    r14
0x180013a6c  sub     rsp, 38h
0x180013a70  mov     rsi, r8
0x180013a73  mov     r14, rdx
0x180013a76  test    r8, r8
0x180013a79  jnz     short loc_180013A85
0x180013a7b  mov     eax, 80004003h
0x180013a80  jmp     loc_180013B56
0x180013a85  mov     qword ptr [r8], 0
0x180013a8c  mov     edi, 8007000Eh
0x180013a91  mov     dword ptr [rsp+58h+arg_0], edi
0x180013a95  mov     [rsp+58h+var_38], 0
0x180013a9e  mov     ecx, 288h; Size
0x180013aa3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013aa8  mov     rbx, rax
0x180013aab  mov     [rsp+58h+arg_18], rax
0x180013ab0  test    rax, rax
0x180013ab3  jz      short loc_180013AE9
0x180013ab5  mov     rcx, rax; this
0x180013ab8  call    ??0CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::CFciPropertiesShellExt(void)
0x180013abd  nop
0x180013abe  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'}
0x180013ac5  mov     [rcx], rax
0x180013ac8  lea     rax, ??_7?$CComObject@VCFciPropertiesShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180013acf  mov     [rcx+8], rax
0x180013ad3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013ada  mov     rax, [rcx]
0x180013add  mov     rax, [rax+8]
0x180013ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ae6  nop
0x180013ae7  jmp     short loc_180013AEB
0x180013ae9  xor     ebx, ebx
0x180013aeb  mov     [rsp+58h+var_38], rbx
0x180013af0  jmp     short loc_180013B05
0x180013af2  mov     rsi, [rsp+58h+arg_10]
0x180013af7  mov     r14, [rsp+58h+arg_8]
0x180013afc  mov     edi, dword ptr [rsp+58h+arg_0]
0x180013b00  mov     rbx, [rsp+58h+var_38]
0x180013b05  test    rbx, rbx
0x180013b08  jz      short loc_180013B54
0x180013b0a  mov     ecx, [rbx+10h]
0x180013b0d  cmp     ecx, 7FFFFFFFh
0x180013b13  jz      short loc_180013B26
0x180013b15  lea     eax, [rcx+1]
0x180013b18  mov     [rbx+10h], eax
0x180013b1b  cmp     ecx, 7FFFFFFEh
0x180013b21  jz      short loc_180013B26
0x180013b23  mov     [rbx+10h], ecx
0x180013b26  mov     rax, [rbx]
0x180013b29  mov     r8, rsi
0x180013b2c  mov     rdx, r14
0x180013b2f  mov     rcx, rbx
0x180013b32  mov     rax, [rax]
0x180013b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b3a  mov     edi, eax
0x180013b3c  test    eax, eax
0x180013b3e  jz      short loc_180013B54
0x180013b40  mov     rdx, [rbx]
0x180013b43  mov     rax, [rdx+20h]
0x180013b47  mov     edx, 1
0x180013b4c  mov     rcx, rbx
0x180013b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b54  mov     eax, edi
0x180013b56  add     rsp, 38h
0x180013b5a  pop     r14
0x180013b5c  pop     rdi
0x180013b5d  pop     rsi
0x180013b5e  pop     rbx
0x180013b5f  retn
```
