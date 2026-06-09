# RtmCreateEnumerationHandle

- ea: `0x180010090`
- end: `0x1800102c7`
- name: `RtmCreateEnumerationHandle`
- size: `567`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f780`
- `0x18000fa20`
- `0x18000fcb0`

## callees

- `0x180010090`
- `0x18001163c`
- `0x180011778`
- `0x180011800`
- `0x18001f946`
- `0x180020010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800102a8`
- `KERNEL32!GlobalFree` at `0x1800102a8`
- `KERNEL32!SetLastError` at `0x1800100d0`
- `KERNEL32!SetLastError` at `0x1800102b5`
- `KERNEL32!SetLastError` at `0x1800100d0`
- `KERNEL32!SetLastError` at `0x1800102b5`
- `KERNEL32!GlobalAlloc` at `0x180010107`
- `KERNEL32!GlobalAlloc` at `0x180010107`

## pseudocode

```c
_DWORD *__fastcall RtmCreateEnumerationHandle(unsigned int a1, int a2, char *a3)
{
  __int64 v3; // rbp
  DWORD v6; // ecx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  unsigned int v10; // ecx
  __int64 v11; // rdx
  __int64 InterfaceList; // rax
  __int64 **v13; // r8
  __int64 *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  _QWORD *v17; // rdx
  _QWORD *v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx

  v3 = a1;
  if ( a1 )
    goto LABEL_4;
  if ( _InterlockedAdd(&dword_18002BB08, 1u) <= 0 || (a2 & 0xBFFFFFF0) != 0 )
  {
    _InterlockedDecrement(&dword_18002BB08);
LABEL_4:
    v6 = 87;
LABEL_5:
    SetLastError(v6);
    return 0;
  }
  if ( (unsigned int)(LODWORD(qword_18002BB10[33]) + 104) < LODWORD(qword_18002BB10[33]) )
  {
    _InterlockedDecrement(&dword_18002BB08);
    v6 = 534;
    goto LABEL_5;
  }
  v8 = GlobalAlloc(0, (unsigned int)(LODWORD(qword_18002BB10[33]) + 104));
  v9 = v8;
  if ( v8 )
  {
    v8[16] = 1;
    v8[25] = a2;
    if ( (a2 & 7) != 0 )
      memcpy_0(v8 + 26, a3, SLODWORD(qword_18002BB10[33]));
    *((_QWORD *)v9 + 11) = 0;
    *((_QWORD *)v9 + 9) = 0;
    if ( (a2 & 2) != 0 )
    {
      v10 = v9[29];
      v9[17] = 1;
      v11 = qword_18002BB10[31] + 32LL * (v10 % 0x1F);
      *((_QWORD *)v9 + 10) = v11;
      if ( !DoEnterSyncList((__int64)&Tables[48 * v3], v11, 1) )
        goto LABEL_24;
      InterfaceList = FindInterfaceList(*((_QWORD *)v9 + 10), (unsigned int)v9[29], 0);
      *((_QWORD *)v9 + 9) = InterfaceList;
      if ( !InterfaceList )
        goto LABEL_23;
      v13 = *(__int64 ***)(InterfaceList + 8);
      if ( *v13 == (__int64 *)InterfaceList )
      {
        v14 = (__int64 *)&v9[4 * v9[17]];
        *v14 = InterfaceList;
        v14[1] = (__int64)v13;
        *v13 = v14;
        *(_QWORD *)(InterfaceList + 8) = v14;
LABEL_23:
        LeaveSyncList(&Tables[48 * v3], *((_QWORD *)v9 + 10));
        goto LABEL_24;
      }
    }
    else
    {
      v9[17] = 0;
      if ( (a2 & 1) != 0 )
      {
        v15 = qword_18002BB10[30] + 32LL * ((int (__fastcall *)(char *))qword_18002BB10[38])(a3 + 32);
        *((_QWORD *)v9 + 10) = v15;
        if ( !DoEnterSyncList((__int64)&Tables[48 * v3], v15, 1) )
          goto LABEL_24;
        v16 = *((_QWORD *)v9 + 10);
        v17 = (_QWORD *)(v16 + 16);
        if ( (_QWORD *)*v17 == v17 )
          goto LABEL_23;
        *((_QWORD *)v9 + 9) = v17;
        v18 = *(_QWORD **)(v16 + 24);
      }
      else
      {
        v20 = qword_18002BB10[30];
        *((_QWORD *)v9 + 10) = qword_18002BB10[30];
        if ( !DoEnterSyncList((__int64)&Tables[48 * v3], v20, 1) )
        {
LABEL_24:
          if ( *((_QWORD *)v9 + 9) )
          {
            v9[24] = v3 | 0x52544D00;
          }
          else
          {
            GlobalFree(v9);
            v9 = 0;
            SetLastError(0x103u);
          }
          goto LABEL_30;
        }
        v17 = (_QWORD *)(*((_QWORD *)v9 + 10) + 16LL);
        *((_QWORD *)v9 + 9) = v17;
        v18 = (_QWORD *)v17[1];
      }
      if ( (_QWORD *)*v18 == v17 )
      {
        v19 = &v9[4 * v9[17]];
        *v19 = v17;
        v19[1] = v18;
        *v18 = v19;
        v17[1] = v19;
        goto LABEL_23;
      }
    }
    __fastfail(3u);
  }
LABEL_30:
  _InterlockedDecrement(&dword_18002BB08);
  return v9;
}

```

## disassembly

```asm
0x180010090  push    rbx
0x180010092  push    rbp
0x180010093  push    rsi
0x180010094  push    rdi
0x180010095  push    r14
0x180010097  sub     rsp, 20h
0x18001009b  mov     ebp, ecx
0x18001009d  mov     r14, r8
0x1800100a0  mov     esi, edx
0x1800100a2  cmp     ecx, 1
0x1800100a5  jnb     short loc_1800100CB
0x1800100a7  lea     rdi, ds:0[rbp*2]
0x1800100af  add     rdi, rbp
0x1800100b2  lea     rax, Tables
0x1800100b9  shl     rdi, 7
0x1800100bd  add     rdi, rax
0x1800100c0  lock add dword ptr [rdi+8], 1
0x1800100c5  jg      short loc_1800100E3
0x1800100c7  lock dec dword ptr [rdi+8]
0x1800100cb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800100d0  call    cs:__imp_SetLastError
0x1800100d6  xor     eax, eax
0x1800100d8  add     rsp, 20h
0x1800100dc  pop     r14
0x1800100de  pop     rdi
0x1800100df  pop     rsi
0x1800100e0  pop     rbp
0x1800100e1  pop     rbx
0x1800100e2  retn
0x1800100e3  test    esi, 0BFFFFFF0h
0x1800100e9  jnz     short loc_1800100C7
0x1800100eb  mov     eax, [rdi+118h]
0x1800100f1  lea     ecx, [rax+68h]
0x1800100f4  cmp     ecx, eax
0x1800100f6  jnb     short loc_180010103
0x1800100f8  lock dec dword ptr [rdi+8]
0x1800100fc  mov     ecx, 216h
0x180010101  jmp     short loc_1800100D0
0x180010103  mov     edx, ecx; dwBytes
0x180010105  xor     ecx, ecx; uFlags
0x180010107  call    cs:__imp_GlobalAlloc
0x18001010d  mov     rbx, rax
0x180010110  test    rax, rax
0x180010113  jz      loc_1800102BB
0x180010119  mov     dword ptr [rax+40h], 1
0x180010120  mov     [rax+64h], esi
0x180010123  test    sil, 7
0x180010127  jz      short loc_18001013C
0x180010129  movsxd  r8, dword ptr [rdi+118h]; Size
0x180010130  lea     rcx, [rax+68h]; void *
0x180010134  mov     rdx, r14; Src
0x180010137  call    memcpy_0
0x18001013c  mov     qword ptr [rbx+58h], 0
0x180010144  mov     qword ptr [rbx+48h], 0
0x18001014c  test    sil, 2
0x180010150  jz      loc_1800101DF
0x180010156  mov     ecx, [rbx+74h]
0x180010159  mov     eax, 8421085h
0x18001015e  mul     ecx
0x180010160  mov     eax, ecx
0x180010162  mov     dword ptr [rbx+44h], 1
0x180010169  sub     eax, edx
0x18001016b  mov     r8b, 1
0x18001016e  shr     eax, 1
0x180010170  add     eax, edx
0x180010172  shr     eax, 4
0x180010175  imul    eax, 1Fh
0x180010178  sub     ecx, eax
0x18001017a  mov     edx, ecx
0x18001017c  mov     rcx, rdi
0x18001017f  shl     rdx, 5
0x180010183  add     rdx, [rdi+108h]
0x18001018a  mov     [rbx+50h], rdx
0x18001018e  call    DoEnterSyncList
0x180010193  test    al, al
0x180010195  jz      loc_180010260
0x18001019b  mov     edx, [rbx+74h]
0x18001019e  xor     r8d, r8d
0x1800101a1  mov     rcx, [rbx+50h]
0x1800101a5  call    FindInterfaceList
0x1800101aa  mov     [rbx+48h], rax
0x1800101ae  test    rax, rax
0x1800101b1  jz      loc_180010254
0x1800101b7  mov     r8, [rax+8]
0x1800101bb  cmp     [r8], rax
0x1800101be  jnz     loc_18001029E
0x1800101c4  movsxd  rdx, dword ptr [rbx+44h]
0x1800101c8  shl     rdx, 4
0x1800101cc  add     rdx, rbx
0x1800101cf  mov     [rdx], rax
0x1800101d2  mov     [rdx+8], r8
0x1800101d6  mov     [r8], rdx
0x1800101d9  mov     [rax+8], rdx
0x1800101dd  jmp     short loc_180010254
0x1800101df  mov     dword ptr [rbx+44h], 0
0x1800101e6  test    sil, 1
0x1800101ea  jz      loc_180010272
0x1800101f0  mov     rax, [rdi+140h]
0x1800101f7  lea     rcx, [r14+20h]
0x1800101fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010200  movsxd  rdx, eax
0x180010203  mov     r8b, 1
0x180010206  shl     rdx, 5
0x18001020a  mov     rcx, rdi
0x18001020d  add     rdx, [rdi+100h]
0x180010214  mov     [rbx+50h], rdx
0x180010218  call    DoEnterSyncList
0x18001021d  test    al, al
0x18001021f  jz      short loc_180010260
0x180010221  mov     r8, [rbx+50h]
0x180010225  lea     rdx, [r8+10h]
0x180010229  cmp     [rdx], rdx
0x18001022c  jz      short loc_180010254
0x18001022e  mov     [rbx+48h], rdx
0x180010232  mov     r8, [r8+18h]
0x180010236  cmp     [r8], rdx
0x180010239  jnz     short loc_18001029E
0x18001023b  movsxd  rcx, dword ptr [rbx+44h]
0x18001023f  shl     rcx, 4
0x180010243  add     rcx, rbx
0x180010246  mov     [rcx], rdx
0x180010249  mov     [rcx+8], r8
0x18001024d  mov     [r8], rcx
0x180010250  mov     [rdx+8], rcx
0x180010254  mov     rdx, [rbx+50h]
0x180010258  mov     rcx, rdi
0x18001025b  call    LeaveSyncList
0x180010260  cmp     qword ptr [rbx+48h], 0
0x180010265  jz      short loc_1800102A5
0x180010267  or      ebp, 52544D00h
0x18001026d  mov     [rbx+60h], ebp
0x180010270  jmp     short loc_1800102BB
0x180010272  mov     rdx, [rdi+100h]
0x180010279  mov     r8b, 1
0x18001027c  mov     rcx, rdi
0x18001027f  mov     [rbx+50h], rdx
0x180010283  call    DoEnterSyncList
0x180010288  test    al, al
0x18001028a  jz      short loc_180010260
0x18001028c  mov     rdx, [rbx+50h]
0x180010290  add     rdx, 10h
0x180010294  mov     [rbx+48h], rdx
0x180010298  mov     r8, [rdx+8]
0x18001029c  jmp     short loc_180010236
0x18001029e  mov     ecx, 3
0x1800102a3  int     29h; Win8: RtlFailFast(ecx)
0x1800102a5  mov     rcx, rbx; hMem
0x1800102a8  call    cs:__imp_GlobalFree
0x1800102ae  mov     ecx, 103h; dwErrCode
0x1800102b3  xor     ebx, ebx
0x1800102b5  call    cs:__imp_SetLastError
0x1800102bb  lock dec dword ptr [rdi+8]
0x1800102bf  mov     rax, rbx
0x1800102c2  jmp     loc_1800100D8
```
