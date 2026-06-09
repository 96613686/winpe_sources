# CWshURLShortcut::Load(ushort *)

- ea: `0x18000d940`
- end: `0x18000db4d`
- name: `?Load@CWshURLShortcut@@UEAAJPEAG@Z`
- size: `525`
- prototype: `int(CWshURLShortcut *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d940`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000da82`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000da82`
- `ole32!CoCreateInstance` at `0x18000dad5`
- `ole32!CoCreateInstance` at `0x18000dad5`
- `KERNEL32!GetLastError` at `0x18000da2d`
- `KERNEL32!GetLastError` at `0x18000da2d`
- `KERNEL32!WideCharToMultiByte` at `0x18000d9b9`
- `KERNEL32!WideCharToMultiByte` at `0x18000da07`
- `KERNEL32!WideCharToMultiByte` at `0x18000d9b9`
- `KERNEL32!WideCharToMultiByte` at `0x18000da07`
- `KERNEL32!MultiByteToWideChar` at `0x18000da6b`
- `KERNEL32!MultiByteToWideChar` at `0x18000daa5`
- `KERNEL32!MultiByteToWideChar` at `0x18000da6b`
- `KERNEL32!MultiByteToWideChar` at `0x18000daa5`
- `KERNEL32!GetFullPathNameA` at `0x18000da23`
- `KERNEL32!GetFullPathNameA` at `0x18000da23`

## pseudocode

```c
int __fastcall CWshURLShortcut::Load(CWshURLShortcut *this, unsigned __int16 *a2)
{
  int result; // eax
  CHAR *v5; // rsi
  int v6; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v8; // rax
  void *v9; // rsp
  DWORD FullPathNameA; // eax
  int v11; // eax
  int v12; // edi
  WCHAR *v13; // rax
  _QWORD *v14; // rdi
  int v15; // esi
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  CHAR Buffer[272]; // [rsp+50h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147467261;
  if ( *((_QWORD *)this + 11) )
    return -2147418113;
  v5 = 0;
  v6 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 )
  {
    v8 = v6 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    v5 = MultiByteStr;
    WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  }
  *(_QWORD *)MultiByteStr = 0;
  FullPathNameA = GetFullPathNameA(v5, 0x104u, Buffer, (LPSTR *)MultiByteStr);
  if ( FullPathNameA )
  {
    if ( FullPathNameA < 0x104 )
    {
      v11 = MultiByteToWideChar(0, 0, Buffer, -1, 0, 0);
      v12 = v11;
      if ( v11 )
      {
        v13 = SysAllocStringLen(0, v11 - 1);
        *((_QWORD *)this + 11) = v13;
        if ( v13 )
          MultiByteToWideChar(0, 0, Buffer, -1, v13, v12);
      }
      else
      {
        *((_QWORD *)this + 11) = 0;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v14 = (_QWORD *)((char *)this + 72);
        result = CoCreateInstance(&CLSID_InternetShortcut, 0, 1u, &IID_IUniformResourceLocatorA, (LPVOID *)this + 9);
        if ( result >= 0 )
        {
          v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v14)(*v14, &IID_IPersistFile, (char *)this + 80);
          if ( v15 >= 0 )
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 10) + 40LL))(
              *((_QWORD *)this + 10),
              *((_QWORD *)this + 11),
              0);
          else
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
          return v15;
        }
      }
      else
      {
        return -2147024882;
      }
    }
    else
    {
      return -2147024809;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000d940  push    rbp
0x18000d942  push    rsi
0x18000d943  push    rdi
0x18000d944  push    r14
0x18000d946  push    r15
0x18000d948  sub     rsp, 170h
0x18000d94f  lea     rbp, [rsp+40h]
0x18000d954  mov     [rbp+150h+arg_10], rbx
0x18000d95b  mov     rax, cs:__security_cookie
0x18000d962  xor     rax, rbp
0x18000d965  mov     [rbp+150h+var_30], rax
0x18000d96c  xor     r15d, r15d
0x18000d96f  mov     rdi, rdx
0x18000d972  mov     rbx, rcx
0x18000d975  test    rdx, rdx
0x18000d978  jnz     short loc_18000D984
0x18000d97a  mov     eax, 80004003h
0x18000d97f  jmp     loc_18000DB28
0x18000d984  cmp     [rcx+58h], r15
0x18000d988  jz      short loc_18000D994
0x18000d98a  mov     eax, 8000FFFFh
0x18000d98f  jmp     loc_18000DB28
0x18000d994  mov     [rsp+190h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000d999  or      r14d, 0FFFFFFFFh
0x18000d99d  mov     [rsp+190h+lpDefaultChar], r15; lpDefaultChar
0x18000d9a2  mov     r9d, r14d; cchWideChar
0x18000d9a5  mov     [rsp+190h+cbMultiByte], r15d; cbMultiByte
0x18000d9aa  mov     r8, rdi; lpWideCharStr
0x18000d9ad  xor     edx, edx; dwFlags
0x18000d9af  mov     [rsp+190h+lpMultiByteStr], r15; lpMultiByteStr
0x18000d9b4  xor     ecx, ecx; CodePage
0x18000d9b6  mov     rsi, r15
0x18000d9b9  call    cs:__imp_WideCharToMultiByte
0x18000d9bf  movsxd  rdx, eax
0x18000d9c2  test    eax, eax
0x18000d9c4  jz      short loc_18000DA0D
0x18000d9c6  lea     rax, [rdx+0Fh]
0x18000d9ca  cmp     rax, rdx
0x18000d9cd  ja      short loc_18000D9D9
0x18000d9cf  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000d9d9  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000d9dd  call    _alloca_probe
0x18000d9e2  sub     rsp, rax
0x18000d9e5  mov     r9d, r14d; cchWideChar
0x18000d9e8  mov     r8, rdi; lpWideCharStr
0x18000d9eb  xor     ecx, ecx; CodePage
0x18000d9ed  mov     [rsp+190h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000d9f2  lea     rsi, [rsp+190h+MultiByteStr]
0x18000d9f7  mov     [rsp+190h+lpDefaultChar], r15; lpDefaultChar
0x18000d9fc  mov     [rsp+190h+cbMultiByte], edx; cbMultiByte
0x18000da00  xor     edx, edx; dwFlags
0x18000da02  mov     [rsp+190h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000da07  call    cs:__imp_WideCharToMultiByte
0x18000da0d  mov     edi, 104h
0x18000da12  mov     qword ptr [rbp+150h+MultiByteStr], r15
0x18000da16  mov     edx, edi; nBufferLength
0x18000da18  lea     r9, [rbp+150h+MultiByteStr]; lpFilePart
0x18000da1c  lea     r8, [rbp+150h+Buffer]; lpBuffer
0x18000da20  mov     rcx, rsi; lpFileName
0x18000da23  call    cs:__imp_GetFullPathNameA
0x18000da29  test    eax, eax
0x18000da2b  jnz     short loc_18000DA48
0x18000da2d  call    cs:__imp_GetLastError
0x18000da33  test    eax, eax
0x18000da35  jle     loc_18000DB28
0x18000da3b  movzx   eax, ax
0x18000da3e  or      eax, 80070000h
0x18000da43  jmp     loc_18000DB28
0x18000da48  cmp     eax, edi
0x18000da4a  jb      short loc_18000DA56
0x18000da4c  mov     eax, 80070057h
0x18000da51  jmp     loc_18000DB28
0x18000da56  mov     [rsp+190h+cbMultiByte], r15d; cchWideChar
0x18000da5b  lea     r8, [rbp+150h+Buffer]; lpMultiByteStr
0x18000da5f  mov     r9d, r14d; cbMultiByte
0x18000da62  mov     [rsp+190h+lpMultiByteStr], r15; lpWideCharStr
0x18000da67  xor     edx, edx; dwFlags
0x18000da69  xor     ecx, ecx; CodePage
0x18000da6b  call    cs:__imp_MultiByteToWideChar
0x18000da71  mov     edi, eax
0x18000da73  test    eax, eax
0x18000da75  jnz     short loc_18000DA7D
0x18000da77  mov     [rbx+58h], r15
0x18000da7b  jmp     short loc_18000DAAB
0x18000da7d  lea     edx, [rax-1]; ui
0x18000da80  xor     ecx, ecx; strIn
0x18000da82  call    cs:__imp_SysAllocStringLen
0x18000da88  mov     [rbx+58h], rax
0x18000da8c  test    rax, rax
0x18000da8f  jz      short loc_18000DAAB
0x18000da91  mov     [rsp+190h+cbMultiByte], edi; cchWideChar
0x18000da95  lea     r8, [rbp+150h+Buffer]; lpMultiByteStr
0x18000da99  mov     r9d, r14d; cbMultiByte
0x18000da9c  mov     [rsp+190h+lpMultiByteStr], rax; lpWideCharStr
0x18000daa1  xor     edx, edx; dwFlags
0x18000daa3  xor     ecx, ecx; CodePage
0x18000daa5  call    cs:__imp_MultiByteToWideChar
0x18000daab  cmp     [rbx+58h], r15
0x18000daaf  jnz     short loc_18000DAB8
0x18000dab1  mov     eax, 8007000Eh
0x18000dab6  jmp     short loc_18000DB28
0x18000dab8  xor     edx, edx; pUnkOuter
0x18000daba  lea     rdi, [rbx+48h]
0x18000dabe  lea     r9, IID_IUniformResourceLocatorA; riid
0x18000dac5  mov     [rsp+190h+lpMultiByteStr], rdi; ppv
0x18000daca  lea     rcx, CLSID_InternetShortcut; rclsid
0x18000dad1  lea     r8d, [rdx+1]; dwClsContext
0x18000dad5  call    cs:__imp_CoCreateInstance
0x18000dadb  test    eax, eax
0x18000dadd  js      short loc_18000DB28
0x18000dadf  mov     rcx, [rdi]
0x18000dae2  lea     r8, [rbx+50h]
0x18000dae6  lea     rdx, IID_IPersistFile
0x18000daed  mov     rax, [rcx]
0x18000daf0  mov     rax, [rax]
0x18000daf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf8  mov     esi, eax
0x18000dafa  test    eax, eax
0x18000dafc  jns     short loc_18000DB0F
0x18000dafe  mov     rcx, [rdi]
0x18000db01  mov     rdx, [rcx]
0x18000db04  mov     rax, [rdx+10h]
0x18000db08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0d  jmp     short loc_18000DB26
0x18000db0f  mov     rcx, [rbx+50h]
0x18000db13  xor     r8d, r8d
0x18000db16  mov     rdx, [rbx+58h]
0x18000db1a  mov     rax, [rcx]
0x18000db1d  mov     rax, [rax+28h]
0x18000db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db26  mov     eax, esi
0x18000db28  mov     rcx, [rbp+150h+var_30]
0x18000db2f  xor     rcx, rbp; StackCookie
0x18000db32  call    __security_check_cookie
0x18000db37  mov     rbx, [rbp+150h+arg_10]
0x18000db3e  lea     rsp, [rbp+130h]
0x18000db45  pop     r15
0x18000db47  pop     r14
0x18000db49  pop     rdi
0x18000db4a  pop     rsi
0x18000db4b  pop     rbp
0x18000db4c  retn
```
