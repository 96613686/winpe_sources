# CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)

- ea: `0x180070dac`
- end: `0x180070f11`
- name: `?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CAceList *this, struct CAce *const, char, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800709b0`

## callees

- `0x180070dac`
- `0x180077272`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070eef`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180070ee5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180070ee5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180070e26`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180070e71`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180070e26`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180070e71`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180070ea2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180070ea2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180070e35`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180070e35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070dee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070dee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070ec4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070ec4`

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
0x180070dac  push    rbx
0x180070dae  push    rbp
0x180070daf  push    rsi
0x180070db0  push    rdi
0x180070db1  push    r14
0x180070db3  sub     rsp, 30h
0x180070db7  mov     rbp, r9
0x180070dba  mov     rsi, rdx
0x180070dbd  test    r8b, r8b
0x180070dc0  jz      short loc_180070DD8
0x180070dc2  cmp     dword ptr [rcx+18h], 0
0x180070dc6  jnz     short loc_180070DD8
0x180070dc8  cmp     dword ptr [rcx+1Ch], 0
0x180070dcc  jnz     short loc_180070DD8
0x180070dce  mov     dil, [rdx+1]
0x180070dd2  and     dil, 0EFh
0x180070dd6  jmp     short loc_180070DDC
0x180070dd8  mov     dil, [rdx+1]
0x180070ddc  cmp     byte ptr [rdx], 9
0x180070ddf  jnz     loc_180070ECC
0x180070de5  movzx   edx, word ptr [rdx+2]; uBytes
0x180070de9  mov     ecx, 40h ; '@'; uFlags
0x180070dee  call    cs:__imp_LocalAlloc
0x180070df4  mov     r14, rax
0x180070df7  test    rax, rax
0x180070dfa  jnz     short loc_180070E06
0x180070dfc  mov     ebx, 8007000Eh
0x180070e01  jmp     loc_180070F04
0x180070e06  mov     al, [rsi]
0x180070e08  mov     [r14], al
0x180070e0b  mov     [r14+1], dil
0x180070e0f  movzx   eax, word ptr [rsi+2]
0x180070e13  mov     [r14+2], ax
0x180070e18  mov     eax, [rsi+4]
0x180070e1b  mov     [r14+4], eax
0x180070e1f  mov     rbx, [rsi+8]
0x180070e23  mov     rcx, rbx; pSid
0x180070e26  call    cs:__imp_GetLengthSid
0x180070e2c  lea     rdx, [r14+8]; pDestinationSid
0x180070e30  mov     r8, rbx; pSourceSid
0x180070e33  mov     ecx, eax; nDestinationSidLength
0x180070e35  call    cs:__imp_CopySid
0x180070e3b  test    eax, eax
0x180070e3d  jnz     short loc_180070E60
0x180070e3f  call    cs:__imp_GetLastError
0x180070e45  mov     ebx, eax
0x180070e47  test    eax, eax
0x180070e49  jle     short loc_180070E54
0x180070e4b  movzx   ebx, ax
0x180070e4e  or      ebx, 80070000h
0x180070e54  test    ebx, ebx
0x180070e56  mov     eax, 80004005h
0x180070e5b  cmovns  ebx, eax
0x180070e5e  jmp     short loc_180070EC1
0x180070e60  cmp     dword ptr [rsi+18h], 0
0x180070e64  jz      short loc_180070E8B
0x180070e66  mov     rcx, [rsi+8]; pSid
0x180070e6a  mov     rdi, [rsi+10h]
0x180070e6e  mov     ebx, [rsi+18h]
0x180070e71  call    cs:__imp_GetLengthSid
0x180070e77  mov     ecx, eax
0x180070e79  mov     r8d, ebx; Size
0x180070e7c  add     rcx, 8
0x180070e80  mov     rdx, rdi; Src
0x180070e83  add     rcx, r14; void *
0x180070e86  call    memcpy_0
0x180070e8b  movzx   eax, word ptr [rsi+2]
0x180070e8f  xor     ebx, ebx
0x180070e91  mov     r9, r14; pAceList
0x180070e94  mov     [rsp+58h+nAceListLength], eax; nAceListLength
0x180070e98  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180070e9c  mov     rcx, rbp; pAcl
0x180070e9f  lea     edx, [rbx+2]; dwAceRevision
0x180070ea2  call    cs:__imp_AddAce
0x180070ea8  test    eax, eax
0x180070eaa  jnz     short loc_180070EC1
0x180070eac  call    cs:__imp_GetLastError
0x180070eb2  mov     ebx, eax
0x180070eb4  test    eax, eax
0x180070eb6  jle     short loc_180070EC1
0x180070eb8  movzx   ebx, ax
0x180070ebb  or      ebx, 80070000h
0x180070ec1  mov     rcx, r14; hMem
0x180070ec4  call    cs:__imp_LocalFree
0x180070eca  jmp     short loc_180070F04
0x180070ecc  mov     rax, [rdx+8]
0x180070ed0  xor     ebx, ebx
0x180070ed2  mov     r9d, [rdx+4]; AccessMask
0x180070ed6  mov     rcx, rbp; pAcl
0x180070ed9  movzx   r8d, dil; AceFlags
0x180070edd  mov     qword ptr [rsp+58h+nAceListLength], rax; pSid
0x180070ee2  lea     edx, [rbx+2]; dwAceRevision
0x180070ee5  call    cs:__imp_AddAccessAllowedAceEx
0x180070eeb  test    eax, eax
0x180070eed  jnz     short loc_180070F04
0x180070eef  call    cs:__imp_GetLastError
0x180070ef5  mov     ebx, eax
0x180070ef7  test    eax, eax
0x180070ef9  jle     short loc_180070F04
0x180070efb  movzx   ebx, ax
0x180070efe  or      ebx, 80070000h
0x180070f04  mov     eax, ebx
0x180070f06  add     rsp, 30h
0x180070f0a  pop     r14
0x180070f0c  pop     rdi
0x180070f0d  pop     rsi
0x180070f0e  pop     rbp
0x180070f0f  pop     rbx
0x180070f10  retn
```
