# TagDirectory(ushort const *,_FILE_KNOWN_FOLDER_TYPE)

- ea: `0x18001ca14`
- end: `0x18001cafb`
- name: `?TagDirectory@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cb04`

## callees

- `0x1800010b0`
- `0x1800025b0`
- `0x180010440`
- `0x1800190a0`
- `0x18001ca14`
- `0x18001f1e0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18001ca79`
- `ntdll!NtSetInformationFile` at `0x18001ca79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TagDirectory(const unsigned __int16 *a1, int a2)
{
  int Handle; // ebx
  int v5; // ecx
  int v6; // r8d
  HANDLE FileHandle; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+38h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-18h] BYREF
  int FileInformation; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+88h] [rbp+28h] BYREF

  FileHandle = (HANDLE)-1LL;
  FileInformation = 0;
  IoStatusBlock = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&FileHandle);
  Handle = GetHandle(a1, &FileHandle);
  if ( Handle >= 0 )
  {
    FileInformation = a2;
    Handle = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, FileNamesInformation|0x40)
           | 0x10000000;
  }
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v9 = 0x1000000;
    v13 = Handle;
    v10 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)byte_180037F6B,
      v6,
      (unsigned int)&v10,
      (__int64)&v13,
      (__int64)&v9);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x18001ca14  mov     [rsp-8+arg_0], rbx
0x18001ca19  mov     [rsp-8+arg_8], rdi
0x18001ca1e  push    rbp
0x18001ca1f  mov     rbp, rsp
0x18001ca22  sub     rsp, 60h
0x18001ca26  mov     edi, edx
0x18001ca28  mov     rbx, rcx
0x18001ca2b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ca2f  mov     [rbp+FileHandle], rdx
0x18001ca33  mov     [rbp+FileInformation], 0
0x18001ca3a  xorps   xmm0, xmm0
0x18001ca3d  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001ca41  lea     rcx, [rbp+FileHandle]
0x18001ca45  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ca4a  lea     rdx, [rbp+FileHandle]; void **
0x18001ca4e  mov     rcx, rbx; unsigned __int16 *
0x18001ca51  call    ?GetHandle@@YAJPEBGPEAPEAX@Z; GetHandle(ushort const *,void * *)
0x18001ca56  mov     ebx, eax
0x18001ca58  test    eax, eax
0x18001ca5a  js      short loc_18001CA85
0x18001ca5c  mov     [rbp+FileInformation], edi
0x18001ca5f  mov     [rsp+60h+FileInformationClass], 4Ch ; 'L'; FileInformationClass
0x18001ca67  mov     r9d, 4; Length
0x18001ca6d  lea     r8, [rbp+FileInformation]; FileInformation
0x18001ca71  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18001ca75  mov     rcx, [rbp+FileHandle]; FileHandle
0x18001ca79  call    cs:__imp_NtSetInformationFile
0x18001ca7f  mov     ebx, eax
0x18001ca81  bts     ebx, 1Ch
0x18001ca85  mov     eax, cs:dword_180040010
0x18001ca8b  cmp     eax, 5
0x18001ca8e  jbe     short loc_18001CAE0
0x18001ca90  mov     rdx, 400000000000h
0x18001ca9a  lea     rcx, dword_180040010
0x18001caa1  call    _tlgKeywordOn
0x18001caa6  test    al, al
0x18001caa8  jz      short loc_18001CAE0
0x18001caaa  mov     [rbp+var_28], 1000000h
0x18001cab2  mov     [rbp+arg_18], ebx
0x18001cab5  mov     [rbp+var_20], 1
0x18001cabd  lea     rax, [rbp+var_28]
0x18001cac1  mov     [rsp+60h+var_38], rax
0x18001cac6  lea     rax, [rbp+arg_18]
0x18001caca  mov     qword ptr [rsp+60h+FileInformationClass], rax
0x18001cacf  lea     r9, [rbp+var_20]
0x18001cad3  lea     rdx, byte_180037F6B
0x18001cada  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001cadf  nop
0x18001cae0  lea     rcx, [rbp+FileHandle]
0x18001cae4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001cae9  mov     eax, ebx
0x18001caeb  mov     rbx, [rsp+60h+arg_0]
0x18001caf0  mov     rdi, [rsp+60h+arg_8]
0x18001caf5  add     rsp, 60h
0x18001caf9  pop     rbp
0x18001cafa  retn
```
