# CreateArchiveThread::CreateAsync(CreateArchiveOptions const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>,IUnknown *,bool)

- ea: `0x18005da60`
- end: `0x18005dca1`
- name: `?CreateAsync@CreateArchiveThread@@SAJAEBUCreateArchiveOptions@@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@PEAUIUnknown@@_N@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005d9e4`

## callees

- `0x180030a3c`
- `0x180031e94`
- `0x180033aa8`
- `0x18003519c`
- `0x18003534c`
- `0x180036f50`
- `0x18004f308`
- `0x18005b0f0`
- `0x18005b680`
- `0x18005da60`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18005dbdd`
- `SHLWAPI!__imp_SHCreateThread` at `0x18005dbdd`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18005db0e`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x18005db0e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005db3d`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18005db3d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18005db6e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18005db6e`

## string_xrefs

- `0x18005db83`: `shell\ext\zip\archive\archivecreate.cpp`
- `0x18005dbec`: `shell\ext\zip\archive\archivecreate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CreateArchiveThread::CreateAsync(__int128 *a1, char *a2, char *a3, IUnknown *a4, char a5)
{
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  char *v11; // rbx
  __int64 v12; // rax
  IUnknown *v13; // rdx
  HRESULT v14; // eax
  unsigned int v15; // r15d
  const char *v16; // r9
  __int64 result; // rax
  const char *v18; // r9
  unsigned int LastError; // ebx
  void *ppvOut; // [rsp+30h] [rbp-48h] BYREF
  void *pData; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  std::make_unique<CreateArchiveThread,,0>(&pData);
  v9 = *a1;
  v10 = a1[1];
  v11 = (char *)pData;
  *((_OWORD *)pData + 1) = v9;
  *((_OWORD *)v11 + 2) = v10;
  if ( v11 + 48 != a2 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v11 + 48,
      *(_QWORD *)a2);
    *(_QWORD *)a2 = 0;
  }
  if ( v11 + 56 != a3 )
  {
    std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(v11 + 56);
    *((_QWORD *)v11 + 7) = *(_QWORD *)a3;
    *((_QWORD *)v11 + 8) = *((_QWORD *)a3 + 1);
    v12 = *((_QWORD *)a3 + 2);
    *((_QWORD *)v11 + 9) = v12;
    *(_QWORD *)a3 = 0;
    *((_QWORD *)a3 + 1) = 0;
    *((_QWORD *)a3 + 2) = 0;
  }
  try
  {
    IUnknown_GetWindow(a4, (HWND *)v11 + 1);
    v11[88] = a5;
    ppvOut = 0;
    IUnknown_QueryService(a4, &IID_INewMenuClient, &GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0, &ppvOut);
    v13 = (IUnknown *)ppvOut;
    if ( !ppvOut )
      goto LABEL_28;
    if ( *((_QWORD *)v11 + 10) )
    {
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v11 + 80);
      v13 = (IUnknown *)ppvOut;
    }
    v14 = CoMarshalInterThreadInterfaceInStream(&IID_INewMenuClient, v13, (LPSTREAM *)v11 + 10);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x330,
        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
        (const char *)(unsigned int)v14);
      if ( ppvOut )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppvOut);
      std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(&pData);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
      std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(a3);
      result = v15;
    }
    else
    {
LABEL_28:
      if ( SHCreateThread(CreateArchiveThread::ThreadProc, v11, 8u, 0) )
      {
        pData = 0;
        if ( ppvOut )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppvOut);
        std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(&pData);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
        std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(a3);
        result = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x333,
                      (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                      v18);
        if ( ppvOut )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppvOut);
        std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(&pData);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
        std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(a3);
        result = LastError;
      }
    }
  }
  catch ( ... )
  {
    LODWORD(ppvOut) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x338,
                        (unsigned int)"shell\\ext\\zip\\archive\\archivecreate.cpp",
                        v16);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
    std::vector<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Tidy(a3);
    return (unsigned int)ppvOut;
  }
  return result;
}

```

## disassembly

```asm
0x18005da60  push    rbx
0x18005da62  push    rsi
0x18005da63  push    r12
0x18005da65  push    r14
0x18005da67  push    r15
0x18005da69  sub     rsp, 50h
0x18005da6d  mov     rax, cs:__security_cookie
0x18005da74  xor     rax, rsp
0x18005da77  mov     [rsp+78h+var_38], rax
0x18005da7c  mov     r12, r9
0x18005da7f  mov     rsi, r8
0x18005da82  mov     r14, rdx
0x18005da85  mov     rbx, rcx
0x18005da88  mov     [rsp+78h+var_58], rdx
0x18005da8d  mov     [rsp+78h+var_50], r8
0x18005da92  lea     rcx, [rsp+78h+pData]
0x18005da97  call    ??$make_unique@UCreateArchiveThread@@$$V$0A@@std@@YA?AV?$unique_ptr@UCreateArchiveThread@@U?$default_delete@UCreateArchiveThread@@@std@@@0@XZ; std::make_unique<CreateArchiveThread,,0>(void)
0x18005da9c  nop
0x18005da9d  movups  xmm0, xmmword ptr [rbx]
0x18005daa0  movups  xmm1, xmmword ptr [rbx+10h]
0x18005daa4  mov     rbx, [rsp+78h+pData]
0x18005daa9  movups  xmmword ptr [rbx+10h], xmm0
0x18005daad  movups  xmmword ptr [rbx+20h], xmm1
0x18005dab1  lea     rcx, [rbx+30h]
0x18005dab5  cmp     rcx, r14
0x18005dab8  jz      short loc_18005DAC9
0x18005daba  mov     rdx, [r14]
0x18005dabd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005dac2  mov     qword ptr [r14], 0
0x18005dac9  lea     r15, [rbx+38h]
0x18005dacd  cmp     r15, rsi
0x18005dad0  jz      short loc_18005DB07
0x18005dad2  mov     rcx, r15
0x18005dad5  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18005dada  mov     rax, [rsi]
0x18005dadd  mov     [r15], rax
0x18005dae0  mov     rax, [rsi+8]
0x18005dae4  mov     [r15+8], rax
0x18005dae8  mov     rax, [rsi+10h]
0x18005daec  mov     [r15+10h], rax
0x18005daf0  mov     qword ptr [rsi], 0
0x18005daf7  mov     qword ptr [rsi+8], 0
0x18005daff  mov     qword ptr [rsi+10h], 0
0x18005db07  lea     rdx, [rbx+8]; phwnd
0x18005db0b  mov     rcx, r12; punk
0x18005db0e  call    cs:__imp_IUnknown_GetWindow
0x18005db14  mov     al, [rsp+78h+arg_20]
0x18005db1b  mov     [rbx+58h], al
0x18005db1e  mov     [rsp+78h+ppvOut], 0
0x18005db27  lea     r9, [rsp+78h+ppvOut]; ppvOut
0x18005db2c  lea     r8, _GUID_dcb07fdc_3bb5_451c_90be_966644fed7b0; riid
0x18005db33  lea     rdx, IID_INewMenuClient; guidService
0x18005db3a  mov     rcx, r12; punk
0x18005db3d  call    cs:__imp_IUnknown_QueryService
0x18005db43  mov     rdx, [rsp+78h+ppvOut]
0x18005db48  test    rdx, rdx
0x18005db4b  jz      short loc_18005DBCC
0x18005db4d  lea     r15, [rbx+50h]
0x18005db51  cmp     qword ptr [r15], 0
0x18005db55  jz      short loc_18005DB64
0x18005db57  mov     rcx, r15
0x18005db5a  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005db5f  mov     rdx, [rsp+78h+ppvOut]; pUnk
0x18005db64  mov     r8, r15; ppStm
0x18005db67  lea     rcx, IID_INewMenuClient; riid
0x18005db6e  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18005db74  mov     r15d, eax
0x18005db77  test    eax, eax
0x18005db79  jns     short loc_18005DBCC
0x18005db7b  mov     rcx, [rsp+78h]
0x18005db80  mov     r9d, eax
0x18005db83  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005db8a  mov     edx, 330h
0x18005db8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005db94  nop
0x18005db95  cmp     [rsp+78h+ppvOut], 0
0x18005db9b  jz      short loc_18005DBA8
0x18005db9d  lea     rcx, [rsp+78h+ppvOut]
0x18005dba2  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005dba7  nop
0x18005dba8  lea     rcx, [rsp+78h+pData]
0x18005dbad  call    ??1?$unique_ptr@UCreateArchiveThread@@U?$default_delete@UCreateArchiveThread@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(void)
0x18005dbb2  nop
0x18005dbb3  mov     rcx, r14
0x18005dbb6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dbbb  nop
0x18005dbbc  mov     rcx, rsi
0x18005dbbf  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18005dbc4  mov     eax, r15d
0x18005dbc7  jmp     loc_18005DC87
0x18005dbcc  xor     r9d, r9d; pfnCallback
0x18005dbcf  lea     r8d, [r9+8]; flags
0x18005dbd3  mov     rdx, rbx; pData
0x18005dbd6  lea     rcx, ?ThreadProc@CreateArchiveThread@@CAKPEAX@Z; pfnThreadProc
0x18005dbdd  call    cs:__imp_SHCreateThread
0x18005dbe3  test    eax, eax
0x18005dbe5  jnz     short loc_18005DC32
0x18005dbe7  mov     rcx, [rsp+78h]; this
0x18005dbec  lea     r8, aShellExtZipArc_10; "shell\\ext\\zip\\archive\\archivecreate"...
0x18005dbf3  mov     edx, 333h; void *
0x18005dbf8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005dbfd  mov     ebx, eax
0x18005dbff  cmp     [rsp+78h+ppvOut], 0
0x18005dc05  jz      short loc_18005DC12
0x18005dc07  lea     rcx, [rsp+78h+ppvOut]
0x18005dc0c  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005dc11  nop
0x18005dc12  lea     rcx, [rsp+78h+pData]
0x18005dc17  call    ??1?$unique_ptr@UCreateArchiveThread@@U?$default_delete@UCreateArchiveThread@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(void)
0x18005dc1c  nop
0x18005dc1d  mov     rcx, r14
0x18005dc20  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dc25  nop
0x18005dc26  mov     rcx, rsi
0x18005dc29  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18005dc2e  mov     eax, ebx
0x18005dc30  jmp     short loc_18005DC87
0x18005dc32  mov     [rsp+78h+pData], 0
0x18005dc3b  cmp     [rsp+78h+ppvOut], 0
0x18005dc41  jz      short loc_18005DC4E
0x18005dc43  lea     rcx, [rsp+78h+ppvOut]
0x18005dc48  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18005dc4d  nop
0x18005dc4e  lea     rcx, [rsp+78h+pData]
0x18005dc53  call    ??1?$unique_ptr@UCreateArchiveThread@@U?$default_delete@UCreateArchiveThread@@@std@@@std@@QEAA@XZ; std::unique_ptr<CreateArchiveThread>::~unique_ptr<CreateArchiveThread>(void)
0x18005dc58  nop
0x18005dc59  mov     rcx, r14
0x18005dc5c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dc61  nop
0x18005dc62  mov     rcx, rsi
0x18005dc65  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18005dc6a  xor     eax, eax
0x18005dc6c  jmp     short loc_18005DC87
0x18005dc6e  mov     rcx, [rsp+78h+var_58]
0x18005dc73  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dc78  nop
0x18005dc79  mov     rcx, [rsp+78h+var_50]
0x18005dc7e  call    ?_Tidy@?$vector@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAXXZ; std::vector<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Tidy(void)
0x18005dc83  mov     eax, dword ptr [rsp+78h+ppvOut]
0x18005dc87  mov     rcx, [rsp+78h+var_38]
0x18005dc8c  xor     rcx, rsp; StackCookie
0x18005dc8f  call    __security_check_cookie
0x18005dc94  add     rsp, 50h
0x18005dc98  pop     r15
0x18005dc9a  pop     r14
0x18005dc9c  pop     r12
0x18005dc9e  pop     rsi
0x18005dc9f  pop     rbx
0x18005dca0  retn
```
