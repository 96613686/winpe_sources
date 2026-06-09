# UmpoRpcDeleteScheme

- ea: `0x1800147b0`
- end: `0x180014808`
- name: `UmpoRpcDeleteScheme`
- size: `88`
- prototype: `DWORD __fastcall(__int64, UUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800036f0`
- `0x180004b80`
- `0x180011f4c`
- `0x1800147b0`

## pseudocode

```c
DWORD __fastcall UmpoRpcDeleteScheme(__int64 a1, UUID *a2)
{
  DWORD result; // eax

  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  result = UmpoRpcSettingAccessCheck(0, 0x14u, 0, 0x20006u);
  if ( !result )
    return UmpoDeleteScheme(a2);
  return result;
}

```

## disassembly

```asm
0x1800147b0  push    rbx
0x1800147b2  sub     rsp, 20h
0x1800147b6  mov     rbx, rdx
0x1800147b9  call    UmpoIsClientLocal
0x1800147be  test    eax, eax
0x1800147c0  jnz     short loc_1800147CD
0x1800147c2  mov     eax, 5
0x1800147c7  add     rsp, 20h
0x1800147cb  pop     rbx
0x1800147cc  retn
0x1800147cd  mov     al, cs:UmpoPowerPolicyInitialized
0x1800147d3  test    al, al
0x1800147d5  jnz     short loc_1800147E2
0x1800147d7  mov     eax, 15h
0x1800147dc  add     rsp, 20h
0x1800147e0  pop     rbx
0x1800147e1  retn
0x1800147e2  xor     r8d, r8d
0x1800147e5  mov     r9d, 20006h
0x1800147eb  xor     ecx, ecx
0x1800147ed  lea     edx, [r8+14h]
0x1800147f1  call    UmpoRpcSettingAccessCheck
0x1800147f6  test    eax, eax
0x1800147f8  jnz     short loc_180014802
0x1800147fa  mov     rcx, rbx; Uuid1
0x1800147fd  call    UmpoDeleteScheme
0x180014802  add     rsp, 20h
0x180014806  pop     rbx
0x180014807  retn
```
