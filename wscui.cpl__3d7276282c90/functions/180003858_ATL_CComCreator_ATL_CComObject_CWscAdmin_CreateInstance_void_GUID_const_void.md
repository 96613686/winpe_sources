# ATL::CComCreator<ATL::CComObject<CWscAdmin>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003858`
- end: `0x180003953`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWscAdmin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003830`

## callees

- `0x180001c7c`
- `0x180003858`
- `0x180003b4c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWscAdmin>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // r14d
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  _DWORD *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x50u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_QWORD *)v7 + 2) = 0;
      v7[6] = 0;
      v7[18] = 0;
      CCriticalSection::Initialize((CCriticalSection *)(v7 + 8));
      *(_QWORD *)v8 = &ATL::CComObject<CWscAdmin>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003858  mov     [rsp+arg_10], r8
0x18000385d  mov     [rsp+arg_8], rdx
0x180003862  mov     [rsp+arg_0], rcx
0x180003867  push    rbx
0x180003868  push    rsi
0x180003869  push    r14
0x18000386b  push    r15
0x18000386d  sub     rsp, 28h
0x180003871  mov     rsi, r8
0x180003874  mov     r15, rdx
0x180003877  test    r8, r8
0x18000387a  jnz     short loc_180003886
0x18000387c  mov     eax, 80004003h
0x180003881  jmp     loc_180003948
0x180003886  mov     qword ptr [r8], 0
0x18000388d  mov     r14d, 8007000Eh
0x180003893  mov     dword ptr [rsp+48h+arg_0], r14d
0x180003898  mov     [rsp+48h+arg_18], 0
0x1800038a1  mov     ecx, 50h ; 'P'; Size
0x1800038a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800038ab  mov     rbx, rax
0x1800038ae  test    rbx, rbx
0x1800038b1  jz      short loc_1800038F6
0x1800038b3  mov     dword ptr [rax+8], 0
0x1800038ba  mov     qword ptr [rax+10h], 0
0x1800038c2  mov     dword ptr [rax+18h], 0
0x1800038c9  lea     rcx, [rax+20h]; this
0x1800038cd  mov     dword ptr [rcx+28h], 0
0x1800038d4  call    ?Initialize@CCriticalSection@@QEAAJXZ; CCriticalSection::Initialize(void)
0x1800038d9  lea     rax, ??_7?$CComObject@VCWscAdmin@@@ATL@@6B@; const ATL::CComObject<CWscAdmin>::`vftable'
0x1800038e0  mov     [rbx], rax
0x1800038e3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800038ea  mov     rax, [rcx]
0x1800038ed  mov     rax, [rax+8]
0x1800038f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f6  mov     [rsp+48h+arg_18], rbx
0x1800038fb  jmp     short loc_180003911
0x1800038fd  mov     rsi, [rsp+48h+arg_10]
0x180003902  mov     r15, [rsp+48h+arg_8]
0x180003907  mov     r14d, dword ptr [rsp+48h+arg_0]
0x18000390c  mov     rbx, [rsp+48h+arg_18]
0x180003911  test    rbx, rbx
0x180003914  jz      short loc_180003945
0x180003916  mov     rax, [rbx]
0x180003919  mov     r8, rsi
0x18000391c  mov     rdx, r15
0x18000391f  mov     rcx, rbx
0x180003922  mov     rax, [rax]
0x180003925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000392a  mov     r14d, eax
0x18000392d  test    eax, eax
0x18000392f  jz      short loc_180003945
0x180003931  mov     rdx, [rbx]
0x180003934  mov     rax, [rdx+28h]
0x180003938  mov     edx, 1
0x18000393d  mov     rcx, rbx
0x180003940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003945  mov     eax, r14d
0x180003948  add     rsp, 28h
0x18000394c  pop     r15
0x18000394e  pop     r14
0x180003950  pop     rsi
0x180003951  pop     rbx
0x180003952  retn
```
