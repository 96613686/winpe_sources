# DsqFreeObject(tagDSUpdatePropsLoc *,ulong,int)

- ea: `0x180133884`
- end: `0x180133a0a`
- name: `?DsqFreeObject@@YAXPEAUtagDSUpdatePropsLoc@@KH@Z`
- size: `390`
- prototype: `void __fastcall(struct tagDSUpdatePropsLoc *, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800b8820`
- `0x180133a10`
- `0x1801977d0`

## callees

- `0x180133884`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013394e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013397e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801339ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801339c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801338f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133916`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013394e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013397e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133994`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801339ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801339c4`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSUpdatePropsLoc *a1, unsigned int a2, int a3)
{
  unsigned int v6; // esi
  char *v7; // rbx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 i; // rdi
  void *v16; // rcx
  void *v17; // rcx
  __int64 j; // rdi
  void *v19; // rcx
  void *v20; // rcx
  __int64 k; // rdi
  void *v22; // rcx
  void *v23; // rcx

  if ( a1 && a2 )
  {
    v6 = 0;
    v7 = (char *)a1 + 16;
    do
    {
      v8 = (void *)*((_QWORD *)v7 - 2);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)*((_QWORD *)v7 - 1);
      if ( v9 )
        CoTaskMemFree(v9);
      if ( *(_QWORD *)v7 )
        CoTaskMemFree(*(LPVOID *)v7);
      v10 = (void *)*((_QWORD *)v7 + 1);
      if ( v10 )
        CoTaskMemFree(v10);
      v11 = (void *)*((_QWORD *)v7 + 2);
      if ( v11 )
        CoTaskMemFree(v11);
      v12 = (void *)*((_QWORD *)v7 + 3);
      if ( v12 )
        CoTaskMemFree(v12);
      v13 = (void *)*((_QWORD *)v7 + 5);
      if ( v13 )
        CoTaskMemFree(v13);
      v14 = (void *)*((_QWORD *)v7 + 4);
      if ( v14 )
        CoTaskMemFree(v14);
      for ( i = 0; (unsigned int)i < *((_DWORD *)v7 + 22); i = (unsigned int)(i + 1) )
      {
        v16 = *(void **)(*((_QWORD *)v7 + 12) + 8 * i);
        if ( v16 )
          CoTaskMemFree(v16);
      }
      v17 = (void *)*((_QWORD *)v7 + 12);
      if ( v17 )
        CoTaskMemFree(v17);
      for ( j = 0; (unsigned int)j < *((_DWORD *)v7 + 14); j = (unsigned int)(j + 1) )
      {
        v19 = *(void **)(*((_QWORD *)v7 + 8) + 8 * j);
        if ( v19 )
          CoTaskMemFree(v19);
      }
      v20 = (void *)*((_QWORD *)v7 + 8);
      if ( v20 )
        CoTaskMemFree(v20);
      for ( k = 0; (unsigned int)k < *((_DWORD *)v7 + 18); k = (unsigned int)(k + 1) )
      {
        v22 = *(void **)(*((_QWORD *)v7 + 10) + 8 * k);
        if ( v22 )
          CoTaskMemFree(v22);
      }
      v23 = (void *)*((_QWORD *)v7 + 10);
      if ( v23 )
        CoTaskMemFree(v23);
      if ( a3 )
        memset((char *)a1 + 120 * v6, 0, 0x78u);
      ++v6;
      v7 += 120;
    }
    while ( v6 < a2 );
  }
}

```

## disassembly

```asm
0x180133884  test    rcx, rcx
0x180133887  jz      locret_180133A09
0x18013388d  mov     [rsp+arg_0], rbx
0x180133892  mov     [rsp+arg_8], rbp
0x180133897  mov     [rsp+arg_10], rsi
0x18013389c  push    rdi
0x18013389d  push    r14
0x18013389f  push    r15
0x1801338a1  sub     rsp, 20h
0x1801338a5  mov     r15d, r8d
0x1801338a8  mov     ebp, edx
0x1801338aa  mov     r14, rcx
0x1801338ad  test    edx, edx
0x1801338af  jz      loc_1801339F1
0x1801338b5  xor     esi, esi
0x1801338b7  test    edx, edx
0x1801338b9  jz      loc_1801339F1
0x1801338bf  lea     rbx, [rcx+10h]
0x1801338c3  mov     rcx, [rbx-10h]; pv
0x1801338c7  test    rcx, rcx
0x1801338ca  jz      short loc_1801338D2
0x1801338cc  call    cs:__imp_CoTaskMemFree
0x1801338d2  mov     rcx, [rbx-8]; pv
0x1801338d6  test    rcx, rcx
0x1801338d9  jz      short loc_1801338E1
0x1801338db  call    cs:__imp_CoTaskMemFree
0x1801338e1  mov     rcx, [rbx]; pv
0x1801338e4  test    rcx, rcx
0x1801338e7  jz      short loc_1801338EF
0x1801338e9  call    cs:__imp_CoTaskMemFree
0x1801338ef  mov     rcx, [rbx+8]; pv
0x1801338f3  test    rcx, rcx
0x1801338f6  jz      short loc_1801338FE
0x1801338f8  call    cs:__imp_CoTaskMemFree
0x1801338fe  mov     rcx, [rbx+10h]; pv
0x180133902  test    rcx, rcx
0x180133905  jz      short loc_18013390D
0x180133907  call    cs:__imp_CoTaskMemFree
0x18013390d  mov     rcx, [rbx+18h]; pv
0x180133911  test    rcx, rcx
0x180133914  jz      short loc_18013391C
0x180133916  call    cs:__imp_CoTaskMemFree
0x18013391c  mov     rcx, [rbx+28h]; pv
0x180133920  test    rcx, rcx
0x180133923  jz      short loc_18013392B
0x180133925  call    cs:__imp_CoTaskMemFree
0x18013392b  mov     rcx, [rbx+20h]; pv
0x18013392f  test    rcx, rcx
0x180133932  jz      short loc_18013393A
0x180133934  call    cs:__imp_CoTaskMemFree
0x18013393a  xor     edi, edi
0x18013393c  cmp     [rbx+58h], edi
0x18013393f  jbe     short loc_18013395B
0x180133941  mov     rax, [rbx+60h]
0x180133945  mov     rcx, [rax+rdi*8]; pv
0x180133949  test    rcx, rcx
0x18013394c  jz      short loc_180133954
0x18013394e  call    cs:__imp_CoTaskMemFree
0x180133954  inc     edi
0x180133956  cmp     edi, [rbx+58h]
0x180133959  jb      short loc_180133941
0x18013395b  mov     rcx, [rbx+60h]; pv
0x18013395f  test    rcx, rcx
0x180133962  jz      short loc_18013396A
0x180133964  call    cs:__imp_CoTaskMemFree
0x18013396a  xor     edi, edi
0x18013396c  cmp     [rbx+38h], edi
0x18013396f  jbe     short loc_18013398B
0x180133971  mov     rax, [rbx+40h]
0x180133975  mov     rcx, [rax+rdi*8]; pv
0x180133979  test    rcx, rcx
0x18013397c  jz      short loc_180133984
0x18013397e  call    cs:__imp_CoTaskMemFree
0x180133984  inc     edi
0x180133986  cmp     edi, [rbx+38h]
0x180133989  jb      short loc_180133971
0x18013398b  mov     rcx, [rbx+40h]; pv
0x18013398f  test    rcx, rcx
0x180133992  jz      short loc_18013399A
0x180133994  call    cs:__imp_CoTaskMemFree
0x18013399a  xor     edi, edi
0x18013399c  cmp     [rbx+48h], edi
0x18013399f  jbe     short loc_1801339BB
0x1801339a1  mov     rax, [rbx+50h]
0x1801339a5  mov     rcx, [rax+rdi*8]; pv
0x1801339a9  test    rcx, rcx
0x1801339ac  jz      short loc_1801339B4
0x1801339ae  call    cs:__imp_CoTaskMemFree
0x1801339b4  inc     edi
0x1801339b6  cmp     edi, [rbx+48h]
0x1801339b9  jb      short loc_1801339A1
0x1801339bb  mov     rcx, [rbx+50h]; pv
0x1801339bf  test    rcx, rcx
0x1801339c2  jz      short loc_1801339CA
0x1801339c4  call    cs:__imp_CoTaskMemFree
0x1801339ca  test    r15d, r15d
0x1801339cd  jz      short loc_1801339E3
0x1801339cf  mov     eax, esi
0x1801339d1  xor     edx, edx; Val
0x1801339d3  imul    rcx, rax, 78h ; 'x'
0x1801339d7  lea     r8d, [rdx+78h]; Size
0x1801339db  add     rcx, r14; void *
0x1801339de  call    memset
0x1801339e3  inc     esi
0x1801339e5  add     rbx, 78h ; 'x'
0x1801339e9  cmp     esi, ebp
0x1801339eb  jb      loc_1801338C3
0x1801339f1  mov     rbx, [rsp+38h+arg_0]
0x1801339f6  mov     rbp, [rsp+38h+arg_8]
0x1801339fb  mov     rsi, [rsp+38h+arg_10]
0x180133a00  add     rsp, 20h
0x180133a04  pop     r15
0x180133a06  pop     r14
0x180133a08  pop     rdi
0x180133a09  retn
```
