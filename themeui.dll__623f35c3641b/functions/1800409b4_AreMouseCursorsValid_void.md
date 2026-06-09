# AreMouseCursorsValid(void)

- ea: `0x1800409b4`
- end: `0x180040ab5`
- name: `?AreMouseCursorsValid@@YA_NXZ`
- size: `257`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180040f10`

## callees

- `0x1800358c0`
- `0x1800409b4`

## import_xrefs

- `SHCORE!SHSetValueW` at `0x180040a7d`
- `SHCORE!SHSetValueW` at `0x180040a7d`
- `SHCORE!SHRegGetPathW` at `0x180040a17`
- `SHCORE!SHRegGetPathW` at `0x180040a17`
- `SHLWAPI!PathFileExistsW` at `0x180040a2d`
- `SHLWAPI!PathFileExistsW` at `0x180040a2d`

## pseudocode

```c
char AreMouseCursorsValid(void)
{
  char v0; // bl
  int v1; // edi
  __int64 v2; // rax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  v0 = 1;
  v1 = 0;
  if ( aArrow[0] )
  {
    do
    {
      if ( !v0 )
        break;
      if ( !SHRegGetPathW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", off_18006E940[v1], pszPath, 0) )
      {
        if ( !pszPath[0] || PathFileExistsW(pszPath) )
        {
          v0 = 1;
          v2 = -1;
          do
            ++v2;
          while ( pszPath[v2] );
          SHSetValueW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", off_18006E940[v1], 1u, pszPath, 2 * v2 + 2);
        }
        else
        {
          v0 = 0;
        }
      }
      ++v1;
    }
    while ( *off_18006E940[v1] );
  }
  return v0;
}

```

## disassembly

```asm
0x1800409b4  push    rbx
0x1800409b6  push    rbp
0x1800409b7  push    rsi
0x1800409b8  push    rdi
0x1800409b9  push    r14
0x1800409bb  sub     rsp, 250h
0x1800409c2  mov     rax, cs:__security_cookie
0x1800409c9  xor     rax, rsp
0x1800409cc  mov     [rsp+278h+var_38], rax
0x1800409d4  mov     rax, cs:off_18006E940; "Arrow"
0x1800409db  xor     ebp, ebp
0x1800409dd  mov     bl, 1
0x1800409df  mov     edi, ebp
0x1800409e1  cmp     [rax], bp
0x1800409e4  jz      loc_180040A95
0x1800409ea  lea     r14, off_18006E940; "Arrow"
0x1800409f1  test    bl, bl
0x1800409f3  jz      loc_180040A95
0x1800409f9  movsxd  rsi, edi
0x1800409fc  lea     r9, [rsp+278h+pszPath]; pszPath
0x180040a01  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x180040a08  mov     [rsp+278h+dwFlags], ebp; dwFlags
0x180040a0c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180040a13  mov     r8, [r14+rsi*8]; pcszValue
0x180040a17  call    cs:__imp_SHRegGetPathW
0x180040a1d  test    eax, eax
0x180040a1f  jnz     short loc_180040A83
0x180040a21  cmp     [rsp+278h+pszPath], bp
0x180040a26  jz      short loc_180040A3C
0x180040a28  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180040a2d  call    cs:__imp_PathFileExistsW
0x180040a33  test    eax, eax
0x180040a35  jnz     short loc_180040A3C
0x180040a37  mov     bl, bpl
0x180040a3a  jmp     short loc_180040A83
0x180040a3c  mov     bl, 1
0x180040a3e  lea     rcx, [rsp+278h+pszPath]
0x180040a43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040a47  inc     rax
0x180040a4a  cmp     [rcx+rax*2], bp
0x180040a4e  jnz     short loc_180040A47
0x180040a50  mov     r8, [r14+rsi*8]; pszValue
0x180040a54  lea     eax, ds:2[rax*2]
0x180040a5b  mov     [rsp+278h+cbData], eax; cbData
0x180040a5f  lea     rdx, pcszSubKey; "Control Panel\\Cursors"
0x180040a66  lea     rax, [rsp+278h+pszPath]
0x180040a6b  mov     r9d, 1; dwType
0x180040a71  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180040a78  mov     qword ptr [rsp+278h+dwFlags], rax; pvData
0x180040a7d  call    cs:__imp_SHSetValueW
0x180040a83  inc     edi
0x180040a85  movsxd  rcx, edi
0x180040a88  mov     rcx, [r14+rcx*8]
0x180040a8c  cmp     [rcx], bp
0x180040a8f  jnz     loc_1800409F1
0x180040a95  mov     al, bl
0x180040a97  mov     rcx, [rsp+278h+var_38]
0x180040a9f  xor     rcx, rsp; StackCookie
0x180040aa2  call    __security_check_cookie
0x180040aa7  add     rsp, 250h
0x180040aae  pop     r14
0x180040ab0  pop     rdi
0x180040ab1  pop     rsi
0x180040ab2  pop     rbp
0x180040ab3  pop     rbx
0x180040ab4  retn
```
