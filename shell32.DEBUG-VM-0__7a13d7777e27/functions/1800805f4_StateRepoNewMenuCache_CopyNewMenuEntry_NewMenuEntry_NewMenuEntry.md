# StateRepoNewMenuCache::CopyNewMenuEntry(NewMenuEntry *,NewMenuEntry * *)

- ea: `0x1800805f4`
- end: `0x180080b89`
- name: `?CopyNewMenuEntry@StateRepoNewMenuCache@@AEAAJPEAUNewMenuEntry@@PEAPEAU2@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(StateRepoNewMenuCache *__hidden this, struct NewMenuEntry *, struct NewMenuEntry **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180080dc8`

## callees

- `0x1800181e0`
- `0x1800295b0`
- `0x18003cd64`
- `0x18007fd9c`
- `0x180080470`
- `0x1800805f4`
- `0x180080d44`
- `0x1801a8498`
- `0x1802464f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008076b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800807f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800809b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008076b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800807f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800809b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080a69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800807ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800808c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080a2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080725`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800807ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800808c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180080a2a`

## string_xrefs

- `0x18008062e`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180080923`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x180080af7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180080b1d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180080b3b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180080b59`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180080b77`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800805f4  mov     [rsp-38h+arg_0], rbx
0x1800805f9  push    rbp
0x1800805fa  push    rsi
0x1800805fb  push    rdi
0x1800805fc  push    r12
0x1800805fe  push    r13
0x180080600  push    r14
0x180080602  push    r15
0x180080604  mov     rbp, rsp
0x180080607  sub     rsp, 30h
0x18008060b  xor     r14d, r14d
0x18008060e  mov     [rbp+var_8], r8
0x180080612  lea     rcx, [rbp+pv]
0x180080616  mov     [r8], r14
0x180080619  mov     rsi, rdx
0x18008061c  call    ??$make_unique_nothrow@UNewMenuEntry@@$$V@wil@@YA?AV?$unique_ptr@UNewMenuEntry@@U?$default_delete@UNewMenuEntry@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<NewMenuEntry,>(void)
0x180080621  mov     rdi, [rbp+pv]
0x180080625  test    rdi, rdi
0x180080628  jnz     short loc_18008065F
0x18008062a  mov     rcx, [rbp+38h]; this
0x18008062e  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x180080635  mov     r9d, 8007000Eh; char *
0x18008063b  mov     edx, 99h; void *
0x180080640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080645  mov     eax, 8007000Eh
0x18008064a  mov     rbx, [rsp+30h+arg_0]
0x18008064f  add     rsp, 30h
0x180080653  pop     r15
0x180080655  pop     r14
0x180080657  pop     r13
0x180080659  pop     r12
0x18008065b  pop     rdi
0x18008065c  pop     rsi
0x18008065d  pop     rbp
0x18008065e  retn
0x18008065f  mov     rax, [rsi]
0x180080662  test    rax, rax
0x180080665  jz      loc_180080AF3
0x18008066b  mov     ebx, 7FFFFFFFh
0x180080670  mov     r12, rax
0x180080673  mov     ecx, ebx
0x180080675  cmp     [rax], r14w
0x180080679  jz      short loc_180080685
0x18008067b  add     rax, 2
0x18008067f  sub     rcx, 1
0x180080683  jnz     short loc_180080675
0x180080685  sub     rax, r12
0x180080688  sar     rax, 1
0x18008068b  lea     r15, [rax+rax]
0x18008068f  lea     rcx, [r15+2]; cb
0x180080693  call    cs:__imp_CoTaskMemAlloc
0x180080699  mov     r14, rax
0x18008069c  test    rax, rax
0x18008069f  jz      loc_180080B09
0x1800806a5  mov     r9, r15; SourceSize
0x1800806a8  lea     rdx, [r15+2]; DestinationSize
0x1800806ac  mov     r8, r12; Source
0x1800806af  mov     rcx, rax; Destination
0x1800806b2  call    memcpy_s_0
0x1800806b7  xor     r13d, r13d
0x1800806ba  mov     [r15+r14], r13w
0x1800806bf  lea     rdx, [rbp+pv]
0x1800806c3  mov     [rbp+pv], r14
0x1800806c7  mov     rcx, rdi
0x1800806ca  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800806cf  mov     rcx, [rbp+pv]; pv
0x1800806d3  test    rcx, rcx
0x1800806d6  jz      short loc_1800806DE
0x1800806d8  call    cs:__imp_CoTaskMemFree
0x1800806de  cmp     [rdi], r13
0x1800806e1  jz      loc_18008091A
0x1800806e7  mov     r14, [rsi+8]
0x1800806eb  test    r14, r14
0x1800806ee  jnz     loc_18008094B
0x1800806f4  mov     rax, [rsi+40h]
0x1800806f8  test    rax, rax
0x1800806fb  jz      loc_180080B19
0x180080701  mov     rcx, rbx
0x180080704  mov     r12, rax
0x180080707  cmp     [rax], r13w
0x18008070b  jz      short loc_180080717
0x18008070d  add     rax, 2
0x180080711  sub     rcx, 1
0x180080715  jnz     short loc_180080707
0x180080717  sub     rax, r12
0x18008071a  sar     rax, 1
0x18008071d  lea     r15, [rax+rax]
0x180080721  lea     rcx, [r15+2]; cb
0x180080725  call    cs:__imp_CoTaskMemAlloc
0x18008072b  mov     r14, rax
0x18008072e  test    rax, rax
0x180080731  jz      loc_180080B2F
0x180080737  mov     r9, r15; SourceSize
0x18008073a  lea     rdx, [r15+2]; DestinationSize
0x18008073e  mov     r8, r12; Source
0x180080741  mov     rcx, rax; Destination
0x180080744  call    memcpy_s_0
0x180080749  xor     r13d, r13d
0x18008074c  mov     [r15+r14], r13w
0x180080751  lea     rdx, [rbp+pv]
0x180080755  mov     [rbp+pv], r14
0x180080759  lea     rcx, [rdi+40h]
0x18008075d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180080762  mov     rcx, [rbp+pv]; pv
0x180080766  test    rcx, rcx
0x180080769  jz      short loc_180080771
0x18008076b  call    cs:__imp_CoTaskMemFree
0x180080771  cmp     [rdi+40h], r13
0x180080775  jz      loc_1800809D1
0x18008077b  mov     rax, [rsi+48h]
0x18008077f  test    rax, rax
0x180080782  jz      loc_180080B37
0x180080788  mov     rcx, rbx
0x18008078b  mov     r12, rax
0x18008078e  cmp     [rax], r13w
0x180080792  jz      short loc_18008079E
0x180080794  add     rax, 2
0x180080798  sub     rcx, 1
0x18008079c  jnz     short loc_18008078E
0x18008079e  sub     rax, r12
0x1800807a1  sar     rax, 1
0x1800807a4  lea     r15, [rax+rax]
0x1800807a8  lea     rcx, [r15+2]; cb
0x1800807ac  call    cs:__imp_CoTaskMemAlloc
0x1800807b2  mov     r14, rax
0x1800807b5  test    rax, rax
0x1800807b8  jz      loc_180080B4D
0x1800807be  mov     r9, r15; SourceSize
0x1800807c1  lea     rdx, [r15+2]; DestinationSize
0x1800807c5  mov     r8, r12; Source
0x1800807c8  mov     rcx, rax; Destination
0x1800807cb  call    memcpy_s_0
0x1800807d0  xor     r13d, r13d
0x1800807d3  mov     [r15+r14], r13w
0x1800807d8  lea     rdx, [rbp+pv]
0x1800807dc  mov     [rbp+pv], r14
0x1800807e0  lea     rcx, [rdi+48h]
0x1800807e4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800807e9  mov     rcx, [rbp+pv]; pv
0x1800807ed  test    rcx, rcx
0x1800807f0  jz      short loc_1800807F8
0x1800807f2  call    cs:__imp_CoTaskMemFree
0x1800807f8  cmp     [rdi+48h], r13
0x1800807fc  jz      loc_1800809DB
0x180080802  mov     r14, [rsi+20h]
0x180080806  test    r14, r14
0x180080809  jnz     loc_180080A09
0x18008080f  mov     rax, [rsi+10h]
0x180080813  test    rax, rax
0x180080816  jz      loc_180080B55
0x18008081c  mov     rcx, rbx
0x18008081f  mov     r12, rax
0x180080822  cmp     [rax], r13w
0x180080826  jz      short loc_180080832
0x180080828  add     rax, 2
0x18008082c  sub     rcx, 1
0x180080830  jnz     short loc_180080822
0x180080832  sub     rax, r12
0x180080835  sar     rax, 1
0x180080838  lea     r15, [rax+rax]
0x18008083c  lea     rcx, [r15+2]; cb
0x180080840  call    cs:__imp_CoTaskMemAlloc
0x180080846  mov     r14, rax
0x180080849  test    rax, rax
0x18008084c  jz      loc_180080B6B
0x180080852  mov     r9, r15; SourceSize
0x180080855  lea     rdx, [r15+2]; DestinationSize
0x180080859  mov     r8, r12; Source
0x18008085c  mov     rcx, rax; Destination
0x18008085f  call    memcpy_s_0
0x180080864  xor     r12d, r12d
0x180080867  mov     [r15+r14], r12w
0x18008086c  lea     rdx, [rbp+pv]
0x180080870  mov     [rbp+pv], r14
0x180080874  lea     rcx, [rdi+10h]
0x180080878  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18008087d  mov     rcx, [rbp+pv]; pv
0x180080881  test    rcx, rcx
0x180080884  jz      short loc_18008088C
0x180080886  call    cs:__imp_CoTaskMemFree
0x18008088c  cmp     [rdi+10h], r12
0x180080890  jz      loc_1800809FF
0x180080896  mov     rax, [rsi+18h]
0x18008089a  test    rax, rax
0x18008089d  jz      loc_180080B73
0x1800808a3  mov     r15, rax
0x1800808a6  cmp     [rax], r12w
0x1800808aa  jz      short loc_1800808B6
0x1800808ac  add     rax, 2
0x1800808b0  sub     rbx, 1
0x1800808b4  jnz     short loc_1800808A6
0x1800808b6  sub     rax, r15
0x1800808b9  sar     rax, 1
0x1800808bc  lea     rsi, [rax+rax]
0x1800808c0  lea     rcx, [rsi+2]; cb
0x1800808c4  call    cs:__imp_CoTaskMemAlloc
0x1800808ca  mov     rbx, rax
0x1800808cd  test    rax, rax
0x1800808d0  jz      short loc_1800808E9
0x1800808d2  mov     r9, rsi; SourceSize
0x1800808d5  lea     rdx, [rsi+2]; DestinationSize
0x1800808d9  mov     r8, r15; Source
0x1800808dc  mov     rcx, rax; Destination
0x1800808df  call    memcpy_s_0
0x1800808e4  mov     [rsi+rbx], r12w
0x1800808e9  lea     rdx, [rbp+pv]
0x1800808ed  mov     [rbp+pv], rbx
0x1800808f1  lea     rcx, [rdi+18h]
0x1800808f5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800808fa  mov     rcx, [rbp+pv]; pv
0x1800808fe  test    rcx, rcx
0x180080901  jz      short loc_180080909
0x180080903  call    cs:__imp_CoTaskMemFree
0x180080909  cmp     [rdi+18h], r12
0x18008090d  jnz     loc_1800809F1
0x180080913  mov     edx, 0C1h
0x180080918  jmp     short loc_18008091F
0x18008091a  mov     edx, 9Ch; void *
0x18008091f  mov     rcx, [rbp+38h]; this
0x180080923  lea     r8, aShellShell32Un_12; "shell\\shell32\\unicpp\\statereponewmen"...
0x18008092a  mov     r9d, 8007000Eh; char *
0x180080930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080935  test    rdi, rdi
0x180080938  jz      loc_180080645
0x18008093e  mov     rcx, rdi; this
0x180080941  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x180080946  jmp     loc_180080645
0x18008094b  mov     rcx, rbx
0x18008094e  mov     rax, r14
0x180080951  cmp     [rax], r13w
0x180080955  jz      short loc_180080961
0x180080957  add     rax, 2
0x18008095b  sub     rcx, 1
0x18008095f  jnz     short loc_180080951
0x180080961  sub     rax, r14
0x180080964  sar     rax, 1
0x180080967  lea     r12, [rax+rax]
0x18008096b  lea     rcx, [r12+2]; cb
0x180080970  call    cs:__imp_CoTaskMemAlloc
0x180080976  mov     r15, rax
0x180080979  test    rax, rax
0x18008097c  jz      loc_180080B11
0x180080982  mov     r9, r12; SourceSize
0x180080985  lea     rdx, [r12+2]; DestinationSize
0x18008098a  mov     r8, r14; Source
0x18008098d  mov     rcx, rax; Destination
0x180080990  call    memcpy_s_0
0x180080995  xor     r13d, r13d
0x180080998  mov     [r12+r15], r13w
0x18008099d  lea     rdx, [rbp+pv]
0x1800809a1  mov     [rbp+pv], r15
0x1800809a5  lea     rcx, [rdi+8]
0x1800809a9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800809ae  mov     rcx, [rbp+pv]; pv
0x1800809b2  test    rcx, rcx
0x1800809b5  jz      short loc_1800809BD
0x1800809b7  call    cs:__imp_CoTaskMemFree
0x1800809bd  cmp     [rdi+8], r13
0x1800809c1  jnz     loc_1800806F4
0x1800809c7  mov     edx, 0A2h
0x1800809cc  jmp     loc_18008091F
0x1800809d1  mov     edx, 0A6h
0x1800809d6  jmp     loc_18008091F
0x1800809db  mov     edx, 0A9h
0x1800809e0  jmp     loc_18008091F
0x1800809e5  mov     eax, [rsi+38h]
0x1800809e8  mov     [rdi+38h], eax
0x1800809eb  mov     eax, [rsi+3Ch]
0x1800809ee  mov     [rdi+3Ch], eax
0x1800809f1  mov     rax, [rbp+var_8]
0x1800809f5  mov     [rax], rdi
0x1800809f8  xor     eax, eax
0x1800809fa  jmp     loc_18008064A
0x1800809ff  mov     edx, 0BEh
0x180080a04  jmp     loc_18008091F
0x180080a09  mov     rax, r14
0x180080a0c  cmp     [rax], r13w
0x180080a10  jz      short loc_180080A1C
0x180080a12  add     rax, 2
0x180080a16  sub     rbx, 1
0x180080a1a  jnz     short loc_180080A0C
0x180080a1c  sub     rax, r14
0x180080a1f  sar     rax, 1
0x180080a22  lea     r15, [rax+rax]
0x180080a26  lea     rcx, [r15+2]; cb
0x180080a2a  call    cs:__imp_CoTaskMemAlloc
0x180080a30  mov     rbx, rax
0x180080a33  test    rax, rax
0x180080a36  jz      short loc_180080A4F
0x180080a38  mov     r9, r15; SourceSize
0x180080a3b  lea     rdx, [r15+2]; DestinationSize
0x180080a3f  mov     r8, r14; Source
0x180080a42  mov     rcx, rax; Destination
0x180080a45  call    memcpy_s_0
0x180080a4a  mov     [r15+rbx], r13w
0x180080a4f  lea     rdx, [rbp+pv]
0x180080a53  mov     [rbp+pv], rbx
0x180080a57  lea     rcx, [rdi+20h]
0x180080a5b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180080a60  mov     rcx, [rbp+pv]; pv
  ... truncated ...
```
