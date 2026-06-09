# SvSpontUnadvise(tagSVR_CONV_INFO *,__int64)

- ea: `0x180090768`
- end: `0x180090956`
- name: `?SvSpontUnadvise@@YAHPEAUtagSVR_CONV_INFO@@_J@Z`
- size: `494`
- prototype: `__int64 __fastcall(struct tagSVR_CONV_INFO *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180090050`

## callees

- `0x1800198dc`
- `0x180019b20`
- `0x180048320`
- `0x180063cc8`
- `0x1800881b0`
- `0x180090768`
- `0x180091030`
- `0x180096db9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800907ca`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908ae`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908eb`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908f9`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908ae`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908eb`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800908f9`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009093c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18009093c`

## pseudocode

```c
__int64 __fastcall SvSpontUnadvise(struct tagSVR_CONV_INFO *a1, unsigned __int64 a2)
{
  unsigned __int64 v3; // rsi
  __int16 v4; // r15
  unsigned __int16 v5; // ax
  _WORD *v6; // rbx
  HSZ v7; // r14
  void *v8; // rcx
  _WORD *v9; // rcx
  unsigned int v10; // ebp
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int v16; // eax

  v3 = a2 >> 16;
  v4 = a2;
  v5 = GlobalToLocalAtom(WORD1(a2));
  v6 = (_WORD *)*((_QWORD *)a1 + 9);
  v7 = (HSZ)v5;
  while ( v6 && v6[20] == (_WORD)v3 )
  {
    v8 = v6;
    v6 = *(_WORD **)v6;
    LocalFree(v8);
  }
  *((_QWORD *)a1 + 9) = v6;
  if ( v6 )
  {
    while ( 1 )
    {
      v9 = *(_WORD **)v6;
      if ( !*(_QWORD *)v6 )
        break;
      if ( v9[20] == (_WORD)v3 )
      {
        *(_QWORD *)v6 = *(_QWORD *)v9;
        LocalFree(v9);
      }
      else
      {
        v6 = *(_WORD **)v6;
      }
    }
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)a1 + 8) = v6;
  v10 = 0;
  v11 = *((_QWORD *)a1 + 12);
  while ( v10 < *((_DWORD *)a1 + 26) )
  {
    if ( !(_WORD)v7 || *(_WORD *)(v11 + 8) == (_WORD)v7 && (!v4 || v4 == *(_WORD *)(v11 + 10)) )
    {
      v12 = *((_QWORD *)a1 + 1);
      if ( (*(_DWORD *)(v12 + 56) & 0x4000) == 0
        && DoCallback(
             (struct tagCL_INSTANCE_INFO *)v12,
             0x8040u,
             *(_WORD *)(v11 + 10),
             *((HCONV *)a1 + 3),
             (HSZ)*((unsigned __int16 *)a1 + 17),
             v7,
             0,
             0,
             0) == (HDDEDATA)-1LL )
      {
        DeleteAtom((ATOM)v7);
        return 0;
      }
      v13 = *((_QWORD *)a1 + 1);
      if ( (*(_DWORD *)(v13 + 24) & 0x20000000) != 0 )
        MonitorLink(
          (struct tagCL_INSTANCE_INFO *)v13,
          1,
          0,
          *((_WORD *)a1 + 16),
          *((_WORD *)a1 + 17),
          v3,
          *(_WORD *)(v11 + 10),
          1,
          *((HCONV *)a1 + 6),
          *((HCONV *)a1 + 5));
      DeleteAtom(*(_WORD *)(v11 + 8));
      DeleteLinkCount(*((struct tagCL_INSTANCE_INFO **)a1 + 1), *(struct tagLINK_COUNT **)v11);
      if ( (*((_DWORD *)a1 + 26))-- != 1 )
        memmove_0((void *)v11, (const void *)(v11 + 16), 16LL * (*((_DWORD *)a1 + 26) - v10));
    }
    else
    {
      v11 += 16;
      ++v10;
    }
  }
  DeleteAtom((ATOM)v7);
  v16 = PackAndPostMessage(*((HWND *)a1 + 5), 0, 0x3E4u, *((HWND *)a1 + 6), 0, 0x8000u, (unsigned __int16)v3);
  if ( v16 )
  {
    SetLastDDEMLError(*((struct tagCL_INSTANCE_INFO **)a1 + 1), v16);
    GlobalDeleteAtom(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180090768  push    rbx
0x18009076a  push    rbp
0x18009076b  push    rsi
0x18009076c  push    rdi
0x18009076d  push    r12
0x18009076f  push    r14
0x180090771  push    r15
0x180090773  sub     rsp, 50h
0x180090777  mov     rsi, rdx
0x18009077a  mov     rdi, rcx
0x18009077d  shr     rsi, 10h
0x180090781  mov     r15, rdx
0x180090784  movzx   ecx, si; unsigned __int16
0x180090787  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x18009078c  mov     rbx, [rdi+48h]
0x180090790  xor     r12d, r12d
0x180090793  movzx   r14d, ax
0x180090797  jmp     short loc_1800907AB
0x180090799  cmp     [rbx+28h], si
0x18009079d  jnz     short loc_1800907B0
0x18009079f  mov     rcx, rbx; hMem
0x1800907a2  mov     rbx, [rbx]
0x1800907a5  call    cs:__imp_LocalFree
0x1800907ab  test    rbx, rbx
0x1800907ae  jnz     short loc_180090799
0x1800907b0  mov     [rdi+48h], rbx
0x1800907b4  test    rbx, rbx
0x1800907b7  jnz     short loc_1800907D5
0x1800907b9  mov     rbx, r12
0x1800907bc  jmp     short loc_1800907DD
0x1800907be  cmp     [rcx+28h], si
0x1800907c2  jnz     short loc_1800907D2
0x1800907c4  mov     rax, [rcx]
0x1800907c7  mov     [rbx], rax
0x1800907ca  call    cs:__imp_LocalFree
0x1800907d0  jmp     short loc_1800907D5
0x1800907d2  mov     rbx, rcx
0x1800907d5  mov     rcx, [rbx]; hMem
0x1800907d8  test    rcx, rcx
0x1800907db  jnz     short loc_1800907BE
0x1800907dd  mov     [rdi+40h], rbx
0x1800907e1  mov     ebp, r12d
0x1800907e4  mov     rbx, [rdi+60h]
0x1800907e8  cmp     ebp, [rdi+68h]
0x1800907eb  jnb     loc_1800908F5
0x1800907f1  test    r14w, r14w
0x1800907f5  jz      short loc_180090813
0x1800907f7  cmp     [rbx+8], r14w
0x1800907fc  jnz     short loc_18009080B
0x1800907fe  test    r15w, r15w
0x180090802  jz      short loc_180090813
0x180090804  cmp     r15w, [rbx+0Ah]
0x180090809  jz      short loc_180090813
0x18009080b  add     rbx, 10h
0x18009080f  inc     ebp
0x180090811  jmp     short loc_1800907E8
0x180090813  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x180090817  test    dword ptr [rcx+38h], 4000h
0x18009081e  jnz     short loc_18009085B
0x180090820  movzx   r8d, word ptr [rdi+22h]
0x180090825  mov     edx, 8040h; unsigned __int16
0x18009082a  mov     r9, [rdi+18h]; HCONV
0x18009082e  mov     [rsp+88h+var_48], r12; unsigned __int64
0x180090833  mov     [rsp+88h+var_50], r12; unsigned __int64
0x180090838  mov     [rsp+88h+hData], r12; hData
0x18009083d  mov     [rsp+88h+var_60], r14; HSZ
0x180090842  mov     [rsp+88h+var_68], r8; HSZ
0x180090847  movzx   r8d, word ptr [rbx+0Ah]; unsigned __int16
0x18009084c  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x180090851  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180090855  jz      loc_1800908E7
0x18009085b  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x18009085f  test    dword ptr [rcx+18h], 20000000h
0x180090866  jz      short loc_1800908AA
0x180090868  mov     rax, [rdi+28h]
0x18009086c  xor     r8d, r8d; int
0x18009086f  movzx   r9d, word ptr [rdi+20h]; unsigned __int16
0x180090874  mov     [rsp+88h+var_40], rax; HCONV
0x180090879  mov     rax, [rdi+30h]
0x18009087d  mov     [rsp+88h+var_48], rax; HCONV
0x180090882  lea     edx, [r8+1]; int
0x180090886  movzx   eax, word ptr [rbx+0Ah]
0x18009088a  mov     dword ptr [rsp+88h+var_50], 1; int
0x180090892  mov     word ptr [rsp+88h+hData], ax; unsigned __int16
0x180090897  movzx   eax, word ptr [rdi+22h]
0x18009089b  mov     word ptr [rsp+88h+var_60], si; unsigned __int16
0x1800908a0  mov     word ptr [rsp+88h+var_68], ax; unsigned __int16
0x1800908a5  call    ?MonitorLink@@YAXPEAUtagCL_INSTANCE_INFO@@HHGGGGHPEAUHCONV__@@1@Z; MonitorLink(tagCL_INSTANCE_INFO *,int,int,ushort,ushort,ushort,ushort,int,HCONV__ *,HCONV__ *)
0x1800908aa  movzx   ecx, word ptr [rbx+8]; nAtom
0x1800908ae  call    cs:__imp_DeleteAtom
0x1800908b4  mov     rdx, [rbx]; struct tagLINK_COUNT *
0x1800908b7  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x1800908bb  call    ?DeleteLinkCount@@YAXPEAUtagCL_INSTANCE_INFO@@PEAUtagLINK_COUNT@@@Z; DeleteLinkCount(tagCL_INSTANCE_INFO *,tagLINK_COUNT *)
0x1800908c0  add     dword ptr [rdi+68h], 0FFFFFFFFh
0x1800908c4  mov     eax, [rdi+68h]
0x1800908c7  jz      loc_1800907E8
0x1800908cd  sub     eax, ebp
0x1800908cf  lea     rdx, [rbx+10h]; Src
0x1800908d3  mov     r8d, eax
0x1800908d6  mov     rcx, rbx; void *
0x1800908d9  shl     r8, 4; Size
0x1800908dd  call    memmove_0
0x1800908e2  jmp     loc_1800907E8
0x1800908e7  movzx   ecx, r14w; nAtom
0x1800908eb  call    cs:__imp_DeleteAtom
0x1800908f1  xor     eax, eax
0x1800908f3  jmp     short loc_180090947
0x1800908f5  movzx   ecx, r14w; nAtom
0x1800908f9  call    cs:__imp_DeleteAtom
0x1800908ff  mov     r9, [rdi+30h]; HWND
0x180090903  xor     edx, edx; unsigned int
0x180090905  mov     rcx, [rdi+28h]; hWnd
0x180090909  mov     r8d, 3E4h; unsigned int
0x18009090f  movzx   eax, si
0x180090912  mov     [rsp+88h+hData], rax; unsigned __int64
0x180090917  mov     [rsp+88h+var_60], 8000h; unsigned __int64
0x180090920  mov     [rsp+88h+var_68], r12; __int64
0x180090925  call    ?PackAndPostMessage@@YAKPEAUHWND__@@II0_J_K2@Z; PackAndPostMessage(HWND__ *,uint,uint,HWND__ *,__int64,unsigned __int64,unsigned __int64)
0x18009092a  test    eax, eax
0x18009092c  jz      short loc_180090942
0x18009092e  mov     rcx, [rdi+8]; struct tagCL_INSTANCE_INFO *
0x180090932  mov     edx, eax; unsigned int
0x180090934  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180090939  movzx   ecx, si; nAtom
0x18009093c  call    cs:__imp_GlobalDeleteAtom
0x180090942  mov     eax, 1
0x180090947  add     rsp, 50h
0x18009094b  pop     r15
0x18009094d  pop     r14
0x18009094f  pop     r12
0x180090951  pop     rdi
0x180090952  pop     rsi
0x180090953  pop     rbp
0x180090954  pop     rbx
0x180090955  retn
```
