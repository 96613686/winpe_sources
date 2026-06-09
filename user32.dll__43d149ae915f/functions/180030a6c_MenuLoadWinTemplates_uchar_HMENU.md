# MenuLoadWinTemplates(uchar *,HMENU__ * *)

- ea: `0x180030a6c`
- end: `0x180030c2f`
- name: `?MenuLoadWinTemplates@@YAPEAEPEAEPEAPEAUHMENU__@@@Z`
- size: `451`
- prototype: `unsigned __int8 *__fastcall(unsigned __int8 *, HMENU *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180030a10`
- `0x180030a6c`

## callees

- `0x180030a6c`
- `0x180096dc5`

## import_xrefs

- `win32u!NtUserThunkedMenuItemInfo` at `0x180030b8f`
- `win32u!NtUserThunkedMenuItemInfo` at `0x180030b8f`
- `win32u!NtUserCreateMenu` at `0x180030aa8`
- `win32u!NtUserCreateMenu` at `0x180030aa8`
- `win32u!NtUserDestroyMenu` at `0x180030c15`
- `win32u!NtUserDestroyMenu` at `0x180030c1e`
- `win32u!NtUserDestroyMenu` at `0x180030c15`
- `win32u!NtUserDestroyMenu` at `0x180030c1e`
- `ntdll!RtlInitUnicodeString` at `0x180030ae9`
- `ntdll!RtlInitUnicodeString` at `0x180030ae9`

## pseudocode

```c
unsigned __int8 *__fastcall MenuLoadWinTemplates(unsigned __int8 *a1, HMENU *a2)
{
  HMENU Menu; // r14
  __int16 v5; // bx
  const WCHAR *v6; // rdi
  HMENU v7; // rax
  const WCHAR *v8; // rsi
  int v9; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-49h] BYREF
  int v12; // [rsp+40h] [rbp-39h] BYREF
  int v13; // [rsp+44h] [rbp-35h]
  int v14; // [rsp+48h] [rbp-31h]
  int v15; // [rsp+4Ch] [rbp-2Dh]
  int v16; // [rsp+50h] [rbp-29h]
  HMENU v17; // [rsp+58h] [rbp-21h]
  const WCHAR *v18; // [rsp+70h] [rbp-9h]
  const WCHAR *v19; // [rsp+78h] [rbp-1h]
  int v20; // [rsp+80h] [rbp+7h]
  HMENU v21; // [rsp+F0h] [rbp+77h] BYREF

  v21 = 0;
  memset_0(&v12, 0, 0x50u);
  DestinationString = 0;
  Menu = (HMENU)NtUserCreateMenu();
  if ( Menu )
  {
    while ( 1 )
    {
      v5 = *(_WORD *)a1;
      v6 = (const WCHAR *)(a1 + 2);
      if ( (v5 & 0x10) == 0 )
      {
        v7 = (HMENU)*v6++;
        v21 = v7;
      }
      if ( *v6 )
      {
        v8 = v6;
        RtlInitUnicodeString(&DestinationString, v6);
        v6 = (const WCHAR *)((char *)v6 + DestinationString.Length);
      }
      else
      {
        v8 = 0;
      }
      a1 = (unsigned __int8 *)v6 + (((unsigned __int8)v6 + 2) & 1) + 2;
      memset_0(&v12, 0, 0x50u);
      v9 = 259;
      v12 = 80;
      if ( v8 )
        v9 = 323;
      v13 = v9;
      if ( (v5 & 0x10) != 0 )
      {
        v13 = v9 | 4;
        a1 = MenuLoadWinTemplates(a1, &v21);
        if ( !a1 )
          goto LABEL_21;
        v9 = v13;
        v17 = v21;
      }
      if ( (v5 & 4) != 0 )
        v5 = v5 & 0xBFFB | 0x4000;
      v15 = v5 & 0xB;
      v14 = v5 & 0x6B64;
      if ( (v5 & 0x100) != 0 )
      {
        v18 = v8;
        v13 = v9 | 0x20;
        v8 = 0;
      }
      v16 = (int)v21;
      v19 = v8;
      v20 = -1;
      if ( !(unsigned int)NtUserThunkedMenuItemInfo(
                            Menu,
                            0xFFFFFFFFLL,
                            1,
                            1,
                            &v12,
                            (unsigned __int64)&DestinationString & -(__int64)(v8 != 0)) )
        break;
      if ( (v5 & 0x80u) != 0 )
      {
        *a2 = Menu;
        return a1;
      }
    }
    if ( (v5 & 0x10) != 0 )
      NtUserDestroyMenu(v17);
LABEL_21:
    NtUserDestroyMenu(Menu);
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180030a6c  push    rbp
0x180030a6e  push    rbx
0x180030a6f  push    rsi
0x180030a70  push    rdi
0x180030a71  push    r12
0x180030a73  push    r13
0x180030a75  push    r14
0x180030a77  push    r15
0x180030a79  lea     rbp, [rsp-1Fh]
0x180030a7e  sub     rsp, 98h
0x180030a85  xor     r13d, r13d
0x180030a88  mov     r12, rdx
0x180030a8b  mov     rdi, rcx
0x180030a8e  mov     [rbp+57h+arg_10], r13
0x180030a92  xor     edx, edx; Val
0x180030a94  lea     rcx, [rbp+57h+var_90]; void *
0x180030a98  lea     r8d, [r13+50h]; Size
0x180030a9c  call    memset_0
0x180030aa1  xorps   xmm0, xmm0
0x180030aa4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180030aa8  call    cs:__imp_NtUserCreateMenu
0x180030aae  mov     r14, rax
0x180030ab1  test    rax, rax
0x180030ab4  jz      loc_180030C24
0x180030aba  movzx   ebx, word ptr [rdi]
0x180030abd  add     rdi, 2
0x180030ac1  mov     r15d, ebx
0x180030ac4  and     r15d, 10h
0x180030ac8  jnz     short loc_180030AD5
0x180030aca  movzx   eax, word ptr [rdi]
0x180030acd  add     rdi, 2
0x180030ad1  mov     [rbp+57h+arg_10], rax
0x180030ad5  cmp     [rdi], r13w
0x180030ad9  jz      loc_180030BBC
0x180030adf  mov     rdx, rdi; SourceString
0x180030ae2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030ae6  mov     rsi, rdi
0x180030ae9  call    cs:__imp_RtlInitUnicodeString
0x180030aef  movzx   eax, [rbp+57h+DestinationString.Length]
0x180030af3  add     rdi, rax
0x180030af6  lea     rcx, [rdi+2]
0x180030afa  xor     edx, edx; Val
0x180030afc  mov     rdi, rcx
0x180030aff  and     edi, 1
0x180030b02  add     rdi, rcx
0x180030b05  lea     rcx, [rbp+57h+var_90]; void *
0x180030b09  lea     r8d, [rdx+50h]; Size
0x180030b0d  call    memset_0
0x180030b12  mov     ecx, 103h
0x180030b17  mov     [rbp+57h+var_90], 50h ; 'P'
0x180030b1e  test    rsi, rsi
0x180030b21  lea     eax, [rcx+40h]
0x180030b24  cmovnz  ecx, eax
0x180030b27  mov     [rbp+57h+var_8C], ecx
0x180030b2a  test    r15d, r15d
0x180030b2d  jnz     loc_180030BC4
0x180030b33  test    bl, 4
0x180030b36  jnz     loc_180030BEE
0x180030b3c  mov     eax, ebx
0x180030b3e  and     eax, 0Bh
0x180030b41  mov     [rbp+57h+var_84], eax
0x180030b44  mov     eax, ebx
0x180030b46  and     eax, 6B64h
0x180030b4b  mov     [rbp+57h+var_88], eax
0x180030b4e  bt      ebx, 8
0x180030b52  jb      loc_180030BFA
0x180030b58  mov     eax, dword ptr [rbp+57h+arg_10]
0x180030b5b  lea     rcx, [rbp+57h+DestinationString]
0x180030b5f  mov     [rbp+57h+var_80], eax
0x180030b62  or      edx, 0FFFFFFFFh
0x180030b65  mov     [rbp+57h+var_58], rsi
0x180030b69  mov     r9d, 1
0x180030b6f  neg     rsi
0x180030b72  mov     [rbp+57h+var_50], edx
0x180030b75  mov     r8d, r9d
0x180030b78  sbb     rax, rax
0x180030b7b  and     rax, rcx
0x180030b7e  mov     rcx, r14
0x180030b81  mov     [rsp+0D0h+var_A8], rax
0x180030b86  lea     rax, [rbp+57h+var_90]
0x180030b8a  mov     [rsp+0D0h+var_B0], rax
0x180030b8f  call    cs:__imp_NtUserThunkedMenuItemInfo
0x180030b95  test    eax, eax
0x180030b97  jz      short loc_180030C0C
0x180030b99  test    bl, bl
0x180030b9b  jns     loc_180030ABA
0x180030ba1  mov     [r12], r14
0x180030ba5  mov     rax, rdi
0x180030ba8  add     rsp, 98h
0x180030baf  pop     r15
0x180030bb1  pop     r14
0x180030bb3  pop     r13
0x180030bb5  pop     r12
0x180030bb7  pop     rdi
0x180030bb8  pop     rsi
0x180030bb9  pop     rbx
0x180030bba  pop     rbp
0x180030bbb  retn
0x180030bbc  mov     rsi, r13
0x180030bbf  jmp     loc_180030AF6
0x180030bc4  or      ecx, 4
0x180030bc7  lea     rdx, [rbp+57h+arg_10]; HMENU *
0x180030bcb  mov     [rbp+57h+var_8C], ecx
0x180030bce  mov     rcx, rdi; unsigned __int8 *
0x180030bd1  call    ?MenuLoadWinTemplates@@YAPEAEPEAEPEAPEAUHMENU__@@@Z; MenuLoadWinTemplates(uchar *,HMENU__ * *)
0x180030bd6  mov     rdi, rax
0x180030bd9  test    rax, rax
0x180030bdc  jz      short loc_180030C1B
0x180030bde  mov     rax, [rbp+57h+arg_10]
0x180030be2  mov     ecx, [rbp+57h+var_8C]
0x180030be5  mov     [rbp+57h+var_78], rax
0x180030be9  jmp     loc_180030B33
0x180030bee  and     ebx, 0FFFFFFFBh
0x180030bf1  bts     ebx, 0Eh
0x180030bf5  jmp     loc_180030B3C
0x180030bfa  or      ecx, 20h
0x180030bfd  mov     [rbp+57h+var_60], rsi
0x180030c01  mov     [rbp+57h+var_8C], ecx
0x180030c04  mov     rsi, r13
0x180030c07  jmp     loc_180030B58
0x180030c0c  test    bl, 10h
0x180030c0f  jz      short loc_180030C1B
0x180030c11  mov     rcx, [rbp+57h+var_78]
0x180030c15  call    cs:__imp_NtUserDestroyMenu
0x180030c1b  mov     rcx, r14
0x180030c1e  call    cs:__imp_NtUserDestroyMenu
0x180030c24  mov     [r12], r13
0x180030c28  xor     eax, eax
0x180030c2a  jmp     loc_180030BA8
```
