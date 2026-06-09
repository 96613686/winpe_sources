# CSdCommonImpl::s_QueryMediaId(ushort const *,ushort const *,_GUID *)

- ea: `0x18004d78c`
- end: `0x18004da52`
- name: `?s_QueryMediaId@CSdCommonImpl@@SAJPEBG0PEAU_GUID@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800161d8`
- `0x18001632c`
- `0x18001c468`
- `0x18001c978`
- `0x18002919c`
- `0x1800317e8`
- `0x18003ffd8`
- `0x180049cf0`

## callees

- `0x180008240`
- `0x18004d78c`
- `0x18004da58`
- `0x18004dd80`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18004d9fc`
- `KERNEL32!SetFileAttributesW` at `0x18004d9fc`
- `KERNEL32!CreateFileW` at `0x18004d879`
- `KERNEL32!CreateFileW` at `0x18004d95c`
- `KERNEL32!CreateFileW` at `0x18004d879`
- `KERNEL32!CreateFileW` at `0x18004d95c`
- `KERNEL32!GetLastError` at `0x18004d8df`
- `KERNEL32!GetLastError` at `0x18004d8ea`
- `KERNEL32!GetLastError` at `0x18004d8df`
- `KERNEL32!GetLastError` at `0x18004d8ea`
- `KERNEL32!CloseHandle` at `0x18004d9d8`
- `KERNEL32!CloseHandle` at `0x18004da13`
- `KERNEL32!CloseHandle` at `0x18004d9d8`
- `KERNEL32!CloseHandle` at `0x18004da13`
- `KERNEL32!GetFileAttributesW` at `0x18004d9e5`
- `KERNEL32!GetFileAttributesW` at `0x18004d9e5`

## string_xrefs

- `0x18004d7b6`: `CSdCommonImpl::s_QueryMediaId`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v19, "CSdCommonImpl::s_QueryMediaId", 2146, 1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
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
0x18004d78c  push    rbp
0x18004d78e  push    rbx
0x18004d78f  push    rsi
0x18004d790  push    rdi
0x18004d791  push    r14
0x18004d793  push    r15
0x18004d795  lea     rbp, [rsp-2Fh]
0x18004d79a  sub     rsp, 98h
0x18004d7a1  mov     r14, r8
0x18004d7a4  mov     rbx, rdx
0x18004d7a7  mov     r15, rcx
0x18004d7aa  mov     r9d, 1; unsigned __int16
0x18004d7b0  mov     r8d, 862h; unsigned __int16
0x18004d7b6  lea     rdx, aCsdcommonimplS_7; "CSdCommonImpl::s_QueryMediaId"
0x18004d7bd  lea     rcx, [rbp+57h+var_70]; this
0x18004d7c1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004d7c6  lea     rax, qword_1800E8530
0x18004d7cd  mov     [rbp+57h+lpFileName], rax
0x18004d7d1  mov     [rbp+57h+var_78], 0
0x18004d7d9  test    r14, r14
0x18004d7dc  jz      short loc_18004D7F2
0x18004d7de  mov     ecx, 10h
0x18004d7e3  mov     rax, r14
0x18004d7e6  mov     byte ptr [rax], 0
0x18004d7e9  inc     rax
0x18004d7ec  sub     rcx, 1
0x18004d7f0  jnz     short loc_18004D7E6
0x18004d7f2  mov     eax, 86Ah
0x18004d7f7  test    r15, r15
0x18004d7fa  jnz     short loc_18004D809
0x18004d7fc  mov     edi, 80070057h
0x18004d801  mov     [rbp+57h+var_70], edi
0x18004d804  jmp     loc_18004DA2A
0x18004d809  mov     [rbp+57h+var_6C], ax
0x18004d80d  mov     eax, 86Bh
0x18004d812  test    r14, r14
0x18004d815  jz      short loc_18004D7FC
0x18004d817  mov     [rbp+57h+var_70], 0
0x18004d81e  mov     [rbp+57h+var_6C], ax
0x18004d822  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004d826  mov     r8d, 1; int
0x18004d82c  mov     rdx, rbx; unsigned __int16 *
0x18004d82f  mov     rcx, r15; unsigned __int16 *
0x18004d832  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004d837  mov     edi, eax
0x18004d839  mov     [rbp+57h+var_70], eax
0x18004d83c  test    eax, eax
0x18004d83e  mov     eax, 86Fh
0x18004d843  js      loc_18004DA2A
0x18004d849  mov     [rbp+57h+var_6C], ax
0x18004d84d  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18004d856  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004d85e  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004d866  xor     r9d, r9d; lpSecurityAttributes
0x18004d869  mov     edx, 80000000h; dwDesiredAccess
0x18004d86e  lea     r8d, [r9+1]; dwShareMode
0x18004d872  mov     rsi, [rbp+57h+lpFileName]
0x18004d876  mov     rcx, rsi; lpFileName
0x18004d879  call    cs:__imp_CreateFileW
0x18004d87f  mov     rbx, rax
0x18004d882  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004d886  jz      short loc_18004D8DF
0x18004d888  lea     rax, WPP_GLOBAL_Control
0x18004d88f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d896  cmp     rcx, rax
0x18004d899  jz      short loc_18004D8B9
0x18004d89b  test    byte ptr [rcx+1Ch], 40h
0x18004d89f  jz      short loc_18004D8B9
0x18004d8a1  mov     edx, 28h ; '('
0x18004d8a6  mov     r9, rsi
0x18004d8a9  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004d8b0  mov     rcx, [rcx+10h]
0x18004d8b4  call    WPP_SF_S
0x18004d8b9  mov     rdx, r14; struct _GUID *
0x18004d8bc  mov     rcx, rbx; hFile
0x18004d8bf  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004d8c4  mov     edi, eax
0x18004d8c6  mov     [rbp+57h+var_70], eax
0x18004d8c9  test    eax, eax
0x18004d8cb  mov     eax, 875h
0x18004d8d0  jns     loc_18004D9CC
0x18004d8d6  mov     [rbp+57h+var_6A], ax
0x18004d8da  jmp     loc_18004DA0B
0x18004d8df  call    cs:__imp_GetLastError
0x18004d8e5  cmp     eax, 2
0x18004d8e8  jz      short loc_18004D909
0x18004d8ea  call    cs:__imp_GetLastError
0x18004d8f0  cmp     eax, 3
0x18004d8f3  jz      short loc_18004D909
0x18004d8f5  call    GetLastFailureAsHRESULT
0x18004d8fa  mov     edi, eax
0x18004d8fc  mov     [rbp+57h+var_70], eax
0x18004d8ff  mov     eax, 888h
0x18004d904  jmp     loc_18004DA2A
0x18004d909  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004d90d  xor     r8d, r8d; int
0x18004d910  xor     edx, edx; unsigned __int16 *
0x18004d912  mov     rcx, r15; unsigned __int16 *
0x18004d915  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004d91a  mov     edi, eax
0x18004d91c  mov     [rbp+57h+var_70], eax
0x18004d91f  test    eax, eax
0x18004d921  mov     eax, 87Ch
0x18004d926  js      loc_18004DA2A
0x18004d92c  mov     [rbp+57h+var_6C], ax
0x18004d930  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x18004d939  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004d941  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004d949  xor     r9d, r9d; lpSecurityAttributes
0x18004d94c  mov     edx, 80000000h; dwDesiredAccess
0x18004d951  lea     r8d, [r9+1]; dwShareMode
0x18004d955  mov     rsi, [rbp+57h+lpFileName]
0x18004d959  mov     rcx, rsi; lpFileName
0x18004d95c  call    cs:__imp_CreateFileW
0x18004d962  mov     rbx, rax
0x18004d965  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004d969  jz      loc_18004DA1B
0x18004d96f  mov     [rbp+57h+var_70], 0
0x18004d976  mov     eax, 87Fh
0x18004d97b  mov     [rbp+57h+var_6C], ax
0x18004d97f  lea     rax, WPP_GLOBAL_Control
0x18004d986  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d98d  cmp     rcx, rax
0x18004d990  jz      short loc_18004D9B0
0x18004d992  test    byte ptr [rcx+1Ch], 40h
0x18004d996  jz      short loc_18004D9B0
0x18004d998  mov     edx, 29h ; ')'
0x18004d99d  mov     r9, rsi
0x18004d9a0  lea     r8, WPP_5da7dc0cc0c43b39d796028c0b72d66e_Traceguids
0x18004d9a7  mov     rcx, [rcx+10h]
0x18004d9ab  call    WPP_SF_S
0x18004d9b0  mov     rdx, r14; struct _GUID *
0x18004d9b3  mov     rcx, rbx; hFile
0x18004d9b6  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004d9bb  mov     edi, eax
0x18004d9bd  mov     [rbp+57h+var_70], eax
0x18004d9c0  test    eax, eax
0x18004d9c2  mov     eax, 882h
0x18004d9c7  jmp     loc_18004D8D0
0x18004d9cc  mov     [rbp+57h+var_6C], ax
0x18004d9d0  test    rbx, rbx
0x18004d9d3  jz      short loc_18004D9E2
0x18004d9d5  mov     rcx, rbx; hObject
0x18004d9d8  call    cs:__imp_CloseHandle
0x18004d9de  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004d9e2  mov     rcx, rsi; lpFileName
0x18004d9e5  call    cs:__imp_GetFileAttributesW
0x18004d9eb  cmp     eax, 0FFFFFFFFh
0x18004d9ee  jz      short loc_18004DA02
0x18004d9f0  test    al, 1
0x18004d9f2  jnz     short loc_18004DA02
0x18004d9f4  mov     edx, 1; dwFileAttributes
0x18004d9f9  mov     rcx, rsi; lpFileName
0x18004d9fc  call    cs:__imp_SetFileAttributesW
0x18004da02  mov     edi, [rbp+57h+var_70]
0x18004da05  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004da09  jz      short loc_18004DA2E
0x18004da0b  test    rbx, rbx
0x18004da0e  jz      short loc_18004DA2E
0x18004da10  mov     rcx, rbx; hObject
0x18004da13  call    cs:__imp_CloseHandle
0x18004da19  jmp     short loc_18004DA2E
0x18004da1b  call    GetLastFailureAsHRESULT
0x18004da20  mov     edi, eax
0x18004da22  mov     [rbp+57h+var_70], eax
0x18004da25  mov     eax, 87Fh
0x18004da2a  mov     [rbp+57h+var_6A], ax
0x18004da2e  lea     rcx, [rbp+57h+lpFileName]; this
0x18004da32  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18004da37  lea     rcx, [rbp+57h+var_70]; this
0x18004da3b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004da40  mov     eax, edi
0x18004da42  add     rsp, 98h
0x18004da49  pop     r15
0x18004da4b  pop     r14
0x18004da4d  pop     rdi
0x18004da4e  pop     rsi
0x18004da4f  pop     rbx
0x18004da50  pop     rbp
0x18004da51  retn
```
