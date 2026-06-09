# Smux::OpenSession(SNI_Conn *,SNI_Provider * *)

- ea: `0x100431f20`
- end: `0x1004323e1`
- name: `?OpenSession@Smux@@QEAAKPEAVSNI_Conn@@PEAPEAVSNI_Provider@@@Z`
- size: `1217`
- prototype: `unsigned int __fastcall(Smux *__hidden this, struct SNI_Conn *, struct SNI_Provider **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x100425000`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x10042efe0`
- `0x10042f690`
- `0x100431870`
- `0x100431f20`
- `0x100433010`
- `0x1004349f0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004320ec`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004320ec`
- `sqldk!SystemThread_TlsIndex` at `0x100432089`
- `sqldk!SystemThread_TlsOffset` at `0x100432092`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004320ad`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004320ad`

## string_xrefs

- `0x100431f4b`: `sql\common\dk\sni\src\smux.cpp`
- `0x100432154`: `sql\common\dk\sni\src\smux.cpp`
- `0x100432165`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004321e8`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004322a2`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004322c5`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004322f8`: `sql\common\dk\sni\src\smux.cpp`
- `0x100432394`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004323b8`: `sql\common\dk\sni\src\smux.cpp`
- `0x1004321f7`: `Session::Open`
- `0x10043229b`: `Session::Open`
- `0x1004322be`: `Session::Open`
- `0x100431f56`: `Smux::OpenSession`
- `0x10043214a`: `Smux::OpenSession`
- `0x10043216c`: `Smux::OpenSession`
- `0x1004322f1`: `Smux::OpenSession`
- `0x10043238d`: `Smux::OpenSession`
- `0x1004323b1`: `Smux::OpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Smux::OpenSession(Smux *this, struct SNI_Conn *a2, struct SNI_Provider **a3)
{
  SOS_UnfairRecursiveMutexExtendedGuarantee **v5; // r13
  SOS_UnfairRecursiveMutexExtendedGuarantee **v6; // r12
  unsigned int v7; // ebx
  unsigned __int16 v8; // r15
  unsigned int v9; // ecx
  unsigned int v10; // edx
  __int64 v11; // rbx
  __int64 v12; // rax
  Session *v13; // rax
  Session *v14; // rsi
  SOS_UnfairRecursiveMutexExtendedGuarantee **v15; // rbp
  const wchar_t *v16; // r9
  const wchar_t *v17; // r9
  struct Smux *v19; // [rsp+20h] [rbp-C8h]
  __int64 v20; // [rsp+28h] [rbp-C0h]
  __int64 v21; // [rsp+28h] [rbp-C0h]
  __int64 v22; // [rsp+30h] [rbp-B8h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\smux.cpp",
      "Smux::OpenSession",
      3475,
      L"API|SNI%u#, pConn: %p{SNI_Conn*}, ppProv: %p{SNI_Provider**}\n",
      *((_DWORD *)this + 11),
      a2,
      a3);
  v5 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 6);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v5);
  v6 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)this + 7);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v6);
  if ( *((_DWORD *)this + 20) )
  {
    v7 = -1;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v22) = -1;
      LODWORD(v20) = 19;
      LODWORD(v19) = 5;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Smux::OpenSession",
        3496,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v19,
        v20,
        v22);
    }
    SNISetLastError(5, 0xFFFFFFFFLL, 50119);
    goto LABEL_35;
  }
  if ( *((_DWORD *)this + 16) == *((_DWORD *)this + 17) )
  {
    v7 = Smux::GrowSessionList(this);
    if ( v7 )
    {
LABEL_35:
      *a3 = 0;
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v6[1]);
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v5[1]);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v19) = v7;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\smux.cpp",
          "Smux::OpenSession",
          3583,
          L"RET|SNI%d{WINERR}\n",
          v19);
      }
      goto LABEL_40;
    }
  }
  v8 = *((_WORD *)this + 34);
  v9 = 0;
  v10 = *((_DWORD *)this + 17);
  if ( v10 )
  {
    while ( *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * v9) )
    {
      if ( ++v9 >= v10 )
        goto LABEL_14;
    }
    v8 = v9;
  }
LABEL_14:
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = (Session *)operator new(
                     0xD0u,
                     *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v12 + 992) + 56LL) + 8LL),
                     1,
                     "sql\\common\\dk\\sni\\src\\smux.cpp",
                     3528,
                     6u);
  if ( v13 )
    v14 = Session::Session(v13, a2, *((struct SNI_Provider **)this + 1), v8, this);
  else
    v14 = 0;
  if ( !v14 )
  {
    v7 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v22) = 14;
      LODWORD(v21) = 0;
      LODWORD(v19) = 5;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\smux.cpp",
        "Smux::OpenSession",
        3533,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v19,
        v21,
        v22);
    }
    SNISetLastError(5, 14, 50100);
    goto LABEL_35;
  }
  *((_QWORD *)a2 + 1624) = *(_QWORD *)(*((_QWORD *)this + 4) + 12992LL);
  *((_QWORD *)a2 + 1625) = *(_QWORD *)(*((_QWORD *)this + 4) + 13000LL);
  v7 = (*(__int64 (__fastcall **)(Session *))(*(_QWORD *)v14 + 152LL))(v14);
  if ( v7 )
  {
    (**(void (__fastcall ***)(Session *, __int64))v14)(v14, 1);
    goto LABEL_35;
  }
  *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * v8) = v14;
  *((_QWORD *)a2 + 1577) = v14;
  ++*((_DWORD *)this + 16);
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
  {
    LODWORD(v19) = *((_DWORD *)v14 + 11);
    SNIXE_SNI_ENTER_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::Open", 818, L"API|SNI%u#\n", v19);
  }
  v15 = (SOS_UnfairRecursiveMutexExtendedGuarantee **)*((_QWORD *)v14 + 7);
  CCriticalSectionSOS::Enter((CCriticalSectionSOS *)v15);
  v7 = Session::SendControlPacket(v14, 1u);
  if ( v7 )
  {
    *((_BYTE *)v14 + 163) = 1;
    *((_BYTE *)v14 + 160) = 1;
  }
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v15[1]);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v19) = v7;
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::Open", 836, L"RET|SNI%d{WINERR}\n", v19);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Session::Open", 818, v16);
  if ( v7 )
  {
    *((_QWORD *)a2 + 1577) = 0;
    Smux::RemoveSessionId(this, v8);
    (*(void (__fastcall **)(Session *))(*(_QWORD *)v14 + 72LL))(v14);
    goto LABEL_35;
  }
  *a3 = v14;
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v6[1]);
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(v5[1]);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Smux::OpenSession", 3571, L"RET|SNI%d{WINERR}\n", 0);
  v7 = 0;
LABEL_40:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\smux.cpp", "Smux::OpenSession", 3475, v17);
  return v7;
}

```

## disassembly

```asm
0x100431f20  mov     rax, rsp
0x100431f23  mov     [rax+18h], r8
0x100431f27  push    rbp
0x100431f28  push    rsi
0x100431f29  push    rdi
0x100431f2a  push    r12
0x100431f2c  push    r13
0x100431f2e  push    r14
0x100431f30  push    r15
0x100431f32  sub     rsp, 0B0h
0x100431f39  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x100431f41  mov     [rax+10h], rbx
0x100431f45  mov     r14, rdx
0x100431f48  mov     rdi, rcx
0x100431f4b  lea     rsi, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x100431f52  mov     [rax-68h], rsi
0x100431f56  lea     r15, aSmuxOpensessio; "Smux::OpenSession"
0x100431f5d  mov     [rax-60h], r15
0x100431f61  mov     dword ptr [rax-58h], 0D93h
0x100431f68  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431f6f  jz      short loc_100431F9A
0x100431f71  mov     [rsp+0E8h+var_B8], r8
0x100431f76  mov     [rsp+0E8h+var_C0], rdx
0x100431f7b  mov     eax, [rcx+2Ch]
0x100431f7e  mov     dword ptr [rsp+0E8h+var_C8], eax
0x100431f82  lea     r9, aApiSniUPconnPS_1; "API|SNI%u#, pConn: %p{SNI_Conn*}, ppPro"...
0x100431f89  mov     r8d, 0D93h; int
0x100431f8f  mov     rdx, r15; char *
0x100431f92  mov     rcx, rsi; char *
0x100431f95  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100431f9a  mov     r13, [rdi+30h]
0x100431f9e  mov     [rsp+0E8h+var_98], r13
0x100431fa3  xor     ebp, ebp
0x100431fa5  mov     [rsp+0E8h+var_90], ebp
0x100431fa9  mov     rcx, r13; this
0x100431fac  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100431fb1  mov     [rsp+0E8h+var_90], 1
0x100431fb9  mov     r12, [rdi+38h]
0x100431fbd  mov     [rsp+0E8h+var_A8], r12
0x100431fc2  mov     [rsp+0E8h+var_A0], ebp
0x100431fc6  mov     rcx, r12; this
0x100431fc9  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100431fce  mov     [rsp+0E8h+var_A0], 1
0x100431fd6  cmp     [rdi+50h], ebp
0x100431fd9  jz      short loc_10043202C
0x100431fdb  mov     ebx, 0FFFFFFFFh
0x100431fe0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100431fe7  jz      short loc_100432015
0x100431fe9  mov     dword ptr [rsp+0E8h+var_B8], ebx
0x100431fed  mov     dword ptr [rsp+0E8h+var_C0], 13h
0x100431ff5  mov     dword ptr [rsp+0E8h+var_C8], 5
0x100431ffd  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100432004  mov     r8d, 0DA8h; int
0x10043200a  mov     rdx, r15; char *
0x10043200d  mov     rcx, rsi; char *
0x100432010  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100432015  mov     r8d, 0C3C7h
0x10043201b  mov     edx, ebx
0x10043201d  mov     ecx, 5
0x100432022  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100432027  jmp     loc_1004322FF
0x10043202c  mov     eax, [rdi+44h]
0x10043202f  cmp     [rdi+40h], eax
0x100432032  jnz     short loc_100432046
0x100432034  mov     rcx, rdi; this
0x100432037  call    ?GrowSessionList@Smux@@AEAAKXZ; Smux::GrowSessionList(void)
0x10043203c  mov     ebx, eax
0x10043203e  test    eax, eax
0x100432040  jnz     loc_1004322FF
0x100432046  movzx   r15d, word ptr [rdi+44h]
0x10043204b  mov     ecx, ebp
0x10043204d  mov     edx, [rdi+44h]
0x100432050  test    edx, edx
0x100432052  jz      short loc_100432075
0x100432054  mov     r8, [rdi+48h]
0x100432058  nop     dword ptr [rax+rax+00000000h]
0x100432060  mov     eax, ecx
0x100432062  cmp     qword ptr [r8+rax*8], 0
0x100432067  jz      short loc_100432071
0x100432069  inc     ecx
0x10043206b  cmp     ecx, edx
0x10043206d  jb      short loc_100432060
0x10043206f  jmp     short loc_100432075
0x100432071  movzx   r15d, cx
0x100432075  mov     [rsp+0E8h+arg_0], 0DC8h
0x100432080  mov     rdx, gs:58h
0x100432089  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100432090  mov     ecx, [rax]
0x100432092  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100432099  mov     ebx, [rax]
0x10043209b  add     rbx, [rdx+rcx*8]
0x10043209f  mov     rax, [rbx+100h]
0x1004320a6  test    rax, rax
0x1004320a9  jnz     short loc_1004320BA
0x1004320ab  xor     ecx, ecx
0x1004320ad  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004320b3  mov     rax, [rbx+100h]
0x1004320ba  mov     rax, [rax+3E0h]
0x1004320c1  mov     rcx, [rax+38h]
0x1004320c5  mov     rdx, [rcx+8]
0x1004320c9  mov     [rsp+0E8h+arg_18], rdx
0x1004320d1  mov     byte ptr [rsp+0E8h+var_C0], 6
0x1004320d6  mov     dword ptr [rsp+0E8h+var_C8], 0DC8h
0x1004320de  mov     r9, rsi
0x1004320e1  mov     ecx, 0D0h
0x1004320e6  mov     r8d, 1
0x1004320ec  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004320f2  mov     [rsp+0E8h+var_70], rax
0x1004320f7  test    rax, rax
0x1004320fa  jz      short loc_100432119
0x1004320fc  mov     [rsp+0E8h+var_C8], rdi; struct Smux *
0x100432101  movzx   r9d, r15w; unsigned __int16
0x100432105  mov     r8, [rdi+8]; struct SNI_Provider *
0x100432109  mov     rdx, r14; struct SNI_Conn *
0x10043210c  mov     rcx, rax; this
0x10043210f  call    ??0Session@@QEAA@PEAVSNI_Conn@@PEAVSNI_Provider@@GPEAVSmux@@@Z; Session::Session(SNI_Conn *,SNI_Provider *,ushort,Smux *)
0x100432114  mov     rsi, rax
0x100432117  jmp     short loc_10043211C
0x100432119  mov     rsi, rbp
0x10043211c  test    rsi, rsi
0x10043211f  jnz     short loc_10043218A
0x100432121  lea     ebx, [rsi+0Eh]
0x100432124  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043212b  jz      short loc_100432165
0x10043212d  mov     dword ptr [rsp+0E8h+var_B8], ebx
0x100432131  mov     dword ptr [rsp+0E8h+var_C0], ebp
0x100432135  mov     dword ptr [rsp+0E8h+var_C8], 5
0x10043213d  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100432144  mov     r8d, 0DCDh; int
0x10043214a  lea     r15, aSmuxOpensessio; "Smux::OpenSession"
0x100432151  mov     rdx, r15; char *
0x100432154  lea     rsi, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10043215b  mov     rcx, rsi; char *
0x10043215e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100432163  jmp     short loc_100432173
0x100432165  lea     rsi, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10043216c  lea     r15, aSmuxOpensessio; "Smux::OpenSession"
0x100432173  mov     r8d, 0C3B4h
0x100432179  mov     edx, ebx
0x10043217b  mov     ecx, 5
0x100432180  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100432185  jmp     loc_1004322FF
0x10043218a  mov     rax, [rdi+20h]
0x10043218e  mov     rcx, [rax+32C0h]
0x100432195  mov     [r14+32C0h], rcx
0x10043219c  mov     rax, [rdi+20h]
0x1004321a0  mov     rcx, [rax+32C8h]
0x1004321a7  mov     [r14+32C8h], rcx
0x1004321ae  mov     rax, [rsi]
0x1004321b1  mov     rcx, rsi
0x1004321b4  call    qword ptr [rax+98h]
0x1004321ba  mov     ebx, eax
0x1004321bc  test    eax, eax
0x1004321be  jz      short loc_1004321D2
0x1004321c0  mov     rax, [rsi]
0x1004321c3  mov     edx, 1
0x1004321c8  mov     rcx, rsi
0x1004321cb  call    qword ptr [rax]
0x1004321cd  jmp     loc_1004322F1
0x1004321d2  movzx   ecx, r15w
0x1004321d6  mov     rax, [rdi+48h]
0x1004321da  mov     [rax+rcx*8], rsi
0x1004321de  mov     [r14+3148h], rsi
0x1004321e5  inc     dword ptr [rdi+40h]
0x1004321e8  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x1004321ef  mov     [rsp+0E8h+var_50], rcx
0x1004321f7  lea     rdx, aSessionOpen; "Session::Open"
0x1004321fe  mov     [rsp+0E8h+var_48], rdx
0x100432206  mov     [rsp+0E8h+var_40], 332h
0x100432211  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100432218  jz      short loc_100432233
0x10043221a  mov     eax, [rsi+2Ch]
0x10043221d  mov     dword ptr [rsp+0E8h+var_C8], eax
0x100432221  lea     r9, aApiSniU; "API|SNI%u#\n"
0x100432228  mov     r8d, 332h; int
0x10043222e  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100432233  mov     rbp, [rsi+38h]
0x100432237  mov     [rsp+0E8h+var_88], rbp
0x10043223c  mov     [rsp+0E8h+var_80], 0
0x100432244  mov     rcx, rbp; this
0x100432247  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x10043224c  mov     [rsp+0E8h+var_80], 1
0x100432254  mov     dl, 1; unsigned __int8
0x100432256  mov     rcx, rsi; this
0x100432259  call    ?SendControlPacket@Session@@AEAAKE@Z; Session::SendControlPacket(uchar)
0x10043225e  mov     ebx, eax
0x100432260  test    eax, eax
0x100432262  jz      short loc_100432272
0x100432264  mov     byte ptr [rsi+0A3h], 1
0x10043226b  mov     byte ptr [rsi+0A0h], 1
0x100432272  mov     rcx, [rbp+8]; this
0x100432276  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10043227b  xor     ebp, ebp
0x10043227d  mov     [rsp+0E8h+var_80], ebp
0x100432281  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100432288  jz      short loc_1004322AF
0x10043228a  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x10043228e  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100432295  mov     r8d, 344h; int
0x10043229b  lea     rdx, aSessionOpen; "Session::Open"
0x1004322a2  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x1004322a9  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004322ae  nop
0x1004322af  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004322b6  jz      short loc_1004322D1
0x1004322b8  mov     r8d, 332h; int
0x1004322be  lea     rdx, aSessionOpen; "Session::Open"
0x1004322c5  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x1004322cc  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004322d1  test    ebx, ebx
0x1004322d3  jz      short loc_10043234C
0x1004322d5  mov     [r14+3148h], rbp
0x1004322dc  movzx   edx, r15w; unsigned __int16
0x1004322e0  mov     rcx, rdi; this
0x1004322e3  call    ?RemoveSessionId@Smux@@QEAAXG@Z; Smux::RemoveSessionId(ushort)
0x1004322e8  mov     rax, [rsi]
0x1004322eb  mov     rcx, rsi
0x1004322ee  call    qword ptr [rax+48h]
0x1004322f1  lea     r15, aSmuxOpensessio; "Smux::OpenSession"
0x1004322f8  lea     rsi, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x1004322ff  mov     rax, [rsp+0E8h+arg_10]
0x100432307  mov     [rax], rbp
0x10043230a  mov     rcx, [r12+8]; this
0x10043230f  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100432314  mov     [rsp+0E8h+var_A0], ebp
0x100432318  mov     rcx, [r13+8]; this
0x10043231c  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100432321  mov     [rsp+0E8h+var_90], ebp
0x100432325  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043232c  jz      short loc_1004323A2
0x10043232e  mov     dword ptr [rsp+0E8h+var_C8], ebx
0x100432332  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100432339  mov     r8d, 0DFFh; int
0x10043233f  mov     rdx, r15; char *
0x100432342  mov     rcx, rsi; char *
0x100432345  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043234a  jmp     short loc_1004323A2
0x10043234c  mov     rax, [rsp+0E8h+arg_10]
0x100432354  mov     [rax], rsi
0x100432357  mov     rcx, [r12+8]; this
0x10043235c  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100432361  mov     [rsp+0E8h+var_A0], ebp
0x100432365  mov     rcx, [r13+8]; this
0x100432369  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x10043236e  mov     [rsp+0E8h+var_90], ebp
0x100432372  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100432379  jz      short loc_1004323A0
0x10043237b  mov     [rsp+0E8h+var_C8], rbp
0x100432380  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100432387  mov     r8d, 0DF3h; int
0x10043238d  lea     rdx, aSmuxOpensessio; "Smux::OpenSession"
0x100432394  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x10043239b  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004323a0  mov     ebx, ebp
0x1004323a2  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004323a9  jz      short loc_1004323C4
0x1004323ab  mov     r8d, 0D93h; int
0x1004323b1  lea     rdx, aSmuxOpensessio; "Smux::OpenSession"
0x1004323b8  lea     rcx, aSqlCommonDkSni_12; "sql\\common\\dk\\sni\\src\\smux.cpp"
0x1004323bf  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004323c4  mov     eax, ebx
0x1004323c6  mov     rbx, [rsp+0E8h+arg_8]
0x1004323ce  add     rsp, 0B0h
0x1004323d5  pop     r15
0x1004323d7  pop     r14
0x1004323d9  pop     r13
0x1004323db  pop     r12
0x1004323dd  pop     rdi
0x1004323de  pop     rsi
0x1004323df  pop     rbp
0x1004323e0  retn
```
