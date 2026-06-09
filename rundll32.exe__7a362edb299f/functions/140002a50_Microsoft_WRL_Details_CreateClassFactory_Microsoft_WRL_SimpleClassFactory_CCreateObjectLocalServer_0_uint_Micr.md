# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x140002a50`
- end: `0x140002b21`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCCreateObjectLocalServer@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400015c4`
- `0x140002a50`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    v7[3] = 1;
    v7[5] = 4;
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::`vftable';
    ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    v8[5] = *a1;
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
    v10 = v9;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      if ( v9 < 0 )
      {
        v8[5] &= 0xFFFFFFFA;
      }
      else
      {
        if ( (*(_BYTE *)a1 & 4) != 0 )
          (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                            + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
        else
          v8 = 0;
        if ( !v8 )
          return v10;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140002a50  push    rbx
0x140002a52  push    rbp
0x140002a53  push    rsi
0x140002a54  push    rdi
0x140002a55  sub     rsp, 28h
0x140002a59  mov     rsi, rcx
0x140002a5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002a63  mov     ecx, 18h; unsigned __int64
0x140002a68  mov     rdi, r9
0x140002a6b  mov     rbp, r8
0x140002a6e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140002a73  mov     rbx, rax
0x140002a76  test    rax, rax
0x140002a79  jz      loc_140002B13
0x140002a7f  mov     dword ptr [rax+0Ch], 1
0x140002a86  mov     rcx, rbx
0x140002a89  mov     dword ptr [rax+14h], 4
0x140002a90  lea     rax, ??_7?$SimpleClassFactory@VCCreateObjectLocalServer@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CCreateObjectLocalServer,0>::`vftable'
0x140002a97  mov     [rbx], rax
0x140002a9a  mov     rax, cs:off_14000D0B0
0x140002aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002aa6  mov     rax, [rbx]
0x140002aa9  mov     rcx, rbx
0x140002aac  mov     rax, [rax+10h]
0x140002ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ab5  mov     eax, [rsi]
0x140002ab7  mov     r8, rdi
0x140002aba  mov     [rbx+14h], eax
0x140002abd  mov     rdx, rbp
0x140002ac0  mov     rax, [rbx]
0x140002ac3  mov     rcx, rbx
0x140002ac6  mov     rax, [rax]
0x140002ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ace  test    byte ptr [rsi], 1
0x140002ad1  mov     edi, eax
0x140002ad3  jz      short loc_140002B00
0x140002ad5  test    eax, eax
0x140002ad7  js      short loc_140002AFC
0x140002ad9  test    byte ptr [rsi], 4
0x140002adc  jz      short loc_140002AF3
0x140002ade  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140002ae5  mov     rdx, [rcx]
0x140002ae8  mov     rax, [rdx+8]
0x140002aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002af1  jmp     short loc_140002AF5
0x140002af3  xor     ebx, ebx
0x140002af5  test    rbx, rbx
0x140002af8  jz      short loc_140002B0F
0x140002afa  jmp     short loc_140002B00
0x140002afc  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x140002b00  mov     rax, [rbx]
0x140002b03  mov     rcx, rbx
0x140002b06  mov     rax, [rax+10h]
0x140002b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b0f  mov     eax, edi
0x140002b11  jmp     short loc_140002B18
0x140002b13  mov     eax, 8007000Eh
0x140002b18  add     rsp, 28h
0x140002b1c  pop     rdi
0x140002b1d  pop     rsi
0x140002b1e  pop     rbp
0x140002b1f  pop     rbx
0x140002b20  retn
```
