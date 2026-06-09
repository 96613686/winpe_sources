# SclSecuritySetDescriptor

- ea: `0x180001bc0`
- end: `0x180001c6b`
- name: `SclSecuritySetDescriptor`
- size: `171`
- prototype: `int __fastcall(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800088bc`
- `0x180008be0`
- `0x1800121d4`

## callees

- `0x180001bc0`

## import_xrefs

- `ntdll!RtlGetControlSecurityDescriptor` at `0x180001bec`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180001bec`
- `ntdll!NtSetSecurityObject` at `0x180001c55`
- `ntdll!NtSetSecurityObject` at `0x180001c55`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180001c24`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180001c43`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180001c24`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180001c43`

## pseudocode

```c
int __fastcall SclSecuritySetDescriptor(HANDLE Handle, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  int result; // eax
  WORD v5; // r8
  SECURITY_INFORMATION v6; // edi
  WORD v7; // [rsp+40h] [rbp+18h] BYREF
  ULONG v8; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 0;
  result = RtlGetControlSecurityDescriptor(SecurityDescriptor, &v7, &v8);
  if ( result >= 0 )
  {
    v5 = v7;
    v6 = v7 & 4 | 0x1B;
    if ( (v7 & 0x10) == 0 )
      v6 = v7 & 4 | 3;
    if ( (v7 & 0x400) != 0 )
    {
      result = RtlSetControlSecurityDescriptor(SecurityDescriptor, 0x100u, 0x100u);
      v5 = v7;
    }
    if ( (v5 & 0x800) != 0 )
      result = RtlSetControlSecurityDescriptor(SecurityDescriptor, 0x200u, 0x200u);
    if ( result >= 0 )
      return NtSetSecurityObject(Handle, v6, SecurityDescriptor);
  }
  return result;
}

```

## disassembly

```asm
0x180001bc0  mov     r11, rsp
0x180001bc3  mov     [r11+8], rbx
0x180001bc7  mov     [r11+10h], rsi
0x180001bcb  push    rdi
0x180001bcc  sub     rsp, 20h
0x180001bd0  mov     rbx, rdx
0x180001bd3  lea     r8, [r11+20h]; Revision
0x180001bd7  xor     eax, eax
0x180001bd9  lea     rdx, [r11+18h]; Control
0x180001bdd  mov     rsi, rcx
0x180001be0  mov     [rsp+28h+arg_10], ax
0x180001be5  mov     rcx, rbx; SecurityDescriptor
0x180001be8  mov     [rsp+28h+arg_18], eax
0x180001bec  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180001bf2  test    eax, eax
0x180001bf4  js      short loc_180001C5B
0x180001bf6  movzx   r8d, [rsp+28h+arg_10]
0x180001bfc  mov     edx, r8d
0x180001bff  and     edx, 4
0x180001c02  or      edx, 3
0x180001c05  mov     edi, edx
0x180001c07  or      edi, 18h
0x180001c0a  test    r8b, 10h
0x180001c0e  cmovz   edi, edx
0x180001c11  bt      r8w, 0Ah
0x180001c17  jnb     short loc_180001C30
0x180001c19  mov     edx, 100h; ControlBitsOfInterest
0x180001c1e  mov     rcx, rbx; SecurityDescriptor
0x180001c21  mov     r8d, edx; ControlBitsToSet
0x180001c24  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180001c2a  movzx   r8d, [rsp+28h+arg_10]
0x180001c30  bt      r8w, 0Bh
0x180001c36  jnb     short loc_180001C49
0x180001c38  mov     edx, 200h; ControlBitsOfInterest
0x180001c3d  mov     rcx, rbx; SecurityDescriptor
0x180001c40  mov     r8d, edx; ControlBitsToSet
0x180001c43  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180001c49  test    eax, eax
0x180001c4b  js      short loc_180001C5B
0x180001c4d  mov     r8, rbx; SecurityDescriptor
0x180001c50  mov     edx, edi; SecurityInformation
0x180001c52  mov     rcx, rsi; Handle
0x180001c55  call    cs:__imp_NtSetSecurityObject
0x180001c5b  mov     rbx, [rsp+28h+arg_0]
0x180001c60  mov     rsi, [rsp+28h+arg_8]
0x180001c65  add     rsp, 20h
0x180001c69  pop     rdi
0x180001c6a  retn
```
