# CTrkWksSvc::MendLink(void *,ulong,ulong,CDomainRelativeObjId const &,CDomainRelativeObjId const &,CMachineId const &,CDomainRelativeObjId *,CDomainRelativeObjId *,CMachineId *,ushort *)

- ea: `0x180003f90`
- end: `0x180004749`
- name: `?MendLink@CTrkWksSvc@@QEAAJPEAXKKAEBUCDomainRelativeObjId@@1AEBUCMachineId@@PEAU2@3PEAU3@PEAG@Z`
- size: `1977`
- prototype: `__int64 __fastcall(CTrkWksSvc *this, void *, DWORD, int, const struct CDomainRelativeObjId *, const struct CDomainRelativeObjId *, const struct CMachineId *, struct CDomainRelativeObjId *, struct CDomainRelativeObjId *, struct CMachineId *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003d00`

## callees

- `0x180003f90`
- `0x1800048e0`
- `0x18000b4a0`
- `0x180010fb2`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004167`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800041ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004205`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004167`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800041ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004205`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000473e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000473e`

## pseudocode

```c
__int64 __fastcall CTrkWksSvc::MendLink(
        CTrkWksSvc *this,
        void *a2,
        DWORD a3,
        int a4,
        const struct CDomainRelativeObjId *a5,
        const struct CDomainRelativeObjId *a6,
        const struct CMachineId *a7,
        struct CDomainRelativeObjId *a8,
        struct CDomainRelativeObjId *a9,
        struct CMachineId *a10,
        unsigned __int16 *a11)
{
  unsigned __int16 *v13; // r14
  struct CTrkWksSvc *v14; // rsi
  int v15; // r15d
  __int128 v16; // xmm6
  int v17; // eax
  int v18; // edi
  int v19; // r14d
  __int64 v20; // rsi
  struct CDomainRelativeObjId *v21; // r12
  struct CDomainRelativeObjId *v22; // r13
  __int64 v24; // rax
  unsigned __int16 *v25; // rcx
  int v26; // r8d
  unsigned __int16 v27; // dx
  struct CDomainRelativeObjId *v28; // rcx
  struct CDomainRelativeObjId *v29; // rcx
  int v30; // [rsp+48h] [rbp-5F0h] BYREF
  int v31; // [rsp+50h] [rbp-5E8h]
  unsigned __int16 *v32; // [rsp+58h] [rbp-5E0h]
  struct CMachineId *v33; // [rsp+60h] [rbp-5D8h]
  void *v34; // [rsp+68h] [rbp-5D0h]
  struct CTrkWksSvc *v35; // [rsp+70h] [rbp-5C8h]
  struct CDomainRelativeObjId *v36; // [rsp+78h] [rbp-5C0h]
  struct CDomainRelativeObjId *v37; // [rsp+80h] [rbp-5B8h]
  __int128 Buf1; // [rsp+90h] [rbp-5A8h] BYREF
  const struct CMachineId *v39; // [rsp+A0h] [rbp-598h]
  struct CDomainRelativeObjId *v40; // [rsp+A8h] [rbp-590h]
  struct CDomainRelativeObjId *v41; // [rsp+B0h] [rbp-588h]
  struct CDomainRelativeObjId *v42; // [rsp+B8h] [rbp-580h]
  struct CDomainRelativeObjId *v43; // [rsp+C0h] [rbp-578h]
  __int128 v44; // [rsp+D0h] [rbp-568h]
  __int128 v45; // [rsp+E0h] [rbp-558h]
  __int128 v46; // [rsp+F0h] [rbp-548h]
  __int128 v47; // [rsp+100h] [rbp-538h]
  __int128 v48; // [rsp+110h] [rbp-528h]
  __int128 Buf2; // [rsp+130h] [rbp-508h] BYREF
  __int128 v50; // [rsp+140h] [rbp-4F8h] BYREF
  __int128 v51; // [rsp+150h] [rbp-4E8h]
  __int128 v52; // [rsp+160h] [rbp-4D8h]
  __int128 v53; // [rsp+170h] [rbp-4C8h]
  __int128 v54; // [rsp+180h] [rbp-4B8h] BYREF
  __int128 v55; // [rsp+190h] [rbp-4A8h]
  __int128 v56; // [rsp+1A0h] [rbp-498h]
  __int128 v57; // [rsp+1B0h] [rbp-488h]
  __int128 v58; // [rsp+1C0h] [rbp-478h]
  unsigned __int16 v59; // [rsp+1D0h] [rbp-468h] BYREF
  _BYTE v60[6]; // [rsp+1D2h] [rbp-466h] BYREF
  unsigned __int16 v61[264]; // [rsp+3E0h] [rbp-258h] BYREF

  v34 = a2;
  v40 = a9;
  v42 = a9;
  v37 = a9;
  v41 = a8;
  v43 = a8;
  v30 = a4;
  v39 = a7;
  v36 = a8;
  v33 = a10;
  v13 = a11;
  v32 = a11;
  *(_QWORD *)&Buf1 = a11;
  v14 = g_ptrkwks;
  v35 = g_ptrkwks;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v54 = *(_OWORD *)a5;
  v55 = *((_OWORD *)a5 + 1);
  v56 = *(_OWORD *)a6;
  v57 = *((_OWORD *)a6 + 1);
  v58 = *(_OWORD *)a7;
  v15 = 0;
  v59 = 0;
  memset_0(v60, 0, 0x206u);
  v16 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  Buf2 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v31 = 0;
  if ( GetTickCount() >= a3 )
  {
    v18 = -1913990907;
    goto LABEL_16;
  }
  v17 = CTrkWksSvc::SearchChain(v14, a2, 1, a3, &v30, 1, &v54, &v59);
  v18 = v17;
  if ( v17 >= 0 || v17 == -1913990907 )
  {
    Buf2 = v54;
    v50 = v55;
    v51 = v56;
    v52 = v57;
    v53 = v58;
LABEL_16:
    v20 = 260;
    goto LABEL_19;
  }
  v19 = v17;
  v20 = 260;
  if ( v17 == -1913990906 )
  {
    v15 = 1;
    v31 = 1;
    v16 = v54;
    v44 = v54;
    v45 = v55;
    v46 = v56;
    v47 = v57;
    v48 = v58;
    StringCchCopyW(v61, 0x104u, &v59);
  }
  v18 = -1913991141;
  if ( GetTickCount() >= a3 )
  {
    v18 = -1913990907;
  }
  else
  {
    if ( v19 == -1913990911 )
    {
      Buf2 = v54;
      v50 = v55;
      v51 = v56;
      v52 = v57;
      v53 = v58;
      v18 = CTrkWksSvc::SearchChain(v35, v34, 0xFFFFFFFFLL, a3, &v30, 0, &Buf2, &v59);
    }
    if ( GetTickCount() >= a3 )
    {
      v18 = -1913990907;
      v13 = v32;
      goto LABEL_19;
    }
    if ( v19 != -1913990908 && v18 == -1913991141 )
    {
      Buf2 = *(_OWORD *)a5;
      v50 = *((_OWORD *)a5 + 1);
      v51 = *(_OWORD *)a6;
      v52 = *((_OWORD *)a6 + 1);
      v53 = *(_OWORD *)v39;
      v30 |= 2u;
      v18 = CTrkWksSvc::SearchChain(v35, v34, 1, a3, &v30, 0, &Buf2, &v59);
      v13 = v32;
      goto LABEL_19;
    }
  }
  v13 = v32;
LABEL_19:
  v21 = v40;
  v22 = v41;
  if ( v18 >= 0 )
  {
    Buf1 = 0;
    if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
    {
      Buf1 = 0;
      if ( memcmp_0(&Buf1, &v50, 0x10u) )
        goto LABEL_27;
    }
    v18 = -1913990906;
  }
  if ( v18 != -1913990906 )
  {
    if ( v15 )
    {
      v18 = StringCchCopyW(v13, 0x104u, v61);
      if ( v18 >= 0 )
      {
        v18 = -1913990906;
        *(_OWORD *)v22 = v16;
        *((_OWORD *)v36 + 1) = v45;
        *(_QWORD *)v21 = v46;
        v29 = v37;
        *((_QWORD *)v37 + 1) = *((_QWORD *)&v46 + 1);
        *((_OWORD *)v29 + 1) = v47;
        *(_OWORD *)v33 = v48;
      }
    }
    goto LABEL_22;
  }
LABEL_27:
  v24 = 2147483646;
  v25 = &v59;
  v26 = 0;
  do
  {
    if ( !v24 )
      break;
    v27 = *v25;
    if ( !*v25 )
      break;
    ++v25;
    *v13++ = v27;
    --v24;
    --v20;
  }
  while ( v20 );
  if ( !v20 )
  {
    --v13;
    v26 = -2147024774;
  }
  *v13 = 0;
  if ( v26 < 0 )
  {
    v18 = v26;
  }
  else
  {
    *(_OWORD *)v22 = Buf2;
    *((_OWORD *)v36 + 1) = v50;
    *(_QWORD *)v21 = v51;
    v28 = v37;
    *((_QWORD *)v37 + 1) = *((_QWORD *)&v51 + 1);
    *((_OWORD *)v28 + 1) = v52;
    *(_OWORD *)v33 = v53;
  }
LABEL_22:
  if ( (v30 & 8) != 0 )
    Sleep(0x3A98u);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180003f90  mov     r11, rsp
0x180003f93  mov     [r11+8], rbx
0x180003f97  mov     [r11+18h], rsi
0x180003f9b  push    rdi
0x180003f9c  push    r12
0x180003f9e  push    r13
0x180003fa0  push    r14
0x180003fa2  push    r15
0x180003fa4  sub     rsp, 610h
0x180003fab  movaps  xmmword ptr [r11-38h], xmm6
0x180003fb0  mov     rax, cs:__security_cookie
0x180003fb7  xor     rax, rsp
0x180003fba  mov     [rsp+638h+var_48], rax
0x180003fc2  mov     ebx, r8d
0x180003fc5  mov     rdi, rdx
0x180003fc8  mov     [rsp+638h+var_5D0], rdx
0x180003fcd  mov     rax, [rsp+638h+arg_40]
0x180003fd5  mov     [rsp+638h+var_590], rax
0x180003fdd  mov     [rsp+638h+var_580], rax
0x180003fe5  mov     [rsp+638h+var_5B8], rax
0x180003fed  mov     rdx, [rsp+638h+arg_38]
0x180003ff5  mov     [rsp+638h+var_588], rdx
0x180003ffd  mov     [rsp+638h+var_578], rdx
0x180004005  mov     [rsp+638h+var_5F0], r9d
0x18000400a  mov     rcx, [rsp+638h+arg_30]
0x180004012  mov     [rsp+638h+var_598], rcx
0x18000401a  mov     [rsp+638h+var_5C0], rdx
0x18000401f  mov     rax, [rsp+638h+arg_48]
0x180004027  mov     [rsp+638h+var_5D8], rax
0x18000402c  mov     r14, [rsp+638h+arg_50]
0x180004034  mov     [rsp+638h+var_5E0], r14
0x180004039  mov     qword ptr [rsp+638h+Buf1], r14
0x180004041  mov     rsi, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x180004048  mov     [rsp+638h+var_5C8], rsi
0x18000404d  xorps   xmm0, xmm0
0x180004050  xorps   xmm1, xmm1
0x180004053  movups  [rsp+638h+var_4A8], xmm1
0x18000405b  movups  [rsp+638h+var_498], xmm0
0x180004063  movups  [rsp+638h+var_488], xmm1
0x18000406b  movups  [rsp+638h+var_478], xmm0
0x180004073  mov     r13, [rsp+638h+arg_20]
0x18000407b  movups  xmm0, xmmword ptr [r13+0]
0x180004080  movaps  [rsp+638h+var_4B8], xmm0
0x180004088  mov     rax, [r13+10h]
0x18000408c  mov     [r11-4A8h], rax
0x180004093  mov     rax, [r13+18h]
0x180004097  mov     [r11-4A0h], rax
0x18000409e  mov     r12, [rsp+638h+arg_28]
0x1800040a6  mov     rax, [r12]
0x1800040aa  mov     [r11-498h], rax
0x1800040b1  mov     rax, [r12+8]
0x1800040b6  mov     [r11-490h], rax
0x1800040bd  mov     rax, [r12+10h]
0x1800040c2  mov     [r11-488h], rax
0x1800040c9  mov     rax, [r12+18h]
0x1800040ce  mov     [r11-480h], rax
0x1800040d5  mov     rax, [rcx]
0x1800040d8  mov     [r11-478h], rax
0x1800040df  mov     rax, [rcx+8]
0x1800040e3  mov     [r11-470h], rax
0x1800040ea  xor     r15d, r15d
0x1800040ed  mov     [r11-468h], r15w
0x1800040f5  xor     edx, edx; Val
0x1800040f7  mov     r8d, 206h; Size
0x1800040fd  lea     rcx, [r11-466h]; void *
0x180004104  call    memset_0
0x180004109  xorps   xmm6, xmm6
0x18000410c  movaps  [rsp+638h+var_568], xmm6
0x180004114  xorps   xmm0, xmm0
0x180004117  movups  [rsp+638h+var_558], xmm0
0x18000411f  xorps   xmm1, xmm1
0x180004122  movups  [rsp+638h+var_548], xmm1
0x18000412a  movups  [rsp+638h+var_538], xmm0
0x180004132  movups  [rsp+638h+var_528], xmm1
0x18000413a  movups  [rsp+638h+Buf2], xmm0
0x180004142  movups  [rsp+638h+var_4F8], xmm1
0x18000414a  movups  [rsp+638h+var_4E8], xmm0
0x180004152  movups  [rsp+638h+var_4D8], xmm1
0x18000415a  movups  [rsp+638h+var_4C8], xmm0
0x180004162  mov     [rsp+638h+var_5E8], r15d
0x180004167  call    cs:__imp_GetTickCount
0x18000416d  cmp     eax, ebx
0x18000416f  jnb     loc_18000434E
0x180004175  lea     rax, [rsp+638h+var_468]
0x18000417d  mov     [rsp+638h+var_600], rax
0x180004182  lea     rax, [rsp+638h+var_4B8]
0x18000418a  mov     [rsp+638h+var_608], rax
0x18000418f  mov     [rsp+638h+var_610], 1
0x180004197  lea     rax, [rsp+638h+var_5F0]
0x18000419c  mov     [rsp+638h+var_618], rax
0x1800041a1  mov     r9d, ebx
0x1800041a4  mov     r8d, 1
0x1800041aa  mov     rdx, rdi
0x1800041ad  mov     rcx, rsi
0x1800041b0  call    ?SearchChain@CTrkWksSvc@@AEAAJPEAXHKPEAKW4SEARCH_FLAGS@1@PEAUSAllIDs@@PEAG@Z; CTrkWksSvc::SearchChain(void *,int,ulong,ulong *,CTrkWksSvc::SEARCH_FLAGS,SAllIDs *,ushort *)
0x1800041b5  mov     edi, eax
0x1800041b7  mov     [rsp+638h+var_5F8], eax
0x1800041bb  test    eax, eax
0x1800041bd  jns     loc_1800042EC
0x1800041c3  cmp     eax, 8DEAD105h
0x1800041c8  jz      loc_1800042EC
0x1800041ce  mov     r14d, eax
0x1800041d1  mov     esi, 104h
0x1800041d6  cmp     eax, 8DEAD106h
0x1800041db  jz      loc_180004374
0x1800041e1  mov     edi, 8DEAD01Bh
0x1800041e6  mov     [rsp+638h+var_5F8], edi
0x1800041ea  call    cs:__imp_GetTickCount
0x1800041f0  cmp     eax, ebx
0x1800041f2  jnb     loc_180004361
0x1800041f8  cmp     r14d, 8DEAD101h
0x1800041ff  jz      loc_1800043FC
0x180004205  call    cs:__imp_GetTickCount
0x18000420b  cmp     eax, ebx
0x18000420d  jnb     loc_1800042D9
0x180004213  cmp     r14d, 8DEAD104h
0x18000421a  jz      loc_18000436A
0x180004220  cmp     edi, 8DEAD01Bh
0x180004226  jnz     loc_18000436A
0x18000422c  movups  xmm0, xmmword ptr [r13+0]
0x180004231  movaps  [rsp+638h+Buf2], xmm0
0x180004239  movups  xmm1, xmmword ptr [r13+10h]
0x18000423e  movaps  [rsp+638h+var_4F8], xmm1
0x180004246  movups  xmm0, xmmword ptr [r12]
0x18000424b  movaps  [rsp+638h+var_4E8], xmm0
0x180004253  movups  xmm1, xmmword ptr [r12+10h]
0x180004259  movaps  [rsp+638h+var_4D8], xmm1
0x180004261  mov     r9, [rsp+638h+var_598]
0x180004269  mov     rax, [r9]
0x18000426c  mov     qword ptr [rsp+638h+var_4C8], rax
0x180004274  mov     rax, [r9+8]
0x180004278  mov     qword ptr [rsp+638h+var_4C8+8], rax
0x180004280  or      [rsp+638h+var_5F0], 2
0x180004285  lea     rax, [rsp+638h+var_468]
0x18000428d  mov     [rsp+638h+var_600], rax
0x180004292  lea     rax, [rsp+638h+Buf2]
0x18000429a  mov     [rsp+638h+var_608], rax
0x18000429f  mov     [rsp+638h+var_610], 0
0x1800042a7  lea     rax, [rsp+638h+var_5F0]
0x1800042ac  mov     [rsp+638h+var_618], rax
0x1800042b1  mov     r9d, ebx
0x1800042b4  mov     r8d, 1
0x1800042ba  mov     rdx, [rsp+638h+var_5D0]
0x1800042bf  mov     rcx, [rsp+638h+var_5C8]
0x1800042c4  call    ?SearchChain@CTrkWksSvc@@AEAAJPEAXHKPEAKW4SEARCH_FLAGS@1@PEAUSAllIDs@@PEAG@Z; CTrkWksSvc::SearchChain(void *,int,ulong,ulong *,CTrkWksSvc::SEARCH_FLAGS,SAllIDs *,ushort *)
0x1800042c9  mov     edi, eax
0x1800042cb  mov     [rsp+638h+var_5F8], eax
0x1800042cf  mov     r14, [rsp+638h+var_5E0]
0x1800042d4  jmp     loc_1800044AB
0x1800042d9  mov     edi, 8DEAD105h
0x1800042de  mov     [rsp+638h+var_5F8], edi
0x1800042e2  mov     r14, [rsp+638h+var_5E0]
0x1800042e7  jmp     loc_1800044AB
0x1800042ec  movaps  xmm0, [rsp+638h+var_4B8]
0x1800042f4  movaps  [rsp+638h+Buf2], xmm0
0x1800042fc  movaps  xmm1, [rsp+638h+var_4A8]
0x180004304  movaps  [rsp+638h+var_4F8], xmm1
0x18000430c  movaps  xmm0, [rsp+638h+var_498]
0x180004314  movaps  [rsp+638h+var_4E8], xmm0
0x18000431c  movaps  xmm1, [rsp+638h+var_488]
0x180004324  movaps  [rsp+638h+var_4D8], xmm1
0x18000432c  mov     rax, qword ptr [rsp+638h+var_478]
0x180004334  mov     qword ptr [rsp+638h+var_4C8], rax
0x18000433c  mov     rax, qword ptr [rsp+638h+var_478+8]
0x180004344  mov     qword ptr [rsp+638h+var_4C8+8], rax
0x18000434c  jmp     short loc_180004357
0x18000434e  mov     edi, 8DEAD105h
0x180004353  mov     [rsp+638h+var_5F8], edi
0x180004357  mov     esi, 104h
0x18000435c  jmp     loc_1800044AB
0x180004361  mov     edi, 8DEAD105h
0x180004366  mov     [rsp+638h+var_5F8], edi
0x18000436a  mov     r14, [rsp+638h+var_5E0]
0x18000436f  jmp     loc_1800044AB
0x180004374  mov     r15d, 1
0x18000437a  mov     [rsp+638h+var_5E8], r15d
0x18000437f  movaps  xmm6, [rsp+638h+var_4B8]
0x180004387  movaps  [rsp+638h+var_568], xmm6
0x18000438f  movaps  xmm0, [rsp+638h+var_4A8]
0x180004397  movaps  [rsp+638h+var_558], xmm0
0x18000439f  movaps  xmm1, [rsp+638h+var_498]
0x1800043a7  movaps  [rsp+638h+var_548], xmm1
0x1800043af  movaps  xmm0, [rsp+638h+var_488]
0x1800043b7  movaps  [rsp+638h+var_538], xmm0
0x1800043bf  mov     rax, qword ptr [rsp+638h+var_478]
0x1800043c7  mov     qword ptr [rsp+638h+var_528], rax
0x1800043cf  mov     rax, qword ptr [rsp+638h+var_478+8]
0x1800043d7  mov     qword ptr [rsp+638h+var_528+8], rax
0x1800043df  lea     r8, [rsp+638h+var_468]; unsigned __int16 *
0x1800043e7  mov     rdx, rsi; unsigned __int64
0x1800043ea  lea     rcx, [rsp+638h+var_258]; unsigned __int16 *
0x1800043f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800043f7  jmp     loc_1800041E1
0x1800043fc  movaps  xmm0, [rsp+638h+var_4B8]
0x180004404  movaps  [rsp+638h+Buf2], xmm0
0x18000440c  movaps  xmm1, [rsp+638h+var_4A8]
0x180004414  movaps  [rsp+638h+var_4F8], xmm1
0x18000441c  movaps  xmm0, [rsp+638h+var_498]
0x180004424  movaps  [rsp+638h+var_4E8], xmm0
0x18000442c  movaps  xmm1, [rsp+638h+var_488]
0x180004434  movaps  [rsp+638h+var_4D8], xmm1
0x18000443c  mov     rax, qword ptr [rsp+638h+var_478]
0x180004444  mov     qword ptr [rsp+638h+var_4C8], rax
0x18000444c  mov     rax, qword ptr [rsp+638h+var_478+8]
0x180004454  mov     qword ptr [rsp+638h+var_4C8+8], rax
0x18000445c  lea     rax, [rsp+638h+var_468]
0x180004464  mov     [rsp+638h+var_600], rax
0x180004469  lea     rax, [rsp+638h+Buf2]
0x180004471  mov     [rsp+638h+var_608], rax
0x180004476  mov     [rsp+638h+var_610], 0
0x18000447e  lea     rax, [rsp+638h+var_5F0]
0x180004483  mov     [rsp+638h+var_618], rax
0x180004488  mov     r9d, ebx
0x18000448b  mov     r8d, 0FFFFFFFFh
0x180004491  mov     rdx, [rsp+638h+var_5D0]
0x180004496  mov     rcx, [rsp+638h+var_5C8]
0x18000449b  call    ?SearchChain@CTrkWksSvc@@AEAAJPEAXHKPEAKW4SEARCH_FLAGS@1@PEAUSAllIDs@@PEAG@Z; CTrkWksSvc::SearchChain(void *,int,ulong,ulong *,CTrkWksSvc::SEARCH_FLAGS,SAllIDs *,ushort *)
0x1800044a0  mov     edi, eax
0x1800044a2  mov     [rsp+638h+var_5F8], eax
0x1800044a6  jmp     loc_180004205
0x1800044ab  xor     ebx, ebx
0x1800044ad  mov     r12, [rsp+638h+var_590]
0x1800044b5  mov     r13, [rsp+638h+var_588]
0x1800044bd  jmp     short loc_1800044F1
0x1800044bf  mov     edi, eax
0x1800044c1  mov     [rsp+638h+var_5F8], eax
0x1800044c5  xor     ebx, ebx
0x1800044c7  mov     esi, 104h
0x1800044cc  movaps  xmm6, [rsp+638h+var_568]
0x1800044d4  mov     r15d, [rsp+638h+var_5E8]
0x1800044d9  mov     r12, [rsp+638h+var_580]
0x1800044e1  mov     r13, [rsp+638h+var_578]
0x1800044e9  mov     r14, qword ptr [rsp+638h+Buf1]
0x1800044f1  test    edi, edi
0x1800044f3  jns     short loc_180004549
0x1800044f5  cmp     edi, 8DEAD106h
0x1800044fb  jz      loc_1800045AD
0x180004501  test    r15d, r15d
0x180004504  jnz     loc_18000468D
0x18000450a  test    byte ptr [rsp+638h+var_5F0], 8
0x18000450f  jnz     loc_180004739
0x180004515  mov     eax, edi
0x180004517  mov     rcx, [rsp+638h+var_48]
0x18000451f  xor     rcx, rsp; StackCookie
0x180004522  call    __security_check_cookie
0x180004527  lea     r11, [rsp+638h+var_28]
0x18000452f  mov     rbx, [r11+30h]
0x180004533  mov     rsi, [r11+40h]
0x180004537  movaps  xmm6, xmmword ptr [r11-10h]
0x18000453c  mov     rsp, r11
0x18000453f  pop     r15
0x180004541  pop     r14
0x180004543  pop     r13
0x180004545  pop     r12
0x180004547  pop     rdi
0x180004548  retn
0x180004549  xorps   xmm0, xmm0
0x18000454c  movups  [rsp+638h+Buf1], xmm0
0x180004554  mov     r8d, 10h; Size
0x18000455a  lea     rdx, [rsp+638h+Buf2]; Buf2
0x180004562  lea     rcx, [rsp+638h+Buf1]; Buf1
0x18000456a  call    memcmp_0
0x18000456f  test    eax, eax
0x180004571  jz      loc_180004683
0x180004577  xorps   xmm0, xmm0
0x18000457a  movups  [rsp+638h+Buf1], xmm0
0x180004582  mov     r8d, 10h; Size
0x180004588  lea     rdx, [rsp+638h+var_4F8]; Buf2
0x180004590  lea     rcx, [rsp+638h+Buf1]; Buf1
0x180004598  call    memcmp_0
0x18000459d  test    eax, eax
0x18000459f  jz      loc_180004683
0x1800045a5  test    edi, edi
0x1800045a7  js      loc_1800044F5
0x1800045ad  mov     eax, 7FFFFFFEh
0x1800045b2  lea     rcx, [rsp+638h+var_468]
0x1800045ba  mov     r8d, ebx
0x1800045bd  nop     dword ptr [rax]
0x1800045c0  test    rax, rax
0x1800045c3  jz      short loc_1800045E2
0x1800045c5  movzx   edx, word ptr [rcx]
0x1800045c8  test    dx, dx
0x1800045cb  jz      short loc_1800045E2
0x1800045cd  add     rcx, 2
0x1800045d1  mov     [r14], dx
0x1800045d5  add     r14, 2
0x1800045d9  dec     rax
0x1800045dc  sub     rsi, 1
0x1800045e0  jnz     short loc_1800045C0
0x1800045e2  test    rsi, rsi
0x1800045e5  jz      loc_18000472A
0x1800045eb  mov     [r14], bx
0x1800045ef  test    r8d, r8d
0x1800045f2  js      loc_18000467B
0x1800045f8  movaps  xmm0, [rsp+638h+Buf2]
0x180004600  movups  xmmword ptr [r13+0], xmm0
0x180004605  mov     rax, qword ptr [rsp+638h+var_4F8]
0x18000460d  mov     rcx, [rsp+638h+var_5C0]
0x180004612  mov     [rcx+10h], rax
0x180004616  mov     rax, qword ptr [rsp+638h+var_4F8+8]
  ... truncated ...
```
