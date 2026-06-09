# Smux::GrowSessionList(void)

- ea: `0x100431870`
- end: `0x100431ae8`
- name: `?GrowSessionList@Smux@@AEAAKXZ`
- size: `632`
- prototype: `unsigned int __fastcall(Smux *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100430970`
- `0x100431f20`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100431870`
- `0x1004349f0`
- `0x100486250`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100431a7f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100431a7f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004319de`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004319de`
- `sqldk!SystemThread_TlsIndex` at `0x100431969`
- `sqldk!SystemThread_TlsOffset` at `0x100431972`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043198d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043198d`

## string_xrefs

- `0x100431894`: `sql\common\dk\sni\src\smux.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Smux::GrowSessionList(Smux *this)
{
  char v2; // al
  unsigned int v3; // r8d
  unsigned int v4; // ebx
  const wchar_t *v5; // r9
  __int64 v6; // rdi
  __int64 v7; // rax
  struct IMemObj *v8; // r10
  unsigned __int64 v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  __int64 v13; // [rsp+20h] [rbp-48h]
  __int64 v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+28h] [rbp-40h]

  v2 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\smux.cpp",
      "Smux::GrowSessionList",
      3188,
      L"API|SNI%u#\n",
      *((_DWORD *)this + 11));
    v2 = g_XeSniPkg_enabledBitmap;
  }
  v3 = *((_DWORD *)this + 17);
  if ( v3 <= 0xFFFF )
  {
    v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v7 = *(_QWORD *)(v6 + 256);
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
      v3 = *((_DWORD *)this + 17);
    }
    v8 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL);
    v9 = 8LL * (v3 + 1);
    if ( !is_mul_ok(v3 + 1, 8u) )
      v9 = -1;
    v10 = operator new[](v9, v8, 1, "sql\\common\\dk\\sni\\src\\smux.cpp", 3204, 6u);
    v11 = v10;
    if ( v10 )
    {
      memmove(v10, *((const void **)this + 9), 8LL * *((unsigned int *)this + 17));
      v11[(*((_DWORD *)this + 17))++] = 0;
      operator delete[](*((void **)this + 9));
      *((_QWORD *)this + 9) = v11;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::GrowSessionList",
          3220,
          L"RET|SNI%d{WINERR}\n",
          0);
      v4 = 0;
    }
    else
    {
      v4 = 14;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v15) = 0;
        LODWORD(v14) = 5;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::GrowSessionList",
          3207,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v14,
          v15,
          14);
      }
      SNISetLastError(5u, 0xEu, 0xC3B4u);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v14) = 14;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::GrowSessionList",
          3209,
          L"RET|SNI%d{WINERR}\n",
          v14);
      }
    }
  }
  else
  {
    v4 = 5023;
    if ( (v2 & 2) != 0 )
    {
      LODWORD(v13) = 5;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Smux::GrowSessionList",
        3197,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v13,
        0,
        5023);
    }
    SNISetLastError(5u, 0x139Fu, 0xC3B4u);
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v13) = 5023;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Smux::GrowSessionList",
        3199,
        L"RET|SNI%d{WINERR}\n",
        v13);
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Smux::GrowSessionList", 3188, v5);
  return v4;
}

```

## disassembly

```asm
0x100431870  mov     rax, rsp
0x100431873  push    r14
0x100431875  sub     rsp, 60h
0x100431879  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x100431881  mov     [rax+8], rbx
0x100431885  mov     [rax+10h], rbp
0x100431889  mov     [rax+18h], rsi
0x10043188d  mov     [rax+20h], rdi
0x100431891  mov     rbx, rcx
0x100431894  lea     rbp, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10043189b  mov     [rax-20h], rbp
0x10043189f  lea     r14, aSmuxGrowsessio; "Smux::GrowSessionList"
0x1004318a6  mov     [rax-18h], r14
0x1004318aa  mov     dword ptr [rax-10h], 0C74h
0x1004318b1  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004318b7  test    al, 40h
0x1004318b9  jz      short loc_1004318E0
0x1004318bb  mov     eax, [rcx+2Ch]
0x1004318be  mov     dword ptr [rsp+68h+var_48], eax
0x1004318c2  lea     r9, aApiSniU; "API|SNI%u#\n"
0x1004318c9  mov     r8d, 0C74h; int
0x1004318cf  mov     rdx, r14; char *
0x1004318d2  mov     rcx, rbp; char *
0x1004318d5  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004318da  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004318e0  mov     r8d, [rbx+44h]
0x1004318e4  cmp     r8d, 0FFFFh
0x1004318eb  jbe     short loc_100431960
0x1004318ed  mov     ebx, 139Fh
0x1004318f2  test    al, 2
0x1004318f4  jz      short loc_100431920
0x1004318f6  mov     [rsp+68h+var_38], ebx
0x1004318fa  xor     edi, edi
0x1004318fc  mov     dword ptr [rsp+68h+var_40], edi
0x100431900  mov     dword ptr [rsp+68h+var_48], 5
0x100431908  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043190f  mov     r8d, 0C7Dh; int
0x100431915  mov     rdx, r14; char *
0x100431918  mov     rcx, rbp; char *
0x10043191b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100431920  mov     r8d, 0C3B4h
0x100431926  mov     edx, ebx
0x100431928  mov     ecx, 5
0x10043192d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100431932  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431939  jz      loc_100431AB1
0x10043193f  mov     dword ptr [rsp+68h+var_48], ebx
0x100431943  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043194a  mov     r8d, 0C7Fh; int
0x100431950  mov     rdx, r14; char *
0x100431953  mov     rcx, rbp; char *
0x100431956  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043195b  jmp     loc_100431AB1
0x100431960  mov     rdx, gs:58h
0x100431969  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100431970  mov     ecx, [rax]
0x100431972  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100431979  mov     edi, [rax]
0x10043197b  add     rdi, [rdx+rcx*8]
0x10043197f  mov     rax, [rdi+100h]
0x100431986  test    rax, rax
0x100431989  jnz     short loc_10043199E
0x10043198b  xor     ecx, ecx
0x10043198d  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100431993  mov     rax, [rdi+100h]
0x10043199a  mov     r8d, [rbx+44h]
0x10043199e  mov     rax, [rax+3E0h]
0x1004319a5  mov     rcx, [rax+38h]
0x1004319a9  mov     r10, [rcx+8]
0x1004319ad  lea     ecx, [r8+1]
0x1004319b1  mov     eax, 8
0x1004319b6  mul     rcx
0x1004319b9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1004319c0  cmovo   rax, rcx
0x1004319c4  mov     byte ptr [rsp+68h+var_40], 6
0x1004319c9  mov     dword ptr [rsp+68h+var_48], 0C84h
0x1004319d1  mov     r9, rbp
0x1004319d4  lea     r8d, [rcx+2]
0x1004319d8  mov     rdx, r10
0x1004319db  mov     rcx, rax
0x1004319de  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004319e4  mov     rsi, rax
0x1004319e7  test    rax, rax
0x1004319ea  jnz     short loc_100431A5B
0x1004319ec  lea     ebx, [rax+0Eh]
0x1004319ef  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004319f6  jz      short loc_100431A22
0x1004319f8  mov     [rsp+68h+var_38], ebx
0x1004319fc  xor     edi, edi
0x1004319fe  mov     dword ptr [rsp+68h+var_40], edi
0x100431a02  mov     dword ptr [rsp+68h+var_48], 5
0x100431a0a  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100431a11  mov     r8d, 0C87h; int
0x100431a17  mov     rdx, r14; char *
0x100431a1a  mov     rcx, rbp; char *
0x100431a1d  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100431a22  mov     r8d, 0C3B4h
0x100431a28  mov     edx, ebx
0x100431a2a  mov     ecx, 5
0x100431a2f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100431a34  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431a3b  jz      short loc_100431AB1
0x100431a3d  mov     dword ptr [rsp+68h+var_48], ebx
0x100431a41  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100431a48  mov     r8d, 0C89h; int
0x100431a4e  mov     rdx, r14; char *
0x100431a51  mov     rcx, rbp; char *
0x100431a54  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100431a59  jmp     short loc_100431AB1
0x100431a5b  mov     r8d, [rbx+44h]
0x100431a5f  shl     r8, 3; Size
0x100431a63  mov     rdx, [rbx+48h]; Src
0x100431a67  mov     rcx, rsi; void *
0x100431a6a  call    memmove
0x100431a6f  mov     eax, [rbx+44h]
0x100431a72  xor     edi, edi
0x100431a74  mov     [rsi+rax*8], rdi
0x100431a78  inc     dword ptr [rbx+44h]
0x100431a7b  mov     rcx, [rbx+48h]
0x100431a7f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100431a85  mov     [rbx+48h], rsi
0x100431a89  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431a90  jz      short loc_100431AAF
0x100431a92  mov     [rsp+68h+var_48], rdi
0x100431a97  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100431a9e  mov     r8d, 0C94h; int
0x100431aa4  mov     rdx, r14; char *
0x100431aa7  mov     rcx, rbp; char *
0x100431aaa  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100431aaf  mov     ebx, edi
0x100431ab1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431ab8  jz      short loc_100431ACB
0x100431aba  mov     r8d, 0C74h; int
0x100431ac0  mov     rdx, r14; char *
0x100431ac3  mov     rcx, rbp; char *
0x100431ac6  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100431acb  mov     eax, ebx
0x100431acd  lea     r11, [rsp+68h+var_8]
0x100431ad2  mov     rbx, [r11+10h]
0x100431ad6  mov     rbp, [r11+18h]
0x100431ada  mov     rsi, [r11+20h]
0x100431ade  mov     rdi, [r11+28h]
0x100431ae2  mov     rsp, r11
0x100431ae5  pop     r14
0x100431ae7  retn
```
