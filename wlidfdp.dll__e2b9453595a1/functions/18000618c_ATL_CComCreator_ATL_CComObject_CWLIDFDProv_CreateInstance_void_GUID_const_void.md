# ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000618c`
- end: `0x1800062a2`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWLIDFDProv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006060`

## callees

- `0x180002c20`
- `0x18000424c`
- `0x1800051b0`
- `0x18000618c`
- `0x18000867c`
- `0x1800086a4`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  volatile int *v6; // rbx
  int v7; // edi
  volatile int *v10; // [rsp+88h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v6 = (volatile int *)operator new(0x90u);
    CWLIDFDProv::CWLIDFDProv((CWLIDFDProv *)v6);
    *(_QWORD *)v6 = &ATL::CComObject<CWLIDFDProv>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v10 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v6 = v10;
  }
  if ( v6 )
  {
    ATL::SafeIncrementReferenceMultiThread(v6 + 2);
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v6 + 4));
    if ( v7 >= 0 )
    {
      *((_BYTE *)v6 + 56) = 1;
      v7 = 0;
    }
    ATL::SafeDecrementReferenceMultiThread(v6 + 2);
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)((void *)v6, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v6 + 88LL))(v6, 1);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000618c  mov     [rsp+arg_10], r8
0x180006191  mov     [rsp+arg_8], rdx
0x180006196  mov     [rsp+arg_0], rcx
0x18000619b  push    rbx
0x18000619c  push    rsi
0x18000619d  push    rdi
0x18000619e  push    r12
0x1800061a0  push    r14
0x1800061a2  push    r15
0x1800061a4  sub     rsp, 38h
0x1800061a8  mov     rsi, r8
0x1800061ab  mov     r14, rdx
0x1800061ae  test    r8, r8
0x1800061b1  jnz     short loc_1800061BD
0x1800061b3  mov     eax, 80004003h
0x1800061b8  jmp     loc_180006294
0x1800061bd  mov     qword ptr [r8], 0
0x1800061c4  mov     edi, 8007000Eh
0x1800061c9  mov     dword ptr [rsp+68h+arg_0], edi
0x1800061cd  mov     [rsp+68h+arg_18], 0
0x1800061d9  mov     ecx, 90h; Size
0x1800061de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061e3  mov     rbx, rax
0x1800061e6  mov     [rsp+68h+var_48], rax
0x1800061eb  mov     rcx, rax; this
0x1800061ee  call    ??0CWLIDFDProv@@QEAA@XZ; CWLIDFDProv::CWLIDFDProv(void)
0x1800061f3  lea     rax, ??_7?$CComObject@VCWLIDFDProv@@@ATL@@6B@; const ATL::CComObject<CWLIDFDProv>::`vftable'
0x1800061fa  mov     [rbx], rax
0x1800061fd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006204  mov     rax, [rcx]
0x180006207  mov     rax, [rax+8]
0x18000620b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006210  nop
0x180006211  mov     [rsp+68h+arg_18], rbx
0x180006219  jmp     short loc_180006234
0x18000621b  mov     rsi, [rsp+68h+arg_10]
0x180006223  mov     r14, [rsp+68h+arg_8]
0x180006228  mov     edi, dword ptr [rsp+68h+arg_0]
0x18000622c  mov     rbx, [rsp+68h+arg_18]
0x180006234  test    rbx, rbx
0x180006237  jz      short loc_180006292
0x180006239  lea     rcx, [rbx+8]; volatile int *
0x18000623d  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180006242  lea     rcx, [rbx+10h]; this
0x180006246  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000624b  mov     edi, eax
0x18000624d  test    eax, eax
0x18000624f  js      short loc_180006257
0x180006251  mov     byte ptr [rbx+38h], 1
0x180006255  xor     edi, edi
0x180006257  lea     rcx, [rbx+8]; volatile int *
0x18000625b  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180006260  test    edi, edi
0x180006262  jnz     short loc_18000627E
0x180006264  mov     rax, [rbx]
0x180006267  mov     r8, rsi
0x18000626a  mov     rdx, r14
0x18000626d  mov     rcx, rbx
0x180006270  mov     rax, [rax]
0x180006273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006278  mov     edi, eax
0x18000627a  test    eax, eax
0x18000627c  jz      short loc_180006292
0x18000627e  mov     r8, [rbx]
0x180006281  mov     edx, 1
0x180006286  mov     rcx, rbx
0x180006289  mov     rax, [r8+58h]
0x18000628d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006292  mov     eax, edi
0x180006294  add     rsp, 38h
0x180006298  pop     r15
0x18000629a  pop     r14
0x18000629c  pop     r12
0x18000629e  pop     rdi
0x18000629f  pop     rsi
0x1800062a0  pop     rbx
0x1800062a1  retn
```
