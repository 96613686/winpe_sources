# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800010f0`
- end: `0x180001202`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800010f0`
- `0x180001310`
- `0x180001b50`
- `0x18000597c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000114d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000114d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // edi
  _DWORD *v8; // rax
  _QWORD **v9; // rbx
  __int64 (__fastcall *v10)(_QWORD **, __int64, _QWORD *); // rax
  int Interface; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  if ( g_heap && (v8 = HeapAlloc(g_heap, 0, 0x48u), (v9 = (_QWORD **)v8) != 0) )
  {
    v8[2] = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_BYTE *)v8 + 56) = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v9[8] = a1;
    v7 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v9 + 2));
    if ( v7 < 0
      || ((*((_BYTE *)v9 + 56) = 1,
           v10 = (__int64 (__fastcall *)(_QWORD **, __int64, _QWORD *))**v9,
           (char *)v10 != (char *)ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface)
        ? (Interface = v10(v9, a2, a3))
        : (Interface = ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(v9, a2, a3)),
          (v7 = Interface) != 0) )
    {
      ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800010f0  mov     [rsp+arg_10], r8
0x1800010f5  mov     [rsp+arg_8], rdx
0x1800010fa  mov     [rsp+arg_0], rcx
0x1800010ff  push    rbx
0x180001100  push    rsi
0x180001101  push    rdi
0x180001102  push    r14
0x180001104  push    r15
0x180001106  sub     rsp, 30h
0x18000110a  mov     rsi, r8
0x18000110d  mov     r14, rdx
0x180001110  mov     r15, rcx
0x180001113  test    r8, r8
0x180001116  jnz     short loc_180001129
0x180001118  mov     eax, 80004003h
0x18000111d  add     rsp, 30h
0x180001121  pop     r15
0x180001123  pop     r14
0x180001125  pop     rdi
0x180001126  pop     rsi
0x180001127  pop     rbx
0x180001128  retn
0x180001129  mov     qword ptr [r8], 0
0x180001130  mov     edi, 8007000Eh
0x180001135  mov     [rsp+58h+arg_18], edi
0x180001139  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x180001140  test    rcx, rcx
0x180001143  jz      short loc_180001182
0x180001145  xor     edx, edx; dwFlags
0x180001147  mov     r8d, 48h ; 'H'; dwBytes
0x18000114d  call    cs:__imp_HeapAlloc
0x180001153  mov     rbx, rax
0x180001156  test    rax, rax
0x180001159  jz      short loc_180001182
0x18000115b  mov     dword ptr [rax+8], 0
0x180001162  xorps   xmm0, xmm0
0x180001165  xor     eax, eax
0x180001167  movups  xmmword ptr [rbx+10h], xmm0
0x18000116b  movups  xmmword ptr [rbx+20h], xmm0
0x18000116f  mov     [rbx+30h], rax
0x180001173  mov     [rbx+38h], al
0x180001176  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000117d  mov     [rbx], rax
0x180001180  jmp     short loc_180001184
0x180001182  xor     ebx, ebx
0x180001184  mov     [rsp+58h+var_38], rbx
0x180001189  jmp     short loc_1800011A3
0x18000118b  mov     rsi, [rsp+58h+arg_10]
0x180001190  mov     r14, [rsp+58h+arg_8]
0x180001195  mov     r15, [rsp+58h+arg_0]
0x18000119a  mov     edi, [rsp+58h+arg_18]
0x18000119e  mov     rbx, [rsp+58h+var_38]
0x1800011a3  test    rbx, rbx
0x1800011a6  jz      short loc_1800011F4
0x1800011a8  mov     [rbx+40h], r15
0x1800011ac  lea     rcx, [rbx+10h]; this
0x1800011b0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800011b5  mov     edi, eax
0x1800011b7  test    eax, eax
0x1800011b9  js      short loc_1800011EC
0x1800011bb  mov     byte ptr [rbx+38h], 1
0x1800011bf  mov     rax, [rbx]
0x1800011c2  mov     rax, [rax]
0x1800011c5  lea     rcx, ?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)
0x1800011cc  mov     r8, rsi
0x1800011cf  mov     rdx, r14
0x1800011d2  cmp     rax, rcx
0x1800011d5  mov     rcx, rbx
0x1800011d8  jnz     short loc_1800011E1
0x1800011da  call    ?QueryInterface@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObjectCached<ATL::CComClassFactory>::QueryInterface(_GUID const &,void * *)
0x1800011df  jmp     short loc_1800011E6
0x1800011e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e6  mov     edi, eax
0x1800011e8  test    eax, eax
0x1800011ea  jz      short loc_1800011F4
0x1800011ec  mov     rcx, rbx; void *
0x1800011ef  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800011f4  mov     eax, edi
0x1800011f6  add     rsp, 30h
0x1800011fa  pop     r15
0x1800011fc  pop     r14
0x1800011fe  pop     rdi
0x1800011ff  pop     rsi
0x180001200  pop     rbx
0x180001201  retn
```
