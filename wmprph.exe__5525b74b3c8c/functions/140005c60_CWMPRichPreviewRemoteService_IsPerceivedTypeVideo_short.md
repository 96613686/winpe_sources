# CWMPRichPreviewRemoteService::IsPerceivedTypeVideo(short *)

- ea: `0x140005c60`
- end: `0x140005dd6`
- name: `?IsPerceivedTypeVideo@CWMPRichPreviewRemoteService@@UEAAJPEAF@Z`
- size: `374`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140005c60`
- `0x14000d978`
- `0x14000dcf8`
- `0x14000dee0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140005d4c`
- `ADVAPI32!RegOpenKeyExW` at `0x140005d4c`
- `ADVAPI32!RegCloseKey` at `0x140005d67`
- `ADVAPI32!RegCloseKey` at `0x140005d67`
- `KERNEL32!CompareStringW` at `0x140005d9a`
- `KERNEL32!CompareStringW` at `0x140005d9a`
- `KERNEL32!lstrlenW` at `0x140005ced`
- `KERNEL32!lstrlenW` at `0x140005ced`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140005cbb`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140005cbb`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::IsPerceivedTypeVideo(CWMPRichPreviewRemoteService *this, __int16 *a2)
{
  __int64 v2; // rdi
  const wchar_t *v5; // rcx
  wchar_t *v6; // rax
  __int64 v7; // rbx
  const WCHAR *v8; // rcx
  int v9; // r8d
  const WCHAR *v10; // rbx
  const unsigned __int16 *v11; // r8
  __int16 v12; // cx
  PCNZWCH lpString1; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+38h] [rbp-20h]
  __int16 v16; // [rsp+3Ch] [rbp-1Ch]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-18h] BYREF
  int v18; // [rsp+48h] [rbp-10h]
  __int16 v19; // [rsp+4Ch] [rbp-Ch]
  HKEY hKey; // [rsp+90h] [rbp+38h] BYREF

  v2 = *((_QWORD *)this + 4);
  lpSubKey = 0;
  v18 = 0;
  v19 = 0;
  lpString1 = 0;
  v15 = 0;
  v16 = 0;
  if ( v2 )
  {
    v5 = *(const wchar_t **)(v2 + 56);
    if ( v5 )
    {
      if ( *v5 )
      {
        v6 = wcsrchr(v5, 0x2Eu);
        if ( v6 )
        {
          v7 = ((__int64)v6 - *(_QWORD *)(v2 + 56)) >> 1;
          if ( (int)v7 >= 0 )
          {
            v8 = *(const WCHAR **)(*((_QWORD *)this + 4) + 56LL);
            if ( v8 )
            {
              if ( (int)v7 < lstrlenW(v8) )
              {
                WString::Init(
                  (WString *)&lpSubKey,
                  (const unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)this + 4) + 56LL) + 2LL * (int)v7),
                  v9);
                v10 = lpSubKey;
                if ( lpSubKey )
                {
                  if ( *lpSubKey )
                  {
                    WString::DeleteString((unsigned __int16 **)&lpString1);
                    if ( v10 )
                    {
                      hKey = 0;
                      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, v10, 0, 0x20019u, &hKey) )
                      {
                        WString::LoadStringFromRegistry((WString *)&lpString1, hKey, v11);
                        RegCloseKey(hKey);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( a2 )
  {
    if ( lpString1 )
      v12 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"video", -1) != 2;
    else
      v12 = 1;
    *a2 = v12 - 1;
  }
  WString::DeleteString((unsigned __int16 **)&lpString1);
  WString::DeleteString((unsigned __int16 **)&lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x140005c60  push    rbp
0x140005c62  push    rbx
0x140005c63  push    rsi
0x140005c64  push    rdi
0x140005c65  push    r14
0x140005c67  push    r15
0x140005c69  mov     rbp, rsp
0x140005c6c  sub     rsp, 58h
0x140005c70  mov     rdi, [rcx+20h]
0x140005c74  xor     r15d, r15d
0x140005c77  mov     [rbp+lpSubKey], r15
0x140005c7b  mov     r14, rdx
0x140005c7e  mov     [rbp+var_10], r15d
0x140005c82  mov     rsi, rcx
0x140005c85  mov     [rbp+var_C], r15w
0x140005c8a  mov     [rbp+lpString1], r15
0x140005c8e  mov     [rbp+var_20], r15d
0x140005c92  mov     [rbp+var_1C], r15w
0x140005c97  test    rdi, rdi
0x140005c9a  jz      loc_140005D6D
0x140005ca0  mov     rcx, [rdi+38h]; Str
0x140005ca4  test    rcx, rcx
0x140005ca7  jz      loc_140005D6D
0x140005cad  cmp     [rcx], r15w
0x140005cb1  jz      loc_140005D6D
0x140005cb7  lea     edx, [r15+2Eh]; Ch
0x140005cbb  call    cs:__imp_wcsrchr
0x140005cc1  mov     rbx, rax
0x140005cc4  test    rax, rax
0x140005cc7  jz      loc_140005D6D
0x140005ccd  sub     rbx, [rdi+38h]
0x140005cd1  sar     rbx, 1
0x140005cd4  test    ebx, ebx
0x140005cd6  js      loc_140005D6D
0x140005cdc  mov     rcx, [rsi+20h]
0x140005ce0  mov     rcx, [rcx+38h]; lpString
0x140005ce4  test    rcx, rcx
0x140005ce7  jz      loc_140005D6D
0x140005ced  call    cs:__imp_lstrlenW
0x140005cf3  cmp     ebx, eax
0x140005cf5  jge     short loc_140005D6D
0x140005cf7  mov     rax, [rsi+20h]
0x140005cfb  movsxd  rdx, ebx
0x140005cfe  mov     rcx, [rax+38h]
0x140005d02  lea     rdx, [rcx+rdx*2]; unsigned __int16 *
0x140005d06  lea     rcx, [rbp+lpSubKey]; this
0x140005d0a  call    ?Init@WString@@QEAAJPEBGH@Z; WString::Init(ushort const *,int)
0x140005d0f  mov     rbx, [rbp+lpSubKey]
0x140005d13  test    rbx, rbx
0x140005d16  jz      short loc_140005D6D
0x140005d18  cmp     [rbx], r15w
0x140005d1c  jz      short loc_140005D6D
0x140005d1e  lea     rcx, [rbp+lpString1]; this
0x140005d22  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140005d27  test    rbx, rbx
0x140005d2a  jz      short loc_140005D6D
0x140005d2c  lea     rax, [rbp+hKey]
0x140005d30  mov     [rbp+hKey], r15
0x140005d34  mov     r9d, 20019h; samDesired
0x140005d3a  mov     [rsp+58h+phkResult], rax; phkResult
0x140005d3f  xor     r8d, r8d; ulOptions
0x140005d42  mov     rdx, rbx; lpSubKey
0x140005d45  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140005d4c  call    cs:__imp_RegOpenKeyExW
0x140005d52  test    eax, eax
0x140005d54  jnz     short loc_140005D6D
0x140005d56  mov     rdx, [rbp+hKey]; hKey
0x140005d5a  lea     rcx, [rbp+lpString1]; this
0x140005d5e  call    ?LoadStringFromRegistry@WString@@QEAAJQEAUHKEY__@@QEBG@Z; WString::LoadStringFromRegistry(HKEY__ * const,ushort const * const)
0x140005d63  mov     rcx, [rbp+hKey]; hKey
0x140005d67  call    cs:__imp_RegCloseKey
0x140005d6d  test    r14, r14
0x140005d70  jz      short loc_140005DB5
0x140005d72  mov     r8, [rbp+lpString1]; lpString1
0x140005d76  mov     ebx, 1
0x140005d7b  test    r8, r8
0x140005d7e  jz      short loc_140005DAB
0x140005d80  or      r9d, 0FFFFFFFFh; cchCount1
0x140005d84  lea     rax, aVideo; "video"
0x140005d8b  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x140005d90  lea     ecx, [rbx+7Eh]; Locale
0x140005d93  mov     edx, ebx; dwCmpFlags
0x140005d95  mov     [rsp+58h+phkResult], rax; lpString2
0x140005d9a  call    cs:__imp_CompareStringW
0x140005da0  cmp     eax, 2
0x140005da3  mov     ecx, r15d
0x140005da6  setnz   cl
0x140005da9  jmp     short loc_140005DAE
0x140005dab  movzx   ecx, bx
0x140005dae  sub     cx, bx
0x140005db1  mov     [r14], cx
0x140005db5  lea     rcx, [rbp+lpString1]; this
0x140005db9  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140005dbe  lea     rcx, [rbp+lpSubKey]; this
0x140005dc2  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140005dc7  xor     eax, eax
0x140005dc9  add     rsp, 58h
0x140005dcd  pop     r15
0x140005dcf  pop     r14
0x140005dd1  pop     rdi
0x140005dd2  pop     rsi
0x140005dd3  pop     rbx
0x140005dd4  pop     rbp
0x140005dd5  retn
```
