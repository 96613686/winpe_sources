# SqospUpdateClientPolicy

- ea: `0x140006424`
- end: `0x140006666`
- name: `SqospUpdateClientPolicy`
- size: `578`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140014d10`

## callees

- `0x140003a10`
- `0x140003ec0`
- `0x140005de4`
- `0x140006424`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000664e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000664e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140006483`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400064e4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140006483`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400064e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000643b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000643b`

## pseudocode

```c
__int64 __fastcall SqospUpdateClientPolicy(PKSPIN_LOCK SpinLock, __int64 a2)
{
  USHORT v4; // dx
  WCHAR *v5; // rax
  struct _UNICODE_STRING *v6; // rcx
  int v7; // esi
  USHORT v8; // dx
  WCHAR *v9; // rax
  struct _UNICODE_STRING *v10; // rcx
  char v11; // r9
  __int64 v12; // rax
  KSPIN_LOCK v13; // rax
  KSPIN_LOCK *v14; // rcx
  PKSPIN_LOCK v15; // rdx
  KSPIN_LOCK v16; // r8
  __int64 v17; // rax
  KSPIN_LOCK v18; // rax
  KSPIN_LOCK v19; // rcx
  __int128 v20; // xmm0
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-38h] BYREF

  SourceString = 0;
  *((_BYTE *)SpinLock + 8) = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v4 = *(_WORD *)(a2 + 74);
  if ( v4 )
  {
    v5 = (WCHAR *)(a2 + *(unsigned __int16 *)(a2 + 72));
    SourceString.Length = *(_WORD *)(a2 + 74);
    v6 = (struct _UNICODE_STRING *)(SpinLock + 21);
    SourceString.Buffer = v5;
    SourceString.MaximumLength = v4;
    if ( *((_WORD *)SpinLock + 85) < v4 )
    {
      SqospFreeUnicodeString(v6);
      v7 = SqospCopyUnicodeString((PUNICODE_STRING)(SpinLock + 21), &SourceString);
      if ( v7 < 0 )
        goto LABEL_33;
    }
    else
    {
      RtlCopyUnicodeString(v6, &SourceString);
    }
  }
  v8 = *(_WORD *)(a2 + 78);
  if ( v8 )
  {
    v9 = (WCHAR *)(a2 + *(unsigned __int16 *)(a2 + 76));
    SourceString.Length = *(_WORD *)(a2 + 78);
    v10 = (struct _UNICODE_STRING *)(SpinLock + 23);
    SourceString.Buffer = v9;
    SourceString.MaximumLength = v8;
    if ( *((_WORD *)SpinLock + 93) < v8 )
    {
      SqospFreeUnicodeString(v10);
      v7 = SqospCopyUnicodeString((PUNICODE_STRING)(SpinLock + 23), &SourceString);
      if ( v7 < 0 )
        goto LABEL_33;
    }
    else
    {
      RtlCopyUnicodeString(v10, &SourceString);
    }
  }
  v11 = 1;
  v7 = 0;
  *(_OWORD *)(SpinLock + 19) = *(_OWORD *)(a2 + 40);
  *((_BYTE *)SpinLock + 126) = (*(_DWORD *)(a2 + 4) & 0x20000000) != 0;
  v12 = *(_QWORD *)(a2 + 24);
  if ( !v12 )
    v12 = *(_QWORD *)(a2 + 32);
  if ( v12 )
  {
    v19 = *(_QWORD *)(a2 + 24) - SpinLock[17];
    if ( !v19 )
      v19 = *(_QWORD *)(a2 + 32) - SpinLock[18];
    if ( v19 )
    {
      *((_DWORD *)SpinLock + 33) = 2;
      v20 = *(_OWORD *)(a2 + 24);
      SpinLock[26] = 0;
      SpinLock[25] = 0;
      *(_OWORD *)(SpinLock + 17) = v20;
      SpinLock[27] = 0;
LABEL_32:
      SqospAssignClientIoRates(SpinLock);
    }
  }
  else
  {
    v13 = SpinLock[17];
    if ( !v13 )
      v13 = SpinLock[18];
    v14 = (KSPIN_LOCK *)(a2 + 56);
    v15 = SpinLock + 26;
    if ( !v13
      && *v15 == *v14
      && (v16 = SpinLock[25], v16 == *(_QWORD *)(a2 + 64))
      && (*(_WORD *)a2 < 0x101u ? (v17 = 0) : (v17 = *(_QWORD *)(a2 + 112)), SpinLock[27] == v17) )
    {
      v11 = 0;
    }
    else
    {
      *(_OWORD *)(SpinLock + 17) = *(_OWORD *)(a2 + 24);
      *v15 = *v14;
      v16 = *(_QWORD *)(a2 + 64);
      SpinLock[25] = v16;
      if ( *(_WORD *)a2 < 0x101u )
        v18 = 0;
      else
        v18 = *(_QWORD *)(a2 + 112);
      SpinLock[27] = v18;
    }
    *((_DWORD *)SpinLock + 33) = v16 != 0;
    if ( v11 )
      goto LABEL_32;
  }
LABEL_33:
  KeReleaseSpinLock(SpinLock, *((_BYTE *)SpinLock + 8));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140006424  push    rbx
0x140006426  push    rbp
0x140006427  push    rsi
0x140006428  push    rdi
0x140006429  sub     rsp, 38h
0x14000642d  xorps   xmm0, xmm0
0x140006430  mov     rdi, rdx
0x140006433  movups  xmmword ptr [rsp+58h+SourceString.Length], xmm0
0x140006438  mov     rbx, rcx
0x14000643b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006442  nop     dword ptr [rax+rax+00h]
0x140006447  mov     [rbx+8], al
0x14000644a  xor     ebp, ebp
0x14000644c  movzx   edx, word ptr [rdi+4Ah]
0x140006450  test    dx, dx
0x140006453  jz      short loc_1400064AD
0x140006455  movzx   eax, word ptr [rdi+48h]
0x140006459  lea     rsi, [rbx+0A8h]
0x140006460  add     rax, rdi
0x140006463  mov     [rsp+58h+SourceString.Length], dx
0x140006468  mov     rcx, rsi; DestinationString
0x14000646b  mov     [rsp+58h+SourceString.Buffer], rax
0x140006470  mov     [rsp+58h+SourceString.MaximumLength], dx
0x140006475  cmp     [rbx+0AAh], dx
0x14000647c  jb      short loc_140006491
0x14000647e  lea     rdx, [rsp+58h+SourceString]; SourceString
0x140006483  call    cs:__imp_RtlCopyUnicodeString
0x14000648a  nop     dword ptr [rax+rax+00h]
0x14000648f  jmp     short loc_1400064AD
0x140006491  call    SqospFreeUnicodeString
0x140006496  lea     rdx, [rsp+58h+SourceString]; SourceString
0x14000649b  mov     rcx, rsi; DestinationString
0x14000649e  call    SqospCopyUnicodeString
0x1400064a3  mov     esi, eax
0x1400064a5  test    eax, eax
0x1400064a7  js      loc_140006648
0x1400064ad  movzx   edx, word ptr [rdi+4Eh]
0x1400064b1  test    dx, dx
0x1400064b4  jz      short loc_14000650E
0x1400064b6  movzx   eax, word ptr [rdi+4Ch]
0x1400064ba  lea     rsi, [rbx+0B8h]
0x1400064c1  add     rax, rdi
0x1400064c4  mov     [rsp+58h+SourceString.Length], dx
0x1400064c9  mov     rcx, rsi; DestinationString
0x1400064cc  mov     [rsp+58h+SourceString.Buffer], rax
0x1400064d1  mov     [rsp+58h+SourceString.MaximumLength], dx
0x1400064d6  cmp     [rbx+0BAh], dx
0x1400064dd  jb      short loc_1400064F2
0x1400064df  lea     rdx, [rsp+58h+SourceString]; SourceString
0x1400064e4  call    cs:__imp_RtlCopyUnicodeString
0x1400064eb  nop     dword ptr [rax+rax+00h]
0x1400064f0  jmp     short loc_14000650E
0x1400064f2  call    SqospFreeUnicodeString
0x1400064f7  lea     rdx, [rsp+58h+SourceString]; SourceString
0x1400064fc  mov     rcx, rsi; DestinationString
0x1400064ff  call    SqospCopyUnicodeString
0x140006504  mov     esi, eax
0x140006506  test    eax, eax
0x140006508  js      loc_140006648
0x14000650e  movups  xmm0, xmmword ptr [rdi+28h]
0x140006512  mov     r9b, 1
0x140006515  mov     esi, ebp
0x140006517  movdqu  xmmword ptr [rbx+98h], xmm0
0x14000651f  mov     eax, [rdi+4]
0x140006522  shr     eax, 1Dh
0x140006525  and     al, r9b
0x140006528  mov     [rbx+7Eh], al
0x14000652b  mov     rax, [rdi+18h]
0x14000652f  mov     rdx, cs:qword_14000B3C0
0x140006536  mov     rcx, cs:qword_14000B3C8
0x14000653d  sub     rax, rdx
0x140006540  jnz     short loc_140006549
0x140006542  mov     rax, [rdi+20h]
0x140006546  sub     rax, rcx
0x140006549  test    rax, rax
0x14000654c  jnz     loc_1400065F8
0x140006552  mov     rax, [rbx+88h]
0x140006559  sub     rax, rdx
0x14000655c  jnz     short loc_140006568
0x14000655e  mov     rax, [rbx+90h]
0x140006565  sub     rax, rcx
0x140006568  lea     rcx, [rdi+38h]
0x14000656c  mov     r10d, 101h
0x140006572  lea     rdx, [rbx+0D0h]
0x140006579  test    rax, rax
0x14000657c  jnz     short loc_1400065B0
0x14000657e  mov     rax, [rcx]
0x140006581  cmp     [rdx], rax
0x140006584  jnz     short loc_1400065B0
0x140006586  mov     r8, [rbx+0C8h]
0x14000658d  cmp     r8, [rdi+40h]
0x140006591  jnz     short loc_1400065B0
0x140006593  cmp     [rdi], r10w
0x140006597  jb      short loc_14000659F
0x140006599  mov     rax, [rdi+70h]
0x14000659d  jmp     short loc_1400065A2
0x14000659f  mov     rax, rbp
0x1400065a2  cmp     [rbx+0D8h], rax
0x1400065a9  jnz     short loc_1400065B0
0x1400065ab  mov     r9b, bpl
0x1400065ae  jmp     short loc_1400065E3
0x1400065b0  movups  xmm0, xmmword ptr [rdi+18h]
0x1400065b4  movdqu  xmmword ptr [rbx+88h], xmm0
0x1400065bc  mov     rax, [rcx]
0x1400065bf  mov     [rdx], rax
0x1400065c2  mov     r8, [rdi+40h]
0x1400065c6  mov     [rbx+0C8h], r8
0x1400065cd  cmp     [rdi], r10w
0x1400065d1  jb      short loc_1400065D9
0x1400065d3  mov     rax, [rdi+70h]
0x1400065d7  jmp     short loc_1400065DC
0x1400065d9  mov     rax, rbp
0x1400065dc  mov     [rbx+0D8h], rax
0x1400065e3  test    r8, r8
0x1400065e6  mov     eax, ebp
0x1400065e8  setnz   al
0x1400065eb  mov     [rbx+84h], eax
0x1400065f1  test    r9b, r9b
0x1400065f4  jz      short loc_140006648
0x1400065f6  jmp     short loc_140006640
0x1400065f8  mov     rcx, [rdi+18h]
0x1400065fc  sub     rcx, [rbx+88h]
0x140006603  jnz     short loc_140006610
0x140006605  mov     rcx, [rdi+20h]
0x140006609  sub     rcx, [rbx+90h]
0x140006610  test    rcx, rcx
0x140006613  jz      short loc_140006648
0x140006615  mov     dword ptr [rbx+84h], 2
0x14000661f  movups  xmm0, xmmword ptr [rdi+18h]
0x140006623  mov     [rbx+0D0h], rbp
0x14000662a  mov     [rbx+0C8h], rbp
0x140006631  movdqu  xmmword ptr [rbx+88h], xmm0
0x140006639  mov     [rbx+0D8h], rbp
0x140006640  mov     rcx, rbx
0x140006643  call    SqospAssignClientIoRates
0x140006648  mov     dl, [rbx+8]; NewIrql
0x14000664b  mov     rcx, rbx; SpinLock
0x14000664e  call    cs:__imp_KeReleaseSpinLock
0x140006655  nop     dword ptr [rax+rax+00h]
0x14000665a  mov     eax, esi
0x14000665c  add     rsp, 38h
0x140006660  pop     rdi
0x140006661  pop     rsi
0x140006662  pop     rbp
0x140006663  pop     rbx
0x140006664  retn
```
