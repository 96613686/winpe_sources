# CredProtectEx

- ea: `0x180040fb0`
- end: `0x180041113`
- name: `CredProtectEx`
- size: `355`
- prototype: `BOOL __stdcall(ULONG Flags, LPWSTR pszCredentials, DWORD cchCredentials, LPWSTR pszProtectedCredentials, DWORD *pcchMaxChars, CRED_PROTECTION_TYPE *ProtectionType)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040e40`
- `0x180041120`

## callees

- `0x180040fb0`
- `0x180041ce0`
- `0x18004f902`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800410ea`
- `ntdll!RtlNtStatusToDosError` at `0x1800410ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800410f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800410f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800410d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800410d0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800410ab`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800410ab`

## pseudocode

```c
BOOL __stdcall CredProtectEx(
        ULONG Flags,
        LPWSTR pszCredentials,
        DWORD cchCredentials,
        LPWSTR pszProtectedCredentials,
        DWORD *pcchMaxChars,
        CRED_PROTECTION_TYPE *ProtectionType)
{
  DWORD *v7; // rbx
  ULONG v8; // r15d
  int v9; // eax
  void *v10; // rsi
  int v11; // ebp
  DWORD v12; // edi
  __int64 v13; // rdi
  CRED_PROTECTION_TYPE *v14; // rbx
  NTSTATUS v15; // ecx
  DWORD v17; // eax
  _QWORD Source1[2]; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+88h] [rbp+10h] BYREF

  Src = 0;
  Source1[0] = 0;
  if ( pszCredentials && (v7 = pcchMaxChars) != 0 && (!*pcchMaxChars || pszProtectedCredentials) && (Flags & 3) == Flags )
  {
    v8 = Flags & 2;
    v9 = CredpEncryptAndMarshalBinaryBlobEx(
           Flags & 1,
           (_DWORD)pszCredentials,
           v8 != 0,
           (_DWORD)pszCredentials,
           2 * cchCredentials,
           (__int64)&Src,
           (__int64)Source1);
    v10 = Src;
    v11 = v9;
    if ( v9 >= 0 )
    {
      v12 = 0;
      if ( Src )
      {
        v13 = -1;
        do
          ++v13;
        while ( *((_WORD *)Src + v13) );
        v12 = v13 + 1;
      }
      if ( v12 > *v7 )
      {
        *v7 = v12;
        v11 = -1073741789;
      }
      else
      {
        memcpy_0(pszProtectedCredentials, Src, 2LL * v12);
        *v7 = v12;
        v14 = ProtectionType;
        if ( ProtectionType )
        {
          if ( v8 )
            *ProtectionType = CredForSystemProtection;
          else
            *v14 = (RtlCompareMemory(Source1, &qword_18007BA88, 8u) == 8) + 1;
        }
      }
    }
    if ( v10 )
      LocalFree(v10);
    if ( v11 >= 0 )
      return 1;
    v15 = v11;
  }
  else
  {
    v15 = -1073741811;
  }
  v17 = RtlNtStatusToDosError(v15);
  SetLastError(v17);
  return 0;
}

```

## disassembly

```asm
0x180040fb0  mov     rax, rsp
0x180040fb3  mov     [rax+8], rbx
0x180040fb7  mov     [rax+18h], rbp
0x180040fbb  push    rsi
0x180040fbc  push    rdi
0x180040fbd  push    r12
0x180040fbf  push    r14
0x180040fc1  push    r15
0x180040fc3  sub     rsp, 50h
0x180040fc7  xor     r12d, r12d
0x180040fca  mov     r14, r9
0x180040fcd  mov     [rax+10h], r12
0x180040fd1  mov     [rax-38h], r12
0x180040fd5  test    rdx, rdx
0x180040fd8  jz      loc_1800410E5
0x180040fde  mov     rbx, [rsp+78h+pcchMaxChars]
0x180040fe6  test    rbx, rbx
0x180040fe9  jz      loc_1800410E5
0x180040fef  cmp     [rbx], r12d
0x180040ff2  jz      short loc_180040FFD
0x180040ff4  test    r9, r9
0x180040ff7  jz      loc_1800410E5
0x180040ffd  mov     eax, ecx
0x180040fff  and     eax, 3
0x180041002  cmp     eax, ecx
0x180041004  jnz     loc_1800410E5
0x18004100a  lea     eax, [r8+r8]
0x18004100e  mov     r15d, ecx
0x180041011  lea     r9, [rsp+78h+Source1]
0x180041016  mov     r8d, r12d
0x180041019  mov     [rsp+78h+var_48], r9
0x18004101e  and     r15d, 2
0x180041022  lea     r9, [rsp+78h+Src]
0x18004102a  mov     [rsp+78h+var_50], r9
0x18004102f  setnz   r8b
0x180041033  and     ecx, 1
0x180041036  mov     [rsp+78h+var_58], eax
0x18004103a  mov     r9, rdx
0x18004103d  call    CredpEncryptAndMarshalBinaryBlobEx
0x180041042  mov     rsi, [rsp+78h+Src]
0x18004104a  mov     ebp, eax
0x18004104c  test    eax, eax
0x18004104e  js      short loc_1800410C8
0x180041050  mov     edi, r12d
0x180041053  test    rsi, rsi
0x180041056  jz      short loc_180041068
0x180041058  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004105c  inc     rdi
0x18004105f  cmp     [rsi+rdi*2], r12w
0x180041064  jnz     short loc_18004105C
0x180041066  inc     edi
0x180041068  cmp     edi, [rbx]
0x18004106a  ja      short loc_1800410C1
0x18004106c  mov     r8d, edi
0x18004106f  mov     rdx, rsi; Src
0x180041072  add     r8, r8; Size
0x180041075  mov     rcx, r14; void *
0x180041078  call    memcpy_0
0x18004107d  mov     [rbx], edi
0x18004107f  mov     rbx, [rsp+78h+ProtectionType]
0x180041087  test    rbx, rbx
0x18004108a  jz      short loc_1800410C8
0x18004108c  test    r15d, r15d
0x18004108f  jz      short loc_180041099
0x180041091  mov     dword ptr [rbx], 3
0x180041097  jmp     short loc_1800410C8
0x180041099  mov     r8d, 8; Length
0x18004109f  lea     rdx, qword_18007BA88; Source2
0x1800410a6  lea     rcx, [rsp+78h+Source1]; Source1
0x1800410ab  call    cs:__imp_RtlCompareMemory
0x1800410b1  cmp     rax, 8
0x1800410b5  mov     ecx, r12d
0x1800410b8  setz    cl
0x1800410bb  inc     ecx
0x1800410bd  mov     [rbx], ecx
0x1800410bf  jmp     short loc_1800410C8
0x1800410c1  mov     [rbx], edi
0x1800410c3  mov     ebp, 0C0000023h
0x1800410c8  test    rsi, rsi
0x1800410cb  jz      short loc_1800410D6
0x1800410cd  mov     rcx, rsi; hMem
0x1800410d0  call    cs:__imp_LocalFree
0x1800410d6  test    ebp, ebp
0x1800410d8  jns     short loc_1800410DE
0x1800410da  mov     ecx, ebp
0x1800410dc  jmp     short loc_1800410EA
0x1800410de  mov     eax, 1
0x1800410e3  jmp     short loc_1800410FA
0x1800410e5  mov     ecx, 0C000000Dh; Status
0x1800410ea  call    cs:__imp_RtlNtStatusToDosError
0x1800410f0  mov     ecx, eax; dwErrCode
0x1800410f2  call    cs:__imp_SetLastError
0x1800410f8  xor     eax, eax
0x1800410fa  lea     r11, [rsp+78h+var_28]
0x1800410ff  mov     rbx, [r11+30h]
0x180041103  mov     rbp, [r11+40h]
0x180041107  mov     rsp, r11
0x18004110a  pop     r15
0x18004110c  pop     r14
0x18004110e  pop     r12
0x180041110  pop     rdi
0x180041111  pop     rsi
0x180041112  retn
```
