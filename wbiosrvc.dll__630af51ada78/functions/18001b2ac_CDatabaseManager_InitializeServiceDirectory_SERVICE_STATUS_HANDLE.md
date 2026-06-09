# CDatabaseManager::InitializeServiceDirectory(SERVICE_STATUS_HANDLE__ *)

- ea: `0x18001b2ac`
- end: `0x18001b44d`
- name: `?InitializeServiceDirectory@CDatabaseManager@@AEAAJPEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(CDatabaseManager *__hidden this, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d378`

## callees

- `0x180011d90`
- `0x1800148b4`
- `0x18001693c`
- `0x18001b2ac`
- `0x18003c8dc`
- `0x18005388c`
- `0x180056358`
- `0x180060254`
- `0x180068f60`
- `0x180069cc8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001b300`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001b300`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18001b362`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18001b3d2`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18001b362`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18001b3d2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001b2da`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001b2da`

## string_xrefs

- `0x18001b311`: `onecore\ds\security\biometrics\service\server\databasemanager.cpp`
- `0x18001b38a`: `onecore\ds\security\biometrics\service\server\databasemanager.cpp`
- `0x18001b3e6`: `onecore\ds\security\biometrics\service\server\databasemanager.cpp`

## pseudocode

```c
__int64 __fastcall CDatabaseManager::InitializeServiceDirectory(
        CDatabaseManager *this,
        struct SERVICE_STATUS_HANDLE__ *a2)
{
  const char *v4; // r9
  int ServiceDirectory; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( !GetSystemDirectoryW(Buffer, 0x105u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x122,
               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\databasemanager.cpp",
               v4);
    std::_WChar_traits<unsigned short>::length(Buffer);
    std::wstring::_Assign<unsigned short>((char *)this + 64, Buffer);
    return 0;
  }
  v10 = 0;
  ServiceDirectory = GetServiceDirectory(a2, 0, 0, 0);
  v7 = ServiceDirectory;
  if ( ServiceDirectory != 122 )
  {
    if ( ServiceDirectory > 0 )
      v7 = (unsigned __int16)ServiceDirectory | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\databasemanager.cpp",
        (const char *)v7,
        (int)&v10);
    return v7;
  }
  std::vector<unsigned short>::vector<unsigned short>(v11, v10 + 1);
  v8 = GetServiceDirectory(a2, 0, v11[0], (__int64)(v11[1] - v11[0]) >> 1);
  if ( v8 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x139,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\databasemanager.cpp",
           (const char *)v8,
           (unsigned int)&v10);
    std::vector<unsigned short>::_Tidy(v11);
    return v7;
  }
  std::_WChar_traits<unsigned short>::length(v11[0]);
  std::wstring::_Assign<unsigned short>((char *)this + 64, v9);
  std::vector<unsigned short>::_Tidy(v11);
  return 0;
}

```

## disassembly

```asm
0x18001b2ac  mov     [rsp-8+arg_10], rbx
0x18001b2b1  push    rbp
0x18001b2b2  push    rsi
0x18001b2b3  push    rdi
0x18001b2b4  lea     rbp, [rsp-170h]
0x18001b2bc  sub     rsp, 270h
0x18001b2c3  mov     rax, cs:__security_cookie
0x18001b2ca  xor     rax, rsp
0x18001b2cd  mov     [rbp+180h+var_20], rax
0x18001b2d4  mov     rsi, rdx
0x18001b2d7  mov     rdi, rcx
0x18001b2da  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001b2e0  xor     edx, edx; Val
0x18001b2e2  test    al, al
0x18001b2e4  jnz     short loc_18001B347
0x18001b2e6  mov     r8d, 20Ah; Size
0x18001b2ec  lea     rcx, [rsp+280h+Buffer]; void *
0x18001b2f1  call    memset_0
0x18001b2f6  mov     edx, 105h; uSize
0x18001b2fb  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x18001b300  call    cs:__imp_GetSystemDirectoryW
0x18001b306  test    eax, eax
0x18001b308  jnz     short loc_18001B327
0x18001b30a  mov     rcx, [rbp+188h]; this
0x18001b311  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\biometrics\\serv"...
0x18001b318  mov     edx, 122h; void *
0x18001b31d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b322  jmp     loc_18001B42B
0x18001b327  lea     rcx, [rsp+280h+Buffer]
0x18001b32c  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b331  mov     r8, rax
0x18001b334  lea     rcx, [rdi+40h]
0x18001b338  lea     rdx, [rsp+280h+Buffer]
0x18001b33d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b342  jmp     loc_18001B429
0x18001b347  mov     [rsp+280h+var_250], 0
0x18001b34f  lea     rax, [rsp+280h+var_250]
0x18001b354  mov     qword ptr [rsp+280h+var_260], rax; int
0x18001b359  xor     r9d, r9d
0x18001b35c  xor     r8d, r8d
0x18001b35f  mov     rcx, rsi
0x18001b362  call    cs:__imp_GetServiceDirectory
0x18001b368  mov     ebx, eax
0x18001b36a  cmp     eax, 7Ah ; 'z'
0x18001b36d  jz      short loc_18001B3A2
0x18001b36f  test    eax, eax
0x18001b371  jle     short loc_18001B37C
0x18001b373  movzx   ebx, ax
0x18001b376  or      ebx, 80070000h
0x18001b37c  test    ebx, ebx
0x18001b37e  jns     short loc_18001B39B
0x18001b380  mov     rcx, [rbp+188h]; this
0x18001b387  mov     r9d, ebx; char *
0x18001b38a  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\biometrics\\serv"...
0x18001b391  mov     edx, 131h; void *
0x18001b396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b39b  mov     eax, ebx
0x18001b39d  jmp     loc_18001B42B
0x18001b3a2  mov     edx, [rsp+280h+var_250]
0x18001b3a6  inc     edx
0x18001b3a8  lea     rcx, [rsp+280h+var_248]
0x18001b3ad  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001b3b2  nop
0x18001b3b3  mov     r8, [rsp+280h+var_248]
0x18001b3b8  mov     r9, [rsp+280h+var_240]
0x18001b3bd  sub     r9, r8
0x18001b3c0  sar     r9, 1
0x18001b3c3  lea     rax, [rsp+280h+var_250]
0x18001b3c8  mov     qword ptr [rsp+280h+var_260], rax; unsigned int
0x18001b3cd  xor     edx, edx
0x18001b3cf  mov     rcx, rsi
0x18001b3d2  call    cs:__imp_GetServiceDirectory
0x18001b3d8  test    eax, eax
0x18001b3da  jz      short loc_18001B405
0x18001b3dc  mov     rcx, [rbp+188h]; this
0x18001b3e3  mov     r9d, eax; char *
0x18001b3e6  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\biometrics\\serv"...
0x18001b3ed  mov     edx, 139h; void *
0x18001b3f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b3f7  mov     ebx, eax
0x18001b3f9  lea     rcx, [rsp+280h+var_248]
0x18001b3fe  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001b403  jmp     short loc_18001B39B
0x18001b405  mov     rdx, [rsp+280h+var_248]
0x18001b40a  mov     rcx, rdx
0x18001b40d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b412  lea     rcx, [rdi+40h]
0x18001b416  mov     r8, rax
0x18001b419  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001b41e  nop
0x18001b41f  lea     rcx, [rsp+280h+var_248]
0x18001b424  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001b429  xor     eax, eax
0x18001b42b  mov     rcx, [rbp+180h+var_20]
0x18001b432  xor     rcx, rsp; StackCookie
0x18001b435  call    __security_check_cookie
0x18001b43a  mov     rbx, [rsp+280h+arg_10]
0x18001b442  add     rsp, 270h
0x18001b449  pop     rdi
0x18001b44a  pop     rsi
0x18001b44b  pop     rbp
0x18001b44c  retn
```
