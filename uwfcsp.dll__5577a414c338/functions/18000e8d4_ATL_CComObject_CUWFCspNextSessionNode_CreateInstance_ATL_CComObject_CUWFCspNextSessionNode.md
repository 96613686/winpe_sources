# ATL::CComObject<CUWFCspNextSessionNode>::CreateInstance(ATL::CComObject<CUWFCspNextSessionNode> * *)

- ea: `0x18000e8d4`
- end: `0x18000e9e0`
- name: `?CreateInstance@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@SAJPEAPEAV12@@Z`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e9f0`

## callees

- `0x180002c54`
- `0x1800094e8`
- `0x18000e8d4`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNextSessionNode>::CreateInstance(_QWORD *a1)
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
    *(_QWORD *)v3 = &CUWFCspNextSessionNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &CUWFCspNextSessionNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_180028594);
    v5 = ATL::_pAtlModule;
    *(_QWORD *)v3 = &ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNode'};
    *((_QWORD *)v3 + 1) = &ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNodeTransactioning'};
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
0x18000e8d4  mov     [rsp+arg_0], rbx
0x18000e8d9  mov     [rsp+arg_8], rsi
0x18000e8de  push    rdi
0x18000e8df  sub     rsp, 20h
0x18000e8e3  mov     rsi, rcx
0x18000e8e6  test    rcx, rcx
0x18000e8e9  jnz     short loc_18000E8F5
0x18000e8eb  mov     eax, 80004003h
0x18000e8f0  jmp     loc_18000E9D0
0x18000e8f5  mov     qword ptr [rcx], 0
0x18000e8fc  mov     ecx, 80h; Size
0x18000e901  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e906  mov     rbx, rax
0x18000e909  test    rax, rax
0x18000e90c  jz      loc_18000E9C4
0x18000e912  mov     dword ptr [rax+48h], 0
0x18000e919  xorps   xmm0, xmm0
0x18000e91c  movups  xmmword ptr [rbx+50h], xmm0
0x18000e920  xor     eax, eax
0x18000e922  movups  xmmword ptr [rbx+60h], xmm0
0x18000e926  mov     [rbx+70h], rax
0x18000e92a  mov     [rbx+78h], al
0x18000e92d  mov     [rbx+10h], rax
0x18000e931  mov     [rbx+18h], rax
0x18000e935  lea     rax, ??_7CUWFCspNextSessionNode@@6BICSPNode@@@; const CUWFCspNextSessionNode::`vftable'{for `ICSPNode'}
0x18000e93c  mov     dword ptr [rbx+40h], 1
0x18000e943  movups  xmmword ptr [rbx+20h], xmm0
0x18000e947  movups  xmmword ptr [rbx+30h], xmm0
0x18000e94b  mov     [rbx], rax
0x18000e94e  lea     rax, ??_7CUWFCspNextSessionNode@@6BICSPNodeTransactioning@@@; const CUWFCspNextSessionNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000e955  mov     [rbx+8], rax
0x18000e959  lock inc cs:dword_180028594
0x18000e960  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e967  lea     rax, ??_7?$CComObject@VCUWFCspNextSessionNode@@@ATL@@6BICSPNode@@@; const ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNode'}
0x18000e96e  mov     [rbx], rax
0x18000e971  lea     rax, ??_7?$CComObject@VCUWFCspNextSessionNode@@@ATL@@6BICSPNodeTransactioning@@@; const ATL::CComObject<CUWFCspNextSessionNode>::`vftable'{for `ICSPNodeTransactioning'}
0x18000e978  mov     [rbx+8], rax
0x18000e97c  mov     rax, [rcx]
0x18000e97f  mov     rax, [rax+8]
0x18000e983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e988  lea     rcx, [rbx+50h]; this
0x18000e98c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000e991  test    eax, eax
0x18000e993  js      short loc_18000E999
0x18000e995  mov     byte ptr [rbx+78h], 1
0x18000e999  xor     ecx, ecx
0x18000e99b  test    eax, eax
0x18000e99d  cmovs   ecx, eax
0x18000e9a0  xor     edi, edi
0x18000e9a2  test    ecx, ecx
0x18000e9a4  cmovs   edi, ecx
0x18000e9a7  test    edi, edi
0x18000e9a9  jz      short loc_18000E9CB
0x18000e9ab  mov     rax, [rbx]
0x18000e9ae  mov     edx, 1
0x18000e9b3  mov     rcx, rbx
0x18000e9b6  mov     rax, [rax+80h]
0x18000e9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9c2  jmp     short loc_18000E9C9
0x18000e9c4  mov     edi, 8007000Eh
0x18000e9c9  xor     ebx, ebx
0x18000e9cb  mov     [rsi], rbx
0x18000e9ce  mov     eax, edi
0x18000e9d0  mov     rbx, [rsp+28h+arg_0]
0x18000e9d5  mov     rsi, [rsp+28h+arg_8]
0x18000e9da  add     rsp, 20h
0x18000e9de  pop     rdi
0x18000e9df  retn
```
