# UmpoRpcReadACValue

- ea: `0x180003070`
- end: `0x180003146`
- name: `UmpoRpcReadACValue`
- size: `214`
- prototype: `DWORD __fastcall(__int64, UUID *, UUID *, __int64, DWORD *, __int64, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180003070`
- `0x1800036f0`
- `0x180004b80`
- `0x180004e0c`

## pseudocode

```c
DWORD __fastcall UmpoRpcReadACValue(
        __int64 a1,
        UUID *a2,
        UUID *a3,
        __int64 a4,
        DWORD *a5,
        __int64 a6,
        DWORD a7,
        DWORD *a8)
{
  DWORD result; // eax

  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  result = UmpoRpcSettingAccessCheck(0, 0x10u, (__int64)a2, 0x20019u);
  if ( !result || result == 1260 )
  {
    result = UmpoRpcSettingAccessCheck(0, 0, a4, 0x20019u);
    if ( !result || result == 1260 )
    {
      *a8 = a7;
      return UmpoReadACValue(0, a2, a3, 0, a4, a5, a6, a8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003070  mov     [rsp+arg_0], rbx
0x180003075  mov     [rsp+arg_8], rsi
0x18000307a  push    rdi
0x18000307b  sub     rsp, 40h
0x18000307f  mov     rbx, r9
0x180003082  mov     rsi, r8
0x180003085  mov     rdi, rdx
0x180003088  call    UmpoIsClientLocal
0x18000308d  test    eax, eax
0x18000308f  jnz     short loc_1800030A6
0x180003091  mov     eax, 5
0x180003096  mov     rbx, [rsp+48h+arg_0]
0x18000309b  mov     rsi, [rsp+48h+arg_8]
0x1800030a0  add     rsp, 40h
0x1800030a4  pop     rdi
0x1800030a5  retn
0x1800030a6  mov     al, cs:UmpoPowerPolicyInitialized
0x1800030ac  test    al, al
0x1800030ae  jz      short loc_180003123
0x1800030b0  mov     r9d, 20019h
0x1800030b6  mov     r8, rdi
0x1800030b9  mov     edx, 10h
0x1800030be  xor     ecx, ecx
0x1800030c0  call    UmpoRpcSettingAccessCheck
0x1800030c5  test    eax, eax
0x1800030c7  jnz     short loc_18000312D
0x1800030c9  mov     r9d, 20019h
0x1800030cf  mov     r8, rbx
0x1800030d2  xor     edx, edx
0x1800030d4  xor     ecx, ecx
0x1800030d6  call    UmpoRpcSettingAccessCheck
0x1800030db  test    eax, eax
0x1800030dd  jnz     short loc_180003139
0x1800030df  mov     rcx, [rsp+48h+arg_38]
0x1800030e7  xor     r9d, r9d
0x1800030ea  mov     eax, [rsp+48h+arg_30]
0x1800030f1  mov     r8, rsi
0x1800030f4  mov     [rsp+48h+var_10], rcx
0x1800030f9  mov     rdx, rdi
0x1800030fc  mov     [rcx], eax
0x1800030fe  xor     ecx, ecx
0x180003100  mov     rax, [rsp+48h+arg_28]
0x180003105  mov     [rsp+48h+var_18], rax
0x18000310a  mov     rax, [rsp+48h+arg_20]
0x18000310f  mov     [rsp+48h+var_20], rax
0x180003114  mov     [rsp+48h+var_28], rbx
0x180003119  call    UmpoReadACValue
0x18000311e  jmp     loc_180003096
0x180003123  mov     eax, 15h
0x180003128  jmp     loc_180003096
0x18000312d  cmp     eax, 4ECh
0x180003132  jz      short loc_1800030C9
0x180003134  jmp     loc_180003096
0x180003139  cmp     eax, 4ECh
0x18000313e  jnz     loc_180003096
0x180003144  jmp     short loc_1800030DF
```
