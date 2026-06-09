# CTransitionVisualController::_ShouldMoveOriginalWindowOffscreenForClone(CWindowData *)

- ea: `0x180074cc8`
- end: `0x180074da5`
- name: `?_ShouldMoveOriginalWindowOffscreenForClone@CTransitionVisualController@@IEAA_NPEAVCWindowData@@@Z`
- size: `221`
- prototype: `bool __fastcall(CTransitionVisualController *__hidden this, struct CWindowData *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002cbd0`

## callees

- `0x180074cc8`
- `0x180095130`
- `0x180095b4c`

## import_xrefs

- `USER32!GetPropW` at `0x180074d05`
- `USER32!GetPropW` at `0x180074d05`
- `USER32!GetClassNameW` at `0x180074d3e`
- `USER32!GetClassNameW` at `0x180074d3e`

## string_xrefs

- `0x180074cfe`: `NoAnimationOffscreenMovement`

## pseudocode

```c
char __fastcall CTransitionVisualController::_ShouldMoveOriginalWindowOffscreenForClone(
        CTransitionVisualController *this,
        struct CWindowData *a2)
{
  HWND *v2; // rdi
  char v3; // bl
  __int64 i; // rcx
  WCHAR *v5; // rdx
  int v6; // r8d
  int v7; // eax
  WCHAR ClassName[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( *((_DWORD *)a2 + 32) == 2 || *((_DWORD *)a2 + 32) == 3 )
  {
    v2 = (HWND *)((char *)a2 + 40);
    goto LABEL_6;
  }
  v2 = (HWND *)((char *)a2 + 40);
  if ( (unsigned int)GetPropW(*((HWND *)a2 + 5), L"NoAnimationOffscreenMovement") == 1 )
  {
LABEL_6:
    v3 = 0;
    goto LABEL_7;
  }
  v3 = 1;
LABEL_7:
  memset_0(ClassName, 0, 0x208u);
  if ( v3 && GetClassNameW(*v2, ClassName, 260) )
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      v5 = ClassName;
      do
      {
        v6 = *(WCHAR *)((char *)v5 + (char *)off_1800F2370[i] - (char *)ClassName);
        v7 = *v5 - v6;
        if ( v7 )
          break;
        ++v5;
      }
      while ( v6 );
      if ( !v7 )
        return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180074cc8  mov     [rsp+arg_0], rbx
0x180074ccd  push    rdi
0x180074cce  sub     rsp, 240h
0x180074cd5  mov     rax, cs:__security_cookie
0x180074cdc  xor     rax, rsp
0x180074cdf  mov     [rsp+248h+var_18], rax
0x180074ce7  mov     ecx, [rdx+80h]
0x180074ced  sub     ecx, 2
0x180074cf0  jz      short loc_180074D14
0x180074cf2  cmp     ecx, 1
0x180074cf5  jz      short loc_180074D14
0x180074cf7  lea     rdi, [rdx+28h]
0x180074cfb  mov     rcx, [rdi]; hWnd
0x180074cfe  lea     rdx, aNoanimationoff; "NoAnimationOffscreenMovement"
0x180074d05  call    cs:__imp_GetPropW
0x180074d0b  cmp     eax, 1
0x180074d0e  jz      short loc_180074D18
0x180074d10  mov     bl, 1
0x180074d12  jmp     short loc_180074D1A
0x180074d14  lea     rdi, [rdx+28h]
0x180074d18  xor     bl, bl
0x180074d1a  xor     edx, edx; Val
0x180074d1c  lea     rcx, [rsp+248h+ClassName]; void *
0x180074d21  mov     r8d, 208h; Size
0x180074d27  call    memset_0
0x180074d2c  test    bl, bl
0x180074d2e  jz      short loc_180074D82
0x180074d30  mov     rcx, [rdi]; hWnd
0x180074d33  lea     rdx, [rsp+248h+ClassName]; lpClassName
0x180074d38  mov     r8d, 104h; nMaxCount
0x180074d3e  call    cs:__imp_GetClassNameW
0x180074d44  test    eax, eax
0x180074d46  jz      short loc_180074D82
0x180074d48  xor     ecx, ecx
0x180074d4a  cmp     ecx, 2
0x180074d4d  jnb     short loc_180074D82
0x180074d4f  lea     r9, off_1800F2370; "IPTip_Main_Window"
0x180074d56  mov     r9, [r9+rcx*8]
0x180074d5a  lea     rdx, [rsp+248h+ClassName]
0x180074d5f  sub     r9, rdx
0x180074d62  movzx   eax, word ptr [rdx]
0x180074d65  movzx   r8d, word ptr [rdx+r9]
0x180074d6a  sub     eax, r8d
0x180074d6d  jnz     short loc_180074D78
0x180074d6f  add     rdx, 2
0x180074d73  test    r8d, r8d
0x180074d76  jnz     short loc_180074D62
0x180074d78  test    eax, eax
0x180074d7a  jz      short loc_180074D80
0x180074d7c  inc     ecx
0x180074d7e  jmp     short loc_180074D4A
0x180074d80  xor     bl, bl
0x180074d82  mov     al, bl
0x180074d84  mov     rcx, [rsp+248h+var_18]
0x180074d8c  xor     rcx, rsp; StackCookie
0x180074d8f  call    __security_check_cookie
0x180074d94  mov     rbx, [rsp+248h+arg_0]
0x180074d9c  add     rsp, 240h
0x180074da3  pop     rdi
0x180074da4  retn
```
