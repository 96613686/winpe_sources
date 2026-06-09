# CContentContextMenuCB::s_DeleteReadOnlyPrompt(long,ushort const *,CDeleteThreadData *,int)

- ea: `0x18004921c`
- end: `0x18004941b`
- name: `?s_DeleteReadOnlyPrompt@CContentContextMenuCB@@CAJJPEBGPEAVCDeleteThreadData@@H@Z`
- size: `511`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, struct CDeleteThreadData *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180016780`

## callees

- `0x180035590`
- `0x180041e44`
- `0x180042010`
- `0x18004921c`
- `0x180053834`
- `0x18006d310`
- `0x18006e410`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800493a4`
- `KERNEL32!LocalFree` at `0x1800493a4`
- `SHLWAPI!PathFindFileNameW` at `0x180049317`
- `SHLWAPI!PathFindFileNameW` at `0x180049317`
- `USER32!LoadStringW` at `0x18004930c`
- `USER32!LoadStringW` at `0x18004930c`

## pseudocode

```c
__int64 __fastcall CContentContextMenuCB::s_DeleteReadOnlyPrompt(
        __int64 a1,
        const unsigned __int16 *a2,
        struct CDeleteThreadData *a3,
        int a4)
{
  __int64 v4; // r14
  unsigned __int16 *v7; // r15
  unsigned int v8; // ebx
  UINT v9; // edx
  HWND v10; // r13
  int v11; // ebp
  signed int v12; // edi
  __int64 v13; // rax
  LPWSTR FileNameW; // rax
  unsigned __int16 *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  char v22[8]; // [rsp+38h] [rbp-870h] BYREF
  __int64 v23; // [rsp+40h] [rbp-868h] BYREF
  int v24; // [rsp+48h] [rbp-860h]
  int v25; // [rsp+4Ch] [rbp-85Ch]
  unsigned __int16 *v26; // [rsp+50h] [rbp-858h]
  WCHAR Buffer[1024]; // [rsp+60h] [rbp-848h] BYREF

  v4 = *((_QWORD *)a3 + 4);
  v7 = 0;
  CPauseTimer::CPauseTimer((CPauseTimer *)v22, (struct CProgressUI *)v4);
  if ( (*((_DWORD *)a3 + 4) & 0x400) != 0 )
    goto LABEL_2;
  v9 = a4 != 0 ? 405 : 403;
  if ( *(_DWORD *)(v4 + 104) )
  {
    v8 = -2147023673;
    goto LABEL_23;
  }
  v10 = *(HWND *)(v4 + 120);
  v11 = -1;
  v12 = 0;
  v8 = 1;
  while ( (unsigned int)v12 < 0x14 )
  {
    if ( v9 == *((_DWORD *)a3 + 3 * v12 + 12) )
    {
      v13 = 12LL * v12;
      goto LABEL_12;
    }
    if ( !*((_DWORD *)a3 + 3 * v12 + 12) )
    {
      *((_DWORD *)a3 + 3 * v12 + 12) = v9;
      v13 = 12LL * v12;
      *(_QWORD *)((char *)a3 + v13 + 52) = 0;
LABEL_12:
      if ( *(_DWORD *)((char *)a3 + v13 + 52) )
        goto LABEL_23;
      if ( *(_DWORD *)((char *)a3 + v13 + 56) )
      {
        v8 = 0;
        goto LABEL_23;
      }
      v11 = v12;
      break;
    }
    ++v12;
  }
  LoadStringW(g_hInst, v9, Buffer, 1024);
  FileNameW = PathFindFileNameW(a2);
  v15 = FormatString(Buffer, FileNameW);
  v7 = v15;
  if ( !v15 )
  {
LABEL_22:
    v8 = -2147024891;
    goto LABEL_23;
  }
  v26 = v15;
  v24 = 0;
  v25 = 0;
  v23 = a4 != 0 ? 406 : 404;
  v16 = ShellDialogBoxParam(
          (HINSTANCE)v23,
          (const unsigned __int16 *)0x190,
          v10,
          (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))CContentContextMenuCB::s_DeleteReadOnlyDlgProc,
          (__int64)&v23)
      - 1;
  if ( !v16 )
  {
LABEL_2:
    v8 = 0;
    goto LABEL_23;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v8 = -2147023673;
    CProgressUI::_ForceCancel((CProgressUI *)v4);
    goto LABEL_23;
  }
  v18 = v17 - 405;
  if ( !v18 )
  {
    if ( v11 != -1 )
      *((_DWORD *)a3 + 3 * v12 + 14) = 1;
    goto LABEL_2;
  }
  v19 = v18 - 1;
  if ( v19 )
  {
    if ( v19 == 1 )
      goto LABEL_23;
    goto LABEL_22;
  }
  if ( v11 != -1 )
    *((_DWORD *)a3 + 3 * v12 + 13) = 1;
LABEL_23:
  LocalFree(v7);
  CPauseTimer::~CPauseTimer((CPauseTimer *)v22);
  return v8;
}

```

## disassembly

```asm
0x18004921c  mov     [rsp+arg_0], rbx
0x180049221  push    rbp
0x180049222  push    rsi
0x180049223  push    rdi
0x180049224  push    r12
0x180049226  push    r13
0x180049228  push    r14
0x18004922a  push    r15
0x18004922c  sub     rsp, 870h
0x180049233  mov     rax, cs:__security_cookie
0x18004923a  xor     rax, rsp
0x18004923d  mov     [rsp+8A8h+var_48], rax
0x180049245  mov     r14, [r8+20h]
0x180049249  lea     rcx, [rsp+8A8h+var_870]; this
0x18004924e  mov     [rsp+8A8h+pszPath], rdx
0x180049253  mov     r12d, r9d
0x180049256  mov     rdx, r14; struct CProgressUI *
0x180049259  mov     rsi, r8
0x18004925c  xor     r15d, r15d
0x18004925f  call    ??0CPauseTimer@@QEAA@PEAVCProgressUI@@@Z; CPauseTimer::CPauseTimer(CProgressUI *)
0x180049264  mov     r9d, 400h; cchBufferMax
0x18004926a  test    [rsi+10h], r9d
0x18004926e  jz      short loc_180049277
0x180049270  xor     ebx, ebx
0x180049272  jmp     loc_1800493A1
0x180049277  mov     eax, r12d
0x18004927a  neg     eax
0x18004927c  sbb     edx, edx
0x18004927e  xor     r8d, r8d
0x180049281  and     edx, 2
0x180049284  add     edx, 193h; uID
0x18004928a  cmp     [r14+68h], r8d
0x18004928e  jz      short loc_18004929A
0x180049290  mov     ebx, 800704C7h
0x180049295  jmp     loc_1800493A1
0x18004929a  mov     r13, [r14+78h]
0x18004929e  or      ebp, 0FFFFFFFFh
0x1800492a1  mov     edi, r8d
0x1800492a4  lea     ebx, [rbp+2]
0x1800492a7  cmp     edi, 14h
0x1800492aa  jnb     short loc_180049300
0x1800492ac  movsxd  rax, edi
0x1800492af  lea     rcx, [rax+rax*2]
0x1800492b3  cmp     edx, [rsi+rcx*4+30h]
0x1800492b7  jz      short loc_1800492D7
0x1800492b9  cmp     [rsi+rcx*4+30h], r8d
0x1800492be  jz      short loc_1800492C4
0x1800492c0  add     edi, ebx
0x1800492c2  jmp     short loc_1800492A7
0x1800492c4  lea     rax, [rax+rax*2]
0x1800492c8  mov     [rsi+rcx*4+30h], edx
0x1800492cc  shl     rax, 2
0x1800492d0  mov     [rax+rsi+34h], r8
0x1800492d5  jmp     short loc_1800492DF
0x1800492d7  lea     rax, [rax+rax*2]
0x1800492db  shl     rax, 2
0x1800492df  cmp     edi, 0FFFFFFFFh
0x1800492e2  jz      short loc_1800492FE
0x1800492e4  cmp     [rax+rsi+34h], r8d
0x1800492e9  jnz     loc_1800493A1
0x1800492ef  cmp     [rax+rsi+38h], r8d
0x1800492f4  jz      short loc_1800492FE
0x1800492f6  mov     ebx, r8d
0x1800492f9  jmp     loc_1800493A1
0x1800492fe  mov     ebp, edi
0x180049300  mov     rcx, cs:g_hInst; hInstance
0x180049307  lea     r8, [rsp+8A8h+Buffer]; lpBuffer
0x18004930c  call    cs:__imp_LoadStringW
0x180049312  mov     rcx, [rsp+8A8h+pszPath]; pszPath
0x180049317  call    cs:__imp_PathFindFileNameW
0x18004931d  mov     rdx, rax
0x180049320  lea     rcx, [rsp+8A8h+Buffer]; lpSource
0x180049325  call    ?FormatString@@YAPEAGPEBGZZ; FormatString(ushort const *,...)
0x18004932a  mov     r15, rax
0x18004932d  test    rax, rax
0x180049330  jz      short loc_18004939C
0x180049332  mov     [rsp+8A8h+var_858], rax
0x180049337  lea     r9, ?s_DeleteReadOnlyDlgProc@CContentContextMenuCB@@CA_JPEAUHWND__@@I_K_J@Z; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x18004933e  lea     rax, [rsp+8A8h+var_868]
0x180049343  mov     [rsp+8A8h+var_868+4], 0
0x18004934c  neg     r12d
0x18004934f  mov     [rsp+8A8h+var_85C], 0
0x180049357  mov     r8, r13; HWND
0x18004935a  mov     [rsp+8A8h+var_888], rax; __int64
0x18004935f  sbb     ecx, ecx
0x180049361  mov     edx, 190h; unsigned __int16 *
0x180049366  and     ecx, 2
0x180049369  add     ecx, 194h; HINSTANCE
0x18004936f  mov     dword ptr [rsp+8A8h+var_868], ecx
0x180049373  call    ?ShellDialogBoxParam@@YA_JPEAUHINSTANCE__@@PEBGPEAUHWND__@@P6A_J2I_K_J@Z4@Z; ShellDialogBoxParam(HINSTANCE__ *,ushort const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x180049378  sub     rax, rbx
0x18004937b  jz      loc_180049270
0x180049381  sub     rax, rbx
0x180049384  jz      loc_18004940C
0x18004938a  sub     rax, 195h
0x180049390  jz      short loc_1800493F3
0x180049392  sub     rax, rbx
0x180049395  jz      short loc_1800493E1
0x180049397  cmp     rax, rbx
0x18004939a  jz      short loc_1800493A1
0x18004939c  mov     ebx, 80070005h
0x1800493a1  mov     rcx, r15; hMem
0x1800493a4  call    cs:__imp_LocalFree
0x1800493aa  lea     rcx, [rsp+8A8h+var_870]; this
0x1800493af  call    ??1CPauseTimer@@QEAA@XZ; CPauseTimer::~CPauseTimer(void)
0x1800493b4  mov     eax, ebx
0x1800493b6  mov     rcx, [rsp+8A8h+var_48]
0x1800493be  xor     rcx, rsp; StackCookie
0x1800493c1  call    __security_check_cookie
0x1800493c6  mov     rbx, [rsp+8A8h+arg_0]
0x1800493ce  add     rsp, 870h
0x1800493d5  pop     r15
0x1800493d7  pop     r14
0x1800493d9  pop     r13
0x1800493db  pop     r12
0x1800493dd  pop     rdi
0x1800493de  pop     rsi
0x1800493df  pop     rbp
0x1800493e0  retn
0x1800493e1  cmp     ebp, 0FFFFFFFFh
0x1800493e4  jz      short loc_1800493A1
0x1800493e6  movsxd  rax, edi
0x1800493e9  lea     rcx, [rax+rax*2]
0x1800493ed  mov     [rsi+rcx*4+34h], ebx
0x1800493f1  jmp     short loc_1800493A1
0x1800493f3  cmp     ebp, 0FFFFFFFFh
0x1800493f6  jz      loc_180049270
0x1800493fc  movsxd  rax, edi
0x1800493ff  lea     rcx, [rax+rax*2]
0x180049403  mov     [rsi+rcx*4+38h], ebx
0x180049407  jmp     loc_180049270
0x18004940c  mov     rcx, r14; this
0x18004940f  mov     ebx, 800704C7h
0x180049414  call    ?_ForceCancel@CProgressUI@@QEAAJXZ; CProgressUI::_ForceCancel(void)
0x180049419  jmp     short loc_1800493A1
```
