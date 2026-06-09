# CWMDSPComBase::NDAddRef(void)

- ea: `0x180012310`
- end: `0x180012322`
- name: `?NDAddRef@CWMDSPComBase@@UEAAKXZ`
- size: `18`
- prototype: `unsigned int __fastcall(CWMDSPComBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CWMDSPComBase::NDAddRef(CWMDSPComBase *this)
{
  __int64 result; // rax
  unsigned int v2; // ecx

  result = 1;
  _InterlockedAdd((volatile signed __int32 *)this + 4, 1u);
  v2 = *((_DWORD *)this + 4);
  if ( v2 > 1 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x180012310  mov     eax, 1
0x180012315  lock add [rcx+10h], eax
0x180012319  mov     ecx, [rcx+10h]
0x18001231c  cmp     ecx, eax
0x18001231e  cmova   eax, ecx
0x180012321  retn
```
