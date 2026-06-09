# CACConnectionPage::GetUpdatedIHVParams(void)

- ea: `0x18000dc38`
- end: `0x18000ddf7`
- name: `?GetUpdatedIHVParams@CACConnectionPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ`
- size: `447`
- prototype: `struct _DOT11EXT_IHV_PARAMS *__fastcall(CACConnectionPage *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000df1c`
- `0x18000e148`

## callees

- `0x18000dc38`
- `0x180010cf0`

## pseudocode

```c
struct _DOT11EXT_IHV_PARAMS *__fastcall CACConnectionPage::GetUpdatedIHVParams(CACConnectionPage *this)
{
  unsigned int v2; // edx
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  unsigned int **v6; // r8
  unsigned int v7; // eax
  BOOL v8; // eax
  __int64 v9; // rdx
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  int v14; // ecx
  __int128 v15; // xmm0
  int v16; // eax

  v2 = 0x80000000;
  v3 = *(_QWORD *)(*((_QWORD *)this + 18) + 552LL);
  v4 = *(_QWORD *)(v3 + 32);
  v5 = *(_QWORD *)(v4 + 424);
  v6 = (unsigned int **)(v5 + 24);
  if ( *(_DWORD *)(v4 + 432) )
    v7 = 0x80000000;
  else
    v7 = **v6;
  *((_DWORD *)this + 182) = v7;
  if ( !*(_DWORD *)(*(_QWORD *)(v3 + 32) + 432LL) )
    v2 = (*v6)[1];
  *((_DWORD *)this + 183) = v2;
  v8 = v5 && *(_DWORD *)(v5 + 32);
  *((_DWORD *)this + 184) = v8;
  *((_DWORD *)this + 189) = 0;
  *((_QWORD *)this + 95) = 0;
  *(_OWORD *)((char *)this + 740) = 0;
  if ( *((_DWORD *)this + 184) && *(_DWORD *)(v5 + 40) )
  {
    v9 = *(_QWORD *)(v5 + 48) + *(unsigned int *)(*(_QWORD *)(v5 + 48) + 64LL);
    if ( (*(_BYTE *)(v9 + 20) & 1) != 0 )
    {
      *((_DWORD *)this + 189) = *(_DWORD *)(v9 + 24);
      *((_QWORD *)this + 95) = v9 + *(unsigned int *)(v9 + 28);
    }
    *(_OWORD *)((char *)this + 740) = *(_OWORD *)(v9 + 4);
  }
  *((_QWORD *)this + 23) = (char *)this + 728;
  CreateIhvSsidList(*(struct DOT11_SSID_LIST **)(v3 + 8), (struct _DOT11EXT_IHV_SSID_LIST **)this + 21);
  v10 = (_OWORD *)((char *)this + 192);
  *((_DWORD *)this + 44) = *(_DWORD *)(v3 + 16);
  v11 = 4;
  v12 = (_OWORD *)(*((_QWORD *)this + 18) + 24LL);
  do
  {
    *v10 = *v12;
    v10[1] = v12[1];
    v10[2] = v12[2];
    v10[3] = v12[3];
    v10[4] = v12[4];
    v10[5] = v12[5];
    v10[6] = v12[6];
    v13 = v12[7];
    v12 += 8;
    v10[7] = v13;
    v10 += 8;
    --v11;
  }
  while ( v11 );
  v14 = *((_DWORD *)this + 192);
  v15 = *(_OWORD *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 176) = 0;
  *(_OWORD *)((char *)this + 708) = v15;
  *((_DWORD *)this + 44) = *(_DWORD *)(v3 + 16);
  v16 = 0;
  if ( (v14 & 1) != 0 )
  {
    *((_DWORD *)this + 176) = 1;
    v16 = 1;
  }
  if ( (v14 & 2) != 0 )
    *((_DWORD *)this + 176) = v16 | 2;
  return (struct _DOT11EXT_IHV_PARAMS *)((char *)this + 168);
}

```

## disassembly

```asm
0x18000dc38  mov     [rsp+arg_0], rbx
0x18000dc3d  mov     [rsp+arg_8], rsi
0x18000dc42  push    rdi
0x18000dc43  sub     rsp, 20h
0x18000dc47  mov     rax, [rcx+90h]
0x18000dc4e  mov     rbx, rcx
0x18000dc51  mov     edx, 80000000h
0x18000dc56  mov     rdi, [rax+228h]
0x18000dc5d  mov     rax, [rdi+20h]
0x18000dc61  cmp     dword ptr [rax+1B0h], 0
0x18000dc68  mov     rcx, [rax+1A8h]
0x18000dc6f  lea     r8, [rcx+18h]
0x18000dc73  jz      short loc_18000DC79
0x18000dc75  mov     eax, edx
0x18000dc77  jmp     short loc_18000DC7E
0x18000dc79  mov     rax, [r8]
0x18000dc7c  mov     eax, [rax]
0x18000dc7e  lea     r9, [rbx+2D8h]
0x18000dc85  mov     [r9], eax
0x18000dc88  mov     rax, [rdi+20h]
0x18000dc8c  cmp     dword ptr [rax+1B0h], 0
0x18000dc93  jnz     short loc_18000DC9B
0x18000dc95  mov     rax, [r8]
0x18000dc98  mov     edx, [rax+4]
0x18000dc9b  mov     [rbx+2DCh], edx
0x18000dca1  test    rcx, rcx
0x18000dca4  jz      short loc_18000DCB3
0x18000dca6  cmp     dword ptr [rcx+20h], 0
0x18000dcaa  jz      short loc_18000DCB3
0x18000dcac  mov     eax, 1
0x18000dcb1  jmp     short loc_18000DCB5
0x18000dcb3  xor     eax, eax
0x18000dcb5  mov     [rbx+2E0h], eax
0x18000dcbb  xorps   xmm0, xmm0
0x18000dcbe  mov     dword ptr [rbx+2F4h], 0
0x18000dcc8  mov     qword ptr [rbx+2F8h], 0
0x18000dcd3  movups  xmmword ptr [r9+0Ch], xmm0
0x18000dcd8  cmp     dword ptr [rbx+2E0h], 0
0x18000dcdf  jz      short loc_18000DD19
0x18000dce1  cmp     dword ptr [rcx+28h], 0
0x18000dce5  jz      short loc_18000DD19
0x18000dce7  mov     rcx, [rcx+30h]
0x18000dceb  mov     edx, [rcx+40h]
0x18000dcee  add     rdx, rcx
0x18000dcf1  test    byte ptr [rdx+14h], 1
0x18000dcf5  jz      short loc_18000DD0D
0x18000dcf7  mov     eax, [rdx+18h]
0x18000dcfa  mov     [rbx+2F4h], eax
0x18000dd00  mov     eax, [rdx+1Ch]
0x18000dd03  add     rax, rdx
0x18000dd06  mov     [rbx+2F8h], rax
0x18000dd0d  movups  xmm0, xmmword ptr [rdx+4]
0x18000dd11  movdqu  xmmword ptr [rbx+2E4h], xmm0
0x18000dd19  lea     rsi, [rbx+0A8h]
0x18000dd20  mov     [rsi+10h], r9
0x18000dd24  mov     rdx, rsi; struct _DOT11EXT_IHV_SSID_LIST **
0x18000dd27  mov     rcx, [rdi+8]; struct DOT11_SSID_LIST *
0x18000dd2b  call    ?CreateIhvSsidList@@YAKPEAUDOT11_SSID_LIST@@PEAPEAU_DOT11EXT_IHV_SSID_LIST@@@Z; CreateIhvSsidList(DOT11_SSID_LIST *,_DOT11EXT_IHV_SSID_LIST * *)
0x18000dd30  mov     eax, [rdi+10h]
0x18000dd33  lea     rcx, [rbx+0C0h]
0x18000dd3a  mov     [rbx+0B0h], eax
0x18000dd40  mov     edx, 4
0x18000dd45  mov     rax, [rbx+90h]
0x18000dd4c  add     rax, 18h
0x18000dd50  lea     r8d, [rdx+7Ch]
0x18000dd54  movups  xmm0, xmmword ptr [rax]
0x18000dd57  movups  xmmword ptr [rcx], xmm0
0x18000dd5a  movups  xmm1, xmmword ptr [rax+10h]
0x18000dd5e  movups  xmmword ptr [rcx+10h], xmm1
0x18000dd62  movups  xmm0, xmmword ptr [rax+20h]
0x18000dd66  movups  xmmword ptr [rcx+20h], xmm0
0x18000dd6a  movups  xmm1, xmmword ptr [rax+30h]
0x18000dd6e  movups  xmmword ptr [rcx+30h], xmm1
0x18000dd72  movups  xmm0, xmmword ptr [rax+40h]
0x18000dd76  movups  xmmword ptr [rcx+40h], xmm0
0x18000dd7a  movups  xmm1, xmmword ptr [rax+50h]
0x18000dd7e  movups  xmmword ptr [rcx+50h], xmm1
0x18000dd82  movups  xmm0, xmmword ptr [rax+60h]
0x18000dd86  movups  xmmword ptr [rcx+60h], xmm0
0x18000dd8a  movups  xmm1, xmmword ptr [rax+70h]
0x18000dd8e  add     rax, r8
0x18000dd91  movups  xmmword ptr [rcx+70h], xmm1
0x18000dd95  add     rcx, r8
0x18000dd98  sub     rdx, 1
0x18000dd9c  jnz     short loc_18000DD54
0x18000dd9e  mov     rax, [rbx+10h]
0x18000dda2  mov     ecx, [rbx+300h]
0x18000dda8  movups  xmm0, xmmword ptr [rax]
0x18000ddab  mov     [rbx+2C0h], edx
0x18000ddb1  movdqu  xmmword ptr [rbx+2C4h], xmm0
0x18000ddb9  mov     eax, [rdi+10h]
0x18000ddbc  mov     [rbx+0B0h], eax
0x18000ddc2  xor     eax, eax
0x18000ddc4  test    cl, 1
0x18000ddc7  jz      short loc_18000DDD6
0x18000ddc9  mov     dword ptr [rbx+2C0h], 1
0x18000ddd3  lea     eax, [rdx+1]
0x18000ddd6  test    cl, 2
0x18000ddd9  jz      short loc_18000DDE4
0x18000dddb  or      eax, 2
0x18000ddde  mov     [rbx+2C0h], eax
0x18000dde4  mov     rbx, [rsp+28h+arg_0]
0x18000dde9  mov     rax, rsi
0x18000ddec  mov     rsi, [rsp+28h+arg_8]
0x18000ddf1  add     rsp, 20h
0x18000ddf5  pop     rdi
0x18000ddf6  retn
```
