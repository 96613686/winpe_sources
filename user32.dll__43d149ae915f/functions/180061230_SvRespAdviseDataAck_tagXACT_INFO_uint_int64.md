# SvRespAdviseDataAck(tagXACT_INFO *,uint,__int64)

- ea: `0x180061230`
- end: `0x18006133e`
- name: `?SvRespAdviseDataAck@@YAHPEAUtagXACT_INFO@@I_J@Z`
- size: `270`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callees

- `0x180019b20`
- `0x180047aa8`
- `0x180061230`
- `0x180068bf8`
- `0x18006ef34`
- `0x1800706c8`
- `0x180090050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0eee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0eee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061305`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061305`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f3b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006129a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006129a`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800612ed`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x1800612ed`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006127c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800612f7`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18006127c`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800612f7`

## pseudocode

```c
int __fastcall SvRespAdviseDataAck(struct tagXACT_INFO *a1, unsigned int a2, const void *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbp
  __int64 v6; // rsi
  unsigned __int16 v7; // ax
  __int64 v8; // rcx
  ATOM v9; // bp
  unsigned int v10; // edx
  __int64 v11; // rdi
  HLOCAL v12; // rcx
  struct tagSVR_CONV_INFO *v14; // rcx
  __int16 v15; // ax
  HLOCAL v16; // rsi
  int v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = 0;
  v3 = (__int64)a3;
  if ( !a2 )
  {
LABEL_16:
    GlobalDeleteAtom(*((_WORD *)a1 + 20));
    UnlinkTransaction(a1);
    LocalFree(v12);
    return 1;
  }
  if ( a2 == 996 )
  {
    if ( (unsigned int)IsValidGlobalHandle(a3) )
    {
      v5 = *(_QWORD *)v3;
      v6 = *(_QWORD *)(v3 + 8);
    }
    else
    {
      LOWORD(v5) = 0;
      LOWORD(v6) = 0;
    }
    if ( (_WORD)v6 == *((_WORD *)a1 + 20) )
    {
      GlobalDeleteAtom(v6);
      if ( v3 > 0xFFFF && (unsigned int)IsValidGlobalHandle((LPCVOID)v3) )
        GlobalFree((HGLOBAL)v3);
      if ( (v5 & 0x8000) == 0 || !*((_QWORD *)a1 + 7) )
        FreeDDEData(*((HGLOBAL *)a1 + 7), 0, 1);
      v7 = GlobalToLocalAtom(v6);
      v8 = *((_QWORD *)a1 + 1);
      v9 = v7;
      v10 = 0;
      v11 = *(_QWORD *)(v8 + 96);
      while ( v10 < *(_DWORD *)(v8 + 104) )
      {
        if ( *(_WORD *)(v11 + 8) == v9 )
        {
          v15 = *(_WORD *)(v11 + 14);
          if ( (v15 & 0x80u) != 0 )
          {
            *(_WORD *)(v11 + 14) = v15 & 0xFF7F;
            v16 = LocalAlloc(0x40u, 0x48u);
            if ( v16 )
            {
              if ( !(unsigned int)UpdateLinkIfChanged(
                                    (struct tagADVISE_LINK *)v11,
                                    (struct tagXACT_INFO *)v16,
                                    *((struct tagCONV_INFO **)a1 + 1),
                                    (struct tagADVISE_LINK *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL)
                                                            + 16LL
                                                            * (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 1) + 104LL) - 1)),
                                    &v17,
                                    0xFFFFu) )
                LocalFree(v16);
            }
            break;
          }
        }
        ++v10;
        v11 += 16;
      }
      DeleteAtom(v9);
      goto LABEL_16;
    }
    v14 = (struct tagSVR_CONV_INFO *)*((_QWORD *)a1 + 1);
    a3 = (const void *)v3;
    a2 = 996;
  }
  else
  {
    v14 = (struct tagSVR_CONV_INFO *)*((_QWORD *)a1 + 1);
  }
  return SpontaneousServerMessage(v14, a2, (__int64)a3);
}

```

## disassembly

```asm
0x180061230  push    rbx
0x180061232  push    rbp
0x180061233  push    rsi
0x180061234  push    rdi
0x180061235  sub     rsp, 38h
0x180061239  mov     [rsp+58h+arg_8], 0
0x180061241  mov     rdi, r8
0x180061244  mov     rbx, rcx
0x180061247  test    edx, edx
0x180061249  jz      loc_1800612F3
0x18006124f  cmp     edx, 3E4h
0x180061255  jnz     loc_180061319
0x18006125b  mov     rcx, r8; pMem
0x18006125e  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x180061263  test    eax, eax
0x180061265  jnz     loc_1800A0EC2
0x18006126b  xor     ebp, ebp
0x18006126d  xor     esi, esi
0x18006126f  cmp     si, [rbx+28h]
0x180061273  jnz     loc_18006131F
0x180061279  movzx   ecx, si; nAtom
0x18006127c  call    cs:__imp_GlobalDeleteAtom
0x180061282  cmp     rdi, 0FFFFh
0x180061289  jle     short loc_1800612A0
0x18006128b  mov     rcx, rdi; pMem
0x18006128e  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x180061293  test    eax, eax
0x180061295  jz      short loc_1800612A0
0x180061297  mov     rcx, rdi; hMem
0x18006129a  call    cs:__imp_GlobalFree
0x1800612a0  bt      rbp, 0Fh
0x1800612a5  jb      loc_180061332
0x1800612ab  mov     rcx, [rbx+38h]; hMem
0x1800612af  xor     edx, edx; int
0x1800612b1  lea     r8d, [rdx+1]; int
0x1800612b5  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x1800612ba  movzx   ecx, si; unsigned __int16
0x1800612bd  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x1800612c2  mov     rcx, [rbx+8]
0x1800612c6  movzx   ebp, ax
0x1800612c9  xor     edx, edx
0x1800612cb  mov     rdi, [rcx+60h]
0x1800612cf  mov     r8d, [rcx+68h]
0x1800612d3  cmp     edx, r8d
0x1800612d6  jnb     short loc_1800612EA
0x1800612d8  cmp     [rdi+8], bp
0x1800612dc  jz      loc_1800A0ECE
0x1800612e2  inc     edx
0x1800612e4  add     rdi, 10h
0x1800612e8  jmp     short loc_1800612D3
0x1800612ea  movzx   ecx, bp; nAtom
0x1800612ed  call    cs:__imp_DeleteAtom
0x1800612f3  movzx   ecx, word ptr [rbx+28h]; nAtom
0x1800612f7  call    cs:__imp_GlobalDeleteAtom
0x1800612fd  mov     rcx, rbx; struct tagXACT_INFO *
0x180061300  call    ?UnlinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; UnlinkTransaction(tagXACT_INFO *)
0x180061305  call    cs:__imp_LocalFree
0x18006130b  mov     eax, 1
0x180061310  add     rsp, 38h
0x180061314  pop     rdi
0x180061315  pop     rsi
0x180061316  pop     rbp
0x180061317  pop     rbx
0x180061318  retn
0x180061319  mov     rcx, [rcx+8]
0x18006131d  jmp     short loc_18006132B
0x18006131f  mov     rcx, [rbx+8]; struct tagSVR_CONV_INFO *
0x180061323  mov     r8, rdi; __int64
0x180061326  mov     edx, 3E4h; unsigned int
0x18006132b  call    ?SpontaneousServerMessage@@YAHPEAUtagSVR_CONV_INFO@@I_J@Z; SpontaneousServerMessage(tagSVR_CONV_INFO *,uint,__int64)
0x180061330  jmp     short loc_180061310
0x180061332  cmp     qword ptr [rbx+38h], 0
0x180061337  jnz     short loc_1800612BA
0x180061339  jmp     loc_1800612AB
0x1800a0ec2  mov     rbp, [rdi]
0x1800a0ec5  mov     rsi, [rdi+8]
0x1800a0ec9  jmp     loc_18006126F
0x1800a0ece  movzx   eax, word ptr [rdi+0Eh]
0x1800a0ed2  test    al, al
0x1800a0ed4  jns     loc_1800612E2
0x1800a0eda  mov     ecx, 0FF7Fh
0x1800a0edf  mov     edx, 48h ; 'H'; uBytes
0x1800a0ee4  and     ax, cx
0x1800a0ee7  mov     [rdi+0Eh], ax
0x1800a0eeb  lea     ecx, [rdx-8]; uFlags
0x1800a0eee  call    cs:__imp_LocalAlloc
0x1800a0ef4  mov     rsi, rax
0x1800a0ef7  test    rax, rax
0x1800a0efa  jz      loc_1800612EA
0x1800a0f00  mov     r8, [rbx+8]; struct tagCONV_INFO *
0x1800a0f04  lea     rax, [rsp+58h+arg_8]
0x1800a0f09  mov     [rsp+58h+var_30], 0FFFFh; unsigned int
0x1800a0f11  mov     rdx, rsi; struct tagXACT_INFO *
0x1800a0f14  mov     rcx, rdi; struct tagADVISE_LINK *
0x1800a0f17  mov     [rsp+58h+var_38], rax; int *
0x1800a0f1c  mov     r9d, [r8+68h]
0x1800a0f20  dec     r9d
0x1800a0f23  shl     r9, 4
0x1800a0f27  add     r9, [r8+60h]; struct tagADVISE_LINK *
0x1800a0f2b  call    ?UpdateLinkIfChanged@@YAHPEAUtagADVISE_LINK@@PEAUtagXACT_INFO@@PEAUtagCONV_INFO@@0PEAHK@Z; UpdateLinkIfChanged(tagADVISE_LINK *,tagXACT_INFO *,tagCONV_INFO *,tagADVISE_LINK *,int *,ulong)
0x1800a0f30  test    eax, eax
0x1800a0f32  jnz     loc_1800612EA
0x1800a0f38  mov     rcx, rsi; hMem
0x1800a0f3b  call    cs:__imp_LocalFree
0x1800a0f41  nop
0x1800a0f42  jmp     loc_1800612EA
```
