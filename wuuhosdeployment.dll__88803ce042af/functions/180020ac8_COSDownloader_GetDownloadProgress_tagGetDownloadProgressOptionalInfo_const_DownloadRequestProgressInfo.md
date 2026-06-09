# COSDownloader::GetDownloadProgress(tagGetDownloadProgressOptionalInfo const &,DownloadRequestProgressInfo *)

- ea: `0x180020ac8`
- end: `0x180020e8b`
- name: `?GetDownloadProgress@COSDownloader@@QEAAJAEBUtagGetDownloadProgressOptionalInfo@@PEAVDownloadRequestProgressInfo@@@Z`
- size: `963`
- prototype: `int(COSDownloader *__hidden this, const struct tagGetDownloadProgressOptionalInfo *, struct DownloadRequestProgressInfo *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800250b0`
- `0x180025180`

## callees

- `0x180003950`
- `0x18000956c`
- `0x180020ac8`
- `0x1800430f8`
- `0x1800492e0`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b44`

## string_xrefs

- `0x180020c99`: `DumpProgressInfo: cbServiceStackAndMetadataBytes = %I64u; cbLastRequestBytes = %I64u; cbTotalRequestBytes = %I64u; cbTotalPayloadBytes = %I64u; cbPredownloadingBytes = %I64u; dwPercentage = %d; fServiceStackAndMetadataFilesDownloaded = %ws.`
- `0x180020e5b`: `pPercentCompleteAsOfLastGdr = %d; cbDownloaded = %I64u;pTotalBytesExpected = %I64u;pSubPhase = %lu;pdwPercentSubPhase = %lu;m_fGeneratingRequest = %ws;m_fGDRCalled = %ws.`

## pseudocode

```c
__int64 __fastcall COSDownloader::GetDownloadProgress(
        COSDownloader *this,
        const struct tagGetDownloadProgressOptionalInfo *a2,
        struct DownloadRequestProgressInfo *a3)
{
  __int64 v7; // rax
  _OWORD *v8; // rcx
  unsigned int v9; // ebp
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r10
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80004003LL,
      v21);
    return 2147500035LL;
  }
  memset(a3, 0, 0xC0u);
  *((_DWORD *)a3 + 7) = -1;
  *((_DWORD *)a3 + 6) = 1;
  if ( this != (COSDownloader *)-208LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( *((_QWORD *)this + 32) )
    goto LABEL_20;
  v7 = *((_QWORD *)a2 + 2);
  if ( !v7 || !*(_QWORD *)(v7 + 8) )
  {
    *((_DWORD *)a3 + 6) = 1;
    v9 = 0;
    goto LABEL_17;
  }
  v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v8 )
  {
    *v8 = 0;
    v8[1] = 0;
    v8[2] = 0;
    *((_QWORD *)v8 + 6) = 0;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 32) = v8;
  v9 = v8 == 0 ? 0x8007000E : 0;
  if ( v8 )
  {
    memmove(v8, *(const void **)(*((_QWORD *)a2 + 2) + 8LL), **((unsigned int **)a2 + 2));
    if ( **((_BYTE **)this + 32) != 4 )
    {
      v9 = -2145112065;
      v10 = 1100;
      goto LABEL_15;
    }
LABEL_20:
    if ( this != (COSDownloader *)-208LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    WUTrace(0, 0, 4096, 5);
    v11 = *((_QWORD *)this + 32);
    v12 = *(_QWORD *)(v11 + 8);
    if ( !v12 )
    {
      *((_DWORD *)a3 + 6) = 1;
      return 0;
    }
    if ( !*(_BYTE *)(v11 + 52) )
    {
      *((_DWORD *)a3 + 6) = 1;
      v13 = (unsigned __int64)(100LL * *((_QWORD *)a2 + 1)) / *(_QWORD *)(*((_QWORD *)this + 32) + 8LL);
      if ( v13 > 0x64 )
        LODWORD(v13) = 100;
      *((_DWORD *)a3 + 7) = v13;
      goto LABEL_53;
    }
    if ( *((_DWORD *)this + 118) == 1 )
    {
      *(_DWORD *)a3 = 0;
      *((_DWORD *)a3 + 7) = 100;
      *((_QWORD *)a3 + 2) = 0;
      *((_DWORD *)a3 + 6) = 1;
LABEL_53:
      WUTrace(0, 0, 4096, 5);
      return 0;
    }
    if ( *((_BYTE *)this + 17) )
    {
      *((_DWORD *)a3 + 6) = 3;
      LODWORD(v14) = *((_DWORD *)a2 + 6);
LABEL_52:
      *((_DWORD *)a3 + 7) = v14;
      goto LABEL_53;
    }
    if ( *(_QWORD *)(v11 + 24) )
    {
      if ( *(_QWORD *)(v11 + 40) )
      {
        v16 = *(_QWORD *)(v11 + 16);
        v17 = *(_QWORD *)(v11 + 32);
        *((_QWORD *)a3 + 2) = *(_QWORD *)(v11 + 40) + v16 + v12;
        v18 = *((_QWORD *)a2 + 1);
        if ( v18 > v16 + v12 )
          v19 = v18 - v12 - v16;
        else
          v19 = 0;
        v20 = v17 - v16;
        if ( v20 )
        {
          v14 = 100 * v19 / v20;
          if ( v14 > 0x64 )
            LODWORD(v14) = 100;
        }
        else
        {
          LODWORD(v14) = 0;
        }
        *(_DWORD *)a3 = v14;
        *((_DWORD *)a3 + 6) = 4;
      }
      else
      {
        *((_DWORD *)a3 + 6) = 2;
        v14 = (unsigned __int64)(100LL * *((_QWORD *)a2 + 1)) / *(_QWORD *)(*((_QWORD *)this + 32) + 24LL);
        if ( v14 > 0x64 )
          LODWORD(v14) = 100;
      }
      goto LABEL_52;
    }
    if ( *((_BYTE *)this + 18) )
    {
      if ( *(_QWORD *)(v11 + 40) )
      {
        *(_DWORD *)a3 = 100;
        v15 = *(_QWORD *)(*((_QWORD *)this + 32) + 8LL)
            + *(_QWORD *)(*((_QWORD *)this + 32) + 16LL)
            + *(_QWORD *)(v11 + 40);
        *((_DWORD *)a3 + 6) = 4;
        *((_DWORD *)a3 + 7) = 100;
        goto LABEL_39;
      }
      *((_QWORD *)a3 + 3) = 4;
    }
    else
    {
      *((_QWORD *)a3 + 3) = 2;
    }
    *(_DWORD *)a3 = 0;
    v15 = 0;
LABEL_39:
    *((_QWORD *)a3 + 2) = v15;
    goto LABEL_53;
  }
  v10 = 1091;
LABEL_15:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
    (const char *)v9,
    v21);
LABEL_17:
  if ( this != (COSDownloader *)-208LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return v9;
}

```

## disassembly

```asm
0x180020ac8  mov     [rsp+arg_18], rbx
0x180020acd  push    rbp
0x180020ace  push    rsi
0x180020acf  push    rdi
0x180020ad0  push    r12
0x180020ad2  push    r13
0x180020ad4  push    r14
0x180020ad6  push    r15
0x180020ad8  sub     rsp, 70h
0x180020adc  xor     r12d, r12d
0x180020adf  mov     rdi, r8
0x180020ae2  mov     r15, rdx
0x180020ae5  mov     r14, rcx
0x180020ae8  test    r8, r8
0x180020aeb  jnz     short loc_180020B15
0x180020aed  mov     rcx, [rsp+0A8h]; this
0x180020af5  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180020afc  mov     ebx, 80004003h
0x180020b01  mov     edx, 42Fh; void *
0x180020b06  mov     r9d, ebx; char *
0x180020b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b0e  mov     eax, ebx
0x180020b10  jmp     loc_180020E73
0x180020b15  xor     edx, edx; Val
0x180020b17  mov     r8d, 0C0h; Size
0x180020b1d  mov     rcx, rdi; void *
0x180020b20  call    memset
0x180020b25  lea     rbx, [r14+0D0h]
0x180020b2c  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180020b33  mov     esi, 1
0x180020b38  mov     [rdi+18h], esi
0x180020b3b  test    rbx, rbx
0x180020b3e  jz      short loc_180020B4A
0x180020b40  lea     rcx, [rbx+8]; lpCriticalSection
0x180020b44  call    cs:__imp_EnterCriticalSection
0x180020b4a  mov     r13d, 4
0x180020b50  cmp     [r14+100h], r12
0x180020b57  jnz     loc_180020C23
0x180020b5d  mov     rax, [r15+10h]
0x180020b61  test    rax, rax
0x180020b64  jz      loc_180020C07
0x180020b6a  cmp     [rax+8], r12
0x180020b6e  jz      loc_180020C07
0x180020b74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020b7b  lea     ecx, [r13+34h]; unsigned __int64
0x180020b7f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020b84  mov     rcx, rax
0x180020b87  test    rax, rax
0x180020b8a  jz      short loc_180020BA2
0x180020b8c  xorps   xmm0, xmm0
0x180020b8f  xor     eax, eax
0x180020b91  movups  xmmword ptr [rcx], xmm0
0x180020b94  movups  xmmword ptr [rcx+10h], xmm0
0x180020b98  movups  xmmword ptr [rcx+20h], xmm0
0x180020b9c  mov     [rcx+30h], rax
0x180020ba0  jmp     short loc_180020BA5
0x180020ba2  mov     rcx, r12; void *
0x180020ba5  mov     rax, rcx
0x180020ba8  mov     [r14+100h], rcx
0x180020baf  neg     rax
0x180020bb2  sbb     ebp, ebp
0x180020bb4  not     ebp
0x180020bb6  and     ebp, 8007000Eh
0x180020bbc  test    rcx, rcx
0x180020bbf  jnz     short loc_180020BC8
0x180020bc1  mov     edx, 443h
0x180020bc6  jmp     short loc_180020BEE
0x180020bc8  mov     rdx, [r15+10h]
0x180020bcc  mov     r8d, [rdx]; Size
0x180020bcf  mov     rdx, [rdx+8]; Src
0x180020bd3  call    memmove
0x180020bd8  mov     rax, [r14+100h]
0x180020bdf  cmp     [rax], r13b
0x180020be2  jz      short loc_180020C23
0x180020be4  mov     ebp, 80242FFFh
0x180020be9  mov     edx, 44Ch; void *
0x180020bee  mov     rcx, [rsp+0A8h]; this
0x180020bf6  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180020bfd  mov     r9d, ebp; char *
0x180020c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c05  jmp     short loc_180020C0D
0x180020c07  mov     [rdi+18h], esi
0x180020c0a  mov     ebp, r12d
0x180020c0d  test    rbx, rbx
0x180020c10  jz      short loc_180020C1C
0x180020c12  lea     rcx, [rbx+8]; lpCriticalSection
0x180020c16  call    cs:__imp_LeaveCriticalSection
0x180020c1c  mov     eax, ebp
0x180020c1e  jmp     loc_180020E73
0x180020c23  test    rbx, rbx
0x180020c26  jz      short loc_180020C32
0x180020c28  lea     rcx, [rbx+8]; lpCriticalSection
0x180020c2c  call    cs:__imp_LeaveCriticalSection
0x180020c32  mov     rcx, [r14+100h]
0x180020c39  lea     rbx, aFalse_0; "FALSE"
0x180020c40  lea     rbp, aTrue; "TRUE"
0x180020c47  mov     rax, rbx
0x180020c4a  mov     r8d, 1000h
0x180020c50  cmp     [rcx+34h], r12b
0x180020c54  cmovnz  rax, rbp
0x180020c58  xor     edx, edx
0x180020c5a  mov     [rsp+0A8h+var_48], rax
0x180020c5f  mov     eax, [rcx+30h]
0x180020c62  mov     dword ptr [rsp+0A8h+var_50], eax
0x180020c66  mov     rax, [rcx+10h]
0x180020c6a  lea     r9d, [rdx+5]
0x180020c6e  mov     [rsp+0A8h+var_58], rax
0x180020c73  mov     rax, [rcx+28h]
0x180020c77  mov     [rsp+0A8h+var_60], rax
0x180020c7c  mov     rax, [rcx+20h]
0x180020c80  mov     [rsp+0A8h+var_68], rax
0x180020c85  mov     rax, [rcx+18h]
0x180020c89  mov     [rsp+0A8h+var_70], rax
0x180020c8e  mov     rax, [rcx+8]
0x180020c92  xor     ecx, ecx
0x180020c94  mov     [rsp+0A8h+var_78], rax
0x180020c99  lea     rax, aDumpprogressin; "DumpProgressInfo: cbServiceStackAndMeta"...
0x180020ca0  mov     [rsp+0A8h+var_80], rax
0x180020ca5  mov     [rsp+0A8h+var_88], r12
0x180020caa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180020caf  mov     r8, [r14+100h]
0x180020cb6  mov     r10, [r8+8]
0x180020cba  test    r10, r10
0x180020cbd  jnz     short loc_180020CC7
0x180020cbf  mov     [rdi+18h], esi
0x180020cc2  jmp     loc_180020E71
0x180020cc7  cmp     [r8+34h], r12b
0x180020ccb  jnz     short loc_180020CF9
0x180020ccd  mov     [rdi+18h], esi
0x180020cd0  xor     edx, edx
0x180020cd2  imul    rax, [r15+8], 64h ; 'd'
0x180020cd7  mov     rcx, [r14+100h]
0x180020cde  div     qword ptr [rcx+8]
0x180020ce2  mov     edx, 64h ; 'd'
0x180020ce7  cmp     rax, rdx
0x180020cea  mov     rcx, rax
0x180020ced  cmova   rcx, rdx
0x180020cf1  mov     [rdi+1Ch], ecx
0x180020cf4  jmp     loc_180020E10
0x180020cf9  cmp     [r14+1D8h], esi
0x180020d00  jnz     short loc_180020D16
0x180020d02  mov     edx, 64h ; 'd'
0x180020d07  mov     [rdi], r12d
0x180020d0a  mov     [rdi+1Ch], edx
0x180020d0d  mov     [rdi+10h], r12
0x180020d11  mov     [rdi+18h], esi
0x180020d14  jmp     short loc_180020D84
0x180020d16  cmp     [r14+11h], r12b
0x180020d1a  jz      short loc_180020D2D
0x180020d1c  mov     esi, 3
0x180020d21  mov     [rdi+18h], esi
0x180020d24  mov     eax, [r15+18h]
0x180020d28  jmp     loc_180020E0B
0x180020d2d  cmp     [r8+18h], r12
0x180020d31  jnz     short loc_180020D8B
0x180020d33  cmp     [r14+12h], r12b
0x180020d37  jnz     short loc_180020D44
0x180020d39  mov     esi, 2
0x180020d3e  mov     [rdi+18h], rsi
0x180020d42  jmp     short loc_180020D51
0x180020d44  mov     esi, r13d
0x180020d47  cmp     [r8+28h], r12
0x180020d4b  jnz     short loc_180020D5C
0x180020d4d  mov     [rdi+18h], r13
0x180020d51  mov     [rdi], r12d
0x180020d54  mov     rax, r12
0x180020d57  mov     edx, r12d
0x180020d5a  jmp     short loc_180020D80
0x180020d5c  mov     edx, 64h ; 'd'
0x180020d61  mov     [rdi], edx
0x180020d63  mov     rax, [r14+100h]
0x180020d6a  mov     rcx, [rax+10h]
0x180020d6e  add     rcx, [rax+8]
0x180020d72  mov     rax, [r8+28h]
0x180020d76  add     rax, rcx
0x180020d79  mov     [rdi+18h], r13d
0x180020d7d  mov     [rdi+1Ch], edx
0x180020d80  mov     [rdi+10h], rax
0x180020d84  mov     ecx, edx
0x180020d86  jmp     loc_180020E10
0x180020d8b  cmp     [r8+28h], r12
0x180020d8f  jnz     short loc_180020DB7
0x180020d91  xor     edx, edx
0x180020d93  mov     esi, 2
0x180020d98  mov     [rdi+18h], esi
0x180020d9b  imul    rax, [r15+8], 64h ; 'd'
0x180020da0  mov     rcx, [r14+100h]
0x180020da7  div     qword ptr [rcx+18h]
0x180020dab  lea     edx, [rsi+62h]
0x180020dae  cmp     rax, rdx
0x180020db1  cmova   rax, rdx
0x180020db5  jmp     short loc_180020E0B
0x180020db7  mov     rdx, [r8+10h]
0x180020dbb  mov     r9, [r8+20h]
0x180020dbf  lea     rax, [rdx+r10]
0x180020dc3  add     rax, [r8+28h]
0x180020dc7  mov     [rdi+10h], rax
0x180020dcb  lea     rax, [rdx+r10]
0x180020dcf  mov     rcx, [r15+8]
0x180020dd3  cmp     rcx, rax
0x180020dd6  ja      short loc_180020DDD
0x180020dd8  mov     rcx, r12
0x180020ddb  jmp     short loc_180020DE3
0x180020ddd  sub     rcx, r10
0x180020de0  sub     rcx, rdx
0x180020de3  sub     r9, rdx
0x180020de6  jnz     short loc_180020DED
0x180020de8  mov     rax, r12
0x180020deb  jmp     short loc_180020E02
0x180020ded  xor     edx, edx
0x180020def  imul    rax, rcx, 64h ; 'd'
0x180020df3  div     r9
0x180020df6  mov     edx, 64h ; 'd'
0x180020dfb  cmp     rax, rdx
0x180020dfe  cmova   rax, rdx
0x180020e02  mov     [rdi], eax
0x180020e04  mov     esi, r13d
0x180020e07  mov     [rdi+18h], r13d
0x180020e0b  mov     [rdi+1Ch], eax
0x180020e0e  mov     ecx, eax
0x180020e10  cmp     [r14+12h], r12b
0x180020e14  mov     rax, rbx
0x180020e17  mov     r8d, 1000h
0x180020e1d  cmovnz  rax, rbp
0x180020e21  cmp     [r14+11h], r12b
0x180020e25  mov     [rsp+0A8h+var_48], rax
0x180020e2a  mov     rax, [rdi+10h]
0x180020e2e  cmovnz  rbx, rbp
0x180020e32  mov     [rsp+0A8h+var_50], rbx
0x180020e37  xor     edx, edx
0x180020e39  mov     dword ptr [rsp+0A8h+var_58], ecx
0x180020e3d  xor     ecx, ecx
0x180020e3f  mov     dword ptr [rsp+0A8h+var_60], esi
0x180020e43  mov     [rsp+0A8h+var_68], rax
0x180020e48  mov     rax, [r15+8]
0x180020e4c  lea     r9d, [rdx+5]
0x180020e50  mov     [rsp+0A8h+var_70], rax
0x180020e55  mov     eax, [rdi]
0x180020e57  mov     dword ptr [rsp+0A8h+var_78], eax
0x180020e5b  lea     rax, aPpercentcomple; "pPercentCompleteAsOfLastGdr = %d; cbDow"...
0x180020e62  mov     [rsp+0A8h+var_80], rax
0x180020e67  mov     [rsp+0A8h+var_88], r12
0x180020e6c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180020e71  xor     eax, eax
0x180020e73  mov     rbx, [rsp+0A8h+arg_18]
0x180020e7b  add     rsp, 70h
0x180020e7f  pop     r15
0x180020e81  pop     r14
0x180020e83  pop     r13
0x180020e85  pop     r12
0x180020e87  pop     rdi
0x180020e88  pop     rsi
0x180020e89  pop     rbp
0x180020e8a  retn
```
