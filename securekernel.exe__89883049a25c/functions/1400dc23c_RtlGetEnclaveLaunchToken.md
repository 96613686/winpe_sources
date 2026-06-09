# RtlGetEnclaveLaunchToken

- ea: `0x1400dc23c`
- end: `0x1400dc4df`
- name: `RtlGetEnclaveLaunchToken`
- size: `675`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14006b0e4`

## callees

- `0x1400dc23c`
- `0x1400dc704`
- `0x1400dc7f4`
- `0x1400dc918`
- `0x1400f3620`
- `0x1400f9a80`
- `0x1400ff484`
- `0x1400ff4fc`

## pseudocode

```c
__int64 __fastcall RtlGetEnclaveLaunchToken(__int64 a1, __int64 a2, void *a3)
{
  int v3; // r14d
  __int64 result; // rax
  int v7; // r12d
  int v8; // ecx
  _BYTE *v9; // rbx
  _BYTE *v10; // rdi
  int v11; // r13d
  unsigned int v12; // esi
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  bool v22; // zf
  int v23; // eax
  unsigned int v24; // ecx
  int v25; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-3Ch] BYREF
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  _BYTE *v28; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v29[3]; // [rsp+48h] [rbp-28h] BYREF

  v3 = 0;
  v29[1] = L"VBS";
  v25 = 0;
  v29[0] = L"ENCLAVE";
  v27 = 0;
  v28 = 0;
  v29[2] = 0;
  result = LdrFindResource_U(a1, v29, a3, &v27);
  if ( (int)result < 0 )
    return result;
  result = LdrAccessResource(a1, v27, &v28, &v25);
  if ( (int)result < 0 )
    return result;
  memset_0(a3, 0, 0x70u);
  v7 = v25;
  v8 = 0;
  v9 = v28;
  v10 = 0;
  v11 = 0;
  v26 = 0;
  v12 = 0;
  LODWORD(v27) = 0;
  while ( 1 )
  {
    if ( !v7 )
      return 3221225595LL;
    v13 = (char)*v9;
    if ( !*v9 )
      return 3221225595LL;
    if ( ((v8 - 2) & 0xFFFFFFFB) != 0 )
      break;
    if ( (_BYTE)v13 != 34 )
      goto LABEL_44;
    if ( v8 == 6 )
    {
      result = RtlpHandleEnclaveValueString((_DWORD)v10, (int)v9 - (int)v10, (_DWORD)a3, v12, v3);
LABEL_38:
      if ( (int)result < 0 )
        return result;
      v8 = 7;
      goto LABEL_44;
    }
    if ( v8 == 2 )
    {
      result = RtlpHandleEnclaveTokenName(v10, v9 - v10, &v26, &v27);
      if ( (int)result < 0 )
        return result;
      v12 = v26;
      if ( ((1 << v26) & v11) != 0 )
        return 3221225595LL;
      v3 = v27;
      v11 |= 1 << v26;
      v8 = 3;
    }
LABEL_44:
    ++v9;
    --v7;
  }
  v14 = v13 - 9;
  if ( !v14 || (v15 = v14 - 1) == 0 || (v16 = v15 - 3) == 0 || (v17 = v16 - 19) == 0 )
  {
    if ( v8 != 5 )
      goto LABEL_44;
    result = RtlpHandleEnclaveValueToken(v10, v9 - v10, a3, v12, v3);
    goto LABEL_38;
  }
  v18 = v17 - 2;
  if ( !v18 )
  {
    if ( v8 == 4 )
    {
      v8 = 6;
    }
    else
    {
      if ( v8 != 1 )
        return 3221225595LL;
      v8 = 2;
    }
    v10 = v9 + 1;
    goto LABEL_44;
  }
  v19 = v18 - 10;
  if ( !v19 )
  {
    if ( v8 == 5 )
    {
      result = RtlpHandleEnclaveValueToken(v10, v9 - v10, a3, v12, v3);
      if ( (int)result < 0 )
        return result;
LABEL_21:
      v8 = 1;
      goto LABEL_44;
    }
    v22 = v8 == 7;
LABEL_20:
    if ( !v22 )
      return 3221225595LL;
    goto LABEL_21;
  }
  v20 = v19 - 14;
  if ( !v20 )
  {
    if ( v8 != 3 )
      return 3221225595LL;
    v8 = 4;
    goto LABEL_44;
  }
  v21 = v20 - 65;
  if ( !v21 )
  {
    v22 = v8 == 0;
    goto LABEL_20;
  }
  if ( v21 != 2 )
  {
    if ( v8 != 5 )
    {
      if ( v8 != 4 )
        return 3221225595LL;
      v10 = v9;
      v8 = 5;
    }
    goto LABEL_44;
  }
  if ( v8 != 5 )
  {
    if ( v8 == 7 )
      return 0;
    return 3221225595LL;
  }
  v23 = RtlpHandleEnclaveValueToken(v10, v9 - v10, a3, v12, v3);
  v24 = 0;
  if ( v23 < 0 )
    return (unsigned int)v23;
  return v24;
}

```

## disassembly

```asm
0x1400dc23c  mov     [rsp-38h+arg_8], rbx
0x1400dc241  push    rbp
0x1400dc242  push    rsi
0x1400dc243  push    rdi
0x1400dc244  push    r12
0x1400dc246  push    r13
0x1400dc248  push    r14
0x1400dc24a  push    r15
0x1400dc24c  mov     rbp, rsp
0x1400dc24f  sub     rsp, 70h
0x1400dc253  mov     rax, cs:__security_cookie
0x1400dc25a  xor     rax, rsp
0x1400dc25d  mov     [rbp+var_10], rax
0x1400dc261  xor     r14d, r14d
0x1400dc264  lea     rax, aVbs; "VBS"
0x1400dc26b  mov     [rbp+var_20], rax
0x1400dc26f  lea     r9, [rbp+var_38]
0x1400dc273  lea     rax, aEnclave; "ENCLAVE"
0x1400dc27a  mov     [rbp+var_40], r14d
0x1400dc27e  lea     rdx, [rbp+var_28]
0x1400dc282  mov     [rbp+var_28], rax
0x1400dc286  mov     r15, r8
0x1400dc289  mov     [rbp+var_38], r14
0x1400dc28d  mov     rbx, rcx
0x1400dc290  mov     [rbp+var_30], r14
0x1400dc294  mov     [rbp+var_18], r14
0x1400dc298  call    LdrFindResource_U
0x1400dc29d  test    eax, eax
0x1400dc29f  js      loc_1400DC4BA
0x1400dc2a5  mov     rdx, [rbp+var_38]
0x1400dc2a9  lea     r9, [rbp+var_40]
0x1400dc2ad  lea     r8, [rbp+var_30]
0x1400dc2b1  mov     rcx, rbx
0x1400dc2b4  call    LdrAccessResource
0x1400dc2b9  test    eax, eax
0x1400dc2bb  js      loc_1400DC4BA
0x1400dc2c1  xor     edx, edx; Val
0x1400dc2c3  lea     r8d, [r14+70h]; Size
0x1400dc2c7  mov     rcx, r15; void *
0x1400dc2ca  call    memset_0
0x1400dc2cf  mov     r12d, [rbp+var_40]
0x1400dc2d3  mov     ecx, r14d
0x1400dc2d6  mov     rbx, [rbp+var_30]
0x1400dc2da  mov     edi, r14d
0x1400dc2dd  mov     r13d, r14d
0x1400dc2e0  mov     [rbp+var_3C], r14d
0x1400dc2e4  mov     esi, r14d
0x1400dc2e7  mov     dword ptr [rbp+var_38], r14d
0x1400dc2eb  test    r12d, r12d
0x1400dc2ee  jz      loc_1400DC4B5
0x1400dc2f4  movsx   edx, byte ptr [rbx]
0x1400dc2f7  test    dl, dl
0x1400dc2f9  jz      loc_1400DC4B5
0x1400dc2ff  lea     eax, [rcx-2]
0x1400dc302  test    eax, 0FFFFFFFBh
0x1400dc307  jz      loc_1400DC40A
0x1400dc30d  sub     edx, 9
0x1400dc310  jz      loc_1400DC3E6
0x1400dc316  sub     edx, 1
0x1400dc319  jz      loc_1400DC3E6
0x1400dc31f  sub     edx, 3
0x1400dc322  jz      loc_1400DC3E6
0x1400dc328  sub     edx, 13h
0x1400dc32b  jz      loc_1400DC3E6
0x1400dc331  sub     edx, 2
0x1400dc334  jz      loc_1400DC3C3
0x1400dc33a  sub     edx, 0Ah
0x1400dc33d  jz      short loc_1400DC396
0x1400dc33f  sub     edx, 0Eh
0x1400dc342  jz      short loc_1400DC383
0x1400dc344  sub     edx, 41h ; 'A'
0x1400dc347  jz      short loc_1400DC371
0x1400dc349  cmp     edx, 2
0x1400dc34c  jz      loc_1400DC483
0x1400dc352  cmp     ecx, 5
0x1400dc355  jz      loc_1400DC478
0x1400dc35b  cmp     ecx, 4
0x1400dc35e  jnz     loc_1400DC4B5
0x1400dc364  mov     rdi, rbx
0x1400dc367  mov     ecx, 5
0x1400dc36c  jmp     loc_1400DC478
0x1400dc371  test    ecx, ecx
0x1400dc373  jnz     loc_1400DC4B5
0x1400dc379  mov     ecx, 1
0x1400dc37e  jmp     loc_1400DC478
0x1400dc383  cmp     ecx, 3
0x1400dc386  jnz     loc_1400DC4B5
0x1400dc38c  mov     ecx, 4
0x1400dc391  jmp     loc_1400DC478
0x1400dc396  cmp     ecx, 5
0x1400dc399  jnz     short loc_1400DC3BE
0x1400dc39b  mov     rdx, rbx
0x1400dc39e  mov     [rsp+70h+var_50], r14d
0x1400dc3a3  sub     rdx, rdi
0x1400dc3a6  mov     r9d, esi
0x1400dc3a9  mov     r8, r15
0x1400dc3ac  mov     rcx, rdi
0x1400dc3af  call    RtlpHandleEnclaveValueToken
0x1400dc3b4  test    eax, eax
0x1400dc3b6  js      loc_1400DC4BA
0x1400dc3bc  jmp     short loc_1400DC379
0x1400dc3be  cmp     ecx, 7
0x1400dc3c1  jmp     short loc_1400DC373
0x1400dc3c3  cmp     ecx, 4
0x1400dc3c6  jnz     short loc_1400DC3CF
0x1400dc3c8  mov     ecx, 6
0x1400dc3cd  jmp     short loc_1400DC3DD
0x1400dc3cf  cmp     ecx, 1
0x1400dc3d2  jnz     loc_1400DC4B5
0x1400dc3d8  mov     ecx, 2
0x1400dc3dd  lea     rdi, [rbx+1]
0x1400dc3e1  jmp     loc_1400DC478
0x1400dc3e6  cmp     ecx, 5
0x1400dc3e9  jnz     loc_1400DC478
0x1400dc3ef  mov     rdx, rbx
0x1400dc3f2  mov     [rsp+70h+var_50], r14d
0x1400dc3f7  sub     rdx, rdi
0x1400dc3fa  mov     r9d, esi
0x1400dc3fd  mov     r8, r15
0x1400dc400  mov     rcx, rdi
0x1400dc403  call    RtlpHandleEnclaveValueToken
0x1400dc408  jmp     short loc_1400DC42D
0x1400dc40a  cmp     dl, 22h ; '"'
0x1400dc40d  jnz     short loc_1400DC478
0x1400dc40f  cmp     ecx, 6
0x1400dc412  jnz     short loc_1400DC43C
0x1400dc414  mov     rdx, rbx
0x1400dc417  mov     [rsp+70h+var_50], r14d
0x1400dc41c  sub     rdx, rdi
0x1400dc41f  mov     r9d, esi
0x1400dc422  mov     r8, r15
0x1400dc425  mov     rcx, rdi
0x1400dc428  call    RtlpHandleEnclaveValueString
0x1400dc42d  test    eax, eax
0x1400dc42f  js      loc_1400DC4BA
0x1400dc435  mov     ecx, 7
0x1400dc43a  jmp     short loc_1400DC478
0x1400dc43c  cmp     ecx, 2
0x1400dc43f  jnz     short loc_1400DC478
0x1400dc441  mov     rdx, rbx
0x1400dc444  lea     r9, [rbp+var_38]
0x1400dc448  sub     rdx, rdi
0x1400dc44b  lea     r8, [rbp+var_3C]
0x1400dc44f  mov     rcx, rdi
0x1400dc452  call    RtlpHandleEnclaveTokenName
0x1400dc457  test    eax, eax
0x1400dc459  js      short loc_1400DC4BA
0x1400dc45b  mov     esi, [rbp+var_3C]
0x1400dc45e  mov     eax, 1
0x1400dc463  mov     ecx, esi
0x1400dc465  shl     eax, cl
0x1400dc467  test    r13d, eax
0x1400dc46a  jnz     short loc_1400DC4B5
0x1400dc46c  mov     r14d, dword ptr [rbp+var_38]
0x1400dc470  or      r13d, eax
0x1400dc473  mov     ecx, 3
0x1400dc478  inc     rbx
0x1400dc47b  dec     r12d
0x1400dc47e  jmp     loc_1400DC2EB
0x1400dc483  cmp     ecx, 5
0x1400dc486  jnz     short loc_1400DC4AC
0x1400dc488  sub     rbx, rdi
0x1400dc48b  mov     [rsp+70h+var_50], r14d
0x1400dc490  mov     rdx, rbx
0x1400dc493  mov     r9d, esi
0x1400dc496  mov     r8, r15
0x1400dc499  mov     rcx, rdi
0x1400dc49c  call    RtlpHandleEnclaveValueToken
0x1400dc4a1  xor     ecx, ecx
0x1400dc4a3  test    eax, eax
0x1400dc4a5  cmovs   ecx, eax
0x1400dc4a8  mov     eax, ecx
0x1400dc4aa  jmp     short loc_1400DC4BA
0x1400dc4ac  cmp     ecx, 7
0x1400dc4af  jnz     short loc_1400DC4B5
0x1400dc4b1  xor     eax, eax
0x1400dc4b3  jmp     short loc_1400DC4BA
0x1400dc4b5  mov     eax, 0C000007Bh
0x1400dc4ba  mov     rcx, [rbp+var_10]
0x1400dc4be  xor     rcx, rsp; StackCookie
0x1400dc4c1  call    __security_check_cookie
0x1400dc4c6  mov     rbx, [rsp+70h+arg_8]
0x1400dc4ce  add     rsp, 70h
0x1400dc4d2  pop     r15
0x1400dc4d4  pop     r14
0x1400dc4d6  pop     r13
0x1400dc4d8  pop     r12
0x1400dc4da  pop     rdi
0x1400dc4db  pop     rsi
0x1400dc4dc  pop     rbp
0x1400dc4dd  retn
```
