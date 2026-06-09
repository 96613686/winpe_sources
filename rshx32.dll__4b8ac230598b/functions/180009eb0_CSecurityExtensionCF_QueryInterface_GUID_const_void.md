# CSecurityExtensionCF::QueryInterface(_GUID const &,void * *)

- ea: `0x180009eb0`
- end: `0x180009ef8`
- name: `?QueryInterface@CSecurityExtensionCF@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CSecurityExtensionCF *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009eb0`

## pseudocode

```c
__int64 __fastcall CSecurityExtensionCF::QueryInterface(CSecurityExtensionCF *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
  {
    *a3 = this;
    ++*((_DWORD *)this + 2);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180009eb0  mov     rax, [rdx]
0x180009eb3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180009eba  jnz     short loc_180009EC9
0x180009ebc  mov     rax, [rdx+8]
0x180009ec0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009ec7  jz      short loc_180009EE2
0x180009ec9  mov     rax, [rdx]
0x180009ecc  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x180009ed3  jnz     short loc_180009EEB
0x180009ed5  mov     rax, [rdx+8]
0x180009ed9  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x180009ee0  jnz     short loc_180009EEB
0x180009ee2  mov     [r8], rcx
0x180009ee5  inc     dword ptr [rcx+8]
0x180009ee8  xor     eax, eax
0x180009eea  retn
0x180009eeb  mov     qword ptr [r8], 0
0x180009ef2  mov     eax, 80004002h
0x180009ef7  retn
```
