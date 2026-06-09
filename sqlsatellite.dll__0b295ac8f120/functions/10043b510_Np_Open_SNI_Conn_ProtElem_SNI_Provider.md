# Np::Open(SNI_Conn *,ProtElem *,SNI_Provider * *)

- ea: `0x10043b510`
- end: `0x10043b7ef`
- name: `?Open@Np@@SAKPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@@Z`
- size: `735`
- prototype: `unsigned int __fastcall(struct SNI_Conn *, struct ProtElem *, struct SNI_Provider **)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100425000`
- `0x100453cd0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042bef0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x10043ac30`
- `0x10043af90`
- `0x10043b510`
- `0x10045a2f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x10043b772`
- `KERNEL32!CloseHandle` at `0x10043b772`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043b5fd`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10043b5fd`
- `sqldk!SystemThread_TlsIndex` at `0x10043b59b`
- `sqldk!SystemThread_TlsOffset` at `0x10043b5a4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b5bf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043b5bf`

## string_xrefs

- `0x10043b53d`: `sql\common\dk\sni\src\np.cpp`
- `0x10043b548`: `Np::Open`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Np::Open(struct SNI_Conn *a1, struct ProtElem *a2, struct SNI_Provider **a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  void *v8; // rax
  unsigned int v9; // esi
  __int64 v10; // r8
  __int64 v11; // rbx
  unsigned int v12; // edi
  int v13; // r8d
  const wchar_t *v14; // r9
  char v15; // al
  void *v16; // rcx
  char *v18; // [rsp+20h] [rbp-78h]
  __int64 v19; // [rsp+28h] [rbp-70h]
  __int64 v20; // [rsp+30h] [rbp-68h]

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::Open",
      1432,
      L"API|SNIpConn: %p{SNI_Conn*}, pProtElem: %p{ProtElem*}, ppProv: %p{SNI_Provider**}\n",
      a1,
      a2,
      a3);
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = operator new(
         0x80u,
         *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL),
         1,
         "sql\\common\\dk\\sni\\src\\np.cpp",
         1436,
         6u);
  v9 = 0;
  if ( v8 )
  {
    v10 = *((unsigned int *)a2 + 1);
    if ( (_DWORD)v10 == 10 )
      v10 = 1;
    v11 = Np::Np(v8, a1, v10);
  }
  else
  {
    v11 = 0;
  }
  if ( !v11 )
  {
    v12 = 14;
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
    {
LABEL_14:
      SNISetLastError(*((_DWORD *)a2 + 1), v12, 0xC3B4u);
LABEL_29:
      *a3 = 0;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v18) = v12;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Open", 1506, L"RET|SNI%d{WINERR}\n", v18);
      }
      v9 = v12;
      goto LABEL_32;
    }
    v13 = 1443;
LABEL_13:
    LODWORD(v20) = v12;
    LODWORD(v19) = 0;
    LODWORD(v18) = *((_DWORD *)a2 + 1);
    SNIXE_SNI_ERROR_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::Open",
      v13,
      L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
      v18,
      v19,
      v20);
    goto LABEL_14;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 152LL))(v11);
  if ( v12 )
  {
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    if ( (g_XeSniPkg_enabledBitmap & 2) == 0 )
      goto LABEL_14;
    v13 = 1452;
    goto LABEL_13;
  }
  v12 = Np::OpenPipe((Np *)v11, (const wchar_t *)a2 + 516, 0x1388u);
  if ( v12 )
    goto LABEL_26;
  v15 = g_XeSniPkg_enabledBitmap;
  if ( (g_XeSniPkg_enabledBitmap & 0x20) != 0 )
  {
    SNIXE_SNI_UPDATE_ID_ON(
      *(_DWORD *)(v11 + 44),
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::Open",
      1466,
      "ID|SNIconnection: %p{ProtElem}",
      a2);
    v15 = g_XeSniPkg_enabledBitmap;
  }
  if ( (v15 & 1) != 0 )
  {
    LODWORD(v18) = *(_DWORD *)(v11 + 44);
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\np.cpp",
      "Np::Open",
      1471,
      L"SNI%u#{Np}, handle: %p{HANDLE}\n",
      v18,
      *(_QWORD *)(v11 + 64));
  }
  *a3 = (struct SNI_Provider *)v11;
  *(_QWORD *)(v11 + 16) = *(_QWORD *)(v11 + 64);
  v12 = SNI::detail::Transport::DWSetSkipCompletionPortOnSuccess((SNI::detail::Transport *)v11);
  if ( v12 )
  {
LABEL_26:
    v16 = *(void **)(v11 + 64);
    if ( v16 != (void *)-1LL )
    {
      CloseHandle(v16);
      *(_QWORD *)(v11 + 64) = -1;
    }
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    goto LABEL_29;
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Open", 1487, L"RET|SNI%d{WINERR}\n", 0);
LABEL_32:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\np.cpp", "Np::Open", 1432, v14);
  return v9;
}

```

## disassembly

```asm
0x10043b510  mov     rax, rsp
0x10043b513  push    rdi
0x10043b514  push    r12
0x10043b516  push    r13
0x10043b518  push    r14
0x10043b51a  push    r15
0x10043b51c  sub     rsp, 70h
0x10043b520  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x10043b528  mov     [rax+8], rbx
0x10043b52c  mov     [rax+10h], rbp
0x10043b530  mov     [rax+18h], rsi
0x10043b534  mov     r14, r8
0x10043b537  mov     rbp, rdx
0x10043b53a  mov     rdi, rcx
0x10043b53d  lea     r15, aSqlCommonDkSni_22; "sql\\common\\dk\\sni\\src\\np.cpp"
0x10043b544  mov     [rax-40h], r15
0x10043b548  lea     r12, aNpOpen; "Np::Open"
0x10043b54f  mov     [rax-38h], r12
0x10043b553  mov     dword ptr [rax-30h], 598h
0x10043b55a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b561  jz      short loc_10043B587
0x10043b563  mov     [rax-68h], r8
0x10043b567  mov     [rax-70h], rdx
0x10043b56b  mov     [rax-78h], rcx
0x10043b56f  lea     r9, aApiSnipconnPSn_8; "API|SNIpConn: %p{SNI_Conn*}, pProtElem:"...
0x10043b576  mov     r8d, 598h; int
0x10043b57c  mov     rdx, r12; char *
0x10043b57f  mov     rcx, r15; char *
0x10043b582  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b587  mov     [rsp+98h+arg_18], 59Ch
0x10043b592  mov     rdx, gs:58h
0x10043b59b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043b5a2  mov     ecx, [rax]
0x10043b5a4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043b5ab  mov     ebx, [rax]
0x10043b5ad  add     rbx, [rdx+rcx*8]
0x10043b5b1  mov     rax, [rbx+100h]
0x10043b5b8  test    rax, rax
0x10043b5bb  jnz     short loc_10043B5CC
0x10043b5bd  xor     ecx, ecx
0x10043b5bf  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043b5c5  mov     rax, [rbx+100h]
0x10043b5cc  mov     rax, [rax+3E0h]
0x10043b5d3  mov     rcx, [rax+38h]
0x10043b5d7  mov     rdx, [rcx+8]
0x10043b5db  mov     [rsp+98h+var_50], rdx
0x10043b5e0  mov     byte ptr [rsp+98h+var_70], 6
0x10043b5e5  mov     dword ptr [rsp+98h+var_78], 59Ch
0x10043b5ed  mov     r9, r15
0x10043b5f0  mov     r13d, 1
0x10043b5f6  mov     r8d, r13d
0x10043b5f9  lea     ecx, [r13+7Fh]
0x10043b5fd  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10043b603  mov     [rsp+98h+var_48], rax
0x10043b608  xor     esi, esi
0x10043b60a  test    rax, rax
0x10043b60d  jz      short loc_10043B62B
0x10043b60f  mov     r8d, [rbp+4]
0x10043b613  cmp     r8d, 0Ah
0x10043b617  cmovz   r8d, r13d
0x10043b61b  mov     rdx, rdi
0x10043b61e  mov     rcx, rax
0x10043b621  call    ??0Np@@QEAA@PEAVSNI_Conn@@W4ProviderNum@@@Z; Np::Np(SNI_Conn *,ProviderNum)
0x10043b626  mov     rbx, rax
0x10043b629  jmp     short loc_10043B62E
0x10043b62b  mov     rbx, rsi
0x10043b62e  test    rbx, rbx
0x10043b631  jnz     short loc_10043B67B
0x10043b633  lea     edi, [rbx+0Eh]
0x10043b636  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b63d  jz      short loc_10043B666
0x10043b63f  mov     r8d, 5A3h; int
0x10043b645  mov     dword ptr [rsp+98h+var_68], edi
0x10043b649  mov     dword ptr [rsp+98h+var_70], esi
0x10043b64d  mov     eax, [rbp+4]
0x10043b650  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043b657  mov     dword ptr [rsp+98h+var_78], eax
0x10043b65b  mov     rdx, r12; char *
0x10043b65e  mov     rcx, r15; char *
0x10043b661  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b666  mov     r8d, 0C3B4h
0x10043b66c  mov     edx, edi
0x10043b66e  mov     ecx, [rbp+4]
0x10043b671  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043b676  jmp     loc_10043B78B
0x10043b67b  mov     rax, [rbx]
0x10043b67e  mov     rcx, rbx
0x10043b681  call    qword ptr [rax+98h]
0x10043b687  mov     edi, eax
0x10043b689  mov     rcx, rbx; this
0x10043b68c  test    eax, eax
0x10043b68e  jz      short loc_10043B6AA
0x10043b690  mov     r8, [rbx]
0x10043b693  mov     edx, r13d
0x10043b696  call    qword ptr [r8]
0x10043b699  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b6a0  jz      short loc_10043B666
0x10043b6a2  mov     r8d, 5ACh
0x10043b6a8  jmp     short loc_10043B645
0x10043b6aa  lea     rdx, [rbp+408h]; wchar_t *
0x10043b6b1  mov     r8d, 1388h; unsigned int
0x10043b6b7  call    ?OpenPipe@Np@@AEAAKPEB_WK@Z; Np::OpenPipe(wchar_t const *,ulong)
0x10043b6bc  mov     edi, eax
0x10043b6be  test    eax, eax
0x10043b6c0  jnz     loc_10043B768
0x10043b6c6  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b6cc  test    al, 20h
0x10043b6ce  jz      short loc_10043B6FB
0x10043b6d0  mov     [rsp+98h+var_70], rbp
0x10043b6d5  lea     rax, aIdSniconnectio; "ID|SNIconnection: %p{ProtElem}"
0x10043b6dc  mov     [rsp+98h+var_78], rax; char *
0x10043b6e1  mov     r9d, 5BAh; int
0x10043b6e7  mov     r8, r12; char *
0x10043b6ea  mov     rdx, r15; char *
0x10043b6ed  mov     ecx, [rbx+2Ch]; int
0x10043b6f0  call    ?SNIXE_SNI_UPDATE_ID_ON@@YAXHPEBD0H0ZZ; SNIXE_SNI_UPDATE_ID_ON(int,char const *,char const *,int,char const *,...)
0x10043b6f5  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b6fb  test    al, 1
0x10043b6fd  jz      short loc_10043B727
0x10043b6ff  mov     rax, [rbx+40h]
0x10043b703  mov     [rsp+98h+var_70], rax
0x10043b708  mov     eax, [rbx+2Ch]
0x10043b70b  mov     dword ptr [rsp+98h+var_78], eax
0x10043b70f  lea     r9, aSniUNpHandlePH; "SNI%u#{Np}, handle: %p{HANDLE}\n"
0x10043b716  mov     r8d, 5BFh; int
0x10043b71c  mov     rdx, r12; char *
0x10043b71f  mov     rcx, r15; char *
0x10043b722  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b727  mov     [r14], rbx
0x10043b72a  mov     rax, [rbx+40h]
0x10043b72e  mov     [rbx+10h], rax
0x10043b732  mov     rcx, rbx; this
0x10043b735  call    ?DWSetSkipCompletionPortOnSuccess@Transport@detail@SNI@@IEAAKXZ; SNI::detail::Transport::DWSetSkipCompletionPortOnSuccess(void)
0x10043b73a  mov     edi, eax
0x10043b73c  test    eax, eax
0x10043b73e  jnz     short loc_10043B768
0x10043b740  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b747  jz      short loc_10043B7B5
0x10043b749  mov     [rsp+98h+var_78], rsi
0x10043b74e  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b755  mov     r8d, 5CFh; int
0x10043b75b  mov     rdx, r12; char *
0x10043b75e  mov     rcx, r15; char *
0x10043b761  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b766  jmp     short loc_10043B7B5
0x10043b768  mov     rcx, [rbx+40h]; hObject
0x10043b76c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x10043b770  jz      short loc_10043B780
0x10043b772  call    cs:__imp_CloseHandle
0x10043b778  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x10043b780  mov     rax, [rbx]
0x10043b783  mov     edx, r13d
0x10043b786  mov     rcx, rbx
0x10043b789  call    qword ptr [rax]
0x10043b78b  mov     [r14], rsi
0x10043b78e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b795  jz      short loc_10043B7B3
0x10043b797  mov     dword ptr [rsp+98h+var_78], edi
0x10043b79b  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043b7a2  mov     r8d, 5E2h; int
0x10043b7a8  mov     rdx, r12; char *
0x10043b7ab  mov     rcx, r15; char *
0x10043b7ae  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043b7b3  mov     esi, edi
0x10043b7b5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043b7bc  jz      short loc_10043B7CF
0x10043b7be  mov     r8d, 598h; int
0x10043b7c4  mov     rdx, r12; char *
0x10043b7c7  mov     rcx, r15; char *
0x10043b7ca  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x10043b7cf  mov     eax, esi
0x10043b7d1  lea     r11, [rsp+98h+var_28]
0x10043b7d6  mov     rbx, [r11+30h]
0x10043b7da  mov     rbp, [r11+38h]
0x10043b7de  mov     rsi, [r11+40h]
0x10043b7e2  mov     rsp, r11
0x10043b7e5  pop     r15
0x10043b7e7  pop     r14
0x10043b7e9  pop     r13
0x10043b7eb  pop     r12
0x10043b7ed  pop     rdi
0x10043b7ee  retn
```
