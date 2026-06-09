# ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800043e8`
- end: `0x1800044ec`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardTypeRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e50`

## callees

- `0x1800011dc`
- `0x1800043e8`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x40u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CPXWizardTypeRegistration>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800043e8  mov     [rsp+arg_10], r8
0x1800043ed  mov     [rsp+arg_8], rdx
0x1800043f2  mov     [rsp+arg_0], rcx
0x1800043f7  push    rbx
0x1800043f8  push    rsi
0x1800043f9  push    rdi
0x1800043fa  push    r14
0x1800043fc  sub     rsp, 28h
0x180004400  mov     rsi, r8
0x180004403  mov     r14, rdx
0x180004406  test    r8, r8
0x180004409  jnz     short loc_180004415
0x18000440b  mov     eax, 80004003h
0x180004410  jmp     loc_1800044E2
0x180004415  mov     qword ptr [r8], 0
0x18000441c  mov     edi, 8007000Eh
0x180004421  mov     dword ptr [rsp+48h+arg_0], edi
0x180004425  mov     [rsp+48h+arg_18], 0
0x18000442e  mov     ecx, 40h ; '@'; Size
0x180004433  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004438  mov     rbx, rax
0x18000443b  test    rbx, rbx
0x18000443e  jz      short loc_180004478
0x180004440  mov     dword ptr [rax+8], 0
0x180004447  xorps   xmm0, xmm0
0x18000444a  xor     eax, eax
0x18000444c  movups  xmmword ptr [rbx+10h], xmm0
0x180004450  movups  xmmword ptr [rbx+20h], xmm0
0x180004454  mov     [rbx+30h], rax
0x180004458  mov     [rbx+38h], al
0x18000445b  lea     rax, ??_7?$CComObject@VCPXWizardTypeRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardTypeRegistration>::`vftable'
0x180004462  mov     [rbx], rax
0x180004465  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000446c  mov     rax, [rcx]
0x18000446f  mov     rax, [rax+8]
0x180004473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004478  mov     [rsp+48h+arg_18], rbx
0x18000447d  jmp     short loc_180004492
0x18000447f  mov     rsi, [rsp+48h+arg_10]
0x180004484  mov     r14, [rsp+48h+arg_8]
0x180004489  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000448d  mov     rbx, [rsp+48h+arg_18]
0x180004492  test    rbx, rbx
0x180004495  jz      short loc_1800044E0
0x180004497  lea     rcx, [rbx+10h]; this
0x18000449b  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800044a0  xor     ecx, ecx
0x1800044a2  test    eax, eax
0x1800044a4  cmovs   ecx, eax
0x1800044a7  xor     edi, edi
0x1800044a9  test    ecx, ecx
0x1800044ab  cmovs   edi, ecx
0x1800044ae  test    edi, edi
0x1800044b0  jnz     short loc_1800044CC
0x1800044b2  mov     rax, [rbx]
0x1800044b5  mov     r8, rsi
0x1800044b8  mov     rdx, r14
0x1800044bb  mov     rcx, rbx
0x1800044be  mov     rax, [rax]
0x1800044c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c6  mov     edi, eax
0x1800044c8  test    eax, eax
0x1800044ca  jz      short loc_1800044E0
0x1800044cc  mov     rdx, [rbx]
0x1800044cf  mov     rax, [rdx+28h]
0x1800044d3  mov     edx, 1
0x1800044d8  mov     rcx, rbx
0x1800044db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044e0  mov     eax, edi
0x1800044e2  add     rsp, 28h
0x1800044e6  pop     r14
0x1800044e8  pop     rdi
0x1800044e9  pop     rsi
0x1800044ea  pop     rbx
0x1800044eb  retn
```
