# PROTOCOL_HANDLE_OBJECT::AbortConnection(ulong)

- ea: `0x18009baec`
- end: `0x18009bbb6`
- name: `?AbortConnection@PROTOCOL_HANDLE_OBJECT@@QEAAXK@Z`
- size: `202`
- prototype: `void __fastcall(PROTOCOL_HANDLE_OBJECT *this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007148`
- `0x1800b1a54`
- `0x1800b1cfc`

## callees

- `0x18008da14`
- `0x18009baec`
- `0x1800cf1a8`
- `0x1800cf58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bb69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bb69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bb8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bba0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bb8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bba0`
- `webio!__imp_WebCancelProtocolHandle` at `0x18009bb98`
- `webio!__imp_WebCancelProtocolHandle` at `0x18009bb98`

## pseudocode

```c
void __fastcall PROTOCOL_HANDLE_OBJECT::AbortConnection(PROTOCOL_HANDLE_OBJECT *this, unsigned int a2)
{
  char *v4; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rcx

  if ( g_fKirHttpBugFix2605 )
  {
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_qD(1025, 15, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids, this);
  }
  else if ( (xmmword_180107A60 & 2) != 0 )
  {
    v4 = InternetMapError(a2);
    WPP_SF_qs(1025, 16, (unsigned int)WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids, (_DWORD)this, (__int64)v4);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  if ( *((_DWORD *)this + 132) )
  {
    LeaveCriticalSection(v5);
  }
  else
  {
    *((_DWORD *)this + 132) = 1;
    *((_DWORD *)this + 133) = a2;
    LeaveCriticalSection(v5);
    WebCancelProtocolHandle(*((_QWORD *)this + 54));
  }
}

```

## disassembly

```asm
0x18009baec  mov     [rsp+arg_0], rbx
0x18009baf1  mov     [rsp+arg_8], rsi
0x18009baf6  push    rdi
0x18009baf7  sub     rsp, 30h
0x18009bafb  cmp     cs:g_fKirHttpBugFix2605, 0
0x18009bb02  mov     esi, edx
0x18009bb04  mov     rbx, rcx
0x18009bb07  jz      short loc_18009BB31
0x18009bb09  test    byte ptr cs:xmmword_180107A60, 2
0x18009bb10  jz      short loc_18009BB5F
0x18009bb12  mov     edx, 0Fh
0x18009bb17  mov     dword ptr [rsp+38h+var_18], esi
0x18009bb1b  mov     ecx, 401h
0x18009bb20  lea     r8, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids
0x18009bb27  mov     r9, rbx
0x18009bb2a  call    WPP_SF_qD
0x18009bb2f  jmp     short loc_18009BB5F
0x18009bb31  test    byte ptr cs:xmmword_180107A60, 2
0x18009bb38  jz      short loc_18009BB5F
0x18009bb3a  mov     ecx, esi; unsigned int
0x18009bb3c  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x18009bb41  mov     edx, 10h
0x18009bb46  mov     [rsp+38h+var_18], rax
0x18009bb4b  mov     ecx, 401h
0x18009bb50  lea     r8, WPP_918dff8dee053ecc13ef49af7a3537cb_Traceguids
0x18009bb57  mov     r9, rbx
0x18009bb5a  call    WPP_SF_qs
0x18009bb5f  lea     rdi, [rbx+1E8h]
0x18009bb66  mov     rcx, rdi; lpCriticalSection
0x18009bb69  call    cs:__imp_EnterCriticalSection
0x18009bb6f  cmp     dword ptr [rbx+210h], 0
0x18009bb76  mov     rcx, rdi; lpCriticalSection
0x18009bb79  jnz     short loc_18009BBA0
0x18009bb7b  mov     dword ptr [rbx+210h], 1
0x18009bb85  mov     [rbx+214h], esi
0x18009bb8b  call    cs:__imp_LeaveCriticalSection
0x18009bb91  mov     rcx, [rbx+1B0h]
0x18009bb98  call    cs:__imp_WebCancelProtocolHandle
0x18009bb9e  jmp     short loc_18009BBA6
0x18009bba0  call    cs:__imp_LeaveCriticalSection
0x18009bba6  mov     rbx, [rsp+38h+arg_0]
0x18009bbab  mov     rsi, [rsp+38h+arg_8]
0x18009bbb0  add     rsp, 30h
0x18009bbb4  pop     rdi
0x18009bbb5  retn
```
