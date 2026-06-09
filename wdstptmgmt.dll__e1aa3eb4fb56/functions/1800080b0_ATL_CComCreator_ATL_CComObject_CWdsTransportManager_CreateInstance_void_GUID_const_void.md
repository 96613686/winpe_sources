# ATL::CComCreator<ATL::CComObject<CWdsTransportManager>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800080b0`
- end: `0x1800081bd`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWdsTransportManager@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007f70`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180007d00`
- `0x1800080b0`
- `0x18000832c`
- `0x180020010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWdsTransportManager>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  CWdsTransportManager *v7; // rax
  volatile int *v8; // rbx
  int v9; // eax
  volatile int *v12; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CWdsTransportManager *)operator new(0x70u);
    v8 = (volatile int *)v7;
    if ( v7 )
    {
      CWdsTransportManager::CWdsTransportManager(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CWdsTransportManager>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 2);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    if ( v9 >= 0 )
      v9 = CWdsTransportManager::FinalConstruct((CWdsTransportManager *)v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 64LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800080b0  mov     [rsp+arg_10], r8
0x1800080b5  mov     [rsp+arg_8], rdx
0x1800080ba  mov     [rsp+arg_0], rcx
0x1800080bf  push    rbx
0x1800080c0  push    rsi
0x1800080c1  push    rdi
0x1800080c2  push    r14
0x1800080c4  push    r15
0x1800080c6  sub     rsp, 30h
0x1800080ca  mov     rsi, r8
0x1800080cd  mov     r14, rdx
0x1800080d0  test    r8, r8
0x1800080d3  jnz     short loc_1800080DF
0x1800080d5  mov     eax, 80004003h
0x1800080da  jmp     loc_1800081B0
0x1800080df  and     qword ptr [r8], 0
0x1800080e3  mov     edi, 8007000Eh
0x1800080e8  mov     dword ptr [rsp+58h+arg_0], edi
0x1800080ec  and     [rsp+58h+arg_18], 0
0x1800080f2  mov     ecx, 70h ; 'p'; Size
0x1800080f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080fc  mov     rbx, rax
0x1800080ff  mov     [rsp+58h+var_38], rax
0x180008104  test    rbx, rbx
0x180008107  jz      short loc_18000812F
0x180008109  mov     rcx, rax; this
0x18000810c  call    ??0CWdsTransportManager@@QEAA@XZ; CWdsTransportManager::CWdsTransportManager(void)
0x180008111  lea     rax, ??_7?$CComObject@VCWdsTransportManager@@@ATL@@6B@; const ATL::CComObject<CWdsTransportManager>::`vftable'
0x180008118  mov     [rbx], rax
0x18000811b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008122  mov     rax, [rcx]
0x180008125  mov     rax, [rax+8]
0x180008129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000812e  nop
0x18000812f  mov     [rsp+58h+arg_18], rbx
0x180008134  jmp     short loc_180008149
0x180008136  mov     rsi, [rsp+58h+arg_10]
0x18000813b  mov     r14, [rsp+58h+arg_8]
0x180008140  mov     edi, dword ptr [rsp+58h+arg_0]
0x180008144  mov     rbx, [rsp+58h+arg_18]
0x180008149  test    rbx, rbx
0x18000814c  jz      short loc_1800081AE
0x18000814e  lea     rcx, [rbx+8]; volatile int *
0x180008152  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180008157  lea     rcx, [rbx+10h]; this
0x18000815b  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180008160  test    eax, eax
0x180008162  js      short loc_18000816C
0x180008164  mov     rcx, rbx; this
0x180008167  call    ?FinalConstruct@CWdsTransportManager@@QEAAJXZ; CWdsTransportManager::FinalConstruct(void)
0x18000816c  xor     edi, edi
0x18000816e  test    eax, eax
0x180008170  cmovs   edi, eax
0x180008173  lea     rcx, [rbx+8]; volatile int *
0x180008177  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000817c  test    edi, edi
0x18000817e  jnz     short loc_18000819A
0x180008180  mov     rax, [rbx]
0x180008183  mov     r8, rsi
0x180008186  mov     rdx, r14
0x180008189  mov     rcx, rbx
0x18000818c  mov     rax, [rax]
0x18000818f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008194  mov     edi, eax
0x180008196  test    eax, eax
0x180008198  jz      short loc_1800081AE
0x18000819a  mov     rdx, [rbx]
0x18000819d  mov     rax, [rdx+40h]
0x1800081a1  mov     edx, 1
0x1800081a6  mov     rcx, rbx
0x1800081a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ae  mov     eax, edi
0x1800081b0  add     rsp, 30h
0x1800081b4  pop     r15
0x1800081b6  pop     r14
0x1800081b8  pop     rdi
0x1800081b9  pop     rsi
0x1800081ba  pop     rbx
0x1800081bb  retn
```
