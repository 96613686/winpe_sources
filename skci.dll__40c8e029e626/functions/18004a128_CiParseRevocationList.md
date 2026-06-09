# CiParseRevocationList

- ea: `0x18004a128`
- end: `0x18004a2c3`
- name: `CiParseRevocationList`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a2cc`

## callees

- `0x180006f10`
- `0x1800155d0`
- `0x18001673c`
- `0x180018a04`
- `0x18004a128`
- `0x18004cb6c`
- `0x18004db40`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x18004a1b4`
- `securekernel!RtlCompareMemory` at `0x18004a1b4`
- `securekernel!SkFreePool` at `0x18004a29a`
- `securekernel!SkFreePool` at `0x18004a29a`

## pseudocode

```c
__int64 __fastcall CiParseRevocationList(int a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *PoolHelper; // rax
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdi
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx

  PoolHelper = (char *)SkAllocatePoolHelper(258, 0x140u, 1919109443);
  v12 = PoolHelper;
  if ( PoolHelper )
  {
    v13 = MinCrypK_VerifySignedDataKMode(a1, a2, v10, v11, 0, a4, (__int64)PoolHelper);
    if ( v13 >= 0 )
    {
      if ( *(_DWORD *)v12 == 9 && RtlCompareMemory(qword_180037EA8, *((const void **)v12 + 1), 9u) == 9 )
      {
        if ( (int)MinAsn1ParseCTL(v12 + 16, v12 + 80) >= 0 )
        {
          if ( *((_DWORD *)v12 + 32) != 14 )
            goto LABEL_16;
          v14 = *((_QWORD *)v12 + 17);
          v15 = 0x401062B0A060C30LL - *(_QWORD *)v14;
          if ( *(_QWORD *)v14 == 0x401062B0A060C30LL )
          {
            v16 = *(unsigned int *)(v14 + 8);
            v15 = 1027047937 - v16;
            if ( v16 == 1027047937 )
              v15 = 259LL - *(unsigned __int16 *)(v14 + 12);
          }
          if ( v15 )
          {
LABEL_16:
            v13 = -1073740760;
          }
          else if ( (unsigned __int8)MinAsn1DecodeTime(v12 + 176, a5) )
          {
            v13 = MinCryptParseRevocationList(v12 + 240, v17, a3);
          }
          else
          {
            v13 = -1073740760;
          }
        }
        else
        {
          v13 = -1073740760;
        }
      }
      else
      {
        v13 = -1073740760;
      }
    }
  }
  else
  {
    v13 = -1073741801;
  }
  if ( v12 )
    SkFreePool(1, v12);
  if ( v13 < 0 )
    MincryptFreePolicyInfo(a4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18004a128  mov     [rsp+arg_18], r9
0x18004a12d  push    rbx
0x18004a12e  push    rsi
0x18004a12f  push    rdi
0x18004a130  push    r12
0x18004a132  push    r14
0x18004a134  push    r15
0x18004a136  sub     rsp, 58h
0x18004a13a  mov     r14, r9
0x18004a13d  mov     r12, r8
0x18004a140  mov     ebx, edx
0x18004a142  mov     r15, rcx
0x18004a145  mov     edx, 140h
0x18004a14a  lea     ecx, [rdx-3Eh]
0x18004a14d  mov     r8d, 72634943h
0x18004a153  call    SkAllocatePoolHelper
0x18004a158  mov     rdi, rax
0x18004a15b  mov     [rsp+88h+var_40], rax
0x18004a160  test    rax, rax
0x18004a163  jnz     short loc_18004A16F
0x18004a165  mov     ebx, 0C0000017h
0x18004a16a  jmp     loc_18004A28D
0x18004a16f  mov     [rsp+88h+var_58], rdi
0x18004a174  mov     [rsp+88h+var_60], r14
0x18004a179  mov     [rsp+88h+var_68], 0
0x18004a182  mov     edx, ebx
0x18004a184  mov     rcx, r15
0x18004a187  call    MinCrypK_VerifySignedDataKMode
0x18004a18c  mov     ebx, eax
0x18004a18e  mov     [rsp+88h+var_48], eax
0x18004a192  test    eax, eax
0x18004a194  js      loc_18004A28D
0x18004a19a  cmp     dword ptr [rdi], 9
0x18004a19d  jnz     loc_18004A26F
0x18004a1a3  mov     r8d, 9; Length
0x18004a1a9  mov     rdx, [rdi+8]; Source2
0x18004a1ad  lea     rcx, qword_180037EA8; Source1
0x18004a1b4  call    cs:__imp_RtlCompareMemory
0x18004a1bb  nop     dword ptr [rax+rax+00h]
0x18004a1c0  cmp     rax, 9
0x18004a1c4  jnz     loc_18004A26F
0x18004a1ca  lea     rcx, [rdi+10h]
0x18004a1ce  lea     rdx, [rdi+50h]
0x18004a1d2  call    MinAsn1ParseCTL
0x18004a1d7  test    eax, eax
0x18004a1d9  jns     short loc_18004A1E9
0x18004a1db  mov     ebx, 0C0000428h
0x18004a1e0  mov     [rsp+88h+var_48], ebx
0x18004a1e4  jmp     loc_18004A28D
0x18004a1e9  cmp     dword ptr [rdi+80h], 0Eh
0x18004a1f0  jnz     short loc_18004A264
0x18004a1f2  mov     rdx, [rdi+88h]
0x18004a1f9  mov     rcx, cs:qword_180037EB8
0x18004a200  sub     rcx, [rdx]
0x18004a203  jnz     short loc_18004A221
0x18004a205  mov     ecx, cs:dword_180037EC0
0x18004a20b  mov     eax, [rdx+8]
0x18004a20e  sub     rcx, rax
0x18004a211  jnz     short loc_18004A221
0x18004a213  movzx   ecx, cs:word_180037EC4
0x18004a21a  movzx   eax, word ptr [rdx+0Ch]
0x18004a21e  sub     rcx, rax
0x18004a221  test    rcx, rcx
0x18004a224  jnz     short loc_18004A264
0x18004a226  lea     rcx, [rdi+0B0h]
0x18004a22d  mov     rdx, [rsp+88h+arg_20]
0x18004a235  call    MinAsn1DecodeTime
0x18004a23a  test    al, al
0x18004a23c  jnz     short loc_18004A249
0x18004a23e  mov     ebx, 0C0000428h
0x18004a243  mov     [rsp+88h+var_48], ebx
0x18004a247  jmp     short loc_18004A28D
0x18004a249  lea     rcx, [rdi+0F0h]
0x18004a250  mov     r8, r12
0x18004a253  call    MinCryptParseRevocationList
0x18004a258  mov     ebx, eax
0x18004a25a  mov     [rsp+88h+var_48], eax
0x18004a25e  test    eax, eax
0x18004a260  js      short loc_18004A28D
0x18004a262  jmp     short loc_18004A28D
0x18004a264  mov     ebx, 0C0000428h
0x18004a269  mov     [rsp+88h+var_48], ebx
0x18004a26d  jmp     short loc_18004A28D
0x18004a26f  mov     ebx, 0C0000428h
0x18004a274  mov     [rsp+88h+var_48], ebx
0x18004a278  jmp     short loc_18004A28D
0x18004a27a  mov     ebx, eax
0x18004a27c  mov     [rsp+88h+var_48], eax
0x18004a280  mov     r14, [rsp+88h+arg_18]
0x18004a288  mov     rdi, [rsp+88h+var_40]
0x18004a28d  test    rdi, rdi
0x18004a290  jz      short loc_18004A2A6
0x18004a292  mov     rdx, rdi
0x18004a295  mov     ecx, 1
0x18004a29a  call    cs:__imp_SkFreePool
0x18004a2a1  nop     dword ptr [rax+rax+00h]
0x18004a2a6  test    ebx, ebx
0x18004a2a8  jns     short loc_18004A2B2
0x18004a2aa  mov     rcx, r14
0x18004a2ad  call    MincryptFreePolicyInfo
0x18004a2b2  mov     eax, ebx
0x18004a2b4  add     rsp, 58h
0x18004a2b8  pop     r15
0x18004a2ba  pop     r14
0x18004a2bc  pop     r12
0x18004a2be  pop     rdi
0x18004a2bf  pop     rsi
0x18004a2c0  pop     rbx
0x18004a2c1  retn
```
