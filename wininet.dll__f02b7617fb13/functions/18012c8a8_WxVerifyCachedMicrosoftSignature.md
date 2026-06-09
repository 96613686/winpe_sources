# WxVerifyCachedMicrosoftSignature

- ea: `0x18012c8a8`
- end: `0x18012ca86`
- name: `WxVerifyCachedMicrosoftSignature`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18012c5f4`

## callees

- `0x18012c8a8`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e9d2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c92f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c92f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18012c911`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18012c911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012ca5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012ca5b`
- `ntdll!RtlNtStatusToDosError` at `0x18012ca2c`
- `ntdll!RtlNtStatusToDosError` at `0x18012ca2c`
- `ntdll!NtGetCachedSigningLevel` at `0x18012c97e`
- `ntdll!NtGetCachedSigningLevel` at `0x18012c97e`
- `ntdll!NtCompareSigningLevels` at `0x18012c9b2`
- `ntdll!NtCompareSigningLevels` at `0x18012c9b2`
- `ntdll!NtSetCachedSigningLevel` at `0x18012ca02`
- `ntdll!NtSetCachedSigningLevel` at `0x18012ca02`

## pseudocode

```c
__int64 __fastcall WxVerifyCachedMicrosoftSignature(const WCHAR *a1, int a2)
{
  unsigned __int8 v2; // si
  HANDLE FileW; // rax
  DWORD LastError; // eax
  ULONG v5; // ebx
  int CachedSigningLevel; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  NTSTATUS v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-58h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-50h]
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v16[4]; // [rsp+48h] [rbp-30h] BYREF
  int v17; // [rsp+4Ch] [rbp-2Ch] BYREF

  v17 = 0;
  v16[0] = 0;
  v2 = a2 != 0 ? 4 : 12;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  hObject = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (BYTE3(xmmword_180266B60) & 0x20) == 0 )
      goto LABEL_19;
    WPP_SF_d(1053, 10, WPP_417ff70581123b89fdcd028156f355ef_Traceguids, LastError);
    goto LABEL_17;
  }
  CachedSigningLevel = NtGetCachedSigningLevel(FileW, &v17, v16, 0, 0, 0);
  v9 = CachedSigningLevel;
  if ( CachedSigningLevel < 0 && CachedSigningLevel != -1073741275 )
  {
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    {
      v10 = 11;
LABEL_15:
      WPP_SF_d(1053, v10, WPP_417ff70581123b89fdcd028156f355ef_Traceguids, (unsigned int)v9);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v5 = 0;
  if ( CachedSigningLevel >= 0 )
  {
    LOBYTE(v8) = v16[0];
    LOBYTE(v7) = v2;
    v11 = NtCompareSigningLevels(v8, v7);
    if ( v11 >= 0 )
      goto LABEL_17;
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    {
      dwFlagsAndAttributes[0] = v11;
      dwCreationDisposition[0] = v2;
      WPP_SF_ddd(
        1053,
        12,
        WPP_417ff70581123b89fdcd028156f355ef_Traceguids,
        v16[0],
        *(_QWORD *)dwCreationDisposition,
        *(_QWORD *)dwFlagsAndAttributes);
    }
  }
  LOBYTE(v7) = v2;
  v9 = NtSetCachedSigningLevel(4, v7, &hObject);
  if ( v9 < 0 )
  {
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    {
      v10 = 13;
      goto LABEL_15;
    }
LABEL_16:
    v5 = RtlNtStatusToDosError(v9);
  }
LABEL_17:
  if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_417ff70581123b89fdcd028156f355ef_Traceguids, v5);
LABEL_19:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x18012c8a8  mov     r11, rsp
0x18012c8ab  mov     [r11+10h], rbx
0x18012c8af  mov     [r11+18h], rsi
0x18012c8b3  push    rdi
0x18012c8b4  push    r12
0x18012c8b6  push    r15
0x18012c8b8  sub     rsp, 60h
0x18012c8bc  mov     rax, cs:__security_cookie
0x18012c8c3  xor     rax, rsp
0x18012c8c6  mov     [rsp+78h+var_28], rax
0x18012c8cb  neg     edx
0x18012c8cd  mov     qword ptr [r11-48h], 0
0x18012c8d5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18012c8dd  mov     edx, 80000000h; dwDesiredAccess
0x18012c8e2  sbb     sil, sil
0x18012c8e5  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x18012c8ed  xor     r9d, r9d; lpSecurityAttributes
0x18012c8f0  mov     [rsp+78h+var_2C], 0
0x18012c8f8  and     sil, 0F8h
0x18012c8fc  mov     [rsp+78h+var_30], 0
0x18012c901  add     sil, 0Ch
0x18012c905  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18012c90d  lea     r8d, [r9+1]; dwShareMode
0x18012c911  call    cs:__imp_CreateFileW
0x18012c917  mov     [rsp+78h+hObject], rax
0x18012c91c  mov     r15d, 41Dh
0x18012c922  lea     r12, WPP_417ff70581123b89fdcd028156f355ef_Traceguids
0x18012c929  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012c92d  jnz     short loc_18012C95C
0x18012c92f  call    cs:__imp_GetLastError
0x18012c935  mov     ebx, eax
0x18012c937  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18012c93e  jz      loc_18012CA50
0x18012c944  mov     edx, 0Ah
0x18012c949  mov     ecx, r15d
0x18012c94c  mov     r9d, eax
0x18012c94f  mov     r8, r12
0x18012c952  call    WPP_SF_d
0x18012c957  jmp     loc_18012CA34
0x18012c95c  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0
0x18012c965  lea     r8, [rsp+78h+var_30]
0x18012c96a  xor     r9d, r9d
0x18012c96d  mov     qword ptr [rsp+78h+dwCreationDisposition], 0
0x18012c976  lea     rdx, [rsp+78h+var_2C]
0x18012c97b  mov     rcx, rax
0x18012c97e  call    cs:__imp_NtGetCachedSigningLevel
0x18012c984  mov     edi, eax
0x18012c986  test    eax, eax
0x18012c988  jns     short loc_18012C9A5
0x18012c98a  cmp     eax, 0C0000225h
0x18012c98f  jz      short loc_18012C9A5
0x18012c991  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18012c998  jz      loc_18012CA2A
0x18012c99e  mov     edx, 0Bh
0x18012c9a3  jmp     short loc_18012CA1C
0x18012c9a5  xor     ebx, ebx
0x18012c9a7  test    edi, edi
0x18012c9a9  js      short loc_18012C9E6
0x18012c9ab  mov     cl, [rsp+78h+var_30]
0x18012c9af  mov     dl, sil
0x18012c9b2  call    cs:__imp_NtCompareSigningLevels
0x18012c9b8  test    eax, eax
0x18012c9ba  jns     short loc_18012CA34
0x18012c9bc  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18012c9c3  jz      short loc_18012C9E6
0x18012c9c5  movzx   r9d, [rsp+78h+var_30]
0x18012c9cb  lea     edx, [rbx+0Ch]
0x18012c9ce  movzx   r8d, sil
0x18012c9d2  mov     ecx, r15d
0x18012c9d5  mov     [rsp+78h+dwFlagsAndAttributes], eax
0x18012c9d9  mov     [rsp+78h+dwCreationDisposition], r8d
0x18012c9de  mov     r8, r12
0x18012c9e1  call    WPP_SF_ddd
0x18012c9e6  mov     rax, [rsp+78h+hObject]
0x18012c9eb  lea     r8, [rsp+78h+hObject]
0x18012c9f0  mov     r9d, 1
0x18012c9f6  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18012c9fb  mov     dl, sil
0x18012c9fe  lea     ecx, [r9+3]
0x18012ca02  call    cs:__imp_NtSetCachedSigningLevel
0x18012ca08  mov     edi, eax
0x18012ca0a  test    eax, eax
0x18012ca0c  jns     short loc_18012CA34
0x18012ca0e  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18012ca15  jz      short loc_18012CA2A
0x18012ca17  mov     edx, 0Dh
0x18012ca1c  mov     r9d, edi
0x18012ca1f  mov     r8, r12
0x18012ca22  mov     ecx, r15d
0x18012ca25  call    WPP_SF_d
0x18012ca2a  mov     ecx, edi; Status
0x18012ca2c  call    cs:__imp_RtlNtStatusToDosError
0x18012ca32  mov     ebx, eax
0x18012ca34  test    byte ptr cs:xmmword_180266B60+3, 20h
0x18012ca3b  jz      short loc_18012CA50
0x18012ca3d  mov     edx, 0Eh
0x18012ca42  mov     ecx, r15d
0x18012ca45  mov     r9d, ebx
0x18012ca48  mov     r8, r12
0x18012ca4b  call    WPP_SF_d
0x18012ca50  mov     rcx, [rsp+78h+hObject]; hObject
0x18012ca55  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012ca59  jz      short loc_18012CA61
0x18012ca5b  call    cs:__imp_CloseHandle
0x18012ca61  mov     eax, ebx
0x18012ca63  mov     rcx, [rsp+78h+var_28]
0x18012ca68  xor     rcx, rsp; StackCookie
0x18012ca6b  call    __security_check_cookie
0x18012ca70  lea     r11, [rsp+78h+var_18]
0x18012ca75  mov     rbx, [r11+28h]
0x18012ca79  mov     rsi, [r11+30h]
0x18012ca7d  mov     rsp, r11
0x18012ca80  pop     r15
0x18012ca82  pop     r12
0x18012ca84  pop     rdi
0x18012ca85  retn
```
