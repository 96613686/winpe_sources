# CACSecurityPage::NeedsKey(_AUI_AUTH_INFO *,_AUI_CIPHER_INFO *)

- ea: `0x180009278`
- end: `0x1800092c9`
- name: `?NeedsKey@CACSecurityPage@@AEAAHPEAU_AUI_AUTH_INFO@@PEAU_AUI_CIPHER_INFO@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, struct _AUI_AUTH_INFO *, struct _AUI_CIPHER_INFO *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009380`
- `0x18000c824`

## callees

- `0x180009278`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::NeedsKey(
        CACSecurityPage *this,
        struct _AUI_AUTH_INFO *a2,
        struct _AUI_CIPHER_INFO *a3)
{
  __int64 result; // rax
  BOOL v4; // ecx
  unsigned int v5; // ecx
  int v6; // edx

  result = 1;
  if ( a2 )
  {
    v4 = 0;
    if ( *((_DWORD *)a2 + 3) )
      v4 = *(_DWORD *)a2 == 0;
    if ( a3 && !*(_DWORD *)a3 || v4 )
      return 0;
  }
  v5 = *((_DWORD *)a2 + 1);
  if ( v5 != 1 || *((_DWORD *)a3 + 1) != 257 )
  {
    if ( v5 > 9 )
      return 0;
    v6 = 660;
    if ( !_bittest(&v6, v5) )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009278  xor     r9d, r9d
0x18000927b  mov     eax, 1
0x180009280  test    rdx, rdx
0x180009283  jz      short loc_1800092A5
0x180009285  mov     ecx, r9d
0x180009288  cmp     [rdx+0Ch], r9d
0x18000928c  jz      short loc_180009294
0x18000928e  cmp     [rdx], r9d
0x180009291  cmovz   ecx, eax
0x180009294  test    r8, r8
0x180009297  jz      short loc_18000929E
0x180009299  cmp     [r8], r9d
0x18000929c  jz      short loc_1800092A2
0x18000929e  test    ecx, ecx
0x1800092a0  jz      short loc_1800092A5
0x1800092a2  xor     eax, eax
0x1800092a4  retn
0x1800092a5  mov     ecx, [rdx+4]
0x1800092a8  cmp     ecx, eax
0x1800092aa  jnz     short loc_1800092B6
0x1800092ac  cmp     dword ptr [r8+4], 101h
0x1800092b4  jz      short locret_1800092C8
0x1800092b6  cmp     ecx, 9
0x1800092b9  ja      short loc_1800092C5
0x1800092bb  mov     edx, 294h
0x1800092c0  bt      edx, ecx
0x1800092c3  jb      short locret_1800092C8
0x1800092c5  mov     eax, r9d
0x1800092c8  retn
```
