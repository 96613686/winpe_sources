# ClSpontAdviseData(tagCL_CONV_INFO *,__int64)

- ea: `0x18008f9b0`
- end: `0x18008fbf4`
- name: `?ClSpontAdviseData@@YAHPEAUtagCL_CONV_INFO@@_J@Z`
- size: `580`
- prototype: `int(struct tagCL_CONV_INFO *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18008f600`
- `0x180090000`

## callees

- `0x1800198dc`
- `0x180019b20`
- `0x180048320`
- `0x180063cc8`
- `0x180068ab0`
- `0x180068bf8`
- `0x180068c40`
- `0x18006ef34`
- `0x18008f9b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fbd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008fbd1`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008fae4`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008fba5`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008fae4`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008fba5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008fbb3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008fbb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008fa0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008fa0f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008fa3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008fa3a`

## pseudocode

```c
__int64 __fastcall ClSpontAdviseData(struct tagCL_CONV_INFO *a1, __int64 a2)
{
  void *v4; // rbp
  unsigned __int64 v5; // r14
  unsigned int v6; // r12d
  HDDEDATA v7; // rsi
  HSZ v8; // r15
  __int16 *v9; // rax
  __int16 v10; // r13
  HDDEDATA hData; // r12
  unsigned int v12; // eax
  _WORD *v13; // rbp
  unsigned __int16 v15; // [rsp+A0h] [rbp+18h]
  __int16 v16; // [rsp+A8h] [rbp+20h]

  if ( (unsigned int)IsValidGlobalHandle((LPCVOID)a2) )
  {
    v4 = *(void **)a2;
    v5 = *(_QWORD *)(a2 + 8);
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  v16 = 0;
  v6 = 0;
  v7 = 0;
  v8 = (HSZ)GlobalToLocalAtom(v5);
  if ( v4 )
  {
    v9 = (__int16 *)GlobalLock(v4);
    if ( !v9 )
      goto LABEL_12;
    v10 = *v9;
    v15 = v9[1];
    v16 = *v9;
    GlobalUnlock(v4);
    hData = InternalCreateDataHandle(
              *((struct tagCL_INSTANCE_INFO **)a1 + 1),
              (unsigned __int8 *)v4,
              0xFFFFFFFF,
              0,
              0xC000u,
              0,
              0);
    if ( hData )
    {
      v7 = DoCallback(
             *((struct tagCL_INSTANCE_INFO **)a1 + 1),
             0x4010u,
             v15,
             *((HCONV *)a1 + 3),
             (HSZ)*((unsigned __int16 *)a1 + 17),
             v8,
             hData,
             0,
             0);
      if ( v7 != (HDDEDATA)-1LL )
      {
        UnpackAndFreeDDEMLDataHandle(hData, 0);
        if ( ((unsigned __int16)v7 & 0x8000) != 0 || v10 >= 0 )
          FreeDDEData(v4, 0, 1);
      }
    }
  }
  else
  {
    v13 = (_WORD *)*((_QWORD *)a1 + 12);
    while ( v6 < *((_DWORD *)a1 + 26) )
    {
      if ( v13[4] == (_WORD)v8 && (v13[6] & 0x4000) != 0 )
      {
        v7 = DoCallback(
               *((struct tagCL_INSTANCE_INFO **)a1 + 1),
               0x4010u,
               v13[5],
               *((HCONV *)a1 + 3),
               (HSZ)*((unsigned __int16 *)a1 + 17),
               v8,
               0,
               0,
               0);
        if ( v7 == (HDDEDATA)-1LL )
        {
          DeleteAtom((ATOM)v8);
          return 0;
        }
      }
      ++v6;
      v13 += 8;
    }
  }
  LOWORD(v6) = v16;
LABEL_12:
  DeleteAtom((ATOM)v8);
  if ( v7 == (HDDEDATA)-1LL )
    return 0;
  if ( (v6 & 0x8000u) == 0 )
  {
    GlobalDeleteAtom(v5);
    if ( a2 > 0xFFFF && (unsigned int)IsValidGlobalHandle((LPCVOID)a2) )
      GlobalFree((HGLOBAL)a2);
  }
  else
  {
    v12 = PackAndPostMessage(
            *((HWND *)a1 + 5),
            0x3E5u,
            0x3E4u,
            *((HWND *)a1 + 6),
            a2,
            (unsigned __int16)v7 & 0xC0FF,
            v5);
    if ( v12 )
      SetLastDDEMLError(*((struct tagCL_INSTANCE_INFO **)a1 + 1), v12);
  }
  return 1;
}

```

## disassembly

```asm
0x18008f9b0  mov     [rsp+arg_0], rbx
0x18008f9b5  push    rbp
0x18008f9b6  push    rsi
0x18008f9b7  push    rdi
0x18008f9b8  push    r12
0x18008f9ba  push    r13
0x18008f9bc  push    r14
0x18008f9be  push    r15
0x18008f9c0  sub     rsp, 50h
0x18008f9c4  mov     rdi, rcx
0x18008f9c7  mov     rbx, rdx
0x18008f9ca  mov     rcx, rdx; pMem
0x18008f9cd  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f9d2  xor     r13d, r13d
0x18008f9d5  test    eax, eax
0x18008f9d7  jnz     short loc_18008F9E1
0x18008f9d9  mov     ebp, r13d
0x18008f9dc  mov     r14d, r13d
0x18008f9df  jmp     short loc_18008F9E8
0x18008f9e1  mov     rbp, [rbx]
0x18008f9e4  mov     r14, [rbx+8]
0x18008f9e8  movzx   ecx, r14w; unsigned __int16
0x18008f9ec  mov     [rsp+88h+arg_18], r13d
0x18008f9f4  mov     r12d, r13d
0x18008f9f7  mov     rsi, r13
0x18008f9fa  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x18008f9ff  movzx   r15d, ax
0x18008fa03  test    rbp, rbp
0x18008fa06  jz      loc_18008FB41
0x18008fa0c  mov     rcx, rbp; hMem
0x18008fa0f  call    cs:__imp_GlobalLock
0x18008fa15  test    rax, rax
0x18008fa18  jz      loc_18008FAE0
0x18008fa1e  movzx   ecx, word ptr [rax+2]
0x18008fa22  movzx   r13d, word ptr [rax]
0x18008fa26  mov     [rsp+88h+arg_10], cx
0x18008fa2e  mov     rcx, rbp; hMem
0x18008fa31  mov     word ptr [rsp+88h+arg_18], r13w
0x18008fa3a  call    cs:__imp_GlobalUnlock
0x18008fa40  xor     ecx, ecx
0x18008fa42  xor     r9d, r9d; unsigned int
0x18008fa45  mov     word ptr [rsp+88h+hData], cx; unsigned __int16
0x18008fa4a  or      r8d, 0FFFFFFFFh; unsigned int
0x18008fa4e  mov     word ptr [rsp+88h+var_60], cx; unsigned __int16
0x18008fa53  mov     rdx, rbp; unsigned __int8 *
0x18008fa56  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18008fa5a  mov     dword ptr [rsp+88h+var_68], 0C000h; unsigned int
0x18008fa62  call    ?InternalCreateDataHandle@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@PEAEKKKGG@Z; InternalCreateDataHandle(tagCL_INSTANCE_INFO *,uchar *,ulong,ulong,ulong,ushort,ushort)
0x18008fa67  mov     r12, rax
0x18008fa6a  xor     eax, eax
0x18008fa6c  test    r12, r12
0x18008fa6f  jz      short loc_18008FAD8
0x18008fa71  movzx   r9d, word ptr [rdi+22h]
0x18008fa76  mov     edx, 4010h; unsigned __int16
0x18008fa7b  movzx   r8d, [rsp+88h+arg_10]; unsigned __int16
0x18008fa84  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18008fa88  mov     [rsp+88h+var_48], rax; unsigned __int64
0x18008fa8d  mov     [rsp+88h+var_50], rax; unsigned __int64
0x18008fa92  mov     [rsp+88h+hData], r12; hData
0x18008fa97  mov     [rsp+88h+var_60], r15; HSZ
0x18008fa9c  mov     [rsp+88h+var_68], r9; HSZ
0x18008faa1  mov     r9, [rdi+18h]; HCONV
0x18008faa5  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x18008faaa  mov     rsi, rax
0x18008faad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008fab1  jz      short loc_18008FAD8
0x18008fab3  xor     edx, edx; int
0x18008fab5  mov     rcx, r12; HDDEDATA
0x18008fab8  call    ?UnpackAndFreeDDEMLDataHandle@@YAPEAXPEAUHDDEDATA__@@H@Z; UnpackAndFreeDDEMLDataHandle(HDDEDATA__ *,int)
0x18008fabd  bt      rsi, 0Fh
0x18008fac2  jb      short loc_18008FACA
0x18008fac4  test    r13w, r13w
0x18008fac8  js      short loc_18008FAD8
0x18008faca  xor     edx, edx; int
0x18008facc  mov     rcx, rbp; hMem
0x18008facf  lea     r8d, [rdx+1]; int
0x18008fad3  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x18008fad8  mov     r12d, [rsp+88h+arg_18]
0x18008fae0  movzx   ecx, r15w; nAtom
0x18008fae4  call    cs:__imp_DeleteAtom
0x18008faea  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18008faee  jz      loc_18008FBAB
0x18008faf4  test    r12w, r12w
0x18008faf8  jns     loc_18008FBAF
0x18008fafe  mov     r9, [rdi+30h]; HWND
0x18008fb02  mov     edx, 3E5h; unsigned int
0x18008fb07  mov     rcx, [rdi+28h]; hWnd
0x18008fb0b  and     esi, 0C0FFh
0x18008fb11  mov     [rsp+88h+hData], r14; unsigned __int64
0x18008fb16  mov     [rsp+88h+var_60], rsi; unsigned __int64
0x18008fb1b  lea     r8d, [rdx-1]; unsigned int
0x18008fb1f  mov     [rsp+88h+var_68], rbx; __int64
0x18008fb24  call    ?PackAndPostMessage@@YAKPEAUHWND__@@II0_J_K2@Z; PackAndPostMessage(HWND__ *,uint,uint,HWND__ *,__int64,unsigned __int64,unsigned __int64)
0x18008fb29  test    eax, eax
0x18008fb2b  jz      loc_18008FBD7
0x18008fb31  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18008fb35  mov     edx, eax; unsigned int
0x18008fb37  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18008fb3c  jmp     loc_18008FBD7
0x18008fb41  mov     rbp, [rdi+60h]
0x18008fb45  cmp     r12d, [rdi+68h]
0x18008fb49  jnb     short loc_18008FAD8
0x18008fb4b  cmp     [rbp+8], r15w
0x18008fb50  jnz     short loc_18008FB98
0x18008fb52  mov     eax, 4000h
0x18008fb57  test    [rbp+0Ch], ax
0x18008fb5b  jz      short loc_18008FB98
0x18008fb5d  movzx   ecx, word ptr [rdi+22h]
0x18008fb61  lea     edx, [rax+10h]; unsigned __int16
0x18008fb64  mov     r9, [rdi+18h]; HCONV
0x18008fb68  movzx   r8d, word ptr [rbp+0Ah]; unsigned __int16
0x18008fb6d  mov     [rsp+88h+var_48], r13; unsigned __int64
0x18008fb72  mov     [rsp+88h+var_50], r13; unsigned __int64
0x18008fb77  mov     [rsp+88h+hData], r13; hData
0x18008fb7c  mov     [rsp+88h+var_60], r15; HSZ
0x18008fb81  mov     [rsp+88h+var_68], rcx; HSZ
0x18008fb86  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18008fb8a  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x18008fb8f  mov     rsi, rax
0x18008fb92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008fb96  jz      short loc_18008FBA1
0x18008fb98  inc     r12d
0x18008fb9b  add     rbp, 10h
0x18008fb9f  jmp     short loc_18008FB45
0x18008fba1  movzx   ecx, r15w; nAtom
0x18008fba5  call    cs:__imp_DeleteAtom
0x18008fbab  xor     eax, eax
0x18008fbad  jmp     short loc_18008FBDC
0x18008fbaf  movzx   ecx, r14w; nAtom
0x18008fbb3  call    cs:__imp_GlobalDeleteAtom
0x18008fbb9  cmp     rbx, 0FFFFh
0x18008fbc0  jle     short loc_18008FBD7
0x18008fbc2  mov     rcx, rbx; pMem
0x18008fbc5  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008fbca  test    eax, eax
0x18008fbcc  jz      short loc_18008FBD7
0x18008fbce  mov     rcx, rbx; hMem
0x18008fbd1  call    cs:__imp_GlobalFree
0x18008fbd7  mov     eax, 1
0x18008fbdc  mov     rbx, [rsp+88h+arg_0]
0x18008fbe4  add     rsp, 50h
0x18008fbe8  pop     r15
0x18008fbea  pop     r14
0x18008fbec  pop     r13
0x18008fbee  pop     r12
0x18008fbf0  pop     rdi
0x18008fbf1  pop     rsi
0x18008fbf2  pop     rbp
0x18008fbf3  retn
```
