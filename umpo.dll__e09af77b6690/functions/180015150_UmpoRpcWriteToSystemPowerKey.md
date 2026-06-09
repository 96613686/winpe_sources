# UmpoRpcWriteToSystemPowerKey

- ea: `0x180015150`
- end: `0x180015235`
- name: `UmpoRpcWriteToSystemPowerKey`
- size: `229`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, __int64, __int64, __int64, __int64, int, int, int, _WORD *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180004b80`
- `0x18000c88c`
- `0x18000cb4c`
- `0x18000d2f4`
- `0x180015150`

## pseudocode

```c
__int64 __fastcall UmpoRpcWriteToSystemPowerKey(
        RPC_BINDING_HANDLE Binding,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        _WORD *a9,
        int a10)
{
  __int64 v14; // rcx
  unsigned int v15; // ebx

  if ( UmpoIsClientLocal() )
  {
    if ( UmpoPowerPolicyInitialized )
    {
      v15 = UmpoInternalSanitizeWrite(v14, a6, a9, a10);
      if ( !v15 )
      {
        v15 = UmpoWriteToSystemPowerKey(a2, a3, a4, a5, a6, a7, a8, a9, a10);
        if ( !v15 )
          UmpoTracePowerSettingWrite(Binding, a6, 1, (__int64)a9, a10);
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
  return v15;
}

```

## disassembly

```asm
0x180015150  push    rbx
0x180015152  push    rbp
0x180015153  push    rsi
0x180015154  push    rdi
0x180015155  push    r12
0x180015157  push    r13
0x180015159  push    r14
0x18001515b  push    r15
0x18001515d  sub     rsp, 58h
0x180015161  mov     r13, r9
0x180015164  mov     r14, r8
0x180015167  mov     r15, rdx
0x18001516a  mov     r12, rcx
0x18001516d  call    UmpoIsClientLocal
0x180015172  test    eax, eax
0x180015174  jnz     short loc_18001517E
0x180015176  lea     ebx, [rax+5]
0x180015179  jmp     loc_180015222
0x18001517e  mov     al, cs:UmpoPowerPolicyInitialized
0x180015184  test    al, al
0x180015186  jnz     short loc_180015192
0x180015188  mov     ebx, 15h
0x18001518d  jmp     loc_180015222
0x180015192  mov     rsi, [rsp+98h+arg_40]
0x18001519a  mov     edi, [rsp+98h+arg_48]
0x1800151a1  mov     r8, rsi
0x1800151a4  mov     ebp, [rsp+98h+arg_28]
0x1800151ab  mov     r9d, edi
0x1800151ae  mov     edx, ebp
0x1800151b0  call    UmpoInternalSanitizeWrite
0x1800151b5  mov     ebx, eax
0x1800151b7  test    eax, eax
0x1800151b9  jnz     short loc_180015222
0x1800151bb  mov     eax, [rsp+98h+arg_38]
0x1800151c2  mov     r8, r13
0x1800151c5  mov     r9, [rsp+98h+arg_20]
0x1800151cd  mov     rdx, r14
0x1800151d0  mov     [rsp+98h+var_58], edi
0x1800151d4  mov     rcx, r15
0x1800151d7  mov     qword ptr [rsp+98h+var_60], rsi
0x1800151dc  mov     dword ptr [rsp+98h+var_68], eax
0x1800151e0  mov     eax, [rsp+98h+arg_30]
0x1800151e7  mov     dword ptr [rsp+98h+var_70], eax
0x1800151eb  mov     [rsp+98h+var_78], ebp
0x1800151ef  call    UmpoWriteToSystemPowerKey
0x1800151f4  mov     ebx, eax
0x1800151f6  test    eax, eax
0x1800151f8  jnz     short loc_180015222
0x1800151fa  mov     r9, [rsp+98h+arg_20]
0x180015202  mov     r8, r14
0x180015205  mov     [rsp+98h+var_60], edi; int
0x180015209  mov     rdx, r15
0x18001520c  mov     [rsp+98h+var_68], rsi; __int64
0x180015211  mov     rcx, r12; Binding
0x180015214  mov     [rsp+98h+var_70], 1; char
0x180015219  mov     [rsp+98h+var_78], ebp; int
0x18001521d  call    UmpoTracePowerSettingWrite
0x180015222  mov     eax, ebx
0x180015224  add     rsp, 58h
0x180015228  pop     r15
0x18001522a  pop     r14
0x18001522c  pop     r13
0x18001522e  pop     r12
0x180015230  pop     rdi
0x180015231  pop     rsi
0x180015232  pop     rbp
0x180015233  pop     rbx
0x180015234  retn
```
