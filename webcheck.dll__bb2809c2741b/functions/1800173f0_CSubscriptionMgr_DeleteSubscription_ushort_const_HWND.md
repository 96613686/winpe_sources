# CSubscriptionMgr::DeleteSubscription(ushort const *,HWND__ *)

- ea: `0x1800173f0`
- end: `0x180017492`
- name: `?DeleteSubscription@CSubscriptionMgr@@UEAAJPEBGPEAUHWND__@@@Z`
- size: `162`
- prototype: `int(CSubscriptionMgr *__hidden this, const unsigned __int16 *, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180003950`
- `0x18000b880`
- `0x18000e28c`
- `0x1800173f0`
- `0x18001c10c`
- `0x18001d420`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180017473`
- `ole32!CoTaskMemFree` at `0x180017473`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::DeleteSubscription(CSubscriptionMgr *this, const unsigned __int16 *a2, HWND a3)
{
  __int64 v4; // r11
  LPCITEMIDLIST *v5; // rbx
  int v7; // edi

  StringCchCopyW((unsigned __int16 *)this + 24, 0x824u, a2);
  v5 = (LPCITEMIDLIST *)(v4 + 24);
  if ( !*(_QWORD *)(v4 + 24) && ((unsigned int)LoadSubscription(v4 + 48, v4 + 24) || !*v5)
    || !(unsigned int)ConfirmDelete(a3) )
  {
    return 2147500037LL;
  }
  v7 = DoDeleteSubscription((struct OOEntry *)(*v5)[2].mkid.abID);
  if ( v7 >= 0 )
  {
    GenerateEvent(4, *v5);
    CoTaskMemFree((LPVOID)*v5);
    *v5 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800173f0  mov     [rsp+arg_0], rbx
0x1800173f5  mov     [rsp+arg_8], rsi
0x1800173fa  push    rdi
0x1800173fb  sub     rsp, 20h
0x1800173ff  mov     rsi, r8
0x180017402  mov     r11, rcx
0x180017405  mov     r8, rdx; unsigned __int16 *
0x180017408  add     rcx, 30h ; '0'; unsigned __int16 *
0x18001740c  mov     edx, 824h; unsigned __int64
0x180017411  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017416  lea     rbx, [r11+18h]
0x18001741a  cmp     qword ptr [rbx], 0
0x18001741e  jnz     short loc_180017436
0x180017420  mov     rdx, rbx
0x180017423  lea     rcx, [r11+30h]
0x180017427  call    LoadSubscription
0x18001742c  test    eax, eax
0x18001742e  jnz     short loc_18001744A
0x180017430  cmp     qword ptr [rbx], 0
0x180017434  jz      short loc_18001744A
0x180017436  mov     r8, rbx
0x180017439  mov     edx, 1
0x18001743e  mov     rcx, rsi; hWnd
0x180017441  call    ConfirmDelete
0x180017446  test    eax, eax
0x180017448  jnz     short loc_180017451
0x18001744a  mov     eax, 80004005h
0x18001744f  jmp     short loc_180017482
0x180017451  mov     rcx, [rbx]
0x180017454  add     rcx, 8; struct OOEntry *
0x180017458  call    ?DoDeleteSubscription@@YAJPEFAUOOEntry@@@Z; DoDeleteSubscription(OOEntry *)
0x18001745d  mov     edi, eax
0x18001745f  test    eax, eax
0x180017461  js      short loc_180017480
0x180017463  mov     rdx, [rbx]; pidl2
0x180017466  mov     ecx, 4; wEventId
0x18001746b  call    _GenerateEvent
0x180017470  mov     rcx, [rbx]; pv
0x180017473  call    cs:__imp_CoTaskMemFree
0x180017479  mov     qword ptr [rbx], 0
0x180017480  mov     eax, edi
0x180017482  mov     rbx, [rsp+28h+arg_0]
0x180017487  mov     rsi, [rsp+28h+arg_8]
0x18001748c  add     rsp, 20h
0x180017490  pop     rdi
0x180017491  retn
```
