# VidSidpInitializeVmms

- ea: `0x14009b9ec`
- end: `0x14009baa6`
- name: `VidSidpInitializeVmms`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400769d8`

## callees

- `0x140021c60`
- `0x14009b9ec`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14009ba29`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14009ba29`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009ba7e`
- `ntoskrnl!RtlInitializeSidEx` at `0x14009ba7e`

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
0x14009b9ec  mov     [rsp+arg_10], rbx
0x14009b9f1  push    rdi
0x14009b9f2  sub     rsp, 60h
0x14009b9f6  mov     rax, cs:__security_cookie
0x14009b9fd  xor     rax, rsp
0x14009ba00  mov     [rsp+68h+var_10], rax
0x14009ba05  xor     eax, eax
0x14009ba07  mov     [rsp+68h+var_14], 500h
0x14009ba0e  mov     [rsp+68h+var_18], eax
0x14009ba12  mov     rbx, rdx
0x14009ba15  mov     rdi, rcx
0x14009ba18  test    rdx, rdx
0x14009ba1b  jnz     short loc_14009BA24
0x14009ba1d  mov     eax, 0C000000Dh
0x14009ba22  jmp     short loc_14009BA8A
0x14009ba24  mov     ecx, 6; SubAuthorityCount
0x14009ba29  call    cs:__imp_RtlLengthRequiredSid
0x14009ba30  nop     dword ptr [rax+rax+00h]
0x14009ba35  mov     ecx, eax
0x14009ba37  cmp     [rbx], eax
0x14009ba39  jnb     short loc_14009BA44
0x14009ba3b  mov     eax, 0C0000023h
0x14009ba40  mov     [rbx], ecx
0x14009ba42  jmp     short loc_14009BA8A
0x14009ba44  mov     [rsp+68h+var_28], 61EB4C27h
0x14009ba4c  lea     rdx, [rsp+68h+var_18]
0x14009ba51  mov     [rsp+68h+var_30], 0C7CA7EEh
0x14009ba59  mov     r9d, 50h ; 'P'
0x14009ba5f  mov     [rsp+68h+var_38], 0D0B140A6h
0x14009ba67  mov     rcx, rdi
0x14009ba6a  mov     [rsp+68h+var_40], 7925472Dh
0x14009ba72  mov     [rsp+68h+var_48], 16396D1Bh
0x14009ba7a  lea     r8d, [r9-4Ah]
0x14009ba7e  call    cs:__imp_RtlInitializeSidEx
0x14009ba85  nop     dword ptr [rax+rax+00h]
0x14009ba8a  mov     rcx, [rsp+68h+var_10]
0x14009ba8f  xor     rcx, rsp; StackCookie
0x14009ba92  call    __security_check_cookie
0x14009ba97  mov     rbx, [rsp+68h+arg_10]
0x14009ba9f  add     rsp, 60h
0x14009baa3  pop     rdi
0x14009baa4  retn
```
