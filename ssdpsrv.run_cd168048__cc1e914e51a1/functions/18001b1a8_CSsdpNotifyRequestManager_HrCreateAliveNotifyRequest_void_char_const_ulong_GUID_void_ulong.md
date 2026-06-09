# CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(void * *,char const *,ulong,_GUID,void *,ulong)

- ea: `0x18001b1a8`
- end: `0x18001b2e2`
- name: `?HrCreateAliveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAPEAXPEBDKU_GUID@@PEAXK@Z`
- size: `314`
- prototype: `int(CSsdpNotifyRequestManager *__hidden this, void **, const char *, unsigned int, struct _GUID *__struct_ptr, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800204e8`

## callees

- `0x18000a934`
- `0x18001b1a8`
- `0x18001b2e8`
- `0x180021a50`
- `0x180021e1c`
- `0x1800271fc`
- `0x18002fe8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1c5`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(
        CSsdpNotifyRequestManager *this,
        void **a2,
        const char *a3,
        unsigned int a4,
        struct _GUID *a5,
        void *a6,
        unsigned int a7)
{
  int v11; // ebx
  __int64 v12; // r10
  struct _GUID v14; // [rsp+30h] [rbp-48h] BYREF
  void *v15; // [rsp+80h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *a2 = 0;
  v15 = 0;
  v11 = CUList<CSsdpNotifyRequest>::HrPushFrontDefault(&v15);
  if ( v11 >= 0 )
  {
    v14 = *a5;
    v11 = CSsdpNotifyRequest::HrInitializeAlive((CSsdpNotifyRequest *)((char *)v15 + 8), a3, a4, &v14, a6, a7);
    if ( v11 >= 0 )
    {
      CUList<CSsdpNotifyRequest>::Prepend((char *)this + 88, &v15);
      *a2 = (void *)(*(_QWORD *)v12 + 8LL);
      if ( *(_QWORD *)v12 != -8 )
        v11 = CSsdpRundownSupport::HrAddRundownItem<CSsdpNotifyRequest>(&CSsdpRundownSupport::s_instance);
    }
  }
  if ( v11 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids,
      (unsigned int)v11);
  if ( v15 )
    CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(v15);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b1a8  push    rbx
0x18001b1aa  push    rbp
0x18001b1ab  push    rsi
0x18001b1ac  push    rdi
0x18001b1ad  push    r14
0x18001b1af  push    r15
0x18001b1b1  sub     rsp, 48h
0x18001b1b5  mov     rbp, rcx
0x18001b1b8  mov     r14d, r9d
0x18001b1bb  add     rcx, 30h ; '0'; lpCriticalSection
0x18001b1bf  mov     r15, r8
0x18001b1c2  mov     rsi, rdx
0x18001b1c5  call    cs:__imp_EnterCriticalSection
0x18001b1cc  nop     dword ptr [rax+rax+00h]
0x18001b1d1  lea     rcx, [rsp+78h+arg_0]
0x18001b1d9  mov     qword ptr [rsi], 0
0x18001b1e0  mov     [rsp+78h+arg_0], 0
0x18001b1ec  call    ?HrPushFrontDefault@?$CUList@VCSsdpNotifyRequest@@@@QEAAJXZ; CUList<CSsdpNotifyRequest>::HrPushFrontDefault(void)
0x18001b1f1  mov     ebx, eax
0x18001b1f3  test    eax, eax
0x18001b1f5  js      loc_18001B27B
0x18001b1fb  mov     rax, [rsp+78h+arg_20]
0x18001b203  lea     r9, [rsp+78h+var_48]; struct _GUID
0x18001b208  mov     rcx, [rsp+78h+arg_0]
0x18001b210  mov     r8d, r14d; unsigned int
0x18001b213  add     rcx, 8; this
0x18001b217  mov     rdx, r15; char *
0x18001b21a  movaps  xmm0, xmmword ptr [rax]
0x18001b21d  mov     eax, [rsp+78h+arg_30]
0x18001b224  mov     [rsp+78h+var_50], eax; unsigned int
0x18001b228  mov     rax, [rsp+78h+arg_28]
0x18001b230  mov     [rsp+78h+var_58], rax; void *
0x18001b235  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x18001b23b  call    ?HrInitializeAlive@CSsdpNotifyRequest@@QEAAJPEBDKU_GUID@@PEAXK@Z; CSsdpNotifyRequest::HrInitializeAlive(char const *,ulong,_GUID,void *,ulong)
0x18001b240  mov     ebx, eax
0x18001b242  test    eax, eax
0x18001b244  js      short loc_18001B27B
0x18001b246  lea     r10, [rbp+58h]
0x18001b24a  mov     rcx, r10
0x18001b24d  lea     rdx, [rsp+78h+arg_0]
0x18001b255  call    ?Prepend@?$CUList@VCSsdpNotifyRequest@@@@QEAAXAEAV1@@Z; CUList<CSsdpNotifyRequest>::Prepend(CUList<CSsdpNotifyRequest> &)
0x18001b25a  mov     rcx, [r10]
0x18001b25d  add     rcx, 8
0x18001b261  mov     [rsi], rcx
0x18001b264  mov     rdx, [r10]
0x18001b267  add     rdx, 8
0x18001b26b  jz      short loc_18001B27B
0x18001b26d  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18001b274  call    ??$HrAddRundownItem@VCSsdpNotifyRequest@@@CSsdpRundownSupport@@QEAAJPEAVCSsdpNotifyRequest@@@Z; CSsdpRundownSupport::HrAddRundownItem<CSsdpNotifyRequest>(CSsdpNotifyRequest *)
0x18001b279  mov     ebx, eax
0x18001b27b  test    ebx, ebx
0x18001b27d  jz      short loc_18001B2B0
0x18001b27f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b286  lea     rax, WPP_GLOBAL_Control
0x18001b28d  cmp     rcx, rax
0x18001b290  jz      short loc_18001B2B0
0x18001b292  test    byte ptr [rcx+1Ch], 1
0x18001b296  jz      short loc_18001B2B0
0x18001b298  mov     rcx, [rcx+10h]
0x18001b29c  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18001b2a3  mov     edx, 55h ; 'U'
0x18001b2a8  mov     r9d, ebx
0x18001b2ab  call    WPP_SF_d
0x18001b2b0  mov     rcx, [rsp+78h+arg_0]; void *
0x18001b2b8  test    rcx, rcx
0x18001b2bb  jz      short loc_18001B2C2
0x18001b2bd  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x18001b2c2  lea     rcx, [rbp+30h]; lpCriticalSection
0x18001b2c6  call    cs:__imp_LeaveCriticalSection
0x18001b2cd  nop     dword ptr [rax+rax+00h]
0x18001b2d2  mov     eax, ebx
0x18001b2d4  add     rsp, 48h
0x18001b2d8  pop     r15
0x18001b2da  pop     r14
0x18001b2dc  pop     rdi
0x18001b2dd  pop     rsi
0x18001b2de  pop     rbp
0x18001b2df  pop     rbx
0x18001b2e0  retn
```
