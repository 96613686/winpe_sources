# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ulong)

- ea: `0x18001f764`
- end: `0x18001f863`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2K@Z`
- size: `255`
- prototype: `unsigned int(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180001fb0`
- `0x180006650`
- `0x180019fb0`

## callees

- `0x180007460`
- `0x18001f764`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001f7ef`
- `ntdll!EtwEventWrite` at `0x18001f7ef`
- `ntdll!EtwEventEnabled` at `0x18001f7a7`
- `ntdll!EtwEventEnabled` at `0x18001f7a7`

## string_xrefs

- `0x18001f80c`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001f841`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        _QWORD *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        signed int a5)
{
  unsigned int v5; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  EventManager *v12; // rcx
  signed int v13; // ebx
  __int64 v14; // r8
  unsigned int v15; // r8d
  unsigned int v17; // [rsp+20h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+28h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+38h] [rbp-50h] BYREF
  unsigned int *v20; // [rsp+48h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-38h]

  v5 = a5;
  if ( a5 > 0 )
    v5 = (unsigned __int16)a5 | 0x80070000;
  v10 = *a1;
  v17 = v5;
  if ( v10 )
  {
    if ( (unsigned __int8)EtwEventEnabled(v10, a2)
      && (CreateDataDescriptor(&v18, a3),
          CreateDataDescriptor(&v19, a4),
          v21 = 4,
          v20 = &v17,
          v11 = EtwEventWrite(*a1, a2, 3, &v18),
          (v13 = v11) != 0) )
    {
      EventManager::LogIt(v12, L"EventWrite error", v11);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
  }
  else
  {
    v13 = 1;
  }
  v14 = (unsigned __int16)v13;
  if ( v13 >= 0 )
    v14 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v14);
  return v15;
}

```

## disassembly

```asm
0x18001f764  push    rbx
0x18001f766  push    rbp
0x18001f767  push    rsi
0x18001f768  push    rdi
0x18001f769  sub     rsp, 68h
0x18001f76d  mov     rax, cs:__security_cookie
0x18001f774  xor     rax, rsp
0x18001f777  mov     [rsp+88h+var_30], rax
0x18001f77c  mov     eax, [rsp+88h+arg_20]
0x18001f783  mov     rbp, r9
0x18001f786  mov     rsi, r8
0x18001f789  mov     rdi, rdx
0x18001f78c  mov     rbx, rcx
0x18001f78f  test    eax, eax
0x18001f791  jg      loc_18001F831
0x18001f797  mov     rcx, [rcx]
0x18001f79a  mov     [rsp+88h+var_68], eax
0x18001f79e  test    rcx, rcx
0x18001f7a1  jz      loc_18001F85C
0x18001f7a7  call    cs:__imp_EtwEventEnabled
0x18001f7ad  test    al, al
0x18001f7af  jz      short loc_18001F7FB
0x18001f7b1  mov     rdx, rsi; unsigned __int16 *
0x18001f7b4  lea     rcx, [rsp+88h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f7b9  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f7be  mov     rdx, rbp; unsigned __int16 *
0x18001f7c1  lea     rcx, [rsp+88h+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f7c6  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f7cb  lea     rcx, [rsp+88h+var_68]
0x18001f7d0  mov     [rsp+88h+var_38], 4
0x18001f7d9  mov     [rsp+88h+var_40], rcx
0x18001f7de  lea     r9, [rsp+88h+var_60]
0x18001f7e3  mov     rcx, [rbx]
0x18001f7e6  mov     r8d, 3
0x18001f7ec  mov     rdx, rdi
0x18001f7ef  call    cs:__imp_EtwEventWrite
0x18001f7f5  mov     ebx, eax
0x18001f7f7  test    eax, eax
0x18001f7f9  jnz     short loc_18001F83E
0x18001f7fb  xor     ebx, ebx
0x18001f7fd  xor     ecx, ecx
0x18001f7ff  movzx   r8d, bx
0x18001f803  test    ebx, ebx
0x18001f805  mov     rdx, rdi
0x18001f808  cmovns  r8d, ecx
0x18001f80c  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001f813  call    TaskEventTrace
0x18001f818  mov     eax, r8d
0x18001f81b  mov     rcx, [rsp+88h+var_30]
0x18001f820  xor     rcx, rsp; StackCookie
0x18001f823  call    __security_check_cookie
0x18001f828  add     rsp, 68h
0x18001f82c  pop     rdi
0x18001f82d  pop     rsi
0x18001f82e  pop     rbp
0x18001f82f  pop     rbx
0x18001f830  retn
0x18001f831  movzx   eax, ax
0x18001f834  or      eax, 80070000h
0x18001f839  jmp     loc_18001F797
0x18001f83e  mov     r8d, ebx; unsigned int
0x18001f841  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f848  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f84d  test    ebx, ebx
0x18001f84f  jle     short loc_18001F7FD
0x18001f851  movzx   ebx, bx
0x18001f854  or      ebx, 80070000h
0x18001f85a  jmp     short loc_18001F7FD
0x18001f85c  mov     ebx, 1
0x18001f861  jmp     short loc_18001F7FD
```
