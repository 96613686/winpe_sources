# DsqFreeObject(tagDSServiceProps *,ulong,int)

- ea: `0x18013419c`
- end: `0x1801342e3`
- name: `?DsqFreeObject@@YAXPEAUtagDSServiceProps@@KH@Z`
- size: `327`
- prototype: `void __fastcall(struct tagDSServiceProps *, unsigned int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800441c0`
- `0x1800528e4`
- `0x18005d104`
- `0x1801342ec`
- `0x18018c37c`

## callees

- `0x18013419c`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013420e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134249`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013425f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801341ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013420e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134235`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134249`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18013425f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134280`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180134296`

## pseudocode

```c
void __fastcall DsqFreeObject(struct tagDSServiceProps *a1, unsigned int a2, int a3)
{
  char *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // r15
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  unsigned int i; // edi
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 j; // rdi
  void *v16; // rcx
  void *v17; // rcx

  if ( a1 && a2 )
  {
    v5 = (char *)a1 + 8;
    v6 = a2;
    v7 = a2;
    do
    {
      v8 = (void *)*((_QWORD *)v5 + 6);
      if ( v8 )
        CoTaskMemFree(v8);
      v9 = (void *)*((_QWORD *)v5 - 1);
      if ( v9 )
        CoTaskMemFree(v9);
      if ( *(_QWORD *)v5 )
        CoTaskMemFree(*(LPVOID *)v5);
      v10 = (void *)*((_QWORD *)v5 + 1);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( *((_QWORD *)v5 + 13) )
      {
        for ( i = 0; i < *((_DWORD *)v5 + 25); ++i )
        {
          v12 = *(void **)(*((_QWORD *)v5 + 13) + 16LL * i);
          if ( v12 )
            CoTaskMemFree(v12);
          v13 = *(void **)(*((_QWORD *)v5 + 13) + 16LL * i + 8);
          if ( v13 )
            CoTaskMemFree(v13);
        }
        v14 = (void *)*((_QWORD *)v5 + 13);
        if ( v14 )
          CoTaskMemFree(v14);
      }
      if ( *((_QWORD *)v5 + 15) )
      {
        for ( j = 0; (unsigned int)j < *((_DWORD *)v5 + 28); j = (unsigned int)(j + 1) )
        {
          v16 = *(void **)(*((_QWORD *)v5 + 15) + 8 * j);
          if ( v16 )
            CoTaskMemFree(v16);
        }
        v17 = (void *)*((_QWORD *)v5 + 15);
        if ( v17 )
          CoTaskMemFree(v17);
      }
      v5 += 144;
      --v7;
    }
    while ( v7 );
    if ( a3 )
      memset(a1, 0, 144 * v6);
  }
}

```

## disassembly

```asm
0x18013419c  test    rcx, rcx
0x18013419f  jz      locret_1801342E2
0x1801341a5  mov     rax, rsp
0x1801341a8  mov     [rax+8], rbx
0x1801341ac  mov     [rax+10h], rbp
0x1801341b0  mov     [rax+18h], rsi
0x1801341b4  mov     [rax+20h], rdi
0x1801341b8  push    r12
0x1801341ba  push    r14
0x1801341bc  push    r15
0x1801341be  sub     rsp, 20h
0x1801341c2  mov     r12d, r8d
0x1801341c5  mov     rbp, rcx
0x1801341c8  test    edx, edx
0x1801341ca  jz      loc_1801342C4
0x1801341d0  lea     rbx, [rcx+8]
0x1801341d4  mov     esi, edx
0x1801341d6  mov     r15d, edx
0x1801341d9  mov     rcx, [rbx+30h]; pv
0x1801341dd  test    rcx, rcx
0x1801341e0  jz      short loc_1801341E8
0x1801341e2  call    cs:__imp_CoTaskMemFree
0x1801341e8  mov     rcx, [rbx-8]; pv
0x1801341ec  test    rcx, rcx
0x1801341ef  jz      short loc_1801341F7
0x1801341f1  call    cs:__imp_CoTaskMemFree
0x1801341f7  mov     rcx, [rbx]; pv
0x1801341fa  test    rcx, rcx
0x1801341fd  jz      short loc_180134205
0x1801341ff  call    cs:__imp_CoTaskMemFree
0x180134205  mov     rcx, [rbx+8]; pv
0x180134209  test    rcx, rcx
0x18013420c  jz      short loc_180134214
0x18013420e  call    cs:__imp_CoTaskMemFree
0x180134214  cmp     qword ptr [rbx+68h], 0
0x180134219  jz      short loc_180134265
0x18013421b  xor     edi, edi
0x18013421d  cmp     [rbx+64h], edi
0x180134220  jbe     short loc_180134256
0x180134222  mov     rax, [rbx+68h]
0x180134226  mov     r14d, edi
0x180134229  add     r14, r14
0x18013422c  mov     rcx, [rax+r14*8]; pv
0x180134230  test    rcx, rcx
0x180134233  jz      short loc_18013423B
0x180134235  call    cs:__imp_CoTaskMemFree
0x18013423b  mov     rax, [rbx+68h]
0x18013423f  mov     rcx, [rax+r14*8+8]; pv
0x180134244  test    rcx, rcx
0x180134247  jz      short loc_18013424F
0x180134249  call    cs:__imp_CoTaskMemFree
0x18013424f  inc     edi
0x180134251  cmp     edi, [rbx+64h]
0x180134254  jb      short loc_180134222
0x180134256  mov     rcx, [rbx+68h]; pv
0x18013425a  test    rcx, rcx
0x18013425d  jz      short loc_180134265
0x18013425f  call    cs:__imp_CoTaskMemFree
0x180134265  cmp     qword ptr [rbx+78h], 0
0x18013426a  jz      short loc_18013429C
0x18013426c  xor     edi, edi
0x18013426e  cmp     [rbx+70h], edi
0x180134271  jbe     short loc_18013428D
0x180134273  mov     rax, [rbx+78h]
0x180134277  mov     rcx, [rax+rdi*8]; pv
0x18013427b  test    rcx, rcx
0x18013427e  jz      short loc_180134286
0x180134280  call    cs:__imp_CoTaskMemFree
0x180134286  inc     edi
0x180134288  cmp     edi, [rbx+70h]
0x18013428b  jb      short loc_180134273
0x18013428d  mov     rcx, [rbx+78h]; pv
0x180134291  test    rcx, rcx
0x180134294  jz      short loc_18013429C
0x180134296  call    cs:__imp_CoTaskMemFree
0x18013429c  add     rbx, 90h
0x1801342a3  sub     r15, 1
0x1801342a7  jnz     loc_1801341D9
0x1801342ad  test    r12d, r12d
0x1801342b0  jz      short loc_1801342C4
0x1801342b2  lea     r8, [rsi+rsi*8]
0x1801342b6  xor     edx, edx; Val
0x1801342b8  shl     r8, 4; Size
0x1801342bc  mov     rcx, rbp; void *
0x1801342bf  call    memset
0x1801342c4  mov     rbx, [rsp+38h+arg_0]
0x1801342c9  mov     rbp, [rsp+38h+arg_8]
0x1801342ce  mov     rsi, [rsp+38h+arg_10]
0x1801342d3  mov     rdi, [rsp+38h+arg_18]
0x1801342d8  add     rsp, 20h
0x1801342dc  pop     r15
0x1801342de  pop     r14
0x1801342e0  pop     r12
0x1801342e2  retn
```
