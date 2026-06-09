# WPP_SF_D

- ea: `0x1800111dc`
- end: `0x180011236`
- name: `WPP_SF_D`
- size: `90`
- prototype: ``
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x180002390`
- `0x180002550`
- `0x180002750`
- `0x180002bd0`
- `0x180002e00`
- `0x180003c30`
- `0x180003f90`
- `0x180004530`
- `0x180004d40`
- `0x180005f40`
- `0x180006604`
- `0x180008010`
- `0x1800112e0`
- `0x180011480`
- `0x180011690`
- `0x180011970`
- `0x180011b10`
- `0x180011de0`
- `0x180011f80`
- `0x180012130`
- `0x180012400`
- `0x180012670`
- `0x180012b10`
- `0x180012ee0`
- `0x1800130e0`
- `0x1800133d0`
- `0x180013580`
- `0x1800136c0`
- `0x180013990`
- `0x180013bf0`
- `0x180013db0`
- `0x180017cb0`
- `0x18001c25c`
- `0x18001c410`

## callees

- `0x180008a90`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180011217`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180011217`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+40h] [rbp-18h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x1800111dc  mov     r11, rsp
0x1800111df  sub     rsp, 58h
0x1800111e3  mov     rax, cs:__security_cookie
0x1800111ea  xor     rax, rsp
0x1800111ed  mov     [rsp+58h+var_10], rax
0x1800111f2  mov     qword ptr [r11-28h], 0
0x1800111fa  lea     rax, [r11-18h]
0x1800111fe  mov     [r11-18h], r9d
0x180011202  movzx   r9d, dx; MessageNumber
0x180011206  mov     edx, 2Bh ; '+'; MessageFlags
0x18001120b  mov     qword ptr [r11-30h], 4
0x180011213  mov     [r11-38h], rax
0x180011217  call    cs:__imp_TraceMessage
0x18001121e  nop     dword ptr [rax+rax+00h]
0x180011223  mov     rcx, [rsp+58h+var_10]
0x180011228  xor     rcx, rsp; StackCookie
0x18001122b  call    __security_check_cookie
0x180011230  add     rsp, 58h
0x180011234  retn
```
