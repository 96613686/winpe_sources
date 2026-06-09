# UpdateSampleTimeWindowInformation

- ea: `0x140014fbc`
- end: `0x140015115`
- name: `UpdateSampleTimeWindowInformation`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140013930`

## callees

- `0x140005464`
- `0x140014fbc`

## pseudocode

```c
void __fastcall UpdateSampleTimeWindowInformation(_QWORD *a1)
{
  _QWORD *v2; // rbx
  unsigned __int64 v3; // r8
  unsigned __int64 *v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rtt
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx

  if ( a1[27] && a1[25] )
  {
    v2 = (_QWORD *)a1[6];
    v3 = v2[99];
    v4 = v2 + 97;
    if ( v3 )
      *v4 = v2[98] / v3;
    v5 = *v4;
    v6 = v5;
    v7 = a1[27] * a1[25];
    if ( !v5 )
      v6 = v2[95];
    v8 = 8 * a1[24] * v6;
    v2[104] = v8 / v7;
    v9 = v8 / v7;
    v2[103] = v9 / 0xC8;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_qiii(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        a1,
        a1[27],
        v5,
        v9);
    v10 = v2[101];
    if ( v10 )
    {
      v11 = v2[102];
      if ( v11 )
        v2[100] = v10 / v11;
    }
    v12 = v2[100];
    if ( v12 )
    {
      v13 = v12 + v2[11];
      v14 = 2 * v12;
      v15 = v13 >> 1;
      if ( v15 <= v14 )
        v14 = v15;
      v16 = v2[12] / 0x14uLL;
      if ( v14 > v16 )
        v16 = v14;
      v2[10] = v16;
    }
  }
}

```

## disassembly

```asm
0x140014fbc  push    rbx
0x140014fbe  sub     rsp, 40h
0x140014fc2  cmp     qword ptr [rcx+0D8h], 0
0x140014fca  mov     r9, rcx
0x140014fcd  jz      loc_14001510E
0x140014fd3  cmp     qword ptr [rcx+0C8h], 0
0x140014fdb  jz      loc_14001510E
0x140014fe1  mov     rbx, [rcx+30h]
0x140014fe5  mov     r8, [rbx+318h]
0x140014fec  lea     rcx, [rbx+308h]
0x140014ff3  test    r8, r8
0x140014ff6  jz      short loc_140015007
0x140014ff8  mov     rax, [rbx+310h]
0x140014fff  xor     edx, edx
0x140015001  div     r8
0x140015004  mov     [rcx], rax
0x140015007  mov     r8, [rcx]
0x14001500a  xor     edx, edx
0x14001500c  mov     rcx, [r9+0C8h]
0x140015013  mov     rax, r8
0x140015016  imul    rcx, [r9+0D8h]
0x14001501e  test    r8, r8
0x140015021  jnz     short loc_14001502A
0x140015023  mov     rax, [rbx+2F8h]
0x14001502a  imul    rax, [r9+0C0h]
0x140015032  shl     rax, 3
0x140015036  div     rcx
0x140015039  mov     [rbx+340h], rax
0x140015040  mov     rcx, rax
0x140015043  mov     rax, 47AE147AE147AE15h
0x14001504d  mul     rcx
0x140015050  mov     rax, rcx
0x140015053  sub     rax, rdx
0x140015056  shr     rax, 1
0x140015059  add     rax, rdx
0x14001505c  shr     rax, 7
0x140015060  mov     [rbx+338h], rax
0x140015067  mov     r10, cs:WPP_GLOBAL_Control
0x14001506e  lea     rax, WPP_GLOBAL_Control
0x140015075  cmp     r10, rax
0x140015078  jz      short loc_1400150AD
0x14001507a  mov     eax, [r10+2Ch]
0x14001507e  test    al, 20h
0x140015080  jz      short loc_1400150AD
0x140015082  mov     rax, [r9+0D8h]
0x140015089  mov     edx, 28h ; '('
0x14001508e  mov     [rsp+48h+var_18], rcx
0x140015093  mov     rcx, [r10+18h]
0x140015097  mov     [rsp+48h+var_20], r8
0x14001509c  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400150a3  mov     [rsp+48h+var_28], rax
0x1400150a8  call    WPP_SF_qiii
0x1400150ad  mov     rax, [rbx+328h]
0x1400150b4  test    rax, rax
0x1400150b7  jz      short loc_1400150D1
0x1400150b9  mov     rcx, [rbx+330h]
0x1400150c0  test    rcx, rcx
0x1400150c3  jz      short loc_1400150D1
0x1400150c5  xor     edx, edx
0x1400150c7  div     rcx
0x1400150ca  mov     [rbx+320h], rax
0x1400150d1  mov     rcx, [rbx+320h]
0x1400150d8  test    rcx, rcx
0x1400150db  jz      short loc_14001510E
0x1400150dd  mov     rax, [rbx+58h]
0x1400150e1  add     rax, rcx
0x1400150e4  add     rcx, rcx
0x1400150e7  shr     rax, 1
0x1400150ea  cmp     rax, rcx
0x1400150ed  cmovbe  rcx, rax
0x1400150f1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400150fb  mul     qword ptr [rbx+60h]
0x1400150ff  shr     rdx, 4
0x140015103  cmp     rcx, rdx
0x140015106  cmova   rdx, rcx
0x14001510a  mov     [rbx+50h], rdx
0x14001510e  add     rsp, 40h
0x140015112  pop     rbx
0x140015113  retn
```
