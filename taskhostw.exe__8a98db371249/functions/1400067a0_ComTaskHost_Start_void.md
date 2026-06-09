# ComTaskHost::Start(void)

- ea: `0x1400067a0`
- end: `0x140006882`
- name: `?Start@ComTaskHost@@QEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140009910`

## callees

- `0x1400067a0`
- `0x140009be0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400067d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400067d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400067ee`

## pseudocode

```c
__int64 __fastcall ComTaskHost::Start(ComTaskHost *this)
{
  char *v2; // rcx
  signed int LastError; // eax
  signed int v4; // edi

  (*(void (__fastcall **)(ComTaskHost *))(*(_QWORD *)this + 8LL))(this);
  v2 = (char *)_InterlockedExchange64(
                 (volatile __int64 *)this + 10,
                 (__int64)CreateThread(0, 0, ComTaskHost::StartTaskThread, this, 0, 0));
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 10, -1, -1) )
    return 0;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
    v4 = -2147467259;
  (*(void (__fastcall **)(ComTaskHost *))(*(_QWORD *)this + 16LL))(this);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400067a0  mov     [rsp+arg_0], rbx
0x1400067a5  mov     [rsp+arg_8], rsi
0x1400067aa  push    rdi
0x1400067ab  sub     rsp, 30h
0x1400067af  mov     rax, [rcx]
0x1400067b2  mov     rbx, rcx
0x1400067b5  xor     esi, esi
0x1400067b7  mov     rax, [rax+8]
0x1400067bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067c0  mov     r9, rbx; lpParameter
0x1400067c3  mov     [rsp+38h+lpThreadId], rsi; lpThreadId
0x1400067c8  lea     r8, ?StartTaskThread@ComTaskHost@@CAKPEAX@Z; lpStartAddress
0x1400067cf  mov     [rsp+38h+dwCreationFlags], esi; dwCreationFlags
0x1400067d3  xor     edx, edx; dwStackSize
0x1400067d5  xor     ecx, ecx; lpThreadAttributes
0x1400067d7  call    cs:__imp_CreateThread
0x1400067dd  mov     rcx, rax
0x1400067e0  xchg    rcx, [rbx+50h]; hObject
0x1400067e4  lea     rax, [rcx-1]
0x1400067e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400067ec  ja      short loc_1400067F4
0x1400067ee  call    cs:__imp_CloseHandle
0x1400067f4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400067fb  mov     rax, rcx
0x1400067fe  lock cmpxchg [rbx+50h], rcx
0x140006804  test    rax, rax
0x140006807  jnz     short loc_140006870
0x140006809  call    cs:__imp_GetLastError
0x14000680f  mov     edi, eax
0x140006811  test    eax, eax
0x140006813  jle     short loc_14000681E
0x140006815  movzx   edi, ax
0x140006818  or      edi, 80070000h
0x14000681e  test    edi, edi
0x140006820  mov     eax, 80004005h
0x140006825  cmovns  edi, eax
0x140006828  mov     rax, [rbx]
0x14000682b  mov     rcx, rbx
0x14000682e  mov     rax, [rax+10h]
0x140006832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006837  mov     rcx, cs:WPP_GLOBAL_Control
0x14000683e  lea     rax, WPP_GLOBAL_Control
0x140006845  cmp     rcx, rax
0x140006848  jz      short loc_14000686C
0x14000684a  test    byte ptr [rcx+1Ch], 1
0x14000684e  jz      short loc_14000686C
0x140006850  mov     rcx, [rcx+10h]
0x140006854  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x14000685b  mov     edx, 0Ch
0x140006860  mov     [rsp+38h+dwCreationFlags], edi
0x140006864  mov     r9, rbx
0x140006867  call    WPP_SF_qD
0x14000686c  mov     eax, edi
0x14000686e  jmp     short loc_140006872
0x140006870  mov     eax, esi
0x140006872  mov     rbx, [rsp+38h+arg_0]
0x140006877  mov     rsi, [rsp+38h+arg_8]
0x14000687c  add     rsp, 30h
0x140006880  pop     rdi
0x140006881  retn
```
