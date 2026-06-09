# COleScript::GetScriptThreadState(ulong,tagSCRIPTTHREADSTATE *)

- ea: `0x180054250`
- end: `0x1800542be`
- name: `?GetScriptThreadState@COleScript@@UEAAJKPEAW4tagSCRIPTTHREADSTATE@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, enum tagSCRIPTTHREADSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180054250`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180054267`
- `KERNEL32!GetCurrentThreadId` at `0x180054267`

## pseudocode

```c
__int64 __fastcall COleScript::GetScriptThreadState(COleScript *this, DWORD a2, enum tagSCRIPTTHREADSTATE *a3)
{
  DWORD CurrentThreadId; // eax
  int v7; // ecx

  CurrentThreadId = a2;
  if ( a2 == -1 )
  {
    CurrentThreadId = GetCurrentThreadId();
  }
  else if ( a2 == -2 )
  {
    CurrentThreadId = *((_DWORD *)this + 61);
  }
  if ( !a3 )
    return 2147500035LL;
  *a3 = SCRIPTTHREADSTATE_NOTINSCRIPT;
  v7 = *((_DWORD *)this + 61);
  if ( v7 == -1 )
    return 2147549183LL;
  if ( CurrentThreadId != v7 )
    return 2147942487LL;
  *a3 = *((enum tagSCRIPTTHREADSTATE *)this + 67);
  return 0;
}

```

## disassembly

```asm
0x180054250  mov     [rsp+arg_0], rbx
0x180054255  push    rdi
0x180054256  sub     rsp, 20h
0x18005425a  mov     rdi, r8
0x18005425d  mov     eax, edx
0x18005425f  mov     rbx, rcx
0x180054262  cmp     edx, 0FFFFFFFFh
0x180054265  jnz     short loc_18005426F
0x180054267  call    cs:__imp_GetCurrentThreadId
0x18005426d  jmp     short loc_18005427A
0x18005426f  cmp     eax, 0FFFFFFFEh
0x180054272  jnz     short loc_18005427A
0x180054274  mov     eax, [rcx+0F4h]
0x18005427a  test    rdi, rdi
0x18005427d  jnz     short loc_180054286
0x18005427f  mov     eax, 80004003h
0x180054284  jmp     short loc_1800542B3
0x180054286  mov     dword ptr [rdi], 0
0x18005428c  mov     ecx, [rbx+0F4h]
0x180054292  cmp     ecx, 0FFFFFFFFh
0x180054295  jnz     short loc_18005429E
0x180054297  mov     eax, 8000FFFFh
0x18005429c  jmp     short loc_1800542B3
0x18005429e  cmp     eax, ecx
0x1800542a0  jz      short loc_1800542A9
0x1800542a2  mov     eax, 80070057h
0x1800542a7  jmp     short loc_1800542B3
0x1800542a9  mov     eax, [rbx+10Ch]
0x1800542af  mov     [rdi], eax
0x1800542b1  xor     eax, eax
0x1800542b3  mov     rbx, [rsp+28h+arg_0]
0x1800542b8  add     rsp, 20h
0x1800542bc  pop     rdi
0x1800542bd  retn
```
