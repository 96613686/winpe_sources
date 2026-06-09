# VidHandlerpMsrAddressRegisterEntry

- ea: `0x1400866a8`
- end: `0x1400867c6`
- name: `VidHandlerpMsrAddressRegisterEntry`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140085e30`

## callees

- `0x140021650`
- `0x14002f524`
- `0x140073e0c`
- `0x1400866a8`
- `0x1400b13c0`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14008678a`
- `ntoskrnl!RtlRbRemoveNode` at `0x14008678a`
- `winhvr!WinHvInstallIntercept` at `0x140086752`
- `winhvr!WinHvInstallIntercept` at `0x140086752`

## pseudocode

```c
__int64 __fastcall VidHandlerpMsrAddressRegisterEntry(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-38h] BYREF
  int v12; // [rsp+28h] [rbp-30h]

  v3 = a1 + 3424;
  v12 = 0;
  v11 = 0;
  if ( (unsigned __int8)VidHandlerTableInsert(a1 + 3424) )
  {
    if ( a3 )
    {
      v7 = VsmmPhuStoreHandlerRestore(a1, a2, a3);
      if ( v7 < 0 )
      {
        v8 = 3688;
LABEL_8:
        VidTraceErrorStatusInternal0(
          "VidHandlerpMsrAddressRegisterEntry",
          "onecore\\vm\\vid\\sys\\driver\\vidhandler.c",
          v8);
        RtlRbRemoveNode(v3, a2 + 160);
        return (unsigned int)v7;
      }
    }
    else
    {
      v9 = *(_QWORD *)(a1 + 648);
      v12 = *(_DWORD *)(a2 + 120);
      LODWORD(v11) = 12;
      v7 = WinHvInstallIntercept(v9, 3, &v11);
      if ( v7 < 0 )
      {
        v8 = 3707;
        goto LABEL_8;
      }
    }
    _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 1528) + 504LL));
    return 0;
  }
  v7 = -1070137343;
  VidTraceErrorStatusInternal0(
    "VidHandlerpMsrAddressRegisterEntry",
    "onecore\\vm\\vid\\sys\\driver\\vidhandler.c",
    3676);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400866a8  mov     [rsp+arg_18], rbx
0x1400866ad  push    rbp
0x1400866ae  push    rsi
0x1400866af  push    rdi
0x1400866b0  sub     rsp, 40h
0x1400866b4  mov     rax, cs:__security_cookie
0x1400866bb  xor     rax, rsp
0x1400866be  mov     [rsp+58h+var_28], rax
0x1400866c3  xor     eax, eax
0x1400866c5  lea     rbp, [rcx+0D60h]
0x1400866cc  mov     rdi, rcx
0x1400866cf  mov     qword ptr [rsp+58h+var_34], rax
0x1400866d4  mov     rcx, rbp
0x1400866d7  mov     [rsp+20h], rax
0x1400866dc  mov     rbx, r8
0x1400866df  mov     rsi, rdx
0x1400866e2  call    VidHandlerTableInsert
0x1400866e7  test    al, al
0x1400866e9  jnz     short loc_140086711
0x1400866eb  mov     ebx, 0C0370001h
0x1400866f0  mov     r9d, ebx
0x1400866f3  lea     rdx, aOnecoreVmVidSy_14; "onecore\\vm\\vid\\sys\\driver\\vidhandl"...
0x1400866fa  mov     r8d, 0E5Ch
0x140086700  lea     rcx, aVidhandlerpmsr; "VidHandlerpMsrAddressRegisterEntry"
0x140086707  call    VidTraceErrorStatusInternal0
0x14008670c  jmp     loc_1400867A9
0x140086711  test    rbx, rbx
0x140086714  jz      short loc_140086732
0x140086716  mov     r8, rbx
0x140086719  mov     rdx, rsi
0x14008671c  mov     rcx, rdi
0x14008671f  call    VsmmPhuStoreHandlerRestore
0x140086724  mov     ebx, eax
0x140086726  test    eax, eax
0x140086728  jns     short loc_140086798
0x14008672a  mov     r8d, 0E68h
0x140086730  jmp     short loc_14008676A
0x140086732  mov     eax, [rsi+78h]
0x140086735  lea     r8, [rsp+58h+var_38]
0x14008673a  mov     rcx, [rdi+288h]
0x140086741  mov     edx, 3
0x140086746  mov     [rsp+58h+var_34+4], eax
0x14008674a  mov     [rsp+58h+var_38], 0Ch
0x140086752  call    cs:__imp_WinHvInstallIntercept
0x140086759  nop     dword ptr [rax+rax+00h]
0x14008675e  mov     ebx, eax
0x140086760  test    eax, eax
0x140086762  jns     short loc_140086798
0x140086764  mov     r8d, 0E7Bh
0x14008676a  mov     r9d, ebx
0x14008676d  lea     rdx, aOnecoreVmVidSy_14; "onecore\\vm\\vid\\sys\\driver\\vidhandl"...
0x140086774  lea     rcx, aVidhandlerpmsr; "VidHandlerpMsrAddressRegisterEntry"
0x14008677b  call    VidTraceErrorStatusInternal0
0x140086780  lea     rdx, [rsi+0A0h]
0x140086787  mov     rcx, rbp
0x14008678a  call    cs:__imp_RtlRbRemoveNode
0x140086791  nop     dword ptr [rax+rax+00h]
0x140086796  jmp     short loc_1400867A9
0x140086798  mov     rax, [rdi+5F8h]
0x14008679f  lock inc qword ptr [rax+1F8h]
0x1400867a7  xor     ebx, ebx
0x1400867a9  mov     eax, ebx
0x1400867ab  mov     rcx, [rsp+58h+var_28]
0x1400867b0  xor     rcx, rsp; StackCookie
0x1400867b3  call    __security_check_cookie
0x1400867b8  mov     rbx, [rsp+58h+arg_18]
0x1400867bd  add     rsp, 40h
0x1400867c1  pop     rdi
0x1400867c2  pop     rsi
0x1400867c3  pop     rbp
0x1400867c4  retn
```
