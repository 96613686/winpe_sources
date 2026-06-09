# CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(ushort const *,ushort const *,int,_GUID *)

- ea: `0x18004dbd0`
- end: `0x18004dd78`
- name: `?s_QueryMediaIdFromSpecificLocation@CSdCommonImpl@@SAJPEBG0HPEAU_GUID@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800381f8`

## callees

- `0x18004da58`
- `0x18004dbd0`
- `0x18004dd80`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18004dd26`
- `KERNEL32!SetFileAttributesW` at `0x18004dd26`
- `KERNEL32!CreateFileW` at `0x18004dcb2`
- `KERNEL32!CreateFileW` at `0x18004dcb2`
- `KERNEL32!CloseHandle` at `0x18004dd00`
- `KERNEL32!CloseHandle` at `0x18004dd3d`
- `KERNEL32!CloseHandle` at `0x18004dd00`
- `KERNEL32!CloseHandle` at `0x18004dd3d`
- `KERNEL32!GetFileAttributesW` at `0x18004dd0e`
- `KERNEL32!GetFileAttributesW` at `0x18004dd0e`

## string_xrefs

- `0x18004dbf6`: `CSdCommonImpl::s_QueryMediaIdFromSpecificLocation`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        struct _GUID *a4)
{
  __int64 v7; // rcx
  struct _GUID *v8; // rax
  __int16 v9; // ax
  int MediaIdLocation; // edi
  __int64 v11; // rcx
  __int64 FileW; // rbx
  DWORD FileAttributesW; // eax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-9h] BYREF
  __int16 v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+56h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v16,
    "CSdCommonImpl::s_QueryMediaIdFromSpecificLocation",
    2211,
    1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  if ( a4 )
  {
    v7 = 16;
    v8 = a4;
    do
    {
      LOBYTE(v8->Data1) = 0;
      v8 = (struct _GUID *)((char *)v8 + 1);
      --v7;
    }
    while ( v7 );
  }
  v9 = 2218;
  if ( !a1 || (v17 = 2218, v9 = 2219, !a4) )
  {
    MediaIdLocation = -2147024809;
    v16 = -2147024809;
LABEL_20:
    v18 = v9;
    goto LABEL_21;
  }
  v16 = 0;
  v17 = 2219;
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdLocation(a1, 0, a3, (struct CBsString *)lpFileName);
  v16 = MediaIdLocation;
  v9 = 2221;
  if ( MediaIdLocation < 0 )
    goto LABEL_20;
  v17 = 2221;
  FileW = (__int64)CreateFileW(lpFileName[0], 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v11);
    v16 = MediaIdLocation;
    v9 = 2224;
    goto LABEL_20;
  }
  v16 = 0;
  v17 = 2224;
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdByHandle((HANDLE)FileW, a4);
  v16 = MediaIdLocation;
  if ( MediaIdLocation < 0 )
  {
    v18 = 2226;
LABEL_17:
    if ( FileW )
      CloseHandle((HANDLE)FileW);
    goto LABEL_21;
  }
  v17 = 2226;
  if ( FileW )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
  }
  FileAttributesW = GetFileAttributesW(lpFileName[0]);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) == 0 )
    SetFileAttributesW(lpFileName[0], 1u);
  MediaIdLocation = v16;
  if ( FileW != -1 )
    goto LABEL_17;
LABEL_21:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)MediaIdLocation;
}

```

## disassembly

```asm
0x18004dbd0  push    rbp
0x18004dbd2  push    rbx
0x18004dbd3  push    rsi
0x18004dbd4  push    rdi
0x18004dbd5  lea     rbp, [rsp-3Fh]
0x18004dbda  sub     rsp, 98h
0x18004dbe1  mov     rsi, r9
0x18004dbe4  mov     edi, r8d
0x18004dbe7  mov     rbx, rcx
0x18004dbea  mov     r9d, 1; unsigned __int16
0x18004dbf0  mov     r8d, 8A3h; unsigned __int16
0x18004dbf6  lea     rdx, aCsdcommonimplS; "CSdCommonImpl::s_QueryMediaIdFromSpecif"...
0x18004dbfd  lea     rcx, [rbp+57h+var_60]; this
0x18004dc01  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004dc06  lea     rax, qword_1800E8530
0x18004dc0d  mov     [rbp+57h+lpFileName], rax
0x18004dc11  mov     [rbp+57h+var_68], 0
0x18004dc19  test    rsi, rsi
0x18004dc1c  jz      short loc_18004DC32
0x18004dc1e  mov     ecx, 10h
0x18004dc23  mov     rax, rsi
0x18004dc26  mov     byte ptr [rax], 0
0x18004dc29  inc     rax
0x18004dc2c  sub     rcx, 1
0x18004dc30  jnz     short loc_18004DC26
0x18004dc32  mov     eax, 8AAh
0x18004dc37  test    rbx, rbx
0x18004dc3a  jnz     short loc_18004DC49
0x18004dc3c  mov     edi, 80070057h
0x18004dc41  mov     [rbp+57h+var_60], edi
0x18004dc44  jmp     loc_18004DD54
0x18004dc49  mov     [rbp+57h+var_5C], ax
0x18004dc4d  mov     eax, 8ABh
0x18004dc52  test    rsi, rsi
0x18004dc55  jz      short loc_18004DC3C
0x18004dc57  mov     [rbp+57h+var_60], 0
0x18004dc5e  mov     [rbp+57h+var_5C], ax
0x18004dc62  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004dc66  mov     r8d, edi; int
0x18004dc69  xor     edx, edx; unsigned __int16 *
0x18004dc6b  mov     rcx, rbx; unsigned __int16 *
0x18004dc6e  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004dc73  mov     edi, eax
0x18004dc75  mov     [rbp+57h+var_60], eax
0x18004dc78  test    eax, eax
0x18004dc7a  mov     eax, 8ADh
0x18004dc7f  js      loc_18004DD54
0x18004dc85  mov     [rbp+57h+var_5C], ax
0x18004dc89  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18004dc92  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004dc9a  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004dca2  xor     r9d, r9d; lpSecurityAttributes
0x18004dca5  mov     edx, 80000000h; dwDesiredAccess
0x18004dcaa  lea     r8d, [r9+1]; dwShareMode
0x18004dcae  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004dcb2  call    cs:__imp_CreateFileW
0x18004dcb8  mov     rbx, rax
0x18004dcbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004dcbf  jz      loc_18004DD45
0x18004dcc5  mov     [rbp+57h+var_60], 0
0x18004dccc  mov     eax, 8B0h
0x18004dcd1  mov     [rbp+57h+var_5C], ax
0x18004dcd5  mov     rdx, rsi; struct _GUID *
0x18004dcd8  mov     rcx, rbx; hFile
0x18004dcdb  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004dce0  mov     edi, eax
0x18004dce2  mov     [rbp+57h+var_60], eax
0x18004dce5  test    eax, eax
0x18004dce7  mov     eax, 8B2h
0x18004dcec  jns     short loc_18004DCF4
0x18004dcee  mov     [rbp+57h+var_5A], ax
0x18004dcf2  jmp     short loc_18004DD35
0x18004dcf4  mov     [rbp+57h+var_5C], ax
0x18004dcf8  test    rbx, rbx
0x18004dcfb  jz      short loc_18004DD0A
0x18004dcfd  mov     rcx, rbx; hObject
0x18004dd00  call    cs:__imp_CloseHandle
0x18004dd06  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004dd0a  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004dd0e  call    cs:__imp_GetFileAttributesW
0x18004dd14  cmp     eax, 0FFFFFFFFh
0x18004dd17  jz      short loc_18004DD2C
0x18004dd19  test    al, 1
0x18004dd1b  jnz     short loc_18004DD2C
0x18004dd1d  mov     edx, 1; dwFileAttributes
0x18004dd22  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004dd26  call    cs:__imp_SetFileAttributesW
0x18004dd2c  mov     edi, [rbp+57h+var_60]
0x18004dd2f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004dd33  jz      short loc_18004DD58
0x18004dd35  test    rbx, rbx
0x18004dd38  jz      short loc_18004DD58
0x18004dd3a  mov     rcx, rbx; hObject
0x18004dd3d  call    cs:__imp_CloseHandle
0x18004dd43  jmp     short loc_18004DD58
0x18004dd45  call    GetLastFailureAsHRESULT
0x18004dd4a  mov     edi, eax
0x18004dd4c  mov     [rbp+57h+var_60], eax
0x18004dd4f  mov     eax, 8B0h
0x18004dd54  mov     [rbp+57h+var_5A], ax
0x18004dd58  lea     rcx, [rbp+57h+lpFileName]; this
0x18004dd5c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18004dd61  lea     rcx, [rbp+57h+var_60]; this
0x18004dd65  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004dd6a  mov     eax, edi
0x18004dd6c  add     rsp, 98h
0x18004dd73  pop     rdi
0x18004dd74  pop     rsi
0x18004dd75  pop     rbx
0x18004dd76  pop     rbp
0x18004dd77  retn
```
