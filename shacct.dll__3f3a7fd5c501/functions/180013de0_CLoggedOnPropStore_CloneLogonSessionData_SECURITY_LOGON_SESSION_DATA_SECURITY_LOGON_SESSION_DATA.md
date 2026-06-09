# CLoggedOnPropStore::_CloneLogonSessionData(_SECURITY_LOGON_SESSION_DATA *,_SECURITY_LOGON_SESSION_DATA * *)

- ea: `0x180013de0`
- end: `0x180013f3b`
- name: `?_CloneLogonSessionData@CLoggedOnPropStore@@AEAAJPEAU_SECURITY_LOGON_SESSION_DATA@@PEAPEAU2@@Z`
- size: `347`
- prototype: `__int64 __fastcall(CLoggedOnPropStore *__hidden this, struct _SECURITY_LOGON_SESSION_DATA *, struct _SECURITY_LOGON_SESSION_DATA **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800140ec`

## callees

- `0x18000bdac`
- `0x180013de0`
- `0x180013ffc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013eed`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180013eed`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013ec5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013ec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ed0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013e06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ed0`

## pseudocode

```c
__int64 __fastcall CLoggedOnPropStore::_CloneLogonSessionData(
        CLoggedOnPropStore *this,
        struct _SECURITY_LOGON_SESSION_DATA *a2,
        struct _UNICODE_STRING **a3)
{
  int v3; // edi
  struct _UNICODE_STRING *v6; // rax
  struct _UNICODE_STRING *v7; // rbx
  CLoggedOnPropStore *v8; // rcx
  PSID Sid; // rcx
  DWORD LengthSid; // r14d
  WCHAR *v11; // rax
  WCHAR *v12; // rbp

  *a3 = 0;
  v3 = -2147024882;
  v6 = (struct _UNICODE_STRING *)CoTaskMemAlloc(0x110u);
  v7 = v6;
  if ( v6 )
  {
    *(_DWORD *)&v6->Length = a2->Size;
    *(_DWORD *)&v6[4].Length = a2->LogonType;
    *(_DWORD *)(&v6[4].MaximumLength + 1) = a2->Session;
    *(_QWORD *)&v6[5].Length = a2->LogonTime.QuadPart;
    v3 = _CopyUnicodeString((const struct _UNICODE_STRING *)&a2->UserName, v6 + 1);
    if ( v3 >= 0 )
    {
      v3 = _CopyUnicodeString((const struct _UNICODE_STRING *)&a2->LogonDomain, v7 + 2);
      if ( v3 >= 0 )
      {
        v3 = _CopyUnicodeString((const struct _UNICODE_STRING *)&a2->AuthenticationPackage, v7 + 3);
        if ( v3 >= 0 )
        {
          v3 = _CopyUnicodeString(
                 (const struct _UNICODE_STRING *)&a2->LogonServer,
                 (struct _UNICODE_STRING *)((char *)v7 + 88));
          if ( v3 >= 0 )
          {
            v3 = _CopyUnicodeString(
                   (const struct _UNICODE_STRING *)&a2->DnsDomainName,
                   (struct _UNICODE_STRING *)((char *)v7 + 104));
            if ( v3 >= 0 )
            {
              v3 = _CopyUnicodeString(
                     (const struct _UNICODE_STRING *)&a2->Upn,
                     (struct _UNICODE_STRING *)((char *)v7 + 120));
              if ( v3 >= 0 )
              {
                Sid = a2->Sid;
                a2->LogonId = *(LUID *)(&v7->MaximumLength + 1);
                if ( Sid )
                {
                  v3 = -2147024882;
                  LengthSid = GetLengthSid(Sid);
                  v11 = (WCHAR *)CoTaskMemAlloc(LengthSid);
                  v12 = v11;
                  if ( !v11 )
                    goto LABEL_13;
                  v3 = -2147467259;
                  if ( CopySid(LengthSid, v11, a2->Sid) )
                  {
                    v7[4].Buffer = v12;
                    v12 = 0;
                    v3 = 0;
                  }
                  CoTaskMemFree(v12);
                  if ( v3 < 0 )
                    goto LABEL_13;
                }
                else
                {
                  v7[4].Buffer = 0;
                }
                *a3 = v7;
                v7 = 0;
                goto LABEL_14;
              }
            }
          }
        }
      }
    }
LABEL_13:
    CLoggedOnPropStore::_ClearLogonSessionData(v8, (struct _SECURITY_LOGON_SESSION_DATA *)v7);
LABEL_14:
    CoTaskMemFree(v7);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013de0  push    rbx
0x180013de2  push    rbp
0x180013de3  push    rsi
0x180013de4  push    rdi
0x180013de5  push    r14
0x180013de7  push    r15
0x180013de9  sub     rsp, 28h
0x180013ded  mov     ebp, 8007000Eh
0x180013df2  mov     qword ptr [r8], 0
0x180013df9  mov     ecx, 110h; cb
0x180013dfe  mov     edi, ebp
0x180013e00  mov     r15, r8
0x180013e03  mov     rsi, rdx
0x180013e06  call    cs:__imp_CoTaskMemAlloc
0x180013e0c  mov     rbx, rax
0x180013e0f  test    rax, rax
0x180013e12  jz      loc_180013F1D
0x180013e18  mov     eax, [rsi]
0x180013e1a  lea     rdx, [rbx+10h]; struct _UNICODE_STRING *
0x180013e1e  mov     [rbx], eax
0x180013e20  lea     rcx, [rsi+10h]; struct _UNICODE_STRING *
0x180013e24  mov     eax, [rsi+40h]
0x180013e27  mov     [rbx+40h], eax
0x180013e2a  mov     eax, [rsi+44h]
0x180013e2d  mov     [rbx+44h], eax
0x180013e30  mov     rax, [rsi+50h]
0x180013e34  mov     [rbx+50h], rax
0x180013e38  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013e3d  mov     edi, eax
0x180013e3f  test    eax, eax
0x180013e41  js      loc_180013F0C
0x180013e47  lea     rdx, [rbx+20h]; struct _UNICODE_STRING *
0x180013e4b  lea     rcx, [rsi+20h]; struct _UNICODE_STRING *
0x180013e4f  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013e54  mov     edi, eax
0x180013e56  test    eax, eax
0x180013e58  js      loc_180013F0C
0x180013e5e  lea     rdx, [rbx+30h]; struct _UNICODE_STRING *
0x180013e62  lea     rcx, [rsi+30h]; struct _UNICODE_STRING *
0x180013e66  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013e6b  mov     edi, eax
0x180013e6d  test    eax, eax
0x180013e6f  js      loc_180013F0C
0x180013e75  lea     rdx, [rbx+58h]; struct _UNICODE_STRING *
0x180013e79  lea     rcx, [rsi+58h]; struct _UNICODE_STRING *
0x180013e7d  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013e82  mov     edi, eax
0x180013e84  test    eax, eax
0x180013e86  js      loc_180013F0C
0x180013e8c  lea     rdx, [rbx+68h]; struct _UNICODE_STRING *
0x180013e90  lea     rcx, [rsi+68h]; struct _UNICODE_STRING *
0x180013e94  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013e99  mov     edi, eax
0x180013e9b  test    eax, eax
0x180013e9d  js      short loc_180013F0C
0x180013e9f  lea     rdx, [rbx+78h]; struct _UNICODE_STRING *
0x180013ea3  lea     rcx, [rsi+78h]; struct _UNICODE_STRING *
0x180013ea7  call    ?_CopyUnicodeString@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; _CopyUnicodeString(_UNICODE_STRING const *,_UNICODE_STRING *)
0x180013eac  mov     edi, eax
0x180013eae  test    eax, eax
0x180013eb0  js      short loc_180013F0C
0x180013eb2  mov     rcx, [rsi+48h]; pSid
0x180013eb6  mov     rax, [rbx+4]
0x180013eba  mov     [rsi+4], rax
0x180013ebe  test    rcx, rcx
0x180013ec1  jz      short loc_180013F2C
0x180013ec3  mov     edi, ebp
0x180013ec5  call    cs:__imp_GetLengthSid
0x180013ecb  mov     ecx, eax; cb
0x180013ecd  mov     r14d, eax
0x180013ed0  call    cs:__imp_CoTaskMemAlloc
0x180013ed6  mov     rbp, rax
0x180013ed9  test    rax, rax
0x180013edc  jz      short loc_180013F0C
0x180013ede  mov     r8, [rsi+48h]; pSourceSid
0x180013ee2  mov     rdx, rax; pDestinationSid
0x180013ee5  mov     ecx, r14d; nDestinationSidLength
0x180013ee8  mov     edi, 80004005h
0x180013eed  call    cs:__imp_CopySid
0x180013ef3  test    eax, eax
0x180013ef5  jz      short loc_180013EFF
0x180013ef7  mov     [rbx+48h], rbp
0x180013efb  xor     ebp, ebp
0x180013efd  xor     edi, edi
0x180013eff  mov     rcx, rbp; pv
0x180013f02  call    cs:__imp_CoTaskMemFree
0x180013f08  test    edi, edi
0x180013f0a  jns     short loc_180013F34
0x180013f0c  mov     rdx, rbx; struct _SECURITY_LOGON_SESSION_DATA *
0x180013f0f  call    ?_ClearLogonSessionData@CLoggedOnPropStore@@AEAAXPEAU_SECURITY_LOGON_SESSION_DATA@@@Z; CLoggedOnPropStore::_ClearLogonSessionData(_SECURITY_LOGON_SESSION_DATA *)
0x180013f14  mov     rcx, rbx; pv
0x180013f17  call    cs:__imp_CoTaskMemFree
0x180013f1d  mov     eax, edi
0x180013f1f  add     rsp, 28h
0x180013f23  pop     r15
0x180013f25  pop     r14
0x180013f27  pop     rdi
0x180013f28  pop     rsi
0x180013f29  pop     rbp
0x180013f2a  pop     rbx
0x180013f2b  retn
0x180013f2c  mov     qword ptr [rbx+48h], 0
0x180013f34  mov     [r15], rbx
0x180013f37  xor     ebx, ebx
0x180013f39  jmp     short loc_180013F14
```
