# CContentContextMenuCB::s_DeleteOpErrorMessageWithSkip(long,ushort const *,CDeleteThreadData *,int)

- ea: `0x180048f50`
- end: `0x18004913f`
- name: `?s_DeleteOpErrorMessageWithSkip@CContentContextMenuCB@@CAJJPEBGPEAVCDeleteThreadData@@H@Z`
- size: `495`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, struct CDeleteThreadData *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016780`

## callees

- `0x180035590`
- `0x180048f50`
- `0x180053834`
- `0x18006d310`
- `0x18006e410`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004910c`
- `KERNEL32!LocalFree` at `0x18004910c`
- `SHLWAPI!PathFindFileNameW` at `0x180049072`
- `SHLWAPI!PathFindFileNameW` at `0x180049072`
- `USER32!LoadStringW` at `0x180049067`
- `USER32!LoadStringW` at `0x180049067`

## pseudocode

```c
__int64 __fastcall CContentContextMenuCB::s_DeleteOpErrorMessageWithSkip(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct CDeleteThreadData *a3,
        int a4)
{
  unsigned int v6; // ebx
  unsigned __int16 *v7; // r12
  __int64 v8; // r15
  int v9; // edi
  UINT v10; // edx
  int v11; // ebp
  signed int v12; // esi
  __int64 v13; // rax
  LPWSTR FileNameW; // rax
  unsigned __int16 *v15; // rax
  HINSTANCE v16; // rcx
  __int64 v17; // rax
  HWND v20; // [rsp+38h] [rbp-870h]
  __int64 v21; // [rsp+40h] [rbp-868h] BYREF
  int v22; // [rsp+48h] [rbp-860h]
  int v23; // [rsp+4Ch] [rbp-85Ch]
  unsigned __int16 *v24; // [rsp+50h] [rbp-858h]
  WCHAR Buffer[1024]; // [rsp+60h] [rbp-848h] BYREF

  v6 = a1;
  v7 = 0;
  if ( a1 != -2147023673 && (*((_DWORD *)a3 + 4) & 0x400) == 0 )
  {
    v8 = *((_QWORD *)a3 + 4);
    v9 = -2147023673;
    if ( !*(_DWORD *)(v8 + 104) )
      v9 = a1;
    if ( v9 == -2147023673 )
      goto LABEL_29;
    v20 = *(HWND *)(v8 + 120);
    switch ( v9 )
    {
      case -2147024891:
        v10 = 245;
        break;
      case -2147024882:
        v10 = 252;
        break;
      case -2147024877:
        v10 = 246;
        break;
      default:
        v10 = 242;
        if ( v9 == -2147020579 )
          v10 = 244;
        break;
    }
    v11 = -1;
    v12 = 0;
    v6 = 1;
    while ( (unsigned int)v12 < 0x14 )
    {
      if ( v10 == *((_DWORD *)a3 + 3 * v12 + 12) )
      {
        v13 = 12LL * v12;
        goto LABEL_21;
      }
      if ( !*((_DWORD *)a3 + 3 * v12 + 12) )
      {
        *((_DWORD *)a3 + 3 * v12 + 12) = v10;
        v13 = 12LL * v12;
        *(_QWORD *)((char *)a3 + v13 + 52) = 0;
LABEL_21:
        if ( *(_DWORD *)((char *)a3 + v13 + 52) )
          goto LABEL_30;
        v11 = v12;
        break;
      }
      ++v12;
    }
    LoadStringW(g_hInst, v10, Buffer, 1024);
    FileNameW = PathFindFileNameW(a2);
    v15 = FormatString(Buffer, FileNameW);
    v7 = v15;
    if ( !v15 )
    {
LABEL_29:
      v6 = v9;
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v24 = v15;
      v21 = (unsigned int)(a4 != 0) + 240;
      v17 = ShellDialogBoxParam(
              v16,
              (const unsigned __int16 *)0x18F,
              v20,
              (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))CContentContextMenuCB::s_DeleteErrorDlgProc,
              (__int64)&v21)
          - 1;
      if ( v17 )
      {
        if ( v17 == 360 )
        {
          if ( v11 != -1 )
            *((_DWORD *)a3 + 3 * v12 + 13) = 1;
        }
        else
        {
          v6 = -2147023673;
          CProgressUI::_ForceCancel((CProgressUI *)v8);
        }
      }
    }
  }
LABEL_30:
  LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x180048f50  mov     [rsp+arg_0], rbx
0x180048f55  push    rbp
0x180048f56  push    rsi
0x180048f57  push    rdi
0x180048f58  push    r12
0x180048f5a  push    r13
0x180048f5c  push    r14
0x180048f5e  push    r15
0x180048f60  sub     rsp, 870h
0x180048f67  mov     rax, cs:__security_cookie
0x180048f6e  xor     rax, rsp
0x180048f71  mov     [rsp+8A8h+var_48], rax
0x180048f79  mov     r14, r8
0x180048f7c  mov     [rsp+8A8h+pszPath], rdx
0x180048f81  xor     r8d, r8d
0x180048f84  mov     eax, 800704C7h
0x180048f89  mov     r13d, r9d
0x180048f8c  mov     ebx, ecx
0x180048f8e  mov     r12d, r8d
0x180048f91  cmp     ecx, eax
0x180048f93  jz      loc_180049109
0x180048f99  mov     r9d, 400h; cchBufferMax
0x180048f9f  test    [r14+10h], r9d
0x180048fa3  jnz     loc_180049109
0x180048fa9  mov     r15, [r14+20h]
0x180048fad  mov     edi, eax
0x180048faf  cmp     [r15+68h], r8d
0x180048fb3  cmovz   edi, ecx
0x180048fb6  cmp     edi, eax
0x180048fb8  jz      loc_180049107
0x180048fbe  mov     rax, [r15+78h]
0x180048fc2  mov     [rsp+8A8h+var_870], rax
0x180048fc7  cmp     edi, 80070005h
0x180048fcd  jz      short loc_180049001
0x180048fcf  cmp     edi, 8007000Eh
0x180048fd5  jz      short loc_180048FFA
0x180048fd7  cmp     edi, 80070013h
0x180048fdd  jz      short loc_180048FF3
0x180048fdf  mov     edx, 0F2h
0x180048fe4  cmp     edi, 800710DDh
0x180048fea  jnz     short loc_180049006
0x180048fec  mov     edx, 0F4h
0x180048ff1  jmp     short loc_180049006
0x180048ff3  mov     edx, 0F6h
0x180048ff8  jmp     short loc_180049006
0x180048ffa  mov     edx, 0FCh
0x180048fff  jmp     short loc_180049006
0x180049001  mov     edx, 0F5h; uID
0x180049006  or      ebp, 0FFFFFFFFh
0x180049009  mov     esi, r8d
0x18004900c  lea     ebx, [rbp+2]
0x18004900f  cmp     esi, 14h
0x180049012  jnb     short loc_18004905B
0x180049014  movsxd  rax, esi
0x180049017  lea     rcx, [rax+rax*2]
0x18004901b  cmp     edx, [r14+rcx*4+30h]
0x180049020  jz      short loc_180049041
0x180049022  cmp     [r14+rcx*4+30h], r8d
0x180049027  jz      short loc_18004902D
0x180049029  add     esi, ebx
0x18004902b  jmp     short loc_18004900F
0x18004902d  lea     rax, [rax+rax*2]
0x180049031  mov     [r14+rcx*4+30h], edx
0x180049036  shl     rax, 2
0x18004903a  mov     [rax+r14+34h], r8
0x18004903f  jmp     short loc_180049049
0x180049041  lea     rax, [rax+rax*2]
0x180049045  shl     rax, 2
0x180049049  cmp     esi, 0FFFFFFFFh
0x18004904c  jz      short loc_180049059
0x18004904e  cmp     [rax+r14+34h], r8d
0x180049053  jnz     loc_180049109
0x180049059  mov     ebp, esi
0x18004905b  mov     rcx, cs:g_hInst; hInstance
0x180049062  lea     r8, [rsp+8A8h+Buffer]; lpBuffer
0x180049067  call    cs:__imp_LoadStringW
0x18004906d  mov     rcx, [rsp+8A8h+pszPath]; pszPath
0x180049072  call    cs:__imp_PathFindFileNameW
0x180049078  mov     rdx, rax
0x18004907b  lea     rcx, [rsp+8A8h+Buffer]; lpSource
0x180049080  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x180049085  mov     r12, rax
0x180049088  test    rax, rax
0x18004908b  jz      short loc_180049107
0x18004908d  mov     r8, [rsp+8A8h+var_870]; HWND
0x180049092  lea     r9, ?s_DeleteErrorDlgProc@CContentContextMenuCB@@CA_JPEAUHWND__@@I_K_J@Z; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x180049099  neg     r13d
0x18004909c  mov     [rsp+8A8h+var_868+4], 0
0x1800490a5  mov     edx, 18Fh; unsigned __int16 *
0x1800490aa  mov     [rsp+8A8h+var_85C], 0
0x1800490b2  sbb     eax, eax
0x1800490b4  mov     [rsp+8A8h+var_858], r12
0x1800490b9  neg     eax
0x1800490bb  add     eax, 0F0h
0x1800490c0  mov     dword ptr [rsp+8A8h+var_868], eax
0x1800490c4  lea     rax, [rsp+8A8h+var_868]
0x1800490c9  mov     [rsp+8A8h+var_888], rax; __int64
0x1800490ce  call    ?ShellDialogBoxParam@@YA_JPEAUHINSTANCE__@@PEBGPEAUHWND__@@P6A_J2I_K_J@Z4@Z; ShellDialogBoxParam(HINSTANCE__ *,ushort const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x1800490d3  sub     rax, rbx
0x1800490d6  jz      short loc_180049109
0x1800490d8  sub     rax, rbx
0x1800490db  jz      short loc_1800490F8
0x1800490dd  cmp     rax, 167h
0x1800490e3  jnz     short loc_1800490F8
0x1800490e5  cmp     ebp, 0FFFFFFFFh
0x1800490e8  jz      short loc_180049109
0x1800490ea  movsxd  rax, esi
0x1800490ed  lea     rcx, [rax+rax*2]
0x1800490f1  mov     [r14+rcx*4+34h], ebx
0x1800490f6  jmp     short loc_180049109
0x1800490f8  mov     rcx, r15; this
0x1800490fb  mov     ebx, 800704C7h
0x180049100  call    ?_ForceCancel@CProgressUI@@QEAAJXZ; CProgressUI::_ForceCancel(void)
0x180049105  jmp     short loc_180049109
0x180049107  mov     ebx, edi
0x180049109  mov     rcx, r12; hMem
0x18004910c  call    cs:__imp_LocalFree
0x180049112  mov     eax, ebx
0x180049114  mov     rcx, [rsp+8A8h+var_48]
0x18004911c  xor     rcx, rsp; StackCookie
0x18004911f  call    __security_check_cookie
0x180049124  mov     rbx, [rsp+8A8h+arg_0]
0x18004912c  add     rsp, 870h
0x180049133  pop     r15
0x180049135  pop     r14
0x180049137  pop     r13
0x180049139  pop     r12
0x18004913b  pop     rdi
0x18004913c  pop     rsi
0x18004913d  pop     rbp
0x18004913e  retn
```
