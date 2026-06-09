# UWFUpdateAgent::filter(IUpdateCollection *,IUpdateCollection * *)

- ea: `0x18000490c`
- end: `0x180004a69`
- name: `?filter@UWFUpdateAgent@@AEAAJPEAUIUpdateCollection@@PEAPEAU2@@Z`
- size: `349`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdateCollection *, struct IUpdateCollection **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000399c`

## callees

- `0x180003d68`
- `0x180004008`
- `0x18000422c`
- `0x1800043f4`
- `0x18000490c`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::filter(
        UWFUpdateAgent *this,
        struct IUpdateCollection *a2,
        struct IUpdateCollection **a3)
{
  unsigned int v3; // ebx
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  __int64 result; // rax
  unsigned int v8; // esi
  struct IUpdateCollectionVtbl *v9; // rax
  UWFUpdateAgent *v10; // rcx
  UWFUpdateAgent *v11; // rcx
  UWFUpdateAgent *v12; // rcx
  UWFUpdateAgent *v13; // rcx
  UWFUpdateAgent *v14; // [rsp+50h] [rbp+30h] BYREF
  int v15; // [rsp+58h] [rbp+38h] BYREF
  struct IUpdate *v16; // [rsp+68h] [rbp+48h] BYREF

  v14 = this;
  v3 = 0;
  if ( !a2 )
    return v3;
  lpVtbl = a2->lpVtbl;
  LODWORD(v14) = 0;
  result = ((__int64 (__fastcall *)(struct IUpdateCollection *, struct IUpdateCollection **))lpVtbl->Copy)(a2, a3);
  if ( (int)result < 0 )
    return result;
  if ( !a3 )
    return result;
  result = ((__int64 (__fastcall *)(_QWORD))(*a3)->lpVtbl->Clear)(*a3);
  if ( (int)result < 0 )
    return result;
  result = ((__int64 (__fastcall *)(struct IUpdateCollection *, UWFUpdateAgent **))a2->lpVtbl->get_Count)(a2, &v14);
  v3 = result;
  if ( (int)result < 0 )
    return result;
  v8 = 0;
  if ( (int)v14 <= 0 )
    return v3;
  while ( 1 )
  {
    v9 = a2->lpVtbl;
    v16 = 0;
    v15 = 0;
    result = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, struct IUpdate **))v9->get_Item)(a2, v8, &v16);
    v3 = result;
    if ( (int)result < 0 || !v16 )
      break;
    if ( (unsigned int)UWFUpdateAgent::MatchCategories(v10, v16)
      || (unsigned int)UWFUpdateAgent::MatchSeverity(v11, v16)
      || (unsigned int)UWFUpdateAgent::MatchKBNumber(v12, v16)
      || (unsigned int)UWFUpdateAgent::MatchType(v13, v16) )
    {
      ((void (__fastcall *)(struct IUpdate *))v16->lpVtbl->AcceptEula)(v16);
      v3 = ((__int64 (__fastcall *)(_QWORD, struct IUpdate *, int *))(*a3)->lpVtbl->Add)(*a3, v16, &v15);
      ((void (__fastcall *)(struct IUpdate *))v16->lpVtbl->Release)(v16);
      if ( (v3 & 0x80000000) != 0 )
        return v3;
    }
    else
    {
      ((void (__fastcall *)(struct IUpdate *))v16->lpVtbl->Release)(v16);
    }
    if ( (int)++v8 >= (int)v14 )
      return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000490c  mov     [rsp-28h+arg_0], rcx
0x180004911  push    rbp
0x180004912  push    rbx
0x180004913  push    rsi
0x180004914  push    rdi
0x180004915  push    r14
0x180004917  mov     rbp, rsp
0x18000491a  sub     rsp, 20h
0x18000491e  xor     ebx, ebx
0x180004920  mov     r14, r8
0x180004923  mov     rdi, rdx
0x180004926  test    rdx, rdx
0x180004929  jz      loc_180004A5C
0x18000492f  mov     rax, [rdx]
0x180004932  mov     rcx, rdi
0x180004935  mov     rdx, r8
0x180004938  mov     dword ptr [rbp+arg_0], ebx
0x18000493b  mov     rax, [rax+70h]
0x18000493f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004944  test    eax, eax
0x180004946  js      loc_180004A5E
0x18000494c  test    r14, r14
0x18000494f  jz      loc_180004A5E
0x180004955  mov     rcx, [r14]
0x180004958  mov     rax, [rcx]
0x18000495b  mov     rax, [rax+68h]
0x18000495f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004964  test    eax, eax
0x180004966  js      loc_180004A5E
0x18000496c  mov     rax, [rdi]
0x18000496f  lea     rdx, [rbp+arg_0]
0x180004973  mov     rcx, rdi
0x180004976  mov     rax, [rax+50h]
0x18000497a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497f  mov     ebx, eax
0x180004981  test    eax, eax
0x180004983  js      loc_180004A5E
0x180004989  xor     esi, esi
0x18000498b  cmp     dword ptr [rbp+arg_0], esi
0x18000498e  jle     loc_180004A5C
0x180004994  mov     rax, [rdi]
0x180004997  lea     r8, [rbp+arg_18]
0x18000499b  mov     edx, esi
0x18000499d  mov     [rbp+arg_18], 0
0x1800049a5  mov     rcx, rdi
0x1800049a8  mov     [rbp+arg_8], 0
0x1800049af  mov     rax, [rax+38h]
0x1800049b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b8  mov     ebx, eax
0x1800049ba  test    eax, eax
0x1800049bc  js      loc_180004A5E
0x1800049c2  mov     rdx, [rbp+arg_18]; struct IUpdate *
0x1800049c6  test    rdx, rdx
0x1800049c9  jz      loc_180004A5E
0x1800049cf  call    ?MatchCategories@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z; UWFUpdateAgent::MatchCategories(IUpdate *)
0x1800049d4  test    eax, eax
0x1800049d6  jnz     short loc_180004A11
0x1800049d8  mov     rdx, [rbp+arg_18]; struct IUpdate *
0x1800049dc  call    ?MatchSeverity@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z; UWFUpdateAgent::MatchSeverity(IUpdate *)
0x1800049e1  test    eax, eax
0x1800049e3  jnz     short loc_180004A11
0x1800049e5  mov     rdx, [rbp+arg_18]; struct IUpdate *
0x1800049e9  call    ?MatchKBNumber@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z; UWFUpdateAgent::MatchKBNumber(IUpdate *)
0x1800049ee  test    eax, eax
0x1800049f0  jnz     short loc_180004A11
0x1800049f2  mov     rdx, [rbp+arg_18]; struct IUpdate *
0x1800049f6  call    ?MatchType@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z; UWFUpdateAgent::MatchType(IUpdate *)
0x1800049fb  test    eax, eax
0x1800049fd  jnz     short loc_180004A11
0x1800049ff  mov     rcx, [rbp+arg_18]
0x180004a03  mov     rax, [rcx]
0x180004a06  mov     rax, [rax+10h]
0x180004a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0f  jmp     short loc_180004A51
0x180004a11  mov     rcx, [rbp+arg_18]
0x180004a15  mov     rax, [rcx]
0x180004a18  mov     rax, [rax+178h]
0x180004a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a24  mov     rcx, [r14]
0x180004a27  lea     r8, [rbp+arg_8]
0x180004a2b  mov     rdx, [rbp+arg_18]
0x180004a2f  mov     rax, [rcx]
0x180004a32  mov     rax, [rax+60h]
0x180004a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a3b  mov     rcx, [rbp+arg_18]
0x180004a3f  mov     ebx, eax
0x180004a41  mov     rax, [rcx]
0x180004a44  mov     rax, [rax+10h]
0x180004a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4d  test    ebx, ebx
0x180004a4f  js      short loc_180004A5C
0x180004a51  inc     esi
0x180004a53  cmp     esi, dword ptr [rbp+arg_0]
0x180004a56  jl      loc_180004994
0x180004a5c  mov     eax, ebx
0x180004a5e  add     rsp, 20h
0x180004a62  pop     r14
0x180004a64  pop     rdi
0x180004a65  pop     rsi
0x180004a66  pop     rbx
0x180004a67  pop     rbp
0x180004a68  retn
```
