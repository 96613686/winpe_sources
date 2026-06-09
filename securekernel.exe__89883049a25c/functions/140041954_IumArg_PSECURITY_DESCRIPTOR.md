# IumArg_PSECURITY_DESCRIPTOR

- ea: `0x140041954`
- end: `0x140041b7d`
- name: `IumArg_PSECURITY_DESCRIPTOR`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140040f54`

## callees

- `0x14000f0f0`
- `0x1400119c4`
- `0x140037e68`
- `0x140041234`
- `0x140041954`
- `0x140044378`
- `0x14004439c`
- `0x1400d9528`
- `0x1400d9604`
- `0x1400f38f0`
- `0x1400fc5b8`

## pseudocode

```c
__int64 __fastcall IumArg_PSECURITY_DESCRIPTOR(
        int a1,
        unsigned int a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        void *Src,
        int *a9,
        __int64 a10,
        char a11,
        char a12)
{
  void *v14; // rbx
  _BYTE *StackBase; // r14
  char v16; // r14
  __int64 v17; // rsi
  void *v18; // rdi
  unsigned int v19; // eax
  __int64 Pool; // rax
  __int64 v21; // r9
  unsigned int v22; // edi
  ULONG v23; // eax
  __int64 v24; // r9
  __int64 v25; // [rsp+30h] [rbp-78h]

  if ( (a2 & 0x20000000) != 0 )
    return 3221225474LL;
  v14 = 0;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( a1 != 2 )
  {
    LOBYTE(v25) = a7;
    v22 = IumArg_GENERIC(a1, a2, a3, a4, a5, a6, v25, Src, a9, a10, a11);
    goto LABEL_23;
  }
  v16 = StackBase[96];
  if ( !v16 )
    RtlCopyVolatileMemory(a3, Src, (unsigned int)*a9);
  if ( a12 )
  {
    if ( v16 == 1 )
      RtlCopyToUserFromUser(a3, Src, (unsigned int)*a9);
    goto LABEL_21;
  }
  LODWORD(v17) = *a9;
  if ( !v16 )
  {
    v18 = a3;
LABEL_14:
    if ( !RtlValidRelativeSecurityDescriptor(v18, v17, (SECURITY_INFORMATION)a3) )
      SkeBugCheckEx(0x29u, 0x44536149u, (ULONG_PTR)v18, (unsigned int)v17, 0);
    v23 = RtlLengthSecurityDescriptor(v18);
    if ( !v23 || v23 > (unsigned int)v17 )
      SkeBugCheckEx(0x29u, 0x44536149u, (ULONG_PTR)v18, (unsigned int)v17, v23);
    if ( v16 == 1 )
    {
      LOBYTE(v24) = 1;
      SkCopyToUntrusted(a3, v18, v23, v24);
    }
LABEL_21:
    v22 = 0;
    goto LABEL_23;
  }
  v19 = 131226;
  if ( (unsigned int)v17 < 0x2009A )
    v19 = *a9;
  v17 = v19;
  Pool = SkAllocatePool(1, v19);
  v14 = (void *)Pool;
  if ( Pool )
  {
    LOBYTE(v21) = 1;
    SkCopyFromUntrusted(Pool, Src, v17, v21);
    v18 = v14;
    goto LABEL_14;
  }
  v22 = -1073741670;
LABEL_23:
  if ( v14 )
    SkFreePool(1, v14);
  return v22;
}

```

## disassembly

```asm
0x140041954  push    rbx
0x140041956  push    rsi
0x140041957  push    rdi
0x140041958  push    r14
0x14004195a  push    r15
0x14004195c  sub     rsp, 80h
0x140041963  mov     r15, r8
0x140041966  bt      edx, 1Dh
0x14004196a  jnb     short loc_140041976
0x14004196c  mov     eax, 0C0000002h
0x140041971  jmp     loc_140041B31
0x140041976  xor     ebx, ebx
0x140041978  mov     [rsp+0A8h+var_38], rbx
0x14004197d  mov     r14, gs:8
0x140041986  cmp     ecx, 2
0x140041989  jnz     loc_140041AB4
0x14004198f  mov     r14b, [r14+60h]
0x140041993  test    r14b, r14b
0x140041996  jnz     short loc_1400419B3
0x140041998  mov     rax, [rsp+0A8h+arg_40]
0x1400419a0  mov     r8d, [rax]; Size
0x1400419a3  mov     rdx, [rsp+0A8h+Src]; Src
0x1400419ab  mov     rcx, r15; void *
0x1400419ae  call    RtlCopyVolatileMemory
0x1400419b3  cmp     [rsp+0A8h+arg_58], bl
0x1400419ba  jnz     loc_140041A81
0x1400419c0  mov     rax, [rsp+0A8h+arg_40]
0x1400419c8  mov     esi, [rax]
0x1400419ca  test    r14b, r14b
0x1400419cd  jnz     short loc_1400419D4
0x1400419cf  mov     rdi, r15
0x1400419d2  jmp     short loc_140041A23
0x1400419d4  mov     eax, 2009Ah
0x1400419d9  cmp     esi, eax
0x1400419db  cmovb   eax, esi
0x1400419de  mov     esi, eax
0x1400419e0  mov     r8d, 44536149h
0x1400419e6  mov     edx, eax
0x1400419e8  mov     ecx, 1
0x1400419ed  call    SkAllocatePool
0x1400419f2  mov     rbx, rax
0x1400419f5  mov     [rsp+0A8h+var_38], rax
0x1400419fa  test    rax, rax
0x1400419fd  jnz     short loc_140041A09
0x1400419ff  mov     edi, 0C000009Ah
0x140041a04  jmp     loc_140041B1D
0x140041a09  mov     r9b, 1
0x140041a0c  mov     r8, rsi
0x140041a0f  mov     rdx, [rsp+0A8h+Src]
0x140041a17  mov     rcx, rbx
0x140041a1a  call    SkCopyFromUntrusted
0x140041a1f  nop
0x140041a20  mov     rdi, rbx
0x140041a23  mov     edx, esi; SecurityDescriptorLength
0x140041a25  mov     rcx, rdi; SecurityDescriptorInput
0x140041a28  call    RtlValidRelativeSecurityDescriptor
0x140041a2d  test    al, al
0x140041a2f  jz      loc_140041B41
0x140041a35  mov     rcx, rdi; SecurityDescriptor
0x140041a38  call    RtlLengthSecurityDescriptor
0x140041a3d  test    eax, eax
0x140041a3f  jz      loc_140041B60
0x140041a45  cmp     eax, esi
0x140041a47  ja      loc_140041B60
0x140041a4d  cmp     r14b, 1
0x140041a51  jnz     short loc_140041AB0
0x140041a53  mov     r8d, eax
0x140041a56  mov     r9b, r14b
0x140041a59  mov     rdx, rdi
0x140041a5c  mov     rcx, r15
0x140041a5f  call    SkCopyToUntrusted
0x140041a64  jmp     short loc_140041AB0
0x140041a66  mov     edi, 0C000000Dh
0x140041a6b  mov     rbx, [rsp+0A8h+var_38]
0x140041a70  jmp     loc_140041B1D
0x140041a75  mov     edi, eax
0x140041a77  mov     rbx, [rsp+0A8h+var_38]
0x140041a7c  jmp     loc_140041B1D
0x140041a81  cmp     r14b, 1
0x140041a85  jnz     short loc_140041AB0
0x140041a87  mov     rax, [rsp+0A8h+arg_40]
0x140041a8f  mov     r8d, [rax]; Size
0x140041a92  mov     rdx, [rsp+0A8h+Src]; Src
0x140041a9a  mov     rcx, r15; void *
0x140041a9d  call    RtlCopyToUserFromUser
0x140041aa2  jmp     short loc_140041AB0
0x140041aa4  mov     edi, 0C000000Dh
0x140041aa9  mov     rbx, [rsp+0A8h+var_38]
0x140041aae  jmp     short loc_140041B1D
0x140041ab0  xor     edi, edi
0x140041ab2  jmp     short loc_140041B1D
0x140041ab4  mov     al, [rsp+0A8h+arg_58]
0x140041abb  mov     [rsp+0A8h+var_50], al
0x140041abf  mov     al, [rsp+0A8h+arg_50]
0x140041ac6  mov     [rsp+0A8h+var_58], al
0x140041aca  mov     rax, [rsp+0A8h+arg_48]
0x140041ad2  mov     [rsp+0A8h+var_60], rax
0x140041ad7  mov     rax, [rsp+0A8h+arg_40]
0x140041adf  mov     [rsp+0A8h+var_68], rax
0x140041ae4  mov     rax, [rsp+0A8h+Src]
0x140041aec  mov     [rsp+0A8h+var_70], rax
0x140041af1  mov     al, [rsp+0A8h+arg_30]
0x140041af8  mov     byte ptr [rsp+0A8h+var_78], al
0x140041afc  mov     rax, [rsp+0A8h+arg_28]
0x140041b04  mov     [rsp+0A8h+var_80], rax
0x140041b09  mov     rax, [rsp+0A8h+arg_20]
0x140041b11  mov     [rsp+0A8h+BugCheckParameter4], rax
0x140041b16  call    IumArg_GENERIC
0x140041b1b  mov     edi, eax
0x140041b1d  test    rbx, rbx
0x140041b20  jz      short loc_140041B2F
0x140041b22  mov     rdx, rbx
0x140041b25  mov     ecx, 1
0x140041b2a  call    SkFreePool
0x140041b2f  mov     eax, edi
0x140041b31  add     rsp, 80h
0x140041b38  pop     r15
0x140041b3a  pop     r14
0x140041b3c  pop     rdi
0x140041b3d  pop     rsi
0x140041b3e  pop     rbx
0x140041b3f  retn
0x140041b41  mov     r9d, esi; BugCheckParameter3
0x140041b44  mov     [rsp+0A8h+BugCheckParameter4], 0; BugCheckParameter4
0x140041b4d  mov     r8, rdi; BugCheckParameter2
0x140041b50  mov     edx, 44536149h; BugCheckParameter1
0x140041b55  mov     ecx, 29h ; ')'; BugCheckCode
0x140041b5a  call    SkeBugCheckEx
0x140041b60  mov     eax, eax
0x140041b62  mov     r9d, esi; BugCheckParameter3
0x140041b65  mov     [rsp+0A8h+BugCheckParameter4], rax; BugCheckParameter4
0x140041b6a  mov     r8, rdi; BugCheckParameter2
0x140041b6d  mov     edx, 44536149h; BugCheckParameter1
0x140041b72  mov     ecx, 29h ; ')'; BugCheckCode
0x140041b77  call    SkeBugCheckEx
0x1400fa437  push    rbp
0x1400fa439  sub     rsp, 60h
0x1400fa43d  mov     rbp, rdx
0x1400fa440  mov     dword ptr [rbp+64h], 1
0x1400fa447  mov     eax, [rbp+64h]
0x1400fa44a  add     rsp, 60h
0x1400fa44e  pop     rbp
0x1400fa44f  retn
0x1400fa451  push    rbp
0x1400fa453  sub     rsp, 60h
0x1400fa457  mov     rbp, rdx
0x1400fa45a  mov     dword ptr [rbp+60h], 1
0x1400fa461  mov     eax, [rbp+60h]
0x1400fa464  add     rsp, 60h
0x1400fa468  pop     rbp
0x1400fa469  retn
0x1400fa46b  push    rbp
0x1400fa46d  sub     rsp, 60h
0x1400fa471  mov     rbp, rdx
0x1400fa474  mov     dword ptr [rbp+68h], 1
0x1400fa47b  mov     eax, [rbp+68h]
0x1400fa47e  add     rsp, 60h
0x1400fa482  pop     rbp
0x1400fa483  retn
```
