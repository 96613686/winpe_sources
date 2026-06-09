# CWinTaskClassFactoryT<CUsbCeipTask,1>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800037f0`
- end: `0x18000385c`
- name: `?QueryInterface@?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800037f0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CUsbCeipTask,1>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *a2 - *(_QWORD *)&IID_IClassFactory.Data1;
  if ( *a2 == *(_QWORD *)&IID_IClassFactory.Data1 )
    v4 = a2[1] - *(_QWORD *)IID_IClassFactory.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *a2 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = a2[1] - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x1800037f0  sub     rsp, 28h
0x1800037f4  test    r8, r8
0x1800037f7  jnz     short loc_180003800
0x1800037f9  mov     eax, 80070057h
0x1800037fe  jmp     short loc_180003857
0x180003800  mov     rax, [rdx]
0x180003803  sub     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000380a  jnz     short loc_180003817
0x18000380c  mov     rax, [rdx+8]
0x180003810  sub     rax, qword ptr cs:IID_IClassFactory.Data4
0x180003817  test    rax, rax
0x18000381a  jz      short loc_180003846
0x18000381c  mov     rax, [rdx]
0x18000381f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180003826  jnz     short loc_180003833
0x180003828  mov     rax, [rdx+8]
0x18000382c  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180003833  test    rax, rax
0x180003836  jz      short loc_180003846
0x180003838  mov     qword ptr [r8], 0
0x18000383f  mov     eax, 80004002h
0x180003844  jmp     short loc_180003857
0x180003846  mov     [r8], rcx
0x180003849  mov     rax, [rcx]
0x18000384c  mov     rax, [rax+8]
0x180003850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003855  xor     eax, eax
0x180003857  add     rsp, 28h
0x18000385b  retn
```
