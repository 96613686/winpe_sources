# UmpoRpcReadDCValue

- ea: `0x180002e90`
- end: `0x180002f76`
- name: `UmpoRpcReadDCValue`
- size: `230`
- prototype: `DWORD __fastcall(__int64, UUID *, UUID *, __int64, DWORD *, __int64, DWORD, DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002e90`
- `0x1800036f0`
- `0x180004b80`
- `0x1800059c0`

## pseudocode

```c
DWORD __fastcall UmpoRpcReadDCValue(
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
    result = UmpoRpcSettingAccessCheck(0, 1u, a4, 0x20019u);
    if ( !result || result == 1260 )
    {
      *a8 = a7;
      return UmpoInternalReadxCValue(0, a2, a3, 0, a4, 0, a5, a6, a8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  mov     [rsp+arg_8], rsi
0x180002e9a  push    rdi
0x180002e9b  sub     rsp, 50h
0x180002e9f  mov     rbx, r9
0x180002ea2  mov     rsi, r8
0x180002ea5  mov     rdi, rdx
0x180002ea8  call    UmpoIsClientLocal
0x180002ead  test    eax, eax
0x180002eaf  jz      loc_180002F5A
0x180002eb5  mov     al, cs:UmpoPowerPolicyInitialized
0x180002ebb  test    al, al
0x180002ebd  jz      loc_180002F53
0x180002ec3  mov     r9d, 20019h
0x180002ec9  mov     r8, rdi
0x180002ecc  mov     edx, 10h
0x180002ed1  xor     ecx, ecx
0x180002ed3  call    UmpoRpcSettingAccessCheck
0x180002ed8  test    eax, eax
0x180002eda  jnz     loc_180002F61
0x180002ee0  mov     r9d, 20019h
0x180002ee6  mov     r8, rbx
0x180002ee9  mov     edx, 1
0x180002eee  xor     ecx, ecx
0x180002ef0  call    UmpoRpcSettingAccessCheck
0x180002ef5  test    eax, eax
0x180002ef7  jnz     short loc_180002F6D
0x180002ef9  mov     rcx, [rsp+58h+arg_38]
0x180002f01  xor     r9d, r9d
0x180002f04  mov     eax, [rsp+58h+arg_30]
0x180002f0b  mov     r8, rsi
0x180002f0e  mov     [rsp+58h+var_18], rcx
0x180002f13  mov     rdx, rdi
0x180002f16  mov     [rcx], eax
0x180002f18  xor     ecx, ecx
0x180002f1a  mov     rax, [rsp+58h+arg_28]
0x180002f22  mov     [rsp+58h+var_20], rax
0x180002f27  mov     rax, [rsp+58h+arg_20]
0x180002f2f  mov     [rsp+58h+var_28], rax
0x180002f34  mov     [rsp+58h+var_30], 0
0x180002f39  mov     [rsp+58h+var_38], rbx
0x180002f3e  call    UmpoInternalReadxCValue
0x180002f43  mov     rbx, [rsp+58h+arg_0]
0x180002f48  mov     rsi, [rsp+58h+arg_8]
0x180002f4d  add     rsp, 50h
0x180002f51  pop     rdi
0x180002f52  retn
0x180002f53  mov     eax, 15h
0x180002f58  jmp     short loc_180002F43
0x180002f5a  mov     eax, 5
0x180002f5f  jmp     short loc_180002F43
0x180002f61  cmp     eax, 4ECh
0x180002f66  jnz     short loc_180002F43
0x180002f68  jmp     loc_180002EE0
0x180002f6d  cmp     eax, 4ECh
0x180002f72  jnz     short loc_180002F43
0x180002f74  jmp     short loc_180002EF9
```
