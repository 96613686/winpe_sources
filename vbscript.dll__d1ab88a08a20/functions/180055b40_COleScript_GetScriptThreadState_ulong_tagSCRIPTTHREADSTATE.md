# COleScript::GetScriptThreadState(ulong,tagSCRIPTTHREADSTATE *)

- ea: `0x180055b40`
- end: `0x180055bb5`
- name: `?GetScriptThreadState@COleScript@@UEAAJKPEAW4tagSCRIPTTHREADSTATE@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(COleScript *__hidden this, unsigned int, enum tagSCRIPTTHREADSTATE *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180055b40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180055b57`
- `KERNEL32!GetCurrentThreadId` at `0x180055b57`

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
0x180055b40  mov     [rsp+arg_0], rbx
0x180055b45  push    rdi
0x180055b46  sub     rsp, 20h
0x180055b4a  mov     rdi, r8
0x180055b4d  mov     eax, edx
0x180055b4f  mov     rbx, rcx
0x180055b52  cmp     edx, 0FFFFFFFFh
0x180055b55  jnz     short loc_180055B65
0x180055b57  call    cs:__imp_GetCurrentThreadId
0x180055b5e  nop     dword ptr [rax+rax+00h]
0x180055b63  jmp     short loc_180055B70
0x180055b65  cmp     eax, 0FFFFFFFEh
0x180055b68  jnz     short loc_180055B70
0x180055b6a  mov     eax, [rcx+0F4h]
0x180055b70  test    rdi, rdi
0x180055b73  jnz     short loc_180055B7C
0x180055b75  mov     eax, 80004003h
0x180055b7a  jmp     short loc_180055BA9
0x180055b7c  mov     dword ptr [rdi], 0
0x180055b82  mov     ecx, [rbx+0F4h]
0x180055b88  cmp     ecx, 0FFFFFFFFh
0x180055b8b  jnz     short loc_180055B94
0x180055b8d  mov     eax, 8000FFFFh
0x180055b92  jmp     short loc_180055BA9
0x180055b94  cmp     eax, ecx
0x180055b96  jz      short loc_180055B9F
0x180055b98  mov     eax, 80070057h
0x180055b9d  jmp     short loc_180055BA9
0x180055b9f  mov     eax, [rbx+10Ch]
0x180055ba5  mov     [rdi], eax
0x180055ba7  xor     eax, eax
0x180055ba9  mov     rbx, [rsp+28h+arg_0]
0x180055bae  add     rsp, 20h
0x180055bb2  pop     rdi
0x180055bb3  retn
```
