# Windows::System::Internal::StoreBuffer(ushort const *,Windows::Storage::Streams::IBuffer *)

- ea: `0x18006900c`
- end: `0x180069112`
- name: `?StoreBuffer@Internal@System@Windows@@YAJPEBGPEAUIBuffer@Streams@Storage@3@@Z`
- size: `262`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a44a0`

## callees

- `0x18000ce48`
- `0x18004bfa0`
- `0x180068e98`
- `0x18006900c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006906d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800690c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006906d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800690c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800690d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800690d9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800690b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800690b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006905f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006905f`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::StoreBuffer(
        const WCHAR *this,
        const unsigned __int16 *a2,
        struct Windows::Storage::Streams::IBuffer *a3)
{
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int ByteArrayFromBuffer; // ebx
  signed int v7; // eax
  __int64 v9; // [rsp+40h] [rbp-18h] BYREF
  __int64 v10; // [rsp+48h] [rbp-10h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+70h] [rbp+18h] BYREF
  LPCVOID lpBuffer; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  v9 = 0;
  lpBuffer = 0;
  nNumberOfBytesToWrite = 0;
  FileW = CreateFileW(this, 0x40000000u, 2u, 0, 2u, 6u, 0);
  if ( FileW )
    goto LABEL_5;
  LastError = GetLastError();
  ByteArrayFromBuffer = LastError;
  if ( LastError > 0 )
    ByteArrayFromBuffer = (unsigned __int16)LastError | 0x80070000;
  if ( ByteArrayFromBuffer >= 0 )
  {
LABEL_5:
    ByteArrayFromBuffer = Windows::System::Internal::GetByteArrayFromBuffer(a2, &nNumberOfBytesToWrite, &lpBuffer);
    if ( ByteArrayFromBuffer >= 0 && !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, 0, 0) )
    {
      v7 = GetLastError();
      ByteArrayFromBuffer = v7;
      if ( v7 > 0 )
        ByteArrayFromBuffer = (unsigned __int16)v7 | 0x80070000;
    }
  }
  CloseHandle(FileW);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v10);
  return (unsigned int)ByteArrayFromBuffer;
}

```

## disassembly

```asm
0x18006900c  mov     rax, rsp
0x18006900f  mov     [rax+8], rbx
0x180069013  mov     [rax+10h], rsi
0x180069017  push    rdi
0x180069018  sub     rsp, 50h
0x18006901c  mov     rsi, rdx
0x18006901f  mov     qword ptr [rax-10h], 0
0x180069027  mov     qword ptr [rax-18h], 0
0x18006902f  mov     qword ptr [rax+20h], 0
0x180069037  mov     dword ptr [rax+18h], 0
0x18006903e  mov     qword ptr [rax-28h], 0
0x180069046  mov     dword ptr [rax-30h], 6
0x18006904d  mov     r8d, 2; dwShareMode
0x180069053  mov     [rax-38h], r8d
0x180069057  xor     r9d, r9d; lpSecurityAttributes
0x18006905a  mov     edx, 40000000h; dwDesiredAccess
0x18006905f  call    cs:__imp_CreateFileW
0x180069065  mov     rdi, rax
0x180069068  test    rax, rax
0x18006906b  jnz     short loc_180069086
0x18006906d  call    cs:__imp_GetLastError
0x180069073  mov     ebx, eax
0x180069075  test    eax, eax
0x180069077  jle     short loc_180069082
0x180069079  movzx   ebx, ax
0x18006907c  or      ebx, 80070000h
0x180069082  test    ebx, ebx
0x180069084  js      short loc_1800690D6
0x180069086  lea     r8, [rsp+58h+lpBuffer]
0x18006908b  lea     rdx, [rsp+58h+nNumberOfBytesToWrite]
0x180069090  mov     rcx, rsi
0x180069093  call    ?GetByteArrayFromBuffer@Internal@System@Windows@@YAJPEAUIBuffer@Streams@Storage@3@PEAIAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::System::Internal::GetByteArrayFromBuffer(Windows::Storage::Streams::IBuffer *,uint *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180069098  mov     ebx, eax
0x18006909a  test    eax, eax
0x18006909c  js      short loc_1800690D6
0x18006909e  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1800690a7  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800690aa  mov     r8d, [rsp+58h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800690af  mov     rdx, [rsp+58h+lpBuffer]; lpBuffer
0x1800690b4  mov     rcx, rdi; hFile
0x1800690b7  call    cs:__imp_WriteFile
0x1800690bd  test    eax, eax
0x1800690bf  jnz     short loc_1800690D6
0x1800690c1  call    cs:__imp_GetLastError
0x1800690c7  mov     ebx, eax
0x1800690c9  test    eax, eax
0x1800690cb  jle     short loc_1800690D6
0x1800690cd  movzx   ebx, ax
0x1800690d0  or      ebx, 80070000h
0x1800690d6  mov     rcx, rdi; hObject
0x1800690d9  call    cs:__imp_CloseHandle
0x1800690df  nop
0x1800690e0  lea     rcx, [rsp+58h+lpBuffer]
0x1800690e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800690ea  nop
0x1800690eb  lea     rcx, [rsp+58h+var_18]
0x1800690f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800690f5  nop
0x1800690f6  lea     rcx, [rsp+58h+var_10]
0x1800690fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180069100  mov     eax, ebx
0x180069102  mov     rbx, [rsp+58h+arg_0]
0x180069107  mov     rsi, [rsp+58h+arg_8]
0x18006910c  add     rsp, 50h
0x180069110  pop     rdi
0x180069111  retn
```
