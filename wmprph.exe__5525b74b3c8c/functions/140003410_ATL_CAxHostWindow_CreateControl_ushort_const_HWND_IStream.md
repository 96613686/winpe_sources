# ATL::CAxHostWindow::CreateControl(ushort const *,HWND__ *,IStream *)

- ea: `0x140003410`
- end: `0x140003467`
- name: `?CreateControl@CAxHostWindow@ATL@@UEAAJPEBGPEAUHWND__@@PEAUIStream@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const unsigned __int16 *, HWND, struct IStream *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003410`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::CreateControl(
        ATL::CAxHostWindow *this,
        const unsigned __int16 *a2,
        HWND a3,
        struct IStream *a4)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(ATL::CAxHostWindow *, const unsigned __int16 *, HWND, struct IStream *, __int64 *, GUID *, _QWORD))(v4 + 32))(
         this,
         a2,
         a3,
         a4,
         &v7,
         &GUID_NULL,
         0);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v5;
}

```

## disassembly

```asm
0x140003410  mov     r11, rsp
0x140003413  push    rbx
0x140003414  sub     rsp, 40h
0x140003418  mov     rax, [rcx]
0x14000341b  lea     r10, GUID_NULL
0x140003422  mov     qword ptr [r11-18h], 0
0x14000342a  mov     [r11-20h], r10
0x14000342e  lea     r10, [r11+8]
0x140003432  mov     qword ptr [r11+8], 0
0x14000343a  mov     rax, [rax+20h]
0x14000343e  mov     [r11-28h], r10
0x140003442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003447  mov     rcx, [rsp+48h+arg_0]
0x14000344c  mov     ebx, eax
0x14000344e  test    rcx, rcx
0x140003451  jz      short loc_14000345F
0x140003453  mov     rdx, [rcx]
0x140003456  mov     rax, [rdx+10h]
0x14000345a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000345f  mov     eax, ebx
0x140003461  add     rsp, 40h
0x140003465  pop     rbx
0x140003466  retn
```
