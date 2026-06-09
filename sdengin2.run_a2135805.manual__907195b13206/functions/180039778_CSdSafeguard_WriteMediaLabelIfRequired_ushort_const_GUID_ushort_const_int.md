# CSdSafeguard::_WriteMediaLabelIfRequired(ushort const *,_GUID,ushort const *,int)

- ea: `0x180039778`
- end: `0x180039a5d`
- name: `?_WriteMediaLabelIfRequired@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z`
- size: `741`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039a64`

## callees

- `0x180009d44`
- `0x180038fb4`
- `0x180039778`
- `0x18004f9a8`
- `0x18004fb78`
- `0x180072e08`
- `0x180072f14`
- `0x18008a874`
- `0x1800935fc`
- `0x18009f560`
- `0x1800cf546`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800398c1`
- `KERNEL32!CreateFileW` at `0x1800398c1`
- `KERNEL32!GetLastError` at `0x180039985`
- `KERNEL32!GetLastError` at `0x180039985`
- `KERNEL32!CloseHandle` at `0x180039a03`
- `KERNEL32!CloseHandle` at `0x180039a03`
- `KERNEL32!WriteFile` at `0x18003993b`
- `KERNEL32!WriteFile` at `0x18003993b`

## string_xrefs

- `0x1800397c2`: `CSdSafeguard::_WriteMediaLabelIfRequired`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_WriteMediaLabelIfRequired(
        CSdSafeguard *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int16 v9; // ax
  int IsPathUNC; // ebx
  int MediaIdLocation; // ecx
  struct _SECURITY_ATTRIBUTES *v12; // r9
  HANDLE FileW; // rdi
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rcx
  CSdSafeguard *v17; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-B4h]
  __int16 v22; // [rsp+4Eh] [rbp-B2h]
  LPCWSTR lpFileName[2]; // [rsp+80h] [rbp-80h] BYREF
  GUID Buf2; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Buffer; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+A4h] [rbp-5Ch] BYREF
  int v27; // [rsp+ACh] [rbp-54h]
  unsigned __int16 v28[256]; // [rsp+B0h] [rbp-50h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v20,
    "CSdSafeguard::_WriteMediaLabelIfRequired",
    0x168u,
    1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  NumberOfBytesWritten = 0;
  Buffer = 0;
  memset_0(&v26, 0, 0x20Cu);
  Buf2 = GUID_NULL;
  v9 = 369;
  if ( !a2 || (v21 = 369, v9 = 370, !a4) )
  {
    IsPathUNC = -2147024809;
    v20 = -2147024809;
LABEL_28:
    v22 = v9;
    goto LABEL_29;
  }
  v20 = 0;
  v21 = 370;
  IsPathUNC = SdIsPathUNC(a2);
  v20 = IsPathUNC;
  v9 = 373;
  if ( IsPathUNC < 0 )
    goto LABEL_28;
  v21 = 373;
  MediaIdLocation = CSdCommonImpl::s_QueryMediaIdLocation(a2, 0, a5, (struct CBsString *)lpFileName);
  v20 = MediaIdLocation;
  v9 = 376;
  if ( MediaIdLocation < 0 )
  {
    IsPathUNC = MediaIdLocation;
    goto LABEL_28;
  }
  v21 = 376;
  if ( IsPathUNC )
    v12 = (struct _SECURITY_ATTRIBUTES *)((char *)this + 72);
  else
    v12 = 0;
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 0, v12, 1u, 1u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() != 80 )
    {
      IsPathUNC = GetLastFailureAsHRESULT(v16);
      v20 = IsPathUNC;
      v9 = 411;
      goto LABEL_28;
    }
    if ( (int)CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(a2, v15, a5, &Buf2) >= 0 && !memcmp_0(a3, &Buf2, 0x10u) )
    {
      IsPathUNC = v20;
      goto LABEL_24;
    }
    Buf2 = *a3;
    IsPathUNC = CSdSafeguard::_OverWriteMediaId(v17, a2, &Buf2, a4, a5);
    v20 = IsPathUNC;
    v9 = 403;
    if ( IsPathUNC < 0 )
      goto LABEL_28;
LABEL_23:
    v21 = v9;
LABEL_24:
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_29;
    goto LABEL_25;
  }
  Buffer = a3->Data1;
  v26 = *(_QWORD *)&a3->Data2;
  v27 = *(_DWORD *)&a3->Data4[4];
  IsPathUNC = StringCchCopyW(v28, 0x100u, a4);
  v20 = IsPathUNC;
  v9 = 389;
  if ( IsPathUNC >= 0 )
  {
    v21 = 389;
    if ( !WriteFile(FileW, &Buffer, 0x210u, &NumberOfBytesWritten, 0) )
    {
      IsPathUNC = GetLastFailureAsHRESULT(v14);
      v20 = IsPathUNC;
      v9 = 391;
      goto LABEL_12;
    }
    v21 = 391;
    v9 = 392;
    if ( NumberOfBytesWritten != 528 )
    {
      IsPathUNC = -2130706379;
      v20 = -2130706379;
      goto LABEL_12;
    }
    IsPathUNC = 0;
    v20 = 0;
    goto LABEL_23;
  }
LABEL_12:
  v22 = v9;
LABEL_25:
  if ( FileW )
    CloseHandle(FileW);
LABEL_29:
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)IsPathUNC;
}

```

## disassembly

```asm
0x180039778  push    rbp
0x18003977a  push    rbx
0x18003977b  push    rsi
0x18003977c  push    rdi
0x18003977d  push    r12
0x18003977f  push    r14
0x180039781  push    r15
0x180039783  lea     rbp, [rsp-1C0h]
0x18003978b  sub     rsp, 2C0h
0x180039792  mov     rax, cs:__security_cookie
0x180039799  xor     rax, rsp
0x18003979c  mov     [rbp+1F0h+var_40], rax
0x1800397a3  mov     r15, r9
0x1800397a6  mov     rsi, r8
0x1800397a9  mov     r14, rdx
0x1800397ac  mov     rdi, rcx
0x1800397af  mov     r12d, [rbp+1F0h+arg_20]
0x1800397b6  mov     r9d, 1; unsigned __int16
0x1800397bc  mov     r8d, 168h; unsigned __int16
0x1800397c2  lea     rdx, aCsdsafeguardWr_1; "CSdSafeguard::_WriteMediaLabelIfRequire"...
0x1800397c9  lea     rcx, [rsp+2F0h+var_2A8]; this
0x1800397ce  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800397d3  lea     rax, qword_1800EE510
0x1800397da  mov     [rbp+1F0h+lpFileName], rax
0x1800397de  mov     [rbp+1F0h+var_268], 0
0x1800397e6  mov     [rsp+2F0h+NumberOfBytesWritten], 0
0x1800397ee  mov     [rbp+1F0h+Buffer], 0
0x1800397f5  xor     edx, edx; Val
0x1800397f7  mov     r8d, 20Ch; Size
0x1800397fd  lea     rcx, [rbp+1F0h+var_24C]; void *
0x180039801  call    memset_0
0x180039806  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003980d  movdqu  [rbp+1F0h+Buf2], xmm0
0x180039812  mov     eax, 171h
0x180039817  test    r14, r14
0x18003981a  jnz     short loc_18003982A
0x18003981c  mov     ebx, 80070057h
0x180039821  mov     [rsp+2F0h+var_2A8], ebx
0x180039825  jmp     loc_180039A21
0x18003982a  mov     [rsp+2F0h+var_2A4], ax
0x18003982f  mov     eax, 172h
0x180039834  test    r15, r15
0x180039837  jz      short loc_18003981C
0x180039839  mov     [rsp+2F0h+var_2A8], 0
0x180039841  mov     [rsp+2F0h+var_2A4], ax
0x180039846  mov     rcx, r14; unsigned __int16 *
0x180039849  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x18003984e  mov     ebx, eax
0x180039850  mov     [rsp+2F0h+var_2A8], eax
0x180039854  test    eax, eax
0x180039856  mov     eax, 175h
0x18003985b  js      loc_180039A21
0x180039861  mov     [rsp+2F0h+var_2A4], ax
0x180039866  lea     r9, [rbp+1F0h+lpFileName]; struct CBsString *
0x18003986a  mov     r8d, r12d; int
0x18003986d  xor     edx, edx; unsigned __int16 *
0x18003986f  mov     rcx, r14; unsigned __int16 *
0x180039872  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x180039877  mov     ecx, eax
0x180039879  mov     [rsp+2F0h+var_2A8], eax
0x18003987d  test    eax, eax
0x18003987f  mov     eax, 178h
0x180039884  jns     short loc_18003988D
0x180039886  mov     ebx, ecx
0x180039888  jmp     loc_180039A21
0x18003988d  mov     [rsp+2F0h+var_2A4], ax
0x180039892  test    ebx, ebx
0x180039894  jnz     short loc_18003989B
0x180039896  xor     r9d, r9d
0x180039899  jmp     short loc_18003989F
0x18003989b  lea     r9, [rdi+48h]; lpSecurityAttributes
0x18003989f  mov     [rsp+2F0h+hTemplateFile], 0; hTemplateFile
0x1800398a8  mov     eax, 1
0x1800398ad  mov     [rsp+2F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800398b1  mov     [rsp+2F0h+dwCreationDisposition], eax; dwCreationDisposition
0x1800398b5  xor     r8d, r8d; dwShareMode
0x1800398b8  mov     edx, 0C0000000h; dwDesiredAccess
0x1800398bd  mov     rcx, [rbp+1F0h+lpFileName]; lpFileName
0x1800398c1  call    cs:__imp_CreateFileW
0x1800398c8  nop     dword ptr [rax+rax+00h]
0x1800398cd  mov     rdi, rax
0x1800398d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800398d4  jz      loc_180039985
0x1800398da  mov     eax, [rsi]
0x1800398dc  mov     [rbp+1F0h+Buffer], eax
0x1800398df  movsd   xmm0, qword ptr [rsi+4]
0x1800398e4  movsd   [rbp+1F0h+var_24C], xmm0
0x1800398e9  mov     eax, [rsi+0Ch]
0x1800398ec  mov     [rbp+1F0h+var_244], eax
0x1800398ef  mov     r8, r15; unsigned __int16 *
0x1800398f2  mov     edx, 100h; unsigned __int64
0x1800398f7  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x1800398fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180039900  mov     ebx, eax
0x180039902  mov     [rsp+2F0h+var_2A8], eax
0x180039906  test    eax, eax
0x180039908  mov     eax, 185h
0x18003990d  jns     short loc_180039919
0x18003990f  mov     [rsp+2F0h+var_2A2], ax
0x180039914  jmp     loc_1800399FB
0x180039919  mov     [rsp+2F0h+var_2A4], ax
0x18003991e  mov     qword ptr [rsp+2F0h+dwCreationDisposition], 0; lpOverlapped
0x180039927  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003992c  mov     ebx, 210h
0x180039931  mov     r8d, ebx; nNumberOfBytesToWrite
0x180039934  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x180039938  mov     rcx, rdi; hFile
0x18003993b  call    cs:__imp_WriteFile
0x180039942  nop     dword ptr [rax+rax+00h]
0x180039947  test    eax, eax
0x180039949  jnz     short loc_18003995D
0x18003994b  call    GetLastFailureAsHRESULT
0x180039950  mov     ebx, eax
0x180039952  mov     [rsp+2F0h+var_2A8], eax
0x180039956  mov     eax, 187h
0x18003995b  jmp     short loc_18003990F
0x18003995d  mov     eax, 187h
0x180039962  mov     [rsp+2F0h+var_2A4], ax
0x180039967  mov     eax, 188h
0x18003996c  cmp     [rsp+2F0h+NumberOfBytesWritten], ebx
0x180039970  jz      short loc_18003997D
0x180039972  mov     ebx, 81000035h
0x180039977  mov     [rsp+2F0h+var_2A8], ebx
0x18003997b  jmp     short loc_18003990F
0x18003997d  xor     ebx, ebx
0x18003997f  mov     [rsp+2F0h+var_2A8], ebx
0x180039983  jmp     short loc_1800399F0
0x180039985  call    cs:__imp_GetLastError
0x18003998c  nop     dword ptr [rax+rax+00h]
0x180039991  cmp     eax, 50h ; 'P'
0x180039994  jnz     short loc_180039A11
0x180039996  lea     r9, [rbp+1F0h+Buf2]; struct _GUID *
0x18003999a  mov     r8d, r12d; int
0x18003999d  mov     rcx, r14; unsigned __int16 *
0x1800399a0  call    ?s_QueryMediaIdFromSpecificLocation@CSdCommonImpl@@SAJPEBG0HPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(ushort const *,ushort const *,int,_GUID *)
0x1800399a5  test    eax, eax
0x1800399a7  js      short loc_1800399C5
0x1800399a9  mov     r8d, 10h; Size
0x1800399af  lea     rdx, [rbp+1F0h+Buf2]; Buf2
0x1800399b3  mov     rcx, rsi; Buf1
0x1800399b6  call    memcmp_0
0x1800399bb  test    eax, eax
0x1800399bd  jnz     short loc_1800399C5
0x1800399bf  mov     ebx, [rsp+2F0h+var_2A8]
0x1800399c3  jmp     short loc_1800399F5
0x1800399c5  movaps  xmm0, xmmword ptr [rsi]
0x1800399c8  movdqa  [rbp+1F0h+Buf2], xmm0
0x1800399cd  mov     [rsp+2F0h+dwCreationDisposition], r12d; int
0x1800399d2  mov     r9, r15; unsigned __int16 *
0x1800399d5  lea     r8, [rbp+1F0h+Buf2]; struct _GUID
0x1800399d9  mov     rdx, r14; unsigned __int16 *
0x1800399dc  call    ?_OverWriteMediaId@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z; CSdSafeguard::_OverWriteMediaId(ushort const *,_GUID,ushort const *,int)
0x1800399e1  mov     ebx, eax
0x1800399e3  mov     [rsp+2F0h+var_2A8], eax
0x1800399e7  test    eax, eax
0x1800399e9  mov     eax, 193h
0x1800399ee  js      short loc_180039A21
0x1800399f0  mov     [rsp+2F0h+var_2A4], ax
0x1800399f5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800399f9  jz      short loc_180039A26
0x1800399fb  test    rdi, rdi
0x1800399fe  jz      short loc_180039A26
0x180039a00  mov     rcx, rdi; hObject
0x180039a03  call    cs:__imp_CloseHandle
0x180039a0a  nop     dword ptr [rax+rax+00h]
0x180039a0f  jmp     short loc_180039A26
0x180039a11  call    GetLastFailureAsHRESULT
0x180039a16  mov     ebx, eax
0x180039a18  mov     [rsp+2F0h+var_2A8], eax
0x180039a1c  mov     eax, 19Bh
0x180039a21  mov     [rsp+2F0h+var_2A2], ax
0x180039a26  lea     rcx, [rbp+1F0h+lpFileName]; this
0x180039a2a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180039a2f  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180039a34  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180039a39  mov     eax, ebx
0x180039a3b  mov     rcx, [rbp+1F0h+var_40]
0x180039a42  xor     rcx, rsp; StackCookie
0x180039a45  call    __security_check_cookie
0x180039a4a  add     rsp, 2C0h
0x180039a51  pop     r15
0x180039a53  pop     r14
0x180039a55  pop     r12
0x180039a57  pop     rdi
0x180039a58  pop     rsi
0x180039a59  pop     rbx
0x180039a5a  pop     rbp
0x180039a5b  retn
```
