# GetAccountSidAndDomain(ushort const *,void *,ulong,ushort *,ulong)

- ea: `0x1800150c4`
- end: `0x1800151af`
- name: `?GetAccountSidAndDomain@@YAJPEBGPEAXKPEAGK@Z`
- size: `235`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016040`

## callees

- `0x1800150c4`
- `0x180015b10`
- `0x180030700`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001512b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001512b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001513b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001513b`

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
0x1800150c4  mov     [rsp-8+arg_10], rbx
0x1800150c9  push    rbp
0x1800150ca  mov     rbp, rsp
0x1800150cd  sub     rsp, 70h
0x1800150d1  mov     rax, cs:__security_cookie
0x1800150d8  xor     rax, rsp
0x1800150db  mov     [rbp+var_8], rax
0x1800150df  xor     ebx, ebx
0x1800150e1  mov     [rbp+var_28], 10h
0x1800150e8  mov     eax, 44h ; 'D'
0x1800150ed  mov     [rbp+var_20], eax
0x1800150f0  test    rcx, rcx
0x1800150f3  jz      loc_18001518F
0x1800150f9  test    rdx, rdx
0x1800150fc  jz      loc_18001518F
0x180015102  test    r9, r9
0x180015105  jz      loc_18001518F
0x18001510b  cmp     [rcx], bx
0x18001510e  jnz     short loc_180015159
0x180015110  lea     r8, [rbp+pSourceSid]; pSourceSid
0x180015114  mov     [rbp+pSourceSid], 101h
0x18001511b  mov     ecx, eax; nDestinationSidLength
0x18001511d  mov     [rbp+var_14], 5000000h
0x180015124  mov     [rbp+var_10], 12h
0x18001512b  call    cs:__imp_CopySid
0x180015132  nop     dword ptr [rax+rax+00h]
0x180015137  test    eax, eax
0x180015139  jnz     short loc_180015155
0x18001513b  call    cs:__imp_GetLastError
0x180015142  nop     dword ptr [rax+rax+00h]
0x180015147  test    eax, eax
0x180015149  jle     short loc_180015194
0x18001514b  movzx   eax, ax
0x18001514e  or      eax, 80070000h
0x180015153  jmp     short loc_180015194
0x180015155  xor     eax, eax
0x180015157  jmp     short loc_180015194
0x180015159  lea     rax, [rbp+var_30]
0x18001515d  mov     [rbp+var_30], ebx
0x180015160  mov     [rsp+70h+var_40], rax; enum _SID_NAME_USE *
0x180015165  mov     r8, rdx; void *
0x180015168  lea     rax, [rbp+var_28]
0x18001516c  mov     rdx, rcx; unsigned __int16 *
0x18001516f  mov     [rsp+70h+var_48], rax; unsigned int *
0x180015174  mov     [rsp+70h+var_50], r9; unsigned __int16 *
0x180015179  lea     r9, [rbp+var_20]; unsigned int *
0x18001517d  call    ?LookupAccountNameWrap@@YAHPEBG0PEAXPEAKPEAG2PEAW4_SID_NAME_USE@@@Z; LookupAccountNameWrap(ushort const *,ushort const *,void *,ulong *,ushort *,ulong *,_SID_NAME_USE *)
0x180015182  neg     eax
0x180015184  sbb     eax, eax
0x180015186  not     eax
0x180015188  and     eax, 80041310h
0x18001518d  jmp     short loc_180015194
0x18001518f  mov     eax, 80070057h
0x180015194  mov     rcx, [rbp+var_8]
0x180015198  xor     rcx, rsp; StackCookie
0x18001519b  call    __security_check_cookie
0x1800151a0  mov     rbx, [rsp+70h+arg_10]
0x1800151a8  add     rsp, 70h
0x1800151ac  pop     rbp
0x1800151ad  retn
```
