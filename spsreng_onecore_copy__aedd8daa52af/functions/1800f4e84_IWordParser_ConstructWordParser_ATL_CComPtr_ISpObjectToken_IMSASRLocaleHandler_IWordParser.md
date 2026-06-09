# IWordParser::ConstructWordParser(ATL::CComPtr<ISpObjectToken>,IMSASRLocaleHandler *,IWordParser * *)

- ea: `0x1800f4e84`
- end: `0x1800f5067`
- name: `?ConstructWordParser@IWordParser@@SAJV?$CComPtr@UISpObjectToken@@@ATL@@PEAUIMSASRLocaleHandler@@PEAPEAV1@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c973c`

## callees

- `0x180002470`
- `0x180002db8`
- `0x180004306`
- `0x1800061d0`
- `0x1800b36c4`
- `0x1800f4e84`
- `0x1800f6cbc`
- `0x1800f6d00`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800f4fbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4fcf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4fbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f4fcf`

## string_xrefs

- `0x1800f4fa6`: `Datafile does not have xml or bin extension.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IWordParser::ConstructWordParser(__int64 *a1, __int64 a2, CWordParsingENX **a3)
{
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  CWordParsingENX *v8; // rax
  CWordParsingENX *v9; // rdi
  unsigned __int16 *v10; // rsi
  int v11; // eax
  int v12; // esi
  CWordParsingENX *v13; // rax
  _QWORD v15[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v16; // [rsp+80h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+58h] BYREF

  v15[0] = 0;
  v16 = 0;
  v6 = *a1;
  if ( !v6
    || (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD *))(*(_QWORD *)v6 + 72LL))(v6, L"Wordparse", v15) < 0
    || (*(int (__fastcall **)(_QWORD, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v15[0] + 48LL))(
         v15[0],
         L"DataFile",
         &v16) < 0 )
  {
    v13 = (CWordParsingENX *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x18u, 0);
    v9 = v13;
    if ( !v13 )
    {
      v12 = -2147024882;
      goto LABEL_25;
    }
    *((_QWORD *)v13 + 1) = 0;
    *((_QWORD *)v13 + 2) = 0;
    *(_QWORD *)v13 = &CWordParsingDefault::`vftable';
    v12 = 0;
    goto LABEL_21;
  }
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v16);
  v7 = -1;
  do
    ++v7;
  while ( v16[v7] );
  v8 = (CWordParsingENX *)CWinHeap::Alloc((CWinHeap *)&g_heap, 0x48u, 0);
  v15[1] = v8;
  if ( !v8 )
  {
    v9 = 0;
    goto LABEL_18;
  }
  v9 = CWordParsingENX::CWordParsingENX(v8);
  if ( !v9 )
  {
LABEL_18:
    v12 = -2147024882;
    SysFreeString(bstrString);
    goto LABEL_26;
  }
  if ( v7 <= 4 )
    goto LABEL_15;
  v10 = &v16[v7];
  if ( wcscmp_0(v10 - 3, L"xml") )
  {
    if ( !wcscmp_0(v10 - 3, L"bin") )
    {
      v11 = (*(__int64 (__fastcall **)(CWordParsingENX *, BSTR, __int64))(*(_QWORD *)v9 + 16LL))(v9, bstrString, a2);
      goto LABEL_13;
    }
    WPFsmError(L"Datafile does not have xml or bin extension.");
LABEL_15:
    v12 = -2147467259;
    goto LABEL_16;
  }
  v11 = (*(__int64 (__fastcall **)(CWordParsingENX *, BSTR, __int64))(*(_QWORD *)v9 + 8LL))(v9, bstrString, a2);
LABEL_13:
  v12 = v11;
LABEL_16:
  SysFreeString(bstrString);
LABEL_21:
  *((_QWORD *)v9 + 1) = 0;
  *((_DWORD *)v9 + 4) = 0;
  if ( v12 < 0 && v9 )
  {
    (**(void (__fastcall ***)(CWordParsingENX *, __int64))v9)(v9, 1);
LABEL_25:
    v9 = 0;
  }
LABEL_26:
  *a3 = v9;
  CSpDynamicString::_free((LPVOID *)&v16);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v15);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(a1);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800f4e84  mov     [rsp-38h+arg_0], rcx
0x1800f4e89  push    rbp
0x1800f4e8a  push    rsi
0x1800f4e8b  push    rdi
0x1800f4e8c  push    r12
0x1800f4e8e  push    r13
0x1800f4e90  push    r14
0x1800f4e92  push    r15
0x1800f4e94  mov     rbp, rsp
0x1800f4e97  sub     rsp, 30h
0x1800f4e9b  mov     r12, r8
0x1800f4e9e  mov     r15, rdx
0x1800f4ea1  mov     r14, rcx
0x1800f4ea4  xor     r13d, r13d
0x1800f4ea7  mov     [rbp+var_10], r13
0x1800f4eab  mov     [rbp+arg_10], r13
0x1800f4eaf  mov     rcx, [rcx]
0x1800f4eb2  test    rcx, rcx
0x1800f4eb5  jz      loc_1800F4FD7
0x1800f4ebb  mov     rax, [rcx]
0x1800f4ebe  lea     r8, [rbp+var_10]
0x1800f4ec2  lea     rdx, aWordparse; "Wordparse"
0x1800f4ec9  mov     rax, [rax+48h]
0x1800f4ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ed2  test    eax, eax
0x1800f4ed4  js      loc_1800F4FD7
0x1800f4eda  mov     rcx, [rbp+var_10]
0x1800f4ede  mov     rax, [rcx]
0x1800f4ee1  lea     r8, [rbp+arg_10]
0x1800f4ee5  lea     rdx, aDatafile; "DataFile"
0x1800f4eec  mov     rax, [rax+30h]
0x1800f4ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4ef5  test    eax, eax
0x1800f4ef7  js      loc_1800F4FD7
0x1800f4efd  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x1800f4f01  lea     rcx, [rbp+bstrString]; this
0x1800f4f05  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800f4f0a  nop
0x1800f4f0b  mov     rax, [rbp+arg_10]
0x1800f4f0f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800f4f13  inc     rsi
0x1800f4f16  cmp     [rax+rsi*2], r13w
0x1800f4f1b  jnz     short loc_1800F4F13
0x1800f4f1d  xor     r8d, r8d; bool
0x1800f4f20  lea     edx, [r8+48h]; unsigned __int64
0x1800f4f24  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800f4f2b  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800f4f30  mov     [rbp+var_8], rax
0x1800f4f34  test    rax, rax
0x1800f4f37  jz      loc_1800F4FC3
0x1800f4f3d  mov     rcx, rax; this
0x1800f4f40  call    ??0CWordParsingENX@@QEAA@XZ; CWordParsingENX::CWordParsingENX(void)
0x1800f4f45  mov     rdi, rax
0x1800f4f48  test    rax, rax
0x1800f4f4b  jz      short loc_1800F4FC6
0x1800f4f4d  cmp     rsi, 4
0x1800f4f51  jbe     short loc_1800F4FB2
0x1800f4f53  mov     rax, [rbp+arg_10]
0x1800f4f57  lea     rsi, [rax+rsi*2]
0x1800f4f5b  lea     rdx, aXml; "xml"
0x1800f4f62  lea     rcx, [rsi-6]; String1
0x1800f4f66  call    wcscmp_0
0x1800f4f6b  test    eax, eax
0x1800f4f6d  jnz     short loc_1800F4F78
0x1800f4f6f  mov     rax, [rdi]
0x1800f4f72  mov     rax, [rax+8]
0x1800f4f76  jmp     short loc_1800F4F93
0x1800f4f78  lea     rdx, aBin; "bin"
0x1800f4f7f  lea     rcx, [rsi-6]; String1
0x1800f4f83  call    wcscmp_0
0x1800f4f88  test    eax, eax
0x1800f4f8a  jnz     short loc_1800F4FA6
0x1800f4f8c  mov     rax, [rdi]
0x1800f4f8f  mov     rax, [rax+10h]
0x1800f4f93  mov     rcx, rdi
0x1800f4f96  mov     rdx, [rbp+bstrString]
0x1800f4f9a  mov     r8, r15
0x1800f4f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4fa2  mov     esi, eax
0x1800f4fa4  jmp     short loc_1800F4FB7
0x1800f4fa6  lea     rcx, aDatafileDoesNo; "Datafile does not have xml or bin exten"...
0x1800f4fad  call    ?WPFsmError@@YAXPEBGZZ; WPFsmError(ushort const *,...)
0x1800f4fb2  mov     esi, 80004005h
0x1800f4fb7  mov     rcx, [rbp+bstrString]; bstrString
0x1800f4fbb  call    cs:__imp_SysFreeString
0x1800f4fc1  jmp     short loc_1800F5007
0x1800f4fc3  mov     rdi, r13
0x1800f4fc6  mov     esi, 8007000Eh
0x1800f4fcb  mov     rcx, [rbp+bstrString]; bstrString
0x1800f4fcf  call    cs:__imp_SysFreeString
0x1800f4fd5  jmp     short loc_1800F5035
0x1800f4fd7  xor     r8d, r8d; bool
0x1800f4fda  lea     edx, [r8+18h]; unsigned __int64
0x1800f4fde  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800f4fe5  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800f4fea  mov     rdi, rax
0x1800f4fed  test    rax, rax
0x1800f4ff0  jz      short loc_1800F502D
0x1800f4ff2  mov     [rax+8], r13
0x1800f4ff6  mov     [rax+10h], r13
0x1800f4ffa  lea     rax, ??_7CWordParsingDefault@@6B@; const CWordParsingDefault::`vftable'
0x1800f5001  mov     [rdi], rax
0x1800f5004  mov     esi, r13d
0x1800f5007  mov     [rdi+8], r13
0x1800f500b  mov     [rdi+10h], r13d
0x1800f500f  test    esi, esi
0x1800f5011  jns     short loc_1800F5035
0x1800f5013  test    rdi, rdi
0x1800f5016  jz      short loc_1800F5035
0x1800f5018  mov     rax, [rdi]
0x1800f501b  mov     edx, 1
0x1800f5020  mov     rcx, rdi
0x1800f5023  mov     rax, [rax]
0x1800f5026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f502b  jmp     short loc_1800F5032
0x1800f502d  mov     esi, 8007000Eh
0x1800f5032  mov     rdi, r13
0x1800f5035  mov     [r12], rdi
0x1800f5039  lea     rcx, [rbp+arg_10]; this
0x1800f503d  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800f5042  nop
0x1800f5043  lea     rcx, [rbp+var_10]
0x1800f5047  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800f504c  nop
0x1800f504d  mov     rcx, r14
0x1800f5050  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800f5055  mov     eax, esi
0x1800f5057  add     rsp, 30h
0x1800f505b  pop     r15
0x1800f505d  pop     r14
0x1800f505f  pop     r13
0x1800f5061  pop     r12
0x1800f5063  pop     rdi
0x1800f5064  pop     rsi
0x1800f5065  pop     rbp
0x1800f5066  retn
```
