# ATL::CComObject<CAttributeString>::CreateInstance(ATL::CComObject<CAttributeString> * *)

- ea: `0x18000ad18`
- end: `0x18000ae48`
- name: `?CreateInstance@?$CComObject@VCAttributeString@@@ATL@@SAJPEAPEAV12@@Z`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bf40`

## callees

- `0x180001b50`
- `0x180002f3c`
- `0x180005284`
- `0x18000ad18`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ad5b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ad5b`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAttributeString>::CreateInstance(_QWORD *a1)
{
  unsigned int v3; // esi
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  _DWORD *v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rsi
  int v9; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  if ( g_heap && (v4 = HeapAlloc(g_heap, 0, 0x60u), (v5 = v4) != 0) )
  {
    v4[2] = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_BYTE *)v4 + 56) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<CAttributeString>::`vftable';
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v5 = 0;
  }
  v6 = v5;
  if ( v5 )
  {
    ATL::CComMultiThreadModel::SafeIncrementReference(v5 + 2);
    v8 = v7 + 8;
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 8));
    if ( v9 >= 0 )
    {
      *(_BYTE *)(v8 + 40) = 1;
      *((_QWORD *)v5 + 8) = 0;
      *((_QWORD *)v5 + 9) = 0;
      v5[20] = 0;
      *((_QWORD *)v5 + 11) = 0;
      v9 = 0;
    }
    v3 = 0;
    if ( v9 < 0 )
      v3 = v9;
    CTextNormMultiResult::InternalFinalConstructRelease((CTextNormMultiResult *)v5);
    if ( v3 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
      v6 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *a1 = v6;
  return v3;
}

```

## disassembly

```asm
0x18000ad18  mov     [rsp+arg_0], rcx
0x18000ad1d  push    rsi
0x18000ad1e  push    rdi
0x18000ad1f  push    r14
0x18000ad21  push    r15
0x18000ad23  sub     rsp, 28h
0x18000ad27  mov     r14, rcx
0x18000ad2a  test    rcx, rcx
0x18000ad2d  jnz     short loc_18000AD39
0x18000ad2f  mov     eax, 80004003h
0x18000ad34  jmp     loc_18000AE3D
0x18000ad39  mov     qword ptr [rcx], 0
0x18000ad40  mov     esi, 8007000Eh
0x18000ad45  mov     [rsp+48h+arg_8], esi
0x18000ad49  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x18000ad50  test    rcx, rcx
0x18000ad53  jz      short loc_18000ADA3
0x18000ad55  xor     edx, edx; dwFlags
0x18000ad57  lea     r8d, [rdx+60h]; dwBytes
0x18000ad5b  call    cs:__imp_HeapAlloc
0x18000ad61  mov     rdi, rax
0x18000ad64  test    rax, rax
0x18000ad67  jz      short loc_18000ADA3
0x18000ad69  mov     dword ptr [rax+8], 0
0x18000ad70  xorps   xmm0, xmm0
0x18000ad73  xor     eax, eax
0x18000ad75  movups  xmmword ptr [rdi+10h], xmm0
0x18000ad79  movups  xmmword ptr [rdi+20h], xmm0
0x18000ad7d  mov     [rdi+30h], rax
0x18000ad81  mov     [rdi+38h], al
0x18000ad84  lea     rax, ??_7?$CComObject@VCAttributeString@@@ATL@@6B@; const ATL::CComObject<CAttributeString>::`vftable'
0x18000ad8b  mov     [rdi], rax
0x18000ad8e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ad95  mov     rax, [rcx]
0x18000ad98  mov     rax, [rax+8]
0x18000ad9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada1  jmp     short loc_18000ADA5
0x18000ada3  xor     edi, edi
0x18000ada5  mov     [rsp+48h+arg_10], rdi
0x18000adaa  mov     r15, rdi
0x18000adad  mov     [rsp+48h+arg_18], rdi
0x18000adb2  jmp     short loc_18000ADC7
0x18000adb4  mov     r14, [rsp+48h+arg_0]
0x18000adb9  mov     esi, [rsp+48h+arg_8]
0x18000adbd  mov     r15, [rsp+48h+arg_18]
0x18000adc2  mov     rdi, [rsp+48h+arg_10]
0x18000adc7  test    rdi, rdi
0x18000adca  jz      short loc_18000AE38
0x18000adcc  lea     rcx, [rdi+8]; int *
0x18000add0  call    ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
0x18000add5  lea     rsi, [rcx+8]
0x18000add9  mov     rcx, rsi; this
0x18000addc  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ade1  test    eax, eax
0x18000ade3  js      short loc_18000AE0A
0x18000ade5  mov     byte ptr [rsi+28h], 1
0x18000ade9  mov     qword ptr [rdi+40h], 0
0x18000adf1  mov     qword ptr [rdi+48h], 0
0x18000adf9  mov     dword ptr [rdi+50h], 0
0x18000ae00  mov     qword ptr [rdi+58h], 0
0x18000ae08  xor     eax, eax
0x18000ae0a  xor     esi, esi
0x18000ae0c  test    eax, eax
0x18000ae0e  cmovs   esi, eax
0x18000ae11  mov     rcx, rdi; this
0x18000ae14  call    ?InternalFinalConstructRelease@CTextNormMultiResult@@QEAAXXZ; CTextNormMultiResult::InternalFinalConstructRelease(void)
0x18000ae19  test    esi, esi
0x18000ae1b  jz      short loc_18000AE36
0x18000ae1d  mov     rax, [rdi]
0x18000ae20  mov     edx, 1
0x18000ae25  mov     rcx, rdi
0x18000ae28  mov     rax, [rax+38h]
0x18000ae2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae31  xor     r15d, r15d
0x18000ae34  jmp     short loc_18000AE38
0x18000ae36  xor     esi, esi
0x18000ae38  mov     [r14], r15
0x18000ae3b  mov     eax, esi
0x18000ae3d  add     rsp, 28h
0x18000ae41  pop     r15
0x18000ae43  pop     r14
0x18000ae45  pop     rdi
0x18000ae46  pop     rsi
0x18000ae47  retn
```
