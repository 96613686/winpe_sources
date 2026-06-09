# CleanupCurrentThread(int)

- ea: `0x18002ffc0`
- end: `0x180030270`
- name: `?CleanupCurrentThread@@YAXH@Z`
- size: `688`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f690`
- `0x18009da20`

## callees

- `0x1800150e0`
- `0x18002ffc0`
- `0x180030278`
- `0x1800302c4`
- `0x18003030c`
- `0x18005d4dc`
- `0x18005d864`
- `0x180081800`
- `0x1800bbfc0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003002f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003011a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003002f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003011a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030152`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003009b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003009b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800300e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800300e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002fff6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002fff6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ffcf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002ffcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800301bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800301d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003020d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800301bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800301d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003020d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030242`

## pseudocode

```c
void __fastcall CleanupCurrentThread(int a1)
{
  char *Value; // rbx
  _QWORD *v3; // rdx
  void *v4; // rdi
  __int64 v5; // rax
  char *v6; // rdi
  char *v7; // rdi
  void *v8; // rdi
  __int64 v9; // rcx
  NotificationWindow **v10; // rdi
  NotificationWindow *v11; // rsi
  char *v12; // rax
  NotificationWindow *v13; // rsi
  void *v14; // rcx
  _QWORD *v15; // rsi
  int v16; // edi
  void *v17; // rdi
  CPlex *v18; // rcx
  int v19; // r14d
  __int64 v20; // [rsp+48h] [rbp+10h] BYREF

  Value = (char *)TlsGetValue(gTlsIndex);
  if ( Value )
  {
    TlsSetValue(gTlsIndex, 0);
    EnterCriticalSection(&stru_18015C010);
    v3 = (_QWORD *)qword_18015DDF0;
    if ( qword_18015DDF0 )
    {
      while ( 1 )
      {
        v3 = (_QWORD *)*v3;
        if ( !v3 )
          break;
        if ( (char *)v3[2] == Value )
        {
          CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt();
          break;
        }
      }
    }
    LeaveCriticalSection(&stru_18015C010);
    *((_DWORD *)Value + 1) |= 4u;
    v4 = (void *)*((_QWORD *)Value + 2);
    if ( v4 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll(*((_QWORD *)Value + 2));
      CoTaskMemFree(v4);
      *((_QWORD *)Value + 2) = 0;
    }
    v5 = *((_QWORD *)Value + 6);
    if ( v5 )
    {
      v15 = *(_QWORD **)v5;
      v16 = 0;
      v19 = *(_DWORD *)(v5 + 16);
      if ( v19 > 0 )
      {
        do
        {
          v14 = (void *)v15[2];
          v15 = (_QWORD *)*v15;
          if ( v14 )
            CoTaskMemFree(v14);
          ++v16;
        }
        while ( v16 < v19 );
      }
      v17 = (void *)*((_QWORD *)Value + 6);
      if ( v17 )
      {
        v18 = (CPlex *)*((_QWORD *)v17 + 4);
        *((_DWORD *)v17 + 4) = 0;
        *((_QWORD *)v17 + 3) = 0;
        *((_QWORD *)v17 + 1) = 0;
        *(_QWORD *)v17 = 0;
        CPlex::FreeDataChain(v18);
        *((_QWORD *)v17 + 4) = 0;
        CoTaskMemFree(v17);
      }
      *((_QWORD *)Value + 6) = 0;
    }
    v6 = (char *)*((_QWORD *)Value + 4);
    if ( v6 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll(v6 + 8);
      CoTaskMemFree(v6);
      *((_QWORD *)Value + 4) = 0;
    }
    v7 = (char *)*((_QWORD *)Value + 3);
    if ( v7 )
    {
      CList<CClBinding *,CClBinding *>::RemoveAll(v7 + 8);
      CoTaskMemFree(v7);
      *((_QWORD *)Value + 3) = 0;
    }
    v8 = (void *)*((_QWORD *)Value + 5);
    if ( v8 )
    {
      CCDLPacketMgr::~CCDLPacketMgr(*((CCDLPacketMgr **)Value + 5));
      CoTaskMemFree(v8);
      *((_QWORD *)Value + 5) = 0;
    }
    v9 = *((_QWORD *)Value + 7);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)Value + 7) = 0;
    }
    v20 = 0;
    EnterCriticalSection(&stru_18015C010);
    v10 = (NotificationWindow **)(Value + 552);
    if ( *((_QWORD *)Value + 69) )
    {
      Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(&v20);
      v11 = *v10;
      if ( *v10 )
        goto LABEL_24;
      v12 = (char *)operator new(0x40u);
      v11 = (NotificationWindow *)v12;
      if ( v12 )
      {
        *(_DWORD *)v12 = 1;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 24));
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 1) = 0;
      }
      else
      {
        v11 = 0;
      }
      if ( *v10 )
        NotificationWindow::Release(*v10);
      *v10 = v11;
      if ( v11 )
LABEL_24:
        _InterlockedIncrement((volatile signed __int32 *)v11);
      v13 = *v10;
      Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(Value + 552);
      LeaveCriticalSection(&stru_18015C010);
      if ( v13 )
      {
        NotificationWindow::Shutdown(v13, a1 != 0);
        NotificationWindow::Release(v13);
      }
    }
    else
    {
      LeaveCriticalSection(&stru_18015C010);
    }
    HeapFree(g_hHeap, 0, Value);
  }
}

```

## disassembly

```asm
0x18002ffc0  push    rbx
0x18002ffc2  push    rbp
0x18002ffc3  sub     rsp, 28h
0x18002ffc7  mov     ebp, ecx
0x18002ffc9  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18002ffcf  call    cs:__imp_TlsGetValue
0x18002ffd5  mov     rbx, rax
0x18002ffd8  test    rax, rax
0x18002ffdb  jnz     short loc_18002FFE4
0x18002ffdd  add     rsp, 28h
0x18002ffe1  pop     rbp
0x18002ffe2  pop     rbx
0x18002ffe3  retn
0x18002ffe4  mov     ecx, cs:?gTlsIndex@@3KA; dwTlsIndex
0x18002ffea  xor     edx, edx; lpTlsValue
0x18002ffec  mov     [rsp+38h+arg_10], rdi
0x18002fff1  mov     [rsp+38h+var_18], r15
0x18002fff6  call    cs:__imp_TlsSetValue
0x18002fffc  lea     rcx, stru_18015C010; lpCriticalSection
0x180030003  call    cs:__imp_EnterCriticalSection
0x180030009  mov     rdx, cs:qword_18015DDF0
0x180030010  test    rdx, rdx
0x180030013  jz      short loc_180030028
0x180030015  mov     rdx, [rdx]
0x180030018  test    rdx, rdx
0x18003001b  jz      short loc_180030028
0x18003001d  cmp     [rdx+10h], rbx
0x180030021  jnz     short loc_180030015
0x180030023  call    ?RemoveAt@?$CList@PEAUtagSUrlMkTlsData@@PEAU1@@@QEAAXPEAX@Z; CList<tagSUrlMkTlsData *,tagSUrlMkTlsData *>::RemoveAt(void *)
0x180030028  lea     rcx, stru_18015C010; lpCriticalSection
0x18003002f  call    cs:__imp_LeaveCriticalSection
0x180030035  or      dword ptr [rbx+4], 4
0x180030039  xor     r15d, r15d
0x18003003c  mov     rdi, [rbx+10h]
0x180030040  test    rdi, rdi
0x180030043  jnz     loc_1800301CE
0x180030049  mov     rax, [rbx+30h]
0x18003004d  mov     [rsp+38h+arg_0], rsi
0x180030052  test    rax, rax
0x180030055  jnz     loc_1800301E8
0x18003005b  mov     rdi, [rbx+20h]
0x18003005f  test    rdi, rdi
0x180030062  jnz     loc_180030201
0x180030068  mov     rdi, [rbx+18h]
0x18003006c  test    rdi, rdi
0x18003006f  jnz     loc_18003021C
0x180030075  mov     rdi, [rbx+28h]
0x180030079  test    rdi, rdi
0x18003007c  jnz     loc_180030237
0x180030082  mov     rcx, [rbx+38h]
0x180030086  test    rcx, rcx
0x180030089  jnz     loc_180030251
0x18003008f  lea     rcx, stru_18015C010; lpCriticalSection
0x180030096  mov     [rsp+38h+arg_8], r15
0x18003009b  call    cs:__imp_EnterCriticalSection
0x1800300a1  lea     rdi, [rbx+228h]
0x1800300a8  cmp     [rdi], r15
0x1800300ab  jz      loc_18003014B
0x1800300b1  lea     rcx, [rsp+38h+arg_8]
0x1800300b6  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x1800300bb  mov     rsi, [rdi]
0x1800300be  test    rsi, rsi
0x1800300c1  jnz     short loc_180030105
0x1800300c3  mov     ecx, 40h ; '@'; Size
0x1800300c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800300cd  mov     rsi, rax
0x1800300d0  test    rax, rax
0x1800300d3  jz      loc_180030171
0x1800300d9  lea     rcx, [rax+18h]; lpCriticalSection
0x1800300dd  mov     dword ptr [rax], 1
0x1800300e3  call    cs:__imp_InitializeCriticalSection
0x1800300e9  mov     [rsi+10h], r15
0x1800300ed  mov     [rsi+8], r15
0x1800300f1  mov     rcx, [rdi]; this
0x1800300f4  test    rcx, rcx
0x1800300f7  jnz     loc_180030266
0x1800300fd  mov     [rdi], rsi
0x180030100  test    rsi, rsi
0x180030103  jz      short loc_180030108
0x180030105  lock inc dword ptr [rsi]
0x180030108  mov     rsi, [rdi]
0x18003010b  mov     rcx, rdi
0x18003010e  call    ?InternalRelease@?$ComPtr@VNotificationWindow@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<NotificationWindow>::InternalRelease(void)
0x180030113  lea     rcx, stru_18015C010; lpCriticalSection
0x18003011a  call    cs:__imp_LeaveCriticalSection
0x180030120  test    rsi, rsi
0x180030123  jnz     short loc_18003015A
0x180030125  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18003012c  mov     r8, rbx; lpMem
0x18003012f  xor     edx, edx; dwFlags
0x180030131  call    cs:__imp_HeapFree
0x180030137  mov     r15, [rsp+38h+var_18]
0x18003013c  mov     rdi, [rsp+38h+arg_10]
0x180030141  mov     rsi, [rsp+38h+arg_0]
0x180030146  jmp     loc_18002FFDD
0x18003014b  lea     rcx, stru_18015C010; lpCriticalSection
0x180030152  call    cs:__imp_LeaveCriticalSection
0x180030158  jmp     short loc_180030125
0x18003015a  test    ebp, ebp
0x18003015c  mov     rcx, rsi; this
0x18003015f  setnz   dl; bool
0x180030162  call    ?Shutdown@NotificationWindow@@QEAAX_N@Z; NotificationWindow::Shutdown(bool)
0x180030167  mov     rcx, rsi; this
0x18003016a  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x18003016f  jmp     short loc_180030125
0x180030171  mov     rsi, r15
0x180030174  jmp     loc_1800300F1
0x180030179  mov     rcx, [rsi+10h]; pv
0x18003017d  mov     rsi, [rsi]
0x180030180  test    rcx, rcx
0x180030183  jz      short loc_18003018B
0x180030185  call    cs:__imp_CoTaskMemFree
0x18003018b  inc     edi
0x18003018d  cmp     edi, r14d
0x180030190  jl      short loc_180030179
0x180030192  mov     rdi, [rbx+30h]
0x180030196  mov     r14, [rsp+38h+arg_18]
0x18003019b  test    rdi, rdi
0x18003019e  jz      short loc_1800301C5
0x1800301a0  mov     rcx, [rdi+20h]; this
0x1800301a4  mov     [rdi+10h], r15d
0x1800301a8  mov     [rdi+18h], r15
0x1800301ac  mov     [rdi+8], r15
0x1800301b0  mov     [rdi], r15
0x1800301b3  call    ?FreeDataChain@CPlex@@QEAAXXZ; CPlex::FreeDataChain(void)
0x1800301b8  mov     rcx, rdi; pv
0x1800301bb  mov     [rdi+20h], r15
0x1800301bf  call    cs:__imp_CoTaskMemFree
0x1800301c5  mov     [rbx+30h], r15
0x1800301c9  jmp     loc_18003005B
0x1800301ce  mov     rcx, rdi
0x1800301d1  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x1800301d6  mov     rcx, rdi; pv
0x1800301d9  call    cs:__imp_CoTaskMemFree
0x1800301df  mov     [rbx+10h], r15
0x1800301e3  jmp     loc_180030049
0x1800301e8  mov     rsi, [rax]
0x1800301eb  mov     edi, r15d
0x1800301ee  mov     [rsp+38h+arg_18], r14
0x1800301f3  mov     r14d, [rax+10h]
0x1800301f7  test    r14d, r14d
0x1800301fa  jle     short loc_180030192
0x1800301fc  jmp     loc_180030179
0x180030201  lea     rcx, [rdi+8]
0x180030205  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x18003020a  mov     rcx, rdi; pv
0x18003020d  call    cs:__imp_CoTaskMemFree
0x180030213  mov     [rbx+20h], r15
0x180030217  jmp     loc_180030068
0x18003021c  lea     rcx, [rdi+8]
0x180030220  call    ?RemoveAll@?$CList@PEAVCClBinding@@PEAV1@@@QEAAXXZ; CList<CClBinding *,CClBinding *>::RemoveAll(void)
0x180030225  mov     rcx, rdi; pv
0x180030228  call    cs:__imp_CoTaskMemFree
0x18003022e  mov     [rbx+18h], r15
0x180030232  jmp     loc_180030075
0x180030237  mov     rcx, rdi; this
0x18003023a  call    ??1CCDLPacketMgr@@QEAA@XZ; CCDLPacketMgr::~CCDLPacketMgr(void)
0x18003023f  mov     rcx, rdi; pv
0x180030242  call    cs:__imp_CoTaskMemFree
0x180030248  mov     [rbx+28h], r15
0x18003024c  jmp     loc_180030082
0x180030251  mov     rax, [rcx]
0x180030254  mov     rax, [rax+10h]
0x180030258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003025d  mov     [rbx+38h], r15
0x180030261  jmp     loc_18003008F
0x180030266  call    ?Release@NotificationWindow@@QEAAKXZ; NotificationWindow::Release(void)
0x18003026b  jmp     loc_1800300FD
```
