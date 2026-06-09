# CImgSrvPacket::GetNamespaceName(ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x180010d70`
- end: `0x180010eea`
- name: `?GetNamespaceName@CImgSrvPacket@@AEAAKPEBG0KPEAPEAG@Z`
- size: `378`
- prototype: `unsigned int __fastcall(CImgSrvPacket *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800102a0`

## callees

- `0x180010d70`
- `0x180011090`
- `0x1800127c8`
- `0x180017010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010ecb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010ecb`
- `KERNEL32!GetLastError` at `0x180010e15`
- `KERNEL32!GetLastError` at `0x180010e56`
- `KERNEL32!GetLastError` at `0x180010e15`
- `KERNEL32!GetLastError` at `0x180010e56`
- `KERNEL32!FreeLibrary` at `0x180010eb2`
- `KERNEL32!FreeLibrary` at `0x180010eb2`
- `KERNEL32!GetModuleHandleExW` at `0x180010e05`
- `KERNEL32!GetModuleHandleExW` at `0x180010e05`
- `KERNEL32!GetProcAddress` at `0x180010e45`
- `KERNEL32!GetProcAddress` at `0x180010e45`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x180010dbd`
- `WdsCommonLib!?FormatString@@YAKPEAPEAG_KPEBGZZ` at `0x180010dbd`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010e8d`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x180010e8d`

## string_xrefs

- `0x180010dfe`: `WDSMC.DLL`

## pseudocode

```c
__int64 __fastcall CImgSrvPacket::GetNamespaceName(
        CImgSrvPacket *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5)
{
  unsigned __int16 *v5; // rdi
  __int64 v6; // rbx
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  FARPROC ProcAddress; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  HMODULE phModule; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 *v16; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  v5 = 0;
  v16 = 0;
  if ( a2 && *a2 && a3 && *a3 )
  {
    v6 = FormatString(&v16, 0, L"WDS:%s/%s/%u", a2, a3, a4);
    if ( !(unsigned int)ElValidateWin32_6(v6) )
      v5 = v16;
  }
  else
  {
    LODWORD(v6) = 87;
  }
  if ( !(unsigned int)ElValidateWin32_3((unsigned int)v6, a2, a3, 1155) )
  {
    if ( !GetModuleHandleExW(0, L"WDSMC.DLL", &phModule) )
    {
      LastError = GetLastError();
      LODWORD(v6) = LastError;
      if ( LastError == 126 )
      {
LABEL_16:
        LODWORD(v6) = DuplicateStringW(&pszSrch, a5);
        ElValidateWin32_3((unsigned int)v6, v11, v12, 1210);
        goto LABEL_17;
      }
      if ( (unsigned int)ElValidateWin32_3(LastError, v8, v9, 1178) )
        goto LABEL_17;
    }
    ProcAddress = GetProcAddress(phModule, "WdsTransportServerCanJoinNamespace");
    if ( !ProcAddress )
    {
      LODWORD(v6) = GetLastError();
      goto LABEL_17;
    }
    if ( !((unsigned int (__fastcall *)(unsigned __int16 *))ProcAddress)(v5) )
    {
      LODWORD(v6) = 0;
      *a5 = v5;
      v5 = 0;
      goto LABEL_17;
    }
    goto LABEL_16;
  }
LABEL_17:
  if ( phModule )
  {
    FreeLibrary(phModule);
    phModule = 0;
  }
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010d70  mov     rax, rsp
0x180010d73  mov     [rax+18h], rbx
0x180010d77  mov     [rax+20h], rsi
0x180010d7b  mov     [rax+8], rcx
0x180010d7f  push    rdi
0x180010d80  sub     rsp, 30h
0x180010d84  xor     esi, esi
0x180010d86  mov     [rax+8], rsi
0x180010d8a  mov     edi, esi
0x180010d8c  mov     [rax+10h], rsi
0x180010d90  test    rdx, rdx
0x180010d93  jz      short loc_180010DDD
0x180010d95  cmp     [rdx], si
0x180010d98  jz      short loc_180010DDD
0x180010d9a  test    r8, r8
0x180010d9d  jz      short loc_180010DDD
0x180010d9f  cmp     [r8], si
0x180010da3  jz      short loc_180010DDD
0x180010da5  mov     [rax-10h], r9d
0x180010da9  lea     rcx, [rax+10h]
0x180010dad  mov     [rax-18h], r8
0x180010db1  mov     r9, rdx
0x180010db4  lea     r8, aWdsSSU; "WDS:%s/%s/%u"
0x180010dbb  xor     edx, edx
0x180010dbd  call    cs:__imp_?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x180010dc4  nop     dword ptr [rax+rax+00h]
0x180010dc9  mov     ecx, eax
0x180010dcb  mov     ebx, eax
0x180010dcd  call    ElValidateWin32_6
0x180010dd2  test    eax, eax
0x180010dd4  jnz     short loc_180010DE2
0x180010dd6  mov     rdi, [rsp+38h+arg_8]
0x180010ddb  jmp     short loc_180010DE2
0x180010ddd  mov     ebx, 57h ; 'W'
0x180010de2  mov     r9d, 483h
0x180010de8  mov     ecx, ebx
0x180010dea  call    ElValidateWin32_3
0x180010def  test    eax, eax
0x180010df1  jnz     loc_180010EA8
0x180010df7  lea     r8, [rsp+38h+phModule]; phModule
0x180010dfc  xor     ecx, ecx; dwFlags
0x180010dfe  lea     rdx, ModuleName; "WDSMC.DLL"
0x180010e05  call    cs:__imp_GetModuleHandleExW
0x180010e0c  nop     dword ptr [rax+rax+00h]
0x180010e11  test    eax, eax
0x180010e13  jnz     short loc_180010E39
0x180010e15  call    cs:__imp_GetLastError
0x180010e1c  nop     dword ptr [rax+rax+00h]
0x180010e21  mov     ebx, eax
0x180010e23  cmp     eax, 7Eh ; '~'
0x180010e26  jz      short loc_180010E81
0x180010e28  mov     r9d, 49Ah
0x180010e2e  mov     ecx, eax
0x180010e30  call    ElValidateWin32_3
0x180010e35  test    eax, eax
0x180010e37  jnz     short loc_180010EA8
0x180010e39  mov     rcx, [rsp+38h+phModule]; hModule
0x180010e3e  lea     rdx, ProcName; "WdsTransportServerCanJoinNamespace"
0x180010e45  call    cs:__imp_GetProcAddress
0x180010e4c  nop     dword ptr [rax+rax+00h]
0x180010e51  test    rax, rax
0x180010e54  jnz     short loc_180010E66
0x180010e56  call    cs:__imp_GetLastError
0x180010e5d  nop     dword ptr [rax+rax+00h]
0x180010e62  mov     ebx, eax
0x180010e64  jmp     short loc_180010EA8
0x180010e66  mov     rcx, rdi
0x180010e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e6e  test    eax, eax
0x180010e70  jnz     short loc_180010E81
0x180010e72  mov     rax, [rsp+38h+arg_20]
0x180010e77  mov     ebx, esi
0x180010e79  mov     [rax], rdi
0x180010e7c  mov     rdi, rsi
0x180010e7f  jmp     short loc_180010EA8
0x180010e81  mov     rdx, [rsp+38h+arg_20]
0x180010e86  lea     rcx, pszSrch
0x180010e8d  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x180010e94  nop     dword ptr [rax+rax+00h]
0x180010e99  mov     ecx, eax
0x180010e9b  mov     r9d, 4BAh
0x180010ea1  mov     ebx, eax
0x180010ea3  call    ElValidateWin32_3
0x180010ea8  mov     rcx, [rsp+38h+phModule]; hLibModule
0x180010ead  test    rcx, rcx
0x180010eb0  jz      short loc_180010EC3
0x180010eb2  call    cs:__imp_FreeLibrary
0x180010eb9  nop     dword ptr [rax+rax+00h]
0x180010ebe  mov     [rsp+38h+phModule], rsi
0x180010ec3  test    rdi, rdi
0x180010ec6  jz      short loc_180010ED7
0x180010ec8  mov     rcx, rdi
0x180010ecb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010ed2  nop     dword ptr [rax+rax+00h]
0x180010ed7  mov     rsi, [rsp+38h+arg_18]
0x180010edc  mov     eax, ebx
0x180010ede  mov     rbx, [rsp+38h+arg_10]
0x180010ee3  add     rsp, 30h
0x180010ee7  pop     rdi
0x180010ee8  retn
```
