# CWDMListener::OpenRemove(void)

- ea: `0x1800059a8`
- end: `0x180005a16`
- name: `?OpenRemove@CWDMListener@@QEAAKXZ`
- size: `110`
- prototype: `__int64 __fastcall(CWDMListener *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ad0`
- `0x180016aec`

## callees

- `0x180005000`
- `0x1800059a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a02`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800059e6`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800059e6`
- `WMICLNT!WmiOpenBlock` at `0x1800059c2`
- `WMICLNT!WmiOpenBlock` at `0x1800059c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWDMListener::OpenRemove(CWDMListener *this)
{
  __int64 v2; // rax
  DWORD LastError; // ebx

  if ( !(unsigned int)WmiOpenBlock((char *)this + 112, 1048580, (char *)this + 16) )
  {
    v2 = RegisterWaitForSingleObjectEx(*((_QWORD *)this + 2), CWDMListener::EvtCallBackRem, this, 0xFFFFFFFFLL, 8);
    *((_QWORD *)this + 4) = v2;
    if ( v2 )
      return 0;
  }
  LastError = GetLastError();
  CWDMListener::CloseRemove(this);
  return LastError;
}

```

## disassembly

```asm
0x1800059a8  mov     [rsp+arg_0], rbx
0x1800059ad  push    rdi
0x1800059ae  sub     rsp, 30h
0x1800059b2  mov     rdi, rcx
0x1800059b5  mov     edx, 100004h
0x1800059ba  add     rcx, 70h ; 'p'
0x1800059be  lea     r8, [rdi+10h]
0x1800059c2  call    cs:__imp_WmiOpenBlock
0x1800059c8  test    eax, eax
0x1800059ca  jnz     short loc_180005A02
0x1800059cc  mov     rcx, [rdi+10h]
0x1800059d0  lea     rdx, ?EvtCallBackRem@CWDMListener@@SAXPEAXE@Z; CWDMListener::EvtCallBackRem(void *,uchar)
0x1800059d7  or      r9d, 0FFFFFFFFh
0x1800059db  mov     [rsp+38h+var_18], 8
0x1800059e3  mov     r8, rdi
0x1800059e6  call    cs:__imp_RegisterWaitForSingleObjectEx
0x1800059ec  mov     [rdi+20h], rax
0x1800059f0  test    rax, rax
0x1800059f3  jz      short loc_180005A02
0x1800059f5  xor     eax, eax
0x1800059f7  mov     rbx, [rsp+38h+arg_0]
0x1800059fc  add     rsp, 30h
0x180005a00  pop     rdi
0x180005a01  retn
0x180005a02  call    cs:__imp_GetLastError
0x180005a08  mov     rcx, rdi; this
0x180005a0b  mov     ebx, eax
0x180005a0d  call    ?CloseRemove@CWDMListener@@QEAAKXZ; CWDMListener::CloseRemove(void)
0x180005a12  mov     eax, ebx
0x180005a14  jmp     short loc_1800059F7
```
