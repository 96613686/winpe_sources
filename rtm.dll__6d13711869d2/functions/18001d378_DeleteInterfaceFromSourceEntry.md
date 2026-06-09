# DeleteInterfaceFromSourceEntry

- ea: `0x18001d378`
- end: `0x18001d8ff`
- name: `DeleteInterfaceFromSourceEntry`
- size: `1415`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180012800`
- `0x18001ba30`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x180019a1c`
- `0x18001d1ec`
- `0x18001d2a0`
- `0x18001d378`
- `0x18001d908`
- `0x18001db88`
- `0x18001dbd0`
- `0x18001dc28`
- `0x18001dcbc`
- `0x18001dd8c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x18001d6d3`: `Invoked Local Leave Alert for protocol %x, %x`

## pseudocode

```c
__int64 __fastcall DeleteInterfaceFromSourceEntry(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        int a7,
        int a8)
{
  int v10; // r15d
  unsigned int v11; // edx
  __int64 v12; // r12
  int v13; // r8d
  int GroupEntry; // eax
  __int64 v15; // rbx
  unsigned int v16; // edx
  int SourceEntry; // eax
  _DWORD *v18; // rdi
  int v19; // r8d
  __int16 *v20; // rcx
  __int16 v21; // ax
  bool v22; // zf
  __int64 result; // rax
  int v24; // esi
  int v25; // r9d
  __int16 *v26; // rsi
  __int64 v27; // r9
  __int64 v28; // r8
  int v29; // r12d
  unsigned int v30; // r14d
  __int64 v31; // rsi
  char *v32; // rcx
  _QWORD *v33; // r15
  unsigned int i; // [rsp+40h] [rbp-C0h]
  _DWORD *v36; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  __int16 *v38; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-A0h]
  unsigned int v40; // [rsp+64h] [rbp-9Ch]
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  int v42; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v40 = a3;
  v37 = 0;
  v41 = 0;
  v36 = 0;
  v38 = 0;
  v10 = 0;
  v42 = 0;
  v39 = a4;
  memset_0(v43, 0, sizeof(v43));
  if ( a2 )
    v11 = a2 % (dword_18002B930 - 1) + 1;
  else
    v11 = 0;
  v12 = 32LL * v11;
  AcquireWriteLock((char *)qword_18002BA40 + v12 + 16);
  GroupEntry = FindGroupEntry((int)v12 + (int)qword_18002BA40, a2, v13, (unsigned int)&v41, 1);
  v15 = v41;
  if ( !GroupEntry
    || ((AcquireWriteLock(v41 + 40), v10 = 1, !v39) ? (v16 = 0) : (v16 = v39 % (dword_18002B934 - 1) + 1),
        SourceEntry = FindSourceEntry((unsigned int)v15 + 16 * v16 + 88, v39, v39, (unsigned int)&v36, 1),
        v18 = v36,
        !SourceEntry) )
  {
LABEL_21:
    v22 = v10 == 0;
LABEL_22:
    if ( v22 )
      return ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
LABEL_23:
    ReleaseWriteLock(v15 + 40);
    return ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
  }
  if ( !(unsigned int)FindOutInterfaceEntry(
                        (int)v36 + 48,
                        a6,
                        a7,
                        *(_DWORD *)(a1 + 16),
                        *(_DWORD *)(a1 + 20),
                        (__int64)&v36,
                        (__int64)&v38) )
  {
    if ( (unsigned int)FindOutInterfaceEntry(
                         (int)v18 + 64,
                         a6,
                         v19,
                         *(_DWORD *)(a1 + 16),
                         *(_DWORD *)(a1 + 20),
                         (__int64)&v36,
                         (__int64)&v38) )
    {
      v20 = v38;
      if ( a8 )
      {
        v38[18] = 0;
        v21 = 0x7FFF;
      }
      else
      {
        v38[19] = 0;
        v21 = -16385;
      }
      v20[17] &= v21;
      if ( v20[17] < 0 || (v20[17] & 0x4000) != 0 )
        goto LABEL_23;
      DeleteOutInterfaceEntry(v20, 0);
      v22 = v18[9]-- == 1;
      if ( v22 && !v18[28] )
      {
        DeleteSourceEntry(v18);
        --*(_DWORD *)(v15 + 48);
      }
      if ( *(_DWORD *)(v15 + 48) )
        goto LABEL_23;
      ReleaseWriteLock(v15 + 40);
      v10 = 0;
      DeleteGroupEntry(v15);
      v15 = 0;
    }
    goto LABEL_21;
  }
  v26 = v38;
  if ( a8 )
  {
    if ( v38[17] >= 0 )
      goto LABEL_23;
    v38[18] = 0;
    v26[17] &= ~0x8000u;
    if ( *(_QWORD *)(a1 + 88) )
    {
      if ( qword_18002B8A8 )
      {
        v27 = *(unsigned int *)(a1 + 20);
        v28 = *(unsigned int *)(a1 + 16);
        LOWORD(v42) = 0;
        FormatRRASErrorString(&v42, L"Invoked Local Leave Alert for protocol %x, %x", v28, v27);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v42);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, int))(a1 + 88))(v39, a5, a2, v40, a6, a7);
    }
  }
  else
  {
    if ( (v38[17] & 0x4000) == 0 )
      goto LABEL_23;
    v38[19] = 0;
    v26[17] &= ~0x4000u;
  }
  if ( v26[17] < 0 || (v26[17] & 0x4000) != 0 )
  {
    v24 = a6;
  }
  else
  {
    DeleteOutInterfaceEntry(v26, 0);
    --v18[9];
    v24 = a6;
    v25 = *(_DWORD *)(a1 + 16);
    LODWORD(v36) = 0;
    FindOutInterfaceEntry((_DWORD)v18 + 48, a6, a7, v25, *(_DWORD *)(a1 + 20), (__int64)&v36, (__int64)&v38);
    if ( (_DWORD)v36 )
    {
      --v18[10];
      InvokePruneAlertCallbacks(v15, (__int64)v18, a6, a7, a1);
    }
  }
  if ( !v18[9] && !v18[28] )
  {
    DeleteSourceEntry(v18);
    --*(_DWORD *)(v15 + 48);
    v18 = 0;
  }
  if ( !*(_DWORD *)(v15 + 48) )
  {
    ReleaseWriteLock(v15 + 40);
    DeleteGroupEntry(v15);
    v15 = 0;
  }
  if ( a2 )
  {
    if ( !v39 )
    {
      if ( !v15 )
        return ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
      DeleteInterfaceFromGroupMfe(v15, v24, a7, *(_DWORD *)(a1 + 16), *(_DWORD *)(a1 + 20), a8);
      goto LABEL_23;
    }
    if ( v18 && v18[28] )
      DeleteInterfaceFromSourceMfe(v15, (__int64)v18, v24, a7, *(_DWORD *)(a1 + 16), *(_DWORD *)(a1 + 20), a8, 0);
    v22 = v15 == 0;
    goto LABEL_22;
  }
  if ( v15 )
    ReleaseWriteLock(v15 + 40);
  ReleaseWriteLock((char *)qword_18002BA40 + v12 + 16);
  v29 = *(_DWORD *)(a1 + 20);
  v37 = *(_DWORD *)(a1 + 16);
  result = 0;
  v30 = 0;
  for ( i = 0; v30 < dword_18002B930; i = v30 )
  {
    v31 = 32LL * v30;
    AcquireWriteLock((char *)qword_18002BA40 + v31 + 16);
    v32 = (char *)qword_18002BA40;
    v33 = *(_QWORD **)((char *)qword_18002BA40 + v31);
    if ( v33 != (_QWORD *)((char *)qword_18002BA40 + v31) )
    {
      do
      {
        AcquireWriteLock(v33 + 3);
        DeleteInterfaceFromGroupMfe((_DWORD)v33 - 16, a6, a7, v37, v29, a8);
        ReleaseWriteLock(v33 + 3);
        v32 = (char *)qword_18002BA40;
        v33 = (_QWORD *)*v33;
      }
      while ( v33 != (_QWORD *)((char *)qword_18002BA40 + v31) );
      v30 = i;
    }
    result = ReleaseWriteLock(&v32[v31 + 16]);
    ++v30;
  }
  return result;
}

```

## disassembly

```asm
0x18001d378  push    rbp
0x18001d37a  push    rbx
0x18001d37b  push    rsi
0x18001d37c  push    rdi
0x18001d37d  push    r12
0x18001d37f  push    r13
0x18001d381  push    r14
0x18001d383  push    r15
0x18001d385  lea     rbp, [rsp-788h]
0x18001d38d  sub     rsp, 888h
0x18001d394  mov     rax, cs:__security_cookie
0x18001d39b  xor     rax, rsp
0x18001d39e  mov     [rbp+7C0h+var_50], rax
0x18001d3a5  xor     r12d, r12d
0x18001d3a8  mov     [rsp+8C0h+var_85C], r8d
0x18001d3ad  mov     ebx, edx
0x18001d3af  mov     [rsp+8C0h+var_880], edx
0x18001d3b3  mov     r14, rcx
0x18001d3b6  mov     [rsp+8C0h+var_870], r12d
0x18001d3bb  xor     edx, edx; Val
0x18001d3bd  mov     [rsp+8C0h+var_858], r12
0x18001d3c2  mov     r8d, 7FCh; Size
0x18001d3c8  mov     [rsp+8C0h+var_878], r12
0x18001d3cd  lea     rcx, [rsp+8C0h+var_84C]; void *
0x18001d3d2  mov     [rsp+8C0h+var_868], r12
0x18001d3d7  mov     r15d, r12d
0x18001d3da  mov     [rsp+8C0h+var_850], r12d
0x18001d3df  mov     edi, r12d
0x18001d3e2  mov     [rsp+8C0h+var_860], r9d
0x18001d3e7  mov     esi, r12d
0x18001d3ea  call    memset_0
0x18001d3ef  test    ebx, ebx
0x18001d3f1  jz      short loc_18001D405
0x18001d3f3  mov     ecx, cs:dword_18002B930
0x18001d3f9  xor     edx, edx
0x18001d3fb  dec     ecx
0x18001d3fd  mov     eax, ebx
0x18001d3ff  div     ecx
0x18001d401  inc     edx
0x18001d403  jmp     short loc_18001D408
0x18001d405  mov     edx, r12d
0x18001d408  mov     rcx, cs:qword_18002BA40
0x18001d40f  mov     r12d, edx
0x18001d412  add     rcx, 10h
0x18001d416  shl     r12, 5
0x18001d41a  add     rcx, r12
0x18001d41d  call    AcquireWriteLock
0x18001d422  mov     rcx, cs:qword_18002BA40
0x18001d429  lea     r9, [rsp+8C0h+var_858]
0x18001d42e  add     rcx, r12
0x18001d431  mov     dword ptr [rsp+8C0h+var_8A0], 1
0x18001d439  mov     edx, ebx
0x18001d43b  call    FindGroupEntry
0x18001d440  mov     r13d, [rbp+7C0h+arg_30]
0x18001d447  xor     edx, edx
0x18001d449  mov     rbx, [rsp+8C0h+var_858]
0x18001d44e  mov     ecx, 4000h
0x18001d453  test    eax, eax
0x18001d455  jz      loc_18001D5A5
0x18001d45b  lea     rcx, [rbx+28h]
0x18001d45f  call    AcquireWriteLock
0x18001d464  mov     r8d, [rsp+8C0h+var_860]
0x18001d469  xor     eax, eax
0x18001d46b  mov     r9d, 1
0x18001d471  mov     r15d, r9d
0x18001d474  test    r8d, r8d
0x18001d477  jz      short loc_18001D48D
0x18001d479  mov     ecx, cs:dword_18002B934
0x18001d47f  xor     edx, edx
0x18001d481  dec     ecx
0x18001d483  mov     eax, r8d
0x18001d486  div     ecx
0x18001d488  add     edx, r9d
0x18001d48b  jmp     short loc_18001D48F
0x18001d48d  mov     edx, eax
0x18001d48f  mov     ecx, edx
0x18001d491  mov     edx, r8d
0x18001d494  shl     rcx, 4
0x18001d498  add     rcx, 58h ; 'X'
0x18001d49c  mov     dword ptr [rsp+8C0h+var_8A0], r9d
0x18001d4a1  add     rcx, rbx
0x18001d4a4  lea     r9, [rsp+8C0h+var_878]
0x18001d4a9  call    FindSourceEntry
0x18001d4ae  mov     rdi, [rsp+8C0h+var_878]
0x18001d4b3  xor     edx, edx
0x18001d4b5  test    eax, eax
0x18001d4b7  jz      loc_18001D5EE
0x18001d4bd  mov     eax, [r14+14h]
0x18001d4c1  lea     rdx, [rsp+8C0h+var_868]
0x18001d4c6  mov     esi, [rbp+7C0h+arg_28]
0x18001d4cc  lea     rcx, [rdi+30h]
0x18001d4d0  mov     r9d, [r14+10h]
0x18001d4d4  mov     r8d, r13d
0x18001d4d7  mov     [rsp+8C0h+var_890], rdx
0x18001d4dc  lea     rdx, [rsp+8C0h+var_878]
0x18001d4e1  mov     [rsp+8C0h+var_898], rdx
0x18001d4e6  mov     edx, esi
0x18001d4e8  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18001d4ec  call    FindOutInterfaceEntry
0x18001d4f1  xor     edx, edx
0x18001d4f3  test    eax, eax
0x18001d4f5  jnz     loc_18001D68A
0x18001d4fb  mov     r9d, [r14+10h]
0x18001d4ff  lea     rax, [rsp+8C0h+var_868]
0x18001d504  mov     [rsp+8C0h+var_890], rax
0x18001d509  lea     rcx, [rdi+40h]
0x18001d50d  lea     rax, [rsp+8C0h+var_878]
0x18001d512  mov     edx, esi
0x18001d514  mov     [rsp+8C0h+var_898], rax
0x18001d519  mov     eax, [r14+14h]
0x18001d51d  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18001d521  call    FindOutInterfaceEntry
0x18001d526  xor     edx, edx
0x18001d528  test    eax, eax
0x18001d52a  jz      loc_18001D5E9
0x18001d530  mov     rcx, [rsp+8C0h+var_868]
0x18001d535  cmp     [rbp+7C0h+arg_38], edx
0x18001d53b  jz      short loc_18001D548
0x18001d53d  mov     [rcx+24h], dx
0x18001d541  mov     eax, 7FFFh
0x18001d546  jmp     short loc_18001D551
0x18001d548  mov     [rcx+26h], dx
0x18001d54c  mov     eax, 0BFFFh
0x18001d551  and     [rcx+22h], ax
0x18001d555  cmp     [rcx+22h], dx
0x18001d559  jl      short loc_18001D5AA
0x18001d55b  mov     eax, 4000h
0x18001d560  test    [rcx+22h], ax
0x18001d564  jnz     short loc_18001D5AA
0x18001d566  call    DeleteOutInterfaceEntry
0x18001d56b  xor     esi, esi
0x18001d56d  or      r15d, 0FFFFFFFFh
0x18001d571  add     [rdi+24h], r15d
0x18001d575  jnz     short loc_18001D588
0x18001d577  cmp     [rdi+70h], esi
0x18001d57a  jnz     short loc_18001D588
0x18001d57c  mov     rcx, rdi
0x18001d57f  call    DeleteSourceEntry
0x18001d584  add     [rbx+30h], r15d
0x18001d588  cmp     [rbx+30h], esi
0x18001d58b  jnz     short loc_18001D5AA
0x18001d58d  lea     rcx, [rbx+28h]
0x18001d591  call    ReleaseWriteLock
0x18001d596  mov     rcx, rbx
0x18001d599  mov     r15d, esi
0x18001d59c  call    DeleteGroupEntry
0x18001d5a1  xor     edx, edx
0x18001d5a3  mov     ebx, edx
0x18001d5a5  test    r15d, r15d
0x18001d5a8  jz      short loc_18001D5B3
0x18001d5aa  lea     rcx, [rbx+28h]
0x18001d5ae  call    ReleaseWriteLock
0x18001d5b3  mov     rcx, cs:qword_18002BA40
0x18001d5ba  add     rcx, 10h
0x18001d5be  add     rcx, r12
0x18001d5c1  call    ReleaseWriteLock
0x18001d5c6  mov     rcx, [rbp+7C0h+var_50]
0x18001d5cd  xor     rcx, rsp; StackCookie
0x18001d5d0  call    __security_check_cookie
0x18001d5d5  add     rsp, 888h
0x18001d5dc  pop     r15
0x18001d5de  pop     r14
0x18001d5e0  pop     r13
0x18001d5e2  pop     r12
0x18001d5e4  pop     rdi
0x18001d5e5  pop     rsi
0x18001d5e6  pop     rbx
0x18001d5e7  pop     rbp
0x18001d5e8  retn
0x18001d5e9  mov     rsi, [rsp+8C0h+var_868]
0x18001d5ee  mov     ecx, 4000h
0x18001d5f3  test    eax, eax
0x18001d5f5  jz      short loc_18001D5A5
0x18001d5f7  mov     eax, [rsp+8C0h+var_870]
0x18001d5fb  test    eax, eax
0x18001d5fd  jz      short loc_18001D5A5
0x18001d5ff  or      r15d, 0FFFFFFFFh
0x18001d603  cmp     [rsi+22h], dx
0x18001d607  jl      loc_18001D75A
0x18001d60d  test    [rsi+22h], cx
0x18001d611  jnz     loc_18001D75A
0x18001d617  mov     rcx, rsi
0x18001d61a  call    DeleteOutInterfaceEntry
0x18001d61f  add     [rdi+24h], r15d
0x18001d623  lea     rcx, [rdi+30h]
0x18001d627  mov     esi, [rbp+7C0h+arg_28]
0x18001d62d  xor     eax, eax
0x18001d62f  mov     r9d, [r14+10h]
0x18001d633  mov     r8d, r13d
0x18001d636  mov     dword ptr [rsp+8C0h+var_878], eax
0x18001d63a  mov     edx, esi
0x18001d63c  lea     rax, [rsp+8C0h+var_868]
0x18001d641  mov     [rsp+8C0h+var_890], rax
0x18001d646  lea     rax, [rsp+8C0h+var_878]
0x18001d64b  mov     [rsp+8C0h+var_898], rax
0x18001d650  mov     eax, [r14+14h]
0x18001d654  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18001d658  call    FindOutInterfaceEntry
0x18001d65d  xor     edx, edx
0x18001d65f  cmp     dword ptr [rsp+8C0h+var_878], edx
0x18001d663  jz      loc_18001D760
0x18001d669  add     [rdi+28h], r15d
0x18001d66d  mov     r9d, r13d
0x18001d670  mov     r8d, esi
0x18001d673  mov     [rsp+8C0h+var_8A0], r14
0x18001d678  mov     rdx, rdi
0x18001d67b  mov     rcx, rbx
0x18001d67e  call    InvokePruneAlertCallbacks
0x18001d683  xor     edx, edx
0x18001d685  jmp     loc_18001D760
0x18001d68a  mov     rsi, [rsp+8C0h+var_868]
0x18001d68f  cmp     [rbp+7C0h+arg_38], edx
0x18001d695  jz      loc_18001D736
0x18001d69b  cmp     [rsi+22h], dx
0x18001d69f  jge     loc_18001D5AA
0x18001d6a5  mov     [rsi+24h], dx
0x18001d6a9  mov     eax, 7FFFh
0x18001d6ae  and     [rsi+22h], ax
0x18001d6b2  cmp     [r14+58h], rdx
0x18001d6b6  jz      short loc_18001D72C
0x18001d6b8  cmp     cs:qword_18002B8A8, rdx
0x18001d6bf  jz      short loc_18001D6FE
0x18001d6c1  mov     r9d, [r14+14h]
0x18001d6c5  lea     rcx, [rsp+8C0h+var_850]
0x18001d6ca  mov     r8d, [r14+10h]
0x18001d6ce  mov     word ptr [rsp+8C0h+var_850], dx
0x18001d6d3  lea     rdx, aInvokedLocalLe; "Invoked Local Leave Alert for protocol "...
0x18001d6da  call    FormatRRASErrorString
0x18001d6df  mov     rdx, cs:qword_18002B8A8
0x18001d6e6  lea     r8, [rsp+8C0h+var_850]
0x18001d6eb  mov     rcx, cs:gMgmEtwContext
0x18001d6f2  mov     rax, cs:gMgmTemplateFunc
0x18001d6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fe  mov     eax, [rbp+7C0h+arg_28]
0x18001d704  mov     r9d, [rsp+8C0h+var_85C]
0x18001d709  mov     r8d, [rsp+8C0h+var_880]
0x18001d70e  mov     edx, [rbp+7C0h+arg_20]
0x18001d714  mov     ecx, [rsp+8C0h+var_860]
0x18001d718  mov     dword ptr [rsp+8C0h+var_898], r13d
0x18001d71d  mov     dword ptr [rsp+8C0h+var_8A0], eax
0x18001d721  mov     rax, [r14+58h]
0x18001d725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d72a  xor     edx, edx
0x18001d72c  mov     ecx, 4000h
0x18001d731  jmp     loc_18001D5FF
0x18001d736  mov     ecx, 4000h
0x18001d73b  test    [rsi+22h], cx
0x18001d73f  jz      loc_18001D5AA
0x18001d745  mov     eax, 0BFFFh
0x18001d74a  mov     [rsi+26h], dx
0x18001d74e  and     [rsi+22h], ax
0x18001d752  mov     eax, r15d
0x18001d755  jmp     loc_18001D5FB
0x18001d75a  mov     esi, [rbp+7C0h+arg_28]
0x18001d760  cmp     [rdi+24h], edx
0x18001d763  jnz     short loc_18001D77A
0x18001d765  cmp     [rdi+70h], edx
0x18001d768  jnz     short loc_18001D77A
0x18001d76a  mov     rcx, rdi
0x18001d76d  call    DeleteSourceEntry
0x18001d772  xor     edx, edx
0x18001d774  add     [rbx+30h], r15d
0x18001d778  mov     edi, edx
0x18001d77a  cmp     [rbx+30h], edx
0x18001d77d  jnz     short loc_18001D794
0x18001d77f  lea     rcx, [rbx+28h]
0x18001d783  call    ReleaseWriteLock
0x18001d788  mov     rcx, rbx
0x18001d78b  call    DeleteGroupEntry
0x18001d790  xor     edx, edx
0x18001d792  mov     ebx, edx
0x18001d794  cmp     [rsp+8C0h+var_880], edx
0x18001d798  jnz     loc_18001D887
0x18001d79e  test    rbx, rbx
0x18001d7a1  jz      short loc_18001D7AC
0x18001d7a3  lea     rcx, [rbx+28h]
0x18001d7a7  call    ReleaseWriteLock
0x18001d7ac  mov     rcx, cs:qword_18002BA40
0x18001d7b3  add     rcx, 10h
0x18001d7b7  add     rcx, r12
0x18001d7ba  call    ReleaseWriteLock
0x18001d7bf  mov     eax, [r14+10h]
0x18001d7c3  mov     r12d, [r14+14h]
0x18001d7c7  mov     [rsp+8C0h+var_870], eax
0x18001d7cb  xor     eax, eax
0x18001d7cd  cmp     cs:dword_18002B930, eax
0x18001d7d3  mov     r14d, eax
0x18001d7d6  mov     [rsp+8C0h+var_880], eax
0x18001d7da  jbe     loc_18001D5C6
0x18001d7e0  mov     rcx, cs:qword_18002BA40
0x18001d7e7  add     rcx, 10h
0x18001d7eb  mov     esi, r14d
0x18001d7ee  shl     rsi, 5
0x18001d7f2  add     rcx, rsi
0x18001d7f5  call    AcquireWriteLock
0x18001d7fa  mov     rcx, cs:qword_18002BA40
0x18001d801  lea     rax, [rsi+rcx]
0x18001d805  mov     r15, [rax]
0x18001d808  cmp     r15, rax
0x18001d80b  jz      short loc_18001D861
  ... truncated ...
```
