# CWcnPageProfileCreateNew::OnEditSsid(ushort,ushort,HWND__ *,int &)

- ea: `0x1800146b0`
- end: `0x18001477b`
- name: `?OnEditSsid@CWcnPageProfileCreateNew@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `203`
- prototype: `__int64 __fastcall(CWcnPageProfileCreateNew *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000bbc0`

## callees

- `0x180001820`
- `0x1800146b0`

## import_xrefs

- `USER32!PostMessageW` at `0x180014746`
- `USER32!PostMessageW` at `0x180014746`
- `USER32!GetWindowTextW` at `0x1800146e8`
- `USER32!GetWindowTextW` at `0x1800146e8`
- `wlanapi!WlanStringToSsid` at `0x180014722`
- `wlanapi!WlanStringToSsid` at `0x180014722`

## pseudocode

```c
__int64 __fastcall CWcnPageProfileCreateNew::OnEditSsid(
        CWcnPageProfileCreateNew *this,
        __int64 a2,
        __int64 a3,
        HWND a4)
{
  char *v4; // rdi
  __int64 v6; // rax
  WPARAM v7; // r8
  int v8; // eax
  _OWORD v10[2]; // [rsp+20h] [rbp-38h] BYREF
  int v11; // [rsp+40h] [rbp-18h]

  v4 = (char *)this + 368;
  GetWindowTextW(*((HWND *)this + 37), (LPWSTR)this + 184, 64);
  v11 = 0;
  v6 = -1;
  memset(v10, 0, sizeof(v10));
  do
    ++v6;
  while ( *(_WORD *)&v4[2 * v6] );
  if ( v6 )
  {
    v8 = WlanStringToSsid(v4, v10);
    v7 = 2;
    if ( v8 )
      v7 = 0;
  }
  else
  {
    v7 = 0;
  }
  PostMessageW(*((HWND *)this + 20), 0x48Bu, v7, 2);
  if ( !*((_BYTE *)this + 666) )
    *((_BYTE *)this + 664) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800146b0  mov     [rsp+arg_8], rbx
0x1800146b5  mov     [rsp+arg_10], rsi
0x1800146ba  push    rdi
0x1800146bb  sub     rsp, 50h
0x1800146bf  mov     rax, cs:__security_cookie
0x1800146c6  xor     rax, rsp
0x1800146c9  mov     [rsp+58h+var_10], rax
0x1800146ce  lea     rdi, [rcx+170h]
0x1800146d5  mov     rbx, rcx
0x1800146d8  mov     rcx, [rcx+128h]; hWnd
0x1800146df  mov     rdx, rdi; lpString
0x1800146e2  mov     r8d, 40h ; '@'; nMaxCount
0x1800146e8  call    cs:__imp_GetWindowTextW
0x1800146ee  xor     eax, eax
0x1800146f0  xorps   xmm0, xmm0
0x1800146f3  mov     [rsp+58h+var_18], eax
0x1800146f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800146fb  xor     esi, esi
0x1800146fd  movups  [rsp+58h+var_38], xmm0
0x180014702  movups  [rsp+58h+var_28], xmm0
0x180014707  inc     rax
0x18001470a  cmp     [rdi+rax*2], si
0x18001470e  jnz     short loc_180014707
0x180014710  test    rax, rax
0x180014713  jnz     short loc_18001471A
0x180014715  mov     r8, rsi
0x180014718  jmp     short loc_180014734
0x18001471a  lea     rdx, [rsp+58h+var_38]
0x18001471f  mov     rcx, rdi
0x180014722  call    cs:__imp_WlanStringToSsid
0x180014728  test    eax, eax
0x18001472a  mov     r8d, 2
0x180014730  cmovnz  r8, rsi; wParam
0x180014734  mov     rcx, [rbx+0A0h]; hWnd
0x18001473b  mov     edx, 48Bh; Msg
0x180014740  mov     r9d, 2; lParam
0x180014746  call    cs:__imp_PostMessageW
0x18001474c  cmp     [rbx+29Ah], sil
0x180014753  jnz     short loc_18001475C
0x180014755  mov     byte ptr [rbx+298h], 1
0x18001475c  xor     eax, eax
0x18001475e  mov     rcx, [rsp+58h+var_10]
0x180014763  xor     rcx, rsp; StackCookie
0x180014766  call    __security_check_cookie
0x18001476b  mov     rbx, [rsp+58h+arg_8]
0x180014770  mov     rsi, [rsp+58h+arg_10]
0x180014775  add     rsp, 50h
0x180014779  pop     rdi
0x18001477a  retn
```
