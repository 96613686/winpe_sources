# CTrayClock::ShowFlyout(HWND__ *,tagRECT const *)

- ea: `0x18001f280`
- end: `0x18001f34b`
- name: `?ShowFlyout@CTrayClock@@UEAAJPEAUHWND__@@PEBUtagRECT@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this, HWND, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014db0`
- `0x18001f280`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18001f2f1`
- `SHLWAPI!__imp_SHCreateThread` at `0x18001f2f1`
- `USER32!SetForegroundWindow` at `0x18001f333`
- `USER32!SetForegroundWindow` at `0x18001f333`
- `USER32!FindWindowW` at `0x18001f325`
- `USER32!FindWindowW` at `0x18001f325`
- `USER32!GetWindowBand` at `0x18001f2c9`
- `USER32!GetWindowBand` at `0x18001f2c9`

## pseudocode

```c
__int64 __fastcall CTrayClock::ShowFlyout(CTrayClock *this, HWND a2, const struct tagRECT *a3)
{
  __int128 v6; // xmm0
  unsigned int v7; // edi
  HWND WindowW; // rax
  int v10; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 17) )
  {
    v7 = 0;
    if ( *((int *)this + 18) >= 0 )
    {
      (*(void (__fastcall **)(CTrayClock *))(*(_QWORD *)this + 32LL))(this);
      WindowW = FindWindowW(L"Shell_TrayWnd", 0);
      if ( WindowW )
        SetForegroundWindow(WindowW);
    }
  }
  else
  {
    if ( *((_QWORD *)this + 3) )
      (*(void (__fastcall **)(CTrayClock *))(*(_QWORD *)this + 48LL))(this);
    v6 = (__int128)*a3;
    v10 = 0;
    *((_OWORD *)this + 3) = v6;
    if ( (unsigned int)GetWindowBand(a2, &v10) )
      *((_DWORD *)this + 16) = v10;
    if ( SHCreateThread(
           (LPTHREAD_START_ROUTINE)CTrayClock::s_FlyoutThreadProc,
           this,
           4u,
           (LPTHREAD_START_ROUTINE)CTrayClock::s_FlyoutThreadCreateCallback) )
    {
      return *((unsigned int *)this + 18);
    }
    else
    {
      return (unsigned int)ResultFromLastError();
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001f280  mov     [rsp+arg_8], rbx
0x18001f285  mov     [rsp+arg_10], rsi
0x18001f28a  push    rdi
0x18001f28b  sub     rsp, 20h
0x18001f28f  cmp     dword ptr [rcx+44h], 0
0x18001f293  mov     rdi, r8
0x18001f296  mov     rsi, rdx
0x18001f299  mov     rbx, rcx
0x18001f29c  jnz     short loc_18001F309
0x18001f29e  cmp     qword ptr [rcx+18h], 0
0x18001f2a3  jz      short loc_18001F2B1
0x18001f2a5  mov     rax, [rcx]
0x18001f2a8  mov     rax, [rax+30h]
0x18001f2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b1  movups  xmm0, xmmword ptr [rdi]
0x18001f2b4  lea     rdx, [rsp+28h+arg_0]
0x18001f2b9  mov     [rsp+28h+arg_0], 0
0x18001f2c1  mov     rcx, rsi
0x18001f2c4  movdqu  xmmword ptr [rbx+30h], xmm0
0x18001f2c9  call    cs:__imp_GetWindowBand
0x18001f2cf  test    eax, eax
0x18001f2d1  jz      short loc_18001F2DA
0x18001f2d3  mov     eax, [rsp+28h+arg_0]
0x18001f2d7  mov     [rbx+40h], eax
0x18001f2da  lea     r9, ?s_FlyoutThreadCreateCallback@CTrayClock@@CAKPEAX@Z; pfnCallback
0x18001f2e1  mov     r8d, 4; flags
0x18001f2e7  mov     rdx, rbx; pData
0x18001f2ea  lea     rcx, ?s_FlyoutThreadProc@CTrayClock@@CAKPEAX@Z; pfnThreadProc
0x18001f2f1  call    cs:__imp_SHCreateThread
0x18001f2f7  test    eax, eax
0x18001f2f9  jz      short loc_18001F300
0x18001f2fb  mov     edi, [rbx+48h]
0x18001f2fe  jmp     short loc_18001F339
0x18001f300  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f305  mov     edi, eax
0x18001f307  jmp     short loc_18001F339
0x18001f309  xor     edi, edi
0x18001f30b  cmp     [rcx+48h], edi
0x18001f30e  jl      short loc_18001F339
0x18001f310  mov     rax, [rcx]
0x18001f313  mov     rax, [rax+20h]
0x18001f317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f31c  xor     edx, edx; lpWindowName
0x18001f31e  lea     rcx, ClassName; "Shell_TrayWnd"
0x18001f325  call    cs:__imp_FindWindowW
0x18001f32b  test    rax, rax
0x18001f32e  jz      short loc_18001F339
0x18001f330  mov     rcx, rax; hWnd
0x18001f333  call    cs:__imp_SetForegroundWindow
0x18001f339  mov     rbx, [rsp+28h+arg_8]
0x18001f33e  mov     eax, edi
0x18001f340  mov     rsi, [rsp+28h+arg_10]
0x18001f345  add     rsp, 20h
0x18001f349  pop     rdi
0x18001f34a  retn
```
