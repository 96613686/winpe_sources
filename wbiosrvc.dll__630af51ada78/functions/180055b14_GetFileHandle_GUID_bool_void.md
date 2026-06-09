# GetFileHandle(_GUID,bool,void * *)

- ea: `0x180055b14`
- end: `0x180055bf8`
- name: `?GetFileHandle@@YAJU_GUID@@_NPEAPEAX@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct _GUID *, __int64, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180054720`
- `0x1800760f0`

## callees

- `0x180014854`
- `0x180014894`
- `0x180014914`
- `0x1800549a0`
- `0x180055b14`
- `0x180068f60`
- `0x180075ed8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055b8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180055b8d`

## pseudocode

```c
__int64 __fastcall GetFileHandle(struct _GUID *a1, __int64 a2, void **a3)
{
  int v4; // ebx
  UUID *v5; // r9
  const WCHAR *v6; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  UUID Uuid1; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v12[32]; // [rsp+50h] [rbp-38h] BYREF

  v4 = (unsigned __int8)a2;
  std::wstring::wstring(v12, a2, a3, a1);
  Uuid1 = *v5;
  GetFilePath(&Uuid1, (__int64)v12);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  FileW = CreateFileW(v6, 0xC0000000, 0, 0, v4 + 2, 0x80u, 0);
  *(_QWORD *)&Uuid1.Data1 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    *(_QWORD *)&Uuid1.Data1 = 0;
    *a3 = FileW;
    v9 = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Uuid1);
  std::wstring::_Tidy_deallocate(v12);
  return v9;
}

```

## disassembly

```asm
0x180055b14  mov     [rsp+arg_8], rbx
0x180055b19  push    rdi
0x180055b1a  sub     rsp, 80h
0x180055b21  mov     rax, cs:__security_cookie
0x180055b28  xor     rax, rsp
0x180055b2b  mov     [rsp+88h+var_18], rax
0x180055b30  mov     rdi, r8
0x180055b33  movzx   ebx, dl
0x180055b36  mov     r9, rcx
0x180055b39  lea     rcx, [rsp+88h+var_38]
0x180055b3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180055b43  nop
0x180055b44  movaps  xmm1, xmmword ptr [r9]
0x180055b48  movdqa  xmmword ptr [rsp+88h+Uuid1.Data1], xmm1
0x180055b4e  lea     rdx, [rsp+88h+var_38]
0x180055b53  lea     rcx, [rsp+88h+Uuid1]; Uuid1
0x180055b58  call    ?GetFilePath@@YAJU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFilePath(_GUID,std::wstring *)
0x180055b5d  add     ebx, 2
0x180055b60  lea     rcx, [rsp+88h+var_38]
0x180055b65  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055b6a  mov     rcx, rax; lpFileName
0x180055b6d  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180055b76  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180055b7e  mov     [rsp+88h+dwCreationDisposition], ebx; dwCreationDisposition
0x180055b82  xor     r9d, r9d; lpSecurityAttributes
0x180055b85  xor     r8d, r8d; dwShareMode
0x180055b88  mov     edx, 0C0000000h; dwDesiredAccess
0x180055b8d  call    cs:__imp_CreateFileW
0x180055b93  mov     qword ptr [rsp+88h+Uuid1.Data1], rax
0x180055b98  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055b9c  jnz     short loc_180055BB5
0x180055b9e  call    cs:__imp_GetLastError
0x180055ba4  mov     ebx, eax
0x180055ba6  test    eax, eax
0x180055ba8  jle     short loc_180055BC3
0x180055baa  movzx   ebx, ax
0x180055bad  or      ebx, 80070000h
0x180055bb3  jmp     short loc_180055BC3
0x180055bb5  mov     qword ptr [rsp+88h+Uuid1.Data1], 0
0x180055bbe  mov     [rdi], rax
0x180055bc1  xor     ebx, ebx
0x180055bc3  lea     rcx, [rsp+88h+Uuid1]
0x180055bc8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180055bcd  nop
0x180055bce  lea     rcx, [rsp+88h+var_38]
0x180055bd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055bd8  mov     eax, ebx
0x180055bda  mov     rcx, [rsp+88h+var_18]
0x180055bdf  xor     rcx, rsp; StackCookie
0x180055be2  call    __security_check_cookie
0x180055be7  mov     rbx, [rsp+88h+arg_8]
0x180055bef  add     rsp, 80h
0x180055bf6  pop     rdi
0x180055bf7  retn
```
