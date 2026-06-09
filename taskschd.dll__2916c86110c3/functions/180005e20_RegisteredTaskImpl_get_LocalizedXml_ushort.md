# RegisteredTaskImpl::get_LocalizedXml(ushort * *)

- ea: `0x180005e20`
- end: `0x1800062c5`
- name: `?get_LocalizedXml@RegisteredTaskImpl@@AEAAJPEAPEAG@Z`
- size: `1189`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180005a20`

## callees

- `0x1800017f0`
- `0x180005e20`
- `0x180007aa0`
- `0x18000fca0`
- `0x18001e240`
- `0x18001fa40`
- `0x180030d7c`
- `0x180032504`
- `0x180036290`
- `0x180039524`
- `0x18003b51c`
- `0x180048cb0`
- `0x18004e90f`
- `0x180054010`

## import_xrefs

- `msvcrt!malloc` at `0x180005e70`
- `msvcrt!malloc` at `0x180005e70`
- `msvcrt!free` at `0x180005f1c`
- `msvcrt!free` at `0x180005fec`
- `msvcrt!free` at `0x18000602e`
- `msvcrt!free` at `0x180005f1c`
- `msvcrt!free` at `0x180005fec`
- `msvcrt!free` at `0x18000602e`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180005eaf`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006136`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180005eaf`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x180006136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000610e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f36`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000610e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ff8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000603a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ff8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000603a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006100`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800061c5`
- `OLEAUT32!__imp_SysAllocString` at `0x180005fd2`
- `OLEAUT32!__imp_SysAllocString` at `0x180005fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fc0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006286`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fc0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800061a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006286`
- `OLEAUT32!__imp_SysStringLen` at `0x1800061e3`
- `OLEAUT32!__imp_SysStringLen` at `0x18000626a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800061e3`
- `OLEAUT32!__imp_SysStringLen` at `0x18000626a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall RegisteredTaskImpl::get_LocalizedXml(RegisteredTaskImpl *this, unsigned __int16 **a2)
{
  int v4; // esi
  BSTR *v5; // r14
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  unsigned __int64 v8; // rax
  ULONG v9; // r8d
  const unsigned __int16 *v10; // rdx
  void *v11; // rbx
  HANDLE v12; // rax
  unsigned __int16 *v14; // rax
  RpcSession *v15; // rcx
  const OLECHAR *v16; // rbx
  BSTR v17; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  signed int LastError; // eax
  unsigned int v21; // esi
  HANDLE v22; // rax
  void *v23; // rax
  HANDLE ProcessHeap; // rax
  int XmlLegacy; // ebx
  HANDLE v26; // rax
  UINT v27; // eax
  _WORD *v28; // rax
  const unsigned __int16 *v29; // rbx
  UINT v30; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C0h] BYREF
  struct ITask *v33; // [rsp+40h] [rbp-B8h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+48h] [rbp-B0h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-A8h] BYREF
  char v36; // [rsp+58h] [rbp-A0h]
  __int64 *v37; // [rsp+60h] [rbp-98h]
  __int64 v38; // [rsp+68h] [rbp-90h]
  __int64 v39; // [rsp+70h] [rbp-88h]
  int v40; // [rsp+78h] [rbp-80h]
  __int64 v41; // [rsp+7Ch] [rbp-7Ch]
  void **v42; // [rsp+88h] [rbp-70h] BYREF
  char v43; // [rsp+90h] [rbp-68h]
  __int64 *v44; // [rsp+98h] [rbp-60h]
  __int64 v45; // [rsp+A0h] [rbp-58h]
  __int64 v46; // [rsp+A8h] [rbp-50h]
  int v47; // [rsp+B0h] [rbp-48h]
  __int64 v48; // [rsp+B4h] [rbp-44h]
  ULONG pcchLanguagesBuffer; // [rsp+110h] [rbp+18h] BYREF
  ULONG pulNumLanguages; // [rsp+118h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = 0;
  v5 = (BSTR *)((char *)this + 120);
  if ( *((_QWORD *)this + 15) )
    goto LABEL_16;
  lpMem = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 200;
  v6 = (WCHAR *)malloc(0x190u);
  v7 = v6;
  if ( !v6 )
  {
    v36 = 0;
    v37 = &qword_180077320;
    v38 = 0;
    v39 = 0;
    v40 = 14;
    v41 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  pwszLanguagesBuffer = v6;
  memset_0(v6, 0, 0x190u);
  if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, v7, &pcchLanguagesBuffer) )
    goto LABEL_5;
  if ( GetLastError() == 111 )
  {
    wmi::AutoVectorPtr<unsigned short>::Delete(&pwszLanguagesBuffer);
    v23 = operator new(saturated_mul(pcchLanguagesBuffer, 2u));
    wmi::AutoVectorPtr<unsigned short>::operator=(&pwszLanguagesBuffer, v23);
    v7 = pwszLanguagesBuffer;
    if ( !pwszLanguagesBuffer )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
      return 2147942414LL;
    }
    if ( GetThreadPreferredUILanguages(0x28u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
    {
LABEL_5:
      v8 = 0;
      v9 = pcchLanguagesBuffer;
      if ( pcchLanguagesBuffer != 1 )
      {
        do
        {
          if ( !v7[v8] )
          {
            v7[v8] = 92;
            v9 = pcchLanguagesBuffer;
          }
          ++v8;
        }
        while ( v8 < v9 - 1 );
      }
      v10 = (const unsigned __int16 *)((char *)this + 80);
      if ( *((_QWORD *)this + 13) >= 8u )
        v10 = *(const unsigned __int16 **)v10;
      if ( !*((_DWORD *)this + 32) )
      {
        v4 = -2147023645;
LABEL_13:
        if ( v7 )
          free(v7);
        v11 = lpMem;
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v11);
        return (unsigned int)v4;
      }
      v15 = (RpcSession *)*((_QWORD *)this + 17);
      if ( v15 )
      {
        v4 = RpcSession::RetrieveTask(v15, v10, v7, &pulNumLanguages, (struct RpcString *)&lpMem);
        if ( v4 < 0 )
          goto LABEL_13;
        goto LABEL_21;
      }
      if ( v10 && *v10 == 92 )
        ++v10;
      v33 = 0;
      XmlLegacy = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, struct ITask **))(**((_QWORD **)this + 18) + 48LL))(
                    *((_QWORD *)this + 18),
                    v10,
                    &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                    &v33);
      if ( XmlLegacy >= 0 )
      {
        bstrString = 0;
        XmlLegacy = UniSession::GenerateXmlLegacy(v33, (struct ATL::CComBSTR *)&bstrString);
        if ( XmlLegacy >= 0 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, lpMem);
          v27 = SysStringLen(bstrString);
          v28 = MIDL_user_allocate(2LL * (v27 + 1));
          lpMem = v28;
          if ( !v28 )
          {
            v43 = 0;
            v44 = &qword_180077320;
            v45 = 0;
            v46 = 0;
            v47 = 14;
            v48 = -1;
            v42 = &wmi::GenericException::`vftable';
            throw (wmi::OutOfMemoryException *)&v42;
          }
          *v28 = 0;
          v29 = bstrString;
          v30 = SysStringLen(bstrString);
          StringCchCopyW((unsigned __int16 *)lpMem, v30 + 1, v29);
          SysFreeString(bstrString);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
LABEL_21:
          v16 = (const OLECHAR *)lpMem;
          if ( lpMem != *v5 )
          {
            SysFreeString(*v5);
            if ( v16 )
            {
              v17 = SysAllocString(v16);
              *v5 = v17;
              if ( !v17 )
                ATL::PrivateAtlThrow(-2147024882);
            }
            else
            {
              *v5 = 0;
            }
          }
          if ( v7 )
            free(v7);
          v18 = lpMem;
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v18);
LABEL_16:
          v14 = ATL::CComBSTR::Copy((ATL::CComBSTR *)v5);
          if ( *v5 && !v14 )
            ATL::PrivateAtlThrow(-2147024882);
          *a2 = v14;
          SysFreeString(0);
          return (unsigned int)v4;
        }
        SysFreeString(bstrString);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      v4 = XmlLegacy;
      goto LABEL_13;
    }
  }
  LastError = GetLastError();
  v21 = LastError;
  if ( LastError > 0 )
    v21 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 )
    free(v7);
  v22 = GetProcessHeap();
  HeapFree(v22, 0, lpMem);
  return v21;
}

```

## disassembly

```asm
0x180005e20  mov     rax, rsp
0x180005e23  push    rbx
0x180005e24  push    rsi
0x180005e25  push    rdi
0x180005e26  push    r12
0x180005e28  push    r13
0x180005e2a  push    r14
0x180005e2c  push    r15
0x180005e2e  sub     rsp, 0C0h
0x180005e35  mov     r15, rdx
0x180005e38  mov     rbx, rcx
0x180005e3b  test    rdx, rdx
0x180005e3e  jz      loc_180006055
0x180005e44  xor     r13d, r13d
0x180005e47  mov     esi, r13d
0x180005e4a  mov     [rax+10h], r13d
0x180005e4e  lea     r14, [rcx+78h]
0x180005e52  cmp     [r14], r13
0x180005e55  jnz     loc_180005F51
0x180005e5b  mov     [rsp+0F8h+lpMem], r13
0x180005e60  mov     [rax+20h], r13d
0x180005e64  mov     dword ptr [rax+18h], 0C8h
0x180005e6b  mov     ecx, 190h; Size
0x180005e70  call    cs:__imp_malloc
0x180005e76  mov     rdi, rax
0x180005e79  test    rax, rax
0x180005e7c  jz      loc_18000605F
0x180005e82  mov     [rsp+0F8h+pwszLanguagesBuffer], rax
0x180005e87  xor     edx, edx; Val
0x180005e89  mov     r8d, 190h; Size
0x180005e8f  mov     rcx, rax; void *
0x180005e92  call    memset_0
0x180005e97  lea     r9, [rsp+0F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180005e9f  mov     r8, rdi; pwszLanguagesBuffer
0x180005ea2  lea     rdx, [rsp+0F8h+pulNumLanguages]; pulNumLanguages
0x180005eaa  mov     ecx, 28h ; '('; dwFlags
0x180005eaf  call    cs:__imp_GetThreadPreferredUILanguages
0x180005eb5  test    eax, eax
0x180005eb7  jz      loc_1800060A9
0x180005ebd  mov     rax, r13
0x180005ec0  mov     r8d, [rsp+0F8h+pcchLanguagesBuffer]
0x180005ec8  lea     ecx, [r8-1]
0x180005ecc  test    ecx, ecx
0x180005ece  jz      short loc_180005EF1
0x180005ed0  cmp     word ptr [rdi+rax*2], 0
0x180005ed5  jnz     short loc_180005EE5
0x180005ed7  mov     word ptr [rdi+rax*2], 5Ch ; '\'
0x180005edd  mov     r8d, [rsp+0F8h+pcchLanguagesBuffer]
0x180005ee5  inc     rax
0x180005ee8  lea     edx, [r8-1]
0x180005eec  cmp     rax, rdx
0x180005eef  jb      short loc_180005ED0
0x180005ef1  lea     rdx, [rbx+50h]
0x180005ef5  cmp     qword ptr [rdx+18h], 8
0x180005efa  jb      short loc_180005EFF
0x180005efc  mov     rdx, [rdx]; unsigned __int16 *
0x180005eff  cmp     dword ptr [rbx+80h], 0
0x180005f06  jnz     short loc_180005F78
0x180005f08  mov     esi, 800704E3h
0x180005f0d  mov     [rsp+0F8h+arg_8], esi
0x180005f14  test    rdi, rdi
0x180005f17  jz      short loc_180005F23
0x180005f19  mov     rcx, rdi; Block
0x180005f1c  call    cs:__imp_free
0x180005f22  nop
0x180005f23  mov     rbx, [rsp+0F8h+lpMem]
0x180005f28  call    cs:__imp_GetProcessHeap
0x180005f2e  mov     r8, rbx; lpMem
0x180005f31  xor     edx, edx; dwFlags
0x180005f33  mov     rcx, rax; hHeap
0x180005f36  call    cs:__imp_HeapFree
0x180005f3c  mov     eax, esi
0x180005f3e  add     rsp, 0C0h
0x180005f45  pop     r15
0x180005f47  pop     r14
0x180005f49  pop     r13
0x180005f4b  pop     r12
0x180005f4d  pop     rdi
0x180005f4e  pop     rsi
0x180005f4f  pop     rbx
0x180005f50  retn
0x180005f51  mov     rcx, r14; this
0x180005f54  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180005f59  cmp     qword ptr [r14], 0
0x180005f5d  jz      short loc_180005F68
0x180005f5f  test    rax, rax
0x180005f62  jz      loc_1800062AE
0x180005f68  mov     [r15], rax
0x180005f6b  xor     ecx, ecx; bstrString
0x180005f6d  call    cs:__imp_SysFreeString
0x180005f73  nop
0x180005f74  mov     eax, esi
0x180005f76  jmp     short loc_180005F3E
0x180005f78  mov     rcx, [rbx+88h]; this
0x180005f7f  test    rcx, rcx
0x180005f82  jz      loc_180006149
0x180005f88  lea     rax, [rsp+0F8h+lpMem]
0x180005f8d  mov     [rsp+0F8h+var_D8], rax; struct RpcString *
0x180005f92  lea     r9, [rsp+0F8h+pulNumLanguages]; unsigned int *
0x180005f9a  mov     r8, rdi; unsigned __int16 *
0x180005f9d  call    ?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z; RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)
0x180005fa2  mov     esi, eax
0x180005fa4  mov     [rsp+0F8h+arg_8], eax
0x180005fab  test    eax, eax
0x180005fad  js      loc_180005F14
0x180005fb3  mov     rbx, [rsp+0F8h+lpMem]
0x180005fb8  mov     rcx, [r14]; bstrString
0x180005fbb  cmp     rbx, rcx
0x180005fbe  jz      short loc_180005FE4
0x180005fc0  call    cs:__imp_SysFreeString
0x180005fc6  test    rbx, rbx
0x180005fc9  jz      loc_1800062A6
0x180005fcf  mov     rcx, rbx; psz
0x180005fd2  call    cs:__imp_SysAllocString
0x180005fd8  mov     [r14], rax
0x180005fdb  test    rax, rax
0x180005fde  jz      loc_18000629C
0x180005fe4  test    rdi, rdi
0x180005fe7  jz      short loc_180005FF3
0x180005fe9  mov     rcx, rdi; Block
0x180005fec  call    cs:__imp_free
0x180005ff2  nop
0x180005ff3  mov     rbx, [rsp+0F8h+lpMem]
0x180005ff8  call    cs:__imp_GetProcessHeap
0x180005ffe  mov     r8, rbx; lpMem
0x180006001  xor     edx, edx; dwFlags
0x180006003  mov     rcx, rax; hHeap
0x180006006  call    cs:__imp_HeapFree
0x18000600c  jmp     loc_180005F51
0x180006011  call    cs:__imp_GetLastError
0x180006017  mov     esi, eax
0x180006019  test    eax, eax
0x18000601b  jle     short loc_180006026
0x18000601d  movzx   esi, ax
0x180006020  or      esi, 80070000h
0x180006026  test    rdi, rdi
0x180006029  jz      short loc_180006035
0x18000602b  mov     rcx, rdi; Block
0x18000602e  call    cs:__imp_free
0x180006034  nop
0x180006035  mov     rbx, [rsp+0F8h+lpMem]
0x18000603a  call    cs:__imp_GetProcessHeap
0x180006040  mov     r8, rbx; lpMem
0x180006043  xor     edx, edx; dwFlags
0x180006045  mov     rcx, rax; hHeap
0x180006048  call    cs:__imp_HeapFree
0x18000604e  mov     eax, esi
0x180006050  jmp     loc_180005F3E
0x180006055  mov     eax, 80004003h
0x18000605a  jmp     loc_180005F3E
0x18000605f  mov     [rsp+0F8h+var_A0], 0
0x180006064  lea     rax, qword_180077320
0x18000606b  mov     [rsp+0F8h+var_98], rax
0x180006070  mov     [rsp+0F8h+var_90], r13
0x180006075  mov     [rsp+0F8h+var_88], r13
0x18000607a  mov     [rsp+0F8h+var_80], 0Eh
0x180006082  mov     [rsp+0F8h+var_7C], 0FFFFFFFFFFFFFFFFh
0x18000608b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180006092  mov     [rsp+0F8h+pExceptionObject], rax
0x180006097  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000609e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800060a3  call    _CxxThrowException_0
0x1800060a9  call    cs:__imp_GetLastError
0x1800060af  cmp     eax, 6Fh ; 'o'
0x1800060b2  jnz     loc_180006011
0x1800060b8  lea     rcx, [rsp+0F8h+pwszLanguagesBuffer]
0x1800060bd  call    ?Delete@?$AutoVectorPtr@G@wmi@@QEAAXXZ; wmi::AutoVectorPtr<ushort>::Delete(void)
0x1800060c2  mov     ecx, [rsp+0F8h+pcchLanguagesBuffer]
0x1800060c9  mov     eax, 2
0x1800060ce  mul     rcx
0x1800060d1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800060d8  cmovb   rax, r12
0x1800060dc  mov     rcx, rax; unsigned __int64
0x1800060df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800060e4  mov     rdx, rax
0x1800060e7  lea     rcx, [rsp+0F8h+pwszLanguagesBuffer]
0x1800060ec  call    ??4?$AutoVectorPtr@G@wmi@@QEAAAEAV01@PEAG@Z; wmi::AutoVectorPtr<ushort>::operator=(ushort *)
0x1800060f1  mov     rdi, [rsp+0F8h+pwszLanguagesBuffer]
0x1800060f6  test    rdi, rdi
0x1800060f9  jnz     short loc_18000611E
0x1800060fb  mov     rbx, [rsp+0F8h+lpMem]
0x180006100  call    cs:__imp_GetProcessHeap
0x180006106  mov     r8, rbx; lpMem
0x180006109  xor     edx, edx; dwFlags
0x18000610b  mov     rcx, rax; hHeap
0x18000610e  call    cs:__imp_HeapFree
0x180006114  mov     eax, 8007000Eh
0x180006119  jmp     loc_180005F3E
0x18000611e  lea     r9, [rsp+0F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180006126  mov     r8, rdi; pwszLanguagesBuffer
0x180006129  lea     rdx, [rsp+0F8h+pulNumLanguages]; pulNumLanguages
0x180006131  mov     ecx, 28h ; '('; dwFlags
0x180006136  call    cs:__imp_GetThreadPreferredUILanguages
0x18000613c  test    eax, eax
0x18000613e  jnz     loc_180005EBD
0x180006144  jmp     loc_180006011
0x180006149  test    rdx, rdx
0x18000614c  jz      short loc_180006158
0x18000614e  cmp     word ptr [rdx], 5Ch ; '\'
0x180006152  jnz     short loc_180006158
0x180006154  add     rdx, 2
0x180006158  mov     [rsp+0F8h+var_B8], r13
0x18000615d  mov     rcx, [rbx+90h]
0x180006164  mov     rax, [rcx]
0x180006167  lea     r9, [rsp+0F8h+var_B8]
0x18000616c  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x180006173  mov     rax, [rax+30h]
0x180006177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617c  mov     ebx, eax
0x18000617e  test    eax, eax
0x180006180  js      short loc_1800061A8
0x180006182  mov     [rsp+0F8h+bstrString], r13
0x180006187  lea     rdx, [rsp+0F8h+bstrString]; struct ATL::CComBSTR *
0x18000618c  mov     rcx, [rsp+0F8h+var_B8]; struct ITask *
0x180006191  call    ?GenerateXmlLegacy@UniSession@@CAJPEAUITask@@AEAVCComBSTR@ATL@@@Z; UniSession::GenerateXmlLegacy(ITask *,ATL::CComBSTR &)
0x180006196  mov     ebx, eax
0x180006198  test    eax, eax
0x18000619a  jns     short loc_1800061C0
0x18000619c  mov     rcx, [rsp+0F8h+bstrString]; bstrString
0x1800061a1  call    cs:__imp_SysFreeString
0x1800061a7  nop
0x1800061a8  lea     rcx, [rsp+0F8h+var_B8]
0x1800061ad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800061b2  mov     [rsp+0F8h+arg_8], ebx
0x1800061b9  mov     esi, ebx
0x1800061bb  jmp     loc_180005F14
0x1800061c0  mov     rbx, [rsp+0F8h+lpMem]
0x1800061c5  call    cs:__imp_GetProcessHeap
0x1800061cb  mov     r8, rbx; lpMem
0x1800061ce  xor     edx, edx; dwFlags
0x1800061d0  mov     rcx, rax; hHeap
0x1800061d3  call    cs:__imp_HeapFree
0x1800061d9  mov     [rsp+0F8h+lpMem], r13
0x1800061de  mov     rcx, [rsp+0F8h+bstrString]; pbstr
0x1800061e3  call    cs:__imp_SysStringLen
0x1800061e9  lea     ecx, [rax+1]
0x1800061ec  add     rcx, rcx; size
0x1800061ef  call    MIDL_user_allocate
0x1800061f4  mov     [rsp+0F8h+lpMem], rax
0x1800061f9  test    rax, rax
0x1800061fc  jnz     short loc_18000625E
0x1800061fe  mov     [rsp+0F8h+var_68], al
0x180006205  lea     rax, qword_180077320
0x18000620c  mov     [rsp+0F8h+var_60], rax
0x180006214  mov     [rsp+0F8h+var_58], r13
0x18000621c  mov     [rsp+0F8h+var_50], r13
0x180006224  mov     [rsp+0F8h+var_48], 0Eh
0x18000622f  mov     [rsp+0F8h+var_44], 0FFFFFFFFFFFFFFFFh
0x18000623b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180006242  mov     [rsp+0F8h+var_70], rax
0x18000624a  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180006251  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x180006259  call    _CxxThrowException_0
0x18000625e  mov     [rax], r13w
0x180006262  mov     rbx, [rsp+0F8h+bstrString]
0x180006267  mov     rcx, rbx; pbstr
0x18000626a  call    cs:__imp_SysStringLen
0x180006270  lea     edx, [rax+1]; unsigned __int64
0x180006273  mov     r8, rbx; unsigned __int16 *
0x180006276  mov     rcx, [rsp+0F8h+lpMem]; unsigned __int16 *
0x18000627b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006280  nop
0x180006281  mov     rcx, [rsp+0F8h+bstrString]; bstrString
0x180006286  call    cs:__imp_SysFreeString
0x18000628c  nop
0x18000628d  lea     rcx, [rsp+0F8h+var_B8]
0x180006292  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006297  jmp     loc_180005FB3
0x18000629c  mov     ecx, 8007000Eh; int
0x1800062a1  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800062a6  mov     [r14], r13
0x1800062a9  jmp     loc_180005FE4
0x1800062ae  mov     ecx, 8007000Eh; int
0x1800062b3  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800062b9  mov     esi, [rsp+0F8h+arg_8]
0x1800062c0  jmp     loc_180005F74
```
