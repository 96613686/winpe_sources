# Microsoft::CommonDatapoints::GetDiskGeometry(ulong *,ulong *)

- ea: `0x180105fcc`
- end: `0x1801061e9`
- name: `?GetDiskGeometry@CommonDatapoints@Microsoft@@CAJPEAK0@Z`
- size: `541`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800d77d4`

## callees

- `0x18009bd1c`
- `0x180105fcc`
- `0x1801061f0`
- `0x18012de40`
- `0x18012eb08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106071`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106071`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180106061`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180106061`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801060dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801060dd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180106134`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180106193`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180106134`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180106193`

## pseudocode

```c
__int64 __fastcall Microsoft::CommonDatapoints::GetDiskGeometry(unsigned int *a1, unsigned int *a2)
{
  HANDLE v4; // rbx
  signed int LastError; // eax
  __int64 v6; // rcx
  signed int v7; // edi
  __int64 v8; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h] BYREF
  int OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+54h] [rbp-ACh]
  __int128 v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+74h] [rbp-8Ch]
  WCHAR Buffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v17[526]; // [rsp+82h] [rbp-7Eh] BYREF
  WCHAR FileName; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v19[526]; // [rsp+292h] [rbp+192h] BYREF

  v15 = 0;
  v11 = 0;
  Buffer = 0;
  v4 = 0;
  OutBuffer = 0;
  v13 = 0;
  v14 = 0;
  memset_0(v17, 0, 0x206u);
  FileName = 0;
  memset_0(v19, 0, 0x206u);
  *a1 = 0;
  BytesReturned = 0;
  *a2 = 0;
  if ( GetSystemDirectoryW(&Buffer, 0x104u) )
  {
    v7 = StringCchPrintfW(&FileName, 0x104u, L"\\\\.\\%c:", Buffer);
    if ( v7 < 0 )
      goto LABEL_9;
    v4 = CreateFileW(&FileName, 0x80000000, 3u, 0, 3u, 0, 0);
    tlx::file_handle_traits::operator()(v8, 0);
    if ( (unsigned __int64)v4 + 1 > 1 )
    {
      if ( DeviceIoControl(v4, 0x700A0u, 0, 0, &OutBuffer, 0x28u, &BytesReturned, 0) )
      {
        *(__int64 *)((char *)&v14 + 4) /= 0x40000000;
        *a1 = DWORD1(v14);
        if ( DeviceIoControl(v4, 0x7405Cu, 0, 0, &v11, 8u, &BytesReturned, 0) )
        {
          v11 /= 0x40000000;
          *a2 = v11;
          goto LABEL_9;
        }
      }
    }
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
  tlx::file_handle_traits::operator()(v6, v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180105fcc  mov     [rsp-8+arg_10], rbx
0x180105fd1  push    rbp
0x180105fd2  push    rsi
0x180105fd3  push    rdi
0x180105fd4  push    r12
0x180105fd6  push    r14
0x180105fd8  lea     rbp, [rsp-3B0h]
0x180105fe0  sub     rsp, 4B0h
0x180105fe7  mov     rax, cs:__security_cookie
0x180105fee  xor     rax, rsp
0x180105ff1  mov     [rbp+3D0h+var_30], rax
0x180105ff8  xor     eax, eax
0x180105ffa  xorps   xmm0, xmm0
0x180105ffd  mov     rsi, rdx
0x180106000  mov     [rsp+4D0h+var_45C], eax
0x180106004  mov     r14, rcx
0x180106007  mov     [rsp+4D0h+var_488], rax
0x18010600c  mov     edi, 206h
0x180106011  mov     [rbp+3D0h+Buffer], ax
0x180106015  xor     ebx, ebx
0x180106017  lea     rcx, [rbp+3D0h+var_44E]; void *
0x18010601b  mov     r8d, edi; Size
0x18010601e  mov     [rsp+4D0h+OutBuffer], ebx
0x180106022  xor     edx, edx; Val
0x180106024  movups  [rsp+4D0h+var_47C], xmm0
0x180106029  movups  [rsp+4D0h+var_46C], xmm0
0x18010602e  call    memset_0
0x180106033  xor     eax, eax
0x180106035  lea     rcx, [rbp+3D0h+var_23E]; void *
0x18010603c  mov     r8d, edi; Size
0x18010603f  mov     [rbp+3D0h+FileName], ax
0x180106046  xor     edx, edx; Val
0x180106048  call    memset_0
0x18010604d  mov     [r14], ebx
0x180106050  lea     rcx, [rbp+3D0h+Buffer]; lpBuffer
0x180106054  mov     edi, 104h
0x180106059  mov     [rsp+4D0h+BytesReturned], ebx
0x18010605d  mov     edx, edi; uSize
0x18010605f  mov     [rsi], ebx
0x180106061  call    cs:__imp_GetSystemDirectoryW
0x180106068  nop     dword ptr [rax+rax+00h]
0x18010606d  test    eax, eax
0x18010606f  jnz     short loc_180106095
0x180106071  call    cs:__imp_GetLastError
0x180106078  nop     dword ptr [rax+rax+00h]
0x18010607d  mov     edi, eax
0x18010607f  test    eax, eax
0x180106081  jle     loc_1801061B8
0x180106087  movzx   edi, ax
0x18010608a  or      edi, 80070000h
0x180106090  jmp     loc_1801061B8
0x180106095  movzx   r9d, [rbp+3D0h+Buffer]
0x18010609a  lea     r8, aC; "\\\\.\\%c:"
0x1801060a1  mov     rdx, rdi; unsigned __int64
0x1801060a4  lea     rcx, [rbp+3D0h+FileName]; wchar_t *
0x1801060ab  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801060b0  mov     edi, eax
0x1801060b2  test    eax, eax
0x1801060b4  js      loc_1801061B8
0x1801060ba  mov     [rsp+4D0h+hTemplateFile], rbx; hTemplateFile
0x1801060bf  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x1801060c6  mov     r8d, 3; dwShareMode
0x1801060cc  mov     [rsp+4D0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1801060d0  xor     r9d, r9d; lpSecurityAttributes
0x1801060d3  mov     [rsp+4D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801060d8  mov     edx, 80000000h; dwDesiredAccess
0x1801060dd  call    cs:__imp_CreateFileW
0x1801060e4  nop     dword ptr [rax+rax+00h]
0x1801060e9  xor     edx, edx
0x1801060eb  mov     rbx, rax
0x1801060ee  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x1801060f3  lea     rax, [rbx+1]
0x1801060f7  cmp     rax, 1
0x1801060fb  jbe     loc_180106071
0x180106101  mov     [rsp+4D0h+lpOverlapped], 0; lpOverlapped
0x18010610a  lea     rax, [rsp+4D0h+BytesReturned]
0x18010610f  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x180106114  xor     r9d, r9d; nInBufferSize
0x180106117  lea     rax, [rsp+4D0h+OutBuffer]
0x18010611c  mov     [rsp+4D0h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x180106124  xor     r8d, r8d; lpInBuffer
0x180106127  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax; lpOutBuffer
0x18010612c  mov     edx, 700A0h; dwIoControlCode
0x180106131  mov     rcx, rbx; hDevice
0x180106134  call    cs:__imp_DeviceIoControl
0x18010613b  nop     dword ptr [rax+rax+00h]
0x180106140  test    eax, eax
0x180106142  jz      loc_180106071
0x180106148  mov     rax, qword ptr [rsp+4D0h+var_46C+4]
0x18010614d  mov     r12d, 40000000h
0x180106153  cqo
0x180106155  mov     [rsp+4D0h+lpOverlapped], 0; lpOverlapped
0x18010615e  idiv    r12
0x180106161  xor     r9d, r9d; nInBufferSize
0x180106164  xor     r8d, r8d; lpInBuffer
0x180106167  mov     qword ptr [rsp+4D0h+var_46C+4], rax
0x18010616c  mov     edx, 7405Ch; dwIoControlCode
0x180106171  mov     [r14], eax
0x180106174  mov     rcx, rbx; hDevice
0x180106177  lea     rax, [rsp+4D0h+BytesReturned]
0x18010617c  mov     [rsp+4D0h+hTemplateFile], rax; lpBytesReturned
0x180106181  lea     rax, [rsp+4D0h+var_488]
0x180106186  mov     [rsp+4D0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18010618e  mov     qword ptr [rsp+4D0h+dwCreationDisposition], rax; lpOutBuffer
0x180106193  call    cs:__imp_DeviceIoControl
0x18010619a  nop     dword ptr [rax+rax+00h]
0x18010619f  test    eax, eax
0x1801061a1  jz      loc_180106071
0x1801061a7  mov     rax, [rsp+4D0h+var_488]
0x1801061ac  cqo
0x1801061ae  idiv    r12
0x1801061b1  mov     [rsp+4D0h+var_488], rax
0x1801061b6  mov     [rsi], eax
0x1801061b8  mov     rdx, rbx
0x1801061bb  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x1801061c0  mov     eax, edi
0x1801061c2  mov     rcx, [rbp+3D0h+var_30]
0x1801061c9  xor     rcx, rsp; StackCookie
0x1801061cc  call    __security_check_cookie
0x1801061d1  mov     rbx, [rsp+4D0h+arg_10]
0x1801061d9  add     rsp, 4B0h
0x1801061e0  pop     r14
0x1801061e2  pop     r12
0x1801061e4  pop     rdi
0x1801061e5  pop     rsi
0x1801061e6  pop     rbp
0x1801061e7  retn
```
