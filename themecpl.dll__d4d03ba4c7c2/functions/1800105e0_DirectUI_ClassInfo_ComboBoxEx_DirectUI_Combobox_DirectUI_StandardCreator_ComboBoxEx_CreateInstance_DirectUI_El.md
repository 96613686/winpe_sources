# DirectUI::ClassInfo<ComboBoxEx,DirectUI::Combobox,DirectUI::StandardCreator<ComboBoxEx>>::CreateInstance(DirectUI::Element *,ulong *,DirectUI::Element * *)

- ea: `0x1800105e0`
- end: `0x18001069c`
- name: `?CreateInstance@?$ClassInfo@VComboBoxEx@@VCombobox@DirectUI@@V?$StandardCreator@VComboBoxEx@@@3@@DirectUI@@UEAAJPEAVElement@2@PEAKPEAPEAV32@@Z`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800105e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001061a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001061a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010600`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010600`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180010682`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180010682`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18001065b`
- `DUI70!?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z` at `0x18001065b`
- `DUI70!??0Combobox@DirectUI@@QEAA@XZ` at `0x180010631`
- `DUI70!??0Combobox@DirectUI@@QEAA@XZ` at `0x180010631`

## pseudocode

```c
__int64 __fastcall DirectUI::ClassInfo<ComboBoxEx,DirectUI::Combobox,DirectUI::StandardCreator<ComboBoxEx>>::CreateInstance(
        __int64 a1,
        struct DirectUI::Element *a2,
        unsigned int *a3,
        DirectUI::Combobox **a4)
{
  int v7; // edi
  HANDLE ProcessHeap; // rax
  DirectUI::Combobox *v9; // rax
  DirectUI::Combobox *v10; // rbx

  *a4 = 0;
  v7 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v9 = (DirectUI::Combobox *)HeapAlloc(ProcessHeap, 8u, 0x158u);
  v10 = v9;
  if ( v9 )
  {
    DirectUI::Combobox::Combobox(v9);
    *(_QWORD *)v10 = &ComboBoxEx::`vftable';
    v7 = DirectUI::HWNDHost::Initialize(v10, 0x19u, 3u, a2, a3);
    if ( v7 < 0 )
    {
      DirectUI::Element::Destroy(v10, 1);
    }
    else
    {
      *(_QWORD *)((char *)v10 + 332) = 0;
      *a4 = v10;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800105e0  push    rbx
0x1800105e2  push    rbp
0x1800105e3  push    rsi
0x1800105e4  push    rdi
0x1800105e5  push    r14
0x1800105e7  sub     rsp, 30h
0x1800105eb  mov     rsi, r9
0x1800105ee  mov     qword ptr [r9], 0
0x1800105f5  mov     rbp, r8
0x1800105f8  mov     r14, rdx
0x1800105fb  mov     edi, 8007000Eh
0x180010600  call    cs:__imp_GetProcessHeap
0x180010607  nop     dword ptr [rax+rax+00h]
0x18001060c  mov     edx, 8; dwFlags
0x180010611  mov     r8d, 158h; dwBytes
0x180010617  mov     rcx, rax; hHeap
0x18001061a  call    cs:__imp_HeapAlloc
0x180010621  nop     dword ptr [rax+rax+00h]
0x180010626  mov     rbx, rax
0x180010629  test    rax, rax
0x18001062c  jz      short loc_18001068E
0x18001062e  mov     rcx, rax
0x180010631  call    cs:__imp_??0Combobox@DirectUI@@QEAA@XZ; DirectUI::Combobox::Combobox(void)
0x180010638  nop     dword ptr [rax+rax+00h]
0x18001063d  mov     edx, 19h
0x180010642  mov     [rsp+58h+var_38], rbp
0x180010647  lea     rax, ??_7ComboBoxEx@@6B@; const ComboBoxEx::`vftable'
0x18001064e  mov     r9, r14
0x180010651  mov     rcx, rbx
0x180010654  mov     [rbx], rax
0x180010657  lea     r8d, [rdx-16h]
0x18001065b  call    cs:__imp_?Initialize@HWNDHost@DirectUI@@QEAAJIIPEAVElement@2@PEAK@Z; DirectUI::HWNDHost::Initialize(uint,uint,DirectUI::Element *,ulong *)
0x180010662  nop     dword ptr [rax+rax+00h]
0x180010667  mov     edi, eax
0x180010669  test    eax, eax
0x18001066b  js      short loc_18001067D
0x18001066d  mov     qword ptr [rbx+14Ch], 0
0x180010678  mov     [rsi], rbx
0x18001067b  jmp     short loc_18001068E
0x18001067d  mov     dl, 1
0x18001067f  mov     rcx, rbx
0x180010682  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x180010689  nop     dword ptr [rax+rax+00h]
0x18001068e  mov     eax, edi
0x180010690  add     rsp, 30h
0x180010694  pop     r14
0x180010696  pop     rdi
0x180010697  pop     rsi
0x180010698  pop     rbp
0x180010699  pop     rbx
0x18001069a  retn
```
