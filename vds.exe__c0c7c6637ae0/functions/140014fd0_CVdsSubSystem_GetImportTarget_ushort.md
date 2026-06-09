# CVdsSubSystem::GetImportTarget(ushort * *)

- ea: `0x140014fd0`
- end: `0x14001535a`
- name: `?GetImportTarget@CVdsSubSystem@@UEAAJPEAPEAG@Z`
- size: `906`
- prototype: `__int64 __fastcall(CVdsSubSystem *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1400069e8`
- `0x140013298`
- `0x140014fd0`
- `0x140015360`
- `0x140052e46`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400150e4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400150e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001522b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140015294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001522b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140015294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001528a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001531f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001528a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400152ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015305`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001531f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140015272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140015272`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140015139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400151af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140015139`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400151af`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001504e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001504e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001532b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001532b`
- `vdsutil!VdsTraceW` at `0x14001507a`
- `vdsutil!VdsTraceW` at `0x1400150c6`
- `vdsutil!VdsTraceW` at `0x140015151`
- `vdsutil!VdsTraceW` at `0x1400151c5`
- `vdsutil!VdsTraceW` at `0x140015204`
- `vdsutil!VdsTraceW` at `0x140015242`
- `vdsutil!VdsTraceW` at `0x1400152bb`
- `vdsutil!VdsTraceW` at `0x1400152d8`
- `vdsutil!VdsTraceW` at `0x14001507a`
- `vdsutil!VdsTraceW` at `0x1400150c6`
- `vdsutil!VdsTraceW` at `0x140015151`
- `vdsutil!VdsTraceW` at `0x1400151c5`
- `vdsutil!VdsTraceW` at `0x140015204`
- `vdsutil!VdsTraceW` at `0x140015242`
- `vdsutil!VdsTraceW` at `0x1400152bb`
- `vdsutil!VdsTraceW` at `0x1400152d8`

## string_xrefs

- `0x1400150ff`: `System\CurrentControlSet\Services\vds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsSubSystem::GetImportTarget(CVdsSubSystem *this, BYTE **a2)
{
  BYTE *v4; // rdi
  int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // eax
  LSTATUS Value; // eax
  SIZE_T cb; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[16]; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v15; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v16; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+78h] [rbp-88h]
  __int128 v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+98h] [rbp-68h]
  GUID Buf2; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[48]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[152]; // [rsp+110h] [rbp+10h] BYREF

  Buf2 = 0;
  hKey = 0;
  phkResult = 0;
  v16 = 0;
  *(_OWORD *)lpValueName = 0;
  v18 = 0;
  v19 = 0;
  v4 = 0;
  cb = 50;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v14, 0x5Eu, "CVdsSubSystem::GetImportTarget()");
  v16 = 0;
  *(_OWORD *)lpValueName = 0;
  v18 = 0;
  v19 = 0;
  if ( a2 )
  {
    *a2 = 0;
    Buf2 = *CVdsSubSystem::GetProviderId((CVdsSubSystem *)((char *)this - 32), &v15);
    if ( !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
    {
      VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 2");
      v5 = -2147211929;
    }
    else
    {
      StringFromGUID2(&Buf2, sz, 45);
      StringCchPrintfW(SubKey, 0x96u, L"%s\\%s\\%s", g_wszVdsKey, aHardwareprovid, sz);
      v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2000000u, &hKey);
      v5 = v6;
      if ( v6 )
      {
        VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 3, %ld", v6);
        VdsLogError(0xC2000001, 0, 0, v5, 0x2090010u, 0, cb, hKey, phkResult);
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
      }
      else
      {
        v7 = RegOpenKeyExW(hKey, g_wszVdsImportTargets, 0, 0x2000000u, &phkResult);
        if ( v7 )
        {
          VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 4, %ld", v7);
LABEL_10:
          *a2 = 0;
          v5 = -2147211501;
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(char *, __int128 *))(*((_QWORD *)this - 4) + 24LL))((char *)this - 32, &v16);
          v5 = v8;
          if ( v8 >= 0 )
          {
            if ( lpValueName[1] && *lpValueName[1] )
            {
              v4 = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
              if ( v4 )
              {
                while ( 1 )
                {
                  Value = RegQueryValueExW(phkResult, lpValueName[1], 0, (LPDWORD)&cb + 1, v4, (LPDWORD)&cb);
                  if ( !Value )
                    break;
                  if ( Value != 234 )
                    goto LABEL_10;
                  CoTaskMemFree(v4);
                  v4 = (BYTE *)CoTaskMemAlloc((unsigned int)cb);
                  if ( !v4 )
                  {
                    VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 9");
                    goto LABEL_17;
                  }
                }
                if ( HIDWORD(cb) == 1 )
                {
                  v5 = 0;
                  *a2 = v4;
                }
                else
                {
                  VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 8");
                  v5 = -2147023267;
                }
              }
              else
              {
                VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 7.");
LABEL_17:
                v5 = -2147024882;
              }
            }
            else
            {
              VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 6");
              v5 = -2147211001;
            }
          }
          else
          {
            VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 5, hr=%lX", (unsigned int)v8);
          }
        }
      }
    }
  }
  else
  {
    VdsTraceW(0, L"CVdsSubSystem::GetImportTarget, 1");
    v5 = -2147024809;
  }
  if ( lpValueName[0] )
  {
    CoTaskMemFree((LPVOID)lpValueName[0]);
    lpValueName[0] = 0;
  }
  if ( lpValueName[1] )
  {
    CoTaskMemFree((LPVOID)lpValueName[1]);
    lpValueName[1] = 0;
  }
  if ( v5 < 0 && v4 )
    CoTaskMemFree(v4);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014fd0  mov     [rsp-8+arg_10], rbx
0x140014fd5  mov     [rsp-8+arg_18], rsi
0x140014fda  push    rbp
0x140014fdb  push    rdi
0x140014fdc  push    r14
0x140014fde  lea     rbp, [rsp-150h]
0x140014fe6  sub     rsp, 250h
0x140014fed  mov     rax, cs:__security_cookie
0x140014ff4  xor     rax, rsp
0x140014ff7  mov     [rbp+160h+var_20], rax
0x140014ffe  mov     rsi, rdx
0x140015001  mov     r14, rcx
0x140015004  xorps   xmm0, xmm0
0x140015007  movups  [rbp+160h+Buf2], xmm0
0x14001500b  mov     [rsp+260h+hKey], 0
0x140015014  mov     [rsp+260h+var_220], 0
0x14001501d  xor     eax, eax
0x14001501f  movups  [rsp+260h+var_1F8], xmm0
0x140015024  movups  xmmword ptr [rsp+260h+lpValueName], xmm0
0x140015029  movups  [rbp+160h+var_1D8], xmm0
0x14001502d  mov     [rbp+160h+var_1C8], rax
0x140015031  xor     edi, edi
0x140015033  mov     dword ptr [rsp+260h+cb+4], eax
0x140015037  mov     dword ptr [rsp+260h+cb], 32h ; '2'
0x14001503f  lea     r8, aCvdssubsystemG_24; "CVdsSubSystem::GetImportTarget()"
0x140015046  lea     edx, [rax+5Eh]
0x140015049  lea     rcx, [rsp+260h+var_218]
0x14001504e  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140015054  nop
0x140015055  xorps   xmm0, xmm0
0x140015058  xor     eax, eax
0x14001505a  movups  [rsp+260h+var_1F8], xmm0
0x14001505f  movups  xmmword ptr [rsp+260h+lpValueName], xmm0
0x140015064  movups  [rbp+160h+var_1D8], xmm0
0x140015068  mov     [rbp+160h+var_1C8], rax
0x14001506c  test    rsi, rsi
0x14001506f  jnz     short loc_14001508A
0x140015071  lea     rdx, aCvdssubsystemG_2; "CVdsSubSystem::GetImportTarget, 1"
0x140015078  xor     ecx, ecx
0x14001507a  call    cs:__imp_VdsTraceW
0x140015080  mov     ebx, 80070057h
0x140015085  jmp     loc_1400152E3
0x14001508a  mov     [rsi], rax
0x14001508d  lea     rdx, [rsp+260h+var_208]; retstr
0x140015092  lea     rcx, [r14-20h]; this
0x140015096  call    ?GetProviderId@CVdsSubSystem@@QEAA?AU_GUID@@XZ; CVdsSubSystem::GetProviderId(void)
0x14001509b  movups  xmm0, xmmword ptr [rax]
0x14001509e  movdqu  [rbp+160h+Buf2], xmm0
0x1400150a3  mov     r8d, 10h; Size
0x1400150a9  lea     rdx, [rbp+160h+Buf2]; Buf2
0x1400150ad  lea     rcx, GUID_NULL; Buf1
0x1400150b4  call    memcmp_0
0x1400150b9  test    eax, eax
0x1400150bb  jnz     short loc_1400150D6
0x1400150bd  lea     rdx, aCvdssubsystemG_12; "CVdsSubSystem::GetImportTarget, 2"
0x1400150c4  xor     ecx, ecx
0x1400150c6  call    cs:__imp_VdsTraceW
0x1400150cc  mov     ebx, 80042567h
0x1400150d1  jmp     loc_1400152E3
0x1400150d6  mov     r8d, 2Dh ; '-'; cchMax
0x1400150dc  lea     rdx, [rbp+160h+sz]; lpsz
0x1400150e0  lea     rcx, [rbp+160h+Buf2]; rguid
0x1400150e4  call    cs:__imp_StringFromGUID2
0x1400150ea  lea     rax, [rbp+160h+sz]
0x1400150ee  mov     [rsp+260h+lpcbData], rax
0x1400150f3  lea     rax, aHardwareprovid; "HardwareProviders"
0x1400150fa  mov     [rsp+260h+phkResult], rax
0x1400150ff  lea     r9, ?g_wszVdsKey@@3PAGA; "System\\CurrentControlSet\\Services\\vd"...
0x140015106  lea     r8, aSSS; "%s\\%s\\%s"
0x14001510d  mov     edx, 96h; unsigned __int64
0x140015112  lea     rcx, [rbp+160h+SubKey]; unsigned __int16 *
0x140015116  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001511b  lea     rax, [rsp+260h+hKey]
0x140015120  mov     [rsp+260h+phkResult], rax; phkResult
0x140015125  mov     r9d, 2000000h; samDesired
0x14001512b  xor     r8d, r8d; ulOptions
0x14001512e  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x140015132  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015139  call    cs:__imp_RegOpenKeyExW
0x14001513f  mov     ebx, eax
0x140015141  test    eax, eax
0x140015143  jz      short loc_140015190
0x140015145  mov     r8d, eax
0x140015148  lea     rdx, aCvdssubsystemG_19; "CVdsSubSystem::GetImportTarget, 3, %ld"
0x14001514f  xor     ecx, ecx
0x140015151  call    cs:__imp_VdsTraceW
0x140015157  mov     [rsp+260h+lpcbData], 0; unsigned __int16 *
0x140015160  mov     dword ptr [rsp+260h+phkResult], 2090010h; unsigned int
0x140015168  mov     r9d, ebx; unsigned int
0x14001516b  xor     r8d, r8d; void *
0x14001516e  xor     edx, edx; unsigned int
0x140015170  mov     ecx, 0C2000001h; unsigned int
0x140015175  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001517a  test    ebx, ebx
0x14001517c  jle     loc_1400152E3
0x140015182  movzx   ebx, bx
0x140015185  or      ebx, 80070000h
0x14001518b  jmp     loc_1400152E3
0x140015190  lea     rax, [rsp+260h+var_220]
0x140015195  mov     [rsp+260h+phkResult], rax; phkResult
0x14001519a  mov     r9d, 2000000h; samDesired
0x1400151a0  xor     r8d, r8d; ulOptions
0x1400151a3  lea     rdx, ?g_wszVdsImportTargets@@3PAGA; "ImportTargets"
0x1400151aa  mov     rcx, [rsp+260h+hKey]; hKey
0x1400151af  call    cs:__imp_RegOpenKeyExW
0x1400151b5  test    eax, eax
0x1400151b7  jz      short loc_1400151DC
0x1400151b9  mov     r8d, eax
0x1400151bc  lea     rdx, aCvdssubsystemG; "CVdsSubSystem::GetImportTarget, 4, %ld"
0x1400151c3  xor     ecx, ecx
0x1400151c5  call    cs:__imp_VdsTraceW
0x1400151cb  mov     qword ptr [rsi], 0
0x1400151d2  mov     ebx, 80042713h
0x1400151d7  jmp     loc_1400152E3
0x1400151dc  mov     rax, [r14-20h]
0x1400151e0  lea     rdx, [rsp+260h+var_1F8]
0x1400151e5  lea     rcx, [r14-20h]
0x1400151e9  mov     rax, [rax+18h]
0x1400151ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151f2  mov     ebx, eax
0x1400151f4  test    eax, eax
0x1400151f6  jns     short loc_14001520F
0x1400151f8  mov     r8d, eax
0x1400151fb  lea     rdx, aCvdssubsystemG_8; "CVdsSubSystem::GetImportTarget, 5, hr=%"...
0x140015202  xor     ecx, ecx
0x140015204  call    cs:__imp_VdsTraceW
0x14001520a  jmp     loc_1400152E3
0x14001520f  mov     rcx, [rbp+160h+lpValueName+8]
0x140015213  test    rcx, rcx
0x140015216  jz      loc_1400152CF
0x14001521c  xor     eax, eax
0x14001521e  cmp     ax, [rcx]
0x140015221  jz      loc_1400152CF
0x140015227  mov     ecx, dword ptr [rsp+260h+cb]; cb
0x14001522b  call    cs:__imp_CoTaskMemAlloc
0x140015231  mov     rdi, rax
0x140015234  test    rax, rax
0x140015237  jnz     short loc_140015252
0x140015239  lea     rdx, aCvdssubsystemG_15; "CVdsSubSystem::GetImportTarget, 7."
0x140015240  xor     ecx, ecx
0x140015242  call    cs:__imp_VdsTraceW
0x140015248  mov     ebx, 8007000Eh
0x14001524d  jmp     loc_1400152E3
0x140015252  lea     rax, [rsp+260h+cb]
0x140015257  mov     [rsp+260h+lpcbData], rax; lpcbData
0x14001525c  mov     [rsp+260h+phkResult], rdi; lpData
0x140015261  lea     r9, [rsp+260h+cb+4]; lpType
0x140015266  xor     r8d, r8d; lpReserved
0x140015269  mov     rdx, [rbp+160h+lpValueName+8]; lpValueName
0x14001526d  mov     rcx, [rsp+260h+var_220]; hKey
0x140015272  call    cs:__imp_RegQueryValueExW
0x140015278  test    eax, eax
0x14001527a  jz      short loc_1400152AB
0x14001527c  cmp     eax, 0EAh
0x140015281  jnz     loc_1400151CB
0x140015287  mov     rcx, rdi; pv
0x14001528a  call    cs:__imp_CoTaskMemFree
0x140015290  mov     ecx, dword ptr [rsp+260h+cb]; cb
0x140015294  call    cs:__imp_CoTaskMemAlloc
0x14001529a  mov     rdi, rax
0x14001529d  test    rax, rax
0x1400152a0  jnz     short loc_140015252
0x1400152a2  lea     rdx, aCvdssubsystemG_18; "CVdsSubSystem::GetImportTarget, 9"
0x1400152a9  jmp     short loc_140015240
0x1400152ab  cmp     dword ptr [rsp+260h+cb+4], 1
0x1400152b0  jz      short loc_1400152C8
0x1400152b2  lea     rdx, aCvdssubsystemG_0; "CVdsSubSystem::GetImportTarget, 8"
0x1400152b9  xor     ecx, ecx
0x1400152bb  call    cs:__imp_VdsTraceW
0x1400152c1  mov     ebx, 8007065Dh
0x1400152c6  jmp     short loc_1400152E3
0x1400152c8  xor     ebx, ebx
0x1400152ca  mov     [rsi], rdi
0x1400152cd  jmp     short loc_1400152E3
0x1400152cf  lea     rdx, aCvdssubsystemG_32; "CVdsSubSystem::GetImportTarget, 6"
0x1400152d6  xor     ecx, ecx
0x1400152d8  call    cs:__imp_VdsTraceW
0x1400152de  mov     ebx, 80042907h
0x1400152e3  mov     rcx, [rsp+260h+lpValueName]; pv
0x1400152e8  test    rcx, rcx
0x1400152eb  jz      short loc_1400152FC
0x1400152ed  call    cs:__imp_CoTaskMemFree
0x1400152f3  mov     [rsp+260h+lpValueName], 0
0x1400152fc  mov     rcx, [rbp+160h+lpValueName+8]; pv
0x140015300  test    rcx, rcx
0x140015303  jz      short loc_140015313
0x140015305  call    cs:__imp_CoTaskMemFree
0x14001530b  mov     [rbp+160h+lpValueName+8], 0
0x140015313  test    ebx, ebx
0x140015315  jns     short loc_140015326
0x140015317  test    rdi, rdi
0x14001531a  jz      short loc_140015326
0x14001531c  mov     rcx, rdi; pv
0x14001531f  call    cs:__imp_CoTaskMemFree
0x140015325  nop
0x140015326  lea     rcx, [rsp+260h+var_218]
0x14001532b  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140015331  mov     eax, ebx
0x140015333  mov     rcx, [rbp+160h+var_20]
0x14001533a  xor     rcx, rsp; StackCookie
0x14001533d  call    __security_check_cookie
0x140015342  lea     r11, [rsp+260h+var_10]
0x14001534a  mov     rbx, [r11+30h]
0x14001534e  mov     rsi, [r11+38h]
0x140015352  mov     rsp, r11
0x140015355  pop     r14
0x140015357  pop     rdi
0x140015358  pop     rbp
0x140015359  retn
```
