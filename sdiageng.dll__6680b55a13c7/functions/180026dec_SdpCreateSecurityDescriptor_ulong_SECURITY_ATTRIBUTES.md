# SdpCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180026dec`
- end: `0x180026ef6`
- name: `?SdpCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800101cc`

## callees

- `0x1800012a4`
- `0x180026bf4`
- `0x180026dec`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026ed2`
- `KERNEL32!GetLastError` at `0x180026ed2`
- `KERNEL32!LocalFree` at `0x180026ead`
- `KERNEL32!LocalFree` at `0x180026ead`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026e78`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026e78`

## string_xrefs

- `0x180026e20`: `SdpCreateSecurityDescriptor`
- `0x180026e46`: `SdpCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SdpCreateSecurityDescriptor(unsigned int a1, struct _SECURITY_ATTRIBUTES *a2)
{
  WCHAR *v2; // rdi
  signed int v4; // ebx
  int v5; // r8d
  int Sddl; // eax
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp+10h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  SecurityDescriptor = 0;
  StringSecurityDescriptor = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2450;
LABEL_3:
    SdpDebugTrace(1u, L"SdpCreateSecurityDescriptor", v5, v4);
    goto LABEL_9;
  }
  Sddl = SdpCreateSddl(a1, (unsigned __int16 **)&StringSecurityDescriptor);
  v4 = Sddl;
  if ( Sddl >= 0 )
  {
    v2 = (WCHAR *)StringSecurityDescriptor;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
      {
        v5 = 2459;
        goto LABEL_3;
      }
    }
    a2->lpSecurityDescriptor = SecurityDescriptor;
    a2->nLength = 24;
    a2->bInheritHandle = 0;
    SecurityDescriptor = 0;
  }
  else
  {
    SdpDebugTrace(1u, L"SdpCreateSecurityDescriptor", 2453, Sddl);
    v2 = (WCHAR *)StringSecurityDescriptor;
  }
LABEL_9:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v2 )
    operator delete(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026dec  mov     rax, rsp
0x180026def  mov     [rax+8], rbx
0x180026df3  mov     [rax+20h], rsi
0x180026df7  push    rdi
0x180026df8  sub     rsp, 20h
0x180026dfc  xor     edi, edi
0x180026dfe  mov     qword ptr [rax+10h], 0
0x180026e06  mov     [rax+18h], rdi
0x180026e0a  mov     rsi, rdx
0x180026e0d  test    rdx, rdx
0x180026e10  jnz     short loc_180026E33
0x180026e12  mov     ebx, 80070057h
0x180026e17  mov     r8d, 992h; int
0x180026e1d  mov     r9d, ebx; int
0x180026e20  lea     rdx, aSdpcreatesecur; "SdpCreateSecurityDescriptor"
0x180026e27  mov     ecx, 1; Level
0x180026e2c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026e31  jmp     short loc_180026EA3
0x180026e33  lea     rdx, [rsp+28h+StringSecurityDescriptor]; unsigned __int16 **
0x180026e38  call    ?SdpCreateSddl@@YAJKPEAPEAG@Z; SdpCreateSddl(ulong,ushort * *)
0x180026e3d  mov     ebx, eax
0x180026e3f  test    eax, eax
0x180026e41  jns     short loc_180026E64
0x180026e43  mov     r9d, eax; int
0x180026e46  lea     rdx, aSdpcreatesecur; "SdpCreateSecurityDescriptor"
0x180026e4d  mov     r8d, 995h; int
0x180026e53  mov     ecx, 1; Level
0x180026e58  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180026e5d  mov     rdi, [rsp+28h+StringSecurityDescriptor]
0x180026e62  jmp     short loc_180026EA3
0x180026e64  mov     rdi, [rsp+28h+StringSecurityDescriptor]
0x180026e69  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180026e6e  xor     r9d, r9d; SecurityDescriptorSize
0x180026e71  mov     rcx, rdi; StringSecurityDescriptor
0x180026e74  lea     edx, [r9+1]; StringSDRevision
0x180026e78  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180026e7e  test    eax, eax
0x180026e80  jz      short loc_180026ED2
0x180026e82  xor     ebx, ebx
0x180026e84  mov     rax, [rsp+28h+SecurityDescriptor]
0x180026e89  mov     [rsi+8], rax
0x180026e8d  mov     dword ptr [rsi], 18h
0x180026e93  mov     dword ptr [rsi+10h], 0
0x180026e9a  mov     [rsp+28h+SecurityDescriptor], 0
0x180026ea3  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x180026ea8  test    rcx, rcx
0x180026eab  jz      short loc_180026EB3
0x180026ead  call    cs:__imp_LocalFree
0x180026eb3  test    rdi, rdi
0x180026eb6  jz      short loc_180026EC0
0x180026eb8  mov     rcx, rdi; Block
0x180026ebb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026ec0  mov     rsi, [rsp+28h+arg_18]
0x180026ec5  mov     eax, ebx
0x180026ec7  mov     rbx, [rsp+28h+arg_0]
0x180026ecc  add     rsp, 20h
0x180026ed0  pop     rdi
0x180026ed1  retn
0x180026ed2  call    cs:__imp_GetLastError
0x180026ed8  mov     ebx, eax
0x180026eda  test    eax, eax
0x180026edc  jle     short loc_180026EE7
0x180026ede  movzx   ebx, ax
0x180026ee1  or      ebx, 80070000h
0x180026ee7  test    ebx, ebx
0x180026ee9  jns     short loc_180026E84
0x180026eeb  mov     r8d, 99Bh
0x180026ef1  jmp     loc_180026E1D
```
