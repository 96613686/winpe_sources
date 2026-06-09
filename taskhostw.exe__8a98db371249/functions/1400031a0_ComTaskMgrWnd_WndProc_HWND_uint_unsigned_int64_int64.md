# ComTaskMgrWnd::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1400031a0`
- end: `0x140003246`
- name: `?WndProc@ComTaskMgrWnd@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `166`
- prototype: `LRESULT __fastcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400031a0`
- `0x140003880`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostQuitMessage` at `0x1400031f3`
- `ext-ms-win-ntuser-message-l1-1-0!PostQuitMessage` at `0x1400031f3`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1400031cf`

## pseudocode

```c
LRESULT __fastcall ComTaskMgrWnd::WndProc(HWND a1, UINT a2, WPARAM a3, LPARAM a4)
{
  switch ( a2 )
  {
    case 1u:
    case 0xCu:
      return 0;
    case 2u:
      PostQuitMessage(0);
      return 0;
    case 0x11u:
    case 0x16u:
      ComTaskMgrWnd::Shutdown((RTL_SRWLOCK *)ComTaskMgrBase::s_pVirtualSingleton, a2 == 17);
      return DefWindowProcW(a1, a2, a3, a4);
    default:
      return DefWindowProcW(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x1400031a0  push    rbx
0x1400031a2  push    rbp
0x1400031a3  push    rsi
0x1400031a4  push    rdi
0x1400031a5  sub     rsp, 28h
0x1400031a9  lea     eax, [rdx-1]; switch 22 cases
0x1400031ac  mov     rdi, r9
0x1400031af  mov     rsi, r8
0x1400031b2  mov     ebx, edx
0x1400031b4  mov     rbp, rcx
0x1400031b7  cmp     eax, 15h
0x1400031ba  jbe     short loc_1400031D6
0x1400031bc  mov     r9, rdi; jumptable 00000001400031EF default case, cases 3-11,13-16,18-21
0x1400031bf  mov     r8, rsi
0x1400031c2  mov     edx, ebx
0x1400031c4  mov     rcx, rbp
0x1400031c7  add     rsp, 28h
0x1400031cb  pop     rdi
0x1400031cc  pop     rsi
0x1400031cd  pop     rbp
0x1400031ce  pop     rbx
0x1400031cf  jmp     cs:__imp_DefWindowProcW
0x1400031d6  lea     rcx, __ImageBase
0x1400031dd  movzx   eax, ds:(byte_140003230 - 140000000h)[rcx+rax]
0x1400031e5  mov     edx, ds:(jpt_1400031EF - 140000000h)[rcx+rax*4]
0x1400031ec  add     rdx, rcx
0x1400031ef  jmp     rdx; switch jump
0x1400031f1  xor     ecx, ecx; jumptable 00000001400031EF case 2
0x1400031f3  call    cs:__imp_PostQuitMessage
0x1400031f9  xor     eax, eax; jumptable 00000001400031EF cases 1,12
0x1400031fb  add     rsp, 28h
0x1400031ff  pop     rdi
0x140003200  pop     rsi
0x140003201  pop     rbp
0x140003202  pop     rbx
0x140003203  retn
0x140003204  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; jumptable 00000001400031EF cases 17,22
0x14000320b  xor     edx, edx
0x14000320d  cmp     ebx, 11h
0x140003210  setz    dl; int
0x140003213  call    ?Shutdown@ComTaskMgrWnd@@AEAAJH@Z; ComTaskMgrWnd::Shutdown(int)
0x140003218  jmp     short def_1400031EF; jumptable 00000001400031EF default case, cases 3-11,13-16,18-21
```
