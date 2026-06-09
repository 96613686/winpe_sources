# CWshEnvRegistry::put_Item(ushort *,ushort *)

- ea: `0x18000c6d0`
- end: `0x18000c78f`
- name: `?put_Item@CWshEnvRegistry@@UEAAJPEAG0@Z`
- size: `191`
- prototype: `int(CWshEnvRegistry *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000c6d0`
- `0x18000c8b8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000c730`
- `ADVAPI32!RegSetValueExW` at `0x18000c730`
- `USER32!SendMessageTimeoutA` at `0x18000c781`
- `USER32!SendMessageTimeoutA` at `0x18000c781`

## pseudocode

```c
int __fastcall CWshEnvRegistry::put_Item(HKEY *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  const unsigned __int16 *lpData; // r9
  const unsigned __int16 *v4; // r10
  __int64 v5; // rax
  int result; // eax
  bool v7; // sf
  ULONG_PTR dwResult; // [rsp+58h] [rbp+10h] BYREF

  lpData = &psz;
  v4 = &psz;
  if ( a2 )
    v4 = a2;
  if ( a3 )
    lpData = a3;
  if ( !Global::g_fWindowsNT )
  {
    result = CWshEnvRegistry::put_ItemA(this, v4, lpData);
    goto LABEL_14;
  }
  if ( lpData )
  {
    v5 = -1;
    do
      ++v5;
    while ( lpData[v5] );
  }
  else
  {
    LODWORD(v5) = 0;
  }
  result = RegSetValueExW(this[9], v4, 0, 2u, (const BYTE *)lpData, 2 * v5 + 2);
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
LABEL_14:
    v7 = result < 0;
  }
  if ( !v7 )
  {
    dwResult = 0;
    SendMessageTimeoutA(HWND_BROADCAST, 0x1Au, 0, (LPARAM)"Environment", 0, 0x3E8u, &dwResult);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c6d0  push    rbx
0x18000c6d2  sub     rsp, 40h
0x18000c6d6  xor     ebx, ebx
0x18000c6d8  lea     r9, psz
0x18000c6df  test    rdx, rdx
0x18000c6e2  mov     r10, r9
0x18000c6e5  cmovnz  r10, rdx
0x18000c6e9  test    r8, r8
0x18000c6ec  cmovnz  r9, r8
0x18000c6f0  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x18000c6f6  jz      short loc_18000C744
0x18000c6f8  test    r9, r9
0x18000c6fb  jz      short loc_18000C70D
0x18000c6fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c701  inc     rax
0x18000c704  cmp     [r9+rax*2], bx
0x18000c709  jnz     short loc_18000C701
0x18000c70b  jmp     short loc_18000C710
0x18000c70d  mov     rax, rbx
0x18000c710  mov     rcx, [rcx+48h]; hKey
0x18000c714  lea     eax, ds:2[rax*2]
0x18000c71b  mov     [rsp+48h+cbData], eax; cbData
0x18000c71f  xor     r8d, r8d; Reserved
0x18000c722  mov     [rsp+48h+lpData], r9; lpData
0x18000c727  mov     rdx, r10; lpValueName
0x18000c72a  mov     r9d, 2; dwType
0x18000c730  call    cs:__imp_RegSetValueExW
0x18000c736  test    eax, eax
0x18000c738  jle     short loc_18000C751
0x18000c73a  movzx   eax, ax
0x18000c73d  or      eax, 80070000h
0x18000c742  jmp     short loc_18000C74F
0x18000c744  mov     r8, r9; unsigned __int16 *
0x18000c747  mov     rdx, r10; unsigned __int16 *
0x18000c74a  call    ?put_ItemA@CWshEnvRegistry@@AEAAJPEBG0@Z; CWshEnvRegistry::put_ItemA(ushort const *,ushort const *)
0x18000c74f  test    eax, eax
0x18000c751  js      short loc_18000C789
0x18000c753  xor     r8d, r8d; wParam
0x18000c756  mov     [rsp+48h+dwResult], rbx
0x18000c75b  lea     rax, [rsp+48h+dwResult]
0x18000c760  mov     ecx, 0FFFFh; hWnd
0x18000c765  mov     [rsp+48h+lpdwResult], rax; lpdwResult
0x18000c76a  lea     r9, aEnvironment; "Environment"
0x18000c771  mov     [rsp+48h+cbData], 3E8h; uTimeout
0x18000c779  lea     edx, [r8+1Ah]; Msg
0x18000c77d  mov     dword ptr [rsp+48h+lpData], ebx; fuFlags
0x18000c781  call    cs:__imp_SendMessageTimeoutA
0x18000c787  mov     eax, ebx
0x18000c789  add     rsp, 40h
0x18000c78d  pop     rbx
0x18000c78e  retn
```
