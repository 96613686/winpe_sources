# CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)

- ea: `0x1800dc1d4`
- end: `0x1800dc365`
- name: `?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z`
- size: `401`
- prototype: `int(CAceList *__hidden this, struct CAce *const, bool, struct _ACL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dbbf8`

## callees

- `0x18003d244`
- `0x18005a1b6`
- `0x1800dc1d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc33a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dc303`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc215`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dc215`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dc256`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dc29d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dc256`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800dc29d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800dc26b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800dc26b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800dc32a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800dc32a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800dc2d5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800dc2d5`

## pseudocode

```c
__int64 __fastcall CAceList::_AddAllowedAceToAcl(CAceList *this, struct CAce *const a2, char a3, struct _ACL *a4)
{
  unsigned __int8 v6; // bl
  char *v7; // rax
  char *v8; // r15
  unsigned int Error; // esi
  void *v10; // rbx
  DWORD LengthSid; // eax
  const void *v12; // rdi
  unsigned int v13; // ebx
  DWORD v14; // eax
  signed int LastError; // eax
  signed int v16; // eax

  if ( !a3 || *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
    v6 = *((_BYTE *)a2 + 1);
  else
    v6 = *((_BYTE *)a2 + 1) & 0xEF;
  if ( *(_BYTE *)a2 == 9 )
  {
    v7 = (char *)LocalAlloc(0x40u, *((unsigned __int16 *)a2 + 1));
    v8 = v7;
    if ( !v7 )
      return (unsigned int)-2147024882;
    *v7 = *(_BYTE *)a2;
    v7[1] = v6;
    *((_WORD *)v7 + 1) = *((_WORD *)a2 + 1);
    *((_DWORD *)v7 + 1) = *((_DWORD *)a2 + 1);
    v10 = (void *)*((_QWORD *)a2 + 1);
    LengthSid = GetLengthSid(v10);
    if ( CopySid(LengthSid, v8 + 8, v10) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( (Error & 0x80000000) != 0 )
      {
LABEL_17:
        LocalFree(v8);
        return Error;
      }
    }
    if ( *((_DWORD *)a2 + 6) )
    {
      v12 = (const void *)*((_QWORD *)a2 + 2);
      v13 = *((_DWORD *)a2 + 6);
      v14 = GetLengthSid(*((PSID *)a2 + 1));
      memcpy_0(&v8[v14 + 8], v12, v13);
    }
    if ( !AddAce(a4, 2u, 0xFFFFFFFF, v8, *((unsigned __int16 *)a2 + 1)) )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
    }
    goto LABEL_17;
  }
  Error = 0;
  if ( !AddAccessAllowedAceEx(a4, 2u, v6, *((_DWORD *)a2 + 1), *((PSID *)a2 + 1)) )
  {
    v16 = GetLastError();
    Error = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return Error;
}

```

## disassembly

```asm
0x1800dc1d4  push    rbx
0x1800dc1d6  push    rbp
0x1800dc1d7  push    rsi
0x1800dc1d8  push    rdi
0x1800dc1d9  push    r14
0x1800dc1db  push    r15
0x1800dc1dd  sub     rsp, 38h
0x1800dc1e1  mov     rbp, r9
0x1800dc1e4  mov     r14, rdx
0x1800dc1e7  test    r8b, r8b
0x1800dc1ea  jz      short loc_1800DC200
0x1800dc1ec  cmp     dword ptr [rcx+18h], 0
0x1800dc1f0  jnz     short loc_1800DC200
0x1800dc1f2  cmp     dword ptr [rcx+1Ch], 0
0x1800dc1f6  jnz     short loc_1800DC200
0x1800dc1f8  mov     bl, [rdx+1]
0x1800dc1fb  and     bl, 0EFh
0x1800dc1fe  jmp     short loc_1800DC203
0x1800dc200  mov     bl, [rdx+1]
0x1800dc203  cmp     byte ptr [rdx], 9
0x1800dc206  jnz     loc_1800DC311
0x1800dc20c  movzx   edx, word ptr [rdx+2]; uBytes
0x1800dc210  mov     ecx, 40h ; '@'; uFlags
0x1800dc215  call    cs:__imp_LocalAlloc
0x1800dc21c  nop     dword ptr [rax+rax+00h]
0x1800dc221  mov     r15, rax
0x1800dc224  test    rax, rax
0x1800dc227  jnz     short loc_1800DC233
0x1800dc229  mov     esi, 8007000Eh
0x1800dc22e  jmp     loc_1800DC355
0x1800dc233  mov     al, [r14]
0x1800dc236  mov     [r15], al
0x1800dc239  mov     [r15+1], bl
0x1800dc23d  movzx   eax, word ptr [r14+2]
0x1800dc242  mov     [r15+2], ax
0x1800dc247  mov     eax, [r14+4]
0x1800dc24b  mov     [r15+4], eax
0x1800dc24f  mov     rbx, [r14+8]
0x1800dc253  mov     rcx, rbx; pSid
0x1800dc256  call    cs:__imp_GetLengthSid
0x1800dc25d  nop     dword ptr [rax+rax+00h]
0x1800dc262  lea     rdx, [r15+8]; pDestinationSid
0x1800dc266  mov     r8, rbx; pSourceSid
0x1800dc269  mov     ecx, eax; nDestinationSidLength
0x1800dc26b  call    cs:__imp_CopySid
0x1800dc272  nop     dword ptr [rax+rax+00h]
0x1800dc277  test    eax, eax
0x1800dc279  jz      short loc_1800DC27F
0x1800dc27b  xor     esi, esi
0x1800dc27d  jmp     short loc_1800DC28A
0x1800dc27f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800dc284  mov     esi, eax
0x1800dc286  test    eax, eax
0x1800dc288  js      short loc_1800DC300
0x1800dc28a  cmp     dword ptr [r14+18h], 0
0x1800dc28f  jz      short loc_1800DC2BD
0x1800dc291  mov     rcx, [r14+8]; pSid
0x1800dc295  mov     rdi, [r14+10h]
0x1800dc299  mov     ebx, [r14+18h]
0x1800dc29d  call    cs:__imp_GetLengthSid
0x1800dc2a4  nop     dword ptr [rax+rax+00h]
0x1800dc2a9  mov     ecx, eax
0x1800dc2ab  mov     r8d, ebx; Size
0x1800dc2ae  add     rcx, 8
0x1800dc2b2  mov     rdx, rdi; Src
0x1800dc2b5  add     rcx, r15; void *
0x1800dc2b8  call    memcpy_0
0x1800dc2bd  movzx   eax, word ptr [r14+2]
0x1800dc2c2  mov     r9, r15; pAceList
0x1800dc2c5  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800dc2c9  mov     [rsp+68h+nAceListLength], eax; nAceListLength
0x1800dc2cd  mov     edx, 2; dwAceRevision
0x1800dc2d2  mov     rcx, rbp; pAcl
0x1800dc2d5  call    cs:__imp_AddAce
0x1800dc2dc  nop     dword ptr [rax+rax+00h]
0x1800dc2e1  test    eax, eax
0x1800dc2e3  jnz     short loc_1800DC300
0x1800dc2e5  call    cs:__imp_GetLastError
0x1800dc2ec  nop     dword ptr [rax+rax+00h]
0x1800dc2f1  mov     esi, eax
0x1800dc2f3  test    eax, eax
0x1800dc2f5  jle     short loc_1800DC300
0x1800dc2f7  movzx   esi, ax
0x1800dc2fa  or      esi, 80070000h
0x1800dc300  mov     rcx, r15; hMem
0x1800dc303  call    cs:__imp_LocalFree
0x1800dc30a  nop     dword ptr [rax+rax+00h]
0x1800dc30f  jmp     short loc_1800DC355
0x1800dc311  mov     rax, [rdx+8]
0x1800dc315  xor     esi, esi
0x1800dc317  mov     r9d, [rdx+4]; AccessMask
0x1800dc31b  mov     rcx, rbp; pAcl
0x1800dc31e  movzx   r8d, bl; AceFlags
0x1800dc322  mov     qword ptr [rsp+68h+nAceListLength], rax; pSid
0x1800dc327  lea     edx, [rsi+2]; dwAceRevision
0x1800dc32a  call    cs:__imp_AddAccessAllowedAceEx
0x1800dc331  nop     dword ptr [rax+rax+00h]
0x1800dc336  test    eax, eax
0x1800dc338  jnz     short loc_1800DC355
0x1800dc33a  call    cs:__imp_GetLastError
0x1800dc341  nop     dword ptr [rax+rax+00h]
0x1800dc346  mov     esi, eax
0x1800dc348  test    eax, eax
0x1800dc34a  jle     short loc_1800DC355
0x1800dc34c  movzx   esi, ax
0x1800dc34f  or      esi, 80070000h
0x1800dc355  mov     eax, esi
0x1800dc357  add     rsp, 38h
0x1800dc35b  pop     r15
0x1800dc35d  pop     r14
0x1800dc35f  pop     rdi
0x1800dc360  pop     rsi
0x1800dc361  pop     rbp
0x1800dc362  pop     rbx
0x1800dc363  retn
```
