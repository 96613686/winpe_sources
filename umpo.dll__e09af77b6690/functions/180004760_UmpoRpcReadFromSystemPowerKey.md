# UmpoRpcReadFromSystemPowerKey

- ea: `0x180004760`
- end: `0x180004825`
- name: `UmpoRpcReadFromSystemPowerKey`
- size: `197`
- prototype: `__int64 __fastcall(__int64, UUID *, UUID *, __int64, UUID *, char, unsigned int, DWORD *, unsigned int, BYTE *, DWORD, LPDWORD, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180004760`
- `0x180004b80`
- `0x18000681c`

## pseudocode

```c
__int64 __fastcall UmpoRpcReadFromSystemPowerKey(
        __int64 a1,
        UUID *a2,
        UUID *a3,
        __int64 a4,
        UUID *a5,
        char a6,
        unsigned int a7,
        DWORD *a8,
        unsigned int a9,
        BYTE *a10,
        DWORD a11,
        LPDWORD a12,
        int *a13)
{
  if ( !UmpoIsClientLocal() )
    return 5;
  if ( !UmpoPowerPolicyInitialized )
    return 21;
  *a12 = a11;
  return UmpoReadFromSystemPowerKey(a2, a3, a4, a5, a6, a7, a8, a9, a10, a12, a13);
}

```

## disassembly

```asm
0x180004760  mov     [rsp+arg_0], rbx
0x180004765  mov     [rsp+arg_8], rsi
0x18000476a  push    rdi
0x18000476b  sub     rsp, 60h
0x18000476f  mov     rbx, r9
0x180004772  mov     rdi, r8
0x180004775  mov     rsi, rdx
0x180004778  call    UmpoIsClientLocal
0x18000477d  test    eax, eax
0x18000477f  jz      loc_180004817
0x180004785  mov     al, cs:UmpoPowerPolicyInitialized
0x18000478b  test    al, al
0x18000478d  jz      loc_18000481E
0x180004793  mov     rcx, [rsp+68h+arg_58]
0x18000479b  mov     r8, rbx
0x18000479e  mov     eax, [rsp+68h+arg_50]
0x1800047a5  mov     rdx, rdi; Uuid1
0x1800047a8  mov     r9, [rsp+68h+arg_20]
0x1800047b0  mov     [rcx], eax
0x1800047b2  mov     rax, [rsp+68h+arg_60]
0x1800047ba  mov     [rsp+68h+var_18], rax; __int64
0x1800047bf  mov     rax, [rsp+68h+arg_48]
0x1800047c7  mov     [rsp+68h+var_20], rcx; LPDWORD
0x1800047cc  mov     rcx, rsi; __int64
0x1800047cf  mov     [rsp+68h+var_28], rax; __int64
0x1800047d4  mov     eax, [rsp+68h+arg_40]
0x1800047db  mov     [rsp+68h+var_30], eax; int
0x1800047df  mov     rax, [rsp+68h+arg_38]
0x1800047e7  mov     [rsp+68h+var_38], rax; __int64
0x1800047ec  mov     eax, [rsp+68h+arg_30]
0x1800047f3  mov     [rsp+68h+var_40], eax; int
0x1800047f7  mov     al, [rsp+68h+arg_28]
0x1800047fe  mov     [rsp+68h+var_48], al; char
0x180004802  call    UmpoReadFromSystemPowerKey
0x180004807  mov     rbx, [rsp+68h+arg_0]
0x18000480c  mov     rsi, [rsp+68h+arg_8]
0x180004811  add     rsp, 60h
0x180004815  pop     rdi
0x180004816  retn
0x180004817  mov     eax, 5
0x18000481c  jmp     short loc_180004807
0x18000481e  mov     eax, 15h
0x180004823  jmp     short loc_180004807
```
