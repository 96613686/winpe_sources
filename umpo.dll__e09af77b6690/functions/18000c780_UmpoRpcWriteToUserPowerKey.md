# UmpoRpcWriteToUserPowerKey

- ea: `0x18000c780`
- end: `0x18000c885`
- name: `UmpoRpcWriteToUserPowerKey`
- size: `261`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, UUID *Uuid1, __int64, __int64, unsigned int, int, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800036f0`
- `0x180004b80`
- `0x18000b7b0`
- `0x18000c780`
- `0x18000c88c`
- `0x18000d2f4`

## pseudocode

```c
__int64 __fastcall UmpoRpcWriteToUserPowerKey(
        RPC_BINDING_HANDLE Binding,
        UUID *Uuid1,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        unsigned int a8)
{
  __int64 v11; // rcx
  unsigned int v12; // ebx

  if ( (unsigned int)UmpoIsClientLocal() )
  {
    if ( UmpoPowerPolicyInitialized )
    {
      v12 = UmpoInternalSanitizeWrite(v11, a5, a7, a8);
      if ( !v12 && (a5 > 1 || (v12 = UmpoRpcSettingAccessCheck(0, 16, Uuid1, 131078)) == 0) )
      {
        v12 = UmpoRpcSettingAccessCheck(0, a5, a4, 131078);
        if ( !v12 )
        {
          v12 = UmpoWriteToUserPowerKey(Uuid1, a6, a7, a8);
          if ( !v12 )
            UmpoTracePowerSettingWrite(Binding, a5, 0, a7, a8);
        }
      }
    }
    else
    {
      return 21;
    }
  }
  else
  {
    return 5;
  }
  return v12;
}

```

## disassembly

```asm
0x18000c780  push    rbx
0x18000c782  push    rbp
0x18000c783  push    rsi
0x18000c784  push    rdi
0x18000c785  push    r12
0x18000c787  push    r13
0x18000c789  push    r14
0x18000c78b  push    r15
0x18000c78d  sub     rsp, 48h
0x18000c791  mov     r14, r9
0x18000c794  mov     r12, r8
0x18000c797  mov     r15, rdx
0x18000c79a  mov     r13, rcx
0x18000c79d  call    UmpoIsClientLocal
0x18000c7a2  test    eax, eax
0x18000c7a4  jnz     short loc_18000C7AE
0x18000c7a6  lea     ebx, [rax+5]
0x18000c7a9  jmp     loc_18000C872
0x18000c7ae  mov     al, cs:UmpoPowerPolicyInitialized
0x18000c7b4  test    al, al
0x18000c7b6  jnz     short loc_18000C7C2
0x18000c7b8  mov     ebx, 15h
0x18000c7bd  jmp     loc_18000C872
0x18000c7c2  mov     rbp, [rsp+88h+arg_30]
0x18000c7ca  mov     esi, [rsp+88h+arg_38]
0x18000c7d1  mov     r8, rbp
0x18000c7d4  mov     edi, [rsp+88h+arg_20]
0x18000c7db  mov     r9d, esi
0x18000c7de  mov     edx, edi
0x18000c7e0  call    UmpoInternalSanitizeWrite
0x18000c7e5  mov     ebx, eax
0x18000c7e7  test    eax, eax
0x18000c7e9  jnz     loc_18000C872
0x18000c7ef  cmp     edi, 1
0x18000c7f2  ja      short loc_18000C80D
0x18000c7f4  mov     r9d, 20006h
0x18000c7fa  lea     edx, [rax+10h]
0x18000c7fd  mov     r8, r15
0x18000c800  xor     ecx, ecx
0x18000c802  call    UmpoRpcSettingAccessCheck
0x18000c807  mov     ebx, eax
0x18000c809  test    eax, eax
0x18000c80b  jnz     short loc_18000C872
0x18000c80d  mov     r9d, 20006h
0x18000c813  mov     r8, r14
0x18000c816  mov     edx, edi
0x18000c818  xor     ecx, ecx
0x18000c81a  call    UmpoRpcSettingAccessCheck
0x18000c81f  mov     ebx, eax
0x18000c821  test    eax, eax
0x18000c823  jnz     short loc_18000C872
0x18000c825  mov     eax, [rsp+88h+arg_28]
0x18000c82c  mov     r9d, edi
0x18000c82f  mov     dword ptr [rsp+88h+var_58], esi; int
0x18000c833  mov     r8, r14
0x18000c836  mov     qword ptr [rsp+88h+var_60], rbp; __int64
0x18000c83b  mov     rdx, r12
0x18000c83e  mov     rcx, r15; Uuid1
0x18000c841  mov     [rsp+88h+var_68], eax; int
0x18000c845  call    UmpoWriteToUserPowerKey
0x18000c84a  mov     ebx, eax
0x18000c84c  test    eax, eax
0x18000c84e  jnz     short loc_18000C872
0x18000c850  mov     [rsp+88h+var_50], esi; int
0x18000c854  mov     r9, r14
0x18000c857  mov     [rsp+88h+var_58], rbp; __int64
0x18000c85c  mov     r8, r12
0x18000c85f  mov     [rsp+88h+var_60], al; char
0x18000c863  mov     rdx, r15
0x18000c866  mov     rcx, r13; Binding
0x18000c869  mov     [rsp+88h+var_68], edi; int
0x18000c86d  call    UmpoTracePowerSettingWrite
0x18000c872  mov     eax, ebx
0x18000c874  add     rsp, 48h
0x18000c878  pop     r15
0x18000c87a  pop     r14
0x18000c87c  pop     r13
0x18000c87e  pop     r12
0x18000c880  pop     rdi
0x18000c881  pop     rsi
0x18000c882  pop     rbp
0x18000c883  pop     rbx
0x18000c884  retn
```
