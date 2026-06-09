# Windows::System::Internal::GetLocalPicture(ushort const *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x1800d2674`
- end: `0x1800d289b`
- name: `?GetLocalPicture@Internal@System@Windows@@YAJPEBGW4UserPictureSize@23@PEAPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z`
- size: `551`
- prototype: `__int64 __fastcall(const WCHAR *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180064638`

## callees

- `0x1800088e8`
- `0x180008b10`
- `0x18000ce48`
- `0x180015960`
- `0x18002514c`
- `0x18004bfa0`
- `0x18004c378`
- `0x18005f6c8`
- `0x18005f7e4`
- `0x1800d23a4`
- `0x1800d2674`
- `0x1800d2c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d274d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d274d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d26f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d272a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d27a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d26f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d272a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d2768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d27a3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800d2720`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800d2720`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d2799`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d2799`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d26de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d26de`

## string_xrefs

- `0x1800d283f`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Windows::System::Internal::GetLocalPicture(const WCHAR *a1, unsigned int a2, __int64 a3)
{
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int BufferFromByteArray; // ecx
  signed int v8; // eax
  LPVOID v9; // rax
  void *v10; // rbx
  signed int v11; // eax
  signed int v12; // eax
  struct Windows::Storage::Streams::IBuffer **v13; // r9
  struct Windows::Storage::Streams::IRandomAccessStreamReference **v14; // rdx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v15; // r8
  int DefaultPicture; // eax
  unsigned int v17; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  struct Windows::Storage::Streams::IBuffer *v20; // [rsp+40h] [rbp-38h] BYREF
  Windows::System::Internal *v21; // [rsp+48h] [rbp-30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-28h] BYREF
  LPVOID lpBuffer; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  DWORD NumberOfBytesRead; // [rsp+C8h] [rbp+50h] BYREF

  v24[0] = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  lpBuffer = 0;
  v21 = 0;
  v20 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 6u, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_5;
  LastError = GetLastError();
  BufferFromByteArray = LastError;
  if ( LastError > 0 )
    BufferFromByteArray = (unsigned __int16)LastError | 0x80070000;
  if ( BufferFromByteArray >= 0 )
  {
LABEL_5:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v24,
      FileW);
    if ( GetFileSizeEx(FileW, &FileSize) )
      goto LABEL_9;
    v8 = GetLastError();
    BufferFromByteArray = v8;
    if ( v8 > 0 )
      BufferFromByteArray = (unsigned __int16)v8 | 0x80070000;
    if ( BufferFromByteArray >= 0 )
    {
LABEL_9:
      NumberOfBytesRead = FileSize.LowPart;
      v9 = CoTaskMemAlloc(FileSize.LowPart);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &lpBuffer,
        v9);
      v10 = lpBuffer;
      if ( lpBuffer )
        goto LABEL_16;
      v11 = GetLastError();
      BufferFromByteArray = v11;
      if ( v11 > 0 )
        BufferFromByteArray = (unsigned __int16)v11 | 0x80070000;
      if ( BufferFromByteArray >= 0 )
      {
LABEL_16:
        if ( ReadFile(FileW, v10, FileSize.LowPart, &NumberOfBytesRead, 0) )
          goto LABEL_17;
        v12 = GetLastError();
        BufferFromByteArray = v12;
        if ( v12 > 0 )
          BufferFromByteArray = (unsigned __int16)v12 | 0x80070000;
        if ( BufferFromByteArray >= 0 )
        {
LABEL_17:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
          BufferFromByteArray = Windows::System::Internal::GetBufferFromByteArray(
                                  (Windows::System::Internal *)v10,
                                  (unsigned __int8 *)NumberOfBytesRead,
                                  (unsigned int)&v21,
                                  v13);
          if ( BufferFromByteArray >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
            BufferFromByteArray = Windows::System::Internal::CreateEmptyStream((Windows::System::Internal *)&v20, v14);
            if ( BufferFromByteArray >= 0 )
            {
              BufferFromByteArray = Windows::System::Internal::WriteBufferToStreamReference(v21, v20, v15);
              if ( BufferFromByteArray >= 0 )
                BufferFromByteArray = Windows::System::Internal::ResizePicture(v20, a2, a3);
            }
          }
        }
      }
    }
  }
  if ( (unsigned int)(BufferFromByteArray + 2147024894) > 1 )
    goto LABEL_25;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  DefaultPicture = Windows::System::Internal::GetDefaultPicture(0, &v20);
  v17 = DefaultPicture;
  if ( DefaultPicture >= 0 )
  {
    BufferFromByteArray = Windows::System::Internal::ResizePicture(v20, a2, a3);
LABEL_25:
    v17 = BufferFromByteArray;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x530,
    (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
    (const char *)(unsigned int)DefaultPicture,
    dwCreationDisposition);
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpBuffer);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v24);
  return v17;
}

```

## disassembly

```asm
0x1800d2674  push    rbp
0x1800d2676  push    rbx
0x1800d2677  push    rsi
0x1800d2678  push    rdi
0x1800d2679  push    r12
0x1800d267b  push    r14
0x1800d267d  mov     rbp, rsp
0x1800d2680  sub     rsp, 78h
0x1800d2684  mov     rsi, r8
0x1800d2687  mov     r14d, edx
0x1800d268a  mov     [rbp+var_18], 0
0x1800d2692  mov     qword ptr [rbp+FileSize], 0
0x1800d269a  mov     [rbp+NumberOfBytesRead], 0
0x1800d26a1  mov     [rbp+lpBuffer], 0
0x1800d26a9  mov     [rbp+var_30], 0
0x1800d26b1  mov     [rbp+var_38], 0
0x1800d26b9  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800d26c2  mov     [rsp+78h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800d26ca  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800d26d2  xor     r9d, r9d; lpSecurityAttributes
0x1800d26d5  mov     edx, 80000000h; dwDesiredAccess
0x1800d26da  lea     r8d, [r9+1]; dwShareMode
0x1800d26de  call    cs:__imp_CreateFileW
0x1800d26e4  mov     rdi, rax
0x1800d26e7  mov     r12d, 80070000h
0x1800d26ed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d26f1  jnz     short loc_1800D270D
0x1800d26f3  call    cs:__imp_GetLastError
0x1800d26f9  mov     ecx, eax
0x1800d26fb  test    eax, eax
0x1800d26fd  jle     short loc_1800D2705
0x1800d26ff  movzx   ecx, ax
0x1800d2702  or      ecx, r12d
0x1800d2705  test    ecx, ecx
0x1800d2707  js      loc_1800D2813
0x1800d270d  mov     rdx, rdi
0x1800d2710  lea     rcx, [rbp+var_18]
0x1800d2714  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d2719  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800d271d  mov     rcx, rdi; hFile
0x1800d2720  call    cs:__imp_GetFileSizeEx
0x1800d2726  test    eax, eax
0x1800d2728  jnz     short loc_1800D2744
0x1800d272a  call    cs:__imp_GetLastError
0x1800d2730  mov     ecx, eax
0x1800d2732  test    eax, eax
0x1800d2734  jle     short loc_1800D273C
0x1800d2736  movzx   ecx, ax
0x1800d2739  or      ecx, r12d
0x1800d273c  test    ecx, ecx
0x1800d273e  js      loc_1800D2813
0x1800d2744  mov     rax, qword ptr [rbp+FileSize]
0x1800d2748  mov     [rbp+NumberOfBytesRead], eax
0x1800d274b  mov     ecx, eax; cb
0x1800d274d  call    cs:__imp_CoTaskMemAlloc
0x1800d2753  mov     rdx, rax
0x1800d2756  lea     rcx, [rbp+lpBuffer]
0x1800d275a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800d275f  mov     rbx, [rbp+lpBuffer]
0x1800d2763  test    rbx, rbx
0x1800d2766  jnz     short loc_1800D2782
0x1800d2768  call    cs:__imp_GetLastError
0x1800d276e  mov     ecx, eax
0x1800d2770  test    eax, eax
0x1800d2772  jle     short loc_1800D277A
0x1800d2774  movzx   ecx, ax
0x1800d2777  or      ecx, r12d
0x1800d277a  test    ecx, ecx
0x1800d277c  js      loc_1800D2813
0x1800d2782  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; int
0x1800d278b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800d278f  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x1800d2793  mov     rdx, rbx; lpBuffer
0x1800d2796  mov     rcx, rdi; hFile
0x1800d2799  call    cs:__imp_ReadFile
0x1800d279f  test    eax, eax
0x1800d27a1  jnz     short loc_1800D27B9
0x1800d27a3  call    cs:__imp_GetLastError
0x1800d27a9  mov     ecx, eax
0x1800d27ab  test    eax, eax
0x1800d27ad  jle     short loc_1800D27B5
0x1800d27af  movzx   ecx, ax
0x1800d27b2  or      ecx, r12d
0x1800d27b5  test    ecx, ecx
0x1800d27b7  js      short loc_1800D2813
0x1800d27b9  lea     rcx, [rbp+var_30]
0x1800d27bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d27c2  lea     r8, [rbp+var_30]; unsigned int
0x1800d27c6  mov     edx, [rbp+NumberOfBytesRead]; unsigned __int8 *
0x1800d27c9  mov     rcx, rbx; this
0x1800d27cc  call    ?GetBufferFromByteArray@Internal@System@Windows@@YAJPEAEIPEAPEAUIBuffer@Streams@Storage@3@@Z; Windows::System::Internal::GetBufferFromByteArray(uchar *,uint,Windows::Storage::Streams::IBuffer * *)
0x1800d27d1  mov     ecx, eax
0x1800d27d3  test    eax, eax
0x1800d27d5  js      short loc_1800D2813
0x1800d27d7  lea     rcx, [rbp+var_38]
0x1800d27db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d27e0  lea     rcx, [rbp+var_38]; this
0x1800d27e4  call    ?CreateEmptyStream@Internal@System@Windows@@YAJPEAPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::System::Internal::CreateEmptyStream(Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800d27e9  mov     ecx, eax
0x1800d27eb  test    eax, eax
0x1800d27ed  js      short loc_1800D2813
0x1800d27ef  mov     rdx, [rbp+var_38]; struct Windows::Storage::Streams::IBuffer *
0x1800d27f3  mov     rcx, [rbp+var_30]; this
0x1800d27f7  call    ?WriteBufferToStreamReference@Internal@System@Windows@@YAJPEAUIBuffer@Streams@Storage@3@PEAUIRandomAccessStreamReference@563@@Z; Windows::System::Internal::WriteBufferToStreamReference(Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IRandomAccessStreamReference *)
0x1800d27fc  mov     ecx, eax
0x1800d27fe  test    eax, eax
0x1800d2800  js      short loc_1800D2813
0x1800d2802  mov     r8, rsi
0x1800d2805  mov     edx, r14d
0x1800d2808  mov     rcx, [rbp+var_38]
0x1800d280c  call    ?ResizePicture@Internal@System@Windows@@YAJPEAUIRandomAccessStreamReference@Streams@Storage@3@W4UserPictureSize@23@PEAPEAU4563@@Z; Windows::System::Internal::ResizePicture(Windows::Storage::Streams::IRandomAccessStreamReference *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800d2811  mov     ecx, eax
0x1800d2813  lea     eax, [rcx+7FF8FFFEh]
0x1800d2819  cmp     eax, 1
0x1800d281c  ja      short loc_1800D2863
0x1800d281e  lea     rcx, [rbp+var_38]
0x1800d2822  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d2827  lea     rdx, [rbp+var_38]
0x1800d282b  xor     ecx, ecx
0x1800d282d  call    ?GetDefaultPicture@Internal@System@Windows@@YAJW4DefaultUserPictureFileType@123@PEAPEAUIRandomAccessStreamReference@Streams@Storage@3@@Z; Windows::System::Internal::GetDefaultPicture(Windows::System::Internal::DefaultUserPictureFileType,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800d2832  mov     ebx, eax
0x1800d2834  test    eax, eax
0x1800d2836  jns     short loc_1800D2852
0x1800d2838  mov     rcx, [rbp+30h]; this
0x1800d283c  mov     r9d, eax; char *
0x1800d283f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x1800d2846  mov     edx, 530h; void *
0x1800d284b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2850  jmp     short loc_1800D2865
0x1800d2852  mov     r8, rsi
0x1800d2855  mov     edx, r14d
0x1800d2858  mov     rcx, [rbp+var_38]
0x1800d285c  call    ?ResizePicture@Internal@System@Windows@@YAJPEAUIRandomAccessStreamReference@Streams@Storage@3@W4UserPictureSize@23@PEAPEAU4563@@Z; Windows::System::Internal::ResizePicture(Windows::Storage::Streams::IRandomAccessStreamReference *,Windows::System::UserPictureSize,Windows::Storage::Streams::IRandomAccessStreamReference * *)
0x1800d2861  mov     ecx, eax
0x1800d2863  mov     ebx, ecx
0x1800d2865  lea     rcx, [rbp+var_38]
0x1800d2869  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d286e  nop
0x1800d286f  lea     rcx, [rbp+var_30]
0x1800d2873  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d2878  nop
0x1800d2879  lea     rcx, [rbp+lpBuffer]
0x1800d287d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d2882  nop
0x1800d2883  lea     rcx, [rbp+var_18]
0x1800d2887  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d288c  mov     eax, ebx
0x1800d288e  add     rsp, 78h
0x1800d2892  pop     r14
0x1800d2894  pop     r12
0x1800d2896  pop     rdi
0x1800d2897  pop     rsi
0x1800d2898  pop     rbx
0x1800d2899  pop     rbp
0x1800d289a  retn
```
