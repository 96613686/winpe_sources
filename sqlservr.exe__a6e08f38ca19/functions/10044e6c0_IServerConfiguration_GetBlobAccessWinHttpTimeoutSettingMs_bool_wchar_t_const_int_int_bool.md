# IServerConfiguration::GetBlobAccessWinHttpTimeoutSettingMs(bool,wchar_t const *,int *,int,bool)

- ea: `0x10044e6c0`
- end: `0x10044e7bb`
- name: `?GetBlobAccessWinHttpTimeoutSettingMs@IServerConfiguration@@UEAA_N_NPEB_WPEAHH0@Z`
- size: `251`
- prototype: `bool(IServerConfiguration *__hidden this, bool, const wchar_t *, int *, int, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x100401580`
- `0x10044e6c0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x10044e752`
- `KERNEL32!GetEnvironmentVariableW` at `0x10044e752`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e709`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e730`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e709`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10044e730`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10044e761`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x10044e761`

## string_xrefs

- `0x10044e779`: `BlobAccess`
- `0x10044e6f9`: `"serverconfig.cpp"`
- `0x10044e71f`: `"serverconfig.cpp"`

## pseudocode

```c
char __fastcall IServerConfiguration::GetBlobAccessWinHttpTimeoutSettingMs(
        IServerConfiguration *this,
        char a2,
        const wchar_t *a3,
        int *a4,
        int a5,
        bool a6)
{
  int v11; // [rsp+20h] [rbp-48h]
  WCHAR Buffer[12]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a3 )
    utassert_fail(1u, "setting", "\"serverconfig.cpp\"", 1206, 0);
  if ( !a4 )
    utassert_fail(1u, "plVal", "\"serverconfig.cpp\"", 1207, 0);
  *a4 = a5;
  if ( a2 )
  {
    if ( GetEnvironmentVariableW(a3, Buffer, 0x16u) )
    {
      *a4 = _wtoi(Buffer);
      return 1;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    LOBYTE(v11) = a6;
    return (*(__int64 (__fastcall **)(IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)this + 520LL))(
             this,
             L"BlobAccess",
             a3,
             a4,
             v11,
             0);
  }
}

```

## disassembly

```asm
0x10044e6c0  mov     [rsp+arg_8], rbx
0x10044e6c5  push    rsi
0x10044e6c6  push    rdi
0x10044e6c7  push    r14
0x10044e6c9  sub     rsp, 50h
0x10044e6cd  mov     rax, cs:__security_cookie
0x10044e6d4  xor     rax, rsp
0x10044e6d7  mov     [rsp+68h+var_20], rax
0x10044e6dc  mov     rbx, r9
0x10044e6df  mov     rdi, r8
0x10044e6e2  movzx   esi, dl
0x10044e6e5  mov     r14, rcx
0x10044e6e8  test    r8, r8
0x10044e6eb  jnz     short loc_10044E70F
0x10044e6ed  mov     [rsp+68h+var_48], r8
0x10044e6f2  lea     rdx, aSetting; "setting"
0x10044e6f9  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044e700  mov     r9d, 4B6h
0x10044e706  lea     ecx, [rdi+1]
0x10044e709  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044e70f  test    rbx, rbx
0x10044e712  jnz     short loc_10044E736
0x10044e714  mov     r9d, 4B7h
0x10044e71a  mov     [rsp+68h+var_48], rbx
0x10044e71f  lea     r8, aServerconfigCp; "\"serverconfig.cpp\""
0x10044e726  lea     rdx, aPlval; "plVal"
0x10044e72d  lea     ecx, [rbx+1]
0x10044e730  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x10044e736  mov     eax, [rsp+68h+arg_20]
0x10044e73d  mov     [rbx], eax
0x10044e73f  test    sil, sil
0x10044e742  jz      short loc_10044E771
0x10044e744  mov     r8d, 16h; nSize
0x10044e74a  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x10044e74f  mov     rcx, rdi; lpName
0x10044e752  call    cs:__imp_GetEnvironmentVariableW
0x10044e758  test    eax, eax
0x10044e75a  jz      short loc_10044E76D
0x10044e75c  lea     rcx, [rsp+68h+Buffer]; String
0x10044e761  call    cs:__imp__wtoi
0x10044e767  mov     [rbx], eax
0x10044e769  mov     al, 1
0x10044e76b  jmp     short loc_10044E7A0
0x10044e76d  xor     al, al
0x10044e76f  jmp     short loc_10044E7A0
0x10044e771  movzx   eax, [rsp+68h+arg_28]
0x10044e779  lea     rdx, aBlobaccess; "BlobAccess"
0x10044e780  mov     r10, [r14]
0x10044e783  mov     r9, rbx
0x10044e786  mov     [rsp+68h+var_40], 0
0x10044e78f  mov     r8, rdi
0x10044e792  mov     rcx, r14
0x10044e795  mov     byte ptr [rsp+68h+var_48], al
0x10044e799  call    qword ptr [r10+208h]
0x10044e7a0  mov     rcx, [rsp+68h+var_20]
0x10044e7a5  xor     rcx, rsp; StackCookie
0x10044e7a8  call    __security_check_cookie
0x10044e7ad  mov     rbx, [rsp+68h+arg_8]
0x10044e7b2  add     rsp, 50h
0x10044e7b6  pop     r14
0x10044e7b8  pop     rdi
0x10044e7b9  pop     rsi
0x10044e7ba  retn
```
