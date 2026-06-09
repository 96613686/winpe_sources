# CMDEContentServer::BeginAuthorize(IMFNetEvent *,IMFAsyncCallback *,IUnknown *)

- ea: `0x14008c648`
- end: `0x14008c93d`
- name: `?BeginAuthorize@CMDEContentServer@@AEAAJPEAUIMFNetEvent@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(CMDEContentServer *this, IUnknown *, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008f4ac`

## callees

- `0x140024688`
- `0x140035084`
- `0x1400359f4`
- `0x14003f17c`
- `0x14005480c`
- `0x140057bc4`
- `0x14008c648`
- `0x140090118`
- `0x140090174`
- `0x14009e010`

## import_xrefs

- `MFPlat!MFCreateAsyncResult` at `0x14008c702`
- `MFPlat!MFCreateAsyncResult` at `0x14008c702`
- `MFPlat!MFInvokeCallback` at `0x14008c852`
- `MFPlat!MFInvokeCallback` at `0x14008c852`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::BeginAuthorize(
        CMDEContentServer *this,
        IUnknown *a2,
        struct IMFAsyncCallback *a3,
        struct IUnknown *a4)
{
  int v7; // ecx
  __int64 v8; // rcx
  HRESULT v9; // ebx
  PVOID *v10; // r10
  __int64 v11; // rdx
  HRESULT v12; // eax
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    &v15,
    ((unsigned __int64)this + 8) & -(__int64)(this != 0));
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v7,
      (unsigned int)MDE_Callback_Begin_Authorize_Start,
      (_DWORD)a2,
      (_DWORD)a3,
      (char)a4,
      0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, a3, a4);
  }
  ppAsyncResult = 0;
  v16 = 0;
  v9 = MFCreateAsyncResult(a2, a3, a4, &ppAsyncResult);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v9 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v9);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl[13].QueryInterface)(
           a2,
           &IID_IPropertyStore,
           &v16);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = ((v9 >> 31) & 0xFFFFFFFD) + 5;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v8 )
      {
        WPP_SF_dq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          141,
          &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          (unsigned int)v9,
          v16);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    {
      McTemplateU0p_EventWriteTransfer(v8, v11, v16);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 >= 0 )
    {
      v9 = ((__int64 (__fastcall *)(IMFAsyncResult *, _QWORD))ppAsyncResult->lpVtbl->SetStatus)(
             ppAsyncResult,
             (unsigned int)v9);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LODWORD(v8) = ((v9 >> 31) & 0xFFFFFFFD) + 5;
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v8 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            142,
            &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
            (unsigned int)v9);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
      if ( v9 >= 0 )
      {
        v12 = MFInvokeCallback(ppAsyncResult);
        v9 = v12;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_32;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LODWORD(v8) = ((v12 >> 31) & 0xFFFFFFFD) + 5;
          if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)v8 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              143,
              &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              (unsigned int)v12);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
      }
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
  {
    LODWORD(v8) = ((v9 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)v10 + 25) >= (unsigned int)v8 )
      WPP_SF_d(v10[2], 144, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)v9);
  }
LABEL_32:
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
    McTemplateU0pppq_EventWriteTransfer(
      v8,
      (unsigned int)MDE_Callback_Begin_Authorize_Stop,
      (_DWORD)a2,
      (_DWORD)a3,
      (char)a4,
      v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppAsyncResult);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v15);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14008c648  mov     [rsp-28h+arg_8], rbx
0x14008c64d  mov     [rsp-28h+arg_10], rsi
0x14008c652  push    rbp
0x14008c653  push    rdi
0x14008c654  push    r13
0x14008c656  push    r14
0x14008c658  push    r15
0x14008c65a  mov     rbp, rsp
0x14008c65d  sub     rsp, 40h
0x14008c661  mov     rsi, r9
0x14008c664  mov     r14, r8
0x14008c667  mov     rdi, rdx
0x14008c66a  lea     rax, [rcx+8]
0x14008c66e  neg     rcx
0x14008c671  sbb     rdx, rdx
0x14008c674  and     rdx, rax
0x14008c677  lea     rcx, [rbp+var_8]
0x14008c67b  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14008c680  nop
0x14008c681  xor     r15d, r15d
0x14008c684  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008c68b  jz      short loc_14008C6A9
0x14008c68d  mov     dword ptr [rsp+40h+var_18], r15d
0x14008c692  mov     [rsp+40h+var_20], rsi
0x14008c697  mov     r9, r14
0x14008c69a  mov     r8, rdi
0x14008c69d  lea     rdx, MDE_Callback_Begin_Authorize_Start
0x14008c6a4  call    McTemplateU0pppq_EventWriteTransfer
0x14008c6a9  lea     rax, WPP_GLOBAL_Control
0x14008c6b0  lea     r13, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008c6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c6be  cmp     rcx, rax
0x14008c6c1  jz      short loc_14008C6ED
0x14008c6c3  test    byte ptr [rcx+1Ch], 1
0x14008c6c7  jz      short loc_14008C6ED
0x14008c6c9  cmp     byte ptr [rcx+19h], 5
0x14008c6cd  jb      short loc_14008C6ED
0x14008c6cf  mov     edx, 8Bh
0x14008c6d4  mov     [rsp+40h+var_18], rsi
0x14008c6d9  mov     [rsp+40h+var_20], r14
0x14008c6de  mov     r9, rdi
0x14008c6e1  mov     r8, r13
0x14008c6e4  mov     rcx, [rcx+10h]
0x14008c6e8  call    WPP_SF_qqq
0x14008c6ed  mov     [rbp+ppAsyncResult], r15
0x14008c6f1  mov     [rbp+arg_0], r15
0x14008c6f5  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x14008c6f9  mov     r8, rsi; punkState
0x14008c6fc  mov     rdx, r14; pCallback
0x14008c6ff  mov     rcx, rdi; punkObject
0x14008c702  call    cs:__imp_MFCreateAsyncResult
0x14008c708  mov     ebx, eax
0x14008c70a  mov     r10, cs:WPP_GLOBAL_Control
0x14008c711  lea     rax, WPP_GLOBAL_Control
0x14008c718  cmp     r10, rax
0x14008c71b  jz      short loc_14008C753
0x14008c71d  test    byte ptr [r10+1Ch], 2
0x14008c722  jz      short loc_14008C753
0x14008c724  mov     edx, ebx
0x14008c726  sar     edx, 1Fh
0x14008c729  and     edx, 0FFFFFFFDh
0x14008c72c  add     edx, 5
0x14008c72f  movzx   eax, byte ptr [r10+19h]
0x14008c734  cmp     eax, edx
0x14008c736  jb      short loc_14008C753
0x14008c738  mov     edx, 8Ch
0x14008c73d  mov     r9d, ebx
0x14008c740  mov     r8, r13
0x14008c743  mov     rcx, [r10+10h]
0x14008c747  call    WPP_SF_d
0x14008c74c  mov     r10, cs:WPP_GLOBAL_Control
0x14008c753  test    ebx, ebx
0x14008c755  js      loc_14008C8A5
0x14008c75b  mov     rax, [rdi]
0x14008c75e  lea     r8, [rbp+arg_0]
0x14008c762  lea     rdx, IID_IPropertyStore
0x14008c769  mov     rcx, rdi
0x14008c76c  mov     rax, [rax+138h]
0x14008c773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c778  mov     ebx, eax
0x14008c77a  mov     r10, cs:WPP_GLOBAL_Control
0x14008c781  lea     rax, WPP_GLOBAL_Control
0x14008c788  cmp     r10, rax
0x14008c78b  jz      short loc_14008C7CC
0x14008c78d  test    byte ptr [r10+1Ch], 2
0x14008c792  jz      short loc_14008C7CC
0x14008c794  mov     ecx, ebx
0x14008c796  sar     ecx, 1Fh
0x14008c799  and     ecx, 0FFFFFFFDh
0x14008c79c  add     ecx, 5
0x14008c79f  movzx   eax, byte ptr [r10+19h]
0x14008c7a4  cmp     eax, ecx
0x14008c7a6  jb      short loc_14008C7CC
0x14008c7a8  mov     edx, 8Dh
0x14008c7ad  mov     rax, [rbp+arg_0]
0x14008c7b1  mov     [rsp+40h+var_20], rax
0x14008c7b6  mov     r9d, ebx
0x14008c7b9  mov     r8, r13
0x14008c7bc  mov     rcx, [r10+10h]
0x14008c7c0  call    WPP_SF_dq
0x14008c7c5  mov     r10, cs:WPP_GLOBAL_Control
0x14008c7cc  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008c7d3  jz      short loc_14008C7E5
0x14008c7d5  mov     r8, [rbp+arg_0]
0x14008c7d9  call    McTemplateU0p_EventWriteTransfer
0x14008c7de  mov     r10, cs:WPP_GLOBAL_Control
0x14008c7e5  test    ebx, ebx
0x14008c7e7  js      loc_14008C8A5
0x14008c7ed  mov     rcx, [rbp+ppAsyncResult]
0x14008c7f1  mov     rax, [rcx]
0x14008c7f4  mov     edx, ebx
0x14008c7f6  mov     rax, [rax+28h]
0x14008c7fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008c7ff  mov     ebx, eax
0x14008c801  mov     r10, cs:WPP_GLOBAL_Control
0x14008c808  lea     rax, WPP_GLOBAL_Control
0x14008c80f  cmp     r10, rax
0x14008c812  jz      short loc_14008C84A
0x14008c814  test    byte ptr [r10+1Ch], 2
0x14008c819  jz      short loc_14008C84A
0x14008c81b  mov     ecx, ebx
0x14008c81d  sar     ecx, 1Fh
0x14008c820  and     ecx, 0FFFFFFFDh
0x14008c823  add     ecx, 5
0x14008c826  movzx   eax, byte ptr [r10+19h]
0x14008c82b  cmp     eax, ecx
0x14008c82d  jb      short loc_14008C84A
0x14008c82f  mov     edx, 8Eh
0x14008c834  mov     r9d, ebx
0x14008c837  mov     r8, r13
0x14008c83a  mov     rcx, [r10+10h]
0x14008c83e  call    WPP_SF_d
0x14008c843  mov     r10, cs:WPP_GLOBAL_Control
0x14008c84a  test    ebx, ebx
0x14008c84c  js      short loc_14008C8A5
0x14008c84e  mov     rcx, [rbp+ppAsyncResult]; pAsyncResult
0x14008c852  call    cs:__imp_MFInvokeCallback
0x14008c858  mov     ebx, eax
0x14008c85a  mov     r10, cs:WPP_GLOBAL_Control
0x14008c861  lea     r15, WPP_GLOBAL_Control
0x14008c868  cmp     r10, r15
0x14008c86b  jz      short loc_14008C8E0
0x14008c86d  test    byte ptr [r10+1Ch], 2
0x14008c872  jz      short loc_14008C8AC
0x14008c874  mov     ecx, eax
0x14008c876  sar     ecx, 1Fh
0x14008c879  and     ecx, 0FFFFFFFDh
0x14008c87c  add     ecx, 5
0x14008c87f  movzx   eax, byte ptr [r10+19h]
0x14008c884  cmp     eax, ecx
0x14008c886  jb      short loc_14008C8AC
0x14008c888  mov     edx, 8Fh
0x14008c88d  mov     r9d, ebx
0x14008c890  mov     r8, r13
0x14008c893  mov     rcx, [r10+10h]
0x14008c897  call    WPP_SF_d
0x14008c89c  mov     r10, cs:WPP_GLOBAL_Control
0x14008c8a3  jmp     short loc_14008C8AC
0x14008c8a5  lea     r15, WPP_GLOBAL_Control
0x14008c8ac  cmp     r10, r15
0x14008c8af  jz      short loc_14008C8E0
0x14008c8b1  test    byte ptr [r10+1Ch], 1
0x14008c8b6  jz      short loc_14008C8E0
0x14008c8b8  mov     ecx, ebx
0x14008c8ba  sar     ecx, 1Fh
0x14008c8bd  and     ecx, 0FFFFFFFDh
0x14008c8c0  add     ecx, 5
0x14008c8c3  movzx   eax, byte ptr [r10+19h]
0x14008c8c8  cmp     eax, ecx
0x14008c8ca  jb      short loc_14008C8E0
0x14008c8cc  mov     edx, 90h
0x14008c8d1  mov     r9d, ebx
0x14008c8d4  mov     r8, r13
0x14008c8d7  mov     rcx, [r10+10h]
0x14008c8db  call    WPP_SF_d
0x14008c8e0  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x14008c8e7  jz      short loc_14008C905
0x14008c8e9  mov     dword ptr [rsp+40h+var_18], ebx
0x14008c8ed  mov     [rsp+40h+var_20], rsi
0x14008c8f2  mov     r9, r14
0x14008c8f5  mov     r8, rdi
0x14008c8f8  lea     rdx, MDE_Callback_Begin_Authorize_Stop
0x14008c8ff  call    McTemplateU0pppq_EventWriteTransfer
0x14008c904  nop
0x14008c905  lea     rcx, [rbp+arg_0]
0x14008c909  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008c90e  nop
0x14008c90f  lea     rcx, [rbp+ppAsyncResult]
0x14008c913  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008c918  nop
0x14008c919  lea     rcx, [rbp+var_8]
0x14008c91d  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x14008c922  mov     eax, ebx
0x14008c924  lea     r11, [rsp+40h+var_s0]
0x14008c929  mov     rbx, [r11+38h]
0x14008c92d  mov     rsi, [r11+40h]
0x14008c931  mov     rsp, r11
0x14008c934  pop     r15
0x14008c936  pop     r14
0x14008c938  pop     r13
0x14008c93a  pop     rdi
0x14008c93b  pop     rbp
0x14008c93c  retn
```
