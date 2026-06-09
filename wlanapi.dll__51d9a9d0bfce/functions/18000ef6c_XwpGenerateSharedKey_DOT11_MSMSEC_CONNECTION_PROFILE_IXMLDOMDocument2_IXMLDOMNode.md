# XwpGenerateSharedKey(DOT11_MSMSEC_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x18000ef6c`
- end: `0x18000f15c`
- name: `?XwpGenerateSharedKey@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `496`
- prototype: `unsigned int(struct DOT11_MSMSEC_CONNECTION_PROFILE *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9e0`

## callees

- `0x18000dea8`
- `0x18000ec9c`
- `0x18000ef6c`
- `0x180018e1c`
- `0x180019370`
- `0x18004e46c`
- `0x18004e4a4`
- `0x18004e558`
- `0x18004e6ec`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000f087`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000f0cf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000f087`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000f0cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0d9`

## string_xrefs

- `0x18000efcb`: `http://www.microsoft.com/networking/WLAN/profile/v1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XwpGenerateSharedKey(
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  unsigned int v5; // edi
  struct IXMLDOMNode *v6; // rbx
  struct IXMLDOMNode *v7; // r11
  int v8; // eax
  int v9; // edi
  DWORD v10; // eax
  WCHAR *lpWideCharStr; // r14
  int v12; // eax
  DWORD LastError; // eax
  struct IXMLDOMNode **cchWideChar; // [rsp+28h] [rbp-50h]
  struct IXMLDOMNode **cchWideChara; // [rsp+28h] [rbp-50h]
  struct IXMLDOMNode **v17; // [rsp+30h] [rbp-48h]
  struct IXMLDOMNode **v18; // [rsp+38h] [rbp-40h]
  struct IXMLDOMNode *v19; // [rsp+80h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  v19 = 0;
  if ( (unsigned int)AuthCipher1xRequiresKeyMaterial(
                       **((unsigned int **)a1 + 3),
                       *(unsigned int *)(*((_QWORD *)a1 + 3) + 4LL),
                       *((unsigned int *)a1 + 8)) )
  {
    if ( *((_DWORD *)a1 + 16) )
    {
      if ( *((_QWORD *)a1 + 9) )
      {
        v5 = XcAddChildElement(
               a2,
               v7,
               (OLECHAR *)L"sharedKey",
               (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
               0,
               &v19);
        v6 = v19;
        if ( !v5 )
        {
          v5 = XcAddChildElementEnum(
                 a2,
                 v19,
                 (OLECHAR *)L"keyType",
                 (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                 (*(_DWORD *)a1 >> 1) & 1,
                 (const struct _XC_STRING_VALUE_MAPPING *)&off_180063130,
                 2u,
                 v18);
          if ( !v5 )
          {
            v5 = XcAddChildElementBoolean(
                   a2,
                   v6,
                   L"protected",
                   L"http://www.microsoft.com/networking/WLAN/profile/v1",
                   *(_DWORD *)a1 & 1,
                   cchWideChar);
            if ( !v5 )
            {
              if ( (*(_BYTE *)a1 & 3) == 2 )
              {
                v8 = MultiByteToWideChar(0xFDE9u, 0, *((LPCCH *)a1 + 9), *((_DWORD *)a1 + 16), 0, v5);
                v9 = v8;
                if ( v8 )
                {
                  lpWideCharStr = (WCHAR *)Xc_Process_user_allocate(2LL * v8 + 2);
                  if ( lpWideCharStr )
                  {
                    v12 = MultiByteToWideChar(
                            0xFDE9u,
                            0,
                            *((LPCCH *)a1 + 9),
                            *((_DWORD *)a1 + 16),
                            lpWideCharStr,
                            v9 + 1);
                    if ( v12 )
                    {
                      lpWideCharStr[v12] = 0;
                      LastError = XcAddChildElementFullString(
                                    a2,
                                    v6,
                                    (OLECHAR *)L"keyMaterial",
                                    (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                                    lpWideCharStr,
                                    cchWideChara);
                    }
                    else
                    {
                      LastError = GetLastError();
                    }
                    v5 = LastError;
                    Xc_Process_user_free(lpWideCharStr);
                    goto LABEL_17;
                  }
                }
                v10 = GetLastError();
              }
              else
              {
                v10 = XcAddChildElementHexBinary(
                        a2,
                        v6,
                        (OLECHAR *)L"keyMaterial",
                        (OLECHAR *)L"http://www.microsoft.com/networking/WLAN/profile/v1",
                        *((unsigned __int8 **)a1 + 9),
                        *((_DWORD *)a1 + 16),
                        v17);
              }
              v5 = v10;
            }
          }
        }
      }
    }
  }
LABEL_17:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  return v5;
}

```

## disassembly

```asm
0x18000ef6c  mov     rax, rsp
0x18000ef6f  push    rbx
0x18000ef70  push    rbp
0x18000ef71  push    rsi
0x18000ef72  push    rdi
0x18000ef73  push    r12
0x18000ef75  push    r14
0x18000ef77  sub     rsp, 48h
0x18000ef7b  mov     r11, r8
0x18000ef7e  mov     rbp, rdx
0x18000ef81  mov     rsi, rcx
0x18000ef84  xor     edi, edi
0x18000ef86  xor     ebx, ebx
0x18000ef88  mov     [rax+8], rbx
0x18000ef8c  mov     rcx, [rcx+18h]
0x18000ef90  mov     r8d, [rsi+20h]
0x18000ef94  mov     edx, [rcx+4]
0x18000ef97  mov     ecx, [rcx]
0x18000ef99  call    AuthCipher1xRequiresKeyMaterial
0x18000ef9e  test    eax, eax
0x18000efa0  jz      loc_18000F138
0x18000efa6  cmp     [rsi+40h], ebx
0x18000efa9  jz      loc_18000F138
0x18000efaf  cmp     [rsi+48h], rbx
0x18000efb3  jz      loc_18000F138
0x18000efb9  lea     rax, [rsp+78h+arg_0]
0x18000efc1  mov     qword ptr [rsp+78h+cchWideChar], rax; struct IXMLDOMNode **
0x18000efc6  mov     [rsp+78h+lpWideCharStr], rbx; OLECHAR *
0x18000efcb  lea     r12, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18000efd2  mov     r9, r12; OLECHAR *
0x18000efd5  lea     r8, aSharedkey; "sharedKey"
0x18000efdc  mov     rdx, r11; struct IXMLDOMNode *
0x18000efdf  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000efe2  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000efe7  mov     edi, eax
0x18000efe9  mov     rbx, [rsp+78h+arg_0]
0x18000eff1  test    eax, eax
0x18000eff3  jnz     loc_18000F138
0x18000eff9  mov     eax, [rsi]
0x18000effb  shr     eax, 1
0x18000effd  and     eax, 1
0x18000f000  mov     dword ptr [rsp+78h+var_48], 2; struct IXMLDOMNode **
0x18000f008  lea     rcx, off_180063130; "networkKey"
0x18000f00f  mov     qword ptr [rsp+78h+cchWideChar], rcx; struct IXMLDOMNode **
0x18000f014  mov     dword ptr [rsp+78h+lpWideCharStr], eax; unsigned int
0x18000f018  mov     r9, r12; OLECHAR *
0x18000f01b  lea     r8, aKeytype; "keyType"
0x18000f022  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f025  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f028  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x18000f02d  mov     edi, eax
0x18000f02f  test    eax, eax
0x18000f031  jnz     loc_18000F138
0x18000f037  mov     eax, [rsi]
0x18000f039  and     eax, 1
0x18000f03c  mov     dword ptr [rsp+78h+lpWideCharStr], eax; int
0x18000f040  mov     r9, r12; unsigned __int16 *
0x18000f043  lea     r8, aProtected; "protected"
0x18000f04a  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f04d  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f050  call    ?XcAddChildElementBoolean@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2HPEAPEAU2@@Z; XcAddChildElementBoolean(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,int,IXMLDOMNode * *)
0x18000f055  mov     edi, eax
0x18000f057  test    eax, eax
0x18000f059  jnz     loc_18000F138
0x18000f05f  mov     eax, [rsi]
0x18000f061  and     al, 3
0x18000f063  cmp     al, 2
0x18000f065  jnz     loc_18000F111
0x18000f06b  mov     [rsp+78h+cchWideChar], edi; cchWideChar
0x18000f06f  mov     [rsp+78h+lpWideCharStr], 0; lpWideCharStr
0x18000f078  mov     r9d, [rsi+40h]; cbMultiByte
0x18000f07c  mov     r8, [rsi+48h]; lpMultiByteStr
0x18000f080  xor     edx, edx; dwFlags
0x18000f082  mov     ecx, 0FDE9h; CodePage
0x18000f087  call    cs:__imp_MultiByteToWideChar
0x18000f08d  movsxd  rdi, eax
0x18000f090  test    eax, eax
0x18000f092  jnz     short loc_18000F09F
0x18000f094  call    cs:__imp_GetLastError
0x18000f09a  jmp     loc_18000F136
0x18000f09f  lea     rcx, ds:2[rdi*2]; dwBytes
0x18000f0a7  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18000f0ac  mov     r14, rax
0x18000f0af  test    rax, rax
0x18000f0b2  jz      short loc_18000F094
0x18000f0b4  lea     eax, [rdi+1]
0x18000f0b7  mov     [rsp+78h+cchWideChar], eax; struct IXMLDOMNode **
0x18000f0bb  mov     [rsp+78h+lpWideCharStr], r14; lpWideCharStr
0x18000f0c0  mov     r9d, [rsi+40h]; cbMultiByte
0x18000f0c4  mov     r8, [rsi+48h]; lpMultiByteStr
0x18000f0c8  xor     edx, edx; dwFlags
0x18000f0ca  mov     ecx, 0FDE9h; CodePage
0x18000f0cf  call    cs:__imp_MultiByteToWideChar
0x18000f0d5  test    eax, eax
0x18000f0d7  jnz     short loc_18000F0E1
0x18000f0d9  call    cs:__imp_GetLastError
0x18000f0df  jmp     short loc_18000F105
0x18000f0e1  movsxd  rcx, eax
0x18000f0e4  xor     eax, eax
0x18000f0e6  mov     [r14+rcx*2], ax
0x18000f0eb  mov     [rsp+78h+lpWideCharStr], r14; lpString2
0x18000f0f0  mov     r9, r12; OLECHAR *
0x18000f0f3  lea     r8, aKeymaterial; "keyMaterial"
0x18000f0fa  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f0fd  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f100  call    ?XcAddChildElementFullString@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElementFullString(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f105  mov     edi, eax
0x18000f107  mov     rcx, r14; lpMem
0x18000f10a  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18000f10f  jmp     short loc_18000F138
0x18000f111  mov     eax, [rsi+40h]
0x18000f114  mov     [rsp+78h+cchWideChar], eax; unsigned int
0x18000f118  mov     rax, [rsi+48h]
0x18000f11c  mov     [rsp+78h+lpWideCharStr], rax; unsigned __int8 *
0x18000f121  mov     r9, r12; OLECHAR *
0x18000f124  lea     r8, aKeymaterial; "keyMaterial"
0x18000f12b  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f12e  mov     rcx, rbp; struct IXMLDOMDocument2 *
0x18000f131  call    ?XcAddChildElementHexBinary@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2PEAEKPEAPEAU2@@Z; XcAddChildElementHexBinary(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,uchar *,ulong,IXMLDOMNode * *)
0x18000f136  mov     edi, eax
0x18000f138  test    rbx, rbx
0x18000f13b  jz      short loc_18000F14D
0x18000f13d  mov     rax, [rbx]
0x18000f140  mov     rcx, rbx
0x18000f143  mov     rax, [rax+10h]
0x18000f147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f14c  nop
0x18000f14d  mov     eax, edi
0x18000f14f  add     rsp, 48h
0x18000f153  pop     r14
0x18000f155  pop     r12
0x18000f157  pop     rdi
0x18000f158  pop     rsi
0x18000f159  pop     rbp
0x18000f15a  pop     rbx
0x18000f15b  retn
```
