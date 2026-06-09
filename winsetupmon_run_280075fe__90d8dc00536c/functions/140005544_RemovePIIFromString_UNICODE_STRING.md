# RemovePIIFromString(_UNICODE_STRING *)

- ea: `0x140005544`
- end: `0x140005633`
- name: `?RemovePIIFromString@@YAEPEAU_UNICODE_STRING@@@Z`
- size: `239`
- prototype: `unsigned __int8 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001e808`

## callees

- `0x140003944`
- `0x140004670`
- `0x140005544`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400055c7`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x1400055c7`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140005583`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140005583`
- `FLTMGR!FltReleasePushLockEx` at `0x14000560f`
- `FLTMGR!FltReleasePushLockEx` at `0x14000560f`

## string_xrefs

- `0x140005564`: `Could not start profile list watch thread (0x%08X)`

## pseudocode

```c
bool __fastcall RemovePIIFromString(struct _UNICODE_STRING *a1)
{
  int v2; // eax
  int v3; // ebx
  PCWCH i; // r14
  wchar_t *Buffer; // rsi
  SIZE_T v6; // rbp
  wchar_t *v7; // r15
  wchar_t *v8; // rdi
  SIZE_T j; // rcx

  v2 = EnsureWatchingProfileList();
  v3 = v2;
  if ( v2 >= 0 )
  {
    FltAcquirePushLockSharedEx(&PushLock, 0);
    for ( i = (PCWCH)qword_140019420; i; i = *(PCWCH *)i )
    {
      Buffer = a1->Buffer;
      v6 = (unsigned __int64)i[4] >> 1;
      v7 = &Buffer[((unsigned __int64)a1->Length >> 1) - v6];
      while ( Buffer < v7 )
      {
        if ( !RtlCompareUnicodeStrings(Buffer, v6, *((PCWCH *)i + 2), v6, 1u) )
        {
          if ( v6 )
          {
            v8 = Buffer;
            for ( j = v6; j; --j )
              *v8++ = 35;
          }
          Buffer = &Buffer[v6 - 1];
        }
        ++Buffer;
      }
    }
    FltReleasePushLockEx(&PushLock, 0);
  }
  else
  {
    WriteLogMessage(3, L"Could not start profile list watch thread (0x%08X)", (unsigned int)v2);
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x140005544  push    rbx
0x140005546  push    rbp
0x140005547  push    rsi
0x140005548  push    rdi
0x140005549  push    r13
0x14000554b  push    r14
0x14000554d  push    r15
0x14000554f  sub     rsp, 30h
0x140005553  mov     r13, rcx
0x140005556  call    ?EnsureWatchingProfileList@@YAJXZ; EnsureWatchingProfileList(void)
0x14000555b  mov     ebx, eax
0x14000555d  test    eax, eax
0x14000555f  jns     short loc_14000557A
0x140005561  mov     r8d, eax
0x140005564  lea     rdx, aCouldNotStartP; "Could not start profile list watch thre"...
0x14000556b  mov     ecx, 3
0x140005570  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140005575  jmp     loc_14000561B
0x14000557a  xor     edx, edx
0x14000557c  lea     rcx, PushLock
0x140005583  call    cs:__imp_FltAcquirePushLockSharedEx
0x14000558a  nop     dword ptr [rax+rax+00h]
0x14000558f  mov     r14, cs:qword_140019420
0x140005596  jmp     short loc_140005601
0x140005598  movzx   ebp, word ptr [r14+8]
0x14000559d  movzx   eax, word ptr [r13+0]
0x1400055a2  mov     rsi, [r13+8]
0x1400055a6  shr     rbp, 1
0x1400055a9  shr     rax, 1
0x1400055ac  sub     rax, rbp
0x1400055af  lea     r15, [rsi+rax*2]
0x1400055b3  jmp     short loc_1400055F9
0x1400055b5  mov     r8, [r14+10h]; String2
0x1400055b9  mov     r9, rbp; String2Length
0x1400055bc  mov     rdx, rbp; String1Length
0x1400055bf  mov     [rsp+68h+CaseInSensitive], 1; CaseInSensitive
0x1400055c4  mov     rcx, rsi; String1
0x1400055c7  call    cs:__imp_RtlCompareUnicodeStrings
0x1400055ce  nop     dword ptr [rax+rax+00h]
0x1400055d3  test    eax, eax
0x1400055d5  jnz     short loc_1400055F5
0x1400055d7  test    rbp, rbp
0x1400055da  jz      short loc_1400055ED
0x1400055dc  mov     eax, 23h ; '#'
0x1400055e1  mov     rdi, rsi
0x1400055e4  movzx   eax, ax
0x1400055e7  mov     rcx, rbp
0x1400055ea  rep stosw
0x1400055ed  lea     rsi, [rsi+rbp*2]
0x1400055f1  add     rsi, 0FFFFFFFFFFFFFFFEh
0x1400055f5  add     rsi, 2
0x1400055f9  cmp     rsi, r15
0x1400055fc  jb      short loc_1400055B5
0x1400055fe  mov     r14, [r14]
0x140005601  test    r14, r14
0x140005604  jnz     short loc_140005598
0x140005606  xor     edx, edx
0x140005608  lea     rcx, PushLock
0x14000560f  call    cs:__imp_FltReleasePushLockEx
0x140005616  nop     dword ptr [rax+rax+00h]
0x14000561b  shr     ebx, 1Fh
0x14000561e  xor     bl, 1
0x140005621  mov     al, bl
0x140005623  add     rsp, 30h
0x140005627  pop     r15
0x140005629  pop     r14
0x14000562b  pop     r13
0x14000562d  pop     rdi
0x14000562e  pop     rsi
0x14000562f  pop     rbp
0x140005630  pop     rbx
0x140005631  retn
```
