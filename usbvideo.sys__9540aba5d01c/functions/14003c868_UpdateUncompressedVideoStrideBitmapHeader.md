# UpdateUncompressedVideoStrideBitmapHeader

- ea: `0x14003c868`
- end: `0x14003c9fd`
- name: `UpdateUncompressedVideoStrideBitmapHeader`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140012ed0`

## callees

- `0x1400051e4`
- `0x1400053fc`
- `0x140019cd4`
- `0x14003c868`

## pseudocode

```c
__int64 __fastcall UpdateUncompressedVideoStrideBitmapHeader(int *a1, __int64 a2, unsigned int a3, int *a4, int *a5)
{
  int v5; // esi
  int *v6; // r11
  int v7; // ebp
  __int64 v10; // r9
  int *v11; // r8
  int v13; // edx
  int v14; // eax
  unsigned int v15; // r8d
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // ebx
  int v20; // r10d

  v5 = a1[1];
  v6 = (int *)(a2 + 8);
  v7 = *(_DWORD *)(a2 + 4);
  v10 = (unsigned int)-v5;
  v11 = a1 + 2;
  if ( v5 > 0 )
    v10 = (unsigned int)v5;
  if ( (int)v10 < v7 )
    goto LABEL_19;
  v13 = *v6;
  v14 = -*v11;
  if ( *v11 > 0 )
    v14 = *v11;
  if ( v14 == v13 )
  {
    v15 = a1[5];
    if ( v15 < *(_DWORD *)(a2 + 20) || v15 > a3 )
    {
      v19 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids);
    }
    else
    {
      v16 = *(unsigned __int16 *)(a2 + 14);
      v17 = -v13;
      if ( v13 > 0 )
        v17 = *v6;
      v18 = (int)v10 * v16 * v17 / 8;
      if ( v18 <= v15 )
      {
        v19 = 0;
        *a4 = v5 * v16 / 8;
        *a5 = *(_DWORD *)(a2 + 4) * *(unsigned __int16 *)(a2 + 14) / 8;
      }
      else
      {
        v19 = -1073741823;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids, v18, v15);
      }
    }
  }
  else
  {
LABEL_19:
    v19 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v20 = -*v11;
      if ( *v11 > 0 )
        v20 = *v11;
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_412e8667c1693d69367ca3076725fe7f_Traceguids,
        v10,
        v20,
        v7,
        *v6);
    }
  }
  return v19;
}

```

## disassembly

```asm
0x14003c868  push    rbx
0x14003c86a  push    rbp
0x14003c86b  push    rsi
0x14003c86c  push    rdi
0x14003c86d  push    r14
0x14003c86f  sub     rsp, 40h
0x14003c873  mov     esi, [rcx+4]
0x14003c876  lea     r11, [rdx+8]
0x14003c87a  mov     ebp, [rdx+4]
0x14003c87d  mov     r14, r9
0x14003c880  mov     r9d, esi
0x14003c883  mov     ebx, r8d
0x14003c886  neg     r9d
0x14003c889  lea     r8, [rcx+8]
0x14003c88d  mov     r10, rdx
0x14003c890  cmovs   r9d, esi
0x14003c894  cmp     r9d, ebp
0x14003c897  jl      loc_14003C99E
0x14003c89d  mov     edi, [r8]
0x14003c8a0  mov     eax, edi
0x14003c8a2  mov     edx, [r11]
0x14003c8a5  neg     eax
0x14003c8a7  cmovs   eax, edi
0x14003c8aa  cmp     eax, edx
0x14003c8ac  jnz     loc_14003C99E
0x14003c8b2  mov     r8d, [rcx+14h]
0x14003c8b6  cmp     r8d, [r10+14h]
0x14003c8ba  jb      loc_14003C95D
0x14003c8c0  cmp     r8d, ebx
0x14003c8c3  ja      loc_14003C95D
0x14003c8c9  movzx   ecx, word ptr [r10+0Eh]
0x14003c8ce  mov     eax, edx
0x14003c8d0  neg     eax
0x14003c8d2  cmovs   eax, edx
0x14003c8d5  imul    eax, ecx
0x14003c8d8  imul    eax, r9d
0x14003c8dc  mov     r9d, 8
0x14003c8e2  cdq
0x14003c8e3  idiv    r9d
0x14003c8e6  cmp     eax, r8d
0x14003c8e9  jbe     short loc_14003C932
0x14003c8eb  mov     ebx, 0C0000001h
0x14003c8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c8f7  lea     rdx, WPP_GLOBAL_Control
0x14003c8fe  cmp     rcx, rdx
0x14003c901  jz      loc_14003C9EF
0x14003c907  cmp     byte ptr [rcx+29h], 3
0x14003c90b  jb      loc_14003C9EF
0x14003c911  mov     rcx, [rcx+18h]
0x14003c915  lea     edx, [r9+12h]
0x14003c919  mov     [rsp+68h+var_48], r8d
0x14003c91e  mov     r9d, eax
0x14003c921  lea     r8, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids
0x14003c928  call    WPP_SF_dd
0x14003c92d  jmp     loc_14003C9EF
0x14003c932  imul    ecx, esi
0x14003c935  xor     ebx, ebx
0x14003c937  mov     eax, ecx
0x14003c939  mov     rcx, [rsp+68h+arg_20]
0x14003c941  cdq
0x14003c942  idiv    r9d
0x14003c945  mov     [r14], eax
0x14003c948  movzx   eax, word ptr [r10+0Eh]
0x14003c94d  imul    eax, [r10+4]
0x14003c952  cdq
0x14003c953  idiv    r9d
0x14003c956  mov     [rcx], eax
0x14003c958  jmp     loc_14003C9EF
0x14003c95d  mov     ebx, 0C0000001h
0x14003c962  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c969  lea     rdx, WPP_GLOBAL_Control
0x14003c970  cmp     rcx, rdx
0x14003c973  jz      short loc_14003C9EF
0x14003c975  cmp     byte ptr [rcx+29h], 3
0x14003c979  jb      short loc_14003C9EF
0x14003c97b  mov     rcx, [rcx+18h]
0x14003c97f  mov     edx, 19h
0x14003c984  mov     [rsp+68h+var_40], r8d
0x14003c989  mov     r9d, esi
0x14003c98c  lea     r8, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids
0x14003c993  mov     [rsp+68h+var_48], edi
0x14003c997  call    WPP_SF_ddD
0x14003c99c  jmp     short loc_14003C9EF
0x14003c99e  mov     ebx, 0C0000001h
0x14003c9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003c9aa  lea     rdx, WPP_GLOBAL_Control
0x14003c9b1  cmp     rcx, rdx
0x14003c9b4  jz      short loc_14003C9EF
0x14003c9b6  cmp     byte ptr [rcx+29h], 3
0x14003c9ba  jb      short loc_14003C9EF
0x14003c9bc  mov     edx, [r8]
0x14003c9bf  mov     r10d, edx
0x14003c9c2  mov     r8d, [r11]
0x14003c9c5  neg     r10d
0x14003c9c8  mov     rcx, [rcx+18h]
0x14003c9cc  mov     [rsp+68h+var_38], r8d
0x14003c9d1  cmovs   r10d, edx
0x14003c9d5  mov     edx, 18h
0x14003c9da  mov     [rsp+68h+var_40], ebp
0x14003c9de  lea     r8, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids
0x14003c9e5  mov     [rsp+68h+var_48], r10d
0x14003c9ea  call    WPP_SF_DDDD
0x14003c9ef  mov     eax, ebx
0x14003c9f1  add     rsp, 40h
0x14003c9f5  pop     r14
0x14003c9f7  pop     rdi
0x14003c9f8  pop     rsi
0x14003c9f9  pop     rbp
0x14003c9fa  pop     rbx
0x14003c9fb  retn
```
