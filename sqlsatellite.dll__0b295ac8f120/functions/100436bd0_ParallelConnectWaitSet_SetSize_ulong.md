# ParallelConnectWaitSet::SetSize(ulong)

- ea: `0x100436bd0`
- end: `0x100436e7b`
- name: `?SetSize@ParallelConnectWaitSet@@AEAAKK@Z`
- size: `683`
- prototype: `unsigned int(ParallelConnectWaitSet *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100438970`

## callees

- `0x10042b9b0`
- `0x1004349f0`
- `0x100436bd0`
- `0x100486bf0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436c86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436d9d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436e36`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436c86`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436d9d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100436e36`
- `sqldk!SystemThread_TlsIndex` at `0x100436c04`
- `sqldk!SystemThread_TlsIndex` at `0x100436d34`
- `sqldk!SystemThread_TlsIndex` at `0x100436dcd`
- `sqldk!SystemThread_TlsOffset` at `0x100436c0e`
- `sqldk!SystemThread_TlsOffset` at `0x100436d3d`
- `sqldk!SystemThread_TlsOffset` at `0x100436dd6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436c29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436d58`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436df1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436c29`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436d58`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100436df1`

## string_xrefs

- `0x100436c75`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100436d02`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100436d89`: `sql\common\dk\sni\src\tcp.cpp`
- `0x100436e22`: `sql\common\dk\sni\src\tcp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParallelConnectWaitSet::SetSize(ParallelConnectWaitSet *this, unsigned int a2)
{
  unsigned __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rax
  struct IMemObj *v7; // r10
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  unsigned __int64 *v11; // rax
  _QWORD *v12; // rdi
  int v13; // r8d
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  void *v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int64 v23; // rax
  void *v24; // rax
  void (*v25)(void *); // [rsp+20h] [rbp-58h]
  __int64 v26; // [rsp+28h] [rbp-50h]

  v4 = a2;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v6 = *(_QWORD *)(v5 + 256);
  if ( !v6 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v6 = *(_QWORD *)(v5 + 256);
  }
  v7 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v6 + 992) + 56LL) + 8LL);
  v8 = 48 * v4;
  if ( !is_mul_ok(v4, 0x30u) )
    v8 = -1;
  v9 = __CFADD__(v8, 8);
  v10 = v8 + 8;
  if ( v9 )
    v10 = -1;
  v11 = (unsigned __int64 *)operator new[](v10, v7, 1, "sql\\common\\dk\\sni\\src\\tcp.cpp", 3933, 6u);
  if ( v11 )
  {
    *v11 = v4;
    v12 = v11 + 1;
    `eh vector constructor iterator'(
      v11 + 1,
      0x30u,
      v4,
      (void (*)(void *))TcpConnection::TcpConnection,
      (void (*)(void *))TcpConnection::~TcpConnection);
  }
  else
  {
    v12 = 0;
  }
  *((_QWORD *)this + 1) = v12;
  if ( !v12 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
    {
LABEL_14:
      SNISetLastError(7, 14, 50100);
      return 14;
    }
    v13 = 3937;
LABEL_13:
    LODWORD(v26) = 0;
    LODWORD(v25) = 7;
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "ParallelConnectWaitSet::SetSize",
      v13,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      v25,
      v26,
      14);
    goto LABEL_14;
  }
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = *(_QWORD *)(*(_QWORD *)(v16 + 992) + 56LL);
  v18 = 8 * v4;
  if ( !is_mul_ok(v4, 8u) )
    v18 = -1;
  v19 = operator new[](v18, *(struct IMemObj **)(v17 + 8), 1, "sql\\common\\dk\\sni\\src\\tcp.cpp", 3942, 6u);
  *((_QWORD *)this + 2) = v19;
  if ( !v19 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_14;
    v13 = 3946;
    goto LABEL_13;
  }
  v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v21 = *(_QWORD *)(v20 + 256);
  if ( !v21 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v21 = *(_QWORD *)(v20 + 256);
  }
  v22 = *(_QWORD *)(*(_QWORD *)(v21 + 992) + 56LL);
  v23 = 8 * v4;
  if ( !is_mul_ok(v4, 8u) )
    v23 = -1;
  v24 = operator new[](v23, *(struct IMemObj **)(v22 + 8), 1, "sql\\common\\dk\\sni\\src\\tcp.cpp", 3951, 6u);
  *((_QWORD *)this + 3) = v24;
  if ( !v24 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_14;
    v13 = 3955;
    goto LABEL_13;
  }
  *((_DWORD *)this + 9) = a2;
  *((_DWORD *)this + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x100436bd0  mov     rax, rsp
0x100436bd3  push    rbp
0x100436bd4  push    rsi
0x100436bd5  push    rdi
0x100436bd6  push    r14
0x100436bd8  push    r15
0x100436bda  sub     rsp, 50h
0x100436bde  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x100436be6  mov     [rax+20h], rbx
0x100436bea  mov     ebp, edx
0x100436bec  mov     rbx, rcx
0x100436bef  xor     r14d, r14d
0x100436bf2  mov     esi, edx
0x100436bf4  mov     dword ptr [rax+10h], 0F5Dh
0x100436bfb  mov     r9, gs:58h
0x100436c04  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436c0b  mov     r8d, [rax]
0x100436c0e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100436c15  mov     edi, [rax]
0x100436c17  add     rdi, [r9+r8*8]
0x100436c1b  mov     rax, [rdi+100h]
0x100436c22  test    rax, rax
0x100436c25  jnz     short loc_100436C36
0x100436c27  xor     ecx, ecx
0x100436c29  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100436c2f  mov     rax, [rdi+100h]
0x100436c36  mov     rax, [rax+3E0h]
0x100436c3d  mov     rcx, [rax+38h]
0x100436c41  mov     r10, [rcx+8]
0x100436c45  mov     [rsp+78h+arg_0], r10
0x100436c4d  mov     eax, 30h ; '0'
0x100436c52  mul     rsi
0x100436c55  mov     r15, 0FFFFFFFFFFFFFFFFh
0x100436c5c  cmovo   rax, r15
0x100436c60  add     rax, 8
0x100436c64  cmovb   rax, r15
0x100436c68  mov     byte ptr [rsp+78h+var_50], 6
0x100436c6d  mov     dword ptr [rsp+78h+var_58], 0F5Dh
0x100436c75  lea     r9, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100436c7c  lea     r8d, [r15+2]
0x100436c80  mov     rdx, r10
0x100436c83  mov     rcx, rax
0x100436c86  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100436c8c  mov     [rsp+78h+arg_10], rax
0x100436c94  test    rax, rax
0x100436c97  jz      short loc_100436CC4
0x100436c99  mov     [rax], rsi
0x100436c9c  lea     rdi, [rax+8]
0x100436ca0  lea     rax, ??1TcpConnection@@QEAA@XZ; TcpConnection::~TcpConnection(void)
0x100436ca7  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x100436cac  lea     r9, ??0TcpConnection@@QEAA@XZ; void (*)(void *)
0x100436cb3  mov     r8, rsi; unsigned __int64
0x100436cb6  lea     edx, [r15+31h]; unsigned __int64
0x100436cba  mov     rcx, rdi; void *
0x100436cbd  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x100436cc2  jmp     short loc_100436CC7
0x100436cc4  mov     rdi, r14
0x100436cc7  mov     [rbx+8], rdi
0x100436ccb  test    rdi, rdi
0x100436cce  jnz     short loc_100436D2B
0x100436cd0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436cd7  jz      short loc_100436D0E
0x100436cd9  mov     r8d, 0F61h; int
0x100436cdf  mov     [rsp+78h+var_48], 0Eh
0x100436ce7  mov     dword ptr [rsp+78h+var_50], r14d
0x100436cec  mov     dword ptr [rsp+78h+var_58], 7
0x100436cf4  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100436cfb  lea     rdx, aParallelconnec_1; "ParallelConnectWaitSet::SetSize"
0x100436d02  lea     rcx, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100436d09  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100436d0e  mov     edx, 0Eh
0x100436d13  lea     ecx, [rdx-7]
0x100436d16  mov     r8d, 0C3B4h
0x100436d1c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100436d21  mov     eax, 0Eh
0x100436d26  jmp     loc_100436E67
0x100436d2b  mov     rdx, gs:58h
0x100436d34  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436d3b  mov     ecx, [rax]
0x100436d3d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100436d44  mov     edi, [rax]
0x100436d46  add     rdi, [rdx+rcx*8]
0x100436d4a  mov     rax, [rdi+100h]
0x100436d51  test    rax, rax
0x100436d54  jnz     short loc_100436D65
0x100436d56  xor     ecx, ecx
0x100436d58  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100436d5e  mov     rax, [rdi+100h]
0x100436d65  mov     rax, [rax+3E0h]
0x100436d6c  mov     rcx, [rax+38h]
0x100436d70  mov     eax, 8
0x100436d75  mul     rsi
0x100436d78  cmovo   rax, r15
0x100436d7c  mov     byte ptr [rsp+78h+var_50], 6
0x100436d81  mov     dword ptr [rsp+78h+var_58], 0F66h
0x100436d89  lea     r9, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100436d90  mov     r8d, 1
0x100436d96  mov     rdx, [rcx+8]
0x100436d9a  mov     rcx, rax
0x100436d9d  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100436da3  mov     [rbx+10h], rax
0x100436da7  test    rax, rax
0x100436daa  jnz     short loc_100436DC4
0x100436dac  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436db3  jz      loc_100436D0E
0x100436db9  mov     r8d, 0F6Ah
0x100436dbf  jmp     loc_100436CDF
0x100436dc4  mov     rdx, gs:58h
0x100436dcd  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436dd4  mov     ecx, [rax]
0x100436dd6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100436ddd  mov     edi, [rax]
0x100436ddf  add     rdi, [rdx+rcx*8]
0x100436de3  mov     rax, [rdi+100h]
0x100436dea  test    rax, rax
0x100436ded  jnz     short loc_100436DFE
0x100436def  xor     ecx, ecx
0x100436df1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100436df7  mov     rax, [rdi+100h]
0x100436dfe  mov     rax, [rax+3E0h]
0x100436e05  mov     rcx, [rax+38h]
0x100436e09  mov     eax, 8
0x100436e0e  mul     rsi
0x100436e11  cmovo   rax, r15
0x100436e15  mov     byte ptr [rsp+78h+var_50], 6
0x100436e1a  mov     dword ptr [rsp+78h+var_58], 0F6Fh
0x100436e22  lea     r9, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100436e29  mov     r8d, 1
0x100436e2f  mov     rdx, [rcx+8]
0x100436e33  mov     rcx, rax
0x100436e36  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100436e3c  mov     [rbx+18h], rax
0x100436e40  test    rax, rax
0x100436e43  jnz     short loc_100436E5D
0x100436e45  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100436e4c  jz      loc_100436D0E
0x100436e52  mov     r8d, 0F73h
0x100436e58  jmp     loc_100436CDF
0x100436e5d  mov     [rbx+24h], ebp
0x100436e60  mov     [rbx+20h], r14d
0x100436e64  mov     eax, r14d
0x100436e67  mov     rbx, [rsp+78h+arg_18]
0x100436e6f  add     rsp, 50h
0x100436e73  pop     r15
0x100436e75  pop     r14
0x100436e77  pop     rdi
0x100436e78  pop     rsi
0x100436e79  pop     rbp
0x100436e7a  retn
```
