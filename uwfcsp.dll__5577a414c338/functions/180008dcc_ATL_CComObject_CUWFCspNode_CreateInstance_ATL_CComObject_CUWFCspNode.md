# ATL::CComObject<CUWFCspNode>::CreateInstance(ATL::CComObject<CUWFCspNode> * *)

- ea: `0x180008dcc`
- end: `0x180008ed8`
- name: `?CreateInstance@?$CComObject@VCUWFCspNode@@@ATL@@SAJPEAPEAV12@@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008ee0`

## callees

- `0x180002c54`
- `0x180008dcc`
- `0x1800094e8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNode>::CreateInstance(_QWORD *a1)
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
    *(_QWORD *)v3 = &CUWFCspNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_180028594);
    v5 = ATL::_pAtlModule;
    *(_QWORD *)v3 = &ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNodeTransactioning'};
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
0x180008dcc  mov     [rsp+arg_0], rbx
0x180008dd1  mov     [rsp+arg_8], rsi
0x180008dd6  push    rdi
0x180008dd7  sub     rsp, 20h
0x180008ddb  mov     rsi, rcx
0x180008dde  test    rcx, rcx
0x180008de1  jnz     short loc_180008DED
0x180008de3  mov     eax, 80004003h
0x180008de8  jmp     loc_180008EC8
0x180008ded  mov     qword ptr [rcx], 0
0x180008df4  mov     ecx, 80h; Size
0x180008df9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008dfe  mov     rbx, rax
0x180008e01  test    rax, rax
0x180008e04  jz      loc_180008EBC
0x180008e0a  mov     dword ptr [rax+48h], 0
0x180008e11  xorps   xmm0, xmm0
0x180008e14  movups  xmmword ptr [rbx+50h], xmm0
0x180008e18  xor     eax, eax
0x180008e1a  movups  xmmword ptr [rbx+60h], xmm0
0x180008e1e  mov     [rbx+70h], rax
0x180008e22  mov     [rbx+78h], al
0x180008e25  mov     [rbx+10h], rax
0x180008e29  mov     [rbx+18h], rax
0x180008e2d  lea     rax, ??_7CUWFCspNode@@6BICSPNode@@@; const CUWFCspNode::`vftable'{for `ICSPNode'}
0x180008e34  mov     dword ptr [rbx+40h], 1
0x180008e3b  movups  xmmword ptr [rbx+20h], xmm0
0x180008e3f  movups  xmmword ptr [rbx+30h], xmm0
0x180008e43  mov     [rbx], rax
0x180008e46  lea     rax, ??_7CUWFCspNode@@6BICSPNodeTransactioning@@@; const CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'}
0x180008e4d  mov     [rbx+8], rax
0x180008e51  lock inc cs:dword_180028594
0x180008e58  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008e5f  lea     rax, ??_7?$CComObject@VCUWFCspNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNode'}
0x180008e66  mov     [rbx], rax
0x180008e69  lea     rax, ??_7?$CComObject@VCUWFCspNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspNode>::`vftable'{for `ICSPNodeTransactioning'}
0x180008e70  mov     [rbx+8], rax
0x180008e74  mov     rax, [rcx]
0x180008e77  mov     rax, [rax+8]
0x180008e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e80  lea     rcx, [rbx+50h]; this
0x180008e84  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008e89  test    eax, eax
0x180008e8b  js      short loc_180008E91
0x180008e8d  mov     byte ptr [rbx+78h], 1
0x180008e91  xor     ecx, ecx
0x180008e93  test    eax, eax
0x180008e95  cmovs   ecx, eax
0x180008e98  xor     edi, edi
0x180008e9a  test    ecx, ecx
0x180008e9c  cmovs   edi, ecx
0x180008e9f  test    edi, edi
0x180008ea1  jz      short loc_180008EC3
0x180008ea3  mov     rax, [rbx]
0x180008ea6  mov     edx, 1
0x180008eab  mov     rcx, rbx
0x180008eae  mov     rax, [rax+80h]
0x180008eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eba  jmp     short loc_180008EC1
0x180008ebc  mov     edi, 8007000Eh
0x180008ec1  xor     ebx, ebx
0x180008ec3  mov     [rsi], rbx
0x180008ec6  mov     eax, edi
0x180008ec8  mov     rbx, [rsp+28h+arg_0]
0x180008ecd  mov     rsi, [rsp+28h+arg_8]
0x180008ed2  add     rsp, 20h
0x180008ed6  pop     rdi
0x180008ed7  retn
```
