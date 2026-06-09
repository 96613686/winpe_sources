# TcpRIO::InitCQ(ulong,bool,ulong,SNI_IOCompletionQueue * *)

- ea: `0x100457960`
- end: `0x100457cf2`
- name: `?InitCQ@TcpRIO@@IEAAKK_NKPEAPEAVSNI_IOCompletionQueue@@@Z`
- size: `914`
- prototype: `unsigned int(TcpRIO *__hidden this, unsigned int, bool, unsigned int, struct SNI_IOCompletionQueue **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x100459830`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042c270`
- `0x10042c430`
- `0x100455b40`
- `0x100456730`
- `0x100456900`
- `0x100457960`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100457af6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100457c11`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100457af6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100457c11`
- `sqldk!SystemThread_TlsIndex` at `0x1004579e3`
- `sqldk!SystemThread_TlsIndex` at `0x100457a96`
- `sqldk!SystemThread_TlsIndex` at `0x100457bb1`
- `sqldk!SystemThread_TlsOffset` at `0x1004579ec`
- `sqldk!SystemThread_TlsOffset` at `0x100457a9f`
- `sqldk!SystemThread_TlsOffset` at `0x100457bba`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457a07`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457aba`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457bd5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457a07`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457aba`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457bd5`

## string_xrefs

- `0x100457991`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TcpRIO::InitCQ(
        TcpRIO *this,
        unsigned int a2,
        bool a3,
        const wchar_t *a4,
        struct SNI_IOCompletionQueue **a5)
{
  unsigned int v5; // r14d
  __int64 v7; // r12
  unsigned int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // ebp
  CCriticalSectionSOS **v14; // rsi
  CCriticalSectionSOS **v15; // r14
  TcpRIOCompletionQueue *v16; // rbx
  struct SNI_IOCompletionQueue *v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rax
  TcpRIOCompletionQueue *v20; // rax
  unsigned int v21; // ebp
  bool v22; // zf
  __int64 v23; // rbx
  __int64 v24; // rax
  TcpRIOCompletionQueue *v25; // rax
  __int64 v27; // [rsp+20h] [rbp-68h]

  v5 = (unsigned int)a4;
  v7 = a2;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::InitCQ",
      929,
      L"API|SNIpConn: %p{SNI_Conn*}",
      *((_QWORD *)this + 4));
  v9 = 0;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v11 = *(_QWORD *)(v10 + 256);
  if ( !v11 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v11 = *(_QWORD *)(v10 + 256);
  }
  v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 992) + 56LL) + 64LL);
  if ( *(_DWORD *)(v12 + 12) <= 1u )
    v13 = 0;
  else
    v13 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v12 + 8)) % *(_DWORD *)(v12 + 12);
  if ( a3 )
  {
    v23 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v24 = *(_QWORD *)(v23 + 256);
    if ( !v24 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v24 = *(_QWORD *)(v23 + 256);
    }
    v25 = (TcpRIOCompletionQueue *)operator new(
                                     0x108u,
                                     *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v24 + 992) + 56LL) + 8LL),
                                     1,
                                     "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
                                     985,
                                     6u);
    if ( v25 )
      v16 = TcpRIOCompletionQueue::TcpRIOCompletionQueue(v25, v13, *((struct TcpRIOProviderData **)this + 43));
    else
      v16 = 0;
    if ( !v16 )
    {
      v9 = 14;
      goto LABEL_32;
    }
    v9 = TcpRIOCompletionQueue::Init(v16, a3, v5);
    v22 = v9 == 0;
  }
  else
  {
    v14 = (CCriticalSectionSOS **)(*(_QWORD *)v12 + 152LL * v13);
    v15 = &v14[v7];
    v16 = v15[1];
    if ( v16 )
    {
LABEL_30:
      *a5 = v16;
      goto LABEL_35;
    }
    CCriticalSectionSOS::Enter(v14[18]);
    v17 = v15[1];
    if ( v17 )
    {
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)v14[18] + 1));
      *a5 = v17;
      goto LABEL_35;
    }
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    v20 = (TcpRIOCompletionQueue *)operator new(
                                     0x108u,
                                     *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v19 + 992) + 56LL) + 8LL),
                                     1,
                                     "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
                                     952,
                                     6u);
    if ( v20 )
      v16 = TcpRIOCompletionQueue::TcpRIOCompletionQueue(v20, v13, *((struct TcpRIOProviderData **)this + 43));
    else
      v16 = 0;
    if ( !v16 )
    {
      v9 = 14;
      SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)v14[18] + 1));
      goto LABEL_32;
    }
    v21 = TcpRIOCompletionQueue::Init(v16, 0, 0x4000u);
    if ( !v21 )
      v21 = SNI_NodeIOCompletionQueue::SetIOQueue((SNI_NodeIOCompletionQueue *)v14, v7, v16);
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*((SOS_UnfairRecursiveMutexExtendedGuarantee **)v14[18] + 1));
    v9 = v21;
    v22 = v21 == 0;
  }
  if ( v22 )
    goto LABEL_30;
LABEL_32:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 44, 0xFFFFFFFF) == 1 && v16 )
    (**(void (__fastcall ***)(TcpRIOCompletionQueue *, __int64))v16)(v16, 1);
LABEL_35:
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v27) = v9;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIO::InitCQ",
      1010,
      L"RET|SNI%d{WINERR}\n",
      v27);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp", "TcpRIO::InitCQ", 929, a4);
  return v9;
}

```

## disassembly

```asm
0x100457960  mov     rax, rsp
0x100457963  push    rdi
0x100457964  push    r12
0x100457966  push    r13
0x100457968  push    r14
0x10045796a  push    r15
0x10045796c  sub     rsp, 60h
0x100457970  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x100457978  mov     [rax+8], rbx
0x10045797c  mov     [rax+10h], rbp
0x100457980  mov     [rax+20h], rsi
0x100457984  mov     r14d, r9d
0x100457987  movzx   esi, r8b
0x10045798b  mov     r12d, edx
0x10045798e  mov     r15, rcx
0x100457991  lea     r13, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457998  mov     [rax-40h], r13
0x10045799c  lea     rcx, aTcprioInitcq; "TcpRIO::InitCQ"
0x1004579a3  mov     [rax-38h], rcx
0x1004579a7  mov     dword ptr [rax-30h], 3A1h
0x1004579ae  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004579b5  jz      short loc_1004579D8
0x1004579b7  mov     rax, [r15+20h]
0x1004579bb  mov     [rsp+88h+var_68], rax
0x1004579c0  lea     r9, aApiSnipconnPSn_7; "API|SNIpConn: %p{SNI_Conn*}"
0x1004579c7  mov     r8d, 3A1h; int
0x1004579cd  mov     rdx, rcx; char *
0x1004579d0  mov     rcx, r13; char *
0x1004579d3  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004579d8  xor     edi, edi
0x1004579da  mov     rdx, gs:58h
0x1004579e3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004579ea  mov     ecx, [rax]
0x1004579ec  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004579f3  mov     ebx, [rax]
0x1004579f5  add     rbx, [rdx+rcx*8]
0x1004579f9  mov     rax, [rbx+100h]
0x100457a00  test    rax, rax
0x100457a03  jnz     short loc_100457A14
0x100457a05  xor     ecx, ecx
0x100457a07  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457a0d  mov     rax, [rbx+100h]
0x100457a14  mov     rax, [rax+3E0h]
0x100457a1b  mov     rcx, [rax+38h]
0x100457a1f  mov     r8, [rcx+40h]
0x100457a23  cmp     dword ptr [r8+0Ch], 1
0x100457a28  jbe     short loc_100457A41
0x100457a2a  mov     eax, 1
0x100457a2f  lock xadd [r8+8], eax
0x100457a35  inc     eax
0x100457a37  xor     edx, edx
0x100457a39  div     dword ptr [r8+0Ch]
0x100457a3d  mov     ebp, edx
0x100457a3f  jmp     short loc_100457A43
0x100457a41  mov     ebp, edi
0x100457a43  test    sil, sil
0x100457a46  jnz     loc_100457B9D
0x100457a4c  mov     eax, ebp
0x100457a4e  imul    rsi, rax, 98h
0x100457a55  add     rsi, [r8]
0x100457a58  lea     r14, [rsi+r12*8]
0x100457a5c  mov     rbx, [r14+8]
0x100457a60  test    rbx, rbx
0x100457a63  jnz     loc_100457C54
0x100457a69  mov     rcx, [rsi+90h]; this
0x100457a70  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100457a75  mov     rbx, [r14+8]
0x100457a79  test    rbx, rbx
0x100457a7c  jnz     loc_100457B7D
0x100457a82  mov     [rsp+88h+arg_10], 3B8h
0x100457a8d  mov     rdx, gs:58h
0x100457a96  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457a9d  mov     ecx, [rax]
0x100457a9f  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100457aa6  mov     ebx, [rax]
0x100457aa8  add     rbx, [rdx+rcx*8]
0x100457aac  mov     rax, [rbx+100h]
0x100457ab3  test    rax, rax
0x100457ab6  jnz     short loc_100457AC7
0x100457ab8  xor     ecx, ecx
0x100457aba  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457ac0  mov     rax, [rbx+100h]
0x100457ac7  mov     rax, [rax+3E0h]
0x100457ace  mov     rcx, [rax+38h]
0x100457ad2  mov     rdx, [rcx+8]
0x100457ad6  mov     [rsp+88h+var_50], rdx
0x100457adb  mov     [rsp+88h+var_60], 6
0x100457ae0  mov     dword ptr [rsp+88h+var_68], 3B8h
0x100457ae8  mov     r9, r13
0x100457aeb  mov     ecx, 108h
0x100457af0  mov     r8d, 1
0x100457af6  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100457afc  mov     [rsp+88h+var_48], rax
0x100457b01  test    rax, rax
0x100457b04  jz      short loc_100457B1C
0x100457b06  mov     r8, [r15+158h]; struct TcpRIOProviderData *
0x100457b0d  mov     edx, ebp; unsigned int
0x100457b0f  mov     rcx, rax; this
0x100457b12  call    ??0TcpRIOCompletionQueue@@QEAA@KPEAUTcpRIOProviderData@@@Z; TcpRIOCompletionQueue::TcpRIOCompletionQueue(ulong,TcpRIOProviderData *)
0x100457b17  mov     rbx, rax
0x100457b1a  jmp     short loc_100457B1F
0x100457b1c  mov     rbx, rdi
0x100457b1f  test    rbx, rbx
0x100457b22  jz      short loc_100457B63
0x100457b24  xor     edx, edx; bool
0x100457b26  mov     r8d, 4000h; unsigned int
0x100457b2c  mov     rcx, rbx; this
0x100457b2f  call    ?Init@TcpRIOCompletionQueue@@QEAAK_NK@Z; TcpRIOCompletionQueue::Init(bool,ulong)
0x100457b34  mov     ebp, eax
0x100457b36  test    eax, eax
0x100457b38  jnz     short loc_100457B4A
0x100457b3a  mov     r8, rbx; struct SNI_IOCompletionQueue *
0x100457b3d  mov     edx, r12d; unsigned int
0x100457b40  mov     rcx, rsi; this
0x100457b43  call    ?SetIOQueue@SNI_NodeIOCompletionQueue@@QEAAKKPEAVSNI_IOCompletionQueue@@@Z; SNI_NodeIOCompletionQueue::SetIOQueue(ulong,SNI_IOCompletionQueue *)
0x100457b48  mov     ebp, eax
0x100457b4a  mov     rcx, [rsi+90h]
0x100457b51  mov     rcx, [rcx+8]; this
0x100457b55  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100457b5a  mov     edi, ebp
0x100457b5c  test    ebp, ebp
0x100457b5e  jmp     loc_100457C52
0x100457b63  mov     edi, 0Eh
0x100457b68  mov     rcx, [rsi+90h]
0x100457b6f  mov     rcx, [rcx+8]; this
0x100457b73  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100457b78  jmp     loc_100457C66
0x100457b7d  mov     rcx, [rsi+90h]
0x100457b84  mov     rcx, [rcx+8]; this
0x100457b88  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100457b8d  mov     rcx, [rsp+88h+arg_20]
0x100457b95  mov     [rcx], rbx
0x100457b98  jmp     loc_100457C8A
0x100457b9d  mov     [rsp+88h+arg_10], 3D9h
0x100457ba8  mov     rdx, gs:58h
0x100457bb1  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457bb8  mov     ecx, [rax]
0x100457bba  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100457bc1  mov     ebx, [rax]
0x100457bc3  add     rbx, [rdx+rcx*8]
0x100457bc7  mov     rax, [rbx+100h]
0x100457bce  test    rax, rax
0x100457bd1  jnz     short loc_100457BE2
0x100457bd3  xor     ecx, ecx
0x100457bd5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100457bdb  mov     rax, [rbx+100h]
0x100457be2  mov     rax, [rax+3E0h]
0x100457be9  mov     rcx, [rax+38h]
0x100457bed  mov     rdx, [rcx+8]
0x100457bf1  mov     [rsp+88h+var_48], rdx
0x100457bf6  mov     [rsp+88h+var_60], 6
0x100457bfb  mov     dword ptr [rsp+88h+var_68], 3D9h
0x100457c03  mov     r9, r13
0x100457c06  mov     ecx, 108h
0x100457c0b  mov     r8d, 1
0x100457c11  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100457c17  mov     [rsp+88h+var_50], rax
0x100457c1c  test    rax, rax
0x100457c1f  jz      short loc_100457C37
0x100457c21  mov     r8, [r15+158h]; struct TcpRIOProviderData *
0x100457c28  mov     edx, ebp; unsigned int
0x100457c2a  mov     rcx, rax; this
0x100457c2d  call    ??0TcpRIOCompletionQueue@@QEAA@KPEAUTcpRIOProviderData@@@Z; TcpRIOCompletionQueue::TcpRIOCompletionQueue(ulong,TcpRIOProviderData *)
0x100457c32  mov     rbx, rax
0x100457c35  jmp     short loc_100457C3A
0x100457c37  mov     rbx, rdi
0x100457c3a  test    rbx, rbx
0x100457c3d  jz      short loc_100457C61
0x100457c3f  mov     r8d, r14d; unsigned int
0x100457c42  movzx   edx, sil; bool
0x100457c46  mov     rcx, rbx; this
0x100457c49  call    ?Init@TcpRIOCompletionQueue@@QEAAK_NK@Z; TcpRIOCompletionQueue::Init(bool,ulong)
0x100457c4e  mov     edi, eax
0x100457c50  test    eax, eax
0x100457c52  jnz     short loc_100457C66
0x100457c54  mov     rcx, [rsp+88h+arg_20]
0x100457c5c  mov     [rcx], rbx
0x100457c5f  jmp     short loc_100457C8A
0x100457c61  mov     edi, 0Eh
0x100457c66  mov     eax, 0FFFFFFFFh
0x100457c6b  lock xadd [rbx+0B0h], eax
0x100457c73  cmp     eax, 1
0x100457c76  jnz     short loc_100457C8A
0x100457c78  test    rbx, rbx
0x100457c7b  jz      short loc_100457C8A
0x100457c7d  mov     rax, [rbx]
0x100457c80  mov     edx, 1
0x100457c85  mov     rcx, rbx
0x100457c88  call    qword ptr [rax]
0x100457c8a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457c91  jz      short loc_100457CB4
0x100457c93  mov     dword ptr [rsp+88h+var_68], edi
0x100457c97  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100457c9e  mov     r8d, 3F2h; int
0x100457ca4  lea     rdx, aTcprioInitcq; "TcpRIO::InitCQ"
0x100457cab  mov     rcx, r13; char *
0x100457cae  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100457cb3  nop
0x100457cb4  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457cbb  jz      short loc_100457CD2
0x100457cbd  mov     r8d, 3A1h; int
0x100457cc3  lea     rdx, aTcprioInitcq; "TcpRIO::InitCQ"
0x100457cca  mov     rcx, r13; char *
0x100457ccd  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100457cd2  mov     eax, edi
0x100457cd4  lea     r11, [rsp+88h+var_28]
0x100457cd9  mov     rbx, [r11+30h]
0x100457cdd  mov     rbp, [r11+38h]
0x100457ce1  mov     rsi, [r11+48h]
0x100457ce5  mov     rsp, r11
0x100457ce8  pop     r15
0x100457cea  pop     r14
0x100457cec  pop     r13
0x100457cee  pop     r12
0x100457cf0  pop     rdi
0x100457cf1  retn
```
