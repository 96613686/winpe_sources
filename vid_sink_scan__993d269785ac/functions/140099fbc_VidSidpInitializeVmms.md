# VidSidpInitializeVmms

- ea: `0x140099fbc`
- end: `0x14009a076`
- name: `VidSidpInitializeVmms`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140075afc`

## callees

- `0x140021650`
- `0x140099fbc`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140099ff9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140099ff9`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009a04e`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009a04e`

## pseudocode

```c
__int64 __fastcall VidSidpInitializeVmms(__int64 a1, ULONG *a2)
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
    return RtlInitializeSidEx(a1, &v6, 6, 80, 372862235);
  result = 3221225507LL;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x140099fbc  mov     [rsp+arg_10], rbx
0x140099fc1  push    rdi
0x140099fc2  sub     rsp, 60h
0x140099fc6  mov     rax, cs:__security_cookie
0x140099fcd  xor     rax, rsp
0x140099fd0  mov     [rsp+68h+var_10], rax
0x140099fd5  xor     eax, eax
0x140099fd7  mov     [rsp+68h+var_14], 500h
0x140099fde  mov     [rsp+68h+var_18], eax
0x140099fe2  mov     rbx, rdx
0x140099fe5  mov     rdi, rcx
0x140099fe8  test    rdx, rdx
0x140099feb  jnz     short loc_140099FF4
0x140099fed  mov     eax, 0C000000Dh
0x140099ff2  jmp     short loc_14009A05A
0x140099ff4  mov     ecx, 6; SubAuthorityCount
0x140099ff9  call    cs:__imp_RtlLengthRequiredSid
0x14009a000  nop     dword ptr [rax+rax+00h]
0x14009a005  mov     ecx, eax
0x14009a007  cmp     [rbx], eax
0x14009a009  jnb     short loc_14009A014
0x14009a00b  mov     eax, 0C0000023h
0x14009a010  mov     [rbx], ecx
0x14009a012  jmp     short loc_14009A05A
0x14009a014  mov     [rsp+68h+var_28], 61EB4C27h
0x14009a01c  lea     rdx, [rsp+68h+var_18]
0x14009a021  mov     [rsp+68h+var_30], 0C7CA7EEh
0x14009a029  mov     r9d, 50h ; 'P'
0x14009a02f  mov     [rsp+68h+var_38], 0D0B140A6h
0x14009a037  mov     rcx, rdi
0x14009a03a  mov     [rsp+68h+var_40], 7925472Dh
0x14009a042  mov     [rsp+68h+var_48], 16396D1Bh
0x14009a04a  lea     r8d, [r9-4Ah]
0x14009a04e  call    cs:__imp_RtlInitializeSidEx
0x14009a055  nop     dword ptr [rax+rax+00h]
0x14009a05a  mov     rcx, [rsp+68h+var_10]
0x14009a05f  xor     rcx, rsp; StackCookie
0x14009a062  call    __security_check_cookie
0x14009a067  mov     rbx, [rsp+68h+arg_10]
0x14009a06f  add     rsp, 60h
0x14009a073  pop     rdi
0x14009a074  retn
```
