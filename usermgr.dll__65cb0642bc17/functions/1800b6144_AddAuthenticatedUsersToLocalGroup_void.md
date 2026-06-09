# AddAuthenticatedUsersToLocalGroup(void)

- ea: `0x1800b6144`
- end: `0x1800b6282`
- name: `?AddAuthenticatedUsersToLocalGroup@@YAHXZ`
- size: `318`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b6cdc`

## callees

- `0x1800b6144`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b61a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b61ed`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b61a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800b61ed`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6228`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6237`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6259`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6228`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6237`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800b6259`
- `samcli!NetLocalGroupAddMembers` at `0x1800b6217`
- `samcli!NetLocalGroupAddMembers` at `0x1800b6217`

## pseudocode

```c
__int64 AddAuthenticatedUsersToLocalGroup(void)
{
  DWORD v0; // ebx
  PSID pSid; // [rsp+68h] [rbp+27h] BYREF
  PSID v3; // [rsp+70h] [rbp+2Fh] BYREF
  BYTE buf[8]; // [rsp+78h] [rbp+37h] BYREF
  PSID v5; // [rsp+80h] [rbp+3Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+47h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  v3 = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    *(_QWORD *)buf = pSid;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v3) )
    {
      v5 = v3;
      v0 = NetLocalGroupAddMembers(0, L"Users", 0, buf, 2u);
      if ( pSid )
        FreeSid(pSid);
      if ( v3 )
        FreeSid(v3);
      if ( !v0 || v0 == 1378 )
        return 1;
    }
    else if ( pSid )
    {
      FreeSid(pSid);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800b6144  mov     r11, rsp
0x1800b6147  mov     [r11+8], rbx
0x1800b614b  mov     [r11+10h], rdi
0x1800b614f  push    rbp
0x1800b6150  lea     rbp, [r11-5Fh]
0x1800b6154  sub     rsp, 90h
0x1800b615b  mov     rax, cs:__security_cookie
0x1800b6162  xor     rax, rsp
0x1800b6165  mov     [rbp+57h+var_8], rax
0x1800b6169  xor     edi, edi
0x1800b616b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800b6171  lea     rax, [rbp+57h+var_30]
0x1800b6175  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800b6178  mov     [r11-48h], rax
0x1800b617c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b6180  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x1800b6184  xor     r9d, r9d; nSubAuthority1
0x1800b6187  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x1800b618b  lea     r8d, [rdi+0Bh]; nSubAuthority0
0x1800b618f  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x1800b6193  mov     dl, 1; nSubAuthorityCount
0x1800b6195  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x1800b6199  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x1800b619d  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x1800b61a1  mov     [rbp+57h+var_30], rdi
0x1800b61a5  mov     [rbp+57h+var_28], rdi
0x1800b61a9  call    cs:__imp_AllocateAndInitializeSid
0x1800b61af  test    eax, eax
0x1800b61b1  jz      loc_1800B625F
0x1800b61b7  mov     rax, [rbp+57h+var_30]
0x1800b61bb  lea     r8d, [rdi+4]; nSubAuthority0
0x1800b61bf  mov     qword ptr [rbp+57h+buf], rax
0x1800b61c3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800b61c7  lea     rax, [rbp+57h+var_28]
0x1800b61cb  xor     r9d, r9d; nSubAuthority1
0x1800b61ce  mov     [rsp+90h+pSid], rax; pSid
0x1800b61d3  mov     dl, 1; nSubAuthorityCount
0x1800b61d5  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x1800b61d9  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x1800b61dd  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x1800b61e1  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x1800b61e5  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x1800b61e9  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x1800b61ed  call    cs:__imp_AllocateAndInitializeSid
0x1800b61f3  test    eax, eax
0x1800b61f5  jz      short loc_1800B6250
0x1800b61f7  mov     rax, [rbp+57h+var_28]
0x1800b61fb  lea     r9, [rbp+57h+buf]; buf
0x1800b61ff  xor     r8d, r8d; level
0x1800b6202  mov     [rbp+57h+var_18], rax
0x1800b6206  lea     rdx, groupname; "Users"
0x1800b620d  mov     [rsp+90h+nSubAuthority2], 2; totalentries
0x1800b6215  xor     ecx, ecx; servername
0x1800b6217  call    cs:__imp_NetLocalGroupAddMembers
0x1800b621d  mov     rcx, [rbp+57h+var_30]; pSid
0x1800b6221  mov     ebx, eax
0x1800b6223  test    rcx, rcx
0x1800b6226  jz      short loc_1800B622E
0x1800b6228  call    cs:__imp_FreeSid
0x1800b622e  mov     rcx, [rbp+57h+var_28]; pSid
0x1800b6232  test    rcx, rcx
0x1800b6235  jz      short loc_1800B623D
0x1800b6237  call    cs:__imp_FreeSid
0x1800b623d  test    ebx, ebx
0x1800b623f  jz      short loc_1800B6249
0x1800b6241  cmp     ebx, 562h
0x1800b6247  jnz     short loc_1800B625F
0x1800b6249  mov     eax, 1
0x1800b624e  jmp     short loc_1800B6261
0x1800b6250  mov     rcx, [rbp+57h+var_30]; pSid
0x1800b6254  test    rcx, rcx
0x1800b6257  jz      short loc_1800B625F
0x1800b6259  call    cs:__imp_FreeSid
0x1800b625f  xor     eax, eax
0x1800b6261  mov     rcx, [rbp+57h+var_8]
0x1800b6265  xor     rcx, rsp; StackCookie
0x1800b6268  call    __security_check_cookie
0x1800b626d  lea     r11, [rsp+90h+var_s0]
0x1800b6275  mov     rbx, [r11+10h]
0x1800b6279  mov     rdi, [r11+18h]
0x1800b627d  mov     rsp, r11
0x1800b6280  pop     rbp
0x1800b6281  retn
```
