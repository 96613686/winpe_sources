# CSDeleteAccount

- ea: `0x1800119fc`
- end: `0x180011c9c`
- name: `CSDeleteAccount`
- size: `672`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010230`

## callees

- `0x180003660`
- `0x1800119fc`
- `0x180013130`
- `0x1800131b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180011a4e`
- `ntdll!RtlInitUnicodeString` at `0x180011a4e`
- `SAMLIB!SamDeleteAlias` at `0x180011bbf`
- `SAMLIB!SamDeleteAlias` at `0x180011bbf`
- `SAMLIB!SamDeleteUser` at `0x180011af7`
- `SAMLIB!SamDeleteUser` at `0x180011af7`
- `SAMLIB!SamOpenUser` at `0x180011ae9`
- `SAMLIB!SamOpenUser` at `0x180011ae9`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180011aa8`
- `SAMLIB!SamLookupNamesInDomain2` at `0x180011aa8`
- `SAMLIB!SamCloseHandle` at `0x180011c7a`
- `SAMLIB!SamCloseHandle` at `0x180011c84`
- `SAMLIB!SamCloseHandle` at `0x180011c7a`
- `SAMLIB!SamCloseHandle` at `0x180011c84`
- `SAMLIB!SamOpenAlias` at `0x180011bb1`
- `SAMLIB!SamOpenAlias` at `0x180011bb1`
- `SAMLIB!SamFreeMemory` at `0x180011c2c`
- `SAMLIB!SamFreeMemory` at `0x180011c36`
- `SAMLIB!SamFreeMemory` at `0x180011c2c`
- `SAMLIB!SamFreeMemory` at `0x180011c36`

## pseudocode

```c
__int64 __fastcall CSDeleteAccount(void *a1, const WCHAR *a2, int a3)
{
  int v4; // edi
  int v6; // ebx
  int v7; // eax
  int v8; // r8d
  int v9; // eax
  int v10; // r8d
  int v11; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // eax
  int v15; // eax
  _DWORD *v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  void *v19; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  unsigned int *v21; // [rsp+88h] [rbp+28h] BYREF
  void *v22; // [rsp+98h] [rbp+38h] BYREF

  v17 = 0;
  v21 = 0;
  v4 = (int)a2;
  DestinationString = 0;
  if ( a2 )
  {
    if ( *a2 == 48 )
      return (unsigned int)-2147024809;
    RtlInitUnicodeString(&DestinationString, a2);
    v19 = 0;
    v22 = 0;
    v6 = SamHandleForDomain(a1, 0xF003Fu, 0x25Eu, &v19, &v22);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v7 = SamLookupNamesInDomain2(v22, 1, &DestinationString, &v21, &v17);
    if ( v7 < 0 )
    {
      v6 = v7 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, v8, v4, a3, v7);
      goto LABEL_33;
    }
    if ( *v17 == 1 )
    {
      if ( a3 == 1 )
      {
        v18 = 0;
        v9 = SamOpenUser(v22, 985087, *v21, &v18);
        if ( v9 >= 0 )
        {
          v11 = SamDeleteUser(v18);
          if ( v11 < 0 )
          {
            v6 = v11 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_SdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, *v21, v4, *v21, v11);
          }
          goto LABEL_29;
        }
        v6 = v9 | 0x10000000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_29:
          SamFreeMemory(v21);
          SamFreeMemory(v17);
LABEL_33:
          SamCloseHandle(v22);
          SamCloseHandle(v19);
          return (unsigned int)v6;
        }
        v13 = 95;
LABEL_27:
        WPP_SF_SD(v12[2], v13, v10, v4, v6);
        goto LABEL_29;
      }
    }
    else if ( *v17 == 4 && a3 == 2 )
    {
      v18 = 0;
      v14 = SamOpenAlias(v22, 983071, *v21, &v18);
      if ( v14 < 0 )
      {
        v6 = v14 | 0x10000000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_29;
        v13 = 97;
      }
      else
      {
        v15 = SamDeleteAlias(v18);
        if ( v15 >= 0 )
          goto LABEL_29;
        v6 = v15 | 0x10000000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_29;
        v13 = 96;
      }
      goto LABEL_27;
    }
    v6 = -805306230;
    goto LABEL_29;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x1800119fc  mov     [rsp-18h+arg_0], rbx
0x180011a01  push    rbp
0x180011a02  push    rsi
0x180011a03  push    rdi
0x180011a04  mov     rbp, rsp
0x180011a07  sub     rsp, 60h
0x180011a0b  mov     [rbp+var_30], 0
0x180011a13  xorps   xmm0, xmm0
0x180011a16  mov     [rbp+arg_8], 0
0x180011a1e  mov     esi, r8d
0x180011a21  mov     rdi, rdx
0x180011a24  mov     rbx, rcx
0x180011a27  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180011a2b  test    rdx, rdx
0x180011a2e  jnz     short loc_180011A3A
0x180011a30  mov     ebx, 80004003h
0x180011a35  jmp     loc_180011C8A
0x180011a3a  cmp     word ptr [rdx], 30h ; '0'
0x180011a3e  jnz     short loc_180011A4A
0x180011a40  mov     ebx, 80070057h
0x180011a45  jmp     loc_180011C8A
0x180011a4a  lea     rcx, [rbp+DestinationString]; DestinationString
0x180011a4e  call    cs:__imp_RtlInitUnicodeString
0x180011a54  lea     rax, [rbp+arg_18]
0x180011a58  mov     [rbp+var_20], 0
0x180011a60  lea     r9, [rbp+var_20]; void **
0x180011a64  mov     [rsp+60h+var_40], rax; void **
0x180011a69  mov     edx, 0F003Fh; unsigned int
0x180011a6e  mov     [rbp+arg_18], 0
0x180011a76  mov     r8d, 25Eh; unsigned int
0x180011a7c  mov     rcx, rbx; void *
0x180011a7f  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180011a84  mov     ebx, eax
0x180011a86  test    eax, eax
0x180011a88  js      loc_180011C8A
0x180011a8e  mov     rcx, [rbp+arg_18]
0x180011a92  lea     rax, [rbp+var_30]
0x180011a96  lea     r9, [rbp+arg_8]
0x180011a9a  mov     [rsp+60h+var_40], rax
0x180011a9f  lea     r8, [rbp+DestinationString]
0x180011aa3  mov     edx, 1
0x180011aa8  call    cs:__imp_SamLookupNamesInDomain2
0x180011aae  test    eax, eax
0x180011ab0  js      loc_180011C3E
0x180011ab6  mov     rax, [rbp+var_30]
0x180011aba  mov     ecx, [rax]
0x180011abc  cmp     ecx, 1
0x180011abf  jnz     loc_180011B83
0x180011ac5  cmp     esi, ecx
0x180011ac7  jnz     loc_180011C23
0x180011acd  mov     r8, [rbp+arg_8]
0x180011ad1  lea     r9, [rbp+var_28]
0x180011ad5  mov     rcx, [rbp+arg_18]
0x180011ad9  mov     edx, 0F07FFh
0x180011ade  mov     [rbp+var_28], 0
0x180011ae6  mov     r8d, [r8]
0x180011ae9  call    cs:__imp_SamOpenUser
0x180011aef  test    eax, eax
0x180011af1  js      short loc_180011B52
0x180011af3  mov     rcx, [rbp+var_28]
0x180011af7  call    cs:__imp_SamDeleteUser
0x180011afd  test    eax, eax
0x180011aff  jns     loc_180011C28
0x180011b05  mov     ebx, eax
0x180011b07  bts     ebx, 1Ch
0x180011b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b12  lea     rax, WPP_GLOBAL_Control
0x180011b19  cmp     rcx, rax
0x180011b1c  jz      loc_180011C28
0x180011b22  test    byte ptr [rcx+1Ch], 2
0x180011b26  jz      loc_180011C28
0x180011b2c  mov     rax, [rbp+arg_8]
0x180011b30  mov     edx, 5Eh ; '^'
0x180011b35  mov     rcx, [rcx+10h]
0x180011b39  mov     r9, rdi
0x180011b3c  mov     [rsp+60h+var_38], ebx
0x180011b40  mov     r8d, [rax]
0x180011b43  mov     dword ptr [rsp+60h+var_40], r8d
0x180011b48  call    WPP_SF_SdD
0x180011b4d  jmp     loc_180011C28
0x180011b52  mov     ebx, eax
0x180011b54  bts     ebx, 1Ch
0x180011b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b5f  lea     rax, WPP_GLOBAL_Control
0x180011b66  cmp     rcx, rax
0x180011b69  jz      loc_180011C28
0x180011b6f  test    byte ptr [rcx+1Ch], 2
0x180011b73  jz      loc_180011C28
0x180011b79  mov     edx, 5Fh ; '_'
0x180011b7e  jmp     loc_180011C11
0x180011b83  cmp     ecx, 4
0x180011b86  jnz     loc_180011C23
0x180011b8c  cmp     esi, 2
0x180011b8f  jnz     loc_180011C23
0x180011b95  mov     r8, [rbp+arg_8]
0x180011b99  lea     r9, [rbp+var_28]
0x180011b9d  mov     rcx, [rbp+arg_18]
0x180011ba1  mov     edx, 0F001Fh
0x180011ba6  mov     [rbp+var_28], 0
0x180011bae  mov     r8d, [r8]
0x180011bb1  call    cs:__imp_SamOpenAlias
0x180011bb7  test    eax, eax
0x180011bb9  js      short loc_180011BED
0x180011bbb  mov     rcx, [rbp+var_28]
0x180011bbf  call    cs:__imp_SamDeleteAlias
0x180011bc5  test    eax, eax
0x180011bc7  jns     short loc_180011C28
0x180011bc9  mov     ebx, eax
0x180011bcb  bts     ebx, 1Ch
0x180011bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bd6  lea     rax, WPP_GLOBAL_Control
0x180011bdd  cmp     rcx, rax
0x180011be0  jz      short loc_180011C28
0x180011be2  test    [rcx+1Ch], sil
0x180011be6  jz      short loc_180011C28
0x180011be8  lea     edx, [rsi+5Eh]
0x180011beb  jmp     short loc_180011C11
0x180011bed  mov     ebx, eax
0x180011bef  bts     ebx, 1Ch
0x180011bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bfa  lea     rax, WPP_GLOBAL_Control
0x180011c01  cmp     rcx, rax
0x180011c04  jz      short loc_180011C28
0x180011c06  test    byte ptr [rcx+1Ch], 2
0x180011c0a  jz      short loc_180011C28
0x180011c0c  mov     edx, 61h ; 'a'
0x180011c11  mov     rcx, [rcx+10h]
0x180011c15  mov     r9, rdi
0x180011c18  mov     dword ptr [rsp+60h+var_40], ebx
0x180011c1c  call    WPP_SF_SD
0x180011c21  jmp     short loc_180011C28
0x180011c23  mov     ebx, 0D000008Ah
0x180011c28  mov     rcx, [rbp+arg_8]
0x180011c2c  call    cs:__imp_SamFreeMemory
0x180011c32  mov     rcx, [rbp+var_30]
0x180011c36  call    cs:__imp_SamFreeMemory
0x180011c3c  jmp     short loc_180011C76
0x180011c3e  mov     ebx, eax
0x180011c40  bts     ebx, 1Ch
0x180011c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c4b  lea     rax, WPP_GLOBAL_Control
0x180011c52  cmp     rcx, rax
0x180011c55  jz      short loc_180011C76
0x180011c57  test    byte ptr [rcx+1Ch], 2
0x180011c5b  jz      short loc_180011C76
0x180011c5d  mov     rcx, [rcx+10h]
0x180011c61  mov     edx, 62h ; 'b'
0x180011c66  mov     [rsp+60h+var_38], ebx
0x180011c6a  mov     r9, rdi
0x180011c6d  mov     dword ptr [rsp+60h+var_40], esi
0x180011c71  call    WPP_SF_SdD
0x180011c76  mov     rcx, [rbp+arg_18]
0x180011c7a  call    cs:__imp_SamCloseHandle
0x180011c80  mov     rcx, [rbp+var_20]
0x180011c84  call    cs:__imp_SamCloseHandle
0x180011c8a  mov     eax, ebx
0x180011c8c  mov     rbx, [rsp+60h+arg_0]
0x180011c94  add     rsp, 60h
0x180011c98  pop     rdi
0x180011c99  pop     rsi
0x180011c9a  pop     rbp
0x180011c9b  retn
```
