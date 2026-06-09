# SNI_NodeIOCompletionQueues::Init(void)

- ea: `0x100455bf0`
- end: `0x100455ea3`
- name: `?Init@SNI_NodeIOCompletionQueues@@QEAAKXZ`
- size: `691`
- prototype: `unsigned int __fastcall(SNI_NodeIOCompletionQueues *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100424110`

## callees

- `0x10041da80`
- `0x10042b7f0`
- `0x100455bf0`
- `0x100486bf0`
- `0x100487cd6`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100455e1d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100455e1d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100455cf6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100455cf6`
- `sqldk!SystemThread_TlsIndex` at `0x100455c1d`
- `sqldk!SystemThread_TlsIndex` at `0x100455c75`
- `sqldk!SystemThread_TlsIndex` at `0x100455db8`
- `sqldk!SystemThread_TlsOffset` at `0x100455c26`
- `sqldk!SystemThread_TlsOffset` at `0x100455c7e`
- `sqldk!SystemThread_TlsOffset` at `0x100455dc1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455c41`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455c99`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455ddc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455c41`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455c99`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100455ddc`

## string_xrefs

- `0x100455ce5`: `sql\common\dk\sni\src\SNI_IOCompletionQueue.cpp`
- `0x100455e0d`: `sql\common\dk\sni\src\SNI_IOCompletionQueue.cpp`
- `0x100455e69`: `sql\common\dk\sni\src\SNI_IOCompletionQueue.cpp`
- `0x100455e62`: `SNI_NodeIOCompletionQueue::Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SNI_NodeIOCompletionQueues::Init(SNI_NodeIOCompletionQueues *this)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // ecx
  unsigned __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  struct IMemObj *v8; // r10
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  unsigned __int64 *v12; // rax
  void *v13; // rbx
  unsigned int v15; // edi
  __int64 v16; // rsi
  unsigned int v17; // ebx
  __int64 v18; // rbp
  __int64 v19; // rax
  _DWORD *v20; // rax
  void (*v21)(void *); // [rsp+20h] [rbp-58h]

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  v4 = *(_DWORD *)(*(_QWORD *)(v3 + 992) + 200LL);
  *((_DWORD *)this + 3) = v4;
  v5 = v4;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  v8 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v7 + 992) + 56LL) + 8LL);
  v9 = 152 * v5;
  if ( !is_mul_ok(v5, 0x98u) )
    v9 = -1;
  v10 = __CFADD__(v9, 8);
  v11 = v9 + 8;
  if ( v10 )
    v11 = -1;
  v12 = (unsigned __int64 *)operator new[](v11, v8, 1, "sql\\common\\dk\\sni\\src\\SNI_IOCompletionQueue.cpp", 798, 6u);
  if ( v12 )
  {
    *v12 = v5;
    v13 = v12 + 1;
    `eh vector constructor iterator'(
      v12 + 1,
      0x98u,
      v5,
      (void (*)(void *))SNI_NodeIOCompletionQueue::SNI_NodeIOCompletionQueue,
      (void (*)(void *))SNI_NodeIOCompletionQueue::~SNI_NodeIOCompletionQueue);
  }
  else
  {
    v13 = 0;
  }
  *(_QWORD *)this = v13;
  memset_0(v13, 0, 152LL * *((unsigned int *)this + 3));
  if ( !*(_QWORD *)this )
    return 14;
  v15 = 0;
  if ( !*((_DWORD *)this + 3) )
    return 0;
  while ( 1 )
  {
    v16 = *(_QWORD *)this + 152LL * v15;
    v17 = CCriticalSectionSOS::Initialize((struct CCriticalSectionSOS **)(v16 + 144));
    if ( !v17 )
    {
      *(_DWORD *)v16 = v15;
      v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v19 = *(_QWORD *)(v18 + 256);
      if ( !v19 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v19 = *(_QWORD *)(v18 + 256);
      }
      v20 = operator new(
              0x10u,
              *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v19 + 992) + 56LL) + 8LL),
              1,
              "sql\\common\\dk\\sni\\src\\SNI_IOCompletionQueue.cpp",
              711,
              6u);
      if ( v20 )
      {
        *(_QWORD *)v20 = &SNI_IOCompletionQueue::`vftable';
        v20[2] = v15;
        *(_QWORD *)v20 = &SNI_IOCPIOQueue::`vftable';
      }
      *(_QWORD *)(v16 + 8) = v20;
      if ( !*(_QWORD *)(v16 + 8) )
        v17 = 14;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v21) = v17;
      SNIXE_SNI_TRACE_ON(
        "sql\\common\\dk\\sni\\src\\SNI_IOCompletionQueue.cpp",
        "SNI_NodeIOCompletionQueue::Init",
        719,
        L"RET|SNI%d{WINERR}\n",
        v21);
    }
    if ( v17 )
      break;
    if ( ++v15 >= *((_DWORD *)this + 3) )
      return 0;
  }
  return v17;
}

```

## disassembly

```asm
0x100455bf0  push    rbp
0x100455bf2  push    rsi
0x100455bf3  push    rdi
0x100455bf4  push    r12
0x100455bf6  push    r13
0x100455bf8  push    r14
0x100455bfa  push    r15
0x100455bfc  sub     rsp, 40h
0x100455c00  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x100455c09  mov     [rsp+78h+arg_18], rbx
0x100455c11  mov     r14, rcx
0x100455c14  mov     r8, gs:58h
0x100455c1d  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100455c24  mov     edx, [rax]
0x100455c26  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100455c2d  mov     ebx, [rax]
0x100455c2f  add     rbx, [r8+rdx*8]
0x100455c33  mov     rax, [rbx+100h]
0x100455c3a  test    rax, rax
0x100455c3d  jnz     short loc_100455C4E
0x100455c3f  xor     ecx, ecx
0x100455c41  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100455c47  mov     rax, [rbx+100h]
0x100455c4e  mov     rax, [rax+3E0h]
0x100455c55  mov     ecx, [rax+0C8h]
0x100455c5b  mov     [r14+0Ch], ecx
0x100455c5f  mov     edi, ecx
0x100455c61  mov     [rsp+78h+arg_0], 31Eh
0x100455c6c  mov     rdx, gs:58h
0x100455c75  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100455c7c  mov     ecx, [rax]
0x100455c7e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100455c85  mov     ebx, [rax]
0x100455c87  add     rbx, [rdx+rcx*8]
0x100455c8b  mov     rax, [rbx+100h]
0x100455c92  test    rax, rax
0x100455c95  jnz     short loc_100455CA6
0x100455c97  xor     ecx, ecx
0x100455c99  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100455c9f  mov     rax, [rbx+100h]
0x100455ca6  mov     rax, [rax+3E0h]
0x100455cad  mov     rcx, [rax+38h]
0x100455cb1  mov     r10, [rcx+8]
0x100455cb5  mov     [rsp+78h+arg_8], r10
0x100455cbd  mov     eax, 98h
0x100455cc2  mul     rdi
0x100455cc5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100455ccc  cmovo   rax, rcx
0x100455cd0  add     rax, 8
0x100455cd4  cmovb   rax, rcx
0x100455cd8  mov     [rsp+78h+var_50], 6
0x100455cdd  mov     dword ptr [rsp+78h+var_58], 31Eh
0x100455ce5  lea     r9, aSqlCommonDkSni_8; "sql\\common\\dk\\sni\\src\\SNI_IOComple"...
0x100455cec  lea     r8d, [rcx+2]
0x100455cf0  mov     rdx, r10
0x100455cf3  mov     rcx, rax
0x100455cf6  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100455cfc  mov     [rsp+78h+arg_10], rax
0x100455d04  test    rax, rax
0x100455d07  jz      short loc_100455D35
0x100455d09  mov     [rax], rdi
0x100455d0c  lea     rbx, [rax+8]
0x100455d10  lea     rax, ??1SNI_NodeIOCompletionQueue@@QEAA@XZ; SNI_NodeIOCompletionQueue::~SNI_NodeIOCompletionQueue(void)
0x100455d17  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x100455d1c  lea     r9, ??0SNI_NodeIOCompletionQueue@@QEAA@XZ; void (*)(void *)
0x100455d23  mov     r8, rdi; unsigned __int64
0x100455d26  mov     edx, 98h; unsigned __int64
0x100455d2b  mov     rcx, rbx; void *
0x100455d2e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x100455d33  jmp     short loc_100455D37
0x100455d35  xor     ebx, ebx
0x100455d37  mov     [r14], rbx
0x100455d3a  mov     eax, [r14+0Ch]
0x100455d3e  imul    r8, rax, 98h; Size
0x100455d45  xor     edx, edx; Val
0x100455d47  mov     rcx, rbx; void *
0x100455d4a  call    memset_0
0x100455d4f  cmp     qword ptr [r14], 0
0x100455d53  jnz     short loc_100455D5F
0x100455d55  mov     eax, 0Eh
0x100455d5a  jmp     loc_100455E87
0x100455d5f  xor     edi, edi
0x100455d61  cmp     [r14+0Ch], edi
0x100455d65  jbe     loc_100455E85
0x100455d6b  lea     r15d, [rdi+0Eh]
0x100455d6f  lea     r12, ??_7SNI_IOCompletionQueue@@6B@; const SNI_IOCompletionQueue::`vftable'
0x100455d76  lea     r13, ??_7SNI_IOCPIOQueue@@6B@; const SNI_IOCPIOQueue::`vftable'
0x100455d7d  nop     dword ptr [rax]
0x100455d80  mov     eax, edi
0x100455d82  imul    rsi, rax, 98h
0x100455d89  add     rsi, [r14]
0x100455d8c  lea     rcx, [rsi+90h]; struct CCriticalSectionSOS **
0x100455d93  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x100455d98  mov     ebx, eax
0x100455d9a  test    eax, eax
0x100455d9c  jnz     loc_100455E48
0x100455da2  mov     [rsi], edi
0x100455da4  mov     [rsp+78h+arg_0], 2C7h
0x100455daf  mov     r8, gs:58h
0x100455db8  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100455dbf  mov     edx, [rcx]
0x100455dc1  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100455dc8  mov     ebp, [rcx]
0x100455dca  add     rbp, [r8+rdx*8]
0x100455dce  mov     rax, [rbp+100h]
0x100455dd5  test    rax, rax
0x100455dd8  jnz     short loc_100455DE9
0x100455dda  xor     ecx, ecx
0x100455ddc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100455de2  mov     rax, [rbp+100h]
0x100455de9  mov     rax, [rax+3E0h]
0x100455df0  mov     rcx, [rax+38h]
0x100455df4  mov     rdx, [rcx+8]
0x100455df8  mov     [rsp+78h+arg_8], rdx
0x100455e00  mov     [rsp+78h+var_50], 6
0x100455e05  mov     dword ptr [rsp+78h+var_58], 2C7h
0x100455e0d  lea     r9, aSqlCommonDkSni_8; "sql\\common\\dk\\sni\\src\\SNI_IOComple"...
0x100455e14  mov     ecx, 10h
0x100455e19  lea     r8d, [rcx-0Fh]
0x100455e1d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100455e23  mov     [rsp+78h+arg_10], rax
0x100455e2b  test    rax, rax
0x100455e2e  jz      short loc_100455E39
0x100455e30  mov     [rax], r12
0x100455e33  mov     [rax+8], edi
0x100455e36  mov     [rax], r13
0x100455e39  mov     [rsi+8], rax
0x100455e3d  mov     rax, [rsi+8]
0x100455e41  test    rax, rax
0x100455e44  cmovz   ebx, r15d
0x100455e48  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100455e4f  jz      short loc_100455E75
0x100455e51  mov     dword ptr [rsp+78h+var_58], ebx
0x100455e55  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100455e5c  mov     r8d, 2CFh; int
0x100455e62  lea     rdx, aSniNodeiocompl_0; "SNI_NodeIOCompletionQueue::Init"
0x100455e69  lea     rcx, aSqlCommonDkSni_8; "sql\\common\\dk\\sni\\src\\SNI_IOComple"...
0x100455e70  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100455e75  test    ebx, ebx
0x100455e77  jnz     short loc_100455E9F
0x100455e79  inc     edi
0x100455e7b  cmp     edi, [r14+0Ch]
0x100455e7f  jb      loc_100455D80
0x100455e85  xor     eax, eax
0x100455e87  mov     rbx, [rsp+78h+arg_18]
0x100455e8f  add     rsp, 40h
0x100455e93  pop     r15
0x100455e95  pop     r14
0x100455e97  pop     r13
0x100455e99  pop     r12
0x100455e9b  pop     rdi
0x100455e9c  pop     rsi
0x100455e9d  pop     rbp
0x100455e9e  retn
0x100455e9f  mov     eax, ebx
0x100455ea1  jmp     short loc_100455E87
```
