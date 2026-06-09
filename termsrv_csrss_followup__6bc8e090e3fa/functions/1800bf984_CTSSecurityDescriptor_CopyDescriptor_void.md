# CTSSecurityDescriptor::CopyDescriptor(void *)

- ea: `0x1800bf984`
- end: `0x1800bfa44`
- name: `?CopyDescriptor@CTSSecurityDescriptor@@QEAAJPEAX@Z`
- size: `192`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180055a3c`

## callees

- `0x1800168c0`
- `0x1800bf984`
- `0x1800caedc`

## import_xrefs

- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800bf9b3`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800bf9b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bf9f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bf9f1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800bf9db`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800bf9db`

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
0x1800bf984  mov     r11, rsp
0x1800bf987  mov     [r11+8], rbx
0x1800bf98b  mov     [r11+10h], rbp
0x1800bf98f  push    rsi
0x1800bf990  push    rdi
0x1800bf991  push    r14
0x1800bf993  sub     rsp, 20h
0x1800bf997  mov     rbp, rdx
0x1800bf99a  lea     r8, [r11+20h]; Revision
0x1800bf99e  xor     eax, eax
0x1800bf9a0  lea     rdx, [r11+18h]; Control
0x1800bf9a4  mov     rsi, rcx
0x1800bf9a7  mov     [rsp+38h+arg_10], ax
0x1800bf9ac  mov     rcx, rbp; SecurityDescriptor
0x1800bf9af  mov     [rsp+38h+arg_18], eax
0x1800bf9b3  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800bf9ba  nop     dword ptr [rax+rax+00h]
0x1800bf9bf  mov     ebx, eax
0x1800bf9c1  test    eax, eax
0x1800bf9c3  js      short loc_1800BFA2E
0x1800bf9c5  mov     eax, 8000h
0x1800bf9ca  test    [rsp+38h+arg_10], ax
0x1800bf9cf  jnz     short loc_1800BF9D8
0x1800bf9d1  mov     ebx, 8007053Ah
0x1800bf9d6  jmp     short loc_1800BFA2E
0x1800bf9d8  mov     rcx, rbp; pSecurityDescriptor
0x1800bf9db  call    cs:__imp_GetSecurityDescriptorLength
0x1800bf9e2  nop     dword ptr [rax+rax+00h]
0x1800bf9e7  mov     edx, eax; uBytes
0x1800bf9e9  mov     ecx, 40h ; '@'; uFlags
0x1800bf9ee  mov     r14d, eax
0x1800bf9f1  call    cs:__imp_LocalAlloc
0x1800bf9f8  nop     dword ptr [rax+rax+00h]
0x1800bf9fd  mov     rdi, rax
0x1800bfa00  test    rax, rax
0x1800bfa03  jnz     short loc_1800BFA0C
0x1800bfa05  mov     ebx, 8007000Eh
0x1800bfa0a  jmp     short loc_1800BFA2E
0x1800bfa0c  mov     r8, r14; Size
0x1800bfa0f  mov     rdx, rbp; Src
0x1800bfa12  mov     rcx, rdi; void *
0x1800bfa15  xor     ebx, ebx
0x1800bfa17  call    memcpy_0
0x1800bfa1c  mov     rcx, [rsi+8]; hMem
0x1800bfa20  test    rcx, rcx
0x1800bfa23  jz      short loc_1800BFA2A
0x1800bfa25  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800bfa2a  mov     [rsi+8], rdi
0x1800bfa2e  mov     rbp, [rsp+38h+arg_8]
0x1800bfa33  mov     eax, ebx
0x1800bfa35  mov     rbx, [rsp+38h+arg_0]
0x1800bfa3a  add     rsp, 20h
0x1800bfa3e  pop     r14
0x1800bfa40  pop     rdi
0x1800bfa41  pop     rsi
0x1800bfa42  retn
```
