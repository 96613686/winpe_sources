# XPartVisMakeMdlHostVisible

- ea: `0x140014a40`
- end: `0x140014c3c`
- name: `XPartVisMakeMdlHostVisible`
- size: `508`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400071f0`
- `0x14000f158`
- `0x14000f7e4`
- `0x140014a40`
- `0x14002cbc8`
- `0x14002cee0`

## callees

- `0x14000c8bc`
- `0x140014a40`
- `0x140017540`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014bd1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014bd1`
- `winhv!WinHvModifySparseGpaPageHostVisibility` at `0x140014b4b`
- `winhv!WinHvModifySparseGpaPageHostVisibility` at `0x140014b4b`

## pseudocode

```c
__int64 __fastcall XPartVisMakeMdlHostVisible(__int64 *a1, __int64 a2)
{
  int v2; // esi
  unsigned __int64 v3; // r14
  __int64 v4; // r8
  unsigned int v6; // r13d
  int v7; // edi
  char v8; // r12
  __int64 *i; // rbx
  bool v10; // zf
  __int64 v11; // rdx
  unsigned __int64 v12; // rbp
  __int64 v13; // rcx
  PVOID v14; // rax
  char j; // [rsp+80h] [rbp+18h]
  __int64 v17; // [rsp+88h] [rbp+20h] BYREF

  v2 = a2;
  if ( !dword_140020870 )
    return 3224698886LL;
  v3 = qword_140020868;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 == 1 )
    {
      v6 = 3;
    }
    else
    {
      v4 = (unsigned int)(a2 - 2);
      if ( (unsigned int)v4 >= 2 )
      {
        MicrosoftTelemetryAssertTriggeredArgsKM(a1, a2, v4);
        return 3221225485LL;
      }
      v6 = 0;
    }
  }
  else
  {
    v6 = 1;
    if ( qword_140020868 )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM(a1, 0, (unsigned int)a2);
      return 3221225659LL;
    }
  }
  v7 = -1073741637;
  j = 0;
  v8 = 0;
  for ( i = a1; i; i = (__int64 *)*i )
  {
    v10 = *((_DWORD *)i + 11) == 0;
    v17 = 0;
    if ( !v10 )
      __fastfail(5u);
    v11 = 0;
    v12 = ((i[4] & 0xFFF) + (unsigned __int64)*((unsigned int *)i + 10) + 4095) >> 12;
    if ( v3 )
    {
      while ( (unsigned int)v11 < (unsigned int)v12 )
      {
        i[v11 + 6] &= ~(v3 >> 12);
        v11 = (unsigned int)(v11 + 1);
      }
    }
    v7 = WinHvModifySparseGpaPageHostVisibility(-1, v6, (unsigned int)v12, i + 6, &v17);
    if ( v7 < 0 )
      return (unsigned int)v7;
    if ( v3 )
    {
      if ( v2 == 1 )
      {
        v13 = 0;
        for ( j = 1; (unsigned int)v13 < (unsigned int)v12; v13 = (unsigned int)(v13 + 1) )
          i[v13 + 6] |= v3 >> 12;
      }
      else
      {
        *((_WORD *)i + 5) &= ~0x800u;
        if ( !j )
          continue;
      }
      if ( !v8 )
      {
        if ( (*((_BYTE *)i + 10) & 5) != 0 )
          v14 = (PVOID)i[3];
        else
          v14 = MmMapLockedPagesSpecifyCache((PMDL)i, 0, MmCached, 0, 0, 0x40000020u);
        if ( v14 )
        {
          memset(v14, 0, *((unsigned int *)i + 10));
        }
        else
        {
          v7 = -1073741670;
          v8 = 1;
        }
      }
    }
  }
  if ( v8 )
    XPartVisMakeMdlHostVisible(a1, 3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140014a40  mov     [rsp+arg_8], rbx
0x140014a45  mov     [rsp+MemoryDescriptorList], rcx
0x140014a4a  push    rbp
0x140014a4b  push    rsi
0x140014a4c  push    rdi
0x140014a4d  push    r12
0x140014a4f  push    r13
0x140014a51  push    r14
0x140014a53  push    r15
0x140014a55  sub     rsp, 30h
0x140014a59  cmp     cs:dword_140020870, 0
0x140014a60  mov     esi, edx
0x140014a62  jz      loc_140014C21
0x140014a68  mov     r14, cs:qword_140020868
0x140014a6f  mov     r8d, edx
0x140014a72  test    edx, edx
0x140014a74  jz      loc_140014B14
0x140014a7a  sub     r8d, 1
0x140014a7e  jz      loc_140014B0C
0x140014a84  sub     r8d, 1
0x140014a88  jz      short loc_140014A9F
0x140014a8a  cmp     r8d, 1
0x140014a8e  jz      short loc_140014A9F
0x140014a90  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140014a95  mov     eax, 0C000000Dh
0x140014a9a  jmp     loc_140014C26
0x140014a9f  xor     r13d, r13d
0x140014aa2  mov     edi, 0C00000BBh
0x140014aa7  mov     [rsp+68h+arg_10], 0
0x140014aaf  xor     r12b, r12b
0x140014ab2  mov     rbx, rcx
0x140014ab5  test    rbx, rbx
0x140014ab8  jz      loc_140014C09
0x140014abe  cmp     dword ptr [rbx+2Ch], 0
0x140014ac2  mov     [rsp+68h+arg_18], 0
0x140014ace  jnz     loc_140014C02
0x140014ad4  mov     ecx, [rbx+20h]
0x140014ad7  xor     edx, edx
0x140014ad9  mov     ebp, [rbx+28h]
0x140014adc  and     ecx, 0FFFh
0x140014ae2  add     rbp, 0FFFh
0x140014ae9  add     rbp, rcx
0x140014aec  shr     rbp, 0Ch
0x140014af0  test    r14, r14
0x140014af3  jz      short loc_140014B30
0x140014af5  cmp     edx, ebp
0x140014af7  jnb     short loc_140014B30
0x140014af9  mov     rax, r14
0x140014afc  shr     rax, 0Ch
0x140014b00  not     rax
0x140014b03  and     [rbx+rdx*8+30h], rax
0x140014b08  inc     edx
0x140014b0a  jmp     short loc_140014AF5
0x140014b0c  mov     r13d, 3
0x140014b12  jmp     short loc_140014AA2
0x140014b14  mov     r13d, 1
0x140014b1a  test    r14, r14
0x140014b1d  jz      short loc_140014AA2
0x140014b1f  xor     edx, edx
0x140014b21  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140014b26  mov     eax, 0C00000BBh
0x140014b2b  jmp     loc_140014C26
0x140014b30  lea     rax, [rsp+68h+arg_18]
0x140014b38  mov     r8d, ebp
0x140014b3b  lea     r9, [rbx+30h]
0x140014b3f  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax
0x140014b44  mov     edx, r13d
0x140014b47  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140014b4b  call    cs:__imp_WinHvModifySparseGpaPageHostVisibility
0x140014b52  nop     dword ptr [rax+rax+00h]
0x140014b57  mov     edi, eax
0x140014b59  test    eax, eax
0x140014b5b  js      loc_140014C1D
0x140014b61  test    r14, r14
0x140014b64  jz      loc_140014BFA
0x140014b6a  cmp     esi, 1
0x140014b6d  jnz     short loc_140014B91
0x140014b6f  xor     ecx, ecx
0x140014b71  mov     [rsp+68h+arg_10], sil
0x140014b79  test    ebp, ebp
0x140014b7b  jz      short loc_140014BA4
0x140014b7d  mov     rdx, r14
0x140014b80  shr     rdx, 0Ch
0x140014b84  or      [rbx+rcx*8+30h], rdx
0x140014b89  inc     ecx
0x140014b8b  cmp     ecx, ebp
0x140014b8d  jb      short loc_140014B84
0x140014b8f  jmp     short loc_140014BA4
0x140014b91  mov     eax, 0FFFFF7FFh
0x140014b96  and     [rbx+0Ah], ax
0x140014b9a  cmp     [rsp+68h+arg_10], 0
0x140014ba2  jz      short loc_140014BFA
0x140014ba4  test    r12b, r12b
0x140014ba7  jnz     short loc_140014BFA
0x140014ba9  test    byte ptr [rbx+0Ah], 5
0x140014bad  jz      short loc_140014BB5
0x140014baf  mov     rax, [rbx+18h]
0x140014bb3  jmp     short loc_140014BDD
0x140014bb5  xor     r9d, r9d; RequestedAddress
0x140014bb8  mov     [rsp+68h+Priority], 40000020h; Priority
0x140014bc0  xor     edx, edx; AccessMode
0x140014bc2  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014bca  mov     rcx, rbx; MemoryDescriptorList
0x140014bcd  lea     r8d, [r9+1]; CacheType
0x140014bd1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014bd8  nop     dword ptr [rax+rax+00h]
0x140014bdd  test    rax, rax
0x140014be0  jnz     short loc_140014BEC
0x140014be2  mov     edi, 0C000009Ah
0x140014be7  mov     r12b, 1
0x140014bea  jmp     short loc_140014BFA
0x140014bec  mov     r8d, [rbx+28h]; Size
0x140014bf0  xor     edx, edx; Val
0x140014bf2  mov     rcx, rax; void *
0x140014bf5  call    memset
0x140014bfa  mov     rbx, [rbx]
0x140014bfd  jmp     loc_140014AB5
0x140014c02  mov     ecx, 5
0x140014c07  int     29h; Win8: RtlFailFast(ecx)
0x140014c09  test    r12b, r12b
0x140014c0c  jz      short loc_140014C1D
0x140014c0e  mov     rcx, [rsp+68h+MemoryDescriptorList]
0x140014c13  mov     edx, 3
0x140014c18  call    XPartVisMakeMdlHostVisible
0x140014c1d  mov     eax, edi
0x140014c1f  jmp     short loc_140014C26
0x140014c21  mov     eax, 0C0350006h
0x140014c26  mov     rbx, [rsp+68h+arg_8]
0x140014c2b  add     rsp, 30h
0x140014c2f  pop     r15
0x140014c31  pop     r14
0x140014c33  pop     r13
0x140014c35  pop     r12
0x140014c37  pop     rdi
0x140014c38  pop     rsi
0x140014c39  pop     rbp
0x140014c3a  retn
```
