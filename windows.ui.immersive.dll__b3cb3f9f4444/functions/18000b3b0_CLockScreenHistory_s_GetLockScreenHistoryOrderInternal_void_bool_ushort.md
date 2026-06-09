# CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)

- ea: `0x18000b3b0`
- end: `0x18000b5af`
- name: `?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z`
- size: `511`
- prototype: `__int64 __fastcall(void *, bool, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009890`
- `0x18000c600`
- `0x1800366e8`
- `0x180037e20`
- `0x180042244`
- `0x1800516fc`
- `0x180051898`
- `0x180053050`
- `0x1800bb3ec`
- `0x1800bffa4`

## callees

- `0x18000b3b0`
- `0x18000b5b8`
- `0x18000da00`
- `0x18000da90`
- `0x180026440`
- `0x18003d244`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b4d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b4d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b496`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b401`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b401`

## string_xrefs

- `0x18000b434`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *a1, char a2, unsigned __int16 **a3)
{
  bool v5; // r14
  WCHAR *v6; // rbp
  int Error; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // esi
  int v12; // r9d
  int v13; // eax
  __int64 v14; // rax
  unsigned int i; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-258h] BYREF
  void *v18; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 v19[264]; // [rsp+50h] [rbp-248h] BYREF

  v5 = 1;
  if ( a3 )
    *a3 = 0;
  v18 = 0;
  v6 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), v10 = Error, Error >= 0) )
  {
    v10 = StringCchPrintfW(
            v19,
            0x104u,
            L"%s\\%s\\%s\\%s",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
            StringSid);
    if ( v10 >= 0 )
    {
      v13 = SHRegAllocData(HKEY_LOCAL_MACHINE, v19, &Class, v12, &v18, (unsigned int *)L"AnyoneRead");
      v6 = (WCHAR *)v18;
      v10 = v13;
    }
    LocalFree(StringSid);
    v11 = v10;
    if ( v10 < 0 )
      goto LABEL_17;
    v8 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v6[v14] );
    if ( v14 == 6 )
    {
      v5 = CompareStringOrdinal(v6, -1, L"ZYXWVU", -1, 0) == 2;
      if ( a3 )
      {
        *a3 = v6;
        goto LABEL_15;
      }
    }
    else if ( a3 )
    {
LABEL_15:
      if ( *a3 )
        goto LABEL_19;
    }
    CoTaskMemFree(v6);
    goto LABEL_17;
  }
  v11 = Error;
LABEL_17:
  if ( !a3 )
    goto LABEL_22;
  if ( !*a3 )
  {
LABEL_21:
    v11 = _AllocString<CTCoAllocPolicy>(v9, v8, L"ZYXWVU", a3);
    goto LABEL_22;
  }
LABEL_19:
  v9 = 0x80000000LL;
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024882 )
    goto LABEL_21;
LABEL_22:
  if ( a2 && a3 && (int)LockScreenPathFromPolicy(0) >= 0 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( (*a3)[i] == word_1801357F0[0] )
      {
        (*a3)[i] = 80;
        break;
      }
    }
  }
  if ( v11 >= 0 )
    return v5;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000b3b0  mov     [rsp+arg_8], rbx
0x18000b3b5  mov     [rsp+arg_18], rbp
0x18000b3ba  push    rsi
0x18000b3bb  push    rdi
0x18000b3bc  push    r12
0x18000b3be  push    r14
0x18000b3c0  push    r15
0x18000b3c2  sub     rsp, 270h
0x18000b3c9  mov     rax, cs:__security_cookie
0x18000b3d0  xor     rax, rsp
0x18000b3d3  mov     [rsp+298h+var_38], rax
0x18000b3db  xor     r12d, r12d
0x18000b3de  mov     rdi, r8
0x18000b3e1  mov     r15b, dl
0x18000b3e4  mov     r14b, 1
0x18000b3e7  test    r8, r8
0x18000b3ea  jz      short loc_18000B3EF
0x18000b3ec  mov     [r8], r12
0x18000b3ef  lea     rdx, [rsp+298h+StringSid]; StringSid
0x18000b3f4  mov     [rsp+298h+var_250], r12
0x18000b3f9  mov     rbp, r12
0x18000b3fc  mov     [rsp+298h+StringSid], r12
0x18000b401  call    cs:__imp_ConvertSidToStringSidW
0x18000b408  nop     dword ptr [rax+rax+00h]
0x18000b40d  test    eax, eax
0x18000b40f  jnz     short loc_18000B423
0x18000b411  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b416  mov     ebx, eax
0x18000b418  test    eax, eax
0x18000b41a  jns     short loc_18000B423
0x18000b41c  mov     esi, eax
0x18000b41e  jmp     loc_18000B508
0x18000b423  mov     rcx, [rsp+298h+StringSid]
0x18000b428  lea     rax, aLockscreen; "LockScreen"
0x18000b42f  mov     [rsp+298h+var_268], rax
0x18000b434  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000b43b  mov     rax, cs:off_1800EE7D8; "AnyoneRead"
0x18000b442  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18000b449  mov     [rsp+298h+var_270], rax; unsigned int *
0x18000b44e  mov     edx, 104h; unsigned __int64
0x18000b453  mov     qword ptr [rsp+298h+bIgnoreCase], rcx
0x18000b458  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x18000b45d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b462  mov     ebx, eax
0x18000b464  test    eax, eax
0x18000b466  js      short loc_18000B491
0x18000b468  lea     rax, [rsp+298h+var_250]
0x18000b46d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18000b474  lea     r8, Class; unsigned __int16 *
0x18000b47b  mov     qword ptr [rsp+298h+bIgnoreCase], rax; void **
0x18000b480  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x18000b485  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18000b48a  mov     rbp, [rsp+298h+var_250]
0x18000b48f  mov     ebx, eax
0x18000b491  mov     rcx, [rsp+298h+StringSid]; hMem
0x18000b496  call    cs:__imp_LocalFree
0x18000b49d  nop     dword ptr [rax+rax+00h]
0x18000b4a2  mov     esi, ebx
0x18000b4a4  test    ebx, ebx
0x18000b4a6  js      short loc_18000B508
0x18000b4a8  or      rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18000b4ac  mov     rax, rdx
0x18000b4af  inc     rax
0x18000b4b2  cmp     [rbp+rax*2+0], r12w
0x18000b4b8  jnz     short loc_18000B4AF
0x18000b4ba  cmp     rax, 6
0x18000b4be  jnz     short loc_18000B4EF
0x18000b4c0  mov     r9d, edx; cchCount2
0x18000b4c3  mov     [rsp+298h+bIgnoreCase], r12d; bIgnoreCase
0x18000b4c8  lea     r8, String2; "ZYXWVU"
0x18000b4cf  mov     rcx, rbp; lpString1
0x18000b4d2  call    cs:__imp_CompareStringOrdinal
0x18000b4d9  nop     dword ptr [rax+rax+00h]
0x18000b4de  cmp     eax, 2
0x18000b4e1  setz    r14b
0x18000b4e5  test    rdi, rdi
0x18000b4e8  jz      short loc_18000B4F9
0x18000b4ea  mov     [rdi], rbp
0x18000b4ed  jmp     short loc_18000B4F4
0x18000b4ef  test    rdi, rdi
0x18000b4f2  jz      short loc_18000B4F9
0x18000b4f4  cmp     [rdi], r12
0x18000b4f7  jnz     short loc_18000B512
0x18000b4f9  mov     rcx, rbp; pv
0x18000b4fc  call    cs:__imp_CoTaskMemFree
0x18000b503  nop     dword ptr [rax+rax+00h]
0x18000b508  test    rdi, rdi
0x18000b50b  jz      short loc_18000B537
0x18000b50d  cmp     [rdi], r12
0x18000b510  jz      short loc_18000B526
0x18000b512  mov     ecx, 80000000h
0x18000b517  lea     eax, [rbx+rcx]
0x18000b51a  test    ecx, eax
0x18000b51c  jnz     short loc_18000B537
0x18000b51e  cmp     ebx, 8007000Eh
0x18000b524  jz      short loc_18000B537
0x18000b526  mov     r9, rdi
0x18000b529  lea     r8, String2; "ZYXWVU"
0x18000b530  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000b535  mov     esi, eax
0x18000b537  test    r15b, r15b
0x18000b53a  jz      short loc_18000B572
0x18000b53c  test    rdi, rdi
0x18000b53f  jz      short loc_18000B572
0x18000b541  xor     ecx, ecx; unsigned __int16 **
0x18000b543  call    ?LockScreenPathFromPolicy@@YAJPEAPEAG@Z; LockScreenPathFromPolicy(ushort * *)
0x18000b548  test    eax, eax
0x18000b54a  js      short loc_18000B572
0x18000b54c  movzx   r8d, cs:word_1801357F0
0x18000b554  mov     eax, r12d
0x18000b557  cmp     eax, 6
0x18000b55a  jnb     short loc_18000B572
0x18000b55c  mov     rdx, [rdi]
0x18000b55f  mov     ecx, eax
0x18000b561  cmp     [rdx+rcx*2], r8w
0x18000b566  jz      short loc_18000B56C
0x18000b568  inc     eax
0x18000b56a  jmp     short loc_18000B557
0x18000b56c  mov     word ptr [rdx+rcx*2], 50h ; 'P'
0x18000b572  test    esi, esi
0x18000b574  js      short loc_18000B580
0x18000b576  test    r14b, r14b
0x18000b579  mov     esi, r12d
0x18000b57c  setnz   sil
0x18000b580  mov     eax, esi
0x18000b582  mov     rcx, [rsp+298h+var_38]
0x18000b58a  xor     rcx, rsp; StackCookie
0x18000b58d  call    __security_check_cookie
0x18000b592  lea     r11, [rsp+298h+var_28]
0x18000b59a  mov     rbx, [r11+38h]
0x18000b59e  mov     rbp, [r11+48h]
0x18000b5a2  mov     rsp, r11
0x18000b5a5  pop     r15
0x18000b5a7  pop     r14
0x18000b5a9  pop     r12
0x18000b5ab  pop     rdi
0x18000b5ac  pop     rsi
0x18000b5ad  retn
```
