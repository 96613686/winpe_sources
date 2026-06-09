# StpGetProfileFilePath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)

- ea: `0x180005430`
- end: `0x1800055fc`
- name: `?StpGetProfileFilePath@@YAKPEBU_GUID@@0HPEAG_K@Z`
- size: `460`
- prototype: `unsigned int __fastcall(GUID *rguid, GUID *, int, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x1800052a0`
- `0x180005430`
- `0x180019a20`
- `0x18001aea0`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000547c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000547c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000549a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800054ba`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000549a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800054ba`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomStorageRootPath` at `0x1800055c6`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomStorageRootPath` at `0x1800055c6`

## pseudocode

```c
__int64 __fastcall StpGetProfileFilePath(GUID *rguid, GUID *a2, __int64 a3, unsigned __int16 *a4)
{
  int CustomStorageRootPath; // eax
  unsigned int v8; // ecx
  int v9; // eax
  OLECHAR sz[40]; // [rsp+50h] [rbp-2D8h] BYREF
  OLECHAR v12[40]; // [rsp+A0h] [rbp-288h] BYREF
  _BYTE v13[528]; // [rsp+F0h] [rbp-238h] BYREF

  if ( (unsigned __int8)IsGetCustomRegRootPathPresent() )
    CustomStorageRootPath = GetCustomStorageRootPath(v13, 260, 0);
  else
    CustomStorageRootPath = GetBasicProfileFolderPath(4, 0, v13, 260);
  v8 = CustomStorageRootPath;
  if ( CustomStorageRootPath >= 0 )
    goto LABEL_4;
  if ( (CustomStorageRootPath & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)CustomStorageRootPath;
  if ( !v8 )
  {
LABEL_4:
    StringFromGUID2(a2, sz, 39);
    if ( rguid )
    {
      StringFromGUID2(rguid, v12, 39);
      v9 = StringCchPrintfW(
             a4,
             0x104u,
             L"%s\\%s\\%s\\%s\\%s\\%s.%s",
             v13,
             L"Microsoft\\Wlansvc",
             L"Profiles",
             L"Interfaces",
             v12,
             sz,
             L"xml");
    }
    else
    {
      v9 = StringCchPrintfW(
             a4,
             0x104u,
             L"%s\\%s\\%s\\%s\\%s.%s",
             v13,
             L"Microsoft\\Wlansvc",
             L"Profiles",
             L"Machine",
             sz,
             L"xml");
    }
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        return (unsigned __int16)v9;
    }
    else
    {
      return 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180005430  mov     [rsp+arg_10], rbx
0x180005435  push    rbp
0x180005436  push    rsi
0x180005437  push    rdi
0x180005438  sub     rsp, 310h
0x18000543f  mov     rax, cs:__security_cookie
0x180005446  xor     rax, rsp
0x180005449  mov     [rsp+328h+var_28], rax
0x180005451  mov     rbp, r9
0x180005454  mov     rsi, rdx
0x180005457  mov     rdi, rcx
0x18000545a  call    IsGetCustomRegRootPathPresent
0x18000545f  mov     ebx, 104h
0x180005464  test    al, al
0x180005466  jnz     loc_1800055B8
0x18000546c  xor     edx, edx
0x18000546e  lea     r8, [rsp+328h+var_238]
0x180005476  mov     r9d, ebx
0x180005479  lea     ecx, [rdx+4]
0x18000547c  call    cs:__imp_GetBasicProfileFolderPath
0x180005482  mov     ecx, eax
0x180005484  test    eax, eax
0x180005486  js      loc_1800055D1
0x18000548c  mov     r8d, 27h ; '''; cchMax
0x180005492  lea     rdx, [rsp+328h+sz]; lpsz
0x180005497  mov     rcx, rsi; rguid
0x18000549a  call    cs:__imp_StringFromGUID2
0x1800054a0  test    rdi, rdi
0x1800054a3  jz      loc_180005552
0x1800054a9  mov     r8d, 27h ; '''; cchMax
0x1800054af  lea     rdx, [rsp+328h+var_288]; lpsz
0x1800054b7  mov     rcx, rdi; rguid
0x1800054ba  call    cs:__imp_StringFromGUID2
0x1800054c0  lea     rax, aXml; "xml"
0x1800054c7  mov     rdx, rbx; unsigned __int64
0x1800054ca  mov     [rsp+328h+var_2E0], rax
0x1800054cf  lea     r9, [rsp+328h+var_238]
0x1800054d7  lea     rax, [rsp+328h+sz]
0x1800054dc  mov     rcx, rbp; unsigned __int16 *
0x1800054df  mov     [rsp+328h+var_2E8], rax
0x1800054e4  lea     r8, aSSSSSSS; "%s\\%s\\%s\\%s\\%s\\%s.%s"
0x1800054eb  lea     rax, [rsp+328h+var_288]
0x1800054f3  mov     [rsp+328h+var_2F0], rax
0x1800054f8  lea     rax, aInterfaces; "Interfaces"
0x1800054ff  mov     [rsp+328h+var_2F8], rax
0x180005504  lea     rax, aProfiles; "Profiles"
0x18000550b  mov     [rsp+328h+var_300], rax
0x180005510  lea     rax, aMicrosoftWlans; "Microsoft\\Wlansvc"
0x180005517  mov     [rsp+328h+var_308], rax
0x18000551c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005521  mov     ecx, eax
0x180005523  test    eax, eax
0x180005525  js      loc_1800055E2
0x18000552b  xor     ecx, ecx
0x18000552d  mov     eax, ecx
0x18000552f  mov     rcx, [rsp+328h+var_28]
0x180005537  xor     rcx, rsp; StackCookie
0x18000553a  call    __security_check_cookie
0x18000553f  mov     rbx, [rsp+328h+arg_10]
0x180005547  add     rsp, 310h
0x18000554e  pop     rdi
0x18000554f  pop     rsi
0x180005550  pop     rbp
0x180005551  retn
0x180005552  lea     rax, aXml; "xml"
0x180005559  mov     rdx, rbx; unsigned __int64
0x18000555c  mov     [rsp+328h+var_2E8], rax
0x180005561  lea     r9, [rsp+328h+var_238]
0x180005569  lea     rax, [rsp+328h+sz]
0x18000556e  mov     rcx, rbp; unsigned __int16 *
0x180005571  mov     [rsp+328h+var_2F0], rax
0x180005576  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s.%s"
0x18000557d  lea     rax, aMachine_0; "Machine"
0x180005584  mov     [rsp+328h+var_2F8], rax
0x180005589  lea     rax, aProfiles; "Profiles"
0x180005590  mov     [rsp+328h+var_300], rax
0x180005595  lea     rax, aMicrosoftWlans; "Microsoft\\Wlansvc"
0x18000559c  mov     [rsp+328h+var_308], rax
0x1800055a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800055a6  jmp     loc_180005521
0x1800055ab  test    ecx, ecx
0x1800055ad  jnz     loc_18000552D
0x1800055b3  jmp     loc_18000548C
0x1800055b8  xor     r8d, r8d
0x1800055bb  lea     rcx, [rsp+328h+var_238]
0x1800055c3  mov     rdx, rbx
0x1800055c6  call    cs:__imp_GetCustomStorageRootPath
0x1800055cc  jmp     loc_180005482
0x1800055d1  and     eax, 1FFF0000h
0x1800055d6  cmp     eax, 70000h
0x1800055db  jnz     short loc_1800055AB
0x1800055dd  movzx   ecx, cx
0x1800055e0  jmp     short loc_1800055AB
0x1800055e2  mov     eax, ecx
0x1800055e4  and     eax, 1FFF0000h
0x1800055e9  cmp     eax, 70000h
0x1800055ee  jnz     loc_18000552D
0x1800055f4  movzx   ecx, cx
0x1800055f7  jmp     loc_18000552D
```
