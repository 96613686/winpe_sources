# SampQueryRegistryAccountsByMatchingRid(HKEY__ *,_UNICODE_STRING *,ulong,ulong *,ushort * * *)

- ea: `0x180097b14`
- end: `0x180097ff2`
- name: `?SampQueryRegistryAccountsByMatchingRid@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAKPEAPEAPEAG@Z`
- size: `1246`
- prototype: `__int64 __fastcall(HKEY, struct _UNICODE_STRING *, unsigned int, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180096d88`

## callees

- `0x180027e24`
- `0x18002d720`
- `0x1800372ac`
- `0x180059a74`
- `0x180097b14`
- `0x1800bb788`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180097cad`
- `ntdll!NtEnumerateKey` at `0x180097cad`
- `ntdll!NtOpenKey` at `0x180097ba2`
- `ntdll!NtOpenKey` at `0x180097d15`
- `ntdll!NtOpenKey` at `0x180097ba2`
- `ntdll!NtOpenKey` at `0x180097d15`
- `ntdll!NtQueryValueKey` at `0x180097d63`
- `ntdll!NtQueryValueKey` at `0x180097d63`
- `ntdll!NtClose` at `0x180097e43`
- `ntdll!NtClose` at `0x180097f63`
- `ntdll!NtClose` at `0x180097faa`
- `ntdll!NtClose` at `0x180097e43`
- `ntdll!NtClose` at `0x180097f63`
- `ntdll!NtClose` at `0x180097faa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097c45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097db5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097e05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097c45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097db5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180097e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097de9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097de9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097f9b`

## pseudocode

```c
__int64 __fastcall SampQueryRegistryAccountsByMatchingRid(
        HKEY a1,
        struct _UNICODE_STRING *a2,
        int a3,
        unsigned int *a4,
        unsigned __int16 ***a5)
{
  _WORD *v5; // r14
  int v6; // edi
  _DWORD *v7; // r13
  unsigned int v8; // r15d
  unsigned __int16 **v9; // rsi
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  PUNICODE_STRING v12; // rcx
  int v13; // edx
  __int128 *v14; // r9
  PUNICODE_STRING v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  ULONG v18; // r12d
  unsigned int v19; // edi
  NTSTATUS v20; // eax
  unsigned int v21; // ebx
  HLOCAL v22; // rax
  void *v23; // rdi
  HLOCAL v24; // rax
  void *v25; // rbx
  __int64 v26; // rcx
  __int64 i; // rdi
  HANDLE Handle; // [rsp+38h] [rbp-51h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-49h] BYREF
  __int128 v31; // [rsp+48h] [rbp-41h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+E8h] [rbp+5Fh] BYREF
  int v35; // [rsp+ECh] [rbp+63h]
  ULONG v36; // [rsp+F0h] [rbp+67h]
  int v37; // [rsp+F8h] [rbp+6Fh]
  unsigned int *v38; // [rsp+100h] [rbp+77h]

  v38 = a4;
  v37 = a3;
  v35 = HIDWORD(a1);
  v5 = 0;
  ObjectAttributes.ObjectName = a2;
  ResultLength = 0;
  v6 = (int)a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a5 = 0;
  ObjectAttributes.RootDirectory = SampKey;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v7 = 0;
  KeyHandle = 0;
  v31 = 0;
  Handle = 0;
  v8 = 0;
  ValueName = 0;
  v9 = 0;
  *a4 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v13 = 52;
      LODWORD(v14) = v6;
LABEL_5:
      WPP_SF_ZD(v12[3].Buffer, v13, (unsigned int)WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (_DWORD)v14, v10);
    }
    goto LABEL_51;
  }
  v5 = LocalAlloc(0x40u, 0x54u);
  if ( !v5 )
  {
    v11 = -1073741670;
    v15 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_51;
    v16 = 53;
LABEL_10:
    v17 = 3221225626LL;
LABEL_11:
    WPP_SF_d(v15[3].Buffer, v16, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, v17);
    goto LABEL_51;
  }
  v7 = LocalAlloc(0x40u, 0x38u);
  if ( !v7 )
  {
    v11 = -1073741670;
    v15 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_51;
    v16 = 54;
    goto LABEL_10;
  }
  v18 = 0;
  v19 = 0;
  while ( 1 )
  {
    v36 = v18;
    memset_0(v5, 0, 0x54u);
    v20 = NtEnumerateKey(KeyHandle, v18, KeyBasicInformation, v5, 0x54u, &ResultLength);
    v11 = v20;
    if ( v20 == -2147483622 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 55, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, 2147483674LL);
      *v38 = v8;
      *a5 = v9;
      v9 = 0;
      v11 = 0;
      goto LABEL_51;
    }
    if ( v20 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
        goto LABEL_51;
      v16 = 56;
LABEL_46:
      v17 = (unsigned int)v20;
      goto LABEL_11;
    }
    LOWORD(v31) = v5[6];
    WORD1(v31) = v5[6];
    ObjectAttributes.Length = 48;
    *((_QWORD *)&v31 + 1) = v5 + 8;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v31;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = NtOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    v11 = v10;
    if ( v10 < 0 )
      break;
    ValueName = 0;
    *(_OWORD *)v7 = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v20 = NtQueryValueKey(Handle, &ValueName, KeyValueBasicInformation, v7, 0x38u, &ResultLength);
    v11 = v20;
    if ( v20 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
        goto LABEL_51;
      v16 = 58;
      goto LABEL_46;
    }
    if ( v7[1] == v37 )
    {
      if ( v8 == v19 )
      {
        v21 = v19 + 20;
        if ( v19 + 20 < v19 || 8 * (unsigned __int64)v21 > 0xFFFFFFFF )
        {
          v11 = -1073741675;
          goto LABEL_51;
        }
        v22 = LocalAlloc(0x40u, 8 * v21);
        v23 = v22;
        if ( !v22 )
        {
          v11 = -1073741670;
          v15 = WPP_GLOBAL_Control;
          if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
            && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            v16 = 59;
            goto LABEL_10;
          }
          goto LABEL_51;
        }
        memset_0(v22, 0, 8 * v21);
        memcpy_0(v23, v9, 8LL * v8);
        LocalFree(v9);
        v18 = v36;
        v9 = (unsigned __int16 **)v23;
        v19 = v21;
      }
      v24 = LocalAlloc(0x40u, *((unsigned int *)v5 + 3) + 2LL);
      v25 = v24;
      if ( !v24 )
      {
        v11 = -1073741670;
        v15 = WPP_GLOBAL_Control;
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          v16 = 60;
          goto LABEL_10;
        }
        goto LABEL_51;
      }
      memset_0(v24, 0, *((unsigned int *)v5 + 3) + 2LL);
      memcpy_0(v25, v5 + 8, *((unsigned int *)v5 + 3));
      v26 = v8++;
      v9[v26] = (unsigned __int16 *)v25;
    }
    NtClose(Handle);
    ++v18;
    Handle = 0;
  }
  v12 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    v13 = 57;
    v14 = &v31;
    goto LABEL_5;
  }
LABEL_51:
  if ( Handle )
    NtClose(Handle);
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
      LocalFree(v9[i]);
    LocalFree(v9);
  }
  LocalFree(v7);
  LocalFree(v5);
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 61, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, v11, v11);
  return v11;
}

```

## disassembly

```asm
0x180097b14  mov     rax, rsp
0x180097b17  mov     [rax+20h], r9
0x180097b1b  mov     [rax+18h], r8d
0x180097b1f  mov     [rax+8], rcx
0x180097b23  push    rbp
0x180097b24  push    rbx
0x180097b25  push    rsi
0x180097b26  push    rdi
0x180097b27  push    r12
0x180097b29  push    r13
0x180097b2b  push    r14
0x180097b2d  push    r15
0x180097b2f  lea     rbp, [rax-57h]
0x180097b33  sub     rsp, 98h
0x180097b3a  mov     rax, [rbp+4Fh+arg_20]
0x180097b3e  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180097b42  xor     r14d, r14d
0x180097b45  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rdx
0x180097b49  xorps   xmm0, xmm0
0x180097b4c  mov     [rbp+4Fh+ResultLength], r14d
0x180097b50  mov     rdi, rdx
0x180097b53  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180097b5b  mov     [rax], r14
0x180097b5e  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x180097b62  mov     rax, cs:SampKey
0x180097b69  lea     r12d, [r14+40h]
0x180097b6d  xorps   xmm1, xmm1
0x180097b70  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x180097b74  mov     edx, 20019h; DesiredAccess
0x180097b79  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180097b81  mov     r13d, r14d
0x180097b84  mov     [rbp+4Fh+KeyHandle], r14
0x180097b88  movups  [rbp+4Fh+var_90], xmm0
0x180097b8c  mov     [rbp+4Fh+Handle], r14
0x180097b90  mov     r15d, r14d
0x180097b93  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm1
0x180097b97  mov     esi, r14d
0x180097b9a  mov     [r9], r14d
0x180097b9d  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180097ba2  call    cs:__imp_NtOpenKey
0x180097ba8  mov     ebx, eax
0x180097baa  test    eax, eax
0x180097bac  jns     short loc_180097BE9
0x180097bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180097bb5  test    byte ptr [rcx+44h], 1
0x180097bb9  jz      loc_180097F5A
0x180097bbf  cmp     byte ptr [rcx+41h], 2
0x180097bc3  jb      loc_180097F5A
0x180097bc9  lea     edx, [r14+34h]
0x180097bcd  mov     r9, rdi
0x180097bd0  mov     rcx, [rcx+38h]
0x180097bd4  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180097bdb  mov     [rsp+0D0h+Length], eax
0x180097bdf  call    WPP_SF_ZD
0x180097be4  jmp     loc_180097F5A
0x180097be9  mov     edx, 54h ; 'T'; uBytes
0x180097bee  mov     ecx, r12d; uFlags
0x180097bf1  call    cs:__imp_LocalAlloc
0x180097bf7  mov     r14, rax
0x180097bfa  test    rax, rax
0x180097bfd  jnz     short loc_180097C3D
0x180097bff  mov     ebx, 0C000009Ah
0x180097c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c0b  test    byte ptr [rcx+44h], 1
0x180097c0f  jz      loc_180097F5A
0x180097c15  cmp     byte ptr [rcx+41h], 2
0x180097c19  jb      loc_180097F5A
0x180097c1f  lea     edx, [rax+35h]
0x180097c22  mov     r9d, 0C000009Ah
0x180097c28  mov     rcx, [rcx+38h]
0x180097c2c  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180097c33  call    WPP_SF_d
0x180097c38  jmp     loc_180097F5A
0x180097c3d  mov     edx, 38h ; '8'; uBytes
0x180097c42  mov     ecx, r12d; uFlags
0x180097c45  call    cs:__imp_LocalAlloc
0x180097c4b  mov     r13, rax
0x180097c4e  test    rax, rax
0x180097c51  jnz     short loc_180097C78
0x180097c53  mov     ebx, 0C000009Ah
0x180097c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c5f  test    byte ptr [rcx+44h], 1
0x180097c63  jz      loc_180097F5A
0x180097c69  cmp     byte ptr [rcx+41h], 2
0x180097c6d  jb      loc_180097F5A
0x180097c73  lea     edx, [rax+36h]
0x180097c76  jmp     short loc_180097C22
0x180097c78  xor     r12d, r12d
0x180097c7b  xor     edi, edi
0x180097c7d  xor     edx, edx; Val
0x180097c7f  mov     [rbp+4Fh+arg_8], r12d
0x180097c83  mov     rcx, r14; void *
0x180097c86  lea     r8d, [rdx+54h]; Size
0x180097c8a  call    memset_0
0x180097c8f  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x180097c93  lea     rax, [rbp+4Fh+ResultLength]
0x180097c97  mov     [rsp+28h], rax; ResultLength
0x180097c9c  mov     r9, r14; KeyInformation
0x180097c9f  xor     r8d, r8d; KeyInformationClass
0x180097ca2  mov     [rsp+0D0h+Length], 54h ; 'T'; Length
0x180097caa  mov     edx, r12d; Index
0x180097cad  call    cs:__imp_NtEnumerateKey
0x180097cb3  mov     ebx, eax
0x180097cb5  cmp     eax, 8000001Ah
0x180097cba  jz      loc_180097F1A
0x180097cc0  test    eax, eax
0x180097cc2  js      loc_180097EFA
0x180097cc8  movzx   eax, word ptr [r14+0Ch]
0x180097ccd  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180097cd1  mov     word ptr [rbp+4Fh+var_90], ax
0x180097cd5  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180097cd9  movzx   eax, word ptr [r14+0Ch]
0x180097cde  xorps   xmm0, xmm0
0x180097ce1  mov     word ptr [rbp+4Fh+var_90+2], ax
0x180097ce5  mov     edx, 20019h; DesiredAccess
0x180097cea  lea     rax, [r14+10h]
0x180097cee  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180097cf5  mov     qword ptr [rbp+4Fh+var_90+8], rax
0x180097cf9  mov     rax, [rbp+4Fh+KeyHandle]
0x180097cfd  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x180097d01  lea     rax, [rbp+4Fh+var_90]
0x180097d05  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180097d09  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180097d10  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180097d15  call    cs:__imp_NtOpenKey
0x180097d1b  mov     ebx, eax
0x180097d1d  test    eax, eax
0x180097d1f  js      loc_180097ED9
0x180097d25  xorps   xmm1, xmm1
0x180097d28  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x180097d2c  xor     eax, eax
0x180097d2e  xorps   xmm0, xmm0
0x180097d31  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x180097d35  mov     r9, r13; KeyValueInformation
0x180097d38  xor     r8d, r8d; KeyValueInformationClass
0x180097d3b  movups  xmmword ptr [r13+0], xmm1
0x180097d40  movups  xmmword ptr [r13+10h], xmm1
0x180097d45  movups  xmmword ptr [r13+20h], xmm1
0x180097d4a  mov     [r13+30h], rax
0x180097d4e  lea     rax, [rbp+4Fh+ResultLength]
0x180097d52  mov     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180097d56  mov     [rsp+28h], rax; ResultLength
0x180097d5b  mov     [rsp+0D0h+Length], 38h ; '8'; Length
0x180097d63  call    cs:__imp_NtQueryValueKey
0x180097d69  mov     ebx, eax
0x180097d6b  test    eax, eax
0x180097d6d  js      loc_180097EB7
0x180097d73  mov     eax, [rbp+4Fh+arg_10]
0x180097d76  cmp     [r13+4], eax
0x180097d7a  jnz     loc_180097E3F
0x180097d80  cmp     r15d, edi
0x180097d83  jnz     short loc_180097DF8
0x180097d85  lea     ebx, [rdi+14h]
0x180097d88  cmp     ebx, edi
0x180097d8a  jb      loc_180097E83
0x180097d90  mov     eax, ebx
0x180097d92  mov     ecx, 0FFFFFFFFh
0x180097d97  shl     rax, 3
0x180097d9b  cmp     rax, rcx
0x180097d9e  ja      loc_180097E83
0x180097da4  lea     eax, ds:0[rbx*8]
0x180097dab  mov     ecx, 40h ; '@'; uFlags
0x180097db0  mov     edx, eax; uBytes
0x180097db2  mov     r12d, eax
0x180097db5  call    cs:__imp_LocalAlloc
0x180097dbb  mov     rdi, rax
0x180097dbe  test    rax, rax
0x180097dc1  jz      loc_180097E59
0x180097dc7  mov     r8d, r12d; Size
0x180097dca  xor     edx, edx; Val
0x180097dcc  mov     rcx, rax; void *
0x180097dcf  call    memset_0
0x180097dd4  mov     r8d, r15d
0x180097dd7  mov     rdx, rsi; Src
0x180097dda  shl     r8, 3; Size
0x180097dde  mov     rcx, rdi; void *
0x180097de1  call    memcpy_0
0x180097de6  mov     rcx, rsi; hMem
0x180097de9  call    cs:__imp_LocalFree
0x180097def  mov     r12d, [rbp+4Fh+arg_8]
0x180097df3  mov     rsi, rdi
0x180097df6  mov     edi, ebx
0x180097df8  mov     edx, [r14+0Ch]
0x180097dfc  mov     ecx, 40h ; '@'; uFlags
0x180097e01  add     rdx, 2; uBytes
0x180097e05  call    cs:__imp_LocalAlloc
0x180097e0b  mov     rbx, rax
0x180097e0e  test    rax, rax
0x180097e11  jz      short loc_180097E8D
0x180097e13  mov     r8d, [r14+0Ch]
0x180097e17  xor     edx, edx; Val
0x180097e19  add     r8, 2; Size
0x180097e1d  mov     rcx, rax; void *
0x180097e20  call    memset_0
0x180097e25  mov     r8d, [r14+0Ch]; Size
0x180097e29  lea     rdx, [r14+10h]; Src
0x180097e2d  mov     rcx, rbx; void *
0x180097e30  call    memcpy_0
0x180097e35  mov     ecx, r15d
0x180097e38  inc     r15d
0x180097e3b  mov     [rsi+rcx*8], rbx
0x180097e3f  mov     rcx, [rbp+4Fh+Handle]; Handle
0x180097e43  call    cs:__imp_NtClose
0x180097e49  inc     r12d
0x180097e4c  mov     [rbp+4Fh+Handle], 0
0x180097e54  jmp     loc_180097C7D
0x180097e59  mov     ebx, 0C000009Ah
0x180097e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e65  test    byte ptr [rcx+44h], 1
0x180097e69  jz      loc_180097F5A
0x180097e6f  cmp     byte ptr [rcx+41h], 2
0x180097e73  jb      loc_180097F5A
0x180097e79  mov     edx, 3Bh ; ';'
0x180097e7e  jmp     loc_180097C22
0x180097e83  mov     ebx, 0C0000095h
0x180097e88  jmp     loc_180097F5A
0x180097e8d  mov     ebx, 0C000009Ah
0x180097e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e99  test    byte ptr [rcx+44h], 1
0x180097e9d  jz      loc_180097F5A
0x180097ea3  cmp     byte ptr [rcx+41h], 2
0x180097ea7  jb      loc_180097F5A
0x180097ead  mov     edx, 3Ch ; '<'
0x180097eb2  jmp     loc_180097C22
0x180097eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180097ebe  test    byte ptr [rcx+44h], 1
0x180097ec2  jz      loc_180097F5A
0x180097ec8  cmp     byte ptr [rcx+41h], 2
0x180097ecc  jb      loc_180097F5A
0x180097ed2  mov     edx, 3Ah ; ':'
0x180097ed7  jmp     short loc_180097F12
0x180097ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180097ee0  test    byte ptr [rcx+44h], 1
0x180097ee4  jz      short loc_180097F5A
0x180097ee6  cmp     byte ptr [rcx+41h], 2
0x180097eea  jb      short loc_180097F5A
0x180097eec  mov     edx, 39h ; '9'
0x180097ef1  lea     r9, [rbp+4Fh+var_90]
0x180097ef5  jmp     loc_180097BD0
0x180097efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180097f01  test    byte ptr [rcx+44h], 1
0x180097f05  jz      short loc_180097F5A
0x180097f07  cmp     byte ptr [rcx+41h], 2
0x180097f0b  jb      short loc_180097F5A
0x180097f0d  mov     edx, 38h ; '8'
0x180097f12  mov     r9d, eax
0x180097f15  jmp     loc_180097C28
0x180097f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180097f21  test    byte ptr [rcx+44h], 1
0x180097f25  jz      short loc_180097F48
0x180097f27  cmp     byte ptr [rcx+41h], 4
0x180097f2b  jb      short loc_180097F48
0x180097f2d  mov     rcx, [rcx+38h]
0x180097f31  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180097f38  mov     edx, 37h ; '7'
0x180097f3d  mov     r9d, 8000001Ah
0x180097f43  call    WPP_SF_d
0x180097f48  mov     rax, [rbp+4Fh+arg_18]
0x180097f4c  mov     [rax], r15d
0x180097f4f  mov     rax, [rbp+4Fh+arg_20]
0x180097f53  mov     [rax], rsi
0x180097f56  xor     esi, esi
0x180097f58  xor     ebx, ebx
0x180097f5a  mov     rcx, [rbp+4Fh+Handle]; Handle
0x180097f5e  test    rcx, rcx
0x180097f61  jz      short loc_180097F69
0x180097f63  call    cs:__imp_NtClose
0x180097f69  test    rsi, rsi
0x180097f6c  jz      short loc_180097F8F
0x180097f6e  xor     edi, edi
0x180097f70  test    r15d, r15d
0x180097f73  jz      short loc_180097F86
0x180097f75  mov     rcx, [rsi+rdi*8]; hMem
0x180097f79  call    cs:__imp_LocalFree
0x180097f7f  inc     edi
0x180097f81  cmp     edi, r15d
0x180097f84  jb      short loc_180097F75
0x180097f86  mov     rcx, rsi; hMem
0x180097f89  call    cs:__imp_LocalFree
0x180097f8f  mov     rcx, r13; hMem
0x180097f92  call    cs:__imp_LocalFree
0x180097f98  mov     rcx, r14; hMem
0x180097f9b  call    cs:__imp_LocalFree
0x180097fa1  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x180097fa5  test    rcx, rcx
0x180097fa8  jz      short loc_180097FB0
0x180097faa  call    cs:__imp_NtClose
0x180097fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180097fb7  test    dword ptr [rcx+44h], 20000h
0x180097fbe  jz      short loc_180097FDC
0x180097fc0  mov     rcx, [rcx+38h]
0x180097fc4  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180097fcb  mov     edx, 3Dh ; '='
0x180097fd0  mov     [rsp+0D0h+Length], ebx
0x180097fd4  mov     r9d, ebx
0x180097fd7  call    WPP_SF_Dd
0x180097fdc  mov     eax, ebx
0x180097fde  add     rsp, 98h
0x180097fe5  pop     r15
0x180097fe7  pop     r14
  ... truncated ...
```
