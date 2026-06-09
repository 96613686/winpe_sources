# Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005140`
- end: `0x1800051e8`
- name: `?CreateInstance@?$SimpleClassFactory@VTzChangeToastActivationHandler@@$0A@@WRL@Microsoft@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003430`
- `0x180005140`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000516a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000516a`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  int v6; // ebx
  __int64 v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  *a4 = 0;
  if ( a2 )
  {
    v6 = -2147221232;
    RoOriginateError(2147746064LL, 0);
    return (unsigned int)v6;
  }
  v10 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<TzChangeToastActivationHandler,IUnknown,>(&v10);
  if ( v6 < 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)v6;
  }
  v8 = v10;
  v9 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v10)(v10, a3, a4);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v9;
}

```

## disassembly

```asm
0x180005140  mov     [rsp+arg_0], rbx
0x180005145  mov     [rsp+arg_10], rsi
0x18000514a  push    rdi
0x18000514b  sub     rsp, 20h
0x18000514f  mov     rdi, r9
0x180005152  mov     rsi, r8
0x180005155  mov     qword ptr [r9], 0
0x18000515c  test    rdx, rdx
0x18000515f  jz      short loc_180005174
0x180005161  xor     edx, edx
0x180005163  mov     ebx, 80040110h
0x180005168  mov     ecx, ebx
0x18000516a  call    cs:__imp_RoOriginateError
0x180005170  mov     eax, ebx
0x180005172  jmp     short loc_1800051D8
0x180005174  mov     [rsp+28h+arg_8], 0
0x18000517d  lea     rcx, [rsp+28h+arg_8]
0x180005182  call    ??$MakeAndInitialize@VTzChangeToastActivationHandler@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TzChangeToastActivationHandler,IUnknown,>(IUnknown * *)
0x180005187  mov     ebx, eax
0x180005189  test    eax, eax
0x18000518b  jns     short loc_1800051A6
0x18000518d  mov     rcx, [rsp+28h+arg_8]
0x180005192  test    rcx, rcx
0x180005195  jz      short loc_1800051A4
0x180005197  mov     rdx, [rcx]
0x18000519a  mov     rax, [rdx+10h]
0x18000519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a3  nop
0x1800051a4  jmp     short loc_180005170
0x1800051a6  mov     rbx, [rsp+28h+arg_8]
0x1800051ab  mov     rax, [rbx]
0x1800051ae  mov     r8, rdi
0x1800051b1  mov     rdx, rsi
0x1800051b4  mov     rcx, rbx
0x1800051b7  mov     rax, [rax]
0x1800051ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051bf  mov     edi, eax
0x1800051c1  test    rbx, rbx
0x1800051c4  jz      short loc_1800051D6
0x1800051c6  mov     rdx, [rbx]
0x1800051c9  mov     rcx, rbx
0x1800051cc  mov     rax, [rdx+10h]
0x1800051d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d5  nop
0x1800051d6  mov     eax, edi
0x1800051d8  mov     rbx, [rsp+28h+arg_0]
0x1800051dd  mov     rsi, [rsp+28h+arg_10]
0x1800051e2  add     rsp, 20h
0x1800051e6  pop     rdi
0x1800051e7  retn
```
