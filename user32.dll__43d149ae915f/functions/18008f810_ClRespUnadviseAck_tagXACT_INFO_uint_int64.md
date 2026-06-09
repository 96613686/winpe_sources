# ClRespUnadviseAck(tagXACT_INFO *,uint,__int64)

- ea: `0x18008f810`
- end: `0x18008f9a7`
- name: `?ClRespUnadviseAck@@YAHPEAUtagXACT_INFO@@I_J@Z`
- size: `407`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, UINT msg, LPCVOID pMem)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180019b20`
- `0x180065e90`
- `0x180068bf8`
- `0x1800706c8`
- `0x18008f810`
- `0x180090000`
- `0x18009095c`
- `0x180096db9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f979`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008f8b5`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008f8fc`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008f8b5`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18008f8fc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f906`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f92f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f906`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f92f`

## pseudocode

```c
__int64 __fastcall ClRespUnadviseAck(struct tagXACT_INFO *a1, UINT msg, _QWORD *pMem)
{
  unsigned int v3; // r15d
  _QWORD *v4; // rdi
  UINT v5; // esi
  struct tagCL_CONV_INFO *v7; // rcx
  __int64 v9; // r13
  __int64 v10; // r14
  unsigned __int16 v11; // ax
  __int64 v12; // rcx
  ATOM v13; // r12
  _WORD *v14; // rbp
  __int16 v15; // cx
  __int64 v16; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // [rsp+70h] [rbp+18h]

  v23 = pMem;
  v3 = 0;
  v4 = pMem;
  v5 = msg;
  if ( msg )
  {
    if ( msg != 996 )
    {
      v7 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
      return SpontaneousClientMessage(v7, msg, (__int64)pMem);
    }
    if ( (unsigned int)IsValidGlobalHandle(pMem) )
    {
      v9 = *v4;
      v10 = v4[1];
    }
    else
    {
      LOWORD(v9) = 0;
      LOWORD(v10) = 0;
    }
    if ( (_WORD)v10 != *((_WORD *)a1 + 20) )
    {
      v7 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
      pMem = v4;
      msg = 996;
      return SpontaneousClientMessage(v7, msg, (__int64)pMem);
    }
    v11 = GlobalToLocalAtom(v10);
    v12 = *((_QWORD *)a1 + 1);
    v13 = v11;
    v14 = *(_WORD **)(v12 + 96);
    if ( *(_DWORD *)(v12 + 104) )
    {
      do
      {
        if ( v14[4] == v13 && ((v15 = *((_WORD *)a1 + 21)) == 0 || v14[5] == v15) )
        {
          DeleteAtom(v13);
          v16 = *((_QWORD *)a1 + 1);
          if ( (*(_DWORD *)(v16 + 104))-- != 1 )
            memmove_0(v14, v14 + 8, 16LL * (*(_DWORD *)(*((_QWORD *)a1 + 1) + 104LL) - v3));
        }
        else
        {
          v14 += 8;
          ++v3;
        }
      }
      while ( v3 < *(_DWORD *)(*((_QWORD *)a1 + 1) + 104LL) );
      v4 = v23;
    }
    DeleteAtom(v13);
    GlobalDeleteAtom(v10);
    *((_WORD *)a1 + 25) = 14;
    *((_WORD *)a1 + 23) = v9;
    if ( !(unsigned int)TransactionComplete(a1, (HDDEDATA)1) )
      goto LABEL_23;
  }
  GlobalDeleteAtom(*((_WORD *)a1 + 20));
  UnlinkTransaction(a1);
  v18 = *((_QWORD *)a1 + 3);
  if ( v18 )
  {
    v19 = iFirstFree;
    v20 = (v18 >> 10) & 0x3FFF;
    v21 = 2 * v20;
    v22 = aHandleEntry;
    iFirstFree = v20;
    *((_QWORD *)aHandleEntry + v21) = 0;
    v22[v21 + 1] = v19;
  }
  LocalFree(a1);
  if ( v5 )
LABEL_23:
    FreeDDElParam(v5, (LPARAM)v4);
  return 1;
}

```

## disassembly

```asm
0x18008f810  mov     [rsp+arg_0], rbx
0x18008f815  mov     [rsp+arg_10], r8
0x18008f81a  push    rbp
0x18008f81b  push    rsi
0x18008f81c  push    rdi
0x18008f81d  push    r12
0x18008f81f  push    r13
0x18008f821  push    r14
0x18008f823  push    r15
0x18008f825  sub     rsp, 20h
0x18008f829  xor     r15d, r15d
0x18008f82c  mov     rdi, r8
0x18008f82f  mov     esi, edx
0x18008f831  mov     rbx, rcx
0x18008f834  test    edx, edx
0x18008f836  jz      loc_18008F92B
0x18008f83c  mov     ebp, 3E4h
0x18008f841  cmp     edx, ebp
0x18008f843  jz      short loc_18008F853
0x18008f845  mov     rcx, [rcx+8]; struct tagCL_CONV_INFO *
0x18008f849  call    ?SpontaneousClientMessage@@YAHPEAUtagCL_CONV_INFO@@I_J@Z; SpontaneousClientMessage(tagCL_CONV_INFO *,uint,__int64)
0x18008f84e  jmp     loc_18008F992
0x18008f853  mov     rcx, rdi; pMem
0x18008f856  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f85b  test    eax, eax
0x18008f85d  jnz     short loc_18008F867
0x18008f85f  mov     r13, r15
0x18008f862  mov     r14, r15
0x18008f865  jmp     short loc_18008F86E
0x18008f867  mov     r13, [rdi]
0x18008f86a  mov     r14, [rdi+8]
0x18008f86e  cmp     r14w, [rbx+28h]
0x18008f873  jz      short loc_18008F880
0x18008f875  mov     rcx, [rbx+8]
0x18008f879  mov     r8, rdi
0x18008f87c  mov     edx, ebp
0x18008f87e  jmp     short loc_18008F849
0x18008f880  movzx   ecx, r14w; unsigned __int16
0x18008f884  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x18008f889  mov     rcx, [rbx+8]
0x18008f88d  movzx   r12d, ax
0x18008f891  mov     rbp, [rcx+60h]
0x18008f895  cmp     [rcx+68h], r15d
0x18008f899  jbe     short loc_18008F8F8
0x18008f89b  cmp     [rbp+8], r12w
0x18008f8a0  jnz     short loc_18008F8E2
0x18008f8a2  movzx   ecx, word ptr [rbx+2Ah]
0x18008f8a6  test    cx, cx
0x18008f8a9  jz      short loc_18008F8B1
0x18008f8ab  cmp     [rbp+0Ah], cx
0x18008f8af  jnz     short loc_18008F8E2
0x18008f8b1  movzx   ecx, r12w; nAtom
0x18008f8b5  call    cs:__imp_DeleteAtom
0x18008f8bb  mov     rax, [rbx+8]
0x18008f8bf  add     dword ptr [rax+68h], 0FFFFFFFFh
0x18008f8c3  jz      short loc_18008F8E9
0x18008f8c5  mov     rax, [rbx+8]
0x18008f8c9  lea     rdx, [rbp+10h]; Src
0x18008f8cd  mov     rcx, rbp; void *
0x18008f8d0  mov     r8d, [rax+68h]
0x18008f8d4  sub     r8d, r15d
0x18008f8d7  shl     r8, 4; Size
0x18008f8db  call    memmove_0
0x18008f8e0  jmp     short loc_18008F8E9
0x18008f8e2  add     rbp, 10h
0x18008f8e6  inc     r15d
0x18008f8e9  mov     rax, [rbx+8]
0x18008f8ed  cmp     r15d, [rax+68h]
0x18008f8f1  jb      short loc_18008F89B
0x18008f8f3  mov     rdi, [rsp+58h+arg_10]
0x18008f8f8  movzx   ecx, r12w; nAtom
0x18008f8fc  call    cs:__imp_DeleteAtom
0x18008f902  movzx   ecx, r14w; nAtom
0x18008f906  call    cs:__imp_GlobalDeleteAtom
0x18008f90c  mov     edx, 1; HDDEDATA
0x18008f911  mov     word ptr [rbx+32h], 0Eh
0x18008f917  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f91a  mov     [rbx+2Eh], r13w
0x18008f91f  call    ?TransactionComplete@@YAHPEAUtagXACT_INFO@@PEAUHDDEDATA__@@@Z; TransactionComplete(tagXACT_INFO *,HDDEDATA__ *)
0x18008f924  xor     r15d, r15d
0x18008f927  test    eax, eax
0x18008f929  jz      short loc_18008F983
0x18008f92b  movzx   ecx, word ptr [rbx+28h]; nAtom
0x18008f92f  call    cs:__imp_GlobalDeleteAtom
0x18008f935  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f938  call    ?UnlinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; UnlinkTransaction(tagXACT_INFO *)
0x18008f93d  mov     rcx, [rbx+18h]
0x18008f941  test    rcx, rcx
0x18008f944  jz      short loc_18008F976
0x18008f946  movsxd  rax, cs:?iFirstFree@@3HA; int iFirstFree
0x18008f94d  shr     rcx, 0Ah
0x18008f951  and     ecx, 3FFFh
0x18008f957  mov     edx, ecx
0x18008f959  mov     r8d, ecx
0x18008f95c  add     rdx, rdx
0x18008f95f  mov     rcx, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18008f966  mov     cs:?iFirstFree@@3HA, r8d; int iFirstFree
0x18008f96d  mov     [rcx+rdx*8], r15
0x18008f971  mov     [rcx+rdx*8+8], rax
0x18008f976  mov     rcx, rbx; hMem
0x18008f979  call    cs:__imp_LocalFree
0x18008f97f  test    esi, esi
0x18008f981  jz      short loc_18008F98D
0x18008f983  mov     rdx, rdi; lParam
0x18008f986  mov     ecx, esi; msg
0x18008f988  call    FreeDDElParam
0x18008f98d  mov     eax, 1
0x18008f992  mov     rbx, [rsp+58h+arg_0]
0x18008f997  add     rsp, 20h
0x18008f99b  pop     r15
0x18008f99d  pop     r14
0x18008f99f  pop     r13
0x18008f9a1  pop     r12
0x18008f9a3  pop     rdi
0x18008f9a4  pop     rsi
0x18008f9a5  pop     rbp
0x18008f9a6  retn
```
