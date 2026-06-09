# CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)

- ea: `0x140007e30`
- end: `0x140008367`
- name: `?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z`
- size: `1335`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int, PWSTR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140007510`

## callees

- `0x140007e30`
- `0x140008370`
- `0x140008870`
- `0x14000fb30`
- `0x14003a544`
- `0x140041c34`
- `0x140053720`
- `0x14005f3c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ed2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400080eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400082b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ed2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400080eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400082b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000805d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008297`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000832b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009cfdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000805d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008297`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000832b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009cfdf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007f37`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007f37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007eab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007eab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000833b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009cff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000833b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009cff6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140007fa9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140007fe4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000801f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140007fa9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140007fe4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000801f`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140008170`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x140008170`
- `ntdll!RtlInitUnicodeStringEx` at `0x140008133`
- `ntdll!RtlInitUnicodeStringEx` at `0x140008133`

## string_xrefs

- `0x140007ffb`: `Os2LibPath`
- `0x140007fc0`: `LibPath`

## pseudocode

```c
__int64 __fastcall CUser::LoadUserEnvironmentFromRegistry(__int64 a1, const WCHAR *a2, int a3, PWSTR *a4)
{
  int v4; // esi
  WCHAR *v6; // rdi
  WCHAR *v7; // r12
  DWORD v8; // r14d
  unsigned int v9; // r15d
  WCHAR *v10; // rax
  __int64 v11; // r9
  WCHAR *lpData; // rsi
  int v13; // eax
  int v14; // r9d
  WCHAR *v15; // r13
  NTSTATUS v16; // eax
  __int64 v17; // r13
  unsigned __int16 *v18; // rax
  DWORD Type; // [rsp+40h] [rbp-2D8h] BYREF
  ULONG Length; // [rsp+44h] [rbp-2D4h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-2D0h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-2CCh] BYREF
  int v24; // [rsp+50h] [rbp-2C8h]
  PWSTR *Environment; // [rsp+58h] [rbp-2C0h]
  HKEY hKey; // [rsp+60h] [rbp-2B8h] BYREF
  int v27; // [rsp+68h] [rbp-2B0h]
  WCHAR *v28; // [rsp+70h] [rbp-2A8h]
  WCHAR *v29; // [rsp+78h] [rbp-2A0h]
  WCHAR *v30; // [rsp+80h] [rbp-298h]
  struct _UNICODE_STRING Destination; // [rsp+88h] [rbp-290h] BYREF
  DWORD v32; // [rsp+98h] [rbp-280h]
  __int64 v33; // [rsp+A0h] [rbp-278h]
  _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-270h] BYREF
  WCHAR ValueName[264]; // [rsp+C0h] [rbp-258h] BYREF

  Environment = a4;
  v24 = a3;
  v4 = (int)a2;
  v33 = a1;
  v6 = 0;
  v29 = 0;
  v7 = 0;
  cchValueName = 260;
  cbData = 0;
  Type = 0;
  v8 = 0;
  hKey = 0;
  v9 = RegOpenKeyExW(*(HKEY *)(a1 + 232), a2, 0, 0x20019u, &hKey);
  v27 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
        v4,
        v9);
    }
  }
  else
  {
    v10 = (WCHAR *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, 0x2000u);
    v6 = v10;
    v29 = v10;
    if ( v10 )
    {
      lpData = v10;
      v30 = v10;
      cbData = 0x2000;
      while ( !RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, &Type, (LPBYTE)lpData, &cbData) )
      {
        if ( cchValueName )
        {
          lpData[4095] = 0;
          if ( Type != 1 || v24 )
          {
            if ( Type != 2 || v24 != 1 )
              goto LABEL_19;
            v7 = (WCHAR *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, 0x2000u);
            v28 = v7;
            if ( v7 )
            {
              v15 = *Environment;
              DestinationString = 0;
              Destination = 0;
              Length = 0;
              if ( RtlInitUnicodeStringEx(&DestinationString, lpData) >= 0 )
              {
                Destination.Buffer = v7;
                *(_DWORD *)&Destination.Length = 0x20000000;
                Length = 0;
                v16 = RtlExpandEnvironmentStrings_U(v15, &DestinationString, &Destination, &Length);
                if ( (int)(v16 + 0x80000000) < 0 || v16 == -1073741789 )
                {
                  v17 = Length;
                  if ( Length > 0x1000 )
                  {
                    HeapFree(*(HANDLE *)(a1 + 8), 0, v7);
                    v28 = 0;
                    v18 = (unsigned __int16 *)HeapAlloc(*(HANDLE *)(a1 + 8), 8u, 2 * v17);
                    v7 = v18;
                    v28 = v18;
                    if ( v18 )
                      ExpandUserEnvironmentStrings(*Environment, lpData, v18, v17);
                  }
                }
              }
            }
            if ( v7 )
            {
              Type = 0;
              lpData = v7;
              v30 = v7;
              v13 = 0;
            }
            else
            {
LABEL_19:
              v13 = -1;
              Type = -1;
            }
          }
          else
          {
            Type = 0;
            v13 = 0;
          }
          if ( !v13 )
          {
            if ( CompareStringW(0x7Fu, 1u, ValueName, -1, L"PATH", -1) == 2
              || CompareStringW(0x7Fu, 1u, ValueName, -1, L"LibPath", -1) == 2
              || CompareStringW(0x7Fu, 1u, ValueName, -1, L"Os2LibPath", -1) == 2 )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  61,
                  WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
                  ValueName);
              }
              BuildEnvironmentPath(Environment, ValueName, lpData);
            }
            else
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  62,
                  WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
                  ValueName);
              }
              SetUserEnvironmentVariable((void **)Environment, ValueName, lpData, v14);
            }
          }
          if ( v7 )
          {
            HeapFree(*(HANDLE *)(a1 + 8), 0, v7);
            v7 = 0;
            v28 = 0;
          }
        }
        v32 = ++v8;
        lpData = v6;
        v30 = v6;
        cbData = 0x2000;
        cchValueName = 260;
      }
    }
    else
    {
      v9 = 14;
      v27 = 14;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v11);
      }
    }
  }
  if ( v6 )
    HeapFree(*(HANDLE *)(a1 + 8), 0, v6);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x140007e30  push    rbx
0x140007e32  push    rsi
0x140007e33  push    rdi
0x140007e34  push    r12
0x140007e36  push    r13
0x140007e38  push    r14
0x140007e3a  push    r15
0x140007e3c  sub     rsp, 2E0h
0x140007e43  mov     rax, cs:__security_cookie
0x140007e4a  xor     rax, rsp
0x140007e4d  mov     [rsp+318h+var_48], rax
0x140007e55  mov     [rsp+318h+Environment], r9
0x140007e5a  mov     [rsp+318h+var_2C8], r8d
0x140007e5f  mov     rsi, rdx
0x140007e62  mov     rbx, rcx
0x140007e65  mov     [rsp+318h+var_278], rcx
0x140007e6d  xor     eax, eax
0x140007e6f  mov     edi, eax
0x140007e71  mov     [rsp+318h+var_2A0], rax
0x140007e76  mov     r12d, eax
0x140007e79  mov     [rsp+318h+cchValueName], 104h
0x140007e81  mov     [rsp+318h+cbData], eax
0x140007e85  mov     [rsp+318h+Type], eax
0x140007e89  mov     r14d, eax
0x140007e8c  mov     [rsp+318h+hKey], rax
0x140007e91  lea     rax, [rsp+318h+hKey]
0x140007e96  mov     [rsp+318h+phkResult], rax; phkResult
0x140007e9b  mov     r9d, 20019h; samDesired
0x140007ea1  xor     r8d, r8d; ulOptions
0x140007ea4  mov     rcx, [rcx+0E8h]; hKey
0x140007eab  call    cs:__imp_RegOpenKeyExW
0x140007eb1  mov     r15d, eax
0x140007eb4  mov     [rsp+318h+var_2B0], eax
0x140007eb8  test    eax, eax
0x140007eba  jnz     loc_1400081F1
0x140007ec0  mov     r13d, 2000h
0x140007ec6  mov     r8d, r13d; dwBytes
0x140007ec9  mov     edx, 8; dwFlags
0x140007ece  mov     rcx, [rbx+8]; hHeap
0x140007ed2  call    cs:__imp_HeapAlloc
0x140007ed8  mov     rdi, rax
0x140007edb  mov     [rsp+318h+var_2A0], rax
0x140007ee0  test    rax, rax
0x140007ee3  jz      loc_14000823E
0x140007ee9  mov     rsi, rax
0x140007eec  mov     [rsp+318h+var_298], rax
0x140007ef4  mov     [rsp+318h+cbData], r13d
0x140007ef9  lea     r13, WPP_GLOBAL_Control
0x140007f00  lea     rax, [rsp+318h+cbData]
0x140007f05  mov     [rsp+318h+lpcbData], rax; lpcbData
0x140007f0a  mov     [rsp+318h+lpData], rsi; lpData
0x140007f0f  lea     rax, [rsp+318h+Type]
0x140007f14  mov     [rsp+318h+lpType], rax; lpType
0x140007f19  mov     [rsp+318h+phkResult], 0; lpReserved
0x140007f22  lea     r9, [rsp+318h+cchValueName]; lpcchValueName
0x140007f27  lea     r8, [rsp+318h+ValueName]; lpValueName
0x140007f2f  mov     edx, r14d; dwIndex
0x140007f32  mov     rcx, [rsp+318h+hKey]; hKey
0x140007f37  call    cs:__imp_RegEnumValueW
0x140007f3d  test    eax, eax
0x140007f3f  jnz     loc_14000831D
0x140007f45  cmp     [rsp+318h+cchValueName], eax
0x140007f49  jz      loc_14000806B
0x140007f4f  mov     [rsi+1FFEh], ax
0x140007f56  mov     eax, [rsp+318h+Type]
0x140007f5a  mov     ecx, [rsp+318h+var_2C8]
0x140007f5e  cmp     eax, 1
0x140007f61  jnz     loc_140008096
0x140007f67  test    ecx, ecx
0x140007f69  jnz     loc_140008096
0x140007f6f  mov     [rsp+318h+Type], ecx
0x140007f73  xor     eax, eax
0x140007f75  test    eax, eax
0x140007f77  jnz     loc_14000804F
0x140007f7d  mov     dword ptr [rsp+318h+lpType], 0FFFFFFFFh; cchCount2
0x140007f85  lea     rax, String2; "PATH"
0x140007f8c  mov     [rsp+318h+phkResult], rax; lpString2
0x140007f91  mov     r9d, 0FFFFFFFFh; cchCount1
0x140007f97  lea     r8, [rsp+318h+ValueName]; lpString1
0x140007f9f  mov     edx, 1; dwCmpFlags
0x140007fa4  mov     ecx, 7Fh; Locale
0x140007fa9  call    cs:__imp_CompareStringW
0x140007faf  cmp     eax, 2
0x140007fb2  jz      loc_1400081BE
0x140007fb8  mov     dword ptr [rsp+318h+lpType], 0FFFFFFFFh; cchCount2
0x140007fc0  lea     rax, aLibpath; "LibPath"
0x140007fc7  mov     [rsp+318h+phkResult], rax; lpString2
0x140007fcc  mov     r9d, 0FFFFFFFFh; cchCount1
0x140007fd2  lea     r8, [rsp+318h+ValueName]; lpString1
0x140007fda  mov     edx, 1; dwCmpFlags
0x140007fdf  mov     ecx, 7Fh; Locale
0x140007fe4  call    cs:__imp_CompareStringW
0x140007fea  cmp     eax, 2
0x140007fed  jz      loc_1400081BE
0x140007ff3  mov     dword ptr [rsp+318h+lpType], 0FFFFFFFFh; cchCount2
0x140007ffb  lea     rax, aOs2libpath; "Os2LibPath"
0x140008002  mov     [rsp+318h+phkResult], rax; lpString2
0x140008007  mov     r9d, 0FFFFFFFFh; cchCount1
0x14000800d  lea     r8, [rsp+318h+ValueName]; lpString1
0x140008015  mov     edx, 1; dwCmpFlags
0x14000801a  mov     ecx, 7Fh; Locale
0x14000801f  call    cs:__imp_CompareStringW
0x140008025  cmp     eax, 2
0x140008028  jz      loc_1400081BE
0x14000802e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008035  cmp     rcx, r13
0x140008038  jnz     short loc_1400080A9
0x14000803a  mov     r8, rsi; unsigned __int16 *
0x14000803d  lea     rdx, [rsp+318h+ValueName]; unsigned __int16 *
0x140008045  mov     rcx, [rsp+318h+Environment]; void **
0x14000804a  call    ?SetUserEnvironmentVariable@@YAHPEAPEAXPEBG1H@Z; SetUserEnvironmentVariable(void * *,ushort const *,ushort const *,int)
0x14000804f  test    r12, r12
0x140008052  jz      short loc_14000806B
0x140008054  mov     r8, r12; lpMem
0x140008057  xor     edx, edx; dwFlags
0x140008059  mov     rcx, [rbx+8]; hHeap
0x14000805d  call    cs:__imp_HeapFree
0x140008063  xor     r12d, r12d
0x140008066  mov     [rsp+318h+var_2A8], r12
0x14000806b  inc     r14d
0x14000806e  mov     [rsp+318h+var_280], r14d
0x140008076  mov     rsi, rdi
0x140008079  mov     [rsp+318h+var_298], rdi
0x140008081  mov     [rsp+318h+cbData], 2000h
0x140008089  mov     [rsp+318h+cchValueName], 104h
0x140008091  jmp     loc_140007F00
0x140008096  cmp     eax, 2
0x140008099  jz      short loc_1400080D7
0x14000809b  mov     eax, 0FFFFFFFFh
0x1400080a0  mov     [rsp+318h+Type], eax
0x1400080a4  jmp     loc_140007F75
0x1400080a9  test    byte ptr [rcx+1Ch], 20h
0x1400080ad  jz      short loc_14000803A
0x1400080af  cmp     byte ptr [rcx+19h], 5
0x1400080b3  jb      short loc_14000803A
0x1400080b5  mov     edx, 3Eh ; '>'
0x1400080ba  lea     r9, [rsp+318h+ValueName]
0x1400080c2  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400080c9  mov     rcx, [rcx+10h]
0x1400080cd  call    WPP_SF_S
0x1400080d2  jmp     loc_14000803A
0x1400080d7  cmp     ecx, 1
0x1400080da  jnz     short loc_14000809B
0x1400080dc  mov     edx, 8; dwFlags
0x1400080e1  mov     r8d, 2000h; dwBytes
0x1400080e7  mov     rcx, [rbx+8]; hHeap
0x1400080eb  call    cs:__imp_HeapAlloc
0x1400080f1  mov     r12, rax
0x1400080f4  mov     [rsp+318h+var_2A8], rax
0x1400080f9  test    rax, rax
0x1400080fc  jz      loc_14000819B
0x140008102  mov     rax, [rsp+318h+Environment]
0x140008107  mov     r13, [rax]
0x14000810a  xorps   xmm0, xmm0
0x14000810d  movups  xmmword ptr [rsp+318h+DestinationString.Length], xmm0
0x140008115  xorps   xmm1, xmm1
0x140008118  movups  xmmword ptr [rsp+318h+Destination.Length], xmm1
0x140008120  mov     [rsp+318h+Length], 0
0x140008128  mov     rdx, rsi; SourceString
0x14000812b  lea     rcx, [rsp+318h+DestinationString]; DestinationString
0x140008133  call    cs:__imp_RtlInitUnicodeStringEx
0x140008139  test    eax, eax
0x14000813b  js      short loc_140008194
0x14000813d  mov     [rsp+318h+Destination.Buffer], r12
0x140008145  mov     dword ptr [rsp+318h+Destination.Length], 20000000h
0x140008150  mov     [rsp+318h+Length], 0
0x140008158  lea     r9, [rsp+318h+Length]; Length
0x14000815d  lea     r8, [rsp+318h+Destination]; Destination
0x140008165  lea     rdx, [rsp+318h+DestinationString]; Source
0x14000816d  mov     rcx, r13; Environment
0x140008170  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x140008176  mov     edx, 80000000h
0x14000817b  lea     ecx, [rax+rdx]
0x14000817e  test    edx, ecx
0x140008180  jz      short loc_1400081E8
0x140008182  mov     r13d, [rsp+318h+Length]
0x140008187  cmp     r13d, 1000h
0x14000818e  ja      loc_14000828E
0x140008194  lea     r13, WPP_GLOBAL_Control
0x14000819b  test    r12, r12
0x14000819e  jz      loc_14000809B
0x1400081a4  mov     [rsp+318h+Type], 0
0x1400081ac  mov     rsi, r12
0x1400081af  mov     [rsp+318h+var_298], r12
0x1400081b7  xor     eax, eax
0x1400081b9  jmp     loc_140007F75
0x1400081be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081c5  cmp     rcx, r13
0x1400081c8  jnz     loc_1400082E7
0x1400081ce  mov     r8, rsi; unsigned __int16 *
0x1400081d1  lea     rdx, [rsp+318h+ValueName]; unsigned __int16 *
0x1400081d9  mov     rcx, [rsp+318h+Environment]; Environment
0x1400081de  call    ?BuildEnvironmentPath@@YAHPEAPEAXPEBG1@Z; BuildEnvironmentPath(void * *,ushort const *,ushort const *)
0x1400081e3  jmp     loc_14000804F
0x1400081e8  cmp     eax, 0C0000023h
0x1400081ed  jz      short loc_140008182
0x1400081ef  jmp     short loc_140008194
0x1400081f1  lea     rax, WPP_GLOBAL_Control
0x1400081f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081ff  cmp     rcx, rax
0x140008202  jz      loc_14000831D
0x140008208  test    byte ptr [rcx+1Ch], 20h
0x14000820c  jz      loc_14000831D
0x140008212  cmp     byte ptr [rcx+19h], 2
0x140008216  jb      loc_14000831D
0x14000821c  mov     edx, 3Bh ; ';'
0x140008221  mov     dword ptr [rsp+318h+phkResult], r15d
0x140008226  mov     r9, rsi
0x140008229  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140008230  mov     rcx, [rcx+10h]
0x140008234  call    WPP_SF_SD
0x140008239  jmp     loc_14000831D
0x14000823e  mov     r15d, 0Eh
0x140008244  mov     [rsp+318h+var_2B0], r15d
0x140008249  lea     rax, WPP_GLOBAL_Control
0x140008250  mov     rcx, cs:WPP_GLOBAL_Control
0x140008257  cmp     rcx, rax
0x14000825a  jz      loc_14000831D
0x140008260  test    byte ptr [rcx+1Ch], 20h
0x140008264  jz      loc_14000831D
0x14000826a  cmp     byte ptr [rcx+19h], 2
0x14000826e  jb      loc_14000831D
0x140008274  mov     edx, 3Ch ; '<'
0x140008279  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140008280  mov     rcx, [rcx+10h]
0x140008284  call    WPP_SF_
0x140008289  jmp     loc_14000831D
0x14000828e  mov     r8, r12; lpMem
0x140008291  xor     edx, edx; dwFlags
0x140008293  mov     rcx, [rbx+8]; hHeap
0x140008297  call    cs:__imp_HeapFree
0x14000829d  mov     [rsp+318h+var_2A8], 0
0x1400082a6  mov     r8, r13
0x1400082a9  add     r8, r8; dwBytes
0x1400082ac  mov     edx, 8; dwFlags
0x1400082b1  mov     rcx, [rbx+8]; hHeap
0x1400082b5  call    cs:__imp_HeapAlloc
0x1400082bb  mov     r12, rax
0x1400082be  mov     [rsp+318h+var_2A8], rax
0x1400082c3  test    rax, rax
0x1400082c6  jz      loc_140008194
0x1400082cc  mov     r9d, r13d; unsigned int
0x1400082cf  mov     r8, rax; unsigned __int16 *
0x1400082d2  mov     rdx, rsi; unsigned __int16 *
0x1400082d5  mov     rax, [rsp+318h+Environment]
0x1400082da  mov     rcx, [rax]; Environment
0x1400082dd  call    ?ExpandUserEnvironmentStrings@@YAKPEAXPEBGPEAGK@Z; ExpandUserEnvironmentStrings(void *,ushort const *,ushort *,ulong)
0x1400082e2  jmp     loc_140008194
0x1400082e7  test    byte ptr [rcx+1Ch], 20h
0x1400082eb  jz      loc_1400081CE
0x1400082f1  cmp     byte ptr [rcx+19h], 5
0x1400082f5  jb      loc_1400081CE
0x1400082fb  mov     edx, 3Dh ; '='
0x140008300  lea     r9, [rsp+318h+ValueName]
0x140008308  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000830f  mov     rcx, [rcx+10h]
0x140008313  call    WPP_SF_S
0x140008318  jmp     loc_1400081CE
0x14000831d  test    rdi, rdi
0x140008320  jz      short loc_140008331
0x140008322  mov     r8, rdi; lpMem
0x140008325  xor     edx, edx; dwFlags
0x140008327  mov     rcx, [rbx+8]; hHeap
0x14000832b  call    cs:__imp_HeapFree
0x140008331  mov     rcx, [rsp+318h+hKey]; hKey
0x140008336  test    rcx, rcx
0x140008339  jz      short loc_140008341
0x14000833b  call    cs:__imp_RegCloseKey
0x140008341  mov     eax, r15d
0x140008344  mov     rcx, [rsp+318h+var_48]
0x14000834c  xor     rcx, rsp; StackCookie
0x14000834f  call    __security_check_cookie
0x140008354  add     rsp, 2E0h
0x14000835b  pop     r15
0x14000835d  pop     r14
0x14000835f  pop     r13
0x140008361  pop     r12
0x140008363  pop     rdi
0x140008364  pop     rsi
0x140008365  pop     rbx
0x140008366  retn
0x14009cfc0  push    rbp
0x14009cfc2  sub     rsp, 40h
0x14009cfc6  mov     rbp, rdx
0x14009cfc9  mov     r8, [rbp+78h]; lpMem
0x14009cfcd  test    r8, r8
0x14009cfd0  jz      short loc_14009CFED
0x14009cfd2  xor     edx, edx; dwFlags
0x14009cfd4  mov     rcx, [rbp+0A0h]
0x14009cfdb  mov     rcx, [rcx+8]; hHeap
0x14009cfdf  call    cs:__imp_HeapFree
0x14009cfe5  mov     qword ptr [rbp+78h], 0
0x14009cfed  mov     rcx, [rbp+60h]; hKey
0x14009cff1  test    rcx, rcx
0x14009cff4  jz      short loc_14009CFFD
0x14009cff6  call    cs:__imp_RegCloseKey
0x14009cffc  nop
0x14009cffd  add     rsp, 40h
0x14009d001  pop     rbp
0x14009d002  retn
  ... truncated ...
```
