# SSOControls::CommitAdditionalSettings(void)

- ea: `0x180012d1c`
- end: `0x180012ea5`
- name: `?CommitAdditionalSettings@SSOControls@@QEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(SSOControls *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009380`

## callees

- `0x180012d1c`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x180012d7f`
- `ntdll!WinSqmIncrementDWORD` at `0x180012e8d`
- `ntdll!WinSqmIncrementDWORD` at `0x180012d7f`
- `ntdll!WinSqmIncrementDWORD` at `0x180012e8d`

## pseudocode

```c
__int64 __fastcall SSOControls::CommitAdditionalSettings(SSOControls *this)
{
  __int64 v1; // r8
  int v3; // eax
  _DWORD *v4; // r10
  int v5; // edi
  int *v6; // rbx
  unsigned int v7; // r11d
  int v8; // edx
  unsigned int v9; // ecx
  int v10; // eax
  int v11; // r11d
  BOOL v12; // edx
  int v13; // r11d
  int v14; // ecx
  int v15; // ecx

  v1 = *((_QWORD *)this + 2);
  v3 = *(_DWORD *)(v1 + 60);
  v4 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 552LL) + 32LL) + 424LL) + 48LL);
  v5 = v4[3];
  v6 = v4 + 2;
  v7 = v5 & 0xFFFFFFF3;
  v4[3] = v5 & 0xFFFFFFF3;
  if ( v3 )
  {
    v8 = *v6;
    v9 = *v6 | 1;
    *v6 = v9;
    if ( *((_DWORD *)this + 6) )
    {
      v10 = 8;
      if ( *((_DWORD *)this + 8) != 1 )
        v10 = 4;
      v4[3] = v7 | v10;
    }
    v11 = *((_DWORD *)this + 6);
    v12 = ((v9 >> 8) & 1) != v11 || ((v9 >> 9) & 1) != v11 || ((v9 >> 11) & 1) != v11 || (v8 & 1) == 0;
    v13 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)((_WORD)v11 << 8)) & 0x100;
    *v6 = v13;
    v14 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)((unsigned __int16)*((_DWORD *)this + 6) << 9)) & 0x200;
    *v6 = v14;
    *v6 = v14 ^ ((unsigned __int16)v14 ^ (unsigned __int16)((unsigned __int16)*((_DWORD *)this + 6) << 11)) & 0x800;
    if ( *((_DWORD *)this + 6) )
    {
      v15 = *((_DWORD *)this + 9);
      if ( v4[11] != v15 || v4[13] != *((_DWORD *)this + 10) || v4[14] != *((_DWORD *)this + 11) )
        v12 = 1;
      v4[11] = v15;
      v4[13] = *((_DWORD *)this + 10);
      v4[14] = *((_DWORD *)this + 11);
    }
    *(_DWORD *)(*((_QWORD *)this + 2) + 64LL) = *((_DWORD *)this + 6);
    if ( v4[3] != v5 || v12 )
      WinSqmIncrementDWORD(0, 6150, 1);
  }
  else
  {
    if ( v7 != v5 || (*v6 & 0xB00) != 0 )
      WinSqmIncrementDWORD(0, 6150, 1);
    *v6 &= ~0x100u;
    *v6 &= 0xFFFFF5FF;
  }
  return 0;
}

```

## disassembly

```asm
0x180012d1c  mov     [rsp+arg_0], rbx
0x180012d21  mov     [rsp+arg_8], rsi
0x180012d26  push    rdi
0x180012d27  sub     rsp, 20h
0x180012d2b  mov     r8, [rcx+10h]
0x180012d2f  mov     r9, rcx
0x180012d32  mov     rax, [r8+48h]
0x180012d36  mov     rdx, [rax+228h]
0x180012d3d  mov     rax, [rdx+20h]
0x180012d41  mov     rdx, [rax+1A8h]
0x180012d48  mov     eax, [r8+3Ch]
0x180012d4c  mov     r10, [rdx+30h]
0x180012d50  mov     edi, [r10+0Ch]
0x180012d54  lea     rbx, [r10+8]
0x180012d58  mov     r11d, edi
0x180012d5b  and     r11d, 0FFFFFFF3h
0x180012d5f  mov     [r10+0Ch], r11d
0x180012d63  test    eax, eax
0x180012d65  jnz     short loc_180012D9A
0x180012d67  cmp     r11d, edi
0x180012d6a  jnz     short loc_180012D74
0x180012d6c  test    dword ptr [rbx], 0B00h
0x180012d72  jz      short loc_180012D85
0x180012d74  xor     ecx, ecx
0x180012d76  mov     edx, 1806h
0x180012d7b  lea     r8d, [rcx+1]
0x180012d7f  call    cs:__imp_WinSqmIncrementDWORD
0x180012d85  btr     dword ptr [rbx], 8
0x180012d89  mov     eax, [rbx]
0x180012d8b  btr     eax, 9
0x180012d8f  btr     eax, 0Bh
0x180012d93  mov     [rbx], eax
0x180012d95  jmp     loc_180012E93
0x180012d9a  mov     edx, [rbx]
0x180012d9c  mov     r8d, 1
0x180012da2  mov     ecx, edx
0x180012da4  or      ecx, r8d
0x180012da7  mov     [rbx], ecx
0x180012da9  cmp     dword ptr [r9+18h], 0
0x180012dae  jz      short loc_180012DC5
0x180012db0  cmp     [r9+20h], r8d
0x180012db4  lea     eax, [r8+7]
0x180012db8  lea     esi, [rax-4]
0x180012dbb  cmovnz  eax, esi
0x180012dbe  or      eax, r11d
0x180012dc1  mov     [r10+0Ch], eax
0x180012dc5  mov     r11d, [r9+18h]
0x180012dc9  mov     eax, ecx
0x180012dcb  shr     eax, 8
0x180012dce  and     eax, r8d
0x180012dd1  cmp     eax, r11d
0x180012dd4  jnz     short loc_180012DF7
0x180012dd6  mov     eax, ecx
0x180012dd8  shr     eax, 9
0x180012ddb  and     eax, r8d
0x180012dde  cmp     eax, r11d
0x180012de1  jnz     short loc_180012DF7
0x180012de3  mov     eax, ecx
0x180012de5  shr     eax, 0Bh
0x180012de8  and     eax, r8d
0x180012deb  cmp     eax, r11d
0x180012dee  jnz     short loc_180012DF7
0x180012df0  not     edx
0x180012df2  and     edx, r8d
0x180012df5  jmp     short loc_180012DFA
0x180012df7  mov     edx, r8d
0x180012dfa  shl     r11d, 8
0x180012dfe  xor     r11d, ecx
0x180012e01  and     r11d, 100h
0x180012e08  xor     r11d, ecx
0x180012e0b  mov     [rbx], r11d
0x180012e0e  mov     ecx, [r9+18h]
0x180012e12  shl     ecx, 9
0x180012e15  xor     ecx, r11d
0x180012e18  and     ecx, 200h
0x180012e1e  xor     ecx, r11d
0x180012e21  mov     [rbx], ecx
0x180012e23  mov     eax, [r9+18h]
0x180012e27  shl     eax, 0Bh
0x180012e2a  xor     eax, ecx
0x180012e2c  and     eax, 800h
0x180012e31  xor     eax, ecx
0x180012e33  mov     [rbx], eax
0x180012e35  cmp     dword ptr [r9+18h], 0
0x180012e3a  jz      short loc_180012E71
0x180012e3c  mov     ecx, [r9+24h]
0x180012e40  cmp     [r10+2Ch], ecx
0x180012e44  jnz     short loc_180012E5A
0x180012e46  mov     eax, [r9+28h]
0x180012e4a  cmp     [r10+34h], eax
0x180012e4e  jnz     short loc_180012E5A
0x180012e50  mov     eax, [r9+2Ch]
0x180012e54  cmp     [r10+38h], eax
0x180012e58  jz      short loc_180012E5D
0x180012e5a  mov     edx, r8d
0x180012e5d  mov     [r10+2Ch], ecx
0x180012e61  mov     eax, [r9+28h]
0x180012e65  mov     [r10+34h], eax
0x180012e69  mov     eax, [r9+2Ch]
0x180012e6d  mov     [r10+38h], eax
0x180012e71  mov     rcx, [r9+10h]
0x180012e75  mov     eax, [r9+18h]
0x180012e79  mov     [rcx+40h], eax
0x180012e7c  cmp     [r10+0Ch], edi
0x180012e80  jnz     short loc_180012E86
0x180012e82  test    edx, edx
0x180012e84  jz      short loc_180012E93
0x180012e86  mov     edx, 1806h
0x180012e8b  xor     ecx, ecx
0x180012e8d  call    cs:__imp_WinSqmIncrementDWORD
0x180012e93  mov     rbx, [rsp+28h+arg_0]
0x180012e98  xor     eax, eax
0x180012e9a  mov     rsi, [rsp+28h+arg_8]
0x180012e9f  add     rsp, 20h
0x180012ea3  pop     rdi
0x180012ea4  retn
```
