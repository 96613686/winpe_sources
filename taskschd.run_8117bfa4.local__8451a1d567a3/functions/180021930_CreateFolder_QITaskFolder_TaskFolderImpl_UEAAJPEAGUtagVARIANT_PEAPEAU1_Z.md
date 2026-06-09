# ?CreateFolder@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGUtagVARIANT@@PEAPEAU1@@Z

- ea: `0x180021930`
- end: `0x180021b71`
- name: `?CreateFolder@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGUtagVARIANT@@PEAPEAU1@@Z`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18000c550`
- `0x180021930`
- `0x180021b80`
- `0x180021f70`
- `0x18002220c`
- `0x18003c664`
- `0x18005260b`
- `0x180052640`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180021a45`
- `OLEAUT32!__imp_VariantClear` at `0x180021aa5`
- `OLEAUT32!__imp_VariantClear` at `0x180021aba`
- `OLEAUT32!__imp_VariantClear` at `0x180021aef`
- `OLEAUT32!__imp_VariantClear` at `0x180021b28`
- `OLEAUT32!__imp_VariantClear` at `0x180021a45`
- `OLEAUT32!__imp_VariantClear` at `0x180021aa5`
- `OLEAUT32!__imp_VariantClear` at `0x180021aba`
- `OLEAUT32!__imp_VariantClear` at `0x180021aef`
- `OLEAUT32!__imp_VariantClear` at `0x180021b28`
- `OLEAUT32!__imp_VariantCopy` at `0x18002196c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002196c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021ad4`
- `OLEAUT32!__imp_VariantChangeType` at `0x180021ad4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall _CreateFolder__QITaskFolder__TaskFolderImpl__UEAAJPEAGUtagVARIANT__PEAPEAU1__Z(
        __int64 a1,
        const unsigned __int16 *a2,
        const struct tagVARIANT *a3,
        _QWORD *a4)
{
  HRESULT v8; // eax
  unsigned __int16 *v9; // rdx
  int v10; // ebx
  int Folder; // ebx
  unsigned int v12; // r9d
  const unsigned __int16 *bstrVal; // r8
  RpcSession *v14; // rcx
  HRESULT v15; // eax
  __int64 v17; // rax
  const unsigned __int16 *v18; // [rsp+20h] [rbp-288h]
  __int64 v19; // [rsp+38h] [rbp-270h] BYREF
  VARIANTARG pvargDest; // [rsp+40h] [rbp-268h] BYREF
  unsigned __int16 v21[264]; // [rsp+60h] [rbp-248h] BYREF

  pvargDest.vt = 0;
  v8 = VariantCopy(&pvargDest, a3);
  if ( v8 < 0 )
  {
    pvargDest.vt = 10;
    pvargDest.lVal = v8;
    ATL::PrivateAtlThrow(v8);
  }
  if ( !IsVariantEmpty(a3) && a3->vt != 8 )
  {
    VariantClear(&pvargDest);
    v15 = VariantChangeType(&pvargDest, a3, 0, 8u);
    Folder = v15;
    if ( v15 < 0 )
      goto LABEL_19;
  }
  v19 = 0;
  memset_0(v21, 0, 0x20Au);
  v10 = tsched::SafePathAppend((tsched *)v21, v9, *(_QWORD *)(a1 + 112), a2, v18);
  if ( v10 >= 0 )
  {
    Folder = TaskFolderImpl::CreateNewObject(a1 + 104, v21, &v19);
    if ( Folder < 0 )
    {
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_19;
    }
    bstrVal = 0;
    if ( pvargDest.vt == 8 )
      bstrVal = pvargDest.bstrVal;
    if ( *(_DWORD *)(a1 + 80) )
    {
      v14 = *(RpcSession **)(a1 + 88);
      if ( v14 )
      {
        Folder = RpcSession::CreateFolder(v14, v21, bstrVal, v12);
        if ( Folder >= 0 )
        {
          if ( a4 )
          {
            v17 = v19;
            v19 = 0;
            *a4 = v17;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
          goto LABEL_19;
        }
      }
      else
      {
        Folder = -2147024846;
      }
    }
    else
    {
      Folder = -2147023645;
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_19:
    VariantClear(&pvargDest);
    return (unsigned int)Folder;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  VariantClear(&pvargDest);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180021930  push    rbx
0x180021932  push    rsi
0x180021933  push    rdi
0x180021934  push    r14
0x180021936  push    r15
0x180021938  sub     rsp, 280h
0x18002193f  mov     rax, cs:__security_cookie
0x180021946  xor     rax, rsp
0x180021949  mov     [rsp+2A8h+var_38], rax
0x180021951  mov     r14, r9
0x180021954  mov     rbx, r8
0x180021957  mov     r15, rdx
0x18002195a  mov     rsi, rcx
0x18002195d  xor     eax, eax
0x18002195f  mov     word ptr [rsp+2A8h+pvargDest], ax
0x180021964  mov     rdx, r8; pvargSrc
0x180021967  lea     rcx, [rsp+2A8h+pvargDest]; pvargDest
0x18002196c  call    cs:__imp_VariantCopy
0x180021973  nop     dword ptr [rax+rax+00h]
0x180021978  test    eax, eax
0x18002197a  js      loc_180021B02
0x180021980  mov     rcx, rbx; struct tagVARIANT *
0x180021983  call    ?IsVariantEmpty@@YA_NAEBUtagVARIANT@@@Z; IsVariantEmpty(tagVARIANT const &)
0x180021988  mov     edi, 8
0x18002198d  test    al, al
0x18002198f  jz      loc_180021A7E
0x180021995  mov     [rsp+2A8h+var_270], 0
0x18002199e  xor     edx, edx; Val
0x1800219a0  mov     r8d, 20Ah; Size
0x1800219a6  lea     rcx, [rsp+2A8h+var_248]; void *
0x1800219ab  call    memset_0
0x1800219b0  mov     r9, r15; unsigned __int16 *
0x1800219b3  mov     r8, [rsi+70h]; unsigned int
0x1800219b7  lea     rcx, [rsp+2A8h+var_248]; this
0x1800219bc  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x1800219c1  mov     ebx, eax
0x1800219c3  mov     [rsp+2A8h+var_278], eax
0x1800219c7  test    eax, eax
0x1800219c9  js      loc_180021B18
0x1800219cf  lea     rcx, [rsi+68h]
0x1800219d3  lea     r8, [rsp+2A8h+var_270]
0x1800219d8  lea     rdx, [rsp+2A8h+var_248]
0x1800219dd  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x1800219e2  mov     ebx, eax
0x1800219e4  mov     [rsp+2A8h+var_278], eax
0x1800219e8  test    eax, eax
0x1800219ea  js      loc_180021A89
0x1800219f0  xor     r8d, r8d
0x1800219f3  cmp     word ptr [rsp+2A8h+pvargDest], di
0x1800219f8  cmovz   r8, qword ptr [rsp+2A8h+pvargDest+8]; unsigned __int16 *
0x1800219fe  cmp     dword ptr [rsi+50h], 0
0x180021a02  jz      loc_180021B3B
0x180021a08  mov     rcx, [rsi+58h]; this
0x180021a0c  test    rcx, rcx
0x180021a0f  jz      short loc_180021A73
0x180021a11  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180021a16  call    ?CreateFolder@RpcSession@@QEBAJPEBG0K@Z; RpcSession::CreateFolder(ushort const *,ushort const *,ulong)
0x180021a1b  mov     ebx, eax
0x180021a1d  mov     [rsp+2A8h+var_278], eax
0x180021a21  test    eax, eax
0x180021a23  jns     loc_180021B45
0x180021a29  mov     rcx, [rsp+2A8h+var_270]
0x180021a2e  test    rcx, rcx
0x180021a31  jz      short loc_180021A40
0x180021a33  mov     rax, [rcx]
0x180021a36  mov     rax, [rax+10h]
0x180021a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a3f  nop
0x180021a40  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180021a45  call    cs:__imp_VariantClear
0x180021a4c  nop     dword ptr [rax+rax+00h]
0x180021a51  mov     eax, ebx
0x180021a53  mov     rcx, [rsp+2A8h+var_38]
0x180021a5b  xor     rcx, rsp; StackCookie
0x180021a5e  call    __security_check_cookie
0x180021a63  add     rsp, 280h
0x180021a6a  pop     r15
0x180021a6c  pop     r14
0x180021a6e  pop     rdi
0x180021a6f  pop     rsi
0x180021a70  pop     rbx
0x180021a71  retn
0x180021a73  mov     ebx, 80070032h
0x180021a78  mov     [rsp+2A8h+var_278], ebx
0x180021a7c  jmp     short loc_180021A29
0x180021a7e  cmp     di, [rbx]
0x180021a81  jz      loc_180021995
0x180021a87  jmp     short loc_180021AB5
0x180021a89  mov     rcx, [rsp+2A8h+var_270]
0x180021a8e  test    rcx, rcx
0x180021a91  jz      short loc_180021AA0
0x180021a93  mov     rax, [rcx]
0x180021a96  mov     rax, [rax+10h]
0x180021a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a9f  nop
0x180021aa0  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180021aa5  call    cs:__imp_VariantClear
0x180021aac  nop     dword ptr [rax+rax+00h]
0x180021ab1  mov     eax, ebx
0x180021ab3  jmp     short loc_180021A53
0x180021ab5  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180021aba  call    cs:__imp_VariantClear
0x180021ac1  nop     dword ptr [rax+rax+00h]
0x180021ac6  mov     r9d, edi; vt
0x180021ac9  xor     r8d, r8d; wFlags
0x180021acc  mov     rdx, rbx; pvarSrc
0x180021acf  lea     rcx, [rsp+2A8h+pvargDest]; pvargDest
0x180021ad4  call    cs:__imp_VariantChangeType
0x180021adb  nop     dword ptr [rax+rax+00h]
0x180021ae0  mov     ebx, eax
0x180021ae2  test    eax, eax
0x180021ae4  jns     loc_180021995
0x180021aea  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180021aef  call    cs:__imp_VariantClear
0x180021af6  nop     dword ptr [rax+rax+00h]
0x180021afb  mov     eax, ebx
0x180021afd  jmp     loc_180021A53
0x180021b02  mov     ecx, 0Ah
0x180021b07  mov     word ptr [rsp+2A8h+pvargDest], cx
0x180021b0c  mov     dword ptr [rsp+2A8h+pvargDest+8], eax
0x180021b10  mov     ecx, eax; int
0x180021b12  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180021b18  lea     rcx, [rsp+2A8h+var_270]
0x180021b1d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021b22  nop
0x180021b23  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180021b28  call    cs:__imp_VariantClear
0x180021b2f  nop     dword ptr [rax+rax+00h]
0x180021b34  mov     eax, ebx
0x180021b36  jmp     loc_180021A53
0x180021b3b  mov     ebx, 800704E3h
0x180021b40  jmp     loc_180021A78
0x180021b45  test    r14, r14
0x180021b48  jz      short loc_180021B5B
0x180021b4a  mov     rax, [rsp+2A8h+var_270]
0x180021b4f  mov     [rsp+2A8h+var_270], 0
0x180021b58  mov     [r14], rax
0x180021b5b  jmp     short loc_180021B61
0x180021b5d  mov     ebx, [rsp+2A8h+var_278]
0x180021b61  lea     rcx, [rsp+2A8h+var_270]
0x180021b66  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180021b6b  jmp     loc_180021AEA
```
