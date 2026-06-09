# DsqFreeObject(tagDSFile *,ulong,int)

- ea: `0x180133470`
- end: `0x1801335ee`
- name: `?DsqFreeObject@@YAXPEAUtagDSFile@@KH@Z`
- size: `382`
- prototype: `void __fastcall(struct tagDSFile *, unsigned int, int)`
- caller_count: `9`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180042b70`
- `0x180052974`
- `0x18008be04`
- `0x18009b488`
- `0x1800b8860`
- `0x180133a10`
- `0x1801980d4`
- `0x18019b4ac`
- `0x18019cf0c`

## callees

- `0x1801333e8`
- `0x180133470`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013350d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013351f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013358a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801335ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801334fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013350d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013351f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133555`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013358a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801335ad`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSFile *a1, unsigned int a2, int a3)
{
  char *v4; // rbx
  __int64 v5; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx

  if ( a1 && a2 )
  {
    v4 = (char *)a1 + 8;
    v5 = a2;
    do
    {
      DsqFreeObject((struct tagDSFileState *)(v4 + 8));
      if ( *(_QWORD *)v4 )
        CoTaskMemFree(*(LPVOID *)v4);
      v6 = (void *)*((_QWORD *)v4 + 8);
      if ( v6 )
        CoTaskMemFree(v6);
      v7 = (void *)*((_QWORD *)v4 + 9);
      if ( v7 )
        CoTaskMemFree(v7);
      v8 = (void *)*((_QWORD *)v4 + 15);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)*((_QWORD *)v4 + 16);
      if ( v9 )
        CoTaskMemFree(v9);
      v10 = (void *)*((_QWORD *)v4 + 11);
      if ( v10 )
        CoTaskMemFree(v10);
      v11 = (void *)*((_QWORD *)v4 + 12);
      if ( v11 )
        CoTaskMemFree(v11);
      v12 = (void *)*((_QWORD *)v4 + 27);
      if ( v12 )
        CoTaskMemFree(v12);
      v13 = (void *)*((_QWORD *)v4 + 22);
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = (void *)*((_QWORD *)v4 + 23);
      if ( v14 )
        CoTaskMemFree(v14);
      v15 = (void *)*((_QWORD *)v4 + 25);
      if ( v15 )
        CoTaskMemFree(v15);
      v16 = (void *)*((_QWORD *)v4 + 26);
      if ( v16 )
        CoTaskMemFree(v16);
      memset(*((void **)v4 + 18), 0, *((unsigned int *)v4 + 34));
      v17 = (void *)*((_QWORD *)v4 + 18);
      if ( v17 )
        CoTaskMemFree(v17);
      memset(*((void **)v4 + 20), 0, *((unsigned int *)v4 + 39));
      v18 = (void *)*((_QWORD *)v4 + 20);
      if ( v18 )
        CoTaskMemFree(v18);
      if ( a3 )
        memset(v4 - 8, 0, 0xF8u);
      v4 += 248;
      --v5;
    }
    while ( v5 );
  }
}

```

## disassembly

```asm
0x180133470  test    rcx, rcx
0x180133473  jz      locret_1801335ED
0x180133479  mov     [rsp+arg_0], rbx
0x18013347e  mov     [rsp+arg_8], rbp
0x180133483  mov     [rsp+arg_10], rsi
0x180133488  push    rdi
0x180133489  sub     rsp, 20h
0x18013348d  mov     ebp, r8d
0x180133490  cmp     edx, 1
0x180133493  jb      loc_1801335D9
0x180133499  lea     rbx, [rcx+8]
0x18013349d  mov     esi, edx
0x18013349f  lea     rcx, [rbx+8]; struct tagDSFileState *
0x1801334a3  call    ?DsqFreeObject@@YAXAEAUtagDSFileState@@@Z; DsqFreeObject(tagDSFileState &)
0x1801334a8  mov     rcx, [rbx]; pv
0x1801334ab  test    rcx, rcx
0x1801334ae  jz      short loc_1801334B6
0x1801334b0  call    cs:__imp_CoTaskMemFree
0x1801334b6  mov     rcx, [rbx+40h]; pv
0x1801334ba  test    rcx, rcx
0x1801334bd  jz      short loc_1801334C5
0x1801334bf  call    cs:__imp_CoTaskMemFree
0x1801334c5  mov     rcx, [rbx+48h]; pv
0x1801334c9  test    rcx, rcx
0x1801334cc  jz      short loc_1801334D4
0x1801334ce  call    cs:__imp_CoTaskMemFree
0x1801334d4  mov     rcx, [rbx+78h]; pv
0x1801334d8  test    rcx, rcx
0x1801334db  jz      short loc_1801334E3
0x1801334dd  call    cs:__imp_CoTaskMemFree
0x1801334e3  mov     rcx, [rbx+80h]; pv
0x1801334ea  test    rcx, rcx
0x1801334ed  jz      short loc_1801334F5
0x1801334ef  call    cs:__imp_CoTaskMemFree
0x1801334f5  mov     rcx, [rbx+58h]; pv
0x1801334f9  test    rcx, rcx
0x1801334fc  jz      short loc_180133504
0x1801334fe  call    cs:__imp_CoTaskMemFree
0x180133504  mov     rcx, [rbx+60h]; pv
0x180133508  test    rcx, rcx
0x18013350b  jz      short loc_180133513
0x18013350d  call    cs:__imp_CoTaskMemFree
0x180133513  mov     rcx, [rbx+0D8h]; pv
0x18013351a  test    rcx, rcx
0x18013351d  jz      short loc_180133525
0x18013351f  call    cs:__imp_CoTaskMemFree
0x180133525  mov     rcx, [rbx+0B0h]; pv
0x18013352c  test    rcx, rcx
0x18013352f  jz      short loc_180133537
0x180133531  call    cs:__imp_CoTaskMemFree
0x180133537  mov     rcx, [rbx+0B8h]; pv
0x18013353e  test    rcx, rcx
0x180133541  jz      short loc_180133549
0x180133543  call    cs:__imp_CoTaskMemFree
0x180133549  mov     rcx, [rbx+0C8h]; pv
0x180133550  test    rcx, rcx
0x180133553  jz      short loc_18013355B
0x180133555  call    cs:__imp_CoTaskMemFree
0x18013355b  mov     rcx, [rbx+0D0h]; pv
0x180133562  test    rcx, rcx
0x180133565  jz      short loc_18013356D
0x180133567  call    cs:__imp_CoTaskMemFree
0x18013356d  mov     ecx, [rbx+88h]
0x180133573  xor     eax, eax
0x180133575  mov     rdi, [rbx+90h]
0x18013357c  rep stosb
0x18013357e  mov     rcx, [rbx+90h]; pv
0x180133585  test    rcx, rcx
0x180133588  jz      short loc_180133590
0x18013358a  call    cs:__imp_CoTaskMemFree
0x180133590  mov     ecx, [rbx+9Ch]
0x180133596  xor     eax, eax
0x180133598  mov     rdi, [rbx+0A0h]
0x18013359f  rep stosb
0x1801335a1  mov     rcx, [rbx+0A0h]; pv
0x1801335a8  test    rcx, rcx
0x1801335ab  jz      short loc_1801335B3
0x1801335ad  call    cs:__imp_CoTaskMemFree
0x1801335b3  test    ebp, ebp
0x1801335b5  jz      short loc_1801335C8
0x1801335b7  lea     rcx, [rbx-8]; void *
0x1801335bb  xor     edx, edx; Val
0x1801335bd  mov     r8d, 0F8h; Size
0x1801335c3  call    memset
0x1801335c8  add     rbx, 0F8h
0x1801335cf  sub     rsi, 1
0x1801335d3  jnz     loc_18013349F
0x1801335d9  mov     rbx, [rsp+28h+arg_0]
0x1801335de  mov     rbp, [rsp+28h+arg_8]
0x1801335e3  mov     rsi, [rsp+28h+arg_10]
0x1801335e8  add     rsp, 20h
0x1801335ec  pop     rdi
0x1801335ed  retn
```
