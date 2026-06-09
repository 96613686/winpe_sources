# RecordDirScanFailures(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ushort const *,long,uint)

- ea: `0x180022684`
- end: `0x18002279e`
- name: `?RecordDirScanFailures@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@PEBGJI@Z`
- size: `282`
- prototype: `int(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, const unsigned __int16 *, int, unsigned int)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18001dca4`
- `0x18001e58c`
- `0x180020750`
- `0x1800208fc`
- `0x180020b5c`
- `0x180022ab4`

## callees

- `0x1800152d4`
- `0x18001f218`
- `0x180020c30`
- `0x180022684`
- `0x180023944`

## string_xrefs

- `0x1800226c0`: `<EmptyPath>`

## pseudocode

```c
__int64 __fastcall RecordDirScanFailures(
        struct _FILE_ID_EXTD_DIR_INFORMATION *a1,
        struct DIRECTORY_SCAN_FUNC_ARGS *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // dx
  unsigned int v11; // ecx
  const wchar_t *v12; // rdi
  unsigned int v13; // edx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = 2 * wcsnlen_s(a3, 0x4000u);
  if ( v9 )
    v10 = v9;
  else
    v10 = 22;
  v11 = *((unsigned __int16 *)a2 + 357);
  v12 = L"<EmptyPath>";
  if ( v9 )
    v12 = a3;
  v13 = v10 + 6;
  if ( v13 <= v11 )
  {
    if ( *((_WORD *)a2 + 352) >= 0x3E8u || v13 + *((unsigned __int16 *)a2 + 356) > v11 )
      WriteDirScanFailureBuffer(a2);
    v15 = CopyPath(a1, a2, 2, 0, v12);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v17 = *((unsigned __int16 *)a2 + 352);
      *(_DWORD *)(*((_QWORD *)a2 + 91) + 4 * v17) = a4;
      *(_DWORD *)(*((_QWORD *)a2 + 92) + 4 * v17) = *(_DWORD *)a2;
      *(_DWORD *)(*((_QWORD *)a2 + 93) + 4 * v17) = a5;
      ++*((_WORD *)a2 + 352);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C3,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
        (const char *)(unsigned int)v15,
        v19);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BA,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)0x8007000ELL,
      v18);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180022684  push    rbx
0x180022686  push    rbp
0x180022687  push    rsi
0x180022688  push    rdi
0x180022689  push    r14
0x18002268b  push    r15
0x18002268d  sub     rsp, 38h
0x180022691  mov     rbx, rdx
0x180022694  mov     r14, rcx
0x180022697  mov     edx, 4000h; MaxCount
0x18002269c  mov     rcx, r8; Source
0x18002269f  mov     ebp, r9d
0x1800226a2  mov     rsi, r8
0x1800226a5  call    wcsnlen_s
0x1800226aa  add     ax, ax
0x1800226ad  jnz     short loc_1800226B6
0x1800226af  mov     edx, 16h
0x1800226b4  jmp     short loc_1800226B9
0x1800226b6  movzx   edx, ax
0x1800226b9  movzx   ecx, word ptr [rbx+2CAh]
0x1800226c0  lea     rdi, aEmptypath; "<EmptyPath>"
0x1800226c7  test    ax, ax
0x1800226ca  movzx   edx, dx
0x1800226cd  cmovnz  rdi, rsi
0x1800226d1  add     edx, 6
0x1800226d4  cmp     edx, ecx
0x1800226d6  jbe     short loc_1800226FD
0x1800226d8  mov     rcx, [rsp+68h]; this
0x1800226dd  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800226e4  mov     ebx, 8007000Eh
0x1800226e9  mov     edx, 3BAh; void *
0x1800226ee  mov     r9d, ebx; char *
0x1800226f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226f6  mov     eax, ebx
0x1800226f8  jmp     loc_180022791
0x1800226fd  mov     eax, 3E8h
0x180022702  cmp     [rbx+2C0h], ax
0x180022709  jnb     short loc_180022718
0x18002270b  movzx   eax, word ptr [rbx+2C8h]
0x180022712  add     eax, edx
0x180022714  cmp     eax, ecx
0x180022716  jbe     short loc_180022720
0x180022718  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18002271b  call    ?WriteDirScanFailureBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteDirScanFailureBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x180022720  xor     r9d, r9d
0x180022723  mov     qword ptr [rsp+68h+var_48], rdi; int
0x180022728  mov     rdx, rbx
0x18002272b  mov     rcx, r14
0x18002272e  lea     r8d, [r9+2]
0x180022732  call    ?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z; CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)
0x180022737  mov     edi, eax
0x180022739  test    eax, eax
0x18002273b  jns     short loc_18002275A
0x18002273d  mov     rcx, [rsp+68h]; this
0x180022742  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180022749  mov     r9d, eax; char *
0x18002274c  mov     edx, 3C3h; void *
0x180022751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022756  mov     eax, edi
0x180022758  jmp     short loc_180022791
0x18002275a  movzx   edx, word ptr [rbx+2C0h]
0x180022761  mov     rax, [rbx+2D8h]
0x180022768  mov     [rax+rdx*4], ebp
0x18002276b  mov     rcx, [rbx+2E0h]
0x180022772  mov     eax, [rbx]
0x180022774  mov     [rcx+rdx*4], eax
0x180022777  mov     eax, [rsp+68h+arg_20]
0x18002277e  mov     rcx, [rbx+2E8h]
0x180022785  mov     [rcx+rdx*4], eax
0x180022788  inc     word ptr [rbx+2C0h]
0x18002278f  xor     eax, eax
0x180022791  add     rsp, 38h
0x180022795  pop     r15
0x180022797  pop     r14
0x180022799  pop     rdi
0x18002279a  pop     rsi
0x18002279b  pop     rbp
0x18002279c  pop     rbx
0x18002279d  retn
```
