# Microsoft::WRL::Details::MakeAndInitialize<CCreateObjectLocalServer,IUnknown,>(IUnknown * *)

- ea: `0x140002b28`
- end: `0x140002bd7`
- name: `??$MakeAndInitialize@VCCreateObjectLocalServer@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004210`

## callees

- `0x1400015c4`
- `0x140002b28`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140002b9b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140002b9b`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCreateObjectLocalServer,IUnknown,>(_QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi
  Microsoft::WRL::Details *v5; // rcx
  unsigned int v6; // ebx

  *a1 = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  v2[3] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable';
  if ( v5 )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v5 + 8LL))(v5);
  *(_QWORD *)v3 = &CCreateObjectLocalServer::`vftable';
  if ( g_hConnected )
    SetEvent(g_hConnected);
  v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, a1);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x140002b28  mov     [rsp+arg_0], rbx
0x140002b2d  push    rdi
0x140002b2e  sub     rsp, 20h
0x140002b32  mov     rbx, rcx
0x140002b35  mov     qword ptr [rcx], 0
0x140002b3c  mov     ecx, 10h; unsigned __int64
0x140002b41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140002b48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140002b4d  mov     rdi, rax
0x140002b50  test    rax, rax
0x140002b53  jnz     short loc_140002B5C
0x140002b55  mov     eax, 8007000Eh
0x140002b5a  jmp     short loc_140002BCC
0x140002b5c  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140002b63  mov     dword ptr [rax+0Ch], 1
0x140002b6a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICreateObject@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICreateObject>::`vftable'
0x140002b71  mov     [rdi], rax
0x140002b74  test    rcx, rcx
0x140002b77  jz      short loc_140002B85
0x140002b79  mov     rax, [rcx]
0x140002b7c  mov     rax, [rax+8]
0x140002b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b85  lea     rax, ??_7CCreateObjectLocalServer@@6B@; const CCreateObjectLocalServer::`vftable'
0x140002b8c  mov     [rdi], rax
0x140002b8f  mov     rcx, cs:?g_hConnected@@3PEAXEA; hEvent
0x140002b96  test    rcx, rcx
0x140002b99  jz      short loc_140002BA1
0x140002b9b  call    cs:__imp_SetEvent
0x140002ba1  mov     rax, [rdi]
0x140002ba4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140002bab  mov     r8, rbx
0x140002bae  mov     rcx, rdi
0x140002bb1  mov     rax, [rax]
0x140002bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bb9  mov     rcx, [rdi]
0x140002bbc  mov     ebx, eax
0x140002bbe  mov     rax, [rcx+10h]
0x140002bc2  mov     rcx, rdi
0x140002bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bca  mov     eax, ebx
0x140002bcc  mov     rbx, [rsp+28h+arg_0]
0x140002bd1  add     rsp, 20h
0x140002bd5  pop     rdi
0x140002bd6  retn
```
