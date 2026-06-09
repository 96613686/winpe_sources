# CSecurityExtensionCF::Release(void)

- ea: `0x180009f50`
- end: `0x180009f7b`
- name: `?Release@CSecurityExtensionCF@@UEAAKXZ`
- size: `43`
- prototype: `__int64 __fastcall(CSecurityExtensionCF *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009f50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f6e`

## pseudocode

```c
__int64 __fastcall CSecurityExtensionCF::Release(CSecurityExtensionCF *this)
{
  bool v1; // zf
  __int64 result; // rax

  v1 = (*((_DWORD *)this + 2))-- == 1;
  result = *((unsigned int *)this + 2);
  if ( v1 )
  {
    *(_QWORD *)this = &CSecurityExtensionCF::`vftable';
    _InterlockedDecrement(&g_cRefThisDll);
    LocalFree(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009f50  sub     rsp, 28h
0x180009f54  add     dword ptr [rcx+8], 0FFFFFFFFh
0x180009f58  mov     eax, [rcx+8]
0x180009f5b  jnz     short loc_180009F76
0x180009f5d  lea     rax, ??_7CSecurityExtensionCF@@6B@; const CSecurityExtensionCF::`vftable'
0x180009f64  mov     [rcx], rax
0x180009f67  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180009f6e  call    cs:__imp_LocalFree
0x180009f74  xor     eax, eax
0x180009f76  add     rsp, 28h
0x180009f7a  retn
```
