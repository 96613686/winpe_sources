# ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013834`
- end: `0x180013946`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013800`

## callees

- `0x180001264`
- `0x180004780`
- `0x180013834`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CFciPropertiesShellExt>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  _QWORD *v10; // rcx
  _DWORD *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  try
  {
    v8 = operator new(0x298u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CFciPropertiesShellExt>::`vftable';
      CFciPropertiesShellExt::CFciPropertiesShellExt((CFciPropertiesShellExt *)(v8 + 4));
      *v10 = &ATL::CComContainedObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'};
      v10[1] = &ATL::CComContainedObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'};
      v10[2] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v11 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180013834  mov     [rsp+arg_10], r8
0x180013839  mov     [rsp+arg_8], rdx
0x18001383e  push    rbx
0x18001383f  push    rsi
0x180013840  push    rdi
0x180013841  push    r14
0x180013843  push    r15
0x180013845  sub     rsp, 40h
0x180013849  mov     rsi, r8
0x18001384c  mov     r14, rdx
0x18001384f  mov     r15, rcx
0x180013852  test    r8, r8
0x180013855  jnz     short loc_180013861
0x180013857  mov     eax, 80004003h
0x18001385c  jmp     loc_18001393A
0x180013861  mov     qword ptr [r8], 0
0x180013868  mov     edi, 8007000Eh
0x18001386d  mov     [rsp+68h+arg_18], edi
0x180013874  mov     [rsp+68h+var_48], 0
0x18001387d  mov     ecx, 298h; Size
0x180013882  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013887  mov     rbx, rax
0x18001388a  mov     [rsp+68h+var_40], rax
0x18001388f  test    rax, rax
0x180013892  jz      short loc_1800138E3
0x180013894  mov     dword ptr [rax+8], 0
0x18001389b  lea     rax, ??_7?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@6B@; const ATL::CComAggObject<CFciPropertiesShellExt>::`vftable'
0x1800138a2  mov     [rbx], rax
0x1800138a5  lea     rcx, [rbx+10h]; this
0x1800138a9  mov     [rsp+68h+var_38], rcx
0x1800138ae  call    ??0CFciPropertiesShellExt@@QEAA@XZ; CFciPropertiesShellExt::CFciPropertiesShellExt(void)
0x1800138b3  nop
0x1800138b4  lea     rax, ??_7?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComContainedObject<CFciPropertiesShellExt>::`vftable'{for `IShellExtInit'}
0x1800138bb  mov     [rcx], rax
0x1800138be  lea     rax, ??_7?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComContainedObject<CFciPropertiesShellExt>::`vftable'{for `IShellPropSheetExt'}
0x1800138c5  mov     [rcx+8], rax
0x1800138c9  mov     [rcx+10h], r15
0x1800138cd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800138d4  mov     rax, [rcx]
0x1800138d7  mov     rax, [rax+8]
0x1800138db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138e0  nop
0x1800138e1  jmp     short loc_1800138E5
0x1800138e3  xor     ebx, ebx
0x1800138e5  mov     [rsp+68h+var_48], rbx
0x1800138ea  jmp     short loc_180013905
0x1800138ec  mov     rsi, [rsp+68h+arg_10]
0x1800138f4  mov     r14, [rsp+68h+arg_8]
0x1800138f9  mov     edi, [rsp+68h+arg_18]
0x180013900  mov     rbx, [rsp+68h+var_48]
0x180013905  test    rbx, rbx
0x180013908  jz      short loc_180013938
0x18001390a  mov     rax, [rbx]
0x18001390d  mov     r8, rsi
0x180013910  mov     rdx, r14
0x180013913  mov     rcx, rbx
0x180013916  mov     rax, [rax]
0x180013919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001391e  mov     edi, eax
0x180013920  test    eax, eax
0x180013922  jz      short loc_180013938
0x180013924  mov     rdx, [rbx]
0x180013927  mov     rax, [rdx+18h]
0x18001392b  mov     edx, 1
0x180013930  mov     rcx, rbx
0x180013933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013938  mov     eax, edi
0x18001393a  add     rsp, 40h
0x18001393e  pop     r15
0x180013940  pop     r14
0x180013942  pop     rdi
0x180013943  pop     rsi
0x180013944  pop     rbx
0x180013945  retn
```
