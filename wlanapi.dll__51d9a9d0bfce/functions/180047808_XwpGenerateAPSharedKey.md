# XwpGenerateAPSharedKey

- ea: `0x180047808`
- end: `0x1800479c9`
- name: `XwpGenerateAPSharedKey`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047760`

## callees

- `0x180009654`
- `0x18000dea8`
- `0x18000ec9c`
- `0x180019370`
- `0x180047808`
- `0x18004e46c`
- `0x18004e4a4`
- `0x18004e6ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800478f7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047937`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800478f7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180047937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047941`

## string_xrefs

- `0x18004783d`: `http://www.microsoft.com/networking/WLANAP/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XwpGenerateAPSharedKey(__int64 a1, struct IXMLDOMDocument2 *a2, struct IXMLDOMNode *a3)
{
  unsigned int v5; // edi
  int v6; // eax
  DWORD LastError; // eax
  WCHAR *lpWideCharStr; // rax
  OLECHAR *v9; // r14
  int v10; // eax
  unsigned int v11; // eax
  struct IXMLDOMNode **cchWideChar; // [rsp+28h] [rbp-30h]
  struct IXMLDOMNode **v14; // [rsp+30h] [rbp-28h]
  struct IXMLDOMNode **v15; // [rsp+38h] [rbp-20h]
  struct IXMLDOMNode *v16; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  v5 = XcAddChildElement(
         a2,
         a3,
         (OLECHAR *)L"sharedKey",
         (OLECHAR *)L"http://www.microsoft.com/networking/WLANAP/profile/v1",
         0,
         &v16);
  if ( v5 )
    goto LABEL_14;
  v5 = XcAddChildElementEnum(
         a2,
         v16,
         (OLECHAR *)L"keyType",
         (OLECHAR *)L"http://www.microsoft.com/networking/WLANAP/profile/v1",
         (*(_DWORD *)a1 >> 1) & 1,
         (const struct _XC_STRING_VALUE_MAPPING *)&off_18006AA70,
         2u,
         v15);
  if ( v5 )
    goto LABEL_14;
  v5 = XcAddChildElementBoolean(
         a2,
         v16,
         L"protected",
         L"http://www.microsoft.com/networking/WLANAP/profile/v1",
         *(_DWORD *)a1 & 1,
         cchWideChar);
  if ( v5 )
    goto LABEL_14;
  if ( (*(_BYTE *)a1 & 3) != 2 )
  {
    LastError = XcAddChildElementHexBinary(
                  a2,
                  v16,
                  (OLECHAR *)L"keyMaterial",
                  (OLECHAR *)L"http://www.microsoft.com/networking/WLANAP/profile/v1",
                  *(unsigned __int8 **)(a1 + 72),
                  *(_DWORD *)(a1 + 64),
                  v14);
    goto LABEL_13;
  }
  v6 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)(a1 + 72), *(_DWORD *)(a1 + 64), 0, 0);
  if ( !v6 || (lpWideCharStr = (WCHAR *)Xc_Process_user_allocate(2LL * (v6 + 1)), (v9 = lpWideCharStr) == 0) )
  {
    LastError = GetLastError();
LABEL_13:
    v5 = LastError;
    goto LABEL_14;
  }
  v10 = MultiByteToWideChar(0xFDE9u, 0, *(LPCCH *)(a1 + 72), *(_DWORD *)(a1 + 64), lpWideCharStr, *(_DWORD *)(a1 + 64));
  if ( v10 )
  {
    v9[v10] = 0;
    v11 = XcAddChildElement(
            a2,
            v16,
            (OLECHAR *)L"keyMaterial",
            (OLECHAR *)L"http://www.microsoft.com/networking/WLANAP/profile/v1",
            v9,
            0);
  }
  else
  {
    v11 = GetLastError();
  }
  v5 = v11;
  Xc_Process_user_free(v9);
LABEL_14:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v16);
  return v5;
}

```

## disassembly

```asm
0x180047808  mov     r11, rsp
0x18004780b  mov     [r11+8], rbp
0x18004780f  mov     [r11+10h], rsi
0x180047813  push    rdi
0x180047814  push    r12
0x180047816  push    r14
0x180047818  sub     rsp, 40h
0x18004781c  mov     rax, r8
0x18004781f  mov     rbp, rdx
0x180047822  mov     rsi, rcx
0x180047825  mov     qword ptr [r11+20h], 0
0x18004782d  lea     rcx, [r11+20h]
0x180047831  mov     [r11-30h], rcx
0x180047835  mov     qword ptr [r11-38h], 0
0x18004783d  lea     r12, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WLA"...
0x180047844  mov     r9, r12; OLECHAR *
0x180047847  lea     r8, aSharedkey; "sharedKey"
0x18004784e  mov     rdx, rax; struct IXMLDOMNode *
0x180047851  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x180047854  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180047859  mov     edi, eax
0x18004785b  test    eax, eax
0x18004785d  jnz     loc_1800479A9
0x180047863  mov     eax, [rsi]
0x180047865  shr     eax, 1
0x180047867  and     eax, 1
0x18004786a  mov     dword ptr [rsp+58h+var_28], 2; struct IXMLDOMNode **
0x180047872  lea     rcx, off_18006AA70; "networkKey"
0x180047879  mov     qword ptr [rsp+58h+cchWideChar], rcx; struct IXMLDOMNode **
0x18004787e  mov     dword ptr [rsp+58h+lpWideCharStr], eax; unsigned int
0x180047882  mov     r9, r12; OLECHAR *
0x180047885  lea     r8, aKeytype; "keyType"
0x18004788c  mov     rdx, [rsp+58h+arg_18]; struct IXMLDOMNode *
0x180047891  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x180047894  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180047899  mov     edi, eax
0x18004789b  test    eax, eax
0x18004789d  jnz     loc_1800479A9
0x1800478a3  mov     eax, [rsi]
0x1800478a5  and     eax, 1
0x1800478a8  mov     dword ptr [rsp+58h+lpWideCharStr], eax; int
0x1800478ac  mov     r9, r12; unsigned __int16 *
0x1800478af  lea     r8, aProtected; "protected"
0x1800478b6  mov     rdx, [rsp+58h+arg_18]; struct IXMLDOMNode *
0x1800478bb  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x1800478be  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x1800478c3  mov     edi, eax
0x1800478c5  test    eax, eax
0x1800478c7  jnz     loc_1800479A9
0x1800478cd  mov     eax, [rsi]
0x1800478cf  and     al, 3
0x1800478d1  cmp     al, 2
0x1800478d3  jnz     loc_180047980
0x1800478d9  mov     [rsp+58h+cchWideChar], edi; cchWideChar
0x1800478dd  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x1800478e6  mov     r9d, [rsi+40h]; cbMultiByte
0x1800478ea  mov     r8, [rsi+48h]; lpMultiByteStr
0x1800478ee  xor     edx, edx; dwFlags
0x1800478f0  mov     edi, 0FDE9h
0x1800478f5  mov     ecx, edi; CodePage
0x1800478f7  call    cs:__imp_MultiByteToWideChar
0x1800478fd  test    eax, eax
0x1800478ff  jnz     short loc_18004790C
0x180047901  call    cs:__imp_GetLastError
0x180047907  jmp     loc_1800479A7
0x18004790c  inc     eax
0x18004790e  movsxd  rcx, eax
0x180047911  add     rcx, rcx; dwBytes
0x180047914  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x180047919  mov     r14, rax
0x18004791c  test    rax, rax
0x18004791f  jz      short loc_180047901
0x180047921  mov     r9d, [rsi+40h]; cbMultiByte
0x180047925  mov     [rsp+58h+cchWideChar], r9d; cchWideChar
0x18004792a  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18004792f  mov     r8, [rsi+48h]; lpMultiByteStr
0x180047933  xor     edx, edx; dwFlags
0x180047935  mov     ecx, edi; CodePage
0x180047937  call    cs:__imp_MultiByteToWideChar
0x18004793d  test    eax, eax
0x18004793f  jnz     short loc_180047949
0x180047941  call    cs:__imp_GetLastError
0x180047947  jmp     short loc_180047974
0x180047949  movsxd  rcx, eax
0x18004794c  xor     eax, eax
0x18004794e  mov     [r14+rcx*2], ax
0x180047953  mov     qword ptr [rsp+58h+cchWideChar], rax; struct IXMLDOMNode **
0x180047958  mov     [rsp+58h+lpWideCharStr], r14; OLECHAR *
0x18004795d  mov     r9, r12; OLECHAR *
0x180047960  lea     r8, aKeymaterial; "keyMaterial"
0x180047967  mov     rdx, [rsp+58h+arg_18]; struct IXMLDOMNode *
0x18004796c  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18004796f  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180047974  mov     edi, eax
0x180047976  mov     rcx, r14; lpMem
0x180047979  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18004797e  jmp     short loc_1800479A9
0x180047980  mov     eax, [rsi+40h]
0x180047983  mov     [rsp+58h+cchWideChar], eax; unsigned int
0x180047987  mov     rax, [rsi+48h]
0x18004798b  mov     [rsp+58h+lpWideCharStr], rax; unsigned __int8 *
0x180047990  mov     r9, r12; OLECHAR *
0x180047993  lea     r8, aKeymaterial; "keyMaterial"
0x18004799a  mov     rdx, [rsp+58h+arg_18]; struct IXMLDOMNode *
0x18004799f  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x1800479a2  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x1800479a7  mov     edi, eax
0x1800479a9  lea     rcx, [rsp+58h+arg_18]
0x1800479ae  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800479b3  mov     eax, edi
0x1800479b5  mov     rbp, [rsp+58h+arg_0]
0x1800479ba  mov     rsi, [rsp+58h+arg_8]
0x1800479bf  add     rsp, 40h
0x1800479c3  pop     r14
0x1800479c5  pop     r12
0x1800479c7  pop     rdi
0x1800479c8  retn
```
