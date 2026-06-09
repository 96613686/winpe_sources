# ShellUICommand_OnEditW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x18003fb90`
- end: `0x18003fcfe`
- name: `?ShellUICommand_OnEditW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `366`
- prototype: `void(HWND, HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006f7c`
- `0x180009aec`
- `0x18003f8f4`
- `0x18003fa80`
- `0x18003fb90`
- `0x180091eaa`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x18003fbf4`
- `SHLWAPI!PathFindExtensionW` at `0x18003fbf4`
- `SHLWAPI!StrCmpNIW` at `0x18003fc0d`
- `SHLWAPI!StrCmpNIW` at `0x18003fc35`
- `SHLWAPI!StrCmpNIW` at `0x18003fc0d`
- `SHLWAPI!StrCmpNIW` at `0x18003fc35`
- `ntdll!WinSqmIncrementDWORD` at `0x18003fc50`
- `ntdll!WinSqmIncrementDWORD` at `0x18003fc50`

## pseudocode

```c
void __fastcall ShellUICommand_OnEditW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  WCHAR *v3; // rdi
  unsigned int v4; // r15d
  const unsigned __int16 *i; // rcx
  const WCHAR *ExtensionW; // r14
  const unsigned __int16 *v7; // r14
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rdx
  const WCHAR *v10; // rcx
  const unsigned __int16 *v11; // rsi
  int v12; // [rsp+20h] [rbp-48h] BYREF
  LPCWSTR pszPath[2]; // [rsp+28h] [rbp-40h] BYREF
  int v14; // [rsp+38h] [rbp-30h]
  unsigned int v15; // [rsp+40h] [rbp-28h] BYREF
  LPCWSTR lpParameters[2]; // [rsp+48h] [rbp-20h] BYREF
  int v17; // [rsp+58h] [rbp-10h]

  v3 = 0;
  lpParameters[1] = 0;
  lpParameters[0] = 0;
  v4 = 0;
  v17 = 0;
  pszPath[1] = 0;
  pszPath[0] = 0;
  v14 = 0;
  v12 = 0;
  for ( i = ParseCmdLine(a3, 1, (struct STRW *)&v12); ; i = v11 )
  {
    v11 = ParseCmdLine(i, 1, (struct STRW *)&v12);
    if ( !v11 || !v12 )
      break;
    ExtensionW = PathFindExtensionW(pszPath[0]);
    if ( StrCmpNIW(L".group", ExtensionW, 6) )
    {
      if ( StrCmpNIW(L".contact", ExtensionW, 8) )
        continue;
      v7 = L"/Contact ";
      v8 = 7243;
    }
    else
    {
      v7 = L"/Group ";
      v8 = 7244;
    }
    WinSqmIncrementDWORD(0, v8, 1);
    memset_0(v3, 0, 2LL * v4);
    v15 = 0;
    if ( (int)STRW::Append((STRW *)&v15, v7) < 0 )
      break;
    v9 = &Str;
    if ( v12 )
      v9 = pszPath[0];
    if ( (int)STRW::Append((STRW *)&v15, v9) < 0 )
      break;
    v4 = v15;
    v10 = &Str;
    v3 = (WCHAR *)lpParameters[0];
    if ( v15 )
      v10 = lpParameters[0];
    ExecOpenObject(v10);
  }
  v12 = 0;
  BUFFER::ReleaseStorage((BUFFER *)pszPath);
  v15 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpParameters);
}

```

## disassembly

```asm
0x18003fb90  push    rbp
0x18003fb92  push    rsi
0x18003fb93  push    rdi
0x18003fb94  push    r13
0x18003fb96  push    r14
0x18003fb98  push    r15
0x18003fb9a  mov     rbp, rsp
0x18003fb9d  sub     rsp, 68h
0x18003fba1  xor     edi, edi
0x18003fba3  mov     [rbp+var_18], 0
0x18003fbab  mov     rcx, r8; unsigned __int16 *
0x18003fbae  mov     [rbp+lpParameters], rdi
0x18003fbb2  xor     r15d, r15d
0x18003fbb5  mov     [rbp+var_10], edi
0x18003fbb8  lea     r8, [rbp+var_48]; struct STRW *
0x18003fbbc  mov     [rbp+var_38], rdi
0x18003fbc0  lea     r13d, [rdi+1]
0x18003fbc4  mov     [rbp+pszPath], rdi
0x18003fbc8  mov     edx, r13d; int
0x18003fbcb  mov     [rbp+var_30], edi
0x18003fbce  mov     [rbp+var_48], edi
0x18003fbd1  call    ?ParseCmdLine@@YAPEBGPEBGHPEAVSTRW@@@Z; ParseCmdLine(ushort const *,int,STRW *)
0x18003fbd6  mov     rcx, rax
0x18003fbd9  jmp     loc_18003FCB8
0x18003fbde  cmp     [rbp+var_48], 0
0x18003fbe2  jbe     loc_18003FCD0
0x18003fbe8  lea     rcx, Str
0x18003fbef  cmovnz  rcx, [rbp+pszPath]; pszPath
0x18003fbf4  call    cs:__imp_PathFindExtensionW
0x18003fbfa  mov     r8d, 6; nChar
0x18003fc00  lea     rcx, aGroup_1; ".group"
0x18003fc07  mov     rdx, rax; psz2
0x18003fc0a  mov     r14, rax
0x18003fc0d  call    cs:__imp_StrCmpNIW
0x18003fc13  test    eax, eax
0x18003fc15  jnz     short loc_18003FC25
0x18003fc17  lea     r14, aGroup_2; "/Group "
0x18003fc1e  mov     edx, 1C4Ch
0x18003fc23  jmp     short loc_18003FC4B
0x18003fc25  mov     r8d, 8; nChar
0x18003fc2b  lea     rcx, aContact_2; ".contact"
0x18003fc32  mov     rdx, r14; psz2
0x18003fc35  call    cs:__imp_StrCmpNIW
0x18003fc3b  test    eax, eax
0x18003fc3d  jnz     short loc_18003FCB5
0x18003fc3f  lea     r14, aContact_3; "/Contact "
0x18003fc46  mov     edx, 1C4Bh
0x18003fc4b  mov     r8d, r13d
0x18003fc4e  xor     ecx, ecx
0x18003fc50  call    cs:__imp_WinSqmIncrementDWORD
0x18003fc56  mov     r8d, r15d
0x18003fc59  xor     edx, edx; Val
0x18003fc5b  add     r8, r8; Size
0x18003fc5e  mov     rcx, rdi; void *
0x18003fc61  call    memset_0
0x18003fc66  mov     rdx, r14; unsigned __int16 *
0x18003fc69  mov     [rbp+var_28], 0
0x18003fc70  lea     rcx, [rbp+var_28]; this
0x18003fc74  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18003fc79  test    eax, eax
0x18003fc7b  js      short loc_18003FCD0
0x18003fc7d  cmp     [rbp+var_48], 0
0x18003fc81  lea     rdx, Str
0x18003fc88  lea     rcx, [rbp+var_28]; this
0x18003fc8c  cmovnz  rdx, [rbp+pszPath]; unsigned __int16 *
0x18003fc91  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x18003fc96  test    eax, eax
0x18003fc98  js      short loc_18003FCD0
0x18003fc9a  mov     r15d, [rbp+var_28]
0x18003fc9e  lea     rcx, Str
0x18003fca5  mov     rdi, [rbp+lpParameters]
0x18003fca9  test    r15d, r15d
0x18003fcac  cmovnz  rcx, rdi; lpParameters
0x18003fcb0  call    ExecOpenObject
0x18003fcb5  mov     rcx, rsi; unsigned __int16 *
0x18003fcb8  lea     r8, [rbp+var_48]; struct STRW *
0x18003fcbc  mov     edx, r13d; int
0x18003fcbf  call    ?ParseCmdLine@@YAPEBGPEBGHPEAVSTRW@@@Z; ParseCmdLine(ushort const *,int,STRW *)
0x18003fcc4  mov     rsi, rax
0x18003fcc7  test    rax, rax
0x18003fcca  jnz     loc_18003FBDE
0x18003fcd0  lea     rcx, [rbp+pszPath]; this
0x18003fcd4  mov     [rbp+var_48], 0
0x18003fcdb  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18003fce0  lea     rcx, [rbp+lpParameters]; this
0x18003fce4  mov     [rbp+var_28], 0
0x18003fceb  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18003fcf0  add     rsp, 68h
0x18003fcf4  pop     r15
0x18003fcf6  pop     r14
0x18003fcf8  pop     r13
0x18003fcfa  pop     rdi
0x18003fcfb  pop     rsi
0x18003fcfc  pop     rbp
0x18003fcfd  retn
```
