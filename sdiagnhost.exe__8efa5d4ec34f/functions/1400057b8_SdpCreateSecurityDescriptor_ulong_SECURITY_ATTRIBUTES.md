# SdpCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1400057b8`
- end: `0x1400058b9`
- name: `?SdpCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `257`
- prototype: `__int64 __fastcall(unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140001ee4`

## callees

- `0x1400055d8`
- `0x1400057b8`
- `0x140005964`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000583a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000583a`
- `KERNEL32!LocalFree` at `0x14000586f`
- `KERNEL32!LocalFree` at `0x14000586f`
- `KERNEL32!GetLastError` at `0x140005895`
- `KERNEL32!GetLastError` at `0x140005895`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000587d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000587d`

## string_xrefs

- `0x1400057ec`: `SdpCreateSecurityDescriptor`
- `0x14000580d`: `SdpCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SdpCreateSecurityDescriptor(unsigned int a1, struct _SECURITY_ATTRIBUTES *a2)
{
  WCHAR *v2; // rdi
  signed int v4; // ebx
  int v5; // r8d
  int Sddl; // eax
  unsigned int v7; // ecx
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
    SdpDebugTrace(a1, L"SdpCreateSecurityDescriptor", v5, v4);
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
    SdpDebugTrace(v7, L"SdpCreateSecurityDescriptor", 2453, Sddl);
    v2 = (WCHAR *)StringSecurityDescriptor;
  }
LABEL_9:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v2 )
    operator delete[](v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400057b8  mov     rax, rsp
0x1400057bb  mov     [rax+8], rbx
0x1400057bf  mov     [rax+20h], rsi
0x1400057c3  push    rdi
0x1400057c4  sub     rsp, 20h
0x1400057c8  xor     edi, edi
0x1400057ca  mov     qword ptr [rax+10h], 0
0x1400057d2  mov     [rax+18h], rdi
0x1400057d6  mov     rsi, rdx
0x1400057d9  test    rdx, rdx
0x1400057dc  jnz     short loc_1400057FA
0x1400057de  mov     ebx, 80070057h
0x1400057e3  mov     r8d, 992h; int
0x1400057e9  mov     r9d, ebx; int
0x1400057ec  lea     rdx, aSdpcreatesecur; "SdpCreateSecurityDescriptor"
0x1400057f3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400057f8  jmp     short loc_140005865
0x1400057fa  lea     rdx, [rsp+28h+StringSecurityDescriptor]; unsigned __int16 **
0x1400057ff  call    ?SdpCreateSddl@@YAJKPEAPEAG@Z; SdpCreateSddl(ulong,ushort * *)
0x140005804  mov     ebx, eax
0x140005806  test    eax, eax
0x140005808  jns     short loc_140005826
0x14000580a  mov     r9d, eax; int
0x14000580d  lea     rdx, aSdpcreatesecur; "SdpCreateSecurityDescriptor"
0x140005814  mov     r8d, 995h; int
0x14000581a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x14000581f  mov     rdi, [rsp+28h+StringSecurityDescriptor]
0x140005824  jmp     short loc_140005865
0x140005826  mov     rdi, [rsp+28h+StringSecurityDescriptor]
0x14000582b  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x140005830  xor     r9d, r9d; SecurityDescriptorSize
0x140005833  mov     rcx, rdi; StringSecurityDescriptor
0x140005836  lea     edx, [r9+1]; StringSDRevision
0x14000583a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140005840  test    eax, eax
0x140005842  jz      short loc_140005895
0x140005844  xor     ebx, ebx
0x140005846  mov     rax, [rsp+28h+SecurityDescriptor]
0x14000584b  mov     [rsi+8], rax
0x14000584f  mov     dword ptr [rsi], 18h
0x140005855  mov     dword ptr [rsi+10h], 0
0x14000585c  mov     [rsp+28h+SecurityDescriptor], 0
0x140005865  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x14000586a  test    rcx, rcx
0x14000586d  jz      short loc_140005875
0x14000586f  call    cs:__imp_LocalFree
0x140005875  test    rdi, rdi
0x140005878  jz      short loc_140005883
0x14000587a  mov     rcx, rdi
0x14000587d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005883  mov     rsi, [rsp+28h+arg_18]
0x140005888  mov     eax, ebx
0x14000588a  mov     rbx, [rsp+28h+arg_0]
0x14000588f  add     rsp, 20h
0x140005893  pop     rdi
0x140005894  retn
0x140005895  call    cs:__imp_GetLastError
0x14000589b  mov     ebx, eax
0x14000589d  test    eax, eax
0x14000589f  jle     short loc_1400058AA
0x1400058a1  movzx   ebx, ax
0x1400058a4  or      ebx, 80070000h
0x1400058aa  test    ebx, ebx
0x1400058ac  jns     short loc_140005846
0x1400058ae  mov     r8d, 99Bh
0x1400058b4  jmp     loc_1400057E9
```
