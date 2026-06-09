# DialogBox2(HWND__ *,HWND__ *,int,int)

- ea: `0x180009710`
- end: `0x180009b9f`
- name: `?DialogBox2@@YA_JPEAUHWND__@@0HH@Z`
- size: `1167`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x18002aafc`

## callees

- `0x180009710`
- `0x180009ba8`
- `0x180009fb0`
- `0x18000a6a0`
- `0x18000abd0`
- `0x18000ae90`
- `0x18000cf20`
- `0x18000d210`
- `0x180015780`
- `0x180043ac0`
- `0x18004dca0`
- `0x1800526a0`

## import_xrefs

- `win32u!NtUserNotifyWinEvent` at `0x1800099c3`
- `win32u!NtUserNotifyWinEvent` at `0x180009ae4`
- `win32u!NtUserNotifyWinEvent` at `0x1800099c3`
- `win32u!NtUserNotifyWinEvent` at `0x180009ae4`
- `win32u!NtUserPostQuitMessage` at `0x180009a6a`
- `win32u!NtUserPostQuitMessage` at `0x180009a6a`
- `win32u!NtUserQueryWindow` at `0x180009af9`
- `win32u!NtUserQueryWindow` at `0x180009af9`
- `win32u!NtUserSetForegroundWindow` at `0x180009b07`
- `win32u!NtUserSetForegroundWindow` at `0x180009b07`
- `win32u!NtUserEnableWindow` at `0x180009b82`
- `win32u!NtUserEnableWindow` at `0x180009b82`
- `win32u!NtUserGetThreadState` at `0x180009ab9`
- `win32u!NtUserGetThreadState` at `0x180009ab9`
- `win32u!NtUserWaitMessage` at `0x1800098ea`
- `win32u!NtUserWaitMessage` at `0x1800098ea`
- `win32u!NtUserShowWindow` at `0x180009991`
- `win32u!NtUserShowWindow` at `0x180009991`
- `win32u!NtUserSetFocus` at `0x180009b93`
- `win32u!NtUserSetFocus` at `0x180009b93`
- `win32u!NtUserDestroyWindow` at `0x180009aa9`
- `win32u!NtUserDestroyWindow` at `0x180009aa9`
- `ntdll!NtYieldExecution` at `0x18000989a`
- `ntdll!NtYieldExecution` at `0x18000989a`

## pseudocode

```c
__int64 __fastcall DialogBox2(HWND hWnd, HWND a2, int a3, int a4)
{
  struct tagWND *v8; // r14
  int v9; // r12d
  HWND Capture; // rax
  __int64 v11; // rax
  int v12; // r15d
  int v13; // r13d
  __int64 v14; // rcx
  struct _TEB *v15; // rdx
  unsigned int v16; // r9d
  SIZE_T v17; // r8
  __int64 v18; // r8
  __int64 result; // rax
  __int64 v20; // rsi
  __int64 v21; // rsi
  tagMSG Msg; // [rsp+40h] [rbp-78h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  if ( hWnd )
  {
    v8 = ValidateHwnd(hWnd);
    if ( v8 )
    {
      v9 = 0;
      Capture = GetCapture();
      if ( Capture )
        SendMessageW(Capture, 0x1Fu, 0, 0);
      v11 = gpsi;
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 37) + 8LL) + 24LL) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 37) + 8LL)
                                                                              + 24LL)
                                                                  & 0xFFFFFFFD
                                                                  | (a3 != 0 ? 2 : 0);
      v12 = *((_BYTE *)v8 + 31) & 0x10;
      v13 = *((_DWORD *)v8 + 7) & 0x100;
      if ( (*(_BYTE *)(v11 + 2188) & 1) != 0
        && (*((_BYTE *)v8 + 31) & 0x10) == 0
        && (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v8 + 37) + 8LL) + 24LL) & 1) == 0 )
      {
        goto LABEL_20;
      }
      while ( 1 )
      {
        v14 = *(_QWORD *)(*((_QWORD *)v8 + 37) + 8LL);
        if ( !v14 || (*(_BYTE *)(v14 + 24) & 1) != 0 )
        {
LABEL_49:
          if ( (*(_DWORD *)(gpsi + 1892) & 0x8000) != 0 )
            NtUserNotifyWinEvent(17, hWnd, 0, 0);
          result = HMValidateHandleNoSecure(hWnd);
          if ( result )
          {
            v20 = *(_QWORD *)(*((_QWORD *)v8 + 37) + 8LL);
            if ( v20 )
              v21 = *(_QWORD *)(v20 + 32);
            else
              v21 = 0;
            NtUserDestroyWindow(hWnd);
            if ( a2 && (unsigned int)NtUserGetThreadState(10) && !NtUserQueryWindow(a2, 7) )
              NtUserSetForegroundWindow(a2);
            return v21;
          }
          return result;
        }
        v15 = NtCurrentTeb();
        v16 = 0;
        v17 = v15->Win32ClientInfo[12];
        if ( v17 )
        {
          if ( ((*(_DWORD *)(v17 + 4) | *(_DWORD *)(v17 + 8)) & 0x3DFF) == 0
            && (*(_BYTE *)v17 & 1) == 0
            && (++v15->Win32ClientInfo[1] < 0x64 || (v15->Win32ClientInfo[3] & 0x40000000000LL) != 0)
            && (v15->Win32ClientInfo[3] & 0x400000000000LL) == 0
            && (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24) - *(_DWORD *)(v17 + 20) <= 0x3E8 )
          {
            if ( (v15->Win32ClientInfo[3] & 0x40000000000LL) != 0 && v15->Win32ClientInfo[1] >= 0x64 )
            {
              v15->Win32ClientInfo[1] = 0;
              NtYieldExecution();
              v16 = 1;
            }
            else
            {
              v16 = 3;
            }
            if ( !NtCurrentTeb()->Win32ClientInfo[61] )
              goto LABEL_20;
          }
        }
        if ( !(unsigned int)_PeekMessage(&Msg, 0, 0, 0, 1u, v16, 0) )
          goto LABEL_20;
        if ( Msg.message == 18 )
        {
          NtUserPostQuitMessage(LODWORD(Msg.wParam));
          goto LABEL_49;
        }
        v9 = 0;
        if ( (*((_BYTE *)v8 + 16) & 0x20) != 0
          && (Msg.message == 258 && LOBYTE(Msg.wParam) == 3
           || Msg.message == 256 && LOBYTE(Msg.wParam) == 45 && GetKeyState(17) < 0) )
        {
          SendMessageW(hWnd, 0x301u, 0, 0);
        }
        if ( !IsDialogMessageW(hWnd, &Msg) )
        {
          TranslateMessage(&Msg);
          DispatchMessageWorker(&Msg, 0, v18);
        }
        if ( !v12 )
        {
          if ( Msg.message == 275 || Msg.message == 280 )
          {
LABEL_34:
            v12 = 1;
            NtUserShowWindow(hWnd, 1);
            UpdateWindow(hWnd);
            if ( (*(_DWORD *)(gpsi + 1892) & 0x8000) != 0 )
              NtUserNotifyWinEvent(16, hWnd, 0, 0);
            goto LABEL_25;
          }
          if ( Msg.message == 260 )
          {
LABEL_20:
            if ( !v12 )
              goto LABEL_34;
            if ( a2 )
            {
              if ( IsWindow(a2) )
              {
                if ( !v13 && !v9 )
                {
                  v9 = 1;
                  SendMessageW(a2, 0x121u, 0, (LPARAM)hWnd);
                  goto LABEL_25;
                }
              }
              else
              {
                a2 = 0;
              }
            }
            if ( !HMValidateHandleNoSecure(hWnd) || (*((_WORD *)v8 + 21) & 0xC000) != 0 )
              goto LABEL_49;
            NtUserWaitMessage();
          }
        }
LABEL_25:
        if ( !HMValidateHandleNoSecure(hWnd) )
          goto LABEL_49;
      }
    }
  }
  if ( a2 )
  {
    if ( !a3 )
    {
      if ( IsWindow(a2) )
      {
        NtUserEnableWindow(a2, 1);
        if ( a4 )
          NtUserSetFocus(a2);
      }
    }
  }
  return -1;
}

```

## disassembly

```asm
0x180009710  push    rbx
0x180009712  push    rbp
0x180009713  push    rsi
0x180009714  push    rdi
0x180009715  push    r12
0x180009717  push    r13
0x180009719  push    r14
0x18000971b  push    r15
0x18000971d  sub     rsp, 78h
0x180009721  xorps   xmm0, xmm0
0x180009724  xor     r15d, r15d
0x180009727  mov     ebp, r9d
0x18000972a  mov     esi, r8d
0x18000972d  mov     rbx, rdx
0x180009730  mov     rdi, rcx
0x180009733  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x180009738  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x18000973d  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x180009742  test    rcx, rcx
0x180009745  jz      loc_180009B5B
0x18000974b  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180009750  mov     r14, rax
0x180009753  test    rax, rax
0x180009756  jz      loc_180009B5B
0x18000975c  mov     r12d, r15d
0x18000975f  call    GetCapture
0x180009764  test    rax, rax
0x180009767  jnz     loc_180009B2C
0x18000976d  mov     rax, [r14+128h]
0x180009774  neg     esi
0x180009776  mov     esi, 1
0x18000977b  mov     rbp, r14
0x18000977e  sbb     ecx, ecx
0x180009780  xor     r10d, r10d
0x180009783  and     ecx, 2
0x180009786  mov     rdx, [rax+8]
0x18000978a  mov     eax, [rdx+18h]
0x18000978d  and     eax, 0FFFFFFFDh
0x180009790  or      ecx, eax
0x180009792  mov     rax, cs:gpsi
0x180009799  mov     [rdx+18h], ecx
0x18000979c  movzx   r15d, byte ptr [r14+1Fh]
0x1800097a1  mov     r13d, [r14+1Ch]
0x1800097a5  and     r15d, 10h
0x1800097a9  and     r13d, 100h
0x1800097b0  test    [rax+88Ch], sil
0x1800097b7  jz      short loc_1800097D3
0x1800097b9  test    r15d, r15d
0x1800097bc  jnz     short loc_1800097D3
0x1800097be  mov     rax, [r14+128h]
0x1800097c5  mov     rcx, [rax+8]
0x1800097c9  test    [rcx+18h], sil
0x1800097cd  jz      loc_1800098B8
0x1800097d3  mov     rax, [r14+128h]
0x1800097da  mov     rcx, [rax+8]
0x1800097de  test    rcx, rcx
0x1800097e1  jz      loc_180009A70
0x1800097e7  test    [rcx+18h], sil
0x1800097eb  jnz     loc_180009A70
0x1800097f1  mov     rdx, gs:30h
0x1800097fa  mov     r9d, r10d
0x1800097fd  mov     r8, [rdx+860h]
0x180009804  test    r8, r8
0x180009807  jz      loc_180009909
0x18000980d  mov     eax, [r8+8]
0x180009811  or      eax, [r8+4]
0x180009815  test    eax, 3DFFh
0x18000981a  jnz     loc_180009909
0x180009820  test    [r8], sil
0x180009823  jnz     loc_180009909
0x180009829  add     [rdx+808h], rsi
0x180009830  cmp     qword ptr [rdx+808h], 64h ; 'd'
0x180009838  jnb     loc_180009A51
0x18000983e  test    dword ptr [rdx+81Ch], 4000h
0x180009848  jnz     loc_180009909
0x18000984e  mov     eax, 7FFE0320h
0x180009853  mov     rax, [rax]
0x180009856  mov     ecx, ds:7FFE0004h
0x18000985d  imul    rcx, rax
0x180009861  shr     rcx, 18h
0x180009865  sub     ecx, [r8+14h]
0x180009869  cmp     ecx, 3E8h
0x18000986f  ja      loc_180009909
0x180009875  test    dword ptr [rdx+81Ch], 400h
0x18000987f  jz      loc_1800099CE
0x180009885  cmp     qword ptr [rdx+808h], 64h ; 'd'
0x18000988d  jb      loc_1800099CE
0x180009893  mov     [rdx+808h], r10
0x18000989a  call    cs:__imp_NtYieldExecution
0x1800098a0  mov     r9d, esi
0x1800098a3  xor     r10d, r10d
0x1800098a6  mov     rax, gs:30h
0x1800098af  cmp     [rax+9E8h], r10
0x1800098b6  jnz     short loc_180009909
0x1800098b8  test    r15d, r15d
0x1800098bb  jz      loc_180009989
0x1800098c1  test    rbx, rbx
0x1800098c4  jnz     loc_1800099D9
0x1800098ca  mov     rcx, rdi
0x1800098cd  call    HMValidateHandleNoSecure
0x1800098d2  test    rax, rax
0x1800098d5  jz      loc_180009A70
0x1800098db  mov     eax, 0C000h
0x1800098e0  test    [rbp+2Ah], ax
0x1800098e4  jnz     loc_180009A70
0x1800098ea  call    cs:__imp_NtUserWaitMessage
0x1800098f0  mov     rcx, rdi
0x1800098f3  call    HMValidateHandleNoSecure
0x1800098f8  xor     r10d, r10d
0x1800098fb  test    rax, rax
0x1800098fe  jnz     loc_1800097D3
0x180009904  jmp     loc_180009A70
0x180009909  mov     [rsp+0B8h+var_88], r10d; int
0x18000990e  lea     rcx, [rsp+0B8h+Msg]; struct tagMSG *
0x180009913  mov     [rsp+0B8h+var_90], r9d; unsigned int
0x180009918  xor     r8d, r8d; unsigned int
0x18000991b  xor     r9d, r9d; unsigned int
0x18000991e  mov     [rsp+0B8h+var_98], esi; unsigned int
0x180009922  xor     edx, edx; HWND
0x180009924  call    ?_PeekMessage@@YAHPEAUtagMSG@@PEAUHWND__@@IIIIH@Z; _PeekMessage(tagMSG *,HWND__ *,uint,uint,uint,uint,int)
0x180009929  xor     r10d, r10d
0x18000992c  test    eax, eax
0x18000992e  jz      short loc_1800098B8
0x180009930  mov     eax, [rsp+0B8h+Msg.message]
0x180009934  cmp     eax, 12h
0x180009937  jz      loc_180009A66
0x18000993d  test    byte ptr [rbp+10h], 20h
0x180009941  mov     r12d, r10d
0x180009944  jnz     loc_180009A18
0x18000994a  lea     rdx, [rsp+0B8h+Msg]; lpMsg
0x18000994f  mov     rcx, rdi; hDlg
0x180009952  call    IsDialogMessageW
0x180009957  test    eax, eax
0x180009959  jnz     short loc_180009971
0x18000995b  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x180009960  call    TranslateMessage
0x180009965  xor     edx, edx
0x180009967  lea     rcx, [rsp+0B8h+Msg]
0x18000996c  call    DispatchMessageWorker
0x180009971  test    r15d, r15d
0x180009974  jnz     loc_1800098F0
0x18000997a  mov     eax, [rsp+0B8h+Msg.message]
0x18000997e  cmp     eax, 113h
0x180009983  jnz     loc_180009B11
0x180009989  mov     edx, esi
0x18000998b  mov     rcx, rdi
0x18000998e  mov     r15d, esi
0x180009991  call    cs:__imp_NtUserShowWindow
0x180009997  mov     rcx, rdi; hWnd
0x18000999a  call    UpdateWindow
0x18000999f  mov     rax, cs:gpsi
0x1800099a6  test    dword ptr [rax+764h], 8000h
0x1800099b0  jz      loc_1800098F0
0x1800099b6  xor     r9d, r9d
0x1800099b9  xor     r8d, r8d
0x1800099bc  mov     rdx, rdi
0x1800099bf  lea     ecx, [r9+10h]
0x1800099c3  call    cs:__imp_NtUserNotifyWinEvent
0x1800099c9  jmp     loc_1800098F0
0x1800099ce  mov     r9d, 3
0x1800099d4  jmp     loc_1800098A6
0x1800099d9  mov     rcx, rbx; hWnd
0x1800099dc  call    IsWindow
0x1800099e1  xor     ecx, ecx
0x1800099e3  test    eax, eax
0x1800099e5  jz      loc_180009B53
0x1800099eb  test    r13d, r13d
0x1800099ee  jnz     loc_1800098CA
0x1800099f4  test    r12d, r12d
0x1800099f7  jnz     loc_1800098CA
0x1800099fd  mov     r9, rdi; lParam
0x180009a00  xor     r8d, r8d; wParam
0x180009a03  mov     edx, 121h; Msg
0x180009a08  mov     rcx, rbx; hWnd
0x180009a0b  mov     r12d, esi
0x180009a0e  call    SendMessageW
0x180009a13  jmp     loc_1800098F0
0x180009a18  cmp     eax, 102h
0x180009a1d  jz      loc_180009B43
0x180009a23  cmp     eax, 100h
0x180009a28  jnz     loc_18000994A
0x180009a2e  cmp     byte ptr [rsp+0B8h+Msg.wParam], 2Dh ; '-'
0x180009a33  jnz     loc_18000994A
0x180009a39  mov     ecx, 11h; nVirtKey
0x180009a3e  call    GetKeyState
0x180009a43  test    ax, ax
0x180009a46  jns     loc_18000994A
0x180009a4c  jmp     loc_1800980E6
0x180009a51  test    dword ptr [rdx+81Ch], 400h
0x180009a5b  jnz     loc_18000983E
0x180009a61  jmp     loc_180009909
0x180009a66  mov     ecx, dword ptr [rsp+0B8h+Msg.wParam]
0x180009a6a  call    cs:__imp_NtUserPostQuitMessage
0x180009a70  mov     rax, cs:gpsi
0x180009a77  test    dword ptr [rax+764h], 8000h
0x180009a81  jnz     short loc_180009AD7
0x180009a83  mov     rcx, rdi
0x180009a86  call    HMValidateHandleNoSecure
0x180009a8b  xor     ebp, ebp
0x180009a8d  test    rax, rax
0x180009a90  jz      short loc_180009B0F
0x180009a92  mov     rax, [r14+128h]
0x180009a99  mov     rsi, [rax+8]
0x180009a9d  test    rsi, rsi
0x180009aa0  jz      short loc_180009AEC
0x180009aa2  mov     rsi, [rsi+20h]
0x180009aa6  mov     rcx, rdi
0x180009aa9  call    cs:__imp_NtUserDestroyWindow
0x180009aaf  test    rbx, rbx
0x180009ab2  jz      short loc_180009AC3
0x180009ab4  mov     ecx, 0Ah
0x180009ab9  call    cs:__imp_NtUserGetThreadState
0x180009abf  test    eax, eax
0x180009ac1  jnz     short loc_180009AF1
0x180009ac3  mov     rax, rsi
0x180009ac6  add     rsp, 78h
0x180009aca  pop     r15
0x180009acc  pop     r14
0x180009ace  pop     r13
0x180009ad0  pop     r12
0x180009ad2  pop     rdi
0x180009ad3  pop     rsi
0x180009ad4  pop     rbp
0x180009ad5  pop     rbx
0x180009ad6  retn
0x180009ad7  xor     r9d, r9d
0x180009ada  xor     r8d, r8d
0x180009add  mov     rdx, rdi
0x180009ae0  lea     ecx, [r9+11h]
0x180009ae4  call    cs:__imp_NtUserNotifyWinEvent
0x180009aea  jmp     short loc_180009A83
0x180009aec  mov     rsi, rbp
0x180009aef  jmp     short loc_180009AA6
0x180009af1  mov     edx, 7
0x180009af6  mov     rcx, rbx
0x180009af9  call    cs:__imp_NtUserQueryWindow
0x180009aff  test    rax, rax
0x180009b02  jnz     short loc_180009AC3
0x180009b04  mov     rcx, rbx
0x180009b07  call    cs:__imp_NtUserSetForegroundWindow
0x180009b0d  jmp     short loc_180009AC3
0x180009b0f  jmp     short loc_180009AC6
0x180009b11  cmp     eax, 118h
0x180009b16  jz      loc_180009989
0x180009b1c  cmp     eax, 104h
0x180009b21  jz      loc_1800098B8
0x180009b27  jmp     loc_1800098F0
0x180009b2c  xor     r9d, r9d; lParam
0x180009b2f  xor     r8d, r8d; wParam
0x180009b32  mov     rcx, rax; hWnd
0x180009b35  lea     edx, [r9+1Fh]; Msg
0x180009b39  call    SendMessageW
0x180009b3e  jmp     loc_18000976D
0x180009b43  cmp     byte ptr [rsp+0B8h+Msg.wParam], 3
0x180009b48  jz      loc_1800980E6
0x180009b4e  jmp     loc_180009A23
0x180009b53  mov     rbx, rcx
0x180009b56  jmp     loc_1800098CA
0x180009b5b  test    rbx, rbx
0x180009b5e  jz      loc_1800980FF
0x180009b64  test    esi, esi
0x180009b66  jnz     loc_1800980FF
0x180009b6c  mov     rcx, rbx; hWnd
0x180009b6f  call    IsWindow
0x180009b74  test    eax, eax
0x180009b76  jz      loc_1800980FF
0x180009b7c  lea     edx, [rsi+1]
0x180009b7f  mov     rcx, rbx
0x180009b82  call    cs:__imp_NtUserEnableWindow
0x180009b88  test    ebp, ebp
0x180009b8a  jz      loc_1800980FF
0x180009b90  mov     rcx, rbx
0x180009b93  call    cs:__imp_NtUserSetFocus
0x180009b99  nop
0x180009b9a  jmp     loc_1800980FF
0x1800980e6  xor     r9d, r9d; lParam
0x1800980e9  xor     r8d, r8d; wParam
0x1800980ec  mov     edx, 301h; Msg
0x1800980f1  mov     rcx, rdi; hWnd
0x1800980f4  call    SendMessageW
0x1800980f9  nop
0x1800980fa  jmp     loc_18000994A
0x1800980ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180098103  jmp     loc_180009AC6
```
