# ATL::CSid::Clear(void)

- ea: `0x140009680`
- end: `0x1400096be`
- name: `?Clear@CSid@ATL@@AEAAXXZ`
- size: `62`
- prototype: `void __fastcall(ATL::CSid *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400097f8`
- `0x14000b018`

## callees

- `0x140009724`

## pseudocode

```c
void __fastcall ATL::CSid::Clear(ATL::CSid *this)
{
  *((_DWORD *)this + 20) = 7;
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 88);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 96);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104);
  ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 112);
  *((_BYTE *)this + 76) = 0;
}

```

## disassembly

```asm
0x140009680  push    rbx
0x140009682  sub     rsp, 20h
0x140009686  mov     rbx, rcx
0x140009689  mov     dword ptr [rcx+50h], 7
0x140009690  add     rcx, 58h ; 'X'
0x140009694  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140009699  lea     rcx, [rbx+60h]
0x14000969d  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400096a2  lea     rcx, [rbx+68h]
0x1400096a6  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400096ab  lea     rcx, [rbx+70h]
0x1400096af  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400096b4  mov     byte ptr [rbx+4Ch], 0
0x1400096b8  add     rsp, 20h
0x1400096bc  pop     rbx
0x1400096bd  retn
```
