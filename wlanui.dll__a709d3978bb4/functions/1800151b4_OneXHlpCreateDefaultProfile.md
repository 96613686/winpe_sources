# OneXHlpCreateDefaultProfile

- ea: `0x1800151b4`
- end: `0x18001530e`
- name: `OneXHlpCreateDefaultProfile`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001561c`

## callees

- `0x1800151b4`
- `0x180015314`
- `0x18001bf0a`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x1800151f1`
- `MobileNetworking!AllocateMemory` at `0x1800151f1`

## string_xrefs

- `0x1800151e1`: `OneXHlpCreateDefaultProfile`

## pseudocode

```c
__int64 __fastcall OneXHlpCreateDefaultProfile(void **a1, _DWORD *a2)
{
  unsigned int valid; // ecx
  __int64 v5; // rbx
  _DWORD *v6; // rbx
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF
  void *v9; // [rsp+60h] [rbp+28h] BYREF

  *a1 = 0;
  *a2 = 0;
  v9 = 0;
  valid = AllocateMemory(104, &v9, "OneXHlpCreateDefaultProfile", 556);
  if ( !valid )
  {
    memset_0(v9, 0, 0x68u);
    *(_DWORD *)v9 = 1;
    *((_DWORD *)v9 + 1) = 104;
    if ( v9 == (void *)-60LL )
      return 87;
    *((_DWORD *)v9 + 15) = 32;
    if ( v9 == (void *)-64LL )
      return 87;
    *((_DWORD *)v9 + 16) = 72;
    if ( !v9 )
      return 87;
    v5 = -1;
    if ( (char *)v9 + 72 >= v9 )
      v5 = (__int64)v9 + 72;
    valid = (char *)v9 + 72 < v9 ? 0x216 : 0;
    if ( (char *)v9 + 72 >= v9 )
    {
      *(_BYTE *)(v5 + 4) = 25;
      *(_QWORD *)(v5 + 12) = 0;
      *(_DWORD *)(v5 + 8) = 0;
      *(_DWORD *)v5 = 0;
      *((_DWORD *)v9 + 6) = -1;
      *((_DWORD *)v9 + 7) = -1;
      *((_DWORD *)v9 + 8) = -1;
      *((_DWORD *)v9 + 9) = -1;
      *((_DWORD *)v9 + 10) = -1;
      *((_DWORD *)v9 + 4) = 3;
      v8 = *(_OWORD *)(v5 + 4);
      valid = OneXIsValidEapTypeAndFlags(&v8);
      if ( !valid )
      {
        *(_DWORD *)(v5 + 20) &= ~1u;
        *(_DWORD *)(v5 + 24) = 0;
        v6 = (_DWORD *)(v5 + 28);
        if ( v6 )
        {
          *v6 = 32;
          *a1 = v9;
          *a2 = 104;
          return valid;
        }
        return 87;
      }
    }
  }
  return valid;
}

```

## disassembly

```asm
0x1800151b4  push    rbp
0x1800151b6  push    rbx
0x1800151b7  push    rsi
0x1800151b8  push    rdi
0x1800151b9  mov     rbp, rsp
0x1800151bc  sub     rsp, 38h
0x1800151c0  mov     qword ptr [rcx], 0
0x1800151c7  mov     rdi, rdx
0x1800151ca  mov     dword ptr [rdx], 0
0x1800151d0  mov     rsi, rcx
0x1800151d3  mov     [rbp+arg_0], 0
0x1800151db  mov     r9d, 22Ch
0x1800151e1  lea     r8, aOnexhlpcreated; "OneXHlpCreateDefaultProfile"
0x1800151e8  lea     rdx, [rbp+arg_0]
0x1800151ec  mov     ecx, 68h ; 'h'
0x1800151f1  call    cs:__imp_AllocateMemory
0x1800151f7  mov     ecx, eax
0x1800151f9  test    eax, eax
0x1800151fb  jnz     loc_180015303
0x180015201  mov     rcx, [rbp+arg_0]; void *
0x180015205  lea     r8d, [rax+68h]; Size
0x180015209  xor     edx, edx; Val
0x18001520b  call    memset_0
0x180015210  mov     rax, [rbp+arg_0]
0x180015214  mov     dword ptr [rax], 1
0x18001521a  mov     rax, [rbp+arg_0]
0x18001521e  mov     dword ptr [rax+4], 68h ; 'h'
0x180015225  mov     rax, [rbp+arg_0]
0x180015229  add     rax, 3Ch ; '<'
0x18001522d  jz      loc_1800152FE
0x180015233  mov     dword ptr [rax], 20h ; ' '
0x180015239  mov     rax, [rbp+arg_0]
0x18001523d  add     rax, 40h ; '@'
0x180015241  jz      loc_1800152FE
0x180015247  mov     dword ptr [rax], 48h ; 'H'
0x18001524d  mov     rdx, [rbp+arg_0]
0x180015251  test    rdx, rdx
0x180015254  jz      loc_1800152FE
0x18001525a  lea     rax, [rdx+48h]
0x18001525e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015262  cmp     rax, rdx
0x180015265  cmovnb  rbx, rax
0x180015269  sbb     ecx, ecx
0x18001526b  and     ecx, 216h
0x180015271  cmp     rax, rdx
0x180015274  jb      loc_180015303
0x18001527a  mov     byte ptr [rbx+4], 19h
0x18001527e  or      ecx, 0FFFFFFFFh
0x180015281  mov     qword ptr [rbx+0Ch], 0
0x180015289  mov     dword ptr [rbx+8], 0
0x180015290  mov     dword ptr [rbx], 0
0x180015296  mov     rax, [rbp+arg_0]
0x18001529a  mov     [rax+18h], ecx
0x18001529d  mov     rax, [rbp+arg_0]
0x1800152a1  mov     [rax+1Ch], ecx
0x1800152a4  mov     rax, [rbp+arg_0]
0x1800152a8  mov     [rax+20h], ecx
0x1800152ab  mov     rax, [rbp+arg_0]
0x1800152af  mov     [rax+24h], ecx
0x1800152b2  mov     rax, [rbp+arg_0]
0x1800152b6  mov     [rax+28h], ecx
0x1800152b9  lea     rcx, [rbp+var_18]
0x1800152bd  mov     rax, [rbp+arg_0]
0x1800152c1  mov     dword ptr [rax+10h], 3
0x1800152c8  movups  xmm0, xmmword ptr [rbx+4]
0x1800152cc  movdqu  [rbp+var_18], xmm0
0x1800152d1  call    OneXIsValidEapTypeAndFlags
0x1800152d6  mov     ecx, eax
0x1800152d8  test    eax, eax
0x1800152da  jnz     short loc_180015303
0x1800152dc  and     dword ptr [rbx+14h], 0FFFFFFFEh
0x1800152e0  mov     [rbx+18h], eax
0x1800152e3  add     rbx, 1Ch
0x1800152e7  jz      short loc_1800152FE
0x1800152e9  mov     dword ptr [rbx], 20h ; ' '
0x1800152ef  mov     rax, [rbp+arg_0]
0x1800152f3  mov     [rsi], rax
0x1800152f6  mov     dword ptr [rdi], 68h ; 'h'
0x1800152fc  jmp     short loc_180015303
0x1800152fe  mov     ecx, 57h ; 'W'
0x180015303  mov     eax, ecx
0x180015305  add     rsp, 38h
0x180015309  pop     rdi
0x18001530a  pop     rsi
0x18001530b  pop     rbx
0x18001530c  pop     rbp
0x18001530d  retn
```
