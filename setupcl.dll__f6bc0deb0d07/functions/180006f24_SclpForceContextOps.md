# SclpForceContextOps

- ea: `0x180006f24`
- end: `0x180007057`
- name: `SclpForceContextOps`
- size: `307`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006024`

## callees

- `0x180006f24`
- `0x18000a524`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180006f56`
- `ntdll!_wcsicmp` at `0x180006fdc`
- `ntdll!_wcsicmp` at `0x180006f56`
- `ntdll!_wcsicmp` at `0x180006fdc`

## string_xrefs

- `0x180006fa5`: `Old and new paths were identical ([%ws]); using new path [%ws]...`
- `0x180007032`: `Old and new SID strings are identical ([%ws]); using new SID string [%ws]...`

## pseudocode

```c
__int64 __fastcall SclpForceContextOps(__int64 a1)
{
  _WORD *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rcx

  if ( (*(_DWORD *)(a1 + 8) & 2) != 0 )
  {
    v2 = (_WORD *)(a1 + 552);
    v3 = a1 + 32;
    if ( !_wcsicmp((const wchar_t *)(a1 + 32), (const wchar_t *)(a1 + 552)) )
    {
      if ( (unsigned __int16)(++*v2 - 97) > 0x19u && (unsigned __int16)(*v2 - 65) > 0x19u )
        *v2 = 65;
      v4 = a1 + 1152;
      if ( !a1 )
        v4 = 0;
      SclLogGenericMessage(
        v4,
        1,
        (int)SclEvent_Generic_Info,
        1291,
        (__int64)"SclpForceContextOps",
        "Old and new paths were identical ([%ws]); using new path [%ws]...",
        v3,
        v2);
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 4) != 0 && !_wcsicmp((const wchar_t *)(a1 + 1336), (const wchar_t *)(a1 + 1856)) )
  {
    v5 = (unsigned int)(*(_DWORD *)(a1 + 2380) - 1);
    if ( ++*(_WORD *)(a1 + 2 * v5 + 1856) > 0x39u )
      *(_WORD *)(a1 + 2 * v5 + 1856) = 48;
    v6 = a1 + 1152;
    if ( !a1 )
      v6 = 0;
    SclLogGenericMessage(
      v6,
      1,
      (int)SclEvent_Generic_Info,
      1310,
      (__int64)"SclpForceContextOps",
      "Old and new SID strings are identical ([%ws]); using new SID string [%ws]...",
      a1 + 1336,
      a1 + 1856);
  }
  return 0;
}

```

## disassembly

```asm
0x180006f24  push    rbx
0x180006f26  push    rbp
0x180006f27  push    rsi
0x180006f28  push    rdi
0x180006f29  push    r14
0x180006f2b  sub     rsp, 40h
0x180006f2f  mov     eax, [rcx+8]
0x180006f32  lea     r14, aSclpforceconte; "SclpForceContextOps"
0x180006f39  mov     rbx, rcx
0x180006f3c  mov     ebp, 1
0x180006f41  test    al, 2
0x180006f43  jz      short loc_180006FBD
0x180006f45  lea     rdi, [rcx+228h]
0x180006f4c  lea     rsi, [rcx+20h]
0x180006f50  mov     rdx, rdi; String2
0x180006f53  mov     rcx, rsi; String1
0x180006f56  call    cs:__imp__wcsicmp
0x180006f5c  test    eax, eax
0x180006f5e  jnz     short loc_180006FBD
0x180006f60  add     [rdi], bp
0x180006f63  movzx   ecx, word ptr [rdi]
0x180006f66  lea     eax, [rcx-61h]
0x180006f69  cmp     ax, 19h
0x180006f6d  jbe     short loc_180006F7E
0x180006f6f  lea     eax, [rbp+40h]
0x180006f72  sub     cx, ax
0x180006f75  cmp     cx, 19h
0x180006f79  jbe     short loc_180006F7E
0x180006f7b  mov     [rdi], ax
0x180006f7e  xor     eax, eax
0x180006f80  mov     [rsp+68h+var_30], rdi
0x180006f85  test    rbx, rbx
0x180006f88  mov     [rsp+68h+var_38], rsi
0x180006f8d  lea     rcx, [rbx+480h]
0x180006f94  mov     r9d, 50Bh
0x180006f9a  cmovz   rcx, rax
0x180006f9e  lea     r8, SclEvent_Generic_Info
0x180006fa5  lea     rax, aOldAndNewPaths; "Old and new paths were identical ([%ws]"...
0x180006fac  mov     edx, ebp
0x180006fae  mov     [rsp+68h+var_40], rax
0x180006fb3  mov     [rsp+68h+var_48], r14
0x180006fb8  call    SclLogGenericMessage
0x180006fbd  mov     eax, [rbx+8]
0x180006fc0  test    al, 4
0x180006fc2  jz      loc_18000704A
0x180006fc8  lea     rdi, [rbx+740h]
0x180006fcf  lea     rsi, [rbx+538h]
0x180006fd6  mov     rdx, rdi; String2
0x180006fd9  mov     rcx, rsi; String1
0x180006fdc  call    cs:__imp__wcsicmp
0x180006fe2  test    eax, eax
0x180006fe4  jnz     short loc_18000704A
0x180006fe6  mov     eax, [rbx+94Ch]
0x180006fec  sub     eax, ebp
0x180006fee  add     [rbx+rax*2+740h], bp
0x180006ff6  cmp     word ptr [rbx+rax*2+740h], 39h ; '9'
0x180006fff  jbe     short loc_18000700B
0x180007001  mov     word ptr [rbx+rax*2+740h], 30h ; '0'
0x18000700b  xor     eax, eax
0x18000700d  mov     [rsp+68h+var_30], rdi
0x180007012  test    rbx, rbx
0x180007015  mov     [rsp+68h+var_38], rsi
0x18000701a  lea     rcx, [rbx+480h]
0x180007021  mov     r9d, 51Eh
0x180007027  cmovz   rcx, rax
0x18000702b  lea     r8, SclEvent_Generic_Info
0x180007032  lea     rax, aOldAndNewSidSt_0; "Old and new SID strings are identical ("...
0x180007039  mov     edx, ebp
0x18000703b  mov     [rsp+68h+var_40], rax
0x180007040  mov     [rsp+68h+var_48], r14
0x180007045  call    SclLogGenericMessage
0x18000704a  xor     eax, eax
0x18000704c  add     rsp, 40h
0x180007050  pop     r14
0x180007052  pop     rdi
0x180007053  pop     rsi
0x180007054  pop     rbp
0x180007055  pop     rbx
0x180007056  retn
```
