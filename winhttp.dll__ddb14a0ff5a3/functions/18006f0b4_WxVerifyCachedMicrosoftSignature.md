# WxVerifyCachedMicrosoftSignature

- ea: `0x18006f0b4`
- end: `0x18006f2b4`
- name: `WxVerifyCachedMicrosoftSignature`
- size: `512`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006ede4`

## callees

- `0x18006f0b4`
- `0x1800a1d10`
- `0x1800cf660`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f240`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f1b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f1b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f11d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f11d`
- `ntdll!RtlNtStatusToDosError` at `0x18006f2a7`
- `ntdll!RtlNtStatusToDosError` at `0x18006f2a7`
- `ntdll!NtGetCachedSigningLevel` at `0x18006f161`
- `ntdll!NtGetCachedSigningLevel` at `0x18006f161`
- `ntdll!NtCompareSigningLevels` at `0x18006f1e9`
- `ntdll!NtCompareSigningLevels` at `0x18006f1e9`
- `ntdll!NtSetCachedSigningLevel` at `0x18006f193`
- `ntdll!NtSetCachedSigningLevel` at `0x18006f193`

## pseudocode

```c
__int64 __fastcall WxVerifyCachedMicrosoftSignature(const WCHAR *a1, int a2)
{
  unsigned __int8 v2; // si
  HANDLE FileW; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  NTSTATUS CachedSigningLevel; // edi
  ULONG v7; // ebx
  int v9; // eax
  DWORD LastError; // eax
  __int64 v11; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-58h]
  HANDLE dwCreationDispositiona; // [rsp+20h] [rbp-58h]
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v15[4]; // [rsp+48h] [rbp-30h] BYREF
  int v16; // [rsp+4Ch] [rbp-2Ch] BYREF

  v16 = 0;
  v15[0] = 0;
  v2 = a2 != 0 ? 4 : 12;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  hObject = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    dwCreationDispositiona = 0;
    CachedSigningLevel = NtGetCachedSigningLevel(FileW, &v16, v15, 0);
    if ( CachedSigningLevel >= 0 || CachedSigningLevel == -1073741275 )
    {
      v7 = 0;
      if ( CachedSigningLevel >= 0 )
      {
        LOBYTE(v5) = v15[0];
        LOBYTE(v4) = v2;
        v9 = NtCompareSigningLevels(v5, v4);
        if ( v9 >= 0 )
          goto LABEL_5;
        if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
        {
          LODWORD(dwCreationDispositiona) = v2;
          WPP_SF_DDD(
            1053,
            12,
            WPP_417ff70581123b89fdcd028156f355ef_Traceguids,
            v15[0],
            dwCreationDispositiona,
            (unsigned int)v9);
        }
      }
      dwCreationDispositiona = hObject;
      LOBYTE(v4) = v2;
      CachedSigningLevel = NtSetCachedSigningLevel(4, v4, &hObject);
      if ( CachedSigningLevel >= 0 )
        goto LABEL_5;
      if ( (BYTE3(xmmword_180107A60) & 0x20) == 0 )
        goto LABEL_21;
      v11 = 13;
    }
    else
    {
      if ( (BYTE3(xmmword_180107A60) & 0x20) == 0 )
      {
LABEL_21:
        v7 = RtlNtStatusToDosError(CachedSigningLevel);
        goto LABEL_5;
      }
      v11 = 11;
    }
    WPP_SF_d(
      1053,
      v11,
      WPP_417ff70581123b89fdcd028156f355ef_Traceguids,
      (unsigned int)CachedSigningLevel,
      dwCreationDispositiona);
    goto LABEL_21;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( (BYTE3(xmmword_180107A60) & 0x20) == 0 )
    goto LABEL_7;
  WPP_SF_d(1053, 10, WPP_417ff70581123b89fdcd028156f355ef_Traceguids, LastError, *(_QWORD *)dwCreationDisposition);
LABEL_5:
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_417ff70581123b89fdcd028156f355ef_Traceguids, v7, dwCreationDispositiona);
LABEL_7:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v7;
}

```

## disassembly

```asm
0x18006f0b4  mov     r11, rsp
0x18006f0b7  mov     [r11+10h], rbx
0x18006f0bb  mov     [r11+18h], rsi
0x18006f0bf  push    rdi
0x18006f0c0  push    r12
0x18006f0c2  push    r15
0x18006f0c4  sub     rsp, 60h
0x18006f0c8  mov     rax, cs:__security_cookie
0x18006f0cf  xor     rax, rsp
0x18006f0d2  mov     [rsp+78h+var_28], rax
0x18006f0d7  neg     edx
0x18006f0d9  mov     qword ptr [r11-48h], 0
0x18006f0e1  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f0e9  mov     edx, 80000000h; dwDesiredAccess
0x18006f0ee  sbb     sil, sil
0x18006f0f1  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x18006f0f9  xor     r9d, r9d; lpSecurityAttributes
0x18006f0fc  mov     [rsp+78h+var_2C], 0
0x18006f104  and     sil, 0F8h
0x18006f108  mov     [rsp+78h+var_30], 0
0x18006f10d  add     sil, 0Ch
0x18006f111  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18006f119  lea     r8d, [r9+1]; dwShareMode
0x18006f11d  call    cs:__imp_CreateFileW
0x18006f123  mov     [rsp+78h+hObject], rax
0x18006f128  mov     r15d, 41Dh
0x18006f12e  lea     r12, WPP_417ff70581123b89fdcd028156f355ef_Traceguids
0x18006f135  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f139  jz      loc_18006F240
0x18006f13f  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0
0x18006f148  lea     r8, [rsp+78h+var_30]
0x18006f14d  xor     r9d, r9d
0x18006f150  mov     qword ptr [rsp+78h+dwCreationDisposition], 0
0x18006f159  lea     rdx, [rsp+78h+var_2C]
0x18006f15e  mov     rcx, rax
0x18006f161  call    cs:__imp_NtGetCachedSigningLevel
0x18006f167  mov     edi, eax
0x18006f169  test    eax, eax
0x18006f16b  js      loc_18006F26D
0x18006f171  xor     ebx, ebx
0x18006f173  test    edi, edi
0x18006f175  jns     short loc_18006F1E2
0x18006f177  mov     rax, [rsp+78h+hObject]
0x18006f17c  lea     r8, [rsp+78h+hObject]
0x18006f181  mov     r9d, 1
0x18006f187  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18006f18c  mov     dl, sil
0x18006f18f  lea     ecx, [r9+3]
0x18006f193  call    cs:__imp_NtSetCachedSigningLevel
0x18006f199  mov     edi, eax
0x18006f19b  test    eax, eax
0x18006f19d  js      loc_18006F289
0x18006f1a3  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18006f1aa  jnz     short loc_18006F228
0x18006f1ac  mov     rcx, [rsp+78h+hObject]; hObject
0x18006f1b1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006f1b5  jz      short loc_18006F1BD
0x18006f1b7  call    cs:__imp_CloseHandle
0x18006f1bd  mov     eax, ebx
0x18006f1bf  mov     rcx, [rsp+78h+var_28]
0x18006f1c4  xor     rcx, rsp; StackCookie
0x18006f1c7  call    __security_check_cookie
0x18006f1cc  lea     r11, [rsp+78h+var_18]
0x18006f1d1  mov     rbx, [r11+28h]
0x18006f1d5  mov     rsi, [r11+30h]
0x18006f1d9  mov     rsp, r11
0x18006f1dc  pop     r15
0x18006f1de  pop     r12
0x18006f1e0  pop     rdi
0x18006f1e1  retn
0x18006f1e2  mov     cl, [rsp+78h+var_30]
0x18006f1e6  mov     dl, sil
0x18006f1e9  call    cs:__imp_NtCompareSigningLevels
0x18006f1ef  test    eax, eax
0x18006f1f1  jns     short loc_18006F1A3
0x18006f1f3  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18006f1fa  jz      loc_18006F177
0x18006f200  movzx   r9d, [rsp+78h+var_30]
0x18006f206  mov     edx, 0Ch
0x18006f20b  movzx   r8d, sil
0x18006f20f  mov     ecx, r15d
0x18006f212  mov     [rsp+78h+dwFlagsAndAttributes], eax
0x18006f216  mov     [rsp+78h+dwCreationDisposition], r8d
0x18006f21b  mov     r8, r12
0x18006f21e  call    WPP_SF_DDD
0x18006f223  jmp     loc_18006F177
0x18006f228  mov     edx, 0Eh
0x18006f22d  mov     ecx, r15d
0x18006f230  mov     r9d, ebx
0x18006f233  mov     r8, r12
0x18006f236  call    WPP_SF_d
0x18006f23b  jmp     loc_18006F1AC
0x18006f240  call    cs:__imp_GetLastError
0x18006f246  mov     ebx, eax
0x18006f248  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18006f24f  jz      loc_18006F1AC
0x18006f255  mov     edx, 0Ah
0x18006f25a  mov     ecx, r15d
0x18006f25d  mov     r9d, eax
0x18006f260  mov     r8, r12
0x18006f263  call    WPP_SF_d
0x18006f268  jmp     loc_18006F1A3
0x18006f26d  cmp     edi, 0C0000225h
0x18006f273  jz      loc_18006F171
0x18006f279  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18006f280  jz      short loc_18006F2A5
0x18006f282  mov     edx, 0Bh
0x18006f287  jmp     short loc_18006F297
0x18006f289  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18006f290  jz      short loc_18006F2A5
0x18006f292  mov     edx, 0Dh
0x18006f297  mov     r9d, edi
0x18006f29a  mov     r8, r12
0x18006f29d  mov     ecx, r15d
0x18006f2a0  call    WPP_SF_d
0x18006f2a5  mov     ecx, edi; Status
0x18006f2a7  call    cs:__imp_RtlNtStatusToDosError
0x18006f2ad  mov     ebx, eax
0x18006f2af  jmp     loc_18006F1A3
```
