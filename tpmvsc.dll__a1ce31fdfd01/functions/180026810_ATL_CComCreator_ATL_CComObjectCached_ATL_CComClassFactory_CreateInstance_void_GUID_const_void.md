# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180026810`
- end: `0x1800268f8`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800023c0`
- `0x18001bf1c`
- `0x18002602c`
- `0x180026810`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  _BYTE *v7; // rbx
  int v8; // edi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026810  mov     [rsp+arg_10], r8
0x180026815  mov     [rsp+arg_8], rdx
0x18002681a  mov     [rsp+arg_0], rcx
0x18002681f  push    rbx
0x180026820  push    rsi
0x180026821  push    rdi
0x180026822  push    r14
0x180026824  push    r15
0x180026826  sub     rsp, 30h
0x18002682a  mov     rsi, r8
0x18002682d  mov     r15, rdx
0x180026830  mov     r14, rcx
0x180026833  test    r8, r8
0x180026836  jnz     short loc_180026842
0x180026838  mov     eax, 80004003h
0x18002683d  jmp     loc_1800268EC
0x180026842  mov     qword ptr [r8], 0
0x180026849  mov     edi, 8007000Eh
0x18002684e  mov     [rsp+58h+arg_18], edi
0x180026852  mov     [rsp+58h+var_38], 0
0x18002685b  mov     ecx, 48h ; 'H'; Size
0x180026860  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026865  mov     rbx, rax
0x180026868  mov     dword ptr [rax+8], 0
0x18002686f  xorps   xmm0, xmm0
0x180026872  xor     eax, eax
0x180026874  movups  xmmword ptr [rbx+10h], xmm0
0x180026878  movups  xmmword ptr [rbx+20h], xmm0
0x18002687c  mov     [rbx+30h], rax
0x180026880  mov     [rbx+38h], al
0x180026883  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18002688a  mov     [rbx], rax
0x18002688d  mov     [rsp+58h+var_38], rbx
0x180026892  jmp     short loc_1800268AC
0x180026894  mov     rsi, [rsp+58h+arg_10]
0x180026899  mov     r15, [rsp+58h+arg_8]
0x18002689e  mov     r14, [rsp+58h+arg_0]
0x1800268a3  mov     edi, [rsp+58h+arg_18]
0x1800268a7  mov     rbx, [rsp+58h+var_38]
0x1800268ac  test    rbx, rbx
0x1800268af  jz      short loc_1800268EA
0x1800268b1  mov     [rbx+40h], r14
0x1800268b5  lea     rcx, [rbx+10h]; this
0x1800268b9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800268be  mov     edi, eax
0x1800268c0  test    eax, eax
0x1800268c2  js      short loc_1800268E2
0x1800268c4  mov     byte ptr [rbx+38h], 1
0x1800268c8  mov     rax, [rbx]
0x1800268cb  mov     r8, rsi
0x1800268ce  mov     rdx, r15
0x1800268d1  mov     rcx, rbx
0x1800268d4  mov     rax, [rax]
0x1800268d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268dc  mov     edi, eax
0x1800268de  test    eax, eax
0x1800268e0  jz      short loc_1800268EA
0x1800268e2  mov     rcx, rbx; Block
0x1800268e5  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800268ea  mov     eax, edi
0x1800268ec  add     rsp, 30h
0x1800268f0  pop     r15
0x1800268f2  pop     r14
0x1800268f4  pop     rdi
0x1800268f5  pop     rsi
0x1800268f6  pop     rbx
0x1800268f7  retn
```
