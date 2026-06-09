# LoadStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)

- ea: `0x1800247f8`
- end: `0x180024908`
- name: `?LoadStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(HINSTANCE hModule, HRSRC hResInfo, LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800237dc`

## callees

- `0x1800247f8`
- `0x180028f22`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800248d8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800248d8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024853`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180024853`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180024824`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180024824`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002483c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18002483c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180024812`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180024812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002488e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248e7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800248b2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800248b2`
- `KERNEL32!GlobalLock` at `0x180024868`
- `KERNEL32!GlobalLock` at `0x180024868`
- `KERNEL32!GlobalUnlock` at `0x180024884`
- `KERNEL32!GlobalUnlock` at `0x180024884`

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
0x1800247f8  push    rbx
0x1800247fa  push    rsi
0x1800247fb  push    rdi
0x1800247fc  push    r14
0x1800247fe  sub     rsp, 28h
0x180024802  mov     r14, r8
0x180024805  mov     qword ptr [r8], 0
0x18002480c  mov     rbx, rdx
0x18002480f  mov     rdi, rcx
0x180024812  call    cs:__imp_LoadResource
0x180024818  test    rax, rax
0x18002481b  jz      loc_1800248E7
0x180024821  mov     rcx, rax; hResData
0x180024824  call    cs:__imp_LockResource
0x18002482a  mov     rsi, rax
0x18002482d  test    rax, rax
0x180024830  jz      loc_1800248E0
0x180024836  mov     rdx, rbx; hResInfo
0x180024839  mov     rcx, rdi; hModule
0x18002483c  call    cs:__imp_SizeofResource
0x180024842  test    eax, eax
0x180024844  jz      loc_1800248E7
0x18002484a  mov     edx, eax; dwBytes
0x18002484c  mov     ecx, 2; uFlags
0x180024851  mov     ebx, eax
0x180024853  call    cs:__imp_GlobalAlloc
0x180024859  mov     rdi, rax
0x18002485c  test    rax, rax
0x18002485f  jz      loc_1800248E7
0x180024865  mov     rcx, rax; hMem
0x180024868  call    cs:__imp_GlobalLock
0x18002486e  test    rax, rax
0x180024871  jz      short loc_1800248BC
0x180024873  mov     r8d, ebx; Size
0x180024876  mov     rdx, rsi; Src
0x180024879  mov     rcx, rax; void *
0x18002487c  call    memcpy_0
0x180024881  mov     rcx, rdi; hMem
0x180024884  call    cs:__imp_GlobalUnlock
0x18002488a  test    eax, eax
0x18002488c  jnz     short loc_1800248A7
0x18002488e  call    cs:__imp_GetLastError
0x180024894  mov     ebx, eax
0x180024896  test    eax, eax
0x180024898  jle     short loc_1800248A3
0x18002489a  movzx   ebx, ax
0x18002489d  or      ebx, 80070000h
0x1800248a3  test    ebx, ebx
0x1800248a5  js      short loc_1800248D5
0x1800248a7  mov     r8, r14; ppstm
0x1800248aa  mov     edx, 1; fDeleteOnRelease
0x1800248af  mov     rcx, rdi; hGlobal
0x1800248b2  call    cs:__imp_CreateStreamOnHGlobal
0x1800248b8  mov     ebx, eax
0x1800248ba  jmp     short loc_1800248D1
0x1800248bc  call    cs:__imp_GetLastError
0x1800248c2  mov     ebx, eax
0x1800248c4  test    eax, eax
0x1800248c6  jle     short loc_1800248D1
0x1800248c8  movzx   ebx, ax
0x1800248cb  or      ebx, 80070000h
0x1800248d1  test    ebx, ebx
0x1800248d3  jns     short loc_1800248FC
0x1800248d5  mov     rcx, rdi; hMem
0x1800248d8  call    cs:__imp_GlobalFree
0x1800248de  jmp     short loc_1800248FC
0x1800248e0  mov     ebx, 80004005h
0x1800248e5  jmp     short loc_1800248FC
0x1800248e7  call    cs:__imp_GetLastError
0x1800248ed  mov     ebx, eax
0x1800248ef  test    eax, eax
0x1800248f1  jle     short loc_1800248FC
0x1800248f3  movzx   ebx, ax
0x1800248f6  or      ebx, 80070000h
0x1800248fc  mov     eax, ebx
0x1800248fe  add     rsp, 28h
0x180024902  pop     r14
0x180024904  pop     rdi
0x180024905  pop     rsi
0x180024906  pop     rbx
0x180024907  retn
```
