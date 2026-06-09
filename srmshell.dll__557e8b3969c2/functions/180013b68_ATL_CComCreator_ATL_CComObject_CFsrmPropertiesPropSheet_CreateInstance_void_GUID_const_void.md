# ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013b68`
- end: `0x180013c76`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013820`

## callees

- `0x180001264`
- `0x180008288`
- `0x180013b68`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  CFsrmPropertiesPropSheet *v8; // rcx
  _DWORD *v9; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  _DWORD *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  try
  {
    v7 = operator new(0x10u);
    v9 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CFsrmPropertiesPropSheet>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v9 = 0;
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = v9[2];
    if ( v10 != 0x7FFFFFFF )
      v9[2] = v10 + 1;
    v11 = CFsrmPropertiesPropSheet::FinalConstruct(v8);
    v12 = v9[2];
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    if ( v12 != 0x7FFFFFFF )
      v9[2] = v12 - 1;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 32LL))(v9, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180013b68  mov     [rsp+arg_10], r8
0x180013b6d  mov     [rsp+arg_8], rdx
0x180013b72  mov     [rsp+arg_0], rcx
0x180013b77  push    rbx
0x180013b78  push    rsi
0x180013b79  push    rdi
0x180013b7a  push    r14
0x180013b7c  sub     rsp, 38h
0x180013b80  mov     rsi, r8
0x180013b83  mov     r14, rdx
0x180013b86  test    r8, r8
0x180013b89  jnz     short loc_180013B95
0x180013b8b  mov     eax, 80004003h
0x180013b90  jmp     loc_180013C6C
0x180013b95  mov     qword ptr [r8], 0
0x180013b9c  mov     edi, 8007000Eh
0x180013ba1  mov     dword ptr [rsp+58h+arg_0], edi
0x180013ba5  mov     [rsp+58h+var_38], 0
0x180013bae  mov     ecx, 10h; Size
0x180013bb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013bb8  mov     rbx, rax
0x180013bbb  mov     [rsp+58h+arg_18], rax
0x180013bc0  test    rax, rax
0x180013bc3  jz      short loc_180013BEB
0x180013bc5  mov     dword ptr [rax+8], 0
0x180013bcc  lea     rax, ??_7?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@6B@; const ATL::CComObject<CFsrmPropertiesPropSheet>::`vftable'
0x180013bd3  mov     [rbx], rax
0x180013bd6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013bdd  mov     rax, [rcx]
0x180013be0  mov     rax, [rax+8]
0x180013be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013be9  jmp     short loc_180013BED
0x180013beb  xor     ebx, ebx
0x180013bed  mov     [rsp+58h+var_38], rbx
0x180013bf2  jmp     short loc_180013C07
0x180013bf4  mov     rsi, [rsp+58h+arg_10]
0x180013bf9  mov     r14, [rsp+58h+arg_8]
0x180013bfe  mov     edi, dword ptr [rsp+58h+arg_0]
0x180013c02  mov     rbx, [rsp+58h+var_38]
0x180013c07  test    rbx, rbx
0x180013c0a  jz      short loc_180013C6A
0x180013c0c  mov     eax, [rbx+8]
0x180013c0f  cmp     eax, 7FFFFFFFh
0x180013c14  jz      short loc_180013C1B
0x180013c16  inc     eax
0x180013c18  mov     [rbx+8], eax
0x180013c1b  call    ?FinalConstruct@CFsrmPropertiesPropSheet@@QEAAJXZ; CFsrmPropertiesPropSheet::FinalConstruct(void)
0x180013c20  mov     ecx, [rbx+8]
0x180013c23  xor     edi, edi
0x180013c25  test    eax, eax
0x180013c27  cmovs   edi, eax
0x180013c2a  cmp     ecx, 7FFFFFFFh
0x180013c30  jz      short loc_180013C38
0x180013c32  lea     eax, [rcx-1]
0x180013c35  mov     [rbx+8], eax
0x180013c38  test    edi, edi
0x180013c3a  jnz     short loc_180013C56
0x180013c3c  mov     rax, [rbx]
0x180013c3f  mov     r8, rsi
0x180013c42  mov     rdx, r14
0x180013c45  mov     rcx, rbx
0x180013c48  mov     rax, [rax]
0x180013c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c50  mov     edi, eax
0x180013c52  test    eax, eax
0x180013c54  jz      short loc_180013C6A
0x180013c56  mov     rdx, [rbx]
0x180013c59  mov     rax, [rdx+20h]
0x180013c5d  mov     edx, 1
0x180013c62  mov     rcx, rbx
0x180013c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6a  mov     eax, edi
0x180013c6c  add     rsp, 38h
0x180013c70  pop     r14
0x180013c72  pop     rdi
0x180013c73  pop     rsi
0x180013c74  pop     rbx
0x180013c75  retn
```
