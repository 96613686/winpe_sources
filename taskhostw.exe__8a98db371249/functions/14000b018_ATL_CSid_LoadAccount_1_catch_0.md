# _ATL::CSid::LoadAccount_::_1_::catch$0

- ea: `0x14000b018`
- end: `0x14000b038`
- name: `_ATL::CSid::LoadAccount_::_1_::catch$0`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000894c`
- `0x140009680`

## pseudocode

```c
void __fastcall __noreturn ATL::CSid::LoadAccount_::_1_::catch_0(__int64 a1, __int64 a2)
{
  ATL::CSid::Clear(*(ATL::CSid **)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x14000b018  mov     [rsp+arg_8], rdx
0x14000b01d  push    rbp
0x14000b01e  sub     rsp, 20h
0x14000b022  mov     rbp, rdx
0x14000b025  mov     rcx, [rbp+30h]; this
0x14000b029  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x14000b02e  xor     edx, edx; pThrowInfo
0x14000b030  xor     ecx, ecx; pExceptionObject
0x14000b032  call    _CxxThrowException_0
```
