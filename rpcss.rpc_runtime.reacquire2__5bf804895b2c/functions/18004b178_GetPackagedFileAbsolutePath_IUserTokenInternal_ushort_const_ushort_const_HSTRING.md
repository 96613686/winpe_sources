# GetPackagedFileAbsolutePath(IUserTokenInternal *,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x18004b178`
- end: `0x18004b43a`
- name: `?GetPackagedFileAbsolutePath@@YAJPEAUIUserTokenInternal@@PEBG1PEAPEAUHSTRING__@@@Z`
- size: `706`
- prototype: `int(struct IUserTokenInternal *, const unsigned __int16 *, const unsigned __int16 *, HSTRING *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012c20`
- `0x18004adcc`
- `0x18007693c`
- `0x1800e43b0`
- `0x1800e6f50`

## callees

- `0x1800210f8`
- `0x180025950`
- `0x18004b178`
- `0x18004b524`
- `0x18004bf1c`
- `0x180095c0c`
- `0x1800a2aec`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004b233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004b3a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004b233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18004b3a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18004b2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18004b2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18004b200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18004b200`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004b1c3`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004b28f`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004b1c3`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18004b28f`

## string_xrefs

- `0x18004b21b`: `onecore\com\combase\catalog\services.cxx`
- `0x18004b2f6`: `onecore\com\combase\catalog\services.cxx`
- `0x18004b338`: `onecore\com\combase\catalog\services.cxx`
- `0x18004b381`: `onecore\com\combase\catalog\services.cxx`
- `0x18004b3d9`: `onecore\com\combase\catalog\services.cxx`

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
0x18004b178  push    rbp
0x18004b17a  push    rbx
0x18004b17b  push    rsi
0x18004b17c  push    rdi
0x18004b17d  push    r12
0x18004b17f  push    r13
0x18004b181  push    r14
0x18004b183  push    r15
0x18004b185  mov     rbp, rsp
0x18004b188  sub     rsp, 58h
0x18004b18c  xor     r13d, r13d
0x18004b18f  mov     r12, r9
0x18004b192  mov     rsi, r8
0x18004b195  mov     r15, rdx
0x18004b198  mov     rbx, rcx
0x18004b19b  test    rcx, rcx
0x18004b19e  jz      loc_18004B400
0x18004b1a4  mov     [rbp+var_28], r13d
0x18004b1a8  test    rbx, rbx
0x18004b1ab  jnz     loc_18004B318
0x18004b1b1  xor     r9d, r9d
0x18004b1b4  mov     [rbp+var_24], r13d
0x18004b1b8  lea     r8, [rbp+var_24]
0x18004b1bc  mov     rcx, r15
0x18004b1bf  lea     edx, [r9+2]
0x18004b1c3  call    cs:__imp_GetStagedPackagePathByFullName2
0x18004b1ca  nop     dword ptr [rax+rax+00h]
0x18004b1cf  cmp     eax, 7Ah ; 'z'
0x18004b1d2  jnz     loc_18004B3C1
0x18004b1d8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004b1dc  inc     rcx
0x18004b1df  cmp     [rsi+rcx*2], r13w
0x18004b1e4  jnz     short loc_18004B1DC
0x18004b1e6  mov     r14d, [rbp+var_24]
0x18004b1ea  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18004b1ee  add     r14d, ecx
0x18004b1f1  mov     [rbp+charBuffer], r13
0x18004b1f5  mov     ecx, r14d; length
0x18004b1f8  mov     [rbp+bufferHandle], r13
0x18004b1fc  lea     rdx, [rbp+charBuffer]; charBuffer
0x18004b200  call    cs:__imp_WindowsPreallocateStringBuffer
0x18004b207  nop     dword ptr [rax+rax+00h]
0x18004b20c  mov     edi, eax
0x18004b20e  test    eax, eax
0x18004b210  jns     short loc_18004B26A
0x18004b212  mov     edx, 0C90h; void *
0x18004b217  mov     rcx, [rbp+40h]; this
0x18004b21b  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18004b222  mov     r9d, edi; char *
0x18004b225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b22a  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18004b22e  test    rcx, rcx
0x18004b231  jz      short loc_18004B23F
0x18004b233  call    cs:__imp_WindowsDeleteStringBuffer
0x18004b23a  nop     dword ptr [rax+rax+00h]
0x18004b23f  test    rbx, rbx
0x18004b242  jz      short loc_18004B256
0x18004b244  mov     rax, [rbx]
0x18004b247  mov     rax, [rax+68h]
0x18004b24b  mov     edx, [rbp+var_28]
0x18004b24e  mov     rcx, rbx
0x18004b251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b256  mov     eax, edi
0x18004b258  add     rsp, 58h
0x18004b25c  pop     r15
0x18004b25e  pop     r14
0x18004b260  pop     r13
0x18004b262  pop     r12
0x18004b264  pop     rdi
0x18004b265  pop     rsi
0x18004b266  pop     rbx
0x18004b267  pop     rbp
0x18004b268  retn
0x18004b26a  mov     ecx, 22h ; '"'
0x18004b26f  cmp     [rsi], cx
0x18004b272  jz      loc_18004B41B
0x18004b278  mov     r9, [rbp+charBuffer]
0x18004b27c  inc     r14d
0x18004b27f  lea     r8, [rbp+var_24]
0x18004b283  mov     edx, 2
0x18004b288  mov     [rbp+var_24], r14d
0x18004b28c  mov     rcx, r15
0x18004b28f  call    cs:__imp_GetStagedPackagePathByFullName2
0x18004b296  nop     dword ptr [rax+rax+00h]
0x18004b29b  test    eax, eax
0x18004b29d  jnz     loc_18004B37D
0x18004b2a3  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x18004b2a7  lea     r8, asc_180123420; "\\"
0x18004b2ae  mov     edx, r14d; unsigned __int64
0x18004b2b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b2b6  mov     edi, eax
0x18004b2b8  test    eax, eax
0x18004b2ba  js      loc_18004B373
0x18004b2c0  mov     rcx, [rbp+charBuffer]; unsigned __int16 *
0x18004b2c4  mov     r8, rsi; unsigned __int16 *
0x18004b2c7  mov     edx, r14d; unsigned __int64
0x18004b2ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004b2cf  mov     edi, eax
0x18004b2d1  test    eax, eax
0x18004b2d3  js      loc_18004B3F6
0x18004b2d9  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18004b2dd  mov     rdx, r12; string
0x18004b2e0  call    cs:__imp_WindowsPromoteStringBuffer
0x18004b2e7  nop     dword ptr [rax+rax+00h]
0x18004b2ec  mov     edi, eax
0x18004b2ee  test    eax, eax
0x18004b2f0  jns     short loc_18004B351
0x18004b2f2  mov     rcx, [rbp+40h]; this
0x18004b2f6  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18004b2fd  mov     r9d, eax; char *
0x18004b300  mov     edx, 0CA5h; void *
0x18004b305  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b30a  lea     rcx, [rbp+bufferHandle]
0x18004b30e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING_BUFFER__@@P6AJPEAU1@@Z$1?WindowsDeleteStringBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING_BUFFER__ *,long (*)(HSTRING_BUFFER__ *),&WindowsDeleteStringBuffer(HSTRING_BUFFER__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING_BUFFER__ *,HSTRING_BUFFER__ *,0,std::nullptr_t>>(void)
0x18004b313  jmp     loc_18004B23F
0x18004b318  mov     rax, [rcx]
0x18004b31b  lea     r8, [rbp+var_28]
0x18004b31f  xor     edx, edx
0x18004b321  mov     rax, [rax+60h]
0x18004b325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b32a  mov     edi, eax
0x18004b32c  test    eax, eax
0x18004b32e  jns     loc_18004B1B1
0x18004b334  mov     rcx, [rbp+40h]; this
0x18004b338  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18004b33f  mov     r9d, eax; char *
0x18004b342  mov     edx, 0C74h; void *
0x18004b347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b34c  jmp     loc_18004B256
0x18004b351  mov     [rbp+bufferHandle], r13
0x18004b355  test    rbx, rbx
0x18004b358  jz      short loc_18004B36C
0x18004b35a  mov     rax, [rbx]
0x18004b35d  mov     rcx, rbx
0x18004b360  mov     edx, [rbp+var_28]
0x18004b363  mov     rax, [rax+68h]
0x18004b367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b36c  xor     eax, eax
0x18004b36e  jmp     loc_18004B258
0x18004b373  mov     edx, 0CA2h
0x18004b378  jmp     loc_18004B217
0x18004b37d  mov     rcx, [rbp+40h]; this
0x18004b381  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18004b388  mov     r9d, eax; char *
0x18004b38b  mov     edx, 0CA0h; void *
0x18004b390  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b395  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18004b399  mov     edi, eax
0x18004b39b  test    rcx, rcx
0x18004b39e  jz      short loc_18004B3AC
0x18004b3a0  call    cs:__imp_WindowsDeleteStringBuffer
0x18004b3a7  nop     dword ptr [rax+rax+00h]
0x18004b3ac  test    rbx, rbx
0x18004b3af  jz      loc_18004B256
0x18004b3b5  mov     rcx, [rbx]
0x18004b3b8  mov     rax, [rcx+68h]
0x18004b3bc  jmp     loc_18004B24B
0x18004b3c1  test    eax, eax
0x18004b3c3  jz      loc_18004B1D8
0x18004b3c9  mov     rcx, [rbp+40h]; this
0x18004b3cd  lea     rdx, aPackagefullnam; "PackageFullName:%ws"
0x18004b3d4  mov     [rsp+58h+var_30], r15; char *
0x18004b3d9  lea     r8, aOnecoreComComb_75; "onecore\\com\\combase\\catalog\\service"...
0x18004b3e0  mov     qword ptr [rsp+58h+var_38], rdx; unsigned int
0x18004b3e5  mov     r9d, eax; char *
0x18004b3e8  mov     edx, 0C85h; void *
0x18004b3ed  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18004b3f2  mov     edi, eax
0x18004b3f4  jmp     short loc_18004B3AC
0x18004b3f6  mov     edx, 0CA3h
0x18004b3fb  jmp     loc_18004B217
0x18004b400  cmp     cs:?g_bInSCM@@3JA, r13d; long g_bInSCM
0x18004b407  jz      loc_18004B1A4
0x18004b40d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004b412  mov     [rbp+var_28], r13d
0x18004b416  jmp     loc_18004B1B1
0x18004b41b  mov     rax, [rbp+charBuffer]
0x18004b41f  mov     [rax], cx
0x18004b422  mov     r9, [rbp+charBuffer]
0x18004b426  add     r9, 2
0x18004b42a  dec     r14d
0x18004b42d  mov     [rbp+charBuffer], r9
0x18004b431  add     rsi, 2
0x18004b435  jmp     loc_18004B27C
```
