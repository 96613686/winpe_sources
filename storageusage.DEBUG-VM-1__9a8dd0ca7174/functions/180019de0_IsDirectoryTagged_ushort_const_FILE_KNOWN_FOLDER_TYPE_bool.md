# IsDirectoryTagged(ushort const *,_FILE_KNOWN_FOLDER_TYPE,bool &)

- ea: `0x180019de0`
- end: `0x180019ed4`
- name: `?IsDirectoryTagged@@YAJPEBGW4_FILE_KNOWN_FOLDER_TYPE@@AEA_N@Z`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001cb04`
- `0x18001d020`

## callees

- `0x1800010b0`
- `0x1800025b0`
- `0x180010440`
- `0x1800190a0`
- `0x180019de0`
- `0x18001f1e0`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180019e46`
- `ntdll!NtQueryInformationFile` at `0x180019e46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsDirectoryTagged(const unsigned __int16 *a1, int a2, bool *a3)
{
  int Handle; // ebx
  NTSTATUS v7; // eax
  int v8; // ecx
  int v9; // r8d
  HANDLE FileHandle; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-18h] BYREF
  int FileInformation; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+98h] [rbp+38h] BYREF

  FileHandle = (HANDLE)-1LL;
  FileInformation = 0;
  IoStatusBlock = 0;
  *a3 = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&FileHandle);
  Handle = GetHandle(a1, &FileHandle);
  if ( Handle >= 0 )
  {
    v7 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, FileNamesInformation|0x40);
    Handle = v7 | 0x10000000;
    if ( v7 >= 0 )
      *a3 = FileInformation == a2;
  }
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v12 = 0x1000000;
    v16 = Handle;
    v13 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v8,
      (unsigned int)&dword_1800377DC,
      v9,
      (unsigned int)&v13,
      (__int64)&v16,
      (__int64)&v12);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x180019de0  mov     [rsp-18h+arg_0], rbx
0x180019de5  push    rbp
0x180019de6  push    rsi
0x180019de7  push    rdi
0x180019de8  mov     rbp, rsp
0x180019deb  sub     rsp, 60h
0x180019def  mov     rdi, r8
0x180019df2  mov     esi, edx
0x180019df4  mov     rbx, rcx
0x180019df7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019dfb  mov     [rbp+FileHandle], rdx
0x180019dff  mov     [rbp+FileInformation], 0
0x180019e06  xorps   xmm0, xmm0
0x180019e09  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180019e0d  mov     byte ptr [r8], 0
0x180019e11  lea     rcx, [rbp+FileHandle]
0x180019e15  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180019e1a  lea     rdx, [rbp+FileHandle]; void **
0x180019e1e  mov     rcx, rbx; unsigned __int16 *
0x180019e21  call    ?GetHandle@@YAJPEBGPEAPEAX@Z; GetHandle(ushort const *,void * *)
0x180019e26  mov     ebx, eax
0x180019e28  test    eax, eax
0x180019e2a  js      short loc_180019E5E
0x180019e2c  mov     [rsp+60h+FileInformationClass], 4Ch ; 'L'; FileInformationClass
0x180019e34  mov     r9d, 4; Length
0x180019e3a  lea     r8, [rbp+FileInformation]; FileInformation
0x180019e3e  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180019e42  mov     rcx, [rbp+FileHandle]; FileHandle
0x180019e46  call    cs:__imp_NtQueryInformationFile
0x180019e4c  mov     ebx, eax
0x180019e4e  or      ebx, 10000000h
0x180019e54  jl      short loc_180019E5E
0x180019e56  cmp     [rbp+FileInformation], esi
0x180019e59  setz    al
0x180019e5c  mov     [rdi], al
0x180019e5e  mov     eax, cs:dword_180040010
0x180019e64  cmp     eax, 5
0x180019e67  jbe     short loc_180019EB9
0x180019e69  mov     rdx, 400000000000h
0x180019e73  lea     rcx, dword_180040010
0x180019e7a  call    _tlgKeywordOn
0x180019e7f  test    al, al
0x180019e81  jz      short loc_180019EB9
0x180019e83  mov     [rbp+var_28], 1000000h
0x180019e8b  mov     [rbp+arg_18], ebx
0x180019e8e  mov     [rbp+var_20], 1
0x180019e96  lea     rax, [rbp+var_28]
0x180019e9a  mov     [rsp+60h+var_38], rax
0x180019e9f  lea     rax, [rbp+arg_18]
0x180019ea3  mov     qword ptr [rsp+60h+FileInformationClass], rax
0x180019ea8  lea     r9, [rbp+var_20]
0x180019eac  lea     rdx, dword_1800377DC
0x180019eb3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180019eb8  nop
0x180019eb9  lea     rcx, [rbp+FileHandle]
0x180019ebd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180019ec2  mov     eax, ebx
0x180019ec4  mov     rbx, [rsp+60h+arg_0]
0x180019ecc  add     rsp, 60h
0x180019ed0  pop     rdi
0x180019ed1  pop     rsi
0x180019ed2  pop     rbp
0x180019ed3  retn
```
