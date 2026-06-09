# GrepThreadCallout

- ea: `0x14002d450`
- end: `0x14002d763`
- name: `GrepThreadCallout`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002d420`

## callees

- `0x14001bf60`
- `0x14002d450`
- `0x140091f1c`
- `0x1400f26f0`
- `0x14016d0a0`
- `0x1401e1fd8`
- `0x140238bf0`

## import_xrefs

- `WIN32K!DxDdThreadCallout` at `0x14002d4d8`
- `WIN32K!DxDdThreadCallout` at `0x14002d61a`
- `WIN32K!DxDdThreadCallout` at `0x14002d4d8`
- `WIN32K!DxDdThreadCallout` at `0x14002d61a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d462`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d4e8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d522`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d54f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d587`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d5c9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d62b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d655`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d691`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d6be`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d462`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d4e8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d522`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d54f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d587`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d5c9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d62b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d655`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d691`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14002d6be`
- `WIN32K!W32GetSessionState` at `0x14002d717`
- `WIN32K!W32GetSessionState` at `0x14002d717`

## pseudocode

```c
__int64 __fastcall GrepThreadCallout(_QWORD *a1, int a2)
{
  unsigned int v4; // esi
  int (*v5)(void); // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v9; // rcx
  unsigned int (*v10)(void); // rax
  __int64 v11; // rcx
  int (*v12)(void); // rax
  __int64 v13; // rcx
  void (*v14)(void); // rax
  ThreadRestrictNewHandlesRegion *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  int (*v18)(void); // rax
  __int64 v19; // rdi
  _QWORD *v20; // rdi
  _QWORD *v21; // rcx
  int (*v22)(void); // rax
  __int64 v23; // rcx
  _QWORD *v24; // rdi
  _QWORD *v25; // rbx
  void (*v26)(void); // rax
  void (__fastcall *v27)(_QWORD *); // rax
  __int64 v28; // rcx
  int (*v29)(void); // rax
  __int64 v30; // rcx
  void (__fastcall *v31)(_QWORD *); // rax
  __int64 SessionState; // rax
  __int64 v33; // r14
  void (__fastcall *v34)(__int64); // rbp

  v4 = 0;
  v5 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(a1) + 24) + 1344LL);
  if ( v5
    && v5() >= 0
    && (v10 = *(unsigned int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v7) + 24) + 1352LL)) != 0
    && v10() )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v12 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v11) + 24) + 1376LL);
        if ( v12 )
        {
          if ( v12() >= 0 )
          {
            v14 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v13) + 24) + 1384LL);
            if ( v14 )
              v14();
          }
        }
      }
    }
    else if ( a1 )
    {
      a1[12] = a1 + 11;
      a1[11] = a1 + 11;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else if ( a2 )
  {
    if ( a2 == 1 )
    {
      v15 = ThreadRestrictNewHandlesRegion::Get();
      if ( v15 )
        ThreadRestrictNewHandlesRegion::OnThreadTermination(v15);
      v17 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v16) + 24);
      v18 = *(int (**)(void))(v17 + 2448);
      if ( v18 )
      {
        if ( v18() >= 0 )
        {
          v17 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v17) + 24);
          v26 = *(void (**)(void))(v17 + 2456);
          if ( v26 )
            v26();
        }
      }
      v19 = a1[4];
      if ( v19 )
      {
        SessionState = W32GetSessionState(v17);
        HmgFreeDcAttr(*(_QWORD *)(SessionState + 88), v19);
      }
      v20 = a1 + 11;
      while ( 1 )
      {
        v21 = (_QWORD *)*v20;
        if ( (_QWORD *)*v20 == v20 )
          break;
        if ( v21 )
        {
          v33 = v21[2];
          v34 = (void (__fastcall *)(__int64))v21[3];
          PopThreadGuardedObject(v21);
          if ( v34 )
            v34(v33);
        }
      }
      v22 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v21) + 24) + 2464LL);
      if ( v22 )
      {
        if ( v22() >= 0 )
        {
          v27 = *(void (__fastcall **)(_QWORD *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v23) + 24) + 2472LL);
          if ( v27 )
            v27(a1);
        }
      }
      v24 = (_QWORD *)a1[35];
      if ( v24 )
      {
        a1[35] = 0;
        bDeletePalette(*v24);
        v29 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v28) + 24) + 2480LL);
        if ( v29 )
        {
          if ( v29() >= 0 )
          {
            v31 = *(void (__fastcall **)(_QWORD *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v30) + 24) + 2488LL);
            if ( v31 )
              v31(v24);
          }
        }
      }
      v25 = a1 - 1;
      if ( v25 && v25[48] )
        DxDdThreadCallout(v25 + 48, 0);
    }
  }
  else
  {
    a1[10] = a1 + 9;
    a1[9] = a1 + 9;
    a1[12] = a1 + 11;
    a1[11] = a1 + 11;
    a1[34] = a1 + 13;
    if ( a1 != (_QWORD *)8 )
    {
      v9 = a1 + 47;
      LOBYTE(v6) = 1;
      *v9 = 0;
      return (unsigned int)DxDdThreadCallout(v9, v6);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14002d450  push    rbx
0x14002d452  push    rbp
0x14002d453  push    rsi
0x14002d454  push    rdi
0x14002d455  push    r14
0x14002d457  sub     rsp, 20h
0x14002d45b  mov     edi, edx
0x14002d45d  mov     rbx, rcx
0x14002d460  xor     esi, esi
0x14002d462  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d469  nop     dword ptr [rax+rax+00h]
0x14002d46e  mov     r8, [rax+18h]
0x14002d472  mov     rax, [r8+540h]
0x14002d479  test    rax, rax
0x14002d47c  jz      short loc_14002D487
0x14002d47e  call    _guard_dispatch_icall
0x14002d483  test    eax, eax
0x14002d485  jns     short loc_14002D4E8
0x14002d487  test    edi, edi
0x14002d489  jz      short loc_14002D4A2
0x14002d48b  cmp     edi, 1
0x14002d48e  jz      loc_14002D579
0x14002d494  mov     eax, esi
0x14002d496  add     rsp, 20h
0x14002d49a  pop     r14
0x14002d49c  pop     rdi
0x14002d49d  pop     rsi
0x14002d49e  pop     rbp
0x14002d49f  pop     rbx
0x14002d4a0  retn
0x14002d4a2  lea     rax, [rbx+48h]
0x14002d4a6  mov     [rax+8], rax
0x14002d4aa  lea     rcx, [rbx-8]
0x14002d4ae  mov     [rax], rax
0x14002d4b1  lea     rax, [rbx+58h]
0x14002d4b5  mov     [rax+8], rax
0x14002d4b9  mov     [rax], rax
0x14002d4bc  lea     rax, [rbx+68h]
0x14002d4c0  mov     [rbx+110h], rax
0x14002d4c7  test    rcx, rcx
0x14002d4ca  jz      short loc_14002D494
0x14002d4cc  add     rcx, 180h
0x14002d4d3  mov     dl, 1
0x14002d4d5  mov     [rcx], rsi
0x14002d4d8  call    cs:__imp_DxDdThreadCallout
0x14002d4df  nop     dword ptr [rax+rax+00h]
0x14002d4e4  mov     esi, eax
0x14002d4e6  jmp     short loc_14002D494
0x14002d4e8  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d4ef  nop     dword ptr [rax+rax+00h]
0x14002d4f4  mov     rcx, [rax+18h]
0x14002d4f8  mov     rax, [rcx+548h]
0x14002d4ff  test    rax, rax
0x14002d502  jz      short loc_14002D487
0x14002d504  call    _guard_dispatch_icall
0x14002d509  test    eax, eax
0x14002d50b  jz      loc_14002D487
0x14002d511  test    edi, edi
0x14002d513  jz      loc_14002D6EB
0x14002d519  cmp     edi, 1
0x14002d51c  jnz     loc_14002D494
0x14002d522  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d529  nop     dword ptr [rax+rax+00h]
0x14002d52e  mov     rcx, [rax+18h]
0x14002d532  mov     rax, [rcx+560h]
0x14002d539  test    rax, rax
0x14002d53c  jz      loc_14002D494
0x14002d542  call    _guard_dispatch_icall
0x14002d547  test    eax, eax
0x14002d549  js      loc_14002D494
0x14002d54f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d556  nop     dword ptr [rax+rax+00h]
0x14002d55b  mov     rcx, [rax+18h]
0x14002d55f  mov     rax, [rcx+568h]
0x14002d566  test    rax, rax
0x14002d569  jz      loc_14002D494
0x14002d56f  call    _guard_dispatch_icall
0x14002d574  jmp     loc_14002D494
0x14002d579  call    ?Get@ThreadRestrictNewHandlesRegion@@SAPEAV1@XZ; ThreadRestrictNewHandlesRegion::Get(void)
0x14002d57e  test    rax, rax
0x14002d581  jnz     loc_14002D70A
0x14002d587  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d58e  nop     dword ptr [rax+rax+00h]
0x14002d593  mov     rcx, [rax+18h]
0x14002d597  mov     rax, [rcx+990h]
0x14002d59e  test    rax, rax
0x14002d5a1  jz      short loc_14002D5AC
0x14002d5a3  call    _guard_dispatch_icall
0x14002d5a8  test    eax, eax
0x14002d5aa  jns     short loc_14002D62B
0x14002d5ac  mov     rdi, [rbx+20h]
0x14002d5b0  test    rdi, rdi
0x14002d5b3  jnz     loc_14002D717
0x14002d5b9  lea     rdi, [rbx+58h]
0x14002d5bd  mov     rcx, [rdi]
0x14002d5c0  cmp     rcx, rdi
0x14002d5c3  jnz     loc_14002D734
0x14002d5c9  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d5d0  nop     dword ptr [rax+rax+00h]
0x14002d5d5  mov     rcx, [rax+18h]
0x14002d5d9  mov     rax, [rcx+9A0h]
0x14002d5e0  test    rax, rax
0x14002d5e3  jz      short loc_14002D5EE
0x14002d5e5  call    _guard_dispatch_icall
0x14002d5ea  test    eax, eax
0x14002d5ec  jns     short loc_14002D655
0x14002d5ee  mov     rdi, [rbx+118h]
0x14002d5f5  test    rdi, rdi
0x14002d5f8  jnz     loc_14002D682
0x14002d5fe  add     rbx, 0FFFFFFFFFFFFFFF8h
0x14002d602  jz      loc_14002D494
0x14002d608  lea     rcx, [rbx+180h]
0x14002d60f  cmp     [rcx], rsi
0x14002d612  jz      loc_14002D494
0x14002d618  xor     edx, edx
0x14002d61a  call    cs:__imp_DxDdThreadCallout
0x14002d621  nop     dword ptr [rax+rax+00h]
0x14002d626  jmp     loc_14002D494
0x14002d62b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d632  nop     dword ptr [rax+rax+00h]
0x14002d637  mov     rcx, [rax+18h]
0x14002d63b  mov     rax, [rcx+998h]
0x14002d642  test    rax, rax
0x14002d645  jz      loc_14002D5AC
0x14002d64b  call    _guard_dispatch_icall
0x14002d650  jmp     loc_14002D5AC
0x14002d655  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d65c  nop     dword ptr [rax+rax+00h]
0x14002d661  mov     rcx, [rax+18h]
0x14002d665  mov     rax, [rcx+9A8h]
0x14002d66c  test    rax, rax
0x14002d66f  jz      loc_14002D5EE
0x14002d675  mov     rcx, rbx
0x14002d678  call    _guard_dispatch_icall
0x14002d67d  jmp     loc_14002D5EE
0x14002d682  mov     [rbx+118h], rsi
0x14002d689  mov     rcx, [rdi]
0x14002d68c  call    bDeletePalette
0x14002d691  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d698  nop     dword ptr [rax+rax+00h]
0x14002d69d  mov     rcx, [rax+18h]
0x14002d6a1  mov     rax, [rcx+9B0h]
0x14002d6a8  test    rax, rax
0x14002d6ab  jz      loc_14002D5FE
0x14002d6b1  call    _guard_dispatch_icall
0x14002d6b6  test    eax, eax
0x14002d6b8  js      loc_14002D5FE
0x14002d6be  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14002d6c5  nop     dword ptr [rax+rax+00h]
0x14002d6ca  mov     rdx, [rax+18h]
0x14002d6ce  mov     rax, [rdx+9B8h]
0x14002d6d5  test    rax, rax
0x14002d6d8  jz      loc_14002D5FE
0x14002d6de  mov     rcx, rdi
0x14002d6e1  call    _guard_dispatch_icall
0x14002d6e6  jmp     loc_14002D5FE
0x14002d6eb  test    rbx, rbx
0x14002d6ee  jnz     short loc_14002D6FA
0x14002d6f0  mov     esi, 0C0000017h
0x14002d6f5  jmp     loc_14002D494
0x14002d6fa  lea     rcx, [rbx+58h]
0x14002d6fe  mov     [rcx+8], rcx
0x14002d702  mov     [rcx], rcx
0x14002d705  jmp     loc_14002D494
0x14002d70a  mov     rcx, rax; this
0x14002d70d  call    ?OnThreadTermination@ThreadRestrictNewHandlesRegion@@QEAAXXZ; ThreadRestrictNewHandlesRegion::OnThreadTermination(void)
0x14002d712  jmp     loc_14002D587
0x14002d717  call    cs:__imp_W32GetSessionState
0x14002d71e  nop     dword ptr [rax+rax+00h]
0x14002d723  mov     rdx, rdi
0x14002d726  mov     rcx, [rax+58h]
0x14002d72a  call    HmgFreeDcAttr
0x14002d72f  jmp     loc_14002D5B9
0x14002d734  test    rcx, rcx
0x14002d737  jz      loc_14002D5BD
0x14002d73d  mov     r14, [rcx+10h]
0x14002d741  mov     rbp, [rcx+18h]
0x14002d745  call    PopThreadGuardedObject
0x14002d74a  test    rbp, rbp
0x14002d74d  jz      loc_14002D5BD
0x14002d753  mov     rcx, r14
0x14002d756  mov     rax, rbp
0x14002d759  call    _guard_dispatch_icall
0x14002d75e  jmp     loc_14002D5BD
```
