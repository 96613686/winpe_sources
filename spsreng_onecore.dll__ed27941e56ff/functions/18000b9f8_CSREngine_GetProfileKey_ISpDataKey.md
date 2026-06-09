# CSREngine::GetProfileKey(ISpDataKey * *)

- ea: `0x18000b9f8`
- end: `0x18000ba87`
- name: `?GetProfileKey@CSREngine@@QEAAJPEAPEAUISpDataKey@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(CSREngine *__hidden this, struct ISpDataKey **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007b70`
- `0x18000bb5c`
- `0x180011f8c`

## callees

- `0x1800061d0`
- `0x18000b9f8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000ba1e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000ba1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSREngine::GetProfileKey(const IID *this, struct ISpDataKey **a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  v4 = StringFromCLSID(this + 7, (LPOLESTR *)&v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, struct ISpDataKey **))(**(_QWORD **)this[15].Data4 + 72LL))(
           *(_QWORD *)this[15].Data4,
           v6,
           a2);
    if ( v4 == -2147200966 )
      v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID, struct ISpDataKey **))(**(_QWORD **)this[15].Data4 + 80LL))(
             *(_QWORD *)this[15].Data4,
             v6,
             a2);
  }
  CSpDynamicString::_free(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b9f8  mov     rax, rsp
0x18000b9fb  mov     [rax+10h], rbx
0x18000b9ff  mov     [rax+18h], rsi
0x18000ba03  push    rdi
0x18000ba04  sub     rsp, 20h
0x18000ba08  mov     rsi, rdx
0x18000ba0b  mov     rdi, rcx
0x18000ba0e  mov     qword ptr [rax+8], 0
0x18000ba16  add     rcx, 70h ; 'p'; rclsid
0x18000ba1a  lea     rdx, [rax+8]; lplpsz
0x18000ba1e  call    cs:__imp_StringFromCLSID
0x18000ba24  mov     ebx, eax
0x18000ba26  test    eax, eax
0x18000ba28  js      short loc_18000BA6B
0x18000ba2a  mov     rcx, [rdi+0F8h]
0x18000ba31  mov     rax, [rcx]
0x18000ba34  mov     r8, rsi
0x18000ba37  mov     rdx, [rsp+28h+arg_0]
0x18000ba3c  mov     rax, [rax+48h]
0x18000ba40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba45  mov     ebx, eax
0x18000ba47  cmp     eax, 8004503Ah
0x18000ba4c  jnz     short loc_18000BA6B
0x18000ba4e  mov     rcx, [rdi+0F8h]
0x18000ba55  mov     rax, [rcx]
0x18000ba58  mov     r8, rsi
0x18000ba5b  mov     rdx, [rsp+28h+arg_0]
0x18000ba60  mov     rax, [rax+50h]
0x18000ba64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba69  mov     ebx, eax
0x18000ba6b  lea     rcx, [rsp+28h+arg_0]; this
0x18000ba70  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x18000ba75  mov     eax, ebx
0x18000ba77  mov     rbx, [rsp+28h+arg_8]
0x18000ba7c  mov     rsi, [rsp+28h+arg_10]
0x18000ba81  add     rsp, 20h
0x18000ba85  pop     rdi
0x18000ba86  retn
```
