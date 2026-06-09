# CUpdateServiceManager::SetOption(wchar_t *,tagVARIANT)

- ea: `0x180072ac0`
- end: `0x180072c2d`
- name: `?SetOption@CUpdateServiceManager@@UEAAJPEA_WUtagVARIANT@@@Z`
- size: `365`
- prototype: `int(CUpdateServiceManager *__hidden this, wchar_t *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007ecc`
- `0x180072ac0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180072b70`
- `RPCRT4!UuidFromStringW` at `0x180072b70`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072b32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072bb4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072b32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072bb4`
- `OLEAUT32!__imp_SysStringLen` at `0x180072afa`
- `OLEAUT32!__imp_SysStringLen` at `0x180072b51`
- `OLEAUT32!__imp_SysStringLen` at `0x180072afa`
- `OLEAUT32!__imp_SysStringLen` at `0x180072b51`

## string_xrefs

- `0x180072b7f`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x180072c01`: `C:\__w\1\s\src\Client\comapi\UpdateServiceManager.cpp`
- `0x180072b14`: `AllowedServiceID`

## pseudocode

```c
unsigned int __fastcall CUpdateServiceManager::SetOption(
        CUpdateServiceManager *this,
        wchar_t *a2,
        struct tagVARIANT *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // ebx
  unsigned int v9; // eax
  bool v11; // zf
  unsigned int lpString2; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *((_DWORD *)this - 2) != 1 )
  {
    v8 = 0;
    if ( !SysStringLen(a2) )
    {
      v7 = 274;
LABEL_22:
      v6 = -2147024809;
      goto LABEL_23;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"AllowedServiceID", -1) == 2 )
    {
      if ( a3->vt != 8 )
      {
        v7 = 278;
        goto LABEL_22;
      }
      if ( !SysStringLen(a3->bstrVal) )
      {
        v7 = 279;
        goto LABEL_22;
      }
      v9 = UuidFromStringW(a3->bstrVal, (UUID *)((char *)this + 268));
      if ( v9 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x118,
                 (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
                 (const char *)v9,
                 lpString2);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"AllowWarningUI", -1) != 2 )
      {
        v7 = 290;
        goto LABEL_22;
      }
      if ( a3->vt != 11 )
      {
        v7 = 284;
        goto LABEL_22;
      }
      v11 = a3->iVal == 0xFFFF;
      if ( a3->iVal != -1 )
      {
        if ( a3->iVal )
        {
          v7 = 285;
          goto LABEL_22;
        }
        v11 = a3->iVal == 0xFFFF;
      }
      LOBYTE(v8) = v11;
      *((_DWORD *)this + 66) = v8;
    }
    return 0;
  }
  v6 = -2145124298;
  v7 = 271;
LABEL_23:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\UpdateServiceManager.cpp",
    (const char *)v6,
    lpString2);
  return v6;
}

```

## disassembly

```asm
0x180072ac0  mov     rax, rsp
0x180072ac3  mov     [rax+8], rbx
0x180072ac7  mov     [rax+10h], rbp
0x180072acb  mov     [rax+18h], rsi
0x180072acf  mov     [rax+20h], rdi
0x180072ad3  push    r14
0x180072ad5  sub     rsp, 30h
0x180072ad9  cmp     dword ptr [rcx-8], 1
0x180072add  mov     rdi, r8
0x180072ae0  mov     rbp, rdx
0x180072ae3  mov     rsi, rcx
0x180072ae6  jnz     short loc_180072AF7
0x180072ae8  mov     ebx, 80240036h
0x180072aed  mov     edx, 10Fh
0x180072af2  jmp     loc_180072BFC
0x180072af7  mov     rcx, rbp; pbstr
0x180072afa  call    cs:__imp_SysStringLen
0x180072b00  xor     ebx, ebx
0x180072b02  test    eax, eax
0x180072b04  jnz     short loc_180072B10
0x180072b06  mov     edx, 112h
0x180072b0b  jmp     loc_180072BF7
0x180072b10  or      r14d, 0FFFFFFFFh
0x180072b14  lea     rax, aAllowedservice; "AllowedServiceID"
0x180072b1b  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x180072b20  mov     r9d, r14d; cchCount1
0x180072b23  mov     r8, rbp; lpString1
0x180072b26  mov     [rsp+38h+lpString2], rax; unsigned int
0x180072b2b  lea     edx, [r14+2]; dwCmpFlags
0x180072b2f  lea     ecx, [rdx+7Eh]; Locale
0x180072b32  call    cs:__imp_CompareStringW
0x180072b38  cmp     eax, 2
0x180072b3b  jnz     short loc_180072B95
0x180072b3d  cmp     word ptr [rdi], 8
0x180072b41  jz      short loc_180072B4D
0x180072b43  mov     edx, 116h
0x180072b48  jmp     loc_180072BF7
0x180072b4d  mov     rcx, [rdi+8]; pbstr
0x180072b51  call    cs:__imp_SysStringLen
0x180072b57  test    eax, eax
0x180072b59  jnz     short loc_180072B65
0x180072b5b  mov     edx, 117h
0x180072b60  jmp     loc_180072BF7
0x180072b65  mov     rcx, [rdi+8]; StringUuid
0x180072b69  lea     rdx, [rsi+10Ch]; Uuid
0x180072b70  call    cs:__imp_UuidFromStringW
0x180072b76  test    eax, eax
0x180072b78  jz      short loc_180072BEE
0x180072b7a  mov     rcx, [rsp+38h]; this
0x180072b7f  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180072b86  mov     r9d, eax; char *
0x180072b89  mov     edx, 118h; void *
0x180072b8e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180072b93  jmp     short loc_180072C12
0x180072b95  mov     edx, 1; dwCmpFlags
0x180072b9a  mov     [rsp+38h+cchCount2], r14d; cchCount2
0x180072b9f  lea     rax, aAllowwarningui; "AllowWarningUI"
0x180072ba6  mov     r9d, r14d; cchCount1
0x180072ba9  mov     r8, rbp; lpString1
0x180072bac  mov     [rsp+38h+lpString2], rax; int
0x180072bb1  lea     ecx, [rdx+7Eh]; Locale
0x180072bb4  call    cs:__imp_CompareStringW
0x180072bba  cmp     eax, 2
0x180072bbd  jnz     short loc_180072BF2
0x180072bbf  cmp     word ptr [rdi], 0Bh
0x180072bc3  jz      short loc_180072BCC
0x180072bc5  mov     edx, 11Ch
0x180072bca  jmp     short loc_180072BF7
0x180072bcc  cmp     [rdi+8], r14w
0x180072bd1  jz      short loc_180072BE5
0x180072bd3  cmp     bx, [rdi+8]
0x180072bd7  jz      short loc_180072BE0
0x180072bd9  mov     edx, 11Dh
0x180072bde  jmp     short loc_180072BF7
0x180072be0  cmp     [rdi+8], r14w
0x180072be5  setz    bl
0x180072be8  mov     [rsi+108h], ebx
0x180072bee  xor     eax, eax
0x180072bf0  jmp     short loc_180072C12
0x180072bf2  mov     edx, 122h; void *
0x180072bf7  mov     ebx, 80070057h
0x180072bfc  mov     rcx, [rsp+38h]; this
0x180072c01  lea     r8, aCW1SSrcClientC_50; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180072c08  mov     r9d, ebx; char *
0x180072c0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072c10  mov     eax, ebx
0x180072c12  mov     rbx, [rsp+38h+arg_0]
0x180072c17  mov     rbp, [rsp+38h+arg_8]
0x180072c1c  mov     rsi, [rsp+38h+arg_10]
0x180072c21  mov     rdi, [rsp+38h+arg_18]
0x180072c26  add     rsp, 30h
0x180072c2a  pop     r14
0x180072c2c  retn
```
