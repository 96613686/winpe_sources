# ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003f88`
- end: `0x1800040a4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e30`

## callees

- `0x1800011dc`
- `0x180003f88`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // edi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  int v11; // ecx
  int v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x58u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CPXWizardRegistration>::`vftable';
    *(_OWORD *)(v8 + 40) = 0;
    *(_OWORD *)(v8 + 56) = 0;
    *((_QWORD *)v8 + 9) = 0;
    v8[80] = 0;
    *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CPXWizardRegistration>::`vftable';
    *((_QWORD *)v8 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180003f88  mov     [rsp+arg_10], r8
0x180003f8d  mov     [rsp+arg_8], rdx
0x180003f92  push    rbx
0x180003f93  push    rsi
0x180003f94  push    rdi
0x180003f95  push    r14
0x180003f97  push    r15
0x180003f99  sub     rsp, 30h
0x180003f9d  mov     rsi, r8
0x180003fa0  mov     r14, rdx
0x180003fa3  mov     r15, rcx
0x180003fa6  test    r8, r8
0x180003fa9  jnz     short loc_180003FB5
0x180003fab  mov     eax, 80004003h
0x180003fb0  jmp     loc_180004098
0x180003fb5  mov     qword ptr [r8], 0
0x180003fbc  mov     edi, 8007000Eh
0x180003fc1  mov     [rsp+58h+arg_18], edi
0x180003fc5  mov     [rsp+58h+var_38], 0
0x180003fce  mov     ecx, 58h ; 'X'; Size
0x180003fd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fd8  mov     rbx, rax
0x180003fdb  test    rbx, rbx
0x180003fde  jz      short loc_180004027
0x180003fe0  mov     dword ptr [rax+8], 0
0x180003fe7  lea     rax, ??_7?$CComAggObject@VCPXWizardRegistration@@@ATL@@6B@; const ATL::CComAggObject<CPXWizardRegistration>::`vftable'
0x180003fee  mov     [rbx], rax
0x180003ff1  xorps   xmm0, xmm0
0x180003ff4  xor     eax, eax
0x180003ff6  movups  xmmword ptr [rbx+28h], xmm0
0x180003ffa  movups  xmmword ptr [rbx+38h], xmm0
0x180003ffe  mov     [rbx+48h], rax
0x180004002  mov     [rbx+50h], al
0x180004005  lea     rax, ??_7?$CComContainedObject@VCPXWizardRegistration@@@ATL@@6B@; const ATL::CComContainedObject<CPXWizardRegistration>::`vftable'
0x18000400c  mov     [rbx+18h], rax
0x180004010  mov     [rbx+20h], r15
0x180004014  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000401b  mov     rax, [rcx]
0x18000401e  mov     rax, [rax+8]
0x180004022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004027  mov     [rsp+58h+var_38], rbx
0x18000402c  jmp     short loc_180004041
0x18000402e  mov     rsi, [rsp+58h+arg_10]
0x180004033  mov     r14, [rsp+58h+arg_8]
0x180004038  mov     edi, [rsp+58h+arg_18]
0x18000403c  mov     rbx, [rsp+58h+var_38]
0x180004041  test    rbx, rbx
0x180004044  jz      short loc_180004096
0x180004046  lea     rcx, [rbx+28h]; this
0x18000404a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000404f  xor     ecx, ecx
0x180004051  test    eax, eax
0x180004053  cmovs   ecx, eax
0x180004056  xor     eax, eax
0x180004058  test    ecx, ecx
0x18000405a  cmovs   eax, ecx
0x18000405d  xor     edi, edi
0x18000405f  test    eax, eax
0x180004061  cmovs   edi, eax
0x180004064  test    edi, edi
0x180004066  jnz     short loc_180004082
0x180004068  mov     rax, [rbx]
0x18000406b  mov     r8, rsi
0x18000406e  mov     rdx, r14
0x180004071  mov     rcx, rbx
0x180004074  mov     rax, [rax]
0x180004077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000407c  mov     edi, eax
0x18000407e  test    eax, eax
0x180004080  jz      short loc_180004096
0x180004082  mov     rdx, [rbx]
0x180004085  mov     rax, [rdx+18h]
0x180004089  mov     edx, 1
0x18000408e  mov     rcx, rbx
0x180004091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004096  mov     eax, edi
0x180004098  add     rsp, 30h
0x18000409c  pop     r15
0x18000409e  pop     r14
0x1800040a0  pop     rdi
0x1800040a1  pop     rsi
0x1800040a2  pop     rbx
0x1800040a3  retn
```
