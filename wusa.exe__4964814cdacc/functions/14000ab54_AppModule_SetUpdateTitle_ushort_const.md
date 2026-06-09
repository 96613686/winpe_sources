# AppModule::SetUpdateTitle(ushort const *)

- ea: `0x14000ab54`
- end: `0x14000ac60`
- name: `?SetUpdateTitle@AppModule@@QEAAJPEBG@Z`
- size: `268`
- prototype: `__int64 __fastcall(AppModule *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1400075b0`
- `0x14000afc0`

## callees

- `0x140001258`
- `0x140001264`
- `0x1400044e0`
- `0x14000ab54`
- `0x140013490`

## string_xrefs

- `0x14000abdf`: `AppModule::CopyStringWithQuote`
- `0x14000ac19`: `AppModule::CopyStringWithQuote`
- `0x14000ac49`: `AppModule::CopyStringWithQuote`
- `0x14000abd3`: `Failed to allocate temp buffer`
- `0x14000ac0d`: `Failed to copy string`

## pseudocode

```c
__int64 __fastcall AppModule::SetUpdateTitle(AppModule *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  __int64 *v9; // rdi

  if ( !a2 )
  {
    v5 = -2147024809;
LABEL_12:
    WusaLogDebugEventA(L"AppModule::CopyStringWithQuote", 724, "Failed to get source length");
    return v5;
  }
  v3 = a2;
  v4 = 2147483646;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  v5 = v4 == 0 ? 0x80070057 : 0;
  v6 = (2147483646 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    goto LABEL_12;
  v7 = v6 + 3;
  v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 3, 2u));
  v9 = (__int64 *)v8;
  if ( v8 )
  {
    v5 = StringCchPrintfW(v8, v7, L"\"%s\"", a2);
    if ( (v5 & 0x80000000) == 0 )
    {
      off_1400201D8 = v9;
    }
    else
    {
      WusaLogDebugEventA(L"AppModule::CopyStringWithQuote", 730, "Failed to copy string");
      operator delete(v9);
    }
  }
  else
  {
    WusaLogDebugEventA(L"AppModule::CopyStringWithQuote", 727, "Failed to allocate temp buffer");
    return (unsigned int)-2147024882;
  }
  return v5;
}

```

## disassembly

```asm
0x14000ab54  push    rbx
0x14000ab56  push    rbp
0x14000ab57  push    rsi
0x14000ab58  push    rdi
0x14000ab59  sub     rsp, 28h
0x14000ab5d  xor     ebp, ebp
0x14000ab5f  mov     rsi, rdx
0x14000ab62  test    rdx, rdx
0x14000ab65  jz      loc_14000AC38
0x14000ab6b  mov     edx, 7FFFFFFEh
0x14000ab70  mov     rax, rsi
0x14000ab73  mov     ecx, edx
0x14000ab75  cmp     [rax], bp
0x14000ab78  jz      short loc_14000AB84
0x14000ab7a  add     rax, 2
0x14000ab7e  sub     rcx, 1
0x14000ab82  jnz     short loc_14000AB75
0x14000ab84  mov     rax, rcx
0x14000ab87  neg     rax
0x14000ab8a  mov     rax, rcx
0x14000ab8d  sbb     ebx, ebx
0x14000ab8f  sub     rdx, rcx
0x14000ab92  not     ebx
0x14000ab94  and     ebx, 80070057h
0x14000ab9a  neg     rax
0x14000ab9d  sbb     r8, r8
0x14000aba0  and     r8, rdx
0x14000aba3  test    rcx, rcx
0x14000aba6  jz      loc_14000AC3D
0x14000abac  lea     rbx, [r8+3]
0x14000abb0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000abb7  mov     eax, 2
0x14000abbc  mul     rbx
0x14000abbf  cmovb   rax, rcx
0x14000abc3  mov     rcx, rax; Size
0x14000abc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000abcb  mov     rdi, rax
0x14000abce  test    rax, rax
0x14000abd1  jnz     short loc_14000ABF2
0x14000abd3  lea     r8, aFailedToAlloca_10; "Failed to allocate temp buffer"
0x14000abda  mov     edx, 2D7h
0x14000abdf  lea     rcx, aAppmoduleCopys; "AppModule::CopyStringWithQuote"
0x14000abe6  call    WusaLogDebugEventA
0x14000abeb  mov     ebx, 8007000Eh
0x14000abf0  jmp     short loc_14000AC55
0x14000abf2  mov     r9, rsi
0x14000abf5  lea     r8, aS_0; "\"%s\""
0x14000abfc  mov     rdx, rbx; unsigned __int64
0x14000abff  mov     rcx, rdi; unsigned __int16 *
0x14000ac02  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000ac07  mov     ebx, eax
0x14000ac09  test    eax, eax
0x14000ac0b  jns     short loc_14000AC2F
0x14000ac0d  lea     r8, aFailedToCopySt; "Failed to copy string"
0x14000ac14  mov     edx, 2DAh
0x14000ac19  lea     rcx, aAppmoduleCopys; "AppModule::CopyStringWithQuote"
0x14000ac20  call    WusaLogDebugEventA
0x14000ac25  mov     rcx, rdi; Block
0x14000ac28  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000ac2d  jmp     short loc_14000AC55
0x14000ac2f  mov     cs:off_1400201D8, rdi
0x14000ac36  jmp     short loc_14000AC55
0x14000ac38  mov     ebx, 80070057h
0x14000ac3d  lea     r8, aFailedToGetSou; "Failed to get source length"
0x14000ac44  mov     edx, 2D4h
0x14000ac49  lea     rcx, aAppmoduleCopys; "AppModule::CopyStringWithQuote"
0x14000ac50  call    WusaLogDebugEventA
0x14000ac55  mov     eax, ebx
0x14000ac57  add     rsp, 28h
0x14000ac5b  pop     rdi
0x14000ac5c  pop     rsi
0x14000ac5d  pop     rbp
0x14000ac5e  pop     rbx
0x14000ac5f  retn
```
