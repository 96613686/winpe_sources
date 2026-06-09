# _ATL::CSid::Sid_::_1_::catch$0

- ea: `0x140007766`
- end: `0x14000778a`
- name: `_ATL::CSid::Sid_::_1_::catch$0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x14000326c`
- `0x1400075c4`

## pseudocode

```c
void __fastcall __noreturn ATL::CSid::Sid_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3)
{
  ATL::CSimpleStringT<unsigned short,0>::Empty(*(_QWORD *)(a2 + 48) + 104LL, a2, a3);
  throw;
}

```

## disassembly

```asm
0x140007766  mov     [rsp+arg_8], rdx
0x14000776b  push    rbp
0x14000776c  sub     rsp, 20h
0x140007770  mov     rbp, rdx
0x140007773  mov     rcx, [rbp+30h]
0x140007777  add     rcx, 68h ; 'h'
0x14000777b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140007780  xor     edx, edx; pThrowInfo
0x140007782  xor     ecx, ecx; pExceptionObject
0x140007784  call    _CxxThrowException_0
```
