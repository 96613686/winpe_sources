# GetProcAddressForCaller

- ea: `0x14001a254`
- end: `0x14001a30d`
- name: `GetProcAddressForCaller`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140017684`

## callees

- `0x14001a254`
- `0x14001cabc`
- `0x14001cae0`

## import_xrefs

- `ntdll!RtlInitString` at `0x14001a289`
- `ntdll!RtlInitString` at `0x14001a289`
- `ntdll!LdrGetProcedureAddressForCaller` at `0x14001a2c0`
- `ntdll!LdrGetProcedureAddressForCaller` at `0x14001a2c0`

## pseudocode

```c
__int64 __fastcall GetProcAddressForCaller(__int64 a1, const char *a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // r8
  struct _STRING *v10; // rdx
  int ProcedureAddressForCaller; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v16; // rax
  struct _STRING v17; // [rsp+30h] [rbp-18h] BYREF
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v18 = 0;
  v17 = 0;
  if ( (unsigned __int64)a2 <= 0xFFFF )
  {
    v8 = BasepMapModuleHandle(a1, a2, (unsigned int)a2);
    v10 = 0;
  }
  else
  {
    RtlInitString(&v17, a2);
    v8 = BasepMapModuleHandle(a1, v6, v7);
    v9 = 0;
    v10 = &v17;
  }
  ProcedureAddressForCaller = LdrGetProcedureAddressForCaller(
                                v8,
                                v10,
                                v9,
                                &v18,
                                0,
                                a3,
                                *(_QWORD *)&v17.Length,
                                v17.Buffer);
  if ( ProcedureAddressForCaller < 0 )
  {
    v14 = (unsigned int)ProcedureAddressForCaller;
LABEL_6:
    BaseSetLastNTError(v14);
    return 0;
  }
  v16 = BasepMapModuleHandle(a1, v12, v13);
  if ( v18 == v16 )
  {
    v14 = (unsigned int)((unsigned __int64)a2 > 0xFFFF) - 1073741512;
    goto LABEL_6;
  }
  return v18;
}

```

## disassembly

```asm
0x14001a254  mov     rax, rsp
0x14001a257  mov     [rax+8], rbx
0x14001a25b  mov     [rax+18h], rsi
0x14001a25f  push    rdi
0x14001a260  sub     rsp, 40h
0x14001a264  mov     qword ptr [rax+10h], 0
0x14001a26c  xorps   xmm0, xmm0
0x14001a26f  mov     rsi, r8
0x14001a272  mov     rbx, rdx
0x14001a275  mov     rdi, rcx
0x14001a278  movups  xmmword ptr [rax-18h], xmm0
0x14001a27c  cmp     rdx, 0FFFFh
0x14001a283  jbe     short loc_14001A2A1
0x14001a285  lea     rcx, [rax-18h]; DestinationString
0x14001a289  call    cs:__imp_RtlInitString
0x14001a28f  mov     rcx, rdi
0x14001a292  call    BasepMapModuleHandle
0x14001a297  xor     r8d, r8d
0x14001a29a  lea     rdx, [rsp+48h+var_18]
0x14001a29f  jmp     short loc_14001A2AB
0x14001a2a1  mov     r8d, ebx
0x14001a2a4  call    BasepMapModuleHandle
0x14001a2a9  xor     edx, edx
0x14001a2ab  mov     [rsp+48h+var_20], rsi
0x14001a2b0  lea     r9, [rsp+48h+arg_8]
0x14001a2b5  mov     rcx, rax
0x14001a2b8  mov     [rsp+48h+var_28], 0
0x14001a2c0  call    cs:__imp_LdrGetProcedureAddressForCaller
0x14001a2c6  test    eax, eax
0x14001a2c8  jns     short loc_14001A2D5
0x14001a2ca  mov     ecx, eax
0x14001a2cc  call    BaseSetLastNTError
0x14001a2d1  xor     eax, eax
0x14001a2d3  jmp     short loc_14001A2FD
0x14001a2d5  mov     rcx, rdi
0x14001a2d8  call    BasepMapModuleHandle
0x14001a2dd  cmp     [rsp+48h+arg_8], rax
0x14001a2e2  jnz     short loc_14001A2F8
0x14001a2e4  xor     ecx, ecx
0x14001a2e6  cmp     rbx, 0FFFFh
0x14001a2ed  setnbe  cl
0x14001a2f0  add     ecx, 0C0000138h
0x14001a2f6  jmp     short loc_14001A2CC
0x14001a2f8  mov     rax, [rsp+48h+arg_8]
0x14001a2fd  mov     rbx, [rsp+48h+arg_0]
0x14001a302  mov     rsi, [rsp+48h+arg_10]
0x14001a307  add     rsp, 40h
0x14001a30b  pop     rdi
0x14001a30c  retn
```
