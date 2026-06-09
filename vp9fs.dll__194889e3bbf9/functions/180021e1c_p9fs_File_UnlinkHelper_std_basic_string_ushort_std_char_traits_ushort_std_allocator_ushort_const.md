# p9fs::File::UnlinkHelper(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180021e1c`
- end: `0x180021fd3`
- name: `?UnlinkHelper@File@p9fs@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180020f30`
- `0x1800212b8`
- `0x180021d80`

## callees

- `0x180004120`
- `0x18001ca24`
- `0x18001db60`
- `0x180021e1c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021fac`
- `lxutil!LxUtilFsDeleteReadOnlyFile` at `0x180021f8d`
- `lxutil!LxUtilFsDeleteReadOnlyFile` at `0x180021f8d`
- `lxutil!LxUtilFsDeleteFileCore` at `0x180021eb7`
- `lxutil!LxUtilFsDeleteFileCore` at `0x180021eb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::File::UnlinkHelper(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rcx
  int v6; // eax
  int v7; // edx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // [rsp+60h] [rbp-9h] BYREF
  __int64 v15; // [rsp+68h] [rbp-1h]
  __int64 v16; // [rsp+70h] [rbp+7h] BYREF
  __int64 v17; // [rsp+78h] [rbp+Fh]
  _BYTE v18[8]; // [rsp+80h] [rbp+17h] BYREF
  HANDLE v19; // [rsp+88h] [rbp+1Fh]
  _BYTE v20[8]; // [rsp+90h] [rbp+27h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+2Fh]

  v4 = *(_QWORD *)(a1 + 72);
  v5 = *(_QWORD *)(v4 + 112);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  (*(void (__fastcall **)(__int64, _BYTE *, _QWORD, __int64, int, int, _DWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v5 + 8LL))(
    v5,
    v20,
    *(_QWORD *)(v4 + 24),
    a2,
    0x10000,
    1,
    0,
    &v16,
    &v14,
    0);
  if ( !v20[0] )
    return (unsigned int)hObject;
  v6 = LxUtilFsDeleteFileCore(*(_QWORD *)(a1 + 72) + 32LL, hObject);
  if ( v6 < 0 )
  {
    if ( v6 != -1073741535 )
    {
      v8 = p9fs::util::NtStatusToLinuxError((p9fs::util *)(unsigned int)v6, v7);
LABEL_5:
      v9 = v8;
      if ( v20[0] )
      {
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
      return v9;
    }
    v11 = *(_QWORD *)(a1 + 72);
    v12 = *(_QWORD *)(v11 + 112);
    v16 = 0;
    v17 = 0;
    v14 = 0;
    v15 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, __int64, int, int, _DWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v12 + 8LL))(
            v12,
            v18,
            *(_QWORD *)(v11 + 24),
            a2,
            65920,
            1,
            0,
            &v14,
            &v16,
            0);
    util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,long>::operator=(
      v20,
      v13);
    if ( v18[0] && (char *)v19 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v19);
    if ( v20[0] )
    {
      v8 = LxUtilFsDeleteReadOnlyFile(*(_QWORD *)(a1 + 72) + 32LL, hObject);
      goto LABEL_5;
    }
    return (unsigned int)hObject;
  }
  if ( v20[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180021e1c  mov     [rsp-8+arg_10], rbx
0x180021e21  push    rbp
0x180021e22  push    rsi
0x180021e23  push    rdi
0x180021e24  lea     rbp, [rsp-47h]
0x180021e29  sub     rsp, 0B0h
0x180021e30  mov     rax, cs:__security_cookie
0x180021e37  xor     rax, rsp
0x180021e3a  mov     [rbp+57h+var_20], rax
0x180021e3e  mov     rdi, rdx
0x180021e41  mov     rbx, rcx
0x180021e44  mov     r8, [rcx+48h]
0x180021e48  mov     rcx, [r8+70h]
0x180021e4c  xor     esi, esi
0x180021e4e  mov     [rbp+57h+var_60], rsi
0x180021e52  mov     [rbp+57h+var_58], rsi
0x180021e56  mov     [rbp+57h+var_50], rsi
0x180021e5a  mov     [rbp+57h+var_48], rsi
0x180021e5e  mov     rax, [rcx]
0x180021e61  mov     [rsp+0C0h+var_78], rsi
0x180021e66  lea     rdx, [rbp+57h+var_60]
0x180021e6a  mov     [rsp+0C0h+var_80], rdx
0x180021e6f  lea     rdx, [rbp+57h+var_50]
0x180021e73  mov     [rsp+0C0h+var_88], rdx
0x180021e78  mov     [rsp+0C0h+var_90], esi
0x180021e7c  mov     [rsp+0C0h+var_98], 1
0x180021e84  mov     [rsp+0C0h+var_A0], 10000h
0x180021e8c  mov     r9, rdi
0x180021e8f  mov     r8, [r8+18h]
0x180021e93  lea     rdx, [rbp+57h+var_30]
0x180021e97  mov     rax, [rax+8]
0x180021e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ea0  nop
0x180021ea1  cmp     [rbp+57h+var_30], sil
0x180021ea5  jz      loc_180021F7C
0x180021eab  mov     rcx, [rbx+48h]
0x180021eaf  add     rcx, 20h ; ' '
0x180021eb3  mov     rdx, [rbp+57h+hObject]
0x180021eb7  call    cs:__imp_LxUtilFsDeleteFileCore
0x180021ebd  test    eax, eax
0x180021ebf  jns     loc_180021F98
0x180021ec5  cmp     eax, 0C0000121h
0x180021eca  jz      short loc_180021EF6
0x180021ecc  mov     ecx, eax; this
0x180021ece  call    ?NtStatusToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::NtStatusToLinuxError(long)
0x180021ed3  mov     ebx, eax
0x180021ed5  cmp     [rbp+57h+var_30], sil
0x180021ed9  jz      short loc_180021EEF
0x180021edb  mov     rcx, [rbp+57h+hObject]; hObject
0x180021edf  lea     rdx, [rcx-1]
0x180021ee3  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180021ee7  ja      short loc_180021EEF
0x180021ee9  call    cs:__imp_CloseHandle
0x180021eef  mov     eax, ebx
0x180021ef1  jmp     loc_180021FB4
0x180021ef6  mov     r8, [rbx+48h]
0x180021efa  mov     rcx, [r8+70h]
0x180021efe  mov     [rbp+57h+var_50], rsi
0x180021f02  mov     [rbp+57h+var_48], rsi
0x180021f06  mov     [rbp+57h+var_60], rsi
0x180021f0a  mov     [rbp+57h+var_58], rsi
0x180021f0e  mov     rax, [rcx]
0x180021f11  mov     [rsp+0C0h+var_78], rsi
0x180021f16  lea     rdx, [rbp+57h+var_50]
0x180021f1a  mov     [rsp+0C0h+var_80], rdx
0x180021f1f  lea     rdx, [rbp+57h+var_60]
0x180021f23  mov     [rsp+0C0h+var_88], rdx
0x180021f28  mov     [rsp+0C0h+var_90], esi
0x180021f2c  mov     [rsp+0C0h+var_98], 1
0x180021f34  mov     [rsp+0C0h+var_A0], 10180h
0x180021f3c  mov     r9, rdi
0x180021f3f  mov     r8, [r8+18h]
0x180021f43  lea     rdx, [rbp+57h+var_40]
0x180021f47  mov     rax, [rax+8]
0x180021f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f50  mov     rdx, rax
0x180021f53  lea     rcx, [rbp+57h+var_30]
0x180021f57  call    ??4?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@QEAAAEAV01@$$QEAV01@@Z; util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long>::operator=(util::BasicExpected<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,long> &&)
0x180021f5c  cmp     [rbp+57h+var_40], sil
0x180021f60  jz      short loc_180021F76
0x180021f62  mov     rcx, [rbp+57h+var_38]; hObject
0x180021f66  lea     rax, [rcx-1]
0x180021f6a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021f6e  ja      short loc_180021F76
0x180021f70  call    cs:__imp_CloseHandle
0x180021f76  cmp     [rbp+57h+var_30], sil
0x180021f7a  jnz     short loc_180021F81
0x180021f7c  mov     eax, dword ptr [rbp+57h+hObject]
0x180021f7f  jmp     short loc_180021FB4
0x180021f81  mov     rcx, [rbx+48h]
0x180021f85  add     rcx, 20h ; ' '
0x180021f89  mov     rdx, [rbp+57h+hObject]
0x180021f8d  call    cs:__imp_LxUtilFsDeleteReadOnlyFile
0x180021f93  jmp     loc_180021ED3
0x180021f98  cmp     [rbp+57h+var_30], sil
0x180021f9c  jz      short loc_180021FB2
0x180021f9e  mov     rcx, [rbp+57h+hObject]; hObject
0x180021fa2  lea     rax, [rcx-1]
0x180021fa6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021faa  ja      short loc_180021FB2
0x180021fac  call    cs:__imp_CloseHandle
0x180021fb2  xor     eax, eax
0x180021fb4  mov     rcx, [rbp+57h+var_20]
0x180021fb8  xor     rcx, rsp; StackCookie
0x180021fbb  call    __security_check_cookie
0x180021fc0  mov     rbx, [rsp+0C0h+arg_10]
0x180021fc8  add     rsp, 0B0h
0x180021fcf  pop     rdi
0x180021fd0  pop     rsi
0x180021fd1  pop     rbp
0x180021fd2  retn
```
