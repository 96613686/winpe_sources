# CipValidateSigningPolicyForScenario

- ea: `0x180049d40`
- end: `0x180049e76`
- name: `CipValidateSigningPolicyForScenario`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180049e7c`
- `0x18004a364`

## callees

- `0x18004756c`
- `0x180049c2c`
- `0x180049d40`

## import_xrefs

- `securekernel!SeQuerySecureBootPlatformManifest` at `0x180049dff`
- `securekernel!SeQuerySecureBootPlatformManifest` at `0x180049dff`

## pseudocode

```c
__int64 __fastcall CipValidateSigningPolicyForScenario(int a1, __int64 a2, __int64 a3, char a4, char a5, _DWORD *a6)
{
  int v7; // r13d
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // edi
  __int64 v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rsi
  int SecureBootPlatformManifest; // eax
  __int64 v17; // [rsp+20h] [rbp-48h]
  char v19; // [rsp+88h] [rbp+20h]

  v19 = a4;
  v7 = a3;
  v8 = a1;
  v9 = -1073740760;
  v10 = 0;
LABEL_2:
  if ( v10 > v7 )
    return v9;
  v11 = v8;
  v12 = 0;
  v13 = v10 + 12LL * v8;
  v17 = v13;
  while ( 1 )
  {
    if ( (unsigned int)v12 >= g_CiScenarios[v13 + 8] )
    {
      v8 = a1;
      ++v10;
      goto LABEL_2;
    }
    v14 = *(unsigned int *)(*(_QWORD *)&g_CiScenarios[12 * v11 + 2 + 2 * v10] + 4 * v12);
    if ( (unsigned int)v14 >= g_CiSignersCount )
      return 3225616387LL;
    LOBYTE(a3) = a4;
    if ( !(unsigned __int8)CipValidateChainAgainstSigner(a2, g_CiSigners + 40 * v14, a3) )
      goto LABEL_14;
    if ( a5 || !CipRequirePlatformManifestForSigner(v14) )
      break;
    if ( a2 )
    {
      SecureBootPlatformManifest = SeQuerySecureBootPlatformManifest(a2 + 72, 32);
      v9 = SecureBootPlatformManifest;
      if ( SecureBootPlatformManifest >= 0 )
        break;
      if ( SecureBootPlatformManifest == -1073741275 )
        v9 = -1058340861;
    }
    else
    {
      v9 = -1058340861;
    }
LABEL_14:
    v13 = v17;
    a4 = v19;
    v12 = (unsigned int)(v12 + 1);
  }
  if ( a6 )
    *a6 = v14;
  return 0;
}

```

## disassembly

```asm
0x180049d40  mov     [rsp+arg_8], rbx
0x180049d45  mov     [rsp+arg_18], r9b
0x180049d4a  mov     [rsp+arg_0], ecx
0x180049d4e  push    rbp
0x180049d4f  push    rsi
0x180049d50  push    rdi
0x180049d51  push    r12
0x180049d53  push    r13
0x180049d55  push    r14
0x180049d57  push    r15
0x180049d59  sub     rsp, 30h
0x180049d5d  mov     r15, rdx
0x180049d60  mov     r13d, r8d
0x180049d63  lea     rdx, g_CiScenarios
0x180049d6a  mov     eax, ecx
0x180049d6c  mov     ebx, 0C0000428h
0x180049d71  xor     edi, edi
0x180049d73  cmp     edi, r13d
0x180049d76  jg      loc_180049E5E
0x180049d7c  movsxd  r14, eax
0x180049d7f  xor     ebp, ebp
0x180049d81  movsxd  r12, edi
0x180049d84  lea     rax, [r14+r14*2]
0x180049d88  lea     rax, [r12+rax*4]
0x180049d8c  mov     [rsp+68h+var_48], rax
0x180049d91  cmp     ebp, [rdx+rax*4+20h]
0x180049d95  jnb     loc_180049E39
0x180049d9b  lea     rax, [r14+r14*2]
0x180049d9f  lea     rax, [r12+rax*2]
0x180049da3  mov     rax, [rdx+rax*8+8]
0x180049da8  mov     esi, [rax+rbp*4]
0x180049dab  cmp     esi, cs:g_CiSignersCount
0x180049db1  jnb     loc_180049E57
0x180049db7  mov     rax, cs:g_CiSigners
0x180049dbe  lea     rcx, [rsi+rsi*4]
0x180049dc2  mov     r8b, r9b
0x180049dc5  lea     rdx, [rax+rcx*8]
0x180049dc9  mov     rcx, r15
0x180049dcc  call    CipValidateChainAgainstSigner
0x180049dd1  test    al, al
0x180049dd3  jz      short loc_180049E1E
0x180049dd5  cmp     [rsp+68h+arg_20], 0
0x180049ddd  jnz     short loc_180049E44
0x180049ddf  mov     ecx, esi
0x180049de1  call    CipRequirePlatformManifestForSigner
0x180049de6  test    al, al
0x180049de8  jz      short loc_180049E44
0x180049dea  test    r15, r15
0x180049ded  jnz     short loc_180049DF6
0x180049def  mov     ebx, 0C0EB0003h
0x180049df4  jmp     short loc_180049E1E
0x180049df6  lea     rcx, [r15+48h]
0x180049dfa  mov     edx, 20h ; ' '
0x180049dff  call    cs:__imp_SeQuerySecureBootPlatformManifest
0x180049e06  nop     dword ptr [rax+rax+00h]
0x180049e0b  mov     ebx, eax
0x180049e0d  test    eax, eax
0x180049e0f  jns     short loc_180049E44
0x180049e11  cmp     eax, 0C0000225h
0x180049e16  mov     eax, 0C0EB0003h
0x180049e1b  cmovz   ebx, eax
0x180049e1e  mov     rax, [rsp+68h+var_48]
0x180049e23  lea     rdx, g_CiScenarios
0x180049e2a  mov     r9b, [rsp+68h+arg_18]
0x180049e32  inc     ebp
0x180049e34  jmp     loc_180049D91
0x180049e39  mov     eax, [rsp+68h+arg_0]
0x180049e3d  inc     edi
0x180049e3f  jmp     loc_180049D73
0x180049e44  mov     rax, [rsp+68h+arg_28]
0x180049e4c  test    rax, rax
0x180049e4f  jz      short loc_180049E53
0x180049e51  mov     [rax], esi
0x180049e53  xor     eax, eax
0x180049e55  jmp     short loc_180049E60
0x180049e57  mov     eax, 0C0430003h
0x180049e5c  jmp     short loc_180049E60
0x180049e5e  mov     eax, ebx
0x180049e60  mov     rbx, [rsp+68h+arg_8]
0x180049e65  add     rsp, 30h
0x180049e69  pop     r15
0x180049e6b  pop     r14
0x180049e6d  pop     r13
0x180049e6f  pop     r12
0x180049e71  pop     rdi
0x180049e72  pop     rsi
0x180049e73  pop     rbp
0x180049e74  retn
```
