# ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Release(void)

- ea: `0x1400079c0`
- end: `0x140007a30`
- name: `?Release@?$CComObject@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAKXZ`
- size: `112`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x140002014`
- `0x1400079c0`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Release(
        CExeModule *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = *((_DWORD *)a1 + 12);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    *((_DWORD *)a1 + 12) = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      if ( a1 )
      {
        *((_DWORD *)a1 + 12) = 1;
        *(_QWORD *)a1 = &ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable';
        CExeModule::Unlock(a1);
        ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>((__int64)a1);
        operator delete(a1);
      }
      CExeModule::Unlock(a1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1400079c0  mov     [rsp+arg_0], rbx
0x1400079c5  push    rdi
0x1400079c6  sub     rsp, 20h
0x1400079ca  mov     edi, [rcx+30h]
0x1400079cd  mov     rbx, rcx
0x1400079d0  cmp     edi, 7FFFFFFFh
0x1400079d6  jnz     short loc_1400079DF
0x1400079d8  mov     edi, 7FFFFFFEh
0x1400079dd  jmp     short loc_140007A23
0x1400079df  sub     edi, 1
0x1400079e2  mov     [rcx+30h], edi
0x1400079e5  jnz     short loc_140007A23
0x1400079e7  lock inc cs:dword_1400153D8
0x1400079ee  test    rbx, rbx
0x1400079f1  jz      short loc_140007A1E
0x1400079f3  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable'
0x1400079fa  mov     dword ptr [rcx+30h], 1
0x140007a01  mov     [rcx], rax
0x140007a04  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007a09  mov     rcx, rbx
0x140007a0c  call    ??1?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>(void)
0x140007a11  mov     edx, 40h ; '@'; unsigned __int64
0x140007a16  mov     rcx, rbx; void *
0x140007a19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007a1e  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007a23  mov     rbx, [rsp+28h+arg_0]
0x140007a28  mov     eax, edi
0x140007a2a  add     rsp, 20h
0x140007a2e  pop     rdi
0x140007a2f  retn
```
