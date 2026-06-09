# _CatAdminReleaseContext(CRYPT_CAT_ADMIN_ *)

- ea: `0x1800074e0`
- end: `0x18000757f`
- name: `?_CatAdminReleaseContext@@YAXPEAUCRYPT_CAT_ADMIN_@@@Z`
- size: `159`
- prototype: `void __fastcall(struct CRYPT_CAT_ADMIN_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800067b0`

## callees

- `0x1800074e0`
- `0x180007680`
- `0x1800077e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007529`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007559`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007562`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007559`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007562`

## pseudocode

```c
void __fastcall _CatAdminReleaseContext(struct CRYPT_CAT_ADMIN_ *a1)
{
  _QWORD *i; // rsi
  _QWORD *v3; // rcx
  HLOCAL *v4; // rbx
  _QWORD *v5; // rbx

  for ( i = (_QWORD *)*((_QWORD *)a1 + 4); i; i = (_QWORD *)*i )
  {
    v4 = (HLOCAL *)i[1];
    SortedCatalogClose(v4[2]);
    LocalFree(v4[1]);
    LocalFree(v4);
  }
  v3 = (_QWORD *)*((_QWORD *)a1 + 4);
  if ( v3 )
  {
    do
    {
      v5 = (_QWORD *)*v3;
      PkiFree(v3);
      v3 = v5;
    }
    while ( v5 );
  }
  *((_QWORD *)a1 + 5) = 0;
  *((_QWORD *)a1 + 4) = 0;
  *((_DWORD *)a1 + 12) = 0;
  LocalFree(*((HLOCAL *)a1 + 3));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 64));
  LocalFree(a1);
}

```

## disassembly

```asm
0x1800074e0  mov     [rsp+arg_0], rbx
0x1800074e5  mov     [rsp+arg_8], rsi
0x1800074ea  push    rdi
0x1800074eb  sub     rsp, 20h
0x1800074ef  mov     rsi, [rcx+20h]
0x1800074f3  mov     rdi, rcx
0x1800074f6  test    rsi, rsi
0x1800074f9  jnz     short loc_180007548
0x1800074fb  mov     rcx, [rdi+20h]; hMem
0x1800074ff  test    rcx, rcx
0x180007502  jnz     short loc_18000756D
0x180007504  mov     qword ptr [rdi+28h], 0
0x18000750c  mov     qword ptr [rdi+20h], 0
0x180007514  mov     dword ptr [rdi+30h], 0
0x18000751b  mov     rcx, [rdi+18h]; hMem
0x18000751f  call    cs:__imp_LocalFree
0x180007525  lea     rcx, [rdi+40h]; lpCriticalSection
0x180007529  call    cs:__imp_DeleteCriticalSection
0x18000752f  mov     rcx, rdi
0x180007532  mov     rbx, [rsp+28h+arg_0]
0x180007537  mov     rsi, [rsp+28h+arg_8]
0x18000753c  add     rsp, 20h
0x180007540  pop     rdi
0x180007541  jmp     cs:__imp_LocalFree
0x180007548  mov     rbx, [rsi+8]
0x18000754c  mov     rcx, [rbx+10h]; hMem
0x180007550  call    SortedCatalogClose
0x180007555  mov     rcx, [rbx+8]; hMem
0x180007559  call    cs:__imp_LocalFree
0x18000755f  mov     rcx, rbx; hMem
0x180007562  call    cs:__imp_LocalFree
0x180007568  mov     rsi, [rsi]
0x18000756b  jmp     short loc_1800074F6
0x18000756d  mov     rbx, [rcx]
0x180007570  call    PkiFree
0x180007575  mov     rcx, rbx
0x180007578  test    rbx, rbx
0x18000757b  jz      short loc_180007504
0x18000757d  jmp     short loc_18000756D
```
