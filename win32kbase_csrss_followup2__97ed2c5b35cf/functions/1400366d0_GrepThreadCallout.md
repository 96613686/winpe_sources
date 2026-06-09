# GrepThreadCallout

- ea: `0x1400366d0`
- end: `0x1400369e3`
- name: `GrepThreadCallout`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400366a0`

## callees

- `0x14000db3c`
- `0x140024f80`
- `0x1400366d0`
- `0x1400efd70`
- `0x14016d840`
- `0x1401e1948`
- `0x140238240`

## import_xrefs

- `WIN32K!DxDdThreadCallout` at `0x140036758`
- `WIN32K!DxDdThreadCallout` at `0x14003689a`
- `WIN32K!DxDdThreadCallout` at `0x140036758`
- `WIN32K!DxDdThreadCallout` at `0x14003689a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400366e2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036768`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400367a2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400367cf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036807`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036849`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400368ab`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400368d5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036911`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003693e`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400366e2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036768`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400367a2`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400367cf`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036807`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036849`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400368ab`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400368d5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140036911`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14003693e`
- `WIN32K!W32GetSessionState` at `0x140036997`
- `WIN32K!W32GetSessionState` at `0x140036997`

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
0x1400366d0  push    rbx
0x1400366d2  push    rbp
0x1400366d3  push    rsi
0x1400366d4  push    rdi
0x1400366d5  push    r14
0x1400366d7  sub     rsp, 20h
0x1400366db  mov     edi, edx
0x1400366dd  mov     rbx, rcx
0x1400366e0  xor     esi, esi
0x1400366e2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400366e9  nop     dword ptr [rax+rax+00h]
0x1400366ee  mov     r8, [rax+18h]
0x1400366f2  mov     rax, [r8+540h]
0x1400366f9  test    rax, rax
0x1400366fc  jz      short loc_140036707
0x1400366fe  call    _guard_dispatch_icall
0x140036703  test    eax, eax
0x140036705  jns     short loc_140036768
0x140036707  test    edi, edi
0x140036709  jz      short loc_140036722
0x14003670b  cmp     edi, 1
0x14003670e  jz      loc_1400367F9
0x140036714  mov     eax, esi
0x140036716  add     rsp, 20h
0x14003671a  pop     r14
0x14003671c  pop     rdi
0x14003671d  pop     rsi
0x14003671e  pop     rbp
0x14003671f  pop     rbx
0x140036720  retn
0x140036722  lea     rax, [rbx+48h]
0x140036726  mov     [rax+8], rax
0x14003672a  lea     rcx, [rbx-8]
0x14003672e  mov     [rax], rax
0x140036731  lea     rax, [rbx+58h]
0x140036735  mov     [rax+8], rax
0x140036739  mov     [rax], rax
0x14003673c  lea     rax, [rbx+68h]
0x140036740  mov     [rbx+110h], rax
0x140036747  test    rcx, rcx
0x14003674a  jz      short loc_140036714
0x14003674c  add     rcx, 180h
0x140036753  mov     dl, 1
0x140036755  mov     [rcx], rsi
0x140036758  call    cs:__imp_DxDdThreadCallout
0x14003675f  nop     dword ptr [rax+rax+00h]
0x140036764  mov     esi, eax
0x140036766  jmp     short loc_140036714
0x140036768  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003676f  nop     dword ptr [rax+rax+00h]
0x140036774  mov     rcx, [rax+18h]
0x140036778  mov     rax, [rcx+548h]
0x14003677f  test    rax, rax
0x140036782  jz      short loc_140036707
0x140036784  call    _guard_dispatch_icall
0x140036789  test    eax, eax
0x14003678b  jz      loc_140036707
0x140036791  test    edi, edi
0x140036793  jz      loc_14003696B
0x140036799  cmp     edi, 1
0x14003679c  jnz     loc_140036714
0x1400367a2  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400367a9  nop     dword ptr [rax+rax+00h]
0x1400367ae  mov     rcx, [rax+18h]
0x1400367b2  mov     rax, [rcx+560h]
0x1400367b9  test    rax, rax
0x1400367bc  jz      loc_140036714
0x1400367c2  call    _guard_dispatch_icall
0x1400367c7  test    eax, eax
0x1400367c9  js      loc_140036714
0x1400367cf  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400367d6  nop     dword ptr [rax+rax+00h]
0x1400367db  mov     rcx, [rax+18h]
0x1400367df  mov     rax, [rcx+568h]
0x1400367e6  test    rax, rax
0x1400367e9  jz      loc_140036714
0x1400367ef  call    _guard_dispatch_icall
0x1400367f4  jmp     loc_140036714
0x1400367f9  call    ?Get@ThreadRestrictNewHandlesRegion@@SAPEAV1@XZ; ThreadRestrictNewHandlesRegion::Get(void)
0x1400367fe  test    rax, rax
0x140036801  jnz     loc_14003698A
0x140036807  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x14003680e  nop     dword ptr [rax+rax+00h]
0x140036813  mov     rcx, [rax+18h]
0x140036817  mov     rax, [rcx+990h]
0x14003681e  test    rax, rax
0x140036821  jz      short loc_14003682C
0x140036823  call    _guard_dispatch_icall
0x140036828  test    eax, eax
0x14003682a  jns     short loc_1400368AB
0x14003682c  mov     rdi, [rbx+20h]
0x140036830  test    rdi, rdi
0x140036833  jnz     loc_140036997
0x140036839  lea     rdi, [rbx+58h]
0x14003683d  mov     rcx, [rdi]
0x140036840  cmp     rcx, rdi
0x140036843  jnz     loc_1400369B4
0x140036849  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140036850  nop     dword ptr [rax+rax+00h]
0x140036855  mov     rcx, [rax+18h]
0x140036859  mov     rax, [rcx+9A0h]
0x140036860  test    rax, rax
0x140036863  jz      short loc_14003686E
0x140036865  call    _guard_dispatch_icall
0x14003686a  test    eax, eax
0x14003686c  jns     short loc_1400368D5
0x14003686e  mov     rdi, [rbx+118h]
0x140036875  test    rdi, rdi
0x140036878  jnz     loc_140036902
0x14003687e  add     rbx, 0FFFFFFFFFFFFFFF8h
0x140036882  jz      loc_140036714
0x140036888  lea     rcx, [rbx+180h]
0x14003688f  cmp     [rcx], rsi
0x140036892  jz      loc_140036714
0x140036898  xor     edx, edx
0x14003689a  call    cs:__imp_DxDdThreadCallout
0x1400368a1  nop     dword ptr [rax+rax+00h]
0x1400368a6  jmp     loc_140036714
0x1400368ab  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400368b2  nop     dword ptr [rax+rax+00h]
0x1400368b7  mov     rcx, [rax+18h]
0x1400368bb  mov     rax, [rcx+998h]
0x1400368c2  test    rax, rax
0x1400368c5  jz      loc_14003682C
0x1400368cb  call    _guard_dispatch_icall
0x1400368d0  jmp     loc_14003682C
0x1400368d5  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400368dc  nop     dword ptr [rax+rax+00h]
0x1400368e1  mov     rcx, [rax+18h]
0x1400368e5  mov     rax, [rcx+9A8h]
0x1400368ec  test    rax, rax
0x1400368ef  jz      loc_14003686E
0x1400368f5  mov     rcx, rbx
0x1400368f8  call    _guard_dispatch_icall
0x1400368fd  jmp     loc_14003686E
0x140036902  mov     [rbx+118h], rsi
0x140036909  mov     rcx, [rdi]
0x14003690c  call    bDeletePalette
0x140036911  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140036918  nop     dword ptr [rax+rax+00h]
0x14003691d  mov     rcx, [rax+18h]
0x140036921  mov     rax, [rcx+9B0h]
0x140036928  test    rax, rax
0x14003692b  jz      loc_14003687E
0x140036931  call    _guard_dispatch_icall
0x140036936  test    eax, eax
0x140036938  js      loc_14003687E
0x14003693e  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x140036945  nop     dword ptr [rax+rax+00h]
0x14003694a  mov     rdx, [rax+18h]
0x14003694e  mov     rax, [rdx+9B8h]
0x140036955  test    rax, rax
0x140036958  jz      loc_14003687E
0x14003695e  mov     rcx, rdi
0x140036961  call    _guard_dispatch_icall
0x140036966  jmp     loc_14003687E
0x14003696b  test    rbx, rbx
0x14003696e  jnz     short loc_14003697A
0x140036970  mov     esi, 0C0000017h
0x140036975  jmp     loc_140036714
0x14003697a  lea     rcx, [rbx+58h]
0x14003697e  mov     [rcx+8], rcx
0x140036982  mov     [rcx], rcx
0x140036985  jmp     loc_140036714
0x14003698a  mov     rcx, rax; this
0x14003698d  call    ?OnThreadTermination@ThreadRestrictNewHandlesRegion@@QEAAXXZ; ThreadRestrictNewHandlesRegion::OnThreadTermination(void)
0x140036992  jmp     loc_140036807
0x140036997  call    cs:__imp_W32GetSessionState
0x14003699e  nop     dword ptr [rax+rax+00h]
0x1400369a3  mov     rdx, rdi
0x1400369a6  mov     rcx, [rax+58h]
0x1400369aa  call    HmgFreeDcAttr
0x1400369af  jmp     loc_140036839
0x1400369b4  test    rcx, rcx
0x1400369b7  jz      loc_14003683D
0x1400369bd  mov     r14, [rcx+10h]
0x1400369c1  mov     rbp, [rcx+18h]
0x1400369c5  call    PopThreadGuardedObject
0x1400369ca  test    rbp, rbp
0x1400369cd  jz      loc_14003683D
0x1400369d3  mov     rcx, r14
0x1400369d6  mov     rax, rbp
0x1400369d9  call    _guard_dispatch_icall
0x1400369de  jmp     loc_14003683D
```
