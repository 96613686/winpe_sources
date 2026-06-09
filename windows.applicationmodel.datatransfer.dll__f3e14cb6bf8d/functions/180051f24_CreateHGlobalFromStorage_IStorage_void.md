# _CreateHGlobalFromStorage(IStorage *,void * *)

- ea: `0x180051f24`
- end: `0x1800520a5`
- name: `?_CreateHGlobalFromStorage@@YAJPEAUIStorage@@PEAPEAX@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct IStorage *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019f64`

## callees

- `0x180051f24`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052016`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052016`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051fdd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051fdd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052053`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052021`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180051f53`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180051f53`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180051f7b`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180051f7b`

## string_xrefs

- `0x180051fd6`: `ole32.dll`

## pseudocode

```c
__int64 __fastcall _CreateHGlobalFromStorage(struct IStorage *a1, void **a2)
{
  int v4; // ebx
  HMODULE Library; // rax
  HMODULE v6; // rdi
  signed int v7; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  IStorage *v10; // rcx
  LPLOCKBYTES v11; // rcx
  IStorage *ppstgOpen; // [rsp+58h] [rbp+28h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+60h] [rbp+30h] BYREF

  *a2 = 0;
  pplkbyt = 0;
  v4 = CreateILockBytesOnHGlobal(0, 1, &pplkbyt);
  if ( v4 >= 0 )
  {
    ppstgOpen = 0;
    v4 = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, IStorage *))a1->lpVtbl->CopyTo)(
             a1,
             0,
             0,
             0,
             ppstgOpen);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(IStorage *, _QWORD))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 0);
        if ( v4 >= 0 )
        {
          Library = LoadLibraryExW(L"ole32.dll", 0, 0);
          v6 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "GetHGlobalFromILockBytes");
            if ( ProcAddress )
            {
              v4 = ((__int64 (__fastcall *)(LPLOCKBYTES, void **))ProcAddress)(pplkbyt, a2);
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError > 0 )
                v4 = (unsigned __int16)LastError | 0x80070000;
              if ( v4 >= 0 )
                v4 = -2147467259;
            }
            FreeLibrary(v6);
          }
          else
          {
            v7 = GetLastError();
            v4 = v7;
            if ( v7 > 0 )
              v4 = (unsigned __int16)v7 | 0x80070000;
            if ( v4 >= 0 )
              v4 = -2147467259;
          }
        }
      }
    }
    v10 = ppstgOpen;
    if ( ppstgOpen )
    {
      ppstgOpen = 0;
      ((void (__fastcall *)(IStorage *))v10->lpVtbl->Release)(v10);
    }
  }
  v11 = pplkbyt;
  if ( pplkbyt )
  {
    pplkbyt = 0;
    ((void (__fastcall *)(LPLOCKBYTES))v11->lpVtbl->Release)(v11);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180051f24  mov     [rsp-18h+arg_0], rbx
0x180051f29  push    rbp
0x180051f2a  push    rsi
0x180051f2b  push    rdi
0x180051f2c  mov     rbp, rsp
0x180051f2f  sub     rsp, 30h
0x180051f33  mov     rsi, rdx
0x180051f36  mov     rdi, rcx
0x180051f39  mov     qword ptr [rdx], 0
0x180051f40  mov     [rbp+pplkbyt], 0
0x180051f48  lea     r8, [rbp+pplkbyt]; pplkbyt
0x180051f4c  mov     edx, 1; fDeleteOnRelease
0x180051f51  xor     ecx, ecx; hGlobal
0x180051f53  call    cs:__imp_CreateILockBytesOnHGlobal
0x180051f59  mov     ebx, eax
0x180051f5b  test    eax, eax
0x180051f5d  js      loc_180052078
0x180051f63  mov     [rbp+ppstgOpen], 0
0x180051f6b  lea     r9, [rbp+ppstgOpen]; ppstgOpen
0x180051f6f  xor     r8d, r8d; reserved
0x180051f72  mov     edx, 1012h; grfMode
0x180051f77  mov     rcx, [rbp+pplkbyt]; plkbyt
0x180051f7b  call    cs:__imp_StgCreateDocfileOnILockBytes
0x180051f81  mov     ebx, eax
0x180051f83  test    eax, eax
0x180051f85  js      loc_18005205A
0x180051f8b  mov     rcx, [rbp+ppstgOpen]
0x180051f8f  mov     rax, [rdi]
0x180051f92  mov     [rsp+30h+var_10], rcx
0x180051f97  xor     r9d, r9d
0x180051f9a  xor     r8d, r8d
0x180051f9d  xor     edx, edx
0x180051f9f  mov     rcx, rdi
0x180051fa2  mov     rax, [rax+38h]
0x180051fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fab  mov     ebx, eax
0x180051fad  test    eax, eax
0x180051faf  js      loc_18005205A
0x180051fb5  mov     rcx, [rbp+ppstgOpen]
0x180051fb9  mov     rax, [rcx]
0x180051fbc  xor     edx, edx
0x180051fbe  mov     rax, [rax+48h]
0x180051fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fc7  mov     ebx, eax
0x180051fc9  test    eax, eax
0x180051fcb  js      loc_18005205A
0x180051fd1  xor     r8d, r8d; dwFlags
0x180051fd4  xor     edx, edx; hFile
0x180051fd6  lea     rcx, LibFileName; "ole32.dll"
0x180051fdd  call    cs:__imp_LoadLibraryExW
0x180051fe3  mov     rdi, rax
0x180051fe6  test    rax, rax
0x180051fe9  jnz     short loc_18005200C
0x180051feb  call    cs:__imp_GetLastError
0x180051ff1  mov     ebx, eax
0x180051ff3  test    eax, eax
0x180051ff5  jle     short loc_180052000
0x180051ff7  movzx   ebx, ax
0x180051ffa  or      ebx, 80070000h
0x180052000  mov     eax, 80004005h
0x180052005  test    ebx, ebx
0x180052007  cmovns  ebx, eax
0x18005200a  jmp     short loc_18005205A
0x18005200c  lea     rdx, aGethglobalfrom; "GetHGlobalFromILockBytes"
0x180052013  mov     rcx, rdi; hModule
0x180052016  call    cs:__imp_GetProcAddress
0x18005201c  test    rax, rax
0x18005201f  jnz     short loc_180052042
0x180052021  call    cs:__imp_GetLastError
0x180052027  mov     ebx, eax
0x180052029  test    eax, eax
0x18005202b  jle     short loc_180052036
0x18005202d  movzx   ebx, ax
0x180052030  or      ebx, 80070000h
0x180052036  mov     eax, 80004005h
0x18005203b  test    ebx, ebx
0x18005203d  cmovns  ebx, eax
0x180052040  jmp     short loc_180052050
0x180052042  mov     rdx, rsi
0x180052045  mov     rcx, [rbp+pplkbyt]
0x180052049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005204e  mov     ebx, eax
0x180052050  mov     rcx, rdi; hLibModule
0x180052053  call    cs:__imp_FreeLibrary
0x180052059  nop
0x18005205a  mov     rcx, [rbp+ppstgOpen]
0x18005205e  test    rcx, rcx
0x180052061  jz      short loc_180052078
0x180052063  mov     [rbp+ppstgOpen], 0
0x18005206b  mov     rax, [rcx]
0x18005206e  mov     rax, [rax+10h]
0x180052072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052077  nop
0x180052078  mov     rcx, [rbp+pplkbyt]
0x18005207c  test    rcx, rcx
0x18005207f  jz      short loc_180052096
0x180052081  mov     [rbp+pplkbyt], 0
0x180052089  mov     rax, [rcx]
0x18005208c  mov     rax, [rax+10h]
0x180052090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052095  nop
0x180052096  mov     eax, ebx
0x180052098  mov     rbx, [rsp+30h+arg_0]
0x18005209d  add     rsp, 30h
0x1800520a1  pop     rdi
0x1800520a2  pop     rsi
0x1800520a3  pop     rbp
0x1800520a4  retn
```
