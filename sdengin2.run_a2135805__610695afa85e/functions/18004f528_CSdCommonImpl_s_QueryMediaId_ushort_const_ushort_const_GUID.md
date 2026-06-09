# CSdCommonImpl::s_QueryMediaId(ushort const *,ushort const *,_GUID *)

- ea: `0x18004f528`
- end: `0x18004f81f`
- name: `?s_QueryMediaId@CSdCommonImpl@@SAJPEBG0PEAU_GUID@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016b54`
- `0x180016ca8`
- `0x18001cf40`
- `0x18001d464`
- `0x18002a20c`
- `0x180032afc`
- `0x1800417b0`
- `0x18004b960`

## callees

- `0x1800083e4`
- `0x18004f528`
- `0x18004f828`
- `0x18004fb78`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009f560`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18004f7bc`
- `KERNEL32!SetFileAttributesW` at `0x18004f7bc`
- `KERNEL32!CreateFileW` at `0x18004f615`
- `KERNEL32!CreateFileW` at `0x18004f70a`
- `KERNEL32!CreateFileW` at `0x18004f615`
- `KERNEL32!CreateFileW` at `0x18004f70a`
- `KERNEL32!GetLastError` at `0x18004f681`
- `KERNEL32!GetLastError` at `0x18004f692`
- `KERNEL32!GetLastError` at `0x18004f681`
- `KERNEL32!GetLastError` at `0x18004f692`
- `KERNEL32!CloseHandle` at `0x18004f78c`
- `KERNEL32!CloseHandle` at `0x18004f7d9`
- `KERNEL32!CloseHandle` at `0x18004f78c`
- `KERNEL32!CloseHandle` at `0x18004f7d9`
- `KERNEL32!GetFileAttributesW` at `0x18004f79f`
- `KERNEL32!GetFileAttributesW` at `0x18004f79f`

## string_xrefs

- `0x18004f552`: `CSdCommonImpl::s_QueryMediaId`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::s_QueryMediaId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  __int64 v6; // rcx
  struct _GUID *v7; // rax
  __int16 v8; // ax
  int MediaIdLocation; // edi
  const WCHAR *v10; // rsi
  __int64 FileW; // rbx
  bool v12; // sf
  __int16 v13; // ax
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD FileAttributesW; // eax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+50h] [rbp-19h] BYREF
  __int16 v20; // [rsp+54h] [rbp-15h]
  __int16 v21; // [rsp+56h] [rbp-13h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "CSdCommonImpl::s_QueryMediaId", 0x862u, 1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  if ( a3 )
  {
    v6 = 16;
    v7 = a3;
    do
    {
      LOBYTE(v7->Data1) = 0;
      v7 = (struct _GUID *)((char *)v7 + 1);
      --v6;
    }
    while ( v6 );
  }
  v8 = 2154;
  if ( !a1 || (v20 = 2154, v8 = 2155, !a3) )
  {
    MediaIdLocation = -2147024809;
    v19 = -2147024809;
LABEL_33:
    v21 = v8;
    goto LABEL_34;
  }
  v19 = 0;
  v20 = 2155;
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdLocation(a1, a2, 1, (struct CBsString *)lpFileName);
  v19 = MediaIdLocation;
  v8 = 2159;
  if ( MediaIdLocation < 0 )
    goto LABEL_33;
  v20 = 2159;
  v10 = lpFileName[0];
  FileW = (__int64)CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW != -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids, v10);
    MediaIdLocation = CSdCommonImpl::s_QueryMediaIdByHandle((HANDLE)FileW, a3);
    v19 = MediaIdLocation;
    v12 = MediaIdLocation < 0;
    v13 = 2165;
    goto LABEL_13;
  }
  if ( GetLastError() != 2 && GetLastError() != 3 )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v14);
    v19 = MediaIdLocation;
    v8 = 2184;
    goto LABEL_33;
  }
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdLocation(a1, 0, 0, (struct CBsString *)lpFileName);
  v19 = MediaIdLocation;
  v8 = 2172;
  if ( MediaIdLocation < 0 )
    goto LABEL_33;
  v20 = 2172;
  v10 = lpFileName[0];
  FileW = (__int64)CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v15);
    v19 = MediaIdLocation;
    v8 = 2175;
    goto LABEL_33;
  }
  v19 = 0;
  v20 = 2175;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids, v10);
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdByHandle((HANDLE)FileW, a3);
  v19 = MediaIdLocation;
  v12 = MediaIdLocation < 0;
  v13 = 2178;
LABEL_13:
  if ( v12 )
  {
    v21 = v13;
LABEL_30:
    if ( FileW )
      CloseHandle((HANDLE)FileW);
    goto LABEL_34;
  }
  v20 = v13;
  if ( FileW )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
  }
  FileAttributesW = GetFileAttributesW(v10);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) == 0 )
    SetFileAttributesW(v10, 1u);
  MediaIdLocation = v19;
  if ( FileW != -1 )
    goto LABEL_30;
LABEL_34:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v19);
  return (unsigned int)MediaIdLocation;
}

```

## disassembly

```asm
0x18004f528  push    rbp
0x18004f52a  push    rbx
0x18004f52b  push    rsi
0x18004f52c  push    rdi
0x18004f52d  push    r14
0x18004f52f  push    r15
0x18004f531  lea     rbp, [rsp-2Fh]
0x18004f536  sub     rsp, 98h
0x18004f53d  mov     r14, r8
0x18004f540  mov     rbx, rdx
0x18004f543  mov     r15, rcx
0x18004f546  mov     r9d, 1; unsigned __int16
0x18004f54c  mov     r8d, 862h; unsigned __int16
0x18004f552  lea     rdx, aCsdcommonimplS_7; "CSdCommonImpl::s_QueryMediaId"
0x18004f559  lea     rcx, [rbp+57h+var_70]; this
0x18004f55d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004f562  lea     rax, qword_1800EE510
0x18004f569  mov     [rbp+57h+lpFileName], rax
0x18004f56d  mov     [rbp+57h+var_78], 0
0x18004f575  test    r14, r14
0x18004f578  jz      short loc_18004F58E
0x18004f57a  mov     ecx, 10h
0x18004f57f  mov     rax, r14
0x18004f582  mov     byte ptr [rax], 0
0x18004f585  inc     rax
0x18004f588  sub     rcx, 1
0x18004f58c  jnz     short loc_18004F582
0x18004f58e  mov     eax, 86Ah
0x18004f593  test    r15, r15
0x18004f596  jnz     short loc_18004F5A5
0x18004f598  mov     edi, 80070057h
0x18004f59d  mov     [rbp+57h+var_70], edi
0x18004f5a0  jmp     loc_18004F7F6
0x18004f5a5  mov     [rbp+57h+var_6C], ax
0x18004f5a9  mov     eax, 86Bh
0x18004f5ae  test    r14, r14
0x18004f5b1  jz      short loc_18004F598
0x18004f5b3  mov     [rbp+57h+var_70], 0
0x18004f5ba  mov     [rbp+57h+var_6C], ax
0x18004f5be  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004f5c2  mov     r8d, 1; int
0x18004f5c8  mov     rdx, rbx; unsigned __int16 *
0x18004f5cb  mov     rcx, r15; unsigned __int16 *
0x18004f5ce  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004f5d3  mov     edi, eax
0x18004f5d5  mov     [rbp+57h+var_70], eax
0x18004f5d8  test    eax, eax
0x18004f5da  mov     eax, 86Fh
0x18004f5df  js      loc_18004F7F6
0x18004f5e5  mov     [rbp+57h+var_6C], ax
0x18004f5e9  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18004f5f2  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004f5fa  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f602  xor     r9d, r9d; lpSecurityAttributes
0x18004f605  mov     edx, 80000000h; dwDesiredAccess
0x18004f60a  lea     r8d, [r9+1]; dwShareMode
0x18004f60e  mov     rsi, [rbp+57h+lpFileName]
0x18004f612  mov     rcx, rsi; lpFileName
0x18004f615  call    cs:__imp_CreateFileW
0x18004f61c  nop     dword ptr [rax+rax+00h]
0x18004f621  mov     rbx, rax
0x18004f624  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f628  jz      short loc_18004F681
0x18004f62a  lea     rax, WPP_GLOBAL_Control
0x18004f631  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f638  cmp     rcx, rax
0x18004f63b  jz      short loc_18004F65B
0x18004f63d  test    byte ptr [rcx+1Ch], 40h
0x18004f641  jz      short loc_18004F65B
0x18004f643  mov     edx, 28h ; '('
0x18004f648  mov     r9, rsi
0x18004f64b  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004f652  mov     rcx, [rcx+10h]
0x18004f656  call    WPP_SF_S
0x18004f65b  mov     rdx, r14; struct _GUID *
0x18004f65e  mov     rcx, rbx; hFile
0x18004f661  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004f666  mov     edi, eax
0x18004f668  mov     [rbp+57h+var_70], eax
0x18004f66b  test    eax, eax
0x18004f66d  mov     eax, 875h
0x18004f672  jns     loc_18004F780
0x18004f678  mov     [rbp+57h+var_6A], ax
0x18004f67c  jmp     loc_18004F7D1
0x18004f681  call    cs:__imp_GetLastError
0x18004f688  nop     dword ptr [rax+rax+00h]
0x18004f68d  cmp     eax, 2
0x18004f690  jz      short loc_18004F6B7
0x18004f692  call    cs:__imp_GetLastError
0x18004f699  nop     dword ptr [rax+rax+00h]
0x18004f69e  cmp     eax, 3
0x18004f6a1  jz      short loc_18004F6B7
0x18004f6a3  call    GetLastFailureAsHRESULT
0x18004f6a8  mov     edi, eax
0x18004f6aa  mov     [rbp+57h+var_70], eax
0x18004f6ad  mov     eax, 888h
0x18004f6b2  jmp     loc_18004F7F6
0x18004f6b7  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004f6bb  xor     r8d, r8d; int
0x18004f6be  xor     edx, edx; unsigned __int16 *
0x18004f6c0  mov     rcx, r15; unsigned __int16 *
0x18004f6c3  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004f6c8  mov     edi, eax
0x18004f6ca  mov     [rbp+57h+var_70], eax
0x18004f6cd  test    eax, eax
0x18004f6cf  mov     eax, 87Ch
0x18004f6d4  js      loc_18004F7F6
0x18004f6da  mov     [rbp+57h+var_6C], ax
0x18004f6de  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18004f6e7  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004f6ef  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f6f7  xor     r9d, r9d; lpSecurityAttributes
0x18004f6fa  mov     edx, 80000000h; dwDesiredAccess
0x18004f6ff  lea     r8d, [r9+1]; dwShareMode
0x18004f703  mov     rsi, [rbp+57h+lpFileName]
0x18004f707  mov     rcx, rsi; lpFileName
0x18004f70a  call    cs:__imp_CreateFileW
0x18004f711  nop     dword ptr [rax+rax+00h]
0x18004f716  mov     rbx, rax
0x18004f719  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f71d  jz      loc_18004F7E7
0x18004f723  mov     [rbp+57h+var_70], 0
0x18004f72a  mov     eax, 87Fh
0x18004f72f  mov     [rbp+57h+var_6C], ax
0x18004f733  lea     rax, WPP_GLOBAL_Control
0x18004f73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f741  cmp     rcx, rax
0x18004f744  jz      short loc_18004F764
0x18004f746  test    byte ptr [rcx+1Ch], 40h
0x18004f74a  jz      short loc_18004F764
0x18004f74c  mov     edx, 29h ; ')'
0x18004f751  mov     r9, rsi
0x18004f754  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004f75b  mov     rcx, [rcx+10h]
0x18004f75f  call    WPP_SF_S
0x18004f764  mov     rdx, r14; struct _GUID *
0x18004f767  mov     rcx, rbx; hFile
0x18004f76a  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004f76f  mov     edi, eax
0x18004f771  mov     [rbp+57h+var_70], eax
0x18004f774  test    eax, eax
0x18004f776  mov     eax, 882h
0x18004f77b  jmp     loc_18004F672
0x18004f780  mov     [rbp+57h+var_6C], ax
0x18004f784  test    rbx, rbx
0x18004f787  jz      short loc_18004F79C
0x18004f789  mov     rcx, rbx; hObject
0x18004f78c  call    cs:__imp_CloseHandle
0x18004f793  nop     dword ptr [rax+rax+00h]
0x18004f798  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004f79c  mov     rcx, rsi; lpFileName
0x18004f79f  call    cs:__imp_GetFileAttributesW
0x18004f7a6  nop     dword ptr [rax+rax+00h]
0x18004f7ab  cmp     eax, 0FFFFFFFFh
0x18004f7ae  jz      short loc_18004F7C8
0x18004f7b0  test    al, 1
0x18004f7b2  jnz     short loc_18004F7C8
0x18004f7b4  mov     edx, 1; dwFileAttributes
0x18004f7b9  mov     rcx, rsi; lpFileName
0x18004f7bc  call    cs:__imp_SetFileAttributesW
0x18004f7c3  nop     dword ptr [rax+rax+00h]
0x18004f7c8  mov     edi, [rbp+57h+var_70]
0x18004f7cb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004f7cf  jz      short loc_18004F7FA
0x18004f7d1  test    rbx, rbx
0x18004f7d4  jz      short loc_18004F7FA
0x18004f7d6  mov     rcx, rbx; hObject
0x18004f7d9  call    cs:__imp_CloseHandle
0x18004f7e0  nop     dword ptr [rax+rax+00h]
0x18004f7e5  jmp     short loc_18004F7FA
0x18004f7e7  call    GetLastFailureAsHRESULT
0x18004f7ec  mov     edi, eax
0x18004f7ee  mov     [rbp+57h+var_70], eax
0x18004f7f1  mov     eax, 87Fh
0x18004f7f6  mov     [rbp+57h+var_6A], ax
0x18004f7fa  lea     rcx, [rbp+57h+lpFileName]; this
0x18004f7fe  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18004f803  lea     rcx, [rbp+57h+var_70]; this
0x18004f807  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004f80c  mov     eax, edi
0x18004f80e  add     rsp, 98h
0x18004f815  pop     r15
0x18004f817  pop     r14
0x18004f819  pop     rdi
0x18004f81a  pop     rsi
0x18004f81b  pop     rbx
0x18004f81c  pop     rbp
0x18004f81d  retn
```
