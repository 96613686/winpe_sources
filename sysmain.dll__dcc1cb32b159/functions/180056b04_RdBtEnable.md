# RdBtEnable

- ea: `0x180056b04`
- end: `0x180056dcc`
- name: `RdBtEnable`
- size: `712`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800564d0`
- `0x180096e14`

## callees

- `0x180056b04`
- `0x180056e20`
- `0x180062be0`
- `0x180068428`
- `0x18006fb9c`
- `0x1800b3ba8`
- `0x1800b644e`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180056c0a`
- `ntdll!NtCreateKey` at `0x180056c0a`
- `ntdll!RtlNtStatusToDosError` at `0x180056c16`
- `ntdll!RtlNtStatusToDosError` at `0x180056c16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056d8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056d8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056d01`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056d01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d5c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d6e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d38`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d5c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180056d6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056cc5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056cc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056da5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180056da5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056c77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056c77`

## string_xrefs

- `0x180056b80`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x180056c90`: `ReadyBootVolumeUniqueId`
- `0x180056ce7`: `ReadyBootVolumeUniqueId`
- `0x180056d43`: `ReadyBootVolumeUniqueId`

## pseudocode

```c
__int64 __fastcall RdBtEnable(const BYTE **a1, int a2)
{
  void *v4; // rdi
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  __int64 v7; // rcx
  __int16 v8; // cx
  int v9; // eax
  ULONG v10; // ebx
  const BYTE *v11; // rsi
  DWORD v12; // r14d
  _WORD *v13; // rax
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-B4h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  pdwType = 0;
  pcbData = 0;
  KeyHandle = 0;
  v4 = 0;
  v18 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a2 )
  {
    v5 = 0;
  }
  else
  {
    RdBtLoggerControl(2);
    v5 = 1;
  }
  RdBtLoggerControl(v5);
  v18 = 0;
  v6 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  v7 = 0x7FFF;
  while ( *v6 )
  {
    ++v6;
    if ( !--v7 )
      goto LABEL_9;
  }
  v8 = 2 * v7;
  *((_QWORD *)&v18 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  LOWORD(v18) = -2 - v8;
  WORD1(v18) = -v8;
LABEL_9:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtCreateKey(&KeyHandle, 3u, &ObjectAttributes, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    v10 = RtlNtStatusToDosError(v9);
    goto LABEL_24;
  }
  if ( !a2 )
  {
    RegDeleteValueW((HKEY)KeyHandle, L"BootPlan");
    RegDeleteValueW((HKEY)KeyHandle, L"ReadyBootVolumeUniqueId");
    RegDeleteValueW((HKEY)KeyHandle, L"EffectivePends");
    RegDeleteValueW((HKEY)KeyHandle, L"BootCountwithPends");
    RdBtLogSystemVolumeUniqueId(0, 0);
LABEL_23:
    v10 = 0;
    goto LABEL_24;
  }
  ResetReadyBootTrainingCountIfNecessary();
  v10 = PfsSystemRootPathGet(pszDest);
  if ( !v10 )
  {
    v10 = RdBtVolumeInfoQuery(pszDest, a1);
    if ( !v10 )
    {
      v11 = *a1;
      v12 = *(unsigned __int16 *)v11 + 4;
      v13 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v12);
      v4 = v13;
      if ( !v13 )
      {
        v10 = 8;
        goto LABEL_24;
      }
      *v13 = *(_WORD *)v11;
      pcbData = v12;
      if ( RegGetValueW((HKEY)KeyHandle, 0, L"ReadyBootVolumeUniqueId", 0xFFFFu, &pdwType, v13, &pcbData) )
        memset_0(v4, 0, v12);
      v10 = RegSetValueExW((HKEY)KeyHandle, L"ReadyBootVolumeUniqueId", 0, 3u, v11 + 2, *(unsigned __int16 *)v11);
      if ( memcmp_0(v11, v4, *(unsigned __int16 *)v11) )
        RdBtLogSystemVolumeUniqueId(v11, v10);
      if ( !v10 )
        goto LABEL_23;
    }
  }
LABEL_24:
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  if ( v4 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v4);
  return v10;
}

```

## disassembly

```asm
0x180056b04  push    rbp
0x180056b06  push    rbx
0x180056b07  push    rsi
0x180056b08  push    rdi
0x180056b09  push    r14
0x180056b0b  push    r15
0x180056b0d  lea     rbp, [rsp-1B8h]
0x180056b15  sub     rsp, 2B8h
0x180056b1c  mov     rax, cs:__security_cookie
0x180056b23  xor     rax, rsp
0x180056b26  mov     [rbp+1E0h+var_40], rax
0x180056b2d  xor     r15d, r15d
0x180056b30  xorps   xmm0, xmm0
0x180056b33  xor     eax, eax
0x180056b35  mov     [rsp+2E0h+pdwType], r15d
0x180056b3a  mov     [rsp+2E0h+pcbData], r15d
0x180056b3f  mov     ebx, edx
0x180056b41  mov     [rsp+2E0h+KeyHandle], r15
0x180056b46  mov     rsi, rcx
0x180056b49  mov     edi, r15d
0x180056b4c  lea     r14d, [rax+2]
0x180056b50  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180056b55  movups  [rsp+2E0h+var_290], xmm0
0x180056b5a  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180056b5f  movups  xmmword ptr [rsp+2E0h+ObjectAttributes+1Ch], xmm0
0x180056b64  test    edx, edx
0x180056b66  jnz     short loc_180056B75
0x180056b68  mov     ecx, r14d
0x180056b6b  call    RdBtLoggerControl
0x180056b70  lea     ecx, [rbx+1]
0x180056b73  jmp     short loc_180056B78
0x180056b75  mov     ecx, r15d
0x180056b78  call    RdBtLoggerControl
0x180056b7d  xorps   xmm0, xmm0
0x180056b80  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180056b87  movups  [rsp+2E0h+var_290], xmm0
0x180056b8c  mov     rax, rdx
0x180056b8f  mov     ecx, 7FFFh
0x180056b94  cmp     [rax], r15w
0x180056b98  jz      short loc_180056BA5
0x180056b9a  add     rax, r14
0x180056b9d  sub     rcx, 1
0x180056ba1  jnz     short loc_180056B94
0x180056ba3  jmp     short loc_180056BC3
0x180056ba5  add     cx, cx
0x180056ba8  mov     qword ptr [rsp+2E0h+var_290+8], rdx
0x180056bad  mov     eax, 0FFFEh
0x180056bb2  sub     ax, cx
0x180056bb5  mov     word ptr [rsp+2E0h+var_290], ax
0x180056bba  add     ax, r14w
0x180056bbe  mov     word ptr [rsp+2E0h+var_290+2], ax
0x180056bc3  xor     r9d, r9d; TitleIndex
0x180056bc6  mov     [rsp+2E0h+Disposition], r15; Disposition
0x180056bcb  lea     rax, [rsp+2E0h+var_290]
0x180056bd0  mov     [rsp+2E0h+CreateOptions], r15d; CreateOptions
0x180056bd5  xorps   xmm0, xmm0
0x180056bd8  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180056be0  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180056be5  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r15
0x180056bea  lea     edx, [r9+3]; DesiredAccess
0x180056bee  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180056bf6  lea     rcx, [rsp+2E0h+KeyHandle]; KeyHandle
0x180056bfb  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180056c00  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180056c05  mov     [rsp+2E0h+Class], r15; Class
0x180056c0a  call    cs:__imp_NtCreateKey
0x180056c10  test    eax, eax
0x180056c12  jns     short loc_180056C23
0x180056c14  mov     ecx, eax; Status
0x180056c16  call    cs:__imp_RtlNtStatusToDosError
0x180056c1c  mov     ebx, eax
0x180056c1e  jmp     loc_180056D80
0x180056c23  test    ebx, ebx
0x180056c25  jz      loc_180056D2C
0x180056c2b  call    ResetReadyBootTrainingCountIfNecessary
0x180056c30  lea     rcx, [rbp+1E0h+pszDest]; pszDest
0x180056c34  call    PfsSystemRootPathGet
0x180056c39  mov     ebx, eax
0x180056c3b  test    eax, eax
0x180056c3d  jnz     loc_180056D80
0x180056c43  mov     rdx, rsi
0x180056c46  lea     rcx, [rbp+1E0h+pszDest]
0x180056c4a  call    RdBtVolumeInfoQuery
0x180056c4f  mov     ebx, eax
0x180056c51  test    eax, eax
0x180056c53  jnz     loc_180056D80
0x180056c59  mov     rsi, [rsi]
0x180056c5c  xor     edx, edx; dwFlags
0x180056c5e  mov     rcx, cs:PfSvcGlobals
0x180056c65  movzx   r14d, word ptr [rsi]
0x180056c69  mov     rcx, [rcx+58h]; hHeap
0x180056c6d  add     r14d, 4
0x180056c71  mov     r8d, r14d; dwBytes
0x180056c74  mov     ebx, r14d
0x180056c77  call    cs:__imp_HeapAlloc
0x180056c7d  mov     rdi, rax
0x180056c80  test    rax, rax
0x180056c83  jnz     short loc_180056C8D
0x180056c85  lea     ebx, [rax+8]
0x180056c88  jmp     loc_180056D80
0x180056c8d  movzx   eax, word ptr [rsi]
0x180056c90  lea     r8, Value; "ReadyBootVolumeUniqueId"
0x180056c97  mov     [rdi], ax
0x180056c9a  mov     r9d, 0FFFFh; dwFlags
0x180056ca0  mov     rcx, [rsp+2E0h+KeyHandle]; hkey
0x180056ca5  lea     rax, [rsp+2E0h+pcbData]
0x180056caa  mov     [rsp+2E0h+Disposition], rax; pcbData
0x180056caf  xor     edx, edx; lpSubKey
0x180056cb1  lea     rax, [rsp+2E0h+pdwType]
0x180056cb6  mov     qword ptr [rsp+2E0h+CreateOptions], rdi; pvData
0x180056cbb  mov     [rsp+2E0h+Class], rax; pdwType
0x180056cc0  mov     [rsp+2E0h+pcbData], r14d
0x180056cc5  call    cs:__imp_RegGetValueW
0x180056ccb  test    eax, eax
0x180056ccd  jz      short loc_180056CDC
0x180056ccf  mov     r8, rbx; Size
0x180056cd2  xor     edx, edx; Val
0x180056cd4  mov     rcx, rdi; void *
0x180056cd7  call    memset_0
0x180056cdc  movzx   eax, word ptr [rsi]
0x180056cdf  lea     rcx, [rsi+2]
0x180056ce3  mov     [rsp+2E0h+CreateOptions], eax; cbData
0x180056ce7  lea     rdx, Value; "ReadyBootVolumeUniqueId"
0x180056cee  mov     [rsp+2E0h+Class], rcx; lpData
0x180056cf3  mov     r9d, 3; dwType
0x180056cf9  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056cfe  xor     r8d, r8d; Reserved
0x180056d01  call    cs:__imp_RegSetValueExW
0x180056d07  movzx   r8d, word ptr [rsi]; Size
0x180056d0b  mov     rdx, rdi; Buf2
0x180056d0e  mov     rcx, rsi; Buf1
0x180056d11  mov     ebx, eax
0x180056d13  call    memcmp_0
0x180056d18  test    eax, eax
0x180056d1a  jz      short loc_180056D26
0x180056d1c  mov     edx, ebx
0x180056d1e  mov     rcx, rsi
0x180056d21  call    RdBtLogSystemVolumeUniqueId
0x180056d26  test    ebx, ebx
0x180056d28  jz      short loc_180056D7D
0x180056d2a  jmp     short loc_180056D80
0x180056d2c  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056d31  lea     rdx, aBootplan; "BootPlan"
0x180056d38  call    cs:__imp_RegDeleteValueW
0x180056d3e  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056d43  lea     rdx, Value; "ReadyBootVolumeUniqueId"
0x180056d4a  call    cs:__imp_RegDeleteValueW
0x180056d50  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056d55  lea     rdx, aEffectivepends; "EffectivePends"
0x180056d5c  call    cs:__imp_RegDeleteValueW
0x180056d62  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056d67  lea     rdx, aBootcountwithp; "BootCountwithPends"
0x180056d6e  call    cs:__imp_RegDeleteValueW
0x180056d74  xor     edx, edx
0x180056d76  xor     ecx, ecx
0x180056d78  call    RdBtLogSystemVolumeUniqueId
0x180056d7d  mov     ebx, r15d
0x180056d80  mov     rcx, [rsp+2E0h+KeyHandle]; hKey
0x180056d85  test    rcx, rcx
0x180056d88  jz      short loc_180056D90
0x180056d8a  call    cs:__imp_RegCloseKey
0x180056d90  test    rdi, rdi
0x180056d93  jz      short loc_180056DAB
0x180056d95  mov     rcx, cs:PfSvcGlobals
0x180056d9c  mov     r8, rdi; lpMem
0x180056d9f  xor     edx, edx; dwFlags
0x180056da1  mov     rcx, [rcx+58h]; hHeap
0x180056da5  call    cs:__imp_HeapFree
0x180056dab  mov     eax, ebx
0x180056dad  mov     rcx, [rbp+1E0h+var_40]
0x180056db4  xor     rcx, rsp; StackCookie
0x180056db7  call    __security_check_cookie
0x180056dbc  add     rsp, 2B8h
0x180056dc3  pop     r15
0x180056dc5  pop     r14
0x180056dc7  pop     rdi
0x180056dc8  pop     rsi
0x180056dc9  pop     rbx
0x180056dca  pop     rbp
0x180056dcb  retn
```
