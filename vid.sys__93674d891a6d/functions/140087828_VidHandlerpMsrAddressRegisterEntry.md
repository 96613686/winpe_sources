# VidHandlerpMsrAddressRegisterEntry

- ea: `0x140087828`
- end: `0x140087946`
- name: `VidHandlerpMsrAddressRegisterEntry`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x140086fb0`

## callees

- `0x140021c60`
- `0x14002f724`
- `0x140074df4`
- `0x140087828`
- `0x1400b3210`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14008790a`
- `ntoskrnl!RtlRbRemoveNode` at `0x14008790a`
- `winhvr!WinHvInstallIntercept` at `0x1400878d2`
- `winhvr!WinHvInstallIntercept` at `0x1400878d2`

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
          v8,
          (unsigned int)v7);
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
    3676,
    3224829953LL);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140087828  mov     [rsp+arg_18], rbx
0x14008782d  push    rbp
0x14008782e  push    rsi
0x14008782f  push    rdi
0x140087830  sub     rsp, 40h
0x140087834  mov     rax, cs:__security_cookie
0x14008783b  xor     rax, rsp
0x14008783e  mov     [rsp+58h+var_28], rax
0x140087843  xor     eax, eax
0x140087845  lea     rbp, [rcx+0D60h]
0x14008784c  mov     rdi, rcx
0x14008784f  mov     qword ptr [rsp+58h+var_34], rax
0x140087854  mov     rcx, rbp
0x140087857  mov     [rsp+20h], rax
0x14008785c  mov     rbx, r8
0x14008785f  mov     rsi, rdx
0x140087862  call    VidHandlerTableInsert
0x140087867  test    al, al
0x140087869  jnz     short loc_140087891
0x14008786b  mov     ebx, 0C0370001h
0x140087870  mov     r9d, ebx
0x140087873  lea     rdx, aOnecoreVmVidSy_14; "onecore\\vm\\vid\\sys\\driver\\vidhandl"...
0x14008787a  mov     r8d, 0E5Ch
0x140087880  lea     rcx, aVidhandlerpmsr; "VidHandlerpMsrAddressRegisterEntry"
0x140087887  call    VidTraceErrorStatusInternal0
0x14008788c  jmp     loc_140087929
0x140087891  test    rbx, rbx
0x140087894  jz      short loc_1400878B2
0x140087896  mov     r8, rbx
0x140087899  mov     rdx, rsi
0x14008789c  mov     rcx, rdi
0x14008789f  call    VsmmPhuStoreHandlerRestore
0x1400878a4  mov     ebx, eax
0x1400878a6  test    eax, eax
0x1400878a8  jns     short loc_140087918
0x1400878aa  mov     r8d, 0E68h
0x1400878b0  jmp     short loc_1400878EA
0x1400878b2  mov     eax, [rsi+78h]
0x1400878b5  lea     r8, [rsp+58h+var_38]
0x1400878ba  mov     rcx, [rdi+288h]
0x1400878c1  mov     edx, 3
0x1400878c6  mov     [rsp+58h+var_34+4], eax
0x1400878ca  mov     [rsp+58h+var_38], 0Ch
0x1400878d2  call    cs:__imp_WinHvInstallIntercept
0x1400878d9  nop     dword ptr [rax+rax+00h]
0x1400878de  mov     ebx, eax
0x1400878e0  test    eax, eax
0x1400878e2  jns     short loc_140087918
0x1400878e4  mov     r8d, 0E7Bh
0x1400878ea  mov     r9d, ebx
0x1400878ed  lea     rdx, aOnecoreVmVidSy_14; "onecore\\vm\\vid\\sys\\driver\\vidhandl"...
0x1400878f4  lea     rcx, aVidhandlerpmsr; "VidHandlerpMsrAddressRegisterEntry"
0x1400878fb  call    VidTraceErrorStatusInternal0
0x140087900  lea     rdx, [rsi+0A0h]
0x140087907  mov     rcx, rbp
0x14008790a  call    cs:__imp_RtlRbRemoveNode
0x140087911  nop     dword ptr [rax+rax+00h]
0x140087916  jmp     short loc_140087929
0x140087918  mov     rax, [rdi+5F8h]
0x14008791f  lock inc qword ptr [rax+1F8h]
0x140087927  xor     ebx, ebx
0x140087929  mov     eax, ebx
0x14008792b  mov     rcx, [rsp+58h+var_28]
0x140087930  xor     rcx, rsp; StackCookie
0x140087933  call    __security_check_cookie
0x140087938  mov     rbx, [rsp+58h+arg_18]
0x14008793d  add     rsp, 40h
0x140087941  pop     rdi
0x140087942  pop     rsi
0x140087943  pop     rbp
0x140087944  retn
```
