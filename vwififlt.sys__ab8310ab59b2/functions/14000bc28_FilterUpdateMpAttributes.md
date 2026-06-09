# FilterUpdateMpAttributes

- ea: `0x14000bc28`
- end: `0x14000bfb0`
- name: `FilterUpdateMpAttributes`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000b8d0`

## callees

- `0x140007d00`
- `0x14000bc28`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f200`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x14000bdd0`
- `NDIS!NdisFreeMemory` at `0x14000bf16`
- `NDIS!NdisFreeMemory` at `0x14000bf68`
- `NDIS!NdisFreeMemory` at `0x14000bf94`
- `NDIS!NdisFreeMemory` at `0x14000bdd0`
- `NDIS!NdisFreeMemory` at `0x14000bf16`
- `NDIS!NdisFreeMemory` at `0x14000bf68`
- `NDIS!NdisFreeMemory` at `0x14000bf94`

## pseudocode

```c
__int64 __fastcall FilterUpdateMpAttributes(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // rbx
  unsigned int v4; // esi
  _BYTE *v7; // rax
  __int16 v8; // ax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  void *v12; // rcx
  size_t v13; // r8
  const void *v14; // rdx
  void *v15; // rbx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  _OWORD *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  _OWORD *v23; // [rsp+40h] [rbp+8h] BYREF
  void *v24; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(__int64 **)(a2 + 16);
  v4 = 0;
  v23 = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  while ( 1 )
  {
    if ( !v3 )
      goto LABEL_3;
    if ( *((_DWORD *)v3 + 2) == 66077 )
      break;
    v3 = (__int64 *)*v3;
  }
  if ( *((_DWORD *)v3 + 3) >= 0x58u )
  {
    if ( *((_BYTE *)v3 + 16) != 0xA2 )
      TraceAssert(
        "pRestartGen->Header.Type == NDIS_OBJECT_TYPE_RESTART_GENERAL_ATTRIBUTES",
        "onecoreuap\\net\\vwifi\\filter\\filter.c",
        1523);
    if ( *((_WORD *)v3 + 9) != 88 )
      TraceAssert(
        "pRestartGen->Header.Size == sizeof(NDIS_RESTART_GENERAL_ATTRIBUTES)",
        "onecoreuap\\net\\vwifi\\filter\\filter.c",
        1524);
    if ( *((_BYTE *)v3 + 17) )
    {
      *(_DWORD *)(a1 + 2312) = *((_DWORD *)v3 + 5);
      *(_DWORD *)(a1 + 2488) = *((_DWORD *)v3 + 20);
      *(_QWORD *)(a1 + 2320) = v3[3];
      *(_QWORD *)(a1 + 2336) = v3[4];
      *(_DWORD *)(a1 + 2360) = *((_DWORD *)v3 + 10);
      *(_DWORD *)(a1 + 2376) = *((_DWORD *)v3 + 11);
      *(_DWORD *)(a1 + 2380) = *((_DWORD *)v3 + 12);
      *(_DWORD *)(a1 + 2384) = *((_DWORD *)v3 + 13);
      v7 = (_BYTE *)v3[7];
      if ( v7 && *v7 == 0x88 )
      {
        v4 = AllocMem(*(_QWORD *)(a1 + 128), 20, a3, &v23);
        if ( v4 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_42;
          }
          v17 = 98;
          goto LABEL_36;
        }
        v18 = *(void **)(a1 + 2456);
        if ( v18 )
          NdisFreeMemory(v18, 0, 0);
        v19 = v3[7];
        v20 = v23;
        *v23 = *(_OWORD *)v19;
        *((_DWORD *)v20 + 4) = *(_DWORD *)(v19 + 16);
        *(_QWORD *)(a1 + 2456) = v20;
      }
      *(_DWORD *)(a1 + 2468) = 0;
      v8 = 71;
      if ( *(_DWORD *)(a1 + 2692) != 16 )
        v8 = 243;
      *(_WORD *)(a1 + 2476) = v8;
      *(_BYTE *)(a1 + 2478) = 1;
      *(_DWORD *)(a1 + 2464) = *((_DWORD *)v3 + 16);
      *(_DWORD *)(a1 + 2472) = *((_DWORD *)v3 + 18);
      v9 = *((_DWORD *)v3 + 21);
      if ( *(_BYTE *)(a1 + 2682) )
      {
        v10 = v9 + 16;
        *(_DWORD *)(a1 + 2492) = v10;
        *((_DWORD *)v3 + 21) = v10;
      }
      else
      {
        *(_DWORD *)(a1 + 2492) = v9;
      }
      *(_DWORD *)(a1 + 2480) = *((_DWORD *)v3 + 19);
      *(_DWORD *)(a1 + 2380) = *((_DWORD *)v3 + 12);
      *(_DWORD *)(a1 + 2504) = *((_DWORD *)v3 + 24);
      v11 = *((unsigned int *)v3 + 24);
      if ( (_DWORD)v11 && v3[11] )
      {
        v4 = AllocMem(*(_QWORD *)(a1 + 128), v11, a3, &v24);
        if ( v4 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_42;
          }
          v17 = 99;
LABEL_36:
          WPP_SF_d(v16->AttachedDevice, v17, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_42:
          v21 = *(void **)(a1 + 2456);
          if ( v21 )
          {
            NdisFreeMemory(v21, 0, 0);
            *(_QWORD *)(a1 + 2456) = 0;
          }
          v22 = *(void **)(a1 + 2496);
          if ( v22 )
          {
            NdisFreeMemory(v22, 0, 0);
            *(_QWORD *)(a1 + 2496) = 0;
          }
          goto LABEL_3;
        }
        v12 = *(void **)(a1 + 2496);
        if ( v12 )
          NdisFreeMemory(v12, 0, 0);
        v13 = *((unsigned int *)v3 + 24);
        v14 = (const void *)v3[11];
        v15 = v24;
        memmove(v24, v14, v13);
        *(_QWORD *)(a1 + 2496) = v15;
      }
      *(_BYTE *)(a1 + 2288) = 1;
    }
  }
LABEL_3:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x14000bc28  mov     rax, rsp
0x14000bc2b  mov     [rax+18h], rbx
0x14000bc2f  mov     [rax+20h], rsi
0x14000bc33  push    rdi
0x14000bc34  push    r14
0x14000bc36  push    r15
0x14000bc38  sub     rsp, 20h
0x14000bc3c  mov     rbx, [rdx+10h]
0x14000bc40  xor     esi, esi
0x14000bc42  mov     [rax+8], rsi
0x14000bc46  mov     rdi, rcx
0x14000bc49  mov     [rax+10h], rsi
0x14000bc4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc54  lea     r15, WPP_GLOBAL_Control
0x14000bc5b  cmp     rcx, r15
0x14000bc5e  jnz     loc_14000BE47
0x14000bc64  test    rbx, rbx
0x14000bc67  jnz     short loc_14000BC90
0x14000bc69  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc70  cmp     rcx, r15
0x14000bc73  jnz     loc_14000BE17
0x14000bc79  mov     rbx, [rsp+38h+arg_10]
0x14000bc7e  mov     eax, esi
0x14000bc80  mov     rsi, [rsp+38h+arg_18]
0x14000bc85  add     rsp, 20h
0x14000bc89  pop     r15
0x14000bc8b  pop     r14
0x14000bc8d  pop     rdi
0x14000bc8e  retn
0x14000bc90  cmp     dword ptr [rbx+8], 1021Dh
0x14000bc97  jnz     loc_14000BE3F
0x14000bc9d  mov     r14d, 58h ; 'X'
0x14000bca3  cmp     [rbx+0Ch], r14d
0x14000bca7  jb      short loc_14000BC69
0x14000bca9  cmp     byte ptr [rbx+10h], 0A2h
0x14000bcad  jnz     loc_14000BE6C
0x14000bcb3  cmp     [rbx+12h], r14w
0x14000bcb8  jnz     loc_14000BE8A
0x14000bcbe  mov     r14b, 1
0x14000bcc1  cmp     [rbx+11h], r14b
0x14000bcc5  jb      short loc_14000BC69
0x14000bcc7  mov     eax, [rbx+14h]
0x14000bcca  mov     [rdi+908h], eax
0x14000bcd0  mov     eax, [rbx+50h]
0x14000bcd3  mov     [rdi+9B8h], eax
0x14000bcd9  mov     rax, [rbx+18h]
0x14000bcdd  mov     [rdi+910h], rax
0x14000bce4  mov     rax, [rbx+20h]
0x14000bce8  mov     [rdi+920h], rax
0x14000bcef  mov     eax, [rbx+28h]
0x14000bcf2  mov     [rdi+938h], eax
0x14000bcf8  mov     eax, [rbx+2Ch]
0x14000bcfb  mov     [rdi+948h], eax
0x14000bd01  mov     eax, [rbx+30h]
0x14000bd04  mov     [rdi+94Ch], eax
0x14000bd0a  mov     eax, [rbx+34h]
0x14000bd0d  mov     [rdi+950h], eax
0x14000bd13  mov     rax, [rbx+38h]
0x14000bd17  test    rax, rax
0x14000bd1a  jnz     loc_14000BEA8
0x14000bd20  mov     dword ptr [rdi+9A4h], 0
0x14000bd2a  mov     eax, 47h ; 'G'
0x14000bd2f  cmp     dword ptr [rdi+0A84h], 10h
0x14000bd36  mov     ecx, 0F3h
0x14000bd3b  cmovnz  ax, cx
0x14000bd3f  mov     [rdi+9ACh], ax
0x14000bd46  mov     [rdi+9AEh], r14b
0x14000bd4d  mov     eax, [rbx+40h]
0x14000bd50  mov     [rdi+9A0h], eax
0x14000bd56  mov     eax, [rbx+48h]
0x14000bd59  mov     [rdi+9A8h], eax
0x14000bd5f  cmp     byte ptr [rdi+0A7Ah], 0
0x14000bd66  mov     eax, [rbx+54h]
0x14000bd69  jz      loc_14000BE0C
0x14000bd6f  add     eax, 10h
0x14000bd72  mov     [rdi+9BCh], eax
0x14000bd78  mov     [rbx+54h], eax
0x14000bd7b  mov     eax, [rbx+4Ch]
0x14000bd7e  mov     [rdi+9B0h], eax
0x14000bd84  mov     eax, [rbx+30h]
0x14000bd87  mov     [rdi+94Ch], eax
0x14000bd8d  mov     eax, [rbx+60h]
0x14000bd90  mov     [rdi+9C8h], eax
0x14000bd96  mov     edx, [rbx+60h]
0x14000bd99  test    edx, edx
0x14000bd9b  jz      short loc_14000BDF8
0x14000bd9d  cmp     qword ptr [rbx+58h], 0
0x14000bda2  jz      short loc_14000BDF8
0x14000bda4  mov     rcx, [rdi+80h]
0x14000bdab  lea     r9, [rsp+38h+arg_8]
0x14000bdb0  call    AllocMem
0x14000bdb5  mov     esi, eax
0x14000bdb7  test    eax, eax
0x14000bdb9  jnz     loc_14000BF43
0x14000bdbf  mov     rcx, [rdi+9C0h]; VirtualAddress
0x14000bdc6  test    rcx, rcx
0x14000bdc9  jz      short loc_14000BDDC
0x14000bdcb  xor     r8d, r8d; MemoryFlags
0x14000bdce  xor     edx, edx; Length
0x14000bdd0  call    cs:__imp_NdisFreeMemory
0x14000bdd7  nop     dword ptr [rax+rax+00h]
0x14000bddc  mov     r8d, [rbx+60h]; Size
0x14000bde0  mov     rdx, [rbx+58h]; Src
0x14000bde4  mov     rbx, [rsp+38h+arg_8]
0x14000bde9  mov     rcx, rbx; void *
0x14000bdec  call    memmove
0x14000bdf1  mov     [rdi+9C0h], rbx
0x14000bdf8  mov     [rdi+8F0h], r14b
0x14000bdff  test    esi, esi
0x14000be01  jz      loc_14000BC69
0x14000be07  jmp     loc_14000BF57
0x14000be0c  mov     [rdi+9BCh], eax
0x14000be12  jmp     loc_14000BD7B
0x14000be17  mov     eax, [rcx+2Ch]
0x14000be1a  test    al, 20h
0x14000be1c  jz      loc_14000BC79
0x14000be22  mov     rcx, [rcx+18h]
0x14000be26  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000be2d  mov     edx, 64h ; 'd'
0x14000be32  mov     r9d, esi
0x14000be35  call    WPP_SF_d
0x14000be3a  jmp     loc_14000BC79
0x14000be3f  mov     rbx, [rbx]
0x14000be42  jmp     loc_14000BC64
0x14000be47  mov     eax, [rcx+2Ch]
0x14000be4a  test    al, 20h
0x14000be4c  jz      loc_14000BC64
0x14000be52  mov     rcx, [rcx+18h]
0x14000be56  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000be5d  mov     edx, 61h ; 'a'
0x14000be62  call    WPP_SF_
0x14000be67  jmp     loc_14000BC64
0x14000be6c  mov     r8d, 5F3h
0x14000be72  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000be79  lea     rcx, aPrestartgenHea_0; "pRestartGen->Header.Type == NDIS_OBJECT"...
0x14000be80  call    TraceAssert
0x14000be85  jmp     loc_14000BCB3
0x14000be8a  mov     r8d, 5F4h
0x14000be90  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000be97  lea     rcx, aPrestartgenHea; "pRestartGen->Header.Size == sizeof(NDIS"...
0x14000be9e  call    TraceAssert
0x14000bea3  jmp     loc_14000BCBE
0x14000bea8  cmp     byte ptr [rax], 88h
0x14000beab  jnz     loc_14000BD20
0x14000beb1  mov     rcx, [rdi+80h]
0x14000beb8  lea     r9, [rsp+38h+arg_0]
0x14000bebd  mov     edx, 14h
0x14000bec2  call    AllocMem
0x14000bec7  mov     esi, eax
0x14000bec9  test    eax, eax
0x14000becb  jz      short loc_14000BF05
0x14000becd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bed4  cmp     rcx, r15
0x14000bed7  jz      short loc_14000BF57
0x14000bed9  mov     edx, [rcx+2Ch]
0x14000bedc  test    r14b, dl
0x14000bedf  jz      short loc_14000BF57
0x14000bee1  mov     edx, 62h ; 'b'
0x14000bee6  mov     r9d, eax
0x14000bee9  jmp     short loc_14000BEF3
0x14000beeb  mov     edx, 63h ; 'c'
0x14000bef0  mov     r9d, esi
0x14000bef3  mov     rcx, [rcx+18h]
0x14000bef7  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000befe  call    WPP_SF_d
0x14000bf03  jmp     short loc_14000BF57
0x14000bf05  mov     rcx, [rdi+998h]; VirtualAddress
0x14000bf0c  test    rcx, rcx
0x14000bf0f  jz      short loc_14000BF22
0x14000bf11  xor     r8d, r8d; MemoryFlags
0x14000bf14  xor     edx, edx; Length
0x14000bf16  call    cs:__imp_NdisFreeMemory
0x14000bf1d  nop     dword ptr [rax+rax+00h]
0x14000bf22  mov     rax, [rbx+38h]
0x14000bf26  mov     rcx, [rsp+38h+arg_0]
0x14000bf2b  movups  xmm0, xmmword ptr [rax]
0x14000bf2e  movups  xmmword ptr [rcx], xmm0
0x14000bf31  mov     eax, [rax+10h]
0x14000bf34  mov     [rcx+10h], eax
0x14000bf37  mov     [rdi+998h], rcx
0x14000bf3e  jmp     loc_14000BD20
0x14000bf43  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf4a  cmp     rcx, r15
0x14000bf4d  jz      short loc_14000BF57
0x14000bf4f  mov     eax, [rcx+2Ch]
0x14000bf52  test    r14b, al
0x14000bf55  jnz     short loc_14000BEEB
0x14000bf57  mov     rcx, [rdi+998h]; VirtualAddress
0x14000bf5e  test    rcx, rcx
0x14000bf61  jz      short loc_14000BF7F
0x14000bf63  xor     r8d, r8d; MemoryFlags
0x14000bf66  xor     edx, edx; Length
0x14000bf68  call    cs:__imp_NdisFreeMemory
0x14000bf6f  nop     dword ptr [rax+rax+00h]
0x14000bf74  mov     qword ptr [rdi+998h], 0
0x14000bf7f  mov     rcx, [rdi+9C0h]; VirtualAddress
0x14000bf86  test    rcx, rcx
0x14000bf89  jz      loc_14000BC69
0x14000bf8f  xor     r8d, r8d; MemoryFlags
0x14000bf92  xor     edx, edx; Length
0x14000bf94  call    cs:__imp_NdisFreeMemory
0x14000bf9b  nop     dword ptr [rax+rax+00h]
0x14000bfa0  mov     qword ptr [rdi+9C0h], 0
0x14000bfab  jmp     loc_14000BC69
```
