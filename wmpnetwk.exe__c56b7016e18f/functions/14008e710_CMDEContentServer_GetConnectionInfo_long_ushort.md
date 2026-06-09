# CMDEContentServer::GetConnectionInfo(long,ushort * *)

- ea: `0x14008e710`
- end: `0x14008e89e`
- name: `?GetConnectionInfo@CMDEContentServer@@UEAAJJPEAPEAG@Z`
- size: `398`
- prototype: `int(CMDEContentServer *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x140024688`
- `0x140035084`
- `0x1400359f4`
- `0x14003f17c`
- `0x140047798`
- `0x14008e514`
- `0x14008e710`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14008e7fa`
- `OLEAUT32!__imp_SysAllocString` at `0x14008e819`
- `OLEAUT32!__imp_SysAllocString` at `0x14008e7fa`
- `OLEAUT32!__imp_SysAllocString` at `0x14008e819`
- `ole32!CoTaskMemFree` at `0x14008e808`
- `ole32!CoTaskMemFree` at `0x14008e808`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::GetConnectionInfo(CMDEContentServer *this, int a2, unsigned __int16 **a3)
{
  CMDEContentServer *v6; // rcx
  PVOID *v7; // r10
  int ConnectionID; // ebx
  struct IMFNetVRoot *v9; // rdx
  struct IMFNetVRoot *v10; // rdx
  unsigned __int16 *v11; // rax
  OLECHAR *v12; // rcx
  struct IMDEExternalSessionState *v14; // [rsp+40h] [rbp+8h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp+18h] BYREF
  __int64 v16; // [rsp+58h] [rbp+20h] BYREF

  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(
    &v16,
    ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 280, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v14 = 0;
  if ( !a3 )
  {
    ConnectionID = -2147467261;
    goto LABEL_17;
  }
  *a3 = 0;
  v9 = (struct IMFNetVRoot *)*((_QWORD *)this + 18);
  if ( !v9 || (int)CMDEContentServer::FindConnectionID(v6, v9, a2, &v14) < 0 )
  {
    v10 = (struct IMFNetVRoot *)*((_QWORD *)this + 17);
    if ( v10 )
    {
      ConnectionID = CMDEContentServer::FindConnectionID(v6, v10, a2, &v14);
      if ( ConnectionID >= 0 )
        goto LABEL_10;
    }
    else
    {
      ConnectionID = -2147467259;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
LABEL_10:
  psz = 0;
  ConnectionID = (*(__int64 (__fastcall **)(struct IMDEExternalSessionState *, OLECHAR **))(*(_QWORD *)v14 + 48LL))(
                   v14,
                   &psz);
  if ( ConnectionID < 0 )
  {
    ConnectionID = 0;
    *a3 = SysAllocString(&Password);
  }
  else
  {
    v11 = SysAllocString(psz);
    v12 = psz;
    *a3 = v11;
    CoTaskMemFree(v12);
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( !*a3 )
    ConnectionID = -2147024882;
LABEL_17:
  if ( v7 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 28) & 1) != 0
    && *((unsigned __int8 *)v7 + 25) >= ((ConnectionID >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v7[2], 281, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, (unsigned int)ConnectionID);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v16);
  return (unsigned int)ConnectionID;
}

```

## disassembly

```asm
0x14008e710  mov     [rsp+arg_8], rbx
0x14008e715  push    rsi
0x14008e716  push    rdi
0x14008e717  push    r14
0x14008e719  sub     rsp, 20h
0x14008e71d  mov     rax, rcx
0x14008e720  lea     r9, [rcx+8]
0x14008e724  mov     esi, edx
0x14008e726  neg     rax
0x14008e729  mov     rbx, rcx
0x14008e72c  mov     rdi, r8
0x14008e72f  sbb     rdx, rdx
0x14008e732  lea     rcx, [rsp+38h+arg_18]
0x14008e737  and     rdx, r9
0x14008e73a  call    ??0?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@PEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@1@@Z; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::CComObjectLockT<ATL::CComMultiThreadModel>(ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *)
0x14008e73f  mov     r10, cs:WPP_GLOBAL_Control
0x14008e746  lea     r14, WPP_GLOBAL_Control
0x14008e74d  cmp     r10, r14
0x14008e750  jz      short loc_14008E775
0x14008e752  test    byte ptr [r10+1Ch], 1
0x14008e757  jz      short loc_14008E775
0x14008e759  mov     rcx, [r10+10h]
0x14008e75d  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008e764  mov     edx, 118h
0x14008e769  call    WPP_SF_
0x14008e76e  mov     r10, cs:WPP_GLOBAL_Control
0x14008e775  mov     [rsp+38h+arg_0], 0
0x14008e77e  test    rdi, rdi
0x14008e781  jnz     short loc_14008E78D
0x14008e783  mov     ebx, 80004003h
0x14008e788  jmp     loc_14008E842
0x14008e78d  mov     qword ptr [rdi], 0
0x14008e794  mov     rdx, [rbx+90h]; struct IMFNetVRoot *
0x14008e79b  test    rdx, rdx
0x14008e79e  jz      short loc_14008E7B1
0x14008e7a0  lea     r9, [rsp+38h+arg_0]; struct IMDEExternalSessionState **
0x14008e7a5  mov     r8d, esi; int
0x14008e7a8  call    ?FindConnectionID@CMDEContentServer@@AEAAJPEAUIMFNetVRoot@@JPEAPEAUIMDEExternalSessionState@@@Z; CMDEContentServer::FindConnectionID(IMFNetVRoot *,long,IMDEExternalSessionState * *)
0x14008e7ad  test    eax, eax
0x14008e7af  jns     short loc_14008E7D0
0x14008e7b1  mov     rdx, [rbx+88h]; struct IMFNetVRoot *
0x14008e7b8  test    rdx, rdx
0x14008e7bb  jz      short loc_14008E836
0x14008e7bd  lea     r9, [rsp+38h+arg_0]; struct IMDEExternalSessionState **
0x14008e7c2  mov     r8d, esi; int
0x14008e7c5  call    ?FindConnectionID@CMDEContentServer@@AEAAJPEAUIMFNetVRoot@@JPEAPEAUIMDEExternalSessionState@@@Z; CMDEContentServer::FindConnectionID(IMFNetVRoot *,long,IMDEExternalSessionState * *)
0x14008e7ca  mov     ebx, eax
0x14008e7cc  test    eax, eax
0x14008e7ce  js      short loc_14008E83B
0x14008e7d0  mov     rcx, [rsp+38h+arg_0]
0x14008e7d5  lea     rdx, [rsp+38h+psz]
0x14008e7da  mov     [rsp+38h+psz], 0
0x14008e7e3  mov     rax, [rcx]
0x14008e7e6  mov     rax, [rax+30h]
0x14008e7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008e7ef  mov     ebx, eax
0x14008e7f1  test    eax, eax
0x14008e7f3  js      short loc_14008E810
0x14008e7f5  mov     rcx, [rsp+38h+psz]; psz
0x14008e7fa  call    cs:__imp_SysAllocString
0x14008e800  mov     rcx, [rsp+38h+psz]; pv
0x14008e805  mov     [rdi], rax
0x14008e808  call    cs:__imp_CoTaskMemFree
0x14008e80e  jmp     short loc_14008E822
0x14008e810  xor     ebx, ebx
0x14008e812  lea     rcx, Password; psz
0x14008e819  call    cs:__imp_SysAllocString
0x14008e81f  mov     [rdi], rax
0x14008e822  cmp     qword ptr [rdi], 0
0x14008e826  mov     r10, cs:WPP_GLOBAL_Control
0x14008e82d  jnz     short loc_14008E842
0x14008e82f  mov     ebx, 8007000Eh
0x14008e834  jmp     short loc_14008E842
0x14008e836  mov     ebx, 80004005h
0x14008e83b  mov     r10, cs:WPP_GLOBAL_Control
0x14008e842  cmp     r10, r14
0x14008e845  jz      short loc_14008E87A
0x14008e847  test    byte ptr [r10+1Ch], 1
0x14008e84c  jz      short loc_14008E87A
0x14008e84e  movzx   eax, byte ptr [r10+19h]
0x14008e853  mov     ecx, ebx
0x14008e855  sar     ecx, 1Fh
0x14008e858  and     ecx, 0FFFFFFFDh
0x14008e85b  add     ecx, 5
0x14008e85e  cmp     eax, ecx
0x14008e860  jb      short loc_14008E87A
0x14008e862  mov     rcx, [r10+10h]
0x14008e866  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x14008e86d  mov     edx, 119h
0x14008e872  mov     r9d, ebx
0x14008e875  call    WPP_SF_d
0x14008e87a  lea     rcx, [rsp+38h+arg_0]
0x14008e87f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008e884  lea     rcx, [rsp+38h+arg_18]
0x14008e889  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x14008e88e  mov     eax, ebx
0x14008e890  mov     rbx, [rsp+38h+arg_8]
0x14008e895  add     rsp, 20h
0x14008e899  pop     r14
0x14008e89b  pop     rdi
0x14008e89c  pop     rsi
0x14008e89d  retn
```
