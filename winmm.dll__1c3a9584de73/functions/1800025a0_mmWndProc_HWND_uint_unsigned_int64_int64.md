# mmWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800025a0`
- end: `0x180002790`
- name: `?mmWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `496`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800025a0`

## callees

- `0x1800025a0`
- `0x1800027a0`
- `0x180003684`
- `0x18000b6d4`
- `0x180010efc`
- `0x180011428`
- `0x180019de0`
- `0x18001a110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026b2`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180002689`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180002689`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageA` at `0x1800025f7`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageA` at `0x1800025f7`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcA` at `0x180002716`

## pseudocode

```c
__int64 __fastcall mmWndProc(HWND a1, UINT a2, WPARAM a3, struct tagMCI_SYSTEM_MESSAGE *a4)
{
  __int64 v7; // rax
  DWORD v8; // ecx
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 != 972 )
  {
    if ( a2 > 0x3BD )
    {
      if ( a2 == 970 )
        return (unsigned int)mciRelaySystemString(a4);
      if ( a2 != 973 )
      {
        if ( a2 != 974 )
          return DefWindowProcA(a1, a2, a3, (LPARAM)a4);
        v7 = mmWndProc(0, *(_DWORD *)(a3 + 8), *(_QWORD *)(a3 + 16), *(_QWORD *)(a3 + 24));
        v8 = *(_DWORD *)(a3 + 32);
        *(_QWORD *)a3 = v7;
        PostThreadMessageA(v8, 0x3CFu, 0, 0);
      }
    }
    else
    {
      switch ( a2 )
      {
        case 0x3BDu:
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids);
          }
          WaveOutNotify();
          return 0;
        case 1u:
          hwndNotify = a1;
          return 0;
        case 0x3Du:
          return sndGetObject(a3);
      }
      if ( a2 != 953 )
        return DefWindowProcA(a1, a2, a3, (LPARAM)a4);
      MciNotify(a1, (unsigned int)a4);
    }
    return 0;
  }
  memset(&Msg, 0, sizeof(Msg));
  if ( (a3 & 0x110000) != 0x110000 )
  {
    if ( !PeekMessageA(&Msg, a1, 0x3CDu, 0x3CDu, 0) )
      return (int)sndMessage((unsigned __int16 *)a4);
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids);
    }
    if ( (a3 & 0x80000000) != 0 )
      LocalFree(a4);
    return 0;
  }
  return PlaySoundA((LPCSTR)a4, 0, a3 & 0xFFFFFFFE);
}

```

## disassembly

```asm
0x1800025a0  mov     [rsp+arg_0], rbx
0x1800025a5  push    rdi
0x1800025a6  sub     rsp, 60h
0x1800025aa  mov     rdi, r9
0x1800025ad  mov     rbx, r8
0x1800025b0  cmp     edx, 3CCh
0x1800025b6  jnz     short loc_18000261D
0x1800025b8  xorps   xmm0, xmm0
0x1800025bb  mov     rax, rbx
0x1800025be  and     eax, 110000h
0x1800025c3  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x1800025c8  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x1800025cd  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x1800025d2  cmp     rax, 110000h
0x1800025d8  jz      loc_180002748
0x1800025de  mov     r9d, 3CDh; wMsgFilterMax
0x1800025e4  mov     [rsp+68h+wRemoveMsg], 0; wRemoveMsg
0x1800025ec  mov     rdx, rcx; hWnd
0x1800025ef  mov     r8d, r9d; wMsgFilterMin
0x1800025f2  lea     rcx, [rsp+68h+Msg]; lpMsg
0x1800025f7  call    cs:__imp_PeekMessageA
0x1800025fd  test    eax, eax
0x1800025ff  jnz     loc_180002691
0x180002605  mov     r8d, ebx
0x180002608  mov     rcx, rdi; unsigned __int16 *
0x18000260b  call    sndMessage
0x180002610  cdqe
0x180002612  mov     rbx, [rsp+68h+arg_0]
0x180002617  add     rsp, 60h
0x18000261b  pop     rdi
0x18000261c  retn
0x18000261d  cmp     edx, 3BDh
0x180002623  ja      short loc_18000264B
0x180002625  jnz     loc_1800026BA
0x18000262b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002632  lea     rax, WPP_GLOBAL_Control
0x180002639  cmp     rcx, rax
0x18000263c  jnz     loc_1800026CF
0x180002642  call    WaveOutNotify
0x180002647  xor     eax, eax
0x180002649  jmp     short loc_180002612
0x18000264b  mov     eax, edx
0x18000264d  sub     eax, 3CAh
0x180002652  jz      loc_180002739
0x180002658  sub     eax, 3
0x18000265b  jz      short loc_180002647
0x18000265d  cmp     eax, 1
0x180002660  jnz     loc_18000270C
0x180002666  mov     r9, [r8+18h]; __int64
0x18000266a  xor     ecx, ecx; HWND
0x18000266c  mov     r8, [r8+10h]; unsigned __int64
0x180002670  mov     edx, [rbx+8]; unsigned int
0x180002673  call    ?mmWndProc@@YA_JPEAUHWND__@@I_K_J@Z; mmWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180002678  mov     ecx, [rbx+20h]; idThread
0x18000267b  xor     r9d, r9d; lParam
0x18000267e  xor     r8d, r8d; wParam
0x180002681  mov     [rbx], rax
0x180002684  mov     edx, 3CFh; Msg
0x180002689  call    cs:__imp_PostThreadMessageA
0x18000268f  jmp     short loc_180002647
0x180002691  mov     rcx, cs:WPP_GLOBAL_Control
0x180002698  lea     rax, WPP_GLOBAL_Control
0x18000269f  cmp     rcx, rax
0x1800026a2  jnz     loc_18000275F
0x1800026a8  bt      rbx, 1Fh
0x1800026ad  jnb     short loc_180002647
0x1800026af  mov     rcx, rdi; hMem
0x1800026b2  call    cs:__imp_LocalFree
0x1800026b8  jmp     short loc_180002647
0x1800026ba  mov     eax, edx
0x1800026bc  sub     eax, 1
0x1800026bf  jnz     short loc_180002700
0x1800026c1  mov     cs:hwndNotify, rcx
0x1800026c8  xor     eax, eax
0x1800026ca  jmp     loc_180002612
0x1800026cf  test    dword ptr [rcx+1Ch], 400000h
0x1800026d6  jz      loc_180002642
0x1800026dc  cmp     byte ptr [rcx+19h], 4
0x1800026e0  jb      loc_180002642
0x1800026e6  mov     rcx, [rcx+10h]
0x1800026ea  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x1800026f1  mov     edx, 13h
0x1800026f6  call    WPP_SF_
0x1800026fb  jmp     loc_180002642
0x180002700  sub     eax, 3Ch ; '<'
0x180002703  jz      short loc_180002729
0x180002705  cmp     eax, 37Ch
0x18000270a  jz      short loc_18000271D
0x18000270c  mov     rbx, [rsp+68h+arg_0]
0x180002711  add     rsp, 60h
0x180002715  pop     rdi
0x180002716  jmp     cs:__imp_DefWindowProcA
0x18000271d  mov     edx, edi
0x18000271f  call    MciNotify
0x180002724  jmp     loc_180002647
0x180002729  mov     rdx, rdi
0x18000272c  mov     rcx, rbx; wParam
0x18000272f  call    sndGetObject
0x180002734  jmp     loc_180002612
0x180002739  mov     rcx, rdi; struct tagMCI_SYSTEM_MESSAGE *
0x18000273c  call    mciRelaySystemString
0x180002741  mov     eax, eax
0x180002743  jmp     loc_180002612
0x180002748  and     ebx, 0FFFFFFFEh
0x18000274b  xor     edx, edx; hmod
0x18000274d  mov     r8d, ebx; fdwSound
0x180002750  mov     rcx, rdi; pszSound
0x180002753  call    PlaySoundA
0x180002758  cdqe
0x18000275a  jmp     loc_180002612
0x18000275f  test    dword ptr [rcx+1Ch], 400000h
0x180002766  jz      loc_1800026A8
0x18000276c  cmp     byte ptr [rcx+19h], 4
0x180002770  jb      loc_1800026A8
0x180002776  mov     rcx, [rcx+10h]
0x18000277a  lea     r8, WPP_c5fb3da3b9933c3192700b6086acf07d_Traceguids
0x180002781  mov     edx, 15h
0x180002786  call    WPP_SF_
0x18000278b  jmp     loc_1800026A8
```
