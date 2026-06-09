# CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(ushort const *,ushort const *,int,_GUID *)

- ea: `0x18004f9a8`
- end: `0x18004fb6f`
- name: `?s_QueryMediaIdFromSpecificLocation@CSdCommonImpl@@SAJPEBG0HPEAU_GUID@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039778`

## callees

- `0x18004f828`
- `0x18004f9a8`
- `0x18004fb78`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009f560`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18004fb10`
- `KERNEL32!SetFileAttributesW` at `0x18004fb10`
- `KERNEL32!CreateFileW` at `0x18004fa8a`
- `KERNEL32!CreateFileW` at `0x18004fa8a`
- `KERNEL32!CloseHandle` at `0x18004fade`
- `KERNEL32!CloseHandle` at `0x18004fb2d`
- `KERNEL32!CloseHandle` at `0x18004fade`
- `KERNEL32!CloseHandle` at `0x18004fb2d`
- `KERNEL32!GetFileAttributesW` at `0x18004faf2`
- `KERNEL32!GetFileAttributesW` at `0x18004faf2`

## string_xrefs

- `0x18004f9ce`: `CSdCommonImpl::s_QueryMediaIdFromSpecificLocation`

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
    0x8A3u,
    1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x18004f9a8  push    rbp
0x18004f9aa  push    rbx
0x18004f9ab  push    rsi
0x18004f9ac  push    rdi
0x18004f9ad  lea     rbp, [rsp-3Fh]
0x18004f9b2  sub     rsp, 98h
0x18004f9b9  mov     rsi, r9
0x18004f9bc  mov     edi, r8d
0x18004f9bf  mov     rbx, rcx
0x18004f9c2  mov     r9d, 1; unsigned __int16
0x18004f9c8  mov     r8d, 8A3h; unsigned __int16
0x18004f9ce  lea     rdx, aCsdcommonimplS; "CSdCommonImpl::s_QueryMediaIdFromSpecif"...
0x18004f9d5  lea     rcx, [rbp+57h+var_60]; this
0x18004f9d9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004f9de  lea     rax, qword_1800EE510
0x18004f9e5  mov     [rbp+57h+lpFileName], rax
0x18004f9e9  mov     [rbp+57h+var_68], 0
0x18004f9f1  test    rsi, rsi
0x18004f9f4  jz      short loc_18004FA0A
0x18004f9f6  mov     ecx, 10h
0x18004f9fb  mov     rax, rsi
0x18004f9fe  mov     byte ptr [rax], 0
0x18004fa01  inc     rax
0x18004fa04  sub     rcx, 1
0x18004fa08  jnz     short loc_18004F9FE
0x18004fa0a  mov     eax, 8AAh
0x18004fa0f  test    rbx, rbx
0x18004fa12  jnz     short loc_18004FA21
0x18004fa14  mov     edi, 80070057h
0x18004fa19  mov     [rbp+57h+var_60], edi
0x18004fa1c  jmp     loc_18004FB4A
0x18004fa21  mov     [rbp+57h+var_5C], ax
0x18004fa25  mov     eax, 8ABh
0x18004fa2a  test    rsi, rsi
0x18004fa2d  jz      short loc_18004FA14
0x18004fa2f  mov     [rbp+57h+var_60], 0
0x18004fa36  mov     [rbp+57h+var_5C], ax
0x18004fa3a  lea     r9, [rbp+57h+lpFileName]; struct CBsString *
0x18004fa3e  mov     r8d, edi; int
0x18004fa41  xor     edx, edx; unsigned __int16 *
0x18004fa43  mov     rcx, rbx; unsigned __int16 *
0x18004fa46  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x18004fa4b  mov     edi, eax
0x18004fa4d  mov     [rbp+57h+var_60], eax
0x18004fa50  test    eax, eax
0x18004fa52  mov     eax, 8ADh
0x18004fa57  js      loc_18004FB4A
0x18004fa5d  mov     [rbp+57h+var_5C], ax
0x18004fa61  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18004fa6a  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004fa72  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004fa7a  xor     r9d, r9d; lpSecurityAttributes
0x18004fa7d  mov     edx, 80000000h; dwDesiredAccess
0x18004fa82  lea     r8d, [r9+1]; dwShareMode
0x18004fa86  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004fa8a  call    cs:__imp_CreateFileW
0x18004fa91  nop     dword ptr [rax+rax+00h]
0x18004fa96  mov     rbx, rax
0x18004fa99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004fa9d  jz      loc_18004FB3B
0x18004faa3  mov     [rbp+57h+var_60], 0
0x18004faaa  mov     eax, 8B0h
0x18004faaf  mov     [rbp+57h+var_5C], ax
0x18004fab3  mov     rdx, rsi; struct _GUID *
0x18004fab6  mov     rcx, rbx; hFile
0x18004fab9  call    ?s_QueryMediaIdByHandle@CSdCommonImpl@@SAJPEAXPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdByHandle(void *,_GUID *)
0x18004fabe  mov     edi, eax
0x18004fac0  mov     [rbp+57h+var_60], eax
0x18004fac3  test    eax, eax
0x18004fac5  mov     eax, 8B2h
0x18004faca  jns     short loc_18004FAD2
0x18004facc  mov     [rbp+57h+var_5A], ax
0x18004fad0  jmp     short loc_18004FB25
0x18004fad2  mov     [rbp+57h+var_5C], ax
0x18004fad6  test    rbx, rbx
0x18004fad9  jz      short loc_18004FAEE
0x18004fadb  mov     rcx, rbx; hObject
0x18004fade  call    cs:__imp_CloseHandle
0x18004fae5  nop     dword ptr [rax+rax+00h]
0x18004faea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004faee  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004faf2  call    cs:__imp_GetFileAttributesW
0x18004faf9  nop     dword ptr [rax+rax+00h]
0x18004fafe  cmp     eax, 0FFFFFFFFh
0x18004fb01  jz      short loc_18004FB1C
0x18004fb03  test    al, 1
0x18004fb05  jnz     short loc_18004FB1C
0x18004fb07  mov     edx, 1; dwFileAttributes
0x18004fb0c  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18004fb10  call    cs:__imp_SetFileAttributesW
0x18004fb17  nop     dword ptr [rax+rax+00h]
0x18004fb1c  mov     edi, [rbp+57h+var_60]
0x18004fb1f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004fb23  jz      short loc_18004FB4E
0x18004fb25  test    rbx, rbx
0x18004fb28  jz      short loc_18004FB4E
0x18004fb2a  mov     rcx, rbx; hObject
0x18004fb2d  call    cs:__imp_CloseHandle
0x18004fb34  nop     dword ptr [rax+rax+00h]
0x18004fb39  jmp     short loc_18004FB4E
0x18004fb3b  call    GetLastFailureAsHRESULT
0x18004fb40  mov     edi, eax
0x18004fb42  mov     [rbp+57h+var_60], eax
0x18004fb45  mov     eax, 8B0h
0x18004fb4a  mov     [rbp+57h+var_5A], ax
0x18004fb4e  lea     rcx, [rbp+57h+lpFileName]; this
0x18004fb52  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18004fb57  lea     rcx, [rbp+57h+var_60]; this
0x18004fb5b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004fb60  mov     eax, edi
0x18004fb62  add     rsp, 98h
0x18004fb69  pop     rdi
0x18004fb6a  pop     rsi
0x18004fb6b  pop     rbx
0x18004fb6c  pop     rbp
0x18004fb6d  retn
```
