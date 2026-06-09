# SclEtwWriteSid

- ea: `0x1800059a4`
- end: `0x180005a1a`
- name: `SclEtwWriteSid`
- size: `118`
- prototype: `void __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006024`

## callees

- `0x1800059a4`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800059d6`
- `ntdll!RtlLengthSid` at `0x1800059d6`
- `ntdll!EtwEventWrite` at `0x1800059ff`
- `ntdll!EtwEventWrite` at `0x1800059ff`

## pseudocode

```c
void __fastcall SclEtwWriteSid(__int64 a1, __int64 a2, void *a3)
{
  ULONG v6; // eax
  __int64 v7; // rcx
  __int128 v8; // [rsp+20h] [rbp-38h] BYREF

  if ( *(_QWORD *)(a1 + 32) )
  {
    v8 = 0;
    v6 = RtlLengthSid(a3);
    v7 = *(_QWORD *)(a1 + 32);
    *((_QWORD *)&v8 + 1) = v6;
    *(_QWORD *)&v8 = a3;
    ((void (__fastcall *)(__int64, __int64, __int64, __int128 *))EtwEventWrite)(v7, a2, 1, &v8);
  }
}

```

## disassembly

```asm
0x1800059a4  push    rbx
0x1800059a6  push    rsi
0x1800059a7  push    rdi
0x1800059a8  sub     rsp, 40h
0x1800059ac  mov     rax, cs:__security_cookie
0x1800059b3  xor     rax, rsp
0x1800059b6  mov     [rsp+58h+var_28], rax
0x1800059bb  cmp     qword ptr [rcx+20h], 0
0x1800059c0  mov     rdi, r8
0x1800059c3  mov     rsi, rdx
0x1800059c6  mov     rbx, rcx
0x1800059c9  jz      short loc_180005A05
0x1800059cb  xorps   xmm0, xmm0
0x1800059ce  mov     rcx, r8; Sid
0x1800059d1  movups  [rsp+58h+var_38], xmm0
0x1800059d6  call    cs:__imp_RtlLengthSid
0x1800059dc  mov     rcx, [rbx+20h]
0x1800059e0  lea     r9, [rsp+58h+var_38]
0x1800059e5  mov     r8d, 1
0x1800059eb  mov     dword ptr [rsp+58h+var_38+8], eax
0x1800059ef  mov     rdx, rsi
0x1800059f2  mov     qword ptr [rsp+58h+var_38], rdi
0x1800059f7  mov     dword ptr [rsp+58h+var_38+0Ch], 0
0x1800059ff  call    cs:__imp_EtwEventWrite
0x180005a05  mov     rcx, [rsp+58h+var_28]
0x180005a0a  xor     rcx, rsp; StackCookie
0x180005a0d  call    __security_check_cookie
0x180005a12  add     rsp, 40h
0x180005a16  pop     rdi
0x180005a17  pop     rsi
0x180005a18  pop     rbx
0x180005a19  retn
```
