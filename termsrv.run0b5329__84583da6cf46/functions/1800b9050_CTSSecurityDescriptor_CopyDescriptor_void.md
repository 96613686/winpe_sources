# CTSSecurityDescriptor::CopyDescriptor(void *)

- ea: `0x1800b9050`
- end: `0x1800b90fd`
- name: `?CopyDescriptor@CTSSecurityDescriptor@@QEAAJPEAX@Z`
- size: `173`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800532dc`

## callees

- `0x180015dcc`
- `0x1800b9050`
- `0x1800c4e0c`

## import_xrefs

- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800b907f`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800b907f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b90b1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b90b1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800b90a1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800b90a1`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::CopyDescriptor(CTSSecurityDescriptor *this, void *a2)
{
  NTSTATUS ControlSecurityDescriptor; // ebx
  SIZE_T SecurityDescriptorLength; // r14
  HLOCAL v6; // rax
  HLOCAL v7; // rdi
  void *v8; // rcx
  __int16 v10; // [rsp+50h] [rbp+18h] BYREF
  ULONG v11; // [rsp+58h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(a2, (PSECURITY_DESCRIPTOR_CONTROL)&v10, &v11);
  if ( ControlSecurityDescriptor >= 0 )
  {
    if ( v10 < 0 )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
      v6 = LocalAlloc(0x40u, SecurityDescriptorLength);
      v7 = v6;
      if ( v6 )
      {
        ControlSecurityDescriptor = 0;
        memcpy_0(v6, a2, SecurityDescriptorLength);
        v8 = (void *)*((_QWORD *)this + 1);
        if ( v8 )
          CUtils::CleanupSD(v8);
        *((_QWORD *)this + 1) = v7;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147023558;
    }
  }
  return (unsigned int)ControlSecurityDescriptor;
}

```

## disassembly

```asm
0x1800b9050  mov     r11, rsp
0x1800b9053  mov     [r11+8], rbx
0x1800b9057  mov     [r11+10h], rbp
0x1800b905b  push    rsi
0x1800b905c  push    rdi
0x1800b905d  push    r14
0x1800b905f  sub     rsp, 20h
0x1800b9063  mov     rbp, rdx
0x1800b9066  lea     r8, [r11+20h]; Revision
0x1800b906a  xor     eax, eax
0x1800b906c  lea     rdx, [r11+18h]; Control
0x1800b9070  mov     rsi, rcx
0x1800b9073  mov     [rsp+38h+arg_10], ax
0x1800b9078  mov     rcx, rbp; SecurityDescriptor
0x1800b907b  mov     [rsp+38h+arg_18], eax
0x1800b907f  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800b9085  mov     ebx, eax
0x1800b9087  test    eax, eax
0x1800b9089  js      short loc_1800B90E8
0x1800b908b  mov     eax, 8000h
0x1800b9090  test    [rsp+38h+arg_10], ax
0x1800b9095  jnz     short loc_1800B909E
0x1800b9097  mov     ebx, 8007053Ah
0x1800b909c  jmp     short loc_1800B90E8
0x1800b909e  mov     rcx, rbp; pSecurityDescriptor
0x1800b90a1  call    cs:__imp_GetSecurityDescriptorLength
0x1800b90a7  mov     edx, eax; uBytes
0x1800b90a9  mov     ecx, 40h ; '@'; uFlags
0x1800b90ae  mov     r14d, eax
0x1800b90b1  call    cs:__imp_LocalAlloc
0x1800b90b7  mov     rdi, rax
0x1800b90ba  test    rax, rax
0x1800b90bd  jnz     short loc_1800B90C6
0x1800b90bf  mov     ebx, 8007000Eh
0x1800b90c4  jmp     short loc_1800B90E8
0x1800b90c6  mov     r8, r14; Size
0x1800b90c9  mov     rdx, rbp; Src
0x1800b90cc  mov     rcx, rdi; void *
0x1800b90cf  xor     ebx, ebx
0x1800b90d1  call    memcpy_0
0x1800b90d6  mov     rcx, [rsi+8]; hMem
0x1800b90da  test    rcx, rcx
0x1800b90dd  jz      short loc_1800B90E4
0x1800b90df  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800b90e4  mov     [rsi+8], rdi
0x1800b90e8  mov     rbp, [rsp+38h+arg_8]
0x1800b90ed  mov     eax, ebx
0x1800b90ef  mov     rbx, [rsp+38h+arg_0]
0x1800b90f4  add     rsp, 20h
0x1800b90f8  pop     r14
0x1800b90fa  pop     rdi
0x1800b90fb  pop     rsi
0x1800b90fc  retn
```
