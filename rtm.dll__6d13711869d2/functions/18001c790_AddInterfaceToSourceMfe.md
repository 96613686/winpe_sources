# AddInterfaceToSourceMfe

- ea: `0x18001c790`
- end: `0x18001ca95`
- name: `AddInterfaceToSourceMfe`
- size: `773`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011850`
- `0x18001a360`
- `0x18001c0c8`
- `0x18001c1a8`

## callees

- `0x18001b548`
- `0x18001c790`
- `0x18001cd94`
- `0x18001dcbc`
- `0x18001f11c`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18001c99d`
- `rtutils!RouterLogEventA` at `0x18001c99d`

## string_xrefs

- `0x18001c9bd`: `Invoked Join Alert for protocol %x, %x`
- `0x18001c83b`: `Group %lx scoped on incoming i/f %lx`
- `0x18001c947`: `AddInterfaceToSourceMfe : cannot find protocol component : %x, %x`

## pseudocode

```c
void __fastcall AddInterfaceToSourceMfe(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  int v8; // r15d
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // r8d
  int v16; // ecx
  __int64 ProtocolEntry; // rax
  unsigned int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v8 = 0;
  v26 = a8;
  v23 = 0;
  v24 = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  if ( *(_QWORD *)(a2 + 112) == __PAIR64__(a4, a3) )
    goto LABEL_25;
  if ( qword_18002B950 && (unsigned int)qword_18002B950(*(unsigned int *)(a2 + 112), *(unsigned int *)(a1 + 32)) )
  {
    if ( qword_18002B8A8 )
    {
      v13 = *(unsigned int *)(a2 + 112);
      v14 = *(unsigned int *)(a1 + 32);
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, L"Group %lx scoped on incoming i/f %lx", v14, v13);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
    }
    goto LABEL_25;
  }
  if ( (unsigned int)FindOutInterfaceEntry((int)a2 + 88, a3, a4, a5, a6, (__int64)v25, (__int64)&v23) )
  {
    v21 = v23;
    if ( a7 )
    {
      *(_WORD *)(v23 + 34) |= 0x8000u;
      ++*(_WORD *)(v21 + 36);
    }
    else
    {
      *(_WORD *)(v23 + 34) |= 0x4000u;
      ++*(_WORD *)(v21 + 38);
    }
    goto LABEL_25;
  }
  v16 = v23;
  if ( !v23 )
  {
    v8 = 1;
    v16 = a2 + 88;
  }
  if ( !(unsigned int)CreateOutInterfaceEntry(v16, a3, v15, a5, a6, a7, (__int64)&v24) )
  {
    ++*(_DWORD *)(a2 + 80);
    if ( v8 )
    {
      ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *(unsigned int *)(a2 + 136), *(unsigned int *)(a2 + 140));
      v20 = ProtocolEntry;
      if ( !ProtocolEntry )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(&v27, L"AddInterfaceToSourceMfe : cannot find protocol component : %x, %x", v18, v19);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
        }
        if ( dword_18002BA54 )
          RouterLogEventA(qword_18002BA58, 1u, 0xC35Au, 0, 0, 0x490u);
        goto LABEL_25;
      }
      if ( *(_QWORD *)(ProtocolEntry + 64) )
      {
        if ( qword_18002B8A8 )
        {
          LOWORD(v27) = 0;
          FormatRRASErrorString(
            &v27,
            L"Invoked Join Alert for protocol %x, %x",
            *(unsigned int *)(ProtocolEntry + 16),
            *(unsigned int *)(ProtocolEntry + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v27);
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))(v20 + 64))(
          *(unsigned int *)(a2 + 104),
          *(unsigned int *)(a2 + 108),
          *(unsigned int *)(a1 + 32),
          *(unsigned int *)(a1 + 36),
          0);
      }
    }
    if ( *(_DWORD *)(a2 + 144) )
      AddMfeToForwarder(a1, a2, 0);
  }
LABEL_25:
  if ( v26 )
    *v26 = v24;
}

```

## disassembly

```asm
0x18001c790  mov     [rsp-8+arg_10], rbx
0x18001c795  push    rbp
0x18001c796  push    rsi
0x18001c797  push    rdi
0x18001c798  push    r12
0x18001c79a  push    r13
0x18001c79c  push    r14
0x18001c79e  push    r15
0x18001c7a0  lea     rbp, [rsp-780h]
0x18001c7a8  sub     rsp, 880h
0x18001c7af  mov     rax, cs:__security_cookie
0x18001c7b6  xor     rax, rsp
0x18001c7b9  mov     [rbp+7B0h+var_40], rax
0x18001c7c0  mov     rax, [rbp+7B0h+arg_38]
0x18001c7c7  xor     r15d, r15d
0x18001c7ca  mov     edi, r8d
0x18001c7cd  mov     [rsp+8B0h+var_870], r8d
0x18001c7d2  mov     rbx, rdx
0x18001c7d5  mov     [rsp+8B0h+var_850], rax
0x18001c7da  mov     r14, rcx
0x18001c7dd  mov     [rsp+8B0h+var_868], r15
0x18001c7e2  xor     edx, edx; Val
0x18001c7e4  mov     [rsp+8B0h+var_860], r15
0x18001c7e9  mov     r8d, 7FCh; Size
0x18001c7ef  mov     [rsp+8B0h+var_840], r15d
0x18001c7f4  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18001c7f9  mov     esi, r9d
0x18001c7fc  call    memset_0
0x18001c801  mov     ecx, [rbx+70h]
0x18001c804  cmp     ecx, edi
0x18001c806  jnz     short loc_18001C811
0x18001c808  cmp     [rbx+74h], esi
0x18001c80b  jz      loc_18001CA59
0x18001c811  mov     rax, cs:qword_18002B950
0x18001c818  test    rax, rax
0x18001c81b  jz      short loc_18001C87A
0x18001c81d  mov     edx, [r14+20h]
0x18001c821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c826  test    eax, eax
0x18001c828  jz      short loc_18001C87A
0x18001c82a  cmp     cs:qword_18002B8A8, r15
0x18001c831  jz      loc_18001CA59
0x18001c837  mov     r9d, [rbx+70h]
0x18001c83b  lea     rdx, aGroupLxScopedO; "Group %lx scoped on incoming i/f %lx"
0x18001c842  mov     r8d, [r14+20h]
0x18001c846  lea     rcx, [rsp+8B0h+var_840]
0x18001c84b  mov     word ptr [rsp+8B0h+var_840], r15w
0x18001c851  call    FormatRRASErrorString
0x18001c856  mov     rdx, cs:qword_18002B8A8
0x18001c85d  lea     r8, [rsp+8B0h+var_840]
0x18001c862  mov     rcx, cs:gMgmEtwContext
0x18001c869  mov     rax, cs:gMgmTemplateFunc
0x18001c870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c875  jmp     loc_18001CA59
0x18001c87a  mov     r13d, [rbp+7B0h+arg_20]
0x18001c881  lea     rcx, [rsp+8B0h+var_868]
0x18001c886  mov     r12d, [rbp+7B0h+arg_28]
0x18001c88d  mov     r9d, r13d
0x18001c890  mov     [rsp+8B0h+var_880], rcx
0x18001c895  mov     r8d, esi
0x18001c898  lea     rcx, [rsp+8B0h+var_858]
0x18001c89d  mov     edx, edi
0x18001c89f  mov     qword ptr [rsp+8B0h+dwErrorCode], rcx
0x18001c8a4  lea     rcx, [rbx+58h]
0x18001c8a8  mov     dword ptr [rsp+8B0h+plpszSubStringArray], r12d
0x18001c8ad  call    FindOutInterfaceEntry
0x18001c8b2  mov     edi, 1
0x18001c8b7  test    eax, eax
0x18001c8b9  jnz     loc_18001CA2F
0x18001c8bf  mov     rcx, [rsp+8B0h+var_868]
0x18001c8c4  lea     rax, [rsp+8B0h+var_860]
0x18001c8c9  mov     edx, [rsp+8B0h+var_870]
0x18001c8cd  mov     r9d, r13d
0x18001c8d0  mov     [rsp+8B0h+var_880], rax
0x18001c8d5  mov     eax, [rbp+7B0h+arg_30]
0x18001c8db  mov     [rsp+8B0h+dwErrorCode], eax
0x18001c8df  mov     dword ptr [rsp+8B0h+plpszSubStringArray], r12d
0x18001c8e4  test    rcx, rcx
0x18001c8e7  jnz     short loc_18001C8F0
0x18001c8e9  mov     r15d, edi
0x18001c8ec  lea     rcx, [rbx+58h]
0x18001c8f0  call    CreateOutInterfaceEntry
0x18001c8f5  test    eax, eax
0x18001c8f7  jnz     loc_18001CA59
0x18001c8fd  add     [rbx+50h], edi
0x18001c900  test    r15d, r15d
0x18001c903  jz      loc_18001CA13
0x18001c909  mov     r8d, [rbx+8Ch]
0x18001c910  lea     rcx, qword_18002B9A8
0x18001c917  mov     edx, [rbx+88h]
0x18001c91d  call    GetProtocolEntry
0x18001c922  xor     r15d, r15d
0x18001c925  mov     rsi, rax
0x18001c928  test    rax, rax
0x18001c92b  jnz     short loc_18001C9A8
0x18001c92d  cmp     cs:qword_18002B8A8, r15
0x18001c934  jz      short loc_18001C972
0x18001c936  mov     r9d, r8d
0x18001c939  mov     word ptr [rsp+8B0h+var_840], r15w
0x18001c93f  mov     r8d, edx
0x18001c942  lea     rcx, [rsp+8B0h+var_840]
0x18001c947  lea     rdx, aAddinterfaceto; "AddInterfaceToSourceMfe : cannot find p"...
0x18001c94e  call    FormatRRASErrorString
0x18001c953  mov     rdx, cs:qword_18002B8A8
0x18001c95a  lea     r8, [rsp+8B0h+var_840]
0x18001c95f  mov     rcx, cs:gMgmEtwContext
0x18001c966  mov     rax, cs:gMgmTemplateFunc
0x18001c96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c972  cmp     cs:dword_18002BA54, edi
0x18001c978  jb      loc_18001CA59
0x18001c97e  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001c985  xor     r9d, r9d; dwSubStringCount
0x18001c988  mov     [rsp+8B0h+dwErrorCode], 490h; dwErrorCode
0x18001c990  mov     r8d, 0C35Ah; dwMessageId
0x18001c996  mov     edx, edi; dwEventType
0x18001c998  mov     [rsp+8B0h+plpszSubStringArray], r15; plpszSubStringArray
0x18001c99d  call    cs:__imp_RouterLogEventA
0x18001c9a3  jmp     loc_18001CA59
0x18001c9a8  cmp     [rax+40h], r15
0x18001c9ac  jz      short loc_18001CA16
0x18001c9ae  cmp     cs:qword_18002B8A8, r15
0x18001c9b5  jz      short loc_18001C9F5
0x18001c9b7  mov     word ptr [rsp+8B0h+var_840], r15w
0x18001c9bd  lea     rdx, aInvokedJoinAle; "Invoked Join Alert for protocol %x, %x"
0x18001c9c4  mov     r9d, [rax+14h]
0x18001c9c8  lea     rcx, [rsp+8B0h+var_840]
0x18001c9cd  mov     r8d, [rax+10h]
0x18001c9d1  call    FormatRRASErrorString
0x18001c9d6  mov     rdx, cs:qword_18002B8A8
0x18001c9dd  lea     r8, [rsp+8B0h+var_840]
0x18001c9e2  mov     rcx, cs:gMgmEtwContext
0x18001c9e9  mov     rax, cs:gMgmTemplateFunc
0x18001c9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f5  mov     r9d, [r14+24h]
0x18001c9f9  mov     r8d, [r14+20h]
0x18001c9fd  mov     edx, [rbx+6Ch]
0x18001ca00  mov     ecx, [rbx+68h]
0x18001ca03  mov     rax, [rsi+40h]
0x18001ca07  mov     dword ptr [rsp+8B0h+plpszSubStringArray], r15d
0x18001ca0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca11  jmp     short loc_18001CA16
0x18001ca13  xor     r15d, r15d
0x18001ca16  cmp     [rbx+90h], r15d
0x18001ca1d  jz      short loc_18001CA59
0x18001ca1f  xor     r8d, r8d
0x18001ca22  mov     rdx, rbx
0x18001ca25  mov     rcx, r14
0x18001ca28  call    AddMfeToForwarder
0x18001ca2d  jmp     short loc_18001CA59
0x18001ca2f  mov     rax, [rsp+8B0h+var_868]
0x18001ca34  cmp     [rbp+7B0h+arg_30], r15d
0x18001ca3b  jz      short loc_18001CA4C
0x18001ca3d  mov     ecx, 8000h
0x18001ca42  or      [rax+22h], cx
0x18001ca46  add     [rax+24h], di
0x18001ca4a  jmp     short loc_18001CA59
0x18001ca4c  mov     ecx, 4000h
0x18001ca51  or      [rax+22h], cx
0x18001ca55  add     [rax+26h], di
0x18001ca59  mov     rcx, [rsp+8B0h+var_850]
0x18001ca5e  test    rcx, rcx
0x18001ca61  jz      short loc_18001CA6B
0x18001ca63  mov     rax, [rsp+8B0h+var_860]
0x18001ca68  mov     [rcx], rax
0x18001ca6b  mov     rcx, [rbp+7B0h+var_40]
0x18001ca72  xor     rcx, rsp; StackCookie
0x18001ca75  call    __security_check_cookie
0x18001ca7a  mov     rbx, [rsp+8B0h+arg_10]
0x18001ca82  add     rsp, 880h
0x18001ca89  pop     r15
0x18001ca8b  pop     r14
0x18001ca8d  pop     r13
0x18001ca8f  pop     r12
0x18001ca91  pop     rdi
0x18001ca92  pop     rsi
0x18001ca93  pop     rbp
0x18001ca94  retn
```
