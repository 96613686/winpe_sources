# CIEApplicationAssociation::GetClsidFromProgID(ushort const *,_GUID *)

- ea: `0x1800efda8`
- end: `0x1800f000f`
- name: `?GetClsidFromProgID@CIEApplicationAssociation@@SAJPEBGPEAU_GUID@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCLSID pclsid)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008eaa0`
- `0x1800efbd0`
- `0x1800efca4`

## callees

- `0x18001db50`
- `0x180023130`
- `0x180024ea0`
- `0x18002fee0`
- `0x180064f50`
- `0x1800efda8`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800effba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800effba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eff36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eff8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eff36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eff8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800efec3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800efec3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eff4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800eff4e`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800eff62`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800eff62`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800effa7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800effa7`

## string_xrefs

- `0x1800efe74`: `\Clsid`
- `0x1800efede`: `Clsid\`

## pseudocode

```c
__int64 __fastcall CIEApplicationAssociation::GetClsidFromProgID(unsigned __int16 *a1, LPCLSID pclsid)
{
  int v4; // ebx
  char *v5; // rdi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r14
  unsigned int v8; // r10d
  HANDLE CurrentProcess; // rax
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL Wow64Process; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[80]; // [rsp+A0h] [rbp-60h] BYREF

  pcbData = 78;
  phkResult = 0;
  if ( a1 && pclsid )
  {
    *pclsid = GUID_NULL;
    v4 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)&phkResult);
    if ( v4 >= 0 )
    {
      v5 = (char *)phkResult + 7;
      if ( (HKEY)((char *)phkResult + 7) < phkResult )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        v6 = (unsigned __int16 *)operator new(saturated_mul((unsigned __int64)v5, 2u));
        v7 = v6;
        if ( v6 )
        {
          v4 = StringCchCopyW(v6, (unsigned __int64)v5, a1);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(v7, (__int64)v5, L"\\Clsid");
            if ( v4 >= 0 )
            {
              if ( RegGetValueW(HKEY_CLASSES_ROOT, v7, 0, 0x10000006u, 0, sz, &pcbData) )
                goto LABEL_17;
              v4 = StringCchCopyW(SubKey, 0x50u, L"Clsid\\");
              if ( v4 >= 0 )
              {
                v4 = StringCchCatW(SubKey, v8, sz);
                if ( v4 >= 0 )
                {
                  if ( (phkResult = 0, RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult))
                    && ((Wow64Process = 0,
                         CurrentProcess = GetCurrentProcess(),
                         IsWow64Process(CurrentProcess, &Wow64Process),
                         Wow64Process)
                     || RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20219u, &phkResult))
                    || (v4 = CLSIDFromString(sz, pclsid), RegCloseKey(phkResult), v4 < 0) )
                  {
LABEL_17:
                    v4 = -2147221164;
                    *pclsid = GUID_NULL;
                  }
                }
              }
            }
          }
          operator delete(v7);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800efda8  mov     [rsp-8+arg_10], rbx
0x1800efdad  push    rbp
0x1800efdae  push    rsi
0x1800efdaf  push    rdi
0x1800efdb0  push    r14
0x1800efdb2  push    r15
0x1800efdb4  lea     rbp, [rsp-50h]
0x1800efdb9  sub     rsp, 150h
0x1800efdc0  mov     rax, cs:__security_cookie
0x1800efdc7  xor     rax, rsp
0x1800efdca  mov     [rbp+70h+var_30], rax
0x1800efdce  mov     [rsp+170h+var_124], 4Eh ; 'N'
0x1800efdd6  mov     rsi, rdx
0x1800efdd9  mov     [rsp+170h+phkResult], 0
0x1800efde2  mov     r15, rcx
0x1800efde5  test    rcx, rcx
0x1800efde8  jnz     short loc_1800EFDF4
0x1800efdea  mov     ebx, 80070057h
0x1800efdef  jmp     loc_1800EFFE9
0x1800efdf4  test    rsi, rsi
0x1800efdf7  jz      short loc_1800EFDEA
0x1800efdf9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800efe00  lea     r8, [rsp+170h+phkResult]; unsigned __int64 *
0x1800efe05  movdqu  xmmword ptr [rdx], xmm0
0x1800efe09  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800efe0e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800efe13  mov     ebx, eax
0x1800efe15  test    eax, eax
0x1800efe17  js      loc_1800EFFE9
0x1800efe1d  mov     rax, [rsp+170h+phkResult]
0x1800efe22  lea     rdi, [rax+7]
0x1800efe26  cmp     rdi, rax
0x1800efe29  jb      loc_1800EFFE4
0x1800efe2f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800efe36  mov     eax, 2
0x1800efe3b  mul     rdi
0x1800efe3e  cmovb   rax, rcx
0x1800efe42  mov     rcx, rax; Size
0x1800efe45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800efe4a  mov     r14, rax
0x1800efe4d  test    rax, rax
0x1800efe50  jnz     short loc_1800EFE5C
0x1800efe52  mov     ebx, 8007000Eh
0x1800efe57  jmp     loc_1800EFFE9
0x1800efe5c  mov     r8, r15; unsigned __int16 *
0x1800efe5f  mov     rdx, rdi; unsigned __int64
0x1800efe62  mov     rcx, r14; unsigned __int16 *
0x1800efe65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800efe6a  mov     ebx, eax
0x1800efe6c  test    eax, eax
0x1800efe6e  js      loc_1800EFFDA
0x1800efe74  lea     r8, aClsid_0; "\\Clsid"
0x1800efe7b  mov     rdx, rdi; unsigned __int64
0x1800efe7e  mov     rcx, r14; unsigned __int16 *
0x1800efe81  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800efe86  mov     ebx, eax
0x1800efe88  test    eax, eax
0x1800efe8a  js      loc_1800EFFDA
0x1800efe90  lea     rax, [rsp+170h+var_124]
0x1800efe95  mov     rdi, 0FFFFFFFF80000000h
0x1800efe9c  mov     [rsp+170h+pcbData], rax; pcbData
0x1800efea1  mov     r9d, 10000006h; dwFlags
0x1800efea7  lea     rax, [rsp+170h+sz]
0x1800efeac  xor     r8d, r8d; lpValue
0x1800efeaf  mov     [rsp+170h+pvData], rax; pvData
0x1800efeb4  mov     rdx, r14; lpSubKey
0x1800efeb7  mov     rcx, rdi; hkey
0x1800efeba  mov     [rsp+170h+pdwType], 0; pdwType
0x1800efec3  call    cs:__imp_RegGetValueW
0x1800efeca  nop     dword ptr [rax+rax+00h]
0x1800efecf  test    eax, eax
0x1800efed1  jnz     loc_1800EFFCA
0x1800efed7  lea     r10d, [rax+50h]
0x1800efedb  mov     edx, r10d; unsigned __int64
0x1800efede  lea     r8, aClsid_6; "Clsid\\"
0x1800efee5  lea     rcx, [rbp+70h+SubKey]; unsigned __int16 *
0x1800efee9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800efeee  mov     ebx, eax
0x1800efef0  test    eax, eax
0x1800efef2  js      loc_1800EFFDA
0x1800efef8  lea     r8, [rsp+170h+sz]; unsigned __int16 *
0x1800efefd  mov     edx, r10d; unsigned __int64
0x1800eff00  lea     rcx, [rbp+70h+SubKey]; unsigned __int16 *
0x1800eff04  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800eff09  mov     ebx, eax
0x1800eff0b  test    eax, eax
0x1800eff0d  js      loc_1800EFFDA
0x1800eff13  lea     rax, [rsp+170h+phkResult]
0x1800eff18  mov     [rsp+170h+phkResult], 0
0x1800eff21  mov     r9d, 20019h; samDesired
0x1800eff27  mov     [rsp+170h+pdwType], rax; phkResult
0x1800eff2c  xor     r8d, r8d; ulOptions
0x1800eff2f  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x1800eff33  mov     rcx, rdi; hKey
0x1800eff36  call    cs:__imp_RegOpenKeyExW
0x1800eff3d  nop     dword ptr [rax+rax+00h]
0x1800eff42  test    eax, eax
0x1800eff44  jz      short loc_1800EFF9F
0x1800eff46  mov     [rsp+170h+Wow64Process], 0
0x1800eff4e  call    cs:__imp_GetCurrentProcess
0x1800eff55  nop     dword ptr [rax+rax+00h]
0x1800eff5a  mov     rcx, rax; hProcess
0x1800eff5d  lea     rdx, [rsp+170h+Wow64Process]; Wow64Process
0x1800eff62  call    cs:__imp_IsWow64Process
0x1800eff69  nop     dword ptr [rax+rax+00h]
0x1800eff6e  cmp     [rsp+170h+Wow64Process], 0
0x1800eff73  jnz     short loc_1800EFFCA
0x1800eff75  lea     rax, [rsp+170h+phkResult]
0x1800eff7a  mov     r9d, 20219h; samDesired
0x1800eff80  xor     r8d, r8d; ulOptions
0x1800eff83  mov     [rsp+170h+pdwType], rax; phkResult
0x1800eff88  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x1800eff8c  mov     rcx, rdi; hKey
0x1800eff8f  call    cs:__imp_RegOpenKeyExW
0x1800eff96  nop     dword ptr [rax+rax+00h]
0x1800eff9b  test    eax, eax
0x1800eff9d  jnz     short loc_1800EFFCA
0x1800eff9f  mov     rdx, rsi; pclsid
0x1800effa2  lea     rcx, [rsp+170h+sz]; lpsz
0x1800effa7  call    cs:__imp_CLSIDFromString
0x1800effae  nop     dword ptr [rax+rax+00h]
0x1800effb3  mov     rcx, [rsp+170h+phkResult]; hKey
0x1800effb8  mov     ebx, eax
0x1800effba  call    cs:__imp_RegCloseKey
0x1800effc1  nop     dword ptr [rax+rax+00h]
0x1800effc6  test    ebx, ebx
0x1800effc8  jns     short loc_1800EFFDA
0x1800effca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800effd1  mov     ebx, 80040154h
0x1800effd6  movdqu  xmmword ptr [rsi], xmm0
0x1800effda  mov     rcx, r14; void *
0x1800effdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800effe2  jmp     short loc_1800EFFE9
0x1800effe4  mov     ebx, 80070216h
0x1800effe9  mov     eax, ebx
0x1800effeb  mov     rcx, [rbp+70h+var_30]
0x1800effef  xor     rcx, rsp; StackCookie
0x1800efff2  call    __security_check_cookie
0x1800efff7  mov     rbx, [rsp+170h+arg_10]
0x1800effff  add     rsp, 150h
0x1800f0006  pop     r15
0x1800f0008  pop     r14
0x1800f000a  pop     rdi
0x1800f000b  pop     rsi
0x1800f000c  pop     rbp
0x1800f000d  retn
```
