# tip2::details::shared_data<0,0,0>::log(char const *)

- ea: `0x18002f35c`
- end: `0x18002f4b5`
- name: `?log@?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAAXPEBD@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f4bc`

## callees

- `0x18000e480`
- `0x18000f44c`
- `0x18002f35c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f42e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f46f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f44f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f44f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f3e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f441`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f3e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f441`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f3f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f3f0`

## string_xrefs

- `0x18002f4a3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::log(__int64 a1, _BYTE *a2, __int64 a3, const char *a4)
{
  rsize_t v6; // rbx
  _BYTE *v7; // rax
  _BYTE *v8; // rsi
  unsigned __int64 v9; // rax
  char v10; // bp
  __int64 v11; // r14
  HANDLE ProcessHeap; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // r15
  unsigned __int64 i; // rbx
  __int64 v16; // rcx
  void *v17; // rcx
  void *v18; // rbx
  HANDLE v19; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = CoTaskMemAlloc(v6 + 1);
  v8 = v7;
  if ( v7 )
  {
    memcpy_s(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  v9 = *(_QWORD *)(a1 + 104);
  v10 = 1;
  if ( *(_QWORD *)(a1 + 112) < v9 )
    goto LABEL_23;
  if ( v9 )
  {
    v11 = 2 * v9;
    if ( 2 * v9 <= v9 )
      goto LABEL_19;
  }
  else
  {
    v11 = 10;
  }
  ProcessHeap = GetProcessHeap();
  v13 = HeapAlloc(ProcessHeap, 0, 8 * v11);
  v14 = v13;
  if ( !v13 )
    goto LABEL_20;
  if ( *(_QWORD *)(a1 + 96) )
  {
    for ( i = 0; i < *(_QWORD *)(a1 + 112); ++i )
    {
      v16 = *(_QWORD *)(a1 + 96);
      v14[i] = *(_QWORD *)(v16 + 8 * i);
      *(_QWORD *)(v16 + 8 * i) = 0;
      v17 = *(void **)(*(_QWORD *)(a1 + 96) + 8 * i);
      if ( v17 )
        CoTaskMemFree(v17);
    }
    v18 = *(void **)(a1 + 96);
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
  }
  *(_QWORD *)(a1 + 96) = v14;
  *(_QWORD *)(a1 + 104) = v11;
LABEL_19:
  LOBYTE(v13) = 1;
LABEL_20:
  if ( (_BYTE)v13 )
  {
LABEL_23:
    *(_QWORD *)(*(_QWORD *)(a1 + 96) + 8LL * (*(_QWORD *)(a1 + 112))++) = v8;
LABEL_24:
    if ( v10 )
      return;
    goto LABEL_25;
  }
  v10 = 0;
  if ( !v8 )
    goto LABEL_24;
  CoTaskMemFree(v8);
LABEL_25:
  *(_DWORD *)(a1 + 64) |= 0x100000u;
}

```

## disassembly

```asm
0x18002f35c  push    rbx
0x18002f35e  push    rbp
0x18002f35f  push    rsi
0x18002f360  push    rdi
0x18002f361  push    r14
0x18002f363  push    r15
0x18002f365  sub     rsp, 28h
0x18002f369  mov     rbp, rdx
0x18002f36c  mov     rdi, rcx
0x18002f36f  test    rdx, rdx
0x18002f372  jz      loc_18002F49E
0x18002f378  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002f37c  inc     rbx
0x18002f37f  cmp     byte ptr [rbx+rdx], 0
0x18002f383  jnz     short loc_18002F37C
0x18002f385  lea     rcx, [rbx+1]; cb
0x18002f389  call    cs:__imp_CoTaskMemAlloc
0x18002f38f  mov     rsi, rax
0x18002f392  test    rax, rax
0x18002f395  jz      short loc_18002F3AD
0x18002f397  mov     r9, rbx; SourceSize
0x18002f39a  lea     rdx, [rbx+1]; DestinationSize
0x18002f39e  mov     r8, rbp; Source
0x18002f3a1  mov     rcx, rax; Destination
0x18002f3a4  call    memcpy_s
0x18002f3a9  mov     byte ptr [rbx+rsi], 0
0x18002f3ad  mov     rax, [rdi+68h]
0x18002f3b1  mov     ebp, 1
0x18002f3b6  cmp     [rdi+70h], rax
0x18002f3ba  jb      loc_18002F477
0x18002f3c0  test    rax, rax
0x18002f3c3  jz      short loc_18002F3D4
0x18002f3c5  lea     r14, [rax+rax]
0x18002f3c9  cmp     r14, rax
0x18002f3cc  jbe     loc_18002F45D
0x18002f3d2  jmp     short loc_18002F3DA
0x18002f3d4  mov     r14d, 0Ah
0x18002f3da  lea     rbx, ds:0[r14*8]
0x18002f3e2  call    cs:__imp_GetProcessHeap
0x18002f3e8  mov     r8, rbx; dwBytes
0x18002f3eb  xor     edx, edx; dwFlags
0x18002f3ed  mov     rcx, rax; hHeap
0x18002f3f0  call    cs:__imp_HeapAlloc
0x18002f3f6  mov     r15, rax
0x18002f3f9  test    rax, rax
0x18002f3fc  jz      short loc_18002F460
0x18002f3fe  cmp     qword ptr [rdi+60h], 0
0x18002f403  jz      short loc_18002F455
0x18002f405  xor     ebx, ebx
0x18002f407  cmp     [rdi+70h], rbx
0x18002f40b  jbe     short loc_18002F43D
0x18002f40d  mov     rcx, [rdi+60h]
0x18002f411  mov     rax, [rcx+rbx*8]
0x18002f415  mov     [r15+rbx*8], rax
0x18002f419  mov     qword ptr [rcx+rbx*8], 0
0x18002f421  mov     rax, [rdi+60h]
0x18002f425  mov     rcx, [rax+rbx*8]; pv
0x18002f429  test    rcx, rcx
0x18002f42c  jz      short loc_18002F434
0x18002f42e  call    cs:__imp_CoTaskMemFree
0x18002f434  add     rbx, rbp
0x18002f437  cmp     rbx, [rdi+70h]
0x18002f43b  jb      short loc_18002F40D
0x18002f43d  mov     rbx, [rdi+60h]
0x18002f441  call    cs:__imp_GetProcessHeap
0x18002f447  mov     r8, rbx; lpMem
0x18002f44a  xor     edx, edx; dwFlags
0x18002f44c  mov     rcx, rax; hHeap
0x18002f44f  call    cs:__imp_HeapFree
0x18002f455  mov     [rdi+60h], r15
0x18002f459  mov     [rdi+68h], r14
0x18002f45d  mov     al, bpl
0x18002f460  test    al, al
0x18002f462  jnz     short loc_18002F477
0x18002f464  xor     bpl, bpl
0x18002f467  test    rsi, rsi
0x18002f46a  jz      short loc_18002F487
0x18002f46c  mov     rcx, rsi; pv
0x18002f46f  call    cs:__imp_CoTaskMemFree
0x18002f475  jmp     short loc_18002F48C
0x18002f477  mov     rcx, [rdi+70h]
0x18002f47b  mov     rax, [rdi+60h]
0x18002f47f  mov     [rax+rcx*8], rsi
0x18002f483  add     [rdi+70h], rbp
0x18002f487  test    bpl, bpl
0x18002f48a  jnz     short loc_18002F491
0x18002f48c  bts     dword ptr [rdi+40h], 14h
0x18002f491  add     rsp, 28h
0x18002f495  pop     r15
0x18002f497  pop     r14
0x18002f499  pop     rdi
0x18002f49a  pop     rsi
0x18002f49b  pop     rbp
0x18002f49c  pop     rbx
0x18002f49d  retn
0x18002f49e  mov     rcx, [rsp+58h]; this
0x18002f4a3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f4aa  mov     edx, 0FBDh; void *
0x18002f4af  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
