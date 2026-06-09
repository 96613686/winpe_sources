# GrepThreadCallout

- ea: `0x1400d7f40`
- end: `0x1400d8253`
- name: `GrepThreadCallout`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400d7f10`

## callees

- `0x14000d65c`
- `0x14000f9b0`
- `0x1400317e0`
- `0x1400d7f40`
- `0x1400f5b90`
- `0x1401e2488`
- `0x1402389c0`

## import_xrefs

- `WIN32K!DxDdThreadCallout` at `0x1400d7fc8`
- `WIN32K!DxDdThreadCallout` at `0x1400d810a`
- `WIN32K!DxDdThreadCallout` at `0x1400d7fc8`
- `WIN32K!DxDdThreadCallout` at `0x1400d810a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d7f52`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d7fd8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8012`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d803f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8077`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d80b9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d811b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8145`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8181`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d81ae`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d7f52`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d7fd8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8012`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d803f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8077`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d80b9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d811b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8145`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d8181`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400d81ae`
- `WIN32K!W32GetSessionState` at `0x1400d8207`
- `WIN32K!W32GetSessionState` at `0x1400d8207`

## pseudocode

```c
__int64 __fastcall GrepThreadCallout(_QWORD *a1, __int64 a2)
{
  int v2; // edi
  unsigned int v4; // esi
  int (*v5)(void); // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v9; // rcx
  unsigned int (*v10)(void); // rax
  __int64 v11; // rcx
  int (*v12)(void); // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  void (*v15)(void); // rax
  ThreadRestrictNewHandlesRegion *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  int (*v21)(void); // rax
  __int64 v22; // rdi
  _QWORD *v23; // rdi
  _QWORD *v24; // rcx
  int (*v25)(void); // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // rdi
  _QWORD *v29; // rbx
  void (*v30)(void); // rax
  void (__fastcall *v31)(_QWORD *); // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  int (*v34)(void); // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  void (__fastcall *v37)(_QWORD *); // rax
  __int64 SessionState; // rax
  __int64 v39; // r14
  void (__fastcall *v40)(__int64); // rbp

  v2 = a2;
  v4 = 0;
  v5 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(a1, a2) + 24) + 1344LL);
  if ( v5
    && v5() >= 0
    && (v10 = *(unsigned int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v7, v6) + 24) + 1352LL)) != 0
    && v10() )
  {
    if ( v2 )
    {
      if ( v2 == 1 )
      {
        v12 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v11, v6) + 24) + 1376LL);
        if ( v12 )
        {
          if ( v12() >= 0 )
          {
            v15 = *(void (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v14, v13) + 24) + 1384LL);
            if ( v15 )
              v15();
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
  else if ( v2 )
  {
    if ( v2 == 1 )
    {
      v16 = ThreadRestrictNewHandlesRegion::Get();
      if ( v16 )
        ThreadRestrictNewHandlesRegion::OnThreadTermination(v16);
      v20 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v18, v17) + 24);
      v21 = *(int (**)(void))(v20 + 2448);
      if ( v21 )
      {
        if ( v21() >= 0 )
        {
          v20 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v20, v19) + 24);
          v30 = *(void (**)(void))(v20 + 2456);
          if ( v30 )
            v30();
        }
      }
      v22 = a1[4];
      if ( v22 )
      {
        SessionState = W32GetSessionState(v20);
        HmgFreeDcAttr(*(_QWORD *)(SessionState + 88), v22);
      }
      v23 = a1 + 11;
      while ( 1 )
      {
        v24 = (_QWORD *)*v23;
        if ( (_QWORD *)*v23 == v23 )
          break;
        if ( v24 )
        {
          v39 = v24[2];
          v40 = (void (__fastcall *)(__int64))v24[3];
          PopThreadGuardedObject(v24);
          if ( v40 )
            v40(v39);
        }
      }
      v25 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v24, v19) + 24) + 2464LL);
      if ( v25 )
      {
        if ( v25() >= 0 )
        {
          v31 = *(void (__fastcall **)(_QWORD *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v27, v26) + 24) + 2472LL);
          if ( v31 )
            v31(a1);
        }
      }
      v28 = (_QWORD *)a1[35];
      if ( v28 )
      {
        a1[35] = 0;
        bDeletePalette(*v28);
        v34 = *(int (**)(void))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v33, v32) + 24) + 2480LL);
        if ( v34 )
        {
          if ( v34() >= 0 )
          {
            v37 = *(void (__fastcall **)(_QWORD *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v36, v35) + 24) + 2488LL);
            if ( v37 )
              v37(v28);
          }
        }
      }
      v29 = a1 - 1;
      if ( v29 && v29[48] )
        DxDdThreadCallout(v29 + 48, 0);
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
0x1400d7f40  push    rbx
0x1400d7f42  push    rbp
0x1400d7f43  push    rsi
0x1400d7f44  push    rdi
0x1400d7f45  push    r14
0x1400d7f47  sub     rsp, 20h
0x1400d7f4b  mov     edi, edx
0x1400d7f4d  mov     rbx, rcx
0x1400d7f50  xor     esi, esi
0x1400d7f52  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d7f59  nop     dword ptr [rax+rax+00h]
0x1400d7f5e  mov     r8, [rax+18h]
0x1400d7f62  mov     rax, [r8+540h]
0x1400d7f69  test    rax, rax
0x1400d7f6c  jz      short loc_1400D7F77
0x1400d7f6e  call    _guard_dispatch_icall
0x1400d7f73  test    eax, eax
0x1400d7f75  jns     short loc_1400D7FD8
0x1400d7f77  test    edi, edi
0x1400d7f79  jz      short loc_1400D7F92
0x1400d7f7b  cmp     edi, 1
0x1400d7f7e  jz      loc_1400D8069
0x1400d7f84  mov     eax, esi
0x1400d7f86  add     rsp, 20h
0x1400d7f8a  pop     r14
0x1400d7f8c  pop     rdi
0x1400d7f8d  pop     rsi
0x1400d7f8e  pop     rbp
0x1400d7f8f  pop     rbx
0x1400d7f90  retn
0x1400d7f92  lea     rax, [rbx+48h]
0x1400d7f96  mov     [rax+8], rax
0x1400d7f9a  lea     rcx, [rbx-8]
0x1400d7f9e  mov     [rax], rax
0x1400d7fa1  lea     rax, [rbx+58h]
0x1400d7fa5  mov     [rax+8], rax
0x1400d7fa9  mov     [rax], rax
0x1400d7fac  lea     rax, [rbx+68h]
0x1400d7fb0  mov     [rbx+110h], rax
0x1400d7fb7  test    rcx, rcx
0x1400d7fba  jz      short loc_1400D7F84
0x1400d7fbc  add     rcx, 180h
0x1400d7fc3  mov     dl, 1
0x1400d7fc5  mov     [rcx], rsi
0x1400d7fc8  call    cs:__imp_DxDdThreadCallout
0x1400d7fcf  nop     dword ptr [rax+rax+00h]
0x1400d7fd4  mov     esi, eax
0x1400d7fd6  jmp     short loc_1400D7F84
0x1400d7fd8  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d7fdf  nop     dword ptr [rax+rax+00h]
0x1400d7fe4  mov     rcx, [rax+18h]
0x1400d7fe8  mov     rax, [rcx+548h]
0x1400d7fef  test    rax, rax
0x1400d7ff2  jz      short loc_1400D7F77
0x1400d7ff4  call    _guard_dispatch_icall
0x1400d7ff9  test    eax, eax
0x1400d7ffb  jz      loc_1400D7F77
0x1400d8001  test    edi, edi
0x1400d8003  jz      loc_1400D81DB
0x1400d8009  cmp     edi, 1
0x1400d800c  jnz     loc_1400D7F84
0x1400d8012  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d8019  nop     dword ptr [rax+rax+00h]
0x1400d801e  mov     rcx, [rax+18h]
0x1400d8022  mov     rax, [rcx+560h]
0x1400d8029  test    rax, rax
0x1400d802c  jz      loc_1400D7F84
0x1400d8032  call    _guard_dispatch_icall
0x1400d8037  test    eax, eax
0x1400d8039  js      loc_1400D7F84
0x1400d803f  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d8046  nop     dword ptr [rax+rax+00h]
0x1400d804b  mov     rcx, [rax+18h]
0x1400d804f  mov     rax, [rcx+568h]
0x1400d8056  test    rax, rax
0x1400d8059  jz      loc_1400D7F84
0x1400d805f  call    _guard_dispatch_icall
0x1400d8064  jmp     loc_1400D7F84
0x1400d8069  call    ?Get@ThreadRestrictNewHandlesRegion@@SAPEAV1@XZ; ThreadRestrictNewHandlesRegion::Get(void)
0x1400d806e  test    rax, rax
0x1400d8071  jnz     loc_1400D81FA
0x1400d8077  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d807e  nop     dword ptr [rax+rax+00h]
0x1400d8083  mov     rcx, [rax+18h]
0x1400d8087  mov     rax, [rcx+990h]
0x1400d808e  test    rax, rax
0x1400d8091  jz      short loc_1400D809C
0x1400d8093  call    _guard_dispatch_icall
0x1400d8098  test    eax, eax
0x1400d809a  jns     short loc_1400D811B
0x1400d809c  mov     rdi, [rbx+20h]
0x1400d80a0  test    rdi, rdi
0x1400d80a3  jnz     loc_1400D8207
0x1400d80a9  lea     rdi, [rbx+58h]
0x1400d80ad  mov     rcx, [rdi]
0x1400d80b0  cmp     rcx, rdi
0x1400d80b3  jnz     loc_1400D8224
0x1400d80b9  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d80c0  nop     dword ptr [rax+rax+00h]
0x1400d80c5  mov     rcx, [rax+18h]
0x1400d80c9  mov     rax, [rcx+9A0h]
0x1400d80d0  test    rax, rax
0x1400d80d3  jz      short loc_1400D80DE
0x1400d80d5  call    _guard_dispatch_icall
0x1400d80da  test    eax, eax
0x1400d80dc  jns     short loc_1400D8145
0x1400d80de  mov     rdi, [rbx+118h]
0x1400d80e5  test    rdi, rdi
0x1400d80e8  jnz     loc_1400D8172
0x1400d80ee  add     rbx, 0FFFFFFFFFFFFFFF8h
0x1400d80f2  jz      loc_1400D7F84
0x1400d80f8  lea     rcx, [rbx+180h]
0x1400d80ff  cmp     [rcx], rsi
0x1400d8102  jz      loc_1400D7F84
0x1400d8108  xor     edx, edx
0x1400d810a  call    cs:__imp_DxDdThreadCallout
0x1400d8111  nop     dword ptr [rax+rax+00h]
0x1400d8116  jmp     loc_1400D7F84
0x1400d811b  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d8122  nop     dword ptr [rax+rax+00h]
0x1400d8127  mov     rcx, [rax+18h]
0x1400d812b  mov     rax, [rcx+998h]
0x1400d8132  test    rax, rax
0x1400d8135  jz      loc_1400D809C
0x1400d813b  call    _guard_dispatch_icall
0x1400d8140  jmp     loc_1400D809C
0x1400d8145  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d814c  nop     dword ptr [rax+rax+00h]
0x1400d8151  mov     rcx, [rax+18h]
0x1400d8155  mov     rax, [rcx+9A8h]
0x1400d815c  test    rax, rax
0x1400d815f  jz      loc_1400D80DE
0x1400d8165  mov     rcx, rbx
0x1400d8168  call    _guard_dispatch_icall
0x1400d816d  jmp     loc_1400D80DE
0x1400d8172  mov     [rbx+118h], rsi
0x1400d8179  mov     rcx, [rdi]
0x1400d817c  call    bDeletePalette
0x1400d8181  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d8188  nop     dword ptr [rax+rax+00h]
0x1400d818d  mov     rcx, [rax+18h]
0x1400d8191  mov     rax, [rcx+9B0h]
0x1400d8198  test    rax, rax
0x1400d819b  jz      loc_1400D80EE
0x1400d81a1  call    _guard_dispatch_icall
0x1400d81a6  test    eax, eax
0x1400d81a8  js      loc_1400D80EE
0x1400d81ae  call    cs:__imp_W32GetWin32kBaseApiSetTable
0x1400d81b5  nop     dword ptr [rax+rax+00h]
0x1400d81ba  mov     rdx, [rax+18h]
0x1400d81be  mov     rax, [rdx+9B8h]
0x1400d81c5  test    rax, rax
0x1400d81c8  jz      loc_1400D80EE
0x1400d81ce  mov     rcx, rdi
0x1400d81d1  call    _guard_dispatch_icall
0x1400d81d6  jmp     loc_1400D80EE
0x1400d81db  test    rbx, rbx
0x1400d81de  jnz     short loc_1400D81EA
0x1400d81e0  mov     esi, 0C0000017h
0x1400d81e5  jmp     loc_1400D7F84
0x1400d81ea  lea     rcx, [rbx+58h]
0x1400d81ee  mov     [rcx+8], rcx
0x1400d81f2  mov     [rcx], rcx
0x1400d81f5  jmp     loc_1400D7F84
0x1400d81fa  mov     rcx, rax; this
0x1400d81fd  call    ?OnThreadTermination@ThreadRestrictNewHandlesRegion@@QEAAXXZ; ThreadRestrictNewHandlesRegion::OnThreadTermination(void)
0x1400d8202  jmp     loc_1400D8077
0x1400d8207  call    cs:__imp_W32GetSessionState
0x1400d820e  nop     dword ptr [rax+rax+00h]
0x1400d8213  mov     rdx, rdi
0x1400d8216  mov     rcx, [rax+58h]
0x1400d821a  call    HmgFreeDcAttr
0x1400d821f  jmp     loc_1400D80A9
0x1400d8224  test    rcx, rcx
0x1400d8227  jz      loc_1400D80AD
0x1400d822d  mov     r14, [rcx+10h]
0x1400d8231  mov     rbp, [rcx+18h]
0x1400d8235  call    PopThreadGuardedObject
0x1400d823a  test    rbp, rbp
0x1400d823d  jz      loc_1400D80AD
0x1400d8243  mov     rcx, r14
0x1400d8246  mov     rax, rbp
0x1400d8249  call    _guard_dispatch_icall
0x1400d824e  jmp     loc_1400D80AD
```
