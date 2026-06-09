# DigestFilterSids(_DIGEST_PARAMETER *,_NETLOGON_VALIDATION_SAM_INFO3 *)

- ea: `0x180022940`
- end: `0x180022a58`
- name: `?DigestFilterSids@@YAJPEAU_DIGEST_PARAMETER@@PEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct _DIGEST_PARAMETER *, struct _NETLOGON_VALIDATION_SAM_INFO3 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180022bb8`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x180022940`

## import_xrefs

- `LSASRV!LsaIFilterSids` at `0x1800229cd`
- `LSASRV!LsaIFilterSids` at `0x1800229cd`

## pseudocode

```c
__int64 __fastcall DigestFilterSids(struct _DIGEST_PARAMETER *a1, struct _NETLOGON_VALIDATION_SAM_INFO3 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
  v4 = LsaIFilterSids(
         0,
         *((unsigned int *)a1 + 248),
         *((unsigned int *)a1 + 249),
         *((unsigned int *)a1 + 250),
         *((_QWORD *)a1 + 126),
         3,
         a2,
         0,
         0,
         0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_12;
    v7 = 73;
    goto LABEL_11;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 72;
LABEL_11:
    WPP_SF_d(v6[2], v7, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, (unsigned int)v4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v6 != &WPP_GLOBAL_Control && *((char *)v6 + 28) < 0 )
    WPP_SF_d(v6[2], 74, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180022940  mov     [rsp+arg_0], rbx
0x180022945  mov     [rsp+arg_8], rbp
0x18002294a  push    rdi
0x18002294b  sub     rsp, 50h
0x18002294f  mov     rdi, rdx
0x180022952  mov     rbx, rcx
0x180022955  mov     rcx, cs:WPP_GLOBAL_Control
0x18002295c  lea     rbp, WPP_GLOBAL_Control
0x180022963  cmp     rcx, rbp
0x180022966  jz      short loc_180022983
0x180022968  test    byte ptr [rcx+1Ch], 80h
0x18002296c  jz      short loc_180022983
0x18002296e  mov     rcx, [rcx+10h]
0x180022972  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022979  mov     edx, 46h ; 'F'
0x18002297e  call    WPP_SF_
0x180022983  mov     rax, [rbx+3F0h]
0x18002298a  xor     ecx, ecx
0x18002298c  mov     r9d, [rbx+3E8h]
0x180022993  mov     r8d, [rbx+3E4h]
0x18002299a  mov     edx, [rbx+3E0h]
0x1800229a0  mov     [rsp+58h+var_10], 0
0x1800229a9  mov     [rsp+58h+var_18], 0
0x1800229b2  mov     [rsp+58h+var_20], 0
0x1800229bb  mov     [rsp+58h+var_28], rdi
0x1800229c0  mov     [rsp+58h+var_30], 3
0x1800229c8  mov     [rsp+58h+var_38], rax
0x1800229cd  call    cs:__imp_LsaIFilterSids
0x1800229d3  mov     ebx, eax
0x1800229d5  test    eax, eax
0x1800229d7  jns     short loc_1800229F2
0x1800229d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229e0  cmp     rcx, rbp
0x1800229e3  jz      short loc_180022A46
0x1800229e5  test    byte ptr [rcx+1Ch], 1
0x1800229e9  jz      short loc_180022A23
0x1800229eb  mov     edx, 48h ; 'H'
0x1800229f0  jmp     short loc_180022A09
0x1800229f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229f9  cmp     rcx, rbp
0x1800229fc  jz      short loc_180022A46
0x1800229fe  test    byte ptr [rcx+1Ch], 4
0x180022a02  jz      short loc_180022A23
0x180022a04  mov     edx, 49h ; 'I'
0x180022a09  mov     rcx, [rcx+10h]
0x180022a0d  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022a14  mov     r9d, ebx
0x180022a17  call    WPP_SF_d
0x180022a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a23  cmp     rcx, rbp
0x180022a26  jz      short loc_180022A46
0x180022a28  test    byte ptr [rcx+1Ch], 80h
0x180022a2c  jz      short loc_180022A46
0x180022a2e  mov     rcx, [rcx+10h]
0x180022a32  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180022a39  mov     edx, 4Ah ; 'J'
0x180022a3e  mov     r9d, ebx
0x180022a41  call    WPP_SF_d
0x180022a46  mov     rbp, [rsp+58h+arg_8]
0x180022a4b  mov     eax, ebx
0x180022a4d  mov     rbx, [rsp+58h+arg_0]
0x180022a52  add     rsp, 50h
0x180022a56  pop     rdi
0x180022a57  retn
```
