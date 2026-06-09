# _ClientCopyDDEOut2(tagINTDDEINFO *)

- ea: `0x1800786b4`
- end: `0x180078769`
- name: `?_ClientCopyDDEOut2@@YAHPEAUtagINTDDEINFO@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct tagINTDDEINFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800948a0`

## callees

- `0x1800784d4`
- `0x1800786b4`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078715`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078739`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078715`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180078739`
- `GDI32!GdiCreateLocalEnhMetaFile` at `0x180078705`
- `GDI32!GdiCreateLocalEnhMetaFile` at `0x180078705`
- `GDI32!GdiCreateLocalMetaFilePict` at `0x18007871d`
- `GDI32!GdiCreateLocalMetaFilePict` at `0x18007871d`

## pseudocode

```c
_BOOL8 __fastcall _ClientCopyDDEOut2(struct tagINTDDEINFO *a1)
{
  BOOL v2; // ebx
  void *v3; // rcx
  __int64 v4; // rsi
  __int64 LocalEnhMetaFile; // rax
  int v6; // edx

  v2 = 1;
  v3 = (void *)*((_QWORD *)a1 + 6);
  if ( v3 )
  {
    v4 = *((_QWORD *)a1 + 4);
    if ( *(_WORD *)(v4 + 2) != 2 )
    {
      if ( *(_WORD *)(v4 + 2) == 3 )
        goto LABEL_14;
      if ( *(_WORD *)(v4 + 2) == 8 )
      {
        *(_QWORD *)(v4 + 4) = v3;
        v3 = (void *)*((_QWORD *)a1 + 6);
        goto LABEL_13;
      }
      if ( *(_WORD *)(v4 + 2) != 9 )
      {
        if ( *(_WORD *)(v4 + 2) == 14 )
        {
LABEL_11:
          LocalEnhMetaFile = GdiCreateLocalEnhMetaFile(v3);
LABEL_15:
          *(_QWORD *)(v4 + 4) = LocalEnhMetaFile;
          v2 = LocalEnhMetaFile != 0;
          goto LABEL_17;
        }
        if ( *(_WORD *)(v4 + 2) != 130 )
        {
          if ( *(_WORD *)(v4 + 2) != 131 )
          {
            if ( *(_WORD *)(v4 + 2) != 142 )
            {
              v2 = 0;
LABEL_13:
              GlobalUnlock(v3);
              goto LABEL_17;
            }
            goto LABEL_11;
          }
LABEL_14:
          LocalEnhMetaFile = GdiCreateLocalMetaFilePict(v3);
          goto LABEL_15;
        }
      }
    }
    *(_QWORD *)(v4 + 4) = v3;
  }
LABEL_17:
  GlobalUnlock(*((HGLOBAL *)a1 + 3));
  v6 = *((_DWORD *)a1 + 4);
  if ( (v6 & 0x800) != 0 )
    FixupDdeExecuteIfNecessary((void **)a1 + 3, v6 & 0x10000);
  return v2;
}

```

## disassembly

```asm
0x1800786b4  mov     [rsp+arg_0], rbx
0x1800786b9  mov     [rsp+arg_8], rsi
0x1800786be  push    rdi
0x1800786bf  sub     rsp, 20h
0x1800786c3  mov     rdi, rcx
0x1800786c6  mov     ebx, 1
0x1800786cb  mov     rcx, [rcx+30h]
0x1800786cf  test    rcx, rcx
0x1800786d2  jz      short loc_180078735
0x1800786d4  mov     rsi, [rdi+20h]
0x1800786d8  movzx   edx, word ptr [rsi+2]
0x1800786dc  sub     edx, 2
0x1800786df  jz      short loc_180078731
0x1800786e1  sub     edx, ebx
0x1800786e3  jz      short loc_18007871D
0x1800786e5  sub     edx, 5
0x1800786e8  jz      short loc_18007870D
0x1800786ea  sub     edx, ebx
0x1800786ec  jz      short loc_180078731
0x1800786ee  sub     edx, 5
0x1800786f1  jz      short loc_180078705
0x1800786f3  sub     edx, 74h ; 't'
0x1800786f6  jz      short loc_180078731
0x1800786f8  sub     edx, ebx
0x1800786fa  jz      short loc_18007871D
0x1800786fc  cmp     edx, 0Bh
0x1800786ff  jz      short loc_180078705
0x180078701  xor     ebx, ebx
0x180078703  jmp     short loc_180078715
0x180078705  call    cs:__imp_GdiCreateLocalEnhMetaFile
0x18007870b  jmp     short loc_180078723
0x18007870d  mov     [rsi+4], rcx
0x180078711  mov     rcx, [rdi+30h]; hMem
0x180078715  call    cs:__imp_GlobalUnlock
0x18007871b  jmp     short loc_180078735
0x18007871d  call    cs:__imp_GdiCreateLocalMetaFilePict
0x180078723  xor     ebx, ebx
0x180078725  mov     [rsi+4], rax
0x180078729  test    rax, rax
0x18007872c  setnz   bl
0x18007872f  jmp     short loc_180078735
0x180078731  mov     [rsi+4], rcx
0x180078735  mov     rcx, [rdi+18h]; hMem
0x180078739  call    cs:__imp_GlobalUnlock
0x18007873f  mov     edx, [rdi+10h]
0x180078742  bt      edx, 0Bh
0x180078746  jnb     short loc_180078757
0x180078748  and     edx, 10000h; int
0x18007874e  lea     rcx, [rdi+18h]; void **
0x180078752  call    ?FixupDdeExecuteIfNecessary@@YAHPEAPEAXH@Z; FixupDdeExecuteIfNecessary(void * *,int)
0x180078757  mov     rsi, [rsp+28h+arg_8]
0x18007875c  mov     eax, ebx
0x18007875e  mov     rbx, [rsp+28h+arg_0]
0x180078763  add     rsp, 20h
0x180078767  pop     rdi
0x180078768  retn
```
