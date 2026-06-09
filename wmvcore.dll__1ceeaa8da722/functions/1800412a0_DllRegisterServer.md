# DllRegisterServer

- ea: `0x1800412a0`
- end: `0x1800414da`
- name: `DllRegisterServer`
- size: `570`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x18003f7c0`
- `0x18003f800`
- `0x1800411a8`
- `0x1800412a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180041392`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180041392`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180041325`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180041325`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x1800414ad`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x1800414ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004130e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004130e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180041349`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180041349`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800412c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800412c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041449`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041449`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180041481`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180041481`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800413d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800413d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041362`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004149e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004149e`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800412f4`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800412f4`

## string_xrefs

- `0x1800412c0`: `wmvcore.dll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HMODULE ModuleHandleW; // rax
  HMODULE v1; // rbx
  HRESULT v2; // ebx
  HRSRC ResourceW; // rax
  HRSRC v4; // rdi
  HGLOBAL Resource; // rax
  void *v6; // rsi
  const void *v7; // rbp
  DWORD v8; // r14d
  UINT SystemDirectoryW; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r9d
  int i; // ebx
  unsigned __int64 v14; // rcx
  signed int LastError; // eax
  HANDLE FileW; // rax
  void *v17; // rdi
  BOOL v18; // eax
  int v19; // ecx
  __int64 v21; // [rsp+0h] [rbp-298h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  ModuleHandleW = GetModuleHandleW(L"wmvcore.dll");
  v1 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    ResourceW = FindResourceW(ModuleHandleW, (LPCWSTR)0xC8, L"PRXFILE");
    v4 = ResourceW;
    if ( ResourceW )
    {
      Resource = LoadResource(v1, ResourceW);
      v6 = Resource;
      if ( Resource )
      {
        v7 = LockResource(Resource);
        if ( v7 )
        {
          v8 = SizeofResource(v1, v4);
          SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
          if ( SystemDirectoryW )
          {
            for ( i = SystemDirectoryW - 7; i >= 0; --i )
            {
              LODWORD(v4) = i;
              if ( !(unsigned int)o__wcsnicmp(i, v6, L"\\system", &Buffer[i], 7) )
              {
                v14 = 2LL * i + 2;
                if ( v14 >= 0x208 )
                  _report_rangecheckfailure(i, v6, v10, v14, v11);
                *(WCHAR *)((char *)Buffer + v14) = 0;
                break;
              }
            }
            v2 = sub_1800411A8((_DWORD)v4, (_DWORD)v6, v10, (unsigned int)Buffer, v11, v12, v21);
            if ( v2 < 0 )
              goto LABEL_26;
            if ( GetFileAttributesW(Buffer) != -1 )
            {
              v2 = 0;
              goto LABEL_26;
            }
            LastError = GetLastError();
            if ( LastError != 2 )
            {
              if ( LastError > 0 )
                v2 = (unsigned __int16)LastError | 0x80070000;
              else
                v2 = LastError;
              goto LABEL_26;
            }
            FileW = CreateFileW(Buffer, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
            v17 = FileW;
            if ( FileW != (HANDLE)-1LL )
            {
              NumberOfBytesWritten = 0;
              v18 = WriteFile(FileW, v7, v8, &NumberOfBytesWritten, 0);
              v19 = v2;
              if ( !v18 )
                v19 = -2147467259;
              v2 = v19;
              CloseHandle(v17);
              goto LABEL_26;
            }
          }
        }
        v2 = -2147467259;
LABEL_26:
        FreeResource(v6);
        return v2;
      }
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x1800412a0  push    rbx
0x1800412a2  push    rbp
0x1800412a3  push    rsi
0x1800412a4  push    rdi
0x1800412a5  push    r14
0x1800412a7  sub     rsp, 270h
0x1800412ae  mov     rax, cs:__security_cookie
0x1800412b5  xor     rax, rsp
0x1800412b8  mov     [rsp+298h+var_38], rax
0x1800412c0  lea     rcx, aWmvcoreDll_0; "wmvcore.dll"
0x1800412c7  call    cs:GetModuleHandleW
0x1800412ce  nop     dword ptr [rax+rax+00h]
0x1800412d3  mov     rbx, rax
0x1800412d6  test    rax, rax
0x1800412d9  jnz     short loc_1800412E5
0x1800412db  mov     ebx, 80004005h
0x1800412e0  jmp     loc_1800414B9
0x1800412e5  lea     r8, Type; "PRXFILE"
0x1800412ec  mov     edx, 0C8h; lpName
0x1800412f1  mov     rcx, rbx; hModule
0x1800412f4  call    cs:FindResourceW
0x1800412fb  nop     dword ptr [rax+rax+00h]
0x180041300  mov     rdi, rax
0x180041303  test    rax, rax
0x180041306  jz      short loc_1800412DB
0x180041308  mov     rdx, rax; hResInfo
0x18004130b  mov     rcx, rbx; hModule
0x18004130e  call    cs:LoadResource
0x180041315  nop     dword ptr [rax+rax+00h]
0x18004131a  mov     rsi, rax
0x18004131d  test    rax, rax
0x180041320  jz      short loc_1800412DB
0x180041322  mov     rcx, rax; hResData
0x180041325  call    cs:LockResource
0x18004132c  nop     dword ptr [rax+rax+00h]
0x180041331  mov     rbp, rax
0x180041334  test    rax, rax
0x180041337  jnz     short loc_180041343
0x180041339  mov     ebx, 80004005h
0x18004133e  jmp     loc_1800414AA
0x180041343  mov     rdx, rdi; hResInfo
0x180041346  mov     rcx, rbx; hModule
0x180041349  call    cs:SizeofResource
0x180041350  nop     dword ptr [rax+rax+00h]
0x180041355  mov     edx, 104h; uSize
0x18004135a  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x18004135f  mov     r14d, eax
0x180041362  call    cs:GetSystemDirectoryW
0x180041369  nop     dword ptr [rax+rax+00h]
0x18004136e  test    eax, eax
0x180041370  jz      short loc_180041339
0x180041372  lea     ebx, [rax-7]
0x180041375  test    ebx, ebx
0x180041377  js      short loc_1800413BE
0x180041379  movsxd  rdi, ebx
0x18004137c  lea     rcx, [rsp+298h+Buffer]
0x180041381  mov     r8d, 7
0x180041387  lea     rdx, aSystem; "\\system"
0x18004138e  lea     rcx, [rcx+rdi*2]
0x180041392  call    cs:_o__wcsnicmp
0x180041399  nop     dword ptr [rax+rax+00h]
0x18004139e  test    eax, eax
0x1800413a0  jz      short loc_1800413A6
0x1800413a2  dec     ebx
0x1800413a4  jmp     short loc_180041375
0x1800413a6  lea     rcx, ds:2[rdi*2]
0x1800413ae  cmp     rcx, 208h
0x1800413b5  jnb     short loc_1800413EF
0x1800413b7  xor     eax, eax
0x1800413b9  mov     [rsp+rcx+298h+Buffer], ax
0x1800413be  lea     rcx, [rsp+298h+Buffer]
0x1800413c3  call    sub_1800411A8
0x1800413c8  mov     ebx, eax
0x1800413ca  test    eax, eax
0x1800413cc  js      loc_1800414AA
0x1800413d2  lea     rcx, [rsp+298h+Buffer]; lpFileName
0x1800413d7  call    cs:GetFileAttributesW
0x1800413de  nop     dword ptr [rax+rax+00h]
0x1800413e3  cmp     eax, 0FFFFFFFFh
0x1800413e6  jz      short loc_1800413F5
0x1800413e8  xor     ebx, ebx
0x1800413ea  jmp     loc_1800414AA
0x1800413ef  call    __report_rangecheckfailure
0x1800413f5  call    cs:GetLastError
0x1800413fc  nop     dword ptr [rax+rax+00h]
0x180041401  cmp     eax, 2
0x180041404  jz      short loc_18004141F
0x180041406  test    eax, eax
0x180041408  jg      short loc_180041411
0x18004140a  mov     ebx, eax
0x18004140c  jmp     loc_1800414AA
0x180041411  movzx   ebx, ax
0x180041414  or      ebx, 80070000h
0x18004141a  jmp     loc_1800414AA
0x18004141f  xor     r9d, r9d; lpSecurityAttributes
0x180041422  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x18004142b  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180041433  lea     rcx, [rsp+298h+Buffer]; lpFileName
0x180041438  mov     edx, 0C0000000h; dwDesiredAccess
0x18004143d  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x180041445  lea     r8d, [r9+1]; dwShareMode
0x180041449  call    cs:CreateFileW
0x180041450  nop     dword ptr [rax+rax+00h]
0x180041455  mov     rdi, rax; StackCookie
0x180041458  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004145c  jz      loc_180041339
0x180041462  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180041467  mov     [rsp+298h+NumberOfBytesWritten], 0
0x18004146f  mov     r8d, r14d; nNumberOfBytesToWrite
0x180041472  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x18004147b  mov     rdx, rbp; lpBuffer
0x18004147e  mov     rcx, rax; hFile
0x180041481  call    cs:WriteFile
0x180041488  nop     dword ptr [rax+rax+00h]
0x18004148d  mov     ecx, ebx
0x18004148f  test    eax, eax
0x180041491  mov     ebx, 80004005h
0x180041496  cmovz   ecx, ebx
0x180041499  mov     ebx, ecx
0x18004149b  mov     rcx, rdi; hObject
0x18004149e  call    cs:CloseHandle
0x1800414a5  nop     dword ptr [rax+rax+00h]
0x1800414aa  mov     rcx, rsi; hResData
0x1800414ad  call    cs:FreeResource
0x1800414b4  nop     dword ptr [rax+rax+00h]
0x1800414b9  mov     eax, ebx
0x1800414bb  mov     rcx, [rsp+298h+var_38]
0x1800414c3  xor     rcx, rsp
0x1800414c6  call    __security_check_cookie
0x1800414cb  add     rsp, 270h
0x1800414d2  pop     r14
0x1800414d4  pop     rdi
0x1800414d5  pop     rsi
0x1800414d6  pop     rbp
0x1800414d7  pop     rbx
0x1800414d8  retn
```
