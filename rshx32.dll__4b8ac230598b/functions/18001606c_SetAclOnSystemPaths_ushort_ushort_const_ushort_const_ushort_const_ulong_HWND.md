# SetAclOnSystemPaths(ushort *,ushort const *,ushort const *,ushort const *,ulong,HWND__ *)

- ea: `0x18001606c`
- end: `0x180016220`
- name: `?SetAclOnSystemPaths@@YAHPEAGPEBG11KPEAUHWND__@@@Z`
- size: `436`
- prototype: `_BOOL8 __fastcall(PCNZWCH lpString2, PCNZWCH lpString1, PCNZWCH, PCNZWCH, char, HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007950`

## callees

- `0x18001606c`
- `0x180019404`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800160e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001614e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800160e5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001614e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800161b8`
- `KERNEL32!lstrlenW` at `0x180016124`
- `KERNEL32!lstrlenW` at `0x180016124`

## pseudocode

```c
_BOOL8 __fastcall SetAclOnSystemPaths(PCNZWCH lpString2, PCNZWCH lpString1, PCNZWCH a3, PCNZWCH a4, char a5, HWND hWnd)
{
  __int64 v9; // rdi
  __int64 v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // r14d
  char cchCount2; // [rsp+28h] [rbp-40h]
  char cchCount2a; // [rsp+28h] [rbp-40h]
  char cchCount2b; // [rsp+28h] [rbp-40h]

  if ( lpString2 )
  {
    if ( (a5 & 0x44) == 0 )
      return 1;
    LODWORD(v9) = 0;
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
    }
    LODWORD(v10) = 0;
    if ( a4 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a4[v10] );
    }
    if ( !lpString1
      || CompareStringW(0x400u, 0, lpString1, -1, lpString2, -1) != 2
      || (unsigned int)MsgPopup(hWnd, 0x55u, 0x57u, 0x10134u, g_hInstance, cchCount2) != 7 )
    {
      if ( (v11 = lstrlenW(lpString2), v12 = v11, !(_DWORD)v9)
        || v11 < (unsigned int)v9
        || CompareStringW(0x400u, 1u, a3, v9, lpString2, v9) != 2
        || lpString2[(unsigned int)v9] && lpString2[(unsigned int)v9] != 92
        || (unsigned int)MsgPopup(hWnd, 0x56u, 0x57u, 0x10134u, g_hInstance, cchCount2a) != 7 )
      {
        if ( (_DWORD)v10
          && v12 >= (unsigned int)v10
          && CompareStringW(0x400u, 1u, a4, v10, lpString2, v10) == 2
          && (!lpString2[(unsigned int)v10] || lpString2[(unsigned int)v10] == 92) )
        {
          return (unsigned int)MsgPopup(hWnd, 0x56u, 0x57u, 0x10134u, g_hInstance, cchCount2b) != 7;
        }
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001606c  push    rbx
0x18001606e  push    rbp
0x18001606f  push    rsi
0x180016070  push    rdi
0x180016071  push    r13
0x180016073  push    r14
0x180016075  push    r15
0x180016077  sub     rsp, 30h
0x18001607b  xor     r13d, r13d
0x18001607e  mov     r15, r9
0x180016081  mov     rbp, r8
0x180016084  mov     rsi, rcx
0x180016087  test    rcx, rcx
0x18001608a  jz      loc_18001620F
0x180016090  test    [rsp+68h+arg_20], 44h
0x180016098  jz      loc_180016208
0x18001609e  or      r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x1800160a2  mov     edi, r13d
0x1800160a5  test    r8, r8
0x1800160a8  jz      short loc_1800160B7
0x1800160aa  mov     rdi, r9
0x1800160ad  inc     rdi
0x1800160b0  cmp     [r8+rdi*2], r13w
0x1800160b5  jnz     short loc_1800160AD
0x1800160b7  mov     ebx, r13d
0x1800160ba  test    r15, r15
0x1800160bd  jz      short loc_1800160CC
0x1800160bf  mov     rbx, r9
0x1800160c2  inc     rbx
0x1800160c5  cmp     [r15+rbx*2], r13w
0x1800160ca  jnz     short loc_1800160C2
0x1800160cc  test    rdx, rdx
0x1800160cf  jz      short loc_180016121
0x1800160d1  mov     r8, rdx; lpString1
0x1800160d4  mov     dword ptr [rsp+68h+cchCount2], r9d; char
0x1800160d9  xor     edx, edx; dwCmpFlags
0x1800160db  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800160e0  mov     ecx, 400h; Locale
0x1800160e5  call    cs:__imp_CompareStringW
0x1800160eb  cmp     eax, 2
0x1800160ee  jnz     short loc_180016121
0x1800160f0  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800160f7  mov     edx, 55h ; 'U'; unsigned int
0x1800160fc  mov     rcx, [rsp+68h+hWnd]; hWnd
0x180016104  mov     r9d, 10134h; uType
0x18001610a  mov     [rsp+68h+lpString2], rax; hAppInst
0x18001610f  lea     r8d, [rdx+2]; unsigned int
0x180016113  call    MsgPopup
0x180016118  cmp     eax, 7
0x18001611b  jz      loc_18001620F
0x180016121  mov     rcx, rsi; lpString
0x180016124  call    cs:__imp_lstrlenW
0x18001612a  mov     r14d, eax
0x18001612d  test    edi, edi
0x18001612f  jz      short loc_180016196
0x180016131  cmp     eax, edi
0x180016133  jb      short loc_180016196
0x180016135  mov     dword ptr [rsp+68h+cchCount2], edi; char
0x180016139  mov     r9d, edi; cchCount1
0x18001613c  mov     r8, rbp; lpString1
0x18001613f  mov     [rsp+68h+lpString2], rsi; lpString2
0x180016144  mov     edx, 1; dwCmpFlags
0x180016149  mov     ecx, 400h; Locale
0x18001614e  call    cs:__imp_CompareStringW
0x180016154  cmp     eax, 2
0x180016157  jnz     short loc_180016196
0x180016159  mov     eax, edi
0x18001615b  cmp     [rsi+rax*2], r13w
0x180016160  jz      short loc_180016169
0x180016162  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x180016167  jnz     short loc_180016196
0x180016169  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180016170  mov     edx, 56h ; 'V'; unsigned int
0x180016175  mov     rcx, [rsp+68h+hWnd]; hWnd
0x18001617d  mov     r9d, 10134h; uType
0x180016183  mov     [rsp+68h+lpString2], rax; hAppInst
0x180016188  lea     r8d, [rdx+1]; unsigned int
0x18001618c  call    MsgPopup
0x180016191  cmp     eax, 7
0x180016194  jz      short loc_18001620F
0x180016196  test    ebx, ebx
0x180016198  jz      short loc_180016208
0x18001619a  cmp     r14d, ebx
0x18001619d  jb      short loc_180016208
0x18001619f  mov     dword ptr [rsp+68h+cchCount2], ebx; char
0x1800161a3  mov     r9d, ebx; cchCount1
0x1800161a6  mov     r8, r15; lpString1
0x1800161a9  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800161ae  mov     edx, 1; dwCmpFlags
0x1800161b3  mov     ecx, 400h; Locale
0x1800161b8  call    cs:__imp_CompareStringW
0x1800161be  cmp     eax, 2
0x1800161c1  jnz     short loc_180016208
0x1800161c3  mov     eax, ebx
0x1800161c5  cmp     [rsi+rax*2], r13w
0x1800161ca  jz      short loc_1800161D3
0x1800161cc  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x1800161d1  jnz     short loc_180016208
0x1800161d3  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800161da  mov     edx, 56h ; 'V'; unsigned int
0x1800161df  mov     rcx, [rsp+68h+hWnd]; hWnd
0x1800161e7  mov     r9d, 10134h; uType
0x1800161ed  mov     [rsp+68h+lpString2], rax; hAppInst
0x1800161f2  lea     r8d, [rdx+1]; unsigned int
0x1800161f6  call    MsgPopup
0x1800161fb  cmp     eax, 7
0x1800161fe  mov     ecx, r13d
0x180016201  setnz   cl
0x180016204  mov     eax, ecx
0x180016206  jmp     short loc_180016211
0x180016208  mov     eax, 1
0x18001620d  jmp     short loc_180016211
0x18001620f  xor     eax, eax
0x180016211  add     rsp, 30h
0x180016215  pop     r15
0x180016217  pop     r14
0x180016219  pop     r13
0x18001621b  pop     rdi
0x18001621c  pop     rsi
0x18001621d  pop     rbp
0x18001621e  pop     rbx
0x18001621f  retn
```
