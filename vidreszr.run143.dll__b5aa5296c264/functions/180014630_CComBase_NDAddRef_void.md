# CComBase::NDAddRef(void)

- ea: `0x180014630`
- end: `0x180014642`
- name: `?NDAddRef@CComBase@@UEAAKXZ`
- size: `18`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CComBase::NDAddRef(CComBase *this)
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
0x180014630  mov     eax, 1
0x180014635  lock add [rcx+10h], eax
0x180014639  mov     ecx, [rcx+10h]
0x18001463c  cmp     ecx, eax
0x18001463e  cmova   eax, ecx
0x180014641  retn
```
