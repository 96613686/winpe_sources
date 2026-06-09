# CTrayClock::s_FlyoutThreadProc(void *)

- ea: `0x1800201d0`
- end: `0x1800202b5`
- name: `?s_FlyoutThreadProc@CTrayClock@@CAKPEAX@Z`
- size: `229`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x1800201d0`
- `0x1800202bc`
- `0x18002a010`

## import_xrefs

- `USER32!GetMessageW` at `0x180020215`
- `USER32!GetMessageW` at `0x180020215`
- `USER32!DispatchMessageW` at `0x180020202`
- `USER32!DispatchMessageW` at `0x180020202`
- `USER32!TranslateMessage` at `0x1800201f7`
- `USER32!TranslateMessage` at `0x1800201f7`
- `USER32!DestroyWindow` at `0x180020283`
- `USER32!DestroyWindow` at `0x1800202a2`
- `USER32!DestroyWindow` at `0x180020283`
- `USER32!DestroyWindow` at `0x1800202a2`
- `USER32!SetWindowLongPtrW` at `0x18002027a`
- `USER32!SetWindowLongPtrW` at `0x18002027a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18002026a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18002026a`

## pseudocode

```c
__int64 __fastcall CTrayClock::s_FlyoutThreadProc(int *Parameter)
{
  HWND v2; // rdi
  HWND v3; // rbp
  DirectUI::DUIXmlParser *v4; // rsi
  void (__fastcall *v5)(int *); // rax
  int v6; // r14d
  MSG Msg; // [rsp+20h] [rbp-58h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  while ( GetMessageW(&Msg, 0, 0, 0) )
  {
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  v2 = (HWND)*((_QWORD *)Parameter + 4);
  v3 = (HWND)*((_QWORD *)Parameter + 2);
  v4 = (DirectUI::DUIXmlParser *)*((_QWORD *)Parameter + 11);
  v5 = *(void (__fastcall **)(int *))(*(_QWORD *)Parameter + 16LL);
  v6 = Parameter[19];
  *((_QWORD *)Parameter + 4) = 0;
  *((_QWORD *)Parameter + 2) = 0;
  Parameter[18] = -2147467259;
  *((_QWORD *)Parameter + 11) = 0;
  v5(Parameter);
  if ( v3 )
  {
    if ( v4 )
      DirectUI::DUIXmlParser::Destroy(v4);
    SetWindowLongPtrW(v3, -21, 0);
    DestroyWindow(v3);
  }
  if ( v6 >= 0 )
    CTrayClock::s_Uninitialize();
  Parameter[17] = 0;
  if ( v2 )
    DestroyWindow(v2);
  return 0;
}

```

## disassembly

```asm
0x1800201d0  push    rbx
0x1800201d2  push    rbp
0x1800201d3  push    rsi
0x1800201d4  push    rdi
0x1800201d5  push    r14
0x1800201d7  sub     rsp, 50h
0x1800201db  xorps   xmm0, xmm0
0x1800201de  mov     rbx, rcx
0x1800201e1  movups  xmmword ptr [rsp+78h+Msg.hwnd], xmm0
0x1800201e6  movups  xmmword ptr [rsp+78h+Msg.wParam], xmm0
0x1800201eb  movups  xmmword ptr [rsp+78h+Msg.time], xmm0
0x1800201f0  jmp     short loc_180020208
0x1800201f2  lea     rcx, [rsp+78h+Msg]; lpMsg
0x1800201f7  call    cs:__imp_TranslateMessage
0x1800201fd  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180020202  call    cs:__imp_DispatchMessageW
0x180020208  xor     r9d, r9d; wMsgFilterMax
0x18002020b  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180020210  xor     r8d, r8d; wMsgFilterMin
0x180020213  xor     edx, edx; hWnd
0x180020215  call    cs:__imp_GetMessageW
0x18002021b  test    eax, eax
0x18002021d  jnz     short loc_1800201F2
0x18002021f  mov     rax, [rbx]
0x180020222  mov     rcx, rbx
0x180020225  mov     rdi, [rbx+20h]
0x180020229  mov     rbp, [rbx+10h]
0x18002022d  mov     rsi, [rbx+58h]
0x180020231  mov     rax, [rax+10h]
0x180020235  mov     r14d, [rbx+4Ch]
0x180020239  mov     qword ptr [rbx+20h], 0
0x180020241  mov     qword ptr [rbx+10h], 0
0x180020249  mov     dword ptr [rbx+48h], 80004005h
0x180020250  mov     qword ptr [rbx+58h], 0
0x180020258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002025d  test    rbp, rbp
0x180020260  jz      short loc_180020289
0x180020262  test    rsi, rsi
0x180020265  jz      short loc_180020270
0x180020267  mov     rcx, rsi
0x18002026a  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180020270  xor     r8d, r8d; dwNewLong
0x180020273  mov     rcx, rbp; hWnd
0x180020276  lea     edx, [r8-15h]; nIndex
0x18002027a  call    cs:__imp_SetWindowLongPtrW
0x180020280  mov     rcx, rbp; hWnd
0x180020283  call    cs:__imp_DestroyWindow
0x180020289  test    r14d, r14d
0x18002028c  js      short loc_180020293
0x18002028e  call    ?s_Uninitialize@CTrayClock@@CAXXZ; CTrayClock::s_Uninitialize(void)
0x180020293  mov     dword ptr [rbx+44h], 0
0x18002029a  test    rdi, rdi
0x18002029d  jz      short loc_1800202A8
0x18002029f  mov     rcx, rdi; hWnd
0x1800202a2  call    cs:__imp_DestroyWindow
0x1800202a8  xor     eax, eax
0x1800202aa  add     rsp, 50h
0x1800202ae  pop     r14
0x1800202b0  pop     rdi
0x1800202b1  pop     rsi
0x1800202b2  pop     rbp
0x1800202b3  pop     rbx
0x1800202b4  retn
```
