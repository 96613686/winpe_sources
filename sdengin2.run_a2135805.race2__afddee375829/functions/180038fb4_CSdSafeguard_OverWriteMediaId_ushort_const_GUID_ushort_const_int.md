# CSdSafeguard::_OverWriteMediaId(ushort const *,_GUID,ushort const *,int)

- ea: `0x180038fb4`
- end: `0x1800392b8`
- name: `?_OverWriteMediaId@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z`
- size: `772`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039778`

## callees

- `0x180009d44`
- `0x180038fb4`
- `0x18004fb78`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18003917d`
- `KERNEL32!SetFilePointer` at `0x18003917d`
- `KERNEL32!SetFileAttributesW` at `0x1800390a1`
- `KERNEL32!SetFileAttributesW` at `0x180039243`
- `KERNEL32!SetFileAttributesW` at `0x1800390a1`
- `KERNEL32!SetFileAttributesW` at `0x180039243`
- `KERNEL32!CreateFileW` at `0x180039100`
- `KERNEL32!CreateFileW` at `0x180039100`
- `KERNEL32!CloseHandle` at `0x18003922a`
- `KERNEL32!CloseHandle` at `0x180039261`
- `KERNEL32!CloseHandle` at `0x18003922a`
- `KERNEL32!CloseHandle` at `0x180039261`
- `KERNEL32!WriteFile` at `0x1800391cd`
- `KERNEL32!WriteFile` at `0x1800391cd`

## string_xrefs

- `0x180038ff7`: `CSdSafeguard::_OverWriteMediaId`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CSdSafeguard::_OverWriteMediaId", 0x1AEu, 1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x180038fb4  push    rbp
0x180038fb6  push    rbx
0x180038fb7  push    rdi
0x180038fb8  push    r14
0x180038fba  push    r15
0x180038fbc  lea     rbp, [rsp-1B0h]
0x180038fc4  sub     rsp, 2B0h
0x180038fcb  mov     rax, cs:__security_cookie
0x180038fd2  xor     rax, rsp
0x180038fd5  mov     [rbp+1D0h+var_30], rax
0x180038fdc  mov     r14, r9
0x180038fdf  mov     r15, r8
0x180038fe2  mov     rbx, rdx
0x180038fe5  mov     edi, [rbp+1D0h+arg_20]
0x180038feb  mov     r9d, 1; unsigned __int16
0x180038ff1  mov     r8d, 1AEh; unsigned __int16
0x180038ff7  lea     rdx, aCsdsafeguardOv; "CSdSafeguard::_OverWriteMediaId"
0x180038ffe  lea     rcx, [rsp+2D0h+var_288]; this
0x180039003  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180039008  lea     rax, qword_1800EE510
0x18003900f  mov     [rbp+1D0h+lpFileName], rax
0x180039013  mov     [rbp+1D0h+var_248], 0
0x18003901b  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x180039023  mov     [rbp+1D0h+Buffer], 0
0x18003902a  xor     edx, edx; Val
0x18003902c  mov     r8d, 20Ch; Size
0x180039032  lea     rcx, [rbp+1D0h+var_23C]; void *
0x180039036  call    memset_0
0x18003903b  mov     eax, 1B5h
0x180039040  test    rbx, rbx
0x180039043  jnz     short loc_180039053
0x180039045  mov     edi, 80070057h
0x18003904a  mov     [rsp+2D0h+var_288], edi
0x18003904e  jmp     loc_18003927F
0x180039053  mov     [rsp+2D0h+var_284], ax
0x180039058  mov     eax, 1B6h
0x18003905d  test    r14, r14
0x180039060  jz      short loc_180039045
0x180039062  mov     [rsp+2D0h+var_288], 0
0x18003906a  mov     [rsp+2D0h+var_284], ax
0x18003906f  lea     r9, [rbp+1D0h+lpFileName]; struct CBsString *
0x180039073  mov     r8d, edi; int
0x180039076  xor     edx, edx; unsigned __int16 *
0x180039078  mov     rcx, rbx; unsigned __int16 *
0x18003907b  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x180039080  mov     edi, eax
0x180039082  mov     [rsp+2D0h+var_288], eax
0x180039086  test    eax, eax
0x180039088  mov     eax, 1B8h
0x18003908d  js      loc_18003927F
0x180039093  mov     [rsp+2D0h+var_284], ax
0x180039098  mov     edx, 80h; dwFileAttributes
0x18003909d  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x1800390a1  call    cs:__imp_SetFileAttributesW
0x1800390a8  nop     dword ptr [rax+rax+00h]
0x1800390ad  test    eax, eax
0x1800390af  jnz     short loc_1800390C6
0x1800390b1  call    GetLastFailureAsHRESULT
0x1800390b6  mov     edi, eax
0x1800390b8  mov     [rsp+2D0h+var_288], eax
0x1800390bc  mov     eax, 1BDh
0x1800390c1  jmp     loc_18003927F
0x1800390c6  mov     [rsp+2D0h+var_288], 0
0x1800390ce  mov     eax, 1BDh
0x1800390d3  mov     [rsp+2D0h+var_284], ax
0x1800390d8  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x1800390e1  mov     [rsp+2D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800390e9  mov     [rsp+2D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800390f1  xor     r9d, r9d; lpSecurityAttributes
0x1800390f4  xor     r8d, r8d; dwShareMode
0x1800390f7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800390fc  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180039100  call    cs:__imp_CreateFileW
0x180039107  nop     dword ptr [rax+rax+00h]
0x18003910c  mov     rbx, rax
0x18003910f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039113  jz      loc_18003926F
0x180039119  mov     [rsp+2D0h+var_288], 0
0x180039121  mov     eax, 1C3h
0x180039126  mov     [rsp+2D0h+var_284], ax
0x18003912b  mov     eax, [r15]
0x18003912e  mov     [rbp+1D0h+Buffer], eax
0x180039131  movsd   xmm0, qword ptr [r15+4]
0x180039137  movsd   [rbp+1D0h+var_23C], xmm0
0x18003913c  mov     eax, [r15+0Ch]
0x180039140  mov     [rbp+1D0h+var_234], eax
0x180039143  mov     r8, r14; unsigned __int16 *
0x180039146  mov     edx, 100h; unsigned __int64
0x18003914b  lea     rcx, [rbp+1D0h+var_230]; unsigned __int16 *
0x18003914f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039154  mov     edi, eax
0x180039156  mov     [rsp+2D0h+var_288], eax
0x18003915a  test    eax, eax
0x18003915c  mov     eax, 1C9h
0x180039161  jns     short loc_18003916D
0x180039163  mov     [rsp+2D0h+var_282], ax
0x180039168  jmp     loc_180039259
0x18003916d  mov     [rsp+2D0h+var_284], ax
0x180039172  xor     r9d, r9d; dwMoveMethod
0x180039175  xor     r8d, r8d; lpDistanceToMoveHigh
0x180039178  xor     edx, edx; lDistanceToMove
0x18003917a  mov     rcx, rbx; hFile
0x18003917d  call    cs:__imp_SetFilePointer
0x180039184  nop     dword ptr [rax+rax+00h]
0x180039189  cmp     eax, 0FFFFFFFFh
0x18003918c  jnz     short loc_1800391A0
0x18003918e  call    GetLastFailureAsHRESULT
0x180039193  mov     edi, eax
0x180039195  mov     [rsp+2D0h+var_288], eax
0x180039199  mov     eax, 1CCh
0x18003919e  jmp     short loc_180039163
0x1800391a0  mov     [rsp+2D0h+var_288], 0
0x1800391a8  mov     eax, 1CCh
0x1800391ad  mov     [rsp+2D0h+var_284], ax
0x1800391b2  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x1800391bb  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800391c0  lea     edi, [rax+44h]
0x1800391c3  mov     r8d, edi; nNumberOfBytesToWrite
0x1800391c6  lea     rdx, [rbp+1D0h+Buffer]; lpBuffer
0x1800391ca  mov     rcx, rbx; hFile
0x1800391cd  call    cs:__imp_WriteFile
0x1800391d4  nop     dword ptr [rax+rax+00h]
0x1800391d9  test    eax, eax
0x1800391db  jnz     short loc_1800391F2
0x1800391dd  call    GetLastFailureAsHRESULT
0x1800391e2  mov     edi, eax
0x1800391e4  mov     [rsp+2D0h+var_288], eax
0x1800391e8  mov     eax, 1CEh
0x1800391ed  jmp     loc_180039163
0x1800391f2  mov     eax, 1CEh
0x1800391f7  mov     [rsp+2D0h+var_284], ax
0x1800391fc  mov     eax, 1CFh
0x180039201  cmp     [rsp+2D0h+NumberOfBytesWritten], edi
0x180039205  jz      short loc_180039215
0x180039207  mov     edi, 81000035h
0x18003920c  mov     [rsp+2D0h+var_288], edi
0x180039210  jmp     loc_180039163
0x180039215  mov     [rsp+2D0h+var_288], 0
0x18003921d  mov     [rsp+2D0h+var_284], ax
0x180039222  test    rbx, rbx
0x180039225  jz      short loc_18003923A
0x180039227  mov     rcx, rbx; hObject
0x18003922a  call    cs:__imp_CloseHandle
0x180039231  nop     dword ptr [rax+rax+00h]
0x180039236  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003923a  mov     edx, 1; dwFileAttributes
0x18003923f  mov     rcx, [rbp+1D0h+lpFileName]; lpFileName
0x180039243  call    cs:__imp_SetFileAttributesW
0x18003924a  nop     dword ptr [rax+rax+00h]
0x18003924f  mov     edi, [rsp+2D0h+var_288]
0x180039253  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180039257  jz      short loc_180039284
0x180039259  test    rbx, rbx
0x18003925c  jz      short loc_180039284
0x18003925e  mov     rcx, rbx; hObject
0x180039261  call    cs:__imp_CloseHandle
0x180039268  nop     dword ptr [rax+rax+00h]
0x18003926d  jmp     short loc_180039284
0x18003926f  call    GetLastFailureAsHRESULT
0x180039274  mov     edi, eax
0x180039276  mov     [rsp+2D0h+var_288], eax
0x18003927a  mov     eax, 1C3h
0x18003927f  mov     [rsp+2D0h+var_282], ax
0x180039284  lea     rcx, [rbp+1D0h+lpFileName]; this
0x180039288  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003928d  lea     rcx, [rsp+2D0h+var_288]; this
0x180039292  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180039297  mov     eax, edi
0x180039299  mov     rcx, [rbp+1D0h+var_30]
0x1800392a0  xor     rcx, rsp; StackCookie
0x1800392a3  call    __security_check_cookie
0x1800392a8  add     rsp, 2B0h
0x1800392af  pop     r15
0x1800392b1  pop     r14
0x1800392b3  pop     rdi
0x1800392b4  pop     rbx
0x1800392b5  pop     rbp
0x1800392b6  retn
```
