# VidSidInitializeVmCompute

- ea: `0x140099efc`
- end: `0x140099fb6`
- name: `VidSidInitializeVmCompute`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140075afc`
- `0x1400a7d58`

## callees

- `0x140021650`
- `0x140099efc`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140099f39`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140099f39`
- `ntoskrnl!RtlInitializeSidEx` at `0x140099f8e`
- `ntoskrnl!RtlInitializeSidEx` at `0x140099f8e`

## pseudocode

```c
__int64 __fastcall VidSidInitializeVmCompute(__int64 a1, ULONG *a2)
{
  __int64 result; // rax
  ULONG v5; // ecx
  int v6; // [rsp+50h] [rbp-18h] BYREF
  __int16 v7; // [rsp+54h] [rbp-14h]

  v7 = 1280;
  v6 = 0;
  if ( !a2 )
    return 3221225485LL;
  v5 = RtlLengthRequiredSid(6u);
  if ( *a2 >= v5 )
    return RtlInitializeSidEx(a1, &v6, 6, 80, -427641928);
  result = 3221225507LL;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x140099efc  mov     [rsp+arg_10], rbx
0x140099f01  push    rdi
0x140099f02  sub     rsp, 60h
0x140099f06  mov     rax, cs:__security_cookie
0x140099f0d  xor     rax, rsp
0x140099f10  mov     [rsp+68h+var_10], rax
0x140099f15  xor     eax, eax
0x140099f17  mov     [rsp+68h+var_14], 500h
0x140099f1e  mov     [rsp+68h+var_18], eax
0x140099f22  mov     rbx, rdx
0x140099f25  mov     rdi, rcx
0x140099f28  test    rdx, rdx
0x140099f2b  jnz     short loc_140099F34
0x140099f2d  mov     eax, 0C000000Dh
0x140099f32  jmp     short loc_140099F9A
0x140099f34  mov     ecx, 6; SubAuthorityCount
0x140099f39  call    cs:__imp_RtlLengthRequiredSid
0x140099f40  nop     dword ptr [rax+rax+00h]
0x140099f45  mov     ecx, eax
0x140099f47  cmp     [rbx], eax
0x140099f49  jnb     short loc_140099F54
0x140099f4b  mov     eax, 0C0000023h
0x140099f50  mov     [rbx], ecx
0x140099f52  jmp     short loc_140099F9A
0x140099f54  mov     [rsp+68h+var_28], 3D66EE0Fh
0x140099f5c  lea     rdx, [rsp+68h+var_18]
0x140099f61  mov     [rsp+68h+var_30], 0F9BCB43Ch
0x140099f69  mov     r9d, 50h ; 'P'
0x140099f6f  mov     [rsp+68h+var_38], 0B1F45B9Bh
0x140099f77  mov     rcx, rdi
0x140099f7a  mov     [rsp+68h+var_40], 0CE815B35h
0x140099f82  mov     [rsp+68h+var_48], 0E682B3B8h
0x140099f8a  lea     r8d, [r9-4Ah]
0x140099f8e  call    cs:__imp_RtlInitializeSidEx
0x140099f95  nop     dword ptr [rax+rax+00h]
0x140099f9a  mov     rcx, [rsp+68h+var_10]
0x140099f9f  xor     rcx, rsp; StackCookie
0x140099fa2  call    __security_check_cookie
0x140099fa7  mov     rbx, [rsp+68h+arg_10]
0x140099faf  add     rsp, 60h
0x140099fb3  pop     rdi
0x140099fb4  retn
```
