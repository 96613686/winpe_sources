# SkProvisionDumpKeys

- ea: `0x1400bf1ec`
- end: `0x1400bf381`
- name: `SkProvisionDumpKeys`
- size: `405`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140014dd0`

## callees

- `0x140037e68`
- `0x140038af8`
- `0x1400baac4`
- `0x1400bacac`
- `0x1400bb060`
- `0x1400bc544`
- `0x1400bf1ec`
- `0x1400bf388`

## string_xrefs

- `0x1400bf201`: `\SystemRoot\system32\hvdumpkey.p7b`
- `0x1400bf216`: `\SystemRoot\system32\skdumpkey.p7b`

## pseudocode

```c
__int64 SkProvisionDumpKeys()
{
  int CrashDumpEncryptionContext; // ebx
  __int64 v1; // rdi
  int DumpKeys; // eax
  __int64 v3; // rsi
  __int64 v4; // r14
  unsigned int *v5; // rdi
  unsigned int v6; // r15d
  _QWORD *v7; // r14
  __int64 i; // rdi
  __int64 v9; // rdx
  __int64 v11; // [rsp+40h] [rbp-39h]
  int v12; // [rsp+48h] [rbp-31h]
  int v13; // [rsp+4Ch] [rbp-2Dh]
  __int128 v14; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-19h]
  int v16[4]; // [rsp+70h] [rbp-9h]
  _DWORD v17[2]; // [rsp+80h] [rbp+7h] BYREF
  const wchar_t *v18; // [rsp+88h] [rbp+Fh]
  int v19; // [rsp+90h] [rbp+17h]
  const wchar_t *v20; // [rsp+98h] [rbp+1Fh]
  __int64 v21; // [rsp+E0h] [rbp+67h] BYREF

  v17[0] = 4587588;
  v18 = L"\\SystemRoot\\system32\\hvdumpkey.p7b";
  v19 = 4587588;
  v20 = L"\\SystemRoot\\system32\\skdumpkey.p7b";
  CrashDumpEncryptionContext = 0;
  v11 = 0;
  v15[0] = &IumHvCrashDumpEncryptionHandle;
  v1 = 0;
  v14 = 0;
  v12 = 1;
  v15[1] = &IumSkCrashDumpEncryptionHandle;
  *(__m128i *)v16 = _mm_load_si128((const __m128i *)&_xmm);
  v13 = 1;
  while ( (unsigned int)v1 < 2 )
  {
    DumpKeys = SkpLoadDumpKeys(&v17[4 * (unsigned int)v1], &v15[v1 - 2]);
    CrashDumpEncryptionContext = DumpKeys;
    if ( ((DumpKeys + 0x80000000) & 0x80000000) == 0 && DumpKeys != -1073741772 )
      goto LABEL_15;
    v1 = (unsigned int)(v1 + 1);
  }
  v3 = 0;
  do
  {
    v4 = *((unsigned int *)&v11 + v3);
    v5 = (unsigned int *)v15[v4 - 2];
    if ( v5 )
    {
      v6 = v16[v3];
      v21 = 0;
      CrashDumpEncryptionContext = SkpGetCrashDumpEncryptionContext(v6, &v21);
      if ( CrashDumpEncryptionContext < 0 )
        break;
      CrashDumpEncryptionContext = SkpInstallEncryptionKey(
                                     v6,
                                     v21,
                                     (unsigned int)v5 + *((unsigned __int8 *)v5 + 8) + 9,
                                     v5[1],
                                     1,
                                     (char *)v5 + 9,
                                     *((unsigned __int8 *)v5 + 8));
      if ( CrashDumpEncryptionContext >= 0 )
      {
        v7 = (_QWORD *)v15[v4];
        if ( *v7 )
        {
          SkKSDeleteKey();
          *v7 = 0;
        }
        SkKSAddKey(v7, v5, *v5);
      }
      SkpReleaseCrashDumpEncryptionContext(v6);
      if ( CrashDumpEncryptionContext < 0 )
        break;
    }
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 4 );
LABEL_15:
  for ( i = 0; i != 2; ++i )
  {
    v9 = v15[i - 2];
    if ( v9 )
      SkFreePool(1, v9);
  }
  return (unsigned int)CrashDumpEncryptionContext;
}

```

## disassembly

```asm
0x1400bf1ec  push    rbp
0x1400bf1ee  push    rbx
0x1400bf1ef  push    rsi
0x1400bf1f0  push    rdi
0x1400bf1f1  push    r14
0x1400bf1f3  push    r15
0x1400bf1f5  lea     rbp, [rsp-2Fh]
0x1400bf1fa  sub     rsp, 0A8h
0x1400bf201  lea     rax, aSystemrootSyst; "\\SystemRoot\\system32\\hvdumpkey.p7b"
0x1400bf208  mov     [rbp+57h+var_50], 460044h
0x1400bf20f  mov     [rbp+57h+var_48], rax
0x1400bf213  xorps   xmm0, xmm0
0x1400bf216  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\system32\\skdumpkey.p7b"
0x1400bf21d  mov     [rbp+57h+var_40], 460044h
0x1400bf224  mov     [rbp+57h+var_38], rax
0x1400bf228  xor     ebx, ebx
0x1400bf22a  lea     rax, IumHvCrashDumpEncryptionHandle
0x1400bf231  mov     [rbp+57h+var_90], 0
0x1400bf239  mov     [rbp+57h+var_70], rax
0x1400bf23d  xor     edi, edi
0x1400bf23f  movdqu  [rbp+57h+var_80], xmm0
0x1400bf244  lea     rax, IumSkCrashDumpEncryptionHandle
0x1400bf24b  mov     [rbp+57h+var_88], 1
0x1400bf252  movdqa  xmm0, cs:__xmm@00000007000000020000000600000001
0x1400bf25a  mov     esi, 80000000h
0x1400bf25f  mov     [rbp+57h+var_68], rax
0x1400bf263  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x1400bf268  mov     [rbp+57h+var_84], 1
0x1400bf26f  cmp     edi, 2
0x1400bf272  jnb     short loc_1400BF2A6
0x1400bf274  mov     eax, edi
0x1400bf276  lea     rdx, [rbp+57h+var_80]
0x1400bf27a  shl     rax, 4
0x1400bf27e  lea     rcx, [rbp+57h+var_50]
0x1400bf282  add     rcx, rax
0x1400bf285  lea     rdx, [rdx+rdi*8]
0x1400bf289  call    SkpLoadDumpKeys
0x1400bf28e  mov     ebx, eax
0x1400bf290  lea     ecx, [rax+rsi]
0x1400bf293  test    esi, ecx
0x1400bf295  jnz     short loc_1400BF2A2
0x1400bf297  cmp     eax, 0C0000034h
0x1400bf29c  jnz     loc_1400BF34F
0x1400bf2a2  inc     edi
0x1400bf2a4  jmp     short loc_1400BF26F
0x1400bf2a6  xor     esi, esi
0x1400bf2a8  mov     r14d, dword ptr [rbp+rsi*4+57h+var_90]
0x1400bf2ad  mov     rdi, qword ptr [rbp+r14*8+57h+var_80]
0x1400bf2b2  test    rdi, rdi
0x1400bf2b5  jz      loc_1400BF344
0x1400bf2bb  mov     r15d, [rbp+rsi*4+57h+var_60]
0x1400bf2c0  lea     rdx, [rbp+57h+arg_0]
0x1400bf2c4  mov     ecx, r15d
0x1400bf2c7  mov     [rbp+57h+arg_0], 0
0x1400bf2cf  call    SkpGetCrashDumpEncryptionContext
0x1400bf2d4  mov     ebx, eax
0x1400bf2d6  test    eax, eax
0x1400bf2d8  js      short loc_1400BF34F
0x1400bf2da  movzx   eax, byte ptr [rdi+8]
0x1400bf2de  lea     rcx, [rdi+9]
0x1400bf2e2  mov     r9d, [rdi+4]; int
0x1400bf2e6  mov     rdx, [rbp+57h+arg_0]; int
0x1400bf2ea  mov     [rsp+0D0h+Size], rax; Size
0x1400bf2ef  mov     [rsp+0D0h+Src], rcx; Src
0x1400bf2f4  lea     r8, [rax+9]
0x1400bf2f8  add     r8, rdi; int
0x1400bf2fb  mov     [rsp+0D0h+var_B0], 1; int
0x1400bf303  mov     ecx, r15d; int
0x1400bf306  call    SkpInstallEncryptionKey
0x1400bf30b  mov     ebx, eax
0x1400bf30d  test    eax, eax
0x1400bf30f  js      short loc_1400BF338
0x1400bf311  mov     r14, [rbp+r14*8+57h+var_70]
0x1400bf316  mov     rcx, [r14]
0x1400bf319  test    rcx, rcx
0x1400bf31c  jz      short loc_1400BF32A
0x1400bf31e  call    SkKSDeleteKey
0x1400bf323  mov     qword ptr [r14], 0
0x1400bf32a  mov     r8d, [rdi]
0x1400bf32d  mov     rdx, rdi
0x1400bf330  mov     rcx, r14
0x1400bf333  call    SkKSAddKey
0x1400bf338  mov     ecx, r15d
0x1400bf33b  call    SkpReleaseCrashDumpEncryptionContext
0x1400bf340  test    ebx, ebx
0x1400bf342  js      short loc_1400BF34F
0x1400bf344  inc     esi
0x1400bf346  cmp     esi, 4
0x1400bf349  jb      loc_1400BF2A8
0x1400bf34f  xor     edi, edi
0x1400bf351  mov     rdx, qword ptr [rbp+rdi*8+57h+var_80]
0x1400bf356  test    rdx, rdx
0x1400bf359  jz      short loc_1400BF365
0x1400bf35b  mov     ecx, 1
0x1400bf360  call    SkFreePool
0x1400bf365  inc     rdi
0x1400bf368  cmp     rdi, 2
0x1400bf36c  jnz     short loc_1400BF351
0x1400bf36e  mov     eax, ebx
0x1400bf370  add     rsp, 0A8h
0x1400bf377  pop     r15
0x1400bf379  pop     r14
0x1400bf37b  pop     rdi
0x1400bf37c  pop     rsi
0x1400bf37d  pop     rbx
0x1400bf37e  pop     rbp
0x1400bf37f  retn
```
