# StateRepoNewMenuCache::CopyNewMenuEntry(NewMenuEntry *,NewMenuEntry * *)

- ea: `0x18007c1f0`
- end: `0x18007c7da`
- name: `?CopyNewMenuEntry@StateRepoNewMenuCache@@AEAAJPEAUNewMenuEntry@@PEAPEAU2@@Z`
- size: `1514`
- prototype: `__int64 __fastcall(StateRepoNewMenuCache *__hidden this, struct NewMenuEntry *, struct NewMenuEntry **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ca24`

## callees

- `0x180026890`
- `0x180038608`
- `0x180063e10`
- `0x18007b9b0`
- `0x18007c180`
- `0x18007c1f0`
- `0x18007c9a0`
- `0x1801bce4c`
- `0x18025cc2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c2db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c37a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c4ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c2db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c37a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c4ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c3c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c4f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c66f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c32e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c3c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c4f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c5a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c66f`

## string_xrefs

- `0x18007c22a`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007c55c`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007c748`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18007c76e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18007c78c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18007c7aa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18007c7c8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall StateRepoNewMenuCache::CopyNewMenuEntry(
        StateRepoNewMenuCache *this,
        char **a2,
        struct NewMenuEntry **a3)
{
  const char *v4; // r9
  _QWORD *v5; // rdi
  char *v7; // rax
  __int64 v8; // rbx
  char *v9; // r12
  __int64 v10; // rcx
  rsize_t v11; // r15
  char *v12; // rax
  char *v13; // r14
  const char *v14; // r9
  char *v15; // r14
  char *v16; // rax
  __int64 v17; // rcx
  char *v18; // r12
  rsize_t v19; // r15
  char *v20; // rax
  char *v21; // r14
  const char *v22; // r9
  char *v23; // rax
  __int64 v24; // rcx
  char *v25; // r12
  rsize_t v26; // r15
  char *v27; // rax
  char *v28; // r14
  const char *v29; // r9
  char *v30; // r14
  char *v31; // rax
  __int64 v32; // rcx
  char *v33; // r12
  rsize_t v34; // r15
  char *v35; // rax
  char *v36; // r14
  const char *v37; // r9
  char *v38; // rax
  char *v39; // r15
  rsize_t v40; // rsi
  char *v41; // rax
  char *v42; // rbx
  __int64 v43; // rdx
  unsigned int v44; // edx
  __int64 v45; // rcx
  char *v46; // rax
  rsize_t v47; // r12
  char *v48; // rax
  char *v49; // r15
  char *v50; // rax
  rsize_t v51; // r15
  char *v52; // rax
  char *v53; // rbx
  LPVOID pv; // [rsp+20h] [rbp-10h] BYREF
  struct NewMenuEntry **v55; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]

  v55 = a3;
  *a3 = 0;
  wil::make_unique_nothrow<NewMenuEntry,>(&pv);
  v5 = pv;
  if ( !pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)0x8007000ELL,
      0);
    return 2147942414LL;
  }
  v7 = *a2;
  if ( !*a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v8 = 0x7FFFFFFF;
  v9 = *a2;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v10;
  }
  while ( v10 );
  v11 = 2 * ((v7 - v9) >> 1);
  v12 = (char *)CoTaskMemAlloc(v11 + 2);
  v13 = v12;
  if ( v12 )
  {
    memcpy_s_0(v12, v11 + 2, v9, v11);
    *(_WORD *)&v13[v11] = 0;
  }
  pv = v13;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v5,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !*v5 )
  {
    v43 = 156;
    goto LABEL_53;
  }
  v15 = a2[1];
  if ( v15 )
  {
    v45 = 0x7FFFFFFF;
    v46 = a2[1];
    do
    {
      if ( !*(_WORD *)v46 )
        break;
      v46 += 2;
      --v45;
    }
    while ( v45 );
    v47 = 2 * ((v46 - v15) >> 1);
    v48 = (char *)CoTaskMemAlloc(v47 + 2);
    v49 = v48;
    if ( v48 )
    {
      memcpy_s_0(v48, v47 + 2, v15, v47);
      *(_WORD *)&v49[v47] = 0;
    }
    pv = v49;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      v5 + 1,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    if ( !v5[1] )
    {
      v43 = 162;
      goto LABEL_53;
    }
  }
  v16 = a2[8];
  if ( !v16 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v14);
  v17 = 0x7FFFFFFF;
  v18 = a2[8];
  do
  {
    if ( !*(_WORD *)v16 )
      break;
    v16 += 2;
    --v17;
  }
  while ( v17 );
  v19 = 2 * ((v16 - v18) >> 1);
  v20 = (char *)CoTaskMemAlloc(v19 + 2);
  v21 = v20;
  if ( v20 )
  {
    memcpy_s_0(v20, v19 + 2, v18, v19);
    *(_WORD *)&v21[v19] = 0;
  }
  pv = v21;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v5 + 8,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5[8] )
  {
    v43 = 166;
    goto LABEL_53;
  }
  v23 = a2[9];
  if ( !v23 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  v24 = 0x7FFFFFFF;
  v25 = a2[9];
  do
  {
    if ( !*(_WORD *)v23 )
      break;
    v23 += 2;
    --v24;
  }
  while ( v24 );
  v26 = 2 * ((v23 - v25) >> 1);
  v27 = (char *)CoTaskMemAlloc(v26 + 2);
  v28 = v27;
  if ( v27 )
  {
    memcpy_s_0(v27, v26 + 2, v25, v26);
    *(_WORD *)&v28[v26] = 0;
  }
  pv = v28;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v5 + 9,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5[9] )
  {
    v43 = 169;
    goto LABEL_53;
  }
  v30 = a2[4];
  if ( v30 )
  {
    v50 = a2[4];
    do
    {
      if ( !*(_WORD *)v50 )
        break;
      v50 += 2;
      --v8;
    }
    while ( v8 );
    v51 = 2 * ((v50 - v30) >> 1);
    v52 = (char *)CoTaskMemAlloc(v51 + 2);
    v53 = v52;
    if ( v52 )
    {
      memcpy_s_0(v52, v51 + 2, v30, v51);
      *(_WORD *)&v53[v51] = 0;
    }
    pv = v53;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      v5 + 4,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v5[4] )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        a2[5],
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v5 + 5,
        &pv);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pv);
      if ( v5[5] )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          a2[6],
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          v5 + 6,
          &pv);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pv);
        if ( v5[6] )
        {
          *((_DWORD *)v5 + 14) = *((_DWORD *)a2 + 14);
          *((_DWORD *)v5 + 15) = *((_DWORD *)a2 + 15);
          goto LABEL_67;
        }
        v43 = 182;
      }
      else
      {
        v43 = 179;
      }
    }
    else
    {
      v43 = 176;
    }
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
      (const char *)0x8007000ELL,
      (int)pv);
    if ( v5 )
      NewMenuEntry::`scalar deleting destructor'((NewMenuEntry *)v5, v44);
    return 2147942414LL;
  }
  v31 = a2[2];
  if ( !v31 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v29);
  v32 = 0x7FFFFFFF;
  v33 = a2[2];
  do
  {
    if ( !*(_WORD *)v31 )
      break;
    v31 += 2;
    --v32;
  }
  while ( v32 );
  v34 = 2 * ((v31 - v33) >> 1);
  v35 = (char *)CoTaskMemAlloc(v34 + 2);
  v36 = v35;
  if ( v35 )
  {
    memcpy_s_0(v35, v34 + 2, v33, v34);
    *(_WORD *)&v36[v34] = 0;
  }
  pv = v36;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v5 + 2,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5[2] )
  {
    v43 = 190;
    goto LABEL_53;
  }
  v38 = a2[3];
  if ( !v38 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v37);
  v39 = a2[3];
  do
  {
    if ( !*(_WORD *)v38 )
      break;
    v38 += 2;
    --v8;
  }
  while ( v8 );
  v40 = 2 * ((v38 - v39) >> 1);
  v41 = (char *)CoTaskMemAlloc(v40 + 2);
  v42 = v41;
  if ( v41 )
  {
    memcpy_s_0(v41, v40 + 2, v39, v40);
    *(_WORD *)&v42[v40] = 0;
  }
  pv = v42;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v5 + 3,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !v5[3] )
  {
    v43 = 193;
    goto LABEL_53;
  }
LABEL_67:
  *v55 = (struct NewMenuEntry *)v5;
  return 0;
}

```

## disassembly

```asm
0x18007c1f0  mov     [rsp-38h+arg_0], rbx
0x18007c1f5  push    rbp
0x18007c1f6  push    rsi
0x18007c1f7  push    rdi
0x18007c1f8  push    r12
0x18007c1fa  push    r13
0x18007c1fc  push    r14
0x18007c1fe  push    r15
0x18007c200  mov     rbp, rsp
0x18007c203  sub     rsp, 30h
0x18007c207  xor     r14d, r14d
0x18007c20a  mov     [rbp+var_8], r8
0x18007c20e  lea     rcx, [rbp+pv]
0x18007c212  mov     [r8], r14
0x18007c215  mov     rsi, rdx
0x18007c218  call    ??$make_unique_nothrow@UNewMenuEntry@@$$V@wil@@YA?AV?$unique_ptr@UNewMenuEntry@@U?$default_delete@UNewMenuEntry@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<NewMenuEntry,>(void)
0x18007c21d  mov     rdi, [rbp+pv]
0x18007c221  test    rdi, rdi
0x18007c224  jnz     short loc_18007C25C
0x18007c226  mov     rcx, [rbp+38h]; this
0x18007c22a  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007c231  mov     r9d, 8007000Eh; char *
0x18007c237  mov     edx, 99h; void *
0x18007c23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c241  mov     eax, 8007000Eh
0x18007c246  mov     rbx, [rsp+30h+arg_0]
0x18007c24b  add     rsp, 30h
0x18007c24f  pop     r15
0x18007c251  pop     r14
0x18007c253  pop     r13
0x18007c255  pop     r12
0x18007c257  pop     rdi
0x18007c258  pop     rsi
0x18007c259  pop     rbp
0x18007c25a  retn
0x18007c25c  mov     rax, [rsi]
0x18007c25f  test    rax, rax
0x18007c262  jz      loc_18007C744
0x18007c268  mov     ebx, 7FFFFFFFh
0x18007c26d  mov     r12, rax
0x18007c270  mov     ecx, ebx
0x18007c272  cmp     [rax], r14w
0x18007c276  jz      short loc_18007C282
0x18007c278  add     rax, 2
0x18007c27c  sub     rcx, 1
0x18007c280  jnz     short loc_18007C272
0x18007c282  sub     rax, r12
0x18007c285  sar     rax, 1
0x18007c288  lea     r15, [rax+rax]
0x18007c28c  lea     rcx, [r15+2]; cb
0x18007c290  call    cs:__imp_CoTaskMemAlloc
0x18007c297  nop     dword ptr [rax+rax+00h]
0x18007c29c  mov     r14, rax
0x18007c29f  test    rax, rax
0x18007c2a2  jz      loc_18007C75A
0x18007c2a8  mov     r9, r15; SourceSize
0x18007c2ab  lea     rdx, [r15+2]; DestinationSize
0x18007c2af  mov     r8, r12; Source
0x18007c2b2  mov     rcx, rax; Destination
0x18007c2b5  call    memcpy_s_0
0x18007c2ba  xor     r13d, r13d
0x18007c2bd  mov     [r15+r14], r13w
0x18007c2c2  lea     rdx, [rbp+pv]
0x18007c2c6  mov     [rbp+pv], r14
0x18007c2ca  mov     rcx, rdi
0x18007c2cd  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c2d2  mov     rcx, [rbp+pv]; pv
0x18007c2d6  test    rcx, rcx
0x18007c2d9  jz      short loc_18007C2E7
0x18007c2db  call    cs:__imp_CoTaskMemFree
0x18007c2e2  nop     dword ptr [rax+rax+00h]
0x18007c2e7  cmp     [rdi], r13
0x18007c2ea  jz      loc_18007C553
0x18007c2f0  mov     r14, [rsi+8]
0x18007c2f4  test    r14, r14
0x18007c2f7  jnz     loc_18007C584
0x18007c2fd  mov     rax, [rsi+40h]
0x18007c301  test    rax, rax
0x18007c304  jz      loc_18007C76A
0x18007c30a  mov     rcx, rbx
0x18007c30d  mov     r12, rax
0x18007c310  cmp     [rax], r13w
0x18007c314  jz      short loc_18007C320
0x18007c316  add     rax, 2
0x18007c31a  sub     rcx, 1
0x18007c31e  jnz     short loc_18007C310
0x18007c320  sub     rax, r12
0x18007c323  sar     rax, 1
0x18007c326  lea     r15, [rax+rax]
0x18007c32a  lea     rcx, [r15+2]; cb
0x18007c32e  call    cs:__imp_CoTaskMemAlloc
0x18007c335  nop     dword ptr [rax+rax+00h]
0x18007c33a  mov     r14, rax
0x18007c33d  test    rax, rax
0x18007c340  jz      loc_18007C780
0x18007c346  mov     r9, r15; SourceSize
0x18007c349  lea     rdx, [r15+2]; DestinationSize
0x18007c34d  mov     r8, r12; Source
0x18007c350  mov     rcx, rax; Destination
0x18007c353  call    memcpy_s_0
0x18007c358  xor     r13d, r13d
0x18007c35b  mov     [r15+r14], r13w
0x18007c360  lea     rdx, [rbp+pv]
0x18007c364  mov     [rbp+pv], r14
0x18007c368  lea     rcx, [rdi+40h]
0x18007c36c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c371  mov     rcx, [rbp+pv]; pv
0x18007c375  test    rcx, rcx
0x18007c378  jz      short loc_18007C386
0x18007c37a  call    cs:__imp_CoTaskMemFree
0x18007c381  nop     dword ptr [rax+rax+00h]
0x18007c386  cmp     [rdi+40h], r13
0x18007c38a  jz      loc_18007C616
0x18007c390  mov     rax, [rsi+48h]
0x18007c394  test    rax, rax
0x18007c397  jz      loc_18007C788
0x18007c39d  mov     rcx, rbx
0x18007c3a0  mov     r12, rax
0x18007c3a3  cmp     [rax], r13w
0x18007c3a7  jz      short loc_18007C3B3
0x18007c3a9  add     rax, 2
0x18007c3ad  sub     rcx, 1
0x18007c3b1  jnz     short loc_18007C3A3
0x18007c3b3  sub     rax, r12
0x18007c3b6  sar     rax, 1
0x18007c3b9  lea     r15, [rax+rax]
0x18007c3bd  lea     rcx, [r15+2]; cb
0x18007c3c1  call    cs:__imp_CoTaskMemAlloc
0x18007c3c8  nop     dword ptr [rax+rax+00h]
0x18007c3cd  mov     r14, rax
0x18007c3d0  test    rax, rax
0x18007c3d3  jz      loc_18007C79E
0x18007c3d9  mov     r9, r15; SourceSize
0x18007c3dc  lea     rdx, [r15+2]; DestinationSize
0x18007c3e0  mov     r8, r12; Source
0x18007c3e3  mov     rcx, rax; Destination
0x18007c3e6  call    memcpy_s_0
0x18007c3eb  xor     r13d, r13d
0x18007c3ee  mov     [r15+r14], r13w
0x18007c3f3  lea     rdx, [rbp+pv]
0x18007c3f7  mov     [rbp+pv], r14
0x18007c3fb  lea     rcx, [rdi+48h]
0x18007c3ff  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c404  mov     rcx, [rbp+pv]; pv
0x18007c408  test    rcx, rcx
0x18007c40b  jz      short loc_18007C419
0x18007c40d  call    cs:__imp_CoTaskMemFree
0x18007c414  nop     dword ptr [rax+rax+00h]
0x18007c419  cmp     [rdi+48h], r13
0x18007c41d  jz      loc_18007C620
0x18007c423  mov     r14, [rsi+20h]
0x18007c427  test    r14, r14
0x18007c42a  jnz     loc_18007C64E
0x18007c430  mov     rax, [rsi+10h]
0x18007c434  test    rax, rax
0x18007c437  jz      loc_18007C7A6
0x18007c43d  mov     rcx, rbx
0x18007c440  mov     r12, rax
0x18007c443  cmp     [rax], r13w
0x18007c447  jz      short loc_18007C453
0x18007c449  add     rax, 2
0x18007c44d  sub     rcx, 1
0x18007c451  jnz     short loc_18007C443
0x18007c453  sub     rax, r12
0x18007c456  sar     rax, 1
0x18007c459  lea     r15, [rax+rax]
0x18007c45d  lea     rcx, [r15+2]; cb
0x18007c461  call    cs:__imp_CoTaskMemAlloc
0x18007c468  nop     dword ptr [rax+rax+00h]
0x18007c46d  mov     r14, rax
0x18007c470  test    rax, rax
0x18007c473  jz      loc_18007C7BC
0x18007c479  mov     r9, r15; SourceSize
0x18007c47c  lea     rdx, [r15+2]; DestinationSize
0x18007c480  mov     r8, r12; Source
0x18007c483  mov     rcx, rax; Destination
0x18007c486  call    memcpy_s_0
0x18007c48b  xor     r12d, r12d
0x18007c48e  mov     [r15+r14], r12w
0x18007c493  lea     rdx, [rbp+pv]
0x18007c497  mov     [rbp+pv], r14
0x18007c49b  lea     rcx, [rdi+10h]
0x18007c49f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c4a4  mov     rcx, [rbp+pv]; pv
0x18007c4a8  test    rcx, rcx
0x18007c4ab  jz      short loc_18007C4B9
0x18007c4ad  call    cs:__imp_CoTaskMemFree
0x18007c4b4  nop     dword ptr [rax+rax+00h]
0x18007c4b9  cmp     [rdi+10h], r12
0x18007c4bd  jz      loc_18007C644
0x18007c4c3  mov     rax, [rsi+18h]
0x18007c4c7  test    rax, rax
0x18007c4ca  jz      loc_18007C7C4
0x18007c4d0  mov     r15, rax
0x18007c4d3  cmp     [rax], r12w
0x18007c4d7  jz      short loc_18007C4E3
0x18007c4d9  add     rax, 2
0x18007c4dd  sub     rbx, 1
0x18007c4e1  jnz     short loc_18007C4D3
0x18007c4e3  sub     rax, r15
0x18007c4e6  sar     rax, 1
0x18007c4e9  lea     rsi, [rax+rax]
0x18007c4ed  lea     rcx, [rsi+2]; cb
0x18007c4f1  call    cs:__imp_CoTaskMemAlloc
0x18007c4f8  nop     dword ptr [rax+rax+00h]
0x18007c4fd  mov     rbx, rax
0x18007c500  test    rax, rax
0x18007c503  jz      short loc_18007C51C
0x18007c505  mov     r9, rsi; SourceSize
0x18007c508  lea     rdx, [rsi+2]; DestinationSize
0x18007c50c  mov     r8, r15; Source
0x18007c50f  mov     rcx, rax; Destination
0x18007c512  call    memcpy_s_0
0x18007c517  mov     [rsi+rbx], r12w
0x18007c51c  lea     rdx, [rbp+pv]
0x18007c520  mov     [rbp+pv], rbx
0x18007c524  lea     rcx, [rdi+18h]
0x18007c528  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c52d  mov     rcx, [rbp+pv]; pv
0x18007c531  test    rcx, rcx
0x18007c534  jz      short loc_18007C542
0x18007c536  call    cs:__imp_CoTaskMemFree
0x18007c53d  nop     dword ptr [rax+rax+00h]
0x18007c542  cmp     [rdi+18h], r12
0x18007c546  jnz     loc_18007C636
0x18007c54c  mov     edx, 0C1h
0x18007c551  jmp     short loc_18007C558
0x18007c553  mov     edx, 9Ch; void *
0x18007c558  mov     rcx, [rbp+38h]; this
0x18007c55c  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18007c563  mov     r9d, 8007000Eh; char *
0x18007c569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c56e  test    rdi, rdi
0x18007c571  jz      loc_18007C241
0x18007c577  mov     rcx, rdi; this
0x18007c57a  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007c57f  jmp     loc_18007C241
0x18007c584  mov     rcx, rbx
0x18007c587  mov     rax, r14
0x18007c58a  cmp     [rax], r13w
0x18007c58e  jz      short loc_18007C59A
0x18007c590  add     rax, 2
0x18007c594  sub     rcx, 1
0x18007c598  jnz     short loc_18007C58A
0x18007c59a  sub     rax, r14
0x18007c59d  sar     rax, 1
0x18007c5a0  lea     r12, [rax+rax]
0x18007c5a4  lea     rcx, [r12+2]; cb
0x18007c5a9  call    cs:__imp_CoTaskMemAlloc
0x18007c5b0  nop     dword ptr [rax+rax+00h]
0x18007c5b5  mov     r15, rax
0x18007c5b8  test    rax, rax
0x18007c5bb  jz      loc_18007C762
0x18007c5c1  mov     r9, r12; SourceSize
0x18007c5c4  lea     rdx, [r12+2]; DestinationSize
0x18007c5c9  mov     r8, r14; Source
0x18007c5cc  mov     rcx, rax; Destination
0x18007c5cf  call    memcpy_s_0
0x18007c5d4  xor     r13d, r13d
0x18007c5d7  mov     [r12+r15], r13w
0x18007c5dc  lea     rdx, [rbp+pv]
0x18007c5e0  mov     [rbp+pv], r15
0x18007c5e4  lea     rcx, [rdi+8]
0x18007c5e8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007c5ed  mov     rcx, [rbp+pv]; pv
0x18007c5f1  test    rcx, rcx
0x18007c5f4  jz      short loc_18007C602
0x18007c5f6  call    cs:__imp_CoTaskMemFree
0x18007c5fd  nop     dword ptr [rax+rax+00h]
0x18007c602  cmp     [rdi+8], r13
0x18007c606  jnz     loc_18007C2FD
0x18007c60c  mov     edx, 0A2h
0x18007c611  jmp     loc_18007C558
0x18007c616  mov     edx, 0A6h
0x18007c61b  jmp     loc_18007C558
0x18007c620  mov     edx, 0A9h
0x18007c625  jmp     loc_18007C558
0x18007c62a  mov     eax, [rsi+38h]
0x18007c62d  mov     [rdi+38h], eax
0x18007c630  mov     eax, [rsi+3Ch]
0x18007c633  mov     [rdi+3Ch], eax
0x18007c636  mov     rax, [rbp+var_8]
0x18007c63a  mov     [rax], rdi
0x18007c63d  xor     eax, eax
0x18007c63f  jmp     loc_18007C246
0x18007c644  mov     edx, 0BEh
0x18007c649  jmp     loc_18007C558
0x18007c64e  mov     rax, r14
0x18007c651  cmp     [rax], r13w
0x18007c655  jz      short loc_18007C661
0x18007c657  add     rax, 2
0x18007c65b  sub     rbx, 1
0x18007c65f  jnz     short loc_18007C651
0x18007c661  sub     rax, r14
0x18007c664  sar     rax, 1
0x18007c667  lea     r15, [rax+rax]
0x18007c66b  lea     rcx, [r15+2]; cb
0x18007c66f  call    cs:__imp_CoTaskMemAlloc
0x18007c676  nop     dword ptr [rax+rax+00h]
0x18007c67b  mov     rbx, rax
  ... truncated ...
```
