# CSdSafeguard::_WriteMediaLabelIfRequired(ushort const *,_GUID,ushort const *,int)

- ea: `0x1800381f8`
- end: `0x1800384c4`
- name: `?_WriteMediaLabelIfRequired@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z`
- size: `716`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, struct _GUID *__struct_ptr, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800384cc`

## callees

- `0x180009ac8`
- `0x180037aa8`
- `0x1800381f8`
- `0x18004dbd0`
- `0x18004dd80`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086ef8`
- `0x18008f5d0`
- `0x18009ae34`
- `0x1800c97b6`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180038341`
- `KERNEL32!CreateFileW` at `0x180038341`
- `KERNEL32!GetLastError` at `0x1800383f9`
- `KERNEL32!GetLastError` at `0x1800383f9`
- `KERNEL32!CloseHandle` at `0x180038471`
- `KERNEL32!CloseHandle` at `0x180038471`
- `KERNEL32!WriteFile` at `0x1800383b5`
- `KERNEL32!WriteFile` at `0x1800383b5`

## string_xrefs

- `0x180038242`: `CSdSafeguard::_WriteMediaLabelIfRequired`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "CSdSafeguard::_WriteMediaLabelIfRequired", 360, 1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
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
0x1800381f8  push    rbp
0x1800381fa  push    rbx
0x1800381fb  push    rsi
0x1800381fc  push    rdi
0x1800381fd  push    r12
0x1800381ff  push    r14
0x180038201  push    r15
0x180038203  lea     rbp, [rsp-1C0h]
0x18003820b  sub     rsp, 2C0h
0x180038212  mov     rax, cs:__security_cookie
0x180038219  xor     rax, rsp
0x18003821c  mov     [rbp+1F0h+var_40], rax
0x180038223  mov     r15, r9
0x180038226  mov     rsi, r8
0x180038229  mov     r14, rdx
0x18003822c  mov     rdi, rcx
0x18003822f  mov     r12d, [rbp+1F0h+arg_20]
0x180038236  mov     r9d, 1; unsigned __int16
0x18003823c  mov     r8d, 168h; unsigned __int16
0x180038242  lea     rdx, aCsdsafeguardWr_1; "CSdSafeguard::_WriteMediaLabelIfRequire"...
0x180038249  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18003824e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180038253  lea     rax, qword_1800E8530
0x18003825a  mov     [rbp+1F0h+lpFileName], rax
0x18003825e  mov     [rbp+1F0h+var_268], 0
0x180038266  mov     [rsp+2F0h+NumberOfBytesWritten], 0
0x18003826e  mov     [rbp+1F0h+Buffer], 0
0x180038275  xor     edx, edx; Val
0x180038277  mov     r8d, 20Ch; Size
0x18003827d  lea     rcx, [rbp+1F0h+var_24C]; void *
0x180038281  call    memset_0
0x180038286  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003828d  movdqu  [rbp+1F0h+Buf2], xmm0
0x180038292  mov     eax, 171h
0x180038297  test    r14, r14
0x18003829a  jnz     short loc_1800382AA
0x18003829c  mov     ebx, 80070057h
0x1800382a1  mov     [rsp+2F0h+var_2A8], ebx
0x1800382a5  jmp     loc_180038489
0x1800382aa  mov     [rsp+2F0h+var_2A4], ax
0x1800382af  mov     eax, 172h
0x1800382b4  test    r15, r15
0x1800382b7  jz      short loc_18003829C
0x1800382b9  mov     [rsp+2F0h+var_2A8], 0
0x1800382c1  mov     [rsp+2F0h+var_2A4], ax
0x1800382c6  mov     rcx, r14; unsigned __int16 *
0x1800382c9  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x1800382ce  mov     ebx, eax
0x1800382d0  mov     [rsp+2F0h+var_2A8], eax
0x1800382d4  test    eax, eax
0x1800382d6  mov     eax, 175h
0x1800382db  js      loc_180038489
0x1800382e1  mov     [rsp+2F0h+var_2A4], ax
0x1800382e6  lea     r9, [rbp+1F0h+lpFileName]; struct CBsString *
0x1800382ea  mov     r8d, r12d; int
0x1800382ed  xor     edx, edx; unsigned __int16 *
0x1800382ef  mov     rcx, r14; unsigned __int16 *
0x1800382f2  call    ?s_QueryMediaIdLocation@CSdCommonImpl@@SAJPEBG0HPEAVCBsString@@@Z; CSdCommonImpl::s_QueryMediaIdLocation(ushort const *,ushort const *,int,CBsString *)
0x1800382f7  mov     ecx, eax
0x1800382f9  mov     [rsp+2F0h+var_2A8], eax
0x1800382fd  test    eax, eax
0x1800382ff  mov     eax, 178h
0x180038304  jns     short loc_18003830D
0x180038306  mov     ebx, ecx
0x180038308  jmp     loc_180038489
0x18003830d  mov     [rsp+2F0h+var_2A4], ax
0x180038312  test    ebx, ebx
0x180038314  jnz     short loc_18003831B
0x180038316  xor     r9d, r9d
0x180038319  jmp     short loc_18003831F
0x18003831b  lea     r9, [rdi+48h]; lpSecurityAttributes
0x18003831f  mov     [rsp+2F0h+hTemplateFile], 0; hTemplateFile
0x180038328  mov     eax, 1
0x18003832d  mov     [rsp+2F0h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180038331  mov     [rsp+2F0h+dwCreationDisposition], eax; dwCreationDisposition
0x180038335  xor     r8d, r8d; dwShareMode
0x180038338  mov     edx, 0C0000000h; dwDesiredAccess
0x18003833d  mov     rcx, [rbp+1F0h+lpFileName]; lpFileName
0x180038341  call    cs:__imp_CreateFileW
0x180038347  mov     rdi, rax
0x18003834a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003834e  jz      loc_1800383F9
0x180038354  mov     eax, [rsi]
0x180038356  mov     [rbp+1F0h+Buffer], eax
0x180038359  movsd   xmm0, qword ptr [rsi+4]
0x18003835e  movsd   [rbp+1F0h+var_24C], xmm0
0x180038363  mov     eax, [rsi+0Ch]
0x180038366  mov     [rbp+1F0h+var_244], eax
0x180038369  mov     r8, r15; unsigned __int16 *
0x18003836c  mov     edx, 100h; unsigned __int64
0x180038371  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x180038375  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003837a  mov     ebx, eax
0x18003837c  mov     [rsp+2F0h+var_2A8], eax
0x180038380  test    eax, eax
0x180038382  mov     eax, 185h
0x180038387  jns     short loc_180038393
0x180038389  mov     [rsp+2F0h+var_2A2], ax
0x18003838e  jmp     loc_180038469
0x180038393  mov     [rsp+2F0h+var_2A4], ax
0x180038398  mov     qword ptr [rsp+2F0h+dwCreationDisposition], 0; lpOverlapped
0x1800383a1  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800383a6  mov     ebx, 210h
0x1800383ab  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800383ae  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x1800383b2  mov     rcx, rdi; hFile
0x1800383b5  call    cs:__imp_WriteFile
0x1800383bb  test    eax, eax
0x1800383bd  jnz     short loc_1800383D1
0x1800383bf  call    GetLastFailureAsHRESULT
0x1800383c4  mov     ebx, eax
0x1800383c6  mov     [rsp+2F0h+var_2A8], eax
0x1800383ca  mov     eax, 187h
0x1800383cf  jmp     short loc_180038389
0x1800383d1  mov     eax, 187h
0x1800383d6  mov     [rsp+2F0h+var_2A4], ax
0x1800383db  mov     eax, 188h
0x1800383e0  cmp     [rsp+2F0h+NumberOfBytesWritten], ebx
0x1800383e4  jz      short loc_1800383F1
0x1800383e6  mov     ebx, 81000035h
0x1800383eb  mov     [rsp+2F0h+var_2A8], ebx
0x1800383ef  jmp     short loc_180038389
0x1800383f1  xor     ebx, ebx
0x1800383f3  mov     [rsp+2F0h+var_2A8], ebx
0x1800383f7  jmp     short loc_18003845E
0x1800383f9  call    cs:__imp_GetLastError
0x1800383ff  cmp     eax, 50h ; 'P'
0x180038402  jnz     short loc_180038479
0x180038404  lea     r9, [rbp+1F0h+Buf2]; struct _GUID *
0x180038408  mov     r8d, r12d; int
0x18003840b  mov     rcx, r14; unsigned __int16 *
0x18003840e  call    ?s_QueryMediaIdFromSpecificLocation@CSdCommonImpl@@SAJPEBG0HPEAU_GUID@@@Z; CSdCommonImpl::s_QueryMediaIdFromSpecificLocation(ushort const *,ushort const *,int,_GUID *)
0x180038413  test    eax, eax
0x180038415  js      short loc_180038433
0x180038417  mov     r8d, 10h; Size
0x18003841d  lea     rdx, [rbp+1F0h+Buf2]; Buf2
0x180038421  mov     rcx, rsi; Buf1
0x180038424  call    memcmp_0
0x180038429  test    eax, eax
0x18003842b  jnz     short loc_180038433
0x18003842d  mov     ebx, [rsp+2F0h+var_2A8]
0x180038431  jmp     short loc_180038463
0x180038433  movaps  xmm0, xmmword ptr [rsi]
0x180038436  movdqa  [rbp+1F0h+Buf2], xmm0
0x18003843b  mov     [rsp+2F0h+dwCreationDisposition], r12d; int
0x180038440  mov     r9, r15; unsigned __int16 *
0x180038443  lea     r8, [rbp+1F0h+Buf2]; struct _GUID
0x180038447  mov     rdx, r14; unsigned __int16 *
0x18003844a  call    ?_OverWriteMediaId@CSdSafeguard@@AEAAJPEBGU_GUID@@0H@Z; CSdSafeguard::_OverWriteMediaId(ushort const *,_GUID,ushort const *,int)
0x18003844f  mov     ebx, eax
0x180038451  mov     [rsp+2F0h+var_2A8], eax
0x180038455  test    eax, eax
0x180038457  mov     eax, 193h
0x18003845c  js      short loc_180038489
0x18003845e  mov     [rsp+2F0h+var_2A4], ax
0x180038463  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180038467  jz      short loc_18003848E
0x180038469  test    rdi, rdi
0x18003846c  jz      short loc_18003848E
0x18003846e  mov     rcx, rdi; hObject
0x180038471  call    cs:__imp_CloseHandle
0x180038477  jmp     short loc_18003848E
0x180038479  call    GetLastFailureAsHRESULT
0x18003847e  mov     ebx, eax
0x180038480  mov     [rsp+2F0h+var_2A8], eax
0x180038484  mov     eax, 19Bh
0x180038489  mov     [rsp+2F0h+var_2A2], ax
0x18003848e  lea     rcx, [rbp+1F0h+lpFileName]; this
0x180038492  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180038497  lea     rcx, [rsp+2F0h+var_2A8]; this
0x18003849c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800384a1  mov     eax, ebx
0x1800384a3  mov     rcx, [rbp+1F0h+var_40]
0x1800384aa  xor     rcx, rsp; StackCookie
0x1800384ad  call    __security_check_cookie
0x1800384b2  add     rsp, 2C0h
0x1800384b9  pop     r15
0x1800384bb  pop     r14
0x1800384bd  pop     r12
0x1800384bf  pop     rdi
0x1800384c0  pop     rsi
0x1800384c1  pop     rbx
0x1800384c2  pop     rbp
0x1800384c3  retn
```
