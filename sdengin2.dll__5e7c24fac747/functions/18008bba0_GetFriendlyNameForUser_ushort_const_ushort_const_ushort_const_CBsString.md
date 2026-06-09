# GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)

- ea: `0x18008bba0`
- end: `0x18008bda1`
- name: `?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z`
- size: `513`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008bef4`

## callees

- `0x180003430`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180079e1c`
- `0x18008bba0`
- `0x18008f5d0`
- `0x18009a24c`
- `0x18009a378`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008bd4e`
- `msvcrt!_wcsicmp` at `0x18008bd4e`
- `KERNEL32!GetComputerNameW` at `0x18008bc8e`
- `KERNEL32!GetComputerNameW` at `0x18008bc8e`
- `ole32!CoTaskMemFree` at `0x18008bd08`
- `ole32!CoTaskMemFree` at `0x18008bd08`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18008bc70`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18008bc70`

## pseudocode

```c
__int64 __fastcall GetFriendlyNameForUser(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CBsString *a4)
{
  __int16 v8; // ax
  __int64 v9; // rcx
  bool v10; // sf
  unsigned int v11; // ebx
  const unsigned __int16 *v13; // [rsp+30h] [rbp-79h]
  const unsigned __int16 *v14; // [rsp+38h] [rbp-71h]
  const unsigned __int16 *v15; // [rsp+40h] [rbp-69h]
  const unsigned __int16 *v16; // [rsp+48h] [rbp-61h]
  const unsigned __int16 *v17; // [rsp+50h] [rbp-59h]
  LPVOID pv; // [rsp+60h] [rbp-49h] BYREF
  HRESULT LastFailureAsHRESULT; // [rsp+68h] [rbp-41h] BYREF
  __int16 v20; // [rsp+6Ch] [rbp-3Dh]
  __int16 v21; // [rsp+6Eh] [rbp-3Bh]
  DWORD nSize; // [rsp+A0h] [rbp-9h] BYREF
  void *ppv; // [rsp+A8h] [rbp-1h] BYREF
  WCHAR Buffer[16]; // [rsp+B0h] [rbp+7h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetFriendlyNameForUser", 122, 1);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&ppv);
  nSize = 16;
  memset(Buffer, 0, sizeof(Buffer));
  pv = 0;
  v8 = 131;
  if ( !a4 )
    goto LABEL_2;
  v20 = 131;
  v8 = 132;
  if ( !a2 )
    goto LABEL_2;
  v20 = 132;
  if ( !a3 )
  {
    v8 = 133;
LABEL_2:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v20 = 134;
  LastFailureAsHRESULT = SHCoCreateInstance(0, &CLSID_SidResolver, 0, &GUID_d550d193_668c_47e2_a512_fbed58fd82bc, &ppv);
  v8 = 136;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v20 = 136;
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      LastFailureAsHRESULT = 0;
      v20 = 138;
      if ( (*(int (__fastcall **)(void *, WCHAR *, const unsigned __int16 *, __int64, LPVOID *))(*(_QWORD *)ppv + 24LL))(
             ppv,
             Buffer,
             a1,
             536870914,
             &pv) < 0 )
      {
        if ( _wcsicmp(a2, Buffer) )
        {
          LastFailureAsHRESULT = CBsString::SetPath(a4, a2, a3, 0, 0, 0, v13, v14, v15, v16, v17);
          v10 = LastFailureAsHRESULT < 0;
          v8 = 151;
        }
        else
        {
          LastFailureAsHRESULT = CBsString::Set(a4, a3);
          v10 = LastFailureAsHRESULT < 0;
          v8 = 155;
        }
      }
      else
      {
        LastFailureAsHRESULT = CBsString::Set(a4, (const unsigned __int16 *)pv);
        v10 = LastFailureAsHRESULT < 0;
        v8 = 144;
      }
      if ( !v10 )
      {
        v20 = v8;
        goto LABEL_14;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
      v8 = 138;
    }
  }
LABEL_3:
  v21 = v8;
LABEL_14:
  CoTaskMemFree(pv);
  pv = 0;
  v11 = LastFailureAsHRESULT;
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>();
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v11;
}

```

## disassembly

```asm
0x18008bba0  push    rbp
0x18008bba2  push    rbx
0x18008bba3  push    rsi
0x18008bba4  push    rdi
0x18008bba5  push    r14
0x18008bba7  lea     rbp, [rsp-37h]
0x18008bbac  sub     rsp, 0E0h
0x18008bbb3  mov     rax, cs:__security_cookie
0x18008bbba  xor     rax, rsp
0x18008bbbd  mov     [rbp+57h+var_30], rax
0x18008bbc1  mov     rbx, r9
0x18008bbc4  mov     rsi, r8
0x18008bbc7  mov     r9d, 1; unsigned __int16
0x18008bbcd  mov     rdi, rdx
0x18008bbd0  mov     r14, rcx
0x18008bbd3  lea     rdx, aGetfriendlynam; "GetFriendlyNameForUser"
0x18008bbda  lea     rcx, [rbp+57h+var_98]; this
0x18008bbde  lea     r8d, [r9+79h]; unsigned __int16
0x18008bbe2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008bbe7  lea     rcx, [rbp+57h+var_58]; void *
0x18008bbeb  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18008bbf0  xor     eax, eax
0x18008bbf2  mov     [rbp+57h+nSize], 10h
0x18008bbf9  mov     [rbp+57h+Buffer], ax
0x18008bbfd  xorps   xmm0, xmm0
0x18008bc00  mov     [rbp+57h+pv], rax
0x18008bc04  mov     eax, 83h
0x18008bc09  movups  xmmword ptr [rbp+57h+var_4E], xmm0
0x18008bc0d  movups  xmmword ptr [rbp+57h+var_4E+0Eh], xmm0
0x18008bc11  test    rbx, rbx
0x18008bc14  jnz     short loc_18008BC26
0x18008bc16  mov     [rbp+57h+var_98], 80070057h
0x18008bc1d  mov     [rbp+57h+var_92], ax
0x18008bc21  jmp     loc_18008BD04
0x18008bc26  mov     [rbp+57h+var_94], ax
0x18008bc2a  mov     eax, 84h
0x18008bc2f  test    rdi, rdi
0x18008bc32  jz      short loc_18008BC16
0x18008bc34  mov     [rbp+57h+var_94], ax
0x18008bc38  test    rsi, rsi
0x18008bc3b  jnz     short loc_18008BC44
0x18008bc3d  mov     eax, 85h
0x18008bc42  jmp     short loc_18008BC16
0x18008bc44  mov     eax, 86h
0x18008bc49  mov     [rbp+57h+var_98], 0
0x18008bc50  mov     [rbp+57h+var_94], ax
0x18008bc54  lea     r9, _GUID_d550d193_668c_47e2_a512_fbed58fd82bc; riid
0x18008bc5b  lea     rax, [rbp+57h+var_58]
0x18008bc5f  xor     r8d, r8d; pUnkOuter
0x18008bc62  lea     rdx, CLSID_SidResolver; pclsid
0x18008bc69  mov     [rsp+100h+ppv], rax; ppv
0x18008bc6e  xor     ecx, ecx; pszCLSID
0x18008bc70  call    cs:__imp_SHCoCreateInstance
0x18008bc76  mov     [rbp+57h+var_98], eax
0x18008bc79  test    eax, eax
0x18008bc7b  mov     eax, 88h
0x18008bc80  js      short loc_18008BC1D
0x18008bc82  lea     rdx, [rbp+57h+nSize]; nSize
0x18008bc86  mov     [rbp+57h+var_94], ax
0x18008bc8a  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18008bc8e  call    cs:__imp_GetComputerNameW
0x18008bc94  test    eax, eax
0x18008bc96  jnz     short loc_18008BCAA
0x18008bc98  call    GetLastFailureAsHRESULT
0x18008bc9d  mov     [rbp+57h+var_98], eax
0x18008bca0  mov     eax, 8Ah
0x18008bca5  jmp     loc_18008BC1D
0x18008bcaa  mov     rcx, [rbp+57h+var_58]
0x18008bcae  lea     rdx, [rbp+57h+pv]
0x18008bcb2  mov     eax, 8Ah
0x18008bcb7  mov     [rbp+57h+var_98], 0
0x18008bcbe  mov     [rbp+57h+var_94], ax
0x18008bcc2  mov     r9d, 20000002h
0x18008bcc8  mov     [rsp+100h+ppv], rdx
0x18008bccd  mov     r8, r14
0x18008bcd0  mov     rax, [rcx]
0x18008bcd3  lea     rdx, [rbp+57h+Buffer]
0x18008bcd7  mov     rax, [rax+18h]
0x18008bcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bce0  test    eax, eax
0x18008bce2  js      short loc_18008BD47
0x18008bce4  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18008bce8  mov     rcx, rbx; this
0x18008bceb  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008bcf0  mov     [rbp+57h+var_98], eax
0x18008bcf3  test    eax, eax
0x18008bcf5  mov     eax, 90h
0x18008bcfa  js      loc_18008BC1D
0x18008bd00  mov     [rbp+57h+var_94], ax
0x18008bd04  mov     rcx, [rbp+57h+pv]; pv
0x18008bd08  call    cs:__imp_CoTaskMemFree
0x18008bd0e  mov     [rbp+57h+pv], 0
0x18008bd16  mov     ebx, [rbp+57h+var_98]
0x18008bd19  lea     rcx, [rbp+57h+var_58]
0x18008bd1d  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x18008bd22  lea     rcx, [rbp+57h+var_98]; this
0x18008bd26  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008bd2b  mov     eax, ebx
0x18008bd2d  mov     rcx, [rbp+57h+var_30]
0x18008bd31  xor     rcx, rsp; StackCookie
0x18008bd34  call    __security_check_cookie
0x18008bd39  add     rsp, 0E0h
0x18008bd40  pop     r14
0x18008bd42  pop     rdi
0x18008bd43  pop     rsi
0x18008bd44  pop     rbx
0x18008bd45  pop     rbp
0x18008bd46  retn
0x18008bd47  lea     rdx, [rbp+57h+Buffer]; String2
0x18008bd4b  mov     rcx, rdi; String1
0x18008bd4e  call    cs:__imp__wcsicmp
0x18008bd54  mov     rcx, rbx; this
0x18008bd57  test    eax, eax
0x18008bd59  jz      short loc_18008BD8A
0x18008bd5b  mov     [rsp+100h+var_D8], 0; unsigned __int16 *
0x18008bd64  xor     r9d, r9d; unsigned __int16 *
0x18008bd67  mov     r8, rsi; unsigned __int16 *
0x18008bd6a  mov     [rsp+100h+ppv], 0; unsigned __int16 *
0x18008bd73  mov     rdx, rdi; unsigned __int16 *
0x18008bd76  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18008bd7b  mov     [rbp+57h+var_98], eax
0x18008bd7e  test    eax, eax
0x18008bd80  mov     eax, 97h
0x18008bd85  jmp     loc_18008BCFA
0x18008bd8a  mov     rdx, rsi; unsigned __int16 *
0x18008bd8d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008bd92  mov     [rbp+57h+var_98], eax
0x18008bd95  test    eax, eax
0x18008bd97  mov     eax, 9Bh
0x18008bd9c  jmp     loc_18008BCFA
```
