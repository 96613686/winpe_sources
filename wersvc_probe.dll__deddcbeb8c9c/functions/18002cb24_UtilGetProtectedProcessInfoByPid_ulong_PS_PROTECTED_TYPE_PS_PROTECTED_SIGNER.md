# UtilGetProtectedProcessInfoByPid(ulong,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)

- ea: `0x18002cb24`
- end: `0x18002cbd7`
- name: `?UtilGetProtectedProcessInfoByPid@@YAJKPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(DWORD dwProcessId, enum _PS_PROTECTED_TYPE *, enum _PS_PROTECTED_SIGNER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180014378`

## callees

- `0x180011f38`
- `0x18002c9dc`
- `0x18002cb24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cb5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cbbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cbbf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002cb47`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002cb47`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProtectedProcessInfoByPid(
        DWORD dwProcessId,
        enum _PS_PROTECTED_TYPE *a2,
        enum _PS_PROTECTED_SIGNER *a3)
{
  HANDLE v5; // rax
  void *v6; // rdi
  signed int LastError; // eax
  unsigned int ProtectedProcessInfo; // ebx

  v5 = OpenProcess(0x1000u, 0, dwProcessId);
  v6 = v5;
  if ( (unsigned __int64)v5 + 1 > 1 )
  {
    ProtectedProcessInfo = UtilGetProtectedProcessInfo(v5, a2, 0);
    CloseHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    ProtectedProcessInfo = LastError;
    if ( LastError > 0 )
      ProtectedProcessInfo = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids,
        dwProcessId,
        ProtectedProcessInfo);
  }
  return ProtectedProcessInfo;
}

```

## disassembly

```asm
0x18002cb24  mov     [rsp+arg_0], rbx
0x18002cb29  mov     [rsp+arg_8], rsi
0x18002cb2e  mov     [rsp+arg_10], r8
0x18002cb33  push    rdi
0x18002cb34  sub     rsp, 30h
0x18002cb38  mov     rbx, rdx
0x18002cb3b  mov     esi, ecx
0x18002cb3d  mov     r8d, ecx; dwProcessId
0x18002cb40  xor     edx, edx; bInheritHandle
0x18002cb42  mov     ecx, 1000h; dwDesiredAccess
0x18002cb47  call    cs:__imp_OpenProcess
0x18002cb4d  mov     rdi, rax
0x18002cb50  mov     [rsp+38h+arg_10], rax
0x18002cb55  lea     r8, [rax+1]
0x18002cb59  cmp     r8, 1
0x18002cb5d  ja      short loc_18002CBAC
0x18002cb5f  call    cs:__imp_GetLastError
0x18002cb65  mov     ebx, eax
0x18002cb67  test    eax, eax
0x18002cb69  jle     short loc_18002CB74
0x18002cb6b  movzx   ebx, ax
0x18002cb6e  or      ebx, 80070000h
0x18002cb74  lea     rax, WPP_GLOBAL_Control
0x18002cb7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb82  cmp     rcx, rax
0x18002cb85  jz      short loc_18002CBAA
0x18002cb87  test    byte ptr [rcx+1Ch], 1
0x18002cb8b  jz      short loc_18002CBAA
0x18002cb8d  mov     edx, 0Dh
0x18002cb92  mov     [rsp+38h+var_18], ebx
0x18002cb96  mov     r9d, esi
0x18002cb99  lea     r8, WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids
0x18002cba0  mov     rcx, [rcx+10h]
0x18002cba4  call    WPP_SF_Dd
0x18002cba9  nop
0x18002cbaa  jmp     short loc_18002CBC5
0x18002cbac  xor     r8d, r8d; enum _PS_PROTECTED_SIGNER *
0x18002cbaf  mov     rdx, rbx; enum _PS_PROTECTED_TYPE *
0x18002cbb2  mov     rcx, rdi; void *
0x18002cbb5  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x18002cbba  mov     ebx, eax
0x18002cbbc  mov     rcx, rdi; hObject
0x18002cbbf  call    cs:__imp_CloseHandle
0x18002cbc5  mov     eax, ebx
0x18002cbc7  mov     rbx, [rsp+38h+arg_0]
0x18002cbcc  mov     rsi, [rsp+38h+arg_8]
0x18002cbd1  add     rsp, 30h
0x18002cbd5  pop     rdi
0x18002cbd6  retn
```
