# Ext_IECompatMatchExtension(ushort const *,ushort const *,ulong,ulong,ulong *,ulong *)

- ea: `0x1800a30b4`
- end: `0x1800a3388`
- name: `?Ext_IECompatMatchExtension@@YAJPEBG0KKPEAK1@Z`
- size: `724`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800608b4`

## callees

- `0x18008f3f8`
- `0x1800937fc`
- `0x1800a30b4`
- `0x180119568`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800a31a5`
- `msvcrt!wcstok_s` at `0x1800a31bf`
- `msvcrt!wcstok_s` at `0x1800a31d9`
- `msvcrt!wcstok_s` at `0x1800a31f3`
- `msvcrt!wcstok_s` at `0x1800a3345`
- `msvcrt!wcstok_s` at `0x1800a335d`
- `msvcrt!wcstok_s` at `0x1800a3375`
- `msvcrt!wcstok_s` at `0x1800a31a5`
- `msvcrt!wcstok_s` at `0x1800a31bf`
- `msvcrt!wcstok_s` at `0x1800a31d9`
- `msvcrt!wcstok_s` at `0x1800a31f3`
- `msvcrt!wcstok_s` at `0x1800a3345`
- `msvcrt!wcstok_s` at `0x1800a335d`
- `msvcrt!wcstok_s` at `0x1800a3375`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800a3279`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800a32a5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800a3279`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x1800a32a5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800a3230`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800a3230`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a32f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a3309`

## string_xrefs

- `0x1800a30df`: `DllName`
- `0x1800a315b`: `CompatibilityFlags`

## pseudocode

```c
__int64 __fastcall Ext_IECompatMatchExtension(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  HKEY v8; // rcx
  int v9; // ebx
  int v10; // r9d
  HKEY v11; // rcx
  int v12; // r9d
  HKEY v13; // rcx
  int v14; // r9d
  wchar_t *v15; // rcx
  wchar_t *v16; // rdi
  wchar_t *v17; // r14
  wchar_t *v18; // rax
  wchar_t *i; // rcx
  const WCHAR *v20; // r12
  wchar_t *v21; // rax
  const WCHAR *v22; // r15
  int v23; // eax
  int v24; // ecx
  unsigned int *v26; // [rsp+28h] [rbp-58h]
  unsigned int *v27; // [rsp+28h] [rbp-58h]
  unsigned int *v28; // [rsp+28h] [rbp-58h]
  unsigned int *v29; // [rsp+28h] [rbp-58h]
  int piRet; // [rsp+30h] [rbp-50h] BYREF
  int v31; // [rsp+34h] [rbp-4Ch] BYREF
  wchar_t *v32; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *v33; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v34; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *String; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *v37; // [rsp+60h] [rbp-20h] BYREF
  wchar_t *v38; // [rsp+68h] [rbp-18h] BYREF
  wchar_t *v39; // [rsp+70h] [rbp-10h] BYREF

  String = 0;
  v9 = SHRegAllocData((HKEY)a1, a1, L"DllName", a4, (void **)&String, v26);
  if ( v9 >= 0 )
  {
    v34 = 0;
    v9 = SHRegAllocData(v8, a1, L"Version", v10, (void **)&v34, v27);
    if ( v9 >= 0 )
    {
      v33 = 0;
      v9 = SHRegAllocData(v11, a1, L"BlockType", v12, (void **)&v33, v28);
      if ( v9 >= 0 )
      {
        v32 = 0;
        v9 = SHRegAllocData(v13, a1, L"CompatibilityFlags", v14, (void **)&v32, v29);
        if ( v9 >= 0 )
        {
          v15 = String;
          Context = 0;
          v9 = 0;
          v37 = 0;
          *a6 = 0;
          v38 = 0;
          v39 = 0;
          v16 = wcstok_s(v15, L";", &Context);
          v17 = wcstok_s(v34, L";", &v37);
          v18 = wcstok_s(v33, L";", &v38);
          for ( i = v32; ; i = 0 )
          {
            v20 = v18;
            v21 = wcstok_s(i, L";", &v39);
            v22 = v21;
            if ( !v16 || !v17 || !v20 || !v21 )
              break;
            if ( (!StrCmpICW(L"*", v16) || (unsigned int)Ext_CompareFileNames(a2, v16))
              && !(unsigned int)Ext_IsVersionInRange(v17, a3, a4) )
            {
              piRet = 0;
              v23 = StrToIntExW(v22, 1, &piRet);
              if ( v23 )
                v23 = piRet;
              else
                piRet = 0;
              if ( v23 )
              {
                *a6 |= v23;
              }
              else
              {
                v31 = 0;
                if ( StrToIntExW(v20, 1, &v31) )
                  v24 = v31;
                else
                  v24 = 0;
                if ( (v24 & 0x10) != 0 || (v24 & 0xC) == 0 || (v24 & 4) != 0 )
                {
                  *a6 = 0;
                  v9 = 1;
                  *a5 = v24;
                  break;
                }
              }
            }
            v16 = wcstok_s(0, L";", &Context);
            v17 = wcstok_s(0, L";", &v37);
            v18 = wcstok_s(0, L";", &v38);
          }
          CoTaskMemFree(v32);
        }
        CoTaskMemFree(v33);
      }
      CoTaskMemFree(v34);
    }
    CoTaskMemFree(String);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a30b4  mov     [rsp-38h+arg_0], rbx
0x1800a30b9  mov     [rsp-38h+arg_10], r8d
0x1800a30be  mov     [rsp-38h+arg_8], rdx
0x1800a30c3  push    rbp
0x1800a30c4  push    rsi
0x1800a30c5  push    rdi
0x1800a30c6  push    r12
0x1800a30c8  push    r13
0x1800a30ca  push    r14
0x1800a30cc  push    r15
0x1800a30ce  mov     rbp, rsp
0x1800a30d1  sub     rsp, 80h
0x1800a30d8  lea     rax, [rbp+String]
0x1800a30dc  xor     r14d, r14d
0x1800a30df  lea     r8, aDllname_0; "DllName"
0x1800a30e6  mov     [rbp+String], r14
0x1800a30ea  mov     rdx, rcx; unsigned __int16 *
0x1800a30ed  mov     [rsp+80h+var_60], rax; void **
0x1800a30f2  mov     r13d, r9d
0x1800a30f5  mov     rdi, rcx
0x1800a30f8  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800a30fd  mov     ebx, eax
0x1800a30ff  test    eax, eax
0x1800a3101  js      loc_1800A3315
0x1800a3107  lea     rax, [rbp+var_38]
0x1800a310b  mov     [rbp+var_38], r14
0x1800a310f  lea     r8, aVersion_2; "Version"
0x1800a3116  mov     [rsp+80h+var_60], rax; void **
0x1800a311b  mov     rdx, rdi; unsigned __int16 *
0x1800a311e  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800a3123  mov     ebx, eax
0x1800a3125  test    eax, eax
0x1800a3127  js      loc_1800A3305
0x1800a312d  lea     rax, [rbp+var_40]
0x1800a3131  mov     [rbp+var_40], r14
0x1800a3135  lea     r8, aBlocktype; "BlockType"
0x1800a313c  mov     [rsp+80h+var_60], rax; void **
0x1800a3141  mov     rdx, rdi; unsigned __int16 *
0x1800a3144  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800a3149  mov     ebx, eax
0x1800a314b  test    eax, eax
0x1800a314d  js      loc_1800A32F5
0x1800a3153  lea     rax, [rbp+var_48]
0x1800a3157  mov     [rbp+var_48], r14
0x1800a315b  lea     r8, aCompatibilityf; "CompatibilityFlags"
0x1800a3162  mov     [rsp+80h+var_60], rax; void **
0x1800a3167  mov     rdx, rdi; unsigned __int16 *
0x1800a316a  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800a316f  mov     ebx, eax
0x1800a3171  test    eax, eax
0x1800a3173  js      loc_1800A32E5
0x1800a3179  mov     rsi, [rbp+arg_28]
0x1800a317d  lea     r15, SubStr; ";"
0x1800a3184  mov     rcx, [rbp+String]; String
0x1800a3188  lea     r8, [rbp+Context]; Context
0x1800a318c  mov     rdx, r15; Delimiter
0x1800a318f  mov     [rbp+Context], r14
0x1800a3193  mov     ebx, r14d
0x1800a3196  mov     [rbp+var_20], r14
0x1800a319a  mov     [rsi], r14d
0x1800a319d  mov     [rbp+var_18], r14
0x1800a31a1  mov     [rbp+var_10], r14
0x1800a31a5  call    cs:__imp_wcstok_s
0x1800a31ac  nop     dword ptr [rax+rax+00h]
0x1800a31b1  mov     rcx, [rbp+var_38]; String
0x1800a31b5  lea     r8, [rbp+var_20]; Context
0x1800a31b9  mov     rdx, r15; Delimiter
0x1800a31bc  mov     rdi, rax
0x1800a31bf  call    cs:__imp_wcstok_s
0x1800a31c6  nop     dword ptr [rax+rax+00h]
0x1800a31cb  mov     rcx, [rbp+var_40]; String
0x1800a31cf  lea     r8, [rbp+var_18]; Context
0x1800a31d3  mov     rdx, r15; Delimiter
0x1800a31d6  mov     r14, rax
0x1800a31d9  call    cs:__imp_wcstok_s
0x1800a31e0  nop     dword ptr [rax+rax+00h]
0x1800a31e5  mov     rcx, [rbp+var_48]; String
0x1800a31e9  lea     r8, [rbp+var_10]; Context
0x1800a31ed  mov     rdx, r15; Delimiter
0x1800a31f0  mov     r12, rax
0x1800a31f3  call    cs:__imp_wcstok_s
0x1800a31fa  nop     dword ptr [rax+rax+00h]
0x1800a31ff  mov     r15, rax
0x1800a3202  test    rdi, rdi
0x1800a3205  jz      loc_1800A32D5
0x1800a320b  test    r14, r14
0x1800a320e  jz      loc_1800A32D5
0x1800a3214  test    r12, r12
0x1800a3217  jz      loc_1800A32D5
0x1800a321d  test    rax, rax
0x1800a3220  jz      loc_1800A32D5
0x1800a3226  mov     rdx, rdi; pszStr2
0x1800a3229  lea     rcx, pszStr1; "*"
0x1800a3230  call    cs:__imp_StrCmpICW
0x1800a3237  nop     dword ptr [rax+rax+00h]
0x1800a323c  test    eax, eax
0x1800a323e  jz      short loc_1800A3254
0x1800a3240  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x1800a3244  mov     rdx, rdi; unsigned __int16 *
0x1800a3247  call    ?Ext_CompareFileNames@@YAHPEBG0@Z; Ext_CompareFileNames(ushort const *,ushort const *)
0x1800a324c  test    eax, eax
0x1800a324e  jz      loc_1800A3335
0x1800a3254  mov     edx, [rbp+arg_10]; unsigned int
0x1800a3257  mov     r8d, r13d; unsigned int
0x1800a325a  mov     rcx, r14; unsigned __int16 *
0x1800a325d  call    ?Ext_IsVersionInRange@@YAJPEBGKK@Z; Ext_IsVersionInRange(ushort const *,ulong,ulong)
0x1800a3262  test    eax, eax
0x1800a3264  jnz     loc_1800A3335
0x1800a326a  lea     edi, [rax+1]
0x1800a326d  mov     [rbp+piRet], ebx
0x1800a3270  mov     edx, edi; dwFlags
0x1800a3272  lea     r8, [rbp+piRet]; piRet
0x1800a3276  mov     rcx, r15; pszString
0x1800a3279  call    cs:__imp_StrToIntExW
0x1800a3280  nop     dword ptr [rax+rax+00h]
0x1800a3285  test    eax, eax
0x1800a3287  jnz     short loc_1800A328E
0x1800a3289  mov     [rbp+piRet], eax
0x1800a328c  jmp     short loc_1800A3291
0x1800a328e  mov     eax, [rbp+piRet]
0x1800a3291  test    eax, eax
0x1800a3293  jnz     loc_1800A3333
0x1800a3299  lea     r8, [rbp+var_4C]; piRet
0x1800a329d  mov     [rbp+var_4C], ebx
0x1800a32a0  mov     edx, edi; dwFlags
0x1800a32a2  mov     rcx, r12; pszString
0x1800a32a5  call    cs:__imp_StrToIntExW
0x1800a32ac  nop     dword ptr [rax+rax+00h]
0x1800a32b1  test    eax, eax
0x1800a32b3  jnz     short loc_1800A32B9
0x1800a32b5  xor     ecx, ecx
0x1800a32b7  jmp     short loc_1800A32BC
0x1800a32b9  mov     ecx, [rbp+var_4C]
0x1800a32bc  test    cl, 10h
0x1800a32bf  jnz     short loc_1800A32CB
0x1800a32c1  test    cl, 0Ch
0x1800a32c4  jz      short loc_1800A32CB
0x1800a32c6  test    cl, 4
0x1800a32c9  jz      short loc_1800A3335
0x1800a32cb  mov     rax, [rbp+arg_20]
0x1800a32cf  mov     [rsi], ebx
0x1800a32d1  mov     ebx, edi
0x1800a32d3  mov     [rax], ecx
0x1800a32d5  mov     rcx, [rbp+var_48]; pv
0x1800a32d9  call    cs:__imp_CoTaskMemFree
0x1800a32e0  nop     dword ptr [rax+rax+00h]
0x1800a32e5  mov     rcx, [rbp+var_40]; pv
0x1800a32e9  call    cs:__imp_CoTaskMemFree
0x1800a32f0  nop     dword ptr [rax+rax+00h]
0x1800a32f5  mov     rcx, [rbp+var_38]; pv
0x1800a32f9  call    cs:__imp_CoTaskMemFree
0x1800a3300  nop     dword ptr [rax+rax+00h]
0x1800a3305  mov     rcx, [rbp+String]; pv
0x1800a3309  call    cs:__imp_CoTaskMemFree
0x1800a3310  nop     dword ptr [rax+rax+00h]
0x1800a3315  mov     eax, ebx
0x1800a3317  mov     rbx, [rsp+80h+arg_0]
0x1800a331f  add     rsp, 80h
0x1800a3326  pop     r15
0x1800a3328  pop     r14
0x1800a332a  pop     r13
0x1800a332c  pop     r12
0x1800a332e  pop     rdi
0x1800a332f  pop     rsi
0x1800a3330  pop     rbp
0x1800a3331  retn
0x1800a3333  or      [rsi], eax
0x1800a3335  lea     r15, SubStr; ";"
0x1800a333c  xor     ecx, ecx; String
0x1800a333e  mov     rdx, r15; Delimiter
0x1800a3341  lea     r8, [rbp+Context]; Context
0x1800a3345  call    cs:__imp_wcstok_s
0x1800a334c  nop     dword ptr [rax+rax+00h]
0x1800a3351  lea     r8, [rbp+var_20]; Context
0x1800a3355  mov     rdx, r15; Delimiter
0x1800a3358  xor     ecx, ecx; String
0x1800a335a  mov     rdi, rax
0x1800a335d  call    cs:__imp_wcstok_s
0x1800a3364  nop     dword ptr [rax+rax+00h]
0x1800a3369  lea     r8, [rbp+var_18]; Context
0x1800a336d  mov     rdx, r15; Delimiter
0x1800a3370  xor     ecx, ecx; String
0x1800a3372  mov     r14, rax
0x1800a3375  call    cs:__imp_wcstok_s
0x1800a337c  nop     dword ptr [rax+rax+00h]
0x1800a3381  xor     ecx, ecx
0x1800a3383  jmp     loc_1800A31E9
```
