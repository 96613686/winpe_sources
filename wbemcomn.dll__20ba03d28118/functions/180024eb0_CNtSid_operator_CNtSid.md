# CNtSid::operator==(CNtSid &)

- ea: `0x180024eb0`
- end: `0x180024efa`
- name: `??8CNtSid@@QEAAHAEAV0@@Z`
- size: `74`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001f360`

## callees

- `0x180024eb0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180024ed4`
- `ntdll!RtlEqualSid` at `0x180024ed4`

## pseudocode

```c
__int64 __fastcall CNtSid::operator==(__int64 a1, __int64 a2)
{
  void *v2; // rdx

  if ( !*(_QWORD *)a1 && !*(_QWORD *)a2 && *(_DWORD *)(a1 + 8) == *(_DWORD *)(a2 + 8) )
    return 1;
  if ( *(_DWORD *)(a1 + 8) == *(_DWORD *)(a2 + 8) )
  {
    if ( *(_QWORD *)a1 )
    {
      v2 = *(void **)a2;
      if ( v2 )
        return RtlEqualSid(*(PSID *)a1, v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024eb0  sub     rsp, 28h
0x180024eb4  xor     r8d, r8d
0x180024eb7  cmp     [rcx], r8
0x180024eba  jz      short loc_180024EE6
0x180024ebc  mov     eax, [rdx+8]
0x180024ebf  cmp     [rcx+8], eax
0x180024ec2  jnz     short loc_180024EE2
0x180024ec4  cmp     [rcx], r8
0x180024ec7  jz      short loc_180024EE2
0x180024ec9  mov     rdx, [rdx]; Sid2
0x180024ecc  test    rdx, rdx
0x180024ecf  jz      short loc_180024EE2
0x180024ed1  mov     rcx, [rcx]; Sid1
0x180024ed4  call    cs:__imp_RtlEqualSid
0x180024eda  movzx   eax, al
0x180024edd  add     rsp, 28h
0x180024ee1  retn
0x180024ee2  xor     eax, eax
0x180024ee4  jmp     short loc_180024EDD
0x180024ee6  cmp     [rdx], r8
0x180024ee9  jnz     short loc_180024EBC
0x180024eeb  mov     eax, [rdx+8]
0x180024eee  cmp     [rcx+8], eax
0x180024ef1  jnz     short loc_180024EBC
0x180024ef3  mov     eax, 1
0x180024ef8  jmp     short loc_180024EDD
```
