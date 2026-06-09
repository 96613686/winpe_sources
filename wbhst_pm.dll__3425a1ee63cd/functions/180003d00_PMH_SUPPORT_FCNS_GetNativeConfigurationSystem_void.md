# PMH_SUPPORT_FCNS::GetNativeConfigurationSystem(void * *)

- ea: `0x180003d00`
- end: `0x180003d1a`
- name: `?GetNativeConfigurationSystem@PMH_SUPPORT_FCNS@@UEAAJPEAPEAX@Z`
- size: `26`
- prototype: `__int64 __fastcall(PMH_SUPPORT_FCNS *__hidden this, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003d00`

## pseudocode

```c
__int64 __fastcall PMH_SUPPORT_FCNS::GetNativeConfigurationSystem(PMH_SUPPORT_FCNS *this, void **a2)
{
  void *v2; // rax

  if ( !a2 )
    return 2147942487LL;
  v2 = (void *)*((_QWORD *)this + 5);
  if ( !v2 )
    return 2147942487LL;
  *a2 = v2;
  return 0;
}

```

## disassembly

```asm
0x180003d00  test    rdx, rdx
0x180003d03  jz      short loc_180003D14
0x180003d05  mov     rax, [rcx+28h]
0x180003d09  test    rax, rax
0x180003d0c  jz      short loc_180003D14
0x180003d0e  mov     [rdx], rax
0x180003d11  xor     eax, eax
0x180003d13  retn
0x180003d14  mov     eax, 80070057h
0x180003d19  retn
```
