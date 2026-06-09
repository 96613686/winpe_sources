# FreeEventData(void *)

- ea: `0x180003aa0`
- end: `0x180003bbd`
- name: `?FreeEventData@@YAXPEAX@Z`
- size: `285`
- prototype: `void __fastcall(_QWORD *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030a0`
- `0x180003190`
- `0x180003690`

## callees

- `0x180003aa0`
- `0x180008300`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ae0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ac8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ae0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003af8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0a`

## pseudocode

```c
void __fastcall FreeEventData(_QWORD *lpMem)
{
  __int64 v1; // r9
  void *v3; // r8
  void *v4; // r8
  void *v5; // r8

  if ( !lpMem )
    return;
  v1 = *(unsigned int *)lpMem;
  if ( (_DWORD)v1 == 11 )
  {
LABEL_3:
    v3 = (void *)lpMem[2];
    if ( v3 )
      HeapFree(ghSensHeap, 0, v3);
    v4 = (void *)lpMem[3];
    if ( v4 )
      HeapFree(ghSensHeap, 0, v4);
    v5 = (void *)lpMem[4];
    goto LABEL_8;
  }
  if ( !(_DWORD)v1 )
  {
    v5 = (void *)lpMem[3];
LABEL_8:
    if ( v5 )
LABEL_9:
      HeapFree(ghSensHeap, 0, v5);
LABEL_10:
    HeapFree(ghSensHeap, 0, lpMem);
    return;
  }
  switch ( (int)v1 )
  {
    case 2:
    case 3:
    case 5:
    case 6:
    case 7:
    case 8:
    case 10:
    case 12:
    case 13:
      goto LABEL_3;
    case 14:
    case 15:
    case 16:
    case 17:
    case 18:
    case 19:
    case 20:
    case 21:
    case 22:
    case 23:
    case 24:
      goto LABEL_10;
    case 25:
    case 26:
      v5 = (void *)lpMem[1];
      if ( v5 )
        goto LABEL_9;
      goto LABEL_10;
    default:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, v1);
      }
      break;
  }
}

```

## disassembly

```asm
0x180003aa0  test    rcx, rcx
0x180003aa3  jz      short locret_180003B15
0x180003aa5  push    rbx
0x180003aa6  sub     rsp, 20h
0x180003aaa  mov     r9d, [rcx]
0x180003aad  mov     rbx, rcx
0x180003ab0  cmp     r9d, 0Bh
0x180003ab4  jnz     short loc_180003B16
0x180003ab6  mov     r8, [rbx+10h]; jumptable 0000000180003B7E cases 2,3,5-8,10,12,13
0x180003aba  test    r8, r8
0x180003abd  jz      short loc_180003ACE
0x180003abf  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003ac6  xor     edx, edx; dwFlags
0x180003ac8  call    cs:__imp_HeapFree
0x180003ace  mov     r8, [rbx+18h]; lpMem
0x180003ad2  test    r8, r8
0x180003ad5  jz      short loc_180003AE6
0x180003ad7  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003ade  xor     edx, edx; dwFlags
0x180003ae0  call    cs:__imp_HeapFree
0x180003ae6  mov     r8, [rbx+20h]; lpMem
0x180003aea  test    r8, r8
0x180003aed  jz      short loc_180003AFE; jumptable 0000000180003B7E cases 14-24
0x180003aef  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180003af6  xor     edx, edx; dwFlags
0x180003af8  call    cs:__imp_HeapFree
0x180003afe  mov     rcx, cs:?ghSensHeap@@3PEAXEA; jumptable 0000000180003B7E cases 14-24
0x180003b05  mov     r8, rbx; lpMem
0x180003b08  xor     edx, edx; dwFlags
0x180003b0a  call    cs:__imp_HeapFree
0x180003b10  add     rsp, 20h
0x180003b14  pop     rbx
0x180003b15  retn
0x180003b16  test    r9d, r9d
0x180003b19  jz      short loc_180003B5D
0x180003b1b  lea     eax, [r9-2]; switch 25 cases
0x180003b1f  cmp     eax, 18h
0x180003b22  jbe     short loc_180003B63
0x180003b24  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003B7E default case, cases 4,9,11
0x180003b2b  lea     rax, WPP_GLOBAL_Control
0x180003b32  cmp     rcx, rax
0x180003b35  jz      short loc_180003B10
0x180003b37  test    byte ptr [rcx+1Ch], 1
0x180003b3b  jz      short loc_180003B10
0x180003b3d  cmp     byte ptr [rcx+19h], 2
0x180003b41  jb      short loc_180003B10
0x180003b43  mov     rcx, [rcx+10h]
0x180003b47  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003b4e  mov     edx, 17h
0x180003b53  add     rsp, 20h
0x180003b57  pop     rbx
0x180003b58  jmp     WPP_SF_d
0x180003b5d  mov     r8, [rcx+18h]
0x180003b61  jmp     short loc_180003AEA
0x180003b63  lea     rdx, __ImageBase
0x180003b6a  cdqe
0x180003b6c  movzx   eax, ds:(byte_180003BA4 - 180000000h)[rdx+rax]
0x180003b74  mov     ecx, ds:(jpt_180003B7E - 180000000h)[rdx+rax*4]
0x180003b7b  add     rcx, rdx
0x180003b7e  jmp     rcx; switch jump
0x180003b80  mov     r8, [rbx+8]; jumptable 0000000180003B7E cases 25,26
0x180003b84  test    r8, r8
0x180003b87  jz      loc_180003AFE; jumptable 0000000180003B7E cases 14-24
0x180003b8d  jmp     loc_180003AEF
```
