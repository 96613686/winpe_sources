# ManifestProcessor::Remove(AbstractDomElement &,StringSet const &)

- ea: `0x140001bf0`
- end: `0x140001ccd`
- name: `?Remove@ManifestProcessor@@QEAAXAEAVAbstractDomElement@@AEBVStringSet@@@Z`
- size: `221`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, struct AbstractDomElement *, const struct StringSet *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140001ce0`

## callees

- `0x140001bf0`
- `0x140002b9c`
- `0x14000a6a0`
- `0x140031804`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ManifestProcessor::Remove(
        ManifestProcessor *this,
        struct AbstractDomElement *a2,
        const struct StringSet *a3)
{
  wmi::RefBase *v5; // rbx
  wmi::RefBase **v6; // rdi
  const wchar_t *v7; // rax
  wmi::RefBase *v8; // [rsp+58h] [rbp+10h] BYREF
  wmi::RefBase *v9; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  (*(void (__fastcall **)(struct AbstractDomElement *, wmi::RefBase **))(*(_QWORD *)a2 + 24LL))(a2, &v8);
  while ( 1 )
  {
    v6 = (wmi::RefBase **)(*(__int64 (__fastcall **)(wmi::RefBase *, wmi::RefBase **))(*(_QWORD *)v8 + 8LL))(v8, &v9);
    if ( v5 )
      wmi::RefBase::Release(v5);
    v5 = *v6;
    *v6 = 0;
    if ( v9 )
      wmi::RefBase::Release(v9);
    v9 = 0;
    if ( !v5 )
      break;
    v7 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v5 + 16LL))(v5);
    if ( !wcscmp_0(L"provider", v7) )
      ManifestProcessor::RetractProviderNode(this, v5, a3);
  }
  if ( v8 )
    wmi::RefBase::Release(v8);
}

```

## disassembly

```asm
0x140001bf0  mov     [rsp+arg_0], rbx
0x140001bf5  push    rbp
0x140001bf6  push    rsi
0x140001bf7  push    rdi
0x140001bf8  sub     rsp, 30h
0x140001bfc  mov     rsi, r8
0x140001bff  mov     r9, rdx
0x140001c02  mov     rbp, rcx
0x140001c05  xor     ebx, ebx
0x140001c07  mov     [rsp+48h+var_28], rbx
0x140001c0c  mov     rax, [rdx]
0x140001c0f  lea     rdx, [rsp+48h+arg_8]
0x140001c14  mov     rcx, r9
0x140001c17  mov     rax, [rax+18h]
0x140001c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c20  nop
0x140001c21  mov     rcx, [rsp+48h+arg_8]
0x140001c26  mov     rax, [rcx]
0x140001c29  lea     rdx, [rsp+48h+arg_18]
0x140001c2e  mov     rax, [rax+8]
0x140001c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c37  mov     rdi, rax
0x140001c3a  test    rbx, rbx
0x140001c3d  jz      short loc_140001C47
0x140001c3f  mov     rcx, rbx; this
0x140001c42  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001c47  mov     rbx, [rdi]
0x140001c4a  mov     [rsp+48h+var_28], rbx
0x140001c4f  mov     qword ptr [rdi], 0
0x140001c56  mov     rcx, [rsp+48h+arg_18]; this
0x140001c5b  test    rcx, rcx
0x140001c5e  jz      short loc_140001C65
0x140001c60  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001c65  mov     [rsp+48h+arg_18], 0
0x140001c6e  test    rbx, rbx
0x140001c71  jz      short loc_140001CA8
0x140001c73  mov     rax, [rbx]
0x140001c76  mov     rcx, rbx
0x140001c79  mov     rax, [rax+10h]
0x140001c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001c82  mov     rdx, rax; String2
0x140001c85  lea     rcx, aProvider; "provider"
0x140001c8c  call    wcscmp_0
0x140001c91  test    eax, eax
0x140001c93  jnz     short loc_140001C21
0x140001c95  mov     r8, rsi; struct StringSet *
0x140001c98  mov     rdx, rbx; struct AbstractDomElement *
0x140001c9b  mov     rcx, rbp; this
0x140001c9e  call    ?RetractProviderNode@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEBVStringSet@@@Z; ManifestProcessor::RetractProviderNode(AbstractDomElement &,StringSet const &)
0x140001ca3  jmp     loc_140001C21
0x140001ca8  mov     rcx, [rsp+48h+arg_8]; this
0x140001cad  test    rcx, rcx
0x140001cb0  jz      short loc_140001CB7
0x140001cb2  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001cb7  mov     [rsp+48h+arg_8], 0
0x140001cc0  mov     rbx, [rsp+48h+arg_0]
0x140001cc5  add     rsp, 30h
0x140001cc9  pop     rdi
0x140001cca  pop     rsi
0x140001ccb  pop     rbp
0x140001ccc  retn
```
