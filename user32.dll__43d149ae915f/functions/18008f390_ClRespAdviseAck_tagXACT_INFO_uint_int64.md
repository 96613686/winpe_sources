# ClRespAdviseAck(tagXACT_INFO *,uint,__int64)

- ea: `0x18008f390`
- end: `0x18008f4e1`
- name: `?ClRespAdviseAck@@YAHPEAUtagXACT_INFO@@I_J@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, UINT msg, LPCVOID pMem)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180065e90`
- `0x180068bf8`
- `0x1800702f8`
- `0x1800706c8`
- `0x1800881b0`
- `0x18008f390`
- `0x180090000`
- `0x18009095c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f4bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f4bd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008f491`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008f491`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f3df`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f4af`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f3df`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f4af`

## pseudocode

```c
__int64 __fastcall ClRespAdviseAck(struct tagXACT_INFO *a1, UINT msg, __int64 *pMem)
{
  __int64 v7; // rbp
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rcx
  HLOCAL v11; // rcx

  if ( msg )
  {
    if ( msg != 996 )
      return SpontaneousClientMessage(*((struct tagCL_CONV_INFO **)a1 + 1), msg, (__int64)pMem);
    if ( (unsigned int)IsValidGlobalHandle(pMem) )
    {
      v7 = *pMem;
      v8 = pMem[1];
    }
    else
    {
      LOWORD(v7) = 0;
      LOWORD(v8) = 0;
    }
    GlobalDeleteAtom(v8);
    *((_WORD *)a1 + 25) = 13;
    *((_WORD *)a1 + 23) = v7;
    if ( (v7 & 0x8000u) == 0LL )
    {
      GlobalFree(*((HGLOBAL *)a1 + 7));
    }
    else if ( (unsigned int)AddLink(
                              *((struct tagCONV_INFO **)a1 + 1),
                              *((_WORD *)a1 + 20),
                              *((_WORD *)a1 + 21),
                              (*((_WORD *)a1 + 22) & 0xFFFCu) << 12) )
    {
      v9 = *((_QWORD *)a1 + 1);
      if ( (*(_BYTE *)(v9 + 56) & 4) == 0 )
      {
        v10 = *(_QWORD *)(v9 + 8);
        if ( (*(_DWORD *)(v10 + 24) & 0x20000000) != 0 )
          MonitorLink(
            (struct tagCL_INSTANCE_INFO *)v10,
            1,
            v7 & 0x4000,
            *(_WORD *)(v9 + 32),
            *(_WORD *)(v9 + 34),
            *((_WORD *)a1 + 20),
            *((_WORD *)a1 + 21),
            0,
            *(HCONV *)(v9 + 40),
            *(HCONV *)(v9 + 48));
      }
    }
    else
    {
      *((_WORD *)a1 + 23) = 0;
    }
    if ( !(unsigned int)TransactionComplete(a1, (HDDEDATA)((unsigned __int64)*((unsigned __int16 *)a1 + 23) >> 15)) )
      goto LABEL_16;
  }
  GlobalDeleteAtom(*((_WORD *)a1 + 20));
  UnlinkTransaction(a1);
  LocalFree(v11);
  if ( msg )
LABEL_16:
    FreeDDElParam(msg, (LPARAM)pMem);
  return 1;
}

```

## disassembly

```asm
0x18008f390  push    rbx
0x18008f392  push    rbp
0x18008f393  push    rsi
0x18008f394  push    rdi
0x18008f395  push    r14
0x18008f397  sub     rsp, 50h
0x18008f39b  xor     r14d, r14d
0x18008f39e  mov     rsi, r8
0x18008f3a1  mov     edi, edx
0x18008f3a3  mov     rbx, rcx
0x18008f3a6  test    edx, edx
0x18008f3a8  jz      loc_18008F4AB
0x18008f3ae  cmp     edx, 3E4h
0x18008f3b4  jz      short loc_18008F3C4
0x18008f3b6  mov     rcx, [rcx+8]; struct tagCL_CONV_INFO *
0x18008f3ba  call    ?SpontaneousClientMessage@@YAHPEAUtagCL_CONV_INFO@@I_J@Z; SpontaneousClientMessage(tagCL_CONV_INFO *,uint,__int64)
0x18008f3bf  jmp     loc_18008F4D6
0x18008f3c4  mov     rcx, rsi; pMem
0x18008f3c7  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f3cc  test    eax, eax
0x18008f3ce  jnz     short loc_18008F3D8
0x18008f3d0  mov     rbp, r14
0x18008f3d3  mov     rcx, r14
0x18008f3d6  jmp     short loc_18008F3DF
0x18008f3d8  mov     rbp, [rsi]
0x18008f3db  mov     rcx, [rsi+8]; nAtom
0x18008f3df  call    cs:__imp_GlobalDeleteAtom
0x18008f3e5  mov     word ptr [rbx+32h], 0Dh
0x18008f3eb  mov     [rbx+2Eh], bp
0x18008f3ef  test    bp, bp
0x18008f3f2  jns     loc_18008F48D
0x18008f3f8  movzx   r9d, word ptr [rbx+2Ch]
0x18008f3fd  mov     eax, 0FFFCh
0x18008f402  movzx   r8d, word ptr [rbx+2Ah]; unsigned __int16
0x18008f407  and     r9w, ax
0x18008f40b  movzx   edx, word ptr [rbx+28h]; unsigned __int16
0x18008f40f  mov     rcx, [rbx+8]; struct tagCONV_INFO *
0x18008f413  shl     r9w, 0Ch; unsigned __int16
0x18008f418  call    ?AddLink@@YAHPEAUtagCONV_INFO@@GGG@Z; AddLink(tagCONV_INFO *,ushort,ushort,ushort)
0x18008f41d  test    eax, eax
0x18008f41f  jz      short loc_18008F486
0x18008f421  mov     r9, [rbx+8]
0x18008f425  test    byte ptr [r9+38h], 4
0x18008f42a  jnz     short loc_18008F497
0x18008f42c  mov     rcx, [r9+8]; struct tagCL_INSTANCE_INFO *
0x18008f430  test    dword ptr [rcx+18h], 20000000h
0x18008f437  jz      short loc_18008F497
0x18008f439  mov     rax, [r9+30h]
0x18008f43d  and     ebp, 4000h
0x18008f443  mov     [rsp+78h+var_30], rax; HCONV
0x18008f448  mov     r8d, ebp; int
0x18008f44b  mov     rax, [r9+28h]
0x18008f44f  mov     edx, 1; int
0x18008f454  mov     [rsp+78h+var_38], rax; HCONV
0x18008f459  movzx   eax, word ptr [rbx+2Ah]
0x18008f45d  mov     [rsp+78h+var_40], r14d; int
0x18008f462  mov     [rsp+78h+var_48], ax; unsigned __int16
0x18008f467  movzx   eax, word ptr [rbx+28h]
0x18008f46b  mov     [rsp+78h+var_50], ax; unsigned __int16
0x18008f470  movzx   eax, word ptr [r9+22h]
0x18008f475  movzx   r9d, word ptr [r9+20h]; unsigned __int16
0x18008f47a  mov     [rsp+78h+var_58], ax; unsigned __int16
0x18008f47f  call    ?MonitorLink@@YAXPEAUtagCL_INSTANCE_INFO@@HHGGGGHPEAUHCONV__@@1@Z; MonitorLink(tagCL_INSTANCE_INFO *,int,int,ushort,ushort,ushort,ushort,int,HCONV__ *,HCONV__ *)
0x18008f484  jmp     short loc_18008F497
0x18008f486  mov     [rbx+2Eh], r14w
0x18008f48b  jmp     short loc_18008F497
0x18008f48d  mov     rcx, [rbx+38h]; hMem
0x18008f491  call    cs:__imp_GlobalFree
0x18008f497  movzx   edx, word ptr [rbx+2Eh]
0x18008f49b  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f49e  shr     rdx, 0Fh; HDDEDATA
0x18008f4a2  call    ?TransactionComplete@@YAHPEAUtagXACT_INFO@@PEAUHDDEDATA__@@@Z; TransactionComplete(tagXACT_INFO *,HDDEDATA__ *)
0x18008f4a7  test    eax, eax
0x18008f4a9  jz      short loc_18008F4C7
0x18008f4ab  movzx   ecx, word ptr [rbx+28h]; nAtom
0x18008f4af  call    cs:__imp_GlobalDeleteAtom
0x18008f4b5  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f4b8  call    ?UnlinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; UnlinkTransaction(tagXACT_INFO *)
0x18008f4bd  call    cs:__imp_LocalFree
0x18008f4c3  test    edi, edi
0x18008f4c5  jz      short loc_18008F4D1
0x18008f4c7  mov     rdx, rsi; lParam
0x18008f4ca  mov     ecx, edi; msg
0x18008f4cc  call    FreeDDElParam
0x18008f4d1  mov     eax, 1
0x18008f4d6  add     rsp, 50h
0x18008f4da  pop     r14
0x18008f4dc  pop     rdi
0x18008f4dd  pop     rsi
0x18008f4de  pop     rbp
0x18008f4df  pop     rbx
0x18008f4e0  retn
```
