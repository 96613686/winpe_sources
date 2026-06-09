# WamRegMetabaseConfig::MDGetAllSiteRoots(ushort * *)

- ea: `0x1800058a0`
- end: `0x180005a49`
- name: `?MDGetAllSiteRoots@WamRegMetabaseConfig@@QEAAJPEAPEAG@Z`
- size: `425`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800030b0`

## callees

- `0x180001044`
- `0x1800058a0`
- `0x180006822`
- `0x180006850`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000596d`
- `msvcrt!wcscat_s` at `0x180005982`
- `msvcrt!wcscat_s` at `0x18000596d`
- `msvcrt!wcscat_s` at `0x180005982`
- `msvcrt!wcscpy_s` at `0x180005958`
- `msvcrt!wcscpy_s` at `0x180005958`
- `msvcrt!_wtoi` at `0x18000592d`
- `msvcrt!_wtoi` at `0x18000592d`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800058eb`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x1800058eb`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x180005a11`
- `iisutil!?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z` at `0x180005a11`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005a1e`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005a1e`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180005992`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180005992`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDGetAllSiteRoots(WamRegMetabaseConfig *this, unsigned __int16 **a2)
{
  int v3; // ebx
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rax
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[48]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v10; // [rsp+68h] [rbp-98h]
  wchar_t Destination[256]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String[256]; // [rsp+270h] [rbp+170h] BYREF

  *a2 = 0;
  v3 = 0;
  memset_0(String, 0, sizeof(String));
  MULTISZ::MULTISZ((MULTISZ *)v9);
  if ( (*(int (__fastcall **)(LPVOID, _QWORD, const wchar_t *, wchar_t *, _DWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                 + 48LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         L"/LM/W3SVC/",
         String,
         0) >= 0 )
  {
    do
    {
      if ( _wtoi(String) )
      {
        memset_0(Destination, 0, sizeof(Destination));
        wcscpy_s(Destination, 0x100u, L"/LM/W3SVC/");
        wcscat_s(Destination, 0x100u, String);
        wcscat_s(Destination, 0x100u, L"/ROOT/");
        if ( !MULTISZ::Append((MULTISZ *)v9, Destination) )
          goto LABEL_8;
      }
    }
    while ( (*(int (__fastcall **)(LPVOID, _QWORD, const wchar_t *, wchar_t *, int))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                   + 48LL))(
              WamRegMetabaseConfig::m_pMetabase,
              0,
              L"/LM/W3SVC/",
              String,
              ++v3) >= 0 );
  }
  v4 = v10;
  v8 = 0;
  v5 = (unsigned __int16 *)operator new(saturated_mul(v10, 2u));
  *a2 = v5;
  if ( !v5 )
  {
LABEL_8:
    v6 = -2147024882;
    goto LABEL_7;
  }
  v8 = v4;
  MULTISZ::CopyToBuffer((MULTISZ *)v9, v5, &v8);
  v6 = 0;
LABEL_7:
  MULTISZ::~MULTISZ((MULTISZ *)v9);
  return v6;
}

```

## disassembly

```asm
0x1800058a0  push    rbp
0x1800058a2  push    rbx
0x1800058a3  push    rdi
0x1800058a4  push    r14
0x1800058a6  lea     rbp, [rsp-388h]
0x1800058ae  sub     rsp, 488h
0x1800058b5  mov     rax, cs:__security_cookie
0x1800058bc  xor     rax, rsp
0x1800058bf  mov     [rbp+3A0h+var_30], rax
0x1800058c6  mov     rdi, rdx
0x1800058c9  mov     qword ptr [rdx], 0
0x1800058d0  xor     edx, edx; Val
0x1800058d2  lea     rcx, [rbp+3A0h+String]; void *
0x1800058d9  mov     r8d, 200h; Size
0x1800058df  xor     ebx, ebx
0x1800058e1  call    memset_0
0x1800058e6  lea     rcx, [rsp+4A0h+var_468]
0x1800058eb  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x1800058f1  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800058f8  lea     r9, [rbp+3A0h+String]
0x1800058ff  lea     r8, aLmW3svc_0; "/LM/W3SVC/"
0x180005906  mov     [rsp+4A0h+var_480], ebx
0x18000590a  xor     edx, edx
0x18000590c  mov     rax, [rcx]
0x18000590f  mov     rax, [rax+30h]
0x180005913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005918  test    eax, eax
0x18000591a  js      loc_1800059D1
0x180005920  mov     r14d, 100h
0x180005926  lea     rcx, [rbp+3A0h+String]; String
0x18000592d  call    cs:__imp__wtoi
0x180005933  test    eax, eax
0x180005935  jz      short loc_1800059A0
0x180005937  xor     edx, edx; Val
0x180005939  lea     rcx, [rsp+4A0h+Destination]; void *
0x18000593e  mov     r8d, 200h; Size
0x180005944  call    memset_0
0x180005949  lea     r8, aLmW3svc_0; "/LM/W3SVC/"
0x180005950  mov     rdx, r14; SizeInWords
0x180005953  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180005958  call    cs:__imp_wcscpy_s
0x18000595e  lea     r8, [rbp+3A0h+String]; Source
0x180005965  mov     rdx, r14; SizeInWords
0x180005968  lea     rcx, [rsp+4A0h+Destination]; Destination
0x18000596d  call    cs:__imp_wcscat_s
0x180005973  lea     r8, aRoot; "/ROOT/"
0x18000597a  mov     rdx, r14; SizeInWords
0x18000597d  lea     rcx, [rsp+4A0h+Destination]; Destination
0x180005982  call    cs:__imp_wcscat_s
0x180005988  lea     rdx, [rsp+4A0h+Destination]
0x18000598d  lea     rcx, [rsp+4A0h+var_468]
0x180005992  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180005998  test    eax, eax
0x18000599a  jz      loc_180005A42
0x1800059a0  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800059a7  lea     r9, [rbp+3A0h+String]
0x1800059ae  inc     ebx
0x1800059b0  lea     r8, aLmW3svc_0; "/LM/W3SVC/"
0x1800059b7  xor     edx, edx
0x1800059b9  mov     [rsp+4A0h+var_480], ebx
0x1800059bd  mov     rax, [rcx]
0x1800059c0  mov     rax, [rax+30h]
0x1800059c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c9  test    eax, eax
0x1800059cb  jns     loc_180005926
0x1800059d1  mov     ebx, [rsp+4A0h+var_438]
0x1800059d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800059dc  mov     eax, 2
0x1800059e1  mov     [rsp+4A0h+var_470], 0
0x1800059e9  mul     rbx
0x1800059ec  cmovb   rax, rcx
0x1800059f0  mov     rcx, rax; Size
0x1800059f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800059f8  mov     [rdi], rax
0x1800059fb  test    rax, rax
0x1800059fe  jz      short loc_180005A42
0x180005a00  lea     r8, [rsp+4A0h+var_470]
0x180005a05  mov     [rsp+4A0h+var_470], ebx
0x180005a09  mov     rdx, rax
0x180005a0c  lea     rcx, [rsp+4A0h+var_468]
0x180005a11  call    cs:__imp_?CopyToBuffer@MULTISZ@@QEBAHPEAGPEAK@Z; MULTISZ::CopyToBuffer(ushort *,ulong *)
0x180005a17  xor     ebx, ebx
0x180005a19  lea     rcx, [rsp+4A0h+var_468]
0x180005a1e  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005a24  mov     eax, ebx
0x180005a26  mov     rcx, [rbp+3A0h+var_30]
0x180005a2d  xor     rcx, rsp; StackCookie
0x180005a30  call    __security_check_cookie
0x180005a35  add     rsp, 488h
0x180005a3c  pop     r14
0x180005a3e  pop     rdi
0x180005a3f  pop     rbx
0x180005a40  pop     rbp
0x180005a41  retn
0x180005a42  mov     ebx, 8007000Eh
0x180005a47  jmp     short loc_180005A19
```
