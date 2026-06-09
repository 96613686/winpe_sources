# LogVolumeSqmData(ushort const *)

- ea: `0x180031284`
- end: `0x18003151f`
- name: `?LogVolumeSqmData@@YAJPEBG@Z`
- size: `667`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x180031528`

## callees

- `0x180001580`
- `0x18000212c`
- `0x1800075b0`
- `0x18002f5d0`
- `0x18002f7c8`
- `0x18002fa14`
- `0x18002fd04`
- `0x180031284`
- `0x180033a8c`
- `0x180033c78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800314e2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800314e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003139c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003139c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800314d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800314d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031401`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800313f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800313f2`
- `ntdll!WinSqmAddToStream` at `0x1800314a2`
- `ntdll!WinSqmAddToStream` at `0x1800314b9`
- `ntdll!WinSqmAddToStream` at `0x1800314d0`
- `ntdll!WinSqmAddToStream` at `0x1800314a2`
- `ntdll!WinSqmAddToStream` at `0x1800314b9`
- `ntdll!WinSqmAddToStream` at `0x1800314d0`

## pseudocode

```c
__int64 __fastcall LogVolumeSqmData(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  unsigned __int64 v3; // rbx
  unsigned __int16 *v4; // rax
  WCHAR *v5; // rsi
  HANDLE FileW; // rax
  void *v7; // rbx
  signed int LastError; // eax
  LPVOID v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v13[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v14; // [rsp+C8h] [rbp-38h]
  int v15; // [rsp+CCh] [rbp-34h]
  int v16; // [rsp+D0h] [rbp-30h]
  _BYTE v17[120]; // [rsp+D8h] [rbp-28h] BYREF
  int v18; // [rsp+150h] [rbp+50h]
  int v19; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v20[136]; // [rsp+198h] [rbp+98h] BYREF
  int v21; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v22[136]; // [rsp+228h] [rbp+128h] BYREF
  int v23; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v24[136]; // [rsp+2B8h] [rbp+1B8h] BYREF

  v14 = 382;
  v12 = L"base\\stor\\vss\\modules\\softprv\\src\\sqm.cxx";
  v15 = 2;
  v13[0] = L"LogVolumeSqmData";
  v16 = 255;
  v13[1] = L"SPRDIFFH";
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v10, (__int64)&v12, 0);
  v12 = 0;
  memset_0(v13, 0, 0xD8u);
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( !a1 )
  {
    v2 = -2147024809;
LABEL_3:
    v11 = v2;
    goto LABEL_20;
  }
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  v4 = (unsigned __int16 *)malloc(2 * v3);
  v5 = v4;
  if ( !v4 )
  {
    v2 = -2147024882;
    goto LABEL_3;
  }
  v11 = StringCchCopyNW(v4, v3, a1, v3 - 1);
  if ( v11 >= 0 )
  {
    FileW = CreateFileW(v5, 0x80000000, 3u, 0, 3u, 0x80u, 0);
    v7 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v11 = LastError;
    }
    else
    {
      v11 = CollectVolumeData(a1, FileW, (struct SQMVOLDATA *)&v12);
      if ( v11 >= 0 )
      {
        v11 = BuildSqmStreamFields_Stream_Cow(a1, (const struct SQMVOLDATA *)&v12, (struct _SQM_STREAM_ENTRY *)&v19);
        if ( v11 >= 0 )
        {
          v11 = BuildSqmStreamFields_Stream_PreCow(
                  a1,
                  (const struct SQMVOLDATA *)&v12,
                  (struct _SQM_STREAM_ENTRY *)&v21);
          if ( v11 >= 0 )
          {
            v11 = BuildSqmStreamFields_Stream_DiffArea(
                    a1,
                    (const struct SQMVOLDATA *)&v12,
                    (struct _SQM_STREAM_ENTRY *)&v23);
            if ( v11 >= 0 )
            {
              WinSqmAddToStream(0, 2089, 9, &v19);
              WinSqmAddToStream(0, 2097, 9, &v21);
              WinSqmAddToStream(0, 2098, 9, &v23);
            }
          }
        }
      }
      CloseHandle(v7);
    }
  }
  free(v5);
  v2 = v11;
LABEL_20:
  CVssFunctionTracer::~CVssFunctionTracer(&v10);
  return v2;
}

```

## disassembly

```asm
0x180031284  mov     [rsp-8+arg_8], rbx
0x180031289  mov     [rsp-8+arg_10], rsi
0x18003128e  push    rbp
0x18003128f  push    rdi
0x180031290  push    r14
0x180031292  lea     rbp, [rsp-250h]
0x18003129a  sub     rsp, 350h
0x1800312a1  mov     rax, cs:__security_cookie
0x1800312a8  xor     rax, rsp
0x1800312ab  mov     [rbp+260h+var_20], rax
0x1800312b2  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800312b9  mov     [rbp+260h+var_298], 17Eh
0x1800312c0  mov     [rbp+260h+var_2B0], rax
0x1800312c4  mov     rdi, rcx
0x1800312c7  lea     rax, aLogvolumesqmda; "LogVolumeSqmData"
0x1800312ce  mov     [rbp+260h+var_294], 2
0x1800312d5  mov     [rbp+260h+var_2A8], rax
0x1800312d9  lea     rcx, [rbp+260h+var_288]; void *
0x1800312dd  lea     rax, aSprdiffh; "SPRDIFFH"
0x1800312e4  mov     [rbp+260h+var_290], 0FFh
0x1800312eb  xor     r14d, r14d
0x1800312ee  mov     [rbp+260h+var_2A0], rax
0x1800312f2  xor     edx, edx; Val
0x1800312f4  mov     [rbp+260h+var_210], 1000000h
0x1800312fb  lea     r8d, [r14+78h]; Size
0x1800312ff  call    memset_0
0x180031304  xor     r8d, r8d
0x180031307  lea     rdx, [rbp+260h+var_2B0]
0x18003130b  lea     rcx, [rsp+360h+var_320]
0x180031310  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180031315  xor     edx, edx; Val
0x180031317  mov     [rbp+260h+var_2B0], r14
0x18003131b  mov     r8d, 0D8h; Size
0x180031321  lea     rcx, [rbp+260h+var_2A8]; void *
0x180031325  call    memset_0
0x18003132a  mov     ebx, 88h
0x18003132f  mov     [rbp+260h+var_1D0], r14d
0x180031336  mov     r8d, ebx; Size
0x180031339  lea     rcx, [rbp+260h+var_1C8]; void *
0x180031340  xor     edx, edx; Val
0x180031342  call    memset_0
0x180031347  mov     r8d, ebx; Size
0x18003134a  mov     [rbp+260h+var_140], r14d
0x180031351  xor     edx, edx; Val
0x180031353  lea     rcx, [rbp+260h+var_138]; void *
0x18003135a  call    memset_0
0x18003135f  mov     r8d, ebx; Size
0x180031362  mov     [rbp+260h+var_B0], r14d
0x180031369  xor     edx, edx; Val
0x18003136b  lea     rcx, [rbp+260h+var_A8]; void *
0x180031372  call    memset_0
0x180031377  test    rdi, rdi
0x18003137a  jnz     short loc_18003138A
0x18003137c  mov     ebx, 80070057h
0x180031381  mov     [rsp+360h+var_318], ebx
0x180031385  jmp     loc_1800314EC
0x18003138a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003138e  inc     rbx
0x180031391  cmp     [rdi+rbx*2], r14w
0x180031396  jnz     short loc_18003138E
0x180031398  lea     rcx, [rbx+rbx]; Size
0x18003139c  call    cs:__imp_malloc
0x1800313a2  mov     rsi, rax
0x1800313a5  test    rax, rax
0x1800313a8  jnz     short loc_1800313B1
0x1800313aa  mov     ebx, 8007000Eh
0x1800313af  jmp     short loc_180031381
0x1800313b1  lea     r9, [rbx-1]; unsigned __int64
0x1800313b5  mov     r8, rdi; unsigned __int16 *
0x1800313b8  mov     rdx, rbx; unsigned __int64
0x1800313bb  mov     rcx, rsi; unsigned __int16 *
0x1800313be  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800313c3  mov     [rsp+360h+var_318], eax
0x1800313c7  test    eax, eax
0x1800313c9  js      loc_1800314DF
0x1800313cf  mov     [rsp+360h+hTemplateFile], r14; hTemplateFile
0x1800313d4  mov     r8d, 3; dwShareMode
0x1800313da  mov     [rsp+360h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800313e2  xor     r9d, r9d; lpSecurityAttributes
0x1800313e5  mov     edx, 80000000h; dwDesiredAccess
0x1800313ea  mov     [rsp+360h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800313ef  mov     rcx, rsi; lpFileName
0x1800313f2  call    cs:__imp_CreateFileW
0x1800313f8  mov     rbx, rax
0x1800313fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800313ff  jnz     short loc_18003141C
0x180031401  call    cs:__imp_GetLastError
0x180031407  test    eax, eax
0x180031409  jle     short loc_180031413
0x18003140b  movzx   eax, ax
0x18003140e  or      eax, 80070000h
0x180031413  mov     [rsp+360h+var_318], eax
0x180031417  jmp     loc_1800314DF
0x18003141c  lea     r8, [rbp+260h+var_2B0]; struct SQMVOLDATA *
0x180031420  mov     rdx, rbx; void *
0x180031423  mov     rcx, rdi; unsigned __int16 *
0x180031426  call    ?CollectVolumeData@@YAJPEBGPEAXPEAUSQMVOLDATA@@@Z; CollectVolumeData(ushort const *,void *,SQMVOLDATA *)
0x18003142b  mov     [rsp+360h+var_318], eax
0x18003142f  test    eax, eax
0x180031431  js      loc_1800314D6
0x180031437  lea     r8, [rbp+260h+var_1D0]; struct _SQM_STREAM_ENTRY *
0x18003143e  mov     rcx, rdi; unsigned __int16 *
0x180031441  lea     rdx, [rbp+260h+var_2B0]; struct SQMVOLDATA *
0x180031445  call    ?BuildSqmStreamFields_Stream_Cow@@YAJPEBGAEBUSQMVOLDATA@@PEAU_SQM_STREAM_ENTRY@@@Z; BuildSqmStreamFields_Stream_Cow(ushort const *,SQMVOLDATA const &,_SQM_STREAM_ENTRY *)
0x18003144a  mov     [rsp+360h+var_318], eax
0x18003144e  test    eax, eax
0x180031450  js      loc_1800314D6
0x180031456  lea     r8, [rbp+260h+var_140]; struct _SQM_STREAM_ENTRY *
0x18003145d  mov     rcx, rdi; unsigned __int16 *
0x180031460  lea     rdx, [rbp+260h+var_2B0]; struct SQMVOLDATA *
0x180031464  call    ?BuildSqmStreamFields_Stream_PreCow@@YAJPEBGAEBUSQMVOLDATA@@PEAU_SQM_STREAM_ENTRY@@@Z; BuildSqmStreamFields_Stream_PreCow(ushort const *,SQMVOLDATA const &,_SQM_STREAM_ENTRY *)
0x180031469  mov     [rsp+360h+var_318], eax
0x18003146d  test    eax, eax
0x18003146f  js      short loc_1800314D6
0x180031471  lea     r8, [rbp+260h+var_B0]; struct _SQM_STREAM_ENTRY *
0x180031478  mov     rcx, rdi; unsigned __int16 *
0x18003147b  lea     rdx, [rbp+260h+var_2B0]; struct SQMVOLDATA *
0x18003147f  call    ?BuildSqmStreamFields_Stream_DiffArea@@YAJPEBGAEBUSQMVOLDATA@@PEAU_SQM_STREAM_ENTRY@@@Z; BuildSqmStreamFields_Stream_DiffArea(ushort const *,SQMVOLDATA const &,_SQM_STREAM_ENTRY *)
0x180031484  mov     [rsp+360h+var_318], eax
0x180031488  test    eax, eax
0x18003148a  js      short loc_1800314D6
0x18003148c  mov     edi, 9
0x180031491  lea     r9, [rbp+260h+var_1D0]
0x180031498  mov     r8d, edi
0x18003149b  mov     edx, 829h
0x1800314a0  xor     ecx, ecx
0x1800314a2  call    cs:__imp_WinSqmAddToStream
0x1800314a8  lea     r9, [rbp+260h+var_140]
0x1800314af  mov     r8d, edi
0x1800314b2  mov     edx, 831h
0x1800314b7  xor     ecx, ecx
0x1800314b9  call    cs:__imp_WinSqmAddToStream
0x1800314bf  lea     r9, [rbp+260h+var_B0]
0x1800314c6  mov     r8d, edi
0x1800314c9  mov     edx, 832h
0x1800314ce  xor     ecx, ecx
0x1800314d0  call    cs:__imp_WinSqmAddToStream
0x1800314d6  mov     rcx, rbx; hObject
0x1800314d9  call    cs:__imp_CloseHandle
0x1800314df  mov     rcx, rsi; Block
0x1800314e2  call    cs:__imp_free
0x1800314e8  mov     ebx, [rsp+360h+var_318]
0x1800314ec  lea     rcx, [rsp+360h+var_320]; this
0x1800314f1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1800314f6  mov     eax, ebx
0x1800314f8  mov     rcx, [rbp+260h+var_20]
0x1800314ff  xor     rcx, rsp; StackCookie
0x180031502  call    __security_check_cookie
0x180031507  lea     r11, [rsp+360h+var_10]
0x18003150f  mov     rbx, [r11+28h]
0x180031513  mov     rsi, [r11+30h]
0x180031517  mov     rsp, r11
0x18003151a  pop     r14
0x18003151c  pop     rdi
0x18003151d  pop     rbp
0x18003151e  retn
```
