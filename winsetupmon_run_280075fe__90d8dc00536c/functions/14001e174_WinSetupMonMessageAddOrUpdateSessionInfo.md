# WinSetupMonMessageAddOrUpdateSessionInfo

- ea: `0x14001e174`
- end: `0x14001e234`
- name: `WinSetupMonMessageAddOrUpdateSessionInfo`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140007668`

## callees

- `0x140001220`
- `0x1400030b8`
- `0x14000f930`
- `0x14001e044`
- `0x14001e10c`
- `0x14001e174`

## pseudocode

```c
__int64 __fastcall WinSetupMonMessageAddOrUpdateSessionInfo(char a1, void *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // r8
  __int64 v7; // rdx
  UNICODE_STRING v9; // [rsp+28h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-40h] BYREF
  __int128 v11; // [rsp+48h] [rbp-30h] BYREF
  __int128 v12; // [rsp+58h] [rbp-20h] BYREF
  __int64 v13; // [rsp+68h] [rbp-10h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  SourceString = 0;
  v9 = 0;
  if ( a1 )
    RtlCopyFromUser(&v11, a2, 0x28u);
  else
    RtlCopyVolatileMemory(&v11, a2, 0x28u);
  LOBYTE(v3) = a1;
  v5 = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&SourceString, (char *)&v11 + 8, v3);
  if ( v5 >= 0 )
  {
    LOBYTE(v6) = a1;
    v5 = WinSetupMonDuplicateCapturedUnicodeStringFromMode(&v9, (char *)&v12 + 8, v6);
    if ( v5 >= 0 )
      v5 = SetLogSessionInfo(&SourceString, &v9);
  }
  LOBYTE(v4) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v9, v4);
  LOBYTE(v7) = a1;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&SourceString, v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001e174  mov     [rsp+arg_8], rbx
0x14001e179  mov     [rsp+arg_0], cl
0x14001e17d  push    rdi
0x14001e17e  sub     rsp, 70h
0x14001e182  mov     bl, cl
0x14001e184  xorps   xmm0, xmm0
0x14001e187  xor     eax, eax
0x14001e189  movups  [rsp+78h+var_30], xmm0
0x14001e18e  movups  [rsp+78h+var_20], xmm0
0x14001e193  mov     [rsp+78h+var_10], rax
0x14001e198  movups  xmmword ptr [rsp+78h+SourceString.Length], xmm0
0x14001e19d  xorps   xmm1, xmm1
0x14001e1a0  movups  xmmword ptr [rsp+78h+var_50.Length], xmm1
0x14001e1a5  lea     r8d, [rax+28h]; Size
0x14001e1a9  lea     rcx, [rsp+78h+var_30]; void *
0x14001e1ae  test    bl, bl
0x14001e1b0  jz      short loc_14001E1B9
0x14001e1b2  call    RtlCopyFromUser
0x14001e1b7  jmp     short loc_14001E1BF
0x14001e1b9  call    RtlCopyVolatileMemory
0x14001e1be  nop
0x14001e1bf  mov     r8b, bl
0x14001e1c2  lea     rdx, [rsp+78h+var_30+8]
0x14001e1c7  lea     rcx, [rsp+78h+SourceString]
0x14001e1cc  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e1d1  mov     edi, eax
0x14001e1d3  test    eax, eax
0x14001e1d5  js      short loc_14001E20B
0x14001e1d7  mov     r8b, bl
0x14001e1da  lea     rdx, [rsp+78h+var_20+8]
0x14001e1df  lea     rcx, [rsp+78h+var_50]
0x14001e1e4  call    WinSetupMonDuplicateCapturedUnicodeStringFromMode
0x14001e1e9  mov     edi, eax
0x14001e1eb  test    eax, eax
0x14001e1ed  js      short loc_14001E20B
0x14001e1ef  lea     rdx, [rsp+78h+var_50]; PCUNICODE_STRING
0x14001e1f4  lea     rcx, [rsp+78h+SourceString]; SourceString
0x14001e1f9  call    ?SetLogSessionInfo@@YAJPEBU_UNICODE_STRING@@0@Z; SetLogSessionInfo(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x14001e1fe  mov     edi, eax
0x14001e200  jmp     short loc_14001E20B
0x14001e202  mov     edi, eax
0x14001e204  mov     bl, [rsp+78h+arg_0]
0x14001e20b  mov     dl, bl
0x14001e20d  lea     rcx, [rsp+78h+var_50]
0x14001e212  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e217  mov     dl, bl
0x14001e219  lea     rcx, [rsp+78h+SourceString]
0x14001e21e  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e223  mov     eax, edi
0x14001e225  mov     rbx, [rsp+78h+arg_8]
0x14001e22d  add     rsp, 70h
0x14001e231  pop     rdi
0x14001e232  retn
0x140021bed  push    rbp
0x140021bef  sub     rsp, 20h
0x140021bf3  mov     rbp, rdx
0x140021bf6  xor     eax, eax
0x140021bf8  cmp     [rbp+80h], al
0x140021bfe  setnz   al
0x140021c01  mov     [rbp+20h], eax
0x140021c04  mov     eax, [rbp+20h]
0x140021c07  add     rsp, 20h
0x140021c0b  pop     rbp
0x140021c0c  retn
```
