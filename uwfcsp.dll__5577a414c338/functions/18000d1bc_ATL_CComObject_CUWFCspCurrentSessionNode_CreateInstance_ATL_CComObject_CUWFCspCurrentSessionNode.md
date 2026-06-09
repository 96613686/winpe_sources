# ATL::CComObject<CUWFCspCurrentSessionNode>::CreateInstance(ATL::CComObject<CUWFCspCurrentSessionNode> * *)

- ea: `0x18000d1bc`
- end: `0x18000d2c8`
- name: `?CreateInstance@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@SAJPEAPEAV12@@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d2d0`

## callees

- `0x180002c54`
- `0x1800094e8`
- `0x18000d1bc`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::CreateInstance(_QWORD *a1)
{
  _BYTE *v3; // rax
  _BYTE *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = operator new(0x80u);
  v4 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 18) = 0;
    *((_OWORD *)v3 + 5) = 0;
    *((_OWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 14) = 0;
    v3[120] = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_DWORD *)v3 + 16) = 1;
    *((_OWORD *)v3 + 2) = 0;
    *((_OWORD *)v3 + 3) = 0;
    *(_QWORD *)v3 = &CUWFCspCurrentSessionNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_180028594);
    v5 = ATL::_pAtlModule;
    *(_QWORD *)v3 = &ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNodeTransactioning'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 80));
    if ( v6 >= 0 )
      v4[120] = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v8 = 0;
    if ( v7 < 0 )
      v8 = v7;
    if ( !v8 )
      goto LABEL_14;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v4 + 128LL))(v4, 1);
  }
  else
  {
    v8 = -2147024882;
  }
  v4 = 0;
LABEL_14:
  *a1 = v4;
  return v8;
}

```

## disassembly

```asm
0x18000d1bc  mov     [rsp+arg_0], rbx
0x18000d1c1  mov     [rsp+arg_8], rsi
0x18000d1c6  push    rdi
0x18000d1c7  sub     rsp, 20h
0x18000d1cb  mov     rsi, rcx
0x18000d1ce  test    rcx, rcx
0x18000d1d1  jnz     short loc_18000D1DD
0x18000d1d3  mov     eax, 80004003h
0x18000d1d8  jmp     loc_18000D2B8
0x18000d1dd  mov     qword ptr [rcx], 0
0x18000d1e4  mov     ecx, 80h; Size
0x18000d1e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d1ee  mov     rbx, rax
0x18000d1f1  test    rax, rax
0x18000d1f4  jz      loc_18000D2AC
0x18000d1fa  mov     dword ptr [rax+48h], 0
0x18000d201  xorps   xmm0, xmm0
0x18000d204  movups  xmmword ptr [rbx+50h], xmm0
0x18000d208  xor     eax, eax
0x18000d20a  movups  xmmword ptr [rbx+60h], xmm0
0x18000d20e  mov     [rbx+70h], rax
0x18000d212  mov     [rbx+78h], al
0x18000d215  mov     [rbx+10h], rax
0x18000d219  mov     [rbx+18h], rax
0x18000d21d  lea     rax, ??_7CUWFCspCurrentSessionNode@@6BICSPNode@@@; const CUWFCspCurrentSessionNode::`vftable'{for `ICSPNode'}
0x18000d224  mov     dword ptr [rbx+40h], 1
0x18000d22b  movups  xmmword ptr [rbx+20h], xmm0
0x18000d22f  movups  xmmword ptr [rbx+30h], xmm0
0x18000d233  mov     [rbx], rax
0x18000d236  lea     rax, ??_7CUWFCspNode@@6BICSPNodeTransactioning@@@; const CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000d23d  mov     [rbx+8], rax
0x18000d241  lock inc cs:dword_180028594
0x18000d248  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d24f  lea     rax, ??_7?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNode'}
0x18000d256  mov     [rbx], rax
0x18000d259  lea     rax, ??_7?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspCurrentSessionNode>::`vftable'{for `ICSPNodeTransactioning'}
0x18000d260  mov     [rbx+8], rax
0x18000d264  mov     rax, [rcx]
0x18000d267  mov     rax, [rax+8]
0x18000d26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d270  lea     rcx, [rbx+50h]; this
0x18000d274  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000d279  test    eax, eax
0x18000d27b  js      short loc_18000D281
0x18000d27d  mov     byte ptr [rbx+78h], 1
0x18000d281  xor     ecx, ecx
0x18000d283  test    eax, eax
0x18000d285  cmovs   ecx, eax
0x18000d288  xor     edi, edi
0x18000d28a  test    ecx, ecx
0x18000d28c  cmovs   edi, ecx
0x18000d28f  test    edi, edi
0x18000d291  jz      short loc_18000D2B3
0x18000d293  mov     rax, [rbx]
0x18000d296  mov     edx, 1
0x18000d29b  mov     rcx, rbx
0x18000d29e  mov     rax, [rax+80h]
0x18000d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2aa  jmp     short loc_18000D2B1
0x18000d2ac  mov     edi, 8007000Eh
0x18000d2b1  xor     ebx, ebx
0x18000d2b3  mov     [rsi], rbx
0x18000d2b6  mov     eax, edi
0x18000d2b8  mov     rbx, [rsp+28h+arg_0]
0x18000d2bd  mov     rsi, [rsp+28h+arg_8]
0x18000d2c2  add     rsp, 20h
0x18000d2c6  pop     rdi
0x18000d2c7  retn
```
