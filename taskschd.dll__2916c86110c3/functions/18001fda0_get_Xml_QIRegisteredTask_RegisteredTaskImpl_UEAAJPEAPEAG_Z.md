# ?get_Xml@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z

- ea: `0x18001fda0`
- end: `0x1800200dc`
- name: `?get_Xml@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z`
- size: `828`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18001e240`
- `0x18001fa40`
- `0x18001fda0`
- `0x1800351ec`
- `0x180036290`
- `0x180039524`
- `0x18003b51c`
- `0x180048cb0`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ff05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ff05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fece`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ffc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fece`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ffc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fff7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ffb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ffe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fec0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ffb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ffe9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fea5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001fea5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fe93`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff90`
- `OLEAUT32!__imp_SysFreeString` at `0x18002009b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fe93`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ff90`
- `OLEAUT32!__imp_SysFreeString` at `0x18002009b`
- `OLEAUT32!__imp_SysStringLen` at `0x18002000a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002007c`
- `OLEAUT32!__imp_SysStringLen` at `0x18002000a`
- `OLEAUT32!__imp_SysStringLen` at `0x18002007c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001ff14`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001ff14`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ff20`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001ff20`

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
          v31 = &qword_180077320;
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
0x18001fda0  mov     [rsp+arg_0], rbx
0x18001fda5  push    rsi
0x18001fda6  push    rdi
0x18001fda7  push    r12
0x18001fda9  push    r14
0x18001fdab  push    r15
0x18001fdad  sub     rsp, 80h
0x18001fdb4  mov     r14, rdx
0x18001fdb7  mov     rsi, rcx
0x18001fdba  test    rdx, rdx
0x18001fdbd  jnz     short loc_18001FDDC
0x18001fdbf  mov     eax, 80004003h
0x18001fdc4  mov     rbx, [rsp+0A8h+arg_0]
0x18001fdcc  add     rsp, 80h
0x18001fdd3  pop     r15
0x18001fdd5  pop     r14
0x18001fdd7  pop     r12
0x18001fdd9  pop     rdi
0x18001fdda  pop     rsi
0x18001fddb  retn
0x18001fddc  xor     r12d, r12d
0x18001fddf  mov     r15d, r12d
0x18001fde2  mov     [rsp+0A8h+arg_8], r12d
0x18001fdea  lea     rdi, [rcx+10h]
0x18001fdee  test    rsi, rsi
0x18001fdf1  cmovz   rdi, r12
0x18001fdf5  test    rdi, rdi
0x18001fdf8  jz      short loc_18001FE04
0x18001fdfa  lea     rcx, [rdi+8]; lpCriticalSection
0x18001fdfe  call    cs:__imp_EnterCriticalSection
0x18001fe04  mov     [rsp+0A8h+var_68], rdi
0x18001fe09  cmp     qword ptr [rsi+70h], 0
0x18001fe0e  jnz     loc_18001FED4
0x18001fe14  mov     [rsp+0A8h+psz], r12
0x18001fe1c  mov     [rsp+0A8h+arg_10], r12d
0x18001fe24  lea     rdx, [rsi+50h]
0x18001fe28  cmp     qword ptr [rdx+18h], 8
0x18001fe2d  jb      short loc_18001FE32
0x18001fe2f  mov     rdx, [rdx]; unsigned __int16 *
0x18001fe32  cmp     dword ptr [rsi+80h], 0
0x18001fe39  jz      loc_18001FF28
0x18001fe3f  mov     rcx, [rsi+88h]; this
0x18001fe46  test    rcx, rcx
0x18001fe49  jz      loc_18001FF38
0x18001fe4f  lea     rax, [rsp+0A8h+psz]
0x18001fe57  mov     [rsp+0A8h+var_88], rax; struct RpcString *
0x18001fe5c  lea     r9, [rsp+0A8h+arg_10]; unsigned int *
0x18001fe64  lea     r8, Src; unsigned __int16 *
0x18001fe6b  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x18001fe70  mov     r15d, eax
0x18001fe73  mov     [rsp+0A8h+arg_8], eax
0x18001fe7a  test    eax, eax
0x18001fe7c  js      loc_18001FFAB
0x18001fe82  mov     rbx, [rsp+0A8h+psz]
0x18001fe8a  mov     rcx, [rsi+70h]; bstrString
0x18001fe8e  cmp     rbx, rcx
0x18001fe91  jz      short loc_18001FEB8
0x18001fe93  call    cs:__imp_SysFreeString
0x18001fe99  test    rbx, rbx
0x18001fe9c  jz      loc_1800200BB
0x18001fea2  mov     rcx, rbx; psz
0x18001fea5  call    cs:__imp_SysAllocString
0x18001feab  mov     [rsi+70h], rax
0x18001feaf  test    rax, rax
0x18001feb2  jz      loc_1800200B1
0x18001feb8  mov     rbx, [rsp+0A8h+psz]
0x18001fec0  call    cs:__imp_GetProcessHeap
0x18001fec6  mov     r8, rbx; lpMem
0x18001fec9  xor     edx, edx; dwFlags
0x18001fecb  mov     rcx, rax; hHeap
0x18001fece  call    cs:__imp_HeapFree
0x18001fed4  mov     rcx, [rsi+70h]; bstr
0x18001fed8  test    rcx, rcx
0x18001fedb  jnz     short loc_18001FF14
0x18001fedd  mov     rax, r12
0x18001fee0  cmp     qword ptr [rsi+70h], 0
0x18001fee5  jz      short loc_18001FEF0
0x18001fee7  test    rax, rax
0x18001feea  jz      loc_1800200C4
0x18001fef0  mov     [r14], rax
0x18001fef3  xor     ecx, ecx; bstrString
0x18001fef5  call    cs:__imp_SysFreeString
0x18001fefb  nop
0x18001fefc  test    rdi, rdi
0x18001feff  jz      short loc_18001FF0C
0x18001ff01  lea     rcx, [rdi+8]; lpCriticalSection
0x18001ff05  call    cs:__imp_LeaveCriticalSection
0x18001ff0b  nop
0x18001ff0c  mov     eax, r15d
0x18001ff0f  jmp     loc_18001FDC4
0x18001ff14  call    cs:__imp_SysStringByteLen
0x18001ff1a  mov     edx, eax; len
0x18001ff1c  mov     rcx, [rsi+70h]; psz
0x18001ff20  call    cs:__imp_SysAllocStringByteLen
0x18001ff26  jmp     short loc_18001FEE0
0x18001ff28  mov     r15d, 800704E3h
0x18001ff2e  mov     [rsp+0A8h+arg_8], r15d
0x18001ff36  jmp     short loc_18001FFAB
0x18001ff38  test    rdx, rdx
0x18001ff3b  jz      short loc_18001FF47
0x18001ff3d  cmp     word ptr [rdx], 5Ch ; '\'
0x18001ff41  jnz     short loc_18001FF47
0x18001ff43  add     rdx, 2
0x18001ff47  mov     [rsp+0A8h+var_70], r12
0x18001ff4c  mov     rcx, [rsi+90h]
0x18001ff53  mov     rax, [rcx]
0x18001ff56  lea     r9, [rsp+0A8h+var_70]
0x18001ff5b  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18001ff62  mov     rax, [rax+30h]
0x18001ff66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff6b  mov     ebx, eax
0x18001ff6d  test    eax, eax
0x18001ff6f  js      short loc_18001FF97
0x18001ff71  mov     [rsp+0A8h+bstrString], r12
0x18001ff76  lea     rdx, [rsp+0A8h+bstrString]; struct ATL::CComBSTR *
0x18001ff7b  mov     rcx, [rsp+0A8h+var_70]; struct ITask *
0x18001ff80  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x18001ff85  mov     ebx, eax
0x18001ff87  test    eax, eax
0x18001ff89  jns     short loc_18001FFE1
0x18001ff8b  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18001ff90  call    cs:__imp_SysFreeString
0x18001ff96  nop
0x18001ff97  lea     rcx, [rsp+0A8h+var_70]
0x18001ff9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ffa1  mov     [rsp+0A8h+arg_8], ebx
0x18001ffa8  mov     r15d, ebx
0x18001ffab  mov     rbx, [rsp+0A8h+psz]
0x18001ffb3  call    cs:__imp_GetProcessHeap
0x18001ffb9  mov     r8, rbx; lpMem
0x18001ffbc  xor     edx, edx; dwFlags
0x18001ffbe  mov     rcx, rax; hHeap
0x18001ffc1  call    cs:__imp_HeapFree
0x18001ffc7  mov     [rsp+0A8h+psz], r12
0x18001ffcf  lea     rcx, [rsp+0A8h+var_68]
0x18001ffd4  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x18001ffd9  mov     eax, r15d
0x18001ffdc  jmp     loc_18001FDC4
0x18001ffe1  mov     rbx, [rsp+0A8h+psz]
0x18001ffe9  call    cs:__imp_GetProcessHeap
0x18001ffef  mov     r8, rbx; lpMem
0x18001fff2  xor     edx, edx; dwFlags
0x18001fff4  mov     rcx, rax; hHeap
0x18001fff7  call    cs:__imp_HeapFree
0x18001fffd  mov     [rsp+0A8h+psz], r12
0x180020005  mov     rcx, [rsp+0A8h+bstrString]; pbstr
0x18002000a  call    cs:__imp_SysStringLen
0x180020010  lea     ecx, [rax+1]
0x180020013  add     rcx, rcx; size
0x180020016  call    MIDL_user_allocate
0x18002001b  mov     [rsp+0A8h+psz], rax
0x180020023  test    rax, rax
0x180020026  jnz     short loc_180020070
0x180020028  mov     [rsp+0A8h+var_58], al
0x18002002c  lea     rax, qword_180077320
0x180020033  mov     [rsp+0A8h+var_50], rax
0x180020038  mov     [rsp+0A8h+var_48], r12
0x18002003d  mov     [rsp+0A8h+var_40], r12
0x180020042  mov     [rsp+0A8h+var_38], 0Eh
0x18002004a  mov     [rsp+0A8h+var_34], 0FFFFFFFFFFFFFFFFh
0x180020053  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002005a  mov     [rsp+0A8h+pExceptionObject], rax
0x18002005f  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180020066  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18002006b  call    _CxxThrowException_0
0x180020070  mov     [rax], r12w
0x180020074  mov     rbx, [rsp+0A8h+bstrString]
0x180020079  mov     rcx, rbx; pbstr
0x18002007c  call    cs:__imp_SysStringLen
0x180020082  lea     edx, [rax+1]; unsigned __int64
0x180020085  mov     r8, rbx; unsigned __int16 *
0x180020088  mov     rcx, [rsp+0A8h+psz]; unsigned __int16 *
0x180020090  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020095  nop
0x180020096  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18002009b  call    cs:__imp_SysFreeString
0x1800200a1  nop
0x1800200a2  lea     rcx, [rsp+0A8h+var_70]
0x1800200a7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800200ac  jmp     loc_18001FE82
0x1800200b1  mov     ecx, 8007000Eh; int
0x1800200b6  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800200bb  mov     [rsi+70h], r12
0x1800200bf  jmp     loc_18001FEB8
0x1800200c4  mov     ecx, 8007000Eh; int
0x1800200c9  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800200cf  mov     r15d, [rsp+0A8h+arg_8]
0x1800200d7  jmp     loc_18001FF0C
```
