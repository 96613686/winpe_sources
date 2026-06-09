# CACSecurityPage::GetUpdatedIHVParams(void)

- ea: `0x180008498`
- end: `0x180008667`
- name: `?GetUpdatedIHVParams@CACSecurityPage@@AEAAPEAU_DOT11EXT_IHV_PARAMS@@XZ`
- size: `463`
- prototype: `struct _DOT11EXT_IHV_PARAMS *__fastcall(CACSecurityPage *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180009380`
- `0x180009f38`
- `0x18000a29c`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000b63c`
- `0x18000ba98`
- `0x18000d714`

## callees

- `0x180008498`
- `0x180010cf0`

## pseudocode

```c
struct _DOT11EXT_IHV_PARAMS *__fastcall CACSecurityPage::GetUpdatedIHVParams(CACSecurityPage *this)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  __int64 v4; // rdx
  unsigned int *v5; // r8
  bool v6; // zf
  unsigned int v7; // ecx
  unsigned int v8; // eax
  char *v9; // r8
  BOOL v10; // eax
  __int64 v11; // rdx
  _OWORD *v12; // rcx
  __int64 v13; // rdx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  int v16; // ecx
  __int128 v17; // xmm0
  int v18; // eax

  v2 = *(_QWORD *)(*((_QWORD *)this + 5) + 552LL);
  v3 = *(_QWORD *)(v2 + 32);
  v4 = *(_QWORD *)(v3 + 424);
  if ( v4 && (v5 = *(unsigned int **)(v4 + 24)) != 0 )
  {
    v6 = *(_DWORD *)(v3 + 432) == 0;
    v7 = 0x80000000;
    v8 = 0x80000000;
    if ( v6 )
      v8 = *v5;
    v9 = (char *)this + 1192;
    *((_DWORD *)this + 298) = v8;
    if ( !*(_DWORD *)(*(_QWORD *)(v2 + 32) + 432LL) )
      v7 = *(_DWORD *)(*(_QWORD *)(v4 + 24) + 4LL);
  }
  else
  {
    v9 = (char *)this + 1192;
    v7 = 0x80000000;
    *(_DWORD *)v9 = 0x80000000;
  }
  *((_DWORD *)this + 299) = v7;
  v10 = v4 && *(_DWORD *)(v4 + 32);
  *((_DWORD *)v9 + 2) = v10;
  *((_DWORD *)this + 305) = 0;
  *((_QWORD *)this + 153) = 0;
  *(_OWORD *)(v9 + 12) = 0;
  if ( *((_DWORD *)this + 300) && *(_DWORD *)(v4 + 40) )
  {
    v11 = *(_QWORD *)(v4 + 48) + *(unsigned int *)(*(_QWORD *)(v4 + 48) + 64LL);
    if ( (*(_BYTE *)(v11 + 20) & 1) != 0 )
    {
      *((_DWORD *)this + 305) = *(_DWORD *)(v11 + 24);
      *((_QWORD *)this + 153) = v11 + *(unsigned int *)(v11 + 28);
    }
    *(_OWORD *)((char *)this + 1204) = *(_OWORD *)(v11 + 4);
  }
  *((_QWORD *)this + 81) = v9;
  CreateIhvSsidList(*(struct DOT11_SSID_LIST **)(v2 + 8), (struct _DOT11EXT_IHV_SSID_LIST **)this + 79);
  v12 = (_OWORD *)((char *)this + 656);
  *((_DWORD *)this + 160) = *(_DWORD *)(v2 + 16);
  v13 = 4;
  v14 = (_OWORD *)(*((_QWORD *)this + 5) + 24LL);
  do
  {
    *v12 = *v14;
    v12[1] = v14[1];
    v12[2] = v14[2];
    v12[3] = v14[3];
    v12[4] = v14[4];
    v12[5] = v14[5];
    v12[6] = v14[6];
    v15 = v14[7];
    v14 += 8;
    v12[7] = v15;
    v12 += 8;
    --v13;
  }
  while ( v13 );
  v16 = *((_DWORD *)this + 311);
  v17 = *(_OWORD *)*((_QWORD *)this + 2);
  *((_DWORD *)this + 292) = 0;
  *(_OWORD *)((char *)this + 1172) = v17;
  *((_DWORD *)this + 160) = *(_DWORD *)(v2 + 16);
  v18 = 0;
  if ( (v16 & 1) != 0 )
  {
    *((_DWORD *)this + 292) = 1;
    v18 = 1;
  }
  if ( (v16 & 2) != 0 )
    *((_DWORD *)this + 292) = v18 | 2;
  return (struct _DOT11EXT_IHV_PARAMS *)((char *)this + 632);
}

```

## disassembly

```asm
0x180008498  mov     [rsp+arg_0], rbx
0x18000849d  mov     [rsp+arg_8], rsi
0x1800084a2  push    rdi
0x1800084a3  sub     rsp, 20h
0x1800084a7  mov     rax, [rcx+28h]
0x1800084ab  mov     rbx, rcx
0x1800084ae  mov     rdi, [rax+228h]
0x1800084b5  mov     rax, [rdi+20h]
0x1800084b9  mov     rdx, [rax+1A8h]
0x1800084c0  test    rdx, rdx
0x1800084c3  jz      short loc_180008501
0x1800084c5  mov     r8, [rdx+18h]
0x1800084c9  test    r8, r8
0x1800084cc  jz      short loc_180008501
0x1800084ce  cmp     dword ptr [rax+1B0h], 0
0x1800084d5  mov     ecx, 80000000h
0x1800084da  mov     eax, ecx
0x1800084dc  jnz     short loc_1800084E1
0x1800084de  mov     eax, [r8]
0x1800084e1  lea     r8, [rbx+4A8h]
0x1800084e8  mov     [r8], eax
0x1800084eb  mov     rax, [rdi+20h]
0x1800084ef  cmp     dword ptr [rax+1B0h], 0
0x1800084f6  jnz     short loc_180008510
0x1800084f8  mov     rax, [rdx+18h]
0x1800084fc  mov     ecx, [rax+4]
0x1800084ff  jmp     short loc_180008510
0x180008501  lea     r8, [rcx+4A8h]
0x180008508  mov     ecx, 80000000h
0x18000850d  mov     [r8], ecx
0x180008510  mov     [rbx+4ACh], ecx
0x180008516  test    rdx, rdx
0x180008519  jz      short loc_180008528
0x18000851b  cmp     dword ptr [rdx+20h], 0
0x18000851f  jz      short loc_180008528
0x180008521  mov     eax, 1
0x180008526  jmp     short loc_18000852A
0x180008528  xor     eax, eax
0x18000852a  mov     [r8+8], eax
0x18000852e  xorps   xmm0, xmm0
0x180008531  mov     dword ptr [rbx+4C4h], 0
0x18000853b  mov     qword ptr [rbx+4C8h], 0
0x180008546  movups  xmmword ptr [r8+0Ch], xmm0
0x18000854b  cmp     dword ptr [rbx+4B0h], 0
0x180008552  jz      short loc_18000858C
0x180008554  cmp     dword ptr [rdx+28h], 0
0x180008558  jz      short loc_18000858C
0x18000855a  mov     rcx, [rdx+30h]
0x18000855e  mov     edx, [rcx+40h]
0x180008561  add     rdx, rcx
0x180008564  test    byte ptr [rdx+14h], 1
0x180008568  jz      short loc_180008580
0x18000856a  mov     eax, [rdx+18h]
0x18000856d  mov     [rbx+4C4h], eax
0x180008573  mov     eax, [rdx+1Ch]
0x180008576  add     rax, rdx
0x180008579  mov     [rbx+4C8h], rax
0x180008580  movups  xmm0, xmmword ptr [rdx+4]
0x180008584  movdqu  xmmword ptr [rbx+4B4h], xmm0
0x18000858c  lea     rsi, [rbx+278h]
0x180008593  mov     [rsi+10h], r8
0x180008597  mov     rdx, rsi; struct _DOT11EXT_IHV_SSID_LIST **
0x18000859a  mov     rcx, [rdi+8]; struct DOT11_SSID_LIST *
0x18000859e  call    ?CreateIhvSsidList@@YAKPEAUDOT11_SSID_LIST@@PEAPEAU_DOT11EXT_IHV_SSID_LIST@@@Z; CreateIhvSsidList(DOT11_SSID_LIST *,_DOT11EXT_IHV_SSID_LIST * *)
0x1800085a3  mov     eax, [rdi+10h]
0x1800085a6  lea     rcx, [rbx+290h]
0x1800085ad  mov     [rbx+280h], eax
0x1800085b3  mov     edx, 4
0x1800085b8  mov     rax, [rbx+28h]
0x1800085bc  add     rax, 18h
0x1800085c0  lea     r8d, [rdx+7Ch]
0x1800085c4  movups  xmm0, xmmword ptr [rax]
0x1800085c7  movups  xmmword ptr [rcx], xmm0
0x1800085ca  movups  xmm1, xmmword ptr [rax+10h]
0x1800085ce  movups  xmmword ptr [rcx+10h], xmm1
0x1800085d2  movups  xmm0, xmmword ptr [rax+20h]
0x1800085d6  movups  xmmword ptr [rcx+20h], xmm0
0x1800085da  movups  xmm1, xmmword ptr [rax+30h]
0x1800085de  movups  xmmword ptr [rcx+30h], xmm1
0x1800085e2  movups  xmm0, xmmword ptr [rax+40h]
0x1800085e6  movups  xmmword ptr [rcx+40h], xmm0
0x1800085ea  movups  xmm1, xmmword ptr [rax+50h]
0x1800085ee  movups  xmmword ptr [rcx+50h], xmm1
0x1800085f2  movups  xmm0, xmmword ptr [rax+60h]
0x1800085f6  movups  xmmword ptr [rcx+60h], xmm0
0x1800085fa  movups  xmm1, xmmword ptr [rax+70h]
0x1800085fe  add     rax, r8
0x180008601  movups  xmmword ptr [rcx+70h], xmm1
0x180008605  add     rcx, r8
0x180008608  sub     rdx, 1
0x18000860c  jnz     short loc_1800085C4
0x18000860e  mov     rax, [rbx+10h]
0x180008612  mov     ecx, [rbx+4DCh]
0x180008618  movups  xmm0, xmmword ptr [rax]
0x18000861b  mov     [rbx+490h], edx
0x180008621  movdqu  xmmword ptr [rbx+494h], xmm0
0x180008629  mov     eax, [rdi+10h]
0x18000862c  mov     [rbx+280h], eax
0x180008632  xor     eax, eax
0x180008634  test    cl, 1
0x180008637  jz      short loc_180008646
0x180008639  mov     dword ptr [rbx+490h], 1
0x180008643  lea     eax, [rdx+1]
0x180008646  test    cl, 2
0x180008649  jz      short loc_180008654
0x18000864b  or      eax, 2
0x18000864e  mov     [rbx+490h], eax
0x180008654  mov     rbx, [rsp+28h+arg_0]
0x180008659  mov     rax, rsi
0x18000865c  mov     rsi, [rsp+28h+arg_8]
0x180008661  add     rsp, 20h
0x180008665  pop     rdi
0x180008666  retn
```
