# COSAsyncDownloader::HandleDownloadJobCompletion(tagDSUpdateMetadata const *,wchar_t const *,wchar_t const *,wchar_t * const,ISusHandlerNotification *,tagDownloadJobReportingInfo *)

- ea: `0x180025380`
- end: `0x18002568a`
- name: `?HandleDownloadJobCompletion@COSAsyncDownloader@@UEAAJPEBUtagDSUpdateMetadata@@PEB_W1QEA_WPEAUISusHandlerNotification@@PEAUtagDownloadJobReportingInfo@@@Z`
- size: `778`
- prototype: `__int64 __fastcall(COSAsyncDownloader *this, const struct tagDSUpdateMetadata *, const wchar_t *, const wchar_t *, wchar_t *const, struct ISusHandlerNotification *, struct tagDownloadJobReportingInfo *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000956c`
- `0x18000a6d0`
- `0x18000e594`
- `0x180019330`
- `0x180024714`
- `0x1800247b0`
- `0x180025380`
- `0x180042630`
- `0x180049260`
- `0x1800492e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025445`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025445`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall COSAsyncDownloader::HandleDownloadJobCompletion(
        COSAsyncDownloader *this,
        const struct tagDSUpdateMetadata *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *const a5,
        struct ISusHandlerNotification *a6,
        struct tagDownloadJobReportingInfo *a7)
{
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v14; // ebx
  const WCHAR *v15; // r12
  __int64 v16; // rsi
  int *v17; // r9
  const wchar_t **v18; // rsi
  char *v19; // rbx
  __int128 v20; // xmm0
  int v21; // eax
  unsigned int v22; // edx
  void *v23; // rcx
  void *v24; // rdi
  bool v25; // zf
  __int128 v26; // xmm0
  __int64 v27; // rax
  int lpString2; // [rsp+20h] [rbp-C1h]
  unsigned int lpString2a; // [rsp+20h] [rbp-C1h]
  void *lpMem[2]; // [rsp+40h] [rbp-A1h] BYREF
  __int128 v31; // [rsp+50h] [rbp-91h] BYREF
  int v32; // [rsp+60h] [rbp-81h]
  _QWORD v33[14]; // [rsp+70h] [rbp-71h] BYREF
  int v34; // [rsp+E0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = -1;
  do
    ++v10;
  while ( a4[v10] );
  if ( v10 <= v9 )
  {
    v11 = -2147024735;
    v12 = 418;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)v11,
      lpString2);
    return v11;
  }
  v14 = 0;
  v15 = &a4[v9 + 1];
  if ( *((_DWORD *)a2 + 116) )
  {
    while ( 1 )
    {
      v16 = 248LL * v14;
      if ( CompareStringW(0x7Fu, 1u, v15, -1, *(PCNZWCH *)(v16 + *((_QWORD *)a2 + 59) + 72), -1) == 2 )
        break;
      if ( ++v14 >= *((_DWORD *)a2 + 116) )
        return 0;
    }
    v18 = (const wchar_t **)(*((_QWORD *)a2 + 59) + v16);
    if ( v18 )
    {
      if ( *((_DWORD *)v18 + 28) == 8 || *((_DWORD *)v18 + 28) == 9 )
      {
        v34 = 0;
        v11 = OSDeploymentHelper::EvaluateFileInSandbox(a3, v18, (const struct tagDSFile *)&v34, v17);
        if ( (v11 & 0x80000000) != 0 )
        {
          WUTrace(0, 0, 4096, 1);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C9,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
            (const char *)v11,
            v11);
          return v11;
        }
        if ( v34 < 0 )
        {
          lpString2 = v34;
          WUTrace(0, 0, 4096, 1);
          v11 = v34;
          if ( v34 >= 0 )
            return v11;
          v12 = 463;
          goto LABEL_7;
        }
        if ( a6 )
        {
          memset(v33, 0, 0x68u);
          v33[4] = a3;
          v19 = 0;
          lpMem[0] = 0;
          LODWORD(v33[0]) = 2;
          v33[5] = v15;
          LODWORD(v33[8]) = 1;
          if ( a7 )
          {
            v20 = *((_OWORD *)a7 + 1);
            v33[11] = *((_QWORD *)a7 + 4);
            v33[12] = *((_QWORD *)a7 + 5);
            v33[2] = *(_QWORD *)a7;
            v33[3] = *((_QWORD *)a7 + 1);
            *(_OWORD *)&v33[9] = v20;
          }
          v21 = HexStringFromBlobAllocW((const unsigned __int8 *)v18[16], *((_DWORD *)v18 + 31), (wchar_t **)lpMem);
          v23 = (void *)v33[7];
          v24 = lpMem[0];
          if ( v21 >= 0 )
            v23 = lpMem[0];
          v25 = *((_DWORD *)v18 + 28) == 8;
          v33[7] = v23;
          if ( v25 )
          {
            LODWORD(lpMem[0]) = ATL::Base64EncodeGetRequiredLength(*((_DWORD *)v18 + 31), v22);
            if ( LODWORD(lpMem[0]) == -1 || (v19 = (char *)SafeSusAllocArray(LODWORD(lpMem[0]) + 1, 1u)) != 0 )
            {
              if ( ATL::Base64Encode(
                     (const unsigned __int8 *)v18[16],
                     *((_DWORD *)v18 + 31),
                     v19,
                     (int *)lpMem,
                     lpString2a) )
              {
                v19[SLODWORD(lpMem[0])] = 0;
              }
              else
              {
                *v19 = 0;
              }
            }
            HIDWORD(v33[8]) = 4;
            v33[1] = L"ServicingStackDownloaded";
            v33[6] = v19;
          }
          v26 = *(_OWORD *)((char *)a2 + 4);
          v32 = *((_DWORD *)a2 + 5);
          v27 = *(_QWORD *)a6;
          v31 = v26;
          (*(void (__fastcall **)(struct ISusHandlerNotification *, __int128 *, _QWORD *, _QWORD))(v27 + 24))(
            a6,
            &v31,
            v33,
            0);
          if ( v19 )
            CSusBaseAllocTag<942762101>::operator delete(v19);
          if ( v24 )
            CSusBaseAllocTag<942762101>::operator delete(v24);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025380  mov     [rsp-8+arg_0], rbx
0x180025385  push    rbp
0x180025386  push    rsi
0x180025387  push    rdi
0x180025388  push    r12
0x18002538a  push    r13
0x18002538c  push    r14
0x18002538e  push    r15
0x180025390  lea     rbp, [rsp-0Fh]
0x180025395  sub     rsp, 0F0h
0x18002539c  mov     rax, cs:__security_cookie
0x1800253a3  xor     rax, rsp
0x1800253a6  mov     [rbp+3Fh+var_38], rax
0x1800253aa  mov     rdi, [rbp+3Fh+arg_30]
0x1800253ae  mov     r15, r8
0x1800253b1  mov     r13, [rbp+3Fh+arg_28]
0x1800253b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800253b9  mov     r14, rdx
0x1800253bc  mov     rax, r8
0x1800253bf  xor     edx, edx
0x1800253c1  inc     rax
0x1800253c4  cmp     [r15+rax*2], dx
0x1800253c9  jnz     short loc_1800253C1
0x1800253cb  mov     rcx, r8
0x1800253ce  inc     rcx
0x1800253d1  cmp     [r9+rcx*2], dx
0x1800253d6  jnz     short loc_1800253CE
0x1800253d8  cmp     rcx, rax
0x1800253db  ja      short loc_180025401
0x1800253dd  mov     ebx, 800700A1h
0x1800253e2  mov     edx, 1A2h; void *
0x1800253e7  mov     rcx, [rbp+47h]; this
0x1800253eb  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800253f2  mov     r9d, ebx; char *
0x1800253f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800253fa  mov     eax, ebx
0x1800253fc  jmp     loc_180025663
0x180025401  lea     r12, [r9+2]
0x180025405  mov     ebx, edx
0x180025407  lea     r12, [r12+rax*2]
0x18002540b  cmp     [r14+1D0h], edx
0x180025412  jbe     loc_180025661
0x180025418  mov     [rsp+120h+cchCount2], r8d; cchCount2
0x18002541d  mov     edx, 1; dwCmpFlags
0x180025422  mov     eax, ebx
0x180025424  mov     r9d, r8d; cchCount1
0x180025427  imul    rsi, rax, 0F8h
0x18002542e  mov     rax, [r14+1D8h]
0x180025435  mov     r8, r12; lpString1
0x180025438  lea     ecx, [rdx+7Eh]; Locale
0x18002543b  mov     rax, [rsi+rax+48h]
0x180025440  mov     [rsp+120h+lpString2], rax; unsigned int
0x180025445  call    cs:__imp_CompareStringW
0x18002544b  cmp     eax, 2
0x18002544e  jz      short loc_180025467
0x180025450  inc     ebx
0x180025452  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180025459  cmp     ebx, [r14+1D0h]
0x180025460  jb      short loc_180025418
0x180025462  jmp     loc_180025661
0x180025467  add     rsi, [r14+1D8h]
0x18002546e  jz      loc_180025661
0x180025474  cmp     dword ptr [rsi+70h], 8
0x180025478  jz      short loc_180025484
0x18002547a  cmp     dword ptr [rsi+70h], 9
0x18002547e  jnz     loc_180025661
0x180025484  lea     r8, [rbp+3Fh+var_40]; struct tagDSFile *
0x180025488  mov     [rbp+3Fh+var_40], 0
0x18002548f  mov     rdx, rsi; wchar_t *
0x180025492  mov     rcx, r15; this
0x180025495  call    ?EvaluateFileInSandbox@OSDeploymentHelper@@YAJPEB_WAEBUtagDSFile@@PEAJ@Z; OSDeploymentHelper::EvaluateFileInSandbox(wchar_t const *,tagDSFile const &,long *)
0x18002549a  mov     ebx, eax
0x18002549c  test    eax, eax
0x18002549e  jns     short loc_1800254D6
0x1800254a0  mov     rcx, [rsi+48h]
0x1800254a4  lea     rax, aEvaluatefilein; "EvaluateFileInSandbox failed for the fi"...
0x1800254ab  mov     [rsp+120h+var_F0], rcx
0x1800254b0  xor     edx, edx
0x1800254b2  mov     qword ptr [rsp+120h+cchCount2], rax
0x1800254b7  xor     ecx, ecx
0x1800254b9  mov     r8d, 1000h
0x1800254bf  mov     dword ptr [rsp+120h+lpString2], ebx
0x1800254c3  lea     r9d, [rdx+1]
0x1800254c7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800254cc  mov     edx, 1C9h
0x1800254d1  jmp     loc_1800253E7
0x1800254d6  mov     ecx, [rbp+3Fh+var_40]
0x1800254d9  test    ecx, ecx
0x1800254db  jns     short loc_18002551E
0x1800254dd  mov     rax, [rsi+48h]
0x1800254e1  xor     edx, edx
0x1800254e3  mov     [rsp+120h+var_F0], rax
0x1800254e8  mov     r8d, 1000h
0x1800254ee  lea     rax, aFileWsFailedVa; "File '%ws' failed validation"
0x1800254f5  mov     qword ptr [rsp+120h+cchCount2], rax
0x1800254fa  mov     dword ptr [rsp+120h+lpString2], ecx
0x1800254fe  lea     r9d, [rdx+1]
0x180025502  xor     ecx, ecx
0x180025504  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180025509  mov     ebx, [rbp+3Fh+var_40]
0x18002550c  test    ebx, ebx
0x18002550e  jns     loc_1800253FA
0x180025514  mov     edx, 1CFh
0x180025519  jmp     loc_1800253E7
0x18002551e  test    r13, r13
0x180025521  jz      loc_180025661
0x180025527  xor     edx, edx; Val
0x180025529  lea     rcx, [rbp+3Fh+var_B0]; void *
0x18002552d  lea     r8d, [rdx+68h]; Size
0x180025531  call    memset
0x180025536  mov     [rbp+3Fh+var_90], r15
0x18002553a  xor     ebx, ebx
0x18002553c  xor     r15d, r15d
0x18002553f  mov     [rsp+120h+lpMem], 0
0x180025548  mov     [rbp+3Fh+var_B0], 2
0x18002554f  mov     [rbp+3Fh+var_88], r12
0x180025553  mov     [rbp+3Fh+var_70], 1
0x18002555a  test    rdi, rdi
0x18002555d  jz      short loc_180025587
0x18002555f  mov     rax, [rdi+20h]
0x180025563  movups  xmm0, xmmword ptr [rdi+10h]
0x180025567  mov     [rbp+3Fh+var_58], rax
0x18002556b  mov     rax, [rdi+28h]
0x18002556f  mov     [rbp+3Fh+var_50], rax
0x180025573  mov     rax, [rdi]
0x180025576  mov     [rbp+3Fh+var_A0], rax
0x18002557a  mov     rax, [rdi+8]
0x18002557e  mov     [rbp+3Fh+var_98], rax
0x180025582  movdqu  [rbp+3Fh+var_68], xmm0
0x180025587  mov     edx, [rsi+7Ch]; unsigned int
0x18002558a  lea     r8, [rsp+120h+lpMem]; wchar_t **
0x18002558f  mov     rcx, [rsi+80h]; unsigned __int8 *
0x180025596  call    ?HexStringFromBlobAllocW@@YAJPEBEKPEAPEA_W@Z; HexStringFromBlobAllocW(uchar const *,ulong,wchar_t * *)
0x18002559b  mov     rcx, [rbp+3Fh+var_78]
0x18002559f  test    eax, eax
0x1800255a1  mov     rdi, [rsp+120h+lpMem]
0x1800255a6  cmovns  rcx, rdi
0x1800255aa  cmp     dword ptr [rsi+70h], 8
0x1800255ae  mov     [rbp+3Fh+var_78], rcx
0x1800255b2  jnz     short loc_180025619
0x1800255b4  mov     ecx, [rsi+7Ch]; int
0x1800255b7  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x1800255bc  mov     dword ptr [rsp+120h+lpMem], eax
0x1800255c0  add     eax, 1
0x1800255c3  jz      short loc_1800255DA
0x1800255c5  movsxd  rcx, eax; unsigned __int64
0x1800255c8  mov     edx, 1; unsigned __int64
0x1800255cd  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800255d2  mov     rbx, rax
0x1800255d5  test    rax, rax
0x1800255d8  jz      short loc_180025603
0x1800255da  mov     edx, [rsi+7Ch]; int
0x1800255dd  lea     r9, [rsp+120h+lpMem]; int *
0x1800255e2  mov     rcx, [rsi+80h]; unsigned __int8 *
0x1800255e9  mov     r8, rbx; char *
0x1800255ec  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x1800255f1  test    eax, eax
0x1800255f3  jz      short loc_180025600
0x1800255f5  movsxd  rax, dword ptr [rsp+120h+lpMem]
0x1800255fa  mov     [rax+rbx], r15b
0x1800255fe  jmp     short loc_180025603
0x180025600  mov     [rbx], r15b
0x180025603  lea     rax, aServicingstack; "ServicingStackDownloaded"
0x18002560a  mov     [rbp+3Fh+var_6C], 4
0x180025611  mov     [rbp+3Fh+var_A8], rax
0x180025615  mov     [rbp+3Fh+var_80], rbx
0x180025619  mov     eax, [r14+14h]
0x18002561d  lea     r8, [rbp+3Fh+var_B0]
0x180025621  movups  xmm0, xmmword ptr [r14+4]
0x180025626  mov     [rsp+120h+var_C0], eax
0x18002562a  lea     rdx, [rsp+120h+var_D0]
0x18002562f  mov     rax, [r13+0]
0x180025633  xor     r9d, r9d
0x180025636  mov     rcx, r13
0x180025639  movaps  [rsp+120h+var_D0], xmm0
0x18002563e  mov     rax, [rax+18h]
0x180025642  call    _guard_dispatch_icall
0x180025647  test    rbx, rbx
0x18002564a  jz      short loc_180025654
0x18002564c  mov     rcx, rbx; lpMem
0x18002564f  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180025654  test    rdi, rdi
0x180025657  jz      short loc_180025661
0x180025659  mov     rcx, rdi; lpMem
0x18002565c  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180025661  xor     eax, eax
0x180025663  mov     rcx, [rbp+3Fh+var_38]
0x180025667  xor     rcx, rsp; StackCookie
0x18002566a  call    __security_check_cookie
0x18002566f  mov     rbx, [rsp+120h+arg_0]
0x180025677  add     rsp, 0F0h
0x18002567e  pop     r15
0x180025680  pop     r14
0x180025682  pop     r13
0x180025684  pop     r12
0x180025686  pop     rdi
0x180025687  pop     rsi
0x180025688  pop     rbp
0x180025689  retn
```
