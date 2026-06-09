# ?CreateFolder@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGUtagVARIANT@@PEAPEAU1@@Z

- ea: `0x180020640`
- end: `0x180020853`
- name: `?CreateFolder@?QITaskFolder@@TaskFolderImpl@@UEAAJPEAGUtagVARIANT@@PEAPEAU1@@Z`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18000bff0`
- `0x18000dd10`
- `0x180020640`
- `0x180020860`
- `0x180020934`
- `0x180039524`
- `0x18004e90f`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18002074f`
- `OLEAUT32!__imp_VariantClear` at `0x1800207a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800207b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800207e0`
- `OLEAUT32!__imp_VariantClear` at `0x180020813`
- `OLEAUT32!__imp_VariantClear` at `0x18002074f`
- `OLEAUT32!__imp_VariantClear` at `0x1800207a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800207b7`
- `OLEAUT32!__imp_VariantClear` at `0x1800207e0`
- `OLEAUT32!__imp_VariantClear` at `0x180020813`
- `OLEAUT32!__imp_VariantCopy` at `0x18002067c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002067c`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800207cb`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800207cb`

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
0x180020640  push    rbx
0x180020642  push    rsi
0x180020643  push    rdi
0x180020644  push    r14
0x180020646  push    r15
0x180020648  sub     rsp, 280h
0x18002064f  mov     rax, cs:__security_cookie
0x180020656  xor     rax, rsp
0x180020659  mov     [rsp+2A8h+var_38], rax
0x180020661  mov     r14, r9
0x180020664  mov     rbx, r8
0x180020667  mov     r15, rdx
0x18002066a  mov     rsi, rcx
0x18002066d  xor     eax, eax
0x18002066f  mov     word ptr [rsp+2A8h+pvargDest], ax
0x180020674  mov     rdx, r8; pvargSrc
0x180020677  lea     rcx, [rsp+2A8h+pvargDest]; pvargDest
0x18002067c  call    cs:__imp_VariantCopy
0x180020682  test    eax, eax
0x180020684  js      loc_1800207ED
0x18002068a  mov     rcx, rbx; struct tagVARIANT *
0x18002068d  call    ?IsVariantEmpty@@YA_NAEBUtagVARIANT@@@Z; IsVariantEmpty(tagVARIANT const &)
0x180020692  mov     edi, 8
0x180020697  test    al, al
0x180020699  jz      loc_180020781
0x18002069f  mov     [rsp+2A8h+var_270], 0
0x1800206a8  xor     edx, edx; Val
0x1800206aa  mov     r8d, 20Ah; Size
0x1800206b0  lea     rcx, [rsp+2A8h+var_248]; void *
0x1800206b5  call    memset_0
0x1800206ba  mov     r9, r15; unsigned __int16 *
0x1800206bd  mov     r8, [rsi+70h]; unsigned int
0x1800206c1  lea     rcx, [rsp+2A8h+var_248]; this
0x1800206c6  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x1800206cb  mov     ebx, eax
0x1800206cd  mov     [rsp+2A8h+var_278], eax
0x1800206d1  test    eax, eax
0x1800206d3  js      loc_180020803
0x1800206d9  lea     rcx, [rsi+68h]
0x1800206dd  lea     r8, [rsp+2A8h+var_270]
0x1800206e2  lea     rdx, [rsp+2A8h+var_248]
0x1800206e7  call    ?CreateNewObject@TaskFolderImpl@@SAJAEBV?$AutoRef@VTaskServiceImpl@@@wmi@@PEBGPEAPEAUITaskFolder@@@Z; TaskFolderImpl::CreateNewObject(wmi::AutoRef<TaskServiceImpl> const &,ushort const *,ITaskFolder * *)
0x1800206ec  mov     ebx, eax
0x1800206ee  mov     [rsp+2A8h+var_278], eax
0x1800206f2  test    eax, eax
0x1800206f4  js      loc_18002078C
0x1800206fa  xor     r8d, r8d
0x1800206fd  cmp     word ptr [rsp+2A8h+pvargDest], di
0x180020702  cmovz   r8, qword ptr [rsp+2A8h+pvargDest+8]; unsigned __int16 *
0x180020708  cmp     dword ptr [rsi+50h], 0
0x18002070c  jz      loc_180020820
0x180020712  mov     rcx, [rsi+58h]; this
0x180020716  test    rcx, rcx
0x180020719  jz      short loc_180020776
0x18002071b  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180020720  call    ?CreateFolder@RpcSession@@QEBAJPEBG0K@Z; RpcSession::CreateFolder(ushort const *,ushort const *,ulong)
0x180020725  mov     ebx, eax
0x180020727  mov     [rsp+2A8h+var_278], eax
0x18002072b  test    eax, eax
0x18002072d  jns     loc_18002082A
0x180020733  mov     rcx, [rsp+2A8h+var_270]
0x180020738  test    rcx, rcx
0x18002073b  jz      short loc_18002074A
0x18002073d  mov     rax, [rcx]
0x180020740  mov     rax, [rax+10h]
0x180020744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020749  nop
0x18002074a  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x18002074f  call    cs:__imp_VariantClear
0x180020755  mov     eax, ebx
0x180020757  mov     rcx, [rsp+2A8h+var_38]
0x18002075f  xor     rcx, rsp; StackCookie
0x180020762  call    __security_check_cookie
0x180020767  add     rsp, 280h
0x18002076e  pop     r15
0x180020770  pop     r14
0x180020772  pop     rdi
0x180020773  pop     rsi
0x180020774  pop     rbx
0x180020775  retn
0x180020776  mov     ebx, 80070032h
0x18002077b  mov     [rsp+2A8h+var_278], ebx
0x18002077f  jmp     short loc_180020733
0x180020781  cmp     di, [rbx]
0x180020784  jz      loc_18002069F
0x18002078a  jmp     short loc_1800207B2
0x18002078c  mov     rcx, [rsp+2A8h+var_270]
0x180020791  test    rcx, rcx
0x180020794  jz      short loc_1800207A3
0x180020796  mov     rax, [rcx]
0x180020799  mov     rax, [rax+10h]
0x18002079d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207a2  nop
0x1800207a3  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x1800207a8  call    cs:__imp_VariantClear
0x1800207ae  mov     eax, ebx
0x1800207b0  jmp     short loc_180020757
0x1800207b2  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x1800207b7  call    cs:__imp_VariantClear
0x1800207bd  mov     r9d, edi; vt
0x1800207c0  xor     r8d, r8d; wFlags
0x1800207c3  mov     rdx, rbx; pvarSrc
0x1800207c6  lea     rcx, [rsp+2A8h+pvargDest]; pvargDest
0x1800207cb  call    cs:__imp_VariantChangeType
0x1800207d1  mov     ebx, eax
0x1800207d3  test    eax, eax
0x1800207d5  jns     loc_18002069F
0x1800207db  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x1800207e0  call    cs:__imp_VariantClear
0x1800207e6  mov     eax, ebx
0x1800207e8  jmp     loc_180020757
0x1800207ed  mov     ecx, 0Ah
0x1800207f2  mov     word ptr [rsp+2A8h+pvargDest], cx
0x1800207f7  mov     dword ptr [rsp+2A8h+pvargDest+8], eax
0x1800207fb  mov     ecx, eax; int
0x1800207fd  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180020803  lea     rcx, [rsp+2A8h+var_270]
0x180020808  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002080d  nop
0x18002080e  lea     rcx, [rsp+2A8h+pvargDest]; pvarg
0x180020813  call    cs:__imp_VariantClear
0x180020819  mov     eax, ebx
0x18002081b  jmp     loc_180020757
0x180020820  mov     ebx, 800704E3h
0x180020825  jmp     loc_18002077B
0x18002082a  test    r14, r14
0x18002082d  jz      short loc_180020840
0x18002082f  mov     rax, [rsp+2A8h+var_270]
0x180020834  mov     [rsp+2A8h+var_270], 0
0x18002083d  mov     [r14], rax
0x180020840  jmp     short loc_180020846
0x180020842  mov     ebx, [rsp+2A8h+var_278]
0x180020846  lea     rcx, [rsp+2A8h+var_270]
0x18002084b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180020850  jmp     short loc_1800207DB
```
