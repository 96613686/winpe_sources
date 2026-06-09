# ?get_Xml@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z

- ea: `0x180020e40`
- end: `0x1800211e3`
- name: `?get_Xml@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z`
- size: `931`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x18001f240`
- `0x180020ad0`
- `0x180020e40`
- `0x180037cf0`
- `0x1800391c0`
- `0x18003c664`
- `0x18003e88c`
- `0x18004c7d8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020fca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020fca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020e9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020e9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021090`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800210d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021090`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800210d2`
- `OLEAUT32!__imp_SysAllocString` at `0x180020f52`
- `OLEAUT32!__imp_SysAllocString` at `0x180020f52`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180021067`
- `OLEAUT32!__imp_SysFreeString` at `0x18002119c`
- `OLEAUT32!__imp_SysFreeString` at `0x180020f3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180020fb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180021067`
- `OLEAUT32!__imp_SysFreeString` at `0x18002119c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800210ff`
- `OLEAUT32!__imp_SysStringLen` at `0x180021177`
- `OLEAUT32!__imp_SysStringLen` at `0x1800210ff`
- `OLEAUT32!__imp_SysStringLen` at `0x180021177`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180020fdf`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180020fdf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020ff1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180020ff1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall _get_Xml__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAPEAG_Z(__int64 a1, BSTR *a2)
{
  int v5; // r15d
  __int64 v6; // rdi
  const unsigned __int16 *v7; // rdx
  RpcSession *v8; // rcx
  OLECHAR *v9; // rbx
  OLECHAR *v10; // rcx
  BSTR v11; // rax
  OLECHAR *v12; // rbx
  HANDLE v13; // rax
  OLECHAR *v14; // rcx
  BSTR v15; // rax
  UINT v16; // eax
  int XmlLegacy; // ebx
  OLECHAR *v18; // rbx
  HANDLE v19; // rax
  OLECHAR *v20; // rbx
  HANDLE ProcessHeap; // rax
  UINT v22; // eax
  OLECHAR *v23; // rax
  const unsigned __int16 *v24; // rbx
  UINT v25; // eax
  BSTR bstrString; // [rsp+30h] [rbp-78h] BYREF
  struct ITask *v27; // [rsp+38h] [rbp-70h] BYREF
  __int64 v28; // [rsp+40h] [rbp-68h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-60h] BYREF
  char v30; // [rsp+50h] [rbp-58h]
  __int64 *v31; // [rsp+58h] [rbp-50h]
  __int64 v32; // [rsp+60h] [rbp-48h]
  __int64 v33; // [rsp+68h] [rbp-40h]
  int v34; // [rsp+70h] [rbp-38h]
  __int64 v35; // [rsp+74h] [rbp-34h]
  unsigned int v36; // [rsp+C0h] [rbp+18h] BYREF
  OLECHAR *psz; // [rsp+C8h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = 0;
  v6 = a1 + 16;
  if ( !a1 )
    v6 = 0;
  if ( v6 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  v28 = v6;
  if ( *(_QWORD *)(a1 + 112) )
    goto LABEL_17;
  psz = 0;
  v36 = 0;
  v7 = (const unsigned __int16 *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v7 = *(const unsigned __int16 **)v7;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    v5 = -2147023645;
    goto LABEL_33;
  }
  v8 = *(RpcSession **)(a1 + 136);
  if ( !v8 )
  {
    if ( v7 && *v7 == 92 )
      ++v7;
    v27 = 0;
    XmlLegacy = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, struct ITask **))(**(_QWORD **)(a1 + 144) + 48LL))(
                  *(_QWORD *)(a1 + 144),
                  v7,
                  &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                  &v27);
    if ( XmlLegacy >= 0 )
    {
      bstrString = 0;
      XmlLegacy = UniSession::GenerateXmlLegacy(v27, (struct ATL::CComBSTR *)&bstrString);
      if ( XmlLegacy >= 0 )
      {
        v20 = psz;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v20);
        psz = 0;
        v22 = SysStringLen(bstrString);
        v23 = (OLECHAR *)MIDL_user_allocate(2LL * (v22 + 1));
        psz = v23;
        if ( !v23 )
        {
          v30 = 0;
          v31 = &qword_18007B2F0;
          v32 = 0;
          v33 = 0;
          v34 = 14;
          v35 = -1;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::OutOfMemoryException *)&pExceptionObject;
        }
        *v23 = 0;
        v24 = bstrString;
        v25 = SysStringLen(bstrString);
        StringCchCopyW(psz, v25 + 1, v24);
        SysFreeString(bstrString);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
        goto LABEL_13;
      }
      SysFreeString(bstrString);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v27);
    v5 = XmlLegacy;
LABEL_33:
    v18 = psz;
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
    psz = 0;
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(&v28);
    return (unsigned int)v5;
  }
  v5 = RpcSession::RetrieveTask(v8, v7, &Src, &v36, (struct RpcString *)&psz);
  if ( v5 < 0 )
    goto LABEL_33;
LABEL_13:
  v9 = psz;
  v10 = *(OLECHAR **)(a1 + 112);
  if ( psz != v10 )
  {
    SysFreeString(v10);
    if ( v9 )
    {
      v11 = SysAllocString(v9);
      *(_QWORD *)(a1 + 112) = v11;
      if ( !v11 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      *(_QWORD *)(a1 + 112) = 0;
    }
  }
  v12 = psz;
  v13 = GetProcessHeap();
  HeapFree(v13, 0, v12);
LABEL_17:
  v14 = *(OLECHAR **)(a1 + 112);
  if ( v14 )
  {
    v16 = SysStringByteLen(v14);
    v15 = SysAllocStringByteLen(*(LPCSTR *)(a1 + 112), v16);
  }
  else
  {
    v15 = 0;
  }
  if ( *(_QWORD *)(a1 + 112) && !v15 )
    ATL::PrivateAtlThrow(-2147024882);
  *a2 = v15;
  SysFreeString(0);
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020e40  mov     [rsp+arg_0], rbx
0x180020e45  push    rsi
0x180020e46  push    rdi
0x180020e47  push    r12
0x180020e49  push    r14
0x180020e4b  push    r15
0x180020e4d  sub     rsp, 80h
0x180020e54  mov     r14, rdx
0x180020e57  mov     rsi, rcx
0x180020e5a  test    rdx, rdx
0x180020e5d  jnz     short loc_180020E7D
0x180020e5f  mov     eax, 80004003h
0x180020e64  mov     rbx, [rsp+0A8h+arg_0]
0x180020e6c  add     rsp, 80h
0x180020e73  pop     r15
0x180020e75  pop     r14
0x180020e77  pop     r12
0x180020e79  pop     rdi
0x180020e7a  pop     rsi
0x180020e7b  retn
0x180020e7d  xor     r12d, r12d
0x180020e80  mov     r15d, r12d
0x180020e83  mov     [rsp+0A8h+arg_8], r12d
0x180020e8b  lea     rdi, [rcx+10h]
0x180020e8f  test    rsi, rsi
0x180020e92  cmovz   rdi, r12
0x180020e96  test    rdi, rdi
0x180020e99  jz      short loc_180020EAB
0x180020e9b  lea     rcx, [rdi+8]; lpCriticalSection
0x180020e9f  call    cs:__imp_EnterCriticalSection
0x180020ea6  nop     dword ptr [rax+rax+00h]
0x180020eab  mov     [rsp+0A8h+var_68], rdi
0x180020eb0  cmp     qword ptr [rsi+70h], 0
0x180020eb5  jnz     loc_180020F93
0x180020ebb  mov     [rsp+0A8h+psz], r12
0x180020ec3  mov     [rsp+0A8h+arg_10], r12d
0x180020ecb  lea     rdx, [rsi+50h]
0x180020ecf  cmp     qword ptr [rdx+18h], 8
0x180020ed4  jb      short loc_180020ED9
0x180020ed6  mov     rdx, [rdx]; unsigned __int16 *
0x180020ed9  cmp     dword ptr [rsi+80h], 0
0x180020ee0  jz      loc_180020FFF
0x180020ee6  mov     rcx, [rsi+88h]; this
0x180020eed  test    rcx, rcx
0x180020ef0  jz      loc_18002100F
0x180020ef6  lea     rax, [rsp+0A8h+psz]
0x180020efe  mov     [rsp+0A8h+var_88], rax; struct RpcString *
0x180020f03  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x180020f0b  lea     r8, Src; unsigned __int16 *
0x180020f12  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x180020f17  mov     r15d, eax
0x180020f1a  mov     [rsp+0A8h+arg_8], eax
0x180020f21  test    eax, eax
0x180020f23  js      loc_180021088
0x180020f29  mov     rbx, [rsp+0A8h+psz]
0x180020f31  mov     rcx, [rsi+70h]; bstrString
0x180020f35  cmp     rbx, rcx
0x180020f38  jz      short loc_180020F6B
0x180020f3a  call    cs:__imp_SysFreeString
0x180020f41  nop     dword ptr [rax+rax+00h]
0x180020f46  test    rbx, rbx
0x180020f49  jz      loc_1800211C2
0x180020f4f  mov     rcx, rbx; psz
0x180020f52  call    cs:__imp_SysAllocString
0x180020f59  nop     dword ptr [rax+rax+00h]
0x180020f5e  mov     [rsi+70h], rax
0x180020f62  test    rax, rax
0x180020f65  jz      loc_1800211B8
0x180020f6b  mov     rbx, [rsp+0A8h+psz]
0x180020f73  call    cs:__imp_GetProcessHeap
0x180020f7a  nop     dword ptr [rax+rax+00h]
0x180020f7f  mov     r8, rbx; lpMem
0x180020f82  xor     edx, edx; dwFlags
0x180020f84  mov     rcx, rax; hHeap
0x180020f87  call    cs:__imp_HeapFree
0x180020f8e  nop     dword ptr [rax+rax+00h]
0x180020f93  mov     rcx, [rsi+70h]; bstr
0x180020f97  test    rcx, rcx
0x180020f9a  jnz     short loc_180020FDF
0x180020f9c  mov     rax, r12
0x180020f9f  cmp     qword ptr [rsi+70h], 0
0x180020fa4  jz      short loc_180020FAF
0x180020fa6  test    rax, rax
0x180020fa9  jz      loc_1800211CB
0x180020faf  mov     [r14], rax
0x180020fb2  xor     ecx, ecx; bstrString
0x180020fb4  call    cs:__imp_SysFreeString
0x180020fbb  nop     dword ptr [rax+rax+00h]
0x180020fc0  nop
0x180020fc1  test    rdi, rdi
0x180020fc4  jz      short loc_180020FD7
0x180020fc6  lea     rcx, [rdi+8]; lpCriticalSection
0x180020fca  call    cs:__imp_LeaveCriticalSection
0x180020fd1  nop     dword ptr [rax+rax+00h]
0x180020fd6  nop
0x180020fd7  mov     eax, r15d
0x180020fda  jmp     loc_180020E64
0x180020fdf  call    cs:__imp_SysStringByteLen
0x180020fe6  nop     dword ptr [rax+rax+00h]
0x180020feb  mov     edx, eax; len
0x180020fed  mov     rcx, [rsi+70h]; psz
0x180020ff1  call    cs:__imp_SysAllocStringByteLen
0x180020ff8  nop     dword ptr [rax+rax+00h]
0x180020ffd  jmp     short loc_180020F9F
0x180020fff  mov     r15d, 800704E3h
0x180021005  mov     [rsp+0A8h+arg_8], r15d
0x18002100d  jmp     short loc_180021088
0x18002100f  test    rdx, rdx
0x180021012  jz      short loc_18002101E
0x180021014  cmp     word ptr [rdx], 5Ch ; '\'
0x180021018  jnz     short loc_18002101E
0x18002101a  add     rdx, 2
0x18002101e  mov     [rsp+0A8h+var_70], r12
0x180021023  mov     rcx, [rsi+90h]
0x18002102a  mov     rax, [rcx]
0x18002102d  lea     r9, [rsp+0A8h+var_70]
0x180021032  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x180021039  mov     rax, [rax+30h]
0x18002103d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021042  mov     ebx, eax
0x180021044  test    eax, eax
0x180021046  js      short loc_180021074
0x180021048  mov     [rsp+0A8h+bstrString], r12
0x18002104d  lea     rdx, [rsp+0A8h+bstrString]; struct ATL::CComBSTR *
0x180021052  mov     rcx, [rsp+0A8h+var_70]; struct ITask *
0x180021057  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x18002105c  mov     ebx, eax
0x18002105e  test    eax, eax
0x180021060  jns     short loc_1800210CA
0x180021062  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x180021067  call    cs:__imp_SysFreeString
0x18002106e  nop     dword ptr [rax+rax+00h]
0x180021073  nop
0x180021074  lea     rcx, [rsp+0A8h+var_70]
0x180021079  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002107e  mov     [rsp+0A8h+arg_8], ebx
0x180021085  mov     r15d, ebx
0x180021088  mov     rbx, [rsp+0A8h+psz]
0x180021090  call    cs:__imp_GetProcessHeap
0x180021097  nop     dword ptr [rax+rax+00h]
0x18002109c  mov     r8, rbx; lpMem
0x18002109f  xor     edx, edx; dwFlags
0x1800210a1  mov     rcx, rax; hHeap
0x1800210a4  call    cs:__imp_HeapFree
0x1800210ab  nop     dword ptr [rax+rax+00h]
0x1800210b0  mov     [rsp+0A8h+psz], r12
0x1800210b8  lea     rcx, [rsp+0A8h+var_68]
0x1800210bd  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x1800210c2  mov     eax, r15d
0x1800210c5  jmp     loc_180020E64
0x1800210ca  mov     rbx, [rsp+0A8h+psz]
0x1800210d2  call    cs:__imp_GetProcessHeap
0x1800210d9  nop     dword ptr [rax+rax+00h]
0x1800210de  mov     r8, rbx; lpMem
0x1800210e1  xor     edx, edx; dwFlags
0x1800210e3  mov     rcx, rax; hHeap
0x1800210e6  call    cs:__imp_HeapFree
0x1800210ed  nop     dword ptr [rax+rax+00h]
0x1800210f2  mov     [rsp+0A8h+psz], r12
0x1800210fa  mov     rcx, [rsp+0A8h+bstrString]; pbstr
0x1800210ff  call    cs:__imp_SysStringLen
0x180021106  nop     dword ptr [rax+rax+00h]
0x18002110b  lea     ecx, [rax+1]
0x18002110e  add     rcx, rcx; size
0x180021111  call    MIDL_user_allocate
0x180021116  mov     [rsp+0A8h+psz], rax
0x18002111e  test    rax, rax
0x180021121  jnz     short loc_18002116B
0x180021123  mov     [rsp+0A8h+var_58], al
0x180021127  lea     rax, qword_18007B2F0
0x18002112e  mov     [rsp+0A8h+var_50], rax
0x180021133  mov     [rsp+0A8h+var_48], r12
0x180021138  mov     [rsp+0A8h+var_40], r12
0x18002113d  mov     [rsp+0A8h+var_38], 0Eh
0x180021145  mov     [rsp+0A8h+var_34], 0FFFFFFFFFFFFFFFFh
0x18002114e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180021155  mov     [rsp+0A8h+pExceptionObject], rax
0x18002115a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180021161  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180021166  call    _CxxThrowException_0
0x18002116b  mov     [rax], r12w
0x18002116f  mov     rbx, [rsp+0A8h+bstrString]
0x180021174  mov     rcx, rbx; pbstr
0x180021177  call    cs:__imp_SysStringLen
0x18002117e  nop     dword ptr [rax+rax+00h]
0x180021183  lea     edx, [rax+1]; unsigned __int64
0x180021186  mov     r8, rbx; unsigned __int16 *
0x180021189  mov     rcx, [rsp+0A8h+psz]; unsigned __int16 *
0x180021191  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021196  nop
0x180021197  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18002119c  call    cs:__imp_SysFreeString
0x1800211a3  nop     dword ptr [rax+rax+00h]
0x1800211a8  nop
0x1800211a9  lea     rcx, [rsp+0A8h+var_70]
0x1800211ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800211b3  jmp     loc_180020F29
0x1800211b8  mov     ecx, 8007000Eh; int
0x1800211bd  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800211c2  mov     [rsi+70h], r12
0x1800211c6  jmp     loc_180020F6B
0x1800211cb  mov     ecx, 8007000Eh; int
0x1800211d0  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800211d6  mov     r15d, [rsp+0A8h+arg_8]
0x1800211de  jmp     loc_180020FD7
```
