# RecordWinOldDirStats(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001b430`
- end: `0x18001b521`
- name: `?RecordWinOldDirStats@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `241`
- prototype: `int __high(struct _FILE_ID_EXTD_DIR_INFORMATION *, struct DIRECTORY_SCAN_FUNC_ARGS *, enum ScanDirectoryObjectFlag, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800152d4`
- `0x18001b430`
- `0x18001ea24`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall RecordWinOldDirStats(__int64 a1, __int64 a2, int a3, unsigned __int8 a4)
{
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  unsigned int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // edi
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v7 = a3 - 1;
  if ( v7 && (v8 = v7 - 1) != 0 && (v9 = v8 - 2) != 0 )
  {
    if ( v9 == 12 )
      WriteWinOldScanBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
  }
  else
  {
    v10 = *(unsigned __int16 *)(a2 + 130);
    v11 = *(unsigned __int16 *)(a2 + 16LL * a4 + 40) + *(_DWORD *)(a1 + 60) + 6;
    if ( v11 <= v10 )
    {
      if ( *(_WORD *)(a2 + 120) >= 0x3E8u || v11 + *(unsigned __int16 *)(a2 + 128) > v10 )
        WriteWinOldScanBuffer((struct DIRECTORY_SCAN_FUNC_ARGS *)a2);
      v12 = CopyPath(a1, a2, 0, a4, 0);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7DC,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
          (const char *)(unsigned int)v12,
          v15);
        return v13;
      }
      *(_QWORD *)(*(_QWORD *)(a2 + 144) + 8LL * (unsigned __int16)(*(_WORD *)(a2 + 120))++) = *(_QWORD *)(a1 + 40);
    }
    else
    {
      ++*(_WORD *)(a2 + 80);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b430  mov     [rsp+arg_0], rbx
0x18001b435  mov     [rsp+arg_8], rsi
0x18001b43a  push    rdi
0x18001b43b  sub     rsp, 30h
0x18001b43f  movzx   edi, r9b
0x18001b443  mov     rbx, rdx
0x18001b446  mov     rsi, rcx
0x18001b449  sub     r8d, 1
0x18001b44d  jz      short loc_18001B472
0x18001b44f  sub     r8d, 1
0x18001b453  jz      short loc_18001B472
0x18001b455  sub     r8d, 2
0x18001b459  jz      short loc_18001B472
0x18001b45b  cmp     r8d, 0Ch
0x18001b45f  jnz     loc_18001B50F
0x18001b465  mov     rcx, rdx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001b468  call    ?WriteWinOldScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteWinOldScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001b46d  jmp     loc_18001B50F
0x18001b472  mov     r8d, [rsi+3Ch]
0x18001b476  mov     rax, rdi
0x18001b479  movzx   edx, word ptr [rdx+82h]
0x18001b480  add     rax, rax
0x18001b483  add     r8d, 6
0x18001b487  movzx   ecx, word ptr [rbx+rax*8+28h]
0x18001b48c  add     r8d, ecx
0x18001b48f  cmp     r8d, edx
0x18001b492  jbe     short loc_18001B49A
0x18001b494  inc     word ptr [rbx+50h]
0x18001b498  jmp     short loc_18001B50F
0x18001b49a  mov     eax, 3E8h
0x18001b49f  cmp     [rbx+78h], ax
0x18001b4a3  jnb     short loc_18001B4B3
0x18001b4a5  movzx   eax, word ptr [rbx+80h]
0x18001b4ac  add     eax, r8d
0x18001b4af  cmp     eax, edx
0x18001b4b1  jbe     short loc_18001B4BB
0x18001b4b3  mov     rcx, rbx; struct DIRECTORY_SCAN_FUNC_ARGS *
0x18001b4b6  call    ?WriteWinOldScanBuffer@@YAXPEAUDIRECTORY_SCAN_FUNC_ARGS@@@Z; WriteWinOldScanBuffer(DIRECTORY_SCAN_FUNC_ARGS *)
0x18001b4bb  mov     r9b, dil
0x18001b4be  mov     qword ptr [rsp+38h+var_18], 0; int
0x18001b4c7  xor     r8d, r8d
0x18001b4ca  mov     rdx, rbx
0x18001b4cd  mov     rcx, rsi
0x18001b4d0  call    ?CopyPath@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4PATH_TYPE@@_NPEBG@Z; CopyPath(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,PATH_TYPE,bool,ushort const *)
0x18001b4d5  mov     edi, eax
0x18001b4d7  test    eax, eax
0x18001b4d9  jns     short loc_18001B4F8
0x18001b4db  mov     rcx, [rsp+38h]; this
0x18001b4e0  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001b4e7  mov     r9d, eax; char *
0x18001b4ea  mov     edx, 7DCh; void *
0x18001b4ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4f4  mov     eax, edi
0x18001b4f6  jmp     short loc_18001B511
0x18001b4f8  movzx   edx, word ptr [rbx+78h]
0x18001b4fc  mov     rax, [rsi+28h]
0x18001b500  mov     rcx, [rbx+90h]
0x18001b507  mov     [rcx+rdx*8], rax
0x18001b50b  inc     word ptr [rbx+78h]
0x18001b50f  xor     eax, eax
0x18001b511  mov     rbx, [rsp+38h+arg_0]
0x18001b516  mov     rsi, [rsp+38h+arg_8]
0x18001b51b  add     rsp, 30h
0x18001b51f  pop     rdi
0x18001b520  retn
```
