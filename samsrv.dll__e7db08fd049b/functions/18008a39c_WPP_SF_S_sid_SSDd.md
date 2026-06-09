# WPP_SF_S_sid_SSDd

- ea: `0x18008a39c`
- end: `0x18008a548`
- name: `WPP_SF_S_sid_SSDd`
- size: `428`
- prototype: `__int64 __fastcall(int, int, int, int, PSID pSid, __int64, __int64, char, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023c00`

## callees

- `0x18008a39c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18008a527`
- `ntdll!EtwTraceMessage` at `0x18008a527`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008a45a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008a45a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008a44b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008a473`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008a44b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008a473`

## pseudocode

```c
__int64 __fastcall WPP_SF_S_sid_SSDd(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char *pSid,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // rdi
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  const char *v12; // rbx

  v7 = -1;
  v9 = 10;
  if ( a7 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(a7 + 2 * v10) );
  }
  if ( a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a6 + 2 * v11) );
  }
  v12 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    GetLengthSid(pSid);
    goto LABEL_11;
  }
  if ( pSid )
  {
LABEL_11:
    if ( IsValidSid(pSid) )
      goto LABEL_13;
  }
  v12 = "NULL";
LABEL_13:
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v9 = 2 * v7 + 2;
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids, 32, a4, v9, v12);
}

```

## disassembly

```asm
0x18008a39c  mov     [rsp+arg_8], rbx
0x18008a3a1  mov     [rsp+arg_10], r8
0x18008a3a6  mov     [rsp+arg_0], rcx
0x18008a3ab  push    rbp
0x18008a3ac  push    rsi
0x18008a3ad  push    rdi
0x18008a3ae  push    r12
0x18008a3b0  push    r13
0x18008a3b2  push    r14
0x18008a3b4  push    r15
0x18008a3b6  sub     rsp, 90h
0x18008a3bd  mov     rsi, [rsp+0C8h+arg_30]
0x18008a3c5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008a3c9  xor     ecx, ecx
0x18008a3cb  mov     r15, r9
0x18008a3ce  mov     r14d, 0Ah
0x18008a3d4  test    rsi, rsi
0x18008a3d7  jz      short loc_18008A3F7
0x18008a3d9  mov     rax, rdi
0x18008a3dc  inc     rax
0x18008a3df  cmp     [rsi+rax*2], cx
0x18008a3e3  jnz     short loc_18008A3DC
0x18008a3e5  lea     rax, ds:2[rax*2]
0x18008a3ed  mov     [rsp+0C8h+arg_10], rax
0x18008a3f5  jmp     short loc_18008A3FF
0x18008a3f7  mov     [rsp+0C8h+arg_10], r14
0x18008a3ff  mov     rbp, [rsp+0C8h+arg_28]
0x18008a407  lea     rdx, aNull_0; "NULL"
0x18008a40e  test    rsi, rsi
0x18008a411  cmovz   rsi, rdx
0x18008a415  test    rbp, rbp
0x18008a418  jz      short loc_18008A431
0x18008a41a  mov     rax, rdi
0x18008a41d  inc     rax
0x18008a420  cmp     [rbp+rax*2+0], cx
0x18008a425  jnz     short loc_18008A41D
0x18008a427  lea     r13, ds:2[rax*2]
0x18008a42f  jmp     short loc_18008A434
0x18008a431  mov     r13, r14
0x18008a434  mov     rbx, [rsp+0C8h+pSid]
0x18008a43c  test    rbp, rbp
0x18008a43f  cmovz   rbp, rdx
0x18008a443  test    rbx, rbx
0x18008a446  jz      short loc_18008A465
0x18008a448  mov     rcx, rbx; pSid
0x18008a44b  call    cs:__imp_IsValidSid
0x18008a451  xor     ecx, ecx
0x18008a453  test    eax, eax
0x18008a455  jz      short loc_18008A465
0x18008a457  mov     rcx, rbx; pSid
0x18008a45a  call    cs:__imp_GetLengthSid
0x18008a460  mov     r12d, eax
0x18008a463  jmp     short loc_18008A470
0x18008a465  mov     r12d, 5
0x18008a46b  test    rbx, rbx
0x18008a46e  jz      short loc_18008A47F
0x18008a470  mov     rcx, rbx; pSid
0x18008a473  call    cs:__imp_IsValidSid
0x18008a479  xor     ecx, ecx
0x18008a47b  test    eax, eax
0x18008a47d  jnz     short loc_18008A486
0x18008a47f  lea     rbx, aNull; "NULL"
0x18008a486  test    r15, r15
0x18008a489  jz      short loc_18008A49D
0x18008a48b  inc     rdi
0x18008a48e  cmp     [r15+rdi*2], cx
0x18008a493  jnz     short loc_18008A48B
0x18008a495  lea     r14, ds:2[rdi*2]
0x18008a49d  mov     [rsp+0C8h+var_48], rcx
0x18008a4a5  lea     rdx, aNull_0; "NULL"
0x18008a4ac  mov     r9d, 20h ; ' '
0x18008a4b2  mov     eax, r12d
0x18008a4b5  test    r15, r15
0x18008a4b8  lea     rcx, [rsp+0C8h+arg_40]
0x18008a4c0  lea     r8, WPP_399428e82d8c35f3bf4ebd44ea527e78_Traceguids
0x18008a4c7  cmovz   r15, rdx
0x18008a4cb  lea     edx, [r9-1Ch]
0x18008a4cf  mov     [rsp+0C8h+var_50], rdx
0x18008a4d4  mov     [rsp+0C8h+var_58], rcx
0x18008a4d9  lea     rcx, [rsp+0C8h+arg_38]
0x18008a4e1  mov     [rsp+0C8h+var_60], rdx
0x18008a4e6  lea     edx, [r9+0Bh]
0x18008a4ea  mov     [rsp+0C8h+var_68], rcx
0x18008a4ef  mov     rcx, [rsp+0C8h+arg_10]
0x18008a4f7  mov     [rsp+0C8h+var_70], rcx
0x18008a4fc  mov     rcx, [rsp+0C8h+arg_0]
0x18008a504  mov     [rsp+0C8h+var_78], rsi
0x18008a509  mov     [rsp+0C8h+var_80], r13
0x18008a50e  mov     [rsp+0C8h+var_88], rbp
0x18008a513  mov     [rsp+0C8h+var_90], rax
0x18008a518  mov     [rsp+0C8h+var_98], rbx
0x18008a51d  mov     [rsp+0C8h+var_A0], r14
0x18008a522  mov     [rsp+0C8h+var_A8], r15
0x18008a527  call    cs:__imp_EtwTraceMessage
0x18008a52d  mov     rbx, [rsp+0C8h+arg_8]
0x18008a535  add     rsp, 90h
0x18008a53c  pop     r15
0x18008a53e  pop     r14
0x18008a540  pop     r13
0x18008a542  pop     r12
0x18008a544  pop     rdi
0x18008a545  pop     rsi
0x18008a546  pop     rbp
0x18008a547  retn
```
