# Ssl::AcquireCredentialsForServer_v1(_CERT_CONTEXT const *,_SecHandle * *)

- ea: `0x10044bbf0`
- end: `0x10044be9e`
- name: `?AcquireCredentialsForServer_v1@Ssl@@SAKPEBU_CERT_CONTEXT@@PEAPEAU_SecHandle@@@Z`
- size: `686`
- prototype: `unsigned int __fastcall(const struct _CERT_CONTEXT *, struct _SecHandle **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044cff0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10044bbf0`
- `0x10045d370`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044bd35`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044bd35`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044be3b`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10044be3b`
- `sqldk!SystemThread_TlsIndex` at `0x10044bcdb`
- `sqldk!SystemThread_TlsOffset` at `0x10044bce4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044bcff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044bcff`

## string_xrefs

- `0x10044bc16`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`
- `0x10044bd78`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::AcquireCredentialsForServer_v1(const struct _CERT_CONTEXT *a1, struct _SecHandle **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  struct _SecHandle *v5; // rax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  const wchar_t *v8; // r9
  _DWORD *v10; // [rsp+20h] [rbp-B8h]
  __int64 v11; // [rsp+28h] [rbp-B0h]
  __int64 v12; // [rsp+30h] [rbp-A8h]
  _DWORD v13[2]; // [rsp+70h] [rbp-68h] BYREF
  const struct _CERT_CONTEXT **v14; // [rsp+78h] [rbp-60h]
  __int128 v15; // [rsp+80h] [rbp-58h]
  __int128 v16; // [rsp+90h] [rbp-48h]
  __int64 v17; // [rsp+A0h] [rbp-38h]
  int v18; // [rsp+A8h] [rbp-30h]
  __int64 v19; // [rsp+ACh] [rbp-2Ch]
  __int64 v20; // [rsp+B4h] [rbp-24h]
  int v21; // [rsp+BCh] [rbp-1Ch]
  const struct _CERT_CONTEXT *v22; // [rsp+E0h] [rbp+8h] BYREF

  v22 = a1;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::AcquireCredentialsForServer_v1",
      607,
      L"API|SNIpHandle: %p{PCCERT_CONTEXT}\n",
      v22);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v13[0] = 4;
  v13[1] = 1;
  v14 = &v22;
  v18 = 16320;
  if ( Ssl::s_fDisableSchannelSessionResumption )
    HIDWORD(v20) |= 0x80u;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v4 = *(_QWORD *)(v3 + 256);
  if ( !v4 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v4 = *(_QWORD *)(v3 + 256);
  }
  v5 = (struct _SecHandle *)operator new(
                              0x10u,
                              *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v4 + 992) + 56LL) + 8LL),
                              1,
                              "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
                              629,
                              6u);
  *a2 = v5;
  if ( !v5 )
  {
    v6 = 14;
LABEL_14:
    scierrlog(0x659Au, v6);
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v12) = v6;
      LODWORD(v11) = 0;
      LODWORD(v10) = 6;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::AcquireCredentialsForServer_v1",
        654,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v10,
        v11,
        v12);
    }
    SNISetLastError(6u, v6, 0xC3B4u);
    operator delete(*a2, 0x10u);
    *a2 = 0;
    goto LABEL_17;
  }
  HIDWORD(v12) = 0;
  HIDWORD(v11) = 0;
  v10 = v13;
  v7 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, __int64))Ssl::s_pfTable->AcquireCredentialsHandleW)(
         0,
         L"Microsoft Unified Security Protocol Provider",
         1);
  v6 = v7;
  if ( v7 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v10) = v7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
        "Ssl::AcquireCredentialsForServer_v1",
        647,
        L"ERR|SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
        v10);
    }
    goto LABEL_14;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) == 0 )
    goto LABEL_19;
  LODWORD(v10) = 0;
  SNIXE_SNI_TRACE_ON(
    "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
    "Ssl::AcquireCredentialsForServer_v1",
    647,
    L"SNIAcquireCredentialsHandle return value: %d{DWORD}\n",
    v10);
LABEL_17:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v10) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp",
      "Ssl::AcquireCredentialsForServer_v1",
      660,
      L"RET|SNI%d{WINERR}\n",
      v10);
  }
LABEL_19:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", "Ssl::AcquireCredentialsForServer_v1", 607, v8);
  return v6;
}

```

## disassembly

```asm
0x10044bbf0  mov     rax, rsp
0x10044bbf3  mov     [rax+8], rcx
0x10044bbf7  push    rsi
0x10044bbf8  push    rdi
0x10044bbf9  push    r14
0x10044bbfb  sub     rsp, 0C0h
0x10044bc02  mov     [rsp+0D8h+var_88], 0FFFFFFFFFFFFFFFEh
0x10044bc0b  mov     [rax+18h], rbx
0x10044bc0f  mov     [rax+20h], rbp
0x10044bc13  mov     rdi, rdx
0x10044bc16  lea     rsi, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044bc1d  mov     [rax-80h], rsi
0x10044bc21  lea     r14, aSslAcquirecred_0; "Ssl::AcquireCredentialsForServer_v1"
0x10044bc28  mov     [rax-78h], r14
0x10044bc2c  mov     dword ptr [rax-70h], 25Fh
0x10044bc33  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bc3a  jz      short loc_10044BC5D
0x10044bc3c  mov     rax, [rax+8]
0x10044bc40  mov     [rsp+0D8h+var_B8], rax
0x10044bc45  lea     r9, aApiSniphandleP_0; "API|SNIpHandle: %p{PCCERT_CONTEXT}\n"
0x10044bc4c  mov     r8d, 25Fh; int
0x10044bc52  mov     rdx, r14; char *
0x10044bc55  mov     rcx, rsi; char *
0x10044bc58  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bc5d  xorps   xmm0, xmm0
0x10044bc60  movdqa  [rsp+0D8h+var_58], xmm0
0x10044bc69  xorps   xmm1, xmm1
0x10044bc6c  movdqa  [rsp+0D8h+var_48], xmm1
0x10044bc75  xor     ebp, ebp
0x10044bc77  mov     [rsp+0D8h+var_38], rbp
0x10044bc7f  mov     [rsp+0D8h+var_2C], rbp
0x10044bc87  mov     [rsp+0D8h+var_24], rbp
0x10044bc8f  mov     [rsp+0D8h+var_1C], ebp
0x10044bc96  mov     [rsp+0D8h+var_68], 4
0x10044bc9e  mov     [rsp+0D8h+var_64], 1
0x10044bca6  lea     rax, [rsp+0D8h+arg_0]
0x10044bcae  mov     [rsp+0D8h+var_60], rax
0x10044bcb3  mov     [rsp+0D8h+var_30], 3FC0h
0x10044bcbe  cmp     cs:?s_fDisableSchannelSessionResumption@Ssl@@0_NA, bpl; bool Ssl::s_fDisableSchannelSessionResumption
0x10044bcc5  jz      short loc_10044BCD2
0x10044bcc7  or      dword ptr [rsp+0D8h+var_24+4], 80h
0x10044bcd2  mov     rdx, gs:58h
0x10044bcdb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044bce2  mov     ecx, [rax]
0x10044bce4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044bceb  mov     ebx, [rax]
0x10044bced  add     rbx, [rdx+rcx*8]
0x10044bcf1  mov     rax, [rbx+100h]
0x10044bcf8  test    rax, rax
0x10044bcfb  jnz     short loc_10044BD0C
0x10044bcfd  xor     ecx, ecx
0x10044bcff  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044bd05  mov     rax, [rbx+100h]
0x10044bd0c  mov     rax, [rax+3E0h]
0x10044bd13  mov     rcx, [rax+38h]
0x10044bd17  mov     byte ptr [rsp+0D8h+var_B0], 6
0x10044bd1c  mov     dword ptr [rsp+0D8h+var_B8], 275h
0x10044bd24  mov     r9, rsi
0x10044bd27  mov     r8d, 1
0x10044bd2d  mov     rdx, [rcx+8]
0x10044bd31  lea     ecx, [r8+0Fh]
0x10044bd35  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044bd3b  mov     [rdi], rax
0x10044bd3e  test    rax, rax
0x10044bd41  jnz     short loc_10044BD4B
0x10044bd43  lea     ebx, [rax+0Eh]
0x10044bd46  jmp     loc_10044BDE4
0x10044bd4b  lea     rcx, [rsp+0D8h+arg_8]
0x10044bd53  mov     [rsp+0D8h+var_98], rcx
0x10044bd58  mov     [rsp+0D8h+var_A0], rax
0x10044bd5d  mov     [rsp+0D8h+var_A8], rbp
0x10044bd62  mov     [rsp+0D8h+var_B0], rbp
0x10044bd67  lea     rax, [rsp+0D8h+var_68]
0x10044bd6c  mov     [rsp+0D8h+var_B8], rax
0x10044bd71  xor     r9d, r9d
0x10044bd74  lea     r8d, [r9+1]
0x10044bd78  lea     rdx, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x10044bd7f  xor     ecx, ecx
0x10044bd81  mov     rax, cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x10044bd88  call    qword ptr [rax+18h]
0x10044bd8b  mov     ebx, eax
0x10044bd8d  test    eax, eax
0x10044bd8f  jnz     short loc_10044BDBF
0x10044bd91  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bd98  jz      loc_10044BE6A
0x10044bd9e  mov     dword ptr [rsp+0D8h+var_B8], ebp
0x10044bda2  lea     r9, aSniacquirecred; "SNIAcquireCredentialsHandle return valu"...
0x10044bda9  mov     r8d, 287h; int
0x10044bdaf  mov     rdx, r14; char *
0x10044bdb2  mov     rcx, rsi; char *
0x10044bdb5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bdba  jmp     loc_10044BE44
0x10044bdbf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bdc6  jz      short loc_10044BDE4
0x10044bdc8  mov     dword ptr [rsp+0D8h+var_B8], eax
0x10044bdcc  lea     r9, aErrSniacquirec; "ERR|SNIAcquireCredentialsHandle return "...
0x10044bdd3  mov     r8d, 287h; int
0x10044bdd9  mov     rdx, r14; char *
0x10044bddc  mov     rcx, rsi; char *
0x10044bddf  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044bde4  mov     edx, ebx
0x10044bde6  mov     ecx, 659Ah; unsigned int
0x10044bdeb  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10044bdf0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044bdf7  jz      short loc_10044BE21
0x10044bdf9  mov     dword ptr [rsp+0D8h+var_A8], ebx
0x10044bdfd  mov     dword ptr [rsp+0D8h+var_B0], ebp
0x10044be01  mov     dword ptr [rsp+0D8h+var_B8], 6
0x10044be09  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10044be10  mov     r8d, 28Eh; int
0x10044be16  mov     rdx, r14; char *
0x10044be19  mov     rcx, rsi; char *
0x10044be1c  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10044be21  mov     r8d, 0C3B4h
0x10044be27  mov     edx, ebx
0x10044be29  mov     ecx, 6
0x10044be2e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10044be33  mov     edx, 10h
0x10044be38  mov     rcx, [rdi]
0x10044be3b  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x10044be41  mov     [rdi], rbp
0x10044be44  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044be4b  jz      short loc_10044BE6A
0x10044be4d  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x10044be51  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10044be58  mov     r8d, 294h; int
0x10044be5e  mov     rdx, r14; char *
0x10044be61  mov     rcx, rsi; char *
0x10044be64  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10044be69  nop
0x10044be6a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10044be71  jz      short loc_10044BE84
0x10044be73  mov     r8d, 25Fh; int
0x10044be79  mov     rdx, r14; char *
0x10044be7c  mov     rcx, rsi; char *
0x10044be7f  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10044be84  mov     eax, ebx
0x10044be86  lea     r11, [rsp+0D8h+var_18]
0x10044be8e  mov     rbx, [r11+30h]
0x10044be92  mov     rbp, [r11+38h]
0x10044be96  mov     rsp, r11
0x10044be99  pop     r14
0x10044be9b  pop     rdi
0x10044be9c  pop     rsi
0x10044be9d  retn
```
