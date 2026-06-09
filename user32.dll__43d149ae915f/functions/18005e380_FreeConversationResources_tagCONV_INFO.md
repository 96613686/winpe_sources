# FreeConversationResources(tagCONV_INFO *)

- ea: `0x18005e380`
- end: `0x18005e605`
- name: `?FreeConversationResources@@YAXPEAUtagCONV_INFO@@@Z`
- size: `645`
- prototype: `void __fastcall(struct tagCONV_INFO *)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800470a0`
- `0x180047800`
- `0x180047b90`
- `0x18005e2b4`
- `0x1800657d4`
- `0x180073ab0`
- `0x180078364`

## callees

- `0x180020990`
- `0x180046dec`
- `0x1800481f4`
- `0x18005e380`
- `0x18005e60c`
- `0x18006da20`
- `0x1800881b0`
- `0x180091030`
- `0x1800a2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e49d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e58a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e5f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e49d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e58a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e5f2`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e56d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e594`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e59e`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e5ad`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e56d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e594`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e59e`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18005e5ad`

## pseudocode

```c
void __fastcall FreeConversationResources(struct tagCONV_INFO *a1)
{
  __int64 **i; // rax
  unsigned __int64 v3; // rax
  _QWORD *v4; // rcx
  int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // r14
  int v11; // ecx
  HCONV v12; // rbx
  HCONV v13; // rdi
  unsigned __int16 v14; // si
  unsigned __int16 v15; // ax
  HCONV v16; // rbx
  HCONV v17; // rdi
  unsigned __int16 v18; // si
  unsigned __int16 v19; // ax
  void *v21; // rcx
  ATOM v22; // cx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax

  if ( *((_DWORD *)a1 + 27) )
  {
    *((_WORD *)a1 + 28) |= 0x800u;
  }
  else
  {
    for ( i = (__int64 **)*((_QWORD *)a1 + 9); i; i = (__int64 **)*i )
    {
      if ( ((_BYTE)i[6] & 1) != 0 )
      {
        PostMessageW(*((HWND *)a1 + 6), 0x113u, 1u, 0);
        *((_WORD *)a1 + 28) |= 0x800u;
        return;
      }
    }
    if ( *((__int16 *)a1 + 28) >= 0 || (*((_WORD *)a1 + 28) & 0x200) != 0 )
    {
      while ( *((_QWORD *)a1 + 9) )
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)a1 + 9) + 32LL))(*((_QWORD *)a1 + 9), 0, 0);
      while ( 1 )
      {
        v9 = *((_QWORD *)a1 + 11);
        if ( !v9 )
          break;
        DumpDDEMessage((unsigned __int16)~*((_WORD *)a1 + 28) >> 15, *(_DWORD *)(v9 + 16), *(_QWORD *)(v9 + 24));
        v8 = **((_QWORD **)a1 + 11);
        *((_QWORD *)a1 + 11) = v8;
        if ( !v8 )
          *((_QWORD *)a1 + 10) = 0;
        LocalFree((HLOCAL)v9);
      }
      v10 = *((_QWORD *)a1 + 12);
      if ( *((_DWORD *)a1 + 26) )
      {
        do
        {
          v11 = *(_DWORD *)(*((_QWORD *)a1 + 1) + 24LL) & 0x20000000;
          if ( (*((_BYTE *)a1 + 56) & 0x10) != 0 )
          {
            if ( v11 )
            {
              v12 = (HCONV)*((_QWORD *)a1 + 6);
              v13 = (HCONV)*((_QWORD *)a1 + 5);
              v14 = *(_WORD *)(v10 + 10);
              v15 = LocalToGlobalAtom(*(_WORD *)(v10 + 8));
              MonitorLink(
                *((struct tagCL_INSTANCE_INFO **)a1 + 1),
                0,
                *(_WORD *)(v10 + 12) & 4,
                *((_WORD *)a1 + 16),
                *((_WORD *)a1 + 17),
                v15,
                v14,
                0,
                v13,
                v12);
            }
          }
          else if ( v11 )
          {
            v16 = (HCONV)*((_QWORD *)a1 + 5);
            v17 = (HCONV)*((_QWORD *)a1 + 6);
            v18 = *(_WORD *)(v10 + 10);
            v19 = LocalToGlobalAtom(*(_WORD *)(v10 + 8));
            MonitorLink(
              *((struct tagCL_INSTANCE_INFO **)a1 + 1),
              0,
              *(_WORD *)(v10 + 12) & 4,
              *((_WORD *)a1 + 16),
              *((_WORD *)a1 + 17),
              v19,
              v18,
              1,
              v17,
              v16);
          }
          if ( (*((_BYTE *)a1 + 56) & 0x10) == 0 )
            DeleteLinkCount(*((struct tagCL_INSTANCE_INFO **)a1 + 1), *(struct tagLINK_COUNT **)v10);
          DeleteAtom(*(_WORD *)(v10 + 8));
          v10 += 16;
        }
        while ( (*((_DWORD *)a1 + 26))-- != 1 );
      }
      v21 = (void *)*((_QWORD *)a1 + 12);
      if ( v21 )
        LocalFree(v21);
      DeleteAtom(*((_WORD *)a1 + 16));
      DeleteAtom(*((_WORD *)a1 + 17));
      v22 = *((_WORD *)a1 + 29);
      if ( v22 )
        DeleteAtom(v22);
      UnlinkConvFromOthers(a1, 0);
      v23 = aHandleEntry;
      v24 = 2LL * ((*((_DWORD *)a1 + 6) >> 10) & 0x3FFF);
      v25 = iFirstFree;
      iFirstFree = (*((_DWORD *)a1 + 6) >> 10) & 0x3FFF;
      *((_QWORD *)aHandleEntry + v24) = 0;
      v23[v24 + 1] = v25;
      LocalFree(a1);
    }
    else
    {
      v3 = *((unsigned int *)a1 + 6);
      v4 = aHandleEntry;
      v5 = (v3 >> 10) & 0x3FFF;
      v6 = (v3 >> 10) & 0x3FFF;
      v7 = iFirstFree;
      v6 *= 2;
      iFirstFree = v5;
      *((_QWORD *)aHandleEntry + v6) = 0;
      v4[v6 + 1] = v7;
      *((_QWORD *)a1 + 3) = CreateHandle((unsigned __int64)a1, 7u, *((_DWORD *)a1 + 6) & 0x7F);
      UnlinkConvFromOthers(a1, 1);
    }
  }
}

```

## disassembly

```asm
0x18005e380  push    rbx
0x18005e382  push    rbp
0x18005e383  push    rsi
0x18005e384  push    rdi
0x18005e385  push    r14
0x18005e387  push    r15
0x18005e389  sub     rsp, 58h
0x18005e38d  xor     r15d, r15d
0x18005e390  mov     rbp, rcx
0x18005e393  cmp     [rcx+6Ch], r15d
0x18005e397  jbe     short loc_18005E3A7
0x18005e399  mov     eax, 800h
0x18005e39e  or      [rcx+38h], ax
0x18005e3a2  jmp     loc_18005E5F8
0x18005e3a7  mov     rax, [rcx+48h]
0x18005e3ab  test    rax, rax
0x18005e3ae  jz      short loc_18005E3DE
0x18005e3b0  test    byte ptr [rax+30h], 1
0x18005e3b4  jnz     short loc_18005E3BB
0x18005e3b6  mov     rax, [rax]
0x18005e3b9  jmp     short loc_18005E3AB
0x18005e3bb  mov     rcx, [rcx+30h]; hWnd
0x18005e3bf  xor     r9d, r9d; lParam
0x18005e3c2  mov     edx, 113h; Msg
0x18005e3c7  lea     r8d, [r9+1]; wParam
0x18005e3cb  call    PostMessageW
0x18005e3d0  mov     eax, 800h
0x18005e3d5  or      [rbp+38h], ax
0x18005e3d9  jmp     loc_18005E5F8
0x18005e3de  cmp     [rcx+38h], r15w
0x18005e3e3  jge     short loc_18005E44D
0x18005e3e5  mov     eax, 200h
0x18005e3ea  test    [rcx+38h], ax
0x18005e3ee  jnz     short loc_18005E44D
0x18005e3f0  mov     eax, [rcx+18h]
0x18005e3f3  mov     rcx, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18005e3fa  shr     rax, 0Ah
0x18005e3fe  and     eax, 3FFFh
0x18005e403  mov     r8d, eax
0x18005e406  mov     edx, eax
0x18005e408  movsxd  rax, cs:?iFirstFree@@3HA; int iFirstFree
0x18005e40f  add     rdx, rdx
0x18005e412  mov     cs:?iFirstFree@@3HA, r8d; int iFirstFree
0x18005e419  mov     [rcx+rdx*8], r15
0x18005e41d  mov     [rcx+rdx*8+8], rax
0x18005e422  mov     edx, 7; unsigned int
0x18005e427  mov     r8d, [rbp+18h]
0x18005e42b  mov     rcx, rbp; unsigned __int64
0x18005e42e  and     r8d, 7Fh; unsigned int
0x18005e432  call    ?CreateHandle@@YAPEAX_KKK@Z; CreateHandle(unsigned __int64,ulong,ulong)
0x18005e437  mov     edx, 1; int
0x18005e43c  mov     [rbp+18h], rax
0x18005e440  mov     rcx, rbp; struct tagCONV_INFO *
0x18005e443  call    ?UnlinkConvFromOthers@@YAXPEAUtagCONV_INFO@@H@Z; UnlinkConvFromOthers(tagCONV_INFO *,int)
0x18005e448  jmp     loc_18005E5F8
0x18005e44d  cmp     [rcx+48h], r15
0x18005e451  jz      short loc_18005E4A3
0x18005e453  mov     rcx, [rbp+48h]
0x18005e457  xor     r8d, r8d
0x18005e45a  xor     edx, edx
0x18005e45c  mov     rax, [rcx+20h]
0x18005e460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e465  cmp     [rbp+48h], r15
0x18005e469  jnz     short loc_18005E453
0x18005e46b  jmp     short loc_18005E4A3
0x18005e46d  movzx   eax, word ptr [rbp+38h]
0x18005e471  mov     r8, [rbx+18h]; __int64
0x18005e475  not     ax
0x18005e478  mov     edx, [rbx+10h]; unsigned int
0x18005e47b  movzx   ecx, ax
0x18005e47e  shr     ecx, 0Fh; int
0x18005e481  call    ?DumpDDEMessage@@YAXHI_J@Z; DumpDDEMessage(int,uint,__int64)
0x18005e486  mov     rax, [rbp+58h]
0x18005e48a  mov     rdx, [rax]
0x18005e48d  mov     [rbp+58h], rdx
0x18005e491  test    rdx, rdx
0x18005e494  jnz     short loc_18005E49A
0x18005e496  mov     [rbp+50h], r15
0x18005e49a  mov     rcx, rbx; hMem
0x18005e49d  call    cs:__imp_LocalFree
0x18005e4a3  mov     rbx, [rbp+58h]
0x18005e4a7  test    rbx, rbx
0x18005e4aa  jnz     short loc_18005E46D
0x18005e4ac  mov     r14, [rbp+60h]
0x18005e4b0  cmp     [rbp+68h], r15d
0x18005e4b4  jz      loc_18005E581
0x18005e4ba  mov     rax, [rbp+8]
0x18005e4be  mov     ecx, [rax+18h]
0x18005e4c1  and     ecx, 20000000h
0x18005e4c7  test    byte ptr [rbp+38h], 10h
0x18005e4cb  jz      short loc_18005E4FD
0x18005e4cd  test    ecx, ecx
0x18005e4cf  jz      loc_18005E556
0x18005e4d5  movzx   ecx, word ptr [r14+8]; unsigned __int16
0x18005e4da  mov     rbx, [rbp+30h]
0x18005e4de  mov     rdi, [rbp+28h]
0x18005e4e2  movzx   esi, word ptr [r14+0Ah]
0x18005e4e7  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x18005e4ec  mov     [rsp+88h+var_40], rbx
0x18005e4f1  mov     [rsp+88h+var_48], rdi
0x18005e4f6  mov     [rsp+88h+var_50], r15d
0x18005e4fb  jmp     short loc_18005E52A
0x18005e4fd  test    ecx, ecx
0x18005e4ff  jz      short loc_18005E556
0x18005e501  movzx   ecx, word ptr [r14+8]; unsigned __int16
0x18005e506  mov     rbx, [rbp+28h]
0x18005e50a  mov     rdi, [rbp+30h]
0x18005e50e  movzx   esi, word ptr [r14+0Ah]
0x18005e513  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x18005e518  mov     [rsp+88h+var_40], rbx; HCONV
0x18005e51d  mov     [rsp+88h+var_48], rdi; HCONV
0x18005e522  mov     [rsp+88h+var_50], 1; int
0x18005e52a  movzx   r8d, word ptr [r14+0Ch]
0x18005e52f  xor     edx, edx; int
0x18005e531  movzx   r9d, word ptr [rbp+20h]; unsigned __int16
0x18005e536  and     r8d, 4; int
0x18005e53a  mov     rcx, [rbp+8]; struct tagCL_INSTANCE_INFO *
0x18005e53e  mov     [rsp+88h+var_58], si; unsigned __int16
0x18005e543  mov     [rsp+88h+var_60], ax; unsigned __int16
0x18005e548  movzx   eax, word ptr [rbp+22h]
0x18005e54c  mov     [rsp+88h+var_68], ax; unsigned __int16
0x18005e551  call    ?MonitorLink@@YAXPEAUtagCL_INSTANCE_INFO@@HHGGGGHPEAUHCONV__@@1@Z; MonitorLink(tagCL_INSTANCE_INFO *,int,int,ushort,ushort,ushort,ushort,int,HCONV__ *,HCONV__ *)
0x18005e556  test    byte ptr [rbp+38h], 10h
0x18005e55a  jnz     short loc_18005E568
0x18005e55c  mov     rdx, [r14]; struct tagLINK_COUNT *
0x18005e55f  mov     rcx, [rbp+8]; struct tagCL_INSTANCE_INFO *
0x18005e563  call    ?DeleteLinkCount@@YAXPEAUtagCL_INSTANCE_INFO@@PEAUtagLINK_COUNT@@@Z; DeleteLinkCount(tagCL_INSTANCE_INFO *,tagLINK_COUNT *)
0x18005e568  movzx   ecx, word ptr [r14+8]; nAtom
0x18005e56d  call    cs:__imp_DeleteAtom
0x18005e573  add     r14, 10h
0x18005e577  sub     dword ptr [rbp+68h], 1
0x18005e57b  jnz     loc_18005E4BA
0x18005e581  mov     rcx, [rbp+60h]; hMem
0x18005e585  test    rcx, rcx
0x18005e588  jz      short loc_18005E590
0x18005e58a  call    cs:__imp_LocalFree
0x18005e590  movzx   ecx, word ptr [rbp+20h]; nAtom
0x18005e594  call    cs:__imp_DeleteAtom
0x18005e59a  movzx   ecx, word ptr [rbp+22h]; nAtom
0x18005e59e  call    cs:__imp_DeleteAtom
0x18005e5a4  movzx   ecx, word ptr [rbp+3Ah]; nAtom
0x18005e5a8  test    cx, cx
0x18005e5ab  jz      short loc_18005E5B3
0x18005e5ad  call    cs:__imp_DeleteAtom
0x18005e5b3  xor     edx, edx; int
0x18005e5b5  mov     rcx, rbp; struct tagCONV_INFO *
0x18005e5b8  call    ?UnlinkConvFromOthers@@YAXPEAUtagCONV_INFO@@H@Z; UnlinkConvFromOthers(tagCONV_INFO *,int)
0x18005e5bd  mov     eax, [rbp+18h]
0x18005e5c0  mov     rcx, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18005e5c7  shr     rax, 0Ah
0x18005e5cb  and     eax, 3FFFh
0x18005e5d0  mov     edx, eax
0x18005e5d2  add     rdx, rdx
0x18005e5d5  mov     r8d, eax
0x18005e5d8  movsxd  rax, cs:?iFirstFree@@3HA; int iFirstFree
0x18005e5df  mov     cs:?iFirstFree@@3HA, r8d; int iFirstFree
0x18005e5e6  mov     [rcx+rdx*8], r15
0x18005e5ea  mov     [rcx+rdx*8+8], rax
0x18005e5ef  mov     rcx, rbp; hMem
0x18005e5f2  call    cs:__imp_LocalFree
0x18005e5f8  add     rsp, 58h
0x18005e5fc  pop     r15
0x18005e5fe  pop     r14
0x18005e600  pop     rdi
0x18005e601  pop     rsi
0x18005e602  pop     rbp
0x18005e603  pop     rbx
0x18005e604  retn
```
