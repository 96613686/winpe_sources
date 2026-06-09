# FllwanpGetCompartmentInformation

- ea: `0x140004d48`
- end: `0x140004efb`
- name: `FllwanpGetCompartmentInformation`
- size: `435`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e89c`
- `0x14000ef18`
- `0x140011618`
- `0x14001447c`
- `0x1400146ec`

## callees

- `0x140002e40`
- `0x140004d48`
- `0x1400050f0`
- `0x1400054c0`

## import_xrefs

- `NETIO!NmrClientDetachProviderComplete` at `0x140004edf`
- `NETIO!NmrClientDetachProviderComplete` at `0x140004edf`

## pseudocode

```c
__int64 __fastcall FllwanpGetCompartmentInformation(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // ebx
  _QWORD v10[11]; // [rsp+20h] [rbp-58h] BYREF

  memset(v10, 0, 0x50u);
  if ( (unsigned __int8)RoReferenceEx((char *)&qword_140009948 + 4) )
  {
    memset(v10, 0, 0x50u);
    LODWORD(v10[1]) = qword_140009948;
    v10[2] = &NPI_MS_NDIS_MODULEID;
    v10[9] = 0x1000000010LL;
    LODWORD(v10[3]) = 7;
    LODWORD(v10[4]) = 1;
    HIDWORD(v10[4]) = a1;
    v10[5] = a2;
    LODWORD(v10[6]) = 4;
    LODWORD(v10[7]) = 0;
    v10[8] = a4;
    v8 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)*(&NmrClientHandle + 1) + 1) + 16LL))(v10);
    if ( v8 >= 0 )
    {
      memset(v10, 0, 0x50u);
      LODWORD(v10[1]) = qword_140009948;
      v10[2] = &NPI_MS_NDIS_MODULEID;
      v10[5] = a2;
      LODWORD(v10[3]) = 7;
      LODWORD(v10[4]) = 1;
      HIDWORD(v10[4]) = a1;
      LODWORD(v10[6]) = 4;
      LODWORD(v10[7]) = 0;
      v10[8] = a3;
      v10[9] = 0x800000008LL;
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)*(&NmrClientHandle + 1) + 1) + 16LL))(v10);
      if ( v8 >= 0 )
      {
        LODWORD(v10[3]) = 0;
        v10[8] = a3 + 8;
        HIDWORD(v10[4]) = 0;
        v10[5] = a3;
        LODWORD(v10[6]) = 8;
        LODWORD(v10[7]) = 2;
        v10[9] = 4;
        v8 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)*(&NmrClientHandle + 1) + 1) + 16LL))(v10);
      }
    }
    if ( _InterlockedExchangeAdd((_DWORD *)&qword_140009948 + 1, 0xFFFFFFFE) == 3 )
      NmrClientDetachProviderComplete(*((HANDLE *)*(&NmrClientHandle + 1) + 2));
  }
  else
  {
    return (unsigned int)-1073741823;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140004d48  push    rbp
0x140004d4a  push    rbx
0x140004d4b  push    rsi
0x140004d4c  push    rdi
0x140004d4d  push    r12
0x140004d4f  push    r14
0x140004d51  mov     rbp, rsp
0x140004d54  sub     rsp, 78h
0x140004d58  mov     rdi, r8
0x140004d5b  mov     rsi, rdx
0x140004d5e  mov     r14d, ecx
0x140004d61  mov     r12d, 50h ; 'P'
0x140004d67  mov     r8d, r12d; Size
0x140004d6a  lea     rcx, [rbp+var_58]; void *
0x140004d6e  xor     edx, edx; Val
0x140004d70  mov     rbx, r9
0x140004d73  call    memset
0x140004d78  lea     rcx, qword_140009948+4
0x140004d7f  call    RoReferenceEx
0x140004d84  test    al, al
0x140004d86  jnz     short loc_140004D92
0x140004d88  mov     ebx, 0C0000001h
0x140004d8d  jmp     loc_140004EEB
0x140004d92  mov     r8, r12; Size
0x140004d95  lea     rcx, [rbp+var_58]; void *
0x140004d99  xor     edx, edx; Val
0x140004d9b  call    memset
0x140004da0  mov     eax, dword ptr cs:qword_140009948
0x140004da6  mov     [rbp+var_50], eax
0x140004da9  lea     rax, NPI_MS_NDIS_MODULEID
0x140004db0  mov     [rbp+var_48], rax
0x140004db4  mov     eax, 10h
0x140004db9  mov     dword ptr [rbp+var_10], eax
0x140004dbc  mov     dword ptr [rbp+var_10+4], eax
0x140004dbf  mov     rax, qword ptr cs:NmrClientHandle+8
0x140004dc6  mov     [rbp+var_40], 7
0x140004dcd  mov     [rbp+var_38], 1
0x140004dd4  mov     [rbp+var_34], r14d
0x140004dd8  mov     [rbp+var_30], rsi
0x140004ddc  mov     [rbp+var_28], 4
0x140004de3  mov     [rbp+var_20], 0
0x140004dea  mov     [rbp+var_18], rbx
0x140004dee  mov     rcx, [rax+8]
0x140004df2  mov     rax, [rcx+10h]
0x140004df6  lea     rcx, [rbp+var_58]
0x140004dfa  call    _guard_dispatch_icall
0x140004dff  mov     ebx, eax
0x140004e01  test    eax, eax
0x140004e03  js      loc_140004EC2
0x140004e09  mov     r8, r12; Size
0x140004e0c  lea     rcx, [rbp+var_58]; void *
0x140004e10  xor     edx, edx; Val
0x140004e12  call    memset
0x140004e17  mov     eax, dword ptr cs:qword_140009948
0x140004e1d  mov     [rbp+var_50], eax
0x140004e20  lea     rax, NPI_MS_NDIS_MODULEID
0x140004e27  mov     [rbp+var_48], rax
0x140004e2b  mov     rax, qword ptr cs:NmrClientHandle+8
0x140004e32  mov     [rbp+var_30], rsi
0x140004e36  mov     esi, 8
0x140004e3b  mov     [rbp+var_40], 7
0x140004e42  mov     [rbp+var_38], 1
0x140004e49  mov     [rbp+var_34], r14d
0x140004e4d  mov     [rbp+var_28], 4
0x140004e54  mov     [rbp+var_20], 0
0x140004e5b  mov     [rbp+var_18], rdi
0x140004e5f  mov     dword ptr [rbp+var_10], esi
0x140004e62  mov     dword ptr [rbp+var_10+4], esi
0x140004e65  mov     rcx, [rax+8]
0x140004e69  mov     rax, [rcx+10h]
0x140004e6d  lea     rcx, [rbp+var_58]
0x140004e71  call    _guard_dispatch_icall
0x140004e76  mov     ebx, eax
0x140004e78  test    eax, eax
0x140004e7a  js      short loc_140004EC2
0x140004e7c  mov     [rbp+var_40], 0
0x140004e83  lea     rax, [rdi+8]
0x140004e87  mov     [rbp+var_18], rax
0x140004e8b  mov     rax, qword ptr cs:NmrClientHandle+8
0x140004e92  mov     [rbp+var_34], 0
0x140004e99  mov     [rbp+var_30], rdi
0x140004e9d  mov     [rbp+var_28], esi
0x140004ea0  mov     [rbp+var_20], 2
0x140004ea7  mov     [rbp+var_10], 4
0x140004eaf  mov     rcx, [rax+8]
0x140004eb3  mov     rax, [rcx+10h]
0x140004eb7  lea     rcx, [rbp+var_58]
0x140004ebb  call    _guard_dispatch_icall
0x140004ec0  mov     ebx, eax
0x140004ec2  mov     eax, 0FFFFFFFEh
0x140004ec7  lock xadd dword ptr cs:qword_140009948+4, eax
0x140004ecf  cmp     eax, 3
0x140004ed2  jnz     short loc_140004EEB
0x140004ed4  mov     rcx, qword ptr cs:NmrClientHandle+8
0x140004edb  mov     rcx, [rcx+10h]; NmrBindingHandle
0x140004edf  call    cs:__imp_NmrClientDetachProviderComplete
0x140004ee6  nop     dword ptr [rax+rax+00h]
0x140004eeb  mov     eax, ebx
0x140004eed  add     rsp, 78h
0x140004ef1  pop     r14
0x140004ef3  pop     r12
0x140004ef5  pop     rdi
0x140004ef6  pop     rsi
0x140004ef7  pop     rbx
0x140004ef8  pop     rbp
0x140004ef9  retn
```
