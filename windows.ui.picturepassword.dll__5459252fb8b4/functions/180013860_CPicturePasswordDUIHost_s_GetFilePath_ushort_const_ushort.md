# CPicturePasswordDUIHost::s_GetFilePath(ushort const *,ushort * *)

- ea: `0x180013860`
- end: `0x18001396c`
- name: `?s_GetFilePath@CPicturePasswordDUIHost@@KAJPEBGPEAPEAG@Z`
- size: `268`
- prototype: `__int64 __fastcall(PCWSTR pszMore, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x180011534`
- `0x180011e88`
- `0x180013b88`
- `0x180013cc0`

## callees

- `0x180002610`
- `0x1800056a0`
- `0x180011b00`
- `0x180013860`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800138f2`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800138f2`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001390b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001390b`
- `SHELL32!SHGetKnownFolderPath` at `0x1800138d0`
- `SHELL32!SHGetKnownFolderPath` at `0x1800138d0`

## pseudocode

```c
__int64 __fastcall CPicturePasswordDUIHost::s_GetFilePath(PCWSTR pszMore, unsigned __int16 **a2)
{
  __int64 v3; // rdi
  HRESULT v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v9; // [rsp+38h] [rbp-C8h]
  __int64 v10; // [rsp+40h] [rbp-C0h]
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a2 = 0;
  ppszPath = 0;
  v9 = 0;
  v10 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&ppszPath);
  v3 = -1;
  v9 = -1;
  v10 = -1;
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v4 >= 0 )
  {
    v4 = PathCchCombine(pszPathOut, 0x104u, ppszPath, L"Microsoft\\Windows\\PicturePassword");
    if ( v4 >= 0 )
    {
      v4 = PathCchAppend(pszPathOut, 0x104u, pszMore);
      if ( v4 >= 0 )
      {
        do
          ++v3;
        while ( pszPathOut[v3] );
        v4 = _AllocStringWorker<CTCoAllocPolicy>(v6, v5, pszPathOut);
      }
    }
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&ppszPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013860  mov     [rsp-8+arg_10], rbx
0x180013865  push    rbp
0x180013866  push    rsi
0x180013867  push    rdi
0x180013868  push    r14
0x18001386a  push    r15
0x18001386c  lea     rbp, [rsp-170h]
0x180013874  sub     rsp, 270h
0x18001387b  mov     rax, cs:__security_cookie
0x180013882  xor     rax, rsp
0x180013885  mov     [rbp+190h+var_30], rax
0x18001388c  xor     r15d, r15d
0x18001388f  mov     r14, rcx
0x180013892  lea     rcx, [rsp+290h+ppszPath]
0x180013897  mov     [rdx], r15
0x18001389a  mov     [rsp+290h+ppszPath], r15
0x18001389f  mov     rsi, rdx
0x1800138a2  mov     [rsp+290h+var_258], r15
0x1800138a7  mov     [rsp+290h+var_250], r15
0x1800138ac  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800138b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800138b5  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x1800138ba  xor     r8d, r8d; hToken
0x1800138bd  mov     [rsp+290h+var_258], rdi
0x1800138c2  xor     edx, edx; dwFlags
0x1800138c4  mov     [rsp+290h+var_250], rdi
0x1800138c9  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800138d0  call    cs:__imp_SHGetKnownFolderPath
0x1800138d6  mov     ebx, eax
0x1800138d8  test    eax, eax
0x1800138da  js      short loc_18001393A
0x1800138dc  mov     r8, [rsp+290h+ppszPath]; pszPathIn
0x1800138e1  lea     r9, aMicrosoftWindo_1; "Microsoft\\Windows\\PicturePassword"
0x1800138e8  mov     edx, 104h; cchPathOut
0x1800138ed  lea     rcx, [rsp+290h+pszPathOut]; pszPathOut
0x1800138f2  call    cs:__imp_PathCchCombine
0x1800138f8  mov     ebx, eax
0x1800138fa  test    eax, eax
0x1800138fc  js      short loc_18001393A
0x1800138fe  mov     r8, r14; pszMore
0x180013901  lea     rcx, [rsp+290h+pszPathOut]; pszPath
0x180013906  mov     edx, 104h; cchPath
0x18001390b  call    cs:__imp_PathCchAppend
0x180013911  mov     ebx, eax
0x180013913  test    eax, eax
0x180013915  js      short loc_18001393A
0x180013917  lea     rax, [rsp+290h+pszPathOut]
0x18001391c  inc     rdi
0x18001391f  cmp     [rax+rdi*2], r15w
0x180013924  jnz     short loc_18001391C
0x180013926  mov     r9, rdi
0x180013929  mov     [rsp+290h+var_268], rsi
0x18001392e  lea     r8, [rsp+290h+pszPathOut]
0x180013933  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180013938  mov     ebx, eax
0x18001393a  lea     rcx, [rsp+290h+ppszPath]
0x18001393f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180013944  mov     eax, ebx
0x180013946  mov     rcx, [rbp+190h+var_30]
0x18001394d  xor     rcx, rsp; StackCookie
0x180013950  call    __security_check_cookie
0x180013955  mov     rbx, [rsp+290h+arg_10]
0x18001395d  add     rsp, 270h
0x180013964  pop     r15
0x180013966  pop     r14
0x180013968  pop     rdi
0x180013969  pop     rsi
0x18001396a  pop     rbp
0x18001396b  retn
```
