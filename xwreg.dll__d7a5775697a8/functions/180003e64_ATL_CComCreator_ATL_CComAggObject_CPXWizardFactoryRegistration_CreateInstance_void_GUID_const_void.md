# ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e64`
- end: `0x180003f80`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e10`

## callees

- `0x1800011dc`
- `0x180003e64`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  char *v13; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x58u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CPXWizardFactoryRegistration>::`vftable';
      *(_OWORD *)(v8 + 40) = 0;
      *(_OWORD *)(v8 + 56) = 0;
      *((_QWORD *)v8 + 9) = 0;
      v8[80] = 0;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CPXWizardFactoryRegistration>::`vftable';
      *((_QWORD *)v8 + 4) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v13;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 40));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v7 = 0;
    if ( v12 < 0 )
      v7 = v12;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180003e64  mov     [rsp+arg_10], r8
0x180003e69  mov     [rsp+arg_8], rdx
0x180003e6e  push    rbx
0x180003e6f  push    rsi
0x180003e70  push    rdi
0x180003e71  push    r14
0x180003e73  push    r15
0x180003e75  sub     rsp, 30h
0x180003e79  mov     rsi, r8
0x180003e7c  mov     r14, rdx
0x180003e7f  mov     r15, rcx
0x180003e82  test    r8, r8
0x180003e85  jnz     short loc_180003E91
0x180003e87  mov     eax, 80004003h
0x180003e8c  jmp     loc_180003F74
0x180003e91  mov     qword ptr [r8], 0
0x180003e98  mov     edi, 8007000Eh
0x180003e9d  mov     [rsp+58h+arg_18], edi
0x180003ea1  mov     [rsp+58h+var_38], 0
0x180003eaa  mov     ecx, 58h ; 'X'; Size
0x180003eaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003eb4  mov     rbx, rax
0x180003eb7  test    rbx, rbx
0x180003eba  jz      short loc_180003F03
0x180003ebc  mov     dword ptr [rax+8], 0
0x180003ec3  lea     rax, ??_7?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardFactoryRegistration>::`vftable'
0x180003eca  mov     [rbx], rax
0x180003ecd  xorps   xmm0, xmm0
0x180003ed0  xor     eax, eax
0x180003ed2  movups  xmmword ptr [rbx+28h], xmm0
0x180003ed6  movups  xmmword ptr [rbx+38h], xmm0
0x180003eda  mov     [rbx+48h], rax
0x180003ede  mov     [rbx+50h], al
0x180003ee1  lea     rax, ??_7?$CComContainedObject@VCPXWizardFactoryRegistration@@@ATL@@6B@; const ATL::CComContainedObject<CPXWizardFactoryRegistration>::`vftable'
0x180003ee8  mov     [rbx+18h], rax
0x180003eec  mov     [rbx+20h], r15
0x180003ef0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003ef7  mov     rax, [rcx]
0x180003efa  mov     rax, [rax+8]
0x180003efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f03  mov     [rsp+58h+var_38], rbx
0x180003f08  jmp     short loc_180003F1D
0x180003f0a  mov     rsi, [rsp+58h+arg_10]
0x180003f0f  mov     r14, [rsp+58h+arg_8]
0x180003f14  mov     edi, [rsp+58h+arg_18]
0x180003f18  mov     rbx, [rsp+58h+var_38]
0x180003f1d  test    rbx, rbx
0x180003f20  jz      short loc_180003F72
0x180003f22  lea     rcx, [rbx+28h]; this
0x180003f26  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180003f2b  xor     ecx, ecx
0x180003f2d  test    eax, eax
0x180003f2f  cmovs   ecx, eax
0x180003f32  xor     eax, eax
0x180003f34  test    ecx, ecx
0x180003f36  cmovs   eax, ecx
0x180003f39  xor     edi, edi
0x180003f3b  test    eax, eax
0x180003f3d  cmovs   edi, eax
0x180003f40  test    edi, edi
0x180003f42  jnz     short loc_180003F5E
0x180003f44  mov     rax, [rbx]
0x180003f47  mov     r8, rsi
0x180003f4a  mov     rdx, r14
0x180003f4d  mov     rcx, rbx
0x180003f50  mov     rax, [rax]
0x180003f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f58  mov     edi, eax
0x180003f5a  test    eax, eax
0x180003f5c  jz      short loc_180003F72
0x180003f5e  mov     rdx, [rbx]
0x180003f61  mov     rax, [rdx+18h]
0x180003f65  mov     edx, 1
0x180003f6a  mov     rcx, rbx
0x180003f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f72  mov     eax, edi
0x180003f74  add     rsp, 30h
0x180003f78  pop     r15
0x180003f7a  pop     r14
0x180003f7c  pop     rdi
0x180003f7d  pop     rsi
0x180003f7e  pop     rbx
0x180003f7f  retn
```
