# GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)

- ea: `0x18008f970`
- end: `0x18008fb8a`
- name: `?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z`
- size: `538`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008fce0`

## callees

- `0x180003520`
- `0x180072e08`
- `0x180072f14`
- `0x18007d000`
- `0x18008f970`
- `0x1800935fc`
- `0x18009e904`
- `0x18009ea34`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18008fb31`
- `msvcrt!_wcsicmp` at `0x18008fb31`
- `KERNEL32!GetComputerNameW` at `0x18008fa64`
- `KERNEL32!GetComputerNameW` at `0x18008fa64`
- `ole32!CoTaskMemFree` at `0x18008fae4`
- `ole32!CoTaskMemFree` at `0x18008fae4`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18008fa40`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18008fa40`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetFriendlyNameForUser", 0x7Au, 1u);
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
  ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(&ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v11;
}

```

## disassembly

```asm
0x18008f970  push    rbp
0x18008f972  push    rbx
0x18008f973  push    rsi
0x18008f974  push    rdi
0x18008f975  push    r14
0x18008f977  lea     rbp, [rsp-37h]
0x18008f97c  sub     rsp, 0E0h
0x18008f983  mov     rax, cs:__security_cookie
0x18008f98a  xor     rax, rsp
0x18008f98d  mov     [rbp+57h+var_30], rax
0x18008f991  mov     rbx, r9
0x18008f994  mov     rsi, r8
0x18008f997  mov     r9d, 1; unsigned __int16
0x18008f99d  mov     rdi, rdx
0x18008f9a0  mov     r14, rcx
0x18008f9a3  lea     rdx, aGetfriendlynam; "GetFriendlyNameForUser"
0x18008f9aa  lea     rcx, [rbp+57h+var_98]; this
0x18008f9ae  lea     r8d, [r9+79h]; unsigned __int16
0x18008f9b2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008f9b7  lea     rcx, [rbp+57h+var_58]; void *
0x18008f9bb  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18008f9c0  xor     eax, eax
0x18008f9c2  mov     [rbp+57h+nSize], 10h
0x18008f9c9  mov     [rbp+57h+Buffer], ax
0x18008f9cd  xorps   xmm0, xmm0
0x18008f9d0  mov     [rbp+57h+pv], rax
0x18008f9d4  mov     eax, 83h
0x18008f9d9  movups  xmmword ptr [rbp+57h+var_4E], xmm0
0x18008f9dd  movups  xmmword ptr [rbp+57h+var_4E+0Eh], xmm0
0x18008f9e1  test    rbx, rbx
0x18008f9e4  jnz     short loc_18008F9F6
0x18008f9e6  mov     [rbp+57h+var_98], 80070057h
0x18008f9ed  mov     [rbp+57h+var_92], ax
0x18008f9f1  jmp     loc_18008FAE0
0x18008f9f6  mov     [rbp+57h+var_94], ax
0x18008f9fa  mov     eax, 84h
0x18008f9ff  test    rdi, rdi
0x18008fa02  jz      short loc_18008F9E6
0x18008fa04  mov     [rbp+57h+var_94], ax
0x18008fa08  test    rsi, rsi
0x18008fa0b  jnz     short loc_18008FA14
0x18008fa0d  mov     eax, 85h
0x18008fa12  jmp     short loc_18008F9E6
0x18008fa14  mov     eax, 86h
0x18008fa19  mov     [rbp+57h+var_98], 0
0x18008fa20  mov     [rbp+57h+var_94], ax
0x18008fa24  lea     r9, _GUID_d550d193_668c_47e2_a512_fbed58fd82bc; riid
0x18008fa2b  lea     rax, [rbp+57h+var_58]
0x18008fa2f  xor     r8d, r8d; pUnkOuter
0x18008fa32  lea     rdx, CLSID_SidResolver; pclsid
0x18008fa39  mov     [rsp+100h+ppv], rax; ppv
0x18008fa3e  xor     ecx, ecx; pszCLSID
0x18008fa40  call    cs:__imp_SHCoCreateInstance
0x18008fa47  nop     dword ptr [rax+rax+00h]
0x18008fa4c  mov     [rbp+57h+var_98], eax
0x18008fa4f  test    eax, eax
0x18008fa51  mov     eax, 88h
0x18008fa56  js      short loc_18008F9ED
0x18008fa58  lea     rdx, [rbp+57h+nSize]; nSize
0x18008fa5c  mov     [rbp+57h+var_94], ax
0x18008fa60  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18008fa64  call    cs:__imp_GetComputerNameW
0x18008fa6b  nop     dword ptr [rax+rax+00h]
0x18008fa70  test    eax, eax
0x18008fa72  jnz     short loc_18008FA86
0x18008fa74  call    GetLastFailureAsHRESULT
0x18008fa79  mov     [rbp+57h+var_98], eax
0x18008fa7c  mov     eax, 8Ah
0x18008fa81  jmp     loc_18008F9ED
0x18008fa86  mov     rcx, [rbp+57h+var_58]
0x18008fa8a  lea     rdx, [rbp+57h+pv]
0x18008fa8e  mov     eax, 8Ah
0x18008fa93  mov     [rbp+57h+var_98], 0
0x18008fa9a  mov     [rbp+57h+var_94], ax
0x18008fa9e  mov     r9d, 20000002h
0x18008faa4  mov     [rsp+100h+ppv], rdx
0x18008faa9  mov     r8, r14
0x18008faac  mov     rax, [rcx]
0x18008faaf  lea     rdx, [rbp+57h+Buffer]
0x18008fab3  mov     rax, [rax+18h]
0x18008fab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fabc  test    eax, eax
0x18008fabe  js      short loc_18008FB2A
0x18008fac0  mov     rdx, [rbp+57h+pv]; unsigned __int16 *
0x18008fac4  mov     rcx, rbx; this
0x18008fac7  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008facc  mov     [rbp+57h+var_98], eax
0x18008facf  test    eax, eax
0x18008fad1  mov     eax, 90h
0x18008fad6  js      loc_18008F9ED
0x18008fadc  mov     [rbp+57h+var_94], ax
0x18008fae0  mov     rcx, [rbp+57h+pv]; pv
0x18008fae4  call    cs:__imp_CoTaskMemFree
0x18008faeb  nop     dword ptr [rax+rax+00h]
0x18008faf0  mov     [rbp+57h+pv], 0
0x18008faf8  mov     ebx, [rbp+57h+var_98]
0x18008fafb  lea     rcx, [rbp+57h+var_58]
0x18008faff  call    ??1?$CComPtr@UIResolveSidToUserName@@@ATL@@QEAA@XZ; ATL::CComPtr<IResolveSidToUserName>::~CComPtr<IResolveSidToUserName>(void)
0x18008fb04  lea     rcx, [rbp+57h+var_98]; this
0x18008fb08  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008fb0d  mov     eax, ebx
0x18008fb0f  mov     rcx, [rbp+57h+var_30]
0x18008fb13  xor     rcx, rsp; StackCookie
0x18008fb16  call    __security_check_cookie
0x18008fb1b  add     rsp, 0E0h
0x18008fb22  pop     r14
0x18008fb24  pop     rdi
0x18008fb25  pop     rsi
0x18008fb26  pop     rbx
0x18008fb27  pop     rbp
0x18008fb28  retn
0x18008fb2a  lea     rdx, [rbp+57h+Buffer]; String2
0x18008fb2e  mov     rcx, rdi; String1
0x18008fb31  call    cs:__imp__wcsicmp
0x18008fb38  nop     dword ptr [rax+rax+00h]
0x18008fb3d  mov     rcx, rbx; this
0x18008fb40  test    eax, eax
0x18008fb42  jz      short loc_18008FB73
0x18008fb44  mov     [rsp+100h+var_D8], 0; unsigned __int16 *
0x18008fb4d  xor     r9d, r9d; unsigned __int16 *
0x18008fb50  mov     r8, rsi; unsigned __int16 *
0x18008fb53  mov     [rsp+100h+ppv], 0; unsigned __int16 *
0x18008fb5c  mov     rdx, rdi; unsigned __int16 *
0x18008fb5f  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18008fb64  mov     [rbp+57h+var_98], eax
0x18008fb67  test    eax, eax
0x18008fb69  mov     eax, 97h
0x18008fb6e  jmp     loc_18008FAD6
0x18008fb73  mov     rdx, rsi; unsigned __int16 *
0x18008fb76  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18008fb7b  mov     [rbp+57h+var_98], eax
0x18008fb7e  test    eax, eax
0x18008fb80  mov     eax, 9Bh
0x18008fb85  jmp     loc_18008FAD6
```
