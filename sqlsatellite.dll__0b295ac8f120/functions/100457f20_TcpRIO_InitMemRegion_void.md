# TcpRIO::InitMemRegion(void)

- ea: `0x100457f20`
- end: `0x10045822b`
- name: `?InitMemRegion@TcpRIO@@IEAAKXZ`
- size: `779`
- prototype: `unsigned int __fastcall(TcpRIO *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100459830`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10041e4d0`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100457f20`
- `0x100486b14`
- `0x100486bf0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100458176`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100458176`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10045820e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10045820e`
- `sqldk!SystemThread_TlsIndex` at `0x100457f9d`
- `sqldk!SystemThread_TlsIndex` at `0x100458020`
- `sqldk!SystemThread_TlsIndex` at `0x10045810f`
- `sqldk!SystemThread_TlsOffset` at `0x100457fa6`
- `sqldk!SystemThread_TlsOffset` at `0x100458029`
- `sqldk!SystemThread_TlsOffset` at `0x100458118`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457fc1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100458044`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100458133`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457fc1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100458044`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100458133`

## string_xrefs

- `0x100458164`: `sql\common\dk\sni\include\SNI_MemRegion.hpp`
- `0x100457f41`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TcpRIO::InitMemRegion(TcpRIO *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v5; // rsi
  unsigned int v6; // edi
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r14
  SNI_MemRegionProvider *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  CCriticalSectionSOS **v13; // rsi
  __int64 v15; // rbx
  __int64 v16; // rax
  SNI_MemRegionProvider *v17; // rax
  void (*v18)(void *); // [rsp+20h] [rbp-88h]
  _QWORD v19[5]; // [rsp+38h] [rbp-70h] BYREF
  int v20; // [rsp+60h] [rbp-48h]

  v19[3] = "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp";
  v19[4] = "TcpRIO::InitMemRegion";
  v20 = 1102;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::InitMemRegion",
      1102,
      L"API|SNIpConn: %p{SNI_Conn*}",
      *((_QWORD *)this + 4));
  v5 = *(unsigned int *)(*((_QWORD *)this + 43) + 8LL);
  v6 = 0;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v9 = v5;
  v10 = *(SNI_MemRegionProvider **)(8 * v5 + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 992) + 56LL) + 16LL) + 8);
  if ( v10 )
    goto LABEL_12;
  v19[0] = *((_QWORD *)this + 43);
  v19[1] = TcpRIO::StaticRegisterBuffer;
  v19[2] = TcpRIO::StaticUnregisterBuffer;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  v13 = *(CCriticalSectionSOS ***)(*(_QWORD *)(*(_QWORD *)(v12 + 992) + 56LL) + 16LL);
  if ( v13[v9 + 1] )
  {
LABEL_11:
    v10 = v13[v9 + 1];
    if ( v10 )
    {
LABEL_12:
      *(_QWORD *)(*((_QWORD *)this + 4) + 12984LL) = v10;
      goto LABEL_13;
    }
    goto LABEL_29;
  }
  CCriticalSectionSOS::Enter(*v13);
  if ( v13[v9 + 1] )
  {
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)*v13 + 1));
    goto LABEL_11;
  }
  v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v16 = *(_QWORD *)(v15 + 256);
  if ( !v16 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v16 = *(_QWORD *)(v15 + 256);
  }
  v17 = (SNI_MemRegionProvider *)operator new(
                                   0x180u,
                                   *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v16 + 992) + 56LL) + 8LL),
                                   1,
                                   "sql\\common\\dk\\sni\\include\\SNI_MemRegion.hpp",
                                   603,
                                   6u);
  v10 = v17;
  if ( v17 )
    `eh vector constructor iterator'(
      v17,
      0x30u,
      8u,
      (void (*)(void *))SNI_MemRegion::SNI_MemRegion,
      (void (*)(void *))SNI_MemRegion::~SNI_MemRegion);
  else
    v10 = 0;
  if ( v10 && SNI_MemRegionProvider::FInit(v10, (const struct SNI_MemRegionProviderCallbacks *)v19) )
  {
    _InterlockedExchange64((volatile __int64 *)&v13[v9 + 1], (__int64)v10);
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)*v13 + 1));
    goto LABEL_12;
  }
  if ( v10 )
  {
    `eh vector destructor iterator'(v10, 0x30u, 8u, (void (*)(void *))SNI_MemRegion::~SNI_MemRegion);
    operator delete(v10, 0x180u);
  }
  SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)*v13 + 1));
LABEL_29:
  v6 = 14;
LABEL_13:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v18) = v6;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::InitMemRegion",
      1131,
      L"RET|SNI%d{WINERR}\n",
      v18);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp", "TcpRIO::InitMemRegion", 1102, a4);
  return v6;
}

```

## disassembly

```asm
0x100457f20  mov     rax, rsp
0x100457f23  push    rbp
0x100457f24  push    rsi
0x100457f25  push    rdi
0x100457f26  push    r12
0x100457f28  push    r13
0x100457f2a  push    r14
0x100457f2c  push    r15
0x100457f2e  sub     rsp, 70h
0x100457f32  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x100457f3a  mov     [rax+20h], rbx
0x100457f3e  mov     rbp, rcx
0x100457f41  lea     r15, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457f48  mov     [rax-58h], r15
0x100457f4c  lea     r12, aTcprioInitmemr; "TcpRIO::InitMemRegion"
0x100457f53  mov     [rax-50h], r12
0x100457f57  mov     dword ptr [rax-48h], 44Eh
0x100457f5e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457f65  jz      short loc_100457F88
0x100457f67  mov     rax, [rcx+20h]
0x100457f6b  mov     [rsp+0A8h+var_88], rax
0x100457f70  lea     r9, aApiSnipconnPSn_7; "API|SNIpConn: %p{SNI_Conn*}"
0x100457f77  mov     r8d, 44Eh; int
0x100457f7d  mov     rdx, r12; char *
0x100457f80  mov     rcx, r15; char *
0x100457f83  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100457f88  mov     rax, [rbp+158h]
0x100457f8f  mov     esi, [rax+8]
0x100457f92  xor     edi, edi
0x100457f94  mov     rdx, gs:58h
0x100457f9d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457fa4  mov     ecx, [rax]
0x100457fa6  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100457fad  mov     ebx, [rax]
0x100457faf  add     rbx, [rdx+rcx*8]
0x100457fb3  mov     rax, [rbx+100h]
0x100457fba  test    rax, rax
0x100457fbd  jnz     short loc_100457FCE
0x100457fbf  xor     ecx, ecx
0x100457fc1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457fc7  mov     rax, [rbx+100h]
0x100457fce  mov     rax, [rax+3E0h]
0x100457fd5  mov     rcx, [rax+38h]
0x100457fd9  mov     rdx, [rcx+10h]
0x100457fdd  lea     r14, ds:0[rsi*8]
0x100457fe5  mov     rbx, [r14+rdx+8]
0x100457fea  test    rbx, rbx
0x100457fed  jnz     loc_100458096
0x100457ff3  mov     rax, [rbp+158h]
0x100457ffa  mov     [rsp+0A8h+var_70], rax
0x100457fff  lea     rax, ?StaticRegisterBuffer@TcpRIO@@KAKPEAX0KPEA_K@Z; TcpRIO::StaticRegisterBuffer(void *,void *,ulong,unsigned __int64 *)
0x100458006  mov     [rsp+0A8h+var_68], rax
0x10045800b  lea     rax, ?StaticUnregisterBuffer@TcpRIO@@KAXPEAX0K_K@Z; TcpRIO::StaticUnregisterBuffer(void *,void *,ulong,unsigned __int64)
0x100458012  mov     [rsp+0A8h+var_60], rax
0x100458017  mov     rdx, gs:58h
0x100458020  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100458027  mov     ecx, [rax]
0x100458029  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100458030  mov     ebx, [rax]
0x100458032  add     rbx, [rdx+rcx*8]
0x100458036  mov     rax, [rbx+100h]
0x10045803d  test    rax, rax
0x100458040  jnz     short loc_100458051
0x100458042  xor     ecx, ecx
0x100458044  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10045804a  mov     rax, [rbx+100h]
0x100458051  mov     rax, [rax+3E0h]
0x100458058  mov     rcx, [rax+38h]
0x10045805c  mov     rsi, [rcx+10h]
0x100458060  mov     rax, [r14+rsi+8]
0x100458065  test    rax, rax
0x100458068  jnz     short loc_100458088
0x10045806a  mov     rcx, [rsi]; this
0x10045806d  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100458072  mov     rax, [r14+rsi+8]
0x100458077  test    rax, rax
0x10045807a  jz      short loc_1004580FB
0x10045807c  mov     rcx, [rsi]
0x10045807f  mov     rcx, [rcx+8]; this
0x100458083  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100458088  mov     rbx, [r14+rsi+8]
0x10045808d  test    rbx, rbx
0x100458090  jz      loc_100458220
0x100458096  mov     rax, [rbp+20h]
0x10045809a  mov     [rax+32B8h], rbx
0x1004580a1  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004580a8  jz      short loc_1004580C7
0x1004580aa  mov     dword ptr [rsp+0A8h+var_88], edi
0x1004580ae  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004580b5  mov     r8d, 46Bh; int
0x1004580bb  mov     rdx, r12; char *
0x1004580be  mov     rcx, r15; char *
0x1004580c1  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004580c6  nop
0x1004580c7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004580ce  jz      short loc_1004580E1
0x1004580d0  mov     r8d, 44Eh; int
0x1004580d6  mov     rdx, r12; char *
0x1004580d9  mov     rcx, r15; char *
0x1004580dc  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004580e1  mov     eax, edi
0x1004580e3  mov     rbx, [rsp+0A8h+arg_18]
0x1004580eb  add     rsp, 70h
0x1004580ef  pop     r15
0x1004580f1  pop     r14
0x1004580f3  pop     r13
0x1004580f5  pop     r12
0x1004580f7  pop     rdi
0x1004580f8  pop     rsi
0x1004580f9  pop     rbp
0x1004580fa  retn
0x1004580fb  mov     dword ptr [rsp+0A8h+arg_0], 25Bh
0x100458106  mov     rdx, gs:58h
0x10045810f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100458116  mov     ecx, [rax]
0x100458118  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045811f  mov     ebx, [rax]
0x100458121  add     rbx, [rdx+rcx*8]
0x100458125  mov     rax, [rbx+100h]
0x10045812c  test    rax, rax
0x10045812f  jnz     short loc_100458140
0x100458131  xor     ecx, ecx
0x100458133  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100458139  mov     rax, [rbx+100h]
0x100458140  mov     rax, [rax+3E0h]
0x100458147  mov     rcx, [rax+38h]
0x10045814b  mov     rdx, [rcx+8]
0x10045814f  mov     [rsp+0A8h+arg_8], rdx
0x100458157  mov     [rsp+0A8h+var_80], 6
0x10045815c  mov     dword ptr [rsp+0A8h+var_88], 25Bh
0x100458164  lea     r9, aSqlCommonDkSni_17; "sql\\common\\dk\\sni\\include\\SNI_MemR"...
0x10045816b  mov     ecx, 180h
0x100458170  mov     r8d, 1
0x100458176  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10045817c  mov     rbx, rax
0x10045817f  mov     [rsp+0A8h+arg_10], rax
0x100458187  lea     r13, ??1SNI_MemRegion@@QEAA@XZ; SNI_MemRegion::~SNI_MemRegion(void)
0x10045818e  test    rax, rax
0x100458191  jz      short loc_1004581B3
0x100458193  mov     [rsp+0A8h+var_88], r13; void (*)(void *)
0x100458198  lea     r9, ??0SNI_MemRegion@@QEAA@XZ; void (*)(void *)
0x10045819f  mov     edx, 30h ; '0'; unsigned __int64
0x1004581a4  lea     r8d, [rdx-28h]; unsigned __int64
0x1004581a8  mov     rcx, rax; void *
0x1004581ab  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1004581b0  nop
0x1004581b1  jmp     short loc_1004581B6
0x1004581b3  mov     rbx, rdi
0x1004581b6  test    rbx, rbx
0x1004581b9  jz      short loc_1004581E5
0x1004581bb  lea     rdx, [rsp+0A8h+var_70]; struct SNI_MemRegionProviderCallbacks *
0x1004581c0  mov     rcx, rbx; this
0x1004581c3  call    ?FInit@SNI_MemRegionProvider@@QEAA_NAEBUSNI_MemRegionProviderCallbacks@@@Z; SNI_MemRegionProvider::FInit(SNI_MemRegionProviderCallbacks const &)
0x1004581c8  test    al, al
0x1004581ca  jz      short loc_1004581E5
0x1004581cc  mov     rax, rbx
0x1004581cf  xchg    rax, [r14+rsi+8]
0x1004581d4  mov     rcx, [rsi]
0x1004581d7  mov     rcx, [rcx+8]; this
0x1004581db  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x1004581e0  jmp     loc_100458096
0x1004581e5  mov     [rsp+0A8h+arg_0], rbx
0x1004581ed  test    rbx, rbx
0x1004581f0  jz      short loc_100458214
0x1004581f2  mov     r9, r13; void (*)(void *)
0x1004581f5  mov     edx, 30h ; '0'; unsigned __int64
0x1004581fa  lea     r8d, [rdx-28h]; unsigned __int64
0x1004581fe  mov     rcx, rbx; void *
0x100458201  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x100458206  mov     edx, 180h
0x10045820b  mov     rcx, rbx
0x10045820e  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100458214  mov     rcx, [rsi]
0x100458217  mov     rcx, [rcx+8]; this
0x10045821b  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100458220  mov     edi, 0Eh
0x100458225  jmp     loc_1004580A1
```
