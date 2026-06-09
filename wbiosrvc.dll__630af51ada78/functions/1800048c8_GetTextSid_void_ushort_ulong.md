# GetTextSid(void *,ushort *,ulong)

- ea: `0x1800048c8`
- end: `0x180004a64`
- name: `?GetTextSid@@YAJPEAXPEAGK@Z`
- size: `412`
- prototype: `__int64 __fastcall(PSID pSid, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004728`
- `0x180061900`
- `0x1800bc1d0`
- `0x1800bca60`
- `0x1800bcd80`

## callees

- `0x1800048c8`
- `0x180004a6c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800048ff`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800048ff`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800048f3`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800048f3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800048df`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800048df`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800049dc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800049dc`

## pseudocode

```c
__int64 __fastcall GetTextSid(PSID pSid, unsigned __int16 *a2)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v5; // r14d
  __int64 v7; // rcx
  __int64 v8; // rbx
  DWORD i; // esi
  PDWORD SidSubAuthority; // rax

  if ( !IsValidSid(pSid) )
    return 2147942487LL;
  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  v5 = *GetSidSubAuthorityCount(pSid);
  if ( 12 * v5 + 28 > 0x80 )
    return 2147942522LL;
  if ( StringCchPrintfW(a2, 0x80u, L"S-%lu-", 1) )
    return 2147942522LL;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( *(_WORD *)SidIdentifierAuthority->Value
     ? StringCchPrintfW(
         &a2[v7],
         128 - v7,
         L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
         SidIdentifierAuthority->Value[0],
         SidIdentifierAuthority->Value[1],
         SidIdentifierAuthority->Value[2],
         SidIdentifierAuthority->Value[3],
         SidIdentifierAuthority->Value[4],
         SidIdentifierAuthority->Value[5])
     : StringCchPrintfW(
         &a2[v7],
         128 - v7,
         L"%lu",
         SidIdentifierAuthority->Value[5]
       + (SidIdentifierAuthority->Value[4] << 8)
       + (SidIdentifierAuthority->Value[3] << 16)
       + (SidIdentifierAuthority->Value[2] << 24)) )
  {
    return 2147942522LL;
  }
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  for ( i = 0; i < v5; ++i )
  {
    SidSubAuthority = GetSidSubAuthority(pSid, i);
    if ( StringCchPrintfW(&a2[v8], 128 - v8, L"-%lu", *SidSubAuthority) )
      return 2147942522LL;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  return 0;
}

```

## disassembly

```asm
0x1800048c8  push    rbx
0x1800048ca  push    rbp
0x1800048cb  push    rsi
0x1800048cc  push    rdi
0x1800048cd  push    r12
0x1800048cf  push    r13
0x1800048d1  push    r14
0x1800048d3  push    r15
0x1800048d5  sub     rsp, 58h
0x1800048d9  mov     rdi, rdx
0x1800048dc  mov     rbp, rcx
0x1800048df  call    cs:__imp_IsValidSid
0x1800048e5  xor     r15d, r15d
0x1800048e8  test    eax, eax
0x1800048ea  jz      loc_180004A1B
0x1800048f0  mov     rcx, rbp; pSid
0x1800048f3  call    cs:__imp_GetSidIdentifierAuthority
0x1800048f9  mov     rcx, rbp; pSid
0x1800048fc  mov     rbx, rax
0x1800048ff  call    cs:__imp_GetSidSubAuthorityCount
0x180004905  mov     r13d, 80h
0x18000490b  movzx   r14d, byte ptr [rax]
0x18000490f  lea     ecx, [r14+r14*2]
0x180004913  lea     ecx, ds:1Ch[rcx*4]
0x18000491a  cmp     ecx, r13d
0x18000491d  jbe     short loc_180004935
0x18000491f  mov     eax, 8007007Ah
0x180004924  add     rsp, 58h
0x180004928  pop     r15
0x18000492a  pop     r14
0x18000492c  pop     r13
0x18000492e  pop     r12
0x180004930  pop     rdi
0x180004931  pop     rsi
0x180004932  pop     rbp
0x180004933  pop     rbx
0x180004934  retn
0x180004935  mov     r9d, 1
0x18000493b  lea     r8, aSLu; "S-%lu-"
0x180004942  mov     rdx, r13; unsigned __int64
0x180004945  mov     rcx, rdi; unsigned __int16 *
0x180004948  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000494d  test    eax, eax
0x18000494f  jnz     short loc_18000491F
0x180004951  or      r12, 0FFFFFFFFFFFFFFFFh
0x180004955  mov     rcx, r12
0x180004958  inc     rcx
0x18000495b  cmp     [rdi+rcx*2], r15w
0x180004960  jnz     short loc_180004958
0x180004962  movzx   edx, byte ptr [rbx]
0x180004965  test    dl, dl
0x180004967  jnz     short loc_180004973
0x180004969  cmp     [rbx+1], r15b
0x18000496d  jz      loc_180004A25
0x180004973  movzx   r8d, byte ptr [rbx+4]
0x180004978  mov     r9d, edx
0x18000497b  movzx   eax, byte ptr [rbx+5]
0x18000497f  mov     rdx, r13
0x180004982  movzx   r10d, byte ptr [rbx+3]
0x180004987  sub     rdx, rcx; unsigned __int64
0x18000498a  movzx   r11d, byte ptr [rbx+2]
0x18000498f  lea     rcx, [rdi+rcx*2]; unsigned __int16 *
0x180004993  movzx   ebx, byte ptr [rbx+1]
0x180004997  mov     [rsp+98h+var_58], eax
0x18000499b  mov     [rsp+98h+var_60], r8d
0x1800049a0  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x1800049a7  mov     [rsp+98h+var_68], r10d
0x1800049ac  mov     [rsp+98h+var_70], r11d
0x1800049b1  mov     [rsp+98h+var_78], ebx
0x1800049b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800049ba  test    eax, eax
0x1800049bc  jnz     loc_18000491F
0x1800049c2  mov     rbx, r12
0x1800049c5  inc     rbx
0x1800049c8  cmp     [rdi+rbx*2], r15w
0x1800049cd  jnz     short loc_1800049C5
0x1800049cf  mov     esi, r15d
0x1800049d2  cmp     esi, r14d
0x1800049d5  jnb     short loc_180004A14
0x1800049d7  mov     edx, esi; nSubAuthority
0x1800049d9  mov     rcx, rbp; pSid
0x1800049dc  call    cs:__imp_GetSidSubAuthority
0x1800049e2  mov     rdx, r13
0x1800049e5  lea     rcx, [rdi+rbx*2]; unsigned __int16 *
0x1800049e9  sub     rdx, rbx; unsigned __int64
0x1800049ec  lea     r8, aLu; "-%lu"
0x1800049f3  mov     r9d, [rax]
0x1800049f6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800049fb  test    eax, eax
0x1800049fd  jnz     loc_18000491F
0x180004a03  mov     rbx, r12
0x180004a06  inc     rbx
0x180004a09  cmp     [rdi+rbx*2], r15w
0x180004a0e  jnz     short loc_180004A06
0x180004a10  inc     esi
0x180004a12  jmp     short loc_1800049D2
0x180004a14  xor     eax, eax
0x180004a16  jmp     loc_180004924
0x180004a1b  mov     eax, 80070057h
0x180004a20  jmp     loc_180004924
0x180004a25  movzx   r9d, byte ptr [rbx+2]
0x180004a2a  lea     r8, aLu_0; "%lu"
0x180004a31  movzx   eax, byte ptr [rbx+3]
0x180004a35  mov     rdx, r13
0x180004a38  shl     eax, 10h
0x180004a3b  sub     rdx, rcx; unsigned __int64
0x180004a3e  shl     r9d, 18h
0x180004a42  lea     rcx, [rdi+rcx*2]; unsigned __int16 *
0x180004a46  add     r9d, eax
0x180004a49  movzx   eax, byte ptr [rbx+4]
0x180004a4d  shl     eax, 8
0x180004a50  add     r9d, eax
0x180004a53  movzx   eax, byte ptr [rbx+5]
0x180004a57  add     r9d, eax
0x180004a5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004a5f  jmp     loc_1800049BA
```
