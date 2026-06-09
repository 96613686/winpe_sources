# EnableMitigations(void)

- ea: `0x180008fb0`
- end: `0x1800091d7`
- name: `?EnableMitigations@@YAXXZ`
- size: `551`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008cd0`

## callees

- `0x180008fb0`
- `0x1800091e0`
- `0x180054a42`
- `0x180054ad4`
- `0x18005a1b6`
- `0x18005c174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800091aa`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180009037`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x180009037`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800090f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800090f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008fb8`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180009125`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180009125`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008fce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800091c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000913e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000913e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009157`

## string_xrefs

- `0x18000918e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void EnableMitigations(void)
{
  DWORD CurrentProcessId; // eax
  char *v1; // rax
  char *v2; // rbx
  __int64 v3; // rdx
  WCHAR *v4; // rdi
  __int64 v5; // r8
  const WCHAR *v6; // rsi
  int StringOrdinal; // eax
  const char *v8; // r9
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  size_t v11; // r14
  size_t v12; // r15
  WCHAR *v13; // rax
  WCHAR *v14; // rbp
  int i; // esi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCWSTR lpStringSource; // [rsp+50h] [rbp+8h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v1 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  lpStringSource = 0;
  v2 = v1;
  wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
    v1,
    v3,
    &lpStringSource);
  v4 = (WCHAR *)lpStringSource;
  v5 = -1;
  do
    ++v5;
  while ( lpStringSource[v5] );
  v6 = &lpStringSource[v5];
  if ( v5 && *(v6 - 1) == 92 )
    LODWORD(v5) = v5 - 1;
  StringOrdinal = FindStringOrdinal(0x800000u, lpStringSource, v5, L"\\", 1, 1);
  if ( StringOrdinal != -1 )
    v6 = &v4[StringOrdinal + 1];
  if ( !v6 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v8);
  v9 = 0x7FFFFFFF;
  v10 = v6;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = 2 * (v10 - v6);
  v12 = v11 + 2;
  v13 = (WCHAR *)CoTaskMemAlloc(v11 + 2);
  v14 = v13;
  if ( v13 )
  {
    if ( v11 )
    {
      if ( v12 < v11 )
      {
        memset_0(v13, 0, v12);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v13, v6, v11);
      }
    }
    v14[v11 / 2] = 0;
  }
  for ( i = 0; !i; i = 1 )
  {
    if ( CompareStringOrdinal(v14, -1, L"dllhost.exe", -1, 1) == 2 )
    {
      LODWORD(lpStringSource) = 1;
      SetProcessMitigationPolicy(16, &lpStringSource, 4);
      break;
    }
  }
  if ( v14 )
    CoTaskMemFree(v14);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
}

```

## disassembly

```asm
0x180008fb0  push    rbx
0x180008fb2  push    rsi
0x180008fb3  push    rdi
0x180008fb4  sub     rsp, 30h
0x180008fb8  call    cs:__imp_GetCurrentProcessId
0x180008fbf  nop     dword ptr [rax+rax+00h]
0x180008fc4  xor     edx, edx; bInheritHandle
0x180008fc6  mov     ecx, 1000h; dwDesiredAccess
0x180008fcb  mov     r8d, eax; dwProcessId
0x180008fce  call    cs:__imp_OpenProcess
0x180008fd5  nop     dword ptr [rax+rax+00h]
0x180008fda  lea     r8, [rsp+48h+lpStringSource]
0x180008fdf  mov     [rsp+48h+lpStringSource], 0
0x180008fe8  mov     rcx, rax
0x180008feb  mov     rbx, rax
0x180008fee  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180008ff3  mov     rdi, [rsp+48h+lpStringSource]
0x180008ff8  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180008fff  nop
0x180009000  inc     r8; cchSource
0x180009003  cmp     word ptr [rdi+r8*2], 0
0x180009009  jnz     short loc_180009000
0x18000900b  lea     rsi, [rdi+r8*2]
0x18000900f  test    r8, r8
0x180009012  jnz     loc_180009176
0x180009018  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180009020  lea     r9, pszSrc; "\\"
0x180009027  mov     rdx, rdi; lpStringSource
0x18000902a  mov     [rsp+48h+cchValue], 1; cchValue
0x180009032  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x180009037  call    cs:__imp_FindStringOrdinal
0x18000903e  nop     dword ptr [rax+rax+00h]
0x180009043  cmp     eax, 0FFFFFFFFh
0x180009046  jz      short loc_180009052
0x180009048  movsxd  rsi, eax
0x18000904b  inc     rsi
0x18000904e  lea     rsi, [rdi+rsi*2]
0x180009052  test    rsi, rsi
0x180009055  jz      loc_180009189
0x18000905b  mov     [rsp+48h+arg_8], rbp
0x180009060  mov     ecx, 7FFFFFFFh
0x180009065  mov     [rsp+48h+arg_10], r14
0x18000906a  mov     rax, rsi
0x18000906d  mov     [rsp+48h+arg_18], r15
0x180009072  cmp     word ptr [rax], 0
0x180009076  jz      short loc_180009082
0x180009078  add     rax, 2
0x18000907c  sub     rcx, 1
0x180009080  jnz     short loc_180009072
0x180009082  sub     rax, rsi
0x180009085  sar     rax, 1
0x180009088  lea     r14, [rax+rax]
0x18000908c  lea     r15, [r14+2]
0x180009090  mov     rcx, r15; cb
0x180009093  call    cs:__imp_CoTaskMemAlloc
0x18000909a  nop     dword ptr [rax+rax+00h]
0x18000909f  mov     rbp, rax
0x1800090a2  test    rax, rax
0x1800090a5  jz      short loc_1800090CA
0x1800090a7  test    r14, r14
0x1800090aa  jz      short loc_1800090C3
0x1800090ac  mov     rcx, rax; void *
0x1800090af  cmp     r15, r14
0x1800090b2  jb      loc_1800091A0
0x1800090b8  mov     r8, r14; Size
0x1800090bb  mov     rdx, rsi; Src
0x1800090be  call    memcpy_0
0x1800090c3  xor     eax, eax
0x1800090c5  mov     [r14+rbp], ax
0x1800090ca  mov     r15, [rsp+48h+arg_18]
0x1800090cf  lea     r14, off_1800EE050; "dllhost.exe"
0x1800090d6  xor     esi, esi
0x1800090d8  cmp     esi, 1
0x1800090db  jnb     short loc_180009131
0x1800090dd  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800090e3  movsxd  r8, esi
0x1800090e6  mov     edx, r9d; cchCount1
0x1800090e9  mov     [rsp+48h+cchValue], 1; bIgnoreCase
0x1800090f1  mov     rcx, rbp; lpString1
0x1800090f4  mov     r8, [r14+r8*8]; lpString2
0x1800090f8  call    cs:__imp_CompareStringOrdinal
0x1800090ff  nop     dword ptr [rax+rax+00h]
0x180009104  cmp     eax, 2
0x180009107  jz      short loc_18000910D
0x180009109  inc     esi
0x18000910b  jmp     short loc_1800090D8
0x18000910d  mov     r8d, 4
0x180009113  mov     dword ptr [rsp+48h+lpStringSource], 1
0x18000911b  lea     rdx, [rsp+48h+lpStringSource]
0x180009120  mov     ecx, 10h
0x180009125  call    cs:__imp_SetProcessMitigationPolicy
0x18000912c  nop     dword ptr [rax+rax+00h]
0x180009131  mov     r14, [rsp+48h+arg_10]
0x180009136  test    rbp, rbp
0x180009139  jz      short loc_18000914A
0x18000913b  mov     rcx, rbp; pv
0x18000913e  call    cs:__imp_CoTaskMemFree
0x180009145  nop     dword ptr [rax+rax+00h]
0x18000914a  mov     rbp, [rsp+48h+arg_8]
0x18000914f  test    rdi, rdi
0x180009152  jz      short loc_180009163
0x180009154  mov     rcx, rdi; pv
0x180009157  call    cs:__imp_CoTaskMemFree
0x18000915e  nop     dword ptr [rax+rax+00h]
0x180009163  lea     rax, [rbx-1]
0x180009167  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000916b  jbe     short loc_1800091C6
0x18000916d  add     rsp, 30h
0x180009171  pop     rdi
0x180009172  pop     rsi
0x180009173  pop     rbx
0x180009174  retn
0x180009176  cmp     word ptr [rsi-2], 5Ch ; '\'
0x18000917b  jnz     loc_180009018
0x180009181  dec     r8
0x180009184  jmp     loc_180009018
0x180009189  mov     rcx, [rsp+48h]; this
0x18000918e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009195  mov     edx, 0F89h; void *
0x18000919a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800091a0  mov     r8, r15; Size
0x1800091a3  xor     edx, edx; Val
0x1800091a5  call    memset_0
0x1800091aa  call    cs:__imp__o__errno
0x1800091b1  nop     dword ptr [rax+rax+00h]
0x1800091b6  mov     dword ptr [rax], 22h ; '"'
0x1800091bc  call    _invalid_parameter_noinfo
0x1800091c1  jmp     loc_1800090C3
0x1800091c6  mov     rcx, rbx; hObject
0x1800091c9  call    cs:__imp_CloseHandle
0x1800091d0  nop     dword ptr [rax+rax+00h]
0x1800091d5  jmp     short loc_18000916D
```
