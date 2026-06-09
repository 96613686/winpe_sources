# SvcShareSetInfo

- ea: `0x140023c20`
- end: `0x140023f89`
- name: `SvcShareSetInfo`
- size: `873`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x140023c20`
- `0x140025b80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140023d9e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023db7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023e6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023d9e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023db7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023e6a`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140023dee`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140023e3e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140023dee`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140023e3e`

## pseudocode

```c
__int64 __fastcall SvcShareSetInfo(int a1, _DWORD *a2, unsigned __int64 a3, unsigned int a4)
{
  unsigned int v4; // esi
  int v5; // r12d
  __int64 v6; // r15
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int64 v12; // r9
  PCWSTR *v13; // r13
  __int64 v14; // rax
  const WCHAR *v15; // r10
  __int64 v16; // rax
  unsigned __int64 v17; // r11
  PSECURITY_DESCRIPTOR *v18; // rbx
  __int64 v19; // rax
  void *v20; // rcx
  unsigned __int64 v21; // r8
  int v22; // esi
  int v23; // ebx
  int v24; // r15d
  ULONG v25; // ebx
  __int64 result; // rax
  __int64 v27; // [rsp+38h] [rbp-51h]
  PSECURITY_DESCRIPTOR *v28; // [rsp+70h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-11h] BYREF
  struct _UNICODE_STRING v30; // [rsp+88h] [rbp-1h] BYREF
  __int64 v31[2]; // [rsp+98h] [rbp+Fh] BYREF
  int v33; // [rsp+F8h] [rbp+6Fh]
  int v34; // [rsp+100h] [rbp+77h]

  v4 = a2[16];
  v5 = 0;
  v6 = a4;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&v30.Length = 0;
  v30.Buffer = 0;
  *(_OWORD *)v31 = 0;
  if ( v4 == 1005 )
  {
    result = SrvAdminModifyShare(a1, (int)a2, (int)a2 + 16, 0, 0, 0, *(_DWORD *)a3, v27, 0, 0, 0, 0, 0, 4);
  }
  else
  {
    if ( v4 != 1503 )
    {
      v9 = *(_QWORD *)a3;
      if ( *(_QWORD *)a3 )
      {
        v10 = v9 + a3;
        *(_QWORD *)a3 = v9 + a3;
      }
      else
      {
        v10 = 0;
      }
      v11 = *(_QWORD *)(a3 + 56);
      if ( v11 )
      {
        v12 = v11 + a3;
        *(_QWORD *)(a3 + 56) = v11 + a3;
      }
      else
      {
        v12 = 0;
      }
      v13 = (PCWSTR *)(a3 + 16);
      v14 = *(_QWORD *)(a3 + 16);
      if ( v14 )
      {
        v15 = (const WCHAR *)(v14 + a3);
        *v13 = (PCWSTR)(v14 + a3);
      }
      else
      {
        v15 = 0;
      }
      v16 = *(_QWORD *)(a3 + 40);
      if ( v16 )
      {
        v17 = v16 + a3;
        *(_QWORD *)(a3 + 40) = v16 + a3;
      }
      else
      {
        v17 = 0;
      }
      v18 = (PSECURITY_DESCRIPTOR *)(a3 + 72);
      v19 = *(_QWORD *)(a3 + 72);
      v28 = (PSECURITY_DESCRIPTOR *)(a3 + 72);
      if ( v19 )
      {
        v20 = (void *)(v19 + a3);
        *v18 = (PSECURITY_DESCRIPTOR)(v19 + a3);
      }
      else
      {
        v20 = 0;
      }
      v21 = v6 + a3;
      if ( v21 < a3
        || v10 && (v10 <= a3 || v10 >= v21)
        || v12 && (v12 <= a3 || v12 >= v21)
        || v15 && ((unsigned __int64)v15 <= a3 || (unsigned __int64)v15 >= v21)
        || v17 && (v17 <= a3 || v17 >= v21)
        || v20 && ((unsigned __int64)v20 <= a3 || (unsigned __int64)v20 >= v21) )
      {
        return 3221225477LL;
      }
      v34 = 0;
      v33 = 0;
      if ( v4 >= 0x1F9 )
      {
        v22 = *(_DWORD *)(a3 + 80) & 0x3FF;
        if ( (*(_BYTE *)(a3 + 80) & 1) != 0 )
          RtlInitUnicodeString(&DestinationString, v15);
        if ( (v22 & 0x80u) != 0 )
          RtlInitUnicodeString(&v30, *(PCWSTR *)(a3 + 40));
        if ( (v22 & 2) != 0 )
        {
          if ( *(_DWORD *)(a3 + 28) )
            v5 = *(_DWORD *)(a3 + 28);
          else
            v22 &= ~2u;
        }
        if ( (v22 & 0x10) == 0 || *v18 && RtlLengthSecurityDescriptor(*v18) <= (int)a3 - (int)v20 + (int)v6 )
        {
          v23 = *(_DWORD *)(a3 + 84);
          v24 = *(_DWORD *)(a3 + 88);
          if ( (v22 & 0x40) != 0 )
            v34 = *(_DWORD *)(a3 + 92);
          if ( (v22 & 0x100) != 0 )
            v33 = *(_DWORD *)(a3 + 96);
          if ( (v22 & 0x200) != 0 )
            *(_OWORD *)v31 = *(_OWORD *)(a3 + 100);
LABEL_58:
          result = SrvAdminModifyShare(
                     a1,
                     (int)a2,
                     (int)a2 + 16,
                     (int)&DestinationString,
                     (__int64)&v30,
                     v5,
                     v23,
                     v27,
                     *v28,
                     v24,
                     v34,
                     v33,
                     (__int64)v31,
                     v22);
          goto LABEL_62;
        }
        return 3221225485LL;
      }
      v22 = 9;
      if ( v20 )
      {
        v25 = a3 - *(_DWORD *)v18 + v6;
        if ( RtlLengthSecurityDescriptor(v20) > v25 )
          return 3221225485LL;
        v22 = 25;
      }
      v23 = 0;
      v24 = 0;
      RtlInitUnicodeString(&DestinationString, *v13);
      if ( a2[21] )
      {
        v22 |= 2u;
        v5 = a2[21];
      }
      goto LABEL_58;
    }
    result = SrvAdminModifyShare(a1, (int)a2, (int)a2 + 16, 0, 0, 0, 0, v27, 0, 0, 0, 0, 0, 8);
  }
LABEL_62:
  if ( (_DWORD)result == -1073741772 )
  {
    a2[17] = 2310;
  }
  else
  {
    if ( (_DWORD)result != -1073741670 )
      return result;
    a2[17] = 2105;
  }
  return 0;
}

```

## disassembly

```asm
0x140023c20  mov     [rsp-8+arg_18], rbx
0x140023c25  mov     qword ptr [rsp-8+arg_0], rcx
0x140023c2a  push    rbp
0x140023c2b  push    rsi
0x140023c2c  push    rdi
0x140023c2d  push    r12
0x140023c2f  push    r13
0x140023c31  push    r14
0x140023c33  push    r15
0x140023c35  lea     rbp, [rsp-27h]
0x140023c3a  sub     rsp, 0B0h
0x140023c41  mov     esi, [rdx+40h]
0x140023c44  xor     r12d, r12d
0x140023c47  mov     r15d, r9d
0x140023c4a  xorps   xmm0, xmm0
0x140023c4d  mov     qword ptr [rbp+57h+DestinationString.Length], r12
0x140023c51  mov     rdi, r8
0x140023c54  mov     [rbp+57h+DestinationString.Buffer], r12
0x140023c58  mov     r14, rdx
0x140023c5b  mov     qword ptr [rbp+57h+var_58.Length], r12
0x140023c5f  mov     [rbp+57h+var_58.Buffer], r12
0x140023c63  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140023c67  cmp     esi, 3EDh
0x140023c6d  jz      loc_140023F0D
0x140023c73  cmp     esi, 5DFh
0x140023c79  jz      loc_140023EE5
0x140023c7f  mov     rax, [r8]
0x140023c82  test    rax, rax
0x140023c85  jz      short loc_140023C90
0x140023c87  lea     rdx, [rax+r8]
0x140023c8b  mov     [r8], rdx
0x140023c8e  jmp     short loc_140023C93
0x140023c90  mov     rdx, r12
0x140023c93  mov     rax, [r8+38h]
0x140023c97  test    rax, rax
0x140023c9a  jz      short loc_140023CA6
0x140023c9c  lea     r9, [rax+r8]
0x140023ca0  mov     [r8+38h], r9
0x140023ca4  jmp     short loc_140023CA9
0x140023ca6  mov     r9, r12
0x140023ca9  lea     r13, [r8+10h]
0x140023cad  mov     rax, [r13+0]
0x140023cb1  test    rax, rax
0x140023cb4  jz      short loc_140023CC0
0x140023cb6  lea     r10, [rax+r8]
0x140023cba  mov     [r13+0], r10
0x140023cbe  jmp     short loc_140023CC3
0x140023cc0  mov     r10, r12
0x140023cc3  mov     rax, [r8+28h]
0x140023cc7  test    rax, rax
0x140023cca  jz      short loc_140023CD6
0x140023ccc  lea     r11, [rax+r8]
0x140023cd0  mov     [r8+28h], r11
0x140023cd4  jmp     short loc_140023CD9
0x140023cd6  mov     r11, r12
0x140023cd9  lea     rbx, [r8+48h]
0x140023cdd  mov     rax, [rbx]
0x140023ce0  mov     [rbp+57h+var_70], rbx
0x140023ce4  test    rax, rax
0x140023ce7  jz      short loc_140023CF2
0x140023ce9  lea     rcx, [rax+r8]
0x140023ced  mov     [rbx], rcx
0x140023cf0  jmp     short loc_140023CF5
0x140023cf2  mov     rcx, r12; SecurityDescriptor
0x140023cf5  add     r8, r15
0x140023cf8  cmp     r8, rdi
0x140023cfb  jb      loc_140023EDB
0x140023d01  test    rdx, rdx
0x140023d04  jz      short loc_140023D18
0x140023d06  cmp     rdx, rdi
0x140023d09  jbe     loc_140023EDB
0x140023d0f  cmp     rdx, r8
0x140023d12  jnb     loc_140023EDB
0x140023d18  test    r9, r9
0x140023d1b  jz      short loc_140023D2F
0x140023d1d  cmp     r9, rdi
0x140023d20  jbe     loc_140023EDB
0x140023d26  cmp     r9, r8
0x140023d29  jnb     loc_140023EDB
0x140023d2f  test    r10, r10
0x140023d32  jz      short loc_140023D46
0x140023d34  cmp     r10, rdi
0x140023d37  jbe     loc_140023EDB
0x140023d3d  cmp     r10, r8
0x140023d40  jnb     loc_140023EDB
0x140023d46  test    r11, r11
0x140023d49  jz      short loc_140023D5D
0x140023d4b  cmp     r11, rdi
0x140023d4e  jbe     loc_140023EDB
0x140023d54  cmp     r11, r8
0x140023d57  jnb     loc_140023EDB
0x140023d5d  test    rcx, rcx
0x140023d60  jz      short loc_140023D74
0x140023d62  cmp     rcx, rdi
0x140023d65  jbe     loc_140023EDB
0x140023d6b  cmp     rcx, r8
0x140023d6e  jnb     loc_140023EDB
0x140023d74  mov     [rbp+57h+arg_10], r12d
0x140023d78  mov     [rbp+57h+arg_8], r12d
0x140023d7c  cmp     esi, 1F9h
0x140023d82  jb      loc_140023E2E
0x140023d88  mov     esi, [rdi+50h]
0x140023d8b  and     esi, 3FFh
0x140023d91  test    sil, 1
0x140023d95  jz      short loc_140023DAA
0x140023d97  mov     rdx, r10; SourceString
0x140023d9a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140023d9e  call    cs:__imp_RtlInitUnicodeString
0x140023da5  nop     dword ptr [rax+rax+00h]
0x140023daa  test    sil, sil
0x140023dad  jns     short loc_140023DC3
0x140023daf  mov     rdx, [rdi+28h]; SourceString
0x140023db3  lea     rcx, [rbp+57h+var_58]; DestinationString
0x140023db7  call    cs:__imp_RtlInitUnicodeString
0x140023dbe  nop     dword ptr [rax+rax+00h]
0x140023dc3  test    sil, 2
0x140023dc7  jz      short loc_140023DD8
0x140023dc9  mov     eax, [rdi+1Ch]
0x140023dcc  test    eax, eax
0x140023dce  jnz     short loc_140023DD5
0x140023dd0  and     esi, 0FFFFFFFDh
0x140023dd3  jmp     short loc_140023DD8
0x140023dd5  mov     r12d, eax
0x140023dd8  test    sil, 10h
0x140023ddc  jz      short loc_140023DFE
0x140023dde  mov     rcx, [rbx]; SecurityDescriptor
0x140023de1  test    rcx, rcx
0x140023de4  jz      short loc_140023E4E
0x140023de6  mov     eax, edi
0x140023de8  sub     eax, ecx
0x140023dea  lea     ebx, [rax+r15]
0x140023dee  call    cs:__imp_RtlLengthSecurityDescriptor
0x140023df5  nop     dword ptr [rax+rax+00h]
0x140023dfa  cmp     eax, ebx
0x140023dfc  ja      short loc_140023E4E
0x140023dfe  mov     ebx, [rdi+54h]
0x140023e01  mov     r15d, [rdi+58h]
0x140023e05  test    sil, 40h
0x140023e09  jz      short loc_140023E11
0x140023e0b  mov     eax, [rdi+5Ch]
0x140023e0e  mov     [rbp+57h+arg_10], eax
0x140023e11  bt      esi, 8
0x140023e15  jnb     short loc_140023E1D
0x140023e17  mov     eax, [rdi+60h]
0x140023e1a  mov     [rbp+57h+arg_8], eax
0x140023e1d  bt      esi, 9
0x140023e21  jnb     short loc_140023E84
0x140023e23  movups  xmm0, xmmword ptr [rdi+64h]
0x140023e27  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x140023e2c  jmp     short loc_140023E84
0x140023e2e  mov     esi, 9
0x140023e33  test    rcx, rcx
0x140023e36  jz      short loc_140023E5D
0x140023e38  sub     edi, [rbx]
0x140023e3a  lea     ebx, [rdi+r15]
0x140023e3e  call    cs:__imp_RtlLengthSecurityDescriptor
0x140023e45  nop     dword ptr [rax+rax+00h]
0x140023e4a  cmp     eax, ebx
0x140023e4c  jbe     short loc_140023E58
0x140023e4e  mov     eax, 0C000000Dh
0x140023e53  jmp     loc_140023F6D
0x140023e58  mov     esi, 19h
0x140023e5d  mov     rdx, [r13+0]; SourceString
0x140023e61  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140023e65  xor     ebx, ebx
0x140023e67  xor     r15d, r15d
0x140023e6a  call    cs:__imp_RtlInitUnicodeString
0x140023e71  nop     dword ptr [rax+rax+00h]
0x140023e76  mov     eax, [r14+54h]
0x140023e7a  test    eax, eax
0x140023e7c  jz      short loc_140023E84
0x140023e7e  or      esi, 2
0x140023e81  mov     r12d, eax
0x140023e84  mov     rcx, qword ptr [rbp+57h+arg_0]; int
0x140023e88  lea     rax, [rbp+57h+var_48]
0x140023e8c  mov     [rsp+0E0h+var_78], esi; int
0x140023e90  lea     r8, [r14+10h]; int
0x140023e94  mov     [rsp+0E0h+var_80], rax; __int64
0x140023e99  lea     r9, [rbp+57h+DestinationString]; int
0x140023e9d  mov     eax, [rbp+57h+arg_8]
0x140023ea0  mov     rdx, r14; int
0x140023ea3  mov     [rsp+0E0h+var_88], eax; int
0x140023ea7  mov     eax, [rbp+57h+arg_10]
0x140023eaa  mov     [rsp+0E0h+var_90], eax; int
0x140023eae  mov     rax, [rbp+57h+var_70]
0x140023eb2  mov     [rsp+0E0h+var_98], r15d; int
0x140023eb7  mov     rax, [rax]
0x140023eba  mov     [rsp+0E0h+SecurityDescriptor], rax; SecurityDescriptor
0x140023ebf  lea     rax, [rbp+57h+var_58]
0x140023ec3  mov     [rsp+0E0h+var_B0], ebx; int
0x140023ec7  mov     [rsp+0E0h+var_B8], r12d; int
0x140023ecc  mov     [rsp+0E0h+var_C0], rax; __int64
0x140023ed1  call    SrvAdminModifyShare
0x140023ed6  xor     r12d, r12d
0x140023ed9  jmp     short loc_140023F4A
0x140023edb  mov     eax, 0C0000005h
0x140023ee0  jmp     loc_140023F6D
0x140023ee5  mov     [rsp+0E0h+var_78], 8
0x140023eed  mov     [rsp+0E0h+var_80], r12
0x140023ef2  mov     [rsp+0E0h+var_88], r12d
0x140023ef7  mov     [rsp+0E0h+var_90], r12d
0x140023efc  mov     [rsp+0E0h+var_98], r12d
0x140023f01  mov     [rsp+0E0h+SecurityDescriptor], r12
0x140023f06  mov     [rsp+0E0h+var_B0], r12d
0x140023f0b  jmp     short loc_140023F34
0x140023f0d  mov     eax, [rdi]
0x140023f0f  mov     [rsp+0E0h+var_78], 4; int
0x140023f17  mov     [rsp+0E0h+var_80], r12; __int64
0x140023f1c  mov     [rsp+0E0h+var_88], r12d; int
0x140023f21  mov     [rsp+0E0h+var_90], r12d; int
0x140023f26  mov     [rsp+0E0h+var_98], r12d; int
0x140023f2b  mov     [rsp+0E0h+SecurityDescriptor], r12; SecurityDescriptor
0x140023f30  mov     [rsp+0E0h+var_B0], eax; int
0x140023f34  mov     [rsp+0E0h+var_B8], r12d; int
0x140023f39  lea     r8, [rdx+10h]; int
0x140023f3d  xor     r9d, r9d; int
0x140023f40  mov     [rsp+0E0h+var_C0], r12; __int64
0x140023f45  call    SrvAdminModifyShare
0x140023f4a  cmp     eax, 0C0000034h
0x140023f4f  jnz     short loc_140023F5B
0x140023f51  mov     dword ptr [r14+44h], 906h
0x140023f59  jmp     short loc_140023F6A
0x140023f5b  cmp     eax, 0C000009Ah
0x140023f60  jnz     short loc_140023F6D
0x140023f62  mov     dword ptr [r14+44h], 839h
0x140023f6a  mov     eax, r12d
0x140023f6d  mov     rbx, [rsp+0E0h+arg_18]
0x140023f75  add     rsp, 0B0h
0x140023f7c  pop     r15
0x140023f7e  pop     r14
0x140023f80  pop     r13
0x140023f82  pop     r12
0x140023f84  pop     rdi
0x140023f85  pop     rsi
0x140023f86  pop     rbp
0x140023f87  retn
```
