# IsAdmin(void *)

- ea: `0x18001be80`
- end: `0x18001bfa5`
- name: `?IsAdmin@@YAHPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001bbb0`

## callees

- `0x18000ab30`
- `0x18001be80`
- `0x18001c340`
- `0x18001c658`
- `0x18001d19c`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bf76`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bf76`
- `ntdll!RtlFreeSid` at `0x18001bf11`
- `ntdll!RtlFreeSid` at `0x18001bf11`

## string_xrefs

- `0x18001bf68`: `AllocateAndInitializeSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsAdmin(void *a1, __int64 a2)
{
  unsigned int v3; // ebx
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax
  int v7; // [rsp+60h] [rbp+7h] BYREF
  PSID Sid; // [rsp+68h] [rbp+Fh] BYREF
  void *v9; // [rsp+70h] [rbp+17h] BYREF
  int v10; // [rsp+78h] [rbp+1Fh]
  int v11; // [rsp+80h] [rbp+27h] BYREF
  __int16 v12; // [rsp+84h] [rbp+2Bh]

  v3 = 0;
  Sid = 0;
  v11 = 0;
  v12 = 1280;
  ProcAddress = (FARPROC)qword_180070348;
  if ( !qword_180070348 )
  {
    SecurityDll = DLpLoadSecurityDll();
    if ( SecurityDll )
    {
      SetLastError(SecurityDll);
      return v3;
    }
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "AllocateAndInitializeSid");
    qword_180070348 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v3;
  }
  LOBYTE(a2) = 2;
  if ( !((unsigned int (__fastcall *)(int *, __int64, __int64, __int64, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, PSID *))ProcAddress)(
          &v11,
          a2,
          32,
          544,
          0,
          0,
          0,
          0,
          0,
          0,
          &Sid) )
    return v3;
  CNtSid::CNtSid((CNtSid *)&v9, Sid);
  RtlFreeSid(Sid);
  if ( !v10 )
  {
    v3 = 0;
    if ( a1 )
    {
      v7 = 0;
      if ( (unsigned int)DLCheckTokenMembership(a1, v9, &v7) )
        v3 = v7;
    }
    CMUILocale::_Free(v9);
    return v3;
  }
  CMUILocale::_Free(v9);
  return 0;
}

```

## disassembly

```asm
0x18001be80  push    rbp
0x18001be82  push    rbx
0x18001be83  push    rsi
0x18001be84  push    rdi
0x18001be85  lea     rbp, [rsp-3Fh]
0x18001be8a  sub     rsp, 98h
0x18001be91  mov     rax, cs:__security_cookie
0x18001be98  xor     rax, rsp
0x18001be9b  mov     [rbp+57h+var_28], rax
0x18001be9f  mov     rdi, rcx
0x18001bea2  xor     esi, esi
0x18001bea4  mov     ebx, esi
0x18001bea6  mov     [rbp+57h+Sid], rsi
0x18001beaa  mov     [rbp+57h+var_30], esi
0x18001bead  mov     [rbp+57h+var_2C], 500h
0x18001beb3  mov     rax, cs:qword_180070348
0x18001beba  test    rax, rax
0x18001bebd  jz      loc_18001BF5F
0x18001bec3  lea     rcx, [rbp+57h+Sid]
0x18001bec7  mov     [rsp+0B0h+var_60], rcx
0x18001becc  mov     [rsp+0B0h+var_68], esi
0x18001bed0  mov     [rsp+0B0h+var_70], esi
0x18001bed4  mov     [rsp+0B0h+var_78], esi
0x18001bed8  mov     [rsp+0B0h+var_80], esi
0x18001bedc  mov     [rsp+0B0h+var_88], esi
0x18001bee0  mov     [rsp+0B0h+var_90], esi
0x18001bee4  mov     r9d, 220h
0x18001beea  mov     r8d, 20h ; ' '
0x18001bef0  mov     dl, 2
0x18001bef2  lea     rcx, [rbp+57h+var_30]
0x18001bef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001befb  test    eax, eax
0x18001befd  jz      short loc_18001BF45
0x18001beff  mov     rdx, [rbp+57h+Sid]; void *
0x18001bf03  lea     rcx, [rbp+57h+var_40]; this
0x18001bf07  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18001bf0c  nop
0x18001bf0d  mov     rcx, [rbp+57h+Sid]; Sid
0x18001bf11  call    cs:__imp_RtlFreeSid
0x18001bf17  cmp     [rbp+57h+var_38], esi
0x18001bf1a  jnz     short loc_18001BF98
0x18001bf1c  mov     ebx, esi
0x18001bf1e  test    rdi, rdi
0x18001bf21  jz      short loc_18001BF3C
0x18001bf23  mov     [rbp+57h+var_50], esi
0x18001bf26  lea     r8, [rbp+57h+var_50]; int *
0x18001bf2a  mov     rdx, [rbp+57h+var_40]; void *
0x18001bf2e  mov     rcx, rdi; void *
0x18001bf31  call    ?DLCheckTokenMembership@@YAHPEAX0PEAH@Z; DLCheckTokenMembership(void *,void *,int *)
0x18001bf36  test    eax, eax
0x18001bf38  cmovnz  ebx, [rbp+57h+var_50]
0x18001bf3c  mov     rcx, [rbp+57h+var_40]; void *
0x18001bf40  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001bf45  mov     eax, ebx
0x18001bf47  mov     rcx, [rbp+57h+var_28]
0x18001bf4b  xor     rcx, rsp; StackCookie
0x18001bf4e  call    __security_check_cookie
0x18001bf53  add     rsp, 98h
0x18001bf5a  pop     rdi
0x18001bf5b  pop     rsi
0x18001bf5c  pop     rbx
0x18001bf5d  pop     rbp
0x18001bf5e  retn
0x18001bf5f  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001bf64  test    eax, eax
0x18001bf66  jnz     short loc_18001BF8E
0x18001bf68  lea     rdx, aAllocateandini; "AllocateAndInitializeSid"
0x18001bf6f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001bf76  call    cs:__imp_GetProcAddress
0x18001bf7c  mov     cs:qword_180070348, rax
0x18001bf83  test    rax, rax
0x18001bf86  jnz     loc_18001BEC3
0x18001bf8c  jmp     short loc_18001BF45
0x18001bf8e  mov     ecx, eax; dwErrCode
0x18001bf90  call    cs:__imp_SetLastError
0x18001bf96  jmp     short loc_18001BF45
0x18001bf98  mov     rcx, [rbp+57h+var_40]; void *
0x18001bf9c  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001bfa1  xor     eax, eax
0x18001bfa3  jmp     short loc_18001BF47
```
