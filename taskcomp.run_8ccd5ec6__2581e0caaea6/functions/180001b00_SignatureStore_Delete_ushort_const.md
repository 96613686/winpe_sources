# SignatureStore::Delete(ushort const *)

- ea: `0x180001b00`
- end: `0x180001ed8`
- name: `?Delete@SignatureStore@@SAJPEBG@Z`
- size: `984`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001760`
- `0x180011600`

## callees

- `0x180001b00`
- `0x1800050d0`
- `0x180005150`
- `0x180007948`
- `0x180007988`
- `0x180008c66`
- `0x180017ef8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001bc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001eba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001bc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001eba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001b9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001e23`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001b9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001e23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001b44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001b44`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c72`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c0a`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180001da3`
- `OLEAUT32!__imp_SysFreeString` at `0x180001de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e86`
- `OLEAUT32!__imp_SysFreeString` at `0x180001da3`
- `OLEAUT32!__imp_SysFreeString` at `0x180001de8`
- `OLEAUT32!__imp_SysFreeString` at `0x180001e86`
- `OLEAUT32!__imp_SysStringLen` at `0x180001cda`
- `OLEAUT32!__imp_SysStringLen` at `0x180001cf5`
- `OLEAUT32!__imp_SysStringLen` at `0x180001cda`
- `OLEAUT32!__imp_SysStringLen` at `0x180001cf5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180001d22`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180001d22`

## string_xrefs

- `0x180001b36`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SignatureStore::Delete(OLECHAR *psz)
{
  const WCHAR *v1; // rdi
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  volatile signed __int32 *v7; // rax
  struct IErrorInfo *v8; // rdx
  volatile signed __int32 *v9; // r14
  BSTR v10; // rax
  _QWORD *v11; // rax
  struct IErrorInfo *v12; // rdx
  void *v13; // rsi
  BSTR v14; // rax
  volatile signed __int32 *v15; // rax
  struct IErrorInfo *v16; // rdx
  volatile signed __int32 *v17; // rbx
  UINT v18; // ebp
  UINT v19; // r15d
  UINT v20; // edi
  struct IErrorInfo *v21; // rdx
  BSTR v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  const WCHAR *v25; // rdx
  LSTATUS v26; // eax
  unsigned int v27; // esi
  void *v28; // rcx
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF
  volatile signed __int32 *v30; // [rsp+80h] [rbp+18h] BYREF
  volatile signed __int32 *v31; // [rsp+88h] [rbp+20h]

  v1 = psz + 1;
  if ( *psz != 92 )
    v1 = psz;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\CompatibilityAdapter\\Signatures",
         0,
         0x2001Fu,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
      return 0;
    }
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    return v3;
  }
  else
  {
    v5 = RegDeleteValueW(hKey, v1);
    v6 = v5;
    if ( (v5 & 0xFFFFFFFD) != 0 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( hKey )
        RegCloseKey(hKey);
      return v6;
    }
    else
    {
      v7 = (volatile signed __int32 *)operator new(0x18u);
      v9 = v7;
      if ( v7 )
      {
        *((_QWORD *)v7 + 1) = 0;
        *((_DWORD *)v7 + 4) = 1;
        v10 = SysAllocString(v1);
        *(_QWORD *)v9 = v10;
        if ( !v10 && v1 )
          _com_raise_error(-2147024882, v8);
      }
      else
      {
        v9 = 0;
      }
      v30 = v9;
      if ( !v9 )
        _com_raise_error(-2147024882, v8);
      v11 = operator new(0x18u);
      v13 = v11;
      if ( v11 )
      {
        v11[1] = 0;
        *((_DWORD *)v11 + 4) = 1;
        v14 = SysAllocString(L".fp");
        *(_QWORD *)v13 = v14;
        if ( !v14 )
          _com_raise_error(-2147024882, v12);
      }
      else
      {
        v13 = 0;
      }
      if ( !v13 )
        _com_raise_error(-2147024882, v12);
      v15 = (volatile signed __int32 *)operator new(0x18u);
      v17 = v15;
      v31 = v15;
      if ( v15 )
      {
        *((_QWORD *)v15 + 1) = 0;
        *((_DWORD *)v15 + 4) = 1;
        if ( *(_QWORD *)v9 )
          v18 = SysStringLen(*(BSTR *)v9);
        else
          v18 = 0;
        if ( *(_QWORD *)v13 )
          v19 = SysStringLen(*(BSTR *)v13);
        else
          v19 = 0;
        v20 = v19 + v18;
        if ( v19 + v18 < v18 || (v16 = (struct IErrorInfo *)(2LL * v20), (unsigned __int64)v16 > 0xFFFFFFFF) )
          _com_raise_error(-2147024882, v16);
        v22 = SysAllocStringByteLen(0, (UINT)v16);
        *(_QWORD *)v17 = v22;
        if ( v22 )
        {
          if ( *(_QWORD *)v9 )
            memcpy_0(v22, *(const void **)v9, 2LL * (v18 + 1));
          if ( *(_QWORD *)v13 )
            memcpy_0((void *)(*(_QWORD *)v17 + 2LL * v18), *(const void **)v13, 2LL * (v19 + 1));
        }
        else if ( v20 )
        {
          _com_raise_error(-2147024882, v21);
        }
      }
      else
      {
        v17 = 0;
      }
      if ( _InterlockedExchangeAdd(v9 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v9 )
        {
          SysFreeString(*(BSTR *)v9);
          *(_QWORD *)v9 = 0;
        }
        v23 = (void *)*((_QWORD *)v9 + 1);
        if ( v23 )
        {
          operator delete(v23);
          *((_QWORD *)v9 + 1) = 0;
        }
        operator delete((void *)v9);
      }
      v30 = v17;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 4, 0xFFFFFFFF) == 1 )
      {
        if ( *(_QWORD *)v13 )
        {
          SysFreeString(*(BSTR *)v13);
          *(_QWORD *)v13 = 0;
        }
        v24 = (void *)*((_QWORD *)v13 + 1);
        if ( v24 )
        {
          operator delete(v24);
          *((_QWORD *)v13 + 1) = 0;
        }
        operator delete(v13);
      }
      if ( v17 )
        v25 = *(const WCHAR **)v17;
      else
        v25 = 0;
      v26 = RegDeleteValueW(hKey, v25);
      v27 = v26;
      if ( (v26 & 0xFFFFFFFD) == 0 )
      {
        if ( v17 && _InterlockedExchangeAdd(v17 + 4, 0xFFFFFFFF) == 1 )
        {
          if ( *(_QWORD *)v17 )
          {
            SysFreeString(*(BSTR *)v17);
            *(_QWORD *)v17 = 0;
          }
          v28 = (void *)*((_QWORD *)v17 + 1);
          if ( v28 )
          {
            operator delete(v28);
            *((_QWORD *)v17 + 1) = 0;
          }
          operator delete((void *)v17);
        }
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
      if ( v26 > 0 )
        v27 = (unsigned __int16)v26 | 0x80070000;
      _bstr_t::~_bstr_t((_bstr_t *)&v30);
      wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
      return v27;
    }
  }
}

```

## disassembly

```asm
0x180001b00  push    rbx
0x180001b02  push    rbp
0x180001b03  push    rsi
0x180001b04  push    rdi
0x180001b05  push    r12
0x180001b07  push    r14
0x180001b09  push    r15
0x180001b0b  sub     rsp, 30h
0x180001b0f  lea     rdi, [rcx+2]
0x180001b13  cmp     word ptr [rcx], 5Ch ; '\'
0x180001b17  cmovnz  rdi, rcx
0x180001b1b  xor     r12d, r12d
0x180001b1e  mov     [rsp+68h+hKey], r12
0x180001b23  lea     rax, [rsp+68h+hKey]
0x180001b28  mov     [rsp+68h+phkResult], rax; phkResult
0x180001b2d  mov     r9d, 2001Fh; samDesired
0x180001b33  xor     r8d, r8d; ulOptions
0x180001b36  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180001b3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001b44  call    cs:__imp_RegOpenKeyExW
0x180001b4b  nop     dword ptr [rax+rax+00h]
0x180001b50  mov     ebx, eax
0x180001b52  test    eax, eax
0x180001b54  jz      short loc_180001B93
0x180001b56  cmp     eax, 2
0x180001b59  jnz     short loc_180001B6A
0x180001b5b  lea     rcx, [rsp+68h+hKey]; this
0x180001b60  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001b65  jmp     loc_180001EC6
0x180001b6a  test    eax, eax
0x180001b6c  jle     short loc_180001B77
0x180001b6e  movzx   ebx, ax
0x180001b71  or      ebx, 80070000h
0x180001b77  lea     rcx, [rsp+68h+hKey]; this
0x180001b7c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001b81  mov     eax, ebx
0x180001b83  add     rsp, 30h
0x180001b87  pop     r15
0x180001b89  pop     r14
0x180001b8b  pop     r12
0x180001b8d  pop     rdi
0x180001b8e  pop     rsi
0x180001b8f  pop     rbp
0x180001b90  pop     rbx
0x180001b91  retn
0x180001b93  mov     rdx, rdi; lpValueName
0x180001b96  mov     rcx, [rsp+68h+hKey]; hKey
0x180001b9b  call    cs:__imp_RegDeleteValueW
0x180001ba2  nop     dword ptr [rax+rax+00h]
0x180001ba7  mov     ebx, eax
0x180001ba9  test    eax, 0FFFFFFFDh
0x180001bae  jz      short loc_180001BE5
0x180001bb0  test    eax, eax
0x180001bb2  jle     short loc_180001BBD
0x180001bb4  movzx   ebx, ax
0x180001bb7  or      ebx, 80070000h
0x180001bbd  mov     rcx, [rsp+68h+hKey]; hKey
0x180001bc2  test    rcx, rcx
0x180001bc5  jz      short loc_180001BD3
0x180001bc7  call    cs:__imp_RegCloseKey
0x180001bce  nop     dword ptr [rax+rax+00h]
0x180001bd3  mov     eax, ebx
0x180001bd5  add     rsp, 30h
0x180001bd9  pop     r15
0x180001bdb  pop     r14
0x180001bdd  pop     r12
0x180001bdf  pop     rdi
0x180001be0  pop     rsi
0x180001be1  pop     rbp
0x180001be2  pop     rbx
0x180001be3  retn
0x180001be5  mov     ecx, 18h; Size
0x180001bea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001bef  mov     r14, rax
0x180001bf2  mov     [rsp+68h+arg_0], rax
0x180001bf7  test    rax, rax
0x180001bfa  jz      short loc_180001C2E
0x180001bfc  mov     [rax+8], r12
0x180001c00  mov     dword ptr [rax+10h], 1
0x180001c07  mov     rcx, rdi; psz
0x180001c0a  call    cs:__imp_SysAllocString
0x180001c11  nop     dword ptr [rax+rax+00h]
0x180001c16  mov     [r14], rax
0x180001c19  test    rax, rax
0x180001c1c  jnz     short loc_180001C31
0x180001c1e  test    rdi, rdi
0x180001c21  jz      short loc_180001C31
0x180001c23  mov     ecx, 8007000Eh; int
0x180001c28  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001c2e  mov     r14, r12
0x180001c31  mov     [rsp+68h+arg_10], r14
0x180001c39  test    r14, r14
0x180001c3c  jnz     short loc_180001C49
0x180001c3e  mov     ecx, 8007000Eh; int
0x180001c43  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001c49  mov     ecx, 18h; Size
0x180001c4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c53  mov     rsi, rax
0x180001c56  mov     [rsp+68h+arg_0], rax
0x180001c5b  test    rax, rax
0x180001c5e  jz      short loc_180001C91
0x180001c60  mov     [rax+8], r12
0x180001c64  mov     dword ptr [rax+10h], 1
0x180001c6b  lea     rcx, psz; ".fp"
0x180001c72  call    cs:__imp_SysAllocString
0x180001c79  nop     dword ptr [rax+rax+00h]
0x180001c7e  mov     [rsi], rax
0x180001c81  test    rax, rax
0x180001c84  jnz     short loc_180001C94
0x180001c86  mov     ecx, 8007000Eh; int
0x180001c8b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001c91  mov     rsi, r12
0x180001c94  mov     [rsp+68h+arg_0], rsi
0x180001c99  test    rsi, rsi
0x180001c9c  jnz     short loc_180001CA9
0x180001c9e  mov     ecx, 8007000Eh; int
0x180001ca3  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001ca9  mov     ecx, 18h; Size
0x180001cae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001cb3  mov     rbx, rax
0x180001cb6  mov     [rsp+68h+arg_18], rax
0x180001cbe  test    rax, rax
0x180001cc1  jz      loc_180001D86
0x180001cc7  mov     [rax+8], r12
0x180001ccb  mov     dword ptr [rax+10h], 1
0x180001cd2  mov     rcx, [r14]; pbstr
0x180001cd5  test    rcx, rcx
0x180001cd8  jz      short loc_180001CEA
0x180001cda  call    cs:__imp_SysStringLen
0x180001ce1  nop     dword ptr [rax+rax+00h]
0x180001ce6  mov     ebp, eax
0x180001ce8  jmp     short loc_180001CED
0x180001cea  mov     ebp, r12d
0x180001ced  mov     rcx, [rsi]; pbstr
0x180001cf0  test    rcx, rcx
0x180001cf3  jz      short loc_180001D06
0x180001cf5  call    cs:__imp_SysStringLen
0x180001cfc  nop     dword ptr [rax+rax+00h]
0x180001d01  mov     r15d, eax
0x180001d04  jmp     short loc_180001D09
0x180001d06  mov     r15d, r12d
0x180001d09  lea     edi, [r15+rbp]
0x180001d0d  cmp     edi, ebp
0x180001d0f  jb      short loc_180001D7B
0x180001d11  mov     edx, edi
0x180001d13  add     rdx, rdx; len
0x180001d16  mov     eax, 0FFFFFFFFh
0x180001d1b  cmp     rdx, rax
0x180001d1e  ja      short loc_180001D7B
0x180001d20  xor     ecx, ecx; psz
0x180001d22  call    cs:__imp_SysAllocStringByteLen
0x180001d29  nop     dword ptr [rax+rax+00h]
0x180001d2e  mov     rcx, rax; void *
0x180001d31  mov     [rbx], rax
0x180001d34  test    rax, rax
0x180001d37  jnz     short loc_180001D48
0x180001d39  test    edi, edi
0x180001d3b  jz      short loc_180001D89
0x180001d3d  mov     ecx, 8007000Eh; int
0x180001d42  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001d48  mov     rdx, [r14]; Src
0x180001d4b  test    rdx, rdx
0x180001d4e  jz      short loc_180001D5C
0x180001d50  lea     r8d, [rbp+1]
0x180001d54  add     r8, r8; Size
0x180001d57  call    memcpy_0
0x180001d5c  mov     rdx, [rsi]; Src
0x180001d5f  test    rdx, rdx
0x180001d62  jz      short loc_180001D89
0x180001d64  lea     r8d, [r15+1]
0x180001d68  add     r8, r8; Size
0x180001d6b  mov     ecx, ebp
0x180001d6d  mov     rax, [rbx]
0x180001d70  lea     rcx, [rax+rcx*2]; void *
0x180001d74  call    memcpy_0
0x180001d79  jmp     short loc_180001D89
0x180001d7b  mov     ecx, 8007000Eh; int
0x180001d80  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001d86  mov     rbx, r12
0x180001d89  mov     edi, 0FFFFFFFFh
0x180001d8e  mov     eax, edi
0x180001d90  lock xadd [r14+10h], eax
0x180001d96  cmp     eax, 1
0x180001d99  jnz     short loc_180001DCC
0x180001d9b  mov     rcx, [r14]; bstrString
0x180001d9e  test    rcx, rcx
0x180001da1  jz      short loc_180001DB2
0x180001da3  call    cs:__imp_SysFreeString
0x180001daa  nop     dword ptr [rax+rax+00h]
0x180001daf  mov     [r14], r12
0x180001db2  mov     rcx, [r14+8]; Block
0x180001db6  test    rcx, rcx
0x180001db9  jz      short loc_180001DC4
0x180001dbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001dc0  mov     [r14+8], r12
0x180001dc4  mov     rcx, r14; Block
0x180001dc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001dcc  mov     [rsp+68h+arg_10], rbx
0x180001dd4  mov     eax, edi
0x180001dd6  lock xadd [rsi+10h], eax
0x180001ddb  cmp     eax, 1
0x180001dde  jnz     short loc_180001E11
0x180001de0  mov     rcx, [rsi]; bstrString
0x180001de3  test    rcx, rcx
0x180001de6  jz      short loc_180001DF7
0x180001de8  call    cs:__imp_SysFreeString
0x180001def  nop     dword ptr [rax+rax+00h]
0x180001df4  mov     [rsi], r12
0x180001df7  mov     rcx, [rsi+8]; Block
0x180001dfb  test    rcx, rcx
0x180001dfe  jz      short loc_180001E09
0x180001e00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e05  mov     [rsi+8], r12
0x180001e09  mov     rcx, rsi; Block
0x180001e0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e11  test    rbx, rbx
0x180001e14  jz      short loc_180001E1B
0x180001e16  mov     rdx, [rbx]
0x180001e19  jmp     short loc_180001E1E
0x180001e1b  mov     rdx, r12; lpValueName
0x180001e1e  mov     rcx, [rsp+68h+hKey]; hKey
0x180001e23  call    cs:__imp_RegDeleteValueW
0x180001e2a  nop     dword ptr [rax+rax+00h]
0x180001e2f  mov     esi, eax
0x180001e31  test    eax, 0FFFFFFFDh
0x180001e36  jz      short loc_180001E6F
0x180001e38  test    eax, eax
0x180001e3a  jle     short loc_180001E45
0x180001e3c  movzx   esi, ax
0x180001e3f  or      esi, 80070000h
0x180001e45  lea     rcx, [rsp+68h+arg_10]; this
0x180001e4d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180001e52  nop
0x180001e53  lea     rcx, [rsp+68h+hKey]; this
0x180001e58  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001e5d  mov     eax, esi
0x180001e5f  add     rsp, 30h
0x180001e63  pop     r15
0x180001e65  pop     r14
0x180001e67  pop     r12
0x180001e69  pop     rdi
0x180001e6a  pop     rsi
0x180001e6b  pop     rbp
0x180001e6c  pop     rbx
0x180001e6d  retn
0x180001e6f  test    rbx, rbx
0x180001e72  jz      short loc_180001EB0
0x180001e74  lock xadd [rbx+10h], edi
0x180001e79  cmp     edi, 1
0x180001e7c  jnz     short loc_180001EB0
0x180001e7e  mov     rcx, [rbx]; bstrString
0x180001e81  test    rcx, rcx
0x180001e84  jz      short loc_180001E95
0x180001e86  call    cs:__imp_SysFreeString
0x180001e8d  nop     dword ptr [rax+rax+00h]
0x180001e92  mov     [rbx], r12
0x180001e95  mov     rcx, [rbx+8]; Block
0x180001e99  test    rcx, rcx
0x180001e9c  jz      short loc_180001EA7
0x180001e9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001ea3  mov     [rbx+8], r12
0x180001ea7  mov     rcx, rbx; Block
0x180001eaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001eaf  nop
0x180001eb0  mov     rcx, [rsp+68h+hKey]; hKey
0x180001eb5  test    rcx, rcx
0x180001eb8  jz      short loc_180001EC6
0x180001eba  call    cs:__imp_RegCloseKey
0x180001ec1  nop     dword ptr [rax+rax+00h]
0x180001ec6  xor     eax, eax
0x180001ec8  add     rsp, 30h
0x180001ecc  pop     r15
0x180001ece  pop     r14
0x180001ed0  pop     r12
0x180001ed2  pop     rdi
0x180001ed3  pop     rsi
0x180001ed4  pop     rbp
0x180001ed5  pop     rbx
0x180001ed6  retn
```
