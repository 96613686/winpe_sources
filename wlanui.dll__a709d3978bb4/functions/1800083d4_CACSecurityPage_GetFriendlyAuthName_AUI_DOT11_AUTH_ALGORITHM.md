# CACSecurityPage::GetFriendlyAuthName(AUI_DOT11_AUTH_ALGORITHM)

- ea: `0x1800083d4`
- end: `0x180008491`
- name: `?GetFriendlyAuthName@CACSecurityPage@@AEAAPEBGW4AUI_DOT11_AUTH_ALGORITHM@@@Z`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bd88`

## callees

- `0x1800083d4`

## import_xrefs

- `USER32!LoadStringW` at `0x180008478`
- `USER32!LoadStringW` at `0x180008478`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::GetFriendlyAuthName(__int64 a1, int a2)
{
  int v2; // edi
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  UINT v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  __int64 v11; // rbx

  v2 = 1;
  if ( a2 > 7 )
  {
    v8 = a2 - 8;
    if ( !v8 )
    {
      v7 = 17327;
      goto LABEL_23;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v7 = 17328;
      goto LABEL_23;
    }
    v10 = v9 - 2;
    if ( !v10 )
    {
      v7 = 17331;
      goto LABEL_23;
    }
    if ( v10 == 2147483636 )
    {
      v7 = 17106;
      goto LABEL_23;
    }
  }
  else
  {
    if ( a2 == 7 )
    {
      v7 = 17105;
      goto LABEL_23;
    }
    v3 = a2 - 1;
    if ( !v3 )
    {
      v7 = 17101;
      goto LABEL_23;
    }
    v4 = v3 - 1;
    if ( !v4 )
    {
      v7 = 17100;
      goto LABEL_23;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      v7 = 17102;
      goto LABEL_23;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      v7 = 17103;
      goto LABEL_23;
    }
    if ( v6 == 2 )
    {
      v7 = 17104;
LABEL_23:
      v11 = a1 + 96;
      LoadStringW(hInstance, v7, (LPWSTR)(a1 + 96), 256);
      return v11 & -(__int64)(v2 != 0);
    }
  }
  v2 = 0;
  v11 = a1 + 96;
  return v11 & -(__int64)(v2 != 0);
}

```

## disassembly

```asm
0x1800083d4  mov     [rsp+arg_0], rbx
0x1800083d9  push    rdi
0x1800083da  sub     rsp, 20h
0x1800083de  mov     r10, cs:hInstance
0x1800083e5  mov     edi, 1
0x1800083ea  cmp     edx, 7
0x1800083ed  jg      short loc_180008430
0x1800083ef  jz      short loc_180008429
0x1800083f1  sub     edx, edi
0x1800083f3  jz      short loc_180008422
0x1800083f5  sub     edx, edi
0x1800083f7  jz      short loc_18000841B
0x1800083f9  sub     edx, edi
0x1800083fb  jz      short loc_180008414
0x1800083fd  sub     edx, edi
0x1800083ff  jz      short loc_18000840D
0x180008401  cmp     edx, 2
0x180008404  jnz     short loc_180008446
0x180008406  mov     edx, 42D0h
0x18000840b  jmp     short loc_180008468
0x18000840d  mov     edx, 42CFh
0x180008412  jmp     short loc_180008468
0x180008414  mov     edx, 42CEh
0x180008419  jmp     short loc_180008468
0x18000841b  mov     edx, 42CCh
0x180008420  jmp     short loc_180008468
0x180008422  mov     edx, 42CDh
0x180008427  jmp     short loc_180008468
0x180008429  mov     edx, 42D1h
0x18000842e  jmp     short loc_180008468
0x180008430  sub     edx, 8
0x180008433  jz      short loc_180008463
0x180008435  sub     edx, edi
0x180008437  jz      short loc_18000845C
0x180008439  sub     edx, 2
0x18000843c  jz      short loc_180008455
0x18000843e  cmp     edx, 7FFFFFF4h
0x180008444  jz      short loc_18000844E
0x180008446  xor     edi, edi
0x180008448  lea     rbx, [rcx+60h]
0x18000844c  jmp     short loc_18000847E
0x18000844e  mov     edx, 42D2h
0x180008453  jmp     short loc_180008468
0x180008455  mov     edx, 43B3h
0x18000845a  jmp     short loc_180008468
0x18000845c  mov     edx, 43B0h
0x180008461  jmp     short loc_180008468
0x180008463  mov     edx, 43AFh; uID
0x180008468  lea     rbx, [rcx+60h]
0x18000846c  mov     r9d, 100h; cchBufferMax
0x180008472  mov     r8, rbx; lpBuffer
0x180008475  mov     rcx, r10; hInstance
0x180008478  call    cs:__imp_LoadStringW
0x18000847e  neg     edi
0x180008480  sbb     rax, rax
0x180008483  and     rax, rbx
0x180008486  mov     rbx, [rsp+28h+arg_0]
0x18000848b  add     rsp, 20h
0x18000848f  pop     rdi
0x180008490  retn
```
