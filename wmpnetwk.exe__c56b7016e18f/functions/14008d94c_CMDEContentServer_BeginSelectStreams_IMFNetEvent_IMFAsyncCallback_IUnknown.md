# CMDEContentServer::BeginSelectStreams(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14008d94c`
- end: `0x14008daf2`
- name: `?BeginSelectStreams@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(CMDEContentServer *__hidden this, struct IMFNetEvent *, IMFAsyncCallback *pCallback, IUnknown *punkState)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x140024688`
- `0x1400307dc`
- `0x140035084`
- `0x1400359f4`
- `0x14003f17c`
- `0x140057bc4`
- `0x14008d94c`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x14008d9e8`
- `MFPlat!MFCreateAsyncResult` at `0x14008d9e8`
- `MFPlat!MFInvokeCallback` at `0x14008da43`
- `MFPlat!MFInvokeCallback` at `0x14008da43`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMDEContentServer::BeginSelectStreams(
        CMDEContentServer *this,
        struct IMFNetEvent *a2,
        IMFAsyncCallback *pCallback,
        IUnknown *punkState)
{
  HRESULT v8; // eax
  int v9; // ebx
  PVOID *v10; // r10
  HRESULT v11; // eax
  __int64 v13[5]; // [rsp+30h] [rbp-28h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+60h] [rbp+8h] BYREF

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    v13,
    ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      185,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      a2,
      pCallback,
      punkState);
  }
  ppAsyncResult = 0;
  CMDEContentServer::UpdateConnectionInfo(this, a2);
  v8 = MFCreateAsyncResult((IUnknown *)a2, pCallback, punkState, &ppAsyncResult);
  v9 = v8;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      186,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
    v11 = MFInvokeCallback(ppAsyncResult);
    v9 = v11;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        187,
        &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
        (unsigned int)v11);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v10 + 28) & 1) != 0
    && *((unsigned __int8 *)v10 + 25) >= ((v9 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v10[2], 188, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)v9);
  }
LABEL_18:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppAsyncResult);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14008d94c  mov     [rsp+arg_8], rbx
0x14008d951  mov     [rsp+arg_10], rbp
0x14008d956  push    rsi
0x14008d957  push    rdi
0x14008d958  push    r15
0x14008d95a  sub     rsp, 40h
0x14008d95e  mov     rsi, r9
0x14008d961  mov     rbp, r8
0x14008d964  mov     rbx, rdx
0x14008d967  mov     rdi, rcx
0x14008d96a  mov     rax, rcx
0x14008d96d  lea     r10, [rcx+8]
0x14008d971  neg     rax
0x14008d974  sbb     rdx, rdx
0x14008d977  and     rdx, r10
0x14008d97a  lea     rcx, [rsp+58h+var_28]
0x14008d97f  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14008d984  nop
0x14008d985  lea     r15, WPP_GLOBAL_Control
0x14008d98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d993  cmp     rcx, r15
0x14008d996  jz      short loc_14008D9C6
0x14008d998  test    byte ptr [rcx+1Ch], 1
0x14008d99c  jz      short loc_14008D9C6
0x14008d99e  cmp     byte ptr [rcx+19h], 5
0x14008d9a2  jb      short loc_14008D9C6
0x14008d9a4  mov     edx, 0B9h
0x14008d9a9  mov     [rsp+58h+var_30], rsi
0x14008d9ae  mov     [rsp+58h+var_38], rbp
0x14008d9b3  mov     r9, rbx
0x14008d9b6  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008d9bd  mov     rcx, [rcx+10h]
0x14008d9c1  call    WPP_SF_qqq
0x14008d9c6  mov     [rsp+58h+ppAsyncResult], 0
0x14008d9cf  mov     rdx, rbx; struct IMFNetEvent *
0x14008d9d2  mov     rcx, rdi; this
0x14008d9d5  call    ?UpdateConnectionInfo@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@@Z; CMDEContentServer::UpdateConnectionInfo(IMFNetEvent *)
0x14008d9da  lea     r9, [rsp+58h+ppAsyncResult]; ppAsyncResult
0x14008d9df  mov     r8, rsi; punkState
0x14008d9e2  mov     rdx, rbp; pCallback
0x14008d9e5  mov     rcx, rbx; punkObject
0x14008d9e8  call    cs:__imp_MFCreateAsyncResult
0x14008d9ee  mov     ebx, eax
0x14008d9f0  mov     edi, 0FFFFFFFDh
0x14008d9f5  mov     r10, cs:WPP_GLOBAL_Control
0x14008d9fc  cmp     r10, r15
0x14008d9ff  jz      short loc_14008DA3A
0x14008da01  test    byte ptr [r10+1Ch], 2
0x14008da06  jz      short loc_14008DA3A
0x14008da08  mov     edx, eax
0x14008da0a  sar     edx, 1Fh
0x14008da0d  and     edx, edi
0x14008da0f  add     edx, 5
0x14008da12  movzx   eax, byte ptr [r10+19h]
0x14008da17  cmp     eax, edx
0x14008da19  jb      short loc_14008DA3A
0x14008da1b  mov     edx, 0BAh
0x14008da20  mov     r9d, ebx
0x14008da23  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008da2a  mov     rcx, [r10+10h]
0x14008da2e  call    WPP_SF_d
0x14008da33  mov     r10, cs:WPP_GLOBAL_Control
0x14008da3a  test    ebx, ebx
0x14008da3c  js      short loc_14008DA90
0x14008da3e  mov     rcx, [rsp+58h+ppAsyncResult]; pAsyncResult
0x14008da43  call    cs:__imp_MFInvokeCallback
0x14008da49  mov     ebx, eax
0x14008da4b  mov     r10, cs:WPP_GLOBAL_Control
0x14008da52  cmp     r10, r15
0x14008da55  jz      short loc_14008DAC8
0x14008da57  test    byte ptr [r10+1Ch], 2
0x14008da5c  jz      short loc_14008DA90
0x14008da5e  mov     ecx, eax
0x14008da60  sar     ecx, 1Fh
0x14008da63  and     ecx, edi
0x14008da65  add     ecx, 5
0x14008da68  movzx   eax, byte ptr [r10+19h]
0x14008da6d  cmp     eax, ecx
0x14008da6f  jb      short loc_14008DA90
0x14008da71  mov     edx, 0BBh
0x14008da76  mov     r9d, ebx
0x14008da79  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008da80  mov     rcx, [r10+10h]
0x14008da84  call    WPP_SF_d
0x14008da89  mov     r10, cs:WPP_GLOBAL_Control
0x14008da90  cmp     r10, r15
0x14008da93  jz      short loc_14008DAC8
0x14008da95  test    byte ptr [r10+1Ch], 1
0x14008da9a  jz      short loc_14008DAC8
0x14008da9c  mov     ecx, ebx
0x14008da9e  sar     ecx, 1Fh
0x14008daa1  and     ecx, edi
0x14008daa3  add     ecx, 5
0x14008daa6  movzx   eax, byte ptr [r10+19h]
0x14008daab  cmp     eax, ecx
0x14008daad  jb      short loc_14008DAC8
0x14008daaf  mov     edx, 0BCh
0x14008dab4  mov     r9d, ebx
0x14008dab7  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008dabe  mov     rcx, [r10+10h]
0x14008dac2  call    WPP_SF_d
0x14008dac7  nop
0x14008dac8  lea     rcx, [rsp+58h+ppAsyncResult]
0x14008dacd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008dad2  nop
0x14008dad3  lea     rcx, [rsp+58h+var_28]
0x14008dad8  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x14008dadd  mov     eax, ebx
0x14008dadf  mov     rbx, [rsp+58h+arg_8]
0x14008dae4  mov     rbp, [rsp+58h+arg_10]
0x14008dae9  add     rsp, 40h
0x14008daed  pop     r15
0x14008daef  pop     rdi
0x14008daf0  pop     rsi
0x14008daf1  retn
```
