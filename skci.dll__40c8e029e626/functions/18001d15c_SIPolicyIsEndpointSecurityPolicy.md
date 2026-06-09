# SIPolicyIsEndpointSecurityPolicy

- ea: `0x18001d15c`
- end: `0x18001d191`
- name: `SIPolicyIsEndpointSecurityPolicy`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047a80`
- `0x1800492f8`
- `0x180049860`

## callees

- `0x18001d15c`

## pseudocode

```c
bool __fastcall SIPolicyIsEndpointSecurityPolicy(__int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 v2; // rax

  v1 = -(__int64)(*(_DWORD *)(a1 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL;
  v2 = *(_QWORD *)(v1 + a1 + 720) - SiPolicyIDEndpointSec;
  if ( !v2 )
    v2 = *(_QWORD *)(v1 + a1 + 728) - 0x48F222A00D2EB091LL;
  return v2 == 0;
}

```

## disassembly

```asm
0x18001d15c  cmp     dword ptr [rcx+28h], 6
0x18001d160  sbb     rdx, rdx
0x18001d163  and     rdx, 0FFFFFFFFFFFFFD40h
0x18001d16a  mov     rax, [rdx+rcx+2D0h]
0x18001d172  sub     rax, cs:SiPolicyIDEndpointSec
0x18001d179  jnz     short loc_18001D18A
0x18001d17b  mov     rax, [rdx+rcx+2D8h]
0x18001d183  sub     rax, cs:qword_180037680
0x18001d18a  test    rax, rax
0x18001d18d  setz    al
0x18001d190  retn
```
