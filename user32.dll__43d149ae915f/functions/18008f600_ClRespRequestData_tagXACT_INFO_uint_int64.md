# ClRespRequestData(tagXACT_INFO *,uint,__int64)

- ea: `0x18008f600`
- end: `0x18008f7fe`
- name: `?ClRespRequestData@@YAHPEAUtagXACT_INFO@@I_J@Z`
- size: `510`
- prototype: `__int64 __fastcall(struct tagXACT_INFO *, UINT msg, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180048320`
- `0x180063cc8`
- `0x180065e90`
- `0x180068bf8`
- `0x18006ef34`
- `0x1800706c8`
- `0x18008f600`
- `0x18008f9b0`
- `0x18008ffa8`
- `0x180090000`
- `0x18009095c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f786`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f724`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f764`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f7f3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f724`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f764`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18008f7f3`

## pseudocode

```c
__int64 __fastcall ClRespRequestData(struct tagXACT_INFO *a1, UINT msg, _QWORD *a3)
{
  _QWORD *v3; // rdi
  UINT v4; // r14d
  struct tagCL_CONV_INFO *v6; // rcx
  HGLOBAL *v7; // rsi
  unsigned __int64 v8; // rbp
  unsigned __int16 v10; // r12
  unsigned __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  void *v14; // rcx
  HLOCAL v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int16 v18; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 v19; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  v19 = 0;
  v4 = msg;
  v18 = 0;
  switch ( msg )
  {
    case 0u:
      goto LABEL_29;
    case 0x3E4u:
      if ( (unsigned int)IsValidGlobalHandle(a3) )
      {
        v16 = *v3;
        v17 = v3[1];
      }
      else
      {
        LOWORD(v16) = 0;
        LOWORD(v17) = 0;
      }
      if ( (_WORD)v17 != *((_WORD *)a1 + 20) )
      {
        v6 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
        a3 = v3;
        msg = 996;
        return SpontaneousClientMessage(v6, msg, (__int64)a3);
      }
      *((_WORD *)a1 + 25) = 6;
      *((_WORD *)a1 + 23) = v16;
      GlobalDeleteAtom(v17);
      goto LABEL_27;
    case 0x3E5u:
      v7 = (HGLOBAL *)((char *)a1 + 64);
      if ( (unsigned int)IsValidGlobalHandle(a3) )
      {
        if ( v7 )
          *v7 = (HGLOBAL)*v3;
        v8 = v3[1];
      }
      else
      {
        if ( v7 )
          *v7 = 0;
        v8 = 0;
      }
      if ( !*v7 || !(unsigned int)ExtractDDEDataInfo(*v7, &v18, &v19) || (v18 & 0x1000) == 0 )
        return ClSpontAdviseData(*((struct tagCL_CONV_INFO **)a1 + 1), (__int64)v3);
      v10 = v19;
      v11 = 0x8000;
      if ( (v18 & 0x8000u) == 0 )
      {
        GlobalDeleteAtom(v8);
      }
      else
      {
        if ( *((_WORD *)a1 + 21) != v19 || *((_WORD *)a1 + 20) != (_WORD)v8 )
          v11 = 0;
        v12 = PackAndPostMessage(
                *(HWND *)(*((_QWORD *)a1 + 1) + 40LL),
                0x3E5u,
                0x3E4u,
                *(HWND *)(*((_QWORD *)a1 + 1) + 48LL),
                0,
                v11,
                v8);
        if ( v12 )
          SetLastDDEMLError(*(struct tagCL_INSTANCE_INFO **)(*((_QWORD *)a1 + 1) + 8LL), v12);
      }
      if ( v10 == *((_WORD *)a1 + 21) && (_WORD)v8 == *((_WORD *)a1 + 20) )
      {
        v13 = -1;
        goto LABEL_28;
      }
      FreeDDEData(*v7, 0, 1);
      *v7 = 0;
LABEL_27:
      v13 = 0;
LABEL_28:
      if ( !(unsigned int)TransactionComplete(a1, (HDDEDATA)v13) )
      {
LABEL_32:
        FreeDDElParam(v4, (LPARAM)v3);
        return 1;
      }
LABEL_29:
      GlobalDeleteAtom(*((_WORD *)a1 + 20));
      v14 = (void *)*((_QWORD *)a1 + 8);
      if ( v14 )
        FreeDDEData(v14, 0, 1);
      UnlinkTransaction(a1);
      LocalFree(v15);
      if ( !v4 )
        return 1;
      goto LABEL_32;
  }
  v6 = (struct tagCL_CONV_INFO *)*((_QWORD *)a1 + 1);
  return SpontaneousClientMessage(v6, msg, (__int64)a3);
}

```

## disassembly

```asm
0x18008f600  mov     r11, rsp
0x18008f603  mov     [r11+8], rbx
0x18008f607  mov     [r11+18h], rbp
0x18008f60b  push    rsi
0x18008f60c  push    rdi
0x18008f60d  push    r12
0x18008f60f  push    r14
0x18008f611  push    r15
0x18008f613  sub     rsp, 40h
0x18008f617  xor     eax, eax
0x18008f619  mov     rdi, r8
0x18008f61c  mov     [r11+20h], ax
0x18008f621  mov     r14d, edx
0x18008f624  mov     [rsp+68h+arg_8], ax
0x18008f629  mov     rbx, rcx
0x18008f62c  test    edx, edx
0x18008f62e  jz      loc_18008F760
0x18008f634  mov     eax, edx
0x18008f636  mov     esi, 3E4h
0x18008f63b  sub     eax, esi
0x18008f63d  jz      loc_18008F7BA
0x18008f643  cmp     eax, 1
0x18008f646  jz      short loc_18008F651
0x18008f648  mov     rcx, [rcx+8]
0x18008f64c  jmp     loc_18008F7E2
0x18008f651  lea     rsi, [rcx+40h]
0x18008f655  mov     rcx, rdi; pMem
0x18008f658  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f65d  test    eax, eax
0x18008f65f  jnz     short loc_18008F671
0x18008f661  test    rsi, rsi
0x18008f664  jz      short loc_18008F66D
0x18008f666  mov     qword ptr [rsi], 0
0x18008f66d  xor     ebp, ebp
0x18008f66f  jmp     short loc_18008F680
0x18008f671  test    rsi, rsi
0x18008f674  jz      short loc_18008F67C
0x18008f676  mov     rax, [rdi]
0x18008f679  mov     [rsi], rax
0x18008f67c  mov     rbp, [rdi+8]
0x18008f680  mov     rcx, [rsi]; hMem
0x18008f683  test    rcx, rcx
0x18008f686  jnz     short loc_18008F699
0x18008f688  mov     rcx, [rbx+8]; struct tagCL_CONV_INFO *
0x18008f68c  mov     rdx, rdi; __int64
0x18008f68f  call    ?ClSpontAdviseData@@YAHPEAUtagCL_CONV_INFO@@_J@Z; ClSpontAdviseData(tagCL_CONV_INFO *,__int64)
0x18008f694  jmp     loc_18008F7A1
0x18008f699  lea     r8, [rsp+68h+arg_18]; unsigned __int16 *
0x18008f6a1  lea     rdx, [rsp+68h+arg_8]; unsigned __int16 *
0x18008f6a6  call    ?ExtractDDEDataInfo@@YAHPEAXPEAG1@Z; ExtractDDEDataInfo(void *,ushort *,ushort *)
0x18008f6ab  test    eax, eax
0x18008f6ad  jz      short loc_18008F688
0x18008f6af  mov     eax, 1000h
0x18008f6b4  test    [rsp+68h+arg_8], ax
0x18008f6b9  jz      short loc_18008F688
0x18008f6bb  movzx   r12d, [rsp+68h+arg_18]
0x18008f6c4  mov     eax, 8000h
0x18008f6c9  test    [rsp+68h+arg_8], ax
0x18008f6ce  jz      short loc_18008F721
0x18008f6d0  cmp     [rbx+2Ah], r12w
0x18008f6d5  jnz     short loc_18008F6DD
0x18008f6d7  cmp     [rbx+28h], bp
0x18008f6db  jz      short loc_18008F6DF
0x18008f6dd  xor     eax, eax
0x18008f6df  mov     rcx, [rbx+8]
0x18008f6e3  mov     edx, 3E5h; unsigned int
0x18008f6e8  mov     [rsp+68h+var_38], rbp; unsigned __int64
0x18008f6ed  mov     [rsp+68h+var_40], rax; unsigned __int64
0x18008f6f2  mov     [rsp+68h+var_48], 0; __int64
0x18008f6fb  mov     r9, [rcx+30h]; HWND
0x18008f6ff  lea     r8d, [rdx-1]; unsigned int
0x18008f703  mov     rcx, [rcx+28h]; hWnd
0x18008f707  call    ?PackAndPostMessage@@YAKPEAUHWND__@@II0_J_K2@Z; PackAndPostMessage(HWND__ *,uint,uint,HWND__ *,__int64,unsigned __int64,unsigned __int64)
0x18008f70c  test    eax, eax
0x18008f70e  jz      short loc_18008F72A
0x18008f710  mov     rcx, [rbx+8]
0x18008f714  mov     edx, eax; unsigned int
0x18008f716  mov     rcx, [rcx+8]; struct tagCL_INSTANCE_INFO *
0x18008f71a  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18008f71f  jmp     short loc_18008F72A
0x18008f721  movzx   ecx, bp; nAtom
0x18008f724  call    cs:__imp_GlobalDeleteAtom
0x18008f72a  cmp     r12w, [rbx+2Ah]
0x18008f72f  jnz     short loc_18008F73D
0x18008f731  cmp     bp, [rbx+28h]
0x18008f735  jnz     short loc_18008F73D
0x18008f737  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008f73b  jmp     short loc_18008F754
0x18008f73d  mov     rcx, [rsi]; hMem
0x18008f740  xor     edx, edx; int
0x18008f742  lea     r8d, [rdx+1]; int
0x18008f746  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x18008f74b  mov     qword ptr [rsi], 0
0x18008f752  xor     edx, edx; HDDEDATA
0x18008f754  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f757  call    ?TransactionComplete@@YAHPEAUtagXACT_INFO@@PEAUHDDEDATA__@@@Z; TransactionComplete(tagXACT_INFO *,HDDEDATA__ *)
0x18008f75c  test    eax, eax
0x18008f75e  jz      short loc_18008F791
0x18008f760  movzx   ecx, word ptr [rbx+28h]; nAtom
0x18008f764  call    cs:__imp_GlobalDeleteAtom
0x18008f76a  mov     rcx, [rbx+40h]; hMem
0x18008f76e  test    rcx, rcx
0x18008f771  jz      short loc_18008F77E
0x18008f773  xor     edx, edx; int
0x18008f775  lea     r8d, [rdx+1]; int
0x18008f779  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x18008f77e  mov     rcx, rbx; struct tagXACT_INFO *
0x18008f781  call    ?UnlinkTransaction@@YAXPEAUtagXACT_INFO@@@Z; UnlinkTransaction(tagXACT_INFO *)
0x18008f786  call    cs:__imp_LocalFree
0x18008f78c  test    r14d, r14d
0x18008f78f  jz      short loc_18008F79C
0x18008f791  mov     rdx, rdi; lParam
0x18008f794  mov     ecx, r14d; msg
0x18008f797  call    FreeDDElParam
0x18008f79c  mov     eax, 1
0x18008f7a1  lea     r11, [rsp+68h+var_28]
0x18008f7a6  mov     rbx, [r11+30h]
0x18008f7aa  mov     rbp, [r11+40h]
0x18008f7ae  mov     rsp, r11
0x18008f7b1  pop     r15
0x18008f7b3  pop     r14
0x18008f7b5  pop     r12
0x18008f7b7  pop     rdi
0x18008f7b8  pop     rsi
0x18008f7b9  retn
0x18008f7ba  mov     rcx, rdi; pMem
0x18008f7bd  call    ?IsValidGlobalHandle@@YAHPEAX@Z; IsValidGlobalHandle(void *)
0x18008f7c2  test    eax, eax
0x18008f7c4  jnz     short loc_18008F7CC
0x18008f7c6  xor     eax, eax
0x18008f7c8  xor     ecx, ecx
0x18008f7ca  jmp     short loc_18008F7D3
0x18008f7cc  mov     rax, [rdi]
0x18008f7cf  mov     rcx, [rdi+8]; nAtom
0x18008f7d3  cmp     cx, [rbx+28h]
0x18008f7d7  jz      short loc_18008F7E9
0x18008f7d9  mov     rcx, [rbx+8]; struct tagCL_CONV_INFO *
0x18008f7dd  mov     r8, rdi; __int64
0x18008f7e0  mov     edx, esi; unsigned int
0x18008f7e2  call    ?SpontaneousClientMessage@@YAHPEAUtagCL_CONV_INFO@@I_J@Z; SpontaneousClientMessage(tagCL_CONV_INFO *,uint,__int64)
0x18008f7e7  jmp     short loc_18008F7A1
0x18008f7e9  mov     word ptr [rbx+32h], 6
0x18008f7ef  mov     [rbx+2Eh], ax
0x18008f7f3  call    cs:__imp_GlobalDeleteAtom
0x18008f7f9  jmp     loc_18008F752
```
