# CSsdpNotifyRequestManager::HrInitialize(void)

- ea: `0x18000ba40`
- end: `0x18000bab5`
- name: `?HrInitialize@CSsdpNotifyRequestManager@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a768`

## callees

- `0x18000554c`
- `0x18000ba40`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ba5a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ba5a`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrInitialize(CSsdpNotifyRequestManager *this)
{
  unsigned int Win32Error; // edi
  HANDLE EventA; // rax

  Win32Error = 0;
  EventA = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 31) = EventA;
  if ( !EventA )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error )
    {
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, Win32Error);
    }
  }
  return Win32Error;
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_0], rbx
0x18000ba45  push    rdi
0x18000ba46  sub     rsp, 20h
0x18000ba4a  mov     rbx, rcx
0x18000ba4d  xor     edi, edi
0x18000ba4f  xor     r9d, r9d; lpName
0x18000ba52  xor     r8d, r8d; bInitialState
0x18000ba55  xor     ecx, ecx; lpEventAttributes
0x18000ba57  lea     edx, [rdi+1]; bManualReset
0x18000ba5a  call    cs:__imp_CreateEventA
0x18000ba60  mov     [rbx+0F8h], rax
0x18000ba67  test    rax, rax
0x18000ba6a  jnz     short loc_18000BAA8
0x18000ba6c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000ba71  mov     edi, eax
0x18000ba73  test    eax, eax
0x18000ba75  jz      short loc_18000BAA8
0x18000ba77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba7e  lea     rax, WPP_GLOBAL_Control
0x18000ba85  cmp     rcx, rax
0x18000ba88  jz      short loc_18000BAA8
0x18000ba8a  test    byte ptr [rcx+1Ch], 1
0x18000ba8e  jz      short loc_18000BAA8
0x18000ba90  mov     rcx, [rcx+10h]
0x18000ba94  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000ba9b  mov     edx, 54h ; 'T'
0x18000baa0  mov     r9d, edi
0x18000baa3  call    WPP_SF_d
0x18000baa8  mov     rbx, [rsp+28h+arg_0]
0x18000baad  mov     eax, edi
0x18000baaf  add     rsp, 20h
0x18000bab3  pop     rdi
0x18000bab4  retn
```
