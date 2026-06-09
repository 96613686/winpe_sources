# sub_18006ECAC

- ea: `0x18006ecac`
- end: `0x18006ef35`
- name: `sub_18006ECAC`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006e72c`
- `0x18006e824`

## callees

- `0x180001544`
- `0x1800016c0`
- `0x180043550`
- `0x180054c80`
- `0x18006ecac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ee17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ee17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ef0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ef0e`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006ed8f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006ed8f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006eea4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006eea4`

## pseudocode

```c
__int64 __fastcall sub_18006ECAC(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  HANDLE FileW; // rax
  __int64 v15; // rcx
  void *v16; // r14
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  PACL pDacl; // [rsp+40h] [rbp-9h] BYREF
  PSID psidGroup; // [rsp+48h] [rbp-1h] BYREF
  PSID ppsidOwner; // [rsp+50h] [rbp+7h] BYREF
  const WCHAR *v30; // [rsp+58h] [rbp+Fh] BYREF
  const WCHAR *v31; // [rsp+60h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v33; // [rsp+78h] [rbp+2Fh]
  __int64 v34; // [rsp+88h] [rbp+3Fh]
  int v35; // [rsp+C8h] [rbp+7Fh] BYREF

  v34 = 0;
  ppsidOwner = 0;
  *(_OWORD *)ppSecurityDescriptor = 0;
  psidGroup = 0;
  v33 = 0;
  pDacl = 0;
  if ( (unsigned __int8)sub_180043550(a1, a3) )
  {
    if ( GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 7u, &ppsidOwner, &psidGroup, &pDacl, 0, ppSecurityDescriptor) )
    {
      v6 = sub_180054C80(v10);
      if ( (unsigned int)dword_1800C0358 > 4
        && (unsigned __int8)sub_180001544((unsigned int)dword_1800C0358, 0x400000000001LL) )
      {
        v31 = a3;
        v30 = a2;
        v35 = v6;
        sub_1800016C0(v11, (unsigned int)byte_1800B17B1, v12, v13, (__int64)&v35, (__int64)&v30, (__int64)&v31);
      }
    }
    else
    {
      FileW = CreateFileW(a3, 0xE0000u, 0, 0, 3u, 0x2200000u, 0);
      v16 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v6 = sub_180054C80(v15);
        if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)sub_180001544(v17, 0x400000000001LL) )
        {
          v31 = a3;
          v30 = a2;
          v35 = v6;
          sub_1800016C0(v18, (unsigned int)word_1800B19F2, v19, v20, (__int64)&v35, (__int64)&v30, (__int64)&v31);
        }
      }
      else
      {
        v6 = 0;
        if ( SetSecurityInfo(FileW, SE_FILE_OBJECT, 7u, ppsidOwner, psidGroup, pDacl, 0) )
        {
          v6 = sub_180054C80(v21);
          if ( (unsigned int)dword_1800C0358 > 4 )
          {
            if ( (unsigned __int8)sub_180001544(v22, 0x400000000001LL) )
            {
              v31 = a3;
              v30 = a2;
              v35 = v6;
              sub_1800016C0(v23, (unsigned int)word_1800B170A, v24, v25, (__int64)&v35, (__int64)&v30, (__int64)&v31);
            }
          }
        }
        CloseHandle(v16);
      }
    }
  }
  else
  {
    v6 = -2147024891;
    if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)sub_180001544(v5, 0x400000000001LL) )
    {
      v30 = a3;
      v31 = a2;
      v35 = -2147024891;
      sub_1800016C0(v7, (unsigned int)&unk_1800B1A70, v8, v9, (__int64)&v35, (__int64)&v31, (__int64)&v30);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18006ecac  mov     [rsp-8+arg_0], rbx
0x18006ecb1  mov     [rsp-8+arg_8], rsi
0x18006ecb6  push    rbp
0x18006ecb7  push    rdi
0x18006ecb8  push    r14
0x18006ecba  lea     rbp, [rsp-47h]
0x18006ecbf  sub     rsp, 90h
0x18006ecc6  xor     eax, eax
0x18006ecc8  xorps   xmm0, xmm0
0x18006eccb  mov     rsi, rdx
0x18006ecce  mov     [rbp+57h+var_18], rax
0x18006ecd2  mov     rdx, r8
0x18006ecd5  mov     [rbp+57h+ppsidOwner], rax
0x18006ecd9  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18006ecdd  mov     [rbp+57h+psidGroup], rax
0x18006ece1  mov     rdi, r8
0x18006ece4  movups  [rbp+57h+var_28], xmm0
0x18006ece8  mov     [rbp+57h+pDacl], rax
0x18006ecec  call    sub_180043550
0x18006ecf1  test    al, al
0x18006ecf3  jnz     short loc_18006ED5B
0x18006ecf5  mov     eax, cs:dword_1800C0358
0x18006ecfb  mov     ebx, 80070005h
0x18006ed00  cmp     eax, 4
0x18006ed03  jbe     loc_18006EF1A
0x18006ed09  mov     rdx, 400000000001h
0x18006ed13  call    sub_180001544
0x18006ed18  test    al, al
0x18006ed1a  jz      loc_18006EF1A
0x18006ed20  lea     rax, [rbp+57h+var_48]
0x18006ed24  mov     [rbp+57h+var_48], rdi
0x18006ed28  mov     [rsp+0A0h+ppSacl], rax
0x18006ed2d  lea     rdx, unk_1800B1A70
0x18006ed34  lea     rax, [rbp+57h+var_40]
0x18006ed38  mov     [rbp+57h+var_40], rsi
0x18006ed3c  mov     [rbp+57h+arg_18], 80070005h
0x18006ed43  mov     [rsp+0A0h+ppDacl], rax
0x18006ed48  lea     rax, [rbp+57h+arg_18]
0x18006ed4c  mov     [rsp+0A0h+ppsidGroup], rax
0x18006ed51  call    sub_1800016C0
0x18006ed56  jmp     loc_18006EF1A
0x18006ed5b  lea     rax, [rbp+57h+var_38]
0x18006ed5f  mov     edx, 1; ObjectType
0x18006ed64  mov     [rsp+0A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18006ed69  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18006ed6d  lea     rax, [rbp+57h+pDacl]
0x18006ed71  mov     [rsp+0A0h+ppSacl], 0; ppSacl
0x18006ed7a  mov     [rsp+0A0h+ppDacl], rax; ppDacl
0x18006ed7f  mov     rcx, rsi; pObjectName
0x18006ed82  lea     rax, [rbp+57h+psidGroup]
0x18006ed86  lea     r8d, [rdx+6]; SecurityInfo
0x18006ed8a  mov     [rsp+0A0h+ppsidGroup], rax; ppsidGroup
0x18006ed8f  call    cs:GetNamedSecurityInfoW
0x18006ed96  nop     dword ptr [rax+rax+00h]
0x18006ed9b  test    eax, eax
0x18006ed9d  jz      short loc_18006EDF0
0x18006ed9f  call    sub_180054C80
0x18006eda4  mov     ecx, cs:dword_1800C0358
0x18006edaa  mov     ebx, eax
0x18006edac  cmp     ecx, 4
0x18006edaf  jbe     loc_18006EF1A
0x18006edb5  mov     rdx, 400000000001h
0x18006edbf  call    sub_180001544
0x18006edc4  test    al, al
0x18006edc6  jz      loc_18006EF1A
0x18006edcc  lea     rax, [rbp+57h+var_40]
0x18006edd0  mov     [rbp+57h+var_40], rdi
0x18006edd4  mov     [rsp+0A0h+ppSacl], rax
0x18006edd9  lea     rdx, byte_1800B17B1
0x18006ede0  lea     rax, [rbp+57h+var_48]
0x18006ede4  mov     [rbp+57h+var_48], rsi
0x18006ede8  mov     [rbp+57h+arg_18], ebx
0x18006edeb  jmp     loc_18006ED43
0x18006edf0  mov     [rsp+0A0h+ppSacl], 0; hTemplateFile
0x18006edf9  xor     r9d, r9d; lpSecurityAttributes
0x18006edfc  mov     dword ptr [rsp+0A0h+ppDacl], 2200000h; dwFlagsAndAttributes
0x18006ee04  xor     r8d, r8d; dwShareMode
0x18006ee07  mov     edx, 0E0000h; dwDesiredAccess
0x18006ee0c  mov     dword ptr [rsp+0A0h+ppsidGroup], 3; dwCreationDisposition
0x18006ee14  mov     rcx, rdi; lpFileName
0x18006ee17  call    cs:CreateFileW
0x18006ee1e  nop     dword ptr [rax+rax+00h]
0x18006ee23  mov     r14, rax
0x18006ee26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006ee2a  jnz     short loc_18006EE7D
0x18006ee2c  call    sub_180054C80
0x18006ee31  mov     ebx, eax
0x18006ee33  mov     eax, cs:dword_1800C0358
0x18006ee39  cmp     eax, 4
0x18006ee3c  jbe     loc_18006EF1A
0x18006ee42  mov     rdx, 400000000001h
0x18006ee4c  call    sub_180001544
0x18006ee51  test    al, al
0x18006ee53  jz      loc_18006EF1A
0x18006ee59  lea     rax, [rbp+57h+var_40]
0x18006ee5d  mov     [rbp+57h+var_40], rdi
0x18006ee61  mov     [rsp+0A0h+ppSacl], rax
0x18006ee66  lea     rdx, word_1800B19F2
0x18006ee6d  lea     rax, [rbp+57h+var_48]
0x18006ee71  mov     [rbp+57h+var_48], rsi
0x18006ee75  mov     [rbp+57h+arg_18], ebx
0x18006ee78  jmp     loc_18006ED43
0x18006ee7d  mov     rax, [rbp+57h+pDacl]
0x18006ee81  xor     ebx, ebx
0x18006ee83  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x18006ee87  mov     rcx, r14; handle
0x18006ee8a  mov     [rsp+0A0h+ppSacl], rbx; pSacl
0x18006ee8f  mov     [rsp+0A0h+ppDacl], rax; pDacl
0x18006ee94  mov     rax, [rbp+57h+psidGroup]
0x18006ee98  lea     edx, [rbx+1]; ObjectType
0x18006ee9b  lea     r8d, [rbx+7]; SecurityInfo
0x18006ee9f  mov     [rsp+0A0h+ppsidGroup], rax; psidGroup
0x18006eea4  call    cs:SetSecurityInfo
0x18006eeab  nop     dword ptr [rax+rax+00h]
0x18006eeb0  test    eax, eax
0x18006eeb2  jz      short loc_18006EF0B
0x18006eeb4  call    sub_180054C80
0x18006eeb9  mov     ebx, eax
0x18006eebb  mov     eax, cs:dword_1800C0358
0x18006eec1  cmp     eax, 4
0x18006eec4  jbe     short loc_18006EF0B
0x18006eec6  mov     rdx, 400000000001h
0x18006eed0  call    sub_180001544
0x18006eed5  test    al, al
0x18006eed7  jz      short loc_18006EF0B
0x18006eed9  lea     rax, [rbp+57h+var_40]
0x18006eedd  mov     [rbp+57h+var_40], rdi
0x18006eee1  mov     [rsp+0A0h+ppSacl], rax
0x18006eee6  lea     rdx, word_1800B170A
0x18006eeed  lea     rax, [rbp+57h+var_48]
0x18006eef1  mov     [rbp+57h+var_48], rsi
0x18006eef5  mov     [rsp+0A0h+ppDacl], rax
0x18006eefa  lea     rax, [rbp+57h+arg_18]
0x18006eefe  mov     [rsp+0A0h+ppsidGroup], rax
0x18006ef03  mov     [rbp+57h+arg_18], ebx
0x18006ef06  call    sub_1800016C0
0x18006ef0b  mov     rcx, r14; hObject
0x18006ef0e  call    cs:CloseHandle
0x18006ef15  nop     dword ptr [rax+rax+00h]
0x18006ef1a  lea     r11, [rsp+0A0h+var_10]
0x18006ef22  mov     eax, ebx
0x18006ef24  mov     rbx, [r11+20h]
0x18006ef28  mov     rsi, [r11+28h]
0x18006ef2c  mov     rsp, r11
0x18006ef2f  pop     r14
0x18006ef31  pop     rdi
0x18006ef32  pop     rbp
0x18006ef33  retn
```
