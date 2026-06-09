# CEventUI::UploadDlgUpdateState(EVENTUI_STATE,unsigned __int64,unsigned __int64)

- ea: `0x18000899c`
- end: `0x180008b87`
- name: `?UploadDlgUpdateState@CEventUI@@AEAAJW4EVENTUI_STATE@@_K1@Z`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180008760`
- `0x18000899c`

## callees

- `0x180003604`
- `0x180005c20`
- `0x180005c80`
- `0x180006340`
- `0x18000899c`
- `0x180008f3c`
- `0x180009580`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008a54`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008a6c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008ad9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008b1f`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008a54`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008a6c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008ad9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008b1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CEventUI::UploadDlgUpdateState(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  float v8; // xmm0_4
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  unsigned int v12; // edi
  LPARAM lParam[4]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v15[9]; // [rsp+40h] [rbp-48h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v15);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lParam);
  if ( a3 < 0 )
    v8 = (float)(a3 & 1 | (unsigned int)((unsigned __int64)a3 >> 1))
       + (float)(a3 & 1 | (unsigned int)((unsigned __int64)a3 >> 1));
  else
    v8 = (float)(int)a3;
  v9 = v8 * 100.0;
  v10 = 1;
  if ( a4 )
    v10 = a4;
  if ( v10 < 0 )
    v11 = (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1))
        + (float)(v10 & 1 | (unsigned int)((unsigned __int64)v10 >> 1));
  else
    v11 = (float)(int)v10;
  v12 = (int)(float)(v9 / v11);
  if ( !v12 )
    v12 = 1;
  if ( *(_DWORD *)(a1 + 180) != a2 )
  {
    *(_DWORD *)(a1 + 180) = a2;
    SendMessageW(*(HWND *)(a1 + 112), 0x46Bu, 0, 0);
    SendMessageW(*(HWND *)(a1 + 112), 0x469u, 0, 6553600);
  }
  if ( a2 == 3 )
  {
    *(_DWORD *)(a1 + 184) = v12;
  }
  else if ( a2 == 4 )
  {
    *(_DWORD *)(a1 + 184) = 100;
    *(_DWORD *)(a1 + 188) = v12;
  }
  if ( (int)UtilLoadString(v15, 291) >= 0 )
    tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
      lParam,
      v15[0],
      *(unsigned int *)(a1 + 184),
      *(unsigned int *)(a1 + 188));
  SendMessageW(*(HWND *)(a1 + 112), 0x46Cu, 0, lParam[0]);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids, v12);
  SendMessageW(*(HWND *)(a1 + 112), 0x46Au, v12, 0);
  if ( a2 == 3 )
  {
    if ( *(_DWORD *)(a1 + 188) >= 0x64u )
    {
      CEventUI::UploadDlgUpdateState(a1, 4, 0, 1);
      *(_DWORD *)(a1 + 188) = 0;
    }
  }
  else if ( a2 == 4 && *(_DWORD *)(a1 + 188) >= 0x64u )
  {
    CEventUI::DeleteUploadNotifyIcon((CEventUI *)a1);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lParam);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v15);
  return 0;
}

```

## disassembly

```asm
0x18000899c  push    rbx
0x18000899e  push    rbp
0x18000899f  push    rsi
0x1800089a0  push    rdi
0x1800089a1  push    r14
0x1800089a3  sub     rsp, 60h
0x1800089a7  mov     rbp, r9
0x1800089aa  mov     rdi, r8
0x1800089ad  mov     esi, edx
0x1800089af  mov     rbx, rcx
0x1800089b2  lea     rcx, [rsp+88h+var_48]; void *
0x1800089b7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800089bc  nop
0x1800089bd  lea     rcx, [rsp+88h+lParam]; void *
0x1800089c2  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800089c7  nop
0x1800089c8  mov     r14d, 1
0x1800089ce  xorps   xmm0, xmm0
0x1800089d1  test    rdi, rdi
0x1800089d4  js      short loc_1800089DD
0x1800089d6  cvtsi2ss xmm0, rdi
0x1800089db  jmp     short loc_1800089F2
0x1800089dd  mov     rax, rdi
0x1800089e0  shr     rax, 1
0x1800089e3  and     rdi, r14
0x1800089e6  or      rax, rdi
0x1800089e9  cvtsi2ss xmm0, rax
0x1800089ee  addss   xmm0, xmm0
0x1800089f2  mulss   xmm0, cs:__real@42c80000
0x1800089fa  mov     rcx, r14
0x1800089fd  test    rbp, rbp
0x180008a00  cmovnz  rcx, rbp
0x180008a04  xorps   xmm1, xmm1
0x180008a07  test    rcx, rcx
0x180008a0a  js      short loc_180008A13
0x180008a0c  cvtsi2ss xmm1, rcx
0x180008a11  jmp     short loc_180008A28
0x180008a13  mov     rax, rcx
0x180008a16  shr     rax, 1
0x180008a19  and     rcx, r14
0x180008a1c  or      rax, rcx
0x180008a1f  cvtsi2ss xmm1, rax
0x180008a24  addss   xmm1, xmm1
0x180008a28  divss   xmm0, xmm1
0x180008a2c  cvttss2si rdi, xmm0
0x180008a31  test    edi, edi
0x180008a33  cmovz   edi, r14d
0x180008a37  cmp     [rbx+0B4h], esi
0x180008a3d  jz      short loc_180008A72
0x180008a3f  mov     [rbx+0B4h], esi
0x180008a45  xor     r9d, r9d; lParam
0x180008a48  xor     r8d, r8d; wParam
0x180008a4b  mov     edx, 46Bh; Msg
0x180008a50  mov     rcx, [rbx+70h]; hWnd
0x180008a54  call    cs:__imp_SendMessageW
0x180008a5a  mov     r9d, 640000h; lParam
0x180008a60  xor     r8d, r8d; wParam
0x180008a63  mov     edx, 469h; Msg
0x180008a68  mov     rcx, [rbx+70h]; hWnd
0x180008a6c  call    cs:__imp_SendMessageW
0x180008a72  mov     ebp, 4
0x180008a77  cmp     esi, 3
0x180008a7a  jnz     short loc_180008A84
0x180008a7c  mov     [rbx+0B8h], edi
0x180008a82  jmp     short loc_180008A98
0x180008a84  cmp     esi, ebp
0x180008a86  jnz     short loc_180008A98
0x180008a88  mov     dword ptr [rbx+0B8h], 64h ; 'd'
0x180008a92  mov     [rbx+0BCh], edi
0x180008a98  mov     edx, 123h
0x180008a9d  lea     rcx, [rsp+88h+var_48]
0x180008aa2  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x180008aa7  test    eax, eax
0x180008aa9  js      short loc_180008AC8
0x180008aab  mov     r9d, [rbx+0BCh]
0x180008ab2  mov     r8d, [rbx+0B8h]
0x180008ab9  mov     rdx, [rsp+88h+var_48]
0x180008abe  lea     rcx, [rsp+88h+lParam]
0x180008ac3  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180008ac8  mov     r9, [rsp+88h+lParam]; lParam
0x180008acd  xor     r8d, r8d; wParam
0x180008ad0  mov     edx, 46Ch; Msg
0x180008ad5  mov     rcx, [rbx+70h]; hWnd
0x180008ad9  call    cs:__imp_SendMessageW
0x180008adf  lea     rax, WPP_GLOBAL_Control
0x180008ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aed  cmp     rcx, rax
0x180008af0  jz      short loc_180008B10
0x180008af2  test    [rcx+1Ch], bpl
0x180008af6  jz      short loc_180008B10
0x180008af8  mov     edx, 1Eh
0x180008afd  mov     r9d, edi
0x180008b00  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x180008b07  mov     rcx, [rcx+10h]
0x180008b0b  call    WPP_SF_d
0x180008b10  mov     r8d, edi; wParam
0x180008b13  xor     r9d, r9d; lParam
0x180008b16  mov     edx, 46Ah; Msg
0x180008b1b  mov     rcx, [rbx+70h]; hWnd
0x180008b1f  call    cs:__imp_SendMessageW
0x180008b25  cmp     esi, 3
0x180008b28  jnz     short loc_180008B4F
0x180008b2a  cmp     dword ptr [rbx+0BCh], 64h ; 'd'
0x180008b31  jb      short loc_180008B65
0x180008b33  mov     r9, r14
0x180008b36  xor     r8d, r8d
0x180008b39  mov     edx, ebp
0x180008b3b  mov     rcx, rbx
0x180008b3e  call    ?UploadDlgUpdateState@CEventUI@@AEAAJW4EVENTUI_STATE@@_K1@Z; CEventUI::UploadDlgUpdateState(EVENTUI_STATE,unsigned __int64,unsigned __int64)
0x180008b43  mov     dword ptr [rbx+0BCh], 0
0x180008b4d  jmp     short loc_180008B65
0x180008b4f  cmp     esi, ebp
0x180008b51  jnz     short loc_180008B65
0x180008b53  cmp     dword ptr [rbx+0BCh], 64h ; 'd'
0x180008b5a  jb      short loc_180008B65
0x180008b5c  mov     rcx, rbx; this
0x180008b5f  call    ?DeleteUploadNotifyIcon@CEventUI@@AEAAJXZ; CEventUI::DeleteUploadNotifyIcon(void)
0x180008b64  nop
0x180008b65  lea     rcx, [rsp+88h+lParam]
0x180008b6a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008b6f  nop
0x180008b70  lea     rcx, [rsp+88h+var_48]
0x180008b75  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008b7a  xor     eax, eax
0x180008b7c  add     rsp, 60h
0x180008b80  pop     r14
0x180008b82  pop     rdi
0x180008b83  pop     rsi
0x180008b84  pop     rbp
0x180008b85  pop     rbx
0x180008b86  retn
```
