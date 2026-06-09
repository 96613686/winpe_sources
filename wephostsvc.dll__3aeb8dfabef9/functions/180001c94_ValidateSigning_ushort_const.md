# ValidateSigning(ushort const *)

- ea: `0x180001c94`
- end: `0x180001dfb`
- name: `?ValidateSigning@@YAKPEBG@Z`
- size: `359`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800022c0`

## callees

- `0x180001c94`
- `0x180001e44`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001deb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001deb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cdd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001cce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001cce`
- `ntdll!NtGetCachedSigningLevel` at `0x180001d41`
- `ntdll!NtGetCachedSigningLevel` at `0x180001d41`
- `ntdll!NtQuerySystemInformation` at `0x180001d98`
- `ntdll!NtQuerySystemInformation` at `0x180001d98`

## pseudocode

```c
__int64 __fastcall ValidateSigning(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  void *v3; // rsi
  DWORD CachedSigningLevel; // ebx
  int v5; // r8d
  int v6; // r8d
  _QWORD *v7; // rcx
  int v8; // edx
  unsigned __int8 v10; // [rsp+68h] [rbp+10h] BYREF
  int v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 SystemInformation; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  v11 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v3 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    CachedSigningLevel = NtGetCachedSigningLevel(FileW, &v11, &v10, 0, 0, 0);
    if ( CachedSigningLevel )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_18;
      v8 = 15;
      goto LABEL_17;
    }
    if ( v10 < 8u )
    {
      SystemInformation = 8;
      if ( NtQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0) < 0
        || (SystemInformation & 0x200000000LL) == 0
        || v10 != 4 )
      {
        CachedSigningLevel = 577;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_18;
        v8 = 16;
LABEL_17:
        WPP_SF_DS(v7[2], v8, v6, CachedSigningLevel, (__int64)a1);
        goto LABEL_18;
      }
      CachedSigningLevel = 0;
    }
LABEL_18:
    CloseHandle(v3);
    return CachedSigningLevel;
  }
  CachedSigningLevel = GetLastError();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v5, CachedSigningLevel, (__int64)a1);
  return CachedSigningLevel;
}

```

## disassembly

```asm
0x180001c94  mov     rax, rsp
0x180001c97  push    rbx
0x180001c98  push    rsi
0x180001c99  push    rdi
0x180001c9a  sub     rsp, 40h
0x180001c9e  mov     qword ptr [rax-28h], 0
0x180001ca6  xor     r9d, r9d; lpSecurityAttributes
0x180001ca9  mov     dword ptr [rax-30h], 80h
0x180001cb0  mov     edx, 80000000h; dwDesiredAccess
0x180001cb5  mov     rdi, rcx
0x180001cb8  mov     byte ptr [rax+10h], 0
0x180001cbc  mov     dword ptr [rax+18h], 0
0x180001cc3  lea     r8d, [r9+1]; dwShareMode
0x180001cc7  mov     dword ptr [rax-38h], 3
0x180001cce  call    cs:__imp_CreateFileW
0x180001cd4  mov     rsi, rax
0x180001cd7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001cdb  jnz     short loc_180001D1F
0x180001cdd  call    cs:__imp_GetLastError
0x180001ce3  mov     ebx, eax
0x180001ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cec  lea     rax, WPP_GLOBAL_Control
0x180001cf3  cmp     rcx, rax
0x180001cf6  jz      loc_180001DF1
0x180001cfc  test    byte ptr [rcx+1Ch], 1
0x180001d00  jz      loc_180001DF1
0x180001d06  mov     rcx, [rcx+10h]
0x180001d0a  lea     edx, [rsi+0Fh]
0x180001d0d  mov     r9d, ebx
0x180001d10  mov     [rsp+58h+var_38], rdi
0x180001d15  call    WPP_SF_DS
0x180001d1a  jmp     loc_180001DF1
0x180001d1f  mov     [rsp+58h+var_30], 0
0x180001d28  lea     r8, [rsp+58h+arg_8]
0x180001d2d  xor     r9d, r9d
0x180001d30  mov     [rsp+58h+var_38], 0
0x180001d39  lea     rdx, [rsp+58h+arg_10]
0x180001d3e  mov     rcx, rsi
0x180001d41  call    cs:__imp_NtGetCachedSigningLevel
0x180001d47  mov     ebx, eax
0x180001d49  test    eax, eax
0x180001d4b  jz      short loc_180001D71
0x180001d4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d54  lea     rax, WPP_GLOBAL_Control
0x180001d5b  cmp     rcx, rax
0x180001d5e  jz      loc_180001DE8
0x180001d64  test    byte ptr [rcx+1Ch], 1
0x180001d68  jz      short loc_180001DE8
0x180001d6a  mov     edx, 0Fh
0x180001d6f  jmp     short loc_180001DD7
0x180001d71  mov     r8d, 8; SystemInformationLength
0x180001d77  cmp     [rsp+58h+arg_8], r8b
0x180001d7c  jnb     short loc_180001DE8
0x180001d7e  mov     [rsp+58h+SystemInformation], 0
0x180001d87  lea     rdx, [rsp+58h+SystemInformation]; SystemInformation
0x180001d8c  xor     r9d, r9d; ReturnLength
0x180001d8f  mov     dword ptr [rsp+58h+SystemInformation], r8d
0x180001d94  lea     ecx, [r8+5Fh]; SystemInformationClass
0x180001d98  call    cs:__imp_NtQuerySystemInformation
0x180001d9e  test    eax, eax
0x180001da0  js      short loc_180001DB4
0x180001da2  test    byte ptr [rsp+58h+SystemInformation+4], 2
0x180001da7  jz      short loc_180001DB4
0x180001da9  cmp     [rsp+58h+arg_8], 4
0x180001dae  jnz     short loc_180001DB4
0x180001db0  xor     ebx, ebx
0x180001db2  jmp     short loc_180001DE8
0x180001db4  mov     ebx, 241h
0x180001db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dc0  lea     rax, WPP_GLOBAL_Control
0x180001dc7  cmp     rcx, rax
0x180001dca  jz      short loc_180001DE8
0x180001dcc  test    byte ptr [rcx+1Ch], 1
0x180001dd0  jz      short loc_180001DE8
0x180001dd2  mov     edx, 10h
0x180001dd7  mov     rcx, [rcx+10h]
0x180001ddb  mov     r9d, ebx
0x180001dde  mov     [rsp+58h+var_38], rdi
0x180001de3  call    WPP_SF_DS
0x180001de8  mov     rcx, rsi; hObject
0x180001deb  call    cs:__imp_CloseHandle
0x180001df1  mov     eax, ebx
0x180001df3  add     rsp, 40h
0x180001df7  pop     rdi
0x180001df8  pop     rsi
0x180001df9  pop     rbx
0x180001dfa  retn
```
