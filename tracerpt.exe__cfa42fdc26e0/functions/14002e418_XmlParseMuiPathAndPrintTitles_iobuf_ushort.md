# XmlParseMuiPathAndPrintTitles(_iobuf *,ushort *)

- ea: `0x14002e418`
- end: `0x14002e53b`
- name: `?XmlParseMuiPathAndPrintTitles@@YAKPEAU_iobuf@@PEAG@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct _iobuf *, LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14002d050`

## callees

- `0x1400131c8`
- `0x140016360`
- `0x1400164c4`
- `0x14002e418`
- `0x140037f9c`
- `0x14003809c`
- `0x140038330`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002e42d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002e42d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002e443`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002e443`

## pseudocode

```c
__int64 __fastcall XmlParseMuiPathAndPrintTitles(struct _iobuf *a1, LPCWSTR lpSrc)
{
  HANDLE ProcessHeap; // rax
  char *v5; // rax
  struct _XMRW_OPEN_CONTEXT *v6; // rdi
  _QWORD **v8; // rsi
  unsigned int v9; // ebx
  _QWORD *v10; // rbx
  _QWORD *v11; // r14
  __int64 v12; // r15
  unsigned __int64 v13; // r12
  unsigned __int64 i; // r14

  ProcessHeap = GetProcessHeap();
  v5 = (char *)HeapAlloc(ProcessHeap, 8u, 0x98u);
  v6 = (struct _XMRW_OPEN_CONTEXT *)v5;
  if ( !v5 )
    return 8;
  v8 = (_QWORD **)(v5 + 128);
  v5[144] = 1;
  *((_QWORD *)v5 + 17) = v5 + 128;
  *((_QWORD *)v5 + 16) = v5 + 128;
  v9 = XmRWOpenFile(lpSrc, (struct _XMRW_OPEN_CONTEXT *)v5);
  if ( !v9 )
  {
    v9 = XmRWWalk(v6);
    if ( !v9 )
    {
      TracerptFPutws((wchar_t *)L"<StringTable>\r\n", a1);
      v10 = *v8;
      while ( v8 != v10 )
      {
        v11 = v10;
        v10 = (_QWORD *)*v10;
        TracerptFWPrintf(a1, (wchar_t *)L"<String ID='%wZ'>", v11 + 3);
        if ( a1 )
        {
          v12 = v11[9];
          if ( v12 )
          {
            v13 = *((unsigned __int16 *)v11 + 32);
            for ( i = 0; i < v13; v12 += 2 )
            {
              PrintWChar(a1);
              i += 2LL;
            }
          }
        }
        TracerptFPutws((wchar_t *)L"</String>\r\n", a1);
      }
      TracerptFPutws((wchar_t *)L"</StringTable>\r\n", a1);
      v9 = 0;
    }
  }
  XmlCleanup((char *)v6);
  return v9;
}

```

## disassembly

```asm
0x14002e418  push    rbx
0x14002e41a  push    rbp
0x14002e41b  push    rsi
0x14002e41c  push    rdi
0x14002e41d  push    r12
0x14002e41f  push    r14
0x14002e421  push    r15
0x14002e423  sub     rsp, 20h
0x14002e427  mov     rbx, rdx
0x14002e42a  mov     rbp, rcx
0x14002e42d  call    cs:__imp_GetProcessHeap
0x14002e433  mov     esi, 8
0x14002e438  mov     r8d, 98h; dwBytes
0x14002e43e  mov     rcx, rax; hHeap
0x14002e441  mov     edx, esi; dwFlags
0x14002e443  call    cs:__imp_HeapAlloc
0x14002e449  mov     rdi, rax
0x14002e44c  test    rax, rax
0x14002e44f  jnz     short loc_14002E458
0x14002e451  mov     eax, esi
0x14002e453  jmp     loc_14002E52C
0x14002e458  lea     rsi, [rax+80h]
0x14002e45f  mov     byte ptr [rax+90h], 1
0x14002e466  mov     rdx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14002e469  mov     [rax+88h], rsi
0x14002e470  mov     rcx, rbx; lpSrc
0x14002e473  mov     [rsi], rsi
0x14002e476  call    ?XmRWOpenFile@@YAKPEAGPEAU_XMRW_OPEN_CONTEXT@@@Z; XmRWOpenFile(ushort *,_XMRW_OPEN_CONTEXT *)
0x14002e47b  mov     ebx, eax
0x14002e47d  test    eax, eax
0x14002e47f  jnz     loc_14002E522
0x14002e485  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14002e488  call    ?XmRWWalk@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z; XmRWWalk(_XMRW_OPEN_CONTEXT *)
0x14002e48d  mov     ebx, eax
0x14002e48f  test    eax, eax
0x14002e491  jnz     loc_14002E522
0x14002e497  mov     rdx, rbp; struct _iobuf *
0x14002e49a  lea     rcx, aStringtable_3; "<StringTable>\r\n"
0x14002e4a1  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002e4a6  mov     rbx, [rsi]
0x14002e4a9  jmp     short loc_14002E50C
0x14002e4ab  lea     r14, [rbx]
0x14002e4ae  mov     rcx, rbp; struct _iobuf *
0x14002e4b1  mov     rbx, [rbx]
0x14002e4b4  lea     r8, [r14+18h]
0x14002e4b8  lea     rdx, aStringIdWz; "<String ID='%wZ'>"
0x14002e4bf  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14002e4c4  test    rbp, rbp
0x14002e4c7  jz      short loc_14002E4FD
0x14002e4c9  mov     r15, [r14+48h]
0x14002e4cd  test    r15, r15
0x14002e4d0  jz      short loc_14002E4FD
0x14002e4d2  movzx   r12d, word ptr [r14+40h]
0x14002e4d7  xor     r14d, r14d
0x14002e4da  test    r12, r12
0x14002e4dd  jz      short loc_14002E4FD
0x14002e4df  movzx   r9d, word ptr [r15]
0x14002e4e3  xor     r8d, r8d
0x14002e4e6  mov     dl, 1
0x14002e4e8  mov     rcx, rbp; struct _iobuf *
0x14002e4eb  call    PrintWChar
0x14002e4f0  add     r14, 2
0x14002e4f4  lea     r15, [r15+2]
0x14002e4f8  cmp     r14, r12
0x14002e4fb  jb      short loc_14002E4DF
0x14002e4fd  mov     rdx, rbp; struct _iobuf *
0x14002e500  lea     rcx, aString; "</String>\r\n"
0x14002e507  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002e50c  cmp     rsi, rbx
0x14002e50f  jnz     short loc_14002E4AB
0x14002e511  mov     rdx, rbp; struct _iobuf *
0x14002e514  lea     rcx, aStringtable; "</StringTable>\r\n"
0x14002e51b  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14002e520  xor     ebx, ebx
0x14002e522  mov     rcx, rdi; void *
0x14002e525  call    ?XmlCleanup@@YAXPEAX@Z; XmlCleanup(void *)
0x14002e52a  mov     eax, ebx
0x14002e52c  add     rsp, 20h
0x14002e530  pop     r15
0x14002e532  pop     r14
0x14002e534  pop     r12
0x14002e536  pop     rdi
0x14002e537  pop     rsi
0x14002e538  pop     rbp
0x14002e539  pop     rbx
0x14002e53a  retn
```
