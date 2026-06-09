# CSsdpNotifyRequestManager::HrInitialize(void)

- ea: `0x18000d4cc`
- end: `0x18000d548`
- name: `?HrInitialize@CSsdpNotifyRequestManager@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c078`

## callees

- `0x18000683c`
- `0x18000d4cc`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d4e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000d4e6`

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
0x18000d4cc  mov     [rsp+arg_0], rbx
0x18000d4d1  push    rdi
0x18000d4d2  sub     rsp, 20h
0x18000d4d6  mov     rbx, rcx
0x18000d4d9  xor     edi, edi
0x18000d4db  xor     r9d, r9d; lpName
0x18000d4de  xor     r8d, r8d; bInitialState
0x18000d4e1  xor     ecx, ecx; lpEventAttributes
0x18000d4e3  lea     edx, [rdi+1]; bManualReset
0x18000d4e6  call    cs:__imp_CreateEventA
0x18000d4ed  nop     dword ptr [rax+rax+00h]
0x18000d4f2  mov     [rbx+0F8h], rax
0x18000d4f9  test    rax, rax
0x18000d4fc  jnz     short loc_18000D53A
0x18000d4fe  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000d503  mov     edi, eax
0x18000d505  test    eax, eax
0x18000d507  jz      short loc_18000D53A
0x18000d509  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d510  lea     rax, WPP_GLOBAL_Control
0x18000d517  cmp     rcx, rax
0x18000d51a  jz      short loc_18000D53A
0x18000d51c  test    byte ptr [rcx+1Ch], 1
0x18000d520  jz      short loc_18000D53A
0x18000d522  mov     rcx, [rcx+10h]
0x18000d526  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000d52d  mov     edx, 54h ; 'T'
0x18000d532  mov     r9d, edi
0x18000d535  call    WPP_SF_d
0x18000d53a  mov     rbx, [rsp+28h+arg_0]
0x18000d53f  mov     eax, edi
0x18000d541  add     rsp, 20h
0x18000d545  pop     rdi
0x18000d546  retn
```
