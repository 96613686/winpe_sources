# CSdSafeguard::_OverWriteMediaId(ushort const *,_GUID,ushort const *,int)

- ea: `0x180037aa8`
- end: `0x180037d7e`
- name: `?_OverWriteMediaId@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z`
- size: `726`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800381f8`

## callees

- `0x180009ac8`
- `0x180037aa8`
- `0x18004dd80`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180037c65`
- `KERNEL32!SetFilePointer` at `0x180037c65`
- `KERNEL32!SetFileAttributesW` at `0x180037b95`
- `KERNEL32!SetFileAttributesW` at `0x180037d16`
- `KERNEL32!SetFileAttributesW` at `0x180037b95`
- `KERNEL32!SetFileAttributesW` at `0x180037d16`
- `KERNEL32!CreateFileW` at `0x180037bee`
- `KERNEL32!CreateFileW` at `0x180037bee`
- `KERNEL32!CloseHandle` at `0x180037d03`
- `KERNEL32!CloseHandle` at `0x180037d2e`
- `KERNEL32!CloseHandle` at `0x180037d03`
- `KERNEL32!CloseHandle` at `0x180037d2e`
- `KERNEL32!WriteFile` at `0x180037caf`
- `KERNEL32!WriteFile` at `0x180037caf`

## string_xrefs

- `0x180037aeb`: `CSdSafeguard::_OverWriteMediaId`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_OverWriteMediaId(
        CSdSafeguard *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int16 v8; // ax
  int MediaIdLocation; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 FileW; // rbx
  __int16 v13; // ax
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-B4h]
  __int16 v20; // [rsp+4Eh] [rbp-B2h]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Buffer; // [rsp+90h] [rbp-70h] BYREF
  __int64 v23; // [rsp+94h] [rbp-6Ch] BYREF
  int v24; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 v25[256]; // [rsp+A0h] [rbp-60h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CSdSafeguard::_OverWriteMediaId", 430, 1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  NumberOfBytesWritten = 0;
  Buffer = 0;
  memset_0(&v23, 0, 0x20Cu);
  v8 = 437;
  if ( !a2 || (v19 = 437, v8 = 438, !a4) )
  {
    MediaIdLocation = -2147024809;
    v18 = -2147024809;
LABEL_22:
    v20 = v8;
    goto LABEL_23;
  }
  v18 = 0;
  v19 = 438;
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdLocation(a2, 0, a5, (struct CBsString *)lpFileName);
  v18 = MediaIdLocation;
  v8 = 440;
  if ( MediaIdLocation < 0 )
    goto LABEL_22;
  v19 = 440;
  if ( !SetFileAttributesW(lpFileName[0], 0x80u) )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v10);
    v18 = MediaIdLocation;
    v8 = 445;
    goto LABEL_22;
  }
  v18 = 0;
  v19 = 445;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v11);
    v18 = MediaIdLocation;
    v8 = 451;
    goto LABEL_22;
  }
  v18 = 0;
  v19 = 451;
  Buffer = a3->Data1;
  v23 = *(_QWORD *)&a3->Data2;
  v24 = *(_DWORD *)&a3->Data4[4];
  MediaIdLocation = StringCchCopyW(v25, 0x100u, a4);
  v18 = MediaIdLocation;
  v13 = 457;
  if ( MediaIdLocation < 0 )
    goto LABEL_9;
  v19 = 457;
  if ( SetFilePointer((HANDLE)FileW, 0, 0, 0) == -1 )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v14);
    v18 = MediaIdLocation;
    v13 = 460;
LABEL_9:
    v20 = v13;
LABEL_19:
    if ( FileW )
      CloseHandle((HANDLE)FileW);
    goto LABEL_23;
  }
  v18 = 0;
  v19 = 460;
  if ( !WriteFile((HANDLE)FileW, &Buffer, 0x210u, &NumberOfBytesWritten, 0) )
  {
    MediaIdLocation = GetLastFailureAsHRESULT(v15);
    v18 = MediaIdLocation;
    v13 = 462;
    goto LABEL_9;
  }
  v19 = 462;
  v13 = 463;
  if ( NumberOfBytesWritten != 528 )
  {
    MediaIdLocation = -2130706379;
    v18 = -2130706379;
    goto LABEL_9;
  }
  v18 = 0;
  v19 = 463;
  if ( FileW )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
  }
  SetFileAttributesW(lpFileName[0], 1u);
  MediaIdLocation = v18;
  if ( FileW != -1 )
    goto LABEL_19;
LABEL_23:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return (unsigned int)MediaIdLocation;
}

```

## disassembly

```asm
0x180037aa8  push    rbp
0x180037aaa  push    rbx
0x180037aab  push    rdi
0x180037aac  push    r14
0x180037aae  push    r15
0x180037ab0  lea     rbp, [rsp-1B0h]
0x180037ab8  sub     rsp, 2B0h
0x180037abf  mov     rax, cs:__security_cookie
0x180037ac6  xor     rax, rsp
0x180037ac9  mov     [rbp+1D0h+var_30], rax
0x180037ad0  mov     r14, r9
0x180037ad3  mov     r15, r8
0x180037ad6  mov     rbx, rdx
0x180037ad9  mov     edi, [rbp+1D0h+arg_20]
0x180037adf  mov     r9d, 1; unsigned __int16
0x180037ae5  mov     r8d, 1AEh; unsigned __int16
0x180037aeb  lea     rdx, aCsdsafeguardOv; "CSdSafeguard::_OverWriteMediaId"
0x180037af2  lea     rcx, [rsp+2D0h+var_288]; this
0x180037af7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180037afc  lea     rax, qword_1800E8530
0x180037b03  mov     [rbp+1D0h+lpFileName], rax
0x180037b07  mov     [rbp+1D0h+var_248], 0
0x180037b0f  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x180037b17  mov     [rbp+1D0h+Buffer], 0
0x180037b1e  xor     edx, edx; Val
0x180037b20  mov     r8d, 20Ch; Size
0x180037b26  lea     rcx, [rbp+1D0h+var_23C]; void *
0x180037b2a  call    memset_0
0x180037b2f  mov     eax, 1B5h
0x180037b34  test    rbx, rbx
0x180037b37  jnz     short loc_180037B47
0x180037b39  mov     edi, 80070057h
0x180037b3e  mov     [rsp+2D0h+var_288], edi
0x180037b42  jmp     loc_180037D46
0x180037b47  mov     [rsp+2D0h+var_284], ax
0x180037b4c  mov     eax, 1B6h
0x180037b51  test    r14, r14
0x180037b54  jz      short loc_180037B39
0x180037b56  mov     [rsp+2D0h+var_288], 0
0x180037b5e  mov     [rsp+2D0h+var_284], ax
0x180037b63  lea     r9, [rbp+1D0h+lpFileName]; struct CBsString *
0x180037b67  mov     r8d, edi; int
0x180037b6a  xor     edx, edx; unsigned __int16 *
0x180037b6c  mov     rcx, rbx; unsigned __int16 *
0x180037b6f  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x180037b74  mov     edi, eax
0x180037b76  mov     [rsp+2D0h+var_288], eax
0x180037b7a  test    eax, eax
0x180037b7c  mov     eax, 1B8h
0x180037b81  js      loc_180037D46
0x180037b87  mov     [rsp+2D0h+var_284], ax
0x180037b8c  mov     edx, 80h; dwFileAttributes
0x180037b91  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180037b95  call    cs:__imp_SetFileAttributesW
0x180037b9b  test    eax, eax
0x180037b9d  jnz     short loc_180037BB4
0x180037b9f  call    GetLastFailureAsHRESULT
0x180037ba4  mov     edi, eax
0x180037ba6  mov     [rsp+2D0h+var_288], eax
0x180037baa  mov     eax, 1BDh
0x180037baf  jmp     loc_180037D46
0x180037bb4  mov     [rsp+2D0h+var_288], 0
0x180037bbc  mov     eax, 1BDh
0x180037bc1  mov     [rsp+2D0h+var_284], ax
0x180037bc6  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x180037bcf  mov     [rsp+2D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180037bd7  mov     [rsp+2D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180037bdf  xor     r9d, r9d; lpSecurityAttributes
0x180037be2  xor     r8d, r8d; dwShareMode
0x180037be5  mov     edx, 0C0000000h; dwDesiredAccess
0x180037bea  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180037bee  call    cs:__imp_CreateFileW
0x180037bf4  mov     rbx, rax
0x180037bf7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037bfb  jz      loc_180037D36
0x180037c01  mov     [rsp+2D0h+var_288], 0
0x180037c09  mov     eax, 1C3h
0x180037c0e  mov     [rsp+2D0h+var_284], ax
0x180037c13  mov     eax, [r15]
0x180037c16  mov     [rbp+1D0h+Buffer], eax
0x180037c19  movsd   xmm0, qword ptr [r15+4]
0x180037c1f  movsd   [rbp+1D0h+var_23C], xmm0
0x180037c24  mov     eax, [r15+0Ch]
0x180037c28  mov     [rbp+1D0h+var_234], eax
0x180037c2b  mov     r8, r14; unsigned __int16 *
0x180037c2e  mov     edx, 100h; unsigned __int64
0x180037c33  lea     rcx, [rbp+1D0h+var_230]; unsigned __int16 *
0x180037c37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037c3c  mov     edi, eax
0x180037c3e  mov     [rsp+2D0h+var_288], eax
0x180037c42  test    eax, eax
0x180037c44  mov     eax, 1C9h
0x180037c49  jns     short loc_180037C55
0x180037c4b  mov     [rsp+2D0h+var_282], ax
0x180037c50  jmp     loc_180037D26
0x180037c55  mov     [rsp+2D0h+var_284], ax
0x180037c5a  xor     r9d, r9d; dwMoveMethod
0x180037c5d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180037c60  xor     edx, edx; lDistanceToMove
0x180037c62  mov     rcx, rbx; hFile
0x180037c65  call    cs:__imp_SetFilePointer
0x180037c6b  cmp     eax, 0FFFFFFFFh
0x180037c6e  jnz     short loc_180037C82
0x180037c70  call    GetLastFailureAsHRESULT
0x180037c75  mov     edi, eax
0x180037c77  mov     [rsp+2D0h+var_288], eax
0x180037c7b  mov     eax, 1CCh
0x180037c80  jmp     short loc_180037C4B
0x180037c82  mov     [rsp+2D0h+var_288], 0
0x180037c8a  mov     eax, 1CCh
0x180037c8f  mov     [rsp+2D0h+var_284], ax
0x180037c94  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x180037c9d  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037ca2  lea     edi, [rax+44h]
0x180037ca5  mov     r8d, edi; nNumberOfBytesToWrite
0x180037ca8  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x180037cac  mov     rcx, rbx; hFile
0x180037caf  call    cs:__imp_WriteFile
0x180037cb5  test    eax, eax
0x180037cb7  jnz     short loc_180037CCB
0x180037cb9  call    GetLastFailureAsHRESULT
0x180037cbe  mov     edi, eax
0x180037cc0  mov     [rsp+2D0h+var_288], eax
0x180037cc4  mov     eax, 1CEh
0x180037cc9  jmp     short loc_180037C4B
0x180037ccb  mov     eax, 1CEh
0x180037cd0  mov     [rsp+2D0h+var_284], ax
0x180037cd5  mov     eax, 1CFh
0x180037cda  cmp     [rsp+2D0h+NumberOfBytesWritten], edi
0x180037cde  jz      short loc_180037CEE
0x180037ce0  mov     edi, 81000035h
0x180037ce5  mov     [rsp+2D0h+var_288], edi
0x180037ce9  jmp     loc_180037C4B
0x180037cee  mov     [rsp+2D0h+var_288], 0
0x180037cf6  mov     [rsp+2D0h+var_284], ax
0x180037cfb  test    rbx, rbx
0x180037cfe  jz      short loc_180037D0D
0x180037d00  mov     rcx, rbx; hObject
0x180037d03  call    cs:__imp_CloseHandle
0x180037d09  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180037d0d  mov     edx, 1; dwFileAttributes
0x180037d12  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180037d16  call    cs:__imp_SetFileAttributesW
0x180037d1c  mov     edi, [rsp+2D0h+var_288]
0x180037d20  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180037d24  jz      short loc_180037D4B
0x180037d26  test    rbx, rbx
0x180037d29  jz      short loc_180037D4B
0x180037d2b  mov     rcx, rbx; hObject
0x180037d2e  call    cs:__imp_CloseHandle
0x180037d34  jmp     short loc_180037D4B
0x180037d36  call    GetLastFailureAsHRESULT
0x180037d3b  mov     edi, eax
0x180037d3d  mov     [rsp+2D0h+var_288], eax
0x180037d41  mov     eax, 1C3h
0x180037d46  mov     [rsp+2D0h+var_282], ax
0x180037d4b  lea     rcx, [rbp+1D0h+lpFileName]; this
0x180037d4f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180037d54  lea     rcx, [rsp+2D0h+var_288]; this
0x180037d59  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180037d5e  mov     eax, edi
0x180037d60  mov     rcx, [rbp+1D0h+var_30]
0x180037d67  xor     rcx, rsp; StackCookie
0x180037d6a  call    __security_check_cookie
0x180037d6f  add     rsp, 2B0h
0x180037d76  pop     r15
0x180037d78  pop     r14
0x180037d7a  pop     rdi
0x180037d7b  pop     rbx
0x180037d7c  pop     rbp
0x180037d7d  retn
```
