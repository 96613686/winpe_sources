# CreateArchiveWizard::Start(IUnknown *,IShellItemArray *)

- ea: `0x180051f70`
- end: `0x180052256`
- name: `?Start@CreateArchiveWizard@@SAJPEAUIUnknown@@PEAUIShellItemArray@@@Z`
- size: `742`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051c00`

## callees

- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x180036f50`
- `0x18004de28`
- `0x18004f418`
- `0x18004f448`
- `0x18005051c`
- `0x1800505dc`
- `0x180051f70`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x1800521f1`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800521f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800520d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800521c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800520d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800521c0`

## string_xrefs

- `0x180051ffc`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052036`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x1800520ac`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x18005214d`: `shell\ext\zip\archive\createarchivewizard.cpp`
- `0x180052203`: `shell\ext\zip\archive\createarchivewizard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CreateArchiveWizard::Start(struct IUnknown *a1, struct IShellItemArray *a2)
{
  char *v4; // rbx
  _QWORD *v5; // r14
  int v6; // eax
  unsigned int v7; // esi
  unsigned int i; // esi
  int v10; // eax
  int v11; // r14d
  void *v12; // rcx
  __int64 v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  const char *v16; // r9
  unsigned int LastError; // ebx
  LPVOID *p_pv; // [rsp+20h] [rbp-68h] BYREF
  __int64 v19; // [rsp+28h] [rbp-60h] BYREF
  char v20; // [rsp+30h] [rbp-58h]
  unsigned int v21; // [rsp+38h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v23; // [rsp+48h] [rbp-40h] BYREF
  void *pData; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  std::make_unique<CreateArchiveWizard,,0>(&pData);
  v4 = (char *)pData;
  v5 = (char *)pData + 8;
  if ( *((struct IUnknown **)pData + 1) != a1 )
  {
    if ( *v5 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref((char *)pData + 8);
    *v5 = a1;
    if ( a1 )
      ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->AddRef)(a1);
  }
  v21 = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellItemArray *, unsigned int *))a2->lpVtbl->GetCount)(a2, &v21);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v21 )
    {
      std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::reserve(
        v4 + 16,
        v21);
      for ( i = 0; i < v21; ++i )
      {
        v23 = 0;
        pv = 0;
        v10 = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 **))a2->lpVtbl->GetItemAt)(a2, i, &v23);
        v11 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E,
            (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
            (const char *)(unsigned int)v10);
          v12 = pv;
          pv = 0;
          if ( v12 )
            CoTaskMemFree(v12);
          if ( v23 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v23);
LABEL_17:
          std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(&pData);
          return (unsigned int)v11;
        }
        v13 = *v23;
        p_pv = &pv;
        v19 = 0;
        v20 = 1;
        v11 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v13 + 40))(v23, 2147844096LL, &v19);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F,
            (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
            (const char *)(unsigned int)v11);
          v14 = pv;
          pv = 0;
          if ( v14 )
            CoTaskMemFree(v14);
          if ( v23 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v23);
          goto LABEL_17;
        }
        std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::push_back(
          v4 + 16,
          &pv);
        v15 = pv;
        pv = 0;
        if ( v15 )
          CoTaskMemFree(v15);
        if ( v23 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v23);
      }
      if ( SHCreateThread(CreateArchiveWizard::ThreadProc, v4, 0x28u, 0) )
      {
        pData = 0;
        std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(&pData);
        return 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x23,
                      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
                      v16);
        std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(&pData);
        return LastError;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
        (const char *)0x80070057LL);
      std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(&pData);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"shell\\ext\\zip\\archive\\createarchivewizard.cpp",
      (const char *)(unsigned int)v6);
    std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(&pData);
    return v7;
  }
}

```

## disassembly

```asm
0x180051f70  push    rbx
0x180051f72  push    rsi
0x180051f73  push    r14
0x180051f75  push    r15
0x180051f77  sub     rsp, 68h
0x180051f7b  mov     rax, cs:__security_cookie
0x180051f82  xor     rax, rsp
0x180051f85  mov     [rsp+88h+var_30], rax
0x180051f8a  mov     r15, rdx
0x180051f8d  mov     rsi, rcx
0x180051f90  lea     rcx, [rsp+88h+pData]
0x180051f95  call    ??$make_unique@UCreateArchiveWizard@@$$V$0A@@std@@YA?AV?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@0@XZ; std::make_unique<CreateArchiveWizard,,0>(void)
0x180051f9a  nop
0x180051f9b  mov     rbx, [rsp+88h+pData]
0x180051fa0  lea     r14, [rbx+8]
0x180051fa4  cmp     [r14], rsi
0x180051fa7  jz      short loc_180051FCF
0x180051fa9  cmp     qword ptr [r14], 0
0x180051fad  jz      short loc_180051FB7
0x180051faf  mov     rcx, r14
0x180051fb2  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180051fb7  mov     [r14], rsi
0x180051fba  test    rsi, rsi
0x180051fbd  jz      short loc_180051FCF
0x180051fbf  mov     rax, [rsi]
0x180051fc2  mov     rcx, rsi
0x180051fc5  mov     rax, [rax+8]
0x180051fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fce  nop
0x180051fcf  mov     [rsp+88h+var_50], 0
0x180051fd7  mov     rax, [r15]
0x180051fda  lea     rdx, [rsp+88h+var_50]
0x180051fdf  mov     rcx, r15
0x180051fe2  mov     rax, [rax+38h]
0x180051fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051feb  mov     esi, eax
0x180051fed  test    eax, eax
0x180051fef  jns     short loc_18005201F
0x180051ff1  mov     rcx, [rsp+88h]
0x180051ff9  mov     r9d, eax
0x180051ffc  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052003  mov     edx, 17h
0x180052008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005200d  nop
0x18005200e  lea     rcx, [rsp+88h+pData]
0x180052013  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x180052018  mov     eax, esi
0x18005201a  jmp     loc_18005223D
0x18005201f  cmp     [rsp+88h+var_50], 0
0x180052024  jnz     short loc_180052059
0x180052026  mov     rcx, [rsp+88h]
0x18005202e  mov     ebx, 80070057h
0x180052033  mov     r9d, ebx
0x180052036  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x18005203d  mov     edx, 18h
0x180052042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052047  nop
0x180052048  lea     rcx, [rsp+88h+pData]
0x18005204d  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x180052052  mov     eax, ebx
0x180052054  jmp     loc_18005223D
0x180052059  mov     edx, [rsp+88h+var_50]
0x18005205d  lea     rcx, [rbx+10h]
0x180052061  call    ?reserve@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX_K@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::reserve(unsigned __int64)
0x180052066  xor     esi, esi
0x180052068  cmp     esi, [rsp+88h+var_50]
0x18005206c  jnb     loc_1800521E0
0x180052072  mov     [rsp+88h+var_40], 0
0x18005207b  mov     [rsp+88h+pv], 0
0x180052084  mov     rax, [r15]
0x180052087  lea     r8, [rsp+88h+var_40]
0x18005208c  mov     edx, esi
0x18005208e  mov     rcx, r15
0x180052091  mov     rax, [rax+40h]
0x180052095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005209a  mov     r14d, eax
0x18005209d  test    eax, eax
0x18005209f  jns     short loc_1800520FD
0x1800520a1  mov     rcx, [rsp+88h]
0x1800520a9  mov     r9d, eax
0x1800520ac  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x1800520b3  mov     edx, 1Eh
0x1800520b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800520bd  nop
0x1800520be  mov     rcx, [rsp+88h+pv]; pv
0x1800520c3  mov     [rsp+88h+pv], 0
0x1800520cc  test    rcx, rcx
0x1800520cf  jz      short loc_1800520D8
0x1800520d1  call    cs:__imp_CoTaskMemFree
0x1800520d7  nop
0x1800520d8  cmp     [rsp+88h+var_40], 0
0x1800520de  jz      short loc_1800520EB
0x1800520e0  lea     rcx, [rsp+88h+var_40]
0x1800520e5  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800520ea  nop
0x1800520eb  lea     rcx, [rsp+88h+pData]
0x1800520f0  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x1800520f5  mov     eax, r14d
0x1800520f8  jmp     loc_18005223D
0x1800520fd  mov     rcx, [rsp+88h+var_40]
0x180052102  mov     rax, [rcx]
0x180052105  lea     rdx, [rsp+88h+pv]
0x18005210a  mov     [rsp+88h+var_68], rdx
0x18005210f  mov     [rsp+88h+var_60], 0
0x180052118  mov     [rsp+88h+var_58], 1
0x18005211d  lea     r8, [rsp+88h+var_60]
0x180052122  mov     edx, 80058000h
0x180052127  mov     rax, [rax+28h]
0x18005212b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052130  mov     r14d, eax
0x180052133  lea     rcx, [rsp+88h+var_68]
0x180052138  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18005213d  test    r14d, r14d
0x180052140  jns     short loc_18005219E
0x180052142  mov     rcx, [rsp+88h]
0x18005214a  mov     r9d, r14d
0x18005214d  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x180052154  mov     edx, 1Fh
0x180052159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005215e  nop
0x18005215f  mov     rcx, [rsp+88h+pv]; pv
0x180052164  mov     [rsp+88h+pv], 0
0x18005216d  test    rcx, rcx
0x180052170  jz      short loc_180052179
0x180052172  call    cs:__imp_CoTaskMemFree
0x180052178  nop
0x180052179  cmp     [rsp+88h+var_40], 0
0x18005217f  jz      short loc_18005218C
0x180052181  lea     rcx, [rsp+88h+var_40]
0x180052186  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005218b  nop
0x18005218c  lea     rcx, [rsp+88h+pData]
0x180052191  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x180052196  mov     eax, r14d
0x180052199  jmp     loc_18005223D
0x18005219e  lea     rcx, [rbx+10h]
0x1800521a2  lea     rdx, [rsp+88h+pv]
0x1800521a7  call    ?push_back@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAAX$$QEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::push_back(wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x1800521ac  nop
0x1800521ad  mov     rcx, [rsp+88h+pv]; pv
0x1800521b2  mov     [rsp+88h+pv], 0
0x1800521bb  test    rcx, rcx
0x1800521be  jz      short loc_1800521C7
0x1800521c0  call    cs:__imp_CoTaskMemFree
0x1800521c6  nop
0x1800521c7  cmp     [rsp+88h+var_40], 0
0x1800521cd  jz      short loc_1800521D9
0x1800521cf  lea     rcx, [rsp+88h+var_40]
0x1800521d4  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800521d9  inc     esi
0x1800521db  jmp     loc_180052068
0x1800521e0  xor     r9d, r9d; pfnCallback
0x1800521e3  lea     r8d, [r9+28h]; flags
0x1800521e7  mov     rdx, rbx; pData
0x1800521ea  lea     rcx, ?ThreadProc@CreateArchiveWizard@@CAKPEAX@Z; pfnThreadProc
0x1800521f1  call    cs:__imp_SHCreateThread
0x1800521f7  test    eax, eax
0x1800521f9  jnz     short loc_180052222
0x1800521fb  mov     rcx, [rsp+88h]; this
0x180052203  lea     r8, aShellExtZipArc_1; "shell\\ext\\zip\\archive\\createarchive"...
0x18005220a  lea     edx, [rax+23h]; void *
0x18005220d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052212  mov     ebx, eax
0x180052214  lea     rcx, [rsp+88h+pData]
0x180052219  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x18005221e  mov     eax, ebx
0x180052220  jmp     short loc_18005223D
0x180052222  mov     [rsp+88h+pData], 0
0x18005222b  lea     rcx, [rsp+88h+pData]
0x180052230  call    ??1?$unique_ptr@UCreateArchiveWizard@@U?$default_delete@UCreateArchiveWizard@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveWizard>::~unique_ptr<CreateArchiveWizard>(void)
0x180052235  xor     eax, eax
0x180052237  jmp     short loc_18005223D
0x180052239  mov     eax, [rsp+88h+var_50]
0x18005223d  mov     rcx, [rsp+88h+var_30]
0x180052242  xor     rcx, rsp; StackCookie
0x180052245  call    __security_check_cookie
0x18005224a  add     rsp, 68h
0x18005224e  pop     r15
0x180052250  pop     r14
0x180052252  pop     rsi
0x180052253  pop     rbx
0x180052254  retn
```
