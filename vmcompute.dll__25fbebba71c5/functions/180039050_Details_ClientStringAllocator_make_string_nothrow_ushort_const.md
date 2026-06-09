# Details::ClientStringAllocator::make_string_nothrow(ushort const *)

- ea: `0x180039050`
- end: `0x180039147`
- name: `?make_string_nothrow@ClientStringAllocator@Details@@QEAAXPEBG@Z`
- size: `247`
- prototype: `void __fastcall(Details::ClientStringAllocator *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038870`

## callees

- `0x180017014`
- `0x180037f54`
- `0x180039050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800390f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800390a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039114`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800390a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039131`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039097`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390c2`

## pseudocode

```c
void __fastcall Details::ClientStringAllocator::make_string_nothrow(
        Details::ClientStringAllocator *this,
        char *a2,
        __int64 a3,
        const char *a4)
{
  HLOCAL *v5; // rdi
  HLOCAL v6; // rsi
  HLOCAL v7; // rbp
  DWORD v8; // ebx
  HLOCAL v9; // rcx
  LPVOID *v10; // rdi
  void *v11; // rsi
  LPVOID v12; // rbp
  DWORD LastError; // ebx
  void *v14; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv[6]; // [rsp+28h] [rbp-30h] BYREF

  if ( *(_DWORD *)this )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      pv,
      a2,
      a3,
      a4);
    v10 = (LPVOID *)((char *)this + 16);
    if ( v10 == pv )
    {
      v14 = pv[0];
    }
    else
    {
      v11 = *v10;
      v12 = pv[0];
      if ( *v10 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v11);
        SetLastError(LastError);
      }
      *v10 = v12;
      v14 = 0;
    }
    if ( v14 )
      CoTaskMemFree(v14);
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      a2,
      a3,
      a4);
    v5 = (HLOCAL *)((char *)this + 8);
    if ( v5 == &hMem )
    {
      v9 = hMem;
    }
    else
    {
      v6 = *v5;
      v7 = hMem;
      if ( *v5 )
      {
        v8 = GetLastError();
        LocalFree(v6);
        SetLastError(v8);
      }
      *v5 = v7;
      v9 = 0;
    }
    if ( v9 )
      LocalFree(v9);
  }
}

```

## disassembly

```asm
0x180039050  push    rbx
0x180039052  push    rbp
0x180039053  push    rsi
0x180039054  push    rdi
0x180039055  sub     rsp, 38h
0x180039059  cmp     dword ptr [rcx], 0
0x18003905c  mov     rdi, rcx
0x18003905f  jnz     short loc_1800390D0
0x180039061  lea     rcx, [rsp+58h+hMem]
0x180039066  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003906b  lea     rax, [rsp+58h+hMem]
0x180039070  add     rdi, 8
0x180039074  cmp     rdi, rax
0x180039077  jz      short loc_1800390B8
0x180039079  mov     rsi, [rdi]
0x18003907c  mov     rbp, [rsp+58h+hMem]
0x180039081  test    rsi, rsi
0x180039084  jz      short loc_1800390B1
0x180039086  call    cs:__imp_GetLastError
0x18003908d  nop     dword ptr [rax+rax+00h]
0x180039092  mov     rcx, rsi; hMem
0x180039095  mov     ebx, eax
0x180039097  call    cs:__imp_LocalFree
0x18003909e  nop     dword ptr [rax+rax+00h]
0x1800390a3  mov     ecx, ebx; dwErrCode
0x1800390a5  call    cs:__imp_SetLastError
0x1800390ac  nop     dword ptr [rax+rax+00h]
0x1800390b1  mov     [rdi], rbp
0x1800390b4  xor     ecx, ecx
0x1800390b6  jmp     short loc_1800390BD
0x1800390b8  mov     rcx, [rsp+58h+hMem]; hMem
0x1800390bd  test    rcx, rcx
0x1800390c0  jz      short loc_18003913D
0x1800390c2  call    cs:__imp_LocalFree
0x1800390c9  nop     dword ptr [rax+rax+00h]
0x1800390ce  jmp     short loc_18003913D
0x1800390d0  lea     rcx, [rsp+58h+pv]
0x1800390d5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800390da  lea     rax, [rsp+58h+pv]
0x1800390df  add     rdi, 10h
0x1800390e3  cmp     rdi, rax
0x1800390e6  jz      short loc_180039127
0x1800390e8  mov     rsi, [rdi]
0x1800390eb  mov     rbp, [rsp+58h+pv]
0x1800390f0  test    rsi, rsi
0x1800390f3  jz      short loc_180039120
0x1800390f5  call    cs:__imp_GetLastError
0x1800390fc  nop     dword ptr [rax+rax+00h]
0x180039101  mov     rcx, rsi; pv
0x180039104  mov     ebx, eax
0x180039106  call    cs:__imp_CoTaskMemFree
0x18003910d  nop     dword ptr [rax+rax+00h]
0x180039112  mov     ecx, ebx; dwErrCode
0x180039114  call    cs:__imp_SetLastError
0x18003911b  nop     dword ptr [rax+rax+00h]
0x180039120  mov     [rdi], rbp
0x180039123  xor     ecx, ecx
0x180039125  jmp     short loc_18003912C
0x180039127  mov     rcx, [rsp+58h+pv]; pv
0x18003912c  test    rcx, rcx
0x18003912f  jz      short loc_18003913D
0x180039131  call    cs:__imp_CoTaskMemFree
0x180039138  nop     dword ptr [rax+rax+00h]
0x18003913d  add     rsp, 38h
0x180039141  pop     rdi
0x180039142  pop     rsi
0x180039143  pop     rbp
0x180039144  pop     rbx
0x180039145  retn
```
