# CMDEContentServer::QueueNetEvent(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14008fc18`
- end: `0x14008fdca`
- name: `?QueueNetEvent@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `434`
- prototype: `int(CMDEContentServer *__hidden this, struct IMFNetEvent *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008cfc0`
- `0x14008cfd0`
- `0x14008cfe0`
- `0x14008cff0`
- `0x14008d000`
- `0x14008d010`

## callees

- `0x140024688`
- `0x14003f17c`
- `0x14004df30`
- `0x140057bc4`
- `0x14008fc18`
- `0x14009e010`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x14008fc87`
- `MFPlat!MFCreateAsyncResult` at `0x14008fc87`
- `MFPlat!MFPutWorkItem` at `0x14008fd0c`
- `MFPlat!MFPutWorkItem` at `0x14008fd0c`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::QueueNetEvent(
        IMFAsyncCallback *this,
        IUnknown *a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  HRESULT v8; // eax
  int v9; // ebx
  PVOID *v10; // r10
  CWMCService *lpVtbl; // rcx
  IUnknown *v12; // rbx
  DWORD PrivateMFWorkQueue; // eax
  HRESULT v14; // eax
  struct IMFAsyncCallbackVtbl *v15; // rcx
  IMFAsyncResult *ppAsyncResult[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, a3, a4);
  }
  ppAsyncResult[0] = 0;
  v8 = MFCreateAsyncResult(a2, a3, a4, ppAsyncResult);
  v9 = v8;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
    lpVtbl = (CWMCService *)this[57].lpVtbl;
    if ( lpVtbl )
      (*(void (__fastcall **)(CWMCService *))(*(_QWORD *)lpVtbl + 8LL))(lpVtbl);
    v12 = (IUnknown *)ppAsyncResult[0];
    PrivateMFWorkQueue = CWMCService::GetPrivateMFWorkQueue(lpVtbl);
    v14 = MFPutWorkItem(PrivateMFWorkQueue, this + 14, v12);
    v9 = v14;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v14 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v14);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
    {
      v15 = this[57].lpVtbl;
      if ( v15 )
      {
        (*((void (__fastcall **)(struct IMFAsyncCallbackVtbl *))v15->QueryInterface + 2))(v15);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v10 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 28) & 1) != 0
    && *((unsigned __int8 *)v10 + 25) >= ((v9 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v10[2], 121, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)v9);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)ppAsyncResult);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14008fc18  push    rbx
0x14008fc1a  push    rbp
0x14008fc1b  push    rsi
0x14008fc1c  push    rdi
0x14008fc1d  push    r15
0x14008fc1f  sub     rsp, 40h
0x14008fc23  mov     rbx, r9
0x14008fc26  mov     rdi, r8
0x14008fc29  mov     rsi, rdx
0x14008fc2c  mov     rbp, rcx
0x14008fc2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008fc36  lea     r15, WPP_GLOBAL_Control
0x14008fc3d  cmp     rcx, r15
0x14008fc40  jz      short loc_14008FC70
0x14008fc42  test    byte ptr [rcx+1Ch], 1
0x14008fc46  jz      short loc_14008FC70
0x14008fc48  cmp     byte ptr [rcx+19h], 5
0x14008fc4c  jb      short loc_14008FC70
0x14008fc4e  mov     rcx, [rcx+10h]
0x14008fc52  mov     edx, 76h ; 'v'
0x14008fc57  mov     [rsp+68h+var_40], rbx
0x14008fc5c  mov     r9, rsi
0x14008fc5f  mov     [rsp+68h+var_48], r8
0x14008fc64  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008fc6b  call    WPP_SF_qqq
0x14008fc70  lea     r9, [rsp+68h+ppAsyncResult]; ppAsyncResult
0x14008fc75  mov     [rsp+68h+ppAsyncResult], 0
0x14008fc7e  mov     r8, rbx; punkState
0x14008fc81  mov     rdx, rdi; pCallback
0x14008fc84  mov     rcx, rsi; punkObject
0x14008fc87  call    cs:__imp_MFCreateAsyncResult
0x14008fc8d  mov     ebx, eax
0x14008fc8f  mov     r10, cs:WPP_GLOBAL_Control
0x14008fc96  mov     edi, 0FFFFFFFDh
0x14008fc9b  cmp     r10, r15
0x14008fc9e  jz      short loc_14008FCD9
0x14008fca0  test    byte ptr [r10+1Ch], 2
0x14008fca5  jz      short loc_14008FCD9
0x14008fca7  mov     edx, eax
0x14008fca9  movzx   eax, byte ptr [r10+19h]
0x14008fcae  sar     edx, 1Fh
0x14008fcb1  and     edx, edi
0x14008fcb3  add     edx, 5
0x14008fcb6  cmp     eax, edx
0x14008fcb8  jb      short loc_14008FCD9
0x14008fcba  mov     rcx, [r10+10h]
0x14008fcbe  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008fcc5  mov     edx, 77h ; 'w'
0x14008fcca  mov     r9d, ebx
0x14008fccd  call    WPP_SF_d
0x14008fcd2  mov     r10, cs:WPP_GLOBAL_Control
0x14008fcd9  test    ebx, ebx
0x14008fcdb  js      loc_14008FD7C
0x14008fce1  mov     rcx, [rbp+1C8h]
0x14008fce8  test    rcx, rcx
0x14008fceb  jz      short loc_14008FCF9
0x14008fced  mov     rax, [rcx]
0x14008fcf0  mov     rax, [rax+8]
0x14008fcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fcf9  mov     rbx, [rsp+68h+ppAsyncResult]
0x14008fcfe  call    ?GetPrivateMFWorkQueue@CWMCService@@QEAAKXZ; CWMCService::GetPrivateMFWorkQueue(void)
0x14008fd03  lea     rdx, [rbp+70h]; pCallback
0x14008fd07  mov     r8, rbx; pState
0x14008fd0a  mov     ecx, eax; dwQueue
0x14008fd0c  call    cs:__imp_MFPutWorkItem
0x14008fd12  mov     ebx, eax
0x14008fd14  mov     r10, cs:WPP_GLOBAL_Control
0x14008fd1b  cmp     r10, r15
0x14008fd1e  jz      short loc_14008FD59
0x14008fd20  test    byte ptr [r10+1Ch], 2
0x14008fd25  jz      short loc_14008FD59
0x14008fd27  mov     ecx, eax
0x14008fd29  movzx   eax, byte ptr [r10+19h]
0x14008fd2e  sar     ecx, 1Fh
0x14008fd31  and     ecx, edi
0x14008fd33  add     ecx, 5
0x14008fd36  cmp     eax, ecx
0x14008fd38  jb      short loc_14008FD59
0x14008fd3a  mov     rcx, [r10+10h]
0x14008fd3e  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008fd45  mov     edx, 78h ; 'x'
0x14008fd4a  mov     r9d, ebx
0x14008fd4d  call    WPP_SF_d
0x14008fd52  mov     r10, cs:WPP_GLOBAL_Control
0x14008fd59  test    ebx, ebx
0x14008fd5b  jns     short loc_14008FD7C
0x14008fd5d  mov     rcx, [rbp+1C8h]
0x14008fd64  test    rcx, rcx
0x14008fd67  jz      short loc_14008FD7C
0x14008fd69  mov     rax, [rcx]
0x14008fd6c  mov     rax, [rax+10h]
0x14008fd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008fd75  mov     r10, cs:WPP_GLOBAL_Control
0x14008fd7c  cmp     r10, r15
0x14008fd7f  jz      short loc_14008FDB3
0x14008fd81  test    byte ptr [r10+1Ch], 1
0x14008fd86  jz      short loc_14008FDB3
0x14008fd88  movzx   ecx, byte ptr [r10+19h]
0x14008fd8d  mov     edx, ebx
0x14008fd8f  sar     edx, 1Fh
0x14008fd92  and     edx, edi
0x14008fd94  add     edx, 5
0x14008fd97  cmp     ecx, edx
0x14008fd99  jb      short loc_14008FDB3
0x14008fd9b  mov     rcx, [r10+10h]
0x14008fd9f  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008fda6  mov     edx, 79h ; 'y'
0x14008fdab  mov     r9d, ebx
0x14008fdae  call    WPP_SF_d
0x14008fdb3  lea     rcx, [rsp+68h+ppAsyncResult]
0x14008fdb8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008fdbd  mov     eax, ebx
0x14008fdbf  add     rsp, 40h
0x14008fdc3  pop     r15
0x14008fdc5  pop     rdi
0x14008fdc6  pop     rsi
0x14008fdc7  pop     rbp
0x14008fdc8  pop     rbx
0x14008fdc9  retn
```
