# CPlugInManager::Initialize(void)

- ea: `0x18005d65c`
- end: `0x18005d79d`
- name: `?Initialize@CPlugInManager@@SAXXZ`
- size: `321`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001d378`

## callees

- `0x1800133ec`
- `0x18001451c`
- `0x180014894`
- `0x1800148b4`
- `0x180016b64`
- `0x18002d4e8`
- `0x18005d65c`
- `0x180060254`
- `0x180068f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18005d758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d694`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005d68a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18005d68a`

## string_xrefs

- `0x18005d6f3`: `WinBioPlugIns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void CPlugInManager::Initialize(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  __int64 v2; // r9
  struct CPlugInManager *v3; // rax
  struct CPlugInManager *v4; // rax
  struct CPlugInManager *v5; // rax
  struct CPlugInManager *v6; // rax
  int v7; // edi
  struct CPlugInManager *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rbx
  struct CPlugInManager *v12; // rax
  int v13; // eax
  CPlugInManager *v14; // rax
  char v15; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  CPlugInManager::Instance();
  if ( GetSystemDirectoryW(Buffer, 0x105u) )
  {
    CPlugInManager::Instance();
    std::_WChar_traits<unsigned short>::length(Buffer);
    std::wstring::_Assign<unsigned short>(v2, Buffer);
    v3 = CPlugInManager::Instance();
    std::wstring::append((char *)v3 + 64, L"\\");
    v4 = CPlugInManager::Instance();
    std::wstring::append((char *)v4 + 64, L"WinBioPlugIns");
    v5 = CPlugInManager::Instance();
    std::wstring::append((char *)v5 + 64, L"\\");
    v6 = CPlugInManager::Instance();
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v6 + 64);
    v8 = CPlugInManager::Instance();
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v8 + 64);
    v11 = v9 + 2LL * *(_QWORD *)(v10 + 16);
    v12 = CPlugInManager::Instance();
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v12 + 64);
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)&v15,
      v13,
      v11,
      v7,
      (__int64)towupper);
    v14 = CPlugInManager::Instance();
    CPlugInManager::RegisterAll(v14);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    *((_DWORD *)CPlugInManager::Instance() + 24) = v1;
  }
}

```

## disassembly

```asm
0x18005d65c  mov     [rsp+arg_0], rbx
0x18005d661  push    rdi
0x18005d662  sub     rsp, 260h
0x18005d669  mov     rax, cs:__security_cookie
0x18005d670  xor     rax, rsp
0x18005d673  mov     [rsp+268h+var_18], rax
0x18005d67b  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d680  mov     edx, 105h; uSize
0x18005d685  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18005d68a  call    cs:__imp_GetSystemDirectoryW
0x18005d690  test    eax, eax
0x18005d692  jnz     short loc_18005D6B6
0x18005d694  call    cs:__imp_GetLastError
0x18005d69a  mov     ebx, eax
0x18005d69c  test    eax, eax
0x18005d69e  jle     short loc_18005D6A9
0x18005d6a0  movzx   ebx, ax
0x18005d6a3  or      ebx, 80070000h
0x18005d6a9  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d6ae  mov     [rax+60h], ebx
0x18005d6b1  jmp     loc_18005D77C
0x18005d6b6  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d6bb  lea     rcx, [rsp+268h+Buffer]
0x18005d6c0  lea     r9, [rax+40h]
0x18005d6c4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18005d6c9  mov     r8, rax
0x18005d6cc  lea     rdx, [rsp+268h+Buffer]
0x18005d6d1  mov     rcx, r9
0x18005d6d4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d6d9  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d6de  lea     rdx, asc_1800DC1E4; "\\"
0x18005d6e5  lea     rcx, [rax+40h]
0x18005d6e9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005d6ee  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d6f3  lea     rdx, aWinbioplugins; "WinBioPlugIns"
0x18005d6fa  lea     rcx, [rax+40h]
0x18005d6fe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005d703  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d708  lea     rdx, asc_1800DC1E4; "\\"
0x18005d70f  lea     rcx, [rax+40h]
0x18005d713  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18005d718  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d71d  lea     rcx, [rax+40h]
0x18005d721  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d726  mov     rdi, rax
0x18005d729  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d72e  lea     rdx, [rax+40h]
0x18005d732  mov     rcx, rdx
0x18005d735  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d73a  mov     rcx, [rdx+10h]
0x18005d73e  lea     rbx, [rax+rcx*2]
0x18005d742  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d747  lea     rcx, [rax+40h]
0x18005d74b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005d750  mov     rdx, rax
0x18005d753  lea     rcx, [rsp+268h+var_238]
0x18005d758  mov     rax, cs:__imp_towupper
0x18005d75f  mov     r9, rdi
0x18005d762  mov     r8, rbx
0x18005d765  mov     [rsp+268h+var_248], rax
0x18005d76a  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18005d76f  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x18005d774  mov     rcx, rax; this
0x18005d777  call    ?RegisterAll@CPlugInManager@@QEAAJXZ; CPlugInManager::RegisterAll(void)
0x18005d77c  mov     rcx, [rsp+268h+var_18]
0x18005d784  xor     rcx, rsp; StackCookie
0x18005d787  call    __security_check_cookie
0x18005d78c  mov     rbx, [rsp+268h+arg_0]
0x18005d794  add     rsp, 260h
0x18005d79b  pop     rdi
0x18005d79c  retn
```
