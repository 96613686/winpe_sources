# ATL::AtlThrowImpl(long)

- ea: `0x180008c94`
- end: `0x180008cb3`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int, __int64, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008358`
- `0x180008624`
- `0x180008b28`
- `0x180008b5c`
- `0x180009c8c`
- `0x18000a348`
- `0x18000a50c`

## callees

- `0x18000c1d4`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // eax

  v3 = -1073741795;
  if ( a1 == -2147024882 )
    v3 = -1073741801;
  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)v3, -1073741801, a3);
  JUMPOUT(0x180008CB2LL);
}

```

## disassembly

```asm
0x180008c94  sub     rsp, 28h
0x180008c98  cmp     ecx, 8007000Eh
0x180008c9e  mov     eax, 0C000001Dh
0x180008ca3  mov     edx, 0C0000017h; int
0x180008ca8  cmovz   eax, edx
0x180008cab  mov     ecx, eax; this
0x180008cad  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
