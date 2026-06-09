# Threading::ManualEvent::ManualEvent(bool)

- ea: `0x14006752c`
- end: `0x14006758c`
- name: `??0ManualEvent@Threading@@QEAA@_N@Z`
- size: `96`
- prototype: `Threading::ManualEvent *__fastcall(Threading::ManualEvent *this, unsigned __int8)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14003fed0`
- `0x140040b24`
- `0x1400595ec`
- `0x140090810`

## callees

- `0x1400673fc`
- `0x14006752c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140067573`
- `KERNEL32!CloseHandle` at `0x140067573`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067546`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140067546`

## pseudocode

```c
Threading::ManualEvent *__fastcall Threading::ManualEvent::ManualEvent(
        Threading::ManualEvent *this,
        unsigned __int8 a2)
{
  HANDLE hObject; // [rsp+30h] [rbp+8h] BYREF

  hObject = this;
  hObject = CreateEventW(0, 1, a2, 0);
  Threading::Event::Event(this, (__int64 *)&hObject);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  *(_QWORD *)this = &Threading::ManualEvent::`vftable';
  return this;
}

```

## disassembly

```asm
0x14006752c  mov     [rsp+hObject], rcx
0x140067531  push    rbx
0x140067532  sub     rsp, 20h
0x140067536  mov     rbx, rcx
0x140067539  movzx   r8d, dl; bInitialState
0x14006753d  xor     r9d, r9d; lpName
0x140067540  lea     edx, [r9+1]; bManualReset
0x140067544  xor     ecx, ecx; lpEventAttributes
0x140067546  call    cs:__imp_CreateEventW
0x14006754c  mov     [rsp+28h+hObject], rax
0x140067551  lea     rdx, [rsp+28h+hObject]
0x140067556  mov     rcx, rbx
0x140067559  call    ??0Event@Threading@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@std@@@Z; Threading::Event::Event(std::unique_ptr<void,Private::HandleClose> &&)
0x14006755e  nop
0x14006755f  mov     rcx, [rsp+28h+hObject]; hObject
0x140067564  test    rcx, rcx
0x140067567  jz      short loc_140067579
0x140067569  lea     rax, [rcx-1]
0x14006756d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140067571  ja      short loc_140067579
0x140067573  call    cs:__imp_CloseHandle
0x140067579  lea     rax, ??_7ManualEvent@Threading@@6B@; const Threading::ManualEvent::`vftable'
0x140067580  mov     [rbx], rax
0x140067583  mov     rax, rbx
0x140067586  add     rsp, 20h
0x14006758a  pop     rbx
0x14006758b  retn
```
