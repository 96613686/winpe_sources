# UbpmTokenGetTokenForTask

- ea: `0x180001e14`
- end: `0x180001fa8`
- name: `UbpmTokenGetTokenForTask`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a8a8`

## callees

- `0x180001e14`
- `0x180001fb0`
- `0x1800189f4`
- `0x180019d90`
- `0x18001e9f4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001efa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001efa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001f34`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180001f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001f06`

## pseudocode

```c
__int64 __fastcall UbpmTokenGetTokenForTask(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8)
{
  __int64 v12; // rax
  DWORD LastError; // ebx
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD InteractiveToken; // eax
  PSID v19; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v21; // rdx
  PSID pSid; // [rsp+58h] [rbp+10h] BYREF

  pSid = 0;
  if ( !a2 )
  {
    v12 = *(_QWORD *)(a1 + 32);
    if ( !v12 || (unsigned int)(*(_DWORD *)(v12 + 32) - 4) > 1 )
      return 87;
  }
  v15 = a6;
  if ( a4 )
    return (unsigned int)UbpmpTokenGetNonInteractiveToken(a1, a2, a4, a5, v15, a7);
  if ( a8 )
  {
    v16 = *(_QWORD *)(a1 + 32);
    if ( !v16 || (*(_BYTE *)(v16 + 76) & 4) == 0 )
      return (unsigned int)UbpmpTokenGetNonInteractiveToken(a1, a2, a4, a5, v15, a7);
    if ( a2 )
    {
      LODWORD(v17) = a2;
    }
    else
    {
      a3 = -1;
      v17 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8LL);
    }
    InteractiveToken = UbpmTokenGetInteractiveToken(v17, a3, a6, a8, (__int64)&pSid);
    if ( InteractiveToken )
    {
      LastError = 0;
      if ( InteractiveToken != 1168 )
        LastError = InteractiveToken;
      if ( !LastError )
        return (unsigned int)UbpmpTokenGetNonInteractiveToken(a1, a2, a4, a5, v15, a7);
    }
    else
    {
      v19 = pSid;
      LengthSid = GetLengthSid(pSid);
      v21 = LocalAlloc(0, LengthSid);
      *a7 = v21;
      if ( v21 )
      {
        if ( CopySid(LengthSid, v21, v19) )
        {
          return 0;
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              (unsigned int)WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
              a5,
              LastError);
        }
      }
      else
      {
        LastError = 14;
        UBPM_MIDL_user_free(v19);
      }
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x180001e14  mov     [rsp+arg_0], rbx
0x180001e19  mov     [rsp+arg_10], rbp
0x180001e1e  push    rsi
0x180001e1f  push    rdi
0x180001e20  push    r14
0x180001e22  sub     rsp, 30h
0x180001e26  mov     [rsp+48h+pSid], 0
0x180001e2f  mov     rbp, r9
0x180001e32  mov     r10d, r8d
0x180001e35  mov     rdi, rdx
0x180001e38  mov     rsi, rcx
0x180001e3b  test    rdx, rdx
0x180001e3e  jnz     short loc_180001E63
0x180001e40  mov     rax, [rcx+20h]
0x180001e44  test    rax, rax
0x180001e47  jnz     short loc_180001EB2
0x180001e49  mov     ebx, 57h ; 'W'
0x180001e4e  mov     rbp, [rsp+48h+arg_10]
0x180001e53  mov     eax, ebx
0x180001e55  mov     rbx, [rsp+48h+arg_0]
0x180001e5a  add     rsp, 30h
0x180001e5e  pop     r14
0x180001e60  pop     rdi
0x180001e61  pop     rsi
0x180001e62  retn
0x180001e63  mov     r14, [rsp+48h+arg_28]
0x180001e68  test    rbp, rbp
0x180001e6b  jnz     short loc_180001E89
0x180001e6d  mov     r9, [rsp+48h+arg_38]
0x180001e75  test    r9, r9
0x180001e78  jz      short loc_180001E49
0x180001e7a  mov     rax, [rcx+20h]
0x180001e7e  test    rax, rax
0x180001e81  jz      short loc_180001E89
0x180001e83  test    byte ptr [rax+4Ch], 4
0x180001e87  jnz     short loc_180001EBF
0x180001e89  mov     rax, [rsp+48h+arg_30]
0x180001e91  mov     r8, rbp
0x180001e94  mov     r9, [rsp+48h+arg_20]
0x180001e99  mov     rdx, rdi
0x180001e9c  mov     [rsp+48h+var_20], rax
0x180001ea1  mov     rcx, rsi
0x180001ea4  mov     [rsp+48h+var_28], r14
0x180001ea9  call    UbpmpTokenGetNonInteractiveToken
0x180001eae  mov     ebx, eax
0x180001eb0  jmp     short loc_180001E4E
0x180001eb2  mov     eax, [rax+20h]
0x180001eb5  sub     eax, 4
0x180001eb8  cmp     eax, 1
0x180001ebb  ja      short loc_180001E49
0x180001ebd  jmp     short loc_180001E63
0x180001ebf  test    rdi, rdi
0x180001ec2  jnz     short loc_180001ED2
0x180001ec4  mov     rax, [rax+8]
0x180001ec8  or      r10d, 0FFFFFFFFh
0x180001ecc  mov     rcx, [rax+8]
0x180001ed0  jmp     short loc_180001ED5
0x180001ed2  mov     rcx, rdi
0x180001ed5  lea     rax, [rsp+48h+pSid]
0x180001eda  mov     r8, r14
0x180001edd  mov     edx, r10d
0x180001ee0  mov     [rsp+48h+var_28], rax
0x180001ee5  call    UbpmTokenGetInteractiveToken
0x180001eea  test    eax, eax
0x180001eec  jnz     loc_180001F91
0x180001ef2  mov     rdi, [rsp+48h+pSid]
0x180001ef7  mov     rcx, rdi; pSid
0x180001efa  call    cs:__imp_GetLengthSid
0x180001f00  mov     edx, eax; uBytes
0x180001f02  xor     ecx, ecx; uFlags
0x180001f04  mov     ebx, eax
0x180001f06  call    cs:__imp_LocalAlloc
0x180001f0c  mov     rdx, rax; pDestinationSid
0x180001f0f  mov     rax, [rsp+48h+arg_30]
0x180001f17  mov     [rax], rdx
0x180001f1a  test    rdx, rdx
0x180001f1d  jnz     short loc_180001F2F
0x180001f1f  mov     rcx, rdi
0x180001f22  lea     ebx, [rdx+0Eh]
0x180001f25  call    UBPM_MIDL_user_free
0x180001f2a  jmp     loc_180001E4E
0x180001f2f  mov     r8, rdi; pSourceSid
0x180001f32  mov     ecx, ebx; nDestinationSidLength
0x180001f34  call    cs:__imp_CopySid
0x180001f3a  test    eax, eax
0x180001f3c  jnz     short loc_180001F8A
0x180001f3e  call    cs:__imp_GetLastError
0x180001f44  mov     ebx, eax
0x180001f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f4d  lea     rax, WPP_GLOBAL_Control
0x180001f54  cmp     rcx, rax
0x180001f57  jz      loc_180001E4E
0x180001f5d  test    byte ptr [rcx+1Ch], 1
0x180001f61  jz      loc_180001E4E
0x180001f67  mov     r9, [rsp+48h+arg_20]
0x180001f6c  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180001f73  mov     rcx, [rcx+10h]
0x180001f77  mov     edx, 0Ah
0x180001f7c  mov     dword ptr [rsp+48h+var_28], ebx
0x180001f80  call    WPP_SF_Sd
0x180001f85  jmp     loc_180001E4E
0x180001f8a  xor     ebx, ebx
0x180001f8c  jmp     loc_180001E4E
0x180001f91  xor     ebx, ebx
0x180001f93  cmp     eax, 490h
0x180001f98  cmovnz  ebx, eax
0x180001f9b  test    ebx, ebx
0x180001f9d  jnz     loc_180001E4E
0x180001fa3  jmp     loc_180001E89
```
