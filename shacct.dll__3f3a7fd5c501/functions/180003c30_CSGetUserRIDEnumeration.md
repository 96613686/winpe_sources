# CSGetUserRIDEnumeration

- ea: `0x180003c30`
- end: `0x180003e19`
- name: `CSGetUserRIDEnumeration`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008ad0`

## callees

- `0x1800037e0`
- `0x180003c30`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d78`
- `SAMLIB!SamOpenDomain` at `0x180003cec`
- `SAMLIB!SamOpenDomain` at `0x180003cec`
- `SAMLIB!SamConnect` at `0x180003cc6`
- `SAMLIB!SamConnect` at `0x180003cc6`
- `SAMLIB!SamCloseHandle` at `0x180003d12`
- `SAMLIB!SamCloseHandle` at `0x180003df9`
- `SAMLIB!SamCloseHandle` at `0x180003e02`
- `SAMLIB!SamCloseHandle` at `0x180003d12`
- `SAMLIB!SamCloseHandle` at `0x180003df9`
- `SAMLIB!SamCloseHandle` at `0x180003e02`
- `SAMLIB!SamEnumerateUsersInDomain` at `0x180003db5`
- `SAMLIB!SamEnumerateUsersInDomain` at `0x180003db5`

## pseudocode

```c
__int64 __fastcall CSGetUserRIDEnumeration(void *a1, __int64 a2, __int64 a3)
{
  void *v5; // rdi
  __int64 v6; // r14
  __int64 v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // esi
  int v11; // ebx
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  __int64 v17; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v18[4]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v19; // [rsp+58h] [rbp-50h]
  LPVOID pv; // [rsp+B0h] [rbp+8h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+20h] BYREF

  pv = a1;
  v5 = a1;
  v6 = 0;
  v7 = 0;
  if ( a1 )
  {
    v10 = 0;
LABEL_5:
    v18[0] = 48;
    v21 = 0;
    memset(&v18[1], 0, 24);
    v19 = 0;
    v11 = SamConnect(0, &v21, 131105, v18);
    if ( v11 < 0 )
    {
      v9 = v11 | 0x10000000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v14 = 35;
        goto LABEL_14;
      }
    }
    else
    {
      v17 = 0;
      v12 = SamOpenDomain(v21, 131973, v5, &v17);
      if ( v12 >= 0 )
      {
        v7 = v17;
        v9 = 0;
        v6 = v21;
        goto LABEL_15;
      }
      SamCloseHandle(v21);
      v9 = v12 | 0x10000000;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v14 = 34;
LABEL_14:
        WPP_SF_d(v13[2], v14, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v9);
      }
    }
LABEL_15:
    if ( !v10 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v8 = CSGetAccountDomainSid(&pv);
  v5 = pv;
  v9 = v8;
  v10 = 1;
  if ( v8 >= 0 )
    goto LABEL_5;
LABEL_16:
  CoTaskMemFree(v5);
LABEL_17:
  if ( (v9 & 0x80000000) == 0 )
  {
    LODWORD(pv) = 0;
    v15 = SamEnumerateUsersInDomain(v7, &pv, 0, a2, -1, a3);
    if ( v15 < 0 )
    {
      v9 = v15 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, v9);
    }
    SamCloseHandle(v7);
    SamCloseHandle(v6);
  }
  return v9;
}

```

## disassembly

```asm
0x180003c30  mov     rax, rsp
0x180003c33  push    rbx
0x180003c34  push    rbp
0x180003c35  push    r12
0x180003c37  push    r13
0x180003c39  push    r14
0x180003c3b  push    r15
0x180003c3d  sub     rsp, 78h
0x180003c41  xor     r13d, r13d
0x180003c44  mov     [rax+10h], rsi
0x180003c48  mov     [rax-38h], rdi
0x180003c4c  mov     r15, r8
0x180003c4f  mov     [rax+8], rcx
0x180003c53  mov     r12, rdx
0x180003c56  mov     rdi, rcx
0x180003c59  mov     r14d, r13d
0x180003c5c  mov     ebp, r13d
0x180003c5f  test    rcx, rcx
0x180003c62  jnz     short loc_180003C85
0x180003c64  lea     rcx, [rax+8]
0x180003c68  call    CSGetAccountDomainSid
0x180003c6d  mov     rdi, [rsp+0A8h+pv]
0x180003c75  mov     ebx, eax
0x180003c77  mov     esi, 1
0x180003c7c  test    eax, eax
0x180003c7e  jns     short loc_180003C88
0x180003c80  jmp     loc_180003D75
0x180003c85  mov     esi, r13d
0x180003c88  xorps   xmm0, xmm0
0x180003c8b  mov     [rsp+0A8h+var_70], 30h ; '0'
0x180003c94  lea     r9, [rsp+0A8h+var_70]
0x180003c99  mov     [rsp+0A8h+var_58], r13
0x180003c9e  mov     r8d, 20021h
0x180003ca4  mov     [rsp+0A8h+arg_18], r13
0x180003cac  lea     rdx, [rsp+0A8h+arg_18]
0x180003cb4  mov     [rsp+0A8h+var_68], r13
0x180003cb9  xor     ecx, ecx
0x180003cbb  mov     [rsp+0A8h+var_60], r13
0x180003cc0  movdqu  [rsp+0A8h+var_50], xmm0
0x180003cc6  call    cs:__imp_SamConnect
0x180003ccc  mov     ebx, eax
0x180003cce  test    eax, eax
0x180003cd0  js      short loc_180003D3C
0x180003cd2  mov     rcx, [rsp+0A8h+arg_18]
0x180003cda  lea     r9, [rsp+0A8h+var_78]
0x180003cdf  mov     r8, rdi
0x180003ce2  mov     [rsp+0A8h+var_78], r13
0x180003ce7  mov     edx, 20385h
0x180003cec  call    cs:__imp_SamOpenDomain
0x180003cf2  mov     ebx, eax
0x180003cf4  test    eax, eax
0x180003cf6  js      short loc_180003D0A
0x180003cf8  mov     rbp, [rsp+0A8h+var_78]
0x180003cfd  mov     ebx, r13d
0x180003d00  mov     r14, [rsp+0A8h+arg_18]
0x180003d08  jmp     short loc_180003D71
0x180003d0a  mov     rcx, [rsp+0A8h+arg_18]
0x180003d12  call    cs:__imp_SamCloseHandle
0x180003d18  bts     ebx, 1Ch
0x180003d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d23  lea     rax, WPP_GLOBAL_Control
0x180003d2a  cmp     rcx, rax
0x180003d2d  jz      short loc_180003D71
0x180003d2f  test    byte ptr [rcx+1Ch], 2
0x180003d33  jz      short loc_180003D71
0x180003d35  mov     edx, 22h ; '"'
0x180003d3a  jmp     short loc_180003D5E
0x180003d3c  bts     ebx, 1Ch
0x180003d40  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d47  lea     rax, WPP_GLOBAL_Control
0x180003d4e  cmp     rcx, rax
0x180003d51  jz      short loc_180003D71
0x180003d53  test    byte ptr [rcx+1Ch], 2
0x180003d57  jz      short loc_180003D71
0x180003d59  mov     edx, 23h ; '#'
0x180003d5e  mov     rcx, [rcx+10h]
0x180003d62  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180003d69  mov     r9d, ebx
0x180003d6c  call    WPP_SF_d
0x180003d71  test    esi, esi
0x180003d73  jz      short loc_180003D7E
0x180003d75  mov     rcx, rdi; pv
0x180003d78  call    cs:__imp_CoTaskMemFree
0x180003d7e  mov     rdi, [rsp+0A8h+var_38]
0x180003d83  mov     rsi, [rsp+0A8h+arg_8]
0x180003d8b  test    ebx, ebx
0x180003d8d  js      short loc_180003E08
0x180003d8f  mov     [rsp+0A8h+var_80], r15
0x180003d94  lea     rdx, [rsp+0A8h+pv]
0x180003d9c  mov     r9, r12
0x180003d9f  mov     [rsp+0A8h+var_88], 0FFFFFFFFh
0x180003da7  xor     r8d, r8d
0x180003daa  mov     dword ptr [rsp+0A8h+pv], r13d
0x180003db2  mov     rcx, rbp
0x180003db5  call    cs:__imp_SamEnumerateUsersInDomain
0x180003dbb  test    eax, eax
0x180003dbd  jns     short loc_180003DF6
0x180003dbf  mov     ebx, eax
0x180003dc1  bts     ebx, 1Ch
0x180003dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dcc  lea     rax, WPP_GLOBAL_Control
0x180003dd3  cmp     rcx, rax
0x180003dd6  jz      short loc_180003DF6
0x180003dd8  test    byte ptr [rcx+1Ch], 2
0x180003ddc  jz      short loc_180003DF6
0x180003dde  mov     rcx, [rcx+10h]
0x180003de2  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180003de9  mov     edx, 20h ; ' '
0x180003dee  mov     r9d, ebx
0x180003df1  call    WPP_SF_d
0x180003df6  mov     rcx, rbp
0x180003df9  call    cs:__imp_SamCloseHandle
0x180003dff  mov     rcx, r14
0x180003e02  call    cs:__imp_SamCloseHandle
0x180003e08  mov     eax, ebx
0x180003e0a  add     rsp, 78h
0x180003e0e  pop     r15
0x180003e10  pop     r14
0x180003e12  pop     r13
0x180003e14  pop     r12
0x180003e16  pop     rbp
0x180003e17  pop     rbx
0x180003e18  retn
```
