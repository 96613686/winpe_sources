# ?get_Definition@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAUITaskDefinition@@@Z

- ea: `0x180005a20`
- end: `0x180005ced`
- name: `?get_Definition@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAUITaskDefinition@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x180005a20`
- `0x180005cf4`
- `0x180005e20`
- `0x1800062cc`
- `0x1800351ec`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005bc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005bc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c8a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a52`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b08`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b88`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b97`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c03`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c51`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c60`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b08`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b88`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b97`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c03`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c51`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c60`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cbe`

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
0x180005a20  push    rbx
0x180005a22  push    rsi
0x180005a23  push    rdi
0x180005a24  push    r14
0x180005a26  push    r15
0x180005a28  sub     rsp, 40h
0x180005a2c  mov     r14, rdx
0x180005a2f  mov     rsi, rcx
0x180005a32  test    rdx, rdx
0x180005a35  jz      loc_180005C3B
0x180005a3b  lea     rbx, [rcx+10h]
0x180005a3f  xor     r15d, r15d
0x180005a42  test    rcx, rcx
0x180005a45  cmovz   rbx, r15
0x180005a49  test    rbx, rbx
0x180005a4c  jz      short loc_180005A58
0x180005a4e  lea     rcx, [rbx+8]; lpCriticalSection
0x180005a52  call    cs:__imp_EnterCriticalSection
0x180005a58  mov     [rsp+68h+var_30], rbx
0x180005a5d  mov     [rsp+68h+arg_10], r15
0x180005a65  mov     [rsp+68h+arg_8], r15
0x180005a6a  lea     rcx, [rsp+68h+arg_8]
0x180005a6f  call    ?CreateInstance@?$CComObject@VTaskDefinitionImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskDefinitionImpl>::CreateInstance(ATL::CComObject<TaskDefinitionImpl> * *)
0x180005a74  mov     edi, eax
0x180005a76  test    eax, eax
0x180005a78  js      short loc_180005A9B
0x180005a7a  mov     rcx, [rsp+68h+arg_8]
0x180005a7f  mov     rax, [rcx]
0x180005a82  lea     r8, [rsp+68h+arg_10]
0x180005a8a  lea     rdx, _GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6
0x180005a91  mov     rax, [rax]
0x180005a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a99  mov     edi, eax
0x180005a9b  mov     dword ptr [rsp+68h+arg_8], edi
0x180005a9f  test    edi, edi
0x180005aa1  js      loc_180005C97
0x180005aa7  mov     [rsp+68h+bstrString], r15
0x180005aaf  mov     rax, [rsi]
0x180005ab2  lea     rdx, [rsp+68h+bstrString]
0x180005aba  mov     rcx, rsi
0x180005abd  mov     rax, [rax+0A0h]
0x180005ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac9  mov     edi, eax
0x180005acb  mov     dword ptr [rsp+68h+arg_8], eax
0x180005acf  test    eax, eax
0x180005ad1  js      loc_180005CB6
0x180005ad7  mov     rcx, [rsp+68h+arg_10]
0x180005adf  mov     rax, [rcx]
0x180005ae2  mov     rdx, [rsp+68h+bstrString]
0x180005aea  mov     rax, [rax+0A0h]
0x180005af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af6  mov     edi, eax
0x180005af8  mov     dword ptr [rsp+68h+arg_8], eax
0x180005afc  test    eax, eax
0x180005afe  jns     short loc_180005B46
0x180005b00  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005b08  call    cs:__imp_SysFreeString
0x180005b0e  nop
0x180005b0f  mov     rcx, [rsp+68h+arg_10]
0x180005b17  test    rcx, rcx
0x180005b1a  jz      short loc_180005B29
0x180005b1c  mov     rax, [rcx]
0x180005b1f  mov     rax, [rax+10h]
0x180005b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b28  nop
0x180005b29  test    rbx, rbx
0x180005b2c  jz      short loc_180005B38
0x180005b2e  lea     rcx, [rbx+8]; lpCriticalSection
0x180005b32  call    cs:__imp_LeaveCriticalSection
0x180005b38  mov     eax, edi
0x180005b3a  add     rsp, 40h
0x180005b3e  pop     r15
0x180005b40  pop     r14
0x180005b42  pop     rdi
0x180005b43  pop     rsi
0x180005b44  pop     rbx
0x180005b45  retn
0x180005b46  mov     [rsp+68h+var_38], r15
0x180005b4b  lea     rdx, [rsp+68h+var_38]; unsigned __int16 **
0x180005b50  mov     rcx, rsi; this
0x180005b53  call    ?get_LocalizedXml@RegisteredTaskImpl@@AEAAJPEAPEAG@Z; RegisteredTaskImpl::get_LocalizedXml(ushort * *)
0x180005b58  mov     edi, eax
0x180005b5a  mov     dword ptr [rsp+68h+arg_8], eax
0x180005b5e  test    eax, eax
0x180005b60  js      loc_180005C4C
0x180005b66  mov     rdi, [rsp+68h+var_38]
0x180005b6b  mov     rdx, rdi; unsigned __int16 *
0x180005b6e  mov     rcx, [rsp+68h+arg_10]; this
0x180005b76  call    ?put_LocalizedXmlText@TaskDefinitionImpl@@QEAAJPEAG@Z; TaskDefinitionImpl::put_LocalizedXmlText(ushort *)
0x180005b7b  mov     esi, eax
0x180005b7d  mov     dword ptr [rsp+68h+arg_8], eax
0x180005b81  test    eax, eax
0x180005b83  jns     short loc_180005BCE
0x180005b85  mov     rcx, rdi; bstrString
0x180005b88  call    cs:__imp_SysFreeString
0x180005b8e  nop
0x180005b8f  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005b97  call    cs:__imp_SysFreeString
0x180005b9d  nop
0x180005b9e  mov     rcx, [rsp+68h+arg_10]
0x180005ba6  test    rcx, rcx
0x180005ba9  jz      short loc_180005BB8
0x180005bab  mov     rax, [rcx]
0x180005bae  mov     rax, [rax+10h]
0x180005bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb7  nop
0x180005bb8  test    rbx, rbx
0x180005bbb  jz      short loc_180005BC7
0x180005bbd  lea     rcx, [rbx+8]; lpCriticalSection
0x180005bc1  call    cs:__imp_LeaveCriticalSection
0x180005bc7  mov     eax, esi
0x180005bc9  jmp     loc_180005B3A
0x180005bce  mov     rcx, [rsp+68h+arg_10]
0x180005bd6  mov     rax, [rcx]
0x180005bd9  mov     r8, r14
0x180005bdc  lea     rdx, _GUID_f5bc8fc5_536d_4f77_b852_fbc1356fdeb6
0x180005be3  mov     rax, [rax]
0x180005be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005beb  mov     esi, eax
0x180005bed  mov     dword ptr [rsp+68h+arg_8], eax
0x180005bf1  mov     rcx, rdi; bstrString
0x180005bf4  call    cs:__imp_SysFreeString
0x180005bfa  nop
0x180005bfb  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005c03  call    cs:__imp_SysFreeString
0x180005c09  nop
0x180005c0a  mov     rcx, [rsp+68h+arg_10]
0x180005c12  test    rcx, rcx
0x180005c15  jz      short loc_180005C24
0x180005c17  mov     rax, [rcx]
0x180005c1a  mov     rax, [rax+10h]
0x180005c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c23  nop
0x180005c24  test    rbx, rbx
0x180005c27  jz      short loc_180005C34
0x180005c29  lea     rcx, [rbx+8]; lpCriticalSection
0x180005c2d  call    cs:__imp_LeaveCriticalSection
0x180005c33  nop
0x180005c34  mov     eax, esi
0x180005c36  jmp     loc_180005B3A
0x180005c3b  mov     eax, 80004003h
0x180005c40  add     rsp, 40h
0x180005c44  pop     r15
0x180005c46  pop     r14
0x180005c48  pop     rdi
0x180005c49  pop     rsi
0x180005c4a  pop     rbx
0x180005c4b  retn
0x180005c4c  mov     rcx, [rsp+68h+var_38]; bstrString
0x180005c51  call    cs:__imp_SysFreeString
0x180005c57  nop
0x180005c58  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005c60  call    cs:__imp_SysFreeString
0x180005c66  nop
0x180005c67  mov     rcx, [rsp+68h+arg_10]
0x180005c6f  test    rcx, rcx
0x180005c72  jz      short loc_180005C81
0x180005c74  mov     rax, [rcx]
0x180005c77  mov     rax, [rax+10h]
0x180005c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c80  nop
0x180005c81  test    rbx, rbx
0x180005c84  jz      short loc_180005C90
0x180005c86  lea     rcx, [rbx+8]; lpCriticalSection
0x180005c8a  call    cs:__imp_LeaveCriticalSection
0x180005c90  mov     eax, edi
0x180005c92  jmp     loc_180005B3A
0x180005c97  lea     rcx, [rsp+68h+arg_10]
0x180005c9f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005ca4  nop
0x180005ca5  lea     rcx, [rsp+68h+var_30]
0x180005caa  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180005caf  mov     eax, edi
0x180005cb1  jmp     loc_180005B3A
0x180005cb6  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180005cbe  call    cs:__imp_SysFreeString
0x180005cc4  nop
0x180005cc5  lea     rcx, [rsp+68h+arg_10]
0x180005ccd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180005cd2  nop
0x180005cd3  lea     rcx, [rsp+68h+var_30]
0x180005cd8  call    ??1?$CComObjectLockT@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectLockT<ATL::CComMultiThreadModel>::~CComObjectLockT<ATL::CComMultiThreadModel>(void)
0x180005cdd  mov     eax, edi
0x180005cdf  jmp     loc_180005B3A
0x180005ce4  mov     esi, dword ptr [rsp+68h+arg_8]
0x180005ce8  jmp     loc_180005C34
```
