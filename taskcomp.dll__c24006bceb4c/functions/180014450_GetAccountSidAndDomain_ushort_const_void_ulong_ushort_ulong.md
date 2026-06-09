# GetAccountSidAndDomain(ushort const *,void *,ulong,ushort *,ulong)

- ea: `0x180014450`
- end: `0x180014526`
- name: `?GetAccountSidAndDomain@@YAJPEBGPEAXKPEAGK@Z`
- size: `214`
- prototype: `signed int __fastcall(const unsigned __int16 *, void *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015280`

## callees

- `0x180014450`
- `0x180014dbc`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800144af`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800144af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b9`

## pseudocode

```c
signed int __fastcall GetAccountSidAndDomain(const unsigned __int16 *a1, void *a2, __int64 a3, unsigned __int16 *a4)
{
  signed int result; // eax
  enum _SID_NAME_USE v5; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v6; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v7; // [rsp+50h] [rbp-20h] BYREF
  _DWORD pSourceSid[4]; // [rsp+58h] [rbp-18h] BYREF

  v6 = 16;
  v7 = 68;
  if ( !a1 || !a2 || !a4 )
    return -2147024809;
  if ( *a1 )
  {
    v5 = 0;
    return LookupAccountNameWrap(a1, a1, a2, &v7, a4, &v6, &v5) == 0 ? 0x80041310 : 0;
  }
  else
  {
    pSourceSid[0] = 257;
    pSourceSid[1] = 83886080;
    pSourceSid[2] = 18;
    if ( CopySid(0x44u, a2, pSourceSid) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014450  mov     [rsp-8+arg_10], rbx
0x180014455  push    rbp
0x180014456  mov     rbp, rsp
0x180014459  sub     rsp, 70h
0x18001445d  mov     rax, cs:__security_cookie
0x180014464  xor     rax, rsp
0x180014467  mov     [rbp+var_8], rax
0x18001446b  xor     ebx, ebx
0x18001446d  mov     [rbp+var_28], 10h
0x180014474  mov     eax, 44h ; 'D'
0x180014479  mov     [rbp+var_20], eax
0x18001447c  test    rcx, rcx
0x18001447f  jz      loc_180014507
0x180014485  test    rdx, rdx
0x180014488  jz      short loc_180014507
0x18001448a  test    r9, r9
0x18001448d  jz      short loc_180014507
0x18001448f  cmp     [rcx], bx
0x180014492  jnz     short loc_1800144D1
0x180014494  lea     r8, [rbp+pSourceSid]; pSourceSid
0x180014498  mov     [rbp+pSourceSid], 101h
0x18001449f  mov     ecx, eax; nDestinationSidLength
0x1800144a1  mov     [rbp+var_14], 5000000h
0x1800144a8  mov     [rbp+var_10], 12h
0x1800144af  call    cs:__imp_CopySid
0x1800144b5  test    eax, eax
0x1800144b7  jnz     short loc_1800144CD
0x1800144b9  call    cs:__imp_GetLastError
0x1800144bf  test    eax, eax
0x1800144c1  jle     short loc_18001450C
0x1800144c3  movzx   eax, ax
0x1800144c6  or      eax, 80070000h
0x1800144cb  jmp     short loc_18001450C
0x1800144cd  xor     eax, eax
0x1800144cf  jmp     short loc_18001450C
0x1800144d1  lea     rax, [rbp+var_30]
0x1800144d5  mov     [rbp+var_30], ebx
0x1800144d8  mov     [rsp+70h+var_40], rax; enum _SID_NAME_USE *
0x1800144dd  mov     r8, rdx; void *
0x1800144e0  lea     rax, [rbp+var_28]
0x1800144e4  mov     rdx, rcx; unsigned __int16 *
0x1800144e7  mov     [rsp+70h+var_48], rax; unsigned int *
0x1800144ec  mov     [rsp+70h+var_50], r9; unsigned __int16 *
0x1800144f1  lea     r9, [rbp+var_20]; unsigned int *
0x1800144f5  call    ?LookupAccountNameWrap@@YAHPEBG0PEAXPEAKPEAG2PEAW4_SID_NAME_USE@@@Z; LookupAccountNameWrap(ushort const *,ushort const *,void *,ulong *,ushort *,ulong *,_SID_NAME_USE *)
0x1800144fa  neg     eax
0x1800144fc  sbb     eax, eax
0x1800144fe  not     eax
0x180014500  and     eax, 80041310h
0x180014505  jmp     short loc_18001450C
0x180014507  mov     eax, 80070057h
0x18001450c  mov     rcx, [rbp+var_8]
0x180014510  xor     rcx, rsp; StackCookie
0x180014513  call    __security_check_cookie
0x180014518  mov     rbx, [rsp+70h+arg_10]
0x180014520  add     rsp, 70h
0x180014524  pop     rbp
0x180014525  retn
```
