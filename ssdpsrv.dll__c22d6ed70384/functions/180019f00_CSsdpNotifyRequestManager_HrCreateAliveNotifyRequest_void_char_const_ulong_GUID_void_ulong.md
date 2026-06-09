# CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(void * *,char const *,ulong,_GUID,void *,ulong)

- ea: `0x180019f00`
- end: `0x18001a02d`
- name: `?HrCreateAliveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAPEAXPEBDKU_GUID@@PEAXK@Z`
- size: `301`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *this, void **, const char *, unsigned int, struct _GUID *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ef18`

## callees

- `0x1800092f4`
- `0x180019f00`
- `0x18001a034`
- `0x1800200ec`
- `0x1800206fc`
- `0x1800255a8`
- `0x18002dd50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a018`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a018`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f1d`

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
0x180019f00  push    rbx
0x180019f02  push    rbp
0x180019f03  push    rsi
0x180019f04  push    rdi
0x180019f05  push    r14
0x180019f07  push    r15
0x180019f09  sub     rsp, 48h
0x180019f0d  mov     rbp, rcx
0x180019f10  mov     r14d, r9d
0x180019f13  add     rcx, 30h ; '0'; lpCriticalSection
0x180019f17  mov     r15, r8
0x180019f1a  mov     rsi, rdx
0x180019f1d  call    cs:__imp_EnterCriticalSection
0x180019f23  lea     rcx, [rsp+78h+arg_0]
0x180019f2b  mov     qword ptr [rsi], 0
0x180019f32  mov     [rsp+78h+arg_0], 0
0x180019f3e  call    ?HrPushFrontDefault@?$CUList@VCSsdpNotifyRequest@@@@QEAAJXZ; CUList<CSsdpNotifyRequest>::HrPushFrontDefault(void)
0x180019f43  mov     ebx, eax
0x180019f45  test    eax, eax
0x180019f47  js      loc_180019FCD
0x180019f4d  mov     rax, [rsp+78h+arg_20]
0x180019f55  lea     r9, [rsp+78h+var_48]; struct _GUID
0x180019f5a  mov     rcx, [rsp+78h+arg_0]
0x180019f62  mov     r8d, r14d; unsigned int
0x180019f65  add     rcx, 8; this
0x180019f69  mov     rdx, r15; char *
0x180019f6c  movaps  xmm0, xmmword ptr [rax]
0x180019f6f  mov     eax, [rsp+78h+arg_30]
0x180019f76  mov     [rsp+78h+var_50], eax; unsigned int
0x180019f7a  mov     rax, [rsp+78h+arg_28]
0x180019f82  mov     [rsp+78h+var_58], rax; void *
0x180019f87  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x180019f8d  call    ?HrInitializeAlive@CSsdpNotifyRequest@@QEAAJPEBDKU_GUID@@PEAXK@Z; CSsdpNotifyRequest::HrInitializeAlive(char const *,ulong,_GUID,void *,ulong)
0x180019f92  mov     ebx, eax
0x180019f94  test    eax, eax
0x180019f96  js      short loc_180019FCD
0x180019f98  lea     r10, [rbp+58h]
0x180019f9c  mov     rcx, r10
0x180019f9f  lea     rdx, [rsp+78h+arg_0]
0x180019fa7  call    ?Prepend@?$CUList@VCSsdpNotifyRequest@@@@QEAAXAEAV1@@Z; CUList<CSsdpNotifyRequest>::Prepend(CUList<CSsdpNotifyRequest> &)
0x180019fac  mov     rcx, [r10]
0x180019faf  add     rcx, 8
0x180019fb3  mov     [rsi], rcx
0x180019fb6  mov     rdx, [r10]
0x180019fb9  add     rdx, 8
0x180019fbd  jz      short loc_180019FCD
0x180019fbf  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x180019fc6  call    ??$HrAddRundownItem@VCSsdpNotifyRequest@@@CSsdpRundownSupport@@QEAAJPEAVCSsdpNotifyRequest@@@Z; CSsdpRundownSupport::HrAddRundownItem<CSsdpNotifyRequest>(CSsdpNotifyRequest *)
0x180019fcb  mov     ebx, eax
0x180019fcd  test    ebx, ebx
0x180019fcf  jz      short loc_18001A002
0x180019fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fd8  lea     rax, WPP_GLOBAL_Control
0x180019fdf  cmp     rcx, rax
0x180019fe2  jz      short loc_18001A002
0x180019fe4  test    byte ptr [rcx+1Ch], 1
0x180019fe8  jz      short loc_18001A002
0x180019fea  mov     rcx, [rcx+10h]
0x180019fee  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180019ff5  mov     edx, 55h ; 'U'
0x180019ffa  mov     r9d, ebx
0x180019ffd  call    WPP_SF_d
0x18001a002  mov     rcx, [rsp+78h+arg_0]; void *
0x18001a00a  test    rcx, rcx
0x18001a00d  jz      short loc_18001A014
0x18001a00f  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x18001a014  lea     rcx, [rbp+30h]; lpCriticalSection
0x18001a018  call    cs:__imp_LeaveCriticalSection
0x18001a01e  mov     eax, ebx
0x18001a020  add     rsp, 48h
0x18001a024  pop     r15
0x18001a026  pop     r14
0x18001a028  pop     rdi
0x18001a029  pop     rsi
0x18001a02a  pop     rbp
0x18001a02b  pop     rbx
0x18001a02c  retn
```
