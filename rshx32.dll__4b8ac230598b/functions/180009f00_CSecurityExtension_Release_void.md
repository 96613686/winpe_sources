# CSecurityExtension::Release(void)

- ea: `0x180009f00`
- end: `0x180009f2a`
- name: `?Release@CSecurityExtension@@UEAAKXZ`
- size: `42`
- prototype: `__int64 __fastcall(CSecurityExtension *hMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009f30`
- `0x180009f40`

## callees

- `0x180008cd8`
- `0x180009f00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f17`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009f17`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::Release(CSecurityExtension *hMem)
{
  if ( (*((_DWORD *)hMem + 6))-- != 1 )
    return *((unsigned int *)hMem + 6);
  CSecurityExtension::~CSecurityExtension(hMem);
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180009f00  push    rbx
0x180009f02  sub     rsp, 20h
0x180009f06  add     dword ptr [rcx+18h], 0FFFFFFFFh
0x180009f0a  mov     rbx, rcx
0x180009f0d  jnz     short loc_180009F21
0x180009f0f  call    ??1CSecurityExtension@@AEAA@XZ; CSecurityExtension::~CSecurityExtension(void)
0x180009f14  mov     rcx, rbx; hMem
0x180009f17  call    cs:__imp_LocalFree
0x180009f1d  xor     eax, eax
0x180009f1f  jmp     short loc_180009F24
0x180009f21  mov     eax, [rcx+18h]
0x180009f24  add     rsp, 20h
0x180009f28  pop     rbx
0x180009f29  retn
```
