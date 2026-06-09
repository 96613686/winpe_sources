# VsmmCryptGetSecurityCookie

- ea: `0x1400777d0`
- end: `0x140077a41`
- name: `VsmmCryptGetSecurityCookie`
- size: `625`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140035698`

## callees

- `0x140038630`
- `0x1400777d0`
- `0x140099e18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14007780d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007780d`
- `ntoskrnl!VslRetrieveMailbox` at `0x140077889`
- `ntoskrnl!VslRetrieveMailbox` at `0x140077906`
- `ntoskrnl!VslRetrieveMailbox` at `0x140077889`
- `ntoskrnl!VslRetrieveMailbox` at `0x140077906`

## string_xrefs

- `0x140077830`: `VsmmCryptGetSecurityCookie`
- `0x140077859`: `VsmmCryptGetSecurityCookie`
- `0x1400778a8`: `VsmmCryptGetSecurityCookie`
- `0x1400778d1`: `VsmmCryptGetSecurityCookie`
- `0x140077925`: `VsmmCryptGetSecurityCookie`
- `0x14007794e`: `VsmmCryptGetSecurityCookie`
- `0x140077991`: `VsmmCryptGetSecurityCookie`
- `0x1400779c3`: `VsmmCryptGetSecurityCookie`
- `0x1400779fb`: `VsmmCryptGetSecurityCookie`

## pseudocode

```c
__int64 __fastcall VsmmCryptGetSecurityCookie(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+80h] [rbp+40h] BYREF
  __int64 v16; // [rsp+88h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(a1 + 10240);
  v3 = 8;
  v16 = 8;
  v13 = 8;
  v14 = 0;
  v15 = 0;
  if ( v2 == PsGetCurrentProcess() )
  {
    if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
    {
      v7 = -1073740008;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2731);
      goto LABEL_27;
    }
    LOBYTE(v6) = 2;
    v7 = VslRetrieveMailbox(2, a1 + 9816, v6, &v14, &v16);
    if ( v7 < 0 )
    {
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2746);
      goto LABEL_27;
    }
    if ( v16 != 8 )
    {
      v7 = -1073741788;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2753);
      goto LABEL_27;
    }
    v9 = v14;
    if ( (v14 & 1) == 0 )
    {
      v10 = *(_QWORD *)(a1 + 40) | 8LL;
LABEL_26:
      *(_QWORD *)(a1 + 40) = v10 | 1;
      v7 = 0;
      *a2 = v9;
      goto LABEL_27;
    }
    LOBYTE(v8) = 1;
    v7 = VslRetrieveMailbox(2, a1 + 9816, v8, &v15, &v13);
    if ( v7 < 0 )
    {
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2770);
      goto LABEL_27;
    }
    if ( v13 != 8 )
    {
      v7 = -1073741788;
      VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2776);
      goto LABEL_27;
    }
    if ( v15 == 0x736869656C646700LL )
    {
      if ( (*(_BYTE *)(a1 + 40) & 4) == 0 )
      {
LABEL_21:
        v10 = *(_QWORD *)(a1 + 40);
        if ( (v10 & 2) != 0 )
          v10 |= 8uLL;
        v9 = v14;
        goto LABEL_26;
      }
    }
    else
    {
      if ( v15 != 0x736869656C646701LL )
      {
        v7 = -1073741790;
        VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2783);
        goto LABEL_27;
      }
      if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
      {
        if ( !(unsigned int)VidCurrentProcessIsTrusted(a1) )
        {
          v7 = -1073741790;
          VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2812);
          goto LABEL_27;
        }
        goto LABEL_21;
      }
    }
    v7 = -1073741790;
    VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2797);
    goto LABEL_27;
  }
  v7 = -1073741790;
  VidTraceErrorInternal0("VsmmCryptGetSecurityCookie", "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt.c", 2721);
LABEL_27:
  v11 = &v14;
  do
  {
    *(_BYTE *)v11 = 0;
    v11 = (__int64 *)((char *)v11 + 1);
    --v3;
  }
  while ( v3 );
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400777d0  mov     [rsp-28h+arg_8], rbx
0x1400777d5  push    rbp
0x1400777d6  push    rsi
0x1400777d7  push    rdi
0x1400777d8  push    r14
0x1400777da  push    r15
0x1400777dc  mov     rbp, rsp
0x1400777df  sub     rsp, 40h
0x1400777e3  mov     rbx, [rcx+2800h]
0x1400777ea  mov     esi, 8
0x1400777ef  mov     [rbp+arg_18], rsi
0x1400777f3  mov     r15, rdx
0x1400777f6  mov     [rbp+var_10], rsi
0x1400777fa  mov     rdi, rcx
0x1400777fd  mov     [rbp+arg_0], 0
0x140077805  mov     [rbp+arg_10], 0
0x14007780d  call    cs:__imp_PsGetCurrentProcess
0x140077814  nop     dword ptr [rax+rax+00h]
0x140077819  cmp     rbx, rax
0x14007781c  jz      short loc_140077841
0x14007781e  mov     ebx, 0C0000022h
0x140077823  mov     r8d, 0AA1h
0x140077829  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077830  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140077837  call    VidTraceErrorInternal0
0x14007783c  jmp     loc_140077A1D
0x140077841  test    byte ptr [rdi+28h], 1
0x140077845  jz      short loc_14007786A
0x140077847  mov     ebx, 0C0000718h
0x14007784c  mov     r8d, 0AABh
0x140077852  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077859  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140077860  call    VidTraceErrorInternal0
0x140077865  jmp     loc_140077A1D
0x14007786a  lea     rax, [rbp+arg_18]
0x14007786e  mov     r8b, 2
0x140077871  lea     r14, [rdi+2658h]
0x140077878  mov     [rsp+40h+var_20], rax
0x14007787d  mov     rdx, r14
0x140077880  lea     r9, [rbp+arg_0]
0x140077884  mov     ecx, 2
0x140077889  call    cs:__imp_VslRetrieveMailbox
0x140077890  nop     dword ptr [rax+rax+00h]
0x140077895  mov     ebx, eax
0x140077897  test    eax, eax
0x140077899  jns     short loc_1400778B9
0x14007789b  mov     r8d, 0ABAh
0x1400778a1  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400778a8  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400778af  call    VidTraceErrorInternal0
0x1400778b4  jmp     loc_140077A1D
0x1400778b9  cmp     [rbp+arg_18], rsi
0x1400778bd  jz      short loc_1400778E2
0x1400778bf  mov     ebx, 0C0000024h
0x1400778c4  mov     r8d, 0AC1h
0x1400778ca  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400778d1  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400778d8  call    VidTraceErrorInternal0
0x1400778dd  jmp     loc_140077A1D
0x1400778e2  mov     rax, [rbp+arg_0]
0x1400778e6  test    al, 1
0x1400778e8  jz      loc_140077A09
0x1400778ee  lea     rax, [rbp+var_10]
0x1400778f2  mov     r8b, 1
0x1400778f5  lea     r9, [rbp+arg_10]
0x1400778f9  mov     [rsp+40h+var_20], rax
0x1400778fe  mov     rdx, r14
0x140077901  mov     ecx, 2
0x140077906  call    cs:__imp_VslRetrieveMailbox
0x14007790d  nop     dword ptr [rax+rax+00h]
0x140077912  mov     ebx, eax
0x140077914  test    eax, eax
0x140077916  jns     short loc_140077936
0x140077918  mov     r8d, 0AD2h
0x14007791e  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077925  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x14007792c  call    VidTraceErrorInternal0
0x140077931  jmp     loc_140077A1D
0x140077936  cmp     [rbp+var_10], rsi
0x14007793a  jz      short loc_14007795F
0x14007793c  mov     ebx, 0C0000024h
0x140077941  mov     r8d, 0AD8h
0x140077947  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x14007794e  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140077955  call    VidTraceErrorInternal0
0x14007795a  jmp     loc_140077A1D
0x14007795f  mov     rax, 736869656C646700h
0x140077969  cmp     [rbp+arg_10], rax
0x14007796d  jz      short loc_1400779D1
0x14007796f  mov     rax, 736869656C646701h
0x140077979  cmp     [rbp+arg_10], rax
0x14007797d  jz      short loc_14007799F
0x14007797f  mov     ebx, 0C0000022h
0x140077984  mov     r8d, 0ADFh
0x14007798a  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x140077991  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140077998  call    VidTraceErrorInternal0
0x14007799d  jmp     short loc_140077A1D
0x14007799f  test    byte ptr [rdi+28h], 4
0x1400779a3  jz      short loc_1400779E9
0x1400779a5  mov     rcx, rdi
0x1400779a8  call    VidCurrentProcessIsTrusted
0x1400779ad  test    eax, eax
0x1400779af  jnz     short loc_1400779D7
0x1400779b1  mov     ebx, 0C0000022h
0x1400779b6  mov     r8d, 0AFCh
0x1400779bc  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400779c3  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x1400779ca  call    VidTraceErrorInternal0
0x1400779cf  jmp     short loc_140077A1D
0x1400779d1  test    byte ptr [rdi+28h], 4
0x1400779d5  jnz     short loc_1400779E9
0x1400779d7  mov     rcx, [rdi+28h]
0x1400779db  test    cl, 2
0x1400779de  jz      short loc_1400779E3
0x1400779e0  or      rcx, rsi
0x1400779e3  mov     rax, [rbp+arg_0]
0x1400779e7  jmp     short loc_140077A10
0x1400779e9  mov     ebx, 0C0000022h
0x1400779ee  mov     r8d, 0AEDh
0x1400779f4  lea     rdx, aOnecoreVmVidSy_42; "onecore\\vm\\vid\\sys\\vsmm\\vsmmcrypt."...
0x1400779fb  lea     rcx, aVsmmcryptgetse; "VsmmCryptGetSecurityCookie"
0x140077a02  call    VidTraceErrorInternal0
0x140077a07  jmp     short loc_140077A1D
0x140077a09  mov     rcx, [rdi+28h]
0x140077a0d  or      rcx, rsi
0x140077a10  or      rcx, 1
0x140077a14  mov     [rdi+28h], rcx
0x140077a18  xor     ebx, ebx
0x140077a1a  mov     [r15], rax
0x140077a1d  lea     rax, [rbp+arg_0]
0x140077a21  mov     byte ptr [rax], 0
0x140077a24  inc     rax
0x140077a27  sub     rsi, 1
0x140077a2b  jnz     short loc_140077A21
0x140077a2d  mov     eax, ebx
0x140077a2f  mov     rbx, [rsp+40h+arg_8]
0x140077a34  add     rsp, 40h
0x140077a38  pop     r15
0x140077a3a  pop     r14
0x140077a3c  pop     rdi
0x140077a3d  pop     rsi
0x140077a3e  pop     rbp
0x140077a3f  retn
```
