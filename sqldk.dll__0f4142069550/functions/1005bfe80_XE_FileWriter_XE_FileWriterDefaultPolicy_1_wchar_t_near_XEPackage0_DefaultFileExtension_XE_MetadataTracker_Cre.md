# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CreateIndexLog(XE_Log *)

- ea: `0x1005bfe80`
- end: `0x1005c01e9`
- name: `?CreateIndexLog@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@@Z`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1005be5b0`

## callees

- `0x100403070`
- `0x100444860`
- `0x1005bfe80`
- `0x1005c0470`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x1005bfec3`
- `KERNEL32!SystemTimeToFileTime` at `0x1005bfec3`
- `KERNEL32!SetEndOfFile` at `0x1005c005d`
- `KERNEL32!SetEndOfFile` at `0x1005c0137`
- `KERNEL32!SetEndOfFile` at `0x1005c005d`
- `KERNEL32!SetEndOfFile` at `0x1005c0137`
- `KERNEL32!SetFilePointerEx` at `0x1005c004c`
- `KERNEL32!SetFilePointerEx` at `0x1005c0126`
- `KERNEL32!SetFilePointerEx` at `0x1005c004c`
- `KERNEL32!SetFilePointerEx` at `0x1005c0126`
- `KERNEL32!CloseHandle` at `0x1005bfffd`
- `KERNEL32!CloseHandle` at `0x1005c0157`
- `KERNEL32!CloseHandle` at `0x1005bfffd`
- `KERNEL32!CloseHandle` at `0x1005c0157`
- `KERNEL32!GetLastError` at `0x1005c0071`
- `KERNEL32!GetLastError` at `0x1005c00e3`
- `KERNEL32!GetLastError` at `0x1005c017c`
- `KERNEL32!GetLastError` at `0x1005c01ab`
- `KERNEL32!GetLastError` at `0x1005c0071`
- `KERNEL32!GetLastError` at `0x1005c00e3`
- `KERNEL32!GetLastError` at `0x1005c017c`
- `KERNEL32!GetLastError` at `0x1005c01ab`

## pseudocode

```c
__int64 __fastcall XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CreateIndexLog(
        _QWORD *a1,
        __int64 a2)
{
  unsigned int v4; // r15d
  struct _FILETIME v5; // rdx
  __int64 v6; // r9
  _WORD *v7; // r8
  __int16 v8; // ax
  _WORD *v9; // rax
  __int64 v10; // rax
  void *v11; // rcx
  void *v12; // rdi
  __int64 v13; // rax
  unsigned __int64 v14; // rdx
  int v15; // eax
  __int64 *v16; // rdi
  __int64 v17; // rsi
  DWORD LastError; // eax
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  DWORD v21; // eax
  void *v22; // rcx
  void *v23; // rcx
  DWORD v25; // eax
  __int64 *v26; // rdi
  __int64 v27; // rsi
  DWORD v28; // eax
  __int64 v29; // [rsp+20h] [rbp-288h]
  int v30; // [rsp+28h] [rbp-280h]
  __int64 v31; // [rsp+30h] [rbp-278h]
  _QWORD *v32; // [rsp+38h] [rbp-270h]
  struct _FILETIME FileTime; // [rsp+40h] [rbp-268h] BYREF
  SYSTEMTIME SystemTime; // [rsp+48h] [rbp-260h] BYREF
  _BYTE v35[528]; // [rsp+60h] [rbp-248h] BYREF

  v4 = 0;
  SystemTime = *(SYSTEMTIME *)(a2 + 72);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    goto LABEL_49;
  v5 = FileTime;
  if ( *(__int64 *)&FileTime < 0 )
    v5 = (struct _FILETIME)-*(__int64 *)&FileTime;
  LODWORD(v31) = 1;
  v30 = 1;
  if ( !*(_QWORD *)&v5 )
    v5 = (struct _FILETIME)1LL;
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))XE_LogSpecs::LogSpec::CreateFilePathInternal)(
                       a1 + 6,
                       v5,
                       v35,
                       260,
                       &SystemTime,
                       v30,
                       v31) )
  {
    v6 = 260;
    v7 = (_WORD *)(a2 + 112);
    do
    {
      if ( v6 == -2147483386 )
        break;
      v8 = *(_WORD *)&v35[(_QWORD)v7 - 112 - a2];
      if ( !v8 )
        break;
      *v7++ = v8;
      --v6;
    }
    while ( v6 );
    v9 = v7 - 1;
    if ( v6 )
      v9 = v7;
    *v9 = 0;
    *(_QWORD *)(a2 + 104) = a2 + 112;
    if ( qword_100715060 && (unsigned __int8)qword_100715060(a2 + 112, 260) )
    {
      *(_DWORD *)(a2 + 52) = 1;
      v32 = a1 + 211;
      v31 = 0;
      v30 = 671088768;
      LODWORD(v29) = 1;
      a1[226] = 1;
      v10 = qword_100715068(v35, 0x40000000, 1, 0, v29, v30, v31, v32);
    }
    else
    {
      v31 = 0;
      v30 = 671088768;
      LODWORD(v29) = 1;
      *(_DWORD *)(a2 + 52) = 0;
      v10 = qword_100714F18(v35, 0x40000000, 1, 0, v29, v30, v31);
    }
    v11 = *(void **)(a2 + 632);
    v12 = (void *)v10;
    if ( v11 != (void *)-1LL && v11 != (void *)v10 )
      CloseHandle(v11);
    *(_QWORD *)(a2 + 632) = v12;
    if ( v12 != (void *)-1LL )
    {
      v13 = a1[4];
      *(_QWORD *)(a2 + 16) = v13;
      if ( v13 )
      {
        v14 = *(unsigned int *)(a2 + 8)
            * (((unsigned __int64)*(unsigned int *)(a2 + 8) + v13 - 1)
             / *(unsigned int *)(a2 + 8));
        if ( *(_DWORD *)(a2 + 52) )
        {
          v15 = qword_100715080(v12, v14);
        }
        else
        {
          if ( !SetFilePointerEx(v12, (LARGE_INTEGER)v14, 0, 0) )
          {
LABEL_27:
            v16 = (__int64 *)a1[207];
            v17 = *v16;
            LastError = GetLastError();
            (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _BYTE *))(v17 + 56))(
              v16,
              LastError,
              *(_QWORD *)(a2 + 16),
              v35);
            goto LABEL_34;
          }
          v15 = SetEndOfFile(*(HANDLE *)(a2 + 632));
        }
        if ( !v15 )
          goto LABEL_27;
      }
      else
      {
        *(_QWORD *)(a2 + 16) = a1[3];
        if ( *(_DWORD *)(a2 + 52) )
        {
          v19 = a1[3];
          v20 = v19
              ? *(unsigned int *)(a2 + 8)
              * (((unsigned __int64)*(unsigned int *)(a2 + 8) + v19 - 1)
               / *(unsigned int *)(a2 + 8))
              : 0LL;
          v4 = qword_100715080(v12, v20);
          if ( !v4 )
            goto LABEL_34;
        }
      }
      v4 = XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteFileHeader(
             a1,
             a2);
      if ( v4 )
      {
        *(_DWORD *)(a2 + 48) = 0;
        return v4;
      }
LABEL_34:
      v21 = GetLastError();
      (*(void (__fastcall **)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(_QWORD *)a1[207] + 48LL))(a1[207], v21, v35, 0);
      v22 = *(void **)(a2 + 632);
      if ( v22 != (void *)-1LL )
      {
        if ( *(_DWORD *)(a2 + 52) )
        {
          qword_100715080(v22, 0);
        }
        else if ( SetFilePointerEx(v22, 0, 0, 0) )
        {
          SetEndOfFile(*(HANDLE *)(a2 + 632));
        }
        v23 = *(void **)(a2 + 632);
        if ( *(_DWORD *)(a2 + 52) )
        {
          qword_100715090(v23);
        }
        else if ( v23 != (void *)-1LL )
        {
          CloseHandle(v23);
        }
        *(_QWORD *)(a2 + 632) = -1;
      }
      *(_QWORD *)(a2 + 648) = 0;
      return v4;
    }
    v25 = GetLastError();
    if ( v25 != 80 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _BYTE *, _QWORD))(*(_QWORD *)a1[207] + 48LL))(a1[207], v25, v35, 0);
  }
  else
  {
LABEL_49:
    v26 = (__int64 *)a1[207];
    v27 = *v26;
    v28 = GetLastError();
    (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v27 + 48))(v26, v28, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1005bfe80  mov     [rsp+arg_10], rbx
0x1005bfe85  push    rbp
0x1005bfe86  push    rsi
0x1005bfe87  push    rdi
0x1005bfe88  push    r14
0x1005bfe8a  push    r15
0x1005bfe8c  sub     rsp, 280h
0x1005bfe93  mov     rax, cs:__security_cookie
0x1005bfe9a  xor     rax, rsp
0x1005bfe9d  mov     [rsp+2A8h+var_38], rax
0x1005bfea5  movups  xmm0, xmmword ptr [rdx+48h]
0x1005bfea9  mov     rbp, rdx
0x1005bfeac  mov     r14, rcx
0x1005bfeaf  xor     ebx, ebx
0x1005bfeb1  lea     rdx, [rsp+2A8h+FileTime]; lpFileTime
0x1005bfeb6  lea     rcx, [rsp+2A8h+SystemTime]; lpSystemTime
0x1005bfebb  mov     r15d, ebx
0x1005bfebe  movups  xmmword ptr [rsp+2A8h+SystemTime.wYear], xmm0
0x1005bfec3  call    cs:__imp_SystemTimeToFileTime
0x1005bfec9  test    eax, eax
0x1005bfecb  jz      loc_1005C01A1
0x1005bfed1  mov     rdx, qword ptr [rsp+2A8h+FileTime.dwLowDateTime]
0x1005bfed6  test    rdx, rdx
0x1005bfed9  jns     short loc_1005BFEDE
0x1005bfedb  neg     rdx
0x1005bfede  mov     edi, 1
0x1005bfee3  lea     rax, [rsp+2A8h+SystemTime]
0x1005bfee8  test    rdx, rdx
0x1005bfeeb  mov     dword ptr [rsp+2A8h+var_278], edi
0x1005bfeef  mov     [rsp+2A8h+var_280], edi
0x1005bfef3  lea     rcx, [r14+30h]
0x1005bfef7  cmovz   rdx, rdi
0x1005bfefb  mov     [rsp+2A8h+var_288], rax
0x1005bff00  mov     r9d, 104h
0x1005bff06  lea     r8, [rsp+2A8h+var_248]
0x1005bff0b  call    ?CreateFilePathInternal@LogSpec@XE_LogSpecs@@AEBAH_JQEA_WIAEBU_SYSTEMTIME@@IW4XE_FileSourceType@@@Z; XE_LogSpecs::LogSpec::CreateFilePathInternal(__int64,wchar_t * const,uint,_SYSTEMTIME const &,uint,XE_FileSourceType)
0x1005bff10  test    eax, eax
0x1005bff12  jz      loc_1005C01A1
0x1005bff18  lea     r10, [rbp+70h]
0x1005bff1c  mov     r9d, 104h
0x1005bff22  lea     rcx, [rsp+2A8h+var_248]
0x1005bff27  mov     r8, r10
0x1005bff2a  sub     rcx, r10
0x1005bff2d  nop     dword ptr [rax]
0x1005bff30  lea     rax, [r9+7FFFFEFAh]
0x1005bff37  test    rax, rax
0x1005bff3a  jz      short loc_1005BFF53
0x1005bff3c  movzx   eax, word ptr [r8+rcx]
0x1005bff41  test    ax, ax
0x1005bff44  jz      short loc_1005BFF53
0x1005bff46  mov     [r8], ax
0x1005bff4a  add     r8, 2
0x1005bff4e  sub     r9, rdi
0x1005bff51  jnz     short loc_1005BFF30
0x1005bff53  test    r9, r9
0x1005bff56  lea     rax, [r8-2]
0x1005bff5a  cmovnz  rax, r8
0x1005bff5e  mov     [rax], bx
0x1005bff61  mov     [rbp+68h], r10
0x1005bff65  mov     rax, cs:qword_100715060
0x1005bff6c  test    rax, rax
0x1005bff6f  jz      short loc_1005BFFBE
0x1005bff71  mov     edx, 104h
0x1005bff76  mov     rcx, r10
0x1005bff79  call    rax ; qword_100715060
0x1005bff7b  test    al, al
0x1005bff7d  jz      short loc_1005BFFBE
0x1005bff7f  lea     rax, [r14+698h]
0x1005bff86  mov     [rbp+34h], edi
0x1005bff89  mov     [rsp+2A8h+var_270], rax
0x1005bff8e  lea     rcx, [rsp+2A8h+var_248]
0x1005bff93  mov     [rsp+2A8h+var_278], rbx
0x1005bff98  xor     r9d, r9d
0x1005bff9b  mov     [rsp+2A8h+var_280], 28000080h
0x1005bffa3  mov     r8d, edi
0x1005bffa6  mov     edx, 40000000h
0x1005bffab  mov     dword ptr [rsp+2A8h+var_288], edi
0x1005bffaf  mov     [r14+710h], rdi
0x1005bffb6  call    cs:qword_100715068
0x1005bffbc  jmp     short loc_1005BFFE8
0x1005bffbe  mov     [rsp+2A8h+var_278], rbx
0x1005bffc3  lea     rcx, [rsp+2A8h+var_248]
0x1005bffc8  mov     [rsp+2A8h+var_280], 28000080h
0x1005bffd0  xor     r9d, r9d
0x1005bffd3  mov     r8d, edi
0x1005bffd6  mov     dword ptr [rsp+2A8h+var_288], edi
0x1005bffda  mov     edx, 40000000h
0x1005bffdf  mov     [rbp+34h], ebx
0x1005bffe2  call    cs:qword_100714F18
0x1005bffe8  mov     rcx, [rbp+278h]; hObject
0x1005bffef  mov     rdi, rax
0x1005bfff2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005bfff6  jz      short loc_1005C0003
0x1005bfff8  cmp     rcx, rax
0x1005bfffb  jz      short loc_1005C0003
0x1005bfffd  call    cs:__imp_CloseHandle
0x1005c0003  mov     [rbp+278h], rdi
0x1005c000a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1005c000e  jz      loc_1005C017C
0x1005c0014  mov     rax, [r14+20h]
0x1005c0018  mov     [rbp+10h], rax
0x1005c001c  test    rax, rax
0x1005c001f  jz      short loc_1005C008A
0x1005c0021  mov     ecx, [rbp+8]
0x1005c0024  dec     rax
0x1005c0027  add     rax, rcx
0x1005c002a  xor     edx, edx
0x1005c002c  div     rcx
0x1005c002f  imul    rax, rcx
0x1005c0033  mov     rcx, rdi; hFile
0x1005c0036  mov     rdx, rax; liDistanceToMove
0x1005c0039  cmp     [rbp+34h], ebx
0x1005c003c  jz      short loc_1005C0046
0x1005c003e  call    cs:qword_100715080
0x1005c0044  jmp     short loc_1005C0063
0x1005c0046  xor     r9d, r9d; dwMoveMethod
0x1005c0049  xor     r8d, r8d; lpNewFilePointer
0x1005c004c  call    cs:__imp_SetFilePointerEx
0x1005c0052  test    eax, eax
0x1005c0054  jz      short loc_1005C0067
0x1005c0056  mov     rcx, [rbp+278h]; hFile
0x1005c005d  call    cs:__imp_SetEndOfFile
0x1005c0063  test    eax, eax
0x1005c0065  jnz     short loc_1005C00CA
0x1005c0067  mov     rdi, [r14+678h]
0x1005c006e  mov     rsi, [rdi]
0x1005c0071  call    cs:__imp_GetLastError
0x1005c0077  mov     r8, [rbp+10h]
0x1005c007b  lea     r9, [rsp+2A8h+var_248]
0x1005c0080  mov     edx, eax
0x1005c0082  mov     rcx, rdi
0x1005c0085  call    qword ptr [rsi+38h]
0x1005c0088  jmp     short loc_1005C00E3
0x1005c008a  mov     rax, [r14+18h]
0x1005c008e  mov     [rbp+10h], rax
0x1005c0092  cmp     [rbp+34h], ebx
0x1005c0095  jz      short loc_1005C00CA
0x1005c0097  mov     rax, [r14+18h]
0x1005c009b  test    rax, rax
0x1005c009e  jz      short loc_1005C00B4
0x1005c00a0  mov     ecx, [rbp+8]
0x1005c00a3  dec     rax
0x1005c00a6  add     rax, rcx
0x1005c00a9  xor     edx, edx
0x1005c00ab  div     rcx
0x1005c00ae  imul    rax, rcx
0x1005c00b2  jmp     short loc_1005C00B7
0x1005c00b4  mov     rax, rbx
0x1005c00b7  mov     rdx, rax
0x1005c00ba  mov     rcx, rdi
0x1005c00bd  call    cs:qword_100715080
0x1005c00c3  mov     r15d, eax
0x1005c00c6  test    eax, eax
0x1005c00c8  jz      short loc_1005C00E3
0x1005c00ca  mov     eax, [rbp+28h]
0x1005c00cd  mov     rdx, rbp
0x1005c00d0  mov     rcx, r14
0x1005c00d3  call    ?WriteFileHeader@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@@Z; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteFileHeader(XE_Log *)
0x1005c00d8  mov     r15d, eax
0x1005c00db  test    eax, eax
0x1005c00dd  jnz     loc_1005C0174
0x1005c00e3  call    cs:__imp_GetLastError
0x1005c00e9  mov     rcx, [r14+678h]
0x1005c00f0  lea     r8, [rsp+2A8h+var_248]
0x1005c00f5  xor     r9d, r9d
0x1005c00f8  mov     edx, eax
0x1005c00fa  mov     r10, [rcx]
0x1005c00fd  call    qword ptr [r10+30h]
0x1005c0101  mov     rcx, [rbp+278h]; hFile
0x1005c0108  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005c010c  jz      short loc_1005C0168
0x1005c010e  cmp     [rbp+34h], ebx
0x1005c0111  jz      short loc_1005C011D
0x1005c0113  xor     edx, edx
0x1005c0115  call    cs:qword_100715080
0x1005c011b  jmp     short loc_1005C013D
0x1005c011d  xor     r9d, r9d; dwMoveMethod
0x1005c0120  xor     r8d, r8d; lpNewFilePointer
0x1005c0123  mov     rdx, rbx; liDistanceToMove
0x1005c0126  call    cs:__imp_SetFilePointerEx
0x1005c012c  test    eax, eax
0x1005c012e  jz      short loc_1005C013D
0x1005c0130  mov     rcx, [rbp+278h]; hFile
0x1005c0137  call    cs:__imp_SetEndOfFile
0x1005c013d  mov     rcx, [rbp+278h]; hObject
0x1005c0144  cmp     [rbp+34h], ebx
0x1005c0147  jz      short loc_1005C0151
0x1005c0149  call    cs:qword_100715090
0x1005c014f  jmp     short loc_1005C015D
0x1005c0151  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005c0155  jz      short loc_1005C015D
0x1005c0157  call    cs:__imp_CloseHandle
0x1005c015d  mov     qword ptr [rbp+278h], 0FFFFFFFFFFFFFFFFh
0x1005c0168  mov     [rbp+288h], rbx
0x1005c016f  test    r15d, r15d
0x1005c0172  jz      short loc_1005C0177
0x1005c0174  mov     [rbp+30h], ebx
0x1005c0177  mov     eax, r15d
0x1005c017a  jmp     short loc_1005C01C2
0x1005c017c  call    cs:__imp_GetLastError
0x1005c0182  cmp     eax, 50h ; 'P'
0x1005c0185  jz      short loc_1005C01C0
0x1005c0187  mov     rcx, [r14+678h]
0x1005c018e  lea     r8, [rsp+2A8h+var_248]
0x1005c0193  xor     r9d, r9d
0x1005c0196  mov     edx, eax
0x1005c0198  mov     r10, [rcx]
0x1005c019b  call    qword ptr [r10+30h]
0x1005c019f  jmp     short loc_1005C01C0
0x1005c01a1  mov     rdi, [r14+678h]
0x1005c01a8  mov     rsi, [rdi]
0x1005c01ab  call    cs:__imp_GetLastError
0x1005c01b1  movzx   r9d, bx
0x1005c01b5  xor     r8d, r8d
0x1005c01b8  mov     edx, eax
0x1005c01ba  mov     rcx, rdi
0x1005c01bd  call    qword ptr [rsi+30h]
0x1005c01c0  mov     eax, ebx
0x1005c01c2  mov     rcx, [rsp+2A8h+var_38]
0x1005c01ca  xor     rcx, rsp; StackCookie
0x1005c01cd  call    __security_check_cookie
0x1005c01d2  mov     rbx, [rsp+2A8h+arg_10]
0x1005c01da  add     rsp, 280h
0x1005c01e1  pop     r15
0x1005c01e3  pop     r14
0x1005c01e5  pop     rdi
0x1005c01e6  pop     rsi
0x1005c01e7  pop     rbp
0x1005c01e8  retn
```
