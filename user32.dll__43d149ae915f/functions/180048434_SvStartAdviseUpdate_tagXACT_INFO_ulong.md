# SvStartAdviseUpdate(tagXACT_INFO *,ulong)

- ea: `0x180048434`
- end: `0x1800485e3`
- name: `?SvStartAdviseUpdate@@YAHPEAUtagXACT_INFO@@K@Z`
- size: `431`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180047aa8`

## callees

- `0x1800198dc`
- `0x180019b20`
- `0x18003ac24`
- `0x180048320`
- `0x180048434`
- `0x180063cc8`
- `0x180068ab0`
- `0x180068b44`
- `0x18007f2e4`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800484b5`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800484b5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800485a7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800485a7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180048501`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180048501`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18004851c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180048544`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18004851c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180048544`

## pseudocode

```c
__int64 __fastcall SvStartAdviseUpdate(struct tagXACT_INFO *a1, unsigned __int16 a2)
{
  unsigned __int16 *v3; // r15
  char *v5; // r14
  HDDEDATA v6; // rbp
  void *v7; // rbx
  HSZ v8; // rbx
  void *v9; // rax
  _WORD *v11; // rax
  unsigned int v12; // r12d

  v3 = (unsigned __int16 *)((char *)a1 + 40);
  v5 = (char *)a1 + 8;
  if ( (*((_WORD *)a1 + 22) & 0x4000) != 0 )
  {
    v6 = 0;
    v7 = 0;
    goto LABEL_13;
  }
  v8 = (HSZ)GlobalToLocalAtom(*v3);
  v6 = DoCallback(
         *(struct tagCL_INSTANCE_INFO **)(*(_QWORD *)v5 + 8LL),
         0x2022u,
         *((_WORD *)a1 + 21),
         *(HCONV *)(*(_QWORD *)v5 + 24LL),
         (HSZ)*(unsigned __int16 *)(*(_QWORD *)v5 + 34LL),
         v8,
         0,
         a2,
         0);
  DeleteAtom((ATOM)v8);
  if ( !v6 )
    return 0;
  v9 = UnpackAndFreeDDEMLDataHandle(v6, 0);
  v7 = v9;
  if ( !v9 )
  {
LABEL_5:
    InternalFreeDataHandle(v6, 0);
    SetLastDDEMLError(*(struct tagCL_INSTANCE_INFO **)(*(_QWORD *)v5 + 8LL), 0x4004u);
    return 0;
  }
  v11 = GlobalLock(v9);
  if ( !v11 )
    return 0;
  if ( v11[1] != *((_WORD *)a1 + 21) )
  {
    GlobalUnlock(v7);
    goto LABEL_5;
  }
  if ( (*v11 & 0x2000) == 0 )
    *((_WORD *)a1 + 22) |= 0x8000u;
  *v11 |= *((_WORD *)a1 + 22) & 0x8000;
  GlobalUnlock(v7);
LABEL_13:
  IncGlobalAtomCount(*v3);
  v12 = PackAndPostMessage(
          *(HWND *)(*(_QWORD *)v5 + 40LL),
          0,
          0x3E5u,
          *(HWND *)(*(_QWORD *)v5 + 48LL),
          0,
          (unsigned __int64)v7,
          *v3);
  if ( v12 )
  {
    if ( v6 )
      InternalFreeDataHandle(v6, 0);
    SetLastDDEMLError(*(struct tagCL_INSTANCE_INFO **)(*(_QWORD *)v5 + 8LL), v12);
    GlobalDeleteAtom(*v3);
    return 0;
  }
  *((_WORD *)a1 + 25) = 15;
  if ( *((__int16 *)a1 + 22) >= 0 )
    return 0;
  *((_QWORD *)a1 + 7) = v7;
  *((_QWORD *)a1 + 4) = SvRespAdviseDataAck;
  LinkTransaction(a1);
  return 1;
}

```

## disassembly

```asm
0x180048434  push    rbx
0x180048436  push    rbp
0x180048437  push    rsi
0x180048438  push    rdi
0x180048439  push    r12
0x18004843b  push    r14
0x18004843d  push    r15
0x18004843f  sub     rsp, 50h
0x180048443  mov     eax, 4000h
0x180048448  mov     esi, edx
0x18004844a  lea     r15, [rcx+28h]
0x18004844e  mov     rdi, rcx
0x180048451  lea     r14, [rcx+8]
0x180048455  test    [rcx+2Ch], ax
0x180048459  jz      short loc_180048466
0x18004845b  xor     esi, esi
0x18004845d  mov     ebp, esi
0x18004845f  mov     ebx, esi
0x180048461  jmp     loc_18004854A
0x180048466  movzx   ecx, word ptr [r15]; unsigned __int16
0x18004846a  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x18004846f  mov     rcx, [r14]
0x180048472  mov     edx, 2022h; unsigned __int16
0x180048477  movzx   r8d, word ptr [rdi+2Ah]; unsigned __int16
0x18004847c  movzx   ebx, ax
0x18004847f  movzx   eax, si
0x180048482  xor     esi, esi
0x180048484  movzx   r9d, word ptr [rcx+22h]
0x180048489  mov     [rsp+88h+var_48], rsi; unsigned __int64
0x18004848e  mov     [rsp+88h+var_50], rax; unsigned __int64
0x180048493  mov     [rsp+88h+hData], rsi; hData
0x180048498  mov     [rsp+88h+var_60], rbx; HSZ
0x18004849d  mov     [rsp+88h+var_68], r9; HSZ
0x1800484a2  mov     r9, [rcx+18h]; HCONV
0x1800484a6  mov     rcx, [rcx+8]; struct tagCL_INSTANCE_INFO *
0x1800484aa  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x1800484af  movzx   ecx, bx; nAtom
0x1800484b2  mov     rbp, rax
0x1800484b5  call    cs:__imp_DeleteAtom
0x1800484bb  test    rbp, rbp
0x1800484be  jz      short loc_1800484ED
0x1800484c0  xor     edx, edx; int
0x1800484c2  mov     rcx, rbp; HDDEDATA
0x1800484c5  call    ?UnpackAndFreeDDEMLDataHandle@@YAPEAXPEAUHDDEDATA__@@H@Z; UnpackAndFreeDDEMLDataHandle(HDDEDATA__ *,int)
0x1800484ca  mov     rbx, rax
0x1800484cd  test    rax, rax
0x1800484d0  jnz     short loc_1800484FE
0x1800484d2  xor     edx, edx; int
0x1800484d4  mov     rcx, rbp; HDDEDATA
0x1800484d7  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x1800484dc  mov     rcx, [r14]
0x1800484df  mov     edx, 4004h; unsigned int
0x1800484e4  mov     rcx, [rcx+8]; struct tagCL_INSTANCE_INFO *
0x1800484e8  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x1800484ed  xor     eax, eax
0x1800484ef  add     rsp, 50h
0x1800484f3  pop     r15
0x1800484f5  pop     r14
0x1800484f7  pop     r12
0x1800484f9  pop     rdi
0x1800484fa  pop     rsi
0x1800484fb  pop     rbp
0x1800484fc  pop     rbx
0x1800484fd  retn
0x1800484fe  mov     rcx, rbx; hMem
0x180048501  call    cs:__imp_GlobalLock
0x180048507  mov     rdx, rax
0x18004850a  test    rax, rax
0x18004850d  jz      short loc_1800484ED
0x18004850f  movzx   ecx, word ptr [rdi+2Ah]
0x180048513  cmp     [rax+2], cx
0x180048517  jz      short loc_180048524
0x180048519  mov     rcx, rbx; hMem
0x18004851c  call    cs:__imp_GlobalUnlock
0x180048522  jmp     short loc_1800484D2
0x180048524  mov     eax, 2000h
0x180048529  mov     ecx, 8000h
0x18004852e  test    [rdx], ax
0x180048531  jnz     short loc_180048537
0x180048533  or      [rdi+2Ch], cx
0x180048537  movzx   eax, word ptr [rdi+2Ch]
0x18004853b  and     ax, cx
0x18004853e  mov     rcx, rbx; hMem
0x180048541  or      [rdx], ax
0x180048544  call    cs:__imp_GlobalUnlock
0x18004854a  movzx   ecx, word ptr [r15]; unsigned __int16
0x18004854e  call    ?IncGlobalAtomCount@@YAGG@Z; IncGlobalAtomCount(ushort)
0x180048553  mov     rcx, [r14]
0x180048556  xor     edx, edx; unsigned int
0x180048558  movzx   eax, word ptr [r15]
0x18004855c  mov     r8d, 3E5h; unsigned int
0x180048562  mov     [rsp+88h+hData], rax; unsigned __int64
0x180048567  mov     [rsp+88h+var_60], rbx; unsigned __int64
0x18004856c  mov     r9, [rcx+30h]; HWND
0x180048570  mov     rcx, [rcx+28h]; hWnd
0x180048574  mov     [rsp+88h+var_68], rsi; __int64
0x180048579  call    ?PackAndPostMessage@@YAKPEAUHWND__@@II0_J_K2@Z; PackAndPostMessage(HWND__ *,uint,uint,HWND__ *,__int64,unsigned __int64,unsigned __int64)
0x18004857e  mov     r12d, eax
0x180048581  test    eax, eax
0x180048583  jz      short loc_1800485B2
0x180048585  test    rbp, rbp
0x180048588  jz      short loc_180048594
0x18004858a  xor     edx, edx; int
0x18004858c  mov     rcx, rbp; HDDEDATA
0x18004858f  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x180048594  mov     rcx, [r14]
0x180048597  mov     edx, r12d; unsigned int
0x18004859a  mov     rcx, [rcx+8]; struct tagCL_INSTANCE_INFO *
0x18004859e  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x1800485a3  movzx   ecx, word ptr [r15]; nAtom
0x1800485a7  call    cs:__imp_GlobalDeleteAtom
0x1800485ad  jmp     loc_1800484ED
0x1800485b2  mov     word ptr [rdi+32h], 0Fh
0x1800485b8  cmp     [rdi+2Ch], si
0x1800485bc  jge     loc_1800484ED
0x1800485c2  lea     rax, ?SvRespAdviseDataAck@@YAHPEAUtagXACT_INFO@@I_J@Z; SvRespAdviseDataAck(tagXACT_INFO *,uint,__int64)
0x1800485c9  mov     [rdi+38h], rbx
0x1800485cd  mov     rcx, rdi; struct tagXACT_INFO *
0x1800485d0  mov     [rdi+20h], rax
0x1800485d4  call    ?LinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; LinkTransaction(tagXACT_INFO *)
0x1800485d9  mov     eax, 1
0x1800485de  jmp     loc_1800484EF
```
