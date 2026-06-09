# MenuLoadChicagoTemplates(MENUITEMTEMPLATE2 *,HMENU__ * *,ushort,uint)

- ea: `0x180030c38`
- end: `0x180030e98`
- name: `?MenuLoadChicagoTemplates@@YAPEAUMENUITEMTEMPLATE2@@PEAU1@PEAPEAUHMENU__@@GI@Z`
- size: `608`
- prototype: `struct MENUITEMTEMPLATE2 *__fastcall(struct MENUITEMTEMPLATE2 *, HMENU *, unsigned __int16, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180030a10`
- `0x180030c38`

## callees

- `0x180030c38`
- `0x180096dc5`

## import_xrefs

- `win32u!NtUserSetMenuFlagRtoL` at `0x180030e6a`
- `win32u!NtUserSetMenuFlagRtoL` at `0x180030e6a`
- `win32u!NtUserThunkedMenuItemInfo` at `0x180030d9e`
- `win32u!NtUserThunkedMenuItemInfo` at `0x180030d9e`
- `win32u!NtUserCreateMenu` at `0x180030c7b`
- `win32u!NtUserCreateMenu` at `0x180030c7b`
- `win32u!NtUserSetMenuContextHelpId` at `0x180030e42`
- `win32u!NtUserSetMenuContextHelpId` at `0x180030e42`
- `win32u!NtUserDestroyMenu` at `0x180030e28`
- `win32u!NtUserDestroyMenu` at `0x180030e90`
- `win32u!NtUserDestroyMenu` at `0x180030e28`
- `win32u!NtUserDestroyMenu` at `0x180030e90`
- `ntdll!RtlSetLastWin32Error` at `0x180030e1c`
- `ntdll!RtlSetLastWin32Error` at `0x180030e1c`
- `ntdll!RtlInitUnicodeString` at `0x180030d29`
- `ntdll!RtlInitUnicodeString` at `0x180030d29`

## pseudocode

```c
struct MENUITEMTEMPLATE2 *__fastcall MenuLoadChicagoTemplates(
        struct MENUITEMTEMPLATE2 *a1,
        HMENU *a2,
        char a3,
        unsigned int a4)
{
  HMENU Menu; // r14
  unsigned int v9; // esi
  __int16 v10; // bx
  struct MENUITEMTEMPLATE2 *v11; // r15
  int v12; // ecx
  int v13; // ebx
  const WCHAR *v14; // rsi
  unsigned int v15; // eax
  int v17; // [rsp+30h] [rbp-59h]
  HMENU v18; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  int v20; // [rsp+50h] [rbp-39h] BYREF
  int v21; // [rsp+54h] [rbp-35h]
  unsigned int v22; // [rsp+58h] [rbp-31h]
  int v23; // [rsp+5Ch] [rbp-2Dh]
  int v24; // [rsp+60h] [rbp-29h]
  HMENU v25; // [rsp+68h] [rbp-21h]
  const WCHAR *v26; // [rsp+80h] [rbp-9h]
  const WCHAR *v27; // [rsp+88h] [rbp-1h]
  int v28; // [rsp+90h] [rbp+7h]

  v18 = 0;
  memset_0(&v20, 0, 0x50u);
  DestinationString = 0;
  Menu = (HMENU)NtUserCreateMenu();
  if ( Menu )
  {
    while ( 1 )
    {
      v9 = 0;
      v10 = a3 & 1;
      if ( v10 )
        v9 = *(_DWORD *)a1;
      v11 = (struct MENUITEMTEMPLATE2 *)((char *)a1 - 4);
      if ( v10 )
        v11 = a1;
      v17 = *((_DWORD *)v11 + 3);
      memset_0(&v20, 0, 0x50u);
      v12 = 259;
      v20 = 80;
      v21 = 259;
      v22 = *((_DWORD *)v11 + 1) | a4;
      if ( (v22 & 0xFFFC949B) != 0
        || (v23 = *((_DWORD *)v11 + 2), (v23 & 0xFFFFEF74) != 0)
        || (v13 = *((unsigned __int16 *)v11 + 8), (v13 & 0xFFFFFF7E) != 0) )
      {
        RtlSetLastWin32Error(0xDu);
        goto LABEL_27;
      }
      if ( v9 )
      {
        NtUserSetMenuContextHelpId(Menu, v9);
        v12 = v21;
      }
      v14 = (const WCHAR *)((char *)v11 + 18);
      if ( *((_WORD *)v11 + 9) )
        v21 = v12 | 0x40;
      else
        v14 = 0;
      RtlInitUnicodeString(&DestinationString, v14);
      v15 = v22;
      v27 = v14;
      a1 = (struct MENUITEMTEMPLATE2 *)((char *)v11 + ((DestinationString.Length + 3) & 0xFFFFFFFC) + 20);
      if ( (v22 & 0x100) != 0 )
      {
        v21 |= 0x20u;
        v26 = v14;
        v27 = 0;
      }
      if ( (v22 & 0x2000) != 0 )
      {
        a4 = 0x2000;
        NtUserSetMenuFlagRtoL(Menu);
        v15 = v22;
      }
      if ( (v13 & 1) != 0 )
      {
        v21 |= 4u;
        a1 = MenuLoadChicagoTemplates(a1, &v18, 1u, a4);
        if ( !a1 )
          goto LABEL_27;
        v25 = v18;
        v15 = v22;
      }
      if ( (v15 & 4) != 0 )
        v22 = v15 & 0xFFFFBFFB | 0x4000;
      v24 = v17;
      v28 = -1;
      if ( !(unsigned int)NtUserThunkedMenuItemInfo(Menu, 0xFFFFFFFFLL, 1, 1, &v20, &DestinationString) )
        break;
      a3 = v13 & 0xFE;
      if ( a3 < 0 )
      {
        *a2 = Menu;
        return a1;
      }
    }
    if ( (v13 & 1) != 0 )
      NtUserDestroyMenu(v25);
LABEL_27:
    NtUserDestroyMenu(Menu);
  }
  *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180030c38  push    rbp
0x180030c3a  push    rbx
0x180030c3b  push    rsi
0x180030c3c  push    rdi
0x180030c3d  push    r12
0x180030c3f  push    r13
0x180030c41  push    r14
0x180030c43  push    r15
0x180030c45  lea     rbp, [rsp-1Fh]
0x180030c4a  sub     rsp, 0A8h
0x180030c51  xor     r15d, r15d
0x180030c54  movzx   ebx, r8w
0x180030c58  mov     r12, rdx
0x180030c5b  mov     [rbp+57h+var_A8], r15
0x180030c5f  mov     rdi, rcx
0x180030c62  xor     edx, edx; Val
0x180030c64  lea     rcx, [rbp+57h+var_90]; void *
0x180030c68  mov     r13d, r9d
0x180030c6b  lea     r8d, [r15+50h]; Size
0x180030c6f  call    memset_0
0x180030c74  xorps   xmm0, xmm0
0x180030c77  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180030c7b  call    cs:__imp_NtUserCreateMenu
0x180030c81  mov     r14, rax
0x180030c84  test    rax, rax
0x180030c87  jz      loc_180030E2E
0x180030c8d  lea     eax, [r15+1]
0x180030c91  mov     esi, r15d
0x180030c94  and     bx, ax
0x180030c97  jnz     loc_180030E36
0x180030c9d  test    bx, bx
0x180030ca0  lea     r15, [rdi-4]
0x180030ca4  mov     ebx, 50h ; 'P'
0x180030ca9  lea     rcx, [rbp+57h+var_90]; void *
0x180030cad  cmovnz  r15, rdi
0x180030cb1  mov     r8d, ebx; Size
0x180030cb4  xor     edx, edx; Val
0x180030cb6  mov     eax, [r15+0Ch]
0x180030cba  mov     [rbp+57h+var_B0], eax
0x180030cbd  call    memset_0
0x180030cc2  mov     ecx, 103h
0x180030cc7  mov     [rbp+57h+var_90], ebx
0x180030cca  mov     eax, r13d
0x180030ccd  mov     [rbp+57h+var_8C], ecx
0x180030cd0  or      eax, [r15+4]
0x180030cd4  mov     [rbp+57h+var_88], eax
0x180030cd7  test    eax, 0FFFC949Bh
0x180030cdc  jnz     loc_180030E17
0x180030ce2  mov     eax, [r15+8]
0x180030ce6  mov     [rbp+57h+var_84], eax
0x180030ce9  test    eax, 0FFFFEF74h
0x180030cee  jnz     loc_180030E17
0x180030cf4  movzx   ebx, word ptr [r15+10h]
0x180030cf9  test    ebx, 0FFFFFF7Eh
0x180030cff  jnz     loc_180030E17
0x180030d05  xor     edi, edi
0x180030d07  test    esi, esi
0x180030d09  jnz     loc_180030E3D
0x180030d0f  lea     rsi, [r15+12h]
0x180030d13  cmp     [rsi], di
0x180030d16  jz      loc_180030DDC
0x180030d1c  or      ecx, 40h
0x180030d1f  mov     [rbp+57h+var_8C], ecx
0x180030d22  mov     rdx, rsi; SourceString
0x180030d25  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180030d29  call    cs:__imp_RtlInitUnicodeString
0x180030d2f  movzx   edi, [rbp+57h+DestinationString.Length]
0x180030d33  mov     eax, [rbp+57h+var_88]
0x180030d36  add     edi, 3
0x180030d39  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180030d3d  mov     [rbp+57h+var_58], rsi
0x180030d41  add     rdi, 14h
0x180030d45  add     rdi, r15
0x180030d48  bt      eax, 8
0x180030d4c  jb      loc_180030E50
0x180030d52  xor     r15d, r15d
0x180030d55  mov     ecx, 2000h
0x180030d5a  test    ecx, eax
0x180030d5c  jnz     loc_180030E64
0x180030d62  movzx   esi, bx
0x180030d65  mov     ecx, 1
0x180030d6a  and     si, cx
0x180030d6d  jnz     short loc_180030DE4
0x180030d6f  test    al, 4
0x180030d71  jnz     loc_180030E78
0x180030d77  mov     eax, [rbp+57h+var_B0]
0x180030d7a  or      edx, 0FFFFFFFFh
0x180030d7d  mov     [rbp+57h+var_80], eax
0x180030d80  mov     r9d, ecx
0x180030d83  lea     rax, [rbp+57h+DestinationString]
0x180030d87  mov     [rbp+57h+var_50], edx
0x180030d8a  mov     [rsp+0E0h+var_B8], rax
0x180030d8f  mov     r8d, ecx
0x180030d92  lea     rax, [rbp+57h+var_90]
0x180030d96  mov     rcx, r14
0x180030d99  mov     [rsp+0E0h+var_C0], rax
0x180030d9e  call    cs:__imp_NtUserThunkedMenuItemInfo
0x180030da4  test    eax, eax
0x180030da6  jz      loc_180030E87
0x180030dac  mov     eax, 0FFFEh
0x180030db1  and     bx, ax
0x180030db4  mov     eax, 1
0x180030db9  test    bl, bl
0x180030dbb  jns     loc_180030C91
0x180030dc1  mov     [r12], r14
0x180030dc5  mov     rax, rdi
0x180030dc8  add     rsp, 0A8h
0x180030dcf  pop     r15
0x180030dd1  pop     r14
0x180030dd3  pop     r13
0x180030dd5  pop     r12
0x180030dd7  pop     rdi
0x180030dd8  pop     rsi
0x180030dd9  pop     rbx
0x180030dda  pop     rbp
0x180030ddb  retn
0x180030ddc  mov     rsi, rdi
0x180030ddf  jmp     loc_180030D22
0x180030de4  or      [rbp+57h+var_8C], 4
0x180030de8  lea     rdx, [rbp+57h+var_A8]; HMENU *
0x180030dec  mov     r8d, ecx; unsigned __int16
0x180030def  mov     r9d, r13d; unsigned int
0x180030df2  mov     rcx, rdi; struct MENUITEMTEMPLATE2 *
0x180030df5  call    ?MenuLoadChicagoTemplates@@YAPEAUMENUITEMTEMPLATE2@@PEAU1@PEAPEAUHMENU__@@GI@Z; MenuLoadChicagoTemplates(MENUITEMTEMPLATE2 *,HMENU__ * *,ushort,uint)
0x180030dfa  mov     rdi, rax
0x180030dfd  test    rax, rax
0x180030e00  jz      short loc_180030E25
0x180030e02  mov     rax, [rbp+57h+var_A8]
0x180030e06  mov     ecx, 1
0x180030e0b  mov     [rbp+57h+var_78], rax
0x180030e0f  mov     eax, [rbp+57h+var_88]
0x180030e12  jmp     loc_180030D6F
0x180030e17  mov     ecx, 0Dh; LastError
0x180030e1c  call    cs:__imp_RtlSetLastWin32Error
0x180030e22  xor     r15d, r15d
0x180030e25  mov     rcx, r14
0x180030e28  call    cs:__imp_NtUserDestroyMenu
0x180030e2e  mov     [r12], r15
0x180030e32  xor     eax, eax
0x180030e34  jmp     short loc_180030DC8
0x180030e36  mov     esi, [rdi]
0x180030e38  jmp     loc_180030C9D
0x180030e3d  mov     edx, esi
0x180030e3f  mov     rcx, r14
0x180030e42  call    cs:__imp_NtUserSetMenuContextHelpId
0x180030e48  mov     ecx, [rbp+57h+var_8C]
0x180030e4b  jmp     loc_180030D0F
0x180030e50  or      [rbp+57h+var_8C], 20h
0x180030e54  xor     r15d, r15d
0x180030e57  mov     [rbp+57h+var_60], rsi
0x180030e5b  mov     [rbp+57h+var_58], r15
0x180030e5f  jmp     loc_180030D55
0x180030e64  mov     r13d, ecx
0x180030e67  mov     rcx, r14
0x180030e6a  call    cs:__imp_NtUserSetMenuFlagRtoL
0x180030e70  mov     eax, [rbp+57h+var_88]
0x180030e73  jmp     loc_180030D62
0x180030e78  and     eax, 0FFFFFFFBh
0x180030e7b  bts     eax, 0Eh
0x180030e7f  mov     [rbp+57h+var_88], eax
0x180030e82  jmp     loc_180030D77
0x180030e87  test    si, si
0x180030e8a  jz      short loc_180030E25
0x180030e8c  mov     rcx, [rbp+57h+var_78]
0x180030e90  call    cs:__imp_NtUserDestroyMenu
0x180030e96  jmp     short loc_180030E25
```
