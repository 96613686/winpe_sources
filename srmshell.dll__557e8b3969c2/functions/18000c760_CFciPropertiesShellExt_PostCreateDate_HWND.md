# CFciPropertiesShellExt::PostCreateDate(HWND__ *)

- ea: `0x18000c760`
- end: `0x18000c83a`
- name: `?PostCreateDate@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@@Z`
- size: `218`
- prototype: `void __fastcall(CFciPropertiesShellExt *this, HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000c760`
- `0x18000f360`
- `0x18001b420`

## import_xrefs

- `USER32!SendMessageW` at `0x18000c80f`
- `USER32!SendMessageW` at `0x18000c80f`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::PostCreateDate(CFciPropertiesShellExt *this, HWND a2)
{
  _WORD *v2; // r8
  LPARAM *v4; // rax
  __int64 v5; // r9
  __int64 v7; // rdx
  LPARAM *v8; // r8
  unsigned __int16 lParam[208]; // [rsp+20h] [rbp-1B8h] BYREF

  v2 = (_WORD *)((char *)this + 248);
  v4 = (LPARAM *)lParam;
  v5 = 201;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*v2 )
      break;
    *(_WORD *)v4 = *v2++;
    v4 = (LPARAM *)((char *)v4 + 2);
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = (LPARAM *)((char *)v4 - 2);
  if ( v5 )
    v8 = v4;
  *(_WORD *)v8 = 0;
  StringCchCatW(lParam, 0xC9u, L" ");
  StringCchCatW(lParam, 0xC9u, (const unsigned __int16 *)this + 224);
  SendMessageW(a2, 0x1032u, 0, (LPARAM)lParam);
}

```

## disassembly

```asm
0x18000c760  mov     [rsp+arg_10], rbx
0x18000c765  mov     [rsp+arg_18], rsi
0x18000c76a  push    rdi
0x18000c76b  sub     rsp, 1D0h
0x18000c772  mov     rax, cs:__security_cookie
0x18000c779  xor     rax, rsp
0x18000c77c  mov     [rsp+1D8h+var_18], rax
0x18000c784  mov     esi, 0C9h
0x18000c789  lea     r8, [rcx+0F8h]
0x18000c790  mov     rdi, rdx
0x18000c793  lea     rax, [rsp+1D8h+lParam]
0x18000c798  mov     r9d, esi
0x18000c79b  mov     rbx, rcx
0x18000c79e  mov     edx, 7FFFFFFEh
0x18000c7a3  xor     r10d, r10d
0x18000c7a6  test    rdx, rdx
0x18000c7a9  jz      short loc_18000C7C8
0x18000c7ab  movzx   ecx, word ptr [r8]
0x18000c7af  test    cx, cx
0x18000c7b2  jz      short loc_18000C7C8
0x18000c7b4  mov     [rax], cx
0x18000c7b7  add     r8, 2
0x18000c7bb  add     rax, 2
0x18000c7bf  dec     rdx
0x18000c7c2  sub     r9, 1
0x18000c7c6  jnz     short loc_18000C7A6
0x18000c7c8  test    r9, r9
0x18000c7cb  lea     r8, [rax-2]
0x18000c7cf  mov     rdx, rsi; unsigned __int64
0x18000c7d2  lea     rcx, [rsp+1D8h+lParam]; unsigned __int16 *
0x18000c7d7  cmovnz  r8, rax
0x18000c7db  mov     [r8], r10w
0x18000c7df  lea     r8, asc_180022750; " "
0x18000c7e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7eb  lea     r8, [rbx+1C0h]; unsigned __int16 *
0x18000c7f2  mov     rdx, rsi; unsigned __int64
0x18000c7f5  lea     rcx, [rsp+1D8h+lParam]; unsigned __int16 *
0x18000c7fa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7ff  lea     r9, [rsp+1D8h+lParam]; lParam
0x18000c804  xor     r8d, r8d; wParam
0x18000c807  mov     edx, 1032h; Msg
0x18000c80c  mov     rcx, rdi; hWnd
0x18000c80f  call    cs:__imp_SendMessageW
0x18000c815  mov     rcx, [rsp+1D8h+var_18]
0x18000c81d  xor     rcx, rsp; StackCookie
0x18000c820  call    __security_check_cookie
0x18000c825  lea     r11, [rsp+1D8h+var_8]
0x18000c82d  mov     rbx, [r11+20h]
0x18000c831  mov     rsi, [r11+28h]
0x18000c835  mov     rsp, r11
0x18000c838  pop     rdi
0x18000c839  retn
```
