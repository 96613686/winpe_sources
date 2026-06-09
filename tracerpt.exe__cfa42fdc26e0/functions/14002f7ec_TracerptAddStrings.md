# TracerptAddStrings

- ea: `0x14002f7ec`
- end: `0x14002fa08`
- name: `TracerptAddStrings`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002fba4`

## callees

- `0x14002f7ec`
- `0x14002fa10`
- `0x1400400be`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14002f8f9`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14002f8f9`
- `OLEAUT32!__imp_VariantInit` at `0x14002f81f`
- `OLEAUT32!__imp_VariantInit` at `0x14002f81f`
- `OLEAUT32!__imp_VariantClear` at `0x14002f9a0`
- `OLEAUT32!__imp_VariantClear` at `0x14002f9a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f89a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f89a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14002f91a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x14002f91a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x14002f8ba`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x14002f8ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x14002f904`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x14002f904`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14002f865`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14002f865`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002f890`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x14002f890`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14002f876`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x14002f876`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x14002f834`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x14002f834`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14002f8e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14002f8e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x14002f8cb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x14002f8cb`

## string_xrefs

- `0x14002f827`: `TITLES.XML`

## pseudocode

```c
__int64 __fastcall TracerptAddStrings(__int64 a1)
{
  void *v2; // rdi
  HRSRC ResourceW; // rax
  HRSRC v4; // rbx
  signed int v5; // eax
  int v6; // ebx
  HGLOBAL Resource; // rax
  void *v8; // rsi
  const void *v9; // r14
  DWORD v10; // eax
  signed int LastError; // eax
  DWORD v12; // ebx
  HGLOBAL v13; // rax
  void *v14; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp+38h] BYREF
  __int64 v18; // [rsp+80h] [rbp+40h] BYREF
  __int64 v19; // [rsp+88h] [rbp+48h] BYREF

  ppstm = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v18 = 0;
  v19 = 0;
  VariantInit(&pvarg);
  v2 = 0;
  ResourceW = FindResourceW(0, L"TITLES.XML", (LPCWSTR)0x17);
  v4 = ResourceW;
  if ( ResourceW && (Resource = LoadResource(0, ResourceW), (v8 = Resource) != 0) )
  {
    v9 = LockResource(Resource);
    if ( v9 )
    {
      v10 = SizeofResource(0, v4);
      if ( v10 && (v12 = v10, v13 = GlobalAlloc(2u, v10), (v2 = v13) != 0) && (v14 = GlobalLock(v13)) != 0 )
      {
        memcpy_0(v14, v9, v12);
        GlobalUnlock(v2);
        v6 = CreateStreamOnHGlobal(v2, 1, &ppstm);
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v6 = -2147467259;
    }
    FreeResource(v8);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( v6 >= 0 )
  {
    v6 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, ULONG *))ppstm)(
           ppstm,
           &GUID_00000000_0000_0000_c000_000000000046,
           (ULONG *)&pvarg.cyVal);
    if ( v6 >= 0 )
    {
      pvarg.vt = 13;
      v6 = ((__int64 (__fastcall *)(__int64 *, VARIANTARG *, _QWORD, _QWORD))TracerptCreateXmlDocument)(
             &v19,
             &pvarg,
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 360LL))(v19, &v18);
        if ( v6 >= 0 )
          v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 168LL))(a1, v18, 0);
      }
    }
  }
  else if ( v2 )
  {
    GlobalFree(v2);
  }
  VariantClear(&pvarg);
  if ( ppstm )
  {
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    ppstm = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002f7ec  mov     [rsp-28h+arg_0], rbx
0x14002f7f1  push    rbp
0x14002f7f2  push    rsi
0x14002f7f3  push    rdi
0x14002f7f4  push    r14
0x14002f7f6  push    r15
0x14002f7f8  mov     rbp, rsp
0x14002f7fb  sub     rsp, 40h
0x14002f7ff  xor     eax, eax
0x14002f801  mov     r15, rcx
0x14002f804  xorps   xmm0, xmm0
0x14002f807  mov     qword ptr [rbp+pvarg+10h], rax
0x14002f80b  lea     rcx, [rbp+pvarg]; pvarg
0x14002f80f  mov     [rbp+ppstm], rax
0x14002f813  movups  xmmword ptr [rbp+pvarg], xmm0
0x14002f817  mov     [rbp+arg_10], rax
0x14002f81b  mov     [rbp+arg_18], rax
0x14002f81f  call    cs:__imp_VariantInit
0x14002f825  xor     edi, edi
0x14002f827  lea     rdx, aTitlesXml; "TITLES.XML"
0x14002f82e  xor     ecx, ecx; hModule
0x14002f830  lea     r8d, [rdi+17h]; lpType
0x14002f834  call    cs:__imp_FindResourceW
0x14002f83a  mov     rbx, rax
0x14002f83d  test    rax, rax
0x14002f840  jnz     short loc_14002F860
0x14002f842  call    cs:__imp_GetLastError
0x14002f848  mov     ebx, eax
0x14002f84a  test    eax, eax
0x14002f84c  jle     loc_14002F90A
0x14002f852  movzx   ebx, ax
0x14002f855  or      ebx, 80070000h
0x14002f85b  jmp     loc_14002F90A
0x14002f860  mov     rdx, rbx; hResInfo
0x14002f863  xor     ecx, ecx; hModule
0x14002f865  call    cs:__imp_LoadResource
0x14002f86b  mov     rsi, rax
0x14002f86e  test    rax, rax
0x14002f871  jz      short loc_14002F842
0x14002f873  mov     rcx, rax; hResData
0x14002f876  call    cs:__imp_LockResource
0x14002f87c  mov     r14, rax
0x14002f87f  test    rax, rax
0x14002f882  jnz     short loc_14002F88B
0x14002f884  mov     ebx, 80004005h
0x14002f889  jmp     short loc_14002F901
0x14002f88b  mov     rdx, rbx; hResInfo
0x14002f88e  xor     ecx, ecx; hModule
0x14002f890  call    cs:__imp_SizeofResource
0x14002f896  test    eax, eax
0x14002f898  jnz     short loc_14002F8B1
0x14002f89a  call    cs:__imp_GetLastError
0x14002f8a0  mov     ebx, eax
0x14002f8a2  test    eax, eax
0x14002f8a4  jle     short loc_14002F901
0x14002f8a6  movzx   ebx, ax
0x14002f8a9  or      ebx, 80070000h
0x14002f8af  jmp     short loc_14002F901
0x14002f8b1  mov     edx, eax; dwBytes
0x14002f8b3  mov     ecx, 2; uFlags
0x14002f8b8  mov     ebx, eax
0x14002f8ba  call    cs:__imp_GlobalAlloc
0x14002f8c0  mov     rdi, rax
0x14002f8c3  test    rax, rax
0x14002f8c6  jz      short loc_14002F89A
0x14002f8c8  mov     rcx, rax; hMem
0x14002f8cb  call    cs:__imp_GlobalLock
0x14002f8d1  test    rax, rax
0x14002f8d4  jz      short loc_14002F89A
0x14002f8d6  mov     r8d, ebx; Size
0x14002f8d9  mov     rdx, r14; Src
0x14002f8dc  mov     rcx, rax; void *
0x14002f8df  call    memcpy_0
0x14002f8e4  mov     rcx, rdi; hMem
0x14002f8e7  call    cs:__imp_GlobalUnlock
0x14002f8ed  lea     r8, [rbp+ppstm]; ppstm
0x14002f8f1  mov     edx, 1; fDeleteOnRelease
0x14002f8f6  mov     rcx, rdi; hGlobal
0x14002f8f9  call    cs:__imp_CreateStreamOnHGlobal
0x14002f8ff  mov     ebx, eax
0x14002f901  mov     rcx, rsi; hResData
0x14002f904  call    cs:__imp_FreeResource
0x14002f90a  test    ebx, ebx
0x14002f90c  jns     short loc_14002F922
0x14002f90e  test    rdi, rdi
0x14002f911  jz      loc_14002F99C
0x14002f917  mov     rcx, rdi; hMem
0x14002f91a  call    cs:__imp_GlobalFree
0x14002f920  jmp     short loc_14002F99C
0x14002f922  mov     rcx, [rbp+ppstm]
0x14002f926  lea     r8, [rbp+pvarg+8]
0x14002f92a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14002f931  mov     rax, [rcx]
0x14002f934  mov     rax, [rax]
0x14002f937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f93c  mov     ebx, eax
0x14002f93e  test    eax, eax
0x14002f940  js      short loc_14002F99C
0x14002f942  mov     eax, 0Dh
0x14002f947  lea     rdx, [rbp+pvarg]
0x14002f94b  xor     r9d, r9d
0x14002f94e  mov     word ptr [rbp+pvarg], ax
0x14002f952  xor     r8d, r8d
0x14002f955  lea     rcx, [rbp+arg_18]
0x14002f959  call    TracerptCreateXmlDocument
0x14002f95e  mov     ebx, eax
0x14002f960  test    eax, eax
0x14002f962  js      short loc_14002F99C
0x14002f964  mov     rcx, [rbp+arg_18]
0x14002f968  lea     rdx, [rbp+arg_10]
0x14002f96c  mov     rax, [rcx]
0x14002f96f  mov     rax, [rax+168h]
0x14002f976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f97b  mov     ebx, eax
0x14002f97d  test    eax, eax
0x14002f97f  js      short loc_14002F99C
0x14002f981  mov     rax, [r15]
0x14002f984  xor     r8d, r8d
0x14002f987  mov     rdx, [rbp+arg_10]
0x14002f98b  mov     rcx, r15
0x14002f98e  mov     rax, [rax+0A8h]
0x14002f995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f99a  mov     ebx, eax
0x14002f99c  lea     rcx, [rbp+pvarg]; pvarg
0x14002f9a0  call    cs:__imp_VariantClear
0x14002f9a6  mov     rcx, [rbp+ppstm]
0x14002f9aa  test    rcx, rcx
0x14002f9ad  jz      short loc_14002F9C3
0x14002f9af  mov     rax, [rcx]
0x14002f9b2  mov     rax, [rax+10h]
0x14002f9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f9bb  mov     [rbp+ppstm], 0
0x14002f9c3  mov     rcx, [rbp+arg_10]
0x14002f9c7  test    rcx, rcx
0x14002f9ca  jz      short loc_14002F9E0
0x14002f9cc  mov     rax, [rcx]
0x14002f9cf  mov     rax, [rax+10h]
0x14002f9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f9d8  mov     [rbp+arg_10], 0
0x14002f9e0  mov     rcx, [rbp+arg_18]
0x14002f9e4  test    rcx, rcx
0x14002f9e7  jz      short loc_14002F9F5
0x14002f9e9  mov     rax, [rcx]
0x14002f9ec  mov     rax, [rax+10h]
0x14002f9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f9f5  mov     eax, ebx
0x14002f9f7  mov     rbx, [rsp+40h+arg_0]
0x14002f9fc  add     rsp, 40h
0x14002fa00  pop     r15
0x14002fa02  pop     r14
0x14002fa04  pop     rdi
0x14002fa05  pop     rsi
0x14002fa06  pop     rbp
0x14002fa07  retn
```
