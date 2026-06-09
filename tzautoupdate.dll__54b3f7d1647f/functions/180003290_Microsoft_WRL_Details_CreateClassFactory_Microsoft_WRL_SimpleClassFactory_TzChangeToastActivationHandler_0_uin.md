# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180003290`
- end: `0x180003341`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VTzChangeToastActivationHandler@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003290`
- `0x180003398`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // ebx
  _DWORD *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  _DWORD *v12; // [rsp+20h] [rbp-38h] BYREF

  v12 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>,Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>,>(&v12);
  if ( v7 >= 0 )
  {
    v9 = v12;
    v12[5] = *a1;
    v10 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v9)(v9, a3, a4);
    v11 = v10;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v10 < 0 )
      {
        v9[5] &= 0xFFFFFFFA;
      }
      else if ( (*(_BYTE *)a1 & 4) != 0 )
      {
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      }
      else
      {
        v9 = 0;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return v11;
  }
  else
  {
    if ( v12 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180003290  push    rbx
0x180003292  push    rbp
0x180003293  push    rsi
0x180003294  push    rdi
0x180003295  sub     rsp, 38h
0x180003299  mov     rdi, r9
0x18000329c  mov     rbp, r8
0x18000329f  mov     rsi, rcx
0x1800032a2  mov     [rsp+58h+var_38], 0
0x1800032ab  lea     rcx, [rsp+58h+var_38]
0x1800032b0  call    ??$MakeAndInitialize@V?$SimpleClassFactory@VTzChangeToastActivationHandler@@$0A@@WRL@Microsoft@@V123@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactory@VTzChangeToastActivationHandler@@$0A@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>,Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0>,>(Microsoft::WRL::SimpleClassFactory<TzChangeToastActivationHandler,0> * *)
0x1800032b5  mov     ebx, eax
0x1800032b7  test    eax, eax
0x1800032b9  jns     short loc_1800032D6
0x1800032bb  mov     rcx, [rsp+58h+var_38]
0x1800032c0  test    rcx, rcx
0x1800032c3  jz      short loc_1800032D2
0x1800032c5  mov     rdx, [rcx]
0x1800032c8  mov     rax, [rdx+10h]
0x1800032cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d1  nop
0x1800032d2  mov     eax, ebx
0x1800032d4  jmp     short loc_180003338
0x1800032d6  mov     rbx, [rsp+58h+var_38]
0x1800032db  mov     eax, [rsi]
0x1800032dd  mov     [rbx+14h], eax
0x1800032e0  mov     rax, [rbx]
0x1800032e3  mov     r8, rdi
0x1800032e6  mov     rdx, rbp
0x1800032e9  mov     rcx, rbx
0x1800032ec  mov     rax, [rax]
0x1800032ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032f4  mov     edi, eax
0x1800032f6  test    byte ptr [rsi], 1
0x1800032f9  jz      short loc_180003321
0x1800032fb  test    eax, eax
0x1800032fd  js      short loc_18000331D
0x1800032ff  test    byte ptr [rsi], 4
0x180003302  jz      short loc_180003319
0x180003304  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000330b  mov     rax, [rcx]
0x18000330e  mov     rax, [rax+8]
0x180003312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003317  jmp     short loc_180003321
0x180003319  xor     ebx, ebx
0x18000331b  jmp     short loc_180003321
0x18000331d  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180003321  test    rbx, rbx
0x180003324  jz      short loc_180003336
0x180003326  mov     rax, [rbx]
0x180003329  mov     rcx, rbx
0x18000332c  mov     rax, [rax+10h]
0x180003330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003335  nop
0x180003336  mov     eax, edi
0x180003338  add     rsp, 38h
0x18000333c  pop     rdi
0x18000333d  pop     rsi
0x18000333e  pop     rbp
0x18000333f  pop     rbx
0x180003340  retn
```
