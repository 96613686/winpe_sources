# SignatureStore::Delete(ushort const *)

- ea: `0x180001ab0`
- end: `0x180001e36`
- name: `?Delete@SignatureStore@@SAJPEBG@Z`
- size: `902`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001730`
- `0x180010bd0`

## callees

- `0x180001ab0`
- `0x180004e50`
- `0x180004ec0`
- `0x180007488`
- `0x1800074c8`
- `0x1800087a6`
- `0x180016f38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001b6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001b44`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001d95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001b44`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180001d95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001af4`
- `OLEAUT32!__imp_SysAllocString` at `0x180001ba6`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c08`
- `OLEAUT32!__imp_SysAllocString` at `0x180001ba6`
- `OLEAUT32!__imp_SysAllocString` at `0x180001c08`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d21`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180001df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d21`
- `OLEAUT32!__imp_SysFreeString` at `0x180001d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180001df1`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c7f`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180001c7f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180001ca6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180001ca6`

## string_xrefs

- `0x180001ae6`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\CompatibilityAdapter\Signatures`

## pseudocode

```c
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
0x180001ab0  push    rbx
0x180001ab2  push    rbp
0x180001ab3  push    rsi
0x180001ab4  push    rdi
0x180001ab5  push    r12
0x180001ab7  push    r14
0x180001ab9  push    r15
0x180001abb  sub     rsp, 30h
0x180001abf  lea     rdi, [rcx+2]
0x180001ac3  cmp     word ptr [rcx], 5Ch ; '\'
0x180001ac7  cmovnz  rdi, rcx
0x180001acb  xor     r12d, r12d
0x180001ace  mov     [rsp+68h+hKey], r12
0x180001ad3  lea     rax, [rsp+68h+hKey]
0x180001ad8  mov     [rsp+68h+phkResult], rax; phkResult
0x180001add  mov     r9d, 2001Fh; samDesired
0x180001ae3  xor     r8d, r8d; ulOptions
0x180001ae6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180001aed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001af4  call    cs:__imp_RegOpenKeyExW
0x180001afa  mov     ebx, eax
0x180001afc  test    eax, eax
0x180001afe  jz      short loc_180001B3C
0x180001b00  cmp     eax, 2
0x180001b03  jnz     short loc_180001B14
0x180001b05  lea     rcx, [rsp+68h+hKey]; this
0x180001b0a  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001b0f  jmp     loc_180001E25
0x180001b14  test    eax, eax
0x180001b16  jle     short loc_180001B21
0x180001b18  movzx   ebx, ax
0x180001b1b  or      ebx, 80070000h
0x180001b21  lea     rcx, [rsp+68h+hKey]; this
0x180001b26  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001b2b  mov     eax, ebx
0x180001b2d  add     rsp, 30h
0x180001b31  pop     r15
0x180001b33  pop     r14
0x180001b35  pop     r12
0x180001b37  pop     rdi
0x180001b38  pop     rsi
0x180001b39  pop     rbp
0x180001b3a  pop     rbx
0x180001b3b  retn
0x180001b3c  mov     rdx, rdi; lpValueName
0x180001b3f  mov     rcx, [rsp+68h+hKey]; hKey
0x180001b44  call    cs:__imp_RegDeleteValueW
0x180001b4a  mov     ebx, eax
0x180001b4c  test    eax, 0FFFFFFFDh
0x180001b51  jz      short loc_180001B81
0x180001b53  test    eax, eax
0x180001b55  jle     short loc_180001B60
0x180001b57  movzx   ebx, ax
0x180001b5a  or      ebx, 80070000h
0x180001b60  mov     rcx, [rsp+68h+hKey]; hKey
0x180001b65  test    rcx, rcx
0x180001b68  jz      short loc_180001B70
0x180001b6a  call    cs:__imp_RegCloseKey
0x180001b70  mov     eax, ebx
0x180001b72  add     rsp, 30h
0x180001b76  pop     r15
0x180001b78  pop     r14
0x180001b7a  pop     r12
0x180001b7c  pop     rdi
0x180001b7d  pop     rsi
0x180001b7e  pop     rbp
0x180001b7f  pop     rbx
0x180001b80  retn
0x180001b81  mov     ecx, 18h; Size
0x180001b86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b8b  mov     r14, rax
0x180001b8e  mov     [rsp+68h+arg_0], rax
0x180001b93  test    rax, rax
0x180001b96  jz      short loc_180001BC4
0x180001b98  mov     [rax+8], r12
0x180001b9c  mov     dword ptr [rax+10h], 1
0x180001ba3  mov     rcx, rdi; psz
0x180001ba6  call    cs:__imp_SysAllocString
0x180001bac  mov     [r14], rax
0x180001baf  test    rax, rax
0x180001bb2  jnz     short loc_180001BC7
0x180001bb4  test    rdi, rdi
0x180001bb7  jz      short loc_180001BC7
0x180001bb9  mov     ecx, 8007000Eh; int
0x180001bbe  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001bc4  mov     r14, r12
0x180001bc7  mov     [rsp+68h+arg_10], r14
0x180001bcf  test    r14, r14
0x180001bd2  jnz     short loc_180001BDF
0x180001bd4  mov     ecx, 8007000Eh; int
0x180001bd9  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001bdf  mov     ecx, 18h; Size
0x180001be4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001be9  mov     rsi, rax
0x180001bec  mov     [rsp+68h+arg_0], rax
0x180001bf1  test    rax, rax
0x180001bf4  jz      short loc_180001C21
0x180001bf6  mov     [rax+8], r12
0x180001bfa  mov     dword ptr [rax+10h], 1
0x180001c01  lea     rcx, psz; ".fp"
0x180001c08  call    cs:__imp_SysAllocString
0x180001c0e  mov     [rsi], rax
0x180001c11  test    rax, rax
0x180001c14  jnz     short loc_180001C24
0x180001c16  mov     ecx, 8007000Eh; int
0x180001c1b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001c21  mov     rsi, r12
0x180001c24  mov     [rsp+68h+arg_0], rsi
0x180001c29  test    rsi, rsi
0x180001c2c  jnz     short loc_180001C39
0x180001c2e  mov     ecx, 8007000Eh; int
0x180001c33  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001c39  mov     ecx, 18h; Size
0x180001c3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c43  mov     rbx, rax
0x180001c46  mov     [rsp+68h+arg_18], rax
0x180001c4e  test    rax, rax
0x180001c51  jz      loc_180001D04
0x180001c57  mov     [rax+8], r12
0x180001c5b  mov     dword ptr [rax+10h], 1
0x180001c62  mov     rcx, [r14]; pbstr
0x180001c65  test    rcx, rcx
0x180001c68  jz      short loc_180001C74
0x180001c6a  call    cs:__imp_SysStringLen
0x180001c70  mov     ebp, eax
0x180001c72  jmp     short loc_180001C77
0x180001c74  mov     ebp, r12d
0x180001c77  mov     rcx, [rsi]; pbstr
0x180001c7a  test    rcx, rcx
0x180001c7d  jz      short loc_180001C8A
0x180001c7f  call    cs:__imp_SysStringLen
0x180001c85  mov     r15d, eax
0x180001c88  jmp     short loc_180001C8D
0x180001c8a  mov     r15d, r12d
0x180001c8d  lea     edi, [r15+rbp]
0x180001c91  cmp     edi, ebp
0x180001c93  jb      short loc_180001CF9
0x180001c95  mov     edx, edi
0x180001c97  add     rdx, rdx; len
0x180001c9a  mov     eax, 0FFFFFFFFh
0x180001c9f  cmp     rdx, rax
0x180001ca2  ja      short loc_180001CF9
0x180001ca4  xor     ecx, ecx; psz
0x180001ca6  call    cs:__imp_SysAllocStringByteLen
0x180001cac  mov     rcx, rax; void *
0x180001caf  mov     [rbx], rax
0x180001cb2  test    rax, rax
0x180001cb5  jnz     short loc_180001CC6
0x180001cb7  test    edi, edi
0x180001cb9  jz      short loc_180001D07
0x180001cbb  mov     ecx, 8007000Eh; int
0x180001cc0  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001cc6  mov     rdx, [r14]; Src
0x180001cc9  test    rdx, rdx
0x180001ccc  jz      short loc_180001CDA
0x180001cce  lea     r8d, [rbp+1]
0x180001cd2  add     r8, r8; Size
0x180001cd5  call    memcpy_0
0x180001cda  mov     rdx, [rsi]; Src
0x180001cdd  test    rdx, rdx
0x180001ce0  jz      short loc_180001D07
0x180001ce2  lea     r8d, [r15+1]
0x180001ce6  add     r8, r8; Size
0x180001ce9  mov     ecx, ebp
0x180001ceb  mov     rax, [rbx]
0x180001cee  lea     rcx, [rax+rcx*2]; void *
0x180001cf2  call    memcpy_0
0x180001cf7  jmp     short loc_180001D07
0x180001cf9  mov     ecx, 8007000Eh; int
0x180001cfe  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180001d04  mov     rbx, r12
0x180001d07  mov     edi, 0FFFFFFFFh
0x180001d0c  mov     eax, edi
0x180001d0e  lock xadd [r14+10h], eax
0x180001d14  cmp     eax, 1
0x180001d17  jnz     short loc_180001D44
0x180001d19  mov     rcx, [r14]; bstrString
0x180001d1c  test    rcx, rcx
0x180001d1f  jz      short loc_180001D2A
0x180001d21  call    cs:__imp_SysFreeString
0x180001d27  mov     [r14], r12
0x180001d2a  mov     rcx, [r14+8]; Block
0x180001d2e  test    rcx, rcx
0x180001d31  jz      short loc_180001D3C
0x180001d33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d38  mov     [r14+8], r12
0x180001d3c  mov     rcx, r14; Block
0x180001d3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d44  mov     [rsp+68h+arg_10], rbx
0x180001d4c  mov     eax, edi
0x180001d4e  lock xadd [rsi+10h], eax
0x180001d53  cmp     eax, 1
0x180001d56  jnz     short loc_180001D83
0x180001d58  mov     rcx, [rsi]; bstrString
0x180001d5b  test    rcx, rcx
0x180001d5e  jz      short loc_180001D69
0x180001d60  call    cs:__imp_SysFreeString
0x180001d66  mov     [rsi], r12
0x180001d69  mov     rcx, [rsi+8]; Block
0x180001d6d  test    rcx, rcx
0x180001d70  jz      short loc_180001D7B
0x180001d72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d77  mov     [rsi+8], r12
0x180001d7b  mov     rcx, rsi; Block
0x180001d7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d83  test    rbx, rbx
0x180001d86  jz      short loc_180001D8D
0x180001d88  mov     rdx, [rbx]
0x180001d8b  jmp     short loc_180001D90
0x180001d8d  mov     rdx, r12; lpValueName
0x180001d90  mov     rcx, [rsp+68h+hKey]; hKey
0x180001d95  call    cs:__imp_RegDeleteValueW
0x180001d9b  mov     esi, eax
0x180001d9d  test    eax, 0FFFFFFFDh
0x180001da2  jz      short loc_180001DDA
0x180001da4  test    eax, eax
0x180001da6  jle     short loc_180001DB1
0x180001da8  movzx   esi, ax
0x180001dab  or      esi, 80070000h
0x180001db1  lea     rcx, [rsp+68h+arg_10]; this
0x180001db9  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180001dbe  nop
0x180001dbf  lea     rcx, [rsp+68h+hKey]; this
0x180001dc4  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180001dc9  mov     eax, esi
0x180001dcb  add     rsp, 30h
0x180001dcf  pop     r15
0x180001dd1  pop     r14
0x180001dd3  pop     r12
0x180001dd5  pop     rdi
0x180001dd6  pop     rsi
0x180001dd7  pop     rbp
0x180001dd8  pop     rbx
0x180001dd9  retn
0x180001dda  test    rbx, rbx
0x180001ddd  jz      short loc_180001E15
0x180001ddf  lock xadd [rbx+10h], edi
0x180001de4  cmp     edi, 1
0x180001de7  jnz     short loc_180001E15
0x180001de9  mov     rcx, [rbx]; bstrString
0x180001dec  test    rcx, rcx
0x180001def  jz      short loc_180001DFA
0x180001df1  call    cs:__imp_SysFreeString
0x180001df7  mov     [rbx], r12
0x180001dfa  mov     rcx, [rbx+8]; Block
0x180001dfe  test    rcx, rcx
0x180001e01  jz      short loc_180001E0C
0x180001e03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e08  mov     [rbx+8], r12
0x180001e0c  mov     rcx, rbx; Block
0x180001e0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e14  nop
0x180001e15  mov     rcx, [rsp+68h+hKey]; hKey
0x180001e1a  test    rcx, rcx
0x180001e1d  jz      short loc_180001E25
0x180001e1f  call    cs:__imp_RegCloseKey
0x180001e25  xor     eax, eax
0x180001e27  add     rsp, 30h
0x180001e2b  pop     r15
0x180001e2d  pop     r14
0x180001e2f  pop     r12
0x180001e31  pop     rdi
0x180001e32  pop     rsi
0x180001e33  pop     rbp
0x180001e34  pop     rbx
0x180001e35  retn
```
