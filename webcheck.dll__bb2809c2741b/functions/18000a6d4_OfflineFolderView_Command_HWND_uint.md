# OfflineFolderView_Command(HWND__ *,uint)

- ea: `0x18000a6d4`
- end: `0x18000a7f6`
- name: `?OfflineFolderView_Command@@YAJPEAUHWND__@@I@Z`
- size: `290`
- prototype: `__int64 __fastcall(HWND, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a370`
- `0x18000a9a0`

## callees

- `0x18000a6d4`
- `0x18000e688`
- `0x18001bdb0`
- `0x18001bf10`
- `0x180027c04`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000a775`
- `KERNEL32!LocalAlloc` at `0x18000a775`
- `KERNEL32!LocalFree` at `0x18000a7de`
- `KERNEL32!LocalFree` at `0x18000a7de`
- `SHELL32!__imp_SHShellFolderView_Message` at `0x18000a717`
- `SHELL32!__imp_SHShellFolderView_Message` at `0x18000a758`
- `SHELL32!__imp_SHShellFolderView_Message` at `0x18000a717`
- `SHELL32!__imp_SHShellFolderView_Message` at `0x18000a758`

## pseudocode

```c
__int64 __fastcall OfflineFolderView_Command(HWND a1, int a2, UINT a3, DWORD_PTR a4)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  const WCHAR *v7; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // edi
  char *v12; // rsi
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  LPARAM v15; // rcx
  __int64 v16; // r10
  __int64 v17; // rax
  LPARAM lParam; // [rsp+40h] [rbp+18h] BYREF

  v4 = a2 - 1;
  if ( v4 )
  {
    v5 = v4 - 6;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = (const WCHAR *)(unsigned int)(v6 - 2);
        if ( (_DWORD)v7 )
        {
          if ( (_DWORD)v7 != 10 )
            return 2147500037LL;
          HtmlHelpW(a1, v7, a3, a4);
        }
        else
        {
          SHShellFolderView_Message(a1, 1u, 0);
        }
      }
      else
      {
        SendUpdateRequests((__int64)a1, 0, 0);
      }
    }
    else
    {
      v9 = (unsigned int)IsGlobalOffline();
      SetGlobalOffline(v9 == 0);
    }
  }
  else
  {
    lParam = 0;
    v10 = SHShellFolderView_Message(a1, 9u, (LPARAM)&lParam);
    v11 = v10;
    if ( lParam )
    {
      if ( v10 )
      {
        v12 = (char *)LocalAlloc(0x40u, 16LL * v10);
        if ( v12 )
        {
          v13 = 0;
          v14 = 0;
          if ( v11 )
          {
            do
            {
              v15 = lParam;
              v16 = *(_QWORD *)(lParam + 8LL * v14);
              if ( *(_WORD *)v16 > 0xE0u && *(_WORD *)(v16 + 2) == 29701 )
              {
                v17 = 2LL * v13++;
                *(_OWORD *)&v12[8 * v17] = *(_OWORD *)(v16 + 128);
              }
              ++v14;
            }
            while ( v14 < v11 );
            if ( v13 )
              SendUpdateRequests(v15, v12, v13);
          }
          LocalFree(v12);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a6d4  mov     [rsp+arg_0], rbx
0x18000a6d9  mov     [rsp+arg_8], rsi
0x18000a6de  push    rdi
0x18000a6df  sub     rsp, 20h
0x18000a6e3  sub     edx, 1
0x18000a6e6  jz      short loc_18000A749
0x18000a6e8  sub     edx, 6
0x18000a6eb  jz      short loc_18000A731
0x18000a6ed  sub     edx, 1
0x18000a6f0  jz      short loc_18000A722
0x18000a6f2  sub     edx, 2; pszFile
0x18000a6f5  jz      short loc_18000A710
0x18000a6f7  cmp     edx, 0Ah
0x18000a6fa  jz      short loc_18000A706
0x18000a6fc  mov     eax, 80004005h
0x18000a701  jmp     loc_18000A7E6
0x18000a706  call    HtmlHelpW
0x18000a70b  jmp     loc_18000A7E4
0x18000a710  xor     r8d, r8d; lParam
0x18000a713  lea     edx, [r8+1]; uMsg
0x18000a717  call    cs:__imp_SHShellFolderView_Message
0x18000a71d  jmp     loc_18000A7E4
0x18000a722  xor     r8d, r8d
0x18000a725  xor     edx, edx
0x18000a727  call    SendUpdateRequests
0x18000a72c  jmp     loc_18000A7E4
0x18000a731  call    ?IsGlobalOffline@@YAHXZ; IsGlobalOffline(void)
0x18000a736  xor     ebx, ebx
0x18000a738  test    eax, eax
0x18000a73a  setz    bl
0x18000a73d  mov     ecx, ebx; int
0x18000a73f  call    ?SetGlobalOffline@@YAXH@Z; SetGlobalOffline(int)
0x18000a744  jmp     loc_18000A7E4
0x18000a749  xor     ebx, ebx
0x18000a74b  lea     r8, [rsp+28h+lParam]; lParam
0x18000a750  mov     [rsp+28h+lParam], rbx
0x18000a755  lea     edx, [rbx+9]; uMsg
0x18000a758  call    cs:__imp_SHShellFolderView_Message
0x18000a75e  mov     rdi, rax
0x18000a761  cmp     [rsp+28h+lParam], rbx
0x18000a766  jz      short loc_18000A7E4
0x18000a768  test    edi, edi
0x18000a76a  jz      short loc_18000A7E4
0x18000a76c  mov     edx, edi
0x18000a76e  lea     ecx, [rbx+40h]; uFlags
0x18000a771  shl     rdx, 4; uBytes
0x18000a775  call    cs:__imp_LocalAlloc
0x18000a77b  mov     rsi, rax
0x18000a77e  test    rax, rax
0x18000a781  jz      short loc_18000A7E4
0x18000a783  mov     r8d, ebx
0x18000a786  mov     r9d, ebx
0x18000a789  test    edi, edi
0x18000a78b  jz      short loc_18000A7DB
0x18000a78d  mov     rcx, [rsp+28h+lParam]
0x18000a792  mov     eax, 0E0h
0x18000a797  mov     edx, r9d
0x18000a79a  mov     r10, [rcx+rdx*8]
0x18000a79e  cmp     [r10], ax
0x18000a7a2  jbe     short loc_18000A7C6
0x18000a7a4  mov     eax, 7405h
0x18000a7a9  cmp     [r10+2], ax
0x18000a7ae  jnz     short loc_18000A7C6
0x18000a7b0  movups  xmm0, xmmword ptr [r10+80h]
0x18000a7b8  mov     eax, r8d
0x18000a7bb  add     rax, rax
0x18000a7be  inc     r8d
0x18000a7c1  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18000a7c6  inc     r9d
0x18000a7c9  cmp     r9d, edi
0x18000a7cc  jb      short loc_18000A78D
0x18000a7ce  test    r8d, r8d
0x18000a7d1  jz      short loc_18000A7DB
0x18000a7d3  mov     rdx, rsi
0x18000a7d6  call    SendUpdateRequests
0x18000a7db  mov     rcx, rsi; hMem
0x18000a7de  call    cs:__imp_LocalFree
0x18000a7e4  xor     eax, eax
0x18000a7e6  mov     rbx, [rsp+28h+arg_0]
0x18000a7eb  mov     rsi, [rsp+28h+arg_8]
0x18000a7f0  add     rsp, 20h
0x18000a7f4  pop     rdi
0x18000a7f5  retn
```
