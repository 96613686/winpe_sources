# CSafeSaveHandleManager::RuntimeClassInitialize(ushort const *,Windows::Storage::FileAccessMode,SAFE_SAVE_OPTIONS,Windows::Storage::StorageOpenOptions,Windows::Foundation::IClosable *,void *)

- ea: `0x180012ba4`
- end: `0x180012e61`
- name: `?RuntimeClassInitialize@CSafeSaveHandleManager@@QEAAJPEBGW4FileAccessMode@Storage@Windows@@W4SAFE_SAVE_OPTIONS@@W4StorageOpenOptions@34@PEAUIClosable@Foundation@4@PEAX@Z`
- size: `701`
- prototype: `int __high(const unsigned __int16 *, enum Windows::Storage::FileAccessMode, enum SAFE_SAVE_OPTIONS, enum Windows::Storage::StorageOpenOptions, struct Windows::Foundation::IClosable *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800120d4`

## callees

- `0x18000ddd4`
- `0x180011e24`
- `0x180012ba4`
- `0x180012e68`
- `0x180012eb4`
- `0x180012ef8`
- `0x180053bd8`
- `0x180067256`
- `0x1800672e8`
- `0x18006d8a8`
- `0x18009341c`
- `0x180095010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012e4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180012e4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012dd8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012dd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012c1a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012c3e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012c3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012c7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012d01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012c7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012d01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d4f`

## string_xrefs

- `0x180012e2f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSafeSaveHandleManager::RuntimeClassInitialize(
        __int64 a1,
        char *a2,
        int a3,
        const char *a4,
        int a5,
        HLOCAL hMem,
        HANDLE hSourceHandle)
{
  char v7; // di
  HLOCAL v10; // rbx
  HANDLE v11; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE v13; // rax
  __int64 v14; // r14
  __int64 v15; // rcx
  char *v16; // rax
  size_t v17; // rdi
  size_t v18; // r15
  char *v19; // rax
  char *v20; // rbx
  int *v21; // rax
  rsize_t v22; // rdi
  char *v23; // rax
  char *v24; // rbx
  __int64 v26; // rdx
  HANDLE CurrentThread; // rax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-68h]
  char v29; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = (char)a4;
  *(_DWORD *)(a1 + 232) = a3;
  *(_DWORD *)(a1 + 272) = (_DWORD)a4;
  *(_DWORD *)(a1 + 276) = a5;
  v10 = hMem;
  if ( *(HLOCAL *)(a1 + 264) != hMem )
  {
    if ( hMem )
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 8LL))(hMem);
    hMem = *(HLOCAL *)(a1 + 264);
    *(_QWORD *)(a1 + 264) = v10;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&hMem);
  }
  v11 = hSourceHandle;
  if ( hSourceHandle )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 256,
      0);
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    DuplicateHandle(v13, v11, CurrentProcess, (LPHANDLE)(a1 + 256), 0, 0, 2u);
  }
  else if ( (v7 & 0x20) != 0 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 256,
      0);
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 0xEu, 1, (PHANDLE)(a1 + 256));
  }
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v14 = 0x7FFFFFFF;
  v15 = 0x7FFFFFFF;
  v16 = a2;
  do
  {
    if ( !*(_WORD *)v16 )
      break;
    v16 += 2;
    --v15;
  }
  while ( v15 );
  v17 = 2 * ((v16 - a2) >> 1);
  v18 = v17 + 2;
  v19 = (char *)LocalAlloc(0, v17 + 2);
  v20 = v19;
  if ( v19 )
  {
    if ( v17 )
    {
      if ( v18 < v17 )
      {
        memset_0(v19, 0, v18);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v19, a2, v17);
      }
    }
    *(_WORD *)&v20[v17] = 0;
  }
  if ( (char *)(a1 + 216) == &v29 )
  {
    if ( v20 )
      LocalFree(v20);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 216,
      v20);
  }
  if ( *(_QWORD *)(a1 + 216) )
  {
    v21 = &dword_1800ABC6C;
    do
    {
      if ( !*(_WORD *)v21 )
        break;
      v21 = (int *)((char *)v21 + 2);
      --v14;
    }
    while ( v14 );
    v22 = 2 * (((char *)v21 - (char *)&dword_1800ABC6C) >> 1);
    v23 = (char *)LocalAlloc(0, v22 + 2);
    v24 = v23;
    if ( v23 )
    {
      memcpy_s_0(v23, v22 + 2, &dword_1800ABC6C, v22);
      *(_WORD *)&v24[v22] = 0;
    }
    hMem = v24;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1 + 224,
      &hMem);
    if ( hMem )
      LocalFree(hMem);
    if ( *(_QWORD *)(a1 + 224) )
      return 0;
    v26 = 589;
  }
  else
  {
    v26 = 586;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v26,
    (unsigned int)"onecore\\shell\\shcore\\libs\\stream\\safesavehandlemanager.cpp",
    (const char *)0x8007000ELL,
    dwDesiredAccess);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012ba4  push    rbx
0x180012ba6  push    rbp
0x180012ba7  push    rsi
0x180012ba8  push    rdi
0x180012ba9  push    r12
0x180012bab  push    r14
0x180012bad  push    r15
0x180012baf  sub     rsp, 50h
0x180012bb3  mov     edi, r9d
0x180012bb6  mov     rbp, rdx
0x180012bb9  mov     rsi, rcx
0x180012bbc  mov     [rcx+0E8h], r8d
0x180012bc3  mov     [rcx+110h], r9d
0x180012bca  mov     eax, [rsp+88h+arg_20]
0x180012bd1  mov     [rcx+114h], eax
0x180012bd7  xor     r12d, r12d
0x180012bda  mov     rbx, [rsp+88h+hMem]
0x180012be2  cmp     [rcx+108h], rbx
0x180012be9  jnz     loc_180012DEA
0x180012bef  mov     r14, [rsp+88h+hSourceHandle]
0x180012bf7  test    r14, r14
0x180012bfa  jz      loc_180012DA8
0x180012c00  lea     rdi, [rsi+100h]
0x180012c07  xor     edx, edx
0x180012c09  mov     rcx, rdi
0x180012c0c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012c11  call    cs:__imp_GetCurrentProcess
0x180012c17  mov     rbx, rax
0x180012c1a  call    cs:__imp_GetCurrentProcess
0x180012c20  mov     [rsp+88h+dwOptions], 2; dwOptions
0x180012c28  mov     [rsp+88h+bInheritHandle], r12d; bInheritHandle
0x180012c2d  mov     [rsp+88h+dwDesiredAccess], r12d; int
0x180012c32  mov     r9, rdi; lpTargetHandle
0x180012c35  mov     r8, rbx; hTargetProcessHandle
0x180012c38  mov     rdx, r14; hSourceHandle
0x180012c3b  mov     rcx, rax; hSourceProcessHandle
0x180012c3e  call    cs:__imp_DuplicateHandle
0x180012c44  test    rbp, rbp
0x180012c47  jz      loc_180012E27
0x180012c4d  mov     r14d, 7FFFFFFFh
0x180012c53  mov     ecx, r14d
0x180012c56  mov     rax, rbp
0x180012c59  cmp     [rax], r12w
0x180012c5d  jz      short loc_180012C69
0x180012c5f  add     rax, 2
0x180012c63  sub     rcx, 1
0x180012c67  jnz     short loc_180012C59
0x180012c69  sub     rax, rbp
0x180012c6c  sar     rax, 1
0x180012c6f  lea     rdi, [rax+rax]
0x180012c73  lea     r15, [rdi+2]
0x180012c77  mov     rdx, r15; uBytes
0x180012c7a  xor     ecx, ecx; uFlags
0x180012c7c  call    cs:__imp_LocalAlloc
0x180012c82  mov     rbx, rax
0x180012c85  test    rax, rax
0x180012c88  jz      short loc_180012CAB
0x180012c8a  test    rdi, rdi
0x180012c8d  jz      short loc_180012CA6
0x180012c8f  mov     rcx, rax; void *
0x180012c92  cmp     r15, rdi
0x180012c95  jb      loc_180012E41
0x180012c9b  mov     r8, rdi; Size
0x180012c9e  mov     rdx, rbp; Src
0x180012ca1  call    memcpy_0
0x180012ca6  mov     [rdi+rbx], r12w
0x180012cab  lea     rdi, [rsi+0D8h]
0x180012cb2  lea     rax, [rsp+88h+var_48]
0x180012cb7  cmp     rdi, rax
0x180012cba  jnz     loc_180012D98
0x180012cc0  test    rbx, rbx
0x180012cc3  jz      short loc_180012CCE
0x180012cc5  mov     rcx, rbx; hMem
0x180012cc8  call    cs:__imp_LocalFree
0x180012cce  cmp     [rdi], r12
0x180012cd1  jz      loc_180012D66
0x180012cd7  lea     r15, dword_1800ABC6C
0x180012cde  mov     rax, r15
0x180012ce1  cmp     [rax], r12w
0x180012ce5  jz      short loc_180012CF1
0x180012ce7  add     rax, 2
0x180012ceb  sub     r14, 1
0x180012cef  jnz     short loc_180012CE1
0x180012cf1  sub     rax, r15
0x180012cf4  sar     rax, 1
0x180012cf7  lea     rdi, [rax+rax]
0x180012cfb  lea     rdx, [rdi+2]; uBytes
0x180012cff  xor     ecx, ecx; uFlags
0x180012d01  call    cs:__imp_LocalAlloc
0x180012d07  mov     rbx, rax
0x180012d0a  test    rax, rax
0x180012d0d  jz      short loc_180012D26
0x180012d0f  mov     r9, rdi; SourceSize
0x180012d12  mov     r8, r15; Source
0x180012d15  lea     rdx, [rdi+2]; DestinationSize
0x180012d19  mov     rcx, rax; Destination
0x180012d1c  call    memcpy_s_0
0x180012d21  mov     [rdi+rbx], r12w
0x180012d26  mov     [rsp+88h+hMem], rbx
0x180012d2e  lea     rdx, [rsp+88h+hMem]
0x180012d36  lea     rcx, [rsi+0E0h]
0x180012d3d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180012d42  mov     rcx, [rsp+88h+hMem]; hMem
0x180012d4a  test    rcx, rcx
0x180012d4d  jz      short loc_180012D55
0x180012d4f  call    cs:__imp_LocalFree
0x180012d55  cmp     [rsi+0E0h], r12
0x180012d5c  jz      loc_180012DE3
0x180012d62  xor     eax, eax
0x180012d64  jmp     short loc_180012D89
0x180012d66  mov     edx, 24Ah; void *
0x180012d6b  mov     ebx, 8007000Eh
0x180012d70  mov     r9d, ebx; char *
0x180012d73  lea     r8, aOnecoreShellSh_9; "onecore\\shell\\shcore\\libs\\stream\\s"...
0x180012d7a  mov     rcx, [rsp+88h]; this
0x180012d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d87  mov     eax, ebx
0x180012d89  add     rsp, 50h
0x180012d8d  pop     r15
0x180012d8f  pop     r14
0x180012d91  pop     r12
0x180012d93  pop     rdi
0x180012d94  pop     rsi
0x180012d95  pop     rbp
0x180012d96  pop     rbx
0x180012d97  retn
0x180012d98  mov     rdx, rbx
0x180012d9b  mov     rcx, rdi
0x180012d9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180012da3  jmp     loc_180012CCE
0x180012da8  test    dil, 20h
0x180012dac  jz      loc_180012C44
0x180012db2  lea     rbx, [rsi+100h]
0x180012db9  xor     edx, edx
0x180012dbb  mov     rcx, rbx
0x180012dbe  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012dc3  call    cs:__imp_GetCurrentThread
0x180012dc9  mov     r9, rbx; TokenHandle
0x180012dcc  mov     edx, 0Eh; DesiredAccess
0x180012dd1  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180012dd5  mov     rcx, rax; ThreadHandle
0x180012dd8  call    cs:__imp_OpenThreadToken
0x180012dde  jmp     loc_180012C44
0x180012de3  mov     edx, 24Dh
0x180012de8  jmp     short loc_180012D6B
0x180012dea  test    rbx, rbx
0x180012ded  jz      short loc_180012DFF
0x180012def  mov     rax, [rbx]
0x180012df2  mov     rcx, rbx
0x180012df5  mov     rax, [rax+8]
0x180012df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dfe  nop
0x180012dff  mov     rax, [rsi+108h]
0x180012e06  mov     [rsp+88h+hMem], rax
0x180012e0e  mov     [rsi+108h], rbx
0x180012e15  lea     rcx, [rsp+88h+hMem]
0x180012e1d  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x180012e22  jmp     loc_180012BEF
0x180012e27  mov     rcx, [rsp+88h]; this
0x180012e2f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012e36  mov     edx, 0F89h; void *
0x180012e3b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180012e41  mov     r8, r15; Size
0x180012e44  xor     edx, edx; Val
0x180012e46  call    memset_0
0x180012e4b  call    cs:__imp__o__errno
0x180012e51  mov     dword ptr [rax], 22h ; '"'
0x180012e57  call    _invalid_parameter_noinfo
0x180012e5c  jmp     loc_180012CA6
```
