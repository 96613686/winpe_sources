# GetFriendlyNameForUser(ushort const *,ushort const *,ushort const *,CBsString *)

- ea: `0x180018d38`
- end: `0x180018f63`
- name: `?GetFriendlyNameForUser@@YAJPEBG00PEAVCBsString@@@Z`
- size: `555`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, struct CBsString *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800190bc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180018d38`
- `0x18001c58c`
- `0x18001f624`
- `0x18001fcc0`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018f0d`
- `msvcrt!_wcsicmp` at `0x180018f0d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180018e25`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180018e25`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180018e07`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180018e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ebb`

## pseudocode

```c
__int64 __fastcall GetFriendlyNameForUser(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct CBsString *a4)
{
  __int16 v8; // ax
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  _WORD *v11; // rdx
  bool v12; // sf
  unsigned int v13; // ebx
  const unsigned __int16 *v15; // r9
  _WORD *v16; // rcx
  const unsigned __int16 *v17; // [rsp+28h] [rbp-81h]
  const unsigned __int16 *v18; // [rsp+30h] [rbp-79h]
  const unsigned __int16 *v19; // [rsp+38h] [rbp-71h]
  const unsigned __int16 *v20; // [rsp+40h] [rbp-69h]
  const unsigned __int16 *v21; // [rsp+48h] [rbp-61h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-59h]
  LPVOID pv; // [rsp+60h] [rbp-49h] BYREF
  int LastFailureAsHRESULT; // [rsp+68h] [rbp-41h] BYREF
  __int16 v25; // [rsp+6Ch] [rbp-3Dh]
  __int16 v26; // [rsp+6Eh] [rbp-3Bh]
  DWORD nSize; // [rsp+A0h] [rbp-9h] BYREF
  void *ppv; // [rsp+A8h] [rbp-1h] BYREF
  WCHAR Buffer[16]; // [rsp+B0h] [rbp+7h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "GetFriendlyNameForUser", 122, 1);
  ppv = 0;
  memset(Buffer, 0, sizeof(Buffer));
  pv = 0;
  v8 = 131;
  nSize = 16;
  if ( !a4 )
    goto LABEL_2;
  v25 = 131;
  v8 = 132;
  if ( !a2 )
    goto LABEL_2;
  v25 = 132;
  if ( !a3 )
  {
    v8 = 133;
LABEL_2:
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v26 = v8;
    goto LABEL_16;
  }
  LastFailureAsHRESULT = 0;
  v25 = 134;
  LastFailureAsHRESULT = SHCoCreateInstance(0, &CLSID_SidResolver, 0, &GUID_d550d193_668c_47e2_a512_fbed58fd82bc, &ppv);
  v8 = 136;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_3;
  v25 = 136;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v8 = 138;
    goto LABEL_3;
  }
  LastFailureAsHRESULT = 0;
  v25 = 138;
  if ( (*(int (__fastcall **)(void *, WCHAR *, const unsigned __int16 *, __int64))(*(_QWORD *)ppv + 24LL))(
         ppv,
         Buffer,
         a1,
         536870914) < 0 )
  {
    if ( _wcsicmp(a2, Buffer) )
    {
      LastFailureAsHRESULT = CBsString::SetPath(
                               a4,
                               a2,
                               a3,
                               v15,
                               (const unsigned __int16 *)&pv,
                               v17,
                               v18,
                               v19,
                               v20,
                               v21,
                               v22);
      v12 = LastFailureAsHRESULT < 0;
      v8 = 151;
    }
    else
    {
      if ( *((_DWORD *)a4 + 2) )
      {
        v16 = *(_WORD **)a4;
        *((_DWORD *)a4 + 2) = 0;
        *v16 = 0;
      }
      LastFailureAsHRESULT = CBsString::Append(a4, a3);
      v12 = LastFailureAsHRESULT < 0;
      v8 = 155;
    }
  }
  else
  {
    v10 = (unsigned __int16 *)pv;
    if ( *((_DWORD *)a4 + 2) )
    {
      v11 = *(_WORD **)a4;
      *((_DWORD *)a4 + 2) = 0;
      *v11 = 0;
    }
    LastFailureAsHRESULT = CBsString::Append(a4, v10);
    v12 = LastFailureAsHRESULT < 0;
    v8 = 144;
  }
  if ( v12 )
    goto LABEL_3;
  v25 = v8;
LABEL_16:
  CoTaskMemFree(pv);
  pv = 0;
  v13 = LastFailureAsHRESULT;
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v13;
}

```

## disassembly

```asm
0x180018d38  push    rbp
0x180018d3a  push    rbx
0x180018d3b  push    rsi
0x180018d3c  push    rdi
0x180018d3d  push    r14
0x180018d3f  lea     rbp, [rsp-37h]
0x180018d44  sub     rsp, 0E0h
0x180018d4b  mov     rax, cs:__security_cookie
0x180018d52  xor     rax, rsp
0x180018d55  mov     [rbp+57h+var_30], rax
0x180018d59  mov     rbx, r9
0x180018d5c  mov     rsi, r8
0x180018d5f  mov     r9d, 1; unsigned __int16
0x180018d65  mov     rdi, rdx
0x180018d68  mov     r14, rcx
0x180018d6b  lea     rdx, aGetfriendlynam; "GetFriendlyNameForUser"
0x180018d72  lea     rcx, [rbp+57h+var_98]; this
0x180018d76  lea     r8d, [r9+79h]; unsigned __int16
0x180018d7a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018d7f  xor     eax, eax
0x180018d81  mov     [rbp+57h+var_58], 0
0x180018d89  mov     [rbp+57h+Buffer], ax
0x180018d8d  xorps   xmm0, xmm0
0x180018d90  mov     [rbp+57h+pv], rax
0x180018d94  mov     eax, 83h
0x180018d99  mov     [rbp+57h+nSize], 10h
0x180018da0  movups  xmmword ptr [rbp+57h+var_4E], xmm0
0x180018da4  movups  xmmword ptr [rbp+57h+var_4E+0Eh], xmm0
0x180018da8  test    rbx, rbx
0x180018dab  jnz     short loc_180018DBD
0x180018dad  mov     [rbp+57h+var_98], 80070057h
0x180018db4  mov     [rbp+57h+var_92], ax
0x180018db8  jmp     loc_180018EB7
0x180018dbd  mov     [rbp+57h+var_94], ax
0x180018dc1  mov     eax, 84h
0x180018dc6  test    rdi, rdi
0x180018dc9  jz      short loc_180018DAD
0x180018dcb  mov     [rbp+57h+var_94], ax
0x180018dcf  test    rsi, rsi
0x180018dd2  jnz     short loc_180018DDB
0x180018dd4  mov     eax, 85h
0x180018dd9  jmp     short loc_180018DAD
0x180018ddb  mov     eax, 86h
0x180018de0  mov     [rbp+57h+var_98], 0
0x180018de7  mov     [rbp+57h+var_94], ax
0x180018deb  lea     r9, _GUID_d550d193_668c_47e2_a512_fbed58fd82bc; riid
0x180018df2  lea     rax, [rbp+57h+var_58]
0x180018df6  xor     r8d, r8d; pUnkOuter
0x180018df9  lea     rdx, CLSID_SidResolver; pclsid
0x180018e00  mov     [rsp+100h+ppv], rax; ppv
0x180018e05  xor     ecx, ecx; pszCLSID
0x180018e07  call    cs:__imp_SHCoCreateInstance
0x180018e0d  mov     [rbp+57h+var_98], eax
0x180018e10  test    eax, eax
0x180018e12  mov     eax, 88h
0x180018e17  js      short loc_180018DB4
0x180018e19  lea     rdx, [rbp+57h+nSize]; nSize
0x180018e1d  mov     [rbp+57h+var_94], ax
0x180018e21  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x180018e25  call    cs:__imp_GetComputerNameW
0x180018e2b  test    eax, eax
0x180018e2d  jnz     short loc_180018E41
0x180018e2f  call    GetLastFailureAsHRESULT
0x180018e34  mov     [rbp+57h+var_98], eax
0x180018e37  mov     eax, 8Ah
0x180018e3c  jmp     loc_180018DB4
0x180018e41  mov     rcx, [rbp+57h+var_58]
0x180018e45  lea     rdx, [rbp+57h+pv]
0x180018e49  mov     eax, 8Ah
0x180018e4e  mov     [rbp+57h+var_98], 0
0x180018e55  mov     [rbp+57h+var_94], ax
0x180018e59  mov     r9d, 20000002h
0x180018e5f  mov     [rsp+100h+ppv], rdx; unsigned __int16 *
0x180018e64  mov     r8, r14
0x180018e67  mov     rax, [rcx]
0x180018e6a  lea     rdx, [rbp+57h+Buffer]
0x180018e6e  mov     rax, [rax+18h]
0x180018e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e77  test    eax, eax
0x180018e79  js      loc_180018F06
0x180018e7f  cmp     dword ptr [rbx+8], 0
0x180018e83  mov     rcx, [rbp+57h+pv]
0x180018e87  jz      short loc_180018E98
0x180018e89  mov     rdx, [rbx]
0x180018e8c  xor     eax, eax
0x180018e8e  mov     dword ptr [rbx+8], 0
0x180018e95  mov     [rdx], ax
0x180018e98  mov     rdx, rcx; unsigned __int16 *
0x180018e9b  mov     rcx, rbx; this
0x180018e9e  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180018ea3  mov     [rbp+57h+var_98], eax
0x180018ea6  test    eax, eax
0x180018ea8  mov     eax, 90h
0x180018ead  js      loc_180018DB4
0x180018eb3  mov     [rbp+57h+var_94], ax
0x180018eb7  mov     rcx, [rbp+57h+pv]; pv
0x180018ebb  call    cs:__imp_CoTaskMemFree
0x180018ec1  mov     [rbp+57h+pv], 0
0x180018ec9  mov     rcx, [rbp+57h+var_58]
0x180018ecd  mov     ebx, [rbp+57h+var_98]
0x180018ed0  test    rcx, rcx
0x180018ed3  jz      short loc_180018EE1
0x180018ed5  mov     rdx, [rcx]
0x180018ed8  mov     rax, [rdx+10h]
0x180018edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ee1  lea     rcx, [rbp+57h+var_98]; this
0x180018ee5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018eea  mov     eax, ebx
0x180018eec  mov     rcx, [rbp+57h+var_30]
0x180018ef0  xor     rcx, rsp; StackCookie
0x180018ef3  call    __security_check_cookie
0x180018ef8  add     rsp, 0E0h
0x180018eff  pop     r14
0x180018f01  pop     rdi
0x180018f02  pop     rsi
0x180018f03  pop     rbx
0x180018f04  pop     rbp
0x180018f05  retn
0x180018f06  lea     rdx, [rbp+57h+Buffer]; String2
0x180018f0a  mov     rcx, rdi; String1
0x180018f0d  call    cs:__imp__wcsicmp
0x180018f13  test    eax, eax
0x180018f15  jz      short loc_180018F34
0x180018f17  mov     r8, rsi; unsigned __int16 *
0x180018f1a  mov     rdx, rdi; unsigned __int16 *
0x180018f1d  mov     rcx, rbx; this
0x180018f20  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180018f25  mov     [rbp+57h+var_98], eax
0x180018f28  test    eax, eax
0x180018f2a  mov     eax, 97h
0x180018f2f  jmp     loc_180018EAD
0x180018f34  cmp     dword ptr [rbx+8], 0
0x180018f38  jz      short loc_180018F49
0x180018f3a  mov     rcx, [rbx]
0x180018f3d  xor     eax, eax
0x180018f3f  mov     dword ptr [rbx+8], 0
0x180018f46  mov     [rcx], ax
0x180018f49  mov     rdx, rsi; unsigned __int16 *
0x180018f4c  mov     rcx, rbx; this
0x180018f4f  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180018f54  mov     [rbp+57h+var_98], eax
0x180018f57  test    eax, eax
0x180018f59  mov     eax, 9Bh
0x180018f5e  jmp     loc_180018EAD
```
