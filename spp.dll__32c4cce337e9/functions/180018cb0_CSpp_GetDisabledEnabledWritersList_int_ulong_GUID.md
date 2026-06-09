# CSpp::_GetDisabledEnabledWritersList(int,ulong *,_GUID * *)

- ea: `0x180018cb0`
- end: `0x180018f08`
- name: `?_GetDisabledEnabledWritersList@CSpp@@AEAAJHPEAKPEAPEAU_GUID@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(CSpp *this, int, unsigned int *, struct _GUID **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e24`
- `0x180019524`

## callees

- `0x18000f8ac`
- `0x180018cb0`
- `0x18001e898`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018dc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018dc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018e22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ed6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ed6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018e00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018e00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018da5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018da5`

## string_xrefs

- `0x180018d08`: `CSpp::_GetDisabledEnabledWritersList`
- `0x180018d21`: `EnabledWriters`
- `0x180018d2f`: `DisabledWriters`

## pseudocode

```c
__int64 __fastcall CSpp::_GetDisabledEnabledWritersList(CSpp *this, int a2, unsigned int *a3, struct _GUID **a4)
{
  const WCHAR *v7; // r15
  BYTE *v8; // rdi
  __int16 v9; // ax
  __int16 v10; // ax
  LSTATUS v11; // eax
  CSpp *v12; // rcx
  unsigned int v13; // ebx
  DWORD v14; // edx
  unsigned int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  struct _GUID *v19; // [rsp+30h] [rbp-48h] BYREF
  int v20; // [rsp+38h] [rbp-40h] BYREF
  __int16 v21; // [rsp+3Ch] [rbp-3Ch]
  __int16 v22; // [rsp+3Eh] [rbp-3Ah]
  CSpp *Type; // [rsp+C0h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+60h] BYREF

  Type = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "CSpp::_GetDisabledEnabledWritersList", 6629, 1);
  hKey = 0;
  v7 = L"DisabledWriters";
  LODWORD(Type) = 0;
  if ( !a2 )
    v7 = L"EnabledWriters";
  cbData = 0;
  v25 = 0;
  v8 = 0;
  v19 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 6648;
  if ( a4 && (v21 = 6648, v9 = 6649, a3) )
  {
    v21 = 6649;
    v20 = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", 0, 0x20019u, &hKey) )
    {
      v10 = 6662;
LABEL_14:
      v20 = 1;
      v21 = v10;
      goto LABEL_32;
    }
    v8 = (BYTE *)CoTaskMemAlloc(0x400u);
    v9 = 6667;
    if ( v8 )
    {
      while ( 1 )
      {
        v21 = v9;
        v20 = 0;
        v11 = RegQueryValueExW(hKey, v7, 0, (LPDWORD)&Type, v8, &cbData);
        if ( v11 != 234 )
          break;
        v13 = SxScaledGrowth(cbData);
        CoTaskMemFree(v8);
        v8 = (BYTE *)CoTaskMemAlloc(v13);
        v9 = 6684;
        if ( !v8 )
          goto LABEL_18;
      }
      if ( v11 )
      {
        v10 = 6699;
        goto LABEL_14;
      }
      if ( (_DWORD)Type != 7 || (cbData & 1) != 0 )
      {
        v10 = 6711;
        goto LABEL_14;
      }
      v14 = cbData >> 1;
      if ( cbData >> 1 < 3 || *(_WORD *)&v8[2 * v14 - 2] || *(_WORD *)&v8[2 * v14 - 4] )
      {
        v10 = 6726;
        goto LABEL_14;
      }
      v20 = CSpp::_SplitWriterList(v12, a2, (const unsigned __int16 *)v8, &v25, &v19);
      v9 = 6732;
      if ( v20 >= 0 )
      {
        v21 = 6732;
        *a4 = v19;
        *a3 = v25;
        goto LABEL_32;
      }
    }
    else
    {
LABEL_18:
      v20 = -2147024882;
    }
  }
  else
  {
    v20 = -2147024809;
  }
  v22 = v9;
LABEL_32:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CoTaskMemFree(v8);
  v15 = v20;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20, v16, v17);
  return v15;
}

```

## disassembly

```asm
0x180018cb0  mov     [rsp-40h+Type], rcx
0x180018cb5  push    rbp
0x180018cb6  push    rbx
0x180018cb7  push    rsi
0x180018cb8  push    rdi
0x180018cb9  push    r12
0x180018cbb  push    r13
0x180018cbd  push    r14
0x180018cbf  push    r15
0x180018cc1  mov     rbp, rsp
0x180018cc4  sub     rsp, 78h
0x180018cc8  mov     r14, r9
0x180018ccb  mov     rsi, r8
0x180018cce  mov     r12d, edx
0x180018cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180018cd8  lea     rax, WPP_GLOBAL_Control
0x180018cdf  cmp     rcx, rax
0x180018ce2  jz      short loc_180018D02
0x180018ce4  test    dword ptr [rcx+1Ch], 20000000h
0x180018ceb  jz      short loc_180018D02
0x180018ced  mov     rcx, [rcx+10h]
0x180018cf1  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180018cf8  mov     edx, 74h ; 't'
0x180018cfd  call    WPP_SF_
0x180018d02  mov     r9d, 1; unsigned __int16
0x180018d08  lea     rdx, aCsppGetdisable; "CSpp::_GetDisabledEnabledWritersList"
0x180018d0f  mov     r8d, 19E5h; unsigned __int16
0x180018d15  lea     rcx, [rbp+var_40]; this
0x180018d19  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180018d1e  xor     r13d, r13d
0x180018d21  lea     rax, ValueName; "EnabledWriters"
0x180018d28  test    r12d, r12d
0x180018d2b  mov     [rbp+hKey], r13
0x180018d2f  lea     r15, aDisabledwriter; "DisabledWriters"
0x180018d36  mov     dword ptr [rbp+Type], r13d
0x180018d3a  cmovz   r15, rax
0x180018d3e  mov     [rbp+cbData], r13d
0x180018d42  mov     [rbp+arg_10], r13d
0x180018d46  mov     edi, r13d
0x180018d49  mov     [rbp+var_48], r13
0x180018d4d  test    r14, r14
0x180018d50  jz      short loc_180018D55
0x180018d52  mov     [r14], r13
0x180018d55  test    rsi, rsi
0x180018d58  jz      short loc_180018D5D
0x180018d5a  mov     [rsi], r13d
0x180018d5d  mov     eax, 19F8h
0x180018d62  test    r14, r14
0x180018d65  jz      loc_180018EC2
0x180018d6b  mov     [rbp+var_3C], ax
0x180018d6f  mov     eax, 19F9h
0x180018d74  test    rsi, rsi
0x180018d77  jz      loc_180018EC2
0x180018d7d  mov     [rbp+var_3C], ax
0x180018d81  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180018d88  lea     rax, [rbp+hKey]
0x180018d8c  mov     [rbp+var_40], r13d
0x180018d90  mov     r9d, 20019h; samDesired
0x180018d96  mov     [rsp+78h+phkResult], rax; phkResult
0x180018d9b  xor     r8d, r8d; ulOptions
0x180018d9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018da5  call    cs:__imp_RegOpenKeyExW
0x180018dab  test    eax, eax
0x180018dad  jz      short loc_180018DC4
0x180018daf  mov     eax, 1A06h
0x180018db4  mov     [rbp+var_40], 1
0x180018dbb  mov     [rbp+var_3C], ax
0x180018dbf  jmp     loc_180018ECD
0x180018dc4  mov     ecx, 400h; cb
0x180018dc9  call    cs:__imp_CoTaskMemAlloc
0x180018dcf  mov     rdi, rax
0x180018dd2  test    rax, rax
0x180018dd5  mov     eax, 1A0Bh
0x180018dda  jz      short loc_180018E35
0x180018ddc  mov     rcx, [rbp+hKey]; hKey
0x180018de0  lea     r9, [rbp+Type]; lpType
0x180018de4  mov     [rbp+var_3C], ax
0x180018de8  xor     r8d, r8d; lpReserved
0x180018deb  lea     rax, [rbp+cbData]
0x180018def  mov     [rbp+var_40], r13d
0x180018df3  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180018df8  mov     rdx, r15; lpValueName
0x180018dfb  mov     [rsp+78h+phkResult], rdi; lpData
0x180018e00  call    cs:__imp_RegQueryValueExW
0x180018e06  cmp     eax, 0EAh
0x180018e0b  jnz     short loc_180018E41
0x180018e0d  mov     ecx, [rbp+cbData]; unsigned int
0x180018e10  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180018e15  mov     rcx, rdi; pv
0x180018e18  mov     ebx, eax
0x180018e1a  call    cs:__imp_CoTaskMemFree
0x180018e20  mov     ecx, ebx; cb
0x180018e22  call    cs:__imp_CoTaskMemAlloc
0x180018e28  mov     rdi, rax
0x180018e2b  test    rax, rax
0x180018e2e  mov     eax, 1A1Ch
0x180018e33  jnz     short loc_180018DDC
0x180018e35  mov     [rbp+var_40], 8007000Eh
0x180018e3c  jmp     loc_180018EC9
0x180018e41  test    eax, eax
0x180018e43  jz      short loc_180018E4F
0x180018e45  mov     eax, 1A2Bh
0x180018e4a  jmp     loc_180018DB4
0x180018e4f  cmp     dword ptr [rbp+Type], 7
0x180018e53  jnz     short loc_180018EB8
0x180018e55  mov     edx, [rbp+cbData]
0x180018e58  test    dl, 1
0x180018e5b  jnz     short loc_180018EB8
0x180018e5d  shr     edx, 1
0x180018e5f  cmp     edx, 3
0x180018e62  jb      short loc_180018EAE
0x180018e64  lea     eax, [rdx-1]
0x180018e67  cmp     [rdi+rax*2], r13w
0x180018e6c  jnz     short loc_180018EAE
0x180018e6e  lea     eax, [rdx-2]
0x180018e71  cmp     [rdi+rax*2], r13w
0x180018e76  jnz     short loc_180018EAE
0x180018e78  lea     rax, [rbp+var_48]
0x180018e7c  mov     r8, rdi; unsigned __int16 *
0x180018e7f  lea     r9, [rbp+arg_10]; unsigned int *
0x180018e83  mov     [rsp+78h+phkResult], rax; struct _GUID **
0x180018e88  mov     edx, r12d; int
0x180018e8b  call    ?_SplitWriterList@CSpp@@AEAAJHPEBGPEAKPEAPEAU_GUID@@@Z; CSpp::_SplitWriterList(int,ushort const *,ulong *,_GUID * *)
0x180018e90  mov     [rbp+var_40], eax
0x180018e93  test    eax, eax
0x180018e95  mov     eax, 1A4Ch
0x180018e9a  js      short loc_180018EC9
0x180018e9c  mov     [rbp+var_3C], ax
0x180018ea0  mov     rax, [rbp+var_48]
0x180018ea4  mov     [r14], rax
0x180018ea7  mov     eax, [rbp+arg_10]
0x180018eaa  mov     [rsi], eax
0x180018eac  jmp     short loc_180018ECD
0x180018eae  mov     eax, 1A46h
0x180018eb3  jmp     loc_180018DB4
0x180018eb8  mov     eax, 1A37h
0x180018ebd  jmp     loc_180018DB4
0x180018ec2  mov     [rbp+var_40], 80070057h
0x180018ec9  mov     [rbp+var_3A], ax
0x180018ecd  mov     rcx, [rbp+hKey]; hKey
0x180018ed1  test    rcx, rcx
0x180018ed4  jz      short loc_180018EE0
0x180018ed6  call    cs:__imp_RegCloseKey
0x180018edc  mov     [rbp+hKey], r13
0x180018ee0  mov     rcx, rdi; pv
0x180018ee3  call    cs:__imp_CoTaskMemFree
0x180018ee9  mov     ebx, [rbp+var_40]
0x180018eec  lea     rcx, [rbp+var_40]; this
0x180018ef0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180018ef5  mov     eax, ebx
0x180018ef7  add     rsp, 78h
0x180018efb  pop     r15
0x180018efd  pop     r14
0x180018eff  pop     r13
0x180018f01  pop     r12
0x180018f03  pop     rdi
0x180018f04  pop     rsi
0x180018f05  pop     rbx
0x180018f06  pop     rbp
0x180018f07  retn
```
