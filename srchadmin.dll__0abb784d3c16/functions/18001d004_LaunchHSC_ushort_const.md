# LaunchHSC(ushort const *)

- ea: `0x18001d004`
- end: `0x18001d0fb`
- name: `?LaunchHSC@@YAJPEBG@Z`
- size: `247`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800192dc`
- `0x18001a130`
- `0x180027ef8`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x1800095c0`
- `0x18001d004`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d070`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001d070`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d04d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d04d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d0a0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d0a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d0c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d0c7`

## pseudocode

```c
__int64 __fastcall LaunchHSC(const unsigned __int16 *a1)
{
  HRESULT Instance; // edi
  OLECHAR *v3; // rbx
  LPVOID ppv[2]; // [rsp+30h] [rbp-218h] BYREF
  WCHAR Buffer[104]; // [rsp+40h] [rbp-208h] BYREF
  OLECHAR psz[144]; // [rsp+110h] [rbp-138h] BYREF

  ppv[0] = 0;
  Instance = CoCreateInstance(&CLSID_HxHelpPane, 0, 0x17u, &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee, ppv);
  if ( Instance >= 0 )
  {
    if ( LoadStringW(Globals, 0x25Bu, Buffer, 100) )
    {
      if ( StringCchPrintfW(psz, 0x8Bu, Buffer, a1) >= 0 )
      {
        v3 = SysAllocString(psz);
        if ( v3 )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv[0] + 24LL))(ppv[0], v3);
          SysFreeString(v3);
        }
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001d004  mov     [rsp+arg_8], rbx
0x18001d009  push    rdi
0x18001d00a  sub     rsp, 240h
0x18001d011  mov     rax, cs:__security_cookie
0x18001d018  xor     rax, rsp
0x18001d01b  mov     [rsp+248h+var_18], rax
0x18001d023  mov     rbx, rcx
0x18001d026  mov     [rsp+248h+var_218], 0
0x18001d02f  lea     rax, [rsp+248h+var_218]
0x18001d034  mov     [rsp+248h+ppv], rax; ppv
0x18001d039  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18001d040  xor     edx, edx; pUnkOuter
0x18001d042  lea     r8d, [rdx+17h]; dwClsContext
0x18001d046  lea     rcx, CLSID_HxHelpPane; rclsid
0x18001d04d  call    cs:__imp_CoCreateInstance
0x18001d053  mov     edi, eax
0x18001d055  test    eax, eax
0x18001d057  js      short loc_18001D0CE
0x18001d059  mov     r9d, 64h ; 'd'; cchBufferMax
0x18001d05f  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x18001d064  mov     edx, 25Bh; uID
0x18001d069  mov     rcx, cs:Globals; hInstance
0x18001d070  call    cs:__imp_LoadStringW
0x18001d076  test    eax, eax
0x18001d078  jz      short loc_18001D0CE
0x18001d07a  mov     r9, rbx
0x18001d07d  lea     r8, [rsp+248h+Buffer]; unsigned __int16 *
0x18001d082  mov     edx, 8Bh; unsigned __int64
0x18001d087  lea     rcx, [rsp+248h+psz]; unsigned __int16 *
0x18001d08f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d094  test    eax, eax
0x18001d096  js      short loc_18001D0CE
0x18001d098  lea     rcx, [rsp+248h+psz]; psz
0x18001d0a0  call    cs:__imp_SysAllocString
0x18001d0a6  mov     rbx, rax
0x18001d0a9  test    rax, rax
0x18001d0ac  jz      short loc_18001D0CE
0x18001d0ae  mov     rcx, [rsp+248h+var_218]
0x18001d0b3  mov     rdx, [rcx]
0x18001d0b6  mov     rax, [rdx+18h]
0x18001d0ba  mov     rdx, rbx
0x18001d0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0c2  mov     edi, eax
0x18001d0c4  mov     rcx, rbx; bstrString
0x18001d0c7  call    cs:__imp_SysFreeString
0x18001d0cd  nop
0x18001d0ce  lea     rcx, [rsp+248h+var_218]
0x18001d0d3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d0d8  mov     eax, edi
0x18001d0da  mov     rcx, [rsp+248h+var_18]
0x18001d0e2  xor     rcx, rsp; StackCookie
0x18001d0e5  call    __security_check_cookie
0x18001d0ea  mov     rbx, [rsp+248h+arg_8]
0x18001d0f2  add     rsp, 240h
0x18001d0f9  pop     rdi
0x18001d0fa  retn
```
