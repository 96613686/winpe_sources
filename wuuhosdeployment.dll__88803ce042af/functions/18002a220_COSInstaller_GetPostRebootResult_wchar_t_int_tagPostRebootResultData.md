# COSInstaller::GetPostRebootResult(wchar_t *,int,tagPostRebootResultData *)

- ea: `0x18002a220`
- end: `0x18002a835`
- name: `?GetPostRebootResult@COSInstaller@@UEAAJPEA_WHPEAUtagPostRebootResultData@@@Z`
- size: `1557`
- prototype: `int(COSInstaller *__hidden this, wchar_t *, int, struct tagPostRebootResultData *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000c684`
- `0x18002a220`
- `0x18002c66c`
- `0x18002d114`
- `0x180031e88`
- `0x18003a228`
- `0x180042630`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18002a2c0`
- `OLEAUT32!__imp_SysStringLen` at `0x18002a2c0`

## string_xrefs

- `0x18002a2e9`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002a754`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18002a710`: `GetPostRebootResultFromUpdateAgent failed`
- `0x18002a6cf`: `Updateagent is in use. Will try again later`
- `0x18002a790`: `Using product info to determine if the update was successfully installed`
- `0x18002a7da`: `Reporting cookie product version and current installed product version match. We have successfully updated`

## pseudocode

```c
__int64 __fastcall COSInstaller::GetPostRebootResult(
        COSInstaller *this,
        wchar_t *a2,
        int a3,
        struct tagPostRebootResultData *a4)
{
  char v8; // r15
  int IsProductCurrent; // ebx
  __int64 v10; // rdx
  int v11; // edi
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  wchar_t *v16; // rbx
  COSInstaller *v17; // rcx
  int PostRebootResultFromUpdateAgent; // eax
  bool *v19; // r9
  int v20; // [rsp+20h] [rbp-A9h]
  unsigned __int64 v21; // [rsp+70h] [rbp-59h] BYREF
  wchar_t *v22; // [rsp+78h] [rbp-51h] BYREF
  wchar_t *v23; // [rsp+80h] [rbp-49h] BYREF
  wchar_t *v24; // [rsp+88h] [rbp-41h] BYREF
  wchar_t *v25; // [rsp+90h] [rbp-39h] BYREF
  wchar_t *v26; // [rsp+98h] [rbp-31h] BYREF
  wchar_t *v27; // [rsp+A0h] [rbp-29h] BYREF
  void *lpMem; // [rsp+A8h] [rbp-21h] BYREF
  wchar_t *v29; // [rsp+B0h] [rbp-19h] BYREF
  wchar_t *v30; // [rsp+B8h] [rbp-11h] BYREF
  wchar_t *v31; // [rsp+C0h] [rbp-9h] BYREF
  wchar_t *v32; // [rsp+C8h] [rbp-1h] BYREF
  wchar_t v33[4]; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v27 = 0;
  v23 = 0;
  v26 = 0;
  v32 = 0;
  v25 = 0;
  v31 = 0;
  v24 = 0;
  v30 = 0;
  v29 = 0;
  lpMem = 0;
  v8 = 0;
  *(_QWORD *)v33 = 0;
  v22 = 0;
  LOBYTE(v21) = 0;
  WUTrace(0, 0, 4096, 4);
  if ( !SysStringLen(a2) )
  {
    IsProductCurrent = -2147024809;
    v10 = 1464;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)IsProductCurrent,
      0);
    goto LABEL_30;
  }
  if ( !a4 )
  {
    IsProductCurrent = -2147467261;
    v10 = 1465;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    IsProductCurrent = -2145116156;
    goto LABEL_30;
  }
  *(_OWORD *)a4 = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  *(_DWORD *)a4 = -2145116138;
  if ( v29 )
    CSusBaseAllocTag<942762101>::operator delete(v29);
  if ( v30 )
    CSusBaseAllocTag<942762101>::operator delete(v30);
  if ( v24 )
    CSusBaseAllocTag<942762101>::operator delete(v24);
  if ( v31 )
    CSusBaseAllocTag<942762101>::operator delete(v31);
  if ( v25 )
    CSusBaseAllocTag<942762101>::operator delete(v25);
  if ( v32 )
    CSusBaseAllocTag<942762101>::operator delete(v32);
  if ( v26 )
    CSusBaseAllocTag<942762101>::operator delete(v26);
  if ( v23 )
    CSusBaseAllocTag<942762101>::operator delete(v23);
  if ( v27 )
    CSusBaseAllocTag<942762101>::operator delete(v27);
  IsProductCurrent = COSInstaller::ExtractReportingCookieData(
                       (COSInstaller *)((char *)this - 8),
                       a2,
                       &v27,
                       &v23,
                       &v26,
                       &v32,
                       &v25,
                       &v31,
                       &v24,
                       &v30,
                       &v29,
                       (wchar_t **)&lpMem,
                       (unsigned __int64 *)v33);
  v11 = IsProductCurrent;
  if ( IsProductCurrent != -2089484279 )
  {
    if ( IsProductCurrent < 0 )
    {
      v13 = (unsigned int)IsProductCurrent;
      v14 = 1507;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
        (const char *)v13,
        v20);
      goto LABEL_29;
    }
    if ( !v27 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1510;
      v13 = 2147500035LL;
      goto LABEL_80;
    }
    if ( !v23 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1511;
      v13 = 2147500035LL;
      goto LABEL_80;
    }
    if ( !v25 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1512;
      v13 = 2147500035LL;
      goto LABEL_80;
    }
    if ( !v24 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1513;
      v13 = 2147500035LL;
      goto LABEL_80;
    }
    if ( !v30 )
    {
      IsProductCurrent = -2147467261;
      v14 = 1514;
      v13 = 2147500035LL;
      goto LABEL_80;
    }
    v15 = ConvertFileVerToStringW(*(unsigned __int64 *)v33, &v22);
    IsProductCurrent = v15;
    v11 = v15;
    if ( v15 < 0 )
    {
      v13 = (unsigned int)v15;
      v14 = 1517;
      goto LABEL_80;
    }
    v16 = v26;
    if ( !v26 || !*v26 )
      v16 = v23;
    v11 = CheckIfDirExists(v16);
    if ( v11 < 0 )
    {
      v20 = 0;
      WUTrace(0, 0, 4096, 4);
    }
    else
    {
      WUTrace(0, 0, 4096, 4);
      PostRebootResultFromUpdateAgent = COSInstaller::GetPostRebootResultFromUpdateAgent(
                                          v17,
                                          v24,
                                          v23,
                                          v26,
                                          v32,
                                          v25,
                                          v31,
                                          v29,
                                          (wchar_t *const)lpMem,
                                          (bool *)&v21,
                                          a4);
      v8 = v21;
      v11 = PostRebootResultFromUpdateAgent;
      if ( PostRebootResultFromUpdateAgent < 0 )
      {
        if ( PostRebootResultFromUpdateAgent == -2147024864 )
        {
          WUTrace(0, 0, 4096, 3);
          *(_DWORD *)a4 = -2145116140;
          *((_DWORD *)a4 + 2) = 1;
          *((_DWORD *)a4 + 9) = 1;
LABEL_74:
          v11 = 0;
          goto LABEL_28;
        }
        if ( (_BYTE)v21 )
        {
          WUTrace(0, 0, 4096, 2);
          *(_DWORD *)a4 = -2145116138;
          goto LABEL_74;
        }
      }
      if ( PostRebootResultFromUpdateAgent >= 0 )
        goto LABEL_78;
    }
    if ( !v8 )
    {
      LOBYTE(v21) = 0;
      WUTrace(0, 0, 4096, 4);
      IsProductCurrent = ProductDatabase::GetIsProductCurrent((ProductDatabase *)v27, v33, &v21, v19);
      v11 = IsProductCurrent;
      if ( IsProductCurrent >= 0 )
      {
        if ( (_BYTE)v21 )
        {
          WUTrace(0, 0, 4096, 4);
          *(_DWORD *)a4 = 0;
          goto LABEL_29;
        }
        goto LABEL_28;
      }
      v20 = IsProductCurrent;
      WUTrace(0, 0, 4096, 2);
LABEL_79:
      v13 = (unsigned int)v11;
      v14 = 1626;
      goto LABEL_80;
    }
LABEL_78:
    IsProductCurrent = v11;
    if ( v11 >= 0 )
      goto LABEL_28;
    goto LABEL_79;
  }
  WUTrace(0, 0, 4096, 2);
LABEL_28:
  IsProductCurrent = 0;
LABEL_29:
  WUTrace(0, 0, 4096, ((v11 >> 31) & 0xFFFFFFFE) + 4);
LABEL_30:
  if ( v22 )
    CSusBaseAllocTag<942762101>::operator delete(v22);
  if ( lpMem )
  {
    CSusBaseAllocTag<942762101>::operator delete(lpMem);
    lpMem = 0;
  }
  if ( v29 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v30);
    v30 = 0;
  }
  if ( v24 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v24);
    v24 = 0;
  }
  if ( v31 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v31);
    v31 = 0;
  }
  if ( v25 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v25);
    v25 = 0;
  }
  if ( v32 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v32);
    v32 = 0;
  }
  if ( v26 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v26);
    v26 = 0;
  }
  if ( v23 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v23);
    v23 = 0;
  }
  if ( v27 )
    CSusBaseAllocTag<942762101>::operator delete(v27);
  return (unsigned int)IsProductCurrent;
}

```

## disassembly

```asm
0x18002a220  mov     [rsp-8+arg_10], rbx
0x18002a225  push    rbp
0x18002a226  push    rsi
0x18002a227  push    rdi
0x18002a228  push    r12
0x18002a22a  push    r13
0x18002a22c  push    r14
0x18002a22e  push    r15
0x18002a230  lea     rbp, [rsp-27h]
0x18002a235  sub     rsp, 0F0h
0x18002a23c  mov     rax, cs:__security_cookie
0x18002a243  xor     rax, rsp
0x18002a246  mov     [rbp+57h+var_40], rax
0x18002a24a  xor     r12d, r12d
0x18002a24d  mov     [rsp+120h+var_F0], rdx
0x18002a252  lea     rax, aEnterGetpostre; "Enter GetPostRebootResult for Deploymen"...
0x18002a259  mov     [rbp+57h+var_80], r12
0x18002a25d  mov     rsi, r9
0x18002a260  mov     [rsp+120h+var_F8], rax
0x18002a265  mov     ebx, r8d
0x18002a268  mov     [rbp+57h+var_A0], r12
0x18002a26c  mov     rdi, rdx
0x18002a26f  mov     [rbp+57h+var_88], r12
0x18002a273  mov     r14, rcx
0x18002a276  mov     [rbp+57h+var_58], r12
0x18002a27a  mov     r13d, 1000h
0x18002a280  mov     [rbp+57h+var_90], r12
0x18002a284  lea     r9d, [r12+4]
0x18002a289  mov     [rbp+57h+var_60], r12
0x18002a28d  mov     r8d, r13d
0x18002a290  mov     [rbp+57h+var_98], r12
0x18002a294  xor     edx, edx
0x18002a296  mov     [rbp+57h+var_68], r12
0x18002a29a  xor     ecx, ecx
0x18002a29c  mov     [rbp+57h+var_70], r12
0x18002a2a0  mov     [rbp+57h+lpMem], r12
0x18002a2a4  mov     r15b, r12b
0x18002a2a7  mov     qword ptr [rbp+57h+var_50], r12
0x18002a2ab  mov     [rbp+57h+var_A8], r12
0x18002a2af  mov     byte ptr [rbp+57h+var_B0], r12b
0x18002a2b3  mov     [rsp+120h+var_100], r12; int
0x18002a2b8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a2bd  mov     rcx, rdi; pbstr
0x18002a2c0  call    cs:__imp_SysStringLen
0x18002a2c6  test    eax, eax
0x18002a2c8  jnz     short loc_18002A2D6
0x18002a2ca  mov     ebx, 80070057h
0x18002a2cf  mov     edx, 5B8h
0x18002a2d4  jmp     short loc_18002A2E5
0x18002a2d6  test    rsi, rsi
0x18002a2d9  jnz     short loc_18002A2FD
0x18002a2db  mov     ebx, 80004003h
0x18002a2e0  mov     edx, 5B9h; void *
0x18002a2e5  mov     rcx, [rbp+5Fh]; this
0x18002a2e9  lea     r8, aCW1SSrcClientE_14; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18002a2f0  mov     r9d, ebx; char *
0x18002a2f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a2f8  jmp     loc_18002A471
0x18002a2fd  test    ebx, ebx
0x18002a2ff  jnz     short loc_18002A30B
0x18002a301  mov     ebx, 80242004h
0x18002a306  jmp     loc_18002A471
0x18002a30b  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18002a30f  xorps   xmm0, xmm0
0x18002a312  movups  xmmword ptr [rsi], xmm0
0x18002a315  xor     eax, eax
0x18002a317  movups  xmmword ptr [rsi+10h], xmm0
0x18002a31b  mov     [rsi+20h], rax
0x18002a31f  mov     dword ptr [rsi], 80242016h
0x18002a325  test    rcx, rcx
0x18002a328  jz      short loc_18002A32F
0x18002a32a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a32f  mov     rcx, [rbp+57h+var_70]; lpMem
0x18002a333  test    rcx, rcx
0x18002a336  jz      short loc_18002A33D
0x18002a338  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a33d  mov     rcx, [rbp+57h+var_68]; lpMem
0x18002a341  test    rcx, rcx
0x18002a344  jz      short loc_18002A34B
0x18002a346  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a34b  mov     rcx, [rbp+57h+var_98]; lpMem
0x18002a34f  test    rcx, rcx
0x18002a352  jz      short loc_18002A359
0x18002a354  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a359  mov     rcx, [rbp+57h+var_60]; lpMem
0x18002a35d  test    rcx, rcx
0x18002a360  jz      short loc_18002A367
0x18002a362  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a367  mov     rcx, [rbp+57h+var_90]; lpMem
0x18002a36b  test    rcx, rcx
0x18002a36e  jz      short loc_18002A375
0x18002a370  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a375  mov     rcx, [rbp+57h+var_58]; lpMem
0x18002a379  test    rcx, rcx
0x18002a37c  jz      short loc_18002A383
0x18002a37e  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a383  mov     rcx, [rbp+57h+var_88]; lpMem
0x18002a387  test    rcx, rcx
0x18002a38a  jz      short loc_18002A391
0x18002a38c  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a391  mov     rcx, [rbp+57h+var_A0]; lpMem
0x18002a395  test    rcx, rcx
0x18002a398  jz      short loc_18002A39F
0x18002a39a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a39f  mov     rcx, [rbp+57h+var_80]; lpMem
0x18002a3a3  test    rcx, rcx
0x18002a3a6  jz      short loc_18002A3AD
0x18002a3a8  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a3ad  lea     rax, [rbp+57h+var_50]
0x18002a3b1  mov     rdx, rdi; wchar_t *
0x18002a3b4  mov     [rsp+120h+var_C0], rax; unsigned __int64 *
0x18002a3b9  lea     rcx, [r14-8]; this
0x18002a3bd  lea     rax, [rbp+57h+lpMem]
0x18002a3c1  mov     [rsp+120h+var_C8], rax; wchar_t **
0x18002a3c6  lea     r9, [rbp+57h+var_A0]; wchar_t **
0x18002a3ca  lea     rax, [rbp+57h+var_70]
0x18002a3ce  mov     [rsp+120h+var_D0], rax; wchar_t **
0x18002a3d3  lea     r8, [rbp+57h+var_80]; wchar_t **
0x18002a3d7  lea     rax, [rbp+57h+var_68]
0x18002a3db  mov     [rsp+120h+var_D8], rax; wchar_t **
0x18002a3e0  lea     rax, [rbp+57h+var_98]
0x18002a3e4  mov     [rsp+120h+var_E0], rax; wchar_t **
0x18002a3e9  lea     rax, [rbp+57h+var_60]
0x18002a3ed  mov     [rsp+120h+var_E8], rax; wchar_t **
0x18002a3f2  lea     rax, [rbp+57h+var_90]
0x18002a3f6  mov     [rsp+120h+var_F0], rax; wchar_t **
0x18002a3fb  lea     rax, [rbp+57h+var_58]
0x18002a3ff  mov     [rsp+120h+var_F8], rax; wchar_t **
0x18002a404  lea     rax, [rbp+57h+var_88]
0x18002a408  mov     [rsp+120h+var_100], rax; wchar_t **
0x18002a40d  call    ?ExtractReportingCookieData@COSInstaller@@AEAAJPEA_WPEAPEA_W111111111PEA_K@Z; COSInstaller::ExtractReportingCookieData(wchar_t *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,wchar_t * *,unsigned __int64 *)
0x18002a412  mov     ebx, eax
0x18002a414  mov     edi, eax
0x18002a416  cmp     eax, 83750009h
0x18002a41b  jnz     loc_18002A558
0x18002a421  lea     rax, aExtractreporti; "ExtractReportingCookieData failed"
0x18002a428  mov     r9d, 2
0x18002a42e  mov     [rsp+120h+var_F8], rax
0x18002a433  mov     r8d, r13d
0x18002a436  xor     edx, edx
0x18002a438  mov     dword ptr [rsp+120h+var_100], ebx
0x18002a43c  xor     ecx, ecx
0x18002a43e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a443  mov     ebx, r12d
0x18002a446  mov     r9d, edi
0x18002a449  lea     rax, aLeaveGetpostre; "Leave GetPostRebootResult for Deploymen"...
0x18002a450  sar     r9d, 1Fh
0x18002a454  mov     r8d, r13d
0x18002a457  and     r9d, 0FFFFFFFEh
0x18002a45b  mov     [rsp+120h+var_F8], rax
0x18002a460  add     r9d, 4
0x18002a464  mov     dword ptr [rsp+120h+var_100], edi
0x18002a468  xor     edx, edx
0x18002a46a  xor     ecx, ecx
0x18002a46c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a471  mov     rcx, [rbp+57h+var_A8]; lpMem
0x18002a475  test    rcx, rcx
0x18002a478  jz      short loc_18002A47F
0x18002a47a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a47f  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18002a483  test    rcx, rcx
0x18002a486  jz      short loc_18002A491
0x18002a488  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a48d  mov     [rbp+57h+lpMem], r12
0x18002a491  mov     rcx, [rbp+57h+var_70]; lpMem
0x18002a495  test    rcx, rcx
0x18002a498  jz      short loc_18002A4A3
0x18002a49a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a49f  mov     [rbp+57h+var_70], r12
0x18002a4a3  mov     rcx, [rbp+57h+var_68]; lpMem
0x18002a4a7  test    rcx, rcx
0x18002a4aa  jz      short loc_18002A4B5
0x18002a4ac  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a4b1  mov     [rbp+57h+var_68], r12
0x18002a4b5  mov     rcx, [rbp+57h+var_98]; lpMem
0x18002a4b9  test    rcx, rcx
0x18002a4bc  jz      short loc_18002A4C7
0x18002a4be  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a4c3  mov     [rbp+57h+var_98], r12
0x18002a4c7  mov     rcx, [rbp+57h+var_60]; lpMem
0x18002a4cb  test    rcx, rcx
0x18002a4ce  jz      short loc_18002A4D9
0x18002a4d0  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a4d5  mov     [rbp+57h+var_60], r12
0x18002a4d9  mov     rcx, [rbp+57h+var_90]; lpMem
0x18002a4dd  test    rcx, rcx
0x18002a4e0  jz      short loc_18002A4EB
0x18002a4e2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a4e7  mov     [rbp+57h+var_90], r12
0x18002a4eb  mov     rcx, [rbp+57h+var_58]; lpMem
0x18002a4ef  test    rcx, rcx
0x18002a4f2  jz      short loc_18002A4FD
0x18002a4f4  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a4f9  mov     [rbp+57h+var_58], r12
0x18002a4fd  mov     rcx, [rbp+57h+var_88]; lpMem
0x18002a501  test    rcx, rcx
0x18002a504  jz      short loc_18002A50F
0x18002a506  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a50b  mov     [rbp+57h+var_88], r12
0x18002a50f  mov     rcx, [rbp+57h+var_A0]; lpMem
0x18002a513  test    rcx, rcx
0x18002a516  jz      short loc_18002A521
0x18002a518  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a51d  mov     [rbp+57h+var_A0], r12
0x18002a521  mov     rcx, [rbp+57h+var_80]; lpMem
0x18002a525  test    rcx, rcx
0x18002a528  jz      short loc_18002A52F
0x18002a52a  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18002a52f  mov     eax, ebx
0x18002a531  mov     rcx, [rbp+57h+var_40]
0x18002a535  xor     rcx, rsp; StackCookie
0x18002a538  call    __security_check_cookie
0x18002a53d  mov     rbx, [rsp+120h+arg_10]
0x18002a545  add     rsp, 0F0h
0x18002a54c  pop     r15
0x18002a54e  pop     r14
0x18002a550  pop     r13
0x18002a552  pop     r12
0x18002a554  pop     rdi
0x18002a555  pop     rsi
0x18002a556  pop     rbp
0x18002a557  retn
0x18002a558  test    ebx, ebx
0x18002a55a  jns     short loc_18002A569
0x18002a55c  mov     r9d, ebx
0x18002a55f  mov     edx, 5E3h
0x18002a564  jmp     loc_18002A750
0x18002a569  cmp     [rbp+57h+var_80], r12
0x18002a56d  jnz     short loc_18002A581
0x18002a56f  mov     ebx, 80004003h
0x18002a574  mov     edx, 5E6h
0x18002a579  mov     r9d, ebx
0x18002a57c  jmp     loc_18002A750
0x18002a581  cmp     [rbp+57h+var_A0], r12
0x18002a585  jnz     short loc_18002A599
0x18002a587  mov     ebx, 80004003h
0x18002a58c  mov     edx, 5E7h
0x18002a591  mov     r9d, ebx
0x18002a594  jmp     loc_18002A750
0x18002a599  cmp     [rbp+57h+var_90], r12
0x18002a59d  jnz     short loc_18002A5B1
0x18002a59f  mov     ebx, 80004003h
0x18002a5a4  mov     edx, 5E8h
0x18002a5a9  mov     r9d, ebx
0x18002a5ac  jmp     loc_18002A750
0x18002a5b1  cmp     [rbp+57h+var_98], r12
0x18002a5b5  jnz     short loc_18002A5C9
0x18002a5b7  mov     ebx, 80004003h
0x18002a5bc  mov     edx, 5E9h
0x18002a5c1  mov     r9d, ebx
0x18002a5c4  jmp     loc_18002A750
0x18002a5c9  cmp     [rbp+57h+var_68], r12
0x18002a5cd  jnz     short loc_18002A5E1
0x18002a5cf  mov     ebx, 80004003h
0x18002a5d4  mov     edx, 5EAh
0x18002a5d9  mov     r9d, ebx
0x18002a5dc  jmp     loc_18002A750
0x18002a5e1  mov     rcx, qword ptr [rbp+57h+var_50]; unsigned __int64
0x18002a5e5  lea     rdx, [rbp+57h+var_A8]; wchar_t **
0x18002a5e9  call    ?ConvertFileVerToStringW@@YAJ_KPEAPEA_W@Z; ConvertFileVerToStringW(unsigned __int64,wchar_t * *)
0x18002a5ee  mov     ebx, eax
0x18002a5f0  mov     edi, eax
0x18002a5f2  test    eax, eax
0x18002a5f4  jns     short loc_18002A603
0x18002a5f6  mov     r9d, eax
0x18002a5f9  mov     edx, 5EDh
0x18002a5fe  jmp     loc_18002A750
0x18002a603  mov     rbx, [rbp+57h+var_88]
0x18002a607  test    rbx, rbx
0x18002a60a  jz      short loc_18002A617
0x18002a60c  cmp     [rbx], r12w
0x18002a610  jz      short loc_18002A617
0x18002a612  mov     r14b, 1
0x18002a615  jmp     short loc_18002A61E
0x18002a617  mov     rbx, [rbp+57h+var_A0]
0x18002a61b  mov     r14b, r12b
0x18002a61e  mov     rcx, rbx; wchar_t *
0x18002a621  call    ?CheckIfDirExists@@YAJPEB_W@Z; CheckIfDirExists(wchar_t const *)
0x18002a626  mov     edi, eax
0x18002a628  mov     [rsp+120h+var_E8], rbx
0x18002a62d  test    eax, eax
0x18002a62f  lea     rcx, aMerged_0; "Merged"
0x18002a636  lea     rax, aDeployment; "Deployment"
0x18002a63d  mov     r9d, 4
0x18002a643  mov     r8d, r13d
0x18002a646  js      loc_18002A765
0x18002a64c  test    r14b, r14b
0x18002a64f  cmovnz  rax, rcx
0x18002a653  xor     edx, edx
0x18002a655  mov     [rsp+120h+var_F0], rax
0x18002a65a  xor     ecx, ecx
0x18002a65c  lea     rax, aWsSandboxFolde_0; "%ws sandbox folder %ws exists"
0x18002a663  mov     [rsp+120h+var_F8], rax
0x18002a668  mov     [rsp+120h+var_100], r12
0x18002a66d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002a672  mov     r9, [rbp+57h+var_88]; wchar_t *
0x18002a676  lea     rax, [rbp+57h+var_B0]
0x18002a67a  mov     r8, [rbp+57h+var_A0]; wchar_t *
0x18002a67e  mov     rdx, [rbp+57h+var_98]; wchar_t *
0x18002a682  mov     [rsp+120h+var_D0], rsi; struct tagPostRebootResultData *
  ... truncated ...
```
