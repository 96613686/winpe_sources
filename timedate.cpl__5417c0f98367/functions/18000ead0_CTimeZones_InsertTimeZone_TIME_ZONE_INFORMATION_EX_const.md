# CTimeZones::_InsertTimeZone(TIME_ZONE_INFORMATION_EX const *)

- ea: `0x18000ead0`
- end: `0x18000ebd5`
- name: `?_InsertTimeZone@CTimeZones@@AEAAJPEBUTIME_ZONE_INFORMATION_EX@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(CTimeZones *__hidden this, const struct TIME_ZONE_INFORMATION_EX *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ebe0`

## callees

- `0x180001dfc`
- `0x18000ead0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eba0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000eba0`

## pseudocode

```c
__int64 __fastcall CTimeZones::_InsertTimeZone(__int64 **this, const struct TIME_ZONE_INFORMATION_EX *a2)
{
  unsigned int v4; // esi
  char *v5; // rax
  char *v6; // rbx
  _OWORD *v7; // r8
  __int64 v8; // rax
  __int128 v9; // xmm1
  __int64 *v10; // rdi
  _QWORD *v11; // rsi
  int v12; // eax

  v4 = -2147024882;
  v5 = (char *)operator new(0x210u);
  v6 = v5;
  if ( v5 )
  {
    v7 = v5 + 8;
    v8 = 4;
    do
    {
      *v7 = *(_OWORD *)a2;
      v7[1] = *((_OWORD *)a2 + 1);
      v7[2] = *((_OWORD *)a2 + 2);
      v7[3] = *((_OWORD *)a2 + 3);
      v7[4] = *((_OWORD *)a2 + 4);
      v7[5] = *((_OWORD *)a2 + 5);
      v7[6] = *((_OWORD *)a2 + 6);
      v9 = *((_OWORD *)a2 + 7);
      a2 = (const struct TIME_ZONE_INFORMATION_EX *)((char *)a2 + 128);
      v7[7] = v9;
      v7 += 8;
      --v8;
    }
    while ( v8 );
    *(_DWORD *)v7 = *(_DWORD *)a2;
    *(_QWORD *)v6 = 0;
    v10 = *this;
    if ( !*this )
      goto LABEL_12;
    v11 = 0;
    do
    {
      v12 = *((_DWORD *)v10 + 130);
      if ( *((_DWORD *)v6 + 130) > v12
        || *((_DWORD *)v6 + 130) == v12 && CompareStringW(0x400u, 0, (PCNZWCH)v6 + 4, -1, (PCNZWCH)v10 + 4, -1) == 1 )
      {
        break;
      }
      v11 = v10;
      v10 = (__int64 *)*v10;
    }
    while ( v10 );
    *(_QWORD *)v6 = v10;
    if ( v11 )
      *v11 = v6;
    else
LABEL_12:
      *this = (__int64 *)v6;
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000ead0  push    rbx
0x18000ead2  push    rbp
0x18000ead3  push    rsi
0x18000ead4  push    rdi
0x18000ead5  push    r14
0x18000ead7  sub     rsp, 30h
0x18000eadb  mov     r14, rcx
0x18000eade  mov     rdi, rdx
0x18000eae1  mov     ecx, 210h; Size
0x18000eae6  mov     esi, 8007000Eh
0x18000eaeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eaf0  mov     rbx, rax
0x18000eaf3  test    rax, rax
0x18000eaf6  jz      loc_18000EBC8
0x18000eafc  lea     r8, [rax+8]
0x18000eb00  mov     eax, 4
0x18000eb05  lea     ecx, [rax+7Ch]
0x18000eb08  movups  xmm0, xmmword ptr [rdi]
0x18000eb0b  movups  xmmword ptr [r8], xmm0
0x18000eb0f  movups  xmm1, xmmword ptr [rdi+10h]
0x18000eb13  movups  xmmword ptr [r8+10h], xmm1
0x18000eb18  movups  xmm0, xmmword ptr [rdi+20h]
0x18000eb1c  movups  xmmword ptr [r8+20h], xmm0
0x18000eb21  movups  xmm1, xmmword ptr [rdi+30h]
0x18000eb25  movups  xmmword ptr [r8+30h], xmm1
0x18000eb2a  movups  xmm0, xmmword ptr [rdi+40h]
0x18000eb2e  movups  xmmword ptr [r8+40h], xmm0
0x18000eb33  movups  xmm1, xmmword ptr [rdi+50h]
0x18000eb37  movups  xmmword ptr [r8+50h], xmm1
0x18000eb3c  movups  xmm0, xmmword ptr [rdi+60h]
0x18000eb40  movups  xmmword ptr [r8+60h], xmm0
0x18000eb45  movups  xmm1, xmmword ptr [rdi+70h]
0x18000eb49  add     rdi, rcx
0x18000eb4c  movups  xmmword ptr [r8+70h], xmm1
0x18000eb51  add     r8, rcx
0x18000eb54  sub     rax, 1
0x18000eb58  jnz     short loc_18000EB08
0x18000eb5a  mov     eax, [rdi]
0x18000eb5c  mov     [r8], eax
0x18000eb5f  mov     qword ptr [rbx], 0
0x18000eb66  mov     rdi, [r14]
0x18000eb69  test    rdi, rdi
0x18000eb6c  jz      short loc_18000EBC3
0x18000eb6e  xor     esi, esi
0x18000eb70  mov     eax, [rdi+208h]
0x18000eb76  cmp     [rbx+208h], eax
0x18000eb7c  jg      short loc_18000EBB6
0x18000eb7e  jnz     short loc_18000EBAB
0x18000eb80  lea     rax, [rdi+8]
0x18000eb84  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000eb8c  or      r9d, 0FFFFFFFFh; cchCount1
0x18000eb90  mov     [rsp+58h+lpString2], rax; lpString2
0x18000eb95  lea     r8, [rbx+8]; lpString1
0x18000eb99  xor     edx, edx; dwCmpFlags
0x18000eb9b  mov     ecx, 400h; Locale
0x18000eba0  call    cs:__imp_CompareStringW
0x18000eba6  cmp     eax, 1
0x18000eba9  jz      short loc_18000EBB6
0x18000ebab  mov     rsi, rdi
0x18000ebae  mov     rdi, [rdi]
0x18000ebb1  test    rdi, rdi
0x18000ebb4  jnz     short loc_18000EB70
0x18000ebb6  mov     [rbx], rdi
0x18000ebb9  test    rsi, rsi
0x18000ebbc  jz      short loc_18000EBC3
0x18000ebbe  mov     [rsi], rbx
0x18000ebc1  jmp     short loc_18000EBC6
0x18000ebc3  mov     [r14], rbx
0x18000ebc6  xor     esi, esi
0x18000ebc8  mov     eax, esi
0x18000ebca  add     rsp, 30h
0x18000ebce  pop     r14
0x18000ebd0  pop     rdi
0x18000ebd1  pop     rsi
0x18000ebd2  pop     rbp
0x18000ebd3  pop     rbx
0x18000ebd4  retn
```
