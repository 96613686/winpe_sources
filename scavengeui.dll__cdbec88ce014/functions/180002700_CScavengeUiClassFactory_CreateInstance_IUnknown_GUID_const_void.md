# CScavengeUiClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002700`
- end: `0x180002865`
- name: `?CreateInstance@CScavengeUiClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `357`
- prototype: `__int64 __fastcall(CScavengeUiClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180001064`
- `0x180002700`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall CScavengeUiClassFactory::CreateInstance(
        CScavengeUiClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  unsigned int v9; // edi

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  if ( *(_QWORD *)&GUID_606b3777_3051_401f_974a_e66aca82a3a3.Data1 != *(_QWORD *)((char *)this + 12)
    || *(_QWORD *)GUID_606b3777_3051_401f_974a_e66aca82a3a3.Data4 != *(_QWORD *)((char *)this + 20) )
  {
    return 2147746065LL;
  }
  v7 = operator new(0x280u);
  v8 = v7;
  if ( v7 )
  {
    v7[132] = 1;
    *(_QWORD *)v7 = &CCleanupBase::`vftable';
    v7[133] = 16;
    *((_QWORD *)v7 + 67) = 0;
    v7[136] = 0;
    *((_QWORD *)v7 + 69) = 0;
    *((_QWORD *)v7 + 70) = 0;
    *((_QWORD *)v7 + 71) = 0;
    *((_QWORD *)v7 + 72) = 0;
    *((_QWORD *)v7 + 73) = 0;
    *((_QWORD *)v7 + 75) = 0;
    v7[152] = 0;
    *((_QWORD *)v7 + 77) = 0;
    v7[156] = 0;
    *((_QWORD *)v7 + 79) = 0;
    _InterlockedIncrement(&dword_18000A8D4);
    v7[146] = 0;
    *(_QWORD *)v7 = &CUpdateCleanup::`vftable';
    v7[133] = 16;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v9 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v8)(v8, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x180002700  mov     [rsp+arg_0], rbx
0x180002705  mov     [rsp+arg_8], rbp
0x18000270a  push    rsi
0x18000270b  push    rdi
0x18000270c  push    r14
0x18000270e  sub     rsp, 20h
0x180002712  xor     r14d, r14d
0x180002715  mov     rsi, r9
0x180002718  mov     rbp, r8
0x18000271b  test    r9, r9
0x18000271e  jnz     short loc_18000272A
0x180002720  mov     eax, 80070057h
0x180002725  jmp     loc_180002852
0x18000272a  mov     [r9], r14
0x18000272d  test    rdx, rdx
0x180002730  jz      short loc_18000273C
0x180002732  mov     eax, 80040110h
0x180002737  jmp     loc_180002852
0x18000273c  mov     rax, qword ptr cs:_GUID_606b3777_3051_401f_974a_e66aca82a3a3.Data1
0x180002743  cmp     rax, [rcx+0Ch]
0x180002747  jnz     loc_18000284D
0x18000274d  mov     rax, qword ptr cs:_GUID_606b3777_3051_401f_974a_e66aca82a3a3.Data4
0x180002754  cmp     rax, [rcx+14h]
0x180002758  jnz     loc_18000284D
0x18000275e  mov     ecx, 280h; Size
0x180002763  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002768  mov     [rsp+38h+arg_18], rax
0x18000276d  mov     rbx, rax
0x180002770  test    rax, rax
0x180002773  jz      loc_18000280C
0x180002779  lea     rax, ??_7CCleanupBase@@6B@; const CCleanupBase::`vftable'
0x180002780  mov     dword ptr [rbx+210h], 1
0x18000278a  mov     ecx, 10h
0x18000278f  mov     [rbx], rax
0x180002792  mov     [rbx+214h], ecx
0x180002798  mov     [rbx+218h], r14
0x18000279f  mov     [rbx+220h], r14d
0x1800027a6  mov     [rbx+228h], r14
0x1800027ad  mov     [rbx+230h], r14
0x1800027b4  mov     [rbx+238h], r14
0x1800027bb  mov     [rbx+240h], r14
0x1800027c2  mov     [rbx+248h], r14
0x1800027c9  mov     [rbx+258h], r14
0x1800027d0  mov     [rbx+260h], r14d
0x1800027d7  mov     [rbx+268h], r14
0x1800027de  mov     [rbx+270h], r14d
0x1800027e5  mov     [rbx+278h], r14
0x1800027ec  lock inc cs:dword_18000A8D4
0x1800027f3  lea     rax, ??_7CUpdateCleanup@@6B@; const CUpdateCleanup::`vftable'
0x1800027fa  mov     [rbx+248h], r14d
0x180002801  mov     [rbx], rax
0x180002804  mov     [rbx+214h], ecx
0x18000280a  jmp     short loc_18000280F
0x18000280c  mov     rbx, r14
0x18000280f  test    rbx, rbx
0x180002812  mov     edi, r14d
0x180002815  mov     eax, 8007000Eh
0x18000281a  cmovz   edi, eax
0x18000281d  jz      short loc_180002849
0x18000281f  mov     rax, [rbx]
0x180002822  mov     r8, rsi
0x180002825  mov     rdx, rbp
0x180002828  mov     rcx, rbx
0x18000282b  mov     rax, [rax]
0x18000282e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002833  mov     edi, eax
0x180002835  test    rbx, rbx
0x180002838  jz      short loc_180002849
0x18000283a  mov     rax, [rbx]
0x18000283d  mov     rcx, rbx
0x180002840  mov     rax, [rax+10h]
0x180002844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002849  mov     eax, edi
0x18000284b  jmp     short loc_180002852
0x18000284d  mov     eax, 80040111h
0x180002852  mov     rbx, [rsp+38h+arg_0]
0x180002857  mov     rbp, [rsp+38h+arg_8]
0x18000285c  add     rsp, 20h
0x180002860  pop     r14
0x180002862  pop     rdi
0x180002863  pop     rsi
0x180002864  retn
```
