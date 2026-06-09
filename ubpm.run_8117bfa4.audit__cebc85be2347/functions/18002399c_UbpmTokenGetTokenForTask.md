# UbpmTokenGetTokenForTask

- ea: `0x18002399c`
- end: `0x180023b49`
- name: `UbpmTokenGetTokenForTask`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b938`

## callees

- `0x18000e5b0`
- `0x18000fbf0`
- `0x18001af64`
- `0x18002399c`
- `0x180023b50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023a83`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023a83`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023ac9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ad9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023a95`

## pseudocode

```c
__int64 __fastcall UbpmTokenGetTokenForTask(
        __int64 a1,
        void *a2,
        int a3,
        __int64 a4,
        const unsigned __int16 *a5,
        void **a6,
        void **a7,
        __int64 a8)
{
  __int64 v12; // rax
  DWORD LastError; // ebx
  void **v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD InteractiveToken; // eax
  PSID v19; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
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
      LODWORD(v17) = (_DWORD)a2;
    }
    else
    {
      a3 = -1;
      v17 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8LL);
    }
    InteractiveToken = UbpmTokenGetInteractiveToken(v17, a3, (_DWORD)a6, a8, (__int64)&pSid);
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
              (_DWORD)a5,
              LastError);
        }
      }
      else
      {
        LastError = 14;
        UBPM_MIDL_user_free(v19, 0, v22, v23);
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
0x18002399c  mov     [rsp+arg_0], rbx
0x1800239a1  mov     [rsp+arg_10], rbp
0x1800239a6  push    rsi
0x1800239a7  push    rdi
0x1800239a8  push    r14
0x1800239aa  sub     rsp, 30h
0x1800239ae  mov     [rsp+48h+pSid], 0
0x1800239b7  mov     rbp, r9
0x1800239ba  mov     r10d, r8d
0x1800239bd  mov     rdi, rdx
0x1800239c0  mov     rsi, rcx
0x1800239c3  test    rdx, rdx
0x1800239c6  jnz     short loc_1800239EC
0x1800239c8  mov     rax, [rcx+20h]
0x1800239cc  test    rax, rax
0x1800239cf  jnz     short loc_180023A3B
0x1800239d1  mov     ebx, 57h ; 'W'
0x1800239d6  mov     rbp, [rsp+48h+arg_10]
0x1800239db  mov     eax, ebx
0x1800239dd  mov     rbx, [rsp+48h+arg_0]
0x1800239e2  add     rsp, 30h
0x1800239e6  pop     r14
0x1800239e8  pop     rdi
0x1800239e9  pop     rsi
0x1800239ea  retn
0x1800239ec  mov     r14, [rsp+48h+arg_28]
0x1800239f1  test    rbp, rbp
0x1800239f4  jnz     short loc_180023A12
0x1800239f6  mov     r9, [rsp+48h+arg_38]
0x1800239fe  test    r9, r9
0x180023a01  jz      short loc_1800239D1
0x180023a03  mov     rax, [rcx+20h]
0x180023a07  test    rax, rax
0x180023a0a  jz      short loc_180023A12
0x180023a0c  test    byte ptr [rax+4Ch], 4
0x180023a10  jnz     short loc_180023A48
0x180023a12  mov     rax, [rsp+48h+arg_30]
0x180023a1a  mov     r8, rbp
0x180023a1d  mov     r9, [rsp+48h+arg_20]
0x180023a22  mov     rdx, rdi
0x180023a25  mov     [rsp+48h+var_20], rax
0x180023a2a  mov     rcx, rsi
0x180023a2d  mov     [rsp+48h+var_28], r14
0x180023a32  call    UbpmpTokenGetNonInteractiveToken
0x180023a37  mov     ebx, eax
0x180023a39  jmp     short loc_1800239D6
0x180023a3b  mov     eax, [rax+20h]
0x180023a3e  sub     eax, 4
0x180023a41  cmp     eax, 1
0x180023a44  ja      short loc_1800239D1
0x180023a46  jmp     short loc_1800239EC
0x180023a48  test    rdi, rdi
0x180023a4b  jnz     short loc_180023A5B
0x180023a4d  mov     rax, [rax+8]
0x180023a51  or      r10d, 0FFFFFFFFh
0x180023a55  mov     rcx, [rax+8]
0x180023a59  jmp     short loc_180023A5E
0x180023a5b  mov     rcx, rdi
0x180023a5e  lea     rax, [rsp+48h+pSid]
0x180023a63  mov     r8, r14
0x180023a66  mov     edx, r10d
0x180023a69  mov     [rsp+48h+var_28], rax
0x180023a6e  call    UbpmTokenGetInteractiveToken
0x180023a73  test    eax, eax
0x180023a75  jnz     loc_180023B32
0x180023a7b  mov     rdi, [rsp+48h+pSid]
0x180023a80  mov     rcx, rdi; pSid
0x180023a83  call    cs:__imp_GetLengthSid
0x180023a8a  nop     dword ptr [rax+rax+00h]
0x180023a8f  mov     edx, eax; uBytes
0x180023a91  xor     ecx, ecx; uFlags
0x180023a93  mov     ebx, eax
0x180023a95  call    cs:__imp_LocalAlloc
0x180023a9c  nop     dword ptr [rax+rax+00h]
0x180023aa1  mov     rdx, rax; pDestinationSid
0x180023aa4  mov     rax, [rsp+48h+arg_30]
0x180023aac  mov     [rax], rdx
0x180023aaf  test    rdx, rdx
0x180023ab2  jnz     short loc_180023AC4
0x180023ab4  mov     rcx, rdi
0x180023ab7  lea     ebx, [rdx+0Eh]
0x180023aba  call    UBPM_MIDL_user_free
0x180023abf  jmp     loc_1800239D6
0x180023ac4  mov     r8, rdi; pSourceSid
0x180023ac7  mov     ecx, ebx; nDestinationSidLength
0x180023ac9  call    cs:__imp_CopySid
0x180023ad0  nop     dword ptr [rax+rax+00h]
0x180023ad5  test    eax, eax
0x180023ad7  jnz     short loc_180023B2B
0x180023ad9  call    cs:__imp_GetLastError
0x180023ae0  nop     dword ptr [rax+rax+00h]
0x180023ae5  mov     ebx, eax
0x180023ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x180023aee  lea     rax, WPP_GLOBAL_Control
0x180023af5  cmp     rcx, rax
0x180023af8  jz      loc_1800239D6
0x180023afe  test    byte ptr [rcx+1Ch], 1
0x180023b02  jz      loc_1800239D6
0x180023b08  mov     r9, [rsp+48h+arg_20]
0x180023b0d  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180023b14  mov     rcx, [rcx+10h]
0x180023b18  mov     edx, 0Ah
0x180023b1d  mov     dword ptr [rsp+48h+var_28], ebx
0x180023b21  call    WPP_SF_Sd
0x180023b26  jmp     loc_1800239D6
0x180023b2b  xor     ebx, ebx
0x180023b2d  jmp     loc_1800239D6
0x180023b32  xor     ebx, ebx
0x180023b34  cmp     eax, 490h
0x180023b39  cmovnz  ebx, eax
0x180023b3c  test    ebx, ebx
0x180023b3e  jnz     loc_1800239D6
0x180023b44  jmp     loc_180023A12
```
