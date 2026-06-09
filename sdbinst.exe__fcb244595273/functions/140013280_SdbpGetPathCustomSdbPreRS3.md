# SdbpGetPathCustomSdbPreRS3

- ea: `0x140013280`
- end: `0x1400133dc`
- name: `SdbpGetPathCustomSdbPreRS3`
- size: `348`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x14001008c`
- `0x1400100c4`
- `0x140012db0`
- `0x140013280`
- `0x14001357c`
- `0x14002e420`

## string_xrefs

- `0x140013397`: `AslPathCombine failed [%x]`
- `0x14001333f`: `SdbpGetPathCustomSdbPreRS3`

## pseudocode

```c
__int64 __fastcall SdbpGetPathCustomSdbPreRS3(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  int ProcessHostGuestArchitectures; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  __int64 *v12; // rcx
  int v13; // [rsp+20h] [rbp-E0h]
  __int16 v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v15; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h]
  wchar_t v18; // [rsp+44h] [rbp-BCh]
  _OWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v20[264]; // [rsp+70h] [rbp-90h] BYREF

  v16 = *(_QWORD *)L"Custom";
  v17 = *(_DWORD *)L"om";
  v18 = aCustom[6];
  v19[0] = *(_OWORD *)L"Custom\\Custom64";
  v19[1] = *(_OWORD *)L"ustom64";
  if ( a2 < 7 )
    return 3221225507LL;
  *a1 = 0;
  v20[0] = 0;
  v15 = -1;
  v14[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v15, v14, a4);
  v9 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    if ( v14[0] == 9 || (v12 = &v16, v14[0] == 12) )
      v12 = (__int64 *)v19;
    if ( !a3 )
      a3 = (unsigned __int16 *)&Format;
    ProcessHostGuestArchitectures = AslPathCombine(v12, a3, v20, 260);
    v9 = ProcessHostGuestArchitectures;
    if ( ProcessHostGuestArchitectures >= 0 )
      return (unsigned int)SdbpGetPathAppPatch(a1, a2, v20);
    v10 = "AslPathCombine failed [%x]";
    v11 = 1253;
  }
  else
  {
    v10 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v11 = 1239;
  }
  v13 = ProcessHostGuestArchitectures;
  AslLogCallPrintf(1, "SdbpGetPathCustomSdbPreRS3", v11, v10, v13);
  return v9;
}

```

## disassembly

```asm
0x140013280  push    rbp
0x140013282  push    rbx
0x140013283  push    rsi
0x140013284  push    rdi
0x140013285  push    r14
0x140013287  push    r15
0x140013289  lea     rbp, [rsp-198h]
0x140013291  sub     rsp, 298h
0x140013298  mov     rax, cs:__security_cookie
0x14001329f  xor     rax, rsp
0x1400132a2  mov     [rbp+1C0h+var_40], rax
0x1400132a9  movsd   xmm0, qword ptr cs:aCustom; "Custom"
0x1400132b1  mov     r14, r9
0x1400132b4  mov     eax, dword ptr cs:aCustom+8; "om"
0x1400132ba  mov     rdi, r8
0x1400132bd  movsd   [rsp+2C0h+var_288], xmm0
0x1400132c3  mov     r15, rdx
0x1400132c6  mov     [rsp+2C0h+var_280], eax
0x1400132ca  mov     rsi, rcx
0x1400132cd  movzx   eax, word ptr cs:aCustom+0Ch; ""
0x1400132d4  mov     [rsp+2C0h+var_27C], ax
0x1400132d9  movups  xmm0, xmmword ptr cs:aCustomCustom64; "Custom\\Custom64"
0x1400132e0  movups  xmm1, xmmword ptr cs:aCustomCustom64+10h; "ustom64"
0x1400132e7  movups  [rsp+2C0h+var_278], xmm0
0x1400132ec  movups  [rsp+2C0h+var_268], xmm1
0x1400132f1  cmp     rdx, 7
0x1400132f5  jnb     short loc_140013301
0x1400132f7  mov     eax, 0C0000023h
0x1400132fc  jmp     loc_1400133BD
0x140013301  xor     eax, eax
0x140013303  lea     rdx, [rsp+2C0h+var_290]
0x140013308  mov     [rcx], ax
0x14001330b  mov     r8, r14
0x14001330e  mov     [rsp+2C0h+var_250], ax
0x140013313  lea     rcx, [rsp+2C0h+var_28C]
0x140013318  mov     eax, 0FFFFh
0x14001331d  mov     [rsp+2C0h+var_28C], ax
0x140013322  mov     [rsp+2C0h+var_290], ax
0x140013327  call    SdbpGetProcessHostGuestArchitectures
0x14001332c  mov     ebx, eax
0x14001332e  test    eax, eax
0x140013330  jns     short loc_140013356
0x140013332  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x140013339  mov     r8d, 4D7h
0x14001333f  lea     rdx, aSdbpgetpathcus_0; "SdbpGetPathCustomSdbPreRS3"
0x140013346  mov     [rsp+2C0h+var_2A0], eax
0x14001334a  mov     ecx, 1
0x14001334f  call    AslLogCallPrintf
0x140013354  jmp     short loc_1400133BB
0x140013356  cmp     [rsp+2C0h+var_290], 9
0x14001335c  jz      short loc_14001336B
0x14001335e  cmp     [rsp+2C0h+var_290], 0Ch
0x140013364  lea     rcx, [rsp+2C0h+var_288]
0x140013369  jnz     short loc_140013370
0x14001336b  lea     rcx, [rsp+2C0h+var_278]
0x140013370  lea     rax, Format
0x140013377  test    rdi, rdi
0x14001337a  mov     r9d, 104h
0x140013380  lea     r8, [rsp+2C0h+var_250]
0x140013385  cmovz   rdi, rax
0x140013389  mov     rdx, rdi
0x14001338c  call    AslPathCombine
0x140013391  mov     ebx, eax
0x140013393  test    eax, eax
0x140013395  jns     short loc_1400133A6
0x140013397  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x14001339e  mov     r8d, 4E5h
0x1400133a4  jmp     short loc_14001333F
0x1400133a6  mov     r9, r14
0x1400133a9  lea     r8, [rsp+2C0h+var_250]
0x1400133ae  mov     rdx, r15; unsigned __int64
0x1400133b1  mov     rcx, rsi; unsigned __int16 *
0x1400133b4  call    SdbpGetPathAppPatch
0x1400133b9  mov     ebx, eax
0x1400133bb  mov     eax, ebx
0x1400133bd  mov     rcx, [rbp+1C0h+var_40]
0x1400133c4  xor     rcx, rsp; StackCookie
0x1400133c7  call    __security_check_cookie
0x1400133cc  add     rsp, 298h
0x1400133d3  pop     r15
0x1400133d5  pop     r14
0x1400133d7  pop     rdi
0x1400133d8  pop     rsi
0x1400133d9  pop     rbx
0x1400133da  pop     rbp
0x1400133db  retn
```
