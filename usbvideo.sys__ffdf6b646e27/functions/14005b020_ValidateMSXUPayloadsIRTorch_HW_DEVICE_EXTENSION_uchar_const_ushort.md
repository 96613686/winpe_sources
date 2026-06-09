# ValidateMSXUPayloadsIRTorch(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005b020`
- end: `0x14005b257`
- name: `?ValidateMSXUPayloadsIRTorch@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x1400053fc`
- `0x140019cd4`
- `0x14001b118`
- `0x14003b0c8`
- `0x14005b020`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsIRTorch(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  __int64 v3; // r9
  __int64 v4; // r14
  __int64 v6; // rsi
  __int64 v7; // r15
  __int64 v8; // r9
  __int64 v9; // r9
  unsigned int v10; // r9d
  unsigned int v11; // r8d
  bool v12; // zf
  const unsigned __int8 *v13; // rbx
  __int64 v14; // r9
  unsigned int v15; // ebx
  __int64 v16; // r8
  unsigned int v17; // edi
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // r11d

  v3 = *(unsigned int *)a2;
  v4 = a3;
  v6 = 3 * (unsigned int)a3;
  v7 = 2 * (unsigned int)a3;
  if ( (_DWORD)v3 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v3);
  v8 = *(unsigned int *)&a2[v6];
  if ( (_DWORD)v8 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v8);
  v9 = *(unsigned int *)&a2[v4];
  if ( (v9 & 6) == 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v9);
  }
  v10 = *(_DWORD *)&a2[v4 + 4];
  v11 = *((_DWORD *)a2 + 1);
  v12 = v10 == v11;
  if ( v10 < v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v11, v10);
      v11 = *((_DWORD *)a2 + 1);
      v10 = *(_DWORD *)&a2[v4 + 4];
    }
    v12 = v10 == v11;
  }
  if ( !v12 || (v13 = &a2[v6 + 4], *(_DWORD *)v13) )
  {
    v13 = &a2[v6 + 4];
    if ( *(_DWORD *)v13 )
    {
      if ( (v10 - v11) % *(_DWORD *)v13
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    }
  }
  if ( (a2[v4] & a2[v7] & 6) == 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      *(unsigned int *)&a2[v7]);
  }
  v14 = *(unsigned int *)v13;
  v15 = *((_DWORD *)a2 + 1);
  v16 = *(unsigned int *)&a2[v4 + 4];
  v17 = *(_DWORD *)&a2[v7 + 4];
  if ( (int)BoundsCheck<unsigned long>(v17, v15, v16, v14) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        v17,
        v15,
        v18,
        v19);
    return (unsigned int)-1073741436;
  }
  return v20;
}

```

## disassembly

```asm
0x14005b020  push    rbx
0x14005b022  push    rbp
0x14005b023  push    rsi
0x14005b024  push    rdi
0x14005b025  push    r13
0x14005b027  push    r14
0x14005b029  push    r15
0x14005b02b  sub     rsp, 40h
0x14005b02f  mov     r9d, [rdx]
0x14005b032  lea     r13, WPP_GLOBAL_Control
0x14005b039  movzx   ecx, r8w
0x14005b03d  lea     rbx, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b044  xor     r11d, r11d
0x14005b047  movzx   r14d, r8w
0x14005b04b  mov     rdi, rdx
0x14005b04e  mov     ebp, 0C0000184h
0x14005b053  lea     esi, [rcx+rcx*2]
0x14005b056  lea     r15d, [rcx+rcx]
0x14005b05a  test    r9d, r9d
0x14005b05d  jz      short loc_14005B084
0x14005b05f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b066  cmp     rcx, r13
0x14005b069  jz      short loc_14005B081
0x14005b06b  cmp     byte ptr [rcx+29h], 2
0x14005b06f  jb      short loc_14005B081
0x14005b071  mov     rcx, [rcx+18h]
0x14005b075  lea     edx, [r11+2Bh]
0x14005b079  mov     r8, rbx
0x14005b07c  call    WPP_SF_d
0x14005b081  mov     r11d, ebp
0x14005b084  mov     r9d, [rsi+rdi]
0x14005b088  test    r9d, r9d
0x14005b08b  jz      short loc_14005B0B3
0x14005b08d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b094  cmp     rcx, r13
0x14005b097  jz      short loc_14005B0B0
0x14005b099  cmp     byte ptr [rcx+29h], 2
0x14005b09d  jb      short loc_14005B0B0
0x14005b09f  mov     rcx, [rcx+18h]
0x14005b0a3  mov     edx, 2Ch ; ','
0x14005b0a8  mov     r8, rbx
0x14005b0ab  call    WPP_SF_d
0x14005b0b0  mov     r11d, ebp
0x14005b0b3  mov     r9d, [r14+rdi]
0x14005b0b7  test    r9b, 6
0x14005b0bb  jnz     short loc_14005B0E3
0x14005b0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b0c4  cmp     rcx, r13
0x14005b0c7  jz      short loc_14005B0E0
0x14005b0c9  cmp     byte ptr [rcx+29h], 2
0x14005b0cd  jb      short loc_14005B0E0
0x14005b0cf  mov     rcx, [rcx+18h]
0x14005b0d3  mov     edx, 2Dh ; '-'
0x14005b0d8  mov     r8, rbx
0x14005b0db  call    WPP_SF_d
0x14005b0e0  mov     r11d, ebp
0x14005b0e3  mov     r9d, [r14+rdi+4]
0x14005b0e8  mov     r8d, [rdi+4]
0x14005b0ec  cmp     r9d, r8d
0x14005b0ef  jnb     short loc_14005B12B
0x14005b0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b0f8  cmp     rcx, r13
0x14005b0fb  jz      short loc_14005B125
0x14005b0fd  cmp     byte ptr [rcx+29h], 2
0x14005b101  jb      short loc_14005B125
0x14005b103  mov     rcx, [rcx+18h]
0x14005b107  mov     edx, 2Eh ; '.'
0x14005b10c  mov     [rsp+78h+var_58], r9d
0x14005b111  mov     r9d, r8d
0x14005b114  mov     r8, rbx
0x14005b117  call    WPP_SF_dd
0x14005b11c  mov     r8d, [rdi+4]
0x14005b120  mov     r9d, [r14+rdi+4]
0x14005b125  mov     r11d, ebp
0x14005b128  cmp     r9d, r8d
0x14005b12b  jnz     short loc_14005B139
0x14005b12d  lea     rbx, [rdi+4]
0x14005b131  add     rbx, rsi
0x14005b134  cmp     dword ptr [rbx], 0
0x14005b137  jz      short loc_14005B1B3
0x14005b139  lea     rbx, [rdi+4]
0x14005b13d  add     rbx, rsi
0x14005b140  mov     r10d, [rbx]
0x14005b143  test    r10d, r10d
0x14005b146  jnz     short loc_14005B170
0x14005b148  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b14f  cmp     rcx, r13
0x14005b152  jz      short loc_14005B1B0
0x14005b154  cmp     byte ptr [rcx+29h], 2
0x14005b158  jb      short loc_14005B1B0
0x14005b15a  mov     rcx, [rcx+18h]
0x14005b15e  lea     edx, [r10+2Fh]
0x14005b162  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b169  call    WPP_SF_
0x14005b16e  jmp     short loc_14005B1B0
0x14005b170  xor     edx, edx
0x14005b172  mov     eax, r9d
0x14005b175  sub     eax, r8d
0x14005b178  div     r10d
0x14005b17b  test    edx, edx
0x14005b17d  jz      short loc_14005B1B3
0x14005b17f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b186  cmp     rcx, r13
0x14005b189  jz      short loc_14005B1B0
0x14005b18b  cmp     byte ptr [rcx+29h], 2
0x14005b18f  jb      short loc_14005B1B0
0x14005b191  mov     rcx, [rcx+18h]
0x14005b195  mov     edx, 30h ; '0'
0x14005b19a  mov     [rsp+78h+var_50], r10d
0x14005b19f  mov     [rsp+78h+var_58], r8d
0x14005b1a4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b1ab  call    WPP_SF_ddD
0x14005b1b0  mov     r11d, ebp
0x14005b1b3  mov     r9d, [r15+rdi]
0x14005b1b7  mov     eax, r9d
0x14005b1ba  and     eax, [r14+rdi]
0x14005b1be  test    al, 6
0x14005b1c0  jnz     short loc_14005B1EC
0x14005b1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b1c9  cmp     rcx, r13
0x14005b1cc  jz      short loc_14005B1E9
0x14005b1ce  cmp     byte ptr [rcx+29h], 2
0x14005b1d2  jb      short loc_14005B1E9
0x14005b1d4  mov     rcx, [rcx+18h]
0x14005b1d8  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b1df  mov     edx, 31h ; '1'
0x14005b1e4  call    WPP_SF_d
0x14005b1e9  mov     r11d, ebp
0x14005b1ec  mov     r9d, [rbx]
0x14005b1ef  mov     ebx, [rdi+4]
0x14005b1f2  mov     edx, ebx
0x14005b1f4  mov     r8d, [r14+rdi+4]
0x14005b1f9  mov     edi, [r15+rdi+4]
0x14005b1fe  mov     ecx, edi
0x14005b200  call    ??$BoundsCheck@K@@YAJKKKK@Z; BoundsCheck<ulong>(ulong,ulong,ulong,ulong)
0x14005b205  test    eax, eax
0x14005b207  jns     short loc_14005B244
0x14005b209  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b210  cmp     rcx, r13
0x14005b213  jz      short loc_14005B241
0x14005b215  cmp     byte ptr [rcx+29h], 2
0x14005b219  jb      short loc_14005B241
0x14005b21b  mov     rcx, [rcx+18h]
0x14005b21f  mov     edx, 32h ; '2'
0x14005b224  mov     [rsp+78h+var_48], r9d
0x14005b229  mov     r9d, edi
0x14005b22c  mov     [rsp+78h+var_50], r8d
0x14005b231  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b238  mov     [rsp+78h+var_58], ebx
0x14005b23c  call    WPP_SF_DDDD
0x14005b241  mov     r11d, ebp
0x14005b244  mov     eax, r11d
0x14005b247  add     rsp, 40h
0x14005b24b  pop     r15
0x14005b24d  pop     r14
0x14005b24f  pop     r13
0x14005b251  pop     rdi
0x14005b252  pop     rsi
0x14005b253  pop     rbp
0x14005b254  pop     rbx
0x14005b255  retn
```
