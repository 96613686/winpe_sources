# CWcnPageProfileCreateNew::ShowBadPassphrasePopup(int,int,int)

- ea: `0x180015bc8`
- end: `0x180015d21`
- name: `?ShowBadPassphrasePopup@CWcnPageProfileCreateNew@@AEAAXHHH@Z`
- size: `345`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800153e8`

## callees

- `0x180001820`
- `0x18000e19c`
- `0x180015b1c`
- `0x180015bc8`
- `0x18001f6b8`

## import_xrefs

- `USER32!SendMessageW` at `0x180015cc9`
- `USER32!SendMessageW` at `0x180015cf0`
- `USER32!SendMessageW` at `0x180015cc9`
- `USER32!SendMessageW` at `0x180015cf0`
- `USER32!GetDlgItem` at `0x180015cdb`
- `USER32!GetDlgItem` at `0x180015cdb`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::ShowBadPassphrasePopup(CWcnPageProfileCreateNew *this, __int64 a2, UINT a3)
{
  int String; // eax
  _QWORD *v6; // r10
  __int64 v7; // rdx
  HWND v8; // rcx
  HWND DlgItem; // rax
  LPARAM lParam[2]; // [rsp+20h] [rbp-638h] BYREF
  __int128 v11; // [rsp+30h] [rbp-628h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-618h] BYREF
  WCHAR v13[512]; // [rsp+240h] [rbp-418h] BYREF

  *(_OWORD *)lParam = 0;
  v11 = 0;
  String = WcnUxLoadString(0xCFDu, 0x100u, Buffer);
  if ( String >= 0 )
  {
    String = WcnUxLoadString(a3, 0x200u, v13);
    if ( String >= 0 )
    {
      v8 = (HWND)*((_QWORD *)this + 39);
      lParam[1] = (LPARAM)Buffer;
      LODWORD(lParam[0]) = 32;
      *(_QWORD *)&v11 = v13;
      DWORD2(v11) = 3;
      SendMessageW(v8, 0x1503u, 0, (LPARAM)lParam);
      DlgItem = GetDlgItem(*((HWND *)this + 21), 2918);
      SendMessageW(DlgItem, 0xF1u, 1u, 0);
      CWcnPageProfileCreateNew::SetLowerPaneActive(this, 1);
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 31;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 30;
LABEL_5:
      WPP_SF_d(v6[2], v7, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, (unsigned int)String);
    }
  }
}

```

## disassembly

```asm
0x180015bc8  mov     [rsp+arg_8], rbx
0x180015bcd  push    rdi
0x180015bce  sub     rsp, 650h
0x180015bd5  mov     rax, cs:__security_cookie
0x180015bdc  xor     rax, rsp
0x180015bdf  mov     [rsp+658h+var_18], rax
0x180015be7  xorps   xmm0, xmm0
0x180015bea  mov     ebx, r8d
0x180015bed  mov     rdi, rcx
0x180015bf0  lea     r8, [rsp+658h+Buffer]; lpBuffer
0x180015bf5  mov     ecx, 0CFDh; uID
0x180015bfa  mov     edx, 100h; cchBufferMax
0x180015bff  movups  xmmword ptr [rsp+658h+lParam], xmm0
0x180015c04  movups  [rsp+658h+var_628], xmm0
0x180015c09  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180015c0e  test    eax, eax
0x180015c10  jns     short loc_180015C51
0x180015c12  mov     r10, cs:WPP_GLOBAL_Control
0x180015c19  lea     rcx, WPP_GLOBAL_Control
0x180015c20  cmp     r10, rcx
0x180015c23  jz      loc_180015D00
0x180015c29  cmp     byte ptr [r10+19h], 2
0x180015c2e  jb      loc_180015D00
0x180015c34  mov     edx, 1Eh
0x180015c39  mov     rcx, [r10+10h]
0x180015c3d  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015c44  mov     r9d, eax
0x180015c47  call    WPP_SF_d
0x180015c4c  jmp     loc_180015D00
0x180015c51  lea     r8, [rsp+658h+var_418]; lpBuffer
0x180015c59  mov     edx, 200h; cchBufferMax
0x180015c5e  mov     ecx, ebx; uID
0x180015c60  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180015c65  test    eax, eax
0x180015c67  jns     short loc_180015C8E
0x180015c69  mov     r10, cs:WPP_GLOBAL_Control
0x180015c70  lea     rcx, WPP_GLOBAL_Control
0x180015c77  cmp     r10, rcx
0x180015c7a  jz      loc_180015D00
0x180015c80  cmp     byte ptr [r10+19h], 2
0x180015c85  jb      short loc_180015D00
0x180015c87  mov     edx, 1Fh
0x180015c8c  jmp     short loc_180015C39
0x180015c8e  mov     rcx, [rdi+138h]; hWnd
0x180015c95  lea     rax, [rsp+658h+Buffer]
0x180015c9a  mov     [rsp+658h+lParam+8], rax
0x180015c9f  lea     r9, [rsp+658h+lParam]; lParam
0x180015ca4  lea     rax, [rsp+658h+var_418]
0x180015cac  mov     dword ptr [rsp+658h+lParam], 20h ; ' '
0x180015cb4  xor     r8d, r8d; wParam
0x180015cb7  mov     qword ptr [rsp+658h+var_628], rax
0x180015cbc  mov     edx, 1503h; Msg
0x180015cc1  mov     dword ptr [rsp+658h+var_628+8], 3
0x180015cc9  call    cs:__imp_SendMessageW
0x180015ccf  mov     rcx, [rdi+0A8h]; hDlg
0x180015cd6  mov     edx, 0B66h; nIDDlgItem
0x180015cdb  call    cs:__imp_GetDlgItem
0x180015ce1  xor     r9d, r9d; lParam
0x180015ce4  mov     edx, 0F1h; Msg
0x180015ce9  mov     rcx, rax; hWnd
0x180015cec  lea     r8d, [r9+1]; wParam
0x180015cf0  call    cs:__imp_SendMessageW
0x180015cf6  mov     dl, 1; bool
0x180015cf8  mov     rcx, rdi; this
0x180015cfb  call    ?SetLowerPaneActive@CWcnPageProfileCreateNew@@AEAAX_N@Z; CWcnPageProfileCreateNew::SetLowerPaneActive(bool)
0x180015d00  mov     rcx, [rsp+658h+var_18]
0x180015d08  xor     rcx, rsp; StackCookie
0x180015d0b  call    __security_check_cookie
0x180015d10  mov     rbx, [rsp+658h+arg_8]
0x180015d18  add     rsp, 650h
0x180015d1f  pop     rdi
0x180015d20  retn
```
