# CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)

- ea: `0x180006de8`
- end: `0x180006f4d`
- name: `?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CAceList *this, struct CAce *const, char, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800064d4`

## callees

- `0x180006de8`
- `0x180009730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180006f21`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180006f21`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180006ede`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180006ede`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006e62`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006ead`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006e62`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006ead`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006e71`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180006e71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e2a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e2a`

## pseudocode

```c
__int64 __fastcall CAceList::_AddAllowedAceToAcl(CAceList *this, struct CAce *const a2, char a3, struct _ACL *a4)
{
  unsigned __int8 v6; // di
  char *v7; // rax
  char *v8; // r14
  signed int v9; // ebx
  void *v10; // rbx
  DWORD LengthSid; // eax
  signed int v12; // eax
  const void *v13; // rdi
  unsigned int v14; // ebx
  DWORD v15; // eax
  signed int LastError; // eax
  signed int v17; // eax

  if ( !a3 || *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
    v6 = *((_BYTE *)a2 + 1);
  else
    v6 = *((_BYTE *)a2 + 1) & 0xEF;
  if ( *(_BYTE *)a2 == 9 )
  {
    v7 = (char *)LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 1));
    v8 = v7;
    if ( v7 )
    {
      *v7 = *(_BYTE *)a2;
      v7[1] = v6;
      *((_WORD *)v7 + 1) = *((_WORD *)a2 + 1);
      *((_DWORD *)v7 + 1) = *((_DWORD *)a2 + 1);
      v10 = (void *)*((_QWORD *)a2 + 1);
      LengthSid = GetLengthSid(v10);
      if ( CopySid(LengthSid, v8 + 8, v10) )
      {
        if ( *((_DWORD *)a2 + 6) )
        {
          v13 = (const void *)*((_QWORD *)a2 + 2);
          v14 = *((_DWORD *)a2 + 6);
          v15 = GetLengthSid(*((PSID *)a2 + 1));
          memcpy_0(&v8[v15 + 8], v13, v14);
        }
        v9 = 0;
        if ( !AddAce(a4, 2u, 0xFFFFFFFF, v8, *((unsigned __int16 *)a2 + 1)) )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        v12 = GetLastError();
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2147467259;
      }
      LocalFree(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v9 = 0;
    if ( !AddAccessAllowedAceEx(a4, 2u, v6, *((_DWORD *)a2 + 1), *((PSID *)a2 + 1)) )
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        return (unsigned __int16)v17 | 0x80070000;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006de8  push    rbx
0x180006dea  push    rbp
0x180006deb  push    rsi
0x180006dec  push    rdi
0x180006ded  push    r14
0x180006def  sub     rsp, 30h
0x180006df3  mov     rbp, r9
0x180006df6  mov     rsi, rdx
0x180006df9  test    r8b, r8b
0x180006dfc  jz      short loc_180006E14
0x180006dfe  cmp     dword ptr [rcx+18h], 0
0x180006e02  jnz     short loc_180006E14
0x180006e04  cmp     dword ptr [rcx+1Ch], 0
0x180006e08  jnz     short loc_180006E14
0x180006e0a  mov     dil, [rdx+1]
0x180006e0e  and     dil, 0EFh
0x180006e12  jmp     short loc_180006E18
0x180006e14  mov     dil, [rdx+1]
0x180006e18  cmp     byte ptr [rdx], 9
0x180006e1b  jnz     loc_180006F08
0x180006e21  movzx   edx, word ptr [rdx+2]; uBytes
0x180006e25  mov     ecx, 40h ; '@'; uFlags
0x180006e2a  call    cs:__imp_LocalAlloc
0x180006e30  mov     r14, rax
0x180006e33  test    rax, rax
0x180006e36  jnz     short loc_180006E42
0x180006e38  mov     ebx, 8007000Eh
0x180006e3d  jmp     loc_180006F40
0x180006e42  mov     al, [rsi]
0x180006e44  mov     [r14], al
0x180006e47  mov     [r14+1], dil
0x180006e4b  movzx   eax, word ptr [rsi+2]
0x180006e4f  mov     [r14+2], ax
0x180006e54  mov     eax, [rsi+4]
0x180006e57  mov     [r14+4], eax
0x180006e5b  mov     rbx, [rsi+8]
0x180006e5f  mov     rcx, rbx; pSid
0x180006e62  call    cs:__imp_GetLengthSid
0x180006e68  lea     rdx, [r14+8]; pDestinationSid
0x180006e6c  mov     r8, rbx; pSourceSid
0x180006e6f  mov     ecx, eax; nDestinationSidLength
0x180006e71  call    cs:__imp_CopySid
0x180006e77  test    eax, eax
0x180006e79  jnz     short loc_180006E9C
0x180006e7b  call    cs:__imp_GetLastError
0x180006e81  mov     ebx, eax
0x180006e83  test    eax, eax
0x180006e85  jle     short loc_180006E90
0x180006e87  movzx   ebx, ax
0x180006e8a  or      ebx, 80070000h
0x180006e90  test    ebx, ebx
0x180006e92  mov     eax, 80004005h
0x180006e97  cmovns  ebx, eax
0x180006e9a  jmp     short loc_180006EFD
0x180006e9c  cmp     dword ptr [rsi+18h], 0
0x180006ea0  jz      short loc_180006EC7
0x180006ea2  mov     rcx, [rsi+8]; pSid
0x180006ea6  mov     rdi, [rsi+10h]
0x180006eaa  mov     ebx, [rsi+18h]
0x180006ead  call    cs:__imp_GetLengthSid
0x180006eb3  mov     ecx, eax
0x180006eb5  mov     r8d, ebx; Size
0x180006eb8  add     rcx, 8
0x180006ebc  mov     rdx, rdi; Src
0x180006ebf  add     rcx, r14; void *
0x180006ec2  call    memcpy_0
0x180006ec7  movzx   eax, word ptr [rsi+2]
0x180006ecb  xor     ebx, ebx
0x180006ecd  mov     r9, r14; pAceList
0x180006ed0  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x180006ed4  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180006ed8  mov     rcx, rbp; pAcl
0x180006edb  lea     edx, [rbx+2]; dwAceRevision
0x180006ede  call    cs:__imp_AddAce
0x180006ee4  test    eax, eax
0x180006ee6  jnz     short loc_180006EFD
0x180006ee8  call    cs:__imp_GetLastError
0x180006eee  mov     ebx, eax
0x180006ef0  test    eax, eax
0x180006ef2  jle     short loc_180006EFD
0x180006ef4  movzx   ebx, ax
0x180006ef7  or      ebx, 80070000h
0x180006efd  mov     rcx, r14; hMem
0x180006f00  call    cs:__imp_LocalFree
0x180006f06  jmp     short loc_180006F40
0x180006f08  mov     rax, [rdx+8]
0x180006f0c  xor     ebx, ebx
0x180006f0e  mov     r9d, [rdx+4]; AccessMask
0x180006f12  mov     rcx, rbp; pAcl
0x180006f15  movzx   r8d, dil; AceFlags
0x180006f19  mov     qword ptr [rsp+58h+nAceListLength], rax; pSid
0x180006f1e  lea     edx, [rbx+2]; dwAceRevision
0x180006f21  call    cs:__imp_AddAccessAllowedAceEx
0x180006f27  test    eax, eax
0x180006f29  jnz     short loc_180006F40
0x180006f2b  call    cs:__imp_GetLastError
0x180006f31  mov     ebx, eax
0x180006f33  test    eax, eax
0x180006f35  jle     short loc_180006F40
0x180006f37  movzx   ebx, ax
0x180006f3a  or      ebx, 80070000h
0x180006f40  mov     eax, ebx
0x180006f42  add     rsp, 30h
0x180006f46  pop     r14
0x180006f48  pop     rdi
0x180006f49  pop     rsi
0x180006f4a  pop     rbp
0x180006f4b  pop     rbx
0x180006f4c  retn
```
