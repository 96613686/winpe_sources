# SvcShareAdd

- ea: `0x140004d30`
- end: `0x1400050ef`
- name: `SvcShareAdd`
- size: `959`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x140004d30`
- `0x140005570`
- `0x14000a9c0`
- `0x140053040`
- `0x1400537e8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140004f0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f37`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f0f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f37`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f4b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004f7f`

## pseudocode

```c
__int64 __fastcall SvcShareAdd(__int64 a1, __int128 *a2, __int64 a3, unsigned int a4)
{
  signed int v7; // r15d
  signed int v8; // r12d
  signed int v9; // r13d
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r14
  int v16; // ecx
  __int64 result; // rax
  const WCHAR *v18; // rdx
  struct _UNICODE_STRING *v19; // rcx
  USHORT Length; // cx
  char v21; // di
  unsigned __int8 v22; // [rsp+50h] [rbp-D0h]
  struct _UNICODE_STRING v23; // [rsp+A0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v24; // [rsp+B0h] [rbp-70h] BYREF
  _QWORD v25[2]; // [rsp+C0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v26; // [rsp+D0h] [rbp-50h] BYREF
  __int128 v27; // [rsp+E0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-30h] BYREF
  __int128 v29[4]; // [rsp+100h] [rbp-20h] BYREF
  signed int v31; // [rsp+160h] [rbp+40h]
  char v32; // [rsp+168h] [rbp+48h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v27 = 0u;
  *(_QWORD *)&v26.Length = 0;
  v26.Buffer = 0;
  v25[0] = 0;
  v25[1] = 0;
  *(_QWORD *)&v24.Length = 0;
  v24.Buffer = 0;
  *(_QWORD *)&v23.Length = 0;
  v23.Buffer = 0;
  v29[0] = DEFAULT_SMB_STORQOSPOLICY_GUID;
  if ( a4 < 0x50 )
    return 3221225485LL;
  v7 = 1;
  v8 = 0;
  v31 = 0;
  v9 = 0;
  if ( *((_DWORD *)a2 + 16) >= 0x1F9u )
  {
    if ( a4 < 0x78 )
      return 3221225485LL;
    v10 = *(_DWORD *)(a3 + 80);
    if ( (v10 & 0x20) != 0 )
      v7 = *(_DWORD *)(a3 + 88);
    if ( (v10 & 0x40) != 0 )
      v9 = *(_DWORD *)(a3 + 92);
    if ( (v10 & 4) != 0 )
      v8 = *(_DWORD *)(a3 + 84);
    if ( (v10 & 0x100) != 0 )
      v31 = *(_DWORD *)(a3 + 96);
    if ( (v10 & 0x200) != 0 )
      v29[0] = *(_OWORD *)(a3 + 100);
  }
  *((_DWORD *)a2 + 20) = 0;
  if ( !(unsigned __int8)SrvAdminValidatePackedString(a3, a4, *(_QWORD *)a3)
    || !(unsigned __int8)SrvAdminValidatePackedString(a3, a4, *(_QWORD *)(a3 + 56))
    || !(unsigned __int8)SrvAdminValidatePackedString(a3, a4, *(_QWORD *)(a3 + 16))
    || !(unsigned __int8)SrvAdminValidatePackedString(a3, a4, *(_QWORD *)(a3 + 40))
    || !SrvAdminValidatePackedRelativeSecurityDescriptor(a3, a4, *(_QWORD *)(a3 + 72))
    || !SrvAdminValidatePackedRelativeSecurityDescriptor(a3, a4, *(unsigned int *)(a3 + 24)) )
  {
    return 3221225477LL;
  }
  if ( *(_QWORD *)a3 )
    *(_QWORD *)a3 += a3;
  v11 = *(_QWORD *)(a3 + 56);
  if ( v11 )
    *(_QWORD *)(a3 + 56) = a3 + v11;
  v12 = *(_QWORD *)(a3 + 16);
  if ( v12 )
    *(_QWORD *)(a3 + 16) = a3 + v12;
  v13 = *(_QWORD *)(a3 + 40);
  if ( v13 )
    *(_QWORD *)(a3 + 40) = a3 + v13;
  v14 = *(_QWORD *)(a3 + 72);
  if ( v14 )
    *(_QWORD *)(a3 + 72) = a3 + v14;
  v15 = *(unsigned int *)(a3 + 24);
  if ( !(_DWORD)v15 )
    return 3221225485LL;
  v16 = *(_DWORD *)(a3 + 8);
  if ( (_BYTE)v16
    && (unsigned __int8)v16 != 1
    && (unsigned __int8)v16 != 3
    && (unsigned int)(unsigned __int8)v16 - 104 > 1
    || (v16 & 0x8100000) == 0x8100000
    || (v16 & 0x6000000) == 0x6000000 )
  {
    *((_DWORD *)a2 + 20) = 3;
    return 3221225485LL;
  }
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)a3);
  v18 = *(const WCHAR **)(a3 + 40);
  if ( (*(_DWORD *)(a3 + 8) & 0x100000) != 0 )
  {
    v19 = (struct _UNICODE_STRING *)v25;
  }
  else
  {
    v19 = &v26;
    v27 = *a2;
  }
  RtlInitUnicodeString(v19, v18);
  RtlInitUnicodeString(&v24, *(PCWSTR *)(a3 + 16));
  RtlInitUnicodeString(&v23, *(PCWSTR *)(a3 + 56));
  Length = v23.Length;
  if ( !v23.Length )
  {
    RtlInitUnicodeString(&v23, L"*");
    Length = v23.Length;
  }
  if ( (*((_DWORD *)a2 + 18) & 0x10) != 0 )
  {
    v21 = 1;
  }
  else
  {
    v21 = 0;
    if ( Length != 2 || *v23.Buffer != 42 )
    {
      v32 = 0;
      SrvAdminIsScopedNameEx(&v23, &v32);
      if ( !v32 )
      {
        *((_DWORD *)a2 + 20) = 503;
        return 3221225485LL;
      }
    }
  }
  result = SrvAdminAddShare(
             a1,
             (const void **)&DestinationString,
             &v23,
             (const void **)&v27,
             (const void **)&v26,
             (unsigned __int16 *)v25,
             (const void **)&v24,
             *(_DWORD *)(a3 + 28),
             *(_DWORD *)(a3 + 8),
             v8,
             v22,
             (PSECURITY_DESCRIPTOR)(a3 + v15),
             *(PSECURITY_DESCRIPTOR *)(a3 + 72),
             v7,
             v9,
             *(_DWORD *)(a3 + 8) & 0xF000000,
             v21,
             v31,
             v29);
  switch ( (_DWORD)result )
  {
    case 0xC0000035:
      *((_DWORD *)a2 + 17) = 2118;
      return 0;
    case 0xC000009A:
      *((_DWORD *)a2 + 17) = 2105;
      return 0;
    case 0xC0000079:
      *((_DWORD *)a2 + 20) = 501;
      return result;
    case 0xC0980005:
      *((_DWORD *)a2 + 17) = 2114;
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140004d30  mov     [rsp-8+arg_8], rbx
0x140004d35  mov     [rsp-8+arg_0], rcx
0x140004d3a  push    rbp
0x140004d3b  push    rsi
0x140004d3c  push    rdi
0x140004d3d  push    r12
0x140004d3f  push    r13
0x140004d41  push    r14
0x140004d43  push    r15
0x140004d45  lea     rbp, [rsp+10h]
0x140004d4a  sub     rsp, 110h
0x140004d51  movups  xmm0, cs:DEFAULT_SMB_STORQOSPOLICY_GUID
0x140004d58  xor     ecx, ecx
0x140004d5a  mov     edi, r9d
0x140004d5d  mov     qword ptr [rbp+20h+DestinationString.Length], rcx
0x140004d61  mov     rbx, r8
0x140004d64  mov     [rbp+20h+DestinationString.Buffer], rcx
0x140004d68  mov     rsi, rdx
0x140004d6b  mov     qword ptr [rbp+20h+var_60], rcx
0x140004d6f  mov     qword ptr [rbp+20h+var_60+8], rcx
0x140004d73  mov     qword ptr [rbp+20h+var_70.Length], rcx
0x140004d77  mov     [rbp+20h+var_70.Buffer], rcx
0x140004d7b  mov     [rbp+20h+var_80], rcx
0x140004d7f  mov     [rbp+20h+var_78], rcx
0x140004d83  mov     qword ptr [rbp+20h+var_90.Length], rcx
0x140004d87  mov     [rbp+20h+var_90.Buffer], rcx
0x140004d8b  mov     qword ptr [rbp+20h+var_A0.Length], rcx
0x140004d8f  mov     [rbp+20h+var_A0.Buffer], rcx
0x140004d93  movups  [rbp+20h+var_40], xmm0
0x140004d97  cmp     r9d, 50h ; 'P'
0x140004d9b  jb      loc_140004EFE
0x140004da1  cmp     dword ptr [rdx+40h], 1F9h
0x140004da8  mov     r15d, 1
0x140004dae  mov     r12d, ecx
0x140004db1  mov     [rbp+20h+arg_10], ecx
0x140004db4  mov     r13d, ecx
0x140004db7  jb      short loc_140004DF3
0x140004db9  cmp     r9d, 78h ; 'x'
0x140004dbd  jb      loc_140004EFE
0x140004dc3  mov     eax, [r8+50h]
0x140004dc7  test    al, 20h
0x140004dc9  jz      short loc_140004DCF
0x140004dcb  mov     r15d, [r8+58h]
0x140004dcf  test    al, 40h
0x140004dd1  jz      short loc_140004DD7
0x140004dd3  mov     r13d, [r8+5Ch]
0x140004dd7  test    al, 4
0x140004dd9  jz      short loc_140004DDF
0x140004ddb  mov     r12d, [r8+54h]
0x140004ddf  bt      eax, 8
0x140004de3  jb      loc_140005067
0x140004de9  bt      eax, 9
0x140004ded  jb      loc_140005075
0x140004df3  mov     [rdx+50h], ecx
0x140004df6  mov     edx, edi
0x140004df8  mov     r8, [r8]
0x140004dfb  mov     rcx, rbx
0x140004dfe  call    SrvAdminValidatePackedString
0x140004e03  test    al, al
0x140004e05  jz      loc_140005057
0x140004e0b  mov     r8, [rbx+38h]
0x140004e0f  mov     edx, edi
0x140004e11  mov     rcx, rbx
0x140004e14  call    SrvAdminValidatePackedString
0x140004e19  test    al, al
0x140004e1b  jz      loc_140005057
0x140004e21  mov     r8, [rbx+10h]
0x140004e25  mov     edx, edi
0x140004e27  mov     rcx, rbx
0x140004e2a  call    SrvAdminValidatePackedString
0x140004e2f  test    al, al
0x140004e31  jz      loc_140005057
0x140004e37  mov     r8, [rbx+28h]
0x140004e3b  mov     edx, edi
0x140004e3d  mov     rcx, rbx
0x140004e40  call    SrvAdminValidatePackedString
0x140004e45  test    al, al
0x140004e47  jz      loc_140005057
0x140004e4d  mov     r8, [rbx+48h]
0x140004e51  mov     edx, edi
0x140004e53  mov     rcx, rbx
0x140004e56  call    SrvAdminValidatePackedRelativeSecurityDescriptor
0x140004e5b  test    al, al
0x140004e5d  jz      loc_140005057
0x140004e63  mov     r8d, [rbx+18h]
0x140004e67  mov     edx, edi
0x140004e69  mov     rcx, rbx
0x140004e6c  call    SrvAdminValidatePackedRelativeSecurityDescriptor
0x140004e71  test    al, al
0x140004e73  jz      loc_140005057
0x140004e79  mov     rax, [rbx]
0x140004e7c  test    rax, rax
0x140004e7f  jz      short loc_140004E87
0x140004e81  add     rax, rbx
0x140004e84  mov     [rbx], rax
0x140004e87  mov     rax, [rbx+38h]
0x140004e8b  test    rax, rax
0x140004e8e  jnz     loc_140005083
0x140004e94  mov     rax, [rbx+10h]
0x140004e98  test    rax, rax
0x140004e9b  jz      short loc_140004EA4
0x140004e9d  add     rax, rbx
0x140004ea0  mov     [rbx+10h], rax
0x140004ea4  mov     rax, [rbx+28h]
0x140004ea8  test    rax, rax
0x140004eab  jz      short loc_140004EB4
0x140004ead  add     rax, rbx
0x140004eb0  mov     [rbx+28h], rax
0x140004eb4  mov     rax, [rbx+48h]
0x140004eb8  test    rax, rax
0x140004ebb  jz      short loc_140004EC4
0x140004ebd  add     rax, rbx
0x140004ec0  mov     [rbx+48h], rax
0x140004ec4  mov     r14d, [rbx+18h]
0x140004ec8  test    r14d, r14d
0x140004ecb  jz      short loc_140004EFE
0x140004ecd  mov     ecx, [rbx+8]
0x140004ed0  movzx   eax, cl
0x140004ed3  test    cl, cl
0x140004ed5  jnz     loc_14000508F
0x140004edb  mov     eax, ecx
0x140004edd  and     eax, 8100000h
0x140004ee2  cmp     eax, 8100000h
0x140004ee7  jz      short loc_140004EF7
0x140004ee9  and     ecx, 6000000h
0x140004eef  cmp     ecx, 6000000h
0x140004ef5  jnz     short loc_140004F08
0x140004ef7  mov     dword ptr [rsi+50h], 3
0x140004efe  mov     eax, 0C000000Dh
0x140004f03  jmp     loc_14000503B
0x140004f08  mov     rdx, [rbx]; SourceString
0x140004f0b  lea     rcx, [rbp+20h+DestinationString]; DestinationString
0x140004f0f  call    cs:__imp_RtlInitUnicodeString
0x140004f16  nop     dword ptr [rax+rax+00h]
0x140004f1b  test    dword ptr [rbx+8], 100000h
0x140004f22  mov     rdx, [rbx+28h]; SourceString
0x140004f26  jnz     loc_14000505E
0x140004f2c  movups  xmm0, xmmword ptr [rsi]
0x140004f2f  lea     rcx, [rbp+20h+var_70]; DestinationString
0x140004f33  movups  [rbp+20h+var_60], xmm0
0x140004f37  call    cs:__imp_RtlInitUnicodeString
0x140004f3e  nop     dword ptr [rax+rax+00h]
0x140004f43  mov     rdx, [rbx+10h]; SourceString
0x140004f47  lea     rcx, [rbp+20h+var_90]; DestinationString
0x140004f4b  call    cs:__imp_RtlInitUnicodeString
0x140004f52  nop     dword ptr [rax+rax+00h]
0x140004f57  mov     rdx, [rbx+38h]; SourceString
0x140004f5b  lea     rcx, [rbp+20h+var_A0]; DestinationString
0x140004f5f  call    cs:__imp_RtlInitUnicodeString
0x140004f66  nop     dword ptr [rax+rax+00h]
0x140004f6b  movzx   ecx, [rbp+20h+var_A0.Length]
0x140004f6f  test    cx, cx
0x140004f72  jnz     short loc_140004F8F
0x140004f74  lea     rdx, Buf2; "*"
0x140004f7b  lea     rcx, [rbp+20h+var_A0]; DestinationString
0x140004f7f  call    cs:__imp_RtlInitUnicodeString
0x140004f86  nop     dword ptr [rax+rax+00h]
0x140004f8b  movzx   ecx, [rbp+20h+var_A0.Length]
0x140004f8f  mov     eax, [rsi+48h]
0x140004f92  test    al, 10h
0x140004f94  jz      loc_1400050B8
0x140004f9a  mov     dil, 1
0x140004f9d  mov     edx, [rbx+8]
0x140004fa0  lea     r8, [rbp+20h+var_40]
0x140004fa4  mov     [rsp+140h+var_B0], r8
0x140004fac  lea     rcx, [rbx+r14]
0x140004fb0  mov     r8d, [rbp+20h+arg_10]
0x140004fb4  lea     r9, [rbp+20h+var_60]
0x140004fb8  mov     [rsp+140h+var_B8], r8d
0x140004fc0  mov     eax, edx
0x140004fc2  mov     [rsp+140h+var_C0], dil
0x140004fca  lea     r8, [rbp+20h+var_A0]
0x140004fce  and     eax, 0F000000h
0x140004fd3  mov     [rsp+140h+var_C8], eax
0x140004fd7  mov     rax, [rbx+48h]
0x140004fdb  mov     [rsp+140h+var_D0], r13d
0x140004fe0  mov     [rsp+140h+var_D8], r15d
0x140004fe5  mov     [rsp+140h+var_E0], rax
0x140004fea  mov     eax, [rbx+1Ch]
0x140004fed  mov     [rsp+140h+var_E8], rcx
0x140004ff2  mov     rcx, [rbp+20h+arg_0]
0x140004ff6  mov     [rsp+140h+var_F8], r12d
0x140004ffb  mov     [rsp+140h+var_100], edx
0x140004fff  lea     rdx, [rbp+20h+DestinationString]
0x140005003  mov     [rsp+140h+var_108], eax
0x140005007  lea     rax, [rbp+20h+var_90]
0x14000500b  mov     [rsp+140h+var_110], rax
0x140005010  lea     rax, [rbp+20h+var_80]
0x140005014  mov     [rsp+140h+var_118], rax
0x140005019  lea     rax, [rbp+20h+var_70]
0x14000501d  mov     [rsp+140h+var_120], rax
0x140005022  call    SrvAdminAddShare
0x140005027  cmp     eax, 0C0000035h
0x14000502c  jnz     loc_1400050D8
0x140005032  mov     dword ptr [rsi+44h], 846h
0x140005039  xor     eax, eax
0x14000503b  mov     rbx, [rsp+140h+arg_8]
0x140005043  add     rsp, 110h
0x14000504a  pop     r15
0x14000504c  pop     r14
0x14000504e  pop     r13
0x140005050  pop     r12
0x140005052  pop     rdi
0x140005053  pop     rsi
0x140005054  pop     rbp
0x140005055  retn
0x140005057  mov     eax, 0C0000005h
0x14000505c  jmp     short loc_14000503B
0x14000505e  lea     rcx, [rbp+20h+var_80]
0x140005062  jmp     loc_140004F37
0x140005067  mov     ecx, [r8+60h]
0x14000506b  mov     [rbp+20h+arg_10], ecx
0x14000506e  xor     ecx, ecx
0x140005070  jmp     loc_140004DE9
0x140005075  movups  xmm0, xmmword ptr [r8+64h]
0x14000507a  movups  [rbp+20h+var_40], xmm0
0x14000507e  jmp     loc_140004DF3
0x140005083  add     rax, rbx
0x140005086  mov     [rbx+38h], rax
0x14000508a  jmp     loc_140004E94
0x14000508f  sub     eax, 1
0x140005092  jz      loc_140004EDB
0x140005098  sub     eax, 2
0x14000509b  jz      loc_140004EDB
0x1400050a1  sub     eax, 65h ; 'e'
0x1400050a4  jz      loc_140004EDB
0x1400050aa  cmp     eax, 1
0x1400050ad  jnz     loc_140004EF7
0x1400050b3  jmp     loc_140004EDB
0x1400050b8  xor     dil, dil
0x1400050bb  cmp     cx, 2
0x1400050bf  jnz     loc_14002B094
0x1400050c5  mov     rax, [rbp+20h+var_A0.Buffer]
0x1400050c9  cmp     word ptr [rax], 2Ah ; '*'
0x1400050cd  jz      loc_140004F9D
0x1400050d3  jmp     loc_14002B094
0x1400050d8  cmp     eax, 0C000009Ah
0x1400050dd  jnz     loc_14002B0BB
0x1400050e3  mov     dword ptr [rsi+44h], 839h
0x1400050ea  jmp     loc_140005039
0x14002b094  lea     rdx, [rbp+20h+arg_18]
0x14002b098  mov     [rbp+20h+arg_18], dil
0x14002b09c  lea     rcx, [rbp+20h+var_A0]
0x14002b0a0  call    SrvAdminIsScopedNameEx
0x14002b0a5  cmp     [rbp+20h+arg_18], dil
0x14002b0a9  jnz     loc_140004F9D
0x14002b0af  mov     dword ptr [rsi+50h], 1F7h
0x14002b0b6  jmp     loc_140004EFE
0x14002b0bb  cmp     eax, 0C0000079h
0x14002b0c0  jnz     short loc_14002B0CE
0x14002b0c2  mov     dword ptr [rsi+50h], 1F5h
0x14002b0c9  jmp     loc_14000503B
0x14002b0ce  cmp     eax, 0C0980005h
0x14002b0d3  jnz     loc_14000503B
0x14002b0d9  mov     dword ptr [rsi+44h], 842h
0x14002b0e0  jmp     loc_140005039
```
