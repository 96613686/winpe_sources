# TraceActCtxGenManifestParseError(long,ulong,ushort const *,ushort const *,ushort const *,ushort)

- ea: `0x18005d428`
- end: `0x18005d552`
- name: `?TraceActCtxGenManifestParseError@@YAKJKPEBG00G@Z`
- size: `298`
- prototype: `unsigned int __fastcall(int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e290`
- `0x18002e6d0`
- `0x180031260`
- `0x1800419e4`
- `0x1800479c0`
- `0x180048e00`
- `0x1800515ec`
- `0x180065240`
- `0x1800652d0`
- `0x180065370`
- `0x1800659f0`

## callees

- `0x1800176b0`
- `0x18005d428`
- `0x18006a110`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18005d52c`
- `ntdll!EtwEventWrite` at `0x18005d52c`

## pseudocode

```c
__int64 __fastcall TraceActCtxGenManifestParseError(
        int a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 a6)
{
  const wchar_t *v6; // r8
  const wchar_t *v7; // r9
  const wchar_t *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  _WORD v13[2]; // [rsp+20h] [rbp-29h] BYREF
  int v14; // [rsp+24h] [rbp-25h]
  __int64 v15; // [rsp+28h] [rbp-21h]
  _QWORD v16[5]; // [rsp+30h] [rbp-19h] BYREF
  int v17; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+5Ch] [rbp+13h]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  const wchar_t *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  int v25; // [rsp+A0h] [rbp+57h] BYREF
  int v26; // [rsp+A8h] [rbp+5Fh] BYREF

  v26 = a2;
  v25 = a1;
  if ( !(unsigned int)IsEventEnabled(2u, a2) )
    return 0;
  v8 = a5;
  v13[0] = a6;
  if ( !v6 )
    v6 = L"<unknown>";
  v13[1] = 0;
  v14 = 6815746;
  v15 = 256;
  if ( !v7 )
    v7 = L"<unknown>";
  v16[1] = 4;
  v16[3] = 4;
  v16[4] = v6;
  if ( !a5 )
    v8 = L"<unknown>";
  v16[0] = &v25;
  v9 = -1;
  v16[2] = &v26;
  v10 = -1;
  do
    ++v10;
  while ( v6[v10] );
  v18 = 0;
  v17 = 2 * v10 + 2;
  v11 = -1;
  v19 = v7;
  do
    ++v11;
  while ( v7[v11] );
  v21 = 0;
  v20 = 2 * v11 + 2;
  v22 = v8;
  do
    ++v9;
  while ( v8[v9] );
  v24 = 0;
  v23 = 2 * v9 + 2;
  return EtwEventWrite(g_hTraceHandle, v13, 5, v16);
}

```

## disassembly

```asm
0x18005d428  mov     [rsp-8+arg_8], edx
0x18005d42c  mov     [rsp-8+arg_0], ecx
0x18005d430  push    rbp
0x18005d431  lea     rbp, [rsp-47h]
0x18005d436  sub     rsp, 90h
0x18005d43d  mov     rax, cs:__security_cookie
0x18005d444  xor     rax, rsp
0x18005d447  mov     [rbp+47h+var_10], rax
0x18005d44b  mov     cl, 2; unsigned __int8
0x18005d44d  call    ?IsEventEnabled@@YAHE_K@Z; IsEventEnabled(uchar,unsigned __int64)
0x18005d452  xor     r10d, r10d
0x18005d455  test    eax, eax
0x18005d457  jz      loc_18005D53A
0x18005d45d  movzx   eax, [rbp+47h+arg_28]
0x18005d461  test    r8, r8
0x18005d464  mov     rdx, [rbp+47h+arg_20]
0x18005d468  mov     [rbp+47h+var_70], ax
0x18005d46c  lea     rax, aUnknown; "<unknown>"
0x18005d473  cmovz   r8, rax
0x18005d477  mov     [rbp+47h+var_6E], r10w
0x18005d47c  test    r9, r9
0x18005d47f  mov     [rbp+47h+var_6C], 680002h
0x18005d486  mov     [rbp+47h+var_68], 100h
0x18005d48e  cmovz   r9, rax
0x18005d492  mov     [rbp+47h+var_58], 4
0x18005d49a  test    rdx, rdx
0x18005d49d  mov     [rbp+47h+var_48], 4
0x18005d4a5  mov     [rbp+47h+var_40], r8
0x18005d4a9  cmovz   rdx, rax
0x18005d4ad  lea     rax, [rbp+47h+arg_0]
0x18005d4b1  mov     [rbp+47h+var_60], rax
0x18005d4b5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005d4b9  lea     rax, [rbp+47h+arg_8]
0x18005d4bd  mov     [rbp+47h+var_50], rax
0x18005d4c1  mov     rax, rcx
0x18005d4c4  inc     rax
0x18005d4c7  cmp     [r8+rax*2], r10w
0x18005d4cc  jnz     short loc_18005D4C4
0x18005d4ce  lea     eax, ds:2[rax*2]
0x18005d4d5  mov     [rbp+47h+var_34], r10d
0x18005d4d9  mov     [rbp+47h+var_38], eax
0x18005d4dc  mov     rax, rcx
0x18005d4df  mov     [rbp+47h+var_30], r9
0x18005d4e3  inc     rax
0x18005d4e6  cmp     [r9+rax*2], r10w
0x18005d4eb  jnz     short loc_18005D4E3
0x18005d4ed  lea     eax, ds:2[rax*2]
0x18005d4f4  mov     [rbp+47h+var_24], r10d
0x18005d4f8  mov     [rbp+47h+var_28], eax
0x18005d4fb  mov     [rbp+47h+var_20], rdx
0x18005d4ff  inc     rcx
0x18005d502  cmp     [rdx+rcx*2], r10w
0x18005d507  jnz     short loc_18005D4FF
0x18005d509  lea     eax, ds:2[rcx*2]
0x18005d510  mov     [rbp+47h+var_14], r10d
0x18005d514  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18005d51b  lea     r9, [rbp+47h+var_60]
0x18005d51f  mov     r8d, 5
0x18005d525  mov     [rbp+47h+var_18], eax
0x18005d528  lea     rdx, [rbp+47h+var_70]
0x18005d52c  call    cs:__imp_EtwEventWrite
0x18005d533  nop     dword ptr [rax+rax+00h]
0x18005d538  jmp     short loc_18005D53C
0x18005d53a  xor     eax, eax
0x18005d53c  mov     rcx, [rbp+47h+var_10]
0x18005d540  xor     rcx, rsp; StackCookie
0x18005d543  call    __security_check_cookie
0x18005d548  add     rsp, 90h
0x18005d54f  pop     rbp
0x18005d550  retn
```
