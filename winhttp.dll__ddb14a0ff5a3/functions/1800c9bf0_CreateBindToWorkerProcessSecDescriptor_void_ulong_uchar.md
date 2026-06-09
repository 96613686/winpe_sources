# CreateBindToWorkerProcessSecDescriptor(void *,ulong,uchar *)

- ea: `0x1800c9bf0`
- end: `0x1800c9e18`
- name: `?CreateBindToWorkerProcessSecDescriptor@@YAJPEAXKPEAE@Z`
- size: `552`
- prototype: `__int64 __fastcall(PSID pSid, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c9b44`

## callees

- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c9bf0`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800c9ca0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800c9ca0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c9cea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c9d33`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c9cea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800c9d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9cf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d3d`

## pseudocode

```c
__int64 __fastcall CreateBindToWorkerProcessSecDescriptor(PSID pSid, __int64 a2, unsigned __int8 *a3)
{
  signed int v5; // ebx
  signed int v6; // eax
  signed int v7; // eax
  signed int LastError; // eax
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int64 v21; // [rsp+20h] [rbp-89h]
  __int128 v22; // [rsp+30h] [rbp-79h] BYREF
  _ACL pAcl[2]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v24; // [rsp+50h] [rbp-59h]
  __int128 v25; // [rsp+60h] [rbp-49h]
  __int128 v26; // [rsp+70h] [rbp-39h]
  __int128 v27; // [rsp+80h] [rbp-29h]
  __int128 v28; // [rsp+90h] [rbp-19h]
  __int128 v29; // [rsp+A0h] [rbp-9h]
  __int128 v30; // [rsp+B0h] [rbp+7h]
  __int128 v31; // [rsp+C0h] [rbp+17h]
  _OWORD v32[2]; // [rsp+D0h] [rbp+27h]

  HIDWORD(v21) = 0;
  memset_0(&v22, 0, 0xBCu);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 30, WPP_9477e0ba0f3c361da529f6aea3be386c_Traceguids);
  memset_0(a3, 0, 0xBCu);
  if ( pSid )
  {
    LOBYTE(v22) = 1;
    WORD1(v22) = -32764;
    *(_DWORD *)&pAcl[0].AclRevision = 20;
    if ( InitializeAcl((PACL)&pAcl[0].AceCount, 0xA8u, 2u) )
    {
      if ( AddAccessAllowedAce((PACL)&pAcl[0].AceCount, 2u, 0x80000000, pSid) )
      {
        if ( AddAccessAllowedAce((PACL)&pAcl[0].AceCount, 2u, 0x80000000, c_rgbAuthUserSid) )
        {
          v5 = 0;
          v9 = *(_OWORD *)&pAcl[0].AclRevision;
          *(_OWORD *)a3 = v22;
          v10 = v24;
          *((_OWORD *)a3 + 1) = v9;
          v11 = v25;
          *((_OWORD *)a3 + 2) = v10;
          v12 = v26;
          *((_OWORD *)a3 + 3) = v11;
          v13 = v27;
          *((_OWORD *)a3 + 4) = v12;
          v14 = v28;
          *((_OWORD *)a3 + 5) = v13;
          v15 = v29;
          *((_OWORD *)a3 + 6) = v14;
          v16 = v30;
          *((_OWORD *)a3 + 7) = v15;
          v17 = v31;
          *((_OWORD *)a3 + 8) = v16;
          v18 = v32[0];
          *((_OWORD *)a3 + 9) = v17;
          v19 = *(_OWORD *)((char *)v32 + 12);
          *((_OWORD *)a3 + 10) = v18;
          *(_OWORD *)(a3 + 172) = v19;
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          HIDWORD(v21) = 567;
          if ( v5 >= 0 )
            v5 = -2147418113;
        }
      }
      else
      {
        v7 = GetLastError();
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
        HIDWORD(v21) = 562;
        if ( v5 >= 0 )
          v5 = -2147418113;
      }
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      HIDWORD(v21) = 557;
      if ( v5 >= 0 )
        v5 = -2147418113;
    }
  }
  else
  {
    v5 = -2147024809;
    HIDWORD(v21) = 531;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 31, WPP_9477e0ba0f3c361da529f6aea3be386c_Traceguids, (unsigned int)v5, v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c9bf0  mov     [rsp-8+arg_8], rbx
0x1800c9bf5  mov     [rsp-8+arg_18], rdi
0x1800c9bfa  push    rbp
0x1800c9bfb  lea     rbp, [rsp-57h]
0x1800c9c00  sub     rsp, 100h
0x1800c9c07  mov     rax, cs:__security_cookie
0x1800c9c0e  xor     rax, rsp
0x1800c9c11  mov     [rbp+57h+var_10], rax
0x1800c9c15  mov     rdi, r8
0x1800c9c18  mov     [rsp+100h+var_DC], 0
0x1800c9c20  mov     rbx, rcx
0x1800c9c23  mov     r8d, 0BCh; Size
0x1800c9c29  lea     rcx, [rbp+57h+var_D0]; void *
0x1800c9c2d  xor     edx, edx; Val
0x1800c9c2f  call    memset_0
0x1800c9c34  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c9c3b  jz      short loc_1800C9C56
0x1800c9c3d  mov     edx, 1Eh
0x1800c9c42  lea     r8, WPP_9477e0ba0f3c361da529f6aea3be386c_Traceguids
0x1800c9c49  mov     ecx, 405h
0x1800c9c4e  mov     r9, rbx
0x1800c9c51  call    WPP_SF_q
0x1800c9c56  xor     edx, edx; Val
0x1800c9c58  mov     r8d, 0BCh; Size
0x1800c9c5e  mov     rcx, rdi; void *
0x1800c9c61  call    memset_0
0x1800c9c66  test    rbx, rbx
0x1800c9c69  jnz     short loc_1800C9C7D
0x1800c9c6b  mov     ebx, 80070057h
0x1800c9c70  mov     [rsp+100h+var_DC], 213h
0x1800c9c78  jmp     loc_1800C9DD3
0x1800c9c7d  mov     eax, 8004h
0x1800c9c82  mov     byte ptr [rbp+57h+var_D0], 1
0x1800c9c86  mov     edx, 0A8h; nAclLength
0x1800c9c8b  mov     word ptr [rbp+57h+var_D0+2], ax
0x1800c9c8f  mov     r8d, 2; dwAclRevision
0x1800c9c95  mov     dword ptr [rbp+57h+pAcl.AclRevision], 14h
0x1800c9c9c  lea     rcx, [rbp+57h+pAcl.AceCount]; pAcl
0x1800c9ca0  call    cs:__imp_InitializeAcl
0x1800c9ca6  test    eax, eax
0x1800c9ca8  jnz     short loc_1800C9CD6
0x1800c9caa  call    cs:__imp_GetLastError
0x1800c9cb0  mov     ebx, eax
0x1800c9cb2  test    eax, eax
0x1800c9cb4  jle     short loc_1800C9CBF
0x1800c9cb6  movzx   ebx, ax
0x1800c9cb9  or      ebx, 80070000h
0x1800c9cbf  test    ebx, ebx
0x1800c9cc1  mov     [rsp+100h+var_DC], 22Dh
0x1800c9cc9  mov     eax, 8000FFFFh
0x1800c9cce  cmovns  ebx, eax
0x1800c9cd1  jmp     loc_1800C9DD3
0x1800c9cd6  mov     r9, rbx; pSid
0x1800c9cd9  lea     rcx, [rbp+57h+pAcl.AceCount]; pAcl
0x1800c9cdd  mov     ebx, 80000000h
0x1800c9ce2  mov     edx, 2; dwAceRevision
0x1800c9ce7  mov     r8d, ebx; AccessMask
0x1800c9cea  call    cs:__imp_AddAccessAllowedAce
0x1800c9cf0  test    eax, eax
0x1800c9cf2  jnz     short loc_1800C9D20
0x1800c9cf4  call    cs:__imp_GetLastError
0x1800c9cfa  mov     ebx, eax
0x1800c9cfc  test    eax, eax
0x1800c9cfe  jle     short loc_1800C9D09
0x1800c9d00  movzx   ebx, ax
0x1800c9d03  or      ebx, 80070000h
0x1800c9d09  test    ebx, ebx
0x1800c9d0b  mov     [rsp+100h+var_DC], 232h
0x1800c9d13  mov     eax, 8000FFFFh
0x1800c9d18  cmovns  ebx, eax
0x1800c9d1b  jmp     loc_1800C9DD3
0x1800c9d20  lea     r9, c_rgbAuthUserSid; pSid
0x1800c9d27  mov     r8d, ebx; AccessMask
0x1800c9d2a  mov     edx, 2; dwAceRevision
0x1800c9d2f  lea     rcx, [rbp+57h+pAcl.AceCount]; pAcl
0x1800c9d33  call    cs:__imp_AddAccessAllowedAce
0x1800c9d39  test    eax, eax
0x1800c9d3b  jnz     short loc_1800C9D66
0x1800c9d3d  call    cs:__imp_GetLastError
0x1800c9d43  mov     ebx, eax
0x1800c9d45  test    eax, eax
0x1800c9d47  jle     short loc_1800C9D52
0x1800c9d49  movzx   ebx, ax
0x1800c9d4c  or      ebx, 80070000h
0x1800c9d52  test    ebx, ebx
0x1800c9d54  mov     [rsp+100h+var_DC], 237h
0x1800c9d5c  mov     eax, 8000FFFFh
0x1800c9d61  cmovns  ebx, eax
0x1800c9d64  jmp     short loc_1800C9DD3
0x1800c9d66  movaps  xmm0, [rbp+57h+var_D0]
0x1800c9d6a  xor     ebx, ebx
0x1800c9d6c  movaps  xmm1, xmmword ptr [rbp+57h+pAcl.AclRevision]
0x1800c9d70  movups  xmmword ptr [rdi], xmm0
0x1800c9d73  movaps  xmm0, [rbp+57h+var_B0]
0x1800c9d77  movups  xmmword ptr [rdi+10h], xmm1
0x1800c9d7b  movaps  xmm1, [rbp+57h+var_A0]
0x1800c9d7f  movups  xmmword ptr [rdi+20h], xmm0
0x1800c9d83  movaps  xmm0, [rbp+57h+var_90]
0x1800c9d87  movups  xmmword ptr [rdi+30h], xmm1
0x1800c9d8b  movaps  xmm1, [rbp+57h+var_80]
0x1800c9d8f  movups  xmmword ptr [rdi+40h], xmm0
0x1800c9d93  movaps  xmm0, [rbp+57h+var_70]
0x1800c9d97  movups  xmmword ptr [rdi+50h], xmm1
0x1800c9d9b  movaps  xmm1, [rbp+57h+var_60]
0x1800c9d9f  movups  xmmword ptr [rdi+60h], xmm0
0x1800c9da3  movaps  xmm0, [rbp+57h+var_50]
0x1800c9da7  movups  xmmword ptr [rdi+70h], xmm1
0x1800c9dab  movaps  xmm1, [rbp+57h+var_40]
0x1800c9daf  movups  xmmword ptr [rdi+80h], xmm0
0x1800c9db6  movaps  xmm0, xmmword ptr [rbp+57h+var_30]
0x1800c9dba  movups  xmmword ptr [rdi+90h], xmm1
0x1800c9dc1  movups  xmm1, xmmword ptr [rbp+57h+var_30+0Ch]
0x1800c9dc5  movups  xmmword ptr [rdi+0A0h], xmm0
0x1800c9dcc  movups  xmmword ptr [rdi+0ACh], xmm1
0x1800c9dd3  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c9dda  jz      short loc_1800C9DF5
0x1800c9ddc  mov     edx, 1Fh
0x1800c9de1  lea     r8, WPP_9477e0ba0f3c361da529f6aea3be386c_Traceguids
0x1800c9de8  mov     ecx, 405h
0x1800c9ded  mov     r9d, ebx
0x1800c9df0  call    WPP_SF_d
0x1800c9df5  mov     eax, ebx
0x1800c9df7  mov     rcx, [rbp+57h+var_10]
0x1800c9dfb  xor     rcx, rsp; StackCookie
0x1800c9dfe  call    __security_check_cookie
0x1800c9e03  lea     r11, [rsp+100h+var_s0]
0x1800c9e0b  mov     rbx, [r11+18h]
0x1800c9e0f  mov     rdi, [r11+28h]
0x1800c9e13  mov     rsp, r11
0x1800c9e16  pop     rbp
0x1800c9e17  retn
```
