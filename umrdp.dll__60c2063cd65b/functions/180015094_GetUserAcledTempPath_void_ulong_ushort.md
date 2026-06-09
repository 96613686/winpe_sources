# GetUserAcledTempPath(void *,ulong,ushort *)

- ea: `0x180015094`
- end: `0x18001515c`
- name: `?GetUserAcledTempPath@@YAKPEAXKPEAG@Z`
- size: `200`
- prototype: `__int64 __fastcall(void *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014e4c`
- `0x180017494`

## callees

- `0x18000b8f8`
- `0x180015094`
- `0x180017d14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015128`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015106`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015106`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800150a0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800150a0`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800150fa`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800150fa`

## pseudocode

```c
__int64 __fastcall GetUserAcledTempPath(void *a1, __int64 a2, unsigned __int16 *a3)
{
  BOOL v4; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // r8
  unsigned int TempPath2W; // edi
  unsigned int v8; // eax
  __int64 v9; // r8

  v4 = ImpersonateLoggedOnUser(a1);
  if ( !v4
    && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      (unsigned int)(v4 + 10),
      v6,
      CurrentThreadActivityIdPrefix);
  }
  TempPath2W = GetTempPath2W(260, a3);
  if ( v4
    && !RevertToSelf()
    && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    GetLastError();
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dl(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), 11, v9, v8);
  }
  return TempPath2W;
}

```

## disassembly

```asm
0x180015094  push    rbx
0x180015096  push    rbp
0x180015097  push    rsi
0x180015098  push    rdi
0x180015099  sub     rsp, 38h
0x18001509d  mov     rdi, r8
0x1800150a0  call    cs:__imp_ImpersonateLoggedOnUser
0x1800150a6  lea     rbp, WPP_GLOBAL_Control
0x1800150ad  mov     esi, eax
0x1800150af  test    eax, eax
0x1800150b1  jnz     short loc_1800150F2
0x1800150b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150ba  cmp     rcx, rbp
0x1800150bd  jz      short loc_1800150F2
0x1800150bf  test    byte ptr [rcx+1Ch], 1
0x1800150c3  jz      short loc_1800150F2
0x1800150c5  cmp     byte ptr [rcx+19h], 2
0x1800150c9  jb      short loc_1800150F2
0x1800150cb  call    cs:__imp_GetLastError
0x1800150d1  mov     ebx, eax
0x1800150d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800150d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150df  lea     edx, [rsi+0Ah]
0x1800150e2  mov     r9d, eax
0x1800150e5  mov     [rsp+58h+var_38], ebx
0x1800150e9  mov     rcx, [rcx+10h]
0x1800150ed  call    WPP_SF_Dl
0x1800150f2  mov     rdx, rdi
0x1800150f5  mov     ecx, 104h
0x1800150fa  call    cs:__imp_GetTempPath2W
0x180015100  mov     edi, eax
0x180015102  test    esi, esi
0x180015104  jz      short loc_180015151
0x180015106  call    cs:__imp_RevertToSelf
0x18001510c  test    eax, eax
0x18001510e  jnz     short loc_180015151
0x180015110  mov     rcx, cs:WPP_GLOBAL_Control
0x180015117  cmp     rcx, rbp
0x18001511a  jz      short loc_180015151
0x18001511c  test    byte ptr [rcx+1Ch], 1
0x180015120  jz      short loc_180015151
0x180015122  cmp     byte ptr [rcx+19h], 2
0x180015126  jb      short loc_180015151
0x180015128  call    cs:__imp_GetLastError
0x18001512e  mov     ebx, eax
0x180015130  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180015135  mov     rcx, cs:WPP_GLOBAL_Control
0x18001513c  mov     edx, 0Bh
0x180015141  mov     r9d, eax
0x180015144  mov     [rsp+58h+var_38], ebx
0x180015148  mov     rcx, [rcx+10h]
0x18001514c  call    WPP_SF_Dl
0x180015151  mov     eax, edi
0x180015153  add     rsp, 38h
0x180015157  pop     rdi
0x180015158  pop     rsi
0x180015159  pop     rbp
0x18001515a  pop     rbx
0x18001515b  retn
```
