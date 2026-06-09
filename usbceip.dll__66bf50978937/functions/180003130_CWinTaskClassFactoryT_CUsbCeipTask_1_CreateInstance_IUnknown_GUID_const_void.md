# CWinTaskClassFactoryT<CUsbCeipTask,1>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003130`
- end: `0x1800031fe`
- name: `?CreateInstance@?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000246c`
- `0x180003130`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CUsbCeipTask,1>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v6; // edi
  _QWORD *v7; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x38u);
      v7[1] = 0;
      *((_DWORD *)v7 + 4) = 0;
      v7[3] = -1;
      *((_DWORD *)v7 + 8) = 1;
      *((_DWORD *)v7 + 9) = 0;
      v7[5] = 0;
      v7[6] = 0;
      _InterlockedAdd(&CWinTaskHandler::s_cInstances, 1u);
      *v7 = &CUsbCeipTask::`vftable';
      *((_DWORD *)v7 + 4) = 1;
      v6 = ((__int64 (__fastcall *)(_QWORD *, __int64, _QWORD *))CUsbCeipTask::`vftable')(v7, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v7 + 16LL))(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180003130  mov     [rsp+arg_0], rbx
0x180003135  mov     [rsp+arg_8], rsi
0x18000313a  push    rdi
0x18000313b  sub     rsp, 20h
0x18000313f  mov     rdi, r9
0x180003142  mov     rsi, r8
0x180003145  test    r9, r9
0x180003148  jnz     short loc_180003154
0x18000314a  mov     edi, 80070057h
0x18000314f  jmp     loc_1800031EC
0x180003154  mov     qword ptr [r9], 0
0x18000315b  test    rdx, rdx
0x18000315e  jz      short loc_18000316A
0x180003160  mov     edi, 80040110h
0x180003165  jmp     loc_1800031EC
0x18000316a  mov     ecx, 38h ; '8'; Size
0x18000316f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003174  mov     ecx, 1
0x180003179  mov     [rsp+28h+arg_18], rax
0x18000317e  mov     rbx, rax
0x180003181  mov     qword ptr [rax+8], 0
0x180003189  mov     dword ptr [rax+10h], 0
0x180003190  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180003198  mov     [rax+20h], ecx
0x18000319b  mov     dword ptr [rax+24h], 0
0x1800031a2  mov     qword ptr [rax+28h], 0
0x1800031aa  mov     qword ptr [rax+30h], 0
0x1800031b2  lock add cs:?s_cInstances@CWinTaskHandler@@0JC, ecx; long volatile CWinTaskHandler::s_cInstances
0x1800031b9  lea     rax, ??_7CUsbCeipTask@@6B@; const CUsbCeipTask::`vftable'
0x1800031c0  mov     r8, rdi
0x1800031c3  mov     [rbx], rax
0x1800031c6  mov     rdx, rsi
0x1800031c9  mov     [rbx+10h], ecx
0x1800031cc  mov     rcx, rbx
0x1800031cf  mov     rax, cs:??_7CUsbCeipTask@@6B@; const CUsbCeipTask::`vftable'
0x1800031d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031db  mov     edi, eax
0x1800031dd  mov     rcx, [rbx]
0x1800031e0  mov     rax, [rcx+10h]
0x1800031e4  mov     rcx, rbx
0x1800031e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ec  mov     rbx, [rsp+28h+arg_0]
0x1800031f1  mov     eax, edi
0x1800031f3  mov     rsi, [rsp+28h+arg_8]
0x1800031f8  add     rsp, 20h
0x1800031fc  pop     rdi
0x1800031fd  retn
```
