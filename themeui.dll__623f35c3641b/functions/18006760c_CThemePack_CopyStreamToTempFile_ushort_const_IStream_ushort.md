# CThemePack::_CopyStreamToTempFile(ushort const *,IStream *,ushort * *)

- ea: `0x18006760c`
- end: `0x180067747`
- name: `?_CopyStreamToTempFile@CThemePack@@AEAAJPEBGPEAUIStream@@PEAPEAG@Z`
- size: `315`
- prototype: `int(CThemePack *__hidden this, const unsigned __int16 *, struct IStream *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006735c`

## callees

- `0x18000b328`
- `0x180030e84`
- `0x1800358c0`
- `0x18003633c`
- `0x180042f84`
- `0x180053604`
- `0x18006760c`
- `0x18006d010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileEx` at `0x180067689`
- `SHCORE!SHCreateStreamOnFileEx` at `0x180067689`
- `SHCORE!SHStrDupW` at `0x18006770b`
- `SHCORE!SHStrDupW` at `0x18006770b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067717`

## pseudocode

```c
__int64 __fastcall CThemePack::_CopyStreamToTempFile(
        CThemePack *this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        unsigned __int16 **a4)
{
  HRESULT TmpMicroImagePath; // ebx
  IStream **ppstm; // rax
  LPCWSTR pszFile; // [rsp+30h] [rbp-29h] BYREF
  __int64 v10; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v11[16]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+50h] [rbp-9h]

  *a4 = 0;
  pszFile = 0;
  TmpMicroImagePath = CThemePack::_GetTmpMicroImagePath(this, a2, (unsigned __int16 **)&pszFile);
  if ( TmpMicroImagePath >= 0 )
  {
    ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(&v10);
    ppstm = (IStream **)ATL::CComPtrBase<ITheme>::operator&(&v10);
    TmpMicroImagePath = SHCreateStreamOnFileEx(pszFile, 0x1021u, 0x80u, 1, 0, ppstm);
    if ( TmpMicroImagePath >= 0 )
    {
      memset_0(v11, 0, 0x50u);
      TmpMicroImagePath = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a3 + 96LL))(
                            a3,
                            v11,
                            1);
      if ( TmpMicroImagePath >= 0 )
      {
        TmpMicroImagePath = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a3 + 56LL))(
                              a3,
                              v10,
                              v12,
                              0,
                              0);
        if ( TmpMicroImagePath >= 0 )
        {
          TmpMicroImagePath = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 64LL))(v10, 0);
          if ( TmpMicroImagePath >= 0 )
            TmpMicroImagePath = SHStrDupW(pszFile, a4);
        }
      }
    }
    CoTaskMemFree((LPVOID)pszFile);
    ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&v10);
  }
  return (unsigned int)TmpMicroImagePath;
}

```

## disassembly

```asm
0x18006760c  mov     [rsp-8+arg_0], rbx
0x180067611  push    rbp
0x180067612  push    rsi
0x180067613  push    rdi
0x180067614  lea     rbp, [rsp-47h]
0x180067619  sub     rsp, 0A0h
0x180067620  mov     rax, cs:__security_cookie
0x180067627  xor     rax, rsp
0x18006762a  mov     [rbp+57h+var_20], rax
0x18006762e  mov     rdi, r8
0x180067631  mov     qword ptr [r9], 0
0x180067638  lea     r8, [rbp+57h+pszFile]; unsigned __int16 **
0x18006763c  mov     [rbp+57h+pszFile], 0
0x180067644  mov     rsi, r9
0x180067647  call    ?_GetTmpMicroImagePath@CThemePack@@AEAAJPEBGPEAPEAG@Z; CThemePack::_GetTmpMicroImagePath(ushort const *,ushort * *)
0x18006764c  mov     ebx, eax
0x18006764e  test    eax, eax
0x180067650  js      loc_180067726
0x180067656  lea     rcx, [rbp+57h+var_78]
0x18006765a  call    ??0?$CComPtr@UIInitializeWithFile@@@ATL@@QEAA@XZ; ATL::CComPtr<IInitializeWithFile>::CComPtr<IInitializeWithFile>(void)
0x18006765f  lea     rcx, [rbp+57h+var_78]
0x180067663  call    ??I?$CComPtrBase@UITheme@@@ATL@@QEAAPEAPEAUITheme@@XZ; ATL::CComPtrBase<ITheme>::operator&(void)
0x180067668  mov     rcx, [rbp+57h+pszFile]; pszFile
0x18006766c  mov     r9d, 1; fCreate
0x180067672  mov     [rsp+0B0h+ppstm], rax; ppstm
0x180067677  mov     edx, 1021h; grfMode
0x18006767c  mov     [rsp+0B0h+pstmTemplate], 0; pstmTemplate
0x180067685  lea     r8d, [r9+7Fh]; dwAttributes
0x180067689  call    cs:__imp_SHCreateStreamOnFileEx
0x18006768f  mov     ebx, eax
0x180067691  test    eax, eax
0x180067693  js      short loc_180067713
0x180067695  xor     edx, edx; Val
0x180067697  lea     rcx, [rbp+57h+var_70]; void *
0x18006769b  lea     r8d, [rdx+50h]; Size
0x18006769f  call    memset_0
0x1800676a4  mov     rax, [rdi]
0x1800676a7  lea     rdx, [rbp+57h+var_70]
0x1800676ab  mov     r8d, 1
0x1800676b1  mov     rcx, rdi
0x1800676b4  mov     rax, [rax+60h]
0x1800676b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676bd  mov     ebx, eax
0x1800676bf  test    eax, eax
0x1800676c1  js      short loc_180067713
0x1800676c3  mov     rax, [rdi]
0x1800676c6  xor     r9d, r9d
0x1800676c9  mov     r8, [rbp+57h+var_60]
0x1800676cd  mov     rcx, rdi
0x1800676d0  mov     rdx, [rbp+57h+var_78]
0x1800676d4  mov     [rsp+0B0h+pstmTemplate], 0
0x1800676dd  mov     rax, [rax+38h]
0x1800676e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676e6  mov     ebx, eax
0x1800676e8  test    eax, eax
0x1800676ea  js      short loc_180067713
0x1800676ec  mov     rcx, [rbp+57h+var_78]
0x1800676f0  xor     edx, edx
0x1800676f2  mov     rax, [rcx]
0x1800676f5  mov     rax, [rax+40h]
0x1800676f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800676fe  mov     ebx, eax
0x180067700  test    eax, eax
0x180067702  js      short loc_180067713
0x180067704  mov     rcx, [rbp+57h+pszFile]; psz
0x180067708  mov     rdx, rsi; ppwsz
0x18006770b  call    cs:__imp_SHStrDupW
0x180067711  mov     ebx, eax
0x180067713  mov     rcx, [rbp+57h+pszFile]; pv
0x180067717  call    cs:__imp_CoTaskMemFree
0x18006771d  lea     rcx, [rbp+57h+var_78]
0x180067721  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x180067726  mov     eax, ebx
0x180067728  mov     rcx, [rbp+57h+var_20]
0x18006772c  xor     rcx, rsp; StackCookie
0x18006772f  call    __security_check_cookie
0x180067734  mov     rbx, [rsp+0B0h+arg_0]
0x18006773c  add     rsp, 0A0h
0x180067743  pop     rdi
0x180067744  pop     rsi
0x180067745  pop     rbp
0x180067746  retn
```
