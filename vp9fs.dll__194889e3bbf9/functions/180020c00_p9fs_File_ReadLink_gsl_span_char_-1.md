# p9fs::File::ReadLink(gsl::span<char,-1>)

- ea: `0x180020c00`
- end: `0x180020f1e`
- name: `?ReadLink@File@p9fs@@UEAA?AV?$BasicExpected@IJ@util@@V?$span@D$0?0@gsl@@@Z`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting`

## callees

- `0x180004120`
- `0x180004c74`
- `0x18001c93c`
- `0x18001ca24`
- `0x18001d6d0`
- `0x18001db60`
- `0x180020520`
- `0x180020c00`
- `0x180023400`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020da9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ebb`
- `ntdll!NtQueryInformationFile` at `0x180020c9c`
- `ntdll!NtQueryInformationFile` at `0x180020c9c`
- `lxutil!LxUtilTranslateWidePathToLxPath` at `0x180020e7a`
- `lxutil!LxUtilTranslateWidePathToLxPath` at `0x180020e7a`
- `lxutil!LxUtilSymlinkRead` at `0x180020e0f`
- `lxutil!LxUtilSymlinkRead` at `0x180020e0f`
- `lxutil!LxUtilFsReadReparseLink` at `0x180020d40`
- `lxutil!LxUtilFsReadReparseLink` at `0x180020d40`

## string_xrefs

- `0x180020d00`: `onecore\vm\dv\storage\plan9\dll\windows\p9file.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::File::ReadLink(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v6; // ecx
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  gsl::details *v15; // rcx
  int v16; // edi
  void **v17; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h]
  void *v19; // [rsp+40h] [rbp-C0h] BYREF
  const char *v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  __int16 v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+90h] [rbp-70h]
  _OWORD v25[3]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int128 v27; // [rsp+D0h] [rbp-30h] BYREF
  void *Src[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v29[8]; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE FileHandle; // [rsp+F8h] [rbp-8h]
  __int64 FileInformation; // [rsp+100h] [rbp+0h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  void *retaddr; // [rsp+148h] [rbp+48h]

  p9fs::File::OpenHandle(a1, v29, 128);
  if ( !v29[0] )
  {
    v6 = (int)FileHandle;
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 4) = v6;
    return a2;
  }
  FileInformation = 0;
  IoStatusBlock = 0;
  v8 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v8 >= 0 )
  {
    if ( (FileInformation & 0x400) == 0 )
    {
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 4) = -5;
      goto LABEL_26;
    }
    v27 = 0;
    memset(v23, 0, sizeof(v23));
    v24 = 0;
    v17 = (void **)&v27;
    v19 = retaddr;
    v20 = "onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9file.cpp";
    v21 = 0;
    v22 = 1241;
    wil::scope_exit_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___(v23, &v19, &v17);
    v11 = LxUtilFsReadReparseLink(*(_QWORD *)(a1 + 72) + 32LL, FileHandle, *(_QWORD *)(a1 + 72), &v27);
    if ( v11 )
      goto LABEL_9;
    if ( !*((_QWORD *)&v27 + 1) )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, void ***, HANDLE, __int64, _DWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 72)
                                                                                               + 112LL)
                                                                                 + 16LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 72) + 112LL),
              &v17,
              FileHandle,
              129,
              0);
      util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,long>::operator=(
        v29,
        v12);
      if ( (_BYTE)v17 && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( !v29[0] )
      {
        v11 = (int)FileHandle;
        if ( (_DWORD)FileHandle != -95 )
        {
LABEL_9:
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 4) = v11;
LABEL_25:
          wil::details::lambda_call_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___::reset(v23);
          goto LABEL_26;
        }
        v13 = p9fs::File::OpenHandle(a1, &v17, 129);
        util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,long>::operator=(
          v29,
          v13);
        if ( (_BYTE)v17 && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( !v29[0] )
        {
          v11 = (int)FileHandle;
          goto LABEL_9;
        }
      }
      v11 = LxUtilSymlinkRead(FileHandle, &v27);
      if ( v11 )
        goto LABEL_9;
    }
    *(_OWORD *)Src = 0;
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    v17 = Src;
    v19 = retaddr;
    v20 = "onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9file.cpp";
    v21 = 0;
    v22 = 1288;
    wil::scope_exit_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___(v25, &v19, &v17);
    v14 = LxUtilTranslateWidePathToLxPath(&v27, Src);
    if ( v14 )
    {
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 4) = v14;
    }
    else
    {
      v16 = LOWORD(Src[0]);
      if ( !Src[1] && LOWORD(Src[0])
        || Src[1] > (char *)Src[1] + LOWORD(Src[0])
        || (v15 = (gsl::details *)a3[1], LOWORD(Src[0]))
        && (!v15 || !(gsl::details *)((char *)v15 + *a3) || *a3 < (__int64)LOWORD(Src[0])) )
      {
        gsl::details::terminate(v15);
      }
      memmove_0(v15, Src[1], LOWORD(Src[0]));
      *(_BYTE *)a2 = 1;
      *(_DWORD *)(a2 + 4) = v16;
    }
    wil::details::lambda_call_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___::reset(v25);
    goto LABEL_25;
  }
  v10 = p9fs::util::NtStatusToLinuxError((p9fs::util *)(unsigned int)v8, v9);
  *(_BYTE *)a2 = 0;
  *(_DWORD *)(a2 + 4) = v10;
LABEL_26:
  if ( v29[0] && (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(FileHandle);
  return a2;
}

```

## disassembly

```asm
0x180020c00  mov     [rsp-8+arg_10], rbx
0x180020c05  push    rbp
0x180020c06  push    rsi
0x180020c07  push    rdi
0x180020c08  push    r12
0x180020c0a  push    r14
0x180020c0c  lea     rbp, [rsp-20h]
0x180020c11  sub     rsp, 120h
0x180020c18  mov     rax, cs:__security_cookie
0x180020c1f  xor     rax, rsp
0x180020c22  mov     [rbp+40h+var_28], rax
0x180020c26  mov     rsi, r8
0x180020c29  mov     rbx, rdx
0x180020c2c  mov     rdi, rcx
0x180020c2f  mov     r8d, 80h
0x180020c35  lea     rdx, [rbp+40h+var_50]
0x180020c39  call    ?OpenHandle@File@p9fs@@AEBA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@K@Z; p9fs::File::OpenHandle(ulong)
0x180020c3e  nop
0x180020c3f  xor     r14d, r14d
0x180020c42  cmp     [rbp+40h+var_50], r14b
0x180020c46  jnz     short loc_180020C77
0x180020c48  mov     ecx, dword ptr [rbp+40h+FileHandle]
0x180020c4b  mov     [rbx], r14b
0x180020c4e  mov     [rbx+4], ecx
0x180020c51  mov     rax, rbx
0x180020c54  mov     rcx, [rbp+40h+var_28]
0x180020c58  xor     rcx, rsp; StackCookie
0x180020c5b  call    __security_check_cookie
0x180020c60  mov     rbx, [rsp+140h+arg_10]
0x180020c68  add     rsp, 120h
0x180020c6f  pop     r14
0x180020c71  pop     r12
0x180020c73  pop     rdi
0x180020c74  pop     rsi
0x180020c75  pop     rbp
0x180020c76  retn
0x180020c77  mov     [rbp+40h+FileInformation], r14
0x180020c7b  xorps   xmm0, xmm0
0x180020c7e  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x180020c82  mov     [rsp+140h+FileInformationClass], 23h ; '#'; FileInformationClass
0x180020c8a  mov     r9d, 8; Length
0x180020c90  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x180020c94  lea     rdx, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x180020c98  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x180020c9c  call    cs:__imp_NtQueryInformationFile
0x180020ca2  test    eax, eax
0x180020ca4  jns     short loc_180020CB8
0x180020ca6  mov     ecx, eax; this
0x180020ca8  call    ?NtStatusToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::NtStatusToLinuxError(long)
0x180020cad  mov     [rbx], r14b
0x180020cb0  mov     [rbx+4], eax
0x180020cb3  jmp     loc_180020E9F
0x180020cb8  test    dword ptr [rbp+40h+FileInformation], 400h
0x180020cbf  jnz     short loc_180020CD0
0x180020cc1  mov     [rbx], r14b
0x180020cc4  mov     dword ptr [rbx+4], 0FFFFFFFBh
0x180020ccb  jmp     loc_180020E9F
0x180020cd0  xorps   xmm0, xmm0
0x180020cd3  movups  [rbp+40h+var_70], xmm0
0x180020cd7  xorps   xmm1, xmm1
0x180020cda  xor     eax, eax
0x180020cdc  movups  [rsp+140h+var_E0], xmm1
0x180020ce1  movups  [rsp+140h+var_D0], xmm1
0x180020ce6  movups  [rbp+40h+var_C0], xmm1
0x180020cea  mov     [rbp+40h+var_B0], rax
0x180020cee  lea     rax, [rbp+40h+var_70]
0x180020cf2  mov     [rsp+140h+var_110], rax
0x180020cf7  mov     rax, [rbp+48h]
0x180020cfb  mov     [rsp+140h+var_100], rax
0x180020d00  lea     r12, aOnecoreVmDvSto; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180020d07  mov     [rsp+140h+var_F8], r12
0x180020d0c  mov     [rsp+140h+var_F0], r14
0x180020d11  mov     eax, 4D9h
0x180020d16  mov     [rsp+140h+var_E8], ax
0x180020d1b  lea     r8, [rsp+140h+var_110]
0x180020d20  lea     rdx, [rsp+140h+var_100]
0x180020d25  lea     rcx, [rsp+140h+var_E0]
0x180020d2a  call    wil__scope_exit_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___
0x180020d2f  nop
0x180020d30  mov     r8, [rdi+48h]
0x180020d34  lea     rcx, [r8+20h]
0x180020d38  lea     r9, [rbp+40h+var_70]
0x180020d3c  mov     rdx, [rbp+40h+FileHandle]
0x180020d40  call    cs:__imp_LxUtilFsReadReparseLink
0x180020d46  test    eax, eax
0x180020d48  jz      short loc_180020D55
0x180020d4a  mov     [rbx], r14b
0x180020d4d  mov     [rbx+4], eax
0x180020d50  jmp     loc_180020E94
0x180020d55  cmp     qword ptr [rbp+40h+var_70+8], r14
0x180020d59  jnz     loc_180020E1D
0x180020d5f  mov     rax, [rdi+48h]
0x180020d63  mov     rcx, [rax+70h]
0x180020d67  mov     rax, [rcx]
0x180020d6a  mov     [rsp+140h+FileInformationClass], r14d
0x180020d6f  mov     r9d, 81h
0x180020d75  mov     r8, [rbp+40h+FileHandle]
0x180020d79  lea     rdx, [rsp+140h+var_110]
0x180020d7e  mov     rax, [rax+10h]
0x180020d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d87  mov     rdx, rax
0x180020d8a  lea     rcx, [rbp+40h+var_50]
0x180020d8e  call    ??4?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@QEAAAEAV01@$$QEAV01@@Z; util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long>::operator=(util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long> &&)
0x180020d93  cmp     byte ptr [rsp+140h+var_110], r14b
0x180020d98  jz      short loc_180020DAF
0x180020d9a  mov     rcx, [rsp+140h+hObject]; hObject
0x180020d9f  lea     rax, [rcx-1]
0x180020da3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020da7  ja      short loc_180020DAF
0x180020da9  call    cs:__imp_CloseHandle
0x180020daf  cmp     [rbp+40h+var_50], r14b
0x180020db3  jnz     short loc_180020E07
0x180020db5  mov     rax, [rbp+40h+FileHandle]
0x180020db9  cmp     eax, 0FFFFFFA1h
0x180020dbc  jnz     short loc_180020D4A
0x180020dbe  mov     r8d, 81h
0x180020dc4  lea     rdx, [rsp+140h+var_110]
0x180020dc9  mov     rcx, rdi
0x180020dcc  call    ?OpenHandle@File@p9fs@@AEBA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@K@Z; p9fs::File::OpenHandle(ulong)
0x180020dd1  mov     rdx, rax
0x180020dd4  lea     rcx, [rbp+40h+var_50]
0x180020dd8  call    ??4?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@QEAAAEAV01@$$QEAV01@@Z; util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long>::operator=(util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long> &&)
0x180020ddd  cmp     byte ptr [rsp+140h+var_110], r14b
0x180020de2  jz      short loc_180020DF9
0x180020de4  mov     rcx, [rsp+140h+hObject]; hObject
0x180020de9  lea     rax, [rcx-1]
0x180020ded  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020df1  ja      short loc_180020DF9
0x180020df3  call    cs:__imp_CloseHandle
0x180020df9  cmp     [rbp+40h+var_50], r14b
0x180020dfd  jnz     short loc_180020E07
0x180020dff  mov     eax, dword ptr [rbp+40h+FileHandle]
0x180020e02  jmp     loc_180020D4A
0x180020e07  lea     rdx, [rbp+40h+var_70]
0x180020e0b  mov     rcx, [rbp+40h+FileHandle]
0x180020e0f  call    cs:__imp_LxUtilSymlinkRead
0x180020e15  test    eax, eax
0x180020e17  jnz     loc_180020D4A
0x180020e1d  xorps   xmm0, xmm0
0x180020e20  movups  xmmword ptr [rbp+40h+Src], xmm0
0x180020e24  xorps   xmm1, xmm1
0x180020e27  xor     eax, eax
0x180020e29  movups  [rbp+40h+var_A8], xmm1
0x180020e2d  movups  [rbp+40h+var_98], xmm1
0x180020e31  movups  [rbp+40h+var_88], xmm1
0x180020e35  mov     [rbp+40h+var_78], rax
0x180020e39  lea     rax, [rbp+40h+Src]
0x180020e3d  mov     [rsp+140h+var_110], rax
0x180020e42  mov     rax, [rbp+48h]
0x180020e46  mov     [rsp+140h+var_100], rax
0x180020e4b  mov     [rsp+140h+var_F8], r12
0x180020e50  mov     [rsp+140h+var_F0], r14
0x180020e55  mov     eax, 508h
0x180020e5a  mov     [rsp+140h+var_E8], ax
0x180020e5f  lea     r8, [rsp+140h+var_110]
0x180020e64  lea     rdx, [rsp+140h+var_100]
0x180020e69  lea     rcx, [rbp+40h+var_A8]
0x180020e6d  call    wil__scope_exit_log__lambda_be17d0e74ac094b3699b55cc6cea1e80___
0x180020e72  lea     rdx, [rbp+40h+Src]
0x180020e76  lea     rcx, [rbp+40h+var_70]
0x180020e7a  call    cs:__imp_LxUtilTranslateWidePathToLxPath
0x180020e80  test    eax, eax
0x180020e82  jz      short loc_180020EC6
0x180020e84  mov     [rbx], r14b
0x180020e87  mov     [rbx+4], eax
0x180020e8a  lea     rcx, [rbp+40h+var_A8]
0x180020e8e  call    wil__details__lambda_call_log__lambda_be17d0e74ac094b3699b55cc6cea1e80_____reset
0x180020e93  nop
0x180020e94  lea     rcx, [rsp+140h+var_E0]
0x180020e99  call    wil__details__lambda_call_log__lambda_be17d0e74ac094b3699b55cc6cea1e80_____reset
0x180020e9e  nop
0x180020e9f  cmp     [rbp+40h+var_50], r14b
0x180020ea3  jz      loc_180020C51
0x180020ea9  mov     rcx, [rbp+40h+FileHandle]; hObject
0x180020ead  lea     rax, [rcx-1]
0x180020eb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020eb5  ja      loc_180020C51
0x180020ebb  call    cs:__imp_CloseHandle
0x180020ec1  jmp     loc_180020C51
0x180020ec6  movzx   edi, word ptr [rbp+40h+Src]
0x180020eca  mov     rdx, [rbp+40h+Src+8]; Src
0x180020ece  test    rdx, rdx
0x180020ed1  jnz     short loc_180020ED8
0x180020ed3  test    rdi, rdi
0x180020ed6  jnz     short loc_180020F18
0x180020ed8  lea     rax, [rdx+rdi]
0x180020edc  cmp     rdx, rax
0x180020edf  ja      short loc_180020F18
0x180020ee1  mov     rcx, [rsi+8]; void *
0x180020ee5  test    rdi, rdi
0x180020ee8  jz      short loc_180020F05
0x180020eea  test    rcx, rcx
0x180020eed  jz      short loc_180020F18
0x180020eef  mov     r8, [rsi]
0x180020ef2  lea     rax, [r8+rcx]
0x180020ef6  test    rax, rax
0x180020ef9  jz      short loc_180020F18
0x180020efb  test    rdi, rdi
0x180020efe  jz      short loc_180020F05
0x180020f00  cmp     r8, rdi
0x180020f03  jl      short loc_180020F18
0x180020f05  mov     r8, rdi; Size
0x180020f08  call    memmove_0
0x180020f0d  mov     byte ptr [rbx], 1
0x180020f10  mov     [rbx+4], edi
0x180020f13  jmp     loc_180020E8A
0x180020f18  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
