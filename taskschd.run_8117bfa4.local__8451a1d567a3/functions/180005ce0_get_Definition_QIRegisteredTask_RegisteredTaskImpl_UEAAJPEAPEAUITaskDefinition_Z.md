# ?get_Definition@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAUITaskDefinition@@@Z

- ea: `0x180005ce0`
- end: `0x180005ffd`
- name: `?get_Definition@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAUITaskDefinition@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001880`
- `0x180005ce0`
- `0x180006004`
- `0x1800060d0`
- `0x180006618`
- `0x180037cf0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005d12`
- `OLEAUT32!__imp_SysFreeString` at `0x180005dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eee`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f49`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e70`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ed9`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eee`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f49`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall _get_Definition__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAPEAUITaskDefinition___Z(
        RegisteredTaskImpl *this,
        __int64 a2)
{
  char *v4; // rbx
  int v5; // edi
  int v6; // edi
  int v7; // edi
  int LocalizedXml; // edi
  OLECHAR *v10; // rdi
  int v11; // esi
  unsigned int v12; // esi
  BSTR v13; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14[6]; // [rsp+38h] [rbp-30h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, TaskDefinitionImpl **); // [rsp+78h] [rbp+10h] BYREF
  TaskDefinitionImpl *v16; // [rsp+80h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (char *)this + 16;
  if ( !this )
    v4 = 0;
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v14[0] = (__int64)v4;
  v16 = 0;
  v15 = 0;
  v5 = ATL::CComObject<TaskDefinitionImpl>::CreateInstance(&v15);
  if ( v5 >= 0 )
    v5 = (**v15)(v15, &GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6, &v16);
  LODWORD(v15) = v5;
  if ( v5 < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
    ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(v14);
    return (unsigned int)v5;
  }
  else
  {
    bstrString = 0;
    v6 = (*(__int64 (__fastcall **)(RegisteredTaskImpl *, BSTR *))(*(_QWORD *)this + 160LL))(this, &bstrString);
    LODWORD(v15) = v6;
    if ( v6 < 0 )
    {
      SysFreeString(bstrString);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
      ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(v14);
      return (unsigned int)v6;
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(TaskDefinitionImpl *, BSTR))(*(_QWORD *)v16 + 160LL))(v16, bstrString);
      LODWORD(v15) = v7;
      if ( v7 >= 0 )
      {
        v13 = 0;
        LocalizedXml = RegisteredTaskImpl::get_LocalizedXml(this, &v13);
        LODWORD(v15) = LocalizedXml;
        if ( LocalizedXml < 0 )
        {
          SysFreeString(v13);
          SysFreeString(bstrString);
          if ( v16 )
            (*(void (__fastcall **)(TaskDefinitionImpl *))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v4 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
          return (unsigned int)LocalizedXml;
        }
        else
        {
          v10 = v13;
          v11 = TaskDefinitionImpl::put_LocalizedXmlText(v16, v13);
          LODWORD(v15) = v11;
          if ( v11 >= 0 )
          {
            v12 = (**(__int64 (__fastcall ***)(TaskDefinitionImpl *, GUID *, __int64))v16)(
                    v16,
                    &GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6,
                    a2);
            LODWORD(v15) = v12;
            SysFreeString(v10);
            SysFreeString(bstrString);
            if ( v16 )
              (*(void (__fastcall **)(TaskDefinitionImpl *))(*(_QWORD *)v16 + 16LL))(v16);
            if ( v4 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
            return v12;
          }
          else
          {
            SysFreeString(v10);
            SysFreeString(bstrString);
            if ( v16 )
              (*(void (__fastcall **)(TaskDefinitionImpl *))(*(_QWORD *)v16 + 16LL))(v16);
            if ( v4 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
            return (unsigned int)v11;
          }
        }
      }
      else
      {
        SysFreeString(bstrString);
        if ( v16 )
          (*(void (__fastcall **)(TaskDefinitionImpl *))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v4 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
        return (unsigned int)v7;
      }
    }
  }
}

```

## disassembly

```asm
0x180005ce0  push    rbx
0x180005ce2  push    rsi
0x180005ce3  push    rdi
0x180005ce4  push    r14
0x180005ce6  push    r15
0x180005ce8  sub     rsp, 40h
0x180005cec  mov     r14, rdx
0x180005cef  mov     rsi, rcx
0x180005cf2  test    rdx, rdx
0x180005cf5  jz      loc_180005F32
0x180005cfb  lea     rbx, [rcx+10h]
0x180005cff  xor     r15d, r15d
0x180005d02  test    rcx, rcx
0x180005d05  cmovz   rbx, r15
0x180005d09  test    rbx, rbx
0x180005d0c  jz      short loc_180005D1E
0x180005d0e  lea     rcx, [rbx+8]; lpCriticalSection
0x180005d12  call    cs:__imp_EnterCriticalSection
0x180005d19  nop     dword ptr [rax+rax+00h]
0x180005d1e  mov     [rsp+68h+var_30], rbx
0x180005d23  mov     [rsp+68h+arg_10], r15
0x180005d2b  mov     [rsp+68h+arg_8], r15
0x180005d30  lea     rcx, [rsp+68h+arg_8]
0x180005d35  call    ?CreateInstance@?$CComObject@VTaskDefinitionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskDefinitionImpl>::CreateInstance(ATL::CComObject<TaskDefinitionImpl> * *)
0x180005d3a  mov     edi, eax
0x180005d3c  test    eax, eax
0x180005d3e  js      short loc_180005D61
0x180005d40  mov     rcx, [rsp+68h+arg_8]
0x180005d45  mov     rax, [rcx]
0x180005d48  lea     r8, [rsp+68h+arg_10]
0x180005d50  lea     rdx, _GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6
0x180005d57  mov     rax, [rax]
0x180005d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d5f  mov     edi, eax
0x180005d61  mov     dword ptr [rsp+68h+arg_8], edi
0x180005d65  test    edi, edi
0x180005d67  js      loc_180005FA1
0x180005d6d  mov     [rsp+68h+bstrString], r15
0x180005d75  mov     rax, [rsi]
0x180005d78  lea     rdx, [rsp+68h+bstrString]
0x180005d80  mov     rcx, rsi
0x180005d83  mov     rax, [rax+0A0h]
0x180005d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d8f  mov     edi, eax
0x180005d91  mov     dword ptr [rsp+68h+arg_8], eax
0x180005d95  test    eax, eax
0x180005d97  js      loc_180005FC0
0x180005d9d  mov     rcx, [rsp+68h+arg_10]
0x180005da5  mov     rax, [rcx]
0x180005da8  mov     rdx, [rsp+68h+bstrString]
0x180005db0  mov     rax, [rax+0A0h]
0x180005db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbc  mov     edi, eax
0x180005dbe  mov     dword ptr [rsp+68h+arg_8], eax
0x180005dc2  test    eax, eax
0x180005dc4  jns     short loc_180005E19
0x180005dc6  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005dce  call    cs:__imp_SysFreeString
0x180005dd5  nop     dword ptr [rax+rax+00h]
0x180005dda  nop
0x180005ddb  mov     rcx, [rsp+68h+arg_10]
0x180005de3  test    rcx, rcx
0x180005de6  jz      short loc_180005DF5
0x180005de8  mov     rax, [rcx]
0x180005deb  mov     rax, [rax+10h]
0x180005def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df4  nop
0x180005df5  test    rbx, rbx
0x180005df8  jz      short loc_180005E0A
0x180005dfa  lea     rcx, [rbx+8]; lpCriticalSection
0x180005dfe  call    cs:__imp_LeaveCriticalSection
0x180005e05  nop     dword ptr [rax+rax+00h]
0x180005e0a  mov     eax, edi
0x180005e0c  add     rsp, 40h
0x180005e10  pop     r15
0x180005e12  pop     r14
0x180005e14  pop     rdi
0x180005e15  pop     rsi
0x180005e16  pop     rbx
0x180005e17  retn
0x180005e19  mov     [rsp+68h+var_38], r15
0x180005e1e  lea     rdx, [rsp+68h+var_38]; unsigned __int16 **
0x180005e23  mov     rcx, rsi; this
0x180005e26  call    ?get_LocalizedXml@RegisteredTaskImpl@@AEAAJPEAPEAG@Z; RegisteredTaskImpl::get_LocalizedXml(ushort * *)
0x180005e2b  mov     edi, eax
0x180005e2d  mov     dword ptr [rsp+68h+arg_8], eax
0x180005e31  test    eax, eax
0x180005e33  js      loc_180005F44
0x180005e39  mov     rdi, [rsp+68h+var_38]
0x180005e3e  mov     rdx, rdi; unsigned __int16 *
0x180005e41  mov     rcx, [rsp+68h+arg_10]; this
0x180005e49  call    ?put_LocalizedXmlText@TaskDefinitionImpl@@QEAAJPEAG@Z; TaskDefinitionImpl::put_LocalizedXmlText(ushort *)
0x180005e4e  mov     esi, eax
0x180005e50  mov     dword ptr [rsp+68h+arg_8], eax
0x180005e54  test    eax, eax
0x180005e56  jns     short loc_180005EB3
0x180005e58  mov     rcx, rdi; bstrString
0x180005e5b  call    cs:__imp_SysFreeString
0x180005e62  nop     dword ptr [rax+rax+00h]
0x180005e67  nop
0x180005e68  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005e70  call    cs:__imp_SysFreeString
0x180005e77  nop     dword ptr [rax+rax+00h]
0x180005e7c  nop
0x180005e7d  mov     rcx, [rsp+68h+arg_10]
0x180005e85  test    rcx, rcx
0x180005e88  jz      short loc_180005E97
0x180005e8a  mov     rax, [rcx]
0x180005e8d  mov     rax, [rax+10h]
0x180005e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e96  nop
0x180005e97  test    rbx, rbx
0x180005e9a  jz      short loc_180005EAC
0x180005e9c  lea     rcx, [rbx+8]; lpCriticalSection
0x180005ea0  call    cs:__imp_LeaveCriticalSection
0x180005ea7  nop     dword ptr [rax+rax+00h]
0x180005eac  mov     eax, esi
0x180005eae  jmp     loc_180005E0C
0x180005eb3  mov     rcx, [rsp+68h+arg_10]
0x180005ebb  mov     rax, [rcx]
0x180005ebe  mov     r8, r14
0x180005ec1  lea     rdx, _GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6
0x180005ec8  mov     rax, [rax]
0x180005ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed0  mov     esi, eax
0x180005ed2  mov     dword ptr [rsp+68h+arg_8], eax
0x180005ed6  mov     rcx, rdi; bstrString
0x180005ed9  call    cs:__imp_SysFreeString
0x180005ee0  nop     dword ptr [rax+rax+00h]
0x180005ee5  nop
0x180005ee6  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005eee  call    cs:__imp_SysFreeString
0x180005ef5  nop     dword ptr [rax+rax+00h]
0x180005efa  nop
0x180005efb  mov     rcx, [rsp+68h+arg_10]
0x180005f03  test    rcx, rcx
0x180005f06  jz      short loc_180005F15
0x180005f08  mov     rax, [rcx]
0x180005f0b  mov     rax, [rax+10h]
0x180005f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f14  nop
0x180005f15  test    rbx, rbx
0x180005f18  jz      short loc_180005F2B
0x180005f1a  lea     rcx, [rbx+8]; lpCriticalSection
0x180005f1e  call    cs:__imp_LeaveCriticalSection
0x180005f25  nop     dword ptr [rax+rax+00h]
0x180005f2a  nop
0x180005f2b  mov     eax, esi
0x180005f2d  jmp     loc_180005E0C
0x180005f32  mov     eax, 80004003h
0x180005f37  add     rsp, 40h
0x180005f3b  pop     r15
0x180005f3d  pop     r14
0x180005f3f  pop     rdi
0x180005f40  pop     rsi
0x180005f41  pop     rbx
0x180005f42  retn
0x180005f44  mov     rcx, [rsp+68h+var_38]; bstrString
0x180005f49  call    cs:__imp_SysFreeString
0x180005f50  nop     dword ptr [rax+rax+00h]
0x180005f55  nop
0x180005f56  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005f5e  call    cs:__imp_SysFreeString
0x180005f65  nop     dword ptr [rax+rax+00h]
0x180005f6a  nop
0x180005f6b  mov     rcx, [rsp+68h+arg_10]
0x180005f73  test    rcx, rcx
0x180005f76  jz      short loc_180005F85
0x180005f78  mov     rax, [rcx]
0x180005f7b  mov     rax, [rax+10h]
0x180005f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f84  nop
0x180005f85  test    rbx, rbx
0x180005f88  jz      short loc_180005F9A
0x180005f8a  lea     rcx, [rbx+8]; lpCriticalSection
0x180005f8e  call    cs:__imp_LeaveCriticalSection
0x180005f95  nop     dword ptr [rax+rax+00h]
0x180005f9a  mov     eax, edi
0x180005f9c  jmp     loc_180005E0C
0x180005fa1  lea     rcx, [rsp+68h+arg_10]
0x180005fa9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005fae  nop
0x180005faf  lea     rcx, [rsp+68h+var_30]
0x180005fb4  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180005fb9  mov     eax, edi
0x180005fbb  jmp     loc_180005E0C
0x180005fc0  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005fc8  call    cs:__imp_SysFreeString
0x180005fcf  nop     dword ptr [rax+rax+00h]
0x180005fd4  nop
0x180005fd5  lea     rcx, [rsp+68h+arg_10]
0x180005fdd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005fe2  nop
0x180005fe3  lea     rcx, [rsp+68h+var_30]
0x180005fe8  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180005fed  mov     eax, edi
0x180005fef  jmp     loc_180005E0C
0x180005ff4  mov     esi, dword ptr [rsp+68h+arg_8]
0x180005ff8  jmp     loc_180005F2B
```
