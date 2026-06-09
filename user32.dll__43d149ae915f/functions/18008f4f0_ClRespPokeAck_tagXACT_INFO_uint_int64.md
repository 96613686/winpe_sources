# ClRespPokeAck(tagXACT_INFO *,uint,__int64)

- ea: `0x18008f4f0`
- end: `0x18008f5f9`
- name: `?ClRespPokeAck@@YAHPEAUtagXACT_INFO@@I_J@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, UINT msg, LPCVOID pMem)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180065e90`
- `0x180068bf8`
- `0x18006ef34`
- `0x1800706c8`
- `0x18008f4f0`
- `0x180090000`
- `0x18009095c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f5d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f5d5`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f54f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f58b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f54f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f58b`

## pseudocode

```c
__int64 __fastcall ClRespPokeAck(struct tagXACT_INFO *a1, UINT msg, _QWORD *pMem)
{
  _QWORD *v3; // rdi
  UINT v4; // esi
  struct tagCL_CONV_INFO *v6; // rcx
  __int64 v8; // rbp
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  _QWORD *v14; // rcx

  v3 = pMem;
  v4 = msg;
  if ( msg )
  {
    if ( msg != 996 )
    {
      v6 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
      return SpontaneousClientMessage(v6, msg, (__int64)pMem);
    }
    if ( (unsigned int)IsValidGlobalHandle(pMem) )
    {
      v8 = *v3;
      v9 = v3[1];
    }
    else
    {
      LOWORD(v8) = 0;
      LOWORD(v9) = 0;
    }
    if ( (_WORD)v9 != *((_WORD *)a1 + 20) )
    {
      v6 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
      pMem = v3;
      msg = 996;
      return SpontaneousClientMessage(v6, msg, (__int64)pMem);
    }
    GlobalDeleteAtom(v9);
    *((_WORD *)a1 + 25) = 8;
    *((_WORD *)a1 + 23) = v8;
    if ( (v8 & 0x8000u) == 0LL )
      FreeDDEData(*((HGLOBAL *)a1 + 7), 0, 1);
    if ( !(unsigned int)TransactionComplete(a1, (HDDEDATA)((unsigned __int64)*((unsigned __int16 *)a1 + 23) >> 15)) )
      goto LABEL_16;
  }
  GlobalDeleteAtom(*((_WORD *)a1 + 20));
  UnlinkTransaction(a1);
  v10 = *((_QWORD *)a1 + 3);
  if ( v10 )
  {
    v11 = iFirstFree;
    v12 = (v10 >> 10) & 0x3FFF;
    v13 = 2 * v12;
    v14 = aHandleEntry;
    iFirstFree = v12;
    *((_QWORD *)aHandleEntry + v13) = 0;
    v14[v13 + 1] = v11;
  }
  LocalFree(a1);
  if ( v4 )
LABEL_16:
    FreeDDElParam(v4, (LPARAM)v3);
  return 1;
}

```

## disassembly

```asm
0x18008f4f0  push    rbx
0x18008f4f2  push    rbp
0x18008f4f3  push    rsi
0x18008f4f4  push    rdi
0x18008f4f5  push    r14
0x18008f4f7  sub     rsp, 20h
0x18008f4fb  xor     r14d, r14d
0x18008f4fe  mov     rdi, r8
0x18008f501  mov     esi, edx
0x18008f503  mov     rbx, rcx
0x18008f506  test    edx, edx
0x18008f508  jz      short loc_18008F587
0x18008f50a  cmp     edx, 3E4h
0x18008f510  jz      short loc_18008F520
0x18008f512  mov     rcx, [rcx+8]; struct tagCL_CONV_INFO *
0x18008f516  call    ?SpontaneousClientMessage@@YAHPEAUtagCL_CONV_INFO@@I_J@Z; SpontaneousClientMessage(tagCL_CONV_INFO *,uint,__int64)
0x18008f51b  jmp     loc_18008F5EE
0x18008f520  mov     rcx, rdi; pMem
0x18008f523  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f528  test    eax, eax
0x18008f52a  jnz     short loc_18008F534
0x18008f52c  mov     rbp, r14
0x18008f52f  mov     rcx, r14
0x18008f532  jmp     short loc_18008F53B
0x18008f534  mov     rbp, [rdi]
0x18008f537  mov     rcx, [rdi+8]; nAtom
0x18008f53b  cmp     cx, [rbx+28h]
0x18008f53f  jz      short loc_18008F54F
0x18008f541  mov     rcx, [rbx+8]
0x18008f545  mov     r8, rdi
0x18008f548  mov     edx, 3E4h
0x18008f54d  jmp     short loc_18008F516
0x18008f54f  call    cs:__imp_GlobalDeleteAtom
0x18008f555  mov     word ptr [rbx+32h], 8
0x18008f55b  mov     [rbx+2Eh], bp
0x18008f55f  test    bp, bp
0x18008f562  js      short loc_18008F573
0x18008f564  mov     rcx, [rbx+38h]; hMem
0x18008f568  xor     edx, edx; int
0x18008f56a  lea     r8d, [rdx+1]; int
0x18008f56e  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x18008f573  movzx   edx, word ptr [rbx+2Eh]
0x18008f577  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f57a  shr     rdx, 0Fh; HDDEDATA
0x18008f57e  call    ?TransactionComplete@@YAHPEAUtagXACT_INFO@@PEAUHDDEDATA__@@@Z; TransactionComplete(tagXACT_INFO *,HDDEDATA__ *)
0x18008f583  test    eax, eax
0x18008f585  jz      short loc_18008F5DF
0x18008f587  movzx   ecx, word ptr [rbx+28h]; nAtom
0x18008f58b  call    cs:__imp_GlobalDeleteAtom
0x18008f591  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f594  call    ?UnlinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; UnlinkTransaction(tagXACT_INFO *)
0x18008f599  mov     rcx, [rbx+18h]
0x18008f59d  test    rcx, rcx
0x18008f5a0  jz      short loc_18008F5D2
0x18008f5a2  movsxd  rax, cs:?iFirstFree@@3HA; int iFirstFree
0x18008f5a9  shr     rcx, 0Ah
0x18008f5ad  and     ecx, 3FFFh
0x18008f5b3  mov     edx, ecx
0x18008f5b5  mov     r8d, ecx
0x18008f5b8  add     rdx, rdx
0x18008f5bb  mov     rcx, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18008f5c2  mov     cs:?iFirstFree@@3HA, r8d; int iFirstFree
0x18008f5c9  mov     [rcx+rdx*8], r14
0x18008f5cd  mov     [rcx+rdx*8+8], rax
0x18008f5d2  mov     rcx, rbx; hMem
0x18008f5d5  call    cs:__imp_LocalFree
0x18008f5db  test    esi, esi
0x18008f5dd  jz      short loc_18008F5E9
0x18008f5df  mov     rdx, rdi; lParam
0x18008f5e2  mov     ecx, esi; msg
0x18008f5e4  call    FreeDDElParam
0x18008f5e9  mov     eax, 1
0x18008f5ee  add     rsp, 20h
0x18008f5f2  pop     r14
0x18008f5f4  pop     rdi
0x18008f5f5  pop     rsi
0x18008f5f6  pop     rbp
0x18008f5f7  pop     rbx
0x18008f5f8  retn
```
