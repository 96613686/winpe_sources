# VidVpIoctlStateGet

- ea: `0x1400f76fc`
- end: `0x1400f7956`
- name: `VidVpIoctlStateGet`
- size: `602`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, char *, unsigned __int8, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140031fa4`

## callees

- `0x1400116c8`
- `0x140012b3c`
- `0x140021650`
- `0x140034554`
- `0x140034584`
- `0x140078f20`
- `0x1400f76fc`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400f77df`
- `ntoskrnl!ProbeForWrite` at `0x1400f77df`
- `ntoskrnl!ProbeForRead` at `0x1400f77c1`
- `ntoskrnl!ProbeForRead` at `0x1400f77c1`
- `winhvr!WinHvGetVpRegisters` at `0x1400f785b`
- `winhvr!WinHvGetVpRegisters` at `0x1400f785b`

## pseudocode

```c
__int64 __fastcall VidVpIoctlStateGet(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        char *a4,
        unsigned __int8 a5,
        char *a6)
{
  char v7; // bl
  unsigned __int8 v9; // r15
  int VpRegisters; // edi
  unsigned int v11; // eax
  unsigned __int8 v12; // r12
  __int64 v13; // r8
  char v15; // [rsp+40h] [rbp-308h]
  char *Address; // [rsp+48h] [rbp-300h]
  char *Src; // [rsp+50h] [rbp-2F8h]
  size_t v19; // [rsp+58h] [rbp-2F0h]
  __int64 v20; // [rsp+68h] [rbp-2E0h] BYREF
  size_t v21; // [rsp+70h] [rbp-2D8h]
  _BYTE v22[128]; // [rsp+80h] [rbp-2C8h] BYREF
  _BYTE v23[512]; // [rsp+100h] [rbp-248h] BYREF

  Src = a4;
  v7 = a3;
  Address = a6;
  v20 = 0;
  v15 = 0;
  v9 = a5;
  if ( (unsigned __int8)(a5 - 1) > 0x7Fu || a3 >= 0x800 || (a3 & 0x700) != 0 )
  {
    VpRegisters = -1073741811;
  }
  else
  {
    VidObjectLockAcquireShared();
    v15 = 1;
    VpRegisters = -1073741811;
    v11 = *(_DWORD *)(a1 + 3200);
    if ( v11 <= 0x800 && a2 < v11 )
      VpRegisters = 0;
    if ( VpRegisters >= 0 )
    {
      ProbeForRead(a4, 4LL * a5, 1u);
      ProbeForWrite(a6, 16LL * a5, 1u);
      do
      {
        v12 = 32;
        if ( v9 < 0x20u )
          v12 = v9;
        v21 = 4LL * v12;
        RtlCopyFromUser(v22, Src, v21);
        LOBYTE(v13) = v7;
        VpRegisters = WinHvGetVpRegisters(*(_QWORD *)(a1 + 648), a2, v13, v12, v22, &v20, v23);
        if ( VpRegisters < 0 )
          break;
        v19 = 16LL * v12;
        RtlCopyToUser(Address, v23, v19);
        Src += v21;
        Address += v19;
        v9 -= v12;
      }
      while ( v9 );
    }
  }
  if ( v15 )
    VidObjectLockRelease(a1);
  return (unsigned int)VpRegisters;
}

```

## disassembly

```asm
0x1400f76fc  push    rbx
0x1400f76fe  push    rsi
0x1400f76ff  push    rdi
0x1400f7700  push    r12
0x1400f7702  push    r13
0x1400f7704  push    r14
0x1400f7706  push    r15
0x1400f7708  sub     rsp, 310h
0x1400f770f  mov     rax, cs:__security_cookie
0x1400f7716  xor     rax, rsp
0x1400f7719  mov     [rsp+348h+var_48], rax
0x1400f7721  mov     r12, r9
0x1400f7724  mov     [rsp+348h+Src], r9
0x1400f7729  mov     ebx, r8d
0x1400f772c  mov     [rsp+348h+var_304], edx
0x1400f7730  mov     r14, rcx
0x1400f7733  mov     [rsp+348h+var_2E8], rcx
0x1400f7738  mov     rax, [rsp+348h+arg_28]
0x1400f7740  mov     [rsp+348h+Address], rax
0x1400f7745  xor     esi, esi
0x1400f7747  mov     r13b, sil
0x1400f774a  mov     [rsp+348h+var_2E0], rsi
0x1400f774f  mov     [rsp+348h+var_308], sil
0x1400f7754  movzx   r15d, [rsp+348h+arg_20]
0x1400f775d  lea     eax, [r15-1]
0x1400f7761  cmp     al, 7Fh
0x1400f7763  ja      loc_1400F78DF
0x1400f7769  cmp     ebx, 800h
0x1400f776f  jnb     loc_1400F78DF
0x1400f7775  test    ebx, 700h
0x1400f777b  jnz     loc_1400F78DF
0x1400f7781  call    VidObjectLockAcquireShared
0x1400f7786  mov     [rsp+348h+var_308], 1
0x1400f778b  mov     edi, 0C000000Dh
0x1400f7790  mov     eax, [r14+0C80h]
0x1400f7797  cmp     eax, 800h
0x1400f779c  ja      short loc_1400F77A5
0x1400f779e  cmp     [rsp+348h+var_304], eax
0x1400f77a2  cmovb   edi, esi
0x1400f77a5  test    edi, edi
0x1400f77a7  js      loc_1400F78E4
0x1400f77ad  mov     rdi, r15
0x1400f77b0  lea     rdx, ds:0[r15*4]; Length
0x1400f77b8  mov     r8d, 1; Alignment
0x1400f77be  mov     rcx, r12; Address
0x1400f77c1  call    cs:__imp_ProbeForRead
0x1400f77c8  nop     dword ptr [rax+rax+00h]
0x1400f77cd  shl     rdi, 4
0x1400f77d1  mov     r8d, 1; Alignment
0x1400f77d7  mov     rdx, rdi; Length
0x1400f77da  mov     rcx, [rsp+348h+Address]; Address
0x1400f77df  call    cs:__imp_ProbeForWrite
0x1400f77e6  nop     dword ptr [rax+rax+00h]
0x1400f77eb  nop
0x1400f77ec  mov     r12d, 20h ; ' '
0x1400f77f2  movzx   eax, r15b
0x1400f77f6  cmp     r15b, r12b
0x1400f77f9  cmovb   r12d, eax
0x1400f77fd  movzx   eax, r12b
0x1400f7801  mov     [rsp+348h+var_2F0], rax
0x1400f7806  shl     rax, 2
0x1400f780a  mov     [rsp+348h+var_2D8], rax
0x1400f780f  mov     r8, rax; Size
0x1400f7812  mov     rdx, [rsp+348h+Src]; Src
0x1400f7817  lea     rcx, [rsp+348h+var_2C8]; void *
0x1400f781f  call    RtlCopyFromUser
0x1400f7824  nop
0x1400f7825  movzx   r9d, r12b
0x1400f7829  lea     rax, [rsp+348h+var_248]
0x1400f7831  mov     [rsp+348h+var_318], rax
0x1400f7836  lea     rax, [rsp+348h+var_2E0]
0x1400f783b  mov     [rsp+348h+var_320], rax
0x1400f7840  lea     rax, [rsp+348h+var_2C8]
0x1400f7848  mov     [rsp+348h+var_328], rax
0x1400f784d  mov     r8b, bl
0x1400f7850  mov     edx, [rsp+348h+var_304]
0x1400f7854  mov     rcx, [r14+288h]
0x1400f785b  call    cs:__imp_WinHvGetVpRegisters
0x1400f7862  nop     dword ptr [rax+rax+00h]
0x1400f7867  mov     edi, eax
0x1400f7869  test    eax, eax
0x1400f786b  js      short loc_1400F78E4
0x1400f786d  mov     rax, [rsp+348h+var_2F0]
0x1400f7872  shl     rax, 4
0x1400f7876  mov     [rsp+348h+var_2F0], rax
0x1400f787b  mov     r8, rax; Size
0x1400f787e  lea     rdx, [rsp+348h+var_248]; Src
0x1400f7886  mov     rcx, [rsp+348h+Address]; void *
0x1400f788b  call    RtlCopyToUser
0x1400f7890  nop
0x1400f7891  mov     rax, [rsp+348h+Src]
0x1400f7896  add     rax, [rsp+348h+var_2D8]
0x1400f789b  mov     [rsp+348h+Src], rax
0x1400f78a0  mov     rax, [rsp+348h+var_2F0]
0x1400f78a5  add     [rsp+348h+Address], rax
0x1400f78aa  sub     r15b, r12b
0x1400f78ad  jnz     loc_1400F77EC
0x1400f78b3  jmp     short loc_1400F78E4
0x1400f78b5  mov     edi, eax
0x1400f78b7  mov     r13b, 1
0x1400f78ba  xor     esi, esi
0x1400f78bc  mov     r14, [rsp+348h+var_2E8]
0x1400f78c1  jmp     short loc_1400F78E4
0x1400f78c3  mov     edi, eax
0x1400f78c5  mov     r13b, 1
0x1400f78c8  xor     esi, esi
0x1400f78ca  mov     r14, [rsp+348h+var_2E8]
0x1400f78cf  jmp     short loc_1400F78E4
0x1400f78d1  mov     edi, eax
0x1400f78d3  mov     r13b, 1
0x1400f78d6  xor     esi, esi
0x1400f78d8  mov     r14, [rsp+348h+var_2E8]
0x1400f78dd  jmp     short loc_1400F78E4
0x1400f78df  mov     edi, 0C000000Dh
0x1400f78e4  cmp     [rsp+348h+var_308], sil
0x1400f78e9  jz      short loc_1400F78F3
0x1400f78eb  mov     rcx, r14
0x1400f78ee  call    VidObjectLockRelease
0x1400f78f3  test    r13b, r13b
0x1400f78f6  jz      short loc_1400F7930
0x1400f78f8  lea     rax, WPP_GLOBAL_Control
0x1400f78ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f7906  cmp     rcx, rax
0x1400f7909  jz      short loc_1400F7930
0x1400f790b  mov     eax, [rcx+2Ch]
0x1400f790e  test    al, 2
0x1400f7910  jz      short loc_1400F7930
0x1400f7912  cmp     byte ptr [rcx+29h], 2
0x1400f7916  jb      short loc_1400F7930
0x1400f7918  mov     edx, 0Ch
0x1400f791d  mov     r9d, edi
0x1400f7920  lea     r8, WPP_d1d52df2f618343a97df75412feab325_Traceguids
0x1400f7927  mov     rcx, [rcx+18h]
0x1400f792b  call    WPP_SF_d
0x1400f7930  mov     eax, edi
0x1400f7932  mov     rcx, [rsp+348h+var_48]
0x1400f793a  xor     rcx, rsp; StackCookie
0x1400f793d  call    __security_check_cookie
0x1400f7942  add     rsp, 310h
0x1400f7949  pop     r15
0x1400f794b  pop     r14
0x1400f794d  pop     r13
0x1400f794f  pop     r12
0x1400f7951  pop     rdi
0x1400f7952  pop     rsi
0x1400f7953  pop     rbx
0x1400f7954  retn
```
