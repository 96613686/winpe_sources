# CConnectedAccounts::Create(ushort const *,IPropertyStore * *)

- ea: `0x18000dd30`
- end: `0x18000dd3d`
- name: `?Create@CConnectedAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(CConnectedAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CConnectedAccounts::Create(
        CConnectedAccounts *this,
        const unsigned __int16 *a2,
        struct IPropertyStore **a3)
{
  *a3 = 0;
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000dd30  mov     qword ptr [r8], 0
0x18000dd37  mov     eax, 80004001h
0x18000dd3c  retn
```
