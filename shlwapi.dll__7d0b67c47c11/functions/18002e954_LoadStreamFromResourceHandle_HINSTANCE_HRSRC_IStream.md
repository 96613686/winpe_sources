# LoadStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)

- ea: `0x18002e954`
- end: `0x18002ea64`
- name: `?LoadStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(HINSTANCE hModule, HRSRC hResInfo, LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800321ec`

## callees

- `0x18002e954`
- `0x1800369d1`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002e96e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18002e96e`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002e980`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18002e980`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002e998`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002e998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e9ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ea43`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002ea34`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002ea34`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002e9af`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002e9af`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002e9e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002e9e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002e9c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002e9c4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002ea0e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002ea0e`

## pseudocode

```c
__int64 __fastcall LoadStreamFromResourceHandle(HINSTANCE hModule, HRSRC hResInfo, LPSTREAM *ppstm)
{
  HGLOBAL Resource; // rax
  const void *v7; // rsi
  DWORD v8; // eax
  DWORD v9; // ebx
  HGLOBAL v10; // rax
  void *v11; // rdi
  void *v12; // rax
  signed int LastError; // eax
  int StreamOnHGlobal; // ebx
  signed int v15; // eax
  signed int v16; // eax

  *ppstm = 0;
  Resource = LoadResource(hModule, hResInfo);
  if ( !Resource )
    goto LABEL_16;
  v7 = LockResource(Resource);
  if ( !v7 )
    return (unsigned int)-2147467259;
  v8 = SizeofResource(hModule, hResInfo);
  if ( v8 && (v9 = v8, v10 = GlobalAlloc(2u, v8), (v11 = v10) != 0) )
  {
    v12 = GlobalLock(v10);
    if ( v12 )
    {
      memcpy_0(v12, v7, v9);
      if ( !GlobalUnlock(v11) )
      {
        LastError = GetLastError();
        StreamOnHGlobal = LastError;
        if ( LastError > 0 )
          StreamOnHGlobal = (unsigned __int16)LastError | 0x80070000;
        if ( StreamOnHGlobal < 0 )
          goto LABEL_14;
      }
      StreamOnHGlobal = CreateStreamOnHGlobal(v11, 1, ppstm);
    }
    else
    {
      v15 = GetLastError();
      StreamOnHGlobal = v15;
      if ( v15 > 0 )
        StreamOnHGlobal = (unsigned __int16)v15 | 0x80070000;
    }
    if ( StreamOnHGlobal < 0 )
LABEL_14:
      GlobalFree(v11);
  }
  else
  {
LABEL_16:
    v16 = GetLastError();
    StreamOnHGlobal = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18002e954  push    rbx
0x18002e956  push    rsi
0x18002e957  push    rdi
0x18002e958  push    r14
0x18002e95a  sub     rsp, 28h
0x18002e95e  mov     r14, r8
0x18002e961  mov     qword ptr [r8], 0
0x18002e968  mov     rbx, rdx
0x18002e96b  mov     rdi, rcx
0x18002e96e  call    cs:__imp_LoadResource
0x18002e974  test    rax, rax
0x18002e977  jz      loc_18002EA43
0x18002e97d  mov     rcx, rax; hResData
0x18002e980  call    cs:__imp_LockResource
0x18002e986  mov     rsi, rax
0x18002e989  test    rax, rax
0x18002e98c  jz      loc_18002EA3C
0x18002e992  mov     rdx, rbx; hResInfo
0x18002e995  mov     rcx, rdi; hModule
0x18002e998  call    cs:__imp_SizeofResource
0x18002e99e  test    eax, eax
0x18002e9a0  jz      loc_18002EA43
0x18002e9a6  mov     edx, eax; dwBytes
0x18002e9a8  mov     ecx, 2; uFlags
0x18002e9ad  mov     ebx, eax
0x18002e9af  call    cs:__imp_GlobalAlloc
0x18002e9b5  mov     rdi, rax
0x18002e9b8  test    rax, rax
0x18002e9bb  jz      loc_18002EA43
0x18002e9c1  mov     rcx, rax; hMem
0x18002e9c4  call    cs:__imp_GlobalLock
0x18002e9ca  test    rax, rax
0x18002e9cd  jz      short loc_18002EA18
0x18002e9cf  mov     r8d, ebx; Size
0x18002e9d2  mov     rdx, rsi; Src
0x18002e9d5  mov     rcx, rax; void *
0x18002e9d8  call    memcpy_0
0x18002e9dd  mov     rcx, rdi; hMem
0x18002e9e0  call    cs:__imp_GlobalUnlock
0x18002e9e6  test    eax, eax
0x18002e9e8  jnz     short loc_18002EA03
0x18002e9ea  call    cs:__imp_GetLastError
0x18002e9f0  mov     ebx, eax
0x18002e9f2  test    eax, eax
0x18002e9f4  jle     short loc_18002E9FF
0x18002e9f6  movzx   ebx, ax
0x18002e9f9  or      ebx, 80070000h
0x18002e9ff  test    ebx, ebx
0x18002ea01  js      short loc_18002EA31
0x18002ea03  mov     r8, r14; ppstm
0x18002ea06  mov     edx, 1; fDeleteOnRelease
0x18002ea0b  mov     rcx, rdi; hGlobal
0x18002ea0e  call    cs:__imp_CreateStreamOnHGlobal
0x18002ea14  mov     ebx, eax
0x18002ea16  jmp     short loc_18002EA2D
0x18002ea18  call    cs:__imp_GetLastError
0x18002ea1e  mov     ebx, eax
0x18002ea20  test    eax, eax
0x18002ea22  jle     short loc_18002EA2D
0x18002ea24  movzx   ebx, ax
0x18002ea27  or      ebx, 80070000h
0x18002ea2d  test    ebx, ebx
0x18002ea2f  jns     short loc_18002EA58
0x18002ea31  mov     rcx, rdi; hMem
0x18002ea34  call    cs:__imp_GlobalFree
0x18002ea3a  jmp     short loc_18002EA58
0x18002ea3c  mov     ebx, 80004005h
0x18002ea41  jmp     short loc_18002EA58
0x18002ea43  call    cs:__imp_GetLastError
0x18002ea49  mov     ebx, eax
0x18002ea4b  test    eax, eax
0x18002ea4d  jle     short loc_18002EA58
0x18002ea4f  movzx   ebx, ax
0x18002ea52  or      ebx, 80070000h
0x18002ea58  mov     eax, ebx
0x18002ea5a  add     rsp, 28h
0x18002ea5e  pop     r14
0x18002ea60  pop     rdi
0x18002ea61  pop     rsi
0x18002ea62  pop     rbx
0x18002ea63  retn
```
