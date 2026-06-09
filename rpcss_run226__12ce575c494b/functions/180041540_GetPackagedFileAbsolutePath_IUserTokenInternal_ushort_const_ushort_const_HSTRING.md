# GetPackagedFileAbsolutePath(IUserTokenInternal *,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x180041540`
- end: `0x1800417dd`
- name: `?GetPackagedFileAbsolutePath@@YAJPEAUIUserTokenInternal@@PEBG1PEAPEAUHSTRING__@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct IUserTokenInternal *, const char *, const unsigned __int16 *, HSTRING *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cdc8`
- `0x1800411e8`
- `0x1800722a0`
- `0x1800dd430`
- `0x1800dfdb0`

## callees

- `0x18002ba28`
- `0x18002f8cc`
- `0x180041540`
- `0x1800418c0`
- `0x180042270`
- `0x18008e98c`
- `0x18009d39c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800415ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180041749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x1800415ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180041749`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18004168f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18004168f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800415c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x1800415c2`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004158b`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x180041644`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004158b`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x180041644`

## string_xrefs

- `0x1800415d7`: `onecore\com\combase\catalog\services.cxx`
- `0x18004169f`: `onecore\com\combase\catalog\services.cxx`
- `0x1800416e1`: `onecore\com\combase\catalog\services.cxx`
- `0x18004172a`: `onecore\com\combase\catalog\services.cxx`
- `0x18004177c`: `onecore\com\combase\catalog\services.cxx`

## pseudocode

```c
__int64 __fastcall GetPackagedFileAbsolutePath(
        struct IUserTokenInternal *a1,
        const char *a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  unsigned int StagedPackagePathByFullName2; // eax
  __int64 v9; // rcx
  int v10; // r14d
  HRESULT v11; // edi
  __int64 v12; // rdx
  unsigned int v14; // r14d
  unsigned int v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-38h]
  unsigned int v19; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-24h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+38h] [rbp-20h] BYREF
  WCHAR *charBuffer; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  if ( a1 || !g_bInSCM )
  {
    v19 = 0;
    if ( a1 )
    {
      v17 = (*(__int64 (__fastcall **)(struct IUserTokenInternal *, _QWORD, unsigned int *))(*(_QWORD *)a1 + 96LL))(
              a1,
              0,
              &v19);
      v11 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC74,
          (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
          (const char *)(unsigned int)v17,
          v18);
        return (unsigned int)v11;
      }
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
    v19 = 0;
  }
  v20 = 0;
  StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(a2, 2, &v20);
  if ( StagedPackagePathByFullName2 != 122 && StagedPackagePathByFullName2 )
  {
    v11 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)0xC85,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)StagedPackagePathByFullName2,
            (unsigned int)"PackageFullName:%ws",
            a2);
    goto LABEL_28;
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = v9 + v20;
  charBuffer = 0;
  bufferHandle = 0;
  v11 = WindowsPreallocateStringBuffer(v9 + v20, &charBuffer, &bufferHandle);
  if ( v11 < 0 )
  {
    v12 = 3216;
    goto LABEL_8;
  }
  if ( *a3 == 34 )
  {
    *charBuffer = 34;
    --v10;
    ++charBuffer;
    ++a3;
  }
  v14 = v10 + 1;
  v20 = v14;
  v15 = GetStagedPackagePathByFullName2(a2, 2, &v20);
  if ( v15 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xCA0,
            (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
            (const char *)v15,
            v18);
    if ( bufferHandle )
      WindowsDeleteStringBuffer(bufferHandle);
LABEL_28:
    if ( !a1 )
      return (unsigned int)v11;
    goto LABEL_11;
  }
  v11 = StringCchCatW(charBuffer, v14, L"\\");
  if ( v11 < 0 )
  {
    v12 = 3234;
    goto LABEL_8;
  }
  v11 = StringCchCatW(charBuffer, v14, a3);
  if ( v11 < 0 )
  {
    v12 = 3235;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)v11,
      v18);
    if ( bufferHandle )
      WindowsDeleteStringBuffer(bufferHandle);
LABEL_10:
    if ( !a1 )
      return (unsigned int)v11;
LABEL_11:
    (*(void (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a1 + 104LL))(a1, v19);
    return (unsigned int)v11;
  }
  v16 = WindowsPromoteStringBuffer(bufferHandle, a4);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA5,
      (unsigned int)"onecore\\com\\combase\\catalog\\services.cxx",
      (const char *)(unsigned int)v16,
      v18);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&long WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(&bufferHandle);
    goto LABEL_10;
  }
  bufferHandle = 0;
  if ( a1 )
    (*(void (__fastcall **)(struct IUserTokenInternal *, _QWORD))(*(_QWORD *)a1 + 104LL))(a1, v19);
  return 0;
}

```

## disassembly

```asm
0x180041540  push    rbp
0x180041542  push    rbx
0x180041543  push    rsi
0x180041544  push    rdi
0x180041545  push    r12
0x180041547  push    r13
0x180041549  push    r14
0x18004154b  push    r15
0x18004154d  mov     rbp, rsp
0x180041550  sub     rsp, 58h
0x180041554  xor     r13d, r13d
0x180041557  mov     r12, r9
0x18004155a  mov     rsi, r8
0x18004155d  mov     r15, rdx
0x180041560  mov     rbx, rcx
0x180041563  test    rcx, rcx
0x180041566  jz      loc_1800417A3
0x18004156c  mov     [rbp+var_28], r13d
0x180041570  test    rbx, rbx
0x180041573  jnz     loc_1800416C1
0x180041579  xor     r9d, r9d
0x18004157c  mov     [rbp+var_24], r13d
0x180041580  lea     r8, [rbp+var_24]
0x180041584  mov     rcx, r15
0x180041587  lea     edx, [r9+2]
0x18004158b  call    cs:__imp_GetStagedPackagePathByFullName2
0x180041591  cmp     eax, 7Ah ; 'z'
0x180041594  jnz     loc_180041764
0x18004159a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004159e  inc     rcx
0x1800415a1  cmp     [rsi+rcx*2], r13w
0x1800415a6  jnz     short loc_18004159E
0x1800415a8  mov     r14d, [rbp+var_24]
0x1800415ac  lea     r8, [rbp+bufferHandle]; bufferHandle
0x1800415b0  add     r14d, ecx
0x1800415b3  mov     [rbp+charBuffer], r13
0x1800415b7  mov     ecx, r14d; length
0x1800415ba  mov     [rbp+bufferHandle], r13
0x1800415be  lea     rdx, [rbp+charBuffer]; charBuffer
0x1800415c2  call    cs:__imp_WindowsPreallocateStringBuffer
0x1800415c8  mov     edi, eax
0x1800415ca  test    eax, eax
0x1800415cc  jns     short loc_18004161F
0x1800415ce  mov     edx, 0C90h; void *
0x1800415d3  mov     rcx, [rbp+40h]; this
0x1800415d7  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800415de  mov     r9d, edi; char *
0x1800415e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800415e6  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x1800415ea  test    rcx, rcx
0x1800415ed  jz      short loc_1800415F5
0x1800415ef  call    cs:__imp_WindowsDeleteStringBuffer
0x1800415f5  test    rbx, rbx
0x1800415f8  jz      short loc_18004160C
0x1800415fa  mov     rax, [rbx]
0x1800415fd  mov     rax, [rax+68h]
0x180041601  mov     edx, [rbp+var_28]
0x180041604  mov     rcx, rbx
0x180041607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004160c  mov     eax, edi
0x18004160e  add     rsp, 58h
0x180041612  pop     r15
0x180041614  pop     r14
0x180041616  pop     r13
0x180041618  pop     r12
0x18004161a  pop     rdi
0x18004161b  pop     rsi
0x18004161c  pop     rbx
0x18004161d  pop     rbp
0x18004161e  retn
0x18004161f  mov     ecx, 22h ; '"'
0x180041624  cmp     [rsi], cx
0x180041627  jz      loc_1800417BE
0x18004162d  mov     r9, [rbp+charBuffer]
0x180041631  inc     r14d
0x180041634  lea     r8, [rbp+var_24]
0x180041638  mov     edx, 2
0x18004163d  mov     [rbp+var_24], r14d
0x180041641  mov     rcx, r15
0x180041644  call    cs:__imp_GetStagedPackagePathByFullName2
0x18004164a  test    eax, eax
0x18004164c  jnz     loc_180041726
0x180041652  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x180041656  lea     r8, asc_18011A070; "\\"
0x18004165d  mov     edx, r14d; unsigned __int64
0x180041660  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041665  mov     edi, eax
0x180041667  test    eax, eax
0x180041669  js      loc_18004171C
0x18004166f  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x180041673  mov     r8, rsi; unsigned __int16 *
0x180041676  mov     edx, r14d; unsigned __int64
0x180041679  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004167e  mov     edi, eax
0x180041680  test    eax, eax
0x180041682  js      loc_180041799
0x180041688  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18004168c  mov     rdx, r12; string
0x18004168f  call    cs:__imp_WindowsPromoteStringBuffer
0x180041695  mov     edi, eax
0x180041697  test    eax, eax
0x180041699  jns     short loc_1800416FA
0x18004169b  mov     rcx, [rbp+40h]; this
0x18004169f  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800416a6  mov     r9d, eax; char *
0x1800416a9  mov     edx, 0CA5h; void *
0x1800416ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416b3  lea     rcx, [rbp+bufferHandle]
0x1800416b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x1800416bc  jmp     loc_1800415F5
0x1800416c1  mov     rax, [rcx]
0x1800416c4  lea     r8, [rbp+var_28]
0x1800416c8  xor     edx, edx
0x1800416ca  mov     rax, [rax+60h]
0x1800416ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416d3  mov     edi, eax
0x1800416d5  test    eax, eax
0x1800416d7  jns     loc_180041579
0x1800416dd  mov     rcx, [rbp+40h]; this
0x1800416e1  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x1800416e8  mov     r9d, eax; char *
0x1800416eb  mov     edx, 0C74h; void *
0x1800416f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800416f5  jmp     loc_18004160C
0x1800416fa  mov     [rbp+bufferHandle], r13
0x1800416fe  test    rbx, rbx
0x180041701  jz      short loc_180041715
0x180041703  mov     rax, [rbx]
0x180041706  mov     rcx, rbx
0x180041709  mov     edx, [rbp+var_28]
0x18004170c  mov     rax, [rax+68h]
0x180041710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041715  xor     eax, eax
0x180041717  jmp     loc_18004160E
0x18004171c  mov     edx, 0CA2h
0x180041721  jmp     loc_1800415D3
0x180041726  mov     rcx, [rbp+40h]; this
0x18004172a  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180041731  mov     r9d, eax; char *
0x180041734  mov     edx, 0CA0h; void *
0x180041739  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004173e  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x180041742  mov     edi, eax
0x180041744  test    rcx, rcx
0x180041747  jz      short loc_18004174F
0x180041749  call    cs:__imp_WindowsDeleteStringBuffer
0x18004174f  test    rbx, rbx
0x180041752  jz      loc_18004160C
0x180041758  mov     rcx, [rbx]
0x18004175b  mov     rax, [rcx+68h]
0x18004175f  jmp     loc_180041601
0x180041764  test    eax, eax
0x180041766  jz      loc_18004159A
0x18004176c  mov     rcx, [rbp+40h]; this
0x180041770  lea     rdx, aPackagefullnam; "PackageFullName:%ws"
0x180041777  mov     [rsp+58h+var_30], r15; char *
0x18004177c  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x180041783  mov     qword ptr [rsp+58h+var_38], rdx; unsigned int
0x180041788  mov     r9d, eax; char *
0x18004178b  mov     edx, 0C85h; void *
0x180041790  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180041795  mov     edi, eax
0x180041797  jmp     short loc_18004174F
0x180041799  mov     edx, 0CA3h
0x18004179e  jmp     loc_1800415D3
0x1800417a3  cmp     cs:?g_bInSCM@@3JA, r13d; long g_bInSCM
0x1800417aa  jz      loc_18004156C
0x1800417b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800417b5  mov     [rbp+var_28], r13d
0x1800417b9  jmp     loc_180041579
0x1800417be  mov     rax, [rbp+charBuffer]
0x1800417c2  mov     [rax], cx
0x1800417c5  mov     r9, [rbp+charBuffer]
0x1800417c9  add     r9, 2
0x1800417cd  dec     r14d
0x1800417d0  mov     [rbp+charBuffer], r9
0x1800417d4  add     rsi, 2
0x1800417d8  jmp     loc_180041631
```
